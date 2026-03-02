# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p09 -09-Lecture 9 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p9-

All right。Lecture nine， just a continuation of lecture eight。

 we're going to keep going with the demos， this is how far we got before we were left off with a flying number so we're going to do that and then we're going to do these other things here like our pie will be animated and are dealing the cards off a deck。

Tad back to our。Excode。Al right， here's that flying number overlay that we had。

 and just I'm going to review the last 30 seconds of the last one just to orient your cells as to where we were we added this flying number as an overlay because when we have a match it's going to do plus2 it's going to appear here and then a plus two is going to come floating up or a minus- one if we have a mismatch and it's going to go floating down。

 So of course we need an overlay of that flying number and the flying number。

 what the actual number that's going to fly is whatever that last card that we clicked whatever score change it caused So if it was a match it would cause a score change of plus2 and so we're going to fly up and if there's a mismatch minus-1 and if there's no change then it's going to be zero。

This score change function down here we're going to have to implement to keep track of what the score change was of the last card that we chose and then let's go peek over at flying number。

 this was a very simple little view， its body just has the number that's supposed to fly and it shows it as text and we learn this new thing with text that we don't have to always pass a string text sometimes we can pass a number but when we do we have to use a formatter that knows how to format that and this works for other things to dates right you can pass a date and then have a date format or there。

And also notice that we don't show any number here。

 We don't even put a text up there if the number is0 because we don't want zero flying up and down as we click here。

 just plus2 and minus-1。Let's top back to our viewer and implement this score changed thing so to do that score change。

 we have to keep track of what the score change was of the last card we had。

 which means we have to simultaneously keep track of what the change was the last time we clicked and which card caused it and whenever we have two things like that that we want to keep track of together。

One of the data structures we can use in Swift that we haven't shown yet in demo。

 but you hopefully read about is a tuple。Let's create a tuple and in that tuple we're going to keep track of which card it was the last one chosen and the score change that went along with it and it's going to be state。

 so it's little outside state private var， we call it last score change because that's what it is。

And what is its type， type tuple， here's what it looks like to define a tuple I'm going to put the amount as one of the things in the tuple。

 and then I'm going to say the caused by card ID to be you would think a string right because our cards。

 their IDs are string， and I want to keep track of the last card that caused score change by its ID but I'm not going to use string right there。

Instead， I'm going to use this type。Card dot I D。Now why am I using card。 ID and what is card。

 ID this is the don't care from the identifiable protocol。If we go back and look in our model。

At card card implements identifiable， it conforms the identifiable protocol and we know that because it's got this little ID down here string。

 if we go look at the identifiable protocol in the documentation here。

 we'll see here's identifiable that has this associated type and we know that that's a don't care and so this is a type。

 this associated type， it's a type， it's a don't care， but it's still a type。

 and we can use that type on card back here。

![](img/711a6f9e75d5251933b0dd4981118cf8_1.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_2.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_3.png)

As a type for something else and this is as I'm sure you can all agree much more clear about what I mean by this caused by card ID。

 I want it to be the idea of a card right， so yes， that's the same a string because we know that the don't care of a card when it implements identifiable is a string we know that but here we don't have to know that we can just know that this is the identifiable for the card。

So let's go back to understanding the tuple， a tuple can have any number of pieces of data in parentheses。

 we only have two but we could have more， we could have another one you know X is of type double that's perfectly allowed we can have as many of these things as we want in our tuple type and then we can assign it by of course just saying equals let's start it with an amount being zero and the caused by card ID being empty string we know that's not a valid card ID one thing when we're using tuples。

 we use swift type inference a lot for example， I would not put this right here。

Even though if I option click on this， you can see its type is a tuple right where the first thing is an ant called amount and the second one is a card ID called cause by card ID。

 if I take this away this thing right here， it's still going to think that that's its type because it's going to infer it from the initial value I gave it。

Now， another thing about tus to understand is that you don't absolutely have to have these names。

In this case I probably don't want the amount， look at the name of this var， last score change。

 this is the last score change， do I really need to say last score change amount was zero no。

 the last score change was zero and also we let to know what card caused it。

So this is kind of how you define a tuple and use it and we're going to show you down here and score change how we access the value of a tuple。

 but first let's set this var。How do we keep track of the last score change。

 or when does the score change？When we choose a card。

Let's update this var every time we choose a card。Really easy to do and create a little local hero called score before choosing and that equals our view models score。

And then right after I'm going to say let score change equal the view models score minus the score before choosing。

 does everyone agree that that's going to keep track of score changes because every time I choose something in my model。

 the score might change， maybe there's no change at zero。

 but it could change and this is a way to detect it。

Now that I have the score change and I know which card is involved here right I'm inside my aspect B grid。

 I'm obviously drawing the card with a card view card up there I know which card it is now I can say that my last score change equals。

The score change and caused my card ID， the card ID。So this is how we assign the value of the tuple。

 we just give the two things in the tuple， by the way。

 when you're assigning a tuple you don't have to put this in here。

 we could do that that would be perfectly legal， I probably wouldn't here I think it's a little clearer to go like this someone reading my code can see this line and code and say yeah well you have the last score change with this score change and it was caused by this card ID。

Now we know what our last score change is at all times。

 let's go down here to this funk at the bottom and implement that by just looking at the last score change。

 we're asking about the score change that was caused by a certain card。

 the only card that can cause the score change is the last card。

That cause the sc change any previous ones we don't really care about right we have these flying numbers。

 we don't want them flying from previous cards of whatever whenever something changes we want something to fly so we really only care about the most recent one how do I get the values out of my tuple and my tuple here how do I get it out let me say let amount comma caused by card ID ID equal the last score change。

