---
title: Managing the Contact Profiles
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Managing the Contact Profiles | Yespo Guide
  description: >-
    Managing contact profiles: view, edit, and manage info, add fields, edit
    subscriptions, and track activities (campaigns, orders). Detailed steps
    included.
  robots: index
next:
  description: ''
---
The contact profiles keep all the records of each contact in our system. These records include:

- Input contact data.
- The data collected from the contact’s activities, such as interactions with your website, mobile application, campaigns, orders, and others.

In the contact profile, you can do the following:

- View and edit the profile details.
- View the contact activity.

Edit the contact’s subscription and assign additional fields. Read this [article](https://docs.yespo.io/docs/how-add-additional-contact-fields) to learn more about additional fields.

## Viewing the Contact’s Profile

To open the list of your contacts in our system, go to _Contacts → All contacts_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/36ea6c0d31908122bf47edd858a4ceddd6f09bf9c23c4b69a03ced62a4a689d0-all-contacts.webp",
        "Opening All contacts",
        "Opening All contacts"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To open the contact’s profile window:

- Click the _Contact preview_ icon on the right-hand side of the table.   
  Or,  
  Click any _blank space_ in the corresponding contact row. The contact profile window opens.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4fe4a638c3c96d85aa0759e87649a653b9c816348536ffdfffd44e9631de6e46-contact-preview-icon.webp",
        "Opening contact profile",
        "Opening contact profile"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The contact profile window has 2 tabs:

- Contact information
- Contact activity

## Contact Information Tab

This tab displays all the information about the contact entered manually or collected by our system.

You can add or update contact information using our API methods. Read [API Methods for Adding Contacts](https://docs.yespo.io/docs/api-methods-adding-contacts) to learn more.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/981190000248dd6f456d42de9932307e403bcbcb395e4d07e705b80a8c543959-managing-contact-profiles-01.webp",
        "Contact Information Tab",
        "Contact Information Tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The following table lists the information type displayed on the ‘Contact information’ tab and its description.

[block:parameters]
{
  "data": {
    "h-0": "Type",
    "h-1": "Description",
    "0-0": "Name and Surname",
    "0-1": "Contact’s name and surname. They are displayed on the top of the contact’s profile.",
    "1-0": "Email",
    "1-1": "Contact’s email address. It is possible to add only one email address.",
    "2-0": "Phone number",
    "2-1": "Contact’s phone number. It is possible to add only one phone number.",
    "3-0": "Applications",
    "3-1": "Applications that the contact installed on their devices.  \nPoint to the application name to view IDs and connected devices.",
    "4-0": "Telegram",
    "4-1": "Telegram bot ID",
    "5-0": "Mob Push",
    "5-1": "Mob push tokens of the contact. There can be several tokens for the same contact.",
    "6-0": "Web Push",
    "6-1": "Web push tokens of the contact. There can be several tokens for the same contact.",
    "7-0": "Subscription categories",
    "7-1": "Contact subscription categories. To learn more, read this [article](https://docs.yespo.io/docs/how-use-subscription-category) .",
    "8-0": "Address",
    "8-1": "Contacts address. You can pass the contact address from an order.",
    "9-0": "Location",
    "9-1": "This item contains geo-tracking data. Read the [Setting up Geotargeting](https://docs.yespo.io/docs/setting-up-geotargeting)  article to learn more.",
    "10-0": "Regional settings",
    "10-1": "Contact’s timezone and preferred language. See this [article](https://docs.yespo.io/docs/tracking-user-time-zone-and-language)  to learn more.",
    "11-0": "Segments",
    "11-1": "Segments to which the contact has been added.",
    "12-0": "Additional fields",
    "12-1": "[Additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields)  assigned for the contact."
  },
  "cols": 2,
  "rows": 13,
  "align": [
    "left",
    "left"
  ]
}
[/block]


This tab also contains information on the email address and phone number status. If the contact has been blacklisted, the system automatically records the date and the reason for blacklisting.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/384b23feae7da1657ca78300d2cfff6a0bbbd7c326f5552d9a50e7b4b89b4157-managing-contact-profiles-02.webp",
        "Blacklisted email and phone number",
        "Blacklisted email and phone number"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To learn more about blacklisted contacts, read [Contact Blacklist](https://docs.yespo.io/docs/contact-blacklist).

If the contact has reported spam or unsubscribed, the system automatically records the date and reason in the contact profile.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/225b30db169c1ecd7fa4195466adced83c21f12e79df148bf5ef1f269b89b8d0-managing-contact-profiles-03.webp",
        "Spam complained information",
        "Spam complained information"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Contact Activity Tab

The tab displays the contact's activity history in the following categories:

- All activity
- Campaigns
- Events
- Orders

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ed4dc20769f7d80d1863347ed5a42da14446c84ffacea2a6e2176ef5e691960-activity-001.webp",
        "Viewing contact activity",
        "Viewing contact activity"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To view the activities that occurred during a specific period, expand the period dropdown menu and select the corresponding period from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ee0d20e866b7998807891ff84fc0c66498db48d118a1b242bb84dd0d4510163-activity-002.webp",
        "Selecting activity period",
        "Selecting activity period"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> For the _Orders_ category, the history is available for the entire contact activity period.

Each activity contains the following information:

- Sent message, date, and status – _Campaigns_ category.
- Event names and assigned workflows – _Events_ category.
- External ID, amount, date, and order status – _Orders_ category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e7506675ffbf3e7ddf9b7b8eec2899a7579919ee658ce3186a2f8f3a9cf4511-activity-003.webp",
        "",
        "Following information"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The marking on the left-hand side of activity indicates its type and contains the following elements, which are explained in the following table:

- Color bar
- Icon

| Activity type | Color bar | Icon         |
| :------------ | :-------- | :----------- |
| Campaigns     | Green     | Channel name |
| Events        | Brown     | Flag         |
| Orders        | Red       | Shopping bag |

## Editing the Contact Profile

To edit the contact profile, click the Edit contact button on the top right-hand side of the profile. The editing window opens.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb0517931b4bf97d5fa29af2396d83d0cee03924f12d239a8fc029b21f7a3cf6-managing-contact-profiles-04.webp",
        "Switching to contact editing",
        "Switching to contact editing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the editing window, you can do the following editing, as described below.

Select the following fields and add or edit their information:

- First name and last name
- Email
- Phone number
- Contact key

Expand the Address and Location sections and enter or edit information in their fields.

> 📘 Note
> 
> You can use geotargeting to get and update the information about contact’s location. To learn more, read [Setting Up Geotargeting](https://docs.yespo.io/docs/setting-up-geotargeting).

In the _Regional settings_ section, expand the following dropdown menus and select the values from them:

- _Time zone_.
- _Language_. Read this [article](https://docs.yespo.io/docs/adding-the-preferred-language-to-the-user-profile) to learn more about setting the contact’s language.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd99cd08e92f9279f07584403aaa8db930ad31bb2a63ff3adefefd7949bbea39-managing-contact-profiles-05.webp",
        "Setting up Regional settings",
        "Setting up Regional settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To add a contact to one or several segments:

1. Click the _plus_ icon in the top bar on the right-hand side.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d192cb4eacbf6b9f6cb30d46370100b9a203ab473e6ecb1fd91bd24cc981e4b7-managing-contact-profiles-06.webp",
        "Adding segments",
        "Adding segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select or clear the checkbox beside the segment name to add or remove the contact from the segment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5002378efd20d04c65e54b91f6a7ef24725dcc36514fe7afa0ba8cc02720a590-add-segments-select-save.webp",
        "Selecting segments",
        "Selecting segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Save_.

To edit the contact information in additional fields:

1. Expand the list of fields by selecting the _upward-pointing arrow_ icon.
2. Add or select the values for the contact fields in the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62172d3586ccab443bc69e5773f406b0555adc605ff94eaf5ee823a666fa005f-managing-contact-profiles-07.webp",
        "Editing additional fields",
        "Editing additional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Read [How to Add Additional Contact Fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) to learn more about creating and adding additional fields.