# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p05 -05-Lecture 5 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p5-

So we have more demo today to start continuing the demo when we started before。

 and then I am actually going to go to the slides， we're going to talk about this enome type。

 the last thing there that we didn't talk about when we talked about the type system。

 and we're going to talk about a specific type， which happens to be an email called optional。

 really very， very important type。And then back to the demo。

 and we'll finish up doing the game logic for our app。Before I kind of continue from where I was。

 I just want to take just a second to really clarify the difference between Asign observed objects and assign state object covered that at the very last。

Bittter before， and maybe the best way to think about it is in terms of two things。

 one is lifetime and the other one is scope。The lifetime of a variable is tied to which of these outside sign things you use。

If you use assign state inside a view right here， assign state or assign state object， either one。

 then that variable is going to come into existence when this view comes on screen and then as soon as this view is no longer in the body of some other view then it's just taken away so it lifetime it's tied to the lifetime of the view's existence in the UI if you put the state object up in the app。

 then obviously the lifetime of it is the entire lifetime of your application and that's why says sometimes you would have state object in a view because you have views that when they go away you do want that view model and everything about it to just kind of disappear and other times you don't。

Like in var， the outside observed object just has to do with the paying attention to something changed thing this is not really something where there's a lifetime here this var is something you assume someone will pass into you so the lifetime of it is whatever they have the lifetime right whatever but comes from my app then the lifetime is of the app it comes from another view then the lifetime is of that other view when you have an observed object the life is coming from somewhere else。

The scoping side of this is if I do an outside state object at this point， for example。

 then I can only use that thing in this view or in any view it creates in its body or and cascading down to all the views creating all the bodies of the things down there。

 I can never use it to a sibling view of mine。Because when I put outside data I'm being here in my view。

 and it can only be used in the construction of my views。

That's the thing to think about too whereas again observed object it was passed into you so it might be passed into your sibling as well by someone else and then one other thing I want to look at is this thing down here。

 the preview we do a very strange thing here We don't say outside state object line observed objects or anything we just create this thing right on the fly here and the scope of this is every time this line of code is executed it creates a new one because look open parenthees closed parenthees means create one of these。

Now， for your preview， that's okay。 You probably wouldn't want that everywhere else in your app every single time it comes through its it's creating a new view model。

 but it's okay here because this preview is getting recreated pretty much every time we touch our code this line of code is getting executed if I change something about the size of this or Vt basing whatever it's gonna to run that line of code again。

 new view model that's why it resets all the cards being。Unshuffled or face down or whatever。

 because that line of code is creating a new view model， new model， all new that makes sense。

 so you would never do this creating things on the fly except in your previous。All right。

 so let's continue I told you that I'm not going to show you animation this week。

 I'm not going to show it next week even after we'll spend the whole week learning about animation。

 there is a lot to learn about animation animation is super important in a mobile app okay on an iPad or an iPhone very important to have good animation。

 but I am going to show you a little animation today just for fun I'm going to show to you because it's going to lead us down the path of having to do protocols protocol conformance。

Care little bits on our don't cares。 That kind of stuff。 It's going to lead us down that path。

 So that is the reason I'm showing you an。 What I'm going to do here is add some animation to our cards。

 This is our cards。 right here。 you see that's scrollview Vt。 That's our cards。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_1.png)

It's this little guy down here， this lazy V grid and I'm going to say on my cards。

 I want some animation and I'm going to use the default animation we'll talk about all kinds of the other kinds of animations we have and this kind of animation and this is only one kind of animation by having a view modifier see this is a view modifier is modifying this view to give it animation it has an argument there value and what that value is anything you want any variable you want and it's only going to animate things going on inside that view if this value changes。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_3.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_4.png)

So this is really telling what do I care about here to cause animation to happen with our cards now with our cards it's really viewmodel do cards essentially when any of our cards change we need to animated that's why I'm putting the value here to be viewmodel do cards so if our viewmod。

 cards changes then any of those changes that happen to be animated inside here it's like when I hit shuffle it's going to animate the cards moving shuffling。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_6.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_7.png)

When I did that， though。You can see I got this error， and this is an important error to understand。

 Let's take a look at it。 It says referencing the method animation with value on an array。

 which is what asked there， requires that memory game of string。 card conforms to equtable。

SoIt's too bad I can't see this at the same time， but that's what this red thing says。

 it's saying that。Doing this requires that memory game of string。

 card has to be equtable Why is that Well we think about it's obvious in a way the animation system wants to see if those cards had changed so every time something changed happens it's like it grabs a copy of it and then when something' changed happens again it gets another copy and then it says are they equal equal and if they're not equal I need to animate。

That's why it wants to be able that equals equals this on the next pass of things changing Now array knows how to equals equals equals equal is not built into the language in other languages equals equals is like a fundamental thing in Swif。

 believe it or not equals equals is's just a protocol just happens the function equals equals is actually just a function in a protocol and array implements that but arrays version of equals equals only works if the things in the array can be equals equals right Otherwise how can the array do it That's why this little error here。

 which I'll put it back up in verbose mode。Sa this card has to conform to equtable So we're going go do that。

 This is a good opportunity for us to learn about making things conform to a protocol So' go back over here to our model。

 this is our model recognize it right and we have our cards this is the thing that the animation system is saying please make this equtable So I'm just going to say sure it isequtable it behaves like an equtable conforms to equtable Now when I do that get another error here。

 what is this error says type memory game card content card does not conform to equtable So just because I said that it conforms an equtable doesn't mean it does just like when we think that something conforms to view behaves like a view we have to do bar body some view So obviously we have to do something for equtable here and I'm going to choose the fix to make it give me protocol stubbs essentially it's going to try and help you say well here。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_9.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_10.png)

The thing you need to do if you want to be equtable by the way。

 this does not always work some pro are a little more complicated than others and so it doesn't work。

 but with equtable it will always work so I'm going to hit fix。And it gives me the thing。

That is required to be equtable and sure enough it's a funk， a static funk。

 so this is a global equals equals that's because we want anyone globally in our whole app to be able to equals equals two cards and a private。

 so it's the static funk called equal equals and it has a lefthand side。

 which is a card and a right-hand side， which is a card and returns a bull whether those two things are equal。

