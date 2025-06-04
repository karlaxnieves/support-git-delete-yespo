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

<Image align="center" width="40% " src="https://files.readme.io/f81bd534d10a42f7d0a43044f388ff494dbf69924ddbeea33b0424295b9b722a-reminders-1.webp" />

## Creating Additional Contact Field

An [additional contact field](https://docs.yespo.io/docs/how-add-additional-contact-fields) stores any users’ information; in our case, we need a storage for user time. If you already have such a field, skip this section.

1. Go to your account settings → *Additional fields* tab and click *New field*.

<Image align="center" width="80% " src="https://files.readme.io/0173bc0f627d1132946f152a07f810076d2b7d7b794d7e209d33498f207779c8-reminders-2.webp" />

2. Configure the field parameters:

* **List of fields** — select the existing one from the drop-down list.
* **Name**, based on which personalization key will be generated.
* **Personalization key**.
* **Field type** — *Text input*.

<Image align="center" width="80% " src="https://files.readme.io/b5b9d60c2fffbab9a4d060971e94b37778f245aa78688810dcef25a415107edf-reminders-3.webp" />

After creating the field, you can fill it by [importing a file](https://docs.yespo.io/docs/file-uploading) with the corresponding data or by API ([Add/update a contact](https://docs.yespo.io/reference/addcontact-1) or [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) methods).

The time must be sent in the *HH:MM* or *HH:MM:SS* format.

As the system waits until the specified time in the user's time zone, configure recording the user's time zone in Yespo [through SDK or API](https://docs.yespo.io/docs/tracking-user-time-zone-and-language).

## Setting Up Workflow with Timer Block to Automate Reminders

1. Go to the *Automation → Workflows* section and open or create a workflow.

<Image align="center" width="80% " src="https://files.readme.io/b65c5280d54e2452869cc421de443a4014a113308c8f8c9d0363a291a982571b-image.png" />

2. Drag the *Timer* block from the left sidebar into the workflow.

<Image align="center" width="80% " src="https://files.readme.io/a852eb6173ba00885715d7b64badefe4ff9a7f0c22b80a2238a4b4f9e0b04361-reminders-5.gif" />

> 📘 Note
>
> The *[Timer](https://docs.yespo.io/docs/time-blocks#timer)*  block sets a time gap before the following in the workflow action.

3. Configure the block parameters:

* Disable the *Wait time* switcher and enable the *Wait until* switcher to send reminders as soon as the specified time comes
* Select the *From the contact field* option from the drop-down list
* Select the created contact field from the drop-down list

<Image align="center" width="80% " src="https://files.readme.io/0cf1f125c225f17d1a18b005e3740d72c9e114ea3dbb3e9715b79c69639dcf87-reminders-6.webp" />

> 📘 Note
>
> Use the [*One from many*](https://docs.yespo.io/docs/using-one-many-block) message block to improve retention with diverse content for training or lesson reminders.

4. Save the workflow.

## Workflow’s Start Configuration

1. In *Automation → Workflows*, select the created workflow and click *Trigger configuration*.

<Image align="center" width="80% " src="https://files.readme.io/38f5cc1ba0ba0eab5d30ae9747ac99fdcd1895ab9cbfc5c13abf0fb87ec93993-image.png" />

2. Activate *Start configuration* switcher.

<Image align="center" width="80% " src="https://files.readme.io/e8ca606025efbb367d1982d64157ea4e3bb0c7d2315cf79a3be0c563b967d0ed-reminders-8.webp" />

There are two options to launch a workflow with reminders: *Event-based* and *Regular*.

### Event-based Workflow

Select *Event-based* in *Start configuration*, and then

* Select event which must launch the workflow
* Specify the frequency of processing unique events

<Image align="center" width="80% " src="https://files.readme.io/db4ddabd51af37cfd6e885e5adb9a4beff749162d3eaaaa145227fb25d3bec34-event-based.webp" />

### Regular Workflow

1. Create a [dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment) with users subscribed for reminders.
2. Select *Regular*, and then

* In *Segment*, select the created segment
* Select the workflow’s *Start date*

<Image align="center" width="80% " src="https://files.readme.io/53b0c90d71ceea82f145f54313525e7826ae7e6fc24ad98ef9c9a191940ad2fa-reminders-10.webp" />

* In *Start schedule*, select once a day
* Select allowed start days

<Image align="center" width="80% " src="https://files.readme.io/3b63ba01313f9dfad43378d958bd5c5ceaeb4811c76d29ad1e43eed3ae8c78a4-reminders-11.webp" />

* Set the workflow’s *Start time*
* In *Process unique events*, select *Each time*

<Image align="center" width="80% " src="https://files.readme.io/87fe2ee87773a4f095fa0701fdfe2f156ee50e52dbcdb539f939103747666816-reminders-12.webp" />

## Launching Workflow

1. Click *Apply* in *Start/Stop configuration*.

<Image align="center" width="80% " src="https://files.readme.io/7665f71b1d1722acd286fdc419ad0bc4d2b37affd6d03d42cd476da092e23596-reminders-13.webp" />

2. To start the workflow, click *Activate* on the right and confirm the action.

<Image align="center" width="80% " src="https://files.readme.io/7123479817d7b70b0e77a1d54e9a920285f9fb596b5fc4840afe546cd539ff9e-image.png" />

The system will wait for the designated time in the user's time zone and perform the action specified in the workflow after the *Timer* block.

> 📘 Note
>
> If the field of a contact participating in the workflow has a missing or written in an incorrect format value, the message will not be sent