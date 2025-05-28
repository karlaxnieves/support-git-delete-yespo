---
title: Message to Segment Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Message to Segment Blocks | Yespo Guide
  description: >-
    This document explains the use of the "Message to segment" block in a
    workflow, which allows you to send a message to a specific segment of
    contacts.
  robots: index
next:
  description: ''
---
The block sends one message to a segment. It’s used in a workflow after contact import or to launch a series of messages. For example, send a message to a segment, and then either resend it or send another message to those who have not read it or clicked the link.

Typically, one workflow includes either the block with one message to one contact ([Contact blocks](https://docs.yespo.io/docs/contact-blocks)) or the block with the _Message to segment_.

There are six block types:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0ff71bc123b7438c4ce86f562df8654d4045cba7f5c06b8d3c92266b3d795be5-message-to-segment-blocks-0200.webp",
        "Message to segment blocks",
        "Message to segment blocks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> Do not use these blocks for triggered messages. If the event passes the token or contact ID, use one of the [_Message_](https://docs.yespo.io/docs/message-blocks) blocks (one message to one contact).
> 
> The blocks _Message to segment_ are only used for events that pass the segment ID, or for workflows that are launched for a selected segment (for example, dynamic).
> 
> Even if you set _[Regular](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions#regular-workflow-start-configuration)_ in _Trigger configuration_ and select a segment, you still need to use the block with one message to one contact, because this trigger type doesn’t pass a segment group ID to the workflow. Instead, it launches the workflow separately for each segment contact and passes the _email_ and _contact ID_ at each launch.

## Common Block Parameters

Each _Message to segment_ block contains several parameters:

- **Message**: required parameter. 

To select a message:

1. Click the _Select message_ button on the right side of the settings panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8cbb6383bbb69f85c98643849545311c2a9aa99a10d0597f3162184d18d15f74-message-to-segment-blocks-200.webp",
        "Select message",
        "Select message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select a message from the list (by default, the last created one is selected) or specify the dynamic variable _${emailMessageId}_ using the button next to the search bar.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90164dea49470c427b2a06697f53a981471aa5d5c89180f88bd541d27dcb62ac-message-to-segment-blocks-201.webp",
        "List of messages",
        "List of messages"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To search the message in the list, use the search field by message name, subject, [tag](https://docs.yespo.io/docs/how-add-tags), or ID.

You can also sort messages by their update date.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22b0c3444cf8d69164071233ff9b6df75214b5e1bce1d521b7b6e88e7aa13ee1-message-to-segment-blocks-202.webp",
        "Search and sort",
        "Search and sort"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If a workflow is associated with a message, it appears in the list. To open a preview of the workflow, hover over its name and click the corresponding icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45eb1a0242afdd71dd93a9c34d33e53ec84e0b3263997a0a72eed1a388d24940-message-to-segment-blocks-203.webp",
        "Related message and workflow",
        "Related message and workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The following actions are available in the message selection window:

- Create a message copy
- Message preview

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4765a9b39e7b3310d69220de84363ad6e8a3f2656ca1ff86fd6d171304b7c7fb-message-blocks-205.gif",
        "Message copy and preview",
        "Message copy and preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click the _Select_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c2c22288975d05952a3e74d5a00ca14963e7c9af328157eab9918bb08387b40-message-to-segment-blocks-204.webp",
        "Click the Select button",
        "Click the Select button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


By clicking on the three-dot icon, after selecting the message in the block settings, you can:

- Preview the message
- Replace the message
- Edit the message in a new tab
- Copy the ID

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7fdedf7253e68f89e4a8c2e7c3d44a15232c7273da163e711ca85256d0d3286f-message-to-segment-blocks-205.webp",
        "Additional actions",
        "Additional actions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you delete the message, a corresponding tooltip will appear in the block settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa6c945568265910b86e45848074bec72974c628368abf29599d040f9ad12a49-message-to-segment-blocks-206.webp",
        "Deleted message tooltip",
        "Deleted message tooltip"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In that case, you should select a new one by clicking the _Replace message_ button.

- **Segment**: required parameter. Select the segment in the drop-down menu or use dynamic variable _${segmentId}_. You can also select _New list segment_ / _New dynamic segment_ options and create a segment directly in the workflow.

> 📘 Note
> 
> Conditions are not yet set when creating a dynamic segment directly in the workflow, and, accordingly, there are no contacts. Therefore, before launching such a workflow, it is necessary to set the conditions for segment formation in its settings.

After adding or creating the segment in the block parameters, you can proceed to its preview and copy the ID.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cd823929211757bb8e10eb5b97c380c3595a70b2599b08e0012e5f464bfd1109-message-to-segment-blocks-preview-01a.webp",
        "Segment preview",
        "Segment preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> Each segment in the Yespo system has its own ID. For example, if you send an event and with an ID value pass the GroupId parameter
> 
> _"name":"segmentId", "value":167039898_
> 
> _167039898_ will be substituted into the workflow instead of _segmentId_, and the workflow will be launched to this segment. You need to know what the ID corresponds to so as to control the campaign, indicating what to send to which segment.

- **Send only in specified hours**: Enable this parameter to send messages only within a specified time gap.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/012d574766a7fa15baf7434da93c1c5b31a5c297e4a1f0ad6dc87e652eb49cc5-message-to-segment-blocks-222.webp",
        "Common block parameters: Message, Segment, Send only in specified hours",
        "Common block parameters: Message, Segment, Send only in specified hours"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Individual Block Parameters

- **Site** (_Web Push to segment_ parameter): required parameter. The website that collects tokens is specified by default. If you have several websites, choose one from the drop-down menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff5fec546935271c529efc525f6106fe9c7c2a719f33de75de718b083fd51453-message-to-segment-blocks-003a.webp",
        "Web Push to segment parameter: Site",
        "Web Push to segment parameter: Site"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **Application** (_Mobile Push to segment_ parameter): required parameter. An app identifier for accounts with more than one app. You can select the app to send notifications from the dropdown list or specify dynamic parameter _${appId}_. The system extracts the app ID from the event that has triggered the workflow. When sending events through the [SDK](https://docs.yespo.io/docs/sdk-mobile-apps), this parameter is passed automatically.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c47c607e346097b6fb4c0479c07e8d47b7b9c3c4942c3f45c896b90a03b9caed-message-to-segment-blocks-004a.webp",
        "Mobile Push to segment parameter: Application",
        "Mobile Push to segment parameter: Application"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]