---
layout: post
title:Adding margins to App Widgets
---

## Adding margins to App Widgets
Widgets should not generally extend to screen edges and should not visually be flush with other widgets, so you should add margins on all sides around your widget frame.

As of Android 4.0, app widgets are automatically given padding between the widget frame and the app widget's bounding box to provide better alignment with other widgets and icons on the user's home screen. To take advantage of this strongly recommended behavior, set your application's targetSdkVersion to 14 or greater.

It's easy to write a single layout that has custom margins applied for earlier versions of the platform, and has no extra margins for Android 4.0 and greater:
1. Set your application's targetSdkVersion to 14 or greater.
1. Create a layout such as the one below, that references a dimension resource for its margins:

```<FrameLayout
  android:layout_width="match_parent"
  android:layout_height="match_parent"
  android:padding="@dimen/widget_margin">
 
    <LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal"
    android:background="@drawable/my_widget_background">
    …
  </LinearLayout>



</FrameLayout>
```
1. Create two dimensions resources, one in res/values/ to provide the pre-Android 4.0 custom margins, and one in 
1. res/values-v14/ to provide no extra padding for Android 4.0 widgets:


```
res/values/dimens.xml:
<dimen name="widget_margin">8dp</dimen>
res/values-v14/dimens.xml:
<dimen name="widget_margin">0dp</dimen>
```

Another option is to simply build extra margins into your nine-patch background assets by default, and provide different nine-patches with no margins for API level 14 or later.
