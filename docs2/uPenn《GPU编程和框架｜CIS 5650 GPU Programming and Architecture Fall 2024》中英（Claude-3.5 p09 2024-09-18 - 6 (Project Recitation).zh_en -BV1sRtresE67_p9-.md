# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p09 2024-09-18 - 6 (Project Recitation).zh_en -BV1sRtresE67_p9-

![](img/7e218226f4567b321e7daea6bea6976b_0.png)

Okay。All right， hello everybody， I'm Aditia hello， yes， very good I'm Adia， some of you may know me。

 some of you may not doesn't matter I'm going to be doing the project dereciitation today for the Kuta path tracer。

😊，So let's just get right into it。This is that。yeah there we go okay so agenda for today first we'll start with path tracing basics I know a lot of you may have already taken 461 so this will mostly review but it's always good to go over the basics once again we'll talk about GPU implementation specifically including general considerations and then a project based code tour we will do extra features these are extra credit things which are required up to a certain point including physically based materials。

 acceleration structures， denoising etc and then we'll have a gallery at the end of past student work that you might be inspired by。

So first path tracing basics， what the heck is path tracing。

 well in the real world light comes from light sources such as the lamps in this room or the sun in the sky or whatever。

 and then it bounces around all sorts of walls and materials and things until it eventually reaches your eye or a camera and the color of the light is determined by what it hits and you know what it scatters through and all sorts of things。

However， we do this in reverse in path tra because if we simulated every single path of light that came out of the light。

 then a very small fraction then would even hit the camera in the first place。

 so we'll be wasting a lot of power for no reason， instead we shoot rays from the camera itself。

We bounce them around the scene， like in the bottom right。

 you can see it's bouncing on like a chromroe teapot or a glass teapot or like the walls or some cloud in the sky。

And then they hit light sources， and that's how we can determine the final color of each pixel in our scene。

So light transport is calculated using our favoriteed equation， the rendering equation。

 a lot of you have probably already seen this before。

 a lot of terms in here so we'll go through each one of them briefly LO is the outgoing raddiance in the direction omega O this is just like the color of the light and the intensity of the light in that direction。

😊，LE is the emitted radiant， generally this is zero for normal materials， but for like lights。

 for example， it'll be greater than zero because they are emiting light all the time。

There is the integral over the hemisphere aligned to the surface normal。

 the surface normal is just perpendicular to the surface。

 so on this table it would be like a hemisphere that is just pointed straight up。

Then there is the incoming radiance on the direction omega I。

And the bidirectional scattering distribution function， VSDF， which is。

 we'll go over this in the next slide， but it's dependent on the input and the output direction and it determines the way that the light's color changes as it bounces。

That's here。Yesや， yeah，や， yeah。Because all these directions are also like unit vectors do so because we're integrating over incoming directions and they're all just unit directions yeah。

And then Co data term accounts for the fact that surfaces receive less light at glancing angles。

 and this is called Lambert's cosine law。Yeah okay so what the heck is a BSDF well it defines how light reflects off of or transmits through a surface。

 it takes in the incoming direction and the outgoing direction so it's dependent on both directions and it usually also depends on the surface normal everything this world can be modeled using a BSDF just matters how complex it is we'll go over some examples of these in a bit later a light as well。

The terminology is not super well defined， so you might hear that the word BSDF is often used to refer to any be something BF。

 whether it be BRDF or reflection off of the surface or BTDF for transmission through a surface like glass or something。

 so just keep that in mind when you hear the word BSDF。Here's an example of one。

 this is a diffuse material probably the most common example。

 essentially it reflects uniformly in all directions， but the cosline terms still apply。

 so you can see at the top right that as it reflects at more glancing angles there's less light being reflected。

Examples include unfinished wood or like concrete or chalk。

And then there's some examples down here of。Just diffuse materials， even this is a diffuse material。

 but maybe some other stuff on it。Then we have specular reflection。

 this is probably the simplest one， it's just a mirror。

 it bounces the ray exactly in the opposite direction that came in or like reflected around the surface normal。

 so this is just just the mirror， very， very nice。And you can also have a color that tints the ray。

 so you could have like a blue mirror that makes every incoming ray tinted blue as it bounces out。

This is often used in conjunction with a refraction BTDF。

 so this one is now transmitting through the material what this does is that as it transmits through the material it will change direction depending on the index of refraction。

 which is an innate property of materials。It's calculated using Snell's law。

 it's a relatively simple law， you can click the link to find out more。

It can be combined with specular reflection， like I said。

 to make glass like materials such as the example at the bottom right from my pass tracer from last year。

 very simple glass ball in a cornnell box。Accurate implementation of this has to consider finall effects。

 which essentially means that the light transmitted and reflected depends on the angle of incidence。

And you can look this up again in like PBt or any resource that's out there。But of course。

 computationally integrating over every single path。

 even if it's coming from the camera first is impossible because there's infinitely many such paths。

 so we need some way of estimating the final value and the way we do that is we use Monte Carlo estimation。

 which involves taking a large amount of samples and then averaging them。

This is a little nice little function that kind of explains it F of x is the function to be integrated in this case。

 n is the number of samples you're taking。X1 through xn are the samples themselves。

And P of X is a probability distribution from which these samples are drawn。

And as you take more of these samples， the estimator value will approach the actual true integral value。

And fun fact， this is named after the Monte Carlo Caino in Monaco where I won 13 euros in the spring。

 very very nice place， you have a chance go check it out it's very fancy。

I think it was like the creators like uncle was a big gambler。

 and so he like named it after him or something I don't remember exactly。

 but there's like a funny story behind it。Yeah， partially the the way to think about it is in a casino。

 it's all about a game of chance at random。 So that's what you're do here。

