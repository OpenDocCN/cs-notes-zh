# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P10：-10-10. Combinators and Staging _ - GPT中英字幕课程资源 - BV12VChY2EF4

Good morning functional programmers welcome in all right。

 welcome to our 1th lecture Combininators and staging just wanted to give you the state of the House if you will or the houses which is currently Blue team is winning and to be honest it may not be possible for other houses to win depends on if something surprising happens I feel like is' worth aoting points for so maybe there's not hope but we'll see at the end of this lecture all right。

😊，What。mind but yeah， so that's the of the state of the Union as it is All right。

 let's go ahead and get started then okay。

![](img/d474c7327a6e7791cbd47922abc312f5_1.png)

So today we're talking about combinators and staging， to be honest。

 combinators are a topic I've never really felt super passionately about and to be honest I don't think it comes up very often。

 so the lecture is called Cominators and staging it's mostly staging。

 I'm going to be laid on the combinators okay。😡，But I didn't change the name of the lecture all right。

 but last time， okay， actually I won't go to the last empress yes， so here's the mente code。

 copy that down if you so wish， ask a question and I will try to remember to go over it at halftime and if I do not please remind me okay because I'm supposed to do that。

😊，I'll give you a second。It's been like pretty well。

 I think some people have been making use of it so。😊，Cool all right。

 here's what we got on the dockkeeper for today we're gonna to be talking about this idea of staging。

 which is a sort of corollary that comes out of currying okay we're gonna to be talking about how to analyze the cost of a higher order function we're gonna to be talking about using hops on trees the same way we used on lists in the last lecture and how we can use hops to simplify our programming this is very much a hops part two lecture okay so to quick temperature check how do people feel about like the contents of Tuesday's lecture and also Wednesday's lab like thumbs sound。

 thumbs middle。😊，Okay， okay， because this will heavily lean on that， right。

 but this is kind of like a really cumulative idea。 Okay， higher order functions are higher order。

 So we're gonna apply them to higher and higher places。 Okay， and also this case study pre staging。

 if we have time， but it's not no big deal。 if I don't get to it， don't feel stressed about it。

 But it will always be in the notes。 if you'd like to read it。😊。

One thing I wanted to point out again in a lecture was if you didn't see my piazza post about this hacker news thread I saw over the weekend or over the past few days。

 and I just am so unbelievably happy like there are I cannot really stress you how importantly I feel that there are literally people out there who do this as their fulltime jobs and they go on hacker news and they read about their fulltime jobs which are software engineering。

 and someone said， you know， you should learn this way。

 you should consult the course material from 15150 like I realize you're in this class and it doesn't feel it doesn't hit as hard because you're just taking the class。

 It's just a class。 but like this is that's the coolest thing ever that there are people in the world you've never met who wish they could be learning what you're learning right here。

 I just think that's the most amazing thing in the world it's crazy I cannot I cannot get that across you more vehemently But diattro beside will move on。

😊，Okay， so last time we introduced this idea of higher order functions which primarily are functions that take in other functions and this is a really really core idea because basically anything you can do now we can kind of find templates in our code。

 we can find areas of our code that can be simplified by identifying common patterns and using higher order functions right we learned how we can have cur functions which take in quotation mark multiple arguments because they take in one argument and they return a function。

 a lambda which takes in the rest of the arguments and then we also talked about the Hs zoo。

 the menagerie of map filter compose fulldll and folderar which are our base for higher order functions but we're going to improve on that as time goes on。

😊，Audacity is annoying me。Allright， so let's talk about staging， shall we。 Okay， and let' all right。

 let's let me set the stage。 So why do we do curing。

 I gave you a little bit I gave you a little bit of a motivation for why we do curing because I told you about this partial application thing we do。

 All right， I told you about times where we do stuff like Val。😊，Increment all。Equals map。

Of F N X goes to x plus one and I can partially apply this because I don't need to give map the two arguments it's expecting。

 I can just do this。 And now I have a function of type int list to in list。 Part evaluation。

 Part application is one such motivation。 But staging or rather staging the thing we're going to talk about is kind of a corollary of this Another reason why coding is important is we have this idea of a hierarchy of functions。

 We have map， which sort of captures this idea of let me do something to every element in the list。

 We have fold， which is this idea of let me summarize all the elements in the list in a prescribed order by applying a particular function okay。

And so these these higher order functions are really just like templates for code the way same way you could write the source anywhere you wanted。

 I could write increment all recursively if I wanted that pattern。

 that template of a function is captured by the map higher order function。😡。

So I want to kind of you know beat this idea into your head that cur is important because it's like specialization we have fold R which is a template for accumulating in a list we're summarizing the data foldar op plus is a template for summing elements in a list but you can give it a starting value and then if I do fold R op plus of zero that means finding the sum of a list full stop because I just sum everything and I add it to zero at the end of the day so like you know if you can imagine in your mind I didn't actually go ahead and draw one of these but you can imagine one of them like we have this hierarchy much like the ones we've seen prior in this class where I have fold R and its descendants of functions that can be defined by it。

😡，And the various use cases thereof right And this is super， super important because this graph。

 this tree is extremely wide。 Every possible function I can give bold R is is a different specialization of this function。

 For instance， the T list max function function you wrote on your midterm。

 Well maybe I shouldn't have said that yet。 but the T list math function you wrote on your midterm is just an application of bold R。

 And you can ruminate on that if that's not clear to you yet。

 Okay but that's kind of what I had in mind when I wrote that problem。 but that's kind of the idea。

 specialization。 All right。😊，Allright， and here's another fun fact for you and I'll make the claim view。

 Stactically sugared cured functions are trivially total。 And yes。

 that sentence had three alliterations in it。 consider the definition of map like so written back there is a desks a little good。

 It is。😊，Consider the definition of map as I've written up there， right？😊。

I've got this map taking an app， taking a nailil， so on and so forth。😡，The question remains。

 is it total， and I claim to you， it's probably something to bother me， but that's okay。

 I claim to you that this function is total。But why should that be。

 isnn't that a little weird of a claim because？Isn't it true that if I did？Map。Fn x goes to x div0。

If I did this on 1，2，3， what do you expect the behavior to be？Raise an exception。

 So why is Map totalurt， I just told you Ma was total， but I just told you raise an exception。😡。

I said map was total。 I said nothing。The map of this function。Okay， that's the distinction。

Before I evaluate this。 Okay， so let me say okay， there are two different functions I'm talking about map and map given some F。

 which in this case is this guy， two different functions entirely。

 So if we unroll the definition of map。 Remember that like font map is really syntactic trigger for something that looks a little bit like this。

 Okay except not quite。 but I'm let you。 Yeah， so it looks kind of like this。 right， I take in the F。

 And then I return a lambda that's gonna do the casing on nailil into cons。

 Does that make sense why that similar to this。 why those are the same thing。😊。

I claim to you this is really what map is。 So if we look at what map does given any argument。

 is it true that given any value， I get a value out。 Well， if I。

 if I apply this whole thing to any value。😡，I'm going to always get FN Neil goes So da or cons。

