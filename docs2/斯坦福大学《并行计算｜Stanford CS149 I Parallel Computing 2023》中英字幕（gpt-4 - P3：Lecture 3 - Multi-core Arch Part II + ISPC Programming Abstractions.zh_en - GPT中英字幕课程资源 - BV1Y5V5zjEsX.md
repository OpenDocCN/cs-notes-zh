# 斯坦福大学《并行计算｜Stanford CS149 I Parallel Computing 2023》中英字幕（gpt-4 - P3：Lecture 3 - Multi-core Arch Part II + ISPC Programming Abstractions.zh_en - GPT中英字幕课程资源 - BV1Y5V5zjEsX

![](img/905dffa7f6f91f5050a8c9220a43732f_0.png)

Welcome week too。

![](img/905dffa7f6f91f5050a8c9220a43732f_2.png)

How's the week。49ers remain undefeated。Giant season is over。く。😊，Alright， yeah。😊，Yeah， exactly。

 So just as a reminder from last week on Tuesday， we had this pretty。

Pretty substantial lecture where we talked about three kind of big ideas in throughput computing。We。

 we talked about multi core execution。 We talked about SMD execution。 and at the very end。

 we started talking about another idea called hardware multi threading。

 which again happened at the end of the class when people trying to get a little tired or something like that。

So I want to really review the hardware multi threadreading I'm going to start with。

 I'm going to review big concepts from last time， and then we're going to go into the back half of the lecture。

 We'll actually talk about ISPC programming， which is the language that you do a lot of your work in assignment one in。

 not for the purposes of teaching you a language， but to underscore some of the concepts from last time。

Any questions。If not， let me pull up the slides from last time。

Where I had a figure up that looked like this， okay。

So that last 10 minutes of the lecture last time had one very simple idea in it。Which was。

 if you are waiting on something to happen。You go do something else。That was the whole idea。

The the first part of the lecture was largely about。Adding more and more units to the processor。

 This last section was about making use of those units。More efficiently。

 So I closed with a diagram that looked a little bit like this。 I said， we。

 we introduced a Simdy core。You know， a a processor that can execute in this case。

 one instruction per clock， but every one of those instructions is doing8 things at once。

 the same 8 things。 So it's like adding two8 wide vectors or something like that。 Give my diagram。

And， and we talked last time about what does it mean to execute instructions。

 And you all told me that when I run an instruction。

 the result of that is going to be reflected in the change in the value in some register。

Or maybe a change in value in memory。So running a thread， running an instruction stream。

 says I have my state over here， which is like the state of all variables。

 And then I have operations or instructions which change the， the results of those variables。

So then we said， well， wait a minute here， if I'm trying to run operations and I can't do that next operation because I'm waiting on something。

And what was the biggest example of what we might be waiting on in class or last class？Yeah。

We were waiting on memory to， to respond to a request， which could be hundreds or more of cycles now。

Generalize that thought to waiting on anything， right。

 It actually could be waiting on some previous operation to complete。

 like doing some complex math instruction。 But we introduced this idea of waiting for a very。

 very long memory request。So the big idea is that instead of sit there and wait。

Go work on something else。So if this blue box is encapsulating the state of all my variables for a thread。

What I did is I just added more blue boxes to the processor。 I said， well。

 there's no reason why if I I'm not going to change any execution capability。

 This processor can still only do one SD instruction per clock。

But I'm gonna go ahead and allow it to manage state for four threads。

So now when one thread can't make progress when I can't do that next instruction， boom。

 the hardware just switches to the next instruction for the next thread。

 And whenever there's a stall like this， it doesn't waste any time。

 It just moves over and it does something else。Switch on stall， Switch on stall， Sw on stall。

 Sw on stall。 And at some point， maybe it gets back when this data is ready。

 It comes back to running this thread。😊，So in my diagram， time is going down here。

 down the vertical axis， the threads 1，2，3，4 on the diagram。

 And I have these8 little columns inside each thread to indicate that they're issuing S vector instructions。

Okay。So how many instructions is this core run per clock。1。

That instruction is an8 wide vector instruction in this diagram。

How many threads does it run at any one time。1。What is the utilization of the processor。Hundred%。

 if I go to any point in time and I say， is something running。I will conclude that the answer is。

 yes。Now， what's the cost of this idea， which， by the way， was， was you know。

 largely invented by Kumi。When was the first。I mean， I guess there was。

 there was all the U dubb stuff with Intel。 and then there was but they weren't。

 they weren't really doing this， right， So this was Niagara and what was was was your startup before Niagara Ni。

哦，O有。Okay， so now keep in mind that there's a cost。

 One cost is that I have to burn some more chip space to hold all these execution contexts。

Another cost is that。Every one of my threads。Gets done with what it was supposed to do a little bit slower because it's sharing this processor with the other threats。

So， so I， I want you to keep that in mind。 We are at 100% utilization。

 We cannot get all the work done any faster。But any one of those pieces of work。

 any one of those threads will be sharing the processor with other threads。

 So the amount of time it takes to do one thing is actually going up。

So if you had a very latency driven application， you might want to do this。And this cost is。

 you know， the cost of this storage， you can kind of think about it as like。

There's a fixed amount of storage on chip that I can dedicate to these execution contexts。So。

 for example， I can take that fixed amount of storage， and I can say。

We're gonna have a bunch of execution context。 I can interleave a ton of threads。

 like 16 threads in this diagram。 But every one of those threads is only gonna have a pretty small register file。

 small amount of state。 Or I can divvy it up in other ways and say， look。

 I want threads with a lot of registers。 A lot of access to local state。

 but I want a little bit less ability to go do something else and so on。😊，So here's my new core。

This is a core that in this class， I'll use the term hardware multi threaded。

 It means the hardware has the ability to run two different instruction streams or has the ability to maintain state for two different instruction streams。

But this core， as I've drawn it， can only run one instruction per clock。And in this case。

 I've actually redrawn it to be a scalar instruction。You can see from大噶。So single core processor。

 multi threaded core， can once one scalar instruction per clock。From one of the threads。

 So the hardware， every single clock tick is going。 All right， which， which。

 which thread should I run， I don't know， I'll pick one of them that's available to run。

 I'm gonna take the next instruction from that instruction stream。

 And I'm gonna tell tell my execution unit to do it。That's how the ship runs。 Okay。

 there's a question。Poly in the previous scenario。W withす。Secondly， I was this out。

Let's say there's 15 students at office hours gonna ask me questions tomorrow during my office hours。

 which， by the way， I had to move because of a faculty meeting conflict to 11 AM tomorrow。

 Just see note。 So announcement， my office hours。Imagine that I have 15 students there。

 and I give them a bit of a hint。 And then I tell them to go think about it。Okay。

 imagine that when you go think about it， let's say I just SAT there and waited for you to think about it。

 And then you came back to me and we itd on this。 And then I went to help the next student。

