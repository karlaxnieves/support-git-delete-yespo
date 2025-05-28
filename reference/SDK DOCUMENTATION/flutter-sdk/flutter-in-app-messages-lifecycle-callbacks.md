---
title: Flutter In-App Messages Lifecycle Callbacks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter In-App Messages Lifecycle Callbacks | Support
  description: Follow our manual to subscribe to In-App message lifecycle callbacks
  robots: index
next:
  description: ''
---
You can subscribe to In-App messages lifecycle.

You get callbacks:

- before In-App message is displayed
- right after In-App message is displayed
- before In-App message is closed
- after In-App message is closed
- if an error during displaying In-App message occurred

In these callbacks you also receive a data model which contains information whether In-App message was displayed via display rules or push notification click, id or interaction id of In-App message and some other data which may be useful.

```dart Dart
class InAppMessageAction {
  InAppMessageAction({
    required this.isCloseButtonClicked,
    required this.isButtonClicked,
    required this.isOpenUrlClicked,
  });
  final bool isCloseButtonClicked;
  final bool isButtonClicked;
  final bool isOpenUrlClicked;
}
```

## Example usage

```dart Dart
Reteno.onInAppMessageStatusChanged.listen((status) {
    switch (status) {
    case InAppShouldBeDisplayed():
        print('In-app should be displayed');
    case InAppIsDisplayed():
        print('In-app is displayed');
    case InAppShouldBeClosed(:final action):
        print('In-app should be closed $action');
    case InAppIsClosed(:final action):
        print('In-app is closed $action');
    case InAppReceivedError(:final errorMessage):
        print('In-app error: $errorMessage');
    }
});
```

## Pause In-App Messages

You can manage the display of In-App messages by pausing them when needed.  
Pausing In-App messages can be useful to prevent interruptions during critical user flows such as registration or payment processes.

All In-App messages that are supposed to be displayed during the pause period will be skipped and shown later when the display rules match.

You can pause or unpause In-App messages at any time during the application's lifecycle.

```dart Dart
Reteno.pauseInAppMessages(true);
```