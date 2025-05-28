---
title: Sending Email Messages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Email Messages | Yespo Guide
  description: >-
    A step-by-step guide to creating and launching your first email campaign in
    the platform. Create, test, launch and measure the results!
  robots: index
next:
  description: ''
---
Once you [create an email](https://docs.yespo.io/docs/adaptive-email-builder-review) and [prepare an audience for sending it](https://docs.yespo.io/docs/segmentation),  you can launch a campaign. Let's look at this process step by step.

## Choose the Email

1. Go to _Messages → Messages_. Choose the message you want to send and click the _Create campaign_ button. You can also use this button inside an email.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be431b50f74d621355513be7354964f9460836ddc2bc35cd02f17d7d4e1e247d-sending-email-1.webp",
        "Create campaign",
        "Create campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the pop-up window, choose segments or contacts for the campaign and click on _Go to campaign_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c89e02289503cc04ad81fd307bdab6b85263f1144b29513e7960cb39bfeab976-sending-email-2.webp",
        "Choose segments",
        "Choose segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You’ll be forwarded to the campaign scheduling with the following information.

## Scheduling Details

1. **Campaign name.** The name is generated automatically. It includes the message name and the segment name. You can edit the campaign name if necessary. You can find a campaign by its name in _Reports_ and _Scheduled campaigns_.
2. **Recalculate contacts.** Click on it to see the number of contacts to whom the email will be sent.
3. **Included in campaign:** segments selected for the campaign. Click on _Edit_ to add or change segments.
4. **Excluded from campaign:** contact segments excluded from the campaign. Click on _Select segments_ or _Edit_ to exclude other segments from the campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/26ab9673d571abef1bf2edd513c2a0c5148fccc5313a173f6e0175cff9777070-sending-email-3.webp",
        "Scheduling details",
        "Scheduling details"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. **Multilanguage.** For [multilingual campaigns](https://docs.yespo.io/docs/multilanguage-overview), you can see the number of email language versions. You can switch between languages in one click to see the corresponding copy.
6. **Message name:** the name you set when creating the message. This name is automatically set as the _UTM tag_ in _utm_campaign_.
7. **Tags.** Each message can be attributed with [tags](https://docs.yespo.io/docs/how-add-tags) for better search and filter.
8. **Subscriptions categories.** You can create [subscription categories](https://docs.yespo.io/docs/how-use-subscription-category) in the profile settings and use them for more accurate campaign personalization.
9. **Subject:** the subject line of the message. If it isn’t specified, you’ll see a corresponding notification. Go back to the email editor to specify the subject line. Messages without subject lines cannot be sent.
10. **Sender name.** The name is automatically created based on the login. You can change it in your profile settings.
11. **Sender address.** Check it if you use several email addresses to send your campaigns.
12. **Email preview.** Before sending, double-check the email body. Ensure it has no spelling mistakes, broken links, images, irrelevant CTA, etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0ceeefffcaf63d177005e0bfaed466c07f91a51b35180a680d15c38e5cab4c20-sending-email-4.webp",
        "Scheduling details",
        "Scheduling details"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Send Options

Here, you can configure the following options:

### 1. Batching

You can choose the _As soon as possible_ option or limit the speed by specifying the number of messages sent in a particular time (minute, hour, day, week). Rate limiting is required, for example, if there are limitations related to [domain warming up](https://yespo.io/blog/first-campaigns-new-domain-how-warm-right).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/948bb3ecbdda5df5851b3dc3bd63ce5b3b70a3a17701eb9a649b7a40b4f97d63-send-options-1.webp",
        "Batching",
        "Batching"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can set a limited sending speed for a campaign that involves at least ten contacts and does not use the option of sending by contact time zone.

### 2. Annoyance Level

[The annoyance level](https://docs.yespo.io/docs/management-campaign-frequency) allows you to limit the number of campaigns for specific segments to avoid contact database burnout.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29d255a8b21cdb758d6e3eaf399ee20c931616fabd9647fb66ab272b03a379d6-send-options-2.webp",
        "Annoyance level",
        "Annoyance level"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 3. Test

Send yourself a message to check it's correct.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/177eca4e21fd61976b1c1ba28425fbf6b1e61b76e2b00152c849c9da2db19851-send-options-3.webp",
        "Test",
        "Test"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 4. Schedule

Click _Schedule_ to set the date, time, and frequency of sending the campaign.

### 5. Use Contact’s Time Zone

If your database contains many contacts from different time zones, activate this option so that they receive the campaign at a time convenient for them and you.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bcad1e406bce7bf5ad5412ae2be03080dfa5fd703890494e1f6be657f188a313-send-options-5.webp",
        "Contact’s time zone",
        "Contact’s time zone"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


For example, if you schedule a campaign for 4:00 p.m., the contact will receive it as soon as 4:00 p.m. occurs in their time zone.

Contacts whose cards do not have a time zone will receive a message based on the time zone set in your account settings.

> 📘 Note
> 
> You cannot set batching if the contact's time zone is enabled.

Campaigns scheduled by time zones are marked with a special icon on the report table and inside the report. The same icon is displayed in the campaign list scheduled by time zone.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d4742cc1ea2e19a42c7bfa9554374351623f3e7ff8b03791aab503d0483f71fb-send-options-6.webp",
        "Time zone icon",
        "Time zone icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To cancel sending a scheduled campaign based on your contacts' time zone, go to the _Campaigns →  Scheduled campaigns_ section, click on the campaign name, and turn off the _Use contact's time zone_ switch. The campaign will be sent to all contacts in the account's time zone when the scheduled time arrives.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0e21af6b97e8ccfbe36e51f1f9a851af85671c5d4305eadf49c2bcd93d469163-i3.gif",
        " Scheduled campaigns",
        " Scheduled campaigns"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If the campaign is scheduled for a time that has already arrived in one of the time zones, it will immediately go to the _Reports_ section as active and will begin to be sent as soon as contacts appear from the time zone in which the scheduled time occurs. It will not appear in the _Scheduled campaigns_ section.

If the scheduled time has not yet arrived anywhere, after scheduling, such a campaign will be displayed in the scheduled ones until the specified time arrives in the first time zone (UTC+14), after which it will move to the _Reports_ section as active.

Contacts in a time zone where the campaign start time has already passed will receive the message the next day at the same time.

> 📘 Note
> 
> Using the contact's time zone is available for all Yespo channels

### 6. Start Immediately

Click _Start immediately_ to send the campaign immediately after passing the moderation.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a572e40d53ab4f3485bb0024646c8dc894b4d8d8f85605a315ff8e783ae3411-send-options-8.webp",
        "Start immediately",
        "Start immediately"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After launching or planning, the campaign will be sent for moderation. Moderation is carried out at +03 GMT and takes at most 10 minutes during working hours (Mon-Fri - 8 am - 7 pm; Sat-Sun - 9 am - 6 pm) and 1-3 hours in the evening time and on holidays. Moderation is not carried out at night.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c48d49d5b283ec94d1b8b8b7dafad6f9f4de095bb7e80bfaedaf0dfe374e7cee-sending-email-6.webp",
        "Moderation",
        "Moderation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Moderation Statuses

- **Preparing for sending**.
- **Moderation**.
- **Blocked:** the campaign has been rejected by a moderator. The email with the reasons for blocking will be sent to your email address.
- **Confirmed:** the campaign has been approved by a moderator and is waiting for the sending.

Immediately before sending the campaign automatically transferred to _Campaigns → Reports_. Here, you can see the information on the sending and the statistics.