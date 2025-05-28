---
title: Welcome Series Segmented by Category
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Welcome Series Segmented by Category | Yespo Guide
  description: >-
    Learn how to create a Welcome Series Segmented by Category to engage new
    users with personalized messages. Tailor your workflows based on user
    preferences and drive meaningful interactions from the start.
  robots: index
next:
  description: ''
---
In cases where subscribers select a specific subscription category, such as gender, age, city, or product preferences, you may need to set up the appropriate [welcome series](https://docs.yespo.io/docs/how-create-welcome-email-series).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f8168baa9ac6317ec9f66480d515e4ef088494b884abb619d58b4eaf0a81cd0-welcome-series-segmented-by-category-01.webp",
        "",
        "Clothing store"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Consider an example of setting up welcome series for male and female.

> 📘 Important
> 
> Before creating a welcome series:
> 
> 1. [Set up a workflow](https://docs.yespo.io/docs/subscription-form-configuration#setting-up-the-workflows) for double opt-in.
> 2. Create a welcome workflow for each subscription form; then, when you make changes to one workflow, it will not affect the work of others.
> 3. Create welcome emails for different categories of subscribers:
> 
> - for male,
> - for female,
> - for contacts that did not specify gender.

##  Setting Up a Workflow with Data Validation from the Gender Field

Use the workflow when passing subscriber data by the [Subscribe contact](https://docs.yespo.io/reference/subscribecontact-1) API resource. The system saves the data in additional fields and uses it for validation before running the workflow.

You can see additional fields in your account settings on the _Additional fields_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f52c84e6810b1f5df4486673c02674ea41d97cb056c53b17c404cf165f77ff9b-welcome-series-segmented-by-category-02.webp",
        "",
        "Additional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click on the _Personal Information_ heading to open a list of standard fields. The gender of the contact is stored in the additional _Gender_ field; in our case, it is ID 4. You can [recreate this field](https://docs.yespo.io/docs/how-add-additional-contact-fields) if you previously deleted it. Copy the field ID and its case-sensitive value to customize the workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9944b1da0b50a2a7bdedc04d635db1e083bdf5abec9ab957fb8ab5a6092042ec-welcome-series-segmented-by-category-03.gif",
        "",
        "Field list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> ❗️ Important
> 
> When checking the additional field, the values “m” and “M” (“f” and “F”) will be considered different. The value in the contact field must match the value in the workflow parameters.

### Workflow creation

1. Go to _Automation → Workflows → New workflow._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc2046c57202e7e7d2660cf1010968b64c171a76232e624794e396e21cab69b3-welcome-series-segmented-by-category-04.webp",
        "",
        "Creating workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Put in the workflow’s name and add a [tag](https://docs.yespo.io/docs/how-add-tags) (optionally).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc0d9e85d5ca992efced7bb35a3ed755b22eec947d47ba0ed17e679c6c890ad2-welcome-series-segmented-by-category-05.webp",
        "",
        "Workflow name and description"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. Add blocks _Start_ and _Task_; select the _[Confirm contact](https://docs.yespo.io/docs/popular-blocks#confirm-contact)_ task type. The welcome chain will start after the subscriber confirms their email in the Double Opt-in email.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69b2468a67464b08f33919e05ba8f4f111dbc57c1bd84e10e1a0542af9cf20fe-welcome-series-segmented-by-category-06.webp",
        "",
        "Adding block Start  - \"Confirm contact\""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Add the block _Task ([Get contact](https://docs.yespo.io/docs/popular-blocks#get-contact))_ to get contact data. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e7da5e61c11e0e6429698f88e5063d76b817b99002cab7b12978423ed6a70808-welcome-series-segmented-by-category-07.webp",
        "",
        "Adding block Start  - \"Get contact\""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Add Condition block and configure its settings:

- Select the task name _Variable matches regular expression_.
- In the _name_ field, indicate the _smartMessageJson_ system variable, in which information about a contact from the _Get contact_ block is transmitted.
- Indicate the  _**.\*"4":"m".\***_  value in the pattern field, where _4_ is the gender field ID, and _m_ is a variable corresponding to the _male_ value; the system will check the contact data for compliance with this value.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf32f9d1c05bb955c242238d7c6a5f12e93262e9493a9b059e3cb7cf3d9bc381-welcome-series-segmented-by-category-08.webp",
        "",
        "Adding Condition block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. For the next check of the additional field value, copy the _Condition_ block and indicate the regular expression   _**.\*"4": "f".\***_   in the pattern field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d06de6478086c5928a715b3dce454ecae571f38054fa7c3c3b36065a41b65f3-welcome-series-segmented-by-category-09.webp",
        "",
        "Adding Condition block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


All contacts that do not meet the specified conditions (the value of the field is not equal to “m” or “f”) will follow the third branch of the workflow.

7. Add emails ([_Email_](https://docs.yespo.io/docs/message-blocks) block) and a delay in sending messages ([_Timer_](https://docs.yespo.io/docs/time-blocks#timer) block) to each branch, as when setting up a regular welcome series.

8\. Finish each branch with the [_End_](https://docs.yespo.io/docs/popular-blocks#end) block.

The welcome workflow for different subscribers’ categories will look as follows:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e636b99cb996d5708a6ad84d69f3b521f469ed4b0301446d78d5e5621035efd5-welcome-series-segmented-by-category-10.webp",
        "",
        "Welcome workflow for different subscribers’ categories"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Similar articles:

- [Substituting Email Blocks According to Contact Profile Data](https://docs.yespo.io/docs/substituting-email-blocks-according-contact-profile-data)
- [Splitting the Workflow Depending on the Event Parameters](https://docs.yespo.io/docs/splitting-workflow-depending-event-parameters)