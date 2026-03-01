# 斯坦福大学《SwiftUI的iOS应用开发｜CS193p Developing Applications for iOS using SwiftUI 2023》 p04 -04-Lecture 4 _ Stanford CS193p 2023.zh_en -BV1HyzNYdEiD_p4-

So this week is all about this picture that I showed you in the last lecture and how this applies to our memorized game is that we're going to use this to build the game logic so that actually plays the game hopefully by the end of Wednesday let's just zoom right back into our code this is where we left off last time。

And let me review a little bit where we are here so far versus that other picture What you're seeing here。

 this class， you see where it's says this class right there， emoji game， that is our view model。

 So in this picture back here。That's this little thing right here right that's the green thing and over here this is our model in our picture over here。

 it's this blue thing down here that's our model and we've already built our view or it's currently called content view we're going change it to be something else we've already built that piece of it notice also as I click here that I called that file memorized game I ended up calling thestruct memory game so let's just rename that and you're allowed to go in here and just rename things like this memory game if you wanted to rename the actualstruct thens a little more things involved right because you're name thestruct and the file and things and I'm actually going show you how to do that when we rename content view to be something like emoji memory game view some better name for it than just content view we'll show you that in a second Now if we go back here to our view model you'll notice that where we left off is that we created a var for our model。



![](img/557b24fc4abf8c191590fa0977410578_1.png)

![](img/557b24fc4abf8c191590fa0977410578_2.png)

Our view model back in this picture over here， it has full connectivity down to the model。

 it can talk to model， anything it needs because its whole job in a way is to understand the model and talk to it and interpret its data and present that to the view in a really nice way。

Sometimes I like to call the view model the views butler。 if you ever watch it down to Navia。

 one of these things， you see these oldtime butlers， they set the table。

 so you have a nice meal and they arrange all the things。 Well that's what the view model is doing。

 taking whatever's in the model and arranging it nicely。 So the view has this beautiful， simple code。

 Everything's really understood well understood。 That's the role of the view model。

 So of course the view model has this var right here。 and we're going to go over into our content。

 You all just throw it in there right now。 and we're going to put a v in our view。

 I'll call it view model。 that's a bad name。 but it's going to be of type emoji memory game。

 In other words， we're gonna have a var in our view that points back to our view model， of course。

 because it's our butler。 we need to be able to ask it for ask Jees for the things we need。

 we have to be able to ask it。 So we're going to have a var pointing to it。 By the way。

 I call I think I said this before and I'm going say this five more times。 I call that view model。

 you would never call the v in your view model you would call it game or memory game or something like that。

That's meaningful I'm calling this var view model and I'm calling this var model just so you are clear that's what these things are。

 but that's not what you would call them in real life it's just for understanding what's going on here One thing if you look at this picture back here。

 the way that's set up with those two vs a var here that points here and a var here that points here notice there's no var here that points here。

There's no vars and there never will be any vs in my view model that point2 views over here。

 The only way the view model talks to the view is with that something changed view model just say oh something changed in me and then it's the views responsibilities to pull the things that are interesting to it that's because it's a reactive stateless thing that knows how to pull its data and see if things have changed and if so redraw only the things and need change that's all part of the view mechanism So you'll never have a var in there Also of course you would never have a var here the points of here this is UI independence。

 this is part of the UI So that's just completely verboin to have something here knowing about this that would make absolutely no sense right UI independent these two things are part of the UI So that's the relationship between all of these things。

Actually， let me say one more thing about the relationships between these things too because in the slides I talked about like a partial separation and a full separation and then like putting your model in an outside state。

 which is like almost no separation， remember that。

So what you're seeing right here is partial separation and why is that that's because over here in my view。

 I have this var which points to an instance of one of these and this var is there and so there's nothing that stops me in my view from saying view model dot model dot talk directly to my model。

But I can prevent that if I want， if I want full separation， I can put this word in。Private。

 if I make that private， that means that the only code that can use this var。

 see it or talk to it is this code， it's private to this class。Now， if I do that。

How is the view going to？Get the cards and do the things at once。 Well， in that case。

 it's the view model's responsibility to， for example。

 provide a cards thing that returns an array of memory game of string dot cards。

Right and this is just going to return the model's cards and this might seem totally ridiculous to have this one liner that is returning that thing right there。

 but it actually is protecting model from the view the view has to go through the view model to get at things and it really probably is a little ridiculous in our case because our model is so simple it only has two things the cards and the choose function that's the entire model so maybe it is that's why I said maybe this partial separation would have been good enough。

 we could have left our model public， but if we do make it private。

 then we not only have to do that to make the cards so the view can see it。

 but we're also going to have to have the funk choose a card。Which chooses a memory game of string。

card。And this is going to have to have model choose that card。

It's going to have to provide everything This by the way this function we would call an intent function remember I talked about intent view models have intent。

 This is the user's intent to choose a card and we're going to see more about intent functions we're actually going to do a different intent function before we do this one So this would be full separation right here private model only the view model can see it it makes public whatever functions bars it wants to do it。

Now let's also talk a little bit about protection in the model side because this v cards  clearly other code needs to see those cards if I can't see the cards。

 I don't know which ones are face up， I don't know if which ones are matched whatever however I wouldn't want someone to reach you in here and change my cards I start flipping them up and down you know the game has rules about when the cards can be flipped up and down and when they match and that's all going be done inside this choose method I don't want some other code reaching in here so there's another protection I can put on here。

 which is almost the same called private set。In private set， it's just like private。

 but it means only setting this variable is private。

Looking at the variable is allowed so people can look at it and this is what this model would do for sure because we do not want someone interfering with our game logic by flipping cards over externally right so that's only something we can do so it's private to us but we want people to see our cards。

