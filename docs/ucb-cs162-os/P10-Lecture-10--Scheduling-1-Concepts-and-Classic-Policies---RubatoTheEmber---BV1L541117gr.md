# P10：Lecture 10： Scheduling 1 Concepts and Classic Policies - RubatoTheEmber - BV1L541117gr

 Okay， welcome everybody to the first post midterm one lecture。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_1.png)

 Yeah， you survived。 So we're actually going to do a little bit of a change in topic。

 Let me make sure。 Let's see。 Can everybody see my slides？ Also in cyber space。 Okay。

 so if you remember。 I wanted to review a couple of things that we were doing just at the very end。

 And so we can close out kind of a bit on synchronization here。 So， first of all， if you remember。

 we talked about semaphores last time in more detail。 And there's two uses of semaphores。

 So semaphores have an initial number。 Value that you set when you allocate them。

 And if you set that value to one， you basically just get a mutex or what's called a binary semaphore and you can use it for locking。

 And so you'd use it like this， where you do the P operation down and the V operation up when you're done。

 And if two folks try to do that semaphore P at the same time， one of them gets put to sleep。

 And this is a purely atomic operation。 So it's not possible for two threads to get through there by accident。

 Okay， so it will atomically decrement the value。 And if you're would go before zero。

 put you to sleep。 We also looked at the fact that we could do scheduling constraints by setting the initial value to zero。

 And that might allow you to do a joint operation。 So you set it to zero。

 you go to sleep by trying to do a P operation。 Anybody else could wake you up with a V。 Okay。

 and then finally， and so this is the example of thread join where the original parrot thread。

 let's say， goes to sleep and then the finishing child thread executes a V and wakes them up。 Okay。

 and then finally we had the bounded buffer solution for the coke machine。

 And this was a good example for three semaphores。 And if you remember the reason we had three semaphores was we have two conditions and a lock。

 The two conditions have to do with bounding the maximum number of coke cans in the machine and saying that it doesn't make sense to have a negative number of coke cans in the machine so we're bounding the two sides。

 Okay， and if you remember the code kind of look like this for the producer in the consumer。

 This key pattern here is that we always protect things like in queue and because those are those are operations that could get screwed up if multiple threads go in them and so that's why we have new Texas around them。

 And then we execute a semaphore P on the empty slots to make sure there is something before the producer goes in and the flip side for the consumer。

 And so， you know， if you look， what's in red here are critical sections in the locking sense just to protect the cues。

 And then we have this signaling that when the producer finally produces something they'll wake up somebody who might be sleeping。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_3.png)

 And when the consumer kind of finally empties a can out they might wake up a producer。 Okay。

 so before we leave this I just wanted to see if there were any last minute questions on this。

 Semaphores are very common in operating system so。 All right， good。 So， however。

 we said there's something even better。 Okay， a monitor which is a lock and zero or more condition variables。

 And actually if you only have zero condition variables it's not that interesting。

 And the condition variable was specifically a weight queue that you can go to sleep on with the lock being held that's the key idea here。

 Okay， so unlike any other weight queue。 And the condition variable weight queue you grab the lock you check your conditions then you go to sleep if they're not satisfied。

 And it's that weirdness， or difference in API that really makes them so powerful and easy to use。

 There are three operations typically they got different names depending on what the packages are。

 but roughly a weight， a signal and a broadcast。 And the rule is always hold the lock when doing any of these three operations。

 Now， I know there are many of you who would say well why do I have to hold the lock to do a signal or a broadcast。

 There are various reasons for that and depends a lot on the scheduling package as to whether that's legal but for now we'll just say。

 always hold the lock around everything。 Okay， especially in this class。

 Are there any questions on the interface。 So we gave you this typical structure so if you're thinking about a monitor program this is one way to think about it。

 You grab the lock。 You check and see whether conditions are met or not。 And if they aren't met。

 then you go to sleep。 And notice that that weight operation always happens。

 Like a semaphore P which might not put you to sleep a weight always puts you to sleep。

 This is the key interface aspect。 And then when you wake up with typical Mesa scheduling you always have to loop back and check your condition again。

 And then you might somehow reserve the thing that you found you've got and then you can unlock and then when you end you kind of lock again and signal that you're done。

 This is a pattern。 Okay， and we did that with the readers writers example。 Okay。

 And this was the readers writers example can have one writer or multiple readers but never a writer and reader will meet。

 Okay， and actually unlike on the exam question， whatever it was。

 The three C maybe you can't have two writers either。 Okay， so one one writer at a time。

 And that was the motivation for the code that we had here。

 which was this was a reader code where you grab the lock。 See the pattern there。

 You check and make sure there aren't any writers either active or sleeping ones。

 And if there are you become a waiting writer and you go to sleep。

 And then when you wake up you're no longer a waiting writer。

 you loop and you keep doing this until you get through without there being any writers in the system and in that case。

 you do a plus plus saying， you're an active reader， release the lock and do the database access。

 and then on checkout， you acquire the lock again， you decrement you're no longer a waiting reader。

 And then there's this condition that if there are no readers left。

 that are active but there's a waiting writer then you go ahead and wake them up with a signal and then you eventually release。

 Okay。 And so why do we release the lock at this point。 Anybody remember？ What was the story。

 Why do we release at this point。 That's right。 Remember this entry things not is not preventing access to the database。

 What it's doing is it's protecting the entry conditions to the database。

 We need to release the lock so other threads can come in and classify themselves right。

 And then the writer is similar， a little bit the same but different。 Okay。 And so here。

 our entry condition for the writer is there can't be any active writers or active readers。

 in which case， if there are either of those we go to sleep。 Otherwise we wake up， we do our access。

 which is a modification style access。 And then when we acquire the lock again we're no longer an active writer if there are any other waiting writers we wake one of them up。

 Otherwise， if there are any waiting readers， we wake them all up。 And then we exit。 Okay。

 And so again， why do we do a broadcast down here instead of signal。

 Might have multiple readers wake them all up， right。 Okay， any questions on this。 Yeah。 Yep。

 right here you're saying， absolutely， get my little。 So right here， up， wake up。

 And then we'll get more than one waiting writer。 Ah， well。

 you just anticipated a couple slides I was going to do here so the question is。

 could we just to get rid of the check and just wake up a writer anyway。

 And then we'll get to that as well。 Yes， because in that instance。

 what would happen is they would check in that loop。

 Now notice that what we do get by doing this set of if and else is。

 is we make sure that we give priority to writers over readers。

 And then we'll get in broad signal the writer， and then broadcast to the readers。

 It's not clear whether one of the readers would wake up before the writer and so we would actually have violated what here is a priority of our policy。

 which is always， let the writers go first。 Correctness wise， it would be fine。 Okay。

 it wouldn't violate the one writer or multiple readers。 Correctness condition。

 but it would violate the policy， but it seems to be what this particular code has right the policy is that writers get priority over readers。

 Okay， good。 So that's actually leads to， you know， why give priority to writers。

 There's actually a couple of reasons for that right one of them is that if you look at typical traces there are more reads and writes so giving priority to the writers is not a bad thing。

 The other is you can imagine writers are making the data more up to date and so you get the writers or the readers a chance to get more up to date data。

 Okay。 That's not required。 You could do any other policy you want and in fact we even have done that another exams in the past。

 The question here about why releasing the lock again I'm assuming the person who asked us in cyberspace talking about this release the lock up here。

 The answer is we have to release the lock up there so that other threads can come in and classify themselves。

 Okay， because if we hold the lock， then no other thread that comes in could get classified as a reader or writer。

 Okay。 Now， the question that was asked is a couple here one is can the can the reader starve。

 What do you think。 Can this lead to a starvation condition。

 It's different from an incorrectness condition。 Who thinks it could why why why did it start go ahead。

 That's right。 So if there's a continuous stream of writers the readers might never get to go。 Yes。

 Okay， so if that's a use condition for you you might have to design your code slightly differently but monitors are powerful enough to do that。

 What if we erase the condition check we just had that question right so what if we redraw out this。

 Okay。 Will it still be correct。 Yes， it'll still be correct because of the while loop。 Okay。

 at the entry way and that's kind of one of the reasons that Mesa is so much more preferred than the horse semantics is you can also be a little sloppy。

 Okay， you can wake up as long as you wake up more than you need to you know you'll still be correct。

 The danger in these kind of situations is you could wake up not enough of them and then the thing would just sort of deadlock。

 Okay， so we don't want to do that。 Actually， I guess it's kind of a live walk will be more specific about that。

 In a couple of lectures so， and then we could just turn this signal into a broadcast and wake all the writers up。

 Why would that still be correct。 Yeah。 That's right only one writer would get it and the others wouldn't and the way to think about this is because of that lock at the beginning of the code。

 All all threads entering the system are serialized by the lock so you only have them look one at a time at the conditions。

 Okay， and so one at a time even if there's a thousand writers one at a time to go through the first one will get the ability to be an active writer the rest will be waiting later。

 Okay， and then finally， what if we only use one condition variable。 Okay。

 so don't separate between reads and writes and just say well it's okay to continue。 Okay。

 now it turns out that what I said about the loop is correct so we won't get incorrect behavior but what could happen if we don't use broadcast instead of signal。

 Yeah。 That's right， because if the readers and writers are all on the same queue and we only wake up one we might not get the type of waiter we want。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_5.png)

 Okay， and so， so for instance what if we turn okay to write an okay to read into a single okay to continue so this is different code here now see the red。

 And we have this scenario where our one arrives， then w one are to arrive。

 well our one is still working。 And so then when that reader goes to check out。

 If we only signal one。 Waiter than what will happen is we'll actually end up signaling the wrong person right we'll signal w one。

 but w one to wake up and say oh look， there are readers in the system maybe this doesn't work so we have to make sure that we get it correctly。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_7.png)

 There， okay。 And so we put a broadcasting here just to make sure there's enough folks that wake everything up。

 All right， and this is actually particularly challenging on the the writer the。

 well it's challenging on both sides so basically you want to just broadcast。 All right。 Now。

 our monitors fundamentally different than semaphores。 Well， you might suspect the answer is no。

 because we managed to somehow do a very complicated cue。 You know。

 for the coke machine right so semaphores were pretty powerful。

 So if they're really equivalent it seems like if we have semaphores we ought to be able to make monitors。

 Doesn't it sort of like a， you know， completeness from a synchronization standpoint。

 And the trick though is we got to be careful。 So first of all locks are easy right monitors have locks semaphores you start you initialize it to a one you got locks easy。

 Okay， promise it gets harder from there right so what if we try to implement condition variables like this weight takes a semaphore and does a semaphore P and signal does a semaphore V。

 Does this work。 How many people think we could implement monitor condition variables this way。

 How many people think we can't and if you raise your hand you have to tell me why。 Go for it why。

 Right， but let's suppose that we could put any value of a semaphore in here we wanted。 Yes。 Yeah。

 so the problem with this is we grab the lock semaphore and you do a weight。

 On a condition variable semaphore you're going to go to sleep with the lock。 Oh。

 everything's broken。 Okay， so this is a bad implementation right off the bat。

 because you can't sleep with this particular semaphore。 So that doesn't work。 Okay。

 Does this work better so wait releases the lock， then does the semaphore P on the condition variable。

 and then re acquires the lock before exiting wait。 And then the signal just does the semaphore V。

 Okay， so this looks a little better because it doesn't lock up because of the because of holding the lock and going to sleep right because you see when you do wait you release the lock first。

 Okay， but does this work。 Yes。 Great。 So this is still broken。

 because remember that signal is not the same as some of the because if you signal first and then wait with this implementation。

 they'll never wait。 Whereas condition variables you go to say wait you'll always wait。 Okay。

 so this is broken。 Everybody see that。 Prom is semaphores or symmetrical condition variable signal is not。

 Okay。 So what can we do。 Well， you know， and you can say here what if a thread signals and nobody's waiting to know up。

 Right。 So what if a thread later weights， the thread weights。 Okay。

 so if a thread signals in a forest and nobody's listening nobody listens， right。

 Whereas if you do a V， and nobody's waiting。 You increment the semaphore and if the thread later does P you decrement and continue。

 And so this will not have the property that every time you fall wait， you will sleep。 Okay。

 So everybody see the problem。 This looks broken。 Maybe we can't do it。 Well。

 the problem with the previous try courses that P and V are commutative result is the same no matter what order they occur in condition variables aren't。

 So if you look， you could say， well， does this stick fix the problem， wait， releases the law。

 does a semip and acquires and signal says if the semaphore queue is not empty， then you do a semiv。

 Does this work。 It works， but it's illegal。 You're not allowed to read the value of a semaphore。

 Okay。 So， there's a race condition here， signal or can slip in the wrong spot。

 But it actually turns out it is possible。 And I'll give you a hint。

 If we keep a condition variable integer of all our own that we use to increment before we release the lock。

 then we can keep track of how many sleepers there are。

 And the signal or can look at that because that's not illegal。 Since they have the lock。 Okay。

 so here is an interesting example where having the lock around a single actually is it would be crucial to this particular implementation working。

 Okay， because if you didn't have the lock and you tried to do check a condition variable or check that integer variable。

 And you don't have the lock， then somebody could change it out from under use that problem。

 All right。 Not going to belabor the point。 So bottom line is can make monitors out of semaphores and you can imagine it's。

 it's even easier to make semaphores out of monitors that's a an exercise for you guys。 Well。

 you're sitting there。 So。 Okay， going to close this out。 But。 So as we go forward。

 The assumption here is that you're going to get better and better at looking at synchronization situations and figuring them out。

 You know it's one of these things where I can give you examples。

 But it's going to be up to you to sort of retrain your brain into thinking about these。 All right。

 But， you know， I think。 If worse comes to worse going to a monitor certainly ought to be the easiest thing to think about。

 I haven't had an example in a research。 Project I'm doing where I suggested that somebody is condition variable because they had to put the thread to sleep。

 And wake it up later and it turned out that was absolutely the right thing to do。 Very simple。

 And these， by the way， are available in a lot of situations。

 including in thread packages like Pete threads。 But I wanted to say a little bit about before we sort of close out synchronization entirely。

 I wanted to say a little bit about。 Support for synchronization in languages。

 So if you go to the thread， you'll see I should put a slide in here on that。

 There are P thread new Texas and there are P thread condition variables。 That are implemented。

 So if you just do a man on the P thread packages， you'll see those。

 So if you're working with P thread， you'll you'll absolutely be able to synchronize with monitors and semaphores。

 Those are available。 Okay。 So， see is a little bit of a crazy language， though。 All right。

 How many people think C is a crazy language。 Okay。

 The worst part about C is it lets you do all sorts of bad things。 Okay， that you should never do。

 All right。 And the worst thing you can do with C is you can have dangling memory pointers that you forget about or you free something twice or there's a lot of bad things there。

 But that's not what we're going to talk about here。 Here。

 if you have some code that acquires a lock and there's an exception inside of the code。

 you need to check every exception path and release the lock before returning from that procedure。

 Because if you don't do that， we'll be leaving this here。 If you don't do that。

 then you can either easily have an exception and return out of the code to the calling function and the lock is still kept and there's nobody to ever release it。

 See that， because normal， normal code is you acquire you do some stuff you release。

 But if there's an exception， you need to make sure to release the lock。 Okay。

 and this makes see really messy for locking。 You just got to do it。

 What even makes it more messy is the set jump jump long jump idea。

 How many of you have run into set jump and long jump before anybody。 You're lucky。

 Let me tell you what set jump and long jump are these are a poor man's version of exceptions。

 which are here's a stack。 You start with procedure A and then you go to procedure B and you call something called set jump。

 which gives you a handle that'll let you throw out a bunch of the stack and return to the place where you called set jump。

 So it's like an exception。 So here we are， we go to C， we acquire the lock， we go to D。

 There's an error or something in E that calls long jump。

 it'll throw all this stack out and go back up there without acquiring the lock。

 or without releasing the lock。 And so， there we go。 Bad news。 Okay。 Now。

 fortunately set jump and long jump are something you use a lot these days。

 but I'm just warning you that and see this is just messy。 Okay。 And then maybe you could use go to。

 How many people have been told that never use go to。 Okay。

 under pain of losing your first born or something to to the sea troll。 I mean， this is， you know。

 so this is not great。 When you get to anything more powerful than see though it turns out it's good。

 For instance， in C you still got to make sure that if if food has an exception， it'll get thrown。

 And you can catch it， which means that you want to do something like this at minimum where you say I'm going to try to do who if there's an exception I released a lot。

 Notice how that's looks like the C code， but this is a lot cleaner because all exceptions will come through that one path。

 Okay。 Now， if you're a C plus plus person in the audience， you'll say， but wait a minute。

 That's not a good way to do it。 There's an even better way。 Okay， and you guys。

 I encourage you to Google lock guard。 Okay， so what this means is here we have a procedure。

 That's going to increment this global variable cleanly no matter who how many people try to do it。

 And what happens here is when you allocate the lock。

 So this is actually on this is a local variable。 Here you allocate a lock guard and it locks the global mutex。

 And the point of this is it doesn't matter how safe increment exits under any circumstances whatsoever if safe increment exit that lock will get freed。

 Okay， so if you're ever doing locking and C plus plus this or some of its variants are the cleanest。

 Okay， because this particular type of thing this lock guard。 Basically。

 anytime it finally goes out of scope， it pulls the path that basically unlocks。 Okay。 Python。 Well。

 you could allocate a lock and then you can say with lock to stop and what that means is no matter how that with statement exits。

 The lock will be free。 That's almost identical to what I just showed you with C plus plus。 Java。

 your favorite， right。 They， I don't know， they still do Java and 61 be good。

 I haven't taught that in a while。 Actually， I haven't taught that when I。

 I'm not sure if you're not going to get things about it， but if you look here。

 you can say public synchronized。 And what that means is that every object has an implicit monitor built in that includes a lock and a condition variable。

 And so as a result， you can say this particular method get balanced。

 You remember when we talked about the bank account is synchronized。

 And this get balance will ever get run by a thread is if it first acquires the objects lock and then it'll go in there and let you go。

 Okay， so just by saying the word synchronize。 We use the law automatically。

 How's that for a lot simpler than the way we introduced this a few lectures ago。 Okay。

 and furthermore， Java has， like I said， a single condition variable。

 You can write every object and so you can do weight。

 and you can also do a weight that has a timeout。 And you can notify and notify all of those who are the full and await and broadcast or have signal and broadcast。

 I mean。 And so that's how you do it in Java。 So Java actually has monitors built into the language。

 which is kind of cool。 Okay。 All right， I think we're gonna we're gonna let we're gonna let synchronization rest for a little bit unless people have some questions。

 Go ahead。 Let's see。 Make sure there's nobody here。 Okay， anybody else have any questions。 Oh。

 in the back。 No， that was a stretch。 Okay。 So， I've been a strivia as easy today。

 Unlatt like last week where you had an exam and a design review。

 and had to solve the halting problem standing on your head drinking coffee。

 This is a relatively minor week。 And so I don't think there's any major deadlines。

 although you got to keep moving on stuff。 I took a glance at the schedule。 And so。

 I'm waiting the midterm。 I was told to say that there's anywhere between 80% and 85% done。

 And of course I want to inform you that。 You know。

 75% of all statistics are made up so you know you can use that as a。 However you want to。

 I'm not sure if anybody has any administrative， it's trivia today。

 So I figured we start a new topic if that's okay with y'all。

 We can put our minds to rest about the midterm there's solutions that are posted。

 There is a thread for asking questions about the solutions and I'm a little behind on answering some of them。

 but I will make sure they get answered。 Should we move forward。 Forward。 Alright， so I want to say。

 here's a picture。 I think I even had this picture in the slides for the first day。

 which is this this loop of what what it is in operating system does it sort of says if there's a ready thread。

 If there are any ready threads you pick one of them， and you run it。

 And otherwise you run an idle thread and periodically you loop。 Okay， that's。

 I think the way I said well this is the whole operating system we're done let's do our final right。

 What we want to do today is we want to start discussing scheduling which is really what is the select red thing。

 There's another picture I showed you here about， you know， scheduling。

 which says there's a ready queue， which is a set of all threads that the CPU is ready to run。

 And really the question is how is the OS to decide which thing on the ready queue is going to be the one that goes next。

 Okay， and so scheduling is really deciding which threads to give access to resources for moment to moment。

 And by the way， for the next several lectures， we'll talk about giving access to CPU time。

 but scheduling is so much more。 Okay， we， you can talk about scheduling this bandwidth。

 you can talk about scheduling， I/O resources can talk about scheduling memory。

 There's lots of things you can schedule， but we're going to just schedule the CPU for the moment。

 because we're really trying to figure out what happens， between the ready queue and the CPU。

 All right， that's our goal for the next couple of lectures。 And I'm happy to admit， by the way。

 that Anthony is actually back so he may actually get to do a couple of these lectures too so we'll get to see somebody else but for today。

 other than me， but for the day。

![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_9.png)

 Scheduling is all about cues。 Okay， and cues I'm sure are your favorite things。 Okay。

 this is clearly from the before times because they're not all wearing masks。

 and they're not six feet apart。 Yes， soon maybe okay。

 What are some assumptions about scheduling okay the first assumption is some of the assumptions really came up from the 70s so scheduling really became a big deal in the 70s。

 And it was a big area of research。 Notice that we only have three lectures on it。

 but it was a really a major area of research。 And many of the implicit assumptions for CPU scheduling actually came from back then。

 And they are sort of like well there's one program per user。

 One thread per program programs are independent。 Okay， so that's a little bit。

 You know that's a very old school way of thinking of things is also kind of what happens when you have a bunch of different users sharing the same machine so it's kind of the main frame look at things。

 Okay， but a lot of the work that was done in the 70s is still happily used today。

 Clearly these particular ideas here are unrealistic but they do simplify the problem in a way that can be solved。

 So the for the very first lecture here we're going to kind of start with this idea in our background to one program per user one program program through independent。

 And then we're going to slowly add in more complexity to our processes as we go forward to get more interesting scheduling。

 Okay。 And so the high level goal just to remind you here。

 this is you know our favorite diagram again from the first day of the printer inverse colors magenta cyan and yellow。

 Those represent different threads we're going to all decide to how to schedule those on a CPU one CPU。

 And notice how now they're all have different amounts of CPU time because they're longer shorter whatever。

 How does the scheduler decide。 Okay。 All right， so far so easy questions。 Yes。 Ah， what is a user。

 So the user。 Is an instance of a principle or somebody who has。

 Resource is allocated to them the simplest thing you could think of as a login right you log in your user。

 The CPU treats you as with your with your user ID。 But as we get a little bit further in the term。

 it can be more more general than that it can be like I said if you have a public private key pair it could be a principle in this in the security sense but for now think of a login ID for now。

 Okay。 Another question here is process scheduling more of an implicit thing by the scheduler like the scheduler who has switched threads and those might be in different processes。

 So up to for now we're not actually going to talk about。

 Or limit ourselves to worrying about which threads are in which processes。 Okay。

 we got a bunch of threads they all need CPU time。 And in answer to this question。

 you could imagine for instance that you might work your way through all the threads in a process and then switch to another process。

 You could imagine。 I can imagine almost anything right。 A large。

 for a Latino or something right you can imagine almost anything。

 But what's interesting there since it was brought up is if you've got processes with 100 threads and another process with one thread。

 What's fair。 Is it fair to give equal time to 100 threads in process A and one threaded process B so that they're really are 101 threads and each of them get one over 101 of the time。

 Or， what it makes sense to give half of the time to process A and have to be and then process A divides all their time up to their 100 threads。

 Okay， so what is fair。 That's going to be a problem here that we have to solve。 Okay。

 So one assumption that was in a lot of these earlier scheduling papers and is a good one is basically this idea of CPU bursts。

 where if we look at how long does a thread run。 Oh yeah， go ahead。 Is program the same as process。

 Well， I'm going to say yes for now。 Imagine you know about for right so program could have a bunch of processes and then in that case program and process are not quite the same thing but we can only so throw so much complexity in one day so let's stick with one process per program just for now。

 But if you notice， when you have a thread and it's circling between the CPU and the various weight cues。

 You could say how long does it run on the CPU before it's put the sleep。

 So if you have a timer going off and it computes forever。

 Then what you'll see is you'll just see threads maybe cycling between CPU and weight cue。

 And they all have exactly the same amount of time they get to compute before they go to sleep。

 And so， we actually put IO into the picture， then you can imagine that some number of those threads are waiting are only woken up because of a key stroke on a keyboard and they run for a little brief free to time and then they go back to sleep on a way to associate with the keyboard。

 Okay， so there's a lot of reasons that threads could go to sleep and so if we were to measure this called the CPU burst time which is kind of how long does a thread run before it goes back to sleep again。

 So， something like this peak here， where there's a lot of really short bursts and some and a very long tail tail of long ones。

 Okay。 And so programs or whatever they are threads we're not going to get too tight up at all of this yet。

 So， there's threads run for a period period of time called a burst and then they go back to sleep。

 And if we were to measure this think of this as a probability distribution of bursts of threads you see this peak at the low end。

 Can anybody give me an idea where that peak at the low end might come from。 Okay。

 the duration of a timer interrupt。 No， let me explain why I don't think that's what you're looking for。

 So if everybody was bounded by a timer interrupt。 Then there would be a like a delta function at one time right because the。

 you know you'd run for 10 milliseconds a timer go off the next guy run for 10 milliseconds。

 But we have this distribution that's not like that right it's got some peaks at the low end and a very long tail。

 And because there's things with the long tail， you have to suspect that if the timer ever gets involved。

 It's interrupting folks way down here。 Right， because they're running for a long time and then they get interrupted。

 So why do we think there's a burst down here。 Yeah。 Starting up the process。 All right， maybe。 Yeah。

 go ahead。 Okay， I owe you're getting。 Yep， that's pretty good。 Getting closer。 What about I owe。

 Yes。 Okay， maybe it's disk access time， although actually that's going to be way the heck out here in a place you can't see on the screen because remember million cycles。

 What type of I oh yeah。 Okay。 So， yes， you have to load the program so I'm going to give you a guess here so somebody says actively computing and then waiting for I owe yes。

 Point number one。 Why short interactive processing right because you。

 you're waiting and you get a key stroke and you process that the letter a。

 and then you go back to sleep and then they type a B and you process the letter B and go back to sleep。

 So things at the low end here tend to be interactive。 Okay。

 there are situations where the program threads are running on behalf of a user and making the user happy by quickly processing some event from the user and then going back to sleep。

 Okay， and now if we start including other things like I owe of other sorts。

 And we look at this much longer realm， but I think the important part here is if you look at the set of threads out there。

 There's a lot of really short bursts and that's because in even back then you have these machines are processing user interactive。

 I owe。 Okay。 And so every scheduling decision。 Kind of is about if you've got a whole bunch of threads。

 how do you pick the next one。 This shows you if you have a bunch of threads and you run them。

 What did they behave yet the scheduling decision is before we run it。

 How do we decide which are the ones to get。 Okay。 And what。 You know。

 and with time slicing in the timer you probably could be forced to give up the CPU if you're computing pie or something but why can somebody tell me why just processing the threads in BIFO order might not be the best for users。

 Yeah， so users have some interactivity they want to have happen。

 And if you're busy computing the next million digits of pie。 Maybe you don't care。 Right。

 So it might make sense to give priority to the short burst over the long ones right and that's for interactivity。

 So scheduling here you can see starts to come into play with how do we make sure that the scheduler makes users happy。

 So that's going to be important to us。 So what are some goals that we might have for the scheduling policy。

 So one might be we want to minimize the response time。

 So this is minimize the elapsed time to do some operation。

 So it might be the time to echo a keystroke on in an editor or the time to compile a program。

 or maybe with real time tasks which are going to be more topic for next time。

 We might want to meet the goals imposed by the world。 Yeah， it is interesting。

 It hasn't escaped my notice that there's a lot of Tesla model wise floating around these days you guys see them they're like every other car on the road practically。

 But here's a situation where you have cars that are driven by computers。

 And you can imagine certain things really have to happen quickly like breaking。 Okay。

 so if we go back to this， and we're talking about， you know。

 what to prioritize it might be in a real time sense we better prioritize stopping over missing the video that you're not supposed to be watching。

 Right。 So real time tasks scheduling starts to get very interesting。 Okay。

 and we're going to have to have whole lectures on that include real time in it。

 So another is maximizing throughput。 So these， you know。

 things have gotten a lot cheaper over the years， but it's still important to maximize the best use of your CPU。

 And so maximizing throughput could be important and maximizing throughput and minimizing response time are not necessarily compatible with each other。

 Okay， because minimizing response time might mean as soon as a user's responsive thread needs to run。

 go ahead and interrupt the current one and run。 That gives you response time minimizing response time。

 but maximizing throughput might be never interrupt a computing thread so that it's cash state and all that other stuff gets to be undisturbed and the thing can run at maximum speed。

 Right， so minimizing response time maximizing throughput， not quite the same thing。 All right。

 And then of course there's this fairness thing which is you should sharing a CPU among users or among different aspects of the system。

 So in this case， like in a Tesla users could reflect breaks video playback， you know。

 whatever you could， you could divide all these things up。

 Those are all different users and we need to have different priorities among them。 Okay。

 and so that that little conundrum I gave you earlier about what it means to be fair to the threads in a process with 100 threads is a little bit tricky because you could do fairness by thread or fairness by process or fairness by who knows what else。

 Okay。 Good。 I don't want to belabor this point， but any other questions on this so far。

 So now you can start to see why scheduling is not just yeah a couple of slides were done。 Right。

 because you know you have to decide what's the policy you want。

 and then you have to decide how do you build a good scheduler the kids you have policy。 So。

 the first type of scheduling is easy and let's talk about this first come for serve or FIFO。

 So the idea there is basically a thread goes on one cue。

 and it runs until it's done and then you pull the next one and then you pull the next one and then you pull the next one。

 right。 And so， there you go。 There's a， there's a FCFS or FIFO Q。 And in early systems。

 this was basically meant that one program runs until it's done， including IEL。

 So you'd have these huge machines they'd fill a room。 You would submit your job to run overnight。

 and they would run them one at a time。 They'd run the first job， then they run the second job。

 then they run the third job。 And they would do that to really maximize usage of the hardware to make it work as good as well as possible。

 Okay。 Now， we can think of a modern update to first come for service you run until your first runs out。

 and then you go to the end of the queue。 Okay。 So this is that there's no timer interrupt here。

 This is just run into a bunch of bursts until you do something that requires either IO or you're actually done。

 Okay。 And so we could do this with a Gantt chart like this so suppose the processes arrive in order process one。

 two， three， and suppose the process one。 As a first time of 24 process two as a first time of three process three as a first time of three。

 Then， if I， if they arrive in that order and I process them first come first serve what does that mean it means I serve process one and then process two and then process three。

 And so if you look at that， that means if I have one CPU process one runs for 24 time units then process two runs for the next three and process three runs for the next three。

 And we can start computing metrics like what's the waiting time for process one zero because it doesn't have to wait。

 What's the waiting time for process to 24 because it's got to wait for process one to finish。 Okay。

 everybody with me on this。 Okay， and then we can come up with what's the average wait time。

 So zero plus 24 plus 27 over three average wait time is 17。

 and then average completion time so wait time until you get to start completion time is until you're done。

 And so we can compete those two metrics。 Okay， now this is not terribly profound or hopefully not too difficult either unless you can't add and divide which of course that's always a problem we'll have right。

 You can imagine that this average waiting time and the average completion time reflects something about goodness of the scheduler。

 especially since the average waiting time if you've got a bunch of interactive threads that are waiting to run。

 You probably want to keep the waiting time as low as possible to keep your users happy。 Right。

 so this is a metric that maybe we need to optimize。 And actually if you look at this。

 but it's really unfortunate about this is only because process one arrived first through process two and three after wait so long。

 So this particular scheduler is really sensitive to what order things arrived in， you know。

 and that's， that's probably not a good thing。 Right。

 And so we actually have here what's called the convoy effect。

 which is short processes get stuck behind long processes。 Right。

 this is also known as the five items or less problem。

 And safely right do you think you're going into the five items or less line except that the person with their one item is a is a cart full of 12。

