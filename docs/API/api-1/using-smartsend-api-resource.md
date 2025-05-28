---
title: Using the Send Prepared Message API Method
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using the Send Prepared Message API Method | Yespo Guide
  description: >-
    The Send prepared message method allows sending pre-prepared messages to up
    to a thousand recipients across various channels like Email, SMS, Mobile
    Push, and more, with options for personalization using JSON data.
  robots: index
next:
  description: ''
---
The [Send prepared message](https://docs.yespo.io/reference/sendextendedpreparedmessage-1) method allows you to send a pre-prepared message by specifying its ID in the request URL. This could be an email about password recovery, an order, an abandoned browsing or shopping cart, or a notification about a change in the price of a product the user was interested in.

Features of use:

- Up to a thousand recipients are transmitted in one request;
- Messages can be personalized for each recipient using data from the request;
- The method is used in the [Email](https://docs.yespo.io/docs/email-setting-up), [SMS](https://docs.yespo.io/docs/sms), [Mobile Push](https://docs.yespo.io/docs/mobile-push), [Web Push](https://docs.yespo.io/docs/web-push), [Viber](https://docs.yespo.io/docs/viber), [Telegram](https://docs.yespo.io/docs/telegram), and [App Inbox](https://docs.yespo.io/docs/app-inbox) channels.

## 1. Request Description

A call to the method is made using the POST method at [api/v1/message/{id}/smartsend, where](https://docs.yespo.io/reference/sendextendedpreparedmessage-1) `{id}` is the identifier of the message prepared in your account.

{

`"recipients"` : \[{

`"contactId"` : "The identifier of a contact (may not be indicated when the locator parameter is indicated).",

`"locator"` : "A recipient. For example, an email address for email messages, a phone number for SMS or Viber.",

`"jsonParam"` : "Parameter in JSON format. Used for messages with complex velocity patterns.",

`"languageCode"` : "The language of the message for the contact. Used for [multilanguage](https://docs.yespo.io/docs/multilanguage-overview) messages."

`"email"` : "Message type: true for email, false for the rest of the media channels.",

`"fromName"` : "Sender name. You must specify only the sender's name, not the email address. The sender's email selected in the message will be used. For SMS, the alpha name is specified. If the parameter is not specified, the name selected in the message will be used."

`"externalRequestId"` : "Optional parameter, which allows you to assign your own identifier to the sent message and subsequently use the [Get contacts activity](https://docs.yespo.io/reference/contactactivity-1) method to get the status of this message."

}

## 2. Server Response

When the request is successful, the server returns the result of a single message delivery.

- `id` – always returns 0;
- `locator` – email, phone number, Device ID, or contact token to which the message was sent
- status is the result:

  - OK — if the message is successfully added to the sending queue, you can see the message status using a requestId in the request to the [Get single message status](https://docs.yespo.io/reference/getinstantmessagesstatus-1) method;
  - ERROR — If the message cannot be added to the sending queue, the request is returned with the ERROR status, where the message is an error description (for example:  `"message": "'example@mail.com'"` is not valid email).

  ```json
  - {  
        "id": 0,  
        "results": [  
            {  
                "id": 0,  
                "locator": "example@mail.com",  
                "status": "OK",  
                "requestId": "8b2e65d9-060b-4c61-bbd7-73c6796fa504"  
            }, {  
                "id": 0,  
                "locator": "new. example@mail.com",  
                "status": "OK",  
                "requestId": "458f3533-51d9-439e-a5d0-5fb7c2490c41"  
            }  
        ]  
    }
  ```

  ## 3. Use Case for Emails

  You can use the method to send single messages with or without personalization. For personalization, the _jsonParam_ field is used, which can contain JSON objects, nested objects, and arrays that need to be <a rel="nofollow" href="https://en.wikipedia.org/wiki/Serialization" target="_blank"> serialized</a> before sending the request, i.e., you must sequentially convert objects into a JSON string.

### 3.1 Sending Message without Parameterization

The body of a request for sending one message looks as follows:

```json
{
  "recipients": [
    {
      "jsonParam": null,
      "locator": "example@mail.com"
    }
  ],
  "email": true,
  "fromName": null
}
```

And for two recipients correspondingly:

```json
{
  "recipients": [
    {
      "jsonParam": null,
      "locator": "example@mail.com"
    }, {
      "jsonParam": null,
      "locator": "new.example@mail.com"
    }
  ],
  "email": true,
  "fromName": null
}
```

When the _fromName_ field is transmitted with a null value, the email will use the name specified when adding the sender address:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/098661977dfa664b79f02aca5accf654cfd63f7fd522d9d2043e9f59e9676816-e-7.webp",
        "Sender name",
        "Sender name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Transmitting the _jsonParam_ field with the null value indicates that the email does not support dynamic personalization.

### 3.2 Transmission of JSON Objects

Formatting of a JSON object is set using curly braces { } containing the data with the key values. The pairs of key values are separated by a colon: `{"key" : "value"}`. A comma separates every pair of the values, so the middle section of the JSON object looks like this: `{"key" : "value", "key" : "value", "key": "value"}`.

As an example, the object containing two pairs of key values looks as follows:

```json
{
  "discount": "5%",
  "link": "https://example.site.com/items_for_sale"
}
```

For correct transmission, convert an object in the request body to a string to look like this:

```json
{
  "recipients": [
    {
      "jsonParam": "{\"discount\":\"5%\",\"link\":\"https:\/\/site.com\/items_for_sale\"}",
      "locator": "example@mail.com"
    }
  ],
  "email": true,
  "fromName": null
}
```

To display the transmitted values in a message, use the velocity structure:

- `$!data.get('discount')` — instead of the discount size,
- `$!data.get('link')` – in the button settings (link type – “Other”).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3003a7a176e5456c41cba5ac5840377401e8840ba85a81fcd55a644e99d10e4-e-6.webp",
        "Dynamic content",
        "Dynamic content"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Instead of the discount variable, the value "5%" will be substituted, and for the button, instead of the link variable, the value `"https://site.com/items_for_sale"` will be substituted as a link.

### 3.3 Transmission of Nested JSON Objects

The format of a nested JSON object is `”objectName”: {"key" : "value", "key": "value"}`.

The example of the `customerData` and `orderData` nested objects looks like this:

```json
{
  "customerData": {
    "firstName": "John",
    "lastName": "Smith"
  },
    "orderData": {
    "name": "Apple iPhone X 64GB Black",
    "cost": 25999,
    "url": "https:\\example.site.com\smartfon-apple-iphone-x-64gb.html",
    "imageUrl": "https:\\example.site.com\smartfon-apple\apple_iphone_x_64gb.jpg"
  }
}
```

Convert the data to the string (serialize), and the request gets the following look:

```json
{
  "recipients": [
    {
      "jsonParam": "{
\"customerData\":{\"firstName\":\"John\",\"lastName\":\"Smith\"},
\"orderData\":{\"name\":\"Apple iPhone X 64GB Black\",
\"cost\":"25999",\"url\":\"https:\/\/example.site.com\/smartfon-apple-iphone-x-64gb.html\",
\"imageUrl\":\"https:\/\/example.site.com\/smartfon-apple\/apple_iphone_x_64gb.jpg\"}
}",
      "locator": "example@mail.com"
    }
  ],
  "email": true,
  "fromName": null
}
```

To display the data in a message, use the following velocity structure:

- For personal data —

```json
$!data.get('customerData').get('firstName')
```

- For order data —  

```json
$!data.get('orderData').get('name')
```

In both cases, the last brackets contain the parameter's name to be displayed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/875eebab7fff2eb43ee0b99277f560ab4d6f7fd53b5df3302f270e4efa2cdc2a-var1.webp",
        "Velocity variables",
        "Velocity variables"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 3.4 Transmission of Nested JSON Array

Arrays are the ordered collections of values. Use square brackets `[ ]` to define an array. Separate the values inside the brackets with commas.

The format of a nested JSON array is` ”arrayName”:\[{"key":"value", "key":"value"},{...}\]`. You can transmit several arrays within one request.

```json
{
  "orderData": [
    {
      "name": "Smartphone Apple iPhone Xs 512Gb",
      "price": "49999",
      "url": "http://example.com/smartfon-apple-iphone-27.html",
      "imageUrl": "http://example.com/apple_iphone_xs_silver.jpg"
    },
    {...},
    {
      "name": "Apple Watch Series 4 GPS 44mm Space Gray",
      "price": "13699",
      "url": "http://example.com/smart-chasy-apple-watch-series-4-gps-45-2mm.html",
      "imageUrl": "http://example.com/apple_watch_series_4_gps_44mm.jpg"
    }],
  "recommendationsData": [
    {
      "name": "Smartphone protection glass MakeFuture 3D Apple iPhone X/XS",
      "url": "http://example.com/glass.html",
      "imageUrl": "http://example.com/makefuture_3d_apple_iphone_xxs_black.jpg",
      "price": "399"
    },
    {...},
    {
      "name": "Apple 44mm Black Sport Band",
      "url": "http://example.com/sport-band.html",
      "imageUrl": "http://example.com/apple_44mm_black_sport_band.jpg",
      "price": "1999"
    }
  ]
}
```

> 📘 Important
> 
> Like the nested JSON object, the JSON array must be converted to a string (serialized).

It is preferable to use arrays when operating with a large amount of data that can be grouped.

Use the _foreach_ loop structure built into velocity in the message to access the data from the array. Using the _orderData_ array as an example, the 

The velocity code for `orderData` array looks like this:

```json
// Inside the structure, the data are extracted in a sequence from every element of the array
#foreach($order in $!data.get('orderData'))
  // To extract the value from the name field of the order 
  $!order.get('name') 
  // For the url field
  $!order.get('url') 
  // For the imageUrl field
  $!order.get('imageUrl')
  // For the price field
  $!order.get('price')
#end
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a5ca10a97c1d35728cdd0577fb013934f85f8d33c87e2df71ad4dbce1a8c231-smartsend1.webp",
        "Velocity cycle in text editor",
        "Velocity cycle in text editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


A similar construction is used for the array in which the recommendations are transmitted:

```json
// Inside the structure, the data are extracted in a sequence from every element of the array
#foreach($recomm in $!data.get('recommendationsData'))
  $!recomm.get('name')
  $!recomm.get('url')
  $!recomm.get('imageUrl')
  $!recomm.get('price')
#end
```

A prepared email containing velocity code has the following look:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55233609c485eb758f1b1315594bc1e9f209a2df68258c47d03963962c457894-2.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 4. Use Case for SMS

Let’s assume we have a task to inform a user via SMS that their order has been completed and shipped.

Then, we prepare the following request body:

```json
{
  "recipients": [
    {
      "jsonParam": "{\"firstName\":\"John\",\"orderId\":\"JN134173389\",\"deliveryAddress\":\"London, Post office №32\"}",
      "locator": "380501234567"
    }
  ],
  "email": false,
  "fromName": "V-COMP"
}
```

where the recipient’s phone number is in the _locator_ field, and alpha-name is in the _fromName_ field.

Create an SMS:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/400c4f6805be8efee2801bf3d6624a3dbb3db6dd5d5c3564bf5961a666e5b4fe-e-11.webp",
        "SMS message preparation for smartsend",
        "SMS message preparation for smartsend"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


It is not always practical to show an array's content in an SMS using the _foreach_ cycle; instead, it is possible to address a specific element of an array using _orderData_. 

In this example, the velocity structure looks as follows:

In this example, the velocity structure looks as follows: `$!data.get('orderData').get(0).get('name')`, where the addressed element is the first one in an array (enumeration begins with 0).

## 5. Use Case for Viber Messages

The configuration setting process is similar to the one for SMS. Define the data to be displayed in the Viber message. In contrast to SMS, a Viber message allows up to 1,000 symbols. It can display images and buttons with embedded links.

In such a case, the request body looks as follows:

```json
{
    "recipients": [
        {
            "jsonParam": "{


\"firstName\":\"John\",\"orderId\":\"JN134-173-389\",
\"deliveryAddress\":\"London, Post office №32\",
\"url\":\"https:\/\/example.com\/offers.html\",
\"imageUrl\":\"https:\/\/example.com\/apple_iphone_xs.jpg\"
}",
            "locator": "380501234567"
        }
    ],
    "email": false
}
```

In this request,

- **locator** is the recipient's phone number,
- **imageUrl** is a link to the image,
- **url** is a link for the button.

Create a Viber message:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ad23640f30eb5db5098d60590e354fe1ab3137c48fc9884fe29a5da480d3e52-e-9.webp",
        "Viber with variables",
        "Viber with variables"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 6. Use Case for Mob Push Notifications

To send a prepared single mobile push notification, the body of a request has to look like this:

```json
{
    "recipients": [
        {
            "jsonParam": null,
            "contactId": 449790707
        }
    ],
    "email": false
}
```

Instead of _contactId_, use the _locator_ parameter to identify a contact and transmit a token inside it.

The option to parametrize the content by transmitting data in the _jsonParam_ field is available for mobile push notifications, as well as for other channels:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c549ebbb4dfaa30616aa129a5535290b1c57c23a6dd2bd7f9c3f52be810d17e0-e-4.webp",
        "Parametrized mobile push message",
        "Parametrized mobile push message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The [Custom data](https://docs.yespo.io/docs/how-to-create-mobile-push-notifications#additional-settings) field can contain data in JSON format and be an additional source of information. The mobile application side must support the ability to use custom data — developers must provide these parameters when creating a mobile app.

## 7. Use Case for Web Push Notifications

Similar to the request for a Mobile Push message, in Web Push, instead of contactId, you can use the locator to identify a contact and transmit a token in it if contactId is missing.

```json
{
    "recipients": [
        {
            "jsonParam": null,
            "contactId": 449790707
        }
    ],
    "email": false
}
```

You can insert dynamic content into a Web push notification. To do that, insert variables in the message editor in place of the logo, large image, and links:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/54bf68649d98b7c106cdf1fbedba27a4e5838da14778a349353d50373f77c901-e-8.webp",
        "Dynamic content in web push message",
        "Dynamic content in web push message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In this case, the body of the request looks like this:

```json
{
    "recipients": [
        {
            "jsonParam": "{
\"userName\":\"Aleksei\",\"productName\":\"Huawei Watch GT Black\",
\"price\":\"6999 UAH\",\"https:\/\/example.com\/huawei-watch-gt\/431369.html\",
\"imageUrl\":\"https:\/\/example.com\/gallery\/huawei-watch-gt.jpeg\",
\"logo\":\"https:\/\/example.com\/Your-Logo.jpeg\",
\"moreOffer\":\"https:\/\/example.com\/more-offer.html\"
}",
            "contactId": 380470486
       }
    ],
    "email": false
}
```

## 8. Use Case for Telegram

Instead of _contactId_, you can use the locator to identify a contact and transmit a Telegram token to it.

```json
{
    "recipients": [
        {
            "jsonParam": null,
            "contactId": 449790111
        }
    ],
    "email": false
}
```

Use variables to add dynamic content to the message:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9374a2b6b5b41abf7e53e6eb61e2f82c3fc4f07c42453f21da52f621d3236ff6-e-3.webp",
        "Telegram",
        "Telegram"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 9. Use Case for App Inbox

The request body for sending App Inbox looks like this:

```json
{
    "recipients": [
        {
            "jsonParam": null,
            "contactId": 449790707
        }
    ],
    "email": false
}
```

Instead of _contactId_, you can use the _locator_ to identify a contact and transmit a Device ID in it.

Use variables to add dynamic content to the message:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1fbf10fb9face6773d858c05246259b9a85f20a895aaadcd62defda948eba33-e-1.webp",
        "App Inbox",
        "App Inbox"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Custom data_ field can contain data in JSON format and be an additional source of information. The mobile app or site to which the message is sent must support the use of such data.