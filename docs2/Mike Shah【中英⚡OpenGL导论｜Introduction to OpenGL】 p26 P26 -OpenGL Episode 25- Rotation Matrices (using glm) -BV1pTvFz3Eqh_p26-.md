# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p26 P26 -OpenGL Episode 25- Rotation Matrices (using glm) -BV1pTvFz3Eqh_p26-

Hey what's on， folks is Mike here and welcome to the OpenGL series where today we're going to be talking about rotations So previously if you've been following along with this series we've covered lots of stuff like drawing triangle。

 how the graphics pipeline works， and we've even touched on some of the different transformations that take place from the local coordinate system into worldspace things like translation so we're going to do a little bit of a recap here and then we'll get into rotations。

 understand just a little bit how they work and how to apply them in your graphics projects so with that said let's go ahead and cover the highleve idea here。

Now again， the high level idea is just following along our graphics pipeline， again。

 the first step being where we have our vertex specification。And again。

 this might be a little bit of a review for folks who are just hopping into the series or have been otherwise following along。

 where I have a bunch of vertices placed in space。And these vertices here get acted on by the vertex shader。

 so each individual one， and then they undergo some transformation that takes them from their local coordinates。

Two， what's known as World Space。Because every vertex， when we first place it， is specified in this。

Sort of common coordinate system just you know at the origin。

 we can sort of assume that's where they're being placed and then we want to translate them out into the world based off of whatever transformation that we apply。

 So again we've looked at translate which let me go ahead and highlight in our previous sample here which moves a vertex sum offset here in this particular case we have a vector moving a vertex0 on the X0 on the y and then whatever our value is for the offset here So that's just a little bit about what we've done and to form this actual translation we create a new matrix here and offset it by this vector So that's the basic idea。

 we're doing a matrix multiply against some vector and moving things around。

So if you need a little bit of a review on that there's lots of great resources on the web。

 but what we're going start talking about now is various rotations so you can find any sort of tutorial here。

 I'll just go ahead to this one here on transformations and I'll do a little bit of review on matrices。

 I'd recommend reading through one of these resources here Learnup and GL watching my series etc to again just see what these matrices are here that we use for our transformations so again we have a scaling matrix rotation which we're going to talk about and we have three and then as we talked about which is later here。



![](img/f78a25a00744370fc7b9e776b8ba111c_1.png)

Probably in this tutorial， let's see if they have translation， yes。

 here is translation okay and here's the special matrix that GLM creates for us so we could do a deep dive in the math if folks are interested in some more of that style of things that might actually belong in a separate series。

 but please let me know in the comments and subscribe otherwise。

 but let's just go ahead and focus on today's topic which is rotations。

And the basic idea with rotations is these special matrices that we have here where we want to perform some rotation about some axis Now go ahead and notice if we're going to rotate about the X axis if I'm reading the columns here where this is the X column。

 which I'm highlighting。Then well， it's the identity， so it's not actually moving here， okay。

 but the actual works going on in the Y column down this side here and the Z column here。

Now I'm going to go ahead and focus on the Y axis rotation here。

 so let's just go ahead and write that one out here。



![](img/f78a25a00744370fc7b9e776b8ba111c_3.png)

Just so we have it。Wch is cosine of theta zero。Negative s theta is zero， zero，1，0， zero。Sine theta。

 zero， cosine theta zero。And then the last column there is uninterrupted。So again。

 just to make this clear here， these are sort of the columns that I'm reading here。

 this would be the X， this would be the Y， this would be the z， and then this is our W here okay。

 which allows us to do translation with these coordinates here okay。

 so I can read a little bit more about that but what I just want you to focus on here is that this is our special rotation。

About the Y axes， okay， using ouler angle rotations here， let' move out so you can see that。So again。

 the thing to notice here if I'm rotating some object about the y axis is that the points aren't moving up and down here okay so if I draw some little coordinate system here and I have some shape here。

 which let me go ahead and get a different color。To represent this。

 let's go ahead and do this in say blue here。There we are。Oops。Right， all right， there we are。

 there's a blue。I would have some shape here and if I'm rotating about the y axis again that's rotating about this axis here okay just at the very top here So essentially if I have some point here like this again the height's not going to change the y stays the same but it's going rotate all the way around this axis and sort of orbit that point so that's the idea that's how to again interpret these matrices and what the actual columns mean Okay so it can do a little bit of a deeper dive doing some reading on your own here。

 but I do want to get into the programming portion of this now we are going to use the GLM matrix library and continue with that so it'll be handy to search for the documentation here let's go ahead to the API documentation and I'm going actually search for rotate here。

