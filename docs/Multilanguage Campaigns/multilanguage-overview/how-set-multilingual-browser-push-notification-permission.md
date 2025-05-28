---
title: Setting Multilingual Browser Push Notification Permission
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Multilingual Browser Push Notification Permission | Yespo Guide
  description: >-
    The document provides instructions for setting up automatic language
    detection for web notification confirmation prompts, detailing how the
    system determines the user's language and how to configure default and
    alternate languages in the widget settings.
  robots: index
next:
  description: ''
---
Set automatic language detection for the [web notification](https://docs.yespo.io/docs/web-push) confirmation prompt.

> 📘 Note
> 
> The option is available for _Widget_ requests.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/382301bc2c0b3d691a1f6e66b3c4c07cfb3f8c5ddf5e1ccb5bf1987491fe3c8a-yespo_permission_settings01.webp",
        "",
        "Widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


**To determine the user's language, the system checks:**

- the _lang_ attribute in the HTML code of the site;
- if it isn't set – the language in the link (eg, "_/en_");
- if the language parameter is not specified in the link, the system checks the language of the contact's browser;
- if the user's language is not defined, the system will display the default language that you specified in the widget settings;
- if the user's language doesn't match any of the specified widget languages, the default language will be used.

## Set Up Instructions

1. Go to the _Settings_ → _Web Push_ tab → _Permission_ settings in your account settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5736ddb479f2f7be5639d1a368eb5639e435468c4d3da05ae3cf619c35d27239-yespo_permission_settings02.webp",
        "",
        "Permission settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the prompt type _Widget_. Click on the _globe_ icon and select the default language from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09c93cd13fd20d6e99eba1631ea24930522730b2562488142730e8e79677cc5e-yespo_permission_settings03.webp",
        "",
        "Selecting default language"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> The appearance of the subscription prompt is set only in the version with the default language. Then it's automatically applied to other language versions.

3\. Once the prompt with the default language is customized, select the alternate languages you want. Сlick on the _Add a language_ button and select the required language versions from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/44834e5324a1978ccaeb5391fdbd07a5463e68f901058033e6a03333670efc38-yespo_permission_settings04.webp",
        "",
        "Add a language"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Write the copy for subscription request, blocking and confirmation buttons in the appropriate language for each version. Save your changes.

To see the sample of each prompt version, activate _Show prompt sample_ switcher.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/843b7b6b0950fb9053d504e8f0357c3dd24942b581e6554b675309112ccbd8ba-yespo_permission_settings05.webp",
        "",
        "Activating Show prompt sample switcher"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More on web push permission settings >](https://docs.yespo.io/docs/how-send-web-push-notifications-website)