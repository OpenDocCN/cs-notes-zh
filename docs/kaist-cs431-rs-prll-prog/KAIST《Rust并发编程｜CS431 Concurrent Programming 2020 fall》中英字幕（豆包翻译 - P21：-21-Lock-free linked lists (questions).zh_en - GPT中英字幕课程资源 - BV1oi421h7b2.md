# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P21：-21-Lock-free linked lists (questions).zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

![](img/aa334a28bddd8e8860f5a3d695c5d0a3_0.png)

In this video， we are going to continue to study the lock free single links list。

So in the last video， we studied the algorithms and the high explanations of the synchronizations that is conducted on this sorted single linked list。

And in this lecture， we are going to study a few design choices。

 So why design A is designed in this way。 So I'm going to explain a few of them。

And also I'd like to explain why the synchronizations are safe or correct。

 why the insertion deletion and lookup， even though they are concurrently executed。

 they are somehow safe and they are working as expected。So the first question is in the deletion。

 I explained that。We are going to first， tagging a note。To denote that this is logically deleted。

 And only after that， we are going to delete this node or only link this load by actually updating the pointer。

So why do we do that？I already explained it in the previous lecture video。

 but I'd like to repeat it because it is the most important design choice of link list， I mean。

 luck free link list。So， let me explain the。Let me show you this。figure here。

So suppose that a head pointer is pointing to the first node and this first node's next pointer is pointing to the second node and on and on and on。

So far are good， and we suppose that we are concurrently deleting the second note here。And also。

 we are concurrently inserting a new note。 Let's say this nodes。

New note X between node 3 and node node 2 and node 3。So okay， so insertion is easy。

 We are going to perform a comparing swapwab on this node。

So we create a new node and let it point to node 3 and we perform the cuts on the next pointer of this node2 from the original pointer to pointer to the new node。

So that is pretty much easy or pretty much expected。

 It is the atomic way to insert a node between two anding。But， in addition。

Suppose that we are concurrently deleting this note。And suppose that。

In a naive implementation or incorrect implementation， in order to remove this node。

 we are immediately updating this pointer。2。2， this node。So suppose that in our wrong implementation。

 we are going to perform a class on node one's next pointer from node 2 to node 3。If it is the case。

 one of the final results after this deletion and insertion is that head is pointing to node1。

And node one is now pointing2， node 3。Because in the course of removing this node 2。

 node1 X pointer becomes node 3。And those three next pointer is not4 and on and on and on。

So so in may be the final result or final memory layout of the single linked list after this concurrent deletion and insertion。

The problem is that node X that is just inserted in here。It is forgetting。No 2。

2 x after this insertion。Because we perform the costs on node2 next pointer from node 3 to node the X。

But node2 is now inserted and deleted。 it is no longer reachable from the head pointer。

 and as a result， this node the X is just forgotten。😊，That is a problem。

 even though this value is inserted， it is not in the data structure。

 it doesn't satisfy the intuitive specification of a linked list。

 we should not allow such cases to happen。How to do that， how to prevent such cases。

 So the logical de is a very clever idea to do that。😊，So in deletion of this node2。

 we don't update node once next pointer immediately。Before that， we are updating no to next pointer。

So it is currently just pointing to the string， but we are going to tag this pointer。As deleted。

So the， the physical way to do that is that updating the least significant bit of this pointer with one。

Using some of what is called fetch or operation。Okay， so first good。If this pointer is tag as 1。

 let's， let's denote it this way。Then。Insertion will fail。Because no two is marked as。

And logically deleted。😊，And this will fail because it is trying to update that the pointer to no 3 to。

TheThe pointer to the new note。And the， this， this， the value inside this node to the next pointer。

 it is no longer just node 3。 It is tagged pointer of this node 3。

So the cost will fail because of because of the tagging the physical value of the pointers will differ。

 so that's the reason why the cost will fail and as a result this insertion will fail。😊。

After this edition is successfully logically deleting the node2。😊，On the other hand。

 if this this insertion is performed first， then notice two next pointer is。

No 2s next pointer is now node X， and this logical division will fail because it is not going to be。

 It is not going to be。啊。A they。They did note3。So the， the text pointer will just point， I mean。

This node 2， not the pointer from node 2 to node 3 will not be tagged because a new node is inserting in between。

And as a result， this will not succeed in logically deleting by tagging the pointer to node 3。

So depending on the order of the operations， either one of them happen， deletion， I mean。😊，I mean。

 if this de is successfully logically deleting first， then this insertion will fail。😊。

