---
title: Webhooks for Tracking Activity
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Webhooks for Tracking Activity | Yespo Guide
  description: >-
    Learn how to use webhooks to automate follow-up activities and enhance your
    workflows. Discover how to integrate webhooks for seamless communication,
    improved efficiency, and better user engagement.
  robots: index
next:
  description: ''
---
<a rel="nofollow" href="https://en.wikipedia.org/wiki/Webhook" target="_blank">Webhooks</a> allow you to track contact activity in the Yespo in real time and automatically send notifications about each event to a specified client URL

Webhooks are configured by adding an external URL to your account. After that, you will automatically receive data about contact actions across various media channels via POST requests.

The system sends requests to your server whenever one of the following events occurs:

- **Delivered** — the message was delivered to the contact.
- **Undelivered** — the message could not be delivered.
- **Read** — the contact opened the message.
- **Unsubscribed** — the contact unsubscribed from the campaign.
- **Clicked** — the contact clicked on a link in the message.
- **Spam** — the message was marked as spam.
- **Subscription changed** — the contact changed their subscription category.

> 📘 Note
> 
> Before setting up webhooks, you need to configure an URL on your server where you want to receive messages — POST requests in JSON format — and process the data accordingly.

## Creating Data Export

Open the _Data export_ tab in your account settings, click the _New data export_ button, and select _Webhook_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/330b56e0ac0f8113eff88899e975e5a425ed9c5454a318a2b9aad78e9926c770-webhooks-for-tracking-activity-01.webp",
        null,
        "New data export"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Connection

Add a _Webhook name_ and specify the Webhook URL you previously set up on your server.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d680c93d5192ba2f421acbb91380a29ca03b28edba8cebd4181e12785094c35-webhooks-for-tracking-activity-02.webp",
        null,
        "Connection"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Autentification (optional)

If authentication is enabled on your server, enter the login and password that your server requires to accept requests. Enable the _Authentication_ toggle and fill in the corresponding fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c3711183b07820f4735cd9eee2fc89380131a56b452102ae1ccbfcb83bde41b-webhooks-for-tracking-activity-03.webp",
        null,
        "Autentification"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Export Activity Statuses

By default, all activity statuses are selected for tracking. You can modify this list by deselecting the checkboxes following to the statuses you don't want to track.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/243be2350bac68013dbb01353f32259ab104a40b91f458b8346fd8a54df6e4f7-webhooks-for-tracking-activity-04.webp",
        null,
        "Export activity statuses"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After setting up the data export via webhook, click the _Save_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/958eb6117c147420d016a81ab881e14c248bee52d3fdc6103e3fd678d20feebc-webhooks-for-tracking-activity-05.webp",
        null,
        "Save settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The webhook will be active, and data will be sent in real-time to the specified URL.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a6db876bb825336ba09c3c8714c55b2a9dfdd40c74362316f97632d4bd4fffc6-webhooks-for-tracking-activity-06.webp",
        null,
        "Active webhook"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Settings Verification

The system will check the URL's availability using the GET request. If errors occur, your server may block our request for various reasons. You can determine the exact cause based on the server error code on your side.

If the check is successful, the setup is complete.

After that, perform any action in your Yespo account — for example, send yourself an email. The POST request in JSON format with information about the latest activity will be sent to the specified URL.

For example, if a contact receives an email, opens it, and clicks a link, the system will sequentially send three requests with the statuses: `DELIVERED`, `READ`, and `CLICKED`.

If the webhook URL does not return the HTTP 200 response code, the POST request attempt is repeated with incremented intervals (1 minute, 2 minutes, 4 minutes, 8 minutes, and up to 1 request per hour). The following requests are postponed until the first one is successfully delivered, and then delivered in their sequence.

## Webhook Deactivation

To deactivate the webhook, click the three-dot icon, select _Deactivate webhook_, and confirm the action.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32eb6343be50cd9b27f46f618c6e5aef3b96f717107703b3c51191101646b362-animation.gif",
        null,
        "Webhook deactivation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Deactivation suspends the sending of requests, but the webhook remains saved in the system and can be reactivated later.

## Data Export Editing

