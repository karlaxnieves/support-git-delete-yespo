---
title: Sending Campaign to Those Who Did Not Open the Previous One
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Campaign to Those Who Did Not Open the Previous One | Yespo Guide
  description: >-
    Resend campaigns efficiently with three methods: Extra Campaigns via
    Reports, Exporting Contacts from Reports, and Workflow automation.
  robots: index
next:
  description: ''
---
The system has three methods to resend the campaign to contacts who have received the message but haven't read it.

1. Extra campaigns functionality.
2. Via the exporting contacts from the report.
3. Using a workflow.

## Extra Campaigns Functionality

1. Go to *Campaigns → Reports*.

<Image align="center" width="80% " src="https://files.readme.io/197dcfd7efcdad1e26ce7350d481b2c328a2edfa5d067a37474b0166afdd1db3-sending-campaign-to-those-who-did-not-open-the-previous-one-001.webp" />

2. Click *Extra campaigns* in the list of campaigns,

<Image align="center" width="80% " src="https://files.readme.io/1d977c8b5d4ee1e5c31b507f5e23f47d5d9d0b413f0b1fe85e3e066617e6accd-sending-campaign-to-those-who-did-not-open-the-previous-one-002.webp" />

Or open the report and click the *Extra campaigns* button.

<Image align="center" width="80% " src="https://files.readme.io/24553dbfbccfe0e63735c3452914f18f1396d185da15e19f9919b2adf48f80de-sending-campaign-to-those-who-did-not-open-the-previous-one-003.webp" />

3. Select the *To contacts who will receive the message but won’t open* it option.

<Image align="center" width="80% " src="https://files.readme.io/58eabdc1f77e48841a0a3095254f8f4633d8e64631f4d9d4217a6efa80dac3e0-sending-campaign-to-those-who-did-not-open-the-previous-one-004.webp" />

3. Select a media channel and message from the list.

<Image align="center" width="80% " src="https://files.readme.io/adaef03bd1a114b6167326d26195ea06792f55324a642bc7db773af58ea2aff7-sending-campaign-to-those-who-did-not-open-the-previous-one-005.webp" />

You can find the message by a keyword or a specified tag in the search bar.\
Check all the data, as before a regular campaign.

[Learn more about extra campaigns >](https://docs.yespo.io/docs/how-send-extra-campaign)

> 📘 Important
>
> To send extra campaigns, you need to subscribe to any Extra features pricing plan.

## Via the Exporting Contacts From the Report

1. Go to *Campaigns → Reports* and select the report.

<Image align="center" width="80% " src="https://files.readme.io/ca499a6c1f2377c170b4e4361821aa9be6944ccf727e4ec0c71e9e5b5b8a5636-sending-campaign-to-those-who-did-not-open-the-previous-one-006.webp" />

2. Click *Export → Unread → To the new list*.

<Image align="center" width="80% " src="https://files.readme.io/fb1d323213a7a29096642df964a449829406f9d49e3c3d86e2f1e1c68d11fabd-sending-campaign-to-those-who-did-not-open-the-previous-one-007.webp" />

3. Enter the list name (in our case, it’s *Unread campaign*) and click *Create*.

<Image align="center" width="80% " src="https://files.readme.io/67227a918ce957d6b6b54f658cb0ff150466fd2d7b53ead622f63b691e9fb904-sending-campaign-to-those-who-did-not-open-the-previous-one-008.webp" />

4. Go to *Contacts → Segments* and click the *Create campaign* button next to the *Unread campaign* segment.

<Image align="center" width="80% " src="https://files.readme.io/a40ab3731bf1660ab62a934b6e6d9efe3a554df5b191038d70308173fc9a92a4-sending-campaign-to-those-who-did-not-open-the-previous-one-009.webp" />

5. In the *Messages for campaign* window select the message.

<Image align="center" width="80% " src="https://files.readme.io/82b5df7e6b851947473dd816cae277e839c0376d04ba3612a93b160ddf2d809b-sending-campaign-to-those-who-did-not-open-the-previous-one-010.webp" />

You can find the message by a keyword or a specified tag in the search bar.

6. In the campaign planning menu, select the sending options.

<Image align="center" width="80% " src="https://files.readme.io/3a21f41f4b53d2a8bd973d0319180b00982c185263a6e68d7ade285afc69de13-sending-campaign-to-those-who-did-not-open-the-previous-one-011.webp" />

After moderation, the extra campaign will be launched for those contacts who have received the message but have not opened it.

## Using a Workflow

1. Create a workflow.
2. Build a chain of blocks:

* **Start**. Automatically appears and starts the workflow.
* **Email to segmen**t. Sends a message to the selected segment.
* **Timer**. Sets the specified time before performing the following actions.
* **Opened**. Checks whether the contact opened the message.
* **Email to segment**. Sends a repeated message to the selected segment.
* **End**.

<Image align="center" width="80% " src="https://files.readme.io/eba3ce3128c201bf9d5eaaa96d29c6a1d8cb7a403c849f4cde471ad6228dc354-sending-campaign-to-those-who-did-not-open-the-previous-one-012.webp" />

3. Set up workflow blocks and click *Save and launch one time*,

<Image align="center" width="80% " src="https://files.readme.io/36fcee0c19fcccd4e564c7104a3dff7597fd670c079054e49c488acfbf5cc473-sending-campaign-to-those-who-did-not-open-the-previous-one-013.webp" />

or click *Save and exit*, then select the ellipses (three dots) icon beside the workflow and select *Launch one time*.

<Image align="center" width="80% " src="https://files.readme.io/f13545b6d2505fa0f98f951b5f4a93259ab8ea10e78e8eaa2070824cde218424-image.png" />

4. Click the *Start* button.

<Image align="center" width="80% " src="https://files.readme.io/8f6f83327679b394fe80bf8db674d261bafd6b3ce32de91205cceba146d2e18c-sending-campaign-to-those-who-did-not-open-the-previous-one-015.webp" />