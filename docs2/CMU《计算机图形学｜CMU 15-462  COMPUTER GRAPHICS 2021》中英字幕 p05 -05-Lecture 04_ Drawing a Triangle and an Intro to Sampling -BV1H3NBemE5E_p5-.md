# CMU《计算机图形学｜CMU 15-462  COMPUTER GRAPHICS 2021》中英字幕 p05 -05-Lecture 04_ Drawing a Triangle and an Intro to Sampling -BV1H3NBemE5E_p5-

Welcome back to computer graphics so today we're going to talk about a seemingly basic task。

 how do we draw a triangle on the screen， but actually this problem is going to expose a lot of the deeper challenges of computer graphics so over the next few lectures we're going to talk about the process of rasterization。

 which is one of the two major techniques in computer graphics for getting stuff on the screen。

So the first one which we'll talk about today is rasterization。

 and it basically says for each primitive we want to draw each triangle or line segment or point。

 which pixels of the image should get lit up？This technique is extremely popular。

 extremely valuable because it can be made extremely fast。

 we can get billions of triangles on the screen every second if we're using modern graphics hardware。

On the other hand， raization has a significant shortcoming， it's very。

 very hard with raization to generate photorealistic images。

 things with beautiful shadows and reflections and all the kinds of lighting effects that we'd expect to see in a real image。

 so that makes raization a really good match for things like 2D vector art， cartoon images， fonts。

 doing quick 3D previews of a scene。But it doesn't take us all the way there。

 so later on in the class we're going to talk about the second technique of ray tracing or doing photorealistic rendering based on tracing rays and the atomic operation there is to ask well for each pixel。

 which primitives， again， which triangles or other shapes are seen through that pixel？

And as we'll see， this approach makes it a lot easier to generate photoreistic images。

On the other hand， ray tracing is a lot slower。 We might have to wait minutes or even hours to generate one image rather than drawing。

Billions of triangles per second or having hundreds of frames per second on the GPU Okay。

 so we'll get deeper into ray tracing later on in the semester。

Today I want to talk about the restization pipeline so we can talk about image generation and graphics in terms of a pipeline。

So what is a pipeline， this is an idea that shows up all over computer science。

 you see this in processor design and compilers and so forth。

And the basic idea is to structure your computation as a series of stages。

Each one of these stages is going to request。Data as input in a very structured way。

Some really simple regular description of the input data。And likewise。

 it's going to have some simple regular structure for the output data。

And because this data is highly structured and highly predictable。

 you can really go to town and simplify and optimize the computation within that stage so that's the kind of structure we want to have for image generation algorithms。

To do this， we need to understand a few things we need to understand， for instance。

 what are the inputs to the pipeline。What image do we want to draw？

What kind of data describes the three dimensional scene that we're interested in？

We need to choose a decomposition of our computation into a series of stages。

 We need to think about how can we transform the original input into some intermediate output that becomes the input to another stage。

 which becomes the intermediate output for another stage and so on until we get as output。

The final image。Maybe the final。Aray of pixel values that gives us the picture of our scene。

And in fact， we've already seen one example in this class of a graphics pipeline。

 it's what we did in our very first lecture。So there we said we want to draw a picture of a cube。

We have a cube in three dimensions and we want to make a very simple perspective drawing of the cube。

We cooked up an input representation so we said we could represent the cube or any other kind of three dimensional shape as two things。

 a collection of vertices， vertex locations in space。

 and a collection of edges saying which of those vertices get connected together and to make line segments？

We then fed that data into the first stage， the perspective projection stage。

 which mapped the three dimensional vertices onto two dimensional locations in the image plane。

And we did that in a way that captured the notion of perspective of things getting smaller as they go off into the distance。

That data then was fed into our line drawing stage。

 so we knew where the points were on the plane and so we could just connect them by a line segment。

And the output of that final stage was our final image， our drawing of the cube。Okay。

 so obviously this pipeline is a bit simple， it's a little bit of a toy graphics pipeline。

 so what we want to build up is the restization pipeline。

 modern image generation is based on this technique of raization and the basic input to our pipeline instead of points and edges is essentially just going to be points and triangles。

Everything we ever want to draw actually is going to be just points and triangles。

 but possibly with additional attributes， so instead of just knowing the locations of vertices in space。

 we might have additional data like we might know the color of each vertex。

 or we might have something called a texture coordinate， which we'll talk about a lot later。

We then feed this data into the rasterization pipeline， this kind of black box。

 and the final output is a bitmap image， it's an array of pixel values which store one color per pixel possibly again with some additional attributes like depth。

 so how far into the screen is that pixel and alpha， how transparent is that pixel。

So our goal is going to be to build up the stages in between。

 how do we go from that very basic input into this beautiful image that you see on the far right？

And one thing to note actually is that although we'll describe this at the level of software and algorithms。

 real rasterization is typically performed by what's called a graphics processing unit or a GPU。

So this is a real physical piece of hardware that sits inside your computer。

 and it has a chip on it that's different from your CPU。

 your central processing unit that's highly specialized to actually just implement the restization pipeline。

Okay that's part of the reason why raization is such a fast technique because we're able to boil down all the computation we want to do into several simplified stages。

We can really go to town and optimize the heck out of this process， not only in terms of algorithms。

 but in terms of actually designing hardware that executes each of these stages。Okay。

So one really important question to ask is why triangles？

People thought about the design of the graphics pipeline for many。

 many years and somehow they decided that the basic atomic primitive that should get sent down the graphics pipeline。

Is a sequence of triangles。 Why does that make sense， right？So for instance。

 if we're trying to draw this skull， this Ram skull。

 we're actually going to be drawing a big jumble of triangles that you see in this zoom in。In fact。

 even if we draw things as simple as points and lines。Those are actually， it's kind of weird。

 those are actually going to be drawn as really， really small， really， really skinny triangles。

That' split up a square or a quadrilateral or something。 Why do we do that？

 That seems like kind of a funny choice。 Well， actually， there's some really。

 really good reasons to use triangles for rasterization。

 One is that they're pretty good at approximating any shape you can think of。

 So we've already seen here。 we have this very， very complicated model of a skull with all sorts of interesting details。

 and if you have enough triangles， then there's no problem representing that complicated shape。

So you can kind of think of this in analogy to images right， what is the atomic unit of an image。

 it's a pixel I have this little block of color， why well， if I have a little block of color。

 if I have a huge number of them， I can draw pretty much whatever image I want。

