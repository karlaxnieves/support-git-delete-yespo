---
title: Contact Fields in the System
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Contact Fields in the System | Yespo Guide
  description: >-
    The document provides guidelines for managing contact fields in a database,
    including preparing files for upload, mapping fields during import, and
    formatting various data types like names, emails, phone numbers, and
    addresses to ensure accurate data storage and segmentation.
  robots: index
next:
  description: ''
---
Contact fields are used to store and gather information about your subscribers and customers, such as their names, dates of birth, locations, and so on. You can use this data to create [audience segments](https://docs.yespo.io/docs/how-add-dynamic-segment) or [personalize](https://docs.yespo.io/docs/personalization-and-dynamic-variables) message content.

## Preparing a File for Uploading 

Before uploading the database into the system, please check the following:

1. The imported file must be in one of the following formats: `xlsx`,` xls`, `csv` or `txt`, and up to 300 MB.
2. Contact base must contain emails and/or phone numbers for import.
3. You must save all contacts in one worksheet (Excel) and organize them into columns. If the file contains two or more worksheets, the system will not process them: only the contacts from the first worksheet will be imported.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e453a3930ebaffe0aa51cc1a42d91df0751b093d331558fdd9fbbe3a23c7eff0-contact-fields-in-the-system-001.webp",
        null,
        "Example of the imported file"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When importing contacts into Yespo, map the columns in your import file with the fields in the system. If the contact fields have errors or the wrong format, this data will not be saved in the system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8fb12df285c5939438d3093c93cf7b36a34ab5b2f69ac189b08fd9e582103eb2-contact-fields-in-the-system-002.webp",
        null,
        "Mapping columns"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Viewing a Contact Card

Go to _Contacts_ → _All contacts_ and select the contact or click _New contact_ to create a new one.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/533a40e632f31001e061a647c9efffd7da4523e296ea23d78a13864025abd98c-contact-fields-in-the-system-201.webp",
        null,
        "Viewing a contact card"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The card stores all the data uploaded via import or transferred via API.

## Basic Fields Format

By default, the following standard fields are available when creating a new contact:

### First Name

The maximum field value length is 40 characters.

Letters of any alphabet and up to 3 digits are allowed.

Special characters are prohibited, except:

- apostrophes in the middle of a word
- hyphens in the middle of a word or between words without spaces
- a dot at the end of a short (up to 3 characters) word (for example, Jr.)

It is allowed to use 3 words of more than 3 characters and 3 words of a maximum of 3 characters. Names exclusively composed of numbers and/or special characters are prohibited.

### Last Name

The validation rules of the Last name field are the same as for the _First name_, except that any number of words of any length are allowed (but not more than 40 characters in total).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d203246eec8bc480a9142ea697ead98af8fd9210f574146d4ae45c5537dc58ae-contact-fields-in-the-system-203.webp",
        null,
        "First name and last name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Email

This is the main field used to send emails. 

One email line available for each contact. Ensure the email address has no spelling mistakes (**gmeil.com** instead of **gmail.com**, etc.). If you want to specify several emails, you may [create an additional field](https://docs.yespo.io/docs/how-add-additional-contact-fields), but the system will send an email only to the address specified in the main field. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/68e62dfa6fcd350260206ecd99ddc9e282cbcc71c7a0227f26815c20788941bb-contact-fields-in-the-system-204.webp",
        null,
        "Email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Phone Number

Use phone numbers to send SMS and Viber messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a9deecc98a0255ea46419d3fdf579951e6e7384cb19ac6fd9be9903707d8e4f-contact-fields-in-the-system-205.webp",
        null,
        "Phone number"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If your contact database contains different country codes, enter the phone number in the international format: 

\+380955547708

\+447911123456

\+0207183 8750

\+1229501112325

You cannot add text or special characters to the field.

### Address

 Address consists of the following fields:

- Address
- Town
- Region
- Postcode
- Description

Use the _Address_ field to record the contact's address. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e57237fa7cb0e85af529a475d0994af78a8aa66ef929e4e5c08272d20bd0fdb5-contact-fields-in-the-system-206.webp",
        null,
        "Address"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> In the imported file, you must divide the contact's address into columns: address, town, region, postcode and description separately.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cfc129e96dcf16a50f391dccca3f27711af39e425105940c6998acabf5316d29-contact-fields-in-the-system-008.webp",
        null,
        "Address format in the import file"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Language

Use the _Language_ field for segmentation and [multilingual campaigns](https://docs.yespo.io/docs/creating-multilingual-campaigns). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4cf67b751ee3c08902be7cf93167e96d614e31fac89c72118c666c96fd581362-contact-fields-in-the-system-009.webp",
        null,
        "Language"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Language supports text coded according to the international standard of  <a rel="nofollow" href="https://gist.github.com/msikma/8912e62ed866778ff8cd#file-rfc5646-language-tags-js-L41" target="_blank"> RFC 5646 Language Tags:</a>

- "es," "en";
- "es-AR" (Spanish, Argentina), "en-US" (English, USA).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/127e3452b1b2f4f89305bd6854b49c58b5eec4dbcca3090624dbd9891b35d942-contact-fields-in-the-system-010.webp",
        null,
        "Language format in the import file"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[Learn more >](https://docs.yespo.io/docs/adding-the-preferred-language-to-the-user-profile)

### Contact key

The _Contact key_ field is designed for external contact identifiers. Use contact key when you import a database and want to save the contact ID from the original database.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d74159fd5f82e9b0736d71db1fcad4248a071d53f8ecf615ca4b414f95ef63e1-contact-fields-in-the-system-011.webp",
        null,
        "Contact key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### External ID

The [external ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users) is a unique contact identifier generated in your system and helps to avoid duplicate contacts. Unlike the other channels, it will never change. It will help you collect all available data into a single contact profile and get complete information about their interaction with your company.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/93488e56397f6ea6f72dd2981ac4f15b72086478d7a7f6c73bb713d6875d911d-contact-fields-in-the-system-012.webp",
        null,
        "External ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Additional Fields Format Filling

If standard fields are not enough, you can add the necessary fields yourself.

### Text Input

Can include up to 1,000 characters, both text and integer numbers. Special characters (for example, % ^ \* | ~ {) are not supported.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b426cb435bc32d9bdeb17033b7723f2f98dcb224f5dc247b0349a8d5b62e56d3-contact-fields-in-the-system-013.webp",
        null,
        "Text input"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Text Area

You can include a large amount of data of up to 5,000 characters, both text and integer numbers. Special characters are not supported.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b8f680d1281d74bf67cd4da65c4cc60aa37a0b9cd8b6d89e9c87b3f0c0e519ab-contact-fields-in-the-system-014.webp",
        null,
        "Text area"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use _Text input_ and _Text area_ to specify:

- position, workplace, etc.;
- number of employees, number of positions;
- any additional data needed to segment your contacts.

### Number

Supports only integer numbers in the range from - 2147483648 to 2147483647. Set a range to validate the values you will pass in this field.

You can use numbers for email personalization and segmentation, for example, by basing the amount of bonuses a customer has.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3abbffaac9d4f8295ffa0909c4f988fed0740431d122b1225f61a8d20aa82c7-contact-fields-in-the-system-015.webp",
        null,
        "Number"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Fractional Number

If there is a way for customers to rate or rank their rating, satisfaction level, or other indicators, fractional numbers can be used to accurately display, for example, the order price.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4641815fdf8d2cf3023241a03e333c90ec47a8c08c16874c322136b477927ff3-contact-fields-in-the-system-016.webp",
        null,
        "Fractional number"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Date

The _Date_ field in the contact card usually contains any date related to the contact: birthday, anniversary, registration date, etc.

> 📘 Important
> 
> When manually importing or transferring a contact via the API, follow the corresponding date format: **yyyy-MM-dd, dd/MM/yyyy, dd.MM.yy, dd.MM.yyyy.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/98df7a1fd36591caa5663f7e654641893a4eef05fad6942ff1e38ff91e2f3b07-contact-fields-in-the-system-017.webp",
        null,
        "Date"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use _Regular date_ option when creating _Date field_ for formation dynamic segments.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e52a44228dd5e110bd85d9ac9d64eb6a0811d64c4298031f9bd3118a53f8859-contact-fields-in-the-system-018.webp",
        null,
        "Creating dynamic segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Date with Time

Use the _Date with Time field_ to record the exact date and time of events or actions. For example, changing the status of an order.

Unlike the _Date field_, you can make a record more accurate and detailed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0a6dee6c2cf4c41e22d6cd22a18495687886e62dad6c024a303d28272caa655-contact-fields-in-the-system-019.webp",
        null,
        "Date with time"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> When manually importing or transferring a contact via the API, follow the corresponding date format: **YYYY-MM-DDTHH:MM.**

### Dropdown

The field with predefined values. For example, a person's gender.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf12e6b6716eb430c613efef69793a361a1b3abeefc3ae0dcf084bcb673f471b-contact-fields-in-the-system-020.webp",
        null,
        "Dropdown"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can choose only one option from the _Dropdown field_ when creating a contact profile.

### Checkbox

The field with predefined values. For example, subscription categories or client business areas. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa99ac9d259bae76bece34a96eb1aebc0f10fa381515546794675f7fcf7ea7f7-contact-fields-in-the-system-021.webp",
        null,
        "Checkbox"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Unlike the _Dropdown field_, you can choose several parameter values in the _Checkbox field_.

## System Fields

The system fills in the fields automatically or via API.

### Applications, Telegram, Mob Push, Web Push

The fields display information about the connected mobile application, the integrated Telegram bot, and Web Push settings (if any).

Install the [SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo#1-install-sdk-and-connect-communication-channels) to display contacts' mobile device information. When a contact installs your mobile app, SDK collects data about the contact’s mobile devices connected to the app.

Use data from the Applications field to create [App Inbox](https://docs.yespo.io/docs/how-create-app-inbox-messages) and [In-App](https://docs.yespo.io/docs/creating-in-app-message) messages, even if a contact isn't subscribed to mobile push.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9776a9af09a94f383e695ff217c668b7c6f72c759bb432022a739a0ef06b8cc2-contact-fields-in-the-system-207.webp",
        null,
        "Applications, Mob Push, Web Push"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Location

Use contact location information to create dynamic segments for geotargeting campaigns.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b2f9fa3a94120627c615580e8511654d731d77d9d3d0754ed3a964ddbf0e981-contact-fields-in-the-system-023.webp",
        null,
        "Location"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


More about geotargeting in this [article](https://docs.yespo.io/docs/setting-up-geotargeting). 

### Time Zone

When contacts click on a link in the system, the system opens their IP. If the received IP address can be used to determine the country, region, and city, the system records the connection with the time zone in the contact card. The following links do not update the time zone; they can only be updated via the API. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ab80f58398f2d3af0ba6e727bd1202b7eaeaed1450ec323ec327e27dd57e73bf-contact-fields-in-the-system-024.webp",
        null,
        "Time zone"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Send data about time zone in <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones" target="_blank"> TZ database</a> format. Example: Europe/Kyiv

A contact's time zone can be used to send trigger messages only during the allowed time. [Learn more about >](https://docs.yespo.io/docs/setting-up-geotargeting)

### Contact ID

A field containing the internal contact ID in Yespo. The system automatically assigns An internal contact ID to each contact after the import or via the API. Contains only numbers. Next to the ID, the source of the contact entering the database is indicated.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c59deb579f5a6fab45aa0594b87a2515ddae25b51dbab0168ff51d0c40d02257-contact-fields-in-the-system-025.webp",
        null,
        "Contact ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## A Contact Card with Filled Fields Example

Contact card example with basic, additional and system fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/107017d0a4f60266802d75b081b6332e245983ff33d841025f7729d06601779e-contact-fields-in-the-system-209.webp",
        null,
        "Contact card example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Import

When [importing](https://docs.yespo.io/docs/importing-historical-data) a database, follow the formatting guidelines for the various field types to ensure your contact list is updated correctly. Download the example import file in the Import section as a sample. The example file contains columns for basic import: email address, first name, and last name. You can also include additional columns in the file, such as phone numbers or addresses.