# CMU《并行计算机架构与编程｜CMU 15-418 Parallel Computer Architecture and Programming sp18》 - P9：Lecture 9 - 2-2-18 - Carnegie Mellon University.zh_en - GPT中英字幕课程资源 - BV18b421J7cA

今可以。All right， you rate a rock all。Welcome back， so I guess only straight。

Before we get started is that we are。on draining your。Your first assignment。

 some of you turned it in as part of the race to add， if you did you just got a score。

 regardless of whether you turned it in or originally you turned it in as part of the second deadline was' going to happen as you're going to get back a score with feedback。

So previously you just received a score， you're now going to receive a score with feedback。

The reason we didn't provide a lot of feedback at that time was because we still have people doing the assignment。

 right because that would have generated a little bit fair place。

So original that you just got your score about a week。

 you will get score plus some feedback and if you're one to people you use the second deadline because you weren't part of the race to add to class then。

It should not be the case that any of you turned it in earlier will get a different score in the second time。

 first time， but obviously if that happens and is not in your favor。

 then bring that to our attention。嗯。But hopefully we'll just be adding feedback。You know。

 look we gave you two points extra the second time。

 I guess there was difference of opinion between the grader doing the initial review and the second grader。

And that difference is to your benefits。We can't figure out now look。

 we can't figure out if it's 98 or 100 and 100。Oh， you know。Onite might be helpful。Mike is turned on。

 Oh， but can we cancel that Yeah。I care if I can do it。Testing  one， two，3 yeah。1，2，3。That's better。

这可。is all about kuda。And so you know in last class Randy。

 I think explained to you the basic architecture of Kuda and sort of how it works。

 and so I'm going to do yeah。We just keep it guys guessing when tuing out occasionally。平止のケ供を。

I what is VG。不。哪个不管他。So I guess let me just。That the。All right， there we go， so yeah。

 after that doesn't make sense， let me know because I don't have competent， competent。にがござい。Okay。

 I just want to review some of the before we dive in a little further。

Review some of the basics of what we talk about。 So we talked about the idea of a CPU。

 which you guys are very familiar with right you know the CPU is basically know the brain of a typical computer And let me talk about this things the GPU right the graphical processing units。

😡，processing unit is basically the brain of the video board。Right。

We talked about the host versus the device， so when we're talking about programming GPUs。

 we talk about a host in a device， all right the host is the computer itself。😡。

RightThe device is the video。So if we talk about memory on the hose versus memory on the device。

 that's the divide。Who do the compute unify the device？

That is NVIDIA's software framework for doing general purpose computing upon video boards。

There is an open version called openCL， that's sort of the generic version。

Global memory versus shared memory。嗯。Okay， so global memory versus shared memory。

 global memory here means the memory on the device。😡，It's global on the device。

 it's not global between the host and the device， it's global on the device right so global memory。

 you know we do things like Kuda Malek Kuda free and Kuda Mecom right to get things between the host memory and the global memory。

😡，So shared memory is basically memory that's associated with a block。

 it's shared by the threads of that block。😡，Not across。Colonel。

 that's the piece of code that would rubber standing out there across all the cores of the GPUs。

 right？😡，The thread is an abstraction for the work associated with an instance of the kernel。

And that's worth just a quick pause， right， a threat is natural。

The work associated with an instance of the kernel。So we had this kernel。

 which is a piece of work that we're going to want to do in a massively parallel way。

 and a thread is an instance of that， a single one of the many。😡。

A thread block is a partition with threads， an associated work that will be dispatched to a so called streaming media processor SMM。

All right， so if you take a look at your GPU at your video board。

 your video board has a whole bunch of these Ss。And each of these SMMs is sort of roughly analogous to your CPU on your computer。

😡，All right， obviously， with very different capabilities。

 just like the CPU on your computer has a bunch of cores， each of the Ss can have a bunch of cores。

So an SM is not a four， it's actually a processor as it turns out， is a multi corere processor。

So a thread block is a partition of the threads， right we have this kernel and we say okay。

 we want this kernel to be run in a massively parallel way。

 there going to be a basziilion instances of it。😡，All right。

 and now we're chopping this up into blocks and saying， okay， of all these instances we want to run。

 this is one block， one collection of them， and this is another block and this is another block and this is another block。

😡， all those blocks together are set to form the grid， by the way。😡，Well。

The thread block is going to be dispatched to a particular SM。😡，All right， once it gets to an SMM。

 the SMM is going to figure out how to dispat。A P a core is， like I said， a core。

 it's one of the many processors inside of an SM。😡，嗯。All right。

 a warp is a division of a block created within the SM to assign work to course。😡，All right。

 a division of a block created within the S。To assign the work to course， in other words。

 we hand a block of these threads。To one of these S processors。

 the S processors is further going to break it into warps and the warps are actually going to get dispatated。

Okay。Wps aren't scheduled until a core is available， reach the red within the wharf。

 So in other words， we have a warp that has。20 threads of it。And the SM only has 16 floors available。

 it won't be dispatched。You can't do like three quarters of a war。

 it'll dispatch the entire warf at a time。😡，NBCC， obviously the compiler shared the qualifier declare variable in per thread block memory。

Global， that's the qualifier we stick in front of the function in order to make it kernel。😡。

It becomes a function then we can run on the device。It can be called from the host。

 but it's actually executed on the device。Kuta malic， ka free， KaM copy。

 these are the things that we use to play with memory on the device。

 it's how we allocate memory on the device versus memory on the host and how it is that we copy things from the host to the device。

Same threads， we talk about that right once we have all these threads running， right。

 we need to make sure that we can synchronize and make sure that a phase of work is done。

