# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p14 P15 -BV1qBqPBYEy1_p14-

Which gears off。Kind of ever more increasing sophistication of implementation techniques and look at a different。

 completely different way of what we're building VMs is。

That's been developed by my group in Oracle labs。And has some interesting results and momentum。

 and this is what you're going to be using for your next exercise。嗯。Next week is Thanksgiving。

 so no lecture， there'll be two weeks for the next one and then the last two lectures will be on concurrency techniques and tools I have another guest speaker coming in on the end。

O。So。Here's a graph I put together a while ago， it might be more than you。

I've been nearly two years now in which I took the data on this website called the computer Language Benchmarks game you've probably seen if you're a programming language guy。

 used to be called a language Sho tell。Website， and basically it's a bunch of applications。

that have been recoded in a very large number of languages and then performance data have been submitted against them and what I did was I took a collection of languages from mostly from like the ToOB top 20 languages list and plotted the data for the performance of the best performance of each of those language implementation pairs and normalized them to see which I took as you know kind of Uniity。

嗯。Pnge of salt right don't you know it's called a game for a reason you shouldn't take stuff like this very seriously because for a start a lot of these programs are completely out of the normal domain of usage of some of the languages。

 you know the the applications for example， written in our here are like you would never do these things in R like no one in the right mind would do。

So it has to be taken with a very large grain salt， but nonetheless。

 there is some connal of truth in this。When you plot the performance data。On a new logarithmic scale。

 not linear scale， you get a pretty big spread of performance。

 you get a bunch of languages with pretty decent performance。

 you get JavaScriptscript which currently sits in the middle my guess is if I read this graph now it would be a lot better。

And then you get broadly speaking what I would describe as inscriptive languages。我时号白。Sorry。

 what's the blue secret blue right？small talk， oh， small talk。

So that was the best of the small talk' exactly find now again， these numbers are old or take。

 you know， don't use it as a validation that your pet language is the best or the worst or your friends is the worst or whatevers what's the order of。

it's it's not ordered it's just a random selection okay。

 and all I did really was make sure that sort of the good ones were at the left and then over here it's kind of all just spread out。

Car分。but it's it's you know as you can see， it's it's a big spread and there's this this group and their these so which these by far yeah like an order of magnitude worse unless this benchmark than all the other languages which are already pretty bad I'd have to go look at the website。

 but I picked the best numbers for each particular implementation at the time。

 but like I said they're also its all in my the most。テスのデサイン。Yeah， so， I mean， this number is。

Highly suspect because the applications that are in the suite are not statistical in any and they don't rely。

 they don't leverage the power of like the statistical library at all because they don't do statistics so a lot of this is due to the fact that you know in real use you probably it would not feel this bad。

It would feel less bad。Because this is a sense of if you write imperative loopy code in just have bad it hits and it's really bad。

It's really bad， This is the our implementation basically。The only one that's compatible with itself。

But if even even if you， you know， you use the power。

 you're not going to get super high performance if you stay within the language。

 that the reason is widely use this because people call primitives。

That are expressed in C and Forranm and those run of course fast so there are bulk operations that are predefined run fast。

 but that's if you're writing a new piece of program，And it doesn't use one of those things。

This is where you're going to live right to live。We're not going to live down there now。I'm sorry。

 that nobody will no serious r user。你知道U承单的情方。Yeah， no， actually I looked into this。And in fact。

 if you look at the way it's used fairly widely， people will develop new stuff using our， you know。

 like a new technique for which there isn't a kernel implementation and then when they figure they've got something valuable then they recordcode it in CRC++ it's more like a。

Yeah， yeah。 and so what that's saying is， you know， it's painful。It's productive to begin with。

 but the performance is poor， but once you've got something you want， then when you recordcode it。

 you can get the performance，'s。performanceformance is not good。 Did anyone look to buy that。

I think there are MAla benchmarks but I'm not I didn't pull those out I don't think there are many different implementations go look at the website it's kind of fun to browse around there you can slice and dice the data in all sorts of different ways。

Anyway。Well， why is this？So I believe it's because the flow in building implementations historically is being kind of this。

You have some idea for a language， you build a PA， you build an AST interpreter。

 you fiddle with the semantics， you sort of get it to the point where you think you have a reasonable definition of your language and of course it's pretty slow as you've seen AST interpreters are pretty slow so then you go off and you start devising you know building a real VM usually in C orC+ plus you spend a lot of time implementing all the run time you might throw out the conservative col build one that's the exact things like that you know you get some adoption people start using it and as soon as they use it they say we love your language but it's really slow can you make it faster。

So then maybe you go off and do you know what we did in phase two of the exercises。

 divine a bikecode format， build a bikecode， interpreter all of that machinery。

 and as you see so it got faster， but it's still pretty bad。And then， you know。

 if you want real performance， you start doing what you've recently been doing。

 which is right a jet compiler， improve the garbage collector。

You're still a good wear off sea or Java at this point。

And if you want to set that last step we can get into that bottom band。

 well then you know you break out your wallet。You hire half a dozen or 10 or maybe 20 rocket scientists like Lars and burn some tens of millions of dollars in something that's pretty good。

 but you know the reality is，Most give up there because that's kind of where the knee the curve is right in difficulty。

 so it gets much harder at that point as you've seen。How hard here are some。

Estimates based on what I've observed son and oracle。In implementation， okay。

 so you start off with something like a blue book standard interpreter like the the interpreter you had and it's kind of。

 you know a couple of months work not that hard you can get something pretty decent。

When you get into a simple jet for a real language， you know Ph。

 I hope no one will dispute is not a real language。

 it doesn't have any of the complexity of real languages。But if you go down that path now。

 you're talking about a year's effort， maybe to do a decent jet that's maintainable。

The self system you know， gets you another， this is again， another logarithmic chart， you know。

 gets you another fat， several folds speed up。At the cost of maybe 10 exit effort。

And if you want to get that， asymptotically。Disappear in the performance then the effort kind of goes up without bound。

 my guess is hotspot the it's probably well over 10。Years of effortss。

It's probably in the hundrednds。食。Another way of looking at that is so that's where the scripting languages lie lines code。

hottpot， I think， is around 3 million。You can do sort of a decent。

 reasonable perform VM in a couple hundred thousand lines of C++。For a simple language。

But it gets it rapidly gets complex。So I think that's why we don't have a whole bunch of high performance Vs for these languages first there aren't a lot of people who can do this and second。

 who wants to explain all this effort word who's going to pay for all that effort。So。You know。

 the problem is each language needs its own implementation。

 that's the way it's been done historically that we don't really share much。

FromFrom one language to the other， you know， you can try doing the one language on top of another language is the Amtrak。

 stacking them up。But that's kind of mostly not proven very successful。

You either end up with something that doesn't perform well or has terrible complexity or isn't quite as compatible as the original implementation or some mixture of those things。

嗯。And if you go down that path， you can get。Sort of decent performance but absurd levels of complexity so if you look at J Rubi。

 which is what I'm somewhat familiar with J Ruby is the Ruby built on top of Java runs on top of a standard JVM the peak performance is pretty good it's quite a lot faster than the C interpreter that's available for Ruby sort of order 10 x not bad。

But if you compare it with the same code R and Express the Java running on the sameVN it's probably five to 10 x off that it's quite a long way off where you really think the performance should be。

 you know if you compare it with say a well the well tuned small top VMs of the past or the well tuned self VM。

 you it's way off that kind of level of performance。

 even though it's got a much more sophisticated VM underneath it。Something like hospital。

And what's more， it's massively complex because it's trying to work around all of the。

Assumptions of Java that are built into the underlying Java implementation。

 So the Jru is like a couple of million lines to Java code， it's big。Now。

 a fair amount of that is library， but there's also a fair amount of code in there that tries to。

In effect， to generate very special bikecode that's known to run reasonably well and not do it in the sort of straightforward and obvious manner。

So it has its own dynamic compiler generating bycode， for example。

 in addition to the one that's in the VM and that's。Signence something was not quite right。

It was also probably the biggest driving force between the biggest sort of semantic extension to the JM in recent history。

 which was the addition of the invoke dynamic bikeco。

 which unfortunately we didn't have time to go into。呃 before。

Invoke dynamic is a way of invoking kind of arbitrary lookup in the JVM。

 you can't do that at the Java level because it's not for Java it's been reused in the Lada stuff。

But it's really there for dynamic languages and so you know a lot of effort was put into specifying this and developing it and putting it at the J arm and the speed of it was very modest like you2 x at best。

Maybe less than that， I think。So it's still a long way off where you'd really like it to be。

And I have kind of a strawman argument for， you know， this is never going to work。

Which is you probably want to implement both static and dynamic languages。

So suppose you have a dynamic。The dynamically dynamic language and the static language and one of them you already have the high performance of the end and there's always going to be a mismatch between those two if you put a static language at the very base。

 well it won't have support for all the stuff we need to make dynamic languages go fast tagging。

Dynamic layouts and open ended dispatch and all of that hope dynamics is kind of a step in that direction from Java。

 but it's clear from。The history of invo dynamic there's a lot more on needed。

If you're going to run donate languages on top of a stock， JBM。Through the Java whitecode。

And if you do the other way， you end up with a similar mismatch that you don't have in the dynamic advantage of support for machine level types and detail table dispatch and stuff like that。

' dabbled with this in the South project we built a very early implementation of Java by transld Java bycode into self bycode。

And it was faster for its time， but that was before her hotpot and similar VMs appeared。And it' you。

 I don't think I'll ever a compete。With something like hot。So。

