# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P2：-02-2. Equivalence, Binding, and Scope _ - GPT中英字幕课程资源 - BV12VChY2EF4

Okay， we are pretty much your time， I think。一 ok。Let's do this thing allright welcome welcome welcome back to 150 lecture I see there's still quite a few of you so I didn't lose too many of you it seems but here we'll be talking about equivalence binding and scope I hope you had a good lab on Wednesday your tea is working really hard for that one I know that there's a lot of stuff covered in lab that we didn't get to on the lecture on Tuesday but today we'll be talking about it in more detail hopefully okay。

😡，Now I know that my first slide on Tuesday was drab and dreary and black and white that's because the colors of 150 are black and white but functional programming is not drab and dreary。

 it's colorful and cool hence we have these slides right here so let's get into it let's get hyp okay before I get into the actual lecture though there's some administrativea I have to tell you about which is namely。

😊，The house system， you might not be able to see， but you all picked names on on Wednesday。

 And I did say that the house with the best name would get the first 15 points。

 And I have to say that there is， I've chosen the winner。 Okay， so we have， so recap。

 we have the Red House， which is house blue team。We have the yellowel house。

 which is House Ylow headed by Nancy and Stephen， and then we have the Blue House， which is house。

 I love Brandon。😊，呃So。Well。See， I'm an instructor， I don't take bribes。

 so the winner today is going to be House Blue team。

It's also unclear whether or not I love Brandon was me or the TA so you know you only got half of the flattery anyways。

 so I'm going to fill this in。That's 15 that whoops， what？That's 15 points。

 but that's okay because the first 15 points isn't going to mean a whole bunch。

 we're going to have a quiz in the middle of lecture remember you're not counted for a grade but the winning house will get another like I don't know 15 points share let's say so be ready of that all right that will be coming okay。

😡，Congrats House Blue team， you genuinely made me laugh。



![](img/b4538c642549fcec4432fcb6f8b852a4_1.png)

Okay， cool， let's get into it。 So equivalence binding and scope。

 I told you a bunch of highleve ideas about how state is bad。

 how functional programming is different， but today I'm going to concretize some of those ideas because I didn't show you the goods I didn't show you how that was true So our lesson plan for today we're gonna be talking about types again。

 we're gonna be talking about more types of functions than the one I showed you in lecture Tuesday we're going be talking about binding and scope what is that it's my cursor。

We're gonna be talking about binding and scope， which is the main difference in terms of mutability or how how this idea of changing the world。

 I said on Tuesday， we'll talk about pattern matching。

 which is a nice way of how we can sort of manipulate values in SML。

 and then we'll talk about equience， which brings in math into this whole thing and ties a nice ribbon on it。

 Okay， that's good。 Yeah， this is good。 Okay， cool。 Allright。😊，Let's get started。

 So last time just to recap， we learned about expressions， values and types， we learned the mantra。

 Well typed expressions。 only well typed expressions are evaluated。 Remember。

 ill typed programs do not run。 Allright， memorize that。 say it to yourself at night when you sleep。

 and then expressions can do one of three things。 They evaluate to a value。

 They raise an exception or they loop forever。 Nothing else， Nothing more。😊。

And we also saw some typing rules， which are how SL knows how it knows the expression of the ty in an expression。

 Jesus。😊，And this is purely a recap， so don't feel the need to write this down if I'm going too fast and you want time to write stuff down。

 just be like， hey， wait a second and I will happily wait。But remember。

 these slides will be posted after。Okay， more types， I showed you some types on Tuesday。

 but I didn't show you all of them， so there's a few basic ones。

 but I'm going to tell you that right now I' me use the board for this lecture。😡，They are int。

 and some values of this include one。😡，150。And one，3， two， let's say we also have the type real。

 which is the type of real numbers， you know， like floating point numbers， so we have like 0。0，0。1。2。

0。We also have bo， which has precisely two values which are true and false， right？

This should not be unfamiliar， we have the type of strings。Which has such。

Strings as the empty string。Hello。And I don't know X。And then finally。

 we have the type of characters， char or car， however you want to say it， which is car。

 And then the way you phrase is kind of weird。 you have to put like this this hashtag quote a。

Hashtag quote B， this is not super critical to know about。

 but these are like some of the basic types we're working with in SL。

 okay and they are all listed there。But these are just what we call base types right they're like the default types。

 they're like the standard ones that are available。

 so we're going to see that they get actually a lot more interesting。😡，ok。Cool。

 we also have this notion of tuples。So tus。A tuple is a collection of values。

 If I want to store something， maybe I don't just want an int。 Maybe I don't just want a string。

 Maybe I want a string and an int。 Okay， so a valid tuple might be something like。One， comma 2。Okay。

 this is a tuple where the first component， I'll say， is one。 The second component is2。

 and the tuple has its own kind of type。 We say that this type is going to be called a tuple type。

 So it'll be the first thing is an int， right， So it'll be int。Star it。In cross in instar in。

 that's how we usually will say it。 You probably saw this in lab。

 but we have our own notion of tuple types or product types they might be said by some really fancy people and this itself is a tuple。

开。So we have some more examples up there。 A tuple can have any number of things in it。

 except for0 or1。 Okay， you have two things in a tu。 You can have three things in a tuple。

 so on and so forth。 but you can't have 0 or1。 And we call that prototype right。

 And when I'm talking about like code of a of a tuple， it evaluates from left to right。

 So if I had something like。One plus one。Two times 3。Using the notation we learned last lecture。

 I would first step the leftmost component that is not yet a value right， So I would say this steps2。

😡，Two， because I evaluate this guy。And then I would keep two times3 the same because I haven't taken a step on it。

And then that in turn， I now， well， okay。Death of Add， so I actually made this remark。

In a later slide， but when we're doing like a trace like this when we're stepping code usually on the right hand side here。

 we're going to want to cite how that step happened。

 how do we know that this thing set to that thing Well I know that this happened because one plus one by the definition of the add function of the plus function needs a step to2 so I do a little citation here and this's a nice way to format this in lawte but I'm going to go over that right now。

😡，And then once I have this thing， it's not yet a value so because there's this thing right that can still be evaluated。

 So what I'm going to do is I'm going to step it again。

Two will stay the same and then I'm going to get。6， right， is this now simplifiable。

 Can I still simplify this？What do you think， No， I'm hearing。 No， Yep， this is now a value， right。

 So I'm a， you know， this thing hook right arrows to。2 comma 6， right， it evaluates to value。

 and that value is2 comma 6。 So that's how we evaluate a tuple。 right， It has its own typing rules。

 It has its own evaluation rules。Any questions on this yes， so let's say the first entry had to link。

Let's say take three steps to evaluate It will do all those three steps before going on to the right Yep every single entry from left to right has to be a value before we can go to the next one。

 Yeah good question yeah。没 say喂。A we保。Oh， our real floats， I'm not going to get into that right now。

 ask on Piazza， it's a good question， but let's not get into it。😊。

There's a good answer to that coolol， and then the typing rule is that if I have， you know。

 E1 comma do dot EN。😊，Then if I know that each of these components has a certain type call it T 1。

 So E1 is of type T1。 and then all the way down to E N is a type T N。

 then this whole thing just has type E1 or sorry T 1。Star。TN。

 I know I'm using I'm making liberal use of these ellipses here。

 Does everyone understand what I mean， I just mean like you know， if you keep enumerating this。

 you can do this any number of times。Separ4 01。Okay， this is the typing rule for twos。

