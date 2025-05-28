---
title: Integrating with Telegram Bot
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integrating with Telegram Bot | Yespo Guide
  description: Learn how to integrate your Telegram bot with Yespo
  robots: index
next:
  description: ''
---
> 📘 Note
> 
> Telegram bot is required to enable the channel

To send newsletters in your Telegram bot using Yespo, do the following:

1. Create a bot in the <a rel="nofollow" href="https://telegram.me/BotFather" target="_blank"> @BotFather</a> service, copy the access key, and upload it to Yespo.
2. Configure a service on your side that will accept contact tokens from your bot and pass them to Yespo. You can do this in any way that is convenient for you (see the implementation example <a rel="nofollow" href="https://python-telegram-bot.org/" target="_blank"> at the link</a>).

## Access Settings

1. Open <a rel="nofollow" href="https://telegram.me/BotFather" target="_blank"> @BotFather</a> in Telegram.
2. Send commands

- `/start`
- `/newbot`

3. Follow the instructions to set up the bot.
4. After creating the bot, you will receive an access token. Copy it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a189e00636a07e94da93a6b53eeaf6f2bb1d7aaa1a9b78b2af039ac94326dea-bot-1.webp",
        "Copy token",
        "Copy token"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Go to your Yespo account settings → _My bots_ tab and click _Connect Telegram bot_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/82b7d4ff192deee640c3eda1a64f1db2b3cb6a44d4d9e9337245b9bb83cc4f38-bot-en-01.webp",
        "Connect Telegram bot",
        "Connect Telegram bot"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Enter the token in the corresponding field and click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7dcddefdd1393165e5a8f9c3a2bb3de83e33112fe8d197331ae21ff5844ed45e-bot-3.webp",
        "",
        "Enter the token"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To integrate the already existing bot:

1. Go to _My bots_ tab and click _Connect Telegram bot_.
2. Click _Connect existing bot_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5086718e35b3366456f2356a768680a31283f7e8a702a72b44d9a4cdd9884e3e-bot-4.webp",
        "Connect existing bot",
        "Connect existing bot"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Enter the _`/mybots`_ command in the @BotFather chat, select an existing bot from the list, copy its token, add it to the corresponding field, and click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50f0fdb766830cc5d0043ef88c0f04f3a2442f6269685407988c79b74f21e7d1-bot-5.webp",
        "Enter the token",
        "Enter the token"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After connecting the bot, you will receive an application ID (**app\_uuid**) - it must be used in the URL to send a request for adding and updating tokens of your contacts in Yespo: _`https://yespo.io/api/v1/apps/{**app_uuid**}/tokens`_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5570feacb3bebbf11833de667c0d8b4816331f00aa1d02ea2e5cc8d45421bd65-bot-en-02.webp",
        "App ID",
        "App ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The number of subscribers of the _Telegram bot_ is shown to the right of the bot's name.

## Creating and Updating Contacts

To add or update contact tokens, use the [Add application tokens](https://docs.yespo.io/reference/addapptokens) API method (POST type).

**JSON request format:**

```json
{
    "tokens": [Token]
}
```

**Contact data format in the request:**

```json
{
    "token": string,     // required
    
    // identifiers to search for contact (at least one is required)
    "contactId": Long,
    "externalCustomerId": string, 
    "phone": string,
    "email": string
}
```

**URL to send the request:** _`/v1/apps/{app_uuid}/tokens`_

- A contact is created with all identifiers if there is no contact with such identifiers in the system.
- If the identifiers already exist, they are not created or updated.
- Priority of identifiers for searching contacts in the system: contactId → externalCustomerId → phone → email.
- If a contact is not found by any of the identifiers — contactId → externalCustomerId → phone → email — a new contact is created with all the provided identifiers and the token.
- If a contact is found by any of the identifiers — contactId → externalCustomerId → phone → email — the token will be added to the existing contact. **Please note** that requests using the _Add application tokens_ method do not update existing tokens, but only create new ones. For example, if two requests with the same email address contain two different tokens, both will be written to the contact card.

To update other contact information, use the [Add/update a contact](https://docs.yespo.io/reference/addcontact-1) or [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) methods.

## Message Statuses

SENT, FAILED, and CLICKED statuses are tracked.

A token will be removed from the contact card upon receiving the FAILED (Forbidden) status, which is sent when the user blocks the bot.