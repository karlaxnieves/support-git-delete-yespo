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

- add extra fields for segmentation by contact fields;
- configure seamless synchronization of content component;
- get extra data on contacts in order to build precise segments based on specific conditions.

## 1. Set up a connector.

1. Go to your personal profile → _Settings → Connectors_ → and select _Connect PostgreSQL_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/375796eed3e1ef1a2edb74489f64d439559399523766277ee44b11e5713a1cea-connect-postgresql-01.webp",
        "Select Connect PostgreSQL in Connectors",
        "Select Connect PostgreSQL in Connectors"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Fill in all fields:

- Name. Required.
- Host. Can be the domain name of the remote server or its IP address.
- Port. Entered automatically by default.
- Database. Name of the database on a remote server.
- Username. User's database login (read only user role is enough). Required.
- Password. Required.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be6b823cdfe5a92c2291b14a42aae2d55b3efcc26772abb1450999d79cd10dcb-connecting-postgreSQL-001.webp",
        "Fill in all fields",
        "Fill in all fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You may click _Validate connection_ to test whether authorization data is entered correctly.

> 📘 Note
> 
> When connecting to PostgreSQL, we recommend using a secure SSL connection for secure data transfer.

If you are not using an SSL connection, the system will warn you:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a0dd52071a0eecfc539af774bf40e9aa1f2f09fc18488a7aba7ec207f409c19-ssl-en.webp",
        "Connection is not SSL-secured",
        "Connection is not SSL-secured"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In case of a successful connection, the corresponding service notification will appear in the top right corner. If the connection failed, check the entered data and contact your system administrator if needed.

3. In _Set unique contact field_, select a table column that contains a unique contact key and our system's unique contact key. They should match.

For example, you choose _Email_. After connection, the column of the PostgreSQL table with email addresses will be mapped to the corresponding field in the system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bec8dfd1cb9f382c6e0ca58d84c617bf2a4b02714b4b718e455b4f37432a2165-image7.webp",
        "Example of the table with contact data",
        "Table with contact data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Aside from email addresses, uniqueness of contacts can be determined by a phone number, [external ID](https://docs.yespo.io/docs/external-id-for-creating-and-updating-contacts) or additional contact field.

> 📘 Important
> 
> The created connector can be used to connect to several data sources. All of them will have the same unique contact key so it’s recommended to use one key in all tables. To use a different key, then create another connector to the same database and set a different unique contact field.

4. Click _Save_.

## 2. Configure a data source.

Your external database may contain several tables, and you need to select which one you want to connect to.

1. Go to your personal profile → _Settings → Data sources_, click _New data source_ and select _External data source_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ce73f1eabd3e09903561786e445a3685f146ccc2e74f18898aceedf667c913c-connecting-postgreSQL-002.webp",
        "Select External data source",
        "Select External data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the created connector.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/579f1239bed8940bca3d1c47f2c9647ebbb66d9e7af7255eab345c7753c452a8-connecting-postgreSQL-003.webp",
        "Select the connector you've created",
        "Select the created connector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select dataset and table and enter a source name. Click _Save._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d2b7dbbd0517f7e957859ee27d8cccafa25f46a982b62c65ae969c1904f531d-connecting-postgreSQL-004.webp",
        "Select dataset and table",
        "Select dataset and table"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4\. Now, import contacts to our service and fill the external source with data.

Now you can build segments based on the imported contact fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa5c24511c7a5e8791aaf0772927f6e5a831da6c77341929de3eaedb4c849280-build-a-segment.gif",
        "",
        "Build a segment using the imported data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> Connection to the external database doesn’t presuppose contact import. Segmentation is only available for contacts that exist both in your account and in the external database. Synchronize and update contacts before creating campaigns.

## 3\. Add data to a message.

