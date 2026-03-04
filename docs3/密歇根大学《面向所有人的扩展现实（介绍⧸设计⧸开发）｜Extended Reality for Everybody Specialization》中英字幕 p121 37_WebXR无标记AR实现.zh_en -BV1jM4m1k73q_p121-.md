# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p121 37_WebXR无标记AR实现.zh_en -BV1jM4m1k73q_p121-

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_0.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_1.png)

Welcome to this last hands on lecture on。Mar a less AR experiences this time。 So its still Web X R。

 but and again， a frame。 But this time， a frame the AR module and actually some of the latest a frame。

 So using the latest a frame master。 So that is not actually a released yet as a new official release。

 So some of the things I show you are a little bit experimental。 the whole point is。

 we can actually do Mac a less AR on the web。 And so I'll show you what I have here。

 I previously showed you this Mac a less AR scene。 And so I'm gonna play this video。😊。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_3.png)

And you've seen this before。But it's essentially。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_5.png)

My example where I had just a single giraffe here initially with 360。prereview。

 But when you go into the IR into the AR mode down there， then it uses actually。Hit testing。

 So that is one of the more advanced features now。And then you can actually see the giraffe。

 and that's a life size giraffe。And that kind of fits nicely into the room， and。Yeah。

 so I've shown you this video before。 And here in this lecture。

 we want to essentially create something like this。 So let's look at。Marka based AR experiences。

 as says， mostly three more maybe animations， light shadows， maybe menus and hs。

 But then I didn't go too far into that。It's not that popular。 If there's an interaction explicit。

 then would probably be cursi based for Macer based AR GPS location is definitely so location is definitely implicit。

 and then the Fidu obviously the actual marker that plays a role。

 usually So when it comes to Mac Mac less AR experiences are usually a little richer。

 but not necessarily in Webex R。 I think and Webex are what we can do for now。

 what I'm gonna show you is 3D model。 animation。 Yes， I can bring back the animations。

 I'm gonna do that actually， lights and shadows。 I'm gonna talk about that a little bit。Environment。

 yeah， but。I mean， I can show you an environment we can play with so let's see how that goes and physics。

Yeah， so physics could be。Interesting， but I think for the current handheld。

 unless it's physics with a virtualch environment， this would work。 but physics with。

Like the way I'm going to show it or the way I've shown it with the Hollolens using a mixed of the toolkit where basically the cubes would react to the spatial mesh that is a little bit too advanced for what you can do right now on Webex are spatial sound that would be no problem at all。

 just how to demonstrate but it is it is possible。So hand interactions， yes， if you're talking。

 obviously if you're talking headw， I'm going show you handheld。 but then later， maybe at the end。

 I' also it's quickly going go into the Hollens is charging right now。

 the Hollands to speech and voice， Yes， especially with head worn not so much with handheld AR。

 GPS location Yeah implicitly and it's not it's not often used and then obviously environmental features right now。

 this would just be planes in Webex are。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_7.png)

It's harder to get access to the actual spatial mesh， so depth API was just released on AR core。

 so maybe it's going to make it into the browser soon。So， first of all。

 we can actually just take the standard a frame template。 So the one that that you see here。

And this one， when I run this one on my phone， I'll show you what happens actually。

 So here is the a frame template。 And I'm gonna actually run this in the bug mode。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_9.png)

That's important。 Once I have an de back mode， did you notice how I now I have an AR button on there？

 So I'm going to go into the AR view， and I'm going to like go into landscape。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_11.png)

And。Well， it is actually AR。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_13.png)

The way I know is because I can actually move into the scene。

 so Z is supported and I can go backwards。And。But the stuff is pretty far away。

 And so the sky should be going and all these kinds of things。 we're going to make a few changes now。

 Let's do this first。Hello world is basically like the template。

 but as I did for the marker based is on the left here， you can see the marker down there。

 So I removed the sky here as well。 And for this one， I'm going to do the same。

 and I'm gonna run the marker list hello。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_15.png)

