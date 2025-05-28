---
title: Replacing Double Opt-In System Workflow
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Replacing Double Opt-In System Workflow | Yespo Guide
  description: >-
    The document explains how to set up and customize subscription confirmation
    workflows in Yespo, activate default workflows, create custom reminders, and
    configure triggers for efficient email confirmations.
  robots: index
next:
  description: ''
---
System workflows and events make usage of the platform more convenient. For example, Yespo widgets have a subscription confirmation workflow attached by default. When creating a form, it is enough to activate the switcher so that all new contacts who fill out the form on the site receive an email with a link to confirm the subscription.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/348437727e1c2b36f49d8eb2a18989882a49b849d7897de6d7924d8b9443df98-DOI_1.webp",
        null,
        "Enabling DOI"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The built-in system workflow sends one confirmation email, specified in the widget settings, no more than once every 72 hours.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/468a1fcd44201769d3d8101c129b9fc6cf8edc83ca6627af45a12d150e161816-replacing-double-opt-in-system-workflow-01.webp",
        null,
        "System DOI workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In some cases, you may need to change the system workflow: for example, send one or more messages asking to confirm the subscription to those who did not do this in the first email.

**System workflow replacement algorithm:**

1. Setting up the subscription confirmation link in the email.
2. Creating a workflow.
3. Configuring trigger.

> 📘 Note
> 
> If you replace the system workflow, the new mailing scheme will be applied to all widgets in the account, while the emails can still be unique for each form.

## Setting Up a Confirmation Link in an Email

The button with the confirmation link in the email for widgets should have the following settings:

**Link:**

- Type: _Subscription confirmation_,
- Link: `$data.get('redirectUrl')`

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f1bb1c8186b254641b46c85095af22843e5046b27b01cfd788949f8ce0f0eea-DOI_3.webp",
        null,
        "Link"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


**Event type:** _SysContactConfirmed_

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a4b821a50438a25ef8d38a51235f437bafe433ed698d383789ee6a0f36242610-Actions_After_Form_Submission_5.webp",
        null,
        "Event type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Creating Workflow

Create a new workflow. It will be triggered by the _SysContactConfirmationRequest_ system event, which is sent to Yespo when a user submits data from a widget on the site.

For example, if you want to remind about subscription confirmation three times with an interval of an hour, the workflow will be as follows:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ede5b2b175febcbdd3a9a24e596de3492c3c3ce495793af9ad17146b56319056-replacing-double-opt-in-system-workflow-02.webp",
        null,
        "Custom DOI workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Workflow blocks:

1. Start.
2. The _Send obligatory (transactional) email_ task with the following settings:

- **Contact’s email:** specify the _**${email}**_ variable — the system will substitute from the event the email of the user who filled out the form.
- **Message:** specify the _**${messageId}**_ variable — the system will substitute from the event the message specified in the settings of the widget that the user filled out.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c2124f0cf3b9d8c9b11297ca8d2b66870dee008b1b44a7b7137123988de09f4-replacing-double-opt-in-system-workflow-03.webp",
        null,
        "Send obligatory (transactional) email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Timer: specify the time to elapse between subscription checks.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/23981df5401777a51ba405efc8b98342e7906cee2625856a0d323f4eba619bd0-replacing-double-opt-in-system-workflow-04.webp",
        null,
        "Timer"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. The _Contact confirmed_ condition checks if the user has confirmed their email: if yes, the workflow ends; if not, sends the message again.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ce294b5647d4bef1b1e7511918b827160cc569eb9be2fbc5b13637fda029b7f-replacing-double-opt-in-system-workflow-05.webp",
        null,
        "Contact confirmed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. End.

After making the settings in the workflow blocks, save it and go to the launch settings.

## Configuring Trigger

1. Click _Trigger configuration_ in the list of workflows.
2. Activate the _Start configuration_ switcher.
3. In the _Start configuration_, select:

- Event-based;
- _**SysContactConfirmationRequest**_ event;
- arbitrary conditions for processing unique events.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/725a0b002ea9dc8d9450caf9251590c506e1876e9f2809ec85bb9fe259a70aa5-replacing-double-opt-in-system-workflow-06.webp",
        null,
        "Start configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Apply_.

[Learn more about events >](https://docs.yespo.io/docs/creating-events)

Once you activate the workflow, the system will apply it to all widgets in your account.