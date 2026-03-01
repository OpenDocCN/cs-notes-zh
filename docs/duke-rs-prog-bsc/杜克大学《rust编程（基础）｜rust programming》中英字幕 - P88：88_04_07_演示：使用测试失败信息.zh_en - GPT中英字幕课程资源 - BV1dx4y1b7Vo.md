# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P88：88_04_07_演示：使用测试失败信息.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/f08186da59488e2e8f63ea4a58e7c115_0.png)

There are situations where you may want to add more context to the possible failures that your tests may have。

 So in this case where we're creating these test read standard in and we had the new line。

 What we can do is we can extend that with the assert equals and and this will work for assert equals both with that and assert not equals。

 So let's actually show you how you you can do that。 So that's not equal。

 So that's meaning line will not be equal to test now this will fail because these are equal。

 I'm gonna run that and it fails right So if I go all the way to the top because I'm I'm going get。

A problem here with a panic， which is part of the failure。

 you can see here the left is not right because the assertion failed。

 so let's make it equal to so that we can make it a little bit more so that makes more sense。

 but let's assume that we're going to have we're expecting to have a failure at some point。

 but if we have a failure。I want to provide more context and the way you do that is you pass a comma and。

You could add something like what Copit suggests here that says line should be test。

And it isn't right， but I mean that's kind of like a silly example。

 but that is how you would do it you would pass in an extra argument。

 which is this one right here and these two are required。

 So if I run this and it fails but well it's not going to fail because let's actually make it fail so let's say for example。

 that one changes So it's DES instead of test I'm when I run the test。Going to get。

 I'm going to make this a little bit bigger。 scroll away to the top。

 And now what we're going to have is that message right here。 line should be test。

 but it wasn't right。 So whenever you want to provide more context into why your failures are happening。

 this is certainly the right way to do that。And it is actually best practice if your test name is not very meaningful or this is getting rather complex。

 or perhaps if you have multiple assert assert statements in one single test。

 Now a couple of recommendations that I have is try to make the test function names meaningful。

 Like if the names are useful， then the failure should be pretty selfexplanatory in this case。

 test read centering is not very good。 So actually let's go ahead and make that a little bit better。

 So do here is。I'm going to say these test read standard in new line。

So then I'm able to kind of like group together kind of like what I'm expecting， standard empty with。

New line sounds a little bit better that would allow me to actually go ahead and write on our desk it says。

That says test re center in empty with like that not not a new lines， we can say like that。

 and this should actually work as well。 So when that works perfect。

 but when you can see here test test read standard in empty works pretty pretty well。

 So those are things that you should keep in mind I think this is very useful don't overdo it because if you find it cumbersome to add it and the benefit is not too much。

 like in this case because this is a silly example， then the benefit is not well not very good。

 So those are things to consider and especially as your tests start getting more complicated or your assertions get more complicated in this case that we're using assert equals and this is pretty straightforward forward。

 this is just three lines and the expectation is pretty clear to what are we trying to do。

 So there you go that is how you add failure messages。In your tests， when you want more context。



![](img/f08186da59488e2e8f63ea4a58e7c115_2.png)