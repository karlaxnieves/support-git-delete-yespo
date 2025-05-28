---
title: Android App Inbox
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

With the Reteno App Inbox, there is no default UI. This means with a few lines of code, you can connect Reteno with your inbox.

> 📘 Note
>
> SDK Version App Inbox is available in version 1.2.0 and later.

## Reteno App Inbox

To get an instance to the `AppInbox` object, you need to use the `Reteno` instance:

```kotlin
val appInbox = reteno.appInbox
```
```java
AppInbox appInbox = reteno.getAppInbox()
```

## Downloading New Messages

```kotlin
// If  `page`  or  `pageSize`  is not specified, then all messages will be returned
// If `status` filter is not specified, then messages won't be filtered by status
appInbox.getAppInboxMessages(page: Int?, pageSize: Int?, status: AppInboxStatus?, object :
RetenoResultCallback<AppInboxMessages> {
    override fun onSuccess(result: AppInboxMessages) {
        val messages = result.messages
        val totalPages = result.totalPages
```
```java
// If  `page`  or  `pageSize`  is not specified, then all messages will be returned
// If `status` filter is not specified, then messages won't be filtered by status
appInbox.getAppInboxMessages(@Nullable Integer page, @Nullable Integer pageSize, @Nullable
AppInboxStatus status, new RetenoResultCallback<AppInboxMessages>() {
    @Override
    public void onSuccess(AppInboxMessages result) {
        List<AppInboxMessage> messages = result.getMessages();
```

The result is an instance of the `AppInboxMessages` class:

```kotlin
data class AppInboxMessages(
    val messages: List<AppInboxMessage>,
    val totalPages: Int
)
```

Reteno inbox message attributes:

```kotlin
data class AppInboxMessage(
    val id: String,
    val title: String,
    val createdDate: String,
    val isNewMessage: Boolean,
    val content: String?,
    val imageUrl: String?,
    val linkUrl: String?,
    val category: String?,
    val status: AppInboxStatus?,
    val customData: Map<String, String>?
)
```

## Get Inbox Unread Messages Count

```kotlin
appInbox.getAppInboxMessagesCount(object : RetenoResultCallback<Int> {
    override fun onSuccess(count: Int) {
        // handle count
    }
    override fun onFailure(statusCode: Int?, response: String?, throwable: Throwable?) {
        // handle error
    }
})
```
```java
appInbox.getAppInboxMessagesCount(new RetenoResultCallback<Integer>() {
    @Override
    public void onSuccess(Integer count) {
        // handle count
    }
    @Override
    public void onFailure(@Nullable Integer statusCode, @Nullable String response, @Nullable Throwable throwable) {
        // handle error
    }
});
```

## Subscribe on Inbox Unread Messages Count

```java
appInbox.subscribeOnMessagesCountChanged(new RetenoResultCallback<Integer>() {
    @Override
    public void onSuccess(Integer count) {
        // handle count
    }
    @Override
    public void onFailure(@Nullable Integer statusCode, @Nullable String response, @Nullable Throwable throwable) {
        // handle error
    }
});
```
```kotlin
appInbox.subscribeOnMessagesCountChanged(object : RetenoResultCallback<Int> {
    override fun onSuccess(count: Int) {
        // handle count
    }
    override fun onFailure(statusCode: Int?, response: String?, throwable: Throwable?) {
        // handle error
    }
})
```

> 📘 Note
>
> Don't forget to unsubscribe

```kotlin
// pass callback from subscribeOnMessagesCountChanged 
appInbox.unsubscribeMessagesCountChanged(callback: RetenoResultCallback<Int>)
// or
appInbox.unsubscribeAllMessagesCountChanged()
```
```java
// pass callback from subscribeOnMessagesCountChanged 
appInbox.unsubscribeMessagesCountChanged(RetenoResultCallback<Int> callback);
// or
appInbox.unsubscribeAllMessagesCountChanged();
```

## Change Inbox Message Status on `OPENED`

The status will be saved and sent during the next cache push session. See [Force push locally cached data](https://docs.yespo.io/reference/android-user-behaviour#force-push-locally-cached-data).

```kotlin
appInbox.markAsOpened(messageId: String)
```
```java
appInbox.markAsOpened(String messageId);
```

Also you can change all inbox messages status via single method without providing messages ids.

```kotlin
appInbox.markAllMessagesAsOpened(object : RetenoResultCallback<Unit> {
    override fun onSuccess(result: Unit) {
        // handle success
    }
    override fun onFailure(statusCode: Int?, response: String?, throwable: Throwable?) {
        // hande error
    }
})
```
```java
appInbox.markAllMessagesAsOpened(new RetenoResultCallback<Unit>() {
    @Override
    public void onSuccess(Unit result) {
        // handle success
    }
    @Override
    public void onFailure(@Nullable Integer statusCode, @Nullable String response, @Nullable Throwable throwable) {
        // handle error
    }
});
```
