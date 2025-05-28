---
title: Time Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Time Blocks | Yespo Guide
  description: >-
    Discover Time Blocks in marketing automation workflows. Learn how to delay
    actions or schedule them for specific times using the Timer and Start on
    Date block types to optimize workflow execution.
  robots: index
next:
  description: ''
---
The blocks delay the execution of workflow actions or execute actions at a specified time and contains two block types:

- Timer
- Start on date

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f156edc402c083e2a831405ccd53596150cdde908f94eacc2665269b689aa837-time-blocks-001a.webp",
        "Time blocks",
        "Time blocks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Timer

The block is used to set a time gap before the next action or message sending. It is placed before a block you want to delay.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/03a8826ee1a1866359751450ce74b19c668acce9b07c576e467133abdd7528e8-time-blocks-002.webp",
        "Timer",
        "Timer"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Contact confirmation triggers the workflow with a drip welcome series in the example. A new contact receives a welcome email after confirmation, a second email after two days, and a third after the next three days.

To set up _Timer_, configure one of 2 or both parameters:

- Wait time
- Wait until

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3856a93924ebd7b981997495da858a746e445a66e302c43af35d2f70492845db-time-blocks-003a.webp",
        "Timer parameters",
        "Timer parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can configure all parameters or only one; at least one parameter should be configured to start a workflow.

### Wait Time

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4dd64027fd38f6234c51a857b768a47b10614277bb5f223a6e2bfded129532b8-time-blocks-004a.webp",
        "Wait time",
        "Wait time"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Enter the time of delay, and select the parameter to which it will be applied:

- minutes
- hours
- days
- months

Important

If you delay for 1/2/3 days, the delayed action will start 24/48/72 hours after the workflow is triggered. If a person subscribes to you at 7 a.m., they will receive the first email at 7 a.m. the next day.

### Wait Until

In the Wait until parameter, you can specify the time yourself, use data from an [additional field](https://docs.yespo.io/docs/how-add-additional-contact-fields) of the contact card or from the context parameter (the event that launches the workflow).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0730de5372e192e6692235d2e3402ce294cba55ca659e747221502147ff46c0d-wait-until.webp",
        "Specify the time",
        "Specify the time"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Specifying the Time Manually

Here you can select the day of the week and the time for sending.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50afa5c4142f4377bc524272fd81c04ef6809dce11e170c545f5305eb5ca7de1-settings-3.webp",
        "Wait until",
        "Wait until"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you set the sending time at 8:45 a.m. and the workflow starts at 3:00 p.m., the subscriber will receive the message at 8:45 a.m. the next day.

> 📘 Important
> 
> If today is _Tuesday_ and you've chosen to send a message on _Monday_, the message will be sent next _Monday_. If it's _Monday_ today, the subscriber will receive the message today.

#### Using the Time from an Additional Contact Field

For example, you can use this option to set up reminders if you collect data in additional fields about the time your subscribers perform specific actions: make purchases, exercise, study, etc.

Select the contact field containing the time you want to wait.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2de8b55a9acb2e1c5a1ebdd7cd7929bf872c251d3571a3a5be165afe7973df8f-settings-4.webp",
        "Contact field",
        "Contact field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The time from the contact field is based on the contact's time zone and must be sent to the text field in the HH:MM or HH:MM:SS format. If the field of a contact participating in the workflow has a missing or written in an incorrect format value, the corresponding error will be displayed in the launch history of such a workflow.

#### Using the Time from a Context Parameter

You can use this option to set up reminders if the data about the time your subscribers perform specific actions is not tied to additional fields and you are focusing on actual data — for example, when the last event about the workout start was received.

Specify the event parameter containing the time to wait until.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c6be4b38b081e8a9f97e98e8fc6f2fe82396e472b177b6fe343a8d244a30fa9-context-parameter.webp",
        "Context parameter",
        "Context parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The time from the event parameter is based on the contact's time zone and must be sent to the text field in the ISO 8601 format. If the value is missing or written in an incorrect format in the event that launches the workflow, the corresponding error will be displayed in the workflow's launch history.

### Use Contact’s Time Zone Parameter

Activating this parameter will allow you to send a message at a specific time, taking into account the contact’s time zone.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32403e5838026509e5f5a5f18fec79f5bbb637dcfdaf4aa866362320120dc7d3-time-blocks-006a.webp",
        "Contact’s time zone parameter",
        "Contact’s time zone parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Parameter Priority

For example, you've configured the following delay parameters:

- wait day;
- send on Monday.
- send time at 8:45 a.m.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc803d29cfb7339931f4e266bde55e82c79960f8461671a6c8e3c0fe47fe78ed-time-blocks-008.webp",
        "Parameter Priority",
        "Parameter Priority"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The workflow starts on Sunday at 3 p.m. The system waits for 1 day (24 hours). Then it's Monday. The _Wait_ 1 day parameter expires at 3 p.m. on Monday. The system checks the _Send_ parameter. You have chosen Monday, today is Monday, so far everything is fine.

The system checks _Send time_. It’s set for 8:45 a.m., and the workflow is triggered at 3 p.m. The subscriber will receive the message not this Monday but only the next one at 8:45 a.m.

## Start on Date

The block is used to send a message:

- before _X_ days/hours/minutes before the date and time you send in the event;
- with the start time you send in the event or set manually;
- on date from an event parameter or specified in a block.

> 📘 Note
> 
> - If the start time is taken from the event, the transferred time zone is applied.
> - If the start time is set manually, the block will start in the time zone specified in your personal profile.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21d770f5423a3dbff4fb46fd29f3902b9d7754479e989f0dc320c69d5c007a77-time-blocks-007a.webp",
        "Start on date",
        "Start on date"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the _In_ field, specify when before the date to send the message: _1 hour_, _3 days_, _10 minutes_, etc.

In Before date, you can take the required date from the sent event. In the box below insert the parameter name from the event, for example, _${starDate}_.

> 📘 Important
> 
> There are two supported formats for the date and time:
> 
> 1. UTC: 2011-12-03T10:15:30;
> 2. UTC offset: 2011-12-03T10:15:30+02:00.
> 
> The UTC offset is the difference in hours and minutes from UTC for a particular place and date. UTC+02:00 is used in some countries of Central Africa Time, Eastern European Time, and South African Standard Time. See the full list <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_time_zones_by_country" target="_blank"> here</a>.

Activate the _Use contact’s time zone_ parameter to send a message at a specific time, taking into account the contact’s time zone. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d680d63c0480e8d6d16b27ca36ac56f7dbb3be6f39373bc2102fc453f6f907b-time-blocks-0001.webp",
        "Start on date",
        "Use contact’s time zone"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]