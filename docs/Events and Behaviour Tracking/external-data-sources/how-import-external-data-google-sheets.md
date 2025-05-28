---
title: Import External Data from Google Sheets
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Import External Data from Google Sheets | Yespo Guide
  description: >-
    Google Sheets is an internal data source. You can import data from
    spreadsheets and use it to build personalized recommendations in emails or
    segment contacts.
  robots: index
next:
  description: ''
---
External data sources are used for recommendations in emails and for contact base segmentation.

1. Go to your personal profile → *Settings → Data Sources*, click *New data source* and select *External data sources*.

<Image align="center" width="80% " src="https://files.readme.io/f5fe2515dd57e6daa551c6c34239697a024067ecb7198b3dea8a7fd698fe435b-import-external-data-from-gs-001.webp" />

2. Select *Google Sheets*.

<Image align="center" width="80% " src="https://files.readme.io/f6631291308ee0f6d633e8347ce1f1344fc7827223a837fe33bfc37cdf8c90c0-import-external-data-from-gs-002.webp" />

3. Enter a name and description and insert the link to the corresponding Google Spreadsheet.

<Image align="center" width="80% " src="https://files.readme.io/19487ec551a57ed8da060c2c0cb4368467846d102884c42bc960112c59a898a0-import-external-data-from-gs-003.webp" />

Make sure that:

* The file is accessed by anyone with the link, without Google authorization required.

<Image align="center" width="80% " src="https://cdn.esputnik.com/photos/shares/Support/Images/GoogleSheets/image11.webp" />

* The first line of the sheet contains headers in Latin.

<Image align="center" width="80% " src="https://files.readme.io/d60b13ebf946b3a2a521d79df4b8472066980f76dc5d237ef67fbc674d6787a6-image6.webp" />

* The data you will use is contained in the first sheet.

<Image align="center" width="80% " src="https://files.readme.io/84c70ba95a850cbadc9bbb425b58fae2ac03b66cf8cc632929f22c01c612c38e-image14.webp" />

* For [multilingual messages](https://docs.yespo.io/docs/creating-multilingual-campaigns), name the file sheets with the corresponding language codes according to <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes" target="_blank">ISO 639-1</a> (e.g., en) or RFC 5646 for dialects (e.g., es-MX).

> 📘 Note
>
> Multilingualism in messages is not supported for all dialects, if you did not find the one you need, please contact our support at [support@yespo.io](mailto:support@yespo.io).

<Image align="center" width="80% " src="https://files.readme.io/d0c3768fa2b3da9bd052c470b5552f4dd04c6e6e3643a72a48bc271d50b3cd9c-image8.webp" />

Specify the default language for the message this data source will be used in. If the default language is not specified, the content in the language of the first sheet will be used in the message.

4. Click *Refresh data*. Data from the spreadsheet will be available for preview. By default, only the first 10 lines are previewed.

<Image align="center" width="80% " src="https://files.readme.io/4cc0ac125030701aea5e0ff7c4af0a143d4c761851987b5a6fccf8d9783220b6-import-external-data-from-gs-004.webp" />

5. Click *Advanced settings* to specify the number of recommended items that will be displayed in the email. The message will not be sent if the quantity of products in the feed doesn’t match the specified range.
6. Click *Save*. The created data source will be available in the general list. To remove it, click three dots on the right → *Delete*.

<Image align="center" width="80% " src="https://files.readme.io/e8ecc827ce0444d993ad154c53f725da65d5c554f09faefd0b34ea4d60202df8-import-external-data-from-gs-005.webp" />

If you need to edit the data (for example, in case of a typo or no longer valid prices), make necessary edits to the Google Spreadsheet, and click *Refresh data* in the corresponding data source. Changes will be applied immediately.

<Image align="center" width="80% " src="https://files.readme.io/04e2493c9f7aa537cd45e7241787f4501d5f8d207584c582f620c16a20bbf67a-import-external-data-from-gs-006.gif" />

## How to Add Data from Google Spreadsheet to an Email

The data is added to the email via [Velocity](https://docs.yespo.io/docs/introduction-to-velocity).

1. In *Messages → Messages*, select an email with configured dynamic modules or create a new one.
2. Click the stripe with product cards, click *Code editor* and insert the code with the corresponding data source as shown below.

<Image align="center" width="80% " src="https://files.readme.io/cb6a1191a4dc42ee744de6ecb36d934d14647668b64e93e2b1b5e363be7a957e-import-external-data-from-gs-007.webp" />

3. Make sure the stripe with dynamic content ends with the code `!--#end--`.

<Image align="center" width="80% " src="https://files.readme.io/ab4c397294b7a8fc52ffe5bde231511f589bc3d8351dd73b1a1d04b3f808adcb-image13.webp" />

4. Specify product parameters from the spreadsheet (name, link, image and prices here) and add their variables to each product card:

* `$!item.get('Name')`
* `$!item.get('Link')`
* `$!item.get('Image')`
* `$!item.get('Old Price')`
* `$!item.get('New Price')`

<Image align="center" width="80% " src="https://files.readme.io/929764bc5413a9e4b86608090f8b71271a087f12dec580e8dd465e488338cbe7-image4.gif" />

5. To test whether the product data is inserted correctly, send a test email.

<Image align="center" width="80% " src="https://files.readme.io/2552544a1454e973e27aead781365cd298197ec479eee210a998a350083b28d9-import-external-data-from-gs-008.webp" />

If you’ve set everything right, the data from the website will be added at the moment of the launch, and the email would look as follows:

<Image align="center" width="80% " src="https://files.readme.io/ba22e58f3803dbb1ecd8b7b947b562798a69f46ea42d4d9e6ebab775bf203354-email-with-dynamic-content.webp" />

You can change the data in the spreadsheet and refresh the data source, and the updates will be applied immediately. They will be available for new campaigns; products in already sent campaigns will not change.
