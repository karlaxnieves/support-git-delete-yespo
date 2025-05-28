---
title: Creating SMS
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating SMS | Yespo Guide
  description: >-
    Read how to create a new message and set up the SMS campaign. Also you can
    test your SMS before sending.
  robots: index
next:
  description: ''
---
SMS is a high-precision customer communication channel. Additional targeting based on geography, interests, etc. allows for achieving maximum effect.

> 📘 Note
>
> To send SMS via the Yespo system, you first need to register the [SMS sender ID](https://docs.yespo.io/docs/sms-sender-id) or set [up SMS processing](https://docs.yespo.io/docs/setting-up-sms-processing).

After finishing all the necessary settings, you can create an SMS campaign.

## Creating New SMS

Go to *Messages → Messages → SMS*. Click the *New SMS* button.

<Image align="center" width="80% " src="https://files.readme.io/777ba6517883ec8b2ae711b7ec33d0adccbb698af51f18607518f2c5fbcebcca-new-sms-001.webp" />

### Main settings

Fill in the following fields:

1. *Name*.  The system name that the recipient will not see.
2. *Text*. The main content of the SMS.

<Image align="center" width="80% " src="https://files.readme.io/843aeadf87e7628ea6dc25ecc7666881140eafd9791c38d838de48aae6aaef28-image002.webp" />

Messages support the use of special graphic symbols — emojis.

<Image align="center" width="80% " src="https://files.readme.io/af3128c43cba24809fd92c3af23c091a1d9c20f519bc48634c8a64ce741d8c3e-sms-emoji-en.webp" />

> 📘 Note
>
> Some emojis are not supported — mobile operators replace them with question marks or remove the emoji and the text following it.

A list with unsupported emojis will appear if you add at least one of them to the message text.

<Image align="center" width="80% " src="https://files.readme.io/b41b00dc46b4cc5449d5480f7adcbd3edf9b7b33ee585c36f37b49f3cc607867-unsup-emoji-en.webp" />

> 📘 Note
>
> * One part of SMS contains 160 characters.
> * If the message contains at least one emoji, the maximum number of characters in one part of the message will decrease to 70.
> * One individual emoji takes up two regular letter characters.
> * Each part of the message is charged as a separate SMS when sent.

The message editor has counters for the characters and message part to help you control the message's length and calculate the campaign's cost.

<Image align="center" width="80% " src="https://files.readme.io/ebc1b2d08b36f958bf77c485bc18e349849102a572bfd981a6ba072e92172a6f-image03.webp" />

3\. *Personalization*. Use the dynamic variables to add a name, city, bonuses or any personal data available in the [user profile](https://docs.yespo.io/docs/user-profile). Click on the *Personalization icon* in the *Text* field to select data.

<Image align="center" width="80% " src="https://files.readme.io/9c69fa5ca1ae4952c49a6a21ecd98e1957ec0101046fbd924c753e411d2d96bf-image004.webp" />

4\. *Sender*. The *alpha name* or the *sender name* will be displayed to your subscribers while receiving messages. Sender name *Marketing* is set by default. We recommend using your own domain name, as the operator can change the public domain name. 

5. *Tags*. Select tags from the list or enter a new one and click *Enter*. Use [tags](https://docs.yespo.io/docs/how-add-tags) to filter search results and set [campaign frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy).

<Image align="center" width="80% " src="https://files.readme.io/216ee58bed8d0f0629763cf9310d94c08dd91bd3138bf370bce00ba432613342-image005.webp" />

### Additional settings

Fill in the following field:

* *Subscription categories*. Manage [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) to send messages to your contacts based on their preferences.

<Image align="center" width="80% " src="https://files.readme.io/5bc8de4127e869577d710fb5127ddd55564bdd05fa2eece6269d0072fa131b5a-image006.webp" />

### Multilingual version *(optional)*

In our platform, you can create a multilingual version of any message. Click the *Globe icon* in the top panel, specify the default language and add language versions. Fill each version with the content in the corresponding language. You can switch between versions within one template in one click.

<Image align="center" width="80% " src="https://files.readme.io/93f52d3f8f86a0097f5a5a5a8b0903b8abbfd68e3505637458360f72243e78f9-image009.webp" />

[Learn more about multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

## Testing Message

1. Test the messages by clicking the *Test* button on the top panel.

<Image align="center" width="80% " src="https://files.readme.io/7a7046a4cb2964d363460e8524af366c431b906d826358d679e8a53acece3b9b-image007.webp" />

2. In a pop-up window, enter a phone number or select it from the *Choose contact* tab and click *Send*. 

<Image align="center" width="80% " src="https://files.readme.io/141703a554daeb85f4db66e2b820ea2a077e0ac36ad05d3265ce071427c7b624-image08.webp" />

## Creating Campaign

1. Click on the *Create campaign* button.

<Image align="center" width="80% " src="https://files.readme.io/81271773c051b8e2d9ec62ff0a032ff9ab88f078adb7bffb6ac0c1806731a6c9-image010.webp" />

2. In a pop-up window, choose segments or contacts for the campaign and click on *Go to* campaign.

<Image align="center" width="80% " src="https://files.readme.io/610075e6d85d0ebca0d9a55228f621c4c53660ee5f3332838c808630b87f6829-image011.webp" />

3. On the general checkout page:

* In the *Segments* section, click *Recalculate contacts* to see the total number of contacts that will receive the notification. You can also edit segments or select new ones.

<Image align="center" width="80% " src="https://files.readme.io/09a58fcfe289c01e3f24716c496dc1354819d0945b301e05b797156278105c54-image012.webp" />

* See all the necessary information for verification: *Name, Subscription categories, Sender*. You can see how the SMS will look on different platforms (Android, iOS).

<Image align="center" width="80% " src="https://files.readme.io/65b816c3d85098343236ef7cea2cbd80d9bbf5d22f18a5f3fb23ee84ddf3599c-image013.webp" />

* In the *Send options*, you can set the batching. Click the Start immediately button to launch the campaign. For a delayed start, select the Schedule button and set the date and time of sending.

<Image align="center" width="80% " src="https://files.readme.io/503f6d74e1cddcd2be46cf670ad82cdb7f971f0e7399c81e9711f45684e3770c-image014.webp" />
