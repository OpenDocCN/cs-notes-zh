# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p11 -11-Lecture 11 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p11-

Okay， lecture 11。11， let's see we're still doing emoji art。

 we did drag and drop last time and today we're going to do gestures。

 zooming and panning around on our document， and then we're going to add another entirely different MVVM to emoji art so emoji art is going to have two MVVMs in it and of course real appsse have many。

 many MVVM so getting to see what one at least has to in it is a step along the road there。

So let's talk about gestures and how they work， of course gestures are used to get input from the user and SwiftUI has really powerful mechanisms in it for recognizing common gestures like pinches and drags and things like that and we call all this gesture recognition multitouch because you have multiple fingers and they can be on the screen at the same time。

Sift Ui internally takes care of recognizing the gestures like oh is that a pinch or is that a drag what's going on with the fingers right there so you don't actually ever write any code that's looking at a finger and seeing something about it Swift recognizes the combination of fingers as a gesture what you have to do is write the code that handles a gesture what do I do in my app when I get a pinch or a drag or a tap or whatever and you've already actually done this with on tap gesture tap is the world's simplest gesture but now we're going to see how to handle much more powerful gestures。

To handle a gesture， you're going to start by using the view modifier called gesture on the view inside which the gesture is going to be recognized。

And this the gesture that you pass as the argument to the gesture view modifier has to be something that implements the gesture protocol and 99。

99% of the time it's going to be something that Apple has written。

 one of the gestures Apple has written drags and Pes and all that。

So to create this the gesture that you're going to pass your viewmodifier there。

 you're usually going to create a computed bar or a function that holds it。

 it could actually just be a local variable at the top of your view builder if it's a simple one but usually we put it like this in a computed bar and the computer bar return value is going to be some gesture because then inside we can put a gesture and we're going to modify our gestures so creating a gesture feels a little bit like creating a view if there's not really a gesture builder or anything like that。

 but it is similar in that we have a gesture like in this case a tap gesture and then we're going to send functions to it that modify it and most of the modifications we make are how to handle the gesture this is a simple tap gesture。

 it's a double tap actually because it's got a count of two there。

How do we do something to recognize a gesture we've attached it to a view the Swif U eye has realized that inside that view a pinch is happening or a tap is happening or whatever。

 and so how do we recognize it Well it depends a little bit first on whether it's a discrete gesture like a tap where it just the tap happens and that's it there's no other thing going on or whether it's non-discrete like a drag or a pinch where it's happening over time。

So the discrete gesture tap gesture is really the discrete gesture， long press。

 I think can also be treated as a discrete gesture or a long pressed on something let go that it happened and to do something in a discrete gesture all we do is。

Do this gesture modifier if you want to call it that dysfunction dot onend， and we give it a closure。

 we just attach it to the end of our gesture there and that closure can do whatever we want。

That's how we handle。Discrete gestures could not be any easier。 And， of course。

 it's so easy see that we usually use these built in things on tap gesture or on long press gesture。

 which you haven't seen， but you can imagine exists that just passes that closure onto it。

 This is So those things on tap gesture is doing。 literally what it shows are in the green。

 It's creating a tap gesture。A dot on ended and passing the closure in there。

So the meat to this though is non discrete gestures。

 that's what we really have to understand the mechanism for。In these cases。

 you're not just handling the fact that a pinch happened or a drag happened。

 you want to be doing something to give user feedback while it's happening。

That's what the infrastructure here is all about， typical non-discrete gestures， drag magnification。

 there's a rotation gesture which is put two fingers down on your screen and turn it like a knob and these things are all handled this exact same way。

 so let's talk about how that works。Here's a non discretereet gesture drag。 And， of course。

 you can still have dot on ended。 and you almost certainly would have dot on ended。

 But there's a little difference。 The dot on ended of a drag gesture。 that little pink value。

 You see the value there。 So that value is telling you the state of the drag when it ended。

And that depends that value depends on what kind of digest it is for a drag。

 It's actually a fairly complicated value。 It's a struct that has things in there like where the drag started。

 how far the drag went even kind of wacky things of if the user was swiping where the drag would have ended if it had continued to fly at the rate that it was going across the screen so drag gestures have a very complicated value magnification gesture。

 which is what you think of as a pinch super simple value it's just the scale for the finger start here and they move twice as far apart it's just the number two if they start here and move halfway together it's 0。

5 so it's just telling you the scale that is the entirety of the value it's a Cg flowed for a magnification gesture and for rotation gesture。

 it's an angle right and we saw that type angle that we used in our pi it's just going to report to you the angle of the rotation。

On endeded happens， the drag happened， the pinch happened， whatever， and it ends。

 the ending means the fingers left the screen， they got lifted off the screen and you get told via un endeded。

 here's what the state of the world was when it ended。

But what about during the gesture fingers are moving on the screen at that time。

 you get to a chance to update some state and the state is stored in a special at sign var。

 It's called an at sign gesture state。 Now this is different than at sign state。

Atine gesture state still like atine state， and then it can be any value type you want can inter float or astruct your own struct。

 your own enum， whatever you want。 In fact， oftentimes the gesture state is an enum because as a gesture happens on screen。

 you're going to through some sort of state machine。

 Maybe it's dragging in and out of other areas on the screen and some enum is changing its state from I'm inside to now I'm outside or whatever it can be anything you want。

 but this gesture state is kind of interesting because you can only update it while the gesture is happening。

When the gesture is not happening， it goes back to its starting value。

 so you see how I've said outside gesture stay， my gesture state equals starting value。

 it will always be at that starting value unless the gesture is in flight actually happening it's the only time that you can modify this thing and again you can set it to anything you want based on what's happening during the gesture。

So how do we update this thing in the middle of the gesture。

 We know that we can update on dot on ended， what about in the middle Now we're doing that with another modifier called dot updating。

So dot updating and we're going to talk about all the arguments to it here and's I apologize in advance for this because。

These arguments are using some technologies I haven't talked to you about so for now I'm just going to say just do what I say and don't worry about why and then later when we cover some of this up we'll be able to look back and say oh that's why that was like that but I can't really tell you right now so just take it on faith but anyway you have this updating and you can see that updating argument there is the gesture state right has a dollar sign in front but it says my gesture state and then inside that closure you get to update your gesture state and that's the only time you can update your gesture state。

