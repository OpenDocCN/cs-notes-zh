# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p08 -08-Lecture 8 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p8-

All right， this week。lecturelect 8 nine all about animation。

 entire week and your assignment number four is all about animation， in fact。

 your assignment number four is just animate your assignment number three。

 so we're going to really go deep dive and not really talk about much of anything else this week and try to understand how animation works's a very important topic in iOS。

There are lots of different parts of animation and you can see I have a lot of demos queued up I have this slide up here mostly just so you can refer to it later because it's a list of the things that we will have done once we've done them all but I am going make a little detour at the very beginning you see that top miscellaneous topic this miscellaneous topic really has nothing to do with animation whatsoever。

 but I just never found a place to slip it in so we're just going to take a couple of slides time out and go talk about this。

So what is this that I'm talking about well is property observers and a similar related thing called onchan of which we use in view we know that Swt。

 all these value types it can detect when things are changing functions are marked mutating so we know which ones are going to modify things and vs it knows which v are gettable and setable etc so you can kind of stick your nose in there and when a var when its value gets set you can observe it that's what property observing is basically observing the changing of a var now I'm putting this code up here and most important thing to get out of this slide is that middle sentence which is that this syntax for property observing looks a lot like computed vs but it is completely a different thing has absolutely nothing to do with computed vrs so even though it looks almost the same。

So what is this syntax here， So I've got this v is face up。 It's a normal var， like in our card。

 it's a normal stored bar， not a computed v。But I want to observe when it changes now this particular example that I made here is for the pi。

 you know we have the countdown pie that we built the shape of and then we're going animate it this week well every time face up goes to true。

 I want to start using that pies time and every time it goes back face down。

 I want to stop using the pie in other words I don't want the pi to be ticking down when the cards face down。

Here I'm saying I got put a little curly brace after it， like a computer bar in syntax。

 but totally different in terms of semantically what's going on。

 and then I say will set and then another curly brace。

 and then in here this is code that's going to be executed when is space up is about to be set。

And in there， there's a special。Far called new value， which is the value that is going to be set to。

Simple enough， right， so here in Will said， if the new value is going to be true。

 in other words it's going to be face up， I'm going to start using the bonus time if the new value is being set to false。

 I'm going to stop。And this is going to happen every single time is face up gets set， however。

 not on its initial value， so if I were to say vr is face up colon bull equals false。

 which is what we do in Ar and then have this curly brace after it would start out false but this will set would not be called that wouldn't matter here because of course we start out with stopped stopped bonus time usage but it doesn't get set on that initial value。

 but every other change to it this gets involved and there's another one in addition to will set called did set and that gets called right after is face up gets changed and in that one the magic variable and there is old value that's the old value。

just got set to a new value。So that's property observing It's really kind of cool and powerful and great for doing things exactly like this we're going to use it a couple of times this week in animation it's especially valuable to use in your model I find less valuable in your view why is that well let's talk a little bit about what's going on inside of your view and view model you've got this situation where changes are happening。

 you're observing them either they're changes in As sign state or they're changes in As published Rs your view model and it causes your view to redraw right we have this reactive view system and every time it sees changes in those things it's redrawing well if you're observing some property you want to be doing the things you're doing in sync with that redrawing so we don't use property observers in As states。

Instead， we use something in our view called on change Jo， it's a view modifier。

 you can put it on any view， and all it's going to do is execute this closure that comes with it whenever this changes。

So this can be almost any expression in here， and if that changes。

 it's going to execute this closure。So the example I have here is I want to keep track of how many times I've tapped on cards。

 so I'm just going to watch my view modelss cards and every time it changes。

 I'm going to increase my number of taps by one。And I'm actually showing my taps in a text view。

 and I've attached this view modifier to this text view， I could really attach it to almost any view。

 but I would just attach it to the view where it's having the most effect。

 keeping track of this taps。And notice that it takes an argument this closure and this is the new value that is going to have so view modeled by cards are going to change this is what it's going to change two now I don't happen to use that in tap plus equals one。

 but you could use the new value of those changing2 so this is the thing we use when you want to track changes in at states and outside published bars。

Okay， back to this animation thing， so I told you at the beginning of the quarter。

I'm going to try and teach you everything in this class at least three separate times。

 Once I'm going to tell you about it in slides， then I'm going to show it to you with a demo。

 and then you're going to do it in your homework。 And that's very much true for animation。

 So here's the part where I'm going to tell you about animation， all the parts of it， how it works。

 etc。Let's start with the。看 of。Basic。Fundamentals of animation things you need to know to really understand what animation is about and the number one thing to understand is that animation is just showing you change。

In your model， usually over time， that's all it is。 It shows you change over time。

 and this change gets reflected through viewmodifier arguments and obviously shapes can be changing and also all this sounds a separate thing。

 but you're gonna to see it's actually just a variant to the first thing there。

 which is views coming and going from screen right a view comes on screen。

 you want to fade on okay or it goes off screen。 you want to fly off or something like that。

 that's views coming and going。 So those are the three things。

 the three kinds of changes that are happening that we're trying to animate。

This is probably the most important line on this slide。

 animation is showing you changes that have already happened。And just showing them to you over time。

This takes some getting used to for people haven't done asynchronous programming or something like that。

 you just want to think that if I have some animation that's taking five seconds that's animating the opacity or something that the var that sets the opacity is somehow changing over time。

 but it's not when you set the opacity to one from zero and it fades in。When you said it to one。

 it instantly changed to one in your entire view， it's just that the animation system showed it to the user over five seconds right so everything you see that's animating instantly happened。

😡，And just join you over time。Once you get that in your head。

 it'll make a lot more sense how animation fits into all the other things that you're doing。