This thing of putting private and private set on things is called access control and there's some other access control that have to do with public libraries and all that。

 but just private and private set is really all we're going to deal with in this class and it's 99%。

The access you're going to do unless you're a framework writer or something like that and I'm going to suggest to you when you write your code in the real world and you hear that you start out private unless you know you want this to be public you start out private Now sometimes you know right away you want to not be private like here viewmod definitely wants these to be public because it wants the view to be able to call them there's no questions not can't be private but any other vs or things you have kind of lean on the side of private and then make the decision。

 okay I'm going to let other code call this but realize that once you do that you kind of locked into leaving it that way because the person writing the other code might not be you might be someone else in your team or someone in another team in your company and once they start calling that function。

 you gotta leave it there you can't take it away from。

That's the way I kind of think about doing the private stuff。Right so that's access control You know。

 by the way， while we're here， you see this function choose card。This is a type card。

In your reading assignment at the end， there's a little document that talks about how you choose the names of parameters to functions and it would say very clearly this wants to be internal only and have no external name。

 in other words， no argument on caller side。So how do you do that it's actually incredibly easy。

 You just go here and you put underbar。 This is the external name internal name。

 but the external name is underbar which means no external name So when people call they're just going say choose and they're not going to provide the argument they're not going to say choose card colon the thing and why do we do that This is completely redundant to this type This is a card it's clear to card you don't need to say it's a card it is a card When do we have these names there's a numerous reasons to have it and that document will tell you。

 but I'll tell you that the top two reasons one is this is a string or an inch or something where it's not clear what it is not a specific type like a card。

 it's a string well what is that string Another one。

Here is if some external name would read make the code read a lot better。

 This is left the example we saw move so move takes an offset how much to move And if you just said move provided the offset。

 then are you moving the offset or but if you say move by offset you put by colon in there just reads better right I'm moving by the offset So those are the two primary reasons you're gonna to put the names in there or like we saw with image where image can take different arguments like image system name means go look at the system images image named colon means go look at my named images right that means different things but again that's kind of you're passing a string you got to describe a little bit what that string is we would do the same thing obviously over here in our memory game this one we would also say choose underbar card and back here we would not have this。

Retally cool with that。That was just a little aside right there， having to be right there。Okay。

 we have had this error sticking in our face the whole time I've been talking to you class emoji memory game has no initializer what does that mean why is it saying that I told you that classes get a free initializer we already know strs get these nice free initializer like our card view had that free initialitizer had the content and it is face up remember and then we gave is face up a default value and now we didn't have to say is fed up but we could that was all really cool feature and we never had an in initializer for our card view well classes get the same thing but their initializers have no arguments so they only work if all of your variables have default values and we have a variable right here model that has no value and so that's why it's saying I can't give you the free initializer here because you have some uninitialized variables so you have no initializer please give me one it's saying so I could give it in ait and we're going to see an init in a second here in our model but instead I'm going to try to give this a value。

Equals how about memory game of string with no arguments， possibly， can I do that？No， because。

There's a missing argument， cards， okay memory game of string is a struct。 It's free initializer。

 lets me initialize all of the variables。 And if I go back here and look at my model。

 it's got an uninitialized variable， which is the cards U cards， So it's saying， oh。

 that's a struct fine， No problem。 I'll let you do this。

 but you've got to provide those cards In other words it wants me to say something like cards are something but that makes absolutely no sense here。

 we've got a memory game model， it knows how to play the game of memorize。

It knows how to create you know it's the one who has to create the cards internal array and all of stuff beside it wouldn't work because this right here is private set only we can set those cards anyway in our code so it just makes no sense to have cards the argument and that's where initial letters come in because what does make sense if I'm creating my model well I claim that what makes sense is that I should create it with the number of pairs of cards like maybe four pairs of cards。

This is not a var in my model， but it's the information my model needs to create itself。😡。

And when we have that kind of situation， we go over to our model here and we are going to have to create and emit so this is a function it doesn't you don't say funky just say it knit and you can have any arguments you want like number of pairs。

Of cards， which is an ant。you can have multiple ins， all with different arguments， perfectly fine。

 and anyone who's trying to create you can call any one of your ins to get it created and your job inside of an in is to initialize all your varase。

Now some of them might be defaulted so you don't have to do anything here。

 but like in our case we've got that cards， we have to initialize this so I'm going to start by making this card be an empty array。

 which is just array of card， openhees closed parentheses array is astruct get the free in ray doesn't need anything any argument so boom that creates it and yes。

 we could use that alternate array notation here， I could say card open parent close parentheses perfectly legal and believe it or not。

 can also do。This。And this kind of freaks people out at first， but it makes perfect sense actually。

 because we know that this notation is how we create a literal array。

 we did it in our UI over here when we had our emojis see open square bracket and we listed a bunch of strings in that case well here I'm just doing open square bracket and now putting anything in there that means empty array and in terms of the type Swif does type inference。

 it knows that this cards right here is of type array of cards So it knows that's an empty array of cards exactly what I want and that's exactly how we would do this。

 by the way Now what I need to do is to add number。Of airs。Of cards。

Times two cards to that array I won't agree that's what I need to do。

 I'm trying to initialize myself。 I got to go put my cards in there so oh by the way。

 let me take a time I decided my writing was so slow and hard to read instead I'm just going to put these up here and then I'm just gonna put a little thing around them when I'm talking about them so access controls what we talked about right now we're talking about in it we're in the middle of doing it in it and now we're on the next one which is a for loop because we need a four loop we're going to go through that many number of cards and do it so what is a four loop look like in Sw it looks like this for I'm going to call it pair index in a range zero dot dot number of pairs of cards。

Do something this is the only way you can do a for loop in Swt I'll show you what this looks like in C so that you can compare it。

 but it would be something like for pair index equals zero pair index is less than the number of pairs of cards。

