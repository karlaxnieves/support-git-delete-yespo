---
title: Scheduled Mobile Push Message
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Scheduled Mobile Push Message | Yespo Guide
  description: >-
    The document outlines the process of creating and managing mobile push
    notification campaigns, including options for testing, saving, and launching
    campaigns, configuring send options like batching and scheduling, and using
    contact time zones.
  robots: index
next:
  description: ''
---
After creating a message in the editor, you have three options.

<Image align="center" width="80% " src="https://files.readme.io/793fac42c4a6b237b34ee82fb143f73b560b90a6f753cdf0eda21a201f1c72ed-scheduled-mob-push-01.webp" />

You can:

1. **Test** – specify a phone number and send a test message to it without leaving the editor.
2. **Save and exit** – the message will be saved in your account, and you can return to editing it.
3. **Create a campaign** – go to sending the current message. The system will not allow you to do this if the required fields are not filled in, for example, the name of the message is not indicated.

Clicking on the **Test** or **Create campaign** icons you may see the following popup window:

<Image align="center" width="80% " src="https://files.readme.io/413ddf5307437a08a342082f6513e7e8576defb2d901a66f918eb14f598a01c0-scheduled-mob-push-02.webp" />

This is a system reminder that the mobile app is not yet connected or that you haven't selected the appropriate pricing plan for sending your mobile push notifications. If everything is set up all right, you will be able to launch your campaign immediately.

## Campaign Launch

If you want to send a previously saved notification, click on the **Create campaign** button in the message list on the **Messages** → **Messages** → **Mobile push** tab.

<Image align="center" width="80% " src="https://files.readme.io/9fcf259b4b196327006d6c93aa77070a8580b2219dc6848f948a7f8a0f8ce8e7-scheduled-mob-push-10.webp" />

To launch a campaign from the editor click on **Create campaign**:

<Image align="center" width="80% " src="https://files.readme.io/3d2b0b7d2d1baf80af656365b17c5cd7e7e779653f8e3659addd0a0742eb3eb9-scheduled-mob-push-09.webp" />

Select in the popup window the segments you want to send the push notification to.

<Image align="center" width="80% " src="https://files.readme.io/9b2a0178e6d46a4e57971c0b59db86c68f977e5460f6afb22bdb1912dd58687b-scheduled-mob-push-03.webp" />

You just have to check the box next to one or more segments. If the contact is in both selected segments, no duplicate is created and only one push notification will be sent to the user.

In the preview window, check all the data to start the push notification campaign.

<Image align="center" width="80% " src="https://files.readme.io/ca02fa56781592e79023f66f1526c19729a849eff6ab5eb1ae9908f9c846ad1c-scheduled-mob-push-08.webp" />

## Send Options

Here, you can configure the following options:

### 1. Batching

You can choose the **As soon as possible** option or limit the speed by specifying the number of messages sent in a particular time (minute, hour, day, week).

<Image align="center" width="80% " src="https://files.readme.io/a438ed8c29bdffe00d655a403a2eef3a9be6c6793f46f6bbe6386251e034b63c-send-options.png" />

> 📘 Note
>
> You can set a limited sending speed for a campaign that involves at least ten contacts and does not use the option of sending by contact time zone.

### 2. Test

Send yourself a message to check it's correct.

<Image align="center" width="80% " src="https://files.readme.io/8b665020fe8b720a019163685109239251f20825de272e41d857ef7d4c0b806f-test.png" />

### 3. Schedule

Click **Schedule** to set the date, time, and frequency of sending the campaign.

### 4. Use Contact’s Time Zone

If your database contains many contacts from different time zones, activate this option so that they receive the campaign at a time convenient for them and you.

<Image align="center" width="80% " src="https://files.readme.io/4894b04d6691b2848f7c5973a306ec2d7f113e0a73abd76ecc0c6aea5dd38cfe-send-options-5.webp" />

For example, if you schedule a campaign for 4:00 p.m., the contact will receive it as soon as 4:00 p.m. occurs in their time zone.

Contacts whose cards do not have a time zone will receive a message based on the time zone set in your account settings.

> 📘 Note
>
> You cannot set batching if the contact's time zone is enabled.

