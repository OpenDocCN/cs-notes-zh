# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P14：14_04_03_标准绘图.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/348050db896c29bf8a3a050dd6f62bb7_0.png)

Next we're going to look at another abstraction for output that's extremely flexible and you'll find very useful in having your programs produce output that's useful。

 it's called standard drawing。So now we're going to extend our IO abstraction to add the ability to create a drawing。

We're going to use a relatively small set of commands。

 but you'll be surprised at the interesting output that you can produce with a small Java program。

Again， this is a library that we develop for this course but is still broadly useful and again it's available at the book site and is in the package that software。

 the intraRCS software that you've already downloaded。

So the standard draw library is again a list of static methods that you can make use of。

 so there's a method to draw a line， a method to draw a point。

We give coordinates within an abstract drawing。you can plot text at a particular position。

 you can draw a circle of a given radius or square。

 and you can actually also fill them with black or white or gray color， some other color。

You can place a picture that's in a file， a G or J Pe or P&G file at a particular place。

 there's the ability to set the thickness of the line or the pen radius。

 the color and then there's some scaling methods and we'll take a look at using each one of these。

So that's a relatively small library functions that we're going to use to produce a lot of interesting effects with our Java programs。

And then maybe the critical one is show where we're going to show everything that we've drawn in the drawing。

So let's look at a hellello world program for standard draw by a Helloor program we mean a simple program that will illustrate all the things that you need to do to use this library。

 so we're going to draw a triangle。So the drawing is， again。

 an abstract drawing with00 down at the lower left hand corner。

And so what we're going to do is compute square to3 over2， so that's value C。

 set the pen radius to be 100 so the drawing size。And draw a line from 0，0 to 1，0。

 So that draws a line right at the bottom of the abstract drawing。Then we'll draw one from 10。

 which is over here to the top of the triangle， which is x coordinate half and y coordinate squared to 3 over 2。

And I'll draw another line back to the origin from that point back to the origin。

That's a program that draws a triangle and just for variety。

 we'll draw a point in the middle and we'll put some text there too as well。

So that's drawing lines and points in the standard draw window。Draw a triangle。

 that's the hellello World program。So let's look at the mechanics of doing that we have a couple of terminal windows one to edit the program and another for the command line again。

 that's the way that we work in lectures so it's a virtual terminal for the editor another one for operating system command lines and so I compile that program and it's fine so now I run it and what happens is another window pops up with the standard drawing。

That's what you need to know in order to do drawings， you can draw lines anywhere you want。

 you can draw points anywhere you want， and that's a very effective output device in lots of situations。

Let's look at an application from data visualization as I mentioned it's often the case that we have huge amounts of data to process and one technique is to try to visualize what that data is doing or means in a drawing。

 so here's an example。So this is just a filter that takes data from standard input and plots it on a standard draw。

So everything's on standard input and we're going to format our data such that the first four numbers give the coordinates of a bounding box。

 a minimum and maximum X and Y coordinates of all the points that follow。

 so we'll read those four coordinates。Then we'll rescale using those coordinates so that all the points fit right within the drawing window。

 so that's all we're doing is telling standard draw to rescale the drawing so that the smallest x is X min and the largest Y is Y max and so forth。

So now what we're going to do is just read from standard in XY coordinates。

 so pairs of numbers that are Xy coordinates within that bounding box and then draw a point at that coordinate in the drawing。

That's it。So pretty simple program could hardly be simpler， we get some data about the points。

 we get all the points， and the number of points could be huge。

 this program takes them from standard input， so the number of points is unlimited。

So here's a file that you can download and there's a lot of similar ones out there where it's USA。t。

And so the first four coordinates are the bounding box coordinates for the points in this file。

 so X min is 66，99 and x max is12 and so forth， so that's just the way the coordinates are scaled。

And then in this particular file， there's 13，509 points。Now you can look at this data。

 all you want and write programs to process it， but our point right now is that just using this simple program。

 if we run it， taking that from standard input， we can see a lot more about what that data is。

And learn a lot more about it if our interest is in studying the clustering near cities or whatever you need to whatever you want a program。

 you might want to lay out what you have learned or what you think you've learned on a visualization like this。

 maybe you want to find some circles that cover the maxal numbers of points or whatever of a computation that you might want。

Data visualization is very important in modern computing。

 and it's also very easy to achieve with a tool like standard draw。

Here's another application that we want to do all the time。

 we have a function and we want to plot it。Again， the easy way to do that is to just take samples from the function and just draw lines connecting those sample points regularly spaced again。

 this is a very easy program to write with standard draw so we take the number of points that number of samples that we want to take from the command line。

And then in this case we're going to make arrays of that size and what we do is for i from one to n for each sample。

 we're going to compute where our x and Y coordinates and we want to equally space these from zero to pi and so that's where x coordinate and then our Y coordinate is just evaluating the function at those points。

So again， we're going to set the scale of the drawing to be between0 and pi and we'll set the y scale because we know about the function to be between minus 2 and 2。

 and then to just go through and draw the points。

![](img/348050db896c29bf8a3a050dd6f62bb7_2.png)

We could have set this up so that wed draw the points one at a time。

 but this is the way this program is going to work。

 A lot of times you have your function in an array and you just want to plot it。

So here's an example that plots that function with 20 points and any function you want you can plot this is another lesson though。

 and this lesson is going to come back to us in the next lecture。

 you want to make sure that you take enough samples that you see everything that's going on in the function In this case we missed a lot by taking too small a sample。

 There's a lot of fluctuation that goes on in between those sample points。But still。

 we have the flexibility with standard draw to create the plots that we need to understand the functions that we're working with for a whole host of scientific applications。

 and from this point forward， we're going to be using standard draw extensively。



![](img/348050db896c29bf8a3a050dd6f62bb7_4.png)