And then parentheses matter if I have， you know， one comma two comma 3。

 this is a different value than the tuple， one comma 2 comma 3。😡，Why。

 because this thing has two things in it。 The second thing just happens to be a tuple。

 This thing has three things in it。 Each thing is an int。The types are also different。

 so this one would have type。I'm running a space here， but this is going to be a type inch。

Star parentheses。Insstar in。Okay， for this thing。Its going to be a type。Int， star int。Star in。

So the parentheses here do matter， usually in math， we can just discard parentheses doesn't matter。

 right， but here it does。 All right， is this clear to everyone。😡，系。Yeah。When communicating as humans。

 yes， but the actual type， you know would actually be in star in star da da right we're talking about the actual objects as like communicating。

 like if you say that to me， I'll know what you mean。

 but practically like it is actually the iterated like star of inch 50 times。

Although you should never come up in practice， you have a two of 50 things。Okay。Alright。

 so we sped through that。 But those are some， those some things about tus。 Alright， next。

 we're gonna talk about some things about functions。 And then I think I'm going to。

Erase this while I talk。Okay， so functions we talked about functions I showed you one function。

 but there's a lot more of those in particular so we saw how star could be used to make types out of other types right if I have int and int there both types I can put a star between them and I'll get the type in star int so you know。

😡，Instor in。This thing kind of makes types。Out of other types， right？In a similar way。

 we're going to talk about this function type thing。 We put an arrow in the type。

 So I told you about this double function， which takes an int into doubles it。 right。

 So we said that double。Is of tight int？2 int。 I'll say， okay， int， arrow int， in，2 inch。

 These are valid ways of saying the same thing。 This thing also。Makes types， right， so we call it。

A tight constructor。Okay， and arrow is one of them。

 So we can have a more in the advanced notion of types when we have like nested product types。

 nested tu types like。Instar。Int star int or star bull， let's switch it up。

We can also have like a nested concept of a type where we have int arrow int。

 And we'll see later on in the semester that this idea goes structures even farther than what I'm telling you now okay。

That's a function type， and then we have， for instance， you know double of type inch arrow int。😡。

We also have like not， which is the SL function for logical negation on bulloles。

Which is of tableoo arrow bull。Okay， clear enough。So we also have this idea of lambmbda expressions。

 When I showed you the double function， we did it via a declaration。 We said a fun double。😊。

En corn inch。Cn in。Equals n plus n。This is a fun declaration。 But land expressions。

 these things are land expressions。 Let me show you what it is first。 Okay。

 this is what we call lamb expression。 So we use this F N key word。😊，Yes。Quion upload。

So the spiritual answer I'll give you here is what are floating points。

 I don't know what floating points are。 In this class。 We do not know what floating points are。

 We do not care about the intricacies of floating point arithmetic。 Flos are reels， reels， are reels。

 reels just add。Also， the integers are unbounded。 That's another thing that we assume in this class。

 There are no maximum integers in this class。But yeah， that's another good question。 Yeah， I， yeah。

 yeah， good question。 Cool。 So land expressions look like F N。 and then they take in an argument。

 So I could say N colon int。😊，And then I say this arrow。

 which is two characters equals and then greater than， and then I write n plus n。

This is what's known。 This is an expression。 I can bind this to to a variable in everything。

 It's an expression the same way that 2 and 3 are。 It's also a value。 What this is。

 is it's a function that takes in a number。And doubles it。 It is the double function。

 But I can't like put this on my line and then use it。 Okay， I need to。

 I need to first bind it to something。 This is an expression。

 But what I can do is I can surround it in Pers。And then put it next to two。Okay。

 so now this is the application of this landda expression to2。And I'll see that this。Evaluates to。

 it steps to。Sorry， if you can't see this4， it except the4。 Okay。

 land expression is a way of specifying a function on the fly real quick。

 but it's anonymous because it doesn't have a name。

 I can't give a name to this land expression because it Well doesn't have。 I can't give a name to it。

 but it doesn't have a name。It might not be clear why we have these things right now， but I。

 I promise you later on， it will come into play。 Okay， so we will have reasons to want these things。

 so that's the land expression。 They're anonymous， bla，lah， blah， bla，lah， blah。

Here's an important note for yeah， sorry go ahead。Sorry， you're right。 Okay， let me。

 let me revise my claim。 I'm gonna give a more detailed treatment of this later on。 But Im， yes。

 we'll save the next the immediately concluding step to later on when I talk about binding。 Yes。

 good question。😊，拿。All right， let's move on。 So functions are values。

 How many of you have heard this statement in before， raise your hands。All right。

 so all of you should be raising your hands by the end of the course。II've got a present for you。

 here you go。No， it just it was just on the table。 you can rip those up again if you want。

Functions are values。 What does that mean， It means that I can pass around this guy like any other value。

 Okay， I can use， I can use it as I wish。 that means that， for instance， if I took away this stuff。

 right， I took away the application， I took away the。The notation。I can say something like。Bel。

 double， sorry， I'm running that space here。Equals。So I can say instead of saying fun double。

 I can say Val double equals F N， you know， all that stuff。 Okay， it's an expression。

 Those two things are equivalent。 If I say one or the other， it doesn't matter to me。 Okay。

 it's just that the first one kind of looks nicer。 So we do kind of like that。

 but functions are values。 That means I can bind it to a variable。 It's not special。 or well。

 it is special。 but we'll see how that is later， yeah。😊，We can't actually write fund double equals。

You can We can you can and then I'll talk to you more about that in four weeks。

 but you absolutely can and that's going to lead us into a very elegant idea called Korean and we'll talk about that in four weeks and the second idea。

 second question is let's say we just like had the double function and we were like using it。

Are these two things like。Equivalent， like we can't tell them part one third， like you're fine。

So you you're also getting ahead of me again because I'm gonna be talking about extension equivalents later。

 They are equivalent。 You， if I had that thing and I had that thing， I could not。

 I could not tell the difference between them observationally from using things from in SML。

 They are completely indistinguishable。 They are extensionally equivalent。

 And I'll talk about that in like 30 minutes。 good question。 Good question。要喺出程。公。Yeah。

 it equals in greater than sine。 when you're doing a lamb expression。

 it'll have to be this instead of an equals and in a function declaration， it's just an equals。

 but it's just a syntax s， Yeah yeah。😊，Good point okay。You'all getting ahead of me， cool。Alright。

 land does。 there's one difference。 Okay， there's Pol。 we have a class mascot， by the way。

 We have three。 Their names are Polly。 All of them。 This is blue Polly。 Green polys Z O G。

 but she's not here or they're not here right now， polymorphism， polyly， the polymorphic parent。

 This will be hilarious in about two weeks。 cool， So suppose I wanted to declare this fact function via via a land expression。

 So how did I do how would I do fact right now。 So rather yeah， fact， like the factial function。

 Okay， the factial function is defined such that。😊。

I realize I'm getting running into a little bit sequencing here。

 but what I want to say is I want to say like factorial of zero， so if I want to write Briigham math。

Back to0。Equals one， right？And then fact of。It's a piecewise function。

 F of n is equal to n times fact of n -1。 Like these， this is how in math， I would specify it to you。

 If I wanted to write a lambda， that was fact。 Well， I'd write。 Okay， first lets case。

 let's say if n equals 0 than 1， Otherwise， what am I gonna put。How do I。

 How do I call myself again with an a landda。 You can't is the answer。 Lands are anonymous。

 They don't have names， so they are not recursive。So you cannot， okay。That's the。

 this the strength of anonymity。 Okay， if you don't have a name， no one can refer to you。

