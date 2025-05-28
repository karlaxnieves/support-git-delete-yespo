---
title: Setting Bulk Campaign Frequency Strategy
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Bulk Campaign Frequency Strategy | Yespo Guide
  description: >-
    A guide on setting bulk email frequency by tags to reduce churn and boost
    interest. Includes steps for strategy setup, planning, reporting, and
    marketer-led campaign timing.
  robots: index
next:
  description: ''
---
An email frequency strategy determines which days of the month or week bulk campaigns with specific tags can be sent to specific segments of contacts. This allows you to reduce base churn and increase the interest of your target audience in your campaigns.

## Setting Up a Strategy

For example, let's take a case with three types of messages:

- **Promo** – to attract leads on Mondays, Wednesdays, and Fridays, and for regular customers – on Mondays;
- **Personal offers** – only for VIP customers;
- **Service** – for all customers.

Let's move on to creating a strategy.

1. Go to _Campaigns → Frequency strategy_ and click _New strategy_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/563a7b84fb496636bc67a8a9b8eb28a88d6325b4c0aa477179aa2f6b330642f6-strategy-1.webp",
        "New strategy",
        "New strategy"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the name of the strategy.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2cc9449602799b7d580fe873d98852169dccae6b77fce3e08130ee743da7b34-strategy-2.webp",
        "Enter the name",
        "Enter the name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Add segment_ and select the segments you want to set up a strategy for.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/917b67c2312e49b17e4f007c4bf02ea9768f8db6bbc589eab172537f6e130df5-strategy-3.webp",
        "Add segment",
        "Add segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> A special icon in the general list of segments indicates segments participating in the strategy. Hover your cursor over it to see what strategies the segment participates in.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc68cf578cf800252e33024e1a7eb13b0e669d343ebc99c03c5df1f98de1e098-strategy-4.webp",
        "Strategy icon",
        "Strategy icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Add [tags](https://docs.yespo.io/docs/how-add-tags) for messages used in the strategy. When scheduling a campaign, the system will impose sending restrictions based on the message tag.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba7b3cc33ed204e199f493c5449ac31e87d12381c87b048c2f47bf69d2eb764d-strategy-5.webp",
        "Add tag",
        "Add tag"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Set the message frequency at the intersections of segments and tags. To do this, move the cursor over the cell and click the left mouse button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b69e8907693310b2e03c5fd3bc37c44b69fc80724e0758293faf8ff9536946d8-strategy-6.webp",
        "Set the message frequency",
        "Set the message frequency"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Select one of the suggested frequency options and click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0b2f8a7bf38e1bfe0233c809403dd6fc295bfb4150f12aa27c05a70bbb0e413d-strategy-7.webp",
        "Select the suggested frequency",
        "Select the suggested frequency"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Similarly, set the frequency for the remaining cells. If you do not set the settings for a specific cell, it will default to a dash, equivalent to the _Don't send option_.

You can move rows with segments and columns with tags by dragging them to the desired location.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/146cda31ea65e6012629f93241595fa1f942b51b37489c6d2c621d592ab92af8-drag-and-drop.gif",
        "Dragging rows and columns",
        "Dragging rows and columns"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Not included in segments_ row contains all contacts in the campaign that are not included in the segments you selected in the strategy. They also require setting the frequency of sending for selected tags. If you do not choose a frequency for contacts not included in the segments, they will not receive messages using the strategy.

7. After completing the strategy settings, click the _Save_ button.

Before sending a message, Yespo checks segments from top to bottom and tags from left to right. If the system finds a contact in the first segment, it applies the rules of that row to that contact. That is, for example, if there is a contact in both the first and second segments, and the strategy for the first segment does not imply sending today, but for the second, it does, today the system will not allow sending a message to this contact using this strategy.

## Planning Bulk Campaign Based on the Strategy

1. Select or create a message with one of the tags used in the strategy (the _Messages → Messages_ section) and click _Create campaign_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22ed50a51a5918b09b970437bde5f5b0865e37cfa4d593cbedb719ae47d1294f-strategy-9.webp",
        "Create campaign",
        "Create campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Choose segments or contacts and click the _Go to campaign_ button (at this step the strategy is not yet applied).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3266c747e8ad5b07099988431e42f20aa95220614ea3884660f1c8a02b84ab70-strategy-10.webp",
        "Go to campaign",
        "Go to campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click the _Schedule_ button at the bottom of the scheduling page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/177a1d38fa0e3f60ec0e0c6bfb7972ea57b157a8b74262d0e1d86212f36f0bf2-strategy-11.webp",
        "Schedule",
        "Schedule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Set the campaign's frequency, date, and time and click the _Next_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e442d510997912bc985982e8e118279de9391f29fbf91537a03d5154d0dbeeb-strategy-12.webp",
        "Set the frequency",
        "Set the frequency"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 🚧 Important
> 
> The strategy does not automate the launch of campaigns or control the timing of message sending — this remains the responsibility of marketers. The strategy only determines which contacts to deliver bulk campaigns with specific tags on specific days of the month or week.

5. Choose a strategy.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4483c8c08ecc7e90295bd0e501637ebce3858b705239fac1282160f11a912c71-strategy-13.webp",
        "Choose a strategy",
        "Choose a strategy"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Contacts will be recalculated, excluding those that do not meet the conditions of the selected strategy. Click the _Schedule_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/98f2f44925ee16504e78796fa42b81c67ceb6f2fdb2a90715b7f51660c57e8b1-strategy-14.webp",
        "Schedule",
        "Schedule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Changing the launch date of the campaign can change the list of contacts receiving it under the strategy settings

## Reports on Campaigns Using the Strategy

In the report on campaigns using a strategy, you can see statistics for all segments under the applied strategy and separately for each segment to which you send the email under the strategy.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0d90b870195b02c41110ea217a14d7ced0570e1bf2172b9a98565d8c1dfd912-strategy-15.webp",
        "Strategy report",
        "Strategy report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]