Campaigns scheduled by time zones are marked with a special icon on the report table and inside the report. The same icon is displayed in the campaign list scheduled by time zone.

<Image align="center" width="80% " src="https://files.readme.io/7b39326cd5870e458f2d6621a442047b75311c9ba5a7242c919386c1ecb246d2-scheduled-campaigns.png" />

To cancel sending a scheduled campaign based on your contacts' time zone, go to the **Campaigns →  Scheduled campaigns** section, click on the campaign name, and turn off the **Use contact's time zone** switch. The campaign will be sent to all contacts in the account's time zone when the scheduled time arrives.

<Image align="center" width="80% " src="https://files.readme.io/a1c0e6f14a7012aae8056696a47b9cb4768f1ca65bf340608610f75681cc6722-fd8a4a5-scheduling.gif" />

If the campaign is scheduled for a time that has already arrived in one of the time zones, it will immediately go to the **Reports** section as active and will begin to be sent as soon as contacts appear from the time zone in which the scheduled time occurs. It will not appear in the **Scheduled campaigns** section.

If the scheduled time has not yet arrived anywhere, after scheduling, such a campaign will be displayed in the scheduled ones until the specified time arrives in the first time zone (**UTC+14**), after which it will move to the **Reports** section as active.

Contacts in a time zone where the campaign start time has already passed will receive the message the next day at the same time.

> 📘 Note
>
> Using the contact's time zone is available for all Yespo channels

### 5. Start Immediately

Click **Start immediately** to send the campaign immediately after passing the moderation.

<Image align="center" width="80% " src="https://files.readme.io/ceddc991c5e3993a5a731de0faf6729793e0308c1936e956a4926481a56efd86-start.png" />

After launching or planning, the campaign will be sent for moderation. Moderation is carried out at +03 GMT and takes at most 10 minutes during working hours (Mon-Fri - 8 am - 7 pm; Sat-Sun - 9 am - 6 pm) and 1-3 hours in the evening time and on holidays. Moderation is not carried out at night.

## Moderation Statuses

* **Preparing for sending**.
* **Moderation**.
* **Blocked:** the campaign has been rejected by a moderator. The email with the reasons for blocking will be sent to your email address.
* **Confirmed:** the campaign has been approved by a moderator and is waiting for the sending.

Immediately before sending the campaign automatically transferred to **Campaigns → Reports**. Here, you can see the information on the sending and the statistics.

## Sending Messages Automation

You can also use campaign scheduling to send regular and automatic messages, such as birthday greetings.

### Option 1. Schedule a Message for a Segment

1. Create the segment with the condition **Birthday = today.**

<Image align="center" width="80% " src="https://files.readme.io/ab6326414723449c8c877cef7c016ea6b3e3ed5d81f3c6ed5cc0f6f563e3528f-scheduled-mob-push-04.webp" />

2. Go to the saved push notification and click on the **Create campaign** button.
3. In the **Send options** window, select the **Schedule** button. In the window that appears, specify the time for sending, and in the **Recurrency** field, select the frequency **Every day** and confirm the settings.

<Image align="center" width="80% " src="https://files.readme.io/70cfad6ff2d297395b5c9b81959f46685774083c7f135279ea91e45303cb179a-scheduled-mob-push-05.webp" />

### Option 2. Send Message from Workflow

1. Create the segment with the condition **Birthday = today**.
2. Build the workflow using three simple blocks:

   * Start;
   * Mobile Push;
   * End.

   <Image align="center" width="80% " src="https://files.readme.io/66adb7ed6171613b46c1acd4b830d96d157ec68e491710ea35457b268b68b953-scheduled-mob-push-06.webp" />
3. You don't need to set conditions for the first and third blocks. In the parameters of the **Mob Push** block, select the message that you have prepared for the notification:

<Image align="center" width="80% " src="https://files.readme.io/64e0b9b5bb2e68e1c8d378ffcd19830142a24334dcad98aafdf4f25ebc78363c-scheduled-mob-push-07.webp" />

In the launch conditions, select the regular type of workflow, specify the created recipient segment, and set other necessary settings.

You can see the results of all launched campaigns in the [reports tab](https://docs.yespo.io/docs/mobile-push-campaign-report).