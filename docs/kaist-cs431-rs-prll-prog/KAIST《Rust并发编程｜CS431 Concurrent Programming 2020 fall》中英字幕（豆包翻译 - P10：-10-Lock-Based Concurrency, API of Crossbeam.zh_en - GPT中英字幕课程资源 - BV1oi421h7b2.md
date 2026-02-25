# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P10：-10-Lock-Based Concurrency, API of Crossbeam.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

As the final lecture for Ro concurrency libraries， we're going to study CrossBm。

 which is concurrency libraries in rust that is widely used in many programs written in rustT。

 for example， it is deployed to Firefox。I am one of the maintainer of this cross beam and so I contributed the implementation of many of those libraries and so this part of the reason why we study the cross beam here。

 I know internal details to the cross beamm。So first API we want to use is what is called ScptT。

Recall that in Rusk standard library， the Strsp function requires that the function F here and the return type should be statically scpt。

That means that you should be able to move the data to the end of the program。

But it is sometimes a very much， too much constraint。So we want to， for example。

 declare our stack variable and share it it with multiple strip。

The standard library standard library thread doesn't allow that because the function type and the return type should be statically scopeed。

On the other end， this cross beam sculpt thread relaxes the constraint and allows a principled sharing of scopept variables。

So example is easier to learn the thing， so in this example that is copy and pasted from the crosspi documentation。

 it is creating a string that is written the hello word。😊，This is called a greeting。

And greeting is shared with two stress。 Two stress are sped here。

And each thread is immutably borrowing the greeting variable。

 and it is just writing it to the screen。So let's execute it and the two threads are writing or printing the greetings here。

So first good， but it was impossible using the standard library's threadpon function。

 the reason is that the function here and here should be statically scopeptd in standard library Strpon function。

And as a result， you cannot pass the reference to the stack variable。

So in order to pass the stack variables reference， which is not statically scopepted。

 but scopeed within the main function， then the scope stretch should be used。Why is it safe。

 the reason is that the scope is first defined before spawning stress。

And the scope S is defined here， and then the thread bond。

It is guaranteed that by implementation of this Scpt thread at the end of this Co thread here。

 then the all thrust that has been spawned inside this sc thread should be joined。And as a result。

 at this point of time， there is no longer a reference to2。The greetings variable。

So that's the reason why this gring can be shared among multiple stress because it is guaranteed that all the threads are guaranteed to be exited before gring can be dropped。

That's precisely the reason why the send library threadpo require that the stoscope gridding can be dropped before the thread has used it。

 but it is not the case in Scul thread because the threads must exit before grdings are dropped here。

So test one of the motivation of the scope thread， and it can be very much useful when you want to just sponsor stress and wait for them and share some data across multiple stress。

That sharing is usually very much difficult to do so in CN+ plus because the sharing when you have a tiny misconception of the lifetime and scope。

 then your program will become buggy， and you will have a very difficult to find box in your program。

However， in rust， the ScSt API has a safe API only。

 and that's precisely the reason why we can do this。

 we can share data across multiple stress in a principled way without worrying about the possible unsafe behaviors。

So far the good。And the next API， we want to discuss is what is called cache padd。In。

 in concurrent library， it is very much common to。

![](img/e61a870fba74ab9874f512daac5530a0_1.png)

Com on to。

![](img/e61a870fba74ab9874f512daac5530a0_3.png)

Do false sharing。For sharing is that suppose that there are three agents， P1， P2 P3。

Here P should probably mean processor， but let's say they are stress。 there are threat one。

 right two， stress3。And they are accessing their own data。 So it is accessing。 it is the same thing。

 but it is cached into each CPU。And the P1 is accessing the first data， P2 accessing the second data。

 P3 accessing the third data。They are accessing the same cache line， but with different index。

 so they are accessing different locations， but with the same cache line。

The problem is that if the the P2 write some value to here， then。

What is happening here is that it should invalidate the other thread cache lines because they all share the same cacheline。

 so if P2 is writing a value to this cacheline， then the others cache line should be invalidd。😊。

Thats the reason why the cache topic is happening here。But it can be detrimental to the performance。

 because even though multiple stresss are accessing their own data without any sharing。

 we hope that the stress doesn't interfere with each other and get the full performance。😊。

But because the data is put in a single cache line， the the。

 the the right to the one cache line is affecting the others。

 They should invalidate the others cache lines。 Itll be。Very much detrimental to the performance。