Another thing that's good about triangles is that they're always planar。

 they always have a well defined plane passing through the three vertices。That's not true。

 by the way， for other polygons， I could take four points in space。Defining a quadrilateral。

 and they may not sit in a common plane。Who cares about this property of sitting in a plane。

 Actually， it's extremely important for shading。 So if I want to shade a surface。

 I often need to know what is the normal direction， What is the direction orthogonal to the surface。

 And so for a triangle， that normal is always well defined。

 It's the normal of the plane containing the three vertices。Okay。

 so that sounds like a pretty good reason。It'll also turn out to be very easy to interpolate data at corners。

 so if I have three color values at the corners of a triangle and I want to smoothly blend those color values across the rest of the triangle。

 it's going to be really， really simple and efficient to do that using something called berycentric coordinates which will show up over and over again throughout our course。

So。Really， the key reason why triangles are used in the graphics pipeline is once we've reduced everything to triangles once we've。

Expressed how all different kinds of shapes and lines and points can be。Drawn using triangles。

 then all we have to do is focus on making a really， really well optimized pipeline for。

Triangle drawing。Right， so you could really think of the。

Raststerization pipeline or the graphics pipeline as kind of the triangle pipeline。

It's this super optimized machine that does one thing really， really well。

 And that one thing is drawing fancy triangles。And we'll see that you can actually draw some really fantastic images just with that one basic primitive。

Just like you can draw some really beautiful images with pixels。Okay。So。

What does the raization pipeline actually look like here's a rough sketch and we're going to walk through each of these stages in great detail over the next few lectures。

 but to just give the high level view，The first thing we're going to do once we have our list of triangles is we're going to transform and position these things in the world。

 in the scene where we want them to be。We have a person standing inside a house and that house is sitting on top of a planet。

 we have to arrange all of those in the way that we want them to be arranged in our scene。

We're then going to project those objects onto the two dimensional screen。

 This is just like we did with our cube， right we turned our three dimensional coordinates into two dimensional coordinates that we can draw。

For each triangle we're then going to sample the triangle coverage。

 we're going to see which pixels of the screen are covered by that triangle。

 that's what we'll talk a lot about today。Once we've done that。

 we can interpolate attributes at vertices across the triangle， so here I'm smearing the colors red。

 green and blue， across the middle of the triangle to give it some nice shading。I might also。

 in addition， sample images onto the triangle。To give it some texture。

 a lot of other things we could do at this stage。 and finally combine the。

Colors of each pixel of each triangle into the final image so we're going to composite all of those triangles into our output。

 which might also have things like the depth and the transparency。

And this is a pretty good cartoon of real world graphics pipelines。

So if you ever interact with something like OpenGL or Direct 3D or Vulcan。These are all effectively。

Application programming interfaces， ways of。Communicating with different stages of the graphics pipeline。

Okay。By the way， we're not going to discuss in detail how these different APIs work。 It's not really。

Core to the topic of computer graphics。These APIs are just really wrappers around the core algorithms。

 and so we will talk about this in recitation but it won't be a big part of our lectures。Okay。

 so let's go ahead and try to draw some triangles on the screen and to do this we have to answer a couple questions。

Is for a given triangle for this red triangle here， what pixels does the triangle overlap。

 That's the basic question of rasterization， the question of coverage。Another important question is。

 well， okay， we know that the red triangle covers this pixel， we might know that another triangle。

 the blue triangle covers this pixel。Which one is closer to the camera。

 Which color value do we finally see， And that's the question of occlusion。



![](img/c8e348c9c6db8df291d173884772d863_1.png)

Okay。So。This second question， this question is called the visibility problem。

 and we can think about this actually in terms of the pinhole camera model that we saw in our first lecture。

So if you remember we have this idea that we have a camera that's made of a box with a little tiny hole in it and a piece of film sitting on the back of the box。

 and light comes in through this hole and it hits some point on the back of the box and makes a mark on the film。

Actually， often in graphics， just because this pinhole picture is a little confusing。

 we flip things around and we just imagine there's a virtual sensor sitting the same distance from the pinhole。

 but in the opposite direction， that's our image。Right， and we're kind of asking。Well。

 what do we see as we peer out from the pinhole through each of those pixels。

We can also think of this question in terms of rays and ray tracing。And so if I。

Imagine shooting array from the pinhole out into the scene through one of the pixels。

What scene geometry is hit。What is the list of triangles that I hit？

That's going to give me coverage information。Which triangles cover this pixel？

The other question I could ask then is， well， okay， the ray might hit a lot of different triangles。

 which one is hit first？That's the question of occlusion。Okay。

 hopefully those two concepts are clear。So。The problem of triangle coverage is what we'll focus mostly on today。

 and again， what we want to know is for a given triangle， which pixels does the triangle overlap？

So the input to this stage of the pipeline would be the projected two dimensional positions of our triangle vertices。

We could call those P0 P1 P2。The output of this stage should be for each pixel in the grid。

 We just want a binary value。 We want to know， was this pixel covered by the triangle or not。

So maybe something like this blocky triangle that we see on the right。

To actually implement this stage of the pipeline， we need to understand a basic question which is what does it mean for a pixel to be covered by a triangle？

So if we really， really zoom in here， we just look at one big pixel in the middle。

We could ask which of these triangles cover the pixel and what do you think。

 so we have triangles  one， two， three， four。Which of these triangles would you say cover the pixel？

Okay， I mean， some of these， it's pretty clear， right。

 Triangle number one doesn't intersect the pixel at all。

 So it seems really weird to think that that triangle covers the pixel， definitely not。

Triranangle 4 is also pretty easy，4 covers the entire pixel， so it's really easy to say， yeah。

 for sure， the pixels covered by Triangle 4。What about triangles2 and three？Do they cover the pixel？

What is the binary value that we'd output for those triangles， do they or don't they cover the pixel？

And maybe what this tells us is， yeah， maybe we need to refine a little bit our description of the output。



![](img/c8e348c9c6db8df291d173884772d863_3.png)

So instead of just recording a binary value， yes or no， maybe one option is to say。

 really what we want to know is the fraction of the pixel area covered by the triangle。

That seems like useful data， if we know what fraction of each pixel is covered by the triangle。

 then we can adjust the brightness of that pixel according to this fraction。

