# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p10 P11 a -BV1qBqPBYEy1_p10-

And I've been on sort of sabbaticical three months。 so I haven't had much time to do new material。

 So this is a， I can't talk done before。I hope you like it。 I'm a software engineer at Google。

 And this is。Last five years， I've spent a lot of time on the Dart programme I designing it and getting it implemented。

 And this talk will talk about how we learn from past object oriented platforms and how we got some ideas into that。

It's the first time I have been part of a language design team before。

 It's just about the improving the。Performance of。Not so optimal。Languageists。But that's also fun。

 so。😊，Hopefully it will be good for you to learn Ask question along the way。

 I like to talk about details， talk about implementation。😊，And mine will stop me if I go too long。

This is great。 I've type in my password， again。Okay， here we go。So， it's always good to。

When talking about programme， where does it come from and what do you do in the past in order to。

Influence you。 So I'll just talk about few of the system I worked on， and。Some of them， you know。

 some you don't。 How many of you have tried out similar 67。Nan。

That's where I'll be going to the start before small talk。And the professor at my University。

 when I studied all lima medicine。He designed the proe length with Bent and Buer and Chris Ngart。

 Chris Ngart he is also the designer of S。And it had a unified concept called patterns。

 So you could have virtual patterns and that's the patterns。 And， you know， in a vector program。

 you all use usually super to pass control from the sub class to the super class in betas the other way around。

 iss always the superclass of control。 and you can call inner thatll pass the control down to the subclass。

So that means you can have。Yeah， you can have a， a loop and inside the loop， you'll call in。

 and they'll call In repeatedly。 So that's sort of interesting。 You have some。

 you can create some interesting control sort that way。So what I want to tell you about it is。

 it was fun。 It was my first experience washing from machines。 I had to do the garbage collector。😊。

And my first part of the。The gaps was to expand an existing gaps to be generation based。

 and it was all written in assembly。 So that was fun。😊，But it' was hard to learn beta。

 It's not based on curly braces。And。The pattern model was probably too complicated for many people to understand because it was used both for methods and for classes and other for abstractions。

 So people were sometimes confused when they read the library。

 They couldn't really figure out if a pattern should be used for a method or。At closure or， or class。

 So I think that was one of the problems why that didn't go。Much outside the university。

They way to sunlase。To work on self。Self was an inherently inefficient programming language。

 It was designed that way。And the。It was sort of inspired by small talk， E。

 even though it turned out to be。A prototype based language。 You have very simple language semantics。

 And I think the， the cool part about this research project was the implementation techniques invented in that group at that to add that to compilation and the optimization。

 Have you heard about this in this class here。😊，All right。The optimization is the coolest thing ever。

呃。It allows you to preserve the illusion that you are running an interpreter system。

 even though you are optimizing the hell out of it。And the， the language is designed by Dave Wga and。

 and Randy Smith。 Dave Wga was here not not long ago。Yeah， he's got in。 Okay， he was。

 he was my manager in， in， in that group。And I that's why I met the Mario， of course。

 And I think the， the interesting part of the about this project here。

 a lot of interesting compil techniques came out。😊，But the。

The sales product was viewed as being bloated。If you ran the sale system， it reduced a lot of Ram。

 So people thought that people were wasting Ram in order ticket performance。And one of the。

One of the reason for that is they use customization。

So imagine you have a hierarchy and you have a method up top。

And you create a lot of instances of this subtypes of。Of that super where you had the method in。

 you will make a copy of that method for each receiver type。

 So if you had a hierarchy of 400 different videos and the top one was called print。

 And youll call that， you could get 400 different copies of that print method。

And that certainly added。Yes。So it was explodeed， and。But it was very cool。

 And a lot of the techniques I， I've used to do。😊，VMs will and and our teams help doing has been based on what happened in the self project。

 So pay attention to， to the the papers。So we went to a startup。

 and we want to apply the self techniques to strong talk。

And strong talk was basically a small talk system with an optional type system on top of it。

The optional type system had nothing to one time。 it was。

It was mostly for making sure that the programmer could check his programme was correct before he started running it。

 It was created by Dave Grisw and Gillard Praca。 Gillard Braca is now working on on that。 So it's。

 it's all connected。And。What we did is we made sure that in instead of using the customization as itself。

 we eliminated that。 So we had an interpreter that would run until code was hot。

 And then we would do the compilation afterwards。 an interpreter would then collect type information at the call site so we could do appropriate inlining when。

 when doing optimizations。And。Then they ever came along and everything changed。

 Nobody wanted to invest in small talk anymore。So we， we took the。The。

 the strong talk VM and converted。 So it could need the the arrowero bytecode。 and so。

I think nearly to this day， there are some small toisms in the hotpot V M for。

 People are probably wondering why， but。That's where it comes from。嗯。

So you got acquired and I spent way too many years turning into a product afterwards。But apparently。

 its sound technology because theres。They're still using it all。I did some VMs in between。

 but then not that important in 2006， I got hired into Google and my startup project。

Was to hire in a good team that could do a fast jascript implementation。In 2006， b were really slow。

 Firefox。Had an interpreter that was based on bytecodes。

 Apple had an interpreter was based on interpretation of abstract syntax trees。

 So you can imagine they were not that fast。 And if you really want to scale up Web application。

 we needed something that was just radically better。How many of you have program？Devascript。

How many like it？Okay。That's， that's， that's about right。Jaosscript is is an interesting language。

 It has positive sites。 is for the first time you could， as a programmer just open the web page。

 Look at the code， change it and reload。See it was no tools in the way of doing programming。

 So it opened up programming to a lot of new kinds of programmers。 And that was great。😊。

And I think that was sort of the best part about Discript。now。We did we ate。

 and we made it one fast by applying some of the techniques we had done。 we have used in the。

The previous years， by。Looking at structures of objects and so on。

 But theosscope is pretty weird because you can change stuff on the fly。

And that means you need a lot of dependencies in the runtime system。 make sure you always can。

 can flush code when it's not valid anymore。 And that takes a lot of space and whatnot。And。

As Google used。Big and bigger Web apps as part of the business， we're trying to figure out how to。

Make that better。 And cashbal alone and need。Started tinkering with a new programming language a few years after we did V8。

So I'll be talking somewhat about that。And。Firstst of all， I just want to。

tellll you about some issues with jascript that cost us to start this new projectt。

So the first one is read。 In my mind， the JavaScript is hard to read because it's not that it doesn't have it declare to syntax。

The way you set up a program in ja is you read in a lot of expressions。

And when you're done evaluating that， you have a program。

So sometimes it's hard to look at the source code and see what you actually have in your program。

 You basically have to start the debug and see how everything is connected。

