# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P14：-14-Lock-Based Concurrency, Implementation of SpinLock.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

So today we are going to study the implementations of the locks。

 so in the previous part of this lock based concurrency we saw the huge cases of the logs and the interface of the logs and in this part3 we are going to actually look into the implementations and see why they are correct and in what properties they are actually satisfying。



![](img/2b0399a247dc7e485119bbc1238c51b9_1.png)

![](img/2b0399a247dc7e485119bbc1238c51b9_2.png)

![](img/2b0399a247dc7e485119bbc1238c51b9_3.png)

So recall that log is used in order to use sequential data structures as if they are concurrent。

 so suppose that there is a vector， for example， a vector is one of the most representative sequential data structures。

 this just an array of elements and you can push an element to the end of the vector， etc。

And the most easy way to make it concurrent is protecting this vector using a lock。

 So when a vector is paired with a log， then you first need to acquire a log before accessing the underlying vector。

And after acquiring the log， you can mutably access the vector。And after releasing a log。

 then the other threads can acquire the log and then exit the vector。

Locks are serializing all operations of the all stress， and therefore。

 it is completely forbidding the concurrent operations。 All the operations are serialized。

 and at the same time， only one thread is accessing the vector， for example。

It is very important because log is very important because majority of what is called Concur programming is actually covered by these locks。

 so in most cases Concor programming is trying to utilize multiple resources that measure the same resources but it is not particularly interested in optimizing or。

Or making a scalable for the high performance computing。 In most cases。

 correct synchronization is the purpose。So for example， in the operating system， if a data structure。

 for example， a clock is rarely accessed by multiple stress。

 then you can safely protect the clock using a lock。

It may degrade the performance if multiple stresss are trying to access the same clock at the same time。

 but our assumption is that it doesn't happen much， so it is sufficient。In Poma service。

 even performance service is insufficient to protect the clock with a lock。

But if you are really trying to make your data structure scalable and you want to exploit the parallelism opportunity that is allowed by the program。

 you really need to use other methods。 So because lock is。

Completely forbidding concurrent operations， but in some cases you want to actually allow multiple stress to access the same data structure at the same time。

So that is basically the trade off of the lock。It is easy to use。But it is inscalable。Okay。

 and this reposory contains the log implementations and you can see the safe API of in rust and the actual log interfaces。

 I mean actual log implementations， including spin lock， taking lock and this kind of locks。

 so we are going to deal with this kind of logs in the later stage of the lecture and we today we focus on the API here and the spin lock and their implementation。

And。There are many kinds of locks， and these locks also have trade offs。So one want to have a simple。

 fast， compact scalable， fair energy efficient and all the good properties for a single lock。

 but unfortunately multiple locks have different characteristics and they have fundamental traitoff between them for example。

 spin lock is the most simple lock implementation and it is quite fast when uncontended。

 but it is incalable and it is not fair and usually not energy inefficient etc。

So you need to choose the right lock for the right。What lot there is， basically。

The reason why the reason is that there is a fundamental trait of multiple lock implementations。Okay。

 let me first look at the APIs and then this spin。 So we already。

 we already discussed the API of lock in rust。 So you already sell the send sync traits and。

 and the API that contains the lock and unlock my firstst and token， etc cetera。

 But I'd like to recap the lock safe API in order to give a concrete context for a。

Implementation of the spin lock。Okay， so recall that a trait is a type class or a predicate of types。

 So， so a。A trait means that， oh。This type satisfies something。 This type satisfies something。

 or this type doesn't satisfy these properties。So you want to express that idea。

 you want to express the idea that some of the old typess satisfy some properties。In order to。

 in order to。In Nor plastic idea， you are going to use traits。

 trade is expressing a predicate of types。For example。

 here is a send trait that is provided by the Ru Standardends Library。

And send means that if if a type T is send， that means that the data T can be transferred to the other stress。

For example， you can send an atomic size that is meant to be a concurrently accessible word that can be sent to the other stress。

Also， this use size is also sendable to the other threads。

But probably if you have a thread local storage and then it should not be sent to the other threads because it will be specific to a certain thread。

 for example， by holding the thread ID， etc， and this storage。

 this resource cannot be used by the other threads。

 that's the reason why this kind of type should not implement the send。Okay， on the other end。

 there is a sync trait that means that it is if the type T implements T implements the sync trait。

 that means that the type T can be concurrently accessible from multiple stress。

 so that means that oh， I insert A and your third B and thread A and B can concurrently access the data。

So for example， atomic your size which is meant to be a conrently accessible word。

 that is definitely a sink because it is the purpose of this type is allowing multiple stress to access it at the same time。

