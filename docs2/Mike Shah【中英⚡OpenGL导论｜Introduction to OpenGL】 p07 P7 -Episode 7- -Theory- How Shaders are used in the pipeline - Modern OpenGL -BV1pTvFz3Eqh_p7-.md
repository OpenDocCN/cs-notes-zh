# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p07 P7 -Episode 7- -Theory- How Shaders are used in the pipeline - Modern OpenGL -BV1pTvFz3Eqh_p7-

![](img/a39813c4f72be1c4457d54feef9cf617_0.png)

Hey， what's going on， folks， Mike here and welcome back to our modern open GL series。

 So in this lesson， I want to go ahead and talk about the part of the pipeline that happens after you specify your vertices。

 In The previous lesson， we talked about the vertex array object in the vertex buffer object。

 The vertex buffer object being our actual raw data， the X， Y and Z positions of a vertex。

 for instance， and the vertex array object telling us that we have in X。

 Y and Z or position data for some data that we might want to lay out that vertex array object might also have different layouts depending on what's in our vertex buffer object。

 things like texture coordinates， colors， normals and so on。

 But what happens after we actually specify our vertices。 Well， for that。

 we're gonna have to actually look at our graphics pipeline。

 So let's actually take another look at our graphics pipeline here。😊。

Now keep in mind that this pipeline is what goes on on the GPU。

 so this is the actual rendering pipeline。 I've grabbed this figure from the Chronos Wikipedia page if you'd like to read more about it。

So the vertex specification part， if you recall， this was our VAOs。And our VB Os。 Okay。

 so essentially， what we're doing at this stage is specifying some vertices。

 So you could imagine in our CPU side。 that is our C plus plus file。 We have something like this。

 maybe a standard。Vectctor floats。And I just call it， you know， vertices。And we specify a bunch of x。

 Y and Z positions in this initializer list Okay， and then we ship things over to a vertex buffer object using commands like GL buffer data。

 generating those buffers and so on。 and then setting the attributes with a vertex array object。

 So that's essentially what happens in what we talked about in the previous lesson when we're specifying our vertex specification。

But at this point， we don't have a graphics pipeline。So we need to have the rest of this process。

And I'm going to draw special attention to the vertex shader here。And the fragment shader。

Because those are the two pieces that we absolutely must have。 these other stages here， testellation。

 geometry or compute shaders or these types of things are completely optional。

 but we must have a way to process or position our vertices in the vertex shader。 And then finally。

 after determining which pixels arerasterized in the rasterization step。

 how to shade them in the fragment shader。 Now this is very cool because we have the power to program how this actually happens。

 This is what makes modern open sha， Mo open sha。 So let's go ahead and take a look at the vertex shader first。

😊，And I'll admit that this is a little bit weird what I'm going to show you。 but again。

 let me just explain and it'll all make sense soon。

So what I've pasted in here is an example of a vertex shader。

And this is probably one of the more simple vertex shaders that you can have we specify things like the version and well the input which we'll have to talk about here and then we have some other things that look familiar if you've done any amount of C or C++ programming which hopefully you have if not check out my other series but we have our main here which is the entry point into our program So the idea is again we always start from the main here。

And in this vertex shader， this is going to be our sort of hello world vertex shader。

 we have a singular built in function here。Now vertex shaders and fragment shaders and the other shaders have built in functions。

 they're usually indicated with a GL underscore， and that's how you'll know they're built in。

 theirre variables that we haven't defined anywhere else。

But what is this vertex shader doing Well again， it's a pipeline that we have here on the left side of the screen。

 so we're taking in position data。Where is this position data， Well。

 that's part of one of our vertex buffer objects。And there's different ways that we're going to communicate if we have color information or position information or other things。

 but for now we just have X， Y and Z positions and aW coordinate which we'll have to talk about later。

 but that's all that we're bringing in right now。And then the idea is per vertex in any triangle。

 so if I have a triangle here with three vertices。I need to position it so this vertex shader runs once for this vertex。

 once for the other one， and once for the other one in some non deterterministic order。

So that's the idea， and this is what our vertex shader is doing。And again。

 we have through some data structure here， which is just a V4。

 which is just some simple struct with an X， Y， Z， a W position。

That we're retrieving this information and just positioning it to recording。

Now we could do things here like add plus one or plus some sine function and then take in some other input like the time and kind of move around our vertices if we want this is what's powerful about the vertex shader we do all of our transformations here by positioning our vertex。

So once we've actually run our vertex shader， the position of our individual triangles that we're rendering if we're working with a triangle primitive has been set。

