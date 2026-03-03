# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p25 1701699300-Compliers_on_12_4_2023_(Mon).zh_en -BV14PAUejE98_p25-

On Sunday， December 10th， of course we don't actually have any office hours scheduled for Saturday and Sunday so the last office hours are going to be on Friday。

 December 8th as well and I appreciate that end of semester is busy for everyone you'll all have a number of like final projects。

 PS setss and so on but when you do eventually turn your thoughts to the CS153 final exam。

 there is a practice final exam that's up on the Canva website take a look for the page in the menu bar about that。

Final exam itself， it is on Friday， December 15th， 2 pm in Science Center D。

Apologies for whom this is the only final exam。 I hope you。

 and I appreciate that this is fairly late in the exam period。 I don't get to choose。

The timing of the M but。Hopefully you'll enjoy a bit of quiet time and you'll have a bit of time to prepare for it。

 The exam is open book， open note， open laptop。😊，So what this means is that you're able to refer to any course materials including lecture notes and I'd encourage you not to print out rims of paper to have the lecture notes one of the main reasons for making this open laptop so that you can refer to notes online you are also welcome to use compilers and write programs and things in class and sorry in the exam we'll be trying of course to make sure that the exam doesn't rely on you actually using biolo that is rather testing concepts so our intention is that you will not actually need to run any code during the exam but we're not going to prevent you from doing that one thing I forgot to put on the slide though is use no use of generative AI for the exam。



![](img/d6882e73cf5475171596d78b21e177b9_1.png)

So no getting chat GPT to take the exam for you。呃。呃。We have this。

 you may not otherwise use the internet， the key idea here is be central about it if you have files and Dropbox or Google Drive and accessing it within the internet totally fine。

 but don't be using this to communicate， don't be searching for answers on the web。

 essentially just use your common sense if you have any doubts， ask before or during the exam。

The exam is three hours，180 minutes。 There are 30 multiple choice and maybe some short answer questions。

 each are with one point。 no partial credit so。I'm very happy if anyone wants to chat about why I think this is actually a good format for a final exam where as opposed to for example having four or five large questions in many ways I think the many small questions end up being reducing risk for you all as exam takers if you get one question wrong it shouldn't follow on into the other ones there's no penalty for getting a question wrong so we encourage you to try all questions and of course normal exam technique management like actually getting a chance to read all the questions the hope is that it shouldn't be a hugely time- pressured exam。

But 30 questions，180 minutes， about six minutes a question on average means that。

It's quite reasonable that many of you will be using a good chunk of or all of that three hours。

The exam itself we're going to administer on Canva so it's going to be you log into Canva。

 go to a quizzes， there'll be a final exam there you can take you have to be in the classroom for it we will be taking attendance but what it does mean is that you really do need your laptop so make sure to charge your batteries beforehand or in the process of making sure there are power strips and so on in the room。

 bring a charger but definitely try making sure that your laptop is working。

Any questions about the exam or anything else on the administrative side as we get towards the end of the semester？

Okay， so let's jump into the content for today We're going to talk about a bit of a different topic than we've chatted about previously so far in the class we've really been talking about the design and the implementation of compilers and the range of things Today we're going to talk about verified compilation。

😊，So they idea of a verified compiler。Is it's a compiler。 Great。 We know what that is。

 but it's also accompanied by a proof。Of the semantic preservation property。

That is that the generated machine code， the assembly that we're producing。

Does the same thing as the source program。Now， more than just having a proof。Proofs are complicated。

 to be honest， compilers themselves are complicated， reasonably about compilers can also be tough。

So what we actually require is a machine checked proof。Of the semantic preservation property。嗯。

So first of all， why do we want verified compilers？Cile is complicated as anyone who has ever。

Got less than 100% on a homework assignment nose， they have bugs， the compiler might crash。

 that is when you're running the compiler and it' attempt can compile a program。😊，It might fail。

 All right， That's actually the good news。 If you compiler crashes。

 it means you know something is wrong。😊，What's much more insidious is if the compiler completes and outputs assembly code。

 machine code。But that machine code does not actually accurately reflect the source code。

So maybe for example， you look at the source。And you see some arithmetic computation。

You're assuming that when you run that program it's actually performing that arithmetic computation。

 but suppose the compiler made an accident， made a mistake。

 a bug maybe didn't reason about overflow correctly。And the answer that your manings are producing。

Is not the same as you're intending。So this is a problem。

 particularly when we have the output of compilers used to do things like lie aircraft。Drive cars。

 manage nuclear power plants， and various other critical things。So， in that sense。

We should worry about the output of our compilers。 We should worry about software in general。

But I'd argue that compilers is， as we've already talked about in the class。

 part of the critical infrastructure of many systems and bugs in a compiler might be particularly problematic。

Now you might say， you know what， there's not actually that many compilers use from practice， you。

 a handful。There's lots of smart people， people have taken compilers classes as an undergraduate。

 even graduate courses in this thing gone on to actually implement these things。

 so maybe these programs are actually pretty good， pretty solid， they are compiling millions。

 billions of lines of code and the system seem to be working， maybe we're okay。😊，That is。

 maybe it's the case that compilers just aren't that buggy。Well， let me tell you about a tool。

 this was a study done okay， it was a little more than 10 years ago。

 it was published in 2011 the tool was called C Smith。

 was from a group of research group and University of Utah。😊。

The basic idea was that it was a fuzzing tool for C compilers。

So the way fuzz and tools work is essentially given a program。

You might want to test it by using test cases。But there's maybe only a small number of test cases that you tester of the program is able to come up with。

 The idea of a fer is that it's automatically generating。

