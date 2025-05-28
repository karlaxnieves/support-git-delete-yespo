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

- _broadcasts_
- _contactActivities_
- _contacts_
- _devices_
- _events_
- _messages_
- _orderItems_
- _orders_
- _revenue_

This information will update the data in the BigQuery tables once a day after setting up.

> 📘 Note
> 
> You don’t need to pre-create BigQuery tables. They will be generated automatically at the first export, and since then all the incoming data will be updated. All the table names will correspond to the data sets.

## Creating a Data Source for Data Export

1\. Go to _Settings → Connectors_ and click _Add data source_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a25554d8c1135b483ca4073b4b271778bf419c0988a39a18c8ac3487783a24e-image1.webp",
        "Add data source",
        "Add data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Upload [the key file](https://docs.yespo.io/docs/google-bigquery-integration#creating-a-project-key) and check the boxes for the data sets you want to upload. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4c612526d12c3ed179813d33506a037d2413476b1a0aa0bcdd5f858d119fdbf0-image2.webp",
        "Save",
        "Save"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The connection will be displayed in _Connectors → Export to BigQuery_, here you can edit the settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a7d61fc4c98c572a8618354ae3d02c90ec22d6a67c4ee3d08dab3e50919b6e2c-image3.webp",
        "Export to BigQuery",
        "Export to BigQuery"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


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
    "3-1": "string",
    "3-2": "Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget)",
    "4-0": "messageId",
    "4-1": "int",
    "4-2": "Message ID",
    "5-0": "name",
    "5-1": "string",
    "5-2": "Broadcast name",
    "6-0": "startedDate",
    "6-1": "timestamp",
    "6-2": "Day and time of broadcast sending (format: '2021-10-08 11:11:02')",
    "7-0": "status",
    "7-1": "string",
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
    "0-1": "string",
    "0-2": "Activity status:  \n•\tDELIVERED – the message was delivered.  \n•\tUNDELIVERED – the message was undelivered (statusDescription contains the reason).  \n•\tRECEIVED – the message was opened.  \n•\tUNSUBSCRIBED – a contact unsubscribed from the broadcasting list.  \n•\tCLICKED – a contact clicked links in the message.  \n•\tSPAM – a contact reported spam.  \n•\tSUBSCRIPTION_CHANGED – a contact changed the subscription category.  \n•\tPUSH_SUBSCRIBED — a contact subscribed to push notifications.",
    "1-0": "broadcastId",
    "1-1": "int",
    "1-2": "Broadcast ID",
    "2-0": "campaignType",
    "2-1": "string",
    "2-2": "Campaign type:  \n•\tIM — triggered message,  \n•\tGroup — bulk campaign.",
    "3-0": "clickEventLink\t",
    "3-1": "string",
    "3-2": "Contains the link clicked by a contact (when the status is CLICKED)",
    "4-0": "contactId",
    "4-1": "int",
    "4-2": "Contact ID in Reteno (Internal)",
    "5-0": "errorCode (statusDescription) \\*",
    "5-1": "string",
    "5-2": "Delivery error SMTP and description",
    "6-0": "eventKey",
    "6-1": "string",
    "6-2": "Event key",
    "7-0": "eventTypeKey",
    "7-1": "string",
    "7-2": "Event type key",
    "8-0": "eventId",
    "8-1": "string",
    "8-2": "ID of an event that had started a workflow",
    "9-0": "externalCustomerId",
    "9-1": "string",
    "9-2": "Contact ID in your system (External)",
    "10-0": "iid",
    "10-1": "string",
    "10-2": "Sender name for Email and SMS",
    "11-0": "mediaType",
    "11-1": "string",
    "11-2": "Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget, In-App, Telegram)",
    "12-0": "messageInstanceId",
    "12-1": "int",
    "12-2": "Service field",
    "13-0": "messageLanguageCode",
    "13-1": "string",
    "13-2": "Message language code",
    "14-0": "messageName",
    "14-1": "string",
    "14-2": "Message name in Reteno account",
    "15-0": "messageId",
    "15-1": "int",
    "15-2": "Message ID",
    "16-0": "messageTags",
    "16-1": "string",
    "16-2": "Message tags",
    "17-0": "messageURL",
    "17-1": "string",
    "17-2": "Contains the link to the email web-version",
    "18-0": "osName",
    "18-1": "string",
    "18-2": "Device operating system",
    "19-0": "osType",
    "19-1": "string",
    "19-2": "Device type",
    "20-0": "senderName",
    "20-1": "string",
    "20-2": "Viber sender name",
    "21-0": "started (activityDateTime) \\*",
    "21-1": "timestamp",
    "21-2": "Day and time of message sending (format: '2021-10-08 11:11:02')",
    "22-0": "utmCampaign\t",
    "22-1": "string",
    "22-2": "Campaign UTM",
    "23-0": "workflowId",
    "23-1": "string",
    "23-2": "Workflow ID",
    "24-0": "workflowInstanceId",
    "24-1": "string",
    "24-2": "The identifier of a particular workflow launch. Use it to group mailings within the launch of a workflow.",
    "25-0": "workflowBlockId",
    "25-1": "string",
    "25-2": "Workflow block ID"
  },
  "cols": 3,
  "rows": 26,
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
    "0-1": "int",
    "0-2": "Contact ID in Reteno (Internal)",
    "1-0": "contactSource\tstring",
    "1-1": "string",
    "1-2": "Contact source:  \n•\tSITE_AUTOMATED - binding an email to a push subscriber (webPush collection script),  \n•\tI_MESSAGE - sending a single message,  \n•\tCAMPAIGN - workflow (block Create contact or Add to segment),  \n•\tIMPORT - file import or Add contacts method,  \n•\tMANUAL - manually created,  \n•\tSUBSCRIPTION - subscription form (Subscribe a contact API method),  \n•\tAdd contact API method,  \n•\tORDER - order on the site (Add orders API method).",
    "2-0": "createdDate",
    "2-1": "timestamp",
    "2-2": "Contact creation date and time (format: '2021-10-08 11:11:02')",
    "3-0": "email\t",
    "3-1": "string",
    "3-2": "Contact email",
    "4-0": "emailDomain",
    "4-1": "string",
    "4-2": "Email domain",
    "5-0": "emailStatus",
    "5-1": "string",
    "5-2": "Email status",
    "6-0": "externalCustomerId\t",
    "6-1": "string",
    "6-2": "Contact ID in your system (External)",
    "7-0": "firstName\t",
    "7-1": "string",
    "7-2": "Contact first name",
    "8-0": "languageCode\t",
    "8-1": "string",
    "8-2": "Contact language code",
    "9-0": "lastClickedDate\t",
    "9-1": "timestamp",
    "9-2": "Day and time of the last click  (format: '2021-10-08 11:11:02')",
    "10-0": "lastName",
    "10-1": "string",
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
    "14-1": "string",
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

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "contactId",
    "0-1": "int",
    "0-2": "Contact ID in Reteno (Internal)",
    "1-0": "deliveryAddress\t",
    "1-1": "string",
    "1-2": "Delivery address",
    "2-0": "deliveryMethod",
    "2-1": "string",
    "2-2": "Delivery method",
    "3-0": "discount",
    "3-1": "float",
    "3-2": "Discount",
    "4-0": "email",
    "4-1": "string",
    "4-2": "Email",
    "5-0": "externalOrderId",
    "5-1": "string",
    "5-2": "External order ID",
    "6-0": "firstName\t",
    "6-1": "string",
    "6-2": "Contact first name",
    "7-0": "lastName",
    "7-1": "string",
    "7-2": "Contact last name",
    "8-0": "orderCreatedDate",
    "8-1": "timestamp",
    "8-2": "Date of order creation in Reteno (format: '2021-10-08 11:11:02')",
    "9-0": "orderDate\t",
    "9-1": "timestamp",
    "9-2": "Order creation date (format: '2021-10-08 11:11:02')",
    "10-0": "orderId\t",
    "10-1": "int",
    "10-2": "Order ID in Reteno (Internal)",
    "11-0": "paymentMethod",
    "11-1": "string",
    "11-2": "Payment method",
    "12-0": "Phone",
    "12-1": "string",
    "12-2": "Phone number",
    "13-0": "Status",
    "13-1": "string",
    "13-2": "Order status:  \n•\tINITIALIZED,  \n•\tIN PROGRESS,  \n•\tDELIVERED,  \n•\tCANCELED.",
    "14-0": "totalCost",
    "14-1": "float",
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
    "0-1": "string",
    "0-2": "Activity status:  \n•\tDELIVERED – the message was delivered.  \n•\tUNDELIVERED – the message was undelivered (statusDescription contains the reason).  \n•\tRECEIVED – the message was opened.  \n•\tUNSUBSCRIBED – a contact unsubscribed from the broadcasting list.  \n•\tCLICKED – a contact clicked links in the message.  \n•\tSPAM – a contact reported spam.  \n•\tSUBSCRIPTION_CHANGED – a contact changed the subscription category.  \n•\tPUSH_SUBSCRIBED — a contact subscribed to push notifications.",
    "1-0": "campaignType\t",
    "1-1": "string",
    "1-2": "Campaign type:  \n•\tIM — triggered message,  \n•\tGroup — bulk campaign.",
    "2-0": "clickEventLink\t",
    "2-1": "string",
    "2-2": "Contains the link clicked by a contact (when the status is CLICKED)",
    "3-0": "contactId",
    "3-1": "int",
    "3-2": "Contact ID in Reteno (Internal)",
    "4-0": "currency\t\t",
    "4-1": "string",
    "4-2": "Currency",
    "5-0": "externalCustomerId\t",
    "5-1": "string",
    "5-2": "Contact ID in your system (External)",
    "6-0": "externalOrderId\t",
    "6-1": "string",
    "6-2": "External order ID",
    "7-0": "mediaType\t",
    "7-1": "string",
    "7-2": "Media type (Sms, Email, WebPush, Viber, MobilePush, AppInbox, Widget)",
    "8-0": "messageInstanceId",
    "8-1": "int",
    "8-2": "Service field",
    "9-0": "messageName\t",
    "9-1": "string",
    "9-2": "Message name in Reteno account",
    "10-0": "messageTags\t",
    "10-1": "string",
    "10-2": "Message tags",
    "11-0": "messageUrl\t",
    "11-1": "string",
    "11-2": "Contains the link to the email web-version",
    "12-0": "orderDate\t\t",
    "12-1": "timestamp",
    "12-2": "Order creation date (format: '2021-10-08 11:11:02')",
    "13-0": "senderName\t",
    "13-1": "string",
    "13-2": "Viber sender name",
    "14-0": "started (activityDateTime)\\*",
    "14-1": "timestamp",
    "14-2": "Day and time of message sending (format: '2021-10-08 11:11:02')",
    "15-0": "totalCost",
    "15-1": "float",
    "15-2": "Total order cost",
    "16-0": "utmCampaign\t",
    "16-1": "string",
    "16-2": "Campaign UTM",
    "17-0": "eventKey",
    "17-1": "string",
    "17-2": "Event key",
    "18-0": "eventTypeKey",
    "18-1": "string",
    "18-2": "Event type key",
    "19-0": "messageLanguageCode",
    "19-1": "string",
    "19-2": "Message language code",
    "20-0": "orderId",
    "20-1": "int",
    "20-2": "Order ID in Reteno (Internal)",
    "21-0": "workflowId",
    "21-1": "int",
    "21-2": "Workflow ID",
    "22-0": "broadcastId",
    "22-1": "int",
    "22-2": "Broadcast ID"
  },
  "cols": 3,
  "rows": 23,
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