You would get out of there earlier。But I would be very inefficient。

 All the other students would be pissed off because they'd be waiting。Imagine I tell you。

 go think about it and then get in the back of a line。Right。

 so then what's gonna happen is I'm constantly asking questions。 I'm 100% utilized。

 You could make no better use of your professor。But you might， if you have a couple of follow ups。

 you may not get out of there for a while。If my goal is to get you out of my office as quickly as possible。

 I'm gonna sit there and wait， and I will be inefficient。

 If my goal is to help the most amount of students in a fixed amount of time。

 I'm gonna interleave you。That's what I mean by any one student is slower。对。

So let's think about this little。 Here's a diagram。

 Now I flipped the direction now I just because I need with time is going this way。

 These are clock cycles。Now， imagine I have a program here， which says。

It's going do three math operations， and then it's going wait on memory。Okay， and let's just say。

 can't make progress until that comes back。 Okay， so it's gonna do three math operations。

 which I'm gonna denote here。 Not that blue indicates the processor is busy running thread 0。

And then there's going to be a memory operation， which for the sake of this slide。

 I want you to think of as 12 cycles of latency。 so time again is going， going this way。

 I changed it up。Alright， so here's the question。 Let's say this program repeats over and over and over again。

 You know， I can get going again and it stalls and so on and so on。 right， So this makes sense。

My question is， you know what is the utilization of the processor？

I guess I can draw it all the way out for you。在。You just got to count， right？

I do three cycles of work， and then I wait for 12。So out of every group of 15 cycles。

 I'm doing three cycles of work。So 3 out of 15， it's one fifth， right， So I'm at 20% utilized。Now。

 let's think about what happens if I had another threat。So now this core can， it says， well。

 thread 0 can't make progress。 Shoot， I'm gonna go ahead and run instructions from thread1。

So we get three instructions from threadread1， then thread1 stalls。And so on and so on。

 So now what's the utilization of my processor。You know， I doubled。

 right because now I can kind of do three instructions from you and three instructions from you。

 And then I gotta wait till some stuff comes back。 and then I get going。 Okay， Allright。

 so now with your， you know， your best friend sitting next to you， I w to know， talk this over for。

 for 1520 seconds。 How many threads do you need if you want 100% efficiency on this program。😊。

How many threads do you need。嗯，就不是。系呢三。Look at the pattern。

I'm doing three units of work every 15 cycle， three plus 12 stall， three plus 12 stall。Okay。

 what do you think？Anybody want a volunteer answer？How many threads？Why did you say five。

 that's the correct answer。到没有。1 over one fifth， okay。Or， yeah， you can think about it that way。

 Another way to think about it。 The way I like to think about it is how much if I。

 if I have one thread in it stalls。How much latency do I need to cover。

I need to cover four cycles of latency。And in this program。

 every thread gives me three cycles of coverage。So I'm gonna four additional threads to cover that gap。

Right， so I'm gonna need the 1 I just installed on plus four additional threads to be runnable to get to five threads required for 100% utilization。

Okay， so here's a question。 Now， imagine that I move to a processor that can interleave8 threads at once with the same program。

How much faster do I run？Talk it over。All right。What do you think？And really。

 I was a little cavalier in saying， how much faster do I run。

 I probably should have been more specific。 I should say。

 what is the utilization of my processor or what is the rate at which I finish things or get stuff done。

Am doing any better than before。Yes，100%。 I mean， I was already running it 100%。

 And now I'm gonna have， let's say， a bunch more threads in this case。 I guess yeah，8。

 I have like 7 other threads to cover the latency this stall。😊，By the time that memory gets back。

 like， I only need it， like you told me last time， four other threads。

 a total of five in order to cover that stall。So what。You know， would you build。

 if this was the only program you ever had to run， Would you build an8 way threaded processor。

 Probably pretty inefficient because you'd end up burning more chip space to store these execution contexts。

 And every single thread would have higher overall completion latency。

 because it's sharing this one resource with， with more and more threads。

Now let me change this a second。So now I change the program， not the computer。I changed the program。

 So there's six arithmetic instructions followed by that， by that memory access。Now。

 go tell me again， Take care of 30 seconds。 Tell me how many threads you need to run at full tilt。

 full utilization。And by the way， first， convince yourself， I'm currently running at 33% utilization。

So you've got to hi a6 cycle stall or sorry， a 12 cycle stall。

 How many threads do you need if every thread gives you 6。You need two more threads。

 so you need a total。Of three threads surrounded 100% utilization。 So this is kind of interesting。

 right， Like the ratio of math to latency。😊，Is what determines how much multi threading you need to run at peak Uization。

 So if you have programs that have a higher ratio of math to memory latency。Then you have。

 then you have the ability to get by with fewer and fewer threats。Or equivalently， you know。

 if you build a big data cache， a data cache might absorb some of these cache misses and actually bring in your memory access time。

 right， So big data cache probably means you need fewer threads。 If you take out the data cache。

 you take more misses and you actually need more threats。😊，Okay。

 so takeaway number one from the sequence is we haven't added anything to the processor in terms of what it can execute at any one time。

 We have given it no more peak throughput。However， we've given it a new mechanism to be able to utilize those resources more efficiently。

Okay， and yeah， and we talked about how this is about hiding the effects of memory latency。

 Keep in mind that we haven't reduced memory latency at all。 It was always 12 cycles。

 We were just hiding its effects。 We were just not stalling when we were waiting for that， Yes。

This is。please that if we wanted to compute like the theoretical and max benefit of additional hardware trends。

😊，Then we could imagine a case where there's a lot of cash cashes and you're waiting around a lot and then perhaps it cleanly divides the workload。

 but you might be in a setting more that not the case as we just sell。

So if you want to think of like a theoretical max。Well。

 the theoretical max would be 100% utilization。And then if you wanted to know the speed up due to hardware multi threading。

 you'd have to know the speed of only running one thread at a time。Okay， so the two numbers are。

 what do I measure when I do one thread at a time。And then given what I know about what the processor。

 if I just look it up in a book， what this processor can do per clock or estimate it。

Multi threading might be able to get me close to that high watermark。I'm going take your question。

 and then we're gonna iterate on that just a little bit more， yes。

It only take one cycle to go from one thread to another' just for the sake of this class。

 let's just assume that mean you should just think about it if you're familiar with underlying processor details。

 all it's doing is switching the current PC to another PC。Okay。

 so there were three ideas from last time， Multi core， Sdy and multi threading。

 And then the first class actually had superscalealar。 But let's think about it。

 So here is a fake chip。 It has 16 cores。😊，Every core is single thread is is is four way threaded right now。

 So if I have a program that creates 64 threads。Those threads will just get distributed to those 64 execution contexts。

Every single one of these cores， independently， every clock is picking one of those instructions from one of those four threads to go run。

 and those instructions in this case can be8 wide vector。😊，So if I need 6，64 threads。

 each one can be doing eight pieces of data at once。 If let's say we were processing array。

 like computing the sign of all the numbers， I would need 512 independent things to do。

 A of at least 512 to run this thing at peak rate with maximal latency hiding ability。

That's what I want to make sense to you。No， like， if you look at this， you might say， oh。

 this is a 16 core processor。 And I'm telling you。It has a peak throughput of 16 times 8。

