# CMU《计算机图形学｜CMU 15-462  COMPUTER GRAPHICS 2021》中英字幕 p02 -02-Lecture 01_ Course Overview -BV1H3NBemE5E_p2-

Alright welcomel to our first lecture on computer graphics today we're just gonna to do an overview of computer graphics we have two main objectives one is to try to understand broadly what computer graphics is all about where does it show up in the world and we're actually also gonna really get our hands on a first algorithm for making images from 3D shapes Also I should say all information about course logistics is on the web page today I'm really going dive into the content Okay so what is computer graphics why are we here。

 what do we want to talk about this semester when you think about computer graphics probably an image like this one comes to mind something from maybe an animated movie visual effects but。



![](img/85b2849b95af748d1fc31602d6cfd639_1.png)

What we really want to study in this class more fundamentally is how computer graphics shows up broadly in computer science。

 what its function is in digital computation and why we need it so if we think back to the earliest computers。

 they look something like this， these huge machines that took up an entire room and the way that you could interface with these machines was very crude。

 you might have to punch holes in a card that gets fed into the computer。

 it does some calculation and then it spits out some card also with holes punched in it and this takes a lot of time obviously to set up the program。

 but also to interpret the results to understand what is it that came out of the computer and so you think okay well there must be at a better way to get digital information in a form that we can understand in a form that we can digest。

 so if you start looking at the history of computation。



![](img/85b2849b95af748d1fc31602d6cfd639_3.png)

![](img/85b2849b95af748d1fc31602d6cfd639_4.png)

![](img/85b2849b95af748d1fc31602d6cfd639_5.png)

You'll see that over time， very naturally people gravitated toward having some kind of visual display to convey what information was being stored or was computed by a machine and eventually we got to the point where people really started thinking about this problem of display and interaction as a study or topic all on its own。

 so this is one of the earliest examples of somebody who really was starting to think about。

Computer graphics， human computer interaction， so this is a demo of something called the sketchkech pad which was developed by Ivan Sutherland I'll play a short little clip here。

 communicate with the machine how do you actually go about communicating with a computer in a graphical sense Well we are using asoscope here。

 which is much like the TV set except it's being driven by the computer。



![](img/85b2849b95af748d1fc31602d6cfd639_7.png)

![](img/85b2849b95af748d1fc31602d6cfd639_8.png)

In order to get the information into the computer， we have to draw somehow in this display。

 and we use the light pen。RightSo people had really started thinking about how to get information into and especially out of the computer and so if we fast forward to 2020 right we had all this development of display technology getting higher and higher resolution。

 getting richer color to the point where we're no longer just getting a little punch card with holes with a tiny bit of information coming out of the machine but now a single image on a monitor an 8k monitor might convey about 95 megabytes of information right so we can really pump out a lot of information from the machine and if we start looking at even newer devices that are coming down the pipe like virtual reality headsets。

 augmented realityities headsets， these are the devices where we have to supply。



![](img/85b2849b95af748d1fc31602d6cfd639_10.png)

![](img/85b2849b95af748d1fc31602d6cfd639_11.png)

A phenomenal amount of information in order to drive them。

 so a headset that you might purchase today has two displays。

 one for each eye that are each 2160 by 2160 pixels。

 they have some number of bits to convey color and they have to display an image to get some kind of realistic reproduction of something visual。

 they have to display an image 90 times a second， so if you do a little computation that's saying we're pumping out about 2。

3 gigabytes per second of information from the computer。

A lot more than we were at the dawn of computing。

![](img/85b2849b95af748d1fc31602d6cfd639_13.png)

So one natural question to ask here is why is visual information so important there are a lot of other ways that we could have tried to get information out of the machine。

 we could have played sound or had some kind of vibration why are we so focused on visual information in computer science and computer graphics。

 well one big reason is that's just the way your brain works about 30% of your brain is dedicated to visual processing。

 and so if you think about it from a kind of system system level point of view。

 your eyes are kind of the highest bandwidth port into the head。

 so if you're trying to get information from a machine into your mind that's doing something visual makes a whole lot of sense？

Okay， and so this kind of explains perhaps why computer graphics was developed。

 why it was such an important part of computer science。

 and we can start to put together at least a tentative definition of computer graphics。

 what is computer graphics well we might say that computer graphics is the use of computers to synthesize visual information we have digital information just ones and zeros。

 and we want to perform some kind of computation to turn it into something that human beings can consume some kind of visual information。



![](img/85b2849b95af748d1fc31602d6cfd639_15.png)

Now， if we frame it that way， if we say the point is to create information for human beings to consume。

Then it's also natural to ask， well， why only， again， why only concentrate on visual information？

Sure， the brain has a lot of visual computing power。There are other things that we could do。

 and in fact， graphics has evolved a lot since its early days to focus on a much broader set of problems and questions than just the question of how to turn pixels on and off on a high resolution display。

So there have been people who've worked on simulating sound。

 generating sound from fictional or virtual 3D models。

 There are people who've worked on synthesizing or simulating touch so that you could feel the way an object might feel if it existed in physical reality。



![](img/85b2849b95af748d1fc31602d6cfd639_17.png)

And so we can broaden the definition of computer graphics and say really we're interested in using computers to synthesize and manipulate sensory information。

you could go on and maybe think about taste and smell in other senses might be fun。

 but the key word here is synthesis。Computer graphics is kind of the unique discipline in computer science that takes information and synthesizes perceptual stimuli。

There are other disciplines， let's say computer vision that look at the inverse problem I have。