To insert data, you need to reference it using a [Velocity](https://docs.yespo.io/docs/introduction-to-velocity) parameter $!data.get(‘source\_name’). As an example, we will be using the created source with the name _promo\_codes_.

### Bulk campaign to a segment

For example, you plan a campaign to a contact `kozak@example.com`.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ad158393fbe25d1ecb7241da915386717919a10cb763e0b211769df8333c6e8-image7.webp",
        "Table example",
        "Example of table"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


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

- With parameters (if you know the number of parameters in the array).

```json
- $!data.get('promo_codes').get(0).get('name')

  $!data.get('promo_codes').get(0).get('promo_code')
```

- With a loop (most common method).

```json
- # foreach($pc in $!data.get('promo_codes'))

  $!pc.get('name')

  $!pc.get('promo_code')

  # end
```

### Triggered campaign

First, you need to create a dynamic segment with certain conditions. For example, your segment will include only contacts who have a birthday today.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/327140485d042f0a1fd42726c88d1882fb206719bc38ac2180d69cd539add40a-image12.webp",
        "Segment conditions",
        "Segment conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When the workflow is triggered for contacts that match this condition, the system generates the event. The name of the event is formed from the static part (regularEventType) and the segment ID the campaign is sent to. It can be, for example, regularEventType-170531841.

The event contains contact data, contact ID in our platform (ContactId), email address (EmailAddress), and data from an external table.

The data from each table field is converted into a key and is placed in an array with a numerical name that corresponds to the ID of the data source.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/54852f623b0ad09e110f4ea995d2aa4eba6ad0ec9644b2a56686be075de6c64d-image6.webp",
        "Data source key",
        "Data source key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


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

To deserialize a string into a set of objects, in the workflow > block _Email_ > _JSON_ specify the data source from the event - _${jsonParam}_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d96566b6ba01041956021477ca896fed01230c3adf6f4eed960c01c22d9d6a87-workflow-posrgresql-01.webp",
        "JSON of the block Email",
        "JSON parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Having set up the workflow, configure triggers:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4cecef4eabfd6ac021d6d67f1f75550802f3e5c65d0c4164a06bb5c0253807e-connecting-postgresql-02.webp",
        "Configure trigger",
        "Configure trigger"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


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

- With parameters (if you know the number of parameters in the array).

```json
- $!data.get('1043').get(0).get('name')

  $!data.get('1043').get(0).get('promo_code')
```

<br />

- With a loop (most common method).

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

- broadcasts;
- contactActivities;
- contacts;
- devices;
- events
- messages;
- orderItems;
- orders
- revenue.

<br />

### List of Data Export Parameters

#### Broadcasts

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "createdDate",
    "0-1": "timestamp",
    "0-2": "Day and time of message creation (format: '2021-10-08 11:11:02')",
    "1-0": "groupId",
    "1-1": "int",
    "1-2": "Segment IDs participating in the broadcast",
    "2-0": "id",
    "2-1": "int",
    "2-2": "Broadcast ID",
    "3-0": "mediaType",
    "3-1": "varchar (50)",
    "3-2": "Media type (SMS, Email, WebPush, Viber, MobilePush, AppInbox, Widget)",
    "4-0": "messageId",
    "4-1": "int",
    "4-2": "Message ID",
    "5-0": "name",
    "5-1": "varchar (1000)",
    "5-2": "Broadcast name",
    "6-0": "startedDate",
    "6-1": "timestamp",
    "6-2": "Day and time of broadcast sending (format: '2021-10-08 11:11:02')",
    "7-0": "status",
    "7-1": "varchar (50)",
    "7-2": "Broadcast statuses:  \n•\tIDLE - completed;  \n•\tRUNNING - started;  \n•\tPAUSED - paused (if the mailing was not stopped manually by you, contact support for more details);  \n•\tSCHEDULED - planned;  \n•\tUNCONFIRMED - in queue for moderation;  \n•\tCONSIDERATION - under moderation;  \n•\tBLOCKED - blocked by moderator.",
    "8-0": "updatedDate",
    "8-1": "timestamp",
    "8-2": "Day and time of broadcast updating (format: '2021-10-08 11:11:02')"
  },
  "cols": 3,
  "rows": 9,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