One of the problems here is that we don't reuse things and one of the difficulties is if you look at the high performance VMs that are out there。

 there're generally not very well modularized you don't have big pieces that you can just lift out and reuse somewhere else because the components tend to be deeply entangled with each other many have tried to put interfaces in and there's been some level of success in putting interfaces between parts of the VM but even now you're look at most of the high performance formss you get issues that cut across all of the different modules and if you're working on GC you have to something about the compiler does if you add some new barrier you have to go and change the compiler if you' add a layout。

 you have to go and change both， it tends to be very deeply entangled because sort of a holistic attempt to squeeze the last drop of performance out of the underlying machine and to do that really。

You have to know about everything you call just kind of close one from the other at least。

 if you can， no one's figured out。Optimizing compilation is really interesting because that tends to be the single most complex part of the VingM。

An optimizing compiler is sort of ferociously complex， even compared to the GCs that we've seen。

And they tend to be very language specific， but the funny part is that most of an optimizing compiler isn't language specific。

 most of what's on the inside is actually fairly language independent。

And so that interesting question is， if you took an optimizing compile， if you started with。

The core of the optimization framework and the IR， how would you get to？嗯。

A system in which you had a reusable language independent core with。Some language dependent parts。

 probably language dependent optimization。 You need front ends for each language youre going to implement。

You have to somehow optimize for the behaviors that you discovered at runtime because as we've seen。

 it's all the。The techniques here are all about runtime mechanisms and finding out behaviors that aren't manifest in the static code。

So you'd have to have some way of doing that in a way that was language specific and yet somehow reusable。

And then you know， you have to pick a language to write this stuff in what would that language look like is it C。

 I may imagine by now you're probably sick of C？And I'm guessing none of you are going to answer C as that language。

 what would it be if it's not seen？So I'm going to talk about for the rest of today。

Is one pass at this that we are making the Oracle labs。

 So we have a system that's been under development now for。3， four or four years， I think now。

Building on some of the earlier work that we did on things like vaccine。

And we have an approach that tries to address this。

produce a framework in which the bulk of the complexity can be reused from language to language。

But you can still write independent language front ends and give language semantics and get pretty good performance out of the whole thing。

 you know comparable to what you get if you spent all that time building。

A custom VM for that one language loan， so you know you've managed to money to avoid logos。

All this time， now you get the Oracle logo on slides， so this is like。

All our technology coming up but。Hopefully， it'll be interesting。So where do we start from？

Well we go back to AST interpretation， you remember this slide？Takeaking literally from me。

First slide deck。Two things about ITs is they're slow to interpret。

 but they're easy to reason than writing。We have right and reason。

So that would be a great way of specifying。A language is semantics。

 if you could write an AST interpret if I have it run fast， that will be an ideal situation。

So what do we need？To make something run fast。And specifically， you know。

 we're assuming that to make it run fast， we need to compile it。

 we need to generate good code for constructs that are in the original program。

And so what do we need to do that， we need obviously with the program itself because you can't compile an interpreter and get good performance。

 you need to start with the original program somehow。

You need to have an understanding of what each element of the language that that program expresses means in an executable form。

And you need to combine these things， some elements of the program with their semantics。

And then generate code。课阵。So this is just， how do we get code？So remember the simple ST interpreter。

we started with it was just interpreting expressions。

 this is the lifted from that slide so we've got the dispatch on an AST node and we're just going to evaluate it based on what kind of noded we've got and we recurse down the tree So we how would we turn that into a compiler Well。

 suppose we have our favorite expression from early on。And we have our interpreter here。

 what we can do is we can do an abstract interpretation of this。

Executing the parts of the structure that are given by the fact that we have an a known program fragment right and we know we're trying to compile this program fragment so we know the tree share。

So we can do the tree walk a compile time。But we can't evaluate all of the expressions at compile time because these are dynamic things dependent on our own time values。

 but we can pull them out and combine them to make a compileilable expression so there's a sketch。

 you know， let's start with the assignment we're assigning to be。

We can take the definition of an assignment， which is here just pulling out。

Evaluating the right hand side and assigning to a corresponding variable， well。

 we know the variables so we can fill that pie。But we are't on the right hand side。

 the way we do that now is we abstractly interpret down here so we know the structure of the tree and we can recurse down。

So now we look at。The right hand side。We see that there's a plus with two further a recursive evaluations of the tree parts so we can fill the plus in and then recursse down and so on we work our way down the tree。

 pulling out the piece of code， filling in the details as far as we can。Consts are just constants。

 variable becomes a variable lookup。Until we have something which is pretty good code for the original expression part。

 the interpretation is gone and we've got。嗯。We've got the semantics as we would want to compile it。

It's not a new idea that's been around a long time。

The idea is to take a language interpreter in a thing called a partial evaluator。

 which evaluates what it can based on the structure that's known at the time of evaluation and leaves the remainder for evaluation letter and that's one way of taking an interpreter and making it into a compiler you combine the interpreter with a partial evaluator when you get a compiler and to compile a different language we just need a new interpreter in the scheme we don't need a compiler for the original for the guest language we need a compiler for the language that the interpreter is written a partial evaluator for the language。

The interpreter is written。 So that's been known， you know， since the 70s。

 there's a paper from 1971 by a Japanese professor Fuji Mu who who。

Came up with a formalism that describes that it's been around a long time。

 but it actually hasn't resulted in particularly efficient。Language implementations。

 certainly not dynamic language implementations。 Well why is that the problem is when we look at partially evaluating a dynamic language interpreter life is much worse so the previous thing was very simple because we had only one type when we get into dynamic stamps and tagging and all of that stuff。

 So this is the code lifted from the slide when we had a tankgged。ASme for the stack。Now。

 if we imagine substituting that end on one side of a plus。You know。

 and substitutes using something else on the other side of the plus。

 the resulting code is not going to be much more efficient than it was when we were interpret English're going to remove the interpretation loop。

 but that's more or less about all。What we need is some way of pruning out the part of this that isn't useful so what we need is to generate good code for a user program and that requires what we had before the semantics。

And。The user program， but we also need。To be able to gather information at runtime as to what the program is actually doing。

 use that as the predictor of the future， and use that to optimize how we select from the interpreter what goes into the compile code。

So we're going to combine the semantics。Of each element of the program。

In the same way that I just showed you， but we're also going to drive the way we combine it。

Based on usage information gathered set through an interpretation warm up period。And。

That's how we're going to generate。The the code that we're going to compile and we're going to use the deoptimization trick to back out when we get that wrong。

 so deoptimization is the big hammer。Toge sell。So the AST interpreter gives us the semantics of each language element by definition。

 because that's what its job is。We do profiling and specialization within the AST to gather。嗯。

Hotpot type information that's needed for the pro generation。 and then the final stage。

The partial evaluator slash compiler is something that you looks， not just at the interpreter code。

But it also looks at the structure of the AST， the original program to drive cogen。

 to guide how it's going to generate code。Combines all of those together。Okay。

 so how do we do the specialization， what's that all？嗯。

We want to gather profile days as you' ASD interpretation。

And we want to be able to get type information。But it would be good if we did that without having the explicit multiware type dispatch in every interpretation we rely on。

这吧。We rely on history to predict the future So imagine。

There's a little piece of pseudo code for an ad operation in a dynamic language。

 So in this ad operation， we can add integers， we can， we can put a plus between strings。

 which can catate the strings or the some user defined thing that we can call。

 And this is how you write it in a conventional interpreter。

 You did the explicit type dispatch between them。 But what we're going to do is we're going to。

Break that node with this associated semantics into different states。

 one for the state where we're doing integer edition。

 one for what we're doing string addition and one for the generic。And we're going to replace。

This generic example， with a specific example that we've discovered to be the appropriate one when we've run this particular node in the past。

 we're going to rely on that。And optimize the node to node communication to make the interpretation quicker and there's a side effect gather the type information we need。

So imagine again this。We have this language， it has the two types and string and it has some generic case for this edition。

 and we have the state work that we start in which is we see an addition though。

 but we've never executed so we don't know what state is。

What we're going to do is when we execute that for the first time， if the arguments ends。

 we're going to specialize it into it as an imped。We see string arguments will specialize it as a string incatenation。

And if we ever are in one of these sets and we see the other one。It's a mixed type。

 and we're going to fall back to the generic case and say， okay， it's neither in nor strings。

 it's both so we're。We have to cope with vote。How does this work in the tree itself？

So here's the same expression I had earlier。Asume our is storing an integer。

So because that's already been assigned to it knows it has an integer and the integers of course know their integers。

 so they are blue， but the interior nodes having never been executed， they're light gray。

 which means uninitialized pump special。Okay， so an eval comes into this tree to evaluate itself。

The heveval， of course， gets passed down the tree。It evaluates the two。

 which gives us a box or a tanked， a generic representation of two back。

It evaluates the A on the right， and that gives us a similar boxed or tagged。

Representation of the value of that variable back and now the multiplication note can say， oh。

 I got integers。From both of my descendants， which means I'm new integer multiplication。

 andm going to change myself into a multiplication that assumes now in future。

 I'm always going to do integer multiplication I'll optimize that here。

And I'll pessimize the other cases。Okay， that then returns its result back and plus does the same thing now。

 it gets the six it got back and the one it gets back from here and it says， oh。Those were integers。

 I'm going to be an integer audit now from now on。And it returns its number。

Now the next time we come in and execute here。Soon we get the same top level message coming in。

 e as held。The integer plus node says now， oh， I'm a plus node， so I'm an integer plus node。

 so my children are expecting I'm expecting them to give me insight。

 so I'm going to do a different evaluation operation now which assumes the type is an integer。

