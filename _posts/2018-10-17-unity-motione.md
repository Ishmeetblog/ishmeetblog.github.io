---
layout: post
title: Playing with Motion Tracking in Unity3D
---



In the app we will be building, we will not be anchoring the objects to a plane as we are just focussing on the motion tracking component of ARCore and not the complete environmental understanding.

### Step 1: Open Unity3D and create a new project names ARCore102. Make sure to select 3D in the template section.


![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*PWCHzpTnqrwtJlO8wME0yA.png)


### Step 2: After the project is created, head over to Unity->Unity Preferences->External Tools. Add the path of Android SDK and Android JDK taken from Android Studio into the respective fields.



![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*2W6TaiKA9hMYa9cOqqMPsA.png)


Step 3: Go to File->Build Settings, select Android in the Platforms list. Then click Switch Platform. The unity logo should appear in front of Android in the platforms list.



![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*3ftP0Cuf0LYgVy8YFV1t3g.png)




Step 5: Right click in the Assets window->Import Package->Custom Package and select the downloaded ARCore SDK.



![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*7wokAXatLbriO8SLvLlqkw.png)




Step 6: Click on All and then Import in the dialog box that appears.




![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*MEnCheeBY0CgGRjKEj5q2A.png)



Step 7: The Asset window should look like this.




![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*WmQTB5Xb0a4pTbhz2ScP-Q.png)



Step 8: Go to File-> Build Settings and click on Player Settings.



![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*4oK5ApYNqZhuYbB_Jct23A.png)




Step 9: The following window will appear in the Inspector.




![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*rPagmUUtBrDhbBQebgdj6Q.png)


step 10: Save the scene and build the app. Test the app on your Android device and play with it.








