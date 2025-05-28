---
title: Integrating Your App with Yespo
excerpt: How to connect mobile apps with Yespo
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 📘 Note
> 
> [You can see getting started instructions for product marketers by the link >](https://yespo.io/support/quick-start)

Read our integration setup documentation for guidance below

## 1. Install SDK and Connect Communication Channels

Retain your mobile app users and boost the ROI of your mobile app with mobile push messages.

To start messaging with your users, follow the steps below:

1. [Provide Yespo access to your app](https://yespo.io/support/connecting-mobile-apps-esputnik) with the FCM and, optionally, APN keys.
2. [Set up the SDK access key](https://docs.yespo.io/reference/managing-mobile-sdk-access-keys). 
3. Integrate the required SDK versions into your mobile app:
   - [iOS SDK](https://docs.yespo.io/reference/ios-sdk)
   - [Android SDK](https://docs.yespo.io/reference/android-sdk-setup)
   - [React Native SDK](https://docs.yespo.io/reference/react-native-sdk)
   - [Flutter SDK](https://docs.yespo.io/reference/flutter-sdk)
   - [Unity SDK](https://docs.yespo.io/reference/unity-sdk-setup)
   - [Cordova SDK](https://docs.yespo.io/reference/cordova-sdk-setup)
   - [Ionic SDK](https://docs.yespo.io/reference/ionic-sdk)

> 👍 [Connect Mobile App >](https://my.yespo.io/settings-ui/#/mobile-push/app/new)

Add more channels to increase reach and ROI. The more channels you use, the more repeat sales you can get: [Email](https://yespo.io/support/email-setting-up), [SMS](https://yespo.io/support/creation-sms), [In-app messages](https://yespo.io/support/creating-in-app-message), [Web push notifications](https://yespo.io/support/web-push), and [App Inbox messages](https://yespo.io/support/app-inbox).

## 2. Upload Contacts & Add User Data

Yespo will automatically collect new tokens. Emails and [user IDs](https://yespo.io/support/external-id-creating-and-updating-users) will be collected after integrating SDK (see instructions on collecting [iOS User Information](https://docs.yespo.io/reference/ios-user-information) and [Android User Information](https://docs.yespo.io/reference/android-user-information)).

Also, you can [import all user data](https://yespo.io/support/importing-historical-data) you collect to unify it into single profiles on one platform and get the best targeting & personalization.

> 👍 [Import >](https://my.yespo.io/contacts-ui/#/contacts-import/history)

## 3. Launch Event Tracking

Benefit your retention strategy [by using events](https://yespo.io/support/events-and-behaviour-tracking): launch time-sensitive campaigns, build real-time granular segments, and let the AI learn from user behavior to send precise offers.

Log custom events [through SDK](https://docs.yespo.io/reference/ios-user-behaviour).

[Use API](https://docs.yespo.io/reference/sendhistoryevents-1) to transfer your historical event data.

> 👍 [Check Events >](https://my.yespo.io/events-ui/#/events-list)

## Advanced Integration Options

Most often, the integration steps described above are sufficient. For special occasions, the following setting options are helpful.

### Use case 1. You register many events in Google Analytics & Firebase

In this case, you can [transfer events via BigQuery](https://yespo.io/support/streaming-events-firebase) to Yespo and immediately use data from events for segmentation and launching trigger chains. 

> 📘 Note
> 
> Data from GA is updated only once an hour.

### Use case 2. You need to send some users events (like Subscriptions or Payments) from your backend

Use our backend API method [_Generate event_](https://docs.yespo.io/reference/registerevent-1) to send custom backend events.

### Use case 3. You have mobile & web projects

Data from online stores about **contacts and orders** is stored only on the backend. Therefore, to transfer it to Yespo, you need to use the following API methods:

- Use the _[Add Contact](https://docs.yespo.io/reference/addcontact-1)_ method to create the user's profile to an account or update an existing one ([details >](https://yespo.io/support/adding-new-users)).
- Use _[Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1)_ method to transfer orders.