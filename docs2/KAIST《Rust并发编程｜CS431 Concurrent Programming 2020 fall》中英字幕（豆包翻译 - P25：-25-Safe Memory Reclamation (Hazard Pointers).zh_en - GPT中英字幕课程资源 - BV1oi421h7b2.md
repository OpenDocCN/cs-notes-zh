# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P25：-25-Safe Memory Reclamation (Hazard Pointers).zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video， we are going to start studying the issue of garbage collection in concrete programming。

So in the previous lectures on Concorne data searchers， I already said that in concurrency。

 we need to take into account the possibility of concrete stress in collecting garbages or collecting no more used memory locations。

So in this lecture and from now on， I'm going to focus on this particular problem of memory clamation in concurrency and propose a few representative algorithms for garbage collection in concurrency。

So the most of the slides are prepared by your TA in Taiwan and so he shared the slides with me and that's the reason why I could。

Here is this slide in this video lecture。Okay， now。First things first。



![](img/c78565e75a514add4b42d52603be1d6e_1.png)

All these first things first so let me start with the concurren structures in general。

 so this is a linked list so you already know well about this link list and there is a head pointer and the head pointer is pointing to the first node and the first node is pointing to second node and on and on and on。

So， they。As he already discussed pretty extensively。

The benefit of this concurrency in data structuress is that multiple threads can act the same data structure at the same time。

 and as a result the performance can be optimized and furthermore。

 it is nonbing in the sense that even though the other threads are working on the same data structure。

 I can finish my operation，If my operation and the other operations are not conflicting with each other。

So in that sense， this is a non blocking， so I can finish my operation even though the other threads are concurrently working on the same data structure。

Okay， this is the benefit， so here's an example， the T1 and T2 are the two thrusts and they are executing the instruction removal operation for the same linked list。

It can be done in perial because they are modifying a different part of the their and as a result。

 their modification is not conflicting with each other。So fresh us are good。

And let's say that T1 removes the value0 by updating the hat pointer from the first node to the second node。

And similarly， the T2 is removing effectively removing 20 by updating the next pointer of this1 to the later one here the null pointer in this example。

Okay， and after unlinking the nose 0 and 20 or after detaching the nose 0 and 20 from the ni list。

 we want to finally decate the memory location。Because it is no longer inside data search。

 so we eventually need to reclaim the memory。Otherwise。

 the memory consumption will spike high resulting in some very bad system behaviors。Okay。

 so we want to free， actually call the free function for these applicationss。However。

 the problem is that the we cannot free the blocks immediately。

So we already deal with the data searchers and it already has a significant complication over sequential data searchers and this existing self garbage collection or the requirement of this garbage collection is。

Is adding much more complexity to the already complex design of conquer the a because of this rhythm。

So if the node zero and node 20 are immediately delocated。Then there is a problem。

 The reason is that。Maybe the con thrust may access the the node 0 and may access the node 20 at the same time。

 concurrently。And because of the possible existence of those threads that access the same node。

 the nodes 0 and 20 must not be ded immediately。So let me explain it in more a more detailed example here。

So okay， suppose that the block B is going to be removed from the data searcher。But for now。

 let's assume that T1 is concretely accessing the same node B。

 and it it has a reference to or it has a pointer to the first node that contains the value0。

And then this node0， this T1 is going to sleep。Because of various reasons， for example。

 it wants to do some IO or it is maybe the OS scheduler doesn't like to give a slot for this T1。

Anyway， T1 is sleeping now。And at the same time， assume that T2 has just removed the node0 by updating the head pointer from 0 to 10。

Okay， so if。We remove and then immediately free the blog。Then the block B has been free。

And as a result。T1 may wake up and then access the freight block。And as a result。

 it is causing a huge after free bulk。So user after to free bug is a very bad thing。

 the programmers should not invoke and should not incur user after free otherwise。

 if there is a use after to free in the program， the dismats of the program is undefined and as a result the computer can do anything once。

So that is a very bad thing， so we have to avoid this。

The more of the survey is that if T2 is springing the block right after it is removed。

Maybe the remote block have been referenced by the another thread and the another thread may invoke user after free。

Okay， so in order to prevent such a bad thing， in order to prevent such a use after free error。

 we need to do two things， so we need to somehow synchronize multiple stress in such a way that they do not incur use use after free even for those blocks that has been detached from the linked list or other data searchers。

