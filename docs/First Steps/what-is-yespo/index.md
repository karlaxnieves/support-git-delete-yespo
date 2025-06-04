---
title: What Is Yespo?
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: What Is Yespo? | Yespo Guide
  description: >-
    Yespo is an Omnichannel Customer Data Platform designed to enhance
    e-commerce success through advanced analytics, segmentation, automation, and
    communication tools, enabling businesses to make data-driven decisions and
    optimize marketing strategies.
  robots: index
next:
  description: ''
---
Yespo is an Omnichannel Customer Data Platform (**CDP**) made to embody the toughest ideas of enterprise-level solutions in a very clear and efficient way.

With advanced tools for **analytics**, **segmentation**, **automation**, and **omnichannel communication**, Yespo is an essential solution for e-commerce success. Our CDP ensures that your customer data remains up-to-date, structured, and actionable, empowering you to make data-driven decisions that maximize engagement and revenue.

By leveraging the core Yespo concepts described below, you can enhance your marketing efforts and drive business growth.

<Image align="center" width="80% " src="https://files.readme.io/dd4ec67fa32d02d3c80c59dbe754aa39ae12e9f63553e7919217d209acaa1627-yespo_1.png" />

## Contacts

A **Contact** represents an individual interacting with your business via your website, app, or offline store.