Make sense just going to be more straightforward and this is a little verbose that it's saying memory game card content I's starting to get rid of that no reason for that we know the context that we're in here。

And so this is the simple function that we need to implement。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_12.png)

This is easy to implement， I'm just going to say。Return the left hand side is face up。

 equals the right hand side is face up， and the left hand side matched equals the right hand side is matched。

 and the left hand side's content equals right hand sides content。

Does everyone agree that that's probably going to say whether this card。

 which has these three things， is going to be equal to another card， of course？

But we got a problem here too chasing problems what does this one say referencing the operator equal equal onequtable requires that card content conforms waittable because I just said left hand side content equals right hand side content。

 what's the type of these two things card content or don't care。

So that's a bit of a problem and why is this happening well card content is a don't care。

 it could be anything， it doesn't have to be something to implement Etable。

 it could be who knows what it is， we don't know what it is and we don't care。

 but actually this is making it so now we do we do care here because we need to do this we can't say too cardequtable unless their content is the same。

So what are we going to do here because we don't know anything about card content？



![](img/0d8de5d38475531ffb42f5d3d8445d0b_14.png)

Well we're just going to go back up here to our where we say or don't care。

 we're going to say where card content conforms to equtable。

We've just made our care now B a care a little bit， we care a little bit about the card content。

 which is to say it can be anything you want， but it better beequtable。Understand what we did there。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_16.png)

That has solved our problem if we go back down here， look。

 no error because we know that this card content has to be equtable。

Now another cool thing about Swift is when your equals equals looks like this where you're just comparing each thing。

 you don't need it。Swiift will synthesize it for you so I can actually take this and delete it。

And it worked just fine。So it no longer says， oh， wait， you don't conform theeququatable。 It said。

 oh， I see all your vs happen to be equtable so I can make you equtable。Now。

 the next thing we want to do is go back to our。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_18.png)

View and let's see if that worked because this is not complaining anymore， this is now equtable。

 it's an array of equtable things now， so can we hit shuffle and get it animated， let's try it。

shuffle哦。It kind of did animate。 You see that。They kind of faded， they're fading in。

 fading in and dissolving in and out。Now that's not quite what I wanted right。

 I want the cars to move right to fly around on the screen。

 why are they not flying around on the screen， why are they just like replacing each other fading in and out？



![](img/0d8de5d38475531ffb42f5d3d8445d0b_20.png)

Well， that's because of our for each， this four each is not quite right。

We are for eachching here over the indices into this card's array。This is going card0， card one。

 card2， card3， card4， card4 in order right here and making a view for each one。

 this card view right here， that's what it's doing When we shuffle the cards around。

 we move one of our cards from number7 to number0 and the one from0 goes to4。

 but from the four each point of view it's still showing the card at index 0。

 it happens to have changed out from under it， but it's still showing this zero card that's why it's fading in the one that has been moved in there。

 we just keep moving it。The problem here is that we really want for each to not for each over the indexes of the cards。

 but over the cards themselves， we want it to associate this view with an actual card。

 so when the card moves in the array， the view moves。

So how do we make that association between this view and the actual card instead of its index。

 this association is its index here。This is actually incredibly straightforward and really。

 this is the way for reach is meant to be， which is that instead of saying the cards's indices。

 we just say for each over the cards themselves。If we're going to change that to card。

 this doesn't want to be index， this wants to be card。

 and then this card view we want to pass the actual card， Everyone agree with that。

 we're not doing the index anymore， we're going to pass the card in there。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_22.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_23.png)

Now this almost works。 It's got two small problems one。This error here。

 genericstruct for each requires that memoryga。 card conforms too hassable， okay。

 that's another yet another protocol。The reason saying that is because of this ID self and I promised you I would tell you what this ID self is and the time has come。

 what ID self there means is I'm for each I'm trying to identify each of the things in here as an array now it was arranged before。

 but I'm trying to identify each one of them so I can you know hook it up to this view。

 what should I use to identify these things。And Ivy self used the thing itself。

That works great for an int like int 0，1，2，3 having zero works。

 although that doesn't work very well here if this thing that we had。

 this indices had duplicates in there right like let's say this was' an indices but it was some array that had zero。

1，2，2，3，4，1，2 now this is gonna to be very confused and it'll even complain it's like yeahike you passed me something that you told me they were unique identifierifies and they're not unique。

It worked for us because we knew that our range was always going to be0，12，34。

5 up to however many cards and it would never duplicate， so it worked。

The reason it's saying hasable there is it needs to be able to hash this thing。

Because it's going to build a little hash table， a little dictionary between each of these and this view。

I told you trying to hook up each of these two of you in these a little hash table， right。

 a little dictionary of it。But this wouldn't work for us anyway， because if we hashed up our cards。

 it would include the is face up and is matched and those are changing because as you click on cards is face up changed now it's a different card according to this plan we need some sort of thing that identifies a card forever uniquely no matter what happens to that card no matter how much it changes。

 we know it's this card， the first witch or the second pumpkin that's which card it is so then as the cards move around and they go face up and face down or for each view can tell which one is which。

So we are not going to do ID self。Here make sense to do ID self in this case So what you're seeing here。

 this for each this is what a normal for each looks like you would have an array or some range here and you would not have that ID self but you would get this error and this is where you have to fix if you want things to work in your for each and what it says here is that for each requires that card conforms to identifiable okay yet another protocol right we have equtable and then there was hashable now we've made the problem be identifiable。

You can probably guess what this protocol does。 It makes it so this card is identifiable so that the for each can find it knows which one it is。

 So let's go make our card conform to identifiable。 Go back over here。

 We already made it conform to equtable。 Now， we're going to say identifiable。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_25.png)

And it's going to get an error， of course， because there's a requirement to do something when you're identifiable and we click on that and the fix does work here sort of。

 I'm going to click fix and it says， oh， well if you want to be identifiable you need to have a v called ID okay it makes good sense and now it puts a placeholder type in here object identifier。

 I don't know why it really puts in that's why I say it kind of works。

 but really the type of v ID and the identifiable protocol is a don't care。Well。

 to care a little bit， if don't care as long as it's hasable， then it's fine。

We usually use for identifiers in the identifiable protocol， ints and strings， things like that。

 things are easily hashable and that we can make one up for each of our cards I'm going to use a string。