And isn't F and a Lada expression， which is a value。 So for any input I give map for any V。

 let's say for all。Values。V of type T1 to T2 for some type t1 to T2。Map V。Evaluates to。

FNil goes to da da da or x con is goes to da da da。该。Does that make sense。

 I always get the same value well not the same value， but I always get a value out。

 but then as soon as I give it the list， it's optional to the races because then what am I going to do。

 I'm going to go here。And here and there I might raise an exception， in fact， in this case I do。

 okay。😡，So that's another idea， which is kind of that if I have， you know， FN1 sorry。

F then I'm going to say underscore。 Okay， I don't care about I can do this。

 I just don't care about the argument。 Okay， F N underscore goes to one plus one。

I think I might have asked you some derivative of this in the past。

 but does this evaluate to anything， does this reduce？

The answer is no because lambdas always frees everything inside of them。

 This is kind of a corollary of that okay' the exception raising stuff is here。

 doesn't matter or it's here but it doesn't matter because right here I return this lamb up and everything in the lambda is frozen in time okay。

😡，Like the plot of spy kids for all right。That's the thing that you should realize is that cur functions like NAp are kind of quotation marks trivially total。

 all right， you can always kind of say that they're total。😡，Right。Cool。

 but here's another question for you。Is any expression of type T1 to T2 to T3？

When know the itss right associateso says friends around this thing。 iss any such thing total。

 Is it true that every such thing is total rather。好。what。Yeah。Yep， I like that。

 I get what you're saying。 Let's see it。 oops， yeah， let's see it so。😊。

Just because map and friends are is not guaranteed that all of them are。 Actually。

 I'm gonna write this out。 I guess， let's do it。 So fun， actually， let me do it in a vow。

 So it's really clear。 Okay， Valal F equals。 so F N。😊，Let's say I'm not going to call T 1。

 I'm gonna call it X1。 Okay， and this thing is a type T1。

And it goes to what I'm going to say a Latin end expression。

She I was supposed to define something else before this， but it's fine。😊。

Suppose that I defined a function called loop that loops forever on any input。

 particularly on a unit input， right？Where I put whatever inside there。 Okay。

 do you believe me that this thing should be of type T 1 and T 2 to T 3， right。

 because I take into T1， and eventually I'm going to return a lambda that takes in T2 and assume that the body here was of type T 3。

 All right。This is actually the example I just felt like writing it out。

And I can define a trivially looping function here called loop at loops。

 right because it gives itself， it always calls itself， right。This is of type  team and a t2 to t3。

 but it's not total because if I give it any value， what happens， I don't return this。

 I immediately go and evaluate loop and what does loop do loop loops right so we're not going to get anything here So just having a cur type does not make you total。

😡，But if I write something like this。呃。I'm gonna I kind of screwed myself by using different letters。

 but x2 equals。Let's call it E， let's say if there's some expression E that I wanted to return here。

 all right， I'm not going to define it， but let's say it that exists。

Do you see the distinction between these two things？Is this one total？

This one is going to be total because if I give it any argument。

 I immediately get back a lambda taking an x2。 And then that evaluates to this body。

 But this loop never happens because it's in a lambda because to D sugar it implicitly。 what this is。

 is its vow F equals F and X 1 goes to。F N， sorry， I'm running out space。 X2 goes to let da da。

 da end。Does that make sense， this is remember， this is just that or this is just that， right？😡。

So this one is always going to be total because I can't ever evaluate this until I get this。😡。

But this one evaluates this as soon as we give it this argument。 All right， temperature check。

 how do people feel about that。RightThis is a really important thing to have in your evaluation model of how the language works。

 Okay， you should be able to like like the point of of the first five leases class is we're building a little mini SML interpreter in your brain。

 Okay， and， and depending on how good the SM interpreter is。

 you might get plus or minus points on an exam。 But right now is where Im I'm trying to ascertain or trying to teach you more about what that interpreter should do Okay。

 so if your interpreter is faithful enough， like this should make sense。 and if not。

 we can we can work on that Okay but we're refining that idea。 Okay cool。😊。

So here's an example for you。Zayman built a booth。I'm kind gonna。

 I'm kind gonna context switch a little bit here， but sort of related。 Allright。

 Anyone built a booth。 Allright， So we build booth。 we build these big wooden structures。

 I'm saying this for the benefit of the recordinging。 I know you all know。

 suppose you're building a booth。 Alright， and and you've got this a bunch of wood。

 And your friend stays behind your house or wherever to build paint the wood。 Okay。

 and then you say your friend， okay， and you look at like the giant stash of wood that needs to go for the floorboards and stuff。

 And you say， allright， I'm gonna wait for you to finish。 And then I'll take that to midway。😊。

That's really stupid because you're wasting time if I'm。

 if I'm waiting for my friend Dave to finish painting the wood。

 I can still take the giant pack of the giant like， you know。

 stack of wood over there to midway because we need the wood for floorboards。 We need it for walls。

 We need it for God knows what else。 things that don't require him to finish painting。

 What I'm saying is that there's no dependency here。 Okay。

 it's silly for me to refuse to do things just because someone。

 I'm someone else is doing something because I can get started without him。 I don't need him。

 All right。This is the idea of staging， all right？You shouldn't have to wait on something unrelated when you can do work right now with what you have。

 you don't need to wait on other people All right this is the idea of staging。

 which is a term that is describing what happens when you when you put computations in particular places with respect to cur arguments okay and the with respect to cur arguments is kind of the same idea here。

😡，As what we did， the difference between these two things。

 I would say that these two functions I've defined up here are differently staged， Okay。

 and that's why they exhibit different behaviors。 Allright， so let's get into it， shall we all right。

😡，Okay， so the basic idea being that if if I want to save all my computations。

 I can save that until I get all my arguments， but I might not need to okay。

 and I'm going to try and recall this example of Tom my head。

 but I might get some of the names wrong。All right， suppose I'm defining this function。

And this is a realistic function for sure。 I'm calling a function named horrible computation。

All right， and horrible computation， by the way。😡，Takes three years to run。Okay。

 sometimes that happens。Alright， so this function， horrible computation。

 I should have put it up there Actually， takes three years to run。 Okay。

 so what this function does it takes in two career arguments。 It runs horrible computation。

 and it adds it to why， okay。😊，And suppose I wanted to use this function a couple times。 geez。

 suppose I wanted to do I thought an export it fine。

Here's the idea also is that I can't stage this because my thing I want to return x and y x plus y relies on both x and y so the idea is I want to move my computations up if I can。

 if I don't rely on arguments to do them， but I can't do that here because if I move x plus y in like a let before this lambda。

 well how am I going to do that， I haven't bound y yet。If I move it but appear， well。

 I haven't bound X yet。 let's look at this example， and then it'll make more sides， I think， alright。

I don't know why I bother writing it up。 It's up there。 anyways。

 horriblerrible computation takes three years to evaluate。 Alright， So let's。

 let's suppose I wanted to do this。 Well， what if， what if this is what I want to do。

 I want to evaluate， It's actually called mystery。 I want to evaluate a mystery of 2 and 4。

 mystery of  one in 2， a mystery of 2 and 5。😊，All right。

 so how long does that my mystery machine take， How long does this take in total？