It's during this updating thing， no other time like you can't do it in in your on a appear or any other coat only in here。

 so this gesture state literally is the state during the gesture flight and only then and when all this gesture ends it's going to go back to its starting value。

Now let's talk a little about these funky arguments here。The dollar sign。

 you see the dollar sign in front of my gesture state。 again。

 not going to talk about that till next week， but just always put it there。 dollar sign。

 the name of your outside sign gesture state bar。 The value， of course。

 is the same value that's in on ended， except its the value at that point in the gesture as you're dragging across the screen。

 the value is constantly updating and this updating closure that you provide here。

That has with the value it's going to get called every time the fingers move or like in a long press。

 it actually gets called every once in a while over time， but as the gesture is happening。

 basically this value is being updated and your closure keeps getting called over and over Now the second variable very strangely is your gesture state again。

Again， I'm not going to explain why that there again it's like like that need to be there twice。

 but it just does you're always going to have dollar sign you're just your state variable as the argument and then in your closure。

 it's essentially passed back to you。Inside that so you can modify it inside the closure it's weird it's weird we'll see why later and then the third argument there transaction that has to do with animation and we're not going to talk about the transaction but when you're doing just your handling you might want to know what's happening in terms of my animation state what's my animation curve and things like that and the transaction can give you that information buts that's really advanced animation and gesture so we're not going to talk about that at all。

So this is how you do updating and the two takeaways here to really understand。

 one is that inside that updating， you're not updating your model or any of your at sign state。

 you're updating your gesture state， only your gesture state and the second thing is you can only modify your gesture state in here so it works cuts both ways。

Now you might say， why do we make this huge separation like this and I'll be able to show you in the demo what would happen if we didn't have separate state。

 it definitely won't work， but there is a way to do all this without using this separate state and that's unchanged。

Just like you had updating you can instead you can do on change now on change gets past the value。

 but none of that other the stuff and there's no dollar sign gesture tape because in on change you can actually modify your model or at sign state。

This really only makes sense if your model right or your outside state of your view is directly tied to where the finger is like you're doing a drawing app。

 you see and as you drag your finger around， the drawing is following。Or you're doing drag to select。

 And as you drag out the rectangle， you're selecting or deselecting things under it。

 that depends on where the finger is。 If you're doing something like we're doing with zoom pinching to zoom or panning around。

 Those things are really relative to where it started。 when I start to pan on my emoji art document。

 I want to move as far as my finger has moved since I started In other relative。

 I don't want it to move under the finger somehow， it's just moving relative。

 same thing with the zoom。 If I pinch down half， it should be half as big as it was when it started。

It's surprisingly on change， you don't use it that much。

 you would have to have some situation where you wanted to change your model or your at state variables as the thing is happening。

 which is pretty rare。Here's a summary of how to think about handling these non-discrete gestures。

 Now that you've seen all that。 The first thing is you're going to collect all the information that you need to draw differently while the gesture is in motion into an outside gesture state。

 That's what is for right things that you need to know that are changing while the gestures happening that gets put into your gesture date。

 sometimes it's the same thing as the value you're getting back like the pinch you just need to know the amount of the pinch that's fine。

 but you're going to collect it all into a gesture state。

 then you're going to add that dot updating on there。

 and the system is going to be giving you this value over and over to tell you the state of it and you're going to use that information to update your gesture state。

You are going to understand that when the gesture is over。

 the gesture state will reset back their gesture tape really should be at some well known reset position all the time except for when you're actually in the gesture。

Now you update your gesture states。While the fingers are down and moving only。

 you never update your gesture set again in on appear or anywhere else。And your model and your state。

Is permanently updated in on ended。 That's what you do in on endeded update your model or your assign state。

One way to think about this is sometimes clears it up for people is updating is for the outside gesture state onended is for the model in outside states。

Now your views of course are drawing themselves， they have all kinds of view modifiers。

 opacity and all these things， well the arguments to them are using both the gesture state and the model and your outside state。

 all of those things to make those decisions。Maybe while it's in a middle of a gesture。

 it needs to be amplifying the zoom because we're zooming in right and so it's doing that or it needs to add a little extra pan movement during the gesture so you're using both the gesture state bar and among the state throughout your entire view wherever appropriate and you know that your gesture state keeps resetting back to this known value when you're not in flight。

We'll see that in the demo in fact all of this is best understood when you see it。

 so let's go add zooming and panning to our emoji art document and I'm not going to get back to the slides so let me just look ahead a little bit after we do the multi VVMs today next week we're going to talk a little about colors and images and navigation。

 sheets， popover forms， something called at sign binding which is a really important part here and then probably alert and error handling which I originally was thinking I would talk about next week I should put that off to the week after。

Alright， so we want to be able to pinch to zoom in and pan with our finger to move around in our document sort of like this good one over here。

s here's emojiR this a little down the road version of it， but I'm going to pinch by the way。

 when you're using the simulator like this you can pinch by holding down the option key and you see I get two fingers right there option option option and then you can drag。



![](img/6c7fbf660e27175a85d7c5afd2a9c4d7_1.png)

So here I'm zooming， see how I'm pinching to zoom。 and of course， as I zoom out。

 I might then want to move it over so I'm dragging。



![](img/6c7fbf660e27175a85d7c5afd2a9c4d7_3.png)

So dragging and pinching， that's what we're going to be implementing those two things。Now。What gets？

Dragged around and zoomed in on well， it's the contents of our document。

 so that's the background and all the emojis。All of that stuff all gets zoomed。

 That's what you see in blue here。 I'm going to take this stuff and put it in its own v。

 This is going to be the bar of my document contents。

 and that's the thing I'm going to zoom and pan around on。 So I'm just going to cut it out of here。

Put it down here in a private funk document contents I'm going to call it and it's a funk because I need my geometry in here I need my geometry kind of everywhere in this stuff because my view coordinate transform between the emoji art and my view always requires the geometry I just have to know my coordinate system there。

