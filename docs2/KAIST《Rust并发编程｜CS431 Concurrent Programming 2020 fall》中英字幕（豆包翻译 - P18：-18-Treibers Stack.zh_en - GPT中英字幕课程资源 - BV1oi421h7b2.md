# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P18：-18-Treibers Stack.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

Today we are going to start studying the lock free data structures so in the previous videos we studied how Concorne data structures may improve the scalability when compared to a sequential data structures protected by locks and as an example we studied lockup blink list。

And from now on， we are going to focus on what is called lock free data searchers。

So the dictionary meaning of this lockfr is there is no lux。

 The data structure is not protected by lux， but it has further meanings that will be defined later。

 which is very technical。 So I will going to introduce the concept of these luxury free data structures and a few examples。

 a few representative examples of lock free data structuresers。So。In this semester， in 2024。

 the homework 5 will be about implementing what is called split Order the list。

That is basically a hash table and Home6 will be implementing a garbage collector for luxury free data structuress。

 So as a result， you are going to be able to implement on your own the luxury free datas。

 especially the most important one hash table。Okay， so far circuited。And let's think about logs。

 What is log log is allowing only one thread to access the share data， and as a result。

 the other threads may pause or stall So so if one thread is holding a log and then do expensive computations。

Or I O or even E crash。 And it doesn't。It doesnn't return at all。

 then maybe it is possible that the threat is postd or stall。And in that case。

 the other threads cannot acquire the log and it cannot proceed on its own operations。So as a result。

 it may be possible that thelock may happen， the deadlock is that the threads are holding resources that cannot that makes the progress impossible for example。

 if threat A is holding thelock L1 and it is trying to acquire L2。And also。

 let's assume that Str B is holding a lock 2， and it is now acquiring。

 it is trying to acquire the lock L1。And in this case。Both A and B。

 they cannot proceed on each operations because A cannot acquire L2 because L2 is already acquired by B and B cannot acquire L1 because L1 is already acquired by A。

 and as a result， there is some deadlock， they cannot proceed at all。

And it is usually happening in Lville。Conquerd programming。 So in order to do so。

 we may need to somehow。Managed not to in such situations。

And one of the countermeasure is that even if it happens， even if that drug happens。

 it may be possible that we can detect that log and kill one of the operations， for example。

 B is holding L2 and this is dead log and as a result we may pick B as a victim and just throw away these operations。

And then L2 will be freed， and then a will be able to acquire the the log L2， and it can proceed。

And as a result， as a system， as a whole system， it guarantees some progresses。

 at least a will progress。It may be possible that we can kill A and let B progress in either way or we can make sure the system as a whole progresses。

It is a counter measure， but it is not very perfect because there is a situation that is called livela。

 So the see the contrast between dead log and livela。 So it actually does something。

But it is keeping killing the operations。 So let's say that B1 is trying to acquire the log L1。

 L2 and then S3。B is L 2 S L 3， and then L1， C is acquiring L 3， L1 and L 2。So， if B。

This acquired the L2。And the C is holding L3 and1。 So they progressed。 They acquired the luck L2。

 L3 and1。And。If it is the case， it is guaranteed that no threat is able to progress because all the locks are held and all the threads needs to acquire more locks。

And as a result， we may kill C because it is a deadlock。

 so we want to kill one of the operations and at this point of time we want to kill C because it is。

just for random reasons。And F of that。A， let A acquire the L1 and B acquire an L2 industry3。

So B already held L2， and let's say that B additionally acquires S3。

In almost the same situation has happened， one thread has acquired one lock and a thread。

Has acquired two locks。And as a result， we may detect a deadlock for the same reason as above。

 and we may kill B。And the same thing may happen。 let's see acquire a log。

 and then A acquired an additional luck， and then A is killed。And it can loop。After A is killed。

 it may be possible that we have to kill C， and then B A， CBA， CBA， etc。So if that happens。

They seems like progressing。Because some operations are killed and the other operations are making more progresses。

But at the end of the day， if if we look at the entire execution。

 no threats are making meaningful progress because they are。Kept killed by the deadro detector。

So this is a problem， this is the problem of that is due to locks because lock this allows the other threads accesses at all and as a result。

 it may be possible that no stress can progress。Even though we can deal with the deadlock with the。

Operation stop stoppinging the operations。 The library problem may happen。

 So it is much more complicated than what it first。

