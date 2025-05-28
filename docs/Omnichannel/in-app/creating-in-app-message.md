---
title: Creating In-App Message
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating In-App Message | Yespo Guide
  description: >-
    This guide explains how to configure In-App notifications, a feature that
    allows personalized content to be delivered directly within a mobile app.
  robots: index
next:
  description: ''
---
In-App messages are messages that are displayed to the user while they are using a mobile app. You can define the content of the message and the rules for its display to target the message to a specific audience.

> 📘 Important
> 
> [Install SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo#1-install-sdk-and-connect-communication-channels) to send In-App messages through Yespo

<br />

To create a new message:

1. Go to the _Messages → Messages → In-App_ section. Click the _New In-App_ button.

   [block:image]{"images":[{"image":["https://files.readme.io/0a0017e2addd7b78d10c0508353b14dbd57cc226c21922d2305b47092a114f0b-image1.png","","New In-App"],"align":"center","sizing":"600px"}]}[/block]
2. Select the message type:

- **Fullscreen**
  - blocks app content
  - closes by pressing the cross icon
- **Popup**
  - blocks app content
  - closes when tapping outside the message or by pressing the cross icon
- **Slideup**
  - has top or bottom positioning
  - does not block app content
  - closes by swiping left/right and up/down depending on the positioning or by clicking on the cross icon
- **Floating Bar**
  - has bottom positioning
  - does not block app content
  - closes with a swipe left/right/down or by pressing the cross icon

All of the above message types are created in a drag-and-drop editor. You can also use the HTML editor to get more options for customizing the message content.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb44aa4e8e63c9e19a725ccff3cb44bdfbfd28983262e5f65146133327b43914-image2.png",
        "",
        "In-App types"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> All In-App message types are supported in SDK versions starting from Android 2.5.0/iOS 2.5.0.

## Working in the Drag-and-drop Editor

Let's look at creating a full-screen message - the functionality of other In-App types is identical.

The components for building the message are located in the left-hand side panel. To add a component, drag and drop it to the editor field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45e46d75d364db4b73fb0ab059d7cf5a9add9574e34766b389e173f948398b93-add_component_en.gif",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


_Columns_ and _Container_ can contain other components, except for the _Floating image_ component.

_Floating image_ overlays other components. It can be used, for example, to emphasize a specific element.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70556109b02ca4fdf508484f5d0eb7887925e5dc6bfca4bc23ee539b2b6d3438-floating_comp.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


The right-hand side panel of the editor contains a menu with editing options for each component. Click the relevant component to display its menu.

To return to the main layer menu of the editor, click anywhere outside the components.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa735c1963f454898c65c9f60bb1bbd7c59e1c99c493b038704067e649828c92-first_layer.gif",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


The following settings are available for the components.

### Action on click

Expand the _+Add Action_ menu and choose the action to be performed when clicking on the element:

- _Open URL_
- _Use click tracking_
- _Close the current message_

You can add one or several actions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3b2657be94159dd62eae029166c069fc1bc7351824fed4ecf6482363f6f952a-action_onclick.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Align Inner Elements

Select the appropriate icon for aligning elements within the container or columns.

Enter the value for the distance between elements in the corresponding field. The minimum value is 0.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/44d8225f6f5e0f951168185e6edaebc4ee7595577770105cda0f3ad3671ccd33-align_inner_elm.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "605px"
    }
  ]
}
[/block]


### Size

Expand the drop-down lists and select the necessary sizes from the following options.

**For width:**

- _Fixed width_. The minimum value is 20.
- _By container width_.
- _By content width_.

**For height:**

- _Fixed height_. The minimum value is 20.
- _By container height_.
- _By content height_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be72af06abaf5a0edeb20ff2752c6eeb31c8f98a45bfb53f94b030d5b9b90554-size_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Columns

For the \_Columns \_component, you can choose the following settings:

- _Equalize width_. This option sets equal width for all columns.
- _Number of columns_. Select the number of columns from 1 to 8.
- _Spacing between columns_. Enter a number in the field to set the distance between columns in pixels. The range is from 0 to 40.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/797ef59f56f5c99ece63ee06af5fcd1db8e4f5a4efd97dfb970e475f4dc4140a-columns_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Stack Vertically in Portrait Mode

When this option is enabled, the columns are displayed vertically when the message is viewed in portrait mode.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a00b06749bf8d08c1653690b7421cde0248eb3821ec43cc2a2f677490278e2cd-stack_vertically_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Background

To select the background of the component, activate the \_Background \_slide button and choose one of the following options:

- \_Image \_to upload your pictures or select from the built-in library.
- _Color_ to choose the desired color from the palette or enter its code manually.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee67cf030fcec6f96ed656e21fb682870aa7f747dde1fd258a8b687b16aa1534-background_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Background Blur

