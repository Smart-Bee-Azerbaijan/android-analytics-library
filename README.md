# Android analytics library

### Integration

**Step 1. Add the JitPack repository to your ```build.gradle``` file**

```
repositories {
    maven {
        ...

        url "https://jitpack.io"
    }
}


dependencies {
    implementation 'com.github.Smart-Bee-Azerbaijan:android-analytics-library:1.0.0'
}
```

**Step 2. Initialize SmartBeeAnalytics**

Create YourApp class that extends Application. Override the onCreate method, and initialize the SmartBeeAnalytics SDK with your credentials:

```
class YourApp extends Application {
     @Override
     public void onCreate() {
         super.onCreate();

         // Initialize your token
         SmartBeeAnalytics.instance().setToken("YOUR_TOKEN")
     }
}
```

**Important: Also call the setToken function when you get a new token**

**Step 3. Sending Events**

To send events to SmartBeeAnalytics, you can use the sendEvent method. Here's an example of how to use it:

```
 fun sendEvent() {
        // Create a HashMap to store event parameters (optional)
        val eventParameters = hashMapOf(
            "parametr1" to "Value1",
            "parametr2" to "Value2"
        )

        // Send the event to SmartBeeAnalytics
        SmartBeeAnalytics.instance().sendEvent(
            eventType = "Your event type",
            idHash = "Your id hash",
            utmSource = "Your utm source",
            utmCampaign = "Your utm campaign",
            parameters = eventParameters
        )
    }
```
Adjust the event type, idHash, utmSource, utmCampaign, and event parameters according to the events you want to track in YourApp.
