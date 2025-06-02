---
title: Creating Mobile Push Message
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Mobile Push Message | Yespo Guide
  description: >-
    This guide provides instructions on creating mobile push notifications using
    Yespo, including setting up integration, configuring message settings like
    title, text, images, and personalization, and testing the notifications on
    iOS and Android devices.
  robots: index
next:
  description: ''
---
In this guide, you will learn how to create mobile push notifications.

> 📘 Important
>
> To send mobile push messages via Yespo, you need to [set up a connection](https://docs.yespo.io/docs/connecting-mobile-apps) between your mobile app and our system.

Once you set up the integration, you can prepare and send your mobile campaign.

## Creating New Mobile Push

Go to **Messages** → **Messages** → select the **Mobile Push** section in the left sidebar. Click the **New Mobile Push** button.

<Image align="center" width="80% " src="https://files.readme.io/3116394ab6b9d8d2b6e6aa95e8bd0af9bcaab6fd9c0fa439ee568d0ac56d4cf4-mobile-push-01.webp" />

### Main settings

Fill in the following fields:

1. **Name**. The system name that the recipient will not see.
2. **Title**. Required field, the recipient will see its value in the message.
3. **Subtitle**. Optional field, which value only iOS users will see.
4. **Text**. The main content of a push message is up to 1000 characters long.

<Image align="center" width="80% " src="https://files.readme.io/ad4b82ba52c447f544a98b86af4986b77bf0df0bec2c79a86d613854869db841-mob-push-emoji-en-01.webp" />

Use emojis in the title, subtitle, and text fields.

<Image align="center" width="80% " src="https://files.readme.io/b180949b2d3e3c3f5cb99e76ebd47d24478954e0bcb1ac485cd80b2e10974449-mob-push-emoji-en-03.webp" />

> 📘 Note
>
> One emoji takes up two characters. Keep this in mind when creating messages

5. **Personalization**. Use the dynamic variables to add a name, city, bonuses or any personal data available in the [user profile](https://docs.yespo.io/docs/user-profile). Click on the **Personalization** icon in the **Title**, **Subtitle** or  **Text** field to select data.

<Image align="center" width="80% " src="https://files.readme.io/fa91a5d83954f3eaf47b7fc167ca497c9e4e9efd16992e8c86c87f4fd33928f2-mob-push-emoji-en-02.webp" />

6. **Image**. Select one of the options:

* Image — one picture.
* Carousel of images — up to 10 scrolling images. The carousel is available on Android and iOS devices. Before using the image carousel for iOS, you must [set the content extension](https://docs.yespo.io/reference/ios-images-carousel).

You can upload images in `JPG`, `JPEG`,` PNG`, or` GIF` formats with a size of up to 2 MB and a width and height of up to 1200px.

> 📘 Note
>
> The `GIF` format is available only on iOS devices and will appear as a static image on Android devices.

<Image align="center" width="80% " src="https://files.readme.io/bf176d1aba31b4bbbb026b8e599525148f354e37ff74bd69bc0efe243b8c5e3b-image.webp" />

> 📘 Note
>
> You can edit the image directly in the editor when uploading (if it does not meet the requirements) or after uploading (the **Edit** button). After editing, the image is saved in `PNG` format.

<Image align="center" width="80% " src="https://files.readme.io/f40c10c05e39880603789c5a51fcbb27cd8c4b97d4ef05d92c666880b3075436-mob-push-image-editor-en.webp" />

7. **Link**. The URL can be opened by a device browser or as a deep link to a specific location within your mobile app. If no link is specified, a tap on the push notification will open the app. Also, you can set an individual link for each user using the personalization option.

8. **Buttons**. Use buttons [to trigger any event](https://docs.yespo.io/docs/how-add-scenario-button). For example, some answer options or the transition to the specified URL. When a recipient touches the screen for an extended period of time (long pressing), it displays the actions assigned to your push notification.

<Image align="center" width="80% " src="https://files.readme.io/64bb3fc75b7c44e6551a3c8cc854fe9053f405e80ee57b43a02fc65263e2f292-creating_mobpush001.webp" />

> 📘 Note
>
> * We do not recommend using links with the `HTTPS` protocol in mobile pushes because, after the first click, the user will see a pop-up window asking where to open the link — in a browser or in a mobile app.
> * For the user to immediately get to the desired screen of the app by clicking, use links of the format *“myphotoapp:Vacation?index=1”*. <a rel="nofollow" href="https://developer.apple.com/documentation/xcode/defining-a-custom-url-scheme-for-your-app" target="_blank"> Read more > </a>
> * For iOS, you can add up to four buttons; for Android — up to three.

To add the action buttons to your mobile push notification, click **+ Add Button** and enter the following parameters:

| Parameter     | Description                                                                                                                                           |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Action ID     | A unique identifier of the button action.                                                                                                             |
| Text          | The text that the button displays.                                                                                                                    |
| iOS icon path | The icon associated with an action. Available in iOS 15 and later. Enter the name of an image in your app’s bundle, preferably in an asset catalogue. |
| Launch URL    | A URL or a deeplink that opens when the notification is selected.                                                                                     |
| Custom data   | Additional parameters associated with the button in JSON format.                                                                                      |

> 📘 Note
>
> You must enter the values in Action ID and Text for a button to work correctly. Use different Action IDs when you add several buttons.

To learn more about notification action icons, see <a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/unnotificationactionicon" target="_blank"> Apple documentation</a>.

For click event handling, you can use your preferred tools. 

Also, you can use our SDK for this purpose. [Learn more](https://docs.yespo.io/docs/sdk-mobile-apps) about installing and using our SDK for mobile apps.

9. **Tags**. Select tags from the list or enter a new one and click **Enter**. Use [tags](https://docs.yespo.io/docs/how-add-tags) to filter search results and set [campaign frequency strategy](https://docs.yespo.io/docs/how-make-campaign-using-optimal-messaging-frequency-strategy).

<Image align="center" width="80% " src="https://files.readme.io/dd5c0cd98519e8ae697df37c0727038b53d4166b7ae115246de71641ff9b3edd-image0005.webp" />

### Additional settings

Fill in the following fields:

1. **Custom data**. You can create push notification messages using custom data in `JSON` format. If custom data is used in a [multilingual message](https://docs.yespo.io/docs/how-to-create-mobile-push-notifications#multilingual-version-optional), it can be applied to all language versions. To do this, activate the **Use custom data from the default language version for all versions** switcher. If the switcher is disabled, different custom data can be used in each language version.

<Image align="center" width="80% " src="https://files.readme.io/57384eadccea7b75b393812e2b5d64eca1705d04033b5ce531a3153824aad761-creating_mobpush02.webp" />

Also, you can use dynamic variables to add data into the **Custom data** parameter: message name, first name, city, and so on. Click on the personalization icon and select the required.

> 📘 Note
>
> This option will only work if your app supports custom data, regardless of the user’s device. Please make sure that your app’s developers have provided this option.

2. **Sound**. A sound to play when the device receives the notification.

3. **Unread messages badge**. By default, each notification increments a number displayed in the long-press menu. To display arbitrary values, activate the switcher and specify the desired number. For example, you can enter a value greater than the real one to attract attention or, conversely, lesser so as not to disturb the user with many unread messages.

<Image align="center" width="80% " src="https://files.readme.io/58151ae7b91af46d88ab8ac7e3d66c36b1f89a2804a9ce1d3f0c3b55e33e6400-creating_mobpush003.webp" />

4. **Annoyance level**. [Prioritize your notifications](https://docs.yespo.io/docs/management-campaign-frequency) to protect subscribers from intrusive messages.

5. **Subscription categories**. These settings help deliver content to the right users based on their preferences. 

6. **Time to Live (TTL)**. TTL — the period after which the message will not be displayed if it has not been delivered by this time. By default, it’s 1 day, but you can select other options.

<Image align="center" width="80% " src="https://files.readme.io/659e8edc08a85ed808707ce23b54d0e2ebc93eaa97070217d9758c6e4c7bb43f-creating_mobpush004.webp" />

> 📘 Note
>
> Your organization’s logo is added to the mobile push notification from your app automatically.

### Multilingual version (optional)

In our platform, you can create a multilingual version of any message. Click the **Globe icon** in the top panel, specify the default language, and add language versions. Fill each version with the content in the corresponding language. You can switch between versions within one template in one click.

<Image align="center" width="80% " src="https://files.readme.io/eb0d178dda4f11a98be28303bb92958a449c3734ace1278d3bb915eaed1038b3-image27.webp" />

[Learn more about multilanguage >](https://docs.yespo.io/docs/multilanguage-overview)

## Testing Message

1. Test the messages by clicking the **Test button** on the top panel.

<Image align="center" width="80% " src="https://files.readme.io/03356ab69eab19b75399df6ee8a881770c8acc40cc1e39c37482a6526bb61923-image26.webp" />

2.  In a popup window, enter a phone number enter email, contactID, or phone number linked to the mobile push token.

<Image align="center" width="80% " src="https://files.readme.io/e3849487856e2bac0c86e70fa941dc3a5568727a241a5a68b0f66babcaa3a32a-Test.webp" />

* **Under\_Application**, select the app in which you want to send your push notification. If you have only one app, it will be selected automatically.
* **Under\_Search,** enter email, contactID, or phone number to send your push notification to.\
  If the contact with the specified phone number is an app user, you will see such status:

<Image align="center" width="80% " src="https://files.readme.io/5c8e71b475bdfae14b20456f85ff8b532b9bf6772d7df2e7bc9bc34b95a9dd5e-app_user.webp" />

It means the provided contact data has a matching mobile token. You can send a test notification to this contact. Otherwise, you will receive the next notification: **The contact does not have an application token**.

After sending your test mobile notification, you’ll see how your push notification will look on the device it’s sent to. There are three options for how your push notification can be displayed:

**On iOS**: Push notifications display as a banner in the notification tray.

<Image align="center" width="40% " src="https://files.readme.io/22dd2f4f4835c52ef8fafdb257f5062d6526cc85ad7856d2a5bcaf603e75380e-create12.webp" />

**On Android**:

* A cropped push notification is displayed in the push notification drawer.
* The push notification is expanded in the push notification drawer.

<Image align="center" width="40% " src="https://files.readme.io/97e2a760ba1415143eda97373300674af47ba349ce932b0a8ec194fe701509ab-Android.webp" />