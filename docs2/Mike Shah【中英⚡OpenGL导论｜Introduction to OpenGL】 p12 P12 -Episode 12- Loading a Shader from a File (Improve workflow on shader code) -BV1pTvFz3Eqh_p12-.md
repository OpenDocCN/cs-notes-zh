# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p12 P12 -Episode 12- Loading a Shader from a File (Improve workflow on shader code) -BV1pTvFz3Eqh_p12-

![](img/7f30a3bfb03dc1e935d9b64f75595f2b_0.png)

Hey what's going on folks It's Mike here and welcome to the next lesson in our modern OpenG series in which we're learning modern OpenG with C++ So in this lesson I'm going to do a little bit of recap from the previous lesson where we were able to render our triangle or at least the last time that we were writing code And now what I'm gonna to do is go ahead and clean up our code a little bit and talk about the workflow with shaders We're going add a load shader function。

 which is going make it more efficient to work with our CPU programs that we compile and our GPU programs So with that said let's go ahead and dive in for a quick review。

😊，So just in case you're not following along with the series here is our project structure look something like this and again some of you might be using different types of libraries like GLFW or maybe you're using SDL2 like me it doesn't really matter。

 but roughly speaking here's what we got in the main file is where we have all of our code。

So let's go ahead and dive into the source director， the main file。

 and have a look at what we've been doing。

![](img/7f30a3bfb03dc1e935d9b64f75595f2b_2.png)

So just to get a really high level overview of this program again。

Just starting from the main function here， and let's do head from here。

I've broken up our program into the main steps when I think about a graphics application First we set up the initialization。

 which is in charge of setting up your window， setting up open GL selecting the version。

 any of these sorts of functions and the vertex specification was responsible for just specifying some vertices and what we're going to do with those Perhaps we're just going to have a bunch of triangles with x Y and z positions for instance and today what we're really focusing on is this creation of the graphics pipeline and that's with our vertex in our fragment shader the programs that are run when we essentially call GL draw arrays or some other draw function and then we'll have our main application loop which is going to be responsible for constantly drawing using some pipeline that we have and then execute taking an user input and just running your game or whatever project that you're building So let's go ahead and just take a quick look at the crate graphics pipeline function which is what we're gonna to be modifying today。

😊，So if I go ahead and do a quick search for this， let's go ahead。

And what this function is doing will notice the crate。

Shader program is taking in a vertex shader source and a fragment shader source。

 and this is what I want to go ahead and fix or amend from the last time when we wrote our first OpenGL program in one of the prior lessons。

And again， all G graphics pipeline shader program is is just some unsigned integer that is the program object for our shader。

But what are these shader sources again， well， if I go ahead and scroll to the top of our code here。

You'll notice that what I've done here is encode our vertex shader and our fragment shader here just as strings inside of our program。

 and again this holds true with what we do in OpenGL。

 we are just compiling strings at runtime of our Shar programs。

 at least that's a way to do it in most versions of OpenGL。

So this is a little bit of a problem though， because every time that I want to change just our GPU programs which get compiled every time we run our software。

 I have to recompile our whole project here so that's the issue that I want to essentially correct here so again just to illustrate what's going on here when thinking about the compilation setup that we have here。

Is we have some sort of compilation。 So for instance， if I run this command。

 this compiles the actual source code of my C plus plus program。

 these strings are embedded in this program somewhere。

 but what I actually want to do is be able to compile。My CPU program。

So it'll go through some compilation stage， but during this process when the program is actually running。

So， at。Run time。Load。The shader code。Okay， so I'll actually load these strings here or load a file and build a string out of that file that consists of the contents of my vertex shader and my fragment shader and what that saves me from doing is if I only make a change in my GPU code。

 I only have to save that file I don't have to recompile or rebuild this whole main CPP or any other files that I have so with that said now that we understand the objective。

 let's go ahead and write the code and see how this works here。

So what I'm going to go ahead and do here is just create a free function here。

 and I'm just going to call it something like load shader。

 and I'll even give it a really specific name。 I'll give it a name like load shader as string。

 So let's go ahead here and I'm just going to leave this as a free function for now。

 maybe later I'll introduce some abstractions。 but for now。

 let's just go ahead and have load shader as string。😊。

And we can see that it's returning a string type here。

 and I'm just going to read in some file name here， so that'll also be a string。

 We'll pass it in by reference and the file name here。 Okay， so for this。

 I'm just going to be using some really standard C plus plus stuff to just read in a string here。

 I'm going to do this in way here。 so I'll store the string。This will be a the result。

And we could initialize it to empty just to guarantee this resulting。

Shaer program loaded as a single string here。Okay， and then what I'm going to go ahead and do is have my。

Bile that I'm going to read in here， line by line here。And again。

 I'll just initialize that as an empty line here and then the actual input file that I want to ring it。

So this will be an input stream here。So input Fstream。

And I'll just call this my file or something like this， a file name。

 and we want to read in those contents as a string here。And that should do the trick here。Okay。

 so now what I want to go ahead and do is say if my file was successfully open。

 that means if it was found if my file。Dot is open。