This takes9 years to run。 You could raise a child halfway to adulthood in the amount of time that this takes to run。

 Okay， so I don't like that very much。 But if you notice， what do you notice。

 What do you notice about this function。 What point am I making here。

Does this need to take nine years？我工。couldn't take3 years。 It could take six years。 Yes， It could。

 honestly， it could take 18 years。 We could run twice。 but I'm yes。 So here's the idea。

 horribleible computation back there doesn't rely on why whatsoever。 I don't need to wait to do。

To get the argument Y before I do the horrible computation because it's just a function of X。

 That's all I care about。 So I'm going to give this a switch a little bit。Watch this。Boom。

 I'm going to erase this。We need to erase this。equalals there， fNY goes to z plus y。

By equational reasoning， you should be able to reason that this is extensionly equivalent to what I had before。

 Y because Z is horrible computation of X， and this is just another lambda right。

 so it's equivalent in the same type as mystery X Y。

 But all I've done is I've changed the taking of this argument into this let here after the horrible computation okay。

😡，And then suppose I did something like this。😡，So that that was the edit。

Suppose I first bound F to mystery 2 of2， then I bound G to mystery 2 of1。

 then I used F and G independently after their bindings。On four， two and five。

 which are the arguments that were before you probably don't remember it's fine。

How many years does this take to run？Six years right because I only ever do two horrible computations。

 but now I save a third of the time because I noticed the thing that I noticed here was that there was a common prefix。

 I was computing mystery of two twice and you should be suspicious when you see something like that because guess what pure computations means you should never have that sub expressionpression I mean you can like sometimes it results in clearer code but a clearer code is not code that runs three years after schedule okay so。

😡，Noticing this means that we can factor that out。 Okay。

 so this is what I call a staged version of mystery。 Allright。

 I have staged it such that I have moved this horrible computation。

With respect to the current argument， I， I moved to the lambda that takes this argument in here after the horrible computation。

 Does everyone visually like， see what I did there， right， I moved to the lambda。 right。

 That is what staging is。 We move the work with respect to the arguments because of a lack of a data dependency between them。

 There's no data dependency between horrible computation and why。 So I moved it up。Okay。

 temperature check。Uptown sides。I also take questions。

 Ques are also an appropriate thing to ask for now。And yes。あのワ科し。Okay。

We'll see if we have time this is， I said this last time， this was the band of minds instance。

 but we supposedly have a lot of time this lecture all right。😊，Okay， so that that is staging。

 all right。Usually it doesn't matter the order in which we do things like I told you you should be able to equationally reason that this is the same。

 but sometimes it does matter for performance。 Sometimes we do want to care about when things happen。

 I told you one of the things about functional programming is everything happens Like can happen in parallel。

 Wait weve seen this with span。 It is safe to do stuff independently of each other。 In this case。

 that's still true。 I'm just being more deliberate about where I do this。

I know I feel like I might want to address is。If you're really on top of the ball。

 you might say something like， shouldn't So for the horrible computation we had earlier。

 you might say something like， oh， shouldn't a compiler notice that this horrible computation doesn't rely on why and it like hoist it up out of out of the Wo。

 Okay， basically meaning that the compiler should be able to optimize that and do what we did manuallyli here。

 That is true。😊，I claim you don't want that。 Okay， not in all cases。 All right。

 sometimes it's not good if the program does something that you're not expecting。

 We're being very deliberate here。 The cost is here。

 The cost is here and you shouldn't expect it here。 We're here。 We're being deliberate。 Also。

 the source text says the， the cost is here after you receive two cur arguments， okay。

Good programming is clear programming。 Allright， I know I have this complaint with like like Python。

 or let's say I'm a Python。 There's one idiomatic way to do things。 Okay。

 and then there's also like 20 different indexes to do exactly the same thing， Okay， like。😊。

There should be one idmatic ways to do things。 Yes， I agree。

 But source text should not have a gotcha。 you should never have you ever come up with something clever and you're like。

 oh look at this thing I just did， isnn't that clever， In't that so cool how it does that。

 you weren't expecting that that sucks。 never put that in a pride。 you never want clever code in。

 You never want clever code can keep clever code notes Tx the desktop that's fine。

 but don't share it with people in expect them to write it。

 Okay clever codes to look at clever codes not to be read so what I claim to you is doing that optimization results in clever code or clever compiler compiler can be clever。

 just not too clever that it's not what you're expecting that dibe may not make sense here know it's near and dear to my heart。

 I like compilers that's just a point I wanted to make but yes， no clever code。Cool， all right。

 let's move on， this is going to get more important as we talk about things that are not just。

Very extensive operations because we'll talk about things like side effects like IO， like printing。

 like imperative sub。Spoiler alert， we're gonna get there。 Okay， and this is going to matter。

 Alright， it's going matter a lot there。 And honestly。

 also it matters a lot because if I ask you a types question。

 if I ask you a question on the next midterm saying is every value of T 1 to T2 to T 3 total。😊。

This is important remember you're staging， right， I set the stage now you have to walk on。够。Okay。

 now we're going to talk about a little bit of cost analysis of hops。

 because we have to give that a little bit different of a treatment， okay。

If I have a higher order function， this higher order function takes in any arbitrary function。

 It could be a function loop forever。 It could be a function that takes five years。 Okay。

 but that is something that is a valid fear。 So real fast， I'm going to rewrite map for you。

 which is our poster child。😊，Of hopsville， okay。So if I have x times xs， I'm going to say。

 what do I return here， what's my result？So， shut out。Fx cons。Map Fxs， yes， correct。The question is。

 how long does map take to run， okay？😡，So I type penated there， but let's try to write a recurrence。

 shall we， so we'll do this in terms of the length of this list， Okay W use sub map。

It's actually not exactly correct to say math， let me say w subm of F okay。For some arbitrary F。嗯。

If I take in a list of zero lengths still see not， we're not getting away from that。

And the work of map F given an arbitrary F or a specific F， well what do I do。

 I do constant work to cons， but I also compute this F here and the question of the hour is what does F cost？

😡，AndI don't know。 Okay， I don't。 I don't know at all。 My precondition of map is like。

 maybe I have a preconition of map F is total at the very least， but I don't know what it costs。

 So how do I possibly write this recurrence。 Well， I'm gonna do this， okay。Work of F。Work of F given。

Let's let's say this， this might not be exactly good notation， but。

 let's say the work of F on the input X， okay。Plus， C1 plus work of map F。On n， -1。Actually。

 you I don't like this， I'm going to say the work of F。Okay， here's the idea。

 The work of F is independent of the length of the list， right， because I just give F。X， right。

 the amount of work done by this is has to be independent of the length of the list。

 So I'm just going to consider it a， I'm going to consider it a constant。 Okay。

 we're just going to call it D of F，Because it's not dependent on how this function grows。

 And if you build this out， eventually， you're gonna to get something like equals that。In all of N。

W400y。But as a function of the input size here， that will not change。

