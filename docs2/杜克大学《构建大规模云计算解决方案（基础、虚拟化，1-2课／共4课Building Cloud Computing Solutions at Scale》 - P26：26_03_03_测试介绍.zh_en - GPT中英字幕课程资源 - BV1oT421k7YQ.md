# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P26：26_03_03_测试介绍.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/9e60eb2f61e7fa1d0f988f959456cfe4_0.png)

So what is testing and how can you use it to get yourself out of big trouble。

 I thought I would share a few stories of sometimes I've had to get myself at of big trouble with testing one time midway through my career。

 I was in a barrier working at a film company。 And we had some really big problems In fact。

 the entire facility which was worth hundreds of millions of dollars hundreds of employees was stuck in that they couldn't work anymore。

 and we had an immovable deadline。 We had a movie that was going to be released in Christmas and the posters were already up Disney was behind it and we really had no way of fixing this problem other than to kind of dig into it and figure out know how to fix it。

 So what we did was step1 is get some kind of a test working in a simulated environment。

 That's probably the first thing you can do to get yourself out a big trouble is can I take production and replicate it somewhere and。

This is oftentimes， if you haven't set up a continuous delivery type environment。

 you can still get yourself out of trouble by running a simulation somewhere Once you at least can run it you can verify that somethings you going on and then the next step would be to add instrumentation and monitoring So what you'd want to do is add logging add some dashboards that show what goes on and the combination of those two things is really。

 really critical because you can actually verify what happens and then look at the points that are critical failure points and then fix those really this is science this is like a biology lab where chemistry lab where you do in hypothesis。

 you see if the hypothesis works and then verify the next series of actions。

 So that's probably the number one tip I would give somebody is to think about doing in test in a simulation。

 The other thing to remember is that it's easy to get caught up in the purity of test。So if you say。

 well we don't have 100% test coverage so we can't do anything or you have to have full functional tests but really it's the wisdom of an experienced software engineer will tell you that it's really selectively choosing when to test something using just enough to really solve the problem and also having it automated is really the key to having a successful testing strategy really thezelowtry towards any kind of a technique is a way to get yourself in trouble as well if you get too far down the road of I have to have test for everything。

It's possible your project will just grind to a halt because you're spending so much time testing。

 So also you can go to the extreme on the other end。

 so really if you can do a little bit of everything。

 almost like you know the fairyt Goldilocks a little little too hot is one extreme。

 a little too cold is another you want to just write， that's really the best way to handle testing。

 So let's get into some of the details of that in this next section。

So what should your testing strategy be， as I mentioned before。

 the just right strategy is an important way to think about testing。

 You don't want to do too much and you don't want to do too too little。

 You want to have enough that you know that what you're doing works the other thing to keep in mind is judgment right so you know do you have you know a suspicion that a part of your application might have a problem。

 Well， write a test。 You know that's one of the ways that you can actually account for things that are trouble you。

The other thing is that they save you time right， they're not a time waser。

 And I think this is probably the most common beginner mistake is that people don't write any tests because they're so stuck on debugging their code。

 but really what a test is is it's code that you've debugged and that you don't have to debug the same thing again。

 Why would you go through and add a print statement and pass a variable into a function over and over again every single day for a year。

 when you can just write a test that verifies whether your code works。

 And so I think this is one of the most common mistakes I see。 and finally， automation。

 once you've got some testing working， you have to automate it so that the build server or in the case of Giup actions。

 it would go through and test it automatically， this really gives you the opportunity to do this step of improvement you're constantly going through and making sure on a daily basis or even a multiday basis that your code is getting better its。

You know what's happening and that it's a constant state of improvement and there's a word for this。

It's called Kaiszen， so really this concept of Kayzen or continuous improvement is the goal of testing it should be your strategy and really to summarize you want the just right strategy。

Just a little bit here， but not too much。

![](img/9e60eb2f61e7fa1d0f988f959456cfe4_2.png)

![](img/9e60eb2f61e7fa1d0f988f959456cfe4_3.png)