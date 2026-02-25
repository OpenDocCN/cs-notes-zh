# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p21 -P21-Lec 20 - First-Class Functions - Part 1, Reproduced for Fall 25.zh_en -BV1zQ27BeEfF_p21-

Okay， hello， everybody。Thank you for welcoming back after I had to be away from y'all on Tuesday。

 Wist was a lot of fun。 So for those of you who are interested in HCI， consider WISist。😊，嗯。

I don't really have any logisticacy things today， so I was planning to just dive right in on content。

Anything that should stop me from doing that， or we feel good about diving in。Fabulous， okay。

 so today。You know， I， I obviously， I shouldn't play favorites with my own course content， but， but。

This stuff that we're doing today that we're doing next Tuesday is really pretty cool。

 I think this is gonna be a good time。 I'm super excited to get to share it with youall。

 So today and next Tuesday， we are finally， finally， finally。

 after all this time getting to implement first class functions。

 So this is something that there were various questions that came up way back when about functions back when we were first implementing them that we're sort of pushing in the direction are we gonna have first class functions are we gonna to first class functions for many different ways。

 And the answer， of course， was， yes， we are going to implement first class functions。 And today。

 finally， is that day。 So it's gonna be really exciting。

 I have a couple of sample programs that I have put up here that are going to help us get a sense of what we mean when we say first class functions。

 So I'm going to ask you to turn to someone nearby。 And it's okay。

 if you've never heard this terminology before， first class functions。

 But based on the programs that you're seeing up on the board。

 can you come up with some hypothesis about what first class functions might mean。

 And then we'll go ahead and talk about it together。😊，Alright， so do we have any hypotheses？

 What do we think it might mean。For our language to support first class functions based on these programs。

I love it。 So this answer was basically， what if we can use a function as an argument to another function。

😊，So I love it。 So basically， what we're saying here is we can treat functions as values。

 So I'm going to go ahead and point to what's happening here in this very first example。

 which really is that， right， So treating functions as values， treating。😊，Functions。It values。

Let me say， function pointers。So this is the first thing we are going to be dealing with。

 So we have actually broken down the process of implementing first class functions into sort of three stages that are going to correspond to what's happening in these three programs。

 So in this first program， we can see that， you know， we still have this program。

 we still have this function， Mo M2， sitting at our top level right So it's still in those top levell definitions And the only thing that's really different from the programs that we have implemented so far。

 the programs we've been able to run so far is just that now we are able to actually treat that as a value。

That's the big change that's happening here in this first program。

 And then we can see that something else is happening in the second program that's maybe even a little more complicated。

 which is we're getting this anonymous function， right， So all of a sudden。

 this isn't something that we actually see at the top level。

 we can actually go ahead and look over here and see that， okay， actually。

 there's only this one thing F that's made available at the the top level definition side。

 but we still seem to have been able to actually create another function sort of right here without actually naming it。

And so that is anonymous functions。Should I always struggle to spell？Lambdaos。

'sThe other thing that you may have heard those called。And at this point， basically， I mean。

 obviously， all the functional programming languages you've interacted with have had Lambdas。

 but probably even at this point， the the various nonfunctional languages you've interacted with have probably implemented some kind of support for Ladas for first class functions。

 So this is something that you've started to see。And then there's something even slightly more complicated happening in this last program。

 So let's take a look at what that is。 So here we have this anonymous function。

 this lambda down here。 and we can see something interesting happening where we are actually using this value Y。

 but Y is not one of the parameters to our anonymous function。 This Y is coming from somewhere else。

 Where it coming from well， it's coming from this lip binding that's happening outside。

And so in order to actually support that， what we're going to need to do is something called closures。

But for the purposes of today， all we are going to be tackling is definitely this。

 And then if we have time， we'll also get to this。 So we're going to go ahead and break it down。

And probably this is what we end up tackling today。Now。

 why are we breaking it down into these three stages， This is not actually required， right。

 We could jump all the way from where we are right now， all the way to fully featured。

First class functions。 that would be totally fine。 The reason we're breaking it down is that this is pretty advanced stuff。

 Like this is actually beyond the point of what most undergrad compilers classes tackle at all。

 It is very rare for undergrad compilers courses to actually teach y all how to do first class functions。

 And so we are getting into some pretty advanced stuff。 If you remember way。

 way back when we started talking about why are we doing all this And O Camel。 and we talk about。

 okay， it's gonna to let us build more compilers more rapidly。

 And that's gonna give us time to do sort of the fun， exciting fancy stuff。

 This is what we're talking about。 right， Here's the payoff。

 Now we finally actually have the time to go in and start doing these really advanced programming languages features that would be really difficult to fit into a compilers class otherwise。

😊，So we're taking advantage of that。 But since we are now dealing with some pretty advanced stuff。

 we're going to try to break it down into stages。 and we're going sort of implement this one piece at a time。

O。Are we feeling pretty comfortable with the idea that first class functions just means being able to use functions as values。

😊，So far， so good。Fantastic， all right， so let's go ahead。



![](img/2248c37dab8bef217426d4f5fc0135eb_1.png)

And take a look at where we landed last time， last session。



![](img/2248c37dab8bef217426d4f5fc0135eb_3.png)

So we had gone ahead and done this interesting new thing。

Where instead of operating directly on our S expressions。

 we had decided to first transform from our sort of original S expression。Format。

Into something that looks closer to the format of the constructs that we are actually implementing。

And so we had this AC。ml thing and where what we're doing inside there。

 part of what we're doing is actually transforming from things that have that S expression type into things that have the expression type that we are now going to operate over。

 so if we take a look at interpret。 M， what is actually going into Inter X is no longer an S expression right instead we are getting something of type X。

 same deal if we take a look at our compiler。We can see that we are now operating on things of typey X。

 and we can see that our matches are looking somewhat different because we are now taking advantage of that sort of customized style。

 right， We are now getting things in closer to the shape we actually want to interact with them with。