I'm basically saying so this is one really weird thing about asymptotic notation where if something doesn't change based on this。

 you can literally just say it is constant， even if it really is unintuitive。

 even if F is like a function that computes like the end to the end factorial and this is 100。

 but it doesn't scale based on n doesn't scale based on the number of elements scales on what the elements are。

 but I don't care about what the elements are my model by randomness recurrence。

 I'm saying I only care about the complexity in terms of the length。😡。

So it might be bad betting on the elements。 And we could actually make it a function of both。

 if I was really interested in that problem， I might say， oh， math F or the maximum element is K。

 then I would have a bound for you in terms of K。 In this particular instance。

 I'm down scing and saying my problem， I only care about in terms of N。 This is not super important。

 Don't get too caught up on it。 Okay， I'm just trying to get across to you the idea that there are N calls to F。

 There are O of N calls to F， okay。😊，And that's all we can say about the cost of this function， okay？

😡，We can't do much better than that。 All right， not for a completely general F。

 not without making more advanced claims about our list or about our function， Okay， so。

It would still not necessarily be wrong to say that map F is linear work。

 I just would much prefer that you say something like O of n in terms of the cost of F。 okay。

 O of n calls to F。 thats more that's a better story than is linear。

 and then this w sub F function computes like to the n to the n to the n factorial okay。😡，m coolol。

 Allright， does that make sense to everyone。Just be more particular about what you say， All right。

 It is technically correct to say it's an event。 just don't。 All right， that'll be Saeth。O。个。

All right。We actually have a quiz。 I'll dress the once you come back， take your quiz。

Is like we're all pretty much coming up onone here。All right， how did people feel about that one。

 thumbs up down。Okay， all right， that's enough mediums for me to feel good about it， right？Cool。

 okay， let's get started with the next section。 Okay， this one may or may not take， well。

 it will take the rest of the lecture， but it might take a long time。 We'll see。 all right。😊。

We talked about higher order functions on lists we are going to talk about higher order functions on trees。

 There's a very tried and true 150 formula where we introduce choose something to do on on lists and then we do one on trees right and we call that in education Okay you ever seen Aladdin like infinite cosmic power。

 80 B living space， It's like infinite cosmic power， 80 B0 writing ch。Alright， so。

Let's do everything on trees now。 We've talked about mapping and folding on lists。 But hey。

 what also stores data and looks like a binary tree。 That's right， A binary tree。

 So what we can do is we can define some functions for us on this same data type。

 So recall the polymorphic tree data type that we defined some lectures ago。😊。

I'm gonna claim to you that almost every data type， actually。

 that you can define admits a map and fold function。 Okay， I say almost every， unfortunately。

 there's like a very theoretical concern that or very realistic theoretical concern that makes that not true。

 But almost everything can be can be done We're gonna see how we can do that on trees right。

 So the idea is like if I have a map on this， I look at every item in the list。

 and I just change it by applying the F。 Sam thing with mapping on trees。

 I take every element in the tree。 and I apply a function F to it。 And I obtain a tree out。😊。

So here's our type signature。 It should look very familiar to you because it almost exactly resembles the list definition。

 It's just that you exchange the tree or the list for tree。 Okay。

 and then we know we're going to require in the section that F is h， okay。This is our function。 Oh。

 whoops， I was supposed to write with you。 Let's do it。 Let's do it。 Don't cheat too much。 Alright。

 I'm gonna write it in front of you so that I make sure that everyone gets this。 Okay。

 so if I'm going to write it tree map of F， I'm gonna write empty。😊。

And then what do I get out for the empty tree？😡，Yeah。What do you think。Empty。

 I decided to go and write this while you were answering because I knew it would take a while。

Alright， F， and then node of Alex R。Cool， I want to somehow map every element of the tree and apply up to it。

 Okay， so what's the natural thing I should do here。😊，I got to return。

 what's the first character I write？For the first yeah， your friend。Oh。So let's try it。 So T map F L。

 you're absolutely correct。X。F X， yeah， yeah， we apply F to our root， and then we move on， right。

 Inductive assumption。 If I can map everything else， and then I map my place， I get it。 Okay。

 and that's just it。 That's just it。 It's tree map。 It's not。Hopefully not the most mind boggling。

 Okay， like， again， this sort of thing about recursive functions is like。

 I don't want you to have to like try to write this or try to use this on like a big test case to convince yourself of its correctness。

 Okay， I want you to look at it。 And then in a finite amount of time。 tell me， oh， this looks right。

 because of the recursive assumption， right， This looks fair。

 if I map the rest of the list or the tree， I map the rest of the tree。 I map where I am here。

 Okay So it shouldn't take very much brain power for you to think about what this does。

 because you shouldn't have to think about what it does， really。

 you think about what it does once on one step。 And if it doesn't write on the one step。

 and that's always right Okay。😊，Cool， that's train up。 And I claim to you。

 I can write this on any type ever， almost， al right。嗯。I'll just。 Oh I'm so sorry。

So the really funny thing is that last lecture， I made a claim to you like， oh。

 if you write any number of functions， too many times you're gonna make a mistake。 I've done this。

 And I went back and watched the recording。 It turns out I had literally written one of the functions on the board wrong that no one pointed out while I was saying that I did。

 I did X plus one。😊，Cons increment all。And I didn't write Xs。This would have been correct。

 So no one pointed me out as wrong。 But I that just goes to show you。 Alright， like， I've done this。

 I've done this stuff for so many so so long。 Like I still make some mistakes。

 So write less code is the idea。 Allright。😊，We're trying to put ourselves out of a business， okay。

 faster than chat GT can， hopefully。Allright。So let's train up。 Let's move on， though。

 I want to do a fold on trees。 Ire what's up there。 It's not relevant for this part。 Okay。

 I want to do a fold on trees， which means I basically need to go through the tree and apply a function on an accumulator and then kind of update that as I go。

 But I need to pick an order to do it。 And we're gonna pick our favorite， which is in order toveral。

 okay。😊，This type signature should also look very familiar to you， right， because it looks like fold。

 It's just I replaced the list with the tree。 Okay， this is actually a very deep like thing。

 like this would be the fact that this type signature looks the same for pretty much everything。

 Like this is a universal thing。 it wouldn't depend on the type pretty much。

 but that's how we're gonna do our fold function。 Okay， so let's try to write it out。

 So and the neat thing about having these other functions we've defined is now my in clause can be just a relationship between code ensure that tree fold should be correct。

 It should be equivalent to getting the in order toveral and then folding on that Okay。

 except we're not gonna actually do that。 we could implement it that way。

 But like that would be less efficient。 It would be space ine。 It would be， I'd have to do it twice。

 essentially better to fold on the tree itself。 so but this specification comes very nice and concise。

 Allright， let's define treefold L， Allright。😊。

![](img/d474c7327a6e7791cbd47922abc312f5_3.png)

Because it's an order well in order left right to br。Yeah， I originally called it treefold。

 And I was like， but it's not the only treefold。 Let me put an L because it's left or right。

 And then you you are gonna be pin got of me either the way。 It's 1。

