---
title: Order Transfer Using the Add Orders API Method
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Order Transfer Using the Add Orders API Method | Yespo Guide
  description: >-
    Learn how to automate your sales process using API and dynamic variables.
    Order automation allows to process your sales, create triggered order series
    and send personalized post-purchase messages.
  robots: index
next:
  description: ''
---
To transfer orders, send a request using the [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) API method. You can transfer up to 1000 orders in one request.

Every time you send an API order, the system creates an [event](https://docs.yespo.io/docs/events-and-behaviour-tracking) that can trigger a workflow. You can create different events for different order statuses, which allows setting triggers for each change in the order status.

## Event Names

Event names consist of two parts: the word order and its status, for example, `orderINITIALIZED`, `orderIN_PROGRESS`, `orderDELIVERED`, `orderCANCELLED`, `orderABANDONED_SHOPPING_CART`.

To see the created events, go to _Automation_ → _Event history_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6bf10c44a968d429ad13f3a7c3edb605519a9a47849c3a183d152e3437bfdf44-Add_orders_1.webp",
        null,
        "Events history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Event Parameters

Each event contains required parameters and can include optional parameters.

- `${eventKey}` - event unique key transferred in `externalOrderId`. Used as an order identifier;
- `${orderId}` - event ID in our system. Required to assign the event to a workflow.

The contact ID must be one of the following:

- `${externalCustomerId}` - external contact ID;
- `${email}` - contact’s email address;
- `${phone}` - contact’s phone number.

> 📘 Important
> 
> If there is no external customer ID, email or phone number in the event, the system can't match the contact with the order and can’t send messages to such contacts. In such cases, you can see contact ID in the _Automation_ → _Orders_ tab → _Contact data_ column

To substitute parameter values in messages, send the fields with event parameters as an array.

- Required parameters for the order array: `externalOrderId`, `totalCost`, `status`, `date`, `currency`.
- Required parameters for the items array: `externalItemId`, `quantity`.

> 📘 Note
> 
> The price of the products transferred in an order must match the `totalCost` value (total order amount). If a customer buys an item with a discount, it should be placed in the `items.cost` field for each product.

You don't need to transfer the items array if you don't use product data in messages or send orders only for RFM analysis.

[See the full list of order fields with descriptions](https://docs.yespo.io/reference/ordersbulkinsert-1).

Request body example:

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

If the request is successful, the server returns the _200_ status code. The response body contains the list of orders that cannot be added or updated.

The possible reasons for an order to fail:

- One or more required fields are empty, or the format is incorrect.
- All the following optional fields are empty: `externalCustomerId`, `email`, `phone`. At least one of them is required for order creation.

> 🚧 Important
> 
> Only orders with the _DELIVERED_ status are used to build the RFM table and calculate revenue from campaigns on the _Report_ tab.
> 
> Exceptions are orders received from the mobile SDK, in which case the statuses INITIALIZED and DELIVERED are taken into account by default in the revenue visualization. If necessary, the INITIALIZED statuses can be disabled — for this, contact our support service [support@yespo.io](mailto:support@yespo.io)

You can use orders with the _DELIVERED_ status to build segments with the following conditions: _average check, order count, last order date_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1f0fd310487d5bddcc788a6716f5f41931ecd5aee782d5c9cda1d3566779cf01-Add_orders_2.webp",
        null,
        "Building segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Send an _ABANDONED\_SHOPPING\_CART_ status for abandoned carts. Use it if you track abandoned carts on an external platform. If you use web tracking, you don’t need to send abandoned cart events through [API](https://docs.yespo.io/reference/getting-started-with-your-api).

To update the status or other order data, send an updated order with the same `externalOrderId` parameter. It determines the order's uniqueness in the system.

## Checking Event Parameters

To check whether the order is sent to the system with all the parameters, go to _Automation_ → _Orders_. Click the order ID to see all the fields in _JSON_ format. Also you can see information about the contact by clicking _Contact preview_ icon.

> 🚧 Important
> 
> For each unique contact, transfer a unique `externalCustomerId` parameter with the phone number or email that should be the same in the order and the contact card.
> 
> - If you’ve already sent the order with this `externalCustomerId` value, the system will automatically assign a new order to the contact with this ID.
> - If the `externalCustomerId` value is new, the system will match it by phone number or email.

## Creating Workflow

1. Go to the _Automation → Workflows_ section and click _New workflow._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8b91feee87996f73438fa0807593650434b2eeaa263d60f285d931b27c73d77b-building-and-editing-workflows.webp",
        "New workflow",
        "New workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Specify the workflow’s name (_Order delivered, Order in progress,_ etc.).
3. Add the following blocks to the workflow:

- The _Task_ block → _Get order_. Using this block, the system will extract all the order data and transfer it to the message;
- A message-sending block. Select the message that you previously created for this workflow (order notification, NPS, etc.)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/832861e3e6b692b6949ff304336aa3d4cc30ef9717388cc5228f21799f72e5c4-workflow-details.webp",
        "Get order",
        "Get order"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Instead of one message, you can make a series. For example, 1-2 weeks after the message about the delivered order, send a request to leave feedback.

More about [setting up workflow start and stop conditions >](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions)