---
title: Promo Code Added from User Profile
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promo Code Added from User Profile | Yespo Guide
  description: >-
    The document outlines a process for sending personalized bulk mailings with
    unique promo codes to ensure each recipient receives their specific code.
  robots: index
next:
  description: ''
---
Technically – the most straightforward method, when promo code is written in the [user profile](https://docs.yespo.io/docs/user-profile) and is substituted to the message from there.

Convenient for mass mailing when it is necessary to send a unique promo code to each recipient.

Mailing preparation contains next stages:

## Creating additional field in the system

For this, enter *Settings → Additional fields*.

<Image align="center" width="80% " src="https://files.readme.io/4d021c22542dda6f1bfcdb81a87959a5178c7ec7a9f83aef5c254289095a9cc4-100eece-promocodes1.webp" />

Click *New field* button and fill up the field *Name*. The Personalization key is generated automatically. By default, *Field type* contains *Text box* option. You can leave this option If you use promo codes with numbers and letters.

<Image align="center" width="80% " src="https://files.readme.io/c7d351e8fa2df58e7bd969e625f3b9bb21ea811c6ff537683bdb4d798efd1aed-1eb3b58-promocodes7.webp" />

## Uploading the file with contacts and respective promo code

It is a usual Excel or CSV file, which has columns with email addresses or phone numbers and respective promo codes.

Through contact import upload the file. When configuring fields conformity, choose the *Promo code* field for the corresponding column.

The system will update contacts and add promo codes to respective contacts.

<Image align="center" width="80% " src="https://files.readme.io/b7abbbf43b4a2caca482dbd211de325f8e43eddb27cdccc49c020e1d389492f7-7f4b246-promocodes123.webp" />

As a result of import, will be created a group of contacts. The mailing needs to be done for this group.

## Creating and sending the message

In the message template click on the place, where promo code needs to be located, click *[Merge Tags](https://docs.yespo.io/docs/personalization-and-dynamic-variables)*, then *Promo code*. The system will substitute necessary variables by itself.

<Image align="center" width="80% " src="https://files.readme.io/18fa9716eeca1acdcc3916352a413cacb3ec26abdc57803b9f55d5b3493d117d-f10b90d-promocodes13.webp" />

After completing settings, execute usual messages mailing for the group of contacts. So each recipient will receive the message with the proper promo code, assigned for them.
