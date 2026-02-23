# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p04 04_02_01_在MATLAB中表示图像.zh_en -BV1yb421q7yg_p4-

🎼，MaTLB is used by scientists， engineers， and other professionals to perform common image processing tasks。

But before you can process an image， you must first import it into Matlab。So how do you do that？

In this video， you'll learn how to import images into Matlab。

And how image data is represented by numericalmer rays。

You'll also learn how to extract intensity values from image arrays。

And explore image data using the image of viewer app。To import the image data。

He used the I M read function。The data is returned as a numericalmer ray。

And stored in a new variable。Note that your images should be in your current folder or on the MatLb search path。

You view images using the IM show function。Examining the output more closely。

 you see that the import of images are represented as an array of integers。

The total number of rows and columns correspond to the image resolution。

While the individual array values represent the pixel intensities。

You might have also noticed that the image data is of type U in 8。

 which is different from the data type double used by MatTLb to represent most numeric data。

Note that while double variables can represent a wide range of numerical values。

 including negative and decimal values。U and 8 variables can only represent the set of integers between 0 and 2。

55。So why not use doubles to store image data？To see why。

Extract an individual pixel value from the image array by providing the location of the pixel in terms of the row and column number。

Then obtain the corresponding double value using the double function。

 which is used to convert the data type。Lastly， use the whosese function to display the variable information。

The double value requires eight times as much memory as the U8 value。

Note that this memory cost does not depend on the value。

An intensity of 0 requires the same amount of memory to store as an intensity of 2。

55 or any number between。This difference may not matter much for a single value。

But the difference becomes significant when multiplied by the large number of elements in a typical image array。

This is especially true for high resolution color images。Speaking of color images。

 they are also loaded and viewed using the I M read and I M show functions。

The main difference between gray scale and color image data is that there are now three intensity values per pixel。

 one for each of the red， green and blue color channels。

The need to store three intensity values means that a color image array is three dimensional。

Where the intensities for each color are stored along the third dimension。

To access the color intensity for a single pixel， provide the row and column location as before。

Followed by an additional value between one and3， corresponding to the color you want to inspect。

Replace the third value with a colon to extract all three intensities。

The colon is shorthand for all values in that dimension。

Using colons in the row and column dimensions instead allows you to extract all intensities for a given color channel。

The result is a two dimensional array that can be visualized as a gray scale image。

Since this is the green color channel， bright areas indicate pixels with high green intensities。



![](img/8b59f1829609d977cc58fa9e79cc0119_1.png)

![](img/8b59f1829609d977cc58fa9e79cc0119_2.png)

Dark areas indicate low intensity values。Interestingly。

 the green intensities seem to be higher in the yellow flower petals than in the green leaves and stems。

😊，It's challenging to predict brightness and color based on intensity values alone or to estimate intensity values based on the image。

Therefore， it's helpful to inspect the image and the intensities using the image viewer app。

Use the IM tool function with an image variable or file name as an input to load the image。



![](img/8b59f1829609d977cc58fa9e79cc0119_4.png)

The app automatically previews the image and provides a way to interactively inspect the image and data at the same time。

For example， hover the cursor over the image to display the pixel location and intensity values。

Or click the ruler to measure the pixel wise distance between two points of interest。

If you are interested in a particular region。Use the zoom button to enlarge the area and the pan button to navigate around the image。

To investigate the pixelel values， select Pixel region from the tools menu。

This opens an overlay of the intensity values in the selected region of the image。

The pixels in the pedal region seem to have green intensities between 1，40 and 1，50。

After panning to a leaf， you can see that the green intensities are， in fact。

 lower than the yellow flower petal。That's because brighter or whiter pixels often contain high intensities in two or more channels。

Which can be difficult to predict using visual inspection alone。

In cases where you want to limit your focus to a single region。

 use the crop button and adjust the box as needed。The result is a new image。

 which can be analyzed further。Or exported as a variable。In this video。

You learn how to load and display images and how gray scale and color images are represented in Matlab as integer arrays。

You also learned how to extract image data from arrays by providing row， column and channel values。

 or using the colon operator。Lastly， you saw how the image viewer app is used to interactively explore image data。



![](img/8b59f1829609d977cc58fa9e79cc0119_6.png)