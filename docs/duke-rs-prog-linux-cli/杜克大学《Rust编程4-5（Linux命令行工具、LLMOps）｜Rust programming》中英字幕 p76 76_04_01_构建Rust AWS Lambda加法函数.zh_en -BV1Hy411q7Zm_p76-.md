# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p76 76_04_01_构建Rust AWS Lambda加法函数.zh_en -BV1Hy411q7Zm_p76-

![](img/9a007a188776fe47bb28b079d514565e_0.png)

Here is an architecture for a very simple series of Lambda functions that are going to eventually be wrapped together in a step function。

 But first， I'm going to start with rust。 I'm going to build this addd function here。

 So really simple。 it takes an x takes a y and returns back a total。

 the reason I like rust is that it's probably the simplest possible way to make costeff Lambda invocation。

 So let's go ahead and see what I mean。 Here we have a Aws Lada project。

 and the way I was able to create this was by using the cargo Lambda tool。

 So you can see here if you just type in cargo Lada。 it gives you a bunch of options here。

 including new。 and this is the new project that I created。

 Now let's look at the tree structure here。 So really all we have here is a main dors and a cargo file。

 the cargo file that's created is all populated with what you need。 So serialization。

 a synchronous coding tracing the runtime。 it's all set up for you。 Now。



![](img/9a007a188776fe47bb28b079d514565e_2.png)

To use the Lambda here， I did put a little bit of logic inside of this Lada function。

 Let's go ahead and walk through what it does。 So first up。

 I put a comment that says we're building a simple addd function。

 So this is intentionally trivial so that I can explain how rust Lambda works。Now。

 notice here that this struct here。 this is gonna to be the request that comes in。

 So this is an x and a Y。 And so all we need to do is to find that right here in this derived section。

 Next up， I have the response。 So this is what I'm going to return back when I'm done。

 So you can think of x plus Y it will be a total and then finally in terms of the main piece of logic。

 we have an async rust function here。 So really not a lot going on in this function other than the word async。

 which allows us to use the Tokyo library for async communication and then also we have the function handler here as well which is going to do all the work inside it takes this lambda request and returns back a result object。

 So this doesn't look that much different than a scripting language at this point we have the payload that is parsed outside of this。

 And so again， this payload here we can see it's coming from right here。 This is the request。

And then we add the numbers together。 So we have let total x plus y。

 And then to return back the response， we just say let response and then pass in that total so that it's returned back。

 And then here we go。 We have an O wrapped into the response。 So this is the result response error。

Now， the only thing left is to wire it all together via this main handler。 In fact。

 you don't have to do anything。 It's already set up for you。

 All it's going to do is call that function handler， which， again， is defined right here。

 So in order to use this is' actually pretty easy if you do a few tricks。

 one of the things I like to do is create a make file。

And the reason I like to create a make fileile is that I just don't want to think。

 I just want to build things very quickly， and so one of the ways that you can develop locally is by doing the cargo Lambda watch command。

 so I just type in make watch。And what happen is this will run and let me。

 you know do whatever I need to locally。 Now， if I click on this split terminal here。

 we can actually play around with it a little bit more and actually run this invoke。

 So this is very different than let's say scripting language like Python because you have to use Docker and get all kinds of setup up going on。

 there's actually nothing to do because this is actually all set up for you without installing thirdpart tools。

 Now， if I want to go through and I type in make invoke。This will actually call my local binary。

 There we go。 You can see exactly what's happening。 I'm passing in an X of Y。

 So we already know that it works not much more to do。

 So really the next step then would be to stop this and actually build it so we can deploy it。

 So how do we do this again， cargo Lambda build release。 Now， one trick here， though。

 is that if you're just using you know， kind of basic rust code and you're fairly certain that it doesn't do anything tricky using arm 64 could be a great option because you're going to be build at a much lower rate。

 So I'm actually going to build the cheapest cheapest possible Lambda here。

 So I'm just going to type in make build。 There we go。 Now。

 once I've built this to deploy it's trivial again。

 I go cargo Lambda deploy and I can even pass on the region if I want to so we can just say make deploy。

😊，And it's trivial to do the deploy again because of this really tiny binary。Now。

 it gets even better because I can even invoke it remote without doing anything。

 So I'm going to go ahead and kill this other terminal here。 So there's more room。

 Let's go ahead and kill this。Now check this out。 All I have to do is say cargo Lada invoke just like I did before。

 but do dash remote name of the function， and that's it。

 So let's go ahead and do that and we can just say make AWS invoke。There we go。

 Now you might be saying to yourself， oh， well， are we sure this is working。

 Let's go ahead and check this out。 Let's double check that we're actually calling our deployed function here。

 That's always a good idea。 If we go down here， we can do that by looking it monitor。

 That's one of the easier ways to take a look at it。

 is we can just look at the recent invocations here。 And in fact， we just saw one。

 the duration is in milliseconds point89 milliseconds right pretty fast。

 And we can see actually everything about it。 so we can see that the duration was again。

 less than 1 millisecond， which is ridiculous。 And in fact， the memory size that was allocated。 Now。

 if we want to actually test it in the console， that's another great way to do it。 And we go here。

 notice I created an event here in X and Y。 And so all we have to do at this point is go back to the test section。

😊。

![](img/9a007a188776fe47bb28b079d514565e_4.png)

Click this button and we can see， in fact， it also returns back the result。 And again。

 the duration is very， very tiny。 I mean 1。37 milliseconds。

 and we can see that the build duration was 2 milliseconds。

 And this is one of the advantages as well of rust over languages like Python。

 which have 70 x more memory usage by default is that it only uses 15 meby。 Now。

 why do we care about this We care about this because your build by memory usage。

 So the default configuration allows you to do many operations and rust that are really not possible at that cost profile。

 And that's really one of the advantages of using rust for building AWS Lambda functions。



![](img/9a007a188776fe47bb28b079d514565e_6.png)