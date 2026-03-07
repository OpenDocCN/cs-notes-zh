# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p13 P14 5 -BV1qBqPBYEy1_p13-

Oh，那 continue you meet。You can't hear you didnt。嗯m。I think it's not too horrible。

 but it not look weird。I didn't change anything maybe not to say figure out its echo cancellation。

 right？Okay， so I got the recorder running。 So we'll have video with。

With the dialogue and we've got the slides and。I think we can start as everybody here now still a couple of people drifting in。

We'll start at the appointed hour。or。The unofficial appointed hour Yeah， exactly， exactly。

 it's a b with tradition。What time is it there，10 PM？At 11 pm。

Okay you're bringing me I'm not doing any Friday party now， Yeah， right。

You should have like a bear or something。Yeah， great， absolutely。😊，it's something to aspire to。

I have number hipster Poken instead。Okay， I think， I think we've got everyone。Going。

 so welcome to week 10。Yeah， I think it's week 10。Just a few more weeks left now。

 and this week we have another guest Carlfrederick Bols is joining us via Skype from Germany。

 Which city are you in？In Hamburg， okay where it's 11 pm so thank you so much for deing to call and do this it's such an ungodly hour for a lecture。

Carl has been working on Pipe piee for。5 years，6 years more 1111。

 I didn't even know the system was that old and has written and call at a number of， I think。

 very good papers on the techniques of tracing and meta tracing。

 I gave you a couple of things in the reading last week。 suggested you take a look at。

 but the one that you really absolutely should have read was the hot path paper。

 which is the basis of tracing and hopefully is enough setup up for you to get the points of meta tracing。

 which I think is a very cool idea and not the easiest thing to get your head around， though。

 So today we will hear all about that。 I will get out of the way and leave the floor to call。

 Thank you。Thanks a lot， Mario， and thanks for inviting me。So I'd like to start。

 by just encouraging everybody to interrupt。こあの。If I start speaking completely incomprehensible nonsense。

 there's not much point going on。So just like tell me somehow and and I try to hear your question。

So what I'm talking about today is Mari Audrey said， a project that I've been working on。

For quite a long time now， and let's go to the second slide。And the third slide。

Whi is basically a sort of slightly different approach to constructing virtual machines than the one that is typically taken。

 and I guess also the one that you've been taking in your exercise so far。I mean。

 since you're sitting the course， you already know that a lot of languages are basically now executed by virtual machines。

Like Java，net， Python， all the all the hip dynamic languages， JavaScriptscript force。

And of these most of the Vs that are actually used in practice on the production virtual machines。

Are written by hand in CC+ by large groups of people or small groups of people。And V ends。

 as you may or may not already be in the closer of the covering。

 are actually not very straightforward pieces of software。

 so they can be quite sort of geniusedious to write and quite。

They can take a long time to get the bucks out and it can be costly in terms of the manpower that you need to get them to an interesting point。

And this is particularly true if you have a sort of very complex dynamic languages。

 dynamic language like Python or JavaScriptscript or whatever。嗯。So of course next slide， please。嗯。

Of course， a very important goal of virtual machine instruction is performance。

 and since interpreters are often not fast enough for the big applications that virtual machines are used for。

 the virtual machine needs some kind of justin time computation system to bring that performance to an adequate level。

And this again， particularly true for dynamically type languages where none or not can be figured out about the program。

In advance by just looking at。Bs hospital。So what does the architecture of a virtual machine look like I made this nice idealized diagram so the VM of course needs some way to express the language semantics of the language that is supposed to run virtual machine and then I mean there are these nice proper boxes so there's another component that the did compiler that will basically take programs in the language and turn them at runtime into machine code taking into account runtime feedback or whatever and then I made another nice separate box which is basically the optimizer that takes whatever intermediate representation that did uses it applies the number of transformation steps to hopefully improve the performance further all that is sort of embedded in something I just called general runtime which contains to apply the garbage director or integration with the operating system or the。

A dreading model or whatever， I'm not really going to talk much about the engine part。

 so I left that slightly weight。Okay， so this is a nice theoretical model and progress that in practice this nice component model is not really true。

Kl quick interrupt， we see your slides， but I've realized we have no red channel。

On the second projector， so the colors are a bit off if you have any color distinctions that are important。

 we're going to have to。The I realized when I saw your small talk balloon and that it didn't look right。

哦。Also basically the gen part is not much read at the moment kind of gray Yeah okay， okay。

 so that's fine I I think we'll be so if people look if you look puzzled by the pictures then。嗯。

Do speak up a little， so there are colors， but they don't carry a lot of the。

Hopefully there isn't much semantics in red。Right， I mean， the red not grade。 so what I。

The did is ray， which is the very my screen， I think really fine。Right。

So now we get away from the nice idized picture and look at what a real g site。I mean， in fact。

 this doesn't happen but are very large and complex and engineering aspectss that are maintained by like。

诶当读 people分参与毒 people。They're rowing over many years。In some cases， decay。

 and the architecture is often very， very complicated with different bits of the system sort are completely tangled up in each other。

And sort of that's what this weird diagram is supposed to show。

 like the runtime is often deeply integrated with the language the of the independent language。

 which is often very deeply intertwined with the Duke compile and of course。

The optimizations and the language methods are also messed up because they're mixed up because the optimizers need to know how the language works and so on。

And this sort of big tangled mess means that it's very hard to actually change the language that the game is running right so if there's a new feature。

A new language feature that is supposed to be integrated。

Just implementing that can be annoying because there's some sort of optimization that depend on that feature not being there in a corner that is completely forgotten or other random interactions between things that are very hard to。

And that is particularly a problem for languages that still evolve a lot and JavaScriptscript being one example。

 there are actually a number of new JavaScript features that the aid does not implement particularly efficiently because doing that would be really hard it would be quite deep。

I mean， not deep， but let's at least say very annoying changes this to all the rest of them。嗯。

Another problem is next slide please。嗯。And then further one， so we were applied7。

Another problem is that， of course， there's not just one BM。 So， I mean， there are many different Vs。

 and most of them share absolutely no infrastructure whatsoever。

 So every VM implements all the bits of the value director， all the bits of the。

Of having optimizer back end and so on again and again。

So it would be cool and the talk today is going to be about that。

 It would be cool that we could get away from this sort of tangled mess from these tangled messes and move towards。

An architecture diagram that looks more like the nice idealized boxes than I showed you at the beginning。

And this is sort of the goal of the project that I'm going to tell about now。Next slide， please。

So the goal of this project is basically to separate out sort of different concerns that one has when implementing virtual machines。

 So on the one side， there needs to be a way to express the language semantics。

 obviously of the language that is implemented。On the other hand。

 one can imagine that sort of a lot of g compilation issues are completely independent of those language。

を空てれる。And there could be a set of generic optimizations that are sort of shareable amongst a large number of virtual machines。

But then it's， of course。Not really realistic to believe that all optimization are able are expressible in a completely language dependent way。

 So there likely also have to be some kind of。Language specific optimization。

 But what we call it basically those four things can be separated and reused。And next slide， please。

This is indeed the goal of the art project。どて。So what is our weapon？

The word Power license stands for restrictedive Python。

And it's basically a programming language that was designed to write interpretly。

And it's called restricted Python because。Python itself is quite dynamic dynamic type and our Python is restricted in such a way that it's possible to take an our Python program。

 analyze the whole source of the program， find out the type for all the variables that occur in the program and then transform that program into C code。

So it's basically our is a subset of Pyth that is compile to。And so basically。

 what you do to implement your language with our Python is you write an interpret what language in our Python。

And then the other translation tool chain comess， takes your interpreter， produces C basedM。

And in that transformation process， a number of features are added to real interpreter that are not really explicitly in the interpreter。

And the most obvious， one is a dollar factor。So the interpreter itself is written up apart into garbage like language C is not that means when translating your operating program to C the garbage collector needs to be somewhere and needs to come from somewhere and it comes。

Basically from a transformation step that while the interpret being transformed to a C program also sort of。

Bs in the boundary structure to the size。So we've used this language for a number of people。

 the number of interpreters， and the most mature and the one that I will talk about most today is called Pipe。

Which is a Python interpreter in our Python， which is also obviously where the name come from。

And actually， the art project。I mean， sort of the honor in time is really the other way around。

The original project was the Pipe project and in the development of the Pipe project。

 it became clearer and clearer that the art fighting language that was implemented basically only as an implementation vehicle was also very useful for implementinging language language Russian streams for other languages。

And as we already hint that， it's a pretty old photo exercise。3 years。

 something like 13 years old that， and it has like received quite a little funding。

