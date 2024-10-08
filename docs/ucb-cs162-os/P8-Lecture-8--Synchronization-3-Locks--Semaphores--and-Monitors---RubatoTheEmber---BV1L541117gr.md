# P8：Lecture 8： Synchronization 3 Locks, Semaphores, and Monitors - RubatoTheEmber - BV1L541117gr

 All right。

![](img/22a440ab5259f377d19dc5be83e46a76_1.png)

 Welcome back everybody。 So we're going to pick up where we left off last time talking about synchronization and。

 see whether we can get through lock semaphores and monitors。

 So this should be an information filled lecture。 So if you remember from last time， for some reason。

 there we go， we talked about the too， much milk solution。 And if you remember。

 we were trying to figure out how to make a lock with only the， with， only loads and stores。

 And this got pretty complicated pretty quickly。 This was a solution that actually worked。

 But if you notice， the thread A and B code is actually different。

 And we said that if you were to generalize to end threads， there would actually be end。

 different threads and different pieces of code。 I mean， so this is not really very desirable。

 And you can figure this out basically at this point X， we know that if there isn't a note， from B。

 then we'll be able to keep going through because B won't accidentally do the。

 critical section and at point Y， we can say that if there's no note A， it's safe for B， to buy。

 So this works， but it isn't really very satisfying。

 And I'll also point out that it's got a really bad property here for thread A at least。

 It could potentially sit here and spin for the whole time that B goes off to get milk。

 and comes back。 So this is what we're going to call busy waiting later。

 And this is really a sign of a bad synchronization protocol。 So what we really want is we want。

 when you have to wait for a lock， we want it to go， to sleep。 Okay？ Are there any questions on this？

 Are we good？ So this was not so much a solution as an aspiration。 We said， well。

 what we really want is we want something that's gotten acquired in release。

 that we can pass it in an address of a lock， let's say， and a choir will wait until the。

 lock is free and grab it and release will release the lock to let somebody else grab， it。

 And so the nice thing about this is if we have a uniform lock like this， we can put a choir。

 and release around any critical section， like for instance， this one for our milk。

 And it will make sure that there's never more than one thread inside that critical section。

 at a time， and therefore we won't end up with too much milk。 Okay？

 And not only will not end up with too much milk， but it's pretty easy to just look at。

 this code and know that it's correct。 So this is much simpler than that previous thing。

 which was kind of hard to evaluate， right？ Okay。 And so in the critical section， by the way。

 is the piece that we're protecting so that only， one thread can get in there at a time。

 And the other thing， obviously， about this acquire is we sleep。

 So if there are 12 threads that come in simultaneously， one of them gets through。

 the other one goes， to sleep， the other 12 or 11 of them go to sleep without doing anything。

 They're not spinning， they're just on the wait queue。 Okay。

 So that's going to be our desired goal for building a lock。 Now before I go past the API。

 I want to make sure there aren't any questions on this。 Does this make sense to everybody？ Okay。

 Questions？ All right。 So we then said， okay， we're going to build a lock。 What do we do？ Well。

 one thing is we could start using， so clearly having only loads in stores doesn't。

 help us too complicated。 So instead， we want to do something with some other hardware of some sort。

 And the one thing we know about is we know about interrupt， disable and enable。

 And if you think about the way we built our scheduler and thread multiplexer so far is that。

 what a thread's running， the only reason it'll ever switch to another thread is either there's。

 an internal or an external event。 Internal events are all those cases where the thread chooses to go into the kernel。

 Maybe it's doing a read system call。 Maybe it's doing a yield， whatever。

 And we can avoid that by just not doing it。 So the only things we really need to protect against is external events。

 What's a particularly important external event is a timer interrupt going off， which will。

 take the thread that's running， swap it out for another thread。 Okay。

 So that would be a point at which we could potentially violate the critical section。

 And so that's why if we disable interrupts and in particular disable the timer interrupt。

 then we won't have to worry about critical sections。 Okay。

 So that's why interrupt disable is an interesting thing for us because it potentially allows。

 us to prevent scheduling。 Now this only is going to work for a uniprocessor because when you disable interrupts and re-enable。

 them， it's easy to do on a single processor。 But if you have more than one core。

 it's much harder to disable interrupts across all the， cores so that one thread can run。 Okay。

 So whatever we come up with now is not going to really work well on a multi-core system。

 but it does work well on a single core。 And we could do this， right？

 This is the naive approach we said。 Well， you acquire by disabling interrupts and you release by re-enabling them。

 And again， the reason that works is because we know the timer is not going to go off and。

 so we can run that critical section and no thread will get in there。

 There's the only way a thread could get in there is that the timer goes off。 Okay。

 Everybody with me？ But this is not good。 Okay。 Why is this not good？ Yeah。 Yeah。 So your program。

 which you could think of a user program， for instance， might be running， a lower priority。

 There might be something high priority that needs to get in there。 And in particular。

 we can't even let the user do this。 So we kind of said。

 the problem is we never want to give the user control of interrupts。

 because they could say lock a choir and then accidentally go into an infinite loop or intentionally。

 thereby crashing the whole machine。 So whatever this is， this is already bad。

 but it's even worse because when we're disabling， interrupts for a long period of time。

 then it's possible that there's something really crucial， that comes in like， gee。

 your reactor is about to melt down。 And you're going to ignore it because the interrupts are disabled。

 Okay。 And so interrupt disable like this is just not a good plan。 Okay。 Just too drastic。

 But so far， we don't know anything better。 I haven't told you anything else that we could use other than load store and interrupt。

 disable。 So let's see if we can go a little better than this。 Okay。

 And that's where we were as we ended last time。 And so we came up with this better implementation of lock by disabling interrupts。

 And the idea here was that interrupt disable and enable isn't the actual lock。

 The actual lock is going to be a variable in memory somewhere， which is either zero or， one。

 And we're going to use the interrupt disable and enable to implement the lock。

 So rather than interrupt disable and enable being the lock， we're going to set up a situation。

 where we use them to implement the lock。 Everybody with me， that's a little different。

 It's like a meta task here。 Okay。 And so this is， for instance， what our acquire looks like。

 And notice what I've done here is I've got a single variable in memory。

 And I'll leave this to you guys to figure out how to generalize this to many possible， locks。

 But for now we have a single integer。 We set it to free， which is zero。

 And then we acquire does this。 It disables interrupts momentarily。

 It does something really quickly and then re-enables them。

 So the only reason this could be okay is if that thing between the disable and the enable， is fast。

 Okay。 That's going to be our goal。 And notice what we do is we say， well。

 if somebody else has the lock because value is， already busy。

 we'll put ourselves on the thread queue and go to sleep。 Okay。

 The thread queue is going to be associated potentially with this lock。

 Otherwise if the value isn't busy， I'll go ahead and make it busy and exit。

 So the only way that acquire works immediately is if the lock is free， the person that did。

 acquire or the thread that did acquire， disables interrupts， grabs the lock， re-enables them。

 That's very fast。 Alternatively， if the lock is taken。

 they quickly put themselves on a thread queue and， go to sleep and somebody else can run。

 Now don't think about that too hard until we get to a couple slides later because that's。

 a little tricky， right？ Like how do you disable interrupts and go to sleep？

 Now interrupts are disabled。 Okay。 So that sounds bad， but we'll make it less bad very quickly。

 So release is easy here， right？ Release says， well， I know I have the lock。

 So what I'm going to do is I'm going to see if anybody's waiting for it。 And if they are。

 I'll take them off of the wait queue and start them running。 Okay。

 And then I'll exit because with release you're typically saying， well， I'm done with the， lock。

 but somebody else have it。 And notice that we don't even bother to set value we could equal to free and then have。

 it set it to busy again because what happened here is this thing is already sleeping and。

 value is already equal to busy。 So when we just let it fall through and after having woken it up that new thread is now awake。

 and value is still busy。 So it's got the lock。 Okay。

 And only if there's nobody waiting do we go ahead and set the lock to free and exit。 Okay。

 So what we've done here is we've really used disable and enable to implement a lock。

 And I'm going to go through this a little more， but are there any questions to start with， here？

 All right。 You're all 100% on board with this implementation。 Okay。 Good。 So first of all。

 why can we only use this in the kernel？ Yes。 That's right。

 So this code as it is can only be used in the kernel。 Now what I could do。

 and we'll talk about that a little bit later， is I could make an， acquire and a release system call。

 So the user code calls acquire as a system call。 Okay。 But for now these aren't system calls。

 This is just something that the kernel could use， but users can't。 Okay。

 And that's purely because we're disabling and re-enabling interrupts。

 But let's look into this a little bit further because it's a little more subtle perhaps than。

 you might have thought。 So why do we need to disable interrupts at all again？ Okay。

 Because the code that's executing either acquire or release has some logic in it。 See。

 that's between the two red pieces here。 And if that logic gets interleaved by somebody else trying to do acquire or release。

 it's， going to get all screwed up。 So in fact， this code here is actually a critical section that we're protecting。

 Okay。 And we're making sure that only one thread is ever either in this side or this side。 Okay。

 Now， a good question in the chat is if we disable interrupts and go to sleep， are we only talking。

 about disabling interrupts for the current thread？ No。 Interrupt disable is a global thing。

 So this looks broken so far， right？ I hope everybody's kind of wondering if I have interrupts disabled and then I go to sleep。

 what happens here？ How do they get re-enabled and why is the machine not fresh？

 So I admit that looks tricky。 I haven't showed you how to make that work yet。 Okay。 So。

 but we do need to disable interrupts to make sure that nobody gets in there in the。

 middle of a choir and release or that's going to be broken。 Now。

 let's look at this acquire just by itself and notice that there's kind of a critical。

 section between disable and enable， but I'm going to call it a meta critical section because。

 it's a critical section in the lock up of a plantation， which is different from when。

 the user says acquire and release。 The thing in between those two are his， you know。

 the user's critical section。 Okay。 And I figure if Facebook can do it。

 I can call this a meta critical section。 Okay。 Why not？ So， unlike the previous solution。

 this meta critical section is very short。 So the previous solution was acquire being disable interrupts。

 you do a bunch of stuff， and then release。 That's potentially very long。 This should be really fast。

 assuming that this thing here about putting yourself to， sleep is fast。 Okay。

 So we're going to need to figure out how to do that。 Okay。

 So the user of the lock can basically hold on to the lock as long as they want because。

 the only consequence of the operating system of a user holding the lock is there's a value。

 in memory that's equal to one for a long period of time。 All right。 So what？ Okay。

 Question in the back。 No， stretch in the back。 So now we still haven't figured out what to do here。

 Okay。 What's going on there？ And let's look at this。 So here we are and suppose the value is busy。

 So we are some thread that's trying to acquire the lock and we've discovered that the lock， is busy。

 And so what we need to do is we need to go away for a while until the lock is free again。

 So that means we need to put ourselves to sleep。 And the question is what happens if we re-enable interrupts here？

 So rather than no enable interrupt in here， we put it right there。 Okay。 What can happen there？

 Yeah。 So good。 Let me give， let me take what you just said there and simplify it a little bit。

 but you're， on the right track， right？ So if we re-enable here and the timer interrupt comes in and the thread that has the lock releases。

 then look what happens。 We come back here and we put ourselves on the。

 the weight queue and go to sleep。 And we never wake up because the thread that had the lock released us or thought it said。

 well， there's nobody to release。 It went to sleep。 Okay。

 So this is a bad place to re-enable interrupts。 So that's not good。 Now we could， what about here？

 Same problem， right？ Version of that。 Okay。 Release puts the thread on the ready queue or because that's a little bit worse actually。

 than the previous one。 So if we've already put ourselves on the weight queue。

 the waking thread says， oh， there's， somebody in the weight queue and they put us on the ready queue and then we go ahead。

 and do whatever to go to sleep。 So it's all screwed up， right？

 So we can't really re-enable interrupts there either。

 So what we really want to do it is we want to go to sleep and then re-enable interrupts。

 That's the only way to make this really work。 Okay。 But that seems challenging。 Right？

 How do you go to sleep and then re-enable interrupts because you know， you're sleeping。

 Now there was some really good discussion I thought or questions on Piazza that get to。

 this point very carefully and I want to talk this through。

 The thread that's acquiring or trying to acquire the lock that puts itself to sleep puts itself。

 to sleep。 What's happening is it tries to acquire， it's running this disable interrupts。

 it's checking， this off。 It's actually putting the TCB on the weight queue and there's still instructions running。

 there。 So you could kind of think that the thread is running along and it put itself to sleep。

 but there's still code running。 So we could now at that point after putting ourselves to sleep。

 go wake somebody else up， because we have the CPU。

 So I know this is a little weird to think about but you could think this thread is putting。

 itself to sleep and then that same CPU is now picking somebody else up to run。

 And that's going to solve our problem for us because here's what happens。 Thread A and B。

 we got to look at these in combination with each other。 Thread A is running along。

 disables interrupts and decides it has to go to sleep。

 So what sleep means is put all your registers in the TCB， put yourself on some weight queue。

 somewhere， that's sleeping。 But after that， well that thread is asleep but the CPU is still running and so what can。

 it do？ Well it can do a context switch to some other thread and that thread went to sleep with。

 interrupts off。 Right？ That's how we just did it over here。

 And so when we context switch to thread B， we're running also in a context where interrupts。

 are off。 So when we go back to running again， we just re-enable them。

 But now that CPU was running A， goes over it's running B and the fact that interrupts。

 were disabled here， sorry I didn't color this red， I should have， we load the TCB and then。

 re-enable interrupts and then keep running。 Until the next time when we context switch and re-enable interrupts。

 So in fact， if you look at just thread A， the difference between disable and enable is over。

 two context switches。 Okay， I'm going to pause to let that sink in for a second because it's a little weird。

 And in fact， if I go back here， notice thread A， disables interrupts， goes to sleep and then。

 later somebody wakes it up and it re-enables interrupts over here and release because it's。

 been woken up at that point。 So the pair of enable and disable is actually going across the choir and release in the case。

 there。 Okay？ Because the guy who is releasing wakes you up。 Okay。 Now， the question of do we。

 in the chat says do we enable interrupts whenever we context。

 switch or how do we know the previous thread called disable interrupts？

 The answer is you have to be careful that you properly code everything that gets around。

 the scheduler so that when you go into the scheduler actually interrupts are off。

 So that when you come out， you know you have to re-enable them。 Okay， that's a pattern。

 It's like an OS rule number one is whenever you go into the scheduler， interrupts are disabled。

 So you know exactly what happens when you take a thread out of there and start running， it。 Okay。

 And notice that this is fast。 This idea of disabling。

 putting yourself to sleep and waking somebody else up。 That's just a short number of instructions。

 So that's not a long running difference between interrupt， disable and interrupt enable。 Okay。

 that's the fast piece。 All right。 Questions。 So this is an agreement between everybody that knows it's touching the scheduler that。

 you have a certain pattern of， you know， always disabling when you go into the scheduler and。

 mess with who's sleeping and who's not。 That's why this works。 Okay。 Should I go on？

 Now a question here is what if thread B doesn't go back to sleep。 So in this particular example。

 by the way， let me just turn on my little pointer here。 In this particular example。

 if thread B is actually woken up right here。 Okay。

 so we thread B isn't going back to sleep at this point， but the question was kind， of， well。

 what if thread B never goes back to sleep？ It has to go back to sleep because we're not going to let thread B run forever。

 That would be an OS bug， right？ Because we have the timer interrupt going off to switch it。 Okay。

 So we will eventually go back this way。 All right。

 Now I have something for you that's going to help。 Let's simulate this。 Okay。

 You can only handle so many simulations in a class， but this one's not too bad。

 So here's the value here that's going to be either zero or one。 Zero is free。 One is busy。

 We're going to keep track of who the owner of the lock is and who's waiting on the lock。

 So this waiters thing here is going to be a queue of waiters。

 The owner is actually not going to be any real thing right now。

 It's going to just be a bookkeeping to help us understand what's going on。

 And it's going to be who's wait， who's owning the lock right now。 So right now nobody owns the lock。

 but we're going to go through this situation with thread。

 A and B such that somebody owns the lock and then somebody else owns the lock。 Okay。

 And notice what we've got here。 Here's thread A。 Here's thread B。 Here's our require and release。

 Okay。 And notice that thread A is running along and it says lock acquire does something lock release。

 Thread B also is going to do lock acquire do something lock release。 Okay。

 And so let's see what happens if the two of them are trying to do this simultaneously。

 Because what we want is only one of them ever gets into their critical section at a， time。

 That's our primary goal here， right？ Because if more than one of them gets into the critical section。

 we've got a problem。 So here we go。 A happens to be grabbing the CPU for a moment。

 It's running along and hits lock acquire。 So acquire does what it disables interrupts。

 That's what that little red dot there means。 And now it's going to run this code。

 But notice that value started out at zero。 So at this moment in time， nobody has the lock。

 So A is going to get the lock， right？ So we're going to take this arm where we set value to one and we become the owner。

 Okay。 And here's where the CPU is running right now。 And notice that that owner is pointing at A。

 But again， we don't have to keep track of， who the actual owner is。 It's like just for us to know。

 Because the reason the owner is known kind of the system is really that thread A will。

 make it pass lock acquire into its critical section。 And so it will be the owner。

 It knows that because it made it there。 Okay。 But now we re-enable interrupts。

 We return from acquire and now A gets to start running in its critical section and it。

 owns the lock。 Okay。 Now notice， I also put on this slide the ready queue。

 So the ready queue is just that queue where we switch back and forth between running and， ready。

 you know， as we multiplex the CPU。 Okay。 So what this current state says is A is running。

 B is ready to run。 And at any point the timer interrupt could go off and let the ready one run and the running。

 one go ready。 And the only reason that wouldn't happen is if we have interrupts disabled。

 And I just want to pause here for a second to make sure everybody understands all the。

 information on this slide because there's a lot of stuff here。 Okay。 Questions？ Are we good？

 Now let's go a little further。 So now A is computing critical section。

 Not a dum dum dum dum dum dum。 Okay。 It's funny to watch what that just did with the text that's coming up on the screen。

 So anyway， so now we come along and at some point the timer goes off。 Why did the timer go off？

 Well， because the timer went off。 It's there to multiplex us。

 So all that's going to happen is we're going to switch from thread A to B purely because。

 the scheduler is there。 Okay。 So there's no magic so far。

 And if you notice at that point going into the scheduler is going to disable interrupts， as well。

 That's why I've got a little red dot there。 So not only did we disable interrupts explicitly in our acquire and release code。

 but when you， enter the kernel because of an interrupt happening。

 That always starts out with interrupts disabled。 When I talked about interrupts before that's what happens and that's why this is red。

 And it's going to go through the trouble in the scheduler of switching A and B。

 So that now we're in this situation。 First we put A on the ready queue。

 Then we start and get B running。 So now A isn't running。

 It's just on the ready queue and B's running。 Okay。 So all that happened there was we just swap。

 That was last lecture。 Okay。 And if you notice that now we're going to come up with lock acquire。

 So what do we want to have happen there when B goes to lock acquire？ What should happen？

 Go to sleep， right？ Why should B go to sleep？ Because A has the lock， right？

 And if we let B run we got a problem。 So let's see why that happens。

 So B is in the lock calls lock acquire。 We first disable interrupts。

 And now notice what is value values one and the reason value is one is because A has already。

 got the lock。 So we're going to do this arm of the code here and we're going to put ourselves on the。

 weight queue and go to sleep。 Which means we're going to go to the ready queue to find somebody else to run because。

 we can't run we're going to sleep。 And therefore who's ready to run？ A， right？

 So what happens is this CPU disables interrupts goes to sleep which is going to call the scheduler。

 which is going to say B is waiting。 Okay， because it went to sleep so it's waiting and voila we're going to go back into A re-enable。

 interrupts and now it's running again。 So the fact that we tried to grab the lock but we can't really kind of force the scheduling。

 operation bringing A back to life。 And now A is running and B is waiting。

 And if you were to look inside you know what's going on in the kernel you'd see that B is。

 on a queue associated with the lock waiting。 So it's not going to get picked up we could have the timer go off all day right now and。

 B will never get woken up again because it's not on the ready queue it's on a weight queue。

 So B is suspended here all right。 Now we're going to run for a little bit longer and we come to lock release。

 So what do we want to happen with lock release？ Speak up or raise your hand go ahead。

 We want to do what with the lock？ So we want to give B the lock right。

 So at minimum we want to take B off of the weight queue and give it the lock。

 So notice what that really means is the following。 We go to release we disable interrupts。

 We say is there anybody on the weight queue yep we're going to put them on the ready queue。 Poof。

 Now B is the owner okay but that's subtle because this owner thing isn't real it's just。

 telling us as we're simulating who the owner is because we re-enable interrupts and come。

 back and run after lock release for A so A release the lock and it keeps running afterwards。

 The only thing that happened in the kernel inside is that B got taken off the weight。

 queue and put on the ready queue okay and if later when the timer goes off we'll swap。

 again and what's that going to do。 It's going to disable interrupts and it's going to pick somebody off the ready queue to run。

 and if it happens to pick B where was B suspended B was suspended right here and so B will just。

 pick up from there they'll be we'll put B running we'll start running from that point。

 we'll re-enable interrupts we'll go back to lock acquire and now we're running in our。

 critical section。 So the only thing that happened was later after after A release B will now get to run。

 and it'll return from lock acquire which means that B's got the lock。

 Why does B have the lock because it returns from lock acquire you have the lock when you。

 do that okay and so this little owner thing doesn't actually have to have B there in order。

 for this all to work okay and then later we'll release the lock and either wake somebody。

 else up or just release the lock。 Alright I'm going to pause on that simulation how we do it please ask a question。

 Yes。 Yes。 So first question there is does every interrupt disable disable the same interrupts is everybody。

 else。 So there's two if you remember back when we talked about interrupts every device has an。

 interrupt that's unique and it's and when one of them's ready there's an ID this interrupt。

 disable as I've discussing it here is sort of the meta interrupt disable that disables。

 them all and re-adables them all。 Now we could get the same activity here as long as we're very careful if we I'm not even。

 going to say that the reason we want to disable all of them is because pretty much anything。

 that came in could in principle be an interrupt that re-enables the runs the scheduler again。

 so we want to make sure nobody's running the scheduler there okay so this is really inter。

 disable them all okay and there's a question here there's no such thing as interrupts while。

 you're in the kernel mode that's false okay that's a question the answer is no that's。

 why we're in kernel mode and we have to disable and re-enable interrupts because they could， happen。

 And if you remember that slide that I had last time I think it was where I showed you。

 that there's a bunch of user threads that have both a user stack and a kernel stack。

 and a bunch of kernel threads that only have a kernel stack those get multiplex all between。

 them so you could have things you could have the kernel is running a kernel thread and。

 there could be an interrupt that goes off and you could switch to a different kernel thread。

 so we only disable interrupts temporarily okay now there's a question over here I'll get。

 up to you in just a second go ahead so the tricky part about doing it here inside the。

 else clause is if you do it before the value equals one you're going to get a mess if somebody。

 else comes in at the wrong spot and if you do it after you're kind of redoing the same。

 thing the enable interrupt does so there isn't really an advantage of putting it inside the， else。

 Well this fall through might not you might not save an instruction depends on how this。

 compiles because this is just falling through that else clause go ahead you had a question。

 so right now either you have to do assist Paul to do this or this is in the kernel either。

 those could work so this could be used between threat between kernel threads in the kernel。

 to lock each other and be careful now there's a question here so here the idea the lock being。

 acquired is just value equal one when we release thread a we pass ownership to it yes so the。

 moment that we take thread B when you do release in thread a and you take B off of the weight。

 Q and put it on the ready Q you have a implicitly given be the lock because the next time it starts。

 running it's going to be in the critical section good good question and why do we need。

 to disable all interrupts rather than leaving very high priority interrupts so that's a good。

 question we kind of answered it really high priority interrupts like you know nuclear meltdown。

 you could leave those still in a people you just got to make sure that whatever interrupts。

 you leave a naval won't trigger a contact switch because the whole point of disabling。

 interrupts is no contact switch here okay all right and be becomes the owner and release。

 because the ready Q is empty be becomes owner and release here after a release is purely。

 because lock acquire will return the next time we let the thing run because we put it on the。

 ready Q rather than the weight you go ahead。 Okay good so you're talking about kind of this point where a did a lot or be did a lock。

 acquire goes into acquire and it goes to sleep so what happens there is we put ourselves。

 on the weight Q and then what it means to go to sleep is we have to let somebody else。

 run so we go into the scheduler at that point and the scheduler is the thing that will pick。

 a new thread and we'll go through a path that does enable again that's right the scheduler。

 always starts with interrupts disabled and you're re-enable coming out and if you look。

 here this is a little confusing but we go from this point and we hit the green for re-enabling。

 before we start running。 So the question here is interesting does something about sleeping change instruction。

 pointers somewhere so it knows to re-attempt the acquire function every time it wakes up。

 no this is more subtle than that again when we went to sleep our instruction pointer was。

 right here in the middle of a choir when we went to sleep and so now when we get re-enabled。

 our instruction pointer when we start running again it's going to be right there and when。

 we get to that point where we left off and so when we schedule again we'll start running。

 from that point in a choir there's nothing else that's going to hold us out so we're going。

 to exit from a choir and now we've got the lock because we exited from a choir。

 Okay so it's a little more subtle than having to have a loop here yeah question in the back。

 You mean like saying value equals zero and then doing it nothing so good question so。

 what prevents thread B from being malicious and setting value equal to zero。

 So the answer is you could do that but then you've broken kind of like a contract that。

 everybody in the kernel has in that case right and the contract is you go through lock acquire。

 and release before you touch some shared data okay so this is an important point let me say。

 this in another way so once we get to where we're at user mode when we have user threads。

 that are cooperating together and they're acquiring and releasing locks they are implicitly part。

 of the same application and they're going to do their best to not screw it up and so basically。

 you could think of this as if thread B did that it's a bug not a security problem。

 And that's going to be I realize that sounds silly but it's an important point that's going。

 to be important as we get further on yeah go ahead。

 So when B goes to sleep right here so B is going to sleep you're asking who enables it。

 So what happens is we go into the scheduler and we're going to pick A to run again and。

 so in the scheduler releasing A to run is going to is going to re-enable interrupt at。

 that point so you could say that thread A releases the interrupt I guess。

 Okay but hold on you could say that but I want you guys to get very good at going back。

 and forth between the thread view and the CPU view because there's only one CPU here。

 that's why I've got all these little arrows going back and forth right the CPU is running。

 here and it goes over to B and it comes back to A and it goes back。

 So the two views that you've got to pick up sorry about that out there Nittland。

 So the two views that you want to get really good at understanding is that when one view。

 is what's the CPU doing and the other is what are the threads doing and if you can get that。

 in your mind as to how to have those simultaneously there in your mind you're going to be in good。

 shape and that's kind of what this simulation is about okay yeah go ahead。

 Yes there is a weight queue per lock typically。 What about what？

 So the ready queue is for all threads because when you put something on the ready queue it。

 just means it can run it just means I'm ready to be swapped and get some CPU and the reason。

 we put this over on the weight queue is because B can't run because it's trying to get a lock。

 that's already taken and so we have to put it to sleep then a weight queue。 Good yes。 [inaudible]。

 No because when we acquired we disabled and re-enabled if you go through you'll see that。

 there's actually just one re-enable for every disabled。

 Well except that this acquire release didn't use the scheduler because we're still running。

 thread A when we're done。 So here this loop there's no scheduler involved。

 Here it's not going back to thread A's inquire what's doing here is it's going back to thread。

 A running over here in the critical section。 So here thread A never goes to sleep thread A goes around to this else clause。

 So thread A never hits the scheduler in this original acquisition。

 The only time the scheduler is involved is when the timer goes off here and then we as。

 a scheduler we let B run。 So I'm going to move on if that's okay with you guys because this is one of these things。

 where I think staring at a little while to think about it then you could ask me a question。

 later if you like。 But everything's paired up but I think that I think this simulation is useful right because。

 it kind of shows you some of the subtle piece I hope。 Okay， we good？ So good。 So let's go past this。

 So that's fine and dandy except that unfortunately right now we're not able to run this at user。

 mode the way we've written that there。 We'd have to actually have a system call。 Okay。

 and so that seems unfortunate。 And so this also doesn't work on multiprocessors because we'd have to disable interrupts across。

 all the cores and that's also expensive。 So let's see if we can come up with something else and the alternative here is atomic instruction。

 sequences。 Okay， and these are special instructions that are different from load or store and interrupt。

 disabled and enable that do something atomically to a value。 So the hardware has to be different。

 it has to include these instructions in order for， what we're talking about to exist。

 And fortunately all modern processors have that hardware of some form。 Okay。

 and unlike disabling interrupts we can use this on multi core。 So there's a lot of examples。

 The most common one here is what's called test and set。

 And test and set you give it an address and what it does is it reads the value from the。

 address and memory and stores a one and tells you what was there before。

 So atomically with no chance of anybody getting in there it both reads the old value stores， a one。

 Okay， and tells you what it got。 All right。 Now what we're going to do with that of course is we're going to say that zero is free and。

 one is busy。 And if you do a test and set and you happen to be the lucky one that grabbed a zero and。

 started one there you'll be the one that gets the lock and everybody else that tries to。

 do it there'll be a one there you grab the one store the one you'll say I got a one I。

 got a I got to go in a loop。 Okay， so this is the kind of instructions we're going to be interested in。

 Swap is a different type of atomic instruction and what it says is you give it a register。

 and an address and it says grab what's at the address and take what's in the register stored。

 back to the address。 Swap the address and the register and I do that atomically in a way nobody can get in。

 And compare and swap is a more complicated one you get an address and two registers and。

 what that says is if what's in the address matches the first register's value store the。

 second register value there and return success。 Otherwise if the address and if the thing in the address and the register one don't match。

 return failure。 Okay， and then last there's a fun one called load link store conditional which was in the。

 original R 4000 and alpha from MIPS well the R 4000 from MIPS in the alpha from digital。

 equipment corporation and the idea here is that you can construct any arbitrary other。

 instructions with Lord Link stored load linked stored conditional this way you give it an。

 address you load the thing that's in the address you do whatever you want so this move I one。

 to R two and store R two that's a arbitrary code in there and then you basically say that。

 if this store failed then you loop back and what this will do is it'll let you grab a。

 value store a value back but if anybody else is modified the value then you have to loop。

 back and do it again。 So it's a way it's like a risk version of these other ones that allow you to make a more complicated。

 instruction sequence。 So I'm going to hold off on explaining that anymore but let's let's look at other things。

 here let's talk about compare and swap。 So this one is an x86 instruction it was also on the 68000 and again notice what happens。

 here we basically say that if Reg one matches what was in the address of memory so we basically。

 load the value of the address check it with Reg one if that matches then we store Reg two。

 in the address and we return success otherwise we return failure。

 And let me show you how to build a lock free linked list out of this。

 Okay so here's my add to Q and what I do is I give it a pointer to an object okay and that。

 object has to have a link in it and we're going to just say add this add this add this。

 and we can do this simultaneously from a thousand different threads and cores and it'll work。

 Okay and notice some subtleties here I load a value at the root okay that's a single link。

 list I load the value at the root I store the value of of my new of the root into the object。

 so I'm linking it in and then if compare and swap fails I keep retrying it so this has。

 got a retry if somebody else is competing with you to get on the list。

 Let me show you this here's a here's a single link list this is 61 B everybody remember that。

 okay and notice we have a root and the root points at the next which points at the next。

 and so on and what we want to do is add an item to this list and we want to have a lot。

 of threads be able to do this simultaneously without a lock。

 Okay so look what we do here we load the root pointer that's what this thing is into register。

 one we store register one into the new object。 Okay here's the new object we store the root in here and then we say compare what's currently。

 in the root with what we thought it was in R1 and if nobody's messed it up so nobody。

 else has stored something in the root and root is still equal to R1 then we win because。

 we put the root into here we pointed the root at this object and we're good。

 If it fails we go and keep doing it over and over again until we get to link and then we， exit。

 Okay so there's an example of what is often called a lock free style of synchronizing where。

 we don't have to actually put a lock around the root。

 Okay and this will be a lot faster than if we did the obvious thing which by now at this。

 part in the lecture your obvious thing would be acquire lock change the list release lock。

 right that would hopefully that's something that you're now almost ready to do but if。

 you do that now you're you've got a lot of people going to sleep on the lock whereas。

 with this in that rare instance where in you know in a couple of instructions you happen。

 to get there with somebody else you'll loop but that's going to happen very rarely。

 Okay and this is a this is kind of like a busy wait is the question in the in the chat。

 but in fact this resolves extremely quickly。 So you could kind of make an argument that this isn't much of a busy wait the only way。

 it would spin for a long period of time is if you have thousands of threads that are。

 all trying to do this simultaneously。 And it isn't going to happen if you only have one CPU right only one thread is going to get。

 to run at once so all right。 So next Thursday that's a week from today mid term one。

 Okay now we will be putting out on Piazza information about which rooms you go to so。

 there's like four rooms so watch for that that's coming out this soon。

 You get one sheet of handwritten notes both sides。

 Okay do not take microfiche of your textbook and glue it in and bring a mic bring a magnifying。

 glass so that's not that violates the spirit of this note rule here okay so you can have。

 one sheet and you can write both sides of it anything you want。

 Okay there won't be any calculators there won't be any devices just your sheet and a。

 pencil or pen or something okay。 Can bring liquid paper if you feel like using a pen I guess。

 The project one design documents do okay I say next Friday that's really tomorrow so。

 keep in mind that there's going to be design reviews coming up and so that's going to be。

 very soon and so watch for that too it'll probably be either over the weekend or early。

 next week okay because we don't want to compete with the mid term。

 There's also going to be a design review or excuse me there's also going to be a review。

 for the mid term but it hasn't been scheduled yet we're trying to figure that out so watch。

 for that so I'm sorry there's a lot of unknown things here yet。

 I talked about the design review this is like a high level discussion of your design if。

 you have to put code in there try to use you know pseudocode don't put a whole pile of。

 C in there because you're trying to explain your approach to your TA think of this like。

 I don't know they're your manager in a company and you're designing this okay and you have。

 to make sure they understand what you're trying to do。

 Okay so the design review is coming up let's see and that's going to be up to your TA。

 Let's see and then of course do your own work on the projects so I guess are there any other。

 questions on this？ The question that's in the chat is yes the design review is coming up very soon because。

 typically what happens is you submit a design doc and the design review is shortly thereafter。

 I guess we could make that a little clearer on the schedule but it's certainly true。

 All right okay so there's a question here in the chat so I'll move on unless people have。

 a question。 So in fact I'm going to say let's see there's one thing in the chat and then I'm going to。

 give you guys a little bit of a break and then we'll come back but what's the difference。

 between atomic read modify write instructions and a read write lock on a file so the read。

 write lock on a file is software and it's more complicated the atomic instructions are。

 a single instruction okay and you can build all sorts of interesting locks on top of that。

 and that's what we're going to that's our next topic here okay。

 All right let's take a little bit of a break and then come back so let's let's keep it semi。

 short let's say three minutes or so and feel free to stand up and stretch okay。



