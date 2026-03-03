# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p50 24_04_01_C++发明者Bjarne-Stroustrup.zh_en -BV1Kt421V7EE_p50-

是。

![](img/bce7eab86ed919b8c3edd8ec4c79a268_1.png)

🎼，🎼你是。🎼Okay。🎼好。🎼宝宝。I was trying to characterize what is C plus plus particular useful for。

 What did I actually build it for。And what is its strength today after。Almost 30 years of evolution。

And so and also， where's the limits to where it is。

 So the way I see it is there's a coreor mean for C plus plus and。

That's what you would call traditional。Systems programming， but that's not the right term。

 because it's just a style of language and a style of programming。 So I go a little bit further。

 I said， what is it that that that。Requires the kind of services that C plus plus has what。

Is the sum of all these applications I've been dealing with。

 where did would work and where was it essential， And I came up with the phrase infrastructure。

 And I roughly define it as if it breaks。Somebody gets hurt or somebody gets ruined。😔。

These are the kind of foundational things in our systems that must work。火啊。

The system for the society to work。The， the the the question I'm trying to phrase is what matters in those areas。

And I've come up with some notions of compact data structures。

 very strongly typed interfaces for maintainability and for minimizing errors。诶。

A heavier emphasis on algorithms or。Random code because we need reliability。

 we need the stuff to be comprehensible， alyzable， we want to make sure that it's actually correct。

And so the paper I was writing come from， from that kind of of thinking。

 what is the right style and what are the。Supports for that style we need for infrastructure software。

 for software that must be dependable， and we can get real examples。

Sort of the keys of some of the modern Al brain systems， the basics of our phone system。

 the brakes in my car。😔，How do we make that dependable。

 how do we make sure that the space probes don't get the logical equivalent of your blue screen of death halfway to Mars where we can't send that。

A repairman， how do we make sure that they actually go into the right orbits？JPL lost。

A probe of Mars， because two groups。Had communicated nicely， they thought what， in fact。

 one of them spoke imperial measuress and the other one spoke the SI system， the MkS system。

 and the result was a misnavigation that sent。More on。

Hundred million dollars worth of equipment into the wrong orbit。Not not a good idea。 It was。

The work of 200 good engineers， lifetimes work。Down the drain。

And that could have been avoided by ever so slight improvement in the interfaces between the parts of that program。

 so things like that I'm interested in， so there's the core area where I think the facilities for C++。

 the kind of they're not perfect， the kind of things I would like。

 the kind of things I work on are essential。And then there's a huge gray area where。You have choices。

 They can help， in my opinion， but they're not essential。

 Then you have areas where it probably is unsuitable to apply that kind of。Of stringency technique。

 I mean I want to essentially get 100% reliability if I'm putting up a small application for my own use or if somebody is trying to push out a little acute web app。

 they don't need that kind of reliability and maybe what I'm talking about in terms of programming is not for them。

But I think the really important thing here is to realize that。There are different techniques。

 different languages that apply to different areas， and we have to recognize this。 We can't。

Have a single language for everybody， a single technique of using that language for everybody。

We can't have a single tool chain or a single kind of system。

 and from there we can go a little bit further we probably don't need the same kind of training for education。

For for everybody。Engineer， software developer or whatever。 that is building infrastructure， say we。

Mechanism that automatically updates the software on， on a cell phone。

Has to have a different education， different knowledge。

 different training from the one that makes a little game。Because the one can actually destroy。

A whole day or。Or a whole week。For millions of people by a little slip。Maybe even somebody gets hurt。

 if the 911 cords don't get through， bad things hadn't。

And it's not just the software that runs on it。 It's the update software。

 It's anything in the chain of， of。Safety， critical issues that has to be dealt with， but。

Somebody doing that has to think differently from somebody who writes a little application。

 maybe to make a couple of bookss quickly， there's nothing wrong with that。

 but they have to think different as a matter of fact。

 if you apply this very strange engineering oriented thinking to little commercial apps。

You'll probably be a year late to market， and it'll be irrelevant。 On the other hand。

 if you took the attitude of first to market is the only thing that happens and apply them to the steering wheel of my car。

 No， that's not a good idea。 These people have to think differently。

 And the way you get people to think differently is to。In to give them different educations。 We。

 we don't have an Nces standard programmer， and we shouldn't have。If it was， we should have several。

And I think the field has to， in some sense， clean is of its act before somebody else comes in and try and cleans it up for us this notion that you can sort of make your own constants and have the seconds after the constants is that feature that you added at some intermediate stage or is that simple sort of operator overloading？

