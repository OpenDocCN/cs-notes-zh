# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p23 11_04_01_分析三维图像.zh_en -BV1yb421q7yg_p23-

🎼，Three dimensional imaging is an important part of many fields， including medicine， geology。

 and microbiology to name just a few。In this video。

 you'll apply many of the concepts you've learned with 2D images to a 3D image。

You'll segment a volume。Refine a mask with morphology。Combine multiple masks。

And perform region analysis。

![](img/36a7174ceda8f521327c76d26e24e3d9_1.png)

Like with 2D images， you often need to examine your 3D image data before performing analysis。



![](img/36a7174ceda8f521327c76d26e24e3d9_3.png)

Use the Volume viewer app。To view your three dimensional data from any perspective。



![](img/36a7174ceda8f521327c76d26e24e3d9_5.png)

As well as get a better understanding of the voxel intensities throughout the volume。



![](img/36a7174ceda8f521327c76d26e24e3d9_7.png)

And as with 2D images， there is an app to help you segment 3D images。



![](img/36a7174ceda8f521327c76d26e24e3d9_9.png)

The Volum segmenter app enables you to quickly try different segmentation algorithms。

Import your own custom algorithms。

![](img/36a7174ceda8f521327c76d26e24e3d9_11.png)

And visualize the results。In this video， you'll use the volume segmenter app to first separate the brain tissue from the skull and scalp in this MRI scan。



![](img/36a7174ceda8f521327c76d26e24e3d9_13.png)

And then isolate the white matter within the brain tissue。



![](img/36a7174ceda8f521327c76d26e24e3d9_15.png)

Let's begin by importing the three dimensional image into the app。



![](img/36a7174ceda8f521327c76d26e24e3d9_17.png)

The app includes options to segment 3D images， using either volume。Or slice based algorithms。

We'll use slice based segmentation here。

![](img/36a7174ceda8f521327c76d26e24e3d9_19.png)

To segment regions of interest in all slices。You need to give the algorithm a starting point。

You can load in an existing mask if you have one。However。

 because the brain is easy to tell apart here， a hand drawn region is a good way to start。

Don't worry if your region isn't perfect。 You only need to roughly isolate the brain。Now。

 since the brain， skull and scalp have distinct， smooth outlines。

 use the active contours algorithm to refine this mask。



![](img/36a7174ceda8f521327c76d26e24e3d9_21.png)

This looks good。 Let's supply this to the rest of the slices with brain tissue。

It looks like the first slice containing brain tissue is slice 26。



![](img/36a7174ceda8f521327c76d26e24e3d9_23.png)

So we'll apply our algorithm from the starting slice 78。To slice 26。



![](img/36a7174ceda8f521327c76d26e24e3d9_25.png)

It looks like our algorithm did a good job of segmenting the brain in these slices。

In the other direction， it looks like the last slice with brain tissue is 155。



![](img/36a7174ceda8f521327c76d26e24e3d9_27.png)

So let's also apply our algorithm from slice 78。To 1，55。Well。

 it looks like it didn't work quite as well here。You can see we're getting quite a few artifacts in this range。

Looking at both the individual slices。And the 3D display。

You could try to develop a different algorithm for this range。

 but you can also use morphology with 3D images to refine masks。



![](img/36a7174ceda8f521327c76d26e24e3d9_29.png)

![](img/36a7174ceda8f521327c76d26e24e3d9_30.png)

So， let's try that。Using erosion， followed by dilation。With the right size structuring element。

Will eliminate the artifacts， but not the brain。Use the algorithm parameterss button。



![](img/36a7174ceda8f521327c76d26e24e3d9_32.png)

To adjust the size of a disk shaped structuring element。Let's try a radius of 10。

 and like in the 2 D case， set the approximations to 0。Since you don't yet know if this will work。

Test the operation on the current slice， to see the result。



![](img/36a7174ceda8f521327c76d26e24e3d9_34.png)