So it can give it the back unboxed， it doesn't have to tag it or box it。

 it can just give me a rolling back because that's what I'm expecting。

If it turns out to be something else， it has to signal out of band somehow that that assumption was wrong。

😡，But assume that all assumptions are correct， it similarly passes on the evalent to its children。

 the two can just return an unboxed to now。The air can return an unboxed thread。

The multiplication just does a straightforward forward into your multiplication and returns that and so on。

And we've done the evaluation of the expression now。

Using new additional conversion operations or all the intermediate stage right。

 we're not boxing and unboxing in every or tagging and untagging。

We're just patent trucking in regular ros。So every time we do this now， it should be faster。

 plus we know by the fact that this is colored blue。

 the fact that we've never seen anything other dominantminant。question，Yeah。

 where are the guides inserted， Where do you check if it I show the next one。 So assume。

We go off and we do something else and in the meantime we assign a string to A right so now a is no longer an integer。

We fire an every vow message。 This guy says oh， I'm an in plus do any vin that guy says I'm an int multiply do any vin The two responds Okidoki and gives the two back。

 but the a now says。Can't do that。I'm notアレ。It has to respond out of band， so for example。

 it throws an exception maybe and says， I have an ex， it's not an end， do something different。

When this guy handles the exception， what he does is he replaces himself now。With a generic node。

 he says， okay， I used to be an ink node， but I've seen something that's not an ink。

 I can't do it stuff anymore， I'm going to replace this node with a generic node that's going to handle it in the standing box that attack man。

And it replies with the unexpected result back because remember the plus asks for an int and it can't give it an in back because let's assume now in our language。

 two times the string x is x followed by x。Silly language or whatever。

So it replies with the exception and that a plus has to similarly convert itself to the generic case。

Finish off its evaluation。Note that when it is asked for this guy， asked not for an inn。

 but for a generic thing。And return the box example。

And then we have a case where we know from the colors of the nodes that this has seen both string in it。

So， in。Sudocode the way this looks is that you node class。Every node has to know it's parenting。

Because it has to be able to replace itself from the tree so the tree is fully connected up and down。

A binary node then is going to have two subexpressions for the left and right child。

And it's going to respond to three different。Eval requests， one， which is the generic eval。

 evaluate yourself and give me back some kind of box or tagged representation of the result。

The one that says。Please evaluate yourself on the assumption you're an integer and give me back an in。

And if you can't give me an end， then tell me by throwing an exception and similarly for string。Yes。

And then。We're going to have subts of the add node for each of the different states that we're in。

 So the only initialized one。Is going to just call its children and figure out how to replace itself with the appropriate type。

The integer're at now is going to implement the evalent。And the exception。

 But if it gets asked the generic thing， it will do that too， I've delighted that。

The string implements the string contaminatation and the generic wonders whatever is the generic case you know calls the user find plus or whatever is the language specifies What we're going to do now is instantiate the app node。

With the uninitialized one， when it seesNs， it's going to replace itself with the inad when that sees a string it's going to replace itself with the generic one and by that way。

 the tree will color itself with the types that it's seen of the union。As it see multiple times。

So here's what the uninitialized ad node。Eval would look like you know go evaluate the left side or e right side if we have two integers on those。

 then we're going to replace ourselves with an ink， if we have two strings。

 we're going to replace ourselves with a string， otherwise we replace ourselves with a generic same you can really allow to have you know two times a string here and that's legal that' the replacement。

So each node has to have。A state diagram that works its way through this internal type system transitioning。

From one state to another。 and when it makes the transition。Said the multiplier here。

 when it specializes itself to the in case， it makes a new node of the appropriate class。

 the intab node and that gets spliced into the tree now。

Here's what the code for evalent in the int adner looks like。

So this is the case where we're going to do the left and the right evaluations。

 but we're going to catch an exception of either of those。Doesn't。

Give us an int so because remember Evalin， the signature is give me back an in it can't give you back anything else in the normal functional return。

 anything else has to be communicated and out band using the exception。

So this is going to throw an exception if it can't give me an end。And I'll rewrite myself。

By evaluating the right hand side。I'm putting that in there。

 but this is a genericval now it's not an evalent。Similarly， when I do the right side。

 well I already have the left side that stored it in air I can pass that on to the rewrite。

 but I'll have to do a rewrite of the node if I get something different and if I don't get。

Either of those， then I can do the addition。And the important part here is。

When this is compiled and speculated on all that's left is the eval， the EVval and the ad。

 everything else。The pile is going to remove。In was speculation。So the ASTs。

Imagine now we have an AST for a whole method。Connecting all the expressions and the statements。

Do me to give you a call when。When I get to West Palm， sureba。我去。そです。呃，O。我问白。可 on here。3，6。Okay。

 yeah， we took a break after the section and we all contest that。嗯。

So we have an AST for something like a method。That's connected connects all of these mealss with us specializes。

We're going to decorate the node。With counters， the accounting。

 whenever we interpret through a certain。And that's going to give us the profile information。

 the hotness of the tree。When we get a hot node， typically a hot method。

 we're going to invoke a compiler， the compiler is going to walk the AST。

 but the compiler knows about AST， it's not a compiler of the source of the interpreter。

 it's the compiler of the source of the interpreter and the AST so the tree structure is known about the by the compiler so it walks the AST。

And it can connect each AST node to the corresponding Eval or specialized Eval for that node。

 and it knows the types of each node， you can see that because it sees the specializations and it uses that。

Profile information to guide the inlining。 So when it sees an int a node。

 it's going to inline the evalance of the children。

 It's not mean that inline any other evals because it knows that guys been executed again because the only one that matters is the in。

childrenildren。And it's going to do that as far as it can through the treatment。Where。

Exceptions get thrown， so where the code is that does a test， a type test say the actual leaf。

So when the AA， the lookup of the variable has been compiled and specialized。

That will have to do a type test to say， well， do I really contain an in？

If it doesn't contain and it grows the exception and the exception results in the whole tree being deoptimized and reevaluated in June。

So the compilation here's an example， is the code for the intab node。

Suppose we're compiling this tree startinging with a river。When the compiler sees that， it says。

 okay， I got a plus， which means I'm going to evaluate this method because it's a blue plus。

 it's the N plus。When it evaluates， it says， okay， this is an ink plus。

 I'm going to discard all of this boilerp around it。

 that's just going to be stuff that gets the triggers or response to de optimizationim。

And just get left with the evaluations of the children， and then when it goes through the children。

 it'll go through their code。And get successively build up the expressions in a tree form just the same way as I showed you earlier。

When it combines all of that lot， the tri should have been removed， you end up with， you know， two。

 get B or do multiply。Add an ad。Okay。That's the basic idea。Questions。That like。营销还。いてや。ll be right。

So that says。The evaluation of the left child did not return an end， it could not。

It gave us back the result it could return that's boxed inside this exception。

What I need to do is I need to rewrite myself so you think of this as this dot rewrite on the node。

The node is going to。Cologown itself into some other type based on the。

Type of the result they got here and the type of the result it gets there。

It's going to clone itself into the appropriate specific subflor of in this case， add。

Appropriate for those types and it's going to splice itself into the tree here。

 replacing I sorry in here， replacing these links with links to the new one。

So that's what triggers the rewrite of the node in the tree with a different specialization。

And similarly， for this game。有。And the throw is because we have to communicate that result up to our caller because we can't return anything。

Yeah， so I'm guessing here the framework is monitoring the profiling information and then regenerating code with evalent or。

E string based on I'll get to that that， it's actually all generated ahead of time。

All of these variants are generated ahead of time there's no level at this level it's not generated at runtime。

 it's generated at built time and the dynamic compiler is selecting paths。Through this code。

To generate machine code for and everything that's off that path is a de optimizationtim。

' that's where we're headed， but I'll go through that the reason I asked this question was would it't make sense to instead of having code that。

 for example， does that or Evalin， you have a generic Eva。

 but use you use a fancy glass hierarchy and have dynamic dispatch。

 but because the code is being cloned the inline cation of the generated code itself you could do that。

 but this is more direct， it says exactly I know I need an in， I'm just going to go for an end。

That's the assumption in the in out。So it doesn't have to do a dispatch。

 it's encoded that assumption so it can now rely on that assumption in the way it operates。

And that's useful because when they。Partial evalu partially evaluates this。

 it doesn't have to do another level of partial evaluation to take a generic eval here。You know。

 examine an inline cache and resolve all of that you could just look at the source and say oh this is name I'm just going to call the info so sort of it's an extra level of indirection which wouldn't do any harm。

 but it would cost you a little bit of performance and complexity which is why it's not Yeah think you could then you could lift the profiling part and you wouldn't have to have the framework the profiling the run name itself would be doing the profiling。

The run time is doing the profiling anyway you don't write this this is this is just to give you an idea of what's at the bottom you're not going to write this because as you can see if you imagine implementing the plus this way we've got four versions of this with all this boilerp。

 you know you'd go mad typing in the code right've got。

Masses of code here for not much functionality。It's really just a big stamp chain。Okay。

 so how are we going to implement this？We've got to implement it in a language that can describe machine times because that's what we want to talk about in our implementation。

 we want to map。The original。Language into some kind of machine types that we know are efficiently handled。

We want to have some way of having exception paths for unexpected times。

 I mean I sketch this out in Java， but it doesn't have to be Java it could be something else。

 but you do need this out to banned communication to communicate the fact when you've got a tight mismatch。

You need something that hopefully is going to generate efficient code for you at the end。

