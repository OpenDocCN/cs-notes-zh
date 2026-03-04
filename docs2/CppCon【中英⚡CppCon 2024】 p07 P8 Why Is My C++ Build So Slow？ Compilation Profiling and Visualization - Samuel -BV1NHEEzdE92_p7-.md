# CppCon【中英⚡CppCon 2024】 p07 P8 Why Is My C++ Build So Slow？ Compilation Profiling and Visualization - Samuel -BV1NHEEzdE92_p7-

🎼Attending any conference， it's incredibly important to be there that's kind of the only way to really dedicate your time。



![](img/a5447ea329470190008cd22420f64354_1.png)

To be there and kind of be immersed in the whole thing and not distracted by other stuff going on。

 even if you do get distracted with interesting conversations in the hallway。



![](img/a5447ea329470190008cd22420f64354_3.png)

![](img/a5447ea329470190008cd22420f64354_4.png)

My name is Sam Pririvit， just want to say this is my third time at CPPCon。

 this is my first time presenting and it's just an honor to be up here on the stage with you all today。

 Thank you for coming after lunch。

![](img/a5447ea329470190008cd22420f64354_6.png)

So the title of today's talk， Oh， okay， yep。Thank you。😊，All right， let's get serious， huh？

The title of today's talk，"Why is my build so slow， compilation， profiling and visualization？

That has been the question on my mind for the last year or so。Quick disclaimer。

 The views and opinions I'm expressing today are solely my own， not those of my employer。

 Johnson and Johnson。WhatWhat are we going to be going over today。

 We're going to have a quick introduction。 I'm going to talk about a few assumptions。

We're going to get into how you can actually visualize compilation and the tools with that。

We're going to talk about individual problems with single files that can slow down your compilation。

 project level problems that can slow on compilation。

 some higher order solutions that can hopefully mitigate some of these。

Have a little section for takeaways， and then we'll have time for questions at the end。

 I've got about 55 minutes of content。 So if you could just hold your questions till the end。

 that'd be great。O。So who am I？My name is Sam Privit。

 I'm a robotic software engineer at Johnson Johnson。

 and I kind of got curious about compilers not too long ago， which was the inspiration for this talk。

😊，So what is this talk actually？Like I said， we're going to be talking about visualizing compil with Ninjain and Kang。

We are not going to be talking about how to speed up compilers that is outside the scope of this talk。

But we are going to be talking about how we can write code that compiles faster。

So a few assumptions I've got here。In general。The lines of code has a somewhat linear relationship to your build time。

This is because your compiler needs to actually process and parse the source code and needs to tokenize it and build the abstract syntax tree。

And so the more lines of code you have， the longer your builds。This is another big assumption here。

In general， for as long as your software is useful。

 my claim is that there will be pressure to increase the number of lines of code in your project。

This can be in the form of bug fixes， new features， what have you。

 but over time your lines of code will generally be growing。And therefore， transitly。

 your build times will also be growing。Now， if you actually go out and plot your build times over time。

 like end of the day， what's my build time over a month。

 you'll probably actually look something more like this。 It's not a straight， linear line。

There's periods of increase， there's periods of decrease。 Maybe we started refactoring。

 Maybe we found some dead code， and we deleted things。But in general。

 we're actually going to be increasing the trend line， again。

 as long as it is useful or used by others， there will be pressure to increase。

And this is kind of a boiling fraudrog problem。😊，The boiling frog。

 if you're not familiar is this idea that a frog in a pot of water and somebody is slowly increasing the temperature and the frog has all the capacity to leave the pot at any time。

 but it never does， and it ends up perishing because the water is too hot。This is pretty morbid。

That's not actually true either the frog will leave。

 but it's a good way to describe the problem we're talking about here where you may not actually notice the problem until it becomes extremely painful。

So let's talk about developer productivity。You know， when you have long build times。

It's kind of great， right， You get to。Go to the bathroom a lot， you get to get coffee。

 you get to talk to people water， walk around， you know， and I'm compiling。 there's nothing I can do。

