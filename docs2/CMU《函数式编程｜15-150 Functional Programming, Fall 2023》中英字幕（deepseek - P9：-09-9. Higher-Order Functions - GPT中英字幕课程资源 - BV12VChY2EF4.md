# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P9：-09-9. Higher-Order Functions - GPT中英字幕课程资源 - BV12VChY2EF4

Hello functional programmers， we're here to learn about higher order functions。

I hope everyone feels okay after the midterm that will be graded relatively swiftly and by swiftly。

 I mean it's going to we're not going to do anything with it in the next like three days。

 but it will be great eventually。😊，Now we're at the certain point in the semester where I've sort of told you all of the really core things I believe are really important for being a functional programmer and we're not there yet。

 we're not done but this lecture I think maybe this lecture in the next lecture are going to be the last things that are really fundamental I feel the rest of the semester will be like case studies particular niches and techniques that are important but aren't like essential in functional programming and in software design in general。

 so when we conclude this lecture and indeed when we conclude Thursday's lecture you're going to be well equipped to pretty much tackle whatever problem you want I claim by using a functional language SML。

 whatever I think you could do my job after this in the next lecture higher order functions is really the last bastion of like really core important stuff so that's worth noting。

Right， oh， yeah， something I was gonna show you as well because this is contentious is。

House points is close it is close there is there is an opportunity honestly there's an opportunity for I love Brandon because I said I would not feel bad about giving them 20 points if they want today so if I love Brandon won twice like I would I would totally be fine if they tried。

あ。

![](img/d7b88ea1a19e87e9ab8512de9ea1315f_1.png)

So I'm totally， I'm totally okay with that。 You know， like， so just letting you know。 Alright， cool。

 awesome， let's get started of the lecture。 Alright， higher order functions。

 This is easily one of my favorite topics in the whole course。 Let's get into it。 So remember Menti。

 your old Pamanti。 you can ask questions anonymously。 Please ask at that link。

 and ask real questions， please。 There's only so many， so many minutes in a day。😊，But yes。

 that's the code。II don't choose the codes or I would have chosen something more auspicious。

But if I trust everyone's copy in of town， so otherwise well get going。

Okay so we only have three things on our docket for today。

 we're going to be talking about this idea of these things called higher order functions。

 we're going to explore the Hafaoo I call it which is really like a collection of five really core higher order functions that would be good for you to know and then we're told to talk a little bit about some of the theory and the math in particular how we can use that to help our equational reasoning and how we write our proofs。

😊，Okay okay， so this last time is now actually kind of relevant。 So I'm gonna talk about it。

 But remember that last time， well， last last time last time we took a midterm。

 but last last time we learned about parametric polymorphism。

 And we saw that we could have these polymorphic types。

 which were themselves like like a family of types we could have values that had polymorphic type that could then be used in all sorts of types like Neil。

 Neil could be used as an in as a bull list generically， we could use them at each use site。

 And then we also used it to define polymorphic data types like the true definitions of option and list And then we looked at a case study of polymorphic sorting where we wrote merge sort。

 but now we equipped it or rather， you know I went through two slides where。😊。

Merge store was augmented with the comparison function。

 which then let us define every sorting function ever。 Okay。

 and we're going to see that that idea is pretty much what we're talking about in this lecture， so。😊。

I had this idea where I said that we have a family of types。

 I said like a polymorphic type like alpha kind of has like a lot of types to it， right。

 Like alpha is in a family because you have alpha star beta that comes from it。

 you have you know in that comes from it。 It's like hereditarily。

 every type sort of descends from alpha。 Similarlyly， we have like length。

But like the length function actually has many instances of the length function， like we have length。

 which takes in an int list right and returns to us an int。And then similarly。

 we have the length function。But this one takes in a string list。And returns to us an inch。

 right It's a family of a bunch of things， a bunch of common models that are related by this idea of alpha。

 this general alpha or this general length and so on and so forth。

 And that polymorphic function was this one， right But these ones do essentially the same thing if you think about like length。

 The reason why length is polymorphic is because whether or not you're counting an int list or a string list。

 The code for length looks exactly the same， right So polymorphic functions seem like they have to do exactly the same thing。

 They're not that useful right except for code res That's actually not strictly true。

 because we have this idea of higher order functions， which are not just polymorphic。

 but are going to allow us to change the behavior of our functions as well。😊，Okay。

 so with higher order functions， we can use this to abstract away。Design principles themselves。

 common， common patterns in code， I claim。 Allright， I'm gonna to show you how that is。This is。你咩。No。

 went away right matter。 cool So recall we had a polymorphic sorting function。

 which looked like this。 We had sort， which took in our CP function。

 and it took in an L of type alphas and then whatever came after。 Allright。

 it does this one is polymorphic， but it doesn't do the same thing， right。

 because depending on this comparison function。 I give it。 It could do anything。

 It could sort in decreasing order。 It could sort a list of strings。

 It could do very widely varying things。 So this is an example of high order functions。

 We actually get into something more powerful than just doing the same thing but different types。

 So it's because。😊，Surprisse surprise， So is not just a polymorphic function。 It's also higher order。

 And that combination of being both polymorphic and higher order is what's going to give us this kind of power。

 Allright， let's look at it specifically， so。When I say higher order。

 I want to contrast that with this idea of first order functions with the first order function like most of the ones we've written this semester。

 they've taken in Ts right it's been like of type T1 star T2 usually or maybe it has a few more things and it returns to us like int or it returns to us like in option or if we get really fancy about it sometimes it returns to us int list we've had a little bit of an overreliance on these int types but the point is that these things are a first order because function types never appear T1 and T2 never had function types。

The idea behind higher order functions。Is that we can take in a function and return a function also。

Remember， functions are values。 They're treated the same as any other type， Any other value。

 any other thing that I can hold。 Okay， if I the same way I can have。

 I can hold it into my hand and I can manipulate it， Give it as an argument to some function。

 I can do the same thing with functions。 So that is the idea here behind this idea of higher order functions。

 Allright。😊，I want you copy that down briefly， okay。No， it's back。What even is it？Its ax。

 I don't think it was a lotx。 It was blue， I thought。you know what all these gotta go。 Co， alright。

Yeah， you know， okay， so sorts of higher order function， because what does it do， It takes in this。

Function I just told you， right， by taking it a function。

 we've abstracted it over all the possible sorting functions we've given it。

 We can customize based on that。 But how else can we do this。 So let's see it。

Here's how we could use sorted right or the sort of function I just talked about。

 we could define this function called modd 12 compare and then we could which takes in two things and then does their into comparison modd12 and you should be able to assure yourself this is type in or in order。

 okay？😊，And then we just pass it in right here。 to sort on 4，3，1，2。 And this should give us little 1。

