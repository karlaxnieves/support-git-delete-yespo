---
title: How to Migrate to Our Platform from Other Services
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Migrate to our Platform from Other Services | Yespo Guide
  description: >-
    Learn how to migrate to our CDP from other platforms: template import,
    contact base import, data import, transfer of contact activity.
  robots: index
next:
  description: ''
---
Every year, marketers use more and more tools to develop and implement different communication strategies. New channels, a growing contact list and an increasing database require automation to be managed properly. Our system is an all-in-one platform that offers various solutions for marketing automation of all channels you use for customer communication: Email, SMS, Mob Push, Web Push, Viber.

The service allows:

- Create emails in a drag-and-drop editor;
- Segment your contact list based on shopping behavior and product preferences;
- Create automated workflows with triggered message series;
- Run A/B testing;
- Get reports on important metrics such as open rate, deliverability, unsubscribe rate, spam reports, etc.;
- Conduct [RFM analysis](https://yespo.io/blog/practical-rfm-analysis-increase-repeat-sales) and more.

If you want to migrate to the platform from another ESP or CRM, make sure you transfer all data the right way. In this article, you’ll learn how to migrate to our system and retain important information about subscribers and previous campaigns.

## Data Transfer

You can transfer data to our platform in two ways: manual import and automated import through API.

> 📘 Note
> 
> To transfer token bases for web push and mobile push notifications, please contact our support.

### Manual Contact Import

Typically, a contact base consists of the following contact data: name, email address, phone number, and date of birth. There also can be additional information depending on the data you collect.

In the platform, a unique contact ID can be an email address and/or phone number.

To be imported manually, your contact base must be arranged in one of the following formats:

- `.xls` – a table in Excel 97/2000/XP;
- `.xlsx` – a table in Excel 2007 and above;
- `.csv` – a text file that opens in Notepad and Excel;
- `.txt` – a text file of the Notepad app (separated by a semicolon or comma).

Note that `.txt` or `.csv` enables a faster transfer.

You can upload to the system a file up to 300 MB at a time. If your base is larger, split it into multiple files or delete unnecessary columns.

Read more on [contact import](https://docs.yespo.io/docs/uploading-file-with-user-profile-data).

### Segment Import

Contact base segmentation is an important part of modern email marketing strategies. You can keep your segments when transferring the base in two ways:

- Transfer ready segments;
- Transfer the base and build segments after the import.

### Contact Base Transfer through API

We recommend using the _[Search contacts](https://docs.yespo.io/reference/searchcontacts-1)_ method to import contacts through API.

You can use it to synchronize your contact base with your CRM system. This way, your base will be regularly updated with new contacts. Each new contact transferred to the system with this method is considered to be confirmed by default. This means they confirmed their addresses through Double Opt-In in the old system and can be sent to.

### Contact Collection

To continue collecting contacts, сonnect the ready subscription form from a third-party service that has an integration with our platform or any service through Zapier. Next, set up a data transfer from a subscription form and a [Double Opt-In](https://docs.yespo.io/docs/subscription-form-configuration) workflow with the corresponding emails.

### Workflow Transfer

After you set up the data transfer, you need to automate communication. In our platform, there are 5 ready workflows you can use. You only need to create emails for them and configure triggers and launch conditions. Or you can create new workflows from scratch.

Read more on [how to create a workflow](https://docs.yespo.io/docs/workflow-management).

### Additional Data Transfer

You can transfer to the system the following data on contact statuses:

- Active;
- Inactive;
- Reported spam;
- Bounce status (errors in email delivery such as invalid address or domain, bad spelling, etc.).

You can transfer through API contacts with the status Unsubscribed. Or you can include these into a separate segment and our support will unsubscribe them in the system.

Optional but recommended for transfer data include:

- Contact creation date;
- Last open date;
- Last click date.

If needed, you can also transfer the following data:

- Delivery date;
- Open and click dates;
- Clicked links;
- Categories of clicked products (in product recommendations).

This information is transferred to the platform as additional tables through [BigQuery](https://docs.yespo.io/docs/google-bigquery-integration) or [PostgreSQL](https://docs.yespo.io/docs/how-connect-postgresql-external-data-source).

## Contact Activity Transfer

You can transfer contact activity data using different methods depending on your pricing plan.

### Basic Functionality

The basic functionality allows you to transfer unlimited additional fields in a one-dimensional table. They can include:

- Event date;
- Opens;
- Clicks;
- Spam reports;
- Unsubscribes, and more.

To do this, you need to export data from the platform you’re migrating from, put it into a table, add additional fields and attributes, import to our system, and map the corresponding fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eabe1e31a1835b5c33553bee47def68e62ad3e66598ac9440ee8121707f5efcf-migrate-to-our-platform-001.webp",
        "Table for contact activity transfer under basic functionality",
        "Table for contact activity transfer"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The advantage of this method is that the table enables to keep the status of contact activity and save the date of the last interaction.

The disadvantage is that it’s impossible to consider all touchpoints, identify the categories of links that generated clicks, set date ranges, and summarize the number of responses.

### Enterprise

When subscribed to the Enterprise plan, you can transfer the following additional data:

- All open dates;
- Clicks by links and categories;
- Transactions from campaigns;
- any other statuses and actions of users.

In addition, you can connect external data sources and additional tables with data on each subscriber.

To do this, export data from ESP in multiple tables (separate list of open dates, list of feedback dates, list of unsubscribe dates, etc.), put them into tables, add additional fields and attributes, import them to the external database of BigQuery or PostgreSQL, and set up connectors between identifiers of subscribers, campaign and content.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2111fcdd73da3c86e67a05265376e7794ca3cae3eb2c8a72026f30dce731db8-migrate-to-our-platform-002.webp",
        "Table for contact activity transfer under Enterprise functionality",
        "Table under basic functionality"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The advantage of this method is that you can do advanced segmentation and build segments based on all events of the subscriber's life cycle.

The disadvantage is that this method is more complex. You may need help from specialists so that you can set up import and connectors between identifiers.

> 📘 Important
> 
> If you can’t find an export option in the interface of your platform, contact their support.

If there are any other difficulties with migration to our CDP, please contact our support team.

## Template Import

You can import templates to our platform in several ways:

- Transfer of HTML code. If the template is created as HTML code and not in a drag-n-drop editor, it can be downloaded as a file and uploaded to the system.
- Automatic transfer of <a rel="nofollow" href="https://stripo.email/" target="\_blank"> Stripo</a> templates. Open the template in Stripo, select _Export_ in the top menu. In _Export to ESP,_ click on our CDP.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22ce1bf8da931a775bb5e61e8dd1d07bc1072adef5c8d7db8a4abdb17f7ba82d-How-to-import-templates.webp",
        "How to import templates from Stripo",
        "How to import templates from Stripo"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Enter your account details and allow access. In our system, the imported template will appear in Messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b0a8ee972b1befa0c6b62acc1d2629967c4a15bee4ea974c10f6b19d5a7bd59c-migrate-to-our-platform-003.webp",
        "Imported template in our platform",
        "Imported template in our platform"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Transfer from a drag-n-drop editor. Automatic transfer of templates created in drag-n-drop builders isn’t available. You need to build a similar template in our email editor from scratch. You can use one of more than 1000+ ready templates or apply for a free template that’s available for new users.

> 📘 Note
> 
> You can’t transfer templates of push notifications, SMS and Viber messages. You need to create these messages anew.