# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p06 P6 Threads On Multicore Systems -BV19h48zoEeB_p6-

This video was sponsored by Brilliant。

![](img/29276d8c84dab9d0ec6928d5f6b6a416_1.png)

In the previous episode we started talking about threads and it seems you guys loved it Today we're continuing that discussion。

 focusing specifically on the role of threads in systems with multicore processors。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_3.png)

![](img/29276d8c84dab9d0ec6928d5f6b6a416_4.png)

![](img/29276d8c84dab9d0ec6928d5f6b6a416_5.png)

Hi friends， my name is George， and this is Core Ded。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_7.png)

Before we dive in， just a quick announcement， my friends over at Codecrafters are giving away a free lifetime subscription。

 more details at the end of the video。

![](img/29276d8c84dab9d0ec6928d5f6b6a416_9.png)

All right， let's get started once again， an important concept we need to know in advance is concurrency。

When we have multiple processes but only a single CPU。

 the operating system can make it feel like all those processes are running simultaneously by alternating CPU access between them at incredible speed。

In the last episode， we learned about threads， which are very useful when writing programs for two key reasons。

 if one task in the same program takes a long time to complete。

 and another takes only a few milliseconds， concurrency ensures the shorter task doesn't have to wait a long time to start running。

If a task is waiting for an IO resource， such as a file read or a network response。

 it can't use the CPU during that time。Instead of letting the CPU sit idle。

 the operating system can allocate that unused time to another task that's ready to run。

So threads are simply a way to tell the operating system that multiple tasks within the same process can run concurrently。

 they enable applications to perform multiple tasks at the same time。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_11.png)

For example， in an email client app。We need to display the user interface on the screen。

While listening for the user keystrokes， while uploading an attachment。

 like a photo from your file system。While performing grammar checking。

While monitoring for incoming emails。In order to provide a good user experience。

 none of these tasks should wait to each other to complete implementingplement concurrency has some challenges though。

 if the number of concurrent tasks increases too much， at some point。

 the system won't feel smooth anymore。

![](img/29276d8c84dab9d0ec6928d5f6b6a416_13.png)

Even if the CPU alternates between tasks extremely quickly。

 there comes a point where there are so many tasks that it takes too long for each one to regain access to the CPU。

To address this， there are three possible solutions。

The most obvious would be to simply make the CPU faster。

If the CPU can handle more work in the same amount of time。

 tasks can regain access to it more quickly， this solution though isn't perfect。

 because if we keep increasing the number of tasks， we'll eventually end up back where we started。

 too many tasks causing delays。Plus， making CPUs faster has become increasingly difficult over the last decade。

The second solution would be to schedule CPU access in a more clever way。

 this is a more complicated solution that deserves its own video。And the third solution。

 like the first one， is a more like brute force approach。

If a single processor can't handle too many tasks， no matter how fast it is。

 just add more processors。This can be achieved in several ways。

By adding more CPU sockets to the same motherboard， allowing for multiple physical CPUs。

Or by including multiple processing units within a single package or chip。

 known as multicore processors。And though less common， by combining both。

 multiple multi core chips in the same motherboard。

The terminology around processors can get a bit ambiguous；

 the termCU is often used to refer to the entire package or chip； however。

 each core inside the package works as an independent processing unit。

 essentially a CPUU that shares some components like the cache with other cores。In any case。

 each core appears as a separate processor to the operating system。

 so if you heard the term cores a lot in this video， you know what I mean。And before continuing。

 a quick message from Brilliant， one thing many of you agree on is that traditional studying can be boring。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_15.png)

![](img/29276d8c84dab9d0ec6928d5f6b6a416_16.png)

Fortunately， with Bri， learning new things and developing new skills doesn't have to mean endlessly reading PDFs。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_18.png)

Brilliant is designed to offer small lessons that you can engage with whenever you find the time。

 making learning a little each day both enjoyable and convenient。

One of the best brilliant features is the interactive nature of their lessons。

 which encourage critical thinking skills through problem solving activities。

This can help you a lot if you want to become a better problem solver。

 which is what distinguishes good from average developers。Its latest course， thinkinging and Code。

 lays down the foundational principles of coding， enabling you to adopt the mindset of a programmer。

And you can pick other topics such as App Python and C coding you can get for free 30 days of brilliant premium and a lifetime 20% discount when subscribing by accessing brilliant。

org/coDed or by using the link in the description below。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_20.png)

Remember you can also support me by liking this video， it is free。

Consider an application with eight threads。On a system with a single computing core。

 concurrency merely means that the execution of the threads will be interleaved over time。

 because the processing core is capable of executing only one thread at a time。

But on a system with multiple cores， concurrency takes on a new meaning。Here。

 some threads can truly run at the same time， because the system can assign each thread to a separate core。