#### ContactActivities

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "activity (activityStatus) \\*",
    "0-1": "varchar (100)",
    "0-2": "Activity status:  \n•\tDELIVERED – the message was delivered.  \n•\tUNDELIVERED – the message was undelivered (statusDescription contains the reason).  \n•\tRECEIVED – the message was opened.  \n•\tUNSUBSCRIBED – a contact unsubscribed from the broadcasting list.  \n•\tCLICKED – a contact clicked links in the message.  \n•\tSPAM – a contact reported spam.  \n•\tSUBSCRIPTION_CHANGED – a contact changed the subscription category.  \n•\tPUSH_SUBSCRIBED — a contact subscribed to push notifications.",
    "1-0": "broadcastId",
    "1-1": "int",
    "1-2": "Broadcast ID",
    "2-0": "campaignType",
    "2-1": "varchar (50)",
    "2-2": "Campaign type:  \n•\tIM — triggered message,  \n•\tGroup — bulk campaign.",
    "3-0": "clickEventLink\t",
    "3-1": "varchar (1000)",
    "3-2": "Contains the link clicked by a contact (when the status is CLICKED)",
    "4-0": "contactId",
    "4-1": "bigint",
    "4-2": "Contact ID in Yespo (Internal)",
    "5-0": "errorCode (statusDescription) \\*",
    "5-1": "varchar (1000)",
    "5-2": "Delivery error SMTP and description",
    "6-0": "eventKey",
    "6-1": "varchar (100)",
    "6-2": "Event key",
    "7-0": "eventTypeKey",
    "7-1": "varchar (100)",
    "7-2": "Event type key",
    "8-0": "externalCustomerId",
    "8-1": "varchar (100)",
    "8-2": "Contact ID in your system (External)",
    "9-0": "iid",
    "9-1": "string",
    "9-2": "Sender name for Email and SMS",
    "10-0": "mediaType",
    "10-1": "varchar (50)",
    "10-2": "Media type (SMS, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App, Telegram)",
    "11-0": "messageInstanceId",
    "11-1": "int",
    "11-2": "Service field",
    "12-0": "messageLanguageCode",
    "12-1": "varchar (50)",
    "12-2": "Message language code",
    "13-0": "messageName",
    "13-1": "varchar (100)",
    "13-2": "Message name in Yespo account",
    "14-0": "messageId",
    "14-1": "int",
    "14-2": "Message ID",
    "15-0": "messageTags",
    "15-1": "varchar (200)",
    "15-2": "Message tags",
    "16-0": "messageURL",
    "16-1": "varchar (1000)",
    "16-2": "Contains the link to the email web-version",
    "17-0": "osName",
    "17-1": "string",
    "17-2": "Device operating system",
    "18-0": "osType",
    "18-1": "string",
    "18-2": "Device type",
    "19-0": "senderName",
    "19-1": "varchar (200)",
    "19-2": "Viber sender name",
    "20-0": "started (activityDateTime) \\*",
    "20-1": "timestamp",
    "20-2": "Day and time of message sending (format: '2021-10-08 11:11:02')",
    "21-0": "utmCampaign\t",
    "21-1": "varchar (400)",
    "21-2": "Campaign UTM",
    "22-0": "workflowId",
    "22-1": "string",
    "22-2": "Workflow ID",
    "23-0": "workflowInstanceId",
    "23-1": "varchar (200)",
    "23-2": "The identifier of a particular workflow launch. Use it to group mailings within the launch of a workflow.",
    "24-0": "workflowBlockId",
    "24-1": "varchar (200)",
    "24-2": "Workflow block ID"
  },
  "cols": 3,
  "rows": 25,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


\*The field will be removed as overdated; use the field indicated in brackets

