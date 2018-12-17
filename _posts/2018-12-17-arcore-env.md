---
layout: post
title: How is Arcore Superior from others
---
Enviroment understanding with arcore


## Motion tracking


As your phone moves through the world, ARCore uses a process called concurrent odometry and mapping, or COM, to understand where the phone is relative to the world around it. ARCore detects visually distinct features in the captured camera image called feature points and uses these points to compute its change in location. The visual information is combined with inertial measurements from the device's IMU to estimate the pose (position and orientation) of the camera relative to the world over time.

By aligning the pose of the virtual camera that renders your 3D content with the pose of the device's camera provided by ARCore, developers are able to render virtual content from the correct perspective. The rendered virtual image can be overlayed on top of the image obtained from the device's camera, making it appear as if the virtual content is part of the real world.


## Environmental understanding


ARCore is constantly improving its understanding of the real world environment by detecting feature points and planes.

ARCore looks for clusters of feature points that appear to lie on common horizontal or vertical surfaces, like tables or walls, and makes these surfaces available to your app as planes. ARCore can also determine each plane's boundary and make that information available to your app. You can use this information to place virtual objects resting on flat surfaces.

Because ARCore uses feature points to detect planes, flat surfaces without texture, such as a white wall, may not be detected properly.


## Light estimation


ARCore can detect information about the lighting of its environment and provide you with the average intensity and color correction of a given camera image. This information lets you light your virtual objects under the same conditions as the environment around them, increasing the sense of realism.




## User interaction


ARCore uses hit testing to take an (x,y) coordinate corresponding to the phone's screen (provided by a tap or whatever other interaction you want your app to support) and projects a ray into the camera's view of the world, returning any planes or feature points that the ray intersects, along with the pose of that intersection in world space. This allows users to select or otherwise interact with objects in the environment.
