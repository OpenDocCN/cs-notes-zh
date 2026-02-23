# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P26：-26-Safe Memory Reclamation (Epoch-Based Reclamation).zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In the previous video， we studied the hazard printer algorithms in order to safely reclaim the memories in the Concur data structures In this video we are going to study a safe memorylamation for concur data structures。

 but we are going to study on what is called epoch based through coation algorithm for this SMR problem。

So recall that header pointers has a few featured trimings。First， it is difficult to use。

 Each API is a little bit difficult to use。 And the second is that it is not fast due to the fences for each iteration。

And third， it doesn't support a few。Or in useful synchronization patterns in the concur programming。

 for example， the chain de is not supported in header pointers。This EBR。

 where epoch based reclamation is trying to solve all of the problems。 So it is fast。 It is。

It is supporting the chain retirement and other patterns and also each API is a little bit easy to use。

 so all the homework on implementing concretecurne dis will be will be using these EBR rather than hazard pointers or other schemes in this course。

Okay， let me explain EBR in a little bit more details。

 so recall that all SMR algorithms need to answer two questions and the first question is how do I protect B from being freed from the access point of view？

And the second question is when this is safe to free the B from the modifiers perspective。

 so these two aspects are synchronizing with each other and if it is correctly done we can safely reclaim the memories after all the accesses are finished。

😊，So so this in order to answer the first question， in order to protect B。

So the thread is calling on what is called set active function。So in EBR。

 the set active function is protecting all the pointers that I'm going to access from now on。😊。

In this sense， it is a blanket protection。 It is not protecting a single pointer。

 but instead it's trying to protect all the pointers that it is going to use from from now on。

So this is illustrating what's going on here。 So it is。Protecting all the threats。 I mean。

 all the pointers by calling se active by the threat one。And since it is protecting every pointers。

 you can safely iterate through all the blocks， so you can itrate to be 0 from the head pointer because it is protected by this blanket protection of set active function。

😊，And you can also travel to the next pointer without worrying about safety because B1 is also protected by the blanket protection。

And B2， as well。So far second good， so it is protecting all the pointers at the same time。

And you can immediately see that why this is say this is fast。

 The reason why this is fast is that we don't issue the the defenses。

 expensive fences for each iteration。We may have to issue fences at the beginning of the set active。

 but after calling the set active， the I trading through all the node inside this linkists。

 they doesn't incur the cost。On the other hand， the， the from the modifiers perspective after。

For example， detaching B from the data structure， it needs to call the free function for this block B。

And when is it safety to do so when the the， the， the answer is that if B cannot be accessed by any active threat。

 So let's say that a thread is in active state if it is calling， it has called set active。So， if。

No active state。 I mean， no active threats are accessing B。 Then we can。

 It is quite true that B is no longer protected by anyone。 so we can safely delocate the block B。

So suppose that T1 just removed the two blocks B0 and B1 from the linked list by updating the head pointer from B0 to B 2。

And it it may call retire function because B 0 and B1 are detest from the link list。 So it is。

 it must be delocated later。 So for now， we are just marking them， oh， these nodes are retired。

 so please。Place a deal。 look at them at the later stage of execution。So fsco。😊。

And now the collect function wants to delocate those that are retired， but it is not protected。

For now there is no such pointers because even though B0 and B1 are retired。

 they are protected by the T1s active state。They are protected in a blanket manner。It it， it。

 the T 1 doesn't specifically protect B 0 and B1。 It just protects every pointers it is going to access。

 So that's the reason why specifically B0 and B1 will be protected。

So that is basically what's going on here。And now after T1 finishes the iteration of this linked list。

 it is calling set crescent function。 So let's say this is an output of set active。

 so it is finishing the active state of the thread。😊。

It signifies the fact that T1 is no longer accessing the blocks。

So that is basically the meaning of that crescent。 It is synonymous to set inactive and it is finishing the ongoing active state and say that it is not going to access the shared memory blocks。

😊，After set crescent is called， the collect function may free V0 and B1 because they are retired and they are no longer protected by T1 anymore because T1 already called set crescent that means that it doesn't protect all the pointers in a blanket manner and in particular B0 and B1 are no longer protected。

😊，So as a result， a collect function may safely decate or free those 2。er speed0 and B1。Okay。

 as I said before， it is fast because inside T1 side duration。

 it doesn't need to call the expensive fence all the time。