If this assertion will succeed， then。This code will not logically delete the node 2 by tagging the pointer to node 3。

So that is basically how to coordinate this concurrent deletion and insertion in the implementation。

So to summarize， so it is the the possible end results in a9 wrong implementation。

 which is very bad because node X is just forgotten。 This case is prevented if we add logical de。Now。

 logical deletion introduces a little bit of complication。The reason is that。even though logically。

 a node is deleted from the linked list by， by its next pointer being tagged with one。😊。

It may still reside in the linked list physically。You can reach the logically delete node by traversing from the head pointer。

So at the end of the day， we need to just to remove or unlink。The， the deote from the linked list。

So that is what should be done in the implementation。So depending on how to or which node。

 which logically deleted nose is actually physically deleted。 So the。

 the three three travel strategies are invented in order to， I mean。In order to delocate。

 I mean un the node between the logically node and the three strategies are Harris's strategy and Harris Michaels strategy and Harris。

And have so sha strategy。Okay， so first second。

![](img/aa334a28bddd8e8860f5a3d695c5d0a3_2.png)

I think that now you quite well understand why we first logically delete the node and then physically delete a node。

 The reason is to synchronize with insertion and deletion。Okay。

 let me move on to the second question。 What's the motivation of Harris Michael's list。

So in Harrisy' strategy， you are going to update the pointer。

And you are going to physically onlink multiple nodes at the same time。

So if they are two consecutive logically deleted node then in the herey strategy。

 you are going to update the next pointer and I mean。

 it is not just updating the pointer to the just next one。

 but it is updating to next to the next one。😊，Eff factly un linking two consecutive for logically de note。

So you can think that Harrison's latest list might be faster。

And it is indeed the case in our benchmark。Then what is the motivation of this Her Michaels list that is just unlinking only one node at a time。

😊，So the reason is that the most famous algorithm for memoryclamation for concurrent algorithms。

 which is called hazard pointers， it only supports my Cy Michaelel strategy。

 it doesn't support the heresy strategy。😊，That's the reason why we are not going to， I mean。

 we also learn Harris Michaels。strategy for least travelo。So on the hazard pointers。

 we are going to deal with it in the later part of the dis course， and actually Ho 6。

 the final homeworkock will be about implementing hazard pointers。And， and you can then later。

 you can understand that why Harris's list is not supported by Hadpointers。

 but Harris Michael's strategy is supported by hydro pointers。So for now。

 I didn't explain well about this point， but just please memorize this fact。

 so we are going to deal with this at the later stage of the course。And the final question is。

 what is the motivation of this Harry ho Shaish list？So it doesn't physically delete the nose at all。

 It just moves on withouting without bothered with the in between logically deleted nose。

 it just go over。The reason is that it doesn't want to wait for the other threads to succeed in some operations。

 so it is possible that in cu you may fail to update the you may fail to perform the cu。

And if it is case， you may fail to traverse water。And that's the reason why we do Harry or le of it。

 we are just going to go over without bother with a logically dig note， and in that sense。

 this particular lookup or this particular travel hole will be very fast。😊。

So if your query is very much important， an issue should be served with the ultra low latency。

Then you are likely choosing Harry's Holyly Shavic strategy because it should run fast。

The fixing the list， actually physically deleting the nose。

 it can be done by other lower priority test。So that test the motivation of this strategy。😊。

And so far so good。 And now let's move on to this the the synchronization and the question is of the synchronization。

😊，Why this is correct algorithmm on top of the relaxed memory concur。

So this is basically trying to answer such a question。And here are the reasons here。As usual。

Like like for Q and like for stack， we are going to establish an invariant。

Invariant must be maintained by every operation that is concurrently executed at the same time。

 and furthermore， depending using this invariant， we need to be able to prove the safety of the operations。

So basically， this is the for maintaining and exploiting the environment。

If you are going to write something。You usually want to do with release so that you are going to maintain the invariant。

When you are going to read something， usually you want it to be on a acquire read because by acquiring it。

 you want to exploit some invariant。

![](img/aa334a28bddd8e8860f5a3d695c5d0a3_4.png)

So the same thing happens for this too， the write must be release and the read must be acquire for many places。

Okay， that the invariant is that。At every pointer。It can be a head pointer or the next pointer of a node。

 etcter。Every point of value has a release view according to the promising semantics and its release view is bigger than。

 I mean， it is greater than what it called to， the messages for the next pointed nu value and its next pointer。

