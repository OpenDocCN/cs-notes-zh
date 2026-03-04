# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P33：33_08_04_图像处理.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/f3b6cc69e6312f21b71532634f15eb0c_0.png)

Now that we've got color， we can move on to more a higher level and more interesting application of abstract data types。

 and that's image processing。AndIn this immediately。

 you're going to be able to write programs to process things like pictures that you take with your cell phone。

So we're going to work with an abstract data type that's called a picture。

 a pitch is a two dimensional array of pixels， again，' it's defined in terms of its set of values。

 a set of values is 2D arrays of pixels。And so that's what we think of a pitch as being。

 and we're going to have an abstract data type that allows us to write programs that manipulate pictures。

And so values are 2 d arrays of colors and just to get oriented。

 we think of this as rows and columns with00 up at the top left。

And so we're going to use two indices to refer to the pixel and at a particular place。

 we have its column and we have it a row， and that's how we're going to refer to individual pixels it's got a certain width and a certain height。

So just with that orientation then we can define the operations that we're going to perform on pictures first one is a constructor。

 how do we make a new picture well what we're going to do is take a file name as argument and that file name is going to be an image that comes from your camera could be JPEG file or other standard file format。

And then once the constructor has made the image， we can think of it as a two dimensional array of pixels。

We could also create a blank one and then we can ask for properties of the picture like it's width in its height。

 we can ask for the color of a particular pixel given a column in row as long as the column index is within the width and the row index is within the height。

And we can also set the color of a pixel to be some other color。

And then the other thing we can do is just display the image in a window like standard draw。

 know there's also a method in standard draw to display pitches。

 but this just displays the thing in a window。So those simple operations， again。

 we don't really care how the pitch is represented and how the system gets these jobs done。

 we can work with pitch just using these very simple operations。

Oh and also we can save any picture that we've created back out to a file。

So here's an example we're going to do is write a Java program that'll convert an image to grayscale。

 so if we take our mandl in this image by the way， is a standard image that's been used for many decades in computer graphics。

 so that's the one we're using。If you type Java gray scale and give that final name。

 then it'll give this black and white version。呃。Interesting computation。

 so you can make black and white versions of photos that you take on your phone yourself if you want。

So how do we do that， it's a very simple program we get access to the Java's color module with that import and then we just write a mean that first of all it's going to create a new picture and wheres it going to get that picture。

 the first argument is going to be a file name and so the constructor takes that file name if it's a JPG file then it'll use that to create a new picture which now we can manipulate as an array。

 a 2D array of colors。And then what we're going to go do is go through and for every pixel。

 we're going to get its color。So we'll go for all columns and for all rows。

 it's a doubly index for loop to look at every possible pixel we're going to our picture is named PIC your pick。

And so that's stored in a picture object with PIC dot get， that means take that object。

 and then the dot means apply the operation to that object and the get operation gets the color at the given column in row。

So that returns a color and then that's a variable of type color with a capital C so now we're going to compute with that and what do we want to do with that。

 we want to just go to our illuminance library and get the two gray method that we just did that computes the grayscale value with that in another color gray and then in our picture we'll call the set method to change the color of that pixel at that column and row index to that gray value and that's it。

And when we're done with those four loops， just show the picture and that's it。

 an extremely simple program to go ahead and compute any color image into a black and white image。

Now， let's look at some more examples。 just to warm up to do some more interesting computations。

 we'll do a little series of pop quizzes。 So let's think about what's the effect of this code。

 This is a very easy question。 for all the pixels。 What we're going to do is。

Take our picture and set the pixel at column and row to what the color that you get from getting the pixel from column and row。

 Well， that one obviously does nothing。 It just shows the picture。

But that's a warm up for let's do something， try to do something more interesting。

 This one's not so easy。So now what we're trying to do is set the one at column and rather than row。

 we do height minus rh minus1， so the one at the top becomes the one at the bottom and so forth。

So it looks like we're trying to turn the pitcher upside down， but doesn't really work。

 kind of takes the top half and puts it on the bottom half。

 but then it's already done because it's overriding the same picture。

So that's a bug that's worth thinking about what we need to do if we want to do this upside down thing is create a totally new picture。

 and so that's the answer to this question。We're going to take。Our source picture。

 which is the one that we get from the file name and the command line。

 We're going to get the width and the height of that picture。

 and then we're going to create another picture， the target picture。

 and we'll create a blank picture of the same width and height。

 and then we go through for every pixel and we set the pixel in the target picture there we can do the。

Rose upside down not to the color that we get from the。

Sour picture and then show it so that one actually does make an upside down copy of the image。

So but all lots of our pixel pixel processing programs have this same concept of we go through for every pixel and set it to some value。

 maybe it's a value that is a function of value in some source so this is a classic example。

 a scaling filter in this one it useful in lots of context so what we want to do is write a Java program that will scale an image kind of arbitrarily and independently so if that's my mandl then it's a 300 pixel by 300 pixel image maybe I want to make it bigger like 500 by 500 or maybe I want to squash it make it 600 by 200。

Or I don' want to make a tiny one or a long up and down one。

So I want to arbitrarily scale the image and there's lots of applications where we need to do this maybe to get an image to fit in a certain space and maybe scaling it just by a little bit extra in one dimension or the other just to make it fit and it wouldn't be noticeable so that's anyway our computational challenge let's scale an image。

Now for example， let's say you had to cut it in half。

 so one way to do it is to just downscale by just deleting alternate rows and columns so that example you're going to lose some detail when the picture isn't big enough but anyway that's an option。

Or you can upscale by doubling， so that's to make a picture twice as big。

 just replace each pixel with four copies of itself。And then if you were to do that back and forth。

 you don't really get quite the same image back， but that's going to be an issue when we do scaling。

 fortunately our pictures there at high enough resolution that there's maybe not these effects are maybe less noticeable than you might think。

But we want to do this in a systematic organized way and so here's a strategy that will get this scaling done。

 so if we got our source width by height and our target width by height。

 what we're going to do is just take the ratios of those differences to get ourselves column and row index。

But the key thing to do is to set up the computation that really what we want is we want each target pixel to get have a specific value and so we're going to do that by scaling from the source making sure that we get a defined pixel value for every row and column in the target and to do that we just take whatever row index we get by scaling the target row index and whatever column index we get by scaling that and doing the transformation so it turns out to be a pretty simple program so we take as input and the first command argument。

 the file name which is the picture that we want to scale and then we take the width and height that we want out of that picture so we create new picture from the file and that's our source and we create a blank。

Picture of size W by H， that's our target。And so now what we want to do is for every pixel in the target。

 we want to figure out where we're going to have to go in the source to get a pixel that's close to where it should be according to the scaling and so that's what we'll do we'll get some column and some row in the source we'll get that color of that pixel and then set our target pixel to that color that way we've got a good color for every target pixel。

And then we show it and takes a little thought， but that's a pretty compact program to get this scaling job done。

And works fine for our mandro。This one is， is worth studying， but it's indicative of the。

Ability that we have with image processing to really do quite a bit with our images all we need to do is make sure that we set every pixel in the target to some color and people have studied lots and lots of different transformations that we can perform on pictures and you'll have I think some fun doing this with pictures that you've taken from your cell phone。

So you can separate out the RGB colors， that's a thing called a swirll filter， that's a wave filter。

 glass filter， all these types of transformations are actually not so difficult computationally。



![](img/f3b6cc69e6312f21b71532634f15eb0c_2.png)

So all the kinds of effects like this， and you can see how to do them on your own pictures in the book site or in the book。



![](img/f3b6cc69e6312f21b71532634f15eb0c_4.png)