# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p06 P6 -Episode 6- -Theory- Triangles, Vertex Array Object (VAO) and Vertex Buffer O -BV1pTvFz3Eqh_p6-

![](img/4c69b957488eb582e8734f9f5c0d8cd0_0.png)

Hey what's going on folks it's Mike here and welcome to the next lesson in our OpenGL series Now in this lesson。

 we're gonna go ahead and talk a little bit about triangles and just where we're heading in OpenGL as far as using OpenGL to actually render some triangles So as a quick experiment。

 go ahead and find a piece of paper if you want or just fall along and go ahead and create a triangle from it by just bending it in half like this。

Now， triangles have an interesting property， and that if I take one of the corners here。

 if I have a perfectlyle flat triangle and I try to bend it or twist it。

 the rest of the triangle moves with it。In fact， this is actually a really important property of a triangle and why we use it。

 the fact that it always remains plainar here and it's not going to have any curves or anything sort of weird associated with the triangle。

This lets us quickly rastrize or fill in the individual pixels when we model things with triangles。

 So that's one reason why we use triangles in 3D graphics。

 especially in interactive computer graphics。 If you go on to look at movies like a Pixar or dreamworks。

 for instance， they might use other rendering techniques that could be in another series。

 but for now we're going to focus on interactive programs and triangles。 So with that said。

 let's go ahead and take a look at what we've been doing here。So here's a model of a triangle here。

 this golum that showed up here and as I mentioned。

 if you look closely this golum model is made out of triangles so the properties of triangles that we like are that it's plainar and it's just a simple shape to work with given enough triangles we can approximate some character like this with relative ease in the sense of how the graphics hardware actually processes these triangles so some other properties of triangles just so you're aware of the terminology we say that we have three vertices here。

And that's at each of the points here， so shown here， here and here and triangles are connected by。

Or rather， the vertices excuse me are connected by these edges here。

And these are line segments essentially between two vertices and oftentimes in this graphic series you're going to hear me refer to things as points or vertexes。

 you might want to think of a triangle like a graph and call it a node， that's probably okay。

 but in this context we really want to think of it as a vertex and it's actual geometry。

And then this actual triangle here is what we call a face here。

 this triangle has one face or at least one front face facing outwards on the other side of the triangle。

 there would be one other face as well。Okay， so now that we have a little bit of a review of triangles and what they are。

 let's talk about some of the openGL structures that we're actually going to be using here so last time if you watched our previous lesson we actually did some code to do our first openGL function call that was this GL gettrained and that was to ensure that OpenGL and so on had been set up。

But before we move further again with rendering triangles。

 I actually want to take a step back and give you some idea of what we're going to be doing in the next lesson when we open up some code。

So the idea is we're going to be using two open G objects to achieve this。

 so let me go ahead and just label this here。open g l objects。

And there's a lot of different objects in OpenGL， and I'll talk a little bit about this later on when we talk about code again just to help you with your mental model of OpenGL。

But the two that we're going to work with are vertex。Array。Objects。And they're often abbreviated VAO。

 for instance。And I'll go ahead and explain what this is in a moment。

The second thing that we're going to work with is called a vertex buffer。Object。

And they're usually abbreviated VBO。And these usually have to deal with the actual vertex information。

 so let me go ahead and label that ti for you。But this is he。Actual。Datter。And vertex array。Object。

 which the name's a little bit confusing， but it's。Howo。To access。Your。Vertex buffer object。

 or at least that's how I'd like you to think about it for now So let me sort of pictorially try to give you an idea of what this means。

So again， going back to our idea here of what a triangle is。

Now each of these individual vertices here， and I'm just going to highlight one has a X。

 Y in a z position here。And I'm actually going to label these here， x1， y1， and Z1。

And we could do the same for our other vertices， where now just go ahead and put a number here， one。

 two， and three， doesn't really matter the order that I specified of it。

But somewhere I need to capture this information if I'm going to pass it to my hardware so we know how to represent this tri。

And again， to do this， we're going to use something called a vertex buffer object。

So what does this mean well a buffer itself is actually just an array or a block of data here。

So let me go ahead and label this， so x1， y1， z1。X2， Y 2， Z2。x3 y3 and z3，You get the point here。

Okay， so this is essentially just an array here。So what we do as far as open GL syntax is we have to generate one of these buffers。

 so they'll use GL。Jen。Bs and usually there's some arguments here like how many we want and then a handle so we can sort of keep track of this object here。

So my object。Something of this nature。And then what we're eventually going to do is GL buffer。Data。

Which is to populate this actual structure here， okay， that'll be the function call that we use。