So when you're getting the values out of a tuple， you say let and then a variable name there going be any variable name you want。

 I called it amount， it could be foo we're concerned and then caused by card ID this also is a variable when it pulls it out of here it's going to put the two values into these two variables so I'm essentially saying let amount equal the first thing in the tuple and let ID equal the second thing in the tuple。

And again， here， I don't need this name if I don't want take that out of there。

 that's also perfectly legal。And what is the score change that's caused by this card。

 well if this card's ID equals the ID of the last score change， then it's that amount。

 otherwise no change。I'm going to show you another way to access TL stuff that I don't recommend that much。

 but you'll see it so you got to know， which is I could say return last score change。Dot 1。

Equals cards， ID， question mark， last score change。0， colon0。

Now the reason I don't recommend this is this is pretty obscure to understand what's going on here。

 but dot1 on a tuple means the second thing in the tuple。

 do zero on a tuple means the first thing in the tuple。

I don't really recommend doing this there are probably a few times when doing that syntax would be good。

 but I don't generally right。When I flip these over。

 they should start showing this number right let's take a look let's try here that that obviously didn't cause a score change。

 so no number there， another one oh that did cause a score change right plus two you can all see easily see this two right there yeah。

No， obviously very difficult to see because it's orange so you can barely see it and it's small。

 I're going to zoom in so we can see it a little better。



![](img/711a6f9e75d5251933b0dd4981118cf8_5.png)

Now， can you see it？That two right there， but this is terrible this even with this if this flew up。

 we'd be able to see it better， but it's still not what we want。

 so let's go back to flying number and make this two a lot more visible look better back to flying number here。

And what can we do to make this better Well， one thing we could obviously do。

 let's make it large font so make this largest font we know up here which is large title that'll help what else can we do here。

 the color we don't want it to be orange it' going to fade into the background of everything there so let's make the foreground color we since we're changing the foreground color let's have it mean something how about if the number is less than zero。

Then let's have it be red。 Otherwise we'll have it be green， positive numbers。

 positive scroll will be green， negative will be red。 that'll be nice for the user。

 but there's lots of other things we can do to make it more visible。

 We can put a shadow on it There's a few modifier called shadow， we put whatever color we want here。

 How about black and we can specify the radius of the shadow how far it goes out say 1。

5 points and how much it's offset by x1 y1 is's going be over to the right and down one because remember positive y is down an iOS。

And the only other thing is， remember， it said two really would like it say plus2。

WellYou know when I score comes in like plus two instead of just two。

 I can do that with my number formatter up here remember this dot number formatter。

 there's something on there which is called the sign strategy that's the strategy for what sign is and I'm going to say always show the sign。

I put that one up there mostly to let you get an idea that there's an awful lot of stuff inside of SwiftUI that I'm not showing you the details of you got to start looking in the documentation for things if you have a number and you want to format it you know now that there's a number format or you're going go look that up in the documentation see what formatting options are in there and pick the ones that you want in our case we want the number sign strategy to always show the number sign even when it's a positive number。

This will probably look a lot better， let's go back here and try it again。This one。Oh。

 that's way better， much， you see the little shadow there， nice bright green， got the plus in there。

 very， very visible here。Al right， now we need to make it fly we want our plus 22 fly up when this matches how are we gonna make it fly Well。

 let's start by talking about how we can make this thing be not in the middle notice we put this flying number overlaid and of course it put it right in the middle where else would have put it if we want to have it move up a little we do that with another viewmodifier called offset dot offset so dot offset is an interesting viewmodifier。

 it offsets a view from where it would normally be placed So if it was in an Hdac or vStac right it's gonna to get placed in this right place and then dot offset offsets it from there So dot offset is like relative offset to where it should be it's different than the viewmodifier dot position that's the absolute position inside your container that it's in and we'll see that as well a little later in the quarter but dot offset is nice is this relative offset and that's exactly what we want here because we wanted it to appear here in the middle and then relative to that move up or down。

So let's put a dot offset。On our text。offset and it's x and y。

 so we don't want it to be any offset in x， we don't want the number to move left or right。

 but in y we do， and I'm going to have it be a state so Anine state private var。

 my offset to CG floatat， we'll start it at zero。

![](img/711a6f9e75d5251933b0dd4981118cf8_7.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_8.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_9.png)

offsetff of 0 means it's in the middle。 We go here， get this number back up。 You can see offset is 0。

 Let's change it to be。Minus 50。Okay， minus- 50， right， it wasn't in zero， it was 50 points up。

So we're pretty sure that this offset works， again。

 minus means up in iOS because our coordinate system is upside down。

But we don't just want it to appear， up， we want it to fly up there， we want to animate。

 and when do we want this animation to start？We want it to start as soon as it appears。

 as soon as this plus two appears here， we want to immediately have it start animating opt and as we learn in the slides。

 we can do this on appear。ViewMoifier， and that just has arbitrary code in there that we can do when this thing appears。

What's kind of cool is this says number not equals0。

 so this text is going to appear when the number is not0。Like plus 2 or -1。

 that's going to make this thing appear。And what are we going to do in a peer。

 I'm just going to say with animation。Offset equals if the number is less than  zero。

 then I'm going to go to 200。 Otherwise I'll go to minus200。Let's see if that works。Wop， what。

Really nice， and except that we don't want it to start at minus 50。

 we want it to start at zero and go up。Very nice， so that was quite easy。But。