And so we're seeing that that is all happening right here in ASC。 Ml。

 and what's happening is what's going in is an X expression。

 What's coming out is this new expert type， and we can see that basically all of our old match cases are sitting around in here right so this is how we used to actually match a let。

And what's coming out is just the new representation that we find somewhat more elegant。

 somewhat closer to the language that we are actually trying to interpret。And compile。

So that's where we left things before。 And the reason I remind us of what's happening in here is because we are now implementing a new language feature。

 and I mentioned when we made this transition that we may now have to actually change our ASTs。

In order to actually implement new language features。

And so what I'm going to ask you to do is take about a minute to discuss with someone nearby。

 Are we going to actually need to change our AST， right， change what happens inside our expert type。

 Are we going to need to change that。In order。To do this， this change that we're making。

 where we're going to have first class functions， we're going to be able to treat functions as values。

Discuss for one minute。All right， I'm hearing you still some confusion about what's going on with our new expert type and the。

Transition from SX to Exp。 So are there any questions about that before we return to this question of do we need to change it for this new feature。

Or maybe we actually are feeling comfortable with expertt and I was just。Hearing wrong。Okay， well。

 I'll just remind us of the question then， which is that what we are thinking about right now is we have this new expert type。

 and this is now what we actually feed into our compiler and into our interpreter。

And now that we want to actually introduce first class functions， right， the ability to treat。

Functions as values。 Is there anything we need to change about our expert type in order to do that。

Go ahead and discuss for another half a minute。All right。

 if you think that our AST is already good to go， go ahead and hum for it， we are good to go。

If you think we're going to have to change our AST。

 go ahead and hum for you think we're going to have to change our AST。Yeah。

 I completely agree so there is。A bit of a change that we're going to have to make here。

I think there was some uncertainty around that， so I'm going to actually draw our attention to one particular line and then see if you and your neighbors can figure out what we're going to have to change about this particular line。

Go ahead and discuss for another 20 seconds。

![](img/2248c37dab8bef217426d4f5fc0135eb_5.png)

Alright， to help us think about this， I'm just going to highlight this part of this program that we're going to support。

 right。

![](img/2248c37dab8bef217426d4f5fc0135eb_7.png)

And so this is kind of the， the kind of thing that we might be about to interpret or compile that is going to have to be treated differently。

 So if we take a look at what are the top level definitions here。

 We can see that we have a definition for F。 we have a definition for Mo 2。

 We don't have a definition for G。Right， so all of a sudden， if we were expecting， okay， yeah。

 that string G， that is going to be enough for us to find the relevant definition。 In fact， no。

 right， that isn't going to be enough。 So let's turn back to。Over here。

 And what we can say is I am now expecting this to be not a string， but another expression， right。

 Maybe we've actually done something even more complicated where we've actually， you know。

 we've made a pair of functions。 And now we're going grab out the second item in that pair。

 as I like， there could be all kinds of stuff that is happening in there。

And we are actually going to need to figure out， okay。

 what is the actual function value before we try to go ahead and call it。 We can't be just demanding。

 okay， a particular string is going to be all we need there。

And what else are we gonna have to change Well， if we take a look down at expert of S X， Well。

 that's probably gonna to have to change because we can see that right now， right， it is demanding。

 okay， it's gonna to have a string in there。's kind of how it's been set up so far。

 So let's go ahead and say， okay， this is not necessarily going to be a symbol anymore。

 This could be any number of things。 And what we're gonna need to do in order to figure out what it should actually be be pointing us to is we're gonna have to go ahead and call the exact same thing。

 So expert of S X， right we're making that recursive call on that expression And that's how we're gonna actually convert that into an expression that we can then feed into our interpreter or compiler。

Are there questions about that before we actually use this to change the interpreter and the compiler？

So far， so good。All right， so we are now ready to extend the interpreter。

 And I think there's one thing that we're definitely going to realize pretty quickly that we're going want to change。

 So it looks to me as though right now， we don't have any value that would be a reasonable representation of function。

So let's go ahead and add。Function of but function of what。

 So go ahead and discuss with someone nearby for about 30 seconds。

 What what youd like to have in here。 And I'm going to say right ahead of time。

 there are multiple different reasonable answers here。

 Like none of these is necessarily going to be wrong。

 We are just going to happen to choose one for design reasons。

 but there are multiple reasonable answers here。All right。

 so I'm going to run us through a couple options here。 so here's something we could do。

 We could do string list。Paired with expert。What would we be representing there while we would basically be saying。

 okay， here's my list of arguments。 here's the expression associated with the body。

 This would basically be representing all of the same information that we're currently representing in that definitions list。

 And so then when we encounter one of these。 we could say， okay， at that time。

 I'm going to go ahead and just use that。In order to do my call。Would be totally reasonable。

Here's another thing we could do， right？ So one of the things that we have traditionally done in our interpreter is said。

 you know what， Oamel has already implemented a lot of things for us。

 Let's see if we can just piggyback on that existing implementation。

 And so we could do something like value list。To value， right。

 let's go ahead and just have an Ocal function， and that can be our function value。 Again。

 that would be totally reasonable。 We could absolutely do that。

We are going to go ahead and do something a bit simpler， in part。

 because it is going to look more like what we're going to do in the compiler。

 And it lets us keep the structure a bit more consistent。

 So I heard some folks in the seat saying this， we can just do function of string， right。

 So we have that name that we can use to say， oh y， that is， in fact。

 this particular definition right， we can go ahead and look over here and say， okay， yeah。

 any of those things highlighted in yellow。 that is going give us a unique identifier for the particular function that we want to use。

 So we're going to go ahead and actually use that。😊。