So view modifiers are the primary change agents in the UI。

 most of the stuff that's changing like opacity aspect ratios。

 even views flying around is just the position viewmodifier。

 there's a viewmodifier haven't showed you yet called position which like each stack and lazy big grid they use that modifier to position their views in there when things flying around it's just because that position arguments are changing right so viewmodifiers are really what makes everything go and you're really going to see that in the demo that we do。

One thing you have to understand about changes to view modifier arguments though。

 is they're only going to animate after the view has been put on screen so this view is going come on screen with a certain opacity and a certain aspect ratio that's not going to when it comes on screen animate from some random value it's going to be that value when it comes on and then if it changes then you're going to see the animation people sometimes get confused they'll set their opacity to something and they're expecting that their view will you know somehow animate to that opacity but。

It wasn't on screen， so it had no previous value， so it starts with the value it has when it comes on screen。

And not all viewmodifier arguments can be animable。

 but I would say the vast majority is 100% of the ones that you would think you could animate are animable。

When a view arrives or departs on screen， when that animation happens。

 the entire view is animated as a thing， so the whole thing fades in right or the whole thing flies off or the whole thing scales in or out in size and a view coming on screen is only animated if the container that's in is already on screen。

So if a view comes on screen with its container， then it's not going to get animated。

Youll only get animated view come on screen and you're already in a container view that's already there on screen and same thing if your view is going off screen。

 it's only going to get animated if it's leaving some container that's staying on screen。

Because if the container goes off with you， then the only animation going to happen is whatever the container is animating。

Now how do views come and go， how do they come on screen or leave mostly if else is in view builders right you have if this is true。

 then show this view else show this other view well as that if changes one view is coming and the other view is going right appearing disappear viewing also for each is a sneaky way for views to come and go because for each is like take an array of things and building a view for each of them well if you take something out of the array it's going to take the view out that goes with it that's a way for a view to go away or to come back in if you add it back to the array since the primary way the views come and go if else or switch statements inside of a view buildder and for each。

So how do we make animation happen， how do we make it go， and there's three ways to do that。

 one is implicitly， and this is the animation we saw for shuffle。

And the idea here is we're going to use this view modifier called animation and we're going to make it so that everything that that affects the view that we apply it to is going to get animated when things change and we get to say what value。

 what thing has to change to cause this animation to take effect so we could actually put multiple implicit animations on something with different values so different things would cause different kinds of animation to happen。

 so that's implicit animation that's all you've ever seen in this course。

Secondly is explicit animation Now in this one， we wrap something that we're doing with this with animation thing right here。

 and it causes all things that changed because of what we did inside there to animate together。

This one is actually the primary way we do animation， not the implicit。

 we do it with this explicit and one of the first things I'm going to do the demo is switch over from the implicit animation we are doing to explicit animation。

 which is how we would really do it。And then the last way that we cause animation to happen is by including and excluding views from the UI because I told you that we can set what kind of animation happens if we remove a view from the UI does it fade out or whatever。

 so that's something we can do you removing them or adding them that will cause animation to happen and these are really the only three things that cause animation。

Right。Now all of these things though again only happen if they're happening in views that are already on screen where oh we can only animate change after we come on screen I've said this twice already right this is the third time I think just want to get this in your head because in your homework assignment you're going to try and do something I almost guarantee it and you're going to be like it doesn't animate well it's because it came on screen that way you didn't change it after it came on screen。

All right so let's talk about implicit animation here。

 this is what some people would call automatic animation and it's essentially it's a viewmodifier right so it kind of marks a view so that all the things that are happening to that view before that view modifiers added so all the aacities and aspect ratios and other kinds of view modifiers you put on that view changes to those will get animated as long as the value is true in the dot animation according to some animation curve。

We'll talk about what this animation curve is if you remember that dot animation that we did。

 it had an argument right， the first argument there you see this says simply add dot animation。

 there's that animation argument， what is that that specifying this curve and duration of the animations Here's an example I've got a ghost right there and he's got some card maybe this is the ghost。

 this is a piece that's the ghost of some card game that's better than the one we have and it's got scary cards and it's got upside down cards and other kinds of things and you know when the cards scary。

 it shows it to you and when it's not scary it hides it with its opacity and it's also got something here called a rotation effect。

 that's just another view modifier and so it knows how to be upside down rotates itself 180 degrees to go upside down and when I put this dot animation and I've used an ease in out animation here it causes both of these。

To get animated。If I were to put this animation right up here under the ghost。

 neither of these would get animated， if I put this in between the two only the aacsity would get animated。

 not the rotation effect， so where you put the thing determines which things are getting only upstream things get animated there。

And if I didn't have this dot animation， just took it off completely。

 then these things would happen instantly。There would be no and that's assuming there's no explicit animation going on we're talking about implicit here we took that they would just instantly happen and we saw that before we put our animation on our cards we were clicking on things and they're instantly turning over we had shuffle they instantly shuffle you know that without some sort of animation things happen instantly on screen。

This warning dot animation and pluslic animation works more like font and less like padding。

So if you put dot animation on a VStack， it's almost like you put dot animation on everything in the VStack。

It kind of propagates in。And that can be confusing a little bit and to be honest。

 we don't usually put dot animation on a VStack that would be unusual usually dot animation。

 this implicit animation it's less often used and we're usually putting it on the Lego brick view the right text or some view that we've created that we've constructed out of other containers or whatever so that's just something that can kind of confuse you you put dot animation on a VStack and you're like what's going on you know the things inside are being animated but。

In a way， it makes perfect sense that it does that。But just something people get surprised by。

Now let's look at that first argument that ease in ease out thing， the animation curve。

 and that's called an animationstruct， it controls how the animation proceeds and it lets you control some things about the animation like its duration。

 how long is it going to take， or the system to show this change to the user one second， two seconds。

 whatever。You can also control whether to delay the animation。

 this is especially true when you've got two little pieces of animation。

 you want one to happen first and then you want the other one to happen。

 maybe you delay the first one by half a second and then it kicks in。

