# CMU《并行计算机架构与编程｜CMU 15-418 Parallel Computer Architecture and Programming sp18》 - P18：Lecture 18 - 2-23-18 - Carnegie Mellon University.zh_en - GPT中英字幕课程资源 - BV18b421J7cA

Right， how we doing？对。Favorite things on earth。Let mean that。So open MP is behind。

Is to managing threats and to managing parallelism。

And the thing that I love about it is it's actually built into， actually built into。

 you know all of GCC。 And so you can just use it。 It's built in。

 and it's completely supported via pragmas。😊，啊。And so it makes it very， very， very natural。

So you can， I mean， you can just see， I mean， we'll talk our way through this example in a minute。

 But you can just see this example right here。 We see the pound pragma， O MPP。You，4。

And that's basically all it takes to paralyze the for loop。Of course。

 whether or not you want a for loop paraze as a different question。

 but you order to paralyze the for loop， that's sort of all it takes。

That annotation of the compiler saying it's okay to do that。Okay。

So OMP basically has this fork join model where it launches a whole bunch of of worker threads。

 The worker threads charge off and do things independently。

 And then you reach a synchronization point， a barrier point。And then you reach that point。

 you regroup， you launch a bunch of threads。Do whatever you're doing in parallel。

 reach another barrier and regroup。嗯。Nively， this would mean， you know。

 generating about a huge number of threads and then sort of collecting them all and generating a huge number of threads and collecting them all。

 But the compiler is actually fairly good about optimizing that process so that so that it does it smartly when it can。

To minimize the number of threads created。嗯。If you look at sort of this picture of parallelism。

 you see that we have the areas of serial execution right between these areas of parallel execution。

 And notice that one of these threads coming straight down is it blue。

Take a magical guess as to what's special about the thread that's drawn here in blue。😊。

It's in sometimes a mess。 right It's the original thread。 That thread never goes away。

 You start out your program。 There is sort of the main thread， if you will。

 And that main thread is there with you the whole time。嗯。All right。

So if we take a look at this and we see open MP parallel。Okay， count pragma OMP parallel。

Take a while guess what that is。Actually， let me check on one thing。 Okay， yeah， we're good。

Somehow this thing edit bullet points to this slide。 And I didn't notice。 I'm sorry。

Just ignorerant at bullet points， supposed to code。Take a wild guess and？OMP parallel might be。

Might be trying to communicate。Right' that's that's you requesting the compiler use open MP for parallelism from that point forward。

 right。And so that's what that is。 We that's supposed to be。 That's a parallel block， right。

 And then open open， pragma， open MP4。Iteration  zero iteration one iteration two。

 iteration 3 iteration4 is asked the compiler instead。Right to parallelize that。嗯。All right。So。

The translator here is going to automatically generate the appropriate local loop bounds and so on。

 In other words， it's going to partition it for you。😡，We can talk about it。

 there are two ways it' will happen we'll talk about it。

 dynamic or static dynamic or static partition。It's going to insert any of the needed barriers。

 but we need to tell it what should be private and what should be shared。嗯。

It handles the irregular problems in the words， what happens if there's a few left over at the end？😡。

All right and like I said， decomposition to be static or dynamic and we'll talk but ahead of hint this to that so here we see a loop for you know。

 you know just a simple for loop right？Initialization， the test， and then notice the by2， okay。

This is a step。 We're stepping by two。 In other words， instead of incrementing one each time。

 we're incrementing two each time。In here， I have a little bit of super would just to us from you know。

 writing writing swap there。嗯。And then you can see us playing with a done variable and so on。

 So we're basically gonna walk through this。 But you can see that there are some elements of what open MP can do here。

We're paralyzing the loop。😡，Some variables are going to be shared like keys。

 Some variables are going to be private， like I。 and then it has this ability to reduce or to collect results from the iterations。

All right。嗯。So notice that there are a couple of different ways I can ask Open to parallel a loop。

 I can turn on Open MP， and then I can ask it to do a for loop， or I can do open MP parallel for。

 It's the same thing， right， The compiler is getting the same message open MP translator is getting the same message right that what we want there is is a parallel for loop。

Hello。The parallel region are shared by all threats。All right that should sort of make sense。

 right if I declare a bunch of variables and then I parallelze right。

 those variables were declared first。😡，We wouldn't expect that magically we'd rubber stampamp a whole bunch of new versions。

😡，And if we would， that would open a bunch of questions like what value should they have and so on？😡。

So variables declare before we paralyzze by default right， are going to be shared by offerings。

Variables declared inside the region are private。Okay。

 let's think about that for a minute I have a region on top， any variables I declare there。

 those are shared by everybody because they were declared before we paralyze Now once I turn parallelization on right。

 that means that I'm going to have multiple threads， multiple instances。😡，And。

There's an obvious choice between having variables that are shared among those instances。😡。

And having variables that are private among those instances。

Having variables that are private among those instances is and should be the most common option。

 right， because if variables are shared， that's a concur control issue， right？😡，In some way。

 shape or form， we're going to have to manage that， which is in effect going to reduce perils。So。

once we say that this region is going to be paralyzed。

 the default assumption is that we want copies of those variables， they're shared variables。

 each thread then having a tongue。Having said that。

 we can still qualify variables as being global if that's what we want。

So you can see that here we have shared and a list of shared variables and private a list of private variables。

When coding for Open and B， I declare things as private even when I don't need to。😡。

