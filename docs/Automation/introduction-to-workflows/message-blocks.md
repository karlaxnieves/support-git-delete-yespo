---
title: Message Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Message Blocks | Yespo Guide
  description: >-
    Discover the Message Blocks in marketing automation workflows. Learn how to
    use blocks like Email, SMS, Push Notifications, and more to communicate
    effectively with your audience and drive engagement.
  robots: index
next:
  description: ''
---
The system contains eight _Message blocks_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/233e565fd55f6496391603c18e86e341604b0976b6c2da3cb424e5645f8354b7-blocks01.webp",
        "Message Blocks",
        "Message Blocks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


A separate article describes [_The One from many block_](https://docs.yespo.io/docs/using-one-many-block) configurations in detail. Next, we will review the parameters of blocks that send one message to one contact.

Each block includes basic and advanced parameters.

## Basic Parameters

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/acb1694ca1ec21c776e0310ae6dfbb7cb7e7483092494ed0b2261708a4e1ecce-message-blocks-301.webp",
        "Basic Parameters",
        "Basic Parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


List of Basic Parameters:

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Configuration",
    "h-2": "Blocks",
    "0-0": "Message",
    "0-1": "Select a pre-created message that will be sent.",
    "0-2": "All",
    "1-0": "Send only in specified hours",
    "1-1": "Activate the toggle to send the message only in specified hours. The option is disabled by default.  \n  \n[See more detailed information >](https://docs.yespo.io/docs/allowed-send-time-messages-workflows)",
    "1-2": "All",
    "2-0": "TTL ",
    "2-1": "Set the period after which the message will not be displayed if it has not been delivered to the contact by that time.  \nBy default, 1 day is set. The minimum value is 2 minutes, and the maximum is 28 days.",
    "2-2": "Viber",
    "3-0": "Application  ",
    "3-1": "Select the name of the mobile app. If only one app is connected, it will be selected automatically.",
    "3-2": "Mob Push",
    "4-0": "Telegram bot",
    "4-1": "Specify the name of the Telegram bot. It will be selected automatically if only one bot is registered in the account",
    "4-2": "Telegram"
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


## Advanced Parameters

You must fill in advanced parameters when using custom event parameters, sending messages to an additional contact, and inserting dynamic content.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6bc395ca5fcdcd0da20a005f7a202756568a6ff01e22aa5031793f058a71f7a8-message-blocks-302.webp",
        "Advanced Parameters",
        "Advanced Parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)