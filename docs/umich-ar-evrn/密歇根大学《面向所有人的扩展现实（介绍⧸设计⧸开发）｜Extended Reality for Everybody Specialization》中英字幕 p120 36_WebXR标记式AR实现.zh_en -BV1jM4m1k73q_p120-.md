# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p120 36_WebXR标记式AR实现.zh_en -BV1jM4m1k73q_p120-

![](img/190e3597363144eddd250d4ccc81286b_0.png)

![](img/190e3597363144eddd250d4ccc81286b_1.png)

Hello and welcome to this video on marker based AR experiences in Web XR， specifically。

 we're going to use aframe and have a few examples of markers here。

 the hero marker that you've seen before， also put like a kanji marker up like this or a cutout like that。

or I also have like these little markers that I can just like hold and so I'm kind of feel like I'm well prepared to show you a few examples of using markerB theyR and I have a webcam set up and I have。

😊，A few examples prepared for us。 So we're going do single market tracking， multimarket tracking。

 I' going show you how to bring it a little bit more of a VR world into marketbase AR。

 we're gonna do the hello world AR well hello world in aframe but for AR and I'm also going talk little bit about interactions and some of the challenges you will have have there。

 throughout this little demonstration。 I have shown you in the first steps how to get it to run on the phone。

 So each of these examples will actually run on the phone but I'm not gonna actually maybe I'll do some I'll do it sometimes we'll see I'm not gonna put the GoPro on now I feel like that would be a little bit too much。

 So here are my slides。 and so one of the things we are aiming for or something that I've shown before is this scene where we can see the giraff as like one of the elements from the zoo case study on。

😊。

![](img/190e3597363144eddd250d4ccc81286b_3.png)

a hero marker here。And that's something we're going to recreate also as well in this little session。

So when I think in terms of X experiences， then when it comes to markerb， they are content wise。

 usually just a 3D model that we look at， maybe a little bit of animations， lights and shadows。

 maybe。Menuus and hass maybe mostly it really just looking at a 3D model。

 not even too much going on in that 3D model。 Sometimes as I say a little of animation。

 When it comes to interactions， it is mostly cursor based。 Obviously， we don't have a controller。

 voice and speech are very uncommon and。Though actually possible。

 And on the implicit interaction side， a lot of it might be location based。

 but obviously marker based， fiduo。 So I showed you lots of examples。 This is the Kanji1。

 This is the hero1。 These are some of the most prominent ones when it comes to A R J。

 most of my examples were probably just involve the hero marker。😊，you print them out usually。

 so that's what you should do。 You can actually display it on a computer。

So you could actually display it on the monitor。 That's something you could do。

 And I have shown that in the first steps as well。 So Air GS is really this Macb。

 So basically when you。When you see a marker and bring your phone into view。

 then it would show like this marker when it runs an ARJSD and it would show some kind of whatever the virtual content is that you define inside that marker。

 so ARJS here has a little bit of a new website now， some examples。So feel free to look this up。

 tells you how to em it。 I haven't played much with these other modes。 For me。

 Air J S was always just marker based。 I don't actually really understand the differences between image tracking and location based。

And then you have an AMMAC tag and that has various options and you can use it with 3JS so directly on top of 3JS or going the AFM route。

 which is what we're going to do。So that's the documentation。

 and then this is what the marker looks like， so you could print this out， provide PDF of that。

And or I link it， link it to it way you can find the marker。 And here's our first example。

 So I have this A R J S template。 So I'm gonna actually like open this again just so you believe me。

 So it's here。 It's already working。 So basically。

![](img/190e3597363144eddd250d4ccc81286b_5.png)

![](img/190e3597363144eddd250d4ccc81286b_6.png)

I have the webcam set up here， it's looking down there on the marker and it's shaking a little bit when I move。

But that's just how it is。 and now I can actually interact with the marker， move the marker around。

 do all these things and the tracking is relatively robust。Again。

 if you includecc the marker or if you kind of like bend it so that only half of it is visible。

Then it would work。 But as soon as the full marker is in view。 it kind of works。

 Sometimes I have a focus auto auto focus problem here。 I do have lots of these markers。

 I've printed out quite a few because I usually go to lectures。



