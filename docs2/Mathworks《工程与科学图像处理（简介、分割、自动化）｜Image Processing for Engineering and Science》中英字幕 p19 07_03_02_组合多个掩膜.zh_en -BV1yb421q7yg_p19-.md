# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p19 07_03_02_组合多个掩膜.zh_en -BV1yb421q7yg_p19-

🎼。

![](img/668197527a29e0ce81365028085972fa_1.png)

Sometimes you may not have a single mask that produces the segmentation you want。For example。

 segmenting all the colored chips from this image。

![](img/668197527a29e0ce81365028085972fa_3.png)

However， a combination of the masks will produce the desired segmentation。In this video。

 you'll learn to handle situations like this by combining masks using and or as well as not logical operators。



![](img/668197527a29e0ce81365028085972fa_5.png)

![](img/668197527a29e0ce81365028085972fa_6.png)

To start， let's take a look at how we got to the situation in the example you just saw。

Since the chips are circles， a good first approach to segmenting them is to open the image segmenter app。



![](img/668197527a29e0ce81365028085972fa_8.png)

And use find circles。Adjusting the size and sensitivity segments all the yellow chips。

 but not the other colors。This is due to the foreground polarity being set to bright。

Changing the foreground polarity to dark segments all of the remaining colored chips。So。

Generate a segmentation function for each polarity setting to create the masks in a script。

Then open a script and load the image。Next， use the functions generated from the app to create the binary mask for both foreground polarities。



![](img/668197527a29e0ce81365028085972fa_10.png)

Remember to combine binary masks， use and or， and not logical operators。In this case。

 we need the orar operator to get the portions of the image where either mask is true。



![](img/668197527a29e0ce81365028085972fa_12.png)

Now， let's check the result。

![](img/668197527a29e0ce81365028085972fa_14.png)

This looks like it should segment all the chips。

![](img/668197527a29e0ce81365028085972fa_16.png)

Let's take a look at the result of applying the mask to the image。



![](img/668197527a29e0ce81365028085972fa_18.png)

First， create a copy of the image。Then， apply the mask。

Use the Re mat function to duplicate the binary mask into all three color planes。



![](img/668197527a29e0ce81365028085972fa_20.png)

Looks good。Every chip has been segmented by this mask。



![](img/668197527a29e0ce81365028085972fa_22.png)

In your applications， you may need to combine more than two masks with more complex relationships。

But you can always break the combinations down into single operator pairs。



![](img/668197527a29e0ce81365028085972fa_24.png)

。