😊。

![](img/f78a25a00744370fc7b9e776b8ba111c_5.png)

And let's make this a little bit bigger here。And let's click on rotate。

 So the good news is you don't have to memorize those special rotation matrices。

 Now if you are building your own library， that's probably useful if you're doing other things like converting wayer angles to quatians again。

 it's important to understand that type of mathematics。

 but we're just going to use GLM which has that built in and focus on some of these rotation functions here So here's an example of a rotate function which takes in the matrix that's our input matrix here the angle。

 which is going to be in radance， but we can think of it in degrees and convert it and then the axis that we're rotating about So in our case。

 if we're rotating about the y axis， we'd represent that with a vector010 y is010 well。😊。

That's what this vector is。 our Y axis is just 0，1，0 here。 Okay，0，1，0。 Okay， and then， of course。

 you could rotate about other vectors or， you know， make changes as you need。

 But that's the basic idea。 So let's go ahead and see if we can implement this rotate into our existing code。

 Okay， so that's where we're going。 But as always， I'd like to do a little bit of a review in case you're jumping into this series or haven't seen it in a while。

 But here is the main of the program that we've created。

 We've got some steps for initializing our program。 So again， that's things like setting up open GL。

 for instance， making sure our windows created and so on。😊。



![](img/f78a25a00744370fc7b9e776b8ba111c_7.png)

We've got our vertex specification。Wwhich is again just setting up some of our simple primitives。

 we've looked at vertex array objects which sort of set up the state of what type of objects we're going to draw。

 we've set up some vertex buffers which populate our objects with the vertices and we're using an indexed buffer strategy here to reuse our vertices to draw our quad。

And then ultimately， we create our graphics pipeline。

 which consists of a vertex and a fragment shader at the least。

And then we have our main loop where we're doing our work here。

 our input will maybe add some input here so we can demonstrate our rotation。

 but for now we're just changing this global offset value。And let's go ahead and hop back here。

And we have pre-draw， this is where we've been doing our transformations。

 sometimes folks will just label this update or something of that nature。

 but this is where we were previously doing our translate and then we had another matrix here we are multiplying in to get our perspective。

😊，And in particular， how we're passing in data into our vertex shader which ultimately draws the final position of the vertices。

 again that's where our transformations have to take space place because again。

 we have our vertices that we specify but in our vertex shader they undergo these transformations and we've already looked at the perspective transformation so that we can draw a proper square。

So that's what's going on there， here's our projection matrix again here it is set up here。😊。

And I've already set up a model matrix here。And then finally。

 we have our draw which we're not going to really need to play with today。

 but that's basically just taking all of our data， and as soon as we issue the GL draw all elements call that runs our graphics pipeline。

 so it runs all of our vertices that are currently bound in our vertex buffer object through our graphics pipeline performing all the transformations as needed。

Okay， so with that review out of the way， let's go ahead and start looking at implementing a rotation here。

So what we're going to go ahead and do is create another matrix here。😊。

And I'm just going to call this rotate and do a GLM rotate here。

And then the matrix that we want to rotate about here， well when were doing our translation。

 we were just doing this according to the identity and then storing it in translate so let's kind of regroup things here。

😊，So what I want to actually do instead of translate， I want this to be our model matrix here okay。

 so basically it's going to perform a series of maybe translations， rotations， etc。

 that take place here Okay so this is our initial translates that we're doing here to set up our scene。

Our rotation here。We'll apply to our model matrix and again we can just。Store this。

 update our model here， that's how I'll do it， I'll keep it indebted like this。

And then the things that we needed were our degree that we're going to rotate about。

 so we might just say like 45 degrees， for instance， and again this has to be in radance。

 so GLM radians will do the trick there。And the axis that we want to rotate about。

 So let's go ahead and rotate about the Y axis at 1。01。0 f。

And let's go ahead and take a look at that Now I've updated the variable translate。

 so let's make sure that I pass in the correct matrix here。That'll be the model matrix here。