50 tradition that we should call the accumulator Z in retrospect。 I actually hate that。

 Like we've been using a semester。 I'm want to do this。包括这个。Yeah， we'll go away after this semester。

 Okay， if I'm fold on the empty tree， what do I get？Ac， right， Burn that in your brain。 base case， a。

 alright。Alright， now， if I want to do tree fold L on not the empty tree。

 I'm going to have node of L R， what's my game plan。Oh。

 just occurred to me that youll have my slides。 Like， you could totally like just answer everything。

 every question I ask you by looking ahead。 and yet you don't。But yes， don't actually do that。

 coolol。 What do I do， Well， I want to fold in an in order way。

 And what is the three three words that describe it in order traveral。😊，L X R， Yeah， yeah。

 pretty much。 L X R left root right， right， Sure， it， yeah。

 I guess that's an easy way to remember it。 L X R。 So we want to go left。 We want to go to our root。

 and then we want to go right if we can。 Allright， so I'm gonna write it in a little bit of a particular way。

 Okay， but here's what'm gonna do。😊，I'm going to say that we're going to let this value。

 which is I'll call left app。Equal to threefold。L， given my function F， as always， right。

 And then given my initial accumulator， the accumulator I had entering this function。

 and I'll do it on the left。 I claim to you recursively。

 this will be the in order traersal of everything in the left subte。 Okay， the result of doing that。

 Okay， let's assume that threefold L works。😊，If that's true。Well， oops。If that's true。Well。

 what am I going to do？Actually， I'll write out this， I'll make it super explicit， okay。

And then I'll get my root a， which is what， which is taking my left act and applying it to my root。

 which is F given what first， given the element， because it's a type alpha star beta so the accumulator comes second。

 So I'm going to write F of x comma left act。 And that's how I'm going to get my accumulator from looking at the left and the root。

 And then what do I finally do， I'm going to get my right act except I'm going to return it。

Can anyone guess I'm to write？Yeah。最后的管。哎。Was that root？A R。

If fold L looked or fold L or looked scary to you， I actually feel like this looks a lot less scary right because like what am I doing。

 I'm just folding the left， my root am I right， it might not have been clear to you like why I was changing the accumulator in fold L or why I was doing the F on the outside。

 but I'm just doing left。😡，Root， right， right？Yes。Well， well， short does if I say let。X 1， X， N。

Be the in order。Tversal of tea。De dependsd on how you phrase it。 right I agree。 it's kind of harder。

 right I wouldn't want to write node of that it that would be a little difficult。 Okay。

 but that's kind of what I'm trying to capture by this specification。 actually。

 It's pretty much the same。 But yeah， that's that's the strength of having these things where we can translate to racist yeah。

F is not commutative Well then you should define your a different one。 I mean， like fold out like。

Bolddll's job is that only does it like well okay， often beta first of all I don't even need to be the same type So so if it was commutative。

 you'd be restricting them to the same type by the way， right so like like by nature。

 we're considering noncommutative functions because alpha beta might be different types。Yeah。

Depends on your operation。 If it's community。 If it's associative， you'll get the same。 Actually。

 we'll see some implications of if that function isn is associated in a few weeks。 Yes。

 doesn't matter too much right now。 we're gonna look at it in a particular way。

Are people confused over this implementation？To me。

 I feel like this actually looks nicer than Bull out。

 but maybe that's just me Okay let me just do the thing。 Al right。

 And I want to show you how that works just so that you can see a picture。

 I've implemented it in a little bit different wording in my little playground in my little playground here。

 Here's what it is。 Okay， So in this one， I didn't define root act， I just like。😊。

Pass it directly into R。 Okay， does that make sense to everyone， And I also called it left folded。

 Okay， but this is a tree， right， and the tree just looks like 1，5，0。Right。

 that's the test case street。 We're gonna try and run folding with the sum function。 Okay， on this。

 Alright， let's do it。 So Morgan test now。So if I run tripled on this tree。

 which is a left subre of one and a right subre of 0 and a root of 5。 What am I going to do。

 I'm going to enter into the case， and then I'm going to enter the second case。

 So this is my body of my function。 right， I fold the left with the left subree。

 which is just the tree of one。😊，And I later have to use this result when I fold the list of zero。

 right， but first I'm going to fold the left subree， which is this guy。Then what happens， Well。

 in place， I'm going to expand this definition of treefold L。

 This is kind of the picture you should have in your mind for what happens when you evaluate expressions。

 I leave。😡，I leave this here for now and I go and I evaluate this guy。 Okay。

 we're just expanding expressions。 That's all that's happening。So let's do it。

 And now I'm entering a case。 He is my left subree。 No， empty。 It's not。

 It's an a single subree of one。 So I'm going to oh wait， I D is not one。 It is one。 Yes， okay。

And now I'm going to do another call to threefold L where I'm fold the empty subree。

 but my accumulator is 0。Because I'm now folding the empty。 That's the left child of this guy。 Okay。

 that's going return to me。 my accumulator， which is 0。Okay， and then what am I going to do。

 I'm going to fold my root of my left subre， which is the root of this subt。I take that  zero。

 and I pass it into。Let me， let me not skip over that。 Basically， what just happened here is I。

 I did the one plus0 for my function。Sorry， my terminal is actinging up。Whatever， let's。

 let's move forward。 So basically， I， I applied one plus 0。

 and then I pass that into another call to threefold R threefold， except on the right subree of this。

 Okay， which is empty。 So I'm just gonna return one at the end of the day。Right。

 and now Ive take I have my left folded from this subre， so I take that and I add it to five。

So here we see 5 plus one。This guy right here。I have the six， I apply it again。

 so now I'm into this call to treat foldel on the right subt， but now my accumulator is 6。

It's not empty。 So I enter into another call。 This one is empty， So it's just going to return to a6。

 okay。And then， finally。I add six to zero。And I get six。

Does that makes sense for everyone like I kind of want to just be able to visualize the expressions expanding。

 particularly for a function on trees， but if you like work out the math like oh let me go left。

 let me go left here oh it's empty， let me go back， oh， it's here， let me go right， oh。

 it's empty bh， blah， blah so on and so forth， but like you visualize the operations that are left to perform because they're literally still there we're in a let inside of a let that's kind of the point。



![](img/d474c7327a6e7791cbd47922abc312f5_5.png)

Any questions on that？Otherwise， we're going to move on。Yes， okay。 Allright， Otherwise。

 if there are no questions about that， I'm gonna move on。

But we're gonna to write another function called search。 Okay。

 Supp I want to find something in a binary search tree。

 I know you must be sick of binary search trees right now。 I quite liked them。

 I had a lot of fun with them。 but， I want to write a function search that has the following type signature。

😊，Badly， yall are being like super like quiet， like are you super confused after the foldel example。

 I'm trying to trying a temperature check here。Okay。Like I Im free to take questions about that。

 But otherwise， I'm gonna move on if you don't have anything in particular to talk about。

 Okay we're gonna try and do tree search with a predicate function。

 It takes a predicate function is alpha to bo。 I take an an element。

 and then I return a boolean on whether or not I want to search for it。

 whether or not it satisfies it。 Okay， and I want search to evaluate to the first element that satisfies this predicate。