And in order to design such an algorithm， we usually focus on two aspects。

The first aspect of the algorithm is this。Q1， How do I protect B from being freed。

 So from T1's perspective， T1 wants to access the block B after waking up。

So the sleeping may not be caused on its own， maybe it is prim。

 so it doesn't know whether it is going to be slip or not， but T1。

 what is definitely true is that T1， regardless of whether it is cooperativeively or primemptively sleeping。

T1 later wants to access B。That is the fact that doesn't vary。 so we need to somehow say that， oh。

 T1 and from T1's perspective， we want to say that， oh， I want to access this B at some later time。

 so please， please do not delocate the block B without me being noticed。

So that is basically the Q on how do I protect B from being freeed。

 I need to protect B from being freeed and the question is how to do that。

And the other aspect of this algorithm is the T2's perspective。

Here the Q2 says that when is it safe to free B？Okay， so far second。

Let's say that many other threads say that if some thread says， oh， I'm going to access the block B。

 then it should not be the case that this T2 is framed November block。

But then how to determine whether the older the threads finished accessing the block B。

Only after all the stresss finishes accessing the block B， T2 may safely free the block。

 so T2 is very interested in knowing when is is safe to free the block B。So。This isそ yeah。

It is always safe to free the block B if no one is coning accessing the block B。

And it is true if all the other threads finished accessing the block B。

 so we need to somehow figure out when all the other threads finished text accessing the block B for answering this Q2 question first thread2。

Okay， so the answers to such questions， Q1 and Q2， how to protect the blocks and how to safely free the block。

 and answer to those two questions are usually called the Sa memory Relamation algorithms。So here。

 even though this word these are the three word phrases， it doesn't contain the word concurrency。

 usually the safe memorylamation problem is connotated with concurrency。

Because in sequential program， it is usually called memory leak or memory。

Uual the free bulk but this safe memory informationemation is much more difficult and much more interesting in concurrent setting。

 so that's the reason why when youre saying， oh I'm working on some safe memory accommodation algorithm。

 it is usually meaning that oh， I am working on concurrent garbage collection。Okay， so first good。

 so we need to answer those two questions how to protect and how to know when it is safe。



![](img/c78565e75a514add4b42d52603be1d6e_3.png)

Okay， so there are a bunch of algorithms that has been proposed so far and。

So this problem has been known for decades more to put the case and the formal papers about the algorithms about this SMR has appeared since 1990s。

 early 1990s and it has been already3 years or more in the academic literature and in the industrial literature。

 it dates back to much much earlier， for example， even in 1960s or 70s， people already know。

 oh there will be a problem in concurrent collection。And okay。

 so there are many solutions proposed so far， and we can roughly classify those into two categories。

 the first category is what is called hazard pointers。

 and the other category is usually called Epo based memory limitationsations。And actually。

 many proposals that has been proposed after hazard pointers and input based recommendationss are a combination or hybrid or variations of the two schemes。

So these two hedging pointers and input based recommendations are usually indeed the most important algorithms we should learn in this concurrent course。

Concurs course。Okay， and now I'm going to focus on the two algorithms a little bit more。

 So I'm going to tell you a little bit about hydro pointers and then hippo basedlams in this course。



![](img/c78565e75a514add4b42d52603be1d6e_5.png)

Okay， the first algorithm is Hader pointers and let me explain how to somehow synchronize multiple stress for Concur gauge collection by answering the questiontion on and questiontion 2 I introduced you just before and this is the Hader pointers answer。

So how do I protect B from being freed So in order for， for example。

 thread1 to protect the black B from being freed， then head pointers do a very simple thing。

It just writes down the block B in its own list of protective list。

So the API for that is what is called the protect function。

 so you at the beginning of an operation or just before accessing a pointer。

 you first need to declare that oh， I'm going to reference this pointer。

 so before that I want to protect the block。So that is basically the API of this project B。

Before dereferencing the block B， I need to protect it so that the other threads are not going to reclaim the same block concurtly。

So first second good。And heading pointers answer for Q1 is calling a Pro B。

 which in turn is writing it down in its own list of protected list， I mean protected pointers。

And these protected pointers are also called hazards because it is hazardous to reclaim those blocks。

 So that's the reason why this technique is called header pointers。

 So it is synonymous with the phrase protected pointers。And historically， it is usually called ta。

 so that's the reason why this algorithm is called hazard pointers。

 but actually I prefer the name the other name protected pointers because it better conveys what is actually going on in these pointers。

