---
title: Creating a Web Push Notification
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating a Web Push Notification | Yespo Guide
  description: >-
    A web push notification is a message that shows up in the open browser on
    desktop and mobile. Learn how to create and send browser push notifications
    in simple steps.
  robots: index
next:
  description: ''
---
Setting up Web Push includes:

1. Creating a Google Project to collect tokens for web push notifications.
2.  Adding a website to your Yespo account.
3. Configuring permission request prompt.

[See details >](https://docs.yespo.io/docs/web-push) 

After finishing all the necessary settings, you can create a Web Push campaign. 

## Creating New Web Push Notification

Go to **Messages** → **Messages** → **Web Push**. Click the **New Web Push** button

<Image align="center" width="80% " src="https://files.readme.io/d70fef8a000d29cfa80680c80c41fcdbc50e851e237c37a4cf141e2686f74fb7-new-webpush-01.webp" />

### Main Settings

Fill in the following fields:

1. **Name**. The system name that the recipient will not see.
2. **Title**. Stick to no more than 30 characters for correct display on different devices.
3. **Text**. The main content of the Web Push. The optimal number of symbols is 45-70.

<Image align="center" width="80% " src="https://files.readme.io/bf57018cc31dc5bd2d26c69815aefb75a1c4fe72d928158662932a7ad6ce24c0-webpush-1.webp" />

Use emojis in the title and text fields to improve interaction and capture users' attention.

<Image align="center" width="80% " src="https://files.readme.io/24f39c463fba44934c5ca5133a9fe68fc4f11331e681a890cee26a7df9daba67-web-push-emoji-en-01.webp" />

4. **Personalization**. Use the dynamic variables to add a name, city, bonuses or any personal data available in the [user profile](https://docs.yespo.io/docs/user-profile). Click on the Personalization icon in the **Text** or **Title** field to select data.

<Image align="center" width="80% " src="https://files.readme.io/b1ee505c1a5a5473b27abf1495ded365f25a649b556c6595d5928933d7feb979-webpush-2.webp" />

5. **Link**. Add the landing page URL.

<Image align="center" width="80% " src="https://files.readme.io/9b74c4b562670627a423ca0fc47bcddbea474c16ec70d2290e9c89d9a7535f21-webpush-3.webp" />

6. **Logo**. Upload `JPEG` or `PNG` file up to 128 KB. You can also use a [variable](https://docs.yespo.io/docs/introduction-to-velocity) or a link to the image. Use only the `https` protocol for direct references in expressions.

<Image align="center" width="80% " src="https://files.readme.io/a1bf25b4d2864c13bb149ac824b596faadc2b899be283da79e73dc5334c12830-webpush-4.webp" />

7. **Tags**. Select tags from the list or enter a new one and click **Enter**. Use [tags](https://docs.yespo.io/docs/how-add-tags) to filter search results and set [campaign frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy).

<Image align="center" width="80% " src="https://files.readme.io/460ee5fe8ef5b0fb83c129ace06e0e04f4f88cf2a1296f9db7727b0f78ddfdb0-webpush-5.webp" />

### Chrome Settings

Fill in the following fields:

1. **Big image**. Upload `JPEG` or `PNG` file up to **1.89 MB**. You can also use a [variable](https://docs.yespo.io/docs/introduction-to-velocity) or a link to the image. Use only the `https` protocol for direct references in expressions.

<Image align="center" width="80% " src="https://files.readme.io/ef3ba71c97f0055d10827eebd6ae8fa65d393aa1570354ad8f4dcb250fd95285-webpush-6.webp" />

> 📘 Note
>
> You can edit logo and big image directly in the editor when uploading (if it does not meet the requirements) or after uploading (the **Edit** button). After editing, the image is saved in `PNG` format.

<Image align="center" width="80% " src="https://files.readme.io/061378d7868fcd6e8c5f9b66c65a3d642bc8d0fb0ade261a6179fbe4f685d7f9-web-push-emoji-en-02.webp" />

2. **Button**. You can add one or two buttons with the following parameters:

* Title — the text on a button.
* Link.

<Image align="center" width="80% " src="https://files.readme.io/d0a84a373431d6fe481d5e4375b04b96d91562d324c8fa9121b743bd98f2de05-image07.webp" />

### Additional Settings

Fill in the following fields:

* **Subscription categories**. Manage [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) to send messages to your contacts based on their preferences.
* **Time to Live (TTL)**. TTL — the period after which the message will not be displayed if it has not been delivered by this time. By default, it’s 1 day, but you can select other options.
* **UTM tags**. [UTM tags](https://docs.yespo.io/docs/how-transfer-utm-parameter) are enabled by default. The switch activates the setting for all language versions when sending multilingual messages. You can manually add custom UTM tags to the message URL.

<Image align="center" width="80% " src="https://files.readme.io/6a7927d6b19a417f96d3728fbde324bc5706d7af31669d86cd1f0b52b5a00bb0-image08.webp" />

### Multilingual Version (optional)

In our platform, you can create a multilingual version of any message. Click the **Globe icon** in the top panel, specify the default language, and add language versions. Fill each version with the content in the corresponding language. You can switch between versions within one template in one click.

<Image align="center" width="80% " src="https://files.readme.io/af4c406e33c4026c7f59921fb9389588c253e58a206beaa663cfd5c5f041496b-image09.webp" />

[Learn more about multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

## Testing Message

Test the messages by clicking the **Test button** on the top panel.

<Image align="center" width="80% " src="https://files.readme.io/7b04350a2025f50f6d6711b943e2be6200581d638c6e35dca85bb00a7ffe93ec-image10.webp" />

## Creating Campaign

1. Click on the **Create campaign** button.

<Image align="center" width="80% " src="https://files.readme.io/b716d7513c5dfcaf75a857ed6b33da2d831caa8d734deec470b5bc1088c65a9e-image11.webp" />

2.  On the general checkout page:

* In the **Domain** section, select the domain you want to send the message to. If you want to send the campaign to all domains, select the appropriate option from the drop-down list.

<Image align="center" width="80% " src="https://files.readme.io/279417964b1c366627f662818c745885b1513a72002511877d69673f397b2be9-select_domains.webp" />

The message will be on the screen until the contact clicks on it or closes it.  You can activate the switcher to hide notification automatically.

<Image align="center" width="80% " src="https://files.readme.io/794fe4f5e67c92836a8f061dd0f41d9ce0b4e6711412b7c582f7c5dcc53009f7-hide_notification.webp" />

* In the Segments section, you can select segments to include or exclude from the campaign. 

<Image align="center" width="80% " src="https://files.readme.io/379d6f79daee41cf36f2974b8f039eea21a405170090e51fb547877a89f03a03-image15.webp" />

* See all the necessary information for verification: **Subscription categories**, **Message activity time**, **Links**, and **Button titles**.  You can see how the message will look on different operating systems:

  * Windows  – Chrome, Firefox browsers.
  * macOS – Chrome, Safari browsers.

<Image align="center" width="80% " src="https://files.readme.io/138b1f454d09798badb4fadab687afc5cc52f671c8bcf8d91d0a8ab829c24ba4-image12-new.webp" />

* In the **Send options**, you can set the batching. Click the **Start immediately** button to launch the campaign. For a delayed start, select the **Schedule** button and set the date and time of sending.

<Image align="center" width="80% " src="https://files.readme.io/0c250336eeefe45f640484f330f9283bc7fd31d29b5b8bb8c6c0e629cfd5de5b-image17.webp" />