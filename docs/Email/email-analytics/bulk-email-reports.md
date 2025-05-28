---
title: Bulk Email Reports
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The report consists of 4 parts.

## 1. General Information

The first part of the report provides the following information:

* Name of the email.
* Start and Finish: when the campaign was launched and when the email was sent to all the contacts.
* [Sender name](https://docs.reteno.com/docs/adding-a-sender-name).
* Started by user: displays the email of the user who has started the campaign.
* Segments of contacts to whom the email was sent.
* Subject line. If you test several subjects, they will be displayed as a list.
* Tags for quick search and filtering of messages.
* [Annoyance level ](https://docs.reteno.com/docs/annoyance-level)(optional). 
* Email preview.

<Image width="80%" src="https://files.readme.io/6eb8224-image21.png" />

If you send a campaign to a large list or with a limited speed, the *Start/Pause* and *Stop* buttons will be available, so you can temporarily suspend, completely stop or restart the campaign.

<Image width="80%" src="https://files.readme.io/e0579f3-image1.png" />

The campaign is automatically paused if:

* Not sufficient funds.
* The email uses unique promo codes, and they are out of stock.\
  After adding funds or renewing the list of promotional codes, you can unpause the campaign here.

## 2. Email Statistics

In this part of the report, you can see detailed statistics on the campaign.

<Image width="80%" src="https://files.readme.io/d1100f4-image20.png" />

Extra campaigns function allows you to engage users based on their response to this message. At the moment of launch, the system will build a segment with contacts who performed the specified action and send them the extra message you have scheduled.

<Image width="80%" src="https://files.readme.io/1266d7d-image17.png" />

By clicking on the *Export* button, you can export the segments by:

1. Activity: Sent, Delivered, Opened etc.
2. Inaccessible contacts at the time of sending: Blacklisted, Is Not confirmed, In Unsubscribed etc.

> 📘 Note
>
> Contacts to whom a message was not sent when checking for a subscription category, fall into the *In Unsubscribed* category

3. Errors, where you can export contacts:

* To the new list;
* To the existing list;
* Send as a CSV file to the email address used to log in to Reteno.

<Image width="80%" src="https://files.readme.io/7252156-image5.png" />

By clicking the *More* button, you can delete the report, check lock status, and copy technical campaign information and message ID to the clipboard.

<Image width="80%" src="https://files.readme.io/8b073c3-9c0740d7-19e8-4f5d-baa0-b7d062c4f07e.png" />

## 3. Revenue

If you set up integration with a CRM system that records order data, you can evaluate the financial results of the campaign.

<Image width="80%" src="https://files.readme.io/a32b8be-image19.png" />

## 4. Campaign Performance

## 4.1. Opens and clicks

In the section Opens and clicks you can see:

* **Click map** — displays the percentage of clicks on the links in the email.
* **Table of clicks** — shows the number of clicks on each link in the email.
* **AMP** — shows the percentage of domains that support AMP. First of all, in order to send AMP emails, you need to become a trusted sender. 

### 4.1.1. Click map

Click map displays the percentage of clicks on the links in the email.

<Image width="80%" src="https://files.readme.io/d943fda-image14.png" />

Click map reports can show the statistics sorted out by contacts or by click rate:

<Image width="80%" src="https://files.readme.io/6fe2c53-image7.png" />

* Statistics by contact show the percentage of users who clicked on any of the active links in the email. If one user clicks on one link several times, you would see this in the report. The total percentage of clicks can exceed 100%.
* Statistics by clicks show the percentage of clicks on each link. The total number of clicks is set to 100%, and the report shows the rate of clicks each link receives.

### 4.1.2 Table of clicks

This tab shows the number of clicks on each link in the email.

<Image width="80%" src="https://files.readme.io/375ed8e-image12.png" />

You can upload contacts that clicked on a specific link.

The discrepancy between the numbers in the *Clicks* and *Contacts* columns indicates that some users clicked on the same link several times.

The *Group by URL* switch combines the same links that are found in the email under different elements.

### 4.1.3 AMP

**Option 1.** If the email is without AMP content, the report will show the domains and the number of domains with and without AMP support.

<Image width="80%" src="https://files.readme.io/7beeb57-image23.png" />

**Option 2.** If the email contains AMP content, the report will show the statistics on its HTML and AMP versions.

<Image width="80%" src="https://files.readme.io/03e0193-image13.png" />

Read more about [AMP campaign report](https://docs.reteno.com/docs/amp-campaign-reports)>

## 4.2. Revenue

You can evaluate the financial campaign results if you set up integration with a CRM system that records order data.

<Image width="80%" src="https://files.readme.io/6779749-image2.png" />

The visualization of campaign revenue is displayed by 3 indicators: the number of purchases, the average check, and the total revenue.

Also, you can view detailed information about purchases from the campaign by each segment you create in your Reteno account.

## 4.3. Response time

Shows for periods of 24 hours or 7 days the statistics of activity in the email by the hour.

<Image width="80%" src="https://files.readme.io/ce07fdc-image15.png" />

You can see when your campaigns receive a response per day or week. If you regularly send emails during the day, your open rate will be highest in the first 2 hours.

If the email contains AMP elements, you can see the response time by selecting the *AMP HTML* tab:

<Image width="80%" src="https://files.readme.io/d187218-image6.png" />

## 4.4. Segments

Segments section could contain such tabs:

* Domains
* Platforms and OS
* Device languages
* Multilanguage
* Strategy (optional)
* Segments

### 4.4.1. Domains

The report provides statistics on the emails by email domains. It shows the deliverability by individual email domains, and allows to indirectly evaluate the probability of your campaign being landed in Spam.

<Image width="80%" src="https://files.readme.io/74d9d9a-image11.png" />

### 4.4.2. Platforms and OS

In the Platforms and OS tab, you can view statistics on opened, clicked messages, and click-to-open rates by users' platforms and OS.  

<Image width="80%" src="https://files.readme.io/b64621c-image3.png" />

### 4.4.3. Device languages

Statistics on campaign recipients' device languages: 

<Image width="80%" src="https://files.readme.io/4d3cb42-image9.png" />

### 4.4.4. Multilanguage

Here you can view campaign results by [its language versions](https://docs.reteno.com/docs/report-on-multilingual-campaigns).

<Image width="80%" src="https://files.readme.io/18985c0-image8.png" />

### 4.4.5. Strategy

If you have applied a frequency strategy to your campaign,  you can see all the data and statistics for each segment from the strategy. 

<Image width="80%" src="https://files.readme.io/b426e8a-7adbf7e6-3726-4f9d-9c9b-eb237c875e0e.png" />

### 4.4.6. Segments

In the *Segments* -> *Segments* tab, you can choose specific segments to view their statistics.

<Image width="80%" src="https://files.readme.io/be22150-image16.png" />

## 4.5. Experiments

The tab will appear if you have tested subjects for the campaign. Here you can evaluate the results of the A / B test for each version of the email.

<Image width="80%" src="https://files.readme.io/39c2d7c-image18.png" />

### Add details dropdown

In the upper right corner in the Add details dropdown, you can select the details of campaign for any tab by parameters:

<Image width="80%" src="https://files.readme.io/c759fec-image4.png" />

* *Domains* - statistics by domains.
* *Multilanguage* - if you send [multilingual messages](https://docs.reteno.com/docs/creating-multilingual-messages), statistics will be displayed separately for each language version of the message.
* *Strategy* - statistics by segments from strategy.
* *By groups* — Initially, statistics for all contacts are displayed, but you can select individual segments and view statistics only for them by clicking on the filter.

### Special icons

<Image width="80%" src="https://files.readme.io/c8bb715-image10.png" />

* The *copy* icon will help you quickly paste data into Excel or Google Sheets.   
* The *percent* icon shows the data as a percentage.
* Icon *00* shows statistics in numbers.
