---
title: Collecting Contact Information Using Request Forms
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Collecting Contact Information Using Request Forms | Yespo Guide
  description: >-
    The document explains how to create and configure request forms in Yespo:
    collect user data, add fields, automate actions like updating contacts and
    generating events.
  robots: index
next:
  description: ''
---
Request forms allow you to collect and automatically transfer to Yespo additional information about your users, such as their birthdays, preferences, needs, etc.

<Image align="center" width="80% " src="https://files.readme.io/6bad0ae64e6e5db2d8760b8ffdde89f47f179d050d4b4b3684fcecdad542ec62-requests-1.webp" />

## Creating Request Form

Go to *Site → Widgets → Request Forms* and click the *Create request form* button.

<Image align="center" width="80% " src="https://files.readme.io/1a1004b1dce18af74afcd3e62b249bc88e3e435876f591efe2591ed161e6eb39-requests-2.webp" />

The appearance settings generally coincide with [those of other widgets](https://docs.yespo.io/docs/setting-up-widgets-for-your-site). The main difference is the need to assign additional fields to store the received information, which will be discussed below.

## Designation of Additional Fields for Data Storage

1. Click on the question form component, go to the *General* tab on the right sidebar, and click *Change*.

<Image align="center" width="80% " src="https://files.readme.io/b2394501c7a7abc6d8c533099557b8a823d13ee3165c03c4c62ccd5bf342e32d-requests-3.webp" />

2. If the corresponding field does not already exist, click *Add field* and create it (more on [creating additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields)).

<Image align="center" width="80% " src="https://files.readme.io/341437071116f7c17677cca42792a7b8a89037a14933af4d560ca313c844b235-requests-4.webp" />

After saving the settings, you will be redirected to the page with additional widget settings. The [Widgets](https://docs.yespo.io/docs/widgets) article provides more detailed information on configuring forms.

## Contact Identification and Actions after Form Submission

Submitting a request form updates contact data by **email** or **phone** IDs, if the form contains the corresponding fields. If a contact with such IDs is not found, it will be created.

If the form does not have **email** or **phone** fields, the system will search for and update the contact by **webId**.

The request form is not displayed to the contacts that are not identified. Identified contacts are those whose **webId** (cookie) has mapping. That means, the CustomerData, GeneralInfo events with data were transferred, or the contact was auto-detected. For example, when the contact clicked an email link with tags.

The double opt-in setting for [actions after form submission](https://docs.yespo.io/docs/actions-after-form-submission) is available only for forms with an **email** field. The option to add new contacts to a segment is available only for forms with **email** or **phone** fields.

### Generating Events to Start Automation

To trigger an event after filling out a form, activate the corresponding toggle in the widget parameters and select or create an event type.

<Image align="center" width="80% " src="https://files.readme.io/cb6cfb98c80c87be25d8af3712c29b6aa363becdf9719a54e8544d6f750c9990-generate-event.webp" />

The event will contain parameters corresponding to the form parameters (data is transferred from all form components except checkboxes).

Example structure:

```json
"params": [
    {
      "name": "contactId",
      "value": "string"
    },
    {
      "name": "email",
      "value": "string"
    },
    {
      "name": "phone",
      "value": "string"
    },
    {
      "name": "Personalisation key",
      "value": "string"
    }
  ]
}
```

* **contactId** — filled in automatically,
* **email** — contains a value if it is passed in the form,
* **phone** — contains a value if it is passed in the form,
* **Personalization key** — corresponds to the name of the additional contact field.
