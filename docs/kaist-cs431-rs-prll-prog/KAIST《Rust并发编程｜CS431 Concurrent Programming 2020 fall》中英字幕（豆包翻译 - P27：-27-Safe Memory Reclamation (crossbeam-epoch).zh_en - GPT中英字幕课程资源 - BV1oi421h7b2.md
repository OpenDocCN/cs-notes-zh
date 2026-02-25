# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P27：-27-Safe Memory Reclamation (crossbeam-epoch).zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video， I am going to introduce the crossspm epoch Cate， which is the de facto standard。

 the rust concurrency library that is widely deployed in many products， including Firefox。

So Christ me Park is a face foam implementation of epoch past reclamation。

And so if you let solve the videos and the hazard pointers and epoch based recognition。

 I believe it is easy to understand the library's documentation and implementation。

And also the Dxari here， it contains all the documentation for is concrete so you can go there and read the document here。

And it not only describes the implementation details of the library。

 but it also explains the APIs and also a little bit about the algorithmic details of this epo。

 so please go there and read the document and for example， it provides the APIs， for example here。

You can， you can click the the things there and you can read the the APIs of atomic and its APIs functions and examples。

 So we are going to look at the examples and what's going on there。 But for now。

 let's just recognize that there is an。Theres documentation that contains the the examples for each functions。

And there are guards， for example， there are pin and atomic and shared。

 and they are the API the main API of the CR beamm epoch library。

 so please read carefully about shared atomic guard and pin。

And it has been created in 2015 by Aaron Turron。

![](img/c499629267ab2b3e1c0100101e558d91_1.png)

And so it， it， its age is 6 now。6ix years old the library now。

An error started this project to provide a very nice library for the garbage collection work andcur programming。

 and I strongly encourage you to this document as well。

 So it not only implements the garbage collection algorithm and the epo based reclamation algorithm。

 but this library also provides an API that mandates you to use this library safely。

 and it explains a little bit about the effort in this section。And also in the previous。

 in the previous。Section， it also describes the algorithm of hippo based formationation or。

So you can compare this， this， this document and the video I just created before and see what's going on there。

And as I said， this rust API is， is mandating you to use this API safely。 So as a result。

 it created guard and pin and what is called owned and shared atomic。 and they are the。

 they are the fundamental。APpi is for the cross spinm and in order to do your homework5 and6。

 I believe you need to master the API and list。So I strongly encourage you to this document as well。



![](img/c499629267ab2b3e1c0100101e558d91_3.png)

And after reading these two documents， you can now understand what's going on in the examples。

 so this is the stack implementation that is in in the repository our repository here。

 so in the remaining of this video we assume that you already read the document and the trait and the document of Aaron and and now in the remaining of this video we are going to read the implementations of concurrent stack Q list once again and then see what's going on regarding the goch collection。

So this is the stack implementation， and it has a list。 it， it is basically a list of nodes。

And in the push operation， there is no need to think about the， the garbage collection。

 because we are not removing any node from the linked list， and we are not delocating anything。

 We just create a new one， and then it is going to be。

It is going to be propended to the linked list and the solve。And。And here still。

 there is an interesting aspect regarding CRing。 You create an owned pointer that is basically creating an object in the hip。

 but it is exclusively owned by myself。 and it is not shared by the other threads at all。

 That's the reason why this type is called owned。 It's an owned pointer to the hip。😊。

So far second good。 and we try to perform a cus on the hat。

 So we are replacing the head pointer from the original one to the new node here and this that is just created before。

And what is interesting is that this the ownership of this newly created pointer is transfer to this function。

😊，So this function accepts and receives the ownership of the new pointer。

And if this cost is successful， then we are done。 and if this cost is unsuccessful。

 what is interesting here is that the ownership of the pointer you just turned in here。

 it is returned。😊，As Eda knew。As a result， in order to use this even new the new pointer in the next tiation of this s。

 you need to save the ownership of this to the variable that is meant to hold the ownership of the new pointer。

😊，So remember that the ownership to to a hip object is created here by actually allocating an object in the hip。

And this ownership is transferred here， and it is returned back when the cost operation is unsuccessful。

And if it were successful， then ownership is effectively transferred to the shared memory。

 So so we dont need to care， you don't need to care more about the ownership of the object on your own。

