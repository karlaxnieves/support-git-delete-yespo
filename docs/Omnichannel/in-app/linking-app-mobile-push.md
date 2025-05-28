---
title: Linking In-App with Mobile Push
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Linking In-App with Mobile Push | Yespo Guide
  description: >-
    The document explains how to link an In-App message with a mobile push
    notification, including steps for creation, testing, and viewing analytics
  robots: index
next:
  description: ''
---
In-App messages can be shown in the application in two ways:

- [according to triggering rules](https://docs.yespo.io/docs/in-app-publishing-and-triggering-rules);
- by tap on mobile push.

Here we will look at the second method — how to link an In-App with a mobile push message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7186147661066a90cca2a1cf166ee3b2dc117491adb42a075e027b9ac08b585d-creating-in-app-message-01.gif",
        "",
        "How In-App works"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Linking In-App with Mobile Push

1. [Create an In-App](https://docs.yespo.io/docs/creating-in-app-message).
2. Create or open a [mobile push notification](https://docs.yespo.io/docs/how-to-create-mobile-push-notifications).
3. Activate the _Open in-app by clicking_ switcher, and select In-App message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4743ddf0131f4a658737100ed1c40662a2460e842af4e2c6cd12d716180d9c3c-creating-in-app-message-30.webp",
        "",
        "Open in-app by clicking"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The link and buttons are unavailable for mobile pushes with linked In-App messages.

Mobile pushes with linked In-App messages marked with the _chain_ icon in the system. Hover over the icon to see the name of the linked message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/56a64a9d807f0d3a65c9f8b9857070bdae9ffdc5e45797e856e1d359ca4b6366-creating-in-app-message-31.webp",
        "",
        "Chain icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Testing In-App Message

1. Open the mobile push message with the linked In-App.
2. Click the Test button on the top panel of the mobile push.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/505ba487c3c9849897dc0f7115bf5b13634f1e705f2c177d1b0b2a1b55569ccd-creating-in-app-message-32.webp",
        "",
        "Testing In-App"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the application in the _Send Test Message_ window, to which the push notification will be sent. If you have only one application, it will be automatically chosen by default.
4. Enter the email, contact ID, or phone number into the Search field to specify the contact for the push notification.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/214cae4d494874d7f6ab2ad894a73cff6c6940d4855f24e9b06d0d731aef99eb-creating-in-app-message-33.webp",
        "",
        "Send Test Message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If the contact is an app user, you will see the such status:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6245da096cb2288750d80839bae1dd251a7deaec07959105f97c730cd04effca-creating-in-app-message-34.webp",
        "",
        "Status"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


It means the provided contact data has a matching mobile token. You can send a test notification to this contact. 

Otherwise, you will receive the following notification: The contact does not have an application token.

When you receive the test mobile push, click on it to see the linked In-App message.

## Analytics

See reports on In-App campaigns in [mobile push analytics](https://docs.yespo.io/docs/mobile-push-campaign-report) (messages with the chain icon).

The number of clicked messages refers to In-App messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b0ded758e1236d7932d3b4b007073d642536836cc77be41cb77e98e3bc054be0-creating-in-app-message-35.webp",
        "",
        "Analytics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]