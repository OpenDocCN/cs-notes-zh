# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p21 P21 -Episode 21- OpenGL - Putting it all together (SDL2+glad+glm) - Modern OpenG -BV1pTvFz3Eqh_p21-

![](img/d1e41e096a0e737f27e7485894db1846_0.png)

Hey， what's going on， folks。 It's Mike here and welcome to the next lesson in our modern Open GL series and C++ In this lesson。

 I'm going be talking about how to incorporate the GLM library。

 which we've been looking at in our previous lessons with all of our other stuff to make a graphics application。

 That means that we have SDl2 or some windowing framework。

 Maybe some of you are following along in GFW。 We have open GL itself at the G header library to help us set up and use opengl functions Again some of you folks might be using glue。

 And then we have GLm， which is this mathematics library。

 So how do we link everything together and build our graphics application。

 That's what want to talk about and then just briefly review on the whiteboard a little bit how all these components fit together。

 And then we'll get back doing some opengl stuff and learning about some new commands and openg。

 So with that said， let's go ahead and dive in。 So here's where we left off in our previous open G lesson。

 I'll just go ahead and give you high levell overview of the project structure。

 So again we've got our shaders for building our graphics pipeline in the shaders folder our source code。

😊，Wwhichch is essentially all in our main do cP for now。 And then we've got G do cP。

 which was a separate tool we downloaded to help us load all the open GL functions。 And then finally。

 we have the header for that as well。 And then if you're on Windows。

 maybe you have the SDL2 DLL and of course， all the other setup stuff from way early in the lesson where we set up SDL2。

 Allright， Now with that said， we need to go ahead and load up GLM。😊，Now。

 what I'm going to go ahead and do here is show you my directory here where I've got the episodes。

 But something that I've done is I've just created a common folder。

 So this is something that I'll commonly do here。 If I have something that's going to be shared amongst  well。

 essentially all of my episodes here。 So I don't have to keep duplicating And inside this third party folder here。

We'll find the GLM library here， GLM master and so on and eventually find the GLM header file。

 which we will need for our projects to use this math library。

 So you can organize this in any way that you want。

 I imagine lobby folks just have one directory where you're building on top of this。

 But I just wanted to show you that that's my directory structure。

 So let me go ahead back here to our current episode here where we are in episode 21 already。

 I can't believe it。 And let's go ahead and make sure that we can link in the GLM library。

 So how am I going to go ahead and do this。 Well， let's go ahead and just look at my source code in the main。

 And I've got my line here for how I've been compiling this project。

 So let me go ahead and just make sure that this builds go ahead and give this a copy here。

 compileile it。 Let's go ahead and give it a run here。

 and let me make this full screen so we can see the full line here。😊，And if I go to my other window。

 we have our quad where we left off。 So our structure is looking pretty good here。

 but we do want to be able to add to this third party library list GLM so that we can start doing mathematical transformations。

 So I'm going to go ahead and just include GLM slash GLM do HP here and again。

 if I try to compile here， well， if you followed any of my compilation videos。😊。

It's probably going to yell at us saying， hey， we can't find this library。 And， in fact。

 that's exactly what it's doing here。 So what we need to do on our command line here。

 And I'll make this a little bit larger so we can see is update our include path here。

 So where do I want to be able to include things。 Well， I've got to navigate to this library here。

 So I want to actually go up a directory into the common folder。 third party is where I had it。

 G L M。 the repository here。And you could actually just shorten that up。

 and that should be where my actual repository is， wherever the header file is。 So again。

 what you're looking for if you go ahead and look at this。And I'll actually get rid of。

 I actually want to change this。 So it's just GLM， maybe or just third party。

 So I'm going to go ahead and enter。 we'll get this complaint here。

 But let me actually go back and here just fix up my comment here into third party。

And we could go ahead and see where the path is here。And I've got the GLM folderer here。

 Let me just go ahead and move everything that's in that directory。Right here。

 let's go ahead and do this here。 move all the files。And now I can just remove that directory here。

And let's go ahead and see。 that should have everything Nows might have some hidden git files in here。

 So'll go ahead and delete that。 And now we've got things moved up。 That's a little bit cleaner。

 I like that just a little bit better for the purpose of this lesson here。

 Our third party is actually only gonna have GLM stuff in it anyways。 So that's okay。

 how it is setup up here。 All right， So there we are。 And we should be all set。

 Let's go ahead and try to recompile that with our new compilation。😊，String here。

 And we could go ahead and。Compile and it's working。

 So we know that we're actually finding the GLM header file here。

 and there might be certain things that we want to include by default that we're going to need things like GLM V 3。

 for instance， is going to be common and things like mat 4 by 4， for instance， will' be common。

 And we'll add these as we need them。 but I'll go ahead and just include those for now。 Okay。

 so where does this leave us in terms of our structure。

 And let me go ahead and update this compilation string， because we're going to need every time。

 as we compile。😊，And let's go ahead and just paste this in here。 There we are。And again。

 the update was to make sure that we can find this header file because the GL mathematics library is just a header only math library。

 All right， so with that said， let's go ahead and look at how we're doing everything in this project。

 And I know for students or beginning learners， this can be something that's a little bit overwhelming when it comes to open GL。

 All the boiler plates and the different libraries that we're using。

 And it's probably worth even just doing a quick code review here as well of our project。

 So let's just go ahead and open up in our main what's going on here。 So again， we have Sel。

 We have the Gla library。😊。