Add think so much randomness that。Instead so of creating infinite number of vectors through a hemisphere。

 your samples become a representation hub。You know what they say the house always wins。

Okay one last thing for path tra basics is stochastic sampled antialliasing since we're using Monte Carlo estimation antialliaing is basically free for path tra。

 all you have to do is randomly jitter the ray direction within a pixel and over time as you average out the various samples you'll get antialliasing for free you can see at the diagram there。

 if we shoot one if we shoot only one ray it'll always hit this part no matter what and you'll get jagged edges。

 but if we shoot a whole bunch of rays eventually they'll average out to like a more smooth version。

So that's all well and good， all that considered here is a basic recursive yeah。Yes。So further out。

 the rate tend be lower， I guess。it like if you look in if you're on the right。

 you could those rains get further apart as they spread out so like。

Complely essentially that's an contact or something。他会觉的。basicallysically， I mean， yeah。

 race you have you have your entire picture shooting and then within each pixel you're subdivididing that area so you're essentially randomizing。

The word is not discrete right， the word is not discrete as pixels and a pixel is not as discrete as its center。

So you want to create as much distribution as possible。

And it's good that the rain in the bottom left may be a different。

 slightly different than the rain in the bottom right， and that's what creates anius and the。

If you wanted like more sampling density within a certain object。

 you could like zoom in like change your camera's focal length， there's like a real camera would be。

 but the averaging is more just for like avoiding jagged edges and smoothing out the image。

 so it looks more like a real image。Oh， any other questions？Okay。

 so here is a basic pseudocode for a recursive implementation of path tracing we have this trace ray function which is our recursive function。

 if we've reached the maximum depth we just return black because we're not going to trace anymore after that。

Otherwise， we find the closest intersection in the scene。And if we hit nothing。

 then we return zero again because we haven't did anything。

 you might include like an environment light or like some kind of dome light in which case to be different。

 but for now we'll just say a zero。If we've hit a light， then we want to return the light radiance。

 this is the L term in the rendering equation。Otherwise we sample the BSDF of the material that we've hit and what this does is it gives us the like throughput of the BSDF so in the case of the blackboard it'd be like mostly black or in the case of this table it'll be mostly brown and it also creates a new ray direction depending on the BSDF so for Lambert it would be like uniformly distributed around the hemisphere whereas for like a specular reflection it would be exactly the opposite direction once you've reflected it across the surface normal。

And lastly， we just trace ray again with one more depth and we multiply in the BSDF value。

 this absolute absolute value of the dot product is the cost data term because we simply want to dot the surface normal with the outgoing vector。

And we divide by the PDF because we're doing Monte Carlo estimation。

And eventually this step will hit the next step， and if it hasn't hit a light by then。

 then we return nothing。And then the actual code to call this is pretty simple。

 you just run it once or for each sample for each pixel。Add to the accumd value。 and at the end。

 you just divide by the number of samples。 There you go， path tracing done。But。Questions。

And let me know if I'm ever going too fast at any point。

 I am happy to slow down and answer questions。So we can also make this an iterative method instead of recursive。

And the main difference here is that we store now this ray throughput which is like the raised color as it bounces around。

 you can think of it like maybe a photon comes from the sun and it hits this desk and now it's like brown and then it hits the blackboards and now it becomes darker。

 that's what the throughput is basically。And for。Up to the maximum depth here。

 we do the same logic where we find the closest intersection。

 if it's nothing we just break and the radiance of the ray is set to0 by default。

 so if we have a break in here it'll just be0。If we find a light。

 we multiply the light' radance by the accumulated throughput in the ray。

 and that's essentially like applying all of the balances that this ray has done so far to the light。

 like in a backwards manner to get what the final color should be。Otherwise。

 we just proceed with sampling as usual， we multiply in the BSDF value。

 the cosine theta and divide by the PDF into the throughput。

 and we keep going again until the maximum depth or we hit a light。AndFinally。

 we add the radance to the accumulateccumd value and divide by the number of samples and you're done。

 there you go， now it's iterative questions about that。Yeah。Yeah， example that。Comes from Iacbssspf。

 samplele。So is there a different PF for。So type of material you hit。Is that right or。ことも。

Usually this BSDF could be like a layered thing of like multiple materials and I think in that case you multiply like are you saying like if we have like multiple layers of a material。

 there's a PDF for selecting between those also or something different。

I think it might be helpful to break down so if you have a pure diffuse。

 your probability distribution function is a uniform uniform you want a cosine weighted because you have lamb yeah so that's what I'm there have pure diffuse you might want that if you if you want cosine weighted for lamber yes。

 and then if but no material。Might be pure diffuse。

 like you may want to add a little bit of spectula on that。So let's say the object is 10% specular。

So you may first have a distribution function that。Checks， okay。

 am I doing spec in this part or am I doing the cus in this part and then once your parts is selected。

 then you can do the property distribution of that part。

So did I see that anything I think so what I was going to say is that you could have like a layered material that's maybe 50% spec 50% diffuse and you could randomly stochically choose between them and you can multiply that into the PDF as well because like。

Then the PDF of anything。I don't want to get into the least because I know I'm going to mess something up。

 but just think of the BSDF as an accumulation of everything that's on that one material。

 so everything is like baked into it。Other questions。Can you explain why we have a math？

What a max step Oh oh because if you didn't have a max step that would just keep going forever and then then you would run out of computation time so I get a certain point once you bounce around the scene a whole bunch your array is like really dark so even if it hit a light it wouldn't really do much。