And then I'm just going to paste this in here and this is going to get an error and I want to see if anybody can tell me what the problem here is。

 it says here function declares an opaque return type that has no defined value。

 why would it be saying that？This returns some view。

 how does some view know which view it is it looks inside here right inside this cur brace。

 what does it see in here？Two views， a think image for each， that's not valid written thing。

 that's two views， not one。Is it easily fixed？At sign viewBuilder。

Tur this little function into an at a time view builder function。

 all of a sudden it returns one view， which is the combination。

 it's a twople view of those two views。Right now that I have this document content。

 so I can put it up here。Document。Content in my geometry noticeice I didn't put my white background in there because I don't want my white background to get zoomed in on it's the background upon which my document lives right so if my document is small。

 I see the white background so I don't want that。So I my document contents here now I'm going to zoom and pan around on them first let's create some at sign state。

 but down here I think now open here。At Sign State private var zoom which is a CG Fat。

 which is how much I'm zoomed in on and let's have it start one。

 so I'm zoomed in one it's not twice the size and not half the size it's the size I'm not going to have another one here at sign state private var called this My pan and it's going to be a CG size。

 zero and when we talk about offsets in SwiftUI， we use CG sizes。Which。

It's fine because do you really want to have another type in addition to CG size because it's the same as CG size and that it has an X offset and no Y offset。

 but you could imagine having a type CG offset that instead of having width and height as it's two things in thestruct。

 it's like DX and DY or something like that。Now I like to remind myself when I'm using a CG size as a CG offset by calling it CG offset and then over in my extensions here。

I put a low type A is to says CG offset equals CG size。It's just to remind me， oh yeah that's right。

 this is a CG size， but really I'm using it as an offset。So here's my zoom in pan。

 how do I use my zoom in pan to make my document contents be zoomed in pan well this is incredibly easy。

 I'm just going to have a scale effect which is my zoom and I'm going to use something we already know offset to do my pan。

And that is all I need to do to make zooming and panning working。

 So scale effect is a view modifier that just takes whatever view you。

Put it on and it scales it by that much， so I'm scaling it by one in this case so far。

 but as we change it， it's going to scale up and down and same thing offset。

 offsets it from where it normally should be。That's what we've already seen offset before。

So let's see if this works， let's change our zm， how about let's make our Zoom be 0。

5 and just run this。And see if it makes it 0。5 It did we can already tell it did doesn't fill the screen it shunk in 0。

5。 We don't even need to go any farther。 We know that that's what happening。 How about the offset。

 Let's make our offset be C G offset with。100 height， 100。This a CG offset notice it's a type area。

 so it works just as well to say CG offset there， I could also say dot in knit。

Because I did explicitly type this so we can infer that the init to call there is CG offset to knit。

 which is CG size because of our typepaliaius。See if that works。Yeah。offset 100， 100。

 and remember 100 is down， it went over 100 and then down 100 because this is all happening in our iOS upside down system。

So it's definitely working， this is great， I already have a mechanism。😊，To do this。

Now I just somehow need to add gestures that change this zoom and pan。Let's start with Zoom。

 Zoom is probably the easier of the two。 and I told you that if I wanted to make something have a gesture recognized on it。

 I just say gesture。AZoom gesture here。I'm going to go down here。A private bar zoom gesture。

 which is some gesture。 and I'm going to return what gesture in here， and in this case。

 it's going to be a magnification gesture。 So a magnification gesture is that pinching thing。

This dot gesture here knows I put it on the Z stack。 So it's going to be recognized anywhere。

 Even outside of my zoom in document， on the white background， whatever。

 the whole Z stack is going to recognize that this pinch is happening here。

 And it's important to think about where do you want the thing to be recognized， for example。

 in your homework， you're going to add a drag gesture。 lets you drag individual emojis。 Well。

 you want that to be attached to the individual emojis， not to the background。That digester。

 it matters where you put it， you're saying essentially the rectangle in which that gesture assistant is going to recognize。

 oh， there was a pinch there。Now， in your homework。

 you're not going to put the pinch on the little remote because you don't want tiny little pinch to have to resize it。

 so you're going to use the pinch you're using on the background and just have it resize all the things in your selection。

So this zoom gesture down here， let's start by just putting the dot onend here。

 So we're going to do the dot ended and it has this thing value in。 and we can do whatever we want。

 And this is going to be when the pinch stops moving and they lift the fingers there。

 We can go take a look。 I'm just gonna to click on this option click and see the value。

 its type is magnification gesture dot value。 This is a type it's nested inside magnification gesture。

 So let's click on it and look at it and it's just type alias to be a Cg floatlo because that's the only value we have with pinch。

Super simple Now when we do this for drag， you're going to see this is going to be astruct here。

All right， what are we doing in on endeded So we pinched this thing and you know maybe the pinch got twice as big or half as big or whatever。

 we're just going change our zoom by that much We already have this zoom so let's just say zoom times equals that value。

And if this makes it so you understand it any better， I'm not sure it does。

 but instead of calling this value maybe we would call it ending pinch scale or something like that because that's what this is。

 this is just the ending pinch scale the pinch scale we had at the end and that's all we need to do to make this recognize it and pinch it so let's go back over here I'm going to hold down this option thing so I get two fingers and then I'm going to drag。

It worked。😮，But of course， we're not seeing anything while it's dragging， I drag around and then。

 whoop， when I let go。It works， so here I'm going to pinch out。Pinch in。

So see how on ended we've updated our permanent state， which in this case is our at sign state。

 by the way， why is our zoom in an at sign state instead of like being in our model or something well because zooming and panning in on the document is not part of an emoji document it's how we're viewing it so it's part of the view but it's only temporary it's only while we're viewing it to zooming it around so that's perfect to be at sign state。

So we're almost there， we've got this thing so that it is nicely pinching and the on endeded now comes the little bit trickier part。

 I want to update this thing while I'm pinching， I wanted to zoom while I'm pinching。

We can do this dot updating things。So we go down here and say@ sign gesture state private bar。

 I'm going to call this my gesture zoom， this is the zoom that's happeningping why I'm gesturing and it's a CG floatloat and I'll have to be one by default and that's what the value is going to go back to every time。