And I think that should do the trick for us let's go ahead and compile see if we made any silly mistakes。

 no mistakes， and just a quick review of our shaders as well， which I think we should do。

 let's go ahead and look at our shaders， looking at the vertex shader again。

 which is taking in position and colors， we've got our model matrix。

 which will hold our transformations and the projection。And again。

 we're doing our whatever our position of our vertice is that's coming in from the vertex specification。

 So again， positions just up here are vertices， x， Y and z positions and buffer。 the model matrix。

 that's our translation or series of things that we perform on our CPU and pass in here and then lastly。

 the projection。 So again， we're reading right to left as far as the sort of order that the transformations are applied Okay so just something to keep in mind there。

 and I'll go ahead and just let's just go ahead and briefly show you the fragment shader。

 nothing's really changing here。 We're just applying the colors。 Okay。

 so we're not doing anything interesting quite yet。😊，So again， this compiles successfully here。

Let me move out of the way so you can see the full compile command if you're on Linux。

 otherwise watch the other videos of my series for Mac if you need。

 and let's go ahead and run this program here。Okay， now if I go ahead and update this。

 I've got to push back here， you'll ultimately see that our shape is moving somewhere。

 it's in front of the screen here。And it is rotated 45 degrees here so that's pretty cool。

 In fact that was quite easy here so let's add a little bit more to it here So again up and down is just modifying our translation but let's use the left in the right key so that we can rotate about some axis here so what I'm gonna go ahead and do here is just modify and again I'm just creating a global variable here not because it's the best thing in the world to do but because it's the simplest so again G for global again you'd probably want to encapsulate these in some sort of struct or per object that would be a common thing to do。

😊，I'm just going to call this rotate， we're going to start it off at zero here and again the U in front of rotate is because I'm usually setting these up with a uniform variable。

 so I'm just trying to be disciplined about that。😊，And our rotation here。

We're going to actually just change this to。The global variable underscore U rotate and again being disciplined with the naming of your variables helps your Intelence and these types of things be a little bit easier。

 so update our model matrix by applying a rotation。😊。

After our translation okay so let's go ahead and leave that as is and now let's go ahead and we need to go into our input。

 So again， that's going to be from our main loop so it's kind of travel into there and into our input。

😊，And let's update some of our keys here。So this scan code for left。

 let's go ahead and update the rotates here。To do minus equal。0。01。And we'll go ahead and update。

 actually， let me update our print statement here just so we can get a little bit of debugging。

 you rotate。Okay。And make sure that we print out the right variable there。Okay。

 so that's looking pretty good here。And let's go ahead and handle our right key。And again。

 these scan codes are from SDL and that should do the trick here。 Okay。

 so let's go ahead and give this a compile see if we made any mistakes， nothing yet。

And let's go ahead and move in our code and again let's press down here now get to press down you'll notice my objects being offset backwards again if you need a reminder you can kind of do the right hand rule Z positive is facing out of the screen see negative inwards So our cameras looking down the screen that's why we've got to push the object back and I'm going to try left here。

😊，And it is rotating just very slowly here。So let's go ahead and give that another try here。

 let's do something like let's make this 10 times as fast here，0。1。😊，There we go。

That should give us a more convincing rotate， recompile， rerun。

And let me bring the window in for you here， push our object into the screen here。

 and then I'm gonna to hold down the left key and rotate and we can see that our object is rotating again very slowly。

 but it's doing the job here let's speed that up one more time and then we'll get ready to wrap that up。

 let's just make this 1。0 because again， it's got to go1 360 degrees to do a full rotation know which is a journey so let's go ahead and yet again。

 push this into the screen a little bit and then we can see a nice rotating primitive。

 let's go the other way， let's hold down R here and we can see our object rotating here on flipping around here So that's quite nice here and you can see the actual degrees updating there we might want to actually cap that value to 360 but you get the idea here and we can go the other direction。

😊，Now again， it is important here。And maybe I'll play around with this in the next lesson because I think this is enough for this one here that we are doing the order of our transformations correctly here。

 so just something to keep in mind with openGL and in general just be very careful with your operations again I always tell folks if they're not seeing their objects on the screen here。

😊，So for instance， if I push up and down， it's usually because the object might be behind you so you got to think about your coordinate system。

 and then sometimes you have to be careful if that you're not getting expected behavior that your transformations are applied in the correct order。

All right， folks， so with that said。I hope you enjoyed this lesson here put in the triangle here or the square rotating here。

 and I hope you'll go ahead and consider trying this out and letting me know in the discussion if you have any other questions here and as always make sure you subscribe so you don't miss these lessons and as always again。

 thank you for your time and attention I'll look forward to seeing you in that next openGL video。



![](img/f78a25a00744370fc7b9e776b8ba111c_9.png)