We don't want it to fly up there and then just get stuck and sit there until we click the next card if I click another card then it's going to go away because the card went away and here we go again it actually went up off the top of the screen there we don't want it to stay we want to like fade out or something disappear how do we do fading opacity we want obviously an opacity thing here and what is the opacity that we want well when the thing first appears and it's at offset zero。

 we want to be fully opaque at one。When it gets up here we want it to be zero so really the opacity is hooked to the offset so we want to say if the offset does not equal zero。

 then we want it to disappear otherwise we want it to be there and this sounds like oh this is not going to work but remember that this is inside of with animation so this opacity it's going to change from when it first appear at offset zero up to here and that change is going to be animated so that's why it's going to fade out。

We'll see this in action。嗯。Work great little fast for my liking kind of zoom by so fast I didn't really get to appreciate the plus two that I got there so let's slow our animation down。

 we know how to do that How about something like ease in I don't necessarily want to ease out I wanted to ease in but not ease out and duration let's try 1。

5 to start see what that looks like。😊，Maybe that's a little slow but it's not too bad probably live with it for now and we can tweak these numbers over time this wants to be a constant for sure in this flying number and we're not going to do the constants here there's all these one to be constants these things even these up here want to be constant so we would create a struct with statics in it like we always would for constants Now this looks like it's working but it's actually got some problems and really don't see them we unless we back up a little bit。

So let's back up actually to see all of our cards here and watch this problem here I have my demon。

And here's this， no score change there because neither of those cards have been seen so they're not negative。

 but now I'm going to make it so that they're not seen， right， you watch this？Okay，-1 flew down。

 Now I'm going to match the pumpkin， and I should get plus2， right。

 plus2 should fly up from the pumpkin。 Here we go。 Watch this。Oh，No plus two。

Well the problem here is it's only going to show it flying number once。Why is that Well。

 the text appears sets the offset to be 200 or minus 200， then the offset just stays there。

 it never gets reset back to zero。So it never appears again because there's never any animation that's going from when this happens the next time you set the offset and it's nothing the offset has not changed。

 so we need to on disappear。When we disappear， we need to set the offset back to zero and we don't have to animate it or anything because it already will have faded out so we're not going to see it anyway。

 even if we animated it， so we'll just reset our offset to zero now watch if I do this。This guy。

We'll have him do a minus one now we're going to have this guy match plus two， and it works。

So we sometimes have to be careful when we on appear and we set some a sign state。

 we might need to reset it when this thing disappears。That was actually another problem。

 watch this problem。Let's go here。 we've seen this guy wants。

 and now we're going to see this guy again。 he's going to do -1。 When I tap on this guy。

 he's going to do -1 ready， and watch little 1 very carefully。 it went behind this card。

 Did you see that The minus-1 came out， but then it went behind this other card。 That's not good。

 Let's see that happen again， but this guy。Over here， now watch the minus1。

Behind it went behind that card。 Why is that minus1 going behind another card？

These cards are all at the same level in the UI from a ZStack right from SG now they're at the same level in terms of their priority to be there。

 but they're kind of laid out by the4 each and the aspect B grid and lazy B grid in some way we don't necessarily know for sure。

Wwhichhich ones are in front of which other ones， it turns out it looks like the ones at the beginning are in the back and the ones toward the end are in the front。

 which kind of makes sense， but we don't know that for sure， but we need to be sure。

When we click on a card and it causes a score change， we need it to be in the front。

 no matter which card it is， it has to be in the front， so that when this number flies up。

 it flies out on top of all the other cards。So how do we control the zus we do that with something called Z index。

 so I'm going to go back to my memory game here in the same place where I do my overlay。

 I'm going to say that the Z index of this。Card， this card view。

If the score change for this card caused by this card does not equal 0。

 then I'm going to have it Z index be 1， otherwise0。 Now Z index can be any floating point number。

And zero is the default， higher numbers are in front。And I can use that Z index。

 other numbers if I want to order a bunch of views in certain order。

 I can pick different numbers that have to be1 and zero。

 you could definitely set this to 100 and it would work just as well。

 so now let's make sure that worked go here look this guy okay let's have this guy be wrong minus1 it's on top because that card was the last card of have4 so it's Z index was 100 in this case in front。

I'm going to do a little code cleanup before we go here， I'm getting a little worried about this。

Functions getting a lot of lines of code is getting towards near my limit of a dozen lines of code。

 there's an obvious thing to pull out， which is this。

I'mPop this out of here and create a function called choose card。Which is a function on this。

And all that choose card is going to do is the same thing that was in there before。

 so again I'm just breaking it up into smaller pieces。The next thing I want to do is。This pie。

 you see our little pie behind the spider， that's supposed to be a countdown timer。

OkayI have it set to be in my code here that you're going to see six second countdown timer。

 and I'm going to give you one extra bonus point for every second you have left。

So if you match them really quickly， you get a lot of extra bonus points。

 but if you take a long time then that little pie takes down， you lose all your bonus points。

 so there's one point per second you have left， but clearly this needs to animate to show that happening。

Now， that bonus scoring is part of my model。So， all the logic for。

What the time is and how many points you get， that's all in my model。

 so let's go over to my model and put it in there。And it's in my card。

 something about a card because it keeps track of how long the card has been face up and the longer it's been face up。

 the less points you get and I'm not going to show all this code and type it all in I have a little code snippet for it。

 you can go look at this code afterwards I'll post it on the forums there。

 but here's basically how it works， it's in this section I just put in here called bonus time。