For mine and I'm also going to put my ID instead of right here top。

 I'm going to put it down at the bottom because it's not really as important as all my other vs。

 so I kind of put it down out of the way it's identifier that's nice， it's important。

 but it's not as important as what the card face up， that's part of the game。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_27.png)

Now if I add this， look again an error up here missing argument from parameter ID right now I have a bar that has no value in here。

 so I need to give it a value， let's do that let me appear and say。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_29.png)

ID and it's a string， so it has to be some sort of string I could also go click on this and do fix and it'll put a little。

plateholderer there for string， just so I know there's a string。

So what I'm going to use for an identifier 1 a and 1 B for the first card 2 a and 2B for the second card。

 3 a and 3B for right everyone agree that's a good identifier for these cards will be unique and easy for me to understand actually if I ever go look at it in my code which I don't really look at it that often so how do I get this one right here I want a1 and I'm in a four loop I got the pair index it goes from zero to the number of cards minus1 so I need to somehow convert that pair index into that string right in the middle of there and I'm going to use a really cool feature and Sw string interpolation and what this is you can say backslash open parentheses closed parentheses and then you can put inside there almost any expression you want。

And it will evaluate that expression and turn it into a string and plop it right in the middle of your other string。

So for our cases that would be pair index plus1， right， I don't want card0 a。

 I want card 1 a and same thing here。Pair index plus one。So this little string interpolation thing。

 the backslash open preheesis， that's really cool for debugging because you can you know。

 put print on the console complicated expressions， see what's really， really kind of cool。No errors。

 This all must have worked Is that simple really， I just set this thing to have a unique ID。

 let's go back to our view and see if this worked， there's our view， no errors back here。

 Let's try shuffle okay， everybody cross your fingers。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_31.png)

Whoa。😮，Look at that， now that the for each can tell which cards go with which views when I hit shuffle。

 it actually moves the view to its new place in the array。And if we want to see this even better。

 why don't I put a little V stack here。Maybe we're spacing zero just to really up there and say text。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_33.png)

Of my card's ID。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_35.png)

So now see 5， A， 6，A， 4 A， C1A2C， they're nice and ordered and when I hit shuffle。Y， look。

 there's 2 A right there， 1 B got moved over one。So this animation。

 you're seeing the power of the animation of Swiss is incredible。

 we did one line of code up there once we made things equtable and identifiable and you get all this animation is's just amazing you're going to see in two weeks how much stuff you get for very little code and that's because it's animation again is so important to mobile app U eyes。

All right， so I'm going to that's enough of that， let's get rid of this v stack here。

 go back to what we had before。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_37.png)

Let me show you one other quick protocol which is fun to do if we go down here to our console you see how it was printing out our cards with this really long complicated name Swift can convert any type into a string like this but sometimes it's pretty verbose what if I wanted a nice little compact version of this how would I do that Well there's a protocol for that。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_39.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_40.png)

I'm going to go back over here to my model， and I'm going to add yet another protocol here。

 which is my custom debug string convertible。And again I'll wait and hit here and hit fix and it says。

 oh， you just need to provide a string called debug description that describes this thing All right I'll do that。

 I'm going to return something， let's put the ID and then maybe the content obviously。

 how about whether it's face up， maybe I'll flick a nice ternary expression here。

 this is the word up or down。Like that， and then maybe we'll put our is matched in here also if it's matched。

 we'll say matched， otherwise we'll say nothing， something like that。

And so I can basically make it look however I want， by the way。

 I don't need return and oh I can probably put this down at the very bottom。

 it's the least important thing。There。But now look what happens， let's clear my console。

 this little trash can clears it right there， go on here and say shuffle。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_42.png)

So see how it's used my short notation here， 10 B is this guy face up， et ceter。

So this can also be really valuable for debugging just to make your things less ver when you look at them in the console。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_44.png)

Let's have the cards flip now we've been postponing this card flipping over， let's go do that。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_46.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_47.png)

To make my cards flip over could not be easier just I got my card view right here in the middle。

m say on tap gesture， please， Mr。 Viewmod， I have the intent to choose a card。This card。

That's the card that I'm for reaching over， I want to choose it and that this is an intent to remember our view model。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_49.png)

We have these intents， this is one of them and it just calls the models one we go over here。

 here's the models one and we haven't implemented it I just over here by just having this thing flip over just have the card flip we'll eventually play the whole game in here I's going have it flip start actually even simpler and say print chose that card。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_51.png)

Ans is going to have this print this on the console when we go back in here。So let's do that。

 I can move it over here。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_53.png)

Get our console up。Clear it out and start tapping on cards。 That it worked。 right。

 let me talk the demon。 Yeah， spider， it's working。 It's clicking on， I'm tapping on these things。

 It's choosing them。 So it made its way through our view model down to the model。Right。

 let's flip the card over。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_55.png)

This is where many of you and sometimes I'll say， how do you guys think we would do this and people would say。

 well， we would say Car is face up do toggle， we know that toggle。

 that's what toggle does and this error comes up。And this error is really one of the most important errors you're going to see in the first three weeks of this course because it gets to this difference between a value type and a reference type。

You're used to reference types， this would make sense in a reference type。

 someone passed you the card， you flipped its face over。

 but you're not actually being passed the card that's in your model。

 you're being passed a copy of it。Every time you pass a value type， all structure value types。

You pass it。 It's a copy。 So it wouldn't make sense even if it。

This error didn't come up here which is that you can't mutate this thing it wouldn't be right anyway because this card we're saying right here。

 this card is this card， which is the argument to this function which is not only a copy it's also implicitly a let the arguments to a functions are let。

 so that's why it it use a mutating member on it it's a let， it can't be mutated in any case。

 so this is just completely an utterly wrong， even though it looks like it would be exactly the right thing it's exactly wrong because of the difference between the value type which our card is it's astruct and what you're used to reference type or you're essentially passing a pointer to the card then of course you could modify it。

😡，So this takes a little bit of getting used to so what do we do here Well we want change the is face up in the actual cards in our model。

 so instead of trying to do I face up toggle with this card I'm going to do it with the card in here。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_57.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_58.png)

上面四。Cards of chosen index。Plip that over， and then I have to let chosen index equal something。

Now this begs the question， I'm going to find out which card this is in my model。

