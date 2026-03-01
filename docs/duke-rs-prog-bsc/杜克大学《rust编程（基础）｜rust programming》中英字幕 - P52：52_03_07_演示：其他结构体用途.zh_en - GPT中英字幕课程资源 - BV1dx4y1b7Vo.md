# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P52：52_03_07_演示：其他结构体用途.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/d14f52af77937c812798c6eebe8638e5_0.png)

There are other ways that we can define how we can essentially we can create a new instance of user in this case。

 so before we've done something like， for example user and we've done something like these where actually passing passing these fields and those are fine。

 well this is actually incorrect， email is John at samplele。com。And then that's fine。

 And we have that ability of creating that。 So we in this case， we also need to do everything here。

 we can say sure that UI and active is true。 Okay， perfect。 So there we go。

 we have the ability of doing it that way。 and that is definitely valid。

 but there's also a different way。 and I'm going to actually show you how so I'm going to make this go away。

 I'm going to lose some surgery here。So we can actually start doing defining these as variables。

 so if we say let username。So if if these are named。

 let's actually let me go through all of these and then come back Al right I redefined everything to be a variable with let and then using of course the semicolon at the very end so I've defined this and there's a shorthand way of doing this and rust allows me well there's the condition is that that the fields the variables need to be the name the same as the fields so I can now pass in username。

Email your eye active。 And this is perfectly fine。 Look how much nicer that is。

 So if you have something that is already coming from elsewhere。

 you can definitely do that and it's very very， very convenient。

 I really like this Now the condition， of course， is that the variables need to match the name of the fields。

 So in some situations， you know you might be updating astruct somewhere and now this't this doesn't match and then you start having problems and you need to do some heavy reraing。

 but probably using something like visual code with some some of the extensions for rust。

 you will be able to rename those for compliance。Then the other thing that I wanted to show you wasstructs with that can be created as tuples or tuples。

 so if you can say struck for example point and we can say these three points what does that mean well it means that we can access these tuples fields but using indexes because these are these are not named right these are just types there so we can say something like let my point。

 something like that we're passing 10，20 and 30 and then we can we can access those attributes saying points are my point and then zero。

Actually， this would be like that and then passing passing that value like that。

 So these0 would be that one and then one would be these and then two will be that。 So in this case。

0 is going to be 10 right here。 So let's just run it and see what we get yeah， we get points 10。

 and thens that's fine。 So those two are some other things that you might want to run you may run into when you're dealing withstructs and definitely have the the ability of being useful in their own and you know like the main difference here with the tuple and the regular struck here with user is that these fields。

 well， you can you have to name them。 and if you're using the same variable names were going to have the ability of creating them on the fly with a shorthand。

 we kind of like saw that in the constructor。 but if you missed it。

 this is definitely the way you would do it without a constructor。



![](img/d14f52af77937c812798c6eebe8638e5_2.png)