And it is based on this aframe template， but again， removed the sky and rescaled it down。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_17.png)

This showed you was to big。 So now I'm going to show you this version。

 and we're going go to my glitch project， glitch me。And here。If we run hello world。By going into AR。

 then it's kind of like there， it's smaller。And。So now it's kind of cooler right。

 so the distance is better， you can go closer， you can look at the objects and you can also go further away again。

And so basically， the sky is removed and I've resized。 I can't even make it when I make it。

Want to make it baby size。 Okay， let's do make baby size。 I like baby size。

 So let's do baby size just so you see what we can do with the scale。And。So this is。Okay。

 now I'm going to make it really tiny。 so I'm going to make this like。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_19.png)

That， so that's even smaller。 And you can see how small becomes here。

 And I still have it at 80s cent。 And I'm just gonna actually， just gonna go over。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_21.png)

To the phone and run it there。 So I'm just going。Maybe get up。Edit this。

 I actually editing this one right now。 It is tiny， as you can see。And it's not super tiny。

But it's definitely smaller than before。 But what I would like is I'm going to make it really tiny。

 And I think I can also make it a little lower。 So it's hard。To， it's probably not。

 it's still above the。Table a bit， but I'm gonna make it even smaller， so。嗯。I'm gonna to go to to。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_23.png)

It should be。Really。I mean， that's really small。If we preview here。

 this preview again isn't really great for getting a sense of how big it's going to be in AR。

 but try this out again。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_25.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_26.png)

嗯。So， let's see。I'm going to just reload the scenem。And small， yes。Go into AR。 Now it's。It's too low。

But it's kind of like floating there now。嗯。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_28.png)

I don't understand why it is。Or it went lower because everything is kind of like tiny now。

 So that makes sense。 So I'm gonna actually change it to one， then。

Because I really wanted to try one more time。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_30.png)

So， I'm going into A。And now this is kind of cool now。And。It's floating a little bit。Above， but it's。

 and it was re。 okay there that the table is obviously completely mono chromromatic surface， but。

It does kind of look pretty cool now and tracking lost， okay， just because too much white。

 not enough environmental features。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_32.png)

So that keep that in mind， right， as you're like going over a monochromatic surface。

 tracking is terrible。Then it's going to refine itself kind of like it recovered。

And that's why they wanted to move left and right initially。 And now。It's better， but it。

It's trying to re。 It's gonna get confused。 So too much white there on my plane。 But still。

 the first part of the demo was pretty cool。 Alright， so we've done how world。Simple， well。

 simple would just be a。嗯。I'm got do a simple one。 Okay， so simple would just be。

We got just gonna do a box。I'm going to show you a box and。That is red so。

And then what I would like to do is we're actually gonna have it on the floor。

But we are going to have it。50 cm in front of us so。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_34.png)

If we look at it this way， then。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_36.png)

yeah， inopacity。 We need a little bit of opacity， otherwise。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_38.png)

It's opaque op， and so less opacity。 So otherwise it's。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_40.png)

Not transparent， so I like semi me transparent。So I'm going to try this on the phone。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_42.png)

嗯。So here we go， reload。Okay we have our a box now and then we move a little bit。

 and now it is here on the floor and no occlusions so。Suspension of disbelief， okay？嗯。But。

Kind of looks cool。 It's anchored， and I can move above， and it feels like。

Does it feel like a meter by a meter。 Probably feels like a meter by a meter。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_44.png)

嗯。Yes， so no occlusion here， not nothing to advance， but we should plan for it。 It's going to come。

 And so that's like one of my tips later。It is going to be there one day， okay。

 so we have the box example。We're doing well。You're going to get the giraffe， okay。

 so the giraffe is obviously kind of。😊，Interesting and fun。 So giraffe， giraffe giraffe。

So I have prepared this a little bit in my single example。I am going to get the G。

And I'm gonna use this as well as my starting point。 I will need the Google Po。So。

That one I will need。 Otherwise， I won't be able to see myra， and we can always test here， right。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_46.png)