Right before we move on to another phase。You can imagine that that we're applying a whole bunch of filters to some imagech。

 and you want to make sure you apply the first filter before the second filter before the third filter before the fourth filter。

😡，And so you launch the first phase。That applies the first filter in massive parallel， right。

 you sync， you wait till everybody's done， and then you apply the second phase and so on。嗯。Okay。

 we talked about the syntax associated with the kernel launch， right， we have some function。

 the triple black bracket thing， and then the arguments to that function。

The triple bracket thing takes in two arguments I'm calling N& N and being the number of thread locks and then being the number of threads per。

So if you need to multiply n by M， that's obviously the total number of friends。

We have these variables we talked about， block IDX and thread IDX。😡，Okay， ID X is short for。

Shockingly and amazingly indexed。All right， so we talk about doing things like threadIx。

X and block idx。X， I don't know we talked about Y it's doX， do we mention that？😡，我在。😊。

It's multidimenional， that's exactly right， So these things are actually blocks are actually three dimensional。

😡，And so depending upon the code you write， you may treat them as the three dimensional or treat them as one dimensional。

If we're treating them as one dimensional， we're only going to care about x。

 If we're treating them about two dimensional， we're going care about x and Y。

 Are we treating them as three dimension。 we're going care about X and Y and Z。

And that's true for both the thread ID and the block ID。Block dimension and grid dimension。

 same thing， right， what's the dimension of the single block and how many blocks are there in the grid？

Like I say， if you take the total work and break it up into blocks。

The grid is said to be the set of those blocks。啊。Make two部。And again。

 the grid is also three dimensional， so we have to dimension5。You know， using dimension as a the。

Picture。Or at least a few words， right， so this is just a picture we show the device。

 we show the grid， which consists the blocks。Within each block， we see the threats。

And that's the basic hierarchy in。And we talked about the variables that give us visibility to this。

 the thread index， the block index， the block dimension， the grid dimension。So next phase here。

 I want to just offer you some possibly helpful tips。You know。In 213。

 we beat into your head that you should check the return of all library halls， right？😡。

That was like one of the big titles。嗯。And we beat it into your hands， I hope beyond Saturday， right。

 I mean you were checking for the return on function calls that you can't do anything with it。

 they fail， right？😡，You want to think like that here too。Okay。

 you really do want to wrap your calls to Kudah and figure out if they succeeded or fail。

And figure out why， because if you're having trouble with your program and you're working on debugging it。

😡，And the basic dispatch of the program didn't work up。

It's going to be really helpful for you to know that and to know why。So。If you take a look at this。

There's this thing， GPU assert。Okay， that's going to let us check things。And so basically。

What you can see is is we have the GPU As and then decide that we have it wrapped。

 if code not equal to Kupa success， then we get the Kupa errorerostr。

And those are the basic two parts to it， right if we didn't succeed。Right。

Not equal to coup to success， then we get the error string to figure out why。😡，嗯。Okay。

In the case of kernel launches， you can't wrap the kernel launch itself， but you can ask。

For the last error。And so do your kernel launch and then check to make sure the last error is a success。

And that'll at least， you know， look， problems like this are not very common， right。

 but when they happen， they cause hours and hours of debugging for no good reason。

And so the 15 seconds it takes to add this to your code is really cheap in terms against those bad days。

There is GDP for C， your old friend is back and better than never。😡，That's the right reaction。Yes。😊。

213。Oh， this is going be bad ahead。给去之前。Yeah， you know， you you know。

People invent all these weird rules， like you shouldn't use macro as as arguments。

 you should use inline functions and so on。look as a general principle， right。

 you should use inline functions because it makes it much easier， for example。

 when you go are debuing into them。And all that good stuff。

But I think you've got to use your own judgment as to what's the right tool of the job？嗯。

I note that much of the 213 code， at least originally was written with macros。

 I think we eventually sterilized it all for you。Eliminated this evil macros in favor of the nice and beautiful。

And like I said， again， inline functions are generally much cleaner， much nicer。You know。

 they make a code just as readable as macros， they let you debug into things。

 there's a lot of good reasons to use them。😡，All right， your old friend GDP， Yeah， so GDP is back。

It works basically like you remember， you can switch between couda threads using the basic same syntax you had before。

 but with kooa before it。嗯。Info locals will give you information about cut threads also。

So it's really nice when we hope， don't ignore your old power GDB。嗯。You know。

Constents are still sort of evil。 don't wire them down if you can avoid it。

 Comp anything that you can compute。 And the reason is there are a lot of things that are going to seem like the constants right now for a particular board。

 and then you're going to sit down at a different computer or whatever technology is going to be upgraded。

 and you're going to have a different board and all those things that look like relative constants today turn out to be variables tomorrow。

So don't put magic numbers in your code， don't even put magic numbers in your code pounds defined or constant to values。

 compute everything you can and have the most minimum set of constants。Againt the many， many， many。

 many， many， many computations you're going to be doing in anything you're going to be using a GPU for the amount of time it takes to divide in by the by the you know。

😡，By the number of blocks it's just not going to be a big deal。哦。

Don't try to do the roundup stuff yourself right all over your code。

 you're going to find that you're going to round up the number of things you have right to a multiple so that you can divide it up。

😡，You don't want to sit there and do that roundup in your code constantly because it's ugly way。

Write an inline function， write a macro， do it once， wrap it。嗯。

You want to know the correct answer before you try to parallelize something。😡。

Because there are a lot of ways that when you parallellyze something。😡，It can go wrong。

And you saw that you can reach over and grab a value before it's computed。

 you can interfere with the computational of values across partitions and so on。😡。

So before you start， you want to know the correct answer。😡，And that's the baseline that way。

you develop your code， you know whether or not you have a correct answer or simply a faster answer。

