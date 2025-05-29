---
title: User/Account Time Zone Settings
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: User and Account Time Zone Settings | Yespo Guide
  description: >-
    Learn the difference between User Time Zone and Account Time Zone in Yespo.
    Understand how each setting impacts message scheduling, workflows, and time
    display in the UI.
  robots: index
next:
  description: ''
---
In Yespo, there are two types of time zone settings:

* **User Time Zone** — set in your **My profile** settings

<Image align="center" width="80% " src="https://files.readme.io/d9df2233266c21c1c3d54c4ab7a7097280ca6081c6fdfca790f7609a013f6d19-tz_1.png" />

* **Account Time Zone** — set in your **general Settings**.

<Image align="center" width="80% " src="https://files.readme.io/2c8f943adba941ec1a15661f4dc9206f709e9ef7a59ee8bafda5e9711cf0c5fe-tz_2.png" />

Each of these time zones serves a different purpose. Here's how they work.

## User Time Zone (My Profile)

This setting affects **only how time is displayed** in the user interface for you personally.

For example:

* If a campaign is scheduled to start at **18:00 AM** Kyiv time (GMT+2), and your profile is set to GMT+4, you will see the scheduled time as **8:00 PM** in the UI. The actual send time won’t change — only how you see it.

<Image align="center" width="80% " src="https://files.readme.io/c63575cd679e117b25826ba1ddbd6f7b1c9bb36c6da01ba1f9fb8b019fc88217-tz_3.png" />

## Account Time Zone (General Settings)

This is the **default time zone** used

* In the [regular workflows Start time configuration](https://docs.yespo.io/docs/configuring-workflow-startstop-conditions#regular-workflow-start-configuration)

<Image align="center" width="80% " src="https://files.readme.io/28066d017dab94a5c0dd35cc074ec2809f7f87e2cff30326353662afbd02dab3-tz_4.png" />

* In workflows’ [Time blocks](https://docs.yespo.io/docs/time-blocks)

<Image align="center" width="80% " src="https://files.readme.io/fbb85815bbff320c1dc96d066e0c10c809c3989c429e5ae36020775cd0e84815-tz_5.png" />

* In the [allowed send time settings](https://docs.yespo.io/docs/allowed-send-time-messages-workflows)

<Image align="center" width="80% " src="https://files.readme.io/97def3cec6ba4a361e5cc2a8687ef6379b6883fd35a36d5a494ce5237dd09873-tz_6.png" />

* When using the [contact’s time zone](https://docs.yespo.io/docs/scheduled-mobile-push-message#4-use-contacts-time-zone):
  * Each contact will receive the message based on the time in their own time zone (if it’s defined).
  * **If a contact’s time zone is not specified**, the message will be sent according to the **account time zone**.

<Image align="center" width="80% " src="https://files.readme.io/a3a0327fab3c96140b93f988d90c3b5920941585b2c81aeda755351c44b66aaf-tz_7.png" />

## Summary

| Setting           | Purpose                                                    |
| :---------------- | :--------------------------------------------------------- |
| User Time Zone    | Controls how time appears in the UI for that user.         |
| Account Time Zone | Controls the default send time for messages and workflows. |