This also applies to。If you don't give you a kid a name， they can't get bullied。😡，You'll be like。

'll be like， hey you there。 I don't like your shirt。 Who me。 I don't know who you're talking about。

 Sam principle applies here。 Alright， Just close your eyes。 That's a little bit of a stretch。

Function evaluation。 So I already showed you some examples of functions evaluating。 right。

 I showed you like， if I use double on two or something， then I get， I get 4， right。

 But function evaluation the way it actually works。Application。

If I have an expression that looks like E1 applied to E2， so I have a space here。

 if I have E1 applied to E2， my rule is first I need to evaluate E1 to evaluate。😡。

Then I evaluate E2 to evaluate， so let me write this。Eval U12 Val。2。Evaluate E2 to a L。

And then three。Step into。E1's value， I'll say， and I'll expand on this in little in a second here。

 Okay， This is there again， there are rules。 There are concrete rules we obey when talking about what this programming language。

 What a programming language does。 Okay， so we evaluate E1 to value for us。

 Every example I've shown you so far， E one's already been a value like。

Like when I was applying double here or when I was applying this Lada， this Lada is already a。

 No work needed。 but remember that E1 needs to be evaluated first in actuality okay。Okay， so like。

 for instance， if I have this one， I， I'm not gonna to write all this down。

 but we would get a trace that looks like this。 So to step through the parts， I have my lambda here。

 which is already a value。 So I'm not really demonstrating that to you right now。 But I I have this。

 And similarly to what I showed you at the beginning of lecture。

 I stepped the first component of the tuple。 I cite the definition of plus。😊。

Then I step through the definition of multiply to get 12。

 and then I can step into the body of the function。😡。

And there's a little bit more magic that's happening here， which I'll talk about in a second。

Any questions so far？好。Yes， and you want to put justification。 It'll make your TAs happy。

 and it'll make you happy because you will get in trouble if you don't， okay。Alright。

 so stepping into a function， we call the body of a function， the thing that's inside here。

 So this is the body of this land expression。 That's just like vernacular that we use。

 But we step into the body once all the arguments that it's given are now values。

 So here the body and plus N。 But only once we we evaluate these things。

 like if I to here then we step into the body by substituting2 for n。

 and then we go here with respect to what the other person that ask me a question was saying。 Okay。

 so I step into the body and I produce binding。 The next natural question is what are binding。

 Now you kind of learned about this in La。 But let's go over it again。Any questions。个。对。

So I kind of rush through all this stuff。 I'm trying to get you use to the syntax。

 I'm trying to get you used to the machinery that you're using in SML。

 but the main conceptual thing you got to know about is binding in scope。

 The reason why it's different to do declarations in SMML versus in an imperative language。

 The reason why we don't have mutability is because of a choice made here。

So if I give you a variable declaration， I say B X colon int equals2。 what's it doing。

 You might say it assigns x to 2， you might say it declares x size2。 I will accept the latter。

 I will not accept to the former。Assignment is different。Bding is not assignment。

 These are two different things。 And the reason why is because of this idea I was saying earlier。

 where in an imperative program， I change the world to be something。

 But then someone might come underneath me， and then just with the world from underneath my feet and change on me。

 And now， now x is different。 Now X has been assigned。 bindinging that can never happen。

 when I bind a variable， that variable stays at that value forever and ever and ever and ever until the program femininateates Okay。

 or gets shadowed。 yeah， so binding is how we associate a variable a name to a value。

 and it is to a value， because when we evaluate a variable declaration。

 the first thing we do is we evaluate the right hand side to a value。

 or at least we try If I said Val x colon n equals 4 plus4。

 x is not bound to 4 plus4 x is bound to 8。Fair enough。

 and if it was looping forever or raising exception， we would never get the binding。

I won't demonstrate it for you okay。So binding is not assignment， why is that， let's see it。

Suppose I have this trace of code。XZ could得 you。I declare this magic function through。

 and it takes on y and then evaluates to x plus y， where it's referencing this X here。

And then I redelar x at4。😡，What is the value of fo given one？Rriddle me this。

 Who's got an answer for me， yeah。3， is it3。 No， it's not。 Yes， it is 3。 Yes， it is 3。

 but you're not supposed to say that because you already went to lab， You cheat。

 So you don't get to hide you。 No， not not could do anything about that。 If， if。

 if this has been the first first lecture， I could have been， Oh my God， it's actually 3。

 But you know， it's 3。 Yeah， it's3。 right， because that ws。😊。

That X is completely unrelated to this X， they're named the same， they happen to be named the same。

 it's a fluke， but。This guy， this foo， foo knows what's up。 Alright。

 The function foo knows exactly who it， who its main man is here， which is X。 Alright。

 that doesn't change。 Alright， just as someone else comes stroll in， so。Again， I I already said this。

 but you changed the world in imperative language。 But right now， you can't。

 right We cannot change that。 So X is unrelated here。 So let me， let me give you an analogy。 Alright。

 this is gonna be a hard one。 So stick with me here。 Alright。

 supposeuppose that your name is Brandon。 Alright，And you have a  nine to five job。Jez。

And your manager walks in and says。Brandon， your performance is has not been good lately。

 I got to say and he he walks out。 he walks out of the room。 Allright， and then。

 and then you're your mope and you're， you're all sad。

 And then suddenly another engineer named Brandandon walks in。You're still in trouble。

 You are still in。 It doesn't matter that someone unrelated walked in。 You， me are still in trouble。

 Okay， the names were the same， but it doesn't change the content。 my manager was talking about me。

 Brandon， not whoever named Brandon that happened to be in the room。😡。

So the point is that when I do this thing， when I have this X here。😡，This is X， I bind X2。

 and then this binding of ex2 exists forever。😡，And then I happen to buy something that happens to be named X。

 and it's to four。 That's fine。 It's unrelated。 It doesn't， It's not the same thing。

 Im not I'm not reaching into a box somewhere， right。😡，Labeled X， which has2 in it。

 That's not the picture you should have。 The picture is that2。Just exists。😡，Two exist， there's a box。

And then x happens the math to 2。 X happens to have like a cosmic affinity for two。

 And then another guy called X strolls in。 And now it's4。 But like everything。

 every time that I ever referred to this X。Was the same。 It remains the same it doesn't go away。

I went through this any questions on this yeah。Yeah。

 So if you could no longer reach like this this function that we declared。

 if you could no longer reach that and like that was the only time that this original X was ever。

 ever reached， then yeah， you could think of it as it just kind of fizzles out that's kind of what happens in the background。

 But generally， you shouldn't really have to think about whether or not it stays。

 but you can't reach it or if it just goes away entirely because to you to the user。

 it's the same right if I can't reach it， it might as well not exist So in our abstraction。

 we don't really care， That's an implementation detail。 But yeah， good question。啊，有。



![](img/b4538c642549fcec4432fcb6f8b852a4_3.png)

Well， let's find out。

![](img/b4538c642549fcec4432fcb6f8b852a4_5.png)

又不是。I didn't have the set up for lecture， sorry。哦。Fun， double and int。Eals n plus x。

Unbound variable or constructor。 So to reference a variable， it can't be what else I'll call free。

 It can't be a free variable。 It has to exist。 We have to be in the scope of that variable first。

 It has to already have a binding in the environment， which is what I'm going to talk about next。

Yeah。Yes， you can。 That's a construct let end。 I wasn't planning on getting it to it this lecture。

 I was planning on introducing it in Tuesday's lecture。 But， yes， you can。

 And I'll hold up on that because I love stuff to talk about good。 No， good question。 yeah。

