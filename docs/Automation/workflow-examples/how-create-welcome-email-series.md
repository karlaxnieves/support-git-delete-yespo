---
title: Welcome Сampaign
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Create a Welcome Email Series | Yespo Guide
  description: >-
    Learn how to create automated welcome email series that will be sent to new
    subscribers in real time. Welcome emails engage new subscribers, introduce
    your brand and simplify the onboarding process.
  robots: index
next:
  description: ''
---
Customer data is often sent to our CDP using the [subscribe API method](https://docs.yespo.io/docs/api-methods-adding-contacts#subscribe-contact). In this case, the subscriber is added to the database as an unconfirmed contact. You can't send promotional emails to unsubscribed contacts without their permission to receive them from you.

To get the customer's permission, you need to ask them to validate their email address by sending a confirmation email through a [Double Opt-In](https://yespo.io/blog/why-do-we-need-double-opt-in) series. The next step is to send a welcome series.

The design of a welcome series will depend on your marketing goals.

In this article, we’ll create a standard series consisting of two [welcome emails](https://yespo.io/blog/best-practices-welcome-emails). Since it is preceded by a double confirmation, thanking for the subscription is recommended in the first message. A discount or promotional code can also be a good start of the conversation. In the second message, you can tell more about the company and introduce the subscriber to other communication channels (social media, push notifications, YouTube, etc.).

## Step 1. Create welcome emails.

> 📘 Important
>
> Before getting started, we recommend you read a complete guideline on [creating an email in the drag-and-drop editor](https://docs.yespo.io/docs/compose-email).

1. Go to *Messages → Messages* and click *New Email*.

<Image align="center" width="80% " src="https://files.readme.io/075a329644979eaec5f52d001a1c6075df8315ed93c6aaf6f8b0c294ab8cc73b-creating-a-welcome-email-series-015.webp" />

2. For the first email, in *Basic*, select a *Welcome* template or create your own. Fill it with your content and edit as needed.

<Image align="center" width="80% " src="https://files.readme.io/d2e5c16ad3b0b023924adc8e67985955740694fc5f52b1ba91e919ea2c0aa442-creating-a-welcome-email-series-000.webp" />

3. For the second message, select a *Form* template or create your own onboarding email. Fill it with your content and edit as needed.

<Image align="center" width="80% " src="https://files.readme.io/60402e2dce8790438509253820d154c4659547967074ed1e3a103766812fe737-creating-a-welcome-email-series-001.webp" />

4. To send test emails, click *Test* (**1**). To preview ready emails on desktop and mobile, click *View message* (**2**).

<Image align="center" width="80% " src="https://files.readme.io/067172007cb40105a63c57b6ec1cee4039783737f31cab25906abe32188046d4-creating-a-welcome-email-series-002.webp" />

5. Click *Save*.

## Step 2. Create a Workflow

> 📘 Important
>
> Before getting started, we recommend you read complete instructions on [creating a workflow in the drag-and-drop editor](https://docs.yespo.io/docs/workflow-management).

We’ll create a standard workflow that would look as follows:

<Image align="center" width="80% " src="https://files.readme.io/2917e3a624174878396f8ced77bea7d5dbb4eab6cbf20e02e4fdf1e7ea65c994-creating-a-welcome-email-series-011.webp" />

1. Go to *Automation* → *Workflows* and click *New workflow*.
2. Enter its name and add tags (optional).
3. Create a workflow with the following blocks:

* **Start** (created by default). Required. Automatically starts any workflow.\
  **Task: Confirm contact** (*Popular blocks* or *Other blocks*). Create contact is a default task type. To set it manually, select *Confirm contact* in the *Task* name on the right.

<Image align="center" width="80% " src="https://files.readme.io/bb47c6391c6386c82c69c49e98f27892317a81a3f8cdf4bda15875b3ab13bc68-creating-a-welcome-email-series-012.webp" />

* **Email** (*Message blocks*). Select the first email in Message on the right.

<Image align="center" width="80% " src="https://files.readme.io/0e4bfa219e9367ba5a49cd2d0633d10b953904fa456764e5a96cd7ee65665455-creating-a-welcome-email-series-013.webp" />

* **Timer** (*Popular* or *Time*). Set a time gap before the second message in Wait on the right. It’s recommended to select 3 to 5 days between two emails.

<Image align="center" width="80% " src="https://files.readme.io/44fdccac9f7ae23f33513f9234b6a80b3a89eb9316b005c37df6a06f359f99f9-creating-a-welcome-email-series-014.webp" />

* **Email** (*Message* blocks). Select the second email in Message on the right.
* **End** (*Popular* or *Other* blocks). Required.

All blocks must be connected.

4. Click *Save*.

## Step 3. Launch a Workflow

The subscriber confirms their address by clicking the corresponding button in the confirmation email. This button is assigned to the *Confirmed subscription* event type.

<Image align="center" width="80% " src="https://files.readme.io/69690bcf60f0978a929a41c0f28e1a73c4545d9c6f29cd5781db164fc2f9cc6d-creating-a-welcome-email-series-007.webp" />

This event signifies to the system that the subscriber has given their consent to receiving emails from you and triggers a welcome series.

To assign the [event](https://docs.yespo.io/docs/creating-events) to the workflow, go to *Automation* → *Workflows*, select the necessary workflow and click *Start/Stop configuration*.

<Image align="center" width="80% " src="https://files.readme.io/5f8f4ad55b8679602626891ef12dd7f59bbbb63291dc9271aafd7c0939f8e793-creating-a-welcome-email-series-201.webp" />

1. In *Start/Stop configuration* window activate *Start configuration* switcher.
2. Select *Event-based* and *Confirmed subscription* event.

<Image align="center" width="80% " src="https://files.readme.io/2b5a707e0d0d9440c8b9d4f92fda1b712a859625eaba57b98a7df2f1319749fa-creating-a-welcome-email-series-009.webp" />

3. Click *Apply*.

Click *Activate* to launch the workflow.

<Image align="center" width="80% " src="https://files.readme.io/aab040162fe5a898f2de3703b2697dac1ceef951122aa75045c3aab38fe31aac-creating-a-welcome-email-series-202.webp" />