my first job， I was optimizing a neural network。And like the first thing I did is I built this neural network。

And then the next thing I did is I optimized it。That was a first year gratitude student。

Now I was really happy when I got this neural network filled and had this strategy。

We were all really happy。I built this thing， but it was really slow， it was really slow。

SSpice spent a couple of weeks or something optimizing the study。And I got it to run way， way faster。

But the problem is never actually converge。At least not always。

 and so we had this status meeting where I told the boss， well there's good news and bad news。

You know， the good news is we're in 100 times faster， right， the bad news is we don't get an answer。

And that prompted my boss to turn around at his chair。And type in basically hello world and C。

Compile it and run it and say that runs faster than my network。I'm like， what are you talking about。

 he then went deleted the printde line。And then said， that does two。啊。😮，Yeah。

 that was this point because if I wanted a wrong answer， I could do that really fast。

Like why would you trade away correctness for performance， like what are you doing？😡。

Like correct is the baseline。Something broke， you shouldn't have kept optimizing。

 you should have fixed it。Not expected it would like somehow more of itself facted correct by itself。

😡，And of course， the real answer is I didn't know it was broken right until I spent three weeks optimizing things。

 and I ran my regression test before the meeting。😡，They， you don't want to be in that day。要对 that。嗯。

Like you're Carnegie male juniors and seniors， not like Clemson grad students， you pass that， right？

All right。So you what you need to know is you need to know the correct answer before you start。

 and you also want to have correctness checkers that you can use to compare your answer to the correct answer and so on。

😡，Right that way you'd have some confidence， you don't want to be in a situation where you ask the question。

 is this all correct and that comes back and says no either？😡。

You'd like to have to be able to break it down into steps and figure out where you've gone wrong。😡，啊。

Until the second generation of the Kupa architecture。

 there was no such thing as a print death within a colonel。嗯。And at some level。

 print up with an kernel doesn't really make a lot of sense because there's no console attached to a GPPU kernel。

Good conversation。啊，恢。There console attached to a GPU kernel。

 right so this idea of a print deficit within a kernel makes very limited sense。

It's also not clear what it means right， if you have a huge number of hundreds of things going on in parallel。

 right， what it means when you dump them out to your single console in some order。😡。

So print dev is really sort of confusing in this context， but because like programmers want print De。

😡，I mean， at the end of the day， printde is the world's most commonly used debugging tool。😡，In fact。

 in the second generation of this， they did in fact add print depth。

 so you do add print death within kernel。😡，Of course。

 that tells you nothing about ordering blah bh bh bh bh， bh， blah blah， blah。If you're yeah。

 and we can talk more about that in a minute。诶。And again， like Todd said on the very first day。

 you always want to have a baseline， you want to have it done before you start paralyzing it so you know if what you're doing is making sense and as I said。

 you know it's correct。😡，嗯。嗯。Out of bound memory is bad and see， right。

 if you walk past the end of an array， this is a bad day， right？😡。

The good news is things like Do R and St will find that for you pretty quickly。

 and we have a pretty good understanding as to what happens， right？You know。

 if you write out of bounds in memory and C， one of three things is likely to happen， right， A。

 nothing， B an incorrect result。😡，Or C， you'll find out that God likes you。😡。

What happens if God likes you in your programming and you make a mistake like that？Saidful。

Saake faults are actually proof that God exists and likes you。Because like option A， right。

 is that you write your code， you accidentally make one of these mistakes， right？😡。

And then at the end of the day， you compute the wrong result and don't know it。That's a bad day。

Right。Your spaceship just crashed。😡，All right。A good day is during testing。

 you run this thing that blows up with a Se fault。😡，You。Like my test set didn't find this。😡。

My tools didn't find this。不带尬的不啊。Or maybe it did blow up when you were testing。

Because now you know you have a problem， you know where the problem is。

 approximately or at least where the symptom is， and can go without fine。😡，So you， as C programmers。

 we're really used to how things happen when we step past a raise and whatnot。😡，And Kuda。

 just it's much more evil， generally what happens is you just get a wrong result。😡，Right。

And that's really bad。So you want to basically put in a huge amount of bounce checking code。

 huge amount， check everything。😡，And every detail because all it's going to do is save you having to debug a bad result because if you're expecting 47 and you get 40 or 42 and you get 41 and a half。

😡，Right， that's not good。And then you've got to figure out how。If you bounce， check everything。😡。

You to find out immediately where the mistake is and be able to debug whatever rounding function is causing it or whatever。

😡，The problem， of course， is that debugging everything does have some performance。第二品牌。

And so you want to wrap these things。You can debug stuff so that you can turn it off when you don't want。

嗯。We talked about the fact that。You know that the kernel now has printf， the slide says。

 but it doesn't really work very well。And that depends how you define really well。

 It does what it does。 It's not actually random， but there are a lot of constraints on printf。

 and we'll talk about that。😡，嗯。So if you're trying to figure out what's going on。

 sometimes what's helpful to do is to have a local host version of some code right and a parallel version of the code and be able to compare those two。

😡，So the slide says printef is pretty unreliable， I mean printf is what it is。😡。

There are no dis involved in printing。😡，There is nothing random associated with behavior of pro Devk K。

But there run is like a bunch of detail。Okay， the output is stored in a fixed size circular buffer。😡。

If you overwrite the circular buffer， you overwrite the circular buffer。😡，Okay。Yeahay big。

Print more than that， bad day for you。All right， what's worse than that is I didn't tell you there was an F flush in Kuta。

😡，Instead， Kuda is going to flush when it decides it's going to flush。

Which may not be when you want flush， given me the amount that you want to write and your fixed size buffer。