## Use Cases

Here are some key use cases for exporting data from Yespo to BigQuery:

### 1\. Advanced Campaign Performance Analysis

- **Dataset Used:** _broadcasts, contactActivities, messages_
- **Description:** BigQuery enables e-commerce teams to analyze campaign performance in-depth, tracking key metrics such as open and click-through rates. Exporting data on broadcasts, including segmentation criteria, delivery status, and message type, allows marketers to assess which campaigns achieve the best engagement.
- **Use Case Benefit:** By identifying the most effective campaigns, marketers can optimize message content, timing, and audience targeting, enhancing the impact and ROI of future campaigns.

### 2\. Customer Segmentation and Behavioral Analytics

- **Dataset Used:** _contacts, contactActivities, events_
- **Description:** BigQuery can process large volumes of customer activity data, enabling e-commerce brands to spot behavioral patterns such as purchase frequency or preferred interaction channels. This insight allows for deeper segmentation, making it possible to target highly engaged customers more accurately.
- **Use Case Benefit:** Tailored, behavior-driven campaigns lead to increased customer retention and higher lifetime value (LTV) by delivering experiences that resonate with each audience segment.

### 3\. Personalization and Retargeting

- **Dataset Used:** _devices, contacts, contactActivities, events_
- **Description:** By exporting data on user devices, engagement history, and past interactions, e-commerce teams can implement personalized retargeting. For instance, messaging can be tailored to recent activity or device type to enhance relevance and engagement.
- **Use Case Benefit:** Personalizing messages based on user actions and preferences improves user experience, boosts conversions, and builds a more dynamic engagement strategy.

