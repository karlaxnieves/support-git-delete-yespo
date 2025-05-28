---
title: Setting Up Permission Request Prompt
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Permission Request Prompt | Yespo Guide
  description: >-
    This guide provides instructions for configuring web push notification
    settings, including permission request prompt types (Double Opt-In or Single
    Opt-In)
  robots: index
next:
  description: ''
---
In your account, go to _Settings_ → _Web Push_, select the site, and click _Edit_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e27ed57ee54d0a7e36312ebc30b741929c0956a852f000eb249058374742abf9-set-up-request-prompt-001.webp",
        "Edit permission",
        "Edit permission"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Permission Settings

In the _Permission settings_ window, the active tab will correspond to the [type of subscription](https://docs.yespo.io/docs/how-send-web-push-notifications-website#selecting-a-subscription-type) you selected when adding the website to your Yespo account. If you select _Double Opt-in_, the _Custom dialog_ window type will be active by default.

If necessary, select another type and proceed to the settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8df3b6850a48397cb867159c52765cdfb3d3df68fd716e72fcb7f730e9d30fba-set-up-request-prompt-002.webp",
        "Permission Settings",
        "Permission Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Activate the _Show prompt sample_ to preview how the request will look.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa3ba75c737b08d5ada9265ded2d92d1171898f11bab1fa6a567cc42967def60-set-up-request-prompt-003.webp",
        "Show prompt sample",
        "Show prompt sample"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Double Opt-in

The advantage of the double opt-in subscription is the ability to customize the appearance of the subscription and confirmation windows. In this case, a user will first see your customized window, and then the standard one.

There are three types of double opt-in subscription windows:

- **Widget** — a window with an icon that appears in the bottom right or bottom left of the browser.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f26c377cee6b40403932f3dc58c6c3613c1ac1c875469286a215c56ca2c88be-set-up-request-prompt-004.webp",
        "Widget",
        "Widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **Custom dialog** — appears in the top left corner of the page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9779bff77aaaa7df88f87833b6f071862a71144a6d847626de6bf1a6d10eee6f-set-up-request-prompt-005.webp",
        "Custom dialog",
        "Custom dialog"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **Panel** — a bar that appears across the full width of the page, at the top or bottom.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eefe86970b4fcd47d7d2dbf80d1bd51aa0e2099e34e013b412ba58394f1b7d9f-set-up-request-prompt-006.webp",
        "Panel",
        "Panel"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Let's consider the settings for each of them.

#### Widget

The widget will remain on the screen until the user allows or denies receiving push notifications. After the reminder, users who have unsubscribed will be able to turn on notifications again.

The following settings are available for the widget:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ebda8c1278184f67ca40bb7794b88526bc2ed3325062cb2e5fd5c8fd79389d21-set-up-request-prompt-007.webp",
        "Widget settings",
        "Widget settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


1. **Background color**: Select the background color of the widget icon from the palette, or enter the code in HEX or RGB format.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/209333a40f6155d835fb0e141d7bd4de5dcb42252ac9ef4786fe77a4aeadb8ab-set-up-request-prompt-008.webp",
        "Background color of the widget icon",
        "Background color of the widget icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. **Icon**: Click _Change image_ and select an icon for the widget in JPEG or PNG format, up to 200 KB in size.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/810027fbe007729c97651c90d15058a49b955d088192994e1db54639548c3a0a-set-up-request-prompt-009.webp",
        "Icon",
        "Icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. **Placement**: Bottom left or bottom right corner. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0424b86343454222be1dfdb17ff250cbb24fc30a475ddf9429a1d2b9861e258b-set-up-request-prompt-010.gif",
        "Placement",
        "Placement"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Set the widget's paddings — from the side or bottom. The maximum value is 300 px.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5e3cb90cde1cbc913f91add1790022b524d3da0ed8e65beed9c567d70e5bb29-set-up-request-prompt-011.webp",
        "Widget's paddings",
        "Widget's paddings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. **Animation**: Select the type of animation to attract extra attention.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60fb3da179f4c79573e799396c00241a5103cd4e86400e6b6685d91ca662ecd3-set-up-request-prompt-012.gif",
        "Animation",
        "Animation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. **Show unblock reminder**

Activate the option so that users can see the actions they need to take if the subscription request is blocked.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9add3faf50e4fcf9cdc1ddc13f3a92b6722f3e40723df891422fc24431bfe296-set-up-request-prompt-013.webp",
        "Show unblock reminder",
        "Show unblock reminder"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The following settings are available for this option:

- **Widget text and reminder text**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c785fbcc2b234cb87eb4d28847fd6314506c3fdfaa032b6c6af03858da5dfcdc-set-up-request-prompt-014.webp",
        "Widget text and reminder text",
        "Widget text and reminder text"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **Reminder display**: right after or a certain period after blocking.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b68e6bc33b54e0a098912729da14e736e1e6aee513ba452cced177982b0c886b-set-up-request-prompt-015.webp",
        "Reminder display",
        "Reminder display"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Activate the _Preview_ switch to see how the reminder will look.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e2b1ca8a3d53089230e22207799784f23c2979a24ef498e7093871ee8bb67aaa-set-up-request-prompt-016.gif",
        "Preview",
        "Preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. **Permission prompt and button text**: Click the text field and enter the information that will be displayed on the buttons and in the prompt.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed4fc98c35516830fef246019d238a4e79cebb334549c08219ea2260b6b57b6d-set-up-request-prompt-017.webp",
        "Permission prompt and button text",
        "Permission prompt and button text"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


7. **Text color, background color, and button color**: Click the corresponding field, select a color from the palette, or enter the code in HEX or RGB format.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dbb7ac096450bf9c10f87c90694c8e5e1bb541cc5fa46545e5f2be3720c81097-set-up-request-prompt-018.webp",
        "Text color, background color, and button color",
        "Text color, background color, and button color"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


8. **Permission display**

Set the parameters:

- Show upon: page load or click.

If you set Show upon click, the request window will appear after the user clicks on a specific element on the website (banner, button, etc.). Add class="es-push-prompt-init" to this element in the website’s code;

- Time delay after entering the website before prompt display. The maximum value is 1000 seconds.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/021685d00a823cf07c82b849ea596e050582e671bcbd9ad158bc2166aa79b90e-set-up-request-prompt-019.webp",
        "Permission display",
        "Permission display"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Multilanguage

Use the multilingual option in widgets to automatically address users in their languages. [Learn more >](https://docs.yespo.io/docs/how-set-multilingual-browser-push-notification-permission)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/51ae05861b401227066b868154b2c63ce5e03bbbb3f0b7c9ee30c67ee7e73d47-set-up-request-prompt-020.webp",
        "Multilanguage",
        "Multilanguage"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Custom dialog/Panel

They have similar settings, with one difference — for the _Panel_ window type, you can select the placement of the permission prompt: top or bottom

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a41240e0941700e3b4785157f1ab7a059b46561fbf44169c16f520199d70d09a-set-up-request-prompt-021.webp",
        "Custom dialog/Panel settings",
        "Custom dialog/Panel settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The method of changing the settings is similar to that of the _Widget_.

### Single Opt-in

The default browser window, where you can only configure the _Permission Display_ option.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd1ba7c8b0f1d640d97fa99969f3e85f1e5332c99ef8d72a5a96466868d956ed-set-up-request-prompt-022.webp",
        "Single Opt-in",
        "Single Opt-in"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _Save_ button in the top menu to save the subscription request settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/28fb4e384a58dfac0e2dde5c8df73f74d2668cbcdd318ededb12660ad92311cd-set-up-request-prompt-023.webp",
        "Save button",
        "Save button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Features of Permission Settings for Safari

In the general subscription request settings window, you can also add your custom brand logo, which will be displayed for Safari users on macOS. For subscribers using other browsers, you can set any other image while [creating the messages](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications).

Click _Change image_ and select a logo for Web Push in JPEG or PNG format, with a size of up to 200 KB. The image must be square-shaped with a minimum resolution of 256x256 px.

[block:image]
{
  "images": [
    {
      "image": [
        "https://cdn.yespo.io/photos/shares/Support/Images/Set-up-request-prompt/set-up-request-prompt-024.webp",
        "Features of Permission Settings for Safari",
        "Features of Permission Settings for Safari"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]