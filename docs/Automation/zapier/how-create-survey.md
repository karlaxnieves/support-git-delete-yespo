---
title: Building a Customer Loyalty Survey
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Building a Customer Loyalty Survey | Yespo Guide
  description: >-
    Email surveys can help you collect feedback from your subscribers and
    customers. In our CDP, you can create surveys with links to external sites
    or create dynamic surveys with the AMP form.
  robots: index
next:
  description: ''
---
It is much cost-efficient to retain an existing client than to acquire a new one. That's why customer satisfaction is among the top priorities for all brands. And a survey is one of the ways to find how your customers feel about your product or service.

Automation of customer research is especially important for enterprise ecommerces with big customer bases. It helps run multi-stage surveys and quickly respond to changes in customer attitude and loyalty.

Through integration with <a rel="nofollow" href="https://stripo.email/" target="_blank">Stripo.email</a> and <a rel="nofollow" href="https://zapier.com/" target="_blank">Zapier</a>, our CDP enables you to automate any customer research strategy, be it feedback on the shopping experience, a review of the bought product or a classic NPS (NetPromoter Score) survey.

## 1. Create a survey form.

Create a survey in the applicable communication channel. [Add tags](https://docs.yespo.io/docs/how-add-tags), for example, NPS or survey for convenient management within the system.

You can create a survey in two ways:

* Create a form on an external platform (for example, Google Forms) and [add a link](https://yespo.io/blog/how-create-survey-google-forms-and-add-it-email) to it to the email.
* Create a dynamic survey in our editor using a ready block with an [AMP form](https://docs.yespo.io/docs/how-create-amp-form). It will allow the user to take the survey straight in the email.

> 🚧 Important
>
> To send AMP content, you need to [register with Google as a dynamic sender](https://yespo.io/blog/how-apply-sending-amp-powered-emails-within-gmail).

<Image align="center" width="80% " src="https://files.readme.io/430716c0e1a1d97b4ac1a426af4dd339212eb2281337de7481f212d2aed77d85-image7.webp" />

If you need help, please contact to our support team, and our designers will help you create a survey form based on your corporate style.

To do this, you need to provide a list with questions and answer options. To simplify form filling, use skip logic for your survey. Offer users to answer questions based on the answers they've already given. For example, if the user answers “No” to the question “Do you use Product A,” they won’t be shown questions about its price or technical characteristics due to their irrelevance.

## 2. Send the event to our platform

Set up a transfer of the [event](https://docs.yespo.io/docs/creating-events) that will trigger the workflow with a survey. Such an event can be sent from a CRM after an order confirmation call or after order confirmation on the website.

The event should transfer the parameters that will be used to identify the user and the order, for example:

* Contact email address;
* Phone number;
* Physical shop address;
* Call center manager’s SIP number, etc.

<Image align="center" width="80% " src="https://files.readme.io/e7eeb597fc0df7658111ae6a7218607f71c8756662ef43ca4c04454adff98dd6-building-customer-loyalty-survey-001.webp" />

## 3. Create a workflow.

Go to Au*tomation → Workflows* and click *New workflow*. [Create a workflow](https://docs.yespo.io/docs/workflow-management) and set the launch conditions.

You can create a basic workflow with a message block only.

<Image align="center" width="80% " src="https://files.readme.io/3d51d8e877a81d95ada7b7887273eb9fc01d084dc6011dc998c775b5a94bde25-building-a-customer-loyalty-survey-01.webp" />

You can create a more complex workflow with additional conditions. For example, if you send a survey and a follow-up reminder, you can [create a dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment) that will include contacts who respond to the first survey request and fill the form in it.

For this segment, you may add the following conditions:

* Events → Delivery → Tag → NPS;

<Image align="center" width="80% " src="https://files.readme.io/d4a2cd454551c542d5c9d5bb3dbd3acfaa4e328bbad24b67ec9fae9e5807db0f-building-customer-loyalty-survey-002.webp" />

* Delivery during 7 last days.

<Image align="center" width="80% " src="https://files.readme.io/370080fa51f926ba915a5c0e9b3c216458c87169683be1451ec46f4eeea0c682-building-customer-loyalty-survey-003.webp" />

> 📘 Note
>
> To use events as conditions for dynamic segments you need to subscribe to [Segmentation by Events](https://docs.yespo.io/docs/how-to-use-event-segmentation). To subscribe, please contact to our support team.

Build a workflow with the *Included in segment?* condition and select the created segment in the settings on the right.

<Image align="center" width="80% " src="https://files.readme.io/fef8af72b31405608a5e938a6104f38d038d56ee4364c00af3a23861312fb035-building-a-customer-loyalty-survey-02.webp" />

## 4. Collect responses.

Survey responses are collected and stored in Stripo.email. You can download them as a .csv file or [export to oup CDP or other external sources through Zapier](https://docs.yespo.io/docs/integration-zapier).

### 4.1 Set up a service in Stripo.

1. Sign in to your Stripo account.
2. Go to *Data → Services* and click *Create service*.

<Image align="center" width="80% " src="https://files.readme.io/0079f54f0ef5f28b94f13b66ab56bed700d28d4551827a3b52afe229e3f31b3f-image12.webp" />

3. Fill in *General Information*. The Identifier and URL are generated automatically.
4. Enable *Stripo storage*.

<Image align="center" width="50% " src="https://files.readme.io/192664a3f23a6ee13a66677274ed2906be7bf2d911109fa489efd06ac7ab5e6c-image3.webp" />

### 4.2 Set up integration with external resources through Zapier.

1. Enable *External storage resources*.

<Image align="center" width="50% " src="https://files.readme.io/0a38454a77a4484ccf6f7270c7c2d55a885bd65e30ca3649857d219eecfd18dc-how-to-use-webhooks.webp" />

2. To add a webhook, go to your <a rel="nofollow" href="https://zapier.com/" target="_blank">Zapier</a> account and click *MAKE A ZAP*.

<Image align="center" width="40% " src="https://files.readme.io/967bdcb884eac6c449a75d327844b295f9c948f3a6ac56fb380b1b6beb862f40-image5.webp" />

3. Click *Webhook*.

> 📘 Note
>
> Webhooks are available only for subscribers of the Premium pricing plan.

<Image align="center" width="80% " src="https://files.readme.io/d1c5f9d2c514d30b37ae1bf207544ad35655de56b45fc493dc150d68769bf9c3-select-webhook.webp" />

4. Click *Continue to continue*. In the new window, click *Custom Webhook URL*, which will create zap.
5. In *Choose app & event → Trigger Event*, select *Catch Hook* and click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/b6114d99070d5753a52999101a57e99607b136a63cab44d11029643440d45598-image19.webp" />

6. In *Set up trigger → Custom Webhook URL*, copy the generated link.

<Image align="center" width="80% " src="https://files.readme.io/a66cc400b7dcfc8ff06b191bd0cc39dda2d16143b544ac35aa0fbe1b276b0d09-image2.webp" />

7. Insert it in *Webhook URL* in Stripo.

<Image align="center" width="50% " src="https://files.readme.io/fe4b59535dcfb590b8e018ef8842b279088f642934111092d5c91ba5d16eaad2-insert-the-generated-webhook.webp" />

8. In *Action → Choose app & event* select our platform.
9. In *Action Event*, select *Send Event*.

<Image align="center" width="80% " src="https://files.readme.io/40a02ec2f6a8f19422607a92f8713dab578e66aee0a347464ff8e7e43cb9f1ca-select-send-event.webp" />

10. Click *Continue* and sign in to your account.
11. In *Set up action*, fill in fields:

* *Event Type*. Event type in our platform that is assigned to the survey. Enter a name and create the event in tha system or enter the name of the existing one.
* *Event Key*. Contact ID that can check whether the event has been triggered for the contact (email, phone number, ContactID).
* *Parameters*. Values that correspond to the questions and answers of your survey.

<Image align="center" width="80% " src="https://files.readme.io/e70c17172b7d63cd8766cf9d7cbde71c72b62769277e0fd0562a65826fcb3cb2-fill-in-fields.webp" />

12. Turn the zap on.

<Image align="center" width="80% " src="https://files.readme.io/576d33be4adc2191db58ad21e15d85174910bdc8cadcc0281b5b21a7dd186028-image8.webp" />

When the survey form is filled, the zap will send to your account an event with the user's responses.

<Image align="center" width="80% " src="https://files.readme.io/f88738439919dcba65c41dfff588364809e76a81f7b50dd028f3d285f54efc79-building-customer-loyalty-survey-004.webp" />

## 5. Use responses.

### 5.1 Create a workflow based on user responses.

Create a workflow that will be triggered by the event sent to the system upon survey completion.

<Image align="center" width="80% " src="https://files.readme.io/ee2ff3ee682c7914b74c0eafeee6232d2df6657a3e4038f1cc5d379bc7971ad9-building-customer-loyalty-survey-005.webp" />

You can check the variable that corresponds to the answer that is of particular interest to you. For example, take the question "Did we help solve your problem?” the answer to which is transferred in the *Solved parameter*.

<Image align="center" width="80% " src="https://files.readme.io/190916707430417c1944c8ad903b3021000284fe7bff4ff5f5c42d85213651f2-building-a-customer-loyalty-survey-03.webp" />

If its value isn’t Yes, an extra workflow path will start for customers whose problem wasn’t solved. For example, you can send them an apology email with a bonus. Or you can email the responsible manager who can use the user's phone number and call center SIP number to find the right dialogue in the CRM and assess it.

### 5.2 Segment your contacts.

You can build communication strategies for each contact group by creating dynamic segments using segmentation by events. You can add different conditions based on the responses you receive.

<Image align="center" width="80% " src="https://files.readme.io/49c54b909c4f8a106b28390cd05e7b88523268472729b945eff26eaf18b20117-image4.webp" />

Regular surveys can help you identify growth points and weaknesses of your business. You may want to pay attention to product or service quality or review the bonus system for employees who contribute to customer loyalty. Our CDP helps automate your customer research and eventually improve customer satisfaction and retention.