And share even when I don't need to。😡，There is the set of assumptions that if they're declared inside the private region they're going to be private。

 if they're declared before， they're going to be shared。Technically speaking。

 you could just qualify them if you need to。😡，But why is it when I write code that I qualify them always。

 100% of the time？😡，If you like。Can change the code。Bberry。And it's not qualified。Forget that。

Privates were shared。Yeah， I mean， so one example of a problem right is that somebody's doing maintenance coding and move something around because they think they're doing the cleanup right and they don't realize the consequence of what's going on with open entity that gives a problem。

 what else？Yeah。S that you run。Thank you very。Yeah， I mean， like I want like right here。

 this is a trying to parallel stuff， I want to know what my assumptions are。

 I can either try to trace through my code to see where something's declared and hopefully get it right。

😡，Or it could be labeled explicitly for me。😡，There is a correct answer to that right。

 the correct answer is label formating。😡，Because all sorts of things go wrong， we don't do that。

 right a very common thing that goes wrong is people make assumptions。😡。

That variable looks private to them。😡，Right， another thing that goes wrong is people go hunting around and the file。

 you know， the code in that file and the more code in that file there should be， right。

 turns out to be a big file， And they look inside the wrong function， the wrong place。

 and they end up finding the wrong variable。 And they think， oh， it's the cleared way up here。

 you know， it must be shared。😡，And that turns out to be a local variable in some other function。

Right。So realistically speaking， right， I don't really worry about these assumptions。

 I know them if I run into them， but I'm always going to declare it yeah。😡。

We'll complain if you initialize。Inside the for loop， by C99s。Okay。

 we're actually going to talk about that， that turns out to be an interesting question。

 you mean initialize or declare。😡，So the rules for variable declaration。😡，嗯。

So it turns out that's going to be an interesting question。 So as it turns out。

 if what we generally want to do is declare variables outside loops and initialize them inside loops。

 because declaring them outside loops will make them shared and declaring them inside will enable them to be initialized as in each of those in parallel。

😡，So it turns out there's a little more there than just what the syntax is。

 but it doesn't actually change nothing about OpenM changes the syntax of C。😡，So。

 you know your rules for variable declaration are going syntactically you're going to stay the same because it's in no way altering the C language。

 so if the C compiler have declared something in error or giving you a semantic warning about a declaration。

 it's still going to do that。😡，Yeah。Underneath。In ISBC。

So the question is does this get transformed into vector code， so I guess？😡。

If you're doing this on on GCC or G++ on the UniX to Andrew system。

 it's going to get optimized into vector code。😡，Now， that's not a guarantee， right， In fact。

 there's no guarantee that when you put these pragmas in here。

 that anything's going to happen at all， right？😡，So what back end optimization a particular compiler may be able to do is a。

Is an implementation question。Does that make sense？So technically speaking， you can take your code。

 compile it with all these pound pragmas， compile it in a regular compile that doesn't know what they're doing。

 and you're going to have C code。😡，That's not going to be special。

 It's going to iterate through your loops。Right， and at some level， there's nothing wrong with that。

 It's just not helping you out very much。 right， A smarter compiler is going to spawn the appropriate threads。

 blah， blah， blah， bla， blah， and the smartest compiler or no a smarter compiler。

 And that's going to do all the the vectorization for the， you know。

 for the native processor for the target processor。And there is， I mean。

 there are really a lot of levels of smart， like I think our compilers， for example。

 last time I checked， were able to parallelze outer loops， but not inner loops。😡。

So even if you ask them to paralyze both， they just didn't do the interlibse。

That may have changed since last time I looked， but maybe not。Yeah。This question might be a little。

Take us down record we don't want to get into okay。

 but I was just wondering at a high level do you talk about what kind of instructions and a compiler issues to make a new thread on another core？

Like how does one core？Sponna thread on a new course seems like sort of。Okay。

 so I want you to watch as I hop out in the rat hole。Okay， but I am going to give you a short answer。

All right， so spotting a thread there's nothing really magical about spotting a thread on a corner。😡。

So if you think about this from an operating systems perspective， you have a bunch of processors。

 each processor has a bunch of cores as far as you know。

 and each of those cores may well have a hypercurity capacity。😡，Right so at the end of the day。

 it's going to see a certain number of cores， some physical course。

Some presented by virtue of hypert。And now your operating system thread scheduler is going to have a long list of threads that need to be run。

 and when the time goes off， it's going to dispatch the threads onto an available core。

Time sharing those borders， so once thread has exceeded its quantum， it's done for a while， right。

 it gets pulled off but back into the waitlist another thread gets dispatched。😡。

So there's just like an area of memory that the cores are going to read from。

So one core is kind of like right to that cue of thread。I'm just trying to think about one。

Can affect another core。How one core connect can affect another core。 Well。

 the typical way that one core affects another core。

 And as we spent like last class talking a lot about it， right， is via memory。

So you have your whole catchching hierarchy and ultimately if one poor rights， the cashing protocols。

 sweeping protocols， directory protocols are going to have to deal with that。

Those open cores just queues up。Threads in。Yeah， for this。And the schedule's memory。

 then when the next another quarter。It' time when interrupt happens and it's time that it get scheduled。

There's just。Yeah now let's be a little careful to separate the CPU model here from the GPU model。

 So on GPUs， the scheduling of the warps was handled by the hardware。😡。

So the hardware had these war and the hardware was dispatching them。

 executing one Gp in lockstep Once we moved from this GPU model。

 the graphics processing model back to the general purpose CPU model。

 scheduling does not really happen on chipI at least in that way。😡。