And there's one other call I want to sneak in here， which is going to be GL。Bind。😡，Bffer。

Which is essentially saying， hey， we want to work with this specific buffer Okay。

 so those are the function calls that you're going to see associated with vertex buffer objects most often。

Okay， so this is our first vertex buffer object， VB01。Now。

 how does the vertex array object plain into this Well， let's go ahead and label it here。

 vertex array object here。 So again， it is some sort of object。

 and if you want to think about this in terms of Java or C+ plus where you have objects。

 it's collecting some number of attributes， I suppose。So let me go ahead and label it as such VAAO1。

And syntactically， we're going to have something similar here where we do GL。

And here I'll do it's in the same font here。Gen or creation。Vertex。As。Okay。

 so similar syntax here with a GL gen， that means we're allocating something or getting ready to allocate something。

 how many vertex arrays we want， usually just one at a time。

 and then whatever we're going to call our vertex array object。

 and then we'll bind to this vertex array object， a GL bind vertex。All right。

And the vertex array that we want to bind to。And again。

 when we're bind to something that's essentially saying， hey， in open GL speak。

 select this vertex array object， there's something we want to do with it。Okay。

 now what actually lives inside of this vertex array object though？Well。

 this is what's sort of interesting and we're going to see it in the actual openGL syntax。

 but we essentially have these attributes。And what are the attributes of a triangle， Well。

 position is actually an attribute here， so position。

So what our vertex array object is doing is essentially saying， hey。

 how do I walk through my vertex buffer object？Well， what is my vertex buffer object consist of？

Three positions here or three floats here for X， Y and Z。And that's how we get to our。

 say first vertex here。And then we get to the next vertex。

Which would be over here and then to the next vertex over here。

So essentially we just have one attribute here in our vertex array object。

So all vertex array objects are are sort of a specification， again。

 part of that vertex specification in our graphics pipeline that says， hey。

 when I've got some data here， how do I access that data？Now。

 just to give you a different idea of another type of VAO we could have。

Let me go ahead and create another VAAO here。And I'm going to give it attribute。One here。

And attribute。Two， we don't really have better names for them， that's just how it is for now。

And let me go ahead and just create another vertex buffer object here。

But this time I'm going to do something just a little bit different， I'm going to have an X， Y。

 and z position for all of our vertices。As well as a red， green， and blue value here。

So what's different at this time， attribute1 is going to point to our actual position data attribute 2 will point to our red。

 green and blue data for instance， if I've made these vertices red。

This is how we would get color inside of our triangle。

Our rasterization pipeline would read in the positions， so we know where to position vertices1， two。

 and 3。And then we have some more data that we want to pass in or use in our pipeline。

 which is the actual colors of those vertices。And depending on what type of data that I want to access that is these vertex buffer objects。

 I either activate vertex array zero here， or excuse me， one here， or vertex array， well。

 object two here that we have。So that's how I can sort of change。

How the open GL state machine works and that is to say how the rendering pipeline works based off of what type of data I have in my buffers。

 So I'm going to go ahead and close lesson here because this is a really important idea here。 Well。

 a few important ideas rather that we've covered。The first is that we're going to be primarily working with triangles in this series。

 I think is a great place to start we can talk about points and lines later。

But now we at least know the importance of triangles when trying to render various characters here。

The second big idea here is that we're going to be using different openGL objects Now again。

 OpenGL is a C based API so we don't have classes and these types of things。

 but rather collections of functions， things like this where we're going to generate an object。

Bine to it and then populate that actual data and those things working together will in a sense form an object or some collection of data。

And then we had this idea of a vertex array object。

 which tells us how we're going to access this data and then the actual data itself。

 which lives in a vertex buffer object。So folks， I hope that was a useful lesson for you。

 in fact I'm going to go back here one more time I'll remove myself from the screen here just so I can get an overview of this picture here。

Because I think this will be helpful for you to just understand and take in so if you want to pause the video back there。

 feel free to do so。We'll get into coding in the next lesson or so so we can actually put into practice this idea of a vertex array object and vertex buffer object and in these early lessons I'm really going to keep hammering in some of these ideas and taking some pauses like this lesson to talk a little bit about the theory I hope that'll be helpful for you。

So make sure you don't miss those lessons， make sure you subscribe。

 make sure your comment below if this wasn't clear。

 but we will be revvising these topics many times and the good news is it doesn't really get much more complicated than this。

 we just have to understand how things are working。All right folks。

 we'll go ahead and see you in the next one。

![](img/4c69b957488eb582e8734f9f5c0d8cd0_2.png)