000 items right and so they never worked like there should。 Okay。

 so if you look at this convoy effect we could graph this out。 So， we have sort of scheduled task。

 Here we have the green one arrives dark green arrives blue was already ready running。

 Now green gets the run， you see this so this is the actual scheduled task， these are the cues。

 And so， we basically we had blue running green and dark green showed up there run to completion then red shows up。

 etc。 And we can start tracing through this but suppose that red that showed up is going to take。

 a long time。 Notice how we take red off the queue and started running so light blue is the head of the queue and green shows up and purple shows up and some other color of green forest green shows up and then blue。

 And notice how all of these threads showed up in our building up in our queue。 Well， red is running。

 Okay， so that's the convoy effect because they're all stuck in a convoy behind red。 Again。

 hopefully that's just a graphic。 Example of why maybe first come for search that's terribly great for us。

 Okay。 So here's a and here's the other thing to see right if they happen to show up in the other order like P two P three and then P one。

 Then we could compute stuff and notice that our average waiting time now is three instead of 17 and our average completion times 13 instead of 27。

 So just by reordering， we've got really happy users now are much happier users。 Okay， so。

 so the pros and cons of this fight for first come for serve is plus simple。

 Minus short jobs stuck behind the long one。 And that's the safe way example。

 I guess the positive is your stuck in line to get to read about space aliens。

 while you're waiting to check out counter I guess there's something but。 All right。 So。

 the question here also is first defined as a period of time with lots of computation activity no burst is the time。

 Of from when you start running to when you stop running and then we graph that earlier。 Okay。 Now。

 let's do something different。 Okay， go ahead question。 Ah。

 so for now let's assume the scheduler is infinitely fast。

 So it doesn't have to run very long all that has to happen is when P two finishes at that little sliver of time we asked the scheduler who's next。

 And the scheduler says P three。 And if you think about a FIFO queue。

 there's not a lot of computing cycles involved in a FIFO queue。 Right。

 Now as I mean you just pull the thing off the head of the queue。 Now as we get more interesting。

 Our structures are going to get more interesting and you guys are going to have to remember your 61 B so like we could have a heap structure or something like that where we're trying to pull the shortest predicted burst time off the queue but we're not there yet。

 So for now let's just assume the scheduler runs in that infinitely small period of time from when we ask it to get something back。

 Okay， yeah question。 So for now， remember that all of the mechanism mechanism for putting threads to sleep and waking them up all that's in the kernel。

 And that when you go to put a thread to sleep you ask the scheduler will still in the kernel to give me the next thread so all the way cues all that stuff is in the kernel for now。

 Okay。 We'll get more interesting at other times but for now everything's in the kernel still。 Okay。

 so this， this doesn't seem great。 Okay， so first come first service basically not done in interactive systems at all。

 Okay， so what else could we do。 We could do something called round Robin。 So this。

 so the problem with the first come first serve scheme is it's potentially bad for short jobs。

 Depends crucially on the submit order。 Okay， if you're first in line the supermarket with milk you don't care who's behind you but on the other hand if you're behind somebody you do care who's behind you're in front of right。

 or who's in front of you so the round Robin scheme。 Is what we call preemption。 Okay。

 Sorry about the robin there but I was， I got a little carried away with clip art at one time so this Robin I。

 I'm not subjecting you to this Robin spinning around here so we're good。 All right。

 The round Robin scheme often called preemption is very simple。

 and we've been talking about this since day one， but you didn't realize it。 It is， you run a thread。

 a timer goes off you take the thread off the CPU you put it at the end of the queue and you take the next one and you run it。

 Okay， that's called round Robin believe it or not and it's because all of the threads are going around between the ready queue and the CPU。

 Okay， and after the quantum expires whatever that is well I say here between 10 and 100 milliseconds that's a pretty standard number for a modern Linux kernel is 10 or 100 milliseconds。

 And after the quantum expires the process is preempted and we had the current thing to the end of the queue and we grabbed the one at the head。

 So for instance if they're in processes and already Q and the time quantum is Q。

 Every process gets one over end of the CPU time just because it gets one end。

 And in chunks of it most queue time units。 And so if you think about it no process ever has to wait more than n minus one times queue time。

 And why is that well it's just you have to wait for the folks in front of you and then you get to go。

 And so we can tune Q down if we wanted to to make things more responsive to make sure that if somebody were an interactive thread they could run quicker。

 Okay， and if you notice I have the quanta here as a range between 10 and 100 milliseconds being standard。

 I think I mentioned this in a previous lecture let's see if you remember what what is significant about 100 milliseconds and humans。

 Hopefully your reaction time is a little faster than that normally。 What else。

 but that's your on the right track。 It's when you start getting annoyed so when things feel laggy。

 Okay laggyness is certainly at 100 milliseconds they done a lot of studies。

 For this okay and you can imagine if there if you're heavily interactive you might want to get down to the 10 millisecond range or whatever。

 Okay。 But so performance you can imagine a lot of tuning here so if Q is really long。

 Then you almost never have the timer go off and you basically just have first time for a serve again。

 Right， because you almost never cut anybody off。 If it's really small。

 You're interleaving because you run for， you know。

 a few milliseconds and then the next one runs and the next one runs。

 And if you really went down to like one， maybe it's like hyper threading except you'd never do that because the software is running this right so this would be all overhead and no computing。

 Okay， so Q has got to be large with respect to the context switch time。

 Because otherwise the overhead is too high but you want it small enough that interactive jobs don't annoy their users。

 So you can see there's a trade off there。 Okay， questions。 So actually。

 you can't leave that up there long enough any questions。 So now if you look。

 here's an example of round Robin with the time quantum equal to 20。 So process P one。

 First time a 53 process P two first time of eight process P three versus the key eight process for 24。

 So imagine the quantum is 20， which means we wait 20 units of time before the timer goes off。

 So notice if P one starts， it gets to run for 20。 Before it gets killed off restarted using put back on the end of the queue because the first time is over 20 right so we run for at least 20。

 And now P two only runs for eight。 Why。 Because the first time is only eight right。

 So it's going to end at eight and then P three gets to run for 20 because it's time is at least 68。

 Before gets to run for 20。 And then as we work our way through notice that P two is already exited the system。

 etc。 And we could， we could go through those one at a time and that might get very agonizingly painful so we won't。

 But we could say what is the waiting time for different threads so P one's waiting time is notice it starts out with no waiting time。

 But then it has to wait 68 minus 20 units of time right。

 And then it also has to wait 112 minus 88 units of time。 So we could see that for P one。

 the total amount of time it waits is is 72 here。 And similarly we can compute for all the other ones。

 And then the average waiting time is 66 and a quarter and the average completion times 104 and a half。

 So that。 You know， those are just numbers， but you can see we can use these metrics to start playing with。

 Like as we change the quantum， do we have a better average waiting time or not。 Okay。

 and so the brown Robin， the pros are it's better for short jobs by far than first come for serve context switching time adds up for long jobs。

 Okay， and here， we're assuming just because it slides in class that there's zero context which time but we all know better。

 Right。 So if you switch a lot， you know you're going to add up a bunch of time saving and restoring registers and doing all that sort of stuff。

 Okay。 And so， for instance， here we had when we have if we have a quantum of 10。

 and we have T one and T two， we see that we get an average response time that's long if we have a shorter quantum。

 Notice that our average response time goes down。 Why？ Well。

 because we get T one out of the way so T two can run。 Okay， make sense。

 Here we have two threads with a quantum of 10。 Well。

 the quantum of 10 doesn't affect the two threads because their first times are one。

 So the average response times 1。5。 Same with the quantum's one so quantum here doesn't change anything。

 Okay， so now you're going to start to say wait， this is very dependent on the threads。 Yes。

 unfortunately it is。 Right。 So here。 If our quantum goes from one down to a half。

 The average response time goes up。 Why is that because we've gotten to a point where we're switching too much。

 It actually makes things a little worse on the average response time front。 Okay。 Now。

 you can obviously see。 Mid term questions out of this。 But hopefully you don't get hung up on that。

 Try to get some insight here right so。 How do you implement round Robin in the kernel。

 I'm going to show you that trade off with you in another slide in a second。 But a five oh Q。

 Just the same is with first come first serve， but you preempt the job as soon as the timer goes off。

 you take it off of the CPU， put it on the end of the queue and just keep going。 Okay。

 Time or interrupt。 So I've been talking about round Robin since the day we started。 Okay。

 lecture one round Robin。 So in this ready cue。 Here's the cue we're talking about right there。 Okay。

 hopefully not too mysterious。 Project two。 Not there yet。 You get to work on scheduling。

 This is a relaxing week。 You work on project one。 But when we get to project two。

 you get to work on scheduling。 Okay。 Now， you know， how do you choose the time slice？ Well。

 hopefully you see if it's too big。 The response time suffers。 If it's infinite。

 you get first come for serve。 Time slice too small。

 You're through put suffers and you swap too much。 And so actual choices。 I said again。

 we're between 10 and 100 milliseconds。 And， you know， originally in Unix。

 they actually had a one second time。 And I have to say。 I wrote papers with multiple email access。

 Talking to the same mainframe。 And it was amazing when there were too many users you type a long phrase。

 To be or not to be that is the question。 And a second later it would go。

 And you get your to be your thought to be that is the question。 So not interactive。 Even slightly。

 Okay， try to imagine editing a paper like that。 It was。 Not fun。

 So you got a balance short job performance and long job throughput。

 So typical time slices 10 milliseconds to 100 milliseconds。

 Typical contact switch overhead between point one and one millisecond。 And so roughly。

 you could say we're getting about a 1% overhead of switching。 So that's not too bad。

 We're not wasting。 More than about a 1% of our cycles doing the switching。 Okay。 Questions。 Good。

 Yeah。 Ah， is the time slice always constant or can it change？ Yes。 So。

 mostly people leave alone and it's constant。 But you can change it under some circumstances。 So。

 it depends on。 It depends on your scheduler and system。 But， you know。

 the problem with the problem with the quantum and I'm going to show you another slide just a second here is。

 It's a pretty。 Course。 It's a pretty good thing to tune。

 It doesn't necessarily give you what you want in terms of really responsive and so on。

 It's pretty good。 It's a nice kind of heuristic that works pretty well most of the time。

 And so trying to fine tune cue。 It is probably not going to be worth the trouble。 But it's a。

 it's an interesting thing to think about。 And in principle， you can。 I'm going to put this up。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_11.png)

 I wanted to put this up because。 Let's put a couple more slides up here。 So simple example。

 you got 10 jobs each。 Take 100 seconds of CPU time。 Round robin scheduler quantum of one second。

 All jobs start the same time。 So you can look at the completion times here with FIFO。

 And then you're done in a thousand cycles and again we're assuming that there's no overhead to switching with round robin in one second you're just doing。

 you know。 Job one job to job three job for job。 You work your way through and。

 That will also end in a thousand because they're both。 You know。

 100 times 10 total CPU cycles are needed。 So they both finish at the same time。

 but the average response times much worse under round robin here。

 And the easy intuition is with FIFO you got some jobs that end really early。

 whereas with round robin they all end really late。 So the， the， you know， the。

 the average response and final response final completion time are very bad。

 And in this round robin case， your cash state keeps getting swapped out so to any。

 to the extent that your CPU is doing a nice job trying to get things in cash。

 This is kind of working against throughput for you。 Okay。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_13.png)

 So here's another slide。 You know， cyan and Fuchsia great colors right so the best for suppose we have threads here P one is 53。

 P two is eight P three is 68 P four is 24。 We showed you that earlier。

 The best first come first serve is if the shortest one goes first and then we go the next longest and the next longest and the next longest。

 And so you can kind of see。 From a wait time standpoint， the best first come first serve。

 And then for the average of 31 and a quarter， the worst gives you an average of 83 and a half wait time。

 And then from a completion time we get 69 and a half and 121 and three quarters for completion time。

 We can say at the quantum is eight。 We can see that we get our average wait time to 57 and a quarter and average completion time to 95 and a half。

 So notice that that's between the best and the worst。

 And then of course we can put all these other ones in the middle。 And you can see that， you know。

 as long as you're kind of in the middle， it mostly works pretty well。

 And fine tuning plus or minus is not really going to give you necessarily anything consistent there。

 Okay。