You can also decide whether the animation repeats， does this an animation just keep going over and over or how many times it goes or whatever？

I can even repeat forever。And you get to control its curve。

 the animation curve Now what do I mean by animation curve the animation curve is how it splits up the time it takes to animate so ease in ease out which is easy in out actually it called which is kind of the default I believe animation it starts animating it kind of slow and then pixel speed and then kind of slows in at the end and that's so that views don't jerk out of their locations but they still get to where they're going quickly that makes sense。

That's as opposed to linear， which is it goes from the start to the finish at exactly the same speed and there's a bunch of other curves like a spring which is an interesting animation。

 that's something where it gets to where it's going pretty quickly， but then when it gets there。

 it kind of vibrates a little like it was on the end of a spring and you know some things when they fly across the screen。

 you don't want them to just land and stick， you want them to kind of land。

 give a little soft landing as we call it there。And all of this stuff is in this animationstruct。

 you want to go look at the documentation for animation you'll see all the things that you can do and all these curves and all the settings you can do。

 there's really not as many as you might think because you don't really want to have too many different kinds of animation curves going on the user get a little bit like whohoa。

 what is all going on on my screen？Automatic， implicit ones， as I said。

 they're not really the primary source of animation we use them mostly on leaves， leaf views。

 and also we use them for animations that are very much independent of all other views。

If animations go with a whole bunch other views， then we're going to explicitlyly animate the change that causes that and we'll see that in the demo what we do there。

Now， the most likely cause of animations in your app is going to be user interaction。

 The user is going to tap a card。Use are going to hit the shuffle button。

 that's going to cause a lot of animation to happen。SoThose are explicit animations。

We're almost always going to use explicit animations to react to change。

 don't make your UI reactive change by putting a whole bunch of dot animations in there instead you're going to in the place where you make the change or usually calling a viewmod intent function。

 you're going to wrap it with an explicit animation。

So let's talk a little bit more about explicit animation， how it goes here。

 as I said before it's essentially just wrapping a block of code。

 things that are going to be animated together， so here's an example of it。

 you see I've provided a linear animation here two seconds long and whatever happens inside here this do something that will cause View modifier shape arguments to change that's all going to get animated together with that curve。

 a linear curve of two seconds long。explicitplicit animations almost always are wrapped around view model intent function。

 extremely unlikely you would have a view model intent function called without wrapping an explicit animation around。

 you might， but pretty rare。That you would do that。Red text always means pay attention。

 implicit animations have more power than explicit ones。

 So if I explicitly animate something and inside there， there's a dot animation。

 that Don animation is going to win。That makes sense because remember。

 we're putting dot animation on somewhat independent animations。

 so we don't want those independent animations to be affected by whatever is globally going on。

 animating。And you'll see that very clearly in the demo。

let's talk about transitions so transitions are this thing about views coming and going we call those transitions so get used to that word transitions that's what the view modifier that does it that sets it up as called and they only work for views that are CTAAOS that's my nice a acronym there I couldn't actually come up with any phrase that would be a word so I pick this particularly hard to say CTAAOS or stick in your mind right CTAAOS is containers that are already on screen so if you want a transition to happen for your view you have to be in a container that is already on screen。

Underneath the covers of a transition， it's actually nothing more than a pair of viewmodifiers。

 a transition for coming on screen is just one view viewmodifier that has the arguments of that view modifier before it comes on screen and another viewmodifier that has the arguments for that viewmodifier when it is on screen and it just animates between those two viewmodifiers as it's coming on screen and you might have another pair for going off screen viewmodifier what it looks like just before it goes off screen and then another view modifier with its argument set for is off screen and it just animates between those two so that's all under the covers though above the covers it looks like a transition is a thing like opacity transition an opacity transition is just a viewmodifier with opacity1 and another viewmodifier with a opacity but that's all undercover you don't care about any of that you're just going to say transition opacity and you're going to get that transition。

You can also of course have asymmetric transitions where it fades on screen。

 but then it scales down to disappear when it goes off screen。

 in that case you'd have four view modifiers， the two for fading in and the two for scaling down or flying away or whatever。

We mostly 99% of time use precanned transitions and we find these not in astruct called transition。

 unfortunately， it's astruct called any transition。

I'm going to talk a little bit about any transition here。

Any transition is a type erased transition struck now I'm not going to talk about why we do type erasing but。

From your standpoint， just think of thestruct that does transition as any transition。

 even though that's not really true， that's where you see them all。

 that's where you're going to go in the documentation to see what kind of transitions you can do。

 that's where all the static lets are that define all the wellknown transitions， etc。

So what are some of these things， there's opacity that's the fading in and out， their scale。

 that scales in and out， so that's a view that would like shrink down to nothingness when it disappears or if its appearing it would shrink up from nothingness to its full size。

Offsets's an interesting one that's how it would fly off screen so offsetet just takes it from where it isn't offsets it by a certain amount you get to specify how much there's also things like move to edge where it'll fly off to the top edge or the right edge or the bottom edge etc and of course you could define your own transition using this modifier version which has the active and identity view modifiers。

 the pair， the two sides of the pair that it' going to use the before and after of the transition so you can define your own even just using this type era thing there。

So how do we specify transition， how do we say when this view goes on screen or comes off screen。

 use opacV or use scale or whatever， you do it with this dot transition view modifier。

Now here I have。Kind of a pared down card okay， it's got a face up and a face down。

Fewer lines of code than ours， but you get the idea right right we got a rounded rectangle we got a stroke rounded rectangle with the text on it and then in the back we've just got a filled rounded rectangle There's actually three transitions on this slide。

The text is going to transition by scaling up from zero size up to its normal size。

 and it's going to disappear by starting up ghost size and going down to zero。 the back of the card。