If I define x twice in a row。 So if I did something like v x column int equals 2 and the v x column nt equals 4。

 right， these are unrelated， as I said。 But I never， I never referenced this X。

 So kind of like kind of like what he was asking， like， if I， if I never， ever use this guy。

 like it might as well not exist。 So here， because I never use this X， Like。

 it doesn't really matter to you if you can't reach it， if I can never reference this X。

 any time I use X。It's going to be the most recent X。

 because that's the one that was most recently declared。Does that answer your question。

Any other questions？Yeah， it's good to have questions。 Thank you。m cool。 Okay， I'm sorry。

 I need to wait to the slide。

![](img/b4538c642549fcec4432fcb6f8b852a4_7.png)

All right， let's move on okay so we call the environment in the program the collection of all active bindings when when I produce a binding or when I you know do a binding。

 the environment changes every single thing that I know to exist every variable along with the value that it's mapped to。

Is within the environment。 so for instance， if I had。Yeah， okay， sorry。 So in particular。

 when I say like Val。Xcon inch。Equals 2。I produce， I'll say， produces a environment。

 and the notation will look like this， we put square brackets。

And we put the variable slash or we put the value， slash the variable that it was bound to。

 So in this case， I bound2 to x。 So I have two slash X here。 Okay， this is notation。 Again。

 this isn't S ML code。 But it's， it's my way of denoting what the program currently looks like。

 So once I evaluate this。I get an environment that looks like that。Okay。

 but what if I were to immediately do， like I showed you earlier， Valal X con int？Equals4。Well。

 now I'm going to get。I'm going to displace the binding。 It's gonna go away。

 So I'm going to say that。4our/lash x。And something else interesting happens when we get functions in the mix。

 But let's think about this case first。 Okay， if I immediately find it。

 I shadow it is what is called I shadow it。 This vining is no longer visible。

 It's no longer in my environment because I kicked it out and I replaced it with four。

 We like four better。 It's double it。 So it' no we are no longer in that variable scope once we shadow it。

 and this is our， this is our notation。 Okay so for instance。

 if5 was bound to x and true was bound to y， you'd see that one instead。Any questions？Yeah。

So the thing is if I were to like suppose I did this。Ful y coinent。Equals x。If as you're proposing。

 our environment became this。When I like use this X， when I， when I like try to reference that X。

 like， well， there's two x's in my environment， how do I make that choice。

 And it's I suppose you could conceive of， of a programming language where like， you put both in。

 you flip a coin and you pick one randomly。 But that's probably not a good idea， right？

 So what we do is we only ever have one binding for one name at a time， right。

 because now we definitely know that this X references the most recent binding of X。

Which simplifies our conceptual model a bit。要最块是要。对过就行。So you're saying this。F Y corn inch。

Equs x plus x。And then this will， as you said， produce a binding of4 to y， right。

 so we still have the old binding of x。4our dash Y， right？

And you also said that we have like another， we shadow X here again。And the question is。

 what should the environment that we produce at this next line be， The。

 the question doesn't really change， right， Like， if I were to still say， oh。

 I want two bindings of X。 Like I， I'm so the idea is I still should kick out the old binding because then if I do that。

 if I have two slash X，4 slash X。4/lash why。I still don't know which one of these to reference。

 right， It's not so much like I would think about it instead， like， like。

 when I reference a variable at any given time， I just look for the most recent binding of it。

 So at this point， at this program point。When I'm after all of these。

 the most recent binding is2 x is4。 I don't know about this guy。

 I can't possibly see that guy because I'm intercepted by this declaration。 So the actual picture is。

😡，I sorry。This one。Forest/lash X is the most recent binding。Yeah。I guess it ends up being captured。

 Okay， I didn't realize that but。just like to acknowledge to I can see other way， to be honest。

 this isn't really gonna come up。 but it's more of making sure that you get it right that like we're referencing this guy instead of that guy。

 So as long as if if you're aware， basically you're just adding information like two slash X with the thing through it is equivalent to this in terms of how I use it。

 I still can't see this two slash X。 That's what I'm concerned about。

 I want you to know that you cannot see this two slash X from any future bindings here。

That makes sense。afternoon。How dot shift everything oh sorry yes， so this exists like here。

 this exists like here and this exists like here。 Yeah， sorry the alignment is not quite correct。

 You're right about that yep。Yeah。Yeah， sos let's let's get to the function case。

 I was holding off on the function case， but I think it's time we move on。 Good question。

 So this looks like straight line code。 It's basically what I just showed you， but nothing。

 nothing changed about like this。 This is no different than like。

 if I did it in an imperative program。😊，The， the key thing to remember here is that binding is different than assignment only once you introduce functions。

 Okay， here， this straight line code， you could write it in like C or Python。

 and you would get equivalent results。 X will be for here， Y would be for here， so on and so forth。

 right， But the difference is when we get into a case of a having a a function bound。 So let's say。

I don't know the exact example it's going to be， but that's okay。

 Suppose I bind a function right here。 It's going to be funfo。Our friend， Fun Fu and inch。

Called inch。Equals I don't know， n plus x。Okay。Remember remember I said that we bind things to values。

 bind things to values before we evaluate things to values。Before we bind them to variables， right。

 So if I'm， if I'm doing this declaration， I want to evaluate this function to a value and then bind it。

 It's kind of like v2 equals land expression that goes to this， right， But that's already a value。

 My point is that when， when we're trying to think about how to denote the environment here。

 So this is here2 slash x。😊，What do we write？As the thing that we have bound to fo。Right。

 I want to like denote some value。 So I introduce you lambda expressions， right， In reality。

 it would be insufficient to say lambmbda expression， because suppose I put here。

 suppose I put here F N N colon int。Goes to n plus x。I said this is the value bound to foo。

But this is actually not quite correct because what is this x？What is the X that I have here。

 It's two， right， so I can't it's not quite right for me to write X here in particular。

 when we bind something to food， when we bind a function to to a variable。

 we're binding something called a closure。En closure is two things。 It is one。A lamb expression。

And then two。It's an environment。It's a pair of two things。 When I bind a function， I remember the。

Environment at the time that I bound it。 and I store it inside of foo。 So when I bind this thing。

 it's not just this。 Okay， let's say I'm going to put in parentheses。it's one thing， this。

 and the two thing it's。Two slash x。All of this。Is my closure bound to fo。

 I'm including the environment。 It's not just the value。 What the essential effect of that is。

 is if I go here。I do v x sorry， if this is messy。If I shadow X at this point， the environment here。

😡，It's going to be four slash x。And then the flu thing， right？

Is that clear It's gonna be still be still the binding the fo， but we also have four s X。 Sorry。

 this is really hard to see。 But that doesn't change what's in here。

 That doesn't change this yellow thing。 futureture binding to X change this top level environment。

 but it doesn't change what's in the closure。 I think I have a better picture for you on a different slide。

 So another way to remember this is functionss are not just values。 Function are elephants。

 They remember everything。A function when I bind it remembers the exact environment that it was in when it was declared。

 it remembers it forever， so that function can never be changed in the future right because it remembers the fact that it had this2 for x。

😡，Environment， when it was originally declared。Does that make sense to everyone。Yeah。Exactly。

 exactly this another way of thinking about it is。I'm running on space on the sport here。

 but basically like suppose I were to evaluate likeF of two。

