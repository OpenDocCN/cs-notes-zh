# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p11 2024-09-30 - CIS 5650 GPU Programming Fall 2024 Guest Lecture 2.zh_en -BV1sRtresE67_p11-

![](img/d6074904415e109acbca87dc2ee02c9c_0.png)

All right welcome everyone to the second guest lecture of the semester we had De speak with us a few weeks ago and Eric Hainenes is also from India a distinguished researcher there with a keen interest in D tracing and drill time ray tracing to be specific Eric's got you know more years in graphics than I've been alive sorry Eric if I'm revealing your age at。

Eric was originally at Cornell and was influential in the Cornell box that all of you guys are testing right now on your path traces。

 Eric spent a very long time at Autodesk working on the one graphics APIs for that I used in MayA 3DS Max Rait。

 all the software that you guys use today， and then about five years ago， Eric。

 correct me if I'm wrong， no， just about six now。six years ago。

 right around the time when NviDdia launched real time ray chasing with the RTX GPUs。

 Eric joined NviDdia and has been there ever since taking a lot of interest in optics。

 rayray chasing Minecraft。We learn about Eric's most recent projects in today's class Eric's also a fantastic author and educator his books realtime rendering is super popular I'm sure some of you have read it here so yeah we are very excited to have Eric here today and thankful I believe this is your sixth guest lecture in a row every year so I think that is definitely setting a class record here so thank you for all of your time and we look forward to learning from you today just logistically we have two microphones if you have a question raise your hand I'm sure Eric will be happy to take a question anytime。

Okay， I important you。All right hold on i'm going to re reor a little bit okay there we go all right hopefully you're seeing the first slide the first slide is wrong I realized used to be October that I would give this lecture。

 but it's really not quite October yet， but that's okay。😊，So anyway， right。

 so I'm at NVIDdia now and this is just a pretty picture that we did in omniverse。

 which is sort of a whole elaborate system， but the coolest thing about omniverse for me is that it is just a native ray tracer and path tracer it doesn't use any rasterization it's just always ray tracing which。

Kind of amazed me when I first heard that I'm like， really。

 you're not doing any rasterization because because in my mind， you still， I mean。

 games are mostly just raized with maybe some ray tracecing gloss on top of them。 But it's actually。

 you know， possible to make products that are just pure ray trace nowadays， which is pretty great。😊。

So this all is going to probably put a lot of you to sleep you'll see oh I know this I know this but basically yeah ray tracing what is it okay you're shooting rays you know traditionally you start from the camera you should array out you think of it as like I like to think of it as like a screen on a screen door that you're trying to figure out what each color is at each little square each little pixel and so the easiest way to think about that is well what am I seeing when I first look in this direction what's the thing that's closest to me and so it's just a matter of testing array against all the objects in the scene and what's nice about that is it's a nice atomic operation that rays can be intersected against all kinds of things like can be intersected against you know a sphere or a triangle or whatever you know some kind of curved surface or some kind of fluffy thing or whatever you like if you can figure out how to calculate the intersection of that ray with that object you can rayracing which is a really great feature。

As opposed to raturization where it's pretty much all triangles， maybe some lines or points。

 but those are that's kind of all your primitive is and then you have to teskylate everything into like a curve surface。

 whether you got to turn it into you know a thousand triangles or whatever anyway。

So this is kind of where like long ago people figured， oh。

 I could do this thing called raycasting where I'm shooting rays from the camera to an object。

 seeing what's closest， and then I could also do this other thing。

It's back to 68 where you shoot a ray from the surface towards a light source and see if anything's in the way so there's either nothing in the way up here or down here this ray gets this object so this points in shadow。

so then classical ray tracing kind of started in 1980 or what we call ray tracing as opposed to ray casting and Turner Wied's seminal article which basically said。

 hey you know what I could reflect rays or I could refract rays through objects and let's see what happens with that and that's kind of actually what's interesting is it's how the ancient Greeks at one point thought about eyes is that they thought about vision as well how do eyes work oh well the eyes must be shooting out really faint photons essentially they didn't call them that but they said we must be shooting up you know some kind of things out into the world and kind of sensing the world by sending things through the eyes and that's basically we're doing with ray tracing is we're kind of reversing the process instead of tracing all the rays you from light and having all the photons bounce around and then an incredibly tiny fraction of those actually reach our eyes。

 we said well let's try to reverse the process trace from the eyes you know those are going to be the significant ones。

And throughout all of ray tracing basically we try to think of significant rays and that's going to be a theme I'm going to hit again and again and again today today anyway。

 so what's classical ray tracing well you should know it's just where you shoot a array。

And you bounce it let's say it's a polished surface perfect mirror it bounces a ray off and you get puts in the reflection direction so just to walk through this here's a piece of glass and you can do it for refraction too So here i'm shooting ray I might shoot a chat a array back just to see what's going on on that surface and then I shoot two rays I spawn two new rays from that intersection point one's going through the glass that's a refraction one's going bouncing off the glass that's a reflection ray and then。

Again， I'll just follow the refraction ray in this case and I can again test for shadow。

I again spawnmore rays refraction reflection， I again test for shadows and in this case this one's shadowed so we'll you know have less of a contribution and then I kind of sum up all these。

 not some but sort of multiply together all these little contributions and get a final color at the eye。

Next up really on the。Sort of interesting breakthroughs was 1984 Rob Cook at Pixar came up with this idea with other people called stochastic or Pixar actually calls distribution ray tracing there I think the last company on the planet that calls it distribution ray tracing but you might run it into that term the reason we don't usually call it distribution is you can think of it of a ray tracing as being distributed on a cluster or something like that so that's usually what distributed means for most people but anyway usually called like stochastic ray tracing the idea there is that hey instead of just shooting one reflection ray issued a whole bunch whole cluster of them and I kind of gather up you know what's going on with each of those so you can get like fuzzy reflections for example or another thing you can do is get fuzzy shadows in other words for an area light that's going to give a penumbbra you the area between the umbbra total shadow and a fully lit you can get this。

Soft shadow， which you'll see with any kind of areaial light source， including the sun。

So what that does is basically says， well， instead of just shooting one ray back to the light。

 I'm going to shoot a few rays back to the light and I'll again sort of see what percentage of the sun actually you know gets to this point on the surface and so the more shooting more ways you shoot。

 the better the result， but the more costly it is to get that answer。

So next thing on the history list is 1986 Kajiya Jim Kajiia at Caltech came up with this what the well I'll reference it a little bit later the red ring equation which is one of those if you only need one equation in computer graphics that's really as far as I'm concerned the one to know because it's just a way to think about light and a way to think about gathering that light and trying to figure out what's going on I'm a seeing but the idea the sort of super brute force thing that they came up with back 1986 just to see whether they could do it or not。

 was to basically say I'm going to shoot a array whenever I hit anything。

 I'm just going to shoot a burst of arrays out in all different directions and follow them like I'll follow one of them basically I'm just going to instead of really a burst I'm going to just shoot it in one direction this is patch tracing which you all are poking it right now so I don' belabor the point。

 but the idea of patch tracing is indeed that you're shooting out these rays hitting hit something and now you're going to shoot out。

More rays you're basically going to say well you know I don't know what's going on in the environment like a ray towards the light is going to be very significant。

 but there's you know there's light bouncing around the the room so i'm going to shoot a bunch of other ray the original form actually said well you know keep bouncing around until you hit a light and well if lights are really tiny in the scene that could be a very long time here I just sort of follow them until they hit。

some surrounding you know area basically， but the idea is you're summing up you know you basically getting all these different contributions and you're being able to get like other other elements than just pure sharp reflections or even glossy reflections。

 you can get you know what's really going on in the scene。

 but you have to shoot an awful loty is to do that。

But you sum up all the contributions and you get an answer so this kind of algorithm with modifications which I'll talk about later is definitely the way that a lot of computer graphics is done in the film industry you'll shoot you know 100。

 300，5000 some number of thousands of path traced raises per pixel which can be expensive but you know it's all an offline process no big deal and if it takes 20 minutes per frame so be it。

So。

![](img/d6074904415e109acbca87dc2ee02c9c_2.png)

Anyway， that's that's sort of patch tracing in a nutshell we'll get back to it The reason I think ray tracings great This is Paul Heckbert's business card when I was at Pixar around 1994 and also ran this whole little contest for when he was the editor of ray tracing gems so in ray tracing gems for you'll see you know a collection of these sort of ideas of howm going to make just a really small ray tracer because it is such a simple idea it's basically saying you know I've got a that's one simple mathematical thing。

 a direction in it and you know a point rather in a direction and and I've got some object a sphere or whatever in intersecting is not a real tough equation so anyway so this one's you know 1607 bytes and I actually went and ran this code I never actually seen the result of this I realized a few years ago so I finally did it and you get this the original you get this sort of 32 by 32 thing。

Running at high res I get this thing but it's you know it's kind of amazing it's like i'm getting a sharp reflectionion off this you know sort of white light kind of thing and I get these sharp reflectionions of other objects and whatnot so anyway a refras or whatever so。



![](img/d6074904415e109acbca87dc2ee02c9c_4.png)

U， so that's that's one another business card just to show， oh， that's， you know。

 you can do even more kind of thing is。嗯。Sorry， Zoom just quit on me and I hope that that doesn't keep happening I'm not sure if it's some glitch on our end。

 like I said we're having work done here so。Oh。Let's try sharing again。

So we can still see and hear you Eric so when I'm really okay。

 well that's just weird Okay well anyway because on my end it says oh zooms quit okay well anyway。

 so this is just another little ray tracer。😊。

![](img/d6074904415e109acbca87dc2ee02c9c_6.png)

Which I thought was cute。嗯，行。And okay so your quiz question is which one of these is the real cornell box this one I actually have to look at my notes to remember which is which and they actually did this experiment back way back when of just setting it up with a little diffuser to kind of hide any anti-assing you aliasing problems and so on and basically it was kind of a 50-50 thing you know it was nice to realize like oh okay if you actually do this experiment or if you do it you know sort of the right way in this case they were using I think those one actually this path tracing but anyway originally they were doing more of a meshbased thing with rasity but anyway so it turns out the one on the left is a photograph not the one on the right rendering。

So just to go through that box and again I suspect you're all familiar with this。

 we have hard shadows， which is just little point light starts up top and then we have。

Let's see we have， you know， so we can get hard shadows that are either on or off。

We have soft shadows where we have an areaway。There we're shooting a few rays towards the light and summing up how much causes a penumba。

