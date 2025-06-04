---
title: Getting Started With API
excerpt: Overview of API functionality
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## What Is an API?

An API allows two independent software components to exchange information.

## Authentication

### Basic Authentication

Yespo’s API uses [HTTP Basic Access Authentication](http://en.wikipedia.org/wiki/Basic_access_authentication). You can [generate an API key](https://yespo.readme.io/reference/api-keys) and use it for authentication.\
With API keys, the external components can access your Yespo account without transmitting the password.

> ❗️
>
> The API key has access to your Yespo account. Keep it secure and don’t expose it publicly in insecure communication channels.

To access your Yespo account resources with the API key:

* enter any value as a username
* enter the API key value as a password

### Bearer Authentication

You can [generate API token](https://docs.yespo.io/reference/generateapikey-1) to

* Generate events
* Generate past events
* Remove events

## Date/time formats

The format of the passed dates and times is in compliance with [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) standard.

Date: YYYY-MM-DD\
Date and time: YYYY-MM-DDTHH:mm

> ❗️
>
> The timestamp is provided in the contact's time zone

## Currency format

The currency values are passed as an amount and a currency code in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) format.

Supported currencies: USD, EUR, UAH.

## Data charset

The default charset is UTF-8.\
If you want to send or receive data in another charset, use the following HTTP header:

**Content-Type: application/json; charset=UTF-8**

## Results

HTTP-response with status code **2хх** - The operation was completed successfully. The response payload depends on the current operation.\
HTTP-response with status code **4хх** - The operation was completed with an error. Text details can be added to the response body.

## API addresses

All API requests to Yespo are sent to [https://api.yespo.io/api/](https://api.yespo.io/api/), where you should input one of our methods' addresses after the last slash. For example, [https://api.yespo.io/api/v1/account/info](https://api.yespo.io/api/v1/account/info).