![](img/190e3597363144eddd250d4ccc81286b_8.png)

And this is one of my nicer ones， but here are lots of markers。It's going to place them there。

 And so they all work。 And when they are detected， usually just one of them。

 So then it finds the orientation。Cameron is a little confused because I like go in with my hand。

 It tries to refocus。But now we want the attention， so。One marker at a time per default， Okay。

 so that's the ARJS template。 Feel free to use it。I do have a little bit more of a project prepared for us。

So we are actually going to work in my glitch project。 I have an ARjS well folder。

 I was just playing around with a few things in here。

 but ARjS index is our starting point and so that starting point is actually exactly the same contents that we have in the template。

 So you bring the marker into view and Ta okay， so let's look at the code。

 So for that all I'm doing is getting aframe getting aframe ARjs and then。



![](img/190e3597363144eddd250d4ccc81286b_10.png)

![](img/190e3597363144eddd250d4ccc81286b_11.png)

This is kind of more or less required so that one of the issues you may have is that the marker。

 So if the marker， which right now is really a box of scale 1，1 red and a little bit。0。5。 Hi。

 I can explain why that is so that we， we are actually sticking on top of the marker。 So the 0，0。

0 of the world now is really like in the middle here。 And so that's something。



![](img/190e3597363144eddd250d4ccc81286b_13.png)

To， to remember，0，0，0 is there。 So if I actually place if I。



![](img/190e3597363144eddd250d4ccc81286b_15.png)

If I put it at 0，0，0， then。

![](img/190e3597363144eddd250d4ccc81286b_17.png)

That's what it would look like。 So you can now see， it's kind of like。This。

So you you want it to be on top of the marker。 so you push it up along the Y。

 and if you wanted it floating， then you could put it at one。

 So then it would be like floating a little bit above the marker doesn't look good。

 actually usually like this gap doesn't look so good。



![](img/190e3597363144eddd250d4ccc81286b_19.png)

![](img/190e3597363144eddd250d4ccc81286b_20.png)

![](img/190e3597363144eddd250d4ccc81286b_21.png)

So what I'll do usually is just like I take half of this y scale so that's the scale per default is 111 so that would be that reloading and it'll sit on there nicely。

 What you could also see is I actually have a plane here for which I have linked the hero marker So that's just like something I've uploaded to this glitch project in my assets。

 So here's the hero marker。

![](img/190e3597363144eddd250d4ccc81286b_23.png)

![](img/190e3597363144eddd250d4ccc81286b_24.png)

Just so that we have a little bit of feedback regarding tracking， so。



![](img/190e3597363144eddd250d4ccc81286b_26.png)

And I I can show this or not。 now I'm gonna just show you the plane。

 And so this is something I've shown in the previous video。

 but this is just like to show you how well the marker tracking actually works。

 it gets the pose really relatively right。 It's just planer。 So just like a plane on a surface。

So what I mean by this if I bend the marker， it won't work， in fact it stops the tracking。

 so something to keep in mind。

![](img/190e3597363144eddd250d4ccc81286b_28.png)

And and then so I'm gonna just get my object back and we， we can just like hide this plane down here。

 So in this case， we just have really the marker。

![](img/190e3597363144eddd250d4ccc81286b_30.png)

![](img/190e3597363144eddd250d4ccc81286b_31.png)

But don't show anything for the marker and then just have the virtual content on top so one of the things I wanted to show you is the hellello world。

Okay， so how would we， And I'm gonna actually do it rather than just copy paste。

 So in so I can actually change， obviously， the content in here。 Let's just get this plain back。

 But instead of this box， we are gonna。And we're like inside this marker， okay。

 that's maybe also something to say。 So you're defining this marker， a marker， which is P said hero。

And if I wanted to， I'm going to just bring the content back。

I could change this to a different preset。 So right now it's。



![](img/190e3597363144eddd250d4ccc81286b_33.png)

A hero。 But if I change it to Kanji。Then it wouldn't actually show anything anymore unless I bring in the kanji marker。

 So once I bring in the kanji marker。 So now it uses this pattern。

 this kji pattern instead of the hero pattern。 So question would then， of course。

 be how does it work with multiple markers。 And I'll get to that。



![](img/190e3597363144eddd250d4ccc81286b_35.png)

