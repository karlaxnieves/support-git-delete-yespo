---
title: Introduction to Workflows
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Introduction to Workflows | Yespo Guide
  description: >-
    An overview of workflow creation, including the setup of triggers, actions,
    and conditions to personalize user interactions.
  robots: index
next:
  description: ''
---
A workflow is an automated message or series of messages sent based on set up conditions with a particular marketing purpose.

You can use workflows to segment your audience and send different campaign types, such as [welcome series](https://docs.yespo.io/docs/how-create-welcome-email-series), birthday congrats, order confirmation, subscription changes, reactivation, etc.

There are 3 types of workflows:

- [Triggered workflows launched by the event.](https://docs.yespo.io/docs/creating-events)
- [Regular workflows](https://docs.yespo.io/docs/how-launch-regular-workflow-segment-support) launched for the selected segments based on the specified conditions.
- Workflows launched by the change in the [contact's profile](https://docs.yespo.io/docs/user-profile).

In Yespo, we use a drag-and-drop builder [to create workflows](https://docs.yespo.io/docs/workflow-management). It is a constructor that uses blocks — the tasks and conditions that you can add to a workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c84b0bdae723430958e33bcdae8db51c528bb87caf56a2b55dd655e81080e515-introduction-to-workflows.webp",
        "",
        "Workflow builder"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Workflow Blocks

Workflow blocks are divided into the following groups:

[block:parameters]
{
  "data": {
    "h-0": "<div style=\"width:250px\">Library</div>",
    "h-1": "<div style=\"width:150px\">Library</div>",
    "0-0": "[Popular](https://docs.yespo.io/docs/popular-blocks)  — common blocks.",
    "0-1": "• End  \n• Timer  \n• Task  \n• Condition  \n• Check point",
    "1-0": "[Message](https://docs.yespo.io/docs/message-blocks)  — send one message to one contact.",
    "1-1": "• Email  \n• SMS  \n• Viber  \n• Web Push  \n• Mobile Push  \n• App Inbox",
    "2-0": "[Contact](https://docs.yespo.io/docs/contact-blocks)  — remove/add a contact to segments or update custom contact fields.",
    "2-1": "• Update custom fields  \n• Add to segment  \n• Remove from segment",
    "3-0": "[Conditions](https://docs.yespo.io/docs/blocks-description-conditions-group)  — check a contact's compliance with a certain condition, split the workflow into two paths (Yes/No), and run one of them depending on the answer.",
    "3-1": "• Condition  \n• Split  \n• Sent?  \n• Delivered?  \n• Opened?  \n• Clicked?  \n• Included in Segment?  \n• Current day/time",
    "4-0": "[Other](https://docs.yespo.io/docs/other-blocks)  — multifunctional group.",
    "4-1": "• End  \n• Task  \n• Webhook  \n• Sprayer  \n• Check point",
    "5-0": "[Message to segment](https://docs.yespo.io/docs/message-to-segment-blocks)  — send one message to a segment.",
    "5-1": "• Email  \n• SMS  \n• Viber  \n• Web Push  \n• Mobile Push  \n• App Inbox",
    "6-0": "[Time](https://docs.yespo.io/docs/time-blocks)  — delay the execution of actions or execute actions at a specified time.",
    "6-1": "• Timer  \n• Start on date"
  },
  "cols": 2,
  "rows": 7,
  "align": [
    "left",
    "left"
  ]
}
[/block]


And [Start](https://docs.yespo.io/docs/start-block) block — not included in any group. It automatically appears in a new workflow by default.

## Allowed Send Time Settings

[Allowed time settings](https://docs.yespo.io/docs/allowed-send-time-messages-workflows) can increase the likelihood of a quick response to the campaign and communicate with subscribers at the most convenient time for them. 

## Workflow Examples

This section contains instructions for setting up the most common automatic workflows: subscription confirmation, welcome series, abandoned carts and views, etc. [Read more >](https://docs.yespo.io/docs/workflow-examples)