# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P5：-05-Homework 1_ Parallel Web Server.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video， I'd like to introduce the Homeop 1， which is about implementing a parallel web server。

So in the homeworkmark directory， you can run the server using this cargo run hellello server。

You need to implement a few components of the server in order to get it done。

 but this is the completed homework and this is the expected outcome of your homework one So when you start a server it prints some log。

And when you go to the web browser， and then go to the。Address， local host column 7878。

 then it will print an error message。 but if you're going to go to， for example， L。Here。

 then it will wait for a few seconds， and then after computing an expensive computation。

 it will return。A page， but you can see that there is a delay。

 there is a delay between the request and response， so because there is an expensive computation。

But the result is now cacheed。 so if you refresh， then it will return the page immediately。For Alice。

But if now it is asking a page for Bob， it will again compute an expensive computation and it wait for a for a few seconds。

But now the result is cacheed， so you can refresh it and the result will be immediately returned。

So this is basically such a web server and this is basically printing some log。

 though the log is not important， but at the end of the execution you may want to exit the web server by pressing controversy then it should return I mean it should write down some statistics that says there is a。

Viidgeit it is a visitge count basically the above page is visited five times and an error page is visited four times and L page is visited at seven times。

 so basically when control C is pressed， you need to print out the statistics of the accesses。

So this is the specification of the web server。And in order to do so。

 we already provided a significant amount of skeleton code。And let's look at the code a little bit。

And this is the thumb level as file that is actually implementing the server here。

And you are going to first in， in this main function， you are creating a straight pool。

 The straight pool is basically a。A set of stresss， and if you want to execute the job。

 then you are going to store the job to the thread pool and the start pool will automatically select the thread and execute the job。

And if the job is finished， the thread is returned to the red pool so that it can be used to execute another job。

And here we are creating a thread pool of size 7。Now we are creating some channels that is needed to transfer a job to the next thread。

And also， we are creating a discipline listener to that address address of local host Col 7878。And。

This is Mar cancelable in a way that if this discipline listener is canceled。

 then even though there is remaining connections， it is going to be dropped basically。Okay。

 and when controlr C is pressed， it is going to order to cancel the listener。 That is basically the。

What's going on behind when you press Cont C， when you press Cont C。

 the discipline listener is canceled and as a result that the every resource is cleaned up from there。

And there's a listener。Reer is this thread， and it is going to listen to the discipline listener that is created here。

And for its connection， in cominging connection， it is going to。啊。

It is going to execute the job using the， the threat pool that is created at the beginning of the execution。

 and it is doing this， it is first creating a handler here。And actually handle the connection here。

And get the report。 And you're going to ascend the report to the what is called a report the reporter。

 basically。 And the there's a channel between a listener and a reporter。 I mean， I mean the。

The handler and and the reporter。 And this is the handle for the channel you are going to send from a handler。

Your handle us send the report to the reporter。And there's a reporter， as I said。

 it is also a thread and it is collecting the statistics。And when there's no longer reports。

 that means that the server is terminated then。And then it is going to calculate the statistics and then going the statistic goes to the main thread and main receives the statistics and print out。

This is basically what's going on in this code， there are many threads， many kinds of thread。

 listeners and workers and reporter and the main thread。

 and they are collaborating to deliver concurrency in handling the web。We server。

So because there are parallel resources， parallel Thrs， it is truly parallel web server。

And these threads， for example， listener threads and worker as a reporter and the main threads are communicating with each other using channels and the channel is imported from the cross beam crate。

There's unbounding channels and bounding channels， and they are used appropriately。

And this is already provided。 It is also it is in the skeleton code。

 so you don't need to implement the server on your own。

 but you need to implement some components of the server。

 specifically I want you to implement the extract pool。And the the。Cance 오 TCP handler。And the。

The cache that is used for storing the result of expensive computation during the handler。

So let me show you the skeleton code， so let me begin with the cache。

The cash is basically a key value store， and it only provides one function， get or insert if。

So you're basically quarrying this cache key values store with a key here。

And you have to implement it in such a way that if you already have the value for the key。

 the key should be immediately returned。Otherwise， you execute this function。

And add the results of the function to the cache。And then return the result of the function。

This function may be very expensive。 That's the reason why it is cash in particular it can spend seconds。

So， so it is beneficial to store these are the value of the result of this computation in the in the。

Inだ。

![](img/b6f8ccaa151fe9cfd7a1b22799dc5cf0_1.png)

佢。In the cash， basically。Okay， so far so good。And you need to also implement the TP listener that is cancelable。

So there is already a typical listener that is implemented in the standard Library of Ru and you need to use it。

Inside your castleable disciplined listener。And it provides the API。

 the same API with the underlying discipline listener， but in addition to that。

 you need to implement cancel。Cancel is a function that cancels the discipline listener。

So the bind function is simple。 It is binding to an address as the underlying Dis listener。

And what is interesting here is that it's canceled is initialized with the false。

And here you need to cancel， implement the cancel function。Cancel is basically setting up。

 the is cancel variable。And to do so you need to call the API of this atomic pool and as I said in this code here。

 write it you can just call this tour function with release ordering。

But it's not the end of the story after you set up the cancel bit here。

You need to somehow notify the CC listener that you are quitting， you are canceling。

 you are accepting。And you need to do such a thing。

 you need to basically wake up the T listener that may be blocked。

And you need to implement that in this cancel function。Okay， that is the second homework。 And。

 as and further， in the next function， you need to。

Implement the next function that is basically returning the next participant stream。

 the next connection。So what is particularly interesting about this is that if the is canceled is true。

 you need to just return on， which means that your stream is ended。There's no longer connection。

 because it is cancelled。So if it is not the case， you just return the next stream of the underlying discipline listener。

This is basically what we want you to do。And again。

I said that here you need to set is canceled with what is called release ordering and here you need to insert you need to write the I mean you need to read from this is canceled using acquire ordering。

 so the precise meaning of this release acquire will will be discussed in later classes later sessions of this class。

 but just memorize and use release at this stage。And the last thing you should implement your thread pool。

 threat pool is， as I said， a set of threat and a job can be executed inside threat pool。

And the API is like this， you can create the third pool and you can execute the job。

And you can wait for all the， all the。All the executing jobs to be finished。

 so that is basically the meaning of joining here。And you need to implement this using some channels again。

 So there is a channel between the Start pool and the workers。 and if you are executing a job。

 then you are going to insert the job into the channel。

And each worker is trying to get a job from the channel， and then execute it。Basically。

 that is the higher level idea of how to implement this rep pull。And in order to implement join。

 there will be the the there will be the this data this will be used。

 which is basically tracking the number of ongoing jobs。 and if the ongoing jobs。

 the number of ongoing jobs is0。 then you can the join can return。Immediately。

 the you need to implement the logic inside these functions。Fortunately。

 a lot of functions is already implemented in the Robook。

 The final project is also about implementing Tpool。

 and you can just copy and paste on many of the code from there。Okay。

 and if you implement the three components， cache， and Tpo。

 then all the other components are already prepared and you can run the server under the demo I already presented at the beginning of this video。

So and doing that is homework 1。

![](img/b6f8ccaa151fe9cfd7a1b22799dc5cf0_3.png)