I have to go look in my model and find which index is that so I can modify it in right in the array。

 this is the truth in my model。And the answer there is we're just going to write a little function to do this。

 I'm going to call it index of card。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_60.png)

here it's just a little funk index of card and it returns the int， which is the index。

 and we'll have a return zero right now so I can look at the error that's going to happen here。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_62.png)

So we'll eventually fill this out where we go find out which index this card is。

 but before we do that， look what happened didn't work。

 It says cannot use mutating member on immutable。Value， self is immutable。 Do you remember this？

This happened when we did shuffle， we tried to shuffle the cards right down here。

 tried to do this card shuffle， we got this same thing， and what did we how we fix it。

 we marked the method mutating so that Swift would know oh yeah。

 we realize this thing is going to mutate and is it ever going to mutate because this mutating funk choose is going to play our game。

 it's going to massively mutate our memory game。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_64.png)

Now let's make this index work you know what I'm going to do here， I know how to identify my cards。

 they're identifiable so I'm going to use identifiable myself just like for each did I'm going to create my own little four loop here I'm going to say four index in my cards indices。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_66.png)

And'm going say if the cards at that indexes ID equals the cardss ID。

 then I'm going to return this index。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_68.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_69.png)

Everybody agree that that will fine that card。And return this index。Now， it's a little weird， though。

 what if it can't find the card？It's returning zero。

 That's the first card So that's pretty bad I someone asked me to find the index of a card and I couldn't find it so I just return I panicked and I return the first card this return zero right here is bogus。

 but we have to return something because it returns to int so will return zero for now and actually I'll teach you a nice little thing here a fix me if you put fix me in your comment then when you go up to the top here。

 look there's a little bandaid at a orange thing it's a bandaid So in your list of all your functions say oh there's a fix me for me to fix。

All so that fine there's also one called to do， which will put a little kind of to do icon in there。

 so we'll come back and fix that bogusness a little bit later。But。For now， believe it or not。

This should just work because we choose is now finding the right car and it's hopefully flipping it over versus go back to our view here。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_71.png)

Got our view click， it worked。 click， I'm tapping on cards。 They're flipping over。Now again。

 the animation is pretty bad this little cross dissolved。

 you're probably getting the idea cross dissolved is the default animation we want to flip the card over right we want to like give a nice3y look and flip and we will do that。

 but right now we'll have to stick with the default which is。Dissolved。So that's it。

 we've got our thing almost completely working， the only thing that's left to do is to actually play the game。

 but before we can play the game I need to show you the enum and that optional because we are going to use optional this special type in our implementation of our model。

 so let's swap over we take a look at that。You know about instruction classes。

 so EM is another thing kind of like that， you won't be using enum in your assignment two， obviously。

 but in your assignment3。I highly recommend it but I think it will really help in assignment3 and we use enums whenever we have some data type whose values are discrete in other words there's only two different cases that the value can be or maybe three or seven or 20 possibly but they're discrete so enums they look a lot likestruct and classes in terms of open curly brace。

 but there's no stored vars in there。No stored variables in an enum。

 The value of an enum is discrete。 Here。 I have a fast food menu item。

 It can only be either hamburger or fries or drink or cookie。 That's it。

 This fast food place doesn't sell anything else。 That's all it can be。 So there's no var there。

 It's just these for It a discrete value。 So you've seen enums in other languages。 Now， enums。

  importantly， are value types。 They're likestructs。 They get passed around by copying all the time。

 They're not reference types。But what makes？Enums really incredible and swift and really powerful is that you can associate data with each case。

 for example， my hamburger， I might want to know whether it's a single or a double hamburger one patty or two。

 so I have number of patties as an integer as associated data with that case， same thing， my fries。

 I might want to know whether large fries or a small fries。

 which might be another enum my drink actually has two pieces of information。

 Is it a Coke or7 up or what is it and how many ounces is it。

And notice that these things are named kind of like parameters to functions。

 they don't have external internal names though just one name and that name is not required This one for example。

 doesn't say brand or something like that it's just a string it's up to you if you think the type alone is enough。

 I probably wouldn't think that here， but we're try and show an example of it。

This is the big difference， this associated data in enome and Swift。

Setting the value of an enum looks like this， so I've got two variables here menu item and other item they're both of type fast foodod menu item they're of this type this enum。

 and I can set them by just saying fast food menu item。 hamburger or fastfood menu item。

 cookie that sets it and if I have this associated data I just provide it right there in parentheses。

Notice that Swif can infer one side or the other of an equals but not both sides because if I just said yet another item equals dot cookie。

 what if there was another enum that had a cookie in it。

 Swift wouldn't know which one we're talking about here so I've made it infer each side on the first two ones。

 but on the third one that's red because you can't do that you have to do it now of course Swift can also infer the type if you're passing it into a function or something like that you could figure it out then as well but if you're just doing equals you need one side or the other。

You have a menu item of type fast food menu item you want to see which one it is and do something。

 how do you do that do it with a switch statement again other languages have switch statements。

 switch statements are super powerful in Swt one of the things they can do is look at an enum and check every single case。

So here I have this menu item hamburger I'm ignoring the patties， which is fine I can do this。

 this code here is perfectly legal even though hamburger has that patty's hint with it。

 I'm just ignoring it and you're allowed to ignore it when you're switching here so I'm just looking at each one for example here I have a menu item which is a hamburger with two patties and then I've switched on that menu item and I say in the case that it's a fast food menu item got hamburger print burger it does this fast food menu item dot can be inferred so we would not have those there we take those off like that。

And so this is what it typically looks like to switch on an enum and see what its value is。

If you don't want to do something with a certain case， you put break。

Break is break out of this switch， I don't want to do anything here。

The other thing about switch is really important， you must cover every single case in the enum。

If you don't， if you can't like you don't know what to do then use this special default case right here。

 if you do the default case that'll happen if it doesn't match any of the other ones and that's especially important because you can switch on other types。

 not just enums you can switch on a string， which is kind of cool switch on this string in case it's the word goodbye do this if this case is the word hello is do this but then you definitely need default because you can't list every single possible string it would be infinitely long。

So you got to have default for that。When you're doing the code， you can have multiple lines。

 you see this fries， it has multiple lines， you don't even need curly braces surrounding it or whatever。

 just put the multiple lines there and it does not fall through in other languages it would fall through to the next case and execute that line does not you can put the word fall through there if you want and then it will fall through but by default it doesn't and we don't use that that's really not very swift to use this fall through thing I would not do it。

