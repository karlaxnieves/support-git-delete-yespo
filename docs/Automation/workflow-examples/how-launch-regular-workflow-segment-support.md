---
title: Regular Workflow for a Segment
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Launch a Regular Workflow for a Segment | Yespo Guide
  description: >-
    A regular workflow is a series of messages that are automatically sent to a
    segment of contacts based on conditions you determine. You can build both
    single-channel or multichannel workflows with any type of message in an
    unlimited number.
  robots: index
next:
  description: ''
---
A regular workflow is a series of automated messages sent to a contact segment based on determined conditions. Most often, regular workflows are used for dynamic segments, but it’s possible to launch a regular workflow for a list segment.

A regular workflow differs from a one-time workflow in that it automatically runs for all new contacts added to the assigned segment after the workflow has been started.

An important condition for launching a regular workflow for a segment is that you must have a contact database with whom you have been interacting for a long time. Read more about [launching a workflow after a contact import](https://docs.yespo.io/docs/how-to-launch-workflow-upon-import).

In this article, we will describe the process of creating a regular workflow for contacts who show certain activity/inactivity in your messages.

You can build both single-channel or multichannel workflows with any type of message in an unlimited number – Email, Web push, Mob push, SMS, Viber or App inbox.

Messages in workflow work together to accomplish a particular goal. It can be

* birthday greeting;
* event invitation;
* reactivation, etc.

## 1\. Create a Dynamic Segment

Dynamic segments can include contacts based on one or more parameters (conditions). The number of contacts in the segment varies depending on how many current contacts match specified conditions.

Let’s create a dynamic segment that includes contacts who opened your messages a month ago.

1. Go to *Contacts* → *Segments*, click the *Add segment* button.

<Image align="center" width="80% " src="https://files.readme.io/95238f9cf80cbcefbac884f3018fa25eece483bc093dfd1a06c8ca688a2fda1a-launching-a-regular-workflow-for-a-segment-001.webp" />

2. Select *Dynamic* segment and click *Create*.

<Image align="center" width="80% " src="https://files.readme.io/796a1baab855da472ae6018eacaee8f2ff11675a0733f5464f6f7a0a6a12c06b-launching-a-regular-workflow-for-a-segment-002.webp" />

3. Fill in general properties:
   * Name (required) — displayed in the general segment list.
   * Purpose (optional) — specify how the campaigns will be used. For example, for triggered emails, regular promo campaigns, etc.
   * [Tags](https://docs.yespo.io/docs/how-add-tags) (optional) — select from the list or add a new one for quick filtering and segment search.
4. Click *Next*.

<Image align="center" width="80% " src="https://files.readme.io/4db3b3ae505ceeb915ecf74a07e78c00400426f293f078b4d286815adf5d4b6e-regular-workflow-for-a-segment-en.webp" />

5. To select conditions click *Add condition*
6. Go to *Channels* → *Contact activity by Email → Last opened → X time ago → 30 → days ago*.

<Image align="center" width="80% " src="https://files.readme.io/442c7cf0e4af7b5ef659805792f382afbcfa26bee22785e6993824fb366ac476-launching-a-regular-workflow-for-a-segment-004.webp" />

5. Click *Done*. The created segment will appear in the general segment list.

<Image align="center" width="80% " src="https://files.readme.io/f8db34dd28210cf02e6f81bf028206ae09abc41432156dc2792e0b968b352a70-launching-a-regular-workflow-for-a-segment-005.webp" />

> 📘 Note
>
> Contacts in the segment are recalculated daily from 3 a.m. to 4 a.m.

## 2\. Create a Workflow

> 📘 Note
>
> You need to create corresponding messages before getting started with a workflow.

Let’s create the following workflow that consists of two emails, timers and conditions.

[Learn more about building and editing workflows >](https://docs.yespo.io/docs/workflow-management)

1. Go to *Automation* → *Workflows* and click *New workflow*. Enter its name and tags (optionally). Build a workflow with the following blocks:
   * **Start**. A required block that starts every workflow.
   * **Timer 1**. The workflow starts sending messages straight after contact recalculation. Since contacts are recalculated from 3 a.m. to 4 a.m., set the timer so as not to bother your recipients at night.
   * **Email**. In Message, select the previously created email. Repeat this for each *Email* block in the workflow.

<Image align="center" width="80% " src="https://files.readme.io/0a14369189a3dbf2e14e38fe21629095ba775f0f8a665f364f85fa8aca0afa91-launching-a-regular-workflow-for-a-segment-007a.webp" />

> 📘 Important
>
> Make sure you select a block *Email* and not *Email to segment*. A segment will be formed during trigger configuration.

* **Timer 2/3**. Specify a time gap between the sends. You can also select on what day and at what hour the message should be sent. The timer starts counting down after contacts have been recalculated but not after the workflow has been activated.
* **Condition Opened/Not opened.** After a specified timer expires, the system checks whether the contact has performed the target action. The workflow continues to run depending on the result:\
  ✓ *Opened*: The workflow sends a follow-up and ends.\
  ✓ *Not opened*: The workflow repeatedly sends the 1-st email. Depending on the response, it sends a follow-up message or ends.
* **End.** The required block that must end every workflow brunch.

2. Click *Save*.

The workflow will look like this:

<Image align="center" width="80% " src="https://files.readme.io/5c141f4cc4f7dd38e8ed2782b4b15ffc20280380ec8c36c79b69ca08ddaa7a97-launching-a-regular-workflow-for-a-segment-006.webp" />

## 3\. Configure Trigger

1. In *Automation* → *Workflows*, choose the created workflow and click Start/Stop *configuration*.

<Image align="center" width="80% " src="https://files.readme.io/4bbf5298dd270bbf203dc736ac755a30850e40bb2392aeb72a15cad93b3f249f-launching-a-regular-workflow-for-a-segment-201.webp" />

2. Activate *Start configuration* switcher
3. In the *Regular* tab,

* In *Segment*, select the created segment.

<Image align="center" width="80% " src="https://files.readme.io/d339824210267524423a467f390c7cfc69fcadd7f51d8c1406068f5ad2bc0a5d-launching-a-regular-workflow-for-a-segment-009.webp" />

* In *Starts on*, select the current date.
* In *Start schedule*, select once a day.
* Select allowed start days.

<Image align="center" width="80% " src="https://files.readme.io/9503197a87d80f2682ed0c167bb807c36406d0d7ec4ec838cbd3788b29460173-launching-a-regular-workflow-for-a-segment-010.webp" />

* Set the *Start time* and set the *End date* of the workflow;
* In *Process unique events*, select each time.

<Image align="center" width="80% " src="https://files.readme.io/a6e29cfa6e2caa4ec68b9c98cc034b0542aa85b5c74e90dd873ca7fe0ef210da-launching-a-regular-workflow-for-a-segment-011.webp" />

* Click *Apply*.

4. To start a workflow, click *Activate* on the right and confirm the action.

<Image align="center" width="80% " src="https://files.readme.io/db893c7844de7093f99aea9b94771986a4a5b0419b4a10eea33f7567492b9715-launching-a-regular-workflow-for-a-segment-202.webp" />

The workflow status will change to active. The first message will be sent when all the conditions specified for the segment are met.