Inputs for a program and testing those inputs on the program。There's various kinds of fuzzes。

 There are things that are known as black box fuzzes that don't know the internals of the program it's testing that are just producing test cases。

 There are white box fuzzes that get to look inside the program and try and choose test cases that will actively end up。

呃。Testing in particular， trying to get code coverage in the code。

But one of the interesting things about testing a system like compilers， compiler for。

 say the C programming language， is that there are multiple implementations。

There is more than one compiler for the C programming language。

 so the way that CSsmith actually works is it produces test cases， it fuzzes。

 produces random sea programs， rather not uniformly random。

 it's kind of very carefully chosen to really exercise some of the key parts of a compiler。

But it runs that program through multiple compilers。Right， LVM， GCC were the ones that' focused on。

If they disagree on the output， that is on the behavior of the output。One of them。

 there's a few possible situations。 One is that it explored a case where it was up to the compiler。

 the behavior it wanted to implement。 let's say the program。

Exploited undefined behavior or exhibited undefined behavior according to C specificphation。

 then the compiler could do whatever it wanted。But if。The program is well formed。

 well defined with respect to the C source code。Then the compilers should be producing。

 then the programs produced by the compilers should produce the same output。themIf they differ。

 then one of them is wrong。So this is the way where fuzzing can be used to find errors and see compilers。

So on this work， they focused on L ofVM and GCC to open source， C compilers。

 the development teams for these compilers are quite responsive。呃。

Open source so they could actually take a look at the code。So。U。Hands up。

 if you think they found less than 10 bugs。In either one。No one。

 nobody has any confidence and you see compilers so it turns out。

In this study from about 1 years ago， they found about 79。GCC bugs and about 202 LOVM bugs。

T you know LLVM， I guess， started development in the what late 90s or something GTC。lateate 70s。

 mid 80s。 I can't actually remember。 So GCC had been around for quite a while。 L O VM less so。

 So that's one of the reasons for more L V M bugs。 The code isn't as。Stable or secure， but even GCC。

 which is。30 plus years old at the time， extensively used by many， many people。

 extensively worked on and developed， they still found almost 80 bugs in that。

As we'll say here at the time was about the 200 bugs from LLVM was about 2% of all LLVM bugs at the time。

Right， so。This is contending。Right。There were lots of bugs in C code。

So this is the motivation really for verified compilers， that if you can prove that your compiler。

 the output of yourcalil is preserving the semantics of the source program。

We're essentially removing entire classes of bugs， right any bug about。The output program。

 not reflecting。The source program。So， it was。With this in mind that。

This need for verified compilers that in 2003。So Anthony Hore of the UK proposed the idea of a grand challenge for computing research Tony Hores。

Very distinguished computer scientists， for those who have taken 152 and looked at program logic。

 it's the same Tony Ho that developed Ho logic， axiomatic semantics。Okay。

 so the grand challenge that so Tony proposed was。嗯。Well， let me first of all tell you。

The idea of a grand challenge。They idea being a commitment by a significant chunk of the research community to work towards a common goal。

 something that's going to be valuable， achievable with a team effort and a predictable。

Pdicted times to scale。 some of the key things to note here are it's meant to be fundamental work。

 astonishing， testable， revolutionary， inspiring， feasible。

 So think about putting a man on the moon in 10 years call to action in the 60s。😊，嗯。

So something that would unite a large part of the research community some grand goal。So in 2003。

 Saton who suggested a number of challenges， but one of them was for a verified compiler。

 could computer science as a community。Attack this grand challenge。

 like produce a compiler that is verified guaranteed to be correct。So the community took this up。

 this was meant to be a grand challenge on the order of like a decade or longer。😊，诶。

About three years later。There was a paper published about Compt。Certified compiler。

 formal certification of a compiler backend or a programming a compiler with a proof assistant。

This paper。Was essentially 90% of that goal of that grand challenge。

I'm going to talk a bit more about some of the details of this concert tool。

But the key thing is that it is a compiler for a subset， but a large subset of C。Into at the time。

 power PC。assemblysembly language and was able to be verified。

 That is it came with a machine checked proof。ThatThis compiler was correct。We'll dig more into it。嗯。

About a little bit about the design and also about the use of concert in the almost 20 years since。

But one of the key things is that that Csmith paper。

 that C compiler fuzzing paper I told you about earlier， found  AD0H bugs and Gcc， 200 bugs and LVM。

 They also used it on Com。And they found no bugs。And this was just a few years after concert had been developed。

嗯。They found no bugs in the middle end。The striking thing about this is from the C Smith authors。

 the striking thing about our composite results is that the middle end bugs we found in all other compilers were absent。

As of early 2011 the underdevelopment version of Cont is the only compiler we have tested for which CSMth cannot find wrongcode errors。

 this is not for lack of trying we have devoted about six CPU years to the task the apparent unbreakability of concert supports a strong argument that developing compiler optimizations within a proof framework where safety checks are explicit in machine checks has tangible benefits for compiler users。

SoThis is a really impressive result， one， the fact that they were able to produce a verified compiler and indeed the vision of verified compilation。

Actually held up with the Seasmith paper and subsequently。

They did actually find some bugs in concert。 It was actually in the front end and the parsing。

 which at the time was not part of the machine checked。

 part of the compiler of Con Since then they have actually figured out a way to specify and machine check。

The power。 so the verification guarantee is now applied to pretty much the whole pipeline of。

Of concert。So Com was really the first place of Walden， so you said it implemented like a subset of。

Are you aware of like what part of the bugs of like GCC and LVM fell within the subset that would have been valid for concert？

