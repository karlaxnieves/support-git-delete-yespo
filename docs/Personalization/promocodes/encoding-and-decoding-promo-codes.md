---
title: Encoding and Decoding Promo Codes Using PHP/JAVA
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Encoding and Decoding Promo Codes Using PHP/JAVA | Yespo Guide
  description: >-
    The document provides guidelines for implementing promo code substitution
    using PHP or Java, detailing the format of Yespo promo codes, checksum
    calculation, and encoding/decoding processes using Triple DES and Base32,
    along with code examples in Java and PHP.
  robots: index
next:
  description: ''
---
If general methods of substituting promo codes do not suit you, consider implementing this task using PHP/JAVA.

## The promo code format supported by Yespo

The promo code contains the date until which it is valid, the type of promotion, the discount amount and the checksum.  
As a result, we get a line like

```
<YY><MM><DD><Promo type><Discount><CRC>
```

[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Length",
    "h-2": "Description",
    "h-3": "Example",
    "0-0": "YY",
    "0-1": "2 symbols",
    "0-2": "Year, two-digit number",
    "0-3": "15, 54",
    "1-0": "MM",
    "1-1": "2 symbols",
    "1-2": "Month, two-digit number, can be padded on the left with a zero",
    "1-3": "01, 12",
    "2-0": "DD",
    "2-1": "2 symbols",
    "2-2": "Day, two-digit number, can be padded on the left with a zero",
    "2-3": "06, 28",
    "3-0": "Promo type",
    "3-1": "1 symbol",
    "3-2": "Type of promo code, can take a value from 0 to 31, encoded by a character from the alphabet <a rel=\"nofollow\" href=\"https://tools.ietf.org/html/rfc4648#section-6\" target=\"_blank\">Base32</a>",
    "3-3": "A, D, X",
    "4-0": "Discount",
    "4-1": "2 symbols",
    "4-2": "Discount amount in %, two-digit number, can be padded with zero on the left",
    "4-3": "15, 02",
    "5-0": "CRC",
    "5-1": "1 symbol",
    "5-2": "Checksum - one of the values from the alphabet <a rel=\"nofollow\" href=\"https://tools.ietf.org/html/rfc4648#section-6\" target=\"_blank\">Base32</a>",
    "5-3": "B, N, Z"
  },
  "cols": 4,
  "rows": 6,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


The result is a 10-character string like this: **151231Y16N**

> 📘 Note
> 
> The value of promo codes depends on the block parameters and the current calendar date. That is, during the day, all contacts will receive the same promo code if no changes are made to the block parameters. Tracking the use of the promo code and its expiration date should be on your side.

### Promo type usage example

0 - valid for all items in the cart (Must Have)  
1 - valid only for A category  
2 - valid only for B category…

> 📘 Note
> 
> When using promo types in this way, send a file to Yespo support indicating which product category corresponds to one or another promo type.

### Checksum calculation algorithm (CRC)

1. sums the <a rel="nofollow" href="https://tools.ietf.org/html/rfc4648#section-6" target="_blank">ASCII</a> decimal value of each character in the source string in order.

2. the amount received is divided with the remainder by 32.

3. the resulting remainder is used as the character index in the <a rel="nofollow" href="https://tools.ietf.org/html/rfc4648#section-6" target="_blank">Base32</a> alphabet; the character at this index will be the checksum.

Java code example:

```java
public static final String BASE32_ALPHABET = "ABCDEFGHIJKLMNOPQRSTUVWXYZ234567";

public char checkSum(String data) {
    int sum = 0;
    for (char c : data.toCharArray()) {
		sum += c;
}
    return BASE32_ALPHABET.charAt(sum % BASE32_ALPHABET.length()); 
}
```

## Promo code encoding/decoding

Symmetric encryption algorithm <a rel="nofollow" href="https://en.wikipedia.org/wiki/Triple_DES" target="_blank">Triple DES</a> is used for encoding/decoding.

The encrypted data is encoded using <a rel="nofollow" href="https://tools.ietf.org/html/rfc4648#section-6" target="_blank">Base32</a> to obtain a human-readable text.

Encryption parameters:

