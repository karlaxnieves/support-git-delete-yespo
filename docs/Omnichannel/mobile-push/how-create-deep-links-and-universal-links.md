---
title: Deep Link Types
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Create Deep Links and Universal Links | Yespo Guide
  description: >-
    The document explains the use of three types of deep links in Yespo's mobile
    push notifications: Traditional deep links, Web deep links, and
    Universal/Android App Links, detailing their configurations and
    functionalities for directing users to specific app locations or web pages.
  robots: index
next:
  description: ''
---
A deep link is a uniform resource identifier (URI) that links to a specific location within a website, app, or app store. You can use 3 deep link types in Yespo’s mobile push notifications:

- **Traditional links** (_`app-name://category/screenX`_),
- **Web deep links** (_`https://www.example.com/products`_)
- **Universal links** (_`https://www.example.com/products`_)

## Traditional Deep Links

Traditional deep links lead to the app or any of its screens.Add your application name instead of the HTTP protocol to create the traditional deep link. The traditional link may look as follows:

`app-name://category/screenX`

> 📘 Important
> 
> Assigning the appropriate link to the screen within the application is necessary

If the user doesn’t have the app installed, clicking the deep link leads to an error page. But since you send a deep link in a mobile push, you can be sure that the contact has your application installed.

> 📘 Note
> 
> The operation of the traditional deep links after clicking without app installed depends on the implementation of link processing

## Web Deep Links

The click on the web deep link is processed according to the schemes outlined below.

On iOS:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65f7cac310ad5a23437398281daaa917ed100aba11dc9ebb822c9ee7fc7b59e8-2-yespo.webp",
        "Android",
        "Android"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


On Android:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d46a09eb39c20b1178dbc830adc29173119ae32fbd76d4aa86d59026e5a8487e-1-yespo.webp",
        "Android",
        "iOS"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Clicks on web deep links in a web browser direct users to a specific section within an app or to a web page if the app is not installed.

Web deep link looks like a web link: _`https://www.example.com/products`_

You need to set up opening your app by tapping on `www.example.com` in your app settings.

> 📘 Note
> 
> Web deep links may be helpful for apps supported by websites, for example — ecommerce. But we don’t recommend using it because of the high risk of loose UTMs or other important parameters, which may be critical for analytics.

## Universal Links (on iOS) and Android App Links

Universal Links and Android App Links are back-end frameworks with specific configurations.

They can be used in [email campaigns](https://docs.yespo.io/docs/launching-an-email-campaign) to direct users to a specific section within an app.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f1f54d6f1293efd9f1aa8c6fadda429a3a1132c789e9788cbcdce85d86a92da-3-yespo.webp",
        "Universal Links and Android App Links",
        "Universal Links and Android App Links"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Android

Guide on the official website: <a rel="nofollow" href="https://developer.android.com/training/app-links/deep-linking#java" target="_blank"> developer.android.com</a>. 

1. Create links to certain app pages.
2. Add intent filters to incoming links.
3. Add the association file in a JSON format to your domain (app domain or ad tracker domain).

Test intent (Shell):

```Text Shell
adb shell am start
     -W -a android.intent.action.VIEW
     -d <URI> <PACKAGE>
```

### iOS

Guide on the official website: <a rel="nofollow" href="https://developer.android.com/training/app-links/deep-linking#java" target="_blank"> developer.apple.com</a>.

1. In the app settings, create an association between your app and your domain (app domain or ad tracker domain) via XCode.
2. Create an association file — a page that contains data in the JSON format that is content in the app.
3. In app delegate, set up rules for clicks on universal links. A click will redirect to the app if it is installed or to the page in Safari if the app is not installed.

> 📘 Important
> 
> For proper operation, provide the association file (manifest.json) to our support to be placed on our server.
> 
> When creating an association, note that all the links in the campaign will look like this: _`your.domain.esclick.me/FA25jGSLGXxg`_. This is a subdomain. When a user clicks such links, they’re redirected to our server. The system registers the link and returns the original link that the user clicks.