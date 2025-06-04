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

* Text input
* Text area
* Date
* Calendar
* Checkbox
* Dropdown
* Radio

This can enrich a contact profile with data gathered in a widget to improve message personalization. 

These fields are available for all types of subscription forms:

* Inline
* Pop Up
* Floating box
* Floating bar

When a user enters data into the fields and subscribes using the widget, a new contact is created, or an existing contact is updated. 

The information selected or entered into the widget fields is added to the corresponding contact fields.

<Image align="center" width="80% " src="https://files.readme.io/2bc65847e56bed7e654c4e3b7c4fb235af0d7680a9da3b98e9b64447ba65500e-store_data_to_contact_field_01.webp" />

To learn more about creating widgets, read [Setting up Widgets for your Site](https://docs.yespo.iohttps://docs.yespo.io/docs/setting-up-widgets-for-your-site/docs/setting-up-widgets-for-your-site).

## Mapping the field data to a contact field

When you add one of the fields to your subscription form, the **Process collected data as** sidebar opens, offering two options:

* **Contact field:** This option allows you to map the data entered into this field to a contact field that you created in your account.
* **Event parameter:** This option allows collected data processing as event parameters. 

To map the widget field to the contact field:

1. Add one of the following fields to your subscription form. 

* Text input
* Text area
* Date
* Calendar
* Checkbox
* Dropdown
* Radio

The Process collected data as sidebar opens. 

2. Select the **Contact field** option and click **Next**.

<Image align="center" width="80% " src="https://files.readme.io/c5e035844205b15ab5930dc1a655ce5f61eac3c0aa269974a5c16831f04cdfdc-store_data_to_contact_field_02.webp" />

3. Select the contact field existing in your account that you want to map the data to.

You can add a new field, see [Adding a new field](https://docs.yespo.io/docs/storing-data-from-widgets-to-contact-fields#adding-a-new-field) to learn more.

The fields that are not included in a list are displayed at the top of the menu. To see fields in a list, expand the list by clicking the down arrow.

<Image align="center" width="80% " src="https://files.readme.io/8ed1684509af3d83d808671f33006df64c54ea21a06de7e8319a9f99c838b712-store_data_to_contact_field_03.webp" />

> 📘 Note
>
> The field names displayed in gray cannot be added to the selected field type.

You can map the widget fields to the following types of contact fields:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Widget field
      </th>

      <th>
        Contact field type
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Text input
      </td>

      <td>
        • Text field
        • Number
        • Fractional number
      </td>
    </tr>

    <tr>
      <td>
        Text area
      </td>

      <td>
        • Text area
      </td>
    </tr>

    <tr>
      <td>
        Date
      </td>

      <td>
        • Date
      </td>
    </tr>

    <tr>
      <td>
        Calendar
      </td>

      <td>
        • Date
      </td>
    </tr>

    <tr>
      <td>
        Checkbox
      </td>

      <td>
        • Checkbox list
      </td>
    </tr>

    <tr>
      <td>
        Dropdown
      </td>

      <td>
        • Dropdown list
      </td>
    </tr>

    <tr>
      <td>
        Radio
      </td>

      <td>
        • Dropdown list
      </td>
    </tr>
  </tbody>
</Table>

After selecting the contact field for the checkbox, dropdown, or radio fields, the Edit options window opens. Edit the options as described below, then click **Done**:

* Change the names of the options. Enter the option name in the **Names of options in the widget** column.
* Show or hide options. Enable or disable the **slide button** in the Show option column to show or hide the option in the widget.
* Change the option position. Use the **six dots** icon to drag and drop the option to another position.

<Image align="center" width="80% " src="https://files.readme.io/9965bc21c37823bbe6f2a614323c7377cf43919f1be6178b8f4504728c553f3e-store_data_to_contact_field_04.webp" />

## Adding a new field

To add a new field in the Select contact field window:

1. Click  **+ Add a field** at the bottom of the window.

<Image align="center" width="80% " src="https://files.readme.io/44f32c8def38422fa599d0c40af85ba5fd84d51b62af84e8b0d7f5b36e2db8bd-store_data_to_contact_field_05.webp" />

<br />

2. In the Add a field window, select the **radio** button beside the existing list.

Or,

Select the **radio** button beside **+ Create a new list for this field** and enter the list name to create a new list. 

<Image align="center" width="80% " src="https://files.readme.io/8eabc1465a2973492389498a547f528b234e9d77a40d3164b6d428315836e57b-store_data_to_contact_field_06.webp" />

> 📘 Note
>
> The personalization key is created automatically based on the list name. Point to the interrogation (?) icon to learn more.

3. Click **Next**.
4. Enter the field name and select the field type from the **Field type** dropdown list.

> 📘 Note
>
> The personalization key is created automatically based on the list name. Point to the interrogation (?) icon to learn more.

<Image align="center" width="80% " src="https://files.readme.io/8a3aa3abfa9ff50087f0413baeb07c578c1059f912ad60c65b1fa6fb328ccdbd-store_data_to_contact_field_07.webp" />

5. Click **Done**.

## Configuring the added fields

After adding a field to your widget, you can edit its configuration in the **General** tab.

<Image align="center" width="80% " src="https://files.readme.io/6c3e7af8a25fa793843e1da8ca5e23303f98ef0dc6f1e2d14a34192e597ed56a-store_data_to_contact_field_08.webp" />

The sections available in the **General** tab depend on the widget type. The table below provides details about each section.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Section
      </th>

      <th>
        Description
      </th>

      <th>
        Available for fields
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Placeholder
      </td>

      <td>
        The text entered into the **Placeholder** field is shown as a placeholder in the field added to the widget.
      </td>

      <td>
        • Text input
        • Text area
        • Dropdown
      </td>
    </tr>

    <tr>
      <td>
        Collected data storage
      </td>

      <td>
        This section displays the selected contact field.
        To choose another field, click the **Change** button and select another field
      </td>

      <td>
        • Text input
        • Text area
        • Checkbox
        • Dropdown
        • Radio
        • Calendar
        • Date
      </td>
    </tr>

    <tr>
      <td>
        Validation
      </td>

      <td>
        Displays validation parameters.
      </td>

      <td>
        • Text input
        • Text area
        • Checkbox
        • Dropdown
        • Radio
        • Calendar
        • Date
      </td>
    </tr>

    <tr>
      <td>
        Options
      </td>

      <td>
        Shows the names of options in the selected field.
        Click the **Edit** for this widget button to edit options.
      </td>

      <td>
        • Checkbox
        • Dropdown
        • Radio
      </td>
    </tr>

    <tr>
      <td>
        Only in future
      </td>

      <td>
        When enabled, the calendar in the widget will allow users to select only future dates.
      </td>

      <td>
        • Calendar
      </td>
    </tr>
  </tbody>
</Table>