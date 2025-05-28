---
title: Preparation for Campaign Launch
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Preparation for Campaign Launch | Yespo Guide
  description: >-
    The document outlines steps for starting an email campaign, including
    selecting a template, providing general information, adding settings,
    editing content, previewing and testing, and saving the email for future
    use.
  robots: index
next:
  description: ''
---
Complete the following steps before starting a campaign.

## Step 1. Selecting and Creating Template

Go to the *Messages → Messages* section and select a template from one of the three tabs:

* **Basic** — templates of the most common types: plain text, promo, triggers, greetings, etc. The last template on this tab is for using your own HTML code.
* **Gallery** — templates for various industries and information purposes.
* **Saved** — your templates.

<Image align="center" width="80% " src="https://files.readme.io/1bdb3a493cc09a4a1328fec4f13c626d3104c794d0a83e8b76d62fc43f6ad219-image7.webp" />

## Step 2. Providing General Information

Click on the message name to enter its general information.

<Image align="center" width="80% " src="https://files.readme.io/e4a2b417ae4680aa75500270ce398fa086f23710fee11edc4b1091a7eb6b39ef-image15.gif" />

### Message Name

The name for internal identification of messages and reports.

<Image align="center" width="80% " src="https://files.readme.io/a1fb8cd54a39af5a254fff1d16fa87e5c3124894be887824e8601b9d2c78f230-image1.webp" />

Recipients can only see this name in the email's UTM tag if the default settings are used (*utm\_campaign=message name*). To set UTM tags manually, read the instructions [at the link](https://docs.yespo.io/docs/how-transfer-utm-parameter).

If you do not specify the name of the email when saving, the subject of the campaign will be automatically inserted into this field.

### Subject

The email subject is the line of text that appears in a recipient's inbox, summarizing the content or purpose of the email. It's typically placed at the top of the email, just before the body of the message, and serves as a brief, attention-grabbing headline. The subject line is crucial because it influences whether the recipient decides to open the email. A clear, concise, and relevant subject can significantly increase the likelihood of the email being read.

<Image align="center" width="80% " src="https://files.readme.io/b2115cfe1edb4bad381fb0a0fa98edb431a6d0cc0d669feb44ac5d5ebd41abb9-image14.webp" />

To see our subject wording tips, click the check mark/exclamation mark next to the subject.