😊，In the innertroversal， okay？So I'm just gonna like in order to search until I find something that we P true。

 Okay， this is a very common pattern。 right， We search for things in binary search trees all the time。

 but this search function will be for an arbitrary predicate。

 So we will write every single search function right now。 Okay， let's do it。

And what we're going to do is we're going to return to alpha option。

 why because it might not be in the tree， okay？All right， search P。Empty。

If I'm searching for something in the empty tree， what do I get。I get none。

 There's nothing in the tree。What a joy。 Okay， Otherwise， I'm going to be in the node case。L， X， R。

 what do I do， Well， remember， in order， left， root， right。

 I'm going to search in the left substrate first。So I'm going to call search。P， L。

 except I can't use this because this returns to me an option， right。

 because this thing returns an option， right， So remember， if I have a recursive call to a function。

 you learn this during sub the sum。 If I have a recursive function to a recursive call to a function that returns an option。

 I need a case on the recursive call， because I need to decide what to do with it。

 in most all option functions， okay。😊，So I'm， I'm going to case none。 I might run out of space here。

 but whatever。And't really have a choice， okay。Yes。Sorry， yeah， yeah， yeah。 not a binary search tree。

 I'm a binary tree。 Yeah， because we'd have to， if we wanted to do this on a BS T。

 we'd have to include a comparison function on this alpha star on this alpha type。 Yeah， sorry。

 slip of the tongue。 Thank you。Good point。But yes， we're going to be searching this tree if I have none。

 that means I didn't find it。😡，In the left， which means what do I need to do， I'm going to do this。

 If P of x is true， right， if my root is true。Then I return sum of X。Else。

 what am I gonna do if I didn't find that， That means it wasn't in my left subre and it wasn't my route。

 So I searched the right subre， right。Search PR。And what is my sum case。

 What happens if I get some from my recursive call， I know this is going to be hard to see。

 but I'll say it out loud。 What do I get if I return some。Just return it。 So if I get some X。

 I'm going to return sum of x。Not X， because that would make a night to check。Well， actually。

 in my type check， it would just be too constrained of a type。He。

 this is search on an arbitrary binary tree。And it's very pretty concise， I think， right。

 that's route right。 Like It know， I think these tree functions they pretty much speak for themselves because they they just。

 they claim what they are and nothing more。Any questions on searching a binary tree？😊，Okay。

And we can do this with like anything。 we can do on a predicate that looks for even numbers。

 We can do it on a partdicate that looks for the n factorial。 Okay， so on and so forth。

 But this can be an arbitrary predicate is the cool thing there。right。

 and I think that's one like again， I cannot stress you how important this idea is like these higher order functions。

 We are writing code that writes code。 The code is higher order。 The code taste in code。 All right。

 previously， we had code that was dependent on data。 Now we have code that's dependent on code。

 That is like the most meta and the most impressive thing。 Okay this is such a cool thing。

 It's so important。 I was looking at this over the weekend。

 It's so important that in Browns accelerated intro to Cs course。 They teach it in the second week。

 They teach higher order functions in the second week， which I thought was crazy。

 But this is really cool stuff okay。😊，Some people believe in a higher power。

 I believe in a higher order functions。 Alright， cool， So let's， I， I would say I。

 I would say I have  tenure。 They can't fire me for that， but that's not true。 So don't， don。

 don't say anything about that。 Cool， Alright， oh yes， Im supposed to look at men also。

 So I'm gonna do that real quick。😊，呃。Yeah， yeah， yeah。 All right。

 looks like no one had questions cool。Okay。There we go。 all right， Last subject。

 and it looks like we're going to be pretty much on time today， which is great。

I wanted to talk about how we can use higher order functions to make our lives easier as programmers。

 okay， I've already kind of talked about that with respect to these functions like folding on trees and lists and lions and tigers and bears。

 but the point is that we can use it to make the process of writing code in a really general way。

 completely independent of what we're doing。Easier， okay。

ll and this is going to be leaning into the combbinators thing。

 although I don't know if combbinators is precisely the right term。😡，But let's run with it。Okay。

 all right。So。Suppose I have a string of function calls that looks like this。 Okay。

 and I'll write it on the board for emphasis。 Okay， foo， left print， bar， left print， B， left print。

Well， I'll channel need to。AhCs， clocks always gets me， I'll dare it。Again， I like predicting myself。

 but as a next token predictor， turns out I'm abysmally poor， what was a chat GT joke anyways。Right。

 friend， right， friend， right， friend， okay。I already made a mistake writing this。

 I hated myself every second。 I was writing this。 Okay， this was terrible。 Alright。

 this is disgusting。 I didn't。 I didn't write it。 Okay， yeah， this is disgusting。

 Let me try not doing that， okay。If I have to do a bunch of function applications in a row。

 what do I have to do if I want to figure out what this code's doing if I see this code， I say， okay。

 you're taking X and you're okay， you're going to pass it into Ba and you're going to pass that into cooks and then you're going to pass that into bar。

 I'm going right to left。😡，Right。But I read left to right， right， I don't， I don't。

 I don't read Hebrew。 Okay， like I， I go left to right when I read。

 So this is not quite what I want to， what I want to see。 I want to see a natural progression。

 Let me give you an analogy， alright。Oh， I'm not give you analogy yet。 Okay， here's the。

 here's the thing。 I'm gonna define this operator。It's going to be called pipe。

 And here's the definition。 It's just fun X， pipe F。Is equal to F applied to x。That's all it is。

 if I have something like。What do I say two pipe。In two string。Right， the in tuing library function。

 this eventually reduces to2。Does that make sense。 So I'm。

 I'm saying the function now comes after the argument， al right。I claim to you this is， first of all。

 this is an extremely idiomatic functional programming thing， if nothing else you get out of today。

 like this is the state of the art。 Okay， this is what everyone does all right。😊。

And now I can write this。 All right， I'm going to write it。 I'm born for emphasis。

 I can write this X， pipe， ba， pipe， hooks。It know what cooks comes from bar， pipefuo。And now。

 doesn't that read like English。 Why， Because I take X。 What do I do do？ I do bass， Then I do cooks。

 Then I do bower， that I do fo。It's a list， it's a left to right linear list， okay？😡。

And this is what， this is what we get out of this， because what is this， what is this。

 if not a higher order function， It's a function that takes in a function。 So we can do this。

 But guess what， There's no， there's no secrets。 There's no nothing There's no gotcha about this。

 right， because guess what。 This is not hard coded in。 We can just define it ourselves。

 This is kind of like a diet drive about how S andL is nice because。😊，There's no gotcha。 like， right。

 this is just a derivation of what you already know， which is higher order functions， yes。好。

아 이게기도 됐어。That'll be weird， I have no idea what happens there。This is weird。Yeah。

 I wouldn't want to do that， to be honest。Yeah， essentially this will be like。No， you could。

 you could do this。It's a tuple of two comma in to a strength。

 I claim to you that this is going to be essentiallyly equivalent to that。 doesn't matter。

 but I claim to you this is essentiallyly equivalent to that， okay。