2，3，4。 It's a non interesting mod12 sort， but it is sort  mod12， nonetheless。 Okay。

 and that's the idea of how we'd use this。 But that's just one presentation。

 We're gonna look at a different way of doing it。😊，Okay，And in particular。

 I kind of hate that I had to write out mod 12 compare。 Alright。

 one thing I thought about is programmers are you know。

 programmers are especially good at coming up with names for things。 Okay。

 we have to come up with names for things on the fly for a lot of。

 If there was a competition for naming children。 We'd probably win。 But I don't really want to。

 I don't really want to have to come up with this name， because it clutters my workspace。

 Now I have to look in another thing。 I have another thing I could possibly mistake。

 I don't want to do that。 So how can we do that。😊，Actually going I'm going to write it out here。

 Okay， so instead of that， what we're going to do is this。Well' actually design have an idea。

 what are we going to do？You probably already know。Lambda expression。 I like it。

Just because the high shoes are in the bag doesn't mean that they are're not here。Al right。

We're going to do a La expression， so instead of defining his man12th compare， I'm going to say。😡，FN。

X comm Y。Goes to in compare。X mod 12。Why mod 12。Left parent， All right， pre。What was a 43，1，2？

Oh well。 I don't care， actually， but。You know， so this is how I would do it。 I can do it in place。

 One of the really great things about land expressions that we haven't really seen so far is I can just spinit up a function on the fly。

 I don't have to give it a name。 I don't have to bind it。 I don't have to put it on its own line。

 If I want a one time function， I can use for something like a sort。

 I can just immediately go and use it。 This is a really important thing。

 especially when dealing with higher order functions。 But this is what I do。😊，嗯。So， yes。

 that's exactly what was going to write on that side。 Okay。

 so this is the case of when we take in functions， what about when we return functions。

 Let's talk about this。We have this idea called hurrying。Which is when a function。Returns a function。

And the name is interesting because the name actually comes from this guy called Haskell Brooks Curry。

who is a master in this field called Comatorial logic。 And I feel like stressing this guy to you。

 because this guy has not one， not2， but three programming languages named after him。

 There's the Haskell programming language。 The Brooks programming language or Brook。

 maybe in the curry programming language。 So this guy is a big name。 Allright。

 you should know that if you， if you pay enough attention this last， Maybe you want to。

 will have three programming languages named after you。 But Haskell Brooks Curry。

 And we have this idea of curing。 So how does that look。 Well， let's try it this way， okay。Yes。

 I do remember what I was going to do。I can write this。

Would anyone like to tell me what this function does， would anyone like to hazard a guess。

It it why it。It adds two numbers。 Okay， the addd function adds two numbers。 That's great to know。

 Another thing to know。 What's its type signature。😊，What's its type？Inserentent。

 So let's write that well。For reasons which I will I will leave opaque。

 I'm gonna to present to you a different way to do this。 All right， And I like to。

 I like to kind of give you this， this metaphor of a Ma。

 S I think I read this in a story or something once。 But suppose you build teleporters。 All right。

 and you want to go to China。 But your teleporters only go 50 me。 What do you do。

You teleport the teleporter， You put the teleporter into the teleporter。 So here's the idea。 Alright。

 I'm going to define a function which returns a function。 It's gonna to be called C add。

And the idea is once I've taken in one argument， which is my first integer to be summed。

 what I'm going to immediately do。😡，Is return to you a function。

 I'm going to return a lambda expression， taking in y。Which then evaluates to x plus y。

 We haven't really had reason to do anything like this。

 but this is something that if you like kind of adjust your mental model of how SML works。

 you should be able to be totally cool with this Okay and that's kind of interesting now right。

 because do first of all， like do you believe this is like legal syntactic SML code right what's the type。

 What's the type of this。好突条。Yeah， into end quantity by the last one， yep， that's correct。

And actually， yeah， okay， cool。 I like to predict myself。

 I like to not actually look at what I'm going to do next then。

 and then see whether or not I got it right。 So you're correct。 That's in two Pars。😊。



![](img/d7b88ea1a19e87e9ab8512de9ea1315f_3.png)

Int arrow int。 It actually turns out that I'm a。These function type arrows are right associ。

 meaning that if I write this， this is actually the same as this。😡。

So we can actually omit that if we want。 But yeah， good observation。 So int。

 So the way we would say this is int arrow， in arrow int， or we'd say int to int to in。

 And that is our cur add function。 Okay， and it kind of feels like these two should do pretty similar things。

 right， because what what's one way I could use these functions。 Well， I could use the ad function。

 What I'm going write is I'm going write。😊，Vow， you know。

Underscore equals add of two and2 or two and3。like you believe this is going to be like an integer。

 but I can also， how would I use CA？😡，Well， to use see add what I'm going to do is I'm going to first pass in this X。

 okay？😡，Now what I happened it was okay， let me actually display it to you display Cat has typed in to in inch。

 right？Where this is implicitly this。What is the type of CA to？In to end， right。

 We're just gonna follow simple rules to do that。 I can't give a high to all of you。

 assuming you other。 So now if this is sub type in to in， I can just give it an int as a function。

 right。So let me do it。Except that left parentheses are evil。 So let's not actually not do that。

 We're going to do this because this is actually understood to be the same thing because function application is left associated。

 So this is implicitly Pars around here okay。😊，And these look pretty much the same， right。

 but there's a little difference in intention between how I do this。Here's a question for you。

 are these functions。Extentionally equivalent。No， why。Yes， they do different things。

 even though in intention， they kind of do the same thing。 I'm gonna to hate you in the place。

 There we go。They can't be extensionally equivalent because extensional equivalence is only a relationship on things of the same type。

 Okay， so they're not extensionly equivalent， but they correspond。 They kind of do the same thing。

 And we're going to see that it might not be obvious why we want to do this， but I'll explain that。

 yeah。So this， anything that you put here is a pattern and underscore is a valid pattern。

 When I do this， I basically mean I I' I'm exhibiting this computer science programmer thing team where I don't want to come up with a name for this。

Oh， if you if you actually Oh， no， this is not a variable。 Okay， Yeah， actually。

 my first internship ever。Outside of my after my freshman year。

 I was doing this like machine learning thing in Python。 and I was like， oh my God。

 like I told my best friend like， oh my God， you can do you can do wild cards in in Python。

 This is so cool。 Turn out you're binding to a variable named to underscore。

 which is the worst thing I've ever seen in my life。 But I was so excited。 But no。

 this is actually a wild card pattern。 so you can't reference it。😊，Oh， I see， right， Okay。

 it shouldn't have changed the answer of that question。It wouldn't have changed the answer。 Okay。

 it doesn't matter。 I yeah， Talk to me to ask about that。

 He there was something about that on the midterm， but it wasn't important。 Okay， back to the thing。

 let's talk about cur functions。 So one thing to know also is that this is kind of gross to do because I had to write out this explicit lambda function。

 I wanted to return。 It turns out there's gonna be a nicer way of writing cured functions like this。

 Here's how we're gonna write it。😊，And then I'm gonna write X。 Oh my god。这意思。X， Y。

