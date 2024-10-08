# P13：Lecture 13： Memory 1 Address Translation and Virtual Memory - RubatoTheEmber - BV1L541117gr

 Okay， let's get started。

![](img/4debe4e4bf5fd22a7051820601bb8ab1_1.png)

 We're going to finish up with deadlock， and in particular looking at deadlock avoidance。

 and prevention algorithms。 And then we're going to switch gears and look at memory management。

 This is the first of several lectures we're going to have on address translation and virtual。

 memory。 Okay。 All right， so remember that deadlock is basically a form of starvation。

 That with starvation， we have threads that wait indefinitely， like a low priority thread。

 that waits on a high priority thread。 And the key difference between deadlock and starvation is that in deadlock。

 we have a circular， waiting of resources。 So here we have thread A that is waiting for resource two。

 which is being held by thread， B， which is waiting for resource one。

 which is being held by thread A。 The second key difference between deadlock and starvation is that while starvation can。

 end， right， those high priority threads that are blocking that low priority thread can， leave。

 with deadlock， we have to have external intervention to stop it。 Otherwise， it'll just。

 it'll remain in that situation forever。 Okay。 Now， remember。

 there are four requirements for deadlock。 All right。 First being mutual exclusion。

 the second being hold and wait， the third being no preemption。

 and the fourth being circular waiting。 Remove any of those conditions and you don't have deadlock。

 All right。 So here's a hint。 You might see a question about this on the midterm where you're given a situation where。

 there's preemption。 Can deadlock occur if we have preemption？ No。 Right。 Likewise。

 if there isn't a circular waiting， then we can't have deadlock。

 So the other way to think about this is that these might be some of the things。

 If we can guarantee that our system always has preemption， then we can guarantee that our。

 system will be deadlock free。 Similar if we can guarantee that there's no circular waiting for resources。

 we can guarantee， that we won't have deadlock。 Okay。

 So some of the techniques that we can use to prevent deadlock are to make threads request。

 everything that they need at the very beginning。 Right。 But that's not practical。 Right。

 If you tell programmers， request everything that you might possibly potentially need， and。

 if you get it wrong， I'm going to kill your job after it's run for three hours。

 They're going to overestimate。 And so this will lead to poor utilization and low efficiency。

 Another alternative is to force all threads to request resources in some order。 Right。

 If we can guarantee that everybody does their requests in some order， then we don't have， a cycle。

 Right。 We won't have a cyclic request for resources。 We've removed one of those four conditions。

 and so we won't have deadlock。 We might have starvation in our system for other reasons。

 but that can resolve itself。 So one example would be that we impose some lexicographic ordering on lock acquisition。

 So we say you do X dot acquire， then Y dot acquire， then Z dot acquire。

 So that bans us from the situation where one thread holds X and wants Y and the other thread。

 holds Y and wants X。 Because that would not be lexicographic ordering。

 We can do this across resources to say， first you always have to request all of the memory。

 that you need。 Then you request all the disk resources you need， then all the printer resources。

 and， all the network resources， and so on。 By guaranteeing that order。

 and you can't go back and request something earlier， again。

 we won't have a cyclic waiting on requests for resources。 And thus we won't have deadlock。

 Any questions？ Okay。 So another approach is to say， I'll just request all of the resources at once。

 So here I've modified it， so instead of doing thread A doing X dot acquire， Y dot acquire。

 and B doing Y dot acquire， and X dot acquire， we instead call this primitive acquire both。

 So A will just acquire X and Y， and B will acquire Y and Z。

 And we'll say that those occur atomically。 So either get both X and Y or you don't。 Right？

 Now what happens if I want to add another， like， I don't know， I want to add W。 Right？

 And maybe I need acquire triple。 And then I want to add， I don't know， U to it。

 So now I need to acquire quad。 Right？ Well， another way to think about this is that's just why don't we have a guard around the。

 acquisition of the locks？ So we'll have， you know， a Z will be our guard new text。

 And so you acquire Z， then you acquire all the locks you want， then you release Z。 Right？

 And so now it doesn't really matter what the order is inside this critical section， because。

 only one thread is going to be able to acquire the locks at a time。 Right？ So another way to do it。

 as I said， is to have a consistent ordering。 So we assign some lexic， in this case。

 a lexical graphic ordering that you go from A to Z in， acquiring your locks。

 So that bans B from doing this。 You can't do acquire Y then acquire X。 So instead。

 B has to do acquire X and then acquire Y。 Now what about the releases？

 Does it matter that we're releasing X before we release Y？ Yes？ No？ All right， let's do a poll。

 How many people think that the order that we do， the releases， does not matter？ Raise your hand。

 Okay？ How many people think the order that you do the release does matter？ Okay。 Guess what？

 You're both right。 Everybody's right。 So from a semantic standpoint， it doesn't matter。

 It doesn't matter whether we release one lock and then release another lock。

 But what would happen if we release X while thread A is waiting for Y or waiting for X。

 and then waiting for Y？ Right？ It's going to wake up， grab X because now X is free。

 and then go to grab Y and find， oh， why is being held？ Right？

 And so then it'll just go back to sleep， then we'll release Y and then we'll come back context。

 which again and wake it up。 If we flip it around and we release Y first and then release X。

 then when A wakes up because， it can now access X， it'll grab X and then it'll go in and acquire Y。

 So from a semantic standpoint， ordering doesn't matter。

 From a performance and efficiency standpoint， order does matter。

 So we want to avoid the number of context which is and wait and queuing that we have。 Questions？

 All right。 Okay。 So again， remember another example of where we can do ordering was our train network where。

 we have these trains that are all trying to turn right。

 And we can simply set a dimension ordering rule that says first you go and route east， west。

 then you're allowed to route north south。 And that disallows this train that's going north south and then trying to go east west。

 and this train that's going north south and then trying to go east west。

 And so that removes the ability for us to have deadlock。

 And the great thing about this is my multiprocessor network that this was developed for actually。

 are multi-dimensional。 So they may be like hypercubes。

 And so you have XYZ directions and you just order。 So you say you route first in the X。

 then you route in the Y， then you route in the Y， then you route in the Z。

 And so that avoids us having deadlock in these networks。

 And you extend them infinitely and they wrap around and all that。 Okay。

 So let's look at some techniques for recovering from deadlock。 So first is， you know。

 we could terminate the thread。 Forces to give up its resources。

 So if we go back to our singling bridge example， you've got the two cars that are sitting there。

 in a stalemate， you know， no one can go forward because the other car is blocking the segment。

 it has to acquire。 And the simple solution is Godzilla comes up from the ocean。

 picks one of the cars up， throws it into the ocean， and now the cars can go。 Deadlock resolved。

 Okay。 So it's not so good for the people that were in the car that are now in the ocean， but you。

 know， we solved the problem。 Not really。 The bigger issue here is that oftentimes， right。

 we require mutex because we want to modify， some state。

 And we want to do it in a way that's atomically that occurs atomic because we might be doing。

 something that creates inconsistencies。 Like we're transferring money from one bank account to another。

 And we also need to update the branch bank account branch of the bank's account balances。

 So if we just take the lock away and let somebody else run。

 we're going to be operating on inconsistent， data。 So in general。

 this is not a good approach to try and do。 So another approach that we could do is to preempt the resources without actually killing。

 the thread。 So we've seen this already， right？ You know， we have one CPU and we preempt that CPU。

 take it away from the thread that's running， save all the state that's thread specific in the CPU out to memory。

 load the state for， the new thread， and then we run it。

 So maybe we can do that with some of these other resources。

 It might not work for like a lock or something， but it could work for something like memory。

 We'll come back to that in just a moment。 And we're going to spend a lot of time in the rest of the lecture talking about it。

 But it's not always going to fit with the semantics of computation。

 There's no real notion of like preempting a lock and taking away a lock from someone。

 So another approach is to roll back the actions of the deadlock threads。

 So it's like hitting the rewind button on Tivo， which by the way， was the original DVR copied。

 by all the cable companies and everybody else。 And then it's just like it never happened。

 And then we let things roll forward again。 Now one problem is if we roll everybody back to the original starting conditions and then。

 roll them forward， we might end up back in deadlock。 So maybe we pick one of the threads。

 So we back up one of the cars and roll back all the cars behind it。

 Now the car is going in that other direction can proceed。

 So you just have to figure out which makes the most sense。

 This is an approach that's commonly used in databases around transactions。

 If transactions cause the system to end up in a deadlock state， you simply abort a bunch。

 of the transactions and trial over again。 When we look at operating systems。

 there's lots of other options that they use for avoiding， or rather in this case。

 we're covering from deadlock。 In most cases， they just simply ignore that deadlock could occur and try to be designed。

 such that they won't cause deadlock themselves。 All right。

 so coming back to that comment about preempting resources， remember our example。

 that we had where thread A and B are trying to allocate two megabytes on our machine that。

 only has two megabytes of physical memory。 So if one gets one megabyte and the other gets one megabyte。

 then they can't get the， other megabyte that they need to proceed， neither of them can proceed。

 Now if we instead of operating on physical memory， say these threads are going to operate。

 on virtual memory， then we can provide the illusion that there's infinite memory。

 Now we don't really have to make it infinite。 We could just say， you know。

 make the illusion that there's two gigabytes of memory。

 That's more than enough for these two threads to be able to get their two megabytes each。

 And in fact， we could have dozens， hundreds of threads all doing the same thing。

 And to each one of those threads， it would look like there's an infinite amount of memory。

 Just have to have that illusion look large enough such that you don't run into problems。 Okay。

 Another way to think about this is instead， if we didn't have virtual memory， when we wanted。

 to grant one， we could preempt say， you know， a， by copying its contents of its one megabyte。

 region out to disk， clearing them， and then letting B use that region。 When B is done。

 we then wake A back up， copy its contents of memory back into physical memory。

 and allow it to proceed。 So from its point of view。

 it just has to wait a long time to get its second allocation， of one megabyte。

 but otherwise it sees， it doesn't see any other side effects。 That doesn't affect the semantics。

 just the timing of the computation。 Questions？ Okay。 All right。

 So let's look at a technique for trying to avoid deadlock。 So here's a， I'll， I'll。

 I'll propose this as an idea。 When a thread goes to request a resource。

 the operating system checks to see would it result， in deadlock if it granted that request？

 If the answer is no， then it goes ahead and grants the request for the resource right， away。

 If the answer is yes， then it makes that request wait for other threads to release resources。

 So this seems like it might be reasonable， but you know， actually it doesn't work。

 Let's look at why。 So let's look at our example， our running example thread A and thread B。

 So thread A runs， it does x dot acquire。 So we check。 All right。 If we grant x dot acquire。

 is that going to deadlock the system？ No。 All right。

 Because it could be the case that we run x dot acquire， then y dot acquire and， you know。

 A leaves and then sometime later B gets to run。 All right。 So now we come back to thread B。

 Is granting B， why dot acquire going to deadlock the system？ No。 So we grant that。

 Now we come back to A and A tries to do why dot acquire and it blocks。

 Now we come back to B and B tries， oh， it has to wait。 So we can't grant x dot acquire。

 It would actually put the system in deadlock。 Wait， the system is already in deadlock。

 So the issue here is that we're looking just at the request itself。

 We're not looking at what implications it might have on the future。

 And so anything we're going to have to do is going to have to look at what the future。

 state of the system might be。 So really what we have is three different states for our system。

 There's a safe state， which is the system can delay a resource request and keep us out， of deadlock。

 But we're not currently in deadlock。 We're not at risk of deadlock。 There's deadlock。

 It's too late now。 Nothing we can do at this point。 And then there's this weird state in the middle。

 which is we're not in deadlock yet， but， the threads could make requests that are going to lead to a deadlock situation with high certainty。

 So we want to keep the system in a safe state。 Because as soon as we get into that unsafe state。

 there's the risk that things just go， downhill and then it's game over。 Nothing we can do。

 All right。 Note that being in the deadlock state， that's also considered unsafe。

 You're going to deadlock。 You are deadlock rather already。 Okay。

 So deadlock avoidance is all about keeping us from entering an unsafe state and therefore。

 not being able to deadlock。 All right。 So now what we want to do instead of our idea is going to be the following。

 Request comes in。 The operating system is going to check that request to see if I grant this request。

 could， it leave the system in an unsafe state？ The answer is no。 We can grant it right away。

 If the answer is yes， we're going to make it wait。 All right。 So let's look at an example。

 So here we do X dot acquire。 Does that have any potential of putting the system into a deadlock？

 Is there a path forward？ Sure。 There's a path forward， right？

 If Y is available right now and so if Y was granted， A could exit the system。

 So now when we look at the right B and we do Y dot acquire， what's going to happen？ Well。

 if we grant that， is there a path forward？ No， right？ Because by granting that lock Y to be。

 now we've put it into a situation where X can't， finish。

 And if we look forward to what B is going to want to do， B is going to want to acquire。

 lock X and that's being held by A。 And so there's no way for A to proceed or for B to proceed if we grant Y。

 So we have to wait。 And then there is a path forward where now A can grab Y。

 do its work and exit the system。 And once it's exited the system and released X， then B can grab Y。

 grab X and exit the system。 Okay， so now， so that's kind of like a lot of hand waving to kind of get to what we want。

 to do。 So now let's turn this into a more formal algorithm。 All right。

 so this is getting us towards what we want to do。 We want to state the maximum resources that we're going to need in advance。

 And then we're going to allow a thread to proceed if we look at the available resources。

 minus what it's requesting。 And if that's greater than or equal to the maximum remaining resources that any thread。

 might need。 All right， because if that's the case， if there's still going to be enough resources。

 left after we grant this request for the maximum of some thread to proceed， we know that thread。

 can finish。 And if that thread finishes， it'll release its resources。

 And then we can check to see is that the case that for the other threads， this also holds， true。

 And we'll just keep going and keep going until we've checked all of our threads。 Okay。

 so this is a lot less conservative in the bankers algorithm。

 We're going to allow you to allocate the resources dynamically。

 So rather than saying you have to specify and request all of your resources upfront。

 we're just going to say you need to specify the resources upfront。

 Then we'll evaluate it dynamically so we can be less conservative。 So we'll evaluate each request。

 If it won't， if there's some ordering that is not deadlocked for the threads， we can grant。

 that request。 All right， so。 The technique we're going to use is we're going to pretend as if we granted the request and。

 then run our deadlocked detection algorithm。 But with a little bit of a tweak in it。

 So the tweak is that we're going to substitute， instead of having looking at the request from。

 a node to see if that's less than or equal to what's available， we're going to look at。

 the max request that could be requested by that node， minus what's already allocated to， that node。

 If that's less than or equal to what's available。 All right。

 so what's this going to actually look like？ Again， remember from last time we had bankers algorithm。

 we start by taking all of our resources， and putting that our free resources。

 putting that into our available vector。 All right。

 and then we add all of the nodes that are in the system unfinished。 And then we're going to iterate。

 What we're going to do is in each of these iterations， we're going to pull a node and。

 we're going to check to see if the max allocation， the maximum request for that node， minus what's。

 already allocated to that node is less than or equal to what's available。 Right。

 what's that it's going to mean is if the remaining what it could ask for is less。

 than what's available， then we know that that node can finish。 There's a path。

 And so we can let it finish， remove it from the set of unfinished nodes， put all of its。

 allocated resources into our pool of available resources， and we just iterate on this through。

 all of our nodes。 And if we still have nodes left and unfinished， we iterate again。

 And if we don't make any changes， then we know we're done。 All right， and so when we get to the end。

 we get to the end， if we have nothing left in， unfinished。

 that means that all of the nodes were able to exit the system successfully after。

 we virtually granted this request。 There was some path， some ordering that let them finish。

 If there's any nodes left in unfinished， it means that granting this request could potentially。

 put us into a deadlock situation。 So we can't grant it。 Yes。 So the question is。

 how would this connect back to the last example where we were acquiring， the locks？

 So in the case of a lock， that's a case where you just have one instance of a resource。

 So your vector resources here would be x， y， z， and so on。 So you're looking to see， so for example。

 each of those threads is going to want a maximum， of one instance of x and one instance of y。

 So if we get into a situation where one's got one instance of x and one's got one instance， of y。

 and we know that their max is that they're going to need the other， and each of those， is now zero。

 then we know that we'd be in a deadlock situation。 You're welcome。 Any other questions？ Yeah。

 So the question is， when I'm talking about available， am I talking about available in。

 terms of all of the resources in the system or just for that process？ So two things。

 One is when I say available， it's the resources that are unallocated。

 So like the locks that aren't acquired or the disk channels that aren't reserved and， so on。

 And then you can look at this at whatever scope you're trying to do deadlock detection on。

 So if you're doing it on a system-wide level， then it would be all of the system resources。

 If you're just doing it within your program， let's say you're implementing a network file， server。

 you want to make sure that its execution is deadlock free， then it would just be within， that。

 But since it's dependent on external resources， you'd have to make sure that all your uses。

 of those external resources wouldn't potentially lead you to a deadlock situation。 Yes？

 [ Inaudible ]， Yeah， so the question is， how does knowing the remaining resources help you because you。

 might have a lot of different kinds of resources and you might be requesting different resources。

 from the resources that are remaining。 So again， remember that these are vectors。

 So available free resources， those are all vectors where each element of the vector is。

 a different resource。 Similarly， when I look at the max for a node。

 that's the node specific vector of what resources， that node wants。 So I just， you know。

 there's an entry for each of the potential resources I might want。 Some of the resources。

 we may have multiple instances。 If you remember from the resource graph。

 we could have a box with say three instances。 So in that case。

 we'd start initial condition would be three。 Right？ Whereas for a lock。

 we'd start with just one instance of that lock。 Other questions？

 That's a really good question because this can be， Benker's algorithm can be really confusing。

 I recommend you try a couple of toy examples and play with it so you can understand it again。

 That's the kind of thing that sometimes shows up on the midterm。 Any other questions？ Okay。 So。

 again， if we're able to end up in a situation where there are no nodes left and unfinished。

 what it's telling us is that we've got the system in a safe state。

 If any nodes are left and unfinished， it means that there is not a clear path from granting。

 this request to all of the threads being able to exit the system。 That's an unsafe condition。

 It does not guarantee that we will deadlock， but it means that we potentially could deadlock。

 So it's conservative。 All right。 We don't know what the future is going to hold in terms of what the actual ordering of。

 requests might be。 And so we're going to be conservative in granting any requests to prevent us from entering into。

 an unsafe situation。 Okay。 So we could apply Benker's example and we'll do that with our dining lawyers。

 So， safe， I would not cause deadlock is if when you try to grab a chopstick， it's either。

 not the last chopstick。 There's at least one more chopstick left。 Or it is the last chopstick。

 but someone has two already。 Think about that for a moment。 If there's a chopstick left。

 it means somebody else who has one chopstick could take that， chopstick and finish。

 If there's no chopsticks left， but someone has two， they can eat， but their chopsticks。

 back into the pool。 And then other people will be able to finish。

 So we've guaranteed that there will be some path forward。

 Now the cool thing is we can extend this to multiple requirements in terms of how many。

 chopsticks it takes to eat。 So if we have a bunch of octopus armed lawyers。

 we can extend it to K arms。 So a K handed lawyer， our rule for granting is we don't allow that request if granting。

 that request would mean it's the last one and no one has K。

 Or it's the second to last one and no one has K minus one or the third to last one and。

 no one has K minus two and so on。 Right？ So this is really nice because we don't have to change the algorithm if we change number。

 of threads or the number of instances or the number of resources。 It's independent of all of those。

 Okay。 So summarizing deadlock。 Four conditions， again remember mutual exclusion， hold and wait。

 no preemption and circular waiting。 We looked at a couple of different techniques that we can use for trying to avoid。

 for addressing， deadlock。 We can prevent deadlock from happening by writing our code in such a way that deadlock won't。

 occur。 We can do lexical graphic ordering on resource requests。 We can do recovery。

 So deadlock happens。 We detect that the system is in deadlock and then we have some mechanism whether it's。

 preempting or it's terminating or it's rolling back that allows us to proceed。

 We can avoid deadlock in the first place， again doing things like Banger's algorithm。

 where we dynamically delay the servicing of requests in order to preserve a safe situation。

 or we could just simply say deadlock doesn't exist。 And so the system deadlocks， you know， oh well。

 Again， most operating systems tend to take the last approach especially when dealing with。

 applications。 They just assume deadlock never exists。 Those write perfect code and if you don't。

 well that's your fault。 Not the operating system developers。 So there was a question about。

 so this is kind of like priority except the highest priority。

 is who's closest to having the resources that they need。 It's not exactly like priority。

 It's more making sure that someone can get the resources that they need。

 It's not that one thread is more important than another。

 It's just figuring out whether there is some path from the current state where you grant。

 the request to an end state where all threads have completed and been able to get the resources。

 they need。 So you're simply just looking at that's why， you know， there's no ordering。

 Just the ordering that you're using for the nodes that you're looking at doesn't really， matter。

 You can use random ordering when you're going through the nodes that are in unfreeing。

 It doesn't matter what order you're going through。

 You're just looking for is there an ordering that lets all of those nodes finish。 Yes。

 [ Inaudible ]， Yeah， so in the case of locks， you know， there isn't a semantic notion of being able。

 to preempt a lock。 If I've granted you the lock， I can't take it away because you might have left the world。

 in an inconsistent state while you're doing something in a critical region。 So in the case of locks。

 you can't have preemption。 But as we're about to see with memory， you can。

 And we just saw in a bunch of lectures， you can do the same thing with the processor。

 I can take the processor away from one thread and give it to another thread。 Okay。

 so now we're going to switch gears and talk about some more virtualization。

 So we looked at virtualizing the CPU and scheduling。

 Now we're going to look at how we might virtualize memory。 And in future lectures。

 we're going to look at how we might virtualize IO devices like， disks and network and so on。

 So it's all about the fact that we've got this notion that we want to provide the illusion。

 of exclusive access。 I have my own dedicated machine。

 When the physical reality is that we've got hundreds of threads that we're trying to schedule。

 onto a single set of physical resources。 So the question is。

 why is the max allocation bank or algorithm less conservative than the， request one？

 So it's actually the other way around。 The max allocation， oh， it's max minus the allocated。

 That's less conservative because we're not looking at everything that the user wants upfront。

 Rather， we're looking at just what is the current situation if we grant this request。

 That's a little different。 Okay， so why do we want to do memory sharing？ Very simple。

 If we look at the state of a program， it's fully defined by the contents of the CPU， working。

 state that's in the CPU， and memory。 So if we can share memory。

 then we can have lots of programs running at the same time。 Problem is we can't share memory， right？

 We can't have two programs occupying the same physical memory at the same time。

 So we're going to need some way of multiplexing their use of that memory。

 The second reason is one of protection。 I don't want some other program having access to my program's data。

 So we both want to be able to do controlled sharing or no sharing， so protection， and we。

 want to be able to multiplex those programs onto the limited physical RAM that we have。 All right。

 so remember some fundamental concepts。 We have a thread。 That's our execution context。

 It's the active part of our program， fully describes the program's state。 We have our address space。

 That's the passive part of a program， which might or might not have translation。

 So we might be dealing with physical addresses or we might be dealing with virtual addresses。

 and it's the set of memory addresses that a program can read and write and execute off， of。

 When we think about an address space， it might actually be separate in terms of the program's。

 view of memory from the physical instantiation in memory。

 So the program might be looking at a virtualized view of the world， then we have to translate。

 that into a physical view of the world。 In a process， again。

 it's just an instance of a running program that consists of a protected。

 address space along with one or more threads of execution。

 The last component we need is dual mode operation or protection。

 Only the system has the ability to access and manipulate certain resources。

 We combine this with translation to isolate one program from one process from another。

 and from the operating system。 We also， it's the way that we control， right？

 If we let the process control the translation， then it could simply set the translation to。

 let it see anything it wanted to see， including the operating system。

 So this is where dual mode operation comes in， where you can only manipulate translation。

 stuff while you're in the operating system。 Okay。 So basics of an address and address space。

 So an address is k bits in length。 And if it's k bits in length。

 we can reference an address space that has two to the k elements。

 Now in almost all the machines you're going to encounter， those machines are byte addressable。

 And so those two to the k things are two to the k bytes。 So an address space。

 when someone says there are k bits， it means you can reference an。

 address space that contains two to the k bytes。 Now， what's two to the 10 bytes？

 You have to memorize all this stuff。 You'll be using it so much you're going to remember it by the end of the semester。

 Exactly。 It's one kilobyte or 1，024 bytes。 All right。 Note that it is not 1，000。 Right。

 Little of a side， if you buy a hard drive and it says it's five terabytes， if you read。

 in the fine print， it'll say that it is 1，000 times 1，000 times 1，000 bytes。

 That's not five terabytes。 That's marketing speak， but it has nothing to do with terabytes。

 Terabytes would be 1024 times 1024 times 1024。 Why would they do that？

 Because they can sell you a smaller disk and say that it's a larger disk。 It's kind of annoying。

 but we used to run into the same problem with displays。

 There's actually a law which specifies how you measure the display because manufacturers。

 were including the parts of the panel that you couldn't see as the size of the display。

 Because then they can tell you it's a larger display than they're actually selling you。 Okay。

 So let's say we have a page that has four kilobytes in it。

 How many bits do we need to address each byte on that page？

 Doesn't everybody think in like powers of two？ Yes。 Yes， it is 12。 So two to the 12 is 4，096。 Okay。

 So how much memory if we have a 20-bit address space or 32-bit address space or 64-bit address。

 space， can we reference how many individual distinct bytes？

 The answer is just going to be 2 to the K。 Here's a little hint for exams。

 We ask you something and you can't remember what the translation， what the calculation。

 is going to be， leave it in symbolic form。 You should be amazed at the number of students who think。

 you know， I don't know， 2 to the， 2 is 8 or other things because under the pressure of an exam it's very easy to make。

 mistakes like that。 So worst case， always leave in symbolic form。 Okay。

 So now when we think about an address space， right， it's the set of accessible addresses。

 and the data associated with those addresses。 So if we have a 32-bit machine。

 that means our addresses are 32 bits in size and we can。

 reference approximately 4 billion bytes on that machine。

 So how many 32-bit numbers will fit into this address space？ Well， that's just simply going to be。

 each word is 4 bytes in size。 It's just going to be that 2 to the 32nd divided by 2 to the 2。

 So it'll be roughly a billion。 Now when we try to access。

 when the processor tries to read and write one of these addresses， in our address space。

 what happens？ Well it depends is the answer。 Maybe you can just read and write it like normal memory。

 Maybe writing to that address causes some IO operation to happen on the disk or the network。

 or something else。 Or maybe if you like for example try to write in this region right here。

 it causes a segmentation， fault。 Your program crashes。 The operating system terminates it。

 Or maybe it's how we communicate with another program。

 So maybe two programs actually can look at the same physical memory locations。

 You can use it to signal one another or to use shared data structures。

 The key thing is with translation we can do anything we want。

 Within the bounds of the hardware implementation of translation， we'll see that we can do some。

 very powerful things with translation。 You don't have to just think of memory as a blob that all you do is read。

 write， and run， instructions out of。 Okay。 So remember the typical structure for a program is typically we have a code segment。

 So that's where all our instructions live。 We might have some static data。

 We might have some uninitialized data。 There's all sorts of like data segments that we might have data portions that we might。

 have。 Then there's a heap。 This is where we're dynamically allocating things when we do things like malloc。

 That might in this case be growing， this is kind of flipped upside down。

 So that's kind of growing up towards the top of memory。

 And then a stack segment which we put all the way up at the top of memory and is growing。

 down as we do recursion。 All right。 And then we have processor registers that point into various parts of this like a program。

 counterpoints into something in the code segment and the stock pointer points to something in。

 the stack segment。 Now what happens if， you know， say we try to reference a memory location that's outside。

 of our heap because we want to malloc something really large。

 But we're going to reference a region that's not translated， not mapped。

 And so that's going to generate a system call， you know， trap into the kernel and the kernel。

 will actually realize， oh， you want more memory and it'll give us more memory。

 Ubring system dependent， some operating systems will just simply terminate you that some require。

 you to be explicit about how much heap you want and so on。 But in many cases。

 just going off the end of the stack or the heap causes the operating。

 system to allocate more space for you。 Okay。 So remember we have single and multi threaded processes threads again are the active component。

 of an address of a process。 And the address space is the passive component that gives us protection。

 Which what keeps other programs from being able to affect us。

 And it's what it keeps our process from being able to affect other processes or even affect。

 the operating system itself。 That's our protection。

 Now why do we have multiple threads per address space？ Efficiency， communication， you know。

 context switching is very low cost。 Okay。 So let's look at some of the aspects of memory multiplexing。

 So the first and the most important one is protection。

 We want to protect our process from other processes and protect other processes from， us。 Right。

 And so we might also within the process have different protection levels。 So for example。

 we might mark some pages as we don't want。 We try to write to them。

 it'll generate a fault to the operating system。 We might have regions that are instruction only。

 execute only。 Right。 This is a modern security technique that we do to guarantee that you can't inject code。

 into a process。 Because it's execute only and read only。

 And you can only execute out of regions that are marked execute only。

 And you can't modify them since they're read only。

 You can also have regions as we'll see in a moment that we mark as invisible to the user， program。

 It sounds a little weird。 Why would I have a region in the address space of a program that the program actually。

 can't look at？ Trust me， I'll make it clear in just a slide or two。 So kernel data。

 we want to protect from user programs。 And other programs data。

 we want to protect from those programs。 And in some cases。

 we want to protect programs from themselves by doing things like marking， regions read only。

 The second important aspect is translation。 We want to be able to translate from the virtual address space that a program thinks。

 about to how we physically put it into the memory。 And by controlling translation。

 it gives us a lot of flexibility on where that program， actually lives in physical memory。 In fact。

 it gives us the ability to even take it out of physical memory， preempt it out of， physical memory。

 and put it out on the disk。 Not the program， semantically having any idea that that's been done。

 And we'll see that there are a lot of benefits to be able to do that in future lectures。 Okay。

 another benefit is we can use it to avoid physical overlap between two processes。

 in physical memory， even if they have the same virtual addresses。

 We just simply map them to different physical addresses。

 The flip side of it is we can do controlled overlap and let them actually see each other。

 if we want。 So we can have windows between two programs that allow them to share data between two。

 programs。 Okay， so if you think about it， when you do IO， the operating system interposes itself。

 on every IO operation。 It does this so it can do access control。

 It does this so it can translate between you thinking about bytes in a file and the actual。

 physical blocks of a file on disk。 There's lots of reasons why we want to interpose。

 We do buffering and other sorts of things。 The operating system also interposes on processes use of the CPU。

 You impose priority and other sorts of things and we share that CPU across multiple processes。

 So here we want to do the same thing。 We want the operating system to interpose on memory access。

 So we can control that mapping between what the program sees and what is the physical。

 reality on the physical memory。 Now of course we don't want the operating system to actually get you don't want like。

 every instruction fetch every memory read write that cause you to trap into the operating。

 system the operating system does a bunch of work in order to service that。 That would be very slow。

 So we typically do this with hardware and we use that hardware to accelerate that translation。

 process。 And then in the really uncommon case where something weird is happening， that's when。

 we page fault or trap into the operating system and then the operating system decides how。

 am I going to handle this situation。 But the common case has to be used to hardware because the hardware is going to be really。

 fast。 Really， really uncommon case can be the slow case where I have to go through the operating。

 system。 Alright， so remember how loading works， right？



