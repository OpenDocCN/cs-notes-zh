# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P17：-17-Lock-Coupled Linked List.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

Okay in this video， we are going to study the key ideas of concurne data researchersers and one of the first implementation strategies that is on lock coupling and we are going to discuss logcod linked list。



![](img/feb2efcc42557513609631fb7b6bd49c_1.png)

![](img/feb2efcc42557513609631fb7b6bd49c_2.png)

![](img/feb2efcc42557513609631fb7b6bd49c_3.png)

So。Concurrd programming is fundamentally about concurd data structures because multiple stress are trying to access the same resource。

 and the resource is fundamentally about data structures。And this con。

 So the concur data structure is the heart of the concur programming。

And this the key objectives of this， this course， basically。

And there are the three criteria for the concurrent data searchers， safety， scalability and progress。

And let's look at each of them a little bit more detail。For safety。

CDS needs to satisfy some specification。And one is what is called a sequential application。😊。

It means that， oh， if you have a Concur Q and it should work as if it is a sequential Q。😊。

So if two stress are pushing and popping a value to the queue， then the operations are。

Returning the return values as if they are working on a sequential queue。

So if it returns some random values， you can no longer say it is a concurrent Q。

It needs to return a specific value that is governed by the Q specifications。And further。

 you need a synchronations。If you push if thread A pushes the value and threat B pops the value。

 the same value。Then there should be some really acquired synchronization between the pusher and the pa。

But the reason is that the queue can be used used as the communication channel。

 it sends the value to signify something。And in order to do so。

 there should be some really acquired synchronization between the pusher and the popper。😊。

And the second objectives is the scalability。Okay， safety is the minimum required requirement for CDSs。

But what the purpose of using concurrent data search is scalability。

We hope that this is much more scalable， especially for the parallel architectureits than the sequential data searchers。

And。The scalability is that it shows better performance as the number of core grow。Ideally。

 it wants to achieve linear scaling， that means that if you double the zip number of CPU cores。

 then performance is also doubled。But in reality， it is very much difficult to achieve linear scaling。

 especially for more than 16 stress。So you need to account for。 you need to。

Think about the Popons drop。Compared to the linear scaling。

 but still if you want to make it work better。It， it should be sub scaling， subline scaling。

 but you want to drop。As less performance as possible。And finally。

 you want to guarantee some progress about the concur searchers。

 which means that you want to somehow guarantee that your operations will be finished and list。

So there are multiple notions of this progress， and luck freedom means that， oh。

 if multiple stress are trying to do the same thing， then you want to guarantee that。

 at least one of them will succeed finishing its operations。

If multiple threats are trying to acquire a log， then。At least one of them succeed。

 that's basically is guaranteed， what is meant by this luck freedom。

And wave freedom means it a little more stronger。Condition。

 which means that if multiple stress are trying to do the operations， then。

I will eventually take turn。So even though there are multiple contentions。

 even though there are many other threats。That is trying toequ a lot。

And I will eventually be able to acquire a lot。That that is the meaning of a freedom。

So spin lock is not way free， it is lock free， but it is not way free。

 but the ticket locks and CH locks are weight free because it is guaranteed that one day I will succeed in acquire a lock。

So， that is basically the。The meaning of the lock freedom and wave freedom， the progress guarantees。

And there are a way to achieve these desired properties for CDSs。So， for safety。Are the。

The key idea is protecting a data structureer with logs or more primitive synchrons。



![](img/feb2efcc42557513609631fb7b6bd49c_5.png)

![](img/feb2efcc42557513609631fb7b6bd49c_6.png)

So one of the implementation strategy is protecting a sequential data structure with a global lock。😊。

So then you will turn a sequential data structure into a concurrent data structure that is protected by a lock。

It is the easiest way to do so， and most of the implementations use this implementation strategy。

 but it is less scalable than the other options。😊。

![](img/feb2efcc42557513609631fb7b6bd49c_8.png)

![](img/feb2efcc42557513609631fb7b6bd49c_9.png)

![](img/feb2efcc42557513609631fb7b6bd49c_10.png)

Another option is protecting a data structureer with more fine grain logs。

 so there are multiple logs， and each log protects a subset of the entire data structure。



![](img/feb2efcc42557513609631fb7b6bd49c_12.png)

