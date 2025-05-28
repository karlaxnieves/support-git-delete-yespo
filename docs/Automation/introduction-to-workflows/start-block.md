---
title: Start Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Start Block | Yespo Guide
  description: Learn about the Start Block in marketing automation workflows.
  robots: index
next:
  description: ''
---
The _Start_ block is required to create a workflow. It automatically appears in a new workflow by default. There can only be one _Start_ block in the workflow.

> 📘 Note
> 
> _Start_ block cannot be deleted

## Early Workflow Stop Configuration

You can enable automatic checking of contacts participating in the workflow:

- whether they participated in a certain event (for example, they signed up for a course and already received tutorial series);
- whether they are in a certain segment (for example, it is necessary to cover newcomers with a campaign and not launch it on active buyers);
- whether they made an order (for example, 7 days before the start of the workflow).

> 📘 Note
> 
> Workflow stops earlier if a condition is met. The check takes place at the workflow's start and after each _Timer_ block.

1. Activate the _Stop configuration_ switcher.
2. Select one of the check types using the radio button.

- Event-based;
- Included in a segment;
- Order-based.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/860d8c1ffee8c316207b3412fa325f91c570a06cb60c8f53a8788ce48348cbfc-start-block-01.webp",
        "Stop configuration",
        "Stop configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Event-based Workflow Stop

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5dff08e1cf19973032af2427540ba54f8c67f848357a060538dca5a03b874aa-start-block-02.webp",
        "Event-based Workflow End",
        "Event-based Workflow End"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the _Event_ drop-down list, select the event that will stop the workflow for the corresponding contact. The workflow stops if the event happens within the selected period before the workflow starts or any time after it starts. In the _Period_ field, you can set the time before the start of the workflow, during which the event must be checked. By default, the block checks for events since the activation of the workflow.

_${key}_ is the universal variable for the event unique key specified in the block by default. When the system starts a workflow, it checks the selected event: if it finds the event unique key, the workflow ends for this contact.

You can see the event unique key in the _Automation_ → _Event History_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/098039100caa9de2acbfe8fb390e1279e94b54bb3b9caf2ec6b25e6184cd408d-start-block-03.webp",
        "Event History",
        "Event History"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> The event unique key (email, contact ID, etc.) must match in the event that started the workflow and the event that should end the workflow.

### Included in a Segment Workflow Stop

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4de5ae2bae643b5292fd1d20c614f406b7570f593be383aa495267a824b1f889-start-block-04.webp",
        "End Workflow If the Contact Is Included in a Segment",
        "End Workflow If the Contact Is Included in a Segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Select a segment from the drop-down list in the _Segment_ field. If the system detects that a contact enters a specified segment, it will stop the workflow for them. The system identifies contacts by one of the parameters:

- Phone;
- Email;
- Contact ID in Yespo.

### Order-based Workflow Stop

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84141df7cd7df6383ef0a0cb5bde683069586aa4302a5dcfd3d5ee671e25c424-start-block-04.webp",
        "Order-based Workflow End",
        "Order-based Workflow End"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The workflow stops if the contact has placed an order within the selected period before the workflow starts or any time after it starts. Set the time to check in the _Period_ field.  
The system searches contacts by one of the parameters:

- Phone;
- Email;
- Contact ID;

First, the system uses _Contact ID_, if it’s not specified, then by _externalCustomerId_ to search for a contact, if this is present in the event parameters.