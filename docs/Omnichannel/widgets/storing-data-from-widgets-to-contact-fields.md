---
title: Storing Data from Widgets to Contact Fields
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Storing Data from Widgets to Contact Fields | Yespo Guide
  description: >-
    Learn about creating subscription widgets, where you have the flexibility to
    include text input, checkbox, dropdown, and other fields.
  robots: index
next:
  description: ''
---
When creating subscription forms, you can add the following fields and send their data to mapped contact fields: 

- Text input
- Text area
- Date
- Calendar
- Checkbox
- Dropdown
- Radio

This can enrich a contact profile with data gathered in a widget to improve message personalization. 

These fields are available for all types of subscription forms:

- Inline
- Pop Up
- Floating box
- Floating bar

When a user enters data into the fields and subscribes using the widget, a new contact is created, or an existing contact is updated. 

The information selected or entered into the widget fields is added to the corresponding contact fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bc65847e56bed7e654c4e3b7c4fb235af0d7680a9da3b98e9b64447ba65500e-store_data_to_contact_field_01.webp",
        null,
        "Stored data in contact fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To learn more about creating widgets, read [Setting up Widgets for your Site](https://docs.yespo.iohttps://docs.yespo.io/docs/setting-up-widgets-for-your-site/docs/setting-up-widgets-for-your-site).

## Mapping the field data to a contact field

When you add one of the fields to your subscription form, the _Process collected data as_ sidebar opens, offering two options:

- **Contact field:** This option allows you to map the data entered into this field to a contact field that you created in your account.
- **Event parameter:** This option allows collected data processing as event parameters. 

To map the widget field to the contact field:

1. Add one of the following fields to your subscription form. 

- Text input
- Text area
- Date
- Calendar
- Checkbox
- Dropdown
- Radio

The Process collected data as sidebar opens. 

2. Select the _Contact field_ option and click Next.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5e035844205b15ab5930dc1a655ce5f61eac3c0aa269974a5c16831f04cdfdc-store_data_to_contact_field_02.webp",
        null,
        "Selecting Contact field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the contact field existing in your account that you want to map the data to.

You can add a new field, see [Adding a new field](https://docs.yespo.io/docs/storing-data-from-widgets-to-contact-fields#adding-a-new-field) to learn more.

The fields that are not included in a list are displayed at the top of the menu. To see fields in a list, expand the list by clicking the down arrow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ed1684509af3d83d808671f33006df64c54ea21a06de7e8319a9f99c838b712-store_data_to_contact_field_03.webp",
        null,
        "Adding the contact field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The field names displayed in gray cannot be added to the selected field type.

You can map the widget fields to the following types of contact fields:

[block:parameters]
{
  "data": {
    "h-0": "Widget field",
    "h-1": "Contact field type",
    "0-0": "Text input",
    "0-1": "• Text field  \n• Number  \n• Fractional number",
    "1-0": "Text area",
    "1-1": "• Text area",
    "2-0": "Date",
    "2-1": "• Date",
    "3-0": "Calendar",
    "3-1": "• Date",
    "4-0": "Checkbox",
    "4-1": "• Checkbox list",
    "5-0": "Dropdown",
    "5-1": "• Dropdown list",
    "6-0": "Radio",
    "6-1": "• Dropdown list"
  },
  "cols": 2,
  "rows": 7,
  "align": [
    "left",
    "left"
  ]
}
[/block]


After selecting the contact field for the checkbox, dropdown, or radio fields, the Edit options window opens. Edit the options as described below, then click _Done_:

- Change the names of the options. Enter the option name in the _Names of options in the widget_ column.
- Show or hide options. Enable or disable the _slide button_ in the Show option column to show or hide the option in the widget.
- Change the option position. Use the _six dots_ icon to drag and drop the option to another position.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9965bc21c37823bbe6f2a614323c7377cf43919f1be6178b8f4504728c553f3e-store_data_to_contact_field_04.webp",
        null,
        "Editing options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Adding a new field

To add a new field in the Select contact field window:

1. Click  _+ Add a field_ at the bottom of the window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/44f32c8def38422fa599d0c40af85ba5fd84d51b62af84e8b0d7f5b36e2db8bd-store_data_to_contact_field_05.webp",
        null,
        "Adding a new field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


<br />

2. In the Add a field window, select the _radio_ button beside the existing list.

Or,

Select the _radio_ button beside + Create a new list for this field and enter the list name to create a new list. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8eabc1465a2973492389498a547f528b234e9d77a40d3164b6d428315836e57b-store_data_to_contact_field_06.webp",
        null,
        "Selecting or creating a list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The personalization key is created automatically based on the list name. Point to the interrogation (?) icon to learn more.

3. Click _Next_.
4. Enter the field name and select the field type from the Field type dropdown list.

> 📘 Note
> 
> The personalization key is created automatically based on the list name. Point to the interrogation (?) icon to learn more.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a3aa3abfa9ff50087f0413baeb07c578c1059f912ad60c65b1fa6fb328ccdbd-store_data_to_contact_field_07.webp",
        null,
        "Entering the field parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Click _Done_.

## Configuring the added fields

After adding a field to your widget, you can edit its configuration in the _General_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c3e7af8a25fa793843e1da8ca5e23303f98ef0dc6f1e2d14a34192e597ed56a-store_data_to_contact_field_08.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The sections available in the _General_ tab depend on the widget type. The table below provides details about each section.

[block:parameters]
{
  "data": {
    "h-0": "Section",
    "h-1": "Description",
    "h-2": "Available for fields",
    "0-0": "Placeholder",
    "0-1": "The text entered into the _Placeholder_ field is shown as a placeholder in the field added to the widget.",
    "0-2": "• Text input  \n• Text area  \n• Dropdown",
    "1-0": "Collected data storage",
    "1-1": "This section displays the selected contact field.  \nTo choose another field, click the _Change_ button and select another field",
    "1-2": "• Text input  \n• Text area  \n• Checkbox  \n• Dropdown  \n• Radio  \n• Calendar  \n• Date",
    "2-0": "Validation",
    "2-1": "Displays validation parameters.",
    "2-2": "• Text input  \n• Text area  \n• Checkbox  \n• Dropdown  \n• Radio  \n• Calendar  \n• Date",
    "3-0": "Options",
    "3-1": "Shows the names of options in the selected field.  \nClick the _Edit_ for this widget button to edit options.",
    "3-2": "• Checkbox  \n• Dropdown  \n• Radio",
    "4-0": "Only in future",
    "4-1": "When enabled, the calendar in the widget will allow users to select only future dates.",
    "4-2": "• Calendar"
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]