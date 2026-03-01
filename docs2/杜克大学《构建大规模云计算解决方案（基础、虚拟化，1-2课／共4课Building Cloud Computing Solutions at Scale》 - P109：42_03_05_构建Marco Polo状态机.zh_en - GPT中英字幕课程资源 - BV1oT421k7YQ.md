# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P109：42_03_05_构建Marco Polo状态机.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's look at AWS step functions， which are a way of orchestrating。

Different lambda functions together to do different things。 If we take a look here。

 you can see that there's a workflow where something gets fetched。 it goes through。

 and depending on what operation occurs， it processes one direction or another。

 So that's really the gist of a step function。 So if we want to go through here and look at a hello world example。

 you can see here how inside of this JN format， you can go through here in this particular step function。

 I could run through it。And it will actually allow me to run through this whole machine。

 so let's go ahead and try that out。 We'll say hello world， create a new role。

And go ahead and create this machine and then this is going to be the first payload that goes in。

There we go and now watch what will happen is each of these things will go through。

 it'll run through step by step， it'll wait for three seconds。

 and then I can if I want to even look at each of the inputs as well so I can see what went in。

 what went out， I can see that here we go， here's the step input right here。

 here's the hellello world。So it's a great way as well to get very good debugging。

 So let's go ahead and build out a slightly more complex step function ourselves。

 I'm going to go to these state machines here and I'm going to go to Marco simple。

 And let's go ahead and take a look at what this thing actually does。 So if I go and I say edit。

 you'll see that it's a very straightforward way to build a workflow as I first have a function here called Marco that is a lambda function and what happens is it grabs the output and passes it into a polo function and then once that polo function is done。

 it goes through and finishes it。 So let's go through here and run this。 So I'm going to go back。😊。

And now run this function， so I'm going to say start execution。

And noticeice here that it's going to look for an initial payload right so before I do that。

 let's look at each of the lambdas that are actually associated with this function。

So how do we do that？ Well， I can first start an execution here and just see what happens and that's one way to do it。

 And look we can see that it already failed at this particular lambda function and if I look at the input。

 we can see here's my input and if I look at the output。

 nothing happened right so it failed there So it gives me a great visual of actually what's happening Now if I click on that lambda where it failed I can take a look at what the code is that's actually running。

 So if we go over here and I look at this particular lambda function。

 I click on latest and I can look at the code。 you'll see that it really does almost nothing。

 there's an event it is looking for the word name and if that event if there's a name event that has the word marco or turn back polo。

Now， if I go back to this other step function again and I look at this polo function afterwards。

 we can see that it will then go and do the next step right so what I'm going to do is execute this thing again。

 but this time I'm going to say name。And we'll say Marco。Here we go。And let's go ahead and run this。

 let's start this execution。 Now you can see that it's running。And from here， if I scroll back here。

 look， I can see this has already been run， this is currently being run that's in progress and we can see it finished。

 So let's go through step by step。 First what we do is we pass in that J payload name Marco what happens Well it returns back Polo So then it passes that output into this next function we see again that this one accepts the word name Marco and then what is this thing I'm sorry it accepts the polo input and then it returns back the word Marco So basically it transpos the inputs and the outputs and then finally when it's done we can see that it finished successfully So these are really powerful ways to build composable serverless functions and piece them together and also do things like have different states where if it fails。

 you do one action or if it succeeds you do another So in a nutshell step functions are a great way。

To learn lambda functions， and in our particular example， we could easily debug what happened。



![](img/989f7bec68b6ac460911340439ce8895_1.png)

![](img/989f7bec68b6ac460911340439ce8895_2.png)