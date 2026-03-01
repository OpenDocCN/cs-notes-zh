# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P118：51_03_18_通过CLI调用AWS Step Functions.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/86e929da0e52e0e7399db886207cea2a_0.png)

Here we have a couple of Lambda rust functions that I'm going to invoke using the Ci。

 and I'm at first build out this step function infrastructure。

 So since these Lambda functions are already deployed here。

 All I need to do is go over to this function section here。 Doub check that they're there。

 and we can see here rustad divide by two perfect， and once these have actually been set here。

 In fact， we can refresh and we can see that this is actually both a rust runtime。

 I can go over to step functions and get this running。 So let's go ahead and do that step functions。

 build a new one real quick。

![](img/86e929da0e52e0e7399db886207cea2a_2.png)

![](img/86e929da0e52e0e7399db886207cea2a_3.png)

Greatate state machine， let's do a visual workflow。

And what I will do here is say a rust based workflow， rest based workflow。

 And then just drag two of these on here。 So first up， this one will be add。

And the next one will be divide by 2。 Allright， divide by 2。

 let's go ahead and pick this one divided by two latest， perfect。

And all we need to do now is just say next， we can see the layout。And go ahead and run it。

 So we'll call this one rest。Divide。😔，Workflow。Create this new。State machine here。

And we'll go ahead and start the execution。 I' just going to need to pass in。An x。

Which will be one and a Y start execution。Add input as this。The output is4 divided by2。

Output calculation， input total。 So we got this thing working。 Now， how do we run this， Alright。

 let's go ahead and。

![](img/86e929da0e52e0e7399db886207cea2a_5.png)

Tell our environment here to set the output type to JON， now all I need to do is invoke that urn。

And what's great about this is great。 I'm able to see the execution。

 And if I go back to our environment here and I look at the executions and I refresh， aha。

 we can see that there are several executions here。 And in fact。

 I could even double check and put a new execution。 So let's go ahead and change the value。

 Let's change this to5。 Let's do it again。😊。

![](img/86e929da0e52e0e7399db886207cea2a_7.png)

Perfect， and if we go back to this environment here， refresh it。

We should see that the latest execution， if we go to the input。There we go。 Ha five inside of it。

 So a really powerful workflow to build it up and rest， get this really advanced， cheap， fast。

 computational workflow， put them into step functions， and then invoke it from the C I。



![](img/86e929da0e52e0e7399db886207cea2a_9.png)