![](img/2248c37dab8bef217426d4f5fc0135eb_9.png)

![](img/2248c37dab8bef217426d4f5fc0135eb_10.png)

![](img/2248c37dab8bef217426d4f5fc0135eb_11.png)

Now。How is this going to actually be enough information for us to implement first class functions？

Hopefully the the sort of example that I just gave over here is sort of giving us some of the idea。

 right， So it's basically going to look a lot like what we've been doing when we've been looking things up in that definitions list so far。

 right， So we've been able to do this thing of saying， okay， I know the name。

 I want to go ahead and just grab it out by the name。😊。



![](img/2248c37dab8bef217426d4f5fc0135eb_13.png)

So that's how we're actually going to be doing it。So let's go ahead。



![](img/2248c37dab8bef217426d4f5fc0135eb_15.png)

And start implementing。 So OcaMl has helpful highlighted for us one thing that we're definitely going to want to change so we can see that down here。

 this is no longer comprehensive。 Let's make sure we are covering all of our constructors。

So for function， regardless of name， we are going to provide a very unusful output。方ang生eng。

Don't recommend doing this if you are actually implementing a language， but for today。

 we've kind of thought about printing already， and it's not super helpful。

What else are we going to need to change？ Well， there's certainly one spot that looks to me like a very plausible target for change。

So there are a couple of things going on here that aren't really going to make a lot of sense anymore。

So what about， for example。This line。Go ahead and discuss with folks nearby。

 Does this still make sense given what we're doing now？So what do we think。

Say that this is you know left of pair of function1 and function2。

Do we think this is going to work come for yes？Hum for no。Yeah， okay。 so we have some uncertainty。

 but it seems like we're leaning no。And so this is not going to work because of exactly the example that I was just giving right。

 so this is now a full on expression。 It is not just a particular name， right。

 we could have if we're looking at what this actually is right well。

 it still thinks is a string because it hasn't actually been compiled yet。

 but if we take a look at what it says in AST right。

 we know that what we're actually going be getting over here is something of type expert。

 it is no longer a string。So we're going to want to go ahead and make sure that we are treating it as an expression。

 right， So we're going to have to actually go ahead and call Inter X on it in order to get the appropriate function value that we can then use。

 So we're still going to want to figure out at some point， whether it is definition。

 but not at the point right where we see the call， because it could be that what's happening inside there is all kinds of wacky stuff that will eventually once evaluated。

 give us a function value。 So let's go ahead and do that check a little bit deeper inside。

 So we'll go ahead and do let Fv where Fv stands for function value。 We'll interpret X。Dens and。F in。

 and what do we want to do once we're in here。 Well， we do still want to do that check。

 We do still want to make sure that we are actually getting something of type value。

 So let's go or sorry of type value that is constructed with the function constructor。

 So let's go ahead and making sure that we have pars in a way that is going to protect us。

Let's go ahead and do a match。Match F V with。 and what is the case where we know what we want to do with it Well。

 if we find that we have a function。The particular name。And when is deafin。Deefin's name right。

 so here we've just moved that check over here。That is the case where we want to do all the stuff that we've been doing up to this point。

If we have not all the way up there， let's indent those if we have anything other than。

Something introduced with the function constructor。 Then that's where we're in trouble。

 So let's go ahead and in that instance， let's say， raise。That expression。

Because there we don't actually know what to do。Now。

What else do we need to change while we know that we no longer use F as the name right。

 so we're going to use that as name， right function name。

 that's what we're actually going to be using there。

And the other thing that's kind of wacky now is we now have。All of our cases covered here， right。

 we're not going to need this anymore。So that's a big change for us as well。Okay， so far， so good。

 Let's raise bad expression on something useful， like X。This is looking pretty good。

 But what's sort of a weird thing that's happened up to this point， right， So right now。

 we are expecting。That we're going to get something created with the function constructor。

But have we actually introduced anything that uses a function constructor。

 have we made one of these anywhere？See some shaking heads， and I agree， right。

 We haven't actually created one of these yet。 So I'm going to scroll us down to a part of the program that I think we might want to look at as we consider our next question。

So taking a look sort of over here。What is something that we might need to change？

In order to make our new。Implementation for call work。Go ahead and discuss with someone nearby。

All right， so I'm looking at this and I'm thinking to myself， it really seems like。

We're good in the case where the new value that we have introduced in a program is something that we're putting inside our symbol table。

But that， of course， is not actually what we're doing。With our definitions， right。

 those are going somewhere else。 So we're going to have to go ahead and make sure that we can do something else to handle that。

Let's do。And what is going to be are when in this case， well， when is deafin。Deendens there， right。

 So if we're going ahead and seeing a use of a name and it's not a name that we have put in the symbol table。

 but it is a name associated with a function。Then we're good to go and what we're actually going to want to provide。

Is a function。AValue that is pointing back to the particular name used for that function。

 So let's take a look at one of our example programs just to think this through。

 So here we are in our example program。

![](img/2248c37dab8bef217426d4f5fc0135eb_17.png)

![](img/2248c37dab8bef217426d4f5fc0135eb_18.png)

And。We have found that， okay， we are， we are using a particular name， this name Motu， right here。

 right。And we've found， okay， this doesn't seem to be showing up in the symbol table。

 What should we do， given that it's not showing up in the symbol table。

 which is normally where we would look for， for a name like this。 Well。

 given what we have just implemented， we'll now fall through that symbol table case， and we'll say。

 okay， is this in our list of definitions。And we'll see， oh， yep， this is， in fact。

 in our list of definitions。 Good to go。 Let's go ahead and make sure that what we are actually providing here in that case is going to be a function value。

So that's the case that we're handling right there。