And then we have sort of inner reflection where we're actually shooting a ray and each ray is a path and you know。

 it just follows a single path and you shoot a whole bunch of those and you get this， you know。

 these nice innerreflection you know effects where you get color bleeding where the red is on this normally a white cube。

 but it's getting this red picking up this red light。

And then you know there's similar to do like glossy reflections like with the cook kind of thing where you say。

 well， you know I don't want to shoot lots and less arrays。

 but I want to shoot some just in the reflection direction and we'll talk about that important sampling idea in a little bit a little more in depth。

 but the idea of just shooting out a burst arrays and sort of a reflection direction and trying to pick up a soft reflection here。

Okay， so this just gives you an idea of like a soft reflection， you know。

 going glossy from you can vary glossiness， making use textures to control the glossiness and so on and so forth。

So again， here's another quiz question for you， which affects in a reflection and so on can you see in this image？

And the three IC are we have this glossy reflection idea。We have。You know， on top。

 you're getting some kind of reflection on this on this。

Object even it's interesting like if you look at what the fll effect Frell equation actually means everything turns out to be shiny。

 if you look at it at a sort of sharp enough angle like if you you know look almost parallel to a sheet of paper you'll see oh wait it's kind of reflective now so its it's an interesting thing anyway so you're getting these gloss reflections getting soft shadows and we have inter reflection you wouldn't you know if you didn't we're not doing inter reflection here you't only have light where where the light comes in directly you wouldn't see the rest of this scene。

So there's also non physical effects you can do with ray tracing that sort of simulate kind of what light does and this one's called aient occlusion where。

And getting these sort of soft shadow kinds of things。 It says almost as if the。

 the scene is living by is being lit by by a hemisphere， like。

 like it's a cloudy day or something like that。And so the idea there is that you're。

Not really again like this isn't physical in the sense that it's not a real light that you're figuring this out for but what you're doing is you're saying well given some point I want to shoot rays but I only want to shoot them a little distance and I want to see what object I hit if anything if I don't hit anything I'm going to just kind of assume that light is probably going to come from that direction which might not be true like this long ray here might actually hit the building and no light would come from that direction but you know it's sort of a nice first ordered guess and and it can give these nice you know it sort of various or slowly usually from point to point and and yeah you get these this nice effect basically and games use this often use rasterizers to simulate this kind of same sort of ray shooting kind of thing but it turns out with ray tracing you can get ray casting in this case you get a nicer effect anyway long and short it is it's a popular way to do it here's another example。

Is just from this place where things are mostly not occd you can see that you know only one ray is hitting something and you just sort of have this arbitrary cutoff distance how big this radius is and so anyway that that's a cool effect another thing you can do with ray tracing is you can get a depth of field in this case the backgrounds blurry what you're doing is essentially moving where the race starts the ray origin and you' focus you have a point of focus so you're kind of jtering the where the ray is starting it's not always starting in exactly the same place but we've got some focal point that you're kind of a focal distance rather that you're you know aiming for and so you get these things that you know these guys aren't focused these guys not things behind you can also get foreground blur so this person's close this robots behind but we're focused on the for the robot and it's a common cinematography effect to sort of you know。

VDI。The other thing you can do with ray tracing is motion blur this is again part of Cook's work is that he realized oh。

 you know， not only can I shoot bursts of rays to get reflections and soft shadows and so on like that excuse me I can。

Do it over over a frame so let's say this is 130th of the second this frame is this person's moving during that time I can say well okay every time I shoot a array just give me somewhere within that 130th of the second where the object is so the object's moving just lock it in place for that you know at some point during that frame and by adding those all up then you get this nice smooth motion blur kind of effect。

You can also do atmospheric effects where instead of saying I'm going to shoot array and have it just hit something like a wall or whatever be done。

 you can have it instead do a thing called ray marching where you kind of march through the through the scene and just look at each point you go well I want a foot out can I see the sun directly from this point that's a foot out no okay another foot no another foot no another foot yes okay I see through the crack in the ceiling and that place is illuminated and so you can basically come up with some kind of atmospheric equation some inscaing of scatterttering kind of thing where you're basically saying okay light is hitting sort of。

Dust in the atmosphere essentially so you just come up with a dust turn and by then walking through this beam of beam of dust essentially it's catching light so if the beam is thick you're going to catch more light so if it's a bigger beam you get a stronger effect and so on。

Another effect is it's where you get this sort of reflections or refraacts within of swimming pool。

 it's common kind of effect。And this is called caustics。 It's kind of a weird name。

 Caustics to me usually means something like a it's， you know， like a live soap or something。

 something that's causing your skin to get rough， right or it's some acid or something。 anyway。

 but caustics here， it's an optics kind of a thing where。

And just means light lights gathering and something you know some kind of refraction or something is happening or some kind of reflections happening to focus things focus beams so this is actually a clever。

Tricky hacky kind of thing if you wanted to look it up it's in the first ray tracing gemMS book。

 which I'll mention is free online for download。嗯。And it's sort of just this clever way of redirecting light so you can get this beams of light and this caustic effect on the ground and so on you can also brutefor these things this is using PBRT known ray tracer that you basically are just shooting lots and lots and lots of path traces to see where where the light gets focused from there's also I won't go into it all but there's this sort of flipped idea where you really can cast rays from the from the light rather from a light source and kind of shoot them through various you know refractive objects like these glass objects and then you deposit that that light onto various textures so you sort of texture to the whole room shoot a lot of rays you know have them go through the refractive objects and wherever the light goes through you kind of cache it you basically say oh okay I got some light here here here at the focus point and then you can do sort of a four。

R trace or you can do a raization or whatever you want to do to kind of catch all those effects。

Did you know you'd go and hit that texture and say， okay， how much light did I get there and so on？

Anyway， so there's variance on how you can do raycasting you really can't cast from the lights。

 but that can get expensive as far as a amount of rays you shoot and a amount of texture， memory。

 ettera， et ceter。So this is like the danger of caustics of excuse me。

Is I point this out because if you're like me or you start to gather a little chapeas of like。

 oh I'm going to put this cute little thing on on my windowsill and you know these will be you know fun little things I can stare at and contemplate you know what the material is or whatever and so long ago I was given sort of a made up award and like the I figure there's the spherical aberration award or something and。

You know， it had this base， this little wooden base and a sphere and the problem there is that I had it sitting in my office you know on the southern exposure and then I had Western exposure and when I moved the third time I noticed oh wait。

 you know， look the sun is focusing on these various points and is burning holes in the base and luckily didn't cause the thing to burst into flame and you know burn up the building that would have been what we call bad and so anyway。

This is just a warning to you don't you know don't put these things in your window and there are actually stories you'll see it every now minute in the news something about you know someone caused a fire to occur due it to a snowb that they put in their window for you know Christmas or whatever and that focused the light somewhere and caused a fire so beware。

You。So anyway， here's ray tracing techniques， there's a bunch of things you can get and you starting to see these in various games like us so cyberpunk has a lot of lighting stuff going on and reflections。

 control， that's a great game however of that game。

it has like reflections and allkin but a cool ray tracing going on Metro Exodus。

 shadow toator on and on basically there's a bunch of tius portal the sort of reboot a portal has a very cool ray tracing going on so you know it's a usable it's a usable technique for real time。

嗯。So now I'm going to talk a little bit about hardware。This chart only goes so on so far。

It kind of continues and it's like Moore's law you can argue about Moore's law a whole bunch you know it's sort of fine for how many transistors you can shove onto a chip some people say even with that transistor count constantly going up well the chips are getting more expensive so you're not really getting the full Moore's law effect where we were doubling counts every you know two or three years but the price was the same well the price drop you know the price of making these things is not necessarily staying the same but you know argue at how you will there's sort of this other way of looking at at Moore's law。

And you know NviDdia sort of points out well gee， we think Moore's law is ending and this is actually a slide from a Google talk so it's not just NviDdia that thinks is that we're kind of running out for various reasons and like I say of course the notes for this slide that are on my website you'll see that at the end of this and you can download this and look up you know what they're about and why they think this is you what these various things mean but basically we're kind of getting to the end of just a general GPU until of course we'll tell you different and that's fine you know we each have our different view of the world but NviDdia's NviIdia's angle is well you know the way you get around Moore's law is you parallelize things and and luckily happily ray tracing is kind of embarrassingly parallel。



![](img/d6074904415e109acbca87dc2ee02c9c_8.png)

There there's a great little story I show this shot because there's a great story of Turnerwited you know one of the you know fathers of ray tracing kind of thing you know was asked hey gee。

 how can we speed up ray tracing know this is nice process but it's darn slow and he's like oh。

 it's simple you just get a bunch of cr computers where back then the supercomputers of a time know in the 80s and you we put a red green and a blue light bulb on the top of each one and you have each cr computer just compute a pixel and have it just constantly be updating those bulbs on the top of the computer and then you just fly good your blimp over you know over the field and know there you have it you have a realtime ray tracing oddly and no one really did that but we have you know NVDdia like about five or so years ago came up with hardware and others have done this and mean it's not really others have taken a shot at trying to have ray tracing。

Harware， but NviDdia seems to be have gotten you know fairly successful at it。

 but it's been you know this has been this isn't really new in a certain kind of sense it's sort of an idea that's been done since the 80s of like well how can we special purpose hardware so Nvidia basically。

The kind of special purpose hardware on a GPU there's certain little bits but it tends to be lots of shaders and it tends to be these you know how many like these shaders that are kind of general purpose and that you can use in various ways。

 but what NviIdia decided to try one generation for Tring is to add a tensor core which is for artificial intelligence is basically a fast matrix multiply kind of a thing。

 and then an RT core。

![](img/d6074904415e109acbca87dc2ee02c9c_10.png)

Whihich I'll talk about。So what's the difference betweenization and ray tracing well restization you this idea of you draw something and that's basically sending a triangle to the screen Btex shading modifies the vertices possibly basically transform it to camera space or wherever whatever space you're using and then you rasterize you figure out which pixels get covered by the triangle and then you shade them and then you' that's basically it and can you know you can sort of link these rasterizers together but it's not sort of a tightly bound kind of a system although it's getting that way actually there's sort of this new idea called work graphs that is trying to make that happen where you can kind of have shaders talk to each other a tire kind of loop but ray tracing has this idea built in now with past few years where you're sort of saying well the shader can go and then we can have things going on or you're tra traversing and intersecting you find out way to' hit and then you want to shade it。

You can say， well， I want to recurse， I want to shoot out more rays for refraction or reflection or shadows or whatever。

 and you can have this nice loop。And so that's actually sort of part of the direct X API Vulcan API。

 and this part at the bottom is kind of what's put into hardware is this full traversal intersection。