And you need the tools。Which' I'm going to describe for the next section。

 which save you from having to generate write all of this boilerp stuff。

 you write something much more high level and declarative and it's going to generate all this stuff。

Well， you know there isn't really an existing language that does all of this right。

 it's what we're really looking for is a DSL for building VMZ or building interpreters。

But we've got by a series of， you know， happy coincidences a way of doing this without actually having to invent a completely new。

Language and build a tool chain around it， it turns out。If you take Java。

You add the standard Java annotation mechanism， use that。

You add compiler directs so remember we're implementing our own compiler so we can ascribe any semantics we like any element of this program。

 we don't have to follow standard Java semantic。 We can do something different and in particular。

 we can come up with things which tell the compiler stuff。But when you run them into normal VM。

 they're noOs so we can add compiler directors， so the combinations of all of those three it turns out is sufficient to get us what we want without implementing a whole new language。

 but you could， if you wanted， implement a whole new language or you could take this DSL and you could embed it in some of the language that's capable of having these DSLs embeddedbed in it and use that instead。

So the resulting artifact is called the Tffle DSL， and one of the things you going to be reading in the next week is the paper describing this DSM。

Now， I think I probably need to who's familiar with annotations in Java， I'm guessing okay。

 sprinkling but not many， all right， so you don't need to know much because you're not implementing the annotations you're just using them。

But the key thing is that since， I think 1。5 or 1。6。

 there's this annotation mechanism available where before certain language elements。

Mainly classes and methods。You can put one of these annotations that begins with an act。

And the annotation has a name and it has optionally some parameterized list and the stuff that you can put in the parameterized list it's pretty flexible。

 there's all kinds of Java expressions that you can put in there。

And you put this in and your standard compiler says， you know， I don't know what that is。

 I'm just going to stick it in the AST and ignore it but。If you run Java C。With。An optional flag。

Called an annotation processor， which is a Java program you can write。

The annotation processor is called in the middle of the compile and it says， okay I got the tree。

 here's the API， you go do stuff with it and the annotation processor can then go in。

 look at these annotations， look at Java C's syntax tree。

 generate some more tree and hand it all back to Java C and say， okay， I'm done， go compile this。

And so those annotations can turn into kind of arbitrary stuff that's entirely under your control and that's what the system relies on。

So， the flow。When we're using truffle is we start with。Java code with these known specifications。

We use the annotations and there's an annotation processor available for this。We call Java C。

 whether it's the standard command line thing or one embedded in an IDH。

 you're all do the same stuff because this is all part of the standard Java definition。

So that compiler startss compiling yourself， it comes across the annotations。

 assuming you've told it to use the annotation process， it's going to call the annotation process。

That's going to look at all your annotations， it's going to generate some source code and hand it off here and the compiler can compile that to out pops。

The thing that you're going to run。So all of this processing is done at build time。

 none of it is taking place while your interpreter is running nothing。It's all done at build time。

In this particular system， it actually generates source。

And it'll drop that source into you know files and you can look at the source and in fact。

 you're going have to look at the source if you do single stepping because that's what you're going to see。

 you're not going to see your code。You're going to see the output of the imation process。

Which has all these extra classes and nodes and transitions that you specify。

 but you're going directly write。Okay， so on to the nitty gritty。

So you'll find where you come to do this， there's a package hierarchy under Comda oracle truffle。

 which contains the framework and the APIs。Noode is the base of all of this。

 so you when you inherit when you define your AST you have to inherit directly or indirectly from node。

 that's what the compiler is looking for when ar is to figure out what your AST is it wants instances of node。

Or some classes thereof。So you inherit from that。Notode provides some。

Structure for you and some utility stuff。So it knows how to manage tree structures。

 it knows how to navigate up and down the hierarchy， for example， a parent is defined in node。

You don't have to define that。It knows how to do copying and a replacement implements the rewrite methods and all of that stuff and it also gives a placeholder for linking nodes in the tree back to the original source text that they were derived from so when you create a node you can say okay。

 this represents you know lines four to five of file blur。

 that's where the original source was and the tool chain after that can use that to show you。

The award award when it means to。So you inherit and you use all of that stuff。

 you make subuse that define the end the bay of your your specific node。And when you build an AST。

 there's a distinguished node， which is at the top of the AST called a root now。

And that has to be a subclass of a root node， but root node provides extra functionality above and beyond node。

 which we're getting。The next thing you do is you specify in Java。

The implementation types for your guest language， so how are you all going to represent the data？

In your program and you use the sanitation type system。

hi you give the name of a couple of you put lots of classes in here and the order is important as you'll see it matches in a certain order。

So these are the things that are going to implement the values within your interpreter。

The representation of your guest language。And you can also in along with this。

 specify checks and casts that can。Be used by the DSL processors to say。

 is this of one of these types or how do I coerce from one type to another， so for example。

 if your language has automatic conversions from in to strings you can supply a conversion。

That matches that and the annotation processor will when it needs a string， if all this season in。

 it will call your conversion thing to do the conversion。This time system， you put this in a file。

 you typically stick it in a job file and just import it into all of the yellow places that you're going to need。

There's a slightly more complex mechanism if that turns out to be inconveient but I'm not going to go into that detail or by the way。

 the thing I should say is the example code this far the stuff that I gave you was not using the actual names。

 the names were simplified so don't start lifting code from the earlier slides and think it's going to work but from here on out it should be fairly accurate。

Okay， so you've got a bunch of nodes， you've built a hierarchy representing RAT。

 you need structuring RA AST， you have to describe。The， the the tree structure。

 and the way you do that is in a simple way as you would， in any object or into language。

 you have members that are node。Tpe members of。The particular node， so for example。

 if I have been defining a node for binary operators， might obviously need a left and right。

 each of those is going to be some kind expression。

But to make the DSL processor know that these are children nodes。

 you stick this annotation in front of an at child， and that says。When you're navigating this AST。

 these are the things you go down to find more AST if you put other stuff in here which you can do。

 it won't try processing those， it will try inlining through so when it sees a child it's going to say。

 I see a child that should have valve methods or the equivalent as you'll see those are the things I'm going to look up and try in line match types and process and do all the state transitions。

 everything else it's just stuff that you need to the nerve。

There's a slightly different form in the case where。

The DSL process is going to generate everything that you need。

 so if you don't actually need to mention in many cases you can get away with just writing declarative pieces of DSL or no methods in the class they're all generated。

That's the case， and you can use a slightly simple form， it generates the fields。

 it generates the guesses， it generates the setters， the types， the coercions， everything。so啊。

That's just just you'll probably see that in the example， which is why I mentioned。Okay。

 so how do you specify specializations？So you don't have to write any of the subclass definitions at all。

 what you do is you put in the methods。For the node specific behavior that you break them out by type。

 So an a node is going to have。The integer pair and the integer pair is going to just look like an method detects two ins and returns an in。

And it does the obvious thing here， and it's proceedd with the annotation。

 specialization and that what that says it's going to。

Take this and build that graph and all the transitions and insert this as one of the nodes in the graph。

The specialization for string is going to be a little bit more complex。So when you call I have。

Both of the operas have to begins， and it will only call a specialization when both are end。

 but you can provide your own。Guard for a specialization。

 in this case we have to because let's assume in this language。

We're allowed to do pulse between string and anything， and it will convert the other guy to a string。

Before it does the concatenations， so in this case we have to provide our own guard here and the guard is just a fragment of Java and heres the corresponding method for what it's going to execute。

 which just says， okay， is one or the other restraint if either of them is a string。

 this is an eligible specialization。So this method will only get cold。

Because this guard has returned to true。And when it does get cold， everything's boxed up。

 it's in the generic form， right， and it's going to do。

Two string on the left and the right and do this strong concatenation。

One interesting trick here and we'll go into some of these a bit later is you can give hints to the compiler as to where to stop inlining。

Strink concatenation probably isn't that performance critical。

 you probably don't want to bother inlining through this， you want to call it。

 but you don't want to inline it and so you can put this annotation called truffle boundaryary before it and that at runtime when it's compiling it will get to this and say okay。

 I'm not going to inline this I'm just going to call it。So you go through this。

 try and imagine doing this for a whole bunch of stuff。

And you're going to have an it's going to spit out a big G Javava code。

 which is going to be an interpreter for your language with all of these transitions and specializations in it。

You can take that and you can run it on a stock Java VM and it will run just fine。Dog slow。

 but it will do the right thing。If you run it on the special VM with the special compile aim。

It's going to look into all of these specializations and start doing。

Compilation knowledgeable about the structure， so the process is going to take your thing。

 expand it all out to generate all sub classes and everything。And then when the compiler runs。

 it's going to look at all of that information as it's gathered at runtime。

So the processing takes the classes you saw and fills them in with the little template for the things that you specified in a well defined manner。

Now one particular trick here is how to handle。Frames in the language that's being interpreted。

Normally when you build an interpreter， you make a structure typically in your see。

 if you're doing a C interpreter and you stick those things in the heap and you lick them together。

And that's how you implement the interpreted languages stack。And you do just the same here。

But there's a trick。Your frames should be。When possible， virtual F。

 which is another class that's provided by the framework。

And a virtual frame when you program it in Java just looks like a Java object。

But if you follow the rules with what you do with virtual friends。

 you don't store references to them in the heatap， you don't let them escape from methods。

Then when the compiler comes to compile your interpreter combined with the original IT。

 it's going to say，H， this is a virtual frame， it can just become a frame on the stack。

And it will optimize it all the way。Pull out all of the constituent components and just stick those in registers on the stack of where everythings is the appropriate place。