So if a triangle covers 10% of a pixel， it should be 10% red， if it covers 60%。

 it should be 60% red and so on。

![](img/c8e348c9c6db8df291d173884772d863_5.png)

This question of coverage is not always so easy to figure out。

 it gets really tricky when we start considering multiple triangles in the scene and we have occlusion。

Right， so what if we have two different triangles covering the same pixel， well。

 maybe it's not so hard like in the upper left， we might just say， okay well。

Pixels covered 50% by triangle 1， 50% by triangle2。But actually determining this coverage。

 actually computing this coverage can be really hard in general。

So let's say we have two triangles interpenetrating each other。

How do we actually figure out this fraction？How do we determine what fraction of that pixel is covered by two versus 1？

We might have non convex regions where they overlap and so forth。So。

Rather than trying to answer this question exactly， right。

 rather than trying to figure out exactly what percent of the pixel is covered by triangle 2 and exactly what percent is covered by triangle 1。

What else might we try， What's a way we can get a rough idea。Of how much of the pixel is covered。

What do you think。So our basic strategy。Is to acknowledge that real scenes are very。

 very complicated， as we've just seen， we can have occlusion。

We can make it hard to figure out these exact fractions。We can have transparency。

 so if these are both semi transparent triangles， what do we mean by covered？

And we'll talk a lot about these different complexities in the future but。

The main point is that covering the exact fraction of coverage is really not practical。So instead。

 what we're going to do is view this problem of determining coverage as a sampling problem。

What I mean by that is， okay， we're not going to compute the exact or analytical answer。

 but instead we're going to test a collection of sample points。

And we're just going to say for each sample point。Which triangle do we see？

If we have enough points and if we are smart about where we put these points。

 then we can start to get a pretty good estimate of coverage。Okay。

 so before really drilling down and answering this question for triangles。

 let's talk a little bit about sampling in general。

And usually a good place to start is in one dimension， so in one dimension。

 I can think of a signal as just a function， I have a function F of a variable x。

Sampling all that means is I pick some values x， x1， x2， x3， and so on。

 and I ask what is the value of the function at those points？So F of x not f of x1。

 f of x2 are samples of the continuous function f of x。

A great example of this would be an audio file。So an audio file。

That you use to listen to music stores samples of a one dimensional signal。 What is that signal。

 It's the amplitude， It's the amplitude at which you drive the speaker cone。

 So over time that speaker is going to be moving in and out at a certain amplitude and you want to know that for lots and lots and lots of points in time。

So in fact， most consumer audio is sampled 44，000 times a second to get a realistic reproduction of sounds or something like this。

Okay and what the picture that you see here is actually the sampling of that sound。

 it's the amplitude as a function of time。So once you have that data。

 once you've brought that information into the computer and recorded it as a sequence of numbers。

You have kind of the inverse problem， how do you turn those numbers back into a continuous signal that you can listen to？

And that's the problem of reconstruction。RightSo given a set of samples， how can we cook up some？

Continuous function， some function where we know the value at every point in time， rather than just。

At the sample times。What do you think So if I have just these values F of x not through F of x4。

How do I make a。Continuous function that roughly looks like these sample points。Okay， well。

 one really basic idea would be to use a piecewise constant approximation。

I don't know what the function is equal to for every value of x。So what I'm going to do is just say。

 okay， find the closest value of x where I do know the function value and just use that one。

And that gives me my approximate function， which I've called F hat of x here。

How could I do a little bit better？ This looks like kind of a jagged approximation。

 How could I just do slightly better in。Approximating or reconstructing this function。Okay。

So one thing I could do is I could then connect the sample points by rather than these constant plateaus。

 I could draw straight line segments between them， so I could do what's called a piecewise linear approximation。

Okay， now this looks smoother， but you notice something funny about it。 What's。

 what's strange about this。Approxiation of my original function。

There's something really kind of bad that happened here。

 which is that I've completely missed some of these big bumps in the function。

 especially near the end。 I have these two huge bumps between x2 and x3 that don't show up at all in my piecewise linear approximation。

So。What would you do， how can we represent the signal more accurately？What's a better idea。Okay。

 well， the most basic thing we could do is we could just say。

 how about we sample this signal more densely， How about we just。

Take more sample points if we missed certain features。Then， we should just。

Sample more frequently and we'll capture those features， right？So we can increase the sampling rate。

 this is why your audio is recorded at 44，000 times per second。

 is to make sure you don't miss anything important about the way that the music sounds。

And so now we could go ahead and we could reconstruct this from。Peace was linear。Approxiation， right。

 and we do capture those bumps this time around or we could use Pwise linear approximation again。

 we capture the bumps， the function is a little smoother。So that's the basic technique if you have。

Under sampling， if you have too few samples you miss out on features。

 how do you get them back in there， hey， take more samples。



![](img/c8e348c9c6db8df291d173884772d863_7.png)

Okay， and this is true not only for one dimensional signals。

 but this is going to be true for any other kind of signal we want to sample。 So for images。

 it's a similar story。 Sample values are going to measure image， intensity or image color。At each。

 let's say center of a pixel。To then take those values stored at the centers of the pixel and reconstruct an image over the entire image plane。

 we're going to apply some kind of interpolation or reconstruction filter。

 so we could again do piecewise constant。 We could go to the nearest pixel center and use that color。

Or we could do something like linear interpolation。

 we could use a linear function in each direction and get what's called biline。Interpolation。



![](img/c8e348c9c6db8df291d173884772d863_9.png)

Okay，So just a quick summary of the basic concepts of sampling。

 sampling is basically just the process of measuring a signal。

And distilling it down into a discrete or finite set of samples。And in principle。

 the idea is that these sample values represent the。True， continuous function at certain points。

 although the reality is any real measurement device doesn't quite give you that。

 It's really hard to get just the value of a continuous signal at a single point。Usually。

 there's some kind of。Burrrring out of the signal。Reconstruction is the opposite process。

We have this finite set of samples， we have numbers sitting on our computer。

 and we want to construct a function。That interpolates between these values to create a continuous signal。

OkaySo we saw Pwise constant or Pwise linear reconstruction， but there are many。

 many more possibilities， and especially as we start to look at more sophisticated kinds of signals that show up in computer graphics。

 so going from audio to images to three dimensional surfaces。

 the questions about sampling and reconstruction get harder and also a lot more interesting。