Stimuli in the real world， and I want to consume them。

 I want to interpret them and convert them into digital information。So in that sense。

 you might think of computer graphics and computer vision as being kind of inverses of each other and the interplay of those two disciplines actually is very important。



![](img/85b2849b95af748d1fc31602d6cfd639_19.png)

Something that is very contemporary， going beyond turning pixels on the screen is turning digital information into another thing we can experience。

 which is physical matter。So there's a lot of work in computer graphics， for instance。

 on 3D printing， I have a digital model and I want to print it out here I'm printing this bunny rabbit slice by slice until I have a solid physical model I can hold in my hands。

But it goes much further than just 3D printing， people are looking at all sorts of different ways that you can turn digital models into physical models。

 whether that's turning digital objects into food or into clothing or into buildings。

 the bottom right example here is a duck who was born without one of their feet and so somebody went and scanned the other foot reflected it on the computer printed it out to create a prosthesis right so there's a lot of interesting things you can do with the technology from computer graphics that goes beyond image generation。

 and is really starting to have a major impact on the broader world。

So this is going to be our working definition for this class。

 how to use computation to turn digital information into sensory stimuli。

 although I'd say if you talk to somebody who does a lot of computer graphics。

 they would still say you know that definition is still a bit too narrow I don't think it really captures all the interesting things that go on in computer graphics and so if you want a really good picture of what's happening in computer graphics。

 a great place to look is at the ACM Sgraph conference where all of the new results in computer graphics are presented every year。

 lots of exciting new research papers and they produce a nice technical papers trailer that just highlights some of the cool stuff that's going on in graphics so' let's take a look at that。



![](img/85b2849b95af748d1fc31602d6cfd639_21.png)

Welcome to the SigGph 2020 Technical Papers trailer well present clips from just a few of the exciting breakthroughs in the Techical Pa program。



![](img/85b2849b95af748d1fc31602d6cfd639_23.png)

A learning based approach to keyframe video stylization enables this artist to craft a personal look in real time。

By using four fishey monochrome cameras， we can track someone's hands in space。

 enabling them to sort these blocks and win the game。Using clever hinge design。

 a flat lattice of thin， flexible strips can be deformed into a complex 3D structure and then flattened back out again。

To create a realistic knit bunny， this algorithm uses an energy density function to drive a thin shell simulator。

 it can also knit armidills。By interpolating a sparse series of 3D poses。

 this algorithm produces smooth， complex motion that still allows for artistic control。

This algorithm supports immersed bubbles and free surface flow simulators。

 producing the familiar glgging action of a water cooler。

A method for managing the dynamics of nonlinear deformable objects lets us bounce this hairy elastic toy against a wall。



![](img/85b2849b95af748d1fc31602d6cfd639_25.png)

Nural networks can improve photographs of people's faces by removing external shadows and simulating a soft fill light。



![](img/85b2849b95af748d1fc31602d6cfd639_27.png)

Efficiently coupling the interaction between solid objects and turbulent flows lets us unleash a tornado on toy animals。



![](img/85b2849b95af748d1fc31602d6cfd639_29.png)

Genrative adversarial networks and deep reinforcement learning help this quadruped navigate a maze to find delicious stars。



![](img/85b2849b95af748d1fc31602d6cfd639_31.png)

By animating the dynamic fracturing of isotropic and orthoropic materials。

 we can pull off the top layer of a piece of porkrk belly。

An algorithm that exploits tunnels in configuration space can solve complex puzzles made up of entangled rigid shapes。

A method to implicitly model the space of plausible faces lets us discover new faces by sketching or by merging existing parts。



![](img/85b2849b95af748d1fc31602d6cfd639_33.png)

![](img/85b2849b95af748d1fc31602d6cfd639_34.png)

By planning the motion of its two robot arms holding a deformable hot wire。

 this device can cut complex 3D shapes like a bunny。



![](img/85b2849b95af748d1fc31602d6cfd639_36.png)

![](img/85b2849b95af748d1fc31602d6cfd639_37.png)

This system measures the forces we feel in real and simulated worlds and then applies those forces with a fingertip device so we can feel what we see。



![](img/85b2849b95af748d1fc31602d6cfd639_39.png)

This block of soil was simulated by a massively parallel material point method for physical materials。

 it can also collide our medolos。

![](img/85b2849b95af748d1fc31602d6cfd639_41.png)

By processing photographs on a mobile device， this algorithm lets us view our scenes from novel viewpoints。

This technique models large numbers of colliding elastic bodies with friction。

 so running characters can enjoy rich lustrous hair。

A particle based approach to fluid simulation lets us apply neural textures to fluids even while they're moving。



![](img/85b2849b95af748d1fc31602d6cfd639_43.png)

A material method for two way coupling of nonlinear solids and fluids lets us drop balls full of water and orange juice。



![](img/85b2849b95af748d1fc31602d6cfd639_45.png)

Okay， so hopefully from that you get the sense that computer graphics is really a rich and diverse discipline that goes far beyond just turning pixels on and off on the screen and that touches all sorts of different areas of life。

 computer graphics really is everywhere。

![](img/85b2849b95af748d1fc31602d6cfd639_47.png)

So a lot of us， again， first think of computer graphics as something that shows up in entertainment in movies and games and that certainly is a very important use of computer graphics。

 but even within entertainment， it shows up in places you might not even be thinking about。

 so not just kind of cartoon animation， but lots of movies you go to see these days might have effects in them that are so good you don't realize they're there。

 maybe removing wrinkles from the skin or inserting somebody into old photograph who wasn't really there。