It looks like the structuring element needs to be a bit larger to eliminate all the artifacts。



![](img/36a7174ceda8f521327c76d26e24e3d9_36.png)

You can undo the previous erosion using the control plus C key combination。



![](img/36a7174ceda8f521327c76d26e24e3d9_38.png)

Now。Let's try a radius of 13。

![](img/36a7174ceda8f521327c76d26e24e3d9_40.png)

This worked。Now， let's check that it does the same for the rest of the slices with artifacts。



![](img/36a7174ceda8f521327c76d26e24e3d9_42.png)

First。

![](img/36a7174ceda8f521327c76d26e24e3d9_44.png)

Slicees 1，16。To 155。

![](img/36a7174ceda8f521327c76d26e24e3d9_46.png)

Not bad。Okay， now in the other direction， it looks like we'll need to erode artifacts in slices from 1。

14 back to。Slice 96。When performing slice based morphology。

 be careful not to repeat the operation on the same slice。



![](img/36a7174ceda8f521327c76d26e24e3d9_48.png)

![](img/36a7174ceda8f521327c76d26e24e3d9_49.png)

Good。😊，Now， you need to dilate the mask to bring back regions of brain tissue that were removed by erosion。



![](img/36a7174ceda8f521327c76d26e24e3d9_51.png)

Use the same structuring element settings。And set the slice range to go from 96。



![](img/36a7174ceda8f521327c76d26e24e3d9_53.png)

To 1，55。This looks very good。The artifacts are gone。

 and the mask looks like it is capturing essentially all of the brain tissue。



![](img/36a7174ceda8f521327c76d26e24e3d9_55.png)

The 3D display confirms we managed to segment the brain quite well。



![](img/36a7174ceda8f521327c76d26e24e3d9_57.png)

![](img/36a7174ceda8f521327c76d26e24e3d9_58.png)

Let's export this mask to the workspace， using data type logical。

So you can combine it with the next mask to isolate white matter。



![](img/36a7174ceda8f521327c76d26e24e3d9_60.png)

Notice the voxel intensity varies locally from white matter。To gray matter and cerebro spinal fluid。



![](img/36a7174ceda8f521327c76d26e24e3d9_62.png)

This means adaptive thresholdholding is a promising option to segment the white matter from the rest of the brain。

Let's give it a try。

![](img/36a7174ceda8f521327c76d26e24e3d9_64.png)

![](img/36a7174ceda8f521327c76d26e24e3d9_65.png)

This looks pretty good。The mask is capturing both the gray matter and cerebbropinal fluid。

It is also capturing the scalp and other artifacts。

But these will be eliminated when we logically combine it with the brain mask。



![](img/36a7174ceda8f521327c76d26e24e3d9_67.png)

To do this。Let's export this mask to the workspace， as well。



![](img/36a7174ceda8f521327c76d26e24e3d9_69.png)

To isolate the white matter， combine the whole brain and adaptive threshold masks using the and logical operator。

Because the adaptive threshold mass captured tissue other than white matter。

Use a not logical operator to invert it。

![](img/36a7174ceda8f521327c76d26e24e3d9_71.png)

Opening the resulting mask in the app。

![](img/36a7174ceda8f521327c76d26e24e3d9_73.png)

Confirms we have isolated only the white matter。

![](img/36a7174ceda8f521327c76d26e24e3d9_75.png)

Finally， like in the 2D case， you can calculate various mask region properties。For example。

 let's calculate the volume of white matter using the region Pros 3 function。

We need to sum the result， since there are multiple regions in the white matter M。Next。

 let's calculate the total brain volume in this scan。And， finally。

Let's find the ratio of white matter in the brain。Based on our segmentation。

 it looks like this brain is approximately 60% white matter。

There are many other functions for processing and analyzing volume data in MatLb。

Explore the documentation to find everything you can do with your three dimensional images。



![](img/36a7174ceda8f521327c76d26e24e3d9_77.png)

。