So I hope you know the two names not not， I mean， you I hope you know the two names and Hedge Poer is a historical name and it is the standard name actually。

And project pointers is the name that conveys its main meaning a better。Okay， so for a second。

 and let's assume that all the threads has already written down the list of protected pointers that it will undergo id access or dereference。

Now let's move on to the Q2， when is it save to free of block B？

So let's assume that you just remove the block B from the link list by performing some costs or some other atomic operations。

And now we want to somehow make sure that this block is not concurrently accessed by any threat。

So in order to do so， what we do is that。Oh， we read the list of protected pointers of all the stress。

And if B is not contained in any of the list。That means that the block B is no longer protected by anyone。

In maybe the case that one no one protected it in the past。

 but even if some stress was accessing the same block B， then it is guaranteed that， oh。

That the stress has finished each operation， and the block B is no longer accessed。

Provided that the list of the protected pointers of all the threads。

 is it is not containing the block B。If the protected pointer list contains the block B。

 it effectively means that the block B may be concurrentently accessed by the the other stress。Okay。

 so this is the simple answer。 So that's one of the reason why H pointer is what the or SMR algorithm that has been proposed so far。

So the， the answers to these two question is very simple。

 You write down the protected pointers in some， some lists， and then you read it。

 you read it and determine whether some block will be。I is safe to delocate or not？So far so good。

And let's see an example here。In the Had pointers。Suppose that this T 2 T 1 is I 13 over the linked list。

 and it just picked the。The block B。And it needs to protect the blockbe before dereferencing the block B。

 So if you want to traverse to the next block， you have to dereference the block B。But before that。

 the T1 needs to protect the same block just before dereencing it。

That's the reason why it is protected before accessing the next node。And at the same time。

 let's assume that T1 is just going to sleep and T2 has been removing the node with value 0。

By updating the head pointer from the node 0 to node 10。And so that good。And T。

And record that T1 would have a letter written B in its project pointer list。And。

T2 is try to deallocate the same block。And it needs to determine whether it is safe to free the plug Pe or not。

In order to know that it just reads the perfect pointer list， but in order to do so。

 it has to signify its intention that oh， this block B is removed from the data structure。

 so we want to delocate it。It may be possible that it is concurrently accessed by the other threads。

 but anyway， regardless of whether it is the case or not。

 we want to actually free this block at some point of time。Maybe it is not now， but later。

 at least later， we want to dealcate the block B。So in order to signify the intention。

 there is another API that is called retire， which means that。B is detached from the link list。

 so we want to ret it。But please do not delocate the block immediately because it may be possible that it can be reused later。

So far as second could and。Yeah， retire。And you retire the block B。

And now T2 or the other threads want to actually delocate the block B because it is retired。

 it is no longer in the data structure， so we want to delocate it。

But in order to determine whether it is safe to do so。

 we are figuring out the list of the set of blocks that is retired。

 but it is not currently protected at all。So they retired， but non protected pointers。

 those are subject to reclamation。All the other pointers should not be reclaimed。😡。

If it is not retired， you should not reclaim it。😡，If it is retired。

 but it is concurrently accessed by the other threat， you should not deal it。So that's the criteria。

 Those pointer studies are retired， but it is that is no longer protected。

 They are subject to collection。 they are safe to free those locations。

And this kind of job is usually called by a collect function， which may be called by any thread。

 and in this collect function， we list up the retired pointers and figure out which pointers are not protected by any thread。

And those blocks will be delocated in this collect function。So far second。

And I supposed that T1 finishes accessing the block B。For example， it already read the next pointer。

 and after reading the next pointer， this note， it doesn't need to read the block B again。

 So that's the reason why。We can call a function that is named。Unproect。

Which signifies the fact that， oh， B was a protected pointer。

 and we now no longer want to protect it because I finished accessing the blockbe。

So first second good。And by as as， as an effect， this unprotect removes B from the list of property printers in of of the same threat。

So。If you call the collector again， then you can safely delocate B。Because it is already retired。

 but it is no longer protected by the the threat T1。 T1 is called unprotect B。

 which means that the block B is no longer。No longer。Necessary to。Yeah， that。

So that's the reason why we do that so we areproed and as a result。

 T3 or any other threats may be able to delocate it because it is retired but it not protected。Okay。

 so as a result， T3 just has free the bugby。

