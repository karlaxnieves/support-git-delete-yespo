---
title: Managing Mobile SDK Access Keys
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
After you [connect your mobile app to Yespo](https://docs.yespo.io/docs/connecting-mobile-apps), you have to create the access key.

This access key authorizes all the requests sent from the mobile app through the SDK ([iOS](https://docs.yespo.io/reference/ios-sdk), [Android](https://docs.yespo.io/reference/android-sdk), [React Native](https://docs.yespo.io/reference/react-native-sdk), [Flutter](https://docs.yespo.io/reference/flutter-sdk), [Unity](https://docs.yespo.io/reference/unity-sdk-setup), [Cordova](https://docs.yespo.io/reference/cordova-sdk-setup), [Ionic](https://docs.yespo.io/reference/ionic-sdk)) to Reteno.

## Creating and Enabling the Access Key

## 

To create the access key:

1. Go to _your profile_ → _Settings_ (1) → _Mob Push_ (2).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a8d02ad-Settings.png",
        "",
        "Mob Push tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click on the name of your app. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99e9704-edit_app.webp",
        "",
        "Click on the app name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the _Access Keys_ tab and click _Add access key_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/73c8efe-Access_Key_1.png",
        "AddKey.png",
        "Access Keys"
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


4. In the _Create access key_ dialog box, enter the key description in the _Description_ field and click _Create_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d728f9c-key_description_and_create_eng.png",
        "key_description_and_create_eng.png",
        "Create access key"
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


> 📘 Note
> 
> Assigning the description for each mobile access key allows you to identify it and understand which integration it is associated with.

5. To enable the access key, click the slide button on the left-hand side.

> 📘 Note
> 
> If you do not need to use the access key, disable it by clicking its slide button.

## Using the Key to Access Reteno SDK

To use the access key to authenticate access to your Reteno mobile SDK:

1. Go to _your profile_ → _Settings_ → _Mob Push_ and select your mobile app connected to Reteno.
2. Select the _Access Keys_ tab and click the _Copy_ icon beside your key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/67844bb-Access_Key_3.png",
        "copy_key_eng1.png",
        "Access Keys"
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


3. Send your API key in X-Reteno-Access-Key HTTP header in every request.