A large number of person years have heard down their。Right， but so far。

 what I've told you is not actually that interesting。

Basically our respect language that you can use to write the interprets and then comp them to see。

 I mean， so far。Toorrow is like many other languages。Those I do that can be comp。

But what makes our pipeline interesting， next slide please。Is。

The the way that we also are able to integrate the doesn ham compile when taking an interpreter and transforming it to see。

So and the approach how to do that is called meta tracing and how meta tracing works。

 I will explain in a lot more detail sort of in a few slides。

 but the basic principle is that you take this interpreter in ourpyython。

 it's compared to C and while the outputython interpreter is transform to C。

 there is another component inserted into the final C executable， which is a meta dig。

 which is basically a generic reusable just in combination infrastructure。

That can be used for basically any interpreter that's written in our。And。

So the method is contains a lot of sort of the generic doesnt have relation infrastructure that you would expect。

 for example， there is a number of stack for various machine architectures like whatever Intel arm and power and a few others。

 there is integration with the target operating system that the garbage that the Gcomp needs。

 for example， getting executable pages of memory from the OS something like that。

And there's also integration of the the then also inserted into。呃 the反。

So this insertion of the dipcomp into the finite exutable is mostly automatic。

But it's not completely automatic。 So the interpret author needs to。

Help this process by basically adding a number a small number of source code notnotations into the interpreter to sort of tell the process where like how the interpreter works a little bit。

 but that's not actually a lot of code so there's like a couple of。

Like 10 mine or something like that that meant to be added to the interpreter to make the insertion of the data。

And other words。We'll seeing examples to as well， but the basic idea is that it's necessary to tell the process。

Where the main microdispatch loop of the the chart is and which variable in that microdispatch loop stores the program culture。

Right。Next slide， please。嗯。In addition to to this。Gric reusable Jit。

 there is also a generic reusable optimizer that is a bit tangled up with the Jit not too much and anyway it doesn't really matter when you're just writing interpret in ourython because you can just reuse the optimizations that are already there。

And the optimization are sort of what do we expect。Ill talk a video of the later。

 but there's nothing too。Right， so now next slide and the next one， immediately like 13。

So let's talk in some more detail how this meta tracing works。诶。So you read the hot pot paper。

 so you will know most of that， but I will still basically recap it。So one of the。

 one of the cool ideas from。When tracing Js were invented by D Hopark。

 was the idea is that if you have an interpreter for language。嗯。

There's this idea of adding a very simple component sort of to the side of the interpreter that is the tra gate that makes it possible to use that interpreter to produce machine code for the programs of things。

And that is basically the trait。Next slide。So you take the interpreter。

 you add the tracer and optimize on the side， and they can help you to instead of just interpreting also producing machine code from Europe。

From the program。 And the way that works is that。You start out running your program completely regularly as you usually do as an interpreter by just interpreting it。

So the interpreter happy executes the bycode of the program and but while doing that it's also just a little bit of profiling to figure out what。

Which part of the program I you particular of？So another big insight of the tracing date approach is that in order for a program to run for a long time。

 I mean，'s not not such a。I mean， the inside itself is easy。

 but that is not of what follows on that its not completely。

 but the internet is in order for a program to run for a very long time。

 there' is usually some kind of loop that is running manys。

So the idea of a tradecing do is that it tries to focus its。Compilation efforts。

 particularly on these Mongwa groups within a program。

So when the interpreter starts out running the program on top。

It basically does a bit a to figure out which loops in the program are the loops are executed often。

 and it does that in usually very simple ways by simply having some kind of culture per。

 and then you increase。For configuration you increase the counter and if the counter goes over a threshold you say。

 oh， I've already run that a thousand times in the interpreter。

 it must be an important one so it probably worked to focus some computation on that loop。

And so once the threshold is reached。The interpreter tells the tracer over there something important is happening here。

 it's probably worth to start looking at what I'm doing。

So what happens then is that the interpreter keeps running。

So it keeps executing that loop it strictly the next situation。

 but the tracer is also enabled and what the tracer does is basically just keep the tracer keeps a log。

Of the operations that the interpreter executed to run the。

And usually the norm is really simply in the form of the vitalcodes that the interpret of youre executed。

When when exit the loop。So that goes on for a while。

 so the trir simply makes a longer and longer list of Pcodes that were run by。うの。And in the end， the。

Is at the end of the loop is reached again。 and the loop would start back at the beginning。

 And then that ther said， okay， I recorded one situation of the loop now。

 I'm now going to turn that into a piece of machine code， optimize it。

 turn into a piece of machine code that now corresponds to。To the that they took。And actually。

 so one of the really interesting things that happened of as a side effect of this approach。Is that。

You automatically get inlining of all the functions that are called in this。Because。For the tracer。

 it really doesn't matter at all that there is a call instruction in zoom。

 It will simply ignore that call instruction and instead record the operations。

The bike operations that were executed when running the call function。And in that way。

 all the functions that are sort of called from that loop。

Are simply in lineed through the trading well， which means the tradingcing did follow as a。

In the way that is constructed， inlines inlines stop very aggressively。Okay。

 let's look at an example because that wasnt probably little abstract go to the next slide please。嗯。

Okay， this is， this is a completely soon example of a。

And imagine tracer for a p like language So we have this。We have this sequence of instructions and。

Let's assume that the sequence of destruction occurs in a commonly executive。

 So there's some loop around that， but I wanted to sort of have something small。And so the Jor。

Determined it's important to trace this bit， which it starts tracing and it starts tracing and doing。

During the tracing， the value of the very axis。So next slide。嗯。

So the Chinese studies we call it look something like this。嗯。There are all these guard instructionss。

 and I'm going to explain to you what they are because there was actually to execute。

Peration by x smaller than0。This is supposed to be a dynamic language。

So in order to figure out how to actually implement the smaller。

The interpret interpreter first needs to look at the types of。

Of the arguments of that of that instruction。 So at first it these， okay， X is at the end。

So to make sure that this。Again， through the next time building the choice。

 it introduced insert the type card， so it says make sure that x is an image。

And then the other opera， the same thing happens for the other opera。

 so there's another type guard it says。Make sure that's zero。It is obviously， but， I mean。

 it's dont recorded it。And then we come to the end。

So we execute the next then and then there's an if based on that， so we record again with the guard。

That during the tracing of the loop X was smaller than the0， as is much smaller than zero。

And then we're in the second in the L case， so we check again that x is an end。

 we check the two in the end， then we do the addition。

 and then we're after the amount box we check that X is an end。

 check the three is an end and do the other edition。Okay。

 and already we can see there's a lot of redundancy here。 we check， I mean， on the one。

 we check the types of constants。So the type of zero is obviously always in。

 so those can just be removed by the quantum。And then we repeatedly check。The type of X。

 So after after。We saw that Xt one， we don't need check that again。就诶。

The optimizer would turn that into the slide。Something much shorter。

 and it might also fuse the two additions together to just like immediately add five you first add two in then。

But the the important part that's thrown in there is the guard that checks that xs a need not less than zero。

Okay， so and we need to think about those cards some more。なか。So as we saw。

 every time the tracer hits some kind of condition in in the loop。

They need to turn that condition into art。And the reason for that is if later we turn the trades into machine and we run the trades。

That traces the only values， I mean， that traces the linear path。

 it's just a linear long of operations there's no control flow that at all。So。

If we execute the tracelature and one of the age statements goes another way than the way it did during tracing。

That。The machine code is not actually valid for the whole execution。

 and so all the cases where the proposal could have diverged。

Need to be checked with a are to make sure that the control flow is indeed the same as when the face recorded。

And so if one of these traits， if one of these cards fails。

 then execution of the machine code that was generated can actually continue because we， I mean。

 would be a bad idea to just follow some random oil control that we might have sequence once。

So in the bad phase， the execution of the machine code stops and instead the traveler is。

Started again from the point where the bus fade and to go down the other path。And actually。

 one of the surprising thing is that and that is not necessarily obvious our。

 but one of the surprising things is that most artists don't fail。

So if you actually do some statistics for real systems。And you look at how many guard ever fail。

 it turns out that 90 to 95% of the guard never fail。And then of those that failed。

 the very large percentage。俾安哋嘅专查安咗讲。Right， but okay， so it's nice quite often we stay on trays。

 but then of course， sometimes there are conditions in a loop where both sides are equally take right。

 so there is going to be valid for those conditions that。

And tracing needs to like the approach for tracing， needs to deal with such a situation as well。

And the idea for that is if you have a guard that fade。

 you basically increase some kind of counter to remember that this guard fades lot time。

 and if that counter goes over another person，So is that say， oh， this card had paid like 50 times。