Do you see the problem？Yes。So now we can start to talk about when this buffer is flushed。

 the star of a kernel launch， called any your synchronization functions， blocky memory operations。

 module loads， runloads， context destruction。😡，嗯。Interestingly enough， not program exit sense。😡。

Although most of us do have something like who to deviceynchronize right before all of our stuff ends。

 and it actually will print out there， which is sort of like a program。😡。

So the bottom line on this is you're much more likely to succeed with printds if you use them sparingly。

😡，If you start to use them not sparingly， one output will overrite another output will overwrite another output。

 and you may just get a mangled output because they may not be modulus buffer size。😡。

And you may think like I'm not seeing in the output so it's not running。

 but really you just haven't hit one of these events that causes it to flush。😡。

Don't spend your time looking for a way to fix that， there is no coupa Elash。😡，不在。Makeけ Colほ。I mean。

 yeah， I guess。Like we could do a lot of nothing in order to ensure our prints were。啊。

I know another way to achieve that。Learn that to my old boss。All right。

 now I'm going to charge third example now。I actually don't believe we're going to get through this entire stack of slides today。

4 buy more of them。Okay， I have no expectation of that。

My expectation is simply that we're not going to run out of slides today。😡。

Although I could surprise myself， I did last week。So don't feel badly when we don't get to the end of this day。

 because we have a second recitation about Pa。😡，And so I'm going to pick up the slides we didn can cover this week and stick them to the front of that deck。

And that is the plan， so we will not be behind schedule when we do that。

 that's just simply the schedule。😡，All right， so you guys are familiar with Matrix up with you know。

With major multiplication， it's approximately evil。😡。

It may in fact be the most common form of evil in the computational universe。😡。

What is evil about something that's done this way with one row operation and one column operation？😡。

嗯。Well， I guess even before that， before even worry about rows and columns。

 what's generally evil about matrix multiplication case？😡，Involves a lot of。

What's the simplest word you can use to describe what it mouth a lot of？😡，Math， work。

It involves a lot of work， right？I mean， look at that summation。You。All right， I mean。

 that but they're like。More than one subscript there。Two squares involved。Okay， so to begin with。

 this involves a lot of work。😡，Now， when you start to think about it in terms of 213。😡。

 you realize that when we have something that's two dimensional and stor into memory。

 it has to be put into memory in a row major world， right？😡，So we're going to take these rows。

 row after row after row after row。After row。That looks sort of nice。

With respect to the Rwise operation。What does it not look nice with perspective？😡，What's that B。

 yeah， that B thing， column wise operations？Right， because now for each element of the column。

 we're going to have to move a whole row。😡，Right。And I say move a whole Robbie。

 we're talking about cashs here。And either cache is in the traditional sense of L1L2L3 or cache is in the sense of the memory that we're going to manage on the device。

ok。So thank you， bothification。And then this memory access。You've probably seen。

The code associated with this， about 73 times in your career。

We all love this as an example of painful， you know。Qudratic type of thing。

So we always baseline what we're doing， right， we always start out with a simple implementation that we can be really sure is correct and is really easy to debug if it's not。

😡，right I like to refer to as the most expressive implementation。

 the one that's easiest to understand， that's where we start。😡，And then we benchmark。Now。

 213 question， look at the performance。😡，What do you think is happening somewhere around？😡。

Which one do you need to buy 12？Do you think our processor is suddenly getting slower？😡，Dreion。Yeah。

 we're having a problem with the cash right as things get bigger。

 we can no longer fit a whole bunch of rows in， so we're threatening our columns。😡，Make sense。

When it's small， like I don't care a row major column major， just throw it all in there。

But as it gets larger。Right， because we have to load a whole row to access a column。😡。

RightWe're pushing things out of our cap。And our cash isn't big enough to tolerate that。All right。

 so B has a very bad access path。All right， so one thing that we can do an optimization here。

 probably the simplest optimization that when we look at this performance curve。😡。

And realize what the problem is， right？The simplest thing we can do is try to fix that colorwise access。

😡，Because that's just painful。So we can pre transpose B。😡。

We can rotate it and develop a transpose peak and now we can perform this sorry with rowwise operations on both。

So we had one painful thing to do to rotate it， right， but once we have。

 now these operations are row。😡，And that's much， much， much more cash from。😡，So the transpose。

 what to say， converting column from row major to column major ordering， painful。But we do it once。

Okay， so the goal here is。That by paying the price to do that once。😡。

We're going to save performance in the future and if you think about that， right。

 know this amortization should be in our favor right because the work here is cute。😡。

So there's an implementation of pretranspo。嗯。You know what to say， this work is square。

So now if we look at this。And we' looked at basically the same plot we had before with digcolops being what we're measuring as we increase the size。

 we see that our performance is much more steady now。We're encountering much less of a penalty there。

And that's great。😊，而 k。😊，By paying the price to flip that once。

 we now are having a much better cash footprint that we can beat on as we do the now real order operation。

😡，Okay。Well， our next step in this process。Is going to be to convert this to code around GPUs。😡。

All right， shoot， I forgot to turn of my gloss， I'll to go add that back later。Right。SPMD。

 single program， multiple data。All right， that's what we're talking about here。So。

We have end processors all executing the same code。

 where do we find end processors to all execute the same code at the same time on one of the GHC 26 through 46 or whatever machine？

The sudden plug into those machines that gives that to us。On the GPU board， right？

There's little cars made by N video， we plug it in， you can game really well or do your homework。

Paauusible deniability。All right， yeah， so when we talk about the SBMD model， right。

 this is the model that basically we're playing with。

 we talked about using these graphics boards in Kuda。😡，All right。

 so we basically have M processors called kernels， executing the same code。嗯。Okay。

