# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p36 P36 OpenGL -Episode 35- Starting Application and Mesh Abstraction Refactor -BV1pTvFz3Eqh_p36-

![](img/8188d4e7ababd21717cfce1a905d7ecb_0.png)

Hey， what's going on， folks， It's Mike here。 and welcome back to the modern OpengL series。

 In today's lesson， we're gonna be taking a look at starting to abstract our code so that we can have multiple objects because well graphics application or our game or something is' is gonna be much much more fun if we can have lots of objects moving around and how we do this is going be sort of important for how we abstract upon opengL so that we can have separate vertex buffers or vertex array objects and so on for each individual object。

 So I'm going to go with the simplest abstraction possible as we start setting this up。

 And what this means is we're gonna want to clean our application up a little bit getting rid of some global variables and instead of having objects that we can instantiate。

 So with that said we'll go ahead and get started here but just a quick reminder that this is available on courses if you want to track your progress otherwise for this series if you haven't been following along the lessons。

 But with that said let's go ahead to the code and just give you a brief recap of what we've got。

 So our source file currently consists of the main the G which consists of all the opengL functions or rather。

😊。

![](img/8188d4e7ababd21717cfce1a905d7ecb_2.png)

Again， what Gd does is give us the prototype of all those functions。 And then our camera class。

 which manipulates the matrix here。 So let's just briefly again， look at the source and the。😊。

Camera CPP here and actually whenever we're looking at these files。

 it's always best to look at the header file here just to get a brief recap here。

 we've got a little bit of mouse look moving around and then we store some things in our view matrix here like the I view direction and up vector the old mouse position was used for things like mouse look so that was a little review on that and then in our code here last episode we did a little bit of cleanup here but as always I just want to give you a little bit of an idea of what's going on the program so we need some way to initialize our basic program and that is the application side of our program that's the stuff on the CPU setting up the SDL window or GLFW。

 whatever framework we're using for instance， the vertex specification is we're setting up our geometry Now this is what we're gonna want to do on a per object basis because this is basically the portion of our code where we're shipping geometry data X Y and Z points in a 3D。

😊，Application to the GPU and setting up those buffers we set up our graphics pipeline which says。

 well how do we actually process that geometry so doing the transformations and the lighting and the filling in each of the fragments in our vertex specification and then we have our main loop which is the logic of saying draw our actual geometry and position things this way or set open GL state in some way to render things and then of course we've got our cleanup function So where we're going to want to focus today is kind of cleaning up this abstraction with how we initialize our program and our vertex specification So let's go ahead to the top of our code here。

😊，And just start exploring and I'll go ahead and compile this you can see the compilation for the Linux here and let's just do a brief reminder on what our application looks like and I'll bring the window in here and we've got one slowly rotating cube here and I can use the arrow keys in the mouse look to kind of move around it here okay and then I can hit escape now to exit okay so I'm going to move that off to the side here and we'll abstract away some of those details here。

Okay， so as far as our applications concerned， that's this kind of stuff here like the screen dimensions and so on。

 So the simplest thing that we can start to do to abstract waste some of these values is just wrap them in a struct。

 In fact， we've had these global variables exist for a long time for simplicity。

 but what I'm going to do here is put them in a little application struct here。😊。

And for now I'm going to again， try to use as few global variables and so on。

 but as few fancy programming features in case you're following along in a different language on this series here。

 so let's just kind of nicely indent this here。I'm going to get rid of G here and replace these with M because they are now member variables here and again I like doing that because it makes it a little bit easier if you're using Intelense to just hit M and then tab spaces I know folks don't like because in your git dis become kind of messy but again it's a little bit more clear to read here。

And let's go ahead and add our main loop flag in here。And again， change this to a member。

And let's go ahead and just line things up nicely。And we can keep our comments here， oops。

There we are， so we're going to do a little bit of refactoring here just to get things in a nice state。

Overall。What we'll probably want to do here？As far as our。keep all of our comments together。