128 execution units or 128 pieces of data can be processed in parallel。 But in order to hide latency。

 you better give it 512 things。This is all this put together。Now， you asked me a question about X 86。

Let me take one of those cores and give you a coursear approximation to what's in a myth machine。

Okay， a myth machine is a two way multi thread machine。It's also a traditional Intel core。

 which means it can run。In a superscalealar fashion， multiple instructions per clock inside a core。

So what this thing is gonna do is it's gonna get， it's gonna look at its two threads。 Now。

 my core here could only run one instruction per clock。

 So it had to pick a thread and then run the instruction。Would imagine you had a core， a core again。

 just talking about one of these things。 They could run multiple instructions per clock。

 which is what we used to call like superscalealar processors。

 So I have a couple of different execution units。And then I have two threads I can go grab instructions from。

So if I had to like cartoon out myth。😡，It might look something like this。It's got two。

 It's got two threads Intel likes to call these hyperthreads that it can draw from。And it has。

At least 3，8 wide vector A U and a bunch of scalar， you know， I plus one stuff that it can do。

 So in every clock， this chip is going。I can utilize up to three vector operations per clock from these As。

From those two threats。So in some sense， it can find a mole ad。 It can find another moleadd。

 It can find another moleed。You know， the details of this， you know， are not。

 you're not expected to be that precise on the assignment。

 So you can kind of just think about it as there's in general。If there were no vector instructions。

 it can actually do about three ALU scalar ALU ops per clock。With vector instructions。

 it can actually end up doing at Max about three vector operations per clock。

 So you should see about what speed up from vector。😊，Yeah。

 like my max throughput is about three scalar ops。And my max throughput is about  three vector ops。

 So if I move from vector to scalar， I， I could get up to 8 x。Now。

 it turns out that if you're just using one thread。You know。

 there might not be instruction level parallelism in the thread to find those three vector ups。

So when you throw that extra thread in there， the chip is actually going， oh。

 I've got two threads almost all the time。 I'm gonna have the three vector operations there to actually use。

😊，Okay， so you're gonna see a performance benefit from going from running one thread on this core to two threads on this core。

 because one thread is not going to saturate all those execution resources， yes。And what I just said。

 by the way， is if you now we're getting into real， like taking the basic concepts for the course。

 which I would like you to understand this diagram and then applying it in a much more messy real world setting。

 and if you can understand in that jump， you're doing very well。So this is a supers core， right。

 and it's a multi thread。SoAnd it's a Cimdy and it's part of a multith chip multi chip Yeah you're right I mean just again。

 I'm being very， very loose now but。Think about it as I have all these fetch decos。

All those fetch and decos are doing is they're running their， their superscalealar instruction logic。

To say， what independent instructions can I find in thread 0。

 What independent instructions can I find in thread 1。

I've got all these yellow boxes that I want to fill up。

 If I find a mixture of instructions across any of those threads that I can shove into yellow boxes。

 I'm gonna do it and try and saturate the machine。Yep。Let me go here and then here， yeah。

there key vector is how many。Inteructionions can contribute value。Well。

 if there are three vector AluUs， I'd better be able to execute three operations at once。

 otherwise I shouldn't have built these AluUs。Right， so if I。

 if I can run three vector opposites at once， how many total floating point operations am I doing。

Three times 8。 Yeah， and honestly， three times 8 times 2。

 if you count them as a multily a all in one thing。 So it's a lot of ops per clock。

How is having extra PhD for？Plo assets compared to the previous。

I'm just drawing these orange boxes to indicate one box per instruction that can get shoved in the pipeline at once。

You can just as well think about it as a fetch and decocode unit。

 That's a fancy fetch and deco unit that has the ability to dispatch multiple instructions。

 But at the end of the day， if you have a bunch of execution units。

You're gonna have to be dispatching more than one instruction per clock to them in order to keep them full。

 Yeah， okay。The same time。So， now like everything here composes。It's a multithed ship。

It's a simdy chip。 It's a superscalear chip。 And the implementation like superscalealar tends to mean finding instructions within the same thread。

 You should think about it this way if you're an intel architect and correct me if I'm wrong。

 They were sitting around with all of the yellow boxes in one thread。😊。

And they were having trouble because of the diagram that I showed you in the class of finding enough work in that one thread。

In order to fill up all of their execution units。So they just said， oh。

 let's just think about the second thread as a source of independent instructions。

And feed that right into my， my global scheduler because now I don't have to。

 I can assume instructions from two threads are obviously independent because they're in different threads。

 Yes， ma'am move that。ultous correct。 So it's also， you know。

 it's also a form of simultaneous multi threading， which you have two forms of simultaneous multi threading。

 You have different threads on different court。 And then you have this simultaneous multi threading inside a single core with the different threads。

😊，对。The tooth breaths were on this stage。An execution unit does one thing at a time。

So you could use it in this clock， and I could use it in a different clock。

 But the idea that we're gonna give two instructions to one one unit and expect to do two things in one1 clock is。

 is not feasible。 It's not what the hardware does。Yes。

So the In selection box is basically finding seven instructions across two thread that it can really correct。

Now now don't quote me is that that's exactly how Cay Lake works。

 like I tried to read the reference manuals as best as I could， but maybe it's six， maybe it's eight。

 maybe it's you know， but you。That seven fetch equal equal。We should move on。 This came from。

 this came from me reading the Intel instruction manual。And。Some of these instructions。

Our longer latency。So you can get by with lower fetch capability by saying。

 I'm gonna give this instruction unit instruction。 I know I don't have to fill it up for a while。

 if it's not fully pipeline。So we're， we're now getting into micro architectitural details that I actually could not even recite off the top of my head。

 So it's not true necessarily that you need as many orange boxes as you have yellow boxes to keep the the thing in。

 But let's take this one offline。Okay， two more。 And then we should she keep moving。 Yes， Sir。はいあす。

That is why we can fetch more instructions than we have execution。

Because any one thread can have independent instructions inside of it。

 There's nothing preventing a single instruction stream from having two independent multiplies。

On two different sets of registers， that's the idea of superscalear。

Independent instructions inside a thread that the chip finds for you automatically。なか。干死好老秒。You万か。そ。

Theeoretically， it doesnt mean。This I don't know what the rules of this specific processor are。

 but my conceptual answer to your question is， yes。

 if there was sufficient ILP in one thread to fill up the machine。You don't need two。Right。

 and in fact， in the early days of， of hyperthing。When that was actually the case， the。

 the threads actually started interfering。 like one would kick each other's data out of the cache。

And so you had the ability to turn off the second thread。 and it might。

 it would help on certain applications。 So threads can interfere。

 They're not always a positive thing。 Okay， let's get going。 And。

 and I hope that the next sequence will answer even more questions。 First of all， you know。

 this was my fake chip。😊，This is like what one of the cores in a modern Intel processor might look like。

 instead of 16 cores。 remember that like an NviDdia GPU has a whole bunch of these things。

 We're not going talk about it today。 But if I had to diagram the inside of maybe like one core of one of these 144 cores of an Nvidia GPU。

 it might look a little bit like this。And the way you can think about it is as。32 wide vector，4。

