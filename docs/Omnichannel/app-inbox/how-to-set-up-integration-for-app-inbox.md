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
Setting up App Inbox for websites includes:

1. Getting authentication token.
2. Script installation and initialization.
3. Integration of a widget displayed on the site.
   <br />
   > 📘 Note
   >
   > App Inbox functionality works only for users authorized on the site.

## Getting Authentication Token

<Image align="center" width="80% " src="https://files.readme.io/fc35ee3a98578a5a5af79e3246e7d45a325e3c365f98c373d6847d152cea1c0c-auth_token.png" />

Send the request from your backend to eSputnik API to receive the authentication token (authToken).

Authenticate the request using one of the methods specified in the [API](https://docs.esputnik.com/reference/getting-started-with-your-api)  instructions, for example, using an [API key](https://docs.esputnik.com/reference/api-keys) .

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>

      </th>

      <th>

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Request method
      </td>

      <td>
        POST
      </td>
    </tr>

    <tr>
      <td>
        URL
      </td>

      <td>
        `https://esputnik.com/v1/auth/contact/token`
      </td>
    </tr>

    <tr>
      <td>
        Request header
      </td>

      <td>
        Content-Type: application/json
      </td>
    </tr>

    <tr>
      <td>
        Request body
      </td>

      <td>
        `{  
        "email": string,  
        "phone": string,  
        "externalCustomerId": string  
        }`
      </td>
    </tr>

    <tr>
      <td>
        Response: HTTP 200
      </td>

      <td>
        `{  
        “token”: “string”  
        }`
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

The request has to contain the known contact fields: `email, phone, externalCustomerId` (at least one field is required). Those fields are used for searching a contact in eSputnik. Afterward, the script uses authToken in requests to the eSputnik server.

You can find additional information about managing contacts in API methods for [adding contacts](https://docs.esputnik.com/reference/api-methods-for-adding-contacts) .

<br />

> 📘 Important
>
> * The token can become invalidated at any moment for security considerations, so you get it more than once. The script renews the token automatically by calling `getAuthTokenCallback`.
> * If a contact is not in the eSputnik system, the token is not returned, and the following response comes back instead:

```json
{
“token”: “”
}
```

## Script Installation and Initialization

Install and initialize the script on your frontend. Transmit `getAuthTokenCallback` in the parameters. This shall have the function calling your backend and returning the token.

If you have installed the eSputnik script to work with web tracking, forms and recommendations, you don’t need to reinstall it. Just add parameters for App Inbox to the initialization call.

Example:

<br />

```javascript
eS('init', {getAuthTokenCallback: () => yourImplementationOfAuthCallback(),  language: 'en', });
```

<br />

> 📘 Important
>
> Call the `'init'` initialization command one time at every page loading.

If you have not installed the script before, contact the eSputnik support team to get it, indicating that you need it for App Inbox.

You can get the script by yourself in the *Settings > Web Tracking* section.

<Image align="center" width="80% " src="https://files.readme.io/0bb74c50a8d1fdae6a9685cfdcc230f7358443c020222d91179a2a551e8ff84d-image5.webp" />

You can learn how to set up a web tracking code [here](https://docs.esputnik.com/docs/how-to-set-up-web-tracking-for-your-website) .

> 📘 Important
>
> Modify the call of the \`\`'init'’\` command in the script generated in the Web Tracking section as follows:

instead of

```json
eS('init')
```

it has to be

```javascript
eS('init', {getAuthTokenCallback: () =>yourImplementationOfAuthCallback(),  language: 'en', });
```

Example of a script with initialization:

```javascript
<script> !function (t, e, c, n) {var s = e.createElement(c); s.async = 1, s.src = 'https://statics.esputnik.com/scripts/' + n + '.js'; var r = e.scripts[0]; r.parentNode.insertBefore(s, r); var f = function () {f.c(arguments); }; f.q = []; f.c = function () {f.q.push(arguments); }; t['eS'] = t['eS'] || f; }(window, document, 'script', 'UUID'); </script><script>eS('init', {getAuthTokenCallback: () => yourImplementationOfAuthCallback(), language: 'en', });</script>
```

### Parameters of the Object Passed to Yespo Function

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        getAuthTokenCallback
      </td>

      <td>
        function yourImplementationOfAuthCallback() \{ &#x20;
        &#x20; return new Promise((resolve, reject) => \{ &#x20;
        &#x20;     //  place here code with your backend API request, parse token from response and pass it to \`resolve\` function call &#x20;
        &#x20;     resolve('token should be placed here'); &#x20;
        &#x20; }); &#x20;
        } &#x20;
        Required

        type: () => Promise\<String>
      </td>

      <td>
        Asynchronous function called by the script to get `authToken`. It has to address to the Customer Backend and return <a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise" target="_blank"> Promise</a>
      </td>
    </tr>

    <tr>
      <td>
        language
      </td>

      <td>
        en\\\
        Required
        Type: String
      </td>

      <td>
        ISO 639-1
      </td>
    </tr>
  </tbody>
</Table>

## Integration of App Inbox Widget

To integrate the widget on the site, the user has to provide to our CDP:

* <a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors" target="_blank"> CSS selector</a>
* Insert type position relative to other element(s) (<a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML" target="_blank">insertAdjacentHTML</a> method is applied).

In addition, you can submit an SVG file with the desired design of the notification icon (Bell button) and the design of notifications.

> 📘 Note
>
> Send us a request to make up the bell button and notifications according to your desi