And as we've already reasoned about what we're actually going represent in order to represent a function value is we' are actually just going keep track of this particular name。

 right We can actually use that name to get us all the information that we need because we actually know from our our definitions list that this is the the associated function definition for M2。

 It has these arguments。 And it has this body。 and we can go ahead and retrieve that just based on knowing this name。

Are there questions about that transformation that we just did？



![](img/2248c37dab8bef217426d4f5fc0135eb_20.png)

Great question。 Okay， so say that we have introduced a name N。And we have bound it to three。

But then we try to actually use a function。Named N， and we try to give that a new name。

What is going to happen？Go ahead and discuss with someone nearby。Okay。

 so who thinks that that new binding we're doing， that that is then going to get the value of the number that we originally bound to N。

 Home for， that's going to get the value of the number that we originally bound to N。

Hum for that is instead going to get the value of the function that is named N。Yeah， I agree， right。

 So we remember that we're going through these in order， right。

 So we're going to actually go down this case。 So if we have this name repeated。

 this is the case that will actually go down， not this case。Yeah， great question。Other questions。

Okay， looking back at our AS T here， we're saying， okay。

 we no longer want to have just a string here。 We are wanting to have an expression。

 And so let me actually write out an example。

![](img/2248c37dab8bef217426d4f5fc0135eb_22.png)

Of what we could be doing here， so。Maybe this is going to help us think about it。



![](img/2248c37dab8bef217426d4f5fc0135eb_24.png)

So say that we had。Define。呃。F。A。哒哒哒。Define。G A dot dot dot。And then down here in the body， we had。呃。

Let's see。First。Pair。Gf。Called on3。This is a weird program。

 but this is a program that we should be allowed to write。Now， what's happening here。

Is that we actually am going to change the color here to represent what's happening。

 We are calling the function associated with evaluating this expression。Right， because again。

 we are now allowed to treat our functions as values， right。

 We are no longer just using their names for them。 We can represent them with whole expressions。

 And so if we had just said， okay， I want to have a string。

As that that first element associated with a call， right。Then when we are actually doing our parsing。

 we would try to say， okay， I want to go ahead and actually call the function Pren first Pren pair G F Pren Pre。

 right， Not a great name for function。 And not， in fact， the thing that we actually intended， right。

 We really do want to be allowed to put expressions there where we would be expecting something of type something that is created with the function constructor for value。

 Does that make sense。Other questions。

![](img/2248c37dab8bef217426d4f5fc0135eb_26.png)

Okay， cool。 let's go ahead and continue。To our compiler。

 so we are now happy with where we stand with our interpreter， but of course。

 there are some things that we're going to need to change in the compiler to make sure we are good to go。

 So I'm going to go ahead and make a couple of changes preemptively that I think are going to signal to yall some of the changes that we're about to make。

 So first thing we're going to do that let's go ahead and introduce a new tag。😊。



![](img/2248c37dab8bef217426d4f5fc0135eb_28.png)

So what。Tag。And what tag do I actually want to use， Let's use。That。

So there's a tag we're going to go ahead and actually get。Another one of our little helper functions。

 right， So here we have insure numb and insure pair。 Let's go ahead and make an insure FN。

And what are we going to have to change while we're going to still want to compare with the heat mask。

 But let's use the function tag。 So based on the changes that I have just made。

Go ahead and discuss with someone nearby。 What would be your guess about how we are going to represent functions at runtime。

 What are we going to put inside R A X。To represent a function。All right。

 so hopefully we've all landed on something in the general region of this is probably going to be a memory address。

 that is exactly right。 What we are going to do is we're actually going to use the address of the function。

As our way of representing the function， right， so at that address of that first instruction。

 you might be thinking of it as the address of the label。

 That is how we're actually going to be keeping track of what is the function associated with a given value。

So now let's go ahead and actually make sure that we are able to use those last three bits as zeros in order to actually use our function tag。

 So let's go down to。😊，Compile Din。And make sure because right here we can see that what we're doing right now is we're just admitting that label。

 we haven't really done anything special to make sure that it is aligned that it would actually have those three bits available for us。

 let's go ahead and just real quick add line 8， I know it's something y'all have played with in your homeworks before。

 so hopefully that isn't too surprising。O。So that's making one big change that's going to allow us to actually use that tag。

 That is going to be very helpful。 What is the next thing that we're going to want to do， Well。

 let's go ahead and this time deal first with our ver case rather than with our call case because our call case is going to be somewhat more complicated。

So as before， we are going to want to add an additional ver case。

 in addition to the one that we are currently using that interacts with the symbol table。

And so what are we going to want to put in here？So I'm going to go ahead and actually start writing out。

What the match case is going to look like， but I'd like you to discuss with folks nearby what should be inside it。

Remember that our goal is to represent。This function value inside RAX。Okay。

 so hopefully this looks familiar from homework， we already know how to actually get the address associated with a given label in this case。

 the label associated with the definition， we already know how to get that into RAX using Lla and we already know how to actually do our tagging so this isn't actually all that dissimilar from stuff that we have done before。

Are there questions about this before we move on to how we're actually going to change calls because that's where it's going to get somewhat more involved？

So far so good， we buy that this is actually a way of representing our functions in RAX。Yes。

 so this is going to give us an opportunity to sort of break down in one of the layers of abstractions that we've been sort of keeping for ourselves。

 So once our assembly has gone through the assemblymbler and gotten turned into machine code。

There are no labels， right， We have been used to thinking about it as though those labels are things that exist long term。

 But in fact， what happens is those get stripped out and all uses of of them are getting replaced by actual addresses。

 So when we talk about the address associated with the label。

 what we really mean is the address associated with the first instruction after that label。

Does that make sense。Yeah， great question。All right， so let's go ahead and take a look。

At where we are doing our call。And in fact， of course， we're in the compiler。

 so we have a couple of cases for call right， so we have both the case where not is tail。