呃。It is a good question I can't remember the details。

 but I think it might skirt on you should take a look at the C Smith paper。

 it's fun to read and also fun to see the kind of example programs。 These are not natural programs。

 These are things that are really testing the corner cases of the sea specification。呃。There are。

 for example， things like。Actually figuring out whether a program is undefined or not can actually be really quite challenging it' is definitely challenging for humans to do So one example would be you remember how C has like post increment and pre increment operators。

 plus plus I and so on。If you have， for example， multiple。

Post increment and pre increment operators within a single expression。Those are。

Their behavior is undefined。 So sorry， multiple post increment and pre increment operators on the same scalear。

Within a single expression。It's undefined unless there is a sequence point that clearly identifies when one operation is meant to occur after another one。

There are some notions about what a sequence point is。

 this is essentially where the C spec says this thing has to be implemented。

 has to be evaluated before that thing。Right。That isAnd so actually even just looking at an expression and figuring out。

 is this undefined or not？Is this something where it's valid is it valid for me to？呃。

Take advantage that on some values， this will be the undefined and I can have faster performance。

Compile something faster， even that is actually pretty tricky to figure out。嗯。Again。

 I'm going to punt this to Ed， take a post on it， and I'll be able to follow up some specific examples。

To show you some of the programs。Okay， so Com was the first certified compiler， William。

 Yeah other questions sure。😊，the machine check proofs， are they checking how to replace this？

Like the program， the compiler outputs for the compiler itself。

I will actually get into a bit of the details， not about how the proof is structured。

 but how we think about verification so just hold that forward for about half a dozen slides。好。Okay。

 Cont， the first certified compiler for the C programming language。

There have been others as well both， so KML is a verified implementation of ML。

 of which OCML is a variant of ML。嗯。There's also Vellum， verified LLVM。

Work out of UPN that formalises the allum intermediate representation provides a formal semantics for it and enables。

Proofs about program transformations and so on。So there has been a lot of work on verified compilation since then。

 I will say concertt has been commercialized and is widely used in widely used is used in the avionic industry。

 so that is compiling C programs to run the control systems of aircraft。

 so I think Airbus in particular might be a client of the company the commercialized concert。Okay。

 so what I'm going to be doing in a chunk of the rest of the lecture is actually digging into what is the idea of compiler correctness。

 how do we actually characterize， think about compiler correctness and sketch out。

 not the proof techniques， but at least the proof direction。Yes。So compiler correctness。

 the idea is that we have a source program。And source program is， we have a compiled program C。Now。

 intuitively， what we want is we want the compiled program C to preserve the semantics of S。

 that is the meaning of the compiled program should be the same as the meaning of the source program。

This actually requires us to dig into a little more detail。

 to actually try and define more clearly more explicitly what we mean by the meaning。

 the semantics of a program。There's a lot of ways that we can actually model。

The meaning of programs and again， 152 digs into this in quite a bit of detail。

But the way that is one of the ways we can do it and the way that。

Has been done in a lot of the compiler correctness work is to write a。Relation。

Over two things over programs P and behaviors B。Think about a behavior B for observable behavior B as being a sequence。

 a list of observable events。😡，Maybe there might be input and output to the system。

Depending on the level that you're looking at， a behavior might be the modification of a memory location or the reading of a memory location。

 something like that。So we write this P down arrow B to mean that when we execute the program P。

It produces the behavior B， it produces the sequence of observable things。😡。

In addition to Winput and output， behaviors might include the program terminating。😊。

Program finishing， maybe also includes the program crashing。

 so we're able to see when something bad happens like a Seg fault。

 that would be an observable behavior。😊，We might actually also include divergence。

 even though it's kind of weird to observe that， the idea that this program now runs forever without producing any more observable output。

 but that's often something that at least with respect to the modeling of the behavior of a program we might want to include in the model。

Okay， so this is kind of a building block。 This is a way of thinking about。When a program executes。

What do we observe about it？What are the behavior it exhibits？

It allows us to define a notion of semantic equivalentence。

 We can say that a source program S and a compiled program C。

Are semantically equivalent if they have the exact same behaviors。

 That is for all possible behaviors B。The source program， is produces B。

 if and only if the compiled program。Can produce the same behavior。

So there's a few things to note about this， this definition。1。

 it allows the source program and the compile program to have more than one possible behavior， right。

 So you could run it， and it might do different things。

 Maybe it does different things because you provide it with different inputs。

And the program does different things， Or maybe there's some randomness or nondeminism。

In the program， maybe it flips some coins and sometimes does one thing， sometimes does another。

So what this statement of semantic equivalentvalence is saying is that for the set of possible behaviors that S can exhibit。

C must also exhibit all of those behaviors。And vice versa。Anything the compiled program can do。

 the source program also needs to be able to do。In terms of randomness， though。

Or maybe you'll get into what a behavior is later， let's say， I don't know S。

We returns like zero or one with probability one hat C does this with like one third or two third right they technically have the same possible behavior。

 zero or one output， but I would consider them doing different。Yes， so we're not going to。

 you're right， as I mentioned， there are many ways of modeling the behavior of the system。

 this way of modeling it is what's known as a postsbilistic approach。

 it's saying here are the behaviors that are possible。

But it is doing nothing about the probabilities of behaviors。If it was important that。

The probabilistic behavior of a program was preserved。

You would perhaps need a different modeling approach maybe instead of a set of behaviours you instead have a distribution over behaviors and then talk about say the source and the source program and the compile program are having the same distribution over behaviors right that would be compatible with this。

 if they have the same distribution then the support for the distribution would be the same and both that is the set of possible behaviors would be the same。

But there's also more that there would in fact need to be the same。Yeah。

 so we're not going to consider probability， but you're right。

 probability is actually important for a lot of programs。

 imagine an implementation of a cryptographic protocol right that's meant to be generating a random number。

 a random key you definitely wouldn't want it to produce the same key every time。Okay。So。