Has the identity transuers means it just instantly will appear so that's like no animation right identity means that the two view modifiers are identical so there's no nothing to animate between two of them the two of them so it just instantly appears it instantly disappears the back。

There's a third one which is this rounded rectangle， notice it doesn't have dot transition on it。

 the default is opacity， so that would actually fade in and out so when this card went face up the stroked rounded edge would fade in while the little ghost zoomed in。

This transition thing is not like dot animation transition applies to the entire view so if you put dot transition on a ZStack。

 you're talking about how the whole ZStack will fade in together right or grow in together you' it's not going to sprinkle them out to each thing inside。

 you're talking about the entire ZStack。This dot transition。

View modifier like that transitional paity or whatever。You're just specifying the transition there。

The word transition can be used as a verb， people think， oh I put dot transition。

 I want this view to transition okay that's not what's going on here。

 Think of transition there as a noun， This is the transition to use when this thing appears or disappears the way you make a transition animation happen is you take a view off the screen or you put it on screen that's what makes it happen dot transition is just saying which transition to use So think of dot transition as a noun。

Again， I emphasized this because we had students in previous quarters who said， you know， help me。

 I I called that transition on this thing and it didn never transitions and it was because they weren't removing it or adding its link so that transition there is the transition to use。

It is possible to control a transitions animation curve you see here I've made it so that this transition which is an opacity fade in transition it's animation is always going to be a 20 seconds well linear your transition is that's a very slow commentary so you can do it but the reason I mentioned is because notice that the dot animation is not on the view it's actually on the transition you see and transition opacity dot animation I'm actually specifying for that transition use this animation so people get confused by that this dot animation is part of your transition normally we don't do this we allow whatever our explicit animation that's happening or even our implicit animation is having to affected but if you need it to override it you can do it that's what that is。

All right， totally different thing here now matched geometry effect so sometimes you have a view that you want to move from one place to another place and sometimes it's easy it's like shuffle when I hit shuffle and I reorder my4 each it causes the lazy B grid underneath to change the dot position view modifier on all the card views and they move and since dot position is a view modifier it gets animate it changes get animated and one the cards all move around really real easy like。

But what happens if the two views are not in the same container？

This won't work because you can't just change dot position。

 the dot position view modifier is within the container， the other view。

 if the place is somewhere outside the container， there's no global screen wide dot position。

 it's only inside the container。To do this， you actually have to have two views。

 one in one container and one in the other， and you're going to remove one at the same time that you're adding the other one to the other one and you're going to match their geometrymetries。

 that's what match geometry effect here is。SoLet's talk about an example of doing this。

 let's say in our memorized game we wanted to deal the cards out。

 we're not going just have them appear， we want them to deal out from a deck of cards。

 well we would have the deck maybe in the bottom corner or somewhere else。

 and then we would have our field of cards in our lazy begrt。

 they would be in different containers clearly。I would just put match geometry effect。

ViewMoifier on both of them， the one that's in the deck view and the one that's in my memorized game view and the ID I'm going to use is going to have to be some identifier。

 that's the same for both easy for our memorized game。

 We would just choose the card identifier that would clearly identify the same view on both sides and then there's this namespace the reason you want a namespace is we might have matched geometry effects going on between different things like maybe we have a deck we're dealing out of maybe we also have a discard pile maybe it's a game like your set game where the cards get discarded and you want to go to a discard pile So you might have two things going on so you have to have discard IDd be namespaced for which match geometry thing you want。

 So you create a namespace with an at signed thing like outside sign state called outside sign namespace So outside namespace bar my namespace notice you don't have to say colon and namespace It's implicit。

This thing knows that it's an outside sign namespace。

 so you don't put the colon namespace at the end。And now all you have to do is write your code so that only one of the two views is ever on screen at the same time。

 right you got to match up there four reaches， the arrays the drive the four reaches so the ones whatever in the other one's array。

 or if you're doing if thens you got to have an if that matches up the other ones else。

So they're never on screen at the same time and if you do that。

 then the view as it's disappearing will fly over to where the one that's up appearing。

 their geometries， their positions and their sizes， by the way。

 will be matched so even if your deck were small and your cards were big the card would start out small on the deck and then it would just get larger and fly over to the other one you would match geometry that's why it's called match geometry effect。

It is possible to match the geometries of views that are both on screen like ones a bit of a slave to the other one following it around or matching on top of it。

 there are other arguments to match geometry effect which determine which one wins when they're both on screen not really going to talk about that mostly telling you about this so you get an idea that it's out there you will need this for your assignment 4 because you are going to be doing dealing the cards out and discarding with animation so you'll absolutely need this。

But you won't need。They're never be on screen at the same time your cards that you deal are either in the deck or they're up showing to the user or they're in the discard pile。

 they're never in two of those places at once。Now remember I said that animations only work on views that are CTAAOS。

 What if you want to kick off an animation as soon as you are in a CTAAOS right as soon as you appear in CTAAOS you want to kick off your animation well there's a really cool view modifier for doing that which you're going to use all the time。

Dot on a appear。 It just takes a closure。 and that closure is gonna to be executed every time your view appears on screen。

 And when you appear on screen， you are by definition in a container that is already on screen。

 you can't come on screen otherwise。 So since that's the case， you can do some animation in there。

 So inside your on a peer， you can do other things in your' on a appear。 by the way。

 initialize some variable， get some data ready， whatever。

 but you could also do inside there with animation start some animation going。

 change jumping that causes the animation And so on a appear。

 and we're going do this with remember in the demo I showed you have memorized we have the score thing where this match two cars and would say plus two and it would fly up。

 That's exactly what happens there。 that plus two view is gonna appear on screen。

 And as soon as it appears on screen， I'm gonna to start animating it to fly off。Using on appear。

