---
title: Order Transfer Using the Generate Event API Method
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Order data is transmitted to our system via the resource [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) that has a number of limitations:

* Fixed fields that are determined by the specification;
* Impossible to add custom fields;
* Order parameters cannot be used to build segments.

You can overcome them with the resource [Generate event](https://docs.yespo.io/reference/registerevent_1) that can be used to replace or complement *Add orders* API method. By using it, you’ll be able to:

* Transmit more data with additional fields;
* Use [segmentation by events](https://docs.yespo.io/docs/segmentation-by-events) and their parameters, for example, sort out contacts who bought a particular item within a week;
* Expand/receive RFM segmentation by order without additional usage of *Add orders*.

> 🚧
>
> To save orders in the system, you need to set up segmentation by events as the event contains a contact identifier. It can be determined based on the default or conditional parameters.

## How to Send Orders

For example, you can set up identification by unique token. The order will not be saved until these parameters are transmitted to the system. If you don’t set your own parameters, the system will search the identifier based on default parameters (email, phone, etc.).

<Image width="80%" src="https://files.readme.io/c40816a-order1.png" />

You can use [Generate event](https://docs.yespo.io/reference/registerevent_1) only for the existing contact. To send the order for a new contact, first import this contact into the system via:

* [Add/update a contact](https://docs.yespo.io/reference/addcontact-1);
* [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1).

To send an order, you need to specify the event type. Choose the type from the below table based on the order status.

| Event type                                                                         | Description                                              |
| :--------------------------------------------------------------------------------- | :------------------------------------------------------- |
| [orderCreated](https://docs.yespo.io/docs/sending-orders-via-api#ordercreated)     | Creates the order with the status indicated in the array |
| [orderUpdated](https://docs.yespo.io/docs/sending-orders-via-api#orderupdated)     | Updates the order                                        |
| [orderDelivered](https://docs.yespo.io/docs/sending-orders-via-api#orderdelivered) | Changes the order status to `DELIVERED`                  |
| [orderCancelled](https://docs.yespo.io/docs/sending-orders-via-api#ordercancelled) | Changes the order status to `CANCELLED`                  |

### orderCreated

To create an order, name the parameters as indicated here and fill in the required parameters. If any of the required parameters isn’t filled, the event is ignored and the order will not be sent.

<Image width="80%" src="https://files.readme.io/1f39f72-Required_field.png" />

Example:

```json
{
    "eventTypeKey": "orderCreated",
    "keyValue": "380501234567",
    "params": [
        {
            "name": "phone",
            "value": "380501234567"
        },{
            "name": "externalOrderId",
            "value": "12345679"
        }, {
            "name": "externalCustomerId",
            "value": "AV13760"
        }, {
            "name": "totalCost",
            "value": "258.0"
        }, {
            "name": "currency",
            "value": "USD"
        }, {
            "name": "status",
            "value": "INITIALIZED"
    }, {
        "name": "date",
        "value": "2020-05-14T10:11:00"
    }, {
        "name": "items",
        "value": [{
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

> 📘 Important
>
> To save the event assigned to the contact, you need to know what event parameter contains the identifier. By default, the system searches for the following parameters excluding the register: `ContactId`, `Contact_id`, `Email`, `EmailAddress`, `UserEmail`, `ContactEmail`, `Phone`, `SMS`, `PhoneNumber`, `PushToken`, `ContactKey`, `Contact_key`. All values, except for the email address, are mapped including the register.

📌 Pay attention\
If you want to show product data in an email, you need to use products in the event.

```json
{
    "eventTypeKey": "orderCreated",
    "keyValue": "380501234567",
    "params": [
        {
            "name": "phone",
            "value": "380501234567"
        },{
            "name": "externalOrderId",
            "value": "12345679"
        }, {
            "name": "externalCustomerId",
            "value": "AV13760"
        }, {
            "name": "totalCost",
            "value": "258.0"
        }, {
            "name": "currency",
            "value": "USD"
        }, {
            "name": "status",
            "value": "INITIALIZED"
        }, {
            "name": "date",
            "value": "2020-05-14T10:11:00"
        }, {
            "name": "items",
            "value": [{
                "externalItemId": "200600",
                "name": "Super Device",
                "category": "devices",
                "quantity": 1,
                "cost": 990,
                "url": "http://example.com/item/200600",
                "imageUrl": "http://example.com/item/200600/image.png",
                "description": "High quality"
            }]
        },
        {
            "name": "products",
            "value": [{
                "array": [{
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
    ]
}
```

### orderUpdated

Updates the order that has the parameter `externalOrderId` filled.\
If the transmitted order doesn’t exist in the system, it’s created anyway.

The parameters must be named as indicated in `BODY PARAMS`. If the order is to be created, the `orderCreated` requirements apply.

### orderDelivered

Changes the order status to `DELIVERED`.\
If the order does not exist, it is ignored.

### orderCancelled

Changes the order status to `CANCELLED`.