The acceptable values for background blur range from 0 to 100.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a234c06181d11261a5c74ebe9e25639d07093a9fd053fa74afa292b94b8bb7dd-background__blur_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "595px"
    }
  ]
}
[/block]


### Stroke

Activate _Stroke_ to set formatting for the outer contour of the _Container \_and \_Columns_ components. You can set the same stroke format for all sides at once or for each individually by choosing:

- _Stroke Type_: solid, dashed, dotted.
- _Thickness_: Acceptable values are from 0 to 100.
- _Color_: Choose it from the palette or specify manually.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d609fd4f43935cdded92b44eb60cad0bad86f722ef1fcbd50c76115776a055b8-stroke_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Shadow

Activate the slide button to set shadows for the component. The following settings are available:

- Vertical (x) and horizontal (y) spread.
- Blur.
- Size.
- Color.

Hover over each value field to see its minimum and maximum value.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45b2739c84a33d7c65bdc218ac634e5ef100deb0bef2f3bc8d0c262640597ee5-shadow_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Round Corners

This option allows you to set the value for rounding the component's corners.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c33a0115a5000bdf75c72206ac370d7567895dfa5f75dd046c88d19cc402205c-round_corners_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Text Formatting

Select the component that contains text to access the formatting menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ec9aed7262c884079051b56a0e7326e9006ab7c94b727408ee2c3f40e4f4a33b-text_menu_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Icon

For the \_Button \_component, you can add an icon with the following parameters:

- Size
- Alignment
- Distance before text

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d8710a73bf34de32b97d71dd21e527ecea0ea9cf9bc223bcd81a71b7dd007b40-icon_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Hover Effects

Activate the slide button to make the button more interactive when hovered over or tapped.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3447711389f5f5138336d3316668578dacca4eb7309e58eb02b0905930f67a7-hover_effects.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Loop Animation

The _Loop animation_ option allows you to choose the following parameters for the _Button_ component from the drop-down lists:

- Animation type.
- Number of repetitions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7de2cccd2d6673b7b385c46e99a9c3f8aa8c7d4bcf87762ed849dbea4cf15786-loop_animation_en.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Slider

Drag the slider from the left-side panel and drop it into the message template. _Set up slider_ and _Manage slides_ buttons will appear on the right-side panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9868f77b1dbb7befff1df293994fdae59664e85f82b02f90a8b5c6f0b56920cb-image2.webp",
        null,
        "Slider settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In the slider setup window, you can set up navigation buttons, indications, slideshow animation, and the slider's general design.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/74aeb9f54faf1f760ccfe7e5e51beea8b7ae7c0350145dad8798126f5e0881f4-image3.webp",
        null,
        "Slider setup"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Manage slides’ order, add, duplicate, or rename slides after clicking the _Manage slides_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc81a33ab5b894f5de67954b128fbd3ee06d12fa095215bebb282f675d44a20b-image5.webp",
        null,
        "Manage slides"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Also, you can add a slide by clicking on the + sign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10fbdfc2756a880aab5f134f6bf6090cea3991624027f6a2e6815f83e41c030a-image4.webp",
        null,
        "Adding slide"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To change or edit an image, click on it in the template, after which it will appear in the right settings panel. Clicking on the image from the slider in the settings panel opens the editing window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/848f36d1061ae2736922fb5ba006b699a7821f78c29b7d4c872aa8d1adc6e0e6-image1.webp",
        null,
        "Image settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use navigation buttons to switch between the slider’s images.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9519d2e8b1a123078e2fdc0dd8b0c7eec2f802f4e43f0173c67cd71d60499d12-image8.webp",
        null,
        "Navigation buttons"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Set the action on click:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a6fb776efc52517c8ef7795b29850cb0e6f49e696649c2753cf921121f8cbc1-image6.webp",
        null,
        "Action on click"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Context Menu

A _Context menu_ becomes available upon right-clicking on the message component with the following actions:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1dfd550b03ae77c8770cb9906c7cf704fa8658264cb95a8400b56faab2a024e-creating-in-app-message-16.webp",
        null,
        "Context menu"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Copy
- Duplicate
- Cut
- Delete
- Put behind all floating images
- Put in front all floating images
- To container

### Close Icon

The _Close_ icon allows the user to close the message.

You can use standard and custom icons with settings for color, size, and positioning on the screen.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/74390e1af1073b3b3ebd7cf8c53e8c26ae423d7b45359b94c9f439f99ae54fa8-close_icon.webp",
        null,
        "Close icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The position of the _Close_ icon is calculated from the top-right or top-left corner of the message.

### Message Orientation

The message can be displayed in Portrait or Landscape mode, depending on how the user holds the device (vertically or horizontally).