![](img/85b2849b95af748d1fc31602d6cfd639_49.png)

![](img/85b2849b95af748d1fc31602d6cfd639_50.png)

Kind of scary Comp graphics who of course is used a lot these days in art and design。

 people in addition to traditional media are almost always doing some kind of digital media painting or modeling or something in similarly industrial design you want to make products that are not only beautiful but have some particular function so you're balancing aesthetic aspects with functional or engineering aspects that's very core to the kinds of questions people look at in computer graphics how do you balance the physical and mechanical constraints with aesthetic considerations Also in trying to do engineering you might just need to visualize data that's a very important thing you do a car crash simulation you need to understand what happens there's so much data that goes on in these simulations it can be hard to really understand what happened and visualization techniques are very important for that Arch is being revolutionized by techniques from computer graphics in particular。



![](img/85b2849b95af748d1fc31602d6cfd639_52.png)

![](img/85b2849b95af748d1fc31602d6cfd639_53.png)

An area called discrete differential geometry has a lot to say about structures that can be easily built。

 but still can be designed in a very free form way in scientific and mathematical visualization again。

 you have tons and tons of data that might come out of some high resolution simulation okay。

 it's great that the computer can do all that it's great that we can build systems that can。



![](img/85b2849b95af748d1fc31602d6cfd639_55.png)

Solve problems at that scale， but once you've solved those problems。

 how does a human being interpret the answer， there's just so much information to make sense of。

 likewise in medical or anatomical visualization， we have devices that can take very。

 very detailed scans of the body。

![](img/85b2849b95af748d1fc31602d6cfd639_57.png)

How do you come up with techniques and algorithms that lets you efficiently look at all that data and understand what's going on？

Computer graphics plays a huge role in navigation in the way that you get around the world。

 anything from just simple 2D maps to more sophisticated to 3D maps to autonomous vehicles doing autonomous driving or interesting things like taking collections of photographs that are taken by different tourists and assembling them in some way that lets people get a sense of what that location looks like lots of interesting things you can do there。

 and just broadly in communication there are things that you don't think about as computer graphics。

 but requires some pretty amazing technology， so actually every single letter that you see drawn on your screen when you're reading the newspaper when you're reading a website。

 there's some pretty sophisticated algorithms that are needed to draw all that typography and draw it very very quickly and it kind of works like magic you don't even realize that there's some sophisticated algorithm running because people have done such a good job at developing this technology but it is sitting there in the background likewise。



![](img/85b2849b95af748d1fc31602d6cfd639_59.png)

People are exploring all sorts of new mechanisms for communication。

 for telecommunication beyond the written word， so like virtual avatars that you might sit in front of your camera and turn you into 3D model。

 I mean the possibilities are endless。

![](img/85b2849b95af748d1fc31602d6cfd639_61.png)

So there's so much to do， what are we going to do in this class when we're really going to look at the foundations behind all of this。

 the computational foundations behind all these different applications。

 right because all these applications，Whatever domain you're excited about。

 demand sophisticated theory and a sophisticated treatment of computer systems。

 So in the theory category we're going to talk about things like basic representations。

 how do you digitally encode shape or motion。A big theme in this class is going to be sampling and aliasing。

 so how do you navigate acquiring a signal and reproducing a signal so that the thing you reproduced faithfully represents the thing you acquired？

We're going to talk a lot about numerical methods， so how do you manipulate signals numerically。

 how do you solve equations numerically in a lot of computer science education there's a focus on discrete combinatorial problems working with integers and so forth。

 this is really going to be a deep dive， your first real handson experience perhaps in working a lot with floating point representations of numbers which can be a little tricky。

We're going to talk about radioometry and light transport。

 so how do we in a very precise way talk about how light looks， what color it is， how bright it is。

 how it's distributed in a scene， right these questions are all very important for trying to create photorealistic images。

And we're also going to connect this a little bit at least to perception right remember again。

 the goal is to take digital information and convert it into stimuli that a human being can consume well if that's the case。

Then understanding how human beings perceive visual information and other stimuli is really going to factor into our algorithms in an important way。

 for instance， if we say we want to compress an image so that a person doesn't notice anything changed。

 we really have to understand something about human psychology。On the system side。

 you know if we want to create algorithms that pump out gigabytes of data into a VR headset。

 well then we really need to think about performance and the way that information is exchanged by different processes and algorithms in our pipeline so we're going to talk about things like parallel or heterogeneous processing that might be needed to run fast graphics algorithms we're going to talk a little bit about graphic specific programming languages like shader languages and more generally we're going to talk about how we can formulate problems in computer graphics in terms of a pipeline。

 what are the right primitives to break down our problems into so that we can efficiently stream computation through a piece of hardware。

Okay。So。That's it for the high level overview， let's really dig in and get our hands on some concrete problem。

And so what we're going to do for most of the rest of this lecture is we're going to try to think about how we can model a three dimensional object。

 encode it as digital information。And then turn that digital encoding of the object into a picture。

 into a two dimensional picture that we can look at okay and in particular。

We're going to think about a very simple piece of geometry， just a cube。

 okay so we want to generate a somewhat realistic drawing of a cube and we want to do that algorithmically。

 not just by sketching it on paper。So we have these two key questions we'll have to answer。

 one is a modeling question。How do we describe or encode the cube on the computer？

And then we have a question of rendering that word rendering will come up a lot in this class。

 when we say rendering， we mean something about how do you take a。