In other words， with multiple cores， we're no longer just dealing with concurrency。

 we're dealing with parallelism。Notice the distinction between concurrency and parallelism in this discussion。

A concurrent system supports more than one task by allowing all the tasks to make some progress。

In contrast， a parallel system can perform more than one task truly simultaneously。

 thus it is possible to have concurrency without parallelism。

One of the main advantages in parallel systems is that the smoothness of multitasking becomes less reliant on the illusion created by fast interleaving。

And suddenly now it makes even more sense why virtually all modern operating systems consider threads rather than processes as the basic unit of execution。

With multi corere processors now the standard， threads within the same process can take full advantage of parallelism。

For us as programmers， this means that if we want to run tasks in parallel。

 all we need to do is declare those tasks as concurrent using threads。

The operating system will handle the rest， interleaving the CPU between threads if no additional core is available。

 or assigning one core to each thread if the system runs in a multicore processor。

This makes our programs more portable since we don't have to compile for a specific number of cores。

Just always consider two important things The number of cores is fixed。

 so creating a thousand0 threads doesn't mean that a thousand0 tasks will run in parallel instead。

 if the system has N cores， up to end threads can execute in parallel at any given time。

And pay attention to this up to N。Because threads compete for resources。

Even if we create the exact number of threads as the number of cores available。

 threads from other processes also need CPU time。Since one of the main goals of the operating system is to ensure fair distribution of CPU resources across all threads。

 it limits how many of our own threads can run in parallel。With that being said。

 let's discuss another reason why we might need parallelism in our programs。Performance。

This one is pretty obvious if we can truly run more than one task at the same time。

 we can significantly reduce the total time it would take to complete those tasks compared to running them sequentially on a single core system。

In general， there are two types of parallelism， data parallelism， and task parallelism。

Data parallelism focuses on distributing subsets of the same data across multiple computing cores and performing the same operation on each core。

Task parallelism involves distributing not data， but tasks or threads across multiple computing cores；

 In other words， each thread is performing a unique operation。But here we have multiple scenarios。

 different threads may be operating on the same data， or they may be operating on different data。

My plan for this video was to show you some cool programming examples of parallelism in action。

 but well， I messed up my computer， so we'll save that for the next episode。

Before we wrap up this episode though， let's at least look at some animated examples of parallelism。

Let's say we have a large data set of numbers stored in an array。

 and our task is to find all the prime numbers in that array。

This problem requires us to iterate over the entire array， checking whether each number is prime。

The key here is to understand that the result of checking whether a number is prime doesn't depend on the results for any other numbers in the array。

If we want to check whether the last number in the array is prime。

 we don't need to wait for the earlier numbers to be checked。

 each number can be processed independently。Now， if we have a four corere processor。

 we can split the data into four equal parts and assign each part to a different core。

This is an example of data parallelism because all cores are performing the same operation on distributed subsets of the data。

However， keep in mind that splitting the work across four cores doesn't necessarily mean we'll get four times the performance。

For example， I tested the same example in my computer over 10 million times。

 and here's the average time it took to compute each subset。

How much performance gain we can achieve from parallel operations is beyond the scope of this video。

But I'd love to hear your thoughts on this， so your comments are welcome。

 the most upvoted comment will win a free lifetime subscription to Codecrafters this Christmas。

Now let's tweak the problem， say we're given the same data set。

 but this time we're tasked with finding the lowest value in the array， finding the highest value。

 calculating the arithmetic mean of all the elements。

 and checking if the array contains the number 101。In this case。

 it doesn't make sense to split the data into subsets because each of these operations requires access to the entire data set to compute their results。

But here's what we can do assign each operation to a different core This is an example of task parallelism。

 different threads working with the same data set but performing different operations。Again。

 using four cores doesn't mean the process will be four times faster。

 but it's still a significant improvement。On a single core system。

 we'd have to perform these four operations one after the other with four cores。

 we can execute them simultaneously， reducing the total time。

And that's about it for now there's more content about threads coming soon。

 so make sure to subscribe because you don't want to miss it。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_22.png)

Don't forget to leave a comment for a chance to win a free lifetime subscription to Codecrafters For those who aren't familiar。

 Code Crers offers challenge based courses where you can build tools like Git， SQL， HTTP servers。

 and even interpreters from scratch using the programming language of your choice I'll leave a link in the description if you'd like to support me by subscribing。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_24.png)

![](img/29276d8c84dab9d0ec6928d5f6b6a416_25.png)

![](img/29276d8c84dab9d0ec6928d5f6b6a416_26.png)

If you enjoyed this video or learn something， please hit the like button。

 it is free and that would help me a lot see you in the next one。



![](img/29276d8c84dab9d0ec6928d5f6b6a416_28.png)