All right， what about that associated data I had the hamburgers and the fries。

 but I've got all that associated data I want to get at that as well， well I still switch okay。

 the switching still happens。But in each case， I can put open parentheses and then a list of let and local variable names to grab this associated data out。

 and then these lets that I did become local variables that I can use inside the implementation of that case。

See that，ll let that sink in a little bit。Here's an example we look at the drink。

 I grabbed the brand into something called brand， even though it had no name when I declared it and then ounces I called it the same thing ounces and now my prey to saying a。

String interpolation ounces ounce。Sring interpolation of the brand brand。You see。

 so you see how in my switch， I just grabbed those associated data。Now in enums。

 you can have functions， methods， you're allowed to have that in many methods as you want just like a instructor or class。

 and you can have vars， but they have to be computed。

And usually computed from the cases but they have to be computed。

 no stored bars allowed in your enum because all your data is up in here， this is where your data is。

 it's not in bars。Now let's take a look at this function here。

 I put a function in my fast menu I calledIs included in special order number two or whatever。

 what would something like that look like here it is。

What I've decided is that a special order like special order number one is a single patty burger number two is a double patty three is a triple。

 et cetera， that's what the special orders are so here it is include special order I'm switching on myself。

Because this function is in the fast food menu item data structure。

 and so I'm switching on myself and it saying if I'm a hamburger。

 then grab my associated data here and return whether the Patty count equals the special order number because this is the rule here。

Switching on yourself is how you get your own data to look at it to implement most of your functions if you have functions。

Sometimes you might want to four loop， do a four in over all the cases in an enum to do that you actually have to make your enum。

Behave like or conform to the protocol case iterable。And if you conform a case iterable。

 then you will get this static bar called all cases。

 it's static right global namespaced bar that you can pour in over so it's like here I have Tesla models and I'm saying four model in Tesla model all cases and then I'm calling report numbers on each case。

So that how you iterate over the cases in email know。You'll probably want that for assignment three。

 again， that would be really useful。Now I told you all that stuff about enums mostly so I can tell you about optionals and optional is a type a very very important type。

 it's an enum it's just a normal enum this is optional iss not actually like built into the language or something it's just an enum it's actually a very。

 very simple enum， let's take a look at it， it's generic。So we have this in them optional。

 it has a don't care of type T。And it has only two cases， the case none， fine。

 or the case sum in which case the associated data is of that type T。

That's why we have that don't care， just so that in the some case。

 we know the type of the associated data， super simple little enum。

That is going to be used all over in our code。Now， where do we use optional。

 we use optional everywhere in our code where something can be not set or undespecified or undetermined。

Anytime we have some value that sometimes is in this undetermined state or whatever we're going to use an optional instead。

 we're going to take the type that used to be there。

 string or int and we're going to turn into an optional where that string or int is now the don't care of the optional and if we're in the undetermined case we're going to be none and if we're in the determined case or the set case we're going to be some with that thing we originally had。

As to value。Now this is so common to do to want to do that there's a lot of syntactic sugar。

 you know what that is syntactic sugar， just stuff that the compiler does for you and will interpret for you。

 but behind the scenes it's building this enum for you to make it look really cool your code can look really sleek and easy to read so let's dive into this syntactic sugar and see what it looks like。

Let's start with how we declare an optional。So we declare an optional by having the type that we want the associated data to be。

 the don't care and a question mark。Strering question mark， this yellow thing is an enum。

It's an optional enum。And that's it， and you really want to get used to calling this。

Optional strength。Because it's an optional first string is just its associated data。

 but that's an optional string right there， so question mark after a type means make this into an optional with that type is the associated data。

Then you can assign values to it， so down at the bottom here equals nil means the nonen case。

Optional string equals dot9， the non case of the email。If I say hello。

 which is the same type as the associated data， it's that like saying optional dot some case with the hello。

And if I say nothing， I didn't say it equals anything， you get implicit n。

That's important because a lot of times these things， these vs are vs on our classes andstructs。

 and we don't want to initialize them because they start out in the not set state or the undetermined state。

 so we don't have to say equals Ne all the time to have them start out the way they start out equal meal unless you make them equal to something else。

That did， that's how you declare and assign an optional super straightforward exactly what you would imagine。

 in fact。Now what about getting the data out of an optional So let's say I have an optional called Ho。

 it's an optional string。And it's equal to something or not by equal to nil。

 I can say print hello exclamation point， that's called force。Unwrapping of the optional。

 grabbing its value， assuming you're assuming it's not nil。 And if it is nil。Your app crashes。

So this is exactly what I said， brute force， give me that associated value because if it's nailils crash。

 so you would never do this exclamation point unless you had already done some other code。

 some ifs or something to make sure this is not in the nail state。

Now why would you ever use this force unwrap because it crashes your program。

 no one wants their programmed to crash， well when you're developing your code。

 you do want your program to crash often because you want to find the bugs。

 you thought hello could never be nil and somehow it ended up being nil and when it crashes would get a nice back trace。

 you can go look into debugger， find out what's going on。

But more likely you want to safely look at that hello and you do that with if let。It's this like if。

 but you're going to say if I can let。Safe hello equal hello。

 Then I'm going to use Sa hello in here and it will be safe because I checked。And if it is Neil。

 then I'm going to be down here in the else of the earth。

This if let something equals something do this else something else is all over your code okay anytime you have this in undetermined or whatever type things and here I put on the side what this looks like in enum terms right I'm switching on this enum the case of none I'm going to crash in this upper one in the case of some I use it and down here I'm switching on hello in the case of none。

 I'm going to do something else， the else case and in the case of some then I'll do it say hello。

This last one also has another form， which is just if let hello。Not equal something else。

 and that's almost like saying if let hello equals hello。Right same name as the thing has。

 and then inside here， this is not an optional， this will be a string inside here。

 I mean here it would have been nil。So question mark question mark just means give me a default in case this is nil。

 so here I have x， it's an optional string， we don't know what its value is might be nil or not。

 now I'm going to let y equal x， but if x happens to be nil default it to be fo。So that's optional。

Let's jump back to our code here and use Op to implement our game logic。Before we even do that。

 I want to go over here。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_73.png)

