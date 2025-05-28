---
title: Double Opt-In
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Subscription Form Configuration | Yespo Guide
  description: >-
    How to set up the website form and start collecting email addresses for your
    marketing campaigns.
  robots: index
next:
  description: ''
---
Double Opt-In (DOI) is a subscription confirmation. It is an official requirement by many current customer privacy policies (GDPR). After filling in the subscription form, the user receives a confirmation email. By clicking the link in it, they confirm their email address and agree to receive promotional content from you.

You have three options for collecting contacts via the subscription form:

1. Create [your own widget](https://docs.yespo.io/docs/setting-up-widgets-for-your-site) in the Reteno constructor.
2. Use [integration with Wix forms](https://docs.yespo.io/docs/wix-forms-integration).
3. Integrate a third-party form via the [API](https://docs.yespo.io/reference/subscribecontact-1).

For the first two options, setting up double opt-in is the same (follow the links to see instructions).

Let's look at how to set up double opt-in if you integrate a third-party form via the API.

## Setting Up a Subscription Form

You can integrate subscription form via API method [Subscribe contact](https://docs.yespo.io/reference/subscribecontact-1). When a contact fills out the form, the following events are sent to your account:

- _**subscribeFromApi**_ (when a contact fills out a form for the first time);
- _**subscribeUpdateFromApi**_ (when filling again).

After setting up data transferring, create an email and two [workflows](https://docs.yespo.io/docs/workflow-management). The first workflow sends subscription confirmation email, the second makes a contact active.

## Setting Up Confirmation Email

Create an email that the subscriber will receive after filling out the form.

1. Go to _Messages → Messages → Email_. Click the _New Email_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/152562bd02d97ed5226e24d98165dcc2cc085f35fb53937cfb49a8d631d3298c-setting-up-double-opt-in-201.webp",
        "Creating a new email",
        "Creating a new email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Choose the _Welcome_ email from _Basic_ templates.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52993462156307e48f99a9cda3643f8027a49a4d06e5816ff349f8bc36b93651-setting-up-double-opt-in-002.webp",
        "Template selection",
        "Template selection"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Email confirmation block with default text and button looks like this:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9365dca0ba43c9b61666c82400a15aa90139c12fa307d01789a36aeb080ac676-setting-up-double-opt-in-003.webp",
        "Email with default text and button",
        "Email with default text and button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Design the email in your brand style and enter the required text.
4. Link the [event](https://docs.yespo.io/docs/creating-events) to the button or to the link in the email to launch the required workflow.

Select a block with a button in the email. In the left panel, in the corresponding field, select the pre-prepared event _Confirmed subscription_:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/266a82d2a3a836da0c93a55b7c66659eec580f2419bb503a3a3fb77767847d35-setting-up-double-opt-in-004.webp",
        "Select the pre-prepared event",
        "Select the pre-prepared event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the left settings panel, you can specify a link to the subscription confirmation page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a62be1cd03818a7a8038d5b4808ae16bdafab645e40151259a1046c72a38f9ea-setting-up-double-opt-in-005.webp",
        "Adding link",
        "Adding link"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Setting Up the Workflows

To send the confirmation email and change the contact status to active, you need to create two workflows.

### Workflow for Sending Confirmation Email

Filling out the form can launch 2 types of events.

1. _**subscribeFromApi**_ — creating a new contact.
2. _**subscribeUpdateFromApi**_ — Contact update (re-filling the form).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d5686f5de2645038af3042d0b0816e27dca8c6c4bda5770a8ed5f5c1e2a14d3-setting-up-double-opt-in-0006.webp",
        "Event types",
        "Event types"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To create a workflow:

1. Go to _Automation → Workflows_ and click _New workflow_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58b6e042d3980484e969982de93bb525c9d47b26b5a6427422453fa54cb6a26d-setting-up-double-opt-in-007.webp",
        "Creating a workflow",
        "Creating a workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the workflow name and add the _Start_, _Task_ and _End_ blocks.
3. In the _Task block_ parameters, set the following parameters:

- _Task name_ – Send obligatory (transactional) email.
- _Message_ – Select the required email: Confirmation email.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/169b234a69a47a04ede6b85fb9572e645f012223f23106a85792c67dcb3fb23f-setting-up-double-opt-in-008a.webp",
        "Task block parameters",
        "Task block parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Save and exit_.

### Workflow to Confirm a Contact

This workflow launches after clicking the button in the confirmation email and makes a contact available for further campaigns.

To create the workflow:

1. Go to _Automation_ → _Workflows_ and click _New workflow_.
2. Enter the workflow name and add the _Start_, _Task_ and _End_ blocks.
3. In the _Task_ block parameters, set the _Confirm contact_ task name.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ea9be6058177f12bffa6f0dc68fa126894864726621e42295b02f55b39776c27-setting-up-double-opt-in-009a.webp",
        "Confirm contact task",
        "Confirm contact task"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Save and exit_.

#### Welcome Emails Chain After Confirm Contact Block

To send a welcome series, you need to supplement your _Confirm contact_ workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a02642e5cb994b9320abf4ef068899c55252d038bef0b7360b05c07db7d2531-setting-up-double-opt-in-012a.webp",
        "Welcome Email",
        "Welcome Email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Launching Workflow Conditions

1. Go to _Start/stop_ _configuration_ of created workflows.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3a9b3e88dce73f3e589672a2a254ca68b01bf283a734f31adc5324a49153005c-setting-up-double-opt-in-202.webp",
        "Trigger configuration",
        "Trigger configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the following events:

- _subscribeFromApi_: Filled form workflow
- _Confirm contact_: Confirm contact workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/061faf72468c969ece11b5f155fc15703ba800c2d6fddb5127a2221d884dcfad-setting-up-double-opt-in-011.webp",
        "Start configuration panel",
        "Start configuration panel"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[Learn more about creating events >](https://docs.yespo.io/docs/creating-events#creating-an-event-type)

3. Click _Apply_.
4. Activate workflows.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42733037e346c099e57639904e781122973fc96d064fe89d38606f2a290e02e4-setting-up-double-opt-in-203.webp",
        "Activate workflows",
        "Activate workflows"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If needed, set up processing unique events(1 hour by default). You can opt that the contacts who fill in the subscription form several times a day still receive only one confirmation email. In case of re-subscribe, another event - _subscribeUpdateFromApi_ - will be sent. The confirmation email won't be sent, and contact data will be updated.

> 📘 Important
> 
> The segment for contacts who have confirmed subscription is created in the system by default, but if you transfer data via the API, you can specify the name of the segment in the request.
> 
> If the subscribe request specifies a list of segments to which the contact should be added after subscribing, and then the workflow checks for membership in one of these segments, use a timer of at least 4 minutes between these actions. This will ensure the correct workflow operation and consistent execution of all requests in the system.

## Follow-Up Welcome Series

You can add a welcome email or a series of welcome emails to your contact confirmation workflow. They will be sent after the contact confirms the subscription and gets active in the system. You can vary the number of welcome emails depending on your needs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0f50f3bed24f9cac348836e277e127637b71ca85c600788ab8c8d51e3aa213d-setting-up-double-opt-in-013.webp",
        "Welcome Series",
        "Welcome Series"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> A contact becomes available (active) for your campaigns only after they confirm their subscription in the confirmation email. You cannot send bulk campaigns to unconfirmed contacts.

After all the settings, run a test: fill in the form on the website and check if your email address gets to the segment Subscribers in the system. This segment is the default, but you can specify the segment name in the request if you send contact data via API.

If the subscribe request specifies a list of segments to which the contact should be added after subscribing, and then the workflow checks for membership in one of these segments, use a timer of at least 4 minutes between these actions. This will ensure the correct workflow operation and consistent execution of all requests in the system.

## Notes

1. If you have several forms assigned to different confirmation emails, you need to create separate workflows and events for each form.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d863e8ce241c7c904224541c4b9211d0c73d75ce9475b337ae4af9a009712a6-setting-up-double-opt-in-204.webp",
        "Different workflows",
        "Different workflows"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> ❗️ Important
> 
> For the event category Click, Key is a required field. The text is optional, but we recommend using Latin without numbers. For example: click, subscription, confirmation, etc.

2. When creating a subscription form, add a checkbox with your terms of use. According to the [GDPR rules](https://docs.yespo.io/docs/gdpr-compliance), the user must check the box to confirm they agree to your terms of use and privacy policies and want to receive bulk campaigns from you.