But on the other hand。A simple word that is not meant to be concurrent。

 That is not think because because you are not particularly。Marked the type， as I think。Obviously。

 the threshold cluster storage is also not sync because it is meant to be used by a single thread and it should not be accessed by the other thread。

So that is basically the meaning of sentencing and for more information。

 please go to the Ru documentation and read the descriptions there。

And then the thing have a very interesting property here is that T is sink if and only if its reference type is sendable。

That means that a T can be concurrently accessible if and only if the reference type。

 the reference to T is sendable to other threads。🎼So it is like this is very much the same property so this。

Obviously explains the meaning of the sink。 The reference is send。

 That means that the type T is concurrently accessible。

So please memorize what's written here because the sentencing tract will be used throughout this lecture。

 throughout this class， and if you are interested in implementing conquercur programs in Ru。

 then you are going to use this trick all the time。In addition。

 in addition to the two traits provided by the standard library。

 we are going to use another trait that is called a Rolock。 Rolock means that it has。AI。

 that includes the log and unlock function。We already discussed this interface。

 but I'd like to rephrase this。 So it has a log and a log。 And when you log on a roll log。

 then you are going to get a token。And that token will be used to unlock the the log。

And you have to guarantee that the token provided by your log should be。

Return to the unlock function。That's the， that's the guarantee。 you have to make sure the satisfied。

And。And this roll log is also data for example， for example。

 spin lock contains an booleion value that indicates whether the lock is held or not。

 so it is also data is a resource and it contains information inside the log type。

So it needs to implement this trait as well， so you to initialize the lock。

 you need to implement the default trait， which means that you can just create a new default value of Ro lock。

So， please， go to see。The documentation of the default trait that is defined in the standard library。

 that means the track means that you can create any in any times you can create a default value of the type。

Also this solar lock should be sendable and sync because this is a log and this is meant to be accessible from multiple threads and thats the reason why it should implement both send and sink。

 it should be sent to the other threads and it should be accessible by multiple stresss at the same time。

So this is defined in the repository and please go read and the documentations and the implementation there。

And this true love has many。Assumptions。 so in order to implement， for example。

 spinlock and say that spinlock implements the roll lock trait。

 you need to guarantee a few properties of spin lock。And one of that is that the， the。

 the things about token， the token is already discussed， but the most important。

Property that you make sure you want to make sure for a spin knock is that。

Only one agent is acquired， has acquired a log at at a time。

So the purpose of the lock is mutual exclusion。 No agents。

 no two agents are concurrently holding the lock at the same time。 It is the。

It is the fundamental property of the lock， and you have to make sure that it is guaranteed。

So we are going to implement spin locks， taking las and other kinds of locks that guarantees this mutual exclusion property。

So only one agent acquire a luck at a time。 No two agents are。Hing the log at the same time。Okay。

 this is the API。ApiI's descriptions and using these two traits， three traits。

 then think and roll up， we implement the， the log types。So recall that。With the lock。

 you want to guarantee two things in rust。 The first thing is that。

You want to associate a log roll with the data。And the others is that you want to automatically release the log when you finish accessing the underlying data。

 so these are the two structures that guarantee that so first this log type has two components L is a low rock and T is the data and it owns the data T and the data and the object of type T is protected by the L log。

For example。L is a spin lock。 Then this is a T that is protected by a spin lock。If L is， for example。

 a ticken log， then it is the T that is protected by a tickenn。Et cetera， et cetera。And。

This type guarantees that， again， that， like the。They like the guarantee of the roll log rate。

 only one agent acquires the log at a time。This lock tie guarantees that the T object is not concurrently access at all。

So only one agent is having an access to the underlying data that is guaranteed by these log types。

So recall that you want to associate a log with a data， not the code region。

 so you should not think of safety of the concurrent programming in terms of code region。

You should be able to think of the safety of concurrent programming in terms of a data。

 which resource or data is protected by which lock。So this mandates us to think in that way。

 because we are explicitly。Associating a log and data。

 that's the reason why this API automatically guarantees the reasoning in such way。So for example。

 we have this type。😊，This， this is a lot。I mean， luck protected there。And the luck is spin up。

 and the data is a vector of words。Or this is a lock protected data and the lock is what is called CH log that we will learn later。

😊，And the protected data is a reference to some straight local storage。So in rust。

 we can express that idea， too。 this is a very local。

This data actually should not be sent to the other thread。But you can still protect the lock here。

 and。And you have to make sure that even though it is not protected because the underlying data is not sent sick。

 it cannot be accessed by the other threats。 make you have to make sure that。

