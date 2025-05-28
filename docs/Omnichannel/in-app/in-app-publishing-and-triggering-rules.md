---
title: In-App Publishing and Triggering Rules
excerpt: In-App Publishing and Triggering Rules
deprecated: false
hidden: false
metadata:
  title: In-App Publishing and Triggering Rules | Yespo Guide
  description: >-
    Learn about flexible In-App display options to ensure they work as
    efficiently as possible in any given situation.
  robots: index
next:
  description: ''
---
After saving [the message’s appearance](https://docs.yespo.io/docs/creating-in-app-message), its additional settings page will open, where you can:

* Publish the In-App and schedule it’s displaying
* Return to appearance edits
* Set triggering rules

> 📘 Important
>
> [Install SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo#1-install-sdk-and-connect-communication-channels) to send In-Apps through Yespo.

Before publishing In-App messages, subscribe to a pricing plan.

> 📘 Note
>
> * The number of contacts in a subscription is calculated based on *deviceId*.
> * If the number of contacts in an In-App channel exceeds the plan’s limit, messages will not be displayed to contacts above the limit.

## Publishing and Scheduling

Select the *Published* option from the list and save the changes to display the message to app users according to the rules below.

<Image align="center" width="80% " src="https://files.readme.io/288d5c42e59751b48f76e97bcaaae68bb3f365f2db1eaa1728e6f12f2cd5be82-in-app-1.webp" />

Select *Unpublished* to stop the message from displaying, then save your changes.

You can also specify the In-App display schedule by clicking the calendar icon.

<Image align="center" width="80% " src="https://files.readme.io/d476b32fdbcbef4c788bd2fa3a74165f133b39af12c53bdb51a004635a28909f-in-app-2.webp" />

The schedule includes the following options:

* Display start and end dates
* Custom dates and time
* Device timezone — if this option is selected, the display schedule will be applied according to the time zone set on the recipient's device; or you can select one of the timezones from the list

<Image align="center" width="80% " src="https://files.readme.io/fcf581784efb52510eee96998b1beb4261f7d3ecdd18e121a2b61d0126dd434e-en.webp" />

Message statuses are displayed in the general In-App list:

* Published — for published widgets with a current or no scheduled period
* Unpublished
* Scheduled — the publication period is planned for the future
* Expired — the publication period has expired

## Editing

Click *Edit* on the *Appearance* tab to return to editing the message. 

<Image align="center" width="80% " src="https://files.readme.io/c3a7bfed6615a6674ca9f6641f6b26418ebc2789cd9f33f7635e5f9cc8b73a14-in-app-4.webp" />

## In-App Triggering Settings

The *Show Only once* rule is activated by default. Click *Edit* to change the display rules.

<Image align="center" width="80% " src="https://files.readme.io/f3cf0492d195557cb1e57bbfeaa2f2caa3044a75755920a8e8a88b9c3f7185bb-in-app-5.webp" />

> 📘 Note
>
> In-App can be sent only [through a tap on a mobile push message](https://docs.yespo.io/docs/linking-app-mobile-push) without setting triggering rules.  Configure triggering rules to display In-App messages as separate entities.

1. You can choose the following options in the *Display frequency* section:

* Do not limit (the message will be shown once after the session starts unless additional conditions are set)
* Only once (the message will be shown once during the app’s life on the device)
* Once per session (session ends after 5 minutes of user inactivity; session duration is unlimited)
* One time per X minutes/hours/days/weeks (message will be shown every time after the specified period)
* X time, but no more than once per minute/hour/day/week (the message will be displayed the specified number of times after the specified time has expired)

<Image align="center" width="40% " src="https://files.readme.io/2726409a553415a1349a72d31dac78f519f282ff9bc4487be89ea9c3476d8e67-in-app-6.webp" />

2. You can choose the following options in the *When to display* section: 

* On app open
* When any condition is met:
  * Spent X seconds/minutes in app
  * After the event (select one from the list)

<Image align="center" width="40% " src="https://files.readme.io/ea57cdb518f8d5b0c72b388ba7a54130e04c4659949771e495b6c2801c37076b-in-app-7.webp" />

When you activate the *Show after event type* option, you can add one or more event parameters and their values to be checked (the parameter can contain, be equal to, or start with a value).

<Image align="center" width="40% " src="https://files.readme.io/beb34a328f4b7617935d172040d16fee31fa18aa7365cc6315356f99f052402b-in-app-8.webp" />

3. You can choose static and dynamic segments from which contacts should be shown messages in the *To whom* section (*deviceId* identifies contacts).

<Image align="center" width="40% " src="https://files.readme.io/9a9b8ba82531cf8dd44533f6f6cbfa8ae146c636ae1b86cf2ca03ecb1d1f7c00-in-app-9.webp" />

> 📘 Note
>
> You can test messages with set triggering rules only in the test version of your app

## Revenue Calculation

If you turn on revenue calculation, purchases will be associated with the message accordingly to the [settings](https://docs.yespo.io/docs/how-set-revenue-campaign).

<Image align="center" width="80% " src="https://files.readme.io/b69bdd50ed2c3cc545812c0e6fa87dbb0fdc88fff6c631975fb44439b9d95457-in-app-en2.webp" />

Changes apply to future purchases.

After saving, the In-App will appear in the general list, where you can change its publication status or delete the message.

<Image align="center" width="80% " src="https://files.readme.io/2fb5e2181908e1d31b6a4c14a752b40e9d61352030642fa9c180ed9082385ca7-in-app-10.webp" />
