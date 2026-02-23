# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P19：-19-Michael-Scotts Queue.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this video， we are going to study Michael and Scott's Q。

 It is the first lock free queue implementation that is due to Michael， ma Michael and Michael Scott。

 so the Michael and Scott are the last names of the two authors of this paper and。And。

And coincidentally， Scott's first name is Michael。And Michael is Ma Michael。

 and Scott is Michael Scott。So this queue is similar to stack。

 the trirs stuck in that it is a singlely linked list。 It is a list。

 and it is pointed to by the head pointer。And the Q pops from the head pointer。

And the Q pushes into the tail pointer。So compare this with the stack in the driver's stack you push to and puff from the same head pointer。

 but on the other end in this Q data structureer， you puff from the head and then you push to the tail pointer。

And as an optimization， you have a tail pointer。It you have a physical location that is trying to point to the tail pointer。

And the reason is that you don't want to traverse the entire queue when you push an item to the queue。

Instead， you want to load a tail pointer， which is assumed to point to some latter part of the list and then try to traverse less by starting from the tail pointer。

But it doesn't need to be the actual tail。 So it， you have to be a little bit cautious about this。

 So it the tail pointer is in the queue， but it doesn't need to be the actual tail。

 but it still points to some nose。So you can see the implementation in this site here。

And in this video we I am going to mildly explain some of the implementation details of this queue。

Like Tra stack， we use cus to synchronize the operations in the queue。For the P operation。

 you are going to perform Comp swapwab on the head pointer in the same way we do for the driver stack。

The other hand， for push operations， you are going to find the tail by traversing from the tail pointer。

And then perform the class。 So the last last node appointed to this node pointer， right。

 So you are performing cu from the node pointer to the new node。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_1.png)

So let me visualize the idea here using animation。So in order to perform P。

 you first traverse the head pointer and once again， so you traverse two times。

And then you are going to perform a class。So this is basically what is done by using a bulb for the miscocu。

It's， it's pub operation。And one thing to notice is that you are going to receive the value not from this node。

 but from this node。 The reason is that this node is meant to be the dummy node。So it is a dummy。

 and it doesn't contain any useful information。 It just it's just there in order to take place。

 but the value， the hat value is actually 37。So we are going to retrieve the value 37 and return the37 value when you perform the pop function at this is at this stage of the cube。

On the other hand， order to do a push， you first retrieve the tail pointer and get to the actual tail by traversing the next pointers itly。

So you can know that some notice if its next pointer is a no pointer。

And now you create a new node and perform a comparison swap。

Before doing comparing swapb from this node pointer to this new node pointer。

 you create node and you set the next pointer as null and you compare swapwab。

 this node thes next pointer from node pointer to the new node。Effectively。

 you are inserting a new node at the end of the list， which is at the end of the queue。

So it will effectively implement the FiO first thing and first out。Okay。

 this is basically the major design choices， and there are a few implementation details we need take into account。

So the primary design choice here is the tail pointer。 We designated this tail pointer 2。2。

 the tail pointer。But you can see that right after pushing a new node。

 the tail pointer becomes stale in the sense that the tail pointer is actually pointing to an old tail。

 not the actual tail。So we need to somehow fix the tail pointer after pushing a value at the end of the queue by changing the tail pointer from this to the new node。

 basically。So。Theres tail pointer。 The challenge is that the tail pointer can be a tail。

 so our solution to this challenge is that we relaxed the invariant for a tail pointer。

 So tail is actually it doesn't need to be the actual tail。

 as you can see right after pushing a value is no longer an actual tail。

 but we want to establish an invariant that the tail node pointer is reachable from the head pointer。

So it is true at the， at the beginning of the execution， head is here。 and now head becomes。Here。

And this tail pointer here is reachable from either dummy or 37。

So in order to maintain this invariant， we。We， we need to take care about the relationship between the head and tail pointer。

 but still， we can easily establish this invariant that the head pointer is reachable from the head pointer。