Pair index plus plus probably this is what it would look like in C。

 and actually this thing makes it seem like in Swift up till version3， you could do this。

 we're on Swift6 now almost so can't do it anymore， but that's the equivalent there。

 but I really don't want you to think of it this way as the equivalent for this instead I want you to think about the fact of what's going on here。

 which is that this is your iteration variable， of course。

 this is anything that can be iterated over， so not just a range like this。

 but it could be an array or any collection that can be iterated over in order。

So we use four in a lot， obviously， to iterate through things。

The syntax really is for control variable in iterationable thing。

So here we're going to go and do that many pairs of cards。

 And what are we going to do Well we're just going to add cards So I'm going to say cards do append pen is the function in array that adds something to the array and I'm going to append a card So I'm going to here's my card down here remember our card struck down here So I'm going to say card and I'm going to use actually I'm going to use the free。

Initializer you see it right there pre initialitializer I get because I'm a struck the cardstruct is astruct and my card are gonna start out face down and unmatched and oops。

 we got some card gaunted here well have to talk about how we're going to do that and of course I need two of these cards right this is a matching game where we are trying to match cards so we need two of each card that is matchable everybody。

Cool with what I did there now what is that warning here saying immutable value pair index iteration variable there was never used says consider replacing it with underbar in other words to saying consider doing this。

 take this and go underbar。And that's exactly what we would want to do here because we don't use pair index in here。

So we still want to iterate this many times， but we don't care what the pair index is we don't use it in this code so we would use underbar you're probably starting to get the message underbar is the swift thing for just don't put anything here right like underbar we did here and choose card that means don't have any argument there and the underbar here means I don't care what the iteration variable is because I'm not going to look at it。

This code is interesting because you see is face up and is match false when I create a card they're always going to start face down and they're always not going to be matched we have to start playing the game until the card get flipped up so this is an obvious case where this wants to be defaulted。

Equals false down here， equals false。 And then we could just take this stuff out of here。

 We don't really need that。 And this is the exact same thing we did in our card view， right。

 this's an obvious thing to do。 Why we're down here looking at card。

 I also would never put coal and blue here because Swift can infer that on the fact that the value is false。

 false and true can only be that and I'll do another interesting thing here， too。 This content。

 I'm gonna make that a let。Because if I have a memory game card where the contents are changing as the game's going on。

 that's going to be a very hard game to play right so let's just assume for now that our cards the content stays the same on a card so that wants to be a let not a vrs not going change but face up and is match do want to be vs because as you tap on the cards they're changing their face up and sometimestime hopefully they get match and there is match would change so those would need to be vase。

So this is what I'll talking about that kind of explicit mutability here。

 we want to mark the things that can be changed。All right， what about these？This is the card content。

 you could imagine having a let content of type card content equal what？U。

Maybe car content parent disease。Actually， no， we can't do that。Card content is a don't care for us。

 We have no idea from this code what card content is We don't even know if it's a class or astruct。

 we know nothing about it so there is no way that we can call any knit on it we don't even know if it hasn't in it because we've already learned for example thatstructs they're free in it even we'll have any vars that don't have values in them so there's no such thing as in it with no thing here for a lot ofstructs and we know the classes only get this free little thing here if they have no vs are not said so we don't know that we know nothing so there is no way for us to create this content we are just incap of doing it we do not have enough information in this code to do it because it's a don't care for us we just don't care what it is so what do we do now how we can create our cards Well who does know。

What this card content type is。The code or the person person anthroroppomorphize it is。

 who creates us？If we go back and look where this is being created， it's right here。

Memory game of string。 This guy knows the card contest is a string。 In fact， he knows it's an emoji。

 not just a string。 He knows it's an emoji。 He knows everything about what this don't care for that guy is。

 So this guy has to be the one to create the content。But。

This guy is still the guy who knows that he has to create that many pairs of cards and he knows how to set up the cards and I think so we got a little bit of a problem here but we' got one piece of code needs to kind of get some information out another piece of code how are we're going to do this。

Well， this turns out to be super easy to do All I'm going to do is add another argument to my knit which what I'm going to call my card content factory and its type is going to be anyone want to guess。

系咪。An array of card content that would be a way to do this right you could pass in an array of card content and you could use it there and that's I'm really glad you brought that up because that's how you probably would do it in all the languages you've done but this is functional programming so we are going to actually have the type B a function that returns card content。

其实事实。Variable argument is going to be passed to our knit which creates a card content for us and then down here instead of trying to create it this way。

 I will just say call the card content factory please with no arguments in this case and I could probably even be a little better than this I'm going to bring back my pair index right there and pass it along so that the card content factory can do that use that if it wants I'm just going go back here pair index I'm going to pass that pair index here。

 which makes this now become a function that takes an int and returns the card content it's that's fluid and that simple to have these things you know passing around their various values。

This is really the heart of why we call this functional programming because we allow the different parts of the code who own the knowledge of how to do things to pass their knowledge along via passing a function and we're gonna to be passing functions all over the place in this class and so here's your first example to it and this is not even like we're doing this sophisticated thing this is a basic or this is a simple little demo and we're still using functions as types here so get used to this it's new to a lot of you I know but you'll eventually get used to it。

Now， of course we want to use this content that we created as the content for both of the cards。

 so we'll put that on both of the cards right here and we can also do a lot of Sw type inferencefer here。

 we don't need that Sw can infer that type because it knows that this thing returns a card content so we don't need to explicitly type what it is and the same thing back here see we have this model which is a type memory game of string。

 don't need that because it knows that that's what we're creating here and here's the incredible thing。

We don't even need this。As long as our card content factory here。Return something that's a string。

 then this is going to be a memory game a string， we can even infer from the return type of the function I passed what it is。

This function how do we pass this on our end Well you're probably a lot of you are guessingooh this is going mean inline functionoo and it is。

 but first I'm going to create a global function that does this I'm going to call this create card content for pair at index index which is an ant and returns a string。