You can do monkey patching if you want to。 you can， you can swap， push and pop on a array。

That'll probably make a lot of programs behave badly， but you can do it if you want to。

 So it's so it's brittle to， to some extent。 then。 and certainly monkey passing is not good when you have two independent teams working on a big application。

 because if one one， one part of the team is mocking around with the libraries。

 you sort of break the assumptions of the other team。 and that's not good。So me。

 when I looked at big diosco programs。I thought we could do something better。 And certainly， for。

 for readability。We would like to have something where you can see the program structure in the source code in increased program productivity。

 and also it's most easy to debug and and find errors and track out track ways to change it in the source code。

So visibility was one， and then errors。Maybe I'm too， to old school。 I actually like to， when。

 when I run programme to get flag when there's an error。 But in the a。They have an interesting。

They have interesting in semantics。 And I call it keep trucking semantics。

 And it basically means that if you have a spelling error， it'll just continue on executing。

 So you've try to access the property。嗯。That's not there。 It's a spelling mistake in the name。

 It'll just return undefined， and it'll continue executing。And。

That's often helped by that if you have the wrong basic type in the program language。

The underlying semantics will do automatic implicit conversion of the type。

 So strings can be converted into Booles that can could be converted into numbers and so on。

So that's part of this。 Keep on talking semantics。 I actually would like to have runtime errors thrown early。

 especially when you do debugging。And it gives also a better confidence that。

That your unit test work in your framework and also that。After they deploy it。

 they will actually run the right thing。And that's the scalability part。

That's not static types in JavaScriptvascript。 So it means that if you have an interface。

Unless you have comments in the code that describes what kind of opt you're expecting at certain positions when calling。

You know， it's actually a little bit unclear。And code chances on on the fly， which is pretty。

 pretty bad， so。At Google， what we did is we came up with a closer compiler where you can put types in comments。

And use these commentss inside the common in in the code to。

 to tree shaking and also figure out if you call it the right way。And。Yeah， it's not very good。

 And we are， we only use javascript as an assembly language。Not as the。

 the source for the application。So。There was what caused us to start the that project。

 that was nearly five years ago。And。As you all know that it takes many things to make。

languageguage popular。You， you have to have it。 It has to be liable。

 some people that are programming。 they have to like it。 This is not something you can predict。

It to be efficient， certainly。And。It has to be supported by a good programming environment。

 So you do refactoring and stuff like that。 So that's what we're going for。Yeah。So， again。

 when you talk about。If you talk to the the B a lot developing projects in in companies。

 they are all about program of productivity。How fast can we get to something we can ship。

 And hopefully it should be predictable when we can ship it。

And my list for getting that is to have a clear and。And simple language with good semantics。

Have real libraries you can trust， then they're scalable， and then you need fast development cycles。

 That's what we learned from Javavascript。That you want to change the code and run it right away。

 if it takes more than half a second， you blew it。And。In the past。

 there's been tool chains that have taken 15 minutes to compile from you change the code until you can run it。

You have no idea what it does to program creativity。

 The programmer goes and get coffee eaten every time he has typed in a change。

And they become conservative in the way they do programming。 and they know， they don't experiment。

 So this is super important to have this immediacy in the underlying system。And then， of course。

 you'll need to have fast startup and good performance he stay。 Otherwise， he'll never fly。And then。

 tool support。People will like ideas where you can do refactoring。

 move methods around then in certain super classes and whatnot。And also for navigation。

 if you have big。Peace of code。We， we initially。Focused on the browser side。

And not only did you want to solve what I said before。

 we also wanted to have something that could be translated to efficient javascript。

Because it had to be。Comparible with all modern browsers。

 just jaming into Chrome would not solve the problem。Because then we would not function in the。

 the open web。 So if this ascript was important。We had to support the dom。

Had to be sort of secure since you， you're sort of on the fly， download code from the web。

And then it must be easy to learn。 And that's where we come back to the curly braces。

 You cannot make a programming language without curly braces。 It will not be used。Apparently。

People like extremely conservative in learning new languages。

I guess Python is being used without curly braces， but it's say。

It's one of the reasons why curly braces are in Javava。

 they had the same issue They of trying to make something that could be easily picked up。

By a mainstream programmer。And this is me， the first。Few months。Or is the Kespa。

Trying to make all this work isnt all。It's an all constrained problem deciding a program language when you have to make it run on a system。

诶。But that's how it often is。Doing。Languages is taught。By the way。So you sometimes hear that。

Theerocope got created in 10 days and stuff like that。It took us a while to。

 to do the language because we wanted to make sure that。The length design was consistent。

 and it could be implemented efficiently。 So you get a lot of design iterations in the beginning。

 So you want to say that this is a。If when people say， oh， this is easy。

 you just do new program language， it actually takes time。

So we first prototype something called the S programme language。

 It was not running inside the browser， but we did the language and the the V Ms in。

Or the VM in in three months and， and got some experience doing that。 And then afterwards， we。

 we did the initial language design。 So there' are certain constraints in a browser that means that you cannot just do anything in this new language because it had to run a browser。

 for instance。I assume you all have heard about small talk by now。

One of the cool constructs that non local returns is a way to bail out of a recursion。

We cannot do that in that because how would you do make that efficient jascript。

 We can only do exception throwing。 and that's talk slow。

So there are certain things that prevent you from putting in cool features when you。

 when you have to be bound by a platform。So we hired in Gillard Parker to guys who is。

 He wrote the spec for， for， for the D program with language。

 It's important to get a person in that can write a specification。

 There's only a few of them that's good at that。So we got him in， and。

He was also the author of the strong talk system that had optional typing。

whichhich you also have in our system， and this is the algorithm we use we implement it。

An native virtual machine and a DS translator for the initial language and then iterated the design。

 update the implementation until we are sort of happy with consistency and speed。So， that was fun。

Now， the funny， the fun part about that is there's not much new in it。

And you can then ask why then do a program or language。We think it's a step forward。

 even though it has been taking a lot of features from， from other programming languages。

We really wanted to make it easy to learn。 So if you had a background in Java or C sharpp or Java。

 you should pick it up in a few hours。 That's， that was basically the idea。Unmurpri in semantics。

 class based single inheritance。We had makes and interfaces。We have compared to groscope。

 we have real lexical scing。 I kind recommend that to anybody doing languages。

And we have a single thread execution， but we can spin up more isolates。

 and they can communicate with misses passing。 And then we have this。

Optional static types in the system。 And again， the reason why we put that in is that we want。

