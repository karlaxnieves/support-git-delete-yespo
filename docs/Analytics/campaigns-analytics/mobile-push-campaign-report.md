---
title: Mobile Push Campaign Report
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Mobile Push Campaign Report | Yespo Guide
  description: >-
    The document outlines the structure and features of mobile push campaign
    reports, detailing sections on general information, performance indicators,
    revenue, and detailed statistics, with options for exporting data and
    integrating CRM systems for financial analysis.
  robots: index
next:
  description: ''
---
Mobile Push campaign reports provide information about the campaign results, including key metrics and operating systems of the message recipients.

Let’s consider the features of bulk reports. You can also check out

- [additional options for trigger reports](https://docs.yespo.io/docs/triggered-campaign-report);
- [general reports’ capabilities](https://docs.yespo.io/docs/campaigns-analytics).

The interfaces of bulk and triggered reports are similar. They have four parts:

- General information.
- Performance indicators.
- Revenue.
- Detailed statistics.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37ee69ce41a8df27ce2ae7ab0a768338eb1c7a12a547b2e057602788ff466c7e-reports-1.webp",
        "Campaign report",
        "Campaign report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 1. General Information

The first part of the report contains the following data:

- The message’s and segment’s names.
- Campaign start/finish date and time.
- Email of the user who started the campaign.
- Message ID. To copy an ID, click on the copy icon next to it. Click on the link icon to edit a message.
- Message preview across operating systems.
- Message name.
- The segment of contacts to whom the message was sent.
- Segment ID.
- Date of segment’s last editing
- [Tags](https://docs.yespo.io/docs/how-add-tags) for search and filtering of messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92a28e90c47268c710943c9cc86605633368977fd0c794fdf56a6b9e0e21fb5b-reports-2.webp",
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

Yespo automatically tracks push campaign performance metrics, including clicks, errors, and more. All statistics are collected in the form of a table.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/54d5e2bfbd114bffd8b0ae4e118b766fbd367d448b6db61314b7f1895765b91d-reports-3.webp",
        "Performance indicators",
        "Performance indicators"
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
        "https://files.readme.io/d9f20c90db382a35c6b3c5f3b98b9cc33286900c95de4172553110e84b11b1f7-reports-4.webp",
        "Contacts from report",
        "Contacts from report"
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
        "https://files.readme.io/4a3f531e5827c0c5919e45dc9b4fd72cd6d12e1fd53212c02f9774a3a28ed9af-reports-5.webp",
        "Actions with report",
        "Actions with report"
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
        "https://files.readme.io/f7189da87672aeae12472a9ff041c11a8d0e0abe7c25a5d2d9c841307a3b6e27-reports-6.webp",
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

The section includes information about the operating systems of contacts and, optionally, data on the effectiveness of the language versions of the message (if they were used) and revenue (if this option is activated in the account).

### OS

See how users of different operating systems reacted to the campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/321f71d0dd2d5db7b7660fc3abb768b8018dea85c87a76378a1d62f0cc9d6ef9-reports-7.webp",
        "OS",
        "OS"
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
        "https://files.readme.io/166ad9faa3fbbb8f8dd49e7686856f512edc7dd323bdbe7af99459966055520b-reports-8.webp",
        "Add details",
        "Add details"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]