So let me explain a little more about how to establish this invari in the next slide。

So this is an algorithm for Michaelkascu in one slide。

 so let me first explain this and let's go to the code and see what's going on there。

So in the push operation， you first find the actual tail。 So recall that concur thread， for example。

 say through C。Let's say C is also trying to push a value。But it is a pointer 666。

 but actually it may be the case that the actual tail is inserted by newly inserted by the Str beam。

So the strip pointer is sta， it contains an old value。If it is the case， we are going to。

Find the actual tail by traversing from this tail pointer。Oh。

 this is the first node and it read the next pointer and since the next pointer is not nu we this point。

 this node is not the tail。😊，So with Traverse and here we are going to read the next pointer and this is the node pointer。

 So that's the reason why this note is the top detail of the list。Okay， so in this way。

 we are going to find the actual tail。 and also we try to update the tail pointer。So okay。

 and now we assume that we retrieve the actual tail here and we try to update the tail pointer by performing a comparing swab on the tail pointer from the original tail to the new actual tail。

If successful， we are helping the other threads in such a way that we are updating the tail pointer to the latest value。

😊，So it will have the other threads to traverse more efficiently traverse to the actual tails。

But it may fail because maybe even another thread may already updated the tail pointer to something else。

If it is the case， I may fail， but it does matter。 it means that the tail pointer is updated by autothre。

And it is as good as I updated the tail pointer。I am guaranteed that I or someone else updated the tail pointer。

😊，That's probably the everything we want for achieving synchronization。

 So it doesn't matter whether updating tape pointer succeed or not， but it matter。

 what better is it that tape pointer is updated by someone。So in this way。

 we update the tail pointer by performing a comparing swapwab on the tail pointer from the original tail pointer value to the new node。

And as a second step， we try to append a new node by performing a comparison swapwab on the tail pointer's next pointer。

So if we succeed， then we effectively。succeeduced in inserting a new node。

 so the operation is successful。If the cu is not successful， then we need to try again。

By retrieving the new tail and that the reason why the cost fails is that some other threads already performed a cast on the tail。

 So we need to traverse the new tail that is just updated by a concur thread。

 and thenend the node there。So it fails if you should try from the beginning。

 retry from the beginning。 and if it succeed， then the entire operation is successful。And after that。

 if the。Uending on new node by Cu is successful， then you update a tail pointer for the others。

So in this slide slide， threat B successfully pushed a new node here。But tail becomes stale。

So threath B is helping the other source by updating the tail pointer from this 666 to the new node here。

So it helps that it helps the tail pointer to be less stale。 and it is a way of optimizing。

For the other stress to。More efficiently traverse the to the， the actual tail node。So as I said。

 the same in this step， we perform costs from the old to the new tape node。

And it is also okay to fail the cost here as well， because it means that the other threads。

 some of the other threads succeeded in updating the costs updating the tail pointer。

 So the what is important here is updating the tail pointer by someone。

So it doesn't matter whether I succeeded or I failed to perform the class。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_3.png)

On the other hand， the part of operation is doing like this。It first raised the tail pointer， and if。

And it checks if the tail pointer is pointing to the do node。So here。

 if the tail pointer is pointing to this do node， it means that。After updating the head pointer。

 head is taking the back of this the tail pointer。The order of head and tail are reversed。

 So this is what is a bad for this cube。 So if the tail is pointing to the dummy pointer in order to prevent how to take over the tail pointer。

 we we try to update the head point the tail pointer from this dummy to the next node，37。So， if。

what is here is that if the cost is successful， then we are good。 if the cost is unsuccessful。

 we are still good because it means that the tail is no longer the do note。So， by。

Performing a cuss if the tail is pointing to the domino。

 we ensure that the tail is no longer pointing to the domino。And after that。

 we update the head pointer by performing a ca from the first node to the second node。It。

 if it pay fails， then you can try from the。Retry from the beginning and if you are successful。

 then it means that push the pop operation is successfully finished。😊，And as I said。

 the tail pointer is updated if it pointed to the domin node。 And by doing so。

 we can establish the invariant here， The invariant for tail that is tail must be。