The the shaders， we would probably want to also have these maybe as part of the application。

 maybe a resource manager of some sort here for now I am just going move this all into our app here okay so we'll sort of start managing that soon enough in practice this can probably start going into again a shader manager class and we can move some of our shader code into its own file for instance。

 again， that's what we're going to slowly do here Now this stuff here is all what's related to setting up a mesh or 3D object here Okay。

 so our actual openGL object。 So let's go ahead and create astruct for that。

I'm just going to call it object 3D or even better， let's just call it a mesh 3D。And again。

 we're just going to do the same exact structure here where we're going to effectively just。

Make these member variables here。And we'll continue moving on from there， okay？

And then as part of our mesh right， we have the different offsets now if we're going to have multiple objects。

 we want to have different ways to rotate them。So let's go ahead and set this up so per object we' have some sort of transform where we can set the offset or the translation rather in one dimension is what we currently have here。

 rotate and scale our objects Now for our camera I'm going to say that we're just going to have one camera and we'll go ahead and put that into the app class here okay。

Let'sGo ahead and separate that out here。And let's go ahead and see what else we got。 Okay。

 so those are our our globals that we'll now have。R in app。

 I'm just going to call it G app for a global application。Let's go ahead and set that up here。

And then let's go ahead and have a mesh 3D。It's going call it mesh one。

And another mesh 3D G mesh 2 here， let's continue with the global prefix here。Okay。

 so that's the basic idea here。 Let's go ahead and get that all into view。

 So basically all I've done is wrap some things into the app here。And again。

 we could separate these out into separate files， but I'm going to avoid that for now。

Let's go ahead and just keep these here just because it's a little bit easier for you to fall along for now。

 although I will start separating things， there will become a point where we need to do that very。

 very soon。 It'll just get too wild otherwise Okay， so let's go ahead and do this here。

And for folks following along in other languages， it's kind of nice to just see everything， Okay。

 so there's our app。Here is our mesh 3D， and let's also。Clean these up a little bit。

 Now I still like the U prefix that it's a uniform。

So maybe we'll keep something like that here and we'll have to be careful and update all of our uniforms and so on so anyways。

 let's go ahead and start with this。😊，And let's not create a second mesh just yet here。

 let's make sure that our program's running here。Now we have some of these functions here like。

Air handling and checking errors and so on these again could go into some sort of utility function again we could do those things likewise these sorts of functions could go into some sort of shader class for instance where you can have these as member functions or free functions that are friends to that class if you're in C++ and anyway so those are some of the different ideas that we have here。

So let's go ahead and start thinking a little bit here about our program here。

 So let's see what changes we need to make here。 So instead of having our G graphics pipeline。

 what we have， we should have G app do M and that should be。Graphics， let's see。

Pipline Shar program here。 that should be our global here。Let's see something like that。嗯。

Traffics pipeline。Let's see if we define that here。AhI did not put an M in front of it。

Because it's a member function， some folks put underscores。Again， whatever your preference is。

 that's fine。Okay， so let's go ahead and now set that up here。All right。

 so we're just going to have to do this a few times and that's the reason I'm just making this you know a global variable can make things easy for us to get started。

 so it's effectively the same thing， but we've grouped a few variables together which makes things nice to work with。

😊，Let's see here's our application window， which we also need to set up here。

 G app dot which should be M。Let's just make sure that is the right thing and graphics application window y。

And then we're going to set the width and the height。Appropriately。To the M or the G app。

End the screen with。G app。And screen height。And then we want to check some things here。 Now， again。

 these are the types of things here。Where。How we want to handle this， for instance， if you're in C++。

 this could be a member function that is part of the app structure here。

RightThis could just be a member function here could be part of the construct， for instance。

 that way we don't have to do all this you know sort of indirect here with GAP dot something we could make that a free function in which you pass in an app and then you set some of the parameters and then it'll set up this class here or thestruct rather this data type or。

😊，We could just pass in again as a free function and sort of set things up with a pointer or a reference up to you how you want to set this up。

 I'm going to again slowly move this forward as we need here。And again。

 maybe we'll do another refactoring here， but slow and steady here。And let's do the。G app。

