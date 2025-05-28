---
title: Setting Up Delivery and Clicks Analytics
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Delivery and Clicks Analytics | Yespo Guide
  description: >-
    The article provides step-by-step guidance on implementing analytics to
    track the performance of mobile push notifications.
  robots: index
next:
  description: ''
---
Notification delivery and open rates allow you to analyze the success of your mobile push campaigns in more detail. To display this data in Yespo, you need to implement the return of the status of messages to our system.

Before proceeding with this step, [connect your app to your Yespo account](https://docs.yespo.io/docs/connecting-mobile-apps) and upload the contact database.

Choose one of the two available methods for transferring push notification status data from your app.

> 📘 Note
> 
> The delivery and click analytics methods described below are intended for projects that have not installed our SDK

## Public API

Use this _[Update interaction status](https://docs.yespo.io/reference/registerinteractionstatus-1)_ API method to return DELIVERED status (if the notification was delivered to the device).

In addition to the status value in _interactionId_, also pass the FCM token and the time of status change on the device in the request's body.

Example:

```json
{
    "token": "bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
    "status": "DELIVERED",
    "time": "2020-07-09T15:11:17"
}
```

There are differences for exporting message delivery data from different operating systems.

### iOS

Getting a report on push notifications is possible using <a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/unnotificationserviceextension" target="_blank"> Notification Service Extension</a> and calling the API inside the service extension.

1. Add Notification Service Extension to your app.
2. In _didReceiveNotificationRequest_ add your code for calling web service to report to your server about the received message.

- override func _didReceive_ (\_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) → Void)
- _didReceiveNotificationRequest_ should consist of a http request (PUT) with delivered status to [Update interaction status](http://docs.yespo.io/reference/registerinteractionstatus-1).

Enable Background fetch in _Capabilities → Background Modes_ of your app.

> 📘 Note
> 
> The "content-available" and "mutable-content" parameters are enabled (have value == 1) when transmitting tokens to APN. If data transmission is configured via FCM, only the “mutable-content” parameter is enabled and has value == 1.

Learn more about modifying content in delivered notifications in <a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications?language=objc" target="_blank"> Apple's guide</a>.

### Android

Use a service that extends <a rel="nofollow" href="https://firebase.google.com/docs/reference/android/com/google/firebase/messaging/FirebaseMessagingService" target="_blank"> FirebaseMessagingService</a> to receive messages. A service should override the _onMessageReceived_ and _onDeletedMessages_ callbacks.

### Tracking click-through rates

In the [message editor](https://docs.yespo.io/docs/how-to-create-mobile-push-notifications), you can add a link to the message body without being able to analyze its click rate.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a10dc277fe4434e874eaa35d55886ea1e6f5fcdd273f5b20c236b01752385d5-c632dc3-pushlink.webp",
        "",
        "Adding link to the message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When adding a link, two more fields _\- es\_link\_raw_ and _es\_link_ - will be passed in the push notification body:

- _es\_link\_raw – `http://example.com/somelink`_ – contains the original link that can be opened in the device’s browser or can be an internal link, directing to other app sections;
- _es\_link – `https://hh.esclick.me/37NdHw333DjRcukc0l`_ – created based on the added link and contains a wrapped link used for click tracking.

> 📘 Important
> 
> For your mobile app, use the data from the field _es\_link\_raw_ to redirect the user to the app section or to the web resource; use a _GET_ request by the link in _es\_link_ to track clicks.

## Integration with Firebase Message Cloud and BigQuery

<a rel="nofollow" href="https://bigquery.cloud.google.com/" target="_blank">BigQuery</a> allows you to process large amounts of data, analyze it in detail using BigQuery SQL, export the information to other services, and or use the data for your custom machine learning models. In order to transmit the statuses of sent mobile notifications to Yespo through this platform, you need to follow these steps:

1. <a rel="nofollow" href="https://firebase.google.com/docs/cloud-messaging/understand-delivery?hl=en&platform=ios#bigquery-data-export" target="_blank">Link your project to BigQuery</a>.
2. Set up data export from the app to BigQuery:

- <a rel="nofollow" href="https://firebase.google.com/docs/cloud-messaging/understand-delivery?platform=ios#export-platform" target="_blank">iOS</a>;
- <a rel="nofollow" href="https://firebase.google.com/docs/cloud-messaging/understand-delivery?platform=android#export-platform" target="_blank">Android</a>.

3. [Integrate your Yespo account with BigQuery](https://docs.yespo.io/docs/google-bigquery-integration).