#### Contacts

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "contactId",
    "0-1": "bigint",
    "0-2": "Contact ID in Yespo (Internal)",
    "1-0": "contactSource",
    "1-1": "varchar (50)",
    "1-2": "Contact source:  \n•\tSITE_AUTOMATED - binding an email to a push subscriber (webPush collection script),  \n•\tI_MESSAGE - sending a single message,  \n•\tCAMPAIGN - workflow (block Create contact or Add to segment),  \n•\tIMPORT - file import or Add contacts method,  \n•\tMANUAL - manually created,  \n•\tSUBSCRIPTION - subscription form (Subscribe a contact API method),  \n•\tAdd contact API method,  \n•\tORDER - order on the site (Add orders API method).",
    "2-0": "createdDate",
    "2-1": "timestamp",
    "2-2": "Contact creation date and time (format: '2021-10-08 11:11:02')",
    "3-0": "email\t",
    "3-1": "varchar (50)",
    "3-2": "Contact email",
    "4-0": "emailDomain",
    "4-1": "varchar (100)",
    "4-2": "Email domain",
    "5-0": "emailStatus",
    "5-1": "varchar (50)",
    "5-2": "Email status",
    "6-0": "externalCustomerId\t",
    "6-1": "varchar (100)",
    "6-2": "Contact ID in your system (External)",
    "7-0": "firstName\t",
    "7-1": "varchar (50)",
    "7-2": "Contact first name",
    "8-0": "languageCode\t",
    "8-1": "varchar (20)",
    "8-2": "Contact language code",
    "9-0": "lastClickedDate\t",
    "9-1": "timestamp",
    "9-2": "Day and time of the last click  (format: '2021-10-08 11:11:02')",
    "10-0": "lastName",
    "10-1": "varchar (50)",
    "10-2": "Contact last name",
    "11-0": "lastReceivedDate\t",
    "11-1": "timestamp",
    "11-2": "Day and time of the last delivery (format: '2021-10-08 11:11:02')",
    "12-0": "lastSentDate\t",
    "12-1": "timestamp",
    "12-2": "Day and time of the last sending (format: '2021-10-08 11:11:02')",
    "13-0": "lastViewedDate",
    "13-1": "timestamp",
    "13-2": "Day and time of the last opening (format: '2021-10-08 11:11:02')",
    "14-0": "sms",
    "14-1": "varchar (50)",
    "14-2": "Phone number",
    "15-0": "totalClicked",
    "15-1": "int",
    "15-2": "Total clicks amount",
    "16-0": "totalReceived",
    "16-1": "int",
    "16-2": "Total received messages amount",
    "17-0": "totalSent",
    "17-1": "int",
    "17-2": "Total sent messages amount",
    "18-0": "totalViewed",
    "18-1": "int",
    "18-2": "Total viewed messages amount"
  },
  "cols": 3,
  "rows": 19,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


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

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "contactId",
    "0-1": "bigint",
    "0-2": "Contact ID in Yespo (Internal)",
    "1-0": "deliveryAddress\t",
    "1-1": "varchar (100)",
    "1-2": "Delivery address",
    "2-0": "deliveryMethod",
    "2-1": "varchar (50)",
    "2-2": "Delivery method",
    "3-0": "discount",
    "3-1": "numeric",
    "3-2": "Discount",
    "4-0": "email",
    "4-1": "varchar (50)",
    "4-2": "Email",
    "5-0": "externalOrderId",
    "5-1": "varchar (100)",
    "5-2": "External order ID",
    "6-0": "firstName\t",
    "6-1": "varchar (50)",
    "6-2": "Contact first name",
    "7-0": "lastName",
    "7-1": "varchar (50)",
    "7-2": "Contact last name",
    "8-0": "orderCreatedDate",
    "8-1": "timestamp",
    "8-2": "Date of order creation in Yespo (format: '2021-10-08 11:11:02')",
    "9-0": "orderDate\t",
    "9-1": "timestamp",
    "9-2": "Order creation date (format: '2021-10-08 11:11:02')",
    "10-0": "orderId\t",
    "10-1": "int",
    "10-2": "Order ID in Yespo (Internal)",
    "11-0": "paymentMethod",
    "11-1": "varchar (50)",
    "11-2": "Payment method",
    "12-0": "Phone",
    "12-1": "varchar (50)",
    "12-2": "Phone number",
    "13-0": "Status",
    "13-1": "varchar (50)",
    "13-2": "Order status:  \n•\tINITIALIZED,  \n•\tIN PROGRESS,  \n•\tDELIVERED,  \n•\tCANCELED.",
    "14-0": "totalCost",
    "14-1": "numeric",
    "14-2": "Total order cost"
  },
  "cols": 3,
  "rows": 15,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