The OS hasn't so the OS has a list of threads that need work。

 some of these threads the only thread in the process。

 some of these threads actually are part of a greater task。

 there's a period interrupt by the timer device when that happens the operating system schedule runs and basically says okay。

 right now what's happening what of this do I want to be happening and what of this do I want to give a break to let something else run？

And then it's going to sit there in context which the threads is needed。

So there's called yous something called affinity， right。

 which is this idea that we may want to have a certain set of threads run with affinity on a core so that they can take advantage of each other's cacheching。

😡，And so if you're using the Pos threadh library， for example。

 you can specify things about how you'd like those threads to gang。

trying to take advantage of the cache hierarchy there because you have multiple threads within the same process。

 they're sharing the same memory context if they're sharing the same memory context。

 the cache is not invalidated as you move from one thread within that context to another thread within that context。

Which means that if they are， in fact， all working on the same memory。

 then you could take advantage of that。And you could pull your thread into groups saying。

 like these threads working on this object or here。

 these threads working on this object or in this group。

 these threads working on this object or in this group with hosts that when the operating system scheduler goes to deal with this。

 these things will end up being up on this core and needs this core and needs this core。

 If you're the only job running， you have a pretty good sense that's going to work out for you more often than not。

Borarrings of occasional system maintenance or whatever。

 right if you're doing that on a general purpose system and your threads are getting mixed with other people's work。

 then you're going to see less benefit from that type of scheduling。Does that。I know。Okay。

 does that answer your question， You still have most。

 I was just thinking about so open and peace is it going to be。

What it compiles after is' going to be compiling down to Ciscals。啊。这个。Yeah。

 it's going to be making cisco that they OS。And say like， okay， I need to create a thread。

So open MP at the end of the day is creating threads in much the same way as you would create threads with Po threads。

So ultimately what it's doing is it is creating threads and it is joining threads。

As far as to what extent that requires cis calls versus not requiring ciys calls， in general。

 there are user level threads and there are kernel supported threads and when you spa on threads。

 depending upon what type of scheduling visibility you want them to have。

 you can create them either way。Typically， what you have is a certain number of schedule threads represent that the operating system knows about。

 bound to a certain number of user level threads the operating system doesn't know about。😡。

And that binding can be one to one。 That binding could be know， end to M。Where。

And then it could be done with affinity with group scheduling to bind certain collections of threads to certain kernel visible threads or LWPs or processes where the model happens to be internally。

Does that answer your question？And so with respect to if we're doing this with Po threads。

 we think about these things， at least we should， and we ask for a certain level of concurrency。

 ask for a certain level of sort of kernel visible things， and depending upon the operating system。

 you may give a different name to that kernel visible thing。 you may call it an LWP。

 you may call it a kernel thread， you may call it a process individual operating systems name that they just that schedule entity something different。

 but you're going to ask for a certain level of concurrency， which means the operating system。

 if it grants that request is going to give you that number of sable things。

And then you're going to create a certain number of user threads， and if that's all you do。

 when the kernel schedule is one of those kernel threads。

 the user level thread scheduler is going to schedule one among the associated user level thread。

If you have bound that， then any time the kernelel grabs one thread。

 the corresponding thread is going to be chosen if you bound that thread to a group。

 anytime the you know the kernel schedules one of those one of those things。

 the user level thread schedule is is going to schedule one thread from the group that you've associated with that。

And once we're moving into Openmp， we don't have to worry about this because Openmp sort of is。

Does that make sense？Affinity， in some cases， having these groups of threads actually can get significant benefits。

😡，Having said that， that is in the case where it its benefits， right。

 So it's one of those tools that's really valuable when you're the only thing running in the environment or one of the only things running in the environment and you can take advantage of that affinity。

Generally speaking， it's less valuable than it initially seems for a lot of reasons。😡，A。

 there may be both to users in that environment and you're not getting to maintain your footprint in the cache。

😡，B， well， like if I have this group of threads that are all sharing the same thing。😡。

Maybe I don't need multiple threads because only one's running at a time right so you get into a lot of situations where that benefit sort of is where you have a consistent footprint among a set of threads you are the only thing running on the system or one of the only things running on the system so you get to keep your cache footprint and you have blocking that occurs where one thread does one thing and then has to wait for another thread And so your group itself can't all run at the same time。

Because you start to yeah， and so you really have to think through those things before you do that because you may or may not get the performance gains you initially think you will。

And sometimes you can reason about that， and you will get the performance gains you expect to get。

 Sometimes you try it， It doesn't work。 And then you think a little more about it and realize why。

Excellent。All right。So now I think' back out of our rabbit hole， hop， hop， hop。

 we are I think we're done basically talking through this thing。

 the key idea from this is that we have these things shared in private， that there are defaults。

 but we really want to be explicit about that。😡，mLke carried dependencies， right。

 just because we can parallelize something doesn't mean that we should parallelize something。😡。

I think I need to get my laser pointer formed into a gun shape because that would be so much more satisfying to shoot people who are texting in class。

 right with a laser pointer， of course。😡，L carried dependencies。

 right just because we can parallelze something doesn't mean we want to parallelze it， right？😡。

Because there could be dependencies that make a parallelization of it incorrect。So。

Take a look at this and take a look at this at this for loop。😡，ok。

What do you think of that with respect to parallelization。

 let's say I just spawn a thread to handle each eye。😡，I hear the word dependencies being mumbled。

Okay， each element depends on the previous element。😡，So I agree with you。 I mean。

 I see their I depends on I -1。 And in fact， it depends on the element before that that I -2 also。

 So what's the problem with that。 Im， I don't get it。You need。I had issues。Okay。

 you're dying to explain the issues。 I can see it。 You're just like，oo。You're also。Right。

 it's going to invalid into it in the other one。these poor。

