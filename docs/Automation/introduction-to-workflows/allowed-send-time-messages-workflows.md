---
title: Setting Up Allowed Send Time
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Allowed Send Time for Messages from Workflows | Yespo Guide
  description: >-
    See how to set up allowed send time for messages from workflows. By
    implementing allowed time settings, the probability of o engaging with
    subscribers at their most convenient moments is significantly heightened.
  robots: index
next:
  description: ''
---
Set the allowed time for sending messages from workflows, for example, from 10:00 am to 6:00 pm on weekdays.

If the trigger to send a message fires outside the allowed time, the system will send it as soon as the next allowed period begins.

> 📘 Note
>
> * Checking the allowed time when sending single messages first occurs [according to the contact's time zone](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system#time-zone); if it is not set, according to the time zone of the Yespo account.
> * Checking the allowed time for sending messages to segment occurs according to the time zone of the Yespo account.

## Setup Steps

1\. Go to account settings → *Workflows* tab.

<Image align="center" width="80% " src="https://files.readme.io/c9212f4bc138406981ae0744e8ae8c3254d02295fe37fc7cde27e58a7edd8a48-setting-time-messages-from-workflows-001.webp" />

2\. Activate the switcher and specify the allowed send time.

<Image align="center" width="80% " src="https://files.readme.io/839d59b1e5d3794e4909253257f4b7a8eb9dc01d227a1b70b35af7b4ee32b517-Settings.webp" />

3\. Activate the *Send only at specified hours* switcher in the settings of the message-sending block.

<Image align="center" width="80% " src="https://files.readme.io/039f215dd26f032244a3e1f7eb5d79ebe2297f6ade4f5520a41d73be8fdf22c7-setting-time-messages-from-workflows-003.webp" />

## Send Time Mapping

The message with the allowed sending time settings is marked with a clock icon in the workflow and its [launch history](https://docs.yespo.io/docs/using-workflow-launch-history).

<Image align="center" width="80% " src="https://files.readme.io/e960127cee718898f25f3565f52be2d3c54edc7a360b49f38a335ee84c0535dc-setting-time-messages-from-workflows-004.webp" />