And you just call this function start using bonus time every time the card goes face up and then stop using bonus time every time it goes down not just causing the card to keep track how long this thing is face up and then once you do that you get this nice little var here bonus that's how many bonus points you get if this card is matched and you can see that it is just the time limit  six seconds times the percentage you have remaining so you've got 50% of the time remaining。

 you get three points and then there's this bonus point remaining。

 it's just doing a little calculation right here to say well how much time have you used how long is the card been faced up divided by how much time you get。

You get six seconds to get a bonus if you don't match the card within six seconds。

 you get zero so now we're going to use this code。In our model。

 first thing we're going to do is when is face up happens。

 we're already doing something on his face up， which is keeping track of the has been seen when we turn face down。

 but now I'm also going to say if I is face up goes true then I'm going to start using the mode time。

E， if it goes space down， I'm going to stop using the bonus time。

Here we're using property observerserv again， really good use of that and same thing with matched when we're matched。

We want to stop using the bonus time there too。That's it。 So I've got my model now。

 with's keeping track of how much bonus you get here。

 Let's go up to our scoring and add this scoring to it。 So here's where we have a match Scs plus 2。

 In addition to the two points。 you now get the cards。Chose an index， dot bonus。

 and also the cards that potential match index， which was a match。Dot bonus。

There we go it's all I have to do in my model to keep track of this if you match the cards quickly。

 you're going to get a lot of points and you're going to see this because our flying number。

 it's not going to just be plus two， it's going to start saying plus seven plus 10 if you match them really maybe plus 12 if you just go really quick match them right up so we'll see that happening。

LetsGo back to our memory game right here， how can we see it。

 how do we visualize what's happening in our model， but we have the pi in our card view。

Instead of 240， we want it to be our cards bonus percent remaining times 360。There it is， it's 100%。

 it's not moving though we haven't put any animation in so it's not moving but it is happening because watch this let's go over here。

 go here and go back， look when the card flipped straight up。

 it showed that it had seen that card a little bit same thing here back very little left here， here。

 if I go quickly。See how these cards are actually showing how much is being used。

 it's just that it's not ticking in real time， it's not animating it in real time。

Now there's a couple of ways we could do this animation by far the simplest way is to use something called a timeline view。

 so timeline view is a really simple view that just takes whatever view builder you give it and it does that animation thing where it slices it up into pieces and calls you repeatedly。

Exact what we're going to do we're going to take our entire pi and just put it inside a timeline view a timeline view takes an argument for how often you want to do it like we could do it every minute that would be useless in our case because our thing only takes six seconds。

 but it has a great one called animation and the animation one。

Thinkyns up how often it calls this with the animation passes that it's making。😡。

So when it's doing animation， we know that it slices it up into pieces。

 well that same kind of piece slicing rate， whatever that is。

 that's what the animation timeline does We just put our pie inside there and。Look at that。

 timelining it down。The bonus time percentage is changing in the card because the card is keeping track of how long it's been up and the timeline view is redrawing it repeatedly。

And you can control how fast it redraws to， you can say minimum interval， for example。

 let's say one fifth of a second Now when we click see how it's kind of chunking every fifth of a second。

 it's doing it， which is nice， that's going to use less of your battery， essentially in your phone。

 we haven't really talked about performance and all that， really using a lot of CPU。

Forget that you're using the user's battery the more you。

Cank that CPU up and start drawing a lot of things， you're using their battery faster and faster。

 you might decide that it really is not that much more valuable for them to get a smooth turn here versus a chunk one or maybe you make a compromise and say well I'm going to let it chunk。

 but it's going to be at this rate。But you might decide that's distracting and you want to be smooth so make it smooth if you're if you need it。

 but you do have control of how much you can do it so we'll go ahead and let the animation system pick the right for us there notice also the timeline view gives you an argument you see that timeline let's take a look at that in the documentation here。

This is the default one。

![](img/711a6f9e75d5251933b0dd4981118cf8_11.png)

Good look at what a。Timeline context is。And one of the most important things in that timeline thing that gives you is the date that's the current date of。

that the slice happened that it drew that for and so you can look at that date now we don't need to look at that date because our model is really smart it knows how much time has been consumed it can tell you that at all times。

 but you might have something where you want to based on how many seconds since the last time you drew it or whatever。



![](img/711a6f9e75d5251933b0dd4981118cf8_13.png)

You don't usually need that cadence and stuff very much a lot of times you're just doing this animation thing and putting your view in there。

 you wouldn't want this to be really expensive to redraw。

 which ours isn't that pie drawing a shape is like very little CPU usage。

 but you wouldn't want to build some gigantic you know。

 if you're doing some you have a research project and you're doing some gigantic data process and you wouldn't want to do that in a tight loop inside a timeline view。

 you't want that data to be quickly available to it。While we're here。

 let's go ahead and clean up some more because look at this one。More than 12 lines， I don't Yeah。

 I think so right， maybe 13 or I can't really tell it。not good。 in any case。

 this whole thing definitely wants to be its own that many few modifiers on something。

 so I'm going to take that out of there， create a little v here， I'll call it the cards contents。

 some view。Put that back in here and then the overlay is the card contents。Or that。

One thing I'm going to pull out here is this padding of the pie inset。

 that's not really part of the card's contents， that's more up here as part of the layout of that whole thing so I'm going to put it up there really where it semantically belongs。

Someone also asked me， hey， does overlay have to just be a single view like this and if there's no overlay could be a normal view builder？

Like this。All the overlays we've done just happen to accidentally， I guess be these single views。

 a lot of times they might be single views because you're doing what we're doing here and pulling the view out into its own v like this。

Remember this thing dot transition that I talked about。

 which is the coming and going of views when they come and go and animating that let's try and do something here that helps us see that visually what I'm going to do is the disappearing of the cards when they match。

