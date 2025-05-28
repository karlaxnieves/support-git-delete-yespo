---
title: Setting Up an Abandoned Cart Workflow
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up an Abandoned Cart Workflow | Yespo Guide
  description: >-
    To set up and manage an abandoned cart workflow, you need to create an
    abandoned cart email, segment, and workflow, then launch and test the
    workflow, and finally view reports to assess performance.
  robots: index
next:
  description: ''
---
To set up and manage an abandoned cart workflow, you need to:

1. Create an abandoned cart email.
2. Create a segment.
3. Create a workflow.
4. Launch the workflow.
5. Test triggered emails.
6. View reports.

## 1. Create an Abandoned Cart Email

* Go to *Messages* and click *Create email*. In *Basic*, select the template *Abandoned Cart* and edit it as needed.

<Image align="center" width="80% " src="https://files.readme.io/9fd301c7ae249988585478639a6438bf504df1a6a9191e69a74513a2a345d8fc-setting-up-abandoned-cart-workflow-001.webp" />

* Add to the product blocks basic variables (product image, name and price) so that the data on abandoned and recommended items can be automatically added to the email when it’s generated personally for each contact. This data will be taken from the data source you’ve previously uploaded to the system.

Read a [full guide on how to add dynamic variables to emails](https://docs.yespo.io/docs/introduction-to-velocity).

You can choose any other template from *Gallery* or use your custom template and edit them as needed. This way, make sure you specify all the variables for the block with abandoned products and recommended products if you have it.

* Create a data source and assign it to the email. The abandoned cart template typically contains two blocks with products – abandoned items and recommended items. You need to create different data sources for each of them.

If you have added your custom variables, make sure they also correspond to the parameters of the data source so that the content is added properly to the email.

Read a [full guideline on how to create a data source and assign it to the email](https://docs.yespo.io/docs/how-set-product-recommendations-email).

We recommend adding to your abandoned cart emails a corresponding tag (for example, cart). This will allow a faster search of emails and triggers and more convenient report assessment.

<Image align="center" width="80% " src="https://files.readme.io/7829859789bf9d84dd12fbf202ef485b183f62dc7267d32bb2cdb6bab85214cd-setting-up-abandoned-cart-workflow-002.webp" />

## 2. Create a Segment

> 📘 Note
>
> To create segments based on product events and online store events, you need to [setting up web tracking](https://docs.yespo.io/docs/web-tracking-overview) in your account.

Before creating the workflow, you need to create a segment that will include all contacts who have added products to their cart but left without completing the purchase.

* Go to *Contacts → Segments*, click *Add segment* and choose *Dynamic*. Enter the name and optionally purpose and tags, and click *Next*.
* In *Include*, click *Add condition* and select the following conditions: *Product events → Abandoned browses → All*. Change *last weeks* to 24 *last hours*.

<Image align="center" width="80% " src="https://files.readme.io/1fe50ef08ed040fcbfffa53d82f4bd483aca9ff7c590476284d47e65df73c178-setting-up-abandoned-cart-workflow-003.webp" />

* In *Exclude*, click *Add condition* and select the following conditions: *Online store event → Online orders → All*. Change *last weeks* to 24 *last hours*.

<Image align="center" width="80% " src="https://files.readme.io/68b70bd5a3826b5484e71c1b740e446728e76f44dc47ebb23e63b868efb651e5-setting-up-abandoned-cart-workflow-004.webp" />

Your segment should look as follows. Click *Done*.

<Image align="center" width="80% " src="https://files.readme.io/30cb10fb807cfdeaf8d247b3e31c1f135f2c047ba7e3f4348e8761ab1a883b64-setting-up-abandoned-cart-workflow-005.webp" />

## 3. Create a Workflow

* Go to *Automation → Workflows* and click *New workflow*. Create a workflow with the following blocks: *Start, Email, End*.

For the block *Email*, in *Message*, select the created abandoned cart email. In *Contact ID*, enter *$\{ContactId}*.

<Image align="center" width="80% " src="https://files.readme.io/2c978d0a65e0f44c52a0cd1c39c47671d632dc5104a6c272baf6d2859fea131f-setting-up-an-abandoned-cart-workflow-01.webp" />

## 4. Launch the Workflow

* Go to *Automation → Workflows*, select the created abandoned cart workflow and click *Start/Stop configuration*.

<Image align="center" width="80% " src="https://files.readme.io/e9e6cdfe9de492a8deeb10dddffb6e0eb0428c0f912682fab42fe8def9ca52ae-abandoned-cart-201.webp" />

* Click *Regular* and in *Segment* select the created abandoned cart segment. Leave the default start date (that is the day of configuration).
* In *Start schedule*, select once an hour.
* In *Process unique events*, select *start no more than once in 7 days*. Click *Apply*.

<Image align="center" width="80% " src="https://files.readme.io/12c59687c29028a15fca41a2cd3a89b2e553b40e57214fa328414efbeb38f300-abandoned-cart-202.webp" />

> 🚧 Important
>
> The condition *Once in every 7 days* restricts sends to the same contact. Based on it, one contact can receive only one abandoned cart email per week. Such restriction helps minimize spam complaints and unsubscribes because people don’t like receiving reminders after each site visit. However, you can specify any condition you like.

* Click *Activate* and confirm the action. The workflow status will change to active.

<Image align="center" width="80% " src="https://files.readme.io/9d2d0a9dc9ad6fe0e53cff1b6eb7a46cdbf92bf482dbe2d0a83ee0adb2ddb4d8-abandoned-cart-203.webp" />

Such configuration launches the workflow once an hour. After the launch, the segment is refreshed and new contacts are added to it.

## 5. Test Triggered Emails

* To test triggers for an abandoned cart, go to the corresponding website (which data sources you’ve uploaded in the system), from the email or browser, sign in if needed, view products, add them to the cart, and leave without completing the purchase.
* To check whether the system tracked the triggered action, go to your personal profile → *Settings → Data sources* and click the data source you’ve assigned to the abandoned cart email.

<Image align="center" width="80% " src="https://files.readme.io/d8b3c5885abe2c71bed7dbe06f35dec64c60a49c0b518e2c0843086fe6282a44-setting-up-abandoned-cart-workflow-006.webp" />

* In *Contact*, enter your email address. If the action was recorded, you’ll see the items you've added to the cart.

<Image align="center" width="80% " src="https://files.readme.io/ab4e584be220cbbf1cff52b3f1821074e9a9943f17ed90011a62f66a267dd2a6-image10.webp" />

You can send a test abandoned cart email to your address in 2 ways:

* **As a single test email**. Go to *Messages*, select the corresponding template, click *Test*, and send the email to your address. You can send the test email to several addresses.

<Image align="center" width="80% " src="https://files.readme.io/842b1167e38395a6b22a9aa1c562d58c181b8e652b4e39b87c6de8d38dc0f3ca-setting-up-abandoned-cart-workflow-009.webp" />

* **From the workflow**. Go to the created workflow and add there the *Task* block. In *Task name*, select *Get contact*. In *ContactId*, enter `${ContactId}`.

<Image align="center" width="80% " src="https://files.readme.io/ce8967d7ca4d3649b49ce8c1603cc0cdeee95368b343542a664ad4fde01782ae-setting-up-an-abandoned-cart-workflow-04.webp" />

* In the workflow general list, click the menu on the right and select *Launch one time*. In *ContactId*, enter test contact’s ID (go to C*ontacts → All contacts* to copy it) and click *Start*.

<Image align="center" width="80% " src="https://files.readme.io/177044d84b798a21e6688edb3b285aa3cfa7df05f5a0cb6ef74abcbd4125a408-abandoned-cart-204.webp" />

## 6. View Reports

To see reports on single emails (tests), go to *Campaigns → Single reports* and select the necessary email. Hover over the message title or click it to view a full version. You’ll be able to see what email was generated and what products were added to the blocks with variables.

<Image align="center" width="80% " src="https://files.readme.io/514c77764099ec50d1dcf378876a145fd155bbc4ec908353ff70e8db80ba4056-setting-up-abandoned-cart-workflow-007.webp" />

To see reports on campaigns sent from the workflow, go to *Campaigns → Reports* and click the necessary campaign.

<Image align="center" width="80% " src="https://files.readme.io/38353dfd6ca6262b257e862589f2749ed1aeb9fe2b1f9817b1d9b541dd6d1c48-setting-up-abandoned-cart-workflow-008.webp" />

Here, you can see statistics of campaign performance like opens, clicks, results by domain, etc. You won’t be able to see the generated blocks as each contact will receive their own version.