So each iteration doesn't incur any synchronization f because already all the pointers are protected in a blanket manner。

 so you don't need to protect more pointers at this point of time。😊。



![](img/613dd11b2d8ff6788756b6d8d8272215_1.png)

Furthermore， I mean。I mean。In more details， you， you may need to issue a fence when the set active function is called。

 But after the set active function is called， you don't know。

 you don't need to issue additional offenses in its iteration。

The second benefit is that it is widely applicable。

 and in particular it is applicable to the change retirement， as synchronization pattern。So if。

 as we saw in a previous example， even though B 0 and B1 are retired at once。

 we can safely I T 1 is safely it trading through T B0。

 B1 and B2 on and on because B1 is also protected by the set active function。😊，And as a result。

 even though B1 is not traversed yet by T1， it is not going to be delocated by the T2 or the collect function。

That's the reason why it is safe for T1 to enter through this chain retired nose。

So including the chain retirement patterns or many other patterns that you can think of in concurrenent data iteration or travool。

 they are protected by the epoch based reclamation。And at the high level。

 the reason is it protects all the point potential excesses in a blanket protection。😊。

That's the reason why it is widely applicable to many concurrent data structuress。And furthermore。

 it is easy to use， easier to use than pointers。And let me explain that in another video when I will explain the API of the CRpimpoC。

 which is an implementation of this EBR algorithm。So far so good。

 And now we need to answer in a little bit deeper way。

How T 2 or the other threads can deduce that B cannot be access by any active state。

So how to decide that， I just said that T2 or a collect function needs to decide whether B can be cannot be accessed by any active state。

 but it somehow needs some algorithm， you cannot know that from out of the nowhere。

 you need to somehow deduce this information by observing the other threat behaviors。😊。

How to do that。 That is the question I'd like to answer in the next slide。



![](img/613dd11b2d8ff6788756b6d8d8272215_3.png)

So the high level idea of this epoch based reclamation synchronization is the epoch consensus。

 So epo consensus means that。😊，First of all， each thread is marking。Where it is going to。

 where it is going to start accessing the concurrent blocks and where it is going to finish accessing the concurrent blocks and it is called set active and seescent as we saw in the previous slide。

So only after set active function is called T1 may be able to access the shared memory locations。😊。

And after that Cucent is called， it no longer has it should not have the pointers to the shared memory any longer。

So this mouse the range in which the concured data structures are accessed。

 and you can save the pointers to the coned node in a previous active state and use it in a later active state。

😊，So in that sense， the active stage are completely separable。And。

 and pointers are not going to be shared among multiple active states inside the same thread and the other stress。

So first are good。😊，And further， it active state that is the range between these exact active and sequestcent invocations。

 they are annotated with an epoch。😊，Epoch is basically meaning a timestamp。

 So it is a natural number， for example，10 or 11 or 100。

 So it is a natural number that begins from 0。And each active state is annotated with an epoC。

 So it is assigned automatically by the algorithm。 So you don't need to worry much about how to assign them。

 But if you want to actually implement this epo based reclamation。

 you need to somehow come up with an algorithm that determine the epoch of a new active state。😊。

But anyway， at this point of time， let's assume that epochs are just designed for each active state。

😊，And furthermore， the final rule and the most important rule is thispo consensus rule。

 which is that epochs of the concornective states， they may differ only by one。So for example。

 this T1's active state and ti2's active state are overlapping and they are concurrent because there is a time at which T1 and T2 are executing at the same time。

😊，I mean， their active states are executing at the same time。Therefore。

 T1 is active here and T2 active here should differ by M1。😊，It should not defer two or3 or bigger。

 So T2 is epochbu P either E or E plus1。So that's the。

 the consensus rule we are going to have for each active state。And furthermore。

 t3 must be E or e plus1 because t1s active state is overlapping with T3s active state and they should differer by m1。

 and so it can be e plus 1， for example， it cannot be plus 2， however。😊，On the other hand。

 T2 is next active state。 It can be annotated with E plus2 because there is no concurrent thread or no concurrent active state that is annotated with E fogg E。

 so the epoch may advance to E plus2 at this point of time。And T4。

 it is going to can be annotated with the plus 3 for the same reason。

 there is no concurrent active state that is assigned with the plus1 epoch。

