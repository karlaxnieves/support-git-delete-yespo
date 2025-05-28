---
title: RFM Analysis
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: RFM Analysis | Yespo Guide
  description: >-
    Learn how RFM Analysis helps segment customers based on Recency, Frequency,
    and Monetary value. Unlock actionable insights to improve marketing
    strategies, boost customer retention, and maximize revenue.
  robots: index
next:
  description: ''
---
RFM (_Recency, Frequency, Monetary_) analysis helps to get a visual representation of the quality and engagement of your contact base. Yespo provides two 2 RFM graphs: based on data on email engagement and data on sales.

Actions that you can perform with RFM segments:

- exporting to list;
- deleting from the account;
- creating an event at moving between segments that can trigger a workflow.

## Interpretation of the Graph Data

RFM analysis is a component of contact analytics in Yespo.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/615fec7acbe0208c765bda90fa3f1f97ddd754747966e8441ba85249ddbce877-image11.webp",
        "",
        "Where to find RFM analysis"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Data on email engagement and sales are divided into _Campaigns_ and _Sales_ tabs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d0480a04411b2d43bf83f42aaead0b097ca6ecbc92fa48f23a8ad420e200a80-RFM_2.webp",
        "",
        "Campaigns & Sales"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the _Campaigns_ tab, segments are formed according to the number of opens and the last open time.

In the _Sales_ tab, segments are formed according to the number of sales and the amount of time (set up transferring sales data [via API](https://docs.yespo.io/reference/ordersbulkinsert-1) to Yespo to see its RFM analysis).

Calculations are made along the R and F axes:

- R is the time of the last opening/sale.

By default, the parameters are set from two weeks to >1 year.

- F is the number of opens/sales.

In the table with sales analysis, the bottom line (0-1) contains contacts who have not made purchases (x>=0 and x\<1), the second (1-2) includes contacts who have made one purchase (x>=1 and x \<2), etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9875c18003f008db52a8aa28bec90fa987396fe3723cd764a763396ff3c6f7b-sales-rfm.webp",
        "",
        "Sales analysis"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can order a custom display of the sales graph:
> 
> - increase the period and number of sales on the graph,
> - add or remove period columns and _Number of sales_ fields,
> - set display at any time intervals.
> 
> Leave a custom display request at [support@yespo.io](mailto:support@yespo.io).

The segments are colored depending on the activity of the contacts:

- Gray — no reads/sales.
- Red — segments at risk of loss. The more saturated the color, the more passive the contacts in the segment.
- Green — loyal customers. The more saturated the color, the higher the loyalty of the segment.

The top row contains contacts that showed maximum activity. Contacts that can be considered lost are at the bottom left.

## Data Filtering and Actions with Segments

The filter by contact activity in campaigns has the following options:

- All contacts
- Sent within 30 days
- Sent within 90 days
- Ever sent

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e5640a60b111218bc2b6a129baaff33e8915c39249cd3248b82629f17ce311e-image15.webp",
        "",
        "Filter by contact activity"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The filter by segment allows you to see RFM analysis of any contact list in your account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c343cd8aaf173ed9e67e2818c4ad88b32f9263d25ae592d16dd39fa3a799efb0-image2.webp",
        "",
        "Filter by segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click on any cell to remove contacts from it or export them to a static segment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/15a2e29bbf18bd39888aa20b0f855610c3993e808032fe8cdc6cb9b6214fd4bd-image14.webp",
        "",
        "Delete/Export"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can select or create an event triggered when contacts move from one cell to another (for example, from active to inactive) by clicking the _Add event_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b35781bf27fa54cfa4eca24adc90d7f8151d5f58639158125b0ba8814b6975cb-image3.webp",
        "",
        "Add event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The cell, the transition from which triggers the event, is marked with an eye icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1327bcc489d7021eb1ad50c13a12f05d40b6435459569952ce1d55d936aeac7-RFM_7.webp",
        "",
        "Tracking segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Setting Up Trigger Campaigns at Moving Between RFM Segments

You can configure automatic workflows for each RFM segment.

For example, you want to send an email with a special offer to customers who are moving into the risk zone — from the segment of those who bought 3 months ago to those who made purchases 6 months ago.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3056d46b4d15a444d86f6149b036d17fe5aeae537d58e978917320cef07c62f9-image6.webp",
        "",
        "Moving between segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The settings algorithm will be as follows:

1\. Add an event to the transition between segments as described above.

2\. Create a workflow ([Building and editing workflows](https://docs.yespo.io/docs/workflow-management)).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cd166f2532372dfd029c97d7c2e45e7d7cbfae76c5cc8aecb2c4f007d529a553-rfm-analysis-01.webp",
        "",
        "Workflow example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. After saving the workflow, set the event you created as [the start condition](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd28fb4f7d6f7f80dda7dced9a3f554177f785b939e903f03818a4be78eb4a45-image10.webp",
        "",
        "Start configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Every time a contact moves between the segments you specified, they will receive messages from the workflow. It can be an offer with a unique promo code, a special discount, a survey about the quality of service, etc.

You can use such workflows not only to reactivate customers but also to accrue bonuses. In this case, pay attention to the transitions in the green cells. Attach workflows to them to notify the user about the number of bonuses in their account and how much they need to move to a new level.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50246c5d8e58facc22b489aa9d3ac573f5c7046eb47a2db4c850026f742c16b0-image1.webp",
        "",
        "Transitions in the green cells"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Another workflow example is to notify the manager about the contact transition from the green to the red segment. The workflow will look like this:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62d0f13ceb313113045f4f4ca26b1c7bfd99cddce599687db677112700f7561c-rfm-analysis-02.webp",
        "",
        "Workflow example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the parameters of the _Email_ block, specify the message and email address of the manager who should receive it:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b9169189d4aaaec14702bce0c6509f4f60db76b4d4bca65535d0133c63254ba1-rfm-analysis-03.webp",
        "",
        "Email block parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Get contact_ block will substitute data instead of variables in the email template:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/451d49d20af3e718d842519b238b34b99ff19ac3fe214fa00cdb1ceb40944ddb-image7.webp",
        "",
        "Variables"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use the [velocity](https://docs.yespo.io/docs/introduction-to-velocity) expression _$!data.get('X')_, where X is the field with the value to pass to the manager. You can see the names of the variables in the _Merge tags_ section of the message editor:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a4e5000d625850bc785addea8cbefdb306709757072bb344717302e913cb77d9-image12.webp",
        "",
        "Merge tags"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


All additional fields that are in your account are collected here. Copy only the name without special symbols. E. g., convert %FIRSTNAME|% to $!data.get('FIRSTNAME').

See more information about setting up workflows [at the link](https://docs.yespo.io/docs/workflow-examples).