This means that S and C have the exact same behaviors。Turns out， though。

 that this is not good for us to use as a basis for verified compilation。

 turns out that it's too strong。In most compilers， there are actually some behaviors of S that C does not have。

Can anyone think of some examples， So this is where。The source language says， you know。

 here's a possible behavior of executing this program。

But when we end up implementing a compiler and compiling that program down to assembly。

 that behavior is not possible。In the compiled code。Who can think of an example of that？

I see your hand， William， I'll give others。A quick chance。Betty。You haveX这个。Bch that not。

O well typing， that's a good question。I don't think that falls under this because let's suppose that we had。

A branch of S。That is never going to be executed。Regardless of whether it's typed or well typed。

In the compiled program， that branch is also never going to be executed。Right。

So this is the way we're phsing this is is there a behavior of S。

 is this something the source program？But according to the semantics of the source program。

 the program' is able to do。But when we compile it， we the compiler writers say， nope。

 we're not going in our compiled code， we're not going to allow that program to exhibit that possible behavior。

 I think with the idea of like dead code at the source level， it's。There。

 the source code is actually ruling out some behavior， right saying。That branch is ill typed。

 so I'm going to reject that program。So what that would mean is that。

If that program wasn't world type， it'd be the empty set of behaviors。

Of the source and the compiler would never。Actually， compile it。But there are。

Other cases where S might have some behaviors that we don't and S might be well typed will form something that we're okay running our compiler on。

 that our compiled code produce doesn't permit that behavior。William。

 did you have a I was going to say something like。Maybe I'm misunderstanding how S has interpreted。

 but yeah， I've been very vague and hand wavy so turns zero else return one。

Could that just be compiled to return zero， so would that be considered as the source program having two distinct？

Was is that what you just， I think that's similar to the example Maddie broke up。

 So if your source program was something like。If true， then return one， else return zero。

That source program actually only has one behavior， right all it can do is return one。

 it's always going to execute the true branch。And so in the semantics of the source program。

 there's no conditions under which， according to the semantic source program。

 the F branch would be executed。Yeah， does it have something to do with like how to like。

Like that a finite kind of memory to work with。Like are we？Theore Yeah， that's， that's a good one。So。

 for example， in the C program sp。We might say that there's。呃。At the C language definition。

 source program， there's no specific size， maximum size of the stack。

or of the heap or anything like that yeah when we compile down we are going to be compiling for an actual machine。

 when we execute it we're running on an actual machine and willll have a finite amount of memory。

 so you might have things like out of memory error， for example。That happens in the compiled program。

But actually normally in the source program， the way you'd actually do it is。You know。

 when you call Malck。It will in the spec， it says like either little return a valid pointer or it will have an error condition or something so in the set of allowable behaviors。

In the source program， which generally account for。Look。

 you might have run out of memory on this operation。

But you're getting at something where essentially the speck of the source language。Actually。

 it has to allow for a lot of possibilities。And indeed， in some languages。

It leaves some implementation details。Underspecified。Right so for example。😊，In C。

 it actually allows different evaluation orders。Of sub expressionions。Okay， so if you have。

A big complicated expression。嗯。There's actually nothing。In certain situations。

 the C specification does not define which order you need to perform that evaluation in。 Now。

 I think we touched on this that。For implementation reasons when you're evaluating arguments to a function。

It's actually kind of nice if you can evaluate those arguments right to left。

Because then you can evaluate the argument， push it on the stack， evaluate the next one。

 push it on the stack and so on， and as you' have computed them and pushed them on the stack。

 you're all set up ready to invoke the function。But the C language spec might actually allow for those arguments to pre evaluate an arbitrary order。

So there would be a behavior that the source program exhibits。

Let's say evaluating those arguments in a particular order。That the compiled program does not allow。

 which maybe always evaluates it right to left。I think later versions of the C specEC have actually required evaluation order to be left to right to fit programmers in tuition。

 but definitely some versions of the spec。I think allowed arguments to be evaluated in different orders。

嗯。嗯。Okay， so the source language is often non deterministic， right。

 allowing a range of possible behaviors and giving the compiler some choice and how to implement it。

 So that would be a case where the source language has more behaviors available than。

Thenhan the compiler。Then the K program。There might also be cases where the compiler might optimize away some behaviors that go wrong。

Behaviourors that the compiled program might exhibit that are not actually exhibited by the source program。

 so for example， suppose we had the expression x plus1 greater than x。

A compiler might well actually evaluate that perform essentially constant folding。

And say x plus 1 greater than x。It's okay for me to replace that with one。That is being always true。

Most of the time it is true， but effects is actually equal to the maximum integer。

X plus 1 will overflow。I think according to the C spec。

 signed into Gi overflow was actually undefined。Most of the time it will evaluate to the minimum integer due to these two complement representation。

 and this would actually evaluate to false， but because at the C language pick。

 it's undefined behavior。Things kind of have gone wrong。Right。

So to anyone how exactly would define the semantics。

 either this is a case where once you exhibit undefined， you do something undefined。

 any behavior is allowed from that point onwards in which case。😊，You know。

 there are behaviors allowed at the source that may be aren't exhibited at the target level。

 or alternatively， maybe we say the source language isn't allowed to have undefined behavior。

In which case， the program would reject an execution where x was equal to accent。

Even though our compiled program would actually allow it。

But it wouldn' by simplifying this away to one， it's never going to encounter at runtime assigned into your overflow and the compiled program is going to exhibit a behavior that the source program doesn't。

