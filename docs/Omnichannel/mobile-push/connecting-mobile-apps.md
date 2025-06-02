---
title: Connecting Mobile App
excerpt: Learn how to implement push notifications on Android and iOS devices.
deprecated: false
hidden: false
metadata:
  title: Connecting Mobile Apps with Yespo | Yespo Guide
  description: >-
    Detailed instructions on how to create connection between your mobile app
    and Yespo
  robots: index
next:
  description: ''
---
Before you start sending push notifications in your mobile app using our CDP, you have to connect the mobile app to Yespo.

> 📘 Note
>
> In the Pricing plan section, select the plan that best suits your organization based on the available number of mobile app tokens in your contact list.

To connect your mobile app with Yespo:

1. Go to **Account  → Settings**.
2. Click **Mob Push** in the left-hand side menu.
3. Click **Connect mobile app** on the **Mobile apps** page.

<Image align="center" width="80% " src="https://files.readme.io/8b56cc70a6a94752cb8a500285e9cd930c1719b64258e449fd4964b7459c3fd5-image.webp" />

> 📘 Note
>
> We recommend creating applications with different API keys for the stage and prod environments to minimize risks and ensure high quality of the final product before release.

## Step 1. App Name

Type the application name in the **Application name** field.

<Image align="center" width="80% " src="https://files.readme.io/870f0e2c7050334033f80ea2f74fd5492bf30c54a13a4378b34ce1028f4dcc22-mob-push-1.webp" />

## Step 2. Platform

Select whether you need to set up Android and iOS mobile notifications.

<Image align="center" width="80% " src="https://files.readme.io/f96b684f8dda935da6cc66bbae9243b91686478348d326fed8a1869f9137a542-mob-push-2.webp" />

## Step 3. Notification Service

Depending on your choice in Step 2, you will have the following setting options:

1. Firebase Cloud Messaging (**FCM**) for all platforms. 
2. Apple Push Notification Service (**APN**) for iOS.
3. FCM for Android and APN for iOS.

### FCM

1. Click **Upload file**.

<Image align="center" width="80% " src="https://files.readme.io/f783267d6a3aea16e0e37696ba1b714b25c0688b0566befe79c05937ded7dacb-mob-push-3.webp" />

2. Click on the field and upload the Google Firebase private key JSON file from your computer, or drag your JSON file and drop it in the field.

<Image align="center" width="80% " src="https://files.readme.io/776f770aba17a273d847c07b6fbcb738a0e033fdf9ede963aef2f07dd37d5821-mob-push-4.webp" />

> 📘 Note
>
> See the <a rel="nofollow" href="https://firebase.google.com/docs/admin/setup#initialize-sdk" target="_blank"> Firebase documentation </a> for details on how to generate a private key file in Firebase.

3. Click **Done** on the top right of the window.

### APN

Select one of two options:

* Using tokens

See the Apple Developer documentation for details on how to <a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns" target="_blank"> establish a Token-Based Connection to APNs</a>.

* Using certificates

See the Apple Developer documentation for details on how to <a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns" target="_blank"> establish a Certificate-Based Connection to APNs</a>.

#### Using tokens

1. Click **Upload file**.

<Image align="center" width="80% " src="https://files.readme.io/20b80805af7f386ff60b353bc332b9da5d7bad4486412fb12d94c1eee568bb8a-mob-push-5.webp" />

2. Click on the field and upload the Apple push notification authentication key in `P8` format from your computer, or drag your `P8` file and drop it in the field.

<Image align="center" width="80% " src="https://files.readme.io/42cec296a2edb612ed3da8ca54967e4bf48b629f2c4465bebdcbc2f0aecfa59e-mob-push-6.webp" />

3. Enter the following in the corresponding fields:

* **Key ID** — the 10-character key identifier you obtained from your developer account.
* **Team ID** —  the issuer key, the value for which is the 10-character Team ID you use for developing your company’s apps. Obtain this value from your developer account.
* **Topic** — a unique identifier that causes the notification to arrive in the corresponding app on a user's device. Most often, the **Topic** is the app bundle identifier.

<Image align="center" width="80% " src="https://files.readme.io/0e35b084c2a55328f710d0b2c01e08d9ba88824424665f8c2af15aafb8c582c6-mob-push-7.webp" />

<a rel="nofollow" href="https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html" target="_blank"> Read more about these fields ></a>

4. Click **Done** on the top right of the window.

#### Using certificates

1. Click **Upload file**.

<Image align="center" width="80% " src="https://files.readme.io/b0dd4013bbfdf2d66770f63deea60ea1a02ef78954014a333659dbe33402c279-mob-push-8.webp" />

2. Click on the field and upload the Apple certificate file in `P12` format from your computer, or drag your `P12` file and drop it in the field.

<Image align="center" width="80% " src="https://files.readme.io/62a73e508302cdb05f747fab74e2895532f1df25bc18d329f6ccdcfe1ba6a0d9-mob-push-9.webp" />

3. Enter the **Password** and **Topic** in the corresponding fields.

<Image align="center" width="80% " src="https://files.readme.io/1f81f00ac69126f4667a73fb88c15c594656935278e8f3f1ec9f6a9447e86b9e-mob-push-10.webp" />

<a rel="nofollow" href="https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html" target="_blank"> Read more about these fields ></a>

4. Click **Done** on the top right of the window.

If everything is configured correctly, you will see a corresponding notification.

<Image align="center" width="80% " src="https://files.readme.io/4efe087fa478d11fc4c6220c9a182ea40890a3152e56db5481a2ea93c7ea865d-correct.webp" />

If there are errors in the settings, you will see a list of them and a link to recommendations for fixing them.

<Image align="center" width="80% " src="https://files.readme.io/540f2ce66703f9a9bdbbe3f2649b9e5790dee17a71dd1622dc4ac8cf190ac3f7-fix.webp" />