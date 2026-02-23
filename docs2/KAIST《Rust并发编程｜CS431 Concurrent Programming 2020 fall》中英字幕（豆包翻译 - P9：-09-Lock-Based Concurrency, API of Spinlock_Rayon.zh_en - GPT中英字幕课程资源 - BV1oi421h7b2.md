# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P9：-09-Lock-Based Concurrency, API of Spinlock_Rayon.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video， we are going to study the spinn， which is implemented in this courses repository。

And the rayions paralleliteerator， which is the parallelism library on top built on top of other concurrency libraries。

 So in most cases， people want to use parallelism library because it abstract checks out all the concurrency details into libraries and I will show you how easy it is to use the rays parallelerator。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_1.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_2.png)

Okay， first things first。 let me first introduce a spin lock， which is in this reposory。

 the courseository。 and you can you can search for the log folder and source folder and then spin lock the R。

 It it defines the spin lock， which is trying to acquire a log in a spin loop。

 So that's the reason why it is called a spin lock。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_4.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_5.png)

Okay， spinla is just the boolean， but it is that the boolean can be accessed by multiple stress that is the only difference from the usual boolean to the spinx Boolean atomic booleion。

It is a bullion， and that bullion signifies the whether the luck is held or not。 So if it is true。

 then it is held by someone。It is false than it is not held by anyone。

 So it's the meaning of the booleion inside this a spinock。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_7.png)

And this default trade is the trait for the default value of a spin knock， and in this case。

 it is false because at the beginning of an execution， a spinag is not held by anyone。

 That's the reason why it is given false。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_9.png)

You can see the if you already read the book about rust， then you can immediately see the syntactic。

Component of this field lines that this is the default trait。

 which is defined in the standard library， which designates the default value of a type。

And this is a function that returns to default value and self in this context is same with the spin luck here。

 self is for referencing the each own type。It is creating a value of spin up。

 and the inner value becomes false in this case。So， first， the good。And。And in this block of code。

 we are going to define the lock operations of a spin lock。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_11.png)

So here a lock function is given。 and here a type talk。

Type token should be provided for regarding the spin as a log。

 token is basically a value that is returned by a lock function。

 lock function not only acquire the log， but returns as some receipt or proof that oh。

 this log is held。By you。The tokens serves as the role。 So for spinak。

 it is just a unique value which doesn't have any meaningful information。

 but for other kinds of locks， they will have other kinds of more more complicated tokens so。

In this case， for spin lock， you can safely ignore the contents of this token。

So let's just ignore that and let's look at the lock and unlock functions。

In lock functions we are going to define what is called backupoff and backupoff is basically a data structure that makes our lives easier to deal with a spin loopop in spin loopop it is discouraged to spin as fast as possible because when some conditions are not met or in particular the lock has not been acquired than it is likely that for a short period of time you are not going to acquire the lock again。

So if you didn't acquire a log， it's beneficial to just wait for a a few moments。

It is it will not be seconds， but it can be some mill seconds or microseconds。

 And this backup is exactly doing that when back of szey cold， it is just waiting for a few minutes。

 I mean， few moments。So it is it is also exponentially increasing the latency。 At the beginning。

 it is probably immediately return in the hope that the log is just temporarily held by others。

 but if you tried again and again and again and you cause news multiple times。 then it says that oh。

 I'm， its probably I'm not going to acquire the log soon。 So that's the reason why I'm going to。

Wait a little more， probably possibly yielding to other threats， the turn。Okay。

 so this is the the mechanism for exponentially back off in the spin loop， and this is the spin loop。

And here it is trying to atomically swap a false value into true。

The precise meaning of these all the things will be discussed in the later。

 but at this stage I' just memorize that lock is trying to atomically replace a false value into true。

And if it is successful， it is going to return。So it is very much okay because this function atomically replaces force into true。

 that means that the log is held by someone。And that that someone is me。

 I just replace it atomically。Un lock function is very much similar。

 It is just trying to store the false value into the store。So the meaning is that， oh。

 I finished accessing the internal data。 and so I released the log by storing the false value into the inner value。

So effectively， this will。This will signify the other thread that I the log is from now1 released by me。

 so it can be acquired by you。This function is marked as unsafe because this function signature not always guarantees the safe uses of API。

You， for example， you should not a knock a spinock that is not held by not not acquired by me。Also。

 do you have to give the token that is the same with the token that is returned by this slu function。

It is not guaranteed by the Ro API。It is the guarantee that you should， you should。Satif。

That's the reason why it is marked as unsafe。 The implementation is not 100% guaranteed to be safe。

Because it has a contract that the user of this API should satisfy。

 and namely the token given by thislu function should be given to the argument here as a token。

And yeah， this is basically the meaning of dis。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_13.png)

And there is other functions that is going to try to try to acquire a log instead of spin looping here。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_15.png)

But it is almost the same as above， so I will not explain it in details in this course。