So I told you that viewmodifiers and shapes are where animation happens so how does that work what's the engine inside of a viewmodifier that makes these things do what they do it's actually pretty straightforward essentially as you might imagine the animation system is going to take the animation duration and divide it up into little pieces and it's going to ask a viewmodifier okay what do you look like here what do you look like here what do you look like here all the way across and you know of course the animation system takes care of whether it's easy in as that ease out linear duration it does all that well it's doing to the viewmodifiers okay what do you look like now what do you look like now over and over and over and that's it and that' all a viewmodifier has to do to work is to listen to the animation system draw the piece it's supposed to draw and the animation the system will take care of the rest。

For example， our card to five view modifier that flips a card over。

 we know that the way it flips over is bad， doesn't look like a flip at all， it wants to do it。

 it's going to be peaceifying the rotation of the card here's my card to here actually right and I go from face down and it rotates like this and once I get on edge then I start seeing the front and then it。

Finishes right so this is got to get peaceified and that's what's going to happen for Carify。

So how does it do that， how does the animation system talk to your view modifier and tell it what piece to draw and all that。

 it does it through one var。This one var called animatable data is the thing that does it Now any view modifier or shape that wants to be animatable has to implement the animatable protocol。

 It only has this one var in it。 The type of the var is a don't care really。

 but its care a little bit because it has to implement the protocol vector arithmetic。

Vectctor arithmetic exactly what it sounds like being able to do algebra basically on whatever this thing is that you passed so that it can be sliced up into little pieces。

 no matter what it is it can be sliced into little pieces now most of the time that's going to be this animatable data is going to be a float or maybe a double CG float。

 something like that maybe it's opacity or rotation those are going to be double precision floating point numbers but there's a really important vector arithmetic implementer called animatable pair。

And it's got two don't cares， which are themselves vector arithmetic things。 Of course。

 you can have animatable pairs of Cg floats now you have two Cg floats that you're animating or you could have an animable pair of two animatable pairs of two floats。

 Now you have four floats that you can animate。The combination of having animable pair and then these things that implement vector arithmetic。

 you can pretty much animate almost any mathematical。P of data。

So how does it work that there's this's just one var Well that var。

 the setting of that var is the animation system saying draw this piece right so it that that animatable data to a certain piece and you got to draw yourself the getting of the var is actually important too so this is a get and set var the getting of the var is the system getting the start point and the endpoint of the animation So when we go from face down to face up the animation system needs to know that it starts at zero ends at 180。

Right when we go is space up 00180 so it's going to ask that bar before the animation starts。

 where am I starting where does your animable data start and then it's going to find say what's the end point and then it's going to cut that up into little pieces right you can't cut it into pieces unless it knows the start and end。

And it's getting that from this bar， the bar is important for communication both ways here。

Now this var animatable data， you don't really want to be writing the code for our Car toify and then there it's like set rotation to animatable data。

 you want to have a var called rotation， and you say set the rotation to rotation right。

 so animable data is often just a computed var that sets and gets some other real var。😡。

In other words， we just use it as an alias as a name just so we can communicate with the animation system。

 you'll see that when we do our Carify the var we're going to animate is rotation。

 but we still have to make it come in and out of animatable data so we'll have a computed set get var for animable data that sets and get the rotation。

So that's it that's all there is pretty much to animation of course i'm really just showing the highlights of animation all of these things have an enormous amount of depth to them which you'll learn over time but let's go through the demos today and on Wednesday you'll see all this stuff happening is's going to make a lot more sense when like to see it in code as with most things。

All right， I told you that the first thing we were going to do when we got in the demo is get rid of that implicit animation。

 that's this right here， this is what's causing shuffle to cause this animation to happen here if I take it out。

Then shuffle。It becomeses instant， just instantly， it's not moving them around。Remember， I also said。

 I' going put it back here。I told you that。When I click shuffle。

 whatever happens in here happens instantly and it's just taking time to show it to me。

 you can kind of see that when I click shuffle really fast you see it doesn't quite the cards don't get to their new position before I start shuffling them again so they just start heading to the next new position that's because I'm instantly changing the order of that and it's instantly changing in my code and animation systems we just trying to catch up as it desperately tries to do that。

But we would never do shuffling like that because shuffling is response to user intent to view model intent。

 so we would actually do it right below it here， we would say with animation。

 shuffle the cards please， which also reads better from code wise。



![](img/d24111b08240758505b7671af5af9309_1.png)

Because that's really what we want， please with animation shuffle and now if we go back here。

Go on a couple of cards and shuffle back to fully shuffling every time I click shuffle because that's an intent by the user and I'm animating that intent。

 but something has definitely changed because in to watch this， clicking a card instant。Instant。

When we had the implicit animation up there， when I clicked on a card。

 it faded in and faded out because that implicit animation was applying to any change to the cards。

 not just shuffling， but anything， whereas here we've made it specific。

 this animation is specific to that。And we can of course， control the kind of animation we want here。

 so we know that ease in out is the default animation。IfThat's what we went to be seen so far。

 we could also control the duration by making it be an in and ease out with two， so watch this。

And this by the way is a great way to debug your animation。

 I'm to say this right off the bat when you're doing your assignment for set your animations to take a long time and then you'll really see what's happening。

 is it really fading in you know what's actually happening there？

And we could use other curves that maybe we can tell the difference here ease in is ease out looks like that versus linear。

We'll see this later， make even more sense。See it's kind of same speed all the way through the curve。

 how about that funky spring thing told you about。We'll use an interactive spring。

It'll do a response time about one and damping fraction， maybe 0。5。🤢，And here we go。See how it。

hass a soft landing there and we can control the damping to make it more springy or less springy or whatever that's how we control the animation that's going on here。

 but most of the time we don't want any kind of funky animation we actually want the default animation because we want users to have the same experience they're having in all the other apps。