![](img/22a440ab5259f377d19dc5be83e46a76_3.png)

 Okay。

![](img/22a440ab5259f377d19dc5be83e46a76_5.png)

![](img/22a440ab5259f377d19dc5be83e46a76_6.png)

![](img/22a440ab5259f377d19dc5be83e46a76_7.png)

 So let's keep going here。 Now what we can do with test and set is something pretty simple that looks like this。

 I already said this but you can have your lock as an integer and that lock you started。

 out at zero and then the way a choir works is you go in a loop that says while test and。

 set and you give it the lock address it'll spin okay and why does that work well it works。

 because if multiple threads are trying to acquire they'll all try to do test and set。

 one of them will be the one that gets the zero back and stores a one and all the other。

 ones will store a one and this while loop if what comes back is a one then you know that。

 you didn't get the lock and so you just keep running test and set over and over again and。

 what happens is when you release you set that variable to zero and all of a sudden one of。

 the threads it's busy spinning is lucky enough to run the one test and set instruction that。

 pulls the zero out and stores a one okay and then it'll exit from a choir and get to go。

 forward all right。 So you know if the lock is free test and set read zero sets a lock to one so now it's busy。

 when you set it to zero somebody else gets to go okay。

 The problem of course is this is a serious busy wait scenario because when you're waiting。

 for the lock you're spinning okay but before we fix that I just want to pause here and。

 ask because this makes sense to everybody。 Okay we're good now the way we can you know what's the problem so the positives of this。

 is that this is in memory and we're not disabling interrupts or enabling them so the machine can。

 just keep going and we don't have to be running this in the kernel okay so that's good works。

 on a multi processor or multi core why because that memory is shared across all the cores。

 and so they all can do test and set on the same address and it just works okay so that。

 seems like a positive。 The negative here is this extremely inefficient and when you're waiting you're spinning and。

 wasting time and in fact if you think about it when you're spinning you're doing nothing。

 useful and you will actually suppose that you only have one CPU and two threads the thread。

 that's waiting will actually spin until the timer goes off and then thread A gets to go。

 further and eventually release so you're it's worse than wasting time you're wasting a lot。

 of time you're kind of waiting for a hundred milliseconds until the timer goes off and you。

 let thread go A go again to release the lock okay so this is really pretty bad okay because。

 the one that's spinning and wasting cycles isn't the one that has to release the lock we're。

 actually preventing it from doing the work required to release the lock okay so that's。

 why busy waiting this is this poor guy here who's busy waiting is rough and he's blue right。

 this is just not good okay and this is a type of priority inversion potentially because。

 if the busy waiting thread is higher priority than the thread holding the lock you might。

 not get any progress okay because you have to go because you have the busy waiting one。

 is executing cycles and when we get into priority scheduling we're not there yet the one that。

 has to release the lock can't even run because the higher priority one is the one that's spinning。

 okay so this is this is just not good and this was there the original Martian rover had。

 a very interesting priority inversion problem we'll talk a little bit more about that later。

 when we start getting into scheduling but that actually was a problem that caused this rover。

 which is quite a way to wait from the earth keep rebooting over and over again because。

 of a priority inversion problem sort of like this so and when we get into higher level。

 primitives and just a little bit like semaphores or monitors the waiting thread may wait an。

 arbitrarily long time and so we're gonna be wasting a lot of cycles so let's see if we。

 can fix this and it turns out that to fix it we can do something which is kind of colloquially。

 called test and test inset and it looks like this it's almost identical but what it says。

 is to acquire I first say while the lock is one spin okay and then try to grab it now。

 this is actually still busy waiting so that's not quite good yet but it does have a very。

 nice property to it because if you have a bunch of cores and the number of threads you have。

 is less than the core so you're not really preventing a thread from running but a bunch。

 of them are spinning with the previous solution every loop writes the variable over and over。

 again right one right one right over and over again and it also reads it and so if you've。

 got a cache go here multiprocessor the values are bouncing back and forth and so not only。

 are you wasting cycles but you're burning memory bandwidth so this is just bad okay and so this。

 is still a busy way to solution but this test and test inset doesn't do what I just said。

 because what happens is as long as the lock is busy the cores that aren't that are spinning。

 waiting read the one into their cash and now they're only running they're only spinning。

 in their own cash they're not bothering the rest of the processors so when you know when。

 we start talking more about multiprocessors you're probably never going to want to just。

 do a raw test inset you're going to want to do a test in test inset because it's better。

 for the memory use okay now but this is still busy waiting so the question is can we build。

 test inset locks without busy waiting and the idea here is we're going to basically do。

 the same pattern we did with interrupt disable okay so we have our lock which is going to。

 be freer busy but now we're going to have what we call a guard so this is like a meta。

 lock okay remember we got meta I don't know what were they thinking when they called Facebook。

 meta it just seems kind of silly for me but anyway that's by the way that's an opinion。

 doesn't reflect reality I don't know so what we're going to do here is this guard is just。

 like interrupt disable it enable we're going to make sure we only do it short period of。

 time and so notice what we do is we grab the lock which is the guard and now we look at。

 the actual lock that we care about so the meta thing is red we look at the actual lock。

 if the lock we want is busy we put ourselves to sleep we put the thread in the way you put。

 ourselves to sleep and atomically set the guard equal to zero okay that's similar to。

 atomically re-enabling interrupts when we put ourselves to sleep otherwise we set the lock。

 to busy and we exit with guard equals zero and notice that this just like with interrupt。

 disable and enable which we're only you only had the interrupts disabled for a brief period。

 of time for the same argument here we only have that guard variable equal to one for a。

 brief period of time so the likelihood of a bunch of threads running into that guard。

 and wasting a lot of cycles is very low okay so this is kind of a similar idea to the interrupt。

 disable and enable alright now somehow whatever we do for sleep has to reset the guard variable。

 okay and what's tricky about this of course is if we're running this thing at user level。

 which was our goal go to sleep what do we have to do to go to sleep we're running at。

 user level what do we have to do to go to sleep yeah yeah we had to go into the kernel。

 to go to sleep and maybe that's not a big deal here because we only go into the kernel。

 if we're actually have to go to sleep anyway here this kind of says we have to go into the。

 kernel to even see if there's somebody to wake up so this particular solution kind of forces。

 you to take a system call into the kernel just to see if there's somebody to wake up。

 and that might not be desirable because we would really like to have a situation where。

 if there were no contention on the lock which means there weren't more than one thread trying。

 to get the lock that we could acquire and release extremely quickly without ever entering。

 the kernel that would be great okay but this this particular solution doesn't have that。

 property so anybody have any idea what we could do yeah okay question。

 the reason busy waiting on the guard is better than busy waiting on the full acquire release。

 is that the guard is only equal to one for a very short period of time so the probability。

 of running into somebody and busy waiting is extremely low whereas if you acquire and。

 release and you do a long computation between acquire and release the person with the lock。

 might have the lock for a long time and the probability of different threads colliding。

 with that is extremely high so you're going to get a much higher chance of spinning for。

 a very long time yeah， you mean here so remember that we separated the lock from the guard。

 so which part are you worried about being not safe oh I see well that's a really good。

 okay that's a that's a really good question so you're worried about if the CPU reorders。

 the loads and stores then what right yeah so that's an extremely sophisticated question。

 and I'm going to give you the answer is the following you have to make sure that if there's。

 a load store reordering that could happen that you have to put the right guards the right。

 fence instructions in there to prevent that from happening so processors without a border。

 execution but a weaker memory model then release consistency you have the expenses that you。

 could do to prevent those two from bypassing each other well this isn't this is like code。

 this is an instruction so what this compiles down to we haven't really shown you exactly。

 here but feel free to ask me about that that's that could take a much longer time to question。

 but that's a great question all right so if you look remember acquiring this is what。

 we just did with disabling of interrupts and re-enabling this was bad so we did this meta。

 idea where we just disable interrupts and re-enable them quickly and that kind of made things。

 faster notice that this pattern we just did here is very similar right rather than spinning。

 for a long time to do a choir release instead we're using the spinning part for a meta critical。

 section and then we just use the variable as our lock so those are very parallel to each。

 other and the way to think about them okay and the advantage of both of the versions on。

 the right side is really that the lock can have just an address to the lock so you could。

 have a whole array of locks you could have many locks okay now let me briefly I want to。

 tell you briefly about few texts and then I want to tell you about semaphores here but。

 few texts is a special kind of hidden system call in Linux that takes an address of a variable。

 like value that we just talked about an operation like wait or wake and a current value which。

 we're going to look for and the idea is in a time out where if something takes too long。

 we can time out and it's an interface to the kernel sleep function so remember what I said。

 earlier well what does it mean to go to sleep you actually have to go in the kernel to go。

 to sleep so the way Linux gives that to you is with few texts okay but typically this。

 is buried inside the p thread code okay so you don't actually program this but explicitly。

 usually but you can and just as an example we could do a test and set in a few text so。

 this would be while we have we try to grab the lock we get back a one therefore we have。

 to go to sleep we could call few text to go to sleep and notice what we're saying is the。

 lock equal to one atomically with few text wait we'll go into the kernel and go to sleep。

 okay and release is simply to release it you set the lock to zero and then you ask the。

 kernel to wake up one person that might be there okay and so few text becomes the way。

 to get into the kernel to go to sleep now the downside of this the way I did this is we always。

 go into the kernel to see if there's somebody to wake up okay so the lock has no overhead。

 because if something if there is nobody locking you grab it right away and exit but every release。

 has to go into the kernel to see if there's somebody sleeping so this is not quite what。

 we want to do a really good lock all right so instead we could do something like this。

 where we might say well while test and set fails set this maybe to true go to sleep and。

 then set maybe to true again and then keep retrying until you get out of this while loop。

 having the lock and the way we know for sure we got the lock is because we swapped in a。

 one and we got back a zero we got the lock okay so all the stuff we're doing with few。

 text is trying to deal with the go to sleep part of the lock okay and look what happens。

 over here to release we say set the lock to zero so that just released it and then if。

 there's the chance that somebody's sleeping in the kernel then try to wake them up and。

 the reason this is different from the previous is if there's only one thread then there will。

 never be anybody setting maybe to true and when the thread releases they'll never have。

 to go into the kernel so this is messy but it's better than the previous one if you only。

 have one thread that keeps requiring and releasing and the goal of the lock is to just make sure。

 in the rare instance with two of them actually run into the same lock then you can handle it。

 well okay now I'm not going to show you this you can look at this on the slides whoops but。



