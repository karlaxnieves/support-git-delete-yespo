---
title: Contacts Analytics
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Contacts Analytics | Yespo Guide
  description: >-
    Contacts Analytics overview. Learn more about contact lists and different
    types of analysis available in the Yespo system.
  robots: index
next:
  description: ''
---
Contacts analytics contains detailed information about the number of contacts and their details since they were created in the Yespo database.

To view the statistics, go to _Contacts → Analytics_, and select one of the sections from the left-hand menu:

- Channel overview
- Activity overview
- Segment overview
- RFM analysis
- Cohort analysis

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff585a04906d0c9d7c7deaad0862298823ff64bcf1a5696c3d445e8b333b011e-cntcts-analytics-001.webp",
        "",
        "Contacts analytics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Let's consider each section in more detail.

## Channel Overview

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b7f1e1bead955cb5220d5d0fc323c8c063ced11f14107cd89da073e8e6053add-cntcts-analytics-002.webp",
        "",
        "Chart marketing channels"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The chart shows the distribution of contacts by channels, with the number of contacts in each. If a channel is missing from the database, its field will not be displayed or included in the calculations

> 📘 Note
> 
> The overview shows statistics for the last elapsed day; recalculation ends before 02:00 UTC

## Activity Overview

The section is divided into tabs by channels, where the following data is displayed for each channel:

- charts of the contact base by activity;
- contact growth overview;
- subscriber engagement overview.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5bc1a778f78b372c5b1c8dc8e884805d1c55e03b109157f094569169d11dd0b-cntcts-analytics-003-02.webp",
        "",
        "Activity overview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Charts of the Contact Base by Activity

The pie chart displays the contact database structure based on the activity of different subscriber categories. All elements of the chart are interactive and color-coded: clicking on any segment reveals its structure in the selected channel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2e0aa852b28d0ec8fe64db83344e6f36b54e341df8b852c65fec3613819dd90-cntcts-analytics-004.gif",
        "",
        "Activity diagram"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Email

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0258da230c139c9674473fb1a9d2869565145a6980a7475a77eef0dd1629607d-cntcts-analytics-005-02.webp",
        "",
        "Email activity diagram"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Statistics categories:

**Active subscribers**. Contacts included in the campaign in the last 3 months:

- opened;
- opened and clicked — opened and clicked the link from the email.

**Inactive subscribers**. Contacts who received the campaign but were not sufficiently engaged:

- opened over 3 months ago;
- never opened;
- soft-bounced — an email exists, but message delivery is impossible. For example, the mailbox is full, temporarily blocked, etc. If the status changes (for example, the email address becomes inactive after a year), such contact will fall to the Black List category;
- unconfirmed — contacts who indicated their email in the subscription form but did not confirm it. The reasons may differ — an error in the address, filling out the form by a bot, etc.

**Lost subscribers**. Contacts that previously participated in campaigns but are now unavailable for the following reasons:

- unsubscribed;
- reported spam;
- blacklisted — you or another user sent messages to this address, and the mail service answered that the mail does not exist. Such an address is blacklisted and no longer participates in the campaign. The blacklist is end-to-end, that is, you upload an email address to the system, and it may already be on the blacklist.

**Never sent**. Contacts you have never sent campaigns to. For example, a contact was previously blacklisted or was accidentally removed from a campaign segment. Here you can see the following statistics:

- unsubscribed;
- reported spam;
- blacklisted;
- unconfirmed;
- available — addresses available for the campaign.

#### Web Push, Mobile Push, App Inbox, In-App, Telegram

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0933c3ad3c7ff924e87113f68a8b9dd9c1f1d5c64eca1210516d3f69daf8e364-cntcts-analytics-006-02.webp",
        "",
        "Web Push, Mobile Push, App Inbox and In-App activity diagram"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Let's examine the chart using Web Push as an example, as the statistics for the mentioned channels are built based on the same categories of contacts:

**Active subscribers**. Contacts included in the campaign in the last 3 months:

- opened (_Web Push,_ _App inbox_ and _In-App_ channels);
- opened and clicked.

**Inactive subscribers**. Contacts who get the campaign but were not sufficiently engaged:

- opened over 3 months ago;
- never opened.

**Never sent**. Contacts you have never sent campaigns to.

#### Exporting contacts with different activity statuses to the segments 

Let's consider the export of contacts using the _Email_ channel as an example.

1. Go to the chart and select contacts from the desired category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d37274d47d3b3e6cc024ba8cd932cf711d664de63c1745a9f8f3019858664f89-cntcts-analytics-007.webp",
        "",
        "Exporting contacts"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the _Create a segment_ button in pop-up window. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8cc36d58926e29b15e7164bf33e51580fa0961e0648370a5068d10d55c698103-cntcts-analytics-008.webp",
        "",
        "Create a segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The segment will appear in the _Contacts → Segments_ section in the overall list of groups. The contact data is current as of the moment of export to the segment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c6b421a69be37a3df997fc740fbc468a1b55a0594b7132d849b10f5d6b443cdb-cntcts-analytics-009.webp",
        "",
        "New segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Contact Growth Overview

In this section, you can track changes in your contact database over a selected period using bar charts.

To view the statistics, click on the channel tab and select the time range.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e35ef5c31c3d911909d6d63d06796ca134c28bee76d0ea46aa4f8c6bd69c546a-analytics-001-02.webp",
        "",
        "Contacts growth overview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