So now that I have this gesture state， let's put it in here， gesture zoom。

 and then I have to do this wacky thing where I have the value。 That's the pinch scale。

 and I type my gesture zoom again， and then I have this transaction and we're not going to use the transaction because we're not doing the animation thing I'm just going to underbar that out of there。

 Remember underbar and Swift means I don't really care about this。You might think。

 can I just say the same exact thing here， Zoom。Here。All right， and just use this value here。

 we'll call this the in motion。Pinch scale。 Can I just use my in motion pinch scale here when I'm zooming。

Forget that gesture Zoom thing， why do I even need that gesture state。

 let's see what happens if we do that。It seems here like only the unended is working。

 Why is this only working on unended。Well if we go back and look at our code we'll see that we have a purple error and purple error is a runtime error and Xcode is just showing you the line of code that caused this runtime error so what is this thing modifying state during update causes undefined dis behavior inside this update you can't modify your outside sign state or your model or you'll get this purple thing right here。

 the whole system is designed to only have gesture state be modified in here。All。

 so I switch that there to make it so that。Only gesture state is modified in here。

 but I only have to use this gesture state in the normal operation of my view somewhere in the obvious places right here。

 this is my gesture。Zoom。So as I'm zooming， my scale effect is not just the zoom that it normally has when I'm not gesturing。

 it's that times whatever the gesture is。And I'm not saying zoom equals zoom times this。

 I'm just saying the scale is zoom times that， so I'm not getting the exponential effect here。

That's it so I've used both the gesture zoom and my normal steady state zoom if you want to think of it that way together now when I'm not zooming。

 what's the value of this going to be one so this is going to multiply my zoom times1 which is exactly what I want when I'm not gesturing I want to just use my normal zoom。

So let's see this， make sure we don't get any purple。And that this works。 All right， here we go。

 And now I'm going to do tiny little。Movements， you see。

 I'm doing tiny movements and it's moving tiny。 And if I move big movements， big movements。

 so it's tracking。How big my movements are。The simplest possible case is zooming because we have such a simple value here。

 which is just the amount of the pinch， but we're going to do drag also。

 it's a little more complicated because it' got that struck。But similar kind of mechanism。

Just create a new gesture。 We got our zoom gesture here。

 I'm going to create another one called a pan gesture， private var pan gesture， some。Gesture。

And this one is a drag gesture。So drag gesture。Just means anytime you're dragging your finger across the screen。

 we're using it for panning， that's why we call it a pan gesture， but it's a drag gesture。

 and we want both this zoom gesture and the pan gesture to be recognized。

Now it is possible to just go like this gesture。Here and pan gesture here。

You want to be a little careful doing this。 Some gestures will consume the finger movements before you can get to the other one。

 In fact， this order would probably be bad if you did this。

 your pan gestures probably would not work because the zoom gesture would be you'd put one finger down you start moving and the zoom gesture is where's that second finger I need that second finger and it's not coming down so it's not recognizing it。

But there's a way to deal with this， which is much better。

 which is we'll say pan gesture dot simultaneously with zoom gesture。

This tells the system that I want both of these gestures to be recognized at the same time again we're talking about recognition here。

 just recognizing that they exist。 you still only one of them is going to actually get handled and in this case I think what would happen is you start panning it's gonna to immediately start thinking you're panning if you start zooming it's going to start saying oh now you're zooing and it's gonna to switch over to the zooming I think that's how it would do it I'm not 100% here but at least here you're telling it inside my rectangle recognize both of these the same time there's other kind of arrangements you can have here like you can have recognize this gesture before this one so for example。

 long press and drag you can say recognize a long press first then drag don't do the drag unless I get that long press first in addition to simultaneously with there's some other ones you can go looking in gesture to see what they are。

But we now were recognizing these things let's make it so the pan gesture actually does what a pan gesture does again。

 we'll start with the on ended because that's where we have to update our。

Model or outside state let's go take a look at this type the drag gestures value in the documentation and I told you it was astruct and here it is look at all the things that are in here location that's the location of the finger there's a predicted end translation and end location that's where I was telling you about the keeping in mind the velocity of the finger time will tell you actually the date stamp in nanoseconds of when this particular value was taken as the finger moves across the screen and then one we're interested in is this one translation that's how far the finger has moved since it starteds it's offset basically since it started that's the one that we want。

Let's go back in here， our ended value is just saying our pan plus equals the values。Translation。

Now it's an interesting line of code makes sense， right， because translation。

 that's a CG size CG offset in our world and we're plus equaling。

 but you can't actually plus equal CG sizes Cg sizes have a width and height in them。

Youd think you could say plus equals， but you can't so I added that plus equals the recent it works in my extensions。

 and so I'm going to show you and I did it because I wanted to show you what it looks like。

An operator like that plus equals is an operator。 How do you do it。

 You're going to kind of recognize this similar to what we did with the equtable protocol。

 and we overrode equals equals， right that static funk。 So here it is plus equals。Inside CG offset。

 which is CG size， and it's a static funk just like equals equals was a static funk because of course I can take any two CG sizes and do this and it's got a lefthand side and a right hand side and it adds them and it's got this in out we haven't talked about in out。

 you probably read about it in your reading this means that this parameter gets copied back out。

When this function ends， that parameter， LHS。Get copied back out。

And I specifically say it that way because that's the way it is it gets copied in at the start and then you do whatever you do and then it gets copied out at the end and that's what I want here because when I'm doing plus equals I'm changing the value in place right whatever the lefthand side is of the plus equals thing I want it to get the new value。

I overrode this operator2 plus so that I could add two CG offsets together。

So this is actually an overridden one or not overridden。

 but really invented for CG sizes on left and right， and it's using another one。Let's go， and。Run。

I'll zoom first， and I'm going to pan， I'm dragging around， dragging， dragging， and I let go。

 and it worked unended。But we need to work while it's happening， exact same thing as we did before。

 so we're going to have to have some gesture state。Private var， gesture pan。

 and I'm going to have this be a CG offset。It could be。

 I could have that be destruct that has all the information in there， but I don't need it all。

 I just really need that translation， so that's the only piece I'm going to do and I told you that these gesture tapes can be anything you want。

