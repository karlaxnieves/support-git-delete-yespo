---
title: iOS App Inbox
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
App Inbox is similar to an email inbox but is designed for direct messages from an app. As opposed to push notifications, it allows customers to keep promotions and browse a chronological list of messages at any time.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3c083e1-Frame_2483.png",
        "Frame 2483.png",
        808
      ],
      "align": "center",
      "sizing": "smart"
    }
  ]
}
[/block]


With the Reteno App Inbox, there is no default UI. This means with a few lines of code, you can connect Reteno with your inbox.

> 📘 Note
> 
> SDK Version App Inbox is available in version **1.2.0** and later.

### Reteno App Inbox

To get an instance to the `App Inbox` object, you need to use the `Reteno.inbox()` call which you can see below:

```swift
let inbox: AppInbox = Reteno.inbox()
```

### Downloading new messages

```swift
// If  `page`  or  `pageSize`  is not specified, then all messages will be returned
// If `status` is not specified, all messages will be returned. 
Reteno.inbox().downloadMessages(page: 1, pageSize: 10, status: .opened) { [weak self] result in
    switch result {
    case .success(let response):
        // handle messages
        self?.messages = response.messages
        // or totalPages count `response.totalPages`
                
    case .failure(let error):
        // handle error
    }
}
```

Available statuses for downloading

```swift
public enum AppInboxMessagesStatus: String {
    case opened = "OPENED"
    case unopened = "UNOPENED"
}
```

Reteno inbox message attributes:

```swift
public struct Reteno.AppInboxMessage {
  let id: String
  let createdDate: Date
  let title: String
  let content: String
  let imageURL: URL?
  let linkURL: URL?
  let isNew: Bool
}
```

### Get inbox unread messages count

```swift
Reteno.inbox().onUnreadMessagesCountChanged = { count in
  // handle changed count
}
```

### Change inbox messages status on `OPENED`

```swift
Reteno.inbox().markAsOpened(messageIds: ["message_id"]) { result in
    switch result {
    case .success:
        // handle success
                
    case .failure(let error):
        // handle error
    }
}
```

Also you can change all inbox messages status via single method without providing messages ids.

```swift
Reteno.inbox().markAllAsOpened { result in
    switch result {
    case .success:
        // handle success
                
    case .failure(let error):
        // handle error
    }
}
```