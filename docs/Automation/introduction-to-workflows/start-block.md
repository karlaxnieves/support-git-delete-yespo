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
The *Start* block is required to create a workflow. It automatically appears in a new workflow by default. There can only be one *Start* block in the workflow.

> 📘 Note
>
> *Start* block cannot be deleted

## Early Workflow Stop Configuration

You can enable automatic checking of contacts participating in the workflow:

* whether they participated in a certain event (for example, they signed up for a course and already received tutorial series);
* whether they are in a certain segment (for example, it is necessary to cover newcomers with a campaign and not launch it on active buyers);
* whether they made an order (for example, 7 days before the start of the workflow).

> 📘 Note
>
> Workflow stops earlier if a condition is met. The check takes place at the workflow's start and after each *Timer* block.

1. Activate the *Stop configuration* switcher.
2. Select one of the check types using the radio button.

* Event-based;
* Included in a segment;
* Order-based.

<Image align="center" width="80% " src="https://files.readme.io/860d8c1ffee8c316207b3412fa325f91c570a06cb60c8f53a8788ce48348cbfc-start-block-01.webp" />

### Event-based Workflow Stop

<Image align="center" width="80% " src="https://files.readme.io/c5dff08e1cf19973032af2427540ba54f8c67f848357a060538dca5a03b874aa-start-block-02.webp" />

In the *Event* drop-down list, select the event that will stop the workflow for the corresponding contact. The workflow stops if the event happens within the selected period before the workflow starts or any time after it starts. In the *Period* field, you can set the time before the start of the workflow, during which the event must be checked. By default, the block checks for events since the activation of the workflow.

*$\{key}* is the universal variable for the event unique key specified in the block by default. When the system starts a workflow, it checks the selected event: if it finds the event unique key, the workflow ends for this contact.

You can see the event unique key in the *Automation* → *Event History* section.

<Image align="center" width="80% " src="https://files.readme.io/098039100caa9de2acbfe8fb390e1279e94b54bb3b9caf2ec6b25e6184cd408d-start-block-03.webp" />

> 📘 Important
>
> The event unique key (email, contact ID, etc.) must match in the event that started the workflow and the event that should end the workflow.

### Included in a Segment Workflow Stop

<Image align="center" width="80% " src="https://files.readme.io/4de5ae2bae643b5292fd1d20c614f406b7570f593be383aa495267a824b1f889-start-block-04.webp" />

Select a segment from the drop-down list in the *Segment* field. If the system detects that a contact enters a specified segment, it will stop the workflow for them. The system identifies contacts by one of the parameters:

* Phone;
* Email;
* Contact ID in Yespo.

### Order-based Workflow Stop

<Image align="center" width="80% " src="https://files.readme.io/84141df7cd7df6383ef0a0cb5bde683069586aa4302a5dcfd3d5ee671e25c424-start-block-04.webp" />

The workflow stops if the contact has placed an order within the selected period before the workflow starts or any time after it starts. Set the time to check in the *Period* field.\
The system searches contacts by one of the parameters:

* Phone;
* Email;
* Contact ID;

First, the system uses *Contact ID*, if it’s not specified, then by *externalCustomerId* to search for a contact, if this is present in the event parameters.
