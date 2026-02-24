# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p32 08_03_01_实用图像处理.zh_en -BV1yb421q7yg_p32-

🎼。

![](img/96b363c85db9572cc9070246df4e3c1c_1.png)

You now have a toolbox of various image processing techniques。But when you start a project。

 it can be difficult to know which ones to use。

![](img/96b363c85db9572cc9070246df4e3c1c_3.png)

For instance， when we experimented with the concrete images。

 we developed and compared dozens of segmentation algorithms。



![](img/96b363c85db9572cc9070246df4e3c1c_5.png)

We tried thresholding， using both gray scale and color。Bluurrrring， using a Gaussian filter。

And various morphological operations with structuring elements of different shapes and sizes。



![](img/96b363c85db9572cc9070246df4e3c1c_7.png)

In most situations， you won't find an approach that works perfectly for every image。



![](img/96b363c85db9572cc9070246df4e3c1c_9.png)

Therefore， it's important that you establish your goals up front。That way。

 you know which errors you can tolerate。And when your results are accurate enough to move on。



![](img/96b363c85db9572cc9070246df4e3c1c_11.png)

For example， consider if an algorithm for detecting cracks and concrete will be used to estimate the amount of material needed to repair a sidewalk。



![](img/96b363c85db9572cc9070246df4e3c1c_13.png)

In this case， the goal would be to accurately measure a crack's area。



![](img/96b363c85db9572cc9070246df4e3c1c_15.png)

Therefore， you'll want a mask that will accurately capture the edges of a crack。

And exclude any debris inside sight of them。

![](img/96b363c85db9572cc9070246df4e3c1c_17.png)

Alternatively， if the algorithm will be used to assess the condition of a dam。

 the goal would be to identify severe cracks that need repair。Therefore。

 you might consider blurring the original image to smooth over any rough texture in the concrete before you perform the segmentation。



![](img/96b363c85db9572cc9070246df4e3c1c_19.png)

This blurring step might cause the segmentation to ignore narrow cracks。

 but that's okay because the goal wasn't to create an accurate mask。

 but rather to identify severe cracks。It's difficult to know in advance which approach is best。

Stay focused on your end goal as you try different approaches。

 So you know which errors are acceptable。Be sure to use the image batch processor to see how an algorithm generalizes to all your images。

You can also perform data analysis in MATLAB to help you identify outliers for further investigation。

Your image processing approach depends on your images。

 but you can't turn poor data into good results。

![](img/96b363c85db9572cc9070246df4e3c1c_21.png)

If you are able， it may be worth improving your experimental setup and recapturing all of the images。



![](img/96b363c85db9572cc9070246df4e3c1c_23.png)

However， this isn't always possible， such as with autonomous vehicles。

 which must operate safely in real time， regardless of the lighting or weather conditions they encounter。

In these cases， a common solution is to combine video with data from other types of sensors like radar or Lidar。

This is an example of real time image capture when you need your algorithms to process quickly。



![](img/96b363c85db9572cc9070246df4e3c1c_25.png)

Alternatively， in fields such as medical imaging， it may be worth waiting for an extensive processing algorithm to get the most accurate results。



![](img/96b363c85db9572cc9070246df4e3c1c_27.png)

In practice， perfection is rarely possible in image processing。

 So always be sure to define your goals up front and use them to determine how best to approach your project。



![](img/96b363c85db9572cc9070246df4e3c1c_29.png)

。

![](img/96b363c85db9572cc9070246df4e3c1c_31.png)