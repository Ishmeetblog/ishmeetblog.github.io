---
published: false
layout: post
---
## The Basics of Widgets

To create an App Widget, you need the following:

1. AppWidgetProviderInfo object
1. Describes the metadata for an App Widget, such as the App Widget's layout, update frequency, and the AppWidgetProvider class. This should be defined in XML.
1. AppWidgetProvider class implementation
1. Defines the basic methods that allow you to programmatically interface with the App Widget, based on broadcast events. Through it, you will receive broadcasts when the App Widget is updated, enabled, disabled and deleted.

**View layout**
- Defines the initial layout for the App Widget, defined in XML.
- Additionally, you can implement an App Widget configuration Activity. This is an optional Activity that launches when the user adds your App Widget and allows them to modify App Widget settings at create-time.

The following sections describe how to set up each of these components.


```java
<receiver android:name="ExampleAppWidgetProvider" >
    <intent-filter>
        <action android:name="android.appwidget.action.APPWIDGET_UPDATE" />
    </intent-filter>
    <meta-data android:name="android.appwidget.provider"
               android:resource="@xml/example_appwidget_info" />
</receiver>
```