When we click on cards that match these two guys， when I click on the next card。

They simultaneously flip and fade， which is actually kind of weird because the fading of the flip kind of breaks the illusion of the flip。

 so we don't really want that。And I'm going to do that disappearing of the card。

Instead of using opacity here to make the cards go away。

 I'm going to actually make it go away I'm going to make this card actually disappear I'm going to take this same if that we had right here。

 Im going cut that out of here， get rid of the opacity， no more opacity。

 instead up here I'm going to say if that thing， then draw the pie。This pi is the carddified pi。

 you see there's cardified at the bottom so this is the whole card， I'm just not going to draw it。

 so that pi Cardified pi is going to disappear from the UI when it's matched and face down。

So here we have a case of a view the Carified pi leaving the UI Now when I do it this way。

 look what happens right I'm going to do a match， I'm going to click and we're going to make it disappear。

 watch what happens。It still fades out Now it is better because it didn't do the card flip。

But it still fades out， let's try this one， ready。Fade oh oh and even worse it removed the whole view and now our thing collapsed back up。

 which is why we did the opacity in the first phase and remember way back just lecture two。

 we made that the opacity so that it would keep the space when it wasn't there。

So in some ways we've made things better here， in some ways we've made things worse and in some ways we haven't changed anything right we haven't changed anything because the opacity is still happening somehow。

 even though we took opacity away， we made it worse because it collapses like this。

 but we've made it a little better and then it's not doing that card flip anymore it's just making the cards disappear So let's try and understand why all these things are happening here first let's talk about the fact that it's consuming the space Well when you take that view out of there。

 our little aspect B grid says， oh okay well minimum width be damned this thing has nothing to draw。

 it's an empty view， there's no view there that's a simple one to fix in another way besides using the opacity trick was just to say color dot clear。

The color dot clear is like saying rectangle dot foreground color。

Clear clear is clear and that is going to make a rectangle that's going sit in that space that you can't see。

 so watch this at this。 And when I match disappears and now there's a clear rectangle here You can't see it It's clear but it fills that space that's a simple way to stop that collapse views are still coming and going here the cardified pi is still disappearing Now what about the opacity Why is it when I click here fading out still how could it possibly be fading eye there's no opacity for the carddified pi I've got the opacity you know from my little countdown timer。

 but that's a different opacity I deleted that opacity that opacity is coming from this。

Dot transition， dot opacity。Oacity is the default transition to use when you remove or add a view to the view hierarchy since it's the default。

 it's just like you have that on there。 And if I click again， click match。opacity， it， it faded out。

What if I change this， how about scale， remember scale is a different kind of transition。

 that's a transition that makes it go from big to small or small to big。See what happens here。Good。

 do you see that zip down？So we just used a different transition there to make it disappear。

And this transition mechanism is a really cool way when you have a view that you want to wholesale。

 disappear， or appear， or fly away or something like that in your UI。

Ex we're going to do more transition， but I just want to do a quick intro here that's really clear what's happening。

All right， last thing I want to do here is dealing the cards out and dealing the cards out involves a number of things going on all at once。

 And the first thing weve got to think about a little bit is how。

Do we want to kick off the dealing of the cards and I'm going to start by having the dealing of the cards happen when the game appears。

 What if I wanted them to deal out like a dealer deals cards in Vegas I want that kind of animation。

 How would I do that Well the first thing I have to do is make these cards appear after its container is already on screen because if if the cards container is not already on screen。

 you will not see any animation of them coming on screen because they'll come on screen with its container and what is the cards container it's our aspect via grid。

 which is got a lazy V grid。 that's the container So we have to make that thing be on screen first。

Let's talk about how we make this work。First thing I'm going to do is I'm going to say when my aspect v grade of cards appears。

 then I'm going to deal the cards out。So I'm going to let my aspect G grid appear and then once it appears。

 then I'll deal the cards because then I know it's on screen， the container is on screen。

Dealing the cards is not part of my model。 there's no part of the memorized game。

 which is dealing cards， the game has just got the cards， so the dealing is purely a UI thing。

It's the UI that wants to present this game by dealing the cards out to you。

 So we're going to need some outside state。To represent these cards and whether they're det or not so I'm going to create a little private v and call it Dlt and it's going to be a set of these card IDs。

 again， I'm using card ID there instead of string and I'm always using the IDs of cards of course。

 because the cards themselves are copies。This is a value type， so it's copied。

 whereas the card ID is a unique identifier for the card。And this little set。

 if a card ID is in this set， then the card has been dealt， otherwise it has not。

Notice I started empty， that means none of my cards have been dealt。

Now once I have this nice little Asine state data structure， I could create little functions like。

 is this car dealt， I could return a bo？And this is just going to say Dlt contains that cardss ID。

 or I could have another nice little far called Undalt cards， which returns an array of cards。

 and that could just be my view models cards but filtered so that I'm only showing the ones that have not been dealt。

See how I can use my little private bar delt here to create some semantics about whether the cards are det or not。

And it's important to understand that this is at sign state。

 I told you we don't really have at sign state and views。

The only at sign state we have is temporary state UI oriented state。

 well dealing the cards is a UI thing， it's not in your model， it's not part of the game。

 it's purely part of the UI。😡，So this is a great and obvious use of at sign state。

 so now I can find out whether cards are dealt what I'm going to do is go up here to my aspect V grid and I'm only going to show a card if it's been dealt。

I'm going to go here and say， if is Dlt this card， then show my card。