Reachle from the head pointer。After updating the tail pointer from domino to37。

 we can establish the environment that this tail pointer is reachable from head pointer。

 even after we pop a value， we remove the domino from the Q。

So it is important to establish this invariant that the tail is reable from the hat。And。

 and you can see that after popping this doo， this37 node becomes the new domino。

Because it is the first note。Every time the first node of the micro Sky's Q is the domin node。

 and it may contain value， but it means nothing。It is just dummy。Okay。

 there is the algorithms in one slide， and now I'd like to go to the implementation and read line by line。

This algorithm is is published in about 25 years ago。

 so it is quite all the algorithm by Michael and Scott。

 but it is still widely used when lock free queue is necessary。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_5.png)

So for a second， and we again have a crossperaminepo and crossperm mutT is cache padd。

So and let me explain line by line what's going on in the rest of the code。

So the Q is basically pointing to two nodes。 So there is two pointers， head and tail。

 and they are pointing to a node。A node is， as usual， consisting of a data。And on next note。So。

We are。Marking it as maybe an in it， which means that data may not be initialized and it is especially useful because we are having a domino。

 so at the beginning of the queue the dominot value is uninitialized so we want to explicitly mark that in the type that means that the data in the node can be uninitialized for example。

 due to the domino。And it also contains the next pointer。 So it is as usual。 So。

 so the node should have a next pointer to the next node。And Q is pointing to the two noses。

 The one is the head， and the other is the tail。So for a second。At the beginning of Q。

 it is going to。Alloccate the。Q here。 So you're going to create a queue。 and， and， and this will be。

This will be the Q return。But we are not returning this no pointer。At the beginning of the C life。

 we need to insert a domino。At every time the queue has a domino。

 So that's the reason why we want to。We wna put the domino here。So it a domin， we create ainel。

 so the Sinel here means that we are creating a domino， the initial domino。

And it doesn't contain the data。And we are using。we are setting the next pointer as the nu pointer。

And so it is that the Uniinialized data with the no pointer that is the initial do node。

And this sentinel value is now stored in the head and the tail pointer。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_7.png)

So let's see what's going in there。 Sentinel has un init value。No， next pointer。

And at the end of the。Accususe life。Head is pointing to the Sinel。And also。

 the tail is pointing to the Sinel as well。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_9.png)

And this sentinel is allocated in the hip。 so you can see that you are creating an owned bus and this owned in the cross beam terminology is creating I mean。

 allocating the data in the hip。😊，So you are creating a hipA allocation and let the head and the tail pointer to point to the sentinel。

 which is in the hip。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_11.png)

So it is the initial Hs memory layout。Okay， so first are good。So far second good。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_13.png)

And now we are returning this queue。After setting， they had in the tail pointer。

And now let's see how to push your value to the cube。

So you are given a reference to the guard that means that the guard means that you are allowed to access the shared memory。

 the data structure in the shared memory。And it is basically a proof that you are。

You can access the the data search， share the memory。So what you can do first say that add。

 you first create a new node here。So recall that you。

 you need to create a new node with the new data and no pointer。And you are creating this in the hip。

So that you can attach this new pointer， a new new note to the end of the the to the detail of the queue。

Okay， so first second。 and you are creating a newod here。

So this inter shirt means that this new is the type there are two types for the the H allocation。

 the one is owned and the order is shared and owned means that no other thread can access to this note。

🤢，And shared means that the other thread may access to the node。 So by calling this intohir。

 we are effectively releasing some ownership over this node。 So so far here we own the new node。

But from now on here， we release the exclusive ownership。

 and we kinda admit that this new note can be shared among multiple stress。Okay， so first good。