![](img/c78565e75a514add4b42d52603be1d6e_7.png)

So first second could。And。Here's an example， Here is the triverse stack that is in a slightly different style than one that is written in the repory。

 but it is actually the same algorithm， is it has omitted the ordering but that except for the syntical differences and the ordering differences。

 they are actually the identical with the tri stack in the repory that is already discussed in some of the earlier videos。

How do we apply hazard pointers in this example， So that is basically the topping of this slide。

And recall that the line 16 is unsafe because it is to access the next node it is trying to access the next node by dereencing the current node。

 but maybe without protection， maybe this node has been reclaimed by this free function at line 18。

So to protect it， we insert the three lines of code just before the line 16。So let's read it。Le。

 I'd like to protect the block B。And then I'd like to reread the pointer。

Poiner that I So you want to protect cur and cur is loaded from this。 this is head。

And after protecting this current pointer， you need to make sure that that is still remaining in the main memory。

So in order to do so， after Pro， you read it again。

This is the very pointer that has resulted in the the value。And by doing so， we are reloading it。

 and if it is different from the current pointer， then you just spell out。We just begin from a game。

 so it doesn't harm because we are going to go to the beginning of the loop。

 ignoring all the intermediate competitions。And if this condition is mad， I mean this equality holds。

 if the memory still contains the current current nose pointer， then it is the case that， oh， oh。

 I'm still in the data searcher and and I'm safe to。Protect that I。

 So it was safe to protect the blood。 It it did not occur。And after this check， the current is。

Actually， firmly protected by myself。And as a result。

 I can access I can de reference this current note right after this Australian zip。And also。

 after finishing accessing the node， I need to signify the fact that， oh。

 I finished accessing the location and that location is no longer unnecessary to be protected。

So that's the reason why we call unprotected curl here。

KurR was protected in line these three lines of code and curve is accessed here at line 16。

 and after that we want to just signify the fact that we don't want to bother more so we are calling unprotect K。

And the contract here is that after onprotect B， unprotected occur， you should not。

Access occur again without the protection in play。So， first so good。And finally。

 we need to replace this free or with all this got to retire。And as I explained quite extensively。

 you should not call the free immediately， you have to make sure that all the other threads are finished accessing the same block。

 and that's the reason why we need to do free， I， we need to do retire instead of immediately freeing it。

🤢，So in effect， this retire is just。Writing down my writing down my intention that this curve must be de at some point of time。

 but in may be the case that it is not now we need to wait a few threads finish accessing the same。

Note。Okay， so it is everything we need to do for the driververse stuff。

We need to protect pointers before dereencing it， and we should not forget the unprotecting the local pointers because if it is remaining in the program。

 then the locations or blocks are protected more than necessary， that will degrade the performance。

Anyway， we can easily transform a tri stack into a head pointer protected tri stack by inserting this three3。

Aspect。But you can see that this API is a little air prone。

The reason is that you need to make sure that the you need to make sure that what is currently the is I actually protected before and you want to somehow make sure that is satisfied without。

啊， yeah yeah。Yeah。And further， you need to。Validate the fact that the pointer curve is still there。

It is a little bit unintuitive。 And so it is actually the requirement of the hazard pointers。

 but it is often。Often forgotten by the。The users。So there are some approaches to mitigate the problems of this too。

 the first problem is that we may forget the protection。And the second problem is that we may forget。

The the。Validation of the the pointers in the hydro pointers。

And the rust program language can be used to mitigate such problems by designing a better API。

 for example， we can make an API of pointers in such a way that without protection。

 you cannot de referenceence it。It is mandated by the Was program language。

 we can design it in such a way。And further， the you need to act the reference occurred only after the validation and this idea of validation may also be。

啊Yeah。Also be incorporated expressable， expressed on top of the Ro touch checker。

 That's the reason why we can design a safer API inside Ro that automatically satisfies that。

That house automatically satisfies some of the requirement of the header pointers。But still。

 there are a few more things to do， a few things that the RoOS compiler can now automatically automatically reason about。

And in such cases， we need to sum out manually。Reason about the the。The this usage of head pointers。



![](img/c78565e75a514add4b42d52603be1d6e_9.png)

Furthermore， hidden pointers has more drawbacks， and the first drawback is that it is actually not a very fast。

