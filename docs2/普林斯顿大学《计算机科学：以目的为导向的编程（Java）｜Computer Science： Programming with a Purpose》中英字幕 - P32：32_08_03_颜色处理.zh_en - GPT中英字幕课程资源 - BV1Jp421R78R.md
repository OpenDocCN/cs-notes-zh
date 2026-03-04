# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P32：32_08_03_颜色处理.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/1dc82d450c790645e43b57dc2b122ada_0.png)

As a first substantial example， we're going to talk about kind of an ultimate extraction color。

So what is color， well， without going into all the details。

 we're going to say it's a sensation in the eye from electromagnetic radiation。

But from the current context， what we're interested in is an ADT that allows us to write Java programs that manipulate color。

And it's a fairly simple abstract data type， the values are going to be red， green and blue values。

 they're going to be int values， eight bits integer values，8 bits each。

 which are the intensity of the red， green and blue in the color。

 and you mix them on the display or on a printed page you're going to get an associated color。

So if you have all red， no green and blue， then you get this kind of red， or for all green。

 it's kind of a bright green， all blue， it's kind of a bright blue， but if you have mixed values。

 then all zeros is black and all 255s is white and then in between we get the colors that we use in the slide in the book so a nicer blue and a more pleasing looking magenta。

So that's what a color is a。A triple of 8 bit values。And if they're all the same。

 you always get something on a gray scale and we'll see that in a minute。

So the API now just has to define the set of operations that are valid on colors。

The first entry in an API for an ADT is always the constructor。

 so it's the name of the data type in this case color and it's capitalized。

 and then the constructor can take arguments that it can use to create an object and initialize its values in this case the constructor creates an object with the given values RG andB。

And then we have methods that a client program can call to get the various intensities back out of the data type。

And then maybe other methods like make a brighter color， make the color a bit brighter。

 or make it a bit darker。And then usually we have a string representation。

 which is two string and we do that because a Java a convention is if you put an object in a print line statement。

 then it'll automatically convert it to a string， or if you concate it with a。

So those are the basic methods that we're going to have for manipulating color。

 and now we're going to write Java programs that use those methods。Oh， I forgot equals。

 you might want to test whether two colors， one colors equal to another one。 in this case。

 I have an object that's got a certain color value and as an argument。

 I take another color and I want to compare if my values are equal to that color's values。

Okay so as a concrete example we're going to look at Al squares。

 Joseph Albers was a 20th century artist who really changed the way people think about color with a very simple device what he did was produce paintings with squares of different colors within one another。

 and the relationship among these squares give a very interesting perspective about colors he's got a book and it really really changed the way people think。

 and so what we want to do is now is write a Java program that lets us produce these squares with our colors。

That's Albers in front of one of his paintings in black and white。

So our goal is to write a program to generate Albert squares and we'll do simple ones with one square in front of another。

 so we'll want to call the program and we want to give six command line arguments。

 the first three or one color the second three or another color so that's the kind of output that we want to get is two squares next to one another with one of them with the first color and the bigger square and the second color in the little or square and then the other one those reversed and then we can type in any colors we want and we can get these squares and right away you can see some of the interest in Albert squares in that not always clear to the eye that the colors are actually the same on the left and right and anyway they make a very interesting comparison depending on the color。

So we want to write a Java program that does this。 Well， with our color ADT。

 that's extremely easy to do。So。We have a main program。

 and it's going to take the RGB values for the first color from the command line and then create a new color。

So we have a data type color。We have a variable C1， it's of type color。

 and to that variable we're going to assign a reference to a new object that we create by calling the color constructor with those RGB values。

And that's how we do it we have a well definedfin data type， we have a variable refers to an object。

 that data type， object is the thing that holds a data type value。

 we use a constructor to build that object。Then we do the same thing for the second color so now we have those two colors and now we can use the set pen color method from standard draw to get our job done。

 we have a little bit of geometry to do the leftmost square is centered at 0。25 and 0。

5 and the right one is centered at 0。75 in half and the little square is 0。

1 radius and the big square is 0。2 radius but with that little bit of math we set our pen color to the first color then we draw a big square of that color。

And then we set it to the second color and draw the littleer square of that second color that draws the one on the left。

And then we just switch the colors， C2 first， and then C1 to draw the one on the right。That's it。

 that's a program that draws Albert squares and you're welcome to use this program to play around with Albert squares of any color at all that you'd like。

 very simple client but it's profound because we're actually now computing with the different type of data we're computing with colors。

 not just with the numbers that Java provides us in its primitive types。

Here's another interesting computation that we'll use later on。

There's a thing called the monochrome luminance of a color and it's a way to quantify how bright the color is and that's important in plenty of applications and we'll look at a couple of applications in a minute。

 and there's a standard formula that has been developed for luumminance and it's a simple linear combination of the RG and B values。

 about 30% red， a little less than 60% green and a little more in 11% blue。

That's just type in the plug in the RGB values and you get a number since these add to one。

 you get a number of this between 0 and 255， that is the luminance。

So that's going to be pretty easy to compute。 We're going to have a static method that takes a color as argument again it's。

Sorry， it's not a built in type of data， but we can use it the way that we use any other type of data。

And then so that static method takes C as an argument， and then it uses the defined operation。

 get me the red component， get me the green component， get me the blue component。

 and then it just returns the double value that it gets by。From the equation。

