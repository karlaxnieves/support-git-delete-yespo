---
title: Contact Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Contact Blocks | Yespo Guide
  description: >-
    Learn about Contact Blocks. Explore block types like Update Custom Fields,
    Add to Segment, and Remove from Segment to manage audience data and
    segmentation effectively.
  robots: index
next:
  description: ''
---
Special blocks for removing/adding a contact to segments or updating static data in the contact fields that you specify.

Contains three block types:

- Update custom fields
- Add to segment
- Remove from segment

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/564a33cbb5c460ca580ab7d660fcca357c0b2576ee23d3dca2cfcb8a2f329811-contact-blocks-001a.webp",
        "Contact Blocks",
        "Contact Blocks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Block Parameters

Each block contains basic and advanced parameters.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d147c7b1885f1e9230088b250abbf62f88c9e85ec41266dd722e010380a392da-contact-blocks-301.webp",
        "Common block parameters: Email, Contact ID, Phone",
        "Common block parameters: Email, Contact ID, Phone"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


List of basic parameters:

| Parameter      | Configuration                                                                                                  | Blocks                              |
| :------------- | :------------------------------------------------------------------------------------------------------------- | :---------------------------------- |
| Segment        | In this field, select the segment to which the contact will be added or from which the contact will be removed | Add to segment, Remove from segment |
| Updated fields | Select the fields to update the contact.                                                                       | Update custom fields                |

> 📘 Note
> 
> - You can add or remove a contact only from a list segment.
> - After removal, the contact remains in the system.

Read about the use cases for advanced parameters in a separate [article](https://docs.yespo.io/docs/advanced-workflow-block-parameters).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e1482f45e675fb4645ebde0b4bc144e8c00cb038f46f0104b23219d217007496-contact-blocks-302.webp",
        "Advanced parameters",
        "Advanced parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Update Custom Fields

[Custom fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) contain information about your contacts, such as the number of orders, favorite brands, etc. The _Update custom fields_ block automates contact data updates. When this block is activated in a workflow, it searches for a contact in the system and updates the specified fields.

To add fields that need to be updated:

1. Open the “_\+ Add field_” list and select the one you want to update or find it via search.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19296fe009fed872bd5c164ff4858f5f56f8e7efd4a1d503e6f5aa7984fbd736-update-fields1.webp",
        "Add field",
        "Add field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Custom fields are grouped into lists you create.

2. Enter a static field value or a dynamic variable in the _Value_ line.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/165f0e5ce1ab56d5be407c33149454369570ad13dbeca9df02cca11b0095b90b-update-fields2.webp",
        "Value",
        "Value"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If the additional field type is numeric, select the operator:

- **"="** — the field will be assigned the value transmitted in the block;
- **“+”** — the value transmitted in the block will be added to the existing value in the field; if the result is greater than the maximum value of the field range, its maximum permissible value will be written.
- **“-”** — the value transmitted in the block will be subtracted from the existing value in the field; if the result is less than the minimum value of the field range, its minimum permissible value will be written.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d535bb73e59fc9ea4cf96dfc3155ae62a99b02e464a2e4055b8a433778a43c8-update-fields3.webp",
        "Operators",
        "Operators"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. To add more rules, repeat steps 1 and 2.
4. Save the workflow.

The system validates the added fields and their values. If validation fails, an error message is displayed.

To delete the created rule from the block settings, click the trash can icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba77a98563d32fa3921a29d956fceebba22d2e33231a2113fb77839553e95849-update-fields4.webp",
        "Delete rule",
        "Delete rule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]