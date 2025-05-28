---
title: Managing Mobile SDK Access Keys
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Managing mobile SDK access keys | Yespo Guide
  description: >-
    The article provides a comprehensive guide to securely handling access keys
    used in mobile app SDKs
  robots: index
next:
  description: ''
---
After you [connect your mobile app to Yespo](https://docs.yespo.io/docs/connecting-mobile-apps), you have to create the access key.

This access key authorizes all the requests sent from the mobile app through the SDKs ([iOS](https://docs.yespo.io/reference/ios-sdk), [Android](https://docs.yespo.io/reference/android-sdk), [React Native](https://docs.yespo.io/reference/react-native-sdk), [Flutter](https://docs.yespo.io/reference/flutter-sdk), [Unity](https://docs.yespo.io/reference/unity-sdk-setup), [Cordova](https://docs.yespo.io/reference/cordova-sdk-setup), [Ionic](https://docs.yespo.io/reference/ionic-sdk)) to Yespo.

## Creating and Enabling the Access Key

To create and enable the access key:

1. Go to your _profile → Settings → Mob Push_.
2. In the connected app, select the _Access Keys_ tab and click _Add key_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63049173f000ce33586e3d5f0354267110efb9440dd88844a1ea7441b4d3fc51-key-1.webp",
        "",
        "Add access key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. In the Create access key dialog box, enter the key description in the _Description_ field and click _Create_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de976968fca376b5512469adde3d9eb021cdc64ce9c84229a6ca8d5a75faae83-key_description_and_create_eng.webp",
        "",
        "Creating the key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Assigning the description for each mobile access key allows you to identify it and understand which integration it is associated with.

4. To enable the access key, switch on the _slide button_ on the left-hand side.

> ❗️ Note
> 
> If you do not need to use the access key, disable it by clicking its slide button.

## Using the Key to Access SDK

To use the access key to authenticate access to your mobile SDK:

1. Go to your profile → _Settings → Mob Push_ and select your mobile app connected to Yespo.
2. Select the Access Keys tab, point to the key, and click the _Copy_ icon beside your key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c575c9ea4597dd6c8028c28063a7491eb83816d3d8f792c4cd395b086df196e6-key-3.webp",
        "",
        "Copying  the key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Send your API key in _X-Reteno-Access-Key_ HTTP header in every request.