Digital description and convert it into a concrete picture。

 so how do we visualize the model of our cube？Okay。So just to get us going。

 this is obviously a simple example， but just to get something concrete。

 let's say that we have a cube that's centered at the origin 0，0，0 in three dimensional space。

It is a2 by2 by2 cube，2 wide by2 tall by2 deep， and the edges of the cube are going to be parallel to the X。

 Y and z axes。 It's kind of an axis aligned cube。So the first question we could ask。

 how do we encode this？In some sense， we've already encoded the cube。

 we've given a description of the cube that's pretty precise。 We know where it sits in space。

 we know how big it is， we know how it's oriented。Okay。

But this description doesn't generalize very well if we want to start describing other objects。

Like a face or a car。 It's not really enough to just give the position。

The rough size and the orientation。Somehow we're going to need to encode more detailed information about the shape in order to eventually make a picture of it to render it。

So maybe think for just a moment， what's a more explicit description I can give of the cube。

It really spells out in great detail what its geometry looks like。

What kind of information might I encode。Okay， well， it's a little bit of a tough question。

 it's kind of an abstract question。But let's try this。

 so one thing we could do that's pretty concrete。Is we could say， first of all。

 what are all the corners what are all the coordinates of the corners of the cube or the vertices of the cube？

 so given this。Description of the cube， we should be able to figure out where in space its eight corners live。

Okay。And what might be an example， maybe think about what's the coordinate for just one of the corners。

 Can you think of anyone。Okay so if you think about this for a second， you think， okay。

 it's  two by two by two， but it's centered at the origin， so it's kind of kind of a radius of one。

And so at least one of the corners will be at 111， another one might be at minus1， minus1 minus1。

 and then we have all the other possible combination of signs， we have three coordinates。

 two possible signs， two to the three is eight， so we get the eight vertices of the cube。

And kind of the point here is， again， if we think okay。This was easy for the cube。

 and it seems almost unnecessary for the cube。 But again， if I was trying to。

Convey the shape of a face or a car。I could also list a bunch of points。On that shape。

So the point here is that we have a description that will generalize to more interesting geometry。

Okay， but we're not quite done yet。So far， we don't really have a description that captures the essence of a cube。

 we just have these eight points。That are floating out in space。

RightAnd if I just show you these eight points， if I drew a picture now。

 if I rendered these eight points onto a two dimensional canvas。

It might be pretty hard to tell that this is a cube。I would just have these eight dots。

Somewhat strange locations。So what additional information might I provide？

To really capture the shape of the cube。Okay， well， there are a couple natural possibilities here。

One that's pretty straightforward is I could list all the edges。

I could say not only where are the eight corners in space。

 but which of those points are connected to each other by an edge of the cube？

And one simple way to specify that would be to say， okay， an edge has two endpoints。

So if I have these eight points， a through H。I'll specify an edge as just a pair of letters。

So for instance， AB is an edge， Cd is an edge， EF is an edge。And so forth。

 you can pause the video if you like and check me on this。 What do you want to check？

How do you know if I got it right with one of these edges？Well， I guess what you you should。

Check to see is that only one of the coordinates changes when I go from one endpoint to another。

The edges are aligned with the X， Y， and z axes， meaning as it go from one edge endpoint to another。

 only the x coordinate is changing or only the y coordinate or only the z coordinate but I'm pretty sure that those are all the right edges for my cube。

Okay。So。We now have a digital description of the cube。It's no longer a concept。

 it's no longer just the word or the string cube， but it's a very。

 very explicit digital encoding of the cube and we could encode this if we like all the way down to binary data。

Right rather than these text strings that we see on the slide。Okay。

 but this is what we mean by a digital encoding of the geometry or the scene that we're working with。

So we're kind of done now with the modeling task。It was a little bit of a pain。

 right we probably in general don't want to describe our models this way and later on in the semester we'll see how to build tools that give us a lot more ability to easily design and model three dimensional objects。

But for now， we have a reasonable digital description of our cube。So the next question is。

 how do we draw this cube as a flat 2D image， how do we render it？Well。What do you think。I mean。

 the basic problem here is we have。Three coordinates for every vertex。

But if we want to draw it on a 2D piece of paper。We need two dimensional coordinates。

So how could we take these three coordinates and turn them into two？

That's our basic rendering problem， at least for today。What do you think。Okay。

 well there are a lot of possibilities here for one thing we could just throw away one of the coordinates。

 right， we could just say if I want to plot a three dimensional point on a two dimensional plane。

 I'll just toss out the Z coordinate， I'll just draw X and y。And that works okay。

 but we don't really get a three dimensional sense of this cube if we do that。

We would just see what would you see in that case？Let's say， I。Threw away the Z coordinate。

 I plopped these points on the plane， and then I connected any。Pair of points that belong to an edge。

Well， you just see a square。It it'd be like looking at the cube from the side。

 but without any perspective， it'd be this really boring image。

So we want to do something a little more interesting。

So our basic strategy is going to be to map the 3D points to 2D points in some way。

 in some interesting way。Okay， and then we're going to connect those 2 d points with straight lines。

Is that an algorithm， is that really something we can go and implement？Not really。

 it's not yet an algorithm because we haven't really broken it down into atomic operations that a computer knows how to do。

 but it's a good sketch of the algorithm that we want to design。Okay。

So let's talk in a little more detail about how each of those steps is going to look。

The first one is perspective projection。So we said that this really。

 really simple idea of just tossing out a coordinate。

 that's not going to give us a very interesting image。

 What we'd like to do is capture things that we know are true from our day to day experience of looking at the world。

 So one thing we know from walking around the world is that objects tend to look smaller。