Then we'll go ahead and parse or read one line at a time of this file here。

 So while a standard gi line here， my file， So that's the input stream。

 and then we're going to read in each of the lines here。

Then I'm just going to concatenate on my result each of the lines that I'm reading into in this buffer here。

 so that's pretty much it， I'm just going to make it again a really simple and dirty function to read in this file and return a string Now in the instance that I'm maybe be missing some end lines here。

 let me actually go ahead and add an end line here。

 just manually to ensure that we don't have any issues there。

And then if our file was successfully opened， I should of course， close the file。

And then I'm going to want to return the result here。Now again。

 this is sort of the function in one page here and you could do this in many different ways if you want to do a try catch and throw on exception if the file is not found or these types of things you're more than welcome to but again this should do it just fine for us so I think I'm going to need to add in some libraries here。

We're going to need string and we're going to need the F string library here。

 so let's go ahead and give that a compile and just see if this works here。

And I give that a compile Look like I made one mistake here at line 82。

 I'm guessing this should be C underscoreco string。And let's go ahead and give that a compile here。

 oops。and the mistake here see， if you spotted it， I wanted to just pass this in by。Reference here。

 So we avoid making any copies。 and there we go。 Okay。

 so that's our load shader as string function here。

 So where are we going to actually use this function。 Well， again， in our code here。

Let's come down to where we're setting up our graphics pipeline here。

 so here instead I'll make this a little bit larger instead of just directly loading the source code we're going to read in the files here and again I'm going to break this down just to make it very simple for us and I'll just call this the。

Vertex， shader， source。And that's just going to be read in from some file here。

And we'll go ahead and do the same thing with the fragment shader。

So that'll be the fragment shader source。Okay， and now this our code is getting a little bit cleaned up in the sense that well I can get rid of these globals here。

 which is always a good thing， as I mentioned before。

 we're just going to do things in the series kind of dirty just to get things working in the simplest manner and then we'll fix things up so let's go ahead and change this up a little bit here So vertex shader source。

😊，For our first parameter and our fragment shader source for the second parameter。Now， again。

 we need to figure out where these files are going to come from here。

 So what I'm going to go ahead and do is just copy each of these here from our。

Global is here and let's go ahead and move these into their own separate files here。

So let's go ahead and get rid of this here。 I'll go ahead and split my window here。

 And what I'm actually going to do in my directory here is just create a folder for all of my shaders just to keep things organized here。

 So let's go ahead and make it directory here called shaders。 So again。

 you can see that that is just created here next to our C plus plus source here。 Okay。

 so if I go ahead and just create this directory here。

 and I'll just create something called the vert GLsl。😊。

In this window and let's go ahead and just paste these in here。

And I'm just going to have to clean this up a little bit here。Because this is again， just GLSL。

Thatll just allow me to。Edit this。And let's go ahead and do the same thing for our fragment shader。

 let's go ahead and just split this window here， and I'll just call this Fag GL Sl。

And let's go ahead and just。Grab our code here from the fragment shader。

And let's just go ahead and paste it in here。And just clean it up a little bit here。Alright。

 so now that we've got our shaders in here， let's actually make sure that we load them up。 So again。

 where we are doing our load shader as string， we now have our vert shader that's in shaders slash vert GLsl。

😊，And in the fragment shader we will have shaders/fraag。

glsl Okay so let's go ahead and give this a compile and see if this works here。

 maybe there'll be some mistakes， but that's okay and our C++ code is compiling just fine。

 which is a good sign and let's see if our trader code is compiling when I actually run our program。

And in this case well let's see what happens here well I am getting my triangle here。

 I'm getting black here， but it says we have a line here。

 so this is where our actual error logging is being useful in our actual programs here and if we look at this carefully it'll actually give us some sort of line number here and maybe the astute viewer that you folks are notice I have an end line here in my fragment shader here。

😊，So let's go ahead and get rid of this here。And I' was going to carefully scan this to see if I've made any other errors here let's just go ahead and give it a try but the important thing to notice is since there was just an error in this shader。

 I'm not actually going to recompile my code here I'm just going to rerun the program and this time I can see I'm getting my orange triangle So again just to demonstrate the purpose of this here is my triangle here and I don't have to make any change in the c plus plus code which could be a long compilation process。

 but let's go ahead and do something interesting with our fragment shader like make it a red triangle here。

 So I'm going to change the Rrgb values to just be100 and fully opaque in the alpha and then again not recompiling rerunning my program and I can see here that our program is running without making any additional compilation changes So again。

 this is a way to make our code or our workflow very efficient by now just loading our fragment and vertex and any other shaders that we write later as a string from。

😊，A file and pragmatically as a team when you're working with artists and folks who specialize in writing the shader code versus the engine code on the C++ side。

 this again makes sense So folks I hope you enjoyed that lesson it's just a cleaning up our code I hope it also helps you understand just a little bit of the workflow and the separation when using something like openGL of what we're doing the our C++ and GP ourLSL orL shading language if you this lesson make sure you so don't miss lessons and we'll go ahead and see in the next one。



![](img/7f30a3bfb03dc1e935d9b64f75595f2b_4.png)