It failed all the time。 we need to do something because going back to the interpreter and then interpreting。

ですま。So what happens then is that the tracer will start tracing from the point where it does fails。

 produce another piece of traces， like another linear path that take some other control profile path through the loop。

And then produce machine code for that， and patch the original machine code so that the God failure that used to go back to the interpreter for the commonly fade art now goes to the new piece of machine code。

 and then in that way， sort of in a piece by piece fashion。

 we cover more the tracer will cover more and more control paths through the loop until in the end。

Almost all the partss are covered， I， I mean， ideally all the partss that are actually taken are covered by trace。

 and then we don't actually be themhiko anymore。Right。Okay。

 so it may have been a little bit confusing how the tracer sort of goes from interpret to choiceject urine。

 So on the next slide， I had make a small。嗯。不能。State diagram in which sort of states VM with the choices they can actually be in。

Anyこ so。嗯。When you start UVM and start running the program， as I said。

 the program will always be interpreted at first。So we started the upper left corner。

And run the program until the profile of the interpret says， oh。

 this film over there seems to be important。So at that point。

 the vehicle able will transition to the tracing component。

 it still keeps running the interpreter but then。At the side of the interpreter is also the tracer that sort of records what the interpreter does and that goes on until the interpreter has run loop another full duration balloon loop。

 that means the traces corresponds to loop， so the tracer hands it down to the optimizer which will optimize the produce machine code。

And thing the loop， the next thing the the Shier would do is run another situation of the loop。

 so immediately we can go from the optimizing component over to the machine code that we just made。

 we just jumped there and immediately run the next situation of the loop that we just trace in hopefully the efficient machine code。

And we will just keep that as long as the control flow of it doesn't diverge。

 we can happily execute a very efficient machine code version of that， right。Of course， I mean。

 usually it's not going to be an intuitive view。 So at some point either。The loop will be next。

 which is done by a guard or another particle tape， which is not done by another guardte。

So at some point， we believe leave。The running of the singlele on the right。

 and I admire that failure and go back to the。And now there's basically two edges missing。

One edge is kind of obvious when we'。We have we running along。

 at some point we hit a loop that we already made the trace for。

And then we can go directly from the interpreter to the running of the traces that we made earlier。

 of course' be passionateing the trace and connecting it to the loop so that when we hit the same later。

 we can reuse the traces that we don't have。Right， and then there's another。

 there's another like the。The only missing tradition is we really trace a garbage trade。

 running a trace， a garbage trade， we already know that this a garbage trade often before。

 and then we go directly from running the traces to tracing the path that starts from that fame guard。

Trce that until it hits another bit of something that we know and then basically patch in that side trace。

Right。Okay， so this is。So this is the basic idea of how old tracing works and I think it's sort of。

I'm going here to breathe in for a little bit because it's quite different from sort the typical compilation approach。

 which is a method based where the compilation code is a single method。And and sort of just。

Thinking forward。 I mean， does that approach make sense。 Are there any questions or。

I have a question。 I've read a bunch of the papers。I've never seen an answer to this question。

 so maybe you can answer it。What。The situation that you describe works fine in the circumstance that each individual。

Interpreted element has no internal control flow of any sophistication。

But if you imagine a situation like， you， a small talk having a bit more primitive。

the viball is one bike out。And you want to sort of trace your path through the implementation of that bycode or that premiseitive。

 how do you adapt the tracing into that situation right， but you just not do that？

That's an amazingly good question It will also actually。Very directly into into what makes me cool。

 I think there are two answers。 What the tracers typically do is that for a lot of the bikecode。

 they then have special logic。That says。I know if I trace this bycode。

 I also should record some extra information because the Bcode has some internal control flow and I need to sort of explode that bycode into。

Syntatic some， some things， right， A very good example is really already。Something like an addition。

 you can follow in the kind of maps to a metaphor， but there's usually some fast pathway for it。

Right， so already you want to explode that into oh。

 does it happen to be tus then go do this special pathway。

 if not just do the normal method with them。But basically the way it's done is that in the tracer。

 there's a special piece of logic for every bikecode that has internal control field to do that。

Right， okay。And actually that is a very good， I mean， yeah。

 it will be a great saving to the next slide but let's see whether there's anything else there I can answer。

 yes。If you do that， you're going to if you have really。A loop that lives for a long time。

 then you're going to fill up your。Iterations。Is there a way to turn that back into loop？いや、あ。

あ right okay so。So what happened is？You don't really trace all theur balloon， right。

 you just trace one。And then basically every trace， every simple trace is really always a loop。

 So every trace that you make always always。With a junk factor。到嗯。So in a simple model。

 all the traces are， and not only those traces that don't actually starting the interpreter。

 but then start ci。They are a bit more complex， but in the in the very basic tradingcing model。

 all of them are loops and will never sort of trace many rating。 you are always trading 71。

ButHow are the iterations called？How theerations are the iterations？Laundgeched。

Do they have to go back through the interpreter？No。

 it's really just you will really emit jump back to the instruction that to the first instruction the trades。

 right？I mean。That's really the only way that it becomes efficient。

 if you need to sort of jump back between J and interpreter for every iteration。

Oh like you would have a long for。那 that is that okay。Y， what happens in here at Luke？Ittains a loop。

Do you throw away the first loop sir？啊到。There are many answers to that， I mean。

 so that kind of starts to be the area where the tracing gets differ a lot。

The basic idea is that you basically turn the loop inside out。

Because the loop that is actually the hottest in the nest loop situation is the inner one， right？

So what happened is that you make a trace for the Nurulu。

And then there is a garden there that says that is for the situation where the inner is finished。

And then since the album also runs often， that guard paid a lot， right？

So at some point we will start tracing from there， and that trace corresponds to modeur of the outer loop。

Which will then jump back to the industry。so in that way， that the。

So the inner loop becomes the important loop， and the other one is this weird side part。嗯。But。

This is this also starts to be the place where trading gigs。Are not ideal， right。

 So if you have very complex controlled roads with deep atlus。系咯。

Very complex conditions inside where the path through。That positionists are very unbelievable。

This is the kind of situation where tra did not produce the best。嗯。O， how would you consider。

cur of policy do consider。将来。Right， that's another excellent question， though。That again。

 depends the build the system。So in pipeline， we don't。 In pipeline we get turned into。

A piece of machine code that does an actual call on the at level so that the CPU stack is used。

But then for example， I'm not going to talk about it today， but we also have this a record scheme。

And that it's very important to actually turn。To turn recursion also into a loop basically。

And that's not actually not that hard。 So if it's tail recursion。

 it really simply directly responds to loop， but if it's really recursion that goes up and build stack and the need to go down。

 will' turn it into two loops， it turn into one loop that builds up stack frames until you reach the final condition and then it will build another loop that sort of removes stack frames。

But sort different tracing this have。They put protein there。There questionさいあ the same question。哦，O。

So shall we go do。O，那这。So to go back to Mari's question。And I always send。In practice。

The model is not so nice that you keep your interpreter and you have a completely pure box at the size that just peaks what the interpreter does and makes nice code out of it。

Because in practice， a lot of the logic of what happens in the language need to be repeated in the tracers。

 because quite often bycodes have inner logic， so the tracer needs to sort of repeat。

The semantics on the bikecode， both him the interpreter and then again in tracer to sort of expand it into like micro instructions or to optimize it better or stuff like that。

So like。The nice picture is again not true， but it's again quite messed together。And another problem。

 I mean， of course， the problem of needing to start from scratch where every language is also known phone because every language tends to have its own micro set。

That means if you want a tracer for a language with a different bicycle concept you again need to start writing that tracer from scratch。

And that is this problem of not being able to reuse the tracing component is the one that meta solves。

Next slide， I'm on slide 19 audio you as well。O。So manufacturing and I mean。

The idea of mass tracing is a little bit mind bending。

 but actually it makes sense when you start thinking about of bit， and the idea of tracing is that。

 okay， the problem is。We had to write a new tracer for every five% of every interpreter。

 thats the point。And we had to replicate sort a lot of the semantics of a bodycode within the Scher。

the line。 So what do we do， What we do is we。we don't actually place the tracer next to the interpreter。

 but we place the tracers in the figure below the interpreter。

 which means we make the implementation of the interpreter completely transparent to the tracer。

And that means we don't actually trace iteration of the user program， but we trace。We the。

The lines that are executed within the interpreter source code。

And trace what's going on there then I mean， you may not be able to see that。

 but then also why the color of the traits changed from pink to green because we nothing in or and green we from gray it a slightly different type of things。

Right， so anyway， the trace will now no longer contain vitalcodes。

