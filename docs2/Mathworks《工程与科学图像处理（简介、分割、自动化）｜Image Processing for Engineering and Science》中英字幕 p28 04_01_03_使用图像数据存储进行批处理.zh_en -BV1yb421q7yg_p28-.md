# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p28 04_01_03_使用图像数据存储进行批处理.zh_en -BV1yb421q7yg_p28-

🎼，You've now processed large data sets using the I batchch processor app。

But how can you do the same thing using code。The standard method is to use what is called a data store。

Instead of loading an entire set of images， a data store stores their locations so that they can be imported and processed as needed。



![](img/bea0adb640e1d9734b44baf3e28bd852_1.png)

In this video， you'll practice using data stores on the digits dataset set。

This collection contains 10，000 grayscale images of handwritten digits from 0 to9。

Each set of digits is stored in its own folder。It is a good practice to have separate folders to organize different types of images。

 because it allows you to use the folder names to label them。

Notice that many of the images are rotated a significant amount。In this example。

 you'll create a table that contains the image's file name， label， and rotation angle。

Begin by opening a new live script in Matlab。Create a data store variable by telling the image data store function。

 the location of your dataset set。In this case， the images are included with Matlab。Specifically。

 they are located in the Nero network toolbox root folder。

Because the images for each digit are stored in separate folders。

Make sure to set the includelude subfolds option to true。After you run the code。

 the new data store variable has saved the location of all 10000 images。

To generate the final data table。You'll first write code to collect the file name， label。

 and rotation angle for a single image。Then you'll wrap that code in a loop to process every image in the data store。

Use the Read image function to import a single image from the data store。

The first input is a data store variable， and the second is the index of the image to load。

Then use the I show function to display the image。When you are processing your own batches of images。

 it's a good idea to vary the index to see how your processing and analysis steps perform on different images。

The Read image function can do more than just load the image itself。If you ask for a second output。

 it will also return the image's metadata， including its location。

 which you can use to save the file name。Next， notice that the label field in the data store is empty。

To extract the subfold names as labels， when you initialize the data store。

 you can use the label source option and set it to use folder names。



![](img/bea0adb640e1d9734b44baf3e28bd852_3.png)

Now， each image has a label。From here， depending on your data set and goals。

 there are many different directions you can go to process and analyze the images。



![](img/bea0adb640e1d9734b44baf3e28bd852_5.png)

Here， remember， the goal is to calculate the rotation angle for each image。First。

 convert the image to binary using the IM binaryized function。

This will then allow you to use the regionion Pros function to calculate the orientation of the digit。

If you want to know more about how a region's orientation is defined。Check the documentation。

You've now set up a workflow to process one image at a time， but executing this code for all 10。

000 images would be pretty time consuming。Instead， you can automate your processing steps by enclosing them inside of a while loop。

To do this， first convert the read image function to just read。

This function always reads the next image in the data store without requiring you to provide an index。

Then you can use the function has data as the wild condition。

 which will exit the loop after all the images have been read。Before you run the code。

 you'll also need a way to store the file names， labels and orientation angles for each image。

Iitialize the empty arrays that will hold this information。Then at the end of the loop。

 combine these variables into a table。Next， inside the loop。

 append the data to each array using vertical concatenation。This way。

 the arrays will grow by one row during each iteration。In order to concatenate the image name array。

The character vector needs to be converted to a string。Now you can run the code to see how it works。

Oops， it looks like there is an error that says all table variables must have the same number of rows。

By hovering the cursor over each of the three variables。

 you can see that the angle array has more rows than there are images。



![](img/bea0adb640e1d9734b44baf3e28bd852_7.png)

This is because some of the images have two or more disconnected regions when analyzed by the region props function。

Such imperfections can be expected because you are using the same segmentation function on 10。

000 images。Knowing that the images with more than one region were incorrectly segmented。

 you could go back to try and perfect the segmentation。



![](img/bea0adb640e1d9734b44baf3e28bd852_9.png)

However， because there are so many images in this data set， it's probably okay to drop a few。

Just wrap the code that appends the arrays in an if statement that checks if there is only one region detected in the image。

Now， when you execute the code again， there are no more errors。

In your workspace is your final data table with a file name， label and angle for each image。

If you want an extra challenge， try to use this data to rotate the images back to their upright orientations。

Now you know how to process images with either the app or code workflows。

You should experiment around with both to better understand how they work。

If you' are looking for more control and flexibility， then try coding your own image data store。

But if you want to quickly test out a series of analysis steps， then the app may be a better fit。



![](img/bea0adb640e1d9734b44baf3e28bd852_11.png)

Yeah。