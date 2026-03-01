# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p42 42_02_03_在Python中实现基础日志.zh_en -BV1Hy411q7Zm_p42-

![](img/5d10c4564762bd00e9d4345d33c597a8_0.png)

Adding login in Python is a little bit straightforward to begin with。

 which is something that I really enjoy and really like because when we have something that is easy to get started with Well。

 it entices you to try to make it a little bit more complex later Now how can we do this in Python where we can add the login module。

 you don't need to install anything it comes with the standard library。

 you don't need to install anything and the basic configuration。Is something that we can do here。

 we can do logging， essentially what Gihacopiloot is suggesting right here。

 So this basic config is takes care of all of the configurations that the login module allows you to set and tweak to have something that basically will be a good default essentially it will emit messages to standard error on the terminal when you're running with just that basic configuration and we can try it out and to you said you can actually go and do log in the debug and say sure this will get logged or we can see something like this is a debug message sure。

From main pi and we save it and then we can run it。 I've already done Pipinst dash E here。

 which is the same as Python set of the pi developed Now I have my always my virtual environment activated。

 that's signal there and I'm not repeating myself。 So we can do which block pi and that's our tool that we've installed right right there。

 So we're gonna to say block pi dash dash help and if I do that you will see that this is a debug message from mainda pi is coming from right here。

 So with just two lines or actually just one line of configuration you can start adding your messages。

 but let's take this a step further's let's try to make it a little bit better and what I want to show you right here。

 let's toggle。Terminal so that we can see you can see here that there's a root here。

 Why do you think there's a root。 Well， here's the level。

 and here is the logger and this is called the root logger。

 This is actually the message and that's the root logger。

 So what is a root logger is the parent logger of all of the loggers in your application。

 So let's change this because root doesn't really tells us much。

 So in order to do that what we're going to do here is we're going to add a log variable。

 a global login variable I'm going to say login get logger and yes。

 we're going to do underscore name I'm not going to go into the details just yet about what that means and I'm going to remove all of that here I'm going to leave that there。

 and then I'm going to go here into main and I'm going to say。

The this is going to be I'm going to set the configuration there。

But instead of using logging the debug right right here。

 what I'm going to do is I'm going to bring in this variable from there。

 so I'll show you what why like I'm going to use logging the debug there I'm going to say log。

That Dbug， this is a message from main function。And when I save it。

 now I'm going to toggle the terminal again。 and'm going to run block by help。 Now。

 block by help is not actually doing anything because it's just inter intersecting。

The help menu is now reaching the main function body I'm going to type block pi and I'm going to pass in the device that I know will work which is V1 and we are now hitting the main function and let's go quickly back to the main function and you will see that we have logging that debug and we have logged that debug So what is the difference between this one and that one you will see that this one is the root logger while this one says block pi or BLk pi that main what is this well this is giving you the ability to well it is being said by this it could be actually say here my app。

And and then anytime you're using log you'll say my app。

 So let's lets let's try this again really quickly and you will see my app now shows here。

 So why is this important Because now we can actually start saying let's leave it with name。

 now we can start actually doing things like for example。

 going to our utility here and adding more things here at the top I'm going to say import login。

And I'm going to say log equals logging at logger name and then I'm going to say log that info loading utility module right So let's see let's see what happens I'm going save that let's see what happens when I do that'm I clear I'm going to run this again and then we are well this is actually this is actually not correct。

 So let's just actually very quickly fix fix that So this is not this is not the string so I made a mistake right there So okay so let's do that and run it and block by Bda1 So we have back our root logger our block by logger with main block by that main but our new login statement doesn't work and why is not working Why do you think this is not doing anything Well the reason why is because when Python。

Loing this is getting logged in before before the logging configuration is enabled。

 so what we can do here is actually do this take it out and let's say for example running command I think we can actually do a debug here and we can say running command this one like this one and that would work and give us some useful output for debugging so let's do block by V1。

And here you can see that we're getting really nice。

 good and useful output and where' is it coming from blocked by that uT So this allows you to know exactly where these login statements are coming from So this one's coming from UT and this one's coming from main and this is the root logger which is the parent logger So there you go that is how you add basic login to a Python application in a very straightforward way plus understanding where are some what are some of the options that you have when you want to implement login elsewhere in your application。



![](img/5d10c4564762bd00e9d4345d33c597a8_2.png)