And I just go back here and grab my emojis that I have them to have right here， copy them。

 put it over here and say returnturn that thing at that index。Everyone cool with this function。

Does that look like what we want， we're just going to grab the emoji at that index and does everyone agree that this is a function that takes an int as an argument and returns a string。

 which is what this argument is supposed to be。Right then I can just say right here card content factory is create card content and's completely legal to do this because this is a function that takes in return to string and that's what the type of this argument is so I can pass it in there。

Now we would not do it this way， we would of course use a closure。

How do we get from the closure syntax we've been seeing in our other code？

How do we get to there from this function right here， Well。

 let's just take this function and select the whole thing except for not its name because it's in line so we don't care what its name it is and I'm just going to。

Copy this here。And then I'm going to paste it in place of this card content here and before I do that。

 though， so you can see it clearly， I'm going to put this on its own line。

 I'm just going to paste in what I copied ready， paste。

And now every time I do that I have to change two things， I got to take this open curly brace。

 that's this one up here and move it to the front so that the curly brace contains the entire closure and then I replace it with the word in。

Lets do that， take this out of here， cut it， replace it within， and move this over here。

And that is completely valid closure right there， except for this。

s say here closures cannot have keyword arguments I happen to call my function have an external name and an interperternal name for parent index index that's not allowed with a closure。

 so I have to take this out here。Now we have a completely valid closure look。

 no no errors and it's fine， I promised you that I wouldn't have to say memory game up string because it would infer it from this return type。

 which it did， which is kind of cool。But this still doesn't quite look like the closures we've seen before。

 it looks similar though to this one， remember this one for each。Index in。

 it looks awfully similar to that and in fact this is just a closure that takes one argument which is the iteration variable of your forage so that's what's going on there。

 but it looks a little simpler here it just says index in is over in R1 here it has all this parenthees index int arrow string Well why is there all this extra craft here why don't we have it over there because over there we're using type inference。

Clearly， this thing knows that this whole expression here is a card content factory that it's a function that takes an int and returns a string。

 so we don't need to say explicitly that it returns a string it knows can infer that same thing here we knows that the index is an int you don't need that and very nicely just to kind of remove excess parentheses if you just have。

That going there， you can just get rid of the parentheses。Also。

 we know that this memory game creation thing has two arguments。

 the number of pair of cards and the factory， and when the last argument is to a function or a crtcious。

 what can we do with it， we can throw it on the outside。

 trailing closure syntax so let's get rid of this whole thing。Close off are。Function there。

And leave that on the outside。 and since we're doing that， we can。Also do this。

Maybe me clean this up a little too， looks like that so that's pretty clean。

Through that all the stuff that was up in here， we just threw it right in line here with kind of minimal syntax around it and so we don't need this thing anymore just get rid of that。

couple more minor things we can do here， one is。This index here。

 if I were to replace this with0 and say this0， well 0 is a special name。

 okay Do0 means the first argument， and I could have dollar 1 2 however many I want。

 and if I use that special name， then I don't need to say dollar0 in。

So Do0 is a placeholder for the first argument if you pass it now。We could do that here。

 I would recommend against it here。 I don't think this is that readable。 In fact。

 not only would I bring back index， I would call this pair index in and call this pair index。

Just to make it clearer to someone reading my code， what's actually going on there？

Now it reads as the model is a memory game with this many cards and we create the cards by using this pair index index into this array kind of all makes more sense people can understand what's going on so dollar zero you'll see me use it later and you'll start to get the feel like oh yeah。

 I see why we would do Do zero there and we don't use it here。

The other thing I think kind of messy is that we've got this embedded array like right in the middle of our function。

 that doesn't really look good。 I think I want to take that out， call it something like emojis。

Say let emojis equal that。We don't we agree that that just kind of looks nicer。

 this is a nicer looking code， but we got a problem here and this is a big problem。

 this is an important problem to understand what's going on here。

 it says cannot use instance member emojis within a property initializer。

 property initializers run before self is available。Be intimidating to read this。

 but it actually makes a lot of sense。 So what is a property initializer。

 That's when you have a property。 remember I told you we call it vs and lets， properties and swift。

 So this is a property called model to v and I'm initializing it here And least I'm initializing this because if I dont I'm going to have to do it in it。

 So I wanted to essentially have a value to start。 So I'm initializing it I'm giving an initial value。

 This let emojis。This is also a property initializer because' this is just， it happens to be a let。

 but it's still a property and I'm giving it a value。

The important thing to understand in Swift is that the order that your properties are initialized is undetermined。

 it's not in the order you show them in the source code okay the compiler compiles them all up and they can be in any random order so you can't use one to initialize the other because we don't know when we initialize this。

 whether this has even been set yet because maybe we're doing this one first so that's why we can't use emojis there。

Well， that's a bummer because it would be really nice to be able to do this。

So how do we fix this problem？What we're going to do。

 I'm going to start by saying I can fix this problem by having emojis be a global variable。

so I made Mojis just be a global variable global to my entire program when I put lymph emojis up there that's global I could use that anywhere my views。

 my model is completely global now everyone in this class knows we don't use global variables they're bad they completely pollute the namespace。

 they provide access to things that you maybe don't want other people to see it in your code it's terrible。

 we don't use globals。😡，But it did solve the problem look I don't have that anymore because I'm not trying to use one of my other bars seems to flies as far so how can I get the best of those worlds here Now the answer is I'm going to put this back in。

 but I'm going to add the word static to the front of it and what this means is make emochi's global but namespace it inside of my class the real name of this v is now called。

