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

Typically, one workflow includes either the block with one message to one contact ([Contact blocks](https://docs.yespo.io/docs/contact-blocks)) or the block with the *Message to segment*.

There are six block types:

<Image align="center" width="80% " src="https://files.readme.io/0ff71bc123b7438c4ce86f562df8654d4045cba7f5c06b8d3c92266b3d795be5-message-to-segment-blocks-0200.webp" />

> 📘 Important
>
> Do not use these blocks for triggered messages. If the event passes the token or contact ID, use one of the [*Message*](https://docs.yespo.io/docs/message-blocks) blocks (one message to one contact).
>
> The blocks *Message to segment* are only used for events that pass the segment ID, or for workflows that are launched for a selected segment (for example, dynamic).
>
> Even if you set *[Regular](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions#regular-workflow-start-configuration)* in *Trigger configuration* and select a segment, you still need to use the block with one message to one contact, because this trigger type doesn’t pass a segment group ID to the workflow. Instead, it launches the workflow separately for each segment contact and passes the *email* and *contact ID* at each launch.

## Common Block Parameters

Each *Message to segment* block contains several parameters:

* **Message**: required parameter. 

To select a message:

1. Click the *Select message* button on the right side of the settings panel.

<Image align="center" width="80% " src="https://files.readme.io/8cbb6383bbb69f85c98643849545311c2a9aa99a10d0597f3162184d18d15f74-message-to-segment-blocks-200.webp" />

2. Select a message from the list (by default, the last created one is selected) or specify the dynamic variable *$\{emailMessageId}* using the button next to the search bar.

<Image align="center" width="80% " src="https://files.readme.io/90164dea49470c427b2a06697f53a981471aa5d5c89180f88bd541d27dcb62ac-message-to-segment-blocks-201.webp" />

To search the message in the list, use the search field by message name, subject, [tag](https://docs.yespo.io/docs/how-add-tags), or ID.

You can also sort messages by their update date.

<Image align="center" width="80% " src="https://files.readme.io/22b0c3444cf8d69164071233ff9b6df75214b5e1bce1d521b7b6e88e7aa13ee1-message-to-segment-blocks-202.webp" />

If a workflow is associated with a message, it appears in the list. To open a preview of the workflow, hover over its name and click the corresponding icon.

<Image align="center" width="80% " src="https://files.readme.io/45eb1a0242afdd71dd93a9c34d33e53ec84e0b3263997a0a72eed1a388d24940-message-to-segment-blocks-203.webp" />

The following actions are available in the message selection window:

* Create a message copy
* Message preview

<Image align="center" width="80% " src="https://files.readme.io/4765a9b39e7b3310d69220de84363ad6e8a3f2656ca1ff86fd6d171304b7c7fb-message-blocks-205.gif" />

3. Click the *Select* button.

<Image align="center" width="80% " src="https://files.readme.io/6c2c22288975d05952a3e74d5a00ca14963e7c9af328157eab9918bb08387b40-message-to-segment-blocks-204.webp" />

By clicking on the three-dot icon, after selecting the message in the block settings, you can:

* Preview the message
* Replace the message
* Edit the message in a new tab
* Copy the ID

<Image align="center" width="80% " src="https://files.readme.io/7fdedf7253e68f89e4a8c2e7c3d44a15232c7273da163e711ca85256d0d3286f-message-to-segment-blocks-205.webp" />

If you delete the message, a corresponding tooltip will appear in the block settings.

<Image align="center" width="80% " src="https://files.readme.io/aa6c945568265910b86e45848074bec72974c628368abf29599d040f9ad12a49-message-to-segment-blocks-206.webp" />

In that case, you should select a new one by clicking the *Replace message* button.

* **Segment**: required parameter. Select the segment in the drop-down menu or use dynamic variable *$\{segmentId}*. You can also select *New list segment* / *New dynamic segment* options and create a segment directly in the workflow.

> 📘 Note
>
> Conditions are not yet set when creating a dynamic segment directly in the workflow, and, accordingly, there are no contacts. Therefore, before launching such a workflow, it is necessary to set the conditions for segment formation in its settings.

After adding or creating the segment in the block parameters, you can proceed to its preview and copy the ID.

<Image align="center" width="80% " src="https://files.readme.io/cd823929211757bb8e10eb5b97c380c3595a70b2599b08e0012e5f464bfd1109-message-to-segment-blocks-preview-01a.webp" />

> 📘 Important
>
> Each segment in the Yespo system has its own ID. For example, if you send an event and with an ID value pass the GroupId parameter
>
> *"name":"segmentId", "value":167039898*
>
> *167039898* will be substituted into the workflow instead of *segmentId*, and the workflow will be launched to this segment. You need to know what the ID corresponds to so as to control the campaign, indicating what to send to which segment.

* **Send only in specified hours**: Enable this parameter to send messages only within a specified time gap.

<Image align="center" width="80% " src="https://files.readme.io/012d574766a7fa15baf7434da93c1c5b31a5c297e4a1f0ad6dc87e652eb49cc5-message-to-segment-blocks-222.webp" />

## Individual Block Parameters

* **Site** (*Web Push to segment* parameter): required parameter. The website that collects tokens is specified by default. If you have several websites, choose one from the drop-down menu.

<Image align="center" width="80% " src="https://files.readme.io/ff5fec546935271c529efc525f6106fe9c7c2a719f33de75de718b083fd51453-message-to-segment-blocks-003a.webp" />

* **Application** (*Mobile Push to segment* parameter): required parameter. An app identifier for accounts with more than one app. You can select the app to send notifications from the dropdown list or specify dynamic parameter *$\{appId}*. The system extracts the app ID from the event that has triggered the workflow. When sending events through the [SDK](https://docs.yespo.io/docs/sdk-mobile-apps), this parameter is passed automatically.

<Image align="center" width="80% " src="https://files.readme.io/c47c607e346097b6fb4c0479c07e8d47b7b9c3c4942c3f45c896b90a03b9caed-message-to-segment-blocks-004a.webp" />