So here's what I just did。 I put a space in between all these things。 C add， space X， space Y。

 space equals， al right。If you and， if， if it looks to you correct。

 Like like we haven't done this all semester。 we've only ever put arguments。 Now， granted。

 they've been twos， but they've been one thing together。 All right， T is one thing。

 This is two things because space separated。 So this will automatically result in the binding of a function C add。

 which is a type in to in to in and this is just syntactic sugar。

 It is just syntactic sugar for exactly this。 Okay， so when you write this， please do write this。

 right， don't never write this。 But be aware of the fact that what's really happening is we're binding C add to a function that taste in a thing that then returns a function that takes this in。

😊，And this should also make sense to you in some form because the usage C space org space Ag looks the same as CA space orgspace Ag。

 right？😡，嗯。And it's also worth noting that I guess my sequencing is wrong。

 but this is all just intactctic sugar for this。二了。So these three things， what's like。

 What's that mathmatic， Oh yeah。The following are equivalent。If you want to feel fancy。

 just write that。Alright， so all three ways of writing Cd here are going to be intentionally equivalent to theML compiler。

 yes。What happens if you have three or more Well let's find out what happens if you have three or more？

那么。B C， add X， Y， Z， W， AB， C plus equals x plus Y plus C plus W plus a plus A plus B plus C。用。

A function that takes an int and returns a function that takes in an int that returns a function that takes in an int。

 so on and so forth。All right。

![](img/d7b88ea1a19e87e9ab8512de9ea1315f_5.png)

It's not the hardest thing in the world to do。 Its this is the part of the problem。 but yes。

 you can iterate that process as many times as you like for however， many cur arguments。

 It's really no different in intention than taking a tuple of all these things。

 but we will see that there's reasons why you should do。

 I will stop alluding to that and actually talk about it in a second。😊，Okay。

 so I talked about pretty much all the things I wanted to talk about。 It's right here。

 it's like next to this。It's actually Lte， good Lord。Okay， cool。 al right。So yes。

 so Cd is curry and this is how wed use it。 all right I'm pretty sure this is like all I wanted to talk about。

 Yes， I got it right， Okay， early quiz， take this one。😊，Okay。

 sounds like some people might still be taking it， I'm going to go ahead and get started but this next part。

Because we got the last stuff to talk about。 We got a whole zoo of h functions。 All right。

 we're going to take a ride on the wild side。 worth noting that I was looking while you were taking that quiz for the pieces of Hagma truck remaining。

 and there were nothing but like really small pieces left。😊，So this is what I'm working with。

 I feel like I'm collecting infinity stones here， but all right。😊。

We're going to talk about the hop zoo， which are several higher order functions that come into play。

 We talked about how cur lets us return functions， we're going to have functions that are both cur and also higher order and that will rather they take in functions okay。

So for instance， oh， I know what I should have done during the break， I should have written this。

 okay， well， whatever。嗯。😊，Suppose I want a function that increments all of the numbers in a list。

 Okay， and then not to keep you in suspense。 I'm currently defining that function for you， right。

So if I had x con xes。😊，I would just equate that to x plus1。Cons on to increment all of x's， right？

This is like one function I could write， and this is like a fairly reasonably common pattern right。

 and then suppose I had like a suppose I had a function flip， not flip one， it's just flip。

And it just flips all theoles in the list。 Okay， and I wanted to write that。 Okay， let me。 right now。

 actually， in some sense， it's educational for you to watch me write this because my point I'm trying to make here is that this sucks to do。

 Okay， not X cons onto to flip of X's。😊，Reasonable， like this is a type bo list to bo。

 This is a type inlist to in list， right， This one increments。 This one negates。

 but it sucks to right because if you squint your eyes， you look go really far。

 you take off your glasses， like you look at it。 like it looks pretty much the same， right。

 Like I'm kind of like doing the same thing， doing something to the element。

 And then I con it on to the recursive call and the rest of the list。 And then in the base case。

 I return Ne。 So like these feel in intentiontion the same。😊。

This is gonna lead us to an idea of a higher order function called map and map encompasses every possible function that lets us kind of do this。

 I realize I had some more motivation on the next slide。

 so I'm going to really fast context switch abstraction is the name of the game in computer science really if you think about it。

 instance we don't think about bits and bytes because we want to think about expressions and programs。

 we wanted to think about things like four loops and wire loops rather than go to is because this is better lets us communicate about what we do。

 The point I'm trying to make here is that higher order functions let us abstract over what this code is。

 we can write code that in turn kind of writes code for us if that makes sense we're gonna to see examples of this soon。

 but that's kind of the real strength here of higher order functions is how how much we can encompass the idea we can capture common design patterns。

 So all right。😊，Let's go ahead and do it。Here's what we're going to do。 We're in a right map。

 and I'm going to give you the specification of map right here。Map takes in a function。

 The function is type alpha to beta。 It means it takes in something and returns something possibly of a different type。

 I don't really care about what types， particularly。

 we use polymorphism here because we don't want to constrain it。

 then it takes in a type a list of that burst type and it returns to us a list of type beta list。

 which is whatever that output should be。 So basically， in intention。

 map should evaluate to applying the function F that was enclosed to every element of the list。 Okay。

 and you should convince yourself that this is going to be the design that lets us capture the idea of increment all or flip so on and so forth。

 Okay so let's try to write it， shall we。

![](img/d7b88ea1a19e87e9ab8512de9ea1315f_7.png)

All right， so first thing I'm going to do and I remember I said something about how like I can throw off the shackles of type annotations。

 but I'm going to do it for possibly one last time because it is going to get confusing otherwise。

So I take in an out list。And I return a beta list。So what happens if I try to map on the MP list。

 what do I get？The empty list， right， Let's do that。 recursive case。 What do I do， So， alright。

 I have map F， and I have X cons Xs。 And what I really want to do is I want to apply the function F to the first element and then apply to the rest。

 Well， that sounds exactly like what I did over here， isn't it， It's look。

 It sounds like it should look very similar。 So we'll do it。😊，If I'm trying to apply f to x cons xs。

 that's the same as me applying f to x is sorry f to x， and then coning that onto the result。

Of map F Xs。And this is our higher order function， our first one。 Well， after sort， that is。Okay。😊。

Map lets us do all of the things I just described。But now I don't have to go and write out this code because the code defines all of that code for me。

 All right， let's see it in action。 Let's give it a shot。

 if you believe me that this is the map function。Alright。

 so let's try it out on map Fn x goes to x plus1 on like 1，2，3。Alright。

 so I want to apply map to all these things。 What do I do， I step。

And the first thing that's going to happen is I'm going to case on it。

 right I'm going to enter into one of these two cases here。

And then I'm going to see that my argument is in fact not like this x plus1 right here。

 this is not of the form n， so I enter the second case。😡。

That's applying the function FN x goes x plus 1 to1， and then consing onto this right， So I do that。

 I do1 plus1， I get 2。Then I recurarsse on x's where x' is is 2， comma 3。

