---
title: Managing In-App Campaigns
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Managing In-App Campaigns | Yespo Guide
  description: >-
    The guide explains In-App campaigns setup with real-time delivery,
    event-based triggers, and user segmentation to boost engagement, enhance
    experience, and meet business goals.
  robots: index
next:
  description: ''
---
There are two main ways to launch marketing campaigns: **by segments** (bulk) and **by events** (trigger). Bulk campaigns are great for Christmas newsletters, and triggered mobile pushes are essential for onboarding new users. However, In-App messages differ from emails and push notifications in terms of marketing and technical perspectives.

From a marketing standpoint, the concept of sending in-app messages is not accurate. It's more appropriate to view it as **running a continuous campaign** for a specific user segment. This continuous engagement is a key aspect of In-App campaigns.

From a technical perspective, the real-time delivery of In-App messages is of utmost importance. While a 40-second delay in sending push notifications or emails may not be a significant issue, even a 10-second delay in In-App messages can be detrimental to user experience.

Yespo's In-App messages approach fixes these issues. In-App setup and triggering rules **are configured directly in the message settings**. You can run a campaign for the segment and display it instantly through an on-device event.

Let's explore how to set up In-App triggering to meet various business goals.

## Setting Up In-App Campaigns

The preparation of In-App campaigns consists of two parts: [design of the appearance of messages](https://docs.yespo.io/docs/creating-in-app-message) and setting their triggering rules. Triggering rules contain

* selection of the event and its parameters that will trigger In-App,
* definition of target segments,
* display frequency settings.

The main settings options are events and segments.

### Triggering by Event

Select the event that will trigger In-App in its triggering rules, such as completing a lesson or a game level.

<Image align="center" width="80% " src="https://files.readme.io/368a827bd7fa0af09ed7aec2cd5b4d7eec67ab0d439ee2cc6e80746ecb05dfe6-in-app-1.webp" />

You can detail settings by specifying additional event parameters, such as completed **5th** lesson or **5th** level.

<Image align="center" width="80% " src="https://files.readme.io/910050cfd6579ab7def59a798a6a751644c0e7c7220303078a0ba232a8f99a2b-in-app-2.webp" />

> 📘 Important
>
> Only events from the [SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo) can trigger In-Apps

### Triggering by Segment

To address the In-App campaign to a certain segment, specify the appropriate segment in message-triggering rules. For example, you can incentivize the first purchase in the segment of users who use the app for a week but do not use paid functionality. To do this, [create the segment](https://docs.yespo.io/docs/how-add-dynamic-segment) with appropriate conditions and specify it in the triggering rules of the In-App with a special offer.

<Image align="center" width="80% " src="https://files.readme.io/ddce45721dfc6665c62c264c27d89c64dce76bba899ee738474c1b46c121b98a-in-app-3.webp" />

> 📘 Note
>
> Combining the *After event* and the *To whom* triggering rules is possible. For instance, limit the In-App triggering after a specific event to certain countries.

## Using In-App in Omnichannel Workflows

You can use the *Mobile Push* and the *Add to segment* blocks to trigger In-Apps within a workflow.

### Mobile Push

[Link an In-App to tap at a mobile push](https://docs.yespo.io/docs/linking-app-mobile-push), for example, to reveal more details about the offer contained in the push. Specify such a push in the *Mobile Push* block settings, and users will see both messages within the workflow.

<Image align="center" width="80% " src="https://files.readme.io/de921e4c9215af3850c41fd702dc5e9adfa503a702ff99333ae4578ffb092680-in-app-4.webp" />

### Add to Segment

1. Specify a static segment (*List*) into which users will fall in the *Add to segment* block settings.

<Image align="center" width="80% " src="https://files.readme.io/e44b8253addb111c4d038fa0470ce3539c63e66f9f73b188495db27fabd9d8e3-in-app-5.webp" />

Set the corresponding segment in the In-App triggering rules (*To whom*).

<Image align="center" width="80% " src="https://files.readme.io/d77300e47330c85617c0ac9c6abe1b8b5b23b9a094d82566fe395eb7e51aa221-in-app-6.webp" />

Adding a user to the segment in the workflow will trigger the In-App according to its triggering rules.
