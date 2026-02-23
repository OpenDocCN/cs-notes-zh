# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p15 03_01_01_使用空间滤波降噪.zh_en -BV1yb421q7yg_p15-

🎼。

![](img/838dae2dfba21495192a6deff0467351_1.png)

Adjusting an image's contrast can bring out important details that were hard to see。



![](img/838dae2dfba21495192a6deff0467351_3.png)

However， while the same adjustment makes the difference between the crack and the concrete much more visible。

 the subtle variations due to noise become much more significant。

Dealing with noise is a common problem in science and engineering。



![](img/838dae2dfba21495192a6deff0467351_5.png)

In this video， you'll learn about spatial filtering and how it can be used to remove noise from an image。



![](img/838dae2dfba21495192a6deff0467351_7.png)

Noise in an image is anything that makes the subject of the image more difficult to distinguish。



![](img/838dae2dfba21495192a6deff0467351_9.png)

In this concrete crack image， the texture of the concrete produces variations in the pixel values。

When these differences are increased by contrast adjustment。

They could become as significant as the crack。An approach to reducing noise is to apply spatial filtering。



![](img/838dae2dfba21495192a6deff0467351_11.png)

Spatial filtering changes the value of a pixel based on the values of other pixels in a neighborhood around it。

A filter is a matrix that acts like a mask。When placed over an image。

 it creates a window or neighborhood around a pixel。

The value of the central pixel is then modified based on the values of the other pixels in the neighborhood。

For example， an averaging filter takes the average value of the pixels in the neighborhood and assigns that as the value of the central pixel。

The filters then moved to the next pixel， and applied there。

This makes spatial filtering a sliding window operation。

Taking the average value of the pixels in the neighborhood。

Results in a reduced pixel to pixel variation。To create an averaging filter。

 you'll need to specify the size of the window。

![](img/838dae2dfba21495192a6deff0467351_13.png)

![](img/838dae2dfba21495192a6deff0467351_14.png)

And how to treat the boundaries of the image。The default filter size of 3 by3 works well for low resolution images。

 Or when you only want to include the nearest neighboring pixels。



![](img/838dae2dfba21495192a6deff0467351_16.png)

For higher resolution images or to include information from a larger region。

 you can increase the filter size。

![](img/838dae2dfba21495192a6deff0467351_18.png)

Near the boundaries， part of the window will extend outside the image。

You'll need to provide values outside or pad the boundary of the image。



![](img/838dae2dfba21495192a6deff0467351_20.png)

There are several options。 You can use the values of the nearest border pixels。

Mirror the image across the border。Or just use a set value。



![](img/838dae2dfba21495192a6deff0467351_22.png)

You can also perform nonlinear filtering by taking the median of the values in the window instead of the mean。



![](img/838dae2dfba21495192a6deff0467351_24.png)

This reduces the effect of pixels that vary greatly from their neighbors。

 It also helps to preserve edges。

![](img/838dae2dfba21495192a6deff0467351_26.png)

Let's use Matlab to apply an averaging filter to the crack image。



![](img/838dae2dfba21495192a6deff0467351_28.png)

To create a3 by3 averaging filter， use the F special function。Specify the type of filter and size。

Here F is a 3 by3 averaging filter。The I M filter function applies the filter to the image。

The default behavior is to pad the boundaries with zero values。

Use a montage to display the original and filtered images， and run the code。



![](img/838dae2dfba21495192a6deff0467351_30.png)

The crack is slightly blurred， and the background looks smoother。



![](img/838dae2dfba21495192a6deff0467351_32.png)

To see the effect this has on the segmentation， let's adjust the contrast and use IM binaryize on the filtered image。

Then display the segmented image。

![](img/838dae2dfba21495192a6deff0467351_34.png)

That's quite an improvement from the original segmentation。



![](img/838dae2dfba21495192a6deff0467351_36.png)

Reducing noise decreased the background variations that were originally amplified during contrast adjustment。



![](img/838dae2dfba21495192a6deff0467351_38.png)

In this video， you learned what spatial filtering is and how it can be used to remove noise from an image。

You've also seen how to create and use spatial filters in MatTLb。Later。

 you'll see other uses of this powerful image processing technique。



![](img/838dae2dfba21495192a6deff0467351_40.png)