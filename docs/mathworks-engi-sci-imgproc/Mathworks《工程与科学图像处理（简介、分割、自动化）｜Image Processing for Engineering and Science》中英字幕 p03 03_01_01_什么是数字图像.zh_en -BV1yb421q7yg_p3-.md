# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p03 03_01_01_什么是数字图像.zh_en -BV1yb421q7yg_p3-

🎼，Image processing is used to solve challenging problems in many science and engineering applications。

But before you can process an image in MatTlab。It must be captured and stored in a digital format。

In this video， you'll learn more about the different image types you are likely to encounter and the most common file formats。

Digital cameras use electronic light receptors。These receptors use photo sensitiveitive materials to convert incoming light waves into electrical signals and record them as numeric intensity values。

Humans perceive intensity as brightness， which is determined by the amplitude of the light。

Moonicchrome sensors record only intensity values that are used to capture grayscale images。

But to create color images， multiple sensors are used to record the intensity of incoming light at three different wavelengths。

 which humans perceive as red， green and blue。These color components are called channels。

 and they can be recombined according to their intensities to form the original color。

Photoreceptors are typically organized in a rectangular grid。

The intensity captured by an individual receptor on the grid is referred to as a pixel where a pixel is the smallest component of a digital image。

The number of pixels used to form the image is referred to as the image resolution。

Resolution is commonly expressed as either the total number of pixels or the total number of pixels in the vertical and horizontal directions。

In general， higher resolution images allow for more visual information to be captured。

 resulting in better quality。Other factors that affect image quality include sensor efficiency。

 focus and exposure， which is the amount of light allowed to reach the sensors。

Scientific images are also captured using wavelengths， which are invisible to the human eye。

 but detectable by photoreceptors， including ultraviolet and infrared。

But this intensity information can still be transformed into wavelengths that humans can see。

In addition to cameras， image data can be generated from other types of instruments。

 which represent non visual information using images。For example。

 weather maps are generated using radar signals。

![](img/da26aba646a89ef174553b983fb01d5d_1.png)

Here， the amount of reflected signal detected depends on a number of factors。

 including how much precipitation is falling。And medical professionals visualize the composition of the human body by taking X ray images or using magnetic resonance imaging。

In these professions， it's common to work with 3D images when measurements are taken over a volume。



![](img/da26aba646a89ef174553b983fb01d5d_3.png)

As with photographic images， the 3D pixels referred to as voxels are located on a rectangular grid。



![](img/da26aba646a89ef174553b983fb01d5d_5.png)

Viewing all the information in a three dimensional image is challenging。

 So it's common to select slices of the higher dimensional data。

 which correspond to the measurements taken on a particular plane or surface。



![](img/da26aba646a89ef174553b983fb01d5d_7.png)

![](img/da26aba646a89ef174553b983fb01d5d_8.png)

A different type of three dimensional image you are likely familiar with is video。

 as the two dimensional image frames can be stacked sequentially along an additional dimension representing time。

With so many types of digital image data。It's no surprise that there are many different ways to store them。

Some of these file formats may already be familiar。

 while others are likely unfamiliar unless you work in the fields in which they are used。

But why so many。One reason is due to the different possible dimensionalities of image data and whether they represent single images or a sequence of frames。



![](img/da26aba646a89ef174553b983fb01d5d_10.png)

Another reason is that different compression techniques are used with each format。



![](img/da26aba646a89ef174553b983fb01d5d_12.png)

Compression is used in most file formats to reduce the amount of memory needed to store images。

That's because the information recorded by the sensors referred to as the raw image requires a large amount of data to store。

 even for low resolutions。And image data sets often consist of thousands or millions of images。

 or video frames。The goal of compression is to try to store the most amount of visual information using the least amount of memory。



![](img/da26aba646a89ef174553b983fb01d5d_14.png)

Compression algorithms can be divided into two main types。

Losless compression allows the raw image to be reproduced exactly。

 but the reduction in file size is typically low。While lossy compression results in more significant memory savings。

 but visual information is lost during compression。 So the compressed image is close。

 but not exactly the same as the raw image。

![](img/da26aba646a89ef174553b983fb01d5d_16.png)

One other difference between image file types is additional data that may be included in the file。

For example， it's common for video data to be coupled with audio data as a multimedia file。Image。

 video， and multimedia files also contain additional text information called metadata。

Metaadata can include the image capture date and location， the device used。

 a description of the image， the video frame rate and other information。

 depending on the type of image and the file standards。



![](img/da26aba646a89ef174553b983fb01d5d_18.png)

With all these formats， you may be wondering which format should I use。

 Important considerations include the trade off between compression and quality。

 The number of images you are working with。 if you have two or three dimensions。

And the image processing tasks you intend to perform。Hardware limitations。

 such as your available memory or processing power。

 must also be considered when working with large numbers of images or performing computer vision and deep learning tasks。

Note， however， that this choice is often made for you unless you plan to capture your own images or you are willing to convert between formats。

As you'll see in the next lesson， most image data is represented in a similar manner once it is imported into Matlap。

 regardless of the original format。

![](img/da26aba646a89ef174553b983fb01d5d_20.png)

。