And so we'll talk about that more， but to start with。

 I'm going to just talk about the trend which is just and I only go so far because just it kind of keeps going after this。

 but it just depends on what hardware you're kind of talking about I mean these DGX things are just these giant boxes that cost the price of a house where you just shhoveel a bunch of GPUus and I'm going have like Nvy link or something just interconnect so that all the GPUus can talk to all the other GPUs memory and so on so it kind of certain at a certain point becomes kind of meaningless how much memory。

 but basically on a GPU itself you know they sort of have gone up to 24 gigabytes I don't even know what the new high number is for a single GPU but basically the trend is up and up and up but you don't need that you don't need that those gigabytes really for the screen there's only a few really megabytes that you need for a screen so the rest of it is to store stuff it's to store triangles or whatever。

And so we store you know lots of triangles yes， but also we try to storing stuff that's useful for retracing just to give you a sense of how much stuff there is out there unrealal engine to this thing of the matrix awakens which is this cool demo anyway you should go check it out。

 but there's lots and lots of content and so they have a whole elaborate rasterization system that。

callled naite that tries to take care of this and gives little detail and so on and it's very complex for rasterizer kind of thing but gives you these you know amazing kind of cityscapes can really handle a lot of stuff the nice thing about ray tracing is it turns out you can kind of bundle。

Things together in a hierarchical way that makes it instead of having to send every single triangle down the raurizer which is what you kind of have to do with raurizer again there's some tricks you can do things to kind of cull out stuff but with race tracing it's kind of built in that you're kind of doing this login process where you're saying well i'm going to make this a hierarchy so the idea here is that。

Given these five objects， I would say let's just make it simple sort of 2D idea here， I have a。这吃的没。

Iric， I think we lost you again。It。嗯。Ea， you able to hear her？好。可。对。当然。Eric。

 can you hear us you might be on mute it disappeared again for some fun reason， so hold on let's see。



![](img/d6074904415e109acbca87dc2ee02c9c_12.png)

Let's do it again this is my choice yeah we'll keep going here as fast as I can Okay so。😊。



![](img/d6074904415e109acbca87dc2ee02c9c_14.png)

's see what was it so yeah basically we have this idea of a bounding box or a bounding volume this is a sphere let's say and the idea is if you hit the sphere then you look at the nodes within it。

 if you miss the sphere like a ray just misses this tumo sphere well great I'm done I don't have to look at any of the objects inside and and so like you know let's say I'm shooting a ray from over here and it's aimed at the yellow guy okay so it would hit this root object it hits this sphere and it might hit this bounding sphere maybe hit this one too but basically it says okay well then now I have to actually test these two objects with my ray and eventually find out I hit this yellow object but what's nice is know cold out along that process of all these other objects。

Another sort of more 3D view of this is。This where I have this sort of nested set of boxes where I going to be a large boxes。



![](img/d6074904415e109acbca87dc2ee02c9c_16.png)

Okay。嗯。E quick we can still see and hear you， we just lost this beam。Okay， let's try this again。



![](img/d6074904415e109acbca87dc2ee02c9c_18.png)

Still see and hear me， but you can totally understand that。

I'm just going to continue and hope that this works all right。😊， so anyway。

Let's see yeah so right so here's just a 3D view using boxes and you can have any number of boxes at any different level。

 whatever you'll see within hardware there's sort of various configurations。

 but basically the just is that you're able to do the same kind of thing and get down to a box and then within that box and might be a bunch of triangles and you shoot your against all those triangles and you find one that it hits and you can parallelize this kind of a thing like you could shoot you know eight rays at once and and hit one of these triangles。

嗯。All right so let's see continuing on so that's yeah the the ray tracing cores in hardware what they do they do three things they do instancing which I'm not really going to talk about other than say instancecings where you can make copies of objects very easily without having to like load all the geometry again you just say I want another bond here or whatever but the two main things that I care about are that it's doing this bonding volume hierarchy traversal and it's then shooting against the it's then intersecting against the triangles themselves like I say there's lots of different primitives you could use but triangles are extremely popularrasterizers it's kind of all you ever do sos that's the focus here is that we read a triangle intersection so。

You'll see within the direct X。12 okay。Let's try it again。Oh gosh。

 I don't know what's going on here Take your time， I think it's all good。Okay。

 let's just keep trying here， all right。诶。Anyway， so there's these five kinds of shaders re generation is you sort of controls the other shaders。

 intersection shaders are ones that you can actually make for array versus a sphere。

 and then there's these others calledMi closest hit any hit which I'll talk about a little bit more。

So。Let's see here we go that you could have this sort of。

I fry version of this whole you know process， but I'm going to give it this sort of trim down version。

 which is just simple that you have this simply you have this one shader that's creating rays。

You shoot it against the traver acceleration traversal structure， so it basically says。

Go hardware tell me tell me what I hit and hardware goes okay I went through this bonding box there were no triangles there next boing box and so on go through all that。

 find some triangles intersect some eventually hit something when you hit something you kind of have a choice you could either have this thing you know sort of loop back here and I'll say why you'd want to have that normally or why you'd want to have that in a minute but normally what you do is you'll hit and you'll get the closest hit and then you'll go use the closest hit shader and or if you missed everything that's gone through the entire traerssal and missed everything then even another shader that says well what happens if I hit the background。

And then you return， so that's that's kind of it in the nutshell。

 but this loop I'm going to talk about a little bit more。So this loop。

 what's going on is what if I have like a scene like this where yeah， there's tons of geometry。

 there's also geometry though like for all these leaves like oh my gosh。

 these trees like there's a zillion leaves here， I could make up a zillium we use but a common heck。

Is to try to simplify them somewhat at least and you know on maybe a full basis what you do is you just make a single qualateal and you apply a texture to it but it also has an alpha channel so you can see if the object is hit or not and so that's what any hit shader is about is that you go through this you hit something and then you kind of have to jump out of the hardware that hardware that's this acceleration stuff where it's going through the hierarchy shooting triangles and stuff and it comes out here it goes it says okay I'm going to look at the texture it it's a separate shader it's a shader that you has to go look at the texture。

 say okay my ray here okay I didn't really hit anything continue on you know keep going and you know keep moving that ray along so this can be a slow process because they're going from this sort of hardware ray tracing structure like this specialized hardware and then it jumps to a shader and it jumps back and that's。

Something you'll see like call a duty people you know say that's their number one headache。

 for example， is that this sort of jumping back and forth can cost time so one thing that's been added in newer hardware is this idea of basically having like a low res。

Kind of a structure top of on top of these guys that basically say。

Here you know when you when you shoot array against these things you don't have to jump out of the hardware necessarily out of that accelerator that super fast accelerator what we'll do is we'll go look and we can have these different states where we can say oh this state oh you definitely missed just continue here we have ones that are fully occluded like the leaf is definitely hit so you'll definitely want to go say that you've hit you know you definitely hit the leaf and then you have these indeterminate places where you have to you know maybe go to the shade or and decide so anyway this kind speed up this kind of opacity kind of rendering。

There's other new things that have gotten added I won't go into them too deeply， but such things as。

Taking you can make a mesh and turn it into a micro mesh where basically you're taking a low res mesh a low re triangle and turning it into a bunch of little triangles you can also do cool things like motion blur there's some support for that anyway that's a whole that's a whole separate animal。

Let's see。And right， so like you can use that kind of micro mesh stuff within nanoite possibly to do level detail kind of thing where oh。

 okay， I've had a single triangle from far away， but if I get close up。

 I can have this very highly meshed surface to catch some detail。

So anyway that's just a way to help little detail anyway so that's that and there's other clever things you can do well that the hardware do for you。

 which is well ray tracing is embarrassingly parallel well in practice actually what's happening within shaders is this idea of you're making warps which are you're basically saying you have a single shader multiple multiple data so it's you know it's a sort of a single program but it's。

Executing on the same you know executing on a bunch of different chunks of data at the same time。

 and so the problem with doing that is that you can get。

Divergence you can get basically some ways are going one direction。

 some ways are going another direction， and it starts to。嗯。



![](img/d6074904415e109acbca87dc2ee02c9c_20.png)

Erica， think you're in but on mute and camera off。Each。Yeah， there seems。

 it seems to think there's two of me， unfortunately。啊。Can you still see my screen？

No we no okay well I'm going to and I really try to quit and zoom math well I don't I've never had this problem before this is all known and improved here lets so let's see if I can wanted to see if the other is okay。

😊。

![](img/d6074904415e109acbca87dc2ee02c9c_22.png)

对。Right， I think Alex's trying to reach that Zoom， so we just give it a minute。

you guys have questions， you know， free speech to pause Eric can ask and like the direct text。

And real time ray tasting is not something I cover in soedX the expert literally written books on it。

 so use the person to ask if you're in。😊，Yeah so much。

back yeah this is crazy've never seen to do this before lucky me I think I think the electrician's been messing with the wires let's see。

😊，Okay， let's try take 25， okay， so anyway。Excuse me， I won't go into this too deeply。

 but basically the idea is that。Internally， we can kind of see where rays are getting。Excuse me。

Getting issued and underneath the hood。You can reorganize those rays during the frame to like give more coherence to basically say hey。

 all these rays are kind of going the same way and let's have them all shoot the same way and that's just something that the hard work can just do and it give you it's nice it can give you like a 4x faster boost because it's not having this divergence problem。

So anyway just to hark back to old hardware， I was very excited once upon a time in back in 1987。

 I put out this I put out a bunch of these what are called standard its called them standard procedural database models there are about five of these and basically the idea is well instead of just like the internet used to be slow you used to use a dial to get to the internet 300 bo you know and and so。

Instead of trying to send down large triangle models I said well let's just send down a few like a little program so a little procedural program that can generate as much data as you ever would want so anyway I came up with this stuff I released it a few like two weeks before SGraph and I was very excited to surprised really I didn't know anyone had actually compiled the code over me come to SigGraph and find out the AT&T pixels machine people had compiled it and were showing this as a demo。

We also had the first sort of interactive ray tracer I ever saw where it was a plane and a sphere and you know with a machine where $200。

000 you could move the sphere on top of the plane and see reflections in real time it actually had a mandle on this plane but whatever anyway now you can do this you know on your phone I mean it's you know there's I made a shader or to it you just prove it to myself that runs on my phone and I can move the sphere around interactively anyway yeah you know computers got fast so。

What was nice was you know once upon of time back way back when you know the 7000 sphere thing took 30 seconds later got it optimized to have 16 seconds and anyway so you know that was that was at the time like wow that's really amazing like it would take me hours to generate this image so that was you knowoo really to professed。

