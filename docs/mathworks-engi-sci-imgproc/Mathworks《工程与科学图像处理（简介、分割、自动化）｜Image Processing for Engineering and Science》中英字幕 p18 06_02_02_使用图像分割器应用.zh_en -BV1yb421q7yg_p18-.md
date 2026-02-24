# Mathworks《工程与科学图像处理（简介、分割、自动化）｜Image Processing for Engineering and Science》中英字幕 p18 06_02_02_使用图像分割器应用.zh_en -BV1yb421q7yg_p18-

🎼，For some images like this one of a crack in concrete。

 you've seen how simply thresholdholding can produce a good segmentation。



![](img/3405589395c4b477730bf5a8bc3e8f05_1.png)

Often， though， thresholdholding alone will leave you with maskts that need further refinement。



![](img/3405589395c4b477730bf5a8bc3e8f05_3.png)

The exact sequence of refinement steps is usually not known ahead of time。In this video。

 you'll learn how to use the image segment or app to quickly test。

 evaluate and modify different approaches to refine a mask。

You'll also learn how to generate a reusable segmentation function for each approach。Then finally。

 you'll evaluate how each function performs on a new image。

You can find the image segmenter app in the image processing and computer vision section of the apps menu here。

To get started。You'll need to import an image。You can import an image file or an image from the MATLb workspace。

In this case， the images you saw previously are already in the workspace and converted to grayscale。

When you load a new image， you'll be prompted to choose if you want to adjust the image to use the full range of brightness。

This can sometimes help you to threshold， and refine your mask。However， we won't need it here。



![](img/3405589395c4b477730bf5a8bc3e8f05_5.png)

Once you have an image in the app， you'll see several options to create an initial math。

We'll focus on thresholdholding in this video， but you should explore the other options as well。



![](img/3405589395c4b477730bf5a8bc3e8f05_7.png)

Depending on your application， another approach may be a better fit。Clicking the threshold button。

 you'll see an initial mask overlaid on the image。

![](img/3405589395c4b477730bf5a8bc3e8f05_9.png)

Expanding the method menu， the default option is an automatically chosen global threshold。

Adaptive thresholdholding is very useful to segment images， with uneven illumination。

The manual option allows you to choose your own global threshold if neither of the other options fits your needs。

In this case， the global threshold option is sufficient。



![](img/3405589395c4b477730bf5a8bc3e8f05_11.png)

After clicking the create mask button， the option to refine the mask adjust how it is displayed。

And export your results become available。Foreground objects are typically bright。

 So to treat the crack itself as foreground， use the invert mask button in their refined mask options。



![](img/3405589395c4b477730bf5a8bc3e8f05_13.png)

It is sometimes easier to see the imperfections in the mask by viewing the mask in binary form。



![](img/3405589395c4b477730bf5a8bc3e8f05_15.png)

To do this， click the show binary button。As you can see， this mask could use some refinement。



![](img/3405589395c4b477730bf5a8bc3e8f05_17.png)

To get started。Let's select morphology。And see what options are available。



![](img/3405589395c4b477730bf5a8bc3e8f05_19.png)

To eliminate this hole in the foreground， the close operation will work。

A disc shape is a good choice for the structuring element。

Select the radius large enough to cover the hole。Next， to get rid of the extra foregone pixels。

The best option would be to open。Again， you just need a structuring element large enough。



![](img/3405589395c4b477730bf5a8bc3e8f05_21.png)

This segmentation looks pretty good， although it does miss the smaller portion of the crack near the bottom。



![](img/3405589395c4b477730bf5a8bc3e8f05_23.png)

Let's export the results。To save your results， click export。

And either export the mask and masked image to the workspace。

Or generate a function to apply the segmentation steps to other images。In this case。

 let's generate a function。The function code itself is nicely organized， and commented。

But you'll probably want to choose a unique name。Also。

 when you're using gray scale thresholdholding for your initial mask。

 it is often a good idea to add a gray scale conversion step to make sure the function will still work if the input image is originally color。

To try other approaches， you can click back to an earlier step in the history and simply choose different steps from there。



![](img/3405589395c4b477730bf5a8bc3e8f05_25.png)

Or to keep the current segmentation while trying another approach， click New segmentation。

You'll be able to either start from scratch or start a new segmentation from the currently selected step by selecting clone segmentation。



![](img/3405589395c4b477730bf5a8bc3e8f05_27.png)

Maybe there is another shape for the open operation that can eliminate the extra foregground pixels without eliminating the small crack。

To see the available options in the app。

![](img/3405589395c4b477730bf5a8bc3e8f05_29.png)

Expand the shape menu。You can try the different shapes and sizes， without applying them。



![](img/3405589395c4b477730bf5a8bc3e8f05_31.png)

For example， a tall enough rectangle will get rid of the excess foreground。However。

 we're eliminating the small portion of the crack， along with the extra foreground。Remember。

 the shape of the structuring element will determine what parts of the image it affects。Here。

 a line segment at a 45 degree angle will fit within the small crack。

While still crossing the extra foreground pixel areas。

Apply this mask and click the show binary button again to see it overlaid on the image。



![](img/3405589395c4b477730bf5a8bc3e8f05_33.png)

You can see this does a good job of segmenting the crack in this image。

Let's export this as a function too。Again。Giving the function a unique name。

And adding a gray scale conversion are good ideas。

![](img/3405589395c4b477730bf5a8bc3e8f05_35.png)

Now， you may have noticed an option next to invert mask with auring name。Phill holes。

We have been using morphological closing for the initial whole filling。

 But what happens if we use this option instead。To find out。

 let's clone the segmentation at the invert mask step and try it。

This filled the central hole without affecting the extra foreground at all。

You can also use fill holes to attempt to eliminate the extra foreground by first inverting the image。



![](img/3405589395c4b477730bf5a8bc3e8f05_37.png)

Again， clicking fill holes。Then， reinverting。

![](img/3405589395c4b477730bf5a8bc3e8f05_39.png)

This is not bad。 The small crack is still there。The fill holes option does not require you to choose an appropriate structuring element to close holes。

However， since holes are defined as not connected to the border， we did miss some small artifacts。



![](img/3405589395c4b477730bf5a8bc3e8f05_41.png)

Let's export this function， as well。And add the gray scale conversion and unique name， like before。

Now， let's test the three different segmentation approaches on a new image to see if they work well。

The first segmentation function seems to work well。The second one also works。

But you can see the effects of the line segment at the edges are not ideal in this case。Finally。

 the third misses a sizable amount of the crack。When you need to segment many images。

 you'll often need to consider trade offs。

![](img/3405589395c4b477730bf5a8bc3e8f05_43.png)

An approach that does very well on one image may not generalize to others。In this case。

 approach 1 is probably the best。Even though it misses a small crack。It catches both large ones。

 well。In a later lesson， you'll learn how to quickly test your segmentation function on many images at once。

In addition to what you saw here， there are many other options in settings to explore in the image segment or app。

To learn more about what the additional options do or how to use them most effectively。

 just click the question mark in the upper right。And then click getting started with the image segment or app。

Or follow the link below this video。🎼。

![](img/3405589395c4b477730bf5a8bc3e8f05_45.png)