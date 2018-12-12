---
layout: post
title: Basics of Widgets!
published: true
---



### To create an App Widget, you need the following:

1. AppWidgetProviderInfo object
1. Describes the metadata for an App Widget, such as the App Widget's layout, update frequency, and the AppWidgetProvider class. This should be defined in XML.
1. AppWidgetProvider class implementation
1. Defines the basic methods that allow you to programmatically interface with the App Widget, based on broadcast events. Through it, you will receive broadcasts when the App Widget is updated, enabled, disabled and deleted.

**View layout**
- Defines the initial layout for the App Widget, defined in XML.
- Additionally, you can implement an App Widget configuration Activity. This is an optional Activity that launches when the user adds your App Widget and allows them to modify App Widget settings at create-time.

The following sections describe how to set up each of these components.


```
<receiver android:name="ExampleAppWidgetProvider" >
    <intent-filter>
        <action android:name="android.appwidget.action.APPWIDGET_UPDATE" />
    </intent-filter>
    <meta-data android:name="android.appwidget.provider"
               android:resource="@xml/example_appwidget_info" />
</receiver>
```


The `<receiver>` element requires the android:name attribute, which specifies the AppWidgetProvider used by the App Widget.

The `<intent-filter>` element must include an <action> element with the android:name attribute. This attribute specifies that the AppWidgetProvider accepts the ACTION_APPWIDGET_UPDATE broadcast. This is the only broadcast that you must explicitly declare. The AppWidgetManager automatically sends all other App Widget broadcasts to the AppWidgetProvider as necessary.

The `<meta-data>` element specifies the AppWidgetProviderInfo resource and requires the following attributes:

```
android:name - Specifies the metadata name. Use android.appwidget.provider to identify the data as the AppWidgetProviderInfo descriptor.
android:resource - Specifies the AppWidgetProviderInfo resource location.
```