What happens when I do fool of two is I want to step into the body of the function。

 and I want to consult。 I want to say it's n plus X， right， That's what I want to say。 But what is x。

 It doesn't consult this environment where x is4， as in the one with the shadowed variable。

 It consults this one， It own private environment， The state of the world， the state of the world。

 at the time where it was declared。 I can't change that on the function。

 The function will always evaluate knowing what X was。

 This is equivalent to saying that it just like stores all bindings inside of itself， yeah。😊。

Everything， but the unrelated bindings， if it doesn't use them， you don't really have to think about。

 It's not really important。 Again， it's kind of a distinction of if we don't use it versus if it's not there。

 it doesn't really matter to me。 But yeah， I saw another hand。Yeah。

Yes so let me try to write this out with more space so you're correct that when I declare the function through I have to have x defined right I can't use the X if it's not there but later on。

There are kind of two different concepts of it， so I do like funfo。En call and。Equals x plus n。

 right？And I already had here like a binding of 2 to x， I'm not going to rewrite it。So here。

My environment after the step is going to be 2 for x。And then it's going to be。FN Ncor inch。

Goes to X plus N。Along with。The environment two slash X。This whole thing。This whole thing。

This is what I bind to food。Right， so it's the two things。 I have two bound to X。

 and I have this big yellow monstrosity bound to fo。 right， So then later on， when I do vow。

X to inch。Equals4。I get。Or slash x。Again， I get yellow monstrosity。当 feel。

But the point is that these two things are the same thing。

 so there's a two for x in here that is still there。 it's not at the top level。

 I can't see it from future bindings if I did if I referenced x， I would still get this guy。

 but function fo knows about the original X that was bound up here。😡。

Does that make sense for everyone？Yeah。it's if you eagerly substitute in everything。

 so you're saying， why don't we just forget about this idea？And like just write this， right？一刻 for。

Different ways of thinking about the same thing。 If you do that， that's。

 that is exactly what's gonna evaluate to the same thing。 Yeah。

 if I remember my bindings explicitly and I look them up in like a little table I have to myself。

 Or if it's like already there， Like， we're gonna see the same behavior。 Good question。嗯。

I feel like I'm owed two high juice right now。I'm sorry。I not the best at throwing things。 Alright。

 so functions are elephants They remember everything。 I know this is confusing。 I gotta move on。

 Okay， but I hope everyone's got the idea of why this is important because I can never change the behavior of foo。

 The implication here。 I also had a little picture for you。

 but doesn't really do much more than what I put When I bind a foo here。 Oh， actually。

 it's exactly the same。 I use2 and4 and everything。 Great。😊，When I bind this closure。

 if I do anything after this foo function， it never changes foo's behavior cannot change based on binding that happen after foo。

 That means that I can never change the world on myself。 That means that code is modular。

 If I'm looking at a piece of code， everything that happens after it in a functional program is not important to me because my function will always behave the same。

 It lives in a nice little world where it remembers everything that happened up to its point。

 And what happens after whatever， So the point is that because of im mututability because of the fact that I can't change this environment。

 The effect is that。😡，Functions cannot change the behavior based on future binding。 Okay。

 that's the goal here。 That's what I want you to get at of this。 Okay。

 detect technicalable details will work out later， okay。扣。Quz time， all right， get into your houses。

Everyone get up and get your houses， this is where we're taking a quiz together for five minutes。

 blue team here， yellow there， and then red or。😡，I love Brandon， go to the back。Blue team。

 as a house blue team， your color is red， okay， you Jesus， a bunch of jokes？Let's go， let's go。

 let's go， let's go， come on。So I love Brandon in the back， red team here， yellow here。

 yellow on my right， I love Brandon in the back， red team on my left。A blue team， Jesus。ます。

Yellow on my right， yellow here。Okay， is everyone about John， I'm going to call it here， all right。

 submit if you haven't already。😡，Also， you， there's a timer on quiz。 I forgot。

 So you should be unable to submit pretty soon。 Okay， T As。TAAs。

 could you please create that while for the rest of the lecture， thanks？All right。

 they'll do whatever I say， it's fine okay， back to lecture， settling。

 settletling laptops away or take notes， whatever。😊，Cool， okay， hopefully that was fine。

 It's we're gonna be doing this for every lecture from now on。 I realized it was a little buggy。

 I'm sorry about that。 I may or may not have made it at 2 AM last night。 but anyways，quiz time。

 that's over。 Let's move on。😊，I'm not going to finish the rest of the lecture in the next 30 minutes。

 unfortunately， but it's fine because I took some material from lecture 3 and I moved it up to this lecture。

 so I'll see you Tuesday and I'll tell you the rest of the stuff I plan to talk about。

 let's see what we can make it through。😡，But yeah， so pattern matching。

We already saw how we can write variable declarations using that syntax right。

 we say that val x is equal to， you know in this case one comma 2。

 but if I bind a tuple to a variable like that， then how do I get out the values in it I said that x is equal to1 comma 2 but now that I have x which is of type insertent。

 how do I get out the components I can't it's x it's a tuple right I can't do for instance。

 let me show you actually。😡。

![](img/b4538c642549fcec4432fcb6f8b852a4_9.png)

I can't do if I do this。If I do x plus 2。I'm going to get a type error， why。

 why do I get a type error？😡，What's the problem here？Yeah。Type specifically like I mean's in， yeah。

's。That was fine， that was fine all right， yes， there's a type error， I shouldn't have done that so。



![](img/b4538c642549fcec4432fcb6f8b852a4_11.png)

To get the values back out， I'm going to use something called a pattern in the same way that we use tus to put things into tus。

 We use twople patterns to take things back out of tus， okay so。😡。

We say v x comma y colonant int or int is equal to 1 comma 2。😡。



![](img/b4538c642549fcec4432fcb6f8b852a4_13.png)

And if I show you this on the SML and J Reple。We get two bindings， right， X pattern matches to one。

 Y pattern matches to 2。 Okay， so I， I get them back out。 and I now I can use them。

 Now I can say something like X plus 2， you know， okay。



![](img/b4538c642549fcec4432fcb6f8b852a4_15.png)

But this is just one application of patterns。 And this， you know， this produces that environment。

 as we said earlier， right，1 is bound to X。2 is bound to y。可以呃，原告始。位置。So if I ran this。

 I would have x the tuple bound to X。 if I ran this， I would now shadow that tuple with this。

 So this would still be the output environment。 Yeah， good question。Yeah。So what I mean by that。

 I guess is like if I have this x equal to1 comea two， right？



![](img/b4538c642549fcec4432fcb6f8b852a4_17.png)

Like if I say that。J oops， well x equals1 comma 2。 I have this x， and it's just one comma 2。

 What I mean by unpacking is I want to use the one in the two inside of the tuple， but I can't right。

 How do I access the one。 Suppose I put in some secret into the tuple。 I want to get it out。

 How do I do that。So when I say unpacking， I mean that I'm using bad names。Here now。

 x remains the tuple。And now， why。Is the first component。 And Z is the second component。

 So that's what I mean by that。 Does that answer your question。Yes， but that's not super important。

 I'll let you play around with that on your own。 But yes， you can do that。 Yeah， good question， cool。



![](img/b4538c642549fcec4432fcb6f8b852a4_19.png)

Okay， but yeah， we can get this environment out。 and I kind of gotta。Go for the rest of the lecture。

