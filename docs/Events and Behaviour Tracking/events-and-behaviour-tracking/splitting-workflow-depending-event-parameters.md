---
title: Splitting the Workflow Depending on the Event Parameters
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Splitting the Workflow Depending on the Event Parameters | Yespo Guide
  description: >-
    Learn how to split workflows based on event parameters for smarter
    automation. Discover step-by-step guidance to create dynamic, personalized
    user journeys and optimize your marketing strategies.
  robots: index
next:
  description: ''
---
*The Condition block* allows you to split the workflow depending on the parameters of the event that launched the workflow. These can be the following parameters:

* Category of the site visited by the contact
* City of residence
* Clothing size
* Product preferences
* Gender

For example, you need to send emails with selections of products for men and women, depending on gender, the value of which is passed in the event by the [Generate event](https://docs.yespo.io/reference/registerevent_1) API method:

```json
{
    "eventTypeKey": "event_name",
    "keyValue": "user@example.com",
    "params":
    [
        {
            "name": "EmailAddress",
            "value": "user@example.com"
        },
        {
            "name": "Name",
            "value": "John"
        },
        {
            "name": "lang",
            "value": "EN"
        },
        {
            "name": "gender",
            "value": "M"
        }
    ]
}
```

## Workflow Settings

1\. Create a workflow with two *Condition* blocks that check the event parameters and send the contact to the appropriate branch. An example of such a workflow:

<Image align="center" width="80% " src="https://files.readme.io/2662f926260be3d30f28083bfdb0f322654f047739a2ad0882ac428c1c4ce9cf-splitting-the-workflow-01.webp" />

2\. Set up the first *Condition* block:

1. Select [*Variable matches regular expression*](https://docs.yespo.io/docs/popular-blocks#variable-matches-regular-expression) in the *Task* name field to check the contents of the gender parameter.

2. Add the name of the validation parameter in the *name* field, in our case, it is *gender*.

3. Specify the value of the request parameter in the *pattern* field in the following format: **.\*M.\*** (male).

<Image align="center" width="80% " src="https://files.readme.io/950c63650ecc0919d46b658284b2341c7e9888dc6e4b359a747b246501e2ae9b-splitting-the-workflow-02.webp" />

> 📘 Important
>
> The case of the letter in the pattern field must match the case of the letter in the event parameters

3\. Add the second *Condition* block to the workflow with the same settings as the first one, but with the **.\*F.\*** (female) pattern.

<Image align="center" width="80% " src="https://files.readme.io/ff43e906e2667038b9c549a797feca7354679a6be4e59db3341c0884bc552ebf-splitting-the-workflow-03.webp" />

If the event parameters match the value specified in the first condition,  contacts will go along the “Yes” branch; if not, they will go to the next checkpoint.

Contacts without gender specified in the request will go through the third workflow branch.

Similar articles:

* [Substituting Email Blocks According to Contact Profile Data](https://docs.yespo.io/docs/substituting-email-blocks-according-contact-profile-data)
* [Welcome Series Segmented by Category](https://docs.yespo.io/docs/welcome-series-segmented-by-category)