And the case， where is tail， we are going to keep both of those cases。

 but we are going to change some things， right。First。

 just as we're thinking about it in the interpreter， we want to think about。

 does it still make sense for us to right here， be checking whether F。

 this first thing that we're seeing associated with the call。

 whether F appears in the definitions list， go ahead and discuss with someone nearby。All right。

 so do we think yep， we can go ahead and check if F appears in our definitions list， Humphrey yes。

H for no。

![](img/2248c37dab8bef217426d4f5fc0135eb_30.png)

I completely agree， right so it's that same exact situation we were just thinking about when we were looking over here。

 so that purple highlighted item right here， that could be what F is actually representing。

 So we're going to have to actually compile that if we want to actually get the function value that we want to actually apply here。

 We're not going to be able to just go ahead and treat that as a string that we can check for inside our definitions list。

😊。

![](img/2248c37dab8bef217426d4f5fc0135eb_32.png)

So let's go ahead back to our compiler and get ready to make that change。So relatedly。

 one of the things we're going to realize is that we actually can no longer check at compile time if the argument's length matches。

So that's weird， right。 So this actually this prompts us to ask ourselves a question。 Now。

 with this change that we're making， do we know at compile time what function we are calling。

Go ahead and discuss with folks nearby。All right， so do we think yep。

 we know what function this is at compile time？We think no。

 we don't know what function this is at compile time。I completely agree。 Yeah。

 so we are now in the position where we don't actually know what function this is at compile time。

 And so we're not able to do that checking at compile time。 Now。

 if this were our first instance of running into a case where we needed runtime errors。

 this would be a really great opportunity for us to actually figure out how to admit the assembly that is going to do that checking for us。

😊，Since we have already actually run into that in the past。

 this is not going to be a great opportunity for us to do that。

 And we're going to do the lazy version where we don't actually check。

 if you are implementing a real language， don't do this。 if you're implementing a real language。

 go ahead and actually do the check。 It is very important that our number of arguments actually match。

 but we've already seen error handling and past class sessions and it would basically look like that。

So let's go ahead and actually do the thing that we need to do in order to get access to our function value。

 And so in particular， this line doesn't work anymore， right， We don't get to just say， okay。

 based on this name F。 I want you to go into the definitions list and bring me back the right definition。

 Instead， we have to go ahead and actually compile F。

 That's the big change that is happening right here。 So let's go ahead and figure out how to do that。

 So we've gone ahead， we've done our stack base， we've made our compiled as。

 what do we need to do after we've done our compiled as。 Well。Let's call compile X。

 We're going to go ahead and call it on this F thing in order to get the function value。

 but let's think about exactly what we're going to do。

 so we're going to pass in the same old list of Dins。

 We're going to go ahead and pass in the same old symbol table。

 and we're definitely going to want to go ahead and call it on F。

 So let's leave ourselves a blank for what part of the stack we want to use。

 We're definitely going to want to call it on F。 We also want to think for a moment about whether this is going to be en tail position。

Now， my argument would be， we're about to actually call this thing。

 so this is obviously not going to be。The the value associated with the entire thing。

 So let's go ahead and say， nope， that's going to be a false for whether it's entail position。

But what are we going to want to do in here， Well， we can just look at， okay。

 what is the the sort of next available slot。 So let's go ahead and say we can sort of copy this over and fill in some bits。

 So we're not going to want to use I here。 We are going want to use。List dot length。Of as。

 and we'll add to and do what the thing。 Okay， so far， so good。 what are we going to want to do next。

 Well， we definitely want to make sure that this actually is a function before we try to use it as though as a function。

 So let's go ahead and do ensure function。😊，On。What we have inside R X。 So far so good。

 And let's go ahead and do one last thing， which is we'd better not actually try to jump to this or call this if we haven't actually stripped out that tag。

 Sam old， same old there。 So let's go ahead and do sub。AndRX。In function tag。 All right。

 that's stripped it out。 and then。We can do almost exactly what we were doing before， right。

 So we' we've gone ahead。 We've made the compiled ags。 We've put them in the right place。

 We have gone ahead and figure out， okay， what is the function value that we actually want to call。

 right， What is the function we're going to try to call， We've ensured that it is， in fact。

 a function。 And now we've gone ahead and strip off the tags so that we can go ahead and actually use it。

 And's one last thing that we're going to want to change。 And it's going to be this line。

So what is it that we're going to want to change here？Does anyone want to make a guess？All right。

 go ahead and discuss for 20 seconds。All right， what are we thinking？

So we probably don't want to call， you know， first of pair of whatever or whatever right like that doesn't really make sense to try to call def and label on that。

So what would be a good thing to do here， we've seen this in homeworks we're going to go ahead and do computed call and we're just going to go ahead and use not this old label thing right。

 we're not using F in order to figure out anymore right we've gone ahead and actually compiled F and put the value associated with it inside REX specifically so that we can do。

Computer call on what we have inside REX。Now we are going to do a very similar thing down below for our other call case。

It's not going to look exactly the same， but certainly we are still going to have to get rid of these lines。

 Let's get rid of that。Let's get rid of that else there。

 And we are going to want to go ahead and do something pretty similar to sort of what we did in the middle here with。

This will change it slightly。 so let's go ahead and put it。After the compile as here。

 just the same as we did before。Okay， now we don't have stack base in here。 And in fact。

 all we're trying to do here is just make sure that we are using the next available slot on the stack。

 So let's go ahead and replace what is the next available slot on the stack In this case。

 So let's go ahead and do。Stack index。Minus。Eight times list do length。As， okay。

 nothing too wild there。 All that we're trying to do is make sure that we're not clobbering anything as we are figuring out what is the value associated with F。

 So what is the function associated with F Other than that。

 we still want to do this thing of ensuring that it is a function。

 We still want to do the thing of stripping off the function tag in order to actually use it。

