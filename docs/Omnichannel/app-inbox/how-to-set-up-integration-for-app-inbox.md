---
title: Configuring App Inbox for Websites
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Configuring App Inbox for Websites | Yespo Guide
  description: >-
    This guide explains configuring the App Inbox for Websites by sending
    specific requests to Yespo API for an authentication token.
  robots: index
next:
  description: ''
  pages:
    - type: link
      title: Creating App Inbox Messages
      url: >-
        https://dash.readme.com/project/reteno/v1.0/docs/creating-app-inbox-messages
---
Setting up App Inbox includes:

1. Getting authentication token.
2. Script installation and initialization.
3. Integration of a widget displayed on the site.

> 📘 Note
> 
> App Inbox functionality works only for users authorized on the site.

## Getting Authentication Token

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63b20cecbac7ddc131b259f8490abe60bff318eb2692655505ce834bbc443d1b-auth_token.png",
        "",
        "Getting authentication token"
      ],
      "align": "center"
    }
  ]
}
[/block]


Send the request from your backend to our API to receive the authentication token (`authToken`).

Authenticate the request using one of the methods specified in the [API](https://docs.yespo.io/reference/getting-started-with-your-api) instructions, for example, using an [API key](https://docs.yespo.io/reference/api-keys).

[block:parameters]
{
  "data": {
    "h-0": "",
    "h-1": "",
    "0-0": "Request method",
    "0-1": "POST",
    "1-0": "URL",
    "1-1": "`https://v1/auth/contact/token`",
    "2-0": "Request header",
    "2-1": "Content-Type: application/json",
    "3-0": "Request body",
    "3-1": "{  \n\"email\": string,  \n\"phone\": string,  \n\"externalCustomerId\": string  \n}",
    "4-0": "Response: HTTP 200",
    "4-1": "{  \n\"token\": \"string\"  \n}"
  },
  "cols": 2,
  "rows": 5,
  "align": [
    "left",
    "left"
  ]
}
[/block]


The request has to contain the known contact fields: email, phone, externalCustomerId (at least one field is required). Those fields are used for searching a contact in the platform. Afterward, the script uses authToken in requests to our system's server.

You can find additional information about managing contacts in [API methods for adding contacts](https://docs.yespo.io/docs/api-methods-adding-contacts).

> 📘 Important
> 
> - The token can become invalidated at any moment for security considerations, so you get it more than once. The script renews the token automatically by calling `getAuthTokenCallback`.
> - If a contact is not in the system, the token is not returned, and the following response comes back instead:

```json
{
"token": ""
}
```

## Script Installation and Initialization

Install and initialize the script on your frontend. Transmit `getAuthTokenCallback` in the parameters. This shall have the function calling your backend and returning the token.

If you have installed our script to work with web tracking, forms and recommendations, you don’t need to reinstall it. Just add parameters for App Inbox to the initialization call.

Example:

```javascript
eS('init', {getAuthTokenCallback: () => yourImplementationOfAuthCallback(),  language: 'en', });
```

> 📘 Important
> 
> Call the `'init'` initialization command one time at every page loading.

If you have not installed the script before, contact our support team to get it, indicating that you need it for App Inbox.

You can get the script by yourself in the _Settings_→ _Web Tracking_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7abddd441ef6c836ae11abc31fc77a7503da2cb8426cb197a58f453b4f8572ed-image5.webp",
        "Go to Settings > Web Tracking",
        "Go to Settings → Web Tracking"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can learn how to set up a web tracking code [here](https://docs.yespo.io/docs/how-set-web-tracking-your-website).

**Important**: Modify the call of the `'init'` command in the script generated in the Web Tracking section as follows:

instead of

```json
eS('init')
```

it has to be

```javascript
eS('init', {getAuthTokenCallback: () =>yourImplementationOfAuthCallback(),  language: 'en', });
```

Example of a script with initialization:

```javascript
<script> !function (t, e, c, n) {var s = e.createElement(c); s.async = 1, s.src = 'https://scripts/' + n + '.js'; var r = e.scripts[0]; r.parentNode.insertBefore(s, r); var f = function () {f.c(arguments); }; f.q = []; f.c = function () {f.q.push(arguments); }; t['eS'] = t['eS'] || f; }(window, document, 'script', 'UUID'); </script><script>eS('init', {getAuthTokenCallback: () => yourImplementationOfAuthCallback(), language: 'en', });</script>
```

### Parameters of the Object Passed to our platform's Function

[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Example",
    "h-2": "Description",
    "0-0": "getAuthTokenCallback",
    "0-1": "function yourImplementationOfAuthCallback() { return new Promise((resolve, reject) => {  \n//  place here code with your backend API request,  \n//  parse token from response and pass it  \n//  to `resolve` function call  \nresolve('token should be placed here');  \n  });  \n}  \ntype: () => Promise<String>",
    "0-2": "Asynchronous function called by the script to get `authToken`. It has to address to the Customer Backend and return <a rel=\"nofollow\" href=\"https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise\" target=\"_blank\"> Promise</a>",
    "1-0": "language",
    "1-1": "en  \nRequired  \nType: String",
    "1-2": "ISO 639-1"
  },
  "cols": 3,
  "rows": 2,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


## Integration of App Inbox Widget

To integrate the widget on the site, the user has to provide to our CDP:

- <a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors" target="_blank"> CSS selector</a>
- Insert type position relative to other element(s) (<a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML" target="_blank">insertAdjacentHTML</a> method is applied).

In addition, you can submit an SVG file with the desired design of the notification icon (Bell button) and the design of notifications.

> 📘 Note
> 
> Send us a request to make up the bell button and notifications according to your design.