That's a static method that computes the luminance。

 and then we'll have a main that reads in RGB from the command line。

 creates that color and passes it to our luminance thing， and then it's a double value。

 it'll print out the integer closest to it， which will be between 0 and 255。So for example， 0， 64。

 128， the luminance is 52。Again， that's a simple program， useful， and we'll see that it's useful。

 we'll using in some applications and it's computing with this data type that is not what a job is built in data types。

Here's just some examples of luminance， so all red the luminance is 76， black is zero。

 white it's 255 and our other colors， those are the values if you have a gray。

 then it's just going to be the same value coming out again they're all the same waiting them doesn't matter it's all the same。

So those are examples of the luminance that you get for our example colors。Okay。

 so we're going to look at two applications， one is if you see on your screen a web page。

 there's various colors， sometimes it's easy to read the displays， texts， other times it isn't。

 that has to do with this luminance。And also converting to gray scale is another application。

 we'll look at both of those in just a minute。 First application we'll look at is compatibility。

 So the question is， which font color should you use for a given background color on a display。

And the answer is is a well knownn rule of thumb that the absolute value of the differences in the luminosities should be bigger than 128 if you want to be able to read them legibly。

 and so we can write another static method that just computes this takes two colors as argument and just computes the absolute value of the difference。

 whether or not the absolute value of difference is bigger than 128。

And this is something that should always be done when putting text on a display。

 just to illustrate that， here's our standard colors。A few of our standard colors， so the red 76。

 blacks zero， whites 255 and blue is 52。And now if our font color is red。

 of course if it's red on red， you're not going to see anything， that's black on red。

 which has got a difference of 76 and it's legible but not great。

 this is white on red which is much more legible and the blue on red is much less。

Black well black on black isn't any good， but white on black is the highest difference that we can have。

 so that's quite legible in the blue on black， maybe not so legible。In white， again。

In most cases with the white background， we've got a pretty good difference。

 so that's just the indication， and it's a good rule of thumb and it's an example of application of computing with color。

So maybe blue， the only thing you can， if you have a blue background， you better use white text。

 so that's color combatibility using luminosity。Another application is converting colors to grayscale values。

 So it's a basic fact that I already mentioned when all three RG and B values are the same。

 the color is going to be gray。 it's going to be from0， which is black to 255 is white。

 there's 256 different levels。 and it'll be one of those。 So for a given value。

 what's the gray that should correspond to a given color。 And the answer is。

 you just use its luminance for all three values。So here's a static method that takes a color as argument and produces a color as return value。

 The return value color is going to be gray。 and you get that just by。

Computing the luminance of the color， given color as argument and change it to an in because it returns a double。

And then make a new color， which is the gray， which you get by creating a new color with all three values set to that luminous value and then return it。

So that's another method that we can add to our Luminance library that's useful。

 and here's the grays corresponding to the color examples that we've tried so far。

Another useful computation to be done with color。And we'll have applications in just a minute of that。

So the context in objector programming is was how does Java represent color it three values between 0 and 255 are they all packed into one big in value or the three separate invalue or chars or what and the answer is we don't know the representation is hidden it doesn't matter to us。

 it's an abstract data type system can choose to represent the color any way it wants as long as it provides the behavior that we expect through the operations that are defined for the data type。

So like here's an example， it could be that what we have is the。

The variables are the addresses of references to parts of memory that have the three values may be packed in bytes because they can be done in eight bits。

 so maybe gray references this memory word that has an address Y in it and Y is the address of our free values one after the other。

We don't have to worry about how to get to the values and so forth。 that's built into the data type。

 and maybe there's some other representation that might be used。

 particularly when data types become more complicated。

 we really want to be divorced from the actual representation。

That's the big benefit of using abstract data types。So when we're using objects。

We just want to remember that an object reference is like a variable name。

 it's not the value it refers to the value， so the values in the object that the variable name refers to and so we have just that one thing and we can pass it。

 return it from a method and so forth and when it's time to get to the values that's all that the system needs in order to get to the values。

 but that detail is something that we don't have to worry about in our code。

And the other important use of object references is to identify an object as the one that we want to perform an operation on with the dot operator。

 That's actually most often what we use it for。Just to think a little bit more about abstraction。

 we use this famous image from the Belgian artist Renee Maggrite。

 who put this painting and says in French， this is not a pipe。

So what it actually is is a picture of a painting of a pipe。

 or maybe he meant it was a painting of a pipe。But in the same way， we can say in Java。

 these are not colors， they're references to colors and they're not actually colors。

 it's an abstraction。So that's what lies at the basis of object oriented programming。

 it's a natural vehicle for studying abstract models of the real world and very。

 very often in programming， that's what we're doing is working with abstract models of the real world。

Just to finish with a joke， so that's Maggrite next to his brother。

 the serverless plumber that says that's not a pipe either。But actually it is。

 he's referring to an actual pipe， the joke could be a lot better if he were holding a picture of a pipe like that is not a pipe。

 that's a picture of a pipe， or you can't resist inserting a computer science joke。

 that pipe that we talked about， that's not a pipe eater。



![](img/1dc82d450c790645e43b57dc2b122ada_2.png)

So anyway， the whole idea of abstraction is something that's worth thinking about as we move on。



![](img/1dc82d450c790645e43b57dc2b122ada_4.png)