### 4\. Predictive Modeling

- **Dataset Used:** _contacts, orders, revenue, contactActivities_
- **Description:** Historical data on revenue, purchases, and engagement in BigQuery allows for the development of predictive models to forecast customer churn. This enables brands to identify at-risk customers and target them with retention strategies.
- **Use Case Benefit:** Targeted retention campaigns reduce churn and increase LTV, helping brands retain valuable customers and improve long-term revenue.

### 5\. Order and Revenue Analysis for Strategic Insights

- **Dataset Used:** _orders, orderItems, revenue_
- **Description:** By analyzing order and revenue data in BigQuery, e-commerce businesses can track metrics such as average order value and revenue trends. This analysis helps identify upselling and bundling opportunities.
- **Use Case Benefit:** Insights into revenue patterns allow for data-driven decisions on pricing, promotions, and product offerings, maximizing revenue potential.

### 6\. Monitoring and Alerting on Key Metrics

- **Dataset Used:** _broadcasts, contactActivities, revenue_
- **Description:** BigQuery dashboards can monitor key performance indicators (KPIs) such as engagement levels and revenue trends, with the ability to set up alerts for significant changes (e.g., a sudden drop in delivery rates).
- **Use Case Benefit:** Monitoring helps maintain campaign effectiveness by allowing teams to quickly address performance issues, ensuring consistent engagement.

### 7\. Campaign ROI and Budget Allocation Analysis

- **Dataset Used:** _broadcasts, orders, revenue, contactActivities_
- **Description:** Exporting campaign and revenue data into BigQuery allows e-commerce marketers to calculate ROI and assess campaign cost-effectiveness, providing guidance on optimal budget allocation.
- **Use Case Benefit:** By focusing on high-performing campaigns, marketers can optimize spending to maximize marketing effectiveness and returns.

### 8\. Customer Journey Mapping Across Channels

- **Dataset Used:** _contacts, contactActivities, events, orders_
- **Description:** BigQuery’s data processing capabilities enable brands to consolidate user journeys across channels, providing insights into the customer lifecycle from discovery to conversion.
- **Use Case Benefit:** Understanding the customer journey reveals drop-off points and highlights opportunities for improvement, supporting a smoother experience and higher conversion rates.