# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P91：-091-Formal Verification Chap6 Video 21.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

What if your job was to build the next big software system that ran one of these pieces of the real world？

Say an airplane， the autonomous flight controller for that airplane。

Or an autonomous car that drove itself。Or another kind of vehicle entirely， the space shuttle。

 which has to go up into space and come back with humans aboard。Or the power grid or a DNA sequencer。

 or many other kinds of machines。What do all of these have in common？Safety is really critical。

Humans could be injured or killed by any of these devices。

So we need the software that runs them to be much more reliable than your average phone app。

 say for TikTok。😡，That's what the next segment of this course is about。

What are the techniques you would need to use to build software that is that reliable？Much earlier。

 we saw this same slide when we talked about testing， and it's time to come back to it。

There are many approaches to the process of validation that is ensuring that software does what it's supposed to do。

😡，And we've talked before about social approaches all the way up to mathematical approaches。

On the mathematical side of that spectrum， you now have a lot of experience with OKmel's type system。

Which is more strict than other languages。 And perhaps you've come to appreciate that。

 Perhaps you've even had the feeling yourself now of coming to the point in coding and being able to realize。

 wow， once my code compiles， it does what I want it to do。

Which is not necessarily the case in other languages。

 because their type systems simply aren't expressive enough。On the other hand。

 it does make it more annoying sometimes to get the code to compile， of course。Well。

 let's take it one step beyond that beyond type systems to what's called formal verification。

The notion of formal here is in the sense of mathematics of being formal about what you are trying to prove。

So you should be familiar with this kind of idea from CS 2800。



![](img/0ccd8ae938abc5fedec16f4d92e4bea9_1.png)

Formal verification is something that has a history spanning back to about the 60s or 70s。Back then。

 as it turns out， our very own professor Gs at Cornell was one of the ones leading the charge in this area。

And back then， say， about in the 70s。Formal verification that is proving the correctness of program。

Is something that scaled to maybe tens of lines of code。

 It was something that took a lot of human work to do， a lot of proof on paper。

 and it wasn't always necessarily a pleasant thing to do。It kind of had， oh， for a while。

 maybe a bit of a reputation of something that wasn't going to go anywhere。

And you may still meet people who think that from time to time。By the way。

 the same thing happened with machine learning once upon a time and look where we've gotten now with machine learning。

Well， also look where we've gotten now with formal verification。😡。

Now research projects in at scale to real software。😡，For example。

 there's compert which is a verified C compiler it's been proven correct and studies were done to show that it had many。

 many fewer bugs than other C compilers Now you might be thinking how could it have bugs if we proved it correct It's because not the entire part of the compiler was proved correct there were some pieces that there were part of the parser that weren't originally proved correct actually they've gone ahead now and done those as well。

😡。

![](img/0ccd8ae938abc5fedec16f4d92e4bea9_3.png)

![](img/0ccd8ae938abc5fedec16f4d92e4bea9_4.png)

Other examples include SEL4， which is a verified microconal OS。

 why not which provided a library on top of which was built a verified database management system that was done in part by our very own professor Greg Morrisent。

 who actually is now the Dean and Vi Provost of Cornell Tech。

More mathematical results include a computer checked proof of the four color theorem。

 you might remember that from CS 2110 it says that you need at most four colors to color a planar map。

There's other more exciting work in progress like Project Everest。

 just done in part by Microsoft Research， that's a verified HTTPS stack。

And there's all kinds of other interesting projects going on too。So in about 40 years。

 we got from the point of being able to do only somewhat toy examples to real software。

And that's as research efforts， some of these took person years worth of effort。

 SEL4 was especially notable for that。But in another 40 years， where might we be？Well。

 by then I'll be at the end of my career， but you'll be in the prime of yours。

 and so I'm excited about what you will see 40 years from now in terms of what it's able to do in improving the correctness of software。

😡。

![](img/0ccd8ae938abc5fedec16f4d92e4bea9_6.png)

What are we going to do here in 3110？Well， it's not going to be an entire verified microconal OS。

 sorry。We are going to do the following。We're going to write some small， purely functional programs。

And by purely functional， what I mean， of course， is that there are no side effects。

 there's no mutability， there's no IO， and they always terminate。

Now there are ways to get around all of those restrictions。

 but they become technically more difficult as you build them up。

 so we're going to start with something easy。Small and pure。

And we're going to do proofs about programs that involve integers， lists， options， trees。

 and a couple other data structures as well。We will be proving correctness theorems about these programs。

So this goes back to what you have learned or what you are learning in CS 2800 you will need to know some logic for this。

 you will definitely get some more practice with induction as we do this。😡。

Now our goal in all of this is not to be 100% completely formal。We're going to be rigorous。

 we're going to be careful about the claims that we make and the proof techniques that we use and the justifications that we give for them。

But we're not going to attempt to dot every eye and cross every T。That can be done。

 it simply takes much， much more work。And if you're ever interested in that。

 I do have a class CS4160， formal verification， where we dive much more into all of this。



![](img/0ccd8ae938abc5fedec16f4d92e4bea9_8.png)

![](img/0ccd8ae938abc5fedec16f4d92e4bea9_9.png)