m opengo contextex。For the。G app dot。Pmographics application。And again。

 I might change my mind about this later on。But I want to make sure I do it for the right reason。

 so let's just keep it as simple as possible。Okay， now our vertex specification here。

And how I want to handle this。This one I might want to actually do something a little bit interesting。

 for instance， let's go ahead and do it in a C like way。

 or I'm going to pass in a pointer to our mesh here。😊。

And let's label it here and I will populate this properly for now。 so let's see here so I want to。

Set up。And we could clean this up a little bit here， I think this is okay though。

 let's just go ahead and do。This is going to be the mesh。And it's a pointer vertex array object。

 okay， so because I'm passing in this pointer here。And let's recall what our。From our mesh here。

 mesh 3D， yeah， we've got these member variables here that we want to set here okay。

So let's go back here。Let's see here。Let's see in the vertex specification。Okay。

 so let's go ahead and。Set this up here。 let's see here。 This is a pointer。 So yeah。

 I want to set the。And vertex array object。And I want to take the address of whatever that value is okay。

Let's see here， mesh。Mesh。Andvertex rough array。Because where we're heading in this series is we are going to。

Start。Adding multiple objects in just to make our scenes a little bit more interesting here。

Let's see you got the vertex data and so on and then you know the next thing。

 one of the next things to abstract is going to be actually to take this vertex data here。

In our little mesh object to be able to populate this with whatever we want。

 but for now let's get it working so that we have the same sort of setup as before。

Let's see here's our index buffer data， so again， we will populate。Alright mesh。The next buffer。

And also bind our mesh index next buffer object。With an M in front of it。

To make sure that we're getting the correct member。Mesh， let's see here。

This is just the index buffer data， so that's okay。And let's see here， Okay。

 so I think we should be okay there， minus anything that I've forgotten。 and again。

 this stuff will abstract away later as needed。Okay， let's start working on our predraw。Gy app。

Screen with。Yeah。height。And then our app here。Let's go back here there we are。Yeah。And again。

 slow and steady Now these rotates here that we're doing ahead of time。

 right these are going to be a part of our。呃，mesh。we call G mesh one。ああ。Rotate。Yeah。

 that's a little bit nasty rotation here， G mesh one。Msh1 M。Rotate。

And let's just go ahead and keep doing these transformations。 I'm going to do it one at a time here。

Even though I know it's a little bit slow here， but。

I want to make sure we don't speed up anytime we're doing refactors in this particular series here。

MU scale。Okay， now this I'm going to want to just。Copy and paste here。あ。Yeah。How about this？呃。

Let's copy this。Up in a line， paste it in。S equals this。And let's call this like a uniform。scaleale。

That's a better name for it。You knowform scale。Uniform scale。Okay， let's see here。

And then what we want to do here now nothing's changed in our shaders yet as far as this goes。

 because we're going to use the same shader pipeline once we have multiple objects。

 at least to get started here。So let's go ahead and。Continue moving along here。

And our camera is now part of our app here。Okay， so we wan to do that。From the app。The camera。

And from the app， also get the pipeline set up here。This looks good to me。

Let's see here our screen with is from the app now。And our projection matrix。

 we're going to send this in from again， the G app。And that looks pretty good to me here。 Okay。

 now when we're going to draw， this is gonna be from。Our global mesh one here。Mash one。

And we bind to its array object。And let's see here。

And I think we're already using the correct program wherever I have set that up in the predrawwl。

 right？I should have done GLU's program for our app the one pipeline we have Now we might want to do this the trick is here if you want to be super optimal is what you want to do is per for all the objects that are using the same pipeline you don't want to keep sort of changing them okay so that's just something to keep in mind that we might want to fix later on。

And I see that I missed a。Offet here for our mesh。Thatch one。Okay。

 let's see here if I missed anything else here， I got our rotate and I got our scales， okay。

