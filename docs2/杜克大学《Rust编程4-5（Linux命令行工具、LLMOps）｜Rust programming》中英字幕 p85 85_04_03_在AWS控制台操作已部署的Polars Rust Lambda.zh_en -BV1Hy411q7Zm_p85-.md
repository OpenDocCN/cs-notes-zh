# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p85 85_04_03_在AWS控制台操作已部署的Polars Rust Lambda.zh_en -BV1Hy411q7Zm_p85-

![](img/3fd1b2a1270dd5be675948126ca35ae5_0.png)

Here is the AWS Lambda console， which allows me to look at different metrics that are available and dive into insights from a deployed Lada function。

 In this case， I'm using rust and I'm using cargo Lambda to deploy this。

 And I'm going to go ahead and look at the modified section。 So oh， look at this。

 I've got a polar's Lada function that has been recently deployed。 If we go ahead and look at it。

 I can see more information about what's happening。 So does it go to a destination。 For example。

 does it have a trigger。 a lot of times when you're building highper code with rust getting a trigger is a great way to build out a large scale data engineering pipeline because of the fact that rust is so performant and it works really well with these other services。

 Now， some of the things that you can do as a trigger would be a load balance or a cloud front。

 you could batchbook data， you could pull things in from S3 S Sqs tons of great triggers for a rust。

😊，Lambda function Now， in terms of the code here， because this is deployed as a binary。

 we don't really do anything with it。 But what we can do is we can actually test it。

 So how would we test it out In this case， I know that the payload that I'm going to send in is going to have a keyword filter and it's going to have the number 5。

 So if I format this and I go ahead and I say test we can actually see the execution perfect。 Now。

 in this case， what's interesting about this is that you can see here that it took 34。

Milliseconds to initialize here。 and then the initial build duration was 1387 milliseconds。

 If I go ahead and I run this thing again， if I go back to test here and I test again。

 the next one is going to be a lot faster。 So you can see here that the duration here is6 milliseconds。

 So really we're getting some incredible response time from this lambda great performance and in fact。

 we can dive into the details like the duration， the build duration。

 the memory size and the max memory sized used。 now one of the things that is very important to point out here about rust and why it's so unique is that you're charged with Aw lambda by the amount of memory allocated to the default instance。

 So if you needed more memory because you're using a scripting language like Python or rubby then you're going to be charged more in the case of rust。

 look at this， it's way under value。 even though I'm doing some reasonably heavy operations with rust。

includinging data frames， etc。 So this is one key insight to pay attention to when you've got your Lada deployed。

 Now we can also go to monitoring and we can take a look at things like the logs and see how many invocations happen recently。

 were were the most expensive invocations we can also go into the metrics and look at for example。

 you know how long were Lada taking， this is often a very good idea to take a look at this and then how many times it's been called and then were there any errors or other things。

 And you can really dive right into tons and tons of details here and really dig into the details。

 so how would we actually invoke this and play around with it if we go back to the console here since this is already running。

 All I would have to do is just type in。

![](img/3fd1b2a1270dd5be675948126ca35ae5_2.png)

Make AWS invoke again。And this would invoke it one more time， and we could even invoke it， you know。

 several times， right， just to test it out。

![](img/3fd1b2a1270dd5be675948126ca35ae5_4.png)

We can see it's getting really good performance here。 and then if we go back to this。

 we can actually take a look at， in fact， the last invocations here and we would be able to refresh it and see lots of different run。

 So a great way to actually play around with the details even dive into the log stream itself is to have that feedback loop when you're initially developing and you can obviously put more logs inside of here as well to get more insights into what's happening。

 but rest really is a kind of go to first language that I would recommend for people doing high performance data engineering。

 MLlase or cloud computing because of the performance and memory usage which is something your charge for when you're using AW Lambda Now one other configuration thing that I'll mention if we go to configuration here if we look at the general configuration as well。

 you can also configure the snapshot snapstar which can help you you can configure e femoal storage and in our particular。



![](img/3fd1b2a1270dd5be675948126ca35ae5_6.png)

Another thing to be aware of is that you also can target the arm runtime and what's nice about arm is you can save 34% or more so already you're saving tons of money by using rust。

 but when you dive into arm， you saving more。

![](img/3fd1b2a1270dd5be675948126ca35ae5_8.png)