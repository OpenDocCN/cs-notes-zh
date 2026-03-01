# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p81 81_04_06_使用Rust AWS Lambda函数URL.zh_en -BV1Hy411q7Zm_p81-

![](img/bdff9c974944582e8c2032c51571a158_0.png)

Let's use one of the most popular and performant languages in the world Ru to build a AWS Lambda URL。

 How do we do this？ Well， if we take a look at what Aws Lada provides。

 there's a new service that allows you to expose a URL。

 So it's very trivial to build a essentially lowco but high performance URL restbased service using AWs Lambda。

 Okay， let's go ahead and get right into it。 Now I have the code right here inside a visual Studio code。

 and let's go ahead and walk through it， I'm using a program called cargo Lambda。

 And when you first build out something with cargo Lambda。

 let's go ahead and just try it out real quick。 if I just say cargo Lambda new test。

 It's gonna ask me if I want to build an HB function。 If I say yes。

 then it'll give me a bunch of boilerp code。 and you can see what that boilerp code looks like right here。

 So this is pretty good。 if I want to do request parameters in my scenario though。😊。



![](img/bdff9c974944582e8c2032c51571a158_2.png)

![](img/bdff9c974944582e8c2032c51571a158_3.png)

What I want to do is I want to actually parse a URL。

 So I'm going to go ahead and go back into this rust Aws Ladasection here。

 and I'm going to seed into add URL。 Now I have the imports here。

 So I have add Lambda HDP then I have the serialization for J。

 How do I use that Well I go to cargo to Ml and I have insert a J right here Next up。

 I go through and I just tweak this function a little bit。

 So what I say is I extract the URL path from the incoming request。

 Now of course I could use some thirdpart library to do this but just for the sake of a demo。

 I'm going to parse it myself and then I'm going split this up into a collection。

 I then grab the first part I then grab the second part and then now all I need to do is take the sum that's passed in in this case in A and the B。

 and then I pass that into adjacent payload Next up， I build the response right here。

And I return back adjacent payload。 now， how do we actually run this pretty straightforward here。

 I'm going to run make watch。And this is going to invoke this server。

 Now I'm going to do a split screen here， and I'm just going hand code a call to the URL。

 So I use curl。 I'll say curl local hosts。9090。And we'll say add 2 and 2。And what happens， Oh。

 it wasn't able to find it because that's the wrong port。 I'm going to do 9000。A ha perfect。

 So we've got this total result here。 Now， pretty easy， actually， to then take it to the final level。

 So if I go to a make file here， all I need to do is do a build and deploy。

 So let's go ahead and do that。 Let's， let's actually kill this terminal here。

And let's just do a make build and make deploy。 So we'll say make。Build and make deploy。

 Let's see what happens。So what's going to do is it's going to build it for arm。

 which is the cheapest runtime for Lambda。 It's going to create an execution role。

 It's going to get all this stuff set up。 And then finally， it's going to deploy it。

 So this particular deploy process。Because I'm not using infrastructure as code。

 I'm going to do one final step， which is pretty easy。 Let's go over to our functions here。

 Let's find 9 seconds ago， the deployment， let's go to add URL and let's just go to configuration here and just add function URL So we go here we say。

 hey， just for a demo I'm going to do no authentication and all I need to do now is grab this function URL。

 go back to my terminal where I mean， I could also do it in the Cloud shellll。

 but let's go ahead and curl this curl。

![](img/bdff9c974944582e8c2032c51571a158_5.png)

![](img/bdff9c974944582e8c2032c51571a158_6.png)

And let's add in the URL， so we'll say add to and2。Trivial。

 so pretty easy to actually build these kind of standalone high performance URLls using the rust framework here with cargo Lambda。

 And you can see the code is actually not too bad to build from scratch course。

 you can always use third party libraries， but really rust is a viable option for modern rest based serverless applications。



![](img/bdff9c974944582e8c2032c51571a158_8.png)