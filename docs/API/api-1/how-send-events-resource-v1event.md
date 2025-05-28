---
title: Sending Orders via the API Resource Generate event
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Orders via the API Resource Generate event | Yespo Guide
  description: >-
    Learn how to send order data to the system using the API resource Generate
    event. What parameters are required and how to add and fill additional
    fields.
  robots: index
next:
  description: ''
---
Order data is transmitted to our system via the _[Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1)_ resource that has the following limitations:

- Fixed fields that are determined by the specification;
- Impossible to add custom fields;
- Order parameters cannot be used to build segments.

You can overcome them with the resource _[Generate event](https://docs.yespo.io/reference/registerevent_1)_ that can be used to replace or complement _Add orders_. By using it, you’ll be able to:

- Transmit more data with additional fields;
- Use [segmentation by events](https://docs.yespo.io/docs/how-to-use-event-segmentation) and their parameters, for example, sort out contacts who bought a particular item within a week;
- Expand/receive RFM segmentation by order without additional usage of _Add orders_.

> 📘 Important
> 
> To save orders in the system, you need to set up segmentation by events as the event contains a contact identifier. It can be determined based on the default or conditional parameters.

## How to Use _Generate event_ to Send Orders

For example, you can set up identification by a unique token. The order will not be saved until these parameters are transmitted to the system. If you don’t set your own parameters, the system will search the identifier based on default parameters (email, phone, etc.).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4571b3f6787189f368a40ae40bc74f087edd534cc0d06dc5556608792e8941c3-events.png",
        "Segmentation by events",
        "Segmentation by events"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can send _Generate event_ only for the existing contact. To send the order for a new contact, first import this contact into the system via:

- [_Add/update a contact_](https://docs.yespo.io/reference/addcontact-1);
- [_Add orders_](https://docs.yespo.io/reference/ordersbulkinsert-1).

To send an order, you need to specify the event type. Choose the type from the below table based on the order status.

| Event type     | Description                                                                                                                                                 |
| :------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| orderCreated   | Creates an order with the status indicated in the array. Valid statuses: `INITIALIZED`, `IN_PROGRESS`, `DELIVERED`, `CANCELLED`, `ABANDONED_SHOPPING_CART`. |
| orderUpdated   | Updates the order                                                                                                                                           |
| orderDelivered | Changes the order status to `DELIVERED`                                                                                                                     |
| orderCancelled | Changes the order status to `CANCELLED`                                                                                                                     |

### orderCreated

To create an order, name the parameters as indicated in the documentation and fill in the required parameters. If any of the required parameters isn’t filled, the event is ignored and the order will not be sent.

- `${eventKey}` - event unique key transferred in externalOrderId. Used as an order identifier;
- `${orderId}` - event ID in our system. Required to assign the event to a workflow.

The contact ID must be one of the following:

- `${externalCustomerId}` - external contact ID;
- `${email}` - contact’s email address;
- `${phone}` - contact’s phone number.

To substitute parameter values in messages, send the fields with event parameters as an array.

- Required parameters for the order array: `externalOrderId`, `totalCost`, `status`, `date`, `externalCustomerId / email / phone`.
- Required parameters for the items array: `externalItemId`, `name`, `quantity`, `cost`, `url`, `imageUrl`.

> 📘 Note
> 
> The price of the products transferred in an order must match the `totalCost` value (total order amount). If a customer buys an item with a discount, it should be placed in the `items.cost` field for each product.

Example:

```json
{
    "eventTypeKey": "orderCreated",
    "keyValue": "380501234567",
    "params": [
        {
            "name": "phone",
            "value": "380501234567"
        },
        {
            "name": "externalOrderId",
            "value": "12345679"
        },
        {
            "name": "externalCustomerId",
            "value": "AV13760"
        },
        {
            "name": "totalCost",
            "value": "258.0"
        },
        {
            "name": "status",
            "value": "INITIALIZED"
        },
        {
            "name": "date",
            "value": "2020-05-14T10:11:00"
        },
        {
            "name": "currency",
            "value": "UAH"
        },
        {
            "name": "items",
            "value": [
                {
                    "externalItemId": "200600",
                    "name": "Super Device",
                    "category": "devices",
                    "quantity": 1,
                    "cost": 990,
                    "url": "http://example.com/item/200600",
                    "imageUrl": "http://example.com/item/200600/image.png",
                    "description": "High quality"
                }
            ]
        }
    ]
}
```

> ❗️ Important
> 
> To save the event assigned to the contact, you need to know what event parameter contains the identifier. By default, the system searches for the following parameters excluding the register: ContactId, Contact\_id, Email, EmailAddress, UserEmail, ContactEmail, Phone, SMS, PhoneNumber, PushToken, ContactKey, Contact\_key. All values, except for the email address, are mapped including the register.

[block:parameters]
{
  "data": {
    "h-0": "Field",
    "h-1": "Description",
    "0-0": "status",
    "0-1": "Can take one of the following values: `INITIALIZED`, `IN_PROGRESS`, `DELIVERED`, `CANCELLED`, `ABANDONED_SHOPPING_CART`.",
    "1-0": "date",
    "1-1": "The date format is YYYY-MM-ddTHH:mm:ss, according to <a rel=\"nofollow\" href=\"https://en.wikipedia.org/wiki/ISO_8601\" target=\"_blank\"> ISO 8601</a>. Example: 2020-05-14T10:11:00.",
    "2-0": "items",
    "2-1": "Items from the order (optional). If you use this field, the required fields must be specified for the orderItem method. Pass the values of items as a JSON string. We support nesting up to the second level inclusive. This means that if another array or object is passed in the items array, it will remain serialized (escaped). We do not ignore such data, but since it will be a string, it is impossible to work with it."
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


### orderUpdated

- Updates the order that has the parameter `externalOrderId` filled.
- If the transmitted order doesn’t exist in the system, it’s created anyway.
- The parameters must be named as indicated in the documentation. If the order is to be created, the `orderCreated` requirements apply.

### orderDelivered

- Changes the order status to `DELIVERED`.
- If the order does not exist, it is ignored.

> 📘 Note
> 
> Only orders with the `DELIVERED` status are used to build the RFM table and calculate revenue from campaigns on the _Report_ tab.
> 
> Exceptions are orders received from the mobile SDK, in which case the statuses `INITIALIZED` and `DELIVERED` are taken into account by default in the revenue visualization. If necessary, the `INITIALIZED` statuses can be disabled — for this, contact our support service [support@yespo.io](mailto:support@yespo.io)

### orderCancelled

- Changes the order status to `CANCELLED`.
- If the order does not exist, it is ignored.