32 wide vectors per clock， drawing instructions from up to 64 threads per core。The numbers are。

 you know， the concepts are the same。 The numbers are larger。

 We'll get more into that when we talk about Nvidia programming。But the implication of this is that。

I need， you know， in the maximum latency hiding state。

64 threads per core times something like 80 or 144 cores times 32 per thread gives you something where if you want to fill up this chip with my cex example。

 you're talking about， don't bother unless you have hundreds of thousands of things in parallel。

Right， this is why a small DNA does not run well on a big GPU because there's just not enough work。哎。

O。Yeah， I think we've， we've gone over this a good deal。 So let me， let me。Go over one more review。

 one more time for everybody。 before we move on to the rest of the day。

Last time I gave you this program， this was just a basic C program。

We focused on running just kind of the inside of the loop。 these instructions， if we compiled it。

I told you that if I had a simple， single threaded single core processor。

 that processor would run run one of those instructions per clock。Very simple。

On the first day of class， I said that without you doing anything to your program。

 an architect at Intel could say， you know what， I'm going to look for independent instructions inside a single thread。

 I will find them for you automatically。I will execute superscalealar。

 And if your program happens to have independent instructions， like what I'm showing here。

 two instructions might get run per clock in the from the same thread from one core。

 I'm highlighting those instructions in orange。😊，I also told you if I changed my program。

If I rewrote it with C， S1，49 intrinsics or A V X intrinsics。

 or I had a compiler like IS PCC generate those intrinsics， the binary might change。

And it might be vector instructions。And if I had a processor that had a vector A U now。

 a vector execution unit， when I ran one instruction per clock， it would do 8 things。

 Notice how I only have one instruction per clock running now， one orange highlight。

 But that's a vector instruction。😊，There's no reason why I can't。Make a super scalar processor。

With different types of units， here's one with one scalar and one vector。And one thread。

 So this core is now kind of looking at the thread and go， well。

 if your program happens to have a scalar instruction that's independent from a vector。

 I could do both at once。But if I can't find a scalar independent from a vector。

 I'm only gonna run one of those two。Can't do two vectors at once。 Just don't have the hardware。

So now superscalealar with two different types of instructions。

Then I said there was this idea of multi threading。 Multi threading is just taking。The core。

I went back to a simple single nonve core and having two threads。

 And now if my program creates two threads， this processor can run each thread。

 notice each with a different current program counter。

 you can have the state for both of those threads on the chip at the same time。

 And because this core can only actually run one instruction per clock。 Every clock。

 it picks one of the two threads and runs the next instruction。

 So I'm highlighting one of those two instructions。😊。

I could also build a super scalar core with two threads， and on this particular clock。

 my superscalealar core found， to your point， two independent instructions。

 one scalar and one vector in this thread and decided to run them both on the core at the same time。

Perfectly valid solution。 if the execution engine supports that。Now， let me move to four threads。

And now the chip decided to pick one vector and one scalar from two of those four threads and run them on the processor at once。

 totally within my rules。Right，It's just trying to find work。And， of course， everything I have here。

 you can just replicate in your head across cores。 So now I have two completely different cores。

 Each is fourway multithreaded。 Each can actually do two a mixture of two instructions per clock。

 So my program better create 8 threads to fill this thing up。 And amongst those eight threads。

 four of them are mapped to these execution context。

 So the the core picks this vector and that scalar to do stuff。😊。

Instruction threads 4 through 7 are mapped to this core。

 And so this core happened to find a vector in a multiply here and fills itself up。Yeah。

I have fourth Freds running at the same time。You let me let me clarify。

 there are 8 threads that are concurrently live on the processor。 And at any one time。

 if it's possible for two of these four to be selected for actual making progress and two of those four。

 But it would not be possible for these four all at once to be chosen at the same time， right。

 because in other words， like， you should think about this side of the diagram or that side of the diagram。

 but never both。嗯。And here I've decided now， and now replace this core with something more like this。

 And you've got something a little bit more like a modern intel chip。 And if you make four of those。

 that's what you have on myth ish。😊，Any more cl。 Yeah，'s a reasonable a good rule rule of thumb。

 Yeah， unless you start doing complicated stuff。 but we're not to talk about that。 Now。

 let me just give you one little detail that we'll talk about offline if folks are interested。

 you know how I said， like if you look closely at my programs。 If it's a vector operation。

 it's here in the instruction stream， like a compiler emitted vectors。😊。

That's actually kind of how it works on Intel CPUs and maybe even Intel G。

 But NviDdia and AMD G work a little bit differently。It's the same ideas。

 But I just want to see this in your mind。They never， ever， ever generate vector instructions。

 They generate scalar instructions at all times。And the chip is designed so that let's just say。

 here's a chip with8 thread execution contexts。And under the hood， there's a single。

 It can do one vector operation per clock。Okay， now this is not this is just an interesting detail。

 So what they do is they have logic in the chip to say。

 if there are 8 threads with the same program counter。

I'm going run all of their instructions on this AU at once。

So the effect is the same as if the compiler had generated a vector instruction。 It just says。

 I'm always trying to run 8 threads at once。As long as all those threads are at the same program counter right now。

Okay， and we I can talk about that offline if you want a little bit of clarity， okay。

So last little question that people ask me， imagine that you write a program that spawns2 P threads or two C+ plus threads。

And we're running on a processor here that has two cores and two execution contexts per core。

What decides， what thread runs on what execution context。That's actually your O S。

 So when you create a thread， your O S goes， oh， we need a thread of control processor。

 start running this PC on execution context 1。Right， so that's the operating system。

 So that's the O S， right， And if you were implementing the O S。

 it would be an interesting scheduling decision to say。Which thread should I put on what course。

Because you know that these two threads share execution resources。

 Imagine if we only had two threads in the machine。Would it make sense to put them both on core 0。

Probably not。 Probably makes sense to put your first thread on core 0 and your next thread on core 1 so they each have their full complement of execution resources。

 Now， of course， that answer might be different if， for example。

 they were touching the same data and you wanted to share a cache or something like that。

 But but that's a pretty interesting scheduling decision。 Okay， so that was sort of。😊，A very。

 very deep dive into these concepts from last time， yes。

Theyre related to what's last point about scheduling。So if you have local execution further。

 it seems like there's also a discussion where sorry multiple A use。

 there's a decision where we could either run multiple hardware。Or run the superter。

 That's not a decision for the operating system to make。 That is a chip implementation detail。

 The operating system says， hey， Chi， you will run this thread on this execution context。 The chip。

 every single clock is now making a decision for given the execution context it has。

What instructions to select as completely out of the regime of the operating system。

 The chip is making that decision every cycle， billion times per second。 The operating system。

 if you have 100 threads or 1 thousand processors， is periodically telling the chip。

 Here are the8 that I want you to run on your execution context。 That is an O S context switch。

 and that might take hundreds of thousands of cycles， and that happens very infrequently。か。

Is there a way to be a compiler something for？Yeah。

 well operating systems have APIs for saying this thread goes on this execution no force is super。

