Using the AppWidgetProvider Class
The AppWidgetProvider class extends BroadcastReceiver as a convenience class to handle the App Widget broadcasts. The AppWidgetProvider receives only the event broadcasts that are relevant to the App Widget, such as when the App Widget is updated, deleted, enabled, and disabled. When these broadcast events occur, the AppWidgetProvider receives the following method calls:

`onUpdate()`

_This is called to update the App Widget at intervals defined by the updatePeriodMillis attribute in the AppWidgetProviderInfo (see Adding the AppWidgetProviderInfo Metadata above). This method is also called when the user adds the App Widget, so it should perform the essential setup, such as define event handlers for Views and start a temporary Service, if necessary. However, if you have declared a configuration Activity, this method is not called when the user adds the App Widget, but is called for the subsequent updates. It is the responsibility of the configuration Activity to perform the first update when configuration is done. (See Creating an App Widget Configuration Activity below.)_

`onAppWidgetOptionsChanged()`
-
This is called when the widget is first placed and any time the widget is resized. You can use this callback to show or hide content based on the widget's size ranges. You get the size ranges by calling getAppWidgetOptions(), which returns a Bundle that includes the following:

- `OPTION_APPWIDGET_MIN_WIDTH`—Contains the lower bound on the current width, in dp units, of a widget instance.
- `OPTION_APPWIDGET_MIN_HEIGHT`—Contains the lower bound on the current height, in dp units, of a widget instance.
- `OPTION_APPWIDGET_MAX_WIDTH`—Contains the upper bound on the current width, in dp units, of a widget instance.
- `OPTION_APPWIDGET_MAX_HEIGHT`—Contains the upper bound on the current height, in dp units, of a widget instance.

This callback was introduced in API Level 16 (Android 4.1). If you implement this callback, make sure that your app doesn't depend on it since it won't be called on older devices.

`onDeleted(Context, int[])`

This is called every time an App Widget is deleted from the App Widget host.

`onEnabled(Context)`
This is called when an instance the App Widget is created for the first time. For example, if the user adds two instances of your App Widget, this is only called the first time. If you need to open a new database or perform other setup that only needs to occur once for all App Widget instances, then this is a good place to do it.
`onDisabled(Context)`
This is called when the last instance of your App Widget is deleted from the App Widget host. This is where you should clean up any work done in `onEnabled(Context)`, such as delete a temporary database.
`onReceive(Context, Intent)`
This is called for every broadcast and before each of the above callback methods. You normally don't need to implement this method because the default AppWidgetProvider implementation filters all App Widget broadcasts and calls the above methods as appropriate.

The most important AppWidgetProvider callback is `onUpdate()` because it is called when each App Widget is added to a host (unless you use a configuration Activity). If your App Widget accepts any user interaction events, then you need to register the event handlers in this callback. If your App Widget doesn't create temporary files or databases, or perform other work that requires clean-up, then `onUpdate()` may be the only callback method you need to define. For example, if you want an App Widget with a button that launches an Activity when clicked, you could use the following implementation of AppWidgetProvider: