# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p15 2024-10-09 - CIS 5650 GPU Programming Fall 2024 Lecture 9 (Recitation).zh_en -BV1sRtresE67_p15-

![](img/dcc7079a1397470b36a013494e2983b3_0.png)

So recommend not recommend as much as it's more or less required。

 I mean no JS you need for the project because it's user setting it up on a local web server this is all done for you so all you have to do really is download the project be like NPpM install NPpM run dev and you'll automatically have it in your browser and whenever you make a change to your files and you save them it will refresh the page automatically next recommended browser is Google Chrome because it supports all the web GPU extensions and whatnot that you need and video GPU is not required for this it also has built in debugging and profiling tools and you can use extensions for other more further debugging such as this one called web GPU dev tools which is kind of like render doc for web GPU sort of so feel free to look around try this extension try anything else you might find and if you find something useful post it on Ed to everybody else in C2。

And then for this one we recommend using visual Studio code not visual studio it's easy to configure like alternate syntax highlighting for example。

 because it's like it says JavaScript here but the project is in PpeScr。

 but either way you can do a lot of nice syntax highlighting with BS code and you can also set up winters to catch errors and It know if I mention it here or in the instructions for the project but there's like a nice plugin you can download ticket syntax highlighting for WGSL so that's the tools to use for the project probably JavaScript。

Pally， I feel like I've done the basic JavaScript tutorial like four times over the course of my greatest university。

But if you haven't done it， it's relatively straightforward。

 the part one of the project which makes you just go through and like fill in a couple of blanks should hopefully get you a bit more used to the environment。

With that said， part one， after that naiveix naive render is the forward plus and plus or deferred renderer。

So for forward what you do is often you can draw the seam once for each light and composite them onto a brain bufferer and the knife code that we provide what it does is it checks every light for every fragment so you know if you have like one cubit for every single pixel in that cubit will check against every single light and you can imagine that it gets really slow especially once you have multiple like layers of things and you're checking the lights for fragments behind that are going to get overwritten eventually anyway so you're wasting a lot of work for no reason。

Forward plus optimizes checking each light by only checking the lights in the cluster that the current fragment is in。

 so we only check lights that actually affect this fragment plus or minus a little bit of wiggle。

Right so for the naive render the project does not work when you clone it immediately and that's because we've left a couple parts for you to fill in the blanks like I said to kind of get used to how the project is laid out what you have to do is create and write to the GPU camera buffer which includes the view projection matrix you need to bind it to the pipeline and then update the shaders to actually make use of it so you know when you start off you'll get just a black screen but once you've completed the first minor part you should get these you know fancy colorful lights it will be slow that is to be expected because the next thing you're going to do is make it a lot faster。

Any questions so far？我机换啊。The clusterative themselves。

 they are portions of 3D space that correspond with tiles on the 2D screen。

 it involves the perspective transform， they are not bounding boxes， this is important。

 they are bounding thrust stems。Which look like this and they are not aligned with the scene they are aligned with the camera so when you rotate the camera。

 the bounding thrusts will also move in world space so keep this in mind I will say though that when you tick for intersections with the thrust it's often easier to calculate the access aligned bounding box of the f in view space。

 otherwise you have to do a bunch of complicated stuff to figure out whether it even intersects or not。

 but the actual shape of the cluster is this bounding thrust here， not like a box or anything。Right。

 so when you actually calculate the clusters what you do is that you you have one compute shader that calculates the bounds of the clusters so for each one you calculate it in screen space the 2D and then you calculate the starting depth and the ending depth for this one I think I already got a question earlier that was like how do we find the max depth for that you can like try to programmatically find it from the like scene depth buffer or something but that's a lot of effort so if you want you can just hardcode it or like calculate some value based on how large the senior loading is but hard codinging is probably the easiest solution for that one。

Then you have to convert these into View space coordinates。

 which will involve adding another buffer to your camera uniforms and using that matrix for this calculation and finally store the computed bounding box of your cluster。

Then you have to have a separate task to assign lights to clusters。For this one。

 what you'll do is that。You want to keep track of how many lights are actually in this cluster up to a certain maximum which you can hard code for each light。

 you simply just check whether it intersects with the cluster's bounding box and if it does add it to the cluster and if you hit the maximum then you stop there and finally make sure you store the number of lights that are in this cluster。

This is all stuff that is also written in the shaders themselves and my comments。

 so you'll see the same comments there as well。And this is like a nice representation of what the bounding clusters actually look like in the scene。

 so you can see there's like multiple depths that bound them as well as like the 2D view from the camera to form 3D bounding thrusts for the clusters。

あい。Yeah。So you can see that like different lights with different ra will have will be placing the different clusters depending on like where they are in the scene and how big the clusters are。