As they get further away， this is the phenomenon of perspective。And， you know。

 it's such a natural thing， it's such a thing that is just obvious。

Most people never really think about， well， why does that happen？

Why is it that if I'm looking at a building downtown and I'm I'm off？Up on a high hilltop。

 why does the building look really small？Is it actually that that building shrinks？

When I walk up to the top of the hill。No， I mean， this is crazy， right。

 The building doesn't change so so why does it look so tiny？Have you ever thought about this？

So let's really think about this。And one way we can get our heads around what's happening is to consider what's called a pinhole model of a camera。

Actually， this is a real kind of camera you can build。

So the way this works is you can imagine you have a cardboard box。That's completely dark inside。

And then you poke just one tiny little hole to let light in。And on the opposite side。

 from where you poke the hole， you put a piece of film。Okay。

 so traditional film was a photo sensitiveitive material。

That had silver palide crystals in it or something like that and the way it works is every time light comes in。

 every time a photon hits that film， it causes a chemical reaction to occur。

Those little crystals get stuck to the film paper。And anywhere that light doesn't hit。

 the crystals don't get stuck。And so then you go into your photo laboratory and you wash the film in some particular chemical。

All of the。Stuff that didn't crystallize， gets washed away。

 all the stuff that got stuck remains on the photo paper。Or really this is your negative right。

 and it creates an impression of the brightness or darkness that was shining through that hole。

 that's how traditional photography worked before digital cameras came around。Okay。So。

Not super important actually all this chemistry and how the film works。

 but that's what's going on in your pinhole camera。

 what we want to understand again is this phenomenon of perspective， why is it given this setup？

That models that are or objects that are closer， look bigger and smaller。

 look further away if I move。The box away from the tree or toward the tree。

Why should the size of the tree change in my two dimensional image？

Maybe this is a little easier to understand if we look at it from a side view。Okay。

So the pinhole now is along this horizontal axis， it's on the right side of the box。

 along the horizontal axis。And we can ask for any point p equals X，Yz in three dimensional space。

 so maybe the tip of some leaf on the tree。Where is that going to end up on the image if there's green light kind of shooting off of that leaf。

 you can imagine there's some light that bounces off and shoots off of that leaf into the camera。

What is the position it's going to end up at on the film， the position Q equals U V。

So we're going to say the point P is where it starts， Q is where it ends up。

 but where exactly does it end up， how could you do this calculation？Well。

 maybe easier to think just for a moment。About just where it ends up。Vertically。

So if V is the vertical coordinate on the two dimensional film。

How could you figure out the V coordinate of this point Q based on this little diagram？Okay， well。

 some of you may have thought， ah， actually， this is something about similar triangles。

I can notice that there are sort of two similar triangles。In this picture。

There's the one on the right with base Z and height y。

And there's the one on the left with base 1 and height V。Okay。So。

What do we know about similar triangles，  similar means， for instance。

 that the ratios of edge lengths are the same。Right， so we know。

That y over z is the same as v over 1。Right so if we assume。That the camera has unit size。

It's a one by one by one box。And its pinhole is at the origin of space 00，0。

Then we just need to solve the equation， v over1 equals y over z。For the coordinate V， well。

 that's a pretty easy equation to solve。Right， we divide v by1， and we get v。

 and that's equal to y over z。In other words， the vertical coordinate on the film is just the slope y over Z。

Okay。How do we get the other coordinate， how do we find the U coordinate where the light hits the film？

Well， that's easy， we just do exactly the same， but we look at the box from the top this time rather than from the side。

Again， we'll get the same kind of picture with two similar triangles。

 we carry out the same calculation and we'll discover that the horizontal coordinate is x over z。

Okay， hopefully that makes sense， if not， pause， rewind， take another look。

But the important thing is。The result we got agrees with our day to day intuition。What do we notice？

That if we have this point on the tree， X， Y， z， and z starts getting bigger and bigger and bigger and bigger。

 what happens to x and Y I'm sorry， what happens to U and V？

U and V start getting smaller as Z gets bigger as the tree goes off into the distance。

The coordinates on the image plane shrink， the apparent size of the image shrinks。As z gets smaller。

 x over z gets bigger and y over z gets bigger， and the image gets bigger。Okay。

 so this actually gives some real concrete explanation for why it is that things look bigger when they're closer and smaller when they're far away。

 The same kind of thing is happening in your eyeball。 Your eyeball is not quite the same as。

A pinhole camera， but it's not so different either you have a pupil， which is like the pinhole。And。

You have a retina on the back of your eyeball， which is kind of like the film in your camera。

And exactly the same kind of calculation explains why things get smaller in the distance。Okay。

The good news too， is that this is an easy calculation， if I want to go from 3D to 2D now。

 all I have to do is divide by Z。So now we can really go ahead and draw our three dimensional cube as a two dimensional image。

And we can do this by a completely algorithmic procedure。

 something that doesn't require that we're good artists。

 we don't have to have any background in painting or sketching or anything like that。To get this。

Ilusion of perspective。We just have to repeat the same simple algorithm 12 times and I will encourage you to actually do this because it's a lot more fun to see that this works out at home to actually do the calculation。

 draw the picture and see that yes indeed the algorithm works then to just sit there and nodge your head and believe that it all happens the way that it should so what you're going to do is repeat the same very simple algorithm 12 times once for each edge of the cube。

 this is a little monotonous so if you want to write a little piece of code。

 you know by all means to carry out this calculations for you or you can do it with a calculator doesn't matter。

