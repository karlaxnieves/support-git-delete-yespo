---
title: Promo Code Added via API
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promo Code Added via API | Yespo Guide
  description: >-
    The document outlines how to use API methods to add promo codes to trigger
    messages, detailing the steps for generating events to launch workflows and
    sending prepared messages , with examples of JSON request formats and
    variable substitution in messages.
  robots: index
next:
  description: ''
---
Let's see how to add promo codes to trigger messages using API methods:

- [Generate event](https://docs.yespo.io/reference/registerevent_1) (via workflow),
- [Send prepared message](https://docs.yespo.io/reference/sendextendedpreparedmessage-1) (without workflow).

## Generate event method

The Generate event method allows you to send any custom events that can launch workflows.  
To substitute a promo code transmitted via API into a trigger message, do the following:

1. Set up the transfer of the necessary parameters in the event.
2. Add a variable to the message.
3. Create a workflow.

### 1. Setting event parameters

The event must contain a promo code and contact identifier for sending the message (e.g., an email address for sending an email or a phone number for SMS).

Event parameters:

```json
{
  "params": [
    {
      "name": "EmailAddress",
      "value": "mail@example.com"
    },
    {
      "name": "code",
      "value": "ABC-123"
    }
  ]
}
```

, where code is the variable's name used in the message, and ABC-123 is the promotional code the contact will receive.

### 2. Substituting variable in the message

Insert the variable's name containing the promo code into the message in the $!data.get('code') format. Instead of a variable, the contact will see the promo code passed in the event.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d619053fd1fcbfa324dc2302ea2ddbf768645e073b32a21df0e4975a8e9e05ac-image1.webp",
        null,
        "Substituting variable in the message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 3. Creating the workflow

In the message block in the workflow, specify the event parameter that contains the contact identifier for sending the message (in our example, this is an email address; for other channels, use the appropriate IDs). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d52abfb3d87d6fe3df8adbb6c746429eee04460fc86b2469b991de33dfd621aa-promo-code-added-via-api-01.webp",
        null,
        "Creating the workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Read more about launching a workflow on an event [in the instructions](https://docs.yespo.io/docs/creating-events).

## Send Prepared Message Method

The _Send prepared message_ method allows you to send campaigns to one or more contacts. 

You can send a unique promo code to each contact.

Request format:

```json
{
    "recipients": [{
        "locator": "mail@example.com",
        "jsonParam": "{\"code\":\"ABC-123\"}"
    }],
    "email": true
}
```

, where the `recipients` array contains elements with `jsonParam`. It can be used to send any data to a message, including a promo code. The data for the message must be in JSON format converted to a string.

Use message ID instead of {id} in `https://esputnik.com/api/v1/message/{id}/smartsend` request.

In the message, use a variable in the `$!data.get('code')` format.