Emojimemoryga do emojis。 That's its name。 This is a nice global variable name。

 It is not going to pollute the namespace。 Nobody else is going to name a variable like that outside of my class。

 and what's really cool。 private。 Now it's a private global variable only for us to use but it solves this problem very。

 very nicely。 And another cool feature is not really type inference， but Swift。

 if you're doing a property initializer like this and you use one of these namespace globals。

 You don't have to put the extra thing in there。 It'll figure out， oh， emojis。 Oh yeah。

 you probably mean this global right here， I'll use that。😊，So that's cool。Question。

Make sure that will be visualized。Exactly， the question is by making that global。

 am I making sure that it's initialized before I use it here and that's exactly what I'm doing because the global variables will be initialized first before my thanks。

That's static vs。 We can do the same thing with functions。

 What if I wanted to make a nice little function to create my model。

 So I'm going to create a fun called create。Memory， game。And it's going to return this。

So I just made a function to this and then I'll call the function here， create memory game。Oh。

 we have problems here， a lot of problems。Let's look at this problem first。

Cannot use instance member create memory game within a property initializer So this is a different problem。

 We're going solve it by using globals， but it's a different problem。

's I'm trying to use a function a fun in my class before I've even initialize my class right what am I doing here。

 but model equals this， I'm trying to initialize my model variable。

 I'm trying to initialize my class。 It's not initialize yet。

 So of course I can't call a function on myself yet So that's what this is saying here cannot use an instance member that functions member within a property initializer and that kind of obvious right I have to initialize myself first before I can start calling my own functions。

How do we fix that， we can also make that static a static function， a global function， it's inside。

 so it's called emoji memoryory game dot createre memory game in other words。

 the name of this function right here is emoji memory game dot create memoryory game。

What else we got here， this static funk return memory game of course it has a return value。

 it returns a memory game of string so that fixes this error right here where it's saying unexpected nonvo return value because I originally had no return value so it was void and yet I was returning something there also notice here that emojis which is a static bar can be used inside a static funk without the long name。

不要。Great question。Why can't we infer return types here？

Return types always have to be explicit that's the one thing you cannot be inferred in Sw can never infer a return type and when we say some view for the var body it's not inferring the view it's actually looking in there and seeing what returns and setting it to be that。

Model here， obviously since it's using a global now it does not need this because of this magic where Swift knows that if you call create memoryga and it's a global funk that's name spaced inside here。

 we don't need to put that in there and yes， of course we would make this be private。

Because we never want anyone creating a memory game for us。

 so this is our own internal thing we're using to create our memory game。

I like to put as a style thing， my statics at the top， they're global to my entire thing。

 I really want them to be listed first or sometimes we'll put them at the very bottom either the bottom or the top but put them together I think having statics scattered out through I'm not a fan of that some people might say that's good you put them near the code that wants to use them I buy that argument too but。

I like to kind of group them anyway， these two clearly go together and this is a nice creation of our bar yeah。

Yeah think。Yes。Yeah， and if you guys have done your reading。

 you'll know that these statics are actually called type variables or type functions because they're really a function on the type itself on theoji memory game type itself。

 I don't describe them that way in class because people get confused by that well type function I don't get it makes more sense to people as a global variable。

 this is names based in here， but they are in fact type variables or type functions that's a good clarification there。

Now we have seen these kind of global variables name spaced in other places， like over here。

 we didn't even notice it was happening in our view， how about this guy？This is actually color。

 orangerange。This is the type color it's astruct and do orange is just a non privatete static v so let's go take a look in the documentation here。

 this is like I did option click on something that's how you can see the documentation for it I'm going to open the documentation itself here's color。

You can see there's a lot of ways to create colors here， various ints creating in different ways。

 HSB or RGB， if you look down the bottom here， look static， let， brown， static， let， clear。

 these are just static， let fars， they're public so I can use them。And let's look at some other one。

 how about down here， font， this is font do large title， let's go look at font。Wen it up。

 scroll down， look at this。Rather large title title cea these are just static bars so when you see these dot whatever things they're one or two things they're either static lets on types or they might be enums because enums also have this kind of dot notation we'll see I'm going to talk about enums and slides right the start of Wednesday's lecturer。

So that's it for static vars and lets， the reason they're confusing to people is just because they look so much like a normal let or var。

 but they have that word static， which of course completely changes them to being these global namespace things or type variables or if you want to call them that。

 but they look so similar people get a little confused。

So we're actually done with our view model and we're done with our model except for it doesn't know how to choose yet so the next step is to use this interview but before we do that I'm going to show you just some swift code being written because I've hardly written any actual Sw code you know and like if thens and stuff like that we just haven't needed much of it I'm going to do on here what I'm going to do is I'm going to protect this line of code so that this array index is never out of bound。

So I don't ever want this thing to call me back to create a card with an invalid pair。

 now I'm sure my model would never be so rude as to do that。

 but I still want to protect myself and it's going to put a real simplest thing here I'm going to say if my emojis indices。

Remember what that is that's that range we use that in the4 each contains。

 so range has a function called contains where have something in there， this pair index。

Then I'll go ahead and return the emojis of that index。

 otherwise I'm just going to return some kind of like oops， emoji， let's go find an oops emoji here。

Mes and symbols， this one。And that's my oops emoji so if I start seeing that in my UI I got a problem with my model or my view model or something so I'm protecting it I'm also going to protect my model over here because what if you say the number of pairs of cards is zero？

That's not going to make much of a memory game。 In fact。

 even one is not a good memory game because you got to have at least two cars match。

 so I'm going to say Max。Two number of the pairs of cards。 So that means number。

 it's the number of pair of cards， but it's at least two。

 Max is just a little swift function takes a couple arguments。 It's generic。

 so the arguments could be。Floats or ints or whatever right。

 it allows you to do that of this and don't care as to what those are as long as they're comparable。

 that's what they have to be。It does that。Now it's time to use our view model if we go back over to here。

 we are going to use the green thing， which is pretty much done。