So for each edge。We're going to imagine that we have a camera sitting at 2，3，5。 Okay。

 so some interesting location in space， not 0，0，0， just because we want a better view of our cube。

And we're going to convert the three dimensional coordinates X， Y。

 Z of each endpoint to two dimensional coordinates UV in the following way。

The first thing we're going to do。Is we're going to subtract the camera location C。

From the vertex location， XYz， so we have our vertices listed at the bottom。

 those are our capital XYZ。So we're going to do， for instance， 11，1 minus2，3，5。

And that gives us the 3D locations of those points。Relative to the camera。

You see how that works if our camera was sitting at the origin 000。

Then the vertices we've listed are already the coordinates we care about。

But if we move the center of the camera a little bit， we also have to change。

The coordinates of the vertices were working in a。Different coordinate system now centered around the camera。

Okay。So subtract C from capital XYz to get lowercase X，Yz。Then how do we go from 3 d to 2D divide。

Little X and Y coordinates by the little Z coordinate to get U and V。

And if you want to plot this on a piece of graph paper。

 you'll make your life a little easier by just writing it out as a fraction。

Okay once you have those coordinates。Just draw a line， let's say on a piece of graph paper。

Between the two coordinates you computed。That's the little subrtine that'll draw a single edge of the cube。

Your overall rendering algorithm then is to just do a loop over all the edges。

And execute this subroutine 12 times。Okay。And so then you could go ahead and。

Draw this on graph paper。In fact， if you don't have graph paper， but you do have a printer。

 you could pause the video and you could print out this moment of the video on your printer。

Lots of ways you could do it， or you could draw a drawing program on your computer。

But give it a shot。Okay。And if you go ahead and do this， maybe you make a mistake or two。

 but that's okay， probably you're going to get an image that looks something like。This。Okay。

 so that is the output of our first graphics algorithm。

It turns a digital description of a cube into a real two dimensional image。

And you can check here if you got the same。2D coordinates。

 But what's really cool about this is it looks pretty good， right。

 This really does look like a three dimensional rendering of cube。😊，And。

We did it completely by a algorithmic deterministic procedure。

We let you know math do all the hard work for us， eventually we'll let code and computation do all the hard work for us。

 so if we now wanted to make an animation of this cube。

 if we wanted to imagine the camera is moving around the world。

 we would get this beautiful perspective， correct image of the cube from different points of view。

It's pretty cool。Here's just a fun picture produced by a previous class where everybody contributed a different edge。

 so 12 different students sat and computed 12 different edges。And hey， they got it right。Okay。

 so again， the point here is you don't need higher level reasoning。To come up with these。

 these images， it's really about breaking down the rendering process into。

Lower and lower level subroutines and components。They can be used to execute this kind of drawing algorithmically。

 Okay， so success， we turned purely digital information into purely visual information using a completely algorithmic procedure。

That's what we want to do in this class in general。But actually it's a little bit of a lie right。

 there was one part of our process that was not really very digital， it was pretty analog。

 let's say because。We didn't really talk about how you would draw lines on a computer。

We relied on maybe drawing lines with a pencil on paper。Okay。

To even start thinking about this question， how do we draw lines on a computer。

 we have to start talking about how an image is represented on a computer。And in fact。

 you can start getting an answer to this question if you just come， come closer to the screen。

Come really， really， really close to the screen。 Okay。

 so if you came really close to your computer monitor and especially if you have a low resolution monitor。

You're going to see that the display is actually not a continuous image。

Like you might see in the real world， but it's actually this grid。

Of little picture elements which are called pixels， pixels really means picture elements。

And they look something like this。So they look like these little blocks of lights that have been turned on or turned off or turned on to varying degrees。

That generate the image。And actually， you notice even some interesting and weird stuff about these pixels。

 which is。They look like they're striped in three colors。 They have red， green and blue stripes。

 like a little flag。All right， so they're not just a continuous color。

And we'll talk a little bit later in the class about color and how it is that little red。

 green and blue lights manage to produce all sorts of different colors。

But it's worth knowing that this is kind of what's going on when you look at a screen。

 whether it's your laptop or your cell phone or whatever it is。

So even though displays are pretty complicated， we can come up with a pretty simple abstraction for displays or for digital images that's good enough for working with algorithms。

Okay，And this abstraction is to say that we have a raster display。

 meaning things get drawn or rasterized onto a grid with some number of rows and columns。

The image is essentially comprised of the values that are stored in this grid。

 the numerical values that are stored in this grid。

And each little cell of the grid represents some color， some color value。Okay， again。

 we'll talk a little bit later on about how exactly to encode colors right。

 if I said please give me the。Digital value， the numbers encoding the color orange or green。

 you may not know exactly how to do that， but later on we'll see there's a very straightforward mapping between these colors or maybe sometimes not so straightforward mapping between these numbers and color values。

Okay but this is what you should think when you think of a digital image。

 you think of a grid with some numbers in it， maybe the easier version is to think not about colors。

 but just a gray scale or black and white image where you have a one if the pixel is white and a0 if the pixel is black or 0。

5， if the pixel is a medium gray。Okay， so that's how we think about a digital image。

 The next question is。If we want to draw a line into a digital image。

 which of these pixels should we turn off or on？If you hand me only the two endpoints。Of the edge。

 you say that the U V coordinate of one endpoint and the U V coordinate of another endpoint。

Which pixels in the grid need to get turned on？That process of turning the high level description of the line segment into a set of pixels is called rasterization。

