---
title: Custom User Fields
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Custom User Fields | Yespo Guide
  description: >-
    The document provides a guide on creating and managing additional fields in
    Yespo for audience segmentation and marketing automation, detailing steps to
    create new lists, add fields, and choose field types to personalize content
    and enhance segmentation.
  robots: index
next:
  description: ''
---
[Additional fields](https://docs.reteno.com/docs/usage-of-additional-fields) contain all the information we know about each contact. You can use it for audience segmentation and marketing automation.

You can create a new list of fields or add new fields to the existing lists. Let's go step by step and create a new Additional info list.

## Step 1. Creating a new list

1. Click the **New list of fields** button.

2. Type the list name in the **Name** field.

The personalization key is generated automatically based on the given name. This key is used in your content to refer to this list. We recommend using a descriptive name in capital Latin letters with no spaces or special symbols.

3. Click the *Save* button.

<Image align="center" width="80%" src="https://files.readme.io/db9d5f7-image9.png" />

## Step 2. Adding fields to the existing list

Now you can add any additional field by clicking the plus button.

<Image align="center" width="80%" src="https://files.readme.io/3448c8d-image2.png" />

Specify the name of the field. By default, the field type is saved in the *Text box* type.

<Image align="center" width="80%" src="https://files.readme.io/5848da3-image8.png" />

If you need to set another field type, go to step 3.

## Step 3. Choosing the field type

Depending on the type of the contact data to be stored, the following field types are available in Reteno:

<Image align="center" width="smart" src="https://files.readme.io/47b20df-image4.png" />

### Text box

Used for text characteristics of the contact. The maximum allowed number of characters in the field is one thousand both letters and integer numbers. Special characters (for example, % ^ \* | \~ \{) are not supported. 

### Text area

The field can contain up to five thousand characters, both letters and integer numbers. Special characters are not supported. 

### Number

Can only contain integer values between -2147483647 and 2147483647.

<Image align="center" width="smart" src="https://files.readme.io/5d14180-image3.png" />

### Fractional number

This field can contain integers and fractions. 

### Date

A field to store the date and time. API values are passed in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format. Date format: YYYY-MM-DD.

A Regular date option is used to determine a creation date, anniversary, etc.

<Image align="center" width="80%" src="https://files.readme.io/91e0622-image5.png" />

Select the *Regular date* checkbox to use it for creating [dynamic segments](https://docs.reteno.com/docs/creating-dynamic-segment):

<Image align="center" width="80%" src="https://files.readme.io/41bd105-image10.png" />

### Date with time

The supported format: YYYY-MM-DDTHH:mm

### Dropdown list

It contains predefined values, useful for storing the gender, status or language data of a subscriber.

> 📘 Important
>
> Do not use the dot character in the field’s name. For example, MARITAL.STATUS.

<Image align="center" width="smart" src="https://files.readme.io/533e8de-image6.png" />

### Checkbox list

This type of field is ideal for characterizing contact's preferences, activity, or professional skills when you need to enter multiple values.

<Image align="center" width="smart" src="https://files.readme.io/421a810-image1.png" />

To write or update the **Checkbox list** field using the [Add/update contacts](https://docs.reteno.com/reference/contactsbulkupdate-1) API method, transfer the field ID in the fields array and specify the values separated by commas:

```json
"fields": [{

"id": 87166,

"value": "Chinese "

 }]
```

Also, don't forget to specify the ID in the `customFieldsIDs` object — the list of identifiers for additional fields to be updated. Only those additional contact fields whose IDs are specified in this list are updated. 

The result of a query for the Favorite dishes field:

<Image align="center" width="80%" src="https://files.readme.io/5463cfc-image7.png" />

Creating lists and adding fields for your segments allows you to make advanced segmentation of your contacts. This allows you to personalize the content and send relevant messages.

> 📘 Important
>
> After creating an additional field, the system takes some time to synchronize until the field becomes available for using via the [API](https://docs.reteno.com/reference/). The procedure may take 1 hour.