Notice that I'm using an if there， so when the card is not dealt， it's not on screen at all。

 this view is not even on screen at all。😡，And when it gets dealt。

 if I ever put it inside of this set， then it will appear on screen。You can see no cards， right。

 no cards over here because none of my cards have been dealt。All right， so let's deal our cards out。

 let's do it right here， says deal the cards， I'm going to do it animated。

 so I'm going to say with animation。And let's do a slow animation so you can see it how about ease in out duration of maybe two and what I need to do just for card in my view models cards。

Dalt。 insertsert that card's ID。I's going to put them in my set。

 that's going to cause those cards to be dealt。And looks。There they are。

 but we have a serious problem here now。 we've reached a limit in a way of the previews when you start doing animation like this where things are happening on a appear and all that。

 you can't really use your preview。 It will not show it for example。

 if I restart my preview by clicking on the live button。 Look it didn't do it。

 it just they were already there so it left them there。

 and it's a little bit about how the architecture previews work。

 So this is a case where we have to use a simulator。 we've gone this whole quarter。

 we never use a simulator。 I know some of you have used it because you're not on the latest Xcode。

 but we've had no reason to do it。 and now I'm going show you what it looks like to use the simulator。

 and it's a couple of things we're going to do here。 one is let's close the preview。

 we're not going to use that。 I'm going to take this out of full screen mode。



![](img/711a6f9e75d5251933b0dd4981118cf8_15.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_16.png)

And here's my simulator over here， see I'm going to do something really cool， so watch closely。

 I'm going to say window tile this on the right side of the screen。And when you do that。

 it's going to on the left give you all your other windows that are up and say which one do you want to be on the other side。

 and I'm going to want X code。 And now I get this nice tiled view between these two。Apps。

 and this will stay on screen for me。Now， if I run。



![](img/711a6f9e75d5251933b0dd4981118cf8_18.png)

Ooh， you see it deallt the cards， Okay， well now it dealt them with opacity because that's the default transition。

This view came on screen and it had the default dot transition dot opacity。

 and that's why when I run and my container appears， I get to fade in。

 so my cards were dealt by fading in。

![](img/711a6f9e75d5251933b0dd4981118cf8_20.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_21.png)

I could definitely control that。 What if I make this one scale， just like I made the other one scale。

 How about that。Here come my cards scaling in， or I could do something even cooler how about this transition。

 there's one called offset。Offset lets you pick an X and Y to offset and it's like where the card will start from。

 and then it'll go to where it wants to be。 So let's say x。

 how about Cgflow do random and minus-1000 up to 1000 and same thing for y copy and paste even pick a random position random x and y probably going be off screen for most of them because 1000 is pretty far screen by the way is you know on an iPad it's maybe 1200 by 700 or 1400 by 900 and then on an iPhone is that I maybe 400 wide by。

I don't know 800 high something like that， you never know and you don't care because notice we don't ever have to know that。

 but1 thousand is pretty far， let's see what this looks like， this transition。

They're the other they coming from some random place and coming in。

 So I'm controlling with transition how this card view。

Appears on screen and it appears once it is dealt and it's only happening here because if I didn't have this with animation。

 then it wouldn't do this because of that explicit animation causing that transition to get animated。

right so that's step one of understanding what's happening here。

 those things are appearing on screen now that's not quite what we want。

 we want to have a deck of card somewhere and when we I'm going to make it so when we tap on the deck of cards it feelss them out。

Let's work on getting a deck of cards on our screen and then we'll try and sync them up so that they're transitioning together the deckca cards pretty easy to implement。

Probably all imagine what this is， let's say bar， private bar。Deck， which is just some view。

And a deck of cards is really just a Z stackack of cards， so I'm to say ZStack for each。

And which cards are in our deck are undalt cards， see the undalt cards right above there that I created earlier。

Card in。We're going to draw it。With the same card view that we drew the other one。

Here' is one thing I do want to do with this， though。

 is I want to explicitly give it a size and this。Little view modifier that I'm going to show you today。

 dot frame， easily abused， be very careful of using this one what is frame about。

I told you that views get to decide what size they want to be remember that well they can do that with frame but frame is not really going to size the thing itself。

 it's more like a create a container that's that size and the thing then is offered that space remember how in layout you get offered space you size yourself to go in there so frame will offer you space now a card view uses all the space offered to it So if I say frame oh let's say with。

My deck width， I'll make a constant for that and the height then would of course， be our deck width。

Divided by our aspect ratio， right， That would be its height。 if I said that。

It would make a little container that that size and our cards would draw the whole thing and that's exactly what I want here。

 but there are other things you can do with frame frame is one I want you to go in the documentation and look at。

 for example， you can specify the minimum width。You want or the maximum width。

And height so there's other things you can do in frame besides just specifically picking one Now the reason I say it's easily abused is that look how we've been programming。

 we never picked the exact sizes of things we just put them in v stackax and the H stackax and they just lay themselves at vast V grids and all the only time we ever picked the size was when we picked the size here that fit this space and even then we used a geometry reader to see well how much space do I have and then I divided it up so even then I was kind of reacting how much space I was given here I'm picking a specific height let's go ahead and make a little。

Constant for that private let deck width to the C float let's say 50 or something like that I'm picking a specific height you don't want to do this very often now why am I doing it here because I actually want this thing to be this little size no matter what size my card is。

I want the deck， I'm going to put it right here that I have a nice little open space to put it right here and put it here and I want it to fit in this space kind of nicely even if my cards are huge because I only have you know four pairs or something like that or even if they're tiny。

 I want it to be here。If you find yourself doing this frame width and height。

 really think is that really what I want here and I'm doing it in this demo mostly to show you what can be done。

 but you will have entire apps where you never do that， never pick as a specific height and width。