So let's try to tie this back to our main problem of rasterization for rasterization。

 what function are we sampling， How do we think of rasterization as a sampling problem？



![](img/c8e348c9c6db8df291d173884772d863_11.png)

Well。We can imagine that what we're trying to do is actually sample。The coverage function。

So the coverage function is a function defined at every single point in the entire plane。

 not just at pixel centers， but really everywhere in the plane。

And it's equal to1 if that point is contained inside the triangle and it's equal to zero otherwise。

Okay。And the goal of rasterization or the simple approach to rasterization is to say we want to sample the coverage function。



![](img/c8e348c9c6db8df291d173884772d863_13.png)

On to our P grid。So I have some sample point X Y。And maybe I put it halfway in the middle of the pixel。

And for each triangle， I'm just going to evaluate the coverage function for that triangle at the sample point。

Now， even this basic sampling process can be tricky。When we come back to this example。

 I have two triangles。Meeting at an edge and that edge passes exactly through my sample point。

So what do I do is？Is this sample point covered by triangle 1 or is it covered by triangle 2。

 or is it in some sense covered by both of them？You know。

 it seems like a little bit of a pedantic problem， but actually if you get this wrong in real image generation。

You can get some really nasty looking artifacts in your image。 Things don't look quite right。

And so people have thought long and hard about， you know what is what is a good way to break ties when it comes to drawing triangles。

 So if an edge falls directly on a screen sample point。For instance。

 you could say the sample is classified within the triangle if the edge is a top edge or a left edge。

 So top edge， meaning a horizontal edge that's above all other edges。

 a left edge is an edge that's not exactly horizontal is on the left side of the triangle。Okay。

The details here are not super important if you're really interested。

 you can go look it up in the reference at the bottom。

 but just knowing that when you go to write real code， when you go to develop real algorithms。

 you want to have crystal clear definitions of the behavior。

 you really want to understand ahead of time how should this work and not just kind of leave this up to。

 well， whatever falls out of the implementation is what happens because you really want to be able to guarantee that one stage of the pipeline。

Produces output that the next stage of the pipeline can rely on。Okay。So。

What does it look like once we've， once we've sampled triangle coverage， So let's again。

 zoom in on our pixel grid。 we've got this red triangle。

 and we've sampled its coverage function onto each pixel center。

And so now some of these centers are turned on， they're colored red， some of them are turned off。

 they're colored white。And actually， all I'm left with。

 if I think what data have I actually really recorded， I've just recorded this data。

I just have this grid of pixel centers， and I have a one or a0 at each center。Okay。

So how do I now go in the opposite direction， I have my sample data。

 and I want to turn it into an image。 I want to。Reconstruct it so that I can look at this approximate signal。

And that's really what your display is doing， that's what your monitor is doing。

So each image sample sent to the display is converted into roughly speaking a little square of light。

 and maybe you get to specify the color of that light。In other words。

 each little sample value gets displayed by turning on a pixel， by the way。

 the word pixel is just an abbreviation for picture element。You have a picture。

 it's your entire screen， one little element of that is a pixel。And。If you really。

 really zoom in on your screen。What you'll discover is that pixels don't look quite as simple as you'd think。

 They don't just look like constant blocks of color。 You can see that there's kind of a blurring。

 for some reason on the left， it looks a little bluer on the right， it looks a little redder。 right。

 There's all sorts of interesting stuff going on with real pixels。But for now。

 for the purpose of thinking about sampling and reconstruction and in restization。

 it's helpful to just think of each pixel as being a solid color。 And for the most part。

 that's a good enough model for。How these sample values will get reconstructed。So for instance。

 if we send the display the sample values， then we look at the screen。

 we'll get something that looks roughly like this。

![](img/c8e348c9c6db8df291d173884772d863_15.png)

Okay。So there you go， we sampled our triangle。We reconstructed it by turning each sample into a little square of light。

But are we happy with what happened？Sure， we get some image。 but the。

 the thing that we really were trying to。Draw trying to reconstruct is this signal。Right。

 so there's definitely some approximation error between our。

Reconstructed signal and our original signal。So this leads us into a discussion of something that's really core to computer graphics。

 which is the phenomenon of aliasing and we'll talk a lot about aliasing throughout the semester。



![](img/c8e348c9c6db8df291d173884772d863_17.png)

In every possible context， not just in rasterization， but also in geometry。

 in photorealistic rendering and animation and so forth。So to understand aliasing。

 let's take another look at this idea of sampling and reconstruction。Okay。

 we have a pretty good handle on this。 now。 The idea is we start out and there's some continuous signal that exists。

 let's say in the real world， like an audio signal， the voice。On this recording。

To turn it into a digital format， to turn it into something that we can store on our computer that we can send over the internet。

 we sample this continuous signal into a list of values， maybe just a long list of numbers， 44。

000 numbers per second。That's all we have after we've done sampling just these numbers。

And then we have to go through if we want to listen to the audio some process of reconstruction。

 we need to turn that list of numbers back into a continuous signal。And the goal。

In this whole process is to reproduce the original signal as accurately as possible here。

 for instance， you can see we didn't do a great job， right。

 There's lots of little wiggles in the original signal that are not present in the reconstructed signal。

So how can we talk about this kind of error？This sampling and reconstruction error in a little more sophisticated way。

Well， one really， really important perspective when it comes to signals of any kind is that they can be decomposed into frequencies。

So a 1D signal like audio can be expressed as a superposition or a sum of different frequencies。

A frequency here just means an oscillating sine wave that has a certain。Well， frequency so the。

Oscillating sine wave at the top goes very slowly and might represent a very low pitched sound。

The next one is oscillating a little more quickly and might be a medium pitch sound and then the next one goes even faster and might give you a really high pitch sound right。

 and if we add these all together， then we start to make different kinds of sounds。



![](img/c8e348c9c6db8df291d173884772d863_19.png)

Voice， music， and so forth。This might explain if you've ever seen on a stereo， a spectrum analyzer。

 something like this， so as the music is playing， these little bars are moving up and down。

 what does that mean while it's telling you how much low frequency stuff is there。

 so if there's a lot of bass you might see a bunch of bars on the left moving up and down if there's a lot of really high frequency sound somebody's playing the trumpet or something you might see bars going up and down on the right side。

Okay， so this is a good way of thinking about our signal as being made up of low frequencies。

 medium frequencies， high frequencies， and so on。

![](img/c8e348c9c6db8df291d173884772d863_21.png)

