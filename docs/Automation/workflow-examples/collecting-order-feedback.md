---
title: Collecting Order Feedback
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Collecting Order Feedback | Yespo Guide
  description: >-
    Receive feedback on a purchased product or service provided - set up a
    workflow for sending an email to receive feedback from your customers.
  robots: index
next:
  description: ''
---
An email campaign is a convenient and effective way to receive customer feedback.

There are four types of email surveys:

* survey inside the email
* link to form/feedback page 
* redirect to a product page
* [AMP form](https://docs.yespo.io/docs/how-create-amp-form)

Let's look at the first three ways to implement such campaigns.

## Survey Inside the Email

For a short survey, you can use the editor functionality and add answer options directly to the email:

<Image align="center" width="80% " src="https://files.readme.io/725c0ccd1c311b3d7a33837c9f568ab4489421f3b9a65c56a7244cdc33793910-image9.webp" />

Each button (survey item) should have a link to record the response, such as a thank you page.

<Image align="center" width="80% " src="https://files.readme.io/0e0f4022171d14b73c65d451fc7cd55b07b4f1ca4bac43bf642cda4acbbe2f6b-image12.webp" />

In addition to recording the clicks on certain links, you can add respondents to segments according to the answer.

For each answer option, you need to create:

* An event.
* A segment.
* A workflow.

1. Create an event in the *Automation → Event types* section by clicking on the *New event type* button:

<Image align="center" width="80% " src="https://files.readme.io/331cdad09dabcb9850ec45bf39ac8ff78c2536a8016545c300be094cc828e7f6-image3.webp" />

2. [Link the event to the button](https://docs.yespo.io/docs/how-add-scenario-button) in the email. To do this, click on the block with the button and select the event on the toolbar's left side.

<Image align="center" width="80% " src="https://files.readme.io/e3e361ad623e6583489a7c935efbda9f7dd71ab7bb74ccb8d8d42fb74a01dd43-image5.webp" />

3. Create a segment in the *Contacts → Segments* section:

<Image align="center" width="80% " src="https://files.readme.io/4d7c7bcf5e0723ed9fa718b964143e1951656c98a57845a27ccf4bd7739dd6ec-image2.webp" />

4. Create a workflow with the *Add to segment* block in the *Automation → Workflows* section. In the workflow, specify the segment you created.

<Image align="center" width="80% " src="https://files.readme.io/d0a42fce7b72e2f5cbfb7062c529d653695256713bc862fb732f578391a23255-collecting-order-feedback-001.webp" />

5. Click *Start/Stop configuration*.

<Image align="center" width="80% " src="https://files.readme.io/822cae4971554f493a1d8ffbee4d3086400e03bf10fb596906dc5ead342b2b8d-collecting-order-feedback-202.webp" />

6. Select the created event in the workflow launch conditions.

<Image align="center" width="80% " src="https://files.readme.io/c9b480efa87e8e34303a5fc3c3f14426e1a9c0f27621e05713967d4aa36a5194-image8.webp" />

7. Activate the workflow.

<Image align="center" width="80% " src="https://files.readme.io/4a7f939bc7b0e30ebb4f9b2574b6c80ad8ae36bab117399339f7019c8fc03187-collecting-order-feedback-201.webp" />

Repeat the same actions for each answer option.

The system will automatically distribute contacts according to clicks.

## Email with a Link to the Form/Feedback Page

To create an extensive survey and better understand your customers, you can add a link to the survey in your email.

<Image align="center" width="80% " src="https://files.readme.io/32dec365d39c279af5248a73aaeaf8e810e88ee3edfc5bac9eb40fc808a8e12c-image7-6.webp" />

You can choose several ways to implement the survey:

* Create a form in a third-party service. For more information on how to do this, [read the article on collecting customer feedback](https://yespo.io/blog/survey-forms-making-how-learn-more-about-your-client).
* Order a survey form from our technical support at [support@yespo.io](mailto:support@yespo.io).

## Collecting Feedback on Purchased Products

It is important to remind about the purchased products to get customer feedback.

Order data can be transferred using two API methods:

* [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1)
* [Generate event](https://docs.yespo.io/reference/registerevent_1)

Information from the request will be displayed in the email instead of variables.

<Image align="center" width="80% " src="https://files.readme.io/e84e23d7a00f751f39285e459d84448fa84b97b3affabdaf3a1559d3656af773-image11.webp" />

[Learn more about using dynamic variables >](https://docs.yespo.io/docs/using-velocity-email)

### Getting Feedback Using the Add Orders Method

The *Add orders* method allows you to use different order statuses, for example:

* INITIALIZED — for a newly created order.
* IN\_PROGRESS — for an order in the process of delivery.
* DELIVERED — for a paid and delivered order.
* CANCELLED — for a canceled order.

The event that should trigger the workflow to collect feedback is orderDELIVERED. This event is generated automatically when order data is transferred; you just need to add [a workflow](https://docs.yespo.io/docs/workflow-management).

<Image align="center" width="80% " src="https://files.readme.io/e013cf1d97ac582332fff6e11c6e8f0e136091470022fbc925c79958cde94b77-collecting-order-feedback-002.webp" />

In addition to the required *Start* and *End* blocks for each workflow, the feedback collection workflow contains the following elements:

* The *Get order* block is needed to obtain product information and order status.
* The *Timer* block sets the number of days before sending the email so that the customer has time to use the product (2-5 days, depending on the specifics of your business).
* The *Email* block sends a message. 

### Getting Feedback Using the Generate Events Method

If you do not transfer order information to the system using the *Add orders* method, you can use the *Generate events* API method to run the workflow and substitute order information in the email.

The simplest workflow consists of three blocks: *Start*, *Email*, and *End*.

<Image align="center" width="80% " src="https://files.readme.io/2381452c423210b60da6040290156766696c1cc1fb53528e3c44bba5d383cb59-collecting-order-feedback-003.webp" />

You can expand the workflow to include a check of opening the message and a reminder asking for feedback.
