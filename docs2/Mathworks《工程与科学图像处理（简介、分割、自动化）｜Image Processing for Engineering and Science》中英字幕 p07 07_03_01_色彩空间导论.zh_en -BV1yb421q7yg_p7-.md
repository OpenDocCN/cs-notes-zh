# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p07 07_03_01_色彩空间导论.zh_en -BV1yb421q7yg_p7-

🎼。

![](img/3a60ce59028e9e948454330d69eed989_1.png)

Consider using imaging to determine the best time to pick ripe fruits， like these blueberries。

You might guess that you can identify the blue ones by looking at the blue channel of the RGB color space。

But the B values of blue， ripe and green unrie blueberries are actually quite close。



![](img/3a60ce59028e9e948454330d69eed989_3.png)

Situations like these and differences in shadow and lighting make it difficult to perform color thresholdholding using the RGB color space。

These photos show the same stop sign at different times of day。

But notice the significant change in all three RGB component values。



![](img/3a60ce59028e9e948454330d69eed989_5.png)

Let's look at the unri blueberry color to see why this is。Just looking at these three colors。

 you probably wouldn't guess that they combine to make like green。



![](img/3a60ce59028e9e948454330d69eed989_7.png)

Different colors are produced by changing the intensities of the three color components， red。

 green and blue。Moving a color component closer to its maximum value increases the contribution from that color。

There are alternative color spaces to RGB that you can use。

This is similar to the way points in the Cartesian coordinate system。

Can be described with other coordinate systems。Like spherical coordinates。Most importantly。

 complex relationships between points in one coordinate system can be much simpler to describe in another。

For example， changing just the theta value of this point P。

Is equivalent to changing all three values in the Cartesian coordinate system。

A commonly used color space is Hue saturation value， or HSV。Like the RGB color space。

 the HSV color space uses three components to build color。

A hue corresponding to the angle on a color wheel。A saturation determining the color intensity。

And a value determining how bright or dark the color is。



![](img/3a60ce59028e9e948454330d69eed989_9.png)

Returning to the blueberry's image。You can isolate the blue by limiting only the hue value in the HSV color space。



![](img/3a60ce59028e9e948454330d69eed989_11.png)

![](img/3a60ce59028e9e948454330d69eed989_12.png)

This is much more difficult in RGB， because all three components change in that space。



![](img/3a60ce59028e9e948454330d69eed989_14.png)

In MatTLb， you convert an image from the RGB。To the HSV color space with the RGB to HSV function。

Notice how the RGB values are integers， while the HSV values are decimals between 0 and1。



![](img/3a60ce59028e9e948454330d69eed989_16.png)

Convert back to the RGB color space using the HSV to RGB function。

The resulting RGB image is still of type double。There are other alternatives as well。

 like the Y CBCR color space， commonly used in video equipment and the LAB color space often used for photo editing。



![](img/3a60ce59028e9e948454330d69eed989_18.png)

MatLB also has functions to convert between these color spaces。

Because it's challenging to know which color space is best suited to your application。

 you'll need to experiment and try different color spaces。



![](img/3a60ce59028e9e948454330d69eed989_20.png)

In the next video， you'll be introduced to a color thresholdholding app that helps you segment images in different color spaces。



![](img/3a60ce59028e9e948454330d69eed989_22.png)

![](img/3a60ce59028e9e948454330d69eed989_23.png)

Yeah。