They share a common global memory， there's no synchronization premise what I mean by that is there are no shared memory synchronization privilege。

There are no mutexes， there are no semaphorees， there are no condition variables。

 what we have is barrier synchronization。That is a synchronization primitive。

 it's just not a shared memory reynchronization。嗯。Alright。So we have these threads。

 but these threads are actually very simple and lightweight things。

 remember that a thread in this context is an instance of the kernel and execution。😡。

It's that kernel code running somewhere。One instance though。

And so the basic model that we're going to have is we're going to start out on the host。😡。

And we're going to set things up and copy some data onto the device。

 and that data is going to be attacked in parallel by the device。😡。

Then because we don't have any other superization primitives。

 we're going to synchronize with some type of barrier sink， wait for everything to be done。😡。

And then step what we want to do next。Copy it back onto the board， let the board attack it。😡，Right。

Let all the threads finish。Synchronize。And we， we're just going to go from phase to phase to phase。

ok。As you might imagine， one limit you do see with these things is how fast you can move data to the board。

😡，There's a huge amount of computation， but they can't actually find themselves Iopried。😡，嗯。

All right， some performance limitations， synchronization requires waiting for the slowest task。

 right， sometimes called the long tail problem， except the tail shouldn't be too too long。

 but the idea is that if something's finished before others， you end up waiting。

RightSo you imagine that if you're trying to build some scene by starting out with a scene and then applying a filter to make it look like a foggy day and then applying a filter to bring focus to certain things right those are separate phases you can't you know。

😡，You know， do the global focus until you set， you've got the fog in place。

whichch means that if you partition this and there's a chunk of work left over。

 that chunk of work has to finish on the fog before you can turn around and start working on the rest of it。

😡，These phases do actually generally have synchrons。嗯。you know。

 no locality of data or synchronization So the memory model here is what the memory model is， right。

 there's the host and there's the device and there's memory that's shared by the blocks。😡。

There's no cash， everything is explicitly managed。And no locality of synchronization basically means the synchronization we have again are the barriers。

哦。All right， executing threads are group into blocks， each block contains the same number of threes。

The host program specifies the block size， right， that's the block convention diets。And again。

 it doesn't have to be one dimensional， you can have two or three dimensional blocks。😡。

The host program makes sure there are enough locks to generate some n number of threads。In general。

 right in the ideal world。😡，The number of things of chunks of data we have would be an exact multiple event。

😡，In the real world， the number of jumps of data we have are not an exact mold。😡，Not common right。

 and so we're going to have a few leftovers， and that means that there's going to be one thread block that's not completely full。

😡，So Sun threads network are just not going to do any useful work。

Because there's no data for them to work。So if you really think about this model。

 the host is acting as the controller， it's setting things up for the board。

 which is now doing the computation。😡，嗯。The host does not have direct access to the device memory。

 right， the host has to copy things there。😡，Why do you think they don't？Engineer some system。Right。

 because you could。Where there is shared memory between the host and the device and。

The hose can read to it write from it and soak in the device。Yeah。The CPU is9 to the GPU。違合が。Okay。

 so。At some level we can look at it and say right now， given the design we have。

 it doesn't exist because the connection is via network， the PCI bus。

 but why don't we design the solution to this problem？😡，I mean it sounds kind ofね。You do。

 since you have these。Different model。Yeah， we have different models of execution but our memory models are really out they're different than reading rights。

Yeah。The memory。Maybe it's because memory the graphics is much more vast。

 but we could look at what the performance specs are and say。

 it that a reasonable thing to do with respect。这是没有。経デや？The challenge。One。バに。one might have been。

Memory controls have very good。So what would be side of that？も前見だ。But the real problem here， right。

 is that if we have multiple things asked to see the same memory， that memory becomes shared。

As soon as we have a shared memory， something that multiple things can lead to right now。

You have to have some discipline that describes what the result is going to be in the life of concur。

😡，And generally， the answer is going to be that。We're going to make very weak guarantees。

 which are approximately useless to a programmer。Or we're going to make very strong guarantees。

 which mean that approximately we're going to move at the speed of thelasses。😡，In the winter。

 a day like today。Right because then we're going to have to go through the overhead of synchronizing access。

So we can't really unify that memory model without imposing significant performance constraints。

Especially when you're talking about something like a GPU。

 you're not talking about having two processes arbit for a bus。

 you're having to talk about a huge number of processes arbitrary for a bus。

Especially when you utilize these SMs are composed of many， many cores。

You guys know the drill on the kuda， we already talked about this。

 the CU file contains a mix of both stuff for the host and stuff for the device。

 I mean look you can take know the Kuda compiler and you can compile host code you can go back and like recompile your 213 stuff with that。

It makes postcode just fine， it just also makes thecode and it understands the extensions that let you integrate the two。

So if we go back and we take a look at our。This是不可能。嗯。

Transforming this is really not very hard Someone walked me through with this chunk of code sets。😡。

You were guilty。Unfortunately， I'm not going to pick our you rate。And you see， there's a chair。

pick got two people for the price one。What are you guys walk me through。

 What do you do guys walk through？Like I he X dot Y times Y dimensiont。Plus thread IX。

So let's focus on block dimension。Let's focus on block ID time。我就在。不要彻底我。Here sorry。ちすを。O。

So what you're suggesting to me is that back in 213。

 we talked about how we project the two dimensional array for one dimensional memory。Did规。冷气。

You didn't work for too also。You거不可거。かた。夢ざ。都没得。でて。Okay。

So you talked earlier earlier in your career when it was 122 or 213， whatever you did， right。

 you talked with this idea of projecting a two dimensional array to one dimensional。

And we said it's real major work， and I'll show you in the pages of the textbook。没 okay。Now。

 remember that when we try to figure out like we're in memory。😡。

