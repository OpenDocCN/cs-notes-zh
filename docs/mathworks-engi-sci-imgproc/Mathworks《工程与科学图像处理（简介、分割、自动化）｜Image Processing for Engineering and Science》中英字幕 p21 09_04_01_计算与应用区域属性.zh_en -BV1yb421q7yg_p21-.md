# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p21 09_04_01_计算与应用区域属性.zh_en -BV1yb421q7yg_p21-

🎼。

![](img/a556449d785addf1b6ca0a27ddc0e178_1.png)

In many applications， segmentation is just one step towards a larger goal。



![](img/a556449d785addf1b6ca0a27ddc0e178_3.png)

Often， you'll need to analyze the segmented regions further by calculating things like area。

Perimeter。Shape。And location。Or using these properties to isolate specific regions。



![](img/a556449d785addf1b6ca0a27ddc0e178_5.png)

To do this， start by opening the Region analyzelyr app。

You'll find it in the apps tab grouped with the other image processing and computer vision apps。Next。

 load the mask into the app。

![](img/a556449d785addf1b6ca0a27ddc0e178_7.png)

You'll notice a list of properties for each region is automatically populated on the right。

You can add or remove properties using this menu。There are regions corresponding to one，2。

 and three puzzle pieces in this image。

![](img/a556449d785addf1b6ca0a27ddc0e178_9.png)

Let's select a few properties that might help us distinguish the different regions。



![](img/a556449d785addf1b6ca0a27ddc0e178_11.png)

Regions with more puzzle pieces should have larger area， so let's see if that is true。

Notice that selecting a particular row in the list highlights the corresponding region in the mask。

Sorting the properties table by area will help here。

This makes it easy to tell that both regions with three puzzle pieces attached。

 have areas above 20000。The regions with two puzzle pieces attached have areas approximately between 12 and 18000。

The regions with areas 9 to 10000 correspond to single puzzle pieces。Finally。

 the two regions with relatively small areas in the 20s are small artifacts in the mask。Thus。

 area can be used to isolate regions with different numbers of pieces。

Let's isolate the regions corresponding to three connected puzzle pieces。To do this。

 click on the filter drop down and make sure area is selected。

Then increase the lower bound for the range to 20000 pixels。Great。

 this filtered out everything except the regions with three pieces。

Filtering by region properties enables you to focus on objects of interest and is often used to remove small artifacts as it did here。

Now， to repeat this workflow or apply it to similar masks。Use the export function option。



![](img/a556449d785addf1b6ca0a27ddc0e178_13.png)

The generated function uses BW Pro F to apply the filtering selected in the app and generate the new mask。

For each filtering operation， the property is specified and arranged provided。

To add some buffer to the upper end of this area range。

 just increase the second number in the brackets to something like 28000。

The function also returns the calculated properties themselves。

A comma separated list of each property will tell the region props function to return them as part of either a structure by default or a table。

To get a table output from this function， unment this line。

It is a good idea to give the function a meaningful， unique name。

The Region analyzer app is a quick way to gain insights about your regions and filter them。

The region prop's function can return even more information。

See the documentation for a full list and description of each available property。For example。

 you may have seen images like this。Where a bounding box is used to highlight regions of interest。

Let's see how to create this。

![](img/a556449d785addf1b6ca0a27ddc0e178_15.png)

Start with the original image and mask in a script。



![](img/a556449d785addf1b6ca0a27ddc0e178_17.png)

Next， apply the previously generated function to the mask。



![](img/a556449d785addf1b6ca0a27ddc0e178_19.png)

Then use the region props function to get the coordinates of a bounding box for each region。Finally。

 use the inserts shape function with the coordinates of the bounding boxes。

It is often helpful to specify a color， as well as adjust the line width。To improve visibility。

In this video， you learned how to calculate region properties using both the Regent analyzelyr app and code。

You filtered the mask using reent properties and generated a function to repeat the analysis。

You also use the region properties to highlight specific objects in an image。



![](img/a556449d785addf1b6ca0a27ddc0e178_21.png)

🎼。