And we are looking because if we didn't succeed in inserting a new value to the end of the queue。

 we should try again。With the same node， so that's the reason why here is a loop。

We first load the tail pointer。So tail is， as I said， optimistic。

 so it doesn't need to actually point to the real tail。

 but it is actually pointing to some node in the cute。So we load the tail。

And we de referencefer the tail， and we read the next pointer of the tail note。If tail is none nu。

 then the tail is actually not the real tail。So we move the tail pointer to the next one。

So we perform comparing swa on the tail pointer， my tail pointer from the old tail here。투다。

Next pointer。So you're trying to perform a cut from the original tail to the tail's next pointer。

 Step one。So there is what's done here。And as I said， it doesn't need to be successful。

If it is successful， it is very good， I move the tail and if it is unsuccessful。

 I fail to move the tail but by failing to do so， I know that someone else。

 some thread else let it succeeded in moving the tail pointer to some next note。😊，So first are good。

 So tail is now updated。 So you will continue from the。Here again。

 because the tail was sta and we updated the tail pointer so we want to try again from the beginning here。

Otherwise， if the next pointer is actually no pointer， then tail is actually the。The next pointer。

I mean， tail is actually the real tail。So now we try to append a new node by performing a comparison swap。

So this is the comparison swap here。 so we perform a comparison swapwa on the tail next pointer。

 So effectively this is the tail nose next pointer。From the no pointer to the new node。

And if it is successful， it's very much good， we help moving the tail in the same way as above and then return。

Otherwise， if it is unsuccessful， then we know that we didn't succeed in a new note， a new value。

 pushing a new value。 it is failed。 so we try from the beginning again。

So that is basically the implementation of the push push function。

And let's go to the implementation of the TriP here。

So we read the hat pointer and then it has next pointer。Okay， so first second again。And。

If this next pointer is a no pointer。So this S ref returns known if this next is the no pointer。

If this is not a no pointer， then it is returning。Reference to the next pointer。

If next is the no pointer， then we return none。Because。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_15.png)

It means that。TheDQ is looking like this。Head pointer is pointing to something。

And it is pointing to the nu pointer that means that the Q contains only the dominode。

Which means that Q， the queue is empty。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_17.png)

So that means we should return none at this point of time。Okay。

 and we are trying to update the tail pointer， if necessary。

So we read a tail pointer and if it is the same with the head pointer。

 that means that the tail pointer and head pointer both points to the do node。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_19.png)

And like here。I mean。So maybe it is possible that it its next pointer can be something else。

But the tail pointer still points to the Sinel。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_21.png)

If it is the case， this condition is met， The tail and hell pointer simultaneously points to the dominantmin。

Then if if it is the case， we update the tail notes as usual。And after updating the tail node。

 regardless of whether we succeeded in or not， we know that the value is the Q' tail is no longer pointing to the do node。

Because it is already updated。Now we can perform a class on the head pointer。

 We perform a class on the head pointer from the original head pointer to the next node。

And if it is successful， we are destroying the head by performing this and then return the value of the next node。

So we don't retrieve the value from the domino。 The domino is here had。

 and we retrieve the value from the next node。 So as I explained before， domino's value is。

That not means nothing。 So it is already taken by an all year operation。

 So we need to take retrieve the value from the next note。

And we perform garbage collection on the D node because head is no longer pointed by the Q's head pointer。

 so we need to destroy it。But。Maybe it is possible that a con spread may simultaneously。

Reference the the same head pointer and the reference its next pointer。

That's the reason why we should not free this head pointer， this stmmy pointer immediately。Instead。

 we rely on cross beam， mean we just say we def destroy the head pointer。

And the crisp beam epoch will automatically handle。And later。

 decate this hipA allocation when no threads are currently accessing the same node。So for now。

 let's assume that you can just differ destroy using the guard here that is given here。

But later we are going to study the Ipo based memory clation algorithms and see the details of this different destroy and this scar and what's going on behind this artifact。