![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_15.png)

 Notice also though， P2。 What about P2 P2 is eight。 It's the shortest one。

 Notice that P2 has the worst variance in possible scheduling here。 So notice。

 if P2 is short because it's an interactive job for a user。

 Notice that it has awesome wait time at zero or really bad wait time at 145。 Okay。

 so this user is really either really happy or pissed。 And fortunately。

 if you kind of get a reasonable quantum there。 Neither right there just they're okay。 Right。

 So the shortest job gets the most impact by varying the scheduling。

 And the other thing to notice the longest job， like we're computing digits of pie has the least variation because notice。

 unless you pick the worst first come first serve when it gets to run first。

 It's otherwise basically the same， no matter what your quantum is。 So what is that。

 What's the bottom line from this slide the bottom line from this slide is。

 You want you don't want to worry as much about the long jobs because the short ones get really impacted by scheduling。

 Okay， and the short jobs are your users。 So what that says is really annoyed users are much easier to get than annoyed computations of pie。

 Right。 Good。

![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_17.png)

 Now， that's all fight and dandy， except that the problem with this is kind of everything is mostly treated I they're treated identically here right because we。

 we basically say we set a timer。

![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_19.png)

 And if the timer goes off and you're still running we put you at the end and we'll run you again later that's the only thing that's going on here and all tasks are equal。

 But we can imagine， instead wanting to prioritize tasks and suddenly we've got a priority scheduler。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_21.png)

 And you'll get to learn a lot more about this and when you start doing number two of your projects。

 And so if you look here， we could have， you know， priority three priority two priority one priorities you're。

 Zero queues。 And this now we have an execution plan which is always execute the highest priority runable jobs to completion。

 possibly with a round robin and then go to the next priority in the next priority in the next priority。

 So notice that now， not only do we have round robin to make sure sort of all the jobs kind of make progress at a given priority level。

 but we've now put priorities on them。 So that we can decide that some jobs are more important than others。

 Okay， you've all read animal farm， how many people remember animal farm right。 Some。

 some animals are more important than others all right so that's what we get out of this priority scheduling。

 Okay。 Now， of course the problem with this is going to be choosing who's what priority right picking the priority so that you get whatever effect you want it's going to be tricky。

 But， and some problems that are pretty obvious hopefully is that starvation becomes very possible。

 If you've got a job stuck at the lowest priority and nothing but higher priority things come in and the low priority one will never run。

 Okay。 And so， you could actually end up with something even worse which is a priority inversion。

 And this actually took out the Martian Rover。 And maybe I'll make sure we talk about that next time but what happened there was if a low priority job grabs a lock。

 And then a high priority job is waiting for the lock。 Okay。

 and a middle priority job is running computing pie。 Now you're now you're dead law。

 Why is that well the high priority ones trying to sleep。

 They're trying to get the lock but sleeping the middle ones running and the low priority one can never run and release the lock。

 Okay， and that is a situation that will never resolve itself。 Okay。

 And it turned out there was a problem with the Martian Rover just like this。

 And where the high priority was was the bus and the low priority was a particular measurement scheme in the middle priority was doing some maintenance of the of the device。

 And the only reason they actually managed to get the Rover to do the right thing。

 This is one of the original rovers was they were able to reboot it and debug it from earth。

 which was pretty fortuitous。 So， so how do we fix problems with priority scheduling well that's going to be an interesting topic for us。

 Because we got to start varying the priorities dynamically。

 So we start with a given set of priorities but then we move things up or down based on dynamic heuristics。

 Okay， and that's how we're going to play with this。 Okay。

 so hopefully you're starting to see that scheduling gets more interesting with the moment right or maybe more complicated。

 I don't know。 We'll have to talk about that。 So we can ask ourselves what about fairness。

 So strict fixed priority scheduling between cues is very unfair。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_23.png)

 Okay， this， this is unfair because as long as there are priority three jobs。

 none of the lower priority ones get to run。 But maybe that's okay if the priority three jobs are trying to put the brakes on。

 Okay。 Now the question I just got in the chat is， is what I'm saying here about priority rearrangement。

 meaning that the something with the lowest priority could suddenly become the highest。 Well。

 in fact， yes， there's something called priority donation。

 where if a high priority thread is trying to grab a lock， but a low priority one has the lock。

 All right， what will happen is the high priority one will be able to donate its priority to low priority one so that it can run long enough to release the law。

 Okay， and that's just one of many dynamic priority things we're going to come up with。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_25.png)

 So， so strict priority scheduling between cues is unfair。

 There was an urban legend that's absolutely not true。

 but I'll repeat it anyway because it's an urban legend， which was in multi。

 They shut down the machine and found a 10 year old job that had been sitting in the queue for 10 years and never run。

 Okay， the only thing this serves is to point out that urban legends are ridiculous。

 And be a B and be that。 Trying to make it very clear that low priority things might not get to run。

 Okay。 So you have to give long running jobs， some fraction of the CPU。

 you do strict priority scheduling。 Maybe you won't have a job stuck for 10 years。

 but you could have very well have a job that you want to make some progress that never makes progress。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_27.png)

 Okay， so this in its purest form is probably not a good plan。 Okay。

 but it starts to give us the idea of knobs that we can twist to try to allocate CPU to things that matter in the moment。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_29.png)

 Okay。 So the trade off is the fairness gained by hurting the average response time。

 So what we do is we give the long running jobs a fraction of the CPU。

 then they're really short ones。 Get less CPU and that might be okay。

 So how do you implement fairness， you could give each cue some fraction of the CPU。

 If you have one long running job and 100 short running ones。 You know， what do you do。

 you could increase the priority of jobs that don't get service。 Yes， go ahead。 Ah， so the。

 is there a way to decide your priorities。 So the tricky part about that question is。

 You think you're doing you come up with a good scheme and invariably it's not a good scheme。 So。

 there's lots of ways that people pick priorities。 Okay， and just because I like answering questions。

 I'll give you this one。