In audio， again， we can get a constant tone by playing a sinusoid of frequency Oomega。

 So if Oomega is something like。4000， we get a sound like that if it's。5000。

 we get a sound like that。 And if it's。6000， we get a sound like that。Okay。

 so here's a really interesting question。What do you think is going to happen if we increase the frequency omega over time？

So rather than a making omega just this constant number 4000， 5，000 or 6，000。

What happens if it changes if it increases over time， so if we say omega as a function of time T is。

 let's say 6，000 times t？What would you think that should sound like。Okay。

 my guess is that it would sound like a rising pitch。Right， it would start out low。

 And then as time goes on， it'll get higher and higher and higher。 just like we see in this plot。

So let's try it out。 Let's play the sound。Sine omega T？H。OhYeah。H。Oh。Okay， that was weird。

 why did that happen， that's not at all。What we thought it would sound like right。

 rather than just going from low to high and higher and higher and higher， it went from low to high。

 back down to low， back up to high， back down to low。What is going on there？Well。

 the important thing to remember is that we're always taking whatever this signal is。

 this quickly oscillating sine wave， and we're sampling it on a finite set of points。

And if we under sample， if we have two few points to capture。

All of the little wiggles in that sound wave。 Then we're going to get aliasing。 We're going to get a。

Sound that doesn't actually represent the original continuous signal。

So we could think about this by thinking about sampling each of these individual tones onto a finite set of samples。

If we have this really low frequency tone at the top， everything's fine。

 I can sample these black dots。 I connect them by straight lines。

 and I get this dashed blue curve that looks pretty much like F1 of x and's a little different。

 but more or less the same。But now let's go all the way to the bottom。

If we sample the function F5 of x onto the same set of sample points。What happens。Well。

 here we got really， really unlucky。Right， these sample points show up at just the wrong location so that when we now connect them by straight lines。

 it looks like we have。A sound that's much lower frequency than the one we are actually listening to。

And so in this case， this is what we mean by aliasing。High frequencies in the original signal。

 quickly oscillating waves masquerade as low frequencies after we perform the reconstruction because we've undersampled。

And that's exactly what happened with the sound we played on the previous slide。At some point。

 the frequency got so high。That we sampled it onto something that sounded much lower。

And just because of the particular way that function looked。

 it ended up sounding like it went up and down and up and down rather than just going straight up。

Okay。So this is really important。Picture to think about decomposing signals into frequencies so that we can think about things like aliasing。

How do we think about frequencies for images， actually images can be decomposed into frequencies。



![](img/c8e348c9c6db8df291d173884772d863_23.png)

But it's a lot。Trickier to think about。Okay， so what I'm showing here on the left is the input image you could think of this as a continuous signal。

And what I'm showing on the right is something like the analyzer that you look at on your stereo。

 Remember that on the stereo， if we look all the way on the left， we're looking at low frequencies。

 the bass and the music， if we look all the way on the right， you're seeing high frequencies。

 the treble。So this image that we see on the right is kind of like the analyzer。

 the spectral analyzer for the image that we see on the left。

 except this time all the low frequencies are dead center。And as we go out in any direction， up down。

 left， right or even off in some diagonal direction。We're looking at higher and higher frequencies。

So bright values here means we have a lot of amplitude in that frequency。

 and dark values mean we have almost no amplitude in that frequency。Okay。

There's still some things that are mysterious about this figure。 Why are there two directions。

 What do frequencies mean in images， And I think it helps mostly to to just start looking at some examples。

 So let's say we take this image。And we actually cut off all of the frequencies。

 except for the ones in the very middle。So we keep what I would call the low frequencies。

And what you notice is that the image got really， really blurred out。 all the sharp features。

 all the high frequency detail， all the little， you know。

 interesting things have been removed and were just left with this， this blur。 In fact。

 you can imagine that if you just。Took one row of the image and plotted it as a one dimensional function。

 what you would see is a nice gently oscillating wave rather than a rapidly oscillating high frequency wave。

Okay。Let's go out a little bit further and look at some mid range frequencies。

 so we're going to ignore these low frequencies， we're going to keep things that are slightly higher in frequency。



![](img/c8e348c9c6db8df291d173884772d863_25.png)

And we start to see things that actually look a bit like edges in the image。

 but kind of blurred out versions of the edges。If we go even higher frequency。

 we definitely start to see the edges and if we go super high frequency， that's kind of all we see。

 just the edges， the place where you see the silhouette of objects in the image。



![](img/c8e348c9c6db8df291d173884772d863_27.png)

Okay。So interestingly enough， we can decompose an image into these different frequency components。

 just like we can decompose audio into different frequency components。

And that starts to help us understand， you know， what do we mean by aliasing， well。

 the same kind of thing if we have。Really， really high frequencies in the image。

 but if we have a really coarse pixel grid， we might miss out on some things。

 we might not faithfully capture the original signal。

Here's an extreme synthetic example of that that phenomenon。

 So what we're going to do is we're going to。

![](img/c8e348c9c6db8df291d173884772d863_29.png)

Build a function intentionally that has crazy high frequencies in it。

And that function is sine of x squared plus y squared。

 where xy equals 00 is on the far left middle of the image。Okay。

 so how does this function behave well as we depart from the origin？

It starts oscillating faster and faster and faster and faster。

 right so you'd think these wiggles or these rings should be getting thinner and thinner and thinner and thinner as we go away from the origin。

But what do you notice， you notice， for instance， all the way on the far right。

 it looks like we again have these low frequency rings。Why is that happening？Well。

 it's not happening because they're really there。ItIt's a complete fiction。

The reason we perceive these rings on the far right is because we've gone so far past what we can represent on the image。

That we just have。Sampling and reconstruction artifacts。

 we have aliasing that makes it look like we have features that aren't really there in the middle also we just have no idea what's going on right there's so high frequency we just can't resolve with our few pixels in this image what's really going on with this function。



![](img/c8e348c9c6db8df291d173884772d863_31.png)

The same phenomenon shows up in video， this one might be more familiar to。

 so if it's ever been nighttime， you're looking out the car window at a car next to you and you stare at the hub caps。

You'll see an effect like this， so maybe as the car leaves through the stoplight。

The wheels start spinning faster and faster。 and rather than looking like they're spinning forward。

 they start spinning backward， but then as they go even faster。

 they start looking like they're spinning forward again。 and perhaps if they get fast enough。

 I don't know if we'll see it here， but they'll maybe start looking like they're spinning backwards again。