Because they're writing adjacent Jason home。Good， I mean you've got both of the issues right there。

 yeah go ahead and may have an issue too。Where。Running these。Then。You obviously don't have a。

Don't have any。Guarantees on what。Keep talking。I'm just trying to burn his cell phone hand hands off。

You don't have any guarantees on what order these luinationss will run in。真ね。Are written out。Meming。

You don't know when on time is。I anyone's read。あ。Yeah， anyone， right。Previous。

Im in the array that I put guaranteeT is too。Okay， correspond。Okay， yeah， so look。

 the only order in which this could successfully be scheduled， right， is sequentially。😡。

Because ultimately these things are reaching back to -1 and -2 before them right so if those values aren't valid this isn't going to work and the only way those things are going to be valid is if I'm walking through it this way one at a time。

😡，There is no other correct scheduling， right？😡，So this loop。

 as it's written is not going to parallellyze well， we can ask Openmp to parallellyze it。

 and OpenM is going to dutifully parallellyze it for us。

 and then suddenly our results are going to be wrong and we're going to blame open MP。😡，Well。

 the poor thing is just trying to do what we asked。😡，And in fact， it is doing exactly what we asked。

Sometimes， again， depending upon your compiler and how much logic it has and exactly what you're doing。

 the Openmp translator that runs make give you warning and say，huh。

 I happen to notice this dependency， you probably don't want to do this。😡，Right。

But it doesn't actually know it's not going to catch everything， right。

 it may catch some simple dependencies and not others， so you have to be responsible for correctness。

😡，No guarantee that open end people find it。😡，Okay。嗯。Now。By default， when we have a for loop。

 a paralyzed for loop， O MP puts a barrier at the end of the for loop。 In other words。

 that forlo must complete before it proceeds past that point。 Does that make sense。

 We paralyzze the forlo， and that we barrier sink after the for loop。😡。

If we don't want the barrier sink after the for loop。

 we can put in a qualifier there that says no weight。😡。

That allows the threads to drop out of the for loop whenever they finish and proceed to the code afterward。

😡，So here you can see the first forlo， I have intentionally poisoned。😡，Well。

 more probably Scott Bden from whom I stole the slides intentionally poisoned。😡。

Added the qualifier or no weight。So now those threads are going to fall out of the for loop whenever they do into the second for loop。

That for loop doesn't have the no weight qualifier。

 so it's good that all going to collect at the end of that one。😡。

So I want to know why the results of this are not correct。😡，Or or not。Let me look at the example。

 okay， so a one of people look at the second example again means I may not be remembering it。

 you guys analyze the example and tell me whether it's correct or not。😡，We look at this together。

Okay， I got the example。と nameも。Like。Some friendss raising ahead。H。one thread finished。嗯。Hm。

So I'm going to note in looking at this example that the first for loop assigns values to A based upon reading B。

😡，The second for loop assigns values to B based upon reading A。😡，Okay。But。

Is it correct or not and look specifically at which A's are being written in red？😡，用你来说。Actually。

 okay。So when we think this correct or not， everybody brings your right hand above your head。😡。

B your head you following that， come on。He proud。你 told呢。Hand up， but had your talk。

 Oh well there we go。Now， it's an only if。You can tell them with self is seeing your problems。

 people lower their heads between their legs in order to lower their hand。😡，Okay。

 if only if you believe this code is correct。😡，Lower your hand。So if your hand is up。

 that means you believe the code to be incorrect。😡，All right， everybody lower your hands。

 raise your left hand。AAbout your head， we're shaking hands。我跟天天在里关。

If only if you believe this color is incorrect， lower your hands。😡，Okay。

 you're taking your best guess， I appreciate that。All right。lowerer hand。Take out a piece of paper。

Tracson， talk to your neighbor。Because we would happy half on that。And， by the way。

If you were looking at the loop bounds， you want to do that。😡，So you believe is correct or not。

Most the slide just changed。like。You're correct， but you missed。

 I mean my that you said that the first time you didn't see the indexes at all。不 you which。

RightRight right， right， right right， and so that's why I said just' these your explanations didn talk about it inus and then I realized beside the drawing。

ど来や。あウスくね。Yes。😊，あ、できるので。Yes。What's that。I''s supposed to be released approximately。

 but I haven't seen if it's actually posted yet。It's all piazza。Yep， the T team。

 of course staff just put together an exam， Professor Brian put together a practice exam， I said。

" hey， how about I put together a practice exam exam them， he's like， I've already done it？

BecauseWhere wherever on schedule？'s next week。All right。

 one thing you learn when you ask a class to work。😡。

Ifs if you pay attention to listening to the class。😡。

There's initially this ramp up in conversation and then it briefly goes down and then it starts to get louder again。

When it starts to get louder again， people are talking more。😡，I done all sorts of stuff。

 not related to the example。😡，So is this correct or not？😡，This slide was wrong， right。

The reason I had people go back and work on is just because I heard people buzzing on it。

 people weren't paying attention to the indexing， and that sometimes matters a lot because a lot of these problems we can detangle by walking through the loops differently。

😡，In order to break the dependencies。So the question is like why do these dependencies prevent parallelism right so you guys。

 I think landed on that pretty clearly right there is a data dependency here where that second loop needs value to the first loop。

😡，If some threads fall down， right， and depend on values from other threads， there's a problem。😡。

It's okay if the second loop depends on values from the first loop， right that could be okay。😡。

