# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P15：15_04_04_分形绘图.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/45bbc5b372ecdd721c77123173b24c41_0.png)

Now we're going to explore some programs that draw fractals really to illustrate how simple programs。

 not much more difficult than the ones that we just looked at can bring us into a whole new world of understanding of really nature。

 So let's look at these examples。 We're going to start out with a very simple application kind of a random game。

 So the idea is we have a triangle with the vertices labeled0，1 and 2。

And we're going to make zero the current point and that's got。Circle on it。

And then our process is going to be to pick a vertex at random。And draw。

A point halfway between that vertex and the current point。And then just repeat that。

So in this example we start at one， start at00 with vertex 0 and this is just a little rule about little table explaining the rules so with probably one third we're going to pick each one of the points as the next point and then these formulas give what we need to do if that happens to be the one picked so let's not worry about those so much let's just look at the process now so if we're at0 zero and we pick two then that points halfway between zero and2。

Now we pick one and then we move to a point halfway between0 and1。 and again。

 these little equations here give us what we need to do to update。So now two， halfway there，0。

Halfway there。 So for 0， it's easy。 if we're up here， then we just take half the x coordinate。

 half the y coordinate。 and the others， you just have to add a half or whatever else you need to do。

So we're just iterating this process looks pretty random。

But let's take a look at a program that implements this again， pretty easy to do。

 and then we can run it for a lot of points and see what happens。

So this is a program we'll call it chaos for now， seems random。

 we're going to take the number of points that we want to run from the command line。

 we call that trials the way that we usually do。And then we'll have these variables here help us do the computation。

 so we need the square root to3 over two in the same way and then these arrays give us the coordinates that we need in order to do the computation。

Those are the points of the triangle to get started。So we set the pen radius。

 it started zero and then。In a for loop that iterates the number of times given by trials which we found in the command line。

 we're going to compute a random integer 0，1 or2， and then we're going to just update the X and Y coordinates to go halfway between the current point and the point given by the arrayse。

And then once we get the updated X and Y， we'll just plot it。So again。

 that's a very simple program easily implemented with standard draw。

 so let's take a look at how we get random points now within our triangle so this is plotting 10。

000 points with that program。Actually not random at all。

 doesn't take much for an amazing and interesting pattern to emerge。But looks random。

 so what's going on and this is introduction to the idea of fractals and computing with chaos that scientists are still studying from all kinds of points of view yet today。

Maybe you've seen this pattern before， it's called the Sirpinsky Triangle and there's many。

 many different ways to look at it or see it even in nature。 one thing that you can do is，You can。

 if you just take the Pascals triangle and you take the odd odd numbers， you get that pattern。

 Maybe you've seen it in popular culture。 You can build it with Coke cans or with pennies or where you can make a cookie or candy corn。

 all of these different realizations of this thing。

 And there's many applications in math and applied math as well。

 That's a three dimensionmensal version in high def。So with a simple random chaos program。

 we can get Spininsky triangles。That's interesting， but if we change the rules。

 we can get even more interesting in patterns， so you know with the Sinsky triangle our rules with probably one third。

 we choose each point so we can adjust those probabilities。And for the Speni triangle。

 we always took the average of the current point and the next point to get halfway between。

 but you can use any function that you want of the current point。

 so this is just a different example。So what happens if we write a program to change our rules to that it's not much or very little。

 much more difficult than the program that we just wrote and there's the program in the book around the book site that takes the coefficients from standard input and then runs the iteration but otherwise it's the same program that we just looked at。

 it's just that it takes its data usually from a file so here's an example of a file that's got the coefficients of how we're going to do the iteration。

 how to update that's just really encoding those tables in numbers and you can study that program in the book。

For lecture， the idea is a simple program where we play that game where we start at a point and we go randomly to another point it's just that the transformation is dictated by a file so here's a file it's a little bit more complicated but not hugely more complicated and that's still only three points and so forth and let's run this one。

This is a completely different random pattern， still from a pretty simple program， and in this case。

 you all you can tell from the name， it's an idea for modeling the behavior of coral in nature。

So there's something about this random process that seems to relate to what happens in the real world and actually scientists are interested in knowing simple rules that might govern what we observe in the real world and with this type of program。

 we can study that。Here's another example of changing the rules。

This time there's four points is one of them that's got a tiny probability。

 one of them that's really likely， let's run that one。Again。

 it's pretty much the same program we're just giving it slightly different data。

You'd like to think that nature kind of works that way， and many people do。

 There's a relatively small number of simple rules that have created the world around us。

So this one is creating something that looks a little bit like a fern。

 This one's called a Barnesley fern。So actually， not just scientists。

 but also people in the entertainment industry use processes like this to build models of nature。

So they can make worlds and you experience this all the time in a video game or a movie nowadays。

 it's often the case that what you see is produced by a process like this。

With simple iterative computations， we get patterns that are extremely similar to those that we find in the natural world。

So there's a fern just like the one that I just did except green， and there's a real fern。

 I can compare those。Is that real or is that generated， That one's actually real。 This one is。

 that's a real plant。 and that one's generated by an iterated function system。

And it really brings up the question， you know what does computation tell us about nature or what does nature tell us about computation really profound questions that we get to with relatively simple programs using standard output and using a little bit of randomness I'll make this point often throughout this course in the 20th century science was all about math models and formulas。

A lot of people believe in the 21st century， science is really all about algorithms and programs to help us understand what's going on in the real world。



![](img/45bbc5b372ecdd721c77123173b24c41_2.png)

Now again， you've seen really lots of applications of iterated function systems in movies and games。

 maybe you remember this one， that's an entire world， none of that's real。

 it's all built with technology like the iterated function systems that we just demonstrated。



![](img/45bbc5b372ecdd721c77123173b24c41_4.png)