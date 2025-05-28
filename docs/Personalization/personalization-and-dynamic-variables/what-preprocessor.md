---
title: Using Preprocessor
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using Preprocessor | Yespo Guide
  description: >-
    The document provides an overview of a preprocessor tool used for creating
    dynamic content in  messages, detailing its capabilities, supported types,
    technical setup, file upload process, and examples of use, with a focus on
    personalization and flexibility in content delivery.
  robots: index
next:
  description: ''
---
- [Definition](https://docs.yespo.io/docs/what-preprocessor#definition)
- [Supported types](https://docs.yespo.io/docs/what-preprocessor#supported-types)
- [How it works](https://docs.yespo.io/docs/what-preprocessor#how-it-works)
- [How to upload file for preprocessor](https://docs.yespo.io/docs/what-preprocessor#how-to-upload-file-for-preprocessor)
- [How to create letter using preprocessor](https://docs.yespo.io/docs/what-preprocessor#how-to-create-letter-using-preprocessor)
- [How to test data for mailing](https://docs.yespo.io/docs/what-preprocessor#how-to-test-data-for-mailing)
- [Examples of use](https://docs.yespo.io/docs/what-preprocessor#examples-of-use)

## Definition

It is a mechanism for constructing dynamic content in letters on the basis of data, prepared beforehand: recommendations in letters, the mutual order of blocks, random selection of goods, urgent offers for different user categories.

All these can be realized with preprocessor without integration with the third service, routine and useless update of additional contact’s fields and use both for mass mailing and trigger emails.

Besides, you can use personalization not only in emails, but also in SMS messages. 

Сapabilities of Preprocessor are very wide and they are not limited by existing functionality. We can easily expand them by adding new logic of external data handling. So if you need a unique or even “strange” feature, email us, we will discuss it and try to shortly realize your requirements.

## Supported types

Next types of preprocessor are available now for public use:

- Key 
- Random

**Key preprocessor** chooses the structure from data array by indicated key, for example, by email, and transfers it in the letter template before sending. You can prepare the list of personal recommendations especially for each contact in {email: json with recommendations} format where email acts as a key. And when sending the mailing for all contacts with the email from the list of a preprocessor, one’s json will be received and it will be used in the letter.  

This approach can show each subscriber its own set of recommended goods, the sales and special offers.

**Random preprocessor** chooses randomly several json structures from prepared data array and transfers them in the letter. You certainly heard that block in the letter with goods offers works very good. Imagine that you have a big contact database and a huge assortment of goods. For example, you want to propose rucksacks for school for the very fetching price. If specific rucksack will be indicated, it will be sold fast and there needs to be alternative for other clients.

At the same time, you have 100 identical rucksacks in quality and attraction. They can all be loaded in Random preprocessor and 3 random models can be shown in each letter. Then rucksacks will be sold approximately evenly and success of each item can be checked by sale quantity / transfers that they brought.

## How it works

In this section, the accent is more for the technical part of realization. If you are not a programmer and understood nothing here, don’t be upset – it is not necessary. But for receiving the conception of insides – I recommend you to become acquainted with this section.

It is necessary to configure two interrelated parts of the preprocessor for its mechanism started to work. Firstly, to create a file with the data structure in necessary format for loading. Secondly, add code in the letter, with the help of which the dynamic content will be generated and placed in the letter “on-the-fly” when sending it.

**The Key type preprocessor** allows loading personal set of goods for each client that is why the data structure needs to be next:

```json
{“test1@mail.com” : [{...}, {...}], “test2@mail.com” : [{...}, {...}, {...}], “test3@mail.com” : [{...}, {...}]},
```

where `[test1@mail.com](mailto:test1@mail.com)`, `[test2@mail.com](mailto:test2@mail.com)`, `[test3@mail.com](mailto:test3@mail.com)` – recipient email-address (or phone number), the data array for substitution in the letter corresponds to each of them.

**Random type preprocessor** allows choosing random structure from the set for placing them in letters for recipients. The file structure for it looks following:

```json
{“test@mail.com” : [{...}, {...}, {...}, {...}, {...}, {...}]},
```

in this case, any email can be indicated – it doesn’t matter; and the only array contains all data set for random selection.

When sending letters the preprocessor determines, exactly what data structure will be transferred in the letter. If Key type is used – the structure, assigned for a specific recipient, is transferred; if Random type is used – the structure is determined in random order. The resulting data array can be used in the letter with the help of special instructions, indicated as a code. These instructions include conditional operators and cycles that allows showing in a sufficiently flexible way the dynamic content in the body of the letter.

Note. The preprocessor also can be used for [SMS-mailing](https://docs.yespo.io/docs/creation-sms). The principles of its work for SMS stay the same.

## How to upload file for preprocessor

**Using API**

API method, which allows you to upload a file with data in the system, now is in development stage.

**In Personal account**

To upload a file using the Personal account, carry out the following actions:

- open settings;

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6925ddd3fd66746b846cda8ea1aa3e2e906e84586d4a71269a114aad779164f4-Dashboard.webp",
        "Open settings",
        "Open settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- click “Upload” button

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e8d9912cda9e0f9df00d91ce7a20670b27fa71149b465bfedfcff8cc85e9531f-Settings.webp",
        "Choose preprocessor",
        "Choose preprocessor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- choose preprocessor type, for example, we will choose Key type (setting preprocessor with Random type will be similar);

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2128e66b647437764144bba114db5a44d448305836a207cf1228fa5f426ab670-Preprocessor.webp",
        "Choose preprocessor type",
        "Choose preprocessor type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- drag your file of preprocessor;  
- then click “Upload”.

The notification about successful uploading will be sent as a message in your Personal account and via email.

## How to create letter using preprocessor

For inserting dynamic content in the letter the special template processor is used – _Apache Velocity_. Exactly it allows realizing conditional operators, cycles and other operations with data directly in the body of the letter. All dynamic content, available when sending, is contained in special system variable `$data`. After loading the file it needs to be chosen when forming the letter. For this:

- after creating the letter, click “Show settings” in the message editor;

  [block:image]{"images":[{"image":["https://files.readme.io/a9453c09acf357a51947076d7b66016d801c9f71d2fa13c6795c0eecc8d6441e-prepr7.webp",null,"Show settings"],"align":"center","sizing":"% "}]}[/block]

  - then choose preprocessor type (for example we chosen Key type, for adding file with Random type preprocessor actions will be similar);

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae7f93764f8497cf1a19ba4c7b4614d7ae0c848496276ea8b261e46a8fe96abd-prepr8.webp",
        null,
        "Key preprocessor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- choose file, uploaded during the previous stage

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9b0be6ecddc312b793f95e4cb7c93aec0da28e176e07315afbb51d1e85fb6b1-prepr9.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


 Thus, uploaded file during the previous stage will be used when sending a current letter.

Data array, determined by the preprocessor, is contained in the array with “recommendations” name. To obtain access to it, use the following construction:  

```json
$data.get('recommendations')
```

For organizing cycle by this array, write the following.

The name of `$item` variable can be arbitrary, but the field with the name _name_ needs to be contained for each element in the file with data, if you are going to address to it in the letter by such name.  
Conditional operation can also be easily done:  

```json
#if($item.get('discount') == 0)
	…
#else
	…
#end
```

Instead of ellipsis in both cases you can substitute arbitrary fragment of HTML-code (though keeping its general integrity within the limits of the letter).

## How to test data for mailing

There is very convenient functionality in the development stage: the review of a prepared letter for a specific recipient. When it will be ready, you will be able to specify email of a specific recipient and see the letter, which will be formed for him by the preprocessor. We will make all efforts for realizing this opportunity as soon as possible.

From already available facilities for testing, we can offer the mailing for the test group. For Key type preprocessor it is necessary for you to form a group of several contacts, whose emails will be contained in the data file; then choose necessary file in the message and activate mailing for this group. In the case with Random type preprocessor there is no need to additionally worry about existence of addresses in the file – it can be tested for any addresses.

## Examples of use

### Addressing elements by index

The result after substitution of dynamic content can look in the following way:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee95d783627e753ff4e9b0cbefbe749ac54b462efe6f917851c31384bcdd07a5-prepr10.webp",
        null,
        "items_by_indexes"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The letter in edit mode looks in the following way:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6b4cc616d929d8092b43f6a423c72a0656ac5bdae89c8ab0f10c116771468439-prepr11.webp",
        null,
        "items_by_indexes_result"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Addressing elements in the cycle

The letter in edit mode looks in the following way:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5523b178dd6def46c4e5b6b067fb2382400fe2fe31ca8c3e2bfe4eeec3b7967f-prepr12.webp",
        null,
        "items_by_foreach"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


The result after substitution the dynamic content can look in the following way:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/910a1eb61c4b59d2e2c45a4c61577514b488aaa40099773dd60379565e8dbdb8-prepr14.webp",
        null,
        "items_by_foreach_result"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you have problems with forming velocity-code in the letter, or you have more questions for more difficult examples of its use, then described in this section – address to our [technical support](mailto:support@yespo.io).