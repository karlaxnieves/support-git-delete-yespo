---
title: Viber Campaign Report
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Viber Campaign Report | Yespo Guide
  description: >-
    Viber messenger provides big text volumes, images, and active links,
    favorably distinguishing Viber messages from SMS.  Learn about the features
    of  Viber campaign reports.
  robots: index
next:
  description: ''
---
Viber campaign reports provide information on campaign results, including key metrics, contact statistics, and revenue.

Let’s consider the features of bulk reports. You can also check out

- [additional options for trigger reports](https://docs.yespo.io/docs/triggered-campaign-report),
- [general reports’ capabilities](https://docs.yespo.io/docs/campaigns-analytics).

Conventionally, the report consists of 4 parts:

1. General information.
2. Performance indicators.
3. Revenue.
4. Detailed statistics.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f6daead79808a7235dc321aaa081094a96cd2fc9cfacf45d66c2b990d92d47f-reports-1.webp",
        "Viber report",
        "Viber report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 1. General Information

The first part of the report contains the following data:

1. The message’s and segment’s names.
2. Campaign start/finish date and time.
3. Message ID. To copy an ID, click on the copy icon next to it. Click on the link icon to edit a message.
4. Message name.
5. TTL (time to live)  – the period after which the message will not be shown if it has not been delivered by that time.
6. The segment of contacts to whom the message was sent, segment ID, and the date of the segment’s last editing.
7. [Tags](https://docs.yespo.io/docs/how-add-tags) to find and filter messages.
8. Email of the user who started the campaign.
9. Message preview on different operating systems.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c23f34db799aea126175851a7e7e81cb52745431f6a41acfa1dbcf3ae295b672-reports-2.webp",
        "General information",
        "General information"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 2. Performance Indicators

Yespo automatically tracks the performance of Viber campaigns, including opens, clicks, errors, etc. Statistics are presented in a table.

> 📘 Note
> 
> Send a request to [support@yespo.io](mailto:support@yespo.io) to enable the _Clicked_ category

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60985df74568028efce556e8831a6afa2984d8c3505fea356105fde4f0add866-reports-3.webp",
        "Performance indicator",
        "Performance indicator"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Green marks on the scale show the conditional indicators of a successful campaign, and red marks are negative indicators' conditional norm.

Clicking on any report item opens a window for viewing the contacts list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86781f928f8fbd7f9ed6d0352e970ce47abeab35795fc9cc549dc3e3c43dd656-reports-4.webp",
        null,
        "Contacts from reports"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Above the general statistics are the following tabs:

- **Extra campaigns.** Allows you to configure the automatic sending of messages based on the activity or inactivity of users regarding this campaign. More — [at the link](https://docs.yespo.io/docs/how-send-extra-campaign).
- **Export.** Allows you to export contacts from the report to a CSV file, to an existing or a new list. Export is available for all campaign metrics: sent, delivered, inaccessible contacts when sending, over plan limit, [annoyance level](https://docs.yespo.io/docs/management-campaign-frequency) exceeded, etc.
- **More.** Allows you to delete the report.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4b536a02281947900582a62c1ca32b46f573707e3bb9436dc26c4dcde5334cf-reports-5.webp",
        "Actions with reports",
        "Actions with reports"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 3. Revenue

If you set up integration with a CRM system that records order data, you can evaluate the financial results of the campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0d446f2e18e1ffbf935f89371e69c40f702ef88ec4b8ceca7349668399c1b915-reports-6.webp",
        "Revenue",
        "Revenue"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More on the settings for displaying revenue >](https://docs.yespo.io/docs/how-set-revenue-campaign)

## 4. Detailed Statistics

The section may include information about the effectiveness of the language versions of the message (if they were used) and revenue (if this option is activated in the account).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbfbba3fbc09b9f1f664fbe233d14de6ecfb245d0258eafbce075e53c62e38c3-reports-7.webp",
        "Detailed statistics",
        "Detailed statistics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Multilanguage (optional)

Multilanguage is an automation tool that enables sending messages in different languages within one campaign. It helps avoid long message lists and voluminous unsystematic reports for every message.  
Reports on multilingual campaigns are described [in a special article](https://docs.yespo.io/docs/report-on-multilingual-campaigns).

### Adding Details

You can filter tabs’ data using the _Add details_ option.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb90f35e5e942daceb68ec733d77be72c401fca67cf839cb475918939048f4d4-reports-8.webp",
        "Add details",
        "Add details"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]