're goingpro and timing not do。出進てて。I mean， to my knowledge。

 that's not something that you get to mess with too much。 I mean。

 you certainly can say I'm only going give you， I'm gonna turn off hyperthreading or something like that。

 That is capable， but actually mucking with the low level details of the instruction schedules to my knowledge。

 I don't know how much control you get over that。 Maybe at the bios level。

 but not not at a standard O S systems API level。Okay， here's a question for you。

 given what you know now。I'm gonna take your favorite nu pie program。Alloccate a big array， A。

 allocateoc a big array， B。Pytorage program， if all you care。

We're gonna do an element wise edition of these or multiplication of these two。EArays。

 let's say these arrays are like tens of millions of elements。 They are really big arrays。

Is this a good application to run on the types of computers that I've told you about， Yes or no。

Talk it over。 once you think about。And then we're going to do have a vote。啊，O。

I'm going to keep it moving， sorry for keeping the discussions a little shorter because we did a good QA。

So。Who thinks this is a great application to be running on machines that we've talked about。 Like。

 for example， what are some properties of it that make us think hey。

 maybe this thing is gonna run super fast。😊，Yeah。ctorize it's okay， so it's， first of all。

 there's infinite parallelism。 Let's say that there's a million element arrays or 10 million element arrays。

 And not only is there parallelism， there is vectorizable parallelism， right。

 because like this is going map to these Sdi operations really， really easily。 So we have。😊。

Way more parallelism than cores。We have vector parallelism。

 So not only are we going use all the ALUs， we can hide any potentially latency that occurs in making this this program。

Alright， so here's where we get to the next topic。 This is probably the worst program that you can run。

 Where it's like the worst parallel program that you can possibly run on any modern computer。

 And you guys probably all run this program 100 times a day。😊，Okay， so let。

 let's just think about this little。 Letm go ahead and take that invidia GPU。

 but think about myth or whatever。I have， yeah， in a V100。

 I have 80 of these like sort of SMM blocks and every block in it has 64。FP 32 A use。

 So I'm gonna multiply those two numbers。 I have 5000 multipliers in the chip。And at first。

 you're like， that's okay。 I have like millions of things to do， like no problem。

And this thing runs at about 1。6 GHz。 So if you just do the math。

That's a lot of data you're going to need。And this gets to something we haven't talked about yet in class。

 which is we've talked about latency。But we haven't talked about bandwidth。Okay。All right。

How many people lived up in San Francisco。How many people live down here now？

How many people have lived up in San Francisco and said， I'm going to live down here now。

How many people said， I wish I lived up in San Francisco。Very unopionated people in this classroom。哎。

So I've got a lot of friends that are a little tired of the fog in San Francisco。 So that's。

 that's them on 1，0，1， driving down south back to Palo Alto because like it looks like this up there during the summer。

 And it looks like this down here。😊，And I like wearing T shirts。

 So let's say that everybody wants to get back to the South Bay。So we got 101。And we got。

 let's just say that the distance between Stanford and San Francisco to keep our math easy is about 50 km。

It's not， but， you know， Matthew。 Now let's say we all drive on 101 at 100 kilometers per hour。

So simple question， how long does it take to get to Stanford？Takes half an hour。

That's the latency of when you leave San Francisco and you get to Stanford half an hour。

 So the latency of driving from San Francisco to Stanford， one half hour。Now。

 let's just say there's a simple rule right now because we like to be safe。😡。

Stay out of the way of these AVs。And we're going to say there's only one car can be on the highway at once。

Very safe。How many cars per hour get to Stanford。2 cars per hour， right。

 because like one car drives a Stanford。 That's 30 minutes， and then 30 minutes later。

 another car comes in。 So we get two cars per hour。 So the latency of driving a car is a half hour。

 But the rate， the throughput is two cars per hour。O。So， one way。

Let's say I didn't change the rules at all of how many cars can be on the road。

 How do I increase the throughput。Can't change the road。 Can't change the rules on how many cars per。

Sorry。Yeah， I can't change the road again we can drive faster， right。

 so let's say we drive two times faster。Al， so my throughput goes to what。4 my latency goes to。

15 minutes， right， because I'm dry faster， right so。Approach 1 is dry faster。 Now。

 let's say you can start now， notice that driving faster， reduced latency and increased throughput。

But driving faster has some limits。 You know， maybe it's dangerous。

 It's actually really inefficient because you get more wind drag and stuff like that。

 So there's a lot of reasons why you can't just keep driving faster。

Like we can't say that if we wanted to get everybody down to San Francisco， we want 1。

000 cars per hour， where everybody's going to drive at like 10，000 miles per hour。

So what happens if you can change the road？They do this all the time， actually。

So what does California do on 101 about every five years。They build more links。😊。

So now let's just say I'm back to my 500 kilometers per hour。

 my throughput is eight cars per hour because I get two cars per lane。

So widenning the road means I have increased throughput。But latency was the same as it was before。

 Latency， still，30 minutes。How can we do better？Let's say we could change the rules of the road。

 but we're not gonna change the road anymore。 That's as big as we can get it。 You know， it's。

 it's falling off into the bay on one side。Yeah。So now I can start using the road more efficiently。

 Like， I can think about the road as not one big thing。 I can think about it as a bunch of pieces。

And it's pretty clear that two cars can't be in the same part of the road at the same time。

 That's not allowed。 but we can definitely divvy up the road and drive bumper to bumper。

 Or let's just say for the sake of math， I space my cars out by 1 km。Right。Okay。

 so cars are spaced out by 1 km， which actually means one car is arriving at Stanford every。

Every 30 seconds。 And what's my total rate of cars per hour。Itll be 100 cars per hour。

If I got my math， right。 Yeah， yeah， one car every 1007 an hours。 That should should be right。

 I think that's right。Doubting myself for a second。 but yeah， okay。Okay。

 so this idea of using the road more efficiently， I can say， well。

 the getting to San Francisco is like taking these 50 steps。😡。

And I get through every one of these steps， like one， you know， once per。Every hundredth of an hour。

 every 30 seconds。No， it's very 120。 yeah， I totally missed that。Yeah， every 36 seconds。

 I I should have just said that if we space out by， no this is wrong。 no， that's right。

 If I space out by1 kilom and I'm going 100 km per hour。

 I am taking one of those steps every hundredth of of an hour。 And now that's， yeah， that's wrong。😊。

Okay， I'll fix that later， but you get the point。Okay， so。Build upon that other math。

 If I have four lanes， then I just get quadruple the throughput， right。So。

 let's get away from highway 1 to one for a second。

 And let's just talk about communication and assist。So I can talk about memory latency。

 and I can talk about memory bandwidth。 Memory bandwidth is a rate。

 How many things are completed per unit time。 So here's an example where I'm completing。

 I'm sending four squares per second。😊，And I know that's true becauseuse I animated it。

4 items per second。Now， the latency of any one of those items is about two seconds。

 The amount of time it gets from memory to the processor。I can increase the bandwidth。