![](img/d1e41e096a0e737f27e7485894db1846_2.png)

![](img/d1e41e096a0e737f27e7485894db1846_3.png)

![](img/d1e41e096a0e737f27e7485894db1846_4.png)

And let me make this a little bit smaller here。 the GLM library， Glad and SDL。

 So let me go ahead and just kind of list those out here as we go through them。 So SDL。

 then we have Glad。😊，And GLM， okay， are three sort of dependencies that we have here。

 And then as far as how our code was structured any time I'm working on a project。

 I always start from the bottom。 or let's use our tools here and search for main。

And actually find our entry point into the function。 And again。

 we're essentially emulating the graphics pipeline。

 Please check out the earlier videos in the playlist if you want to see how that works。

 But initializing our program。 so that is doing things like setting up SDl and setting up G。

 for instance， then setting up our graphics pipeline， creating the graphics pipeline。

 or rather this is setting up the data that we're going pass into our graphics pipeline。

 our vertex in our fragment shader， then calling our loop。

 which is going to do all the work and then cleaning anything up here so that's just a little review of our application。

 Now where do these components all fall into everything。

 Okay so what I've just shown you here as far as our source code。 and I'll indicate that over here。

 that's our main do cP and this is the actual application that we are building here or the app。

 and that's where we're going write our code here。 But in order to build this。

 we're going borrow some components。 So for instance， from GLm， we want to include those components。

 which is essentially doing a copy and paste into。😊。

AppSo we're adding some more code in here to give us those mathematic functions。 In fact。

 that's actually what Glad's doing， too。 We're just adding some more functionality here so we can call open gel functions。

 S DL doing the same thing。 We're including the header file here to help us do things like creating a window and so on。

😊，But as we're doing this， and I'll go ahead and open up our。At the top of the program。

 our compilation string。 Again， there's these other parts here that we can't forget about the linking stage in our application。

 because SDL， we've got the actual header file for。 but we need to glue in the SDl library here。

 So depending on your platform that's going to be SDL DL。 if you're on a Windows， for instance。

 if you're on Mac that's going to be something like SDl diallibib。 And if you're on Linux like I am。

 that's going to be something like SDl S or some file like that。

 And basically what this is these libraries is a bunch of binary code that's been compiled for us。

 This is the actual implementation of all these SDl functions that we're bringing into our code。

 and then that we're going to essentially glue in to our project。 and I'll sort of indicate this。😊。

When we compile our code here， our main dot CPP， this turns into some sort of binary。

And eventually both of these projects will get or these individual components are shared library and our code get glued together in our final dot slash program。

 which is our binary that has everything Okay， so that's the general idea And again。

 why do we need all these components。 Well we need SDL for creating a window and essentially helping us hook into these open GL functions that we have creating this open GL context is what it's called。

And then glad what it does is it helps us say， hey， we want this version of open GL。

 We're using version 4。1 or greater for most of this series。

 And it's basically saying where do those functions exist on our actual hardware。

 So you need a tool like Gla or glue to use that。 And then GlM' is really just a convenience for us。

 It's implemented a lot of the functions that we need4 by four matrices， vectors。

 three dimensional vectors。😊，Or with three components， I said say。

 and various mathematical operations， things like dot product and crossproduct projections and so on。

 So that's what Glm's giving us。 We could implement this ourselves in our CPP file if we want or a header file or whatever we'd want to do but we're just not going do that here。

 so I hope this gives you a layout of again what's going on with our graphics applications。

 The good news is we're not going need to add anything more other than these three components。

 at least for the foreseeable future。 that's just how things work。 Okay so with that said。

 I think we're gonna go ahead and cut this lesson off here。

 give you a chance to just take in all the code or if you want to go ahead and try this and have all the components working。

 then you'll know that you can proceed further as we move on to the next topic。 All right folks。

 I hope you enjoyed that lesson， hope you're enjoying this series as we take bite sizeized chunks and are marching our way through graphics programming here。

 we've got all the components that we need we're already drawing rectangles and while those are super。

😊，Inesting what I tell my students is graphics programming once you get to this point really starts to ramp up as far as the cool stuff that you can do because well。

 once we can draw one or two triangles， we can draw as many as we want。

 and that's where we can start doing interesting things。 So with that said folks。

 thanks for your time， make sure you subscribe so you don't miss future lessons on this series as we continue marching forward。

 And as always， thank you for your time and attention。

 I'll look forward to seeing you in the next video。😊。



![](img/d1e41e096a0e737f27e7485894db1846_6.png)