And the model which is done in except choose， we're going to use this in here to drive our stateless UI。

 so let's see what it looks like to drive that stateless UI with new model that we have right here in this view model only has two things cards and choose everything else is private so the only thing the view is going to use is these two things but that's really all our view needs be able to see the cards I can present them and when you tap on a card needs to be able to choose。

So that's all our view needs， it's also packaged up very nicely for our view。Let's go over here。

Before I do this， I'm going to rename this from content view to be emoji memory game view because again content view was just the default we got when we created a new project didn't know what we were doing so it just pick content view is the content of our UI and the way to do this is you command click on it and you'll get a bunch of options here which is kind of fun you can add some documentation which will put a little comment in there you can add methods and properties and you can also rename things and this is semantic rename this is a rename where it's kind of looking throughout your entire project and renaming so let's click that。

Here it is now it's searching through my app to find every place where I'm actually using this semantically and it even found some places where it's just mentioned。

 but it's not 100% sure like it's in a comment you see that second one up there and that one it's not blue so it's not going to actually replace that but if I click on it plus now it'll replace it so the ones that it semantically knows that's Con it'll queue it up to be replaced are the ones you might have to add。

This is my main program， of course content views at the top level of program so it's in my memorized app right there and then this is my content view that's my comment and the file name too。

I'm going to just change it right in line。Emoji memory game view。 That's what this thing is。

 It is a view onto an emoji memory game view model。 That's what it is showing up。A command click。

Command click select the content you to say command click in that ct that menu and feel free to explore that command click menu it's got a lot of cool little features in there。

Alright， so now I can hit rename up here in the upper right and it renames it you can see it renamed my file over there。

 it renamed my actualstruct， but it did not rename way down here my previews you see this preview here content view preview it didn't kind of figure out that that's what going I'm not sure why it doesn't do I'm especially not sure why it doesn't rename this one because this is semantically that content view Anyway。

 you got to do this manually Moji。Memory， game view。And I could use copy and paste， I guess， here。

 copy。Pce， and there is rename over here， too， in the navigator。 there's a replace。

 but that when you're just doing textual， find and replace。 it's not。

 there's no semantic knowledge there in that case。So we still have one important error here。

 which is that this var is never set。And so down here in our previews。

 what we're trying to create one， it's saying missing argument for that parameter。

So we have to say view model something here。I'm going to postpone doing that。

 but sort of cheating and just say。Equals emo memory game。

And this is bad don't never do what I just did this is just just because I want to postpone doing the right thing until I can explain some other stuff to you。

 the endeavor would set your view model this way， I'm going to show you how to set the view model soon but you would never do it that way。

I know you probably hate it when I say that， but some things have to be done in certain orders。

 unfortunately。So now we're going to do this using view model in a view and really this is quite simple。

 we're just going to get rid of all the stupid ads state we had for the demo and use our view model to get all the data that drives our view。

I'm going to start right down here in my card view。I'm going to get rid of that。

And I'm going to replace it by having card view have only one argument， which is a card。

It's a card view， it's supposed to show a card， so we should give it a cardness to go here and say。

Var card， which is a memory game of strings card。And I'm actually even going to make it a let because I can't default it to anything and once it's set。

 I'm not going to be updating it inside of this card view。

Now you might say what about is face up you're going to be updating it here， no。

 because this tap gesture thing it's not even going to be in here。

 it's going to use the intent in the view model so it's not going to be changing it locally here so we can in fact just get rid of this entirely。

We'll put it back in when we have got our viewmod going here and then we just replace our content so our content here is now the cards content remember that memorygame。

 card it has the content which is this don't care， which is a string for us and is face up similarly card has is face up。

So also。And that changed this。Card view into truly a card view。 It is a view on a card。

And if we add things in the future which we're going to like is matched right we don't use is matched。

 but when we do the is matched up， it's going to be in here because the card view is the thing that draws a card so that really is nice not just in making our code simple here。

 but it kind of semantically conceptually makes sense that we've got this card view and it draws a card。

And then back up here， the other thing problem we have some space here。This is over here。

We've got our emojis， this emojis up here so emojis now are handled by our view model。

 so we' not going to have emojis in our view right here and instead of iterating through our emojis。

 we're going to iterate through our view models cards we're going to go through each of our view models cards。

 the indexes are view models cards and of course we know our card views don't take content anymore。

 they take cards so we'll say it's card is view models cards at that index。Simple。

We understand what we did there？We're just for reachinging through the cards now instead of forreing through that emoji thing。

 and then we're going to pass each of the cards down to the card view。All right， no errors。

 no warnings that all is really required， let's take a look and see if it's working。Preview on pause。

there it is nice now of course can't see our cards so we're not really sure it's working。

 but let's flip those cards over and look at them the other way around Now how do we do that。

 we go to our model or to our view model because that's where the truth is now so we don't even touch our UI if we want to look at these cards face up we bounce over here in this case to our model and we're going to say that all cards start face up instead of face down and we're going go back here。

Get this thing to rebuild Boilla， we see all our cards face up。 Similarlyly。

 the number of cards that's in our view model。 it controls that。 So let's go change to6。

Here rebuild Now we have six pairs of cards。 One thing that was kind of annoying here is every time I went to my model review model。

 I lost my preview。 I can't see my preview anymore。 Well you can pin it。

 you see that little pin that will pin this here so that even when I go over here and change something it stays there。

 let's go 10 cards。It'll change right in line here and we can see 10 cards。

 or even if I make too many cards like。16， we'll get those little。

Question marks because we have too many more cards than we actually have in our array。

And that's all happening， the pinning is what's keeping this here as we change our model of view model。

