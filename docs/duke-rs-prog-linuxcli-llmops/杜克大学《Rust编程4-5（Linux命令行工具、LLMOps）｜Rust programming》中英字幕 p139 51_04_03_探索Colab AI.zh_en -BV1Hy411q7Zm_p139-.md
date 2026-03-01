# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p139 51_04_03_探索Colab AI.zh_en -BV1Hy411q7Zm_p139-

![](img/f06eeb763d42e28f9a540c0b7196caad_0.png)

Yeah。Here we have colaaboratory， which is a famous hosted geoputter notebook solution。

 and some of the things that it can do are very powerful。 So first up here。

 if we look at the runtime here， one of the things that we can do is change the runtime type and notice this。

 we have all these amazing types of hardware acceleration built in including the ability to do highRA use Tensorflow processing units。

 A100 NviDdia GPUs V100 NviDdia GPUus T4 GPUus， So these are really awesome capabilities that we get here。

 now another thing we can do that is also an emerging capability is that you can use generative AI right inside of the notebook。

 So let's go ahead and try this out。 So if we go here and we say coabab AI In fact。

 we can scroll over and even make it all about generative AI。

 So it's essentially a hidden AI assistant that's just right inside of here。 and in fact。

 why don't we try to。😊，Use the default queries here so how do I filter a panda data frame and we see here that it's giving us a great example I also could go back to this and give it more information so we can say here I want an example of how to do a simple linear regression。

All right， so here we have a code sample， so let's go ahead and try this out。 I'll copy this。

 We'll go to file new notebook。And we can actually just paste this in if we run it。

We'll be able to get a visualization here that will show us exactly what's happening。

 Oh we have one problem which is that there's a 2D array and we got a1D array instead so how could we fix this Well let's go in here and say the error and let's just see what it tells us okay。

 try reshaping our array to do a array reshape11 so let's go ahead and try that out。We go back here。

We can go back to the array here。And we can say NP。Horay。Reshape。On each of these， so we can say x。

Is equal to。And then we can say Y is equal to。And notice it even helped me complete that。

 And does this fix our problem。 Oh， we have a problem in that there is no attribute reshape。

 So let's go ahead and throw that back inside of here。

It looks like you're using a function or method as an array。So if I go back here。

I can just say maybe the whole example。 I can just say， can you。Help me fix this。

Here's the corrected code， okay， let's go ahead and throw that back in。

And let's paste it and let's see what happens。there we go， so you can see here that。

It's easy to get tempted to just blindly accept the answers and then when they don't work。

 you just give up， but just like a real programming problem。

One of the ways to approach this is to assume that there's going to be a problem with the generative AI results and that you're going to have to do this back and forth And so now there's a skill involved in that how do you ask the right question to get to the place that you need to go So this is I think one of the tricks with using these AI assistance here is that you have to assume that there always is going to be an issue with the code at some frequency。

 let's say 25% of the time and now the question is how do you actually proceed even though it's not going to give you the exact answer and one of the ways to do that is to narrow down and put those tracebacks inside of the assistant and to keep moving forward so that you're able to essentially bisect the problem into the pieces that are correct and the pieces that are not correct and this is really traditional programming it's just we have a new advanced tool that is going to give us a lot of help。

But with Collab AI， you can see here there's a great strategy to using it successfully。



![](img/f06eeb763d42e28f9a540c0b7196caad_2.png)