So this kind of situations is the enemies of the lock freedom。

 So lock freedom is basically trying to avoid such situations altogether。

 we want to make sure that at least one of the operations are going to progress。

So that is the meaning of the lock freedom。 So the lock freedom as a technical term。

 is not only meaning the lack of the locks， but also meaning the progress guarantee。

 So at least one operations should progress。And if you use lock。

 it is almost always the case that it is not lock free。 So it is like。Euphorism。

 it looks like eupism， but euphorism처럼 보。It is actually nice。If we have luck。It is， love freedom。If。

Even though you don't use log， it may be possible that it is not love freedom。

 So in order to guarantee such a progress guarantee。

 we have to give more attention than just start using logs， so。So from the next slide。

 Im going to explain how to concretely achieve this life freedom for concrete examples。

So the key idea here is that。We want to make sure that the operations progress at a single point。

Which is called a Com point。So suppose that we want to design a stack and we want to design push and pub operations for the stack。

And we make sure that for this idea， we make sure that a single instruction。

 single architecture instruction is committing the changes to the data searcher。

And by doing so we can leverage architecture's guarantee of progresses。

 so architecture or hardware guarantees that if there are multiple CPU cores and there are multiple stress。

 then at least one of the threads or cores are able to execute the following instruction。

And also if the following instruction is， for example， RMW instruction that has success and failure。

 then the architectural Rojaia guarantees that at least one of the cores will succeed in the following。

The later， the RW instruction。So it is guaranteed， so it is a kind of progress guaranteed。

The architecture guarantees the progress of the RW instructions。

So by leveraging the architectureural guarantee， we can design a lockfr software。

 so by using a single R domain instruction as a coming point， we can see that， oh。

 even though multiple stress are trying to access this stack at the same time。

 some are pushing and some are popping， at least one of the operations will succeed because one of their R domain instructions will succeed。

So okay， that is basically what's the high level key idea of almost all work free data structures。

And it usually should be the read Moifier right operations because read is impossible because read doesn't change this memory state at all。

 so it is not acting as a coming point。And also， write this。Limited。

 it is almost impossible to achieve the coming point using writing instructions because right。

 if you write the value。It can be overwritten， arbitrarily。So。

 so there's not so many are guaranteed by the writing instructions。

 So the that's the reason why rights are usually almost always not able to be used as a coming point。

So actually， our internal instruction is introduced in the history in order to guarantee the the signal instruction coming point in order to support the single instruction coming point。

 So in 1970s or so in the。In the main frame computers。

 the armd instructions are introduced in order to achieve such synchronization among multiple threats or multiple cores。

Okay， so and this single instruction come point idea is indeed defeating the enemies of block freedom because threat pose still doesn't bother with a single instruction。

 So single instruction is always executed or not。 It is not post。 It is not interruptruped at all。

 Instruction is a tomy。It is either completely executed or completely not executed。

 so there's no way for the other thread to interrupt or interfere with the single instruction。

And also。Roughly speaking， because there is no locks， we don't have deadlock and live lock problems。

So if we design this single instruction coming point well。

 then we can guarantee that there will be no deadlock or no livelock problems because at least one of the operations will be going to be successful。

Okay。And as a sideic benefit or side effect， we achieve， you can additionally achieve scalability。

Because。Because unlike logs， the contention among multiple stresss are happening only at a single instruction。

If you use Pro data structure with lot， then you're going to going to。

Eute multiple instructions inside the lock。And when the multiple instructions are executed。

 the other instructions among other threats or other course will not be able to proceed。

But on the other hand， in the lock free data search using single instruction comm point。

 we can effectively reduce the contenttingion to just a single instruction。

Because the other instructions are just preparing for the comment。Or the post commit， the cleanup。

And they are not contented at all。 The contention among multiple stress are only happening at a single instruction。

And that is basically the reason why we can achieve better scalability by using this idea。Okay。

 so let's see how this can be implemented in the following example， which is the tri stack。

TriverseTag is one of the oldest Con data search， Concur luxury data searcher。

 and this is published as an internal document of a company。And you can see the source code here。

 so in this repository， you can see the entire source code of the stack。

And the tribalt is basically a single linked list， so it is a linked list。

 and the head pointer is basically the stack top。So this is an illustration of such a stack So top there is a top pointer。

 head pointer is the top and the values are stored in the stack and there is no pointer here。