And by doing so， you can reduce contentions very much because multiple operations that it is accessing different parts of the data search can coexist。



![](img/feb2efcc42557513609631fb7b6bd49c_14.png)

![](img/feb2efcc42557513609631fb7b6bd49c_15.png)

![](img/feb2efcc42557513609631fb7b6bd49c_16.png)

An even more scalable approach is protecting data structure with very custom synchronization protocols。

😊。

![](img/feb2efcc42557513609631fb7b6bd49c_18.png)

And。And at the later stage of this semester， we are going to study such synchronation protocols and finegrained concurrency and finegrained data concurrent data searchers。



![](img/feb2efcc42557513609631fb7b6bd49c_20.png)

![](img/feb2efcc42557513609631fb7b6bd49c_21.png)

![](img/feb2efcc42557513609631fb7b6bd49c_22.png)

And usually the specification is called the linear re。

 which is meaning this two sequential specification plus synchronization。😊。



![](img/feb2efcc42557513609631fb7b6bd49c_24.png)

And this is usually called the linear re。😊，And the concept is explained here。

 So if you are interested， please go to this link and see what's going on there。



![](img/feb2efcc42557513609631fb7b6bd49c_26.png)

And for the scalability， as I discussed in the previous slide。

 the first key idea is reducing dis in contenttion by shrinking lock protection scopes。😊。

So using multiple locks and let each lock protect a smaller subset of the data searchers。By doing so。

 you can register the contentions。The second key idea is reduce cash in validations by avoiding rights。

 So rights are usually detrimental to the performance because it needs to is closely acquire the cacheline。

😊，And it will invalidate all the other threads caches。So in order to avoid that。

 we want to avoid rights as much as possible。And it， it this approach is usually called。

Optimistic andcur control。You read something。To guarantee something。But after you read something。

You cannot be sure about the invariant， and you need to check again later。

So if you succeeded in the later check， then you are happy， but if it is not。

 you need to throw away your operations， for example。So in that sense， it is optimistic。

 it is optimistically assumed that， for example， a value will not change for some period of time。

If it is the case， you will get performance boost and if it is not the case。

 then you need to fall back。So that is basically what is meant by this optimistic concur control that tries to reduce caching validations by avoiding rights。

And as a case study， we are going to study optimistic lac coupling plane。

 but only after we study the lac coupling plane。😊，Oh， this is a typo。

 This is not about a homework too。 So it is for the last semester's homework。

 and in this semester and later this is will not applies。

And the last desired property of CS is progress， which I said is the。

The meaning of them are like this。And the key idea for achieving La freedom is designating a single RNW instruction as Com point so that at least one CPU core we subid this RNW。

😊，Which means that， for example， in spinlock， it has a luck location。

And multiple stresss are trying to acquire a log， concurrently by。

Updating the lock variable by some R Doling instruction。

And the audio architecture guarantees that at least one of them will succeed in doing the RW instruction。

ThatBy doing so， we can achieve the lock freedom。 At least one of the ongoing operations is completed someday。

 At least one of the stress will succeed in the its iron domain instruction。

And there is a notion of wave freedom。And。The key idea for achieving wave freedom is that。

Each thread publishes its ongoing operation so that the other threads can see its operations。So。

You need to guarantee that。Youre going。 your operations will be completed someday。How to doing so。

 you are publishing your operations and let the others do your operations on your health。So。Usually。

The luck freedom means that there is a winning threat。

 There is a threat that wins the race and do succeed in the armed instruction。So， the winner。

Is going to take in charge of the doing the other threats operations that is meant by this wave freedom。

So that is the key idea of this achieving the wave freedom。So for example。

 this YMCQ is a primary example of a wre a queue。Which we are not going to study in this semester because it is much more complicated than the other data searchers。

But if you're interested， please read this paper。Also。

 this is a very fine paper that is describing or defining the meanings of this freedom。

 wave freedom and other kinds of progress guarantees。😊，And it is class。

 it classifies the many guarantees into。Some criteria。 So it is very， very。Very fun paper。

 So if you' are interested in these progress guarantees， please go read this paper。

But we are going to study only lock freedom in this semester because the other progress guarantees are difficult to achieve and difficult to。

A study。 We are sticking to lock freedom in this mystery。Okay， as the first example of data search。

 concurrend data searchers， we are going to study locoly。😊。