But over time， you may actually notice that you're not really as productive as you may think you are。

And。I kind of attribute this to not being able to enter the flow state。 And now。

 the flow state is a term from sports psychology， where athletes are。

So honed in on their craft that they aren't really cognitively thinking much。

 It's just kind of going through the motions。 and their things are just happening and they're not really thinking about why they're happening。

And when you're writing code， I believe you can get into a similar kind of flow state where solutions just kind of come to you as you're working on things。

And long builds kind of get in the way of this， it kind of breaks this feedback loop we have of writing code and testing code quickly。

So。How do we actually visualize compilation？Well， first to ground everybody。If you are using CMake。

 Ninja， and Kang。Your build will look something like this。 I have three source files here。

I call CMake， it generates ninja build files。 I invoke Ninja somehow。

 either directly or through CMake。Ninja then goes out and calls Klang three times for my three different source files and then calls the linker to link all my output objects into my final binary。

And when Ninja does this and invokes those commands， it saves this really cool dot ninja log file。

This tracks the start and stop time of the various build commands in milliseconds。

 stores the name of the output file。And then the hash of the command used。

 So a hash of the compiler command， the linker command or some other custom binary can run here as well。

And this is a lot of information。 This is by default on， if you build with Ninja。

 this is in your build folder somewhere。 This is part of the mechanism Ninja uses to tell if your build is dirty。

So you have this。What can we do with it？Well。I'm going to use Perhetto for this talk。

 Perfetto is a open source tool from Google， and it is an interactive trace viewer。It's web hosted。

 you can go to ui。profeto。ovv， check it out if you're not comfortable doing that。

 you can always build and run the server locally as well。It supports the Chrome event tracing format。

 JSR。Among other things。And it's got a plethora features。

There are many other interactive trace viewers you could use。

To visualize a lot of the things we're going to be talking about today。

 such as speedcope or even Chrome tracing。But I chose Profetto for some of the additional features。

 and we'll get into that later。So what does it look like。

 I can take my dot nja log file and just UI Profeto dump it in， and I get this nice time trace。

So to ground you a little bit here。Along the top， we've got kind of the total time of the build。

 the timeline。So from left to right， that is the order of the build。

 we've got four distinct zones martier。And these zones are the actual。Time of。

ItIt is the total time of how long it took to create that object。 So it's hard to see。

 Sorry about that。 But the highlighted one here is my main CPP。 You can see it's distinct。

 The next one is my other source， The other。 And then finally， at the end。

 the orange one is a the linker。And this is cool。 So we can visually see and get a a gut check understanding of what's going on in my build。

 It's single core。😊，Three similarly sized files。 If you ran this on your build。

 you'd probably find and see that， oh， one of these object files is pretty big。That's useful。

But you might not actually know why that object file is so large。

 just identifying it isn't always enough。Well， thankfully。Plang， as of， I believe， 9。

0 ships with this F time trace flag。And the F time trace flag generates an accompanying JSson file based on the output file name。

 So for every dot O file， you'll have some dot JsonN file。

And this dot JSON file is in that Chrome event tracing format I mentioned earlier。

And it contains detailed information on where the compiler actually spent time。So。Real quick。

 before we actually show this， just want to ground everybody on Kang's kind of architecture。

When you invoke clang through Ninja， or just in general， you take your input source file。

 it gets fed to the front end， creates the abstract syntax tree。

 which is essentially LLVMIR or intermediate representation， which is then fed into the back end。

And the back end is what is ultimately responsible for taking this IR and lowering it to machine code and generating your dot file。

So here it is， I've opened up my main CPP JSON， you can see there's a lot more information in here。😊。

So quick round you again， the individual zones themselves are not the important part right here just want to get you the general view of it again we have the timeline on the top but now importantly this is a flame graph。

 so the purple bar or the purple trace on top that is the total time of executing the compiler。

In blue， we have the total time spent in the front end。 So how。



![](img/a5447ea329470190008cd22420f64354_8.png)