That's why we have a max depth you can certain scenes require increasing this。

 especially if you have an enclosed scene like if you're in this room for example。

 you might want a lot of global illumination which comes from indirect bouncing and in that case you might need a higher max depth。

 but if you just have like say an object outside with the sun is the only light。

 you might only need two or three bounces to get all the effects that you want。Okay。

 so let's move on from this to the GPU implementation， this is from my Pa tracer。

 I'm very proud of the scene。So。This is again， the same code I just showed。

And there is something here that is very easy to parallelze。And that is this。You can simply。

 because every pixel's ray tracing is independent of every other pixel。

 it's what we call embarrassingly parallelizable， meaning that there is minimal work required to make this work in a parallel environment。

And so given that。The naive approach is to simply just parallelize per pixel。

 so we have our fun little kernel that gets the pixel index based off of the block into that index of course。

 and the logic for actually like doing the path tracing is more or less the same as the iterative approach。

And in the main， instead of looping over every single sample pixel， we just run the kernel。

And then we divide， of course， the number of samples into the image at the end。

 this can also be a kernel this to be like your final gather step。

 I just wrote it this way for convenience sake and the pseudo code。However。

 there are problems with this kernel， can anybody tell me what is wrong with this？

It's not so much wrong with the code itself as more of the approach。

 like what could potentially cause a slowdown， for example。Yeah。Exactly。Right on the money。

There is high divergence and low coherence in this kernel here。

Especially when you do the closest intersection and the BSDF sampling。

 you can have wildly divergent threads in the same warp。

 Now at first you might have like your razor in a row and they're relatively coherent because they're all hitting the same thing with the same material。

But then as soon as you bounce it once and if you're stochically sampling。

 they're going all over the place and they can be varied in noncoherent。

So like some might hit the light and they would exit early， some might hit the walls。

 some might hit the glass ball， and in that case， you're now calling very different parts of the code for each adjacent thread。

Any questions on that？Another problem is that the threads can terminate early， unpredictably too。

 like I said， some might hit the light end early， some might hit the wall and keep bouncing around like five more times。

And you are wasting your threads very bad。 So like one thread might be done in the first bounce itself and then just waiting there while the rest of the threads are still bouncing around。

 And that' those are threads that could be doing other work。

So the solution to this is instead of parallelzing by pixel。

 you are now parallellyzing by path segment and splitting your big mega kernel into different stages。

 so we have regeneration， this happens once at the very beginning。We have intersection。

We have shading and sampling， and finally the final gather， which happened at the very end。

These are kernels that are pulled directly from the base code。

 they correspond exactly to those four steps， you have generate ray from camera。

 you have compute intersections， this one is shade fake material to start off because the base code gives you a fake shading your job is to implement the actual bouncing around an actual BDF sampling here and then you have final gather。

Some of these are already like mostly implemented for you， other ones。

 namely like these two are going to be the major ones that you're going to want to focus on。

These two being compute intersections and shape material。

Okay but can I see the final gathering and the generator from panra。

 you may change depending on which feature options you choose。Yeah。

 but like for the required part of the project， those can stay relatively unchanged。

 but there's all sorts of things you can do， you can make your camera like be a fishey camera at depth of field。

 whatever， but we'll go into that in a later section in this slideshow。

Another important thing for this is stream compaction to make sure that your warps are densely packed。

 you can compact away threads that are already done to reduce your launch size。

So you generate every ray。Yeah， this is very familiar， right I'm sure you know。

 you might have heard about this somewhere， I don't know where， but like maybe somewhere。

So you generate your rays and where's the laser goal？Okay， well， there's no laser。

 but you generate your arrays， everything is active。

 then you shoot them off for intersection and maybe some of them miss。

 maybe they hit nothing and then you can just you can't remove those because it's still important to add that to the final thing。

 but you can put those aside for now and focus on the other ones。

And then once you do shading and sampling， maybe some of them hit a material or an object that has no material and they also return black。

 then you can again put those off to the side and focus on the ones that actually have some shading and sampling to do and you do this over and over again until you've either reached your max depth or you have no more threads to simulate and at that point you can do your final gather。

 add them out to the final image and then go on to the next iteration。For this one。

 you can use your project2 code if you want， I personally would suggest using thrust instead because it's way faster so and it'll just be a nicer experience overall。

 but if you want to use your project too， feel free it's your choice。

We can also sort the ray by material because even with stream compaction。

 there can be differences in adjacent threads in what material they're sampling。

 which can again cause divergence。So if we sort by material before performing the shading and sampling。

Again you can use stress for this， then it'll make sure that adjacent threads are doing very similar parts of the code and that will lead to increased coherence。

Any questions on anything so far？Okay sure that。Although it may seem like all the sorting and stuff and stream compaction。

Is additional compute。It goes back to what we've been saying in class where compute is free and optimizing global memory access will give you a speed up so we are doing additional compute so that we can optimize global memory access。

Punfact is also like some cool tech out there in the latest graphics card。

 like NVIDdia graphics cards have a Shar execution reordering， I believe it's called。

 where you can like reorder threads on the fly to maintain divergence。

 but obviously that's way out of scope for this project so。Yeah。Soれ。It's like do this pretty。

 but like is there a way to do stream detection， all sorting？

I don't know there might be a way to do so in trust。

 but I think for my project I just did them separately。

 but you could check the trust API docs there's probably something out there。Maybe。I if you sought。

 so that all the。Well you're sorting my key so and you're sorting based from different。

Because when you sought。When you source for steam compaction or stand for steam compaction。

 you are checking on， whether the thread is active or not。

 whether sort the material you're sort materials， not checking whether its active or not So that mean definitely a changer。

Unless。You do a paper on them to。Have an ordering of， okay， is this material also active language？

Is possible。But。You haveIt may be worth including your performance analysis too if you just decide to do that。

Other questions？All right， moving on then。So here is an overview of how this project is laid out。

