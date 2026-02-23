# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p27 03_01_01_使用图像批处理器应用程序.zh_en -BV1yb421q7yg_p27-

🎼，Consider the data set of concrete crack images。To determine the severity of each crack requires first segmenting each image and then calculating the crack properties from the binary image。



![](img/cc9589d09e49d3575948bf65092de4b4_1.png)

![](img/cc9589d09e49d3575948bf65092de4b4_2.png)

To complete this workflow on hundreds or thousands of images， you'll need to automate this process。



![](img/cc9589d09e49d3575948bf65092de4b4_4.png)

![](img/cc9589d09e49d3575948bf65092de4b4_5.png)

You can combine the automation into two steps。First。

 test and refine the segmentation function to ensure it works well on most of the images。

Then combine the segmentation and analysis functions to automate the entire workflow。



![](img/cc9589d09e49d3575948bf65092de4b4_7.png)

To begin， you need to check if the segmentation function works well。



![](img/cc9589d09e49d3575948bf65092de4b4_9.png)

You could manually run the function repeatedly on each new image。

 but this process would quickly become tedious。A better option is to use the image batch processor app。



![](img/cc9589d09e49d3575948bf65092de4b4_11.png)

After opening the app， load in the folder containing all the concrete images。



![](img/cc9589d09e49d3575948bf65092de4b4_13.png)

![](img/cc9589d09e49d3575948bf65092de4b4_14.png)

And select the segmentation function。Processing hundreds or thousands of images can take a long time。

So it's a good idea to only do a few images to start。 This way。

 you'll quickly learn if the function isn't working well。Process the selected images。

Then show the segmentation mask alongside the original image to compare them。So far。

 the results look promising。So let's apply the function to all the images。

Many of the binary images look good。But notice that this segmentation function does not work well all the time。

By visualizing the original and processed images in the app。

 you can quickly determine if your processing steps need further refinement。



![](img/cc9589d09e49d3575948bf65092de4b4_16.png)

Working with multiple images is an iterative process。



![](img/cc9589d09e49d3575948bf65092de4b4_18.png)

First， develop your image processing steps on a few images。



![](img/cc9589d09e49d3575948bf65092de4b4_20.png)

Then use the image batch processor app to determine if the processing steps need adjustments。



![](img/cc9589d09e49d3575948bf65092de4b4_22.png)

![](img/cc9589d09e49d3575948bf65092de4b4_23.png)

Once you're satisfied with the results， you can export them for further analysis。



![](img/cc9589d09e49d3575948bf65092de4b4_25.png)

In this case， images 165 and 166 are not well segmented。

We have already used these images to refine the segmentation function。



![](img/cc9589d09e49d3575948bf65092de4b4_27.png)

So now we can retest the new function on all the images。The results look much better。

Remember that the final goal is to perform region analysis on the cracks to determine their severity。

 to automate the entire process， you need to create a single function that combines the segmentation and analysis steps。



![](img/cc9589d09e49d3575948bf65092de4b4_29.png)

In the image batch processor app， you can create a new template function that takes in an image as input。



![](img/cc9589d09e49d3575948bf65092de4b4_31.png)

And returns a single output variable。

![](img/cc9589d09e49d3575948bf65092de4b4_33.png)

For this example， the exact code for this new function will be covered in an upcoming reading。

 but for now， you'll learn the general process of how to generate your own function。First。

 delete the sample code。Next， you'll pass the input image to the functions that pre processces the image and produce the segmentation。

Then apply the analysis functions to the segmented image。

Both the binary image and the region properties can be saved as a single output variable using the structure array data type。

A structure is a container for multiple variables， which you can add using dot notation。

These lines of code add the binary image， number of regions， total crack area。

 and maximum crack width to the output structure variable called results。



![](img/cc9589d09e49d3575948bf65092de4b4_35.png)

When you're done。Be sure to save the function file。



![](img/cc9589d09e49d3575948bf65092de4b4_37.png)

Now it's time to check that this function works by applying it to original unsegmented images。



![](img/cc9589d09e49d3575948bf65092de4b4_39.png)

And visually inspecting the results。The cracks that look larger do indeed have larger area values。

Save your results for further analysis by exporting them to the workspace。

This allows you to save the region properties as a table variable。



![](img/cc9589d09e49d3575948bf65092de4b4_41.png)

Now， you can use this table to perform further analysis。

 such as studying the distribution of crack areas。

![](img/cc9589d09e49d3575948bf65092de4b4_43.png)

In this video。You learned how to automate your image processing and analysis steps。

When working with your own data sets， don't forget that image processing is an iterative process。

You may need to improve upon a function multiple times to effectively process an entire collection of images。



![](img/cc9589d09e49d3575948bf65092de4b4_45.png)

。