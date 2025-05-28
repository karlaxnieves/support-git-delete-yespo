---
title: Customer Reactivation
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Automate Customer Reactivation | Yespo Guide
  description: >-
    Learn how to create and launch automated reactivation campaigns and send
    them as bulk or triggered messages. Reactivation campaigns help drive
    customers back, generate revenue and increase your active contact base.
  robots: index
next:
  description: ''
---
Any business has inactive customers who haven’t opened messages or made orders for some time. You can drive back part of this audience with automated reactivation campaigns.

To create a reactivation campaign, you need to build a dynamic segment and schedule a single message or create a workflow.

## Creating a Dynamic Segment for Reactivation

A dynamic segment is a group of contacts where contacts are added automatically based on the set conditions. For a reactivation segment, you can select such conditions as the last open, click, order, etc. performed a certain time ago. Segments are recalculated every day at 3 to 4 a.m. UTC, and all contacts who have been added to it receive the reactivation message at the specified time.

Before getting started, we recommend you read a full guideline on [how to create a dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment).

1. Go to _Contacts → Segments_ and click _Add segment_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/747909c09b64a6037ff624386bf5684a173988c0925ab6c5661d883ad51c3dbb-customer-reactivation-001.webp",
        "Add segment",
        "Add segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select _Dynamic_ and click _Create_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c7300d1f581007bdbeabb565ccf6df4d9a8aab6cae3ae779ee23faac3daf423b-customer-reactivation-002.webp",
        "Dynamic segment",
        "Dynamic segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Enter segment name (required) and purpose and tags (optional). Click _Next_.
4. In _Include_, click _Add condition_ and select conditions (contact activity, orders or events) and time of the last activity.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b29e450b3d4d97390f52810388dbbbf9683e556c054a2dba6172b1a559b76ce8-customer-reactivation-003.webp",
        "Add condition",
        "Add condition"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. After the card is created, you can include more conditions to it or exclude them.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/582600b86600903c9b65608290ced46c337a29ccba58d35601b863223de3d636-customer-reactivation-004.webp",
        "Created card",
        "Created card"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. When all conditions are specified, click _Done_.

## Launching an Automated Reactivation Campaign

Let's look at a regular campaign and workflow creation.

### Regular Campaign

1. Go to _Messages → Messages._
2. Select the previously created reactivation message and click _Create campaign_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3583fffe910e7d85337068b187593d05505140c9612826614c86392cef14104f-customer-reactivation-005.webp",
        "Create campaign",
        "Create campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the created segment or segments for reactivation and click _Go to campaign_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3fcfea6c6e92e9d108a62cccbcd94e4e4c084ff600d4cdcc9eb4c765d041b35b-customer-reactivation-006.webp",
        "Go to campaign",
        "Go to campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Scroll down to _Send options_ and click _Schedule_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4ddcebcbe7366cd8b57b6c425aebf831f8bfe3ac937ee4335f624d4a77984f8-customer-reactivation-007.webp",
        "Send options",
        "Send options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Select _Every day_ and click _Confirm_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79cabde256a590a4c0311843be0a80022ed0db7cae37698f69ffa5370e4781af-customer-reactivation-008.webp",
        "Schedule",
        "Schedule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can find scheduled campaigns in _Campaigns → Scheduled campaigns_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f50ffd55516bd215c665e3e0b6ceecd2cad1da7d4a65a4f54215e5227a97d7c2-customer-reactivation-009.webp",
        "Scheduled campaigns",
        "Scheduled campaigns"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Reactivation Workflow

Workflows allow you to send both single messages and series consisting of multiple multichannel messages and conditions.

Before getting started, we recommend you read a full instruction on [how to create a workflow in the drag-and-drop editor](https://docs.yespo.io/docs/workflow-management).

1. Go to Automation → Workflows and click New workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cd9dbc4c16d06de82c336afa04a0200eea288cc429248cd311fa00a5744b21d1-customer-reactivation-010.webp",
        "Reactivation Workflow Creation",
        "Reactivation Workflow Creation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter its name and tags (optionally).
3. Create a workflow with the following blocks:

The simplest workflow will consist of the following blocks:

- Start
- Timer
- Email (you can choose any type of message available in Yespo)
- End

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37b7859ab4ca5cb186aa540854cdf61115978856c8924bc544ca93c9776a313d-customer-reactivation-011.webp",
        "Workflow",
        "Workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Timer_ block regulates sending time so that the campaign isn’t sent to contacts straight after recalculation. In _Wait time_ enter the time of delay, in _Wait until_ select the day of the week and the time for sending the message.

If you need to consider the contact's time zone, activate the corresponding checkbox.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b59ca883a3428ec585bb98340cdb28ae94f09d39c62586f0418261b056710fdf-customer-reactivation-012.webp",
        "Timer block",
        "Timer block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Select the reactivation email in the _Email_ block parameters.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fedd2886151b9d5c385804dbf0ceb018fbe30f81e149d25cce3113c1c8f07d18-customer-reactivation-013.webp",
        "Email block",
        "Email block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


All blocks must be connected to each other.

4. Click _Save and exit_.
5. Go to _Automation → Workflows_, select the necessary workflow, and click _Start/Stop configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/320f25429b940f7addfe2e8e09e7fe8c2fb51ef1efa9f69b1a2b023016c74c49-customer-reactivation-201.webp",
        "Trigger configuration",
        "Trigger configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Enable the _Start Configuration_ slide button, select the _Regular_ condition and created segment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cab3fd0529e06d39ea7e4f6a5c0f71c7a6767de618e9ee0ad32ff2278a9047a4-customer-reactivation-015.webp",
        "Start Configuration",
        "Start Configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


7. Select _Each time_ in _Process unique events_ and click _Apply_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e7d35884243d90070063ef5ec7b7fc8fdf93e92dc32b6389f9d46e83810c3343-customer-reactivation-016.webp",
        null,
        "Each time"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


8. Click the _Activate_ button to launch the workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a0224fb7648385585d6bf8c2e028caf3b23f27b0e092c78b7eaf266d5824af4-customer-reactivation-202.webp",
        "Activate  button",
        "Activate  button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


All contacts included in the dynamic segment will receive the reactivation campaign at the time specified in the workflow.