And the kind of constraints will be implemented by the lockguard。

And these are the and these are trait constraints。So。You this lock time is。

Sendable and think if if the the type T underlying type T is aendable。 So this。

 this type is not sendable， right， This is a Tl S and even there is a reference to the T S and you you can immediately see that oh。

 this type is not sendable because it is accessible to the the thread roll cost storage that cannot be access by the other thread。

And that's the reason why this entire type， lock protected data of thisterce。

 it is not sendable and it is not sync。Because this lo type is defined as sentenceencing only if then the line type T is sendable。

So that actually means that log is meaningful， this log protected data is meaningful only if the underlying type T is sendable。

Thats， that's basically the idea of this constraint。And on the other end。

 in this type in the left type。The vector is sendable。Even though you created a vector。

 you can safely send the vector to the other threads。

 so it is quite quite obvious from the API documentation。

 that's the reason why T is sent for this case and as a result this luck type。

 Lapro data type is also sendable and sync。Okay， that is the type constraints or trade constraints。

 And you this kind of idea is implemented in rust using some in a hey way and you please read the code and see what's going on there and how to express this idea in this log type。

Okay， so。Luck achieves its goal。 It is associating a luck as a data。

And the second construct that is the lock guard is achieving the second goal here。

 the second goal here is that you want to automatically release the lock when you no longer access the underlying data。

So in order to do that， you define a new type lock guard which is basically an assessor to the underlying value。

 so it is a proof that you have acquired a lock when you call an acquire for this lock type。

 then you are going to get the lock guard that means that you acquired a lock and you are holding the lock。

And it's meant to prove the log is acquired。And it is RAII type as we discussed in the previous lecture。

 it releases the lock when it is dropped， so it is automatically done so if you are not going to intentionally forget about this lock art you are going to release the log when the lock guard is dropped。

And all objectives must be dropped someday。 So thats the reason why the the underlying lock will be automatically released。

So far circuit good and it is very convenient， you don't need to track the lock and you don't need to insert the unlock function for all the implicationss of lock。

Usually in CNC plus plus， there are are a lot of books related to this。 You forget。

You forgot about releasing the lock。 So it happens all the time。

 and it also complicates the control flow of the program very much。

And using RA AI in C plus plus or rust， the problem will be very much simplified so。

So this is much safer and easier API for using a spin lock。And also。

 this lock guard has is thereferible meably to the type T。

 That means it is a mutable accessor to type T。 If you have a lock guard， then you can access。

You can get a reference or mutable reference to the type T that references to the underlying value that is associated with the lock here。

Z。If if you have a lockguard， it can be transformed into a mirrorable。

AMutable reference to the type T。Okay， that is very much expected because you are holding the lock。

 So also you should be able to access the inner data。Okay， and further。

 this lock card is send if the underlying type T is send and it is sync if it underlying type T is sync。

In other words， the slu guard is transparent in terms of descendcing traits。So let me this。

 let me say this way。 So if T is sendable。Then。You can send a lock out to the other thread。

 That means that you can acquire a log and then transfer the knowledge or the ownership that you have acquired a log to the other threads。

And then the other threads can also access the data because it is implementing D and draft mut。

So that's the reason why you have to require the type T is sendable， only if the type is sendable。

 you can safely send a locker to the other thread so that the other thread can safely access the underlying data。

And the other threads， when passed by this lockguard。

 it can drop this lockguard and release the lock。So if this lockcard descend to the other thread。

 it effectively means that the lock is acquired by a thread and then it is released by the other threads。

😊，It is possible because tea is send here。Also， if you have acquired a log。

 then you can share the reference to the data to the other stress。This in order to do so。

 you have to make sure that T is think。 If T can be accessed by multi stress。

 then the lock guard can also be。Accessed by multiple stress and direct to the， their own types。

 So that is basically the the， the reason is that if T is does sink。

Then it is unsafe to share the lockcard because the other threads may be reference to the underlying data。

So in order for the other threads to safely dereference the underlying data。

 the type T should be seen as well。And that， basically。

The the explanation I have so far is summarized like this。 Rockor is a transparent taxi sir。

With respect to the send and sync trait and list。Okay。

 and I have discussed many guarantees about the APIs and these APIs and safety are actually proven。

 formally proven with respect to raw ownership type system。

 so I can be quite sure that the guarantees as far as you satisfies the API's guarantee。

 then the underlying implementation will work as expected without any worrying about the box。

 So that is formally proven that means that there is a proof and that is checked by the machine。

 So there is no way this proof can be wrong。So that's the， the power of the worst。

 as opposed to CNC plus。Okay， this was about the safe API in rust and。

