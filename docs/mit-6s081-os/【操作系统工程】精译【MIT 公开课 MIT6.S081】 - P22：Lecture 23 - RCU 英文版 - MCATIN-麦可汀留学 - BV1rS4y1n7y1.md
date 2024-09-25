# 【操作系统工程】精译【MIT 公开课 MIT6.S081】 - P22：Lecture 23 - RCU 英文版 - MCATIN-麦可汀留学 - BV1rS4y1n7y1

 All right。

![](img/a5823530e230b7c3ee90fda214e7fefe_1.png)

 The sort of underlying topic for today is really， getting multi core。

 getting good multi core performance。 I'm getting good performance on multi core hardware。

 And that's actually like a very interesting and deep。

 fascinating topic with many many different interesting aspects。

 Today we're just going to bite off a fairly small piece。

 And that's how to get good performance for shared data in。

 the kernel that's read much more often than it's written。

 And it turns out there's many kind of specific cases。

 in which different ideas for getting good multi core， performance are useful。

 What we're going to look at today is Linux is R。C。U。

 which has been very successful for sort of read heavy data， read heavy kernel data。

 The general sort of background here is that if you have。

 modern machines with four or eight or 16 or 64 or however many。

 cores running in parallel and sharing memory， the kernel is really a parallel process。

 It's a parallel program。 And if you're going to get good performance。

 you need to make sure that the kernel can run a lot of its work。

 as much as possible in parallel on different cores in order to get， that much more。

 If you can run the kernel parallel on eight cores， all of them do useful work。

 You can get eight times the performance， than if the kernel could only run a single core。

 And at a high level， this should clearly be possible。

 If you have lots and lots of processes running on your computer， first of all。

 the processes aren't running and executing in the kernel。 Then we have very little to worry about。

 They're likely to run in parallel without any kernel having to do anything。

 If the process is if you have many applications running and they're all， making system calls。

 a lot of the time， different system calls made by。

 different processes just seem like they ought to be independent。

 and should be able to proceed in many cases， though certainly not all。

 but should be able to proceed completely without interference。 Like if two processes are forking。

 or two processes are reading different pipes， or reading or writing different files。

 there's no obvious reason why， they should interfere with each other。

 why they shouldn't be able to execute in parallel， at end times the total throughput。

 But the problem is the kernel has a lot of shared resources in order to， you know。

 for other good reasons， the kernel shares a lot of resources。

 like memory and CPUs and a disk cache and an iNo cache。

 And all this other stuff that's actually under the hood shared between different processes。

 And that means that even if two processors are doing system calls。

 two processes that have totally never heard of each other and aren't trying to interact。

 make system calls， if those system calls happen to allocate memory or use the disk cache。

 or involve scheduling decisions， they may well end up both using data structures in the kernel。

 and therefore we need some story for how they're both supposed to use the same data without。

 getting underfoot without interfering with each other。

 And there's been enormous effort over the years in making kernels。

 in making all these cases and kernels run fast。 We've seen one of course that's oriented towards correctness。

 namely spin locks。 Spin locks are straightforward as such things go and easy to reason about。 But。

 you know， what a spin lock does is prevent execution。

 It prevents its job is to prevent parallelism in cases where there might be a problem between。

 two processes。 And so spin locks are just directly away to decrease performance。 That's all they do。

 of course。 They make it easy to reason about correctness。

 but they absolutely prevent parallel execution。 And， you know， that's not always that desirable。

 Okay， so again， we're going to focus on read heavy data on the case in which you have data。

 that's mostly read and relatively rarely written。 And the main example I'm going to use is a link list。

 a singly link list。 And so you can think of just the standard link this diagram。

 There's some sort of maybe global variable that's a pointer， it's a head pointer。

 It's just a pointer and there's a bunch of list elements。 And each list element has some data in it。

 We'll just say it's a string like， you know， hello is the sort of data in this element。

 And each element also has a next pointer that points the next list。 And then finally。

 there's a pointer that points to zero to mark the answer very straightforward。 And again。

 we're going to assume that most uses of this list that we're interested in are just reads， you know。

 the kernel thread or whatever it is that's using this list。

 it's just scanning the list looking for something， it's not trying to modify the list。

 And occasional writers though， you know， if there were zero writers ever。

 we wouldn't need to have to worry about this at all because it'd be a completely static list。

 Never changes， we can read it freely。 But we're going to imagine that every once in a while somebody comes along and wants to write the list。

 So that may mean that some other thread wants to change the data stored in the list element。

 or maybe delete an element， or maybe insert a new element somewhere。

 So even though it's naming it mostly reads， we do have to worry about writes。

 We need to make the reads safe in the face of writes。 And of course， in the next v6。

 we just have a lock protecting this list in a reader that， you know， not only would writers and xv6。

 not only would writers have to acquire the lock， but readers would have to acquire the lock too。

 because we've got to rule out the situation in which。

 while we're reading somebody's actually modifying the list， because that could cause。

 sort of a reader to see a half updated value or follow an invalid pointer or something。 So in xv6。

 we'd have locks。 But that has a defect that if the common case is there's no writers， it means that。

 every time somebody comes along and reads， they have in xv6， they grab an exclusive， like xv6。

 pin locks are exclusive， even if you have just two readers， only one of them can proceed at a time。

 So what we'd like， or sort of one way to improve this situation， would be to have a new kind of。

 lock that allows multiple readers， but only one writer。 And so I'm going to explore those next。

 actually both because they're interesting， and because they help motivate the need for R。C。U。

 which we'll talk about in a little while。 So there's this notion called read/write locks。

 And the interface is a little more complicated than the spin locks we're used to。

 We're going to imagine that there's one set of call that you call if you just want to read something。

 So we're going to imagine an R lock call， you pass it a lock， and then also an R unlock call。

 And readers call these， and then there's a write lock call and a write unlock call。

 And the semantics are that you can either have multiple readers acquire the lock for reading。

 So we do then would get parallelism， or you can have exactly one writer have acquired the lock。

 but you can never have a mix。 You can never be in the locks， rule out the possible read/write locks。

 rule out the possibility of somebody having a lock for writing， and also reading at the same time。

 You're either one writer or lots of readers， but nothing else。 So that's the question。 Yes。

 This may be an implementation detail， but what kind of mechanisms。

 does this locking scheme put in place to prevent someone writing while they hold a read lock？

 Nothing。 Nothing。 It's just like XV6 locks。 Completely。

 We're talking about kernel code written by trusted， responsible developers。

 And so just like spin locks and XV6， if the code that's using the locks， incorrect， it's incorrect。

 There's no。 And this is the way typical kernels are written。

 You just have to assume that people developing the kernel are following their own rules。 Okay。

 And again， the reason why we care is that if we have a read-mostly， data structure。

 we'd love to have multiple readers be able to use it at the same time to get。

 genuine speed up from having multiple cores。 All right。 So if there were no problem here。

 this would just be the answer。 We wouldn't have needed to read today's paper。 But it turns out that。

 if you dig into the details of what actually happens when you use read/write locks。

 especially for data that's actually read a lot， there's some problems。 And in order to see what's。

 going on， we actually have to look at the implementation。 Linux indeed has read/write lock。

 implementation in it。 And this is a kind of simplified version of the Linux code。

 The idea is that we have a struct RW lock， which is like struct lock in XV6。

 and it has a count in it。 If the count is zero， that means that the lock is not held by anybody in any form。

 If the count， is negative one， that means that a writer has it locked。

 And if the count is greater than zero， that means that N readers have it locked。

 And we need to keep track of them because we can only。

 let a writer in if the number of readers descends to zero。 Okay。 So somebody asks about adding。

 this。 No。 I'm not sure if there's a question in the chat interrupt me through it。

 The read/lock function。 Yeah， that's a signal loop because if there's a writer。

 we have to wait for the， writer。 It looks。 It grabs a copy of the current N value。

 If it's less than zero， that means there's， a writer and we just need to continue our loop and we're going to spin waiting for the writer to go away。

 Otherwise， we want to increment that value。 But we only want to increment it if it's still。

 greater than or equal to zero。 So we can't。 There's many things we can't do。 We can't， for example。

 just add one with standard N equals N plus one because if a writer sneaks in between when we。

 check the value of N and when we actually try to increment it， then we may actually go ahead。

 and increment it at the same time that some writer is setting it to minus one， which is wrong。

 So we， need to increment it only if it hasn't changed value since we checked it and verified that it's。

 greater than or equal to zero。 And the way people do that is they take advantage of special atomic。

 or interlocked instructions， which is saw before for the implementation of spin locks in xv6。

 And the interlocked instruction that's one that's particularly convenient to use is something called。

 compare and swap。 The idea is that compare and swap takes three arguments。 The address of some。

 location of memory that we want to act on。 The value that we think it holds and the value that。

 we'd like it to hold。 And the semantics of compare and swap are that the hardware checks。

 The hardware first sort of basically sets an internal lock that makes only one compare and swap x。

 q to the time on a given memory location。 Then the hardware checks that the current value of that。

 location is indeed still x。 And if it still acts sets it to this third argument。

 which is going to be， x plus one。 And then the instruction yields one。 That's its value。

 If compare and swap observes that， the current value isn't x。

 then it doesn't change the value of the memory location and it returns zero。

 So this is basically an atomic if the location is x， set it to x plus one。

 And it has to be atomic because there's really two things going on。 The hardware is。

 checking the current value and setting it to a new value。 Any questions about compare and swap？

 I have a question。 If there would be a reader and our lock needs to continue， would W unlock reset。

 the value back to x？ W unlock if there's a writer， W unlock， which I'm afraid didn't show， sets end。

 zero because there can only be one writer。 If there's what read unlock does is use another compare and swap。

 to decrement in。 Okay， because what happens if a writer locks the lock between when x is being。

 computed and。 Say wait here。 No between the if and x。 Okay。

 it's I'm not sure I understand exactly what time you're asking， but it's absolutely a good。

 question。 What happens if W lock is called somewhere during this sequence？ And for me， the most。

 dangerous time for W lock to be called is after this check， but before the compare and swap。

 So let's imagine that read lock has gotten as far as seeing that x or L L R O N is zero。 Okay。

 so maybe we're right here and x is equal to zero。 We've already checked so the check is finished and then right at this time on another core。

 some other thread calls W lock and it actually gets its compare and swap in first。 So on the other。

 core， let's try to grab the right lock。 Compare and swap is going to see if L R O N is zero。 And。

 let's assume that N is zero so that this test is true and the compare and swap is on that other。

 core is going to set N to negative one。 So now the locks locked， but we still think that N is zero。

 in this code， even the locks locked。 And now we're going to execute now back on the reading core。

 we're going to execute compare and swap， but we're going to pass zero here。 Right。

 this is the value， we actually we're going to pass in the value we actually looked at。

 not the current value of N。 And when we looked at it， it was zero。 So we're going to pass zero here。

 And we're telling， compare and swap look， only add one to only set it to one if its current value is zero。

 But it's not zero at this point， it's minus one。 And so this compare and swap fails。

 does not modify， N return zero。 And so that means we'll go back to the top of the sleep and try again。

 of course now， and this minus one。 This might be related to the previous question of bits。

 but is it possible， for an interrupt to occur when that X plus one is being computed in the CAS parameter or CAS。

 parameter？ You mean before we actually execute CAS， but while we're computing its arguments。 Right。

 so like you compute or you pass in the X argument， and that's okay， but you。

 before you compute the X plus one or while you're computing X plus one， an interrupt occurs。 Okay。

 And so X plus one is wrong。 So even interrupt occurs while we're computing X plus one， that means。

 we haven't， the CAS is actually in instruction， it's a single machine instruction。 So if we're。

 computing S plus one， that means we haven't called CAS yet。 If the interrupt happens。

 and all kinds of things may happen， we're going to get the same， if we originally read zero here。

 right， then interrupt or no interrupt， we're going to pass one as this third argument。

 because the interrupt is not going to reach out and change。 This is a local， this X is a local。

 variable for this code。 So interrupt or context， which are anything， it's not going to change X。

 And so that means we're going to pass zero and one here。 And， you know， if n is still zero。

 then we'll set it to one。 And that's， that's what we want。 If it's not still zero， then。

 compare and so on， change it。 Right。 I guess you would have problems if you didn't set that local。

 variable then。 If you used LRO n here， LRO n plus one， you would almost certainly be in big。

 trouble， because then n could change under foot at any time。 That's why we actually grab a copy and。

 grab a copy here in order to sort of fix a specific value。 Yeah。 Yes。 Okay。 If two readers， okay。

 so I'd cover the case of whatever writer calls at the same， whatever。

 W lock is called the same time as R lock。 It's also interesting to wonder what if R lock。

 is called at the same time。 So supposing the n starts out as zero。 We know if two R locks are。

 called at the same time， what we want is for n to end up with value two and for both R locks to。

 return。 That's what we want， because we want two readers to be able to execute in parallel to use。

 the data in parallel。 Okay。 So they're both going to see zero at this point。 So at this point。

 both of， them are going to have x equal to zero。 They're both going to call compare and swap with zero and one。

 Only one of those two compare and swap。 So exactly one of those two compare and swaps will succeed。

 whichever one， you know， compare and swap is an atomic instruction。

 They're only one of them happens， at a time on a given memory location。

 So whichever compare and swap is first， we'll see， that n is equal to zero and we'll set it to one。

 The other cores simultaneous called R lock， its compare and swap will then execute and it'll still pass zero and one here。

 But n will now be equal to one。 And so the compare and swap will fail with the second core。

 and return zero。 The second core will go back to the top of this loop。 At this point。

 it will read one。 That's not less than zero。 So we'll go on to the compare and swap and now it'll pass one and two。

 and now the second read lock will succeed。 Both of them will have the lock。 So the first one。

 succeeded in the first stride。 The second one actually go back to the loop and try again。

 Any questions？ Oh， sorry。 So it is somehow possible then。

 So a bunch of reads come and they're reading， their stuff and then a write also comes and it also wants to write。

 But then some other reads， also come after the write。

 But then somehow the reads like outrun the write and the， write still has to wait to help。

 So with the sequences that a reader managed to acquire the lock， one or more readers have the locks。

 So now n， each of them， this is called a compare and swap， adds one to n for each reader。

 So now n is greater than zero because there's， multiple readers。

 If a writer tries to acquire the lock at this point， the writer's compare and swap。

 the compare value is zero。 So compare and swap will only change n to minus one if its current value is。

 zero。 But we know the current because there's multiple readers， the current value of n is not zero。

 and so the compare and swap will fail and return zero and the writer will sit here in this loop。

 basically waiting until n is equal to zero before its compare and swap will succeed and return and。

 give the lock to the writer。 So this certainly means the writer can be starved if there's a lot。

 of readers and may never be zero and so the right may never succeed。

 So that's a defect in this locking， scheme。 Thank you。

 I also have a question about the two reader scenario that I just mentioned。

 It appears that in the worst case， the reader that arrives second has to go through another。

 iteration of the loop。 It sounds somewhat wasteful。 I wonder if this generalizes to add writers。

 It certainly does。 They all have to get lost and start again。 You put your finger on why people。

 don't like this scheme if there's a lot of simultaneous reader。

 And so for the reason you just mentioned， OR lock， even if there's no writers at all。

 if there's lots of readers or there's readers on many， cores， OR lock can be very， very expensive。

 And one thing you need to know about the OR lock scheme。

 which I think we've already mentioned in class is that on a multi-core system， every core。

 has an associated cache。 We'll say it's the L1 cache。 So each core has a bit of cache memory。

 And whenever it reads or writes something， it sits in the cache。 So there may be lots and lots of。

 cores。 And there's some kind of interconnect network that allows the cores to talk to each other。

 Because of course， if lots of cores have some data cached and one of the cores writes that data。

 the writing core has to tell the other cores that they're not allowed to cache the data anymore。

 which is called invalidation。 So what actually happens if you have N， readers。

 N people calling OR lock at about the same time on N cores， they're all going to read N， sorry。

 this L-I-R-O-N value， and load this memory， equation into their caches。

 They're all going to call a compare and swap。 The first one to actually call compare and swap is going to modify the data。

 but in order for， to modify the data has to invalidate all these other copies。

 And so the compare and swap instruction， that one has to send out an invalidate message over this little network to each of the other N cores。

 And then it returns all the other cores， the N minus one cores。 They have their compare and swap。

 now actually have to reread again requiring traffic over the network， reread this data。

 this memory location， compare it with X and they'll have fail because they all call X was zero。

 Then the remaining N minus one readers go back to the top of the loop and all N minus one of them。

 again read the data and again one of them writes it。 So on each。

 so there's going to be N times through the loop once for each core trying to acquire the lock。

 Each of those trips through the loop involves order N messages on the network because at least。

 every copy of the cached L-I-R-O-N has to be invalidated。 And that means that the total cost。

 for N cores to acquire a particular lock even for reading is order N。

 And that means as you increase the number of cores for a popular piece of data， the cost for。

 everybody to lock it just once goes up， sorry it's order N squared。 The total cost in time。

 or messages sent over this interconnect is N squared。 And this is a very bad deal。

 You would hope that if you needed to do something 10 times。

 10 different cores needed to do something， especially given that they're just reading the list。

 they're not modifying it， you'd hope that， they could really run in parallel。

 That is the total wall clock time for 16 cores to read something。

 should be the same as the total wall clock time for one quarter read something because that's what。

 that's what getting parallel as a means is that you can do things at the same time。

 But here the more cores I try to read this， the more expensive the lock acquisition is。

 And so what's going on is that this style of locks has converted read-only access to data。

 You know the list is probably sitting in the cache already because nobody's modifying the list。

 right？ So the actual access to the list might only take a few dozen cycles。

 But if the data is popular， getting the lock can take hundreds or thousands of cycles because。

 of this N squared effect and the fact that instead of it being cached accesses。

 it's these accesses that have to go over the bus， this interconnect in order to invalidate and。

 do these cache coherence operations。 So these locks have turned a very cheap read-only access。

 to data into an extremely expensive read-write access to this data。

 And we'll probably completely destroy any possible parallel performance， if what you were doing。

 You know if the actual data was fairly simple to read。

 the lock will dominate and destroy parallel performance。

 So any questions about this performance story？ [silence]， In a sense。

 you know the bad performance of read-write locks is the reason for the existence of our CU。

 Because if this was efficient then there'd be no need to do better than that， right？

 But it's terribly inefficient。 And it's， there's two things going on。 One is the details of this。

 oh there needs to be a total of N squared trips through this loop if， we have N cores。

 it's sort of one way of looking at it。 The other way of looking at it is that， we're writing。

 you know regardless of the details of what's going on here。

 these locks have turned a read-only access which could be cached and extremely fast。

 into an access that one way or another involves a write， one or more writes。

 And writes are just much more expensive than reads if we're writing data that might be shared。

 with other cores。 Because a read for data that's not modified can be satisfied in a couple cycles。

 out of your own cache。 Any write to data that may be cached by other cores has to involve。

 communication between cores to invalidate other copies。 So no matter how you slice it。

 anything that involves a write to share data is a disaster for performance if you otherwise could。

 have been read-only。 So the details of this loop are sort of less important than the fact that it。

 did a write to share data。 So what we're looking for is a way to be able to read data。

 without writes。 We want to be able to scan that list without doing any writes whatsoever including。

 any writes that might be required to do some kind of locking thing。 We're looking for really。

 really read-only access to data。 Okay， so one possibility。

 that's not a possibility but it's sort of a thought experiment is we just。



