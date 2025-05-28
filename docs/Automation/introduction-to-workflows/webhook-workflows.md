---
title: Webhook Workflows
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Webhook Workflows | Yespo Guide
  description: >-
    Explore Webhook Workflows in Yespo to integrate external systems. Learn how
    to work with event parameters and contact profiles to enhance your marketing
    automation and data synchronization.
  robots: index
next:
  description: ''
---
Webhook workflows allow working with parameters from [events](https://docs.yespo.io/docs/events-and-behaviour-tracking) and from the [contact’s profile](https://docs.yespo.io/docs/user-profile) in Yespo.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bfae31f68e4337ea594493785db985ce14f7a9281653e01ffa645d2af6db8f0-webhooks-in-workflows-301.webp",
        "",
        "Webhooks in Workflows"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


This request uploads and sends the contact’s data from Yespo to other systems and contrariwise collects data into Yespo from external systems. Using this as a part of a workflow, you can:

1. Address your own resource, which will process the request and return data for [personalization](https://docs.yespo.io/docs/personalization-and-dynamic-variables) (for example, a personal promo code or a token for authorization) in the message.
2. Send data from an event or from the contact’s card (for example, order id, [additional field](https://docs.yespo.io/docs/how-add-additional-contact-fields) “contact’s id in messenger” or “Birthday”) to an external resource.

> 📘 Note
> 
> Only the contact’s data (fields + additional fields) and the parameters from an event that triggered a workflow with a webhook can be sent through a webhook. In most cases, data transfer in webhooks is configured in **JSON **format, but **XML** and **text** formats are also available.

## Creating a Webhook in a Workflow

1. Go to _Automation → Workflows_ and click the _New workflow_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/96aa05808243a5e794db8712dea288a3ce7dae418457737199fbe1366eeabb30-webhooks-in-workflows-002.webp",
        "",
        "Creating a new workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Open the _Other_ tab on the left panel, and select _Webhook_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8cea7b6d5b833fb9a2c8939902af094c9be67a7ee2d94670c7118a652ed7939b-webhooks-in-workflows-303.webp",
        "",
        "Other tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click the _Create webhook_ button on the _Settings_ panel on the right side.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86598eea6a8ee5f4ff7b35e46067d45d2572acc78d285361de35a0e8fd0b03c2-webhooks-in-workflows-304.webp",
        "",
        "Create webhook"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. The Create webhook window opens. Select the `GET `or `POST` request type from the drop-down menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e4d9a19f7c0a18a0aaeffefc513426ebb6e9ead7703d0db31ddb9b4a3c625d6-webhooks-in-workflows-005.webp",
        "",
        "Select the GET or POST request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Working with GET Request

Use this request type when you want to request data on an external resource using the link to use the data in a workflow and insert it inside the workflow. The data is transmitted to an URL as “name-value” pairs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a60711c0dbf377e73906defa2d4238fbc857670ad2d3b4b7687575d54654a43-webhooks-in-workflows-006.webp",
        "",
        "GET request type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In order to configure the webhook:

1. Enter the webhook name using any symbols (required field) and description (optional field).
2. Enter the resource’s URL through secured `HTTPS` protocol (if you enter `HTTP` the system does not save the link). Type in variables you want to return after the interrogation symbol. In this example, we transmit the email parameter’s value from an event triggering the workflow and address the EMAIL field related to the contact’s card on the resource to which we sent the `GET` request.
3. If your resource reads parameters from headers, enable _Pass parameters in headers_ slide button and enter corresponding variables and values you want to address.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/481fde795ffcfe48b037b9278662065646d0f685a9bdef964f8807730c6f257c-en-webhook-workf-001.webp",
        "",
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Below are examples of parameter names and their values that can be used:

| Parameter | Value                 |
| :-------- | :-------------------- |
| phone     | `$phone`              |
| email     | `$email`              |
| name      | `$name`               |
| city      | `$city`               |
| contactID | `$contact_ID`         |
| param     | `$workflowInstanceId` |

> 📘 Note
> 
> For `GET` requests, the `$workflowInstanceId` value can be passed in the webhook parameters — it is a unique identifier for the workflow instance. It allows identifying which specific events belong to the instance and, based on that, calculating statistics and conversions.

> ❗️ Important
> 
> For` $workflowInstanceId`, the character case matters, while for contact fields, it does not.

4. Enable _Authentication_ slide button and select authentication connector. If you need to configure a new one, click the _New connector_ button to open the _Create connector_ window.
5. In _Create connector_ window enter the following details:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/80bdb7697a61a8d1bb74da50e168f05d27a72a72c7fc26538f11a708b7cd7bf0-webhooks-in-workflows-007.webp",
        "",
        "Creating connector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Connector name.
- Authentication type from the drop-down list: Basic, Bearer token, API key.
- Enter login and password/token/key.

Click the _Done_ button to apply the new connector in the webhook automatically.

### GET-request Testing

1. Click the _Send test_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be685f66ebbd81d077aa63ef37109d3b125fe4e9af11e6db38a9089de0c7d35c-webhooks-in-workflows-008.webp",
        "",
        "Click the Send test button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select a contact from the list or find it through the search and click _Next_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8902f3c12a721eec7eda8bc1cbf7930db498841c9f0e2135d80f358884f7d225-webhooks-in-workflows-009.webp",
        "",
        "Select a contact from the list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To find contacts in a segment, select _Preview contacts from the selected segment_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3ef7b88aab6e0a6d7fc9b7e0db9e778947383b6b9f840dbc6619f48e5c16dc1-webhooks-in-workflows-010.webp",
        "",
        "Preview contacts from the selected segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Send request_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bb1db05e5457221edcdc417b1327f4cd85f46cc3982c75eecb04950401fee0c-webhooks-in-workflows-011.webp",
        "",
        "Send request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. In the testing window, you get the response:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f9ac8814ac792b19bf3306ac27ed413a0a3af0fce3ea1ce00b9b58d7c60ddf31-webhooks-in-workflows-012.webp",
        "",
        "Sending GET request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _Back_ arrow in the top left corner of the dialog window, and click the _Done_ button.

Now the new webhook is available for selection in your workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a883d048f37b767152f3c0b47e7239b3a94790edf74afe4b4892b6c0b8c5b882-webhooks-in-workflows-014.webp",
        "",
        "Created webhook"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Now you can show the received data in a message using the expression in [Velocity language](https://docs.yespo.io/docs/introduction-to-velocity). Go to _Messages_ → _Messages_ → _New Email_ or choose your template.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99caccbf5a41f92bee1e4e68ea90de20d9541802cd679ad6b0c3f463075a459b-webhooks-in-workflows-030.webp",
        "",
        "New Email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Insert the expression with the value of the received variable to output dynamic data into any text area.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d29a115431aadf90151287e5694d8d98c75ea312b40910f9dddf55c1a654f91d-webhooks-in-workflows-015.webp",
        "",
        "Message variable"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Example: `$!mathTool.toInteger($data.contacts_get_by_email.get(0).id)`,

where `contacts_get_by_email `is the name of your webhook (here it plays the role of a data source),

`get(0).id `is a call to a variable in the source pointing to the required parameter. In this case that is contact id.

When testing, the contact ID is inserted into the message that has been found by the email from an event using the webhook.

## Working with POST Requests

Let’s see the example of when it is necessary to send the data about the contact’s city to get a promo code for him/her from an [external source](https://docs.yespo.io/docs/external-data-sources).

Follow the steps below to configure a webhook with the `POST` request:

1. In the webhook block settings, click the _Create webhook_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a92de745666a355e780dc0a3ddc19bd34299a3a68c78d39ecb601ed4d7df83c0-webhooks-in-workflows-016.webp",
        "",
        "Create webhook"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the _Webhook configuration_ window, enter the webhook name and select the `POST` request type. Enter the URL of a resource using the secure `HTTPS `protocol. In this link, you can use variables calling event parameters or contact fields. In the example, we call `TOWN `– the standard contact field in Yespo.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9db8518c4bcb90ef11e99eaaf889d76bca4149365f0129d0ee5d26cffcfaa243-webhooks-in-workflows-017.webp",
        "",
        "POST Request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. If your application reads parameters from headers, enable the _Pass parameters in headers_ slide button. Enter corresponding variables and their values.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d8547a4892a100dcbfe471f36459bd893968e490387a5ea3f18874de4bc41ba-webhooks-in-workflows-018.webp",
        "",
        "Pass parameters in headers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> For `POST` requests, the `$workflowInstanceId `value can be passed in the webhook parameters — it is a unique identifier for the workflow instance. It allows identifying which specific events belong to the instance and, based on that, calculating statistics and conversions.

> ❗️ Important
> 
> For` $workflowInstanceId`, the character case matters, while for contact fields, it does not.

4. Enable the _Authentication_ slide button to configure authentication parameters. Select from existing connectors or create a new one.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/da77fb80d0645d37c2a9b24524916895b36aecf171d805ebf20fd992f50f5c82-webhooks-in-workflows-019.webp",
        "",
        "Configure authentication parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you need to configure a new one, click the _New connector_ button to open the _Create connector_ window.  
In _Create connector_ window:

- Enter the Connector name.
- Select _Authentication type_ from the dropdown list: _Basic, Bearer token, API key_.
- Enter login and password/token/key.

Click the _Done_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1fd6c1eb5a31f004de6dcc73f47de37899f2341e981752619ec07ae72a92db5-webhooks-in-workflows-020.webp",
        "",
        "Create connector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the body of the `POST` request, you can send a random amount of data. For that, enable the corresponding slide button, select the format of the data to be inserted and insert it below. Available formats: JSON, XML, text.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c0f03b62c529e0d76820d6598249a721306be1e9dcabdad3845a85fb37f0a198-en-webhook-workf-002.webp",
        "",
        "Available formats: JSON, XML, text"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To access event parameters, use Apache Velocity, for example: `"param": "$data.get('param')"`.

> 📘 Note
> 
> The value of `$workflowInstanceId` can be passed in the request body.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/842445a5f715bf90286cfcd1b2c9979637709b51ab3f36ce84356d8a64e3630c-en-webhook-workf-003.webp",
        "",
        "$workflowInstanceId in the request body"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Displaying the value of `$workflowInstanceId` in the event parameters:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba1a81967605b1dd691053468b3d572223b665fd4d1db07619a2adbdd7d78644-en-webhook-workf-004.webp",
        "",
        "$workflowInstanceId in the event parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### POST-request Testing

1. Click the _Send test_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f2839a959071996b239478a587c7966c849d08cafbd918c8023e932abd6e77e-webhooks-in-workflows-022.webp",
        "",
        "POST request type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. The system suggests where to take the data for testing – from the contact’s card or from an event. If the webhook URL is configured to address a parameter from an event, then during testing the system suggests choosing an event from the list of those received by the system at any time, or to enter the event’s body manually.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f7dc24e3718b5050fe0f0f3571a33ebd40d2116ed8976da4a4bffdc14c8beb52-webhooks-in-workflows-023.webp",
        "",
        "POST request parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Since in our example we indicate addressing to the contact field, then it is necessary to select a contact from the base in the Yespo account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/261c34db0d4ac76548ee8152a0f7b64ceb03e250e05a037bbc23cb7818784d14-webhooks-in-workflows-024.webp",
        "",
        "POST request dynamic data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can choose another contact (**1**) or view the selected one (**2**).

Upon pressing the _Next_ and _Send request_ buttons you receive the response with _Headers_ and _Body_:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/636b8d7a4cce0796d4f6a23030d10a6bd7444e64f8cc6157bb5d00471e8fcd43-webhooks-in-workflows-025.webp",
        "",
        "Sending POST request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To show the promo code in the message, enter the following expression into the text area:

`$data.get('WH5').get('promocode')`, where

- `WH5` is the source name (webhook name).
- `promocode` is the name of the variable containing the promo code value.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b070002a1a58f5cb4eec162c4a5309a283eb280f6104b160529416fc42e3b444-webhooks-in-workflows-026.webp",
        "",
        "Promo code variable in the message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The result of a promo code inserted in the email:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/77a9ac702fe9130280debc11e9ecadf604daf96cc24454160c96a1726d8ee6c3-webhooks-in-workflows-027.webp",
        "",
        "Promo code inserted in the email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Advanced Parameters

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90d4f19a3c8ceba3838e5b2464e58b21cc147fed4628a63937804571474a9252-webhooks-in-workflows-305.webp",
        "",
        "Advanced Parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The block contains advanced parameters, and the cases for filling them out are detailed in a separate [article](https://docs.yespo.io/docs/advanced-workflow-block-parameters).

## Webhook Management

Press _Manage Webhook_ in the webhook block settings. The window containing the list of webhooks opens. There you can:

- create a new webhook
- edit existing webhooks
- test webhooks
- delete webhooks
- view the list of deleted webhooks

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0cf333d881c7ad71966c2a30beeaab783af47b40cf7b346d3f0d0e5fd0015fc1-webhooks-in-workflows-028.webp",
        "",
        "Webhook management"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the start history of the workflow with a webhook, you will see the details of the request:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c2b19d05613d3c8513224b986bc38359974cdb5597480eb4d6a2eeb6b4eabc2e-webhooks-in-workflows-029.webp",
        "",
        "Details of the request"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]