As long as the same threat is falling through， if one thread requires AI and another threat。

 the net thread requires A ofI later on， that's okay。😡，Because it executed that one thread。

 executed its slice in series。😡，The problem is if we have something like this or like this。

 where one thread depends on another thread。😡，Does that make sense？Yeah。So on that note。

 so what would be our mental model of how OpenmpP is parallelzing these iterations？

Sing i equals0 to thread1， to third0 and equals。One one sort of like right。

 so you should just assume it with your blocking and you can actually specify that blocking if you'd like。

😡，But by default， it's going to do some linear block。usually do block size like one。

 and then you can make it。Fig larger chunkI don't remember what the default is。

 what it is by default。 So I would just assume that it's being sliced。 Oh okay， You know。

 it's being partitioned in contiguous。 It's not going to like。

So it relates zero by get the first 10 elements。And I wouldn't make assumptions about what that's going to be unless you explicitly state those assumptions with a qualifier and you can。

 and we'll talk about how to do that。😡，Yes sir。No， no weight。

 it basically affects the end of the loop for width that it's qualifying。

 So it simply says that after this loop， don't wait。😡，Right， so if those arrays are different sizes。

 what guarantees can be made， and I think I'd have to check before I would trust that the implementation specific detail。

😡，I don't know there's assumptions offhand。So I would make it wait or I would check the documentation for what my compiler's implementation is doing。

 or I would specify it right So there are three things you could do to resolve that right。

 check the documentation I' be really sure in which case you should comment。😡。

Exactly what assumptions you're making， why you're making them and where you got them from。😡。

That way somebody else can check them later on， right， or make it explicit。😡。

Or put a weight after it and put the barrier in there so you're safe。😡，Right， so I mean。

 if those arrays are different sizes， I dont know I don't have the answer for to use I stand here right now。

 you have to check that。😡，I just， I don't know what assumptions the it's making them in that case。

 either。 And what I would tell you is it shouldn't matter because if you're depending upon them。

 go ahead and set your block and so it works。I don't believe in having I don't pay a lot of attention to that type of thing。

 I don't believe in paying a lot of attention to that type of thing。

 I believe in making it explicit since Open MP and I'll show you how to do that in a minute。

 let you specify how things are getting blocked if you care， specify it。

 don't care and rely on some assumption underneath that most people are not going to know。😡。

That's just， that's just。I think bad practice。Okay。嗯。All right。So we basically saw that by default。

 what Open MPP basically does is slams a barrier between the two loops。😡，Okay。

 we eliminated that barrierator by putting on the no way qualifier。😡。

Okay so now we have a second example down here。😡，And now my question is。

 do we need that barrier in the second example？😡，And actually， let's just bump over here to this one。

😡，We have four different loops here， and my question for you is which of these four loops。

 do we need a barrier between the first and the second？😡，Another way of asking the question is。

 if I would parallelze all these loops with openmp。

 in which case could I qualify the first of the loops with no weight？😡，Take a minute。

 talk to the folks next to you， let's do what to think。😡，Yeah。見や。私のかに。这都怎么。

You can't para at all because A of life this one。いです。Chs are really better than put know way。

parallyzable at all。Yeah。咩名。Think more about four and maybe more about three。やせよ。All right。

 I think we've got it because we parallelze number one。Yeah， I mean， if we look at this。

 A of I is interacting with A of I， right， and something totally different which is B。😡，Okay。

 what about number three， right to a right？😡，Hm， I here knows he yes。All right。

 I'm going to go with the yesses。Why。What's that？Yes。I'm stepping right past my problem right。

 so yes， in fact， there's a problem in first glimpse looking from A of I to A of I minus1。😡，Today对。

But I'm processing this in blocks of two。😡，So I'm only reaching back within my block of two。😡，对。Yeah。

 so polite like。All right， didn mind my call。All right。What about two？What's the problem too？

Right going from A of I plus1 to A of I is much like going from A of I to A of I minus1， right？😡。

Our loop is taking us forward and we're reaching backward。😡，What about number four？

Where's my issue there？Yes， C of I plus one， right， you said it's really A of I in disguise。

 why is that？😡，低げ。ていう場合です。So。确。Okay。Avis。人げ。你可避这边。So C of I here is dependent upon A of I here。😡。

Now you said from the threat over。😡，See you。エバイ？How is C5 plus1 dependent on A y plus1？For each I。

 C is dependent on A。 What I'm not seeing is the left or right dependency yet。Yeah。

So let's say if if there have two threats， one is operating。こち。Then if I equal0 goes first。大け察強よ。あまル。

And if I equals one is knocked down， it's going to get like。YeahMmhmm。Yeah。

 so we should be focusing sort of on this C of I and the C of I plus one， right？😡。

Because that's two different slices of that you may have had。 I just didn't understand。Okay。

I just I just sometimes I just miss it when I'm staying in front of the class， but you convinced me。

The problem we have here is we're dealing a c of I and C of I plus one。And so we could have an issue。

Okay。All right， so we talked our way through that。嗯。Let's see。You know， if we take this loop。😡，Right。

We can't parallelze that with Openmp。😡，not just by saying parallel。

 because it's not going to know how to deal with that。😡，Having said that。

 if we actually look at this and understand what we're doing。

 we can make a higher level reorganization that's going to give us the same results。😡。

So just because OpenM can't parallelize something doesn't mean that a human can't。😡。

And this is a classic example where restructuring what we're doing is going to get us the same values in the slots。

 but computing them in a way that they can be paralyzed。😡。

Now this is the example I thought I'd given you earlier。

 so I was sing the ahead of myself in my head。So。Here we have。Three different loops， okay？嗯。