Then down here I'm going to say dot updating and I to put a dollar sign in front of my gesture pan and then the arguments are the value and then once again gesture pan and we don't want to translation forget that go inside here I can only update my gesture state I can't update my model or my outside state I'll get that purple warning so let's do that gesture pan and my gesture pan equals this values translation getting bad out of the struct。

So let's go up here and in our offset， we're going to have our pan plus our gesture。

And and's this plus is going to work also because of my extension。

 I can just add these CG offsets together。Here we go， zoom in， pan around。

 let's make sure it's actually working with a background。Is your background？

It's really valuable now that we have the zooming and pan for this kind of background。😊。

A kind of weird size background， yeah。All right so that's pretty good。

 but this is actually going to cause a major problem it's really nice。

 but watch this so let's put this here and now I want to put how about a airplane in the sky here we go airplane up here in the sky who。

ButThere ares down here。no。AndHow about a rocket over here？

Why does that right Why is it anything way down there Well because when we drop our emojis when we do our translation from one coordinate system to the other。

 we don't take into effect that we might be zoomed and panned we're going to have to put a little math in to make it so that we adjust for thatLuckiily I knew this was going to happen so I put the conversion from one coordinate system to another in this nice emoji position you remember this function that we wrote so we just need to tinker with this a little bit to get this to work。

It's actually quite easy because what's going on is here is our center keeps getting moved when we pan and then the distance we are from the middle keeps getting zoomed out。

 so we need to dezooom it。we're just going to say center dot x right here minus our pan width。

 that's the offset or our pan width here and same thing here our center dot y minus our pan height that we're going to take this value that we just calculated。

 then we got to deZoom it， we're going to take it and just divide it by the zoom same thing here。

Dubide this by the zoom。And what do we got here， cannot， oh。

 we got to put this inside this ink conversion here。

You can convince yourself later that that's right， and we'll also convince ourselves by going and running。

 see if it works。Here we go。 just for fun。 Let's go ahead and bring back our。Background。

 a little different background this time。And we'll zoom in， we' like zoom my in and again。

 let's do the airplane trick， the airplane up in the sky。But no， still doesn't seem like it worked。

Well， actually it kind of did。 There's the airplane it's a very small airplane up there。

 but it's in the right place。 it dropped it where I dropped it， but the size is wrong。 Well。

 we also need to do adjustment on the size we make the thing in there based on the zoom when we're dropping into a highly zoom thing we need to make the thing much bigger so that it matches that zoom。

 that's easy too that's right here where we're adding emoji instead of using the palette emoji size we'll also divide this by the zoom。

Let'stra that。Zoom in here。And we'll get a rocket this time。P。That's the right size。

Co now when you add your gestures， you're going be able to resize the emojis this is really not that big a deal but it's kind of nice right now to be able to control the size of ourojis relatively by zooming and pan on the background So hopefully now you know enough to make it happen I'll just tell you that your homework is mostly about figuring out where to put your gesture variables and your model in your state in all your view view modifiers right you have all the view modifiers and you're trying to figure out which ones go where and there's a little bit in your homework to about you have to manage selection。

I got to be able to select the bike so that I can zoom in on it and move it。And minor。

We're going to go on now to the second topic， which is second MVVM。

 anyone have any questions about Je before we do that？All right。

What is the second M V VM we're going to do， Well， I actually going to show you over here。

 way over here。 Here's a version of emoji art。 we're going to build。

 And you can see down here at the bottom。 And I'm actually to move it out of the way。

 Look at my emoji list right here， it actually has a little name now， sports。

 These are my sports emojis and look at this little palette。 If I tap it。 Oh， I get to the other。



![](img/6c7fbf660e27175a85d7c5afd2a9c4d7_5.png)

Palets， so I'm going to have multiple pallets with different kinds of emojis in there when I tap on that little thing it's going to cycle through them。

 not only that， if I press and hold on it， then I can add a new one in this case I added math and click around and if I don't like animals then I can delete the animals out of there and now they're not even in the list。

So this is what we're going to build and this whole world here is going to be its own MVM。

let's start with the model of this what is the model of that and the core of the model of that is one palette。

 one named set of emojis， that is the core and I'm going to call thatstruct a palette because it's like an artist's palette right we're doing emoji art but instead of paint we have emojis so let's go create。



![](img/6c7fbf660e27175a85d7c5afd2a9c4d7_7.png)

In our model。A palette。Allette I'm going to call it， make sure I put it in the right places。

 and we go create， there it is， and we'll put these down towards the bottom。Here's our model。

Of course it is a model so it's not in the UI it's not going to import swiftif UI it's a simple struct called palette and what's in there Well each one of those little things had a name like vehicles or math or something like that so we're going to have to have var name string and what else did it had well it had a bunch of emojis we'll go ahead and。

Store all those emojis as a string， we already know we have that scrolling thing that takes a string of emojis and scrolls on it for us。

 so we're going to reuse that。And now we know that that those pallets are going to be in the UI they need to be identifiable。

 we all know by now when we're cycling through things， they need to be identifiable。

 so let's just make this thing identifiable right off the bat here， con identifiable。

And a good question here is what mean bar， what should its ID be？

And we've seen different strategies for doing the ID in set， I had the ID of a set card B。

 all the symbols and colors on the card。Because that uniquely identified the card really well and memorized we put a little string right that would semantically you know pair 1 A and 1 B。

 some of you in your set you just put one through 81 a number on there an inteature or whatever that's what we do in emoji art for toojis。

 we just have it inteature and we just keep incrementing it every time we add one。

What I'm going to use here is an interesting one， which is I'm going to set it equal to a UU ID。

UUID is a littlestruct that generates a unique ID It's you know， big， I don't know。

16 bytes or something of just randomly generating randomly but uniquely generated stuff and when do you use a UUI as your identifiable ID Well when you have a fairly small number of things like it would make no sense in emoji art to do that。

 we could have an emoji art hundreds or thousands of it。

 and then we could have hundreds of documents with millions that we wouldn't want to be generating these unique Is for all that it makes no sense plus you can easily do something else anytime you can do something sensible。

 you probably should instead of using UUID but in this case I actually think it make sense we have a fairly small number of palettes。

 maybe it's gonna to be what 15 or 20 over a life maybe 50 maybe so it's a small number why not use this UUID thing here it's also really easy just ID equal UUID。

