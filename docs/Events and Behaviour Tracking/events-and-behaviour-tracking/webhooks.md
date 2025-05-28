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

* **Delivered** — the message was delivered to the contact.
* **Undelivered** — the message could not be delivered.
* **Read** — the contact opened the message.
* **Unsubscribed** — the contact unsubscribed from the campaign.
* **Clicked** — the contact clicked on a link in the message.
* **Spam** — the message was marked as spam.
* **Subscription changed** — the contact changed their subscription category.

> 📘 Note
>
> Before setting up webhooks, you need to configure an URL on your server where you want to receive messages — POST requests in JSON format — and process the data accordingly.

## Creating Data Export

Open the *Data export* tab in your account settings, click the *New data export* button, and select *Webhook*.

<Image align="center" width="80% " src="https://files.readme.io/330b56e0ac0f8113eff88899e975e5a425ed9c5454a318a2b9aad78e9926c770-webhooks-for-tracking-activity-01.webp" />

### Connection

Add a *Webhook name* and specify the Webhook URL you previously set up on your server.

<Image align="center" width="80% " src="https://files.readme.io/1d680c93d5192ba2f421acbb91380a29ca03b28edba8cebd4181e12785094c35-webhooks-for-tracking-activity-02.webp" />

### Autentification (optional)

If authentication is enabled on your server, enter the login and password that your server requires to accept requests. Enable the *Authentication* toggle and fill in the corresponding fields.

<Image align="center" width="80% " src="https://files.readme.io/1c3711183b07820f4735cd9eee2fc89380131a56b452102ae1ccbfcb83bde41b-webhooks-for-tracking-activity-03.webp" />

### Export Activity Statuses

By default, all activity statuses are selected for tracking. You can modify this list by deselecting the checkboxes following to the statuses you don't want to track.

<Image align="center" width="80% " src="https://files.readme.io/243be2350bac68013dbb01353f32259ab104a40b91f458b8346fd8a54df6e4f7-webhooks-for-tracking-activity-04.webp" />

After setting up the data export via webhook, click the *Save* button.

<Image align="center" width="80% " src="https://files.readme.io/958eb6117c147420d016a81ab881e14c248bee52d3fdc6103e3fd678d20feebc-webhooks-for-tracking-activity-05.webp" />

The webhook will be active, and data will be sent in real-time to the specified URL.

<Image align="center" width="80% " src="https://files.readme.io/a6db876bb825336ba09c3c8714c55b2a9dfdd40c74362316f97632d4bd4fffc6-webhooks-for-tracking-activity-06.webp" />

## Settings Verification

The system will check the URL's availability using the GET request. If errors occur, your server may block our request for various reasons. You can determine the exact cause based on the server error code on your side.

If the check is successful, the setup is complete.

After that, perform any action in your Yespo account — for example, send yourself an email. The POST request in JSON format with information about the latest activity will be sent to the specified URL.

For example, if a contact receives an email, opens it, and clicks a link, the system will sequentially send three requests with the statuses: `DELIVERED`, `READ`, and `CLICKED`.

If the webhook URL does not return the HTTP 200 response code, the POST request attempt is repeated with incremented intervals (1 minute, 2 minutes, 4 minutes, 8 minutes, and up to 1 request per hour). The following requests are postponed until the first one is successfully delivered, and then delivered in their sequence.

## Webhook Deactivation

To deactivate the webhook, click the three-dot icon, select *Deactivate webhook*, and confirm the action.

<Image align="center" width="80% " src="https://files.readme.io/32eb6343be50cd9b27f46f618c6e5aef3b96f717107703b3c51191101646b362-animation.gif" />

Deactivation suspends the sending of requests, but the webhook remains saved in the system and can be reactivated later.

## Data Export Editing

To change the settings, click on the webhook name, edit the data, and save the settings.

<Image align="center" width="80% " src="https://files.readme.io/f39d22d98d9ceeaca518988a5a566c8e5215075e197b06b0aa40f61b0c15f9ed-webhooks-for-tracking-activity-08.gif" />

