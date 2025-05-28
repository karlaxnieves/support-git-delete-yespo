---
title: Using One from Many Message Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Optimizing Campaigns Using One from Many Message Block | Yespo Guide
  description: >-
    Learn how to use the One from many message block to simplify the A/B testing
    process, diversify communication and optimize your campaigns.
  robots: index
next:
  description: ''
---
The *One from many* block sends the best one from all messages with specific [tags](https://docs.yespo.io/docs/how-add-tags). The main purpose of the block is to understand what option is the best. At first, the block sends specified messages randomly to gather performance data. After a few thousand messages are sent  within one workflow, the algorithm starts to prefer the messages with higher click-through rate (CTR). At the same time, the block considers the message's previous performance and the last messages sent to the contact to select the best option.

This block can be considered a continuous A/B test that improves performance with every message sent, providing the best possible CTR for the given set of messages.

We encourage you to add messages to *One from many* block at any time. If you have any idea about a better version of the message, just mark it with the tag, and the *One from many* block will give it a try.

## Adding Tags to Messages

Open the message in the editor, find the *Tags* field, and add the necessary ones: *Cart, Browsing, Reminder*, etc.

<Image align="center" width="80% " src="https://files.readme.io/3a80c9683c8a9ba32fbed290788fbfb832cff7d69978b617aae0188479cffa1a-one-for-meny-1.webp" />

## Setting Up Workflow with One From Many Block

The *One from many* block participates in workflows like any other [message](https://docs.yespo.io/docs/message-blocks).

1\. Open or create a workflow in the *Automation → Workflows* section.

<Image align="center" width="80% " src="https://files.readme.io/73937bacfaff5ffc092f35490c042a1aeb6d7ae0079414d40fd92c888e0bf49c-one-for-meny-8.webp" />

2\. Drag the *One from many* block from the left sidebar into the workflow.

<Image align="center" width="80% " src="https://files.readme.io/f220c439ed161b777063e7fa0693e4c7310ccd4c90512d178cdf7858ff325f29-one-for-meny-3.gif" />

3\. Configure the block parameters:

* **Send via** — messages’ media channel.
* **Application** — the name of a Mobile Push app or Telegram bot (there is no option to select an application if there is only one app or bot registered in the account — the corresponding parameter will be applied automatically).

<Image align="center" width="80% " src="https://files.readme.io/dbb059ddca9e57fb005ed69afe26686cf5fcfb753011c166b26625932e53709d-one-for-meny-4.webp" />

* **Include variants with tags** with which messages will be triggered.
* **Exclude variants with tags** so that the block does not trigger them. We recommend implementing a persistent tag like *Excluded* or *Stopped* and then adding it to low-performing messages to stop their sending. The check for sending or excluding messages occurs every time the message is sent.

<Image align="center" width="80% " src="https://files.readme.io/903013bbd39bc7932c05ac554a8734fcc6b7cae3bc4e03b2e951ae2ed39c8b5a-one-for-meny-5.webp" />

> 📘 Note
>
> * The numbers next to the tags indicate the number of messages with those tags. “0” means the tag exists but must be added to the appropriate messages.
>
> * Create a tag in the message editor in advance because it cannot be created while editing a workflow.

* **Get AI suggestions based on message variants:** Generate additional versions of messages and their translations based on existing ones.)

<Image align="center" width="80% " src="https://files.readme.io/fd7511d0b1c1e56150e69db6b24f45fcf169be7a5ce66f97d1101fa78273388d-image1.png" />

> 👍 Recommendation
>
> Use the AI generation feature wherever Mobile Push messages are used in the *One from many* block. Consistent application across campaigns ensures you capture every opportunity to engage contacts with the highest-performing copy.

[Learn more about generation >](https://docs.yespo.io/docs/mobile-push-generation)

* **Send only in[specified hours](https://docs.yespo.io/docs/allowed-send-time-messages-workflows)** — by default, daytime hours are set for all organizations from 8:00 a.m. to 8:00 p.m. to avoid bothering contacts with messages at the unsuitable time and postponing the campaign until the allowed period.

<Image align="center" width="80% " src="https://files.readme.io/35723892361b534abb1f37877d949d55496120459ba4ad58d7b8129609e63c93-one-for-meny-6.webp" />

4\. To quickly preview or edit the messages included in the block, click the preview icon in the field with the number of options filtered by tags.

![Preview](https://cdn.yespo.io/photos/shares/Blog/one_from_many/one-for-meny-7.gif "Preview")

5\. Configure the [launching workflow conditions](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions) and activate it.

> 📘 Note
>
> To diversify communication, the system avoids sending messages that have been used and sends one of the unused ones. The system checks which messages have already been sent to a contact
>
> * within four days;
> * as part of a workflow (for example, when several *One from many* blocks are used).
>
> If all variants have already been sent, the message selection is random.

## Analytics

To investigate the messages’ effectiveness, go to the *Campaigns → Reports* section and enter the tag in the search field or click on it in the report list.

<Image align="center" width="80% " src="https://files.readme.io/d97f04049c5ad40352ed9be485460a306770de4c7e04c85e0f0d8e5e482bbf70-one-for-meny-2.webp" />

To manually stop a message with low performance, add a tag specified in the block's exclusions (for example, *Excluded* or *Stopped*).

## Using Block

The *One from many* block helps to A/B test different messages in your workflows.

Use this block to

* **Simplify the A/B testing process:** There is no need to create separate workflow branches for each message or channel option, which significantly reduces the time for preparation and subsequent workflow adjustments and the probability of making a mistake when changing the message.
* **Diversify communication in trigger campaigns:** If one workflow launches several times for the user, we recommend diversifying the messages so that one customer doesn’t get the same content for training or lesson reminders, abandoned carts and views.
* Test hypotheses: If you have ideas for improving messages, just add a new option to the block settings with a few clicks and watch the result — there is no need to edit the workflow and run A/B tests separately.
* **Continuously optimize campaigns:** We recommend regularly adding new messages to achieve better results. Remove or add the appropriate tag to replace, upgrade, or discontinue an option with lower performance.