And then now I'm going to enter into the， not the nailil case again。

 because the two comma 3 is not Neil。So I do that again， actually I can make this a larger problem。

So I apply， I， I do， I apply the increment function to two。I get three， and I recurse again be I 3。

 I apply the function to 3， I get 4， and I con onto now I'm on x's is nil。

 So I enter into the nil case。And then finally， I collapsed all the con and I'm done。Yeah。



![](img/d7b88ea1a19e87e9ab8512de9ea1315f_9.png)

It was on the slide。 I think I didn't write it out， but yes。Oh yeah。 So this is a good observation。

 which is that。😊。

![](img/d7b88ea1a19e87e9ab8512de9ea1315f_11.png)

The trends are important here。 All right， if I write this type。Alpha a beta。



![](img/d7b88ea1a19e87e9ab8512de9ea1315f_13.png)

Two alphaists。To bealless。 Okay， this is a function， which the first thing it takes in。

Is of type alpha to beta。 It's a function of type alpha to beta。 That is different。Then this。

Why can someone describe why？Well， functions are value。 So this is also a value。 But it's taking in。

 it's taking in some basically， the point is that taking in it's going to return a function and this function is not the same as this function。

 So I guess， I guess the way I would describe it is this is the first thing， the first ag。

 and this is the return。This is in this one。 This is the first argument。

 the type of the first arguments， any type alpha。 And then the return is something of this type。

 So if you want to think of like the cur arguments as like a number of functions。

 this one has two arguments， right， distributed overcur functions or overcuring。 and this one has 3。

Okay，Does that make sense to everyone yeah？Yes， there are implicitly parentheses here because of right associivity of the type errors。

 That's correct。 I'm omitting them slightly。 but you could be a little more supposed to to write this out。

 And this would be fine to do as well。 We typically don't。😊，How always say。

 we typically don't write these parentheses because the usual mode of use of this function is we give these arguments this one and then this one simultaneously。

😊，But there are use cases for why you might want to return a function as your primary use case and we'll see that in like 20 minutes。

But that's a good observation， right？😊，Everyone就。But that's how map works。

 and so now what can I do instead of defining increment all and flip like this。

 here's what I can write。😡，Let's do this。本。Increment all。L。

 so if I want to increment a list L now instead of doing that nonsense where I define it explicitly。

 I'm going to make this recursive， here's what I'm going to say。😊，Map。F and x goes to x plus1。On L。

 And if I wanted to define clip， I believe that this is actually not exactly the example I had yet。

 I had two string all， but I don't actually care。If I wanted to just flip， I would say map。

F N X goes to。Not of x。Onto L， do people see why this should be incrementalcr all and flip。

 I'm mapping， which means I'm applying this function， which flips everything。

But I'm giving it as a land expression because I didn't want to give it a name。 Yeah。

 you got a question。 but I'm giving it this lambda expression because I didn't want to give this lambda or this a name。

 I could have， of course。 but I didn't want to。 Okay。

 so this is how we can write increment all and flip。 And we now we don't have to define it at all。

 because why， because it'd be code duplication It'd be ugly And then two。

 every single time you write code。 there is an n over percent chance that you write a book Allright。

 I don't care if it's incr all， I don't care if it's flip。 Like if you write enough of these。

 you'll start to write them wrong。 Okay， I've done this。

 So it's a kind of a profound thing like by writing less code。

're by default we're by definition writing more correct code。 Okay。

 that's that's like why you should think that code really matters other than inconvenience in your life and your loved ones。

 okay。😊，So both those things seem me true。 right， Everyone good on in yeah。Oh， these things。 Yeah。

 Oh that's good idea。 Okay， so let's do this one， right， Okay， so map has type。Larry wrote it。

 but I'm going to write again down here。This is true， right。

 It's up type alpha the beta to alphapha is to beta list。Well first， let's try to type check this。

 right， what is the type of this slammed expression？😡，In to end， right。

 So I'm passing in something of type in to end here。Right， now by analogy。

 I know this is gonna get a little hard to see。 sorry， but by analogy。

 Al takes the place of int and beta takes the place of int。

 Remember how we were doing tight checking in the presence of polymorphism。

 That means that now I have alpha where alpha is。Ent。

And I beta where beta now has a constraint that beta is equal to n。And if that's true， well。

 can't I just go and replace alpha beta with whatever they are， everywhere else， so I get？Priends。

Int list。To enlist。And if you believe me， this whole thing。Is the type of this in map？

This whole thing。 And then so I take in the in in， and I take in this function of type int list。

 And then S M will type check this whole thing to be a type inlist in list。Does that make sense。

But this is kind of what's happening behind the scenes when SNL type trip these。

 that's a good question， like we're instanting these polymorphic type variables based on clues given to us by what is passed in to the polymorphic function at the use site okay。

All right。Okay， cool。 But that's that。 So we can write increment all and flip。 Okay。

 any further questions on that before I move on。😊，Cool， we have plenty of time。 So， alright。Yes。

 and then I'll also say something about this increment oil is essentiallyly equivalent to the previous increment oil。

 and we'll give that a more detailed treatment in the third half and by half， I mean， third。😊，过。

But I claim there's something not great about this。 Alright。

 and it has to do with this thing back there。 I don't know。

 I'm doing this thing back there called partial application。 Okay。

 I claim that I shouldn't really want to do this。 Okay， let's see why so。

I'm going to have to reuse some board space here increment all。And map。

 the thing about map is that map returns to us it function。

So why should I have to write out this declaration of Increment all where I take in the L explicitly。

 and I give it to this。 Why couldn't I write something like this？ And sorry， I'm going to keep。

 I'm going to cover that up。 But here's I'm to write。Does this make sense？This is type check。

 can I give not all of the arguments to map at once？The answer is yes。

 I can do this because let's compare and contrast them again okay。So I've got increment all。

 I can either define it via saying increment all is equal to map given the incrementing Lambda。

 or I can say fun increment all taking in this L is equal to map。😡，Increment L， right？ Well。

 let's see it in U。 So， let's even actually， I'm gonna do it down here。 It's more convenient。

 Suppose I wanted to use this second increment all。 Let's call it increment all prime。

 I'm gonna adjust the definition in a second。Let's call this one increment all prime。

What would happen if I said increment all？All prime。Given one comm two。Well。

 let's unpack the definition， so this would step two。Map。

I should have picked a lambda I wouldn't have to write out explicitly every time。But。

And then given one come two， right。So this is what increment all given 1 comma 2 is。

 but lets let's use this one， what about that one， if I did just increment all like without the prime。

😡，And I place an x1 comma 2。 What would I have， Well， let's unpack the definition of increment。 Oh。

 it's equal to this thing， right。So this is essentially equivalent too。Whatever that is。

 which is map。FN X goes to x plus one。Next one， one come2。And by Jove， aren't these the same thing？