#### Revenue

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "activity (activityStatus)\\*",
    "0-1": "varchar (100)",
    "0-2": "Activity status:  \n•\tDELIVERED – the message was delivered.  \n•\tUNDELIVERED – the message was undelivered (statusDescription contains the reason).  \n•\tRECEIVED – the message was opened.  \n•\tUNSUBSCRIBED – a contact unsubscribed from the broadcasting list.  \n•\tCLICKED – a contact clicked links in the message.  \n•\tSPAM – a contact reported spam.  \n•\tSUBSCRIPTION_CHANGED – a contact changed the subscription category.  \n•\tPUSH_SUBSCRIBED — a contact subscribed to push notifications.",
    "1-0": "campaignType\t",
    "1-1": "varchar (50)",
    "1-2": "Campaign type:  \n•\tIM — triggered message,  \n•\tGroup — bulk campaign.",
    "2-0": "clickEventLink\t",
    "2-1": "varchar (1000)",
    "2-2": "Contains the link clicked by a contact (when the status is CLICKED)",
    "3-0": "contactId",
    "3-1": "bigint",
    "3-2": "Contact ID in Yespo (Internal)",
    "4-0": "currency\t\t",
    "4-1": "varchar (3)",
    "4-2": "Currency",
    "5-0": "externalCustomerId\t",
    "5-1": "varchar (100)",
    "5-2": "Contact ID in your system (External)",
    "6-0": "externalOrderId\t",
    "6-1": "varchar (200)",
    "6-2": "External order ID",
    "7-0": "mediaType\t",
    "7-1": "varchar (50)",
    "7-2": "Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App)",
    "8-0": "messageInstanceId",
    "8-1": "int",
    "8-2": "Service field",
    "9-0": "messageName\t",
    "9-1": "varchar (100)",
    "9-2": "Message name in Yespo account",
    "10-0": "messageTags\t",
    "10-1": "varchar (200)",
    "10-2": "Message tags",
    "11-0": "messageUrl\t",
    "11-1": "varchar (1000)",
    "11-2": "Contains the link to the email web-version",
    "12-0": "orderDate\t\t",
    "12-1": "timestamp",
    "12-2": "Order creation date (format: '2021-10-08 11:11:02')",
    "13-0": "senderName\t",
    "13-1": "varchar (200)",
    "13-2": "Viber sender name",
    "14-0": "started (activityDateTime)\\*",
    "14-1": "timestamp",
    "14-2": "Day and time of message sending (format: '2021-10-08 11:11:02')",
    "15-0": "totalCost",
    "15-1": "numeric",
    "15-2": "Total order cost",
    "16-0": "utmCampaign\t",
    "16-1": "varchar (400)",
    "16-2": "Campaign UTM"
  },
  "cols": 3,
  "rows": 17,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


\*The field will be removed as overdated; use the field indicated in brackets

> 📘 Note
> 
> Existing entries in the Revenue table (for orders placed after 03.08.2024) can be updated along with the upload of new orders. Updating may be necessary, for example, if the total cost of the order has changed.

This information will be transferred to PostgreSQL and will update the data in the tables.

> 📘 Important
> 
> You don’t need to pre-create PostgreSQL tables. They will be generated automatically at the first export, and since that all the incoming data will be updated. All the table names will correspond to the data sets (contact activities, contacts, order items, orders, revenue)

### Setting up PostgreSQL connector for data export

1\. Go to Settings → _Data export_ and click _New data export_. Select one of the created PostgreSQL connectors.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69efb574f3f1722d65ea80c13a7b40c2e64caca0b16ad73d24a865199289188f-6c77dcd-postgresql3.webp",
        "Select connector",
        "Select connector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Select upload interval and check the boxes for the data sets you want to upload. The data set type by default is _public_, you can select another type if you have specified it in your _PostgreSQL settings_.    
   Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/df0aedd16258ad3dffbd7553ce83c936e0d883256353221b893d22cac149b01d-158de0e-PG_export.webp",
        "Edit data",
        "Edit data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The connection will be displayed in the _Data export section_, here you can edit its settings.