Immediate gratification when you do programming。Often when you have a programme length with static types。

 the static types are often in the way when you do experimentation。

 So we wanted a system where you can experiment。With the program。 and as it matured your code base。

 you could add the static types。So， that is a。Simple syntax with cur braces， object。

 objects model based on small talk。Sttheatic types stolen from strong to O inspired by strong talk。

Ilit El Elang， and then we have asynchronous computation， as they have in C sharp。So， not much new。

Here's a code， here's a point。 you can all read this。For you guys。

 it only take two minutes to understand the code instead of two hours。And。The variable is untyped。

Scrreeen。It's good。And this one here is just a class， a point class with two variables， constructor。

 there's no body part to the constructor because you do all the work in the parameters。

 This do x will assign。The incoming parameter to x and so forth。

 And then you have an operator plus return new point。

And the two string that's using string interpoulation to。

To give you a printable version of the string。Allright。Sttheatic types in dot。Here are。The same。

 here's the same program where we add the staticotypes。So instead of v， we added no。

Return types and types on parameters， but it's pretty much the same。that has interface types。

 So it doesn't really help with the implementation。

 So the VM itself just ignores the static types and executes as， as this。So why。

 why did we put in this wonky type system。Well， we believe the statictype helps the programmer understand what's going on。

So， and we also want to make sure that when youre on testing on a program。

 it works like a chaable documentation。 If you pass in a point to something that respects a strings。

 a string you you should be told this is not good。And。We added generic lyrics。

 It might have been a mistake。 Some claims it was a mistake。

But often you have a list of intes or a set of points and stuff like that。

 So they convey information to the programmer， that type instead of just it' a list or a。As set。

Again。These type annotation on fields variables and parameters have no effect at run time。

 which is sort of the interesting part。 So the VM does all the adaptive compilations independent of the static ties provided in the programme。

Unfortunately， you can say that our type system。It's not sound， but the execution is safe。

 so it doesn't crash if you do something wrong。The unsoundness。Is deliberate。

Because if we want a sound， it gets really complicated。 You probably all have。

Have struggled with type system in the past。 And if you have genericrics where。诶。You have to。

 you often have to figure out if it's a covarian a contravarian type。 Most normal programmers。

 people that have not gone here to Berkeley， they don't understand what it is。

 So they refuse to write libraries that use the lyrics。What we do is we say。Yeah。

 it's probably not safe， but you， you， you can state the intent with your program here。

 and we will have some implicit casts instead of explicit casts we should usually do in Javavo and other programming languages。

Alright。So because we have this optional type system， we can have mixed mode code。

 some code that's typed and some code that's untyped。

And I already mentioned that it's actually fine when you do experimentation to have one type code。

 and as you mature the program， you can start putting the types。

 And especially if you want to handle the code to some of the coworker workers。

 it's nice to have types because then it states the intent of how it should be used。😊。

We have a company that is using that for a web education。 And they， they have of a different split。

 They have designers and engineers， designers， they do the U I and they do a little bit of coding。

 They hate。And I repeat hate types。 So they just want to do the scripting。

Then you have the engineers， they do the connection to the back end。They love types。

 So you have these two bodies of code。 And in that， we。When you check the code。

 you can run check mode。 and it means that when you cross the boundary from on type code to type code。

 you can actually validate that you pass in the right objects and so forth。And。These guys here。

 they like that because then they can claim it's not their problem when the designers are using their API the wrong way。

Here's an example of a generic type。With strong or the class with the types。As well。

 And it's a histogram it's。Has two generic。Values K and V K stands for key， V for value。And。

The point here is just it's an abstraction。That where you can pass in and itable values。

And you pass in a closure that'll give a key compute， now give a valuable co computer key。

 and then it'll sort it and create the histogram。 And you can dump it out。

 I don't have to go through the code， other than。If you notice small talk。

 we also have cascaded calls here。Dot dot。And。And I want to show you a few ways you can use such a typed library histogram。

First， you can just use it untyped， you make a list。Here list and the values in list are。

Strings and interior。 And you create a new histogram without specifying the， the type parameters。

Pass in the identity function or identity closure。And they list and they dump it。 It works fine。

No problem。If you then try to create a histogram where you say it has to be。Key has to be string。

 valuesue should also be string， and you pass in the same list， which is untyped。

Then if you run tech tech mode， as you usually do when you do debugging development。

Then you get a run time error saying that you're trying to。To。

 to use a an end where you should use a string。 So that's where you。

 you actually check when you cross from untype to type。And then， of course， as。

 as you strengthen the， the types in the program here where we say the list is a list of string。

And we specify everything。 Then you get a static warning ahead of running the program。 So you can。

 you can， you can be as static as you want to。Some of our users of that。

They only want fully typed code， and you have that option。

You can just say you all the code has to be typed before running it。

 And that's what they force upon the programmers。But you don't have to in that。So。

So what are these types good for？ Well， they' are good for static analysis。

And they're good for in mixed mode of doing runtime checks when you pass from untype to type code。

And。And then， you can。And just states the， the intent of the program。 And the。

 if you have it static typed， you can also use a program environment for doing refactoring of all the code。

 So we， we give the freedom to。The products are the programmers to decide what they want to use。

Feedom is good。I've talked about this。So I'll just go through， go through a few things。

 we doing that。Very quickly， we have constructors in that， which is great。And。

We have simplified constructors。 So in most case， you don't have to specify the body of the constructor by using initial isolateists。

We have name constructors， and we have factory constructors。 And here's a few， here a few examples。

Since we don't have， we cannot rely on static types and overloading。

 we have name constructors so we can specify several constructors to the same class。

You have the default one point， and then you have point that polar。And at the end。

 you can see how you create these two different。Points in two different ways。Very simple。

Then we have something for simplicity。 Have you all programe。When you say new。

 you have to specify the implementation type you want to allocate。But simple programmers。

 they don't know what Do link list or what kind of list you should have。

 So we decided to put in a a factor construct。 So we just say I want new list and the online system will then decide。

Whatever best to give give it to you。And here's an example。 You say new list， I think， in our case。

Where you get a doubling list by default。And here is， is it the class。

 so you can also specify the element types should be a point。We， we put that in， mostly because。嗯。

The factory construct was put in mostly because we can be。

 we can be more flexible when creating objectss。Instead of if you look at Javava。

 often weards are claiming you should use factory methods or。Instead of so。

 we have static method then generate elements。 And it gets really complicated。

 So we're just trying to keep it simple here。Here's an ex example of。A simple。It has a name。

 and it has a static variable。 And a map is called under by cash。

And we have a factory constructor is in line here。It says if you have already。

That name in the cache willll just return the cache value。 Otherwise。

 Otherwise it willll create a new one。 and it calls the。Named on the bar， internal one。So that's a。

 a simple class。 The interesting part about this is on the bar， means privacy。And on the bar。

