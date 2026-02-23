# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p10 10_04_02_图像对比度与直方图.zh_en -BV1yb421q7yg_p10-

🎼，Image contrast refers to the difference between the dark and bright areas of an image。

An image with good contrast has clear separation between the foreground and background objects。



![](img/289cad6dda99768e27c0d6625ea3189e_1.png)

While an image with poor contrast will have less distinction between objects。



![](img/289cad6dda99768e27c0d6625ea3189e_3.png)

Like in this underexposed image。But don't worry， the details are still there。

There is no technical definition for good or bad image contrast。

By comparing the intensities of pixels and a few images。

 we can get a feel for when an image is ready to work with。



![](img/289cad6dda99768e27c0d6625ea3189e_5.png)

Versus when it will require some adjustment。

![](img/289cad6dda99768e27c0d6625ea3189e_7.png)

While this video will focus on gray scale images， the techniques can be applied to color images plain by plane。



![](img/289cad6dda99768e27c0d6625ea3189e_9.png)

Let's look at a simple example。This image of rice grains has good contrast。

The lighter grains stand out clearly against the dark background。

 and there is a well defined edge to each grain。

![](img/289cad6dda99768e27c0d6625ea3189e_11.png)

Looking at individual pixel intensity values shows the local contrast。

You can see a definite change from the pixels of the grains， with values above 200。To the background。

 pixels where the values are near 100。An image histogram is a way to see all the pixel values at once。

This plot shows how many pixels in the image take on each of the possible intensity values from 0 to 2。

55。For this image， there are several peaks。The peak on the right hand side represents the pixels in the rice grains。

 While the other peaks are associated with the background。

Note that the background in the bottom third of the image is much darker than the background in the rest of the image。



![](img/289cad6dda99768e27c0d6625ea3189e_13.png)

Let's take another look at the underexposed picture of the foozeball table。



![](img/289cad6dda99768e27c0d6625ea3189e_15.png)

Images with poor contrast like this one often require adjustment before other image processing techniques can be applied。



![](img/289cad6dda99768e27c0d6625ea3189e_17.png)

The histogram shows that nearly all the pixels have values near the low end of the intensity range。

To see the details in the image， the pixel values can be changed to stretch the histogram across the intensity range。

This linear scaling is one of the simplest ways of adjusting image contrast。



![](img/289cad6dda99768e27c0d6625ea3189e_19.png)

The result is an improved image where the details that were hidden before are now visible。

In the next video， you'll learn how to do this and other more complex adjustments in Matlab。



![](img/289cad6dda99768e27c0d6625ea3189e_21.png)

。