---
title: Configuring Workflow Start/Stop Conditions
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Configuring Workflow Start/Stop Conditions | Yespo Guide
  description: >-
    The article provides a detailed guide to setting up and managing start and
    stop conditions for marketing automation workflows.
  robots: index
next:
  description: ''
---
In addition to settings you can apply for your workflow blocks, you can set up start/stop configurations for your workflow.  

To open the _Start/Stop configuration_ menu:

1. In your account, go to _Automation → Workflows_ and select the required workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7319dc2fec881176ef10333b2348316eb00c92e12c72ee54c828ae698345b780-trigger-configuration-main-201.webp",
        "Select the workflow",
        "Select the workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the _Start/Stop configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5546888e8bcd1cea9cdb36771f6ac9b50c6c7119a8ce1ace1598a177a00a635-launch-conditions-202.webp",
        "Start/Stop configuration",
        "Start/Stop configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Setting Up Start Configuration

1. Enable the _Start Configuration_ slide button.
2. Select one of the following conditions:

- Event-based
- Regular
- On contact field change
- Event-based with segment parameters

3. Select the settings specific to the selected condition, as described below.
4. When the _Avoid starting a workflow if already in progress_ option is enabled, the workflow will not be launched for contacts that are already in the process of running it. For example, if a user receives a chain of reminders about products left in the cart and leaves new items in the cart during this period of time, the workflow will not react to this event.
5. Click _Apply._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e1e9d0e2a604cf5a1c0febcce002c1b340fba107bbafabbff3d7ac76632347e5-required_parameters_4.webp",
        null,
        "Start Configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Event-based Start Configuration

The event-based settings in the start configuration allow you to start the workflow upon the occurrence of a specified event.

When you select _Event-based_,  you can set up the following workflow settings:

- Event
- Required event parameters
- Process unique events

#### Selecting event

Select an event to start a workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e7e43fe26798beb4b358eb278c40fc806fff3d03a208f60beed741f8905a933-required_parameters_5.webp",
        null,
        "Selecting event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The workflow will start when the selected event occurs.

> 📘 Note
> 
> The same event can trigger different workflows, which allows you to divide complex schemes into separate, independent chains of conditions and actions

#### Selecting Required Parameters

The workflow will only launch if the event parameters meet the conditions set in this section: for example, only if the purchased products match a certain category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e63a81849584156035cf7c894fcd64ed271acb963e66ad86fb567b7caf7e8109-required_parameters_3.webp",
        "",
        "Add required parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To set up a condition, click the _Add required parameter_ button and specify the event parameter and the value you want to check it for. The following check options are available:

- equals,
- does not equals,
- is set,
- is empty,
- contains,
- does not contain,
- starts  with,
- does not start with,
- ends with,
- does not end with,
- one of,
- does not one of.

If necessary, you can add checking for other values ​​(AND/OR conditions, their number is not limited).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10e36bcdcf04111fba3eff6fb75c70963ff31f90daa7c7b588bcb97dccede867-required_parameters_2.webp",
        "",
        "Required parameters settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Selecting Process unique events

The process-unique events define whether to: 

- Repeat the workflow every time when an event occurs.
- Stop the workflow after the selected event occurs once.
- Run the workflow only once during the specified time, no matter how many times the specified event occurs during that time.

To select the required condition, select the _radio button_ beside Process unique events.

If you select the _Once in every_ condition, enter the value in the field and select its definition from the dropdown list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce866527f8fc6f69150921fbbaea079f1984fcbbedca549fe560fd506c8229d7-start-conf-6.webp",
        "",
        "Process unique events"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Regular Workflow Start Configuration

Workflow configuration settings:

