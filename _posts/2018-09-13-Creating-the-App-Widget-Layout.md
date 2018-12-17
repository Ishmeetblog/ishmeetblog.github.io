---
layout: post
title: Creating the App Widget Layout
---

## Creating the App Widget Layout

You must define an initial layout for your App Widget in XML and save it in the project's res/layout/ directory. You can design your App Widget using the View objects listed below, but before you begin designing your App Widget, please read and understand the App Widget Design Guidelines.

Creating the App Widget layout is simple if you're familiar with Layouts. However, you must be aware that App Widget layouts are based on RemoteViews, which do not support every kind of layout or view widget.

A RemoteViews object (and, consequently, an App Widget) can support the following layout classes:

- FrameLayout
- LinearLayout
- RelativeLayout
- GridLayout

**And the following widget classes:**

- AnalogClock
- Button
- Chronometer
- ImageButton
- ImageView
- ProgressBar
- TextView
- ViewFlipper
- ListView
- GridView
- StackView
- AdapterViewFlipper
- Descendants of these classes are not supported.


RemoteViews also supports ViewStub, which is an invisible, zero-sized View you can use to lazily inflate layout resources at runtime.
