---
published: false
---
The `AppWidgetProviderInfo` defines the essential qualities of an App Widget, such as its minimum layout dimensions, its initial layout resource, how often to update the App Widget, and (optionally) a configuration Activity to launch at create-time. Define the `AppWidgetProviderInfo` object in an XML resource using a single `<appwidget-provider>` element and save it in the project's res/xml/ folder.

For example:
```
<appwidget-provider xmlns:android="http://schemas.android.com/apk/res/android"
    android:minWidth="40dp"
    android:minHeight="40dp"
    android:updatePeriodMillis="86400000"
    android:previewImage="@drawable/preview"
    android:initialLayout="@layout/example_appwidget"
    android:configure="com.example.android.ExampleAppWidgetConfigure"
    android:resizeMode="horizontal|vertical"
    android:widgetCategory="home_screen">
</appwidget-provider>
```
### Here's a summary of the <appwidget-provider> attributes:

The values for the minWidth and minHeight attributes specify the minimum amount of space the App Widget consumes by default. The default Home screen positions App Widgets in its window based on a grid of cells that have a defined height and width. If the values for an App Widget's minimum width or height don't match the dimensions of the cells, then the App Widget dimensions round up to the nearest cell size.
See the App Widget Design Guidelines for more information on sizing your App Widgets.
