---
title: Creating a Welcome Series for Web Push
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating a Welcome Series for Web Push | Yespo Guide
  description: >-
    Learn how to set up an automatic welcome message chain after a web push
    subscription
  robots: index
next:
  description: ''
---
Let's organize a chain of welcome push messages after subscribing to a Web Push channel. In this case, we may use the data obtained during the subscription, such as the user's language and the page/site where it happened.

The sequence of actions for connecting a Web Push channel [is described here](https://docs.yespo.io/docs/web-push).

## Data from Web Push Subscription

The Web Push subscription event has the following parameters that are transferred to Yespo:

- **pushToken** — subscriber’s token;
- **os** — their operating system;
- **userAgent** — browser;
- **userAgentVersion** — browser version;
- **userAgentLang** — browser localization (user language);
- **ip** — the address from which the subscription was made;
- **subscriptionPage** — the page on which the subscription was made;
- **appUid** — application identifier (service field);
- **contactId** — identifier of the contact to be created.

This data lets you personalize subsequent communication with the subscriber, as shown below.

Let's start by setting up the welcome workflow without using additional data from the subscribe event.

## Basic Workflow for Launching a Welcome Series

1. Go to the Automation → Workflows section. Click on the _New workflow_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b13d1fd2394d5684ad5dd1fedff66628d3c0de699fcff31b087080cf33b1deba-welcome-1.webp",
        "New workflow",
        "New workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Create a workflow: the simplest option, in which a notification will be sent to the user after subscribing, will include the standard _Start_ and _End_ blocks and a welcome message that needs to be [created in advance](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications):

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7d80a4cc39d2d922f7c7231ead4ab4a3311c2473e4ec0a2f4f4fbe2af0b2d49c-welcome-2.webp",
        "New workflow",
        "New workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Save the workflow and proceed to select the launch condition.

When a user subscribes to Web Push, the newWebpushSubscription event arrives in your account; you can see it in the _Automation → Event_ _history_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/326437d5481e36c9bb4a9e01f4b4ac192652ea921039d18e240690be3b0c8c91-welcome-3.webp",
        "Subscription event",
        "Subscription event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Specify this event in the workflow launch conditions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/886f646bb136f364972dabb997855061542ecd13e3f6e37cb1dabdd06f043da3-welcome-4.webp",
        "Launch condition",
        "Launch condition"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More about workflow launch conditions >](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions)

After activating the workflow, each user after subscribing will receive the welcome web push specified in the workflow.

## Checking Language

Checking the subscriber's language is necessary to communicate with them in the future according to their language preferences.

> 📘 Note
> 
> You can automate multilingual communication by connecting [the appropriate functionality](https://docs.yespo.io/docs/multilanguage-overview)

Add the _Check event_ block to the workflow with the condition Variable matches a regular expression and the _userAgentLang_ check parameter to check the browser localization. The _Pattern_ field indicates the language code in which compliance needs to be checked.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de4deb58be56a90354f659707f720fdc9e346e1b50e5152403819e4dcd10d473-welcome-5.webp",
        "Checking language",
        "Checking language"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Each _Condition_ block must check whether the variable from the event matches the value specified in the pattern field.

- If yes, the workflow will follow the _Yes_ branch, which contains a message in the appropriate language;
- If not, the workflow will follow the _No_ branch, which leads to the next check.

Both branches should associate the last _Condition_ block with a message in the default language: if the variable in the event does not match any of the specified patterns, such users receive this last message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3f0b4e0880b1c6ffe7b090d59a9ef5e49502d1071b4f4c7909d85e2ec96eca11-welcome-6.webp",
        "Conditions",
        "Conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Checking Browser

Browser verification is necessary to send an optimally designed notification since the large image and buttons in the notification are only supported by Chromium-based browsers (Chrome, Opera, Brave, Vivaldi, etc.).

In most situations, it is enough to check if the user is using Chrome:

- Yes — send a push with a large image and buttons;
- No — send a push with an emphasis on text.

To check the subscribers’ browser, specify the userAgent verification parameter in the Condition block and the name of the browser in which compliance you want to check (Chrome, Firefox) — in the _Pattern_ field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/28a5a9cbd0ed54abb798f3987375f4ffe0db95adfd47e91f3565de62c2e791aa-welcome-7.webp",
        "Checking browser",
        "Checking browser"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The rest of the workflow is similar to language checking.

## Checking a Subscription Page / Site

Checking the subscription page indicates the user’s area of interest and allows you to start a dialogue on a  relevant topic.

To check the subscription page, specify the _subscriptionPage_ verification parameter in the _Condition_ block and the address of the page against which you want to check the event in the _Pattern_ field.

Also, if tokens are collected from several sites, it would be correct for the notification of a successful subscription to contain the corresponding logo, links, etc.

Note

Searching for a fragment by partial match in a link is done by writing the search string surrounded by “.\*”, for example, - .\*catalog.\*, \*sale.\*, etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1f9db2012fe961ab4a57b7014054f371adb7c6863147c15b809b90492ca65bd8-welcome-8.webp",
        "Checking a subscription page / site",
        "Checking a subscription page / site"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The rest of the workflow is similar to those described above.

> 📘 Note
> 
> The data from the _subscriptionPage_ parameter is not saved in the contact card. To further use them for segmentation, add the _Add to segment_  block  after the condition block, and indicate the contact identification by Contact ID and the corresponding segment to add:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed6c0d1e552a4b1d7ee9a582c9567e272edb6a387592b51ab41ac3cfb0a499dc-welcome-9.webp",
        "Adding to segment",
        "Adding to segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Thus, thanks to the parameters in the subscription event, you can not only greet or thank the subscribers in their native language but also personalize further communication.