😊，And interesting things will happen in the P function。In the P function。

 you are going to read some pointers and finally you perform a class。On the head pointer。

 you perform a custom on the head pointer and replace the original hat to the next pointer。

It effectively removes or detects the original head pointer from the linked list。And as a result。

 we want to。Free this note， but as we discussed in the previous video。

 we cannot do that without care。We need to retire this node instead of immediately frameing the note。

 and this deferred story is basically the synonymous name of the retire。

We deferred the story of this， using the guard。So that is basically the first the second change we made to the example in the previous video。

And I said that we need to delegate limitit the codes where the thread is accessing the shared memory。

 and it is delimited by this pin function and the drop of this the guard here。So， so effectively。

 an active state begins when you pin。The the guard here。

And the active state is finished when this guard is still located probably at this line。

 at this line， the guard is dropped。 and when the guard is dropped， the。

 the the active state is automatically the finished。😊。

So you can think of this API as a wrapper around set active and secent function that guarantees that once an active state is created and it must be somehow。

😊，Some。Inactivated at some later point of time。 So this is an RAII type wrapper around the set active and secent function。

 basically。And what is interesting about here is that this retire function is a method of discard。😊。

And as a result， this differ destroy must be cost inside the active state because it is a method of a guard which is existing。

 only inside an active state， thanks to the RAI type API of this guard。😊，So。Here。

 here is the active state。 And this guard proves that， oh， in line 76。

 we are in an active state because we have a reference to the guard。 So that is basically。😊。

Ensuring that retire function is called only inside the。The， the， the active state。Furthermore。

 these comparison swap and load functions are are given a reference to the guard。

 which also proves that this reading the global memory is executed only inside an active state the fact is guaranteed by the fact that the functions are given a pointer to the guard。

 which proves that we are inside an active state。😊。

The same thing happens in this push function as well。I mean， the we are creating a guard here。

And we don't need a guard at this point of time because we are just creating a new node inside a hip and it is not accessing the shared memory。

Until here， this n is exclusively owned by myself， so we don't need to pin the guard before the creation of this new node。

And creating this after pinning the guard here， we can safely read the pointers because they are effectively protected by the epoch based reclamation implementation。

😊，And what is interesting about this store function is that unlike load and comparison swap。

 it doesn't accept the code function because， because we are not actively creating a new reference to the。

😊，Shart memory。 So we don't need to be given a guard when the store is executed。

If you have a pointer here， head pointer here， and this head pointer is effectively annotated with the scope of the guard。

 which is the duration of an active state， and that proves that this store function is executed inside an active state。

 that's the reason why we don't need to specifically require additional argument of this reference to the guard。

😊，Okay， so far at the higher level level， the pushian path functions need to do something that is related to garbage collection and that is。

😊，Protecting the， the lines of code with the， the， the guard， which， which limits the。

The beginning and ending of an active state。And it is also the limiting the beginning and ending of the active state using the guard。

 and furthermore， instead of freeing the head pointer immediately。

 we are deeper destroying or retiring the head pointer at this point of time。😊。

So they are the differences from the driver's stack without garbage collection with driver's tax algorithm with an epoch based reclamation。

Now， we can see that the。Now， yeah， yeah。 that's， that's so。

 That's the everything I needed to discuss using this stack。

 except that they are explaining a few types。Stack is an atomic pointer to the node。

 and node contains an atomic pointer to the next node here。

 So atomic is basically a type that that can be concurrently accessed。

 So this is the pointer pointer value。 That can be concurrently accessed by multiple stress。

 Thiss the purpose of the atomic。And it differs from O because Owns being the owned pointer。

 no one else is accessing this pointer at all。 So that's the reason why are we are creating a new HIA object at this line of code。

😊，AndFurthermoremore， there are still a different type of pointer that is shared。

 So this head is the result of this load function， and the type of this head must be shared。

A shit pointer。Is basically a reference to the global memory， so this shared is local。

 you can think of you can you can safely assume that this local pointer is shared pointer is local to a thread and when when a thread reads the global memory when when when a thread reads a pointer from the global memory then the temporary temporarily the pointer is stored inside the stack and this shared is meant to hold the pointer to the global memory。