There are some other flashes of frame， the most notable one is a materialized frame which has exactly the same interface as virtual frame。

 but a little bit more， a material materialized frames are real objects when program executeds so those are eated and you can convert from one to the other and back again using the API。

But you know， as soon as you're working with a materialized frame now。

 it's slower because it's an object， it's not just a stack frame it's been optimized by。

And then there's a thing called a frame descriptor which is generated during the passing。

 which sort of says how the frame is filled in from the source language。

And that's what the system uses is to work。To do its optimization and de optimization。

One of the important things here is you never make these， you know。

 you don't see a new virtual frame anyway， you always get them from the system。

 usually passed in as a parameter。You don't subclass them。

 you don't mess with them because the compiler has to know it's exactly what。

It thinks it is if it's going to optimize it， if it's off。

 then it's going to say' going to know about those， can't do anything for you。

I mentioned the root node。So the root nodeed is important because it's the entry point for the evaluation of NAST。

 so you have to have some way of going from normal Java code。Into。What looks like normal Java COVID？

When the truffle is running and compiling， it's not Java code anymore it's machine code it's been generated by the partial evaluator and so there's a transition there and that's what Ro node provides you with the way of making that transition。

So when you have a root node， you can say to that。From the realtime。

 make a thing called a cold target。And the call target is now just callable。

 you call it and suddenly now you're executing and the interprets are associated with that。嗯。

And you should implement this execute method which is past the virtual frame。

 you know the system will make the virtual frame pass it to you。

 but when you're compiled it's really just a friend。How do you do control flow。

 exactly the same as you would in a normal AST interpret' written in Java。

 so you implement it using Java control flow where you can and where you can't。

 you use things like exceptions。And then what Grl is going to do， which is the underlying compiler。

 when it compiles an entire AST， if there's a throw and a catch point internal to the AST。

 it's just going to connect those with a jump。There will be no actual exception object made。

It won't do all in the wrap maybe equal'll just hand it with a control flow in the associated value。

咁望似。So here's an example， this is how we might implement an if node。So an if node， you know。

 assume I have a statement node class， the if node has three children， one for the expression。

 one for the then part， one for the else part。And to execute this。

 this is a type return return type void because it doesn't return a result and' given the frame。

I execute the condition part on the assumption it's going to return to Google and that's the way this language is defined。

 if it's true， then I call the then part， if it's false。

 then if there's an L' part I call a very straightforward direct sort of no messing amount。

When you want to invoke a function。Then you have to pull out， say the function is the root of a tree。

 you have to pull out the coal target from that。From that node and call it。

And you want to do that in two stages， the first is sort of building and binding the coal target to the coal side。

So let's assume for the moment our a language just has direct function calls， you see an F。

 it's calling an F， there's no dispatchching between that's the simple case。

 we'll deal with a dispatch case。Later， so we've got an app and we want to call it。

 so we make a thing called a direct call node。Out of our root node。

 we pull out this call target and we make call mode。

 direct call node out of that and we keep it somewhere。When we want to call it。

 we need to evaluate the arguments to the call and then pass them to to the thing in the call。

 So that is a common piece curve to do with that argument evaluation。 Let's start with a second line。

 and this isn't just normal Java I'm making an object to ring。

With a length that matches the number of argument nodes in the call node that I' aim。

 so syntactically， you your call has some number of children for each of the arguments and you know that length。

Making an array of that and storing that。In the variable arguments and then I'm iterating over each of those things to those note trees。

 I'm executing as if I were interpreting that thing calling execute generic and the results going back in the array。

 and then I called call node passing in the frame that I had from outside and the argument array。

The couple of things you want to do to make truffle really know what you're trying to get at here is firstly assert for the compiler that this length。

Is a constant。就咩啊。Because then it will do a bit more optimization And then if you see explode loop。

 which is I think you have to put before the method as an annotation。

 the compiler will see this loop in this content and say， oh。

 I know exactly how many times I need to enroll this loop and it will enroll it for you so that all this this actually doesn't become a loop it just becomes direct evaluation of the children that all get in line and。

So there's no loop there in the end before it called us the actual call invocation。

Suppose you want to implement a return statement well return has a classical return has non local flow of control。

You have to do something different in an AS C interpreter。

 Then you do it using the obvious technique using， you know， what we saw weeks ago using exceptions。

 So you build a subclass of control flow exception called， you know， whatever you like。

 return exception that can buck up your result。And when you execute the return note in a statement。

hello。All that does is throw that exception。Stuffing the result in there， when it's handled。

 say in the evaluation of the function body， that will have the handler that catches the return exception and just returns through the function。

When in this case， it's just retain the value that was supplied in the return node。And as I said。

 when this is all processed at runtime by the compiler。All this code will just turn into a jump。

With the value in our register。Yes， you talking about for their frames。NotSpial with。

If you're implementing your target language， all it has。Language staff。It's yes。政治感。

Do we in the straightforward where you would with an EST without doing？

Don't build them explicit tank。O。Let's take a break。

It's a good point to take a break and then I'll go into some of the tricks for making this different task。

A sense of the things that you have to write as inputs of truffle。

 talk a little bit now about what's actually going on。

Under the hood and how you can guide that to generate good code。

There isn't really time to cover everything you'll need to do a full fie。

 so well I'll get to that in a while and we're going to phase it。

One thing I didn't talk about though was if you imagine this specialization going on。

 imagine each of these circles as a method。And the arcs， black and the red arc。

 those are all cold between methods between STTs。When we're interpreting with and specialize these nodes that are types that we observe。

But what happens in the case where we have？A node。A method AST that's called from different places with different parameter types right so in this case we have you know blue types which might be integers and in this case we have string types and this thing is some kind of generic method that can handle both cases。

Well the specialization， the downside of the specialization implemented naively would be that this guy would always be the generic case because it would be specialized first for the first call and then it would get。

Called by the other guy and at that point he would go， you know， I'm both， so I have to be generic。

And that would be a performance problem， but in fact， what the framework does。

Is because it's counting calls in the profile and it will detect the case where you have a frequent call so the red here indicates this is much more frequent than the other one so this is the hot one。

Calling something that's turned into a generic  noded， and it will take that AST。

 and it will clone it。Unspecialized， so it will reset this guide to uninitialized。

 it will clone it over here as uninitialized。And include it directly。

 it some kind of private tree in lined copy of the tree。And so this one now。

 when it calls it through this path could do its own specialization。

 with that being polluted by the types that are coming through there？So this is。

 there are only a couple of things that are going on at the truffle level to do optimization。

 but this is an important one because it means that you can get type information。

That's specific to a particular call path through the graph。

And that you're not blending in all of the types from all the other paths。

 even though they're very infrequent。Okay， so。Once they。Once you've got all this stuff。

You theres a big ball of Java code and you can run it， as I said on NVM。

But if you run it on the Grian。That's basically a version of hotspot with the grail compiler rings。

And the Gl itself is written in Java and it just runs as a Java program on the Gl PM。

 but hottspot about two years ago was extended to have an open compiler interface。

 so basically what you can do is you can write a compiler in Java。For Javava。

And if you register it through the interface， the VM will call your compiler。

To compile code and your compiler can install code into hotspots codeCash。

Not something we want the average application programmer to do。

But useful for this particular technique so this compiler interface is inside there's at least one compiler there mimics it which is the growl compiler now hotspot still has its other compilers inside and that's what's used to compile Grl when you start up。

Because when you start running， you just have Java bikecode and something has to compile light。

 you can't compile itself。就诶诶。It has a couple of compilers but you can add add your own。

And that's what we did。so诶。Your AST starts running。

 hotspots execution mechanisms are running the Java code in truffle。

The Java code has embedded counters， counting things。 eventually one of those counters。

Csses a threshold and it callss off to the side and it says， oh。

 I want to be compiled now and that's where gral kicks in and it's truffle motor ground can also just compile Str。

But in this case， you need kind of the extension。That knows about truffle structure and so gral kicks in knowing it's a truffle compilation。

And at that point， it says， okay， I'm going to assume that the AST is stable。

 that you've been interpreting long enough that the types are stabilized。

 that everything is ready to have a good code generated with the penalty that if something changes later。

 we're going to have to deoptimize and regenerate code and we'll interpret for a while to get the type of information back in。

So the thresholds are set such that this is likely to be true。

So it will then start walking the AST and doing things like looking at the child fields in the nodes to understand the structure。

 looking for the execute methods that are in those three nodes and doing this aggressive inlining through the execute methods guided by the type structure of the AST。

嗯。Also in the trade， there are counters and probability values for things like branches and type information for dispatches。

 which you can to use to optimize and make decisions as to have generates code and some of these you can influence。

 you can put things in specifically to help guide。The conclusion。But by default。

 it does a sort of an OK gel on the compilation。So the compiler inlines you know。

 super hyper aggressive through the tree structure， you know， basically inlining everything it can。

And you know， you might have to stop it from inlining it using various directives without some of those on the slide because there are some things that you know once you get into code which is extremely cold or bulky。

 you don't want the inline， you just want to call it right if you're calling as I said。

 you know Java's print method， you don't want to inline print and all the international internationalization tables and all of that stuff into you know hello world。

 you want to just call that。So， so in certain places。

 it's useful to say don't in line anymore also as you're writing the implementation of a particular operation。

 if you break it out into。A branch with a fast path and a slow path。

 you can see this is the fast path。In line through here， this is the slow path。

Don't inline through here or this is the slow path。 don't even generate code here。

 just the optimize if you go down this path and you'll see how to do that。

