---
title: Muting or Unmuting Telegram Notifications for Users
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Muting or Unmuting Telegram Notifications for Users | Yespo Guide
  description: >-
    The document describes how to mute and unmute notifications for Telegram
    users interacting with a bot or operator using specific API endpoints,
    detailing the required parameters and potential error responses.
  robots: index
next:
  description: ''
---
In some instances, you need to mute broadcasts for Telegram users having a dialog with the bot or an operator to avoid interruptions. And when required, the messaging shall be unmuted.

In our platform, these can be done for users with Telegram tokens. The feature is implemented through two API endpoints described below.

# Muting Notifications

To mute notifications, send requests to the following endpoint: 

* POST `/v1/apps/{app_uuid}/token/mute`

where substitute `{app_uuid}` in the path with your application UUID.

> 📘 NOTE
>
> Muted users or chats can receive transactional messages (smartsend, test).

The method’s parameters and their description are given in the following table.

| Parameter | Type   | Description                                                                                                                                                                                                                                                                                                         |
| :-------- | :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| token     | string | Required. User’s Telegram token.                                                                                                                                                                                                                                                                                    |
| duration  | long   | Optional. Mute duration in seconds: The minimum value is 5 seconds.  The maximum value is 31,536,000 seconds (approximately 1 year). If the duration is not specified, mute is set to 9999-12-31 23:59:59, disabling notifications "forever". To change the mute duration, send another request with the new value. |

The response may return the following errors listed in the table.

| Status | Error message                 |
| :----- | :---------------------------- |
| 400    | Wrong app uuid                |
| 400    | Tokens must be specified      |
| 400    | Duration must be positive int |
| 404    | Not registered application    |

The muted contacts in the campaign reports are shown as `Unavailable contacts` with `Other errors` as the error type.

<Image align="center" width="80% " src="https://files.readme.io/7c086500f0c031dbe53e632d46e985bf7c57e730ef3671f3961098985ee7508c-report_muted_contacts.png" />

The error name in the details is `CHANNEL_WAS_MUTED`.

<Image align="center" width="80% " src="https://files.readme.io/9f9dd1ca9cc71c8ae5f4327a82fa8b284533a242a4681d58669a955d60527f89-error_details.png" />

# Unmuting Notifications

To unmute notifications, send requests to the following endpoint:

* POST `/v1/apps/{app_uuid}/token/unmute`

where substitute `{app_uuid}` in the path with your application UUID.

The request must contain the following parameter:

| Parameter | Type   | Description                      |
| :-------- | :----- | :------------------------------- |
| token     | string | Required. User’s Telegram token. |

The response may return the following errors listed in the table.

| Status | Error message              |
| :----- | :------------------------- |
| 400    | Wrong app uuid             |
| 400    | Tokens must be specified   |
| 404    | Not registered application |