![](img/4debe4e4bf5fd22a7051820601bb8ab1_3.png)

 We start with our program。 Programs out on storage。

 Operating system uses the IO controller and other things to load that program into memory。

 That's the loading process。 Now when we take that program from disk and put it into memory。

 there's a binding of those。

![](img/4debe4e4bf5fd22a7051820601bb8ab1_5.png)

 instructions and the data of that program to physical memory。 Alright。

 so we go from this code here on the left， the processes view of memory， which。

 is it's got some data， it's got some code， it's got some subroutines and loops and things。

 like that。 And we have the physical addresses that are associated with that process。

 Now you might wonder why is this， you know， data one here， the physical address for it is。

 a hex 300 and yet this load here is load word is loading C zero hex。

 What's because it's word addressed and we're loading a word and so the assumption is words。

 are four bytes and so C zero times four is 300 hex。 Okay。

 so now these physical addresses live in our physical memory。 So on the left again。

 over here we have the processes view of memory and then on the right。

 here we have what it actually looks like if we look at the bytes。 Okay， so we loaded our program in。

 Let's say， I don't know， it's your favorite ID or EMAC or whatever。

 Now somebody else on the system also wants to run that same ID or EMACs。

 So we're going to load a second copy。 Now if we had the same exact physical addresses。

 their copy would land right on top of ours， in physical memory。

 So when we're doing that loading process， we need to put it somewhere else in memory。

 So that was our first application instance， our second application instance has to go somewhere。

 else。 So we need address translation。 Whether we're going to do it when we load or when we're going to do it dynamically。

 we， need some way to be able to have two copies of the same program or even end copies of。

 the same program resident and running at the same time。

 The translation would let us have a different set of physical addresses associated with the。

 same program。 So I'm running EMACs。 You're running EMACs。

 They're living in two different locations in memory。 This is just one of many possible translation。

 We're going to look at a bunch as we continue on in the next set of lecturers and where translation。

 takes place， it could be when we compile it， we compile it and give it physical addresses。

 It could be when we load it， it just addresses to be where we want it to be or it could be。

 on every single memory reference。 Do it dynamically at one time。 So let's think about that。

 When we create a process， ultimately end up with a process， we start with a program。

 So you write your code。 First thing you do is then compile it and you're going to link it to link in static libraries。

 and then at execution time we're going to link it， load it and then link in any dynamic libraries。

 that you're using。 So addresses could be bound to final values。

 to the physical values anywhere on this path。 And if we look at the history of computers。

 the earlier you go in history， the earlier， you did this binding。 So early first computers。

 when you compiled it， that's when you generated the physical， addresses。

 Because you're only running one program at a time， so you wouldn't have multiple copies。

 And now when we look at modern computers， the binding is occurring when you're actually。

 referencing the addresses at execution time。 Little aside about dynamic libraries。

 so when you write your programs and you're using， things like libc functions and other things。

 libc doesn't get linked into your program。 Rather。

 stubs get linked in and then we actually go to execute it and load it into memory。

 There's a loader linker that links it with the actual dynamic library。

 That's why it's called dynamic libraries。 And those dynamic libraries will see you could be shared across everybody who's running and。

 using libc。 I don't need to have 100 copies of libc in memory。

 It also is handy because if you have a new operating system version that updates some。

 of the libc functions， you don't have to go back and relink your program。

 Because your program is just linked with a stub， when you actually run， you're going。

 to run with the latest version of libc。 I mentioned this already。

 but in the uni programming environment， you don't need protection。 This is only one thing running。

 That application can always be in the same physical location in memory and it can access。

 any physical address。 That's simple。 But it has the advantage that we're giving the illusion of a dedicated machine by giving。

 you a dedicated machine。 Disadvantage being this application can scribble all over the operating system。

 But it's shared fate。 It's the only thing running if it breaks the operating system。

 application isn't going， to be running anymore。 It's power cycle machine。

 So we don't need translation。 We don't need protection because we're not trying to do anything except run that one。

 application。 And you still see， in， for example， IoT devices， you'll see this as the default model。

 Right？ You don't need translation because there's only one program that's running。 So， you know。

 for example， there's a little thermostat on the wall there that's a digital。

 thermostat with a microcontroller in it or microprocessor。

 It's only running one program and so there's no need to do any translation。 If the thing crashes。

 well， then it， I don't know， it gets really hot in here or something。 Okay。

 Fast forward to the early PC era and we had really primitive multi-programming because。

 we had multi-programming without translation， without protection。 So somehow or other。

 you're going to need some way to be able to load your word and then。

 load your PowerPoint without the two colliding。 And so their solution was to have the loader linker adjust addresses when we load programs。

 into memory。 So every program when it's compiled would have a relocation table。

 That would tell the loader linker what is the address of every location in the program that。

 has like a jump， has a load of data or store of data。 And then when you loaded。

 you'd use that relocation table to go and patch all of those locations。

 to set them to what the actual physical addresses were。 All right。

 And so whatever I said is my target here， I said it is zero。

 I just adjust everything in the relocation table based on that offset of zero。 And here it's 20。

