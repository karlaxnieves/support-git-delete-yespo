---
title: Configuring App Inbox for Mobile Apps
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Configuring App Inbox for Mobile Apps | Yespo Guide
  description: >-
    App Inbox is a communication tool within the CDP that enables automatic and
    manual notifications to mobile app users, requiring configuration steps like
    obtaining an authentication token and managing message statuses.
  robots: index
next:
  description: ''
  pages:
    - type: link
      title: Creating App Inbox Messages
      url: >-
        https://dash.readme.com/project/reteno/v1.0/docs/creating-app-inbox-messages
---
App Inbox is another option to communicate with your customers provided by our CDP. It allows the delivery of automatic and manual notifications to their accounts in the mobile app.

General description of App Inbox, its application, advantages as compared with other communication channels you may find in [this article](http://esputnik.com/en/blog/app-inbox-why-you-will-love-channel).

## Configuring App Inbox for Mobile Apps

To configure App Inbox, you need to send the requests to

- get an authentication token;
- get the number of unread App Inbox messages;
- get the number of pages with messages;
- get the list of all App Inbox messages in the mobile app;
- get the changed status of App Inbox messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b80cadd0e52183931b36cec15c1b067e7c7f8d803daa81e0c97210d4bb58637a-Our-CDP2.webp",
        null,
        "What requests you need to send"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Getting Authentication Token

Send the request from your server to our platform's API to receive the user authentication token (authToken). Authenticate the request using one of the methods specified in the [API](https://docs.yespo.io/reference/getting-started-with-your-api) instructions, for example, using an [API key](https://docs.yespo.io/reference/api-keys).

The request has to contain the known contact fields: email, phone, externalCustomerId (at least one field is required). Those fields are used for searching contacts in our system.

[block:parameters]
{
  "data": {
    "h-0": "Request method",
    "h-1": "POST",
    "0-0": "Request URL",
    "0-1": "`api/v1/auth/contact/token`",
    "1-0": "Request header",
    "1-1": "Content-Type: application/json",
    "2-0": "Request body",
    "2-1": "{  \n\"email\": string,  \n\"phone\": string,  \n\"externalCustomerId\": string  \n}",
    "3-0": "Response",
    "3-1": "{  \n\"token\": string  \n}"
  },
  "cols": 2,
  "rows": 4,
  "align": [
    "left",
    "left"
  ]
}
[/block]


Afterward, `authToken` is used for authentication of all App Inbox requests. Pass it in the header of the `ES-TOKEN request`. The current token becomes invalidated after each request, and the `ES-TOKEN response` header passes the new one used in the following request.

If you receive status code 401 as a response to any App Inbox request, resubmit the request to get the token.

### Getting the Number of Unread App Inbox Messages

The request permits you to get information about unread messages in the client’s mobile app. You can send this request on a regular basis.

[block:parameters]
{
  "data": {
    "h-0": "Request method",
    "h-1": "GET",
    "0-0": "Request URL",
    "0-1": "`appinbox/v1/messages/count`",
    "1-0": "Request header",
    "1-1": "ES-TOKEN: authToken",
    "2-0": "Response header",
    "2-1": "ES-TOKEN: newAuthToken",
    "3-0": "Response",
    "3-1": "{  \n\"count\": int  \n}"
  },
  "cols": 2,
  "rows": 4,
  "align": [
    "left",
    "left"
  ]
}
[/block]


If count > 0, you shall see the indicator of unread messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0e9f2cd27ea81b8be4212a3e88c1e9d13fcde8826de8cdffb6932a3bacb70a2e-Frame_1519app_inbox_1519.webp",
        "",
        "Indicator of unread messages"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Getting the List of All App Inbox Messages

The request permits to get in the response the list of messages in the mobile app, including the following data:

- message ID;
- date of creation;
- header;
- message text content;
- image URL;
- link URL;
- message status (opened or unopened);
- category;
- custom data.

[block:parameters]
{
  "data": {
    "h-0": "Request method",
    "h-1": "GET",
    "0-0": "Request  URL",
    "0-1": "`appinbox/v1/messages?page={pageNumber}&pageSize={pageSize}&status={status}`",
    "1-0": "Request header",
    "1-1": "ES-TOKEN: authToken",
    "2-0": "Response header",
    "2-1": "ES-TOKEN: newAuthToken",
    "3-0": "page",
    "3-1": "minimum value 0",
    "4-0": "pageSize",
    "4-1": "minimum value 1",
    "5-0": "status",
    "5-1": "OPENED/UNOPENED",
    "6-0": "Response",
    "6-1": "{  \n\"list\": [{  \n\"id\" : string, // UUID  \n\"createdDate\" : long, //timestamp in milliseconds  \n\"title\": text,  \n\"content\": text,  \n\"image\": string, // URL  \n\"link\": string, // URL  \n\"newMessage\" : boolean // true for unread message  \n\"status\" : OPENED, UNOPENED // message status  \n},...],  \n\t\"totalPages\": int  \n}"
  },
  "cols": 2,
  "rows": 7,
  "align": [
    "left",
    "left"
  ]
}
[/block]


If `page`, `status` or `pageSize` is not set then return all actual messages.

### Getting the Changed Status of App Inbox Messages

The request transfers the read message event. It is required to pass only the message IDs having **newMessage=true**.

Using this request, you also can change the status of all messages from "unread" to "read".

[block:parameters]
{
  "data": {
    "h-0": "",
    "h-1": "",
    "0-0": "Request method",
    "0-1": "`appinbox/v1/messages/status`",
    "1-0": "Request header",
    "1-1": "ES-TOKEN: authToken",
    "2-0": "Response header",
    "2-1": "ES-TOKEN: newAuthToken",
    "3-0": "Request body",
    "3-1": "{  \n\"status\" : \"OPENED\",  \n\"ids\": [string]  \n}  \n  \n{  \n\"status\": \"OPENED\",  \n\"ids\": null   //or leave empty  \n}",
    "4-0": "Response",
    "4-1": "none"
  },
  "cols": 2,
  "rows": 5,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Creating Segment With Contacts Available for App Inbox 

All contacts that enter Yespo through the [SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo#1-install-sdk-and-connect-communication-channels) have Device IDs. This means you can send them App Inbox messages.

To select all contacts with Device IDs in your database, create a [dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment) and include the _All contacts with device_ condition.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/89c8a10a49aa280330ea1a604d7f2da4e38f0b576d05f18c3af515177c5d9404-en.webp",
        "",
        "All contacts with device"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Creating App Inbox Messages

See [this](https://docs.yespo.io/docs/how-create-app-inbox-messages) article to learn more about creating the messages and campaigns.