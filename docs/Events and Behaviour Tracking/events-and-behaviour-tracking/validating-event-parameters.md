---
title: Validating Event Parameters
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Validating Event Parameters | Yespo Guide
  description: >-
    Learn how to validate event parameters for accurate data tracking and
    analysis. Discover best practices to ensure reliable event data, improve
    reporting accuracy, and optimize your analytics setup.
  robots: index
next:
  description: ''
---
Events that are sent to Yespo must meet specific requirements. Otherwise, the workflows may not work, you may lose important data, etc. 

The Yespo system allows you to validate events and provide immediate feedback if event parameters contain errors. Also, the system checks that event includes the required parameters.

## Setting Required Event Parameters

Set required event parameters so the system accepts an event only if it meets the specified structure.

Steps to set up event’s structure validation:

1. Create a new event or edit an existing one (See _[Events](https://docs.yespo.io/docs/events-and-behaviour-tracking)_ to learn more about how to create events in Yespo).
2. Enable the _Validate parameters_ slide button.
3. Click _+ Add parameter_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b7ac9c016ed6f9985552f4d5bd6fd9491522f68a057b609b58822868c2ee1a9-validating-event_parameters-001.webp",
        "",
        "Add parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Enter the parameter name in the corresponding field and select the _Required parameter_ checkbox if the parameter is required.
5. Add other parameters as necessary, then click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe7029ea4c32f7a02a702fd575938a2971c0b22156e8cecdd30e76a152fa1dcd-validating-event_parameters-002.webp",
        "",
        "Required parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Validating Event Parameters

Validate event parameters and structure using [Generate event](https://docs.yespo.io/reference/registerevent_1) API method. Indicate parameters in the params array.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/36294274e84e5530b8dd360927b455ede5d0fa4b78df2491e10b00ae6ce856be-validation_3.webp",
        "",
        "Generate event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If parameters do not meet the specified structure, you will get the 400 bad request error and the required event structure in the response.

Response example:

```json
The event should have the following params: [
    {
        "name": "EmailAddress",
        "required": true
    },
    {
        "name": "Phone Number",
        "required": false
    },
    {
        "name": "Name",
        "required": false
    }
]
```

Event types with enabled parameter validation are marked with a check icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af59509a409d9f9ca0a437a9268afc46a5cf11f22ac3699d8c696855d5e47a01-validating-event_parameters-003.webp",
        "Event types with enabled parameter validation",
        "Event types with enabled parameter validation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Event requirements

### eventTypeKey

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Required/Optional",
    "h-3": "Description",
    "h-4": "Requirements",
    "0-0": "eventTypeKey",
    "0-1": "String",
    "0-2": "Required",
    "0-3": "**Unique identifier for the event type**, e.g., `PageViewed`. After the first request, it will appear in your account, and you can see it in the _Automation → Event types_ section.",
    "0-4": "1\\. All characters are allowed except \\< ; ’ \\\\ / | \" \\` ' ^ ? ! , >  \n  \n2. Max. length: 100 characters."
  },
  "cols": 5,
  "rows": 1,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


### eventParams

eventParams contain two types of information:

- [Contact Identifiers](https://docs.yespo.io/docs/customer-identifiers-and-matching) (Required). An example:

```json
- {  
     "name": "externalCustomerId",  
     "value": "a7c9f9b8-d3a2-401c-8b93-7f3d4f91bfa2"  
  }
```

- Additional event-specific parameters (Optional). An example:

```json
- {  
    "name": "cartId",  
    "value": "CART12345"  
  }
```

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Required/Optional",
    "h-3": "Description",
    "h-4": "Requirements",
    "0-0": "Contact identifiers",
    "0-1": "String",
    "0-2": "Required",
    "0-3": "`eventParams` **must contain a contact identifier** to determine the event's uniqueness. The priority of the parameters is as follows:  \n  \n- contactId (internal contact ID in our system);\n- externalCustomerId (internal contact ID in your system);\n- email;\n- phone;\n- pushToken (web or mobile). An event without one of these parameters **is not accepted**.\t**Recommended value:** [External ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users).",
    "0-4": "1. All characters are allowed except \\< ; ’ \\\\ / | \" \\` ' ^ ? ! , >\n2. Max. length: 300 characters",
    "1-0": "Additional event-specific parameters",
    "1-1": "Array of objects",
    "1-2": "Optional",
    "1-3": "An array of objects — lists with **key-value** pairs containing event-specific parameters.",
    "1-4": "1. Params array may be empty: \\[]  \n   But if the array is not empty, both name and value fields must be in the array object.\n2. The value of the name parameter must be unique.\n3. Max. length of the name parameter’s value: 100 characters."
  },
  "cols": 5,
  "rows": 2,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


[See an example of the AbandonedCart event >](https://docs.yespo.io/reference/abandonedcart-event-example)