So let's go ahead and go through this。And let's see we got to fix our input again。

 big refactoring today。Let's see if we get our camera， which is also part of our app。

And we're going to have to make that refactoring a couple times here。Not too bad。Okay。

 and then these state here for quitting。Quit。Hopefully I rename some of those things。

Let's see in our event loop， okay， great。Let's get going now in our main loop。Again， from the app。

And quit。And we got to set our for our mouse look。And that might be something that you want to change around a little bit。

 meaning if you want to be able to turn on and off this mouse look mode。

 there's some different things that you could do here。Let's see here at G。だね。Graics application。

 okay。Okay， and then finally， the cleanup。There we go。And we want to clean up for our mesh one。

 the vertex buffer。And the。Mesh2。And the， let's see here， delete our program that's in the app here。

Now again， these are very obvious use cases for having a destructor per object and again。

We probably want to write a function here， in fact， I think it's time。 Well， let me again。

 I can refactor this again if if you want to， we could jump into the C plus plus。

 but I'm sort of intentionally doing this in a C style for now to match Open GL。

 but let's see what we get there。 Let's see how many mistakes we've made。If any。

Let's see how we did here。cross our fingers， give it a compile and yeah we got a bunch of things here。

 so we'll just start fixing some of these 520。 this is part of the GAP。M quit。Let's see 598。

 we miss this one here， G。m。applicationpplication。Line 602。I put mesh number two。

 got ahead of myself。And then in our vertex specification， I did not pass in at line 623 R G mesh1。

Okay because we wanted to pass a pointer to that， I believe I passing as a pointer because we want modify it so I need to pass in the address。

 let's see how we're doing there。Line 325。Let's see， yes。

 we don't have a G vertex array object anymore， we just have the mesh。That we're modifying and again。

 our vertex specification is the first sort of function that we're modifying here。

 we're saying we want to pass in any sort of mesh object here and be able to populate it。

Let's see what else we got here。Line 325， something else is also broken here， let's see。

InV conversion， a pointer。我知。And。Let's see what it's done actually， I don't need the address there。

Because again， that's just going to dereference our mesh and find this field here and give us the value here。

Let's try to compile again。AndClo， four，7，9。Let's see here， what did we do here， geodrral elements？

Expected prehey before numeric constant or just got rid of a comma accidentally。And line 566。

This is again part of G app。And graphics application。

 I'll scroll through this again once we get it working since we did a big refactoring here。

 but I should be able to run my program now。 let's see what happens。 Here it is。

 I move my mouse around。 Yep， still got my object， still got my camera。😊。

And we can move around here Okay， so we're back at where we started here All right。

 but what progress have we made， let's go ahead and do a quick little review here since we did a lot of code here。

 the main thing that we did was we were able to gather everything into our abstract structure here。😊。

Now the advantage of this one is again， even if you are going have a bunch of global variables。

 it's much nicer for instance， to be able to just wrap them into a structure。

 So if you must have globals that's a really good practice to do and we fully haven't dove into like an object oriented type of thing here which we want to be a little bit careful with especially in games we don't have to do that so again I'm going to be kind of careful even though this is a C++ series how we do things but anyways we have everything in the Gap here and then we have our mesh here which we also have available now we don't really have a good way right now to have multiple meshes and transform them。

 we're gonna to build up to that slowly but now we have this mesh structure here so now we just have all of our things like the vertex array object which basically tells us what's the structure of the geometric data so you can go ahead and watch the video on vertex array objects if you need help with that that's tell us how is our mesh structured。

 is it made up of color attributes and position attributes's a normal。

and all that information so that's what that's binding the state the vertex buffer object is the actual information so per mesh 3D we can now have objects with different positions and colors and whatever the vertex data is and then if we have an index buffer to draw our object we have that stored as well and you might want a way to be able to toggle between is this mesh index or not right so we can add different state and so on right now the only state we have is the offsets。

 rotations and scales again which is totally fine here。Okay。

 so we have our mesh here so some of these functions like our air handling didn't change。

 those are just dealing with openGL stuff， our shader functions haven't changed。

 although this kind of stuff could move out of the program here again。

 we're just compiling the shaders and the types by taking in the source code there。