Right。Why is that happening well， in this case， because our video is only being taken at 30 frames per second？

So if the wheel is spinning around much faster than that rate。

 we're just going to catch kind of a random image of the wheel at different moments in time。

 which makes it look like it's doing all sorts of other funny stuff。

 this is exactly what happened with our our audio signal。Okay。

 so how can we be precise about when this phenomenon occurs。

This is something called the Nquist Shannon theorem。Really important theorem in signal processing。

 so it says， let's say that we have a band limited signal。

 meaning we don't have any frequencies above some threshold if we think of audio as a sum of fundamental sine waves。

 we stop adding terms that are past some frequency。So for instance， in our audio。

 if we band limited that sound or that music we listened to before， it might sound like this。

If we band limit our image， it looks like a blurry image we saw that before。

And what the Nquihannnon theorem says is， well， if。Your signal happens to be band limited。

Then it can be perfectly reconstructed as long as you take samples at a rate that's twice as frequent as the highest frequency in the signal。

And once you have those samples。You can reconstruct exactly the original signal by using something called a sync filter。

 so rather than piecewise constant or piecewise linear。

 what you do is for each audio sample or for each pixel in the image。

 you add up one of these oscillating sync filters where the amplitude is determined by the sample value。

Okay so this is an ideal filter， it doesn't get rid of any frequencies and it also has this property that has infinite extent。

 so the sync filter is1 over pi x times sine pi of x。

 which just means it's this oscillation that goes on forever and just gradually falls off。Okay。

So that's cool， I mean， there's this theoretical way in which you can get perfect reconstruction。

But there's a couple of problems with this。 I mean。

 one is that real signals that we want to deal with in computer graphics usually aren't band limited。

You know why， why is that true， I mean， first of all。

 we could just have a lot of high frequency stuff going on in an image。

 But if we look at even something simple like。The coverage function for a triangle。

 we immediately run into a problem。 Here here's our triangle， our coverage function。

How do I express something like a hard edge as a sum of sinusoids？Well， actually。

 it turns out that what I have to do is add an infinite series。

Of higher and higher and higher frequencies until I can eventually approximate something like a piecewise constant function。

Okay， so whenever you have discontinuities in an image。

 whether it's the coverage of a triangle or it's the silhouette on the side of a face。

You have infinite frequency in your input signal。The other problem has to do with reconstruction。

 because this sink filter has。Infinite support。 It goes on forever。

It makes it really hard to efficiently reconstruct an image from or using this filter。

 why is that the case？Well， think about what I have to do for every sample in my image if I have n samples in my image。

Then I'm making contribution to all other N。Samples are N pixels。

 and so this is an order n squared algorithm just to draw the image on the screen， super expensive。



![](img/c8e348c9c6db8df291d173884772d863_33.png)

Okay。So what does that mean in practice that means that？Things are going to go wrong。

 right imperfect sampling and imperfect reconstruction are a fact of life。

And that means we're going to see artifacts and images。

How do these manifest for things like the coverage of a triangle or sampling basic geometry。

 Well really， really common artifacts and graphics are you have。

 let's say jaggs in a static image if I draw a line segment it has these jagged edges in animated images in movies I might have roing or shimmering artifact So if you look at the horizon on this checkerboard。

 you see all sorts of crazy patterns moving around that aren't really there。

 This isn't really how a checkerboard should look， it's just because we're doing really crude sampling and then a really crude reconstruction using piecewise constant approximation。

And there's lots of other kinds of artifacts we also saw this moree pattern in the signine of x squared plus y squared and so forth。

So what can we do about this， how can we reduce aliasing？Well， again， no matter what we do。

 aliasing is a fact of life， right， any sample of representation eventually fails to capture frequencies that are too high。

 but we can still do our best to try to match sampling and reconstruction so that the signal we produce looks as much as possible like the signal we acquire。

So for instance， if we think of a pixel as a little square of light。

Then what we want is that the total light emitted from that pixel to be the same as the total light that we had in our original continuous signal。

 in other words， we want to integrate the input signal over the pixel to get the sample value。

And we already said that's hard to do， it's hard to get that exact coverage value。

 so let's approximately integrate the coverage by sampling。



![](img/c8e348c9c6db8df291d173884772d863_35.png)

OkaySo we come back to our coverage problem yet again。

 we want to figure out for each pixel of the image， how much of it is covered by the triangle。

 the simplest possible thing we could do is just sample the coverage function once at the center of the pixel and we get coverage values like this。

What did we say is the basic thing to do if we have errors in our reconstruction。

 what is the absolute simplest thing we can do to reduce the amount of error？Well。

 we can just increase the frequency of sampling。AllSo we could just take more sample points。

And sort of have a higher resolution image， if you like。But actually， at the end of the day。

 we still have to display the image on the same pixel grid on the same monitor， for instance。 So。

 so what we're really going to do is use a technique called super sampling。

Rather than just taking one sample of the signal， the coverage signal at each pixel。

We're going to take several。Samples right here we take four samples in each pixel in some sort of nicely chosen location。

And then we need to convert these sampled values back to。

Final sample values that we're going to use to reconstruct the image。Okay。

 so we start with the original signal， this coverage function。We do a dense sampling。Of that。

Coverage function onto a very fine grid。And。Then we turn those find values back into course values that we can use to draw the image on the screen。

So you can imagine that each of these four values if they're all for 100% covered。

 then we average them down and say yes， this pixel is 100% covered if none of them are covered。

 then we say the pixels not covered at all， but if some fraction of the samples are covered。

 let's say half of them are covered， well， then we say。

 okay 50% of that pixel is covered so we just use the fraction of sample values that are covered to get an approximation of the fraction of the pixel that's covered。



![](img/c8e348c9c6db8df291d173884772d863_37.png)

Okay， so now we've done a little bit better job of。Recovering our true coverage function。

 That was our original。Coverage function that we wanted to reproduce。 This is our reproduction。 Okay。

 it's slightly better than what we had before。I think this becomes a little more interesting to look at if we look at a real image。

 so let's go back to this checkerboard example。

![](img/c8e348c9c6db8df291d173884772d863_39.png)

![](img/c8e348c9c6db8df291d173884772d863_40.png)

And so if we just do single sampling， we just sample the center of each pixel。

 we get again these shimmering artifacts on the horizon。



