---
title: Other Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Other Blocks | Yespo Guide
  description: >-
    Explore Other Blocks in marketing automation workflows. Learn how to use
    them for tasks like ending workflow paths, creating and updating contacts,
    sending obligatory messages, and generating unique events for contacts.
  robots: index
next:
  description: ''
---
_Other_ blocks are applied to solve various tasks, for example:

- Ending workflow paths
- Creating and updating contacts
- Sending obligatory messages
- Creating separate events for each contact in a segment.

Other blocks include:

- End
- Task
- Webhook
- Sprayer
- Check point

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c99d5156379381a5c16b07924833ed09f2bfb4445bdd8e0d5b466c3167d5c386-other-blocks-001.webp",
        "Other blocks",
        "Other blocks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## End

[More detailed information >](https://docs.yespo.io/docs/popular-blocks#end)

## Task

[More detailed information >](https://docs.yespo.io/docs/popular-blocks#task)

## Webhook

The task of this block is to request the specified URL (use only the _HTTPS_ protocol). Available request types are _GET_ and _POST_. Data format: _JSON, XML, text_.

Use webhooks, when you need to access the data source by reference to return a promo code or authorization token, and then display this data in a message within a workflow. With this block, you can also transmit to the specified address:

- parameters from the event that launched the workflow,
- (additional) fields of the contact on which the workflow launched.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4126988e4351596839d043d44efe7183f5fee13946dad095ad5988d69103e1de-webhooks-in-workflows-301.webp",
        "Webhook",
        "Webhook"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The _Webhook_ block is used only in combination with the block for sending a [single message](https://docs.yespo.io/docs/message-blocks) in any channel, and also with the _Variable matches regular expression_ block. For workflows where a message is sent to a group, the _Webhook_ block does not apply.

Read detailed instructions on setting up, testing, and managing [webhooks in workflows](https://docs.yespo.io/docs/webhook-workflows).

## Sprayer

The block creates events for each contact of the selected segment.

As a rule, if the workflow is launched for a segment, you cannot add the blocks designed for contacts. Sprayer enables to do so.

It works as follows:

- The workflow for a segment has been launched (the segment ID was passed in the event, or the segment is selected in the Sprayer settings).
- The workflow reaches the block _Sprayer_.
- A separate event for each contact is created (transition from segments to contacts).
- This event launches a workflow for each contact.

The events created by the block contain an email address and contact ID. This makes it possible to launch a different workflow with these events and use contact blocks.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e5bc484e5383a085b2c5e6a8b1137e418401945d7ac180c8f41fdad0a3e12cc-other-blocks-0003.webp",
        "Sprayer",
        "Sprayer"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The block has 2 parameters:

- **Segment**: required parameter. Select the segment in the drop-down menu or specify ${segmentId} variable.
- **Event**: required parameter. Select the event you want to create.

When you select the segment in the block parameters, you can proceed to its preview and copy the ID.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4761a1b760ffd9ecba43361d4e9b6e67d1accf021be9c2ea9ff3888056da0912-other-blocks-003a.webp",
        "Sprayer",
        "Segment preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Events must be created beforehand in _Automation_ → _Event types_.

> 📘 Note
> 
> Sprayer will trigger the event only if the segment includes less than 1 000 contacts.
> 
> All attempts to trigger the event for a bigger segment are displayed in _Statistics_.

## Check Point

[More detailed information >](https://docs.yespo.io/docs/popular-blocks#check-point)