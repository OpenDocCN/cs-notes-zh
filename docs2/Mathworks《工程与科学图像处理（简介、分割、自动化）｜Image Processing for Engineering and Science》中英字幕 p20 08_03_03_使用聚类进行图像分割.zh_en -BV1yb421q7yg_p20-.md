# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p20 08_03_03_使用聚类进行图像分割.zh_en -BV1yb421q7yg_p20-

🎼，Segmentation is not always binary。 Some applications require labeling multiple objects in the same image。

 For example， in this image， what if you wanted to segment each chip color separately。



![](img/f87a20428373ba2335fbe358c4def066_1.png)

![](img/f87a20428373ba2335fbe358c4def066_2.png)

One possibility would be to create a binary mask for each color using the color Thr app。

Then combine them into a multi label mask。

![](img/f87a20428373ba2335fbe358c4def066_4.png)

However， this could be a bit tedious。

![](img/f87a20428373ba2335fbe358c4def066_6.png)

A method that will directly result in a multi label mask is clustering the image into regions with similar properties。

 In this case， color coordinates。Clustering is a mathematical technique for grouping data such that the elements of each cluster have more similarity with each other than elements of other clusters。

You can see how the distinct colors in this image form clusters in different color spaces using the color Thr app。

Like with color thresholding。It's often advantageous to use an alternative color space。

 when clustering。In this case， the HSV space appears to have the best separation of the chip color coordinates。

To convert your image into this color space， use the RGB to HSV function。Next。

 the clustering algorithm will need to know how many color clusters to label in the image。

There are five colors of chips， one black pen， and one wood colored table。

So let's start with 7 labels。The I M Seg K means function will perform K means clustering on the image。

Note that it requires the input image to be of data type single。

The output is a matrix of pixel labels。Each element in the matrix is a number。Specifying the cluster。

 the corresponding pixel was assigned to。To compare the label matrix to the original image。

 use the label 2 RGB function。Viewing the label matrix shows that the table pixels fell into three clusters。

And not every color of chip got a unique label。K means clustering divides the color coordinate data into K clusters。

 using the distance between points as a measure of similarity。In this case。

 you can see many pixels for the table spread over a range of brightness。😊。

This volume is being broken up into multiple clusters。However。

 notice that the pixels belonging to the pen and table are all lower saturation than those belonging to the colored chips。

So let's use this to segment the table and pen out of the image and then try clustering the colored chips on a black background。



![](img/f87a20428373ba2335fbe358c4def066_8.png)

It looks like a saturation threshold of about 0。75 works well to separate the table and pen from the colored chips。



![](img/f87a20428373ba2335fbe358c4def066_10.png)

So let's add that to our script。The saturation values are in the second coordinate plane of the HSV image。

So let's assign a binary mask true where these values are greater than 0。75。Next。

 create a copy of the image。And then apply the mask to zero out the table and pen。

Remember that you need to apply the mask to all three color coordinate planes with the rep mat function for color images。

Finally， to visually check the results， I am show needs the RGB version of the new image。😊。



![](img/f87a20428373ba2335fbe358c4def066_12.png)

Looks like it worked correctly。

![](img/f87a20428373ba2335fbe358c4def066_14.png)

Now， let's copy the clustering code from before。

![](img/f87a20428373ba2335fbe358c4def066_16.png)

Update it to use the image we just created。And change the number of labels to 6 to capture the five chip colors and black background。



![](img/f87a20428373ba2335fbe358c4def066_18.png)

It looks like each chip color now has a unique label。



![](img/f87a20428373ba2335fbe358c4def066_20.png)

In general， clustering can be an efficient way to segment an image into several distinct color regions。

You may find that using a particular color space will help the clustering algorithm。

 and as in this example， you may need to combine clustering with other segmentation approaches。



![](img/f87a20428373ba2335fbe358c4def066_22.png)

。