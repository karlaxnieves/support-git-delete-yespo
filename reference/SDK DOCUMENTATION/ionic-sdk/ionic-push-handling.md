---
title: Ionic Push Handling
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
## Listen for New Push Notifications While App is Active

While the app is open, you may need to track, if there is a new push notification.

To do that, set the listener using `FirebasePlugin.onMessageReceived` function:

```typescript
import {AwesomeCordovaPluginFirebase, IChannelOptions} from "awesome-cordova-plugin-reteno-firebase/dist/ngx";

constructor() {
    this.firebasePlugin.onMessageReceived().subscribe(this.onMessageReceived.bind(this));
    this.firebasePlugin.onTokenRefresh().subscribe (this.onTokenRefresh.bind(this));

    if( this.platform.is('android')){
          this.initAndroid();
    }else if( this.platform.is('ios')){
          this.initIos();
    }
}


initAndroid() {
    // Define custom  channel - all keys are except 'id' are optional.
    var customChannel: IChannelOptions  = {
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

    this.firebasePlugin.createChannel(customChannel).then(
      () => {
        this.log("Created custom channel: "+customChannel.id, undefined);
        this.firebasePlugin.listChannels().then((channels) => {
            if(typeof channels == "undefined") return;
            for(var i=0;i<channels.length;i++) {
              this.log("Channel id=" + channels[i].id + "; name=" + channels[i].name, undefined);
            }
          },
          (error: string) => {
            this.logError('List channels error: ' + error, error, false);
          }
        );
      },
      (error: any) => {
        this.logError("Create channel error", error, false);
      }
    );
  }
  initIos(){
    this.firebasePlugin.onApnsTokenReceived().subscribe ((token: string)=> {
      this.log("APNS token received: " + token, undefined)
    }, (error: any) => {
      this.logError("Failed to receive APNS token", error, false);
    });
  }


 onMessageReceived(message: any) {
    try{
      console.log("onMessageReceived");
      console.dir(message);
      if(message.messageType === "notification"){
        this.handleNotificationMessage(message);
      }else{
        this.handleDataMessage(message);
      }
    }catch(e: any){
      this.logError("Exception in onMessageReceived callback: "+e.message, undefined, false);
    }
  };

  handleNotificationMessage(message: any) {
    var title;
    if(message.title){
      title = message.title;
    }else if(message.notification && message.notification.title){
      title = message.notification.title;
    }else if(message.aps && message.aps.alert && message.aps.alert.title){
      title = message.aps.alert.title;
    }

    var body;
    if(message.body){
      body = message.body;
    }else if(message.notification && message.notification.body){
      body = message.notification.body;
    }else if(message.aps && message.aps.alert && message.aps.alert.body){
      body = message.aps.alert.body;
    }

    var msg = "Notification message received";
    if(message.tap){
      msg += " (tapped in " + message.tap + ")";
    }
    if(title){
      msg += '; title='+title;
    }
    if(body){
      msg += '; body='+body;
    }
    msg  += ": "+ JSON.stringify(message);
    this.log(msg, true);
  }

  handleDataMessage(message: any) {
    this.log("Data message received: " + JSON.stringify(message), undefined);
  }

  onTokenRefresh(token: string){
    this.log("Token refreshed: " + token, undefined);
  };

  

```