AndF me this bogus thing。What do we really want to return from index of card if we can't find the card？

We wouldnt return some sort of indication to the caller， I couldnt find this thing。Yeahmil。

 exactly we want to return essentially optional nil。

 so we're going to change this return from being zero to being nil and we're going to change our return here to be into question mark optional int。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_75.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_76.png)

This is。Perfect example of why you need optional you've got something that is calculating something。

 it might not be able to get what you want， it has to tell you I can't find it。

That's how he does it returnedturn to Neil。But that broke our code up there Why did that break our code because cards is an array。

 open square brackets with something inside the thing inside is supposed to be an int。

 but now chose an index is an enum so I can't say array sub enum that's no good right if I option click on these types。

 this type right here， this type is int question mark。

 not int so I can't say array of an inkquest mark it makes no sense。

Now there's a couple ways I could fix this I could say exclamation point that's going make this red error go away but of course if I call index and it couldn't find it it's gonna crash my app now hopefully that should never happen because these functions by the way this function think should be private because I'm only using it inside of my app so hopefully I know what I'm doing in here but's why take the chance because what are we doing here somebody chose a card and if we can find it we're going to flip it over but if we can't find it let's just ignore it。

 let's not crash we'll just do nothing we're going to do that by not force unwrapping it we're going to use iflet so if we can let the chosen index in do this then we will go do this and inside the iflet chosen index ist int and we'll never get inside there if it's not an int because iflet won't even execute that。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_78.png)

So。Also a beautiful looking use of iflet。Do nothing if I can't find the index of that card。

Having this code right here return and optional， that's stuff that all built into array。

And one of the things that I'm going to tell you over the course of the quarter is really familiarize yourself with the programming interface to array array。

 you could do so many things with array， especially functions in array that you pass other functions to to do things for example。

 how could we do how could we get rid of this entirely just totally delete it and do something with our array instead？



![](img/0d8de5d38475531ffb42f5d3d8445d0b_80.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_81.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_82.png)

Amazingly we can use cards， which is the array do first and start typing it。

 here's first index where it tab it'll even fill it out for us a little bit and it's saying it once a function that takes a card and returns a bull don't worry about that throws's for error handling we'll be looking at that very late in the quarter so we don't have to worry about it but you just want something it takes a card and returns a bull so I'm going to double click on it this is memory game equtable card we'll call that card to check because that's what we're doing that's the card we want to check inside here we can check it by saying the card to checks ID equals the cards ID that was passed in to our function。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_84.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_85.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_86.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_87.png)

Now this seems kind of ugly and hard to read， but we're going to do all the things we like to do。

 for example， we'll use the dollar zero trick here to get rid of that and just use dollar zero here then we can。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_89.png)

They're all in one line。AndNow it looks really， really cool。And yes。

 we could do trailing closure syntax by going like this。

 but I actually don't like doing this and Swift doesn't like it either it's probably going to。

Complain， yes， it's just a warning so you could do it。

 but this is a little bit confusing because it looks like this first curly brace is the start of it if。

Even though it's clearly not， it's part of that so don't let this warning happen， in fact。

 don't ever let warnings happen if you have warnings。

Get rid of one way or the other don't have warnings or errors in anything you ever submit in this class or that you ever write in your life warnings are bad so you can see there we don't need our index of we just use something in a that finds the first index and why is it called first index because of course this works with arrays that would have multiple things that would match and it's just telling the first one now in our case we know that our IDs are all unique they better be so we don't have to worry about the first index is fine for us here。

What's the type of the return value of the first index function？no。And why。Optional int， yes。

 optional int bonus points。So first the index returns an optional index that so why we still have to if let it and why is it an optional lid because it might not find something where that function is true。

So it has to be able to return now。Let's just do our game logic， we putting it off。

 let's do it right here right now。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_91.png)

So we can have a little more。Space here， actually， let's go back here。Allright。

 how am I going to this？ Well， the first thing I'm going to do in my game logic is I'm only going to allow you to flip cards over。

That are face down。If a card is face up， I'm going to ignore when you tap on it。

 I'm going to be the one to turn cards face down。So if you have two cards in their face up and they don't match。

 I'll turn them back face down when you click the next card So when you click on a Facebook card。

 I'm going to ignore it so the first thing I'm going to say is if the cards at the chosen index，Dot。

Is face up not？Im going put them not at the beginning， so if it's not face up。

 and I'm also going to ignore if you click on a matched card cards。Chosen index。

That is matched so I'm going only actually do my logic here in the case where you click on a face down card does not matched everyone agree that that limits the amount of work we have to do here。

 but if you do that then I am going to also definitely turn the card face up for you。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_93.png)

You just clicked on a card that was face down， it's not matched， I'm going to now turn it face up。

 no matter what I will turn it face up for you。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_95.png)

Now。How do I decide what to do here？As you'll learn in a data structures and algorithms， course。

 or whatever， sometimes the most important thing when you're deciding on an algorithm is what's my data structure that's going to drive the algorithm？

And my data structure for my card game， I'm going to put the card game back now that I think about so you can see it here side by side。

 it's pin it， it's going to make it so some of our code doesn't fit。

 but at least be able to see the game。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_97.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_98.png)

I'm also going to have the cards start face down。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_100.png)

The day structure I'm really going to keep is。What is the index of the one and only face up card。

I claim， if I know the index of the one and only face up cards。

 not one of two face up cards or no face up cards， but one and only one card is face up。

 then I can easily implement my algorithm because if one in only one card is face up and you click on a card。

 I'm going to try and match it。Otherwise I'm not going to， otherwise。

 just going to basically turn all the cars back face down except for the cards you just clicked on。

It's a really simple algorithm to do that， I need my data structure， which is a var。

 I'm going to call it the index of the one and only face up card。

And it's going to be an in because it's index into my array， and when I do this。

 of course I immediately get an error。An interesting error actually to look at。

 it says you are returning from your initializer without initializing all your stored properties。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_102.png)

Which is true in it， I told you its job is it has to initialize every stored property you have unless they're defaulted or something。

 they have to be initialized and here's one。No value。

So what should its value be when the game first starts。

 which is the index of the one and only face up card， none of them are face up to start。

We need an optional and it needs to be in the not set case。

 so I'm just going to change this from being an int to being an optional int。