We're able to create our shader programs。 And then now for our app， we have the graphics pipeline。

 and we're gonna to be able to create multiple graphics pipelines now。

 and we could store them in the app or some sort of shader manager。 Okay， so nothing's changed there。

 Now when we initialize our program， this is initializing our app。 So again。

 maybe we would want to make this a construct。 In fact。

 it's probably worth doing same sort of design we did here。

 with our vertex specification of of just passing in the app here。 In fact。

 I like that a little bit better here。 So let let's go ahead and make that。😊。

Structure I'll change here。Again， that way we don't have to。Do all these GAP calls。

 It just makes things a little bit easier。 And if you want to put this into your construct， you can。

 let's just go ahead and do app。Yes， I sorry， little overviewfactoring here。

That's just going to be the app。Sreeen with。In height。Yeah， much， much cleaner here。

And set up the context。 So again， these were just the changes here and you get to see them for a second time here。

ICreate the contact for the specific window。Nice little review to the stuff we've done in prior lessons。

And that should do the trick here。 Okay， let's just make sure that compiled there will be one error because I need to pass in the GAP for initialize program。

 but that's fine。We'll get to that again just reviewing our changes the mesh we did the same thing。

 we're able to pass in any mesh， it's always going to populate it with this vertex data for now and always going to set up the vertex buffers but in theory we can set up multiple objects at this stage here and it's always going to be the same index buffer strategy for the mesh that we set up so let's keep scrolling through here。

Our predraw looks pretty similar， except we're gathering from the app to set up the different state for OpenGL。

 the viewport for how large our window is。😊，And then for our mesh。

 which we've just got one right now， we set the individual rotate values and so on so you can imagine now that we could have a giant for each loop for all of our objects that's doing things like setting up the rotation。

 the model matrix， the view matrix for that mesh and so on Okay so that was the idea there。😊。

If we scroll down here to our draw function we。Currently are just again drawing one mesh。

 but we set up its vertex array object which stores all of that state。

 what vertex buffer object are we bound to， what index buffer are we bound to and again how the vertex attributebute should be looked at whether we have things like color position and so on and that's the basic idea here and then not too much change from our input again this could be something that's part of the actual appstruct but I'm just keeping it separate for now。

 again we could pass an app pointer around if we want to do things sort of C style and that would you be fine here but for now we just have the GAP here So yeah we kind of maybe want to decide if we want to go all in on that strategy or not for the initialization I like it maybe we'll refactor that later。

All right， then we have our main loop here。And then let go ahead and and then we have our cleanup functions again some of these。

 since we have this abstraction for a new mesh now could go into the mesh deor like this could also go into our or these two particular things could go into our。

😊，App deor as well for destroying the window in the context， quitting SDL and so on。 Okay， all right。

 so let's go ahead and initialize our program with the correct application。

 let's go ahead and compile it one more time。And let's go ahead and give this another run。

One more time， just to make sure that everything's working。

 I'll bring the window down for my second monitor， and there we are。

Working like a charm here and our program is starting to get organized。 So not too bad。

 We're coming up with an abstraction here。 It is 600 lines with lots of comments。

 but maybe 300 or so here。 but pretty soon we'll be able to have multiple objects and so on。

 So anyways， folks， I hope you enjoyed that lesson。

 hope you enjoyed following along and are basically what we're heading is we want to talk about things like having multiple objects in this series。

 how to make sure that the objects render correctly one in front of the other with a depth test and the Z buffer。

 So we'll get to all that fun stuff。 and then very。

 very soon you'll see that Open GL ramps up very quickly in the cool stuff that we can do by adding textures and lights and so on。

 but we want the proper abstraction so we give our a nice playground to play with。 Anyways， folks。

 thanks for your time attention。 I'll look forward to seeing you in the next one。😊。



![](img/8188d4e7ababd21717cfce1a905d7ecb_4.png)