---
title: Short Links Settings
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Short Links Settings | Yespo Guide
  description: >-
    Learn how to create a custom link shortener domain to increase consistency
    in communication with your subscribers
  robots: index
next:
  description: ''
---
Yespo uses the `esclick.me` domain for link wrapping by default. However, you can make your communication with subscribers more consistent and recognizable by creating your domain for link shortening, for example — `yourbrandname.link`.

## Creating a Custom Domain

1. Go to your account settings → **Links → Short links** tab and click **New custom domain**.

<Image align="center" width="80% " src="https://files.readme.io/e3572cc61e60f37ed317208b49cf9d410554107ebc2da7315a8b23d6e9c233a9-short_links_1.webp" />

2. Enter your domain name and click **Done**. The type, host, target, and `SSL` certificate are generated automatically; you only need to set up a **DNS CNAME** record pointing to our secure server.

<Image align="center" width="80% " src="https://files.readme.io/ff0ca9c2ef0a6a348770d2bc3fa5e30e2a112ed40dadf2071fda468af00694a7-short_links_2.webp" />

## Creating a Destination Domain

If you need the links to direct users to specific content in the app, create a destination domain.

1. Click **New destination domain**.

<Image align="center" width="80% " src="https://files.readme.io/82774d71b0777df42d6f1f1d5715141cf837e19350cb483999f5a4f5a0aae925-short_links_3.webp" />

2. Enter the domain name and upload the associated files:

* **For iOS:** a `TXT `file (no larger than **128 KB**) containing data in `JSON` format.
* **For Android:** a `JSON` file (no larger than **128 KB**).

<Image align="center" width="80% " src="https://files.readme.io/8cad89e3e4f84270aba6f02b30da51cb3e33b0205babeafd5b7f08d61472ebd9-short_links_4.webp" />

### Creating Paths to Open Links in a Browser/App

The paths specified in links allow you to determine where to open them, in a browser or in a mobile app.

The paths in links are processed in the following channels:

* [Email](https://docs.yespo.io/docs/email-setting-up)
* [SMS](https://docs.yespo.io/docs/sms)
* [Viber](https://docs.yespo.io/docs/viber)
* [Web Push](https://docs.yespo.io/docs/web-push)
* [App Inbox](https://docs.yespo.io/docs/app-inbox)
* [Telegram](https://docs.yespo.io/docs/telegram)

In channels such as [Mobile Push](https://docs.yespo.io/docs/mobile-push) and [In-App](https://docs.yespo.io/docs/in-app), links to Android apps require [special processing settings](https://docs.yespo.io/reference/android-push-handling#deeplinks).

Paths for opening links in **Android apps** must be added in the association file that you upload to Yespo, as such settings are made in the `AndroidManifest.xml` file.

Paths for opening links in iOS applications can also be added to the association file, or specified directly in the Yespo settings:

<Image align="center" width="80% " src="https://files.readme.io/719edc9f8b6c451441a0368daad3903329995a5868faed5e9410dc28c87fbf25-short_links_5.webp" />

**Paths examples**

You can use the \*\*\*\*\* symbol instead of the domain name — then the path will work for all destination domains created in your account.

| Example               | Description                                                                                                                                   |
| :-------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| `NOT /unsubscribe*`   | Links starting with `/unsubscribe` (e.g., `/unsubscribe`, `/unsubscribe-now`) always open in the browser.                                     |
| `/faq/*`              | Links that start with `/faq/` (e.g., `/faq/123`, `/faq/general`) always open in the app.                                                      |
| `/about`              | The specific path `/about` opens in the application. This rule does not affect other paths, such as `/about/team`.                            |
| `/contact*`           | Links that start with `/contact` (e.g., `/contact`, `/contact-us`) always open in the app.                                                    |
| `NOT /*/external*`    | Links that start with `/contact` (e.g., `/contact`, `/contact-us`)  always open in the app.                                                   |
| `/products/*/details` | Links that match the pattern `/products/[any path]/details` (e.g., `/products/123/details`, `/products/toys/details`) always open in the app. |
| `NOT /promo*`         | Links starting with `/promo` (e.g., `/promo`, `/promo/offer`) always open in a browser.                                                       |

> 📘 Note
>
> The examples above do not work in the system by default — you must specify similar paths in the association files or in the Yespo settings.

Other features of the functioning of the paths:

* Any other links that do not meet the rules specified in the paths will open in the app.
* An associated file that does not have a path specified cannot be downloaded.
* At least one path must be specified in the account settings.
* The letter **u** is added to links that open in the application, for example, `https://click.example.com/u/jh3kkj3kl`.

## Domain Activating and Deactivating

Only one custom domain can be active. If several are registered in the account, the last one created will be added to the top of the list and activated. You can deactivate a domain and activate any of the listed ones instead.

<Image align="center" width="80% " src="https://files.readme.io/95d3056c83f5a5d838a3a7c333a4f45fc7510cd65a862da03ec2ef4fa15ff796-custom_domain.webp" />

> 📘 Note
>
> Links wrapped in the esclick.me domain that were sent earlier will continue to work.