On the chart, you can see:

- The total number of contacts growth by channel.
- Contact categories are divided by their source of entry into the system or reasons for deactivation, with the number of contacts in each category specified.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e3acbaffeed0f634ddbf53de5bad1e273885d54dfc4ae88de6720e19ac6cbbf7-analytics-002-02.webp",
        "",
        "Contact categories"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Categories for _Web Push,_ _Mobile Push,_ _In-App, Telegram_ channels:

- Subscribers
- Unsubscribed

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e98396ef00bbf5662d7f1db8307237f806a4a8c43d92087e4974d84285b9f235-analytics-005-02.webp",
        "",
        "Web Push, Mobile Push and In-App contact growth overview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To exclude a category from the chart, click on its name to deactivate it. Active values can be copied to the clipboard.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/80dd28d9bf91cb6f04e2441397c1acff6e1f3bc3b04557da4c8212bc09051b00-analytics-003-02.webp",
        "",
        "Exclude a category from the chart"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Contacts added from events are created using the [Generate event v2](https://docs.yespo.io/reference/registerevent_1) method, provided that [segmentation is enabled for the event](https://docs.yespo.io/docs/how-to-use-event-segmentation#using-events-for-segmentation)

The growth dynamics for Mobile Push and In-App displays statistics separately for _Android_ and _iOS_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/87366a9e3954bcf7d4d524841092d0ede5734f9dee690a2d4a62a96bacb467a4-analytics-006-02.webp",
        "",
        "Android and iOS statistics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Subscriber Engagement Overview

This section displays subscribers' reactions to campaigns as linear graphs, showing points with values when hovering over the graph.

Statistic time for all channels — 3, 6, 9, and 12 months. Also, you can set the time interval for a specific period.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42895254b494b36073b6028464ac3eda3b148ac7ec5f677530aefe5cae635069-subscriber-engagement-overview-01.gif",
        "",
        "Subscriber engagement overview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The top graph allows you to assess the level of interaction with the audience and contains the following categories:

- Sent, opened, clicked — for _Email, Web Push_, and _In-App_ channels
- Sent, clicked — for _Mobile Push_ and _Telegram_ channels
- Opened, clicked — for _App Inbox_ channel

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d043b0bd73152dff9af3b22189910bcdb552001b92fa312dacf37383272ddd3-subscriber-engagement-overview-02.webp",
        "",
        "Statistic categories: sent, opened, clicked"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The bottom graph indicates issues or deficiencies that require attention and possibly adjustments in the communication strategy, containing the following categories:

- Unsubscribed, reported spam, error — for the _Email_ channel
- Error — for all other channels

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/baf6cb45f7bb995a8f8af5cc0fd033585725cf653c00f04cd0405704b49ff429-subscriber-engagement-overview-03.webp",
        "",
        "Statistic categories: unsubscribed, reported spam, error"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Segment Overview

The table shows growth dynamics in specific segments.

> 📘 Note
> 
> You can add any segment to collect statistics. The system starts collecting the segment’s statistics for this chart from the day you add it.

[More on segment overview >](https://docs.yespo.io/docs/segment-tracking)

## RFM Analysis

The analysis displays contact activity from two weeks to the entire period.

Campaigns and sales statistics divided into tabs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d15c873a8d2e7ab5cf926d24f4b5a7d1351c8a9e63c4a2d227c2104ec080955-cntcts-analytics-010.webp",
        "",
        "Campaigns and Sales tabs"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Actions with the segments

RFM analysis table is divided into segments. You can do the following actions:

- export to segment;
- delete;
- add an event when the contact moves between segments.

#### Export to segment/delete contacts

1. Click one or more cells. The selected segments will be marked with a checkmark.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4076d55dfbc0e49060d62347e3daf4b0488442e971a69e8a7f30d71992be3dfc-cntcts-analytics-011.webp",
        "",
        "Selected segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the _Export to segment_ or _Delete contacts_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1a4b4d0f537c4689c938a7596aadd866e6830626a1d45e307f53b9473b1a477-cntcts-analytics-012.webp",
        "",
        "Buttons"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Add event

1. Click the _Add event_ button

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7170620183dbcdac68f06655bbc235d07cca1767d30f77987b7a685ebfb77f40-cntcts-analytics-013.webp",
        "",
        "Adding an event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the segments and event type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/64771ad32fa180476f810d418db804a018363e3bc3a69a580383f7dd4e73b8a8-cntcts-analytics-014.webp",
        "",
        "Segments and event type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click the _Save_ button.

 The cell, transition from which triggers an event, is indicated by an eye icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/308f39b2579e988da81a45bb8a71b61709c657fc5897187c113ba2d0a0a91fef-contacts_analytics_023.webp",
        "",
        "Cell indicating"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More details about RFM analysis >](https://docs.yespo.io/docs/rfm-analysis)

## Cohort Analysis

The cohort analysis table shows contact data for different periods depending on contact activity. By default, the table uses _Customer retention rate_ cohort type. Cohort sizes can be defined by month and in different periods.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8b37e3f61ed05d818e7642129a551869015e6239566db6a13f208acf254bc7fd-cntcts-analytics-015.webp",
        "",
        "Cohort Analysis"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More details about Cohort Analysis >](https://docs.yespo.io/docs/cohort-analysis-how-track-segment-activity)