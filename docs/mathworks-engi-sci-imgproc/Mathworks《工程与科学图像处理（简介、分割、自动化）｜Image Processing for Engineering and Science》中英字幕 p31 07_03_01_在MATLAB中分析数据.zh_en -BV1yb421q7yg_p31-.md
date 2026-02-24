# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p31 07_03_01_在MATLAB中分析数据.zh_en -BV1yb421q7yg_p31-

🎼。

![](img/d3f4afa371000ca6a8337479b9766698_1.png)

For complex problems， image processing is often followed by a fair amount of general data analysis。

For example， with the concrete images， you can identify the widest cracks in the data set by comparing their region properties。



![](img/d3f4afa371000ca6a8337479b9766698_3.png)

In this video， you should follow along as we use the live editor to categorize the crack images and investigate outliers。

Earlier， you used the crack segmentation and analysis function to generate a data table。

This variable is stored in a matte file， which is provided in the course files。



![](img/d3f4afa371000ca6a8337479b9766698_5.png)

Upon importing the table， notice that it has a row for each of the concrete crack images。

Along with three columns， representing the properties of each crack and a fourth column with a file name。



![](img/d3f4afa371000ca6a8337479b9766698_7.png)

To get started， use a histogram plot to look at the distribution of crack areas。Interestingly。

 there appears to be two distinct groups of cracks。

The histogram function allows for a second input to specify the number of bins。

 which you can use to help further differentiate the two groups。

The dividing line is a crack area of about 4000 pixels。



![](img/d3f4afa371000ca6a8337479b9766698_9.png)

Therefore， to label the images， we'll define a severe crack as one with a region above 4000 pixels using the discretized function。

This command takes the area of values， divides them into bins based on the provided cutoffs。

And labels them with categories。Here being mild and severe。Finally。

 save the output to a new table column called Ri。At this point。

 it's helpful to see your results using the function montage。

Let's select only the file names where the risk is severe。



![](img/d3f4afa371000ca6a8337479b9766698_11.png)

Using montage to merge many images into one figure is useful for a few images。

But this method may be awkward if you have thousands of images。

An alternative is to use the image browser app。Which can load a data store variable from the workspace。



![](img/d3f4afa371000ca6a8337479b9766698_13.png)

To create a data store of just the images with the severe cracks。

 use the image data store function and save the output as a new variable。



![](img/d3f4afa371000ca6a8337479b9766698_15.png)

Then load the data store variable in the image browser app。



![](img/d3f4afa371000ca6a8337479b9766698_17.png)

Now， let's look at the results。These severe cracks all appear to be properly classified。

Except for maybe the two cracks here， which looked like mild cracks that were incorrectly labeled as severe。

These kinds of errors are not unexpected when automating image processing and are likely the result of poor segmentation。

We found these cases by eye， but such a workflow would be time consuming if you had more than just a couple hundred images。

So how could you identify potential errors if you had thousands of images。Well。

 a common result of poor segmentation is to have an abnormal number of regions。



![](img/d3f4afa371000ca6a8337479b9766698_19.png)

Therefore， finding outliers in the numb regions variable should help us find misclassified images。



![](img/d3f4afa371000ca6a8337479b9766698_21.png)

Live tasks can be inserted into your script to help with common steps。

 like smoothing data or combining variables。

![](img/d3f4afa371000ca6a8337479b9766698_23.png)

It's worth taking the time to explore them。But for now， use the clean outlier data live task。First。

 select the data table as the input data。Then choose the specified variable to be number of regions。

And set the cleaning method to remove outliers。Many outlier detection algorithms are available。

 A good choice for this non normally distributed variable is the median method。



![](img/d3f4afa371000ca6a8337479b9766698_25.png)

The documentation is a good place to learn more about the different options available in this live task。



![](img/d3f4afa371000ca6a8337479b9766698_27.png)

Lastly， to better interpret the results， change the plot style to histogram。



![](img/d3f4afa371000ca6a8337479b9766698_29.png)

From the visualization， you can see that about half of the 200 images yield just one region in their final segmentation。

While the other half have more than one。A few images even have 10 or more regions， which。

 as we are about to see， is a fault of the segmentation process。



![](img/d3f4afa371000ca6a8337479b9766698_31.png)

The live task has also created the variable outlier indices， which stores the index of each outlier。



![](img/d3f4afa371000ca6a8337479b9766698_33.png)

Before we proceed， notice that the live tasks can be converted into regular Matlab code。

 just like with apps。

![](img/d3f4afa371000ca6a8337479b9766698_35.png)

Now， to view all of the outlier images together， first get the names of each outlier image using the outlier indices variable。

Then use this as the input to the montage function。



![](img/d3f4afa371000ca6a8337479b9766698_37.png)

Notice that the two images we previously said were mislabelled as severe have also been marked as outliers。



![](img/d3f4afa371000ca6a8337479b9766698_39.png)

But there are several others identified for further investigation。

To compare an image with its mask side by side， Use the following code that applies the segmentation function described earlier in the course。

The image name variable is where you select from the list of available outliers。



![](img/d3f4afa371000ca6a8337479b9766698_41.png)

![](img/d3f4afa371000ca6a8337479b9766698_42.png)

In this script， we've also converted this variable to a drop down menu control。

This functionality allows you to quickly switch between outlier images by hand。



![](img/d3f4afa371000ca6a8337479b9766698_44.png)

Notice how large numbers of regions are almost always the result of poor segmentation。



![](img/d3f4afa371000ca6a8337479b9766698_46.png)

But thankfully， instead of hunting for them by eye， we found them by detecting outliers。😊。



![](img/d3f4afa371000ca6a8337479b9766698_48.png)

The workflow in this script is just an example。Take this opportunity to practice data analysis on your own。

For instance， do you notice any interesting trends in the max width variable。



![](img/d3f4afa371000ca6a8337479b9766698_50.png)

If you find anything， post your results in the forums。



![](img/d3f4afa371000ca6a8337479b9766698_52.png)

。