- **Segment**. It allows you to select a segment of contacts.
- **Start**. This setting defines the workflow start date.
- **Start schedule**. This setting defines the frequency of a workflow.
- **Allowed start days**. This setting allows you to set the specific days of a week for running a workflow.
- **Start time**. This setting allows you to run the workflow for 1 hour within the specified period of time.
- **End**. This setting allows you to set the workflow end date.
- **Process unique events**. See [Selecting Process Unique Events](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions#selecting-process-unique-events).
- **Avoid starting a workflow if already in progress.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d67a9fdd688e15af33e055037bb6720e2fcb9af74369ffa7a59105737eee062-start-conf-4.webp",
        "",
        "Selecting regular settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When you add the segment in the settings, you can proceed to its preview or copy the ID.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92c45d1040e3b20a48a61f95ee13339403ad2138af0e32c6e8622db0d298df7f-regular-segment-pre.webp",
        "Segment preview",
        "Segment preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The set values of date and time in the start configuration mean that the campaign will launch when the specified time and date occur. For example, if you set the start time from 09:00 to 10:00 once a day, it means that the workflow will automatically run within the specified time each day.

The same applies to the allowed start days — if you specify that the workflow should only be launched on Tuesday and Thursday, then it will only be automatically started on those days.

### On Contact Field Change Start Configuration

When you select the _On contact field change_ option, the workflow starts every time when the selected field changes for a selected contact.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ca0a91a4e33ed80b30d2e9e3041afead9b614209a2159833d9b82cda41141736-configuring-workflow-start-stop-conditions-0011.webp",
        "On Contact Field Change Settings",
        "On Contact Field Change Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The workflow starts when the contact field changes as the result of the contact importing or using the following API methods:

- [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1)
- [Add/update a contact](https://docs.yespo.io/reference/addcontact-1)
- [Update contact](https://docs.yespo.io/reference/updatecontact-1)

### Event-based with Segment Parameters Start Configuration

The workflow starts when the segment parameter matches the event parameter.

**Example of use:** When new chapters are released in a certain book, you need to send a corresponding notification to all contacts who have read this book.

**Settings**

1. Go to the _Contacts → Segments_ section and select _New segment → Dynamic with parameters_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/16d95b667c14a94e7e3e12a0ce74a7e28663885b0d5cfa2a7cebed0f4f66f31f-start-conf-5.webp",
        "",
        "Dynamic with parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the conditions, specify the segment parameter that should correspond to the event parameter.

In our case, the segment parameter is the ID of the book the contact is reading (_bookStartedBookId_), and the event parameter is the dynamic variable of the updated book (_$bookUpdatedBookId_).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53927893824b2faa4e59601c8b7331cbb08ebefa528cbdf2ac11abd3f9723bdd-start-conf-1.webp",
        "",
        "Add condition"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Save the segment and go to the workflow start settings, where you need to specify the appropriate event and parameter segment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a49521c266efc342f7f65cbf14f058f5c586fd98cf4849b727d2eb615ef326d-start-conf-3.webp",
        "",
        "Workflow start settings"
      ],
      "align": "center"
    }
  ]
}
[/block]


When an event with the ID of an updated book is received, contacts reading the same book will receive a notification through the workflow.

## Setting Up Stop Configuration

To set up stop configuration for a workflow:

1. Enable _Stop Configuration_ slide button.
2. Select one of the following conditions:

- Event-based
- Included in a segment
- Order-based

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a7c08eb8b615b1c2163633de0036141290d43b568657ea2f6acdc24381912422-stop-1.webp",
        "",
        "Stop configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the settings specific to the selected condition, as described below, then click _Apply_.

### Event-based Stop Configuration

The event-based condition stops the workflow when the selected event occurs (or happened before the workflow was started).

To configure the _Event-based_ options:

1. Select one or more events. The workflow will stop by `contactId` if it is contained in one of the specified events, even if they have different unique keys. If the event does not contain a `contactId`, the workflow stops by the unique key of that event.

To view unique event keys, go to _Automation → Event history_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/59d208e-configuring-workflow-start-stop-conditions-0011.webp",
        "",
        "Unique keys"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the period value. The workflow will stop if the event occurs within the specified period before its launch.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a49240c7d6c8e2fbaf02e621832f00c7d71f17005c475b20d5e5827b63be76a-event-based1.webp",
        null,
        "Stop configurations"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Included in a Segment Stop Configuration

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a7ad469f847055d55bf48d740949601ac392e8bd7bed2c292ee5cdcd98399d7-stop-2.webp",
        "",
        "Event-based stop configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Included in a Segment Stop Configuration

The _Included in a segment_ condition stops the workflow when the contact is included in a specified segment.

To set up a stop condition by including in a segment, select it from the list or specify a dynamic variable in brackets – the name of the start event parameter containing the segment ID.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62c82b0eb638f2ebf290309149034eba9e7ec79c600d2e997bf57c4c79943ab5-stop-03.webp",
        "",
        "Included in a segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After selecting the segment, you can preview it by clicking the preview icon.

> 📘 Note
> 
> When the workflow is stopped by including in a segment or by order, the system searches for a contact by _contactId_, if it is not specified, by other identifiers.

### Order-based Stop Configuration 

The _Order-based_ condition stops the workflow if an order-related event occurs before the workflow starts or during a specified time after the workflow starts.

To configure the _Order based_ options, enter the period value. The workflow will stop if the order occurs within the specified period before its launch.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/294375146e41324547ecf440fc7b9b93e5f9a3ebd64650b2804a0e23535e7453-stop-4.webp",
        "",
        "Order-based options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]