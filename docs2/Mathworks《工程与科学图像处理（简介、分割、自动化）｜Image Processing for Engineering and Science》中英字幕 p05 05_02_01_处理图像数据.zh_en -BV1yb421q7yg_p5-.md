# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p05 05_02_01_处理图像数据.zh_en -BV1yb421q7yg_p5-

🎼，Images are stored as a rays of numbers。This means you work with image data。

 much like you do other matrices and arrays。For example。

 cropping a gray scale image is the same as accessing a subset of a matrix。However。

 remember that most images are data type U8。Which uses less memory。

 but can lead to some pretty interesting errors if you're not careful。In this video。

 you'll perform arithmetic operations on image data。Convert images to different data types。

Convert color images to grayscale。Transform images by resizing and rotating them。

And save your results for use outside of Matlab。A common image processing task is to average multiple images together。

This often improves the signal to noise ratio。Let's practice working with image data by averaging these images of the Orion nebula。



![](img/58010d1f4a1aa92203ec59ce015ade4b_1.png)

To create an average image， just add the images together。Then divide by the total number of images。



![](img/58010d1f4a1aa92203ec59ce015ade4b_3.png)

Whoa， this does not look correct。

![](img/58010d1f4a1aa92203ec59ce015ade4b_5.png)

The image seems uniform in the center and dim overall， compared to a single image。



![](img/58010d1f4a1aa92203ec59ce015ade4b_7.png)

So what's going on here？

![](img/58010d1f4a1aa92203ec59ce015ade4b_9.png)

Notice the data type of the images is U8。Recall that U intake can only have integer values between 0 and 255。

This saves memory， but has limitations。For example， let's add 200 plus 200 in the UN date data type。

The result is 2，55， not 400。By doing this operation。

 we've saturated the data type to the maximum value of 255。



![](img/58010d1f4a1aa92203ec59ce015ade4b_11.png)

This explains why the average image looks uniform in the center。Yet， dim， at the same time。



![](img/58010d1f4a1aa92203ec59ce015ade4b_13.png)

When doing the addition。Many pixels became saturated to the maximum value of 255。

Then dividing those pixels by 5 resulted in a value of 51。Therefore。

 before doing arithmetic with images， use the IM to double function to convert them to data type double。

This function also rescales the values to be between 0 and 1。

 which is standard for many image processing algorithms。

The averaged image after converting to double， gives the expected result。



![](img/58010d1f4a1aa92203ec59ce015ade4b_15.png)

Let's compare the average to one of the individual images using the montage function。



![](img/58010d1f4a1aa92203ec59ce015ade4b_17.png)

![](img/58010d1f4a1aa92203ec59ce015ade4b_18.png)

To use this function。Provide a list of images inside curly brackets。And separated by commas。



![](img/58010d1f4a1aa92203ec59ce015ade4b_20.png)

The differences are hard to see here， but zooming in。



![](img/58010d1f4a1aa92203ec59ce015ade4b_22.png)

You see that there is less noise in the nebula of the average image。

Recall that the data type double requires significantly more memory than the UNT data type。

Use the IM to UN8 function to convert back to UNate。



![](img/58010d1f4a1aa92203ec59ce015ade4b_24.png)

Some calculations， like averaging， will require you to explicitly convert between data types。However。

 most image processing functions in Matlab will do this for you。 For example。

 converting the image to gray scale。All necessary data type conversions are done inside the function。

Grayscale images require less memory。Are faster to operate on。

And can be used in a wider range of image processing tasks。



![](img/58010d1f4a1aa92203ec59ce015ade4b_26.png)

You might be wondering， aren't you throwing away information by converted to Gscale。Yes。

 but often colour is not needed。Suppose you were counting stars in this image。

All you need is the brightness， which is captured by the gray scale intensity values。



![](img/58010d1f4a1aa92203ec59ce015ade4b_28.png)

Let's compare the size of the gray scale versus color images。All these variables are quite large。

 with the color images requiring three times more memory。

Reducing the image resolution will reduce the required memory。

Use the IM resize function to adjust the image dimensions。There are two ways to use this function。

The first is to provide a scale factor。Here， the image is reduced to 75% of its original resolution。

The second approach is to specify the number of rows and columns in the output image。



![](img/58010d1f4a1aa92203ec59ce015ade4b_30.png)

Use this second approach if your application requires the image to be a specific size。



![](img/58010d1f4a1aa92203ec59ce015ade4b_32.png)

Keep in mind that the resized image will be distorted if the scaling factor in the x and Y directions is different。



![](img/58010d1f4a1aa92203ec59ce015ade4b_34.png)

![](img/58010d1f4a1aa92203ec59ce015ade4b_35.png)

Rotating images is also common to ensure the same alignment for multiple images or across different setups。

Rotate an image using the I am rotate function， entering the angle in degrees。



![](img/58010d1f4a1aa92203ec59ce015ade4b_37.png)

The negative value indicates a clockwise rotation。

![](img/58010d1f4a1aa92203ec59ce015ade4b_39.png)

Notice that the size of the rotated image is larger after the rotation。

Additional rows and columns are needed to make room for the rotated image。



![](img/58010d1f4a1aa92203ec59ce015ade4b_41.png)

If the output image should be the same size as the original， use the crop option。



![](img/58010d1f4a1aa92203ec59ce015ade4b_43.png)

To save your processed images， use the I am right function。

The first input is the variable name of the image to save。The second input is the file name to use。

The file format specified in the file name extension is used when writing the file。



![](img/58010d1f4a1aa92203ec59ce015ade4b_45.png)

So this creates a PNG file。Recall that P And G files use lossless compression。

 but have larger file size than lossy compression formats like JpeEg。



![](img/58010d1f4a1aa92203ec59ce015ade4b_47.png)

This is one reason why Jpeg compression is commonly used。



![](img/58010d1f4a1aa92203ec59ce015ade4b_49.png)

When saving a Jpeg， specify the image quality from 1 to 100。Higher numbers more accurately。

 reproduce the image。Keep in mind that even a quality factor of 100 still uses lossy compression。



![](img/58010d1f4a1aa92203ec59ce015ade4b_51.png)

Notice the significant difference in file size of these three images。



![](img/58010d1f4a1aa92203ec59ce015ade4b_53.png)

Try repeating the analysis done in this video。And open the images to see if there is a noticeable difference in image quality。



![](img/58010d1f4a1aa92203ec59ce015ade4b_55.png)

🎼。