And then what is going to be different is that we're not going to use normal jump anymore。

 as we did up above with turning a call into a computed call， we're going to do computed jump。

And we're going to go ahead and use what's inside。R right X。O。

Let's go ahead and see it in action and see if I've done any typos in here。Oh， and the answer is。

 yes。 What have we got type expression with selective type string。 Okay， did I not save something。

 Let's make sure everything。Is saved。All right， let me debug this while we take our five minute break。

 let's go ahead and get back together at 432。 See y all soon。Allright。

 let's go ahead and come back together。 So we went ahead and fixed it up。

 What had happened was we left in the parts that said check inside Din's list to see if F is Dafin。

 which was telling okay Camel， yep F is a string as we have discussed a couple times today。

 F is not a string right we are now expecting that F is going to be。AnExper。

 And so when we are going ahead and putting in here， when let me remember if I actually see if。

 oh yeah， I guess we have the example down here when we had。

TheThe check for is Din inside our our match situation。 Then we were going go ahead and say。

 okay I'm expecting that F is going to be a string because it's only a string that can actually be used with is Din And so that was a confusing' said。

 is this an expert， is this a string or what But once we went ahead and remove that And now we just check when is tail and when not is tail we are now good to go And so now we can go ahead and say okay let's go ahead and try out our test programs。

 So here's one of our test programs the one that we were playing around with on the whiteboard before what we said was okay let's go ahead and try it where we're actually providing Ml2 as the argument to F so here's Ml2 one of our functions we're going to provide that as the argument to our function F And we're going actually provide that as the the argument that is associated with the name G。

 And so then when we call G on2 what we're actually doing is calling M2。

And that is how we're going to get our answer for。 We can see if we go ahead and do Inter with the same program。

 we are going to get the same result。In fact， we get the same result。 Good to go。

 Let's go ahead and try out one more maybe two more examples of using our first class functions。

 So here we go， here's an example where what's happening is we are just giving a new name to Ml2 right so all we're doing is we're saying let's do some let binding let's go ahead and say that Ml2 can now also be used with this new name and so now if we go ahead and print new name called on5 we should expect to get you can all predict internally what we expect to get。

Uilile and run。And we do in fact， get our answer 10。

 which is to say five multiplied by two or five plus five。So that's how that has worked。But。

We are now also。At this stage where we can actually implement some stuff。

 not just as the compiler writer， the interpreter writer， as the language designer。

 as a programmer with this language， we can implement some stuff that's actually really quite complicated。

 like for example， all throughout the semester， y'all have been using map。And we can now。

 as a user of this language， actually implement maps， so let's take a look。

At how that's actually working。And I'm going to ask you to discuss with folks nearby what do you expect will be the output of this entire program from line 8 to line 16？

Go ahead and discuss with folks nearby。All right。So what do we think， what would be a good answer？

From this program。I love it， I'm hearing  one， two， three， four。

 so let's go ahead and find out what happens when we run it。1，2，3。

 four perfect right so all that happened was we went ahead and made that range using our range right it basically looks like the range function you would find in you know Python or whatever and it's going to go ahead and give us back the list 0。

1，2，3 and then we're going to go ahead and figure out okay， we want to call math。With the argument。

 G and what G is responsible for doing is just adding one to each of these values。

And then we can go ahead and actually apply that function to each of the values in this list。

 and that's going to go ahead and give us the list where we have that， but everything added。Now。

Hopefully， this isn't super surprising because y'all have all been writing， oh。

 Caml this entire semester， right， where you have been using map。

 you have been using first class functions that has been totally natural for you to actually be producing these。

 these function calls where some of the arguments are functions or generally where you're passing around functions。

 but something。May look a little wacky to you about this program。

Based on having been doing all of that Ocal programming。

 So what's one thing that you might find a little inelegant about this。

After all of the calls to map that you yourselves have made。Anything we don't like？

So I would say that at least for me。You know， I'm not opposed to writing this program。

 but I would find it somewhat more natural to write a program more like this。

And we can see that what's different here is instead of having that G function being defined at the top level。

We're instead being able to say， okay， let me just go ahead and make this little throwaway function。

 this function that I'm planning to use once I'm not going to give it a name or anything。

 I'm really only going to use it here。And here's the function that I'm going to use。

 is's going to go ahead and actually map from x to x plus1。this little anonymous function。Now。

 what would it take？For us to actually。Be able to support this in the language that we have implemented so far。

I'm going to propose that it's going to take a little bit less than you might expect。

Because when I look at this， I have an idea for how we could do this right now， right。

 so I could go ahead and say， let me take out。This lambmbda right here。Replace it with。

I should take out the whole thing here， take that out， replace it with some kind of special。

 funny name， right， whatever， whatever。And then I'm going to go ahead and define。That special。

 funny name， whatever， whatever， and somewhere in there， we're going to have the body。So to me。

Sorry for my bad typing， it kind of looks like we can just hoist out。The thing that we have in there。

 put it at the top level and basically be good to go。 right Basically。

 what we can do is we can convert。From a program that looks like this。

To a program that looks just like this。And that would be enough to actually implement this。

So this is kind of weird， right， This transformation process from a program that looks like this to a program that looks like this is totally possible。

 which means that we have actually already implemented。All of the language features we need。

In order to run this program， right， we were not going to actually have to implement any new functionality。

To run this。So given that that is the case， the question I want you to consider with folks nearby for about a minute。

Is would it be possible？For us to implement this without changing Inter。m， without changing compile。

 M。Go ahead and discuss。The transformationform we're thinking of is from this to this。Alright。

 so who thinks， yes， we are probably going have to change Inter do M and compile dot M。

 home for changing them。Who thinks no， we are not going to have to。I completely agree， right。

 And so maybe we have a little bit given away by the fact that we're asking the question in the first place。

 But yeah， if we're thinking about what's happening here。

 we are not having to introduce any new programming language features。 Again。

 we can already run that top program。 And so the way that we are going to do this is right now。

 what we've been doing is string。Tokens。😔，A T。Expert。To， you know， output， so。And call that assembly。

