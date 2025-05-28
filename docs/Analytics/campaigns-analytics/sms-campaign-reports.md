---
title: SMS Campaign Report
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: SMS Campaign Report | Yespo Guide
  description: >-
    SMS campaign reports provide information about the results of the messaging
    campaign, including general information, contacts statistics, and revenue
    from the campaign.
  robots: index
next:
  description: ''
---
SMS reports provide information about the results of your campaigns, including key metrics, contact statistics, and revenue.

Let’s consider the features of bulk reports. You can also check out

* [additional options for trigger reports](https://docs.yespo.io/docs/triggered-campaign-report);
* [general reports’ capabilities](https://docs.yespo.io/docs/campaigns-analytics).

Conventionally, the report consists of 4 parts:

1. General information.
2. Performance indicators.
3. Revenue.
4. Detailed statistics.

<Image align="center" width="80% " src="https://files.readme.io/202354e890ac9b468407f58e7eb27ad2629a973d768ff19335ba165e85e8e287-reports-1.webp" />

## 1. General Information

The first part of the report contains the following data:

* The message’s and segment’s names.
* Campaign start/finish date and time.
* Email of the user who started the campaign.
* Message preview: shows how the message is displayed on iOS and Android.
* Message ID. To copy an ID, click on the copy icon next to it. Click on the link icon to edit a message.
* Name.
* The number of message parts.
* The segment of contacts to whom the message was sent, segment ID, and the date of the segment’s last editing.
* [Tags](https://docs.yespo.io/docs/how-add-tags) to find and filter messages.

<Image align="center" width="80% " src="https://files.readme.io/f30d94e18c6e7641c469a7636c78c3e77f6950f28b283a8adee9a3305634911d-reports-2.webp" />

## 2. Performance Indicators

Yespo automatically tracks the performance of SMS campaigns, including clicks, errors, delivery etc. Statistics are presented in a table.

> 📘 Note
>
> Request to [support@yespo.io](mailto:support@yespo.io) to enable the *Clicked* category.

<Image align="center" width="80% " src="https://files.readme.io/d9a53153a387a939b4198a686538ba2399b212baf75e15e87c5036e391e22cb3-reports-3.webp" />

Green marks on the scale show the conditional indicators of a successful campaign, and red marks are negative indicators' conditional norm.

Clicking on any report item opens a window for viewing the contacts list.

<Image align="center" width="80% " src="https://files.readme.io/807a906717b6e214715947ff618717acafe0f303bfb7505d293c79bf984dbbdd-reports-4.webp" />

Above the general statistics are the following tabs:

* **Extra campaigns.** Allows you to configure the automatic sending of messages based on the activity or inactivity of users regarding this campaign. More — [at the link](https://docs.yespo.io/docs/how-send-extra-campaign).
* **Export.** Allows you to export contacts from the report to a CSV file, to an existing or a new list. Export is available for all campaign metrics: sent, delivered, inaccessible contacts when sending, over plan limit, [annoyance level](https://docs.yespo.io/docs/management-campaign-frequency) exceeded, etc.
* **More.** Allows you to delete the report.

<Image align="center" width="80% " src="https://files.readme.io/dfeb742f21f93274aa21e110a88143056ad59aa664393517f690b23d2c4886cb-reports-5.webp" />

## 3. Revenue

If you set up integration with a CRM system that records order data, you can evaluate the financial results of the campaign.

<Image align="center" width="80% " src="https://files.readme.io/c61fcc4293bcc87b0a923df4aef581846b0a0ae60c5812892f614b1aaf245339-reports-6.webp" />

[More on the settings for displaying revenue >](https://docs.yespo.io/docs/how-set-revenue-campaign)

## 4. Detailed Statistics

The section may include information about the effectiveness of the language versions of the message (if they were used) and revenue (if this option is activated in the account).

<Image align="center" width="80% " src="https://files.readme.io/ae467d4c05ac44b0b870ec35c08ff86cbc0de57f9ac4876cf618eec6d406ad09-reports-7.webp" />

### Multilanguage (optional)

Multilanguage is an automation tool that enables sending messages in different languages within one campaign. It helps avoid long message lists and voluminous unsystematic reports for every message.

Reports on multilingual campaigns are described [in a special article](https://docs.yespo.io/docs/report-on-multilingual-campaigns).

### Adding Details

You can filter tabs’ data using the *Add details* option.

<Image align="center" width="80% " src="https://files.readme.io/f418b389e10a076c06688995f827d0b0daff0a1a327555a3894107b45bfac84d-reports-8.webp" />
