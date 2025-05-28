---
title: Setting Up Firebase Application for Firebase Cloud Messaging
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Most often, mobile applications already have FCM settings. In this case, you do not need to make any additional FCM settings.

Follow the guide below if your application does not have FCM settings.

1. Verify that your Gradle files include the correct FCM and [Reteno libraries](https://docs.yespo.io/reference/android-sdk-setup#getting-started-with-reteno-sdk-for-android).
2. Download your `google-services.json` config file (see how [here](https://support.google.com/firebase/answer/7015592?hl=en)).
3. Add the above file to your root `app/` folder.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92a4356-google-services-json.png",
        "google-services-json.png",
        379
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]

4. Copy your FCM Server Key. In the [Firebase console](https://console.firebase.google.com/), click the gear icon next to Overview

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c35971-FirebaseConsole.png",
        "FirebaseConsole.png",
        743
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]

5. Click _Project Settings_ → _Cloud Messaging_ → _Manage Service Accounts_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6080b18-CloudConsole1.png",
        "CloudConsole1.png",
        648
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]

6. Go to Service accounts to download FirebaseAdminSdk account's json key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc907e7-CloudConsole2.png",
        "CloudConsole2.png",
        654
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]

7. Follow this manual to [set up Yespo admin panel](https://docs.yespo.io/docs/connect-your-mobile-app#for-all-devices) with your Firebase key.