That's been our pipeline， so far。But we are going to be able to actually do something right now。

Where we put in an extra level right here， right， We already know how to go from this to assembly。

 right， That is something we already know how to do。

 So if we just go ahead and introduce one extra passage here。Where we're going ahead and saying。

 in fact， let me， let me make this even a little more specific， right。

 Because this is actually jumping over one of the transitions that we're currently doing in the in- class compiler。

 which is that in between here， we're going ahead and making。S Xs， S X。

And then we're converting it into our AS T expressions， right？

So we are actually going go ahead and make this whole transition one step deeper。

 So let's switch from that to doing string。😊，Tokens。S， x。AT number one， so here we'll do AST1。

 and this will be expert lamb。And the next AS S T2。Expert， the thing we already know how to do。

All of that， too， assembly。So what this is going to mean？

Is that we're not going to have to play around with。This layer， the hardest layer， right。

 that compiled M， that interpreter do M， that gets to say the same。

All that we're going have to do is make it so that we have something that goes from S X to AS S T 1 and something that goes from AS T 1 to AS S T 2。

That is going to be a much simpler task for us。If you have heard of something called syntactic sugar。

That's basically the idea here， right， The idea is we are going to keep all of the same core language features。

 but we are going to provide some extra syntax， right， some syn tactic sugar。

 a syntax that might be sweeter。😊，And we're going to go ahead and provide that。

 We'll make that available。 And then we will de sugarug， right。

 We will go ahead and take out that extra syntax and transform it all back。

Into an equivalent A S T that only uses features in the core language。

So that's what exactly what we're going to actually do。 We're going to go ahead and say， okay。

 we're going to allow folks to introduce these anonymous lambdas， but then we're going to de sugar。

 We're going to go ahead and do this AS T to AS T transformation。In order。

To go ahead and strip out all the new features and just express it in terms of the existing already implemented features。

So that's our general scheme。 Let's go ahead and start it up。 So over here。If we take a look at ASt。

ml。Well， what are we going to have to do， We're going to go ahead and actually change a couple of parts of this。

 So one is we already have this expert type。 We're going to have to go ahead and introduce this new type to represent our other kind of A T。

 So that's one thing that we're going to have to do。

We're also going have to change the thing that goes from S expression to expert because we're going want to go to the new kind of thing instead。

 And we're going want to change the thing that goes from。Sorry， yeah。

 we're going to want to make a thing that goes from。Basically， let me highlight it on the。

 the things here。 So we are going to go ahead and。Change。😔，This thing。

 so that it instead can be subbed in for here， right。

 We're gonna to have to change it so that it goes from expert。

 from S X to Exp La instead of from S X to X。 And we're going have to introduce this thing。

Those are the things that we are going to have to actually do here。So okay let's see it over here。

 let's first start by making our new AST， so it's going to look really similar to the existing one except that we're going to go ahead and allow it to have anonymous functions or lambmbdas so let's go ahead and give it its own name。

 so we'll call it expert lamb。All of the places that currently we have expertss。

 we're going to have to replace that with Exper La。Borring， but necessary。

And then we get the one really interesting thing here。

 which is that we are going to have one other thing represented just to say lambmbda。Of string list。

Expert lamb， and this is basically just going to be our argument list and then the body of our expression。

So now we have that in place。 It turns out it's gonna to be kind of annoying to write out all of the sort of boring cases for converting from expert to Exp La。

 So I'm going to go ahead and start writing it out。 And then I'm going to copy in some code。

 which is going to be， you know， annoying cooking show stuff。

 but sometimes it is actually more convenient。 but basically we're gonna want to go ahead and make something that is going from。

Noum X。2。And right， it's going to be doing all of that stuff。

 so let's go ahead and just copy in the version that is going to walk us through that。

 so let's rename this to。You see old， we'll rename this too。AsT。

And what's going to be happening in here， well， we already saw the introduction of expert La。

So that's one big thing。But we also have this thing that is going from S expression to Exp。

This is AS T old。 That's not helpful。 Yep， here we go。 A T。 So here's our new thing。

 This is the thing we actually want to interact with。 Here's expert La。

 This is the new type that we had already introduced。

 We want to actually go from S expression to this new AS T Exp lamb。

 So I'm going highlight the one interesting thing that's happening here。

 which is this right So everything else sort of looks the same the only changes made to the old thing that was turning an S expression into an expert。

 The only thing that's different is every place before where we are actually calling expert of S X。

 We have changed the name of this to Exp La of S X。 And so we are now calling expert La of of S X。😊。

Hard to say quickly。 So all of those places where previously we were going ahead and making an expert。

 we are now making an expert lamb in our recursive calls。

And then here's the one sort of interesting thing where it actually introduces something with the new constructor。

 So when it sees something that is a lambda followed by a list of as， followed by a body。

And when it goes ahead and actually figures out that all of those as are just symbols。

It's going to go ahead and make something in our new AST。That has this lambmbda constructor。

 and it goes ahead and associates the arguments， and it associates the body。

 So that is now something that we could find inside expert lambs that we couldn't have found inside experts。

 And， in fact， when we do the translation from expert lamb to experter。

 we are going to have to strip out。

![](img/2248c37dab8bef217426d4f5fc0135eb_34.png)

All of the cases of the lambmbda， we are going to have to go ahead and express it in terms of things that are allowed inside Exp。

And so that brings us to this case。 so this is the big new thing that we had to introduce。

 so if we take a look again back at our diagram， we have just seen the transition from this thing to this thing and the only real thing that changed was we now all of a sudden had to recognize Lambdas we had to be able to put those in there and we had to make sure that we are calling the new function name instead of the old function name but now we have to actually introduce the new thing。

 so that's what we're going to take a look at right now。



