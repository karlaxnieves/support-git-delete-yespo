---
title: Time Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Time Blocks | Yespo Guide
  description: >-
    Discover Time Blocks in marketing automation workflows. Learn how to delay
    actions or schedule them for specific times using the Timer and Start on
    Date block types to optimize workflow execution.
  robots: index
next:
  description: ''
---
The blocks delay the execution of workflow actions or execute actions at a specified time and contains two block types:

* Timer
* Start on date

<Image align="center" width="80% " src="https://files.readme.io/f156edc402c083e2a831405ccd53596150cdde908f94eacc2665269b689aa837-time-blocks-001a.webp" />

## Timer

The block is used to set a time gap before the next action or message sending. It is placed before a block you want to delay.

<Image align="center" width="80% " src="https://files.readme.io/03a8826ee1a1866359751450ce74b19c668acce9b07c576e467133abdd7528e8-time-blocks-002.webp" />

Contact confirmation triggers the workflow with a drip welcome series in the example. A new contact receives a welcome email after confirmation, a second email after two days, and a third after the next three days.

To set up *Timer*, configure one of 2 or both parameters:

* Wait time
* Wait until

<Image align="center" width="80% " src="https://files.readme.io/3856a93924ebd7b981997495da858a746e445a66e302c43af35d2f70492845db-time-blocks-003a.webp" />

You can configure all parameters or only one; at least one parameter should be configured to start a workflow.

### Wait Time

<Image align="center" width="80% " src="https://files.readme.io/4dd64027fd38f6234c51a857b768a47b10614277bb5f223a6e2bfded129532b8-time-blocks-004a.webp" />

Enter the time of delay, and select the parameter to which it will be applied:

* minutes
* hours
* days
* months

Important

If you delay for 1/2/3 days, the delayed action will start 24/48/72 hours after the workflow is triggered. If a person subscribes to you at 7 a.m., they will receive the first email at 7 a.m. the next day.

### Wait Until

In the Wait until parameter, you can specify the time yourself, use data from an [additional field](https://docs.yespo.io/docs/how-add-additional-contact-fields) of the contact card or from the context parameter (the event that launches the workflow).

<Image align="center" width="80% " src="https://files.readme.io/0730de5372e192e6692235d2e3402ce294cba55ca659e747221502147ff46c0d-wait-until.webp" />

#### Specifying the Time Manually

Here you can select the day of the week and the time for sending.

<Image align="center" width="80% " src="https://files.readme.io/50afa5c4142f4377bc524272fd81c04ef6809dce11e170c545f5305eb5ca7de1-settings-3.webp" />

If you set the sending time at 8:45 a.m. and the workflow starts at 3:00 p.m., the subscriber will receive the message at 8:45 a.m. the next day.

> 📘 Important
>
> If today is *Tuesday* and you've chosen to send a message on *Monday*, the message will be sent next *Monday*. If it's *Monday* today, the subscriber will receive the message today.

#### Using the Time from an Additional Contact Field

For example, you can use this option to set up reminders if you collect data in additional fields about the time your subscribers perform specific actions: make purchases, exercise, study, etc.

Select the contact field containing the time you want to wait.

<Image align="center" width="80% " src="https://files.readme.io/2de8b55a9acb2e1c5a1ebdd7cd7929bf872c251d3571a3a5be165afe7973df8f-settings-4.webp" />

The time from the contact field is based on the contact's time zone and must be sent to the text field in the HH:MM or HH:MM:SS format. If the field of a contact participating in the workflow has a missing or written in an incorrect format value, the corresponding error will be displayed in the launch history of such a workflow.

#### Using the Time from a Context Parameter

You can use this option to set up reminders if the data about the time your subscribers perform specific actions is not tied to additional fields and you are focusing on actual data — for example, when the last event about the workout start was received.

Specify the event parameter containing the time to wait until.

<Image align="center" width="80% " src="https://files.readme.io/2c6be4b38b081e8a9f97e98e8fc6f2fe82396e472b177b6fe343a8d244a30fa9-context-parameter.webp" />

The time from the event parameter is based on the contact's time zone and must be sent to the text field in the ISO 8601 format. If the value is missing or written in an incorrect format in the event that launches the workflow, the corresponding error will be displayed in the workflow's launch history.

### Use Contact’s Time Zone Parameter

Activating this parameter will allow you to send a message at a specific time, taking into account the contact’s time zone.

<Image align="center" width="80% " src="https://files.readme.io/32403e5838026509e5f5a5f18fec79f5bbb637dcfdaf4aa866362320120dc7d3-time-blocks-006a.webp" />

### Parameter Priority

For example, you've configured the following delay parameters:

* wait day;
* send on Monday.
* send time at 8:45 a.m.

<Image align="center" width="80% " src="https://files.readme.io/bc803d29cfb7339931f4e266bde55e82c79960f8461671a6c8e3c0fe47fe78ed-time-blocks-008.webp" />

The workflow starts on Sunday at 3 p.m. The system waits for 1 day (24 hours). Then it's Monday. The *Wait* 1 day parameter expires at 3 p.m. on Monday. The system checks the *Send* parameter. You have chosen Monday, today is Monday, so far everything is fine.

The system checks *Send time*. It’s set for 8:45 a.m., and the workflow is triggered at 3 p.m. The subscriber will receive the message not this Monday but only the next one at 8:45 a.m.

## Start on Date

The block is used to send a message:

* before *X* days/hours/minutes before the date and time you send in the event;
* with the start time you send in the event or set manually;
* on date from an event parameter or specified in a block.

> 📘 Note
>
> * If the start time is taken from the event, the transferred time zone is applied.
> * If the start time is set manually, the block will start in the time zone specified in your personal profile.

<Image align="center" width="80% " src="https://files.readme.io/21d770f5423a3dbff4fb46fd29f3902b9d7754479e989f0dc320c69d5c007a77-time-blocks-007a.webp" />

In the *In* field, specify when before the date to send the message: *1 hour*, *3 days*, *10 minutes*, etc.

In Before date, you can take the required date from the sent event. In the box below insert the parameter name from the event, for example, *$\{starDate}*.

> 📘 Important
>
> There are two supported formats for the date and time:
>
> 1. UTC: 2011-12-03T10:15:30;
> 2. UTC offset: 2011-12-03T10:15:30+02:00.
>
> The UTC offset is the difference in hours and minutes from UTC for a particular place and date. UTC+02:00 is used in some countries of Central Africa Time, Eastern European Time, and South African Standard Time. See the full list <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_time_zones_by_country" target="_blank"> here</a>.

Activate the *Use contact’s time zone* parameter to send a message at a specific time, taking into account the contact’s time zone. 

<Image align="center" width="80% " src="https://files.readme.io/5d680d63c0480e8d6d16b27ca36ac56f7dbb3be6f39373bc2102fc453f6f907b-time-blocks-0001.webp" />