So the first part of the algorithm， the first part of this epoch based reclamation algorithm is actually assigning epochs to its active state that satisfies this epoch consensus rule。

 concurrent epochs or epochs of concurrent active states may differ by n most one so that is the golden rule of epoch based reclamation and without this we cannot guarantee the safety of the algorithms so it is at the heart of the safety of this epoch based reclamation algorithm。

😊，And now after observing this consensus rule， it is very easy to answer the question too。

 when is it safe to free the block B？😊，So suppose that the block B is retired in an active state with Epoch E。

 for example， in this active state。So by assumption。

 we have to make sure that all thecurrent data concurrent memory blocks will be accessed inside the active states and as a result。

 this plot B must be detached from the data structure and retired in the same active state with an IpoC。

 for example， say E。😊，So first second。 And the answer to this question， too。

 When is it safe to spl free B is。😊，At an epoch， E plus 3。

So it is very simple if it is retired at depog E， then it can be freed at Epog E plus 3。

So I plus 3 is a little bit magical in the sense that three comes from nowhere， but。😊，You can， I can。

 I can I can explain why plus 3 is actually safe using this diagram。😊。

So in Epoch E+ 1 or earlier in an Epoch E or E plus 1， you can still reference the plug B。

Because the， the fact that B is removed from the data search or deestched from the data search。

 this information has not yet been。A propagated to T2 or T3。

It may be possible that even though T1 already removed the block B from the concurrent data structure。

 T2 or T3 may reference the block B。😊，Because these active states are overlapping。 and as a result。

 it may be possible that T2 and T3 may get the pointer to block B before it is removed from the concurrent data structure。

😊，However。In an active state that is annotated with E plus 2。

It must not be the case because this T1s active state。Must happen strictly before a+ 2。

So by the epo consensus rule， this T1's active state and T2 second active state must not overlaplie with each other。

😊，In other words， the T1s end or slip questioncent function is strictly happening before the T2s beginning of this hip active state。

By the invocation of set active。And as a result， all the analogs gathered in the T1 active state must be transferred to T2s a second。

😊，Active state， for example， via release acquired synchronization。

So that is basically the guarantee that is imposed by this hypopo consensus rule。😊。

Because they are so by having a counter positiveitive statement of this。😊。

Because their epochs are differing by 2， they are not concurrent or in other words this active state must happen before this active state and as a result this removal should be obable or acknowledged in tus active state。

 the second one and as a result B must not be reachable from this active state。

 this active state must not know the occurrence of the existence of the pointer B because it has letter been removed from the data structure。

😊，So far are good。 So there is a key difference between the epoch E plus 1 and E plus 2。

 E plus1 may reference B and E plus 2 may should not reference the block B。

And let's say we are in an effective state A plus 3。

And suppose that we invoke the correct function inside is C plus 3。

So this is very much possible because a color function may be called arbitrarily by each thread。

 and let's say that it is involved inside an active state that is annotated with aposttry。😊。

And you can see that all the references that happens in active state E plus 1 or earlier。

 they should happen before this active city+ 3。😊，For the same reason that Act state D plus 2 happens happens after the Act state E。

😊，And for the same reason， the active state+ 3 must happen after all the active state plus1。

And as a result， we can see that all the references to B， they must happen before equal 3。

So in particular， all the D references to the B must happen before the beginning of a plus 3 active state。

And furthermore。AndIn a conquered thread， for example， here。

 all the coned threads must not reference the block B anymore。😊。

Because there epoch must be N C plus 2 due to this consensus rule。

 So we have an epochy plus3 and as a result， all the concurrent stress must have an epoch that is greater than where you equal to E plus 2。

😊，And for the reason I just explained in just before the all coned rat， for example。

 the Epo with the Epog E plus2， they should not reference the block B。😊。

And all the references to the B must happen before the beginning of the C plus 3。

And that's the reason why we can safely decate the block B in a collect function at plus 3。😊。

Because all our reference， we just proved that we somehow pictorially proved that all the reference to the block B must happen before the beginning of thepo+ 3。

And that's the reason why is it is safe to delocate the block at the active state width。