For using an animation curve， we want to have a pretty good reason。Now， when I hit shuffle。

 what's actually happening？What's happening in there is I'm rearranging the order of the cards that's causing the lazy B grid to reposition all of the views inside of it because the for each has changed its order。

 just using the position viewmodifier。All that's really being animated when I click here is the arguments to the position view modifier inside the implementation of lazyV grid。

 which we can't see， but still all view modifiers that change are being affected here because we're explicitly animating everything that changes with that user intent。



![](img/d24111b08240758505b7671af5af9309_3.png)

Let's go back down here to our choose a card and give it animation2 with animation。Choose the card。

Now when we have this and we tap， see we're getting。Fade in effect。

 we'll see it a little better if we。Is in out duration。Two down here。Do would foresee it's fading？

Fading in。Fading out， interestingly， shuffle is still fast。

 Suffle doesn't take two seconds because its explicit animation doesn't have。

Easing ease out duration too。I let's take this back off and just use。The default animation there。

Let's talk about when we would use implicit animation we took that implicit animation off up there and I told you we would never do it that way。

 well， when would we use implicit animation Well how about if we make it so that if we get a match like this？

This little ghost guy does a summerrsault， acceleration summerrsault。

 Lets see if we can get him to do that， but where does that happen。

 Well it's in our card view over right here， this is the ghost。

 right the text that's inside of our card view， I want that text。

 that ghost to do a flip when the things are matched。Really easy to do。

 you can do a flip with a rotation effect fact you saw in the slides there， it just takes an angle。

 me say degrees and we'll have if the card is matched， we'll do 360 degrees， otherwise zero。

So that's a rotation effect。 And if I go over here and match。W he did it。 You see how's so fast。

 you can barely see him there。 and maybe that's a little too fast。

 It's so fast I don't really get to celebrate my victory very long there。

 So I want to affect the animation。 so this is where I would do an implicit animation here。

 Maybe an ease in out。 maybe I want the duration to be and maybe two seconds too much celebration and but we'll see and I'm only going do this when the card is matched。

 There's no reason to apply this animation any other time。

 No other change should cause this animation。 Let's see what happens here。There he is， Anne。

And now you can really see the ease in is out right。

 let's also go and make this so we up fewer our cards， some of the cards are bigger。

See the ease in ease out to happen or he starts and the knee speeds up and he slows down。

What if I wanted him to keep spinning okay， he did a nice flip。

 but what if we just wanted to spend forever we can go on here and say repeatat forever。

That's what that looks like。冇有。It is repeating forever。 that's good。

 And you can really see the easy it is out now because he slows down every time he turns around。

 But what I really wanted was for him to keep going round and round and really wanted to go back and forth and repeat by backing the animation up and then making it go forward no problem inside repeat forever。

 we can say auto reverses。False， don't utter a verse， please。



![](img/d24111b08240758505b7671af5af9309_5.png)

it goes around and round。Again， its easy is that how it's causing him to stop each time。

 let's get rid of that， make this be a linear animation。And that's a little slow。

 I got maybe something like one second to do one full turn。That's pretty good。

So here's where you might use an implicit animation。

 you want this to happen no matter what's happening， for example， shuffle。Keeps doing it。

 Why would it stop my match is still showing， I should still be celebrating it。

 it's completely independent of any other with animation or anything else going on。

And it overriide it two when I did the with animation。

 it didn't use my shuffle duration or something like that it used this duration and this linear curve and all that stuff。

 it's overriding what the explicit one is doing。And another thing we would do here which is kind of interesting。

 see this little animation right here。 This is kind of an animation I might want to use other places spin animation。

 I'm going to take this off here， I would really like to be able to just say spin duration one for example So how could I say that Well extensions So here's a good example of when we can use an extension so I'm going to extend animation and I'm going to add a little static form called spin and it's going to take a duration a time interval and it's going to return an animation and I'm just going to return that linear thing that I had up there。

So now I've made a new kind of animation， animation。min， it compiles， no problem。Works mind。

Now let's talk about the real animation problem we have here， though， which is this animation。

Card is face up， we wanted to turn face down， let's take a close look at what we have right now with that。

 which is in fact I'm going to go in fewer cars take this really large。

So we have total just fade right now。 fades in， fades out。Hey Jane， I see that。Paid out。

That's clearly not what we want we want it to rotate in kind of a 3D manner。

 not rotate like this effect we want to rotate like this Well there's something that actually does that here I'm in my Carify obviously this flipping of the card is a Cardify thing it does nothing to do with a memorized game it's flipping card you go clip anything on here so let's go add on our ZStack in Carify in Carify right here in our ZStack rotation 3D effect。

So it wants an angle as well， this is degrees， and if I'm face up， then let's say zero。

And if I'm face down 180 degrees， I want to rotate from face up 180 degrees。

 everyone agreed this is 180 degrees。And the axis is interesting these three numbers X Y and z specify where you are。

 so this is obviously y this is x and z is out towards U and you can have this thing rotate on any of those axes we had it rotating around x it would flip this way we're going to have it obviously go from y。

 so it flips like a card does like we're flipping a card over and we can specify those here so it would be 0。

1，0，0 in the x direction，0 in the z direction just one in the y direction。

That's all it takes look at this。Nice， and it's a little hard to see it's going so quickly。

 we can't see what's going on。 So let's go back up here to our choose explicit animation and make it so that it takes。

Maybe。Three seconds seems good。Here we go， ready？Now that's not quite right。It's so close。

 not quite right， for example， notice that when my card starts from face down and it starts going。

You start to be able to see the front， Can you guys see the front No。

 there's no front but on here you it's starting to fade in front there's front you can see the front what you shouldn't see the front until you get here right once you get the straight of not now you should see the front and you shouldn't see the back。

So somehow we can make it so that it switches over without this spaading。

 essentially we don't want this opacity right here。To be animated。

