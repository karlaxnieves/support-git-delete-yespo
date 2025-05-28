---
title: Creating Telegram Message
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Telegram Message | Yespo Guide
  description: >-
    Communicate with subscribers of your Telegram bot using Yespo: give advice,
    inform, and sell goods or services.
  robots: index
next:
  description: ''
---
To send Telegram messages via Yespo: 

1. Create a bot in the <a rel="nofollow" href="https://telegram.me/BotFather" target="_blank"> @BotFather</a> service, copy the access key, and upload it to our system.
2. Subscribe to a pricing plan.

> 📘 Note
> 
> - The number of contacts in a subscription is calculated based on contacts with tokens.
> - If the number of contacts in a Telegram channel exceeds the plan’s limit, messages will not be delivered to contacts above the limit.

Then, you can proceed to create a Telegram campaign.

## Creating a New Telegram Message

Go to the _Messages_ section → _Messages → Telegram_. Click _New Telegram_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22f9c516edd6cd39e28975e0dc67dd03cbb6d8edf37d3764a9bf16a4277d2cd4-new-teleg-01.webp",
        "New Telegram",
        "New Telegram"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Main Settings

Fill in the following fields:

1. **Name**. Select a message name. This field is available for searching messages in the general list; users will not see it.
2. **Message text**.

> 📘 Note
> 
> The maximum number of characters in a message is 4096. If the message contains an image, the maximum text length is 1024 characters.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/735ba3a5731a7c0fcd3da14b35af2a6c7dbe821b365aaa4103783fac857d7bf5-telegram-message-new-en01.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use in the text field:

- clickable links that will provide additional transitions to the site and allow the recipient to find out the promotion details or product characteristics immediately;
- emoji;
- personalization with variables from [contact fields](https://docs.yespo.io/docs/how-add-additional-contact-fields): name, city, number of bonuses, etc.; click the person icon and select the desired value.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/801b38c2e2e4def1541e6035287a47d977b4771b655aa3be35153628d774508f-telegram-message-new-en02.webp",
        "Link, emoji, personalization",
        "Link, emoji, personalization"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> One emoji takes up two characters. Keep this in mind when creating messages.

3. **Image** in JPEG, PNG, WEBP or GIF format up to 5 MB. For optimal quality, use an image size of around 800x800 pixels. Image proportions will be preserved; for better display we recommend using standard proportions (for example, 1:1, 4:3, 16:9). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/050d6ddf046620759c709ca043cfba88b03f14598b179031067f84bb91eea418-telegram-message-new-en03.webp",
        "Image",
        "Image"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can edit the image directly in the editor when uploading (if it does not meet the requirements) or after uploading (the _Edit_ button). After editing, the image is saved in PNG format.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c79eadbf84127724339693fc333a1e4b32c26edc631b601add5e13092ffc9820-telegram-message-new-en04.webp",
        "Image editor",
        "Image editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. **Buttons** can be placed horizontally ("_Add button_", up to six in one row) and vertically ("_Add  buttons row_"). Usage options:

- **Open URL** — to redirect users to external resources;
- **Send callback data** — to execute internal commands that redirect users within the bot. The command can be any text up to 64 characters long, for example — `callback|211|||goto|212|82/scanpack`. These commands must be supported in the bot itself. Below is an example of code that passes the `callback\_data` parameter to the bot:

  ```json
  - {  
        "inline_keyboard": \[  
            [  
                {  
                    "text": "Action",  
                    "callback_data": "Option M"  
                }  
            ]  
        ]  
    }
  ```

5. **Tags** (optional). Add [tags](https://docs.yespo.io/docs/how-add-tags) by selecting the ones you need from the list, or create new ones by clicking _Add tag_. Using tags, you can quickly find your desired messages, analyze statistics, and set up your [messaging frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e3a27b6d8b83eaf949aaa800c362dd08c020843ba1140d7815bd6764d907b7c8-telegram-message-new-en05.webp",
        "Main settings",
        "Main settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Additional Settings

1. Specify [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) to send messages to your contacts based on their interests.
2. Enable or disable UTM tags for all language versions (see [the link](https://docs.yespo.io/docs/how-transfer-utm-parameter) for details).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e842ddbb8a72178ec6b89af5438900aa478ce19148be7d32a6f08260175285e2-telegram-message-new-en06.webp",
        "Additional settings",
        "Additional settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Multilingual Version (optional)

Click the globe icon on the top panel, specify the default language, and add language versions to create a multilingual message. Fill in each version with content in the appropriate language. [More on multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f6b5bef44b9fc8dc15d1a4851734f056fcfea76b66a019b0e2921123d8d0e2e4-multilanguage.webp",
        "Multilingual version",
        "Multilingual version"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Testing Message

1. Test the message by clicking the TEST button on the top panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf12718d289d9d067e79c7f78a7734765dbc7019d965c4d1e983e45c5965080c-telegram-4.webp",
        "TEST",
        "TEST"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the contact ID or select a contact from the list. The user to whom the test message is sent must be registered in the corresponding Telegram bot.
3. In the Telegram bot field, specify the bot to which the message will be sent. If you only have one bot, it will be selected by default.
4. Click _Send_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2594caf13e584c31a00d1c953a9b1d58498bc742f84a9b2bec97ef5f78907408-testing-telegram.webp",
        "Send test",
        "Send test"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If everything is set correctly, the message will be displayed in the specified bot.

## Creating Campaign

1. Click on the _Create campaign_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c0914d544fa06a796888379e090ef5d27e3e30372c89abafa5d8300df2b4d6f-telegram-5.webp",
        "Create campaign",
        "Create campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the pop-up window, activate the checkbox next to the contact or segment for which you want to send a campaign. Then click the _Go to campaign_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4239d8c3ac1b5eaa8505282c6eebc87576eb70ee5dc2d1ffd61e48e7d8e13eee-starting-2.webp",
        "Go to campaign",
        "Go to campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. On the general checkout page:

- Check the bot the message will be sent to.
- In the _Segments_ section, click _Recalculate contacts_ to see the total number of contacts that will receive the notification. You can also edit segments or select new ones.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/97510645daecdffd604013c47f69f73ac0b75cf7969a54494161a2abf9bdeafc-starting-3.webp",
        "Settings",
        "Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


See all the necessary information for verification: _Name_ and _Subscription categories_. You can see how the message will look on Android and iOS.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60cffe80adc63fe1be6cc0e81d838723d905610ef3cd94845e1da1a621e12d68-telegram-6.webp",
        "Preview",
        "Preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the _Send options_, you can set the batching. Click the _Start immediately_ button to launch the campaign. For a delayed start, select the _Schedule_ button and set the date and time of sending.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bb9553e2c2d8099a20ee39824a017274bdaacf74fb852fbb5b75226193dc082-starting-5.webp",
        "Preview",
        "Send options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]