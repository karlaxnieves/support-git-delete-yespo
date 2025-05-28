---
title: Tracking Campaign Performance in Google Analytics 4
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Tracking Campaign Performance in Google Analytics 4 | Yespo Guide
  description: >-
    Enable UTM tags in your account and track performance of your campaigns in
    different channels. No extra integration with GA is required.
  robots: index
next:
  description: ''
---
Google Analytics 4 (GA4) is a new version of the Google Analytics platform that provides deeper and more complete tools for event analysis, unlike Google Universal Analytics, where the emphasis is on sessions. Event tracking allows you to collect data about user interactions with brands more flexibly and detailedly. Instructions for getting started with GA4 are available <a rel="nofollow" href="https://support.google.com/analytics/answer/10089681?hl=en" target="_blank">here</a>.

> 📘 Note
>
> Check the settings for transferring UTM tags in your Yespo account: it must be activated. Learn more about [UTM tags](https://docs.yespo.io/docs/how-transfer-utm-parameter).

<Image align="center" width="80% " src="https://files.readme.io/292dc4faa5e032b5ecc2b493e0f525daec1f89c434fb66e73ad6b8153cf0e652-ga4-1-yespo.webp" />

There is no need to additional configure Yespo integration with Google Analytics.

## Channel Analysis

GA4 displays statistics by channels on

* Users,
* Sessions,
* Interactions,
* Events,
* Revenue (Revenue data is available if you configured <a rel="nofollow" href="https://support.google.com/analytics/answer/10089681?hl=en" target="_blank">sending e-commerce events</a> from your website or mobile app in analytics).

To check the collection and mapping of data to a channel, go to the *Acquisition → Traffic acquisition → Session primary channel group* section. The email channel report is included in analytics by default; setting up the display of other media channels is described below.

<Image align="center" width="80% " src="https://files.readme.io/421dbdf59d9854457aefbdd6a3de3c8005b5ddb27af05bbef3fc3af64f11ddf2-ga4-2.webp" />

Specify the date range for analysis in one of the following ways:

* click on the first and last date of the required period in the calendar;
* write them in the appropriate column in the date range;
* select the default period.

<Image align="center" width="80% " src="https://files.readme.io/9b9dfa7a79aba156a516c984f3514713ebc8c9293eb8f809bfaa45f66573f182-ga4-3.webp" />

You can set two date ranges to compare the dynamics of results: check the *Compare* checkbox and specify the date ranges.

<Image align="center" width="80% " src="https://files.readme.io/9930c4e4d9b655673bba1e98c3fad28352783eb463d8ec79caddb1ca4bec9a72-ga4-4.webp" />

> 🚧 Important
>
> Of the channels available in Yespo, analytics by default only displays Email, SMS, and Mobile Push Notifications, where web push indicators are also collected. Other channels are included in the *Unassigned* or *(other)* statistics. Set up channel distribution manually.

<Image align="center" width="80% " src="https://files.readme.io/b9079d1f7d5444b987bb5dc1f3b6ae3bd93c0651525361050fa1f5e91210a36a-ga4-5.webp" />

 Add UTMs to the list with utm\_medium parameters to match them with the corresponding channel. 

1. At the bottom left, open the *Administrator* tab.
2. Go to *Property settings → Data display → Channel groups*.
3. Click *Create new channel group* (creating a new group is required to set the procedure for checking traffic data for compliance with the channel).

<Image align="center" width="80% " src="https://files.readme.io/31075dad69c94df99046a5d3d2cb353eb7a650d53947566ef3b4ca0dd8379ce7-ga4-6.webp" />

Provide channel information:

1. Enter its name.
2. Configure the rule by which you will transmit the channel in the medium parameter.

<Image align="center" width="80% " src="https://files.readme.io/0e57350ca2222739ce2cde11ae60bf0c32bd4991f766071170220dabf2b8e9c6-ga4-7.webp" />

When creating a channel group, pay attention to the order in which they are placed. If the rule definition is repeated in channels, Google will record the traffic of the first channel in the list. For example, traffic is read as a referral, and if the *Referral* channel is higher in order than *Social*, place the channel definition you added above the others (the *Reorder* button). The data in the reports will be updated after 24 hours.

<Image align="center" width="80% " src="https://files.readme.io/bc3039460e3df146d2c8bbb70a66bac644e3ca3dc57a63ac675dc6d4e1b6d7bc-ga4-8.webp" />

## Trigger and Promo Campaign Analysis 

Yespo transfers Yespo-promo and Yespo-trigger UTM tags, by which you can distribute the reports' data.

Open the *Acquisition → Traffic acquisition* tab, select *Session source / medium* from the list, and click *Add filter*.

<Image align="center" width="80% " src="https://files.readme.io/beb15239eb31287c9f198fec233e4bf4f0c3a31f883df86520c2892492f0a5e5-ga4-9.webp" />

Create a filter:

1. Dimension: *Session source / medium*.
2. Match type: *exactly matches*.
3. Value: *Yespo-promo / channel name* and *Yespo-trigger / channel name*.

<Image align="center" width="80% " src="https://files.readme.io/ee8238ad8983c066f9d65f8932b95ebaea3ddeb8042e782d467489e1aab425b7-ga4-10-yespo.webp" />

Apply filters and view the report.

<Image align="center" width="80% " src="https://files.readme.io/a3edd44df58ace0845f57c0b016f46b0bc8b0d6380cedcdaf4a733da50ea6ca6-ga4-11-yespo.webp" />

## Single Campaigns Analysis

To evaluate the effectiveness of individual promo or trigger campaigns, apply the *Yespo-promo / channel name* or *Yespo-trigger / channel name* filters on the *Acquisition → Traffic acquisition → Session source / medium* tab. Select *Session campaign* in the *Session source / medium* column.

<Image align="center" width="80% " src="https://files.readme.io/914928e2fe7f11010195af72cfeed3816a0d58fc4f990a11f9282c1e8ef4a853-ga4-12-yespo.webp" />

## Messages’ Series Analysis

You can evaluate the effectiveness of a messages’ series by their [tags](https://docs.yespo.io/docs/how-add-tags) in Yespo. All messages must have the same tags in the same number and order. Otherwise, GA will consider the messages to be from different campaigns.

<Image align="center" width="80% " src="https://files.readme.io/26d7c6d165c0fad5cca65d46a0405d78aa59f3e4a6d59b1b2ce92726f778188f-ga4-13.webp" />

To evaluate the effectiveness of a series of messages, select the *Session keyword* parameter from the *Custom* list in the *Session source / medium* column on the *Acquisition → Traffic acquisition* tab.

<Image align="center" width="80% " src="https://files.readme.io/536cd70b4831625c3d696abbfc348f711473822af17cdb62b7c9006146bc0989-ga4-18.webp" />

If your GA4 account does not have a *Session keyword* parameter, set it up.

1. Go to *Property settings → Data display → Custom definitions* in the admin panel.
2. Create a custom definition on the *Custom dimensions* tab: 

* Dimension name — *Session keyword*,
* Description – *utm\_term value*,
* Scope — *Event*,
* User property/parameter – *term*.

<Image align="center" width="80% " src="https://files.readme.io/52a93a7c7d463099d5fab0d2976e6b25dab91398427d593e41cf2e1308d6adb3-ga4-15.webp" />

## Contact Tracking by ID

You can track contacts’ purchasing activity using their [external IDs](https://docs.yespo.io/docs/external-id-creating-and-updating-users).

<Image align="center" width="80% " src="https://files.readme.io/67437754131535212bfa5ed3a870eccee8d3e059e137127a4719110d0d3e865a-ga4-16.webp" />

Pass the *$contactId* in the *Contact ID* parameter (Yespo settings → *Links*). It is included in the *utm\_content* field by default.

<Image align="center" width="80% " src="https://files.readme.io/24cb56a3f9162a289e6c7b05692a4f8c98af05a6321749f30a50cd4bb78abca1-ga4-17-yespo.webp" />

To evaluate the contact's purchasing activity, select the *Session content* parameter from the *Custom* list in the *Session source / medium* column on the *Acquisition → Traffic acquisition* tab.

![Session content](https://files.readme.io/d3b58656c1431a4dfc6de4430bf2088046ff3b853cae6005189fd1444bc476ff-ga4-14.webp "Session content")\
 If your GA4 account does not have the \_Session content p\_arameter, set it up.

1. Go to *Property settings → Data display → Custom definitions* in the admin panel.
2. Create a custom definition on the *Custom dimensions* tab: 

* Dimension name — *Session content*,
* Description – *utm\_content value*,
* Scope — *Event*,
* User property/parameter – *content*.

<Image align="center" width="80% " src="https://files.readme.io/0e3eb17f306fa77d448fd48ba70465c33b8d8469a05ffb8520d3fcf42b73e59f-ga4-19.webp" />

> 🚧 Important
>
> Client ID (cid) and User ID (uid) are used in GA and must be integrated into the site's tracking code. They help analyze user behavior, providing crucial information for overall analysis. Contact your developer or analyst for detailed information about these identifiers and their settings.

## Explorations

Explorations are custom reports for tracking more detailed statistics on customer behavior.

To create an exploration, go to the *Studies* tab and create a new exploration or select a template from the gallery.

<Image align="center" width="80% " src="https://files.readme.io/9880c1dd2902ecf4d9586a40a2310efca56372567d70ec1620cc4b8f1c3c84ee-ga4-20.webp" />

You can use up to 10 tabs in one report with methods that optimally visualize data by different indicators.

<Image align="center" width="80% " src="https://files.readme.io/03a6df9d632a2f870e354adae39ec5c6a1c1aed6dab809cddea139fbf93bc24f-ga4-21.webp" />

<a rel="nofollow" href="https://support.google.com/analytics/answer/7579450?hl=en#zippy=%2Cin-this-article" target="_blank">More on GA explorations ></a>