Notice that those last two loops have a no weight loss。😡，The first one does not。😡。

 I want to know if this code is correct is written。😡。

Or if I have to remove one or both of those no weights to make it correct。😡，Obviously。

 right if I remove them all， right？😡，And the rest of the code is correct。 That's going to be correct。

 But what I want to know is like what's the minimum thing I can do this to those no waste for correctness。

So you might want to ask yourself， for example， is that first no weight safefe？😡，And then decide。

 yes or no。And then ask yourself is the second， no waits safe。Yeah。I agree。I'm Sam mean。

 the example doesn't have to。I could have had no weight on everything， but then people， great。

 it is goodness。Yeah。That's the wordre sitting。だい長。So no aint qualifier。G。

I hear a lot about the no weight qualifier applies to the loop that is listed on。

 it removes the barrier after the loop。😡，I understand that the one in the end。

 so I changed the example to be like this。😡，To make sure people had confidence in what the noway did。

That was an intentional decision on my part， even though it doesn't necessarily make sense。😡。

It was designed to cause you to test your assumptions about no weight。😡。

So I'm glad you're doing that。So you've now told me basically the entire class at once that I can remove the no weight at the end。

😡，Because it affects nothing。😡，Okay， now focus on the warm in the middle。😡，Right name。今外いくい。

All right， so I think we're mostly there in the interest of making sure that we get through some more material this class I'm going to move it forward a little bit。

 so obviously the first one has a barrier it needs。

 the third barrier right doesn't matter to this code。😡，It may matter to code after this。

 so we don't know。😡，We just don't know what's going on next to know if that lasts no way to say or not。

😡，Right。And then as far as the middle one， what do we think？What's that？It's not safe， why not？😡，いうこ。

Right。I back。BeingEle that are shifted over。One is breathing。W the other。Okay。

 so this loop needs values set by this。And it's also overriding value。My first one。Which。Okay。

 so we have two possibilities， one is it's not getting a value up to date value that it needs。

 the second is it could write this C of I and that a slow thread could turn around and use it in its computation using a future value as part of the presence。

😡，So we've actually got both problems there。All right。Now。If we take something like this。

 sometimes what we can do is we can split it into two loops。😡，And if we split into two loops。

 we can detangle the problem。So here's an example， where we're setting B of I to B of I plus equals n minus1 minus I。

So what is this doing， this is your classic working from the outside end， right？😡。

WhereN is the total number of things。So B of zero， right the zero thing equals the last thing。

 b of1 equals one in from the last and we're just sitting here walking our way in， right， pairwise。😡。

嗯。你 see that？Starting at zero， one end and starting other end， one is moving forward。

 one is moving backward， and so our pair is just moving inward。😡，Allright， so。One thing we could do。

Is we could rewrite it this way。😡，All right。So take a look at these second two loops。

 and I want someone to explain to me how this is solving the problem。

I want to know how these two loops solve that problem。You'll have to talk to your neighbor。

 if you'd like。Question， are you ready？What time is it now？机会。Do you。Good luck。What do you think？

What's that。Okay。はこでて。あ。What happens about a move at no weight？So if I remove in no way， Im correct。

 I'm more parallel and correct。Yeah。嗯。Because I'm doing the first half in parallel。

As opposed to before， when I couldn't do anything in her。Okay， yeah。All right。

So this strategy is halfway there。😡，So dividing this up means that the first half is that we can do the first half in parallel。

 right？😡，Because we're doing this and this and this。And we can do the second half in parallel。

 which is this and this and this and this。But this no weight right here is dangerous。😡。

Everybody agree。So by doing this。And breaking it up into these two loops。I'm halfway there。

But I need to remove that no weight for correctness。😡，Do we see that。应该。

OpenI has this thing called reductions， reductions are sort of fun。😡。

So here you see that we have this loop。😡，And basically。We have this done n% equals false， right。

 done equals done n false。😡，If you add anything with false， what's the result？😡，False， right？

So basically what's happening is this and is happening in each of these iterations。😡。

We can specify a reduction on the variable done。😡，And what that's going to do is let each of the loops deal with done。

😡，And then open MP is going to reduce all those dones to one done at the end using the Ampersand dot rare。

 Ampersand colon done。😡，Reduce the done variable in each of the instances to one instance of done by adding them together。

😡，Okay。So normally what we do is we do something like this。

 We go through and we then take the take the done and we add the done together with some cleanup loop at the end。

Take the done from the first instance and the second instance in the third instance and end them all together。

Right。By doing it this way， OpenNP will do that for us。😡。

It'll take all the dus from all the instances and them together to force us。😡，Does that make sense？

Which means that they can do this as the threads finish。😡。

It doesn't have to let all the threads finish and then perform the end as each thread finishes。

 right， it can sit there and perform an endt as it goes。😡。

So it's just one operation applied to those many pieces of data。

In terms of things where we can do reductions like this。嗯。Basically， the answer is。

That if we take a look at ad， subtract， logical and， and so on。😡，嗯。

We're allowed to do this in Open MP for ads， subtract and logical end。😡，Okay。All three of those。

 what are the requirements in general for something to work this way？😡。

For us to be able to apply and reduce like this。😡，It has to be associated why？Because the order。

And what else beyond sociattivity？😡，Given the threads are' going to finish in different orders。

Communative Hawaii。对这个。Yeah， I mean it're going to be different disorders and this finishes and this finishes。

 we want to be able to apply the operation。😡，We don't want to have to then figure out what order threads。

 you know when threads are finishing out of order， we don't want to then have to order the threads in order to apply the operation。

