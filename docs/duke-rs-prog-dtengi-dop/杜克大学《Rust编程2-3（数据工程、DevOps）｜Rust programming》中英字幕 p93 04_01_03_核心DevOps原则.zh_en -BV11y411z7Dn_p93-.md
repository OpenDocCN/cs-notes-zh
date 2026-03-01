# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p93 04_01_03_核心DevOps原则.zh_en -BV11y411z7Dn_p93-

![](img/b5a8fcb987d7341cf9336353421cebd2_0.png)

So what are some of the core DevOs principles and we have here a diagram and I put here a lot of things you might read that building testing。

 discovering continuous feedback collaboration communication all of these things that were seen right here are very important and core principles of DevOs but in essence。

 none of those things can happen say for example if you're placed alone to try to figure out things by yourself like I've been in several situations where the company was small we had some developers and then someone had to put things into motion so how do you do that well you start here at the very bottom with automation being the foundational aspect of everything that you're going to do and what is automation what we're going to have I'm going to go into detail these later but。

Anything that is done manually， you have to piece it apart into smaller pieces and those pieces will actually start being the foundation of automation。

 so say for example， you are doing a manual verification of a piece of code。

 well you build some script that automates that verification and then that's automation。



![](img/b5a8fcb987d7341cf9336353421cebd2_2.png)

Now automation by itself is good， you're building some scripts， you're building some files。

 some code that is doing something that is automating something that you were doing previously something manually。

 and that is as we're seeing here that is going to feed into the possibility of enabling something like a CICD system。

 what is a CICD system， well it is something that allows us to do something in a continuous way。

And that is andciI stands for continuous integration and C for continuous delivery so it's a system one of the most popular ones is Jenkins Github has Github actions which will also be covering and these automation these scripts that you might be building right here at the bottom those can actually end up being part of your automation when you're doing CicCD when you're using one of these platforms and why would that be something desirable because then who is going to who is going to run that script well that script is going to run automatically right it's not only automating the task but it is also about the triggers and how is's going to get that in what moment is going to then get data executed so a CICD。

A platformlatform might allow you to define a trigger like whenever someone's pushing code。

 whenever someone's making a change。Whenever we want to push this to production like certain things need to happen like the script that we have that we've written before and we've automated some steps so that that is good but then again if we scroll here a little bit we don't have these things don't necessarily can happen without all of these foundational pieces。

 these core pillars， these core principles of DevOs which starts by by building automation now automation is great and testing is great but rather automation is great but it requires some testing some validation so that's what we have right here and testing is important because if automation is going well well are we verifying things are working well。

 how are we verifying those are working well so we have to have tests in place and numerous different types of tests even for monitoring as well。



![](img/b5a8fcb987d7341cf9336353421cebd2_4.png)

![](img/b5a8fcb987d7341cf9336353421cebd2_5.png)

So you have to pick and choose and then the other portion of it is the measuring and I understand that that this graphic is getting pretty well right now。

 but measuring is what gets us into a position of like comparing we're able to compare things going better or are things going worse you can't have like a baseline if you're not measuring like are we faster are we slower is this code actually doing better Are we solving the problem that we set out to do which was improve speed or improve our capacity or improve our load Those are the things that measuring will give you so。

This is a big high overview of what is DevOs， what are some of the principles that we're going to cover and why automation sits at the foundation as the foundation of everything that we're going to do in DevOps automation is critical and everything and anything that can be automatedm should be things that our manual should be stopped or thought over to try to build automation on those steps as much as possible。

 so this should give you like a good idea of how to get into how to understand some of the DevOps principles that we will be covering in more detail next。



![](img/b5a8fcb987d7341cf9336353421cebd2_7.png)