We' in the one dimensional memory wise？嗯。Something was we had to look at that two dimensional representation and say。

 okay， what row is it in？If it's in row 10， we have to begin by going to 10 times the size of a row。

😡，To skip past 10 rows to get to Ro， zero， first second， third four foot， six，7，8， nine。

 now we're at the beginning of row 1。Then we added in the Y index。佢啲で。The column index。

To get a specific yellow， right？So now when you look at this。Block index。y times block dimension。

y plus thread indexdex。y。Does that remind you of something？Maybe row index。

Times row size plus column index。This is just the row major computation。😡。

So when we say we say is I equal why all we're doing。Finding the linearer address of I based upon。

而是咧。And so what we're doing here is we're finding I and J。

Based upon their two dimensional row and column。😡，X and y。Indexes。

In the one dimensional space that we're using here。We're just linearizing。Thattter address。Okay。

And from there， this code is doing exactly what the other code basically did， right？

There's really no magic here。You为等你实这么 dream表。If I is greaterd equals to n or J is greaterd than equals to n returns。

Make sure that we don't step out of the way。So now。

We come over here and we actually launch the kernels remember you the three angle brackets。

 that's a launch， that's a kernel launch。😡，Okay。嗯。And so if you take a look at that， right？

Threads per block。Right， blockss。And then we launch it。Now， we said that you don't want to sit there。

 know when you need to round these things up。😡，And you don't want to sit there and include that code and everything you do。

 and so we have this inline function updated。😡，And you can see updated views there。

And that's just going me the division rounding up。It should be a multiple of 32。😡。

I am now officially an evil person。😡，I have said it has to be a multiple 32。

 but I haven't reminded you as to why。😡，Somebody remind me， what is 32 in Kuta？

There are 32 something things。Was that。It's the warp size， it's the warp size， that's exactly right。

Okay。😊，So when we take a thread block， we break it up inside one of these streaming processors。😡。

And we actually handed to a core。The warp size is what we're handing off。😡。

And we need to be a multiple of a work size。So that's why we have 32。Now what a maximum value of 1k？

Right when the streaming processor gets a chunk of work。Okay， a block。

 it then takes that block into warps and dispatches the warps。😡，It can't dispatch a single thread。

 it dispatches a work worth。😡，Does that make sense。Technically speaking。

 the warp is the instruction and the data is in the associated memory。😡。

But it's not a problem if you abstractors work to include the data because that's the model。😡。

So we basically have this whole hierarchy， right we you know we take our work and we break it into these blocks。

 and we call it grid。😡，And then we dispatch a block to an SMM， right。

 and then the SMM dispatches the slice of that block， a warp to an individual core。Yeah， we。

 thank you。Well， so I that is interesting， but remember that the concurrencies allowed within those processors。

Yes。There没 sense。Now check this out。😡，So now we've done really nothing but translate our code to Kuta。

😡，we have done intellectually nothing， we have simply sort of mechanically transformed our code from host representation to coupaform。

 right？😡，Go， go parallelism。You can't even distinguish。Our old performance from zero by comparison。

Nice。Right， I mean， just massively embarrassingly parallel stuff fed to GPUs is like magic。😡，那。

What's the difference between these two chunks of code？😡。

You can imagine if you'd like that there's a nested for loop there that walks through X and Y。😡，对。

They didn' even worry about what the consequences might be， what's the difference？X and Y。

X and Y are flipped。Okay， so like we're talking about。

 we've talked about row major ordering versus column major ordering。😡。

You remember back from 213 we played the game flipping X and Y's and saw a performance difference。😡。

So。Here。Theses two chunks of code obviously have X and Ys click。😡。

So they're going to be approaching this with a different you know walking through the rows and columns differently right in one case we're going to walk through rows。

😡，Getting us to columns， in one case we're going to walk through columns， getting us to rows， right？

Here's the performance difference between those two。😡，The green。

Is the performance we saw a few moments ago？The pink。

Is the performance we invert the rows and column？Why。In 213， this was easy to explain， right。

 because we talked about level1 and level2 and level three cache， right？😡。

AndWe talked about footprint and cash。But now we're a GPU， there's no level one。

 level two or level three cache。Why are we seeing column major row major ordering effects here？😡。

It' reallyally interesting question。So。Threads with the same value of Y are mapped to a single war。

The reads with the same value of y and consecutive values of x map the consecutive positions within a single one。

boom boom boom。When a single warp accesses consecutive memory locations。

There's no block to read or write， I'm sorry they do block to read or write。😡。

When a single warp access to separate memory locations， it requires a gather or scatter。All right。

 what is this talking about？Let's take a look。So when a single warp access is consecutive memory location。

They block Read or write when a single warf accesses separate memory locations， it requires a gather。

So。Read it。Gs and the work reference a single location。Readday， threads in the work， do a block read。

So a block read is when we take an entire block。😡，And we read it together。Next thing， right B。

 we're doing a block right， we're taking a bunch of consecutive values and writing them together。😡，嗯。

So the warp breeds right here are matching the memory organization。😡。

So things that are row order and memory are going to be written as a block together。😡。

Things that are column ordered cannot be written together。😡。

They have to be written and written and written and written and written。Does that make sense。

So we're no longer in a situation where we're worried about cash footprints。😡。

We're worried about how long it takes to do the reads and writes。

If I have a bunch of data values together， I can do them in one right。

If I have a bunch of values that are separated。Value skip， value， skip， value， skip。

 value skip that takes multiple reads risk。电是咧。So when we talk about scatter mode and gather mode IO right in general。

 you know gather means take it from multiple locations and bring it together。

 scatter means take it from one buffer and put it in multiple places you see that terminology scatter and gather all over its systems。

 you see it in disscheduling and things like that， take one buffer have to put it in different places on disk。