We want it to happen instantly as soon as we get to 90 degrees well。

 there's no way to do that other than to have the view modifier itself control the animation。

 it has to be involved at every piecewise turn of that rotation so that it can make the opacity be right when switches over from being on edge here。

How do we do that that I talked about in the slides。

 we're going to make our view modifier be animatable。

 which means we need this var animatable data it starts out with empty animatable data right there。

And what is our animatable data again it's that rotation I don't want to call rotation animatable data everywhere in here。

 I have a var called rotation， it's just a double number of degrees so I this animatable data here be that double but it's going to have a get which returns my rotation and it's going to have a set which sets my rotation to the new value。

So this is computed property right remember from index of one and only face up cards we're doing the same thing here。

 we're just getting and setting the rotation directly every single time the animation system talks to us about a slice。

 we're talking about the rotation and the reason we do this is so that we can use rotation down here in our implementation。

 not animatable data， which is just a bad variable name。So where do we need a rotation，Clearly。

 our rotation 3 de effect once the rotation， we want to pick a。3D effect， which is that rotation。

 Now we have to say。This is the rotation because as soon as we start providing this animatable data。

 these animations stop working。These animation don't work anymore because we put that and we told the animation system we're doing the animation so stop automatically animating our stuff in here。

 let us do it so I need to piece wise rotate my card as the animation says。

 oh you're at one degree two degree， 10 degrees I need to beat this many degrees rotate through to defect what about my opacity。

If I redefine is face up to be 90 degrees or less， then this will still be right， let's do that。

 let's go up here to I face up and just have it be a computed var whose value is rotation less than 90。

Now is face up is computed to be the right thing as long as rotation is less than 90 degrees。

 face up is showing as soon as it's not 90 or more now we see the back of the car。

The problem is down here。 Look at this error Cardify is face up， face up well okay yeah， okay。

 I've changed its rotation， but I don't want someone who's calling Cardified to have say Carify rotation equals0 okay。

 or rotation 180 if it's up I still want them to say Carify is face up How would I do that Oh how about an initializer in it is face up It's a bull。

And if is face up， then our rotation。Is zero， otherwise， it's 180。

 I'm just I'm using my initializer there still says is face up and it's just setting the rotation to either zero。

 this or 180 this。This protocol， I'm going to click on it。

 so you have an idea what this looks like in the documentation。

 you can see that this protocol only has the one bar in here。



![](img/d24111b08240758505b7671af5af9309_7.png)

Animable data。 And notice this has associated typed animable data。 Remember the slides from protocol。

 I told you that don't cares for protocols。 This is a protocol。They have this associated type thing。

 So that's what you're seeing here。 That's why I showed you that slide。

 So that when you see things like animable data， you realize， oh， this thing has a。 don't care。

 That don't care is the return value of that var。 See， and it has to。Care a little bit。

 implement vector arithmetic And then from here you can say， okay， well vector arithmetic。

 what is that click on vector arithmetic Here it is ined from additive arithmetic and in fact。

 it's able to calculate default implementations of vector arithmetic from additive arithmetic if you go there you can look and see。

 well what implements this additive arithmetic here they are。



![](img/d24111b08240758505b7671af5af9309_9.png)

All right， now let's see if it works ready， we got this， here's our is space up， rotation。

ll put this code all on here， ready。workeded right， no no more opacity。

 there's no opacity is involved here because once we took over by implementing animatable data。

 all these things stopped being automatically done and now they're being done by us。

Now I'm not going to ask you to do your own animated view boifier in assignment4。

 I'm really showing you this more so that you understand what's going on inside of all those viewmodifiers。

Now I want to start doing some of the animations like the flying number and things like that。

 so let's go back to our model and implement scoring now you all did this was assignment one you did scoring assignment two。

So I'm going to go back to my model here and I'm going to add scoring， which of course。

 is just private set var score， which also have started out as zero and then down here in our chooses when we have a match right these two things are match I'm going say score plus equals two。

 I think we got two points for a match right and then we had minus one when we had a mismatch that we'd already seen the card so let's put that in there。

 we don't have a match here， then we're going to say if the card that the chosen index has been seen or something like that。

Then score minus equals1 and the exact same thing for the potential match。

So what about this has been seen？Where where do we set that， Well。

 that's just something on our card down here。 Cards can be face up。

 They can be matched and they can has been seen goes false。

 I assume you guys had something like this。 Some you had to keep track of whether cards's been seen。



![](img/d24111b08240758505b7671af5af9309_11.png)

How did you set this， Well， I'm guessing you set it up here in index of the one and only face up card。

 or maybe you said it。I don't know if anybody be left the card flipping down down in here somewhere。

 but wherever you flip the card's back face down， you probably said has been seen， which is great。

 but there's another way to do it now you know which is。The property observers I showed you earlier。

 so here I'm going to say in your space up whenever you set it。If the old value was true。

 so it was face up and it's now not face up， so you change it from。

Was face up to not and has been seen equals true。 w a property observer， really easy to set this。

 And we're going to use this property observer， obviously， for the pie thing。

 I was to stop and start using bonus time as well。Now we just need to put the score in our UI。

 so we're going to bounce back here to our view model， expose this。From our model to our view。

Score is an int， which is going to return our models score。Of course you should do that， by the way。

 I have to say having seen some of your assignments， please。

 I said this many times don't call your model bar model and don't call your view model view model I'm calling it that so you learn it you want to call it something meaningful like game or something like that something what it is the bar what it is。

So we add our score in the view model， pop back over here。

 let's put the score along the bottom next to the shuffle right there， I' make a little H stack。

 the text says score， put the view model， that score in there。We'llll put a spacer in between。

Button inside the Ht。I don't tend to tell you about command keys and so like that。

 but this ones really valuable if you select curly bracecing here and do control I it will move all the spacing so I for indent so it's like the automatic indentor。

I mean， it mostly tries indent as you type so you don't need it much。

 but if it didn't do it like it didn't do it there。

