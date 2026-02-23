# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p06 06_03_01_灰度图像分割.zh_en -BV1yb421q7yg_p6-

🎼。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_1.png)

Many image processing applications require analyzing objects within an image。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_3.png)

Such as measuring the size of these objects。Isolating regions of interest within an image is called segmentation。

The most common form of segmentation is binary， where pixels are labeled as belonging to either the foreground or background。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_5.png)

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_6.png)

However， for some applications like this X ray image of an arm。

 it is appropriate to have multiple labels for different objects in the same image。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_8.png)

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_9.png)

In this video， you'll practice segmenting grayscale images using a global threshold。

An adaptive threshold。 and a multi level threshold。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_11.png)

To begin， let's use a global threshold to segment the cracks from these images of concrete。

One of the most common and useful methods for segmenting images is to threshold them。

This means choosing an intensity value， then labeling pixels below this value as false。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_13.png)

And pixels above， as true。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_15.png)

Start by reading in one of the images。Converting it to grayscale。And viewing it using I am show。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_17.png)

The crack is much darker than the concrete。So segmenting it with a threshold should be possible。

You could investigate the pixel values and manually choose a threshold to separate the regions。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_19.png)

Alternatively。The function I am binaryized can choose an optimal value for you。

The result is a matrix。Where each pixel has a logical value of 0 for false and one for true。

Compare the result to the original image， using montage。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_21.png)

Side by side， it's clear to see that binizing an image turns dark pixels black for false and light pixels white for true。

However， because we are interested in the crack and not the solid concrete。

We should invert the black and white image using the logical not operator。This swaps the values。

 so the white foreground pixels represent the crack instead of the concrete。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_23.png)

You can now use the BW variable to calculate various properties。

 such as the total number of foreground pixels。To do this， use the NNZ function。

Which stands for number of nonzero elements。In this case。

 the crack covers nearly 8000 pixels of the image。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_25.png)

The binary image is known as a mask because you can overlay it onto the original image to mask out the false or black regions。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_27.png)

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_28.png)

To do this。First， create a copy of the image variable。

Then use logical indexing with your binary image to specify all pixels where the mask is not true and set them to zero intensity。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_30.png)

The result is an image of all zeroes， except where the mask was true。

You might be wondering how the threshold value was determined and what it was。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_32.png)

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_33.png)

The default behavior of IM binized is to use Ou's method。

Which finds a threshold value based on the distribution of pixel intensities。

Find this value using the gray Thrrush function。This returns a value between 0 and 1。

But you can convert it to an intensity value by multiplying by 2，55。Os's method often works well。

 but not always。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_35.png)

For instance， look at the result with this image of a thin crack。Here。

 the number of pixels representing the cracks is small。

 While the concrete dominates the image and has both brighter and darker regions。Therefore。

 Ou's method prefers to separate regions of the concrete。

Notice the chosen threshold is significantly higher than the previous image's value of 0。32。

In this case， specifying your own threshold value may be a better approach。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_37.png)

Do this using the second input of IM binize。Let's try 0。5。This looks a bit better。

 but can we improve it even more。To quickly test different values。

 it's helpful to add a numeric slider control。After you insert it。

 make sure the minimum and maximum values are set correctly。And the step size is appropriate。Now。

 a new threshold will appear whenever you adjust the slider。

Feel free to experiment with different binization thresholds for other images too。

In some applications， a globally applied threshold doesn't capture all of the objects you'd like。

To demonstrate。Let's binize this image of rice grains。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_39.png)

We don't need to invert the mask， as we did for the concrete images。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_41.png)

Because now， foreground objects are the high intensity grains。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_43.png)

At first， this result looks fine。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_45.png)

But look at the bottom of the mask。Some of the rice grains are missing。Why is this。

This image has uneven illumination。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_47.png)

This causes some of the grains at the bottom to have lower intensities than the background at the top。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_49.png)

Therefore， a single threshold value will not work for the entire image。Instead。

 the value needs to vary depending on the local average intensity。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_51.png)

This is called adaptive thresholdholding。You perform adaptive thresholdholding by specifying the method as a second input to the IM binaryized function。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_53.png)

This result looks much better。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_55.png)

All the rice grains are now captured by the mask。Some extra background pixels are marked as foreground。

 but youll learn techniques to address this later in the specialization。

Segmentation is not always binary。Some applications require multiple labels。

 such as this X ray image of an arm。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_57.png)

There are four clearly defined regions。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_59.png)

Background。tissueissue。Bone and metal。

![](img/019c6dc4d7b1f1d82eeb39c1f3637251_61.png)

Use the multi thrush function to find multiple thresholds。

Osu's method is still used to determine the threshold values。

But now you must specify the number of thresholds as a second input。Which in this case is three。

 because we need three thresholds to segment four regions。

The output of multithrush is a vector containing the threshold values。

To create a multi label segmented image。Pass the image and the vector of threshold values to the IM quantize function。

This returns a label matrix。Containing an integer number。Representing the region。

 each pixel belongs to。This variable is of type double。

So you can't view it in its current form because the values aren't scaled correctly。

The IM show function allows for a second input to specify how to scale the image values for viewing。

To use the full range of values， enter a set of empty brackets。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_63.png)

Now， you can clearly see the four regions found by the multi level thresholding。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_65.png)

From this label matrix， you can still isolate individual regions。To do this。

 create a variable for the new mask and have it store the logical array corresponding to one of the labels。

In this case， we'll isolate the third label， which is the bone。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_67.png)

Look at that。In conclusion， you now have multiple tools that you can use to segment regions of interest from a grayscale image。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_69.png)

Take some time to practice these techniques with other images and share your results in the forums。



![](img/019c6dc4d7b1f1d82eeb39c1f3637251_71.png)