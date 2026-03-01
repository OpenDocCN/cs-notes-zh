# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p71 71_04_05_Cargo Lambda工具入门.zh_en -BV1Hy411q7Zm_p71-

![](img/ced5c79d379b804e79c22e04eaebf13c_0.png)

Here are four drivers of EWS Lambda cost that support the rust runtime。 First up here。

 we have invocation count。 You're charged by how many times you're invoking a lambda。

 So essentially every time it gets called you're going to pay some cost here。

 So a Lada function is a function that can quickly add up。

 And so if you're using lots of applications and building things with lots of invocations。

 you're going to need to monitor and optimize those triggers to make sure that they're actually successful。

 and the second driver here is execution time。 So the execution time is how long it will take to process an event here。

 now this is where computational speed is really critical because if you can do things in milliseconds and you get in the case of rust over Python there's many scenarios like。

 for example， the rough Lter could show us that you could do 10 to10 times performance over regular python based lintting。

 you can see。With other bits of code， there's going to be similar scenarios here that you could save。

 you know anywhere from 10 to 1000 times on execution time， so your build time。

 the other one that's really hard to get around here。

 no matter however you optimize your Python code with C， etc cetera。

 you can't get away from the fact that Python uses more memory。There are recent studies that show。

 you know around 70 times more memory is used by Python than rust。

 And so you're going to have to use a bigger allocation for the runtime。

 And that's how the pricing works with AW Lada。 So you're going pay more money because there's more money in terms of the memory allocation at place。

 You're just wasting let's say， a larger instance that can run with rust here。

 So when you configure a lambda function， you can set them out of memory available to the function。

 And this is going to implicitly allocate the CPU power， the network bandwidth， et cetera。

 So you're kind of limited by how memory inefficient Python is。 Now。

 the other one that's kind of a stealth one here that not a lot of people talk about is that。

Python doesn't support true threads。 And so one of the problems is that if you are using a lambda。

 let's say a large memory lambda that has four or six cores， etc ceter。

 they're going to sit their idol unless you do something fancy like use processes。

 which in turn also increase more memory。 So you're kind of stuck here between a rock on a hard space with this true threads here。

 but with rust， you can open up threads here， use， let's say you know the rayon library automatically handle a thread per core without doing much work at all。

 In fact， you can just work through an iteration and actually have a thread per iteration that hits a core。

 So there's really not much to do to be able to use fully the multico environment in lambda by using rust。

 so。When I hear people say that data engineering at scale works well with Python and serverless I think this is like saying you know chocolate cake can help you lose weight。

 it's true in theory if let's say you starved yourself for seven days in a row and then add one piece of chocolate cake。

 you could lose weight eating chocolate cake， but that's not really telling us the whole story here is that rust is just orders of magnitude more efficient than Python for serverless and it's up to you to really figure out where you can put this in your workflow and you can really save a lot of money by using the rest runtime。



![](img/ced5c79d379b804e79c22e04eaebf13c_2.png)