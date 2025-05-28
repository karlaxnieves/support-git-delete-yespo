---
title: Personalization by Merge Tags
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Personalization by Merge Tags | Yespo Guide
  description: >-
    Learn how to add dynamic variables to emails and other messages: contact
    data fields and Velocity code.
  robots: index
next:
  description: ''
---
One of the ways to personalize a message is to substitute personal data from the values of contact fields automatically.

The most common example of personalization is the `%FIRSTNAME|%` variable substituted as a customer's name from the corresponding field of the contact card.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71748ca3f5a3ff0a3aa4fd99e043fe69a675dafd16d635f7a532531a9f01066a-personalization-merge-tags-001.webp",
        "%FIRSTNAME|% variable and substituted contact's name",
        "%FIRSTNAME|% variable and substituted contact's name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The variable will be replaced if the corresponding field is filled in the contact profile; if the field is empty, the variable will be skipped.

> 📘 Note
> 
> You can [create additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) for personalization.

Personalization is used for bulk and triggered campaigns in all communication channels.

Additional fields can contain any contact data you send to our CDP when [importing historical data](https://docs.yespo.io/docs/importing-historical-data) or sending data via the [API](https://docs.yespo.io/reference/getting-started-with-your-api). 

To see all personalization options available for your account, go to your profile settings → _Additional fields_. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b2a1236c963460fb7f94e03c8777a616ba828dd7d95cbffc71786d0c2ceeb115-personalization-merge-tags-002.webp",
        "Additional fields",
        "Additional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can use all variables from the additional fields to personalize messages in all channels.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b95460c16b161cbe57df4f40125690214fabc95c3b864837ae4d2bedd32497a4-personalization-merge-tags-003.webp",
        "Variables in additional fields",
        "Variables in additional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Add Data from contact fields to a message using a special menu in the message editor.

## Personalization Menu in Yespo Editors

### Email

1. Go to _Messages_, click the _Email_ tab, and open the message.
2. Click the _Text block_. The _Merge tags_ tab will open on the top panel of the editor.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/526a9763e51738b872dfe85f1d87b9e77c091896a3a4b44def83205b8c86e370-personalization.webp",
        "Email message personalization",
        "Email message personalization"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. In the drop-down list, select the field for substitution or find it through the search.

### SMS, Web Push, Mobile Push, Viber, App Inbox

The SMS, Web Push, Mob Push, and Viber editors have a similar interface. The icon with a person indicates personalization fields.

Let's look at personalization using mobile push notifications as an example**.**

1. Go to _Message → Mobile Push_ and open message.    
2. Go to the field with the person icon and click it.      

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e491fa2ad92cc13fb6ede12430ee8f2e5744dde85c9ca503a50ba7ba4b3daba7-personalization-merge-tags-005.webp",
        "Mobile Push message personalization",
        "Mobile Push message personalization"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. In the drop-down list, select the field for substitution or find it through the search.

## Using a Constant Value When There is No Data in Additional Fields

The system automatically adds a **“|”** sign after each variable in message editors, when adding variables

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/16df928fa2d9139704a455569879205ffa27f68f1ee21d1e6fa568ed86983a13-personalization-merge-tags-006.webp",
        "A “|” sign after variable",
        "A “|” sign after variable"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you need to add an alternative value for additional fields that do not contain information, enter the required text after the **“|”** character

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e9cee9c508502262eec05b053ca4ffb3be6f7666750665b5bfc247572b008b0-personalization-merge-tags-007.webp",
        "Alternative information",
        "Alternative information"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


 The contact will receive the following message:

- If they name is known.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/971238445803f6a189582eecb0713b07505506b9c79c58dd8a8ab8a5e8771aa3-personalization-merge-tags-008.webp",
        "The name is known",
        "The name is known"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Alternative title if a name is missing.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/82d96171ad45e40d3773eb0bcc259859642c39847e7be1232fcd323c372b886d-personalization-merge-tags-009.webp",
        "The name is unknown",
        "The name is unknown"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Examples of Using Variables for Personalization

Let's look at an example of the message with the substitution of the following field values from a contact profile:

where: 

- `%FIRSTNAME|%` — contact name; 
- `%EVENT|%` — some event;
- `%PERSONAL.BONUS|%` — number of active bonuses on the card;
- `%MANAGER.PHONE|%` — manager phone.
- `%MANAGER.NAME|%` — manager name;.
- `%PERSONAL.PROMOCODE|%` — client's personal [promocode](https://docs.yespo.io/docs/promocodes).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2b4b6e682a118e6c3d8aa0c52e324583889eb4bdcdd14ee11be9bec7e0721749-personalization-merge-tags-010.webp",
        "Template with variables & email with substituted data",
        "Template with variables & email with substituted data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Variable names can differ depending on the contact field names you have in your account.

To add a variable for an image, click the image block → URL and insert the variable (for example, `%PERSONAL.QRCODE%`) in the Image path.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f14041c36c6be09cf61961c219e51902a2b6485da4cf3c3d0e7c9190c327888d-personalization-merge-tags-011.webp",
        "Adding a variable for an image",
        "Adding a variable for an image"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Or you can add a variable as an `src` attribute straight to code:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8dcb5439d1c5a0e6531ce9eee48ebb8264039bee770dfb7db79f8cb629cc0ea9-personalization-merge-tags-012.webp",
        "Adding a variable as an src attribute",
        "Adding a variable as an src attribute"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> The variable value should be a link with an absolute path, for example: `https://example.com/qr_code.png`

## Substituting Data From an Event

Using variables in the message text allows unifying all messages or its blocks. But this method is devoid of variability — substitution happens or doesn’t happen without additional content management capabilities.

Sometimes, the value of an entire block is lost due to the absence of several parameters in a message. If there is insufficient contact information, data substitution will not occur. For example, the promotional code and QR code may be absent:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c15dcae3ae3806f847b566ba802231b3dcca9ed818d0cb5a1aa91b26f328087-personalization-merge-tags-013.webp",
        "No data available",
        "No data available"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can hide an entire message block and display it only when all the necessary components are available or use data passed from the even. For these cases, use [variables with Velocity functions](https://docs.yespo.io/docs/user-profile-variables-and-velocity-features).