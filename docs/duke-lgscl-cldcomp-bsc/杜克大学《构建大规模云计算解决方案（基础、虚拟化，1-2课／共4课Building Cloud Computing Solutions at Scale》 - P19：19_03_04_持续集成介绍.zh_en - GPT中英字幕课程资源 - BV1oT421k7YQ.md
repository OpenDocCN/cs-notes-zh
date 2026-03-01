# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P19：19_03_04_持续集成介绍.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

What is continuous integration and why do you even care about it。 It's a really important question。

 It comes up a lot when I'm teaching students about building software where I'm working with a company in a consulting project。

 a lot of times its really something that people misunderstand they feel like when you do automated testing or you have to write tests。

 It actually is wasting a lot of time， but it actually saves you a lot of time。

 Let me give you a few examples。 For example， why do you have smoke alarms in your house， Well。

 presumably you don't want to silently die in your sleep because there was a lack of oxygen So it's an automated way to ensure your survival Likewise。

 why do we test for new drugs to make sure that they're effective Well we want to make sure that the drugs that we're delivering for some medical condition are actually helpful and not harmful Likewise。

 why would you wear a seatbelt a seatbelt ensures that if there's。

Sudden event like a crash that it'll stop you from being ejected from the car。

 So these are all forms of automated testing and safety mechanisms and they actually save your life the same thing goes for testing software what continuous integration is it's a way of always making sure that your software is in a known state and that it actually saves you time so those are probably the two big things to remember about continuous integration is that your software is always knowable。

 you know what it is， it's either working or it's not and then it actually saves you time It doesn't cost you time。

 it saves you time once you understand those concepts it really frees you to develop software in a much quicker fashion because like the seatbelt analogy with a car you know that you've got something protecting you and you can go as fast as you want。

Let's dive into some of the technical details of continuous integration or CI。

A lot of times when you're starting with continuous integration， the best step is to work local。

 so let's suppose this is a local environment， it could be， let's say a cloud9 environment。

 it could be a desktop， it could be a laptop， it could be whatever machine you want。

The first steps would be to create a local scaffolding so you could get a make file here。

 you could get your tests inside your project and then you could maybe create a virtual environment as well and then go through here and make sure that the code works so you could say make test for example and this would ensure that you you've got a checkmark here you've got it working locally once that is set up the next thing to do would be to make sure that your SaS built server like GitHub actions is ready to automatically test your code so we'll assume this is Gitthub actions here。

And and then inside， what will happen is that every time you make a change to this environment。

 there'll be an event that's triggered that will essentially check out your code。

 So we'll say CO and then it'll go through and test it。 That's it。

 So really it's a way of replicating what happens locally to the SaS build server that's in the cloud。

 and we can make this a cloud here。 So in a nutshell。

 all continuous integration is is a way of doing the things that you're manually doing over and over again in a repeatable fashion。

 you see lots of examples of this in the real world， for example。

 you wouldn't necessarily want to build a car by hand every single time you're trying to build a car。

 that's why they have factories to build it。 So this is a testing factory that automatically test your code and repeats it so that you know your code is always in a known state and that it will save you time。



![](img/62502bc4ab4f4c69ff6ee19ee98e8ecb_1.png)

![](img/62502bc4ab4f4c69ff6ee19ee98e8ecb_2.png)