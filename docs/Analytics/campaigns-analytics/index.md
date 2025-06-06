---
title: Campaign Reports
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Campaign Reports | Yespo Guide
  description: >-
    The document covers campaign reporting: filter, search, export, and manage
    reports across media channels. View revenue, track performance, and manage
    active campaigns.
  robots: index
next:
  description: ''
---
Reports provide statistical campaign information and are available in the *Campaigns → Reports* section.

Reports display a table of all your campaigns with their respective statuses, the number of contacts who participated in them, and the effectiveness of each campaign.

<Image align="center" width="80% " src="https://files.readme.io/19dfa6062cfd981d3a3035e07c97cad0a6afd242a076338ef512e96fd6c2945c-reports-01.webp" />

Reports are available for the following media channels:

* [Email](https://docs.yespo.io/docs/email-campaign-reports)
* [SMS](https://docs.yespo.io/docs/sms-campaign-reports)
* [Web Push](https://docs.yespo.io/docs/web-push-campaign-report)
* [Mob Push](https://docs.yespo.io/docs/mobile-push-campaign-report)
* [Viber](https://docs.yespo.io/docs/viber-campaign-report)
* [App Inbox](https://docs.yespo.io/docs/app-inbox-campaign-report)
* [In-App](https://docs.yespo.io/docs/in-app-report)
* [Web Widget](https://docs.yespo.io/docs/widget-analytics)
* [Telegram](https://docs.yespo.io/docs/telegram-campaign-report)

## Bulk & Triggered Campaigns

There are 2 types of campaigns depending on the sending way:

* Bulk – one-time sending of one message to a group of contacts. For example, promo or newsletters.
* [Triggered](https://docs.yespo.io/docs/triggered-campaign-report) — automatic campaigns based on specific actions of the contact, such as subscription, purchase, review, and so on.

<Image align="center" width="80% " src="https://files.readme.io/1b11b97f8dc8832b54076988dc5a04fc6aee5c57c1445a0d94bd7bbc42071859-reports-02.webp" />

Activate the checkbox in the *Deleted* field to view deleted campaigns.

<Image align="center" width="80% " src="https://files.readme.io/83bb7ee9ac58e000dfb9bdfc36677f2d7345dcaae16f789479d74ed494be204e-campaign-reports-03.webp" />

## Managing Bulk and Triggered Reports

### Using Message and Widget Preview

To see the message and widget preview in the bottom right-hand side corner, point to the widget or message name in the *Reports* column.

<Image align="center" width="80% " src="https://files.readme.io/fca8fd5e4524c92f42a4d634ac7a5d6942305cfad5d02a5bcd662f82e9ea0d29-preview-widget.webp" />

### Filtering Reports

Reports are displayed as a list and automatically sorted by the start date of the campaigns — the newest ones appear at the top. If needed, you can set a custom period or use one of the preset intervals.

<Image align="center" width="80% " src="https://files.readme.io/e116db03860166ee10218fcd5db436bcf9fd492608a85c139e0602f9bb1b22ac-lifetime_en.png" />

### Searching Reports 

To search for a report in the general list, insert one of the following parameters into the search bar after selecting the media channel and campaign type:

* Campaign name
* Tag (if added)
* Campaign ID
* Message ID

<Image align="center" width="80% " src="https://files.readme.io/0c8ae6ffadf3ef0774e7b572a141141f4c6f1409c5c0fd124cef2037f474895a-image2.webp" />

> 📘 Note
>
> To search using an ID, precede it with the appropriate search operator:
>
> * cid: before the campaign ID
> * mid: before the message ID

### Exporting Reports

To export statistics on selected campaigns into a separate CSV file, click the *Export button*. The file will contain data for the selected media channel for up to six months.

<Image align="center" width="80% " src="https://files.readme.io/30dbc44e91855596cfda707a331767afe094b87c66e1fbaaf918a78219c11397-reports-03.webp" />

### Copying Reports

To copy data to the clipboard, click the corresponding icon. Copying is carried out for the reports displayed on the page, taking into account the settings specified in the *Display* tab.

<Image align="center" width="80% " src="https://files.readme.io/a25666f30c44bc1d9b139b5de87b954599dd4e8cd26067b8d8b313f057460674-reports-04.webp" />

### Viewing Revenue 

The results are presented separately for each media channel and campaign type. To display revenue in the table, click the icon with the dollar symbol.

<Image align="center" width="80% " src="https://files.readme.io/84a0a1823388677fafd01aaa51fe53ce3d2b896d68fb9c59bbab223783cb28b4-reports-05.gif" />

> 📘 Note
>
> To see how much revenue a campaign has generated, [enable its visualization in your Yespo account](https://docs.yespo.io/docs/how-set-revenue-campaign).

### Setting Up Report Displaying

<Image align="center" width="80% " src="https://files.readme.io/d4bf0fa6f442a268d3782258b0f50828b4d72704fa0dd9d71dbd5a5b0888908b-reports-06.webp" />

The *Display* tab allows you to:

1. Highlight the campaigns by the best and the worst indicators.

Activate the *Highlight best and worst campaigns* switch. The best metrics will be highlighted in green and the worst — in red.

<Image align="center" width="80% " src="https://files.readme.io/bf24cc9e1073346778c8d9887e19a8dcafc806d48d1bc12e4ab510e0716a4cd2-reports-07.webp" />

2. Change the number of reports displayed on the page: 5, 10, 25, 50, or 100.

<Image align="center" width="80% " src="https://files.readme.io/501c44fbeee0329f3e6cfbf27c24b804dea436754dc9dca6a1d4cda3c948d55f-reports-08.webp" />

3. Hide or add columns with indicators to the list of reports. For example, hide the categories of unsubscribed contacts or display the number of purchases.

<Image align="center" width="80% " src="https://files.readme.io/46bb18a0cbae83c70726445d5847e9b351e2c828868d0c9228e582db7c21089b-reports-09.gif" />

## Single Reports

Single messages are sent via workflows and APIs, as well as test messages from the message editor.

See single reports in the *Campaigns → Single reports* section.

They are displayed as message lists and contain the following data:

* Receiver
* Message
* Date
* Result

<Image align="center" width="80% " src="https://files.readme.io/ab1ef19edea0dd50318e963185ebd9b0afc559d1e52105a35d721bb377d4ac75-single-en.webp" />

The options for managing the *Single reports* section are similar to reports for bulk and triggered campaigns.

## Special Icons

* The *copy* icon will help you quickly paste data into Excel or Google Sheets.
* The *percent* icon shows the data as a percentage.
* The *00* icon shows statistics in numbers.

<Image align="center" width="80% " src="https://files.readme.io/f6c2246e70a1a1a23e7ab3fcac6aca00eb7982b86985c3cfa133b04a6159f95b-image4.webp" />

Multilingual messages in the lists are marked with a globe icon. The number next to it indicates the number of language versions.

<Image align="center" width="80% " src="https://files.readme.io/5b37e9457c51a195c5601cb8bc87042a41ffd838d903b111e31be3e095a522ea-image14.webp" />

[Learn more about multilingual reports >](https://docs.yespo.io/docs/report-on-multilingual-campaigns)

## Managing Active Campaigns

Reports on campaigns that are in the process of being sent contain *Pause* and *Stop* buttons at the top, with which you can wholly or temporarily stop the campaign. To restart it, click the *Start* button.

<Image align="center" width="80% " src="https://files.readme.io/9607402f53e88aaae31dc849f7bf39d40cbd3bad00a7912c62836150cde6550d-image13.webp" />

The system could also pause the campaign automatically. It happens if:

* There needs to be more funds in your account.
* The email has [unique promo codes](https://docs.yespo.io/docs/promocodes) that have expired.

After you fund your account or update the list of promo codes, you can un-pause the campaign by clicking on the *Start* button.
