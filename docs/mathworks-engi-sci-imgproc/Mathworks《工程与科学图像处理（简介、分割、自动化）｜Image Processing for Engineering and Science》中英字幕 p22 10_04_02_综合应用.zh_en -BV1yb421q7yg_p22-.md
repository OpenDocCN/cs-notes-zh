# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p22 10_04_02_综合应用.zh_en -BV1yb421q7yg_p22-

。

![](img/a0e6b11f402eafb88a2db4351ce693fc_1.png)

You've now used quite a few techniques as part of image segmentation workflows。In this video。

 we'll summarize the techniques you've learned and discuss when each is most appropriate。



![](img/a0e6b11f402eafb88a2db4351ce693fc_3.png)

You've created masks using methods such as global and adaptive thresholdholding on gray scale images。



![](img/a0e6b11f402eafb88a2db4351ce693fc_5.png)

Color， thresholdholding and clustering on color images。As well as edge and shape detection。



![](img/a0e6b11f402eafb88a2db4351ce693fc_7.png)

To improve the results from these methods。You learned how to use pre processingcess steps like spatial filtering and image averaging to reduce noise before mass creation。



![](img/a0e6b11f402eafb88a2db4351ce693fc_9.png)

To address imperfections that remained？You refined masks using morphological operations。

As well as filtering using region properties。And when one mask wasn't enough。

 you combined multiple masks using logical operations。



![](img/a0e6b11f402eafb88a2db4351ce693fc_11.png)

With so many tools and techniques at your disposal。

 you might wonder which to use with your own image data。You'll often need to try several approaches。



![](img/a0e6b11f402eafb88a2db4351ce693fc_13.png)

But determining the properties that most clearly differentiate your foreground from background is often a good start。

If your image has noticeable intensity contrast between foreground and background。

Then a gray scale thresholding approach is likely to work well。



![](img/a0e6b11f402eafb88a2db4351ce693fc_15.png)

If there is also non uniform illumination。Aaptive thresholdholding can adjust for local variations。

Differences between the color of your foreground and background。

Make approaches such as color thresholdholding。Or clustering good options。

It is often helpful to use the color threshold app to evaluate the various color spaces and find the best coordinates to segment your image。



![](img/a0e6b11f402eafb88a2db4351ce693fc_17.png)

Other times， one or more of your foreground objects can be defined by circularity。Remember。

 when using edge based algorithms like find circles。

You'll often need to first apply some pre processingcess like spatial filtering。



![](img/a0e6b11f402eafb88a2db4351ce693fc_19.png)

Regardless of which approach seems most promising。If you know。

 your image data has a significant amount of noise。It may be a good idea to reduce it up front。

This can improve the initial mass results。And reduce the need for further refinement。

You'll need to experiment with your filter size， though。

A filter that is too strong can eliminate less pronounced foreground areas from the resulting mask。



![](img/a0e6b11f402eafb88a2db4351ce693fc_21.png)

Image processing often involves trial and error。So don't spend all of your effort on noise reduction。

You can always return to this step and adjust if you run into issues later in your workflow。



![](img/a0e6b11f402eafb88a2db4351ce693fc_23.png)

Whichever approach you take， the initial mask you end up with may need some further refinement。

In these situations， you've used morphology to close holes in your foreground。



![](img/a0e6b11f402eafb88a2db4351ce693fc_25.png)

And remove small artifacts。

![](img/a0e6b11f402eafb88a2db4351ce693fc_27.png)

This technique is very flexible because you can change both the size and shape of the structuring element。



![](img/a0e6b11f402eafb88a2db4351ce693fc_29.png)

![](img/a0e6b11f402eafb88a2db4351ce693fc_30.png)

As with all the techniques you've learned， if you are working with multiple images。

 make sure to apply your steps to several of them to see if your steps generalize。Finally。😊。



![](img/a0e6b11f402eafb88a2db4351ce693fc_32.png)

If your mask foreground has distinct properties such as size or shape。

Filtering by region properties is an additional tool for massque refinement。



![](img/a0e6b11f402eafb88a2db4351ce693fc_34.png)

In the end， you may find you need to use more than one approach and combine masks。



![](img/a0e6b11f402eafb88a2db4351ce693fc_36.png)

Or return to an earlier step in your workflow and make adjustments。



![](img/a0e6b11f402eafb88a2db4351ce693fc_38.png)

Remember。

![](img/a0e6b11f402eafb88a2db4351ce693fc_40.png)

Image segmentation is often an iterative process。Experiment with multiple approaches and stay focused on your final goal。

As you gain more experience， you'll learn which techniques are most appropriate for your image data。



![](img/a0e6b11f402eafb88a2db4351ce693fc_42.png)

Yeah。