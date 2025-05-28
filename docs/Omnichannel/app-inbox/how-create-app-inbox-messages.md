---
title: Creating App Inbox Messages
excerpt: After completing all settings, you can proceed to create App Inbox campaigns.
deprecated: false
hidden: false
metadata:
  title: Creating App Inbox Messages | Yespo Guide
  description: >-
    To send App Inbox messages, obtain an authentication token, configure the
    App Inbox for your platform, and then create and customize messages with
    various settings like personalization, links, and images before testing and
    launching campaigns.
  robots: index
next:
  description: ''
---
To send App Inbox messages to your customers, you first need to get an authentication token and configure App Inbox for a [website](https://docs.yespo.io/docs/how-to-set-up-integration-for-app-inbox) or [mobile app](https://docs.yespo.io/docs/app-inbox-for-mobile-apps).

After completing all settings, you can proceed to create App Inbox campaigns.

## Creating a New Message

Go to *Messages → Messages → App Inbox*. Click the *New App Inbox* butto&#x6E;*.*

<Image align="center" width="80% " src="https://files.readme.io/3b59a1258e330bed7a2d17b1f3c861673b607bbe407f5019d1b151394f54a681-new-appinbox-01.webp" />

### Main settings

Fill in the following fields:

1. *Name*. The system name that the recipient will not see.
2. *Title*. Brief information about main content message.

<Image align="center" width="80% " src="https://files.readme.io/787895149ec1c3f943940983cdef459037e65f007af997d71dab73a7cff8f557-update-appinbox-en-01.webp" />

3. *Text*. The main content of the App Inbox. In the text formatting menu, you can work on the text styles, lists, links and check the number of symbols in your message.

<Image align="center" width="80% " src="https://files.readme.io/38fc6d2d54773955bd1b61f6d23644cfef95dbcbd87357c80a9dd7a0b53eb75b-App-Inbox-message-PM.webp" />

> 🚧 Important
>
> If you apply text styles for an *app inbox* message, you will receive the message in the HTML format. You will need to parse the HTML message to display it correctly in the mobile app.

Use emojis in the title and text fields to improve interaction and capture users' attention.

<Image align="center" width="80% " src="https://files.readme.io/f37568009f80c843d5e6705f6d7336ea1db4e8f9882e9ec093ce8315daeb5d89-update-appinbox-en-04.webp" />

> 📘 Note
>
> One emoji takes up two characters. Keep this in mind when creating messages.

4. *Personalization*. Use the dynamic variables to add a name, city, bonuses or any personal data available in the [user profile](https://docs.yespo.io/docs/user-profile). Click on the *Personalization* icon in the *Text* or *Title* field to select data.

<Image align="center" width="80% " src="https://files.readme.io/003372ad339d7417286de7f061dfdb60d57b71bf8d60ff56bdc93eb468c04941-update-appinbox-en-03.webp" />

5. *Link.* The URL of the page to which the recipient should go when clicking on the body of the message (place without text links). Activate the switcher if the link should be opened in a new tab.

<Image align="center" width="80% " src="https://files.readme.io/68c36caf28c66bc21f4e19d81bc61b811dd9fa1e6fea7138d3a8977b7b166fa6-update-appinbox-en-05.webp" />

Link settings in App Inbox messages are similar to those in email. You can enable or disable URL tracking, UTM tags, and add custom tags.

To customize the link in the App Inbox, click on the gear icon in the link field ([learn more about UTM tag settings](https://docs.yespo.io/docs/how-transfer-utm-parameter)).

<Image align="center" width="80% " src="https://files.readme.io/597eefb16043c7a5df172d0ae3f2709566c4af70c9fd35a29a2ebf2a56da3c19-update-appinbox-en-06.webp" />

6. *Image*. Add a logo for more brand awareness. Upload JPEG, PNG or GIF file up to 2 MB. You can also use a [variable](https://docs.yespo.io/docs/introduction-to-velocity) or a link to the image. Use only the `https` protocol for direct references in expressions.

<Image align="center" width="80% " src="https://files.readme.io/fae733802d33c7a47ed030bf6ae41e576f3ffa04d72fa867dff816338ccdcdd2-app-inbox-image.webp" />

> 📘 Note
>
> You can edit the image directly in the editor when uploading (if it does not meet the requirements) or after uploading (the *Edit* button). After editing, the image is saved in PNG format.

<Image align="center" width="80% " src="https://files.readme.io/a8123ecedf1f87a40637b0d22fc00923ccb457b6c0d6edd415b24961ffd6dc35-update-appinbox-en-07.webp" />

7. *Tags*. Select tags from the list or enter a new one and click *Enter*. Use [tags](https://docs.yespo.io/docs/how-add-tags) to filter search results and set [campaign frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy).

<Image align="center" width="80% " src="https://files.readme.io/69768ba6ec23e05d4b192fecc76b1c096674ef1841982538e735692a0d8f6ef7-update-appinbox-en-08.webp" />

### Additional settings

Fill in the following fields:

1. *Custom data.* You can create App-Inbox messages using custom data in JSON format. If custom data is used in a [multilingual message](https://docs.yespo.io/docs/creating-multilingual-messages), it can be applied to all language versions. To do this, activate the *Use custom data from the default language version for all versions* switcher.

<Image align="center" width="80% " src="https://files.readme.io/c27c86793c737029b4efdc31b1dde21f1ce40ceb7d46d41d3457f5d37ae0c2b5-app-inbox-add-set-001.webp" />

If the switcher is disabled, different custom data can be used in each language version

Also, you can use dynamic variables to add data into the ***Custom data*** parameter: message name, first name, city, and so on. Click on the personalization icon and select the required.

2. *Subscription categories*. Manage [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) to send messages to your contacts based on their preferences.

3. *Time to Live (TTL)*. TTL — the period after which the message will not be displayed, even if it's delivered and read. By default, it’s 1 day, but you can select other options.

<Image align="center" width="80% " src="https://files.readme.io/16c72559bf1b483230a679afbe24a2340e84223b18540e5bcf1a5da5223ef97b-app-inbox-add-set-002.webp" />

### Multilingual version (*optional*)

In our platform, you can create a multilingual version of any message. Click the globe icon in the top panel, specify the default language and add language versions. Fill each version with the content in the corresponding language. You can switch between versions within one template in one click.

<Image align="center" width="80% " src="https://files.readme.io/40db12e78d57c3a3c263417fb94f105163d170bbd549a93bad9d137a3e9eca65-appinbox009.webp" />

[Learn more about multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

## Testing Message

1. Test the messages by clicking the *Test* button on the top panel.

<Image align="center" width="80% " src="https://files.readme.io/fd24ff2b76263e77a0825d08c74050174523da5108b79f4f273fab89df86c7f7-App_Inbox_9.webp" />

2. You will see a popup window for sending a test App Inbox where you'll need to enter any customer identifier associated with your account.

<Image align="center" width="80% " src="https://files.readme.io/adc703d0c803e9b9a1893f9f118835677a37b57fb5240e2368d21546a1736b04-appinbox8.webp" />

If done correctly, App Inbox will be displayed in your Yespo account.

## Creating Campaign

1. Click on the *Create campaign* button.

<Image align="center" width="80% " src="https://files.readme.io/14598a4adb81c600b776f2bd866979d7b9aed3866b5caac3c55e16f657266b89-App_Inbox_10.webp" />

2. In a popup window, choose segments or contacts for the campaign. Click *Go to campaign*.

<Image align="center" width="80% " src="https://files.readme.io/4e1d55b17a940243f56011123de9ebeff6a906890ec37e471f28ad9c16352c6a-image010a.webp" />

3. On the general checkout page:

* In the *Segments* section, click *Recalculate contacts* to see the total number of contacts that will receive the notification. You can also edit segments or select new ones.

<Image align="center" width="80% " src="https://files.readme.io/190c8a256248e164d2a3e279fd045d4fa73c79c251867c281c3c26bdb528df1c-image011.webp" />

* See all the necessary information for verification: *Name, Subscription categories, Message activity time, Link*. You can see how the App Inbox will look.

<Image align="center" width="80% " src="https://files.readme.io/88fd56021c228b47fbbb516b4739155829ee1f135b383d6bcd9d286b8fbe8107-appinbox-campaign-en.webp" />

* In the *Send options*, you can set the batching. Click the *Start immediately* button to launch the campaign. For a delayed start, select the *Schedule* button and set the date and time of sending.

<Image align="center" width="80% " src="https://files.readme.io/0ae41b8e269dbe975e2aa63e3b555b56c88399538e0a8f46820543180aa2b09a-App_Inbox_12a.webp" />
