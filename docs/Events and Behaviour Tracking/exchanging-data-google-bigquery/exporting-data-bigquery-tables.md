---
title: Exporting Data to the BigQuery Tables
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Exporting Data to the BigQuery Tables | Yespo Guide
  description: Learn how to export data to BigQuery for advanced analytics
  robots: index
next:
  description: ''
---
Set up data export to tables to regularly update information about the audience, contacts' activity, and campaign results in BigQuery. Available datasets for export:

* *broadcasts*
* *contactActivities*
* *contacts*
* *devices*
* *events*
* *messages*
* *orderItems*
* *orders*
* *revenue*

This information will update the data in the BigQuery tables once a day after setting up.

> 📘 Note
>
> You don’t need to pre-create BigQuery tables. They will be generated automatically at the first export, and since then all the incoming data will be updated. All the table names will correspond to the data sets.

## Creating a Data Source for Data Export

1\. Go to *Settings → Connectors* and click *Add data source*.

<Image align="center" width="80% " src="https://files.readme.io/1a25554d8c1135b483ca4073b4b271778bf419c0988a39a18c8ac3487783a24e-image1.webp" />

2\. Upload [the key file](https://docs.yespo.io/docs/google-bigquery-integration#creating-a-project-key) and check the boxes for the data sets you want to upload. Click *Save*.

<Image align="center" width="80% " src="https://files.readme.io/4c612526d12c3ed179813d33506a037d2413476b1a0aa0bcdd5f858d119fdbf0-image2.webp" />

The connection will be displayed in *Connectors → Export to BigQuery*, here you can edit the settings.

<Image align="center" width="80% " src="https://files.readme.io/a7d61fc4c98c572a8618354ae3d02c90ec22d6a67c4ee3d08dab3e50919b6e2c-image3.webp" />

<br />

### List of Data Export Parameters

#### Broadcasts

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
        createdDate
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of message creation (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        groupId
      </td>

      <td>
        int
      </td>

      <td>
        Segment IDs participating in the broadcast
      </td>
    </tr>

    <tr>
      <td>
        id
      </td>

      <td>
        int
      </td>

      <td>
        Broadcast ID
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
        Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget)
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
        Message ID
      </td>
    </tr>

    <tr>
      <td>
        name
      </td>

      <td>
        string
      </td>

      <td>
        Broadcast name
      </td>
    </tr>

    <tr>
      <td>
        startedDate
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of broadcast sending (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        status
      </td>

      <td>
        string
      </td>

      <td>
        Broadcast statuses:\
        •	IDLE - completed;\
        •	RUNNING - started;\
        •	PAUSED - paused (if the mailing was not stopped manually by you, contact support for more details);\
        •	SCHEDULED - planned;\
        •	UNCONFIRMED - in queue for moderation;\
        •	CONSIDERATION - under moderation;\
        •	BLOCKED - blocked by moderator.
      </td>
    </tr>

    <tr>
      <td>
        updatedDate
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of broadcast updating (format: '2021-10-08 11:11:02')
      </td>
    </tr>
  </tbody>
</Table>

#### ContactActivities

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
        activity (activityStatus) \*
      </td>

      <td>
        string
      </td>

      <td>
        Activity status:\
        •	DELIVERED – the message was delivered.\
        •	UNDELIVERED – the message was undelivered (statusDescription contains the reason).\
        •	RECEIVED – the message was opened.\
        •	UNSUBSCRIBED – a contact unsubscribed from the broadcasting list.\
        •	CLICKED – a contact clicked links in the message.\
        •	SPAM – a contact reported spam.\
        •	SUBSCRIPTION\_CHANGED – a contact changed the subscription category.\
        •	PUSH\_SUBSCRIBED — a contact subscribed to push notifications.
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
        Broadcast ID
      </td>
    </tr>

    <tr>
      <td>
        campaignType
      </td>

      <td>
        string
      </td>

      <td>
        Campaign type:\
        •	IM — triggered message,\
        •	Group — bulk campaign.
      </td>
    </tr>

    <tr>
      <td>
        clickEventLink&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contains the link clicked by a contact (when the status is CLICKED)
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
        Contact ID in Reteno (Internal)
      </td>
    </tr>

    <tr>
      <td>
        errorCode (statusDescription) \*
      </td>

      <td>
        string
      </td>

      <td>
        Delivery error SMTP and description
      </td>
    </tr>

    <tr>
      <td>
        eventKey
      </td>

      <td>
        string
      </td>

      <td>
        Event key
      </td>
    </tr>

    <tr>
      <td>
        eventTypeKey
      </td>

      <td>
        string
      </td>

      <td>
        Event type key
      </td>
    </tr>

    <tr>
      <td>
        eventId
      </td>

      <td>
        string
      </td>

      <td>
        ID of an event that had started a workflow
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
        Contact ID in your system (External)
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
        Sender name for Email and SMS
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
        Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App, Telegram)
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
        Service field
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
        Message language code
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
        Message name in Reteno account
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
        Message ID
      </td>
    </tr>

    <tr>
      <td>
        messageTags
      </td>

      <td>
        string
      </td>

      <td>
        Message tags
      </td>
    </tr>

    <tr>
      <td>
        messageURL
      </td>

      <td>
        string
      </td>

      <td>
        Contains the link to the email web-version
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
        Device operating system
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
        Device type
      </td>
    </tr>

    <tr>
      <td>
        senderName
      </td>

      <td>
        string
      </td>

      <td>
        Viber sender name
      </td>
    </tr>

    <tr>
      <td>
        started (activityDateTime) \*
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of message sending (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        utmCampaign&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Campaign UTM
      </td>
    </tr>

    <tr>
      <td>
        workflowId
      </td>

      <td>
        string
      </td>

      <td>
        Workflow ID
      </td>
    </tr>

    <tr>
      <td>
        workflowInstanceId
      </td>

      <td>
        string
      </td>

      <td>
        The identifier of a particular workflow launch. Use it to group mailings within the launch of a workflow.
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
        Workflow block ID
      </td>
    </tr>
  </tbody>
</Table>

\*The field will be removed as overdated; use the field indicated in brackets

#### Contacts

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
        contactId
      </td>

      <td>
        int
      </td>

      <td>
        Contact ID in Reteno (Internal)
      </td>
    </tr>

    <tr>
      <td>
        contactSource	string
      </td>

      <td>
        string
      </td>

      <td>
        Contact source:\
        •	SITE\_AUTOMATED - binding an email to a push subscriber (webPush collection script),\
        •	I\_MESSAGE - sending a single message,\
        •	CAMPAIGN - workflow (block Create contact or Add to segment),\
        •	IMPORT - file import or Add contacts method,\
        •	MANUAL - manually created,\
        •	SUBSCRIPTION - subscription form (Subscribe a contact API method),\
        •	Add contact API method,\
        •	ORDER - order on the site (Add orders API method).
      </td>
    </tr>

    <tr>
      <td>
        createdDate
      </td>

      <td>
        timestamp
      </td>

      <td>
        Contact creation date and time (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        email&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contact email
      </td>
    </tr>

    <tr>
      <td>
        emailDomain
      </td>

      <td>
        string
      </td>

      <td>
        Email domain
      </td>
    </tr>

    <tr>
      <td>
        emailStatus
      </td>

      <td>
        string
      </td>

      <td>
        Email status
      </td>
    </tr>

    <tr>
      <td>
        externalCustomerId&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contact ID in your system (External)
      </td>
    </tr>

    <tr>
      <td>
        firstName&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contact first name
      </td>
    </tr>

    <tr>
      <td>
        languageCode&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contact language code
      </td>
    </tr>

    <tr>
      <td>
        lastClickedDate&#x9;
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of the last click  (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        lastName
      </td>

      <td>
        string
      </td>

      <td>
        Contact last name
      </td>
    </tr>

    <tr>
      <td>
        lastReceivedDate&#x9;
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of the last delivery (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        lastSentDate&#x9;
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of the last sending (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        lastViewedDate
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of the last opening (format: '2021-10-08 11:11:02')
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
        Phone number
      </td>
    </tr>

    <tr>
      <td>
        totalClicked
      </td>

      <td>
        int
      </td>

      <td>
        Total clicks amount
      </td>
    </tr>

    <tr>
      <td>
        totalReceived
      </td>

      <td>
        int
      </td>

      <td>
        Total received messages amount
      </td>
    </tr>

    <tr>
      <td>
        totalSent
      </td>

      <td>
        int
      </td>

      <td>
        Total sent messages amount
      </td>
    </tr>

    <tr>
      <td>
        totalViewed
      </td>

      <td>
        int
      </td>

      <td>
        Total viewed messages amount
      </td>
    </tr>
  </tbody>
</Table>

#### Devices

| Parameter          | Type   | Description          |
| :----------------- | :----- | :------------------- |
| appVersion         | string | App version          |
| applicationId      | int    | App ID               |
| category           | string | Category             |
| contactId          | int    | Contact ID           |
| deviceId           | string | Device ID            |
| deviceModel        | string | Device model         |
| externalCustomerId | string | External customer ID |
| languageCode       | string | Language code        |
| osType             | string | OS type              |
| osVersion          | string | OS version           |
| pushToken          | string | Push token           |
| timeZone           | string | Time zone            |

#### Events

| Parameter    | Type      | Description                                                                                            |
| :----------- | :-------- | :----------------------------------------------------------------------------------------------------- |
| contactId    | int       | Contact ID                                                                                             |
| eventId      | int       | Event ID                                                                                               |
| eventTypeKey | string    | Event type                                                                                             |
| keyValue     | string    | Event key                                                                                              |
| occured      | timestamp | Date and time of occurrence (format: '2021-10-08 11:11:02')                                            |
| paramsJson   | json      | 50 first event parameters and values ​​(name/value); up to 300 characters of values ​​are transferred. |

#### Messages

| Parameter      | Type      | Description                                                                   |
| :------------- | :-------- | :---------------------------------------------------------------------------- |
| annoyanceLevel | int       | Message annoyance level                                                       |
| language       | string    | Language of the main version of the message                                   |
| mediaType      | string    | Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App) |
| messageId      | int       | Message ID                                                                    |
| name           | string    | Message name                                                                  |
| replyTo        | string    | Reply-to address                                                              |
| sender         | string    | Sender                                                                        |
| subject        | string    | Subject                                                                       |
| tags           | string    | Tags                                                                          |
| translations   | string    | Language versions of the message                                              |
| updateDate     | timestamp | Day and time of message updating (format: '2021-10-08 11:11:02')              |

#### OrderItems

| Parameter         | Type      | Description                                         |
| :---------------- | :-------- | :-------------------------------------------------- |
| cost	float        | float     | Product price                                       |
| description       | string    | Product description                                 |
| externalProductId | string    | External product ID                                 |
| imageUrl          | string    | Product image link                                  |
| name              | string    | Product name                                        |
| orderDate         | timestamp | Order creation date (format: '2021-10-08 11:11:02') |
| orderId           | int       | Order ID in Reteno (Internal)                       |
| quantity          | int       | Number of products                                  |
| url               | string    | Product URL                                         |

#### Orders

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
        contactId
      </td>

      <td>
        int
      </td>

      <td>
        Contact ID in Reteno (Internal)
      </td>
    </tr>

    <tr>
      <td>
        deliveryAddress&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Delivery address
      </td>
    </tr>

    <tr>
      <td>
        deliveryMethod
      </td>

      <td>
        string
      </td>

      <td>
        Delivery method
      </td>
    </tr>

    <tr>
      <td>
        discount
      </td>

      <td>
        float
      </td>

      <td>
        Discount
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
        Email
      </td>
    </tr>

    <tr>
      <td>
        externalOrderId
      </td>

      <td>
        string
      </td>

      <td>
        External order ID
      </td>
    </tr>

    <tr>
      <td>
        firstName&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contact first name
      </td>
    </tr>

    <tr>
      <td>
        lastName
      </td>

      <td>
        string
      </td>

      <td>
        Contact last name
      </td>
    </tr>

    <tr>
      <td>
        orderCreatedDate
      </td>

      <td>
        timestamp
      </td>

      <td>
        Date of order creation in Reteno (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        orderDate&#x9;
      </td>

      <td>
        timestamp
      </td>

      <td>
        Order creation date (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        orderId&#x9;
      </td>

      <td>
        int
      </td>

      <td>
        Order ID in Reteno (Internal)
      </td>
    </tr>

    <tr>
      <td>
        paymentMethod
      </td>

      <td>
        string
      </td>

      <td>
        Payment method
      </td>
    </tr>

    <tr>
      <td>
        Phone
      </td>

      <td>
        string
      </td>

      <td>
        Phone number
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        string
      </td>

      <td>
        Order status:\
        •	INITIALIZED,\
        •	IN PROGRESS,\
        •	DELIVERED,\
        •	CANCELED.
      </td>
    </tr>

    <tr>
      <td>
        totalCost
      </td>

      <td>
        float
      </td>

      <td>
        Total order cost
      </td>
    </tr>
  </tbody>
</Table>

#### Revenue

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
        activity (activityStatus)\*
      </td>

      <td>
        string
      </td>

      <td>
        Activity status:\
        •	DELIVERED – the message was delivered.\
        •	UNDELIVERED – the message was undelivered (statusDescription contains the reason).\
        •	RECEIVED – the message was opened.\
        •	UNSUBSCRIBED – a contact unsubscribed from the broadcasting list.\
        •	CLICKED – a contact clicked links in the message.\
        •	SPAM – a contact reported spam.\
        •	SUBSCRIPTION\_CHANGED – a contact changed the subscription category.\
        •	PUSH\_SUBSCRIBED — a contact subscribed to push notifications.
      </td>
    </tr>

    <tr>
      <td>
        campaignType&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Campaign type:\
        •	IM — triggered message,\
        •	Group — bulk campaign.
      </td>
    </tr>

    <tr>
      <td>
        clickEventLink&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contains the link clicked by a contact (when the status is CLICKED)
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
        Contact ID in Reteno (Internal)
      </td>
    </tr>

    <tr>
      <td>
        currency	&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Currency
      </td>
    </tr>

    <tr>
      <td>
        externalCustomerId&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contact ID in your system (External)
      </td>
    </tr>

    <tr>
      <td>
        externalOrderId&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        External order ID
      </td>
    </tr>

    <tr>
      <td>
        mediaType&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget)
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
        Service field
      </td>
    </tr>

    <tr>
      <td>
        messageName&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Message name in Reteno account
      </td>
    </tr>

    <tr>
      <td>
        messageTags&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Message tags
      </td>
    </tr>

    <tr>
      <td>
        messageUrl&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Contains the link to the email web-version
      </td>
    </tr>

    <tr>
      <td>
        orderDate	&#x9;
      </td>

      <td>
        timestamp
      </td>

      <td>
        Order creation date (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        senderName&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Viber sender name
      </td>
    </tr>

    <tr>
      <td>
        started (activityDateTime)\*
      </td>

      <td>
        timestamp
      </td>

      <td>
        Day and time of message sending (format: '2021-10-08 11:11:02')
      </td>
    </tr>

    <tr>
      <td>
        totalCost
      </td>

      <td>
        float
      </td>

      <td>
        Total order cost
      </td>
    </tr>

    <tr>
      <td>
        utmCampaign&#x9;
      </td>

      <td>
        string
      </td>

      <td>
        Campaign UTM
      </td>
    </tr>

    <tr>
      <td>
        eventKey
      </td>

      <td>
        string
      </td>

      <td>
        Event key
      </td>
    </tr>

    <tr>
      <td>
        eventTypeKey
      </td>

      <td>
        string
      </td>

      <td>
        Event type key
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
        Message language code
      </td>
    </tr>

    <tr>
      <td>
        orderId
      </td>

      <td>
        int
      </td>

      <td>
        Order ID in Reteno (Internal)
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
        Workflow ID
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
        Broadcast ID
      </td>
    </tr>
  </tbody>
</Table>

\*The field will be removed as overdated; use the field indicated in brackets

> 📘 Note
>
> Existing entries in the Revenue table (for orders placed after 03.08.2024) can be updated along with the upload of new orders. Updating may be necessary, for example, if the total cost of the order has changed.

## Use Cases

Here are some key use cases for exporting data from Yespo to BigQuery:

### 1\. Advanced Campaign Performance Analysis

* **Dataset Used:** *broadcasts, contactActivities, messages*
* **Description:** BigQuery enables e-commerce teams to analyze campaign performance in-depth, tracking key metrics such as open and click-through rates. Exporting data on broadcasts, including segmentation criteria, delivery status, and message type, allows marketers to assess which campaigns achieve the best engagement.
* **Use Case Benefit:** By identifying the most effective campaigns, marketers can optimize message content, timing, and audience targeting, enhancing the impact and ROI of future campaigns.

### 2\. Customer Segmentation and Behavioral Analytics

* **Dataset Used:** *contacts, contactActivities, events*
* **Description:** BigQuery can process large volumes of customer activity data, enabling e-commerce brands to spot behavioral patterns such as purchase frequency or preferred interaction channels. This insight allows for deeper segmentation, making it possible to target highly engaged customers more accurately.
* **Use Case Benefit:** Tailored, behavior-driven campaigns lead to increased customer retention and higher lifetime value (LTV) by delivering experiences that resonate with each audience segment.

### 3\. Personalization and Retargeting

* **Dataset Used:** *devices, contacts, contactActivities, events*
* **Description:** By exporting data on user devices, engagement history, and past interactions, e-commerce teams can implement personalized retargeting. For instance, messaging can be tailored to recent activity or device type to enhance relevance and engagement.
* **Use Case Benefit:** Personalizing messages based on user actions and preferences improves user experience, boosts conversions, and builds a more dynamic engagement strategy.

### 4\. Predictive Modeling

* **Dataset Used:** *contacts, orders, revenue, contactActivities*
* **Description:** Historical data on revenue, purchases, and engagement in BigQuery allows for the development of predictive models to forecast customer churn. This enables brands to identify at-risk customers and target them with retention strategies.
* **Use Case Benefit:** Targeted retention campaigns reduce churn and increase LTV, helping brands retain valuable customers and improve long-term revenue.

### 5\. Order and Revenue Analysis for Strategic Insights

* **Dataset Used:** *orders, orderItems, revenue*
* **Description:** By analyzing order and revenue data in BigQuery, e-commerce businesses can track metrics such as average order value and revenue trends. This analysis helps identify upselling and bundling opportunities.
* **Use Case Benefit:** Insights into revenue patterns allow for data-driven decisions on pricing, promotions, and product offerings, maximizing revenue potential.

### 6\. Monitoring and Alerting on Key Metrics

* **Dataset Used:** *broadcasts, contactActivities, revenue*
* **Description:** BigQuery dashboards can monitor key performance indicators (KPIs) such as engagement levels and revenue trends, with the ability to set up alerts for significant changes (e.g., a sudden drop in delivery rates).
* **Use Case Benefit:** Monitoring helps maintain campaign effectiveness by allowing teams to quickly address performance issues, ensuring consistent engagement.

### 7\. Campaign ROI and Budget Allocation Analysis

* **Dataset Used:** *broadcasts, orders, revenue, contactActivities*
* **Description:** Exporting campaign and revenue data into BigQuery allows e-commerce marketers to calculate ROI and assess campaign cost-effectiveness, providing guidance on optimal budget allocation.
* **Use Case Benefit:** By focusing on high-performing campaigns, marketers can optimize spending to maximize marketing effectiveness and returns.

### 8\. Customer Journey Mapping Across Channels

* **Dataset Used:** *contacts, contactActivities, events, orders*
* **Description:** BigQuery’s data processing capabilities enable brands to consolidate user journeys across channels, providing insights into the customer lifecycle from discovery to conversion.
* **Use Case Benefit:** Understanding the customer journey reveals drop-off points and highlights opportunities for improvement, supporting a smoother experience and higher conversion rates.