And U ID is hashable and so it can be an identifiable ID all that business。

Now I have some built in palettes here。Those ones that we saw in the demo。

 so I have a static called built ins and it's just an array of pallets。 prettyty cool。

 there nothing special going on there。So that really is our model， a palette is a model。

 now we're going to have an array of these things being our model。

 but this is the fundamental unit of our model。So now let's do our view model here， file new file。

So file。I'm going to call my view model my palette。Store。You'll often see view models called stores。

When do I use the word store in the name of my view model。

 well when my view model store something and in this case。

 my view model for those little things in the bottom is going to store all those palettes。

That's going to be its primary function And we're also going to make this persist because one thing that's really annoying about our program right now is we create a beautiful emoji art and then we go back and fix a bug and we come back it's all gone there's no persistence。

 Well Sam is true with our palettes。 We're going to be able to edit pallets add new palletettes and then we run again and they're all gone again So we're going to make a persistence and that persistence is going to live in our view model in our palette store。

're not going put that in our view somewhere。 That's a great thing。

 our view model can do is provide persistence。 in fact。

 our view model for our emoji art document and for this we'll both provide this persistence for each of their views。

😊，So here's our pallet store。That's a good place for right down there。

It's in the UI because it is a view model it's a class， we know that called pallet store。

 of course it's an observable object， we know that all by now and we're going to say it's got one published bar。

 which is the pallets。Which is an array of palate。That is our model for this view model is an array of pallets there。

Now of course， it's complaining you didn't initialize your pals， so let's go ahead and do that。In it。

 I'm actually going to have my palette be named，I'm going to have my main palette。

 maybe a palette for my previews， possibly I could even have name palette where I'm using different palettes for different kind of emojiR projects or whatever。

 so I'm going to have it have a name it's not super important that it's named but I'm going to have it have a name so let's go up here let name。

String， and this so' will have the init be inniname this name。

Then we can say self do name equals that name， and then the palletettes。

 what are the palettes going to be equal to well， I'm going can start by having them the built ins。

Right， so that'll be our palette and since we don't have any persistence。

 it's just always going to be those and yeah， we're going to learn how to delete them and bring them back and all that stuff。

 but it's just going to always reset every time we create a store for now until we put persistence in there。

Now here's a really interesting thing that I've done。

I did not put private on that app sign published。I've spent this whole quarter talking about and I think you've even asked her earlier like why are you putting that private in there。

 why are you protecting， always protecting your model and I think。

 well you don't always do that and I'm not going to do it here just to show you what it looks like not to do it to have your view model offer the model up to the view directly so my view is going to be able to do anything at once to that array of powers delete things from it。

 add things to it， change things about it because completely free re in there。Now， that。

Is you might say， why do I even need a view model if I'm going to do that。

 if I'm going to open up the model to just do whatever you want。😡，The view model can still provide。

Help to the view。 for example， I'm going to have my view model enforce that there's always at least one palette。

Because you can imagine if you're writing your UI code if you have to deal with the case where you delete the last palette and now that's an empty view there。

 that might be some tricky code or some and if then you have to put in there that you don't want to put in there and it also makes no sense you can't even do emoji art with no palettes so I'm going to make it so that my view model says you can never have no palette in here so Mr。

 View don't worry about that。Now I'm going to do that。 Well。

 one thing I'm going to have to do is right here in the in。

 I'm going to make sure that it starts out with at least one palette。

 So I'm going to say if the palette。Is empty in other words my built and isn't given me any then I'm going to set my pals equal to an array that has at least one pallet in it and let's just make something up maybe warning。

And the emojis， let's put a little warning emoji in there that'll be good if I ever see this in my UI I'll know that's strange。

There's a warning guy。And my users are reporting， hey hello。

 I'm trying to do some Moji art and I'm getting a little warning thing and all my pals are gone then at least you'll know oh whoops that hit that line of code which you should never do because my built ins should have kicked in there。

But now I'm still possible to get to zero pallets。 if the UI deletes the last one。

 I've given it three re， how am I going to stop it from doing that。

 let me you do some really kind of freaky here， which is in my did set for pallets。

 I'm going to say if the pallets are now empty。And the old value of the pallets was not empty。

 then I'm going to set my pals to the old value。That way I can't delete the last one because it's always going to keep reverting back now in you're setting your own vars value in its did set。

 you want to be careful here easy to make an infinite loop here now I'm not going to have an infinite loop because I check to make sure my old value is not empty before I try to do this but if I didn't check it could just sit there looping forever saying it to an old value and they're both empty。

So this is a little bit trickery， but for a demo it's nice it's really easy to enforce this。Now。

 another thing that my view model can do for the view is keep track of the fact that there's only one palette showing at any one time。

 right I cycle through them。 there's only one， so maybe the view model could provide a nice little。

Published v here。Called cursor index or something like that。

Wwhichch will be an int that keeps track of that cursor and why is that a help to the view because I'm going to make sure this is never out of bounds。

Then then my view will never have to worry about a array index out of bounds So I'm going to make cursor index there that publish bar never be out of bounds。

 The first thing I need is a little private function。I'm going to call it bounds， checked palate。

Index。It takes an index and it returns a bounds checked version of that。How do we do that man really。

 easy see， I'm just going to say let's get the index modo the。

Count so that makes sure that the index is in the counts space， but the index could be negative。

 so better check for that too， if the index is less than zero then I'm going to say index plus equals the pallets count。

Then I'm going to return the index。So now I have a nice little function here that bounds checks the index。

 any index into the palette to make sure that it's there and it's always going to work because we always have at least one pallet so worst this would come back zero Everyone agreed with that。

All right， now how do I make this cursor index then be this protected thing I'm going to make this be private and be an underbar and I'm going to have a public var called cursor index。

 which is an int。Whose get value is to get the bounces checked？Version of the underbar， private one。

And for the setting， when you set the cursor index。

 I could just actually say under our cursor index equals the new value that's perfectly fine because anytime To gets it。

 it's going to get bounces checked， but why not let's go ahead and bounce check it on the way into Bos checked pald index。

The new value。That way， if I ever look at the inside of my code。

 it's not going to be some huge number or something I that be somewhere in the vicinity。

