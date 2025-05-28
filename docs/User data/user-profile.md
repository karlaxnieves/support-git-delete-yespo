---
title: User Profile
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: User Profile |  Yespo Guide
  description: >-
    Learn how to create user profiles and collect information for
    personalization and segmentation, including identifiers, personal data,
    subscriptions, etc.
  robots: index
next:
  description: ''
---
After integration with Yespo, the system automatically creates the user profile for each person who fills out forms on your website, downloads your app, etc. Here you can collect all user information, preferences, behaviors and use these data for personalization or segmentation.

To see a full contact profile, click on any blank space in the corresponding contact line in the _Contacts_ → _All contacts_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6626b7e38b95d5a4f670f9423cdb9ad0d57aa9b073ccbbee1bdcea251ef37222-user-profile-01.webp",
        "",
        "User profile"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The information in the profile is divided into two tabs: _Contact information_ and _Contact activity_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/102efb5858d01ac9deea3772056ea71744f8d7c3aeb1b7a2832ee5a034a0954c-user-profile-02.webp",
        "",
        "Contact information"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Contact information

This tab contains:

- [User identifiers](https://docs.yespo.io/docs/customer-identifiers-and-matching) — email, phone number, applications, Telegram bot ID, mobile and push tokens.
- Personal data contains name, age, gender, address, regional settings (time zone/language), etc. Also, you can add specific to your business [custom fields](https://docs.yespo.io/docs/how-add-additional-contact-fields).
- Subscription categories for campaign segmentation.
- Additional information — contact ID, created date, last edit date, source ([import](https://docs.yespo.io/docs/uploading-file-with-user-profile-data), subscription form, [order](https://docs.yespo.io/docs/orders-automation), API, etc.)

Also, here you can find information on the email address status. If the contact is blacklisted, the system automatically records the date and reason (for example, inactive email address) in the contact profile.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/335fae09a42caa492a973d0b1f6314198547351534f343fc1e4abf3c1dc92f12-user-profile-03.webp",
        "",
        "Email address status"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The system automatically records the date and reason in the contact profile if the contact has reported on spam or unsubscribed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c12d8aa575c8069f6f7a22bcebc6714954a0c1f0d13aa5f90feedb592c7460f9-user-profile-04.webp",
        "",
        "Spam complaint"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Contact activity

This tab contains a history of user actions in your app, messages, or website. You can find the number of contact activities, channel, the sent message's name, date, and status here.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/98d36605700e3b73ad67f6fafece2889b367a8490117d0a39297c6d331414c81-user-profile-05.webp",
        "",
        "Contact activity"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Attention
> 
> A widget can be displayed more times than allowed by the [display frequency](https://docs.yespo.io/docs/widget-calling#display-frequency). This can happen when a customer visits the website in incognito mode or after clearing their cache, cookies, and local data on their device.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/735fb5b0dafe36839a31a4daceb4464fbdcd4e324176496be4208cf23d98ac99-user-profile-06.webp",
        "",
        "Re-running widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Apart from _Delivered_, _Read_ and _Clicked_, the status field can also contain the _Undelivered_ and _Unsubscribed_ statuses.