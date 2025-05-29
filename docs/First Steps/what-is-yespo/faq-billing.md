---
title: 'FAQ: Billing'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: 'FAQ: Billing | Yespo Guide'
  description: >-
    The document explains how to start campaigns in Yespo: verify domains for
    promos, set up omnichannel channels, top up accounts, choose payment
    methods, and manage billing history.
  robots: index
next:
  description: ''
---
> 📘 Note
>
> Visit our [pricing page](https://yespo.io/tarif-universum) to view a list of pricing plans.

## Can I Top Up My Balance and Start Campaigns Immediately?

The algorithm for starting the system depends on what functionality you plan to use.

If you want to start with promo campaigns, first [verify the domain](https://docs.yespo.io/docs/how-set-email-domain-authentication). After this, you can send out campaigns even without topping up your account — 2,500 free emails are available.

If you activate CDP features, you need to make some additional settings. Please contact us for advice and support in connecting **Extra features**.

To make omnichannel campaigns, prepare the following settings:

* **SMS** – register an SMS sender ID or [enable processing](https://docs.yespo.io/docs/setting-up-sms-processing).
* **Viber** – [add sender ID](https://docs.yespo.io/docs/how-add-sender-name-viber).
* **Web Push** – [follow the instructions on the link](https://docs.yespo.io/docs/web-push).
* **Mobile Push** – [integrate your mobile app with Yespo](https://docs.yespo.io/docs/mobile-push).
* **App Inbox** – set up a channel for a [website](https://docs.yespo.io/docs/how-to-set-up-integration-for-app-inbox) and/or [mobile app](https://docs.yespo.io/docs/app-inbox-for-mobile-apps).
* **Web Widget** – install script on website and [setting up widgets](https://docs.yespo.io/docs/setting-up-widgets-for-your-site).
* **In-App** – [connect your mobile app to Yespo](https://docs.yespo.io/docs/connecting-mobile-apps) and [install SDK](https://docs.yespo.io/docs/in-app#step-2-install-sdk).
* **Telegram** – integrating with [Telegram Bot](https://docs.yespo.io/docs/integrating-telegram-bot).

After completing the settings, connect the appropriate channels on the **Pricing plans** tab.

<Image align="center" width="80% " src="https://files.readme.io/545122affdb94383b4d1705faa87209e4cb0b8dab3d2eddee64ba295a3a3eb57-001.webp" />

## How to Top Up My Account in the System?

Click the **Add funds** button on the main account page. When replenishing via built-in systems, funds are credited automatically.

When paying by bank transfer, funds are received in the system within 3-4 hours; if there are delays on the bank’s side, the payment may take 1-3 days. If you have an urgent campaign planned, send us a scan/photo of the receipt to [sales@yespo.io](mailto:sales@yespo.io).

## What Payment Methods are in the System?

The system has several payment methods:

* Visa/Mastercard payment cards.
* Payment by legal entities and individuals with an invoice.
* Paypal.

To add a card, click the **Pricing plans** button on the main account page, go to the **Payment methods** tab, and click **Add card**.

<Image align="center" width="80% " src="https://files.readme.io/f2ab5f7f12ca84c31e2aafec1c566e1f1ed52d2e53904eff51087ecb01517de7-002.webp" />

## Where Can I Form an Invoice?

Click the **Pricing plans** button on the main account page. You will see a list of system features that you can activate.

<Image align="center" width="80% " src="https://files.readme.io/bfbff41e66d5fc307f3586fbc20373559d30bfc3476cf580365b851359d0165d-003.webp" />

1. Expand the spacer with the functionality you want to activate.
2. Select your plan settings using the slider.
3. Click **Enable**.

<Image align="center" width="80% " src="https://files.readme.io/50056b79fb963239416d5d95e7cc7482ecd61ed5a4a4848f7db7efa636a96f64-004.webp" />

After replenishing the account, the monthly payment will be debited from the account, and the functionality will be activated. 

## I Made the Payment, But I Don’t See Any Funds on My Balance. Where's the Money?

Bank transactions take from several hours to several days.

## How to Receive Payment Documents?

Please leave a request with a list of required documents at [sales@yespo.io](mailto:sales@yespo.io).

## Where Can I See My Payment History?

Click the **Pricing Plans** button on the main account page and go to the Payment history tab. Select the period for which you want to view history.

<Image align="center" width="800% " src="https://files.readme.io/f397e416468453125bd7b294637f21bc2ba7fc58c0738b1bedea19a1c3f0f486-005.webp" />

You can also use the [Get organization billing history](https://docs.yespo.io/reference/getorganisationbalancehistory) API method — the request will return the billing history separated by days and media channels.

## How Can I Add a Billing Address for Invoice Display?

To add a billing address, click **Pricing plans** on the account homepage, go to the **Billing address** tab, and fill in your organization’s details. All fields are required except for *Additional information*.

<Image align="center" width="80% " src="https://files.readme.io/28945908d65bb6a5171dd86932fcddeb1ae6825e1b57bf710b040413bf390733-billing-address-en.webp" />

These details will then be used for invoice generation.

## How Do I Set Up Billing Notifications?

You can specify the email addresses of users who should receive billing notifications in your account settings → **My account** tab. Enter addresses separated by commas and click **Save**.

<Image align="center" width="80% " src="https://files.readme.io/4e3d0c21d6815341210eba49d06361e933db10b1948bcb2e42dfb65d6ef81586-1-1.webp" />