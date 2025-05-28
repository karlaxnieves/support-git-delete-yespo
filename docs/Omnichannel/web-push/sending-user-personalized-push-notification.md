---
title: Adding Data on User’s Web Activity to Push
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Send a personalized Push Notification with the CDP | Yespo Guide
  description: >-
    Step-by-step guide how to create and start sending personalized Web Push
    notifications depending on his activity on your website. Read how it works.
  robots: index
next:
  description: ''
---
Let's look at the option to create personalized Push notifications to the particular users that are performed certain actions on the website (clicked a button, visited some specific page, filled in a form).

Push button notifications work like this:

1. User clicks, for example, “Order now” button on your website
2. An event "Order button is clicked” transferred to the system
3. This event launches a previously configured script
4. User receives a browser Push notification, for example, "Thank you for ordering!".

In our Push notification service, the process of this option implementation consists of the following stages:

* Configuring your customers addresses (tokens) collecting process.
* Configuring event transfer to the system
* Creating a website Push notification
* Creating and running a script

## Configuring Your Customers Addresses (Tokens) Collecting Process.

You need to start with registering your project in the Google application firebase.google.com and generation of script to collect addresses (push-token) which must be added before closing tag. Details of the setup process are described in [Creating web push notifications](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications) article. By the way, you can add this script using <a rel="nofollow" href="https://tagmanager.google.com/" target="_blank"> Google Tag Manager</a>.

## Configuring Event Transfer to the System

To transmit an event to the system, insert additional lines to the previously installed address-gathering script (push-token) before the closing tag. So, command format will be:

```javascript
function sendEventForToken(pushToken) {
     es('sendEvent', 'abandoned_cart', pushToken, [{"name":"...", "value":"..."}, {...}, ...]);
}
es('getPushToken', sendEventForToken);
```

where\
**eventTypeKey** – the name of the event;\
**keyValue** - here we specify the value of push-token;\
**param\_1, param\_2 … param\_n** – the of the event parameters we shall need in the system;\
**value\_1, value\_2 … value\_n** – corresponding parameters value.

## How to Create Your Own Push Notification

To create a Push notification, go to **Messages menu** → **Notifications section** and click the **Push tab**. For more info on Push notifications building, click [here](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications).

## Creating and Running a Script (on example of "Abandoned cart" script)

To initialize [script in the system](https://docs.yespo.io/docs/how-to-launch-workflow-upon-import), you have to transmit the **abandoned\_cart** event to the system when user added goods to his cart. To do this, add the following code line up to closing tag to the addresses collecting script (push-token) of your clients:

```javascript
function sendEventForToken(pushToken) {
     es('sendEvent', 'abandoned_cart', pushToken);
}
es('getPushToken', sendEventForToken);
```

After inserting this code, an event containing the unique user’s push-token will be sent to the system when he adds products to his cart.

In order for the script to check whether customer completed his ordering or not, we need to generate a **sold** event. It will stop the running script if purchase (payment) is completed successfully. To do this, you need to add the code line to the addresses collecting script (push-token) on the "Thank you for ordering" page:

```javascript
function sendEventForToken(pushToken) {
es('sendEvent', 'sold', pushToken);
}
es('getPushToken', sendEventForToken);
```

Now build a workflow which will trigger with the *Abandoned Cart* event and will include the following blocks:

* Start
* Timer (purchase event waiting time)
* Check event (has a purchase been made?)
* Web Push (pre-prepared reminder about an abandoned cart)
* End (for both paths)

<Image align="center" width="80% " src="https://files.readme.io/7ed7df9be1759942a4cf8a435088d0327cb73991948f82e24957efa35f3c0800-workflow-scheme-en.webp" />

The script timer value is set depending on users behavioral characteristics on your website.

You can check the event generation correctness in **Triggers** menu of **Events history** tab of the system.

Then, test a new script.
