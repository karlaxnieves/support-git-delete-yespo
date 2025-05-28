---
title: Flutter App Inbox Messages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter App Inbox Messages | Support
  description: Send App Inbox messages to your apps on Flutter
  robots: index
next:
  description: ''
---
App Inbox is similar to an email inbox but is designed for direct messages from an app. As opposed to push notifications, it allows customers to keep promotions and browse a chronological list of messages at any time.

With the Reteno App Inbox, there is no default UI. This means with a few lines of code, you can connect Reteno with your inbox.

> 📘 Note
> 
> App Inbox is available in version **1.7.0** and later.

## Downloading New Messages

```dart Dart
// If  `page`  or  `pageSize`  is not specified, then all messages will be returned
final messages = await Reteno.appInbox.getAppInboxMessages();
```

```dart Dart
final messages = await Reteno.appInbox.getAppInboxMessages(
    page: 1,
    pageSize: 20,
);
```

The result is an instance of the `AppInboxMessages` class:

```dart Dart
class AppInboxMessages {
  final List<AppInboxMessage> messages;
  final int totalPages;
  AppInboxMessages({required this.messages, required this.totalPages});
}
```

Reteno inbox message attributes:

```dart Dart
class AppInboxMessage {
  final String id;
  final String title;
  final String createdDate;
  final bool isNewMessage;
  final String? content;
  final String? imageUrl;
  final String? linkUrl;
  final String? category;
}
```

## Get Inbox Unread Messages Count

```dart Dart
final count = await Reteno.appInbox.getAppInboxMessagesCount();
```

## Subscribe on Inbox Unread Messages Count

```dart Dart
Reteno.appInbox.onMessagesCountChanged.listen((count) {
    print(count);
});
```
```dart
StreamBuilder<int>(
    stream: Reteno.appInbox.onMessagesCountChanged,
    builder: (context, snapshot) {
    if (snapshot.hasData) {
        return Text(snapshot.data.toString());
    }
    return const SizedBox.shrink();
    },
),
```

## Change Inbox Message Status on `OPENED`

```dart Dart
Reteno.appInbox.markAsOpened(message.id);
```

Also you can change all inbox messages status via single method without providing messages ids.

```dart Dart
Reteno.appInbox.markAllMessagesAsOpened();
```