Okay， so far so good。And in the drop implementation， we just loop again。

 loop and loop and loop again and pop the nose and drop the the allocate the nose。

So that is the the in one， the un easiest implementation of the queue， basically。Okay。

 so far so good。And this is the。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_23.png)

The key implementation。And now we go back to the slide where we explain the algorithms。

 So these procedures are actually implemented quite straightforwardly in the rust code。

 So please read list and please read the Q implementation and they。

You can immediately relate the steps to the ro implementations。As the same with the tri stack。

 I prepared a few problems set for mycos Q that can be that you can meet in the you can see in the final exam。

And I'm going to answer one by one for these questions。 So while tail pointer may be sta。

 So it is already answered in the previous slide。 So right after a new node is inserted。

 you can see that the tail pointer becomes sta。 So that's the reason why tail pointer may not point to the actual tail node。

And here is a little more tricky question。 why there is a domino at all。

 Why you just point to the first node， first value in the Q， But will。

 you point to the do node from the head pointer。So the main reason is that by doing so。

 you can guarantee that the tail pointer has somewhere to point to。

So recall that at the beginning of the cu live， the a Sinel domino is pointed to by both head and the tail pointer。

But if there is no such a node and head points to the no pointer。You have to see that。 you can。

 you have to。嗯。You have to assign the no pointer to the tail pointer because there is no such a no to point to。

If there is no sentinel dominote。So if it is the case。

 we cannot establish the invariant that the tail pointer is reachable from the head pointer。😊。

So in order to establish the invariant the reachability of the tail pointer from the head pointer。

 we are designating a domino。Just in order to establish the invariant。 So by using the do node。

We especially for the MQ， we are effectively when efficiently establishing the invariant。

 the reachability。😊，Also， so the third question is why head and tail are cache padd。

It is quite easy from the。 So it is the same with the。Previous tri stack implementations。

 we want to separate the hat and tail variables as much as possible。

 so they should not be falsely shared because tail and head are a point of concurrency you can work on tail and you can work on head concurrently。

And in order to achieve higher performance， we need to separate them in separate cache liness in order to prevent the a sharing。

So that's the reason why we are patting the head and tail pointers with a cache pad。

 So to make sure that head and tail pointers are residing in the different cache line。啊。And also。

 as usual， as the same with the driver stack， we are trying to understand why some orderings are released and why some ordering are acquired。

So， so that is the same。 We want to establish some invariant。

 So in order to establish that invariant this on this。

Oerings must be released or required from time to time。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_25.png)

Okay， the microscope Cusing guarantees that a pointer suppose， for example。

 this pointer is pointing to a node A here。😊，And this pointer value has a release view。Right。

 so this the value， the value from this pointer and the value is the the pointer to this a。

And this point of value should have a release view in the promising semantics。😊，And its value。

 its view should be bigger than or equal2 as is value and its next pointer to B， for example。

So that is the environment， its pointer。Its release view is greater than where it equal to the pointed node as value and a's next pointer。

 So that is the invariant we want to establish in order to prove the safety of when functional correct of this micrococh queue。

😊，Okay， let's see how we can be maintained by the release orderings and how it can be exploited by an acquired ordering。

Okay， so far so good。And now we can see the code examples here。Okay， so。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_27.png)

Okay， here are the code example。So there are， for example， really soors here。We want to。

Compar and swapb。The tail pointer from the old pointer to the new pointer。 Here we are using the。

Really soldering。So the reason why it should be released is that this tail pointer will point to some node。

 and we need to establish the fact that this tail pointers release view is greater than or equal to the pointed node here。

 the next here， its value and next pointer。And actually， is established by here。

 This next pointer is acquired。 and as a result， this next pointer。😊，Is， its so the。

 the the cur right view。The construct view is greater than or equal to the next pointer's value and the next pointers view。

So this is released here。And as a result， the tail pointer release view will be greater than what equal equal to the。

 the the。This next node， value and pointer。So that is established by this acquire and then this release。

