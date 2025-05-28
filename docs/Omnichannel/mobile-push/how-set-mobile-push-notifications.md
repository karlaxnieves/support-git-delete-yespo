---
title: Creating and Uploading a Firebase Key
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Push notification for mobile applications using FireBase | Yespo Guide
  description: >-
    Learn how to generate a private key, and upload it to Yespo through your
    account settings
  robots: index
next:
  description: ''
---
To send mobile push notifications via Firebase Cloud Messaging (FCM), register the project in Google Firebase, create a key, and upload it to Yespo.

## Creating a Project

1. Go to the <a rel="nofollow" href="https://firebase.google.com/" target="_blank"> Google Firebase</a> service page and click _Get started_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f66899bd2c6278352de5e7b661ccd1761ca5db31d548b4da14592ae9056fb2fe-fcm-1.webp",
        "Get started",
        "Get started"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the _Create a project_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9db50654fb17c6adaf55c7957aac679487a825a4a73706d7f772847b5ffd8a19-fcm-2.webp",
        "Create a project",
        "Create a project"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Name the project and accept the terms of use; click _Continue_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fcb705951f7d1b1b0d379064e78b2d40e907c999ae4a5c0fc088faf3cc442891-fcm-3.webp",
        "Name the project",
        "Name the project"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Activate or deactivate the use of Google Analytics for the project; click _Continue_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1bbf13afb1dcd850b2b56156bca5f87e41e0b84573f23df7b63f1f73911848dc-fcm-4.webp",
        "GA",
        "GA"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you have agreed to use Google Analytics, select or create a Google Analytics account; click _Create project_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e2529b796e6a5d06b3522d57b2853ff6dfb9c745cd9670e045fea4e04d4e5ac-fcm-5.webp",
        "Create project",
        "Create project"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Your new project is ready; click _Continue_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/487b22b632af7cda0fe3e817190a60fb7fda9079f1358c954710e9a0aa384052-fcm-6.webp",
        "Your new project is ready",
        "Your new project is ready"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Generating a Key

1. In the left panel, click the settings wheel next to _Project Overview_ and go to the _Project settings_ menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3172d5f32dfc854d7c9bd8b8e45f4db9757eee59ff3a5bc94a120a44d3bbc578-fcm-7.webp",
        "Project settings",
        "Project settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Go to the _Service accounts_ tab and click the _Generate new private key_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/330f3488fe722614c6f6e78060120f1c61162529d64b7e3c7fabb4893bfed9b2-fcm-8.webp",
        "Generate new private key",
        "Generate new private key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Generate key_ In the dialog box.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/401613fdb04d2f43ed8af87ebc6c4b40ace334679c8adc9f5471ceb8e9f05cc5-fcm-9.webp",
        "Generate key",
        "Generate key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Download the key to your device.

## Uploading a Key to Yespo

Go to your Yespo account settings to the _Mob Push_ tab, open one of the previously created applications or create a new one and upload the key file.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5516151c7516fdb2db93ed5ecfdfab4e03e5d42dad8f5f7f878751f29b048c9-fcm-10.webp",
        "Generate key",
        "Upload a key to Yespo"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More on connecting mobile app >](https://docs.yespo.io/docs/connecting-mobile-apps)