So if I put it next to its argument， no matter what， I've got something that were these。

 both these things are equivalent to at the end of the day math given the incrementing Lambda。

 and then the list I inputted， okay， even though the presentations were different。

 even though I didn't explicitly name this L when I did the above definition。

Does that make sense to everyone， do everyone see why these are exactly the same pretty much？有。Yeah。

 so I'm using this reduces to here because this is the literal definition of beingcr all prime is that given an argument here。

 it will reduce to map of b of this。I use extension equivalents here because I wouldn't actually say that this reduces this is。

 I would not say this is a true statement。And this is kind of subtle。

 It's because when I bind an in all， this is an expression。 So this goes to a value， right。

 It doesn't go to this thing。Is not a value。 So I can't say that this goes to that because that would be kind of like going backwards in time and saying that two。

St to one plus one。Basically， the thing I would rather say is that。Map of this thing here， okay。😡。

Go to like some function F。Right， some like some like most reduced function。

 And then we produce an environment where F is bound to increment all。But in this context。

 I wouldn't say that I think it would be proper to say that this actually reduces to F。

Of one comma 2， that same f that I defined up there。

 but it would not be proper to say that it steps here。

 Do you see what that is because this steps to this sorry， This steps to this F right here。

Well the F doesn't go the other way。 This is more simple than map given this Lada。

 Basically what I'm saying is that map， given that Lada is not the most simplified form it can be。

 So it wouldn't step to that because that' would be moving backwards in terms of simplification。

 Does that make sense， It's not like super important to know。

 but this is kind of like one of those really advanced things you should have an intuition for if you really hardcore like understand what SML evaluation is doing。

하루 people 배워봤다 다음사 광장。It's not super important。 we're gonna move on。

 but I'm free to talk about after the class if people would like to。

 Okay this is mostly a notation thing。 Okay， allright， let's move on。

 So the idea behind this thing I was describing up here is something called partial application。

 We're using map， but we're using it partially applied。

 I haven't given it all of its arguments because if I don't give it the final list。

 I still get a value of type in to end。 So the value in。😊。

The value in partial application is that now I can write stuff like that where instead of explicitly defining incr all and tutoring all。

 I just use map given a single argument and the next one is implicitly being waited for okay and we'll see a little bit more about that later。

 but this is the strength of partial application is that it simplifies our code that we can write Our people have good on this。

😊，Any questions？Yeah。最可。Yeah， map already takes in another argument， like if we look again。

 I'm going to keep doing this if we look again at like this place where I use increment all。

This is just essentially equivalent to this。Right， because by definition。

 this is map given the increment。 The， the place where the list comes into being is when I place it literally next to it。

 And then by definition， yeah， map expects another argument。 I guess that's a fair way of saying it。

 Yeah， cool， yeah， any further questions on this。 Maybe I don't have enough time。 I don't know。

 It's fine。 We'll go with it。😊，ok 嗯。So， okay， this is just the justification I just gave you。

 So this is something called aid expansion。 This is not super important。

 but you can say it to sound friend include to your friends at parties。

 But the idea is that if I have F of type T 1 to T 2。😊，This is F is always essentially equivalent。😡。

To F N X goes to F X。Does everyone see why this is？This equivalence always holds。

Because it's no different from me saying F， which is a function， F is a function。

 it just is versus saying a land expression that take a function that takes in an argument and gives it to F。

If I were to use this lambda， I would give it to F anyways。

 The most easy way you can see why this is true is if you do this。Suppose we're giving it a value B。

 and this literally reduces2。F B。So for all values V， this one reduces to that。

 so therefore this must be essentiallyly equivalent to that。Does everyone buy what I'm saying？

And if not， please speak up。Okay， that's called8 expansion。 It's not super important。

 but the idea is that you can simplify your code by removing places where you see this。 Okay。

 that's kind of why I said earlier， this is gross because I noticed that this was the8 expanded version of that。

 By that。 I mean， here I have let me use colors。😊，I have L here。And I have L here。

And what did I do when I define increment all above， I cut up the middlemen。 I removed the L。

 I took the L。 you could say， alright， I cope with that。All right， great。

 we do have all this up to cover。Cool， but the idea here is just that map is a hierarchy of functions。

 Map defines every function that involves transforming the data in L。

 there are so many more applications than just the two I showed you here。

 Increment all and flip and whatever。 Okay， but that's kind of like one of the beautiful things about higher order functions。

😊，O。And yeah， so another thing I showed you this kind of came up on your on your quiz。

 But when we defined sort earlier， we had it be tud。

 We had sort that took in the comparison function and also the list both at the same time。

 But if I wanted to， I could curry the function。 Does everyone get what I mean when I say that sort cur is the cured version of sort in the sense that instead of taking in a tuple I' write done。

 instead of taking in a tuple， which is alpha star alpha to order。😊，And then star alpha list。

To alpha list， the type of sort cur is where I just change this。To narrow， yeah。Yeah。

I would not say that that was true if F were not a value。Sorry， Imlic was quantifying over values。

 I would not say this is true if F were not a value。 Yeah， that's actually a very good observation。

 that， in fact， I'm going to claim to you， if F loops forever。

This would not hold because this will look forever。This would not。可以。

You don't have to see why that is right now。 We'll cover this in about five weeks。 gonna be。

 it's called laziness。 But I， there's also something good to know now， I guess， but yeah， the things。

 things in lands are frozen。 I， I'm not gonna give this more treatment because I've been talking about this next lecture。

 But yeah， good good observation。😊，Really good observation， actually。Right， cool。

 so if I wanted to curry my sort function， here's what I would do。

 And then I could define all of these int sorts and string sorts and mod 12 sorts just by using sort cur in a partially applied way。

 that is to say I give it just the sorting function I don't give it the list and each of these are themselves function。

 Int sort is a function of intlist int list String sort is a function of string list to string list Does everyone see why I can do this because I've cured it so that I'm leaving the L unspecified。

 but it's still going be taking it in。😊，Does that make sense， yeah？Maybe， actually， I totally li。

 I don't have some time。 Okay， and this is really powerful because remember that big page I had where I said merge sort can be written so fast。

 Still 20 lines。 I don't want to write 20 lines for each of these sorting functions。 Okay， now I can。

 Allright， cool。 let's go ahead and do it。 yes。😊，And I just have some actual remarks here where map has basically like the platonic structure of transforming list of data。

 I get a little philosophical there。 it's not really important。Cool。

 another thing that is very common is that we usually want to like take in a list of things。

 and we want to keep only the elements of the list that satisfy some condition。

 And that should sound like a higher order function to you when I say some condition because we're gonna be concretizing that by abstracting over it。

 Okay， this function is gonna be called filter。 Here's what it does。

 A function filter has say alpha to bo takes in an alpha list and returns an alpha list。 Okay。

 And it just evaluates to it cuts out all of the elements in the list that don't satisfy that predicate。

 I'm gonna write it for you really fast。😊，But if you understand map。

 you probably will understand how filter works。So filter given the empty list is just the empty list。

 But if I have P and x cons where P is this function of shape alpha tobu。I have two cases。Px is true。