And so there's a giraffe now。 So we have the giraffe there now。And。So that's pretty cool。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_48.png)

And I'm going to。Loaded。On the phone， the scale that I have here is already。

 it's actually the same scale that I used in one of the VR versions。

Andm gonna get the animation back because I like that animation。

 So I'm gonna get the animation from my VR project。 I think I had the animation， even in basic， yeah。

😊，So here we're going to have that animation seems to be recurring。But I just like it。 and it's cool。

 not in， in this one is the one that we're working in。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_50.png)

Okay， so if you play this now， then we have a little bit of shaky， shaky， okay， cool。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_52.png)

Run on the phone。Yes。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_54.png)

So it's going to be big。 okay， it's going to be a big giraffe。

So I just want you to be prepared for that， let's get up bam。And then there's our giraffe。And。Yeah。

So it moves a bit。I thought it moves a bit。Yeah， it does move a bit。 Obviously。

 the entire body moves， but。It is pretty cool。 So we have to show off in here。

And one thing that I wanted to talk about is that we should definitely。

Do a little bit more about light。 So what you can see is obviously I have a light source。Over there。

 And so obviously， from from this right side， there there should be light， but from this left side。

 there shouldn't be。Like there is no light source nothing is on on this side。 So I'm gonna。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_56.png)

Do a little bit about the light。 We don't have light estimation at this stage。

 but I wanted to do something about the light。So this is my demo here。嗯。

We're moving a little faster than in some of the other demos， but previously。

 but we already know more now。 So that's why we're faster。 So what I want to accomplish is。

A spotpotlight on this side。And I also want to reduce the emmb light a little bit。

 So I'm going to do this in two steps。I'm going to actually have。嗯。I'm going to add an ambient light。

So a light type， ambient， and then color。Color。Can be silver。And so， that's my light and intensity。

Should be。Maybe seven， so let's see what that looks like。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_58.png)

You can see how it's already darkcker。Okay。But we will have a light coming from the right。

 So I'm going actually add that light from the right。 Now， I'm going to use the spotlight again。

 I mean， we've done this kind of before。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_60.png)

And so， I a spot。I'm going to make it pretty bright。Intensity。Yeah。

 I have a pretty so the position is interesting。 So I know。

 So what I'm thinking is the giraffees at 0，0 and then 1 m in front of the camera。😊。

And I I'm gonna place it roughly where it was before。 So I know that the light。

 my light were a little bit of to the right from that giraffe。Same。Actually。This is maybe 1。

8 meters high， the source and maybe one line。And so I'm looking like at the light for right now。

 And then also， roughly。A little bit further back。 So it's a little bit。 I wanted to。

 And then we actually wanted to shine at the giraffe。 So we're gonna say giraffe is our a target。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_62.png)

So now we're getting a light source from the right。And。There， and actually。

 what I'm gonna to do is I'm going for de backing purposes。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_64.png)

I' am going to put it as sphere in there。诶。We're gonna make it color。诶。FFF， So also wide。

you're gonna make it。It's going to be right where the light is。

And we're going to have the scale a little bit smaller， So maybe。

So I want it to be looking like a light bulb and opacity。嗯。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_66.png)

Cause it's for debugging。 So relatively low opacity。

 I just want to show you where the light source is。

 So this is roughly where I've played the light source。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_68.png)

Placed the light source， let's make it yellow， even though our light is not yellow， but。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_70.png)

Just so for debugging purposes， so what I'm starting to do now is show a little bit。

How I can play with also light in AR。 when I don't have light estimation right now。

So we're going to run it。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_72.png)

So I've defined the spotlight shining at my object and I placed it roughly where I believe the。

Lights are so going to reload our giraffe here， and。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_74.png)

There is， we can't go to the right yet， so I'm just going to get up。 We're going to place it。In A R。

 roughly so where it was before。 So now it's there。 And let's see。 So the light source， hey， I did。

 I did pretty well。 right， The light source actually matches that one。

