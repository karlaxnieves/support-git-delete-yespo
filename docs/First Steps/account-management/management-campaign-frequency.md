---
title: Setting Up Annoyance Level
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Annoyance Level | Yespo Guide
  description: >-
    When you send numerous campaigns, you may be too intrusive with your
    subscribers. To avoid this, learn how to set up the annoyance level and
    regulate the sending volume.
  robots: index
next:
  description: ''
---
Email marketing consists of different types of campaigns:

* Welcome
* Promo
* Triggered
* News
* Events, etc

However, too often communication can result in the negative outcome:

* Spam complaints
* Unsubscribes
* Decrease of loyalty

If you send frequent (daily) campaigns to different segments that can include the same contacts, there is a chance you might be too intrusive with part of your contact base. To avoid this, set up the annoyance level and limit messages you send.

> 📘 Important
>
> Annoyance Level is applicable to emails and mobile push notifications. To manage the sending limit for all channels, set up [Campaign Frequency](https://yespo.io/blog/how-to-develop-effective-email-frequency-strategy) and [Subscription Categories](https://docs.yespo.io/docs/how-use-subscription-category).

1. Go to your personal profile → *Settings* → *Laboratory* and enable *Annoyance Level*.

<Image align="center" width="80% " src="https://files.readme.io/693975e3a9901817312ff5cf30da0a6d0c6e3b765f7ebd1ebc78457eed816f3c-Settings_rtn.webp" />

2. Unroll the tab and specify daily and weekly annoyance limits.

<Image align="center" width="80% " src="https://files.readme.io/350f7bfd4f173ffa4b0f27a198ce47053a26c1436227970cd5af145979701a98-annoyance_limits.gif" />

The annoyance level consists of the daily and weekly limit credits you assign to a campaign depending on its type and sending frequency. Based on them, the system calculates the acceptable annoyance level for a particular contact using their contact ID. If the annoyance limit is exceeded for the contact, the campaign won’t be sent to them.

## Credit Calculation

The key with assigned daily limit credits resets every day at 00:00 UTC. The key with weekly credits resets on Sunday until 11:59 pm UTC.

## How to Assign Credits

**Email**

* In *Messages* → *Messages* → *Email*, open the necessary email or create one.
* Click the subject to open its sender info settings.
* In *Annoyance level*, enter the necessary credit.

<Image align="center" width="80% " src="https://files.readme.io/9abbf269baf2b8dc81b3febd59b7769183c37a481f5fa5f489ef00b4c28a2130-How_to_assign_credits_to_an_email.webp" />

**Mob Push**

* In *Messages* → *Messages* → *Mob Push*, open the necessary push notification or create one.
* Enable *Annoyance level* and enter the necessary credit.

<Image align="center" width="80% " src="https://files.readme.io/cec227656d6cd3004416b35eda6c4cf0e8cc1ee3d28818722be0f7a2ff085cf6-How_to_assign_credits_to_a_mob_push.webp" />

You can also set up the annoyance level in *Send options* when you schedule a campaign.

<Image align="center" width="80% " src="https://files.readme.io/dc241ae858d0fd0647d1e2f77aa8ea88f36d4d19ef05aadd35ee2e647bb401f2-Send_options.webp" />

> 📘 Important
>
> If one contact has an email address and mob push token with different IDs, annoyance credits will be assigned separately for each ID.

## Example of How to Use Annoyance Level

The online store sends several types of campaigns:

* Triggered promo. Sent to the segment that includes users who haven’t visited the website for a week.
* Daily news.
* Weekly digest.

Annoyance credits for each type:

* Promo – 3 credits;
* News – 1 credit;
* Digest – 2 credits.

**How the daily limit is calculated**

Say the daily annoyance limit is 4 credits. Contacts that have both email address and push token have one ID.

Today, the user has already received a promo email and news push and thus reached the limit. A digest won't be sent to this user.

**How the weekly limit is calculated**

Say that the weekly annoyance limit is 10 credits.

If today is Thursday, and the user has already received several messages and reached 8 credits, till the end of the week they can receive either one message assigned with 2 credits or two messages assigned with 1 credit each.

The system won’t send campaigns to contacts with exceeded limits. Such messages will fall to *Errors*.

<Image align="center" width="80% " src="https://files.readme.io/9dee91b9c045fd4fead65b349a01356894ceac2e5b96f97c8eff5defcc689ef1-Error_status.webp" />

> 📘 Important
>
> Assign important messages with 0 annoyance level so that their send does not affect the limit. But if the daily or weekly level is already exceeded, campaigns with even 0 annoyance level won’t be sent anyway.