In which case。I'm going to， oh， sorry。 This is not the right case。 X clientss filter。Pxs。Else。

Filter Pxs。Does everyone see why this is true？嗯。So if my element I'm currently looking at satisfies the predicate。

 I keep it and I recurse， otherwise I don't keep it and I recurse。And sort of inductively。

 you're going to keep only the elements recursively。

 this will mean that filter will only ever keep elements that satisfy P。자 연결ness。

This is like tricky easier， I think， than map， to be honest。Okay we okay， if no questions。

 we will move on from this。And filter can be implemented like so who would have guessed Well with different indentation。

 That's fine。 I woke up on the different side of the bed today。Okay， so。

Here's the use case for a filter。 Suppose I want to write stuff。

 And I'm not gonna write all this out。 I'm gonna let you look at it。 But here's what I'm gonna to do。

 I'm going to define an is even function。 It's just a lambda takes in a number and tells you if it's even。

 Then I have a keep evens function， which is filter is even。 Let's actually work through it。

 What is the type of keep evens。 And someone tell me。😊，我的笔不黑。So I claim to you。

Is even as a type into pool， okay？Were like keep evens。Which is the application of filter。

I realize I put away the type definition of filter， so maybe it'll help if I write it up here。

Alpha the bull to alpha list to alpha list okay？So the type of cheap evens is going to be given this int to bull function。

 taking the place of that， it's going to be whatever is left， but with alpha replaced with int。

 so I claimed to you that Ke Es is of type int list。😡，To inlist。Okay I partially applied it。

 even though its filter takes in two arguments， I've given it only one。

 that's okay because of partial application。Then isn't it the case that keepevens given the list of 1。

2，34 should be a type int list and in fact this is true Keep even I'm showing you that this is what it evaluates to Keepevens 12。

34 will evaluate to1 comma 3 and if you step through all of the filter stuff you you can think about why but one of the really cool things here is you don't need to think about how filters implemented think about filter at the high level what does filter do it keeps stuff that satisfies this so obviously filter is even on 1。

2，34 should be one comma 3。😊，I'm saying obviously， it might not be obvious to you。 Okay。

 but if you think about at the high level， you I think you， I claim you can see what this is。 right。

 And if I define keep odds， I claim to you that。This lamb right here is also going to be a type intobo。

And therefore， keep odds。Who would have guess is also going to be a type inlist and， okay。

So then if I use keep odds on 1，2，3，4， I'm going to get20， whoops。Thank you。 You know。

 it only takes me like three minutes of talking through the slide before I notice。

 Thank you for that。 Yes， it's， it's flipped。😊，But if you think about that at the high level and you you should read the slide。

 one keep evens on 1， two，3， comm 4 is going to be two column 4，😊。

And when keep odds is going to be one come of three。Yes。😊，Applying functions in pandas。

I'm not familiar with pandas， but I would assume so Yeah， Python has three functions。

Second inner tools thing or something。 Yeah， the 1，50 grading infrastructure used to use it。 Yes。

 but that's how that works。 Co， Any other questions on this。😊，Sorry for the typos。

 I don't actually like check when I'm making these， yeah。

the languages I don't C does not have a proper notion of cur functions。

 C you can only pass around function pointers which are strictly less useful than first class functions。

Not important， by the way， but I'm a C does not have such things because C does not have nice things。

 K and R really dropped the ball on that one。 Alright， so， but this is the example。

 And well go with this。Good question。Fun question。嗯。But I hate this。 All right。

 I hate I had that I had to write f and X goes to not of is even of X。

 I had to write two parentheses here。 I had to explicitly give a name to my variable I was taking in。

 I hate that。 You'll find that I think I say it here。

 I'm some functional programmers would rather be hit by a bus and have to write out an explicit land expression。

 I'm not usually one of them， but in this case， we can do better。

 and maybe you don't know that we can do better because we haven't seen that we can do better。

 Here's here's other lesson of the day。 you can do better。 I believe in you。

 but here' but we're gonna try and do better。right， so for instance， by analogy。

 let me give you this。 I would rather write map fxs than map F and X goes to Fx of Xs。

 This is the ada expansion of F what I told you earlier。

 but I claim to you this is strictly uglier than that。

 Does everyone see why like I had to write more。 I claim to you that this is ugly for that same reason。

 but it's not clear in how I should write it。 So let's figure out how to write it。😊。

And this is going to lead us into something that's going to satisfy the Ma people in the audience or you're all math people。

 because this is going to be called function composition。

Something you learn about when you're like six is function composition， which is straight。😊，😀う。😊。

That's not true。 I'm lying， I didn't learn about it when I was say function composition。

 right where I can do G compose F， and then this on x should be equal to F of G of x， right？😊。

And this is like a nice like notation I can write because this just makes my life easier than when I'm doing math。

 right， I want to write less symbols。 Okay， but turns out we can do something similar in M。 Okay。

 so we're going to write a function compose。😊，And all we know， Okay。

 all we know about this is that G。Goes from some type to some type。 Okay。

 this is like in the math sense， right， G maps from T 2 to T 3， and then F maps from T 1 to T 2。A。

 shoot did I， sorry， my bad。I like， I like explicitly with thinking， I'm okay。

 I'm gonna should I write F O G or should I write G O F。

 I'm gonna write F O G because then I can write F of G of X or G O Fcause of that same reason。

 And then I flipped it when I went here。 Sorry， Thank you for， Thank you for pointing。

 I'm gonna give， I'll give a high true to everyone in the room， for speaking up。😊，I'm joking。

 I can't do that。And that means that this whole total composition should map from T1 to T2， right？T3。

 sorry。Does that make sense for everyone。 Thank God， I finally said something right。😊。

But let's do it an SMML。 So what does it mean for any function T1 and T。

 for any types T1 and T 2 and any types T 2 and T 3 to to do something。 it means。

I've got polymorphism involved， right， because that lets me take in anything。 So here's， I believe。

 my spec of compose Compose takes in a two of two things。

 One of them will be a function from beta to Cta， and then one of them will be a function from alpha to beta。

 Okay， and I'm going to return to you this， yeah。😊，我是。R with that for a second。

 oh actually I spoil it here， there's an Iix operator O defined an SML that does that。Yeah。

 compose can be just replace compose with O。 I was trying to hide it from you。

 but I I actually spoil a little bit here。 But yes， compose is pretty long。 But let's define it。

 Let's actually pull away the wall。 Alright， So let's do it。😊。

So assuming that we have an impex operator O， here's how we define it，5 G。O， F。

 remember that this is our infi operator defining syntax。

 I put the first argument here in the second argument here。 this is going to be equivalent to。

