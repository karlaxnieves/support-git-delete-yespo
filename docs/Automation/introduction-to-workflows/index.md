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

* [Triggered workflows launched by the event.](https://docs.yespo.io/docs/creating-events)
* [Regular workflows](https://docs.yespo.io/docs/how-launch-regular-workflow-segment-support) launched for the selected segments based on the specified conditions.
* Workflows launched by the change in the [contact's profile](https://docs.yespo.io/docs/user-profile).

In Yespo, we use a drag-and-drop builder [to create workflows](https://docs.yespo.io/docs/workflow-management). It is a constructor that uses blocks — the tasks and conditions that you can add to a workflow.

<Image align="center" width="80%" src="https://files.readme.io/c84b0bdae723430958e33bcdae8db51c528bb87caf56a2b55dd655e81080e515-introduction-to-workflows.webp" />

## Workflow Blocks

Workflow blocks are divided into the following groups:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <div style={{ width: "250px" }}>
        Library
        </div>
      </th>
      <th>
        <div style={{ width: "150px" }}>
        Library
        </div>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        [Popular](https://docs.yespo.io/docs/popular-blocks)  — common blocks.
      </td>
      <td>
        • End\
        • Timer\
        • Task\
        • Condition\
        • Check point
      </td>
    </tr>
    <tr>
      <td>
        [Message](https://docs.yespo.io/docs/message-blocks)  — send one message to one contact.
      </td>
      <td>
        • Email\
        • SMS\
        • Viber\
        • Web Push\
        • Mobile Push\
        • App Inbox
      </td>
    </tr>
    <tr>
      <td>
        [Contact](https://docs.yespo.io/docs/contact-blocks)  — remove/add a contact to segments or update custom contact fields.
      </td>
      <td>
        • Update custom fields\
        • Add to segment\
        • Remove from segment
      </td>
    </tr>
    <tr>
      <td>
        [Conditions](https://docs.yespo.io/docs/blocks-description-conditions-group)  — check a contact's compliance with a certain condition, split the workflow into two paths (Yes/No), and run one of them depending on the answer.
      </td>
      <td>
        • Condition\
        • Split\
        • Sent?\
        • Delivered?\
        • Opened?\
        • Clicked?\
        • Included in Segment?\
        • Current day/time
      </td>
    </tr>
    <tr>
      <td>
        [Other](https://docs.yespo.io/docs/other-blocks)  — multifunctional group.
      </td>
      <td>
        • End\
        • Task\
        • Webhook\
        • Sprayer\
        • Check point
      </td>
    </tr>
    <tr>
      <td>
        [Message to segment](https://docs.yespo.io/docs/message-to-segment-blocks)  — send one message to a segment.
      </td>
      <td>
        • Email\
        • SMS\
        • Viber\
        • Web Push\
        • Mobile Push\
        • App Inbox
      </td>
    </tr>
    <tr>
      <td>
        [Time](https://docs.yespo.io/docs/time-blocks)  — delay the execution of actions or execute actions at a specified time.
      </td>
      <td>
        • Timer\
        • Start on date
      </td>
    </tr>
  </tbody>
</Table>

And [Start](https://docs.yespo.io/docs/start-block) block — not included in any group. It automatically appears in a new workflow by default.

## Allowed Send Time Settings

[Allowed time settings](https://docs.yespo.io/docs/allowed-send-time-messages-workflows) can increase the likelihood of a quick response to the campaign and communicate with subscribers at the most convenient time for them.

## Workflow Examples

This section contains instructions for setting up the most common automatic workflows: subscription confirmation, welcome series, abandoned carts and views, etc. [Read more >](https://docs.yespo.io/docs/workflow-examples)