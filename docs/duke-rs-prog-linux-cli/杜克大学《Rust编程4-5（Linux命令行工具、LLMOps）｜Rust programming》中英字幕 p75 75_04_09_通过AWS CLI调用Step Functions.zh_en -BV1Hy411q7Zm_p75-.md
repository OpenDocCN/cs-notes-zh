# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p75 75_04_09_通过AWS CLI调用Step Functions.zh_en -BV1Hy411q7Zm_p75-

![](img/9ab124f1ecba599d451841a52c6b0f3c_0.png)

Yeah。Once you have a step function that is orchestrating one or more or who knows。

 maybe half a dozen lambda functions inside a coordinated distributed application。

 One of the better ways to implement an execution is to simply use the AWs Cloud shell and the CI。

 So let's go ahead and take a look at how that would work。 if we go over to step functions here。

 you can see that there's a step function state machine ad device。 So this is the orchestration。

 of course， I can do it from the console。 But this doesn't necessarily give me the programmatic control that I want。

 So let's go ahead and go over to a cloud shell and vocation here。 So again。

 you can just launch the cloud shell right here。 Now， if I wanted to run this。

 an easy way to do this would be to first put in the command AWS。 Next up， we do step functions。



![](img/9ab124f1ecba599d451841a52c6b0f3c_2.png)

Then I would do start。Execution。Now， all I need to do is put the name of the iron。

 So it would be dashache state machine A R N。 And then I would go over to my R and copy it。

 So in this case， I can actually go to this iron right here。



![](img/9ab124f1ecba599d451841a52c6b0f3c_4.png)

![](img/9ab124f1ecba599d451841a52c6b0f3c_5.png)

Go back to the terminal and just paste it in。Now， the only thing I need to do to finalize this is to put in an input。

 So we're going to do dash input， and then this is where I would put in adjacent payload So I'm just going to paste the sense since I've got it handy right here。

 So if I run this。We're able to actually execute it， and we can see that it was successful。 Now。

 if I go over to the。

![](img/9ab124f1ecba599d451841a52c6b0f3c_7.png)

Console here before there was two。 If I refresh， there should be three。 There we go。

 And then what what I also can do is go over to the step by step details here and even see what the payload was that went into this particular function。

 So this is really powerful to have this kind of iterative feedback loop now。



![](img/9ab124f1ecba599d451841a52c6b0f3c_9.png)

Let's go ahead and make it a little more exciting if I do the up arrow here。

 obviously if I run the same payload over and over again， it might be hard to tell what's going on。

 so let's go ahead and change this to 13 and we'll change this one to 13 as well。

 and then let's run it again。

![](img/9ab124f1ecba599d451841a52c6b0f3c_11.png)

There we go。 We've been able to do another execution。

 If I go over to here we see now there's four executions。 Here we go。 we can see that， in fact。

 it did take the payloads 1313 divided by 2 There we go。 The total is 26 afterwards。

 so we've been able to successfully take this and the output is going to be 13。

 and we're able to reproduce this using the CI。 So the CI with EWs Cloud shellll is one of the better ways to start to orchestrate your functions without having to do a bunch of SDK development you can get in there test some ideas out and make sure it works。

😊。

![](img/9ab124f1ecba599d451841a52c6b0f3c_13.png)

![](img/9ab124f1ecba599d451841a52c6b0f3c_14.png)

![](img/9ab124f1ecba599d451841a52c6b0f3c_15.png)