# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p16 04_01_01_边缘检测.zh_en -BV1yb421q7yg_p16-

🎼。

![](img/de33ec5199c6b0a1366c81906d98203a_1.png)

Thresholding separates an image into foreground and background。



![](img/de33ec5199c6b0a1366c81906d98203a_3.png)

However， sometimes a single region will consist of multiple objects。

Edge detection isolates the boundaries between objects。

By removing the edges from the segmented image， you can separate overlapping regions。

Edges are also used to find shapes or patterns， such as corners or circles。



![](img/de33ec5199c6b0a1366c81906d98203a_5.png)

Edge detection requires a number of operations， including applying several spatial filters to the image and combining and processing the results。

Most edge detection algorithms are based on spatial filters that approximate the gradient of the image。

The sobel filter is the simplest such filter and is used by many algorithms。

 including the sobel method。The sobel filter calculates the gradient by comparing the intensities of the pixels in the neighborhood of the central pixel。

Large， positive or negative values could indicate an edge。

Values near zero indicate areas of more uniform intensity。

The filter shown emphasizes the horizontal edges。Applying the transpose of the filter will emphasize the vertical edges。

Combining the horizontal and vertical gradients shows all the potential edges。

The soble method calculates the magnitude and direction from the horizontal and vertical gradients。



![](img/de33ec5199c6b0a1366c81906d98203a_7.png)

The magnitude of the gradient is shown here。Finally。

 a threshold is applied to remove regions with low gradient values。

And the regions of high gradient are thin to a width of one pixel。

The details of these steps vary by algorithm。

![](img/de33ec5199c6b0a1366c81906d98203a_9.png)

The soble method computes a threshold similar to the approach in image segmentation。

There are many steps in the edge detection process， but in MATLb。

 you can perform them with just one function call。Let's try the edge function on a picture of some real coins to isolate the coins from the background。

The high resolution of the image captured a lot of detail on the faces of the coins。

 Since we are only interested in the outer edge， these other edges can be viewed as noise。

Just like with the background noise， slightly blurring the image before processing can improve the output。

A Gaussian blur is often used before edge detection。

Gausian filters weight the central pixel more heavily than the mean filter。

This removes smaller details while preserving the stronger edges。

The IM Gaus Filt function blurs the image without the need to create and apply a separate filter。

The default standard deviation for the Gaussian function is 0。5， but for higher resolution images。

 you'll need to experiment with larger values。Passing the blurred image to the edge function results in a binary image of coin edges。

 The soble method is the default。As with image segmentation。

 the threshold value can be adjusted to keep or remove more edges as needed。

The edge function can return the value it calculated， and you can use that as a starting point。

Let's increase the threshold value， slightly。

![](img/de33ec5199c6b0a1366c81906d98203a_11.png)

Some details inside the coin are being removed， but some of the fainter coin edges are also lost。



![](img/de33ec5199c6b0a1366c81906d98203a_13.png)

The canny method is another popular algorithm。It uses the same filter as the soble method。

 but processes and thresholds the output differently。



![](img/de33ec5199c6b0a1366c81906d98203a_15.png)

It will usually detect many more edges than the soble method。



![](img/de33ec5199c6b0a1366c81906d98203a_17.png)

This is useful if those details are important for your application。



![](img/de33ec5199c6b0a1366c81906d98203a_19.png)

The edge function includes many other popular edge detection methods beyond sobel and canny。

 including Pruit。Roberts and Laplian of Gaussian。Using edges to find round and nearly round objects is a common application。

And Matlab provides special purpose functions for this task。

The IM Find circles function segments an image by finding circular edges。



![](img/de33ec5199c6b0a1366c81906d98203a_21.png)

The Viz circles function can then be used to overlay the edges on the image。



![](img/de33ec5199c6b0a1366c81906d98203a_23.png)

In this video， you learned the basic ideas behind the soble E detection method。

You've also seen how a Gaussian filter is used to remove the smaller details without degrading larger edges。

Finally， you've learned to apply these techniques with functions included in MATLAb。



![](img/de33ec5199c6b0a1366c81906d98203a_25.png)

。