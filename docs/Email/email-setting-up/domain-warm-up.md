---
title: Domain Warm-up
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Domain Warm-up | Yespo Guide
  description: >-
    This document outlines warming up a new email domain to build trust with
    providers, preventing spam flags. It details gradually increasing daily
    email volume with the new domain signature.
  robots: index
next:
  description: ''
---
After [changing the DNS record](https://docs.yespo.io/docs/dns-record-change), warm up the domain. This is the next step in improving sender reputation.

Domain warm-up is the gradual increase in the number of emails sent from a new domain to establish trust with email service providers (such as Gmail, Outlook, etc.) and avoid being flagged as spam.

<Image align="center" width="80% " src="https://files.readme.io/f8a14ff705eb0bcb0562b9982085a0fb6cd382195337bd66c84c2c97cbade2fc-domain-warm-up-01.webp" />

Yespo automatically warms up the domain for clients who have verified it.

## Domain Warm-up

Let's consider how the process is organized and how many days are required for domain warm-up. For example, let's take sending 100,000 messages per day.

Create an email and [launch a campaign](https://docs.yespo.io/docs/launching-an-email-campaign):  

* **First day campaign**. On the first day with a new domain, you can send up to 1000 emails; otherwise, the campaign may raise suspicions on email servers. Yespo will send the first 1000 emails, signing them with your DKIM, and the remaining 99,000 emails with the Yespo domain signature.
* **Second day campaign**. On the second day, Yespo will send 2000 emails with your DKIM and 98,000 with the Yespo domain signature, and so on.

Below is a table calculated for 25 days with a daily sending limit.

| Day | Limit     |
| :-- | :-------- |
| 1   | 1000      |
| 2   | 2000      |
| 3   | 4000      |
| 4   | 7000      |
| 5   | 11000     |
| 6   | 18000     |
| 7   | 24000     |
| 8   | 40000     |
| 9   | 60000     |
| 10  | 90000     |
| 11  | 140000    |
| 12  | 180000    |
| 13  | 220000    |
| 14  | 300000    |
| 15  | 500000    |
| 16  | 650000    |
| 17  | 800000    |
| 18  | 1000000   |
| 19  | 1200000   |
| 20  | 1500000   |
| 21  | 1700000   |
| 22  | 1900000   |
| 23  | 2100000   |
| 24  | 2300000   |
| 25  | 2500000   |
| 26  | unlimited |

> 📘 Note
>
> The limits are the same for all campaigns, including trigger-based ones.

Yespo's DKIM will sign each campaign regardless of the customer's domain. Initially, most emails will be sent with the Yespo signature, and then the number of emails sent with your domain signature will gradually increase.

When the new domain's warm-up reaches the required level, all emails will be sent with two DKIM signatures—yours and Yespo's.

In our example, with a daily sending limit of 100,000, it takes 11 days to warm up the domain.

<Image align="center" width="80% " src="https://files.readme.io/6962f3e38ed0a4f889fd8370517da5577db4afaf27253768c76161af4e4f4c0a-domain-warm-up-02.webp" />

## Checking the Sending Limit

There are two statuses of the daily sending limit:

* Not reached
* Has been reached/Has been reached for some domains

Go to **Settings → Domain verification** and click **Daily sending limit** to view your daily sending limits.

<Image align="center" width="80% " src="https://files.readme.io/c85cd9e8a3360fd307d902205fb1d9979e6e756c6f210b382f62503f990331c8-domain-warm-up-03.webp" />

### The Sending Limit Has Not Been Reached

<Image align="center" width="80% " src="https://files.readme.io/2434d8ab4037cb07fc25e60d015af9d713556c23ef5085a780a2cf2cede5860f-domain-warm-up-04.webp" />

Hover over the progress bar next to the domain name, and a tooltip will appear showing the number of messages sent and the remaining messages.

<Image align="center" width="80% " src="https://files.readme.io/dd191352594158167549c474faf59cada9a4afe7300af342f7622c61787b0998-domain-warm-up-05.webp" />

### The Sending Limit Has Been Reached

<Image align="center" width="80% " src="https://files.readme.io/fe5c31fee07f96978949894fcc309cffdf7b9728d48210d835657317a1543554-domain-warm-up-06.webp" />

Domains that have reached daily limits are displayed in a separate list.

<Image align="center" width="80% " src="https://files.readme.io/416b1070d384a2af31cbd4a53aa778040bfc952ed2a0532942632273ac283d19-domain-warm-up-07.webp" />

> 📘 Note
>
> Warm-up data is refreshed every day at 00:00

If your domain has no strict DMARC policy, sending limit restrictions will not be displayed in your account. In that case, please contact our technical support to get information about warm-up.

## Sending Limit

A separate case worth noting is when a strict DMARC policy is enforced — a limit on the number of emails the domain owner sends.

In DMARC settings, one of the following values may be specified:

* **none** — takes no action on the email,
* **quarantine** — places the email in spam,
* **reject** — rejects the email.

If the value is set to **none**, the warm-up proceeds as described above. However, if DMARC is set to **quarantine** or **reject**, when the daily limit is reached during the warm-up period, no further emails are sent. Even if the emails are signed using the DKIM signature of the Yespo domain, they may still end up in spam or be rejected.

Under a strict DMARC policy, it's advisable to manually limit the number of daily sends or set the value to none during the warm-up period.

Use the <a rel="nofollow" href="https://mxtoolbox.com/dmarc.aspx" target="_blank"> MxToolbox </a> service to check **DMARC** domain settings. 

<Image align="center" width="80% " src="https://files.readme.io/137650872c1c735668d79a3831755ff2c2fc1e14fdab010609de86878ba6028a-domain-warm-up-08.webp" />

When manually limiting the number of daily sends, use the following recommendations:

1. Begin the campaign with 10-20 emails per send, spaced a few hours apart. This way, approximately a hundred emails will be sent throughout the day.
2. Send the most engaged users. Users should open, read, and take the desired action. 
3. Plan the warm-up phase for 4-6 weeks. Typically, the process occurs within this timeframe.
4. Use the Postmaster tools to check [domain settings and reputation](https://docs.yespo.io/docs/checking-domain-settings-and-reputation-google-postmaster-tools).

The next step in improving the sender's reputation will be setting up [double opt-in](https://docs.yespo.io/docs/subscription-form-configuration).