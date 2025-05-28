---
title: Setting Up Web Push Notifications on Your Website
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Web Push Notifications on Your Website | Yespo Guide
  description: >-
    Learn how to enable web push notifications on your website by installing a
    web push script and collecting web push tokens.
  robots: index
next:
  description: ''
---
> 📘 Note

> Web push token collection is only available for HTTPS protocol websites.

## Selecting a Subscription Type

1. Go to your account settings and select the *Web Push* tab.

<Image align="center" width="80%" src="https://files.readme.io/68d73681895767aaa85cc303efa13d2bf1735c2a1aafb142aecd6bf966122731-adding-website-to-account-001.webp" />

2. Select the subscription type:

* **Double Opt-in**. A double opt-in subscription. The advantage of this type is the ability to customize the appearance of the subscription and confirmation windows. In this case, a user will first see your customized window, and then the standard one.
* **Single Opt-in**. Allows users to subscribe with just one button click, without additional confirmation.

> ❗️ Note

> Google Chrome may block [intrusive subscription windows](https://yespo.io/blog/google-chrome-will-now-block-abusive-browser-notifications). To avoid potential limitations, select the *Double Opt-in* subscription.

<Image align="center" width="80%" src="https://files.readme.io/12cbbe1cc3b4e8b6427fe593301977def35a04418b7dabbc3daec3f8661f78b4-adding-website-to-account-002.gif" />

Click the *+Connect website* button, then select the subscription type if your account has existing subscriptions.

<Image align="center" width="80%" src="https://files.readme.io/2b1000461b1f003a87b0d0f9f84ab18bafd9efe44dabe3daef2baa248e705dad-adding-website-to-account-003.webp" />

## New Website Adding

After selecting the subscription type, fill in the required fields *Website URL* and *Website name*.

<Image align="center" width="80%" src="https://files.readme.io/de45eee066b8bbe17a31103977c6de3f5b4526b8694f0c5bbe845b628e2b12d0-adding-website-to-account-004.webp" />

## Service Worker Setup

*Service Worker* is a script that runs in the background on your device, even when you are not using the website or application.

The *Service Worker* configuration includes three fields (filled in automatically):

* **Path to the file** — the path to the directory on the website where the script file should be uploaded.
* **File name** — the name of the file containing the code (will be generated in the [Web Push Integration](https://docs.yespo.io/docs/how-send-web-push-notifications-website#web-push-integration) step.)
* **Scope** — the scope within which the Service Worker can interact with the website content. It defines on which pages or in which directories of the website this Service Worker will be active.

> ❗️ Important

> * When using a ***web push Service Worker*** together with a ***PWA (Progressive Web App) Service Worker***, it is necessary to separate their scopes to avoid conflicts. A typical setup is to place the *PWA Service Worker* in the root directory of the website and the *web push Service Worker* in any other directory.
> * The scope of the *web push Service Worker* is not limited to the pages where the script is active. It works on all pages of your website, even if they are not within the specified scope.

<Image align="center" width="80%" src="https://files.readme.io/25356e2c57f4e57db78e4f5875893d9ed32248ed666c61c52486a84d8f5dd90f-adding-website-to-account-25032025-02-yespo.webp" />

If you need to place the file in a different directory on the website, change the path to the Service Worker file.

> 📘 Note

> The file path and scope must have the same base path, starting and ending with a slash “/”. For example, if the path is `/push/reteno/`, then the scope must also start and end the same way, meaning it should also be `/push/reteno/`.

## Web Push Certificates

If you already have a subscriber base, enter public and private keys in the corresponding fields. To receive new certificates, leave the fields blank—the keys will be automatically generated along with the script for your website.

<Image align="center" width="80%" src="https://files.readme.io/447c1da33d08a48de89ff4934688fe79c8b930f0d09bd807ea65dc53e5b88ce0-adding-website-to-account-005.webp" />

## Legacy Browsers Support

Follow the [link](https://docs.yespo.io/docs/how-set-web-pushes-safari) to configure Web Push subscriptions on Safari versions below 16.

> 📘 Note

> Sending Web Push notifications in Safari is only available in the *Advanced* plan

<Image align="center" width="80%" src="https://files.readme.io/51c3817518077cc13bca64f5e3cb92b801ac1ea64b02a4d62e4e5cbec4a78852-adding-website-to-account-25032025-04.webp" />

## Web Push Integration

It consists of the following steps:

* Generating and integrating the script
* Checking the website status

Let's take a closer look at these steps

### Generating and Integrating the Script

<Image align="center" width="80%" src="https://files.readme.io/736f9221d17b8853b5076ab6c7cc149ddbf9c5c133e1584a58fd0a51c8d2c12d-adding-website-to-account-25032025-06-yespo.webp" />

Click *Generate script* and follow these steps:

1. Download the Service Worker installation file below and copy it to the `/push/yespo/` directory on your website or to the directory specified in the File path field in the Service Worker settings.
2. Copy the generated code and insert it into the <head> section of your website's HTML pages.
3. <a rel="nofollow" href="https://web.dev/articles/add-manifest" target="_blank">Create a manifest file</a> and place it in the root directory to enable sending messages to devices with iOS/iPadOS.

<Image align="center" width="80%" src="https://files.readme.io/7874523d4311e0f38d991edb33d7724439711d37252c82bbc4484792f45e643e-adding-website-to-account-25032025-09-yespo.webp" />

### Checking the Connection Status

After uploading the installation file and adding the code to your website, click the *Check website status* button.

<Image align="center" width="80%" src="https://files.readme.io/d009bccf7aea5efa3954b64ed7de2575b5ed797110ed3811c563dc86141476b0-adding-website-to-account-25032025-12-yespo.webp" />

The *Website connected* status should appear in the settings. From this moment on, tokens will start to be collected.

<Image align="center" width="80%" src="https://files.readme.io/330afc2478238726059f3d820d452800d887a080b4dc9342eaad875bfdf72c05-adding-website-to-account-010.webp" />

Check the settings you’ve made if you see *Script not installed*.

![Script not installed](https://cdn.yespo.io/photos/shares/Support/Images/Adding-website-to-account/adding-website-to-account-011.webp "Script not installed")

> ❗️ Note

> Sometimes, the website status may not be displayed due to the website provider’s security policy. If the script is installed, ignore this status.

To enable Web Push notifications support on iOS/iPadOS devices in PWA (Progressive Web Apps), make sure the manifest file is placed in the root directory of your website.

<Image align="center" width="80%" src="https://files.readme.io/74c4bbe1646eacc303563250e07cac7d7b03ea10ee08adc6ff823aea49de2178-adding-website-to-account-2-011.webp" />

> 📘 Note

> If support is not required, simply ignore the *Manifest not found* status.

Click *Set up subscription* to go to the appearance settings of the subscription window, or *Back* to return to the general settings tab.

<Image align="center" width="80%" src="https://files.readme.io/60f52d32504cf96a11499da21f7bf238fbf528cbb6a83db37b55b95092a8a5b5-adding-website-to-account-012.webp" />

Learn more about customizing the appearance of the subscription window in a separate [article](https://docs.yespo.io/docs/setting-up-permission-request-prompt).

## Deleting Tokens

Enable the option to automatically delete inactive tokens after 30, 60, or 90 days to keep only those users who interact with the campaigns.

<Image align="center" width="80%" src="https://files.readme.io/610085669a4e27ae8b722b73e5922a3417d32638cc13db1c83ecfb1d1d97cf5d-adding-website-to-account-013.webp" />

## Editing Web Push Integration

To return to the integration settings, for example, to change the website name, re-upload the installation file, or copy the generated code, click the website link or the three dots icon and select *Web Push integration*.

<Image align="center" width="80%" src="https://files.readme.io/b4bb63829093990601475e1e40d5a661eeb2777f35ea91b10c7e16d118e6cf13-adding-website-to-account-014.webp" />

Here you can delete the linked website.

<Image align="center" width="80%" src="https://files.readme.io/4ee82ee7f8a601207fa0e8d957ed081fed35f2e69b7dac045f31b4d8e09f71ab-adding-website-to-account-015.webp" />