So the compiler will take all that stuff， all of directs， all the tree。

 all the huge inlining it does。And then it does optimization on this massive tree structure that's re。

 so it's by virtually inlining all of the dispatch between the nodes it's gone because that's being done at compile time。

 right this tree structure。And the particular shape of the tree is dependent on your AST。

 and that's known at compile times， so that all disappeared be。

The virtual frames all disappear and just become snack frames。And the exceptions。

 if they're within a compilation， you all just disappear and become branches or de optimizations。

 depending on the frequency。There is a tool that can help you see this。

Called ideal ideal graph visualizer in the bibliography。

 I've got a pointer to a YouTube video where they're used of IGV。

 This is kind of more for curiosity than anything。 I hope you don't find you need this。

Because it takes a certain amount of practice to know what you're looking at from this。

 The tutorials pretty good explaining it， but。嗯。When you get into nontrivi examples， you know。

 you'll have a screen， this size is looking at a tree that's you know。

 much bigger than your screen and it will become daunting to wander through it。

Unless you're very need to experience with that， but hopefully you won't need to do that。

 where's your question。嗯。The only performance downfall I can see if you're too aggressive in。23。

How problem。Well， actually， if it gets too big， the compiler。Starts throwing up its hands and saying。

 you know， because there are some out and parts of the compilation that I don't think are strictly linear。

And at some point it will go， is too big， I can't handle this。You know， I'll just give up。

 which is not good because then you'll keep into over10。Also blowing out your own cash。

So like there was a。可能哋未升埋去。AW ago， there was a paper where they showed that eye catch misss were the bottleneck and like oil TV。

Because they because I mean， commercial ones because if you look at like the ones you see in the university。

 they're like。Maybe 10，20，000 lines of code or something。

 and you look at a commercial and it's like 10 million lines of code。So it's kind of one loop。

Yeah the straight one。Is that I catch this。Okay。I don't think you'll get。

 I think the compilations will fail long before you reach that point。

 but that's also bad because it means you won't be compiling and you'll just be interpreting and things will be very slowlu。

Of your interpreter will be compiled by a hotspot， but that's not the same thing as having the interpreter partially evaluated by grant。

Your head can start hosing the think of all the levels。Compation interpretation here actually。

So what level of preparation？isakSo Ra is taking your AST。And the bycode of your interpreter。

And emitting machine code。 Oh， okay， so it's going from bikecode to machine code， yes。

And it can do that for normal Java without an AST， so it's a vanilla Java， bycode。

 dynamic chmo bycode zone shingle compiler， but in this mode it also looks at the ASTs and the profile and type information from those ASTs to guide it in life。

So this comp is specific to the program that's running exactly exactly it's compiling what what's happening here is it's compiling a fragment of a language it's never seen right that's the magic here is that we have a compiler that's compiling something it was。

It doesn't know about Fie， it's never going to know about FNie and we're not going to put Fie specific optimizations in。

 but when it runs on your FNI interpreter， it will be generating code for FNie programs。😡。

If we go back to the desideorrata thing。The trick is。嗯。Let they generate。

What it's doing is it's taking the semantics of each language element as expressed in your interpreter。

It's taking the structure of your program as expressed in the AST。It's taking the hints。

From the profiling data， and it's emitting machine code。For a program in a language。

 it's never seen before。That's the important difference here。

We've got now a compiler which is reusable， it doesn't need to be customized for every language。

 the way customize it is by supplying it with an interpreter。😡。

That's how it knows about the language。ほのこ。So at this。

 if you look at this as a black box and just see what the end result is the end result。

 the machine code that generated， would you say it's similar to the way men tracing works in that you have an AST interpreter and it's doing something？

This whole framework is trying to figure out what machine instruction is doing for a particular program and generating the high level goal is exactly the same。

Which is to generate good code。For a language that's implemented via an interpreter。

The underlying mechanism however is completely different， which is why I wanted you to see both。

Because they're trying to do the same thing， but by a completely different way。And you know。

 you can make your own judgments when you look at the papers as to the effectiveness of one or the other or which you like or how we can。

Now it would have been nice if you could have written an interpreter and processed it with Pipe pie those are another exercise。

 but there are only so many weeks in the semester。It would have been very instructive， I think。

 to do it both ways because I think we would have found。

Very different characteristics in some respects and we can talk about those maybe at the end after you've tried this because it'll be interesting to see how well you do with that。

This， I would say， is harder。In that you need to know more。But in general。

 we' are finding you get more performance out of it at the end。

 it doesn't seem to be quite so much of a performance barrier。But that's still， you know。

 both systems are in development， so that might not prevail to the final story。ok 啊。Yeah。家荒嘛。

that one。Don't do any of this until you've got it working。😔，Before I go any further。

 don't worry about this stuff， this is from when you start wanting to tune and you're probably a couple of weeks away from that。

诶。But I'll cover them here because we got no lecture。

So these are the things that you can put in your code， which if you run your program on a stop JVN。

 they're all noOs， then they don't do anything， but when you run them on the GVN。

 each of them has a specific meaning。So if you annotate a field as compilation final。

 when the Grl compiler processes that AST node with that field。

 it's going to assume that field is never going to change thereafter， trace is final。

So it can do optimizations based on the constancy of that value。

If you want to write code that's never compiled。You put this call where there's obviously a thing before this。

 you know， truffle runtime or something you have to put before it， but this is the important thing。

You put this call in your code and when Grl sees this and gets to this point， it says up。

 just insert a deOt， don't compile past this point， I'm just going to deopt at this point。

So this is the way of saying， don't execute。If you use this call， it will not only deal。

 but it will invalidate the code。 So you put this in when。

You've come down a path that never thought you were going to come down and you've made decisions or assumptions or you'd gather data which you now want to throw away and start again with a fresh compilation This is basically the API for DO or one of them。

And so this is done， for example， when you call replace on a node。

 this is the replace a node with one of a different specialization。

That automatically invalids any method that was generated based on。

So that's why you want your AST to be stable at the point where graphicic in compiles because if it isn't stable。

 the node switch will trigger this and that will cause a deop of any compiled code that's included that piece。

 that fragment。Trffle boundary I already mentioned。

 you can sprinkle that in various places and then that's kind of a hint that says。

 you know probably don't inline through here。I'm not quite sure why they say it's a hint and not。

You know， never in line through him。That's what it's meant to me。

You can also test to see whether you're actually in compiled code。

Or running in the interpretive version of E to using this other test， and there's a use of that。

 which I'll show you in a couple of slides。So。When you want a profile。

You can profile in a number of different directions。

Splet cases are about branches and branch directions， so if you have a test。

And you want to make an assumption。That the code down one branch of that test is very unlikely to be executed。

 but you want to explicitly tell Gr this。 and you can get one of these things called branch profile。

Make a job object and store it in a final field。And da some branch， if you enter that profile。

 then Grl will see that this thing has being called and it will in other compilations。

 it will probably just optimized this code out and put a deOt there。 so when the test passes。

 it will then deOt the code and recompile based on that。

So that gives gives the system a hintin to frequencies There's a more nuanced version。

 which is called a condition profile and that's for the case where you don't know what the probability are like right it could be could be 5050 or 6040 or 9010。

 but you just want to measure and have the compiler based on the measurement it takes during interpretation。

 do whatever it thinks is the right thing so you make one of these objects。

And you pass it to Boulian that's the result of evaluating some other things。And that。

Increments of counters for one， you know the true and the false case and when the compiler comes back to compile this。

 it'll look at the probabilities gathered you know the counts of the directions taken and take that into account as part of the compilation so if it's 99 to one then it'll do an awful lot of optimization down in 99 branch and down the one branch。

 know nothing or it might even bother compiling them beyond。

So that's another way of gathering profile information that's useful。Heres a particularly。

 I think sweet example pulling some of these together， so this is the implementation。

Of the condition profile。The camps， Okay， so it has。

A counter for the number of times it was passed true。

 an counter for the number of times it was past false because remember where you execute。

 you pass the result of the test to this counter。So it's going to count。In true count。

 plus plus and false count plus plus how many times value was true or false？But。你听冇嘅气啊。

Each of these is guarded by an interpreter， which means when this code is compiled。

This code is completely alled， so the counters disappear when the inlining goes through this and inlines this method。

 because the counts are now。In the interpreter only。Cler than that， though。嗯。If。When you compiled it。

 the count was zero， remember this is compilation finals and now those numbers are never going to change if when you compiled it。

 the true count was zero and you made assumptions。Based on the true count being zero。

 if you come through this again。True count is gone because that was a compilation final。

 but value is still there。It will say， oh， we've come down the true branch when we never， ever。

 ever came down there before。 So good time to throw away this code and start again because。

We compiled on the assumption that this was never true， and in fact it's turned out to be true。

So this causes a compilation unit to beed。And interpretation to resume。

 and it will be recomplied again after some more proof。YouHave to think about this。

I like of stare at that。 And then at the end， in the interpreter version， it， it just takes the。

The true and the false counts and it's stuff to the flow in the。

A double with the actual probability of a a true outcome based on the observations。

Li bit mind bending。 Yes， do you see this stuff running into the same problem that like the registered keyword and see has or the in line。

 right， Like， why are you trusting the。Yeah or even why you encourage absolutely this。

 this is not for end user programmers this is for language implement for the language implementer like why can't。

 for instance， geologists always profile。Because it doesn't know where to profile。

 you don't want profiles at every single branch in your program。

You want Braille files that are tailored to。The semantics of your language and the only person who knows that is the person writing the interpreter。

 if they don't know that， don't mess with this because you'll like register。

 it can send you down absolutely the wrong path， which is why it's important to make it work first and worry about tuning later and don't put these things in。