I'm gonna go back to hero， and we're gonna get the a frame A R scene。

 So we're just gonna go to a frame I O。

![](img/190e3597363144eddd250d4ccc81286b_37.png)

![](img/190e3597363144eddd250d4ccc81286b_38.png)

嗯。Not now I just want to go there， show the source and grab the code for just a hello weld so the typical。

 and one of the things I wanted to see is how big it actually is。AndSo， this is our。A frame scene。

 the way it usually is defined。 just so you remember。This is what it looks like。Okay， so。

 and now this is obviously the typical cubes sphere your cylinder plane。

 So if I now bring this into our scene instead of the box， what do you think is gonna happen？ Well。

 trust me， it's gonna look pretty， pretty。

![](img/190e3597363144eddd250d4ccc81286b_40.png)

Weird and big。 And why is that。 So， okay， first thing I could do is。

But I could adjust the camera a little bit， so I'm going to move the camera。

 I actually don't want to move the camera。 What I'm going to do is I'm going to use a slightly different marker。

 so a different marker size。I're going to remove the big one。So let's lose this small marker for now。

Really， the issue is the scale。 Okay， also， if you think about how VR works。

 we usually assume the camera will be at 0，0，0。 So like where the webcam is right now。

 And then we are pushing the scene-3 out。

![](img/190e3597363144eddd250d4ccc81286b_42.png)

But the scale is automatically scale of the marker。 It's normalized by the scale of the marker。

 So the best thing time to do is actually put this entire world。I mean。

 it's not too big a world into an entity。And then scale it down， so。



![](img/190e3597363144eddd250d4ccc81286b_44.png)

One fourth of the size。 And so let's see what that looks like。 Now it's cute， right？

And if we're doing， that will almost fit。 Okay， and now we're going push it a little bit along the Z axis。



![](img/190e3597363144eddd250d4ccc81286b_46.png)

And so we're going to do position and it's probably。So， this is。This is minus-3。

 so we're just going to do0，0。 and then we are going actually get it towards us。

So that's like half macro size down that didn't work so。



![](img/190e3597363144eddd250d4ccc81286b_48.png)

Going to do just the whole thing。 And that's kind of。How we want it。 I mean， this is now my baby。

 my baby hello world。And it's kind of cool。Has the shadow and everything。 I like it。

 And I'm gonna bring back the bigger marker just so you see bigger marker， bigger world， okay。



![](img/190e3597363144eddd250d4ccc81286b_50.png)

Really small， big， small。Big trekking is always better with a big a marker。

 but maybe you don't want it to be that big。 So we've done that。That would be my hello world example。

 And then I also wanted to do。Interaions， so the helllo word example is really my example of showing you a little bit more more complex。

 I's say， Okay， because you have like three things in here。 Obviously。

 maybe you think more complex means models。 I'm gonna get there。

 They're gonna get through the giraffe。 Okay， I do want to do。I do want to do interactions。

 I think it is pretty key。And interactions with models are a little tricky and I talked about collliiders and all these kinds of things in the VR well the VR hands on videos。

 so here I'm just going to focus on the Mac based AR interactions。And keep it relatively simple。

 So we're gonna get actually a。A red box， so color is red and position is 0，0，5，0 scale is。

Default and bringing back our plane。 It's red。 So that's what it's gonna look like。 Ta bam。

 maybe make it see through opacity or add opacity so that you can actually see the world behind it。



![](img/190e3597363144eddd250d4ccc81286b_52.png)

Usually do  point8 or  point5 or something like this。 So's what we had before。 And now， well。

 what you've learned is obviously， we can use。

![](img/190e3597363144eddd250d4ccc81286b_54.png)

The array origin。So we can use a cursor on the scene。That's something I've shown you before。

 so Chris or。Ray origin my house。And then， we could。We could do a little bit of JavaScript。

I'm gonna show you previously， I've done the events set component。 in this example， I'm gonna。

Actually do a little bit of JavaScript down here。And we're gonna to have our function。Change color。

o k。And then。That's gonna call。It's called。Eleement， and then H L。Sa Ed。Color嗯 color。And那个人都。

We're going to take two parameters here， change colors of function。

 And then we're gonna have on mouse enter。诶。And that is。Change color。This。And then。