It means private in library sense。 So if you're outside that library。

 you cannot cook up a name that will invoke that。Very simple。

 I believe Python is doing something similar。Except in Python， I think you can cook up the name。

 But here you cannot。So it's just a simple way of specifying at the。

The call site that it's lip specific。 And also at the declaration side， it's library private。

Cascaded of calls I mentioned before。 It's inspired by small talk。 It's just an easy way。

Of when you compute an expression to call several things on the result of that expression iss used a lot in small talk。

 And I think it's a handy way of expressing code。The only difference between。E small talk and。

And that is that in small talk， you always end up saying， sending yourself to the expression。

 So it turns the original expression。 and that is done automatically。 If you look at how。

The other programmers do it they claim you should do method chaining。

 That means that each method should return this at the end。

But it put a burden on the implement of the different abstractions。

 We don't have to do that when we have cascadia method。 So here it looks。Very simply。

 like can dot context is expression， and you call a number of things on that expression。

It's just handy。Now， I didn't how many have programme for the for web browser。Okay。

 so you know that a web browser web browser code is single thread。And if you do a lot of computation。

 the， the browser will whack you and stop the execution。

 So that means that you cannot ho the CPU in a web browser。That'， that's good。So。

 it's single threaded。And。If you want to do I O in a browser， you have to do it with callbacks。

 right， You cannot just block because you don't know how long time the I O will happen。

So because they'll， they'll kill the the view in the browser。In Javava。

 you solved I O by having multiple threats。 at least that's what you did in the beginning。

It doesn't scale that well。 So they have also。Asynchronous programming in Javava these days， I guess。

 or at least call back completion。So if you write the I O， here's the， the， the。

Very complicated piece of code。That is a method that reads a block and writes it to some。

Other place afterwards， read and write blocking calls。 You have a cat and a final code。

 That works great if you are。😊，If you' are running stand alone on a unique system。

 because you'll just block until these operations completed and continue in it。In the browser。

 you cannot do that。 Itll just kill the execution， so。What do we do in the browser？ Well。

 the first attempt is to。To do callbacks。 So you have the。Readat write method。

 So you first call read。And you pass in a closure that when the recomples。

 it'll call the closure with a result。And then it can do the right。

And then you can pass in all the error handlers all the time。

 and it might work Well we're forgetting about the finally， because that's just too hard to do。

And if you look at note that JS code， you'll often see a。Code that selfned。Maybe I'm just old school。

 I cannot read it。It's very hard to figure out what's going on， especially if。

If you have control flow going on in these callback structures， so。Smart people come up with futures。

 So you say you have an abstraction， call a future。 When you call read， you get a future back。

And on that filter， you can set at then closure and the then closure is executed when the future completes。

 and you can also attach error handlers and， and finally to it。

So as you can see that in the normal program language， you will use cats。 And finally。

 now is library calls， but it's sort of doing the same。It's a little bit better。But not much。

Because often what you want to do， you want to have logic around these flu futures。

 And whenever you have a new kind of。structure。Then you had to put in the library of the of the future。

 And then you have a duality where some。Most most of this。

 the language constructs in the language also have to be matched in the library for futures。

 And that doesn't work really well。So we hired in Are that used to work on the C sharp team。

And he helped doing the eing methods in C sharp。And luckily。

 we had futures and streams in our art platform。And his work on asynchronous methods built on top of these abstractions。

 So this is clearly inspired by C sharprp。And it allows us to write。Synchronous code。In the。

 in a straightforward way。 So on the left， you have。A think Marga on the method。And inside。

 you can use the weight here and here。And otherwise， it looks like the same code we started out with。

So what does it really mean to have a weight in the middle of a method。It basically means that。

The compiler changes the code。Into。Something that could be suspended。

 It takes it off the activation and then it creates continuation points for each， a weight point。

So E Myers famous quote is that the way suspends the activation in an unblocking way。

That's a strange way to think about it。So when you call one of these as methods。

Itll return right away。But it will add a continuation to a scheduler so that when a future completes and what have you。

 it'll be woke to life again。So that's good。 We get the normal control flow back， even file。

 even though we only have one thread and we're running inside the browser。😊。

And the good thing about this model here is you can just change one method at a time。

 The code generation only is local。To the method。The bad part is that。It's really hard to understand。

 when you mix。Sy code with S code。And I don't know how many of you have used see plus plus if you used cont in a certain part of the program。

 its contagious， then you also can only call other cont methods and so on。

This' sort of the same here with， with the asnc， because in asnc， you can only call asing code。If it。

 if it blocks right。So that's one thing。 Another thing is that stack traces disappear because as soon as you call something。

 it returns。So if you put in a break point and stop it in a debugger， that's no stack。

 It's like it looks at spontaneous activation of a continuation point。That's a little bit hot。

But it's better。 Overall， I think it's a good step forward。

 And it turns out a lot of the code we have written with callbacks we've rewro using as sync and it's actually easier to read。

 so。😊，Again， when you do language design is often。Comproises and making sure it works。

But that's how it is。 We also put in for the Dar VM， we。And the dark La。

 we thought about fast startup of applications。I talked this briefly about jascript。

 The way you start jascript is you read in and execute the expressions of the source code before you can start running。

That means if you run programs like Gmail or something similar。

 it can take up to a second before you start executing the code because you have to set up the program each in every time。

What we didn't do is we made sure that when you written the program， you don't do anything。

Other than reading it in。And the first thing you execute is the first statement of main。Right。

 so that's no setup。We also allow tree shaking， which is a word from。Strong talk。

 not no small talk where you， when you have your program。

You do analysis on the program you start shaking it。

 and all the stuff that falls off that's not being called。

 You don't have to have part of your executing program。

The reason we you do that is we have disallowed a well。 You all know what a well is。

 A well takes source coat， generates the coat on the fly。Is this big security hole。

 So for these two reasons， we don't have that。So in the Dar VM。

 we put in a platform independent binary snapshots for fast application loading。

 And when we measured reading in Dar source code versus reading in snapshots。

 we get a effect of 10 in speed up。And that's pretty nice。 F of 10， will always take that。says he样。

Go effect of 10。And the snapshot is easy to implement。 You'd be basically start up the program。On Ma。

And then you serialize the heap in a binary form。And you can make it platform independent。

 So even it'll work。Filing it out on a 32 bit machine and filing it in on a 32 bit machine。

 And that's what we do。So no need for scanning and passing source code。

And it's super important for the for， for these mobile devices， because speed。

Is great for conserving battery。Anyways， that was sort of a little bit of history that we have continued to。