Epog E plus 3。So at at at the first glance， you may see that this C plus3 is very much。

 very much magical。 This3 is a very magic number， but you can now see that actually it it has a reason。

 So the reason is this diagram so you can now I believe that you can understand why the block B。

 you retired that E can be collected in E plus3 in this diagram and in more general in arbitrary execution。

 As far as this Epo consensus rule is satisfied by the oldest stress。😊，Actually。

 there are many variants of this hip based reclamation and in some variation this number may differ as the algorithm and the consensus rule may a little bit differ and as a result the rule can differ a little bit。

😊，But for now， let's assume that we are using this specific consensus rule and this specific rule rule for the free function。

 so。So as far as we are observing this consensus rule。

 E plus 3 is the right solution to the discussion question。

And many other implementations may have different consensus rules of the epo based reclamation。

 and they may have different criteria， but the essence is the same。

 So this diagram is the essence and the essence of this algorithm is almost the same of course all the implementations of epog based reclamations and you don't need to worry about the concrete rules and the rules of the other implementations。

 So for now let's assume that this is the canonical rule for EBR and the canonical criteria for the epo based reclamation algorithm。

😊，Okay， so first good， the stress overlapping this step can now reference B。

 as I explained just before， and as a result， it is safe to free B B in the collect function。😊。



![](img/613dd11b2d8ff6788756b6d8d8272215_5.png)

Now， let me explain the how easy it is to apply the epo based reclamation to concurrent data structures。

So recall that the h pointers needs to insert in a few places the instructions for the Sa numerical limitationss。

😊，Epopress reclamation is the same。 We need to insert a few things， but arguably。

 it is much more simple。Much simpler than those four headed pointers。

 So let me give you the concrete things and then discuss that。

Recall that the line 16 may be unsafe because the concurrent pop function may already fade it at line 18。

So in order to prevent such huge after free， which is the goal of every safe memory combination algorithm。

We first insert the set active invocation between line 12 and 13。So。

The line 13 is the beginning of the access to the concur memory locations。😊。

Line 12 doesn't doesn't access the shared memory locations。 so we can safely cold。

 is it active and at after line 12。😊，That says that， oh， I'm going to access the Con memory blocks。

 so I'd like to protect all the accesses that I'm going to do in a blanket manner。😊。

So that is by invoking the function set active。And the second change will be calling6 Crescent at line after line 20。

😊，So before line 20 we are going to access the shared memory， so this is a loop。

 so maybe it is possible that after line 20 we go to line 13 and then 14 and access the shared memory location。

😊，So only after line 20， we are quite sure that oh， we finished the Con memory。

 so we can safely call set Queescent or we can get out of an active state。😊。

So that is basically all the very basic things we need to do for this epo paste recclamation。

And further， in the exactly same manner as in the pointers。

 we need to replace this free function with an retire。😊。

So recall that we should not immediately free the memory location because it may be concurrently accessed by the other threads。

 so instead of freeing this block curve， we need to retire it so that the E based Relamation algorithm later deal with this intent to free。

😊，And actually， this retire request will be served by actually fraing this curve only when it is guaranteed that all the other threads finished accessing the block B。

😊，I mean， the block curve， as I explained in the previous slide using the Epocon。And that's all。

 that's the all the changes we need to do for the EBR。😊。

So compare this with hazard pointers in the hazard pointers， you need to protect。

8 individual pointers before the referencing it。And also， after protecting it。

 you need to make sure that the pointer is still residing in the concurrent memory。😊，Otherwise。

 you need to go from the beginning。On the other hand。In this EBR implementation。

 it it just marks the beginning and ending of the concur memory axises。

 and you can just replace the invocations of free with the invocations of retire。😊。

Deel that is the API of this ABR is much， much more simple than the API of the Had pointers that required you to protect the individual pointers that you are going to dereference。

😊，And you need to also validate the， the protected pointers after calling the protect。Fction。

And it is difficult to do。 and actually， it is very error prone。

 and many errors may occur due to some missing protection or missing something。But in。

In Ipo past reclamation， it is really， really difficult to break the rule because you just need to mark the beginning and end of the concurrent axis and replace free with the tire。

 That's all that is very easy to use。 and at least much more easier to use than the hedger pointers。

So that is basically the benefits of these epo based reclamations。 However。

 it has a very significant drawback or shortcoming。



![](img/613dd11b2d8ff6788756b6d8d8272215_7.png)

