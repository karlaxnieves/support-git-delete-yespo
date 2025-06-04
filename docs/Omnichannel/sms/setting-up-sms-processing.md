---
title: Setting Up SMS Processing
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up SMS Processing | Yespo Guide
  description: >-
    The article provides a step-by-step guide to configuring and managing SMS
    processing.
  robots: index
next:
  description: ''
---
You can send SMS messages through your service provider using processing in our system. For that, you have to configure the sender settings in your profile.

## Configuring the Sender Settings

To configure SMS processing for registered senders:

1. Go to your profile → **Settings → Senders**.
2. Select the **SMS** tab and click the **New sender** button.

<Image align="center" width="80% " src="https://files.readme.io/26b693af0c056b29023ff25733a8b4ba4d40bff17e34fca5bf65ad647f8d38d1-senders.webp" />

3. In the slide-out window, select the **I’ve already contracted an SMS service provider and have a registered sender** option and select your service provider from the list:

* GMS Hyber
* Infobip
* TurboSMS
* Kyivstar
* Omnicell
* Textlocal
* Acemount Media
* Twilio
* SMSBAT
* Streamtools
* Vodafone
* Intel Telecom
* PROCONTEXT
* Decision Telecom

<Image align="center" width="80% " src="https://files.readme.io/c4bea4705ece450a94327174856d806670abbc603de61d5fd00ca9b8c270032a-sms_list.png" />

4. Enter the required technical parameters of your provider, as listed below:

### **GMS Hyber**

* Sender name
* Login
* Password
* URL
* Timeout

Use [Yespo tags](https://docs.yespo.io/docs/how-transfer-utm-parameter) so that when uploading reports from GMS Hyber, you can quickly analyze how many messages of a specific type were sent: collecting feedback, installing an application, etc. If you use more than one tag in a message, they are substituted in the report separated by commas: `tag=tag1`,`tag2`,`tag3`.

> 📘 Note
>
> Ask GMS Hyber to add the `52.210.222.17` and `52.16.166.210` **IP addresses** to the allowed list.

### **Infobip**

* Sender name
* Login
* Password
* Alpha-name

### **TurboSMS**

* Sender name
* Authorization token

> 📘 Note
>
> To receive the message status, add the following link in your TurboSMS cabinet:
>
> * `https://esputnik.com/dlr/v2/turbosms/status`

### **Kyivstar**

* Sender name
* Client ID
* Client Secret

> 📘 Note
>
> To receive the message status, add the following link in your Kyivstar cabinet:
>
> * `https://esputnik.com/dlr/v1/kyivstar/status`

### **Omnicell**

* Sender name
* Login
* Password

> 📘 Note
>
> To receive the message status, add the following link in your Omnicell cabinet:
>
> * `https://esputnik.com/dlr/v1/omnicell/status`

### **Textlocal**

* Sender name
* API key

Note

To receive the message status, add the next parameters in your Textlocal cabinet:

* **https\://** filed: `esputnik.com/dlr/v1/textlocal/status`
* **Port** field: 443

### **Acemount Media**

* Sender name
* Authorization token

> 📘 Note
>
> To receive the message status, add the next parameter for **Sms URL report** field in Acemount Media user account:
>
> * `https://esputnik.com/dlr/v1/acemount/status`

<Image align="center" width="80% " src="https://files.readme.io/edb888d98f452b4a93c3a155926f575c8ccb41864566a78a40a28b989e14cabc-am_settings_yespo.webp" />

### **Twilio**

* Sender name
* Account SID
* Authorization token

> 📘 Note
>
> To receive the message status, add the next parameters in your Twilio account:
>
> * `https://esputnik.com/dlr/v1/twilio/status`

### **SMSBAT**

* Sender name
* Login
* Password
* Timeout

### **Streamtools**

* Sender name
* Login
* Password

### **Vodafone**

* Sender name (can be any, as it is displayed only in the Yespo account).
* Login
* Password
* Distribution ID — Sender ID from your Vodafone account. Message recipients will see the sender name corresponding to this ID. Please note: Distribution IDs for SMS and Viber are different.

### Intel Telecom

* `Sender name`: You can find this name in the **Senders** menu in Intel Telecom.
* `User name`: Your login name to the Intel Telecom account.
* `API key`: You can create API keys in Intel Telecom in **Developers → API key**.

### PROCONTEXT

The provider supports message delivery **only to Moldovan phone numbers**. There are two types of messages:

* **Notifications** — important triggers that are sent around the clock and as quickly as possible. The content of notifications must be approved by the provider.
* **Marketing** — promotional messages sent only during business hours. Approval from the provider is not required.

Parameters for sender setup:

* Alias — alpha name;
* Partner’s ID — login;
* Password.

To connect PROCONTEXT, submit a request at [support@yespo.io](mailto:support@yespo.io).

### Decision Telecom

Parameters for sender setup:

* Sender name
* Authorization token — key from Decision Telecom account in BASE64 format
* Alpha-name

To connect Decision Telecom, submit a request at [support@yespo.io](mailto:support@yespo.io).

5. Click **Done**.

Now, you can proceed with creating and sending SMS messages. Read [this article](https://docs.yespo.io/docs/creation-sms) to learn more about it.

## Deleting a Sender

To delete a sender: 

1. Go to your profile → **Settings → Senders**. 
2. Select the **SMS** tab and click the **Delete** icon at the right-hand side of the sender name you wish to delete. 

<Image align="center" width="80% " src="https://files.readme.io/04f93bd35adfca7cb8e49dd821f793d94639e2890ab94d801c719b6b1a99ba22-delete.webp" />

3. On the dialog window, select **Delete**. The confirmation message appears for a short while.

Important

Before deleting a sender, you need to create or select another one, otherwise, you will be unable to send messages.

## Changing an SMS Sender

To change a sender in existing SMS messages:

1. Go to **Messages → Messages → SMS** and select an **SMS**.

<Image align="center" width="80% " src="https://files.readme.io/34cd454d659ec947fc64a24921da5337747afbb52fe0a70452f5324aa4792874-message.webp" />

2. In the **Main settings** section, expand the **dropdown list** below **Sender** and select another sender for this message from the list.

<Image align="center" width="80% " src="https://files.readme.io/19d864450cc89e797921fb64d0a2734d28872dee6d1819c7ff6776d66df634c2-change.webp" />