What a， what is a pattern， A pattern is a way of describing the form of a value。

 Like values can take forms like 2 or3 or one comma 2 or true or anything in between， right。

 Those are all things that couldn can be values。 But suppose that we want to like break down that value。

 We want to be able to match to it， so。Patterns should be able to describe them。

 So we use x comma Y to deconstruct the value 1 comma 2， Y。

 because if I put them up next to each other。I have。X comma Y is my pattern。

 I have1 comma 2 is my value。These things match， right， I see that this thing。

 these two things are in the same place， so I match this to that。And I produce a binding。

 And then I match y to 2。 I produce a binding。 So that that's what I mean when I say pattern match。

 we take a value and we query it against the pattern。 And optionally， we might get bindings out。

 Okay， and I'll show you the mechanism by which we do this in a。😊，So。

But the right hand side of this file binding doesn't need to be a value。😡。

If I said val x equals 2 plus 2。Collient。Right， this could be， this could be an arbitrary expression。

 So it doesn't matter what I put here。 so long as the types match， for instance， suppose。

Suppose I had Bell。X comm Y。Cn insert。Suppose I have this equals。wo。Does anyone see a problem here？

Yeah。The right hand side is just It doesn't type check right Not only did I put this type annotation here that says it should have been something else。

 but even if we know this pattern expects a tuple。 that's not a tuple So yeah we would get a type error here。

 that's a mistake。 yeah I have these things up here remind you these every and structure when I have my type here。

 thist and this pattern that's correlated with the pattern itself。 So if I have aple pattern。

 I expect a tuple I expect a tuple value here。 So what I might say also pattern I expect something of type T1 star t2 some t2 could be could be star could be string star doesn't matter to me。

 but the pattern expects that we should have something of type there I should annotated this anyways。

 But yeah So it needs to be a tuple that has two things in it。 otherwise。

 if I was able to do it I try to unpack2 I might try to extract。This and this out of 2。

 And that doesn't make sense。 right， That's a， an error。

 So the type system prevents us from doing that because otherwise， we'd have to say runtime error。

 I wasn't able to do it， which is a mistake。 We should try to avoid doing that。Yeah。还有。Yeah。

 I'm making a mistake here by not type entertainingnotating for this portion of the course。

 assume that you must type annotate everything。 We're gonna see later on that we can omit them。

 but please， please， please use type annotations right now。 It is better for writing more clear code。

 and it'll help you think about the types。But later on， we will see that we can omit them。Okay。

So we can use patterns for things other than tus， that's why I erase this big board。

 I forgot about that， right。If I have patterns， I have a bunch of different kinds of patterns。😡。

Actually， you know what， Im， I'm not gonna write it。 It's up here。 So I have variables like X Y Z。

 We saw this when we said v x equals 2 or colon into equals 2， right， We bind it to the variable X。

 We also have the wild card pattern。 Let me show this to in the， in the reple， so。



![](img/b4538c642549fcec4432fcb6f8b852a4_21.png)

呃。So if I did something like v x conent equals 2， I get a binding to x of 2。

 but what if I did v underscore conantt equals 4。Nothing got printed out。

 Can anyone hazard a guess as to why？Nothing could printed， but I didn't get an error。 I didn't get。

Something malform。 I still am in the reple。喂。I don't know but我。Unfortunately。

 that' that's what Python does。 This would work in Python。 but no。

 So what's happening here is that the wild card pattern。Doesn't produce a binding。

 It just matches to anything。 It matches， but it doesn't produce a binding。

 Mating and binding are two different things。 So if I said v x colon n equals  to， you know。

 I produce this binding， But if I say Val underscore。Here now。

I don't expect a binding back because I didn't give it a name。😡，Wild card matches anything。

 but it doesn't。 It's nameless， essentially， okay， yeah。We'll see what like more。 Okay， actually。

 let me show you specific example。 Suppose I wantan to get the first component out of a twople。

 but not the second。 I might write something like X come。 I keep reusing X。

 I hope you realize this is different each time。 I don't really care about the name。

And I produced just the binding to one。 I didn't want the binding to two。

 Otherwise I might have to come up with like some name。 And that would like clutter my code。

 It would clutter my thinking。 It would be unimportant。

 So judicious use of wild card is important for writing clean functional code， clean SML code， yeah。

是不啥呀。Use to work， which is。For getting rid of parts of patterns that you don't care about。

 essentially。We'll see more examples later， but yeah good question。

We also have constants so we can do something like oops。you'll get a warning here。

 but this succeeded Basically a pattern， which is this guy can be a constant like two。

 This means I'm， I'm expecting two， and I'm trying to bind it。 and I'm not going to produce， rather。

 I'm trying to match it。 but I won't produce a binding。 But if I did this。Well。

 two doesn't match to three， so this should be an issue， right。And in fact。

 we're going to get an exceptionception。 Okay， I can't really stop you from doing this because anything could be on the right hand side here。

 But the what's happening here is that we're trying to match to3 with two。That doesn't work。

 So we get an exception。 Okay， that's what constant patterns too。

 It's generally not a good idea to use them in， in a valve binding like this。

 We'll see other cases where we can use them。

![](img/b4538c642549fcec4432fcb6f8b852a4_23.png)

And then two poles， I already showed you this。 Okay， I kind of need to go move along。

So I already you pretty inferred this， but the form of a vbin is I say vow， I give you a pattern。

 I colon， I give you a type and then I give you an expression right that why here I was able to write that's why I was able to write things like you know vow2 where I could say vow x comm y or I could say vow X where I could say vow_ right because here。

I's just any pattern。Right， any pattern goes there。And then it's equal to some expression。

 And R showed you that if you try to do this， it's not going to type check， right。

 becauseuse the right hand side here。Is a tuple， and the left hand side is a constant of int type。

 right，'s， it's an integer。 It's expecting an integer， which a tuple is not。

 So this will not type check。 So it will never run， right， because ill typed programs do not run。

But if I did it slightly differently， like I just showed you， if I did v 2 equals 1。

 this runs but produces an exception。Okay。There's a distinction here， right， One of them never runs。

 One of them does run， but gives an error， cool。Does this make sense to everyone。嗯。

I'll give you like a second to write， I guess。But I got to move on now。

So I already showed you double。 but suppose I wanted to do something more complicated。

 I already use this， but let's talk about it。 We have these if expressions。 The syntax is this。

 I have fun is even。 And then if and mod 2， where mod is the modular operator is equal to 0。

 then I return true。Else， I return false。 And if expression is an expression。

 I can bind it to a variable。 I can bind it in a function declaration。

 It is an expression that can be added。 It can be subtracted。 It can be used like anything else。

Except that I've shown you something really， really concerning。Do not do this。

 Do not do what I've shown you here。 Does anyone have an idea as to why the idea is， actually。

 I don't know if you went over this in lab。😡，DonDon't do this。Yeah。This is because I。

Maybe add mod2 equals0 like parentheses is like quarter。Yeah， well， it does evaluate first。

 that's true。Yeah。It's already a bull。 I'm putting a bull into a test on that boolean。

 And I'm if it's true， I'm returning true， If it's false， I'm returning false， why am I doing this。😡。

So here's a brief interject。 I got got， I got a out about this。 So we have the expression。

 Look like this。 if X P1， then X P2 X else X P 3， It has certain rules I'm gonna be a little fast about this。

 Sorry I'm a little behind。 But these two branches here need to be of the same type。 why。

 because I might get type on safety if I can condition on something and produce things of two different types。

 I cannot tell you what type I get out because for instance。

 if I have is if Sasquat is real than two L string through。 depending on if sasquatch is real。

 I might get to the integer， I also might get through the string。 That's bad right。

 So we're gonnatrain that these two things need to be of the same type。😊，嗯。