The implementation of the meaning of the Comp swapb and what is the meaning of this acquire release will be discussed in later videos。

Okay， so first second， we studied the APIs of this spinn and。

And the reason why they should be marked as unsafe。And now， I'm going to。

Explain a higher level API of spino that removes the necessity of using unsafe marker here。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_17.png)

So this is the higher level API。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_19.png)

So it defines the trait a for which rose locks should satisfy。

 So here we are going to define a token type lock function， which is returning token， as is。

 as I explained， and the lock function。And as I explained。

 the lock functions is smart as unsafe here， and it is safe only if it is cultivate with a token given by the corresponding lu function。

So it is described here， it is not guaranteed by rust。

 but it is documented here and the user is expected to satisfy this safety condition。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_21.png)

Okay， so first so good。 and we are going to。We are going to。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_23.png)

Hesplain the higher level APIs benefits。 So recall that in the previous lecture。

 we discussed that lock has to satisfy two guarantees。

 The first one is that the lock and unlock should be matched。

Which is represented as here that the token that is returned by La function should be given to unlock function。

 and it is should be matched。 So that is represented in this API's safety guarantee。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_25.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_26.png)

Documentation。And the other part of the guarantee that users should satisfy is that the data that is protected by the spin lock should be associated with the lock that is protecting it。

 and these two aspects are dealt with in this higherleve API and these two aspects of guarantees or contracts are automatically satisfied when using these higherleve API。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_28.png)

So let me explain thestruct here which is consisting of log and data。

 as I explained the lock and data should be paired， they are the two sides of a single coin。

 so we need to put them into a singlestruct。Here I put an unsafe cell here I wrapped a T with this unsafe cell。

 and which means that it has an interimmability。That this is very much okay because it is actually having intermability when using a lock。

 you are going to access mutably access the inner data using only issue references。

 That's the reason why we need to put this T into unsafe cell which signifies that it is Interutable data。

😊，So it is only for rust in rust when you are going to define an interior mutualability。

 you are going to put the data into this unsafe cell， so just memorize it for now。

 but if you are interested in the technical details。

 please search for unsafe cell interior mutualability in Google。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_30.png)

This is the obligatory lines for marking the lock type as sandal sink。 So the the types T。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_32.png)

The underlying type T should be sendable because it is accessed by multiplepo thread。

 so it is at one time access by thread A， and then it is sent to threat B which acquires the log at the next time and it is going to access by C。

 therefore it should be sent to C as well， blah， blah， so T should be sendable。However。

 there is no need to for T to be seen， which means that there is no such a case that multiple stresss are accessing the data T at the same time。

It is guaranteed by the implementation of the spin lock or other logs， so in spin lock。

 when a thread acquires a log， then it is the only thread head that has acquired a log。

 so there is no way T can be accessed by the other threads。

That's the reason why it doesn't need to be sink。It is there is no concurrent accesses at the same time to the same data of T。

Furthermore， they are marked as unsafe because the guarantees， as I said。

 is they are guaranteed by the implementation of block。

It is not guaranteed by the automatically guaranteed by the worst type system。

 It is guaranteed by our own implementation that should be manually inspected。

That's the reason why this line should be marked as unsafe。 that signifies the fact that oh。

 I need to manually inspect that lock types are actually send and sync。Okay， so first second。

And we are going to。show the internal， internal the。Implementations of the logs。

When you create a lock using a row lock type， for example， a spin lock， using a data type T。

 then you are going to be given a data of type T， which is the initial value to be protected inside this lock。

And the luck will be the default value for spinak it should be a false。AndFurthermore。

 the data is also initialized， it is unsafe cell， and it is be given data。Okay。

 and you can destroy the lock and get their inner data T。This is the API that does that。

When you are given the total ownership of this log。

 then you can just destroy the log and then get the inner data so it is no longer protected by the spin lock or other kinds of locks。

 so it is the API for that。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_34.png)

And this is the one of the most interesting API of this lock types。 So when you call a lock。

 it that only acquire the inner inner logs lock。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_36.png)

So that you get the token。You are going to return the lock guard。Lockguard。

 as we discussed in the previous lecture， is a proof that you has acquired a lock。And as a result。

 you put the lock itself。And then you're going to put the token here。Tken is returned by the lock。

 and it proves it partly proves that you have acquired the lock So and it should be given to the unlock function so that should be remembered inside this lock guard。

So so far so good。 And this is the type that is。Guarants or proofs。

Proofs that the lock has been acquired。And how can we use it， So in the。嗯。Okay。In the lock art type。

 it is。It has a scope that is statically guaranteed to enclose the lifetime of this lockguard。

 so recall that， recall from the rust book that when the scope is used at this point then thisstruct is guaranteed to not own life the scope that is given as。

The luck guard should be dropped before the lifetime S has ended。So that's the meaning of this scope。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_38.png)

And this scope is here， because you。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_40.png)