By transferring two things at a time。The latency is still two seconds。

 But now the bandwidth is 8 items per second。So in a system where we're。We're driving back to back。

 or we're sending multiple things at a time。Which I'll introduce the term pipeline in a second。

 latency and bandwidth are decoupled。Latency is about how long it takes to get from memory to the core。

 bandwidthandth is actually going be a function of how wide your road is。

If you assume everything is bumper to bumper like this。You know。

 another example that we do all the time that I like to use in this class is doing your laundry。

 Imagine you have laundry and you have a washer， a dryer and yourself because there's three stages to get your laundry done。

 So I。😊，Divvyed up the road into 100 stages。 Now， I'm diving up laundry into three stages。 You wash。

 you dry and you fold。So if you had one load of laundry， how long would it take you to finish。

Bottom of the slide，2 hours， right， because it takes 45 minutes plus 60 plus 15 to foldge you close。

Now， what's the throughput。Here。Or let's say I wanted you to increase the throughput。

So if we just did one load to laundry and we did it kind of without ever sharing the road。

 we're gonna， takes two hours to do laundry。 So Im， my throughput is one load every two hours。

 half a load per hour。So if I said， let's double the throughput。 Well。

 you might just go down and hope for there's two， two washers， two dryers。

 You call your best friend and you're like， look。Still takes two hours to get my， my load done。

But I get two loads done in two hours。Which makes sense because none of us ever do one load of laundry。

 right， Like we just kind of wait until it all piles up。

 and we have several loads of laundry to do at once。Now， is this a particularly efficient way。

To get the job done。It actually kind of is if you're optimizing for latency。

 because I get two loads done in in two hours。But there's a lot of resources that go idle。 so how。

 how would you probably do this if you。If you showed up downstairs or in the basement somewhere and you had a bunch of loads of laundry。

 Let's say you had a ton of loads of laundry。Say like。

 we had like 20 loads of laundry to docause like we waited all summer or something like that。Yeah。

So when the washer is done， the use the washer is the next load。

Because remember the idea here is don't ever want anything to go idle。

 That's just the name of the game in throughput computing。 If anything goes idle。

 you lost an opportunity to make progress。 So we don't want empty places on the road。

 We don't want threads waiting to run。And we also don't want to wash it or dry or not doing anything。

So now I'm drawing this diagram of what's going on here。

 And so look at the know the X axis is time and notice that my first load。

 my laundry takes the wash is4 you three ticks，45 minutes。

 then there's four ticks for an hour and then 15 minutes。 so the latency of the first load。😊。

Is is two hours。So when can I start putting in the second load。

 Let's just say we only had one washer and one dryer。I put that second load in when。

Sorry how long after the start？45 seconds or sorry 45 minutes。 So at 45 minutes。

 I can start the washer， it gets done an hour and a half in。 And then what happens here。Yeah。

 like the laundry dish sits in the washer because the dryers not done。And let's just say that。

You know， like， at this point， I will go ahead and start the washer。 Let's say， actually。

 I take the laundry out of the washer， put it on top of the dryer。

And start the washer again immediately when the washer is done。Does that make sense？

So we all do anyway。And so what's going on in this diagram， I have two questions for you。 Well。

 my question is。What is the throughput at which we are finishing laundry。

We can do a load of wash every 45 seconds。We can do a load of。

 we can do a dryrier load every one hour。 What is the throughput of loads of laundry。One per hour。

But wait， I thought we could do wash at one every 45 minutes。It's going on， yeah。

I'm limited by the slowest link in the chain in the pipeline。

 right so if the dryer can only get down with one load per hour， that's my throughput。Now。

 why is the laundry here is。Is actually sort of I'm executing a load of laundry every 45 minutes。

So what's actually happening in this scenario。Where's all this laundry， All this wet laundry going。

It's actually building up on top of the washer or the dryer， right， because at this point。

 I've only completed like 1，2，3，4 loads of， of drying。 And we have more than that sitting around。

 So if we ran this for forever， this pile， if I just kept shovlving laundry into the washer。

 as soon as the washer was idle， this pile between the two would just keep growing。😊。

So at some point， I might say this is ridiculous。 I'm not gonna put new stuff in the washer until I take another load out of the dryer and can drain that pile。

 So at some point， there's gonna be a finite buffer。

 And this fast thing is going to slow down to match the rate of the slow thing。

 So here we have a latency of one load takes two hours。 throughput is now one load per hour。

 And we did that with resources of only one washer and one dryer。 not two wasers and dryer。😊，Now。

 we needed multiple loads of laundry to do this。You know。

 another analogy here is imagine you had two pipes。

 And if we ignore the actual physics reasons that if I push more water down one pipe。

 it speeds up then they may rate match。 But let's say I had one pipe that could do 100 L per a second before it burst。

 and another pipe that could do 50 L per second before it burst。 And I connect them together。

 I'm only getting 50 L per second out of the system。 right。

 I'm gonna run at the lower of the throughputs。 when I link things together。😊，All right。

So let's let's apply this concept to a computer。And let's say we go back to， you know。

 we go to a simple program that's like load 64 B， and then add add。Load， add， add， load， add， add。

 load， add， add。 Okay， And， and let's just say that the computer is executing one math operation per clock。

嗯。Something that's actually quite common is we haven't talked about executing loads in stores。 But。

 you know， I'll draw this time and we'll ignore it the rest of the class。

 But often it's the case that there's an execution unit to handle your load store that's in parallel from your math units。

 Like， you don't want to waste the clock of math to do a load in store。

 So think about it as a two- way superscalear。 And we can get 8 B per clock from memory。😊，Okay。

 so memory has a long， as has some latency。Oh， and then there's 8 B for a clock。

 So let's think about how this looks is like my， my laundry diagram， basically， right。

 So here are the instructions。 And here's time。 So in other words。

 here's loads of laundry and here's time。So let's say I start by doing two math operations。

 then I kick off that load， and then there's some latency。

 and then this blue bar are the eight cycles it takes。To get back a total of8 bys per clock。Because。

 oh， sorry， And then the， the other thing is actually， remember we talked about caches。Typically。

 we ask memory for an entire cache line。So when I say load， I really mean like， load a cache line。

Okay，So let's just say it takes eight cycles to get that information over the the highway。

 over highwayway 101 back to to my processor。And so we're just going to keep doing this and notice that at every point in time。

😡，The blue bar is working as soon as the memory gets done with the first load。

 It starts working on the second load。 So there's always something working。Now I can。

 if I'm doing load sorry like math math load， math， math load， that's like the washer。

 it's going really， really fast。And it's not and memory is not keeping up because memory is the long pole。

 It's like the， the dryer here。And at some point， there's so many requests out to memory。

 The processors like， I've filled a buffer。 I've got to stop。Okay， so in this diagram。

 I'm only gonna allow three outstanding loads。 I just chose that number。 So， so now。

 since the processor can't issue any more loads。 And next time it tries to do a load。

 it's just gotta wait。It's got to wait until memory gets done with something in order to shove that next thing in the queue。

Okay， and that' just gonna continue。 It's gonna be。 So when， when this thing gets back。

 the processor can make progress again。 Oh， I got my road back。 Now I can keep going。