![](img/22a440ab5259f377d19dc5be83e46a76_9.png)

 there's a much better implementation where there's actually three states of the lock。

 unlocked locked and contested and in that instance if there's no contention things will。

 go unlocked and locked and the only time you go into the kernel is when there might be。

 a contest with multiple people with the lock okay and this is a pretty cool version of this。

 you should stare at this on your own time or after the class okay there's a smile here。

 okay now this mask thing is kind of weird still alright so let's finish up today given。



![](img/22a440ab5259f377d19dc5be83e46a76_11.png)

 the last couple of lectures what's the right abstraction for synchronizing threads so we've。

 kind of pushed locks as far as we could go be nice to have something higher level so good。

 primitives and practices or design patterns are going to be really important to make things。

 work properly Linux Unix all the Ixas were pretty stable now but boy in the early days。

 you know until the mid 80s or so they would crash on a regular basis or they'd lock up。

 on a regular basis and that was because of bad synchronization okay and good synchronization。

 practices took a while for people to figure out and so really if you don't synchronize。

 properly and you got shared data it's highly likely that something bad is going to happen。

 okay and in the case of locks that's something bad means multiple things in the same critical。

 section at the same time okay now so synchronization in general the word means coordinating multiple。

 concurrent activities in a way that makes sure the code is running correctly and so we're。

 going to talk for the rest of today and next time we're going to talk a lot about ways of。

 producing good sharing of data and let's start here with a bounded buffer okay so the。

 idea of a bounded buffer is this producer consumer idea where the producer produces a。

 bunch of stuff and puts it in the buffer and if the buffer is full the producers will go。

 to sleep and the consumers will try to pull stuff out of the buffer and if there's nothing。

 in the buffer the consumers will go to sleep okay and so this synchronization pattern is。

 going to be trying to make this work cleanly and you don't want the producer and the consumer。

 to have to work and lock step so you put a buffer in between them and now the trick is。

 the buffer is going to absorb some of the timing and we're going to figure out what to。

 do to make the synchronization work cleanly and so the GCC compiler I mentioned this before。

 you got kind of C-preprocessor goes into two different phases the compiler goes into the。

 December assembler and the loader that's a good example of kind of producer consumer。

 because the buffer is exactly this pipe thing here and by the way homework two which I think。

 is handed out tomorrow does the shell and so you're going to get to figure out how to implement。

 these guys okay so another example I like is the Coke machine where the Coke machine。

 has some slots for Coke the guy comes by to fill it up if there's no space well in this。

 example he falls asleep until somebody takes a Coke then he wakes up puts Coke in there。

 okay and the case of the students that go and try to buy Coke if it's empty he falls。

 sleep until somebody puts it in there then they wake you up and you get a Coke okay so。

 that's going to be our Coke machine okay going after the caffeine habits that we know you。

 all have and so do I right but there's lots of things this is good for you know servers。

 and routers okay so a circular buffer this is a 61 B thing typically has a you know a。