First as the core parts these are required and the same for everybody。

 you have to have diffuse and perfect specular reflection materials。

 you don't need roughness that's not required and it's extra credit if you want to do so。

 you also need segmented path tracing with stream compaction。

You need to have the ability to sort past segments by material。

And you need to implement stochastic sample antialliasing。That's the first half of the project。

The second half is still required， but you get to choose this time。

You have to implement 10 points worth of features， each feature is worth a certain number of points they' all listed out and the read me。

For features that are not listed in the instructions that you still want to pursue。

 you can ask on Ed discussion and we'll tell you how many points it's worth。

And this is the most important part， make sure you show and explain every single one of these in you read me because if you don't put them there。

 we're not going to know you did them。It's very important when you want to share this project with someone that they know all the work that you've put into it。

That's good and I。This project is very open。Like if you guys are project one and two had lots of exception and you will open here we had extremely open like students have done absolutely crazy things with their past faces and we're more than open to that of course you know within the time span you have you may want to pick。

Which ones you do and then some students take the pathway and do final projects with them as well so so think about the approach you want to take and be will open with asking questions or that discussion about。

Yeah， I want to do this new feature that was implemented in again how new terms to work maybe be very quick to respond to that。

嗯。The other thing I'll share is the。ActuallyYeah what's up this again。

In the project included is IMGUI I'm Gu I don't know you say it but you can use it for a nice simple GI for exposing settings and statistics you should use this to make your patch tracer more informative and customizable for example you can customize the camera FOV。

 the aperture， the focal distance， all sorts of little parameters in your scene you can display more detailed performance statistics you can maybe break it down by like how long the sorting taking this frame。

Excuse me， or how long is whatever taking in this frame could have like a nice little bar graph or something who knows？

And you could， for example， have an option to toggle sorting by material and see whether how much of a performance improvement it actually gives you。

嗯。What how you you。3。Like the ray tracing， patch tracing， whatever class。せ。And you may be wondering。

 why do we need to interact with our process？Because it's probably just something population0 know different power of views。

We actually don't do a CPU bath anymore they do it in like a fragment shade or know I think yeah。

 it's just just some weird thing。So in this case， you're going to see interactive patterns like based on the scene you have。

You're going to be able to tune it interactively and again， this is potential extra credit。

The scene file of the table color is not JO。You could potentially write a JO parser in image go and have your scene being interactive if you want yourself。

 Again， extra kind of doctrine if you want。For more information about the GI。

 check out the render IMGUI function and preview CPP。

 which leads me to the base code tour I forgot to open this up ahead of time， let me do that。哦。

Does anybody have questions so far？暂次俾。No。就 you系。What advice were like， how would you recommend？

holdold you around。Right。そ thatなソスまオスタメてていう。I do also recommend both people if you want you can。

 but what I would recommend is dive and try。That's that's my number one recommendation if you want to try。

Something that you can do in a day or two that it get your hands dirty in ray tracing。

 try re tracing in a week and while a weekend really means that the weekend you can wrap it up in a day。

What it will walk you through is all the materials and the launching the rays and stuff like that。

 A lot the code， so we're not necessarily solving the problem that we don't want。

So did you take lot bit to about the ERC the books that all these。

And then you can be dive the quarter。All right， so here is how this is laid out。Of course。

 you have your main CPP file and there's not really much of a need to mess with this。

 it's mostly just like infrastructure stuff and like setting up， you know， open GL whatever。So。

 but again， if you're interested in like doing some like out there features。

 definitely look through all of these and see where you can implement them。食我啲 friend去。

You want the zable parts tracer。啊 the you放我呢块。The main path tracing logic itself is stored in pathtrace。

cu very apt named。This will have the four kernels that I mentioned earlier left generate right from camera。

 compute intersections， you'll see here that it's called shade fake material because if you launch this right now it's not going to do pad tracing it'll just like show kind of sort of what the final color is going to look like。

 but not really。Like this is one of the main places where you're going to want to put your BSDF sampling and bouncing around logic。

Then you have the final gather， which is pretty simple as you might expect。

And then like your path rate， there's a big to do block here with a lot of instructions on what you're supposed to do as with any project just look for like things that say to do or check it out and you'll find most of what you need to be editing。

Additionally， we have some other files here， we have interactions。h。

 this is mostly for like material evaluation， some helper functions， for example。

 this calculate random direction and hemisphere is already given to you。

 so you don't have to worry about doing that yourself。We also have intersections。 H。

 which as the name implies is for intersecting with different types of objects。

 what's given to you is a box intersection test and a sphere intersection test because that's what。

The default cornell boss made up in this patch tracer， again。

 if you want to add like planes or triangles for meshes or like procedural objects or whatever。

 that's going to be on you to add those in this file。What else we have a preview that CPP。

 this is where the GUI stuff happens， this is also where a lot of the openGL stuff happens。

 so if you were going to aim to replace openGL with Vulcan， for example。

 this would be a big area to do that in。I believe， yeah， this is where it creates the IMGUI。

There should be like a yeah， the render IMGI， like I mentioned。

 this is where the you can add like different little checkboxes or little text fields， bar graphs。

 whatever you want in this section。What else is there scene does CPP this is where you load in the scene files so if you want to add support for meshes or for other types of objects。

 this is where to do it and it's all JSON based so it should be relatively simple to extend this to add anything you want。

Other files are just like random things， there's like a utilities file with some like clamp and like string utility functions。

 whatever， everything else you can kind of look to yourself。

 but the main things to look at are path trace， interactions， intersections。

 and then maybe preview and scene depending on what you're doing。

I believe that's it for any questions on that？I think there's like， yeah。

 I think if you press S it'll save your image，ll like pop up a little file dialogue or something and you can save your image。

