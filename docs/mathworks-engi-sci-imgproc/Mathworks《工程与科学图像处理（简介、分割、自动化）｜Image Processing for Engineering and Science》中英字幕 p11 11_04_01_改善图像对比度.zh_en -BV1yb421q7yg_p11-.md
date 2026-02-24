# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p11 11_04_01_改善图像对比度.zh_en -BV1yb421q7yg_p11-

。Improving image contrast is important for a wide range of applications。

 from medical diagnostics to autonomous driving。

![](img/ea33e4b9898103e4e8987c641d255383_1.png)

So how can you improve low contrast images to bring out details that are hard to see？



![](img/ea33e4b9898103e4e8987c641d255383_3.png)

To choose an effective approach for a given image， it helps to first view the image histogram。

Using this information， choose a contrast adjustment technique。If the resulting image is good enough。

 great， you are done。If not， you can try a new technique or combine techniques。

 iterating until you achieve the desired results。

![](img/ea33e4b9898103e4e8987c641d255383_5.png)

In this video， you'll use histogram stretching。And histogram reshaping to improve the contrast of gray scale and color images。



![](img/ea33e4b9898103e4e8987c641d255383_7.png)

Let's try it with this ankle X ray。

![](img/ea33e4b9898103e4e8987c641d255383_9.png)

The image appears dim， with the ankle， barely visible。



![](img/ea33e4b9898103e4e8987c641d255383_11.png)

Use the I M hist function to view the distribution of pixel intensities。

The values are accumulated towards the left of the histogram。In this 16 B image。

 the maximum intensity is only 13000， but the maximum possible intensity is over 60000。

The contrast seems low because the image is not taking advantage of the full pixel range。

To address this， you can stretch the histogram using the I am a just function to use the full range of intensities。

Great。😊，The new histogram uses the full numerical range and has many more pixels at higher intensity。

😊，Let's look at the image。

![](img/ea33e4b9898103e4e8987c641d255383_13.png)

This is a big improvement as the ankle is clearly visible。 However。

 the soft tissue in the muscle is still very dim， and the joint of the ankle is too bright。



![](img/ea33e4b9898103e4e8987c641d255383_15.png)

![](img/ea33e4b9898103e4e8987c641d255383_16.png)

Let's look at the stretched histogram， again。Most pixels still have very low intensity values。

Spreading the pixel intensities more evenly， could reveal more detail。

This process of redistributing pixel intensities throughout the entire histogram range is known as histogram equalization。

 which you can perform with the Hist EQ function。Now， the histogram is divided into 64 bins。

 and the pixel intensities are distributed in such a way that the new histogram is approximately flat。

Let's look at the new image。The darker areas have become brighter。

 but at the cost of increasing noise。Moreover， both bones and soft tissues lack details because the image as a whole has been brightened while local variation was lost。

 So how can we perform local equalization without amplifying noise。



![](img/ea33e4b9898103e4e8987c641d255383_18.png)

Rather than trying to equalize the histogram of the entire image。We can break it into tiles。

Each tile is equalized separately。And then blended together to form a final image。

This is called adaptive histogram equalization。

![](img/ea33e4b9898103e4e8987c641d255383_20.png)

You can perform adaptive histogram equalization with the adapt hist EQ function。啊。😮。

Most pixels still have low intensity。Let's compare this with the original image。



![](img/ea33e4b9898103e4e8987c641d255383_22.png)

The bone is slightly more visible now， but is still not bright enough to decipher the details。



![](img/ea33e4b9898103e4e8987c641d255383_24.png)

So far， you've tried three techniques to improve contrast。Histogram stretching。

Histogram equalization。And adaptive histogram equalization。

But we're still not completely satisfied with the results。 Instead， let's try combining techniques。



![](img/ea33e4b9898103e4e8987c641d255383_26.png)

The image with the stretched histogram is the best so far。



![](img/ea33e4b9898103e4e8987c641d255383_28.png)

Perhaps the darker areas of this image can be made brighter with adaptive histogram equalization。



![](img/ea33e4b9898103e4e8987c641d255383_30.png)

Let's combine these approaches by first stretching the original histogram。

Then reshaping it with adapt hisst E Q。The resulting image has great contrast。

Both the bone and the joint are clearly visible。

![](img/ea33e4b9898103e4e8987c641d255383_32.png)

So far， you've adjusted the contrast of grayscale images。

But contrast adjustment for color images is crucial for many applications such as automated driving。



![](img/ea33e4b9898103e4e8987c641d255383_34.png)

So how can you improve contrast in color images？Since the contrast is low。

 you can start with histogram stretching。However， when you do that。

 it returns an error because contrast adjustment functions expect a two dimensional image。

 whereas color images are composed of three different color channels。



![](img/ea33e4b9898103e4e8987c641d255383_36.png)

![](img/ea33e4b9898103e4e8987c641d255383_37.png)

The brightness of an RGB image is linked to all three channels。 Therefore。

 you can't change the brightness of the image without changing the colors of the image， too。 Instead。

 you need a color space where brightness is separated from color， like H S V。



![](img/ea33e4b9898103e4e8987c641d255383_39.png)

In the HSV color scale， the value channel corresponds to the image brightness。



![](img/ea33e4b9898103e4e8987c641d255383_41.png)

Let's try this in Matlab。Convert the image to HSV scale。

Extract the value channel and view the histogram。Notice that most pixels have low intensity。

Since you found the combined algorithm to be effective in grayscale images。

 apply it to the value channel to improve the histogram。

Replace the value channel of the original HSV image with the new value channel and convert the image back to RGB。

Now， let's compare it to the original image。

![](img/ea33e4b9898103e4e8987c641d255383_43.png)

The contrast has been greatly improved while preserving the color， and that's great。

This will allow the autonomous vehicle to detect the pedestrian at night and come to a stop。



![](img/ea33e4b9898103e4e8987c641d255383_45.png)

You've now seen how to apply three of the most common contrast adjustment techniques。



![](img/ea33e4b9898103e4e8987c641d255383_47.png)

There are many other functions included in Matlab for adjusting image contrast。

 which you can explore on your own。You're now ready to apply contrast adjustment to your images。



![](img/ea33e4b9898103e4e8987c641d255383_49.png)

。