But that's the warning anyways。The reason why this works。

 what what this if expression really does is it evaluates E1 to a boolean。 Then if it's true。

 it goes to E 2， Otherwise， if E1 is false， it evaluates the false， then we go to E 3。

 That's what it does。So' let's try is even two。 Okay， let' let's trace it。And this is a lot。

 But by the definition of is even 2， I'm going to get if n mod 2。 So2。

2 is bound for n2 mod2 equals 0， then true is false。 I use the definition of is even to get there。

 Then if 0 equals 0， because2 mod 2 evaluates the 0。So I use the death of Mo。

 and then 0 equals 0 is true。 So I step to this。 I get true。 So I get if true， then true will false。

That's a little redundant， isn't it。It's really redundant。 Sorry。

 pass me thinks it's really redundant。 So I have to say that now。 It's really redundant。

 Don't do this。 Similarlyly， if I put in is even a3， we get this whole thing， but it'd be if false。

 which is similarly redundant。 So never write。 if even true else false， Actually。

 the the greater will complain at you if you do。 But I I feel like giving this。

 giving this information now。 So don't do that。 it's a style error。 It's also just not good code。

 Like you should be aware that these things are equivalent because bulls are bulls。

 And if is just an expression， okay。So you can， you can write like if， if， you know， something， then。

E2 and E3 or E2 and E3 are not true and false。But don't do this。O呃是O嗯。

We can write the factorial function I told you about earlier using a fund declaration。

 So it's facts that takes in an input。If the input is 0， then it returns one， Otherwise。

 if itll return n times fact of n -1， This is clearly the factorial function。 right。

 This makes sense。 And it looks a lot like the mathematical fact I wrote for you earlier today。

 which is a nice thing about S andl functions， is that they just look like equations。

 They look like equations。 Okay， and that's a strength。

But I'm going to show you a different way to write this。

 which is that we can use these function clauses。 So using function clauses。

 we're going to be using the patterns I just taught you about with patterns， we can say。😊。

If I get an input first， I'm going to step linearly through the clauses。 Suppose I have fact of 3。

 Okay， I take the three and I go to the first clause。 Does3 match to 0。I see。

 I see shakes of the head， right， It doesn't。 So I， I go to the next clause。

 Does3 match to any variable N， like a a binding to variable。 And， yes， it does。

 because this pattern matches to anything。 So if I fact of 3， I would。Go into this body。

With the binding of 3 to n。 So factor of 3。It alls to three times that。3 minus-1， right？

Because it didn't match the first case。And if you iterate this process enough。

 I'm not gonna do the trace for you now， but you can imagine like this is gonna be2。

 We're gonna keep going。 And eventually it'll match the0。

 right So that's the reason why So if we write this way， we don't need to use the if expression。

 pattern matching is more powerful than if expressions。 If I use pattern matching。

 I can match on precisely the value withouting needing to get this equality thing involved。

It might not be obvious to you why this is different with just a simple example。

 but with like things like tus with things like other types of things that we'll see later this semester。

 you're going to find that pattern matching is really。

 really powerful for saying exactly what you mean to do。 It makes for clean control flow。

 So we prefer to write this function this way。Over this way。The second way over the first。はい。

And we call those function clauses。 That's the general syntax。

 I'm going to skip over this because it's not super important， but that's what happens。

And then I'll say one last thing， which is that。These outputs in each clause have to be of the same type for the same reason as the if thing I told you earlier。

 if they were different types， we could possibly return different types in different branches。

 which is a big no， no， right， So they need to be of the same type。

 Okay function clauses need to return the same thing。 All of these outputs are of type end。Okay。

 I'm going speed along here。 I'm going to talk about evaluation for just a little bit because I don't have a lot of time。

O。But before does anyone have any questions they really need answered before we talk about quick ones？

Yeah， I， I made this lecture by like consolidating some content from lecture 3 and pulling it in。

 And I I already knew what being in this lecture。 I wasn't gonna get through all of it。 that's fine。

Okay。So with binding and scope， we talked about how variable binding is different than assignment。

 right， When functions get involved， I can never change my mind。

 Bevior of my functions is always the same。 That's the difference， right。

 which means that I can never have a function， like increment。Where if I call increment。

 it returns 0，1， and then 2 and then 3， because of binding， I always get pure functions。

 Remember the term pure I told you last lecture。 It means a mathematical function。

 same outputs given， same inputs。And this is really nice because it lets us reason equationally。

 So we already stress to you that binding gives you modular code， right。

 I only have to think about what happened before a function to reason about what the function does。😊。

I already told you this， but binding preserves function equivalents。

 basically as a direct result of binding， right， if I have FF 2。

I can always say that F of 2 will return me the same thing because it cannot change its behavior based on a binding that happens after the function F was declared。

 So F of 2 is F of 2 is F of 2 is F of 2 always。Okay。So I promised you that we'd think about math。

 I promise you some math， I'm sorry if you don't like that。

 but this is a class about functional programming and there's a lot of math involved here。😡。

We're going to have a new definition here and this is an important one。

 this is an important thing I tell you now。This is a definition of extensional equivalentence。

 and two expressions are extensionly equivalent。 If they either evaluate to the same value。

 they both loop forever or they both raise the same kind of exception。

 You might have gotten this in lab。 So we write this shorthand E1， and we do E1。

Equals with this littleilda over it， E2。When they're extensionally equivalent。 So to put in。

 in mathematical notation， what I was saying earlier， if I have F of2。This is always true。

 F of 2 will always be extensionly equivalent to F of 2， because I cannot mutate the world。

 I cannot change the functionss behavior。 So in any context， it doesn't。

 So instead of needing to think about， but what's increment of。What is this， You have to say， oh。

 well， if you called it two times an increment is3 or if I called it3， No， there's no if。

F of2 is always just rather you， let me concretize back of two。Is always too。

 The factorial function I showed you will always return the same input。

 And that means that in any context， in any time I'm thinking about what factorial does。

 I know precisely what it does。 It always returns this。Okay， for the factorial function。Yes。

Does this be that life？All like infinite loops are extensionally equivalent。

Of expressions at the same type， extension equivalentence is only on expressions when they have the same type。

 But if I have two loops that are of type int， Yes， they are extensionly equivalent。

 It doesn't matter how they loop if they loop forever they are。

We don't necessarily need to be able to prove that， but if they loop， they are。Yeah。No。

 we only are talking about extension equivalents on like well formed SNL programs。

 an ill type program is not well formed， it's not well typed。

 generally we justconsider all ill typed expressions or programs。So yeah， for instance。

2 plus 2 is essentiallyly equivalent to four， but it' also essentiallyly equivalent to1 plus3 because they all end up at four。

So we already talked Oh， sorry， go ahead。Yes。😊，In the queue size map。

The fact that plus works on both realels and ins is like， frankly， a mistake in the language。

 Don't think about it。 It's， it's not worth your time。

 It's it's literally the only one of the only special cases of that in the entire language。

 Don't think about it。 The real version of plus is not equivalent to the in version of plus。

But in general， when we talk about Plus， we'll be dealing with just the integer edition。 Okay。

 it's really a shame。 I have to disma that。It's， it's not nice。 Anyway， Yeah， like a good question。

 So we saw something which looks already like this， right。

 we said that like one plus3 is essentially equivalent to24。We saw something like this already。

 right， We saw reduction。 So one plus one reduces the two。 we learned， right， It simplifies the two。

 but one plus one is also extensionly equivalent to 2。But what's the give。

 why do I have two of these things， don't they look the same？They're not the same。So I'll。

 I'll say this to you。 And I have a slide talking about this。

 but I don't really feel like going fully into it。 Red is stronger than equivalentence。 What I mean。

 when I say that is that if I have that。E1。Reduces E2。原来。