- key 24 bytes long
- initialisation\_vector 8 bytes long
- encryption mode: CFB8 (Cipher Feedback Mode)
- <a rel="nofollow" href="https://en.wikipedia.org/wiki/Padding_(cryptography)" target="_blank">padding</a>: NoPadding
  ### The sequence of actions when encoding a promo code

1. An encryption algorithm <a rel="nofollow" href="https://en.wikipedia.org/wiki/Triple_DES" target="_blank">Triple DES</a> is applied to the promotional code.
2. The data received using encryption is encoded with the <a rel="nofollow" href="https://tools.ietf.org/html/rfc4648#section-6" target="_blank">Base32</a> alphabet to obtain a human-readable text.
3. “-” symbols are added to the promotional code after every 4 characters for readability.

### The sequence of actions when decoding a promo code

1. “-” symbols are deleted.
2. First, the data is decoded using <a rel="nofollow" href="https://tools.ietf.org/html/rfc4648#section-6" target="_blank">Base32</a>.
3. The decoded data is then decrypted using <a rel="nofollow" href="https://en.wikipedia.org/wiki/Triple_DES" target="_blank">Triple DES</a>.
4. You should get a string of 10 characters, according to the format described above. A checksum is used to check the correctness of the decryption.

## Secret key

For encoding and decoding promo codes, a secret key is used on the side of Yespo and on the side of the service that checks promo codes.

Generate a key in such format: eSSuperKeyXXXXXXXXXXXXXX, where xxx… - random numbers. Come up with an initialization vector: 12345678.

> 🚧 
> 
> The initialization vector must always be **12345678**.

Pass both of these values to Yespo support.

## Java code example

```java
package promocode;

import java.security.spec.KeySpec;

import javax.crypto.Cipher;
import javax.crypto.SecretKey;
import javax.crypto.SecretKeyFactory;
import javax.crypto.spec.DESedeKeySpec;
import javax.crypto.spec.IvParameterSpec;

import org.apache.commons.codec.binary.Base32;

public class CryptData {
	private KeySpec keySpec;
	private SecretKey key;
	private IvParameterSpec iv;

	public CryptData(String keyString, String ivString) {
		try {
			keySpec = new DESedeKeySpec(keyString.getBytes("UTF-8"));

			key = SecretKeyFactory.getInstance("DESede")
					.generateSecret(keySpec);

			iv = new IvParameterSpec(ivString.getBytes("UTF-8"));
		} catch (Exception e) {
			e.printStackTrace();
		}
	}

	public String encrypt(String value) {
		try {
			Cipher ecipher = Cipher.getInstance("DESede/CFB8/NoPadding");

			// "SunJCE");
			ecipher.init(Cipher.ENCRYPT_MODE, key, iv);

			if (value == null)
				return null;

			// Encode the string into bytes using utf-8
			byte[] valeur = value.getBytes("UTF-8");

			// Encrypt
			byte[] enc = ecipher.doFinal(valeur);

			// Encode bytes to base64 to get a string
			String encodedString = new String(new Base32().encode(enc), "UTF-8");
			StringBuilder sb = new StringBuilder();
			for (int i = 0 ; i < encodedString.length(); ++i) {
				if (0 != i && i % 4 == 0) {
					sb.append("-");
				}
				sb.append(encodedString.charAt(i));
			}
			return sb.toString();
		} catch (Exception e) {
			e.printStackTrace();
		}
		return null;
	}
	
	public static void main(String[] args) {
		String encrypt = new CryptData("eSSuperKeyXXXXXXXXXXXXXX", "12345678").encrypt("770101K99N");
		System.err.println(encrypt);
	}
}
```

## PHP code example