😊，So let's， let's look at the let's look at the figure here。Suppose that a pointer。

Is pointing to some note。And the invari is that。😊，Pointer release view is greater than what you equal to the message for knows that value and knows that next。

😊。

![](img/aa334a28bddd8e8860f5a3d695c5d0a3_6.png)

So this is written by something。 and know that value is also written by something。

And that right has the timestamp in the promising semantics。😊。

And the in is that those timest for the message here。

 for the latest value of this nodeta value and not that next。

 they must be acknowledged by the pointer release view。😊，So that is the invariant。

And let's look at the code now and how this imvariant is maintained and how this variantvariant is exploited。

😊，Okay， so this is the least implementation just as we looked at in the previous lecture。😊。

And let's search for ordering。So， the drop is。Completely owning a linked list。

 So we don't need to synchronize with each other。 So there is no reason we can。

 we should use releasing acquire。 We can just relax here。And in the fine heritage strategy。

 we are going to。The we are going to our。Read the next pointer。

 the kernelel's next pointer with a cho。What is the reason。The reason is that。At， at the if this is。

 this becomes the next current pointer。So we are in the Traverse seeing this link list。

 So we have a previous and the next previous and the current pointer。😊。

And at the next iteration of this loop。😊，This next pointer will be the new current in the next ti duration。

And actually， we are dereencing the current pointer at this point of time。😊。

So in order for this de to be sound when it sees the latest value。We need to acquire this pointer。

Because this is a acquire， we know the latest value on this next node value and pointer。

 next pointer。And that's the reason why when it becomes the next current pointer in the next iteration。

 we are going to safely dereference the kernels and its key。

So that's basically the reason why we need to make it an acquire。So far start good。

 and a similar thing happens here as well。😊，So since the similar thing happens in other strategies。

 why this should be because we are traversing and in order for this key lookup to read the latest value。

 not just the garbage value， we need to make it an acquire。So， first the good。And the same thing the。

 the same explanation applies to this acquire as well。

And now we are going to explain other orderings as well。 For example。

 in this in this update of this previous node， we are doing release。So the reason is that we are。

We are over overriding the point of value。From the previous pointer。

So we are pointing to some node in the name of the previous node， and we are overriding the pointer。

To the current note here。So the previous is was this and it is being updated to point to the current pointer。

And we need to do it release， because。At the， because we want to establish the invariant。

 the invariant is that the。This pointer， the new point。

 this becomes now pointing to the current node。And this pointer values release view is greater than what equal to。

 the kernel key value and the next pointer。😊，Unfortunately。

 this is already acquired by the previous iteration of the lookup here。So this next becomes the the。

The， the。The next current node。And because this is acquired。Now， it can be released。

To maintain the invariant of this previous note。This previous nose， next pointer， its release view。

 becomes greater than verticalacle to， the current nose key value and next pointer。

So to maintain this invariant， we are using the release here。So， first I could。

And the reason why we should acquire is here is almost the same with the fact that。

Almost same with the reason why this should be a acquired， we are traversing the list。

 so we need to make it an acquire。Similarly， this should be released because we are overriding the previous node next pointer from this to this。

 and we want to release the next pointer's key value and next pointer that has been just acquired here。

And the knowledge acquired here should be released to this previous note。

 That's the reason why it must be released。And similarly。Similarly， this should be released as well。

This and this must be released for almost the same reason。Okay， so first a good。

But what is interesting here is that it can be relaxed。Because we are not going to read the， the。

 the， the next pointers。So this is basically reading the kernels next pointer but we are not going to read the next pointer at this point of time。

 We just want to check the tag of this。The tag value that is written in the next pointer。

We just want to know the value of this， and we don't need to access the。The next actually。

 the next note。So that's the reason why it doesn't need to be a cho。Okay， so first are good。

 And that's basically the reason why all the orderings should be acquired or released。

 or it can be relaxed， etc。And you can read other orderings as well。

 and their region is almost the same with what I just described for the finding strategies。

So it must be released for the same reason that the invariant should be maintained for the selfta pre pointer。

 etc， etc。So that's basically the reason and please go through all the occurrence of the orderings and try to explain why it must be released。

 why it must be acquired， or why can be relaxed。By doing so。

 you can easily understand the the why the， the this code is currently synchronizing among multiple concurrent operations。

Okay， so farly good。An。Oh。

![](img/aa334a28bddd8e8860f5a3d695c5d0a3_8.png)