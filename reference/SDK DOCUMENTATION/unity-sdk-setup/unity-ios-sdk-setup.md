---
title: Unity iOS SDK Setup
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity iOS SDK Setup
  description: Follow our setup guide to integrate the Reteno SDK with your app
  robots: index
next:
  description: ''
---
## Setting up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

After building in Unity open the Xcode Workspace and follow these setups.

Click on "Unity-iPhone" on the left and `select` the "Signing & Capabilities" tab.

If you'd like to make provisioning your app easier, you can `check` "Automatically manage signing", on the prompt `click` "Enable Automatic", and `select your Team`. Otherwise you can do this manually.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5282fc8-step_1.png",
        null,
        "Signing & Capabilities"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Scroll down to "App Groups" and `click` on the refresh button.

> 📘 NOTE
> 
> You may have to press this a few times as it will ask you for each signing type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d8f3394-step_2.png",
        null,
        "App Groups"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Repeat the same steps above but for the "NotificationServiceExtension" target this time.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58dd0c2-step_3.png",
        null,
        "NotificationServiceExtension"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


"App Groups" should now be provisioned for you going forward for your iOS bundle id, even on clean builds.

> 📘 Note
> 
> [iOS Debug Mode](https://docs.yespo.io/reference/ios-debug-mode) enables you to ensure that all events and user properties are logged correctly.