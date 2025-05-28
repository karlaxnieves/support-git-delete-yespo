---
title: Launching Workflow Conditions
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
You can specify different launch conditions for workflows.

* **[Launch on event](https://docs.reteno.com/docs/launching-workflow-conditions#on-event):** the workflow is triggered by the selected event;
* **[Regular launch](https://docs.reteno.com/docs/launching-workflow-conditions#regular):** the workflow launches for the selected segments based on the specified conditions;
* **[Launch on contact field change](https://docs.reteno.com/docs/launching-workflow-conditions#on-contact-field-change):** the workflow is triggered by the change in the [user’s profile](https://docs.reteno.com/docs/user-profile).

## On Event

Workflows triggered by the event are sent in response to a user’s action (trigger). It can be a subscription, registration, click in the message, purchase confirmation, app inactivity, etc. You can send events to Reteno via [Firebase](https://docs.reteno.com/docs/streaming-events-from-firebase) / [API](https://dash.readme.com/project/reteno/v1.0/docs/sending-events-via-api), and they can be [generated within the system](https://docs.reteno.com/docs/events-category).

Let’s see how to configure the launch on the event using a workflow with a welcome mobile push as an example. This workflow is triggered by a registration in your app.

1. Create a workflow and select the message that will be sent to all new subscribers.

<Image width="80%" src="https://files.readme.io/c450bbb-Workflow_conditions_1.png" />

2. In *Trigger configuration*, select *On event* and select the event in *Event type*.
3. In *Process unique events*, select once. This way welcome messages won’t be sent to users who attempt to register for the second time.
4. Click *Apply*.

<Image width="80%" src="https://files.readme.io/91a22c1-Workflow_Conditions_2.png" />

5. In the general list, click *Start* and confirm it. The workflow status will change to *Active*.

<Image width="80%" src="https://files.readme.io/6cdcec4-Workflow_conditions_3.png" />

6. You can manage your workflows using the settings on the right.

<Image width="80%" src="https://files.readme.io/5ba8484-Workflow_conditions_4.png" />

## Regular

Regular workflows are only launched for a dynamic segments. A dynamic segment includes users who match the pre-selected conditions. By default, regular workflows are launched once a day after users’ recalculation. You can change the frequency in the settings. Before creating a workflow, you need to create a segment you assign to this workflow.

1. Create a workflow and select the message that will be sent to contacts included in the segment.
2. In *Trigger configuration*, select *Regular* and select the segment. Configure other settings if needed and click *Apply*.

<Image width="80%" src="https://files.readme.io/aa32238-Workflow_Conditions_5.png" />

3. In the general list, click *Start* and confirm it.\
   Learn more on how to launch a regular workflow.

## On Contact Field Change

Changing the additional fields in the user’s profile can be a workflow trigger. It’s often used to notify about the completion of different actions, such as migration to another plan, subscription, change of preferences, unlocking a new loyalty program level, etc.

1. Create a workflow and select the message that will be sent to users whose profiles have been changed.
2. In *Trigger configuration*, select *On contact field change* and select the contact field. Click *Apply*.

<Image width="80%" src="https://files.readme.io/5a49614-Workflow_Conditions_6.png" />

Note that the workflow will launch only if the field is changed

* after [users’ import](https://docs.reteno.com/docs/importing-data-via-file);
* after data transfer via the [/searchUsers](https://docs.reteno.com/reference/searchcontacts-1) API resource.

If additional fields are changed manually or through any other method, the workflow will not start.