😡，嗯。This is an example of an odd even sort。😡，I'm not going to walk through it because I think we're getting sort of close on time。

 but you may want to take a look at it later， but basically the idea is this。😡。

RightThis sort is going to work by working on odddnum， on the odd items in the list。

 and then working on the even items on the list， and then working on pairing the odd and even items in the list。

😡，Okay。And by doing that， it's not going to have dependencies。😡，There are going to be a problem。

because one thing is working on odds， and another thing is working on eventss。

And so we can work on the odds sequentially， and we can work on the even sequentially。

 but we can work on the odds in parallel with the evens。And it's a fairly standard type of technique。

😡，In order to break dependencies so that we can do things in parallel。

 look at ways of grouping things to avoid the dependencies。嗯。All right so。

I don't think there's anything new here， other than we've now introduced the schedule static thing。



![](img/79ef784d1370d9914d6caee03d8321f3_1.png)

Static partitioning breaks things up in advance， dynamic partitioning does not。

 breaks things up as it goes。😡，Okay， and we'll talk more about that。We've already， I think。

 beat the idea there's no way caused to death。All right。So we're going to pass that。

I already talked about the fact that we can ask to paralyzze inter loopops and if we want the inter loops paralyzed。

 we certainly should ask。😡，Don't have any expectations about what the compiler will do there。

 because a lot of compilers cannot paralyze inter loops。😡。

They just cannot do enough of an analysis to do that。Some can paralyze interludes in some cases。

 but others， most really none at all。😡，We know our oldri matrix vector multiplication right。

 I have a matrix， I have a vector， I want to multiply。😡，Causes much pain， right。

 But it's a great example for paralyzing things。

![](img/79ef784d1370d9914d6caee03d8321f3_3.png)

Okay。So。Here we have some code。And we've gone through and specified that as far as we understand so far。

 we've declared AX and N to be shared variables， we have our parallel for loop and off we go。😡，嗯。

And we can see how this has been。Dividing。Now we can start schedule， yeah。Can we use the Cdy that。

Can you use Cdy， so you're not going to be using your ISPC instructions， right？So okay。

 the question is， what happens if you explicitly call us MD instructions？

The answer is I don't actually know， send me an email of post to P， I'll look that up。

I've never tried that anytime I've used that MP， I've let it worried about it。

But I think itll be fine。But let me look into that so I don't tell you a lie because I haven't thought it truth fully。

So notice static2。😡，Okay， so now what we're saying is we want this divided up in advance。Okay。

 and our blogging is going to be two。😡，All right， and now you can see how that's colored。

The good thing about statically scheduling these things is that there's less overhead involved。

 right？😡，The bad thing about doing it is that if things get bard down。😡，Right。

 because there's a different work density。😡，Then if you've already colored it in terms of which thread is going to be handling it。

 you're going to have a queue for some threads and not for others。😡，Does that make sense？

If we do dynamic scheduling。Then what happens is we're still asking it to be scheduled pair wise。😡。

Okay。But we're not necessarily dividing the resulting chunks up in advance among the threads。😡。

So when the thread finishes， it's going to come back and get another partition to work on。😡。

So you can see here some threads are grabbing a single partition。

 some threads are grabbing two partitions back to back。😡。

And that's because of the work density they happen to land with。

 they finished earlier and went back to the well。😡，嗯。And so static versus dynamic。

Determininees when the scheduling has happened is happening while the stuff is running or in advance in general。

 if you do it， if you have a fairly uniform work density。

 doing it in advance makes sense because there's no overhead for dynamic scheduling。

If you have a work entity that's not uniform， where certain threads going to get bogged down。

 certain are going to get finished earlier， then you want to have dynamic scheduling to let them go back and get work as they finish theirs。

😡，And then this is the chunk size。The two。But you can't see my point。There we go。The two。And so。

Take just a minute and in particular， make sure we understand this middle example。Okay。0，0，1，1，2，2，3。

3，0，0，1，1，2，2，3，3， right？Basically， if I take my array， this is showing which thread is processing。😡。

Notice it 0，1，2，3，0，1，2，3。I'm chunking it by two。😡，And then it's just getting divided up as it goes。

Boom， boom， boom， boom， boom， boom， boom， boom， Nice and even。

Notice that if I have something that's not divisible by two， I have one left over at the end。😡，0，1，2。

0， leftover。Initializing data in OpenM， this turns out to be a really important point。😡，Okay。

 we allocate heat storage outside of a parallel area。

 but we initialize it inside the parallel region。Okay。Why do you think that might be？Yeah。Ultimately。

How。你签的。Okay， so we initializing it outside the parallel area is we want one of them。😡。

sort allocated outside the parallel area， these we only want one of them， but then I said。

 but we initialize it inside the parallel area。😡，Yeah。Nous system you want。Yeah。

 if I allocate some huge chunk。😡，I want to allocate that before I start because I don't want to do that in parallel。

 but now that I have this huge chunk， if my memory system is not uniform。

 and I have certain pieces of it that are closer to certain processors。

 I don't want to have one processor reaching out to all this distant memory in series to initialize it。

😡，Instead， I want each processor to initialize the chunk of it that's closest to it。😡。

So I need the allocation to happen once， so it has to come first。

 but after that there's every reason to want the initialization to happen right in parallel。

 A because it's in parallel and B because it could actually be faster， right？😡，In absolute time。

Avoiding long trips over the bus。 So minimally， the initialization is happening in parallel by multiple processors initializing their chunk。

Maximally， it could actually turn out to save time。😡，To save distance across memory。