Even though I am not reading from and writing to the other data， my cacheline is evicted。

So this is basically what is called false sharing。 They are not too sharing because they are accessing different data。

But they are still false sharing because they are sharing the same cacheline。

So the moral of the story is that when you are doing concurrent programming。

Then you should guarantee that multiple stress are accessing different cache lines。

 So that is the moral of the story。And this cachepa is allows you to do so very easily。

 So this is basically padding data， underlyingline data T with cacheline boundaries。😊。

If the underlying data T is 8 bytes， then cache pad will be 64 bytes or 128 bytes depending on the architecture。

So it is basically padding zeros around this type T to make it multiple of the size of the cacheline。

So as a result， this can be used to。ItRe data for Con data searchers。

 and it is guaranteed that multiple locations are not falsely shared。So， for example。

We are going to learn Q at the later stage of this course and Q has two pointers basically two pointer one pointer is2 hat of the Q and the other pointer is the tail of the Q。

And they should be concurrently accessed， it is the motivation of the concurrency of the queue。

Push and pop side are conquered， and they should be somehow conedly accessed。

But if they are put in a single cache line， then it will be attributabletrimental to performance because all the operations on the head and all the operations on the should be interfering with each other we want to avoid that That's the reason why we cachepaed the head pointer and tail pointer on their own and now the cache liness are different and the operations are not interfered with each other。

😊，So that's basically the， the motivation of cache padit。 And it is very easy to use。

 And please memorize the this picture。😊，What is the meaning of for sharing and when for sharing is。

Suspected， then please use hashpait。 It's very much each to use。And the final API， we want to。

Sty is what is called channel。We already saw a little bit about channel。

 So channel is already in standard library。It is MPC channel that means it has multiple producer and single consumer。

MP means that multiple stress can push the data to the channel at the same time。

That's the reason why it this multiple producer of the data。On the other end。

 it has a single consumer， which means that only one thread can pop the data from the channel at one time。

Only one single consumer。 That the reason why it is called MPC。

Now you can imagine that there are SPPSC， SPMC， and PMC。

I is multiple or a single producer or a consumer。And this cross beam channel is MPMC。

 which means that it is multi producer， multi consumer。 So it is the most general form of channel。

MipConers and multiple producers are at play at the same time。

So you can create it by calling what is called unbounded。

 which will create an unbounded channel with unbounded capacity。

 you can put as many as possible data into the channel。As far as your D has the capacity。

There are also bounded channel which has a bounded number of messages。

 and when you want to put data into this bounded channel and it is full。

 then it is going to return error。So there are the API usage， but。It is very much simple。

 just multiple stress can have a producer or consumer。 I mean。

 they can have a sender or receiver or transmitter or receiver and they can have multiple senders as well。

 and they can just send data。And it is just acting like a channel。Like in go or Python。

So it is very much easy to use， but the internal implementation will be a little bit difficult。 So I。

 I will。Explain the internal implementations at the later stage of this course。At this point of time。

 just look at the code and see， oh， it is not very much difficult to。Understand。Okay， so far so good。

And there are， basically， the。The API is very much easy to use， so please read the documentation。😊。

And what is quite interesting about channel is that it provides a macro that is named select that is trying to receive or send from multiple multiple channels basically。

 so if it is it wants to receive from multiple channels， then you are going to use this select。😊。

When you are receiving a data from this R1， which is this unbounded channel。

 then you are going to do this and when you are receiving a message from R2。

 then you are going to execute this。It is doing this at It is trying to receive a message from multiple channels。

 basically at the same time。It is much more efficient than looping over all the channels at the same time。

 so it is basically an optimization for working with multiple channels。So in， for example。

 in the implementation of actors or other kinds of libraries， then this feature。

 the select feature of the channel will be very much useful。

 so we will discuss this aspect at the later stage of this course。

So this concludes our discussion on the lock based APIs， lock based concurreencies APIs。

 So please look at the all the definitions of the structure that we have。😊，Learned so far。

 and please read the documentation。So usually the rust concur libraries are well documented and they explains the things very clearly a lot。

 so please read the documentation and try to learn something from these documentations。😊。

If you have any questions， please read the documentation and then ask the questions in the issue tracker so that we can answer your questions。



![](img/e61a870fba74ab9874f512daac5530a0_5.png)