So you can see my view model is still helping my view， even though it's given full access to it。

And there's some other things you can do too， like I'm going to put these。

 I'm not going to type them all in， but here are some functions insert。

And append to add a pallet to the pallet's array， which the view could just do it directly。

 but if he uses these， then I'll make sure there's never two of them with the same identifiable。

Because I don't ever want that， so if you say insert one and there's one with the identifiable there。

 just replace it in place。And if you say aend to it and it's already in there。

 then it won't duplicate。So seeing my view model can help。

 even if it allows full access to the model， there' are still things it can do。

So let's go on to our view now that we have this nice powerful helpful view model and build that so let's go here a new file。

 this is a view， this is going to be the view that represents the whole thing on the bottom with the button and the palettes。

I'm going to call it。Caalate chooser。That's what it does， lets me choose the palette that I want。

Here's our palette chooser， I'm going to put this a little higher up near the document view。

 just for fun。So what does our pallet chooser look like。

 I'm going again start with a little bit of like pseudo code and then we'll flesh it out。

 This is kind of a good way to program to it。 if you can tolerate all the red errors happening while you do it。

 which can be distracting， it's still kind of a good way to do it。

 So I know that my pallet chooser on the bottom， it's an H stack of that button and then like a view that draws each of the palette。

 The thing that's rotating。 So let's do that H stack。Like that chooser button。 I'll call it chooser。

 It's in my chooser button。 And then there's a view。For。What for our store。

 assuming we have a variable store or something， the pallet。

 so I want to get those pallets and what index do I want， I want that cursor index。

How about this line of code？Lot of errors， but you get pseudocode what I'm talking about here it's like I want to have a pallet store that's going be my view model I'm going to go look directly at the model and the index I'm going to get is that cursor index that the store is managing for me and since I know it can never be out of bounds。

And I know this can never return。Empty view this is make my code real easy like this。

 And so now I do need to obviously have these two things a var called chooser which is some view and that's just going to be a button that button that chooses it and will have its label。

B。An image， just an image。And I think paint palette is the one I was using there。

 paint palette is the name of the system image that does that。

 and then I had a funk view for palette。That's just a palette or some sort， and that's some to you。

So I have to have some view down here for that and that I can even stub out too。

 that's an H stack as well with the palette's name。And。Actually， a scrolling emojis view。

 Remember that scrolling emojis view that we had originally。

 where the emojis are the pallet's emojis。😊，So that's not even a stubout， actually。

 I think that will just work as tights。That's pretty easy。 Let's go back up here and fix some things。

 your button with only two Ts and C3。This is all working problem is our store Well。

 our store is our view model， we know how to do that right at sign of observed object。Our store。

 which is a pallet store。All right， we have no compile errors so hopefully we have a working palette userr here and where are we going to use this Well it's going to replace that scrolling emojis that we have back in our emoji art document view。

So I'm literally going to put it right in place here。

 I'm just going to say palette chooser instead of the scrolling emojis。

 I'm going to keep all the other things， the font size， the padding， hiding the scrolling indicators。

 I don't need my emojis up here。But this is where you can start to see the problem， look。

 missing argument for parameter store。Who makes this store。I it。

Date object here for sure not because this is an emoji art document view and imagine we're in the multi documentcument situation on our Mac we want the pallet to be the same on all the windows so definitely the pallet store cannot be owned by the individual document views it has to be up at the very top shared out through our entire app so we really want to put it up here。

In our emojiR app as an at state object。I'll call this my pallet store because this is going to be the pallet store for my entire app。

And we'll call it name。Main， this is in our main program。 This is our main pallet store。 Now。

 I want to pass this pallet store to my pallet chooser。 So am I going to pass it to this guy first。

 and then he passes it along。That's pretty annoying。

To have to pass it through like that plus my P door is used everywhere in my app all you see what I mean all my documents are all using this pallet store。

 same pallet store so that if I were to add a pallet down in this window。

 it would show up in the other window and I could start using it there。

So how do I pass it in here Well now we're going to learn another at sign thing to pass。

Essentially state objects。Deep into hierarchies。We're basically going to inject it right into the entire thing。

We do that by saying dot environmentron object， my pallet store。

Doing this says there is this object power store and it is injected to all views if any view wants to use this all they have to do is go like this in my palette chooser here instead of saying observed object and have it passed to me instead I'm going to say environment object by the way。

 not environment that's a different thing where I'll learn about next week， it's environment object。

So environment objects says get a thing of type palor that was injected into me。

Now notice that I can only have one pallet store be injected in because there's no way to say which one right。

 so this injection thing only works when you have one thing of a certain type that's injected down into a view hierarchy。

Now another thing to think about here is that what about our previews。

 if I go back here to my preview。Down here， when Moji art document preview。

 it has to do environment object。And create a pallet store here。

 so I'll just do pallet store named preview for this one。Because remember， these previews。

 they don't get created from Ogr。app， okay， the main program。

 they're little previews that are running right there in Xcode。

 so you have to inject your own thing in and you're also going to have to inject it not only here。

Its preview as well has to inject it in there and we'll use the same palette to the preview one here。

So environment object really great for this kind of thing where it's kind of used globally。

 it's also great if you have some piece of some view model that you create at some level in a view hierarchy and then everyone below it uses it is just like commonly used by everyone below well you could have it be an outside state object of this level and then environment object injected down。

I'm going to do one thing which is the scrolling emojis thing。Right here。

 I'm going to move that over to pallet chooser， I'm not going to change it or touch it。

 but it's clearly part of my pallet chooser， not part of my MojiR document view。

 just a little code cleanup right there。Let's run this and see what happens。Oh， looking pretty good。

 I see it right there， vehicles， let's cycle through them。

It' not doing anything why is that not doing anything Well， here is our button that does something。

It's not doing anything。So what are we going to do here。

 Well we just want to go to the next cursor of our Plow star right。

 so this is a one liner store do cursor index plus equals1。And again。

 you can see the value of our view model being so powerful here。

 it's making sure that bounds checked， we know it's always going to result in something that's valid one liner。

