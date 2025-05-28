---
title: Passing Promo Codes from Messages to Contact Cards
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Passing Promo Codes from Messages to Contact Cards | Yespo Guide
  description: >-
    The document explains how to use the HTTP request data source in Yespo to
    send unique promo codes: upload codes, add fields to contact cards, connect
    the HTTP request, create messages, and set up workflows.
  robots: index
next:
  description: ''
---
The _HTTP request_ data source allows you to send a unique promo code from a trigger message, record it to a contact card, or pass it to your server. Thus, you can automatically fix which particular promo code one or another of your subscribers received.

Setting process:

1. Generate and upload a file with promo codes to your Yespo account.
2. Create an additional field for contact cards in which the promo code will be recorded.
3. Connect the `HTTP` request data source in your Yespo account.
4. Prepare a message with velocity variables to transfer promo codes.
5. Create a workflow by which a message will be sent, and a promo code will be transmitted.

## 1. Uploading a file with promo codes to Yespo

Prepare a list of promo codes in the following format:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/783f91b30e78c0c1a5e8cf4adec2e2e6c6fcde9eb8718372a7666fa38185fbd9-image3.webp",
        null,
        "File example"
      ],
      "align": "center",
      "sizing": "60% "
    }
  ]
}
[/block]


Mandatory fields of the table with promo codes:

- “code” — promo code in any format;
- “expirationDate” — date and time of promo codes expiration in the format 2017-12-31T23:59;
- “discount” — promo code value from 0 to 99;
- “type” — an arbitrary name of the promo code type;
- “inUse” — a flag indicating whether a promo code has been used or not (true/false).

## 2. Adding additional field _Promo code_ to contact cards

Read more on the creation of additional fields [in the instructions](https://docs.yespo.io/docs/how-add-additional-contact-fields). After creating an additional field, copy its ID - you will need to specify it in the body of the JSON request as a field for recording the corresponding promo codes.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c25067621f3cd45b581e9a2c4f8feb0825d6d054ae201ec042fd71dbd8aa3a4f-image2.webp",
        null,
        "Additional field ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 3. Connecting HTTP request

1. Go to your account settings → _Data sources → New data source → External data sources_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/210b070dfb9cf8c5923e556eaf67c0fbbb0b203861533d7e60ba4a82fbdd8a48-image7.webp",
        null,
        "New data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the _HTTP request_ external data source.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f4b60d6920707a135d28eb652706bc78ade7de8a30efb94ec33c7e8f1a1d44b-image8.webp",
        null,
        "HTTP request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Set the arbitrary source name.
4. Select the `POST` protocol type and specify the protocol `https://yespo.io/api/v1/contact`. This API resource will update the data of the contacts participating in the campaign, adding the received promo codes to contact cards in Yespo. If you need to update the contact information in your system, specify the appropriate protocol.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58f925a11242638660e75824ef474a238918ec461cf04f4fbd6b7f587f3d2e4d-Data-source1_en.webp",
        null,
        "POST protocol"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Activate the _Pass JSON in the request body_ switcher and enter the request body in the corresponding field:

```
{
     "channels": [
          {
               "type": "contact unique identifier: email, sms or mobilepush",
               "value": "$data.get('contact_unique_identifier')"
          }
     ],
     "fields": [
          {
               "id": "ID of the contact card field created at the previous stage, where the promo code will be recorded",
               "value": "$data.get('promocode')"
          }
     ]
}
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58bebb8004d85ceda9f5fae7c45f3511e17e074f40a40dc60bd96cce461a5475-Screenshot_4.webp",
        null,
        "\\[JSON in the rquest body"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 4. Message creating

This functionality works in each of the channels available in the Yespo system. We will demonstrate how to set it up using a mobile push notification as an example.

1. Set an arbitrary name for the message.
2. Fill the message with the necessary content. Add a velocity variable to it, which will provide data exchange with the _HTTP request_ external data source.

Construction syntax:

```
#set($url=$!data.get('your data source name'))
```

In the message body where the promo code should be substituted, specify the variable in the following form:

```
$!data.get('promocode')
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac1025c533e7ef148d5540b00131cb10f6930ba77392f2a7809eca68337a014d-image9.webp",
        null,
        "Variables in message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Contacts who receive the message will see it like this (depending on the OS of the mobile device):

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5571a16058da107147dc7350f1ab03157639c1328a2b781233b9e44bdb193152-image6.webp",
        null,
        "Final message look"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


## 5. Workflow creation

The workflow should have 5 required blocks:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ec1544468eea2b19ed8856fbc63bcb37ea8dfe3fc14f89747c6aa947e4d03ec-passing-promo-codes-from-messages-to-contact-cards-01.webp",
        "Workflow scheme",
        "Workflow scheme"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


1. The _Start_ block.
2. _Get contact_ task — the block extracts contact data from the Yespo database, including the contact’s token to which the push will be sent.
3. _Get promo code_ task — the block retrieves the promo code from the previously loaded list to insert it into the message. This task must have 3 required parameters:

- days — number of days for which the promo code must be valid;
- type — the specified type of promo code from the previously loaded list;
- discount — the amount of discount.

4. The message block.
5. The _End_ block.

[More on setting up workflow blocks >](https://docs.yespo.io/docs/building-and-editing-workflows)

Set the workflow launch conditions and activate it. Each promo code received in a message by this workflow will be recorded in the card of the corresponding contact.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/27bd71b83ceec4108cc9b53c7b9d4e60a9611a7b10b8d54de90253f80d755e39-image4.webp",
        null,
        "Promo code in contact card"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]