To change the settings, click on the webhook name, edit the data, and save the settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f39d22d98d9ceeaca518988a5a566c8e5215075e197b06b0aa40f61b0c15f9ed-webhooks-for-tracking-activity-08.gif",
        null,
        "Data Export Editing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## List of Possible Parameters

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "activityDateTime",
    "0-1": "string",
    "0-2": "Activity date and time.",
    "1-0": "activityStatus",
    "1-1": "string",
    "1-2": "Activity status:  \n`SENT`– the message is sent (for Mobile Push only)  \n`DELIVERED` – the message was delivered.  \n`UNDELIVERED` – the message was undelivered (statusDescription contains the reason).  \n`READ` – the message was read.  \n`UNSUBSCRIBED` – a contact unsubscribed from the broadcasting list.  \n`CLICKED` – a contact clicked links in the message.  \n`SPAM` – a contact reported spam.  \n`SUBSCRIPTION_CHANGED` – a contact changed the subscription category.",
    "2-0": "broadcastId",
    "2-1": "int",
    "2-2": "Broadcast ID.",
    "3-0": "clickEventLink",
    "3-1": "string",
    "3-2": "Contains the link clicked by a contact (when the status is `CLICKED`).",
    "4-0": "contactId",
    "4-1": "int",
    "4-2": "Contact ID.",
    "5-0": "email",
    "5-1": "string",
    "5-2": "Contact Email.",
    "6-0": "externalCustomerId",
    "6-1": "string",
    "6-2": "A unique customer ID in the client’s system.",
    "7-0": "from",
    "7-1": "string",
    "7-2": "Sender name (in Email, SMS, and Viber messages).",
    "8-0": "hardBounce",
    "8-1": "bool",
    "8-2": "This field is returned only in case when the status is `UNDELIVERED`. The parameter informs that the contact is in the black list.  \n  \n_false_ – not in the black list at the moment of message delivery.  \n_true_ – in the black list at the moment of message delivery.",
    "9-0": "iid",
    "9-1": "string",
    "9-2": "Service Parameter.",
    "10-0": "mediaType",
    "10-1": "string",
    "10-2": "Media type  (SMS, Email, Web Push, Viber, Mobile Push, AppInbox, Widget, In-App, Telegram).",
    "11-0": "messageId",
    "11-1": "int",
    "11-2": "Message ID.",
    "12-0": "messageInstanceId",
    "12-1": "int",
    "12-2": "Message instance ID.",
    "13-0": "messageLanguageCode",
    "13-1": "string",
    "13-2": "Identifier of the message language.",
    "14-0": "messageName",
    "14-1": "string",
    "14-2": "Message name (empty for test emails).",
    "15-0": "messageTag",
    "15-1": "string",
    "15-2": "Message tag.",
    "16-0": "mobilepush",
    "16-1": "string",
    "16-2": "Mobile app subscriber token.",
    "17-0": "osName",
    "17-1": "string",
    "17-2": "Device operating system.",
    "18-0": "osType",
    "18-1": "string",
    "18-2": "Device type.",
    "19-0": "sms",
    "19-1": "string",
    "19-2": "Contact phone number.",
    "20-0": "sourceEventId",
    "20-1": "int",
    "20-2": "Source event ID.",
    "21-0": "sourceEventKey",
    "21-1": "string",
    "21-2": "Source event key.",
    "22-0": "sourceEventTypeKey",
    "22-1": "string",
    "22-2": "Source event type key.",
    "23-0": "statusData",
    "23-1": "",
    "23-2": "Data array.",
    "24-0": "statusDescription",
    "24-1": "string",
    "24-2": "This field is returned only in the event when the status is `UNDELIVERED`. It contains the reason why the message has been undelivered. This may be a recipient server response, a system response saying that message delivery was not possible, and other similar reasons.",
    "25-0": "subscription",
    "25-1": "",
    "25-2": "Data array.",
    "26-0": "subscriptions",
    "26-1": "array of strings",
    "26-2": "Subscription category keys.",
    "27-0": "viber",
    "27-1": "string",
    "27-2": "Contact phone number.",
    "28-0": "viewMessageLink",
    "28-1": "string",
    "28-2": "Contains the link to the message web version.",
    "29-0": "webpush",
    "29-1": "string",
    "29-2": "Web push subscriber token.",
    "30-0": "workflowBlockId",
    "30-1": "string",
    "30-2": "Workflow block ID.",
    "31-0": "workflowId",
    "31-1": "int",
    "31-2": "Workflow ID.",
    "32-0": "workflowInstanceId",
    "32-1": "uuid",
    "32-2": "The identifier of a particular workflow launch. Use it to group mailings within the launch of a workflow."
  },
  "cols": 3,
  "rows": 33,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


Below are webhook test examples as a JSON array with all possible status options.

Bulk campaign:

