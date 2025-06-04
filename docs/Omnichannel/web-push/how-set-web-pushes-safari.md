---
title: Setting Up Web Pushes for Safari
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Set Up Web Pushes for Safari | Yespo Guide
  description: >-
    Learn how to set up and configure web push notifications for Safari browser.
    Step-by-step guidelines from Website Push ID registration in the Apple
    Developer Program to notification settings in the system.
  robots: index
next:
  description: ''
---
Safari Push Notifications are triggered remotely using Apple Push Notification service (**APNs**), even when the Safari browser isn’t running. Web pushes work just like app push notifications. To set up web pushes for Safari, you need to have an <a rel="nofollow" href="https://appleid.apple.com" target="_blank"> Apple account </a>

<Image align="center" width="80% " src="https://files.readme.io/7beb3ccf1e3cb71711f4aed027ec5d57a3c629f3c3370ecb902cae278596ad3c-image11.webp" />

and a <a rel="nofollow" href="https://developer.apple.com/programs" target="_blank"> developer account </a>.

<Image align="center" width="80% " src="https://files.readme.io/951a176facf197eca1a4578b6c5cef7221c0133fb8ba41d8548f016867cf59ab-image28.webp" />

> 📘 Note
>
> Voluntary Application Server Identification (<a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/sending-web-push-notifications-in-web-apps-and-browsers" target="_blank">VAPID</a>) allows sending web pushes to Safari versions 16+. If you are using VAPID and don't need to send pushes to older Safari versions, you can skip the manual below.

## Step1. Registration of Web Push ID

1. In your developer account go to **Identifiers** and select **Website Push IDs**.

<Image align="center" width="80% " src="https://files.readme.io/5eaceb81218c406dd293e5a549d520f198c763872b2d1168914ba4e537a21f5c-safari-3.webp" />

2. Select **Website Push IDs** and click **Continue**.

<Image align="center" width="80% " src="https://files.readme.io/d7c0a16fc878555776ffaf7897ee2b80b9c92319ce4063eb6c3542370c51f2b0-safari-4.webp" />

3. Fill in **Description and ID** fields, and click **Continue**.

* **Description**. Your service name for the Provisioning Portal which labels your Website Push IDs with a more human-readable description.
* **Identifier**. Your unique reverse-domain string that must start with web (for example, web.com.example.domain).

<Image align="center" width="80% " src="https://files.readme.io/b53681b375894830c01608f61aa0d95203e4dd79d03c1f2a48f1d8b4ef80b5fc-safari-5.webp" />

The new ID will appear on the Web Push IDs list.

<Image align="center" width="80% " src="https://files.readme.io/9b5ee3f168c7bfcf48568f1ce8c895cba9ef11949346294106c8bd1d6d168e12-safari-6.webp" />

**Note.** Your certificate may be revoked by Apple if you violate any of the push notification service rules and provisions. Thus, you’ll be unable to send new notifications. In case of unauthorized violation, you can personally revoke your certificate at your developer account → **Certificates** → **Identifiers & Profiles**.

## Step 2. Certificate Request in Keychain Access for MacOS

1. Open Keychain Access. It's standard for all Apple devices. In the menu, choose **Certificate Assistant** → **Request a Certificate From a Certificate Authority**.

<Image align="center" width="80% " src="https://files.readme.io/97030ec5227feea78c7bf1fc88bf545a04a2cc18310de289ab27469892ae1a26-image23.webp" />

2. Fill in the **User's Email Address** and **Common Name** fields, and select **Saved to disk**.

<Image align="center" width="80% " src="https://files.readme.io/f32582ade296f1603a30ae696b0f0d91f4d89e6b3e4e1d6fe23e8afa6c3834c5-safari-8.webp" />

3. Click **Save**.

<Image align="center" width="80% " src="https://files.readme.io/ea426f02e5f941a9a626c85f40cb725e5ab03f9c3113199022856a9b5ad4c897-safari-9.webp" />

## Step 3. Certificate Generation

1. In your developer account, go to **iOS Certificates** and click **Create a certificate**.

<Image align="center" width="80% " src="https://files.readme.io/fc38e424a83d04cb7846fddb9bfd6fcbd4ea2a8cf4459f2f8148978f68e0661e-safari-10.webp" />

2. Choose **Website Push ID Certificate** and click **Continue**.

<Image align="center" width="80% " src="https://files.readme.io/6c06f8c1f4c326ee442441222d132349db8f48b10d1915515ca3a83353f0551b-safari-11.webp" />

3. Select the Website Push ID you’ve created and click **Continue**.

<Image align="center" width="80% " src="https://files.readme.io/96a9dac07a2e1b344b92914251a590fb39dd9a54ebc4582f21abce1e49d5a120-safari-12.webp" />

4. Upload a Certificate Signing Request.

<Image align="center" width="80% " src="https://files.readme.io/1e07420b70f13145e850ee68cc0276b8753beeb06cb061637636402d0beb3cc6-safari-13.webp" />

5. Download the certificate.

<Image align="center" width="80% " src="https://files.readme.io/55a8f877febc0b885ceca339f6a295c03f824a73283dcf7ee9c8a3ccb572cb6c-safari-14.webp" />

## Step 4. Certificate .p12 Export

1. Double-click the downloaded file. In opened **Keychain Access**, go to **My Certificates** and select the necessary certificate.

<Image align="center" width="80% " src="https://files.readme.io/af3fe9ea88bd9db985ac8c51f791ddedabb7ef721dac9c4d22470909f02cb7b4-safari-15.webp" />

2. Right click the certificate accordion and select **Export**.

<Image align="center" width="80% " src="https://files.readme.io/8366f12213763b1da587d478ee6a4b376e20e1dff3473293bd62281ca780fe38-safari-16.webp" />

3. In **File Format**, select **Personal Information Exchange format (.p12)**.

<Image align="center" width="80% " src="https://files.readme.io/38ed45bcf53bb2d2e21acdf6c51a481876ec2614cba3c053af8dae48b45a4a79-safari-17.webp" />

4. In the file generation window, you can add an additional password to the `.p12` certificate file.

<Image align="center" width="80% " src="https://files.readme.io/8d6dd7b8e74256542910905426b1829168f23f69a6e3b166574093477dd2dac9-safari-18.webp" />

You can leave these fields blank and click **OK**. Next, click **Allow** and enter your **Mac password** to export the certificate to your computer.

## Step 5. .p8 Certificate Download

The `.p8` extension is a text file with keys that are used to execute JWT content for APNs messages.

1. In your developer account, go to **Keys** and click **Create a key**.

<Image align="center" width="80% " src="https://files.readme.io/2c35bea9058f4e4c21c53018579061406327ae265729f3dbf3eefafb7e024ada-safari-19.webp" />

2. Select **Apple Push Notifications Service (APNs)**.

<Image align="center" width="80% " src="https://files.readme.io/18c9d8e2ff9670d298a0cd8423abd9daefeca2e607b651c75a7c4b3651be8f26-safari-20.webp" />

3. Register a new key.

<Image align="center" width="80% " src="https://files.readme.io/20a5b4ac6443ed4b67e98bcaf750f622da3ae1f5439fc379cc75dd4f1b326e98-safari-21.webp" />

4. Download the` .p8` certificate.

<Image align="center" width="80% " src="https://files.readme.io/f04ff873aae5457efa3a38df571802c7e09c6dbc09e1034524d5ce20b2847163-safari-22.webp" />

The new key will appear in the **Keys** list.

<Image align="center" width="80% " src="https://files.readme.io/75209bca19da3232c63b08e00abdb0953af363d36f54c89f6127101cf2c791ce-safari-23.webp" />

## How to Set Up Safari Web Pushes in our CDP

1. In your personal account, go to **Settings → Web Push**.

<Image align="center" width="80% " src="https://files.readme.io/ae1096e853bdcd15069698ea09d1ed907e1db38896f9a0fb006b1dc31a783612-settings.webp" />

2. If you add Safari to the existing website, click on its link (**1**). If you don't have a website, click **+Connect website** (**2**).

<Image align="center" width="80% " src="https://files.readme.io/9b294933ed747281225018606067e1eaea7419da569722d596b594ad60dc6fe3-settings2.webp" />

For a new website, [fill in all the fields](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications). If the site already exists, fill out **For Safari**.

3. In the **Legacy browsers support** section, upload files `.p8` and `p.12`.

<Image align="center" width="80% " src="https://files.readme.io/05a05a760a3d1382fd4b5516ef8539ad774dfc66b3fe98128f4d683153fb2d36-website-web-push-integration.webp" />

4. In the **Key ID** field, insert the corresponding ID from your developer account → **Keys** → **All**.

> 📘 Note
>
> Safari icons should be not less 256x256px, `JPEG`, `PNG`, up to 200 KB. Images should be square. Unlike other browsers, the icon for Safari is installed once and cannot be changed. If you change the icon, old subscribers will receive notifications with the old image, and new ones with the new one.

<Image align="center" width="80% " src="https://files.readme.io/14db377cf8e509e4d98fe03c66fd661eae2fe06a389e6b2acbdc3bb9e9bc87b2-image25.webp" />

Once you’ve saved all the settings, enter your website in Safari and see a web push permission prompt.

<Image align="center" width="60% " src="https://files.readme.io/2fb451a4cde3632076191f9ace5adc3a759505b260bab65f0198e632191ff15a-image17.webp" />