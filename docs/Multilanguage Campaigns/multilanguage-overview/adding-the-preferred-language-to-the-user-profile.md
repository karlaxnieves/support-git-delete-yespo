---
title: Adding the Preferred Language to the User Profile
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding the Preferred Language to the User Profile | Yespo Guide
  description: >-
    Learn how to add the preferred language to a user profile and enhance
    personalization. Discover step-by-step instructions to improve user
    experience with tailored content in their chosen language.
  robots: index
next:
  description: ''
---
Data collection by the system based on the browser languageContact profile has a _Language_ field that indicates the contact language. There are several ways to fill it for existing and new contacts.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c63c40b89af7b1e00eaae5862ce8f75cfc9563bc3a0b8b8d3a1e791959cb522-image01.webp",
        "",
        "Language field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Adding the Language for Existing Contacts

There are four ways to fill the _Language_ field in the contact profile:

###  1\. Contacts Import

- Add the preferred language via the [contacts import](https://docs.yespo.io/docs/file-uploading) unless such information has been added to the system before. For map to the system, the language field should be filled according to the <a rel="nofollow" href="https://gist.github.com/msikma/8912e62ed866778ff8cd#file-rfc5646-language-tags-js-L41" target="_blank">international format of RFC 5646 Language Tags</a>.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f40d0c05c940482f3b29ee5ce090e79de7a7e70c5c0cdc0b651f3e8a9277225a-image02.webp",
        "",
        "RFC 5646 Language Tags"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


For example:  
                。"es," "en";  
                。"es-AR" (Spanish, Argentina), "en-US" (English, USA).

- Update the collected data. For companies that have previously recorded the language of their subscribers, it is enough to adjust the language to the above requirements so that the system can map it correctly. To download updates, export the database and then import the updated file.

### 2. Get the Language from the Browser

Based on the subscriber’s interaction with the campaign, the system records the browser language and inserts it in the language field.

### 3. Get the Language Using Web Tracking

Data about the language of contacts identified from the _webcontact_ [web tracking](https://docs.yespo.io/docs/web-tracking-overview) event can be obtained from the headers of this event if the _Language_ field in the cards of such contacts is empty.

### 4. Change Data Manually

You can edit the language field in the [user profile](https://docs.yespo.io/docs/user-profile), regardless of how it was added.

> 📘 Important
> 
> - Changes made manually would always rank higher than the info automatically collected by the system.
> - In case the language field for the contact has already been filled, the system will not replace the existing data. The browser language would only be recorded for the empty field, and the previously added data is saved by default
> 
> During the import, the data is always updated (replaced)!

## Adding the Language for New Contacts

By default, the language field is filled for all new contacts via:

### 1. API

Transfer of the API _languageCode_ parameter by the [subscribe method](https://docs.yespo.io/reference/subscribecontact-1).

> 📘 Important
> 
> If the contact's profile does not contain the _languageCode_ field, the language chosen by a contact in the mobile app is set as a preferred language in the contact profile.

### 2. Using our Widgets

The system identifies the language of the site where you show a widget. The detection priority is the following:

1. Parse the value of the _lang_ attribute in the _HTML_ tag.
2. Parse the site URL to search for:  
   a. Path segment containing the language code in ISO-639-1.  
   b. Path segment containing the language code and location (ISO-639-1 + ISO-3166).
3. Identify the preferred language set in the browser (_navigator.language_).

Also, you can ask the customer to specify the preferred language in a subscription form, a survey, or their website profile.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff5aafb9da7409c202a28bfd2b24da976118033923dadfd0d320da8d0cfd15a0-image03.webp",
        "",
        "Data collection by the system based on the browser language"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 3. SDK

When a contact installs your mobile app, the SDK collects the data, including _languageCode_.  
See the following instructions for details:

- [iOS >](https://docs.yespo.io/reference/ios-sdk)
- [Android >](https://docs.yespo.io/reference/android-sdk)
- [React Native >](https://docs.yespo.io/reference/react-native-sdk)
- [Flutter >](https://docs.yespo.io/reference/flutter-sdk)
- [Unity >](https://docs.yespo.io/reference/unity-user-information)
- [Cordova >](https://docs.yespo.io/reference/cordova-user-information)
- [Ionic >](https://docs.yespo.io/reference/ionic-user-behaviour)

### 4. Subscription to Web Push Notifications

When a contact subscribes to [web-push notifications](https://docs.yespo.io/docs/web-push), our system collects data about the language used by a contact for data input and writes it to the contact's card.