We are now focusing on the implementation of the Rox。

 so you want to implement a spin lock and then we have to make sure that the spin lock satisfies the guarantees or the specifications of the Rox and we are going to start with a spin lock。

And the spin lock is implemented in this file。And this is an excerpt from this file。

 So in order to look at the every detail of the implementation of the spin app。

 please visit this site and read the code。Okay， and here now look at。

 let's look at the thestructs and the unlock and unlock function for a spin up。

So we already briefly discussed the implementations but I'd like to repeat in order to explain the orderings here。

 So we， we learned the ordering。 So quiet and release orderings。 So here we want to。Here we want to。

Reason about the safety of the spin lock using the acquire release。Ordering on top of it。

 the promising semantics。Okay， a spin lock is basically a boolean value。

 and the boolean value indicates whether the the log is locked or not。

 The true means the the spin is locked and the false means that it is unlocked。AndFurthermoremore。

 this bullolean should be atomic because multiple threads are trying to acquire or release the log at the same time。

 so it should be somehow think。And in order to make a boolean sink。

 you have to use this atomic boolean type。Okay， so far so good。This is an atomic bulloleion。And。😊。

You are。Going to implement a log function like this。 So in order to acquire a log。

 you want to make sure that。Before you acquire a la， the la was a false。 That means it is all。

And right after you acquire the lock， you have to make sure that the lock contains the true value because you just acquire the lock。

That means that the log function should atomically replace the false value with the true value。

So that is the purpose of this comparing swap function。 So comparing soft function is atomically。😊。

Replacing the value from false to true。So that's basically the proposal of this law。Then。

And if this comparison swapb is successful， that means that you successfully replace the false value to true。

Then。😊，Oh， you know that you have acquired a lot。And then you can return from this lock function because you are。

 you have acquired lock。On the other hand， mean may be possible that your comparison one may fail because the value there is already2。

 and you cannot replace false2 because the value is not false at。If that is the case。

 you have to loop again。 You have to go to the beginning of the loop and。

And try the comparison stop again。That's the reason why this is called a spinum。 It is spinning。

In the while lo。And it。Only if it successfully replaces the value from false2。

 it will exit the loop and return from this function。Okay， so this is the lock function。

And on the other hand， in unlock function， you are just storing the false value to the underlying value here。

 So you know that。You already acquired a lot。 So you are。

 you know that the the inner value is true already。

And you also know that you are the only one that who knows the value is true because you are you you are quite a log。

 and that means that the others have doesn't hold a log at all。

And that's the reason why you can just store the false value。

AndYou don't need to replace the true to false value because you already know that the value is true。

You， you are， you can just store the false value to the value， the， the inner value inner variable。

And this store。Can help the other threads to acquire a lot because is they are waiting for the value to be false and false is replaced with true and after this thread is storing the false value to the inner variable。

 then the other threads can replace the false value to true。

And and this is the reason why this can be implemented as a store。

A lock function can be implemented as store false。Okay， so first the good。

And the the and the syntax is a little bit different from this code here because in order to make it into one slide。

 I made a very much simplification， but please visit this site and see what's going on there。

 It contains the complete。😊，Implementation that is in valid rust。Also。

 you can notice that there is an acquire in release。Orderings。

And you may wonder what's the meaning of this， why you need this。



![](img/2b0399a247dc7e485119bbc1238c51b9_5.png)

So because already mutual exclusion seems achieved because because it is atically replacing falseitude。

 So there is no way that multiple stress are holding the locks at the same time。



![](img/2b0399a247dc7e485119bbc1238c51b9_7.png)

And you can store the。The false value because you know that you definitely know that you have acquired a lot。



![](img/2b0399a247dc7e485119bbc1238c51b9_9.png)

And。Why， why we， why are these ordering。 So Qui and release orderings are even necessary。

 What is the purpose of this， So I'm going to explain the necessity of this。

 these orderings in the next slide。

![](img/2b0399a247dc7e485119bbc1238c51b9_11.png)

![](img/2b0399a247dc7e485119bbc1238c51b9_12.png)

Okay， this is the short1 notation for the previous slide。And。

And I'm going to explain what's going on in the promising spans when the lock is held and unheld。

 So lock is meant to be protecting data， so I'd like to show you how data will evolve and how data will be protected by the lock using this implementation。

So， suppose that。This bright green thread。 let's say this is straight 1 and the dark green thread。

 Let's say this is thread 2 are trying to acquire a lot。So luck is false at the beginning。

 and let's say that the lock is this message knows the latest value of this data。So it has a view。

 it has a release view， and its view is pointing to the latest value of the。

