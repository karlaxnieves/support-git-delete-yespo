---
title: Setting up UTM Tags
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting up UTM Tags | Yespo Guide
  description: >-
    A UTM tag is a small snippet of code consisting of a parameter and its
    value. Learn how to use UTM tags to monitor your marketing channels and
    campaigns through analytics systems.
  robots: index
next:
  description: ''
---
UTM tags are code fragments consisting of a parameter and its value. They are added to the URL to maintain the efficiency of marketing campaigns through analytics systems, such as Google Analytics (GA).

You do not need additional integration with analytics systems to obtain UTM tags in Yespo. The tags generate automatically and trigger as soon as the user clicks on the link. If your analytics system is already set for UTM processing, you are only to track the results.

In Yespo account you can:

- use auto-generation of UTM tags or disable it in the particular message or the entire account;
- add your values for UTM tags within the email and App Inbox messages;
- set UTM tags for all or individual language versions of [multilingual](https://docs.yespo.io/docs/multilanguage-overview) email, App Inbox, web push and viber messages.
- set custom UTM tags and rules for their substitution globally for the entire account, single email and App Inbox messages.

For a global UTM tags parameters configuration, go to _Settings_ → _Links_ in your Yespo account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42d125e16ae27aeb417152224a89573bd47c1e5df87d506fff83db9bfc6f443a-utm_14.png",
        null,
        "Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Then activate the _UTM tags_ slider so that parameters about traffic sources start transferring to the analytics system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0122ad1fb122bb3f18f5bb280f52b1ef071f577c39420d6be4927ab866653365-utm_2.png",
        null,
        "Links"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> For correct automatic channel labeling (email, Viber, mob push, etc.), the utm\_medium field should be filled with the `$mediaType` value (as it’s set by default), otherwise, campaigns in GA will be counted to one channel specified in this field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ace41dabe9208a626a397604b6667f252b6d2a733b47d6ac823bf97131de0977-utm_4.png",
        null,
        "Links"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Required tags are:

- `$type` – message type (trigger/promo);
- `$mediaType` – message channel (email/Viber);
- `$messageName` – the name of message;
- `$messageId` – message identifier;
- `$contactId` – contact identifier;
- `$messageTags` – tag added to message.

Optional tags are:

- `$messageInstanceId` – message instance identifier. When sending a campaign, each letter, in addition to its messageId, also has an additional id – messageInstanceId. This is the message id of a particular campaign. For example, you are going to send 1 email message to 5 different groups, which means one letter will be sent 5 times. Then all 5 campaigns will have the same messageId but different messageInstanceId. It is useful when you have to compare the effectiveness of 1 message sent to different segments.
- `$dateStart` – campaign start date.
- `$groupName` – segment name.
- `$contactInfoHash` – gives encrypted email + SMS + contact name combination. For example: `ZT1pdmFuLmtoCXxlem92QGVzcTV0bmlrLmNvbSZwPTM4MFk1MzY1OTM3MyZuRT`. You must enable encryption on your site.
- `$messageLang` – message language, when using [multilanguage functionality](https://docs.yespo.io/docs/multilanguage-overview).
- `$strategyGroupName` – strategy group name, where contact was found when campaign sending started.
- `$workflowId` – id of the workflow triggering the message sending.

If you need to track any of these parameters, specify it in the corresponding **Value** field next to the required **Key** tags.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/457cd7bc0dfacc585b67695d57157bd305e37c380f9bf5d28b14f029368ec938-utm_8.png",
        null,
        "Links"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If other keys are required for recognition by your analytical system, activate the **Additional tags** slider and click the **New key** button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3ba538913807ee1dd4c299fec4aef59aebcbac5aa89d08c2884a9852857ce98c-utm_6.png",
        null,
        "Custom tags"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Two fields for the **Key – Value** pair will be shown. Here you can enter the necessary keys and tag values as variables with the **$** sign or your own static expressions. By clicking on the _gear_ icon, you can select values ​​from a list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c45462fce911a2ac3f91f20c4b6b6e0a34319de117ff8535eb430ce13aad508-utm_1.png",
        "",
        "Gear icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Setting up UTM tags in a particular message

### Email messages

Yespo generates suitable keys for Google Analitycs by default. But there are two ways to use your tag values:

1. Pasting pre-generated UTM tagged links into your letter.

Open additional letter parameters by clicking on the three dots button at the top bar. Then choose the option **Specify links settings**:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba9ab7535b9da358b12644acffb8770f3225a456e0bb7c4369894af00e5cf0cd-utm6.webp",
        null,
        "Email editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Make the UTM tags slider inactive.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b301136d1882ccc8998edc2d29fc62128e75eebd6df6d39ead7232abccd4a64-utm_12.png",
        null,
        "Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When creating a letter in the editor, enter links with your tags:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c6d77c7dd019aac340de967a70157d1b734dd24dd73cc9bb001c9fbe87a49419-utm8.webp",
        null,
        "Email editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


This method is useful, for example, when you need to track the conversions of different buttons or email elements.

> 📘 Important
> 
> When sending a campaign, the priority is always given to a manually entered value, even if the UTM tag switcher is active.

2. Adding tags for a specific letter.

Go to the top bar and click the three dots button → choose the **Specify link settings** item.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/747ede5050327d3776801bdc68cb04ced1ecb7542edc39f8f924ee33fd4b725e-utm9.webp",
        null,
        "Email editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Enter the required values without the **$** sign beside the corresponding keys. Do the same in the **Additional tags** section. If necessary, you can create a new key and enter an additional parameter. All your changes apply to the letter after saving.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f06766eb8b22af36db4e6b3c0e894a5f2258176f81c99cb5c2aaf78489c42e97-utm_19.png",
        null,
        "Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click **Apply** to save the settings, or **Restore default values** to return the basic parameters.

If you set up tracking of UTM tags within an email message but didn't disable tags at the account settings, then the tag generated within an email will have priority for the analytics system.

> 📘 Important
> 
> When a letter is copied, its UTM tags are also copied. The statistics of two or three letters will be included in one report so that the measuring impact of a particular message becomes impossible. If you enter tags manually, be sure to check them in every email. Remember, a new email created from a template will inherit its tags. If you turn off Track URL’s switcher, Google Analytics won’t get any data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/212670206b2779c2d96e0adc1d440b52872c8be02bab9024232d12bc37e4d256-utm_5.png",
        null,
        "Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### App Inbox

Link settings in App Inbox messages are similar to those in email. You can enable or disable URL tracking, UTM tags, and add custom tags.

To customize the link in the App Inbox, click on the gear icon in the link field.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9a88de309f656a797c86e3e4460a8938dd1098c67a91f301f72843b257848b92-image1.webp",
        null,
        "Link settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Viber, SMS, Web Push, Mobile Push and Telegram

The automatic UTM tag switcher in **Web Push, Viber, and Telegram** messages is enabled by default. The same variables are used as those set in the Links section of the account settings.

If you want to customize your values, then disable system tagging and write a link with a pre-generated UTM tag in the post editor.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2e6653941e518def8992984cc64b00d7e7a536fa008681248c4e5265289de684-enable-utm.webp",
        null,
        "Specify UTM"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When creating an **SMS message** use Enable UTM tags for this message switcher to make the automated UTM tags work. Make sure that `$mediaType` variable is set as a value of the UTM channel. When sending an SMS campaign it will be transformed into “sms” value.

You are free to use your UTM-tagged links. Shortening them by the bit.ly service is recommended.

UTM tags for **mobile push** notifications are not created automatically, they must be specified for every single message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/528eeb90d96069f6582a29ff8b090429a5df5670a95e297b587b3c042131a956-link.webp",
        null,
        "Additional settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## FAQ

1. Is it possible to use several links with different UTM tags in one email message, will not the data be lost?  
   If there are clicks on these links, they will be displayed in the analytics system.
2. I don't see sales data in Google Analytics, how can I fix it?  
   Google Analytics must be set to eCommerce to track transaction and revenue data. Please contact your GA specialist to ensure that eCommerce tracking is set properly.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/36de2f5a01dc16c789daa90ad70d7be1632fab03cfcdfdd934d3e8ccd33128a4-utm15.webp",
        null,
        "Google Analytics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. How to find a transaction by a particular customer in Google Analytics?  
   You can track information about transactions of a particular subscriber by the **Contact Id** tag if it is specified as a parameter in the UTM tag as `$contactId`.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc458858fc2af28bb2b80c47d140a0ec0754dbc5cf5a51bc2d93a11679343e12-utm_13.png",
        null,
        "Links"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. How soon will the data be sent to Google Analytics?  
   Data is sent to the analytics system immediately after the user clicks on the link in the message.
5. How to track purchases by one certain channel in Google Analytics?  
   Go to Google Analytics, and select _Traffic Sources_ → _All Traffic_ → _Channels._  
   Read more about tracking campaign performance in the guide.

[block:image]
{
  "images": [
    {
      "image": [
        "https://cdn.yespo.io/photos/shares/Support/support/utm17.webp",
        null,
        "Google Analytics"
      ],
      "align": "center",
      "sizing": "50% "
    }
  ]
}
[/block]