To see how the message will display on the device, click the Orientation icon at the editor's top.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b35064f5e9bf54e95cde2ce74440c7816d2512c09a934afe01798a16a006d456-creating-in-app-message-18.gif",
        null,
        "Message orientation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Press the _Save_ button on the top panel of the editor to apply the changes after configuring the In-App message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b8841f8f621dd6b1984584d0623c44ee626f9cd49936d16e19c4471ab8a8037b-creating-in-app-message-19.webp",
        null,
        "Save button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Fill in the _New Message_ field. This field is available for searching messages in the general list; users will not see it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8c64b40e7d6c0d7dd72814a09bb1bbd96511dc30284ea012cdf66f825e6ad047-save-in-app-en.webp",
        null,
        "\"New Message field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## HTML Editor

This method of creating In-App messages is more labor-intensive and requires specific technical skills in working with HTML and CSS; however, it provides a more flexible approach to customizing message content.

Fill in the _In-app name_ field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/16b1c00ab024d08c13bfafd56eb599a1da90a724f539e497c496b4a43a6e53cb-creating-in-app-message-21.webp",
        null,
        "In-app name field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### HTML Settings

Open the HTML tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc9c3a0d5d8eb55a5db37756064829f19fb25a17a20bf09ce376e820ac6fa8cf-creating-in-app-message-22.webp",
        null,
        "HTML tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can put your HTML code or use our base code.

#### Using base code

Copy and paste the base HTML into the code window. Insert your code instead of Your code goes here text.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9959586855c99a13f5147bb601e16e716d1a966ce5ff75045fb00903a8bbce7c-creating-in-app-message-23.webp",
        null,
        "Copy and paste the base HTML"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> You can use [personalization by merge tags](https://docs.yespo.io/docs/personalization-and-dynamic-variables) and [Velocity features](https://docs.yespo.io/docs/introduction-to-velocity) in the HTML code of In-App messages.

#### Custom HTML markup rules

1. Use buttons instead of anchors

> 🚧 Attention
> 
> Usage of Anchor HTML elements is forbidden.

2. Set data attributes for the clickable element

Each clickable element must have the required data attributes.

- **Code of the button that should open the URL:**

```html
<button 
                data-target-component-id="1c92f19e-c994-11ed-afa1-0242ac120002"
                data-sys-action-type="OPEN_URL"
                data-sys-action-params="{"url":"https://google.com"}"
                class="button">
</button>
```

- **Code of the button that should close a widget:**

```html
<button
                data-target-component-id="c740db99-cfbb-4857-b790-cb5631c33255"
                data-sys-action-type="CLOSE_WIDGET"
                class="close-button">
</button>
```

[block:parameters]
{
  "data": {
    "h-0": "Attribute name",
    "h-1": "Attribute value",
    "0-0": "data-sys-action-type",
    "0-1": "One of action:  \n    • CLOSE_WIDGET  \n    • CLICK  \n    • OPEN_URL  \nCLICK and OPEN_URL are counted in the statistics as clicks, CLOSE_WIDGET — no.",
    "1-0": "data-target-component-id",
    "1-1": "Generate a unique element’s UUID (e.g., using <a rel=\"nofollow\" href=\"https://www.uuidgenerator.net/\" target=\"_blank\"> Online UUID Generator</a>)"
  },
  "cols": 2,
  "rows": 2,
  "align": [
    "left",
    "left"
  ]
}
[/block]


3. Use Margin Top 50 px (approx) so the content does not overflow the iOS devices panel.

### CSS Settings

Open the CSS tab and add CSS rules in the code window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75777736bae5d6cd60e373a4102bd4e9a19cda2aabec8f6af93c4e1a94384967-creating-in-app-message-24.webp",
        null,
        "CSS tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Adding CSS code is optional, but custom HTML is usually displayed incorrectly without CSS.

After adding the code, press the _Save and exit_ button on the top panel of the editor to apply the changes.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e8cce197276e1a281abc1d873b79e41422f0f271cbf5a4cb1c7e9f737479837e-creating-in-app-message-25.webp",
        null,
        "Save and exit"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Messages created using the HTML editor are marked with the corresponding icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d24bc8a8fca301798e865e3018190627df45c2bf3bab1f3917297bcf35e8da4d-creating-in-app-message-26.webp",
        null,
        "Messages created using the HTML editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Multilingual Version (optional)

You can create [multiple language message](https://docs.yespo.io/docs/multilanguage-overview) if this option is available in your pricing plan. Click the globe icon in the editor's top panel, specify the default language, and add language versions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1713dd9e7d32407b090825354541b00a8a37e674bb7b8b8dfda12896cb1558f0-creating-in-app-message-029.webp",
        null,
        "Multilingual version"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When adding a language version, the automatic translation option is enabled by default. To translate manually, disable it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2df8779eee41a1ec67d3f2784f195dcf364863f01a16d6b71c540dd7b331804-translate.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The language is determined by the device language, and not by the one written in the contact card.