And when you push a value， you' are going to insert here。When you pop a value。

 you are going to pop a value at the top of the list。So by doing so。

 you can effectively guarantee that， oh， this will be actually a stuck。

Pushing and popping at one end。 or firsting first out。By the way， do you know how to prounce F IFO。

It is actually5ful not people， so。If you are going toun prounciiate it in front of the others。

 try to remember it is faithfulful， not faithful。Okay。

 so now let's explain how to pop a value from this linked list and suppose that third A is trying to pop a value from the top。

八通より。It first read the top pointer。So this is a pointer to the next block。

 so we are going to read it。So it is the beginning of the P operation。

And the second thing to do is read the next pointer。

The reason is that we are going to remove this42 node。

And the new tab should become pointing to the third7。And as a result， we need to read this pointer。

And the next step is performing a comparing swab from top。

 so this is a pointer that was originally pointing to 42。

 and you have to perform a class from 42 to 37。As a result。

 the top is now  pointing to37 if successful。And after that。

 you can return 42 because you effectively change the text state from 40 to 37 666 to 37 and 666。

So you popped， you just popped the first value for it to at this time。Casing by casting from 42 to37。

 42 is removed from the stack。So you can successfully return the for you too。

If the previous class was a failure， you didn't succeed in performing this class。

 and then you can just go to the beginning and do it again。🤢，Because。If the course isn unsuccessful。

 then it means that the top pointer has already been changed by the other threads。

So you need to start again by reading the top pointer。Now。

 let's suppose that another thread B is trying to push your value to the step。

The first thing to do is reading the top pointer， which is pointing to， for example， sorry 7。And now。

You create a new note。You create a new note that is containing the push value。

And the next pointer of this node should point to the original top top pointer value。

 which is 37 in this case， because you rate top pointer and it was pointing to 37。

 and that's the reason why we are pointing to 37 in this new node。And furthermore。

 we are performing on class。Performa cut from the top for the top pointer from sorry 7 to the new node。

So by doing so， it can effectively insert in a new value， if successful， if the cost is successful。

 the content of the stack is new37 and 666 that is effectively the original stack that is inserted by the new value。

Okay， so by doing so， we can manipulate a single in a synchronized manner among multiple stress。

 and this pop push pub synchronizes with the costs。😊，Operation。

 the comparing sub operation are the top locations。So if this tough successs in the。

Performing a class， then all the concurrent operations will fail to perform a class on this top location。

And as a result， they are it is as if the other stress are。

Executing the operations after3 A's P operation。If B succeeds in its in its operation。

 So is performed is it is successfully performing on cars。 And as a result。

 all the concurrent operations will。Be able to perform its operations after be successfully push the value。

And here discuss is the single instruction coming point that we discussed just before in the previous slide。

If this is successful， the entire operation is successful。If this cost is successful。

 then the entire operation is successful。Otherwise， they are not successful。

So this is the single instruction that decides whether an operation is succeeded or not。Okay。

 some price that good。So so from now on， we are going to look at the code and then go back to this slide and explain a little bit more about the synchronization。

So now let's look at the code。So this is the code of the stack that is in the repository。

 the course's repository。And as I said， it is a singlely linked list。

 so you need to have a head pointer。Head pointer is pointing to a note here。And from now on。

 for luxury free programming， we are going to use what is called the Crosspaypo library。

 which provides。A few utilities to implement a lot of frequent container structures。So。

 so let's say that atomic is just a pointer。 You can think of this as a pointer to node T。

An atomic means that it is a special pointer on which you can perform atomic operations like comparing swap and atomic reason rights。

So this is an intentionally ra location， multiple it you。

Or implic assuming that multiple stress are accessing the head pointer at the same time。

And it is safe only if it is marked as an atomic。So this is， this has a head pointer to the node。

And each node has a value。And the next pointer。The next pointer is the same with the head pointer。

And the data is wrapped with what is called a manually drop。

 So Im going to explain what is the meaning， what's the meaning of the manually drop later。

So you can just think of it as T for now， it is containing the data of type T。So at the beginning。

The empty stack is just having a no pointer。So head pointer is known for the amista。

This is very much anticipated because the stack values are what is in the linked list and the empty stack should have no value at all。

Now， you， let's suppose that we won't push our value。As I explained in the figure。

 you first create a note here。So this is the node and you can think of it as an in the allocation in the queue。

H。So in the hip， a new nose is allocated。But。But in order to use the Crosspay people library。

 you'll need to use what is called owned rather than boxs or adult typess。

 and let's think of it as just a H about location that is meant to be used for concurrent data structures。

