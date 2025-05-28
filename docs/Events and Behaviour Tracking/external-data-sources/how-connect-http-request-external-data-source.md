---
title: Connecting HTTP Request
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Connecting HTTP Request | Yespo Guide
  description: >-
    The document provides instructions for setting up an HTTP request as an
    external data source in Yespo, enabling automated data transfer and message
    personalization using the Velocity language.
  robots: index
next:
  description: ''
---
Like other external data sources, HTTP request allows you to automate the creation of message content. This request uploads and sends contact data from our service to other systems, and vice versa, transfers data from third-party systems to our platform. With its help, you can refer to your API, which will process the request and return personalization data to the message, for example, a personal promo code. The [Velocity](https://docs.yespo.io/docs/introduction-to-velocity) language is used to transfer data.

## Creating Data Source

1. In your account settings, open the *Data Sources* tab, click on the *New data source* button and select *External data source*.

<Image align="center" width="80% " src="https://files.readme.io/a30c882b7b03d813842be5554a10a6038f839cf426c00cffca74313ef7da9731-connecting-http-request-001.webp" />

2. In the pop-up window, select HTTP request.

<Image align="center" width="80% " src="https://files.readme.io/9b201d772b94cfdd49c7b30cd1ccc91d370589121f272195942a66c9b886bad2-connecting-http-request-002.webp" />

## Setting Up Connection

1. Give an arbitrary name to the data source.
2. Add a description if necessary.
3. Select the type of request: *GET* or *POST*.
4. Enter the URL to be requested (HTTPS only). You can refer to [contact fields](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system) and event parameters.

<Image align="center" width="80% " src="https://files.readme.io/8e81a6edf4b5774c5b2c72bf3649c22f89fe191f4714014850ba1c540cffbf4c-connecting-http-request-003.webp" />

5. If your application reads parameters from headers, activate the corresponding switcher. Then specify the required parameters and their values.

<Image align="center" width="80% " src="https://files.readme.io/eb91147c65706ccd226b33dc3912556b163b46aeecaf87d3e790dc7310360e4e-connecting-http-request-004.webp" />

6. To configure authentication, activate the corresponding switcher. There are three types of authentication available:

* Basic,
* Bearer token,
* [API key](https://docs.yespo.io/reference/api-keys) (in headers or the query string).

Specify the connector name. Select the authentication type. Enter your credentials (login and password/token/key). Click on the *Done* button.

<Image align="center" width="80% " src="https://files.readme.io/600a3bfccc94a3f6cd63aaa7ab6abcb573cd456fd47226e0b2de66a579e28dcc-connecting-http-request-005.webp" />

7\. If your application reads parameters from the request body, activate the corresponding switcher, enter the request body in the text area and specify the format: JSON, XML or text.

<Image align="center" width="80% " src="https://files.readme.io/48aaecbdfa632f24f79943ae8d7f1107611e43216f73e484af0cfab86ebf7740-connecting-http-request-006.webp" />

## Testing Connection

Select an event from history or manually paste the request body for testing.

<Image align="center" width="80% " src="https://files.readme.io/7a8abf62f7fb23041eb3e26e6e4e544075d1a0b2fb3d5843f615d68d5b294763-connecting-http-request-007.webp" />

[More on adding data to a message >](https://docs.yespo.io/docs/how-connect-postgresql-external-data-source#3-add-data-to-a-message)
