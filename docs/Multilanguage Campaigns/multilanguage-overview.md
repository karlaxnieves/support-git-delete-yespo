---
title: Multilanguage Overview
excerpt: >-
  Multilanguage is an automation tool that enables sending messages in different
  languages within one campaign. It helps avoid long message lists and
  voluminous unsystematic reports for every message
deprecated: false
hidden: false
metadata:
  title: Multilanguage Overview | Yespo Guide
  description: >-
    The document outlines three methods for using the multilingual feature in
    Yespo: utilizing in-built functionality, employing external data sources
    like Google Spreadsheets for managing multiple language versions, and using
    workflow condition blocks to create separate messages for each language.
  robots: index
next:
  description: ''
---
Multilanguage is an automation tool that enables sending messages in different languages within one campaign. It helps avoid long message lists and voluminous unsystematic reports for every message.

[How contact language data is collected >](https://docs.yespo.io/docs/adding-the-preferred-language-to-the-user-profile)

You can use the multilingual feature in three ways.

## 1. Using In-build Functionality

Create one message with as many language variants as you need. The system will automatically detect recipient's language and send the corresponding variant.

Use multilingual message templates for any Yespo channel:

- [Email](https://docs.yespo.io/docs/compose-email);
- [Mobile Push](https://docs.yespo.io/docs/how-to-create-mobile-push-notifications);
- [In-App](https://docs.yespo.io/docs/creating-in-app-message);
- [Web Push](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications) and [Browser Push Notification Permission](https://docs.yespo.io/docs/how-set-multilingual-browser-push-notification-permission);
- [App Inbox](https://docs.yespo.io/docs/how-create-app-inbox-messages);
- [Viber](https://docs.yespo.io/docs/viber-messages-creation);
- [SMS](https://docs.yespo.io/docs/creation-sms);
- [Telegram](https://docs.yespo.io/docs/creating-telegram-message);
- [Widgets](https://docs.yespo.io/docs/setting-multilingual-widget).

The creation process is similar for all channels. See it on the example of [email](https://docs.yespo.io/docs/creating-multilingual-messages).

Compare and optimize multilingual campaigns [with the help of specialized analytics](https://docs.yespo.io/docs/report-on-multilingual-campaigns).

## 2\. Using External Data Sources

Many apps have users all over the world, so the number of campaign language versions can be in the tens. Even creating these variants inside one message, you can spend many hours on routine work.

Instead, you can create a Google Spreadsheet and write the content of each message language alternatives into it. After that, you will only have to create one version of the message with variables referring to this table, and the system will send the appropriate version to each recipient. [See details >](https://docs.yespo.io/docs/using-google-sheets-for-multilanguage-messaging)

## 3\. Using Workflow Condition Blocks

If you feel more comfortable with creating separate messages for each language — no problem! Just add to the workflow language check blocks. [How it works >](https://docs.yespo.io/docs/creating-multilingual-campaigns#creating-triggered-workflow)

> 📘 Note
> 
> [Find out if _Multilanguage_ is included in your tariff plan](https://yespo.io/segmentation-price).
> 
> To connect the feature, send a request to [sales@yespo.io](mailto:sales@yespo.io)