Well let's make blue， make it blue。 So as we enter。 And then as we exit， make it back to。Red。



![](img/190e3597363144eddd250d4ccc81286b_56.png)

Leave， miles leave， on leave。So the question is now。Why does this not work？

And that's because there are issues with this Ray origin cursor Tingy。



![](img/190e3597363144eddd250d4ccc81286b_58.png)

And also。Mouse enter mouse leaf should I actually work。 Let's see that。



![](img/190e3597363144eddd250d4ccc81286b_60.png)

We have a little bit of deep bag information here。嗯。Yeah， so no  errorss there。



![](img/190e3597363144eddd250d4ccc81286b_62.png)

Muse enter miles leave。嗯。Maybe that's not the exact right， the exactly the right thing。

 So what we're gonna do is we're gonna call this。They're going to give this an I D。

 I'm going to call it box， and then。Box set attribute。诶。Actually， Ed event listener。Okay。

 and then mouse enter。 We're gonna。诶。We're going just。To something like this。Actually。

 we're just gonna。We're going to change color。Of this。To。Be， okay。Then when we exit。 So my was leave。

We're going to make it red again。So to see that works。Still not。And。

I'm just like cursor Ray origin mouse。Ons。Doesn't work so well。

 The issue is that the is actually a bug in a frame A R JS。



![](img/190e3597363144eddd250d4ccc81286b_64.png)

![](img/190e3597363144eddd250d4ccc81286b_65.png)

So what you should do instead is actually go into the camera here。Give it look controls。

Maybe that's for debugging， maybe。And then we're going to have a cursor here。

 and that cursor now actually is should with the trick。 So having a cursor in the scene。



![](img/190e3597363144eddd250d4ccc81286b_67.png)

![](img/190e3597363144eddd250d4ccc81286b_68.png)

So now I bring the object into the scene。And thats， that now does the interaction。 Okay。

 what I'm simulating here is actually moving the device， but I'm moving the。呃马er。

So keep that in mind。 the ray origin， what I had before works normally well。

 but there is a bargain A frame， A R G S。 And so you kind of like have to work with the。

 with the controller。

![](img/190e3597363144eddd250d4ccc81286b_70.png)

With the cursor here。 and I I did the look controlled so I could bring things into view for debugging。

 but it obviously messes up the the experience。 So I'm gonna actually remove that。

 And the way you could debug this is like when you， when you take this and bring it into the view。

 And then as soon as the cursor enters。😊。

![](img/190e3597363144eddd250d4ccc81286b_72.png)

![](img/190e3597363144eddd250d4ccc81286b_73.png)

The object becomes blue and then as it leaves the object becomes red okay。So that's that。

And so we have a little bit of basic interactions with Mo and Mo leave。😊。



![](img/190e3597363144eddd250d4ccc81286b_75.png)

And maybe in the next video， I'm going to show you how to actually develop a component that does something like that。

We have done it BR attributes， so event set attribute， which is actually event set component。

 which is actually a component。And now we've done it via JavaScript。

I'm just wondering whether I'm just going to do this。But I had initially。

 I'm just curious whether that should have would have worked。Because， I mean。

 maybe there's something。Different about this。 So must enter。And mostlyly。

 should actually do the same。 You should actually bind it to the element， and。This is not good style。

 okay， that's maybe one thing to say but。If it works， who cares？And it does work， okay， but still。

I'd rather I'd rather you not do it this way and do it in a a nice way。

 and maybe even better would be redeine the box as。And actually， get element by I D。And then box。

 and that would be the nice way to do it。And then this one， I'll just x out。

So this wouldn't work anymore。But we still have the functionality working because I have the JavaScript functions now properly bind and I actually selected。

The object be a query selector， so we can actually make this a con because this will always be our box。

And the better practice even would be to call this box element。If you're using JQury。

 and then I always think it's better to call things that are really the Dom element L， So scene L。

 camera L， box L。And this will be the best way to do it。 Now， per definition or per per browser。

 I'd say in most browsers， what happens if you name an element with this I D box。

 it would automatically become available under window dot box。