So when I joined Erica， we have a question here。It kind of technical question oh。

 this is this is Michael， talking Michael。嗯。It's not a technical question。

 but is the AT&T pixel machine， does it still exist somewhere out there？I don't know。

 I don't know if they I think they're yeah， that' a good question of any do exist like I know of people gutting them and making them into refrigerators and stuff like that。

I don't know I'll ask that about that I know one or two people worked on it and yeah I'd be curious if there's still one out there you know that actually works。

 I kind of doubt it， but anyway yeah that that's a good question I have no idea is the answer。Anyway。

So it turns out yeah， so I joined you know I joined NviDdia and I said oh I'll give Tring a shot with sphereflake their first generation and you know wow this is nice you I could actually do 60 frames per second at a much higher as and I could do it at 48 million spheres you know so it was really cranked up which is way more spheres than there are pixels on the screen so anyway this just trying to take it to the limit I think beyond that I ran out of space and I could have gone further if I used tricks but good enough what more impressed me in a way was just' not impressed me was like oh yes proof that you ray tracing has has some advantages which was to do things like at a soft shadow。

It took me I'm not a very fast coder but this one I knew what I was doing or I knew what I wanted to do I knew what function I wanted to use and so I just wanted to like vary the ray a little bit I wanted to make it so that instead of shooting a shadow ray at the light I just said well shoot it somewhere at a light just pick a random spot you know within that area。

Within that direction just jitter it a bit just hack it and that took like you know 20 minutes to add that code file run and C it actually works to get soft shadows and so you know you have to shoot more rays to get really nice soft shadows as I've shown but nonetheless by just a little hack and the code you get soft shadows which soft shadows and a rasterizer you have to do a lot of hacking to make them look halfde so hemisphere lighting again just a hack saying oh I'll just shoot array ray anywhere on the hemisphere let's just shoot a whole bunch of arrays shoot them all towards the hemisphere at various angles and add up at summit up and weight it by the cosine so that lights directly overhead are more important then ones near the horizon and whatnot and again like you have to shoot lots more rays but codewise it's not a big deal to do that so this is a softer shadows is the hemisphere and I can also do this depth of field。

Bluurry stuff again just jiting the initial location and so it's just kind of cool to realize these effects。

 which can be。Either are very hard or impossible in a asterizer， but just the general feel is that。

 hey， ray tracing is flexible， you can do all kinds of crazy things。嗯。

I am not going to really talk about the rendering equation except to put up the scary equation on the screen but to point out that it's really not a scary equation that the Ranging equation is basically this equation that's saying well okay given some sort of point in space you know you know how much how much light am I getting essentially from a direction or from a point in space is what it comes down to well if you're staring at a light you're getting this much light。

 otherwise you're going look at the surface or whatever it's getting hit could be you a piece of dust this could be an atmospheric kind of effect you're looking at it and you're saying well what light is coming into that what's the material and how does it respond to that light。

 the incoming and outing directions and then there's just a weighted term for geometric term but the point here is that this is recursive it's basically saying what's the incoming light well that's what path tracing is about you're shooting another ray and trying to pick up some incoming light and you're doing that a whole bunch of times。

So that you get this integration of all of these different paths that are coming in and you know or all these different wayss that you're shooting to get this equation so it's this recursive equation very expensive to fully solve as we saw you have to just shoot tons of rays and hope they hit a light eventually but we you know that's the excitement is well how do you simplify it so for example with quick to。

They took the quick two assets and said， hey， what's。You know。

 let's make this a ray traced game and so you can get effects。嗯。Eric， we lost your screen。

 but we do still see you。你くでた。You're on mute， unfortunately。Just think so I'm still sort of here。 I。

 you can hear me。Yes， okay， okay， yeah just glitches， Okay now now I know the trick。

 I don't have to restart zoom re time。嗯。Let's see， all right， let's try sharing again， Okay， great。

 all right。All right anyway so right you get those beams of light effect and the trick there is what they're doing is instead of I don't have a picture for this。

 but just imagine is that as you do that path trace what you do is it's basically this idea of next event estimation that's the technical term next event estimation but。

All it really means is that well instead of just taking the path and bounce bounce。

 bounce bounce bounce and hope I hit a ray or hope I hit a light rather every ray you basically say well I'm going to send rays towards the shadows I'm always going to take that shadow turn into account essentially and I'm going to shoot these rays at the maybe the nearest or the closest few you know lights or whatever so something that basically says hey I know lights are way more important than just bouncing off the walls so let's just make sure after each bounce that I pick up some light from those so that has that's almost everybody uses that and it's sort of the same way of doing things and so that's really sort of the key thing with a lot of this path tracing and getting this sort of global illumination effects is trying to figure out well where do I shoot those rays so like with a mirror array you naturally just kind of want to sample in the reflection direction。

A light could be overheaded， but that light is not going to show up in a perfect mirror only what's in the reflection direction for a glossy surface。

 I'm shooting a burst arrays for a diffus surface I might be shooting ray and who knows what direction from manx path。

And so what that brings up is this idea of what's called MI multiple important sampling and the idea is there is indeed let's shoot towards the light for a mirror reflection it doesn't matter if you shoot towards the light but for a glossy reflection that shooting towards the light you can weight those basically you can kind of say well in that direction I know I know what the response of my material is so this light does have an effect because it's in my little lobe it's in my little reflection direction kind of area of interest and for a diffuse well all lights are of interest so again you can kind of you know weight these things so this picture I won't spend a lot of time on but I think it's worth a while to to go look it up and just think about it and think like but now why am I getting that result because it's really great to like just sort of get you mental model straight you know that you basically have shiniest of the surface increasing and the radius of the。



![](img/d6074904415e109acbca87dc2ee02c9c_24.png)

Is the radius so the radius of the light as you go from left to right is increasing and so if you think about these you're like oh okay this is a kind of a mat surface it's not like this one's perfectly you know reflect and so on and so。

You can kind of think well what what happens when I'm using the BRDf that's the lobe of how the rays are getting shot from the surface and hows it you know how does it work with MIs where I'm actually thinking about the white contribution anyway I won't belabor this one but this one's a great sort of mental like。

If you can look at it and know why that's happening up here versus what that's doing done here。

 then you're on the path to enlightenment as far as what MIS is about。



![](img/d6074904415e109acbca87dc2ee02c9c_26.png)

So it turns out like I say， you might shoot 5，000 rays or 5000 paths samples per pixel so you might take 5。

000 samples。P pixel to get a nice image that that's you know that's kind of what film people do you can see after just one sample not so great four samples that's getting better 16 better 50 better but still awful awful lot of noise and you're not going to get to shoot 50 raised per pixel in a realtime setting so what do you do。

What you do is you denoise so you're going to start with a noisy result and then you reconstruct using that noisy result denoising is a really old process actually it's something that we've thought about you know getting rid noise is decades and decades old but this is one of those where I don't know if fitting what'll get the reference but there's sort of John Henry in the steam hammer I think it was there something where it's like the steam shovel or something where you know John Henry how fast can he shovel versus the mechanical thing well you know John Henry beats the steam shovel but he dies so that didn't work out a great but the point here is that basically people have tried to come up with like hand tweaked denoisers and so on and eventually we realize like let's just have deep learning to it you know it comes deep learning for you is basically coming with a very coming up with a function that kind of trains on a whole bunch of images and then you can inference like you say well。

Giving you this noisy image， what's the final image look like's that's the gist and so。



![](img/d6074904415e109acbca87dc2ee02c9c_28.png)

Here it is in action here only。Eric， we'll still see you， but on mute and。

Need to share your screen again， I suppose。There I'm getting this down to a fine art， I hope。

So I'll be able to do this。Microseconds soon okay so。Anyway。

 here's one sample per pixel for the shadows and it denoyisess to this really nice image。

 And just to give you a sense of I'm going toggle between there's ground truth。

 that's like if you shot a lot of ray per a lot of shadow races per pixel And you can see it really compares quite nicely。

 there's， you know， some little places where it's maybe。对。对。Okay still fashionless my voice。Yes。Yes。

Yestop。Yeah。你 did的 like。Did。Hello again， oh my gosh， this is just terrible all right。

 but's let's holdggle talk really fast at this point。😊，Anyway， let's see。



![](img/d6074904415e109acbca87dc2ee02c9c_30.png)

Get back to this so yeah anyway ground truth if you just tried to do this with rasterization and this this is a raization kind of a view where you're using this classic algorithm called shadow mapping you can only get really a sharp image out of that you don't get this beautifully denised kind of thing here it is with reflections。

The noising versus the ground truth， there is a clever thing you can do in raurization called screen space reflections。

 but you'll notice what it's doing is it's actually reflecting underneath these various objects the reflection you're getting is actually underneath when in fact those objects really should be getting more of a true reflection I mean this is getting light from bouncing the rays around and so on so you know it kind of works screen space reflections。

 people use them but it's pretty far away from the truth。Here's global elimination， one sample。

You get this。Amazing to me result， basically， that you get that whole thing。

here's ground truth and you can see some little differences like here it's not really capturing those crevices。

But for the most part， does a great job。So this whole system is called like DLSS。

 it's for NVIDdia A&D has its own kind and whatnot and basically the idea is that you off you have this thing and then on you can get these very much sharper things like just here it's just showing sharper textures it's not really including much else but it's sort of as well andm getting some asing problems I'm not really sampling this texture well enough to get the letters but here it's able to sort of rebuild those letters。

This has a whole super involved process， which I vaguely understand。

I put some links to various things in the notes so you can look it up。

 but basically there's the gist is is that it's looking at both。You know like motion vectors。

 it's doing some optical flow stuff and basically you're able to， you know。

 it's using a lot of tricks to try to rebuild this stuff。And anyway。

 long the short is is that it means that we don't have to shoot as many ways and that's a happy thing again。

 you know here you're getting faster results， similar quality。



![](img/d6074904415e109acbca87dc2ee02c9c_32.png)

So there's other things that have gone on as far as adding rate tracing support。

 so N video has a thing called RTXDI， it's basically this idea it's called Re。

And past class classes have done。Donone research projects on using research in various ways and research are the basic ideas like you say。

 well this next event estimation it says， oh I should use the light you know I should always be shooting towards the light because lights are significant well what if you have1 thousand0 by in a scene which are the significant lights again so that's what research sort of about is trying to kind of quickly figure out what the important lights are and try to keep sort of a running tally of those and it uses both kind of screen space ideas where it's sort of or you know like trying to say nearby things I'm getting light you know what lights have been found good oh my neighbor says this lights are really good so maybe I'll try that light next time and also over time that over time you know a frame to frame and you go well I'm going to use whatever the last frame said last frame said this was a really good light for this area even though my view is slightly different I can use motion vectors and so on kind of know Ha ge know here's where I think I should be what did I do。

