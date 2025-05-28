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

* get an authentication token;
* get the number of unread App Inbox messages;
* get the number of pages with messages;
* get the list of all App Inbox messages in the mobile app;
* get the changed status of App Inbox messages.

<Image align="center" width="80%" src="https://files.readme.io/b80cadd0e52183931b36cec15c1b067e7c7f8d803daa81e0c97210d4bb58637a-Our-CDP2.webp" />

### Getting Authentication Token

Send the request from your server to our platform's API to receive the user authentication token (authToken). Authenticate the request using one of the methods specified in the [API](https://docs.yespo.io/reference/getting-started-with-your-api) instructions, for example, using an [API key](https://docs.yespo.io/reference/api-keys).

The request has to contain the known contact fields: email, phone, externalCustomerId (at least one field is required). Those fields are used for searching contacts in our system.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Request method
      </th>
      <th>
        POST
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Request URL
      </td>
      <td>
        api/v1/auth/contact/token
      </td>
    </tr>
    <tr>
      <td>
        Request header
      </td>
      <td>
        Content-Type: application/json
      </td>
    </tr>
    <tr>
      <td>
        Request body
      </td>
      <td>
        `{"email": string, "phone": string, "externalCustomerId": string}`
      </td>
    </tr>
    <tr>
      <td>
        Response
      </td>
      <td>
        `{"token": string}`
      </td>
    </tr>
  </tbody>
</Table>

Afterward, `authToken` is used for authentication of all App Inbox requests. Pass it in the header of the `ES-TOKEN` request. The current token becomes invalidated after each request, and the `ES-TOKEN` response header passes the new one used in the following request.

If you receive status code 401 as a response to any App Inbox request, resubmit the request to get the token.

### Getting the Number of Unread App Inbox Messages

The request permits you to get information about unread messages in the client’s mobile app. You can send this request on a regular basis.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Request method
      </th>
      <th>
        GET
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Request URL
      </td>
      <td>
        appinbox/v1/messages/count
      </td>
    </tr>
    <tr>
      <td>
        Request header
      </td>
      <td>
        ES-TOKEN: authToken
      </td>
    </tr>
    <tr>
      <td>
        Response header
      </td>
      <td>
        ES-TOKEN: newAuthToken
      </td>
    </tr>
    <tr>
      <td>
        Response
      </td>
      <td>
        `{"count": int}`
      </td>
    </tr>
  </tbody>
</Table>

If `count` > 0, you shall see the indicator of unread messages.

<Image align="center" width="80%" src="https://files.readme.io/0e9f2cd27ea81b8be4212a3e88c1e9d13fcde8826de8cdffb6932a3bacb70a2e-Frame_1519app_inbox_1519.webp" />

### Getting the List of All App Inbox Messages

The request permits to get in the response the list of messages in the mobile app, including the following data:

* message ID;
* date of creation;
* header;
* message text content;
* image URL;
* link URL;
* message status (opened or unopened);
* category;
* custom data.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Request method
      </th>
      <th>
        GET
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Request URL
      </td>
      <td>
        appinbox/v1/messages?page=`{pageNumber}`&pageSize=`{pageSize}`&status=`{status}`
      </td>
    </tr>
    <tr>
      <td>
        Request header
      </td>
      <td>
        ES-TOKEN: authToken
      </td>
    </tr>
    <tr>
      <td>
        Response header
      </td>
      <td>
        ES-TOKEN: newAuthToken
      </td>
    </tr>
    <tr>
      <td>
        page
      </td>
      <td>
        minimum value 0
      </td>
    </tr>
    <tr>
      <td>
        pageSize
      </td>
      <td>
        minimum value 1
      </td>
    </tr>
    <tr>
      <td>
        status
      </td>
      <td>
        OPENED/UNOPENED
      </td>
    </tr>
    <tr>
      <td>
        Response
      </td>
      <td>
        `{"list": [{"id": string, "createdDate": long, "title": text, "content": text, "image": string, "link": string, "newMessage": boolean, "status": OPENED}], "totalPages": int}`
      </td>
    </tr>
  </tbody>
</Table>

If `page`, `status` or `pageSize` is not set then return all actual messages.

### Getting the Changed Status of App Inbox Messages

The request transfers the read message event. It is required to pass only the message IDs having **newMessage=true**.

Using this request, you also can change the status of all messages from "unread" to "read".

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Request method
      </th>
      <th>
        POST
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Request URL
      </td>
      <td>
        appinbox/v1/messages/status
      </td>
    </tr>
    <tr>
      <td>
        Request header
      </td>
      <td>
        ES-TOKEN: authToken
      </td>
    </tr>
    <tr>
      <td>
        Response header
      </td>
      <td>
        ES-TOKEN: newAuthToken
      </td>
    </tr>
    <tr>
      <td>
        Request body
      </td>
      <td>
        `{"status": "OPENED", "ids": [string]}`
        `{"status": "OPENED", "ids": null}`
      </td>
    </tr>
    <tr>
      <td>
        Response
      </td>
      <td>
        none
      </td>
    </tr>
  </tbody>
</Table>

## Creating Segment With Contacts Available for App Inbox 

All contacts that enter Yespo through the [SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo#1-install-sdk-and-connect-communication-channels) have Device IDs. This means you can send them App Inbox messages.

To select all contacts with Device IDs in your database, create a [dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment) and include the *All contacts with device* condition.

<Image align="center" width="80%" src="https://files.readme.io/89c8a10a49aa280330ea1a604d7f2da4e38f0b576d05f18c3af515177c5d9404-en.webp" />

## Creating App Inbox Messages

See [this](https://docs.yespo.io/docs/how-create-app-inbox-messages) article to learn more about creating the messages and campaigns.