![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_31.png)

 Assume for a moment that there's 140 priorities。 And the bottom one or the top 100 of them。

 the most important ones get chosen based on how frequently an event's going to happen in the bottom 40 get chosen based on what we're talking about。

 That's exactly what the Linux scheduler has it has 100 real time priorities。

 And the way you choose a priority is the thing that occurs with a higher frequency gets the higher priority。

 And so there's a way to assign based on its period you could choose one of the hundreds。

 One of the hundred priorities and that's a mathematical choice。 And then the remaining 40。

 And then the problem we just talked about， which is you got to choose。

 but that's at least one way of assigning priorities that matter。

 And I'll talk about that when we talk about real time。 So， you could each。

 we could get each queue of some fraction of the CPU。

 And then we could increase priority of jobs that don't get service。

 So if a job is running for a very long time and it's not getting any service。

 then you could slowly up its priority to give it more service。 Okay， that's kind of dynamic。

 But I want to close with this idea of what if we knew the future instead。

 Could we come up with the best first come first serve because remember。

 first come first serve is only bad some of the time where it's really bad。

 But sometimes it's really good。 Right， a really good first come first serve is what we manage to have the shortest jobs first。

 That's great。 Right。 But can anybody tell me why it's hard to do。 No， right。

 you would have to do a good job predicting。 So instead， in the last couple minutes of the class。

 what I want to do is， what if you knew the future。

 So I'm not going to tell you how to know the future yet。

 We'll do that next time and you guys can get your stock trading accounts out and stuff but。

 Suppose we actually knew。 Okay， then we could get an algorithm。

 an algorithm we're going to call the shortest remaining time first， which is when。

 when you've got a cue and you got to pick the next one you just grab the one。

 You just grab the one who has the shortest remaining part portion of their birth， and you run them。

 Shortest remaining time first and there's actually a， a shortest job first。

 which is the non preemptive version but let's just talk about shortest remaining time first。 And。

 and we can apply it to the whole program or to birth or whatever but if we knew the future。

 Then we could do this SRTF and it turns out that SRTF which again it's， we look at the cue。

 I picked the one with the shortest runtime left and I run it has the absolute best minimal average response time。

 So if we could somehow figure out the future we could do that。 Okay， and it's provably optimal。

 Okay， to the extent that provably optimal involves predicting the future。

 So if you compare SRTF with first come first serve， for instance。

 what if all the jobs are the same link。 Well SRTF just becomes the same as first come first serve why 10 jobs that are equal link。

 They're all the same like you pick one， it starts running。

 it's no longer ever going to get preempted because it's now the shortest one left right so it runs the completion next next。

 Okay， on the other hand if the jobs have the varying link。

 the shortest remaining time first just make sure that short jobs always go first。 Okay。

 and here's a benefit。 So if you have three jobs we have a and b are really long so they run for a week。

 See has to run for a very short period of time because it's doing something like copying data off a disk。

 So it computes what the next data get off the disk is that it does the disk time and then it computes the next thing。

 And so to get maximal behavior。 What I'm going to want to do is run this thing at extraordinarily high priority for the brief compute and then I send things out to disk and I can run something else。

 So the only way that this job gets maximum bandwidth out of the disk is if we're always running the short little compute type thing at highest priority。

 Okay， and these guys in the background they're going to compute for a week anyway so they don't care if we interrupt them。

 Okay， so with first come first serve， if a or b gets to run， see is just toast。 Right。

 it will just not work because you got to wait a week。 Okay。

 and you don't copy things off of the disk。 So round Robin。 Well with round Robin。

 you kind of get this right you run see for a very short period of time。

 and then it does its disk access。 And then it gets to run for say 100 milliseconds and be for 100 milliseconds and then see runs for a very short period of time。

 Okay， and if you look at this previous slide here。

 We want to see actually to run for one millisecond and nine milliseconds at this time。

 So it's only with one millisecond and nine milliseconds at this time that we get 100% of the I/O。

 And so here， our disc utilization is now nine out of 201 it's only 4。5%。 Okay， so this is bad。

 If we round Robin it， we waste a huge amount of time。

 We can get the disc utilization back up to close to 90%。 With SRTF。

 we can get it to be exactly 90% which is the best we can do。

 So I'm going to close there for now we're going to pick up this next time。

 But and we're going to take that prediction of the future and we're going to figure out how to do that。

 But round Robin's scheduling is give each thread a small amount of the CPU time when it executes cycle between all the threads shortest job first。

 It's going to be run whatever job has the least amount of computation to do and do that somehow by predicting the future。

 And we're going to turn all that into a multi level feedback scheduler which gives us somewhat of a prediction of the future。

 All right。 Have a great rest of your Tuesday and we'll probably see you on Thursday。 Ciao。



![](img/f6c4cf6f6acdc9fbdb98280ebf30c638_33.png)

 [BLANK_AUDIO]。