F N X goes to。G of Fx。Okay， this is of type， right， I said earlier。

 but I'm going to emphasize it here。都。Beta to Cta to alpha to beta。Two。

 and I claim that actually here to answer your question。

 this is where I might want explicit parentheses。Because my main use case for compose is I produce a value of type alpha to gamma or if I do this and I usually give it this argument。

 that would be fine。 Like if I explicitly write out the X。 but usually I'm not。

 Usually I'll just say I've got G， OF。 And that's it。 That's all I want。

 and maybe I bind this like a value。 Okay so I claim like it might be an intention better to put the print here。

 again， it doesn't matter because they're equivalent Okay but this is the type signature of compose。

 is everyone go with that。😊，Okay， let's revisit our life decisions。

 which is here when I wrote FN X goesson not。Is even S Can someone tell me what I can do here？

To make this less ugly。What do I do here？Yes。Its， it happens to be convention in NJ that everything that's everything usually is like in operators rather are。

Two it doesn't need to be the way。 And hassle is not the way。 and O came is not that way。

 Ask Bob Harper up in 9，1，1，5， not 9，1，1，5， but what are the9 offices。 He designed the language。

 I'll tell you why。 But I'm yeah， I don't know。 cool。 But yes， What do we do here。😊，有。

So let's try it。 So you said， let me put it up here。You said not is even。

So is even as I' type intobo， right？And not， if you can see this。Not is a type。보 to 보。

So we'll type check if I give。If I give them this as with this type。As an input here。

 wheres expecting a bull。No， that way， yes。Let's compose it。That's all we needed。Good本嗯。

Budy guess after defining compose， we're going to use the component operator， but sorry。

If I compose both of these two things because doesn't this look exactly like F of G of or G of F of X。

 it's the same thing I've got G O F， which is defined to be the same thing。

 Like if you look at these two things， I actually pattern match onto each other right so I can avoid all my troubles and an extra friends and of lambic expression by writing it。

Da da da writing it。As such。Okay so instead of doing what I was doing before where I don't have it on the board anymore。

 but I would instead say that is odd is not or even is even。

 or if I didn't even want to give it a name， I would instead just use。😡。

I would just use on the right here。Filter。Not O is even。One， two come at three come up four。

And this whole thing type checks， and this whole thing is the same thing。 So this should be not even。

 Oh yeah， it's one comma  three。系。😊，我了。Doess everyone good with this？Yes。Oh， a definition。Oh。

 this thing like around here。Oh， oh， I'm here。I like here。 Oh， I see what you're saying。 sorry。

 I'm used to that。This bands tighter the superple binds tighter。

 So by convention I you it would probably be more clear right this way。

 but I'm used to the fact that function arrows， basically the way you should think about it is function arrows are like the weakest thing around。

 Like they always go last。 So everything between function arrows is like its own thing。 Yeah。

 but that's that's that's a good point。Cool， okay， I got 15 minutes to talk about folding。

 So we're gonna do that。O。How many of you？Right， Python。Raise your hands right now。Okay。

 T is we take off some points from no。😀呵呵。😊，All right。

 so a very common pattern in Python I claimed to you is where do you do something like this right？😊。

Actually， what's not call X's called act。Alright， if you don't know if you don't know Python and you don't read this like it's fine。

 just read that pseudo code。 but a very common pattern is I say I got something a。

 I said to some default value and then for everything in a list， I like do something Yes。

 I do something with X and then I assign it to act right Maybe also a is involved in there okay。😊。

Okay， like you see what I'm doing， I'm kind of like doing something for everything in the list。

 For instance， summing everything in the list takes this sport， right。Well。

 if you don't want to use like know the sum thing or whatever。But I would say like act plus x， right？

Fair enough。I hate having to do this。I had to write out a four。That's too much for me。

 We don't even have four loops and。 That's actually not true。

 that is true We don't even have four loops and SML。 All right， So so this is like as an analogy。

 doesn't precisely work。 But the point is， I don't want to have to do that。

 If I've got other avenues open to me。 So let's try to do that。

 So the idea here is that we're summarizing everything in a list。

 We're trying to do something for every item in a list and not necessarily produce a list as output。

 because if I map， I always get a list as output。 But if I sum everything in a list， I get an int。

 So let's write it。 This thing is called folding。 right。😊，嗯。So basically。

 the idea is like if I write ML functions like some， you know I sum for everything on the list。

 or I can cat a list of strings， I'm gonna use my concatenation operator with my base case of the empty string。

 or if I'm trying to flatten a list as you do on your homework。

 if I'm cheating I'm allowing to use a pen， I would instead a pen where my base case is nil does this make sense to everyone that this is like a thing that sometimes we do。

😊，Well， again， squint in your eyes， go 50 steps back and then look at it like these look the same。

 So let's try to fix that。😡，This is something called folding。😡，As Im， I， I I didt reverse order。

 but I'm。Alright， here's the point。 I'm going to define a function that's got a really complex type。

 Okay， and we're going to work through it。 This is the type。Alpha star beta to beta。Two beta， right。

 yes， two alpha lists。Two倍ta。Let's work through it。 All right， it's four parts。This， this。

 this and this， okay。The first thing I got is what I call my transforming function。

 It's what I do for every element in the list。 The way you should think about it is。Beta。Is the type？

Of accumulator， I'm essentially automating the process of what we did with T length and T Re and whatever。

 I'm having an accumulator beta。 Okay， so beta is all of these guys。And then， alpha。

Is the type of elements， the type of elements that I'm using to transform my data。😡。

So if I'm folding with this， I'm taking a function that uses an element from the list。

 it uses an accumulator， and it produces a new accumulator。 Okay。

 I call this the transformation function。 It's the function I'm calling for every element in the list。

😊，This is my what I call initial accumulator。😡，It's my initial value。

 the same way that when I was writing those functions earlier like sum and a button。

 Id base cases of like0 or nil， right that's my initial accumulator。And this is my。

Lists to be folded。Okay， and I get out。My final accumulator。In terms of purely the type。

 do you see what this is doing， Do you see why this should be a thing that works， Okay。

 I'm saying give me an accumulator， do something to it for every element in this list。😡，Right。

 and produce a new accumulator each time， and eventually we'll get out the final accumulator once I run out of elements。

 Okay， the same way that if I had this， this is my initial accumulator。For every element in the list。

I'm going to。Call F。X and act and reassign act So I produce a new accumulator。 And eventually。

 once I'm done， I'm going to， I guess all the the corresponding analogy is I return act。OK。

Spiritually， do you see what I'm saying here？We're going to look at some precise examples。

 but this is the type signature for fold， and we're going to go and implement it。

The idea is that we're just keeping an accumulator with us and we change it for every element in the list。

 right， I'll leave this up。こう。This is our type signature Fold L takes。

 it has that exact type I just described to you， but fold L is going to fold from the left。

 What I mean by that is if I have a list of x1 comma XN。😡，If I fold L。And by convention。

 this is usually called F。And then Z， my initial aumulator， this is going to evaluate to this。😊。

F given。X N iterate that process。 and in the very middle， I'm going to have F given x2 of F given x1。

