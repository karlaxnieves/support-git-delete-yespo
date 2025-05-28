---
title: Email Campaign Report
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Email Campaign Report | Yespo Guide
  description: >-
    Learn how to analyze and improve your marketing campaigns using the data
    collected by the CDP for the campaigns you send.
  robots: index
next:
  description: ''
---
After launching the campaign, you can analyze and improve your marketing efforts using the data collected by the Yespo system from the moment you send the email.

Email campaign reports provide information about the campaign results, including a detailed click map, table of clicks, contact statistics, and response time.

Advanced analytics appears in case of activation of the corresponding functionality and includes:

* revenue,
* indicators of AMP and multilingual versions of the email,
* statistics by strategy segments,
* the results of experiments with the topic.

Let’s consider the features of bulk reports. You can also check out

* [additional options for trigger reports](https://docs.yespo.io/docs/triggered-campaign-report),
* [general reports’ capabilities](https://docs.yespo.io/docs/campaigns-analytics).

Conventionally, the report consists of 4 parts:

* General information.
* Performance indicators.
* Revenue.
* Detailed statistics.

<Image align="center" width="80% " src="https://files.readme.io/8137736e03f4c6db83258175637c80d399343d3c451a40ad4828b86fb4b0f47d-report-1-1.webp" />

## 1. General Information

The first part of the report contains the following data:

1. The message’s and segment’s names.
2. Start and finish date and time. 
3. Email of the user who started the campaign.
4. Message ID. To copy an ID, click on the copy icon next to it. Click on the link icon to edit a message.
5. Subject line. If you test several subjects, they will be displayed as a list.
6. Sender name.
7. The segment of contacts to whom the email was sent.
8. [Tags](https://docs.yespo.io/docs/how-add-tags) for search and filtering of emails.
9. Segment ID.
10. The date of the segment’s last editing.
11. Email preview.

<Image align="center" width="80% " src="https://files.readme.io/3d330872638579ac5d10bb2e1dcf561169ba549114dbab306197accaab1e8921-reports-2.webp" />

## 2. Performance Indicators

Yespo automatically tracks the effectiveness of email campaigns, including opens, clicks, unsubscribes, etc. All statistics are collected in the form of a table.

<Image align="center" width="80% " src="https://files.readme.io/04d2cee9d6b5a4515988f67c0158cfd9a21b4ef625f39c0f610c0c1800cc6a91-reports-3.webp" />

Green marks on the scale show the conditional indicators of a successful campaign, and red marks are negative indicators' conditional norm.

Clicking on any report item opens a window for viewing the contacts list.

<Image align="center" width="80% " src="https://files.readme.io/1eca2e5dbddfbb77a64a481cb569a758987082a55b260c2fbc3979810a3b4ac9-reports-4.webp" />

Above the general statistics are the following tabs:

* **Extra campaigns.** Allows you to configure the automatic sending of messages based on the activity or inactivity of users regarding this campaign. More — [at the link](https://docs.yespo.io/docs/how-send-extra-campaign).
* **Export.** Allows you to export contacts from the report to a CSV file, to an existing or a new list. Export is available for all campaign metrics: sent, delivered, inaccessible contacts when sending, over plan limit, [annoyance level](https://docs.yespo.io/docs/management-campaign-frequency) exceeded, etc.
* **More.** Allows you to delete the report.

<Image align="center" width="80% " src="https://files.readme.io/1e11a0602ea1200c6efeb47f6d860d28ae2bee23e75bdfaee1f87acac0710905-reports-5.webp" />

## 3. Revenue

If you set up integration with a CRM system that records order data, you can evaluate the financial results of the campaign.

<Image align="center" width="80% " src="https://files.readme.io/bd6ecdfe374ed64a003959b4b2af296dbc7a95a2cf9296513b757ced400cebe9-reports-6.webp" />

[Learn more about revenue display settings >](https://docs.yespo.io/docs/how-set-revenue-campaign)

## 4. Detailed Statistics

The section includes detailed statistics on opens and clicks, revenue, response time, segments, and experiments with the subject line, if any.

Let's consider each tab separately.

### 4.1. Opens and Clicks

The tab has three subsections: *Click map*, *Table of clicks*, and *AMP*.

#### Click Map

Click map displays the percentage of clicks on the links in the email.

<Image align="center" width="80% " src="https://files.readme.io/67a6cc81683431f3f252f27abbb28f5ccc11de5905fe8d78a1caf1fbf127e5c2-reports-7.webp" />

Click map reports can show the statistics sorted out by contacts or by click rate:

* **Statistics by contacts** show the percentage of users who clicked on any of the active links in the email. You would see this in the report if one user clicks on one link several times. The total percentage of clicks can exceed 100%.
* **Statistics by clicks** show the percentage of clicks on each link. The total number of clicks is set to 100%, and the report shows the rate of clicks each link receives.

If the email has the AMP version, you can view the click map separately for the AMP and HTML versions.

<Image align="center" width="80% " src="https://files.readme.io/a9f2c78cf16a58bb211c9780a6314f74e35bfa6167a7f2b79b9d9543acdf95d0-reports-8.webp" />

#### Table of Clicks

The *Table of clicks* tab shows the number of clicks on each link in the email.

<Image align="center" width="80% " src="https://files.readme.io/f7e9e1a801e8e106d4145a760c14960aec70c50241403a177ee83b8619ee7403-reports-9.webp" />

You can upload contacts that click on a specific link.

The discrepancy between the numbers in the *Clicks* and *Contacts* columns indicates that some users clicked on the same link several times.

The *Group by URL* switch combines the same links in the email under different elements.

#### AMP

By default, this section displays the contact database structure by AMP-supporting domains.

<Image align="center" width="80% " src="https://files.readme.io/1b4bb8ab3694279a5fa55af8804391c3323066c3d3cca19975b823f3a28195be-reports-10.webp" />

* Before sending AMP emails, you need to become a trusted sender. [Read the instructions on how to apply](https://yespo.io/blog/how-apply-sending-amp-powered-emails-within-gmail).
* See the *[AMP Campaign Report](https://docs.yespo.io/docs/amp-campaign-reports)* article if you already have campaigns with AMP content.

### 4.2. Response Time

The graph shows the activity statistics in the email for 24 hours or 7 days.

<Image align="center" width="80% " src="https://files.readme.io/7763c116ed61d0d9424b4e83ed0edbd54a50660592fa3423180160cd635d80dd-reports-22.webp" />

You can see when your campaigns receive a response per day or week. If you regularly send emails during the day, your open rate will be highest in the first 2 hours.

### 4.3. Segments

The segments section could contain such tabs:

* Domains
* Platforms and OS
* Device languages
* Segments
* Multilanguage (optional)
* Strategy (optional)

<Image align="center" width="80% " src="https://files.readme.io/50a9174ff44e3725d694cbcf88dd9428531de257dfba4d1a8bde3282e95bfcff-reports-12.webp" />

#### Domains

The report provides statistics on the emails by email domains. It shows the deliverability by individual email domains and allows you to evaluate indirectly the probability of your campaign getting into spam.

If, for some mailers, the opened percentage is significantly different from other domains, and this percentage is much lower than before, we recommend checking the domain's reputation. Also, pay attention to errors. A high rate of errors affects the probability of getting into spam.

<Image align="center" width="80% " src="https://files.readme.io/a7faba2fe41aed8ca2fb4cfedea861c1cfd59c2d27562e92a762edafa15ab080-reports-13.webp" />

#### Platforms and OS

In the *Platforms and OS* tab, you can view statistics on opened and clicked messages and click-to-open rates by users' platforms and OS.

<Image align="center" width="80% " src="https://files.readme.io/b205d6c2ded229be15e60cbb80e93c9c7f97c47d650fe6aa8373b3926efdeaf6-reports-14.webp" />

The *Other* category includes statistics on eReader, TV, Game Console, etc.

#### Device Languages

Statistics on campaign recipients' device languages:

<Image align="center" width="80% " src="https://files.readme.io/80373b67800db8f63b471734c7aea7d48ed4fcd076b7f4fd67d150d615c99493-reports-15.webp" />

#### Segments

In the *Segments → Segments* tab, you can choose specific segments to view their statistics.

<Image align="center" width="80% " src="https://files.readme.io/56a5ab23cec4edcbf6ceac97823e5da7c1bd51916aa37fbef738e6326a12ff9f-reports-16.webp" />

The first line will display data about the entire campaign, and the lines with segments will show their indicators.

You can sort emails by the following parameters:

* by sent
* by errors
* by opened

<Image align="center" width="80% " src="https://files.readme.io/1247ff8d79f4e6623acc06ce12983587f06f00492314d999393c4b45bdb2f791-reports-17.webp" />

### Advanced Analytics

#### Revenue

You can see the revenue by individual segments, domains, or language versions of the message using filters (the *Add detail* button) on the *Revenue* tab.

<Image align="center" width="80% " src="https://files.readme.io/e60cae2b2542d91beb46bf7207271bd443789fceb28e72512588d399905558f1-reports-18.webp" />

#### Multilanguage

Multilanguage is an automation tool that enables sending messages in different languages within one campaign. It helps avoid long message lists and voluminous unsystematic reports for every message.

Reports on multilingual campaigns are described [in a special article](https://docs.yespo.io/docs/report-on-multilingual-campaigns).

#### Strategy

If you have applied [a frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy) to your campaign, you can see all the data and statistics for each segment from the strategy.

<Image align="center" width="80% " src="https://files.readme.io/a3bdc38cea3bb8f2b4e115d087092f1b286e5e8d68c6462b9e20569effa27ddc-reports-19.webp" />

#### Experiments

The tab will appear if you have [tested subjects](https://docs.yespo.io/docs/how-test-email-subject-lines) for the campaign. Here you can evaluate the results of the A/B test for each version of the email.

<Image align="center" width="80% " src="https://files.readme.io/439c9185ddcfe4b4bf50ea2699b542b9b0a91b152001a88cf9a76c32a59d6f55-reports-20.webp" />

#### Adding Details

In the upper right corner in the Add details dropdown, you can select the details of the campaign for any tab by parameters:

<Image align="center" width="80% " src="https://files.readme.io/461f5505a778a561e473d3ead8e9b2ff107ac6f6e3424bc68b74d0526daeccfe-reports-21.webp" />

* *Domains* — statistics by domains.
* *Multilanguage* — if you send [multilingual messages](https://docs.yespo.io/docs/creating-multilingual-messages), statistics will be displayed separately for each language version of the message.
* *Groups* — initially, statistics for all contacts are displayed, but you can select individual segments and view statistics only for them by clicking on the filter.

<Image align="center" width="80% " src="https://files.readme.io/db9c51266b8782192b42e9002e349640a909b32c9e1e1719176040e19bf28d5a-image5.gif" />

If the filter data repeats the section, it will not be displayed.
