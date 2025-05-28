---
title: Creating a Viber Campaign
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating a Viber Campaign | Yespo Guide
  description: >-
    The document provides a detailed guide on creating and sending Viber
    messages using the Yespo system, including steps for setting up message
    content and personalization, testing messages, and launching campaigns with
    options for multilingual versions and additional settings like UTM tags and
    SMS fallback.
  robots: index
next:
  description: ''
---
[Add a sender ID](https://docs.yespo.io/docs/how-add-sender-name-viber) to send Viber via the Yespo system. You can do this in one of the following ways: 

- via message editor, 
- via account settings, 
- via sending a request to the sales department [info@yespo.io](mailto:info@yespo.io)

## Creating New Viber Message

Go to _Messages → Messages → Viber_. Click the _New Viber_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e24a72619ec269d1772d38fd3c1adb60114e96d7d4d1b4ac71934b15edb4520-new-viber-01.webp",
        "",
        "Creating Viber Message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Main settings

Fill in the following fields:

1. _Name._ The system name that the recipient will not see.
2. _Sender_. Sender ID that was added to the system. Users will see it as the sender of the message.
3. _Message type_. You can use a few types for different purposes:

- _Transactional message_ — contains only text.
- _Promotional message_ — can contain text, an image, and a button. Providers charge higher prices for promotional messages than for transactional messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad46596192c999708faa1a7412234fd00f4466c92e123ec1c1a160b70451a658-image02.webp",
        "",
        "Main settings: Name, Sender, and  Message type fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 🚧 Important
> 
> Before sending, Viber should approve the transactional message template. Messages with unapproved text will not be delivered.

4. _Text_. The main content of the message. 

It can include:

- Up to 1,000 symbols;
- Emoji and special characters;

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3679e3f323607d3143acc60cbd4784ce80704f129009365c8e79846dc0ccaed-emodji-viber-en.webp",
        "",
        "Emoji and special characters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Clickable links;
- Clickable phone number.

> 📘 Note
> 
> Tracking is fixed only for clickable `http://` and `https://` links.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/051534077528525f05933553fc89b91a7fcbcb33032a27b11d3f2a7fcadc6907-image03.webp",
        "",
        "Main settings: Text field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. _Personalization_. Use the dynamic variables to add a name, city, bonuses or any personal data available in the [user profile](https://docs.yespo.io/docs/user-profile). Click on the _Personalization icon_ in the _Text_ field to select data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cbc7693b9d755847791ff0cc1b3f6b691b20b3b675b082e011d5bb4a9ade6678-image04.webp",
        "",
        "Personalization"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. _Image_. Upload JPEG or PNG file up to 2 MB. It is better to use square images (1:1 aspect ratio). When zooming, the image will be fully displayed on any device. You can also use a [variable](https://docs.yespo.io/docs/introduction-to-velocity) or a link to the image. Use only the `https` protocol for direct references in expressions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9cb5ef24dec4b76c3d6d39643a4f078fef46b42de9244c3b6884a8ee0b857ada-viber-image.webp",
        "",
        "Main settings: adding Image"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can edit the image directly in the editor when uploading (if it does not meet the requirements) or after uploading (the _Edit_ button). After editing, the image is saved in _PNG_ format.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f4351a6ff7f6dcb43d283763d498e2d3885fb97c57f42c1d55d75e3205276914-image-editor-viber-en.webp",
        "",
        "Image editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


7. _Button_. You can add one button with the following parameters:

- _Name_ — display text on a button.
- _Link_ — a website link, phone number, Viber, and other.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e7a37fd7611ddc40d747f8bbd26ca2a83d6812eb56e3bb70455e770bf6d1778-image06.webp",
        "",
        "Main settings: adding button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Tracking is fixed only for `http://` and `https://` links of the _Site_ parameter. For _Viber, Tel_ and _Other_ parameters tracking is not fixed.

8. _Tags_. Select tags from the list or enter a new one and click _Enter_. Use [tags](https://docs.yespo.io/docs/how-add-tags) to filter search results and set [campaign frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6358fc9d246f4bfed170ebe5c6e1c0b6a1eae2ba32786818c87041a2fb097cf5-image07.webp",
        "",
        "Main settings: adding tags"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Additional settings

Fill in the following fields:

1. **Subscription categories.** Manage [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) to send messages to your contacts based on their preferences.
2. **Time to Live (TTL).** TTL — the period after which the message will not be displayed if it has not been delivered by this time. By default, it’s 1 day, but you can select other options.
3. **UTM tags.** [UTM tags](https://docs.yespo.io/docs/how-transfer-utm-parameter) are enabled by default. The switch activates the setting for all language versions when sending multilingual messages. You can manually add custom UTM tags to the message URL.
4. **Send SMS if Viber is not delivered.** If you use the services of a [Viber provider](https://docs.yespo.io/docs/how-add-sender-name-viber#adding-an-existing-sender) (except Kyivstar), you can automatically send SMS to contacts who do not have a Viber account. To do this, activate the appropriate option and enter the text of the SMS message. The sender of such SMS can only be the same as for Viber campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa703475ecf2860d456c5c779e01835119cfa68ff73019d060bb39b66ec60be0-ev.webp",
        "Additional settings",
        "Additional settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> If your account does not have the _Send SMS if Viber is not delivered_ option, please send a request for activation to [support@yespo.io](mailto:support@yespo.io).

### Multilingual version (_optional_)

In our platform, you can create a multilingual version of any message. Click the _Globe icon_ in the top panel, specify the default language, and add language versions. Fill each version with the content in the corresponding language. You can switch between versions within one template in one click.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2193f7f7276c8c214a5bd37ba6e4970705631b443ddd30b6ddfda567b615cd43-image11.webp",
        "",
        "Creating a multilingual version"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[Learn more about multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

## Testing Message

1. Test the messages by clicking the _Test button_ on the top panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c5348923dfa2552d6eee353f3635fa2e80957de89b2a3dfe501e2c5010924ed-image09.webp",
        "",
        "Test message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In a popup window, enter a phone number or select it from the _Choose contact_ tab and click _Send_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2990d77b109e2f02684e1be974fc7f75d58a394616c1f73b08883033eaf1f150-image10.webp",
        "",
        "Sending test message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Creating Campaign

1. Click on the _Create campaign_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe9178c676a02e723c5a3510c52aa7b67bf02760b82a91ea837d8ebaffdd6b5d-image12.webp",
        "",
        "Creating campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In a popup window, choose segments or contacts for the campaign. Click _Go to campaign_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4a6e7892d713e65199fef6e2b72ac568409e37bf1e8809db2ef07d3e2fce3185-image13.webp",
        "",
        "Choose segments or contacts for the campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. On the general checkout page:

- In the _Segments_ section, click _Recalculate contacts_ to see the total number of contacts that will receive the notification. You can also edit segments or select new ones.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/56b5f8998fa1efbdbb4873d1a14bcba0928891b5547e475d2895d953ebe86127-image14.webp",
        "",
        "Segments section"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- See all the necessary information for verification: _Name, Subscription categories, Message activity time_. You can see how the message will look on different platforms (Android, iOS).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a1ed5b83540e977ab7518b0880ea397494e87ae399ba83ad83710095933af8b-image15.webp",
        "",
        "Viber preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In the _Send options_, you can set the batching. Click the _Start immediately_ button to launch the campaign. For a delayed start, select the _Schedule_ button and set the date and time of sending.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dfbc8a53f68b727e8022d4089c30ab53b6b53583dd3e965fba8eab9f0554f921-image16.webp",
        "",
        "Send options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]