The， the shortcoming of this EO is that it is not robust in the sense that if some of the stress are。

 if some of the stress are。Hinndering the reclamation。

 then the delocation or the free of these blocks may indefinitely delay。

So let me explain it by example， so let's assume that there are four rests that are maintained by an epoch based reclamation and epo consensus。

And now suppose that。B is retired， and then it put B， E。

And for or assume that T3 is of very bad threat。It is very， very bad and it is not。

 not quitting its active state， and it is continue。

 continuing to access the shared memory without bothered with the other threat。And if it is the case。

 we cannot advance the block epoch to the bigger values。

And all the later stress must have been annotated with an epog+2 or less。

The reason is that E+ 1 is on and on and on， it doesn't finish at all。

 so all the later stress are overlapping with this test， e plus1。

 and as a result by the apo consensus rule all the later stress epoch must be less than more equal to e+2。

😊，And recall that the block B may be delocated at an epogi+3 for the reason that I explained in the previous slide。

But at this point of time， B cannot be claimed indefinitely because of this T3。

 because Ipo cannot advance  to e plus 3 due to the T3s active status with Epogi+1。

So B cannot be claimeded at all， even though it is retired earlier。

 so even after hours and days and even years， this block B cannot be claimeded because of this bad threat history。

In that sense， this is not robust。 A bad thread may block the de location of all the blood。

 all the memory blocks。Indefinitely， so history may effectively be。

Offend or attack the the entire system。 A single thread may attack the entire system by not calling zquestscent。

 So that in that sense， that is not robust。So there are hydro pointers and Epoch has a serious tradeoff。



![](img/613dd11b2d8ff6788756b6d8d8272215_9.png)

So， so this， this slide illustrates that。 So recall that。

SMR algorithms are roughly classified into these two categories。

 hydro pointers and epo based glation。😊。

![](img/613dd11b2d8ff6788756b6d8d8272215_11.png)

And as I explained just before， Heer pointers is slow and it is not applicable to many。

Many patterns of synchronization。On the other end， epoch based reclamation is not robust。

 So they are are having two the distinct characteristics。 and there's distinct shortcomings。

And I said in a previous video that there are many descendants of these two algorithms。

 and many of them are actually hybrid of those two。And however， none of the。

 none of the proposed the。Eorrims satisfy all the desired properties at the same time。 For example。

 this class of algorithms are not compact in the sense that they should annotate all the memory locations with some value。

😊，And， as， and as a result， they may increase the size of the memory allocate， this。

 the size of allocated memory significantly。😊。

![](img/613dd11b2d8ff6788756b6d8d8272215_13.png)

And some of them are utilizing the hardware or operating system specific features。 and as a result。

 they are not that portable。😊，And some of them are not applicable to as well。



![](img/613dd11b2d8ff6788756b6d8d8272215_15.png)

And some of them are not robust。So the problem is that so the hazarder pointers and e page reclamations。

 they have distinctive shortcomings and as far as I know all the descendants of these two algorithms that has been proposed so far share the same shortcomings or they are having a different shortcomings。

😊，So none of the proposed techniques or algorithms satisfy all the desired properties at the same time。

And this is a a very brief advertisement of this laboratory。😊。

And in this year we propose what is called a pointer and epoase reclamation。

 which satisfies all the properties at the same time， it is fast。

 and why do the applicable as in Epo based reclamation and at the same time it is robust as in the hazard pointers。

😊，AndFurthermoremore it is very compact in the sense that it doesn't increase the memory usage at all。

 and it is self contained and as a result it is very portable and it can be applied to many platforms and even embedded systems as well。

😊，So， so that is basically what Jia Wang and I did for last year and this year。

 and it has been published in this P what is called the PLDI conference。So unfortunately。

 in this course and in this semester， we cannot go into deeper aspects of this PBR because it is a bit more complicated than both H pointers and epo based reclamation。

😊，And yeah， if you are interested， you can watch the Ji Huang's talk at PDI 2020。

 and it will explain a little bit about the implementation details and algorithmic details of this algorithm。

So and unfortunately， we， we should stop here and， and hopefully you learn the algorithms of hazard pointers and epo based prolamation as well because they are the。

😊，Most basic and the oldest algorithms of for safe memory limitationsations。



![](img/613dd11b2d8ff6788756b6d8d8272215_17.png)