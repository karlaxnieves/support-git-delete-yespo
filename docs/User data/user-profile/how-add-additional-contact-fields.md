---
title: Creating Additional Fields
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Additional Fields | Yespo Guide
  description: >-
    The document explains how to create and manage additional fields in contact
    cards for storing specific information, enabling advanced segmentation and
    personalized communication
  robots: index
next:
  description: ''
---
Additional fields in contact cards are created to store specific information about contacts — their personal promocodes, memorable dates, location, etc. Creating fields allows for advanced contact segmentation and [deeper personalization of communications](https://docs.yespo.io/docs/personalization-by-merge-tags).

## Additional Fields Tab

Additional fields are listed in the account settings →  _Additional fields_ tab (by default, there is only the _Personal_ list with the _Birthday_ and _Gender_ fields).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c083612abc05df4f7de6bd2899ff817a26185b0b115b279ca1e730d7a31236a-additional-fields-1.webp",
        "Additional fields",
        "Additional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The list of additional fields displays:

1. Field type (text input, date, etc.)
2. Field name.
3. Variable for automatically inserting the contents of the field into the message and updating contact cards with event parameters via SDK.
4. Field ID.
5. _Edit field_ button.
6. _Delete_ field button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/843a7f3f0334fd9c5d905f1362a9fffd5b5d6926eb2e95e8454de11ccdb951d3-additional-fields-2.webp",
        " Additional field",
        " Additional field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can create lists and add fields to them.

## Creating a List

Creating lists allows you to group fields by a specific common value: personal data, product preferences, etc. The algorithm for creating a list of fields is as follows:

1. Click the _New list of fields_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/302c23a22f4c4e3b98f1e4471330f851fd3e21f4f664da890a017b1a46eb153e-additional-fields-3.webp",
        "New list of fields",
        "New list of fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter a name for the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/efef113825402d07f2dbcb182c2d3b7a0851a3e84a9aaf20d9799aaa050c2ab5-additional-fields-4.webp",
        "Name",
        "Name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. The personalization key is generated automatically based on the name, but you can change it. This key is used when creating a variable for a field from this list (therefore, it is better to choose a more concise option).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1cdf82d7e02d11b40a57c94810a68914ae476f8e827914c8b12c8c54f21ac0c-additional-fields-777.webp",
        "Personalization key",
        "Personalization key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6094d22dc3bd0e85a5de0c26f6b7f1004458d23210e3ca92d5d3ed990f1eca77-additional-fields-6.webp",
        "Save",
        "Save"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> - A list will be inactive until the first field is added to it
> - Before you delete a list with fields, delete the fields it contains

## Adding Fields

1. Click plus to create a field in the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d0ff0f74fdc2cde617eb880778c5f44ff91381e5cbfa6bc1b43726a0b122eeee-additional-fields-7.webp",
        "New field",
        "New field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Specify the field's name and, if necessary, edit the automatically generated personalization key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f0c8bc4518534ae468eeb3094e0f3d3163345c03079db27d4e272ae9decf62a-additional-fields-8.webp",
        "Name & Key",
        "Name & Key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the field type (by default, it is saved as a text input).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d4bed842e42b952535f923df3cedb64896b15d538cc91c521d1f5422e86af077-additional-fields-9.webp",
        "Field types",
        "Field types"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Field Types

Depending on [the contact data type](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system#preparing-a-file-for-uploading), the following field types are available in the system:

- The **Text input** can contain up to a thousand characters, both letters and integers. Special characters are not supported. You can use this field type, for example, to record the name and address of a contact.
- The **Text area** can contain up to five thousand characters, both letters and integers. Special characters are not supported. You can use this field type, for example, to record answers to detailed questions.
- The **Number** can only contain integer values from -2147483647 to 2147483647 (order ID, number of bonuses, etc.)
- The **Fractional number** can contain whole numbers and fractions (amount of orders, etc.)
- The **Date** – values must be transmitted in the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601 "{rel='nofollow'}")  format. Date format: `YYYY-MM-DD`. The **Regular date** option is used to create [dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment) for regular communication around recurring events such as anniversaries, [birthdays](https://docs.yespo.io/docs/how-set-automated-birthday-campaign), etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49056b60e43e0c7759bcf1bb408f4abac3089bb1e5fedef32b79ed3653eec6fb-additional-fields-10.webp",
        "Regular date",
        "Regular date"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- The **Date with time** – data format: `YYYY-MM-DDHH:MM` (validity period of the promocode, etc.)
- The **Drop-down list** contains predefined values: gender, status, or language of a contact.

Important

Do not use the period symbol in the field name. For example, you can write _Marital status_ separated by a space or underscore

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1ceaa4e5e2590de864ca2e622548bc2f4a3fe4343deee4008e60ed3eb6ce541f-additional-fields-11.webp",
        "Field name example",
        "Field name example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- The **Checkbox** allows a contact to select more than one answer option.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/539612dfc891d82305c04079f509eb09f537cf00a521b2b79332bda6e430cb89-additional-fields-12.webp",
        "",
        "Checkbox"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To write or update a checkbox field using the [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) API method, pass the field ID (the numeric value specified in the list of fields) in the _fields_ array and specify the value separated by commas:

```json
"fields": [{
"id": 87166,
"value": "Chinese "
 }]
```

Also, specify the `customFieldsIDs `object identifier, which lists additional field IDs to update. Only additional contact fields which IDs are in this list are updated.

> 📘 Note
> 
> After creating an additional field, the system will require up to an hour of synchronization before the field becomes available via [АРІ](https://docs.esputnik.com/reference/getting-started-with-your-api).

## Updating Custom Fields with Data from Custom Events via SDK

Use contacts' fields variables without % characters as a key to update corresponding contact fields via SDK.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/138d92a2ec7258d8cadd40878bec921a948a8b19406cda3244aa584723223a67-variable.webp",
        "",
        "Variable"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Android example:

```kotlin
{
   "userAttributes":{
      "email":user.mail,
      },
      "fields":[
         {
            "key":"TRAININGAPP.GOAL",
            "value":"lose weight"
         }
      ]
   }
}

Reteno.setUserAttributes(externalUserId: String, user: User?)
```

iOS example:

```swift
let UserAttributes = .init(
    email: user.email
    fields: [.init(key: "TRAININGAPP.GOAL", value: "lose weight")]
}

Reteno.updateUserAttributes(externalUserId: "USER_ID", attributes: UserAttributes)
```

[More on Mobile SDK >](https://docs.yespo.io/docs/sdk-mobile-apps)