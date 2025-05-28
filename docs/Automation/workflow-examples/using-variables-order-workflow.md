---
title: Using Variables from Order in Workflow
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using Variables from Order in Workflow | Yespo Guide
  description: >-
    How to correctly write event variables in workflows so that the workflow
    works correctly.
  robots: index
next:
  description: ''
---
Let's look at using variables from an order event in a transactional workflow, for example, _Order delivered_. Correctly writing variables is necessary for the workflow to work without errors and for all the required parameters to be inserted into the message content.

## Main Steps for Preparing Transactional Campaigns

Preparing any workflow that sends messages with information about user data, delivery address, order number, etc., includes the following steps:

- transferring of order data via API (you can use [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) or [Generate event](https://docs.yespo.io/reference/registerevent_1) API resources);
- preparing an email with dynamic content;
- setting up a workflow for sending the email.

We will look at transferring orders using the Add orders API resource. You can find out more about its use in [this manual](https://docs.yespo.io/docs/orders-automation).

### Transferring Order Data

The request contains one or more orders with mandatory and optional fields.

Required fields for the _orders_ array:

- ExternalOrderId,
- ExternalCustomerId,
- TotalCost,
- Status,
- Date,
- Email or Phone

Required fields for the items array:

- ExternalItemId,
- Name,
- Quantity,
- Cost,
- Url,
- ImageUrl

Also, several important order statuses display the sales funnel:

- A created order usually has the INITIALIZED status.
- An order in the delivery process is displayed with the IN\_PROGRESS status.
- For paid and delivered orders, the DELIVERED status is used.
- For canceled – CANCELLED.

Such a differentiation is necessary primarily to understand precisely what stage the customer is at, and not send delivery messages to those who canceled or just created the order.

### Creating Events

Every time you pass order data via the API, corresponding [events](https://docs.yespo.io/docs/creating-events) are created in the system, which you can later use as a condition that launches a triggered workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2b34604ef7d073f5ab07f426434afbfa574515182d3addb58fa75119a6cfa135-workflow-variables-001.webp",
        "Launch conditions",
        "Launch conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The names of transactional events consist of the word order and the status added to it, for example, orderDELIVERED. You can see them in the _Triggers → Event history_ section in the Yespo system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8db5b2b2362448fa8fb11cc7eca476a5686974a8e5a5f03675338d972eb985fb-1-3.webp",
        "Event history",
        "Event history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Each event has a unique key. For _order_ events, these are order identifiers, which are passed in the externalOrderId parameter.

> 📘 Note
> 
> The extrenalCustomerId and ContactId parameters are matched when the order is first submitted. Accordingly, in subsequent orders, even if you specify the email of a new contact in the body of the order, but the extrenalCustomerId will belong to a contact that is already in the system, the order will be assigned to the contact with whom the initial matching took place.

For example, order events include the following standard variables:

- ${eventKey} – order unique key, contains the externalOrderId field value.
- ${orderId} – order ID in the Yespo database. The parameter is needed for the workflow’s functioning.
- ${contactId} – contact ID in Yespo.
- ${EmailAddress} – customer’s email address (if provided in the order).
- ${SMS} – customer’s phone number (if provided in the order).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65ce289c009c4b05ceb40be363ba749ba456b97a5983deab0ce97c8c3bb5d217-1-2.webp",
        "Event parameters",
        "Event parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Using Event Parameters in Workflow

Write event parameters in workflows precisely in the form they are transmitted in events. If the standard EmailAddress parameter is passed in an order event, the variable in the email input field in the workflow should also be called EmailAddress. Other formats like email or EmaiL will not work in the workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/96e2b2a86e7cf35add0d1b3a4e2578b428f553a97208ac832e0c3c21ea496795-workflow-details.webp",
        "Email block parameters",
        "Email block parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


For users' convenience, system events (generated by a _subscribe_ request or a regular workflow) have some standard parameters, so such workflow blocks usually work by default, even without manually specifying variables. However, if you change the event for launching the workflow to something other than the standard one, the workflow will not run by default. The Yespo team recommends manually specifying variables in the workflow to avoid errors.