To test the effectiveness of different subject options, add them using the appropriate button ([see details](https://docs.yespo.io/docs/how-test-email-subject-lines)).

> 📘 Note
>
> You can [use AI](https://docs.yespo.io/docs/using-ai-email-editor) to optimize your email's subject line, preheader, and body. Click the *Improve with AI* button and choose the best option.

### Hidden Preheader

A hidden preheader is displayed in the mailbox after the subject.

<Image align="center" width="80% " src="https://files.readme.io/4b38f835a525259138188eb83267f6bcb56640e0cffb52fa9e820a9f87feddc5-image4.webp" />

You can find more details about the tasks and settings of the preheader [at the link](https://docs.yespo.io/docs/adding-a-hidden-preheader).

### Sender

The sender's name is created by default based on the account user's data.

<Image align="center" width="80% " src="https://files.readme.io/da23ed1bc03b1733467504326d93e14c6392ba73247b6c370a41a4424a3ac7ca-image5.webp" />

To use a branded sender name, you need to add it according \[to the instructions]\(http\://Mailing from public addresses is impossible, so you must add a sender before sending.).

> 📘 Note
>
> Mailing from public addresses is impossible, so you must add a sender before sending.

### Reply to

By default, all replies are accepted to the sender's address. If addresses like `noreply@...` are used as the sender, Gmail may mark the emails as less reliable because recipients cannot quickly contact the sender. This may affect the delivery of emails. In this case, we recommend adding an alternative address to senders and then selecting it in this field.

<Image align="center" width="80% " src="https://files.readme.io/e892dc81dce5df1af8136f2ff4d20d546dfe7c7b074e31e9e1e5429f625e0883-image8.webp" />

### Tags

Tags allow you to group messages, segments, reports, and workflows with common marketing goals. In addition, tags are used

* When building a [campaign frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy),
* In the *[One from many](https://docs.yespo.io/docs/using-one-many-block)* workflow block, which automates A/B testing, diversifies communication, and determines the most effective version of the message.

<Image align="center" width="80% " src="https://files.readme.io/aa46a16705505a46d86211a498f86d0b95f6f8c252d9bb5b8104a8896a1def18-image13.webp" />

### Subscription Categories

Set up [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) to segment promo campaigns based on your audience's interests.

<Image align="center" width="80% " src="https://files.readme.io/b7c434f30563e5fdda7416eceb8dc990768ff223639bef46dcbeada5de923b02-image11.webp" />

### Annoyance Level

Use this option to protect your subscribers from excessive marketing communications.

<Image align="center" width="80% " src="https://files.readme.io/c31ef66ab2d19ddbc8ca84d29629220b6c58c99e6a835973fbc29a6701435117-image10.webp" />

[More on setting annoyance level >](https://docs.yespo.io/docs/management-campaign-frequency)

### Gmail Promotions Annotations

You can [configure the message annotation](https://docs.yespo.io/docs/how-create-gmail-promotions-annotations-emails) displayed in the Gmail mobile mail client for emails in the Promotions folder.

<Image align="center" width="80% " src="https://files.readme.io/c53ab21c247f2dde7431205a5a65dc4d0b67d416612f725303d664e499ddb5df-image12.webp" />

## Step 3. Adding General Settings

This section describes non-required but important options for advanced email settings.

### Multilanguage

This functionality allows you to create an unlimited number of language options directly in the message. This significantly saves time when creating a campaign for a multilingual audience due to the absence of redundant copies of the message, multiple language segments and checks in the workflow, etc.

<Image align="center" width="80% " src="https://files.readme.io/9b3b9a087633bbcb18a270ef3f4d27f20d78b3a87e8940d825db6c32b7e39527-image3.webp" />

[More on multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

### Personalization and Dynamic Variables

To personalize the content of a message in Yespo, you can use built-in merge tags or do it through code ([read more](https://docs.yespo.io/docs/personalization-and-dynamic-variables)).

<Image align="center" width="80% " src="https://files.readme.io/31ccac355703b86297b74b32f3cb7ba3db9caa1136f0f999e19d3e8cfa0c394c-image17.webp" />

You can also use personalized promocodes in messages — the settings options are described [in the link](https://docs.yespo.io/docs/promocodes).

### Unsubscribe

An unsubscribe link is mandatory for every email sent from Yespo, as it is a requirement of mailers and legislation in most countries. You also need to add text explaining why the user received this email.

<Image align="center" width="80% " src="https://files.readme.io/48d061805cf76cf88693610f785340ee7994432cb7f28a3cd67a16b5e54ba56a-image6.webp" />

You can change this structure's text, design, and placement in the email. Only the default unsubscribe link should remain unchanged.

Email addresses of users who unsubscribe are automatically no longer available for email newsletters.

## Step 4. Content Editing 

Our drag-and-drop editor makes it easy to create professional emails without the need to work with code. Just drag the blocks and edit the content; you'll have an email ready in a few minutes. The [Email Editor](https://docs.yespo.io/docs/email-editor) section provides more detailed information.

We also recommend paying attention to the special features of the editor:

* [AMP blocks](https://docs.yespo.io/docs/amp) for using interactive content,
* [Product blocks](https://docs.yespo.io/docs/product-blocks) for displaying personalized recommendations.

## Step 5. Preview and Test

While creating a message, you can easily preview how it will look on desktop and mobile devices. To do this, click the *View message* icon on the top panel of the editor.

<Image align="center" width="80% " src="https://files.readme.io/b17c48a5994764a941ade3cd2b54ffa545c4326d3ac522ae1e7d13f3366f9b9f-image18.webp" />

If you use personalization in the email, you can check in the preview window (1) how a specific contact will see the message or how it will display data from a JSON request (2).To check the email display in the mailbox:

<Image align="center" width="80% " src="https://files.readme.io/1632a862bfa71da17362bf4f7dc85f374982901ad3a6342c7cd6a4e07e52bfa3-image9.webp" />

* Click the TEST icon on the top panel of the editor (1).
* Specify the email address to which you want to send the test email (2),
* Click the *Send* button (3).

<Image align="center" width="80% " src="https://files.readme.io/70dded9b87e71b39c5007c8f6a76030283127897b3d07a59146d9029c7ee1807-image2.webp" />

We also recommend testing your email in special services like Litmus or Email on Acid. This is especially important if you use non-standard designs or transfer HTML code to the editor.

## Step 6. Saving

When you click the *Save* button (1), the Email will be created or updated in the *Messages → Messages* section. Select *Save as template* (2) if you want to use the created message as a template for further campaigns (*Saved* tab). 

<Image align="center" width="80% " src="https://files.readme.io/82f18b0abf67011e1d628bb767b74722bec06c51a1453640f5712274981ca58f-image16.webp" />

Now, you can proceed with the [launch of the campaign](https://docs.yespo.io/docs/how-launch-email-campaign).
