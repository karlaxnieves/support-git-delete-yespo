---
title: Preventing Possible WorkManager Issues
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Preventing Possible WorkManager Issues | Support
  description: Read how to remove your default WorkManager initializer
  robots: index
next:
  description: ''
---
We use WorkManager in Reteno SDK. If you are using WorkManager in your project, you can face WorkManager initialization issues.

If you do, consider removing default WorkManager initializer:

```xml
 <provider
    android:name="androidx.startup.InitializationProvider"
    android:authorities="${applicationId}.androidx-startup"
    tools:node="remove">
 </provider>
```

And implement a configuration provider in your Application class:

```kotlin Kotlin
class MyApplication() : Application(), Configuration.Provider {
     override fun getWorkManagerConfiguration() =
           Configuration.Builder()
                .setMinimumLoggingLevel(android.util.Log.INFO)
                .build()
}
```
```java
class MyApplication extends Application implements Configuration.Provider {
    @Override
    public Configuration getWorkManagerConfiguration() {
        return new Configuration.Builder()
                .setMinimumLoggingLevel(android.util.Log.INFO)
                .build();
    }
}
```

You can find more information in official <a rel="nofollow" href="[WorkManager custom initialization documentation](https://developer.android.com/guide/background/persistent/configuration/custom-configuration)"> WorkManager custom initialization documentation </a>.