## List of Possible Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        activityDateTime
      </td>

      <td>
        string
      </td>

      <td>
        Activity date and time.
      </td>
    </tr>

    <tr>
      <td>
        activityStatus
      </td>

      <td>
        string
      </td>

      <td>
        Activity status:\
        `SENT`– the message is sent (for Mobile Push only)\
        `DELIVERED` – the message was delivered.\
        `UNDELIVERED` – the message was undelivered (statusDescription contains the reason).\
        `READ` – the message was read.\
        `UNSUBSCRIBED` – a contact unsubscribed from the broadcasting list.\
        `CLICKED` – a contact clicked links in the message.\
        `SPAM` – a contact reported spam.\
        `SUBSCRIPTION_CHANGED` – a contact changed the subscription category.
      </td>
    </tr>

    <tr>
      <td>
        broadcastId
      </td>

      <td>
        int
      </td>

      <td>
        Broadcast ID.
      </td>
    </tr>

    <tr>
      <td>
        clickEventLink
      </td>

      <td>
        string
      </td>

      <td>
        Contains the link clicked by a contact (when the status is `CLICKED`).
      </td>
    </tr>

    <tr>
      <td>
        contactId
      </td>

      <td>
        int
      </td>

      <td>
        Contact ID.
      </td>
    </tr>

    <tr>
      <td>
        email
      </td>

      <td>
        string
      </td>

      <td>
        Contact Email.
      </td>
    </tr>

    <tr>
      <td>
        externalCustomerId
      </td>

      <td>
        string
      </td>

      <td>
        A unique customer ID in the client’s system.
      </td>
    </tr>

    <tr>
      <td>
        from
      </td>

      <td>
        string
      </td>

      <td>
        Sender name (in Email, SMS, and Viber messages).
      </td>
    </tr>

    <tr>
      <td>
        hardBounce
      </td>

      <td>
        bool
      </td>

      <td>
        This field is returned only in case when the status is `UNDELIVERED`. The parameter informs that the contact is in the black list.  

        * false\_ – not in the black list at the moment of message delivery.  
        * true\_ – in the black list at the moment of message delivery.
      </td>
    </tr>

    <tr>
      <td>
        iid
      </td>

      <td>
        string
      </td>

      <td>
        Service Parameter.
      </td>
    </tr>

    <tr>
      <td>
        mediaType
      </td>

      <td>
        string
      </td>

      <td>
        Media type  (SMS, Email, Web Push, Viber, Mobile Push, AppInbox, Widget, In-App, Telegram).
      </td>
    </tr>

    <tr>
      <td>
        messageId
      </td>

      <td>
        int
      </td>

      <td>
        Message ID.
      </td>
    </tr>

    <tr>
      <td>
        messageInstanceId
      </td>

      <td>
        int
      </td>

      <td>
        Message instance ID.
      </td>
    </tr>

    <tr>
      <td>
        messageLanguageCode
      </td>

      <td>
        string
      </td>

      <td>
        Identifier of the message language.
      </td>
    </tr>

    <tr>
      <td>
        messageName
      </td>

      <td>
        string
      </td>

      <td>
        Message name (empty for test emails).
      </td>
    </tr>

    <tr>
      <td>
        messageTag
      </td>

      <td>
        string
      </td>

      <td>
        Message tag.
      </td>
    </tr>

    <tr>
      <td>
        mobilepush
      </td>

      <td>
        string
      </td>

      <td>
        Mobile app subscriber token.
      </td>
    </tr>

    <tr>
      <td>
        osName
      </td>

      <td>
        string
      </td>

      <td>
        Device operating system.
      </td>
    </tr>

    <tr>
      <td>
        osType
      </td>

      <td>
        string
      </td>

      <td>
        Device type.
      </td>
    </tr>

    <tr>
      <td>
        sms
      </td>

      <td>
        string
      </td>

      <td>
        Contact phone number.
      </td>
    </tr>

    <tr>
      <td>
        sourceEventId
      </td>

      <td>
        int
      </td>

      <td>
        Source event ID.
      </td>
    </tr>

    <tr>
      <td>
        sourceEventKey
      </td>

      <td>
        string
      </td>

      <td>
        Source event key.
      </td>
    </tr>

    <tr>
      <td>
        sourceEventTypeKey
      </td>

      <td>
        string
      </td>

      <td>
        Source event type key.
      </td>
    </tr>

    <tr>
      <td>
        statusData
      </td>

      <td>

      </td>

      <td>
        Data array.
      </td>
    </tr>

    <tr>
      <td>
        statusDescription
      </td>

      <td>
        string
      </td>

      <td>
        This field is returned only in the event when the status is `UNDELIVERED`. It contains the reason why the message has been undelivered. This may be a recipient server response, a system response saying that message delivery was not possible, and other similar reasons.
      </td>
    </tr>

    <tr>
      <td>
        subscription
      </td>

      <td>

      </td>

      <td>
        Data array.
      </td>
    </tr>

    <tr>
      <td>
        subscriptions
      </td>

      <td>
        array of strings
      </td>

      <td>
        Subscription category keys.
      </td>
    </tr>

    <tr>
      <td>
        viber
      </td>

      <td>
        string
      </td>

      <td>
        Contact phone number.
      </td>
    </tr>

    <tr>
      <td>
        viewMessageLink
      </td>

      <td>
        string
      </td>

      <td>
        Contains the link to the message web version.
      </td>
    </tr>

    <tr>
      <td>
        webpush
      </td>

      <td>
        string
      </td>

      <td>
        Web push subscriber token.
      </td>
    </tr>

    <tr>
      <td>
        workflowBlockId
      </td>

      <td>
        string
      </td>

      <td>
        Workflow block ID.
      </td>
    </tr>

    <tr>
      <td>
        workflowId
      </td>

      <td>
        int
      </td>

      <td>
        Workflow ID.
      </td>
    </tr>

    <tr>
      <td>
        workflowInstanceId
      </td>

      <td>
        uuid
      </td>

      <td>
        The identifier of a particular workflow launch. Use it to group mailings within the launch of a workflow.
      </td>
    </tr>
  </tbody>
</Table>

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
