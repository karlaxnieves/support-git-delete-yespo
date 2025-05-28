---
title: Using Annoyance Safeguard
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using Annoyance Safeguard | Yespo Guide
  description: >-
    The document explains the Annoyance Safeguard feature, which manages
    floating widgets to avoid simultaneous display. Set silent intervals and
    choose from three rules: Show, Sequence, or Hide.
  robots: index
next:
  description: ''
---
When you show floating widgets on your site, they may show simultaneously or immediately one after the other. This may cause annoyance to the site visitors, and they may leave your site in a short time.

You can use our Annoyance Safeguard to avoid such situations when setting the displaying rules for the following floating widgets:

- Floating box
- Floating bar
- Popup

## Setting Silent Interval

To set the value of the silence interval for all widgets:

1. Expand your account menu and select _Settings_ from the dropdown list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/35374a2cbd127089e997103c54fe60cadfc320f6d9a3e4bb777673d7c183228a-account_settings.webp",
        null,
        "Opening account settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select _Web Widgets_, and enter the _Silent Interval_ value into the field.
3. Click the down arrow beside the silent interval value, and select one of the following units from the list:

- pageviews
- seconds
- minutes

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b00e5574c00360f7c675125e18f299f137005d0a06af918403412722cc0e4c91-web_widget_settings.webp",
        null,
        "Setting Silent Interval"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The default value of _Silent Interval_ in _Annoyance Safeguard_ is 3 minutes.

## Setting Annoyance Safeguard

To set Annoyance Safeguard for your widgets:

1. Go to _Site_ → _Widgets_ and create a new floating widget or select a floating widget from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff393bb537aea5154502482719aa40610ae7bc2900e746997670b647aafd375c-site_widgets_menu.webp",
        null,
        "Selecting the Widgets menu"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the _Parameters_ tab and click the _Edit_ button in the _Widget calling_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1d1525b61a21d4ae08718ac7302cabd18859e34273bef1f6d0d3bc571f69e90-widget_calling.webp",
        null,
        "Selecting to edit parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select one of the rules in the _Annoyance Safeguard_ section, then click _Save_ on the top panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f6b99039721128051df321699627fe758c54f2dcdfc48a4e93eac6b7746e6834-asg_settings2.webp",
        null,
        "Selecting Annoyance Safeguard rule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


There are 3 rules for displaying floating widgets you can select from:

- **Show:** The widget is displayed on the site, even if another one is being displayed at the same time. You can apply this rule to the widgets that must be shown on your site, such as information about site maintenance.
- **Show in sequence using Silent interval:** If another widget is being displayed, the widget will be displayed after that widget with a holding time set in Silent Interval. You can apply this rule to the widgets you want to show in sequence, without causing annoyance to site visitors. 
- **Do not show during the current session:** The widget is displayed on the site if no other widget is displayed at the same time. The widget is not displayed on the site if another widget is currently on the screen, or when the silent interval is active.

> 📘 Note
> 
> - By default, the _Show in sequence using Silent interval_ rule applies to all new and unpublished widgets.
> - When the _Show in sequence using Silent interval_ rule is applied, the widgets with more precise settings are shown earlier.
> - The _Show_ rule applies if you have 2 or more published widgets.