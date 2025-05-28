---
title: Creating CTA Button
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating CTA Button | Yespo Guide
  description: >-
    The inclusion of a call-to-action (CTA) button is imperative for any email
    campaign as it encourages recipients to navigate to a website, social media
    platform, or other designated destination.
  robots: index
next:
  description: ''
---
The call-to-action (CTA) button is a mandatory element of [an email campaign](https://yespo.io/email-campaigns) that motivates subscribers to go to a website, social network, etc. The main button in the email is usually made in the same style as the buttons on the website.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/696d2f63687624943eb2168e96e5a92dc0e2aeac1a4a3a593882da2772049fe7-cta-1.webp",
        "CTA",
        "CTA"
      ],
      "align": "center",
      "sizing": "20% "
    }
  ]
}
[/block]


## Creating Button

You can add a button to a container or a separate email structure.

For the content to be rebuilt correctly in the mobile version of the email, for example, if you need to set the inversion of blocks, it is better to add a button to the container.

A structure that contains only a block with CTA will not be rebuilt relative to other structures and content elements in the email.

### Button in a Container

1. Go to the _Blocks_ item in the _Content_ tab on the left sidebar.
2. Select the _Button_ block and drag it into the desired container.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b10e9cca76818da18a96bcacc3e41548a04d1f0909b9309c646375fdf2a1ef09-cta-2.webp",
        "Button in a separate structure",
        "Button in a separate structure"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Button in a Separate Structure

1. Open the _Structures_ tab in the side menu on the left, under the _Content_ tab.
2. Drag the structure to the template, then select the _Button_ content type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c84d0317850eaf537ecea34e281093ca9b9e1cbd0cdf7b83f211a29a77570a8-cta-3.webp",
        "Button in a separate structure",
        "Button in a separate structure"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Editing Button Design

By default, the button is created without a link, with the text _Button_ in Arial 18 font, the button color is green #31cb4b, and the text color is white #ffffff.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a108585b1e89a7866a7261ed341266cb2315ea6180089b47c11ce59405c2830f-cta-4.webp",
        "Default button",
        "Default button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can edit the style of a single button or all buttons you will create.

### Editing an Individual Button

Click the block with the button. A menu will appear on the left, in which you can set the following parameters:

1. A link that will open when by click on the button.
2. Button text.
3. Text style (font, size) — we recommend using standard fonts, the display of which will not change depending on the device and the mailer.
4. Button color.
5. Text color.
6. Background color.

> 📘 Note
> 
> Choose colors that go well with each other and contrast with the button's background.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8cadc89bbdccfd0baa1ef72b6d8fed03f2df6356bda95111be297641a6641762-cta-5.webp",
        "Button parameters",
        "Button parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


7. Border radius. To enable the Border-radius property in Outlook, please activate the _Support of Outlook_ option in the _Appearance_ tab/_Button_ section.
8. Alignment (to set alignment settings on a mobile device, click the phone icon).
9. Fixed height (the button's height will not change depending on the device type).
10. Button with an icon (you can download an icon that will be displayed inside the button).
11. Adjust to width (the button will be displayed to the entire email width; its height will not change).
12. Borders (type of lines and their color).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d8b8dab7334f21918112085febc27f03ecb8b5f09f7e43a4c4d90ea3c9cb991a-cta-6.webp",
        "Button parameters",
        "Button parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


13. Internal padding.
14. External padding.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/66a70b3acd3e1e3a23a5b11379a27a161cfc928908eaab8bc5713da14a10988b-cta-7.webp",
        "Button parameters",
        "Button parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


15. Add an anchor link, clicking on which will take the reader to the specified section of the email.
16. Hide element on different types of devices. By default, the button is always displayed. To disable it on your desktop or phone, click the corresponding device icon.
17. Include in different types of email. Enable/disable the element for HTML and AMP versions of the email.
18. Event type. [Specify an event](https://docs.yespo.io/docs/how-add-scenario-button) that will trigger some action, for example, by clicking a button to send a message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a6d2dd599d3c85c84ea2895f5b9141fa836b0348d7cd5c600a08cc301a7953b-cta-8.webp",
        "Button parameters",
        "Button parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Save the button in the block library to use it in other emails.

### Editing All New Buttons

By default, the email button appearance is determined by the design styles specified in the template. To change the design of this element, you need to change the style of the entire email. Then, all the buttons that will be created after that will have the same look. [Learn more about the design of the buttons >](https://docs.yespo.io/docs/designing-your-email#button-section)