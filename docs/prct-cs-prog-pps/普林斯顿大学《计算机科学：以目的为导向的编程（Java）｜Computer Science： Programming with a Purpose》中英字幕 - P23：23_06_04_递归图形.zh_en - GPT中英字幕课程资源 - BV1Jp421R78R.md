# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P23：23_06_04_递归图形.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/fba38379bc47c06965de23089cc11353_0.png)

Well， we know recursion and we know graphics， so it makes sense to put them together and we'll have some fun and interesting applications。

recursive graphics are all over the place in art and literature and popular culture。

 you're familiar with the work of MC Escher， which involves recursion and that's a famous cocoa box there's well。

 I don't think that's Da Vinci's work or is that， and even the New York Times one time did a recursive headline of a newspaper that has a picture of itself on the cover。

So let's look at how to make images like this， we'll look at some similar simpler and more practical images。

 but let's see what we can do。So one of the simplest programs is actually very useful。

 it's called an H tree， so this is recursive graphics。

 what we're going to do is base our recursion on the image of an H centered。

And to get an H tree of order n， we're going to draw four H trees of order n -1。

 half the size centered at the tips of the H。 So our first one is just an H。 Our second one。

 we have a smaller H centered at each one of the tips。Third， again， four h's。

 half the size centered at each the tips， each of the tips。 So that's an H tree。So。

These are's some bigger ones，4 or5。6。So this actually has an important practical application。

 It's called what's called a space filling curve。 And you can imagine if you had a。

A source that you want to connect electrically to lots of sites like on an integrated circuit chip or wiring a city for cable TV。

 you want to use a structure like this that。Gives you a connection to everywhere in an organized fashion。

 And actually， people have studied many different types of space filling curves。

 This is just a first application。So what's the code to implement in H tree look like。

 how it almost writes itself， and you certainly could write this code。

The trickiest thing is to just figure out exactly how to draw the H。 So we we have to。

We're supposed to in the recursive call， make the new ones half the size。

 so we have to keep the track of the size as one of the parameters in the recursive function。

 and then X Y coordinates of where's the center of it。

So we're going to compute the kind of four corners of the H x0， y0， x1 y1。

 just by taking the XY coordinates and subtracting half the size。

So then we draw a line from x0 to x1 and Y。 that's the bridge of the H。 And then from。X0。

From y 0 to y1 at x0， that's one size， and from y 0 to y1 at x1， that's the other side。

 So that draws the H centered on x and Y。And then we're going to have four recursive calls at each of the four corners。

 x0 y0， x0 y1， x1， y0 and x1 y1， and those are all of size over 2。

And don't forget we need that termination condition if n equals zero return。

 so we're going to keep an integer argument that gives the size of the H tree Another thing we could do is just use the variable size and when the things get so small we could make that termination condition as well。

And then just take the H from the command line and draw the thing at the center。

 and that gives our H tree。And again， we not only have recursion in graphics。 We also have sound。

 so we might as well play a note and get a tune。🎼，🎼I。Oh。Oh。Oh。🎼Yeah。Oh。🎼，Yeah。

So that's recursive H tree implementation。Okay， here's a related thing that is useful as a model in all kinds of scientific situations。

 So this is a process that models in many different phenomenon。 the price of stocks。

 So you're familiar with stock curves。 And then there's the price of a couple of stocks。

That's an actual stock on the left， and the one on the right is a model that people with two different parameters that people think should represent something some model of the actual stock。

There's lots of other things， so this is a model that's supposed to look like a mountain and that's the actual shape of a mountain and this idea of fractal brownian motion is actually quite useful as producing simple models for all these different sorts of phenomenon and it's widely used in lots of scientific applications。

Turns out to be a recursive program， not too different from the ones we've been writing。

So it's called， let's look at the simulation of it， it's called the midpoint displacement method。

And so what we're going to do is we have a line segment that goes from two given points。We're going。

 if it's just short enough， we're just going to draw it in return。

 That's our base case for the recursion。Otherwise， we divide it in half and figure out the point at the middle。

 it's just x0 plus x1 over 2， y 0 plus y1 over 2。And then we're just going to pertuurrb that a little bit and so we're going to compute a number delta and it's going to be random。

 but we're going to use the Gaussian distribution and we talked about Gaussian distribution and center standard random module。

And so we'll just add that value delta to the middle point and could be plus or minus actually。

And then just recurse， draw two line segments and then call that recursively， that's the process。

And here's just the example of running this process a few times。

So let's look at what the code looks like。Again， it's a very simple recursive program。

 very similar to the other ones that we've done。If our。Points are close enough together。

 We just draw the line。 otherwise we compute the middle。啊。We compute this value delta。

 now there's a parameter in here that I'm not going to talk about in detail that。

Controls the Gaussian distribution and so it's called the heararst exponent and that's described in the book and on the book side of it what that actually does。

 but other than that complication， it's a recursive program with the same structure of the other ones that we've been doing divide the middle recurs on the two halves。

 so if you use this with a parameter one， it looks a little bit like the mountains and if you use it with a small parameter like 1/8 it looks a little bit like the stock price。

It's very surprising that such a simple process can model so many natural things。

There's a two dimensional version called plasma Clouds。

 and it's a similar idea just in two dimensions。We'll describe it in terms of pixels you could do it in terms of rectangles just like we did the lines。

 but it's a little simpler to think about in terms of pixels so that's what we're going to do in this lecture slide so if you've got a rectangle and you have pixels at the four corners and they have colors so again if it's small just return that's the base case but what you want to do is for each side you want to color the midpoints the average of the endpoint colors so that's between 0 and 20 you put 10 there this is with gray scale you can do it with colors as well。

20 to 100， you put 60 there， 60 to 100， you put 80 and 0 to 60， you put 30。

 so you can do that for each RGB value if it's in color。and then the last thing you do is again。

 choose a little delta from a Gaussian distribution so that it's not completely rigid。

 it's got a little bit of randomness in it， and what you're going to do is the center pixel of the rectangle。

 you're going to average the four colors， but add Dlta。So in this case。

 if you actually averaged the four colors it should be 45， but instead it's going to be 49。

And now you've got four rectangles。 And again， the book site code actually draws rectangles there rather than pixels。

 Now you've got four quadrants and you just recurse on the four quadrants。



![](img/fba38379bc47c06965de23089cc11353_2.png)

I'm not going to show the code for that it's very similar to the H3 code。

 a combination of the H3 code brown and the Brownian 1D Brownian model code。

 and what's amazing is the results that it gives。So again， recurse on the four quadrants。

 and then you get lots more colored dots until all the pixels are colored。

So that's the result of running that computation looks very much like a cloud。

 It's a model of something that we experience in the real world。

And you can argue about whether the real world operates in exactly the same way as the model or the model reflects reality in some way and this has very important practical uses。

 for example， here's a scene created giving different parameters and different colors and actually many of the scenes that you see nowadays in movies and video games are created in this way。

 it's an important application of a simple recursive process。



![](img/fba38379bc47c06965de23089cc11353_4.png)