I would suggest that when you have cover images for your readme。

 do not include the IMGOI in that unless you are specifically talking about the GOI itself。

 make sure your cover image is as clean as possible， so use this save image function wisely。Okay。

 with that， we will go back to this。

![](img/7e218226f4567b321e7daea6bea6976b_2.png)

And move on to extra features。This is probably the most fun part of this project because you can do whatever you want as long as you meet a bare minimum。

First thing you can do is direct lighting and multiple important gambling。

 you guys have taken 461 we'll probably recognize this from that。

Direct lighting is essentially sampling lights directly instead of waiting to hit them randomly。

 which can significantly decrease the amount of noise in your render because you don't have a whole bunch of arrays that are just hitting nothing and contributing nothing to your final image。

You can also do next event estimation， which involves sampling direct lighting at each bounce along your path。

And to make this work properly， you'll need multiple important sampling。

 which is a way of combining multiple methods of sampling， in this case。

 random BSDF sampling and direct light sampling。And it greatly improves robustness for materials of different roughness This scene here is called the Beachch scene named after like I think his name is James Beachch yeah and this was like in master's thesis or something and the top left you can see with just BSDF sampling for the small light with high roughness it's very hard to hit it because the rays gets scattered all over the place but for light sampling for the low roughness。

 large light it's hard to hit the light because a lot of the light sampling directions are not valid directions for sampling the low roughness BSDF but if you combine both of them then you can see at the bottom image it's a lot more robust than either of them so you know you get the best of both worlds essentially。

Next， this is probably one of the best features you can implement simply because it allows your scenes to be significantly more creative。

 is to allow loading custom meshes。嗯。I believe in the readme it mentions GLTF and OBJ with varying amounts of points for each。

 you can also if you want try other formats like USD。

 which is not a file format per se but you can represent 3D scenes with it I don't think you can do FBX because that's like closed source or something but you can try all sorts of scene formats and if you want one that's not listed then again ask on Ed discussion then we'll let you know how much it's worth。

There's plenty of websites online to find free 3D models。

 my favorite personally a sketchtFab because they have a nice like 3D preview window that you can see the mesh before you download it。

 there's also Turboquiid， CG trader， Pollyhan， this casual effects one has a lot of good like graphics test models like the teapot or like the Stanford Dragon or the bununny or whatever。

There's also the GLTF samples， for this one you can you don't have to worry about more advanced features like animations or scanningning or whatever unless you want to。

 it's up to you again and depending on how much time you're willing to spend on this project。

So want that。The one of G is that T。Every word can be exported at G。

So that'll give you a huge library try out the other thing that' it's pay attention to the licensing because in your Es please3 you Yeah just like as a fun little aside I used to do a render every day for three and a half years and I have a humongous Google doc with like every single model I've downloaded and a link to it on there so attribution is important take it seriously。

All right， if you implement custom meshes， you will pretty much always want spatial acceleration structures because if you iterate over every single triangle in a large mesh。

 you are going to run very， very slow and it's not going to be fun。

This can include for example a BVH or bounding volume hierarchy。

 there's an example of it at the bottom right， it's a treelike structure that groups nodes into larger and larger kind of like bounding volumes and it significantly reduces the number of comparisons for intersections you have to make to determine where and whether youre intersecting with a mesh the top image there is an example that shows kind of a heat map of how many intersection tests were required for different parts of the mesh。

You can also do a KD tree or an a tree it's up to you to look up more about those if you want to implement them one thing to keep in mind this is an open question is how do you represent and traverse a tree on the GPU so think about that if you're implementing these and see if you can try to optimize it somehow。

Any questions on anything so far？Yeah。或者。Some of these extra credit meant to be implementedSo for building the acceleration structure that should be on the CPU because I believe there was a final project previously that built it on the GPs that's way out of scope for like a two week project。

 but most if not all of these are going to be mostly on the GP like mesh loading of course you have to load it on the CPU but then upload to the GPU so the final part will be GPU usually but it depends on like the feature。

Astruction can be on C， but the actual pathway rate。

YouW to accelerate construct construction on the GP all power to you。

 ask for that and we have your how points。对对对。Yeah， I guess another question is。

 does this oh I haven't like compile it， but like does this face code come？

Likereization of the single here I'll just launch it here and I'll show you it essentially just pops up a window that it does like the re generation。

 it does like one intersection and it shades it with like a fake method and then does the final get this is what it looks like to start off it' it's like just some it does some like dot product of like the ray direction and the surface normal or something and it like adds the material color onto it plus a bit of noise。

That's what it comes with， basically。二 yeah。I think if you just like left click and drag。

 it'll move the scene around， you can like use the scroll wheel to zoom in and out or suppose what was it right Luke？

Yeah， right click to zoom in and out， there's like the basic path or IMGUI implementation up here that just shows the like time frame for frame it's pretty slow right now。

 but once you implement all the features that we talked about earlier， it'll be a lot faster。

This space。Wing by computer。Yeah。Because these are all launched using K kernels。



![](img/7e218226f4567b321e7daea6bea6976b_4.png)

ok哦我 didn go here okay。next thing you can do is physically based materials these are how to make your objects look a lot more interesting and a lot more realistic。

 you can have microfacet distributions which is making your specular materials more rough so at roughness zero is the perfect specular reflection but with increasing roughness the specular highlights kind of fade out over the surface and become more diffuse in a way so you might see like some of these tables have like kind of specular highlights but they're not nearly as sharp as the 0。

0 there so that's a good one to implement。You can have texture maps this will allow you to make again more realistic materials that you can't get with just plain colors。

 you could have like wood textures， rock textures， who knows metal textures。

 whatever again like the PD models there's plenty of websites to get these for free online one of my favorites is NmbNcg。

