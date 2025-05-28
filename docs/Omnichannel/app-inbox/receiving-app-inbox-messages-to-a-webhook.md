---
title: Receiving App Inbox Messages to a Webhook
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Receiving App Inbox Messages to a Webhook | Yespo Guide
  description: >-
    You can receive App-Inbox messages for your contacts directly to your
    webhook by providing a URL and optional basic authentication, with a default
    limit of 1,000 messages
  robots: index
next:
  description: ''
---
Instead of sending API requests to our system to get App-inbox messages for your contacts, you can receive the list of all the available App-Inbox messages to your webhook. 

We can configure for you the maximum number of messages for your contacts. The default number is 1,000.

> 📘 Note
>
> We can send the messages to your webhook only for the contacts having externalCustomerId assigned.

## Webhook Requirements

You have to send us the webhook URL, where you want to receive the messages, and the basic authorization (optional).

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        HTTP method
      </th>

      <th>
        POST
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Authentication (optional)
      </td>

      <td>
        Basic
      </td>
    </tr>

    <tr>
      <td>
        Format
      </td>

      <td>
        \{\
            "url" : string,\
            "auth" : \{\
                "type" : "basic",    // Supported basic type only\
                "username" : string,\
                "password" : string\
            }\
        }
      </td>
    </tr>
  </tbody>
</Table>

### App Inbox Message

The messages you receive have the following format:

```json
{
    "externalCustomerId" : string, 	// Receiver identifier
    "id" : UUID,                   		// Interaction ID. Used to set status
    "createdDate" : long,         	// Timestamp in milliseconds
    "title" : text,
    "content" : text,
    "image" : string,              		// URL
    "link" : string,                	// URL
    "category" : string,            	// Message category
    "customData" : string
}
```

### Response HTTP Status Codes

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Code
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        200 OK
      </td>

      <td>
        Successful request processing.
      </td>
    </tr>

    <tr>
      <td>
        401 Forbidden
      </td>

      <td>
        Authentication failed. The system retries such requests.
      </td>
    </tr>

    <tr>
      <td>
        429 Too Many Requests
      </td>

      <td>
        The message number limit is exceeded. The system retries such requests.
      </td>
    </tr>

    <tr>
      <td>
        400 Bad Request
      </td>

      <td>
        An issue with payload processing. The system does NOT retry such requests.
      </td>
    </tr>

    <tr>
      <td>
        500 Internal Server Error\
        502 Bad Gateway\
        503 Service Unavailable
      </td>

      <td>
        Temporary processing issues. The system retries such requests.
      </td>
    </tr>
  </tbody>
</Table>
