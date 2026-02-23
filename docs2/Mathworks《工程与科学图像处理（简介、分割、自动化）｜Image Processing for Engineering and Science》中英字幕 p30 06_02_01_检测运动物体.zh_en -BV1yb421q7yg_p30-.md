# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p30 06_02_01_检测运动物体.zh_en -BV1yb421q7yg_p30-

🎼，Suppose you need to detect one or more moving objects on a complex background。

 such as this turkey walking around the Mathworks campus。



![](img/698fbd201fb3fb9e5b36ca83de700b46_1.png)

In each frame， there is no simple shape。Easy color distinctions。

Or clear clusters in the image to work with， to isolate the turkey。



![](img/698fbd201fb3fb9e5b36ca83de700b46_3.png)

However， in each frame， finding the difference between the background and the image as a whole。



![](img/698fbd201fb3fb9e5b36ca83de700b46_5.png)

Would isolate the turkey。This is because areas of the background subtract to zero。

While areas with the Turkey remain non zero。

![](img/698fbd201fb3fb9e5b36ca83de700b46_7.png)

So how do you get a background image to calculate this difference？

If you have one or more frames with just the background， you could use those。In this case。

 since the turkey is in every frame， you'll need to create the background image。

Since the turkey is moving around the entire time， every pixel location is background round for most of this video。

This means an average of all frames will approximate the background。

To calculate the average of all frames initialize a sum by converting the first frame to double。

Then use this variable in a loop， iteratively adding each remaining frame to it to find the total sum。

Don't forget to ensure your arithmetic is being done in data type double。Finally。

 divide the sum by the number of frames to get the average。Keep in mind。

 video processing code can take a bit of time to execute。



![](img/698fbd201fb3fb9e5b36ca83de700b46_9.png)

Notice the background image is a bit blurry。

![](img/698fbd201fb3fb9e5b36ca83de700b46_11.png)

This is not uncommon when averaging video frames due to camera shake or small movements in the background。



![](img/698fbd201fb3fb9e5b36ca83de700b46_13.png)

Let's see how to isolate the turkey by subtracting this average background from the rest of the frames and segmenting the result。



![](img/698fbd201fb3fb9e5b36ca83de700b46_15.png)

![](img/698fbd201fb3fb9e5b36ca83de700b46_16.png)

The first step is to choose some representative frames from the video。



![](img/698fbd201fb3fb9e5b36ca83de700b46_18.png)

Here we use the read function to extract one from the video object。And convert it to double。

 since we'll be using it in calculations。The average frame we just calculated is already data type double。

But if you save and reload it in the future， you'll need to make sure to convert it as well。



![](img/698fbd201fb3fb9e5b36ca83de700b46_20.png)

To isolate the turkey pixels， find the absolute value difference between the frame and the background。



![](img/698fbd201fb3fb9e5b36ca83de700b46_22.png)

You can see that the turkey stands out pretty well in the resulting image。



![](img/698fbd201fb3fb9e5b36ca83de700b46_24.png)

There are some artifacts which are due to the average background blurring。However。

 they're small enough relative to the turkey that it should not be too hard to segment。Remember。

 when segmenting videos， you have a lot of frames your function needs to work with。 So most likely。

 you'll need to repeat the process of calculating the difference from average on several representative frames in the video and develop a segmentation function that works well on all of them。



![](img/698fbd201fb3fb9e5b36ca83de700b46_26.png)

To save time here， we've already developed a segment turkey function using that process。



![](img/698fbd201fb3fb9e5b36ca83de700b46_28.png)

You can see it does a nice job of getting the outline of the turkey。

A common way to highlight detected objects is to place a bounding box around them。

Let's use the region props function on this mask to get the coordinates of a bounding box for the turkey。

And the insert shape function to add it to the original frame。When doing this。

 it is often helpful to specify a color， as well as adjust the line width to improve the visibility of the bounding box。



![](img/698fbd201fb3fb9e5b36ca83de700b46_30.png)

Great。😊。

![](img/698fbd201fb3fb9e5b36ca83de700b46_32.png)

Now let's put all this together to detect the turkey as it moves in the video。



![](img/698fbd201fb3fb9e5b36ca83de700b46_34.png)

Create and open a new video writer object。And wrap the algorithm we just developed in a loop。

Adjusting the read function to use the loop index。And adding code to write each frame to the new video at the end。

Finally， add code to close the object and you're ready to process the video。Don't forget。

 video processing code can take some time to execute。



![](img/698fbd201fb3fb9e5b36ca83de700b46_36.png)

As you check your results， you may notice frames where the segmentation seems to be incorrect。



![](img/698fbd201fb3fb9e5b36ca83de700b46_38.png)

You may need to go back and refine your steps。However， perfection is rarely possible。In summary。

 if you need to isolate a moving object from a relatively static but complex background。

 using background subtraction is often a good approach。



![](img/698fbd201fb3fb9e5b36ca83de700b46_40.png)

![](img/698fbd201fb3fb9e5b36ca83de700b46_41.png)

In general， you'll need to work in double data type for calculations。

Choose a frame showing only the background or create one by averaging many frames。

Then you find the absolute difference between each frame。In the background。 and segment the results。



![](img/698fbd201fb3fb9e5b36ca83de700b46_43.png)