Last frame anyway， that's that's my 22 Easter explanation， there's lots about this on the internet。

Anyway， you can also rest and dennoise and you get fabulous results and won't go into that too deeply and there's another library called RTxGI and not DI which has this idea of probes and what probes are sort of just points in space where they try to capture global elimination sort of say like well for this point in space I'm you know I think I'm getting this much light you know from from over you know west of me okay and here's another point in space I'm getting some other light somewhere else and you can basically use those probes to more quickly try to get。

And you know， those probes can change over time as lights change。

 you basically use those probes to get a gold illumination effect。嗯。

Again another idea is neural radiance caching you won't go into that again sort of yeah theres basically there's a lot of interesting things going on with sort of neural nets and computer graphics speaking of neural radiance there's another cool thing that started basically in 2020 is this idea of nerves and it got to the。

嗯。No。

![](img/d6074904415e109acbca87dc2ee02c9c_34.png)

![](img/d6074904415e109acbca87dc2ee02c9c_35.png)

I think we still have you wasn't a full crash Okay so anywaynerfs are just this kind of cool technique that says you know I'm going to I'm going to try to not just capture a mesh i'm going to basically given a bunch of like a video or a bunch of camera views you get this idea of'll basically just capturing that in this sort of more interesting kind of sign distance field kind of more fuzzier and kind of a thing where you can get like effects like fur and whatnot anyway there's this whole interesting area of。

😊，Instead of just getting a mesh， which the mesh doesn't capture the actual BRDF。

 it doesn't capture what the materials， how it's responding to light。嗯。嗯，见拜拜。好。This is that。

Yes here I have。😀はは。😊，Oh， some other participant， okay。嗯。Okay， thanks。😊。

All right I get it really over now all right so anyway there's nerves there's Gaussian spts。

 this is sort of the hotness from the past year and it's exciting because Gaussian spts like this earlier thing nerves could only really be done with ra。

😊，I don't think it likes that yet。😀谢。😊。

![](img/d6074904415e109acbca87dc2ee02c9c_37.png)

Bo， I would love to know why this is happening。😊。

![](img/d6074904415e109acbca87dc2ee02c9c_39.png)

Okay， anyway。All right so there's nerves， they can be ray traced。

 what's cool is Gaussian spts can be both rasterized。

 but they can also be ray traced which gives you a better I don't want to say a better result because。

Okay。Okay。M man Lord， All right， my theory。H says there's another one going on， I dont understand。

Okay。OhThank you Shaobhan， you figured it out， great。😊，Yeah， you have to kill the other guy。

 I don't know what happens。Okay， all right， so anyway。

 I think what might have been causing lots of those problems right now is just having those little repeating videos so we're past the video so hopefully i'll have a whole five minutes in a row here so anyway。

😊，There's other things that are going on that are interesting not really you know doing with but that again ray tracing can be used to render these things there's a lot of these where you're generating meshes。

 but that's a whole separate neural net kind of thing but the long short is is one thing that's called what we called internally Laons's law which is just this idea of the render is no longer just trying to like spend all its time in every little pixel and get everything exactly right it's really to try to you know collect enough samples that you know some deep learning neuralNe can try to make the picture for you。

There's sort of a corollary which is， you know， if your razor coherent。

 if you're like shooting lots of rays and you're always getting the same result pixel to pixel。

 you're probably wasting time because you're really not getting all that much more inflammation。

 you know， sort of cherish your samples is the accounts of thing。



![](img/d6074904415e109acbca87dc2ee02c9c_41.png)

So anyway。So I'm going to wh through just a bunch of different uses of ray tracing we know it for media and entertainment you know we have these very complicated things you can use ray tracing for and within that industry it just has to look right that's sort of the jing quote of。

对。😊，Thanks。

![](img/d6074904415e109acbca87dc2ee02c9c_43.png)

Right。All right。So anyway， Jim Bnn， famous pioneers， and just will look great。

The trick is is that well if you're a designer and you're presenting it to a client and they say well you showed me this really beautiful picture but my thing doesn't look like what you showed me you know'm you know you'll be hearing from our lawyer kind of thing and in fact I've seen that with architecture back in the old days is that people would not do realistic architectureural renderings they would make it look like the use non photo realisticalistic renderings so they make it look like a watercolor or something else just to make it clear like your building will not look like this because they were you there were liability problems or questions about that so anyway so within design industrial design you know you can get these realistic things and you know pretty confident if you' done done your homework that you're going to actually the final project project going look that way。

Architectural design， again， This is sort of a which one， you know。



![](img/d6074904415e109acbca87dc2ee02c9c_45.png)

![](img/d6074904415e109acbca87dc2ee02c9c_46.png)

Okay， so which one's the real one？All right， let's do it again。



![](img/d6074904415e109acbca87dc2ee02c9c_48.png)

Um，Which one's the real one， u turns out the one on the right is the real one。

 it's not too hard to tell， but they're pretty close。



![](img/d6074904415e109acbca87dc2ee02c9c_50.png)

嗯。The trick with ray tracing can also be used for simulation。

 so this is kind of a famous one of you may have heard of the friry scraper which was I think from like 2016 the architecture firm designed this thing。

 gave it a concave face on a southern facing exposure so did some like rough estimate saying it probably is fine they had the the tools were available at the time but they did decide na it's going to be fine and it wasn't fine。

 it basically caused this acted just like a magnifying you concave Mi act and focused a beam of heat。

 you know beam of light onto Porsche。Yes。Yeah。嗯嗯。Yeah。

waitait for the moment when Shazaan frees my screen or kills the other me。Yeah。

 don't believe that guy am the real one。Okay。😊。

![](img/d6074904415e109acbca87dc2ee02c9c_52.png)

all right， so anyway the friry scraper is cool because it you know is one of these where oh they should have done this。

 they didn't do it， but you could use ray tracing ray casting to simulate this kind of thing。

And indeed， here's a simulation。And this is using I think it's yeah using IRA and you can actually get you know physical measurements of where the hotspot is actually redesigned this fact I was in London in the summer and it was great there's actually a really wonderful restaurant at the top of this place you can actually go up there for free and just walk around it's really pretty the go around and it doesn't fry cars anymore what's funny is the architects actually claimed oh well I mean we didn't work real hard on this because you know London's not supposed to be sunny。

 we blame global warming and kind of a laneme excuse but anyway but they were able to modify the you know how the windows were and put in blinders and stuff to make it not melt cars anymore anyway you can use it for things like scientific visualization it's like oh okay this model has 1。

7 million atoms not a problem if you if you use a arraypher interor if you were to use it as triangles that might actually be bad。

It it's probably faster to great this than to try to use a rasterizer。

Same thing you can use ray marching to go and get these beautiful you know kinds of atmosphere kinds of effects as opposed to rasterization。

 not good for that。On and on， I can do ray tracing for design of， you know， like I say。

 a simulation of how light interacts and imaging system like bends as it goes through atmosphere。

You can actually design telescopes using raycasting so anyway there's lots and lots of applications you know we talk about ray tracing and raycasting and that we're shooting photons or you know we're gathering photons or whatever well photons that's that term doesn't just mean visible it means everything from you know gamma rays down to long wave radio and so on and so that means that you can do other things like 60 propagation simulation again it's just you know it's a very simple atomic thing of just ray tracing aperture radar synthetic aperture radar heat transfer。

Let's say any audio simulation， which if you think about audio simulation。

 the thing race don't do is things。

![](img/d6074904415e109acbca87dc2ee02c9c_54.png)

There been runnda。

![](img/d6074904415e109acbca87dc2ee02c9c_56.png)

Oh lucky was I this time， oh good， you go to a total crash。All right。So anyway。

 what's interesting about audio simulation is the fact that it's not。You know， how can I say it？

Sound goes around corners and and so you have to sort of simulate diffraction。

 diffraction is not normally something that you know ray racingcing is kind of goes ray go straight right。

 they don't diffracact， but you can try to figure out tricks to to to do this kind of audio simulation。

 And this kind of simulation is done。 I mean it's it's definitely what what gets used for like bow speakers and all all the other companies I think use some kind of ray racingcing and simulation。

Audio simulation and Dolby uses it， you can also use it for simulation。

 the idea of a digital excuse me a digital twin where you know you can simulate what the what the inputs are essentially you know what's getting seen seismology you can do again can sort of march through the Earth and get these sort of refraction effects as things curve as it goes through the Earth's layers。

We can now use it for collision detection in response using rays to see whether objects see each other by just shooting if you raise and seeing if you you know the other object overlaps you or not。

Now。And yeah and sort of the whole idea of a digital twin where you're basically saying hey I've got a robot I want to train it well I can just simulate the inputs to all its you know it says oh okay。

 the robot has a camera all right， the camera is such and so here I'll just simulate that input to the robot by creating a digital twin by creating you know an environment for it and the robot also will have outputs of like okay no I'm spinning the wheels this much and he have a you know physical simulator saying okay。

 the robot's moved a foot forward now it's got a new view and so on。Obviouslyvi on one level。

 but we're now able to do this， you know， much faster than we used to be able to do that。

 that's basically the just。Anyway so' these are just some of the uses so to sum up we have ray tracing simple enough to fit in a business card and complicated enough to consume an entire career which is is absolutely true it's certainly absorbed maybe half of mine I've been in both worlds of restization and ray tracing over my lifetime so far and yeah the old joke was ray tracing is the technology of the future always will be what I like about this joke is the fact that David Kirick said it back in like I tracked it down on the internet to March 28 2008 this was also the time that he sort of in secret started to try to figure out well what can we put into the Nvidia ray tracing know invidia GPU hardware to enable ray tracing and it wasn't until 2017 that we even got a hint that this was got to happen。



![](img/d6074904415e109acbca87dc2ee02c9c_58.png)

So anyway let's see the other thing that Shazanne said is I should try to give some career advice。

 I'm kind of at the far end of my career and I'm not ready to retire yet I'm actually having a lot of fun but but you know and you got good career advice last week I heard a minute the lecture about insight and so on and they gave lots of good advice as far as you know starting out things to do but I'll give you sort of from the far end of like what worked for me in some sense I like to think I'm successful and success to me is like depends on how you define it I consider a success for me of getting to work on interesting problems and not having to go to lots of meetings are my those are my two criteria you know but if you much more enjoy larger projects where you are sort of controlling know you want to sort of work way up the management chain well that's fine there's people really good at people's skills and they don't want to get you know into the new gritty well that's fine。