Evolved programming language。 is' now an open standard。 And yes， you can imagine。

 it's much easier to change stuff。 Alfa is an open standard。 Nobody has an opinion about how。

 what you should put into it， but。That's how it is。 Everything has to be open these days。

 and it's probably a good in the long run， so。We did the first edition in 2014。

Second one in December 14， and we added。Believe it or not， enumerations apparently important。

Asynchronly， I just talked about and deferred loading。

 Def loading is that when you compile to Javascript。

 we can keep part of the program in in a different file and only load on demand to make sure startup is even better in the browser。

And in the third edition， which came out this year， we put in。

Not operators just synthetictactic sugar when you write the expressions。And then generalize tariffs。

 closer tariff。 So you can actually say。You can say new point。

And then the hash sign that will rip off a closure for the constructor。 And you can call that later。

 if you want to。Simple stuff。So I want to talk about the browser， but。

The world has changed since we started this project。Unfortunately。It's all about mobile these days。

 That's where it is mobile and I O T。 So we are also working in these areas。

And I'll just briefly talk about。The three areas we' are focusing on right now。

We still do that for the Web。 Its still our main effort。 We improve the translation to jascript。

 We're trying to do better interrupt the jascript。And then， we are。

Experimenting with a subset of that further web to make it more compact and more interrobable with jascript。

 We don't have final answers yet， but this is happening， as we speak。For mobile。

 we have a an interesting new platform called Flutter dot I O。 Oh， by the way。

 everything I talked about is open source。 So if you want to contribute。😊，You can do that。

Flora is also open source。And it's basically a an application platform that works across Android and ios for writing mobile applications。

呃。Nice animation and is all implemented that， except the lower level graphics。Which is nice。

And then we have start new effort with a new VM。 And that's called。That for IoT。

When you read some prediction about the future， it's all about robots and small。Devices。

 so we created something called Fps， which is a compact。Butt Vm。And。

We can run a that VM plus the application is in 200 cases or so。 So it's， it's very small。

So there's no dynamic optimization right now it's just based on an interpreter。

And a very compact object layout。The promise here is to get away from。

C an assembly and swallowing iron when they do applications for I O T。Often。

 when you do a chance in the。In the program for an Io T device， you have to flash the whole device。

So we really want to make a small system where you can。

That has safe execution where you can have third party code running on the device if you choose to do so without in being it causing failures and and crashes。

And the target for it is this。Cortex M7 microcontroller， so。32 B arm CPU， or 320 kB of Ram。

And then half a megabyte of flash。 And that's， that should be sufficient for the whole O S and the dot VM and the applications on top。

 So this is very exciting。 It's really fun to play with I O T devices。 If youre not tried it， it's。😊。

Its fun to try out。唉。Doing a new language takes， a lot of time。We started in 2010。 we still added it。

And。Who knows when this will become the the world's most popular programme lamp。诶。

I think we're doing fine right now。 I would expect that in 2，3 years。

 we'll see whether there's a big take up of the language。

 One thing that's important to understand is that。Companies select the language， based on。

Who else is using it。 So we have to make sure that big big companies like Google are using it for their applications before other people pick it up。

 So that's just very natural that that people are conservative。But it's still fun to work on。

We also have a。At that process， at that enhancement process。 So if you have。诶。

Features you like to have to have like to added to that， you can。You can， you can submit a proposal。

 We have some proposal for non noable types， which is。A good thing to have in。

 Its not back was compatible， so we cannot put it in before。May I made your release 20。诶。

Dric methods better support filess and configurations sp specific input。

 So you can make platform independent。Interfaces and platform dependent implementations。

 So that's what's in on the list right now。呃。I'm always asked， so。

So what do we regret in this programme language。 Well， first of all。

 we focus too much on the web in the beginning and certainly put some limitations on the。

 on the language。And also。ItCa us to deemphae the work on isism and parallelism。 And now we。

 we are working on that。 But then it just takes longer to get everything in。呃。

Another regret that's so small is that it's。I don't like it。

 but it's something that came from jascript。If you have a point like we tried out before and you say p or two string and you don't put the parentheses in。

 you get a closure。If you add the close， you execute the method。It's very easy to make mistakes。

That way。So assume that you have a field on one object cox and another one where you have a method cox。

 and you say。You have a variable you say。X to it。 Sometimes you get a closer。

 Sometimes you read the field。So that's one of the reasons why we added that the explicit。

Syntax for tariffoffs so we can deprecate this hopefully in the future。

But this is just their Deosk Im。嗯。Research directions。 Well， we're not a research group。

 but we encourage people to try it out。 We have some collaboration with O University。

 that have some type people that are adding plugable type checks for that to see how they can improve。

The language， and we're looking into how to best sp split an application into isolates， where。

There's no shared memory， but you only use message passing。And。

Come over the own story and contribute its open source。And。The sad part about the the P。

 L world is that people are religious about it。And。When we came out with that in， I don't know。

2010 or 11。You had。Comments on the Web saying， you cannot do anything else than Java。

That's treasoning， basically。And I'm of the complete opposite opinion， The modern arr。

 Please go and make new programme languages。 This is the only way to improve program productivity。

Some of them will fail。 and if you look in the past， there are several hundred programming languages。

 most of them have failed。But that's not the same as saying， we should not。

EDo innovation and try out new programmeable languages。I thought about industry was conservative。

 but academia is also。When I went to the university， the languages I used。

 they were created locally at the university for experimentation。I often see now that the。

Even good universities are using C C plus plus and ever because then people。

 students are ready for industry afterwards。 I think that's bad。诶。

Learning more programming languages and experimental programs give you sort of a background in thinking about how they actually work。

So。's it。You don't teach ever here。Right。So you sign this oh program language you tried out。

 I think it's fairly readable and well defined。Has some nice properties。

We don't know if it will become a success。 We are still in the process， and it takes a long time。

But I am certainly still proud of the， the language design and the and how easy it is to use。😊。

So that is my talk。 And I would like you to ask questions now。Yes。😊，Dis so you want to back。So。这是。

No backward compatibility with modern browsers。 So we had to generate jascript。呃。

We have a program called Dar to Js。 And this is what you do in development。 right。

 So you generate the DS code and deploy the DS code。Okay。

 so you to Jeica so but what if you already have with？available。Yeah。Well right now。

 there's no browsers that that have that has a built in Dart VM。 So for the web。

 it's only deployed by ideas right now。So we generate the source map files they're called。

So that when you debug in the Chme debug or look at the profile。

They convert positions back to the source code。 So you can see how。Where the cost stems from。嗯。

But if you run on， on floda or， or the I O T devices is native VMs， we have。

