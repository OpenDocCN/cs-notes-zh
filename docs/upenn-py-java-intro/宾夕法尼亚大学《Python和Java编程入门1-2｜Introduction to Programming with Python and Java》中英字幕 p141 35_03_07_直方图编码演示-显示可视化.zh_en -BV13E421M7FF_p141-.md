# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p141 35_03_07_直方图编码演示-显示可视化.zh_en -BV13E421M7FF_p141-

![](img/2ae307c2302d8b8fa585d373012b32af_0.png)

Now， we're going to have two histograms inside of our plot to show the plot。

 We're going to use the show method。 So PLT dot show。 We'll call that。

 Here's our simple visualization。 We see the yellow bars represents the data for Pittsburgh and the red overlaid here。

 It's orange represents the data for Vegas。

![](img/2ae307c2302d8b8fa585d373012b32af_2.png)

![](img/2ae307c2302d8b8fa585d373012b32af_3.png)

So let's add some additional features to the plot when to update my code here。



![](img/2ae307c2302d8b8fa585d373012b32af_5.png)

We can add labels for our x and Y axes， so PLT X label will be set to rating。

And then PLT dot Y label will be set to。Number of rating scores。Let's add a legend。

 PLT do legend in the best location。We'll let pie plot figure that out。And then let's add a title。

 PLT dot title。Review。😔，Distribution。😔，Of Pittsburgh。And。😔，Las Vegas。Once everything is set。

 let's go ahead and rerun our code to display our work。



![](img/2ae307c2302d8b8fa585d373012b32af_7.png)

Here we see our updated visualization。

![](img/2ae307c2302d8b8fa585d373012b32af_9.png)

This is the review distribution of Pittsburgh and Las Vegas。 The yellow bars represents Pittsburgh。

The red bars represents Las Vegas， and the orange portion represents the overlap between Pittsburgh and Las Vegas。



![](img/2ae307c2302d8b8fa585d373012b32af_11.png)

![](img/2ae307c2302d8b8fa585d373012b32af_12.png)

So you can always tweak the parameters to adjust the plot to your preference for us。

 having two plots overlap doesn't seem appealing。 Let's place the histogram bars side by side。



![](img/2ae307c2302d8b8fa585d373012b32af_14.png)

![](img/2ae307c2302d8b8fa585d373012b32af_15.png)

So this time we're going to have one histogram object with lists of values。



![](img/2ae307c2302d8b8fa585d373012b32af_17.png)

Using pie plot， let's call hist。

![](img/2ae307c2302d8b8fa585d373012b32af_19.png)

Here， we're going to provide a list of data frames to plot。 So I'm going to use pit stars and。

Vegs stars。

![](img/2ae307c2302d8b8fa585d373012b32af_21.png)

I'll set alpha to be 0。7。

![](img/2ae307c2302d8b8fa585d373012b32af_23.png)

The color will be a list of colors。 Let's use red。And blue。

 these will correspond with Pittsburgh and Vegas。And then label will be a list of labels， Pittsburgh。

And Las Vegas。

![](img/2ae307c2302d8b8fa585d373012b32af_25.png)

And the bins will be set to auto。

![](img/2ae307c2302d8b8fa585d373012b32af_27.png)

Other configurations。 Let's go ahead and set a label for the X axis。

 So rating and then PLT dot Y label will be set to。Number。Of rating scores。

Let's create a legend in the best possible location。And let's give it a title。Say， review。

Distribution of Pittsburgh。And Las Vegas。

![](img/2ae307c2302d8b8fa585d373012b32af_29.png)

And to show our visualization， we're going to call show。Let's run that to see our visualization。



![](img/2ae307c2302d8b8fa585d373012b32af_31.png)

This is the review distribution of Pittsburgh in Las Vegas。 Red represents Pittsburgh。

 Blue represents Las Vegas。 The X axis is the average rating score。

 and the Y axis is the count of each of those scores。



![](img/2ae307c2302d8b8fa585d373012b32af_33.png)

![](img/2ae307c2302d8b8fa585d373012b32af_34.png)