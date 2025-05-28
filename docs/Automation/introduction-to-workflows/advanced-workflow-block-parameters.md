---
title: Advanced Workflow Block Parameters
excerpt: Advanced Workflow Block Parameters
deprecated: false
hidden: false
metadata:
  title: Advanced Workflow Block Parameters | Yespo Guide
  description: >-
    Learn how to configure advanced block settings when using custom event
    parameters, message sending, and dynamic content insertion.
  robots: index
next:
  description: ''
---
Fill the advanced parameters in the following cases:

- When using custom event parameters
- For sending messages to an additional contact
- For inserting dynamic content

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f30d22c197e1a6270d56858b4da771c7a426ae9ca37442ca06902c04e280c77-advanced-parameters-000.webp",
        "",
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


List of _Additional parameters_:

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "0-0": "Contact ID",
    "0-1": "Contact identifier in the system or an event parameter containing it.  ",
    "1-0": "Email  ",
    "1-1": "Contact's email address or an event parameter containing the email address.",
    "2-0": "Phone  ",
    "2-1": "Contact's phone number or an event parameter containing it.",
    "3-0": "Token  ",
    "3-1": "Contact's token or an event parameter containing it.",
    "4-0": "Language  ",
    "4-1": "Message language. Leave the field blank if you use a multilingual message in the workflow.  \n  \n[Learn more about setting up multilingual campaigns >](https://docs.yespo.io/docs/creating-multilingual-campaigns)",
    "5-0": "JSON",
    "5-1": "Specific data from the event."
  },
  "cols": 2,
  "rows": 6,
  "align": [
    "left",
    "left"
  ]
}
[/block]


Let's view each case of parameter configuration in detail.

### Using Custom Event Parameters

By default, when starting a workflow, the event should pass standard parameters for contact identification:

<br />

[block:parameters]
{
  "data": {
    "h-0": "Event parameters",
    "h-1": "Identifiers",
    "0-0": "ContactId  \nContact_id",
    "0-1": "Contact ID",
    "1-0": "externalCustomerId",
    "1-1": "External ID",
    "2-0": "Email  \nEmailAddress  \nUserEmail  \nContactEmail",
    "2-1": "Email",
    "3-0": "Phone  \nSMS  \nPhoneNumber",
    "3-1": "Phone number",
    "4-0": "PushToken  \nMobPushToken  \nTelegramBotToken",
    "4-1": "Contact token"
  },
  "cols": 2,
  "rows": 5,
  "align": [
    "left",
    "left"
  ]
}
[/block]


> ❗️ Important
> 
> 1. The primary identifier is _ContactId_. If it is not specified but at least one of the other identifiers is provided, _ContactId_ will be automatically added to the event.
> 2. To start workflows, the system identifies the contact for which the event was received. The system searches for the contact using the following rules:
> 
> - _​​​​​Contact ID_ has the highest priority among all parameters.
> - Entered contact email, phone number, or token are used for sending.
> - If _externalCustomerId_ is specified, the message is sent to the contact it belongs to; among those contacts that were found by email address, phone number or token.
> - If _externalCustomerId_ is not specified, the message is sent to the contact found by email address, phone number or token.
> - If a contact is not found, a new contact will be created for sending.
> 
> 3. For data consistency, provide parameter names according to the specified list.

If the parameters in the event don't match the standard values, such as using _PersonalEmail_ instead of _EmailAddress_, like on the screen below

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e711fe705b65be796f2c640672512529ccfebf3220e7567fcf1ae720ef3d8f3-advanced-parameters-001-2.webp",
        "Event parameters",
        "Event parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In this case, specify the name of the corresponding variable in the _Email_ field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49b695e4758358b513be2b0bd531f29663a4606d17d2717ac8bc3d0edb0dcb0a-advanced-parameters-002.webp",
        "Email field",
        "Email field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Sending Messages to an Additional Contact

For example, if you need to duplicate the message sent to the user and send it to the manager.

[Copy the block](https://docs.yespo.io/docs/workflow-management#copying-blocks--workflows) with the selected message in the workflow and specify the manager's contacts in the advanced parameters.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa4a6c2c3410076361d6fafec2e18bed0ebbd4c4adcba4b7cbc385ac3c4e1969-advanced-parameters-003.webp",
        "Sending Messages to an Additional Contact",
        "Sending Messages to an Additional Contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Inserting Dynamic Content

Used to display specific data from the event in the message.

For example, if the event contains JSON:

```json
{
    "eventTypeKey": "AbandonedCart",
    "keyValue": "2424925572",
    "params": [
        {
            "name": "cartItems",
            "value": [
                {
                    "name": "Conditioner for dry hair",
                    "price": "341",
                    "url": "https://site.com/conditioner-dry-hair",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Le Petit Olivier",
                    "tags_weight": "200",
                    "tags_oldprice": "467"
                },
                {
                    "name": "Magnolia Nobile Perfumed water",
                    "price": "2341",
                    "url": "https://site.com/catalog/perfumed-water-2-750-g",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Acqua Di Parma",
                    "tags_weight": "100",
                    "tags_oldprice": "4467"
                }
            ]
        },
        {
            "name": "recommendedItems",
            "value": [
                {
                    "name": "Shampoo for dry hair",
                    "price": "441",
                    "url": "https://site.com/shampoo-dry-hair",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Le Petit Olivier",
                    "tags_weight": "200",
                    "tags_oldprice": "467"
                },
                {
                    "name": "Magnolia Nobile Face cream",
                    "price": "1341",
                    "url": "https://site.com/catalog/face-cream-2-750-g",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Acqua Di Parma",
                    "tags_weight": "100",
                    "tags_oldprice": "4467"
                }
            ]
        },
        {
            "name": "emailAddress",
            "value": site@ukr.net
        }
    ]
}
```

where:

- **name** – array and field names,
- **value** – the value to be inserted into the message.

In the message, specify the variables that will display the products in the message:

- **$!data.get('recommendedItems')** — The name of the array from which the data needs to be substituted is given in brackets.
- **get(0)** — The index of the array elements is indicated in brackets (counting starts from 0);
- **get('price')** — the name of the event parameter from which data should be substituted is given in brackets.

As a result, the variable might look like this:

- `$!data.get('recommendedItems').get(0).get('price')`

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0fc408f43b6c9c85451d287b629099eadfd75082ced56b14d699ca3a852325a-image3.png",
        "Specify the variables",
        "Specify the variables"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[Learn more about using Velocity in emails >](https://docs.yespo.io/docs/using-velocity-email)