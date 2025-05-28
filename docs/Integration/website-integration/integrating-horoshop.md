---
title: Integrating with Horoshop
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integrating with Horoshop | Yespo Guide
  description: >-
    Horoshop is a SaaS platform that allows users to create online stores and
    integrate them with Yespo for data transfer, requiring a Pro tariff plan and
    API setup, along with steps for web tracking and product feed import.
  robots: index
next:
  description: ''
---
<a rel="nofollow" href="https://horoshop.eu/" target="_blank"> Horoshop</a> is a SaaS platform for creating online stores. You can independently, without involving developers, set up the transfer of contact and order data from a website based on Horoshop to Yespo.

> 📘 Note
>
> To integrate with Yespo on the Horoshop platform, activate the Pro tariff plan in your Horoshop account. Additionally, set up data transmission through API.

Before connecting a new integration, complete the following steps:

* [get a web tracking script](https://docs.yespo.io/docs/how-set-web-tracking-your-website),
* [import product feed into your account](https://docs.yespo.io/docs/importing-product-feed).

If you have already completed these steps, proceed directly to connecting and setting up a new integration.

## Connecting a New Integration in Your Yespo Account

1. Go to the Yespo account settings → *Integrations* tab and click the *New integration* button for the Horoshop service.

<Image align="center" width="80% " src="https://files.readme.io/e43a8d932dccb525421b2c783d956437e1b6ed2c148a41c6df7909ed4eece742-22.webp" />

2. Specify the new site's address and enter your Horoshop username and password.

<Image align="center" width="80% " src="https://files.readme.io/cb00e43c66e2e4aaae0cf27097e1c30bceb5fd2452296c7ab3e9f7cafbf232aa-horoshop-2.webp" />

3. Click *Next* and configure the integration parameters.

### Setting Up Integration Parameters

Activate the switches next to the functions you are going to use:

**Receive contacts**

* Contacts are received after the visitor has registered on the site or has placed an order.
* Contact data can include different parameters depending on the action completed on the site.
* Parameters received by default: email, first name, surname.

**Create contact with confirmed email address**

* If contacts did not provide explicit confirmation when collecting data, you must collect contacts unconfirmed.
* You can send both bulk and triggered messages to confirmed contacts.
* You can send only triggered messages to unconfirmed contacts.

**Receive orders**

You can use order data in workflows and messages.

> 📘 Note
>
> Only the status *Initialized* is transmitted in orders.

[More on automating work with orders >](https://docs.yespo.io/docs/orders-1)

Click the *Done* button.

The service will appear in the list of integrations.

Click the three dots icon in the top right and confirm deletion to remove the integration.

<Image align="center" width="80% " src="https://files.readme.io/8f5dd3b5ffb28bd3e6d77d025bc0503fae5ab9ed76926a4290323ac082f2d7a9-33.webp" />

## Setting Up Web Tracking Events in Your Horoshop Account

Go to the *Marketing → Marketing services* in your Horoshop account and click *Add*.

<Image align="center" width="80% " src="https://files.readme.io/37b390efb8f96ccd3777e8187539049f8ef52da1d51b0f12b3e152b8044a108a-horoshop-5.webp" />

Set up integration:

1. Enter a title.
2. Activate the *Active* checkbox.
3. Insert the tenant value from the web tracking script in the *System ID* field. Our example is `9CA53387A31449DBA5900704ECCFF2B5`.

<Image align="center" width="50% " src="https://files.readme.io/4c02c8bc8de3660f2ef63f02af1babdbfc3ce65b6bbeceeae30128664784f56b-horoshop-6y.webp" />

4. Paste the copied web tracking script in the *Tracking code* field.
5. Specify the *Before* `</body>` placement.

<Image align="center" width="80% " src="https://files.readme.io/6186f8c85f89b72e0e939260926ff787989670a6573563907eae3e65877a3b9c-horoshop-7y.webp" />

Save your settings.

The integration has been successfully configured and is ready to transfer data.

> 📘 Note
>
> The value of the **id** field obtained from the contact data is automatically set as the [external ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users).

## Request Statistics

You can view statistics on requests to create contacts and orders on the *Integrations* tab in Yespo. 

1. Go to *Settings → Integrations*.
2. Select the statistics period and click the number next to the request. You will see detailed information about received contacts and orders: the source of the contact and the history of their activity, the composition and price of the order, address and delivery method, etc.

<Image align="center" width="80% " src="https://files.readme.io/9fbb2f502ab8f453e0c40251c433b43e6f7f7d6a1abcba711dcc155b4a1990e7-horoshop-8.gif" />