And the error goes away because you get this free equals nil。

 So it's starting out in the not set case， which is exactly what we want。

 because when our game starts， all our cards are faced down。

 we have no index of one and only face up card。Now that I have my data structure， as I told you。

 the only implementation is just to see if there is one and only one FacebookOcard。

 if it matches the card you just flipped over let's do that I'm going to say if。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_104.png)

I can let potential match index。 I'll call it equal the index of the one and only face up card。

 It's a good thing that it tabs there because I chose such a long name。

 Now I'm going to see if they match。 So if the cards at the chosen index。

 which is the one you just chose content。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_106.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_107.png)

结果。The cards at the potential match index。It's content。Then we have a match and if we have a match。

 we're just going to mark those two cards as match。

 the cards at the chosen index is match equals true。And same thing here， the cards at the potential。

Match index。It is matched equals true。And that's almost my entire implementation。

 the only thing is if you flip up a card and there's not one in only one Ph of card。

 then I'm going to turn all the other cards face down。

Either there's two card space up that don't match and you've picked another one， you didn't match。

 I got to turn things down or there's no card space up and you clicked one in which case it doesn't hurt to turn them all face down。

 but it might as well， so that's the else case here of if I don't have I can't if let the potential match index there so if this is nil then the else case is going to turn them all face down。

 which I'm just going to do with a four loop for index in cards do indices。

I'm just going free every single one of these cards at that index is face up equals false turn the face down Now of course I just turned the one that you clicked on back face up so that one will be turned back face up The thing about this is though as this is all happening I do need to keep index of the one only face up card。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_109.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_110.png)

Set to what it's supposed to be in the case where two cards are face up， and I tried to match them。

 whether they match or not， there's not one and only one card to face。 There's two。

 So I'm definitely going to say here that the index。Of the one only face of Car in this case， is nil。

So there's two cards， that's how I got inside here。

 but in this case where I just went and four looped and flipped them all straight down， in this case。

 the index of a one an electronic card is the one you just chose。

So I turned all the other ones space down， and then when you click on a past on card。

 I always turn U face up， so there's one and only one and it's you， it's the chosen one。袜。

Cleing up our spacing here。Raise your hand if you think this will play the entire memorized game as is。

With no changes。Ye of little faith， not a single person believes that this will play to get， well。

 let's find out ready， click on a card。I chose two cards now。

This is the moment of truth if I click on another one， is it going to？Do the right thing。 Let's see。

 click， turn them back face down。 How about this。No， find a match。😮，Oh。

 it actually did work because I'm clicking on the spider webbs。

 it's not turning it over because they're matched and face down。

 so it must have marked them as matched。But it is really hard for me to see whether my logic is working here。

 I was clicking on cars， seemed like it might have been doing the right thing。

 but I couldn't see why because the match cards don't go away。

Let's go back to our view and make it so that match cards don't appear here。

 and then we'll really be able to see if things are working， so here's our view。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_112.png)

Of course whether a card is matched is all handled by our card view as promised everything about cards is in here。

 I'm just going to do this with opacity and I'm going to say if the cards is face up or if the card is not matched。

 then I'm going to use opacity1 otherwise I will hide it cards that are face down and matched will have no opacity。

 they won't show orange back they'll just not be seen。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_114.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_115.png)

Butty cool with that and see how I'm doing that opacity to the entire ZStack of my card here。

Let'll see if that works。Click here， click here。Okay， so they didn't go away。

 So those must not have matched。 and they don't。 Let's try this guy。 These do match ready， whooo。嗯。

This appears to be play the game quite nicely。Now again。

 we'd like some nice animations so you're flipping over and all this stuff。

 but the logic of the game seems to be correct， everyone buy that。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_117.png)

The logic that we did there。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_119.png)

Was kind of cool， but it's a little errorprone and the reason it's errorprone is keeping this index of the one and only face up card in sync as I make the changes。

 oh I might have actually forgot to put this line in there or something like that an index of the one and only face up card really can be calculated by looking at the cards if I look at every single card and I only see one that's face up then I know the index of the one only face up card so I'm going to enhance my program here by having this be computed。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_121.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_122.png)

A computed property that just goes and looks at the cards to find the index of the one and only face up card。

 and then I'll be able to remove some of this coordination code in here and it'll always be right I'll always get the right answer here。

The only problem with this is I need to be able to set the index of the one and only face up card because when you click on a card right down here。

 I still need to do this line， I need to say which card is the one and only faceace up card。

We've seen computer properties before， like var body， some view that's computer property。

 but if you have a get Ana a set， then you have two parts。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_124.png)

To your computer property with the word get around the first one and set around the second one。

 and in the set one you have a special variable in there called new value and that's the new value if someone says index of the one and only Facebook card equals something。

 this set will be called with the variable new value set to whatever the value the person said it has。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_126.png)

Let's do the get。 The get just needs to go and look and find if there's one and only face up cards。

 so I'm going to create a little。Face up Car indices。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_128.png)

Aray here， which is going to be an array of ant use this empty array to start。

 I'm going to go through all my cards。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_130.png)

My cards indices。And I'm just going to see if card at that index is face up。

 then I'm going to add it to my face up card indices。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_132.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_133.png)

So now does everyone agree that this is an array of all the indices of the face up cards。

 let me go with that。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_135.png)

This is cards。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_137.png)

Right now that I know that， I can say。If face up card indices。 count equals one exactly one。

 then I'm going to return how about face up card indices do first first is a var in array that returns the first thing in the array。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_139.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_140.png)

So if there's only one， then I'm going to return that first thing in the array， if there's not one。

 then I'm going to return nil。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_142.png)

Because either there's two or there's zero， but there's not one。

 so I'm definitely going to return mill。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_144.png)

And what else we got here needs to be equals。Equals into a colon。

 because I'm setting it to be an empty array to start。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_146.png)

Does seem good。Very simple code we're just checking here and on the set side。

 if you said the index of the one only face on card equals index5。

 then I'm going to make sure all the other cards are faced down so let's do that it's going to say for index in my cards indices。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_148.png)

If the index equals the new value， what you set this thing to， then the cards at that index。

Dot is face up equals true， otherwise。It's false。B buy that。

 does that seem like a reasonable semantic for setting index of one and only face up card to something set all the other ones face down and make that one be face up？