Right now I deal the cards out when my container appears。

I'm going to change that so that I deal them out when I tap on the deck。

 so I'm going to change this to on tap gesture。I do the exact same thing。

 but I'm going to do it when I tap on the deck instead of when my container appears。

Let's putut our deck in there。 I told you I wanted to put it between the score and the shuffle。

 Here's that H stack of the score and the shuffle。 my deck right here， put a spacer。



![](img/711a6f9e75d5251933b0dd4981118cf8_23.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_24.png)

So here we go， Ron。

![](img/711a6f9e75d5251933b0dd4981118cf8_26.png)

All right， there it is， little deck that looks about 50 wide， it's there。

 it's black because I didn't set it foreground color to orange。But。Tap on it。Ooh。

 it made all my cards come in now the cars didn't come from here。And what happened to the deck。

 what can anyone tell me why that deck disappeared。Exactly。

 because there are no more undt cards if you look down here in our deck。

It has a ZStack of the undelt cards and as I added all the cards right here。To dealt。

 the undalt cards disappeared， they were gone and so these views in the deck， what happened to them。

 they transitioned out and they transitioned with opacity because that's the default transition so watch again the deck when I click on it it's going to disappear with opacity。

谁。That's good now I can control this card views transition as well， in fact。

 let's go ahead and put the same transition on those card views as is on this one in other words random transition now these cards。

 the undalt ones are transitioning out the cards up here are transitioning in but they're still transitioning both them are still transitioning so if I use that crazy all over the place transition it'll work for the cards too watch this。



![](img/711a6f9e75d5251933b0dd4981118cf8_28.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_29.png)

They went off random place thousand， plus minus0 out there too。

Now this is clearly not what we want however， we want these card views to match the geometry of those so that the cards fly from the deck up to where they're supposed to be and that's this thing we had in the slides called matched geometry effect we want the geometry which means both the size and the position to match between those and as one is leaving and the other one's coming out their geometryries we'll get。

Automaically animated to match each other。So let's do that of having this crazy transition here。

 let's use a。Matched geometry effect。And match geometry effect once an ID that's to identify this view so it knows which other view to match it with Well this card view right here is showing that card。

 so card do ID is an extremely good way to identify this card view it's the card view for that card and we need this namespace and this namespace is not important for us because we only have this one thing going on but it's important for you in your assignment4 because in assignment4 I'm going to ask you to do dealing the cards out in your set game and also discarding them。

to a discard pile， so you're going to have both a deck and a discard pile。

 so you're going to need two different namespaces so that the card IDs。

 it knows whether you're talking about the view that's coming from the deck or the view that's going to the discard pile。

So how do I do a namespace， it's really easy， you just make one up right here。

 I'm going to say@ sign namespace private bar， we'll call this my dealing namespace。

And then I just put right here， dealing namespace。 Now as I said in the slides。

 you don't have to say dealing namespace， colon namespace， the at sign namespace。

It is kind of like at Sign state， but it's a different one at sign namespace。

 it knows that it's always creating namespaces there， that's what it does。

 so you don't need to put that on there。Well here's one match geometry effect。

 I always need the matching one， so let's go up here to this card view get rid of its crazy transition instead put。

It's match geometry effect and it has the same card ID there and in the samespace。

 if you don't put in the same namespace， obviously they're not going to match。Let's try it。

Here we go。Oh。Well， yeah， kinda， a little weird because。

They started out black and then they kind of faded to be orange。 Did you see that，'s see it again。

 they did match their geometries， but they also are still doing this fading business。

 this guy has transitional opacity， so he's fading out These guys have transition opacity。

 they're fading in。 that's not really what I want。And the lesson here is dot transition is still in effect。

 even if you do match geometry effect， that is going to match the geometry。

 but the transitions are still there。Now that's not what we want here。

 we actually want when we click on this it to immediately just start showing me my orange cards as soon as these disappear。

 we want them gone， we want these ones to start to immediately appear。

So what does anyone remember what the transition you use is if you don't want to。Thing to happen。

 No opacity or scaling or anything or anyone remember。Identity， yes。

 so what happens if I go here and say？Dot transition， the identity transition。

 and we'll do the same thing。For our deck。Now it should work， right。

 because they're not going to do any fading or any other kind of transition， let's see what happens。



![](img/711a6f9e75d5251933b0dd4981118cf8_31.png)

Here's our deck and tap。 whoa， we lost our entire match geometry effect。 They just jumped。

So the lesson here is transition identity means no transition at all， not match geometry。

 nothing now we're in trouble， how do we stop this。

 well there's a really important little trick to know， which is that we can create an asymmetric。

Transition that is identity for insertion and identity for removal。

 which you would think would be exactly the same thing as transition identity right identity on both sides inserting the view and removing view but this does not override the match geometry So if you want to do match geometry and you don't want any other transition you have to use one of these asymmetric insertion removals and I need to do that with both my things here so let's go back up and do this one。

And。Run。And。Tap right， that's what I wanted， I tapped on this immediately turned to the orange cards and they started flying up here that's exactly what I wanted。

I don't want this deck to start out black， though， I want it to start out orange。

 I'm going to go up here to my deck。And set its foreground color to my view modelss color。

Just like I do for my cards， I'm going to do it for my deck as well。

Probably would make it look the same by doing that or something。

We're almost here with the dealing of the cards， but a little more to do， try this though。Yes。