We focus a lot on performance。 And if you compare the， the hotspot and all other the hotpot， the。

The V8 VM with the native dot VM， we usually clock a factor of two in performance improvements。

 And it's mostly to do with that the language is simpler。

 and we don't have all these checks as you have to have when you run the JavaScriptscript。

Next question， yes。然后。Thank you for asking that question。Yeah， you cannot right you。 you。

 you cannot claim effective of two。But what we can do。

 And that's one team that had a substantial web application that to write that that tried twice to make a new generation that app in the javascript。

And in desperation， they， they tried that instead。 And they clocked all the milestones and shipped on time。

 So that's an evidence。 But I don't have any factors in increased productivity。

 I just have to rely on what they tell me after they've done the product。Unfortunately。

 I wish I had the user studies where I can。Take two independent teams and do it。 But we。

 we don't have the resource to do that。So I have to trust on what they tell me。Yes。タ en发。

Did you ever consider like automatically adding？And。Yes， we， we， we T， weve thought about。

 we haven't done it， which is a cool idea。Yes。No。The， the， the problem。Emply。

It has to be the programmer that is very close to that insertion of that extra code。You don't want。

 you don't want on type code and run it through a pre process or whatever you order and then get some code out where you have a lot of annotations。

 I think thatll be more confusing that helpful。Because sometimes it's wrong。 right。

 It's not the right thing。 So you want， you probably want guidance。

 So if you have a programming environment where you can。Say， oh， this might be this type。

 Dont only want to fill that in。 I think that would be great。

 And based on running the program and collecting information， I think that's good to do。

 But we haven't implemented yet。It's too much to do。Yes。My understanding is that。By dark。Yes。

How much do you do you know about S gas。这是。Okay。It's， it's not a。So it's not JavaScript。

It doesn't have objects。Its as D has been done so you can translate C programme into。

Into something runs in the browser and the heap。Is a by array。

So you have to manage all your own things in there。 So you can only allocate optics。

 and it can be copies collecteded。 So is。We don't generate S node J at all。

We then write a subset of javascript。The subset， we know that' fast。And。Yeah， so I didn't have。

But it's changing， right。Well right now。Right now， it's not a good target because you basically have to。

Implement the whole virtual machine on top of asthmama Js， the garbage collected and stuff like that。

 And right now， it's pretty hard to inter intererate with the dom when you are running inside this。

 the asthmama G subset。So there's a lot of restrictions。Right now， I know they are。Right now。

 designing something that's better than S is， where you get opt capabilities and stuff like that。

 Then it makes sense to do it。 But right now， it doesn't。Yeah。Yes。It seems to be the design。

You don't want to be that many。The fewer， so the more merrier is a number of programme blank。

 not amount of people designing it。嗯。We were two that did the initial language。

 And I think you cannot be that， cannot be that many doing the， if it has to be consistent。

When we open it up to comments from the outside。And。

I think you youre often people are often not seeing it sort of holistically。

 They are looking at their pet feature they want to have into the program lens。 And it's like， oh。

 if we don't have optional semicoons， we cannot use your system。Okay。

But the reason I didn't put that in is because length are like jascript that has it。

It changes the semantics， right so。So it's not easy always。😊。

So I think what you see as you go into these standardization committees trying to have evaluate proposals getting in。

 it gets harder and harder to make sure a proposal will fit the entire language。

And that takes a long time to do。 So， for instance， the。G methods， right， So that's proposal。

 but it takes it takes months to for， for a person to figure out if it fit for the rest thing out if adding generic methods requires type inferencing or not。

 because if you're forced to put in these type parameters everywhere。

 Maybe it's it gets annoying And nobody wants to use it。 And as I said。

 them beginning of to talk using a language also about you have to convince a user， it's nice to use。

 right， they have to like it otherwise， they'll switch。So fewer in the， in the beginning is better。

 So I would rather have that。You have a lot of proposals and throw the bad ones out。At least。

 that worked for us。Yes。You hide the weight。Yes。So you get a。You make it infinitely complicated， yes。

Of course， succeed。A。I think it's since。Since I think。Suspendense the activation。

If you call it a sync method， I think it's important to her Marcus in the code that says well it can happen。

Because if you， if you call one of these asc methods。

 it it returns to the call and continues to execute execute。 It doesn't suspend the whole thing。

 It's only that activation。So I don't know how you can do it automatically。I was。Think about how。

You have stacks。Yeah。And。So we， we thought about doing it in in when converting to the a。

 what you have to do， you basically have to have generate two code paths per method。

 one where the activations are happening on the stack and one where it happens off the stack。

But it G， it gets complicated because what you have to do is not only do you have to store store the expression stack and the locals。

 you also have to have a return address。And the only way to continue at a。

 at the return is by creating a continuation。诶。It's not trivialent Ya。Okay， so。Like。

 what would you have done？合同。That's， that' that's a good question。

I think many of the feus would be the same。I would。

I will probably have either had have some in in isolate concurrency or co routines in there。Get a。

 get get rid of the I think。Because if you。If you have co routines or or threats。

 it's must easy to understand what's going on。Because again。

 the way you think about executing an Syn。A method is that you supend it， but you continue。

 It is not。 you， youre like continue in two places at the same time， conceptually。And that's， in my。

 that's a little bit broken。So I， I， I like threading or fis or or what have you。

 So that will probably be the， the outcome。 however， I want to say that。

Do you ever made a hugeot mistake。When they designed。Threading into the programming language。

 they put。synynchronization primitives。In the core language and all the way up in the optic class。

 right， So you have。You have synchronized methods， and you have。诶。the weight， notify。

 notify all is all available on all optics。And I think。

There was a mistake because when you run normal program， even though they're single thread。

 they do a lot of locking， unlocking， even though it's completely unnecessary。

 And I even believe that in the C sharp world， they have they're now recommending you shouldn't use any of this object based locking。

 they use they have libraries use like in the old days for， for doing monitors and so on。

So I think the。There are some lessons to be learn， both from from C sharp and also from J。

 I don't know what the oracle's position is on。On fine grain blocking today。好。But I'm so。

 so here's an interesting fact when we started。Do hotspot， we， we。

 we profiled the classic VM was some of that was before hotpot。To figure out where the time went。

 because we had to figure out where to optimize it。And one third of the time went to。

As synchronization， one third for garbage collection and memory management。

 one third for actual execution。 And that was for a single program。

So we figured out fairly quickly that if you had to make that fast， right， you had to。

 you had to attack the whole pie before you couldn， could make the good performance improvements。嗯。

So not enough about that。 talk about V Ms。 What do you want to to know。Questions that are sent in。

Yes。Are they same one as you print on。Do you all have access to the questions， No probably not。And。

