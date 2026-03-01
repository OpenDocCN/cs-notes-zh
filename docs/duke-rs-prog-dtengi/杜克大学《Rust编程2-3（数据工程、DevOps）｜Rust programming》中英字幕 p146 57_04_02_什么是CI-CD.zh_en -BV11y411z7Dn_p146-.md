# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p146 57_04_02_什么是CI-CD.zh_en -BV11y411z7Dn_p146-

![](img/819cb26c3fb8e28c3c28ec0eaa30188c_0.png)

Let's do a quick overview of what is CIC， but before we get into the details， let's start right here。

 number one with your source code， so in your source code in this case we're talking about rusttor here。

And you have many steps to do anything really right so what happens or what ends up happening really is that you will probably go through a manual set of steps like cargo run or cargo build you check everything that is working if it's not working you go back and you make some fixes to your code which is fine but all these things are manual and that is the key phrase here。

 it's manual， anything and everything that you see that is a manual step well that is an opportunity for building some automation and whenever we're taking manual steps and making them automated。

We are building the foundation for what exactly is a CICD system。

In this very simple use case we're taking our little arrow here is doing so many steps and producing a binary and this binary here will effectively run this can be applied to anything really we could be a web application。

 it could be some other language even like these concepts are not unique need to rust。

But they're foundational for DevOs for sure。Now， this development cycle that happens here in step number one。

Might be fine for quick development and and you're going through several cycles there。

 but things start getting tricky and very dangerous with step number two here step number two is kind of。

Dangerous and problematic because then you start relying into all of these steps to actually try to release your application to a production environment。

 this could be an HtTP service it could be a command line tool even for a command line tool you have to tag you have to see what version I it like did the docs that was the documentation building did I include any 404 links in my documentation is my HtTP application passing all the test am I releasing into some clown provider am I authentic it incorrectly and you have so many different steps that in this case well I put 75 to be outrageous here。



![](img/819cb26c3fb8e28c3c28ec0eaa30188c_2.png)

And then the possibility of messing up one of those steps and missinging out or get them in the wrong order。

 then you get into a problem with a production environment where you have to roll back and you have to do more manual work。



![](img/819cb26c3fb8e28c3c28ec0eaa30188c_4.png)

Now how does CICD help us out， so let's take a look here at our rust code。



![](img/819cb26c3fb8e28c3c28ec0eaa30188c_6.png)

And what we end up having， and this is our build， this is our build system right here。

 a build system or a C ICD system， a continuous integration。

 continuous delivery will allow us to provide feedback。 So we have。

Things going in and definitely things going back。 So you form a feedback loop。

 I'm going to build my rust code I'm going to create a binary。 Did the binary work Yes。

 great like everything's good Oh didn did it not build correctly Well。

 no let's just provide and do some some fixes there and try to see what we can do So there's all kinds of different things that you can do there to try to improve that development cycle and all of these here is happening in an automated way So none of these things are happening manually like the build system is taking care of all that。

To with angle of actually going all the way here to produce a binary。Now in the case of frost。

 that's a binary in some other languages， it's not a binary， if it's an HTP service。

 you're deploying somewhere and doing several different things and but beyond that you can have many different steps。

And all of those steps can be handled in this case it could be number one number two，3。

4 or5 it could be 100 steps it doesn't matter what matters is that all of this is happening with automation and automation is by it's the core concept of DevOs where we're getting all of these things to happen as automated as possible so that we can continue concentrate in in what the most important thing to do the development the rest it is important but it can be automated but we can auto is doing our Ru code right here。



![](img/819cb26c3fb8e28c3c28ec0eaa30188c_8.png)

So what are all of these things the angle goal of this Well releasing eventually going to production right once you get to production in an automated way。

 you're gonna do it faster it's going to be less error prone you're gonna be able to introduce more steps never forget the steps never get the matter of order and be able to also if necessary well roll back and you can say well I want to roll back because my previous version like let's say version1 it's not very good and this says well let let me get the previous version which was version0 so you deploy version zero right here and always good with pro again until you fix those errors back where the Ra code is so it is a CICD platform will allow you to do all of these things it is the foundation for building automation it will help you do all of that automation when you're creating all of these。



![](img/819cb26c3fb8e28c3c28ec0eaa30188c_10.png)

Automation steps when you try to build and release。



![](img/819cb26c3fb8e28c3c28ec0eaa30188c_12.png)