😡，So the penalty thing we're seeing here is that if we're not row major ordered in terms of how we're using things。

We can't do it in one right。We're forced to do it in multiple rights， that is to say to scatter it。😡。

Do you see the performance impact between that？Multiple values， one right。Versus multiple values。

 multiple rights。Scattered。So when we broke the row major order in with our indexes within a war。😡。

It didn't change our cash but for。Speaker。It didn't change our memory， right。

 our memory is our memory， but what it did change is the technique by which those values had to be written。

😡，One at a time。Or altogether。So the warp read and writes match the memory organization。

So I think I actually startedutter a little bit on this slide， but never mind。嗯。

So in terms of optimizing memory instruction performance， right？😡，You know。

 if we do things in one chunk， right， we're going to be able to load them faster than if we have to gather them from multiple places。

 we're going to be able to store them faster than if we have to scatter them。😡，嗯。

We also want to avoid things we're competing for the same block of memory。😡，Because in the end。

 we had multiple threads and we have one memory。And so。Here's another picture。Transpose operation。

We can see kuda symbol， we can see couda transpose。

 and directly underneath that is kudos symbol and burdens， those two are sort of blending together。

So in thinking about Kuda， you really do want to keep in mind how it's organized。😡，Right。

 that if we take a look at one of these things， we have our shared memory right the you know and then we have you know all of these simply functional units basically。

 these things。Right。嗯。So in terms of the block hierarchy。

 we said that blocks have to be greater than or equal to 32， right， and less than or equal to 1024。😡。

And there need to be multiple authority check。嗯。within block synchronization。

 is going to be via asynchronous。Each block is implemented a set of warps， 32 threads per warp。

Single instruction， multiple threads that guarantees they stay synchronized， so what does that mean？

Single instruction， multiple threads guarantees they stay synchronized。

So if I'm dispatching processors， if I'm dispatching different works。😡，Across those wars。

 there's absolutely no coordination， but within a warp what's happening？😡，かです。Simdyian。你嘅 object。

Okay lockstep is the word that is exactly the word I was looking for right so when we dispatch multiple wars。

 those wars are independent in terms of execution， but within a single work。

 they're in lockstep so there's no synchronization issue there。😡，Because it' hardware。泡沫是一样。

So we localize computation within blocks， each performs a sequence of tasks。

 each uses shared memory and local synchronization。So now we're going to continue to optimize this。😡。

In our first approach of this， we took basically the matrix as a whole。😡。

Now what we're going to do is we're going to block this matrix up。

 and this technique should be familiar to you because we talked about something very similar to this in 213 for cash performance reasons。

😡，So we're going to generate results on a block by block basis。

 we're going to localize the accesses to A and B and not be multiple blocks of the block side。

 okay so what are we talking about here？😡，嗯。The goal here is to break these things up into individual blocks。

😡，With the hope that by doing that， we're going to be able to keep our accesses within a block。😡。

And reduce the number of reasons rights。ok嗯。And need not be a multiple of the block size。

 meaning it's okay if the last block is't full。😡，That doesn't actually break it。

We already determined that pre transpose is great， so we're going to continue to use pre transpose。

 right， nothing there is going to change。So we're still going to be doing row wise operations。

Soend the block size8。So here we go。嗯。We blocked this just like we did in 2013。😡。

If you want you can take a second to look through the code。

 if you want to study this in more detail and it's probably worth it。

 if you look inside the standard directory AFS CS academic class 15418-S18/p。

 you're going to find recitation free and you're going to find the code for this all there。

And is probably worth a few minutes after recitation to look through。

And make sure it makes sense one thing I learned is that reading code to people doesn't generate any actual learning。

嗯。And so。Sort of here we go。Now， notice I went to my block implementation in my host code。😡。

Before I did anything with Kuta。1。And we were writing coup to code a minute ago。

 and now we're back to writing host code。😡，Just regular good old fashioned 213 Stcy coach。Why。

Comation that you think is more likely to be。Yeah I have a reference implementation right I mean we talk to this sort of the beginning of the class you want to have a baseline right so I want to have my original version of this and I want to prove my blocking algorithm is correct。

😡，I I want to compare those too now once I know my blocking algorithm is correct。

 now I can you know rewrite it for couda。😡，And compare the results again。

But I don't want to sit there and parallelize something that's incorrect。😡。

If I don't prove that my blocking strategy works， I might as well be。You know。

Just paralyzing nothing because I could get to the end and have the wrong result。Like I said。

 that's how an isolated to learn in the hardware。So we're climbing up the。Added while we're at it。

 fast block with pre transpoposedse and unroll the inter loop eight times and reassociation。

You can tell Randy wrote this code。All tricks apply。

Except those you didn't think he could explain to me， you probably let those out。Okay。

So now we have a blocked version of this。Right。So' going to use now we're going to make it work with Ka。

 so we're going to use one ka block for reach each block to the destination matrix。😡，Okay。

 so we divided up our actual data into these blocks in our code。

 and it obviously makes sense to represent those blocks with thread blocks。

 so that's what we're going to do。😡，We need to have enough of these k of blocks to cover the result matrix。

Each thread in the block accumulates a single destination value right because that's we want to do。

 we don't want to do large amounts of work in threads right the idea is that each thread does a little work in massive parallels。

😡，So each thread is going to accumulate one value。One value within that block。

 one block within that matrix。All right。And since here we see this， this is our kernel。

 it's declared as global， we can see the index computation as much as we did before。😡。

We can see our blocks our sub matrices， right， sub a， sub B are shared。

So these things are going to be on the device， on the GPU board and used by the multiple threads。

 and then we go loop over that and do our work。Just like our old school 213。

