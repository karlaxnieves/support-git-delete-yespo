---
title: Streaming Events from Firebase
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Streaming Events From Firebase | Yespo Guide
  description: >-
    Set up your app user behavior tracking to know all important to your
    business data.
  robots: index
next:
  description: ''
---
Tracking the customers’ activity in your mobile application gives you insights into their journey and experience, thus helping you understand their behavior and see their preferences and expectations.

Using the mobile tracking feature, you can collect this data and use it for segmentation, targeting, and personal recommendations (similar to [web tracking](https://docs.yespo.io/docs/how-set-web-tracking-your-website) for a site).

> 📘 Important
> 
> To activate the mobile app tracking, subscribe to the activate the [PROFESSIONAL plan](https://yespo.io/segmentation-price).

The following diagram shows the overall flow of the data transfer from your mobile application to Yespo’s CDP.

## How to Set Up Tracking

To track users' activity in your mobile app, set up the streaming of relevant data to a BigQuery table, from where it will be automatically sent to our CDP.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/888e1511ba9cfcfc171742ea7c55200a4cd4b38b1efcbddde584724b3c142d04-Data-transfer-scheme.webp",
        "Data transfer scheme",
        "Data transfer scheme"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The data about the customer events come to Firebase. Then they are passed to a BigQuery table and exported to Yespo CDP.

To set up the mobile tracking: 

1. Configure the customer data transfer from a mobile app.
2. Connect Google BigQuery with your Yespo account.

## Configuring data transfer from a mobile app 

To configure the customer data transfer from a mobile app to a BigQuery table, use the following instructions:

- <a rel="nofollow" href="https://support.google.com/firebase/answer/6318765?hl=en&ref_topic=7029512#zippy=%2Cin-this-article" target="_blank">Link BigQuery to Firebase;</a>
- <a rel="nofollow" href="https://support.google.com/firebase/answer/7029846?hl=en&ref_topic=7029512" target="_blank">Data format and schema for Google Analytics 4 resources and Google Analytics for Firebase data exported to BigQuery.</a>

The method of event storing depends on the operating system and programming language used. See <a rel="nofollow" href="https://firebase.google.com/docs/reference" target="_blank">Firebase API Reference</a> for instructions.

The following table describes the required event types:

| Event             | Description                                                                                |
| :---------------- | :----------------------------------------------------------------------------------------- |
| SCREEN_VIEW       | Page view                                                                                  |
| VIEW_ITEM         | Item page view                                                                             |
| VIEW_ITEM_LIST    | View of the items list (from a recommendations block)                                      |
| VIEW_CART         | Cart page view                                                                             |
| ADD_TO_CART       | Items adding to the cart                                                                   |
| REMOVE_FROM_CART  | Items removed from the cart                                                                |
| PURCHASE          | Item purchased                                                                             |
| Firebase_campaign | Used for tracking the link transitions from trigger campaigns. The tracking uses UTM tags. |

For more details, see <a rel="nofollow" href="http://firebase.google.com/docs/analytics/userid" target="_blank">\[GA4] Recommended events</a> for the full list of events recommended by GA.

> ❗️ Important
> 
> - Set the user\_id for all registered users using <a rel="nofollow" href="http://firebase.google.com/docs/analytics/userid" target="_blank">this instruction</a>.
> - Update the contact information (user\_id) in the account using the _[Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1)_ API method.

After setting up the data transfer to BigQuery, [set up the BigQuery connector](https://docs.yespo.io/docs/google-bigquery-integration) in your account.

## Connecting Google BigQuery with Yespo

Connect Google BigQuery with your eSputnik account for sending the data automatically to our CDP.

> 📘 Note
> 
> You need to subscribe to the [PROFESSIONAL plan](https://yespo.io/segmentation-price) to send the data for the mobile app tracking and activate the menu _Mobile Tracking_.

1. In your Yespo account, go to _Account > Settings_ and select _Mobile Tracking_ from the menu on the left-hand side.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/16395d53b5052655b7f48b975e9ac2c45ca61e5bee1fcbd89fd0375da4f72cd7-streaming-events-from-firebase-001.webp",
        "Mobile Tracking Menu",
        "Mobile Tracking Menu"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the _Connect Google BigQuery_ button.

> 📘 Note
> 
> When creating a new connector, the first step warns you that the utm\_term UTM tag will be changed. Go to _Profile → Settings → Links_ and make sure that this change does not hamper tracking your campaigns. See [How to set up UTM tags](https://docs.yespo.io/docs/how-add-tags) for more details.

2. Click _Next_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2f2d1d329263390a613b208c62646a1bc092a6c82165992e17545d6b69233f4-UTM_tag_change_en.webp",
        "UTM Tag Change Step",
        "UTM Tag Change Step"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click _Upload_ to upload the BigQuery key file.  
   **NOTE**: To learn how to create and download a key file, see [Integration with Google BigQuery](https://docs.yespo.io/docs/google-bigquery-integration).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/03349dc0cbb2b3dfd1be35845f617e764992987347193d244f5c444a37803b73-upload_key_file_1.webp",
        "",
        "Upload"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Validate connection_. If a proper connection is established, the “Connection succeeded” message appears for a short while.
4. Click _Next_.
5. Click the _down arrow_ icon and select a BigQuery dataset from the list, then click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f90bc282626ab8ec5ec3a6b20fea87956c056b34d8ca3014c0b4379d4d8ab3e-select_dataset.webp",
        "",
        "Select a BigQuery dataset"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The Google BigQuery connection appears on the Mobile Tracking page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4cd697b89231c63680ac4a2f60a53a351b2d3f3fad59fa9e40a4dd2710be30e7-created_connection.webp",
        "",
        "BigQuery connection"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Now the mobile tracking is configured in your Yespo account.

## Contacts Matching

When a user is not authorized in your app, but has a mobile token, getting a _contactId_ from the account will help you. You can do this using the [public API](https://docs.yespo.io/reference/getting-started-with-your-api) method. Pass the resulting _contactId_ to the <a rel="nofollow" href="https://firebase.google.com/docs/reference/android/com/google/firebase/analytics/FirebaseAnalytics.UserProperty" target="_blank">user.properties</a>.

The contact ID is its unique identifier, with the help of which the system identifies a person when they [enter the application from different channels](https://docs.yespo.io/docs/how-create-deep-links-and-universal-links), browsers, and devices.

This way, you can collect all the data about the interaction of users with your application and send them omnichannel campaigns.

The system will add all available contact identifiers to the unique contact ID, such as mobile and web tokens, phone number, and email address.