com these are all likecc0 so I believe you don't even need attribution to use them you can just use them for free however you want but you should double check that before you use them。

You can do subsurface scattering， this is the phenomenon where like you hold up your hand to like a flashlight and you can see like red shining through it。

 that's because the light is entering into the surface。

 bouncing around a whole bunch and then exiting out again。So you can see on this like rabbit here。

 it's sort of like a jade milky stone mineral type of material。

 you'll see it a lot in like human skin and like milk， ketchup。

 honey that sort of thing and fun fact subsurface scattering is what I worked on for this entire summer。

You can have participating media this is like clouds fogs。

 smoke all sorts of things this is a final project from a previous year I don't expect your participating media for this project to look as crazy as this if you can then great but you know that's a lot of work this can be good especially for outdoor scenes if you want to have some nice like distance fog or something。

Yeah， one thing on this。Oh for pension maps and stuff。

One of the most common combination is mesh loading and extra maps。

 which is yes couple to benefit and there's a bonus point as well if you do both。

You can also do normal maps and bump maps or other kind of texture maps with that as well。

It can give you a lot。 So definitely worth trying up。Questions on any physically based materials。

Yeah， can you design participating media？It's like。It mightight not be the most accurate description。

 but it's like a medium that's not air that the array travels through。

 so it'll like scatter and like absorb and do weird things as it travels along。

The other way to also say it is not mesh， it may be more volumetric， so that's something we may want。

Allright， so you can also make your camera physically based， you can have， for example。

 depth of field this is the ability to put certain things in and out of focus so in this scene here in the center the spheres are more in focus they're sharper。

 but at the corner they're more out of focus or they're blurry。

This can be a nice thing to do for like close up shots of like a very detailed model， for example。

You can have a fishey or panoramic lens in this scene here the models I use are all like straight lines。

 but the camera itself is the one just sorting them to give a more like strange or maybe suspicious kind of effect so if you want to do like a more artistic cover image this could be a good thing to implement。

You can also have motion blur， this is implemented。

 I believe in a similar way to stochastic anti-alliasing。

 but instead of antialliasing over space you're doing it over time so you can like shoot out rays at different times within an interval and when you average them all out。

 it looks like the object has been moving for that entire interval in a similar way to how if you did this with a real camera you would keep the shutter open as the object moves in front of you and it would like sort of average out the emotion of the object。

Of course， to do this， you'll have to also implement some way of storing like animation or movement data as well。

 so keep that in mind。I was just thinking what， what are your thoughts on。

This onet be new for this year。Doing like one of the app pro call spatial spatial images。

 I've never used。 I don't know， basically like。Rendering two images that are next to each other。

 load them in an Apple version code and see how it looks。

 but be a cool extractor to even if you have a headset。Yes。对。You could do like VR ray tracing。

 who know， this project again is like， in my opinion。

 this and the final project are by far the best to put on like resumes and portfolios and whatever。

 so go crazy with it， make it really cool because I also don't want to have to break like a laneme path tracer so you know。

 make my job easier。Okay， you can also do procedural materials and shapes these are like。

If any of you are taking procedural graphics you'll obviously know what this is。

 if not these are just like made using algorithms and formulas as opposed to hand drawn like Minecraft Mincraft has generated entirely using procedural algorithms that's the classic example。

 but you can do it for textures， you can do it for shapes。

 you can do it for other things too so that's one example something you can do。😊，Denoising。

 I think this is one of the most beneficial things you can do outside the ones we had already mentioned because。

What it is is it's a filter that removes noise from your image。

An example that's really easy to implement is Intel Open image D noise。

 it's a deep learning based set of filters that can optionally take an additional buffers for increased quality such as the color or the albedo of your materials as well as the surface normal。

And Intel Openimage Denoy specifically works on both the CPU and the GP。

 and it's nice because if I remember correctly you can actually directly map Kuta memory to be used by open imageage Denoy so there's no need for like weird copying and other things like that。

The reason this is so good is because it can drastically reduce the amount of time you need to render a nice final image like you can see just the best difference it makes here with a very insignificant drop in quality only where it's like a little undersampled maybe near the roof in this seam。

 but just 20 samples for pixel gives you an already almost final quality render using denoising。

 so I would highly recommend this if you have the time。In phrase from your knowledge。

 are there other image noises worth trying as well。

 I know inter open image noise we've added on the instruction for like five years。 I mean。

 this is like the canonical example， I would say that there's like。I've used other denor。

 like optics denois is only used for optics， for example。

 I don't even know if you can use it outside of that。There might be other ones out there。

 but I wouldn't know I've generally stuck with openim D noise。

 even for my own renders with like Ber for example。

 but you know if you find some other one that you want to implement， just ask on ahead。

 we'll take a look and let you know。Yeah， it drastically reduces rendering time。And like I've said。

 if you have something else， just ask and we'll let you know。For further reading。

 if you want to try something even completely different。

 well PBRT is like the canonical resource for path tracing， all the theory， all the implementation。

 everything is here and in the fourth edition released last year there's actually a chapter that covers GPU implementation as well so that can be a good read if you're interested in like maybe optimizing or stuff like that。

There's also ray tracing gems， this one is more like a collection of more like random things that can be formulas for all sorts of things like better sampling or better like random noise algorithms and things like that。

 this can be a good read also if you're looking for inspiration or extra credit features。

Eric Canes is going to just be in the class on September 3 year， so you see name book。Yeah。

 very privileged to have him speak to the past of the year he's a very cool guy。

 he should look forward to that。嗯。Any questions on any of that before I move on？Okay。

 read me and deadline policy， the code deadline is Tuesday， October 1st at 1159 pm。