Cause you pipe in the pipe operator。 Yeah you know， whatever， anyways。

 the point is that nicely little little curiosityioities like that aside。 This is extremely nice。

 Okay， this reads a lot better。 Okay， whenever anyone does like I think that wet have a rule for it like if you maybe not。

 but if you have like three or more function calls in a row， you should be using pipe and set。

 Okay let me give you， let me give you an analogy。 Alright， I'm making mozzarella 6。 Alright。

 and I want to do， this recipe。 I heat the oven to 400。

 I have no idea 400 is the right temperature for mozzarella 6。 but I heat the oven to 400。

 I insert the tray of mozzarella 6， and I wait two hours and then oh yeah。

 it's right it's because I remove the cha remains。😊。

And I remove the chartrred remains of my monzar all6。

 I love reading my slides and like discovering the jokes I wrote like a month ago live in presentation like I wasn't expecting them okay。

 I want to do this recipe right because I am a responsible adult but let's see that in SML right suppose I want to make monzzar all6 in SMML here's what I'd write instead。

😊，I'd say let me call the function or actually let's two two ways， all right？😡。

Let's do it the first way and I'm going to conspicuously start all the way over here。 Okay。

 I want to heat the oven。To 400， right， supposeuppose that heat is like a cur function that takes in this oven value。

 right。And then what I do is I。Ins search。Mass， mats mats Tuesday。Mozzarella sticks。Okay。

 and this is also cur function。 Okay， And then I I put this into weight。And suppose it's like a real。

 like 2。0 hours， Okay， and then。I'd write remove。Okay， and I'm gonna to1，2。Alright， in SML。

 this is how I do it， right。But this looks gross。 Okay， does this not look gross。

 I had to like literally go from right to left。 I was I writing this on this board。 Okay。

 and I don't typically write production code on the board。

 but that doesn't change the fact that I didn't want to do that。 Okay， but I did it anyways。

 let's do better。I feel like that's kind of theme of the past like two lectures or so like let's do better。

 you can do better。right， you deserve better than them。 Allright， so let's write it with pipes。

 So this is gonna to be separate。Yeah， let's do he oven 400。😡，And what do I notice。

 I notice that it goes as an argument into insert Mos real estate， so I do pipe。Insert。Mozars。

And then that itself is an argument。To wait。2。0 hours。And that itself is an argument to remove。

And doesn't what。I don't think that would either。 I do not agree。

But this is this is pretty concise I think。If you look at that and look at this。

 they look pretty similar。 right， Like a recipe sheet has step 1， step 2， step 3， step 4， here。

 that's the same thing。 I follow my recipe going down 1，2，3，4。This is extremely idiomatic。

 except for the part we're writing code about Mozzarella 6。 is。

 this is idiomatic of the way that we sequence operations。 and I think it looks a hell a lot nicer。

 okay。😡，So。This pipe operator is really useful， and it's just a higher order function。

 It's just a consequence of being able to write higher order functions that we can write functions that themselves help us write arbitrary code。

😊，This is a higher order function that's completely agnostic to what we're using it for， okay。

 but it just makes our code nicer。Alright， and then it's there if in case you can't see the board。

 Okay， but that's how I would write it， okay。Any questions about this about pipe？15 minutes。

 let's go。Okay， all right。I think this is really important。 Okay， when like in my workplace。

 we use this， when I was employed at Facebook， we used this， right。

 Like this is the the state of the art。right， I feel like stressing that to you。 coolol， Okay。

 let's move on。😊，So I have some things to say here where like the pipe operators is basically stringing to other computations we say do this than that。

 but it only works if these operations have compatible ends。

 And what I mean by that is like this thing better have a type an input type that's the same as the output type of this right and then this thing better have an input type that's the same as the output type of this。

 it's basically like the same idea compose if I compose operations， they should have compatible ends。

 I'm stringing pipes together， I like to visualize it like I'm really building pipes and I check the pipe end like put them together if if they fit if it doesn't I get a type error but that's what I'm doing here。

 So。😊，But suppose I have a example for you here。 And this is the example。 Okay。

 I'm trying to write a function that will help me find a student's grade。

 I was in a little bit of an inspired mood when I wrote this。 Okay， I taken in two things。

 I taken in a string star string， which is a tuple of the student。

 the student's name and the assignments name and I taken another string。

 which is the name of a file on my computer， the path of a file。

 So like till the slash desktop slash。😊，1，50 grades dot S M L or dot T X C， Okay， or CSB， whatever。

 And then I want to look up that students's grade on that assignment and return to an integer。 Okay。

 Does everyone like kind of get the problem set up。 Okay， like the type signature makes sense， yeah。

😊，I mean to find the grades file， This is the path of the grades file。 Yeah， Oh sorry。

 this is will fine student grade student assignment grade file。拜拜。Yeah。But like okay。

 so like let me give you an example， which is。I'm going to right up here， actually。And do you find？

Student grade。And I'm not going to pick on anyone in particular。 So instead。

 I'm going to cl out and write Caroline。Hello basics。And then string tillda slash。

 tillilda slash desktop。Slash grades。Got CSB。 I realize you can't see this anymore。

 but whatever it's just it doesn't matter okay。I claim you this is what we want to do， okay？O shit。

Okay all right this is what we're gonna try and do all right but let's assume that we have some helper functions to help us out。

 I've got read file takes in a file path and returns to me the content to that file。

 it's string to string it's not super clear from the type signature but it takes in the path gives me the contents it reads the file I've got parse grades which basically reads in the data from the file like the literal plain text and like if it's comma separated。

 maybe it splits out comms maybe you know looks up things and this is type grades here that I don't care to define to you okay it doesn't matter but I've defined a grades type I have a grade type that codifies what grades look like okay does that make sense to everyone like I'm just saying that there is a type grades and that's what this function does。

😊，And then I have a lookup function that takes in this grades value and it takes in the same tuple。

 which is Caroline and basics， for instance， and returns to me the grade of Caroline on the basics homework。

Okay， everyone clear about this。All right， and these are our helpers。Well。

 I claim to you that actually， I want to do this。 Here's what I really want to do more than anything else in the world。

 I want to write fun， find。😊，Students， I'm really running that chalk here。Pine pun grade。Student。

A S SN assigned。And then， file。And what I'd love to do is， hey。

 what's that little handy little pipe operator I just defined for you unless you read file。On file。

 pipe that into parRS grades。Which takes in， Greg， because this this thing outputs a string。

 pars grades takes in a string。 So this's type checks。 I pass that into look up。

But first I give look up。Student comma。A S SN。And then I'm done because this yes， I'm done right。

 because this whole thing， it's worth learninging also that these pipes go last。

 So this is implicitly this。Okay。😊，Does everyone believe me that this type checks and this does what I purport that it should do？

 if you just strain together the outputs， this should work。Except this is not realistic enough。

Because I said something to you about how this only， so that thing。

 this only works if the ends are compatible， but these are not the types they should be。 Why。

 because I can read a file and it might not exist。 So how would I get a string out。

 I might parse a grade， but it might be complete nonsense and might be like not have commas in it or it might be written in Cyyrilllic Okay It might not be a valid grades file。

 so this shouldn't always return to me a grades。 I can look up a student in an assignment， but wait。

 last I checked Caroline is not a student in this class。 She's a T A。

 So this shouldn't succeed at all。So what I'm saying here is that these all of these functions。

 every single one of these functions should return to us actually this signature。😡。

