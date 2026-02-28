# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p62 62_05_02_灰度算法：七步法.zh_en -BV18U411U729_p62-

![](img/8ddf0b467d83355827a24f6ffcc42d38_0.png)

Welcome back You' are currently learning how to convert a bunch of images to grayscale an important component of that process is the ability to convert one image to grayscale in particular you want to take a color image and produce an image that looks like it but only uses shades of gray。

 not any colors， as with all programming problems the way you want to approach this problem is with the sevenstep approach you've learned previously。



![](img/8ddf0b467d83355827a24f6ffcc42d38_2.png)

The first step is to work an instance by hand， As always， we must work with a small。

 manageable problem size here we picked a2 by two image to work with。

 We are going to want to make a two by2 image for the output。

 but how do you figure out what shade of gray to use for this pixel。

You need domain knowledge before you can proceed in this particular problem。

 the knowledge you need is about colors or graphics。

The first thing we need to know is what precisely is a shade of gray？

A color is a shade of gray if its red， blue， and green components are all the same。However。

 this knowledge by itself is not sufficient to tell you how to come up with the shade of gray for a particular color。

 just that the result needs to have their red， blue， and green all the same。

One way you could do this is to average the red， green， and blue components。

 or you might decide you want a weighted average because the human eye does not perceive all colors in the same way。

There could be more complex alternatives， however， just taking the average works pretty well and is simple。

Now you have the domain knowledge required to do this problem yourself。

You can look at the RGB for a pixel， compute the average。

 and color in the output pixel appropriately。Then you would go through looking at the RGB values for each input pixel。

 computing their average and coloring in the output pixel accordingly。

 Once you have colored in all of the pixels， you've worked an instance of the problem yourself and are done with step1。

The next thing you need to do is write down exactly what you just did。

 I started with the image I wanted， which we called an image。

Then I made another image of the same size， which we called out image。I computed 255 plus0 plus0。

 divided by3， which was 83， and I made the first pixel of out image have red。

 green and blue values of 83。And then I went through each other pixel。

 computing the average of the RG and B and coloring the output pixel accordingly。



![](img/8ddf0b467d83355827a24f6ffcc42d38_4.png)

Once we finished this， we had。These 10 steps that we use to solve this particular instance of the problem。

 Now you are ready to move to step 3 and look for patterns and repetition。

 You can see that we are doing very similar things to each pixel， but they are not quite the same。

 We need to find the patterns in the number。To generalize these steps to any image。

 let us look at the particular numbers we need to generalize。Why did we use 255 here and zero here？

These numbers were all the corresponding pixel in in Iage's red component。What about these numbers。

 Similarlyly， these were the green component of the corresponding pixel in an image。Lastly。

 these numbers were the blue component of the corresponding pixel。Next。

 you should give a name to the result of this math。

 it won't always be these particular numbers and you will want to be able to refer to it precisely。

 we'll call it average。

![](img/8ddf0b467d83355827a24f6ffcc42d38_6.png)

Okay， now that weve thought that through， you can write the general algorithm。

 notice how we thought about what we do for each pixel and wrote down general steps now we can write this in terms of steps to do to each pixel in the output image。

 it will work for any size image with any colors。The last thing you should do before you write code is to test your generalized algorithm out on another small input here is a small image and the RGB values for each pixel take a moment to execute the algorithm and see if you get the correct answer。



![](img/8ddf0b467d83355827a24f6ffcc42d38_8.png)

Yes， the answer is right， so youre ready to implement it in code。

