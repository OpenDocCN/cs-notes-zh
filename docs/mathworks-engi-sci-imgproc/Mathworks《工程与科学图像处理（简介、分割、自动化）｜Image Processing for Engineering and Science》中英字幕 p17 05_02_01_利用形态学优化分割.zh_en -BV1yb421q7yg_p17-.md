# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p17 05_02_01_利用形态学优化分割.zh_en -BV1yb421q7yg_p17-

🎼。

![](img/6e4526c852232eba7e03f56ecbdf1168_1.png)

When performing segmentation， for example， using gray scale thresholdholding on this puzzle piece image。

The initial mask may not always be perfect。There may be gaps or holes you don't want in the true pixels。



![](img/6e4526c852232eba7e03f56ecbdf1168_3.png)

Or true pixel artifacts where you want false pixels。



![](img/6e4526c852232eba7e03f56ecbdf1168_5.png)

A powerful tool to address these issues is called morphology。



![](img/6e4526c852232eba7e03f56ecbdf1168_7.png)

Morology is similar to spatial image filtering。It assigns new pixel values using a moving neighborhood of pixels in the original image。

There are two fundamental morphological operations。The first is dilation。

Which assigns the maximum value in the neighborhood to the new pixel。The second is erosion。

 which assigns the minimum value in the neighborhood to the new pixel。

Morology also emphasizes changing the size。And shape of the neighborhood。

Usually called a structuring element。This allows you to effect similar。

Or dissimilar objects in the image differently。

![](img/6e4526c852232eba7e03f56ecbdf1168_9.png)

Let's take a closer look at the puzzle piece mask。

![](img/6e4526c852232eba7e03f56ecbdf1168_11.png)

To see how these operations affect it。Using a simple three by three square structuring element。



![](img/6e4526c852232eba7e03f56ecbdf1168_13.png)

For a binary image。Dialation will assign the new pixel， as true。

Whenever any pixel of the structuring element is true。And falses。

Only when every pixel under it is false。Overall。Dillation expands existing true pixel areas。

The size and shape of the structuring element affect the results。Notice here how changing the size。

Or shape of the structuring element。Affects which areas of the image are affected。

As well as by how much。Erosion does the opposite。It will assign the new pixel is false whenever any pixel under the structuring element is false。

And true， only when every pixel under it is true。Overall， it reduces existing true pixel areas。



![](img/6e4526c852232eba7e03f56ecbdf1168_15.png)

Again， in proportion to the structuring element。

![](img/6e4526c852232eba7e03f56ecbdf1168_17.png)

Sometimes dilation or erosion is all you need to fix a ask。In this example， however。

 each of these operations applied individually helped some issues。While， at the same time。

 making others worse。Using these operations in sequence will often achieve better results。



![](img/6e4526c852232eba7e03f56ecbdf1168_19.png)

In this case， for example， a sequence involving both operations will specifically fill only the puzzle piece。



![](img/6e4526c852232eba7e03f56ecbdf1168_21.png)

Start by dilating the mask with a structuring element large enough to completely fill the gaps in the puzzle piece。

This filled the gaps。But it also added additional true pixels around the border。

And made unwanted true artifacts larger。To solve these problems。Iode the mask。

 using the same structuring element。Now， this looks quite a bit better。

The erosion operation removed the extra two pixels added around the border。

As well as the increases to true artifacts， all while keeping the holes in the puzzle piece filled。



![](img/6e4526c852232eba7e03f56ecbdf1168_23.png)

How is this possible。Well， remember， the dilation closed the gaps in the puzzle piece completely。

 creating an area of true pixels larger than the structuring element。However。

 the excess created at the edges of the puzzle piece and the increases in size to the smaller artifacts were all still adjacent to false pixels。

And within reach of the structuring element。Therefore。

 the subsequent erosion was able to invert these changes without affecting the closed gaps in the puzzle piece。

This sequence of dilation， followed by erosion with the same structuring element。

 is called morphological closing。The key is to remember that this operation closes gaps between true pixels that fit under the structuring element。



![](img/6e4526c852232eba7e03f56ecbdf1168_25.png)

Leaving the rest of the mask unchanged。Returning to the example。

 there are still unwanted Dr pixel artifacts。If you were thinking there is probably a dual method to eliminate these small clusters of true pixels while leaving the large puzzle piece essentially unchanged。

 you'd be right。

![](img/6e4526c852232eba7e03f56ecbdf1168_27.png)

Just reverse the steps。 And you have what is called morphological opening。



![](img/6e4526c852232eba7e03f56ecbdf1168_29.png)

Start by eroding the mask with the structuring element large enough to cover the artifacts。

Then to put the edge back on the puzzle piece。Diallate the result with the same structuring element。

This looks great。The opening sequence further opened up areas of false pixels by removing areas of true pixels small enough to fit under the structuring element。

The larger puzzle piece was essentially untouched。

![](img/6e4526c852232eba7e03f56ecbdf1168_31.png)

Compare the final mask after closing an opening to the initial mask。

You can see we managed to fill in the puzzle piece and eliminate the unwantedwonted true artifacts without modifying the outline of the puzzle piece itself。



![](img/6e4526c852232eba7e03f56ecbdf1168_33.png)

Overlaying this mask on the original image， you can see it provides a very accurate segmentation。



![](img/6e4526c852232eba7e03f56ecbdf1168_35.png)

You've now seen the concepts and techniques behind binary morphology and improving segmentation。



![](img/6e4526c852232eba7e03f56ecbdf1168_37.png)

Next， you'll learn how to use an app in MALb to easily try them out and visualize the results。



![](img/6e4526c852232eba7e03f56ecbdf1168_39.png)

。