And the data will be the new value given here。And the next pointer is yet no。Okay。

 so first second good。And now。We are going to create a guard for the Cond data searcher operation。

 so we are going to study the meaning of this pin and guard later。 but for now。

 let's assume that in all。Data structure operations。 you are going to create a guard。 So this is。

Related to the garbage collection of the infrastructure。And for now let's ignore it。

 so at the last part of this lecture， I mean last part of this semester。

 we are going to deal with the Gop collection and at that time we are going to study garden pin and the purpose of this coursesewe Epo library。

For now， let's just assume that at the beginning of an operation。

 we are going to just acquire a guard here like this。And as I said before， in order to push a value。

 you'll first read a head pointer。You read the hat pointer。

And then the new nose next pointer becomes the head pointer。So effectively。

 you are trying to insert a value that。

![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_1.png)

Like this。Sorry。

![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_3.png)

哦。My fire is。O。My firefox was gone。嗯。It is restarted， so。哦。



![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_5.png)

Sorry， I will complete your dis a little bit。

![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_7.png)

O。So。Okay， we are back。Okay， we are going to。Insert a new note， which is going to be。

I me to point to the original head like this。And then we are going to perform a comparison swap。

 Comp set and Comp swap they are the same。 we are changing the head pointer from the original hat to the new node atomically。

And if it is successful， we are done， we just return。And if it is unsuccessful。

 then we are going to start again and try again。So the reason why we。

Do this is that after failing to perform the class， the new node here is returned here。

And we have to set the end here again， by the。Or what is returned from the comparison swap。

So firstly good。And。Let's see what's going on in the pub operation。So in the pub operation。

 we are going to。Make a guard again。And then。Read the head pointer。

And you are going to dereference the head pointer。Because you are going to read the next pointer of the head pointer。

So you are the first thing。And if it's no pointer， then you are going to just return。No， known。

The means that if the head pointer is no， then it means that there is no value inside the step。

That's the reason why we return immediately， none。If it contains something。

Then you are going to dereference the next pointer of the hat pointer。

And now we are going to perform a comparison swap。By atomically changing the hat pointer from the original hat to the has next pointer。

 which is right here。So firstly good， and if this comparison swap is successful。

 then we know that we succeeded in the P operations， so we are going to return some value。

And what we are going to do is that we first read the head pointer here。

The hotpoint chart data is red here。And then the， we are going to mark the head point head note as。

No longer used， so we are going to destroy this head pointer using this API。

This is a little bit different from the free because it is not going to delocate this node immediately。

 but it will wait for a few more times before actually。Delocating this head pointer。

 it is also related to the garbage collection， and the reason why this should be delayed is that it may be possible that the auto threads are concurrently accessing the head node at the same time。

So we have to wait forward the other thread to finish accessing the head note。And only after that。

 we can destroy this headn using this API。So， we're going to。Study this API。

 I'll did a little bit more at the later stage of this class。 And for now， let's assume that we can。

 you can。Deer destroy a node only after you detach the node from the data searcher completely。

So here we perform the comparison swap， so the head pointer was in the head。

 but this head value is completely eradicated in the memory by this comparison swapb operation。

Because now the new head is next and the old head is no longer presenting the memory。

And only after that， you can do this different destroy hat。

So this is the API contract between the crisping inputpo and your stack code and please memorize the contract。

 you have to remove all the reference to the pointer before you actually call default destroy。

So first second good。And you can also check whether the。啊 the。

The value of the tag is empty by looking at the head pointer， etc。

So that's basically what's going on in the。In the stack implementation。

And now let's look at what's going on in the。啊。What's going on in the。This tag in more detail。

 So in particular， we want to study the the synchronization that is happening inside the inside the。

The drivers stack。So my slide is also closed， so Im going to。



![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_9.png)

![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_10.png)

Okay。Okay， so。Please wait for me， a'll little bit more。Okay， so now we are backing the slice。So。

I have a few questions that is at the line 50， we are using release and also at the line 64。

 we are using a choir。Why we do that， Why we do that is the question。

 So that is basically related to。The last behaviors and the promisemantics。

And why we have to do release and acquire like this。

So I'm going to explain this using by going back to the code here。系。好。Okay。

 so we are back in the code here。At line 50 we are using release at line 64。

 we are loading a acquire。So the reason why we do release a acquire here is that we want to release the value。

 So if we push a value to the stack and then pop the value。

 we hope that there is a synchronization between the push and the pop。