😊，O， it's working now's not quite as nice， it's not animated， let's put some animation in。Oho， yeah。

 smooth， but again， not what we want。 We want it to look like it's rolling。 Remember that。

 How could we do rolling。Well， you know what， there's actually a really cool way to do rolling with transitions。

 If you remember transitions， one of the transitions is have this slide up from the bottom。

 Another one is have it slide up from the top。 Well。

 if I have these things arrive by sliding from the bottom and leave by。😊。

Leaving up the top it'll look like it's rolling now I can do that it's easy to go here and put a transition on this thing dot transition it's asymmetric because the rolling in and the rolling out are different the insertion is move from the bottom。

And the removal is move。Out to the top。So that's a reasonable asymmetric transition。

 that's not going to work though。We try it， which was a good idea， but no， it's still opacity。

 it's still doing the default animation there。Can anyone tell me why this transitions not working？

What do transitions animate？The coming and goings abuse， right？Well。

 this HCStAC is never coming and going。It's just that this palette name emojis are changing。

 so it's just changing the name changing this text and scrolling emojis。

 they' it's staying there its arguments are changing， but it's not causing the whole view。

 there's no for each or if else that's causing it to be removed。However。

 I'm going to show you a really cool feature to make that view get removed and replaced with another one and that is to give it an ID。

 you just say dot ID and give it a unique ID in this case I can use my palette's ID that will unique identify it that makes it so that now this HStAC identity is part of who it is so when this palette comes in and it's a new one with a different ID that whole view has to be replaced。

because it's a different view because its identity for one of the aspects of it is different。

 so it's a different identity and it'll replace the entire entire view。

 so ID is a really cool way to make views common and go by giving them identities。We run。Yeah。

Working great except this is kind of like our flying number thing where it flew up and then it just disappeared。

 you know we had the flying number fade out but that's no good what we really want here is when it goes up we don't want it to show we want it to kind of get cut off here as it rolls up and problem we're going to go back up here and have this view be clipped。

Remember， I told you that views will just draw right outside their bounds all the time like our background does。

 where you can stop that by saying clipped you can say clipped it stays inside his bounds so now that I'm clipping。

To this。HStack right here。When I roll up。ItStays in its bounds。

Both on the bottom and the top as it comes in and as goes out the top。Cool， all right。

 only one other things to do。 remember when I press and hold。

 I have that thing where I could create a new one or delete that super easy to do。

 which' is gonna go to our button， here's our button right here。

 Actually before I do that with one quick thing you see this kind of button that has a label in this app。

 I'm gonna create a bunch of buttons that have animated actions like this。

 some of them have images on them， some of them have text etc。 So in my extensions。

I created a nice little。Struck here called animated action button。

 and it takes a title or an image and an action。And it just makes it into a nice button This is purely done to make my code a little tighter a little look a little nicer and not have so many curly braces and all that stuff it just tightens it up a little bit one thing to notice here I didn't talk about when we did aspect B great and I meant to is this action argument you can see this is my init for my button and it's taking the title and a system image which are optional because you don't have to provide them and this role is just whether it's a destructive button like it destroy something delete or something and then there's the action and notice it has at sign escaping we never talked about outside sign escaping。

What does that mean it means that this function， this in is going to hold on to that closure and call it later so it escapes from this in and why does Swift want to know that clearly is because it's going to inline closures that can't escape inlines them whereas in this case it has to put it closures are actually reference types it puts them in the heap and gives a point or to them essentially so they can be held onto so that's what at time escaping is and usually Swift always Swift can detect that and it'll force you to put it there so that you recognize that's what's happening。

All right， so I'm going to use my animated action button here and my chooser instead of this thing right here。

 I'm just going to say animated。Action button and this one's a system image with this paint palette。

And this is the action， and since it's an animated action button， I don't need the width animation。

See how that cleaned up my code right there。 It's the same exact thing。

 It's just the cleaned up version of it。 And what I'm going to do， though， is add a context menu。Two。

 this animated action button。And context menu is just a view that's going to appear there and it's supposed to be fairly structured。

 it wants it to be buttons essentially and you'll see that it's going to organize them in a certain way and my animated action buttons are great for being in here so I'm going to put an animated action button to create a new one which has both a title and an image the plus button for new and this is easy to create a new one I'm just going use that nice insert I told you that my view model had and inserts。

Well， eventually we're going to insert a new one that you put in the name and all theojis。

 but here I'm going to make one up I'll call it my this is the math one I was showing you there。

And emojis will be a bunch of math emojis。We go down to math symbols plus sign， minus times， divide。

 infinity， whatever。Got those in there and then I have another animated action button。

 this one is delete and it has a system image as well， this is the minus in a circle image。

And it's going to go right to the model to the palette and just say remove at the stores cursor。

Again， you can see how our view model makes this code so easy and if that was trying to remove the last palette。

 the view model would prevent that， just wouldn't do it。See this in action。Already， click。

 working good， press and hold。Delete new， so we say new， there it is。😮。

Battered it in the middle of our list there and if we want to get rid of something delete now delete is actually a destructive action。

 so I'm going to add to my delete this role， which is dot destructive。Put it in the wrong place。

 probably。Cot on that right。Here we go。 Roll was at the end。 All。

 so I put this destructive role in here。 It's just an argument to button that says whether buttons roll is destructive。

 We go here。

![](img/6c7fbf660e27175a85d7c5afd2a9c4d7_9.png)

And we see it's red。Delete is destructive You can also see that this view right here that the button is using as his title。

 this is called a label a label is a special view that has a title and an image and it knows how to format it properly depending on the context it's in like this。

 a context。A menu。All right， we're out of time， so to make your assignment five even easier。

 I added some functions to move and resize your emojis to the view model so you won't even have to figure that out One thing I do want you to look at and note there is how I implemented that in the model。

Because I use subscripting。I made it so you can say emojiartsubscript emoji。

 size equals something which is really convenient syntax it almost looks like I'm accessing an array but I'm accessing the emoji art instead and the index is not an int it's an emoji that's in there and using that kind of subscripting can make really clean code as you will see so take a look at that you'll get all that when you clone your assignment5 you clone your assignment5 it's going to have all the things we just did here and also just some functions there for moving and resizing your emojis to make your assignment a little easier。

