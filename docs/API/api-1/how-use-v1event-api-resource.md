---
title: Using the Generate Event API Resource
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using the Generate Event API Resource | Yespo Guide
  description: >-
    You can use the API resource Generate event to transfer any custom data like
    password reset, order data, customer website activity, etc. This article
    provides details on the various operations and parameters of the Generate
    event resource.
  robots: index
next:
  description: ''
---
Using the [Generate event](https://docs.yespo.io/reference/registerevent_1) API resource, you can send events from your website and store them in our system. These events can be used for triggering a workflow or for segmentation purposes.

> 📘 Note
>
> Version 2 API methods do not require escaping in nested JSON.

The method has the following body parameters explained in the table below.

> ❗️ Important
>
> The maximum size of content for events sent in the request body is 20 kilobytes. Please contact Support if you need to adjust the maximum size.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventTypeKey
      </td>

      <td>
        string, required
      </td>

      <td>
        Event type ID key. If no such event type exists with such a key, a new one is created.\
        All characters are allowed except \< ; ’ \\ / | " \` ' ^ ? ! , >\
        Max length: 100 symbols
      </td>
    </tr>

    <tr>
      <td>
        keyValue
      </td>

      <td>
        string
      </td>

      <td>
        Event key. Determines event uniqueness.\
        The key must contain a unique value for each contact (for example, email, phone number, external contact id, etc.)\
        If this parameter is not set, **params** must contain one of the following contact identifiers:  

        * contactId
        * externalCustomerId (see the note below)
        * email
        * phone
        * pushToken: web or mobileAll characters are allowed except \< ; ’ \\ / | " \` ' ^ ? ! , >\
          Max length: 300 symbols
      </td>
    </tr>

    <tr>
      <td>
        params
      </td>

      <td>
        array of objects
      </td>

      <td>
        List of event parameters represented as an array of "key" - "value" pairs. The parameter keys are arbitrary.\
        Used in campaigns and for creating dynamic content in messages.
      </td>
    </tr>
  </tbody>
</Table>

> ❗️ Important
>
> When passing events using the Generate event v2 method, **externalCustomerId** in **params**  is ignored if it contains the empty or null value. For example, "", " ", " ", "null", null.

You can use this API resource for sending the following requests, as described below.

## Using Product Arrays on the Example of an Abandoned Cart Event

Request example:

```json
{
    "eventTypeKey": "AbandonedCart",
    "keyValue": "2424925572",
    "params": [
        {
            "name": "cartItems",
            "value": [
                {
                    "name": "Conditioner for dry hair",
                    "price": "341",
                    "url": "https://site.com/conditioner-dry-hair",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Le Petit Olivier",
                    "tags_weight": "200",
                    "tags_oldprice": "467"
                },
                {
                    "name": "Magnolia Nobile Perfumed water",
                    "price": "2341",
                    "url": "https://site.com/catalog/perfumed-water-2-750-g",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Acqua Di Parma",
                    "tags_weight": "100",
                    "tags_oldprice": "4467"
                }
            ]
        },
        {
            "name": "recommendedItems",
            "value": [
                {
                    "name": "Shampoo for dry hair",
                    "price": "441",
                    "url": "https://site.com/shampoo-dry-hair",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Le Petit Olivier",
                    "tags_weight": "200",
                    "tags_oldprice": "467"
                },
                {
                    "name": "Magnolia Nobile Face cream",
                    "price": "1341",
                    "url": "https://site.com/catalog/face-cream-2-750-g",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Acqua Di Parma",
                    "tags_weight": "100",
                    "tags_oldprice": "4467"
                }
            ]
        },
        {
            "name": "emailAddress",
            "value": site@en.net
        }
    ]
}
```

*eventTypeKey* is a string identifier for the event type. If it did not exist before, after the first request it appears in the account, and you can see it in the *Automation* → *Event types* section.

<Image align="center" width="80% " src="https://files.readme.io/c43b9e1aac324eeecb65e948eae4997f51ef084b8f113754f0d28a97ecce17ea-image6.png" />

To view the event body, go to *Automation → Event history* and click the event.

<Image align="center" width="80% " src="https://files.readme.io/6473553c76d13de9aa0f1875d054a594f06f025fdcded185f00df07d4d255d27-image5.png" />

* **keyValue** is the event key.
* **params** are event parameters that can be used in a workflow. Their number is unlimited.

The event must contain a contact identifier, such as email, phone number, or [External ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users).

In our example, this is the email `site@ukr.net`. In the future, you need to refer to it in the workflow by writing `${emailAddress}` in the message sending block to successfully send to the email `site@ukr.net`:

<Image align="center" width="80% " src="https://files.readme.io/76b269a0dbeaddb1e2b0e3a667b365c9eee25a21432f0ea59a194e628e82f225-using-the-generate-event-api-resource-31032025-01.webp" />

The request may contain several arrays. In our example, these are two arrays — `cartItems` and `recommendedItems` — containing two products each with a set of variables `name`, `price`, `url`, `imageUrl`, `brand`, `tags_weight`, `tags_oldprice`. The names of variables are arbitrary.

Event data can be substituted into messages using velocity constructs.

To access the data, you can use a loop specifying the name of the desired array:

```json
#foreach($!item in $!data.get('cartItems'))
$!item.get('name')
$!item.get('price')
$!item.get('url')
$!item.get('imageurl')
$!item.get('brand')
$!item.get('tags_weight')
$!item.get('tags_oldprice')
#end
```

You can refer to the array elements straight with the index (order starts at 0). This method can cause errors in content substitution if an element is missing.

First element:

```json
$!data.get('cartItems').get(0).get('name')
$!data.get('array').get(0).get('price')
$!data.get('array').get(0).get('url')
$!data.get('array').get(0).get('imageurl')
$!data.get('array').get(0).get('brand')
$!data.get('array').get(0).get(''tags_weight')
$!data.get('array').get(0).get('tags_oldprice')
```

Second element:

```json
$!data.get('cartItems').get(1).get('name')
$!data.get('array').get(1).get('price')
$!data.get('array').get(1).get('url')
$!data.get('array').get(1).get('imageurl')
$!data.get('array').get(1).get('brand')
$!data.get('array').get(1).get(''tags_weight')
$!data.get('array').get(1).get('tags_oldprice')
```

The number of elements is unlimited.

> 📘 Important
>
> Variables are case-sensitive. If an email contains `$!item.get ('ImageUrl')` and the request transfers imageurl, the variable will not be inserted.

To view and check dynamic data in an email, click *Additional settings → Configuring dynamic content.*

<Image align="center" width="80% " src="https://files.readme.io/38294c77e190a0abe5802a7c057bbc114a629060da4f5e57affb27c3f3a67969-using-the-generate-event-api-resource-003.webp" />

Insert an array with dynamic data and click *View message*.

<Image align="center" width="80% " src="https://files.readme.io/70f645af245c593b26710a0cbf91f5c5a63921876d0ecf04826b1a705cf32f2f-using-the-generate-event-api-resource-004.webp" />

* In case of an error in the dynamic content substitution, check the Velocity syntax in the message.
* If you see the *Wrong Format* error, check the JSON request body.
* If there are no errors, but the data is not inserted in the preview, check whether the variables in the request and variables in the email correspond and whether variables are referred to correctly.
* If there are no errors and the data is substituted correctly, run a test by [sending an API request to the account](https://docs.yespo.io/docs/integration-with-api).

## Create or Update a Contact

Request sample:

```json
{
    "eventTypeKey": "create_contact",
    "keyValue": "site@com.net",
    "params":
    [
        {
            "name": "email",
            "value": "site@ukr.net"
        },
        {
            "name": "phone",
            "value": "380501234567"
        },
        {
            "name": "externalCustomerId",
            "value": "AV13760"
        },
        {
            "name": "json",
            "value":
            {
                "profileInputs":
                [
                    {
                        "profileInputId": 10001,
                        "value": "2020-11-23"
                    }
                ]
            }
        }
    ]
}
```

where,

* **10001** is the ID of the additional field.
* **2020-11-23** is the value of the additional field.

Check that the transferred data comply with the following requirements:

* The name and surname length is up to 60 characters.
* The phone number is in the international format. For example, +1-541-754-3010.
* The value of an additional contact field is in the required format.

If the transferred data contains errors, the system ignores the entire array and does not add or update data in the contact card.

For a workflow to run correctly, in the block *Task (Create contact/Update contact)*, specify a variable `${email}` in the field *Contact’s email* and a variable `${json}` in the field JSON.

<Image align="center" width="80% " src="https://files.readme.io/ab2af31d6c3fef8745cdf39f6a95c3ea2b5053b783dd2d6ad91ae1d3dbf42ab2-how-to-use-the-generate-event-api-03.webp" />

[Learn more about the Task block](https://docs.yespo.io/docs/popular-blocks#task)

In addition to that, the *Generate event* resource can be used to create or update a contact and to trigger a workflow that sends messages with the dynamic content. It can also be used to [send orders to the system](https://docs.yespo.io/docs/how-send-events-resource-v1event).

## Send Transactional Letters

Let's consider the example of launching a password recovery letter.

Request example:

```json
{
"eventTypeKey": "password_recovery",
"keyValue": "site@com.net",
"params": [{
"name": "EmailAddress",
"value": "site@ukr.net"
},
{
"name": "password",
"value": "12345678"
}
]
}
```

In the workflow, it is necessary to use the *Task - Send obligatory (transactional) email* block. Enter the `$!data.get('password')` variable in the letter you want to send.

<Image align="center" width="80% " src="https://files.readme.io/3f3e28c448026611eb950a64616a90280a9ca3ee4e145a8d12be7da38a141ce5-using-the-generate-event-api-resource-31032025-03.webp" />

To learn more about the *Task* block, read [this manual](https://docs.yespo.io/docs/popular-blocks#task).

## Validate Contact Data in Events

You can validate the contact data in events using the Generate event v2 API method.

To validate contact data in events, you have to set *contactJson* in `params` as a parameter `name`.

```json
{
  "params": [
    {
      "name": "contactJson",
      "value": "..."
    }
  ]
}
```

Indicate the data you want to validate in the *value* field.

**Example:**

```json
{"firstname":"...","lastname":"...","sms":"...","town":"...","timeZone":"Etc/GMT+03","languageCode":"uk","profileInputs":
[{"profileInputId":10001,"value":"..."}],"confirmed":false}
```

When you send this request using the Generate event v2 API method, REST API understands it as receiving a new contact and performs data validation.

If the data is not valid, the method returns the 400 Bad Request response. The response contains the non-valid fields and the error details.

Read [Validating event parameters](https://docs.yespo.io/docs/validating-event-parameters) to learn more.

## Enriching Contact Profile with Location by IP in Event

Using the Generate event v2 method, you can enrich the event parameters by passing the contact’s IP in params. IP must be in the IPv4 or IPv6 format.

Request example:

```json
{
  "keyValue": "john.doe@example.com",
  "eventTypeKey": "welcome",
  "params": [
    {
      "name": "email",
      "value": "john.doe@example.com"
    },
    { "name": "ip",
      "value": "192.0.2.1"
    }
    ]
```

The event will be enriched with the parameters explained in the following table.

| **Parameter** | **Description**                         |
| :------------ | :-------------------------------------- |
| countryCode   | Country 2-letter code                   |
| countryId     | Country ID in the geographical database |
| regionName    | Region name in English                  |
| regionId      | Region ID in the geographical database  |
| cityName      | City name in English                    |
| cityId        | City ID in the geographical database    |

<Image align="center" width="80% " src="https://files.readme.io/eaa0f236e574ec1a98862c1ea66d9df1f7305ecd9792afce66500cb016eb8d73-event.webp" />

> 📘 Note
>
> If the system cannot define region and city by the IP, it defines the country by *countryCode* event parameter.

The enriched event uses the contact’s location in a workflow.

Also, these values in the event parameters are used for setting or updating the contact's location data.

<Image align="center" width="80% " src="https://files.readme.io/042c76b832eb5787211c698955d53b90e66f33264fac415676682fff1624f0a6-contact-card.webp" />

> 📘 Note
>
> If the event already contains one of the following parameters, additional fields are not created and the location remains unchanged:
>
> * countryCode,
> * countryId,
> * regionName,
> * regionId,
> * cityName,
> * cityId.