And so users writing box would refer to this element， but。Not a nice way to do it。

 So we've done interactions。 So can take this off。 and we are going to get our。😊，那个。嗯。Girraafe back。

 Okay， so let us。Yeah。I'm just gonna just copy this as a。Another example in here index to HTML。

IJust going to copy that there so we have that there and you can see how I did it。

In the original solution， I've used the event set。嗯。So it's just using the a frame mindset component。

 That's kind of nice because you all you have to do is this。And put the cursor in here。

 So if I call interactions。

![](img/190e3597363144eddd250d4ccc81286b_77.png)

Actions that would be。I done it a little bit differently。 I did mouse down Mo up。

 So you bringing it in doesn't actually trigger the interaction yet。 You have to then。



![](img/190e3597363144eddd250d4ccc81286b_79.png)

Click down up。 and that would be theoretically， that theoretically， that would be here on the phone。

 I'm just gonna。Remove the marker for a second。And go to the phone。

See that I'll show you what this scene now looks like。 So I'm just going to open it on Chrome。

And I'm going to Angar MO， Lch me。ARGS is where I have it and then interactions。

And obviously I'll be sad if it doesn't work。嗯。Nobody knows。So here is the phone， okay。

 so I'm going to rotate。Okay， then I'm gonna bring the marker into view。We're gonna see the marker。

 And now me clicking whoops， okay。So， now， me clicking。Actually， triggers。The event。

 so I'm going to put it a little bit further away。嗯。You see how I'm using the cursor？And。Tapping。

 so hope you believe me。That this kind of works。Alright。

 and having this cursor is actually not the worst of things。

Because you know what you're pointing at and sometimes it's really difficult like it like。

 so if I'm pointing somewhere else and I'm clicking this， it won't trigger it。

The cursor that you see here in this example right now ignore that。嗯。I'm going to just go here again。

We also have the cursor there。Okay， hang on。Going to just remove the cursor。诶。

So that's not so confusing。 You're seeing too many curses， I feel。Okay， so。Weloading。

 no curs anymore。 And now we just see。Kind of like what's on the screen and me clicking triggers the action。

 I realized the webcam resolution isn't very high。 So I'm going to actually do a quick screen capture。

So here's my example scene I'll see， I see the cube， and I bring it into view， and I click。

And that then actually triggers the interaction。 And if I'm not on the object with a curor。

 nothing will happen。 So only when I'm there。Okay， so this one is a version where it requires。

Mouse down Mo app， which is the same as clicking。You could also write pointer down pointer app。

 which is more neutral。 could also use touchdown， touch up on the smartphone。

 But then it would only work on the smartphone。 So the cool thing about these interactions is that they kind of like generalize。

And I find that pretty cool。And so that was， that was just just running this quickly on the smartphone。

And I'm also going to show it here one more time。嗯。Kind of bring it up one more time。

 rotate it nicely， bring it into view。 So now we're going to see it on my smartphone。

 I see the object and I click， and then obviously me moving。Would work still。 And now it feels like。

 oh， AR and I point at the object and I click and that then triggers the interaction。 oops。

 I was accidentally hiding it。

![](img/190e3597363144eddd250d4ccc81286b_81.png)

So that kind of works。And。That's my interactions example， okay？We're getting there and giraffe time。

 okay， giraffe time， so we are getting the giraffe， so for the giraffe。I have。

 I'm going to get Google。Poly load component。So I have a single marker example。

 So for the from that one， I'm just gonna get the Google marker。

 They they Google Po load so we need that so that we can load our girae and then。Instead of the box。

 I'm going remove that script。 We don't need that change color script for now。And we have the hero。

 instead of this box， we are going to get。The giraffe。 So I have that in single。 I have it prepared。

 So this is our。Girafff。Okay， just copy paste it in here。

 so I'm not doing anything else other than like rotating it correctly， giving it the scale。

And you know what。 What I'm also gonna do is I'm gonna get the animation from the VR scene。

 So our basic VR scene headlight the spotlight and everything。 And we had the cool animation here。😊。

I'm going to get that。So。Put that in here， index。Here in this one， I'm in this one。 Get my animation。



![](img/190e3597363144eddd250d4ccc81286b_83.png)

And。Let's reload。Now we have the giraffe there and it's moving。It's a bit big。Okay。Well， you know。

 the deal you can do is a smaller marker。嗯。And it's moving， so。Like seeing an object in AR。

 It's the same one we had in VR before。 but just like seeing a little bit of an animation there。