We were observing that。 We were getting a hold。Sux of little suffixes out of the various fundamental types。

 Su。The use of fix for unsign and ill is for。😔，Long， I think。

 and I can't remember the morning anymore and you thought， you know， you can do anything in C++。

 but you can't make your own literals。And then I'd observed separately that there was techniques that。

Were effective， except that people would not used them because the notation was too ugly。

The UniX example is one UniX example is one of those you've been able to do everything in the UniX example I showed。

 not quite as elegant， but you can do everything showed for the last 10 years libraries have been available and there was a nice one from Fermi labs back to nice places and nice people again。

 but it wasn't used as much as it should because the users didn't believe in the notation they didn't like it。

And so we are looking at， how can you basically clean up peoples source code。

How can we make code look the way it would look in an ideal language。 How can we make code look。

Much as it does in the textbook。 So the units sound is simply a way of getting your code to look。

The way equations look in your physics textbook。We know how to avoid that Mars climate orbit a problem。

 Everybody had been taughtuted in physics in high school。 First， make sure your units match。

 then do the detail calculation。So why didn't people do it， It was too cumbersome。

 and it was too ugly when they did it。Or too costly if they used runtime techniques。So， I。

Together with friends， we thought this problem was worth addressing。

 tried to figure out what solutions we had， went through several evolutions。

 I think the last finishing touches was done by David。And it's now standard。

 this is one of the features that is not shipping highly today。

Wait a year and that example probably around your computer too is are there other kind of examples where you've let people from within a class create their own literals beyond sort of suffixes？

When I started out with C plus+， I provided constructors。

 which allows you to construct objects of a certain type from arguments。And。

 and that has been very effective。 And people have used constructors as。嗯。As if they were， girls。

But they weren't。 There was a run time cost。So the first thing we did with C plus plus X。

 C plus plus 11 was we introduced。Constant expressions as a more fundamentaled unit。

This was work between me and my colleague， Gaer Du raise。

And we have constant expert functions that can be evaluated at compiler time and we have constant expert types so that you can use typebri programming at compile time。

 This is very important in sort of the high performance computing and in the embedded systems world that was what we did to address that Con expression evaluation is much more general。

 much easier to use and yes， more pretty in C+ 11 that in earlier versions。

 So that just strengthens what the direction we've gone before。So you could write complex one comma。

Ch to make a complex number in。C++ in 1984。Today you can write the same thing and have the complex number created at。

Compゃ。And therefore say put him wrong， I don't know why you would want a complex number on wrong。

 but you might want a point， which is the same thing， point of one number two。Now。

 you still have the write point or complex。And the other thread of thinking is C++ which was to generalize and make safer the initialization。

And so it happens that if you know the type you need。

 like you have a function returning a complex number。You can simply write open curly on Comt2。

 and he says， oh，1 Comt2 is supposed to make you a complex number and it will make a complex number and return it。

And if you happens to be a compile time you'll do that at compile time， so things work together。

 you get better notation， you get better performance。

 and anything you can do at Comp time works even better in a concurrent system because you can't get a race condition on a constant if it's been calculated before the program starts。

 you can't get the threading problems So open curly means。

Find a constructor for the thing that I'm about to put this in it looks at where the destination is and it says is there a two parameter constructor or a three parameter constructor or whatever or if it's just astruct it'll take the first element and put in the first element and it does it for astruct as well Oh see I should I haven't played in C++ in a while that's a great idea this and。

Unniform initialization。It'll initialise if it can。And if there's any ambiguity， of course。

 finds the ambiguity。If you're in a context where the target like you're calling a function and the target could be a point or a complex number。

It's a tough look。Go and tell me or tell me， so the error shaking has actually been improved。

C plus plus 11 is slightly better at finding bugs than C plus plus。98 was， I mean。

 I come from the School of Philosophy that says that the compiler is your best friend when you generate。

Co when you build programs。And。To make it your best friend。

 you actually have to have more types if everything is an integer well。

What can the type system help you there No it can't if everything is a floating point number I can't tell you whether it's imperial or II units and youll get bugs so you need type rich interfaces and for that you need to be able to build。

Cheap types， basically and flexible types and convenience that's easy to use simple。

And so we work from complex of one commerce area one comma 2 or something like that。

 So cur is1 comm2， and the type is optional， it' only needed when it's needed。 And then finally。

 we can now write if we wanted to。One plus 2 I。Define I S C。

Jage for the imaginary parts and you get complex arithmetic without ever saying complex。🎼あ。