Without gathering data， I'll talk about that。A little bit later this should all be done on a data driven basis。

 sprinkling， but basically what you're doing is you're putting in。

Declarative structures that shouldn't affect the correctness of your program， right。

 there's no way that this should change the behavior it will only change the performance。

And you're putting them in in places where you think the compiler could use somehow help in making a decision。

And if you can establish that， then you can put the thing in and it should do no harm right the worst it will do is make your interpretation elements long Yes so we're really going to be using the declarative directorives to declare what the children needs。

小丹。There's two uses of that， one is I'm implementing the language。

 I need certain different semantics from my operation。

And the other is I know that I can implement a specific operation or a type。

Using different representations with different performance characteristics。

 So if you were implementing， say JavaScript。A naive implementation would use double as the one and only numeric type。

Because that's what JavaScriptco has is， it's one and only numeric type。

 that's the language semantics， all numbers are doubles。

And you could implement it that way and it would run just fine。

But if you put an additional specialization in that says。In the case where I've seen only ins。

 I'm going to represent things using an in or a along。

 and I'm going to ch specialize when I see an actual fraction appear。

Then it will go faster because it will generate integer only code in the places where those operations are used。

 that only use integers。So there's kind of a two different functions for the specializations capturing the actual semantics and then specializing additionally to capture。

Particular cases that you want handled specially。Again。

 it's a good idea just to start with the first kind and put the second kind in laser because you can always add specializations to laser。

Any other questions。O。The most general。Form of dependency。Is encapsulated in this class assumption。

Remember。When we talked about。Dynamic compilation and deoptimisation。

 I talked about a dependency graph。That registered compiler optimization decisions that had been made。

Based on some assumption。In the compiled code like I showed you this in where you know。

 I could make an assumption about say the types of say the plus plus is going to be ins。

 I've only ever seen ins， I'm going to inline in plus， but when I change the in plus definition。

 I have to find all of the places where I made that decision and throw that code away。Well。

 this is an API for doing exactly that without having to implement all the machinery under the cover。

So in this case， what you do is you create an instance of this thing called assumption。

And in your code in the interpreter， you can check an assumption in a straightforward way by doing assumption。

check。And if this code is true， then the compiled code after it is valid and it will run。

But if somewhere else。You say assumptions don't invalidate。

The runtime system will find all the places that you did this and it will throw away the code。

Where this was in line。So you can this check disappears， it's not in。The compiled code。Right。

 because。The code is assuming that that's true。 The check is made。You know。

 down here and the result is to throw away the code which is on which the check is best so this there is no performance penalty for including these things on the true path。

So this is used in a number of different places， for example。

 if you have a function and you have a language in which you have a function and you can redefine functions。

You can have a call that calls a function and the function will be inlined。

 but you want that code to be discarded if the function is redefined。

Functions are redefined usually and frequently， so it's usually the right thing to do to inline it and discard the code on the redefinition and you can use this mechanism to do that。

There's a particularly sweet example of this in the Ruy implementation that's been done on this in Ruby you can redefine very。

 very basic primitive things like a plus。And so you can be evaluating a plus。

On a couple of integers and in the left child of the plus， plus can get redefined。

And the pulse operation is supposed to use the redefinition。

RightNow if we were to compile that without this mechanism every time you compile plus you'd have to check where the plus has been redefined and in fact that's what G Ruby does It has a global flag that says you know I've redefined plus and it just throws all that stuff away you know and you're running slowly throw all the slow pluses where everybody is checking。

But in our system， you put one of these assumptions in and when Plus getss redefined。

 only the places that use Pket。The optimized and they can be really optimized using the new definition later if you really want。

So that doesn't happen when you call equality。Yeah， because this guy。嗯。

So assume you're running this code and something invalids， we're going to call this invalidation。

RightAnd that's going to throw away this code。And anywhere， anything that it was enlighten London。

So this code here and now， which assumed the assumption was true， is not going to run。

So is there any restriction in the way in which assumption objects can be used？OrHow， how does。

Girl track。if the assumption I check is when it compiles this。

 it' will put in the dependency from this to this。So that when you call this。

 this code gets discarded or any maligned version of this code。That's all it's doing。

But the variable assumption could refer to more than one assumption object。

 and you could have retain a number of objects that you well there。No， I mean， I mean。

 you have to send check to an assumption and assumption is an instance of assumption。

Right follow combinedre you're not really sure whether the assumption that is being evaluated to they're the same assumption that's being checked over there Well are because they're in the same variable。

 right and oh， this should probably I think this should probably fine that's okay or a compil should final or something like that。

喂。But then， you know， it's a reference to an underlying object somewhere。 Yeah， okay。

 you probably I've alled a lot of。Decoration from needs to get to the point。

嗯I think I already said that。Okay。There's an object system in which you can build objects， you。

 I'm not going to go into this men because I don't understand and follow myself here。

Well basically there's this thing called dynamic object。Which looks like a Java object。

 actually looks more like a Java hash mapap with keys and values。

And use it in implementing objects with random structure where the number of the properties can come under。

But behind that there's also other structures called shapes and the shape captures the particular usage of one of these dynamic objects with particular sets of keys and types on their values。

If you use dynamic objects in your guest language and as in most guest languages。

 they change structure in relatively infrequent and well-defined ways。

 you know you run something and you add an X here and you add a Y there。

 and mostly the X's and the Y's are referring to X are doubles， things like that。

 then the compiler can track the use of these shapes and optimize the cases based on the actual shapes that are ex in your program。

 so you end up with something that looks like a hashm。Implementation of an object。

 but actually gets implemented down to a， you know the conventional kind of struck implementation of an object with offsets and direct workup。

嗯。You'll need this when you come to do object in pho。

 but I need to get you more material tutorial material to do that yet which I wasn't quite ready so but。

The exercise will be broken into two parts。 so you're going to start by implementing the basic。诶。

Values and functions。Infinie and control structures。

 but without doing the arrays and objects and methods because that adds a fair amount of complexity。

It will take。Some time for you to get into the mindset of using。This system， it's not like。

Writing an interpreter in C。not very much like it at all and in fact。

 the more your program looks like an interpreter RNC。

 the worse it's going to perform in the long run。Because the one thing that Grl won't do is do magic optimization on arbitrary Java code。

 it needs the structure to understand what you're doing And if you just have sort of Java stuff。

 it's just Java， it's not going rain。嗯。So in step one。

 the exercise which we'll hopefully put together by the beginning next week。

 you'll be doing functions and control structure then step two， if you're feeling brave。

 you can try it all at once， I mean I don't really care whether you break it up or not。

 but I would advise starting small。And you know， you'll be programming a Java。

 you'll probably want to use an IDE of some kind， so it's quite different set of infrastructure than what you've been using。

So far in the bigliographyy。You will find a bunch of resources。That will help you in this path。

 I would recommend reading the paper on the truffle DSL that was published a couple of years ago。

 unfortunately the details of the language have changed since that paper was published。

So don't take the examples literally， there is a pointer to some stuff on the web which explains some of the differences。

 hopefully the basics and the gist of the paper will be。Not misleading。

There are also other tutorial slide sets and sample codes that you can look at for guidance in particular。

There is in。The repository， which everyone will have as part of their setup。

 an implementation of a language called simple language， which in fact。

 is actually I think more complex than fe。By quite a bit。

So F is even simpler than simple language and you can look in there to get hints as to how to structure things and examples which both work and are reasonably well commented。

So it's explained in the code， there's a tutorial， actually， there are several tutorials。

In YouTube with slides and video， because the system is a moving target， the further back you look。

 the less accurate the tutorial material is because the system's evolving and so something two years old is just going to have stuff in it which isn't correct anymore。

I would go for the most recent ones if you can， but the code in simple language is known to work。

 so that's the center of the rock on which you should anchor。嗯。How do you do this Well， like I said。

 don't think of this as writing an AST interpreter in C just translated into Java with the odd app sign here and that。

 that's not what you want。What you want to do is you want to take each of the nodes， you know。

 build a node hierarchy。嗯。Define your types and then start putting in the specializations which will guide the code generation。

Looking simple language for example， but the code that I've had on the slide is all basically derived from the simple language example so shouldn't mislead it。

If you see complex control flow in the node， particularly that's testing on types。

 that's a hint that you should be specializing into those types and letting the DSL。

Select between the alternatives， you shouldn't have instance of in your code， broadly speaking。

 that should all be in the framework guided by the type declarations that you put in。

Don't do any specialization in pausing， I don't think you' have a pause supply to you anyway。

 so I don't think you can just trust in the runtime stuff。

Then if you get to the stage where it's working and you want to tune it once you get there。

The tuning hint are don't try to speed up the interpreter。

 that's the wrong approach here because the interpreter are only going to run for a few thousand iterations。

What you're looking for is to give hints that the compiler can take and generate really good optimized code and itll be like 100 x faster than the interpreter when it compiles。

 but you have to get it to the point where it does compile and you want to guide it to compile the right thing in the right way。

So the trick then is put in the profiling information that it needs。

 you know you'll have the type information already there by virtue of the specializations and it will use that if you find representations that are even more optimized and you can add specializations for those that will help too。

And then you can put in profiles like the branch profiles and the condition profiles and stuff like that to guide compilation and to measure in the places that are key I would use micro benchmarkchmarks if while you're implementing a language feature。

little micro benchmarkchmarks for the variance of that feature and the variance of the type and time them。

 look maybe you can look at the code that's generated and see where or NeGral in the IGV。

 that's the way people are really building languages do stuff。

 they're looking IGV to see where the stuff gets optimized away。

 and then they put in the appropriate specialisations and profiling。

