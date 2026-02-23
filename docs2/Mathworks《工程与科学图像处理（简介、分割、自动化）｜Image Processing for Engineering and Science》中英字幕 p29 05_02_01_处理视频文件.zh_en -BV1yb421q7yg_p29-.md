# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p29 05_02_01_处理视频文件.zh_en -BV1yb421q7yg_p29-

🎼。

![](img/81a3b67541beeb8ded26f37f02fe530a_1.png)

Video files appear in a variety of applications。 And because there are a series of images。

 you can use the segmentation skills you've learned so far to process videos as well。😊。



![](img/81a3b67541beeb8ded26f37f02fe530a_3.png)

For example。Consider the goal of analyzing the rate this container fills with liquid。

You can do this by accessing the individual video frames。

And segmenting each frame to calculate the percentage of true pixels。When introduced to a new video。

 a good first step is to use the video viewer app to learn more about it。😊。

Start by importing the video。Select the liquid video included with the course files。

After opening the video， the app displays the video resolution。Frame rate。And total number of frames。

Controls are included to play the video or jump to a particular frame of interest。

To determine how much liquid is in the container， you need a segmentation function that separates the liquid。

From the background。Choose a few representative frames from the video to use for developing this function。

And export them as images。Here we saved frames，92。185。And 224。With your representative frames。

 use your segmentation skills to create a mask to isolate the liquid。

We use the color Thr app to create ours。You'll need to create your own function to do this analysis。

Once you're satisfied with the processing steps on the sample frames。

It's time to apply them to the entire video。Use the video reader function to create an object for reading the individual frames in the Matlab。

Notice how this object contains a lot of information about the video。

You access these properties by typing the variable name， followed by a dot and the property name。

To process all the frames， use a for loop， starting at one。

And ending at the total number of frames in the video。Inside the loop。

 use the read frame function to import the next available frame as an image。

Now you can apply your processing and analysis steps。As an exercise。

 you'll need to create several variables inside this loop to calculate how full the container is at each time point in the video。

Use the current time property to get that information for each frame。

It's also a good idea to reset the current time property in case you run the for loop again。

At the end， you should have a figure similar to this。But wait。

 what if you get some unexpected results。How can you tell what went wrong in the processing steps。

One approach is to create a video of the processed images for visual inspection。

Use the video writer function to create an object for writing images to a video file。

Specify the file name。And video format as inputs。As with the video reader object。

 you can view the properties the output video will have。Notice the default frame rate is 30。

 which doesn't match our original video。Let's change this。 So they're the same。To create a new video。

 you need to open the video writer object before the for loop。And close it after the forlo。

Inside the fore loop。Pass an image to the right video function。In this example。

 we're using the I Mfuse function with the montage method to create an image of the original and processed image side by side。

After running the code， you'll have a new video in your current folder。

That you can view in the video viewer app。Use this video to verify your processing steps and identify frames for further investigation。

In summary， when working with video files， it's a good idea to use the video viewer app first to familiarize yourself with the video and export some frames。

😊，Develop your processing and analysis with these frames。

Then use a video reader object with a loop to process all the frames。

Visually inspect your image processing results using a video writer object。🎼If necessary。

 export new test frames to refine your approach。

![](img/81a3b67541beeb8ded26f37f02fe530a_5.png)