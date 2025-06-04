---
title: Service Worker. Troubleshooting
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Service Worker. Troubleshooting | Yespo Guide
  description: Learn how to fix problems with Service Worker
  robots: index
next:
  description: ''
---
The Yespo web push script is loaded via a Service Worker file called `sw.js` and placed in the site's root. The problem can occur if the site code already uses files with the same name or uses a different Service Worker.

## 1. Changing the name of Service Worker sw\.js

Some builders (GoDaddy, Wix, etc.) place the sw\.js file in the site root by default. Since the Yespo file has the same name, errors may occur.

To avoid problems, you can rename the file and, if necessary, specify the path to it in the Yespo script.

To do this, find the initialization function in the Yespo script code

```javascript
es("pushOn");
```

and add parameters to this entry in the following format:

```javascript
es("pushOn", {'service-worker': {'relUrl': '/push-worker.js'} });
```

where the `'relUrl'` parameter is the path to the file and its arbitrary name.

<Image align="center" width="40% " src="https://files.readme.io/cb40e9f98d110d1433b94a9c2fa59f701db7e62580abb14cf62eda68f6d5c033-add-parameters.webp" />

## 2. Merging Service Workers from Yespo and PWA

Sites with PWA (progressive web app) already use Service Worker, i.e., they contain a JavaScript file with a specific set of functions. To enable the ability to subscribe and send web pushes via Yespo to your site, you need to add the line at the end of the JavaScript code of your Service Worker

```javascript
importScripts('https://push.yespo.io/service-worker.js');
```

### Note

The names of functions, variables or handlers in your Service Worker and Service Worker from Yespo may be the same. In this case, conflicts leading to failures in your PWA and the Yespo script are possible.

Below is a list of methods’ (functions’) names in the Yespo file:

* `onPushNotification`
* `getNotificationContent`
* `showNotification`
* `getNotificationData`
* `determineClickedLink`
* `collectActionLinks`
* `trackNewServiceWorkerActivation`

If the names in your Service Worker and the Yespo's Service Worker match, the function located last in the code will be called. For example, if the code according to this instruction ends with the line

```javascript
importScripts('https://push.yespo.io/service-worker.js');
```

then the functionality related to web pushes will work correctly.