Yeah， Williams， its related to what I think Maxwell said about the stafft。Could you have， let's say。

 a function that calls itself， I know， 10，000 times？On the source level。

 it should be completely valid。Because like it'll terminate。我。Ex work。Yeah， so definitely at。Yes。

 at the source program level， you might have a behavior where。You know。

 a function does a goodjiillion invocations。And on a real machine， it's not actually able to do that。

The stackingers't that big and so you won't see that behavior so you'll see your behavior that seems to be available the source program that isn't available on the compiled program maybe because the compiled program doesn't have enough memory。

So yeah， that's another case where。This notion of semantic equivalence is too strong。So。Yeah。

 Christian。纯现性。He contains context。environment where the compiled program is run。

You couldn't potentially build a computer that has enough ground。

You arguments rather you extend this。Yes， so I'm being deliberately very vague about what exactly C the compiled program is and the behaviors B。

And even if I have the same compiled program， C， when I'm running it on a machine。

 I might be running on a machine that has a different amount of memory available in the heap。

and as a result， where does that love， is that in C。

 or is that something in the environment and so on， so I'm glossing over that。In some ways， yes。

 you do need to pin this down precisely when we're actually trying to prove。

Theorems about what's going on， so it's a good point you raise。

But come with me with the hand waving at the moment and we'll just try and get the high level ideas。

 so if you have like undefined behavior， but it doesn't。あまだ。App the same。This would depend on。呃。

This would depend on how you end up defining behaviors like and things going wrong。

 but what we're actually going to do right now is weaken the notion of semantic equivalentvalence。

To a point where we can try and avoid these issues about。About this。

One approach that we can use to weaken this notion of semantic equivalence is to actually just restrict our attention to programs that don't go wrong。

So that is。诶。To say that。For a program that doesn't go wrong， that is that can never produce。

 let's say， undefined behavior or crashing or whatever we define as。Going wrong。

Then all behaviors of C are behaviors of S。 so that is if S is safe。😡，If S never goes wrong。

Then for all behaviors B。If the compile program can exhibit behavior B。

 then the source program can exhibit behavior B。Right so what this is saying is。One。

 we're sort of only allowing source programs that are safe。

 that you let's say don't encounter undefined behavior。嗯。Which means that。

For the bees that we care about， they're going to be safe executions where something doesn't go wrong。

We're also phrasing this so that the compiled version can exhibit a subset of behaviors of the source program if the compiled version exhibits a behavior B。

 then their behavior B must be allowed by the source program。

 but the source program might have additional behaviors that the compiled version doesn't。

So this is a weakening of semantic equivalentvalence that ends up getting around a lot of the issues about undefined behavior。

 about underspecation at the source programming level。Now。

 it turns out that in the particular case where both the source and the target language are deterministic。

That is that there's essentially only one behavior or for a given sequence of inputs。

 there's only one behavior。This statement is actually equivalent to the following。

 so for all behaviors that don't go wrong。They don't exhibit undefined behavior。

 they don't crash and so on。 If S exhibits B， then C exhibits B。So this is very much relying。On。嗯。

Determinism。Right on the fact that there can essentially only be。嗯。呃。The if the exhibits B。

 then the implementation of C really has no other choice。Than to implement B。Right。Now。

 it turns out that this formulation is easier to prove， so when we're trying to verify a compiler。

Being able to phrase it this way to say， hey， if the source program does B。

 then the compiled version does B。That's actually going in the four direction of the compilation pipeline right and that turns out to be easier than going the other way where to go the other way to say。

 hey， if my compiled program produces this behavior， then the source program allows it。

 if you do it that way then essentially what ends up happening。

 I won't get into details but essentially in your proof。

 you need to implement decompilation in your proof you end up needing to say if the assembly program can exhibit this behavior。

 then with assembly program construct came from this source program construct and that source program construct allows the behavior。

And so on and so forth， so you end up going backwards in your compiler pipeline and the proof turns out to be quite challenging。

So going in the four direction is nice and convenient for the proof。

But it does rely on determinism in the source and the target language。嗯。

This is what the definition we use going forward Okay， for brreevity。

 we're going to write it as S equivalent to C。Meaning that the source program S。

Compiled with program P S is equivalency F known F。For all behaviors that don't go wrong。

 if S exhibits B， then C exhibits B。Okay， so this is the abbreviation I'll be using from this point one it' is equivalent to C。

Okay， why is this definition a good one？So it turns out that what we're really interested in。

When for a compiled program， yeah， we definitely want equivalent behaviors。

But really what we care about when we're thinking when we're reasoning about programs is that they satisfy a specification。

So that is if I write a program， a source program that's meant to correctly sort a list。

What I'd like to ensure is that my program that correctly sorts a list and I compile it。

 that compiled program is also going to correctly sort the list。嗯。So we can write that as saying。

If the source program S satisfies the specification， then。

The compile program C also satisfies the specification。嗯。By this， I mean that if he is safe。

 then all behaviors of be meet the specification。啊。Now。

 the nice thing is that the semantic equivalence for safe programs。

But we just defined on the previous slide。It implies preservation of specifications。Right。

 so equience of the functional。嗯。Semantic equivalentvalence means that reasoning at the source program level。

About meeting a specification。Carries over into the compiled program。

 also meeting that specification。And that's ultimately what we care about。

So this is kind of saying that the definition of semantic equivalence is sort of strong enough。

For us to get what we want from it， right it's weaker than this full notion of semantic equivalence exhibiting the exact same set of behaviors。

Right， so it's weak than that， but it's strong enough to give us to allow us to reason about specifications。

 to preserve specifications。Okay， so this is what we're trying to do。

We are trying to prove that a compiler is going。To。Provide semantic equivals for safe programs。