Questions on that。Yeah。But。This image， I don't remember exactly。

 but I believe it's that like that the red you know sphere wire sphere is the radius of the light in world space and then the red dots are the clusters which that light affects。

All right， moving on， oh there's more yeah， okay。Then so that's forward plus， which is still nice。

 but you still suffer from the problem of overdrraaw。

 which is you are drawing fragments behind that are going to get overwrittend anyway waste later。

 so you're wasting a lot of work for nothing。What you can do to remedy this is use deferred shading。

 which is you draw each object in the scene two G buffers， which include like the albedo， the normal。

 the position， stuff like that。What this means is that the initial rendering pass is really simple because all you have to do is output to a texture and later on you read from those textures to then do the final rendering。

And this means that for each there's only one fragment for each pixel as opposed to potentially multiple if you have a seen with a lot of depth。

Right the light plus string can be pretty much exactly the same as forward plus and the way the base code is set up you can use the same exact compute shaders so once you've done if for the forward plus there's no need to really go and updated and yeah like I said it mitigates issue with overdraw so you have your albedo buffer。

 your depth buffer from which you can reconstruct the row position and your surface normals and with just those three textures you can basically render the entire scene。

Right， so with that， this is more for reference for later。

 but I'll just go show you in the base code itself how this is all laid out。Let me pull this up oop。

Okay， and let me make sure the screen share is correct also。That should be it。你呀。😔，嗯。O。All right， so。

In the base code， mainly you're going to want to look at just the source folder here。

 everything else is like boilerplate stuff or like no JS or like the web server packageers that we're using or whatever。

Oh， I should turn that off one second。Ho it's going。I'll just mut the volume give me one。なて。And。

Of with you anyways， so source。This is the main entry point。

 this is where like it'll get called from your index at HTML or whatever。

You probably will not need to mess with anything in here I mean all it's really doing is like setting up web GPPU loading the scene。

 adding the lights in the camera and the reason that lights and camera are two separate classes here is that it's a lot easier to reuse them between multiple vendors because like the camera logic is exactly the same for all the vendors it doesn't change at all。

It'll add like GUI for controlling drawing the number of lights so if you want to add more options to your GUI this is the place to do so right here it sets up a stage and there's like a little switch statement here which switches between the three renders so you know naive is almost fully implemented you just have to add the last little bit forward plus and clustered are pretty much empty so that's up to you to figure out。

And then the renderers themselves are stored under this renders tab here。

 or I guess the base class is under the source folder。Oh， it doesn't like all the。Okay。

 ignore the errors， it should work fine if you do it on yours， probably。

 although'll detect this outs。Yeah， okay， so this is the base render class down here。There。

And all three of the renders extend this class， which is nice because like it has all the common stuff that you would need like the scene。

 the lights， the camera， or whatever， and there is this on frame method。Which runs every frame。

 as the name says。This draw call right in the middle here that's the abstract function which is the main thing you're going to have to implement for each render the rest of the stuff is just weatherplate to like update the camera update the lights there's like a computer that moves around the lights which is already there for you。

But this draw method is you know abstract and will have to be implemented by subclasses so if we go to like the naive render for example。

 this is mostly done like I said what it does is that in the constructor it sets up a bunch of things like bind group layouts or you pipeline layouts or whatever。

And you'll see there's comments like to do dash， one point。

 whatever that tell you where to go to finish the naive render and the instructions also mentioned this。

And if you go down to here in the draw function， like Ka mentioned in the guess director will make like a command encoder。

 make a render pass with the render pass description。

And this scene iterate function here is one that you don't really have to mess with。

 but what it does is it goes through all of the meshes in the scene and assigns the correct bind group for like the material and the model matrix and everything。

 and then actually draws the thing。The majority of your work is going to be done like right in the middle here for all the renders。

So that's the naive render and once you go to the instructions and do all the tus。

 it should become a lot clearer how this works。Additionally。

 the last important part is probably the shaders tab。

 this is where all the WGSL shaders are actually stored。

And this shaders that T file is where you can load all of them。

 there's some stuff set up on here to do shader preprocessing so you can actually use like JavaScript constants within your shaders themselves。

And you can there's like a common shader here， which will get prepened to every shader that you load so you can share like the same strips and whatever definitions across all your shaders you will have to of course update some of this when you do your work。

Let's see。 and then。An example of shader pre processing， see if I can finally you' here。

 So you see this。Dollar sign curarly brackets， Vine group model。

What that does is it accesses this constant here bind group model。

 so this means that you can make sure that all of your shaders are using the exact same bind group for the model without having to use some kind of like magic constant and if you ever want to change it all you have to do is change it right here。

These are declared in a bit of a strange way like in this constant like object here because otherwise when you build it it gets like minified and all the names gets screwed up so just just keep everything within that constants thing if you want to use it in a shader。