![](img/a5823530e230b7c3ee90fda214e7fefe_3.png)

 have the readers not bother locking。 Occasionally you get lucky in a chance that the readers can read。

 stuff and that only writers need to lock。 So we'll just do a quick experiment to see whether。

 we could have a lock just have readers just read the list without locking it。

 So suppose we have this list and it has some strings， and， we're gonna read it。 Okay。

 so nothing goes wrong if there's no writer， right？ Just read the list， it's not a problem。

 So we got to imagine there's a writer and there's probably。

 three cases if you read a list while some other course modifying it。 So one case is that the。

 writer is just changing the content that is not adding or deleting。 Although necessarily a writer。

 is just changing the string to be some other string。 So one is the writers changing the content。

 two is the writer is inserting a new list element and the third case is if the writer is deleting。

 a list element。 And I want to examine these because we need a story for each and R。C。U。

 actually kind， of has a story for each。 So the danger。

 so I'm just talking about what goes wrong if somebody's。

 reading a list while on other course writing it。 If the writer wants to just change us this string。

 then the danger is that the reader will be actually reading the bytes of this string or whatever else。

 is in the list element while the writer is modifying the same bytes。 And so if we don't do。

 anything special the reader will see some mixture of the old bytes and the new bytes。

 And that's probably a disaster。 That's one case we have to worry about。 Another possibility is that。

 the writer is inserting a new element。 And of course what that means is that you know。

 supposing the writer wants to insert the new element at the head the writer is going to cook up some。

 new element， going to change the head pointer to point to it。 I'm going to change the new element。

 to point at the old first element。 So the danger here if a reader reads is reading the list while。

 the writer is inserting is that maybe if we really blow it the the writer may set the head pointer。

 to point to the new element before the new elements initialized。

 That is why it maybe contains garbage， for the string or some illegal pointer as the next element。

 So that's the thing that could go， wrong if a writer is inserting。

 So let's end up the writer's deleting then you know what it means。

 to delete an element is first to change let's say we're deleting the first element we changed the。

 head pointer to point to the second element and then call free on the first element to return this。

 to the free list。 And the danger here you know if the reader sees the new head pointer that's fine。

 they're just going to go on to the second element。

 So the first if the reader actually was looking at。

 the first element and then the writer freed it then the problem we have is now the reader is looking。

 at an element that's on the free list and could be allocated for some other use and overwritten for。

 some completely other use while the reader is still looking at this element。

 So from the reader point， of view now all of a sudden the elements filled with garbage instead it was expecting。

 So that's， a third case we have to if we want to have a lock we want to have absolutely no locks for readers。

 we have to worry about these three situations。 Now I'm not talking about writer versus writer。

 problems here because I'm just assuming for this entire lecture that writers still use locks。

 that there's still some ordinary like xv6 style spin lock here and writers acquired this lock。

 before doing anything but readers don't acquire any lock whatsoever。 Questions about these dangers。

 Okay the point is we can't just simply have readers read within locks but it turns out we can't。

 fix these specific problems and that takes us to rcu。

 And rcu has a couple of ideas in it that rcu is by the way it's as much a kind of approach to。

 concurrency concurrency control as it is a particular algorithm or it's a way of structuring。

 approach to structuring readers and writers so that they can get along with the readers not having。

 to take locks。 The general game with read copy update is we're going to fix those three situations。

 in which readers might get into trouble if there's concurrent writers and we're going to do it。

 by making the writers a little bit more complicated so the writer is going to end up somewhat slower。

 they still need to lock plus follow some extra rules but the reward will be the readers will。

 be dramatically faster because they can operate without locks and without ever writing memory。

 Okay so the first big idea in rcu is that in that first trouble situation we talked about before。

 where the writer is updating a list element the content of a list element we're going to actually。

 outlaw that we're going to say writers are not allowed to modify the contents of list elements。

 instead if we have a linked list like this with a couple of elements。

 if a writer wanted to update the content of element two instead of changing it in place。

 which it wouldn't do it would actually cook up it would call the allocator to allocate a new element。

 it would initialize the element completely so whatever new content you know we wanted to put here。

 instead of the old content the writer would set the next pointer on this new element so that this。

 new element is now completely correct looking and then in a single write to e1's next pointer。

 the writer would switch e1 from pointing to the old version of e2 to pointing to the new version of。

 e2 so the game is instead of updating things in place we're going to replace them with new versions。

 of the same data and so now a reader you know for readers gotten as far as e1 is just looking at。

 e1's next pointer the reader is going to either see the old next pointer which points to e2 and。

 that's fine because nobody was changing e2 or the reader is going to see the new next pointer。

 and look at the new list element and either way since the writer initially fully initialized this。

 list element before setting e1's next pointer either way the reader is going to see like a correct。

 next pointer that points to e3 so the point is the reader will never see a string that's in the。

 process of being a content that's in the process of being modified is any questions about this particular idea。

 what about the same sorry okay i can go ahead um will the link between e2 and e3 be deleted or will。

 it be left during case that a reader somehow reached e2 now we're just going to leave it。

 we're just saying oh i'll come to this this is a excellent question um and it's actually the main。

 piece of complexity in rcu but for now we're just going to imagine that e2's left alone for the moment。

 the link from e2 to e3 we don't need to worry about it anyway right because that's a part of e2 and like。

 in normal implementations we just free that anyway like with no rcu involved we don't ever need to。

 worry about that link right but the danger is that's that just before we changed this next pointer。

 that some reader had followed the next pointer to e2 right so what we're all what we're worried about。

 here is that oh some some reader on some course actually right now reading e2 so we'd better not。

 free it right away right right that's all i think that's all we're saying is you better not free e2。

 right away just leave it alone um as a piece of jargon um the right the swap of e1's next。

 pointer from the old e2 to the new e2 um i in my head i call this a committing right there's a。

 there's then part of the reason why this works is that with a single committing right which is atomic。

 like rights to pointers on the machines we use are atomic in the sense that either the right to the。

 pointer happen or didn't happen from the perspective of readers because they're atomic basically without。

 one instruction with the one atomic store we can it's an ordinary store but it's indivisible。

 we switch e1 from point to old the next pointer from point to old one the new one and that right is。

 what sort of commits us to now using the second version this is a very basic technique a very。

 important technique for rcu and um what it means is that rcu is really mostly applicable to data。

 structures for which you can have single committing rights so that means there's some data structures。

 that are quite awkward in the scheme like a doubly linked list um where every element is pointed to。

 from two different pointers now we can't get rid of uh list elements with a single committing right。

 because there's two pointers to it we can't on most machines you can't atomically change。

 two different memory locations at the same time um so doubly linked lists are not so good for rcu。

 a data structure that is good is a tree right if you have a tree of。

 a tree of nodes like this then we can do you know supposedly we want to change。

 want to modify this value down here what we can do。

 there's some head to the tree what we can do is cook up a new a new version of this part of the tree。

 here and with a single committing right to the head pointer switch to the new version of the tree。

 and so the new version of the tree which will you know the writer will allocate would sort of create。

 um can actually share for convenience can share structure the unmodified part with the old tree。

 and then with a single committing right we're going to change the head pointer to the tree head。

 pointer to point to the new version um but for other data structures that don't look like list。

 or trees it's not so easy to use or see you okay um so that's the first idea any last questions。

 the second idea， um one of the problems with uh one of the potential problems with uh。

 the scheme i just described， and we're going to cook up a new e2 prime and what i said was oh well we'll initialize the content for。

 e2 prime and we'll you know set its next pointer correctly and after that we'll set e1's next pointer。

 to point to e2 um as you may recall from discussions of xv6 by default there's no after that on these。

 machines the compiler and the hardware all basically all compilers and many microprocessors reorder。

 memory operations so if you simply you know say we allocate a new element。

 and we just wrote this c code you know e arrow next equals you know e3 and then e1 arrow next。

 equals e this is not going to work well this is not going to work reliably it's going to work fine。

 when you test it um but it won't work in real life all the time occasionally it'll go wrong and。

 the reason is that uh the compiler may end up reordering these writes or the machine may end up。

 reordering these writes or the reading code which reads these various things the compiler or the machine。

 the microprocessor may end up reordering the reader's reads and of course um if we set e1 arrow next。

 to point to e2 before we initialize the content of e2 so that it's string it holds or is next pointer。

 point off into space then some readers going to see this pointer follow it read garbage and crash。

 so the second idea is that both readers and writers have to use memory barriers。

 now even though we're not locking or really because we're not locking。

 read the writers and the readers have to use a barrier and for writers the place the barrier has。

 to go is before the committing write so we need a barrier here that tells the hardware and the。

 compiler look all the writes before this barrier please finish them before doing any writes after。

 the barrier so that e2 is fully initialized before we set e1 to point to it and on the read side。

 um the reader needs to load e1 arrow next into some you know temporary location or register so。

 we'll just say you know register one equals e1 arrow next um then the reader needs a barrier。

 and then the reader is going to look at r1 arrow it's content and r1 arrow next and with this。

 barrier on the reader says is don't issue any of these loads until after we've completed this load。

 so the reader is going to um look at e1 arrow next and either get the old e2 or the new e2。

 and then the barrier says that you know only then are we going to start looking at uh only after we've。

 grabbed this um all these reads have to execute after this read and since the writer guaranteed to。

 initialize the content before committing the pointer to eat the new e2 that means these reads if this。

 pointer points to the new e2 that means these reads are guaranteed to see the initialized content。

 okay um so we also a little bit of this， sorry but how can you sorry oh yeah i was just i was confused about the reader so how how can you。

 read r1 i i run like anything before you read r1 i guess like how how how would they so wrong。

 yeah i guess like if even if it reordered it how would how do you be able to read r1x。

 before it read e1 next， you i think you've stumped me um yeah i mean what were you pointing out is that before you even。

 know what the pointer is uh you can't possibly actually issue the reads the um a a a a a possibility。

 is that whatever this pointer points to maybe it's already cached on this core due to some maybe。

 you know this memory was had been you know a minute ago used for something else something totally else。

 and we have an old version of this cached on our core um yeah at the address at this address but。

 for some previous use of the memory um if this read was to use the old cached value。

 i'm not sure this can happen just making this up for you but if this read could use the old。

 cached value then we'd be in big trouble um and i don't know if the machine would actually do that。

 or whether um， another possibility is that the compiler you know。

 the real answer is i don't know as you go off and think about uh what a specific example would be。

 okay okay i see the cached version makes sense yes yeah i'm not actually completely sure it could。

 could happen in real life um that's a good question。

 okay um so that's the second idea the third problem we have which something somebody raised before is that。

 the writer um is going to swap the e1 pointer to point to the new e2 but there could be readers。

 um you know who started looking at you follow this pointer just before we changed the writer changed。

 it who were still looking at e2 um we need to free this list element someday。

 but we'd better not free it while some readers still using it so we need to somehow wait until the last。

 reader has finished using e2 before we can free it。

 and that's the sort of third and final main problem that our cusolves is how long should the。

 writer wait before it frees e2 um there's you could imagine a number of ways of doing this uh for。

 example we could put a little reference count in every list element and have readers incremented。

 and have readers wait readers incremented when they start using list element decrement when。

 they're done using the list element and have the writer wait for the reference count on this element。

 good is zero um we would forget that instantly because the whole point of rcu is to allow reading。

 without writing um because we know that if lots of readers are uh changing this reference count。

 it's going to be terribly expensive to do the rights involved in maintaining a reference count。

 we absolutely don't want reference counts um another possibility would be use a garbage collected language。

 and in the garbage collected language you don't ever free anything explicitly instead the garbage。

 collector does the book keeping required to decide if any thread for example or any data structure。

 has or still has a reference to this element and the garbage collector once it proves this element。

 can't possibly be ever used again only then will the garbage collector free this so that's another。

 uh quite possibly reasonable um scheme for deciding when to free this list element you know vimics which。

 uses rcu it's not written in a garbage collected language so and we're not even sure the garbage。

 collection would be would improve performance um so we can't use a standard garbage collector here。

 and instead uh rcu uses another uh sort of a trick that works well in the kernel。

 for delaying freeze um， and so that， idea is that the readers and writers have to um each follower rule that will allow writers to delay。

 the freeze um readers are not allowed to hold a pointer to rcu protected data across a context。

 switch so a reader is not allowed to hold a pointer um to one of those list list elements across。

 a context switch so the readers um they cannot yield the cpu， in a rcu critical section。

 and then what the writers do is um they delay the free， until every core。

 has context which is at least once， um it so this is easy enough like this is actually also a rule for spin locks and a spin。

 lock critical section you can't yield the cpu um but nevertheless you do have to be a bit careful。

 um this is a little more involved um but it's relatively clear when each each core。

 knows this context switching um and so this is a pretty well defined point for the writer to have。

 to wait for um and just require some implementation this also requires this may be a significant delay。

 it may be a millisecond or a significant fraction of a millisecond that the writer has to wait。

 before it's allowed to free that list element to be sure that no reader could possibly still be using。

 it um people have come up with a um bunch of techniques for actually implementing this wait。

 though most the straightforward one the paper talks about is that the writing thread simply。

 arranges with the scheduler to have the writing thread be executed briefly on every one of the。

 cores in the system and what that means is that that um every one of the cores must have done a。

 context switch during this process um and since readers can't hold self-accross context which is。

 that means that the writer is now weighted long enough um and so the way the actual writer。

 code looks like is um the writing code does whatever modifications it's going to do to the data。

 and then it calls this um synchronize rcu call， which actually implements two。

 and then the writer uh frees whatever the old element was and so that means that you know the。

 writer is doing whatever it's doing you know at this point let's say it's doing the you know e1。

 arrow next um is equal to the new list element um and so you know uh。

 this synchronize rcu causes a forces a context switch on every core um so any core that could have。

 read you know any core that could have read the old value must have read it at this point um。

 must have read it at this point in time if after that point in time we've done a context switch on。

 every core that means that no core that read the old value could still have a pointer to that value。

 at this point in time due to rule one and that means that we're allowed to free the old value。

 any questions？ you may object that this synchronize rcu will take a significant perhaps fraction of a。

 millisecond that's quite true um it that uh so that's too bad um one of the。

 justifications is that writing you know for rcu protected data writing is going to be。

 relatively rare so the fact that the rights take longer may not well probably not effect overall。

 performance very much um for the situations in which the writer really doesn't want to wait。

 there's another call um that that defers even the wait um called call rcu。

 and the idea is you pass it the um in the usual use case you pass it a pointer to the object you。

 want to free and then a callback function that just calls free um on this pointer and the rcu。

 system basically stashes away the call rcu stashes away um these two values on a list and then。

 immediately returns um and then does some bookkeeping uh typically involving basically looking at the。

 counts of how many contexts which have occurred on each core um the system uh sort of in the。

 background after call rcu returns doesn't bookkeeping to wait until all cores a context which and then。

 calls this call back function with disarguement and so this is a way of avoiding the wait because。

 this call returns instantly um on the other hand you're discouraged from using it because um now。

 this list that um if people if the kernel calls call rcu a lot then the list that holds these uh。

 values can get very long and it means that there may be a lot of memory that's not being freed all。

 the day all the uh this list this list goes very long each list element of a is uh has a pointer in。

 it that should be free the pointers from an object that should be freed and so under extreme。

 circumstances you can run a system if you're not careful a lot of calls to rcu call rcu can。

 run a system out of memory because all the memory ends up on this list of deferred freeze。

 so people don't like to use this if they don't have to， okay um to uh please ask questions if uh。

 if you have questions so this doesn't um this prevents us free that prevents us from freeing。

 something that somebody's still using yes but it doesn't prevent us from modifying like having。

 the reader see a half baked version of something because it's being modified right idea one prevented。

 that yeah okay so they think the idea behind idea one is that instead of updating list element in。

 place which would absolutely cause the problem you mentioned when writers are not allowed to update。

 rcu protected data in place instead they cook up a new data element and sort of swap it into the。

 data structure with a single committing right oh oh and the swap in will be atomic so there's no。

 problem of like because that's a single pointer right which is atomic or it is overwriting a string。

 it's completely not atomic that makes sense other questions um does condition one in um。

 idea three mean we need to be careful about how much work we put inside those protected sections。

 since it kind of hogs the the core for that entire section yes yes so so this is uh that's right so。

 readers in the sort of rcu critical section while they're looking at the protected data they can't。

 context switch and so you're um you know you want to keep those critical sections short now。

 and then that's a consideration um the way it plays out though is that the way rcu's been deployed。

 is typically that there'll be some piece of code in linux that was protected with ordinary locks。

 or read write locks and somebody you know for some workloads um we'll see oh that lock is a terrible。

 performance problem and they're gonna replace the locking critical section with an rcu critical。

 section although sometimes it's more involved than that and since locking critical sections were。

 already was extremely important to make them short because while you hold a lock there may be。

 lots of other cores waiting for that lock so there was a lot of pressure to keep ordinary lock。

 critical sections short because rcu critical sections are often sort of revised lock critical。

 sections things that used to be lock critical sections they tend to be short also um and you know。

 that means that that you know not always but usually there's not a not a direct worry about keeping。

 the rcu critical section short although it is a constraint that they're real constraint actually。

 so you're not allowed to hold pointers over con pointers to rcu data over context switches。

 and that's actually a let me you can't for example read the disc and wait for the disc read to complete。

 while while holding on a pointer onto a pointer to rcu protected data um so it's not quite so much。

 the or the thing that usually comes up is not the length of the critical section so much as。

 the prohibition against yielding the cpu okay， let's see so just to kind of firm up but i all the stuff i just talked about um here's a。

 kind of what you would see in a simple use of rcu so this is code you might see for reading a list。

 um an rcu protected list and this is the code you might see it on the right side if。

 for code that just wants to um the particular case of replacing the first list element so on the。

 read side um there is actually this um these read lock and read unlock calls those do almost nothing。

 almost nothing um the only the only little thing they do is set a flag that says or rcu read lock sets。

 a flag that says if a timer interrupt happens please don't context switch because i'm in the middle of a。

 rcu critical section so that's all it really does is set a flag that prohibits timer interrupt。

 context switches interrupt may still happen but it won't context switch and then read unlock。

 unsets that flag it really gets a you know counter of nested rcu critical sections。

 so these two functions are extremely fast and do almost nothing um and then this loop would sort。

 of scan down the uh um our list this is the call that um inserts the memory barrier so what rcu。

 this really boils down to just a couple of instructions it just reads um it grabs a copy of this pointer。

 for memory issues a memory barrier and then returns that pointer um and then we can look at the content。

 and go on to the next list element so the readers uh wait simple the writer is a little more involved。

 writer still um you know the rcu doesn't help writers avoid interfering with each other so writers。

 still have to have some way of making sure only one writer modifies the list at a time in this case。

 i'm just imagining we're going to use uh ordinary spin locks so the writer requires the lock。

 if we're replacing the first list element we need to save a copy at the beginning because。

 we're going to need to eventually free it so we say this copy of the oldest element and now we're。

 this code plays that trick i talked again about allocating a complete new list element to hold。

 a sort of updated uh content so we're going to allocate a new list element we're going to set its content。

 we're going to set the next pointer um to the next pointer in the old first list element because。

 we're replacing it and then this rcu assign pointer uh issues a memory barrier so that all these。

 these writes happened um and then sets uh the pointer pointed to by this first argument to be。

 equal to that so basically this just issues a memory barrier and then sets head equal to e。

 and now we can release the lock we still have a pointer to the old first list element。

 called synchronize rcu to make sure every um cpu that could have grabbed a uh pointer to the。

 oldest element before we did the committing write has yielded the cpu and therefore given up its。

 pointer to rcu protected data and now we can free the old this element， any questions， all right um。

 there are rcu one thing to note about this is that while in the reader while we're allowed to look。

 at this list element inside the loop here one thing we're not allowed to do is return the list。

 element so for example we using rcu we couldn't write a lookup a list lookup function that returned。

 either the list element or a pointer into um data held in the list element like a string that was。

 embedded in the list element um uh because then we'd be in then we would no longer be in control。

 you know it has to be the case that we don't look at rcu protected data outside um this rcu。

 critical section or we don't do a context which if we just write off generic functions and returns。

 a list element then for all we know the caller i mean you know maybe we can persuade the caller。

 to follow some rules too but um for all we know uh the caller may context switch or。

 or we'd run into trouble either we call rcu read unlock before returning the list element。

 which is illegal because now a timer interrupt could force a switch or we don't call rcu read unlock。

 so the use of rcu sort of um does put some additional constraints on readers that。

 uh wouldn't have existed before a question about that yes so are you saying in particular that if。

 we had some form of uh like read element at index i method that there's no way to structure this。

 so that it could return the value held by the node at element i you could return a copy。

 so what would work you know if ero x is a string we could return a copy of the string and that's fine。

 um what would be a violation of the rcu rules is if we returned a pointer to this very string。

 sitting inside you know or a point it would be a mistake to return a pointer into e somewhere into e。

 like if the string is stored inside the list element we better not return a pointer to that string。

 um because then uh uh and it'll be we have to not context switch while we're holding a pointer。

 into rcu protected data and the you know the convention is you know you just use that data。

 within this critical section and so it would almost certainly be breaking the convention or this set。

 up would have to be much more complicated if we ended up returning pointers into the protected data。

 thank you um the i just want to sort of return briefly to the performance story。

 it's it's um it's hard to characterize sort of what the performance is i mean in a sense。

 the let's see the the overall performance story is that if you use rcu reads are extremely fast they。

 just proceed at you know whatever they have sort of no overhead above the ordinary overhead of。

 looking at that data so if your list is a billion elements long yeah reading the list will take a。

 long time but it's not because of synchronization it's just because you're doing a lot of work um。

 for readers so you can almost view rcu is having zero overhead for readers and the。

 exceptions are minor rcu readlock you know just a tiny amount of work to set this flag saying no。

 context which is and rcu debufference issues in memory barrier which。

 actually might slow you down by dozens a few dozen cycles but it much cheaper than a lock。

 the performance story for writers is much sadder you have to do all the stuff you always had to do。

 using locks in fact kept it acquired released locks in the writer um and you have this potentially。

 extremely expensive called or time-consuming called the synchronized rcu in fact you can give。

 up you know internally synchronized rcu gives up the cpu so you know doesn't spin necessarily。

 but it may require a lot of elapsed time waiting for every other core to context switch。

 so depending on the mix of reason writes um and how much work was being done inside the read critical。

 section the uh performance increase varies tremendously from um much much faster if these。

 critical sections were short and there's few writes to perhaps even slower um if writes are very common。

 and so when people apply rcu to kernel stuff they actually you absolutely have to do performance。

 tests against a bunch of workloads in order to figure out whether using rcu is a win for you。

 because it's so dependent on the workload， i have a maybe a tangential question but。

 we've seen that i guess when there's multiple cores being used there's some added complexity to。

 our usual implementations and it's often the like these atomic instructions kind of come to the rescue。

 and that's assuming there's one shared memory system but i wonder like what happens if a machine。

 is trying to maintain like multiple ram systems how does it unify those， the ordinary um well。

 at a uh at the level we're talking about the machine has one ram system。

 okay the you know yeah it's um for all those sort of ordinary computers you would buy that have。

 multiple cores you can pretty much program them as if they were just one ram system shared among all。

 the cores that's the logical model the hardware provides you at physical levels not like that。

 often um there's plenty of machines out there that have this physical arrangement we have a CPU chip。

 so here's one CPU chip maybe with lots of cores on it right and you know you can get CPU chips with。

 i don't know how many cores these days 32 cores say let's say you want to build a 64 core machine you。

 can only buy 32 core chips while you can make a board they could have two sockets for chips on it so。

 now we have two chips um the fastest way to get at memory is to have the memory more or less as。

 directly attached to the CPU chip as possible so what you would do is you'd have like a very fat set。

 of wires here to right next to the chip a bunch of ram so it has direct access and of course this。

 chip's gonna want its own ram also right so this is i'm just drawing a picture of what you would see。

 if you opened up a pc with two processor chips in it ram but now we're faced with a problem what。

 happens if a software over on this chip uses a memory location it's actually stored in this ram。

 so in fact there's also a inner connect between these two chips generally an extremely fast inner。

 connect like gigabytes per second um and the chips are smart enough to know that certain physical。

 memory locations are in this bank of ram and other physical locations physical memory addresses are。

 in this bank of ram and if software here uh uses a physical address is over in this one the chip is。

 clever enough to send a message just basically a little network send a message over to this chip。

 selling it look i need to read some ram please do it and go read its ram and send the result back。

 you know you can buy four chip arrangements with the same thing with a complex inner connect like。

 this so there's a huge amount of engineering going on in order to map the straightforward shared ram。

 model onto what sort of feasible to build with higher performance um in real life and fit in。

 two or three dimensions um that answer your question yeah that provides a lot of context thank you。

 yeah， okay， um， right any questions on the actual technique。

 all right so um as i'm i'm sure you've got in the sense of our cus not universally applicable。

 there's not you can't just take every situation in which using spin locks and getting bad parallel。

 performance and convert it to rcu and get better performance because the main reason is it completely。

 doesn't help rights makes them slower now really only for helps performance if you if the reads。

 outnumber the rights considerably um it has this restriction that you can't hold pointers to protect。

 the data across sleep which just makes some kind of code quite awkward if you actually need to sleep。

 you may then need to re-look up whatever it is you know to do another rcu critical section after。

 the sleep completes in order to look again for the um for the data that you originally were looking at。

 assuming it still even exists so that just makes code a bit more complicated um。

 the data structures the the most straightforward way to apply it is the data structures that。

 have a structure that's amenable to single committing rights for updates you can't modify things in place。

 so you have to replace stuff um and so you you know list and trees but uh not more complex data。

 structures the paper mentions some more complicated ways like sequence locks to be able to um update。

 stuff in place you know despite readers that aren't using locks but they're a good doing more。

 complicated and the situations under which they actually improve performance are more restricted。

 um another subtle problem is that readers can see stale data。

 without any obvious bound on how long they can see stale data for because if some reader。

 gets a pointer to a rcu protected object just before a writer replaces it。

 the reader may still hold on to that data for quite a long time at least on the scale of。

 modern computer instructions um and a lot of the time this turns out not to matter much。

 but the paper mentions some situations which I actually don't really understand。

 in which people expect rights to actually take effect after the right completes and therefore on。

 which readers seeing stale data is a bit of a surprise。

 um you may also as a separate topic wonder what happens if you have right heavy data like rcu's。

 all about read heavy data but that's just one of many situations you might care about。

 you're getting parallel performance um you also care about right heavy data actually in the。

 extremes in some extreme cases of right heavy data you can do quite well there's no。

 technique I know of for right heavy data that's quite as universally applicable as rcu。

 but there are still ideas for for coping with data that's mostly written so the most powerful。

 idea is to restructure your data restructure the data structure so it's not shared。

 and sometimes you can do that sometimes the sharing is just completely gratuitous。

 and you can get rid of it once you realize it's a problem but it's also often the case that。

 there that while you do sometimes need to have shared data that the common case doesn't require。

 different cores to write the same data even though they need to write some of the data a lot and so。

 you've actually seen that in the labs in the locking lab in the kia lock part of the lab you。

 restructured the free list so that each core has a dedicated free list thus converting a right heavy。

 data structure the free list into one that was sort of semi-private per core so most of the times。

 cores just have to don't conflict with other cores because they have their own private。

 free list and the only time you have to look at other free lists is if your free list runs out。

 so there's actually many examples of this way of dealing with right heavy data in the kernel。

 I'm the owner of the allocator and Linux is like this Linux is scheduling lists。

 there's a sort of separate set of threads for each core that the scheduler looks at most of the time。

 and cores only have to look at each other's scheduling lists if they run out of work to do。

 another example is statistics counters if you're counting something and the counts go change a lot。

 but they're rarely read that is the counter truly dominated by rights not reads you can restructure。

 your counters so that each core has a separate counter and so these core just modifies its own。

 counter when it needs to change the count and if you want to read something then you have to go out。

 and lock and read all the per core counters so that's a technique to make rights very fast。

 because the writers just modify the local per core counter but the reads are now very slow。

 and again you know but if if your counters are right heavy that's just the counters off and on。

 that could be a big win shifting the work now to the reads。

 so the point is there are techniques even though we didn't talk about them much there are also。

 sometimes techniques that help for right intensive worklings。

 to wrap up the RCU the stuff we read about in the paper is actually a giant success story for Linux。

 it's used all over Linux to get at all kinds of different data because it just turns out that。

 read and sort of read mostly data read intensive data is extremely common like。

 cached file blocks for example and mostly read so a technique that speeds up only reads is。

 really very widely applicable and RCU is this particularly magic there's lots of other。

 interesting concurrency techniques synchronization techniques RCU is magic because it completely。

 eliminates locking and writing for the readers so that's just like a big breakthrough compared。

 to things like read write locks which were the previous state of the art and the key idea that。

 really makes it work is the sort of garbage collection like deferring of freeze for the what they call。

 the grace period until all the readers are guaranteed to be finished using the data so you can。

 as well as a synchronization technique it's actually fair to view it as a very much so as a kind of。

 specialized garbage collection technique and that is all I have to say so I'm happy to take questions。

 oh sorry can you explain the the stale data for readers so I don't understand why how that can。

 happen because you you're reading your critical session and you just get whatever data is there。

 at that point and then you just leave yeah it actually usually is not a problem but。

 the reason why it ever might come up well ordinarily you know if you have code that。

 says x equals one and then you you know print done gosh it's pretty surprising if after this point。

 someone reading the data sees that value before you set it to one right that's a maybe a bit of a。

 surprise right well there's a sense in which RCU allows that to happen right if this is really。

 you know what we're really talking about is you know list replace whatever you know find the。

 element that has wanted it and change it to two with our you know using RCU right after that finishes。

 and we print oh yeah we're done if there's some reader that was looking at the list right they may。

 have you know just gotten to the list element that held one that we replaced with two and then a good。

 deal longer you know and then they do the actual read of the list element you know they look at。

 whatever the content is in the list element after we've done this you know they're reading the list。

 element only at this point later in time and they see the old value so if you're not prepared for。

 this so this is like a little bit odd now I mean they mean they may even do a memory barrier right。

 I mean it's not a memory barrier issue it's just like and indeed most of the time it doesn't matter。

 I see so this is when this replace is very close so like the read somehow like starts before the。

 replace but it just takes a while and yes yeah the reader is slower than the writer or something now。

 you know be I think this mostly doesn't matter because after all the reader and the writer were。

 acting concurrently and you know if two things happen currently usually you you would never have。

 imagined that you could have been guaranteed much about the exact order if the two operations were。

 in book concurrently I see the paper claims you I mean the paper has an example in which they said。

 it matters it turned out to cause a real problem although I don't really understand。

 why that was I see this makes sense and my other question was it's called RCU because of。

 idea one is that right read copy update yes I believe it's because of idea one that is that。

 instead of modifying things in place you make a copy and you sort of。

 a copy not the not the real thing right this makes sense thank you so much。

 yes so at the beginning of lecture or towards the beginning we talked about the of and squared。

 runtime for the cash coherence protocols for updating the read write locks isn't this also a。

 problem with spin locks where yeah okay so what is the reason why we didn't discuss that that。

 aspect why we didn't yeah or like is there a reason that that still exists or like what do。

 spin locks do to address that nothing oh okay and locks are hideously expensive if there。

 or standard spin locks like xv6 has are extremely fast if the lock is not particularly contended。

 and terribly slow if lots of course try to get the same lock at the same time gotcha okay。

 this is one of the things that makes life interesting and you know there's。

 there's there's locks that are have better scaling but worse。

 that they have better high load performance but worse low load performance。

 but i'm not aware of a lock that is anyway it's hard it's hard to get this stuff right。

 it's hard to get good performance in these machines。

 other questions just might be over related but can there ever be like lock against between。

 multiple systems like in that just sort of like not just contained to one system maybe like。

 multiple servers perhaps there are absolutely distributed systems in which there's a sort of。

 locking in which the sort of universe of locks spans multiple machines。

 one place this comes up is in distributed databases where the data you know you have。

 many you display your data over multiple servers but if you want to have a transaction。

 that you know uses data that's you know in different pieces of data on different servers。

 you're going to need to collect locks that were you need to basically collect locks from multiple。

 servers another place it comes up although there's been a number of systems that are。

 essentially try to mimic shared memory across independent machines with machines you know if。

 i use a memory that's in your machine then you know there's some infrastructure stuff that causes。

 my machine to talk to your machine and ask for the memory and you know then the game is usually to run。

 existing parallel programs on a cluster of workstations instead of on a big multi-core machine。

 hoping this is going to be cheaper and you know something needs to be done about spin locks there。

 or whatever locking you're going to use and so people have invented various ways to make the locking。

 work out well in that case too you're using like eks that are not you know often not quite the same。

 as this although the pressure to avoid the pressure to avoid costs is even higher in that， case。

 anything else， thank you you're welcome。