you know， for me anyway。I've been more of the I've enjoyed the nitty G so anyway I like this from Pa East you know success a lot to do with luck but if you work hard you get more dice rolls and so my prolish tips on career there's a whole bunch here I'm not going to go through it all but the number one is really make a website for yourself you know if you have one that's like through your school or something which you know you should just make one that's that you own because you won't be at your school forever or you won't be at your job forever or whatever just keep one you know it's sort of a nice add on to whatever your LinkedIn pages and so on you it's a place to destroy your work and so on anyway kind of obvious on one level but I've seen so many people not do that then they move and oh your beautiful website is now gone or is down for a month or whatever as you try to scramble and put it somewhere else。



![](img/d6074904415e109acbca87dc2ee02c9c_60.png)

Anyway， yeah so there's's basically all the rest of these are volunteer in some way or another so this is one thing I volunteered on a few years ago there's a group called the forget the full name of it but basically it's the Academy Award software foundation and it's just a nonprofit group it's you know it's basically a group coming out with various tools for people within film to like to test their software or whatnot so USD is this sort of new file format universal scene description it's a very complex kind of file format you know I'm lucky in that I only have to write out a file format like in the applications that I've been using it trying to read this stuff in is quite the task。

😊。

![](img/d6074904415e109acbca87dc2ee02c9c_62.png)

And also just understanding what a lot of it means is quite the task so my contribution to the cause was just to come up with a little Minecraft scene。

 I like Minecraft it's a nice it's a nice way to test out textures。

 you nice simple blocks but you can have very complicated you know textures that very gloss or very you know very all kinds of attributes so anyway。

So this was just a scene that I gave using the USD file format as a way of saying， hey。

 if you're not getting something that looks like this， you're probably doing something wrong。

 I must have a whole one for just testing this normal map bias and scaling within USD which turns out to be a feature that some people implement some people don't implement it varies so anyway。

 so having this is a way to just quickly know gee， does this renderer actually implement this feature or not and does it do it correctly。

So that kind of thing， you know， it's not like anyone paid me to do it or' you know people were like。

 oh yeah great， yeah， let's let's look it over and you know you can fold it in wasn't there wasn't a lot of process it's more like。

 oh yeah， let's let's add that you know if it's useful， let's let's get it up to the community。



![](img/d6074904415e109acbca87dc2ee02c9c_64.png)

嗯。So my advice for at work is ask questions， you know like try to do a little bit of work before you ask that question perhaps you know if it's something where oh you scribble down the term。

 go Google it and see oh okay that's what the person was talking about fine but you know if it's something where it's like oh I'm spending half an hour trying to figure out what you said that's way too much time you know you know if it takess somewhere more in a few minutes。

 please do just ask the person what you what they were talking about and you know like I say everybody's ignorant about almost everything so you know get over it。

Anyway， yeah as I leave your ego you know leave your ego behind kind of thing and people usually are you know want to help you and will'll try to help you you know solo is fine failing solo is fine failing with others is less likely you know a diverse set of views is good this is actually pushed a lot of video I there's some other。

Acronym， no law or something like that， no one left alone or something like that where you're basically saying you know。

 you shouldn't have somebody just going off and not ever getting feedback and so on。

And enjoy the ride like there's sort of this great book I read last year about this time called 4000 Weeks where he basically says I I it all。

 you know， for years I read about selfhelp books and you know I read these self-help books trying to help myself and his kind of point is like I mean it's sort of a good book like you should read the first chapter。

 you know， maybe not read the whole thing it's kind of repetitive at a certain point。

 but you know he has some really nice ideas about you know what？

What's it about what you know what what are you trying to do you know what's your goal in life in certain kind of ways and you won't get everything done so you only you' have you know maybe 4000 weeks in your life use well anyway Alex Trebek from Jeeopardy I'm old I watch Jeeopardy now and then anyway。

Let's see we're all experts in our own little niches and that's what you you know you are becoming right now an expert at Kuta or knowing something about Kuta that most people don't or and anyway that kind of thing where you undoubtedly through your life I have a bunch of little niches and that's great stuff to have and finally yeah you know I feel the'm not I'm agnostic frankly but the Old Testament I think nailed it you know let someone else praise you。

 people who praise themselves I won't name any presidentialial candidates at this point but people who praise themselves you know it's no praise at all you know you're not fooling anybody and it just looks bad it makes you look kind of foolish to be praising yourself。



![](img/d6074904415e109acbca87dc2ee02c9c_66.png)

And that's about all I have i'm gonna just finish i'm happy I didn't having more crashes but there's yeah there's a bunch of free books on ray tracing out there you know what's nice is that math doesn't lot you know like stuff that you know this books from 1980 something I don't know 8987 something like that but the equations are they all still work you know array versus the sphere still works anyway and yeah this graphics codex is a really nice resource it's this website where it just has lots of basic equations in basic。

Oh it。We are almost there。

![](img/d6074904415e109acbca87dc2ee02c9c_68.png)

Oh， you're muted。I know so close， I was on the next last slide， I think it must just be the， yeah。

 maybe it's just complexity of slide anyway。😊，😀All right， so there yeah， I'm Dar W。😊，嗯。

Sorry that took five minutes long ago I appreciate you surviving that， but anyway。

 so I'm done and yeah that's where you can find more stuff and you should be able to。Yeah。

 if you if you go to Ericricmix com we can download the slides and then in the notes I have lots of links to other resources which hopefully help help you out Oh on one of those slides I had it quickly said you know。

Like a pet peeve on me with me for LinkedIn is where people will just say I want to connect with you and they don't say why you know my advice to you is to spend that extra minute saying I want to connect with you and then put in that little box that comes up saying do you want to say something that person I always say something to that person unless unless it's like a relative that knows you or something you know because you know other than that it's just you're some random person out of the blue and if the person doesn't remember who you are good luck you know anyway so。

That's about it。 Sho， Okay， that was longer than expected， but there you go。Thank you。

You're getting arousing applause here thank you for the talk I see the talk evolve over every year and great to see all the new content you' added id and so much today we can open it up for questions again。

 go as technical as you want or you can go the other way and ask for career advice。

 Eric here he always does a fabulous Q&A so you use him as a mentor with a tremendous amount of graphics experience in the industry。

😊。

![](img/d6074904415e109acbca87dc2ee02c9c_70.png)

So who ask the first question？嗯。This is Michael。对。I have two questions。

One's a bit loaded potentially， one's is just like。About Minecraft， but like。

The first one so you probably know that we're doing implementing rateres right now KUa right now so like。

One of the core features of the rate of the assignment is like， okay。

 you have to implement perfect diffuse， you have to implement perfect specular and then you have to implement。

And I think you have to implement an imperfect specular they gave us this like a couple equations from GPU gems I was like。

It's kind of like a thong based。BSdF， that was like generate this kind of below right random。

Bhing and。I think I did all that， potentially。I implemented a thing that like a like GLTF floater。

One of the aspects of GLTF is the。Metallic roughness map， the BRDF implementation of it。

And I'm looking at the spec and like it's like， oh， BRDf， you know。

 they're split up into dielectrics and metallics and use the roughest map to like kind of mix And I'm like。

 I've got this perfect diffuse， perfect specular like three different like。

Types of materials I've got。 And I'm like， I don't know if I've got enough to like sort of。

Do that and I don't know， maybe you could talk about that。Yeah。Yeah，s here's the bit I know。

 which is that so yeah， Fong was one of these where he just sort of hacked up this idea， you know。

 many， many like 50 odd years ago， something like that。

Of like oh you know we'll just use this sort of you know cosine raised to a power kind of a lobe and people then you know as time went on and physics you know physics experiments were done and people measured materials and so on they realized well it's not really like that and there's also just some problems with。

呃。Yeah， like it being， I do I to say conserving the amount of energy like。

You know that lobe can get big and small and so on。

 but there's no sense of scale like how much light is actually you know it's it's trying to simulate how much light is bouncing off the surface and you know as a whole and so anyway basically I know like open PBR and GLTF and their PBR system and so on these kind of a different thing like you say they're sort of this dielectric which just means you know there's things that conduct and things that don't conduct like metals conduct。

And that that that's。That's sort of one variable and then the other variable is just a roughness kind of parameter and usually like the dielectric is usually on or off but some people will allow you or some models will allow you some number in between which is kind of funky on a theory standpoint as far as i'm concerned but you can kind of justify you go well it's rusty metal on something you know it's like some kind of mix or something but。

Anyway， the longest short is is that yeah， the sort of modern physically based rendering surfaces have these different equations and the sort of one is Smith or sometimes called a GGX。

Is you'll see and it's just， it's just a different function really， it's not， it's not scary。

 It's just， oh okay， there's a different function than this sort of simplified F you know。

 cosine to a power kind of deal。 that's， I don't know I don't I say that's about it。 you know。

 there's definitely resources online where you can， you know。

 go look at the open PBR spec or something and see what equations they use。Okay， that's fair cool。

 thank you。My second question was just about boxallia。No wow， that's an obscure evidence。Go for it。

Oh it was just like how's it going how's that world going Yeah yeah。

 we were Minecraft nerds back in 2010， something like that when Minecraft Beta was first out。

 we got a bunch of geeks together， yeah， maybe I don't another you know 10 people or something I'm proud to say like you know one of them。

 one of them is now you know， like in research at Robblox， Morgan McGuire so he' done well。

The other people are like you know， they were mechanical engineers， there's one guy who is a。

Basically translated German to English technical works and so he didn't really have an engineering background per se。

 but he became like brilliant at like doing electronic systems so so I love that game because it has all these weird systems anyway long and short for me was you know we kind of did it all for about two years and then we got burnt out and then we all a few of us went off and did things with it like and so。

Me I won' often made this program called Minly so so that that that is done you know I try not to touch that i've gone through the 12 steps i've you know i've tried not to touch minecraft since that and get sucked back into the addiction but。

But honestly you know it's a brilliant game， I mean I just saw the PC gamer100 top best games you know Minecraft still number four and disturbly so。

 but anyway， long and short is for me my giving back to the community because a lot of people were giving back like just making mods or making voxelizers or whatever one of our group made of voxelizer。

 I made this program called Minways which basically let's see export stuff。