嗯。Yeah， so that is that。I think the last thing here to go over is probably under the stage tab you can I guess camera and lights are gonna be important because lights is where you do the light clustering logic and camera you may have to add more matrices and stuff as uniforms so in the camera as part of the setup to make the naive render word you'll have to add like a buffer into this camera uniform thing here this is important because we don't want to upload each of our uniforms as individual buffers of the GPU because then you have to make like multiple update calls every frame that's a waste of effort when instead you can just pack them all into one buffer upload that once and read from it like a str so what happens here is that we have an array buffer which is just like bike data of 16 bytes or sorry 64 bytes and you can make a float view on it to write floats to this array buffer so you know you can write 16 floats for one matrix and the next 16 floats could be another matrix and so on and you can even throw in some like un or whatever if you need for example screen size。

Later on， so you'll add one matrix into here for the naive。

 which is required and you will probably need to add more later on for other matrices as well。

And I believe in the common。Yeah， so like just make sure that the layout of your array matches the layout of the struct here so that the data gets copied over exactly。

And then in the lights class here。This is there's already some stuff set up in here to like make the lights move around using a compute shader。

 so when you do your clustering compute shader that might be useful to look at it's all in clustering that not there sorry move lights that CS so you can see there's an example of like this is like the equivalent of a coa kernel you can see this as an example of how to launch a like a large work group or whatever when you do your clustering shader。

But in the lights itself， I believe the major part you'll want to work on is this do light clustering method。

This is where you'll like set up all the compute passes and whatever and run the actual compute shader and this is nice because since it's in the lights Plus you can easily reuse this in both the forward plus and the cluster deferred render because the logic should be like exactly the same。

And I think one last thing I wanted to mention is that this naive vertex shader is useful。

 not only for the naive render， but also for the other two。

 because like the actual rendering of the scene vertices is the same for all three of them it's like what you do with the fragment data afterwards it's different so you can feel free to reuse this for all three of the renders or make your own if you want to do something。

I think that's it for the base code， any questions and all that。这说我好。Stuffer。

It's it's in the instruction that you got to do is like install and run divb I think the reason there's errors is for I forgot to like save some dependencies or something。

 but I will double check this and update the instructions after if there's any anybody have any questions on NPM node whatever in general。

Okay， and if you ever do in the future， feel free to ask on Ed or in office hours or whatever。Right。

 so back to this， yeah and then feel free to redo this again later if you want。

 but it's pretty much the same stuff as I just said just like in a text format。Right。

 tips and tricks。Point lights are the only required light type for this assignment you can feel free to add more if you want that will of course change how the cluster string logic is done so that's on you to figure out Yeah of course it's not you can do it and you get you'll get the G bufferer only requires three basic buffers which are the color the depth and the normal。

You don't need to use a scene that， like I said， for calculating the maximum depth of clusters。

 you can just hard code it or load it on the scene if you want。

You can reuse the naive per shader for multiple pipelines。

 one important thing is this memory alignment calculator already to go。B。

This thing so the way that memory is laid out might not match what you expect if， for example。

 I worked just with like language struck test A V saw like a V3 F and then like another like V2 or something。

Oops can't do that。And then if you were to process this。

 you will see that it's not like tightly packed there's actually one like four bytes of padding there right off for the back three before this next one comes in so if you're facing memory alignment issues this thing is very helpful for figuring that out。

你冇识要为主关但啲货嘛。Essentially the same thing that we。But also。

 if you' like throwing like a float here in F32 then it'll it'll。Pack the floating in there。

 but like。It just might not match what you expect， so make sure to use this if you ever confused it。

Questions。六头。嗯。Right。Right okay extra credit for this project you can implement some post processing effects if you've done4 safety this is like homework work kind of stuff。

 you can do bloom， you can do tune shading whatever you want。

 just check the instructions for more information on that one。

You can optimize the Jeep buffer to try to reduce the amount of memory required per pixel。

You can pack values together into V fours， you can use two component normals because normals always up to always are a length of one。

 you only really need two other components and you can reconstruct the third and if you want to get really crazy with it。

 you can useoctahedron normal encoding which lets you pack an entire normal into one UN 32。

And that's a great way to like optimize your G buffers and then of course you can quantize values by packing them into smaller data types like I just said and you can reduce the number of properties pass via the G buffer。

 for example， there's no need to pass in the world position you can just reconstruct that using the depth and some of the camera matrices so if you do this and do it well you'll get extra for that as well。