So it is just like passage passing。If thread A pushes a value and then threat B pops the same value。

 then it should be the case that all the knowledge that has been gathered so far by A must be transferred to threat B。

So as a result。So we want to guarantee something like this。 If a is， for example， writing a value。

And then。Of push a value to the stack。We want to make sure that。The access value is for to here。

 So the code is like this。 If you push， if you write the value。And then push a signal to the stack。

And in B， it is receiving the signal。And at this point of time。

 we want to make sure that third B should be able to see the value x equals for it2。Actually。

 it must see the value x equals for it too。So in order to do so。

 there should be some release across synchation between the push and pump。That's the reason why。

This is release， and this is a acquire。 The head pointer is changed using a release ordering。

And at the pub， you have to acquire this。😡，In order to transfer the view and the X， for example。

 to the threat B。So access view， x equals 42 view is transferred to the head pointer by the release instruction at this point of time。

And it is acquired here， and as a result， x must be for2 at this point of time。

So that's the reason why we are going to use release and acquire for these lines of code。And further。

 another question on this study is that。We are using what is called manually drawn。

So what's the meaning of this manually you drop and。Actually。

This little bit complicates the code like this， so in order to read the date in order to return the value in P。

 we are reading the internal value that is inside this manually drop。And further。

 we are creating a new node using this API of manually drop。

 So it is a little bit compating on what's going on there。

So the reason why we do this complication is that。The the。え。When this note is destroyed。

At some later point of time。We don't want to call the de or drop of the data once again。

The data is already taken， and it is returned to the path function。As a return。So the data。

 the same data。Must be ded without incurring without calling the de or drop。

So that's the reason why this it is smartest manually drop。

 if it is markedest manually drop when they had no is destroyed or deallocated at some point of time later。

 using this API， then you can guarantee that you。You are not going to call the disruptor again。

Because the deor will be caught by the core of this pump。

This card deferred destroy should not invoke the structure。

 so it is guaranteed by this manually draw。If the data is wrapped with the manually drop。

 its the is not involved。In this node。 So that is basically the meaning of the manually drop。

So for a second。And let's go back to the。Let's go back to the。Slice。And yeah。

It should be releasing an cho in order to achieve the synchronization between push and pop。

And this should。Be satisfied by all almost all the concurrend data searchers。

 If you push a value and pop the value in Q， then there should be some synchronization。E cetera。

 et cetera。 And that's the reason why some orderings must be marked as relation acquire。

Another question is was manually drop and as I said。

 we need to mark some data in with manually drop in order to make sure that that the the structure will not be cultivated for data when the node later delocated after the value is returned。

So it is very common in luck for data searchers because even though you return the value。

 your node must be there for living normal time and in order to do so。

 we need to mark the data as manually drawn。So Q also wrap data data with manually drop hash tables also wrap the data with manually drop。

 etc， etc。So that， this is based the meaning of this manual drop。



![](img/97c4a5ee3e95cdb5bbd1c2ab2ba8d0a2_12.png)

There are a little bit more questions， and I hope that you are going to study this kind of this slide on your own as a homework。

And。In terms of the promising semantics， the imvariant of those stack is that the head pointer value has a release view。

 so recall that all the messages in the Pro semantics has a release view。

And the invari is that they hat pointer。Its release view is bigger than what you call to all the messages for all the nose value next pointer。

So you write values。 You write next pointers for a particular nose。And there are multiple nodes。

And the imvari that is held by that is maintained by the operations is that at any given time。

 head pointer value release view is bigger than or equal to。

Subsum or subsumes all D knows value or next pointer messages。

So this release and acquire is actually guarantee that。

Reasees maintaining the invariant and acquire in the pop operations is explain the invariant so that the push and pop are。

Are properly synchronized。So this is a little difficult topic。 so I will not ask these in the exam。

 but if you're interested， please read this paragraph and ask questions if you are more interested。

Okay， so first good。 So far， we studied the tria。So Triviste is one of the most。

Basic and yet interesting data researcher， conquercurren data researcher。And from the next lecture。

 we are going to study queuees or other data searchers that is a little bit more complicated than this deck。

And and then as a homework， you are required to implement the what is called split ordered。

Liinnkked list， which is meant to be a hash table， Con hash table。

