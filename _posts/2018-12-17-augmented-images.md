---
layout: post
title: Augmented Images
---

 
Augmented Images in ARCore lets you build AR apps that can respond to 2D images, such as posters or product packaging, in the user's environment. You provide a set of reference images, and ARCore tracking tells you where those images are physically located in an AR session, once they are detected in the camera view.


**This following list of features helps you evaluate whether Augmented Images is suitable for your app:**

- Each image database can store feature point information for up to 1000 reference images.
- ARCore can track up to 20 images simultaneously in the environment, but it cannot track multiple instances of the same image.
- The physical image in the environment must be at least 15cm x 15cm and must be flat (for example, not wrinkled or wrapped around a bottle)
- Once tracked, ARCore provides estimates for position, orientation, and physical size. These estimates are continuously refined as ARCore gathers more data.
- ARCore cannot track a moving image, but it can resume tracking that image after it stops moving.
- All tracking happens on the device, so no internet connection is required. Reference images can be updated on-device or over the network without requiring an app update.



**Tips for selecting reference images**

- Augmented Images supports PNG and JPEG file formats. For JPEG files, avoid heavy compression for best performance.
- Detection is solely based on points of high contrast, so both color and black/white images are detected, regardless of whether a color or black/white reference image is used.
- The image's resolution should be at least 300 x 300 pixels.
- Using images with high resolution does not improve performance.
- Avoid images with sparse features.
- Avoid images with repetitive features.
- A good reference image is hard to spot with the human eye. Use the arcoreimg tool to get a score between 0 and 100 for each image. We recommend a score of at least 75. Here are two examples:



**Tips for creating the image database**

- The database stores a compressed representation of the reference images. Each image occupies ~6KB.
- It takes ~30ms to add an image to the database at runtime. Add images on a worker thread to avoid blocking the UI thread, or if possible, add images at compile time with the arcoreimg tool.
- If possible, specify the expected physical size of the image. This metadata improves tracking performance, especially for large physical images (over 75cm).
- Don't keep unused images in the database as there's a slight impact on system performance.