![](img/0d8de5d38475531ffb42f5d3d8445d0b_150.png)

All right， now down here， we don't have to do this anymore index of the one and only faceace up card equals nil。

 we can get rid of that because we always know the index of the one and only face up card。

 we calculate it so we don't need to do that and down here when we set the index of the one and only face up card to be the one you just chose。

 we don't to set all the other cards face down because the setter of that does it。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_152.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_153.png)

So here we're using this computed property to do this。And let's make sure it works。

 let's go over here。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_155.png)

We build tap， tap， still working， yeah。didn't break anything that's good and it seems like this was nice because it made this code really tight this is almost like the minimum possible amount of codes to implement this entire game but。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_157.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_158.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_159.png)

The cost of it was pretty high。 Look at all this code over here。

 We had to write more code to make this thing。Get simple down below then we had when we had it originally that's not a very good tradeoff to have to have written so much code well the reason we had to write so much code here is we didn't really use Swt we didn't use the functional programming we really did that brute force a lot of for loops and ifs and all that really we should use functional programming here so let's take a look at how we can make this happen using functional programming in one line for each of the get and set。

one line， like name that tune， I can name that tune in one line of code for each the top and the bottom。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_161.png)

Let's start with the top。So at the top， I'm going to start by making this getting the face up card indices all in one call。

 which is I'm going to ask the cards。Indices to filter out and when you do filter。

 you provided it a function that takes the index and returns whether to include it or not a bo。

 whether to include it。So what do I want to include it if the card is face up。

 so I'm going to say here filter。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_163.png)

Index is the int in cards at that index is base up。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_165.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_166.png)

I've turned this。Here and just done in one line of code。To get rid of that。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_168.png)

And what about all this stuff right here？Well， I have this， so I could just say， for example。

Return face up card indices。 count equals one question mark。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_170.png)

Its up card in diseased dot first， Otherwise nil。 So we've gotten it down to two lines of code right there。

 It's close， I'm almost there。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_172.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_173.png)

And this， by the way， wouldn't even need to be a bar to be a let since we're not modifying it once we calculate it。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_175.png)

And what about this set， well， the set one I'm going to make it to one liner by using a really cool little function array called for each。

 so for each takes a function， it does that function for each of the things in the array。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_177.png)

Here I'm going to say， and you can kind of watch this one for yourself later and see if you can convince yourself this is right。

 I'm going to return。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_179.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_180.png)

The cards indices for each and the function I'm going to use is that the cards0 is face up equals the new value equaling dollar0。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_182.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_183.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_184.png)

SoI'm not going to spend time going over this， but this is one you can do kind of on your own is a little homework to convince yourself that this actually goes through and sets all the cards except for the one you set the new value to be face down。

Back up to this get， though， I said one line of code and that's two。 Well。

 I would make this one line of code if this second line of code。Were something in a。

Because that e line of code is basically return me the only item in this array if there's only one item。

So wouldn't it be cooled up in array there were a var called only that would do that for me on any array that would be kind of cool to say give me the only thing you have and it's nil if you have more than one or zero well we're going to add that to array we're going do that using this。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_186.png)

Feature called an extension， so I'm going to make an extension to array。

 I'm going to add the var only it's going to return element question mark。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_188.png)

Now element is the don't Care for array， if I alt click on arrayray， look at the documentation。

 look up there。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_190.png)

Aray struck array， angle brackets element。 That's the don't care for the things in the array。

 So only is returning one of those things as an optional。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_192.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_193.png)

And this return is just return， count equals1。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_195.png)

That first， otherwise nil。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_197.png)

Now why am I able to just say things like first and count and stuff these are things in array and I'm in an array。

 I'm extending array， so these are my functions count and first they're mine， I'm array inside here。

😡，And of course， I don't need that return there because it's the one liner and that's pretty nice little code right there。

 and I can use it back up here。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_199.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_200.png)

By just saying faceace up card indices， that's this thing， let's just return this dot only。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_202.png)

You never know that。Only we added it to array， so now this array that comes back from filtering the items with that is face up。

 that's just a function and bet that filters the items out and returns the new array。

We get the only one out of there and we don't need this return right here。

 and we would probably put this all on one line like this。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_204.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_205.png)

Same thing with this。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_207.png)

Now we have very kind of dense code but also quite readable code to get the index of the one and only face of card。

 we're going to get the cards into indices filtered by the ones that are face up and return the only one if there's only one of them in there and on the set side for each of the card indices。

 we're going to set the face of value to either be the thing that was set as or false if it's not true if it's the one we set。

Now this is the entire implementation from right up here to right down here。

 still pretty nice code and you can see where functional programming is coming in。

Unfortunately didn't run out of time， I'll do this next week it's not something you need from your homework。

 but we're going to add another funk to array which does this little thing right here。

 this first index where this， this is something you can imagine would be useful for any array of identifiable things to say do you have something that matches this identifiable ID so we'll do that next time？



![](img/0d8de5d38475531ffb42f5d3d8445d0b_209.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_210.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_211.png)

Really quickly at the start。So your homework number two was assigned on Monday， it's due on Monday。

 you want to use all the code from today so that your game actually plays here because this thing plays this game now。

So you want that。Assignment number three， I actually put out today I hope it's on there and that's due two weeks from today so it's due a week and a half from next Monday next Monday is its official date of being assigned to you but that one is one if you bang out assignment two really quickly which you might because it's still pretty straightforward assignment3 is much more meaty you might want to start it and assignment3 is for you to write your own card game。

You're going to write your own card game from scratch。

At least starting to think about assignment3 in your head a little earlier。

 I would you know encourage maybe you take a look at it this week or this weekend or whatever you have a free moment and just kind of start percolating what you need to do you know everything you need to do I believe to do assignment3 so you don't need to know what we do on Monday maybe we'll cover some stuff on Monday that will help your assignment3 but you don't absolutely have to do except for one thing on Monday we are going talk about shapes doing your own shapes so you will need that but it's minor part of assignment3。

This is by the way the end of the you got to follow along only assignment two requires this following along thing that you've been doing assignment three it's your own app so there's no following along and there's no future assignment where you're supposed to follow along assignment number six will kind of build on your own assignment two but you won't have to do anything from class。



![](img/0d8de5d38475531ffb42f5d3d8445d0b_213.png)