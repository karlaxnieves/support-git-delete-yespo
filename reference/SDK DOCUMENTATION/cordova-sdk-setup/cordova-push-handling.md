---
title: Cordova Push Handling
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Listen for New Push Notifications while App is Active

While app is open, you may need to track, if there is new push;\
To do so, set listener using `FirebasePlugin.onMessageReceived` function;

```typescript
import { FirebasePlugin } from 'cordova-plugin-reteno-firebase';

function onDeviceReady() {
  // Prompt user for push subscription
   FirebasePlugin.onMessageReceived(function(message) {
        try{
            console.log("onMessageReceived");
            console.dir(message);
            if(message.messageType === "notification"){
                handleNotificationMessage(message);
            }else{
                handleDataMessage(message);
            }
        }catch(e){
            logError("Exception in onMessageReceived callback: "+e.message);
        }

    }, function(error) {
        logError("Failed receiving FirebasePlugin message", error);
    });

    FirebasePlugin.onTokenRefresh(function(token){
        log("Token refreshed: " + token)
    }, function(error) {
        logError("Failed to refresh token", error);
    });

    if(cordova.platformId === "android"){
        initAndroid();
    }else if(cordova.platformId === "ios"){
        initIos();
    }
}

// In this example, we'll prompt the user as soon as the 'deviceready' event is fired
// There's good chances you'll find a more suitable moment in the user journey
document.addEventListener('deviceready', onDeviceReady);

var initIos = function(){
    FirebasePlugin.onApnsTokenReceived(function(token){
        log("APNS token received: " + token)
    }, function(error) {
        logError("Failed to receive APNS token", error);
    });

    FirebasePlugin.registerInstallationIdChangeListener(function(installationId){
        log("Installation ID changed - new ID: " + installationId);
    });

    FirebasePlugin.registerApplicationDidBecomeActiveListener(function(){
        log("Application did become active");
    });

    FirebasePlugin.registerApplicationDidEnterBackgroundListener(function(){
        log("Application did enter background");
    });
};

var initAndroid = function(){

    // Define custom  channel - all keys are except 'id' are optional.
    var customChannel  = {
        // channel ID - must be unique per app package
        id: "my_channel_id",

        // Channel name. Default: empty string
        name: "My channel name",

        //The sound to play once a push comes. Default value: 'default'
        //Values allowed:
        //'default' - plays the default notification sound
        //'ringtone' - plays the currently set ringtone
        //filename - the filename of the sound file located in '/res/raw' without file extension (mysound.mp3 -> mysound)
        sound: "blackberry",

        //Vibrate on new notification. Default value: true
        //Possible values:
        //Boolean - vibrate or not
        //Array - vibration pattern - e.g. [500, 200, 500] - milliseconds vibrate, milliseconds pause, vibrate, pause, etc.
        vibration: [300, 200, 300],

        // Whether to blink the LED
        light: true,

        //LED color in ARGB format - this example BLUE color. If set to -1, light color will be default. Default value: -1.
        lightColor: "0xFF0000FF",

        //Importance - integer from 0 to 4. Default value: 3
        //0 - none - no sound, does not show in the shade
        //1 - min - no sound, only shows in the shade, below the fold
        //2 - low - no sound, shows in the shade, and potentially in the status bar
        //3 - default - shows everywhere, makes noise, but does not visually intrude
        //4 - high - shows everywhere, makes noise and peeks
        importance: 4,

        //Show badge over app icon when non handled pushes are present. Default value: true
        badge: true,

        //Show message on locked screen. Default value: 1
        //Possible values (default 1):
        //-1 - secret - Do not reveal any part of the notification on a secure lockscreen.
        //0 - private - Show the notification on all lockscreens, but conceal sensitive or private information on secure lockscreens.
        //1 - public - Show the notification in its entirety on all lockscreens.
        visibility: 1
    };

    FirebasePlugin.createChannel(customChannel,
        function() {
            log("Created custom channel: "+customChannel.id);
            FirebasePlugin.listChannels(
                function(channels) {
                    if(typeof channels == "undefined") return;
                    for(var i=0;i<channels.length;i++) {
                        log("Channel id=" + channels[i].id + "; name=" + channels[i].name);
                    }
                },
                function(error) {
                    logError('List channels error: ' + error);
                }
            );
        },
        function(error) {
            logError("Create channel error", error);
        }
    );
};

```
