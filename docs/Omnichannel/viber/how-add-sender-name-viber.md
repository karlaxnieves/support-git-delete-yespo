---
title: Adding a Sender Name
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding a Sender Name | Yespo Guide
  description: >-
    You need to register a sender name to be able to send Viber messages. Learn
    how to create a new sender name or add an already existing sender.
  robots: index
next:
  description: ''
---
Before starting [Viber campaigns](https://docs.yespo.io/docs/viber-messages-creation), you need to register a sender name from which the campaign will be sent.

In Yespo, two options exist for registering a sender name:

1. Creating a new sender name.
2. Adding an existing sender.

## Creating a New Sender Name

Use this option if you haven't registered a Viber sender before. In this case, you can create it in your Yespo account.

1. Go to the **Pricing plans** tab on the main page of your profile.

<Image align="center" width="80% " src="https://files.readme.io/53ba8a46601d5931023dc2b047e77315d2134776b8e765d9ac9e74971397fadb-adding-a-sender-name-viber-01.webp" />

2. Select the **Viber** tab, expand it, and click **Apply for adding**.

<Image align="center" width="80% " src="https://files.readme.io/5d20487b995ef94799549af809671ca71b3808bede6451a6dbf5523a983cd024-adding-a-sender-name-viber-02.webp" />

3. Send a request.

<Image align="center" width="80% " src="https://files.readme.io/44a55632ea873a9824fe604eb706d6b78d5ad547a2c69937f82a9284f6eef834-adding-a-sender-name-viber-03.webp" />

The sales department will contact you and provide information on further actions.

You can find out the cost of a monthly subscription in your Yespo account or send a request to [sales@yespo.io](mailto:sales@yespo.io) 

The money remains in the account and can be used to pay for messages after connection.

Click **Show pricing plans for all countries** to see pricing by country.

<Image align="center" width="80% " src="https://files.readme.io/763b900ad73613449a6af3484e91387f19205b088cc41ae04227880d5aceb67d-adding-a-sender-name-viber-04.webp" />

> 📘 Note
>
> * The registration term of the sender's name can take 7 to 30 days.
> * You can’t use [SMS Sender ID](https://docs.yespo.io/docs/sms-sender-id) to send Viber messages.
> * Sender name registration for Viber, as well as for SMS, is free. There is no additional fee for using the sender's name in the campaign.

## Adding an Existing Sender

Processing allows you to send messages via the service provider you work with. 

You can find out the prices [here](https://yespo.io/viber-prices).

1. In your profile, go to **Settings → Senders → Viber**.

<Image align="center" width="80% " src="https://files.readme.io/948e906be5f593ab1f080269080ee44e18ee8e66619d2e44c38f4f99ece75627-adding-a-sender-name-viber-05.webp" />

> 📘 Important
>
> To add a sender, you need to be a current customer of one of the following Viber service providers:
>
> * GMS Hyber
> * Infobip
> * TurboSMS
> * Kyivstar
> * Omnicell
> * Messaggio
> * SMS Club
> * SMSBAT
> * Streamtools
> * Vodafone
> * Intel Telecom
> * Decision Telecom

<Image align="center" width="80% " src="https://files.readme.io/d0866ef30c295d9e83e8b111f7a0f4a381e3c3f78b5c59bd1d1f57ca5282d030-viber_list.png" />

If you have a different service provider, please contact [support@yespo.io](mailto:support@yespo.io). 

2. Click **New sender**.

<Image align="center" width="80% " src="https://files.readme.io/54ce47f0fca47472edf1e351f5a7280456da57fec50e8d87983ddc42b6c21d3f-adding-a-sender-name-viber-06.webp" />

3. Select the **I’ve already contracted a Viber service provider and have a registered sender** option and specify the provider you work with.

<Image align="center" width="80% " src="https://files.readme.io/d0433446e242d0b1422b8d26b6c46506d441f6910e4338e798e39e691de89e18-adding-a-sender-name-viber-07.webp" />

If you select the **I want to register a new sender** option, the system will offer to do it via Yespo.

## Provider's Technical Settings Parameters

> 📘 Important
>
> The sender name in technical parameters is the name you received when registering with your service provider. This name is case-sensitive.

<Image align="center" width="80% " src="https://files.readme.io/661b5689f07a06aee9400f2a99b859fd15d452e7b55dcfa8bb72ddc95ae67b52-adding-a-sender-name-viber-08.webp" />

### 1. GMS Hyber

1. Enter the data:

* Sender name.
* Login, password, URL, timeout, Alpha name (required if the recipient has not received the Viber message, and you use the SMS forwarding function).

> 📘 Important
>
> Your provider needs to add the IP addresses `52.210.222.17,52.16.166.210` to the IP allow list.
>
> Please contact your provider.

2. Click **Done**.

> 📘 Advice
>
> Use [Yespo tags](https://docs.yespo.io/docs/how-add-tags) so that when uploading reports from GMS Hyber, you can quickly analyze how many messages of a specific type were sent: collecting feedback, installing an application, etc. If you use more than one tag in a message, they are substituted to the report separated by commas: `tag=tag1`,`tag2`,`tag3`.

### 2. Infobip

1. Enter the data:

* Sender name.
* Login and password are taken from the Infobip account.

> 📘 Important
>
> To get the open rate, contact Infobip and ask to add the link to the webhook in your account. Without the added link, the open rate will equal the click rate.
>
> `https://esputnik.com/dlr/v1/infobip/status`

2. Click **Done**.

### 3) TurboSMS

1. Enter the data:

* Sender name.
* Authorization token: copy it from the API settings in the TurboSMS account. 

2. Click **Done**.

### 4) Kyivstar

1. Enter the data:

* Sender name.
* Login, password, and source are taken from the Kyivstar account.

2. Click **Done**.

### 5) Omnicell

1. Enter the data:

* Sender name.
* Login, password, and sender ID are taken from the Omnicell account.

> 📘 Important
>
> Add the handler URL in the Omnicell account settings to configure status retrieval. The handler URL to which the statuses will be sent is: `https://esputnik.com/dlr/v1/omnicell/status`.

2. Click **Done**.

### 6) Messaggio

1. Enter the data:

* Sender name.
* Login, password, and bulk login are taken from the Messaggio account. 

> 📘 Important
>
> Add the handler URL in the Omnicell account settings to configure status retrieval. The handler URL to which the statuses will be sent is: `https://esputnik.com/dlr/v1/messaggio/status`.

2. Click **Done**.

### 7) SMS Club

1. Enter the data:

* Sender name.
* Login, password, and sender name are taken from the SMS Club account.

2. Click **Done**.

### 8) SMSBAT

1. Enter the data:

* Sender name.
* Login.
* Password.
* Alpha name.
* Timeout.

2. Click **Done**.

### 9. Streamtools

1. Enter the data:

* Sender name.
* Login.
* Password.

2. Click **Done**.

### 10. Vodafone

1. Enter the data:

* Sender name (can be any, as it is displayed only in the Yespo account).
* Login
* Password
* Distribution ID — Sender ID from your Vodafone account. Message recipients will see the sender name corresponding to this ID. Please note: Distribution IDs for SMS and Viber are different.

> 📘 Important
>
> Vodafone does not track the **Opened** message status, so the **Clicked** and **Opened** status numbers in reports will be the same.

### 11. Intel Telecom

Enter the data:

* Sender name: You can find this name in the **Senders**menu in Intel Telecom.
* User name: Your login name to the Intel Telecom account.
* API key: You can create API keys in Intel Telecom in **Developers → API key**.
* IM sender: See the Intel Telecom [API documentation](https://sms.intel-tele.com/cabinet/dev/api/viber/http/).

### 12. Decision Telecom

Parameters for sender setup:

* Sender name
* Authorization token — key from Decision Telecom account in `BASE64` format
* Alpha-name

To connect Decision Telecom, submit a request at [support@yespo.io](mailto:support@yespo.io).

2. Click **Done**.

After registration, you’ll see a confirmation:

<Image align="center" width="80% " src="https://files.readme.io/bb05de9b7327edb8d27ffe0a9d232e3d51a931f79c1852b6891c27930ff065d2-adding-a-sender-name-viber-16.webp" />

> 📘 Note
>
> The fee for sending one message is current at the time of publication of the article; the data may change.

The added sender will be displayed in the general list with the **Available** status.

<Image align="center" width="80% " src="https://files.readme.io/e7081c7477e5829945ad2a313089d3627fb2984a5ac8255c00397daaf067366c-adding-a-sender-name-viber-17.webp" />

## Deleting a Sender

> 📘 Important
>
> Before deleting a sender, you need to create or select another one, otherwise, you will be unable to send messages.

To delete a sender: 

1. Go to your profile  → **Settings → Senders**. 
2. Select the Viber tab and click the trash icon at the right-hand side of the sender name you wish to delete. 

<Image align="center" width="80% " src="https://files.readme.io/d082d0f77bfc6c7cf1df8f33b57728fcba0a31c7f0d9e6c0661de24a6216c969-adding-a-sender-name-viber-18.webp" />

3. Select **Delete** on the dialog window.

<Image align="center" width="80% " src="https://files.readme.io/a8eef5dcc630ca2604e4c65df8e86541a63a9d4c1a79b9b9c619c3f4276e8eed-adding-a-sender-name-viber-19.webp" />

## Changing a Viber Sender

To change a sender in existing Viber messages:

1. Go to **Messages → Messages → Viber** and select Viber message.

<Image align="center" width="80% " src="https://files.readme.io/7cfc65608df4d5c08e9da6e50819f9b9fc449d28f9f0296481992d391be77ab0-adding-a-sender-name-viber-20.webp" />

2. In the **Main settings** section, expand the dropdown list below **Sender** and select another sender for this message from the list.

<Image align="center" width="80% " src="https://files.readme.io/d38089345c34b4a48225d9bc590c0c5ba70b249524213af8c89c21f92e570317-adding-a-sender-name-viber-21.webp" />

## Sending SMS if there is no Viber

All providers except Kyivstar allow you to automatically send SMS to contacts who do not have a Viber account. To do this, you need to activate the corresponding option in the Viber message editor. The sender of such SMS can only be the same as for Viber campaign.

<Image align="center" width="80% " src="https://files.readme.io/77958f69d42c3605c5181a15310a5e9e23aaeee3bec2b96fb0bda65e13d0332b-send-sms.webp" />

> 📘 Note
>
> If your account does not have the **Send SMS if Viber is not delivered** option, please send a request for activation to [support@yespo.io](mailto:support@yespo.io).