Pretty cool， pretty easy， makes the code really nice。 I could make the kitely nicer here in my view。

 by the way， which is right here。 you see this card view cards。 that's redundant again。

 that's like we had what that other thing to choose where we put the underbar in there。

 We got the same thing going on here。 This is a card， this view model cards add an index。

 That's a card。 We don't need to say card here。😊，But whoa。

 how are we going to fix that because that's not a function， that's the creation of our card view。

 that's the automatic in that's getting created for our struct that initializes that uninitialized card。

So the only way to get around is。Provide an in if we provide an in。

 we get to control that external thing。 so I'm going to say in it and you can even say tab to make it created for you and you'll even put this little line here self doc card equals card So this is equivalent to the free in And when I hit in knit tab I got the free in This with the free of an it and I'm going to change it just ever so slightly to have no external name。

Just like I did the other thing， let me go up here， get rid of that。That looks a little nicer。

The next thing I actually want to do is add some UI to our app here which is a shuffle button that shuffles these cards because shuffling the cards really will help us understand what's going on in these are internal data structures when they're moving and how our UI reacts。

 but before we do that I want to make one small change that I didn't get to make at the end of lecture too because we were rush for time which is I want to change the size of these things to be not so small we see how their font large title but even large title it's just too small。

 I want them to be as big as their card will allow。So I'm going to do that？

First thing I'm going to do is see that lazy V grid up here and I promised you that I was going to explain all this to you and how it works and I am going to。

 that's going to be in lecture what is this lecture4， lecture six。

But I'm just gonna to do something real real quick here， which is I am going to。Set the spa in。

Both vertically and horizontally of this thing。To be zero， see all my cards。

 they have no space between them。 and then I'm going to use padding。To provide the space。

And the reason I want to do that is， first of all， this is simpler to control if I wanted more padding or less one number and so having to change both those spacing numbers up there。

But you' also see that it's going to lead into the other thing I'm going to do which is try to pick the size of this card that fits nicely and when we do that we want to be have the padding be taken out of the equation。

Now I want to do that font thing， I'm just going to go down here to thispon large title。

 get rid of that。AndInstead I'm going use font system font of size and let's start with a really big font Okay so that's good。

 I can see those a really great。 Unfortunately it's doing two things wrong one it's getting cut off because the minimum width of that lazy be grids keeping these minimized but the height can be anything So it's getting cut off and two it's controlling the size of the cards It made the cards bigger I don't want that I want the cards to be their normal aspect ratio which this is not and I want the thing to fit down Well incredibly there's a fantastic little view modifier。

lled what do they call that big minimum scale factor？0。01。

And what minimum scale factor says is if this font is too big。

 you can scale it down all the way down to 1100 of its size， that's what this 。01 so that's great。

 that's working a lot better， it's scaling it down but it's doing the vertical size you see so it did scale it down but these things because our aspect ratios that way they're still not quite fitting。

Easy fix to that。How about dot aspect ratiora1？Content mode fit by making the aspect ratio of this text be one to one。

 It has to fit that inside our 2，3 aspect ratio。 and now it fits。 So this is now fitting anything。

 Let's go back up here and make our cards。 Let's say really big 120。Pits perfectly。

 make them really small， about 45， they fit down in there。So let's go back to a size that we like。

 what do we like 85？Yeah， 85s pretty good size。Let's go and do what I was saying。

 which is adding shuffling to this， I'm going to just put a little button on the bottom here that shuffles the cards。

This is the kind of thing we all know how to do now make a VStack。

It the scroll view of the cards and then it has a button， which we'll call a shuffle。And inside here。

 it's going to ask its view model to shuffle。 So this right here。

 this view model shuffle is an intent。Remember I talked about the way the view talks to the view model is it has these intents and these intents are user intents what the user intends and the user intends when it clicks up well please shuffle the cars now we don't have that intent in the view model that's why it's complaining about it so let's go add it。

 we go over here， put it down here and I may even going to create a little Mark dash intent。

And then say funk shuffle。This mark， if you put plus mark dash。

 then up at the top here in your navigation bar。You'll see that intenses will get its own little lined off space。

 you see how it got its own space up there。As you're kind of navigating around。

 you can make your own little。a slash s mark if you don't put the dash。

You still get the little marker， but there's no line in front of it。Right。

 no line before the intent there。Intense or important we'll give them their own little line off space and how would we shuffle the cards well one way we might say it is oh。

 I'm going to take the model's cards and shuffle them。Now this is not going to work。

Why is this not going to work， Because we cannot use a mutating member like shuffle on an immutable value。

 cards is immutable Oh yeah。Is it。Oh， it is。 Look at that private set。We can't touch those cars。

So are we going to shuffle the cards Yeah we're going to have to have the model support it if the model doesn't let you muck with the cards。

 then if it's going to allow shuffling it has to do it so I'm going to have a funk shuffle。Here。

 and I can shuffle my own cards。Because I'm inside my model here。And then back over here。

 we will just say model， please shuffle。So again， this might seem like， what a。

Ways to have these one liners here， but this is full gatekeeping mode。

 which we probably don't need for memorize games so simple。

I want you to see how you do the full gatekeeping， this is how you do it。

Here we are in the model and we said shuffle here and it's complaining even inside here。

Why is this complaining inside here， I'm clearly the model。I can private set， I get to set。

 why can't I shuffle my own cards here？And the answer here is that self is immutable。

 self meaning the model is immutable so if the model is immutable， how does it ever change anything。

 how does it flip over the cards or do anything， well it can。

 it's just that any function that can modify the model has to be marked mutating。

Why does Swift force us to put this mutating here， clearly Swift knew it was mutating。

 it gave us that warning so it knew it doing it， well it's saying put that there so that you know that you're doing it because someone calling dysfunction function is going to cause a copy on right。

Remember， I told you Swift does copy on right， itss value。

 we're passing these arrays of cards orre passing the whole thing in there。

 and only when someone touches it， then we actually make a real copy of it， that's how it knows。

