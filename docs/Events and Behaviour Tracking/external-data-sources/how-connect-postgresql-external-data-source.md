---
title: Connecting PostgreSQL
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Connecting PostgreSQL | Yespo Guide
  description: >-
    The document provides a detailed guide on integrating PostgreSQL as an
    external data source to manage and utilize customer data for marketing
    tasks, such as personalizing messages and building segments.
  robots: index
next:
  description: ''
---
Some companies use several platforms to collect and manage customer data. Thus, sometimes you need to add to messages certain content based on customer data tracked or stored at third-party platforms, such as an external CRM, mobile application, database, etc. For example, you want to add to an email [personalized product recommendations](https://docs.yespo.io/docs/designing-recommendations-email) based on offline sales or orders made via calls and need access to this data.

To access data from third-party sources and use it for content substitution, use a [preprocessor](https://docs.yespo.io/docs/what-preprocessor) or connect to external data sources, such as [Google Sheets](https://docs.yespo.io/docs/how-import-external-data-google-sheets), [BigQuery](https://docs.yespo.io/docs/google-bigquery-integration) or PostgreSQL.

Connection to PostgreSQL would be the most optimal option if you need to

* add extra fields for segmentation by contact fields;
* configure seamless synchronization of content component;
* get extra data on contacts in order to build precise segments based on specific conditions.

## 1. Set up a connector.

1. Go to your personal profile → *Settings → Connectors* → and select *Connect PostgreSQL*.

<Image align="center" width="80% " src="https://files.readme.io/375796eed3e1ef1a2edb74489f64d439559399523766277ee44b11e5713a1cea-connect-postgresql-01.webp" />

2. Fill in all fields:

* Name. Required.
* Host. Can be the domain name of the remote server or its IP address.
* Port. Entered automatically by default.
* Database. Name of the database on a remote server.
* Username. User's database login (read only user role is enough). Required.
* Password. Required.

<Image align="center" width="80% " src="https://files.readme.io/be6b823cdfe5a92c2291b14a42aae2d55b3efcc26772abb1450999d79cd10dcb-connecting-postgreSQL-001.webp" />

You may click *Validate connection* to test whether authorization data is entered correctly.

> 📘 Note
>
> When connecting to PostgreSQL, we recommend using a secure SSL connection for secure data transfer.

If you are not using an SSL connection, the system will warn you:

<Image align="center" width="80% " src="https://files.readme.io/5a0dd52071a0eecfc539af774bf40e9aa1f2f09fc18488a7aba7ec207f409c19-ssl-en.webp" />

In case of a successful connection, the corresponding service notification will appear in the top right corner. If the connection failed, check the entered data and contact your system administrator if needed.

3. In *Set unique contact field*, select a table column that contains a unique contact key and our system's unique contact key. They should match.

For example, you choose *Email*. After connection, the column of the PostgreSQL table with email addresses will be mapped to the corresponding field in the system.

<Image align="center" width="80% " src="https://files.readme.io/bec8dfd1cb9f382c6e0ca58d84c617bf2a4b02714b4b718e455b4f37432a2165-image7.webp" />

Aside from email addresses, uniqueness of contacts can be determined by a phone number, [external ID](https://docs.yespo.io/docs/external-id-for-creating-and-updating-contacts) or additional contact field.

> 📘 Important
>
> The created connector can be used to connect to several data sources. All of them will have the same unique contact key so it’s recommended to use one key in all tables. To use a different key, then create another connector to the same database and set a different unique contact field.

4. Click *Save*.

## 2. Configure a data source.

Your external database may contain several tables, and you need to select which one you want to connect to.

1. Go to your personal profile → *Settings → Data sources*, click *New data source* and select *External data source*.

<Image align="center" width="80% " src="https://files.readme.io/7ce73f1eabd3e09903561786e445a3685f146ccc2e74f18898aceedf667c913c-connecting-postgreSQL-002.webp" />

2. Select the created connector.

<Image align="center" width="80% " src="https://files.readme.io/579f1239bed8940bca3d1c47f2c9647ebbb66d9e7af7255eab345c7753c452a8-connecting-postgreSQL-003.webp" />

3. Select dataset and table and enter a source name. Click *Save.*

<Image align="center" width="80% " src="https://files.readme.io/1d2b7dbbd0517f7e957859ee27d8cccafa25f46a982b62c65ae969c1904f531d-connecting-postgreSQL-004.webp" />

4\. Now, import contacts to our service and fill the external source with data.

Now you can build segments based on the imported contact fields.

<Image align="center" width="80% " src="https://files.readme.io/fa5c24511c7a5e8791aaf0772927f6e5a831da6c77341929de3eaedb4c849280-build-a-segment.gif" />

> 📘 Important
>
> Connection to the external database doesn’t presuppose contact import. Segmentation is only available for contacts that exist both in your account and in the external database. Synchronize and update contacts before creating campaigns.

## 3\. Add data to a message.

To insert data, you need to reference it using a [Velocity](https://docs.yespo.io/docs/introduction-to-velocity) parameter $!data.get(‘source\_name’). As an example, we will be using the created source with the name *promo\_codes*.

### Bulk campaign to a segment

For example, you plan a campaign to a contact `kozak@example.com`.

<Image align="center" width="80% " src="https://files.readme.io/6ad158393fbe25d1ecb7241da915386717919a10cb763e0b211769df8333c6e8-image7.webp" />

A set of data will be extracted from the table and inserted into an object:

```json
{
  "data": {
    "promo_codes": [
      {
        "id": "2",
        "email": "kozak@example.com",
        "name": "Dina Kozak",
        "birthday": "2020-09-02T00:00:00Z",
        "promo_code": "AAAA-BBBB-DDDD"
      }
    ]
  }
}
```

Fields of the array promo\_codes can be referenced in two ways:

* With parameters (if you know the number of parameters in the array).

```json
- $!data.get('promo_codes').get(0).get('name')

  $!data.get('promo_codes').get(0).get('promo_code')
```

* With a loop (most common method).

```json
- # foreach($pc in $!data.get('promo_codes'))

  $!pc.get('name')

  $!pc.get('promo_code')

  # end
```

### Triggered campaign

First, you need to create a dynamic segment with certain conditions. For example, your segment will include only contacts who have a birthday today.

<Image align="center" width="80% " src="https://files.readme.io/327140485d042f0a1fd42726c88d1882fb206719bc38ac2180d69cd539add40a-image12.webp" />

When the workflow is triggered for contacts that match this condition, the system generates the event. The name of the event is formed from the static part (regularEventType) and the segment ID the campaign is sent to. It can be, for example, regularEventType-170531841.

The event contains contact data, contact ID in our platform (ContactId), email address (EmailAddress), and data from an external table.

The data from each table field is converted into a key and is placed in an array with a numerical name that corresponds to the ID of the data source.

<Image align="center" width="80% " src="https://files.readme.io/54852f623b0ad09e110f4ea995d2aa4eba6ad0ec9644b2a56686be075de6c64d-image6.webp" />

In turn, this array is serialized and placed as a string in the field jsonParam. The body of the event may look as follows:

```json
{
  "params": [
    {
      "name": "ContactId",
      "value": "623927159"
    },
    {
      "name": "jsonParam",
      "value": "{\"1043\":[{\"id\":,\"email\":\"kozak@example.com\",\"name\":\"Dina Kozak\",\"birthday\":\"2020-09-02T00:00:00Z\",\"promo_code\":\"AAAA-BBBB-DDDD\"}]}"
    },
    {
      "name": "EmailAddress",
      "value": "kozak@example.com"
    }
  ]
}
```

To deserialize a string into a set of objects, in the workflow > block *Email* > *JSON* specify the data source from the event - *$\{jsonParam}*.

<Image align="center" width="80% " src="https://files.readme.io/d96566b6ba01041956021477ca896fed01230c3adf6f4eed960c01c22d9d6a87-workflow-posrgresql-01.webp" />

Having set up the workflow, configure triggers:

<Image align="center" width="80% " src="https://files.readme.io/c4cecef4eabfd6ac021d6d67f1f75550802f3e5c65d0c4164a06bb5c0253807e-connecting-postgresql-02.webp" />

The same approach as for a bulk campaign is used to extract data from the event, with little difference in the name of the array. The following object will be in the email:

```json
{
  "data": {
    "1043": [
      {
        "id": "2",
        "email": "kozak@example.com",
        "name": "Dina Kozak",
        "birthday": "2020-09-02T00:00:00Z",
        "promo_code": "AAAA-BBBB-DDDD"
      }
    ]
  }
}
```

The fields of the array 1043 can be referenced in two ways:

* With parameters (if you know the number of parameters in the array).

```json
- $!data.get('1043').get(0).get('name')

  $!data.get('1043').get(0).get('promo_code')
```

<br />

* With a loop (most common method).

```json
- # foreach($pc in $!data.get('1043'))

  $!pc.get('name')

  $!pc.get('promo_code')

  # end
```

Connect PostgreSQL as an external data source to fulfill a wide range of marketing tasks, for example, substitute promo codes in triggered campaigns or build complex segments based on data collected on different platforms.

## Step 4. Set up Data Export

To regularly update information about the audience, orders and campaign results in PostgreSQL, set up data export from the Yespo to tables. For example, you can export responses to an NPS survey, purchase history, date of the last click in a message, etc.

Available datasets for export:

* broadcasts;
* contactActivities;
* contacts;
* devices;
* events
* messages;
* orderItems;
* orders
* revenue.

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
        varchar (50)
      </td>

      <td>
        Media type (SMS, Email, WebPush, Viber, MobilePush, AppInbox, Widget)
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
        varchar (1000)
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
        varchar (50)
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
        varchar (100)
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
        varchar (50)
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
        varchar (1000)
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
        bigint
      </td>

      <td>
        Contact ID in Yespo (Internal)
      </td>
    </tr>

    <tr>
      <td>
        errorCode (statusDescription) \*
      </td>

      <td>
        varchar (1000)
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
        varchar (100)
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
        varchar (100)
      </td>

      <td>
        Event type key
      </td>
    </tr>

    <tr>
      <td>
        externalCustomerId
      </td>

      <td>
        varchar (100)
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
        varchar (50)
      </td>

      <td>
        Media type (SMS, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App, Telegram)
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
        varchar (50)
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
        varchar (100)
      </td>

      <td>
        Message name in Yespo account
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
        varchar (200)
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
        varchar (1000)
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
        varchar (200)
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
        varchar (400)
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
        varchar (200)
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
        varchar (200)
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
        bigint
      </td>

      <td>
        Contact ID in Yespo (Internal)
      </td>
    </tr>

    <tr>
      <td>
        contactSource
      </td>

      <td>
        varchar (50)
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
        varchar (50)
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
        varchar (100)
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
        varchar (50)
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
        varchar (100)
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
        varchar (50)
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
        varchar (20)
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
        varchar (50)
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
        varchar (50)
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

| Parameter          | Type          | Description          |
| :----------------- | :------------ | :------------------- |
| appVersion         | varchar (50)  | App version          |
| applicationId      | int           | App ID               |
| category           | varchar (50)  | Category             |
| contactId          | bigint        | Contact ID           |
| deviceId           | varchar (250) | Device ID            |
| deviceModel        | varchar (100) | Device model         |
| externalCustomerId | varchar (100) | External customer ID |
| languageCode       | varchar (20)  | Language code        |
| osType             | varchar (50)  | OS type              |
| osVersion          | varchar (50)  | OS version           |
| pushToken          | varchar (max) | Push token           |
| timeZone           | varchar (100) | Time zone            |

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

| Parameter      | Type           | Description                                                                   |
| :------------- | :------------- | :---------------------------------------------------------------------------- |
| annoyanceLevel | int            | Message annoyance level                                                       |
| language       | varchar (50)   | Language of the main version of the message                                   |
| mediaType      | varchar (50)   | Media type (SMS, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App) |
| messageId      | int            | Message ID                                                                    |
| name           | varchar (200)  | Message name                                                                  |
| replyTo        | varchar (200)  | Reply-to address                                                              |
| sender         | varchar (200)  | Sender                                                                        |
| subject        | varchar (1000) | Subject                                                                       |
| tags           | varchar (200)  | Tags                                                                          |
| translations   | varchar (200)  | Language versions of the message                                              |
| updateDate     | timestamp      | Day and time of message updating (format: '2021-10-08 11:11:02')              |

#### OrderItems

| Parameter         | Type          | Description                                         |
| :---------------- | :------------ | :-------------------------------------------------- |
| cost	float        | numeric       | Product price                                       |
| description       | varchar (300) | Product description                                 |
| externalProductId | varchar (100) | External product ID                                 |
| imageUrl          | varchar (200) | Product image link                                  |
| name              | varchar (100) | Product name                                        |
| orderDate         | timestamp     | Order creation date (format: '2021-10-08 11:11:02') |
| orderId           | int           | Order ID in Yespo (Internal)                        |
| quantity          | int           | Number of products                                  |
| url               | varchar (200) | Product URL                                         |

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
        bigint
      </td>

      <td>
        Contact ID in Yespo (Internal)
      </td>
    </tr>

    <tr>
      <td>
        deliveryAddress&#x9;
      </td>

      <td>
        varchar (100)
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
        varchar (50)
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
        numeric
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
        varchar (50)
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
        varchar (100)
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
        varchar (50)
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
        varchar (50)
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
        Date of order creation in Yespo (format: '2021-10-08 11:11:02')
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
        Order ID in Yespo (Internal)
      </td>
    </tr>

    <tr>
      <td>
        paymentMethod
      </td>

      <td>
        varchar (50)
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
        varchar (50)
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
        varchar (50)
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
        numeric
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
        varchar (100)
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
        varchar (50)
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
        varchar (1000)
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
        bigint
      </td>

      <td>
        Contact ID in Yespo (Internal)
      </td>
    </tr>

    <tr>
      <td>
        currency	&#x9;
      </td>

      <td>
        varchar (3)
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
        varchar (100)
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
        varchar (200)
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
        varchar (50)
      </td>

      <td>
        Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App)
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
        varchar (100)
      </td>

      <td>
        Message name in Yespo account
      </td>
    </tr>

    <tr>
      <td>
        messageTags&#x9;
      </td>

      <td>
        varchar (200)
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
        varchar (1000)
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
        varchar (200)
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
        numeric
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
        varchar (400)
      </td>

      <td>
        Campaign UTM
      </td>
    </tr>
  </tbody>
</Table>

\*The field will be removed as overdated; use the field indicated in brackets

> 📘 Note
>
> Existing entries in the Revenue table (for orders placed after 03.08.2024) can be updated along with the upload of new orders. Updating may be necessary, for example, if the total cost of the order has changed.

This information will be transferred to PostgreSQL and will update the data in the tables.

> 📘 Important
>
> You don’t need to pre-create PostgreSQL tables. They will be generated automatically at the first export, and since that all the incoming data will be updated. All the table names will correspond to the data sets (contact activities, contacts, order items, orders, revenue)

### Setting up PostgreSQL connector for data export

1\. Go to Settings → *Data export* and click *New data export*. Select one of the created PostgreSQL connectors.

<Image align="center" width="80% " src="https://files.readme.io/69efb574f3f1722d65ea80c13a7b40c2e64caca0b16ad73d24a865199289188f-6c77dcd-postgresql3.webp" />

2\. Select upload interval and check the boxes for the data sets you want to upload. The data set type by default is *public*, you can select another type if you have specified it in your *PostgreSQL settings*.  \
   Click *Save*.

<Image align="center" width="80% " src="https://files.readme.io/df0aedd16258ad3dffbd7553ce83c936e0d883256353221b893d22cac149b01d-158de0e-PG_export.webp" />

The connection will be displayed in the *Data export section*, here you can edit its settings.