😊，So there are three types of pointers， atomic that can be concurrently accessed， owned。

 which is an owned pointer to the Hva objects and the shared pointer that is。😊。

Temporarily holding the pointer to the global memory。

And this API is designed in such a way that you cannot easily break the rule of the epo Pasallamations。

And， and you can， you can see that by reading the document。

 the two document I presented at the beginning of this video。Now， let's move on to the queue。

 So Q is a little more a little bit more difficult than stack。 But regarding the。

 the garbage collection， they are not， not that different with the stack。So the， the push function。

Its also creating an own pointer and you're immediately turning turning it into an owned pointer。

And access the shared memory。By passing the guard here。The guard is given as a reference because。

And as a result， you can be quite sure that this push function is executed inside an active state。

And as a result， you can safely load the temporary pointers to the stack。

 so as a result of this load， you can get a shared pointer which is temporarily holding the pointer to the concurrent memory。

And blah， blah。 So there are are， are the the， they are。

 So this means that all the accesses to the con memories are executed inside the。An active state。

And so far is so good。 and as usual， the push is not very interesting regarding the allocation because the push function doesn't decate anything。

On the other hand， this path function is a little bit different different， so it does the same thing。

 It is given a guard which proves that this trip path function is executed inside an active state and using this guard。

 it can load the the concurrent memory pointers in order to traverse to the next pointers。😊。

So first good。 And what is interesting is the same here。If you successfully updated the。啊。

Update the head pointer。 You effectively deched the first node from the queue。 and as a result。

 you need to deallocate it at some point of time。And instead of immediately delocating the pointer。

 we are going to def destroy or retire this pointer in order to wait for the other thread to finish accessing the same node。

And after calling different destroy， we are reading the point of value and returning the value here。

😊，So that is basically basically what's going on in this stack。

 and it is pretty much pretty much the same with the stack regarding the garbage collection。

You protect the functions with the guard， which proves that the function is executed inside and。

An active state。 And further， you free you， you differ。

 destroy or retire the blocks instead of immediately freeing it。The same at toll。

And there is a little。A little bit。Funny things here。So， so here in drop function， you are trying to。

 to top the values until the the the Q is empty。And this function must be called inside an active state。

 So here we are going to give a guard to that， but the guard is an unprotected guard means that oh。

 even the even though you have a guard， you are actually not inside an active state。😊。

But this is actually correct implementation it first at first glance in maybe it may seem like wrong。

 but it is actually correct because at the time that queue is delocated and at the time that the queue is dropped。

 you are quite sure that only you are aware of this queue。😊，No one else。

 no stress else are trying to access this queue at all because they lost all the reference to the queue。

 and its the reason why this drop function may be called for the queue。

So you are you are the only one that accesses the shirt map the nose inside this Q。

 and as a result you don't need to protect your accesses at all That's the reason why we are going to call unprotected instead of the pin and this unprotect function means that you are not actually inside an active state。

 but I will give you a guard regardlessly because you need it。😊，But still。

 it's safe due to the exclusive nature of this， this draw function。Okay， so for a second。

 and list is also the same。😊，有。You are given a guard。 And like as usual， in the draft function。

 you are not going to need a guard the real guard that that signifies the active state。

And here you're having many things。 and that the same thing happens at the beginning of iteration。

 you need to get a guard by pinning it。Because you need to protect your turbosil。

And at the end of the turousore， you need to drop the guard in order to mark the starting of an inactive state or ending the。

 I mean， marking the ending of the active state。The same thing happens for the rest of the code。

And for homeworkock 5， you' are required to implement a few data searches and that collectively implements the Kg hassh table。

And I hope that you， you now understand how to do that， how to protect the， the， the。

The deal location or inside the。Inside the conquer hash table。

 when you begin the access to the conquer memory， you create a guard by pinning it。

And after you finished accessing the shared memory， you drop the guard。

 which effectively calls the set crescent function。😊，And only inside those the， the active state。

 you can safely dereence or reference the shared shared memory。😊，And if you want to delocate a node。

 then instead of immediately freeing it， you need to def destroy or retire the block in question inside an active state。

So that is basically the higher level recipe for protecting data structures using epo based reclamation。

 and I hope that you now quite well understoodtit the how to do that for Con hash table。😊。



![](img/c499629267ab2b3e1c0100101e558d91_5.png)