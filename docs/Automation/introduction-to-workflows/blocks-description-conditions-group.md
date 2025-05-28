---
title: Conditions Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Conditions Blocks | Yespo Guide
  description: >-
    Learn about types of condition blocks and how to use them to create and
    manage workflows. Tasks of each block and the corresponding setting options.
  robots: index
next:
  description: ''
---
Conditions blocks (except for the *Split* block) check the contact's compliance with a certain condition, split the workflow into two paths (*Yes/No*), and run one of them depending on the answer.

There are eight conditions blocks in the system:

* Condition
* Split
* Sent?
* Delivered?
* Opened?
* Clicked?
* Included in Segment?
* Current day/time

<Image align="center" width="80% " src="https://files.readme.io/c9c0bf27a8e633482667922e018a75f5dcc2078809cc8e97889e0db9e4057bef-conditions-blocks-001a.webp" />

> 📘 Note
>
> The following blocks cannot be attached to the *Start* block:
>
> * Sent?
> * Delivered?
> * Opened?
> * Clicked?

## Condition

[More detailed information >](https://docs.yespo.io/docs/popular-blocks#condition)

## Split

The block is used to split-test messages. It splits the workflow into two paths and randomly divides contacts between them. By default, the percentage ratio is 50/50, but you can change it using the slider in the settings on the right.

<Image align="center" width="80% " src="https://files.readme.io/79bd48b43cb535f090473b53b6697ec766d976b70e37b6a160821eb79f2fb8e5-conditions-blocks-002.webp" />

For example, you can create a workflow to test the effectiveness of two different communication channels or two campaign types within one channel by setting the same split percentage.

The above example is a workflow testing Email and Viber. Based on the set percentage, one half of your subscribers will receive an email, and the other half will receive a Viber message. Further [analysis](https://docs.yespo.io/docs/campaigns-analytics) will help determine which channel is more effective.

## Sent?

The block checks whether the message was sent.

<Image align="center" width="80% " src="https://files.readme.io/04b5b17b826ec68665785e3ace40932888481ad79ff40814d51e670d0cb3c718-conditions-blocks-020.webp" />

The example above shows the workflow where the mobile push with the experimental recommendation algorithm is sent first. The system will not send this message without data to generate such recommendations.

At the same time, in addition to the *Delivered* status, mobile push notifications also have the *In Progress* status. It can take a long time between sending and delivery, so the *Delivered?* check is unsuitable.

If the check shows the system did not send the first message, the workflow will send the second one with a universal recommendation algorithm.

The *Timer* block is necessary for the system to have time to check the fact of sending a message. The recommended time in the timer settings is 5 minutes.

## Delivered?

The block checks whether the message was delivered.

<Image align="center" width="80% " src="https://files.readme.io/2caaf1cac06cadd4de48b4713f935404d6c3b731ae3642a4e3e6b94d04193cd7-conditions-blocks-021.webp" />

In this example, subscribers who received the first message would eventually receive the second one, and the rest would be in the segment with invalid contacts. Based on the result, you’ll be able to analyze the effectiveness of email as a communication channel and reduce the error rate in subsequent campaigns.

## Opened?

The block checks whether the recipient opened the message, and depending on the result (*Yes/No*) splits the workflow into two paths. For example, if the recipient didn’t open your email over a certain period of time, you can send one more email but with a different subject, or send a Viber message or SMS with the same content.

<Image align="center" width="80% " src="https://files.readme.io/b78fc6be6bee23103e904987d3311edbaf4cf63696b8545b9e6cf7e8374d5f23-conditions-blocks-022.webp" />

## Clicked?

With this block, you can check whether the contact clicked on the message and set alternative actions based on the results of the check. The block takes into account any click on any link except the unsubscribe link. Note that you can't choose to check a specific link.

<Image align="center" width="80% " src="https://files.readme.io/f048b3a6f986d56c72bce1ea80e35425466ac2d0d56545d2728a72714b7a76ea-conditions-blocks-023.webp" />

In this workflow, the contacts who clicked in the first email and are expected to be interested in your offer, are sent the following email with a special discount, more details, benefits of the presented product or brand, etc. This workflow ends for those recipients who didn’t click.

> 📘 Note
>
> The *Sent?*, *Delivered?*, *Opened?* and *Clicked?* blocks check messages within one workflow and do not consider whether a similar action has been performed with a message in another workflow.

### The Sent?, Delivered?, Opened? and Clicked? Blocks Parameters

The blocks contain two alternative parameters that take into account:

* **Only the last message**. The block checks only the last message before it. If the message is sent (delivered, opened, clicked), the workflow continues along one path; if it is not, it continues along the other.

<Image align="center" width="80% " src="https://files.readme.io/143ad6fa441381faf5d7e9f9946743e1d1f949d34b95559109ff3c1be68cb861-message-blocks-051.webp" />

* **All messages**. The block checks all messages before it. If all messages are sent (delivered, opened, clicked), the workflow continues along one path; if not all or none, the workflow continues along another path.

<Image align="center" width="80% " src="https://files.readme.io/7241bd531ebfcc0c406b59f6aa8b74c11e076908bc2ac9266252062f0b91c1fb-message-blocks-052.webp" />

> 📘 Note
>
> We recommend to additionally use the block *Timer*\- (*Popular* or *Time* blocks) before the blocks *Sent?*, *Delivered?, Opened?* and *Clicked?*. Otherwise, for a major part of your subscribers, the workflow will run the *No* path.
>
> Since the system immediately checks the condition compliance, and subscribers can’t immediately respond to your campaign, there is no reliable data to run the *Yes* path.

## Included in Segment?

The block checks whether the contact is included in a certain segment.

<Image align="center" width="80% " src="https://files.readme.io/e7d644d82dc8215c15c4c1af22aee29f126fc84628a1ee1f55f5a9b3b90e3c61-conditions-blocks-324.webp" />

The block has one basic parameter — *Segment*. In the field, select the segment to check for the contact's membership in that segment.

In this workflow, the subscribers who are included in the segment *Valid email* receive an email; the subscribers who aren’t included receive an SMS. Similarly, you can use other subscriber data (activity, orders, personal data, etc.) to create the most effective and personalized campaigns.

The block also contains advanced parameters, which are detailed in a separate [article](https://docs.yespo.io/docs/advanced-workflow-block-parameters).

## Current Day/Time

The block checks whether the current path is triggered based on a certain date, weekday or time.

<Image align="center" width="80% " src="https://files.readme.io/3665d36233b2951eed0a63bac72987f98735c40d58c67ce902af2448eeaf43e1-conditions-blocks-0050.webp" />

You can set up the following conditions for sending:

* certain day of the week;
* specific date;
* specific time;
* specific time on a specific date/day of the week.

Setting a specific date excludes the option to choose a day of the week. You can specify the date or day of the week and time either together or separately. By default, the time check option is inactive.

If you select a time without specifying a day, the specified time period will be checked every day.

If you choose both a day and time, the time will be checked on the specified day.

The time is checked according to the user's local time, eliminating inaccuracies associated with daylight saving time changes.

The specified boundary values are included in the check. For example, if you set the time from 08:00 to 12:00, and at the time of the check, it is 12:00, the script will follow the *Yes* branch.

Activating the *Use contact’s time zone* parameter will allow you to send a message at a specific time, taking into account the contact’s time zone.

<Image align="center" width="80% " src="https://files.readme.io/d319f91976f8f988a545d55cabfbca1b3950485d37219ee4e60e4787d2be5154-conditions-blocks-0051.webp" />

Let's look at how the block works. For example, on April 5, 2023, at 7:00 PM, there is a webinar that you can register for until the beginning of the broadcast. Depending on the date and time of the user's registration, you want different versions of email messages to be sent to them:

* **Email 1**: Before the day of the event – "We look forward to seeing you at the webinar on April 5 at 7:00 PM."
* **Email 2**: On the day of the event until 5:00 PM – "Already today! See you at 7:00 PM."
* **Email 3**: On the day of the event after 5:00 PM – "Starting very soon! Don't miss the beginning at 7:00 PM."

The workflow operates as follows:

* The workflow proceeds to the 'Current Day/Time' block and checks today's date (Is it now 05/04/2023?);
* If the date does not match the one specified in the parameter, the workflow will follow the 'No' branch – sending *Email 1*;
* If today is 05/04/2023, the workflow will follow the 'Yes' branch and check the time of day;
* If it is not later than 17:00, it will send *Email 2*;
* If the current time does not match the specified time – it means it is later than 17:00, and in that case, it will send *Email 3*.

<Image align="center" width="80% " src="https://files.readme.io/eafe688ff7fdccdad931ffab3a2355f2d69753a2ae9f8ec03204800e90c90fd5-conditions-blocks-025.webp" />

Also, using the same conditions, you can opt not to send your campaign:

* **On specified days**

<Image align="center" width="80% " src="https://files.readme.io/23d92f9a731159099e5e355c7077d918c04092bf8e45d78dad076fc26b0cee71-conditions-blocks-026.webp" />

* **On specified time**

<Image align="center" width="80% " src="https://files.readme.io/3d6d56c4693ff1e0e7c1b3a1df4dbd5097e7fb66db9f1e7dae7f44fc0469c69a-conditions-blocks-027.webp" />

* **At certain times on certain days**

<Image align="center" width="80% " src="https://files.readme.io/8c175f6e69e9206dee9e7da6a3419e6642af4432de361a41e871f3c054185070-conditions-blocks-028.webp" />

* **At a certain time and day**

<Image align="center" width="80% " src="https://files.readme.io/21521af2e87f6913e8afe0a8ab04e49d9a1f2f3580b273161b68e586950d5051-conditions-blocks-029.webp" />
