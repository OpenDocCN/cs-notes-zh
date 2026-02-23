# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p08 08_03_03_彩色图像阈值处理.zh_en -BV1yb421q7yg_p8-

🎼，Segmenting images using color can provide important information， like which blueberries are ripe。

But segmenting color images usually requires some trial and error。

This is because it's difficult to determine which color space and threshold values to use。

In this video， you'll use the color Thr app to quickly try different segmentation approaches。

Start by importing the blueberry image。Then navigate to the apps tab。

Notice that there are a wide variety of apps related to image processing。

 including several that you will explore in this specialization。Let's open the color Thr app。

Once you've opened the app， the first thing you need to do is load the image。For this example。

 load the image from the workspace。Next， you're prompted to choose a color space for the segmentation。

Often， the HSV and LAB color spaces are good starting points。

The goal is to isolate the blue blueberries from the rest of the image。

It looks like blue might be well separated in the HSV point cloud。 So let's start there。



![](img/cb71c6364d74a0634508d307b4a8ba51_1.png)

Notice that the three channels for HSV are represented by these sliders on the right。

You can change the ranges of the sliders and immediately see the effects of the thresholding on the image。

Let's try to isolate the ripe blueberries by moving the thresholds on the H value to only include what appears to be blue。

This result looks promising。We only see blue coming through the mask。

But how can you know that you're not accidentally removing some regions of interest。



![](img/cb71c6364d74a0634508d307b4a8ba51_3.png)

The app includes controls to change the background opacity and color。

Regions where the mask is false appear opaque， helping you determine if your thresholds are appropriate。

You can also view the binary mask。This often helps you find small imperfections in the segmentation that you may need to address later。



![](img/cb71c6364d74a0634508d307b4a8ba51_5.png)

For example， some of the small regions appear to be ripe blueberries obscured by leaves。

 while others are not。

![](img/cb71c6364d74a0634508d307b4a8ba51_7.png)

Later， you'll learn how to refine an initial mask and analyze the regions。



![](img/cb71c6364d74a0634508d307b4a8ba51_9.png)

The HSV color space worked well with this image。But you may need to try multiple color spaces when segmenting your images。

Select new Col space to try another approach。Your previous work is maintained so you can compare the results。

Once you' are satisfied with the results， you can export the segmented image and mask to the workspace for further analysis。

You might be wondering， do I have to do this every time。

 or how can I be sure to reproduce the same result。By exporting the auto generated function。

 you'll have a record to the steps you took and a function you can apply to other images。

It's a good idea to give the function a descriptive name， and then save it。

Now that you work through this example， import some of your own color images and try to segment them in different color spaces。

Post your results in the forums and share the approach you took。



![](img/cb71c6364d74a0634508d307b4a8ba51_11.png)

。