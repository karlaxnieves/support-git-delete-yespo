---
title: NPS/Rating Widget Components
deprecated: false
hidden: false
metadata:
  title: NPS/Rating Widget Components | Yespo Guide
  robots: index
---
**NPS** (Net Promoter Score) and **Rating** widget components are used to collect feedback from website visitors and assess customer loyalty to your brand or company.

* NPS is a rating scale from 0 to 10.

<Image align="center" width="80% " src="https://files.readme.io/f0f3a200919c83308767614aaf2cf09130e7db7d9611356dea81c9dcfc147738-nps-rating-01.webp" />

* The **Rating** includes four types of responses:
  * 5 stars,
  * 1-5 Rating,
  * 3 Emojis,
  * Like/Dislike.

<Image align="center" width="80% " src="https://files.readme.io/fc8b52214956be517681f8990838b67e93e90f71ffc8b280a7046f25a07c9826-nps-rating-02.webp" />

## Settings Data Storage from Widget Components

After adding the component to the widget, select the data processing method: **Contact field** or **Event parameter**.

<Image align="center" width="80% " src="https://files.readme.io/bdf9c1d6c164793453564ad869125b9dc4ee212aa97b3f73c173bebff8254776-nps-rating-03.webp" />

The following values will be sent to the contact field or event:

* For NPS — a number from 0 to 10
* For Rating — depending on the type:
  * 5 stars / rating 1–5: a number from 1 to 5
  * 3 emojis: a number from 1 to 3
  * Yes / No: value in Yes/No format

### Contact Field

When you select this option, the widget components send data directly to the contact’s profile.

[More about storing data from widgets to contact fields >](https://docs.yespo.io/docs/storing-data-from-widgets-to-contact-fields#/)

### Event Parameter

If you select the **Event parameter** option, the system stores component values in events, not in contact fields. After you submit the form, it records all data, including the component values.

For example, a contact filled out the form with an email and phone number and selected a score of 8 in the NPS component. The event parameters will then look like this:

<Image align="center" width="80% " src="https://files.readme.io/ab3aed15bff3c35cf7afdcbe9a707470f7ca5e935274cccee93866a4cddef3ce-nps-rating-04.webp" />

Saving data from components in events allows you to:

* Build segments based on a contact’s response scores.
* Compare different responses from the same contact (for example, over time or across various forms)
* Use event data to personalize messages.

To set the event parameter:

1. Select an existing event from the list or create a new one if needed.

<Image align="center" width="80% " src="https://files.readme.io/768e1e5772be0b26ba7e45f1469bdba31a83788d24d6a18cfb92af94d4399349-nps-rating-05.webp" />

**Note**

You can use multiple components in a widget simultaneously and assign the same or different event types to each. If the form contains two components, two events will be created:

* The first event will include all contact data and the value of the first component (for example, rating the order processing speed);
* The second event will include the same contact data and the value of the second component (for example, rating the quality of support service consultation).

1. Specify the name of the event parameter in which the component’s value will be sent, or leave the default name, then click **Save**.

<Image align="center" width="80% " src="https://files.readme.io/e90c8a6d98b24f4ec18dd6e3a3276a8b05c38e66cf5a8ca4082b58a56966b4ac-nps-rating-06.webp" />

## Component settings

Component settings are the same.

On the **General** tab:

1. Set an action on click:

* Open widget page — select one of the widget pages,
* Open widget page based on answer — select a widget page for each respondent's satisfaction level.

<Image align="center" width="80% " src="https://files.readme.io/39822129d169e910b429c8919abd74a9f2cb929db5ebfb6a48b1dc88e94f6d6a-nps-rating-07.webp" />

1. Determine whether the field is required.

<Image align="center" width="80% " src="https://files.readme.io/0d5cfaedd0b571bff0f43df4e42a3dc707f8d2d9932534e9abcf87d24672a729-nps-rating-08.webp" />

On the **Styles** tab, customize the appearance of the component. For the **Rating** component, you can upload a custom icon for each response type.

<Image align="center" width="80% " src="https://files.readme.io/0efda4026a90caf96471676b1ba8f614a08fdf50cfd00b10b4572445ed5fcdcb-nps-rating-09.webp" />