And then now we can take this information again from our vertex shader pipeline and then move down our pipeline through the other stages again we might have some optional stages like tessellation。

 geometry shaders， the vertex postpro which puts together and starts assembling things in the primitive assembly and then ultimately once we have our triangles here。

 they go through this rasterization step， which says hey。

 these are the triangles that will need to get filled in。

 and then finally we get to our fragment shader， which is the next part that I want to talk about here。

So the fragment shader again is a separate program here。

 we can see that it is again down here and our ver deck shader is up here。

And what this means is we have to， again have this second program that's going to get compiled and executed on the GPU once per fragment again。

 you can think about that as once per pixel if you'd like， but it's really once per fragment。

So we'll see a similar indication of what openGL version we're using 4。

1 for the most part of this series， we're going to see this out variable， V4。

 which is familiar from before from our vertex shader， and then this idea of color。Well。

 what's really going on here？And if we start looking at the main function。

 it we just have one color variable。And again， this is gonna to be new if you've only done C++ R C programming。

 but this idea of an outspecifier， something that's gonna to move out to the next stage of the pipeline。

 we saw in our vertex shader that we had something coming in or to the next stage of the pipeline but this time our fragment shader。

 which is really the last stage here just sent out one piece of information and that's the final color of the fragment or again the pixel if you want to think about it that way that we are filling in so that's the idea that I can determine here what that color is going to be using an RGB and then an alpha value for how opaque that pixel is going to be if we want transparency for instance。

So that's how a fragment shader works。It just determines the final color。

 but since it's running per pixel， we can do some very powerful things like per pixel lighting calculations。

 which we'll look at later in the series when we have a lighting model。

 so I want to go ahead and show you what this is going to look like in the code that we are actually going to write in this series。

And in a sense， what I put up here is going to be a little bit weird。

 So if you go ahead and just take a moment to look at this， you're going to notice that， well。

 it's the same exact code here。 Here's our。Vertex shader。 Here is our fragment sheet。

The one thing that's going to be different and that's a little bit weird to folks who are coming into OpenGL is that this is just a string here。

 it's a C+ plus string， and you can see I've put in end lines and all these things。

 some of them necessary， some of them not necessary， and then the actual same code that we had。Well。

 what OpenGL is going to do is use OpenGL commands。To build individual shader objects。

 we're going to get a shader object for our vertex shader。 Let me highlight it here。

And then another shader object for our fragment shaper。And then what's ultimately going to happen？

Is that we'll run some commands like GL and file。Shader。We'll do the same for our fragment shader。

 we'll compile it here， GL， compile， etc。And then we will link these together。In a link step。

And get a final。I'm just going to call it program。Object。

 let me give myself a little bit of room here。Program。Object。

That represents the actual pipeline here that you see on the far left。So I'll take again。

Our vertex source， our fragment source， and we can have any number of these。

 but we're just going to assemble one pipeline for now that determines how we render our vertex data specified in the vertex specification。

 So I think the tricky part here or the part that again beginners sort of get tripped up on is this idea that within our actual T+ plus code we're going be calling functions that compile this source code。

 So yes that does mean you will get some syntax errors and have to fix them。

I'll talk a little bit about the workflow later， but in a way this is kind of a cool or way to work。

But this makes sense because when we're running our CPU program。

 we actually have to compile this source that's going to be sent to our GPU。

 just like other GPU instructions that we would ultimately do。

So we need to compile at runtime this source code， send it to the GPU。

 and then we can execute on our triangles as we need Ultimately， once we've put all this together。

 we'll do something like GL。Draw。A raise。Or geo draw elements， which are our draw calls。

 which will execute this entire pipeline using the graphics。

 vertex shader and fragment shader that we've specified。Right， folks。

 I hope that gives you some more intuition about this idea of shaders。

 where they belong and where they look like。 Shaderrs can actually be quite simple in the sense of what we've seen here。

 There are just a few lines of code。 Sometimes they do grow more。

 but that's often once we start adding lighting and multitturing and other cool features that you might want to implement these things that you see in the latest and greatest games that you have so much fun play。

😊，All right， folks， I'm going to go ahead and end it here and then we'll dive into actually doing some more open GL shortly。

So I hope you're enjoying this series， I hope you'll leave a like or a thumbs up down below so I know and。

😊，As always， make sure to subscribe so you don't miss the latest lessons thanks for your time folks and we'll see it for the next one。



![](img/a39813c4f72be1c4457d54feef9cf617_2.png)