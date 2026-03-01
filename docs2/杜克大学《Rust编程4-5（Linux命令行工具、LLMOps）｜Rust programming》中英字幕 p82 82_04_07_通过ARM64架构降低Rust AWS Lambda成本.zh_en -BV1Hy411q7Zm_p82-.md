# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p82 82_04_07_通过ARM64架构降低Rust AWS Lambda成本.zh_en -BV1Hy411q7Zm_p82-

![](img/92f6e6d30a832e59bd05047bc86e875e_0.png)

There are four drivers of AWS Lambda cost that support using the rust runtime。

 obviously the less you use it， the less you'll be able to be charged like invocation count also execution time here's where rust computational performance is amazing because you're going to benefit from that 10 to1 thousand times performance benefit。

 and then the memory allocation right because Lambda charges you by memory because rust can use up to 7 times less memory on average scenario。

 you could have a lower runtime and save money that way。

 also concurrency because you can use safe true threads。

 but even beyond that also armbased instances are cheaper by 34% on average。

 and this could be significant cost savings for compute intensive applications。

 also in terms of energy efficiency if your organization has goals around energy efficiency。

 these types。Prosors consume less power than X86。 and so this can translate into meeting those green goals。

 and then in terms of optimized performance， rust has low level control and efficient memory management。

 and you can leverage this。To specifically build something for the arm architecture to create a highly optimized and performant application。

 And this could lead you to have even further reduced execution time because the cost of Lada already is you know。

 very inexpensive。 but you're being charged by execution time。

 And now in terms of scalability when you combine all this together。

 This could be especially beneficial for variable workloads because of that significant value that you're getting。

 And finally， the support for Ar 64 architectures。 AWs does offer specific instances that are optimized like the graviton2 processor and by targeting this and rust a developer could take full advantage of the hardware capabilities。

 even further improving the cost efficiency。 So there are many drivers that are just you know。

 inherent to a rust language that make it the ideal language for serverless。

 But then if you go into the arm scenario here， really。

It's a very tough situation to argue against Ru being the default choice for serverless。 Again。

 if there's other things you're solving， like， for example， data visualization or looking at an API。

 etc cetera。 there's advantages to you to using scripting languages。 but for serverless。

 this is really the sweet spot for language like rust。



![](img/92f6e6d30a832e59bd05047bc86e875e_2.png)