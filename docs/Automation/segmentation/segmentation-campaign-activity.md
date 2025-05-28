---
title: Segmentation by Events in Messages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Segmentation by Events in Messages | Yespo Guide
  description: >-
    The document outlines how to create dynamic segments based on message
    response events to enhance targeting in future campaigns, with segmentation
    features available in paid plans and various parameters like event count,
    time, and message type for precise audience targeting.
  robots: index
next:
  description: ''
---
Build segments based on the response to your messages to further target future campaigns.

Specify a period, and the system will analyze the activity of all contacts who participated in your campaigns at that time. A combination of activity parameters will help build an accurate target segment that changes in real time.

[Learn more about working with dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment)

> 📘 Note
> 
> Segmentation by events in messages is included in paid plans. To enable it, please contact us at [sales@yespo.io](mailto:sales@yespo.io).

## Events in Messages

The following events are available for segmentation in messages:

- Send;
- Delivery;
- Delivery error;
- Open;
- Click;
- Unsubscribe;
- Unavailable when being sent;
- Spam.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/782f9b2109b63014b40f24aa8f10beb56c9f08ee0ca6b60e0806ce8db2582a5d-message-event.webp",
        null,
        "Events in messages"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Event parameters

Most events can be segmented according to the following parameters:

- **Event count:** for example, you can create a segment of contacts that made more than three openings during the week.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bd90c96d20f19ea21694a62003a2d1375ad3b558c4e6709e0dcaa861c161f21-event_count.webp",
        null,
        "Event count"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **Event time:** the range during which certain events occurred. For example, opening from 8:00 to 10:00 every day during the week.
- **[Tag](https://docs.yespo.io/docs/how-add-tags):** filter messages based on the tags you have assigned them.
- **Message type:** Email, SMS, Web Push, Mobile Push, Viber, App Inbox, In-App (message type is not specified for the _Unsubscribe_ and _Spam_ events, since they can only occur in emails; for In-Apps, only the _Open_, _Click_ and _Delivery error_ events are available; for Telegram, only the _Send_, _Delivery_, _Click_ and _Delivery error_ events are available).
- **Campaign type:** bulk or triggered.
- **Workflow:** filter messages by the workflows through which they were launched.
- **Message:** selection of one or more messages of any media type.
- **Message language:** filter by language for multilingual campaigns.
- **Subscription category:** filter by contacts’ subscription categories.
- **Bulk campaign:** selection by one or more bulk campaigns of any media type.
- **Triggered campaign:** selection by one or more triggered campaigns of any media type.
- **Strategy segment:** filter by strategies in which segments participate.
- **Contact’s domain:** filter by contacts’ domains.

Some events have their unique parameters:

- **Delivery:** delivery rate.
- **Open:** open rate; time between send and read; AMP or HTML email version.
- **Click:** CTOR; CTR;  AMP or HTML email version; URL link.
- **Unsubscribe:** reason.

## Examples of Segmentation by Campaign Activity

- **Segmentation of VIP contacts who haven't received important information**

To make sure all paying customers have received the campaign with important information, segment users by delivery error, filter paying ones based on CRM data, and transfer the profile list to the call center. The same can be done for a segment of users who received the campaign but didn’t open it.

- **Segmentation of engaged subscribers to increase the campaign frequency**

Segment users who've opened more than 50% of your campaigns in the last month. Since they're likely interested in your offers, you can increase the send volume. In the workflow, add a condition under which only engaged users will receive campaigns with increased frequency. As soon as the user's campaign activity falls below the specified open rate, they get automatically excluded from the segment and start receiving campaigns at a regular frequency.