And the readme deadline is two days later and the reason for this。

 what this means first of all is that you should not be pushing any new code after the code deadline is up those last two days you should use specifically to make your readme look beautiful like it should be really good because this project is the end output is like can be really good if you make it really good so that's what you should use those two days for。

Use it wisely。Late days can play。This kind of break in the submission deadline matrix especially two or ten0 years ago。

 and the reason we did that is because。Students did always think about how much time it took to generate images and didn't take the time and make beautiful images like zoo being honest。

 like if you look at 2020，2021， when we still have this versus when we did have it。

It's like whole different change in the reading。 and that's because as Ro once and as engineers。

 we want to make the test possible。And we don't think about the presentation of it。

This is specifically to make it think about presentation Now if you find a critical word in your code that needs to be resolved。

 should push it note it down in your full request that yeah I made the because I found it we take that into consideration but ideally use that time to create new scenes。

 create your images， try new things out and then open up the review。Late day policy for this project。

 you can use if you use them on the code deadline， the ReadMe deadline will also get pushed back。

 so for example， you can use one late day to make the code deadline October 2 and the read me deadline October 4th。

And if you've already passed your code deadline and you want more time for the readMe。

 you can also use late Day specifically for the readMe deadline so in this case。

 say you've already used one to push it back to October 2nd and fourth。

 you can use a second one just on the readMe deadline to push it back to the Fi so it's up to you I would suggest this is probably one of the best ways to use your late days。

 especially if you don't have anything else going on over a fall break and you want to make it really good like that's a great time to do so。

Important cover image every you read me should not be a Cornell box because that's lame。

 and like I said， I don't want to grade a Lame path tracer。😡，If you're heavily customizing it。

 which will' see some examples up， seek preapproval in Ed discussion。

 and I cannot emphasize this enough， make your read mes beautiful because that is the way that people interact with your project。

 that is what you're going to send to people that they ask about it。

 so make sure it shows off your best work。呃， question on在。All right。

 so lastly we'll go into a gallery of some previous work。

Here is from my year which is last year top right is mine top middle is Hans it's very nice like environment map and like custom models and sorts of things I quite like this warham model on the left it's a nice example of PVR textures and custom mesh loading。

Another environment example of custom Mes at the bottom bottom right is like kind of Cornell box e。

 so I would stay away from that personally unless you're like really making it something crazy。

 I just think that some kind of more production ready。

 perhaps seen like these is a lot more interesting and it's going to be better for you as well。😊。

The other thing to think about from the common boxes because it's closed on five sides。

 you need a lot of bounces whereas as open scenes like for example Hans chests your window very quickly so that's again the performance to generate your images quickly and I will say in your read me it is very helpful for performance analysis to try both open and closed scenes because they have very different like parameters that are necessary to make them work。

Here's some examples from the year before， top right is a very nice PBR camera。

Top middle is like a basketball trophy this is another cornnell box still very heavily customized。

 but again I would say away from that personality bottom right is like kind of Cornell box disc。

 but also like it looks like a cave with like link it that person might have modeled that themselves I don't know。

 but it's nice and then bottom middle is a nice custom model with some depth of field as well。

And lastly， from earlier than that， we got the classic Wahhu can't go wrong with that with them depth of field and stuff。

 too， we have， this is a nice。😊，Like artistically， I think it's a very interesting scene as well and it shows off a lot of different custom imported models bottom right I believe was doing like spectral dispersion like how you might see dispersion through a diamond in real life。

😊，And then top right is a nice， colorful scene with some depth of field。

And maybe your someday if it's good， so make it good。And that is it for me。Any final questions？

They remember this project。Even without extract credit， it's like 15% of your trade。And then。

Because it's 15% of your grade， the extra credit is weightd more as well。

So ask for the questions you want。I。How does the extra credit work， So if you have those1。



![](img/7e218226f4567b321e7daea6bea6976b_6.png)

I believe it should say in the read somewhere。What the exquisites？This is 5650。



![](img/7e218226f4567b321e7daea6bea6976b_8.png)

There。ner。Like if you do more than the required10 points， you can get up to like 25 extra points。So。

In 2022， we probably didn't have the limit and we were giving like 13 points。 and yeah。

 that could gain pretty well。Now， we， by default， we limited 25。 But let's say， for example。

 as we were discussing before， if you want to do。Had the accelerated construction of your PHs any you deserve more than that we will consider it。

 we want to be fair to everybody so it's not impossible to get more but again get pre approval ask the question know it doesn't matter a lot。

Yeah， at some point， someone mentioned that people have done some pretty wild things in previous years。

 what are examples of like？Exs like stuff that's not in that。

I extra credit that he moved on that are like crazyI think Shazana no better than I。

You're asking me to get it to my mind that I probably raised so the example with the gold statue that was in the other ones。

 that was Hu in June he took class in 2019 in the 2021。



![](img/7e218226f4567b321e7daea6bea6976b_10.png)

![](img/7e218226f4567b321e7daea6bea6976b_11.png)

Okay next slide。that has some pretty crazy in both material features as well as acceleration structures。

And then giant's Park tracer， I think。History of politics project with flow back of 202。

Wait this is the camera one， right， the top right on the scene。If we go back to 2012。

 we are around 2020， so we complete 11 years of classes。后啲。

350 students have taken the class that time。 that's probably one of。嗯。So。这个嗯穿就可以。

I think he's still working on a too right， I think he's still working on it too like outside of yeah。

So this's like tracing material techniques。Crazy acceleration and performance techniques。

 and then if you want to combine it with the noises and stuff like that。

 so yeah all of those are all different vectors along which you can think。平费。

The acceleration are a little less flashy， maybe for if the purpose is to make occur right。

 but they make for great interviews yes and without them without them you're not going to be able to render the scene in a reasonable amount of time。