What I wanted to do now is let's think about how we go about this。Proving that a compiler does it。

 And there's actually two key choices， two ways we could actually think about trying to prove this。

 And this is the idea of verification。Versus validation。Okay， so first bit of notation。

 let's assume that comp is the compiler， it's a total function from source programs either to OKC。

 meaning that it successfully compiled source program S to a target C。

Or this compiler function returns error。 It wasn't able to compile。 Maybe there was a type error。

 Maybe the source program exhibited some undefined behavior。

 So we were able to figure out that it wasn't safe。Or something like that。Okay。

 the idea of verification。A verified compiler。Is this program the compiler comp？Plus， a proof that。

For all source programs。S and compile program C。If the compiler applied to S successfully produces C。

😡，Then S is equivalent to C。Okay。This is a really strong statement。this proof。About the compilers。

 here' something about all possible source programs。

This is that the compilea has to work on all possible source programs。Okay。

 this is the notion of a verified compiler。I want to contrast that with what's known as validation。

So let's validate the。A validation function is a total function from a pair of S and C to ball。Now。

 the idea of a verified validator。Is a validation function， plus a proof。The for all SC。

 if validate SC returns true。Then S is equivalent to C。So the way to think about this is。

Validate gets given a source。Language C S and a compile version C。And it has to validate。

 it has to check that these are equivalent。If it returns true。

Then they really do need to be equivalent。Now， it could return false。

If they're not equivalent or if it just can't figure it out。Right。

 so the validation can be conservative。嗯。It turns out that validation is actually a whole lot easier to prove correct。

Then， in general。A verified compiler。In some ways， validation is easier because the Val program gets the source and the compiled version。

And then just has to for these specific， for these specific two programs。

Has to return true if they're equivalent。 ensure we need to prove that that's the case for any inputs。

 The idea is that validation is actually raising about two specific programs。

By contrast with a compiler。It's。When reason about the correctness of the compiler。

 we're actually in some ways reason to needing to reason about the correctness of its behavior on all source programs。

The good news though， is that if we have a verified validator。😊。

We can very easily turn it into a verified compiler。So to see that。

Suppose that we have comp being a non verified compiler， but we have validate a verified validator。

From this， we can produce a new compiler， Comp Prime。Take on a source program S。

And it tries to compile S with our original compiler。If that compiler fails， okay， we fail。

But if it successfully returns。A compiled program C。What we do is we try to validate。

The To program and target program。If we're able to successfully validate it， then we return OKC。

But if we can't validate it， we return an error。So it turns out that comp Prime is a verified compiler。

 right， It's only going to return O KC。If it's the case that validate SC return true。

 that is S&C have equivalent behavior。The proof to show that comp Prime is a verified compiler is pretty straightforward。

嗯。So this is cool。 What this actually means is that when we are trying to build a verified compiler。

 it's going to be a lot easier for us in general to build a verified validator。

And what that means is the compiler itself。We don't need to reason about it directly。

 It doesn't need to be trusted， if you will。 It's more that the output of the compiler is what we're going to be checking。

 So the validator needs be。 we need to prove something about the validator。

But the compiler we don't actually need to prove anything about。

 we could have a large code base for the compiler。 and this will come up a little later when I show you the architecture for concept。

Okay， so this is cool if we have verified validation， we can turn it into a verified compiler。

The other nice thing about this framework， this approach is that it turns out to be compositional。

Now， by that， I mean if come for one and come to two verified compilers。

From language L1 to L2 and from L2 to L3。We can simply compose these compilers together。

That is given an input S， we apply comp 1 to S and if we're successful。

And get C then we apply Comptu to C。RightIn the intermediate language。You can check the proof。

 but it's a verified compiler from L 1 to L 3。 And this is essentially because our definition of equivalentence that we're using is transitive。

If S is equivalent to C。Which it is if compile is a verified compiler and C to。

 whatever the output of this is is also equivalent， the N to the ultimate output as equivalent。

So this is really， really nice because as we know from all our work this semester。😊。

What a compiler is really doing is just composing together a whole bunch of sequence of smaller translations through a sequence of intermediate languages。

So what this means is that if we're able to verify or validate each translation pass through the pipeline。

We can compose them together。To get verification for the whole compiler。So this is nice。And this is。

 in fact， how concert is architected。Right so I'm not going to go into the details。

 We can definitely spend a lot of time and work on on this but here is。

Essentially the stages of the concert compiler， the diagram keeps on going off the slide。

 I'll show you more of it in just a second。Concert is actually programmed in cameel。Zavio， sorry。

 the main author of Conet is actually also the main author of Vocael。嗯。The way it works is。

In this version of the of concert that I'm showing you， we take in the C source code。

 It's pard and simplified in non verified code。 So this is where。

Csmith actually found some bugs and composite in the unverified PAa。

 but this produces code in an intermediate language called C light C has C light has all the C arithmetic types and operators as well as arrays。

 pointers and function pointers and it has all of the C control structures except go to and switch so those have been compiled away。

Complied away or rejected at this point。So then from CL， they actually have some tools on it。

 reason about the program static analyzer model checker。

 but the key thing is that we can translate sea light。Into what's known as C sharp Min。

 this translation from C light into C sharp Min is verified。

 so this is actually a verified compiler from here to here。C sharp minor is a stripped down。

 typeless variant of C。Athmetic operators are not overloaded。

 so that is youve got a different edition operator for kind every type that addition would operate on。

There are explicit conversions from integers to floats， address computations， so for example。

 accessing anrailment， those address computations are explicit。