So suppose that D is also data and some values are written to this location D。And。

 and at the end of the access to the D， the log should be false and the math。

 these false messages release view should point to the latest value of this D。And' a postd。

Stret one has acquired a lot。And recall that in order to succeed in this comparison swap。The。

 you have to。Put them an adjacent message to the previous value。

And it was false and it is not true because you are comparing swapping。 they are false to true。

So that's the reason why we put the T message here。Right after this F message。

 because they should be adjacent。Okay， so fast so good。So， and the purpose of the lock is that。

The T1 should be able to access the latest value of the。Or in other words。

 this T1 should not access the sta value of the。And as a result。

 the T1s view should be updated to point to the latest value of D。

And that's the reason why it should be acquired。In order to observe。

 always observe the latest value of the the location D， you have to acquire。The comparing swap。

And when this is acquired， you are going to acquire the release view of the previous message that is meant to be pointing to the latest value of this D。

And it should be acquired by this log function。Now， after T1 has acquired a log。

 T2 may want to acquire the log， but it will fail because it cannot replace the false value to 2 because the only false value here is already appended by a two message and this T message cannot be cast because it requires the previous value to be false。

And that means that T2 cannot succeed in comparing swapping the value。

 and it will always go to the arrow branch and loop again again and again。

 so until T1 finishes the excesses and unacquis or releases the lock。Okay， now T1 has acquired a log。

 and it is fine， and it will be able to access the data T。😊。

And it will even modify the data as it wishes because it is provided by the log API。

 You are quite a log， so you can arbitrarily modify the data D。

And suppose that the view has been updated to this。

 and this contains the latest value of the at this point of time。

And now T 1 is trying to unlock the the log so that T 2 can acquire the log later。

So recall that the inner value。Its stored with false。 So you're going to。Oh， I'm sorry。

 Id like to first explain the the T 2 case here。 T 2 is also trying to call a log。

 but it fails to cost。 It just reads that the latest value is true。So you know that oh。

 inner is true， so I cannot succeed in class， so you are going to go to the error。

And because it is acquired， you know you acquire the view here because this is released by this message。

But you're not going to。But you're not going to。Acquire the log， so you have to spin here， basically。

 it cannot acquire the log and spin here by reading this message again and again and again。Now。

T1 unlock the lock。 So recall that。You store the false value to the inner value。

 So you create a new message that contains the false value。But at this point of time。

 you are going to release here。So this is meant to be guaranteeing the invariant of the false messages。

 false messages should point to the latest value of the location being。

And that's the reason why you are releasing it。 So before that。Its view is pointing to D。

But in order to transfer the knowledge here， the knowledge that you have already acquired this view and the latest value of these is here。

And in order to transfer。On the view here， you need to release the view to the message。

That's the reason why this released Me view points to the latest value of D here。And also。

 that's the reason why it should be released。 The view on D should be released here。And after that。

 in the same way， T2 can acquire a log。In this case， by app to the， the fourth message。

 and also this view is acquired。And as a result， T 2 also can see the latest value。😊。

Because the latest value here and it is released by the T1 to this message。

 and this message view is also acquired by T2。And T2。It should observe the latest value of this D。

It can not read or write to the previous area here。

So that's basically the proposal of this release and acquire synchronization。

So to summarize the all information that is modified is T1 should be released here to the message。

In the on the other hand， the message view or information should be acquired by the next successful lockin vocation。

And as a result， all the accesses by T1 is ordered before the T2 operation here。And as a result。

 there should be no concurrent operations among this T182。

And that is guaranteed by this release requires synchronization from unlock to the message to the lock function。

😊，So this is basically the meaning of the second line events between luck and all function are transferred via release acquired synchronization。



![](img/2b0399a247dc7e485119bbc1238c51b9_14.png)

Okay， and T2 can access the value D and it may update the view and later it can unlock its log with the latest value of D here。

So this message also contains the latest message of the D here。

It is imvariant when holding the log ur like the latest value of D and also the false message is holding the latest value at that time。

😊，So that is basically the reason why luck and unlock satisfies the guarantee the mutual exclusion and。

The fact is explained in this promise semantics using this diagram。Okay。

 so far we discussed the we revisited the lockxSafe API in rust and looked at the spin lockx implementation and what's going on in the execution of these spin lock implementations on top of these promising semantics。

 so in this promising semantics， you can reason about the safety and the guarantee of the spin locks in this way。

😊，So T1 axises during here are strictly ordered before T2 axises here。

 thanks to the release acquired synchronization from the unlockn to this message to the the。啊。

 acquirere。