The only thing about this is I don't hear any of you complaining。

 but I've never seen anyone a Vegas deal like that oh let's deal throws all the cards that'd be awesome dealing though if you just throw perfectly throw them out there you'd be a great dealer in Vegas you'd be like a sideshow dealers deal by dealing one card at a time right flip them out there so we want our deal to be exactly the same way how are we going to do that because we are throwing all of these cards out there at once when we click on the deck here we got this four loop we're dealing all the cards all at once。

Well that's okay we can keep doing that remember that animation doesn't show us what happens instantly it shows it over time so all we really need to do is delay the animations of the subsequent cards by a little bit more each time so that we're still throwing all the cards out there but we're seeing it more and more delayed with every card that's really easy to do I'm just going to go here and put the card。

For loop around the outside here。And I'm going to create a delay， which is a time interval。

 and we'll start out with zero， no delay， and then when we do this ease in these out。

 I'm going to say dot delay this by delay。Starts out zero， and then each time through the loop。

 I'm going to say delay plus equals， let's try。A quarter of a second every card we're going to deal the next。

 a quarter of a second later， and it's taking two seconds to deal each card。

 So this is going to be kind of a slow deal。 Now when I do this， I get this really annoying error。

Result of call to with animation。Is unused。 Why is it saying that that's just ridiculous I didn't do anything。

 and now it's saying this。What does it mean here well， with animation。

For good or for bad has a feature， which is that it returns whatever this returns。

Whatever your closure returns in here， the width animation will return it too。

And why is it doing that it's because this has an implicit return we know that if you have a closure with one line that its got an implicit return and insert which inserts something into a set。

 insert actually returns something I don't remember exactly what return returns actually a tuple I think of I don't remember something that I don't care about that it's returning and this return is just implicit because this is a one line or closure so how do we get rid of this underbar equals。

Wwhichch essentially says， give me what that insert gave and then just put it nowhere and put it in the bit bucket right underbar means nothingness。

 this is a way to get rid of that warning， another way to do it would have been to put this in a function that doesn't return anything。

 that would have been another way but this is kind of nice simple way。To do it there。All right。

See if that works。Yeah。And a little。Kind of slow but it definitely doing what we want right it's delaying each card animation let's try and clean this up a little bit to make it work a little better。

 One thing is we don't need to take two seconds to animate the card to me I think one second might be enough and this 0。

25 maybe 0。15 would be enough， by the way， these one to be constants and I'm going go and make them constants put them down here private bit let deal interval。

Is a time interval。0。15 that's this thing right here。

 the interval and I'm even going to have this whole thing right here be a constant。

 I'm going to call this ideal animation。Put this down here， private let deal animation。

 it's an animation， of course， equals that thing。 and these are all constants。

IPut them up with my other constants at the top and you can already see it's about time to start putting this in a struct。

Constant struck， I'm really getting to the point where I have so many constants that you really would want and you know。

 these ones would want to be you know an animation substruct probably all kinds of nice stuff but we're not going to do that but you get the idea。

AllRight。So let's try this these numbers。That's pretty good。 That's pretty good。

 I think it could go even faster， probably， you know，0。5 seconds or whatever。

 so you can play with that and maybe we want to play with the easy in these out like。

But probably for sure want ease in， but maybe we don't want the ease out or maybe we want the spring right we're throwing them out there and when they land where there's a little bit of dampening they would land you see you know remember they interactive spring。

 maybe that's what we want so we would play with that and get it to be what we wanted。

I'm going to clean up again， I got a little clean up to do which is this whole thing。

 this is getting to be more than 12， let's just take all of our deal to cards and turn that into its own little deal function。



![](img/711a6f9e75d5251933b0dd4981118cf8_33.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_34.png)

Don't need to comment anymore， we know that we are dealing that's the name of the function even。

That is it not only that is that it for animation， that's it for memorize in class it's not it for me memorize for you although because assignment number six is going to be back to memorize one thing I'm going to be showing you in the next two weeks is how to build apps that have editors and more than one page right RFf has this one view that's it You can't navigate to anywhere else we're going learn all that in the next couple weeks so you're going to come back to memorize and you're going to have your themes be something you can edit and add new themes and choose them and all that so you're going add a whole UI for managing and editing your theme so that's going to be your assignment 6。

Okay， your assignment four is to animate this， your assignment five。

 just to preview that for you is going to be about multitouch。

How to deal with taps you know how to do taps with on tap gesture but you want to be able to do drags and pinches so that's what your assignment five is going to be about not in memorized though that will not be im memorized it's going to be a different app I'll be showing you in the next couple of weeks。

I think we accomplished everything we wanted to memorize and I don't see any of these that are more than 12 right。

 nope， nope， none of these are more than 12， so that looks good and then in our card view nope。

 none of these flying number Oh that's close， flying numbers is getting close。

 but it's probably okay here。

![](img/711a6f9e75d5251933b0dd4981118cf8_36.png)

![](img/711a6f9e75d5251933b0dd4981118cf8_37.png)

Cardified that looks good。

![](img/711a6f9e75d5251933b0dd4981118cf8_39.png)

Probably the one this longest is right here， the logic。

 the true logic of our playing our entire game， and it really started getting along once we added all the scoring。

 look all this is all these lines of code are all having to do the scoring。

 maybe we would want to put that off into another function。

 calculate score based on matching cards or something like that。



![](img/711a6f9e75d5251933b0dd4981118cf8_41.png)

But we've done a pretty good job of keeping everything simple and I really want you to endeavor to do that for the entirety of your Swt UI programming career。

 not just in this class。

![](img/711a6f9e75d5251933b0dd4981118cf8_43.png)