And if we zoom out of this diagram and look it happens。This is what it'll look like。Math， math load。

Can't even issue my load because like the the， the request Q is full a memory。 Oh， one came back。

 Okay， now I can trickle another one in。 Oh， one came back later。 Oh， I can trickle another one in。

 So look at this diagram at every point in time， memory is busy。

 transferring data at the fastest rate it can，8 B per clock。😊。

But the processor is not busy most of the time。All of these sections are when the。

 the processor is stalled。So you can think about the processor， like these 5000 A OUs。

To do their work， they like need， they're gonna do a math off every clock。

 They need data for that math off every clock。So they're asking for all of this data。

And even if we build like the fanciest memory system on the planet like this modern Nvidia memory system that has 900 GB of bandwidth。

 It's insane。😊，If you do the math here， this thing needs 100  TBte of bandwidth。

In order to give the A L Us on this chip， the data they would need to actually do a math operation every clock。

Cause think about it this way。 We can do 5000 map math operations at 1。6 GBz。 So I can do about。

8 trillion math operations per second。Every one of those math operation needs 12 B， right。

 because it loads two arguments， and stores one。So if I can do 8 trillion operations per second on this chip。

I'm gonna need to feed it with about 100 terabte of， of bandwidth。

And the fastest memory system kind of on the planet。Is about one。So you've got a pipe。

 The math pipe runs it 100 times。The data pipe。So if you just think through this pipe analogy。

 it means if you run this code on a modern GP， and it's very similar if you run on a modern CPU。

 just kind of scaled down in numbers。This thing is gonna run at approximately 1% efficiency。

Standard numpie Add array to Add array。And。If that's the only thing you're doing。

 there's nothing you can do about that。Convince yourself that a cash won't help。

Cash has only help if you reuse data。I'm accessing all the data once。

I'm loading it perfectly through cache lines。 So every time I load a cache line， I read all the data。

There's nothing you can do。 The only thing you can do is change your program so that it doesn't do 12 B of memory traffic for every math off it does。

 y。This is a really important question， you said， couldnn't we set the prefeting？

Imagine if I had a magical memory system that had zero latency。😊。

But transferred data at 8 B per clock。Perfect prefeture。Doesn't matter。Convince yourself that's true。

 This is not a memory latency problem。This is， I'm trying to shove。

 I'm trying to extract water from a pipe at100  TBabtes per second in order to feed my。

 my hungry A L Us。 And the best pipe in the world can give me 1  TB per second of bandwidth。

 That's the problem that we have。😊，There's nothing you can do other than change your program。

Or wait till a new memory system comes up。So。In almost every program you write on these modern processors。

 the name of the game。Is manipulate this ratio of how many math operations you do for every memory access。

 every memory access you read。Every program you're write will be bottleneck by memory。

 regardless of perism。Unless you do this。Okay， one quick aside， a lot of students say。

 how can I do a floating point operation per clock？

The same idea of pipeing applies to an instruction pipeline。

 So when I say my A L Us can do one operation per clock。

I'm actually saying they can complete one operation per clock。Their latency might be higher。

 So here's an example where the latency of an instruction。 Maybe it takes one clock to fetch。

 get ready to execute， execute and put the results back in the register。 The same idea of， you know。

 again，'s like the highway 1，01 analogy。 when I'm talking to you about a processor that does one instruction for a clock。

 I really mean。😊，Complettees one instruction per clock has a throughput of one instruction per a clock because any latencies and stuff are all gonna kind of be hidden under the hood with。

 with smart scheduling and stuff like that。 So in this class。

 I almost always talk in terms of throughput。Okay， let's take a， big， deep breath and。Any questions。

这样。beあの。Bandth is a measure of throughput。So usually when I say bandwidth， I mean bys per clock。

I could have throughput in office hours of students per clock。right。

's just a measure of something per unit time， yes。How fast is like。一生。よさとござます。In general。

 the rate of processing increases faster than the rate of data movement。

For reasons that moving data is expensive。Like moving anything is expensive。

 So usually about every decade or so there's some big technology bump that changes the equation。

 but it typically is like one big catch up of bandwidth and then compute races away and then at some point things get dire and there's another big catch up in bandwidth。

双方多。We bloom it so much but bandwidth width and like why to make a 49。

That chip is not designed to be efficient to add two vectors。

If the only workload you were doing was add two vectors。

 you would take that memory system and you would rip out 99% of the ALs。Luckily。

 things like computer graphics。And machine learning do not have this ratio of one math operation to 12 B red。

 It's flipped around the other direction。 you know。

 like on the order of 10 to 20 operations per by red。

 and you start getting very close to that ratio of compute to bandwidth。

 So as a modern computer architect， the first thing you do is you would kinda say。

 how much bandwidth can I afford。And given how much bandwidth can I afford。

 you say how many A O U can I put in there to keep that memory system busy， given my applications。

Okay。Yeah， we're running a little behind， but that's okay。

 I think Thursday's lecture is a little shorter。 So we'll be fine。 Okay。

 so I want to talk a little bit about IS PCC。 Now in this class by design。

 you are one of the skills is， is go read the manual， Go figure it out for yourself。

 That is sort of by design， because that's what's gonna happen。 You you go to work。😊。

But I do wantan to say a little bit about IS PCC to help out a little bit。

 because it's such a great example of in this class many times when you come to office hours。

 I'm gonna say， I think you're conflating。 You're confusing。😊。

What the abstractions of a program mean？Which is like， when I read the code。

 what should the output answer be， What should it compute。From， or I'm， I'm confusing that with。

Some implementation， How is it computed， and usually in a parallel computing class。

 what order is it computed。What is done in parallel， What is not。So a great example of like。

 what you should always be asking yourself is what is the answer like， you know， what。

 what's the correct answer that this program will compute。And then you could say， okay。

 if I have to think about implementation， I should be asking myself。

 what is every part of the machine， every core or every thread， What is it doing it some time。

What work is it doing？So ISPC， one of the reasons why I give you this sort of fairly obscure。

 simple programming language to learn is that it just makes these concepts， in my opinion， very。

 very clear because of how low level it is。This is a language。 It's like people like。

 I can't find anything on on on Reddit or on a stack overflowca like there's probably like， you know。

 the number of users is all of you times the number of years of this class。

 plus like 100 or 200 other people that want to get really good performance out of intel chips。😊。

If you want to know why you get such great performance out of ISPC and can't get it out of C++。

 this is like an amazing blog post that underscores a lot about why it's so hard to paralyze arbitrary C code and why they invented another language。

😊，Okay， so here's our program from last time。 Again， for every element in array。

 compute the sine of the number。Now I'm going to rewrite the code in ISPC。Okay。

 so all I'm gonna do is I'm going to take this code。 This is C code。😊，Yeah， like。

 you can compile with GC。Here's the ISPC code。 So here's void main， which is C code。

 This is all C code。And then this is， I just took the function， and I did literally nothing。

 And I really now it's an ISDC function。OK。Oh， sorry， sorry。 I haven'。

 I haven't rewritten an IS PCC yet。 I just factored it out。 Excuse me。在在。So if this is normal C code。

 excuse me， I got one。If we're running main， there's one thread of control。

 One thread is running main。 And then when you call the C C function sine X。

