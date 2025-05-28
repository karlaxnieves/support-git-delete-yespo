---
title: Checking Domain Settings and Reputation with Google Postmaster Tools
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: >-
    Checking Domain Settings and Reputation with Google Postmaster Tools | Yespo
    Guide
  description: Learn how to track sender domain reputation using Google Postmaster Tools
  robots: index
next:
  description: ''
---
Postmaster Tools is a set of tools from Google for analyzing and improving the delivery of email campaigns on Gmail. These tools provide insight into how your campaigns are perceived by Gmail and their recipients. The set includes the following tools:

* Spam Rate
* IP Reputation
* Domain Reputation
* Feedback Loop
* Authentication
* Encryption
* Delivery Errors

Note

[Configure digital signatures](https://docs.yespo.io/docs/how-set-email-domain-authentication) for your domain to use Postmaster Tools

## Adding a Domain to Postmaster Tools

1. Go to <a rel="nofollow" href="https://postmaster.google.com/" target="_blank"> Postmaster Tools</a>.
2. Enter the domain name and its TXT or CNAME record to verify that you are the domain’s owner.

<Image align="center" width="80% " src="https://files.readme.io/e22b5cadfc9cbce9516054bb4a3571179d5504e2fe3c9d2443c22cc2d63e484a-postmaster-1.webp" />

Once registered, you will be able to use the tools described below.

## User Reported Spam

Spam complaint percentage (emails delivered directly to the Spam folder are not included in the calculation). The spam level is calculated only for DKIM-authenticated mailings.

<Image align="center" width="80% " src="https://files.readme.io/484716fcb2978392b6238612d4f7f4a528958204a4dc272ce98a40d695e0961e-postmaster-2.webp" />

## IP Reputation

Reputation of the IP address used to send mailings.

<Image align="center" width="80% " src="https://files.readme.io/2cf90086af492633cd887d503eb911f443b5ed0b84f41349340d113594c2cd77-postmaster-3.webp" />

Reputation is assessed by the following indicators:

* High – the IP address has a good reputation, and messages appear in the inbox (General, Suggestions, Social Networks, or Updates).
* Medium – the vast majority of emails arrive in the inbox, but there is a risk that some messages may be classified as spam or rejected.
* Low – most emails will probably end up in spam.
* Bad — with such a reputation, any email will end up in spam or be rejected by SMTP (Simple Mail Transfer Protocol).

## Domain Reputation

Domain reputation in Gmail. If it drops, it is necessary to analyze the mailings made in the corresponding period. A bad reputation leads to mailings ending up in spam.

<Image align="center" width="80% " src="https://files.readme.io/4a9b9fad748e8e98f69fd8a17b7ee384b066d46e830c48bba82cdd1f71816dfe-postmaster-4.webp" />

## Spam Feedback Loop

Following <a rel="nofollow" href="https://support.google.com/a/answer/6254652?hl=en&sjid=6029099505035535639-EU" target="_blank"> Google standards</a>, we transmit information about the campaign type, the sender’s organization ID in Yespo, the campaign ID, and the Sender ID in the Feedback-ID email header.

* An example of Feedback-ID for a bulk campaign: b4502231:Yespo.io.
* An example of Feedback-ID for a trigger campaign: t197398:Yespo.io.
* An example of Feedback-ID for a single message: im14413670895:Yespo.io.

**b** before the first number is the identifier of the bulk campaign; **t** is the identifier of the trigger campaign; **im** is the identifier of a single message.

Long numbers are:

* Callout ID of a bulk campaign.
* ІМ-Callout ID of a trigger campaign via a workflow or the Smartsend method.
* Instant Message ID (IMID) of a single test or sent via the v1/message/email method.

When email recipients with @gmail.com addresses report spam, the Spam Feedback Loop graph displays the complaints.

<Image align="center" width="80% " src="https://files.readme.io/804f513d801a2781fd1414f8067eaf02b8505f8f6c7ca138032764f9998d2327-postmaster-5.webp" />

Click any data point on the graph to see the IDs of campaign types and the corresponding spam complaint rates. The Feedback-ID header will show you which campaign resulted in spam complaints.

## Authentication Traffic

The volume of traffic passing SPF, DKIM, and DMARC authentication.

<Image align="center" width="80% " src="https://files.readme.io/57691edd56c571c156cc8864f2d1f51669b18f28c1ced5826c06826b1afb84ff-postmaster-6.webp" />

## Encrypted Traffic 

The volume of inbound and outbound traffic encrypted using the TLS (Transport Layer Security) protocol.

<Image align="center" width="80% " src="https://files.readme.io/904843253d2acd5e5b2692eb0a1aab044695b8a0ec6cb1fb6a287e23a4495597-postmaster-7.webp" />

## Delivery Errors

2 types of errors are displayed:

* SMTP Error 550: The recipient does not exist or is incorrectly specified.
* SMTP Error 421: The message was not delivered due to temporary problems with the mail server or due to exceeding mail traffic limits.

<Image align="center" width="80% " src="https://files.readme.io/b27e2ada5453b9c871a1426b1f12ce423e0b227e68cf8444c1049e3f03cef9a1-postmaster-8.webp" />

Click on any data point on the graph to see the reason for the error.
