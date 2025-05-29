---
title: Sending Past Events
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Past Events | Yespo Guide
  description: >-
    A detailed guide on transferring offline orders, contact activities, service
    subscriptions, and other events to the Yespo system.
  robots: index
next:
  description: ''
---
If you have migrated from another service or just created an account in our platform, and you have a history of

* offline orders,
* contact activity,
* subscriptions,
* or other events you want to use for advanced segmentation,

you can transfer the available data from your CRM or other data store to our system via the API resource \_[Generate past events](https://docs.yespo.io/reference/sendhistoryevents_1).

> 📘 Important
>
> Before importing events, enable segmentation for the types of events you want to download.
>
> If your tariff plan does not include segmentation by events, please submit a request to [sales@yespo.io](mailto:sales@yespo.io)

[How to set up segmentation by events](https://docs.yespo.io/docs/how-to-use-event-segmentation)

To assign events to contacts, [pre-import](https://docs.yespo.io/docs/uploading-file-with-user-profile-data) the contact database to your account.

For example, you have a certain number of orders over the past year, and you want to [build a segment](https://docs.yespo.io/docs/how-to-use-event-segmentation) with customers interested in a certain type of products or services, get statistics on the average check, or segment contacts by geodata (if applicable).

Convert these orders into a `JSON` format supported for API according to the specification, and send them to the system. You can send an array of up to 500 such events within one request. Specify the time of each event in the field `occurred`:

* format of date: `YYYY-MM-DD`;
* format of date with the time: `YYYY-MM-DDTHH:mm`.

For example, you send an order of two mobile devices bought at a few years interval:

```json
{
	"events": [{
			"eventTypeKey": "orderCreated",
			"keyValue": "John@yourcompany.com",
			"params": [{
				"name": "email",
				"value": "John@yourcompany.com"
			}, {
				"name": "externalOrderId",
				"value": "9239234234234"
			}, {
				"name": "externalCustomerId",
				"value": "d8b6a037-4b6d-11eb-a2f0-0050569b2dc99902"
			}, {
				"name": "totalCost",
				"value": "258.0"
			}, {
				"name": "status",
				"value": "INITIALIZED"
			}, {
				"name": "date",
				"value": "2020-05-14T10:11:00"
			}, {
				"name": "currency",
				"value": "UAH"
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
			}],
			"occurred": "2023-03-22T14:30"
		},

		{
			"eventTypeKey": "orderCreated",
			"keyValue": "Hanna@yourcompany.com",
			"params": [{
				"name": "email",
				"value": "Hanna@yourcompany.com"
			}, {
				"name": "externalOrderId",
				"value": "9239234235555"
			}, {
				"name": "externalCustomerId",
				"value": "d8b6a578-4b6d-11eb-a2f0-0050569b2dc99902"
			}, {
				"name": "totalCost",
				"value": "546.0"
			}, {
				"name": "status",
				"value": "INITIALIZED"
			}, {
				"name": "date",
				"value": "2020-05-14T11:11:00"
			}, {
				"name": "currency",
				"value": "UAH"
			}, {
				"name": "items",
				"value": [{
					"externalItemId": "200601",
					"name": "New Device",
					"category": "devices",
					"quantity": 1,
					"cost": 990,
					"url": "http://example.com/item/200601",
					"imageUrl": "http://example.com/item/200601/image.png",
					"description": "High quality"
				}]
			}],
			"occurred": "2023-03-22T15:30"
		}
	]
}
```

Apart from basic fields with the name, price, and link to a product, you can send any related data that is available to build segments. For example, you can send the country and city of the buyer to use for segmentation by geolocation.

```json
{

    "name": "city",

    "value": "Los Angeles"

 },{

    "name": "country",

    "value": "USA"

}
```

Based on the available datasets you can build dynamic segment:

<Image align="center" width="80% " src="https://files.readme.io/a245deeec1607c00bb51551399a60366a254b8a074b860ed3936c4093e0f391c-add-dynamic-segment.webp" />

You can also delete old or irrelevant events. To do this, send a request to the same resource, but using the method type [DELETE](https://docs.yespo.io/reference/removehistoryevents). Specify the time range to remove in the request body:

```json
{

    "from" : "2019-06-04T10:47",

    "to" : "2020-01-04T13:33"

}
```

The method `DELETE` is inactive by default. To activate it, please contact our support team.