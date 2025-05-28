---
title: 'FAQ: Integrating with API'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: 'FAQ: Integrating with API | Yespo Guide'
  description: >-
    Here you will find answers to frequently asked questions about API usage or
    fixing specific problems. It has more explanations, examples and
    descriptions than method description.
  robots: index
next:
  description: ''
---
See answers to the most common questions about Yespo API integration.

You can find all technical documentation on the data format for calling API requests [here](https://docs.yespo.io/reference/getting-started-with-your-api).

## How to Check API for Correct Performance and Valid Access Options

For example, you can get information about your account using the [Get account info](https://docs.yespo.io/reference/getaccountinfo-1) method. Follow these steps:

1. [Generate an API key](https://docs.yespo.io/reference/api-keys) and copy it to your clipboard.
2. Go to the <https://docs.yespo.io/reference/getaccountinfo-1> page.
3. Enter the username and password that is the copied API key above the example request.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f9d94d8065168e7dc0783734510abcdd3b09ab39c874e9d37cab32969c3b2d52-api-1-e.webp",
        "Get account info",
        "Get account info"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Try it!_

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07e0e79dfa1310db963e67a70460faef158180f5bc0a8f18d92db89d9ea0b84c-api-2-e.webp",
        "Try it!",
        "Try it!"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You should see your username and your organization name in the response:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/adc928adcc1db88c7b477072aabfd0248139608696051992461a1cfd450c6d41-image13.webp",
        "Response",
        "Response"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## How to Unsubscribe a Contact Who Has Unsubscribed in the Personal Account on the Site

There are two API resources to manage unsubscribes — [Add emails to unsubscribed list](https://docs.yespo.io/reference/addtounsubscribed-1) and [Remove emails from unsubscribed list](https://docs.yespo.io/reference/deletefromunsubscribed-1).

> 📘 Important
> 
> The method unsubscribes not contacts but their email addresses (other channels — SMS, Viber, Web Push — remain active). All contacts within the organization who may use these email addresses will stop receiving bulk emails from you.

The request body would look as follows:

```json
{
  "emails" : [ "test1@mail.com", "test2@mail.com" ]
}
```

where emails — the email addresses that will be marked as unsubscribed.

The _Remove emails from unsubscribed list_ request body is similar to the previous method: you enter the email addresses that will be deleted from the unsubscribed.

Let's look at working with the _Remove emails from unsubscribed list_ method:

1. Go to the <https://docs.yespo.io/reference/getaccountinfo-1> page. 
2. Click ADD STRING in BODY PARAMS and enter the addresses of unsubscribed contacts in the strings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b0ce73ed6989798388123f25792e43516cb59f2a7896c3293b9401ca60c03702-api-4-e.webp",
        "ADD STRING",
        "ADD STRING"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Try it!_

If the addresses in the request have been unsubscribed from your Yespo account, they will be removed from this list.

## How to Use Dynamic Content in Messages

There are two ways to implement sending an email with dynamic content:

- Using a workflow
- Using the [Send prepared message](https://docs.yespo.io/reference/sendextendedpreparedmessage-1) method

### Using a Workflow

Use the [Generate event](https://docs.yespo.io/reference/registerevent_1) API method to insert the data dynamically from the request body into the message. The array params may contain a random number of parameters:

```json
{
"name": "field name",
"value": "field value"
}
```

Use [Velocity variables](https://docs.yespo.io/docs/introduction-to-velocity) to insert dynamic data into a message. 

For example, you call the request in the following format:

```json
{
    "eventTypeKey": "testEvent",
    "keyValue": "example@email.com",
    "params": [{
        "name": "discount",
        "value": "5%"
        },{
        "name": "link",
        "value": "https://example.site.com/items_for_sale"
        }
]
}
```

The message must use the variables `$!data.get('discount')` and `$!data.get('link')`, instead of which the data from the request will be substituted.

To insert the content sent by the _Generate event_ method into the body of the message, prepare a workflow using this message, which the corresponding event will trigger. [Details >](https://docs.yespo.io/docs/creating-events)

### Using the Send Prepared Message Method

This method involves sending messages without using a workflow. The `{id}` in the link `https://yespo.io/api/v1/message/{id}/smartsend` is the identifier of the message into which the data will be inserted when sent to the recipient.

Minimum request body:

```json
{
  "recipients" : [ {
    "locator" : "...",
    "jsonParam" : "..."
  } ]
}
```

where:

- recipients are the array of the message recipients’ contact data;
- locator is a recipient. For example, an email address for emails and a phone number for SMS or Viber messages;
- jsonParam is data in the JSON format to insert in the message.

This method allows for generating different content for each recipient. The entered data is organized in "email + a set of parameters” pairs. The parameters are entered as a random JSON structure, and all fields are assigned `$data.get('field_name')`.

Using this method, you can:

- Set the condition for displaying a block of HTML code: `#if($data.get('field\_name').equals('0')) ... #end`.
- Loop through array elements: `#foreach($item in $data.get('items')) ... $item.get('name') ... $item.get('price') ... # end`.
- Perform arithmetic operations with field values in the body of the email.

Note: the double quotes inside the JSON structure with the parameters should be modified by an escape character: `"jsonParam" : "{\\"field1\\":\\"value1\\", ... }"`.

For more information, see the article Using the Send prepared message API method.

## How to Use Events for Triggers

Triggered campaigns can be launched using the [Generate event](https://docs.yespo.io/reference/registerevent_1) API method. This method is suitable for creating custom events; [follow the link for more details](https://docs.yespo.io/docs/how-use-v1event-api-resource).

We also recommend using the Generate event method to transfer orders. [Manual >](https://docs.yespo.io/docs/how-send-events-resource-v1event)

## How to Pass Orders via API, e.g., for Their Confirmation

You can also use the [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) method to pass orders. One request can contain up to 1,000 orders. Pass the array of items with the data on these products in orders to insert products in emails. You may not pass the array if you don't insert the product data in emails or pass orders only for RFM analysis.

The standard request body looks as follows:

```json
{
    "orders": [{
        "externalOrderId": "100500",
        "externalCustomerId": "12345",
        "totalCost": 1000,
        "status": "INITIALIZED",
        "date": "2017-03-08T09:30:00+02:00",
        "email": "mail@example.com",
        "phone": "380942583691",
        "firstName": "John",
        "lastName": "Smith",
        "currency": "USD",
        "shipping": 10,
        "discount": 0,
        "deliveryMethod": "express",
        "paymentMethod": "cash",
        "deliveryAddress": "First str. 1",
        "items": [{
            "externalItemId": "200600",
            "name": "Super Device",
            "category": "devices",
            "quantity": 1,
            "cost": 990,
            "url": "http://example.com/item/200600",
            "imageUrl": "http://example.com/item/200600/image.png",
            "description": "High quality"
        }]
    }]
}
```

Each order must contain the following obligatory fields:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a29ea855ac1b25bbb78d9dc48647700ea9ab7db290953776d1b0a7b97b5acfbe-api-5-r.webp",
        "Body params",
        "Body params"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The response to a successful request will have the 200 status.

You can use several statuses for orders:

- `INITIALIZED` for a newly created order.
- `IN_PROGRESS` for an order being delivered.
- `DELIVERED` for a paid and delivered order.
- `CANCELLED` for cancelled orders.

> 📘 Important
> 
> Only orders with the `DELIVERED` status are used for RFM analysis.

To update the status or other order details, pass the updated order with the same `externalOrderId`. The system uses this parameter to determine the uniqueness of orders.

To check whether the order has been sent into the system and whether the fields have been passed correctly, go to _Automation → Orders_. Click the order to see all the fields in the JSON format.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f54a3c517477bf265afd6d7751660e04a7b655da4a7f082bcec7e983af7b66f6-api-6-r.webp",
        "Order",
        "Order"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More about using order information in emails >](https://docs.yespo.io/docs/orders-automation)

## How to Get a Sent Status for a Message via API

Single messages are sent in the asynchronous mode via the following methods:

- [Send prepared message](https://docs.yespo.io/reference/sendextendedpreparedmessage-1),
- [Send email message](https://docs.yespo.io/reference/sendemail-1),
- [Send SMS message](https://docs.yespo.io/reference/sendsms-1),
- [Send Viber message](https://docs.yespo.io/reference/sendviber-1).

After an API request is called, your message is scheduled for sending and is sent within seconds.

The body of the response looks as follows:

```json
{
    "id": "0",
    "results": {
        "id": "0",
        "locator": "test@mail.com",
        "status": "OK",
        "requestId": "3ff28330-f8ef-4636-92ac-86345c16995e"
    }
}
```

To get the status of the message sent via any channel, call a request of the [Get single message status](https://docs.yespo.io/reference/getinstantmessagesstatus-1) method.

Ids — the identifiers requestId separated by a comma.

The request body looks as follows:

```json
{
    "results": {
        "status": "DELIVERED",
        "requestId": "3ff28330-f8ef-4636-92ac-86345c16995e",
        "failed": "false",
        "delivered": "true"
    }
}
```

## How to Integrate Subscription Form via API

Yespo offers [built-in functionality](https://docs.yespo.io/docs/widgets) for creating widgets without additional API settings.

To integrate a subscription form created using a third-party service, call the request using the [Subscribe a contact](https://docs.yespo.io/reference/subscribecontact-1) method. The minimum request body looks like this:

```json
{
  "contact" : {
    "channels" : [ {
      "type" : "email",
      "value" : "test@mail.com"
    } ]
  }
}
```

A contact with an email address will appear in the system.

To set the contact name, add the firstName field in the contact object to the request body:

```json
{
  "contact" : {
    "firstName" : "...",
    "channels" : [ {
      "type" : "email",
      "value" : "test@mail.com"
    } ]
  }
}
```

To specify which segments the subscribed contact should be in, add the groups field to the request — an array of string values for segment names. If any segments do not exist in the system, they will be created automatically:

```json
{
  "contact" : {
    "firstName" : "...",
    "channels" : [ {
      "type" : "email",
      "value" : "test@mail.com"
    } ]
  },
  "groups" : [ "Subscribers" ]
}
```

Two event types are automatically generated in the system after the call: 

- subscribeFromAPI – in case of creating a new contact;
- subscribeUpdateFromAPI – if such a contact already exists.

You can see these events in the _Triggers → Event history_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4930a70fc6fe22c3faafbbc51ac6e98dd1837c6aa328b72d1291a957b841531f-api-7-r.webp",
        "Event history",
        "Event history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Any type of event can be associated with a workflow launched when the event is generated. We recommend sending an email [to confirm a new contact subscription](https://docs.yespo.io/docs/subscription-form-configuration).

To ensure a new contact has been created, go to _Contacts → All contacts_ section and enter the contact ID in the search field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30a0840719b6d6c6459ca4ddfba734456d43a29dc45fc35e71e0c92c839ab028-api-8-r.webp",
        "Contacts",
        "Contacts"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You will see that the contact's email is grayed out, meaning it is inactive and requires confirmation from the owner.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cffd1dfef28f78d32f3b307d31a31a8b78a9ca8887defb7518f140620c7ba479-api-9-r.webp",
        "New contact",
        "New contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


It is impossible to send newsletters to such addresses; they can only receive subscription confirmation emails and other trigger messages, for example, an abandoned cart email or confirmation of a completed order.

## How to Pass Additional Field Values via API

Let's look at updating [additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) using the [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) method. The standard request body looks as follows:

```json
{
"contacts": [{
"channels": [{
"type": "email",
"value": "test@mail.com"
}],
"fields": [{
"id": 12345,
"value": "..."
}]
}],
"customFieldsIDs": [12345]
}
```

where

- channels is a list of the contact’s media channels (in the example, one media channel — email address — is passed);
- fields is a list of additional fields passed in pairs: field ID + value.

There are two ways to get all the IDs available in your account.

The first is to view the identifiers in the account menu → _Settings → Additional fields_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5778f95bb2fac2cea7106ba653f860060b039eaa41f6f34c0de9c0f3945c1bcc-api-10-r.webp",
        "Additional fields",
        "Additional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The second is to call the [Get the list of catalogs](https://docs.yespo.io/reference/getaddressbooks-1) method. This parameterless method will return you a structure like this:

```json
{
    "addressBook": {
        "addressBookId": "7200",
        "name": "Main",
        "fieldGroups": {
            "name": "Personal",
            "fields": [
                {
                    "id": "15867",
                    "name": "Birthday",
                    "description": {
                        "type": "date",
                        "required": "false",
                        "readonly": "false"
                    }
                },
                {
                    "id": "15868",
                    "name": "Gender",
                    "description": {
                        "type": "combobox",
                        "allowedValues": {
                            "possibleValues": [
                                "M",
                                "F"
                            ]
                        },
                        "required": "false",
                        "readonly": "false"
                    }
                }
            ]
        }
    }
}
```

The fields list is a collection of all your additional fields. In addition to other information, each object in this list contains a field identifier that must be used when passing its value.

## How to Test API Using Postman

Postman is a popular API testing tool. It provides a user-friendly interface for creating, sending, and tracking requests.

To get started with Postman, <a rel="nofollow" href="https://www.getpostman.com/downloads/" target="_blank"> download</a> and install it on your computer.

### Testing the Get Account Info Method

1. Select _Basic Auth_ in the parameters, _Authorization_ tab, _Type_ line:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/152e25e9aa67d9b48c3a12f4f18b3dfd29f0741499c6543bfa1fa6fb5e3a68c0-api-11-r.webp",
        "Basic Auth",
        "Basic Auth"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Log in:

- enter any value in the _Username_ field,
- enter the value of your API key in the _Password_ field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d6424e4bc8d60805327330c7b1cfe580942b694d21bcc19ee0794b714281a26d-api-12-r.webp",
        "Log in",
        "Log in"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the GET method and enter the `https://yespo.io/api/v1/account/info` link.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/baef3343955f4de400724be5781653bb00ff3fdf9dd1481f5826b3f32806000d-api-19-r.webp",
        "Get Account Info Method",
        "Get Account Info Method"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click the _Send_ button.

You should see your username and your organization name in the response:

```
{
    "userEmail": "api-user162065",
    "organisationName": "ExamleName"
}
```

### Testing the Remove Emails from Unsubscribed List Method

1. Select the POST request method and enter the `https://yespo.io/api/v1/emails/unsubscribed/delete` link.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d905f368509220253f8d2620d07091f614a4302b775600f451a326d15e011f87-api-20-r.webp",
        "Remove emails from unsubscribed list",
        "Remove emails from unsubscribed list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select _raw_ and JSON data transfer format in the _Body_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/256878309fc376b85bfeb265576e0c771112bbabaf0ad035b5369d475df9c1ab-api-21-r.webp",
        "Body section",
        "Body section"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Specify the request body in the following format:

```
{
  "emails" : [ "...", "..." ]
}
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e5b0217ff0819e86759eda7164169deaaea545ec5d2a20a7bee53235a32b0bc-api-22-r.webp",
        "Request body",
        "Request body"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Send_.

If the addresses in the request have been unsubscribed from your Yespo account, they will be removed from this list.

### Testing the Generate Event v2 Method

1. Select the POST request method and enter the `https://yespo.io/api/v2/event` link.
2. Select _raw_ and JSON data transfer format in the _Body_ section.
3. Specify the request body in the following format:

```json
{
    "eventTypeKey": "create_contact",
    "keyValue": "site@com.net",
    "params":
    [
        {
            "name": "email",
            "value": "site@ukr.net"
        },
        {
            "name": "phone",
            "value": "380501234567"
        },
        {
            "name": "externalCustomerId",
            "value": "AV13760"
        },
        {
            "name": "json",
            "value":
            {
                "profileInputs":
                [
                    {
                        "profileInputId": 10001,
                        "value": "2020-11-23"
                    }
                ]
            }
        }
    ]
}
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7c2708a14dca9d087c56ff4085d21cc8a23ddc6b539eaa83a1478b74fcbcee66-api-23-r.webp",
        "Request body",
        "Request body"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Send_.

A successfully submitted request will appear in the event history in your Yespo account.