Rassterization is a process of converting a continuous object to a discrete representation on a raster grid or pixel grid。

Okay。So how might you answer this question？The question at the top of the slide。

What pixels should we turn on to depict this line？What do you think。Well。

 there' are a lot of different answers。 In fact， there's no right or wrong answer here。

 but one reasonable answer might be。How about just turning on any pixel？That touches the line。

 so if the line passes through that pixel at all。That's going to be part of the image for the line。

Okay。That works okay。 You might， you might notice that in this example。

 the line looks maybe a little chunky。There's some pixels that are barely touched by the line。

 but still the whole pixel gets turned on。So is that going to look funny？There's another rule。

 a rule that's actually used by a lot of real modern graphics。

 APIs and hardware and so forth called the Diamond rule。Which says you should turn on a pixel。

 not if the line passes through the square box around the pixel。

 but if it passes through the diamond，Made by connecting the midpoints of the pixel。

 this is called the so called diamondd rule。Okay， so you notice compared to the previous rule or simpler rule。

 this line is a little thinner。Pixels that are just grazed by the line don't get turned on and maybe looks a little nicer。

UYou could also ask， you know， is there really not a right answer。

 is there really not a best way to rasterize a line？Wen。One way to answer this question is to say。

 well， what properties would you like that algorithm to have。

 what should be true about a line rasterization algorithm？For instance， you might say， oh。

 if the two endpoints are in the same location， only one pixel should get turned on or maybe no pixel should get turned on。

 you could come up with criteria for what it means to have a good line raization algorithm first and then try to figure out if there is a good rule or a good algorithm for drawing lines that satisfy all those criteria。

Another perspective that we're going to talk about a lot when it comes to rasterization is to think about coverage。

So。You could say， how about we turn on？A pixel with intensity proportional to what fraction of the pixel is covered。

By the object we're drawing。Now， this is a weird question for a line because a line is。

 it's like infinitely thin。It covers0% of any pixel。So maybe you say， well， okay。

 but I'm going to give my line a width。I can think of my line not as an infinitely thin line。

 but actually a little skinny， skinny rectangle that has some width。Ah so now I could start asking。

 well， what fraction of each pixel is covered by this skinny rectangle？

And lighting up the pixel by that amount， that starts to sound pretty reasonable。

 And it also sounds nice because I can deal with things like thick lines and so forth。 Okay。

 but I'm really getting ahead of myself。 I just want to。Stress that in computer graphics。

There's often many， many ways to do things， you shouldn't just believe that there's one right way。

 lots of different possibilities to explore。So let's go back to this simple view of a line as this thing that has two endpoints and is somehow no thickness。

Okay。And let's say we care about something like this diamond rule。So if we do that。

 how algorithmically now could we find the pixels that satisfy。A given raurization rule。

 let's say we've already decided what we think is the right way。

 how do we actually turn on the right pixels？So one stupidly simple algorithm would be we just check every single pixel in the image to see if it meets。

Hour。Reesttsterization rule Okay， so for instance， let's say I have an 8 k monitor。

knowMillions and millions of pixels in my huge high resolution monitor。

And I just want to draw one little line segment， one short line segment。Let's say my image， in fact。

 is n by n for some very large n。And I'm going to raize it by going to every single cell in my pixel grid。

 every single pixel in my pixel grid， and checking。

 does the line pass through the diamond in this pixel？In terms of N。The size of the image。

How many operations do I have to do？To do this。Raststerization。Okay， I have to do。N squared。

Operations， I have to check all n times n pixels in the image。

And this is a little weird because I expect that a line or a line segment。

Is going to cover at most about n pixels。A line is a linear kind of thing。

 it can't cover the whole image if it has no width。So。

It feels like I'm doing way more work than I need to be。Doing there must be a way to do better。

There must be a way to do an amount of work proportional to the number of pixels in the output。

Rather than the number of pixels in the image。Okay。

So this leads to an idea of incremental line rasterization。So， let's say。

A line is represented again with two endpoints， U1 v1 and U2 v2， there they are。

And we're going to for simplicity， assume that these are integer coordinates and those integer coordinates correspond to the centers of pixels。

The slope of the line， hopefully you remember about slope S is rise overrun， in this case。

 it's v2 minus v1 over u2 minus u1。Okay， and we want to light up the pixels along this line segment。

 How do we do that， Well let's consider an easy special case。

Just one of many things that could happen。Let's assume that u1 is less than u2 and V1 is less than。

V2， so1 V1 is at the lower left and U2 V2 is the upper right as in this image。In this case。

 the slope is between 0 and 1， there's more change in x than there is in y。And。

So we can come up with a pretty simple little algorithm for walking along。

The line and figuring out which pixels to light up。In particular， we can start at height V1。

And then going from left to right from U1 to U2。We're just going to increment one column at a time。

In each column we're going to increase our height by the slope S。OkaySo for a unit change in U。

 V changes by S。We're going to draw。The pixel we're going to light up the pixel at U and round v。

 so round v is going to give us the integer closest to our current V value。And then， repeat。

So we move from left to right。Wei。Gradually increment V。

 and we just draw the closest integer to our current V value until we finally reach。

The end of the line segment。Pretty straightforward。

 This is not a general algorithm because in general， S is not between 0 and1。

 We have to think about these different cases。 Okay。

 what if there's more change in V than there is in U， well。

 then we need to write a little piece of code that looks very similar to this one。

 but where some U's and V's are swapped out around and so forth。 but that's the basic idea。