And I'm going to just make sure that my leash is long enough here。嗯。What do you think。

 I think it's cool。I kind of matched the light source。And it's realistic that it。

 it gets lights from， from this side。And it still looks kind of cool， and it's moving。

And here we have oops cable。I need to make sure that I get the cable with me one second。

It does really look cool， doesn't it Okay so and now with the cable。

 we are going to this side and it's still relatively bright on this side。

 but it's not as bright as on the other side。I'm just gonna look at the giraffe。And yeah， I mean。

 obviously， this is a really shiny giraffe。But I like it。 It's pretty cool。 I can look up at it。😊，嗯。

Wished I could feed it。 Now， this is sad that we don't have people segmentation。 Obviously。

 it would be great to see my hand in front of the giraffe。

So this is something that is currently not possible。 You know， in my VR demo。

 I threw like things on the floor to feed it。 we could probably。

We could actually drop something on the floor， oops， a little bit of a tracking issue。 But anyway。

 I'm pretty happy。 And also， let's just look at the light。 I did a good job there。😊。

Kind of like matched it really nicely where the light is。And trackingre works， well， okay。

 just when I said it。But still cool， so。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_76.png)

We did our giraffe example and we placed it in the environment。

And the last thing I want to show you is hit testing。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_78.png)

So for that one I'm going to actually its a little bit more advanced。

 so I' can't run it in code pen and I have everything prepared here in in this file and I'm using a contribution and I should acknowledge this。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_80.png)

Which I thought was pretty cool。 A contribution from。This project。

This is the original hit test project and I've edited it and adapted it。

 and this one was created by Add Rose Cannon， at least it's the nickname here。

And it's a cool little example。 So in her example， there is。诶嚟啊。And。嗯。She has like this lion。

 they have this lion。And。Yeah。We are going to first just have a cube because I want to show you a few things。

 So I'm going go into my hit test example。 So I'm basically。

Getting that hit testing library since it's experimental。 I have to use like the latest。

Build one of the latest aframe builds。 So it's not the release yet。And。

Then I need to use Web XR optional features。 So this is from the Web XR specification。

So the latest aframe master supports the Webex R property on the A scene and uses some of the Webex R stuff that is now in 3 JS。

OrOr directly in the Webex are specification through the browser。 So they added it。

 I think these things will merge eventually and become quite cool。 But for now。

 we have to use hit testing。 And hit testing is when you， I'll show you in a second。

 But when you basically look at， at the screen。😊，And touch the screen。

 And then it finds from your touch point and finds the plane that that that touch point will intersect with as it should ray into the scene。

 So we've talked about this in the lecture。And。Good， I'm just gonna have a box there， so。

I also have put it on a plane， but I hide it in AR。 That's something that addda provides。

 And so I just use that as well。And this world， which is kind of like a preview。

 So when I run it in here， I'm just gonna。I'm just gonna run the hit test now。 So hit test。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_82.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_83.png)

So when I run it， you see it like this。And I will replace the whole thing with it in A R。

 And for that， I have a radical。 And in that radical。

 I have a preview of the box that I implemented it。

 It's basically the same thing that's going to be placed in the world， but it has lower opacity。And。

I should also do。Sder。Flad。嗯。Yes。And。Although I'm not sure exactly whether that's going to work with opacity anyway。

 so we'll see。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_85.png)

I'm going to run it。 Okay， so time to run it in on the phone。 So in A R。

 So this is now with hit testing。So， clearly。More advanced。And close to what I showed you。

with the giraffe earlier。So here。We have。The AR version hit testing and so now I'm going actually started。

 so when I started in AR then it shows this preview where the cube is going to be。

 so if I'm going to go here on this white thing then it's going to be sitting。

 it's actually still on the floor I didn't really detect the plane。嗯。But okay。

 replacing it on the floor。So me moving the phone up and down， actually。

Does the hit test and place it at the hit test location。 And when I press it actually really。

Places it there。And here I can also put it up on the screen。So now it's like sitting。

 sitting on that table。 So are we gonna put it here on the chair。So I like these previews。