And there's only four control structures， right so it's compiled away， for example。

 four loops down as something simpler。🤧。Excuse me。嗯。From C sharpp Min。

 it gets translated into C minor， and this is essentially preallocating the stack。嗯。但是。

C minor it gets compiled into an intermediate language RTL Reg transfer language。So。

This represents functions as CFGs over abstract instructions。

 which roughly correspond to machine instructions。Operating over an unbounded number of temparies。

 Okay， so think about this as an L L VM like。Representation unbounded a number of temporaries that are eventually going to get mapped to registers or stack slots and operations that are pretty close to the things that we're ultimately going to choose machine instructions for。

嗯。Now， what's interesting here is to go from register。

TL register transfer language into LTL location transfer language。

 essentially what we're going to be doing is a bunch of optimizations， constant propagation。

 common sub- expression elimination， but also we're going to be doing register allocation。😊。

So what actually happened here？U。Is that it was really， really hard。

To prove that the graph coloring algorithm is correct。What they ended up doing。Was。

Doing the graph coloring algorithm。In unverified code。

And then just taking the output of that graph coloring algorithm。

 essentially like that location map you all are working on or you have seen in Homework6。

 that is mapping these temporaries to actual locations。And then just validating it。😡。

Right so this is part of the this is in some ways they found while they were implementing concert that this validation approach is much simpler and if they readed the whole thing。

 they would do more as validation as opposed to verification So the the idea is that the graph coloring algorithm with all its heuristics for coalescing for。

😊，You know， for which colors to pick and so on。All of that stuff is untrusted。

 You can let loose whatever heuristics you want， whatever things you want to do。

 but what you need to do is validate in a verified way。

That the coloring that's produced is a valid register allocation。

that is that no two temporaries that are alive at the same time are allocated to the same register。

Right。And that's the key idea of actually proving something about the register allocation。

It doesn't matter how you came up with that Reg allocation。

As so long as you make sure that it's valid， that that registrar allocation is going to preserve the semantics as you go from RTL into LTL。

🤧U。And then they do verify that。The registrar allocation actually。

Taking that allocation map from the graph coloring and transforming the program。

 that does preserve semantics， but that is much easier than the whole complicated mess of deciding what registers temporary should be put in。

And like I say， based on sort of retrospective work， I think the authors didn't end up saying like。

If they'd found this approach earlier， more of the compiler would have been structured in this way。

Of having untrusted code that figures stuff out and then just validating。

The output validating that that step is correct。After LTL location transfer language。

 which is the same as RTL except there are actual locations， stack slots and physical registers。

 After that it gets translated into linear So this is a linearization of the control flow graph so the control flow graph represented essentially as a set of basic blocks and now you actually need to put it into a single list of basic blocks so that's a step closer to producing the assembly from linear it goes down to。

😊，Mark， the machine， it's a variant of linear where the stack slots are mapped to actual memory locations in the stack frame of the current function for local and outgoing slots or stack slots and the calling function for incoming slots for arguments coming in。

Right so the sequence is essentially making things more and more concrete， eventually producing。PPC。

 abstract syntaxt for a subset of the power PC language and then。

Essentially an unverified pieceic code that takes this abstract representation of how PC and actually produces power PC assembly。

Which thing gets given to the assembly editor turn into machine code？嗯。

At the time when Con was written， this PPC used only about 82 of the more than 200 instructions that the Power PC architecture had。

 in addition to seven macro instructions， so instructions that end up translating to a sequence of assembly instructions。

I'm pretty sure that they've been doing work on this since then to。

They also support X86 and a verified version of X86。

 and I can't remember off the top of my head if CO also supports other back ends at the moment。

But this was the initial work。Any questions at the moment about？

There's a very high level overview of concertt。嗯。One thing I will point out， though。

 that a verified compiler is still a compiler， right。

 We're kind of seeing the classic stages of compilation here。

 Just the cool thing is that it comes with proof。😊，The verification that。

This compation step is correct or a verified validator， validating that it's correct。Okay。

 I was just summarizing what I said for those who are looking at the lecture slides。嗯。

One just closing remark about this。So the key thing that we were doing is the reason why we wanted the semantic equivalents was a way this was a suitable or strong enough notion is that it preserved specifications that if we had done some reasoning about input and output behavior of the source program。

 then that would carry over to input output behavior of the target program。

 so if we reason about the fact that the source program correctly sorted a list fantastic。

 the verified compiler guarantees that the compiled version will also do that though。It turns out。

 though， that if we think beyond functional correctness， the idea that given some inputs。

 the program produces appropriate outputs， if we think about things like security requirements。

 it turns out that this notion of compiler correctness is not actually enough。

And this is really because a lot of security requirements that we're interested in are not actually functional specifications。

They're not actually ways of predicates over inputs and outputs。嗯。

This is an area research with the my group， this idea of。Secure verified compilation。

 how we sort of take the ideas from verified compilation and think about appropriate notions of secure compilation and then being able to prove them。

嗯。This' is an exciting ongoing area that's sort of building on top of this notion of verified compiler correctness。

Okay， any questions at the moment about。Verified compilation。Okay， then。So。

In the last 10 minutes of lecture 153 for the semester， what I want you to do is cast your mind back。

Go back。Way way back to the beginning of September。

A comma gentler time when we thought about a compiler。

And first saw this diagram about what this course is about。 This is a slide from the first class。

 this idea of taking source code， expressive high lab track code and producing target code。

 low level code。 It's hard to read， but there's not much ambiguity or redundancy。

And we dug into this box in the middle into the compiler。 We saw various stages， the front end。

 the back end， passingsing， elaboration， lowering， optimization， cogen。And。