All customer data is stored in [Contact Cards](https://docs.yespo.io/docs/user-profile) (profiles),  which include:

* [Customer Identifiers](https://docs.yespo.io/docs/customer-identifiers-and-matching) — external ID, email, phone number, mobile, and push tokens.
* [System Fields](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system) — time zone, location, language.
* [Additional Fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) — business-specific data such as purchase history, loyalty points, or product preferences.

With a **360-degree customer view**, you can track cross-channel interactions and optimize engagement strategies.

<Image align="center" width="80% " src="https://files.readme.io/a50c3a22990d77f52cb9e97f693130f98bc3f15427352b5a67cef2d62fd96d65-Yespo_2.png" />

Closely related to Contact are three essential concepts:

* **External ID**
* **Additional Fields**
* **Contact Activity**

### External ID

The [External ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users) is a unique identifier that consolidates all customer data (email, tokens, personal details, etc.). It serves as your internal user ID, ensuring that contact profiles remain consistent and free from duplication throughout the customer lifecycle.

<Image align="center" width="80% " src="https://files.readme.io/ef74a6569bb066325ea3cdaf0e6ce4203554a8f3bb0fb9d550bf7a95bd872e46-Yespo_3.png" />

The **External ID must remain unchanged** for each customer, ensuring reliable data structuring across all interactions.

> 📘 Note
>
> Properly structured customer identification is crucial for your marketing strategy. To optimize your approach, we recommend exploring more about [customer identifiers and data matching](https://docs.yespo.io/docs/customer-identifiers-and-matching) in Yespo.

### Additional Fields

**Additional fields** are designed to store **specific contact data**, including:

* **Static or rarely changed details**: clothing size, age, gender, etc.
* **Transactional data** (e.g., total spent, last purchase date).
* **Behavioral metrics** (e.g., abandoned cart count, lifetime value, preferred brands).

[More on creating additional fields >](https://docs.yespo.io/docs/how-add-additional-contact-fields)

### Contact Activity

The **Contact activity** tab logs all customer interactions, including:

* **Order history**
* **Marketing engagement** (email opens, push notification clicks, etc.)
* [Events used for segmentation](https://docs.yespo.io/docs/how-to-use-event-segmentation)

<Image align="center" width="80% " src="https://files.readme.io/0c0d7843a5f06be8128a97beabe6c34c9b3a5c5a608bf73d8eb38eeafbe9d1c2-Yespo_4.png" />

## Workflows

A [workflow](https://docs.yespo.io/docs/introduction-to-workflows) (also known as a **Customer Journey**) is an automated sequence of actions triggered by predefined events or conditions with a particular marketing purpose. Workflows allow businesses to:

* Automate welcome series and abandoned cart reminders.
* Personalize post-purchase follow-ups and loyalty campaigns.
* Implement cross-sell and upsell strategies based on user behavior.

Yespo’s [drag-and-drop editor](https://docs.yespo.io/docs/workflow-management) makes workflow creation intuitive, ensuring seamless automation of marketing campaigns.

<Image align="center" width="80% " src="https://files.readme.io/714313739232f3ea6f63f50fae8d9805fe01d5ed0d88298538352475d5711111-Yespo_5.gif" />

## Events

[Events](https://docs.yespo.io/docs/events-and-behaviour-tracking) represent user actions within your website, app, or messages, such as viewing products,  placing orders, and opening emails. You can use system events and [configure sending custom events](https://docs.yespo.io/docs/site-activity-tracking-using-generate-events). For instance, you can transmit the `ReviewAnswered` event every time a customer provides a product review. This event can include details, also known as **parameters**,  such as the review ID, rating, response content, and response time. By tracking this data, you can personalize follow-up messages, encourage further engagement, and measure customer satisfaction effectively.

You can send event data to Yespo via:

* [API resource](https://docs.yespo.io/reference/registerevent_1) (for websites and backend services).
* [SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo) (for mobile apps).

Event data is crucial for:

* Launching and stopping workflows,
* Building segments,
* Personalizing messages,
* Filtering product recommendations.

## Segments

**Segments** group customers based on shared characteristics or behaviors, such as:

* **Demographics** (age, gender, location).
* **Engagement data** (email opens, push clicks).
* **Purchase behavior** (order history, spending patterns).

Yespo provides two segment types:

* **Lists**
* **Dynamic Segments**

### Lists

The **List** is a static segment that could be created and updated manually, via workflows, or by transferring data via API. For example, you can make a list of contacts who clicked a specific link in the email.

### Dynamic Segments

[Dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment) are a flexible tool for defining the target audience for your campaigns. Such segments automatically include contacts that match the rules specified in the segment settings. For example, you can select all customers with average order value  for over 1000 $. The most valuable data for dynamic segment creation is information from events and their parameters.

<Image align="center" width="80% " src="https://files.readme.io/7f44f116fb94a8ce7b2854bd8bcbc5b4d34e08abc88b167876bef78129e06795-yespo_6.png" />

With Yespo’s segmentation tools, you can refine audiences, apply complex filters, and integrate segments seamlessly into automated workflows.

## Messages

Effective **omnichannel communication** is key to increasing revenue. Yespo supports a variety of messaging channels, including:

* [Email](https://docs.yespo.io/docs/email-setting-up)
* [Mobile Push Notifications](https://docs.yespo.io/docs/mobile-push)
* [App Inbox](https://docs.yespo.io/docs/app-inbox)
* [In-App Messages](https://docs.yespo.io/docs/in-app)
* [Web Push Notifications](https://docs.yespo.io/docs/web-push)
* [Viber](https://docs.yespo.io/docs/viber)
* [SMS](https://docs.yespo.io/docs/sms)
* [Widgets](https://docs.yespo.io/docs/widgets)
* [Telegram](https://docs.yespo.io/docs/telegram)

Manage these channels within a single platform and choose the most suitable tool for each situation. The more relevant channels you use in your omnichannel strategy, the more effective each channel will perform.

Yespo’s advanced message editors help create [personalized](https://docs.yespo.io/docs/personalization-and-dynamic-variables), [multilingual](https://docs.yespo.io/docs/multilanguage-overview) campaigns with reusable templates.

<Image align="center" width="80% " src="https://files.readme.io/2f2423c2ba8e68efc29c6b26b5a6bc78ab2c56290e081334821bf7be5d38681c-Yespo_7.png" />

## Web Tracking

Yespo's **Web Tracking** technology is a powerful tool that enables businesses to collect, analyze, and act on user behavior in real time. By tracking website interactions, you can:

1. **Deliver Personalized Product Recommendations** based on browsing history and interactions.
2. **Trigger Behavior-Based Campaigns** based on customer actions like abandoned carts and regular demand.

Implementing Web Tracking requires two simple steps:

1. [Install the Web Tracking Script to your site](https://docs.yespo.io/docs/how-set-web-tracking-your-website)
2. [Upload Your Product Feed to Yespo](https://docs.yespo.io/docs/importing-product-feed)

Once configured, Web Tracking seamlessly integrates with your marketing automation strategy to boost engagement and conversions.

### Recommendations

Yespo’s **AI-driven Product Recommendations** increase customer engagement by automatically suggesting relevant products based on user behavior. Recommendations can be displayed on:

* [Website pages](https://docs.yespo.io/docs/recommendations-overview)
* [Mobile apps](https://docs.yespo.io/docs/recommendations-in-mobile-app)
* [Marketing channels](https://docs.yespo.io/docs/recommendations-in-media-channels)

### Behavior Triggers

**Behavioral Triggers** are automated campaigns activated by specific customer actions, such as:

* **Abandoned carts**
* **Product views**
* **Purchases of frequently reordered items**

Messages can include up to six relevant products and six additional recommended products.

<Image align="center" width="80% " src="https://files.readme.io/f71246da53e604176906db0fdd07969cddc1a4b041ce804362aca9068bd8c6d9-Yespo_8.png" />

By upgrading to the **Professional Plan**, our team will set up these automated campaigns for you, ensuring they are fully functional and ready to drive conversions. You can then customize them further to match your business needs.

You can find a complete list and detailed descriptions of behavioral triggers [at the following link](https://docs.yespo.io/docs/activation-of-behavioral-triggers).

## Tags

[Tags](https://docs.yespo.io/docs/how-add-tags) help organize messages, segments, reports, and workflows under common marketing objectives. Tagging makes it easier to filter and search different objects in your account. Tags are also used in the [One from many](https://docs.yespo.io/docs/using-one-many-block) workflow block, which automates A/B testing, diversifies triggered communication, and defines the most effective message from the pool of options.

<Image align="center" width="80% " src="https://files.readme.io/7b62ab2df05aee8833d43f5fd4b93bf86cf6f3225d7ef1afb37542bb53f8d523-Yespo_9.png" />

> 👍 Get Started Today!
>
> Take the next step in optimizing your marketing strategy with Yespo.
>
> * [Explore the Migration Guide](https://docs.yespo.io/docs/migration)
> * [Review the Quickstart Guide](https://docs.yespo.io/docs/support)