It will now contain operations that corresponds to the source code of the interpreter and the things that are going on in the interpreter。

 that means the operation there are a lot more fine ranges。诶 ok 做。

What you know since you since I look at your exercises is that simple interpreters are actually big groupss。

 I mean particularly bi interpreters you say they are a big like endless loop that just says give me the next fivecode and there's a switch over a bi it is and then you go somewhere so。

This is great， right tracing this loop is perfect because we have a loop and we spend all our time in that loop。

 So one of the conditions for when tracing this health is already met。 we have a loop。

 But then the problem is the control flow through that loop is not actually very predictable。

Like let's say we execute some programming in our vital interpreter and we execute addition vital。

The probability that connects。Housing bycodes are also additional bycodes is very low。

The control flow crew that fight to dischargepatch tube is not following a very predictable path。

 iteration after duration。So it appears like we are stuck， right。

 It appears like tracing the interpreter is an awful idea because。Ever stay on the。

And the insight is that we don't actually just trace one iteration of the bike dispatch。

 but we trace many。And。We trace so manyerations that the length of the trace matches up to a loop on in the program。

So that means。嗯。We start tracing when the interpreter executes some kind of here。

 some kind of wipe that says here is where the loo start。

 and we trace many iterations of the bycode group through many different bys。

Until we hit a jump back that goes back to the beginning of that loop that we started facing and then we stop。

And that means our trace now contains operations that corresponds to source code level operations with interpreter。

 but the length of the trace。Still correspond to loops in the program that the user act。

that is why I want top that in。And in that way， we get our predictableuc profile。

Because since the loop that is running on publicly interpret interpreter， right。

 we will have political control flow。嗯。We get， again， a trace。

Where we can sort of likely stay the trace for many duration of that trace which corresponds to many bycodes by one part to the property user program。

Okay， so again， let's pause and see what questions there are。I have a question。ok。

No I'll say it for the end。好。How do you detect？对。す。You don't know anything about the。

Final target language。So how do you know that you're starting over？Con certainlyly doing。Right。

 that's one approach。 And， of course。I mean， I mean5。

 so what we do is there is we asked for some level of health by the interpret office and that will be that I mean。

Again， a very amazing thing because it will help me get to my next slide。这是这的。So。

What we asked the other author to do is indeed to give us some information about the interpret。Okay。

 we know that the interpret is slightly a lose， but。

Quite likely the bike of this will not be only new in interpret。YeahI mean。

 there are probably the other in terms of the state for example， this。

And so it's not necessarily the case that we should apply widelyly figuring out which of the loos in the trouble otherwise about this。

So what we asked the interpret instead is to basically add a little animation the false code that says。

 this is the group that focus on this one。Right， that's the one piece of information that the asked the interpreter offered to give。

The other piece of information is what we ask the governor for is。

To mark the instruction that can lead to。The closing of a loop at the user。

And let me go to the next slide， which is 21。So those are basically the two ans that you need to add to this。

Lis paint into the room。でした？So as a opposed the why do。

 which it means loads an in and then there's bridge which is just through the statement for each instruction。

At the beginning of the micro， you need to say here enable enable there's diploma functions we need to call and that tells the it。

This will comes。And then in the branch instruction， you need to。Call another。那你放清楚其得就啲。That。

Its called only for those brancheses that compose groups。

And branch of symbol looks exactly if the jump that they do go backward。Because I mean， in other。

 a new situation where you repeat repeatedly execute the instruction can be from market。

And that can only happen if the problem culture decreases at some point。So basically a branch。

 we need to call to at the foreign instruction only if the dump。And with least to him。

The administrator can do highly enough information。To。And figure out， I mean。

 do do some profile because it can basically。At the place where you can it。

 it can keep one counter her value of the scene。To see how often that hope power have already been。

That's the first thing you can do。 and the only thing you can do is。

canA tra if that comes is the threshold， which means it can。

Basically execute many iteration of that what we do until we did another branch that goes back。悭得到晒。

Because， I mean。我是さ。5。So another question。就呃。With this approach the generated trace would also necessarily have the instructions for fetching the next white code from the street right so even if you're in a loop you're still going to be fetching each white code and have a guard to ensure that is the same whitecode that you saw before so you start out be stuck with that problem。

And it then， I mean。It then the job of the optimizer to get rid of that own brand。

 and it's kind of obvious for that。Because so。이 파썬。Strings are availableable。

 That means if you have a function byyth string and you read a program。

You read an instruction at a fixed program counter， you can concentrate that read。

And then the switch to figure out what the correct cycle is can also be concentrated。

 so that way you get rid of all the operations that operate on the program counter and on the bycode straight。

 right。あ呢両方。我三。I'm still a little confused about after you collect the trace of。A。

When you loop back in the user program。How does the tracing jetit no to。

Like I've collected the trays， I want to start executing my native。诶我俾书意。Basically。

 every time the tracer hits an backward bunch。It checks whether the target of the branch corresponds to the beginning of the trade。

If that's the case， we close the。And in that case we can hand the traces。

 we will basically add a jump to the end of the trade saying， jump back to the beginning。

 we hand over that trace to the optimizeimr and then， I mean。

 there is some of the annoying code that then will jump to that newly generated。不 거。O。Right。

And we can always immediately use that machine code。We are still in that group that we just trade。So。

So。Do you咩。Do you map the index in the bycode to？谁 says。Yes， yes yes yes so。For a program culture。

 we keep an entry count。And an address， if we already made machine code for that loop， right？

So in thetro， we hit this energy grid。There's some code on maybe service that says。

 do I already have code for that， and it has just told them。So in the language leg。

Javascript with EBa， you would， there's another mechanism to take it。嗯。

That is not actually clear that it's a problem。So， I mean。

 either its a problem because you need to involve the puzzle and。If you do it。

 often it's just not going to be very efficient， right？

But the meta tracer doesn't actually have a problem with EO because it will simply trace into the par and it will probably pretty quickly say there's absolutely no use in inlining everything here。

So it will， it will just generate。A call that basically goes to the public as we look there。喂。

And Mari， to get back to your bit question， I'm not really sure if it makes sense to trace into bitfi because。

This it contains。Another complex loop。 So it's not like clear that you would win anything by ining all of that。

 right？But actually。If you remind me。The Poam group had written a paper about their art based。

A smallmall talk that indeed has a big has some interesting。Exper along。Thank you， okay， well。嗯。

So let's go to the next slide。I think we had on that。嗯。Right， actually。

 let's I'm referring back to one of the other questions， which is。

All the bikecode operations are still in the trace originally。

 there are more vestiges of the interpreter present in the trace and another very obvious example is staing equation。

Because then interpret stack base， then the face will basically contain operations that say， oh。

 read the stack at theest position I stored out there， into the stack counter， stack pointer。

 and so on。It's actually important that the optimizer that it has are good enough to remove the overhead of that sta manipulation。

 because otherwise the machine goal that you generate is just not going to be。

And then the other thing that I kind of want to hint at， I'm not really go into much detail is that。

There is a lot of sort of annoying technical details that are involved。

 particularly around sort going from the interpreter to the Frr and even more annoyingly going from the Frr back to the interpreter。

Because if a garage fails， it's possible that that happens several inline levels see。

And sort of going from that point where sort of the tror just denied everything but that an interpreter would really like stack frame and infrastructure going from one side to the other is technically。

Rather annoying， but。It's not。 I mean， it's just a matter of programming's it's not that deep。

And also， despite these technical problems， of the separation between the interpreter and the j is still maintained right because all the messy technical stuff is hidden in the j and as an interpreter although you just don't need to look at it。

Okay， right， next slide。So， as I said the。The tracer needs to contain sort of。

It does contain a number of all the typical compiler optimizations that you would imagine。

 so there is stuff by con folding， there's stuff for optimizing deep accesses。

 there is that code emination， there is strength reduction as all that kind of stuff。

So they are all sort of very。I'm surprisingur in a way， which of them are there。

 the thing that's kind of interesting is the fact that。They're all rather easy to implement。

 So one of the thing that makes。A tracing good fund is the fact that。呃。

The optimization stage is really trivial because the optimizer only needs to deal with the completely linear piece of machine air of face。

 so there's never any complex control flow that the optimizers need to reason about。

So all the optimizer does basically have one or two passes up and down the trace and basically just removing operation from there。

 and that makes sort of the optimizer stage significantly easier than in a method where you need to deal with control flow mergers and jump back and jump somewhere completely different by that。

So the only optimization that is。Sort of quite different from what many other dude have。

Is wonderful not。And that optimization is very important in the context of the dynamica。

That every tend to allocate a lot of memory。 And I think that。