I'm guessing you won't have time to go quite a farther。

You want to use final fields where possible because final is a great way of telling the compiler this isn't changing and it can do a lot with that。

 and if the Java final is too restrictive and compilation final can be used instead。

Take 10 minutes and I'll tell you about it。System architecture not called。战略。Same there。嗯。

St with this system， I want to just describe some of the things that we're doing for that。

Hopefully motivate why you're even bothering with this stuff so the architecture of the system。あ。

Is broadly， as I described earlier， we have this trule framework。

 which is pilot Ja code and an an processor。And language implementations that sit on top of that。

 and all of that stuff is pure Java。Stop JVM， but with not good performance。

When you replace JVM with the gral system， which is the combination of grail compiler and the hotspot JVM and the compiler interface。

You then get to run this stuff with pretty good performance and it will run anywhere the hotspot runs because it's using the production version of hotspot。

We currently have these languages in a fairly advanced state。

 there are various little language that our'll list at the end or in a lesser advanced state。

 but we're progressing forward with them， and we've opened so much much of the system。

 certainly enough that you could build languages and experiment with the system。We also have。

A replacement for hotspot that can sit down here because the when we write these languages and the framework and the compiler。

 we actually restrict ourselves to a subset of hotspot of Java。

 which firstly relies on a closed world assumption。

 we don't have any dynamic class loading or anything like that ever in any of these implementations。

And we also don't use reflection。runtime and so what we can do is take all of these things。

 process them statically， tree shaking， elimination。

 all of that stuff and then once you've done all of that and eliminated all of the stuff you don't need。

 you can run them on a VM which implements a much smaller subset of Java that doesn't have all of the mechanisms for don class loading and reflection and many other features and that as a consequences much smaller starts up more quickly has better footprint and by the time you've done all tree shaking up here you've eliminated a lot of the overhead。

In your system。That tool。Is also designed to be embedable within larger systems。

 one of the difficulties with trying to embed something like hot sps。

It tends to assume it's in charge of a lot of global properties within the process that's running and it takes over signal handlers and things like that if you have a thing you want to embed it in and it has its own definitions of signal handlers for the same signals。

 you get these horrible conflicts and memory management and all of that stuff this doesn't have any of those problems it's designed to be embedable。

 in particular given the nature of oracle a couple of obvious places where you might want to put it。

And that is indeed where we're trying to put it。So we think we hope we hypothesize that maybe we've resolved this complex thing that。

 you know， instead of doing all of that。You can write a PAer， you build an AST interpreter。

 you have something that works， it's okay， and then you tune your specializations and your declarations and all of that stuff and you end up with something that's already pretty fast and instead of having to go through all of this pen。

 we are the ones you've gone through this pen and you got to leverage all of that stuff that's been pushed into all of that。

The tools and the tool Cha and the end。嗯。As I said， we're quite well advanced on JavaScript。

 Ruy and all。C of all things is underway and I' explain。で。Slide out two， we just started doing Java。

 which means Java executing by trule interpretation and not by bycode interpretation。

And we're also working on a front end for the system which can inject LLVM bitI code into the system so we can take bit code from languages that have LLVM front ends and run that too that's just begun so we have nothing really show over that。

There are other groups who've tried various other experiments。

 there was an experimental Python implementation done Irvine。

 I don't think that's actively learned and development because the student graduated but he got a fair amount fairway with Python but mostly the language co and it was quite a big amount of thing to make a full Python implementation there's a fairly advanced smallvo implementation and there've been some experiments done with Starlet too you can find all of these mentioned in the literature in the midway。

So performance metrics I'm going to give you a couple of slides。

 these slides are out of date so they don't capture the exact reality of the world but you use them as a flavor of where things are and in the case of Ruby the implementations incomplete so it's hard to make performance claims when you haven't done the whole language。

Because you know you might have cheated but I'll try and explain why we don't think we've cheated so this is an implemented there some numbers from our JavaScript implementation compared with Google being a numbers I think come from early summer so they'll be out something will have changed buying out。

These are running the V8 benchmarks so their benchmarks and our benchmarks and you can see ballpark is' competitive with V8 it's in the same region a little bit up in some places and a little bit down in others。

 but we're getting approximately know the other thing I should quite out is this is peak performance。

 you know not as a startup is terrible and it needs fixing and there are some other things that need fixing。

 but it is a complete implementation， it passes 100% of the X scripts。Javascripts that。

Ormentation by the reasonable definition。嗯。This one shows some of the work we're doing on Ruby。

 so this is an image processing library。That was built by somebody external to do kind of photoshop like processing on images in Ruby when you run it on the C Ruby interpreter that's normalized to one。

 when you run it on our Grl， Ruby interpreter， it's eight times faster。Now。

 the person who wrote this was so unhappy with the performance on the Si Ruee interpreter that they rewrote the cons in C。

And when you run the combined version that they have。

 which has the out parts in Ruby and the inner parts in C， it's 11 times faster than the original。

We have the C implementation as well。Were we of all things interpret CSTs。

 and then we can codegenerate and inline those into other languages？And when we do that our。

Implementation with a C code being fed through braL is now three times faster than their implementation with a C code being fed through a GCC and the difference here is because we're using a common IR for compilation for both languages we can inline across that boundary where a normal system C compiler generate C code but machine code for C part。

 the rubby system is interpreted and it's compiled separately in that boundary is a very expensive boundary otherwise we eliminate it overhead of that boundary significantly。

We're now doing a lot of work on multiple languages and interop between those languages so that you can write。

A relatively fine grain expressions， methods。Loops were the inner part of the loop calling to one language in the outer part into some other language。

 because we think that might be a very interesting direction for going。

And this particular experiment described on Chris Seman's around blog page。The C implementation。

 when you run kind of standard C benchmarks through it。

 within about 25% of GCC with all the optimizations turned on， so it's not about。

So back to the original picture， this is how things stood。This is what we want to do。

 we want to get everything down into this band。I think it's unrealistic that some of these languages will ever be as fast as C。

 partly because semantically they do more work， they have to maintain safety， so he doesn't。

And semantically， they have to maintain some level more flexibility， like redefinition。

Which isn't there in Se。 So you're always going to pay some penalty for that。

 But the hope is that the penalty is， you know， at most small integer multiples， not factors of ten。

And we're trying to get down to this record。 So we're sort of。There with JavaScript Ruy。

 the our implementation is still a ways off but it' takes a lot to implement what we。

And then the nice thing is because we have。One system for all of these languages。

 we can optimize it between them in a way that hasn't been possible。So the substrate the empire。

 then a thing I'll mention。Takes the。The language you specified and the GDK and the substratePM definition does a bunch we use Grl as a static compiler as well to do a ahead of time compilation of that whole stack and treesha came to fiinate all the parts that aren't used and then we can generate。

A conventional binary for the resulting VM that doesn't need hotspot。

 It just runs your language directly。 And this is typically。

Starts up in milliseconds rather than the whole normal stack。

 as you'll see when you run it is about a second in start time and it's often you know。

The minimal hello world is like two orders of magnitude smaller than as you would expect hotspot。

 plus a whole bunch of Java code is going to be a lot of memory and many， many megabytes。

 this can be down to。You know， hundreds of kilobytes。In contrast， so。

I stole some of this stuff from Christian's tutorial。

 I recommend you go look there and to give you some idea of how many people have worked on this。

 there's the eye chart。And we'll close at that point。你冇 questions？If not。

 you to finish a little earlier。Is this substrate straight beyond law also something that's available。

 not yet， it's not finished yet。If you want to work on it， however， we are looking for internships。

For languages through semantics can be expressed。Le's nicely using the JBM bike set。嗯。

How do you imagine those that perform against them？The troubleffle。

So I think J Ruby is a good indicator in that J Ruby can be expressed but not nicely because it's a dynamic language and I think all dynamic languages are going to fall afoul of the same problems that J Rubi had and we're seeing five to10 x speed up over J Ruby。

And I would expect the same for。Python and our description， all of those others。You know。

 if you look at， say the JavaScript that runs on the JVM， there's Rino and Nashorn。

What considerably really fasted。Its muchuch faster than rhino because that's an earlier thing that doesn't attempt to do anything fancy for the JvM route Nas Hol does a little bit more work to try and get speed out of。

The J animal whistle， you know。Many into multiples above。

Which is sort of what you'd expect if you can compile out all of the overhead。

 you should be getting down to。You know， something that's。

That you'd expect out of a C compiler with the extra checks that are。

Can't be removed for safety if you actually go look at the one of the tutorials I found was particularly useful as a tutorial given by Thomas Verter which I mentioned in the bibliography partway through that he takes the simple language example of just running a loop。

And he looks at machine code that's generated for her。

And it's pretty good machine code you have an overflow check that wouldn't be there and see because it all spills out to begin arithmetic on the case of overflow。

 but if you hadn't defined a language that didn't do that， it wouldn't put that in either。没有。

Actually that's my second。I'm not really a processor guide， but you sorry， I'm not a processor okay。

But these extra checks when you run them on an out of water processoror。嗯。

What is the additional penalty that you get？I actually all run in parallel out of。I mean。

 there's a price to all of these things they're not completely free， they're not expansive。

 but they're not completely free and certainly。I think it's a reasonable assumption。

The runtime of your program is roughly proportional to the paths of the machine coach you run。

You know， Patrick， it'll still reduce freeflow because then it has to do the check instead of doing something else even amount of order。

O。Rightright。O。Alright， so I see you in two weeks。And good luck。

