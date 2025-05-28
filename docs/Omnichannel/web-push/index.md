---
title: Web Push
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Web Push | Yespo Guide
  description: >-
    Web push notifications are pop-up messages that appear in browsers and can
    be sent anytime the browser is open; setting them up in Yespo requires
    adding a website, configuring permission prompts, and additional steps for
    Safari.
  robots: index
next:
  description: ''
---
A web push notification is a pop-up message in the desktop and mobile browser. Web push notifications can be delivered anytime when users have their browsers open, regardless of whether they are visiting the sender's website at the moment.

<Image align="center" width="40% " src="https://files.readme.io/0469d6005c356b313970bdd6d5164fec76f3372c9d4656fd125645dcce0b73f4-84fd5f5-web_push.png" />

> 📘 Important
>
> Web push token collection is only available for websites that use the https\:// protocol.

You need to do a few steps before sending web push notifications through Yespo.

> 📘 Note
>
> For the Safari browser, complete [additional settings](https://docs.yespo.io/docs/how-set-web-pushes-safari) before moving on to the first step.

## Step 1. Add a website to your Yespo account

See details [in the instruction](https://docs.yespo.io/docs/how-send-web-push-notifications-website).

## Step 2. Set up permission request prompt

Choose single opt-in or double opt-in request prompt and configure its appearance. [See details >](https://docs.yespo.io/docs/setting-up-permission-request-prompt)

Also, you can set [multilingual browser push notification permission](https://docs.yespo.io/docs/how-set-multilingual-browser-push-notification-permission) if you want to communicate with your site visitors in their native languages.

> 📘 Note
>
> To send push messages to Progressive Web Apps (PWA), add manifest file to the root directory of your site.
>
> The manifest must describe which recourses to use for PWA (you should create it on your own).