So with any each of these threads。Within each of these loops。

 these threads are going to play two different roles。

 they're going to fetch the element from the source memory right。

 and they're going to compute in a value， they're going to have to do both。😡。

They can't do the computation until they read the do。Now at the end。

 we're obviously going to have to synchronize to wait for this to be done， right？😡，嗯。And again。

 we always want to check the ranges， right？And make sure that we're within range because at some point we have a block that's not full and unless we check。

We're going to do bad things。And remember， those bad things are not defined in Pa right and see we understand the memory model。

 we understand what happens if we go past the edge of an array。

 we understand the types of results we're likely to see。So on。

 right here we really don't know what's going to happen。

 that's just totally the model for that is not something that's exposed to us。😡，The computer block。

Wow。😮，That green bar was our first coie implementation。That thing on top is our new implementation。

So what we have here now is a combination of。213 strategies and new Kuda strategies， right？

We started out with a simple implementation， and we did sort of the nickel fix。

 we didn't think we simply converted to kuta。😡，Beautiful， that generated a dramatically good result。

 right， because that line we can't distinguish from zero。😡，Right， was that original implementation？

I'm sorry， actually that last line we can't distinguish from zero was our blocked implementation。😡。

So our original PDa implementation involved almost no thought。😡，Right， was。You know。

30 or 40% of the way to the final solution， way better than anything we did in 213。😡。

Then they went through the 213 process， right， and generated a block solution。😡。

And then turn that into a coa solution， and now we see， you know we're dramatically better。Now。

 again， the performance improvement we're seeing here is not related to a cache。😡，In 2013。

 we do is related to cash。Now the performance improvement we're seeing is related to those access patterns。

 scatter versus scatter gather and contentious memory。嗯。Just to show it that new line you see there。

 first， second， third from the bottom。😡，This one。That's what happens if we mess up the indexes。

And we now have to scatter and gather。What's wrong with this code？Take a minute and figure it out。

一事嗯。Continues getting create。Stread dirgence。It cause some threats to。Okay， so explain that to me。

We want to be able we have these 32 elements operating in a war。Yeah。

 I want them all to basically be doing the same。Or if they're doing something different。

 we want to be able to just kind of skip that operation， sort of mask it。不建你。Continuing me。

Some threads go up to the top of the。And they're basically。Well， maybe it's secret。

What of thoughts do we have？Yeah尾。Gs over all the。The continuous skips over。Wei。え。

The underscore underscores。Sychthized， what do you mean by that？Well， I think you're。

 I think you're on the right track。 And did I just。Trouble figuring out exactly which are。

We don't need to worry about anything outside the foret loop。

 the problem is right here in the foretlift。I think I get what he's saying。When you continue there。

Never going to。Synchronized operations。Will'll never finish。Sized isn't div by N。Okay。

 so if the size is greater than equal to n。Or J is less than or equal to n， what does that mean。

 that means we're out of bound right， that means we don't want to do that computation。

So those threads are finishing。And。They're not being synchronized。Yeah。

 which means they're never going to hit the barrier。Pas the may here。Well。

They're never going to be waiting in line that。😡，I'll give you that。Okay。So what？They you' right。

Get to the third point here。the they're not going to get to the barrier。The rest of the program。

 the other threads are also going to get past the barrier， nothings going。 Yeah。

 that's exactly right， right， so for firstly make a past barrier all threads have to get to the barrier and that thread sink is not part of their code。

Yeah。Okay。嗯。So observations right understanding what the Kuta hierarchy is。

actually can really help our optimization， right？You know， shared access to fast memory。

 the impact of scattering gather mode， lightweight synchronization。And so on。

So the standard apply advice here is going to apply over and over and over again， get it right。

Right optimize from there right so you want your first implementation of anything。

 I repeat this I think five times this lecture。😡，Is to have the most expressive implementation you can。

😡，The one that's easiest to debug and easiest to understand and best articulates what you're doing。😡。

From there， you want to benchmark to know when you start。😡。

You want to know where you spend your time and you want to optimize based upon that。

And then you start want to move step wise， right， checking each time against that。

To make sure that you're correct。嗯。Watch out forization button like we just saw。嗯。

Watch out for memory referencing things right look， memory is really slow。

 computation is really fast， you can waste a lot of computation。

 you can compare X to y a million times and it's not going to matter okay but if you mess up a memory access or mess up a bunch of memory accesses。

 that's going to bite you first。😡，It's not checking the balance that's going to cost you any significant amount of time。

 it's doing a gather operation when you can avoid that or doing a scatter operation you can avoid that。

 or contending for memory when you can avoid that。😡，嗯。

So camemon was an alum was the prior instructor of this， he's now I think at Stanford。

 which is where he got his PhD， but here's another little picture。Okay， rememing with F fours。

 quad blocks。We stepped it up again。嗯。So we read four elements from A， each red loop 16 times cut。

Why is this faster because we're able to make better use of the memory bus？😡。

The bottom line is if we can break this up into from using single values to using groups of four。😡。

We're able to get a higher memory throughput。And memory。

 you know' if we're keeping our processors full， doing computation。

 and we are what we're dispatching is all these things， memory tends to be the bottleneck。



![](img/2ebb25f04bd8badbeb583e5e94c95f7d_1.png)

![](img/2ebb25f04bd8badbeb583e5e94c95f7d_2.png)

Okay， so when we come back， I guess I will see you again a week from today on Friday。

 Randy's teaching Monday and Wednesday， we'm going to go through a whole bunch of optimization examples then。



![](img/2ebb25f04bd8badbeb583e5e94c95f7d_4.png)

Any questions for break？Have a wonderful weekend， they warm out there？

