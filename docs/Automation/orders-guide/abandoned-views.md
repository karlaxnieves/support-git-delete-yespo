---
title: Setting Up an Abandoned Browse Workflow
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up an Abandoned Browse Workflow | Yespo Guide
  description: >-
    To set up and manage an abandoned browse workflow, you need to create an
    email, segment, and workflow, launch and test the workflow, and view reports
    to track performance.
  robots: index
next:
  description: ''
---
To set up and manage an abandoned browse workflow, you need to:

1. Create an abandoned browse email.
2. Create a segment.
3. Create a workflow.
4. Launch the workflow.
5. Test triggered emails.
6. View reports.

## 1. Create an Abandoned Browse Email

* Go to *Messages* and click *Create email*. In *Basic*, select the template *Abandoned Browse* and edit it as needed. This template contains all basic variables (product image, name, price) by default. If you need any additional variables (for example, contact name) add them manually (see the below guideline).

A variable is used to add customized details to your emails at the moment when they are generated. For example, when you send an abandoned browse email, the variables *image, name* and *price* will be automatically completed with data from the data source you’ve previously uploaded to the system.

<Image align="center" width="80% " src="https://files.readme.io/6e8f906bd4e307b1c0d7792893b8a7c5e512f854c0511df6270bc3218b5bcc2b-setting-up-abandoned-browse-workflow-001.webp" />

You can choose any other template from *Gallery* or use your custom template and edit them as needed. This way, make sure you specify all the variables for the block with recently viewed products and recommended products if you have it.

* Create a data source and assign it to the email. The abandoned browse template typically contains two blocks with products – abandoned browse items and recommended items. You need to create different data sources for each of them.

If you have added your custom variables, make sure they also correspond to the parameters of the data source so that the content is added properly to the email.

> 🚧 Important
>
> You can show up to 3 items in the block with recently viewed products.