I think it's better than some other form of radical。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_87.png)

I'm gonna show you a more。Prerimitive version could be。We just show a ring there。A ring。

And then material shader flat。And。Rootation is。 I'm going put the flat on the floor。 So color。

We're going to do white。And opacity。0，9。So。How to， I'm gonna just like， have this。As a preview。

 put it on the world。 So that's the way you can debug things。So it would show me this ring。

 and then it would place the cube inside。So that's cool。 But I don't wantanna see that。

In the initial view， so only after placement。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_89.png)

So let's see what you think of this。 That's kind of。Goin to run it。

 going get up without killing everything。Reload。Go into A mode。And as we move， we see a pretty big。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_91.png)

Radical。I think it's way too big。So。We'm going to actually change this。 Okay。

 I'm going to make the scale。 forgot the scale scale is important so we can really work with just。

A much smaller， so just 15% of this。We'll do the trick。 Let's go back， try it out again。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_93.png)

I like it not really preview。 right， It's more like telling you where the placement would be。

What do you think， So standard radical。And then， you would。okay， we get the idea。

And so I would like work like this now or place it here on the。Chair can be placed on the chair。

It's going to be on the floor。It didn't detect the chairs of us yet。Okay， now it got it。

 so now we placed it on the chair。Okay， so that's the radical solution。And this is nice。

 I put it nicely on a table table。 So this is hit testing as I touch it actually then places is at。😊。

The where the intersection is。 It does actually constant testing all the time。

 That's how it finds it finds planes and then it puts the radical and adapts it to the size of the plane。

So kind of like it rescales depending on。How big the plane is。 So that's similar to。

 at least in this implementation to marker based tracking。These were my demos。

 I'm going to wrap up here with a few tips and tricks a lot of this stuff is。

It's pretty early stage and wait I wanted to show Holloands， I'm going to do Hollands GoPro。Okay。

 so I'm going to just go into the browser edge。I can place it here。Okay。

 I have already entered the URL。 I'm just gonna load it one more time。

And so then it there a little warning there。 I don't know why that is。

 So it's just like a little bug。So here we have already the scene and we can interact with it a little bit。

 but I actually want to go into the VR mode。嗯。嗯。Pla it。It's going to be there。

It could have placed it live a little bit differently I guess。 so anyway。

 so it is here now and as I go as I get up， you can see how it's kind of like obviously now the occlusion stuff。

 nothing advanced， even here on the holidays not working but it is cool so we can see the scene and。

Yeah， so。it appears larger than what I thought we had。

 let's just double check the code one more time。I'm gonna actually lift this up， so。

That I can edit this。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_95.png)

We would want to make it even smaller， and。So。Then。I'm gonna make it。Actually， is0，5。

That would be larger， actually， so。0，0，5。That should be quite a bit tomorrow。

And I want to make it really  one。so。Oops， I didn't add one。 So that。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_97.png)

Now it's tiny。 Okay， let's see what this looks like on the Holland。 So let's go in here again。

How do we。So go to home。This closes this。 Alright。 I'm going activate this。 So it's going follow me。

 And I'm gonna kind of like place it here。In roughly more like in front of me。

 So're gonna leave it here。And they're gonna reload。The scene。ok。

And I have changed a little bit the resolution。It's definitely tiny now。 You can see how small it is。

 And I'm going to go into VR。 I actually going to go into A R。 So for that。

 I actually had to enable some of the the web VR settings。And now， the question is。Where is it， Oh。

 it's really here。 I didn't even see it。Now， that is cute， right， so。That is a tiny。

 little a frame scene。嗯。Ya。Okay， cool though it does work with Mac S AR。 It's really tiny now。嗯。

I don't know。 I've always， yeah， that's what I was looking for before。 It's so。Okay。

 we are done here and that's the Hollands part， at least so。Okay， let's take this off then All right。

 I'm going to show you more Web Xr samples， let's do that。

 so let's try to find them Web XR Web XR samples。Good。Samples。