It's kind of。Super cool， right， it actually does add quite a bit。



![](img/190e3597363144eddd250d4ccc81286b_85.png)

And I， I do like how just with a simple rotation， I mean， there's nothing。Fancy about this。

 It's Just simple rotation。Over 2。5 seconds。嗯。And that's something we played around with the A with the VR scene so。

What I'm going to do now is。Going to do multi market tracking。 So I have an example for that。

 This is this one。A R J S multi。 And I'm actually going copy from there。

We don't actually need a copy from there。 So what I'm going to do is just take the whole thing。

Duplicate。Make it a kanji marker。 I' gonna get a kanji marker， My second giraffe， and。

You gonnaan the hero over the country would look weird。 So that's why I'm moving the plane。

 And in fact， I'm actually gonna remove it here， too。And so I'll reload。 Oh， there's one thing。

It will not work yet， but I'll reload。 So I have like。Go to have。A hero and kanji。So。诶。

Iing to get hero and kanji。And now it works on the country。Oh， it does work with my oh。

 they changed that， I didn't know。I didn't know that it can per default now do multi market tracking unless I have no。

 I have just like this normally， it used to be that you had to specifically。Specify a mode。

 but apparently， this works now。I think they changed that。 So in old versions of A R G S I had to。

I had to change the the matrix。 view。 Okay， so then， okay， you don't have。

 you don't have to worry about it。 Okay， so you're just bring two， two presets。

 We have two markers in our scene now， I'm gonna show a little bit。

 This is actually the multi that we're working on。 I'm gonna hide a few things。Alright。

 so then we have。The giraffe。 So one of the issues now is like。

They're actually moving the exact same way。 Okay， so， and they are too big。

 So we're gonna make them smaller。I think this should do the trick。AndFor both of them。

We can also have them a little bit like a little bit different。

 So it looks like more like a mummy and the。Smaller one。 So maybe that's kind of cute。

 And the other issue that we have right now is that they're really。The exact same animations。

 And so I would change the properties a little bit in one of them。 So you're doing a delay。

 maybe by one second。And you'll have the baby1， maybe move a little faster。

So then there should be interesting。 It should look interesting。 So now。There。A little bit different。

 Okay， and baby1， I mean， baby1 didn't actually turn out to be a baby one。

 So let's make it more like a baby 1。嗯。So now it's definitely a bit small。I did not do this one。

 So we should always do。 We should always scale the right way otherwise。 Okay， so now。



![](img/190e3597363144eddd250d4ccc81286b_87.png)

Now， what do you think， And obviously， we can move them。 In fact， moving wise。

 I wanted to show you one thing。This is not gonna work scale1 it's because I have this really tiny。

I'm going to get a smaller hero marker just。 so this is mamy。 Okay， And then here I have a baby。

 and I put the baby onto this paper stick。And with this paper stick， I could just like， okay。

 I shouldn't includecc the other marker， but I now have some flexibility。With how I tell a story。

 So it's like a baby giraffe or something coming to the big giraffe and could also obviously。

Have them interact。 And tracking is still relatively robust。

 So this is something these techniques using marker based and then。

Streaming and all these kinds of things I've explored in my research project，360 proto。

And also in proto AR， And it's actually pretty， pretty cool。

You could also do something simpler like cutting out a paper shape like this。

AndBut stabilizing is a little harder。 I do like our paper stick that I showed you earlier。 Anyway。

 I thought this is cool that you see this Also， what is interesting now is I can actually also just have it move on paper。

 but be like more like a wizard of Oz approach where you can't see me。

 That's better than me always making my hand visible。 So I think this is cooler for prototyping。

 Obviously you still see the marker， but。😊，You get it。 It's pretty cool。 And then， okay。

 baby is sad and then baby。

![](img/190e3597363144eddd250d4ccc81286b_89.png)

Kind of like walks away right。That was。Those kinds of things。 I'm gonna show you one last thing。

 There is a cube。 Did I prepare a slide for this， or did I forget， Nope， there is。

 I did not have this here， but I'm gonna actually。

![](img/190e3597363144eddd250d4ccc81286b_91.png)