The example language that you're using in your exercise also has their property and that is done for a very simple reason because primitive objects like integer that floats need to be fox。

 which means they need to have a little heat cell they get a little piece of memory on the heat where their value is stored in order to make them look like other objects。

And that means every arithmetic operation actually needs to look at two of these C cells。

 read their content， do the operation， and then make a go to the published page and say。

 I need a new piece of memory for the result。But the fact is that if you're these memory cells or primitive values。

 they often have really limited and a completely predetermined life。

And that becomes completely obvious if you look at a simple athtic expression like A D C。

So if you run in feed and T in an interpreter， what happens is that and they're all in they're all in What happens is that the interpreter will check the type of E。

 it will check the type of C， it will read the content， it will do the modificationplication。

 and then it makes a new box on the heat。Which is then passes to the next operation。

 which is a plus that intermediate resolved。That will do the same dance again。

 we will check the types， We'll do the addition room make the new box， but at that point。

 whether the result of the whole expression is produced。The box of the expression of B C is that。

 so that I was try to kind， but of course it's still worked to get rid of it。

So one of the very important and very language specific optimizations that we have in our patternython is basically's a path that can go through the traces and it looks at all the mammals that occur in the trace。

And it can remove allocations that have a short predetermined bike frame。And that means。

In particular， that all the immediate results of arithmetic like big arithmetic expression can move completely。

 That means if you ever a look at mostly does American calculations。In an interpreter。

 lots and lots and lots of garbage is going like memory garbage is going to be generated。

 but then after tracing， most of these allocation bar did removed which simply increases the performance。

But anyway， this is just the。And unless I am not going to talk much more about that now。Right， okay。

 so we were actually in a pretty good place。 we sort of， I mean。

 we talked about how the method is sort of inserted into the archive interpreter。

 what the interpreter often needs to do to tell the J where。

Like where the main room and where the dumps are and stuff works， right previous。The problem is。

 and we have some generic tightger accumulation done。Re use a lot of progress。

 But the problem is that the。The generic optimization cannot actually make use of a lot of properties of the language that the j doesn't know about。

And so let's go to the next slide。系唔运咗。嗯。So why is it a good idea。れなてかなことが。嗯。

mean why do we use this at all， I hope these students stuff。More people don't let me in。哈哈。

But I have to do something， the compiler can use information from the current execution of the program。

Right use logistic。さ。Absolutely basically， the power of the J comes from being able to look at what the complete run of the program did。

And give that information back into the foundation。そうす。And。

This is something that the system that we described so far is not doing that much。

It doing it a little bit because it does like it chooses control flow that happens to be that run often in the current。

 but it's not really doing。It don't really doing anything大ば。

And the reason why it can' is because while the semantics of the language are completely clear to the tracer。

But the racers still didn't know the typical ways that。The language is used in practice。

And that's actually， not completely obvious point。 I mean， one could think that okay。

The tracer can observe the interpreter， the tracer knows perfectly how the language works。

But there is still not quite enough information to actually do any good optimization because a lot of the ways that a language is used。

Are not necessarily obvious from theman。 Okay， that was hyper abstract。 that be quite quick。 I mean。

 in most in most。A very important optimization for optimizing opticalological languages is the observation that most methods call sites are monomorphic。

 which means that for most call sites。One very specific implementation of the method is called。

 and that is actually a very surprising result。 that is not present。

In the seman of thatlig language at all， in theory。

 it's conceivable that every single whole site will fall。Thousands of different methods of。

But that does not seem to be the case for any realistic estate program factor。

So what we need is a way for the language implement to be able to sort of。

Communicate these expectations about how language is used and practice。Back back to the face media。

And for that， because that information is really not present in of resource。And for that。

 there's basically a second set of things。 So the first set of thingss we're pointing out was the bidi numbers and the second set of hints is responsible for basically encoding。

Knowledge about the language that goes beyond how to execute the language and that goes into how is the language to believe。

And again， let's really look at that method called something that we talking about on the next slide for this。

诶。So as I said， at one method full site， it's quite often the case that always the same method is false。

 I think you will actually use the same。The same common property of ob only languages soon in your own exercises。

嗯。So here is a very， very rough sketch of what in of a method send Google Dr interpreter。

 so basically the same consists of two parts on the one there is a lookup and the lookup basically takes the class of the object that we're sending a message to and it takes the name of the method and then it will walk up or down the inheritality of that class and look at every level whether the method of that name exists。

And it will return the first place point。And the details I just left out here is don't know have that work。

呃And then。There is another function sent here， which actually implements sending of messages on the interpret level。

And it takes an object， it takes the name of the message。

 and it takes like from this arguments it some object of argument。

And so the way it's implemented it should be an osteoic for its class。

And then it looks at the method with a given name on the class， and it have a message method object。

 and then somehow at the interpreter level it will use some mechanism to actually follow that concrete method that was not。

So what we know because we didt logistic。Is that quite likely the method object that we the class object that we see in a specific sense。

A place where S is called in the interpretation of the program。

 the class is always going to be the same。And we can communicate that information but does always the same within which we see on the next slide。

And I think we call promote。And what promote basically says is。I expect。

The argument of the call to promote。To only contain a very small number of values at that pro phase。

So it tells the it， I'm pretty sure that at this place， you will only see one。

 two or a small number of classes when you actually run the trade。

And so during during interpretation that promotion is just ignored by what we trace。

The tracer willing will use the promote and insert the data at that point。And that guard says。

Check that the variable class。Contains this value and the value that it uses to compare the variable again is the concrete runtime class that was seen during tracing。

 right？So from what is basically a mechanism to be able to feed values from。嗯。

From runtime into the trade， so it can basically be made valuable to constant。And of course。

 that's only good。The variable cost really only takes on a small number of values。

 otherwise you introduce the guard that would just paid off on that it's never wrong。

 but it's not a good idea either。Right， okay， so now we know the constant value of the part。

But what do we do with that， it' still going to look up and look up it's probably very complex。

But now we can let's assume be a very simple language where you cannot actually change the inheritance hierarchy at one time。

 you cannot add new methods at one time， that means like classes are completely new and in that case we can add a another another。

Whi is on the next slide， which basically says that if you see if the tracer seal a call to look at with constant arguments。

It can completely remove that call and replace it with the results that will seem to address。

And we can't only do that because that I said， you cannot actually， mean in this particular language。

 you cannot add new methods。And now we run in a pretty cool situation because now the code that is generated for。

Or7。Contain the guard。 that takes that。We still have the class that we saw during tracing。

 and that immediately goes to holding the map。That was the。系。So with these two things。

We basically implement some kind of unit cash。But。An in cash is basically only the simplest thing that you can express with these to。

They're actually surprisingly powerful and in some ways we're still like a couple of years later。

 we're still discovering fun。反転にす病といいて思ります。But the building blocks are。

 I expect this variable able to be to take on only small number of values and basically a way to define。

Your own kind of fun important thing。If you call the abstract constant it it all。

 it's safe to concentrate in all the arguments。等个微信。

So the allable annotation is like a purity annotation。We intensely did not call it pure。

I it was called pure originally， but there there's actually。

A very legitimate use case for adding it to man。当是。And that is。诶。It's the function itself。

 that's some kind of cashching。来做的开始。응。The function itself has some kind of memorization or something。

Then the function has side effects， it changes the rain。But that side effect is notable。

 it external't you call the function the second time with the same monument。

 you'll get the same result of back。Even though if you actually analyze the function you kind of fight the effect and analysis。

 you will see that it does stop。So it's really， I mean， it's really okay to add it to functions。The啊。

That are not really。So that's why we didn't call it that， but basically， I mean。

 it's always safe to add it to your punch ball。And also， this is。So promote is always safe。

 it might generate fast food， but it will generate a drone code， but deable is not safe。 and in fact。

 we have a checking mode that。Where you run your program slowly and check whether all your etable annotations are。

there was another question。You also need to promote their message name。

You also need to promote the message name？That's a good question。嗯。看咗。诶。So if theory。

 you don't have to， because in the send by code， the message name comes somehow。

From a place where it's constant right somehow view it from out of the Vicode stream。

 so we know the Vicode is constant， we know from counter so we get the message name。

So dimension management is usually function， but then there also quite often senses are used in generic ways in some kind of。

Me program study。And there it may even be a bad idea to promote the name because。

It might really be a place where we call the sun with very different mearies， right？So I would say。

It's a little bit risky because because there might be in the interpretter。

 there might really be places that call the send function with message names that really are not that modest as to us。