You're looking at me really fine。Maic。P。Well， right。

 so the question is how does a malic work on a pneumous system？😡。

And the answer is the good news is Malck doesn't actually have to touch the memory it's allocating。

That's right。 You you taking to3 Ken。So when you wrote your Malik， right， you just set a break point。

😡，You didn't actually write to all that memory。😡，はい。I mean。

 you may have written like if you were not optimizing for Nuumma。

 you may have written some accounting information into a block。

 but you were not touching the huge amount of that memory， right。

 You wrote a little bit into a block over here， leaving this huge initial allocation。😡，Right。

 totally untouched。So to allocate that memory， one core may have had to touch one little bit of distance memory。

😡，Okay。Maybe we scheduled down the right core， maybe we scheduled on the wrong core shrugs。

 maybe we could be smart about that。But to initialize it and actually put the values in。

 we want to make sure that each ch is right for the chunk near it。Yeah， smart。Smart enough to。

When you pay fault。To make sure it's an anum system that it gives a physical page that is actually close to that processor。

Right， so if I actually have a system that's truly pneumma architecture as opposed to a systems nuum that has pneumma properties。

 like if you have like a standard multi multiprocessor system。

 you have some pneumma like properties because there are caches local to course。😡。

So there is some non uniformity there， but it's only in the second class cache。

 not in the first class memory。😡，Now， if we're writing a。

 if we're optimizing a computer for that has true pneumma architecture。

 that's not a general purpose system。 And then all these libraries are going be tuned for performance there。

 So， yes， absolutely， that Malic is going to be， is going to be tuned。That way。Or more precisely。

 the Malic is going to be tuned to allocate what it allocates and the scheduling by the threads is going to be tuned to work local to that。

Because I think like the late Ba was make dual socket。For some of the hope is。The page forward。

Each soit memory that is actually close to on a page fall Well， on a page fault。

 what's going to happen is。IfIf it falls。Geez， I'm trying to think of whether or not it's smart enough。

 It's actually gonna be smart enough to do that。 I would， I would think I would go with the answer。

 which is the hope is。 I'd have to look to see what that code is doing。 The answer is。

 I believe it's smart enough to find， to find a page that's gonna be local， but that's only。I mean。

 this is a weird case， right， because it's not going to fault in a page it's from the cache。

Does that make sense， So actually， as it turns out it's not going to be the concern that there's some concern。

 but it's not the one concern you think it is， because if I have something in my cash。

 it's not faulted out。Does that make sense？If it's in my cache。

 it's used recently enough that I haven't faulted it out of memory。😡，That would be a weird day。

每 sense。Okay。Yeah， they does that share。Other。very部。I it almost goes useless？

You could say it just absolutely。So。Well， so a is literally a is what is shared。😡。

As for the mallet region， that is shared simply because it's declared outside of the forelift。😡。

Great， it's never forking new processes here。 The sharing model is entirely threads within the same memory context。

😡，So the only question with this shared thing is for a loop instance。

 do we want to have like a different counter？😡，Things like that， we had 10 four loops。

 and we want that to each have their own eye， so're each iterating separately。😡，Correct。

So if a we're private， then we might have a loop， which actually the increment today， which is legal。

 right， it's just a pointer。😡，All right。Quick notes as we wrap up here because I know we're hitting time。

Open MP is also an API， okay， you could also call functions to do this type of stuff。😡，All right。

 you see some example here calling those folks functions， OMP underscore， get thread number， O。

 you know， and so on。 So anything that you can do with the pragmas。

 you can actually do with the you know with the API function calls。

 back when I first learned learned openmp。 It was not built into the C language。

 And so we use we use the API These days now that it's built in with pragmas。

 I haven't really touched the API very often at all。

 There's occasionally something glad it doesn't exist with pragmas where I just don't know it。

 And I fall back to using the old function calls。 But you should know that it's there。

 You should know that you can use openmp from in other environments like Java and go in other places where it's not built in and you just use the overriding functions。

 not overr， but the API functions。So。OpenMP is you know where does it accomplish for us right it gives us this wonderful high levelvel interface that we can use to basically write threaded code without having to mess with threads。

 we simply say this is what we want and we leave it to the OpenM transator to commit to us we say these things are shared and these things are not shared and divide the work up this way。

😡，Poof。And divide the work of this way could be statically， divided up in advance， assuming。

 you know that's what we want， or if we have varying computational density， we can say， look。

 divide it up dynamically。😡，We can specify the chunk size that we want so that we can make sure that the parallelism works the way we want and that we understand what dependencies exist or don't exist in the code。

 it's actually really nice， it handles the synchronization and petitioning。😡。

And so it does a lot of good things for us。You know。

 it almost makes you wonder sort of why I think that we have a lower level interface。😡。



![](img/79ef784d1370d9914d6caee03d8321f3_5.png)

And the answer is it doesn't do everything for us。It operates under a certain model and the model basically is that it starts out。

 it spawns a whole team of threads， it synchronizes those threads， it spawns a whole team of threads。

 it synchronizes that team of threads。 and if that's not the model that we want。

 then we still to fall back using positive threads or some other model for example。

 if you want half the threads to continue and you know。

For a long time and then you know have some threads you know that get synchronized and so on。

 This is a model that's going get tangled very quickly， right。

 It really is designed to spotwn a whole bunch of threads， tackle something in parallel， sink。

 tackle in parallel and sink。So if you try and do something different。

 then a lower level model might be helpful to you。😡，Having said that。

 this model is really useful and really clean for a lot of problems。😡。

I've become a big fan of it actually。Any questions？Have a great day， everybody。

