# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p94 05_01_04_什么是自动化.zh_en -BV11y411z7Dn_p94-

![](img/d63a28ab82291e07bb58e8936b851913_0.png)

So let's talk about automation and I have a couple of examples I want to go through and one of them is this project that I have here called worryri it's for like several years ago。

 I was working in a company that required these security tokens that were timebased and or event-based and I had to generate them through a complex system so I complained to my manager and I told him like listen。

 this is very cumbersome every time I need to log in， I need to use a different utility。

 a different manager to generate those keys and this is absurd I have to run these and go through I remember it was my phone at the time and then a special website and I had to type in these keys。

 these tokens and he said， well why don't you do something about it？

And of course I didn't realize that yes 100% I could actually go ahead and write one so let's take a look here what these actually the so simple CLI interface so one of the components of automation is building building something so I'm building a simple CLI interface and I'm generating the keys to set up custom tokens for OTP engines which are the receiving end of these tokens L OTP being one of them so the type of tokens could be TOTP which is timebased or event base which is HOTP so I set up to build these commandmelan tool and then would you can see here these are my examples and I would generate a pin a special secret you would copy it straight to my keyword my clip or rather and then the only thing I would need to do is go from either the terminal to actually from the terminal to the website or whatever service。

Require that to log in。And sometimes I would only need the pins and those are part of the security system so as you can see。

 I mean this has been a few years ago， but then I set up to actually go in and build build the interface to do that and generate that and you can see here this is made with open SSL and that's generating that here。

 some other tools but in essence what is doing what is's doing behind the scenes it's automating automating a process that was painful that was time consuming that for me was borderline absurd and I decided to with the help of the nudge from my manager to actually go ahead and do something about it and was that something about it well instead of doing this manual process I set up to automate abstract away some manual steps and do something that would help me do things basically go faster。

Because things are automatically copied to my clipboard and I can move faster between when I'm trying to authenticate so that's one way of automating now let me show you a different way of automation So this is actually a deployment tool。

 a deployment script that was used a while ago to deploy this massive file system open source distributed file system project called SeF and the tool is called Se deploy it is something that years ago I worked on while I was working at Red hatt and it was a highly complex piece of software so what is it that we're doing here and why is how is this related to automation Well。

 the thing is that this is an installer it deploy SeF to infrastructure because it's a distributed file system。

This goes to many， many different， many different servers， so it's quite complex。

 so imagine you having to go through many different servers and install a piece of software。

 not only install the software but also configure it in a specific way so I want to show you here a couple of things that are interesting so I'm going to close the files and I want to see the files it has a host directory。

 The specifics are not that important， but I want to show you what are the steps so I'm gonna click on Devviian。

And let's take a look at the installed P module， this is a Python project。

 and let's take a look at some of the things that this is doing。

You can see here that is setting some variables are installing stable or testing what are keys that are going to be used okay perfect so that that seems reasonable then it starts defining what are some of the packages that it will need to install in this case if it's a div system Ca certificates or app transports Https now right here and then we have several pieces of information that we will need to keep track。

 we need to understand if it's stable or testing and set the key accordingly depending on when these are being said and we need to install certain extra packages now when we're getting into the specifics installing and downloading the SSL certificate from download that Se。

com we need to do all of these things setting up the protocol understanding where things are coming from if it's a development or a specific commit it's going from is coming from a different source in this case is coming from Shaman that。

Not an official repository and it goes on to do several different things。

 including creating the right the right constructing the right URL to get the proper GPG key but do you see the amount of steps Can you imagine doing that manually let's forget about the code and the fact that this is Python and not rust but can you imagine going through this kind of setup in a manual way several things are going to happen without automation you're going to have potential typos and this will probably not be correct you will miss steps where things are going to you're going to misremember steps or put them in the wrong step or in the wrong place or things are going to go into the wrong order。

And because there's so many， the potential to create a problem is going to be an order of money to hire if unless it was scripted like in this case where things are fairly structure like this is a big script but you can see that it has several steps and is doing it in a specific order So those are two examples of what we have here for automation。

 but in essence， you are building things that will be reproducible that will be fast and it will be easy to update and maintain。

 because you're going to be able to quickly identify things like say for example。

 that in a special extra installation flag when you're trying to add certain certain component or make a change that before it wasn't working instead of having to remember absolutely all of the conditions every time you see an else or an F or an LF in this case in Python。

But the same thing with rust， you are branching off into a specific situation like in testing。

 this is called branching and every time you see an L or an if or an LF or an L creates a condition。

 a branch and all of these all of these conditions need to be met and you will need to remember that。

So automation will allow you to go faster， will allow you to be more efficient to create more robust processes that can be reproducible and maintainable in the long term。

 and these two examples are good from the simple to the more complex。



![](img/d63a28ab82291e07bb58e8936b851913_2.png)