Read a [full guideline on how to create a data source and assign it to the email](https://docs.yespo.io/docs/how-set-product-recommendations-email).

We recommend adding to your abandoned browse emails a corresponding tag (for example, browse). This will allow a faster search of emails and triggers and more convenient report assessment.

<Image align="center" width="80% " src="https://files.readme.io/52a6ae22f0d7afaf9e591c1d0f086a5b5d0b1808acfaacb741fb33e48af82e8b-setting-up-abandoned-browse-workflow-002.webp" />

## 2. Create a Segment

> 📘 Note
>
> To create segments based on product events and online store events, you need to [setting up web tracking](https://docs.yespo.io/docs/web-tracking-overview) in your account.

Before creating the workflow, you need to create a segment that will include all contacts who have abandoned the browse on your site.

* Go to *Contacts → Segments*, click *Add segment* and choose *Dynamic*. Enter the name and optionally purpose and tags, and click *Next*.
* In *Include*, click *Add condition* and select the following conditions: *Product events → Abandoned browses → All*. Change *last weeks* to 24 *last hours* .

<Image align="center" width="80% " src="https://files.readme.io/789cda38258bdedc45ece7ec166a0aca9b5ef8d95b3128de92e53eb0aaf178e8-setting-up-abandoned-browse-workflow-003.webp" />

* In *Exclude*, click *Add condition* and select the following conditions: *Online store event → Online orders → All*. Change *last weeks* to 24 *last hours* .

<Image align="center" width="80% " src="https://files.readme.io/ebc253899d381c434af3157a3e255bae1c5b2fb886a41b70c6068355d92cb17b-setting-up-abandoned-browse-workflow-004.webp" />

Your segment should look as follows. Click *Done*.

<Image align="center" width="80% " src="https://files.readme.io/f11e9275bb93cf1534a622f79c8a31762ed2749887103986f4c8de7ee8f6de11-setting-up-abandoned-browse-workflow-005.webp" />

## 3. Create a Workflow

* Go to *Automation → Workflows* and click *New workflow*. Create a workflow with the following blocks: *Start, Email, End*.

**Email**

For the block *Email*, in *Message*, select the created abandoned browse email. In *Contact ID*, enter *$\{ContactId}*.

<Image align="center" width="80% " src="https://files.readme.io/ed6c55de0be1cfec4502cd45954ab8816063e9bef6579f74f98376d7869095c7-setting-up-an-abandoned-browse-01.webp" />

> 📘 Note
>
> For the period of the preliminary trigger testing, consider adding in *Contact’s email* your own email address. This way, you’ll receive abandoned browse emails to your Inbox and will be able to test them.

## 4. Launch the Workflow

* Go to *Automation → Workflows*, select the created abandoned browse workflow and click *Start/Stop configuration*.

<Image align="center" width="80% " src="https://files.readme.io/0687cfcfd941154337422e4d4a53df42c9059a0224dabce04c30ae4f4e6ca7ad-abandoned-browse-201.webp" />

* Click *Regular* and in *Segment* select the created abandoned browse segment. Leave the default start date (that is the day of configuration).
* In *Start schedule*, select *once an hour*.
* In *Process unique events*, select *start no more than once in 7 days*. Click *Apply*.

<Image align="center" width="80% " src="https://files.readme.io/a1dbeb8e0898f247b61119b457f076e5beeb86a3ebb77c487a4e0e89ec480a93-abandoned-browse-202.webp" />

> 🚧 Important
>
> The condition *Once in every 7 days* restricts sends to the same contact. Based on it, one contact can receive only one abandoned browse email per week. Such restriction helps minimize spam complaints and unsubscribes because people don’t like receiving reminders after each site visit. However, you can specify any condition you like.

* Click *Activate* and confirm the action. The workflow status will change to active.

<Image align="center" width="80% " src="https://files.readme.io/0007cc7f61b61018a8cfe82a82b05df4893afc4b4372a0b807a7db3dbeb84032-abandoned-browse-203.webp" />

Such configuration launches the workflow once an hour. After the launch, the segment is refreshed and new contacts are added to it. The workflow is launched to the refreshed segment 60-120 minutes after a user visited the site

## 5. Test Triggered Emails

* To test triggers for an abandoned browse, go to the corresponding website (which data sources you’ve uploaded in the system), from the email or browser, sign in if needed, view products and leave without adding them to the cart.
* To check whether the system tracked the triggered action, go to your personal profile → *Settings → Data sources* and click the data source you’ve assigned to the abandoned browse email.

<Image align="center" width="80% " src="https://files.readme.io/e35d8d634d5514e666ce8e29a056764ae716c5d575125e9d15a6f5347b0bf80a-setting-up-abandoned-browse-workflow-006.webp" />

* In *Contact*, enter your email address. If the action was recorded, you’ll see the items you've browsed.

<Image align="center" width="80% " src="https://files.readme.io/19455ee49d5948f57f52d3cee3b20f0053050ab9d030dd08a1a32b19ad69d478-image7.webp" />

You can send a test abandoned browse email to your address in 2 ways:

* **As a single test email**. Go to *Messages*, select the corresponding template, click *Test*, and send the email to your address. You can send the test email to several addresses.

<Image align="center" width="80% " src="https://files.readme.io/1b65ab2939d613b85688894c0e7e2f96b2a8cb246aea0fb5f33cc8bd95339b44-setting-up-abandoned-browse-workflow-007.webp" />

* **From the workflow**. Go to the created workflow and add there the *Task* block. In *Task name*, select *Get contact*. In *ContactId*, enter *$\{ContactId}*.

<Image align="center" width="80% " src="https://files.readme.io/672e2204e6bc3b0891d6654180857fb203dd62c623a909f983d276a1cd342a55-setting-up-an-abandoned-browse-04.webp" />

* In the workflow general list, click the menu on the right and select *Launch one time*. In *ContactId*, enter test contact’s ID (go to *Contacts → All contacts* to copy it) and click *Start*.

<Image align="center" width="80% " src="https://files.readme.io/db5e5e173d78fc09a9204196977a2bec55484941a1d5abd4bd821935f2a54c5e-abandoned-browse-204.webp" />

## 6. View Reports

To see reports on single emails (tests), go to *Campaigns → Single reports* and select the necessary email. Hover over the message title or click it to view a full version. You’ll be able to see what email was generated and what products were added to the blocks with variables.

<Image align="center" width="80% " src="https://files.readme.io/7600845e5ffcfbf3079b24878c4ebffd30b1988c43d3b5cd0f8c026f9c0f6bfe-setting-up-abandoned-browse-workflow-008.webp" />

To see reports on campaigns sent from the workflow, go to *Campaigns → Reports* and click the necessary campaign.

<Image align="center" width="80% " src="https://files.readme.io/2910a57cce2070da6d98d6d8b2d09ac03619f39d7be0cfa5eb5fa5c898d19311-setting-up-abandoned-browse-workflow-009.webp" />

Here, you can see statistics of campaign performance like opens, clicks, results by domain, etc. You won’t be able to see the generated blocks as each contact will receive their own version.