That thought of would be。In effect， the promotion of the message name would be in the decoding of the bycode where it appeared as a constant。

 yes， a note here。But then I mean， I don't know I guess in total， there's a send primitive somewhere。

 right？Therein would be bad， probably more de， right？So indeed， that's why we don't do it in here。

 but we do it in the bikecode that has a come。그 other question。ok。Cool。

 so actually now now we we're getting it there。 I mean。

 now we understand how the meta tracer is inserted into the V。

 And we also know how the interpreter author can like add some extra pin。

To a language feature per language feature。Improve。The home of the generated code。

And actually that concludeludes the part often talk about。About the military approach。

So what I will like talk about the in the last quarter is basically。

Talk a bit more about two small case studies and next slide and the next slide。

Andre mostly going to song about pipeline。So my was really the reason why。

Why the whole project got started。 So maybe it wasnt coming to people that said。P is great。

 It has it has a slower rotation， and all the attempts to buy a drip has failed because it's so complex。

 So you can't really。You can't really wrap your head around all the optimization rules。

 We need to need some smarter approach。또 한다고 was basically。Original motivation for all this upper。

It's basically our quite implementation of Python。That's also， of course， why of the name。

Appear it python in python yeah。It's a very，'s very comfortable with pricing 2。7。

 that all pure pricing programs。That 1。7 should just look on my by and hopefully they will just be much faster。

It's a rather big community， so we have like 20 active developers but more and less。And they， I mean。

 it's quite a。They have diverse interests for the people that are reading into the。

 people that are doing web stuff， there are some people that like to buy tools and various people。

It's about 60000 land of orbit calledtroer， and then another roughly 1000 I called the England。

There is modules that super。う。Next slide。And。就。When。

I I up to the point where we managed to insert the Jpot first time。In his name。

 he added the two hints。That's say here's the micro especially， here's the dump。

But then from then on， Star was did it， but they solvedom't mean that every single language featured true。

Is like real。So then a continuous process was started that basically。

Goes through all the language features from its extremely common to rarera and rarera over the years。

 And sort of when somebody finds a program that's flow very fast， we look at the trait。We say， oh。

 it's not fast because no comes slow。 and then we。Like add some hints to the interpreter that encode the assumptions about Bill hookup。

How dog lookups are typically used in programs。And then global lookups get a little bit faster。

 And then we find the next feature that's all good。

 And basically it's this continuous post very easy to add a simple dig that doesn't help a lot。

 And then a you can。Improve your language in a very piecemeal fashion until you're sort of happy with the result。

With the funds below and diversity various points on specific a gliding scale。

 there are various points you really can stop and say oh。

I'm happy with the twoX performance improvement that I got over a single interpreter。

That's enough for me or you can sort of go on and on and on and have more and more of these things and have more and more obscure features that are really after a while。

嗯。So in pipelineip， we now about training。So we've been able to add a it since 2008 or 2 2009。

 I think。And since then， we've been in the process office。Rewriting， they talk a little bit。

 adding some things here there and getting better and better。

 and now we are concerned with relatively obscure features。

So all the core I mentioned took on all that。And I give some examples。

To basically give you an impression of the kind of。

I mean the kind of assumptions that you've getting called。 And as I said， we still discover。I mean。

 new， new things。That we can use these for。I mean， method we talked about doorlookups are actually。

Very similar to medical， basically the assumption about global lookups are that globals are constant。

They are， I mean， they don't have to， you can change it over， but in practice， most logos are never。

That means we would like to add hints in such a way that the trades really just。

Immediately uses the correct global value and how the guard that checks that total value had to check。

嗯。So as you do dreams， I will actually talk about more on the next slide。

 but then there is also something rather complex。That's one of the more complex of we do in that way。

 which is that we。We have some very advanced， complex internal terms of representation of lists and date and sets。

That new。On the fly at one time， depending on the way that a specific list is used。

And the observation that led to that optimization is that if you have a list that stores in。

It will typically store only inhibitors。And once you made such a list。

 it's very rare that you add one digital later。And if you look actually at the naive way that a list of integers is represented in memory is really in。

 You have you have an array of pointers that all point to small heat cells that are all integers and that store all store like one value in。

LikeAfter a point of the reference， get way of the heat。

So when you is over such a list and like do something with either indifferent。

 you need to dere all the point you need to do type checks。And it's just not very casual。

And so what we did was we added a special representation police that。

recognizecs the situation where like all the Erman political ins then switches to a more compact。

Representation form at this that really doesn't use the boxes at all to store the list content really directly into the list source the pointer stores the in values。

And has a special flag on the list that says， I'm Elizabethssa Lis。And then when you actually train。

呃。Like a loop at manipulate， especially， you get much better code because you get code that doesn't have to check whether the content of Alex the elements that you just read out this is an end。

 because you already know that all elements are produced priority。

So you get code that looks much closer to something that you would write in。

Is the order for job option。And then， of course， if somebody add something non an integer thing to that list。

 you have to。Change the internal representation is completely to deal with that with the situation that you need to store a mushroom generator。

And that's very costly then but we also figure， I mean， we also out。That is a very rare situation。

 It happens very rarely that。You make a huge list of holdings and then you add a victory little something。

Anyway， detailed are not too important， but it's just sort of to give you an idea of some of the more advanced things that we do。

And。Just get you a amendment go this slide。At the very first time， that started that。

The approach that I'm discussing。His talk is good for complex dynamic。

And the reason I want to show you this slide is because quite often。

So of when one talks about studying language version machines， we talk about say。

 cell or small home and those languages are really rather simple。So theI mean。

 some of the bikes are not in trivial， but they don't do too plus work。This is not true in Python。

 Python has had particlescodes that do a lot of work。

And like surprising much because Tyon actually looks like a relatively simple language when you're sort of just get you know it and write some。

W some scripts and looks all nice， but then when you actually start pickinging， you know the covers。

 what actually happens when fighting runs in the remember scale。And to demonstrate this principle。

 this slide shows。嗯。So a slightly simplified series of steps that is found every single attribute。

So every time you call a method Python or you read a few thousand them。Something like that。

And so the first step is you check whether there's a special method called un underscore score get attribute underscore underscore score。

呃。On that object。 And if it's there， you just call it and you done。It's not there。

 which is the normal case， you look for the attribute。N in the of the。And if it's there， you can。

If it' not it's not in the dictionary， then it poly instance field。 So that means it's somewhere。

 it has to be somewhere on them。呃 on the class of the object。

So we walk up the method resolution order of the size of the object， pattern has multiple inhers。

 So there's some kind of semi complex algorithm that puts all the transitly reachable base classes into some linear order。

following the bill one。And basically， you walk along that method resolution order and you look into every class and you see whether the method is in that bigctionary。

If you find the attribute of goods。You don't just return it instead you call a meone on that attribute。

Which again will trigger parts of all that stuff。If you look there。

 you call another a special method。Because2 minute is there you called in。Wait。

 and only then you raise an error audit with all these steps forward。So all this is one vital。

If if you write a traditional choice， it date or。北海ト。In your trace， you will only see cada。

And that is your job to sort of produce efficient machine code from that。

 following all these steps that are which is obviously completely impossible。就诶。That basically。

 I mean， the leaders again are completely irrelevant。

 but I just want to motivate a bit why I think that in my opinion。

 it's really not that tract to sort of manually write a for Python without having。

Ws much time more ways much money。Theres way too much paint on them。嗯。

So because in the me tradingcing approach。This mess is not a problem at all because the meta will simply。

 I mean， you have to implement it in an interpreter anyway。

But then the mer will simply follow the interpreter along through all those steps。

And you can add some things。 And in the end。The code that is left after constant folding and inriible removal and stuff is really just is usually quite simple。

But you didn't have to sort of strify any complaints。

At top rules for how you generate good code and that do we look up anywhere。And actually， I mean。

So the hints that you that we have to provide to make that stuff pass are again not completely nontri。

 but also not that bad because I mean， in pricing you can change。The methods of the problem one time。

So its not really the lookup function that we saw earlier would be pure because you can change one of the methodary obligation。

So you need to be a little bit more clever， but what we do is we add a version number to every class。

And every time you change。诶。A class， and you add a method to a class or you change your method or a class。

 all the version numbers of all the classes that are affected in。

In thehi they get their version commanded。 And that means in the。

In the place where you cache a method， you can simply check， is it still the same class。

 plus the class have the same version and if not an you to something the special。

 but if those two conditions are making it this please fast together。Right。ok 诶。

Anybody who want wants to ask something about that。

Couldn't you just implement like an intermediate bytecode that you could actually trace that does all of this stuff？

No absolutely could。basicallyically， you would what would you do then is you're shifting the complexity around。

 because that would mean that。In the P compiler， that takes P and generate P。