Acquire the log using a lifetime。 So this is the lifetime of the log。

 and it is immutably borrowed here。And this cop here。

 the scope of this lock is just copy and paste it into this lock guard here。It is elighted。

 but it is still guaranteed that this lock guard does not own life the lifetime of this the lock here。

It is very much。Very much。Expected because luckguard should not outnigh the luck itself。

So it is guaranteed by the lifetime that is described here and here。Okay， so far circuit。

And the lockguard also has a reference to the lock。

 so it is basically the reason why this S is here in the implementation of this lock guard。

And you also have a tuckken。That guarantee that should be given to the unlock function。

So there are many functions here， but the most interesting part of the line is this drop here。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_42.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_43.png)

When lock guard is dropped or distracted， then as we discussed。

 the underlying lock should be automatically released。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_45.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_46.png)

How can we do that？ We are doing that by calling unlock function。Using the tockken。So that's all。

 we just unlock the thing。And that's the only thing we need to do at the end of the lockguard。

Let's see that the implementation here invocation of a log is arrived with unsafe because as we discussed the inner lowx un function is unsafe。

 it should guarantee that the token should be the same with the the one returned from the log function。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_48.png)

But it is guaranteed by our implementation。 The token here。

 Sa the token is actually one that is returned by the lock function。

 That's the reason why we satisfy the guarantee or contract that is set by the。😊，ARola API。

 That's the reason why we don't need to mark this function as unsafe。

 It is always safe to drop a lock guard。Because the underlying data structures invariant is guaranteed by ourselves。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_50.png)

So you need to see the onmark wrapper here， and this is precisely the locations where we need to manually inspect whether we satisfy the guarantee or not。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_52.png)

G so good。And how to use use this lockguard。 So these two tracking implementations are the most important and interesting part of the question。

So when you have a lock guard and then you can dereference the inner data type。Lockard， as I said。

 is a guarantee that you have acquired the lock so you can mutably and immutably access the inner data。

That is guaranteed by these two functions。 So when you have a lockguard。

 then you can de referenceence the inner data。The implementation is， as I said。

 unsafe because the fact that you can access the inner data is guaranteed by the implementation of a lock。

Similarly， you can mutably dereference the inner data。

Also the implementation is unsafe because the again。

 the invariant that you are the only one that access the data is guaranteed by the implementation of the spin lock。

 not by the type of rust， it is not automatically correct。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_54.png)

Okay， so first the good， and it has other kinds of APIs which makes our lives easier。😊。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_56.png)

And please look at the other code as well when you are inclined to do and this is basically the APIs of and a little bit implementation details of this spin lock and higher level API of lock。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_58.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_59.png)

Okay， so far second good， and so far we discussed many kinds of low level APIs of concurrency libraries。

 it is very low level。 it is about locks， stress and conditional variables， etc。😊。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_61.png)

And let me show you a tease of a very， very high level of parallelism library API。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_63.png)

And this interpoit is the epitome of such an example。O。From now on。

 I don't want to discuss concurrency at all。 I just have a range that has a 100 element from 0 to 100。

 and I just want to perform on action here in peril。That is all I want to do。

 and that is the idea that I want to implement in this code。How？

If it were to implement with a low level A API， then we need to somehow synchronize multiple stress and distribute the work into the multiple thrust。

But it is very much low level detail。 I want the library to deal with that on my own。 instead of I。

 I do it on my own。

![](img/f82ac7d75edee96a34edfef2a3f9ace9_65.png)

This line does that。 This line automatically parallellyze the job to multi stress。

 If your your CPU has， for example， 6 stress， then it will distribute the work across 6 stress。

 it will automatically detect the number of CPUus you have CPU core and stress you have。

 and it will automatically distribute the work to multiple stress。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_67.png)

![](img/f82ac7d75edee96a34edfef2a3f9ace9_68.png)

So that's all。 and that's the old code that is needed to paralyze your workload。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_70.png)

So here is the code that is cut and pasted from the example when you run it。

It is actually doing it in peril。From here and to here。

 you cannot see whether it is actually paralyzed or not。 But here there is a。嗯。there is some。

Mising values that is executed later right so this is precisely where the this is precisely the evidence that parallelism kicks in。

 the range from 50 to 74 are executed in a different thread， but they are scheduled later。

 so that's the reason why they are not executed before 705。So it basically proves that， oh。

 this code is paralyzed and executed in multiple stress without knowing any kinds of low level details。

 it is very much higher level， it doesn't even mention threat。

 but it is automatically distributed across multiple stress。

The further benefit is that the API is 100% safe。When you use Inpower item。

 you don't need to worry about the correctness of this library。

 the library author should have already taken into account the safety in their implementation。So。

This rayon is， but under the hood， the rayon is implemented on top of the cross beam。

 which is a heavyweight concurrency library for rust and。In the next video。

 we are going to study the cross scheme and its a few APIs。



![](img/f82ac7d75edee96a34edfef2a3f9ace9_72.png)