That was what three months ago， almost exactly to the day October November yeah three months ago。

 we were actually covered a lot of ground since then and so I'm showing you here on the next few slides。

 not just a handy study technique slides view to actually like see all the various topics wereve covered but also to take a step back and actually to reflect on how much ground we're actually covered from looking at assembly code。

 refreshing or learning about X86 memory layout calling convention。😊，And of course。

 homework too of implementing an assembly an X86 interpreter to intermediate representation。



![](img/d6882e73cf5475171596d78b21e177b9_3.png)

Various forms ending up motivating LOVM。As an intermediate representation。

 digging into the details of LLVM， moving on to the front end， Leing and pasing， recursive pasing。

 LL parsing， LR pasing。

![](img/d6882e73cf5475171596d78b21e177b9_5.png)

A slide into Lo where we took a step back and thought about the broader implications of open source and free software that builds a lot of the compiler infrastructure that the world uses and both the freedoms that enables and the responsibilities that come with it。

嗯。Diging into。Compiling functions， thinking about functions as values and languages like Ocal。

 how we end up implementing that， looking at type checking and of course。

 getting familiar and comfortable with judgments and inference rules。

And then exploring that in terms of subtyping。Looking at a whole laundry list of optimizations。

Understanding what they are， learning about data flow analysis as a way of understanding what's going on in a program and a function in order to enable these optimizations or enable various correctness issues。

 digging into the joy of register allocation， and finding putting at some of these algorithms。

 these heuristics for doing so。At the end， in the last couple of weeks。

 we looked at compiling objects。Thinking about what object oriented programming is and how we end up implementing various parts of it。

 last lecture was garbage collection and then today verified compilation。

So we actually really have covered a lot。It's been。

Really from the beginning to the end and in the homework assignments assignments that you've worked on。

 you've really got to touch the compiler at pretty much all of these stages。嗯。So诶。

This of course was a toy language that we've been dealing with the homeworks with scaffolding along the way that you did。

 but the work you've been doing has definitely been building on each other and you have essentially been able to put together a complete pipeline from a pretty cool high level language where maneuvi writing really interesting programs are out。

They actually go through the lexing， the passing lowering to intermediate representation into L of VM from L of VM into X86 and actually producing the executable code you've actually built something that goes into wind and that's something I think that you should all be proud of and reflect on as kind of really nice thing that you've been able to learn about and accomplish。

I think you've also gotten the foundations for compilers， even though as I said。

 this has been within the context of a homework assignment。

 So one of the things you could do is you know think about that open source thing。

 start digging into GCC or L of VM and look at the framework and the infrastructure there either use it in your own projects and beyond or to contribute or to think about it or at least go and understand what's happening in these complex pieces of code that hundreds of people are contributing to that really do support as we've talked about some key infrastructure and many。

A。Throughout the world。So what's coming up next after 153 after this lecture。

 there is of course the exam and homework X on there as well。

 But if you're interested in digging into other courses that look at similar material。

 you've already heard me mentioning 152 a number of times and I think these courses really go hand in hand you absolutely take one without the other。

 but this idea that a lot of what we've been working on some of these incredibly complicated。

Algorithms or ideas or variants in the compiler these really rise out of the theory of programming language that theory enables us to conceptualize to formalize to abstract away the details and get the right way of thinking about how to implement the compiler and I'd say it goes the other way as well that as people think about languages and think about which features are useful to even try to formalize and reason about and add to a language implementation details are a key concern It's pointless adding magic operation that makes every program super efficient to run but is impossible to actually implement in a compiler。

😊，So that's going to be taught in the spring by Professor Arman。

 I'm going to be teaching in the spring a new course， formal methods for computer security， CS2，5，4。

 It's going to be using。We might end up touching on secure compilation。

 but it's also going to be touching on some， again。

 moving back and forwards between thinking about programs as high level source things versus the low level machine details。

 thinking about the right way to formalize and reason about that with respect to security。

This will be the first time this course to be taught。

 so I'll say this at the beginning of the spring when I start teaching it。

 but it will be a bit bumpier than the undergrad classes have taught 153 and 152 in recent years。

 so expect a little more confusion and disorganization。But of course。

 I think many many people interested in compilers are also interested in systems and architecture and indeed as we've touched on throughout the class。

 these things really go hand in hand， I think these days you don't build new architectures without thinking about the compilation some of the most effective compilation really needs to be co-designed in many ways with the architecture in order for them to get the best out of things。

And， you know， we touch on so many aspects of lower level systems as we go through this。

 thinking about。Say the memory address space as we think about。Programs， separate compilation。

 linking， runtime support and so on， all of these things tie in very tightly with issues about operating systems and so on。

And then of course， if people are interested in research， feel free to come and chat with me。

 happy to talk about projects， if you're interested in something that's related to compilers as well。

 I'm also happy to help you identify other groups or people around the university that might be worthwhile chatting with。

With that I also want to thank you all very much for your time。

 attention and engagement in the class， particularly for you all who are in this room who actually coming to the lecture I know I said it was expected but I was also very careful never to actually take attendance at class so I appreciate you all actually showing up and engaging asking questions keeping me honest and but also making it a lot more fun not just for me up here in front of the class but also for everyone in the classroom including those watching it on lecture video actually having that interaction in your engagement and that's really been obvious and clear how investor engaged many of you are in the classroom interaction but also on Ed and also in your engagement in the homework and other things so thank you all very much good luck with any final projects but for this class and otherwise and I'll see you at the final exam in a couple of weeks Thank you。

😊，Okay。我。系系写咁多。靠什。Well I started feel I shouldn' never be poli。好。



![](img/d6882e73cf5475171596d78b21e177b9_7.png)

![](img/d6882e73cf5475171596d78b21e177b9_8.png)