Add one more example that I have prepared for you， which is the。Cube， air cubes， so。

That1 I have it looks like this， I' show you here。It's a little paper based， has multiple sides。

 And so this makes tracking a little bit more robust。 And now when I bring in this cube。

 it actually can track from each of the sides。 The C is okay， now it works。

 And so now you can actually move this object。 It doesn't always work。

But you see how I can now includecc more of the marker， I mean， obviously not always。

 but it makes tracking more robust。Previously， you could always see like it stopped tracking。

As it couldn't detect things anymore， it's still not perfect。

 It's still not the quality that we have in Wolfulhoria with the unity。

 It is still pretty good for market tracking。 But now there's always a face of the cube that that I'm not occlu。

 And that can be used for market tracking。 And so I can like hold the cube。

 I can actually play with it more。And I thought that's something I wanted you to see。So AR cube iss。



![](img/190e3597363144eddd250d4ccc81286b_93.png)

Relatively cool little thing on top of Air jazzs。I think these are all my examples I have for markbase。

 they are。 A few tips at the end。 So don't include the marker。 all the Macer borders。

 smaller markers are hard to detect to detect， look probably better。 Of course。

 size of marker determines the object scale。 So I showed this multiple times throughout the throughout the view。

 one thing， if you're working in code pen or in disable auto updating。 So in here。

 you could go to settings。 And then behavior。

![](img/190e3597363144eddd250d4ccc81286b_95.png)

And then auto updating preview should be off。Otherwise every time you type it's going to reload the scene which means it's going to reload your webcam which is annoying to say the least。

 so disable that and on glitch， you just don't use the live coding thing。

 that's why I always manually refreshed here and so I think that's the best approach。😊。



![](img/190e3597363144eddd250d4ccc81286b_97.png)

Going to our AR J。 S。 What's our final AR J S example， What am I leaving here。

 this giraffe and the baby giraffe， oops。 And that is probably a good way to end the lecture。

I'm gonna to have baby giraffe and big giraffe。 I hope you remember these two。

 and obviously check out the zoo and。

![](img/190e3597363144eddd250d4ccc81286b_99.png)

You can also work with opacity settings。 Opacity on models is something that will not work initially because aframe doesn't implement it。

 but for example， if you you could see this here it actually mostly occludes the marker because I have opacity1 So for debugging。

 I would always reduce opacity。 So I see whether the marker is or like the thing that I did is I often show the detected marker in the original post。

 So I understand。 like if I didn't show this， I would probably not get why the girae looks like this rather than that I would have expected it to be。

The orientation is a bit different because of the marker。Original marker， the physical marker。

 but this is what it was detected virtually。 and then on top of this is obviously how the object is going to appear。

Use the laptop webcam to develop A GS interfaces。 And so you can work with your laptop webcam。

 You don't have to have a fancy webcam with arm like I showed here in the demo。

 and you could use your phone to show the marker。 that is interesting。 So that is true。

 maybe that's the last thing here I'm going to our scene again， here we have the giraffes。

 And now if I actually bring in a hero marker。 So let me just Google one quickly， hero marker。😊。

I don't think it's the best way to do it， but like if you show one in full screen and when I bring this one into you。

 I also have the giraffe there。So， it's like。Okay， I mean， what's the point， right？ But， I mean。

 you could use your phone to show the marker。 let's say you're doing a little workshop and you forgot。

 you forget to print something or you wna generate a new marker or something that could be a use for you to use a display。

 could be a screen could be your phone to show the marker。 One last thing， maybe。

Use browser options to change the webcam that is being used。 Yes， so that depends on the browser。

 when it accesses this the first time it asks you for permissions。 And if it's not the white webcam。

 then you should go to browser options and check it。 Good。 So hope you enjoyed this lecture。

 It was hands on。 We had a little bit of fun。 And I'm gonna just wave with my little Kenji marker here and hope to see you in the last hands on one on mark S A R。

😊。

![](img/190e3597363144eddd250d4ccc81286b_101.png)

![](img/190e3597363144eddd250d4ccc81286b_102.png)

![](img/190e3597363144eddd250d4ccc81286b_103.png)

![](img/190e3597363144eddd250d4ccc81286b_104.png)