```json
[
  {
    "broadcastId": 3459207,
    "messageName": "test",
    "iid": "99d591ab-e7a5-49ed-8e16-b3023378fc18",
    "contactId": 1967597908,
    "externalCustomerId": "789456512",
    "email": "test1@yourdomain.com",
    "mediaType": "email",
    "activityStatus": "DELIVERED",
    "messageId": 2489300,
    "messageInstanceId": 4702518,
    "activityDateTime": "2023-09-14T08:30:03",
    "viewMessageLink": "https://u51739.esclick.me/J9o6EvyAKGmB",
    "statusData": {}
  },
  {
    "broadcastId": 3459207,
    "messageName": "test",
    "iid": "4af20897-de88-4ad0-ada3-dc4bcf14e8d8",
    "contactId": 889891911,
    "externalCustomerId": "262ac297-6ae1-11ec-a2ec-0050569bdf92",
    "email": "test2@yourdomain.com",
    "mediaType": "email",
    "activityStatus": "DELIVERED",
    "messageId": 2489300,
    "messageInstanceId": 4702518,
    "activityDateTime": "2023-09-14T08:30:03",
    "viewMessageLink": "https://u51739.esclick.me/J9o6Dl1wrDeB",
    "statusData": {}
  },
  {
    "broadcastId": 3459207,
    "messageName": "test",
    "iid": "b14dec37-806e-4bc4-ba71-a5911a7d7ce4",
    "contactId": 1026901517,
    "email": "test3@yourdomain.com",
    "mediaType": "email",
    "activityStatus": "DELIVERED",
    "messageId": 2489300,
    "messageInstanceId": 4702518,
    "activityDateTime": "2023-09-14T08:30:03",
    "viewMessageLink": "https://u51739.esclick.me/J9o6Dttf6fOB",
    "statusData": {}
  },
  {
    "broadcastId": 3459207,
    "messageName": "test",
    "hardBounce": false,
    "iid": "99d591ab-e7a5-49ed-8e16-b3023378fc18",
    "contactId": 1967597908,
    "externalCustomerId": "789456512",
    "email": "test1@yourdomain.com",
    "mediaType": "email",
    "activityStatus": "UNDELIVERED",
    "messageId": 2489300,
    "messageInstanceId": 4702518,
    "activityDateTime": "2023-09-14T08:30:07",
    "statusDescription": "5.1.2 (bad destination system: no such domain)",
    "viewMessageLink": "https://u51739.esclick.me/J9o6EvyAKGmB",
    "statusData": {}
  }
]
```

Triggered campaign:

```json
[
  {
    "messageName": "test",
    "workflowId": 340484,
    "workflowBlockId": "_05cae26d9ae85e1eb40ed34765f9c7be",
    "sourceEventKey": "9d0c163d-cc3b-4f9e-bb03-2f5d1111ef91",
    "sourceEventTypeKey": "productViewed",
    "workflowInstanceId": "da33697d-52d8-11ee-9d24-7ec2059b5114",
    "iid": "019b7450-52d9-11ee-85c4-959256ea468c",
    "contactId": 889891911,
    "externalCustomerId": "262ac297-6ae1-11ec-a2ec-0050569bdf92",
    "email": "test1@yourdomain.com",
    "mediaType": "email",
    "activityStatus": "DELIVERED",
    "messageId": 2489300,
    "messageInstanceId": 4702524,
    "activityDateTime": "2023-09-14T08:30:50",
    "viewMessageLink": "https://u51739.esclick.me/1RocjPwr0MwONsdn2P",
    "statusData": {}
  },
  {
    "messageName": "test",
    "workflowId": 340484,
    "workflowBlockId": "_527e1f819b41bd379d75ebbe3392b879",
    "sourceEventKey": "9d0c163d-cc3b-4f9e-bb03-2f5d1111ef91",
    "sourceEventTypeKey": "productViewed",
    "workflowInstanceId": "da33697d-52d8-11ee-9d24-7ec2059b5114",
    "iid": "01777190-52d9-11ee-917a-ef6e91bfc7c3",
    "contactId": 889891911,
    "externalCustomerId": "262ac297-6ae1-11ec-a2ec-0050569bdf92",
    "email": "test1@yourdomain.com",
    "mediaType": "email",
    "activityStatus": "DELIVERED",
    "messageId": 2489300,
    "messageInstanceId": 4702524,
    "activityDateTime": "2023-09-14T08:30:51",
    "viewMessageLink": "https://u51739.esclick.me/1RocjPwr0MwONsd3gP",
    "statusData": {}
  },
  {
    "messageName": "test",
    "workflowId": 340484,
    "workflowBlockId": "_be178ec8aacbf249d8bb736e9df9fd0d",
    "sourceEventKey": "9d0c163d-cc3b-4f9e-bb03-2f5d1111ef91",
    "sourceEventTypeKey": "productViewed",
    "workflowInstanceId": "da33697d-52d8-11ee-9d24-7ec2059b5114",
    "hardBounce": false,
    "iid": "01a86ca0-52d9-11ee-85c4-959256ea468c",
    "contactId": 706515632,
    "sms": "380956490955",
    "mediaType": "viber",
    "activityStatus": "UNDELIVERED",
    "messageId": 3213684,
    "messageInstanceId": 4696769,
    "messageTag": "tag2,tag,test",
    "activityDateTime": "2023-09-14T08:30:51",
    "statusDescription": "401: null",
    "statusData": {}
  }
]
```

## Alternative Methods for Tracking Activity Statuses

For comparison/alternative, the API method [Get contacts activity](https://docs.yespo.io/reference/contactactivity-1) is used.

It works by sending GET requests from your side, where you can specify a time interval (up to 3 months) and parameters (such as email, status, etc.).