# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P123：56_04_05_使用AWS CloudWatch实现监控触发与告警.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

CloudWch is a very powerful resource that helps you in pretty much anything you're doing on AWS。

 Let's go take a look at how that works。 So let's type in CloududWatch。😊，There we go。

 This allows us to monitor resources and applications。 And from here。

 there's a bunch of different things that we can do。

 So one of the things that you can do is you can set up alarms。 You also can use it for events。

 So you can trigger a Lada at a certain interval。 So for example。

 if we wanted to take our Marco Lambda function and call it over and over and over again。

 you could do that and also you can look at logs and metrics。

 So's there's really these big categories here， alarms events， logs and metrics。 So in fact。

 we can really investigate all of the main features of cloudwach by going back to that Lambda function。

 So let's go through here。 and let's go to our Lambda function again。

 and let's take a look at some cloudwatch logs。 that's a good place to start。

 So every time we call this Marco function there's a monitoring tab here because you see that it has access here。

And your function could go through here and access it now。

 because previously I changed the execution role， I'm going to have to change it back so that it has the ability to do more than just read from S3。

 so what we're going to do is we're going to make it go back to its default execution role， which。

Let's see here we can either do that。Or what we can also do is just I have a development role here and we'll go ahead and we'll save that Okay。

 so once I have that role set up here and I refresh now what we'll do is we'll look at monitoring and you can see these cloudWch monitoring and I can run this function if I just test it over and over again。

 I can get some log entries and I can say view logs in CloudWatch。



![](img/ae4a7c9e3f2f9ea31cdc07f585d1f2b5_1.png)

![](img/ae4a7c9e3f2f9ea31cdc07f585d1f2b5_2.png)

And from here， you can see by the timestamps I can go through here and I can see the latest log files。

 so this is a great way to debug things and Lambda is to use again our CloudWatch log search mechanism。

 I also could go back to my function if I wanted to and write debug messages。

 This is a really common thing to do。 let's just print in， we'll say this is my event。

We'll go say this is my event and I can pass in。These curly brackets here with the word event。

And this is called an F string and Python and this allows us to capture that and print it out to those logs。

 if I say save and again I test this， I run it a bunch of times those boB messages will show up and also these Marco messages which will be able to show up so let's again go back to our CloudWatch monitoring here and look we can see invocations durations So this by itself is pretty helpful but if you want to really get into the weeds it's great to actually look at the actual output itself and we can see all the different outputs as well and so whatll happen here is as we get more into this willll be able to look at the specific log messages so here we see that now that I add that new output I can find it in there。

 so CloudWatch again has lots of different features and logs is something that you'll use a lot when you're developing applications and you can go to let's say Lambda and actually put in messages inside the function itself to get that。

Debugging right and that's what that message does So another thing to point out as well that is relevant to the Lambda ecosystem is I also can add a cloudWatch trigger so let's go through here and let's go to let's say cloudWatch events and from here I can actually create a new rule if I want to so let's go ahead and create a new rule and we'll call this noisy noisy1 one minute and just say this this is a very noisy。

Call。And this is going to happen the call that happens。Every minute。

 and I can tell Cloudwa to call us over and over and over again。 So how do I do that？ Well。

 all I got to do is just say rate。One minute like that。

And then this is going to actually trigger every single minute now。

 so if that's actually the correct syntax， I think it's like this。There we go。There you go。

 so we've got that setup to be one minute and now what we can do is we can go again and look at these logs and we should be able to see this thing being called periodically from that that function So this is another thing you can do that maybe you wanted to set up a data pipeline again you would set up a rule here and you can inspect those rules for events and here we can see here noisy one minute and this will be called and we can we can even see how often this is called by looking at logs so I'm going to go through here and remove this trigger because that's actually not going to be a great way to run this Lada function it doesn't really do anything。

And then what we're going to do next here is make sure that we've got everything configured properly。

 make sure that the permissions are correct， and clean up anything else I want to do with this Lada function so as you can tell。

 CloudWatch is really the heart and soul of many of the different things you do in AWS from events to searching to actually going through and creating dashboards for you automatically。



![](img/ae4a7c9e3f2f9ea31cdc07f585d1f2b5_4.png)

![](img/ae4a7c9e3f2f9ea31cdc07f585d1f2b5_5.png)

![](img/ae4a7c9e3f2f9ea31cdc07f585d1f2b5_6.png)