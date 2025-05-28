---
title: Messenger Protocol Support in Email Clients and Platforms
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Messenger Protocol Support in Email Clients and Platforms | Yespo Guide
  description: >-
    Learn how to integrate messenger protocols into campaigns to facilitate
    direct communication via messaging apps
  robots: index
next:
  description: ''
---
With the growing use of messaging apps for communication, email marketers are increasingly incorporating messenger protocols into their campaigns. These protocols, such as `tg://` for Telegram or `whatsapp://`, provide recipients with easy, clickable access to messaging apps directly from their emails. But how well do email clients and services support these protocols, and what should marketers know before implementing them?

## Messenger Protocols in Email Marketing

Messenger protocols enable users to open their preferred messaging app with a single click, similar to how traditional `mailto:` and `tel:` protocols work in emails. Instead of opening a mail client or making a call, these links direct users to specific chats or conversations in apps like Telegram, WhatsApp, or Facebook Messenger.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6326aa6dff2d0acc6281c100ab989bed6eddd09ba8312a0266c0aaad296b58ff-links.webp",
        "Messenger Protocols in Email",
        "Messenger Protocols in Email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


By integrating messenger protocols into emails, brands aim to reach their audience where they already spend a lot of time — on their favorite messaging platforms. This approach simplifies customer interactions and can lead to faster engagement, whether asking for support, joining a community, or initiating a conversation with the brand.

## How Do Messenger Protocols Work?

Messenger protocols function similarly to URL schemes. When a user clicks on a messenger link, the email triggers the opening of the messaging app on the user’s device, and the specified action — such as starting a conversation or opening a group — is executed. For example:

- `tg://resolve?domain=YourBrandChannel` directs users to a specific Telegram channel.
- `whatsapp://send?phone=YourNumber` opens a WhatsApp chat with your business.

This simple functionality provides an effortless transition from email to direct messaging.

## Challenges with Messenger Protocol Support

While the idea of embedding messenger links into emails is attractive, not all email clients and platforms fully support these protocols. Compatibility can vary across devices and platforms, which can affect the user experience.

Our team tested several popular messenger protocols to assess their compatibility with email clients and platforms. The table below shows the results of this testing.

## Protocol, Email Client, and Platform Compatibility Table

[block:parameters]
{
  "data": {
    "h-0": "Protocols",
    "h-1": "Email Clients",
    "h-2": "Platforms",
    "0-0": "`viber://`",
    "0-1": "Apple Mail  \nOutlook  \nSpark  \nEdisonMail  \nAirmail  \nCanaryMail  \nSamsungMail",
    "0-2": "iOS, macOS  \nmacOS, Windows  \nmacOS, Android  \niOS, Android  \niOS, macOS  \nmacOS, Android  \nAndroid",
    "1-0": "`sms:`",
    "1-1": "Apple Mail  \nOutlook  \nSpark  \nEdisonMail  \nAirmail  \nCanaryMail  \nSamsungMail",
    "1-2": "iOS, macOS  \nmacOS, Windows  \nmacOS, Android  \niOS, Android  \niOS, macOS  \nmacOS, Android  \nAndroid",
    "2-0": "`tel:`",
    "2-1": "Gmail  \nApple Mail  \nUkr.net  \nOutlook  \nSpark  \nEdisonMail  \nAirmail  \nCanaryMail  \nSamsungMail",
    "2-2": "Web, Android  \niOS, macOS  \nWeb, iOS  \nWeb, Windows, macOS, iOS, Android  \niOS, macOS, Android  \niOS, macOS, Android  \niOS, macOS  \niOS, Android  \nAndroid",
    "3-0": "`skype:`",
    "3-1": "Apple Mail  \nYahoo  \nAol  \nOutlook  \nSpark  \nEdisonMail  \niOS, macOS  \nCanaryMail  \nSamsungMail",
    "3-2": "iOS, macOS  \nWeb  \nWeb  \nmacOS, Windows  \niOS, macOS, Android  \niOS, Android  \niOS, macOS  \nAndroid  \nAndroid",
    "4-0": "`tg://`",
    "4-1": "Apple Mail  \nOutlook  \nSpark  \nEdisonMail  \nAirmail  \nCanaryMail  \nSamsungMail",
    "4-2": "iOS, macOS  \nmacOS, Windows  \nmacOS, Android  \niOS, Android  \niOS, macOS  \nmacOS, Android  \nAndroid",
    "5-0": "`whatsapp://`",
    "5-1": "Apple Mail  \nOutlook  \nSpark  \nEdisonMail  \nAirmail  \nCanaryMail  \nSamsungMail",
    "5-2": "iOS, macOS  \nmacOS, Windows  \nmacOS, Android  \niOS, Android  \niOS, macOS  \nmacOS, Android  \nAndroid"
  },
  "cols": 3,
  "rows": 6,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


_Based on June 2021._

_Tested on iOS 14.6, Android 10, 11 and MS Office2019._