So same happens for here too， so new node is created here and we want to release this。

In order to establish the invariant。Also， we want to establish the event here as well。

 The new node is。Becomes the new tail node next pointer。

 so we need to release it because we want to transfer the knowledge。

 the view on this next new node to the tail notes next pointer。By comparison。

That's the reason why it must be released and it must released。

 The new node is written to the location， and it must be done with release。😊，The same thing here。

 Next note is written to the tail pointer， so it must be released。

The knowledge itself is acquired here， and the acquired knowledge is released here。

So these two are matching。And these two releases are matching with this。



![](img/4523fb4d2ed056ec05b1414a8bf23c3b_29.png)

The knowledge here， the knowledge of the hip allocation is release here and here。

So they are the reason why it should be acquired and it should be released。Furthermore。

 this must be acquired as well because we are trying to dereference the next pointer here。And。

 you know， to do so， we need to acquire the tail pointer here so that we are always seeing the。

The the latest value of the next pointer。So otherwise we will we can see some sta next pointer。

 which can be some even no pointer。So in order to prevent that， we。

 we should acquire this tape pointer so that these。

the reference of the next pointer will see the latest value。So， first good。And here as well。

 we are reading this head pointer using a acquire in order to retrieve the latest next pointer from the head pointer。

😊，And we are also acquiring this in order to retrieve the。A the。

The the latest value of the next node。 So recall that。

 So here we are basically retrieving the do node。And here we are retrieving the next node from which we retrieve the value。

 We will return the value from the next pointer。So that's the reason why we need to acquire this to get the latest value that is written in the next pointer。

So， so the value is written here。 So in order for this to read the latest value。

 this must be a acquired。And in order to read the the dumies text node as latest。

 it must be acquired。 That's the reason why these two are acquired。

And this can be relaxed because if it is it detail is read only to check whether this is the same with had or not。

 and if it is the same， we already read the head pointer here。😊，So there's the。

 there's no moral reason to acquire the the the tail pointer here。 It is if， if we go into this line。

If tail is equal to head， then we effectively already acquired the tail pointer because we acquire red the head pointer here。

And further， it must be released for the same reason。

 so we must release the information on the next pointer， which is acquired here， so the current view。

 the stress current view， I have a latest information on the point next node。

 and it is released at this point of time。When the next pointer is written。

And the same thing happens here， the next pointer is written to the head pointer and we need to do that using the release ordering。

😊，打。So， so far so good。 So that is basically what's going on in the orderings。

 So I hope that you can understand the， the actual actual reasoning in the。

Actual reasoning in this release acquired orderings that is explained in the slides in the slide I explained that so this is the release acquire occurrence。

😊。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_31.png)

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_32.png)

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_33.png)

And the reason why they release and acquire is to establish and exploit this imvariant。

So only if this is satisfied， we can safely return the value。Otherwise， if this in is not met。

 then the value that is returned from the tripp， it can be ra。

It can read a very sta value that is not meant to be the value in the Q。

It can reach some garbage value if the release acquire is not properly used like this and。

If this invariant is not established， the tri public will return a very strange value。

So that's the reason why we do regional cho at this point of time。Okay。

 so far we studied the Micar queue and as in the previous video。

 we studied its operations and the orderings and the synchronization were invariant。😊。

So I hope that this explains something to you and I strongly encourage you to ask questions in the Github issue tracker。

 I know that this is quite tricky and from time to time it is difficult to understand some of these synchronizations here。

So that's the reason why I urge you to ask questions if you have any concerns or any questions or any comments。

 So by so it is。It is a way of effectively learning the things by asking questions。

Without asking questions， I am almost certainly sure that you will not be able to。

Grasp the contents of the previous and this slide。 They are quite dense。 So I hope you can， you can。

 you can ask questions in the Gi tracker。

![](img/4523fb4d2ed056ec05b1414a8bf23c3b_35.png)