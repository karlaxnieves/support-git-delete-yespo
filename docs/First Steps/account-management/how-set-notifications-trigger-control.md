---
title: Control Over Events, Tags and Promocodes
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Control Over Events, Tags and Promocodes | Yespo Guide
  description: >-
    The document outlines a process for setting up alerts to monitor automated
    workflows, message tags, and promocode availability, detailing how to create
    notifications and workflows to send alerts via email or SMS when specific
    conditions are met.
  robots: index
next:
  description: ''
---
There is always a risk that some technical or human error will occur that will cause the processes you have automated to fail. To find out about such problems promptly, set up alerts about:

* **Events** received during a specific period to ensure the correct functioning of workflows and segmentation by events. If the integration breaks, events stop flowing into the system, associated workflows do not run, and associated conditional segments are not updated.
* **Messages with specific** [tags](https://docs.yespo.io/docs/how-add-tags) sent over a specific period to maintain the expected frequency of mailings. Message tracking helps control mailing failures that are not related to the arrival of events: for example, due to a lack of funds.

> 📘 Note
>
> The most effective way to control triggers is to specify a lower limit on the daily number of events and message tags included in the workflow associated with that event. Therefore, we recommend that you assign tags to messages corresponding to the associated event.

* **The number of promocodes** in your Reteno account to ensure that you have enough unused promocodes left because if they run out, the system will not be able to send messages that use the corresponding type of promocodes.

## Creating Notification

1. Go to your profile settings → **Notifications** and click **New notification**.

<Image align="center" width="80%" src="https://files.readme.io/dfe1d5b951f79659668978e8bd601ac08ee80974815d35e4a807dfa1d09cb35a-image2.webp" />

2. Select the following parameters:

* **Type** (Event/Tag/Promocode),
* **Title**, or in the case of promotional codes – Type,
* **Amount**,
* **Period** (only for tags and events),
* **Notification type** (Alarm or Warning).

<Image align="center" width="80%" src="https://files.readme.io/b2eaf445e49b1c30554c2b5593cdb6a5f2ce3c64ce7d6a2b877e8c72696afe82-new-notification.webp" />

> 📘 Note
>
> We recommend using both types of notifications — **Warnings** and **Alarms**. For example, you can set a warning when there are 500 promocodes left in the system, and there is still time to respond, and an alarm for 50, when you immediately need to load the next list of promocodes.

3. Click **Create**.

You can set up as many notifications as you wish. But all of them will be transferred through one of the following event types:

* Warning — `alertSettingsWarningTriggerEvent`
* Alarm — `alertSettingsAlarmTriggerEvent`

<Image align="center" width="80%" src="https://files.readme.io/01eb8607c9c697957e5bfa3e4be031cb48f27c2c22fba6e0b5cf355cbc93a506-image5.webp" />

The parameters of these events will contain the following data:

| <div style={{ width: "250px" }}>Name</div> | Value                                                                                               |
| :----------------------------------------- | :-------------------------------------------------------------------------------------------------- |
| `alertLevel`                               | WARNING/ALARM                                                                                       |
| `periodDays`                               | The period selected for counting (only for tags and events)                                         |
| `threshold`                                | The lower limit for tags/events/promocodes                                                          |
| `alertTrackingSourceType`                  | Notification type (TAG, EVENT, PROMOCODE)                                                           |
| `alertTrackingSourceName`                  | Tag or event title/promocode type                                                                   |
| `actualCount`                              | The number of sent messages/events/promo codes in the account at the time the notification was sent |
| `organisationName`                         | Your account name                                                                                   |

Create a message For each notification type – **Warning** and **Alarm** into which the parameter values from the event will be inserted, and a workflow through which this message will be sent.

## Substituting Event Parameters into the Message

Create email and/or SMS messages into which data from the event will be inserted using [Velocity variables](https://docs.yespo.io/docs/introduction-to-velocity).

Insert the variables into the message involved in the workflow in the `$!data.get('name')` format, where

* `$!data.get` — extract data command,
* the parameter name from which the value should be extracted is indicated in parentheses.

Since events can transmit data about both events and tags or promocodes, messages should be universal, for example:

`$!data.get('alertLevel')` for the `$!data.get('organisationName')` organization!

* **Notification type:** `$!data.get('alertTrackingSourceType')`
* **Tag or event title/promocode type:** `$!data.get('alertTrackingSourceName')`
* **The number of sent messages/events/promo codes in the account at the time the notification was sent:** `$!data.get('actualCount')`
* **The period selected for counting (only for tags and events):** `$!data.get('periodDays')`
* **The lower limit for tags/events/promocodes:** `$!data.get('threshold')`

<Image align="center" width="80%" src="https://files.readme.io/fad3b4cc8a4e2ef9ab085a18007f9ad2f2dd9d256da99b8886f9b548adde2562-notification-example.webp" />

## Setting Workflow

Create 2 workflows – for the Warning and Alarm events – with the **Send obligatory (transactional) email** or the **Send transactional SMS tasks**.

Below is an example for the **Warning** workflow; the **Alarm** workflow should be done in the same way.

Fill in block fields:

1. Send obligatory (transactional) email:

* **Contact’s email:** manager's email address.
* **Message:** email with variables.

<Image align="center" width="80%" src="https://files.readme.io/8ff3b661a5657763045da9862e27849efad10c0a0f0fac3df2cbfcec6a10e3c7-image6.webp" />

1. Send transactional SMS:

* **Message:** SMS with variables.
* **Phone:** manager’s phone number in full international format.

<Image align="center" width="80%" src="https://files.readme.io/e3e35cbc5a214dfdf4006fc7511ad2590bdfda40b2e163fd17bab0987799a74f-image4.webp" />

Connect events to workflows [according to the instructions](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions) and launch the workflows.

<Image align="center" width="60% " src="https://files.readme.io/8d533cf6f8c8581726a04e020c5e909ac8cfd36ba4cfa049929ee412d63c3222-image7.webp" />

Now, whenever an event occurs related to one or another notification you created, the workflow will launch and send messages with information about the corresponding issues that need attention.