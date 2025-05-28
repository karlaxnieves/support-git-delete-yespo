---
title: In-App Lifecycle Callbacks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: In-App Lifecycle Callbacks | Yespo Guide
  description: Follow our manual to subscribe to In-App message lifecycle callbacks
  robots: index
next:
  description: ''
---
Since Reteno SDK 2.0.2 you can subscribe to In-App messages lifecycle.

You get callbacks:

* before In-App message is displayed
* right after In-App message is displayed
* before In-App message is closed
* after In-App message is closed
* if an error during displaying In-App message occurred

In these callbacks you also receive a data model which contains information whether In-App message was displayed via display rules or push notification click, ID or interaction ID of In-App message, and some other data which may be useful.

To subscribe to In-App message lifecycle callbacks you have to call `setInAppLifecycleCallback(InAppLifecycleCallback)` from `Reteno` interface.

**2nd Android SDK Version Callbacks Settings:**

```kotlin
val reteno = (application as RetenoApplication).getRetenoInstance()
reteno.setInAppLifecycleCallback(object : InAppLifecycleCallback {
    override fun beforeDisplay(inAppData: InAppData) {
        // ...
    }

    override fun onDisplay(inAppData: InAppData) {
        // ...
    }

    override fun beforeClose(closeData: InAppCloseData) {
        // ...
    }

    override fun afterClose(closeData: InAppCloseData) {
        // ...
    }

    override fun onError(errorData: InAppErrorData) {
        // ...
    }
})
```
```java
Reteno reteno = ((RetenoApplication) getApplication()).getRetenoInstance();
reteno.setInAppLifecycleCallback(new InAppLifecycleCallback() {
    @Override
    public void beforeDisplay(@NonNull InAppData inAppData) {
        // ...
    }

    @Override
    public void onDisplay(@NonNull InAppData inAppData) {
        // ...
    }

    @Override
    public void beforeClose(@NonNull InAppCloseData closeData) {
        // ...
    }

    @Override
    public void afterClose(@NonNull InAppCloseData closeData) {
        // ...
    }

    @Override
    public void onError(@NonNull InAppErrorData errorData) {
        // ...
    }
});
```

**3rd Android SDK Version Callbacks Settings:**

```kotlin
Reteno.instance.setInAppLifecycleCallback(object : InAppLifecycleCallback {
    override fun beforeDisplay(inAppData: InAppData) {
        // ...
    }

    override fun onDisplay(inAppData: InAppData) {
        // ...
    }

    override fun beforeClose(closeData: InAppCloseData) {
        // ...
    }

    override fun afterClose(closeData: InAppCloseData) {
        // ...
    }

    override fun onError(errorData: InAppErrorData) {
        // ...
    }
})
```
```java
Reteno.getInstance().setInAppLifecycleCallback(new InAppLifecycleCallback() {
    @Override
    public void beforeDisplay(@NonNull InAppData inAppData) {
        // ...
    }

    @Override
    public void onDisplay(@NonNull InAppData inAppData) {
        // ...
    }

    @Override
    public void beforeClose(@NonNull InAppCloseData closeData) {
        // ...
    }

    @Override
    public void afterClose(@NonNull InAppCloseData closeData) {
        // ...
    }

    @Override
    public void onError(@NonNull InAppErrorData errorData) {
        // ...
    }
});
```

To unsubscribe pass a `null` to `setInAppLifecycleCallback` function.