That thread of control just jumps to Sine X， executes the logic sequentially when it gets to the return。

 it returns control on that main thread here and continues on。So it just， you know。

 it's kind of how we think about programming naturally and， in one thread of control。Now。

 I'm going to rewrite the right hand side of the slide in ISPC。Okay， so not much is going to change。

 It's really going to change only in the outer for loop。Okay， so I've highlighted a bunch of stuff。

 I'd like you to ignore the uniform keyword for now。 I don't want to get into that。

 Just assume it's a regular end。But look what happens here。

 So now I have a program that has access to two new variables。 One is called program count。

 and the other is program instance。Or index， Ex me。 program index。 Well。

 So what you should think of semantics again， now， now the meaning， you should say， oh。

 when my main thread in C gets to this IS PCC function， when it invokes the IS PCC function。

My thread of control doesn't start executing that function。ISSPC spawns a gang of。

What they call program instances。And they're very clear not to use the word thread here because you kind of have a notion of what a thread actually is implemented as in a real C program。

And here， they're just saying， look， there are。An entire gang of program instances and the number of instances you have is given by program count。

And the current index instance that is running is given by program instance index。 Ex me。

 So in this case， every single instance of the IS PCC program has its own copy of all of the local variables。

😊，Like float numerator index。And it does whatever the function says it should do。

 But that logic is conditioned on。 Maybe every instance well do something a little bit different。

Based on the value of program index。Okay， so let's say that I create。

 I say I configure IS PCC that I want you to create a gang of eight instances when we call an IS PCC function。

So it should look a little bit like this at the point of this call。😡，8 program instances are created。

 Every program instance gets a different value。 I'm going go back to the previous slide of of program index。

Every program instance， runs this logic sequentially to produce some output。

And then when all program instances are done， control returns to your regular C collar。Okay。

 so program count the number of simultaneously executing instances。Program index。 Which one am I。

Okay， so this programming model is kind of you'll see this term SMD。 It stands for single program。

 multiple data。 And the idea is that I've written a single program， a single IS PCC function。

 but its logic does different stuff， works on different data， for example。

 based on whatever the value of program index is， which can be 0，1，2，3，4，5，6 or 7。

 if my gang size is 8。😊，This is a point in which I want you to ask any questions about the meaning of this program。

 and by meaning of this program， I say。我。Does each program instance compute One good， actually。

 here's something I want you to do。Is talk amongst yourself， Tell me。

 tell your partner I have 8 program instances。 I have an array of size N。

 What program instance is responsible for computing every element of the array。

This gets the right answer。 When this IS PCC program， when this function returns。

 when all instances are done。For every input element in the array， X。

 there is a value correctly stored into results of I。 That is the sine of X sub I。

 The program is correct。Question is。What program instance does what。T。

'll let you talk about that for a second。 Yeah， if you have a clarification。

Program count is the total number of instances。 In this case， it takes on the value 8。

Program index is like my thread ID。Yeah。All right， I'm going to bring everybody back together so we can because I'm eye in the clock。

So who can tell me what this program does？😡，Cooperatively， I create a bunch of program instances。

But who does what？对啊。是中一致。こかで。Each program instance computes one array element。

 So let's think about this。 So remember， this is the program run by every program instance。

If I only have8 program instances and every program instance only performs one。后边。One every proveer。

AOkay， so tell me how it works。 This is sequential code。Like when you say。

 what does a program instance do， you just look at this code and you're like， well。

 it runs this logic。 So what does program instance 0 do。It has a for loop。

 It says for my current variable， I equals 0 to n。Compute the value of x you know。

 compute the signine of x sub 0。Put it in results sub 0。 And then what does it do。

And then the computer。program count plus0And then it just increments its loop pointer。

 That's just normal C code at this point。 It says， okay， the next iteration I'm responsible for 8。

 The next iteration I'm responsible for 16 and so on and so on。

 So if one program instance computes every8 item， how do I get the to overall the right result。

Like the other program is to at one。Yeah， so remember， this is happening。

In 8 different copies with different values of program index。And as a result。

 I am interleaving iterations or sorry， I'm， I'm inter interleaving elements of the array and sort of just passing them off round Robin to the various instances。

 That's just what I wrote。 I did that myself。 That's how I designed the program。😊。

I want to know if everybody can visualize that。Now， question。Yeah， so this is interleaved。

 So in other ways， this is like one way to think about it。 Inst 0 does these things。

 Inst 1 does those things and so on and so on。 And cooperatively together， we get the job done。😊。

Make sense。Okay， haven't said anything about implementation。Would it be valid。

 at least to some approximation if the implementation of this call was。

Call IS PCC Sine X on a thread for instant 0。 when it finishes。 Now。

 let's just call that function again and set the value of program index to  one。

Completely sequential。Does it compute the right answer。It does。 You know。

 why would you use ISPC if that was the answer， unclear。

Could the underlying implementation actually spawn 8 P threads。

 run that column on 8 P threads and come back together。The answer is， is， is yes。

 That's what I want you to all to say。 There's some slight little details on why IS PCC prevents that from an implementation。

 But conceptually， you should think about it like that。 I just spawn 8 different threads of control。

 I carried them out with different values of program instance。 And if I just run all eight of them。

 I get the job done。😊，Here's a different ISBC program。 I change the program。

 It computes the exact same answer， but does it differently。Now， what does every instance do。

I'll have you look at it offline， but if you look carefully。

 every program instance now does a contiguous chunk of the array。I change the program。

 still computes the same output。But kind of， there's a different assignment。

 So this is kind of blocked。 So this version of the program looks more like this。Co。Now。

 I'm not going to tell you which one's better。 I'm going to skip this。

And I'm going to tell you really quickly what for each means。

So for each is kind of an interesting concept。 So the two code， I， the two programs I just gave you。

 I said， here's a version where I compute do all the work interleaving。

 I wrote the program so that every program instance takes an interleaved next iteration。

 I gave you a different program that says every program instance takes kind of a block of them。😊。

I don't want to think about that stuff。I just want to tell ISPC， here's a loop。

It has iterations for 0 to n。 Don't care。 I'll tell you that they're independent。I S PC。

 you just go ahead and assign those， the iterations to program instances， however you want。嗯。

I don't care。That's what I've said here。So all I've done here is to say。

 I'm not going to manually assign anything to anything。 I'm just gonna say there's a loop。

That loop is going to get carried out by all the program instances。

 Some iteration is going get done by some program instance。 I don't care。

Let the system figure it out。 Let let the system decide for me。 Choose a good answer。

And what I'd like you to walk away with is convince yourself that all four of these gray boxes are correct and valid implementations of that pink box。

So in other words， I want you to be able to convince yourself， what does the pink box mean。

And convince yourself that if I was a compiler and change the pink box to any of these gray boxes。

It would be a valid implementation。 O， and I'll stop there。



![](img/905dffa7f6f91f5050a8c9220a43732f_4.png)