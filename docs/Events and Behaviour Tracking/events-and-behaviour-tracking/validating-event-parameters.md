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

1. Create a new event or edit an existing one (See *[Events](https://docs.yespo.io/docs/events-and-behaviour-tracking)* to learn more about how to create events in Yespo).
2. Enable the *Validate parameters* slide button.
3. Click *+ Add parameter*.

<Image align="center" width="80% " src="https://files.readme.io/4b7ac9c016ed6f9985552f4d5bd6fd9491522f68a057b609b58822868c2ee1a9-validating-event_parameters-001.webp" />

4. Enter the parameter name in the corresponding field and select the *Required parameter* checkbox if the parameter is required.
5. Add other parameters as necessary, then click *Done*.

<Image align="center" width="80% " src="https://files.readme.io/fe7029ea4c32f7a02a702fd575938a2971c0b22156e8cecdd30e76a152fa1dcd-validating-event_parameters-002.webp" />

## Validating Event Parameters

Validate event parameters and structure using [Generate event](https://docs.yespo.io/reference/registerevent_1) API method. Indicate parameters in the **BODY PARAMS** array.

![BODY PARAMS](https://files.readme.io/83f4e9446c4d29f5a45a38e8577fe250b7bd4d072643add1e7328ee2fe6d0f98-image.png)

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

<Image align="center" width="80% " src="https://files.readme.io/af59509a409d9f9ca0a437a9268afc46a5cf11f22ac3699d8c696855d5e47a01-validating-event_parameters-003.webp" />

## Event requirements

### eventTypeKey

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Type
      </th>

      <th>
        Required/Optional
      </th>

      <th>
        Description
      </th>

      <th>
        Requirements
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventTypeKey
      </td>

      <td>
        String
      </td>

      <td>
        Required
      </td>

      <td>
        * *Unique identifier for the event type*\*, e.g., `PageViewed`. After the first request, it will appear in your account, and you can see it in the *Automation → Event types* section.
      </td>

      <td>
        1. All characters are allowed except \< ; ’ \ / | " \` ' ^ ? ! , >
      </td>
    </tr>
  </tbody>
</Table>

### eventParams

eventParams contain two types of information:

* [Contact Identifiers](https://docs.yespo.io/docs/customer-identifiers-and-matching) (Required). An example:

```json
- {  
     "name": "externalCustomerId",  
     "value": "a7c9f9b8-d3a2-401c-8b93-7f3d4f91bfa2"  
  }
```

* Additional event-specific parameters (Optional). An example:

```json
- {  
    "name": "cartId",  
    "value": "CART12345"  
  }
```

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Type
      </th>

      <th>
        Required/Optional
      </th>

      <th>
        Description
      </th>

      <th>
        Requirements
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Contact identifiers
      </td>

      <td>
        String
      </td>

      <td>
        Required
      </td>

      <td>
        `eventParams` **must contain a contact identifier** to determine the event's uniqueness. The priority of the parameters is as follows:

        * contactId (internal contact ID in our system);
        * externalCustomerId (internal contact ID in your system);
        * email;
        * phone;
        * pushToken (web or mobile). An event without one of these parameters **is not accepted**.	**Recommended value:** [External ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users).
      </td>

      <td>
        1. All characters are allowed except \< ; ’ \ / | " \` ' ^ ? ! , >
        2. Max. length: 300 characters
      </td>
    </tr>

    <tr>
      <td>
        Additional event-specific parameters
      </td>

      <td>
        Array of objects
      </td>

      <td>
        Optional
      </td>

      <td>
        An array of objects — lists with **key-value** pairs containing event-specific parameters.
      </td>

      <td>
        1. Params array may be empty: \[]\
           But if the array is not empty, both name and value fields must be in the array object.
        2. The value of the name parameter must be unique.
        3. Max. length of the name parameter’s value: 100 characters.
      </td>
    </tr>
  </tbody>
</Table>

[See an example of the AbandonedCart event >](https://docs.yespo.io/reference/abandonedcart-event-example)