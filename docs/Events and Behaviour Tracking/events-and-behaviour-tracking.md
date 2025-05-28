---
title: Events and Behavior Tracking
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Events and Behaviour Tracking | Yespo Guide
  description: >-
    Guide on tracking of user actions across apps, sites, and campaigns to
    enhance retention through automated campaigns, segmentation,
    personalization, and analytics
  robots: index
next:
  description: ''
---
Yespo allows you to track events within your app, site, or campaigns resulting from your users' actions: subscriptions, orders, views, clicks, etc. 

You can stream events to Yespo with the SDK help from the front end (for [iOS](https://docs.yespo.io/reference/ios-sdk) & [Android](https://docs.yespo.io/reference/android-sdk)) or [through API](https://docs.yespo.io/reference/registerevent_1) from back end. [Event validation](https://docs.yespo.io/docs/validating-event-parameters) will help you to check the correctness of event parameters at the setting up stage.

Use events for creating automated campaigns, segmentation, personalization, and analytics.

## What are the benefits of event tracking

- [Automated campaigns](https://docs.yespo.io/docs/introduction-to-workflows) are triggered by real-time events, which means you can send relevant, timely messages: stimulate first order with special offers, reactivate those who didn't make target action after some critical time, etc. Use our ready-made workflows for different mobile-first solutions to speed up and facilitate movement through your sales funnel.
- [Segmentation](https://docs.yespo.io/docs/segmentation) helps you to know your customer preferences. Data on website behavior, mobile app and message activity is collected in real-time. You can create dynamic micro-segments for hyper-targeted campaigns based on order history, average check, date of the last order, and any other criteria you like. As a result, every user will receive content that meets their interests.
- [Personalization](https://docs.yespo.io/docs/personalization-and-dynamic-variables) is an ability to construct dynamic content in messages, in the app, and on the site based on contact data: recommendations, a random selection of goods, and urgent offers for different user categories.
- [Analytics](https://docs.yespo.io/docs/campaigns-analytics) generates data-driven solutions and predicts customer behavior. While processing new information from events, AI constantly learns and adapts to new tasks. Based on analytics on the changing and updating data, AI algorithms help answer the central marketing question: To which recipient what content in what order when to send.

## Event Types

Yespo is working with two types of events:

**1\. System generated events** are collected automatically. They include actions that occur in your omnichannel campaigns:

- Delivery and its statistics by user devices and domains;
- Opens;
- Clicks;
- Unsubscribes and spam complaints;
- Delivery errors and their reasons.

**2\. Custom events** are anything that occurs in your app, site, CRM, or CMS:

- App and browser behavior;
- Session duration;
- Orders and all their parameters;
- Custom outcome;
- Subscription updates.

**Note**

Read _Sending Past Events_ for more information on how to transfer historical events to Yespo.

> 📘 Note
> 
> By default, the system stores event data for 2 years. All this data you can use for segmentation. To increase or decrease the storage period, leave a request at [support@yespo.io](mailto:support@yespo.io).