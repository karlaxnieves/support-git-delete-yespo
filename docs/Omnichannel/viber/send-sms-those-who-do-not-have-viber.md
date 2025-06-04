---
title: Automatically Sending SMS to Contacts without Viber
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Automatically Sending SMS to Contacts without Viber | Yespo Guide
  description: Learn how to automate sending SMS for non-Viber users
  robots: index
next:
  description: ''
---
To know if a contact uses Viber, send them a Viber message. 

If Viber is not linked to the number, the messages fall into errors, and the report shows the following cause for non-delivery:

<Image align="center" width="80% " src="https://files.readme.io/30384577450643f09b996b9651f8096a3a756f40ef73d0782d18a314d2573bc7-Contacts_without_Viber.webp" />

To notify such a subscriber of important information, for example, about an order, add the following blocks to your chain in the workflow:

* [Timer](https://docs.yespo.io/docs/time-blocks#timer);
* [Delivered?](https://docs.yespo.io/docs/blocks-description-conditions-group#delivered);
* [SMS](https://docs.yespo.io/docs/message-blocks).

End each of the branches with the **End** block.

<Image align="center" width="80% " src="https://files.readme.io/7067a04a406497e6dc32832e51aae69af90ad6a47fb1f531a555d5c74ff3a201-automatically-sending-sms-to-contacts-without-viber.webp" />

In the timer, specify a time interval longer than the message time to live (**TTL**) set in the message editor.

<Image align="center" width="80% " src="https://files.readme.io/196aa13bcec9d879263e9ee089fd984ed259bb72e8a8cfee58830c01e26ef6d7-image1.webp" />

All numbers to which Viber messages could not be delivered will fall into errors after TTL expires. After the workflow timer expires, contacts who do not receive Viber will go by the No branch and receive SMS.

If the TTL exceeds the timer's time, the subscriber can receive both Viber and SMS.

> 📘 Note
>
> If you use the services of a [Viber provider](https://docs.yespo.io/docs/how-add-sender-name-viber#adding-an-existing-sender) (except Kyivstar), you can automatically send SMS to contacts who do not have a Viber account. To do this, activate the appropriate option in [additional message settings](https://docs.yespo.io/docs/viber-messages-creation#additional-settings) and enter the SMS text.