The reason is that it needs to issue a very expensive fence for each iteration of data structures。

 so for example， in linked list， if you want to traverse to， for example， the followingaway node。

 then you need to somehow follow the nose from the head pointer to the target。And。

And the problem is that pager pointers insert a very expensive fence for each acceleration。

So the synchronization so the defense is used in order to synchronize with the collect function。

 so record that collect function needs to read the set of protected pointers in order to make sure that the pointers。

 it will free emit right after iss actually not protected by any thrust。And to do so。

 this protect function and this collect function needs to synchronize it with each other。

And that synchronization is achievable only with the。

The very expensive fence in the current hardware， that's the reason why H pointer is usually very not fast。

So， yeah， so this expensive fence's name is Storeal fence。

 which means that the store and a later laws should be ordered， I mean。According to the。

The program order。And you can safely think of it as sequentially consistent fence because all the fences that satisfy this property external fencing is actually the biggest fence and that is actually sequentially consistent。

F in the CN C plus post technology。Okay， so let's see this animation once again， so。

In each iteration， it needs to issue the fence and that's the reason why the fence should be issued for the length of the list times。

So we see that very fast。So empirically， header printerers are usually assumed to be slower than the other alternatives by three times。

 so that is very， very bad we can utilize only 30 or 40% of the entire bandwidth or capacity when using these header printers。

And the second problem is that actually these head printers is not widely applicable to many dataers。

That means that there are many data searchers that cannot be implemented with hydro pointers。

And let me explain why， so one of the representative examples of that is what is called a change retirement and in this example。

 so T1 is protecting the block， the first block。And let's assume that T2 has been removing the first and the second block at the same time。

By performing cuts on the head pointer from the original head pointer， 2D， the block block 2 B2。

If that suppose that happens， and let's see what will happen。

And this T2 is going to protect the two node。B 0 and B1。 they can be retired。

 The reason is that they are no longer approachable from the linked list and because they are just unlinked or detached from the diacer。

So we can safely retire those B0 and B1， or at least we imagine that we should easily retire this B0 and B1。

Okay， so press good。And now supposed we involve the collect function。

And recall that this collect function actually phrased the memory blocks that has been。We hired。

 but it is not protected at all。And surprisingly， we won satisfied this criteria because it is retired as as a part of the change retirement。

But it is not protected yet because T1 only protects the block B0。

And B1 is beyond the imagination or beyond the reach of the T 1， because the。

 the T 1 is currently accessing B0， and it doesn't know anything about B1。 So it is very。

 So that's the reason why B1 is。Retired， but it is not protected， and as a result。

 it can be reclaimed in a concurt clock function。Suppose that B1 is free now because there is a correct function that invokes such changes。

But now the problem is that。T1。T1 protected B0， and it it wants to traverse to the next node。

 and T1 will access B1。 and they reference the content of the1。

But it is going to be used at free because B1 has already been freed by T2 before T1 advances to the next node。

the more of the story is that， oh， B1 is very strange。 It is。In the algorithm of hazard pointers。

 we need to be able to delocate the blocks。But however。

 actually delocating it may incur a lot of problems because maybe there are concurrent thrusts that is accessing B0 that will traverse to be1 without asking the other thrust。

So it is problem and that's the reason why this example is not supported by hydro pointers。

And this actual， this example that I call a chain retirement。

 it is happening many times in the realroad data concur data structures。 So as a result。

 head pointers is A pointer applicability is significantly limited and it can be applied to a few simply algorithms only and if multiple locations are are modified at the same time。

 the。I mean， multiple nodes are changed， for example， removed from the data search at the same time。

 and we cannot use the header pointers technique。Okay， so far so good。And。And。



![](img/c78565e75a514add4b42d52603be1d6e_11.png)

So in the next video we are going to resume from the next algorithm。

 the epoop based reclamation algorithm， or shortly EBR and this EBR solves the three problems of hazard pointers。

 it is easier to use and it is much better than hazard pointers and it is much more widely applicable than hazard pointers。



![](img/c78565e75a514add4b42d52603be1d6e_13.png)

And it fixes all the problems of hazard pointers， but by sacrificing some of the most important criteria for this SMR。

So in the next video， we are going to study this EVR and discusses the pros and cons of the hedge pointers and epo based formations and somehow I'll discuss compare those two in。

In a qualitative way。

![](img/c78565e75a514add4b42d52603be1d6e_15.png)