---
title: Sending Yespo Widget Events to Google Analytics
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Yespo events to Google Analytics | Yespo Guide
  description: >-
    Learn how to integrate Yespo forms with Google Analytics 4 (GA4)  to track
    widget interaction events on your website.
  robots: index
next:
  description: ''
---
You can send the event data related to the interaction of users with your Yespo widgets to your Google Analytics (**GA**) account.

Yespo supports the <a rel="nofollow" href="https://support.google.com/analytics/answer/10269537?hl=en" target="_blank"> Universal Analytics</a> and Google Analytics 4 scripts for tracking events on your website.

> 🚧 Important
>
> It is recommended to install the Google Analytics 4 script, since the Google Universal Analytics property will stop processing data starting on July 1, 2023 (July 1, 2024, for Analytics 360 properties).

You have to install the script, using one of the following methods:

* [Setting up GA4 script for a website](https://docs.yespo.io/docs/integrating-widgets-with-ga#setting-up-ga4-script-for-a-website) (directly into the website code).
* [Setting up GA4 in GTM](https://docs.yespo.io/docs/integrating-widgets-with-ga#setting-up-ga4-in-gtm).

After that, you have to [enable exporting the widget event data to Google Analytics](https://docs.yespo.io/docs/integrating-widgets-with-ga#enabling-widget-event-data-exporting-to-ga).

The entry point for events depends on the method you use to install the script:

* If there is GoogleAnalytics3 (`ga`), send into it.
* If there is `dataLayer` and there is `gtag` and dataLayer has at least one `G-\*` tag:
  1. Then call `gtag` with parameters (`send_to` is added) for each `tag id`.
  2. Otherwise, we write to `dataLayer`.

## Setting Up GA4 Script for a Website

To set up the Google Analytics GA4 script for a website:

1. In your GA account, select the **Admin** icon to open the GA settings.

<Image align="center" width="80% " src="https://files.readme.io/9f970cd1d3ccf8a2d838e406b3542dd71a1139184026f10266e468918d0cfbd9-ga4-events-yespo-001.webp" />

2. Click **Create → Property**.

<Image align="center" width="80% " src="https://files.readme.io/c535eba2b801019f18a4d3df2b9db306c47ea15dff12bec23249a7ddae6a9a6d-ga4-events-yespo-002.webp" />

3. In the **Property** setup, enter the **property name**, select the **country**, the **time zone** and the **currency**, then click **Next**.

<Image align="center" width="80% " src="https://files.readme.io/597b025e289041471e1f95983aa6a31a444950f27db1c59b8ad776a3474f7e28-ga4-events-yespo-003.webp" />

4. Describe your business  — indicate the industry category and company size.

<Image align="center" width="80% " src="https://files.readme.io/5865debff53b3fcba5927bbf2dab5e1c6302952b6df2873d2610f37070227382-ga4-events-yespo-004.webp" />

5. Choose your business objectives and click **Create**.

<Image align="center" width="80% " src="https://files.readme.io/cca73c9ffdfece54092c880934c03947c8396624f4a15cd6eecafe9807d48f21-ga4-events-yespo-005.webp" />

6. In your created property menu, select the **Web** platform.

<Image align="center" width="80% " src="https://files.readme.io/93e3a994f7ef4c433b0df82ff1cf21e7e218a1a27b6f0a5b0572a3d072c9790d-ga4-events-yespo-006.webp" />

Enter the **website URL** and the **stream name** in the corresponding boxes, then click **Create & continue**.

<Image align="center" width="80% " src="https://files.readme.io/7ba616cb0a471d94a26115892f1dbb472a7cf52aa4697f422533a989e9ad257c-ga4-events-yespo-007.webp" />

In the **Web stream details** menu, click the **copy** icon beside the **Measurement ID**.

<Image align="center" width="80% " src="https://files.readme.io/b606a590106c08dc6d442f94714c75849b02a2f91870ebf1ee126e93db0bc394-ga4-events-yespo-008.webp" />

9. Go to your site and insert the following code after the `<head>` tag, where substitute `MEASUREMENT_ID` with the one copied in the previous step.

```javascript
<!-- Google Analytics -->
   <!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id={MEASUREMENT_ID}"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', '{MEASUREMENT_ID}');
</script>
```

## Setting Up GA4 in GTM

Before proceeding to setting up GA4 in GTM, you have to:

1. Create a GTM account and a container following these <a rel="nofollow" href="https://support.google.com/tagmanager/answer/6103696" target="_blank">instructions</a>.

2. Follow the GTM <a rel="nofollow" href="https://developers.google.com/tag-platform/tag-manager/web?hl=en#standard_web_page_installation" target="_blank">standard web page installation</a> instructions.

To set up Google Analytics 4 (GA4) in Google Tag Manager (GTM):

1. Follow steps 1 to 6 described in the [Setting up GA4 script for a website](https://docs.yespo.io/docs/integrating-widgets-with-ga#setting-up-ga4-script-for-a-website) section.
2. In Tag Manager, select **Tags** in the left-hand side menu and click **New** to create a new tag.

<Image align="center" width="80% " src="https://files.readme.io/55f08ac06e730979ec540f971a44b4e565a1339eaff0f8156652020a7d59b7c8-ga4-events-yespo-009.webp" />

3. In the window, enter the **tag name**, set the following **tag configuration** and **triggering**, then click **Save**:

* Select **Google Analytics: GA4 Event** as Tag Type.
* Enter the **measurement ID** copied in step 7 of this \[instruction]\(#Setting up GA4 script for a website).
* Select **All pages** for Firing Triggers.

<Image align="center" width="80% " src="https://files.readme.io/c6ff4968807d9b90d8fd2ae88b8cc61991b51741f927d9a4a5327592df3658ee-ga4-events-yespo-010.webp" />

4. In the left-hand side menu, select **Triggers** and then **New** to create a new trigger.

<Image align="center" width="80% " src="https://files.readme.io/e9fa1a0cc3e2c81c006909f28a32b3a0268f1087abab310fae704be01e814525-ga4-events-yespo-011.webp" />

5. In the slide-out window, enter the **trigger name** and click the **Trigger Configuration** pane.

<Image align="center" width="80% " src="https://files.readme.io/9dc4de4f3c9c20952c67f14323c54e09a0f51eb19ffb9ac3d006cd7e9d98f470-ga4-events-yespo-012.webp" />

6. Set the following configuration in the trigger configuration window, then click **Save**:

* Select **Custom Event** as Trigger Type.
* Enter `yespo` as Event name.
* Select **All Custom Events** for the trigger to fire on.

<Image align="center" width="80% " src="https://files.readme.io/7b16319a45f3cb6835ae59ff12003fc23af5358dc579e2457743c0e29303db18-ga4-events-yespo-013.webp" />

7. Go to **Variables** in the left-hand side menu, and select **New** in the User-Defined Variables pane.

<Image align="center" width="80% " src="https://files.readme.io/c9e2ea18e0577612e422230ad30e01e175ead5a81516a06a10cd96cc762e70f9-ga4-events-yespo-014.webp" />

8. In the slide-out window, enter **configuration name** and click the **Variable Configuration** pane.

<Image align="center" width="80% " src="https://files.readme.io/4da56762c4be37da5c944fd7084d0e6b2cf3533999e9a7675a896bffc9bbd11f-ga4-events-yespo-015.webp" />

9. Set the following variable configuration, then click **Save**:

* Variable Type
* Data Layer Variable Name
* Data Layer Version

<Image align="center" width="80% " src="https://files.readme.io/dd2335076b4c953b29c7d27ff32e7da4e7d549e40458402108ffaf5017c61c04-ga4-events-yespo-016.webp" />

You have to create 3 variables with the following parameters:

| Variable Type           | Data Layer Variable Name | Data Layer Version |
| :---------------------- | :----------------------- | :----------------- |
| **Data Layer Variable** | `eventAction`            | Version 2          |
| **Data Layer Variable** | `eventCategory`          | Version 2          |
| **Data Layer Variable** | `eventLabel`             | Version 2          |

10. Go to **Tags** in the left-hand side menu, and create a new tag with the following configuration, then click **Save**:

* Select **Google Analytics: GA4 Event** as Tag Type.
* Select the **tag you created at step 3** as Configuration Tag.
* Enter `yespo`as the event name.
* In Event Parameters, use the parameters and their values created in steps 8 and 9.
* In **Firing Triggers**, select **Yespo event**.

<Image align="center" width="80% " src="https://files.readme.io/bc05741ec61f126db72dcb736240919030bc27c39a6d1660b20b8183a4b1a133-ga4-events-yespo-017-1.webp" />

11. Click **Submit** on the top panel.

<Image align="center" width="80% " src="https://files.readme.io/f9f216f741043597e9623d55730ba58ec76fdeee2925537707608bf6fefc1b42-ga4-events-yespo-018-1.webp" />

## Enabling Widget Event Data Exporting to GA

To enable the widget data transfer:

1. In your Yespo account, click **Site** → **Widgets**, and select the widget type in the left-hand side menu.

<Image align="center" width="80% " src="https://files.readme.io/f9170ecdefb7632e46e155a29b0886f835430f2f661fd874018ab213dfd16848-ga4-events-yespo-019.webp" />

2. Select the widget, which events you want to export.
3. In the widget menu, select **Integrations** and enable the **Export data to Google Analytics** slide button.

<Image align="center" width="80% " src="https://files.readme.io/bd489a1f2cb246ca2bca2b19c93a4ee14a973f2a17dd34641768ca06de014565-ga4-events-yespo-020.webp" />

All the event data collected for that widget will be passed automatically to your GA account.

## Viewing the Real-time Analytics

To view the real-time analytics in your GA account: 

1. Select **Reports** → **Realtime** in the left-hand side menu.

<Image align="center" width="80% " src="https://files.readme.io/038d9070bb6f0470f8d2bc8b987c069aa8a215ead65d8ec53f1d09d175255030-ga4-events-yespo-021.webp" />

2. In the Event count by Event name pane, Select **yespo** in the **Event name** column.

The list of event parameters displays. Click them to see the events.

<Image align="center" width="40% " src="https://files.readme.io/8fa6f9f6a41ac3706be154362d79a205b03b14eb7d6f80620ad108d873425642-ga4-events-yespo-022.webp" />

The highlighted parameters are explained in the following table.

| Parameter     | Description                                                                                                                                                |
| :------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| eventAction   | It contains the events as described in [Event categories and actions](https://docs.yespo.io/docs/integrating-widgets-with-ga#event-categories-and-actions) |
| eventCategory | Widget type                                                                                                                                                |
| eventLable    | Widget ID                                                                                                                                                  |

## Event Categories and Actions

GA displays Yespo events in a table as shown below.

<Image align="center" width="80% " src="https://files.readme.io/757a0de89b8c1a2d97a9202e808c56b12497dd265039dac2ea9f651671b3b653-GAWdget46.webp" />

The **Event Category** column contains the description of a widget/form type, as described in the following table.

| Widget/form type | Description            |
| :--------------- | :--------------------- |
| BUILT\_IN        | Inline widget/form     |
| DETACHED         | Pop-ups                |
| FLOATING\_BOX    | Floating box, informer |
| LAUNCHER         | Launcher               |
| CONTENT\_LOCKER  | Content locker         |

The *Event Action* column in GA contains the action type made on a widget. The event actions are explained in the table below.

| Event Action                | Description                                                                                     |
| :-------------------------- | :---------------------------------------------------------------------------------------------- |
| LauncherShow\_\[ID]         | The launcher button displays on a website.                                                      |
| LauncherClick\_\[ID]        | The launcher button clicked.                                                                    |
| FormShow\_\[ID]             | The form is displayed on a website.                                                             |
| FormClose\_\[ID]            | A site visitor closed the form.                                                                 |
| FormButtonClick\_\[ID]      | A site visitor clicked the form button.                                                         |
| FormClick\_\[ID]            | A site visitor clicked anywhere within the form.                                                |
| FormStartFilling\_\[ID]     | A site visitor started filling up the form.                                                     |
| FormFinish\_\[ID]           | A site visitor completed the subscription form (clicked “Subscribe”, no form validation errors) |
| FormSuccessSubscribe\_\[ID] | Form filling up status (subscription success)                                                   |
| FormAlreadySubscribe\_\[ID] | Form filling up status (already subscribed)                                                     |
| FormErrorSubscribe\_\[ID]   | Form filling up status (subscription error)                                                     |

The \[ID] part of the events for a specific widget sending its data to GA has the following structure: `f(form)\{id}v(variant)\{id`}, where `f(form)\{id}` is the form ID and `v(variant)\{id}` is the form variant ID.

For example, FormShow\_f781v781 in your GA table means that the form with the ID of 781, and the variant ID of 781 was displayed on a site.

The form ID is displayed in Yespo, on the Widgets page in the ID column.

<Image align="center" width="80% " src="https://files.readme.io/66e6c48b139ee859ae94f83cc04e8e2c306252eb9e54c02ec008775ab0898186-ga4-events-yespo-023.webp" />