000 hex。 I just set everything to be off that offset of 20，000 hex。 All right。

 And so this was very common use for Windows 3。1， Windows 95， Windows 98 and so on。 However。

 there's an issue here。 There's no protection。 There's nothing that keeps a program from taking an address and adding a million to it。

 and then just scribbling all over memory or just reading what's there。

 And so there's no protection for between programs。 So if word crashes。

 it could take out PowerPoint crashes。 It could take out the operating system。

 That's why I say this was really primitive because any crashes were problematic。

 And anything malicious was also problematic because there's nothing to keep a malicious。

 version of word from accessing your browser and seeing contents of passwords and things。

 like that or any other secrets。 But it let you run more than one thing。

 So how could we do protection without having translation？



![](img/4debe4e4bf5fd22a7051820601bb8ab1_7.png)

 Well， one approach is an approach called base and bound。

 And so this is the approach that was used by the Cray1 supercomputer。

 So this was the first supercomputer that was built。 And it worked like this。

 We're going to have two registers， a bound register and a base register。 All right。

 And so we're going to use the base register to specify where a program starts。

 We're going to use the bound register to specify where the program ends。 Now little aside。

 this is a picture of a Cray1 computer。 A couple of things to notice about it。

 One is it's kind of shaped like a C。 That was done on purpose because then it makes the。

 distance between all of the components uniform。 Instead of having a linear back plane。

 they basically folded the back plane。 It also is kind of cool because it was created。

 The company founder is Seymour Cray and so you had a computer that also looked like from。

 above like his initial。 But does anybody know what this black thing is around it？

 That's where all the cooling stuff was。 But it doesn't look like it's metal actually。 And it's not。

 It was actually covered in like leather。 You can see more Cray had this vision that supercomputers were not these things that you。

 would lock away in data centers。 But there were things that you could like you could imagine it being in your living room。

 And so wouldn't you want to sit next to the supercomputer？ Needless to say。

 if you were to go visit a data center and see this thing with a nice， leather at， you know。

 I don't know， seats around it and you sat on it， you'd probably。

 be escorted out of the data center and not invited back。 Another little fun aside。 So you know。

 working on the first supercomputer was like an amazing thing。

 It's like going to Google X and getting to work on some crazy， you know， flying contraption。

 So one of my fraternity brothers， he got to spend a summer as an intern at Cray。

 And he was so excited。 He's like， oh， I can't believe this。 You know， I'm going to work on。

 you know， the next generation of computers and all。

 So remember how I said that they had this back plane that was folding？

 One of the things that they did as an innovation to make designing and building machines a lot。

 easier is they thought of everything in units of speed of light。

 So it takes the speed of like roughly one nanosecond to travel 12 inches in copper。

 It's a little bit， it's a little bit different from that， but roughly。

 And so everything in the machine was done in all the copper was done in lengths that were。

 multiples of roughly 12 inches。 His job as an intern was to spend the summer cutting wires to multiples of lengths of 12。

 inches。 It was a really exciting internship。 Needless to say。

 the following summer he did not go back to Cray。 Okay。

 pick internships that are going to be way more fun than sitting there cutting wires。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_9.png)

 all summer。 All right， so how does basin bound work？ We take address generated by the program。

 All right， so that's this address here on the left。 And we use it to reference memory。 All right。

 and what we're going to do is we're going to do two checks。

 One is to make sure that that address is greater than or equal to the base。

 The second check we're going to do is to make sure that it's less than the bound。

 So we take our original program and when we load it into memory， in this case， it's original。

 addresses were zero based。 We're going to adjust them all to be whatever 1000 something based。

 All right， so we're going to translate all of those using our relocation table all of。

 those references。 But by having this dynamic check on the bound and on the base。

 it means that if I have a， program that takes a pointer and just randomly adds a billion to it and then tries to reference。

 memory， it's going to fail because it's going to be greater than our bound。 All right。

 and notice that we're not doing any manipulation of the address。 So this is very fast。

 We can do the checks in parallel with the memory references。

 So that's going to make it extremely efficient。 So this protects the operating system and it isolates programs from each other。

 One program can't go and reference another program's memory and vice versa。

 And they can't reference the operating system。 But it still requires us to do that relocation step when we load the program。

 So it also requires the compiler and the linker to generate that relocation table for when。

 we load it in。 But no addition on the address path。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_11.png)

 All right， so again， remember， we have these two views of memory。 Right here on the left。

 we have virtual addresses that are being generated by the CPU。 And on the right。

 we have our actual sticks of DRAM that are physically addressed。

 And it's the job of this thing in the middle， the memory management unit， to translate from。

 those virtual view of memory to the physical view of memory。

 We can implement anything we want in that black box that is the MMU。 All right。

 so base and bound is just one example of what we could implement in the MMU。

 We're going to see a lot more complicated approaches。 With translation。

 it makes it much easier to implement protection。 Right。

 because we can use the MMU to make sure that we can't generate addresses that would。

 reference someone else。 And I see there's a question in chat。

 where are the base and bound numbers stored？ And the answer is they're stored in processor registers。

 Can they be changed by the user？ Is the second part of that question？ The answer is no。

 They can only be changed by the operating system。 Right， if we were to go back here。

 and we allowed the user program to change base or。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_13.png)

 change bound， then it could set it to be all of memory and access anything in memory。

 And for efficiency and speed， we keep them in the processor because they're small。 Right。

 they're each just two words that we need to keep in memory。

 So when we context switch from one process to another， we will have to save out the base。

 and bound for one process， load in the base and bound for the next process。

 One of the things you're going to see is， depending on the different approaches we use。

 we already had to save and load a lot of stuff， the context switch， all the processor registers。

 maybe the floating point registers。 Now we're adding additional state that we're going to have to save and load on a context。

 switch。 Some of it we don't have to。 If we're context switching between threads in the same address space and we don't have。

 to， but if we're context switching between threads in two different address spaces， then。

 all of the translation stuff that's in the processor has to get context switched out。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_15.png)

 And we have to load that for the new one。 Okay。 Now。

 the cool thing with translation is with translation， we can allow everybody to just。

 have zero based programs and we just dynamically translate those addresses into actual physical。

 addresses。

