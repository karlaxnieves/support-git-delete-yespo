---
title: Sending Reminders at the Time Specified by the User
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Reminders at the Time Specified by the User | Yespo Guide
  description: >-
    Setting reminders based on contacts' time preferences is important option
    for personalization,  better user experience, enhanced motivation, and
    demonstrating the app's adaptability to individual customer needs.
  robots: index
next:
  description: ''
---
Setting reminders based on users' time preferences is essential for improving user experience and customer retention. For example, you can allow users to choose when to exercise or take classes and send them regular reminders at the specified time.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f81bd534d10a42f7d0a43044f388ff494dbf69924ddbeea33b0424295b9b722a-reminders-1.webp",
        "Reminder",
        "Reminder"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


## Creating Additional Contact Field

An [additional contact field](https://docs.yespo.io/docs/how-add-additional-contact-fields) stores any users’ information; in our case, we need a storage for user time. If you already have such a field, skip this section.

1\. Go to your account settings → _Additional fields_ tab and click _New field_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0173bc0f627d1132946f152a07f810076d2b7d7b794d7e209d33498f207779c8-reminders-2.webp",
        "Reminder",
        "New field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Configure the field parameters:

- **List of fields** — select the existing one from the drop-down list.
- **Name**, based on which personalization key will be generated.
- **Personalization key**.
- **Field type** — _Text input_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5b9d60c2fffbab9a4d060971e94b37778f245aa78688810dcef25a415107edf-reminders-3.webp",
        "",
        "Field parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After creating the field, you can fill it by [importing a file](https://docs.yespo.io/docs/file-uploading) with the corresponding data or by API ([Add/update a contact](https://docs.yespo.io/reference/addcontact-1) or [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) methods).

The time must be sent in the _HH:MM_ or _HH:MM:SS_ format.

As the system waits until the specified time in the user's time zone, configure recording the user's time zone in Yespo [through SDK or API](https://docs.yespo.io/docs/tracking-user-time-zone-and-language).

## Setting Up Workflow with Timer Block to Automate Reminders

1\. Go to the _Automation → Workflows_ section and open or create a workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/053e26b7cfd834df85da44c070a415ff46c22a6c16eb2a70eb24c0061a7eb7dc-reminders-4.webp",
        "",
        "Workflows"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Drag the _Timer_ block from the left sidebar into the workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a852eb6173ba00885715d7b64badefe4ff9a7f0c22b80a2238a4b4f9e0b04361-reminders-5.gif",
        "",
        "Timer"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The _[Timer](https://docs.yespo.io/docs/time-blocks#timer)_  block sets a time gap before the following in the workflow action.

3\. Configure the block parameters:

- Disable the _Wait time_ switcher and enable the _Wait until_ switcher to send reminders as soon as the specified time comes
- Select the _From the contact field_ option from the drop-down list
- Select the created contact field from the drop-down list

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0cf1f125c225f17d1a18b005e3740d72c9e114ea3dbb3e9715b79c69639dcf87-reminders-6.webp",
        "Block parameters",
        "Block parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Use the [_One from many_](https://docs.yespo.io/docs/using-one-many-block) message block to improve retention with diverse content for training or lesson reminders.

4\. Save the workflow.

## Workflow’s Start Configuration

1\. In _Automation → Workflows_, select the created workflow and click _Trigger configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/521220239dfc0c7adccdc370cdbfcf73ff17a6f0c9b8b52e8c7ee204159f2daa-reminders-7.webp",
        "",
        "Trigger configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Activate _Start configuration_ switcher.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e8ca606025efbb367d1982d64157ea4e3bb0c7d2315cf79a3be0c563b967d0ed-reminders-8.webp",
        "",
        "Start configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


There are two options to launch a workflow with reminders: _Event-based_ and _Regular_.

### Event-based Workflow

Select _Event-based_ in _Start configuration_, and then

- Select event which must launch the workflow
- Specify the frequency of processing unique events

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db4ddabd51af37cfd6e885e5adb9a4beff749162d3eaaaa145227fb25d3bec34-event-based.webp",
        "Event-based workflow",
        "Event-based workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Regular Workflow

1\. Create a [dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment) with users subscribed for reminders.

2\. Select _Regular_, and then

- In _Segment_, select the created segment
- Select the workflow’s _Start date_

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53b0c90d71ceea82f145f54313525e7826ae7e6fc24ad98ef9c9a191940ad2fa-reminders-10.webp",
        "Regular workflow configuration",
        "Regular workflow configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In _Start schedule_, select once a day
- Select allowed start days

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b63ba01313f9dfad43378d958bd5c5ceaeb4811c76d29ad1e43eed3ae8c78a4-reminders-11.webp",
        "Regular workflow configuration",
        "Regular workflow configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Set the workflow’s _Start time_
- In _Process unique events_, select _Each time_

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/87fe2ee87773a4f095fa0701fdfe2f156ee50e52dbcdb539f939103747666816-reminders-12.webp",
        "Regular workflow configuration",
        "Regular workflow configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Launching Workflow

1\. Click _Apply_ in _Start/Stop configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7665f71b1d1722acd286fdc419ad0bc4d2b37affd6d03d42cd476da092e23596-reminders-13.webp",
        "",
        "Start/Stop configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. To start the workflow, click _Activate_ on the right and confirm the action.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/715f41c091b0d110b946e1baa7742acb01a5820c9cd35aaa309a89290b2fd40b-reminders-14.webp",
        "",
        "Activate"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The system will wait for the designated time in the user's time zone and perform the action specified in the workflow after the _Timer_ block.

> 📘 Note
> 
> If the field of a contact participating in the workflow has a missing or written in an incorrect format value, the message will not be sent