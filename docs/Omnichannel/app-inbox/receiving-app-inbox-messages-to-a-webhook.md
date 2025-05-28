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

[block:parameters]
{
  "data": {
    "h-0": "HTTP method",
    "h-1": "POST",
    "0-0": "Authentication (optional)",
    "0-1": "Basic",
    "1-0": "Format",
    "1-1": "{  \n    \"url\" : string,  \n    \"auth\" : {  \n        \"type\" : \"basic\",    // Supported basic type only  \n        \"username\" : string,  \n        \"password\" : string  \n    }  \n}"
  },
  "cols": 2,
  "rows": 2,
  "align": [
    "left",
    "left"
  ]
}
[/block]


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

[block:parameters]
{
  "data": {
    "h-0": "Code",
    "h-1": "Description",
    "0-0": "200 OK",
    "0-1": "Successful request processing.",
    "1-0": "401 Forbidden",
    "1-1": "Authentication failed. The system retries such requests.",
    "2-0": "429 Too Many Requests",
    "2-1": "The message number limit is exceeded. The system retries such requests.",
    "3-0": "400 Bad Request",
    "3-1": "An issue with payload processing. The system does NOT retry such requests.",
    "4-0": "500 Internal Server Error  \n502 Bad Gateway  \n503 Service Unavailable",
    "4-1": "Temporary processing issues. The system retries such requests."
  },
  "cols": 2,
  "rows": 5,
  "align": [
    "left",
    "left"
  ]
}
[/block]