There's air stuff done there position audio hit test。Hit test A AR basics here。

 hit test that's radical as the flower。Bear bones， A R， extremely simple。 Which one is cool。So。

 let's do No dependencies。Okay， let's see hit testing。star利啊。This one has the they。

 and then it like places。Flowers there。 sunflowers。Yeah， pretty nice， right， I know。

It's always nice to have a little bit of a model。嗯。But I like my giraffe。Okay。

 you have a few flowers。Immersive AR is the planets。I always like solar systems， so。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_99.png)

This is cool。 Let's go into landscape。And now we have all these planets here in my。Well。

 there's one here even。 And then there's the sun， wow。



![](img/68dbc4bc4cf08c5695a755fbe87a81b9_101.png)

The asson is big。My version of the solar system wasn't so bad。 Check it out in course， too。

Of course to everybody。Okay， so more Webex are samples， if you will。Good。

 so now we're going to wrap up so tips and tricks。😊。

Provide a preview of the content during placement I wanted to show this with my cube essentially it's relatively simple。

 but you could imagine like some kind of simplified。

 maybe a little bit reduced opacity so more transparent preview so that I know actually what the scale is gonna to be once I place it because what I don't like and a lot of the experiences right now。

 I always have to always have to place it first and I have no idea what's going to happen it's always like a surprise。

And probably not a good idea。The other thing I say here is incorporate light and shadow to blend with the environment。

 That's my example with a giraffe。 So here this one where I then started to place a light in the background。

 I thought that which is then here on this side， placed the light roughly there and then it spotlight to shine on this side and make it a little bit darker on the other side。

 Also， you could see initially， it was too bright for the room。

 And so reducing the opacity with the ambient light， sorry。

 the light with the ambient light with a shining a little bit darker。

 less intense ambient light was already an improvement， I would say。😊。

So plan for that and also plan for the impact of acclusion rendering and light estimation。

So very important。 if you don't define lights， it'll just be the default lights。

 And I could imagine that as soon as the light estimation stuff is more or less available per default。

 we don't know actually what the good default would be but it might be that it actually really then reduces the light for your entire scene。

 In my case， it would obviously be great to rather than me hardcode。 I know where the light is。

 And I know relative to the giraffe because I knew where I wanted to place the giraffe。

 but rather than hardcodeed this way， it would be better to obviously have light estimation in light estimation would give me the temperature and the color of the light roughly at where I'm pointing。

 probably。😊，And I'm not sure whether they' are going to be ever be able to estimate the location of the light the source。

 they obviously when I bring it into view， they may they may remember we can build a history。

 and then we can see there was really a bright temperature and color there。

 So I use daylight bulbs that maybe makes a difference as well。😊，嗯。And also occlusion rendering。

 So as soon as that kicks in in the browser， you should think about how what that means in terms of scale for your experience。

 And this is， what I also would say is tips and tricks， I haven't shown that too much here。

 but I would prototype these Macca less AR experiences using using 360 VR or Macca based AR。

 So I have a this example here with the menu and a three， this is my this is my menu。 Where is my。😊。

I have the 3，60 example here。 That's what I mean。 So with the 3，60 example。what I could do is just。

 I'm going to just grab the 360 here quickly。And for my。For one of my examples。

 so here was the giraffe。With the light， with the emmb light。 So now I'm going to just like bring in。

 I don't need this， but this。Image， and I'm going have a。Sky sky that I just do for testing。

And I'm gonna use the photo。And so if I now tested this way。I basically can preview。 So in 360。

 I'm gonna reload again。 So now in 360， I know roughly， okay。At this stage。

 I had the the glass table a bit closer to where I'm sitting right now。 but the light。

 I kind of like matched relatively well。😊，And I was doing this relative to， to the giraffe。

But with 3，60， you could prototype。Before like even without being in this room。

 I could start to prototype I know roughly okay， I'm gonna to start here。

 that's my starting location。 So from there the giraffe is gonna to be 1 m in front and then the light is gonna to be1。

2 m to the right and 1。9 m high so that's how that' that's what my approach here。

