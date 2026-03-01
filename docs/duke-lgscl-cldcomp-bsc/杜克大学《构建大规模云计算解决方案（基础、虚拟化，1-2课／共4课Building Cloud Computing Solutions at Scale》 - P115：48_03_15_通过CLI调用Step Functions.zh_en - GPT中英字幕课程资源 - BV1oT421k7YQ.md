# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P115：48_03_15_通过CLI调用Step Functions.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/f3314e3af3fb8c951703fd5ff93954e2_0.png)

Once you have a step function that is orchestrating one or more or who knows。

 maybe half a dozen lambda functions inside a coordinated distributed application。

 one of the better ways to implement an execution is to simply use the AWs Cloud shellll and the Ci。

 So let's go ahead and take a look at how that would work。 if we go over to step functions here。

 you can see that there's a step function state machine add device。 So this is the orchestration。

 of course， I can do it from the console， but this doesn't necessarily give me the programmatic control that I want。

 So let's go ahead and go over to a cloud shellll andvocation here。 So again。

 you can just launch the Cloud shellll right here。 Now。

 if I wanted to run this an easy way to do this would be to first put in the command AWS Next step we do step functions。



![](img/f3314e3af3fb8c951703fd5ff93954e2_2.png)

Then I would do start。Execution。Now， all I need to do is put the name of the iron。

 So it would be dashache state machine A R N。 And then I would go over to my R and copy it。

 So in this case， I can actually go to this R right here。



![](img/f3314e3af3fb8c951703fd5ff93954e2_4.png)

![](img/f3314e3af3fb8c951703fd5ff93954e2_5.png)

Go back to the terminal and just paste it in。Now the only thing I need to do to finalize this is to put in an input。

 so we're going to do dash input， and then this is where I would put in adjacent payload so I'm just going to paste the sense since I've got it handy right here。

 So if I run this。We're able to actually execute it， and we can see that it was successful。 Now。

 if I go over to the。

![](img/f3314e3af3fb8c951703fd5ff93954e2_7.png)

Console here before there was two。 if I refresh， there should be three。 There we go。

 And then what what I also can do is go over to the step by step details here and even see what the payload was that went into this particular function。

 So this is really powerful to have this kind of iterative feedback loop now。



![](img/f3314e3af3fb8c951703fd5ff93954e2_9.png)

Let's go ahead and make it a little more exciting。 if I do the up arrow here。Obviously。

 if I run the same payload over and over again， it might be hard to tell what's going on。

 So let's go ahead and change this to 13 and we'll change this one to 13 as well。

 and then let's run it again。

![](img/f3314e3af3fb8c951703fd5ff93954e2_11.png)

There we go。 We've been able to do another execution。

 If I go over to here we see now there's four executions。 Here we go。 we can see that in fact。

 it did take the payload 1313 divided by two there we go The total is 26 afterwards so we've been able to successfully take this and the output is going to be 13 and we're able to reproduce this using the CI So the CI with EWs Cloud shellll is one of the better ways to start to orchestrate your functions without having to do a bunch of SDK development you can get in there test some ideas out and make sure it works。



![](img/f3314e3af3fb8c951703fd5ff93954e2_13.png)

![](img/f3314e3af3fb8c951703fd5ff93954e2_14.png)