Then it's always the case that E1 is essentially equivalent to E2。 This means that this has like。

 in a sense， more information than this saying this does not imply this， right， because。

I'm really out of space here ge。Saying essential equivalence does not imply。

Reduction because I also know things like1 plus3 is essentially equivalent to 2 plus2。

 but it is not the case that1 plus3 reduces to 2 plus2。

RightThat would be an absurd statement to make。 We do not simplify  one plus 3 to2 plus 2。

 but the extensional behavior， what both of these expressions eventually do is the same。

 So we use exist equivalents， but not reduction in this case。 Reduction is too strong。

But if I knew that these two things reduce to each other， if E1 reduces the E2。

 then I would also necessarily have that E1 and E2 are equivalent。Okay。

 that's the meaning of the next slide that I'm gonna show you。 But Im doesn't really matter。

I rendered you a nice graph here。 But basically the idea is that there are arrows going from this to that。

 this to that， this to that， this to that， so on and so forth。 The arrows show reduction。

 if I have one plus parentheses，1 plus2， that reduces to one plus 3， and one plus3 reduces to 4。

 Similarlyly， two plus2 reduces to 4， so on and so forth。 right All of these are simple arithmetic。

 But the idea is that reduction is one way， reduction is like a road and all roads go to Rome。

 or in this case，4， right， we're going to end up in the same place， no matter what。

 So if I pick any two expressions， any two nodes on this graph， they are extension equivalent。

 They all end up at 4。 But it is only the case that。

One plus parentheses1 plus2 evaluates reduces to 1 plus3。This is not reduce to that。

 this is not reduced to that。Does that make sense to everyone。

I'm not gonna write down like explicitly what I'm saying。 But the idea is that know。

 we're we're going to the same place。 And sometimes we end up that exception here。 or sometimes we。

 the graph is infinitely long。 And that that means we're in an infinite loop。 Okay。

 you can imagine that in your brain。 But for values。

 for expressions that are valuable right that evaluate to values。 eventually， it looks like this。

Reduction is one way。Yes。Rustion is different than。Yes， yes。 there a notation that looks similar。

 but you know， for this one。For reduction， you type。Dash steps two， right？

But implication need to use like dash implies。 and they're like。

I think they're pretty similar looking， but I think they're actually slightly different。

 but like in terms of the notation I'm using， they're actually different。Yeah， yeah， good question。

 Cool。 I have very little time left， but。This is the important thing to talk about here。😡。

Referential transparency means if I have E1 equivalent to E2。Anywhere that E1 appears in a program。

 I can replace it with E2。 I have a mathematical proof that in SM L。

 you will always have the the entire program behave the same。 You can swap equals for equals。

 How many times in a math class have you done that， You know， you you。

 you knew that like there was some equivalents like say like。1 plus2 plus dot dot plus n。

There's a famous equivalence for this one， right， it's what n times n plus 1 over two。Maybe -1。

 I don't know。 We know these two things are equivalent so we can swap them for each other no matter where we see them。

 is it wrong。right， and then prepare this。 they're equivalent。

 So I can swap them for each other whenever I see them。 Same thing with my code。

 I should be able to think about my code， like I think about a mathematical you know。

 expression that I'm trying to prove something about because I want to prove stuff about my code。

 So I can replace two plus2。 if I see it in S ML program I can just go and I can replace it textually with one plus3 or anything equivalent to one plus3 anywhere I want the behavior will not change。

 I will always get the same thing out。 that's not always true in an imperative program， right。

 because if I have you know F of a functional call to F， I can't just stick it wherever I want。

 because it might do something。 It might mutate something It might loop forever。😊。

We're thinking about right now， like for things that don't。 Yeah， yeah， it might。

 it might like mutate some state。 So I don't wantna， don't want to be able to put that。

 I can't put that wherever I want。So we can swap equals for equals。

 and this is a concept I'll call equational reasoning， reasoning about your code。

 like you'd reason about a string of equations， A equals B equals C， so on and so forth。

This is the last thing I'll say to you this lecture。

 which is I want you to think about referential transparency by a different name。

 that's I call it the refactoring lemma， a Lemma like being some like aer， a helper theorem。

 like something you can use in a proof。😊，Referential transparency tells you you can refactor your code for free。

😡，Suppose that you're an engineering manager at a tech company named after a fruit that grows on apple trees。

 Okay， and you hire an intern。You hire an intern for the summer and they say， oh boss。

 I got this PR for you， it's great。 And you look at it and it's in standard ML because Apple uses standard ML of course。

 they don't and then you see this。😊，I'll let you gaze at that for a second。What the hell is this？

What am I looking at， I'm looking at a mess。 I'm looking at not quite spaghetti code。

 but I'm something close to it。 I'm looking at a mess， really， right， Like， like， like。

 can you easily think about what this is knowing。 just step through every single case， right， It's。

 it's pretty groves。😊，Let's solve it using referential transparency， shall we？

The inn didn't take 150， or they took it a long time ago， and they forgot about equivalences。

 So what you need to do is so here， for instance。If flag is set， then we use flags set。

 But under the then branch， we know flagasse set is true， right？ And here， if permission granted。

 but here we know that we're in the else branch， So permissions granted is false。 So let's step it。

So if I replace。Flag is set for true。 Air replace permissions granted for false because they're extensionly equivalent。

 I can swap them。 I can substitute because they're algebraically equivalent。 I get this one。

But now I see another thing， right， isn't it also stupid because I'm doing true and also where and also is the logical and operator。

Isn't it true that true and a is always a， right， It's， there's no point to doing true and something。

 So I can， I can refactor that。 So I'm gonna to get this。Okay， but oh， what's this。

 It's something I showed you earlier this lecture。 I have if something then true else false。

 and we know that if permissions granted， then true else false is the same thing as permissions granted。

 isn't it？ So let me refactor that once more。I get if flag is set。

 then permissions granted else false。But wait， if I。

 it looks like the only time we ever get true is when both of these conditions are true。

 Isn't that the same as ending both of them together。 So if I do this， I get。That。

Which is extensionly equivalent。 And therefore， it's a free simplification。

 I can always replace the intern's mess。With flag is set and end， or're not and end。

 And also permissions granted。 The refactor Lemo gives us up for free。

 Referential transparency gives us that for free。 We can always simplify our code via doing very simple equivalences because it was a big leap to go from the interns code to that。

 right， But each step I showed you was pretty simple， right。

 I just pointed out like a small thing that could be simpler。 And we carried that along with us。

 We did a we did a small。😊，Extension equivalent step。 And eventually。

 we ended up somewhere a little bit far away。 But here's the。

 here's the fun thing about extension equience。 It's what we call an equience relation。

 which means it's transitive， meaning that if I have。😊，E1。Equivalent E2， equivalent E3。

Then I also have。E1 and E 3 are equivalent。 I can do as many times as I like。 I'm。

 I'm giving you the math， but you can probably think about this conceptually， intuitively。

 pretty easily as well。 So the point is， I guess simpler code。😊，And the point is。

 referential transparency saves lives。 It saves my life as a manager anyways， So I have more stuff。

 but I'm not gonna to be able to tell it to you。 So class is missed。

 I'll see you Tuesday and we'll pick up where I left off。😊。



![](img/b4538c642549fcec4432fcb6f8b852a4_25.png)