And so you could also use MacA based AR， So I've shown you all these examples before like here with a giraffe Mac based previous video。

Obviously， then from here to there， we can change the scale entirely with marker。

 unless I place a really fat one on the wall or on the display in the background。

 it would be hard to have a。To be the kind the macon is to stay in views。

 It would be hard to get an experience like this where you're really looking at a life sized animal with a marker。

 But anyway， could prototype it this way。 That's all I'm saying。

And then consider allowing users to adapt the skin of the experience。 right， right now。

 it seems like something。With a hit test example that I was using and that was kindly provided by Addda。

 So someone from the community， the Web X R community。With that， I mean。

 we can adapt the scale according to kind of like the plane that we' are detecting， but not really。

没了。We are still making decisions on behalf of the user。

 and maybe we should actually ask the user or indicate like the scale of their experience。 Obviously。

 I could point， I mean， I have a little bit of control。

 but I can point at the different planes and I can see like the on the table as I had it or like here on the glass table。

😊，But we could still give users more control， I feel like。

 and then also finally consider adapting the layout to fit the detected plane。

So example would be when I look at the table here。Like I could actually lay out the scene maybe this way。

 And then when I placed the giraffe in the room， maybe in this view。

 the layout could be more so longer or deeper， let's say deeper。Rather than wide。

 And so more along the Z。And so what he didn't see so well， but。

As I was moving around with a radical， the orientation of the animal actually was kind of fixed。嗯。

So we can show that here in this example。I'm going to come back to this video。

 So here when I go into AI， what I showed initially， you see how the orientation is fixed。

So of that is essentially the radical that I'm using here。 and that orientation is always fixed。

 So I cannot actually place the giraffe in a different way unless I restart the app。

 And that's something that I think we should definitely address somehow of because that is tedious。

 It looks cool in initial demos。 But the more you think about these， it's still experimental。

 It's still early stage。 and it's。Not the final experience yet that we would want for our users。

 But so these are my tips。So consider adapting the layout to fit the detected plane。

And at this stage， I have to say it like consider and maybe perhaps do these kinds of things just because it's so experimental。

 Unfortunately at this stage， it's not like light estimation， occlusion。

 It's all gonna to come very quickly to the web might already be there。 I mean。

 we are talking we are in September 2020 right now。 And so maybe when you watch this it is there。

 And at that stage， I feel like I should do an update of this one。 Also， by the way。

 if you enjoyed these kind of like well， more handson lectures。

 I've often done online office hours this way with students I fixed that code live and others could learn that way。

 and I would prepare to do something as part of the MOOC as well。

 So let's see how we could schedule this， obviously with time zone， it's gonna be difficult。

 But I enjoy I don't mind making mistakes。😊，And then learning。

 And then have you learn with me that way。 So I think that would be a great way to learn。

 So I enjoyed these four lectures that were a little bit more hands on。

 and a lot of things went wrong。 But so hope that you still learn something theyre also a little longer。

 but less edited and I think that's actually probably good。 so you can maybe follow along。

 or at least like try to follow what I'm doing。 So each of the examples， by the way that I had here。

 they have links。😊，So hello world， and I have them all。 This is obviously my coat pen。

 I have them all on this Xile MOoc project that I'm going actually give。

Kin of I give out with the MOC so that you could have a starting point。

 and I will also update this from time to time。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_103.png)

嗯。When I have the time， but I'll promise I'll keep it up to date I'm obviously working in this space。

And my students in the residential program also need the latest code basis。

 So there are strong incentives to keep this up to date。 So thanks for watching。Hope you enjoyed it。

 So now you keep working on your AR scenes as part of the honest strike。 Hopefully。

 that's why you're watching this so that you can get a better understanding of how to approach that step。

 And it's， it's exciting。 And then get ready for the peer review。

 So also watch my instructions there。😊，Hope to see you at the end。

 also hope to meet you at some stage in person， obviously， or at least in some kind of online office。

 our world All right。 Thanks for watching this。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_105.png)