Of Z。So what I mean by that is I'm going to take the first thing off。

 I'm going to combine it with my initial accumulator Z。😡，I take that result。

 the result of doing the first X element， and I combine that with x2 using F。😡。

And then I keep doing that。 Keep carrying along that result until eventually， finally。

 I combine it with X， N。 The idea is I just have an accumulator， and I'm。

I'm going to update it using F with every element of the list。Okay。

 I'm trying to speak in very broad， like high level terms。 so you get the algorithm。

 like what it's doing into your head。 the specification。 Is everyone good on this。

And it's called fold L because what order are we doing in it。 The innermost one is x sub1。

 So the first thing will be fold is x sub1。 We do it from the left。

 We take the accumiliator and we put in everything in it going from left to right okay。Right。啊。

I guess I'll use， I don't actually care。Let's implement it。 So here's I'm going do。

 I'm going to write on this board。And remember， this is the type ofphistication up there。Fold L， F Z。

 nil。If I have no elements left。And I want to combine my accumulator with all the elements of the list。

I just returned my accumulator， right， I have nothing left to combine it with， okay。

If I'm trying to fold L。And I have F。I have Z。And I have x cons xs， right， That's my next case。

What am I going to do。Well I told you earlier， the first thing I want to do is I want to take that x1 and combine it with Z and then keep recursively going forward and pay that back。

 so I claim to you what I'm going to do is this。😡，Boldll。F， the same F。

But I'm going to do F of x comm a Z。Aes。Okay。This is what I'm going to do。 Okay in retrospect。

 I definitely misjudged how much time I had originally。

The first thing you have to realize is the first thing I do is I take the first thing off and I combine it with my accumulator that's going to correspond to folding left because I want to go left to right and then I'm going to recursively do that for the rest of the list。

 I take my accumulator and I change it once and I keep changing it for everything else in the list and kind of like the order we can quibble about later。

 but this is what the algorithm is doing。😡，The existence of fold L implies the existence of fold R。

So let's talk about folderar， which has。This is actually this is an aside of how we'd use it。

 But basically if I wanted to use fold L。 If I wanted to define the function that sums a list。

 instead of writing the sum， I would write fun is sum L is just folding with the plus function and given0 up is how I turn the in fixed operator plus into like a real function。

 Okay， that's just syntax。 But if I fold with plus in a base case of0。

 I gonna sum everything up in the list。 Do you believe me in terms of like analogy that how this looked up here when I had act is equal to x plus act。

 yeah。😊，それ。Yes， you can， because it's just a value。 R plus is just a value yeah。

But what I'm saying is that fold L up plus zero is essentially this code。I mean， this Python code。

 but it is exactly this N L code。 okay， Well， the sum function I defined earlier。 Okay。

 how you would normally define the sum function。 Do people believe me on that， Does that make sense。

系。Yes。The zero is the default value。 If I told you sum up everything in the list。

 you probably intuitively would be like， okay yeah。

 I'm going to start from zero and then change of every element， but you have to explicitly say that。

 It doesn't know where to start。 One of the strengths of actually doing this is that we could sum up everything but sum it to a base of like 5 or 10 or whatever。

 That's customizable， but it happens to be that zero is our right choice for this problem。Yeah。

 good question， yeah。Yeah， in the base case， you already returned Z。

 I claim to you actually you literally cannot make the function type check with the type signature up here unless you return Z because I have this thing which is not a beta。

 I have this thing which is not a beta， how do I get a beta I have to give it the initial accumulator。

 but also in intention it's because do you remember how we return the accumulator in like T length and T rev at the base case？

Same same principle， I can only return the accumulator once I'm done。

This is just the generalization of that tail recursive stuff I was telling you about， wow。

 there was a point to all of that， no way。All right。

E here's a trace actually so I can show it to you this is important If I want to use some by definition that is foldel given the add function。

 given 0， given one comma2 comma 3， the first thing I do based on my definition of foldel over here the first thing I do is I go to foldel。

 but I'm going to use that function on what the first element and the accumulator So I add one to0 right because I take the one off and I combine it。

😊，And then， I get one。And then the next thing I do is I take off the two， I add it to my accumulator。

That's three。 and I move on。 and then when I do， I take off the first element，3。

 I add it to my accumulator 6。And I go on， now I'm at nil， so I return Z， so I return6。

Does everyone see why sum returns the sum of the list？

This is just to show you like what it's doing with really。

 really all I'm doing is I I fix this accumulator and I keep taking things off the front of the list and combining it with it。

 I take another thing off， I take another thing off。

 and I put it into the accumulator using that same function I defined O there。

 that's your intuition for why this should work。😊，I'm going to really quickly do okay。

Foldar is going to be the same thing， but instead of being that I take the first thing off。

 the first thing I do is I take the last thing。😡，嗯。Nope， it's a linear work。When your work still。

 But the idea is like， if I have X1。Through XN。他对答XN。

I'm going to first thing I do is I take off from here and I give X n to Z。

 And then the next thing I do is I take off the next element and I do F of X n minus1 to that。Da。

 do do。 you see how this iterated is pretty much the opposite of what we just had yeah。Yes。

That is a trade off， but it doesn't need to be。 Let's implement a person。

 I have some remarks on that。 So let's define it where fold R still has that same type， Okay。

 but it doesn't en just a different order。F z nu。What do I do when I don't have any elements left。

 I return the accumulator， so I'm going to return Z。不是。I actually， I don't know why we call Z。

 It should have put been called a， whoops。And if I have X con axis here， so I'm going to do。

I have the first element of the list right here， but I want to do that last right the last thing I want to combine is X。

 So here's what I'm going to do。I'm going to combine X with something。

But I'm going do the rest of it first。 I'm going to do the rest， and then I combine with X。

 So what do I do in some respects， this is actually easier than fullar， a fullel， I think。

 But I'm actually in a very deep sense， it's easier than fullar。I combine the rest of the list。

 I sum the rest of the list and then I sum with the first element。

 right The difference between these two implementations is first element or you know do I combine with the first element first or the first element last。

 This is first element last FL， let's say。😊，Fold out because I do it here。

An eager evaluation means this goes to a value first。Is first element burst？Okay。

They very good about this。 I pretty much no time of someone to yes。我白 ok。嗯。

I claim to you we can implement the sum concateant plantin via how we did it here。

 There's something else I wanted to tell you， which is that for most applications fold R is the most natural fold。

 And I'm not going to be able to show this to you exactly， even though I told the T as I would。

 but here's my here's my claim， Allright。So， op cons。

So if I fold L using cons and the base case of nil。On some list L。

I claim to you this is the same thing as reversing the list。系。

I do not have time to work out with you why this is I probably am going to pick up this lecture from where I did it。

 but I'm yeah I highly recommend looking through these slides and figuring out what the hell these things do。

 I have plenty of examples。😊，はい。

![](img/d7b88ea1a19e87e9ab8512de9ea1315f_15.png)

ThanksThank you so much。Blue team1。Yeah。