![](img/c8e348c9c6db8df291d173884772d863_42.png)

If we run exactly the super sampling procedure that we did before we have four sample values per pixel and then we average them to get the coverage。

 then we get something that's a little bit better， but you still notice there's some pretty nasty shimmering artifact。

 So how can we make this even better。 well how about we do even more samples per pixel。

 So now in each pixel we have 4 by4 or 16 samples， things get a little bit smoother。



![](img/c8e348c9c6db8df291d173884772d863_44.png)

![](img/c8e348c9c6db8df291d173884772d863_45.png)

![](img/c8e348c9c6db8df291d173884772d863_46.png)

![](img/c8e348c9c6db8df291d173884772d863_47.png)

![](img/c8e348c9c6db8df291d173884772d863_48.png)

![](img/c8e348c9c6db8df291d173884772d863_49.png)

Okay， still not perfect。 how do we make it perfect， Well， let's just add more samples Okay。

 so now we do 32 by 32， we have 1024 samples taken for every single pixel and we average them back down。



![](img/c8e348c9c6db8df291d173884772d863_51.png)

![](img/c8e348c9c6db8df291d173884772d863_52.png)

So even though this looks a lot better， you notice it's still not perfect。



![](img/c8e348c9c6db8df291d173884772d863_54.png)

And that's what Nik Shannon was telling us is that well。

 you have infinite frequencies in your signal。

![](img/c8e348c9c6db8df291d173884772d863_56.png)

![](img/c8e348c9c6db8df291d173884772d863_57.png)

No matter how many samples you take， you're always going to have some。



![](img/c8e348c9c6db8df291d173884772d863_59.png)

Error in your reconstruction。RightNow I should say that in this very。

 very special case of the checkerboard there happens to be an exact solution。

 you can analytically integrate the checkerboard over a pixel and get this beautifully smooth image and if you want to know how that was done。

 there are a couple references at the bottom。

![](img/c8e348c9c6db8df291d173884772d863_61.png)

![](img/c8e348c9c6db8df291d173884772d863_62.png)

![](img/c8e348c9c6db8df291d173884772d863_63.png)

![](img/c8e348c9c6db8df291d173884772d863_64.png)

But the real point to make here is that such cases are extremely rare， it's really。

 really hard to work out the exact coverage or the exact integral over a pixel and so the reason that we use sampling in computer graphics。



![](img/c8e348c9c6db8df291d173884772d863_66.png)

![](img/c8e348c9c6db8df291d173884772d863_67.png)

![](img/c8e348c9c6db8df291d173884772d863_68.png)

Is that we want solutions that work in the general case。

We don't just want to talk about checkerboards on planes。

 but we want arbitrarily complex geometry with interesting signals。

 things are intersecting and overlapping and there's transparency and so forth。

 and really the only general purpose solution to that is to try to sample and reconstruct by taking finitely many sample points。



![](img/c8e348c9c6db8df291d173884772d863_70.png)

![](img/c8e348c9c6db8df291d173884772d863_71.png)

![](img/c8e348c9c6db8df291d173884772d863_72.png)

![](img/c8e348c9c6db8df291d173884772d863_73.png)

![](img/c8e348c9c6db8df291d173884772d863_74.png)

Okay。All right。

![](img/c8e348c9c6db8df291d173884772d863_76.png)

Coming back to the actual graphics pipeline， if we think about this stage of the pipeline that's responsible for sampling the coverage function for a triangle。

How do we actually do it？What's kind of the algorithmic approach？

So the most basic thing that we need to do。They say， okay。

 we have this triangle wave of this pixel grid， we want to know which pixels are covered by the triangle。

We can just break this down into an atomic query， which is how do we check if a given point Q is inside a triangle with vertices P0 P1。

 P2？What do you think， what would you do， you know a little bit of vector calculus and linear algebra？

What would be your approach to solving this problem？

 How do you know if a given cu is inside a given triangle。Okay， well。

 there are several different ways you could think about this。

 but they all essentially amount to asking。Whether that query point。

Is contained in three/ half planes associated with the three edges。

So we've broken down this problem even further。 How do you test have a points inside of a triangle well。

I know that if it's contained in。The half plane made by the bottom edge and the right edge and the left edge。

 then it must be inside the triangle。How do I do that test。

 how do I check if a point is inside a half plane well？

That's just a little exercise in linear algebra and vector calculus， given two points。

 Pi and Pj along an edge。And a query point Q。How do I determine whether Q is to the left or the right of the line from PI to PJ？

Now， you have to be。Really careful here because you have to think， okay， well， which。

Which side is left and which side is right， you have to make sure you get the order of PI and PJ right。

Also， you probably have to think carefully about the。Edge rules if I'm exactly on an edge。

 what should I do？Okay。But that's what we do to test just a single point， just a little calculation。

So now if I want to raize a whole triangle， what do I do。

 I need to in some order march over the pixels in the image and for each of them check whether the center of that pixel or the sample points contained inside that pixel are contained inside the triangle。

And one kind of traditional sort of older approach is to say， well。

 I can make this a little bit faster by noticing that the half plane check looks very similar for nearby points。

 so I can save myself some arithmetic by not going through these points in a random order。

 but by marching， let's say along rows of the triangle and incrementally updating my calculations to decide whether each pixel is turned on。

This incremental approach is also nice because it improves memory coherence。

 so actually in real modern hardware， the bottleneck is typically not doing arithmetic， doing math。

 but the bottleneck is reading or writing to memory so if you can traverse the pixels in a pretty coherent order that can actually speed things up significantly and there are lots of different ordering patterns here。

A more modern approach is to recognize that real hardware is also increasingly parallel。

So this idea of traversing the pixels in a grid and incrementally updating some values is a very serial idea。

 What we're going to do instead is just test all the samples in。

The bounding box around the triangles， so it's kind of the tightest fitting box around the triangle。

 we're going to test all those samples in parallel。

And because of the way that parallel hardware works， because we have wide parallel execution units。

The extra cost that we incur by testing more sample points is overcome by the efficiency of the hardware。

 This is especially true when， when super sampling。

There's some common calculations that have to be done for all of these tests so we can save a little bit of time there and also modern graphics processing units because they know that you the whole reason for these things to exist is to do lots and lots and lots of point and triangle tests。

 they actually just have hardware built in。That will efficiently perform this calculation。