Now let he exports stuff in USD with complicated models and so on and the funny thing about that is that it still gets like it's you know like1 thousand downloads a day。

 which is I'm really happy that it seems to work because luckily I only get maybe one user a day writing me about some little technical detail it's like oh good you everybody else is either downloading it and not using it or using it and you know not caring or whatever so anyway that's I think that's you know like you think oh maybe I'll be known for this someday and I suspect on you know that's what I'll be known for someday is oh you know he wrote mineways okay。

Very cool。对。Thank you。Hello， this is Matt speaking。Pretty general question。

 I'm just curious what you are excited about for the future of ray tracing。Or technology。

 any of that。Yeah， yeah。 Good question， really。 I know it's sort of like。Yeah， for me at NVIDdia。

 it's just been kind of like nose down upwards and onwards trying to figure out new hardware features。

So my sort of wider view of the world like like I take a wide view of the world about every 10 years of you know we'll write a new edition of realtime rendering so we wrote a fourth edition in 2018 I think came out something like that and and so that was you know it's not it's not 10 years yet we're eight years when we start writing a new one and so yeah it's kind of fun I've kind of lost track of the wide world in a certain kind of way I mean what's exciting to me like I say like that's sort of stuff about nerves and Gaussian 3D spts I think that's to me when the more exciting things is like just saying you know there's more life than triangles you know like let's look at sign distance feels let's look at you know voxelization let's look at you know these Gaussian spts which are really just kind of 3D little ellipy things that are kind of puffy clouds you know you put enough of those close enough to each other and you get a surface。

And you can also encode in those little puffy clouds you can have a directional component to the material so you look at the puffy cloud from one direction it's dark brown from another direction it's you know a light tan and so on and that's capturing the reflectivity of the thing and so I think these sort of alternate ways of doing things it's just it's interesting know it's like like that that ability to capture it like that is really powerful because you can do the sort of you know I mean people are using it now for real reallife things where you you capture a room or whatever and instead of just having it be all these sort of diffuse surfaces with a mesh and you know not really any material sometimes you can actually capture what the material that start doing so I think that whole sort of material capture kind of thing is really exciting and also the other sort of obvious one is just you know neural nets like they're getting used everywhere。

they're not my cup of tea I mean I've read a bottom off fair bit and you know basically for me they kind of boil down to you do some magical things。

 you figure out a sort of magical numberable layer as you know you set some autoencor here there and you you play with some parameters and you hope you don't overfit and you hope you get a function out and there's people are really good at that and I don't have the patience I'm much more of give me an equation kind of guy but the powers undeniable I mean you know if you haven't heard the word by the word by the way。

 the good word is use coppilot you try it out for a month I'm serious I've seen mixed results of you know of like oh you know like one study says oh you know copilot improves your speed of just you know improving your coding speed by5 to 35% and another study which I saw it just came out today already right just notice the thing today said oh it doesn't help at all。

You know it just makes you into a code reviewer and I'm like， oh I'd much rather。

 you know I have a code I was using coppi today I'm typing code it's saying here's 12 lines of code that I think you probably want and I look it over and go yep those are the 12 lines I don' want you just save me typing know 300 characters nice you so cop I to me is like having a little buddy on the side that just shoves a lot of code at you that sort of says hey。

 when you think about this and sometimes you're like shut up but but it's polite it doesn't mind and you know but other times you're like oh。

 that's actually exactly what I want or oh it's almost what I want and I'll just have to change this one line So anyway it's just like you're a little friendly buddy on the side that you know sort of a really fast typist isn't very smart but it's happy to help anyway that' what excites me is to sort of see you know where things are gonna go both with research and neural nets you know they're all over the place but also just for AIidDs like that or it's like oh yeah is this is helping me do my job great。

Great， thank you and as someone who has copilo open in front of them right now， I could not。

Good deal。Let's。咁拜拜。So I was like trying to figure out what to do for my final project。

 what are your opinions on productive rendering in general and you know all the advances that are going on there。

 I know you talked briefly about like restier GI but like I know there's a bunch of other things going on in the field right now。

Yeah， I know I was trying to think of like， you know。

 I was trying to give you guys actually sort of fodder for projects。And。Yeah I'm not sure in a way。

 I mean Rester is sort of one， you know， it's sort of a thing that people have implemented you know in the past。

 like I say。Yeah， it's tricky， you know， there's just there's a lot of。Nish is out there。

 And it just。I don't know what to tell you I mean you know for me there's sort of a lot of interesting things like I was trying to throw it a lot of here's non graphical uses of ray tracing just because I think there are you know there's sort of a lot of places there where you can use it to simulate other things and I think that's that's you know not an untouched field but sort of an interesting one for me just to see well you know can I use this basic mechanism for something else。

😊，But graphically。You know， I think that。Let's see just just intersecting other kinds of primitives。

 like I say， sort of with the whole Gaussian splats and N and so on， that are these different。

You know nontangular mesh objects out there and it's interesting to try to you know for me would that' be you know if I was like oh I just want to mess around or I want to hobby around a little bit。

 I'd start to dig up some of the old stuff about you how did people use to raytrace you know like quadrics or how did they raytra you know how do they raytrase sign distance fields oh they use ray marching and they do this kind of thing then I think is really interesting sort of place to go another place to just wander around is shade or toy which does a lot of ray tracing kinds of things and you may just by poking around on shader toy and looking at things go oh because they're doing a lot of ray marching there I just saying they're not you know explicitly modeling a lot of their cool scenes they just have little equations that are signine distance fields there are Sarah saying you know given a point given given this sign distance field equation is this point inside or outside of that surface。

alove or below that surface and by doing that you can build up really interesting models and so on I don't know if you know if that modeling paradigm it's time has come but it's an interesting one to think about over another one that's sort of coming back is you know constructive cell geometry where you're taking various objects and subtracting or adding them to each other like you might take a block and subtract out of sphere and well ray tracing is really good at directly doing that kind of thing but you have to figure out how to access that data model and what's the efficient way to do it and so on and so forth anyway。

Other some quick off the top of my。And places to possibly look。Thank you very much。



![](img/d6074904415e109acbca87dc2ee02c9c_72.png)

I不。好么。So。Hi， this is Alan， my question is more like career。Type question， I suppose。

I expect myself to work in realtime rendering stuff more specifically XR when I enter the job market。

 but since I am a new hire， I expect myself to not know much when I go into job and there's so much things to learn so I'll be much more of an active learner and like a practitioner of other people's research and stuff but eventually I would hope to really push the field further and come up with brilliant techniques and maybe do research and convert to research positions or something like that so from based on your past experience and observation in this industry how do people usually make this transition and you know how long do people take to really reach this level of proficiency。

Yeah good question I mean if you're you know if you're going for a PhD in something that's certainly one route as far as going you know if you're like I really just want to do research and that's the common route right is you go PhD and usually you are trying to find a topic that hasn't been explored and that you focus on and you become sort of you know one of the experts in that area so that's you a common way to go if you're just going that way。

Let's see as far as yeah， more like， well， I want to go into industry and then you know。

 possibly get into researchs。That's doable， you know it's possible it just depends on the place and sort of you know what what level research and so on and what is is supported at the place。

 what do they think about researchers is does the person have to， you know。

 some places are very like you know you have to have a PhD I'm sorry。

 other places are like wait you're doing really interesting work on that area。Great。

 you know I want you to continue on and you know I see you've got some you know we've got this problem to solve and again there's sort of levels of research right there's sort of you know like academic I think of more of them looking five years10 years out research at NviDdia is not necessarily directed at a product per se but it's definitely not the oh let's let's think 10。

You know，10 years out so much I there's a few people doing things like that for sure。

 but it's you know there's more of a focus of like oh we're a hardware company could I use this research to you know improve our hardware or or just general you know software that uses our hardware So there's sort of a focus so that's you know a more company directed kind of thing it's going to be a little bit of shorter shorter distance as far as you know how far out you can think So there's you know there's research and there's research and you know and to be honest I see it as a continuum I mean I think like especially well within video I mean not to。

Be all I don't know you know it's the best company ever or anything like that。

 but the things I do like are like that you really there's a funny thing that you cannot look up the title of anybody within NVIdia you can't look up the title of anybody else working at NVDdia you basically you know you can in in the workaround I finally found because I needed to get a vice president to sign off on doing some open source project was that I searched on LinkedIn and realized oh good my managers a vice president I hadn't actually known his title so I was able to get around that requirement but it's kind of a funny thing that。

You really can't look him up you can't know I did finally found working at NVD for about a year after about a year I found this secret link which was this employee graph where you could at least see how high they are in the hierarchy and the hierarchy is very flat and so on and I give it to my manager and he joked at least I think he joked he said oh I never saw this he had been there for 10 years I never saw that link before you know like this is good。

 this way I can see out cool all my reports are who all the people that report me I think he was jodking but anyway but my point here is just that like with NviIDdia there's there's definitely a flow like some people who are officially in research you know they've been hired into the research group our researchers you and they just don't want to get distracted by working on on a release of any kind of software or anything others will flow from research and say hey you know I did all this research and think it's really cool oh wait you're doing a product on it yeah I totally want to you know work。

That you know full time or as a consultant or whatever and that's fine， you know。

 it's just groups find each other and you know， and that kind of flow happens and that's that's anyway。

I don't know what the point of that long-wined story was。

 but the point is for me that it really is this kind of continuum where you know。

 like I'm now doing something I can't talk about， but it's sort of a pure math kind of a research problem which I love。

 but it's very much of applied kind of a thing so you know for me I'm really enjoying it because I'm getting to do something interesting。

But it's not you know it's not just the same old same old which is very rare anyway I mean I don't think any of my jobs have been same old same old except for you know if you the way you can get stuck I guess is if you write a really successful component and you become the expert and that's all you overdo is support that component so I recommend to against that success I've never had that so you know my only success of been mind ways which you know now I have to support that forever so anyway。

Yep， thanks a lot， sure。Eric， quick follow up to that question and maybe keep this short。

Are there any questions you recommend that students ask in an interview that can get a decent directional answer for whether this is the right place for me or not？

Right right， I mean I can think of the bad questions you don't ask like you know。

 how much vacation do you have or things like that？😊，Yeah， it'd be interesting。 I mean。

 I think one that would be interesting to ask would be， you know how。

How do you know what what does your company， how do I get feedback like in other words how。

You know how sort of how do you work you know what's your work process like is it groups or is it kind of like oh you go off and do a thing or you know are there yearly you know kinds of you know formal kinds of you know evaluations or not which can be both good or bad I mean I've heard some companies are like you know well we did our formal evaluation or yearly evaluation and we're cutting the top you know or' we're cutting the you know bottom 10% of the achievement people here you know we're going to push you out the door because you know you're not living up to you know our adult curve here so you know that that can be a tool for for good or evil but yeah trying to get some sense of the。