So there you go， we have a concrete algorithm now for actually drawing the lines。And in fact。

 this algorithm is pretty easy to implement。It's not， by the way。

 how lines are really drawn in modern graphics， software or in modern graphics， hardware。

There are a lot more clever and interesting things you do to draw lines。

 you want to handle things like lines with width as we've already talked about。But this is a really。

Nice algorithm， and nice idea of incremental Latin rationalization that actually does show up in lots of other algorithms in computer graphics。

Most importantly， we now have a complete computational procedure for turning our digital information。

 just a list of vertices and edges and maybe the camera location into a two dimensional image into a collection of。

Pixel values color values on a grid， on an image grid。Okay， so really。

 just from this one lecture alone， you really could go home。And right up pretty easily。

 a piece of code that draws three dimensional images or draws three dimensional models into a two dimensional image。

 It's pretty cool， right， And now you have the freedom。 you can change。😊，The input。

 you don't have to draw the cube， you could mess around with the vertices。

 you could mess around with the edges， you could draw all sorts of interesting， cool 3D models。Okay。

 so this whole exercise that we've just gone through is really what computer graphics is all about。

How do we encode？Visual information digitally， how do we turn that digital information into an actual image？

Or sensory stimuli。So so far， we've only talked about a very， very simple line drawing of a cube。

Okay， if we want to generate more realistic pictures。

 we're going to need a much richer model of the world。 We're going to need to talk about geometry。

 we're going to need to talk about materials。How do you distinguish leather from paint from carpet or whatever？

We need to talk about lights， different kinds of illumination， we need to talk about camera models。

 we need to talk about motion， we need to talk about all sorts of things and all the algorithms to translate that data into images。

 and we will see all of this and more as our course progresses。



![](img/85b2849b95af748d1fc31602d6cfd639_63.png)

Just to get a little taste of how things will go in this class， how will you learn all this stuff。

 Of course， part of it will be by lectures and conversations and so forth。

 we're also going to learn a lot by making and doing。 So a big part of your。

Assignments in this class is going to be building up what's called the Scotty 3D package。

 This is a software package that's kind of a toy software package that's meant to emulate real 3D packages that people use for creating visual effects and so forth。

 so we're going to give you kind of a skeleton code。For Scotty 3D。

 and you're going to fill in all the essential algorithms。

And this is broken up into four major assignments， the first one is on rasterization on the kinds of things that we've been talking about today。

 but not just drawing。

![](img/85b2849b95af748d1fc31602d6cfd639_65.png)

Black lines on a white image， really drawing much more rich and interesting graphics that you might find。

 for instance， in what's called an SVG file， a standard vector graphics file and why do you want to do this well because it lets you display all sorts of beautiful images and animations like you might see around the web like you might see on posters and again typography。

 just text itself involves a process of rasterization？

The next assignment is going to be about geometric modeling。

 so we've already seen a little bit of this today， okay we wanted to model the cubes so we input the vertices in the edges。

 we're going to talk a lot more about tools to generate and design interesting 3D shapes and then to process those shapes。

You created the mesh in one way， but a certain algorithm needs it to be broken up in a different way。

The motivation for tools like these is to create models like these models coming up not only again in entertainment。

 but also in product design and engineering and in all sorts of other things and。

Even with a simple subdivision modeler that you're going to build in Scotty 3D。

 you're actually going to be able to create some pretty sophisticated models。

 people have made some really cool 3D models with their own 3D modeler in previous years。

The third part has to do with our rendering process， we saw a again。

 really simple rendering process of drawing lines， but the third part is going to be about photorealistic rendering。

If I have a description not only of geometry， but also of lights and materials and cameras。

How can I predict what that scene would look like in real life。

 Theres lots of difficult questions about light bouncing off the wall and hitting a surface and shining this way in that way to create this beautiful reality that we live in and this kind of technology gets used all over the place again in the movies of course to make virtual environments look real。

 but also in architecture， you've designed a house and you want to see before you build it。

 hey does it look right if the light is shining in through the south window does the room look the way that I'd really like it to or if I'm doing some kind of product design or engineering。

 how can I get a sense of how this thing will look before I even build it？

That gives you a lot of freedom to design and explore without having to sink millions of dollars into actually building the thing。

And finally， we're going to want to go beyond static images and talk about motion。

 talk about animation。So just like we need digital encodings of 3D geometry。

 what kind of information do we need to encode to describe to the computer and animation？



![](img/85b2849b95af748d1fc31602d6cfd639_67.png)

And again， the motivation is lots of different things， animating characters in movies， of course。

 but not only the bodies of the characters， you also have to think about complicated things like how does the hair of a character move around and respond to its environment and this starts to get into connecting computer graphics to physics and actually taking laws of physics that you might have learned in your intro classes and breaking them down into numerical procedures that you can actually use to approximate how things move in the real world。

Animations show up also in other places like robotics。

 so here we're seeing an example of sort of animating a robot but that animation is being used to actually control a physical object。

So talking about digital encodings of motion is really。

 really important beyond just making animations for the movies。



![](img/85b2849b95af748d1fc31602d6cfd639_69.png)

Okay， so that's it for today。 Next time we're actually going to start diving in to a review and preview of the kind of mathematics that you'll need for this class。

 so the prerequisites are some background in linear algebra and vector calculus。

 but there are a few things that well need to review there are a few things that。

Show up a lot in computer graphics that might not quite have been emphasized in the courses you took previously。

 so we want to make sure you all have the right tools to guarantee your success as you go through this course。



![](img/85b2849b95af748d1fc31602d6cfd639_71.png)

All right， see you then。