You would have to for every method。For a very attribute look。

 you would have to expand this into like。增治委佢为。So that means the vital is a lot。Compact and that。

 I mean， basically you shift the complexity out of the interpretor into the into the power by。诶日到。

It's possible that if you're a little bit smart about where you shifted。

The end result is kind of okay， but。You still need to sort carefully things what you want to3。系。

What do you want want。给我看一下。So yeah， that is basically all I wanted to say about Python and actually。

At least make it somewhat possible that that stuff work。

 I have some benchmark numbers on the next slide。As you hopefully know， all benchmark ouries。

And of course， the regimens I have here are also lies and they also always lies because the numbers are from my PhD that I added in。

Three years ago， so by now their numbers are probably different， but。Yeah， not。 I mean。

 nothing fundamentally changed。 it's probably。A few percent in various directions are general of so。

就。This slide of benchmarks。Is。A number of python programs that we ran on various p applications。

And the baseline that we normalized all the numbers to is C p language is failure。

This may be the standard。诶。Python implementation that everybody uses it basic Python and it's just its a very simple compiler interpreter it's very similar to Sa data。

 gene nothing fancy。Its not particular location。So the next mutation that we looked at was cycle。

So cyto is actually a method based dig for Python that you can use or that you could use at the time。

And an exempt what you proceed。It's written by one of the P founds。And actually。

 it turned out to be completely impossible to maintain。Because it it all the did fall。

We were doing so well。这是么啲呢。啊阔不。You can hear me， right， we can hear you。

I was running about what point was the last thing you know。

NowYou're talking about how psycho is unattainable。

So basically Cy was started around Python version 2。1， I think。

And then every newprint version added features， and at some point。

 the author of psychocho just gave up trying to add the new features to cycle because。

Sor of stuff was so tangangleled and basically at the time there was this joke that said that psycho consumes a brain per inch of progress and it's kind of short so there like two other great people that try to get into it with sort of reach levels of success but nowadays it just beent working。

Right， so the next bar， which is sort of less than half the speed of C Python is pipeline without a it。

 but as you making the R Python interpreter because they you see adding an aGC but not adding them at all。

And okay， it's a little bit annoying that it's lower than C Python。 The reason is that。

So the artyon language is sort of at a somewhat higher level of abstraction than C。

 So a number of things are a little bit more costly。

 we spend a little less time to optimize the interpret， so it's quite a bit slower。

So the next step is， we just add the hints that say， here is the right to be special。

And so tracing works， but the grid doesn't know anything about。Anything specific about al patent use？

So， and then why might I become and so。Goes back to the same level as that。你解啊。

As fast as the microtroor。年間事。诶The real term。いなく。And then the interesting thing happens when you add all the other hints that basically say。

Here is how me is used， et cetera， et cetera。 And then we get a， seven and a half times we speed up。

All version in my。Okay， so that's good。Just do nothing and your program gets more than 70 minutes faster you like that。

 but the other question that you could ask is。So we have this weird method。

 this weird indirect method of constructing a virtual machine。

 how does it stack up against like real virtual machine， whatever real is？Go next five。

So what I need is compare hyp again。So the proper traditional sead plus washing machines， hospital。

And I use the Scher benchmark sets， which is， I mean。

 the reason you use the benchmarker is that there be a number of benchmarks where the the same task is implemented in a wide variety of languages so you can sort of like。

Theres been different of different。And here I normalized to。Pyon， and we can see that。

The added is about 70% talk I'm pretty sure that knowledge is。Even much faster because Google has。

Incre the team and added lots of lots smoke。L is about2 x factor， which is pretty good。

Do I to the one person cor， one genius cor or something about？And then there hotpot。

 which is like the one of pump goilla this pump anyway。

 the huge hundreds and hundreds of person years lot machinechi and that is basically。Yeah。

 that you need to compare yourself again order。And I mean， on the one you could say okay。

 we're sort of twice lower， two times lower， but then in a， I'm actually。

 I'm actually relatively happy with these with because。

So the effort that went into the did part just took piepe。就是说。

Comparable against the huge amount of effort that has gone into。And also now that neuro wrote to。

 which Joge was annoying it took some years， but now that we wrote to。

 it can be reused completely for other。And I'm actually going to。Talk about one such other language。

 but now I'm going to give a slightly silly demo。I mean， the wrong。I mean。

 the problem with language they one is always that they're slightly boring。Because呃。Of course。

 when you write in UBM， you want to behave each exactly do the same。

 so you just you run the same program twice and on the one hand， it takes a second on the other hand。

 it takes a 10 second okay， but so what we started doing is。We started。

We started doing sort of graphical demos to make it at least somewhat exciting。

And since I'm actually using Skype on phone， I'm going to do something beings。Which is。は。

The demo takes about a minute。 So you don't have to stand this walkingpping numbers and so on。

 So what this is， basically a little program that opens the webcam and。Get frameed to frame。

Feeds each frame into a protein program that does a very simple solar edge detection but imp pure。

So if we start that， we should have started that by talking。And we start that with C。You。

 you just like it just pays。I mean it's exactly the same program that T is very bad at。

 it's not super athme heck， it's too huge loops， it just goes over the pixels and it just， I mean。

For the first brain to appear quite a lot of patient。But actually， I mean。

 what I discovered is that it's worth it to wait for a little bit。

But otherwise the python version of the name is not actually the type version of the name was not actually very impressive。

Right okay， so we have a strain of knee， you can see some edges here， but it' actually move。都懂ね。

And of course， then the。The more fun version of but then what is the Bible where you can。Yeah。

 now we see why I'm going to slide shirt。因位。InBack to。Back to corporate governor。诶。フラ。

So just to prove that。I've not been talking about the completely non existing PM for the last 110。

 Okay， very briefly， and next slide， I'd like to talk about how along。

Just sort of to demonstrate this idea of reability of origin。

So para is one of the case I did to prove that the whole out approach works for a very different kind of language than。

Then。The typical object into dynamically type language that most Bs really't care about。

 So who in the room actually knows some folk。え。Pro， was great。Pro is。 I mean， it's kind of。

Its kind obvious that probe is very different。 It's not is a logical language it has。

Toory and test backtracking so logic available it doesn't have objects。Ha pattern matching。

 So in a sense， the execution model is completely different than that。So what I tried to do was。

개나 뭐보다。Use the same approach and still get some of these performance using that J that we wrote for a completely different。

And it turned out that， yes， in a our situations， probably made me fast。and in some other。

 particularly if youll write programs that are very logically and use lots of backtracking and have completely weird unmetism that it is a little bit confused and does not produce such weight。

But anyway， I mean， part was surprisingly pun like 15000 flying the urban gold。 it supports like。

The core of an language， obviously because that but that are also quite number。It doesn't re 현실。

And the numbers are okay to the side。So， this is。Lormalized to the6 ins， So6。

B is one of these weird languages that still have a commercial im that's very good。

So that's called sixus and sixus has two modes， one is a simple micro inor that's what we all have to。

 and then sixus dollars after。So the virus is of to is like nine times faster than the hot。

SWR is the biggest in。2。7 times faster than the chop。And then if you use just the tu I is。

At 60% of the performance fixtures， but the j brings it over the implementation。

 but does not manage to be。Ting for many years。Commercial firm。Right。

So anybody in the involved playlogue？How long you to implement that。How long was it technical？

It's not really that。E to saying， because so it， I mean。

It was was my special project and I sort of kept。Continuously。

 like spend a couple of weeks here and there on it。I have系 agree say。一般？I mean。

 the part language is really rather small。And I mean。

 it's possible a fun to sort of try small product language extension。

 which is really what I wanted before originally。So， in a sense。

People learning just the core of it is probably not。That long。

 I would you can write more in a week or something。Whether the question in the back or not read？

No know听。Okay。Okay， so now we have in in。ああそう summary。Using government it impossible to。

Now that we painfully voted it， it's possible to share the a lot of the is infrastructure between completely different languages。

 as long as you're willing to。People with your language by writing an interpreter。

 an online interpreter for it。And but basically， once you wrote it and offtroer。

 it's enough to add a small number of pins to getit and then some mores to sort of continuously improve home digit to a point where you're happy with。

And by now we've really tried this approach for quite a wide to variety of advantages。

I'm relatively confident in saying that。If your language has some kind of runtime variability and can benefit from it。

 you could probably。来即暂可。And sort the muscle of architecting could be that it gives you like 80% of the great ja wood。

the effort then maybe we can pipe whether it's 80， 20 or 50，160 or or whatever。O，在这一下。 thanks吧。

No question happy。Can you say something about the memory consumption of tra Gits in general or byP in particular？

