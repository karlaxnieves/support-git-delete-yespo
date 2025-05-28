---
title: Substituting Events Data into Messages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Substituting Events Data into Messages | Yespo Guide
  description: >-
    Learn how to substitute event data into messages for personalized
    communication.
  robots: index
next:
  description: ''
---
Mobile app developers often need to send dynamic content messages to their users. For example, transactional messages initiated from the backend: order confirmation, delivery, etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c81747cb9a42c5073ad29424a9431ec66ec52618d353d502bf1143f7bb770c01-1_2.webp",
        "",
        "Transactional message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


We recommend using [Generate event](https://docs.yespo.io/reference/registerevent_1) API method to send custom backend events to Yespo. For more information on sending orders data, please [read the instructions](https://docs.yespo.io/docs/site-activity-tracking-using-generate-events).

Let's consider in practice how to substitute data from events to a message.

> 📘 Note
> 
> The message with dynamic event content must participate in the workflow triggered by the corresponding event.
> 
> See the following instructions to learn [how to launch a triggered campaign on event](https://docs.yespo.io/docs/creating-events).

## Event Data Types

An event can contain different data types, which are substituted differently in the message:

- Simple data (strings and numbers not included in the object or array)
- Object data 
- Array data

Let's consider how to transfer these types of data to the message, using the following request as an example:

```json
{
    "eventTypeKey": "data_for_message",
    "keyValue": "user@imaginary.email",
    "params":
    [
        {
            "name": "EmailAddress",
            "value": "user@imaginary.email"
        },
        {
            "name": "externalOrderId",
            "value": 20233
        },
        {
            "name": "sellerName",
            "value": "Shop Tea"
        },
        {
            "name": "object",
            "value":
            {
                "title": "Black Tea",
                "text": "Tea from the Tonganagaon plantation in India",
                "img": "https://pics.site.com/repository/home/1/common/images/1576074904732.jpg",
                "price": "$11.05",
   "link": "https://site.com"
            }
        },
        {
            "name": "array",
            "value":
            {
                "array_items":
                [
                    {
                        "title": "Black Tea",
                        "text": "Tea from the Tonganagaon plantation in India",
                        "img": "https://pics.site.com/repository/home/1/common/images/1576074904732.jpg",
                        "price": "$11.05"
                    },
                    {
                        "title": "Green Tea",
                        "text": "Tea from the Indian region of Darjeeling",
                        "img": "https://pics.site.com/repository/home/1/common/images/1576074904060.jpg",
                        "price": "$10.20"
                    },
                    {
                        "title": "Herbal tea",
                        "text": "Peach, rosehip, and apple, spring flavor.",
                        "img": "https://pics.site.com/repository/home/1/common/images/1576074902892.jpg",
                        "price": "$15.00"
                    }
                ]
            }
        }
    ]
}
```

### Substituting simple data from event

We have "externalOrderId" and "sellerName"  fields with 20233 and "Shop Tea" values. These string and number are not included in the object or array.  

To substitute values to the message:

- In the message template, use _$data.get('externalOrderId')_ and _$data.get('sellerName')_ [velocity constructions](https://docs.yespo.io/docs/introduction-to-velocity), where _externalOrderId_ and _sellerName_ are field names from the request.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af010c790614b2722f0a3e268d50cedccf32c6963c8649e4f593e777a8f8da00-1_5.webp",
        "",
        "Substituting data from an event into a message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The user who initialized the event will receive the message:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90fe6bf926ed735effbb63f7cb41e0814e8296c69255ca059045b347181c204f-1_6.webp",
        "",
        "Mobile push"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Substituting object data from event

In the example, the object is the data of one product:

```json
{
    "name": "object",
    "value":
    {
        "title": "Black Tea",
        "text": "Tea from the Tonganagaon plantation in India",
        "img": "https://pics.site.com/repository/home/1/common/images/1576074904732.jpg",
        "price": "$11.05",
        "link": "https://site.com"
    }
}
```

To access object data:

1\. Select the message block in the workflow and specify the object name in the JSON field (in this request, ${object}).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc068acb2448e79c53e704da9f8e42c40dc5d6bc6747afcb0602b976e99431ef-substituting-event-data-into-messages-01.webp",
        "Object name",
        "Object name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. In the message template, specify the velocity variables from the object in the appropriate fields:

- $data.get('title')
- $data.get('text')
- $data.get('img')
- $data.get('price')
- $data.get('link')

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9cd98fe725da0ecbd6b5b6cacb993beff9dd354c5e01234d6a7a27ef5a979429-image2.webp",
        "",
        "Variables in email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The email will look like this:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99fc8b7c60cefd598e2f31bc26bccf1e8c75d612550256d7d4e7963ef0a9a5da-image1.webp",
        "",
        "Substitution of data in email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Sending a data object covers most needs for channels like SMS, Web Push, Mobile Push, Viber, and App Inbox.

To send more data, use an array.

### Substituting array data from event

In the example, data about several products are transferred in the array:

```json
{
    "name": "array",
    "value":
    {
        "array_items":
        [
            {
                "title": "Black Tea",
                "text": "Tea from the Tonganagaon plantation in India",
                "img": "https://pics.site.com/repository/home/1/common/images/1576074904732.jpg",
                "price": "$11.05"
            },
            {
                "title": "Green Tea",
                "text": "Tea from the Indian region of Darjeeling",
                "img": "https://pics.site.com/repository/home/1/common/images/1576074904060.jpg",
                "price": "$10.20"
            },
            {
                "title": "Herbal tea",
                "text": "Peach, rosehip, and apple, spring flavor.",
                "img": "https://pics.site.com/repository/home/1/common/images/1576074902892.jpg",
                "price": "$15.00"
            }
        ]
    }
}
```

To access array data:

1\. Select the message block in the workflow and enter the array name in the JSON field (in our example it is ${array}).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6649c67eec2def49c910122180487a719e6645bbad3f3dc635950d0194620009-substituting-event-data-into-messages-02.webp",
        "Array name",
        "Array name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. In the email editor, highlight the appropriate strip, open the code, and add the velocity structure with the #foreach loop:

```json
<!-- #foreach( $item in $data.get('array_items') ) -->
// html content
<!-- #end -->
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e947f33de2d385ed6340ee77068ddf2cc8b0034dd6ce1337919746ee911e24f-image4.webp",
        "",
        "Velocity code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The loop sequentially goes through the array elements, placing the data in the intermediate object $items (arbitrary name), which is used to substitute data into the message.

3\. Specify the velocity variables from the array in the appropriate places of the temlate:

- $item.get('title')
- $item.get('text')
- $item.get('img')
- $item.get('price')
- $item.get('link')

The email will look like this:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d10d2dab95248363be3e3a4bcad3eb9e1bc55f4bf1d890981898aa53761b6d6f-image8.webp",
        "",
        "Data substitution"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The mobile push notification will be displayed differently on different devices, but we recommend writing at most 40 characters. That’s why it is not always rational to display the entire contents of the array using the foreach loop.
> 
> Instead, you can refer to a specific array element. Then velocity construction for the array will look like this: $!data.get('array\_items').get(0).get(' name'), where the first element of the array is accessed (numbered from 0).