![](img/feb2efcc42557513609631fb7b6bd49c_28.png)

![](img/feb2efcc42557513609631fb7b6bd49c_29.png)

So here is a locker pulled。Link list。And this is just a single linked list。

 and the only difference from the sequential linked list is that each node has a lock。😊。

And the lock should be held when accessing its next pointer。

 So each node has a lock and the next pointer， and the lock should be held to access the next pointer。

😊，So or you can say that this lock is protecting this next pointer。And。😊，You need to guarantee that。

You should acquire the next node log before releasing on current。

 So if you want to traverse this link list。You need to acquire the locks。



![](img/feb2efcc42557513609631fb7b6bd49c_31.png)

And before releasing a lock here， you need to acquire the next pointers。 Next notes are the。The lock。

So here is an example。So you can traverse this linked list by first reading the head pointer。

And at this point of time， you don't need to protect the lock because head is short and his head is immutable。

And you acquire a luck for the next pointer。

![](img/feb2efcc42557513609631fb7b6bd49c_33.png)

Before you read the next pointer。And because。And because this next pointer is protected by this nose lock。

 That's the reason why you need to protect。 you need to acquire a lock before reading the next pointer here。



![](img/feb2efcc42557513609631fb7b6bd49c_35.png)

And you need to acquire the next nose lock。

![](img/feb2efcc42557513609631fb7b6bd49c_37.png)

And only after that， you can unlock the previous nose La function。Previous nose lock。So。

 the reason is that。You want to make sure that this current node is not detached。

Before you you access it。So in order to do so， so if you acquire。

You you acquire this log after this is unlockgged。

![](img/feb2efcc42557513609631fb7b6bd49c_39.png)

ItWe maybe case that。As at some point of time， you hold no lucks on the linked list。

So you don't know you know nothing about this linked list。

 Maybe it can be possible that this node can be detached and delocated by another threat。😊。

You need to avoid such a situation。By， at least， you're going to。Hold at least the one nose lock。

SoBy doing so， you are guaranteed that your traversal is not detached。

 Your traveral is not going to be delocated。So let's see this again。 You like this。And you read this。

And as far as this lock is held， you are guaranteed that this node will not be delocated。



![](img/feb2efcc42557513609631fb7b6bd49c_41.png)

After that， you acquire the next node log。And it is guaranteed that this node and this note will not be delocated。

You know that if they exist。

![](img/feb2efcc42557513609631fb7b6bd49c_43.png)

After unlocking this log， then you no longer knows whether this will be delocated or not。

 and at least you know that this will not be delocated。



![](img/feb2efcc42557513609631fb7b6bd49c_45.png)

You are， you know， it， it exists， just。And you can do the remaining travel so by reading and locking。

 reading， locking again， again， again， again。

![](img/feb2efcc42557513609631fb7b6bd49c_47.png)

Crucially， as I said before， you have to acquire this log before before you unlock the previous node on。

 so is that is to make sure the current node is not yetated。Okay， so far so good。

So the reason why it is called luck coupling is that there is a couple of blocks。

 always you acquire couple of blockss and you unlock one of them， and you lock。



![](img/feb2efcc42557513609631fb7b6bd49c_49.png)

![](img/feb2efcc42557513609631fb7b6bd49c_50.png)

On one or another and then you unlock you unlock this and again and again and again。



![](img/feb2efcc42557513609631fb7b6bd49c_52.png)

So that is the reason why it is usually called handover hand locking。 you lock it， you lock。😊。



![](img/feb2efcc42557513609631fb7b6bd49c_54.png)

![](img/feb2efcc42557513609631fb7b6bd49c_55.png)

Next one。😊，And hand this over now， then you unlock the previous log and then you lock the next one and again。

 again like this。

![](img/feb2efcc42557513609631fb7b6bd49c_57.png)

![](img/feb2efcc42557513609631fb7b6bd49c_58.png)

So this is as if then the locks are held handover hand。

 So that's the reason why this is laccoing and handoverhand at the same time。



![](img/feb2efcc42557513609631fb7b6bd49c_60.png)

![](img/feb2efcc42557513609631fb7b6bd49c_61.png)

Okay， so here is how to implement the linked list operations for this locker。Data searchers。

