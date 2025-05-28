---
title: Introduction to Velocity
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Introduction to Velocity | Yespo Guide
  description: >-
    Apache Velocity is Java software that uses the Velocity Engine to generate
    dynamic message content by substituting data from JSON objects, enabling
    flexible bulk and triggered campaigns.
  robots: index
next:
  description: ''
---
<a rel="nofollow" href="https://velocity.apache.org/engine/1.7/user-guide.html" target="_blank">Apache Velocity</a> is a software product consisting of several Java libraries. The product's main component is the Velocity Engine, a library that allows you to generate dynamic output content (images, links, text) based on message templates.

Velocity conditionals such as `if/else`, `for`, and `foreach` allow you to set flexible conditions for displaying content depending on the JSON object parameters. 

[More about velocity variables’ types and functions to use in Yespo >](https://docs.yespo.io/docs/using-velocity-features-yespo)

Velocity Engine could be used both in bulk campaigns and triggered campaigns.

Dynamic content in messages is used to substitute the personalized data to send to the user — for example, goods on a placed order, the username, or their personal promotional code.

Data for substitution in the message can be transmitted:

* From the [user profile](https://docs.yespo.io/docs/user-profile) in the Yespo system
* From the [external data sources](https://docs.yespo.io/docs/external-data-sources)
* From the [event](https://docs.yespo.io/docs/events-and-behaviour-tracking)

No matter where you transfer data from, it enters the Yespo system in the same format: JSON object data with some parameters.

To substitute data from such object to the message, use Velocity variables. Variables are the type of reference that can refer to something defined in the JSON code. The more user data you have, the more dynamic variables you can use.

## Referring to JSON object values via variables

JSON (JavaScript Object Notation) is a human-readable text data exchange format based on JavaScript. Easy to read by man and machine.

Formatting of a JSON object is set using curly braces `{ }` containing the data with the key values. The pairs of key values are separated by a colon: `{"key" : "value"}`. Every pair of values is separated by a comma, so the middle section of the JSON object looks like this:

```json
{
"key" : "value", 
"key" : "value", 
"key": "value"
}.
```

As an example, the object which is transmitted in the event by the smartsend API method containing two pairs of key values looks as follows:

```json
{
  "discount": "5%",
  "link": "https://example.site.com/items_for_sale"
}
```

To display the transmitted values in a message, you have to use the velocity structure `$!data.get('discount')` and `$!data.get('link')` in the message, where:

* `$!data.get` — command to extract data,
* value in quotes and brackets indicates the field where to extract data from.

<Image align="center" width="80% " src="https://files.readme.io/f45e170922a003bad0190b00a01b67cefce35f3ffe0128d14fbfa662be28930c-cc2599e-Introduction_to_Velocity_1.webp" />

After data substitution when sending, the message will look as follows:

<Image align="center" width="80% " src="https://files.readme.io/aeedb73d384930f942a0ea373ea35969d10c1ebebcd0d60a532e2cf057f7dfa6-dc0b6b1-Introduction_to_Velocity_2.webp" />

The value *“5%”* substitutes the discount variable, and the value `https://site.com/items_for_sale` substitutes the link variable as the link for the button.

For more information on how to use velocity variables, see the articles below:

* [User Profile Variables and Velocity Features >](https://docs.yespo.io/docs/user-profile-variables-and-velocity-features)
* [Using Velocity in Email >](https://docs.yespo.io/docs/using-velocity-email)
* [Using Velocity in Mobile Push and other channels >](https://docs.yespo.io/docs/using-velocity-mobile-push)
* [Adding data from external data sources to an email on the Google Spreadsheet example >](https://docs.yespo.io/docs/how-import-external-data-google-sheets)