Should have this signature。Because all of them can fail。Does that make sense？

There's a bunch of reasons I gave you each of these operations can fail。

 and then does this type check？Because read file of file returns to me a string option。

 I pass that into pars grades， pars grades takes in a string， not a string option。

 I can no longer pipe this here's what I have to do all right so to adjust our definition of this。

 here's what I need to do。😡，Let me see if I can still do this with in place。 I hope I can。No。

 I can't， I have to raise this。Okay， here's what instead I'd have to do to make this function work。

 I'm going to have to rewrite it entirely。😡，If I get none。I give back none， right if there's no file。

 I'm going to return an option finally， if I have some。Of S。Then， I case。Hars grades。

Of S of if I get none， I return none。If I get some of grades。Now I have to do case lookup。😡。

S assign for students。Gras。And I should have put it more to the left， but it's fine。None。

Goes to none。Oh my God， okay， we're almost at the end。Some。Res goes to some res。

Did you hate watching me write that because I hated writing it？This。This。Is disgusting。

It's terrible and worst of all。It's ugly， okay？We want clean code。

 We want understandable code These is。This is understandable。

 but it makes me want to stop being a software engineer and go be a lumberjack in the woods。 Okay。

 like， I want to stop writing code entirely looking at this。 So let's do better， shall we。No。

 what I'm doing here， Like what am I doing here， I'm every time I return none， I return none。

 Otherwise I move forward and I case the next thing given the previous argument。

 right like this looks very programmatic， almost like I could write something。😡。

That can make my function do this for me。Okay， so here's what we're going to do。

I'm going to define you something else。 Has anyone here ever heard of Monads， you know。

 have you ever heard this term Monad？😡，So like kind of a hyp beast functional programming term I don't particularly like that Monads are just modads right what it is is it's not important what it is。

 but it's a tool we can use to help write our code Okay it turns out that the option type is something called a Monad and the reason why that's important is because we can write this function here。

Fun bind， which takes in an alpha option。And it takes in a function of type alpha to beta option。

And it returns to us a beta option。Allright， this is just the type signature for bind。 Okay。

 and what I'm going to do is this is going to do this。I'm given an alpha option。

 so I'm going to case on it。If it's none。I return none。And if it's some。Of X。

Where this x' is of type alpha？Right because that's how an alpha option works。

 if I unpack it again alpha， I can now have a function F， which I can call on the alpha。

And I will get out a beta option， which is what I purported to return。

Is everyone clear that this type checks， like this makes sense of this type checks？

We're going to see how we can use it， and this actually kind of looks like what we were doing here。

 right like it resembles this looks like that logic。😡，Now we're going to rewrite it entirely， okay。

So here's my claim deal。Here's my claim deal。Be gone。Is my claiman to you， be gone with ugliness。

 be gone with inefficiency。 We're going to do things better。I'm going to use this bind function。

I need an alpha option。 So what am I going to take in， I'm actually going to take in。

 I believe some Actually， no， sorry， let me let me start off for that line。But no。

 I need to alpha blind。I'm going to take in sum of file。And I'm going to take in another function。

 which is read file。Oh， sorry。 I actually， oh sorry。 I gonna。

 I'm gonna show you cause I don't have a whole lot of time。Okay。爸爸啵，休よ。Yeah， yeah。

 this is way better than me ring out， okay。I claim to you this is what we're going to write instead。

 Okay， Oh， that was it。 except I I did it differently。 I defined bind for you just now。

As a twofold function， but actually strike that， we're going to define it as too cur， okay。Cool。

 this is what we're going to do， I say。Let me do read file on the grades file。

 which will return to me an option。 Then I give it a lambmbda， which takes in contents。

 which are the contents of the grades file， and it gives it to what do I do， I do bind of par grade。

 I parseel the grades with the contents。😡，Then I give a Lada that then takes the grades and looks up the student assignment。

 There should be a grades there， sorry。嗯。This might look like incomprehensible nonsense to you。

 And in some sense， it kind of is。 But the point is， when you see this。

 you should see something like sequencing。 It's sequencing。 It's like pipe。

 I'm saying do read fileile and then do pars grades on what you returned。

 And then look up the student assignment and then the missing grades and I understand this is a lot。

 So you might not see exactly why it does what we want。

 But I claim to you that the thing I just erased。 It is extensionly equivalent to that。

 It is short circuiting。 The bind operator takes care of that for us。

 Okay Another thing I'm gonna to tell you， first of all I'm going to claim to you this is much more readable。

 but not quite enough。 I had to write bind everywhere。😊，Some。

 some enthusiasts like defining this guy。They say say in， I don't know we have space，Could you tryNo。

 I can't。How did on earth， okay， interesting。In the middle of my lecture， come on。嗯。

Some people like defining this greater， greater equals operator in Haskell， they really like this。

 this is like the symbol of the language， they get really nuts about it。

 okay it it's just a mont it's just a pipe， but the point is that now instead of that we can actually write this。

😊，And doesn't this look nice。 Here's what it's doing。 Okay， Great。

 greater equal is just an in operator that is equivalent to bind。 So this is the thing I'm binding。

 This is the thing I do next。 The way you should think about this is that this is an operator。

 bind is an operator that takes in a function F。 The function F is what I do next。

 It's like the pipe。 When I pipe the right hand side is what I do next。

 But now this thing I do next is only invoked if the lefthand side thing didn't go to none。😊。

Otherwise， the whole thing goes to none and you should see this in the type signature， right。

 we're building pipes why， because I take in an option。

I can optionally unpack the option and then produce a new option。Or I produce nothing。

we're stringing to other operations that potentially have fallible output types。 That's all it is。

So I can rewrite my function as this。 And I think this looks so much nicer than bh blah da dah this。

 this， this Ldrich nonsense， okay。😊，What on earth is this， This is a minus10 is style points。 Okay。

 tell you what it is。So let's do better。 we did better。 This is better， all right。啊不不不不睇。

Any questions on bind this is not like strictly course content。

 but this is a really important application of higher order functions Okay like is this is a general pattern that makes programming programming period full stop with pipes or with anything better okay with optionals when we have things that might fail which means it automates error recovery for us essentially okay。

I can't necessarily motivate this super well in a sense。

 without giving you like a whole software engineering。

To like like like a whole software engineering of a year into your brains。

 But if you ever get a chance to use this， you will， this is really important Okay。

 and you can use this in like pretty much any language。Okay， but this is bind， montic bind， right？嗯。

And the idea is just at the end of day。Readability。 I want readable code， okay。 this was a bonus。

 You can look over if you want。 I put it there as a bonus specifically because if you look at it。

 if you don't get it， like I think it'll be fine。 Okay， it was just more examples of staging。

 We're right on time。 Please fill us out if you， if you care to。

 I really appreciate the people who've been filling out every week。😊。



![](img/d474c7327a6e7791cbd47922abc312f5_7.png)