Here's a short one。嗯。After working on V 8， I would imagine you you were very comfortable with javascript and comfortable。

 but you understood it and it's internal。 But did you gain any new or surprising insight when implementing it the translated from。

dot to ja。唉。M。Since we implemented V 8， we sort of had a good idea what kind of sweet spot code we should generate for having optimal performance。

But we did love experiments， still。Because often， we could shorten the code by using a different construct and。

That was good。But the hard part was that we had to run on all browsers， so。

We primarily tested on Chrome which used V 8。 But then when we ran on other browsers。

 it would be slow。 So sometimes we ran out of the sweet spot for the other browser。

 So we had to sort of。Do some joggling in figuring out how to make sure that most browsers ran okay fast。

嗯。Yeah the， that sort of nightmare。 And I think this is one of the。

 the key issues here when we talk about languages and V Ms。If you have a language。

 that's very dynamic， like。Like the JavaScript， where you can change the format of an object at any point in time。

Then optimizations will try to sort of assume that you don't change the opt。

 If you change the optic format。 then you will have the de optimize and start optimizeim again。

 they'll slow down the program。诶。And the programmer doesn't know。

 So often by putting in a small statement， itll run slow on some browsers， but not others。

 which makes testing extremely complicated。 When decidinging that。

 we want to make sure that all the language statements we had in the language could be executed。

In a predictable way without perturbing the performance of the rest of the system。

So this is something that really hit us。So that's my biggest mistake in。Creating a team and V 8。

 that was to make sure it was so successful。嗯。Because we designed it for only a certain sweet spot。

 And I hope we trained the programmers to only use that sweet spot so as fast。😊，嗯。不掉。What else？And。

Okay， the question is minus one times and I intermediate representation as central。

 Yet the V8 virtual machine has no intermediate representation。 I assume that means bikecodes。

 Is that right。Okay。That's an interesting one。Yeah yeah。

The initial implementation of V 8 outside the browser standalone system。 we did that in four months。

So we didn't have much time。And what we learned from hotspot。

Was that if you have several execution mode， an interpreter and a compiler。

Testing is complicated because you have to turn， you have to check all the combinations of all the benchmarks in either one。

 the or mixed mode。So we decided when doing V that we only want to have one execution mode。

 and there was compiled code。 So we only had one way of doing it。 There was a starting point。

 And it turned out it was fast enough。 And that's the reason why I didn't put it in interpreter。

 And also because in any function in jascript， you can extract the source code again。

So the source code is actually the primary representation。 If you look at。At the ever。

 where the bikecodes are the the primary representation， right， You cannot get the source code。

 So that's all you have to deal with。That's when it makes sense I an interpreter because it。

 you can execute the intermediate format。So。We didn't know it worked out。

 We just wonder it was simple to start out with。 So it worked。But recently。The V8 team。

 and it's not my team anymore。 We， we transfer it to another Google team。

They have several execution modes。 They have。I believe， most recently， an interpreter。

What they call a full compiler。Crankshaft with an dynamic compiler。And then they have two of fan。

 which is a coating rate for mostly S and the D code。In the same system。

So you can imagine the the machine resources to check all combination of these execution modes。

So simple is good when you do VM。 So I encourage you， if you。If， as part of this class here。

 you do a VM make it as simple as possible to start up with。Time will make it complicated enough。And。

You have built many V Ms。How have you approached evolved over time？

It was a coffee approach techniques there no use again。That's a complicated one。 Yeah。

 so what have we learned。嗯。I love starting a U V M from scratch。 No lines of code。

 and you do it from scratch， because when you do that， you can focus on a single thing。😊。

It might be that。You only want to use the object he， even for internal data structures。

 We did a VM where generated code， temporary data in the VM and so on floated around in the object he like user data。

That's great， because then you only need one garbage collector to take care of it。

 Very simple In most V Ms today， when they're more complicated。

 they have a code case where you put the code in。😊。

But you also have have pointers from the code up to the user heap and the other way around。

 So suddenly you have two different memory the system have to collaborate gets complicated。

So I think it's important when you always start a U VM that you say。

 what can I do here to make it really simple。And so we also have an idea when starting out。

 and sometimes it works。 sometimes it doesn't work。One thing we， we tried out， that was great。诶。

When you die do VMs， you implement the VM and C， C plus plus or assembly。

And one of the problems is if you get into the random system。And there's a garbage collection。

Then you have to walk the C plus plus activation and figure out this that' point us because they have to be updated if optics move around。

And you in order to handle that， you put in these abstractions called handle so you can traverse them on the fly。

诶。When we did， for instance， V 8 and also other VM。

 we decided to say you cannot stop inside the VM for garbage collection。

So all operations were call to the VM。If they need to allocate something， it'll terminate。

The whole stack with a continuation that you should first allocate the structure and redo the operation。

That means you don't need handles。So stuff like that is important again from the beginning。

 because if you first put in handleified， you'll never get to this state where you can can simplify it。

 So I think for each， V M， we are done， we have tried to simplify。In， in a certain area。

But the problem with being successful， the VM is they get complicated。 So。

 so hotpot we started out with in。In 95， it's still around at Oracle。 and I'm pretty sure。

That the amount of code you have in there is amazingly big， right？ How many lines。質も？It's massive。

 right， millionsions lines of code。Yeah，2 or three mill lines of code。 It's complete insane。

And that always happens when you have a。Successful VM， like V 8， we started out very small。Suddenly。

 I have to run a Linux simulator。On top of jascript and， and ready。What。And。

That means suddenly you have to have different kinds of optimization。

 It's getting more and more complicated， and it requires more compilers and more runtime support。嗯。

In 2006， when I started on， on V 8， if we did benchmarks per In Expr。

 the garbage collection strategy would be that it allocated 1000 objectsic and they did garbage collection。

You can imagine how it scales。So it meant that a lot of programmers。

 they were just pre allating all the up to start up with， and they were allocating again。

Because suddenly， otherwise you'll get these pulse。Now。

 to a day where P V A is also being used for noted J。 And remember when we open sourced it。

 then people start using it， suddenly we were sending， oh。

 we need more than1 GB of heap for the aerosscript。

You pulling your hair out like what supposed to be this small， tiny system。

So popularity is certainly pressure pressure the。You， in terms of implementation。

 because people are using it unexpected ways。Did they go off the subject。So that's。

 so if you really want to do fun stuff， do not try to。

Take an existing platform and making it little bit better。Do it from scratch。 Much more fun。

How do we feel about using C plus process and roation language， great。呃。