![](img/22a440ab5259f377d19dc5be83e46a76_13.png)

 read pointer and a write pointer and a bunch of entries and the trick with this is there's。

 manipulation involved in making sure to see whether the buffer is full or empty based。

 on the queue pointers and then adding something and moving the pointers and you got to do that。

 in a way that doesn't get messed up if multiple threads are going to get mess with it okay。

 so in order to build a circular queue used by many threads we're going to have to put。

 synchronization around this okay and here's an example of what we really want here for。

 instance what if we say for a producer you acquire a lock on the queue and while the buffer is。

 full you spin and as soon as the buffer has a slot then you add the item and you release。

 the lock and exit and this the consumer acquires the lock waits until the buffer is fully empty。

 or waits as long as the buffer is still empty and as soon as there's something there they。

 deque the item release the lock and return the item what's wrong with this so we put a lock。

 in there to make sure that the queue manipulation in red doesn't get screwed up by multiple threads。

 what's wrong with this what was that yeah this is a deadlock why is that because producer grabs。

 the lock spins waiting for the buffer to be full but the the one that will do anything about that。

 has to acquire the lock first and they'll go to sleep so they can't deque any items so the producer。

 can wake up and go forward so this is a permanent lock up situation okay this is not very good now。

 never comes out of the loop so here believe it or not we could do this messy but we acquire the。

 lock we say is the buffer full okay release the lock require the lock is the buffer full okay release。

 the lock require lock the buffer full okay when we eventually encounter a not buffer full then we。

 can in queue a new item release the lock and go forward this is uh not great but this will。

 actually work okay but this is busy waiting okay right because that acquired release goes over and。

 over again so really the question is what is the right abstraction and good primitives are going to。

 be very important and so next time let's do something other than locks and really synchronization is a。

 way of coordinating multiple concurrent activities as I said and we're going to talk about semaphores。

 I have a couple of minutes I want to give you the semaphore pattern here okay semaphores are like a。

 kind of generalized lock and Dykstra first defined them in the 60s and the main synchronization primitive。

 that was used in original Unix was a semaphore and a semaphore is like a special type of integer。

 and it supports the following operations you set a value only when you initialize。

 and then there's only two operations either down or p which uh waits for the semaphore to become。

 bigger than one and then decrements bigger than zero I mean then decrements it by one and then upper。

 v which increments the semaphore by one and wakes up somebody who might be sleeping so you sleep if。

 you try to decrement below zero and you get woken up as soon as somebody increments it above zero。

 so this is a little more powerful than a lock okay and they're like integers except there's no。

 negative values the only thing you can do with them is p and v operations or up and down。

 the down and up I mean the operations are atomic so two p's together can never get you below zero。

 the thread going to sleep and p won't miss a wake up from v and uh so here it's a real。

 railway analogy I'm gonna say and then we'll finish up you start the value equal to two here's。

 a semaphore that's what this little picture is the train comes by and tries to execute a p operation。

 which decrements the value by one and the train gets to go through the semaphore the second one comes。

 along decrements and the train gets through the third one that comes along tries to decrement but。

 that would take it below zero so that p operation puts it to sleep okay and later if one of these。

 exits and increments the value to one the train wakes up and goes through okay so I want to leave。

 you with this idea and we'll follow this more later okay so in conclusion we talked a lot about。

 atomic operations hardware atomicity primitives like test and set compare and swap etc we showed。

 you lots of ways to build locks but we don't want to spin wait very long okay and what we did this。

 time is we started talking about semaphores and uh monitors will be our other topic so what I'm。

 gonna do by the way is I'm gonna put up a video with more information about semaphores and。

 monitors for you guys you could take a look at it and then we'll pick this up next time but I want。

 to make sure that you have a chance of reading more about this all right have a great weekend。

 watch for information about design reviews and about mid-term review， Thank you。



![](img/22a440ab5259f377d19dc5be83e46a76_15.png)

 ( thanks for tuning in )。