And since this is a demo I'm going to make these large fonts。

 this is another thing like calling the thing model that you wouldn't do in real life。

 but I just on the screen here I want you to be able to see these things large。

 but you wouldn't make your buttons large title。It wouldn't make sense。

I I'm going to take the time to do this right I don't like this body。

 it's too many lines of code too hard to see exactly what's going on。

 too many curly braces and all that stuff。 So I would actually take the time in real life to say I'm make a private var called score。

 which is some view I'll put this。Text in here。Even though it's only one line。

 it's still naming it and then same thing here for shuffle。I view and put this。In here。

And that lets me go back up here and say score spacer。



![](img/d24111b08240758505b7671af5af9309_13.png)

Shuffle， and this just makes this more understandable is easier to read what's going on。

 It's not about the fact that and I actually added a line of code here。

 I have two lines of code where I only had one up there。

 but this line of code is a naming line of code and naming computer science is all about naming。

Arguments have been made that that's all it is is one gigantic naming exercise。

But you can see how it makes my code look a lot better at the code that's selected there and that really wants you to do that not to mention the benefit of it's a lot easier to debug your view buildderers when you have small little view buildderers because when they have an error in there sometimes they give you an unfathomable warning what is that but if you break it down into small pieces then you'll see at least where the warning is coming from。

Now let's take a look and see how things are going here， we' got this， got a real slow turn。

 let's see if our scoring is working。It is working to。

 although anything I don't like about it watch this， let's make that match and first of all。

 let's speed ourselves back out。

![](img/d24111b08240758505b7671af5af9309_15.png)

![](img/d24111b08240758505b7671af5af9309_16.png)

I get shoes we go back to normal speed here。😔，All right， so I'm going to pick this， flip over。

Now watch my score down here。You see I've faded in the two faded in I don't like that I I't want to fade there I just want to appear so how do I stop it because the reason that's happening is my explicit animation is saying hey。

 animate everything that happens when I click a card Well that happens when I click a card So it's animating that how do I stop it well implicit animation dot animation nil。

So it turns out that animation that the thing takes is an optional and you can press specify nil and that means do not animate changes to this view now watch our score down here。

 click ready。Good instantsant 2。So dot animation n。

 nice little thing to have when you want to turn off animation。Flying number。

 we're not going get all the way through flying number， but let's get as far as we can get here。

 I am'm going to do my flying number。 It's actually going to be quite easy。

 I'm just going to put a number which is whatever the score changed and then when it appears I'm going to animate it flying off and opacity going to zero So an animation is actually quite easy。

 you already know how to make that opacity go to zero and moving it also turns out to be just one view modifier。

 but I got to get this number on here somehow when the score changes。

 let's talk about where I'm going to put that， I'm going to put that on my card view。

 right when I click on a card， if I got two points like plus two is going to appear right here。

If I click here and I had a mismatch， minus1 might appear here and that's going to move over。



![](img/d24111b08240758505b7671af5af9309_18.png)

It's going to appear on my card view， let's say。Dot overlay。

 because it's going to overlay on top of it。 I'm going to create some view called flying number。



![](img/d24111b08240758505b7671af5af9309_20.png)

And the flying number needs the number to put on it like number。

 And I'm going to create a function for this Sc change caused by。Mi Cart。

That's what I want to put on when I click on a card， right。

 I want the score changed that this card caused。Plus  two， minus1， whatever。

I'm going to write that function， let's go down here and say private funk score change caused by card。

And it's going to be some int because of my scoring is integers right there。

Now I can't say card here because this is what， what's that type memory game of string。 card。

 I am going to immediately go up here and save myself some typing by putting a type alias in there card equals memory game of string。

 card。Now I just go down here and I can have this just be card。And let's return zero for now。

 I guess， but we're somehow going to have to calculate what the score change is that went to that card。

Before we do that， let's go stub out or start to implement that flying number and that's where we'll end today。

 and then when we come in on Wednesday we'll get it animating and figure out how to get that score change going。



![](img/d24111b08240758505b7671af5af9309_22.png)

Solying number， I'm going to go here， file new。F。This is a swift UI view， a lower left corner。

It's called flying number。

![](img/d24111b08240758505b7671af5af9309_24.png)

Make sure it's in the right place here， it is create。Here's our flying number。

 created its own file for it。 That's great。 We know that our flying number needs a number。

 so we'll say let number be an int。😊，And inside its body， it basically just text。

 it's like the text of a number， which you'd like to just say that text number。

 wouldn't that be cool， but we know that the argument to text is what a string so we could do this。

Quote backsage number right， could do that I'm going to show you another cool thing about text。

 it knows how to take other data types like number and format them。

So it has a format argument and one of the formats it has is a number formatter。

And we're going to see that we're going to put other arguments on this number four matter。

 but that's a nice feature of it too there， and let's go down here to this and say number five is going to be our preview number。

And what else do we want to do here， one thing about my flying number。

 I never want zero to appear and fly， we all agree with that。

 which only score changes where it's like plus 2 or minus1 or something that changes。

 so I'm going to put an if number does not equals zero。Then I will do this。

And that's going to keep zeros from popping on， I think， all the time。

That is as far as I'm going to go， we're out of time and just a little preview of what we're going to do next。

We're implement this score change and the fundamental technology I'm going to use for this is something called a tuple and hopefully you all know what a tuple is because you did your reading assignment I hope and you paid attention but a tuple is a really nice little data structure that you can use for exactly cases like this where you need to kind of keep track of a couple of things together in our case we need to keep track of which was the last card that was chosen and what was the score change that's a couple pieces of data they didnt need to be stuck together all the time and yeah I can make a struck forward and all that but it's just nice or useful little tuple so we'll do that to start on Wednesday。



![](img/d24111b08240758505b7671af5af9309_26.png)