You know what the company is actually doing I mean most companies you know。

 they like to see that you have skills and so on， you know in my my feeling is that you know。

I'm usually looking for someone who。Who seems to be interested in， you know。

 in this thing it's not just a job in whatever computer graphics or whatever whatever you know that they're looking for and is。

Let's see what are the kinds of things I guess yeah， you know。

 is sort of interested and it isn't just a you know。

Like oh you I'm just here to get the money and paycheck。

 not that anyone ever does that movement's like this is the best company ever and I've always wanted to join you and that's what you say at every job interview right know so you go overboard on that everyone just tones that down like yeah yeah you know this is the one company you want to join shirtsure but on the other hand if it's you know you trying to I think you can show that indirectly I guess is what I'm trying to say which is why I was sort of pointing out like you know having like a web page and saying hey this is what I've done I think that's really valuable what's sort of being able to say oh here's this is really what I've done and this is what excited me about that or this is what you know anyway that I think is good as far as asking let's see one of the kinds of things what I ask。

嗯。Yeah， I guess， you know， a lot of it is sort of work environment and so on if like， you know。

 like one thing。At a company that a were nameless was this idea of silos。

 you know I mean that's the that's the derogatory term where it's sort of like。

 oh I'm in this group and I would occasionally get this feedback like I'd ask someone else in some other group hey。

 can you help me with such and so and they would say I'm sorry that's not on my yearly goals I cannot help you which is just like oh my gosh you know like。

I mean， I understand it on one level because that's what gets rewarded。

 but it's important to understand like if that's what's getting rewarded is like oh well we have you set goals at the beginning of the year and then depending on how well you fulfill those goals that tells youis how much you know we should promote you or give you stock options or whatever anyway。

 sorry to go on and on about this but you know that silo thing that sort of goals I find it。

A little bit ridiculous for most companies anyway， for most really active tech companies like I mean。

 I had you know goals were set for me one year at a company and within about a month after setting those goals that project was canceled。

 So what am I getting judged on now for the next you know。

11 months who knows so anyway that's that's when。That's way too much， but anyway。😊，Other questions？

Hi I'm Yuhann and I had a question about sort of the bridge between industry and academia for graphics so when you were first entering NviIDdia it was kind of the beginning of the whole realtime rendering movement in the company and right now there's so many new technologies especially in graphics from like Nfs to all sorts of things so my question is how would you evaluate the potential of computer graphics research to be applied to some sort of area like I know you spoke a little bit about using ray tracing for self-driving or kind of what's your thought process behind how research could be used。

😊，Let's see behind how research can you stay like say say the question again the short yeah oh I don't know。

 I don't know if I can， I guess it's just how would you evaluate the applicability of a new graphics research area？

😊，Well， I don't， yeah， I mean， luckily I'm not in that position to like pick and choose。So， yeah。

 I don't know。 But yeah， between research and development， it， yeah， it's interesting， I mean。

 because it is。Like I said， for me， it's kind of a continuum。Yeah。

 I don't know it's a funny thing because there's also sort of there's sort of chicken and any kinds of things where it's like。

 oh this is a really cool technology， but we really need you know this other hardware to exist。

 but but that other hardware needs our feature to really speed it up so that hardware doesn't exist or things like that where just looking at it's not really a great case but like augmented reality we now have these I think what is know theyve just come up with a really ugly new new thick augmented reality classes but I hope they work I but it's one of those tricky things where like well how much time do you put into researching augmented reality if there are devices that can you be used to that have that kind of form factor that actually is going be usable that someone's actually going want to buy or is it just like well this is research and you can can some things you can figure out that it' will probably apply to all augmented reality devices so great or to a large。

So it's kind of a funny business。Yeah， I don't know， I mean， if I had the next billion dollar idea。

 I'd be probably doing it right。But I don't。Thank you。😊，s太咯。

Eric I heard a few and you touched on a few of those already。

 so I've removed them first first question Praex recently announced that they're adopting Sp We。

Um and your thoughts on that as somebody who's done a lot of work using teleex over the years。

Greatai say it again， I'm sorry I missed the two words in there and so it's a total mystery that you're asking about Microsoft and direct X announced that they're going to switch to Spy as a shading level your thoughts on that。

My thoughts on that are yeah， I actually saw that and it was like。

I sort of skimmed the announcement and went sounds good but I honestly I won't claim many expertise at all in that area that's one where you know the term comes by and I go。

 okay， what was it again okay and there's this some of the thing called slang and you know so there's a lot of that mechanical stuff underneath the hood and you know in language and whatever description and so on I frankly don't know much about it you know I sort of like you say I think I skimned that article and went oh good someone's thinking about that。

😊，You know， sounds better。 Okay， but I， it's just not an area I work in at all。

Anybody might I would trust？Hi， this is Matt again， this one should be probably a quick question。

There's just， you know， the field changes so rapidly。

 how would you recommend staying up to date with trends？Oh yeah， that's a good one。Yeah， I mean。

 you know， there's yeah， I don't know let's say， I'm trying to think if there's any particular。

I don't know if there's any particular publications and particularly I mean like blogs and so on。

 I sort of recommend a lot of blogs， but only follow a very few of them， but things like yeah。

 like the NviIDdia blog and the Microsoft blog， we have I think they have a DXR blog and stuff like that on our realtime rendering page。

 we actually have a little you know oldfashed thing called portal。

 which then has a list of various blog on that page， is a list of blogs。And that might be worth。

 you know， one way to do it is to just follow a few blogs that we sort of you know。

 get like a taste of what's going out there and there's other people's blogs that I'll follow and they'll occasionally post something interesting。

Anyway， that that to me is the sort of useful one there's。Yeah， I don't know， I mean you know。

 you can certainly look at SGgra but SigGgras now up to you know what 260 publications that you know。

werere technical talks in the last SG which is way too many to keep track of so it that's a little bit hard I mean I guess you could look at you know within SigGph you might look at courses or you could look at you know what paper did get named you know paper of the you know best paper in this category kind of thing that that at least as a way to filter and try to see what other researchers are thinking about is as an exciting direction。

Anyway， those are sort of the things that come to mind。嗯， it。

One blog I can recommend is the Graics Week， I just looked it up it's by Gendrick Iner。

 I think such Graics weekly blog， it'll probably be one of the top links。

 it really covers a wide gamut of the graphics industry and he does a fantastic job of curating that every week。

Yeah， yeah he sort yeah if you had' you know， there was only one blog you were going to follow that's a good one because he just sort of notes the other blogs and other announcements and so on and kind of consolidate consolidates them into you know。

 here's a list of things to look at。It's a little undifferentiated in a way I mean he'll you know whatever he finds he puts up there。

 but but nonetheless it's it's you know， he catches a lot of stuff so that that is a good one。

Other questions？OkayEric I'll go with one more of mine web GPU has become a recent favorite of mine。

 especially as somebody who doesn't do graphics on a day to day basis I'm more coer than graphics right so web GPU I found has a really nice blend of that I'm curious what you think of web GPU if you've tried it or glance at it and then potential for webbased realtime ray tracing in the future。

Yeah， right， well yeah， I'm assuming love GPU well。

 any amount of money that you know there's rayrayss I haven't really looked at love GPU。

 but it seems like something that you could。know but I don't know if it connects to the GPU hardware at this point for the like the ray tracing acceleration but I love like I mean I taught an online course a decade ago or so which is all just based on webGL and I love that I actually in fact I started with WebGL and I realized it takes like 100 lines to get a you know a triangle on the screen webGL so I went run for something else and I found 3 JS and。

Which is still around it continues to evolve and that's like for just quick graphical things where I just want to I want to get some interaction going and I want to you know just throw some polygons on the screen and I want to have some interactivity I want to be able to click on things and so on。

That for me is just a totally wonderful thing it's like you know there's no compile there's no deployment it's the deployment is uploading your your webpage you know it's there's no there's no you know no downloads no install no anything you know it's just webGO is there and and I see that you know I love seeing things like webG GPU where it's like okay this is just becoming a thing you know this sort of no no no install no deployment kind of thing it's just it's just great and it's also yeah it's just having those kind of tools。

That's wonderful That's all I can say， I mean I've used it internally for research projects where they' like hey。

 you know we're trying this algorithm we're doing this kind of thing and you know we want to see it response bla。

 blah，h and it's like give me a day you know because you can whip up a thing and say okay now we're casting ways like this look how it responds here you can do very quick kind of visualization things once once you get the basics down of just getting stuff on the screen and being able to just say just go to this website you can now see it you know' it's very easy to share results so I like that kind of tool a lot。

😊，Thanks any other questions？I have a last question， your favorite recent paper or project。

 especially an open source project。roof。Yeah， I haven't been looking into many open source projects lately or people I know you've gone to a couple small office conferences right right。

 yeah papers。Well actually I'm going to totally dodge that question and talk about the economy kidding now I'm going to dodge it and actually I will point to one other research which I really liked actually this guy Ace Roola who has like a ton of subscribers so you know on YouTube。

 this guy ACE ROL。😊，you know research I like it's okay it's interesting to see but you know I'm more of a practical guy so what I'm liking is that this guy's done lots some videos he's a young guys just sort of new in the industry in a way and but they're just you know the view that I watched through it like oh yeah that's good you he pretty much nailed it so anyway that's one more research I wanted to make sure to point out is aE ACE ROLA yeah research I mean really like I say the you know this year I like I say you know went I 3D that was fun there was some cool ideas there EGSR again fun cool ideas there nothing lucked out and made me go oh yeah I want to go and implement that right away you know the SG sort of 2023 Gaussian 3D Spts that's one where it's like oh I don't want to implement that right away but I want to use that right away because it was so like you they hit it just right。

T ideas from a bunch of you know that had been around for decades and glue them in such a way that you know it actually worked together well so for that for me is like piece that I really enjoy as far as research。

嗯。AllThank you， Eric， last call for any questions。All right Eric thank you so much once again for sharing your time with us it's been wonderful as always I'm sure the students appreciate your time equally as well and we hope to see you for final projects one thing say if you guys want to run real time project ideas by Eric his email is available you can ask me or look up look it up on his website just go me。

😊，Yeah， Eric Eric's a fantastic mentor for final projects and like he was saying previous research projects have used E as a resource and you guys who are interested in those kind of final projects can also reach out to Eric。

So thanks Eric once again thank you for all of your pain yeah and thank you for all of your time honestly thanks so much。

See yeah。Oh。Yeah。Let me stop this if you guys want to hang out for a minute。

