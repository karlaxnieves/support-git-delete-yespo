---
title: Adding/Changing/Deleting a Sender Name
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding/Changing a Sender | Yespo Guide
  description: >-
    Use different sender names to differentiate your emails and let subscribers
    filter your campaigns.
  robots: index
next:
  description: ''
---
Use different sender names to separate different types of emails and let subscribers filter your messages. For example:

* promos;
* messages from managers;
* triggered emails, etc.

You can add or change a sender in a few ways:

> ❗️ Important
>
> Before configuration, you must add [email authentication](https://docs.yespo.io/docs/email-setting-up).

## Adding a Sender in the Email Editor

### Static Sender Address

1. Go to **Messages** → **Messages** → **Email** → open the email or create new one.

<Image align="center" width="80% " src="https://files.readme.io/3cb5847851145299d685b56147390210eea9c99ad74046477b378ff7b79c1f0c-image1.webp" />

2. Click the **Title** or **Subject** of the message to open the settings.

<Image align="center" width="80% " src="https://files.readme.io/d18290447176d6cde42c515a820d582b9ebe4709f7d061f0d657763caeffaf99-image2.webp" />

3. Click  **+New sender** .

<Image align="center" width="80% " src="https://files.readme.io/8927cd3cf87a10cc50727c6c8eddecb53d493c7099e82ed01482c70bde28cfdf-image4.webp" />

4. Enter a new sender name and email address.

<Image align="center" width="80% " src="https://files.readme.io/dce7738243d01c6e395ef782662124cd5baa3de8fc50e71a0570fe5425134d94-image21.webp" />

> 📘 Important
>
> The sender's email address must be in your corporate domain. For example, for the site yourcompany.com you can add an address like this:
>
> * `marketing@yourcompany.com`
> * `support@yourcompany.com`

After clicking **Add**, the system will send a confirmation email to the specified email. Confirm the request in the email from Yespo Support.

<Image align="center" width="80% " src="https://files.readme.io/21adf256a762170f00362108f63da61b3286ec16f5b54e1de1db7c94165e4be9-image5_y.webp" />

5. To change the sender's address, click on a previously added sender and select a new one.

<Image align="center" width="80% " src="https://files.readme.io/914294fccf7feb6d041c933384a577cefba72ae6f64fd22be8e31d309008967e-image6.webp" />

### Dynamic Sender Address

Use this option to send a bulk campaign with different senders. For example, when you need to automatically substitute the names of a personal manager for each customer. For triggered messages sent through a workflow, you can use as a reply-to address:

* Event parameter value
* Contact field data

To add a dynamic sender address, follow the next steps in the email editor.

1. Click on **Sender**.

<Image align="center" width="80% " src="https://files.readme.io/9597b185fee2a54fa31595fd577d71ce1a77aee7224f3cc757a4c066c5cef92b-image3.webp" />

2. Go to **Dynamic address**.

> 📘 Important
>
> If this option is unavailable in your account, apply for activation

<Image align="center" width="80% " src="https://files.readme.io/136ba3444c47a97a3e59d1000d409de292557bd9380d413126e5d626c6491801-image8.webp" />

To substitute the sender from the event parameters, specify the velocity structure in the corresponding field. For example, `$!data.get(‘yoursender_address’)`, where `yoursender_address` – variable from the event.

To substitute the sender from the contact card, click on the **person icon**  and select the appropriate contact field. The variable will be automatically added to the field.

<Image align="center" width="80% " src="https://files.readme.io/9a76dc6945f84e6fb2e5624e6fe38930b77f1930c80db49aac3f04171da6920c-image9.webp" />

3. Click the **Save** button.

## Adding a Sender Via Account Settings

Go to your account → **Settings** → **Senders**  → **New sender**.

<Image align="center" width="80% " src="https://files.readme.io/ae22b4c4f15a3d439b82a223c858c87056fc4431f1bcf80aa031db6f36feb464-image10.webp" />

2. Enter a new sender name and email address.

<Image align="center" width="80% " src="https://files.readme.io/1ee5b220c1b7c7a8b6b76b0f0383189d8a5cbc880fcb07dfbfdfd8fbb49e63f9-image11.webp" />

After clicking **Add**, the system will send a confirmation email to the specified email. 

3. Confirm the sender name in the email from Yespo Support.

After confirmation, the sender receives the status **Available**. The status **Awaiting confirmation** will be displayed until you click the link from the email. In the **Sender name** tab, you can see a list of all senders with their statuses. For sender names awaiting confirmation, you can resend request:

<Image align="center" width="80% " src="https://files.readme.io/ecc484ac5544902a132bdbea5699d35778551f781ee1ee6a7623774567932171-image12.webp" />

## Adding Reply Address

By default, all users reply to the sender's address. If you need, add another reply address. Send messages from a common address, for example, `news@yourcompany.com`, and receive replies to another address.

<Image align="center" width="80% " src="https://files.readme.io/cace4436fa64360f3e8c4c156acc6671533f4f29def2f8ed61a68d764b2529e5-image11.webp" />

The reply address is added in the same way as the sender name.

> 📘 Important
>
> Reply address must be in your corporate domain

## Deleting a Sender

Go to your account settings →  **Senders → Email** tab. Click on the cross in the spacer with the sender you want to delete (if there is only one sender in the account, you cannot delete it).

<Image align="center" width="80% " src="https://files.readme.io/f7767890d5d9ba01e279c0613a47cecc5af795820419ceb8933d1eee96fe701d-image12.webp" />

If the sender is not used in any messages, click **Delete**, after which the system will delete it from your account.

<Image align="center" width="80% " src="https://files.readme.io/876dbbe67ce9a9de711ffd513172c0f5953fab3556771910b242ce8a01f0ab44-image41.webp" />

If the sender is used in messages, the system will prompt you to select a different one.

Select a new sender to apply to these messages and click **Delete** to remove the old sender from your account.

<Image align="center" width="80% " src="https://files.readme.io/485f05b9c197c576df22442ea657c0082d201383eb66a4f898474d8efaaeaf10-image31.webp" />

If you select the **Leave without sender** option, the system cannot send these messages until you specify a new sender.

<Image align="center" width="80% " src="https://files.readme.io/7e108803b913fd1a65cbec6502e9bcff1dd0e439eaa74421a0a0de86d17b111d-image22.webp" />