```php
 'A',
        1 => 'B',
        2 => 'C',
        3 => 'D',
        4 => 'E',
        5 => 'F',
        6 => 'G',
        7 => 'H',
        8 => 'I',
        9 => 'J',
        10 => 'K',
        11 => 'L',
        12 => 'M',
        13 => 'N',
        14 => 'O',
        15 => 'P',
        16 => 'Q',
        17 => 'R',
        18 => 'S',
        19 => 'T',
        20 => 'U',
        21 => 'V',
        22 => 'W',
        23 => 'X',
        24 => 'Y',
        25 => 'Z',
        26 => 2,
        27 => 3,
        28 => 4,
        29 => 5,
        30 => 6,
        31 => 7,
        32 => '=',
    );
    /**
     * Table for decoding base32
     *
     * @var array
     */
    private static $decode = array(
        'A' => 0,
        'B' => 1,
        'C' => 2,
        'D' => 3,
        'E' => 4,
        'F' => 5,
        'G' => 6,
        'H' => 7,
        'I' => 8,
        'J' => 9,
        'K' => 10,
        'L' => 11,
        'M' => 12,
        'N' => 13,
        'O' => 14,
        'P' => 15,
        'Q' => 16,
        'R' => 17,
        'S' => 18,
        'T' => 19,
        'U' => 20,
        'V' => 21,
        'W' => 22,
        'X' => 23,
        'Y' => 24,
        'Z' => 25,
        2 => 26,
        3 => 27,
        4 => 28,
        5 => 29,
        6 => 30,
        7 => 31,
        '=' => 32,
    );
    /**
     * Creates an array from a binary string into a given chunk size
     *
     * @param string $binaryString String to chunk
     * @param integer $bits Number of bits per chunk
     * @return array
     */
    private static function chunk($binaryString, $bits)
    {
        $binaryString = chunk_split($binaryString, $bits, ' ');
        if (substr($binaryString, (strlen($binaryString)) - 1)  == ' ') {
            $binaryString = substr($binaryString, 0, strlen($binaryString)-1);
        }
        return explode(' ', $binaryString);
    }
    /**
     * Encodes into base32
     *
     * @param string $string Clear text string
     * @return string Base32 encoded string
     */
    public static function encode($string)
    {
        if (strlen($string) == 0) {
            // Gives an empty string
            return '';
        }
        // Convert string to binary
        $binaryString = '';
        foreach (str_split($string) as $s) {
            // Return each character as an 8-bit binary string
            $s = decbin(ord($s));
            $binaryString .= str_pad($s, 8, 0, STR_PAD_LEFT);
        }
        // Break into 5-bit chunks, then break that into an array
        $binaryArray = self::chunk($binaryString, 5);
        // Pad array to be divisible by 8
        while (count($binaryArray) % 8 !== 0) {
            $binaryArray[] = null;
        }
        $base32String = '';
        // Encode in base32
        foreach ($binaryArray as $bin) {
            $char = 32;
            if (!is_null($bin)) {
                // Pad the binary strings
                $bin = str_pad($bin, 5, 0, STR_PAD_RIGHT);
                $char = bindec($bin);
            }
            // Base32 character
            $base32String .= self::$encode[$char];
        }
        return $base32String;
    }
    /**
     * Decodes base32
     *
     * @param string $base32String Base32 encoded string
     * @return string Clear text string
     */
    public static function decode($base32String)
    {
        if (strlen($base32String) == 0) {
            // Gives an empty string
            return '';
        }
        // Only work in upper cases
        $base32String = strtoupper($base32String);
        // Remove anything that is not base32 alphabet
        $pattern = '/[^A-Z2-7]/';
        $base32String = preg_replace($pattern, '', $base32String);
        $base32Array = str_split($base32String);
        $string = '';
        foreach ($base32Array as $str) {
            $char = self::$decode[$str];
            // Ignore the padding character
            if ($char !== 32) {
                $char = decbin($char);
                $string .= str_pad($char, 5, 0, STR_PAD_LEFT);
            }
        }
        while (strlen($string) %8 !== 0) {
            $string = substr($string, 0, strlen($string)-1);
        }
        $binaryArray = self::chunk($string, 8);
        $realString = '';
        foreach ($binaryArray as $bin) {
            // Pad each value to 8 bits
            $bin = str_pad($bin, 8, 0, STR_PAD_RIGHT);
            // Convert binary strings to ASCII
            $realString .= chr(bindec($bin));
        }
        return $realString;
    }
}

    $base32 = new Base32;
    $key = "eSSuperKeyXXXXXXXXXXXXXX";
    $iv = "12345678";
    $encoded = "ILDD-2V7W-SBWD-2X34";

    echo "DECODED: " . mcrypt_decrypt(MCRYPT_3DES, $key, $base32::decode(str_replace("-", "", $encoded)), MCRYPT_MODE_CFB, $iv) . "\n";
?>
```

> 📘 Note
> 
> In order not to spend effort on transforming the code into a human-readable form, use Format Preserving Encryption