![](img/4debe4e4bf5fd22a7051820601bb8ab1_17.png)

 So let's look at how we could do that。 So a little modification that we're going to make to base and bound。

 The modification we're going to make is instead of making base be a check， we're going to。

 make it be something we add to the address。 And now we can take our original program that's zero based。

 load it wherever we want 1000， whatever set base to be 1000。 And every address that's generated。

 we're just simply going to add base。 And then we're going to check also make sure that that address is within the bound。

 So this gives us hardware relocation。 Right。 Now， can the program touch the operating system with this？

 No， the program touch other programs with this。 No， we've isolated them。

 But the disadvantage here is we've now added an addition， right。

 So before we were able to just take that address， start referencing memory and then in parallel。

 we check to see is it within base and bound。 Now before we can reference memory。

 we have to do an addition。 These are pretty fast， but it does take time。

 Now added some number of nanoseconds to the path。 And what we'll see is with some of the more complicated approaches。

 we'll be adding a， lot of nanoseconds to the time it takes to actually read and write memory。

 All right。 So some issues that we might have with this approach。 All right。

 So let's say we've got a bunch of processes running。 We've got process two， process five。

 process six and our operating system。 Well now process two finishes。 All right。

 So now we have a gap， some unallocated memory and a long comes process nine。

 We just put it in that region。 Now process nine is running。 Now at some point， you know。

 later process 10 comes along。 We start running it and process five ends。

 It's now a memory looks like this。 And now a long comes process 11。 And we have a problem。

 We're not out of physical memory。 If we look at the size of the region between nine and six plus the region between 10 and。

 the operating system， it's smaller than process 11。 But we don't have a contiguous region。

 That's the size of process 11。 And this is the problem we're going to have。

 We're fragmenting over time because not every process is the same size。 So what do we do？

 Well one thing would be to say， sorry process 11， you can't run。 Try running later。

 That would be really unpleasant and really painful。 Like imagine， you know。

 it's 1150 and you're trying to submit to the autograder and we say， oh sorry。

 fragmentation come back tomorrow。 All right。 I don't think you'd be too happy。 So what do we do？

 Well， we could move process nine and process 10 down and give ourselves enough room。

 That's really expensive copying memory。 But you know， it would be what we would have to do。

 And it's what systems that use this kind of approach would do。

 They'd end up over time doing a lot of copying to deal with that fragmentation。

 Another problem is that address spaces are not big， continuous blocks。

 Remember when I showed you earlier， right， our code segment， our data segment， our stack， segment。

 our heap segment， it's not one compact block。 They're all over memory。

 all over our virtual address space。 Yet we're treating them as if they were one monolithic block。

 And so that can't be efficient because our address spaces are really sparse in practice。

 And so those blocks are going to be much， much larger than they need to be。

 It's also not easy or possible to do inter-process sharing。

 You have to do some kind of weird overlapping and， you know， that just， it would not work， well。

 Right？ We really want to share like a specific region in our virtual address space with another。

 specific region in a virtual address space， not like the top and bottoms of our address， spaces。

 So that really wouldn't work。 Another thing is， remember I said， you know。

 we've got 10 people running EMACs。 We don't want to have 10 copies of EMACs running。

 With this approach， that's exactly what we'd have to do。

 We're taking our precious memory and we're wasting it on the same code 10 times。

 So that can't be efficient。 So really what we want is more flexible segmentation。 Right？

 If we look at what's in our address space， there's lots of different segments。 There's the stack。

 there's code， there's uninitialized data， initialized data， and so on。

 There's segments that we want to share。 So really what we want is an approach that lets us have a user of space。

 which is， you， know， I've got segment one， two， three， four。

 somewhere scattered in my virtual address space， and I map that into separate regions of my physical memory space。

 That's not all in one。 So each segment will think of as a base and bell。

 Each segment will be contiguous， but the segments as a set can be very discontinuous。

 So how do we do this？ So here's an example of an implementation of a multi-segment model。

 The segment map lives in the processor。 It's not very large。 So in this case。

 we have eight segments。 So it's relatively small。 It's going to be， you know。

 a little over probably like eight words in size。 And we're going to take our virtual address and we're going to divide it up into fields。

 So our upper bits are going to be our segment number， and we're going to use those as an。

 index into our segment map。 And then we're going to take the offset and we're going to add it to the base and use。

 that to generate the physical address。 So all we've got now is just a set of base and bounds。

 That's it。 So instead of having just one base and bound per process， now we have eight。

 So we're going to have eight different segments。 All right。

 we need some error checking because we've got to make sure we're not going outside， of the bound。

 the limit for our segment。 And we can have as many chunks of physical memory in use as we have entries。

 So in this case， we have eight。 So we're going to have up to eight physical chunks of memory that we use。

 Now in this case， I'm giving you an example where we're referencing the segment by using。

 bits from the address。 On x86 architecture， there's actually bits from the instruction。

 which allow you to say， this is from the ES segment or the CS segment or the SS and so on。

 But it's all the same。 Ultimately， you're just interacting into a table of these base and bound pointers。

 Now we also need some additional bits。 In this case。

 I just have a V and an end bit valid and not valid。 But you also might have that it's read only。

 it's an execute only， and so on。 So you could have a lot of different bits。

 And you'll see later when we get into more complex paging and things like that， we need。

 a bunch of metadata bookkeeping bits that we'll use。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_19.png)

 So just really quickly， if we look at the x86 architecture， it has a segment register。

 And then we divide up the segment， the fields of the segment register。 So the， the， uh。

 request or privilege level is the low order bit。 And then the index is actually the upper bits。

 There are multiple different segment registers。 So we have ES segment， SS segment， code segment。

 data segment and so on。 And you actually can't turn off segmentation。 So in the next lecture。

 we're going to look at paging and we're going to look at combining。

 paging and segments and when you get into a situation like that where maybe you just。

 don't want to use segments， you want to use paging because it might be more appropriate。

 an x86 you actually can't turn it off。 So the hack that people do is they just simply set the base and bound to be all of memory。

 And then it effectively turns it off because it's not used。 So a little too much detail。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_21.png)

 We'll， we'll come back to that in future lecture。 All right。

 so here is an example with four segments， 16 bit addresses。 We're going to use the upper two bits。

 because we have four segments， two to two is four， as our index into our segment map。

 And we're going to use the rest of our bits， our 14 bits as our offset。 All right。

 so here we have code is segment zero， data is segment one， share to segment。

 two and stack is segment three。 So where do these live in memory？ Well。

 if we look at segment equal to zero， that's going to live at four thousand， four thousand hacks。

 the forty eight hundred hacks。 If we look at segment one。

 it's going to live at forty eight hundred and go up to five， five C hundred x。

 If we look at segment two， it's going to start at f zero， zero， zero。

 And that is a segment which is shared， so that might be shared with other applications。 And so on。

 right？ So everything else here that's， uh， unallocated， that's space for other applications。

 All right， and so we're going to take these segments and it's like a little game of Tetris。

 we're just going to pack them into memory。 Again， the problem we may run into is with fragmentation and needing to move segments around。

 so that we can satisfy a contiguous request。 But one thing that's going to help us a little bit is the fact that these segments are going。

 to be smaller than those big monolithic process sized segments。 They're still going to be large。

 they're still different sized， so we still can run into the。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_23.png)

 fragmentation problem。 Okay， so let's look at an example of how we do translation。

 So we're going to use our same segment map and now let's simulate what happens with this， code。

 So we've got some code here， it's got a main that starts at 240 hex， it's got a variable。

 here at 4050 hex that has some data in it and then it's got a little subroutine right。

 here for string length and so on。 These addresses here in blue are those virtual addresses or those physical addresses。

 Virtual addresses， right？ So we're going to need to translate them to where they live in physical memory。

 So we start out with our program counter at 240 hex。 So we're going to fetch。

 do an instruction fetch for the data stored at 240 hex in physical， memory。

 So I've color coded here in green， our segment， zero and that's 4000。

 So we're going to take 4000 and add to it our offset 240。

 So that's going to generate the physical address 4240。

 So we fetch the instruction which is a load absolute of the pointer var x into a zero。

 So we're going to take this location and load it into register a zero。 So I have to do translation。

 right？ Yes？ No？ Maybe？ What is the program thinking？ Virtual addresses。 So the answer is no。

 When I'm loading a pointer， I'm loading the pointer in virtual address。

 When I actually reference it， that's when I'll turn it into a physical address。

 But from the point of view of the program， everything it sees is virtual addresses。

 This is really important concept because this is one of the things that really confuses。

 students is the difference between when I'm dealing with a virtual address and when I'm。

 dealing with a physical address。 The programs they always deal with virtual addresses and then translation gives us the。

 physical addresses。 Okay， so we're going to store 4050 into a zero。

 Increment our program counter by four and fetch from 244， translates to 4244。

 We'll fetch the jump to the string length， recursion to string length。

 So that's going to cause us to move 2048 into our return address register， RA。

 And we're going to set our program counter to be string length。 That procedure， which is at 360。

 Again， we're setting the program counter to be the virtual address。

 We'll worry about what it is really when we do the actual execution。

 So now we're going to fetch that instruction at hex 360。 And again， we'll do a translation。

 It'll be 4360 and we'll get the load immediate of zero into V0。 We'll move zero into V0。

 update our program counter。 And now we want to fetch 364。 Again。

 that's fetching 4364 and that's load the byte pointed to the by the region at a， zero。

 And since a zero is 4050， we have to translate now we do the translation， our hex 450 into。

 a physical address。 And so that's going to be segment one。 And so that'll be 4800。

 So it'll be 4800 plus the offset of 50。 So it'll be 4850。

 So we'll load the byte from 4850 into our register。 All right， increment our program。

 Everybody follow that？ Okay， so we'll finish up on this slide。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_25.png)

 So some observations about segmentation。 We're doing our translation on every memory reference。

 So when we do an instruction fetch， when we do a load， when we do a store， that's when。

 we actually do translation。 That's a big difference from where we relocated everything when we loaded it and we only did。

 that translation step once。 But we get protection by doing translation because we can enforce the addresses that can。

 be generated to make sure that invalid addresses cannot be generated。

 Our virtual address space has holes。 Right between the segments are regions of memory that if you try to access them。

 something， happens。 Right？ Sometimes it's okay。 Like if you go off the end of the stack。

 operating system will allocate more memory。 If you go off the end of an initialized data region。

 you'll get a seg fault。 If you go off the end of a code segment。

 you'll get a seg fault and your program will be terminated。

 Now we need a protection mode bit in the segment table。 I didn't go over that， but you know。

 we might mark our code segment as read only and execute， only。

 We might mark as read/write because we want to allow stores。

 Last thing is what do we need to save and restore on a context switch？ Everything in the CPU。

 So that segment map， we have to save it out and we have to load the segment map for the。

 new process that we're going to run。 We could also store some of the segments that are in physical memory out to disk。

 We used to do that when we had programs that were too big to fit in physical memory。

 We might swap portions of the program or we might swap entire programs when we went from。

 running one process to running another process。 All right。 Any questions？ Okay。

 I'll see you next week。 Okay。 I'll see you next week。 Bye。 (crowd chattering)。



![](img/4debe4e4bf5fd22a7051820601bb8ab1_27.png)

 (buzzing)， [BLANK_AUDIO]。