You just have to not use all of it。So。I think I started using C plus plus for run systems back in in a self project the first time exposed to it。

 And it basically means that。No run type type information。Do not use templates。

 Do not use multiple inheritance。And。Yeah， but I think it goes along with on top type of information anyways。

If you use a subset of it， it's great。Because what's the alternative is that C。 Well in C。

 you don't have abstractions and abstractions is actually nice。

So at least you can have spec data types in see plus plus and。You can control the efficiency of it。

 So I think it's a very good language。 I haven not seen any that come close to that。嗯。By the way。

 the plus plus is designed by one comes from all。Beyond the starttop。

What is the future of V construction is the solve problem or the open problems。嗯。There's always。

 Vms to build。So I've been doing it for 30 years now。And I haven't been out of a job yet。

I'm of along this question here， I'm always asked。Why not just do1 VM that rules all。Right。

1 VM is like the S is。Well， the JVM claimed that at some point or the CR。 They said， oh。

 you can run any language on these， this intermediatem position。 the problem is。Yeah。

 if it smells of dibos is sharp， it sort of runs okay on them。

But you can try to convert the aerosscript into this this intermediate format for。

 for Javavo C sharp。 And， and suddenly， it's 10 times too slow。So I think the。

 the essence is here that when you have a new language has some interesting features。

 you really want to， to squeeze the performance out and make it nice。

 And that's where you have to have a special VM for it I。😊，My gut feeling since I haven't tried it。

 is that if you try to make a unified VM， it'll be 20% slower and it'll take 10 times as long time to build。

 so。If that's what you want。That's good， but。But I think it's always。

It's much easier to innovate in a VM for one language。Because you you you don't have to。

To think about the rest。 And there's a language。 It's not only a language。

 It's also about what's the threading model。How big is the heap and stuff like that。 So it's。

 it's actually very complicated to make a a platform that solves everything。Alright。

 but there's plenty of problems still to solve， so。And it's exciting to do V M。

 I don't know if you have you built one yet。Okay。Sooff。And。Should language designers know about。

 more about implementation techniques， Yes， they should。Because performance is super important。

And it's super important that。嗯。That you have a language that is， you can。

 you can get this immediacy out of。 One thing I learned about using Lisp and small talkg is that you empowered。

When you feel how the program is executed， it sounds weird。

 but going into the depog or you can see what's going on， you can thinkly。

 if you understand what's going on。And that means that the。

 the language has to be sort of in tandem with the implementation。Does it make sense。

That's the first question。 I'll， I'll just， it's 10 lines。 So I'll just spend one minute here。嗯。Okay。

 so that is about dynamic combination and crazy language features， it says。嗯。And。

I'll take the last one。 So let make。 it says， also。

 do you see value in letting the programme or communicate with a dynamic compiler through the use of meta programming features such as annotations and mirrors。

history has shown this is a really bad idea。 Programs have no clue how to optimize anyways。

 So when they try to tell the compiler what to do， its usually the wrong thing。嗯。And also。

 what kind of optimizations you want to do often has to do what machine you're running on。

 whether it's。え。A multi core CPU or single core。 What have you if there's an arm or an in CPU。I。

 I don't believe in me the programming features so we can help the programmer， one of the。

One issue is slip it off， but it's related。There's been this notion that programme was of and the programming languages。

Want to control the garbage collector。 And even in the excellent gave， library。

 you can call garbage collector。What does that mean？In the old days。

 he meant a full capscadet of the whole heap。So application programmers mostly on embedded system。

 they would。They will say garbage takes a long time。

 so we will always call full garbage collection when you let go of a menu。

And it basically destroys the performance of the whole program。 And these D C calls， they， they。

 they， they。They don't go away。 And it means that or admit meant in the D case that people start ignoring the calls to garbage collection。

 So it's just a no op。So getting hints from the program is often a bad thing。

And also because it depends on a lot of factors， what you optimize。 Like we talked to。

 you heard about adapt to compilation where you monitor the behavior of the program。

 And based on that， you optimize。The programmer doesn't necessarily know it because he only knows his library code。

So I wouldn't recommend that。But it's right that， as you mentioned here in the question that some languages have。

Crazy language with features。Do you know about the the four in。Consductt in javascript。Okay。

 is it completely insane？construct where you basically have to do a lot of reflective stuff in figuring out how to。

 how to implement it。And this is where this， this contract looks like a for loop， but it's not。

 It's like a huge machinery that's put in place to， to compute that。诶。When you do languages。

 you should not do that。 Make a language where you can。

They make libraries that have the that have constructs and abstractions。

 They'll do the right thing and just keep the language symbol。 It much better。

Because what you really want to have is when you debug your program。

 you want the program to understand what's going on。And I think that's super important。uh。

Anything else。beingM designer。I'm an old drum， but I don't like anything。嗯。嗯。

I V Ms are easy and easy to like， because what you do is you。You make a black box replacement。

 usually， right， there's something that's slow here。 You make a new one 10 times faster。

 You plug it in。There's claps everywhere。 People like it。And that's instant of gratification。

 like with language， thats P people don't like it。 That it's about taste。

 and they think you ugly and。So it's， it's， it's different。 I like doing V Ms。

 but I think it's super important。That we get programming languages that are tied to the implementation。

So we can make the program experience better and therefore get better program productivity。

 So I couldn't。The easiest thing for me was just to go on to do another V。

But I think it's important still to， to， to do these kinds of projects where you show this can be done in a faster way or better way。

And。I I， I still like them both。 I still want to go back and do VM though， because it's。

It just feels good to， to make these execution in that that are toy。 For instance。

 we are doing this I OT VM now that that's， that's very small and。😊。

Building small things that fit well together is just a joy。So。

I probably have one more left VM in before I go on to retirement， but。That that be any。

 any last questions。Yes。What。嗯。That's， that's a very valid question， I think。If you want to go。

 if you want to replace an existing language in an existing environment。

You really have to be twice as good or 10 times as good before you can do it。

 And it's still an uphill battle。 I think the best way of getting a new programme language accepted is within a new field。

 like V O T， which is completely。Greeen right now， if you can get your foot into a platform where they use your language as the。

 the， the core programme language for that platform， they' are certainly easiest。And。So。The。

 the sad part is that。The expectations of a programme length has changed over time。诶。In the old days。

 it was you， you made a language and specification and had a toy implementation。

 and people will start playing with it。 Nowadays， they expect a complete library。

Superior performance， programming environment。And support and everything。

 So it takes a lot of resources。One of the reasons why I'm in a big company。

 because that's where you can do stuff like that。 And all， by the way， it cannot cost anything。

There's no money in in， in languages and V Ms anymore。

So there's basically big companies that think they get something out of building these systems。

Alright， I think that's it。Thanks。