嗯。I's actually not that obvious。Because， I mean， Python。

 it is a lot like Python is a lot more memory efficient about representing all the。たイオレだけた演たが 난。

But then， of course， on the other hand， there is。There is the space that you need to install the machine code that can generate。

And in practice。We see both things， I mean， sometimes we have server applications that just have new sheets。

And then I'm really happy with my life because。I mean， the huge amount object gets smaller。

 but then on the other hand， we have people that say oh。

Something I mean twice to one because of all the because of all machine going that we don。Im。

 I don't really know。 I mean， it's not completely obvious to me that。诶。所以算唔算。

Are generally more or less。诶。Generally consume more or less than say Me basically。 I mean， I don't。

 I don't really think that there's a。At general rule， I know that。

We had to put a lot of effort into some surprising corners in the to reduce the consumption。第三方。

In the beginning cards， I mean， there are little cards。 And if you implement them。Nively， they can。

 I mean， like。They can。유주 뉴스 유즈 앉아 아。Me basically and so。I mean， as someone has said。

 there are some annoying technical difficulties and actually guards are one of them。

It's not that getting them to work is not that hard。

 but then making it practical that you have a lot of cards that could potentially pay by practice never do took a lot of engineering effort to get the involved。

So I have a couple of questions。So you've talked about generating code。Right。

But you've never mentioned anything about invalidating or flushing code。

 and so I wondered whether you had any particular framework that you used for doing that and especially do you use speculative compilation and flushing of code？

To deal with assumptions which are rarely invalidated。Right， so。

One requirement of the hints that I showed you today。来週眠ちいさきだ。And that is actually。

So I talked a little bit about class versions。And password version is a prime example for speculation because you read the version of of the class and usually you can expect that that never changes because in practice。

 it's very rare that sometimes in the middle of programming we used to have new methods。

So what we do is that we mark the version field of the。Our point object that represents classes as a。

Special speculating you。And that adds to machinery that if you read a field of out of such a like if you read such fields。

You don't actually produce anything in the trades。Instead。

 you have a special right variabilityology field。And then you record a dependency between all the traces。

And all the specs with the red fields。So when you。嗯。

When you the right barrier triggers and somebody changes that field。

 you throw away all the traces that depend on that re value。はい。

DoDo you have to do so do you when that happens， what do you do in terms of trying to。嗯。You know。

 if something is executing one of those traces， how do you get it gracefully out of the trust。

 the equivalent of deopive my in a conventional PM？Right， so quietly enough， we don't really need to。

 We don't really need to。When the optimal， we don't actually have to go but。

Machine code to throw away the machine stack right we do instead or like fiddle around and what we do instead。

So if there's a， if there's a trade on the stock it called something else， right。

 and it called something that could financially。Destroy an assumption。

Then that call is followed by a guard on United。we basically a law。

But it's a note that will be patch。Bu a jump to some compensation code。

 So basically when that call returns。And the assumption was invalidd。

 We will immediately execute the drum and go to some。

Incredibly annoying clean up code that tried to figure out what went wrong and puts everything back into order。

But there's no framework。We just relear all the helps and yes， they are going。I mean， I don't think。

I don't really see a way to get around that pain at least once my。I was hoping you find a way。

 I mean， I think the way we found it that you can use our methods if you use our。So yeah。

 I think there's a little bit of long point it。We are time doing hard work。

Was doing artwork as long as it's chaable。I mean， I don't think。

We're not trying to get rid of all the hard work， we're just trying to only have to do it work。Right。

The project。As you mentioned， it's been around a long time。And early on， it settled on。

Our python as the。Language of expression and C is an intermediate language and in the next lecture I'm going to be talking about the choice of C and C++ as an implementation language and some the ends that have stepped away from that I wonder is there anything you can reflect on on the choices of those languages for those tasks and know if you could wave a magic wand would you still use those two language？

都。I think。In as a mean the media language is a good choice。

We tried to use LDM in various points in time。 actually， the first， I mean。

 the way I got into the product was to write another static back for advertising for LM。

 but it turned out that。That actually never gave us much， right？So， our never not really。I mean。

 it's not easier to generate than see， they don't have teachers that we need that you don't have。

Alonium does not really produce by the cold diamond。

So there is not really an obvious candidate of what is immediately。

I think if we know what we know now， we might not have used our plan。You are in some sense。

 a little bit of a weird language， it has some good properties。

One of the best properties of our it's very nicely testable， right？I mean。

 when we test our interpreters， we never translate。

 we just run the interpreters in our present program and write unit intent against that that is one of the great properties of our。

本能。The hydrogen can be obscure and and it didn't。 It wasn't really that consciously designed was it sort of grew over the years and it has some。

No someized corners and some of the。How we put on and something like that。そう。So yeah。

 I think it was sense。Some more conscious language design。嗯。Would have been good， but it's now。

 I mean。I mean， at the moment， it's not really that anything people us to migrate somewhere。I mean。

 it is， but it would be a huge amount birthday。诶。So just out of curious if you reach other。

Lanage is will you discuss I'm going to be talking about。The implementations of things like squeak。

So languages the other implementations that go via state， Java VMs written in Java。

 that kind of thing。嗯。Yeah， actually， I think。I think so one very important feature of our placement。

 and I think it has that in common with the dramama Javava in said。

Our Python is a much more and reliable language。So one方我 is that。

You look at it not memory saved and a study analysis of C cannot really give you a lot of。

So you probably using C as the language that betrays。

Would probably be very bad because a lot of would not be valid。有说。

You need a kind of media language that gives you a lot more guarantee in order to actually write optimize。

And I think that that's a huge thing。And I know that we absolutely need。

For the implementation language， we need to be at a certain level of abstraction to make sure that there are some guarantees that the optimizer can rely on。

ま。AnyMore questions in the room might want one last crazy。😔，Thing which camebell。

 as you were talking earlier， the question I deferred from the middle， which is in。

In many use a program。There are structures that look like switches embedded in Wild loops。

Doing things like decoding images and audio。So what about Yeah， so matter， matter trust。

So I have a weird repplanatory in a corner somewhere。That tried to get that to work。Indeed。

 by trying to sort of unroll even more and trying to pattern match when we were back in a similar situation。

 finally enough， it was actually。A language that's very close to your what income feeling， right。点咩。

Basically also small and small and object。 And yeah， it's surprising to anyway。

It was very hard to get to work， I mean， it works and the thing that children do is long time。

Like I mean， because you need to double trace in the driver。You get huge amount， you get huge。

 completely gigantic trapers， and then you spend ages sort of throwing away 99% time。

P all the observation they did to get something tiny back。If I mean， you wait for a long time。

 it's not very stable and I'm not。I don't think Ive followed。The right tool to to dream that。

So I think it would be very cool。But Im love there。All right。O。

You mentioned in the middle that you're implementing a rack and scheme。Our final implementation。

 did you help to do anything special to implement continuations efficiently？Yes， yes， we do。

So they're true approaching。That the VM is typically changed if you want to implement the team。

 one of them is you can't be stuck around， right？So you write some business scary platform specific assembly that when you do a policy。

 you really。嗯嗯。Do a man copy of exactly the the right amount of see stack copy it over to the and then make sure when you copy by pleasure。

 you copy it back to position because moving it up and long probably not going to work。

That also means that policy is not that part。So that's one approach。

 and we've actually considered it because we have an our Python library to do that kind of thing。

But then what we actually went with， if you do that。

 you can write your interpreter in a naive recursive file right。

 so you can recursion at a language level to recursion at the interpreter level。

But what we did instead was we completely reified all the scheme that that right so the interpreter is really just a loop it never recur。

It builds heat heat brains， and then whole is easy。 You just， your brains are on the he anyway， just。

Switch a pointer around you keep money。 So that is very inefficient， usually。

But then it turns out that the G is actually very good at just removing all the allocation of all spectrum。

Because they're all short on。It can predict where they go and where they come from。

 so it removes their allocation， it removes all the regulation of them and it gives you exactly the kind of machine that you would hope to get。

もうしている。So， this works。For simple things wrote lady well。

 but then sometimes you write the weird skin things that have context。

Control flow and your continuation escapes， sorry your heat brain escapes。

 and then have multiple allegations Egypt for。到了。I'm not sure we have to perfect that today。

But I mean， one thing that is really satisfying to me is that if you write a really a naturalural。

 real loop， that every generation does a call T see。But it will just remove all of that over it。

 runs exactly the same speed as where you just。Use to take hold。But it's fun， I mean。

 basically I went to Indian University in Bloomington for a week and we just brought it。はい。Okay。

more questions， I think we should thank Col once again。嗯好了。你けよ。一分。Hang it up and。

I shall send you a in the video when it's upload see。对系。