So if you want to insert B between A and C， you first acquire a log and read the A's next pointer and allocate B with its next pointer pointing to the C。



![](img/feb2efcc42557513609631fb7b6bd49c_63.png)

![](img/feb2efcc42557513609631fb7b6bd49c_64.png)

And then write a A next to B。So at any point， you can see that。

So you are going to change this pointer here。😡，Right， so thiss the reason why you need to。

You need to hold its luck， always， from the beginning。



![](img/feb2efcc42557513609631fb7b6bd49c_66.png)

Because you are going to change this pointer。 So after traversing this pointer。

 you need to acquire a log and after traversing， you create a new node and you should still hold the lock because you are going to change the next pointer。

😊。

![](img/feb2efcc42557513609631fb7b6bd49c_68.png)

![](img/feb2efcc42557513609631fb7b6bd49c_69.png)

The next pointer should be changed。Under the luggage hole held。And now suppose we want to remove B。

 B is this pointer between A and C。And what we should do is this you acquire a s， read A the next。

 that is B and acquire Bs log。And。Now， you want to remove。This node。

 and you want to change this pointer here。

![](img/feb2efcc42557513609631fb7b6bd49c_71.png)

So you' are not going to release a lock。

![](img/feb2efcc42557513609631fb7b6bd49c_73.png)

Because you are going to change this pointer。So you need to protect this pointer using this lock。



![](img/feb2efcc42557513609631fb7b6bd49c_75.png)

So instead of unlocking a log， you read the pointer again。And now you write Ada next to C。

Because because it is safe because you are holding the lock for this A。

And now you release be loved and then freebie。So you can do that because you can。

 you can do that because you are the only， the only one who can hold the。The pointer to the here。

Because no one is can point to no， no the other， no the other threads can point to this block because。

 in order to do so， it must have already。I acquire this luck， but this luck is held by me。

So no one is going to access this。 So we that's the reason why we are free to free this block B。

So this is basically the linked list operations。 So insertion and removal。

 they all are involved with logs like this。😊。

![](img/feb2efcc42557513609631fb7b6bd49c_77.png)

So。There are pro and cons of lacup plane。And the first process is that it is a relatively easy implementation strategy。

 it is much more easy than the fine grain concurrent data searchers。😊。



![](img/feb2efcc42557513609631fb7b6bd49c_79.png)

And yet it is quite scalable， for example， for the linked list。

 they are concurrently holding only two logs in the data search。

 so it may be possible that multiple threads are accessing the linked list at the same time by accessing different parts of the linked structure。

😊。

![](img/feb2efcc42557513609631fb7b6bd49c_81.png)

![](img/feb2efcc42557513609631fb7b6bd49c_82.png)

And the concept is that you acquire the。Locks， even for res， even for travel。

 So you need to acquire a lock。 So there is a cacheching evaluation due to right。



![](img/feb2efcc42557513609631fb7b6bd49c_84.png)

And this local condition inspired rights will incur caching validation。

 which may degradece the performance。

![](img/feb2efcc42557513609631fb7b6bd49c_86.png)

And also， you need to take in take into account the possibility of thatlock。

 So this implementation doesn't have thatlock because the locks are ordered。 So there's no way。



![](img/feb2efcc42557513609631fb7b6bd49c_88.png)

![](img/feb2efcc42557513609631fb7b6bd49c_89.png)

啊，lus are。呃，No no way。To enter deadlock。 But you need to take care about this。

 You need to take care about the log order so that you can avoid the deadlock altogether。



![](img/feb2efcc42557513609631fb7b6bd49c_91.png)

So that's one of the cons。And the alternative will be lock free conquercur their searchers。

 So here it is very lockful。 We protect nose with locks。😊。



![](img/feb2efcc42557513609631fb7b6bd49c_93.png)

![](img/feb2efcc42557513609631fb7b6bd49c_94.png)

On the other end， we can think of lock for directors， which doesn't have locks。😊。

But the cause is that it is much more difficult than lock of playing。But the process。

 it is much more scalable and there is no caching valuation due to a lock acquisition or no deadlock。

 etc。So in the remaining of this semester， we are going to study this lovely data searchers and their properties and their memory allocator and the allocator。

😊。

![](img/feb2efcc42557513609631fb7b6bd49c_96.png)