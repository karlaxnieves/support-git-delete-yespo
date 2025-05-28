---
title: Actions After Subscription
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Actions After Subscription | Yespo Guide
  description: >-
    The document guides configuring post-submission actions for subscription
    forms, including segmenting contacts, enabling double opt-in, setting email
    confirmations, redirects, and onboarding.
  robots: index
next:
  description: ''
---
After [creating the subscription form](https://docs.yespo.io/docs/setting-up-widgets-for-your-site), you can configure the following actions to occur after a contact submits it:

* Add contacts to a segment.
* Double Opt-In.
* Email confirmation.
* Redirect after clicking on the confirmation link.
* Onboarding.

## Add Contacts to a Segment

By default, new contacts collected through subscription forms are saved to your account without being added to segments. To save new contacts to a segment:

1. In the *Add contacts to segment* section, click *Save contacts to segments*.

<Image align="center" width="80% " src="https://files.readme.io/b22972682cc2a1f004749b493442be2943a3df7877514f291b6cc18ffcb6a68b-add-contacts-2segment-en.webp" />

2. In the Segment edit window, select the corresponding *segment* or *segments* and click *Done*.

<Image align="center" width="80% " src="https://files.readme.io/66f8b4b3edc2ec352733884edf519b9eba686ca2e46df7e3c9ec92f38f14dcbc-segment-edit-done-en.webp" />

You can create a new segment to add new contacts who subscribe using this widget.

<Image align="center" width="80% " src="https://files.readme.io/7ce6640e4726fde65354062c5bbdeefe0a3cb21fb5911593d6c045f79fbe67fa-new-segment-button-en.webp" />

## Double Opt-In

When a subscription form is created, the Double Opt-In option is enabled by default in its settings to verify the email address specified by the contact by sending a confirmation email to that address.

<Image align="center" width="80% " src="https://files.readme.io/b81f5f7665e6aa33fc3cd0e337125ad9fa537403ff6c32b0cfe7f3285d2914b9-Actions_After_Form_Submission_2.webp" />

> 📘 Important
>
> * When this option is enabled, a subscription confirmation email is sent. There is no need to use the SysContactConfirmed event in your workflows.
> * When the option is disabled, the email addresses of all contacts are automatically added as confirmed. We advise you not to use this method to avoid being [marked as spam](https://docs.yespo.io/docs/faq-quick-start#how-not-to-get-into-spam).

## Email Confirmation

Initially, a default email message is added to the settings of this section, which will be sent to new contacts. A preview of this message is shown in the section.

<Image align="center" width="80% " src="https://files.readme.io/418dd2d0486dd37135fd239d65f101b1c119c0b9fc974f4db5b6666cd06c3e76-image001.webp" />

To edit the default message:

1. Click the *Edit* button. This navigates you to the email editor.

<Image align="center" width="80% " src="https://files.readme.io/3f282b4d0915d6fb831cbd801c42fa8f20003ba660f573b4821e875792280336-image002.webp" />

2. Make the necessary changes and save the message. For more information about working with the email editor, see this [article](https://docs.yespo.io/docs/email-editor).

To replace the default message:

1. Select *Replace*.

<Image align="center" width="80% " src="https://files.readme.io/37ab66ea735ed60966e46493b4cf085af0e89b3b409c69e77a05dfa13aab1ba3-image003.webp" />

2. Select the *message*.

<Image align="center" width="80% " src="https://cdn.yespo.io/photos/shares/Support/Images/Forms/onboarding-select-message-window22-en.png" />

You can disable the *Only messages with a confirmation button* option to select from all your messages and add such a button to the selected message by yourself.

<Image align="center" width="80% " src="https://files.readme.io/be798b94d6834699ebc6735368e38b0726456195f0294a3b8ead3dc6b22beb3f-image005.webp" />

In the *Email confirmation* section, you can copy the message ID to quickly find it later in the general list.

<Image align="center" width="80% " src="https://files.readme.io/03272461c665d10b7ed5b1f3a79adf445c665d6c1bc978a8acc5aea2a5939cec-image004.webp" />

> ❗️ Attention
>
> The button for confirming the email address shall have the following settings:
>
> * **Link**
> * **Event type**

**Link**:

* Type: *Subscription confirmation*,
* Value: `$data.get('redirectUrl')`

<Image align="center" width="80% " src="https://files.readme.io/6bed91d97c60373893a66f840549f0267779f2e89bf0d6a9c1b62e43a22658de-Actions_After_Form_Submission_4.webp" />

**Event type:** *SysContactConfirmed*

<Image align="center" width="80% " src="https://files.readme.io/851113d6bb39123b8f716c183036db8ab50f4fad4a6da7324a5c2667b3dc8982-Actions_After_Form_Submission_5.webp" />

If you need to change the system workflow, [see the instructions](https://docs.yespo.io/docs/replacing-double-opt-system-workflow).

## Redirecting After a Click on the Confirmation Link

Once a contact has verified their email address, you can redirect them to:

* Redirect page
* Verified domain URL

<Image align="center" width="80% " src="https://files.readme.io/5b9ba0aae41f9626f1afa57ee642b8043a78652cd83f791dbcb38fed8e71311c-Actions_After_Form_Submission_6.webp" />

If you select Verified domain URL, specify your *company website* or its *subdomain* in the URL field.

<Image align="center" width="80% " src="https://files.readme.io/db55b3c32574bfbfa3c6b23f5b8bf7427692d6bb02d980232dd3ad80f5665d0c-Actions_After_Form_Submission_7.webp" />

If you don’t have verified domains, click the *Verify domain* button.

[More details about verifying domain >](https://docs.yespo.io/docs/dns-record-change)

## Onboarding

Set up further communication steps to be triggered after your subscribers confirm their email addresses. To do that:

1. Enable the *Onboarding* slide button.

<Image align="center" width="80% " src="https://files.readme.io/0c72bd99a44e71d9551f44d84ba8f50476a4e8051ccbfa96d3d45627eb52b3b9-onboarding-off-en.webp" />

2. Choose one of the following *options*:

* Send welcome email
* Send welcome series through workflow

<Image align="center" width="80% " src="https://files.readme.io/cfd31b4a7e2e0e561ed49372c6364200d7650a1512cf3582fbe8c5281af9fa43-onboarding-options-en.webp" />

If you selected the Send welcome email option:

1. Click on the *Select message* button.

<Image align="center" width="80% " src="https://files.readme.io/5495fa748c87243ee86122be95bde8c45cd56033fc28e75b4b3d2ed6ef0f2108-onboarding-select-message-en.webp" />

2. Select the required *message*.

<Image align="center" width="80% " src="https://files.readme.io/2360239f1b455ad5b4981ee12e218cc753f14da98605d10bacd7d3ffad985878-onboarding-select-message-window22-en.webp" />

Just like in the email confirmation, you can replace the message, edit it, and copy the ID.

<Image align="center" width="80% " src="https://files.readme.io/eab53838cf639827d75b4067aa28fcd002f90cb9bc4d942df605eaa0e85699be-image006.webp" />

> 📘 Note
>
> The email will be sent automatically, it is not necessary to create an additional workflow.

If you selected the Send welcome series through workflow option:

* Select the *event type* from the dropdown list. It only displays event types from the Subscribe/Unsubscribe category.

<Image align="center" width="80% " src="https://files.readme.io/0a4f863616b43fdd3548d95b346f22ecd35914655e7dcaaf9e8a7be7dd6d33ab-onboarding-event-type-en.webp" />

Or

* Click the *New Event* button and create the new event type in the opened window. Read more in this [article](https://docs.yespo.io/docs/creating-events#creating-an-event-type).

> 🚧 Important
>
> * The welcome series workflow is triggered only after a contact confirms their email address. You do not need to add the Contact confirmed condition in such workflows.
> * To trigger the welcome series workflow, you must select the same event type as selected in the widget settings.

<Image align="center" width="80% " src="https://files.readme.io/10e4e3fed5158a552d6cd9a8fae44872d2fe3175ac381dfaf9b4edbea9aa4480-workflow-event22-en.webp" />

Activate the toggle *Only to new contacts* to avoid sending a welcome campaign to existing contacts.

<Image align="center" width="80% " src="https://files.readme.io/433e803a75bc90ae2334e9626d071abd2245ce0646b0f550f7fc8337783719e7-onboarding-only-new-contacts-en.webp" />