So that's part of the reason we can draw billions of triangles per second。

 that's what the hardware is designed to do。Okay。So that sounds nice。

 but we still have some tricky cases like what's a case you can think of where the naive parallel approach is still really。

 really inefficient？And I fit the tightest bounding box around this triangle。

 and then I test all the sample points in parallel。When is this kind of a bad idea。Well。

 you can imagine， for instance， that I had just one long skinny triangle that stretched all the way across the screen。



![](img/c8e348c9c6db8df291d173884772d863_78.png)

Right， and so now if I'm。Testing all the points in the bounding box。

 almost none of them are going to be covered I'm wasting a lot of time。



![](img/c8e348c9c6db8df291d173884772d863_80.png)

So。I can take kind of a hybrid or course define approach。And first， ask if large blocks。

Of pixels intersect the triangle。 So before testing any individual pixel。

I draw some kind of medium size square ask， does this block intersect the triangle or not？And if not。

 I'm in good I'm in good shape， right， If I know that this gray box in the upper left doesn't intersect the triangle at all。

 then I don't need to do any more work。 None of those。None of those pixels are covered。Similarly。

 if I actually know that the block is contained entirely inside the triangle。

Then I can do an early in， I can say immediately that all of the pixels inside that triangle are turned on。

Right otherwise， I'm in this middle case。 Okay， I know that the box intersects the triangle， but。

It's not neither completely outside or completely inside。

 I still have to go ahead and test those individual pixels， but I saved myself a lot of work。

I'm only doing this fine grain check kind of along the boundaries of this big triangle。Okay。

 and this is how real graphics hardware works。Again。

 it's super tuned to do these checks in parallel and to do them with great efficiency。By the way。

How would you check if a box intersects a triangle？That's an interesting question to think about。

 You already know how to check。That a point or whether a point is inside or outside a triangle。

Can you use that test as a starting point for checking if a box intersects a triangle？



![](img/c8e348c9c6db8df291d173884772d863_82.png)

That's interesting to think about。Okay， so that's a little better。

 and so now we can imagine if we have this long skinny triangle。

 we've broken up into these boxes and we can quickly skip a bunch of them。

But still looks pretty inefficient， right， I mean， there's still a lot of boxes。

That we're checking and we do an early out， but it was kind of wasted computation。

So how might we do even better？And this leads to another really。

 really important idea in all of computer graphics， which is to take a hierarchical strategy。



![](img/c8e348c9c6db8df291d173884772d863_84.png)

Okay so we're going to apply this same course to thinking， but we're going to do it recursively。

Rather than picking just one box size， we're going to start out by saying， okay， first。

 I'm going to check， is the triangle on the screen at all。 If， for instance。

 all three vertices of the triangle are away off the screen， I shouldn't bother doing anything。Okay。

 but let's say I find that it is on the screen。Then I can check whether the triangle intersects these four big boxes。

OkayAnd for each of them， okay if it does intersect the box。

 then I'll split that box into four smaller boxes and I'll check if each of those four smaller boxes intersects the triangle。

 and I've skipped a lot of empty space already， and if I know that one of these smaller boxes intersects the triangle。

 split them into even smaller boxes。And。Kick out or ignore the ones that don't intersect the triangle。

 and I can split those into even smaller boxes。Okay， and I could keep doing that forever。

 but at some point。Actually， it's。Faster to just stop and check the individual pixels inside a box。

 so maybe I do this down to four by four pixel blocks。So this is pretty cool。

 I've really focused all the computational effort exactly where it's needed。Now。

 I will say this is actually not what happens in rail graphics hardware。

 because there's still quite a bit of overhead to doing this hierarchical traversal。

 So having just one course to。Level is kind of a nice sweet spot。But you can still think about。

 how could you improve this process a bit， if we just look at the pattern of blocks that we finally checked。

 you can think， well， isn't there a better way to find the finest scale blocks do I really need to do this hierarchical thing？

Well， again， given how simple a triangle is and how kind of a standard case this is。

Maybe you could do some kind of incremental traversals。

 So now we're all the way back to where we started。

Maybe there's some kind of incremental algorithm where I just go one little。

Block at a time to figure out which ones I need to check at the finest level。Okay。

 and so playing these kind of games is exactly the activity of computer graphics， trying to think。

 how can I structure the computation， how can I break things down to really match the computation to the problem structure。

Okay。Overall today， what we saw is that we can frame a lot of problems in computer graphics in terms of sampling and reconstruction。

 Saming is the process of turning a continuous signal into digital information。

Reconstruction is going the other direction we have the sample digital information and we want to turn it into a continuous signal。

Aliasing occurs when there's a mismatch when the reconstructed signal presents a false sense of what the original signal actually looked like。

We can frame rasterization as a sampling problem。So what are we sampling we're sampling the coverage function onto a pixel grid？

And we're reconstructing the sampled function by emitting a little square of light for each pixel。

 so basically by using a piecewise constant reconstruction of the sampled values。In this context。

 aliasing manifests as， well we saw it jagged edges。

 shimmering artifacts when things are in motion and so on。

Our basic strategy for reducing aliasing at least for rasterization was to use super sampling。

And this was really inspired in a way by this Nquis Channon theorem Nquis Channon said。

 if you want to reconstruct the signal perfectly， you'd better sample it at a rate that looks like the highest frequency。

Well， we can't always sample it at the highest frequency。

 but we can at least bump up the frequency a bit to get a better sampling。And hence。

 a better reconstruction。From a more system point of view。

 we saw that triangle raization is the basic building block for the graphics pipeline。

 So weirdly enough， we're going to reduce all of drawing images on the screen to。

Just drawing triangles really， really fast。And we saw that drawing a single triangle amounts to essentially just doing three half plane tests。

 Okay， and this is an atomic operations。 We want to make it really， really fast。

 and we talked about several strategies。 We can do it incrementally。

 This is kind of the old fashioned way that might be implemented in software。

We can do it in parallel。As we do it on graphics hardware these days。

 where we use blocks to do early ins and early outs to save ourselves a lot of tests。

 you could also imagine doing hierarchical schemes and all sorts of other things。

No reason that you couldn't improve on existing designs。Okay。

 so that's it for that stage of the pipeline， next time we're going to talk about another important stage of the pipeline was how we actually do these 3D transformations。



![](img/c8e348c9c6db8df291d173884772d863_86.png)

All right。 Talk to you next time。