![](img/2248c37dab8bef217426d4f5fc0135eb_36.png)

So here we go back into the new thing。 What is actually happening inside。 Well。

 we can see that a lot of these cases look incredibly boring。

 And here I want to emphasize that they are doing real work， right。

 So here we have something that's going from numbum X to numbmex。 it really looks the same， right？

 But if we take a look at what's happening。 The thing that is coming in has type X lamb。

The thing that is going out has type X。 So we do need to do that transformation。

 I know this is something we've sort of talked about earlier in class a variety of times。

 but we do need to actually make that transition from the first AS T， AS T 1 into AS T 2。Again。

 we're going to go ahead and do all of these calls where we're actually calling expert of expert La in order to convert all of the things that were previously represented expert lambs into Exps。

 and then I'm going to actually delete this so we can construct it together。

 then we get the really interesting case， which is when we encounter one of these new lambmbda things right so we do have access to a lambda constructor for expert La。

 but we don't for expert。 So if we want to actually go ahead and do the conversion from expert lamb to Exp。

 we're going to have to represent it in terms of things that we already have available just in this type。

So what is that going to look like for us， I want you to go ahead and take maybe a minute。

 minute and a half to try to think through with someone nearby what would be a reasonable way for us to transform the AST to represent the same information that would have been represented inside a lambda that has a particular list of arguments args and a particular expression representing the body called body。

So what should we put。mayy also help to think about this transition where we're taking this lambda。

And we're trying to go ahead and replace it with something like that。All right。

 it sounds like we're a little intimidated by this， so I'm going to walk us through it step by step。

 Please interrupt me with questions。So one thing we know for sure。

Is that we want to make a name for this， right？ Because the thing that we're trying to do is basically replicate the process of turning this into this。

 So we're going to want to act as though we have a definition at the top level for this lambda。

 right That's the transformation that we're trying to do。

So we're going to have to introduce some kind of a name for this。

 even though we see it in this program as though it is an anonymous function internally。

 we are actually going to give it a name right， we probably won't give it a name like ge。

 but we'll give it some kind of a name。So let's go ahead and make a name， so let name。All right。

 we're using our familiar friend Jenssen。We'll go ahead and call it you know some variation of lambmbda because that's the rule that we are actually expecting it to serve。

And this will be a special name that we get to use。 This is how we are going to actually refer to it。

 even though the programmer will never see this name。

So what are we going to do once we have access to the name well？

We have actually done something kind of wacky here。

 so we have made it so that we are now maintaining。A defened list that is actually a ref。

So we're allowed to actually mess with what is stored in here。

 it was a little tricky of me to ask you what we should do down here。

 given that you didn't know that we were allowed to actually modify what's in the Defins list。

 So let's go ahead and now take advantage of knowing the information about the arcs。

 knowing the information about the body， knowing the information about the name。

 That's everything that we need in order to make ourselves a new entry in that deinens list。

 So let's go ahead， say， nope now Defins is going to be， you know， augmented with one new item。

 So we're going to use the name， we're going to use the arguments we're going use the body。

But we're not going to use the body exactly as we found it because remember。

 we have to do the same thing that we've been doing up here。 Exp of expert lamb， right， That body is。

 in fact， an S expression。 So let's go ahead and say expert of。Exper lamb。Defin's body。

 So that's how we're going to go ahead and make that。

 And we're going to go ahead and say go ahead and add that on to the existing deinens that we already had。

 But now we've done all that。 we've made sure that we actually have that representation of the new definition that we've just made。

 We've made that We've put that in our Dins list。 What do we actually want to have come out。

So if we take a look at sort of where the lambda is occurring。

You can take a look at our program right here， you see that， okay， it's occurring right here。

 right where we actually want a value representing that function。So now go ahead and take maybe。

 I don't know， a minute to discuss with someone nearby。

 how can we actually represent that lambda right here where we need it？Al right。

 so this is exactly the case where we want a function value right。

 and we know exactly how to construct those。 We have our there and then name。

 that is exactly the way that we have decided we're going to represent them。

 We've talked about why we're doing it that way both in the interpreter and the compiler so we can go ahead and just do that。

And so now we have actually implemented。These anonymous lambdas。

 these anonymous functions without changing anything about interpret M or anything about interpret compile。

 Sorry， compile M， my brain， We have now gone ahead and actually made it available without changing any of that。

 So let's show our terminal。Let's get rid of AST old。Yes。

Let's go ahead and use that example that we've been working with the anonymous lambmbda。

 the anonymous function。No problem。 It can do the transformation for us， right。

 It is able to do the hoisting of taking that lambmbda out of。

This non top level position and putting it into a top level definition for us。

So without changing interpret。 Ml， compile M by just doing an AST to AST transformation。

 we are able to make this program in scope for our language。

This is a fairly simple AST to AST transformation compared to production compilers and production compilers。

 you often see sort of these big long pipelines of transforming one AST into another AST into another AST just based on sort of what is the representation that is convenient to actually do the thing that you are trying to do。

This is one of the reasons why it can be helpful to have a custom representation for your language Okay。

 that's enough for today so if you have any questions。

 feel free to ask me either by like coming up towards the end of class or just right now。😊。

This the position。If one of the oh， so do you remember how Geen Jenensen works。

 So it is doing that thing so there's no way to actually end up getting the same thing if we are using Geen Yeah Yeah so it actually prevents that clash。



![](img/2248c37dab8bef217426d4f5fc0135eb_38.png)

Yeah， great question。Oh， yeah。 Do you remember Jenssen and how we're sort of doing this thing of making。



![](img/2248c37dab8bef217426d4f5fc0135eb_40.png)