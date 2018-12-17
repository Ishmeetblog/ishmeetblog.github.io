---
layout: post
title: Tips for optimizing tracking
---


- The physical image must occupy 40% of the camera image. You can prompt users to fit the physical image in their camera frame with the FitToScan asset. See the Augmented Images sample app for an example of this prompt.
- When an image is initially detected by ARCore, and no expected physical size was specified, its tracking state will be paused. This means that ARCore has recognized the image, but has not gathered enough data to estimate its location in 3D space. Developers should not use the image's pose and size estimates until the image's tracking state is tracking.