But one way to pack it even further， which I am not too knowledgeable above but is possible with family is using a visibility buffer。

 which is you store the object ID and the triangle ID of your current hit in a single integer and you bind like the vertex and index buffers in the like shading stage and you read from them using the current hit information and you know you calculate like the world positions of the triangle vertices。

 you calculate the very centric coordinates you basically do what all the hardware is doing for you like manually and the reason for this is that you can really drastically decrease the amount of memory required per fragment so this is also an option for extracurex。

And then like I mentioned previously。What other thing I mentioned。Oh yeah， other light types。

 you can also that for extra credit。I don't believe we have any instructions but。You can do that。

 so just ask to add if you need clarification。Yeah， I would expand that and say that。

Vi is like the first four refuge youth project here new industry in a few like fund projects。

People are similar to how you clean the fast where things are open ended。

 the board is what we want you to do， but it's very open ended subject we want to do some field that we are more than working to。

Especially with the benefit of perr， the band pretty crazy with it。

So the community to do and just posted time。Yeah， so like nice to say this is a new project。

 I finished a baseball maybe like a week ago or something so if there's any issues with it。

 if you have any ideas or anything， just let us know and we'll look at it。

But I believe that is it for this recitation， for any final questions？On homework four。Yeah。

 you any required or you just just like following stuff no it's just extra。Yeah， after day。You know。

 it's pretty good because it's actually my birthday。

 which is funny that I'm giving a lecture on my birthday， but it was pretty good thing。Yeah。

 so I after for someone to go like watch a movie。不行。The wild robot， I heard the things about it。

It was like two of my friends it used to be pups at picture they said it was like really good。

 so I' like no， I got to watch it。It's got to be good。Other questions？

Hopefully after fact there is a this。This will still be a very good product， but not as intense。

Again， do you think of strategy because you don't want to。我你咁乜要嚟个安过嚟。It's not really regret driving。

Stop with the forward render and I guess anything stop with。

I will say I really liked working with WebGPU to set up this project。

 so I hope you guys enjoy working on it too I feel like it's a lot less annoying than a lot of graphics APIs out there so you know hopefully it's the same experience for you。

I a thinkish about yeah so。I think for those of people who've done graphic projects in the part。



![](img/dcc7079a1397470b36a013494e2983b3_2.png)

You can put this one there no no yeah， just one to get。



![](img/dcc7079a1397470b36a013494e2983b3_4.png)

又把这个。You can it， you can send it link to your parents at hand。



![](img/dcc7079a1397470b36a013494e2983b3_6.png)

Belie if you go here。Yeah， once you fork this， it should be relatively simple to set up does instructions on here here。

Yeah， if you go to GitHub pages set up in the instructions， if you just follow these steps。

 then every time you make a new commit， it'll automatically deploy to this website and you can just send it to wherever you like。

啊嗯。

![](img/dcc7079a1397470b36a013494e2983b3_8.png)

I think I don't know if it's still good。

![](img/dcc7079a1397470b36a013494e2983b3_10.png)

对。And I might be gone because I made it beach check。



![](img/dcc7079a1397470b36a013494e2983b3_12.png)

Still。Yeah， that's true。

![](img/dcc7079a1397470b36a013494e2983b3_14.png)

哦。Yeah。It might just take a minute to load。Yeah， so here。It's like slow as hell for some reason。

So did you about equipment on what hardware and what operating system you're in。

Being connected with follow helps。It is supposed to be faster than this。Well。

 you can see what when I put at the nightive， it's a slideshow so like I think it's just because it's screen sharing on my like。

MaybeNo， I should be yeah I well， I tested this on my desktop at home and it guess like 144 Fps easy with like cluster deferred so take this to the grandaw。

Yeah。I mean， the idea of like clustering lights and checking certain lights based on like where you're on the scene general might be applicable to you know ray tracing as well。

 but。This specific project is pretty much only restization applicable。你你周唔话。发四四过去。

For future changes and I。Thank you the three subjects from that。



![](img/dcc7079a1397470b36a013494e2983b3_16.png)

Yeah。We may nott do policy。I will say also one random note the lights in here。

 if you implemented point lights in a regular like raizer before。

 it's probably just like one over r squared follow up but these ones are the specific follow up function that's using so that the light contribution is like。

Contained entirely within the light radius， that means that the light can never affect things outside its radius。

 you'll never get like issues with。Like weird borders between clusters and all as long as you have enough maximum lights per clusters。

 so if it doesn't look exactly as you think a light should look。

 just keep these functions in mind in the comment file。

 there's this range of penuation thing which is a bit different than like one over R squared just random mode。



![](img/dcc7079a1397470b36a013494e2983b3_18.png)

Any other questions？Thank right。I will take a look at why there were errors in this thing and fix that in the instructionss。



![](img/dcc7079a1397470b36a013494e2983b3_20.png)

![](img/dcc7079a1397470b36a013494e2983b3_21.png)