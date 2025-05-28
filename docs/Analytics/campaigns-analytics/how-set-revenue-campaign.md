---
title: Revenue from Campaigns
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Revenue from Campaigns | Yespo Guide
  description: >-
    Set up revenue from campaigns to see what profit your messages generate. The
    statistics on the profit is displayed both in the general report list and in
    the report on each particular campaign.
  robots: index
next:
  description: ''
---
Enable the visualization of revenue in reports to see how much income each channel generates.

## Enabling Revenue Display

1. The first step is to set up order data transfer to the system via API resources _[Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1)_ and _[Generate event](https://docs.yespo.io/reference/registerevent_1)_. You can see order information in _Automation → Orders_ if integration is active.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d800d2c29e5398ce9dd11f0fdb057626eec53065b51fded43cab3f7953a5b9ac-revenue-from-campaigns-001.webp",
        null,
        "Order list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Go to your profile _Settings → Revenue from campaigns_ and enable the _Show sales in report_ option.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10c77fb7afedf371067018715a952286e35c18c91b1517b385ee38bcd9aa8f41-revenue-from-campaigns-201.webp",
        null,
        "Profile Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Activate the _Associate with last received message_ switcher and select parameters for each channel:

- The event that connects the channel to sale (_Opened, Sent, Clicked, Delivered_);
- The time between the event and sale (hours, days, weeks).

Different parameters can be set for each channel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4fea912926cfb835ca9594695c35aae5ded9f7ebee9d0f3c333d823a645a255d-revenue-from-campaigns-202.webp",
        null,
        "Channel settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Specify the order currency to calculate the income. Select a currency code from the list and click the _Save_ button. Revenue visualization will include only orders in the specified currency.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08343bf066c5da24c10d3be58406b074998c78741e4ea20cd9b0ff21bef71a3c-revenue-from-campaigns-004.webp",
        null,
        "Revenue currency"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Add [message tags](https://docs.yespo.io/docs/how-add-tags) to exclude specific messages from the revenue calculation (technical notifications, password recovery, delivery confirmation, etc.) Data on them will be available in the report but won’t be included in the revenue calculation. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eee4647b0720e70f43561a14691efe728fb7a10df73133dcd39f80f75f8fada9-revenue-from-campaigns-005.webp",
        null,
        "Adding tags"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Period Revenue

You can see total revenue for a specific period.

1. Go to _Automation → Orders_ and select period to view revenue.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5ebda150ea252d4b670412f5c64bd0797c2f95fb7a7d3d7051dd8dcfa4da109a-revenue-from-campaigns-006.webp",
        null,
        "Selecting period"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. At the top of the list of orders, next to the _Total_ status, you will see revenue amount - the sum of _Initialized_, _In progress_, and _Delivered_ statuses.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a82e877633e9a5250b2f5857fb33abd4b9e56119f09d00b9ced226dae6c2853-revenue-from-campaigns-007.webp",
        null,
        "Revenue"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Hover over the question icon next to the _Total_ status. Detailed information on each status will display.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1002a67873af65c371d2601fdfa59f3410ed3141b3822ab434e4f73caedf3404-revenue-from-campaigns-008.webp",
        null,
        "Detailed information"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Additionally, you can see the canceled orders amount. This amount is not included in total revenue.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9197d276e280b3e2e09bbc1451424ec5034260c81efabc10071034af2c43922a-revenue-from-campaigns-009.webp",
        null,
        "Canceled orders amount"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Revenue from Campaigns in Reports

1. Go to _Campaigns → Reports_. Select the channel, for example, _Email_.

Data on campaign revenue over the specified period will be given on top of the general list:

- Campaigns;
- Purchases;
- Average check;
- Revenue from campaigns.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/edf1f1835e99c5bcf0e7d928bdda6d4d65d993427e3b4fd22e807b5f9bb7f194-revenue-from-campaigns-010.webp",
        null,
        "General revenue results"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the $ icon to see details on each campaign:

- Purchases;
- Average check;
- Revenue from campaigns;
- Purchase-to-open rate;
- Purchase-to-click rate.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8cfb33f753a5af1bb673176c7d5ae30ae283a498ad87055a33e9a818b35753a9-revenue-from-campaigns-011.webp",
        null,
        "Revenue of each campaign"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click on the number of purchases the campaign generated to open a window with a list of contacts who made purchases and other order information.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d0ce83046172ddd125d9460102f388edb1af07792921e38e216315d3348d3fa9-revenue-from-campaigns-012.webp",
        null,
        "\"Purchases"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. To export all customers to a separate segment or file, click the _Export_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d9ab8612f42fe6fe3a1b9f3f13ed4f34eb28fe5e3a43375c21860898cbce932-purchases2.webp",
        null,
        "Export"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Exporting data from the _Purchases_ tab to a CSV file is available only to users [in the role with the appropriate permission](https://docs.yespo.io/docs/user-management) (Admin, Marketer).

Click the preview button to view the contact card.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f39a5318af2d2a4fee67c02bfb5b23350d95887472ac26ac15d9dbb200e5c4e-purchases3.webp",
        null,
        "Preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To copy or export a report with general purchase data, click _Copy_ or _Export_, respectively (with $ active).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bc40bc3d16f4603fd0ba95a6969cf4ea3171d12ccd5802ba0a136e29489209b-revenue-from-campaigns-013.webp",
        null,
        "Copy report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Revenue from the campaign is also displayed inside its report:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c2557d91bdad0f7c0b472b54322b456aaeeb2928fb52e8f4c6825efb200dc580-image2.webp",
        "Revenue statistics inside report",
        "Revenue statistics inside report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Next to the numbers, you can see the sale formula. For example, for the campaign on the screen, a sale is defined as a transition from the message to the website with purchase completion within 24 hours after the transition.

## Notes

- Set up order data transfer to the system via API resources _Add orders_ and _Generate event_.
- The _Reports_ tab displays only orders with the _Delivered_ status.
- All sales transferred to the system are connected to channels. You connect channels to sales in _Settings_ based on events (sent, delivered, opened, clicked) and time period.
- A sale is always associated with the last interaction with the channel.
- Refund data isn’t included in the general statistics.