When it says is a mutating function， so it wants you to know that if anyone calls this。

 Swift is saying， I'm going to do a copy on right for this， so I hope that's what you intend。

Everyone to understand that， so Swt will not let you mutate your own struct without putting mutating on there。

Let's go back to our UI right here and resume。We've got shuffle down here。嗯。嗯。

What's going on here I don't it's not shuffling these cards what is happening here Well。

 actually it is shuffling the card it shuffling them beautifully and let's go into our model and see that that's what's happening I'm going to go here where we shuffle I'm going to print the cards out。

Now when we did print before， I think we said print quote toggled。

 remember that when we were doing the on tap gesture here I'm saying print cards to cards is an array of cards and it allows that so what happens when you print some random struct well Swt is really good at turning it into a string。

It's a little bit of a verbose string， and we're going to show you a little bit how to make it less verbose。

 but we're going to be able to see what's going on。 So let's go down here to our console。

 Remember to drag up from the bottom。And I'm going this is the debugger on the left and the console on the right so I'm going to close the debugger to give us a lot more room in here and I'm also going to put it on previews mode now some of you don't have access to Xcode 14。

3 so to do what I'm doing here you're just going to hit the run button and run it on your simulator and then the will come out here from the simulator but we can do it in the previewer here so let's go down here and hit shuffle。

Whoa， so it's printing all of my cards out there。Very verly but it does appear to be shuffled you see that this is the array here's one card from here over to here really long names see telling me all the vs。

 everything all the content and then these are all the cards and it is in some random order so it's definitely shuffling the cards so why are you why not updating。

Well。It's because of this reactive UI， this reactive part。

 you have to do a tiny bit of work to make it work okay just a tiny couple of protocols you need to use is real easy。

 so let's do that。We start with our view model right here。

And we have to make our view model behave like a view model。

 essentially behave like something that says something changed when things changed。

 we do that by making it implement the protocol observable object。Make sense， right。

 It's an observable object and this observable object protocol has a var in it。

 I'll put this far so you can see it。 It's called objectject will change don't worry about the type right there this object will change var is the var that you send a function to when you want to say something changed so right here when I do shuffle I could say object will change dot send and that says this object will change noticeice is object will change not object did change So actually when I said in that other slide。

 something changed it's really something is about to change so get ready and system gets ready and then less the change is happen and then the view can look at all the changes。

And we're not going to talk about why that is， but it actually makes a lot of sense to kind of queue up that there's going to be a bunch of changes and then see what the differences are once all the changes are made。

But the great thing is you're almost never going to call this and you don't need this var and you can see that it's not even required。

 it's not saying it's not like var body where it's saying where's your object will change。

 it's provided for you behind the scenes you don't do that so how do we get an observable object to say something changed。

 we mark any var that can cause that as published if you put outside published on a var。

 then if this var changes it'll say something changed。

And this is the primary way that we do the something change。 We just mark vs。 Now this v is private。

But that doesn't matter， okay， private just means that the view can't see it。

 but that doesn't mean it can't cause something changed， it can。

It has nothing to do with publish in private。People get confused because publish sounds like you're making something public。

 but it's not about that。 Okay， publish means make something changed happen and then over here in our view。

 we have to mark this v right here， our view model as an at sign observed。Object。

Means that it is observed。this only you can only mark a var that is an observable object to be observed object and what observed object there means is if this thing says something changed。

 redraw me。Now it does that super efficiently told they're going to redraw the abuse that actually have changed because of that change。

 but that's what that mean observed object there。Now when I put that on there。

 this makes a line of code， I never want you to ever write in your entire swiftif program career。

 which is you have observed object and you're saying it equals something。That is a major no， no。

Observed objects always have to be passed into you because they have to be marked as truth as state an observed object is not a truth thing。

 It's just saying I'm observing this thing so never say equals there if you really feel like you had to do that you could use a different one here called state object remember we had outside state this is outside state object but this is really not that much better than just doing at sign state and your model because it's only inside this view so you could never share this view model with any other view because you this is at sign state's an object because it's a class inside your view so you wouldn't do that So how would you do this Well you would make this be observed object。

And you wouldn't have this be here。And instead， everyone who creates this would pass it into you like any other struct right you have a var here that's not initialized when you create it。

 so for example， in our preview we create it so here I would say my view model is and I'll just create it on the fly here。

This is okay to create on the fly because your preview is constantly getting redrawn all the time anyway。

 so you don't care that it's created on the fly， but the other really important place you would change it is in your app。

Right here。View model， I'm going to call this game， and this game would be an at state object。

In your app。So apps like views can have at signed state objects。

 but somewhere there needs to be state Now you wouldn't always have your view model be created at the app level because maybe you've got some like maybe you're doing an app with 20 different games memorize just one of them you might have a view that shows thumbnails or those 20 games okay and you click on them and it plays them maybe the at signed state object is in that view because that is the top no one would use it any higher level me or I'm saying but somewhere it has to be at signed state because it has to be marked as truth and at I observed object I'm surprised they even allow it I think they should not allow I think you should not be able to say。

Equals anything at the end of here， I just think that that causes way more problems than it fixes。

All right， so now hopefully we have a reactive UI， let's try it here and here， shuffle， a good eye。

Cufflelin。Perfect timing。What we're going to do next time is I'm not going to teach you animation。

 but I'm going to use animation to show you all about protocols and care little bits and all those kind of things that we saw in the slides because we'll need all that to make animation of these cards shuffling because I want these cards to fly all around the screen when we shuffle and then of course after we do the animation here I'll show you how to do the game logic which is 10 lines of code to make the entire memorized game logic we'll do that all on Wednesday it's going to be type but we'll do it。



![](img/557b24fc4abf8c191590fa0977410578_4.png)