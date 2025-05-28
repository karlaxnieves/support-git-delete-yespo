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

- Go to _Messages_ and click _Create email_. In _Basic_, select the template _Abandoned Browse_ and edit it as needed. This template contains all basic variables (product image, name, price) by default. If you need any additional variables (for example, contact name) add them manually (see the below guideline).

A variable is used to add customized details to your emails at the moment when they are generated. For example, when you send an abandoned browse email, the variables _image, name_ and _price_ will be automatically completed with data from the data source you’ve previously uploaded to the system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e8f906bd4e307b1c0d7792893b8a7c5e512f854c0511df6270bc3218b5bcc2b-setting-up-abandoned-browse-workflow-001.webp",
        "Abandoned browse template in our editor",
        "Abandoned browse template"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can choose any other template from _Gallery_ or use your custom template and edit them as needed. This way, make sure you specify all the variables for the block with recently viewed products and recommended products if you have it.

- Create a data source and assign it to the email. The abandoned browse template typically contains two blocks with products – abandoned browse items and recommended items. You need to create different data sources for each of them.

If you have added your custom variables, make sure they also correspond to the parameters of the data source so that the content is added properly to the email.

> 🚧 Important
> 
> You can show up to 3 items in the block with recently viewed products.

Read a [full guideline on how to create a data source and assign it to the email](https://docs.yespo.io/docs/how-set-product-recommendations-email).

We recommend adding to your abandoned browse emails a corresponding tag (for example, browse). This will allow a faster search of emails and triggers and more convenient report assessment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52a6ae22f0d7afaf9e591c1d0f086a5b5d0b1808acfaacb741fb33e48af82e8b-setting-up-abandoned-browse-workflow-002.webp",
        "Tag added to the template",
        "Tag in email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 2. Create a Segment

> 📘 Note
> 
> To create segments based on product events and online store events, you need to [setting up web tracking](https://docs.yespo.io/docs/web-tracking-overview) in your account.

Before creating the workflow, you need to create a segment that will include all contacts who have abandoned the browse on your site.

- Go to _Contacts → Segments_, click _Add segment_ and choose _Dynamic_. Enter the name and optionally purpose and tags, and click _Next_.
- In _Include_, click _Add condition_ and select the following conditions: _Product events → Abandoned browses → All_. Change _last weeks_ to 24 _last hours _.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/789cda38258bdedc45ece7ec166a0aca9b5ef8d95b3128de92e53eb0aaf178e8-setting-up-abandoned-browse-workflow-003.webp",
        "Add conditions to a segment",
        "Add conditions to a segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In _Exclude_, click _Add condition_ and select the following conditions: _Online store event → Online orders → All_. Change _last weeks_ to 24 _last hours _.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ebc253899d381c434af3157a3e255bae1c5b2fb886a41b70c6068355d92cb17b-setting-up-abandoned-browse-workflow-004.webp",
        "Exclude conditions from a segment",
        "Exclude conditions from a segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Your segment should look as follows. Click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f11e9275bb93cf1534a622f79c8a31762ed2749887103986f4c8de7ee8f6de11-setting-up-abandoned-browse-workflow-005.webp",
        "Dynamic segment for an abandoned browse workflow",
        "Ready dynamic segment "
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 3. Create a Workflow

- Go to _Automation → Workflows_ and click _New workflow_. Create a workflow with the following blocks: _Start, Email, End_.

**Email**

For the block _Email_, in _Message_, select the created abandoned browse email. In _Contact ID_, enter _${ContactId}_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed6c55de0be1cfec4502cd45954ab8816063e9bef6579f74f98376d7869095c7-setting-up-an-abandoned-browse-01.webp",
        "Settings for the Email block",
        "Settings for the Email block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> For the period of the preliminary trigger testing, consider adding in _Contact’s email_ your own email address. This way, you’ll receive abandoned browse emails to your Inbox and will be able to test them.

## 4. Launch the Workflow

- Go to _Automation → Workflows_, select the created abandoned browse workflow and click _Start/Stop configuration_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0687cfcfd941154337422e4d4a53df42c9059a0224dabce04c30ae4f4e6ca7ad-abandoned-browse-201.webp",
        "Trigger configuration",
        "Trigger configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Click _Regular_ and in _Segment_ select the created abandoned browse segment. Leave the default start date (that is the day of configuration).
- In _Start schedule_, select _once an hour_.
- In _Process unique events_, select _start no more than once in 7 days_. Click _Apply_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a1dbeb8e0898f247b61119b457f076e5beeb86a3ebb77c487a4e0e89ec480a93-abandoned-browse-202.webp",
        "Trigger settings",
        "Triggers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 🚧 Important
> 
> The condition _Once in every 7 days_ restricts sends to the same contact. Based on it, one contact can receive only one abandoned browse email per week. Such restriction helps minimize spam complaints and unsubscribes because people don’t like receiving reminders after each site visit. However, you can specify any condition you like.

- Click _Activate_ and confirm the action. The workflow status will change to active.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0007cc7f61b61018a8cfe82a82b05df4893afc4b4372a0b807a7db3dbeb84032-abandoned-browse-203.webp",
        "Start the launch",
        "Start"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Such configuration launches the workflow once an hour. After the launch, the segment is refreshed and new contacts are added to it. The workflow is launched to the refreshed segment 60-120 minutes after a user visited the site

## 5. Test Triggered Emails

- To test triggers for an abandoned browse, go to the corresponding website (which data sources you’ve uploaded in the system), from the email or browser, sign in if needed, view products and leave without adding them to the cart.
- To check whether the system tracked the triggered action, go to your personal profile → _Settings → Data sources_ and click the data source you’ve assigned to the abandoned browse email.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e35d8d634d5514e666ce8e29a056764ae716c5d575125e9d15a6f5347b0bf80a-setting-up-abandoned-browse-workflow-006.webp",
        "Data sources",
        "Data sources"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In _Contact_, enter your email address. If the action was recorded, you’ll see the items you've browsed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19455ee49d5948f57f52d3cee3b20f0053050ab9d030dd08a1a32b19ad69d478-image7.webp",
        "Data source for the abandoned browse email",
        "Data source "
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can send a test abandoned browse email to your address in 2 ways:

- **As a single test email**. Go to _Messages_, select the corresponding template, click _Test_, and send the email to your address. You can send the test email to several addresses.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b65ab2939d613b85688894c0e7e2f96b2a8cb246aea0fb5f33cc8bd95339b44-setting-up-abandoned-browse-workflow-007.webp",
        "How to send a test email",
        "Test email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **From the workflow**. Go to the created workflow and add there the _Task_ block. In _Task name_, select _Get contact_. In _ContactId_, enter _${ContactId}_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/672e2204e6bc3b0891d6654180857fb203dd62c623a909f983d276a1cd342a55-setting-up-an-abandoned-browse-04.webp",
        "How to send a test email from the workflow",
        "Test email from the workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In the workflow general list, click the menu on the right and select _Launch one time_. In _ContactId_, enter test contact’s ID (go to _Contacts → All contacts_ to copy it) and click _Start_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db5e5e173d78fc09a9204196977a2bec55484941a1d5abd4bd821935f2a54c5e-abandoned-browse-204.webp",
        "Workflow options",
        "Workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 6. View Reports

To see reports on single emails (tests), go to _Campaigns → Single reports_ and select the necessary email. Hover over the message title or click it to view a full version. You’ll be able to see what email was generated and what products were added to the blocks with variables.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7600845e5ffcfbf3079b24878c4ebffd30b1988c43d3b5cd0f8c026f9c0f6bfe-setting-up-abandoned-browse-workflow-008.webp",
        "Reports for single campaigns",
        "Reports for single campaigns"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To see reports on campaigns sent from the workflow, go to _Campaigns → Reports_ and click the necessary campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2910a57cce2070da6d98d6d8b2d09ac03619f39d7be0cfa5eb5fa5c898d19311-setting-up-abandoned-browse-workflow-009.webp",
        "Reports for triggered campaigns",
        "Reports for triggered campaigns"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Here, you can see statistics of campaign performance like opens, clicks, results by domain, etc. You won’t be able to see the generated blocks as each contact will receive their own version.