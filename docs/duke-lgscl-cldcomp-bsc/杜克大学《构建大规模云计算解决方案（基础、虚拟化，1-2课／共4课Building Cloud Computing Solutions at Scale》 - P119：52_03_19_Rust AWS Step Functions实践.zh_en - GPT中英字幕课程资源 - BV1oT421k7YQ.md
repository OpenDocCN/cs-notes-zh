# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P119：52_03_19_Rust AWS Step Functions实践.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/97a6ea77e583ae91700009fdd985a438_0.png)

Okay， let's dive into how to build step functions from AWS using rust。

 Step functions are really powerful in terms of serverless workflows because you can chain together multiple operations and take the input of one Lambda function。

 process it and then put the output into another Lada function And what's really fun about it is you can drag and drop and create your own workflows。

 almost like working with Legos and you can see here。

 this is a diagram of the workflow And then when it runs。

 you can actually introspect and go right into the details of what one function is delivering and what the other one is receiving。

 And this is incredible in terms of debugging。 So can you do this in rust， Yes， you can。 All right。

 let's go ahead and take a look at how you would do this and rust first step。

 I have a step functions directory right here。😊。

![](img/97a6ea77e583ae91700009fdd985a438_2.png)

And inside， I have a rust Marco， which will be the first step function， and then I have a rust polo。

 All I needed to do in order to create this was use the excellent cargo Lambda library。

 which you can see here， I just said cargo Lambda new rust Marco。

And if we go into the source code right here and we take a look at it， I have input here。

 which is the struct and this is the actually let's go to this one right here， which is the name。

And this would be the input to the function in terms of the output we would have the payload that's being sent。

 The handler is where all the work is done。 I have an asyncN handler right here and we say let name event payload name so I take the name value from the Jason payload and I say listen if the name is Marco。

 then I would actually like to make the payload body polo， otherwise let's make it nobody。

And I also add some tracing here so that I can have some debugging inside of my Lambda console。

 Now next， all I have to do is prepare the response right， and so this will be the return payload。

 It's automatically serialized for us when we send the OK and the payload body right here is again。

 just what's inside of here Now to deploy this or run it or whatever I like to use make files And so what I do here is I say make release and all it does is run cargo Lambda build release and we can actually go into this director real quick and take a look at it。

And let's go to step functions。Marco。Rest Marco here。

And we can say make release and we can see what what it does， right， There we go。

 But it's already been released。 so we don't have to do anything。 And then if I say make deploy。

 it would it would then go ahead and redeploy the function you can see again since it didn't have to do anything。

 it was it was very fast。 Now， if I want to invoke it and see what the payload will actually be。



![](img/97a6ea77e583ae91700009fdd985a438_4.png)

I would have to say cargo Lambda invoke remote。Put the name of the am 80 w Lada function here and then send in the payload。

 In this case， again， the make file makes it easy。 I just go ahead and say make invoke。 Now。

 what's great about this is then I can do the same thing for the second one。

 So let's go over to Russ Polo here。Let's look at this one。

 so I know that I'm going to have to accept a payload。 that's the body of the other lambda。

 and then I'm going to return a payload as well。 So at first I say let the name is you go to payload payload and then if I look for the word polo right that was the successful response from Marco。

 I say you win otherwise I say you lose and again， I add some tracing here。Very simple。 Yet again。

 I just add a response right here， which gets serialized and sent back to the user。 Yet again。

 if I just go ahead and I see the up here and we go into the rust polo。Right， we can say make invoke。

And this will be a little bit different， but not much。

 which is that I'm going to send in the payload polo right， And this would say you win。 Now。

 if I want to change it， for example， and I say， you know， no， for example。

 and we change that iss going say you lose right So a very。

 very easy and convenient way to build Lambda functions， and you can see it's very straightforward。

 So now to use them， what do we do， So we can go over to the step functions right here。

 and let's actually just make a new one。 So I'm going to go ahead and say create new state machine。

 go next， and it's just like Legos， I just drag one and we can call this one you know， rust Marco。

And then we could build another one。After this one， but first let's give it the the rust Marco here。

 which is this one。Al。And then we drag a second one。And we say rust polo。 And this would be。

Instead of lambmbda invoke， we'll call it Ru polo。Ras polo。There we go。

 and then again we just go ahead and choose this and we sayre polo。

 Now what's beautiful about this is that we're done and it gives me the the J output if I want to copy this and store it somewhere。

 but you can see here here's how it works。Once I verify that that's what I want。

 then I can name it a step function， we'll call this rust Marco polo chain。

And we can go ahead and say create state machine。 Now， in order to execute it。

 I could call it from the command line， which is actually a nice way to do it。 Or I just say start。

 it gives it a optional， globally unique I。 And then here's where we have to chain things together。

 I would just say name。Here， and we would say Marco。 and this will start the chain。We go over。

 we can watch it actually being executed。And we can say the first input right here。

Which you can see that the payload that was returned was polo。

And then we can hear see this one as you win。 so really straightforward， actually， to run this。 Now。

 if we want to do a failed execution， let's go ahead and do another one。 So let's go back to this。

 It'll do another And let's just leave this default here。 and you can see it'll actually blow up。

 It won't work。 So oh， there's a problem error message， and we can see that it failed。

 So it's a very good debugging as well。 And and this is a great way to build reproducible services with rust and AWS and hopefully give this a try。

😊。

![](img/97a6ea77e583ae91700009fdd985a438_6.png)