I道这个。You can make the flashing by having a foot。And the yeah。

 like the around or was it way back here again from that we before。Other questions。都我没啊。You考 this。哦。

对。有。I mean， unless you want to train the model yourself， I。没什。It's even if it is a pain。

 it's definitely worth the pain， I would say I don't think it's that difficult。

 you just have to deal with some weird seam stuff so if you don't like that then maybe not。

 but if you get it working it's a very huge benefit。嗯。这本啊全。So不是是。喂喂。就是我。

For final renders it might not make so much of a difference。

 but like I believe in mind when I had the denoer I had it update like every three frames it was in the denoising so you could see the like denoed image slowly resolved in the viewport itself so up to you you can do it like on the final save you can do it in the viewport itself I would suggest in the viewport so you can see what it's going to look like once you save it but up to you。

Yeah， what's your favorite feature that you have？Oh in my pet。

 I like the mesh loading because I can load like Freddie Faazber or whatever the hell I want into my battery。

 that's the funniest part。Yeah。like animate isn sit there。たしたい。If you have a very fast path tracer。

 it can be worth putting a gift of you like moving the camera around to show that it's interactive。

If you're doing the really complex scenes， it's not going to be interactive and in that case you just put like a static render or of course if you implement like like some kind of motion like some kind of animation keyframe。

 motion whatever， then of course you should put some kind of animation as well I also say that you don't have to have the animation the same thing as your cover image your cover image can be deeply complex and high whether you see animation can be lower solution but simply limit what shows shows the nature of the interactive。

So you can again game the system in it。Yeah， is there a good resource？

I think I just looked up a tutorial online or something for like building BVHs。I never looked at it。

 but if it's good， then sure， go ahead。I think there should be button this kind of thing。Yeah。好。

I believe it mentions that in the read me， there's like a third party code policy here somewhere。



![](img/7e218226f4567b321e7daea6bea6976b_13.png)

Let's see where it is。Third party there。So it's like if it's not like a core part of the project。

 like you can't if you just use some library to build。

 you haven't really done any work yourself so I feel like it's not really worth points right but like Intel Openim noise is different because there's no way you can train the model yourself in like two weeks or whatever right so。

I would say read through this and if you have any doubts or questions。

 then you can always ask on that discussion， but off the cuff。

 I would say that using a library for BVH loading is probably not worth any points。

I also think it would be very difficult to adapt to the。

Especially since you have to upload it to the GPU as well。

 it's going to be like some kind of bespoke format that you're using probably to make it work with your code base。

あていうの。Yeah。晒飞。

![](img/7e218226f4567b321e7daea6bea6976b_15.png)

I would do it in the read like if I pull up， my read me。



![](img/7e218226f4567b321e7daea6bea6976b_17.png)

是 here。And also， this is a good chance so that these readview can get really long， so don't hesitate。

 like don't get be late with starting this。Because they can get you also want to put things like like debug images and all sorts of like funny little bloopers and whatever。

 performance analysis， et cetera， et cetera， so don't start this too late or you're going to regret it。

But yeah， I put all of my attributions here including for like tutorial Is and like normal map code and the models I downloaded。

 etc ce， this of course depends on the license of the thing that you use。

 so if it's like CC0 I believe you don't have to attribute it at all on SketchFab I think by default you have to provide attribution。

 but I would suggest to do it at the bottom of your reading。I would be。Yeah。

 you it's also a good sign that youre crediting。

![](img/7e218226f4567b321e7daea6bea6976b_19.png)

Yeah。

![](img/7e218226f4567b321e7daea6bea6976b_21.png)

Other questions？I'll make a suggestion here。Both read to ask question。嗯。Of all the projects。

 you get started late on this， you definitely won have the one。

You want to get like the basic part of the project。

Try to get it done by this weekend and then youll have a lot of time to work on extra credit or those optional features and even the actual features get the ones that are easier and get you those turning points in so that then you're ready to work on really complicated stuff so be really strategic about which features you're picking out don don't start with BH right away。

Like you'll run into trouble， get those arguments， get your confidences in the code base and then start customizing the hello and you're you're free to if you say the baseboard is useless。

You're free to change it as long as you're doing a coolla based part traceer with those four features and stuff。

 you're free to change whatever you want will give you a lot of flexibility in your feedback if you have questions ask and the best place to ask is discussion because you don't have to wait off。

第。不是。对。

![](img/7e218226f4567b321e7daea6bea6976b_23.png)

好。That's a good question。I would say。DVH might have taken the longest out of all of them。

I think I have some like yeah I have some like weird little debug images here like of missing parts of this monkey because the BVage wasn't working correctly or whatever that took the longest but it's one of the most beneficial and probably mesh loading was second after that and then maybe maybe denoisising but that one actually was not as bad as I expected。

嗯。Analyst's not an extra credit feature， but doing the re me also takes a large amount of time。

 so don't discount that either。I put the ro I can clearly see。

 I think it was give me worth 20 points。And you think about it。

Your bunch of your coding features would have been2 important。

 So compares amount of time you invested in those coding features versus in your evening。

Most of the time it's like university 10% in your reason。

 but it's worth10 times the amount of funds so think about that way is to detect。他都可行。

Do wrap the one thing I'll say is I've asked that we to optional report office hours on the weekend themselves during project3。

 at least。So just keep an eye on Ed discussions but cannot subscribe to notifications。

 make sure you are because there might be questions that others are asking that can help you as well。

 so just make sure you're putting a good eye on it。Thatss it from me， you want to add anything？哦。

Any advice of your project。好。I think again just into whatever you like。啊，另外。you。不可。えこ。嗯。Hi everyone。

 have a great time with the project and will see you all on Monday。会上面。



![](img/7e218226f4567b321e7daea6bea6976b_25.png)