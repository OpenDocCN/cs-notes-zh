# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P19：-19-Lecture 21 - Dataflow Models.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

All right， it's 11，10， let's get started。So three announcements。

If you're not paying attention to your email， you might have missed this。

 but we need you to use this Doodle poll。To sign up for project mini presentations next week。

 I'm planning to come to all of them and hope to give you all some feedback and hope to see some great progress。

The second thing is that the cyber SIim tool that you guys used in the lab is still very experimental and in fact there are。

You know， a small handful of graduate students who are really making this a major part of their research and they're very interested in your feedback。

And so there's a survey， it's anonymized， but we will find out whether you filled it in or not。

We get one bit of information。But you can， you know， say whatever you like on the survey unless。

Only one of you responds to it， there will be guaranteed ambiguity。哦。

And then the third announcement is that。嗯。There's a talk tomorrow afternoon that I think you might find extremely interesting。

 Philip Coman is from CMU， and he served on the NASA Commission that investigated Toyota's software development practices in the wake of。

The various unintended acceleration accidents that happened。

 and he has some stories that I think you'll find pretty entertaining and very relevant to this class。



![](img/da0c2090d12c483138e9d0e7bc633fde_1.png)

So。We are here， I hope you enjoyed the holiday， I trust everyone enjoyed working with SP。Mh。😊，嗯。I。

 you know one of our goals in this class， as I've said many times。

 is to give you a sense of where the state of the art and the technology is。

Wts and all and to you know。Also。Give you some sense of skepticism， know。

 we want you to be able to use the best available tools。

And I really wish we had used spin to validate the midterm questions。

Before we published our solutions。We didn't and we got bitten and it serves us right because。

One of the points that we've been making about。Using a formal language like LTL and using a formal model like state machines。

Is that you can do mechanized analysis。On these models， whereas with informal models。

 you can't do mechanized analysis。So you could make the same kind of mistakes that we made on the midterm if the true false statements had been written in English。

Okay。And in fact， you're more likely to make the mistakes and less likely to discover them， right。

 one of the mistakes on the midterm we didn't discover until Antonio was putting together the spin tutorial and decided to use our midterm question。

But apparently， nobody in the class who got the answer that we thought was wrong gave an explanation that we found convincing。

So。It wasn't until we used the formal tool， the formal analysis tool that we were able to determine what was really going on there。

In a sense， we were not following what we preached by not validating our midterm questions using the tools。

But I hope that the experience that you got of actually creating a spin model also gives you some skepticism。

One of the things that I find a little troubling about using tools like that is。

You actually can have a lot of confidence in the answer that it gives you。

It tells you definitively whether the LTL formula that you've specified is satisfied for the state machine that you've specified。

But what it doesn't tell you。Is whether the state machine that you've specified is the state machine you meant to specify。

It doesn't tell you that， and it's actually not that easy to be sure that the state machine that you specified to spin is actually the state machine you thought you specified to spin。

This is， know， partly I actually think proel is a pretty ugly language and ugly languages can lead to programming mistakes well so can pretty languages in fact。

Well， all languages。Can lead to mistakes， right？You know。

 it's better to have a language where these mistakes are a little more evident。

So for small state machines， for example， probably a graphical language or at least a language that renders graphically what you've specified might be useful because the graphical visualizations can be pretty useful。

 but that doesn't really work for big state machines。So there you have it。

 know there's a technology there， it's very powerful， it's based on a very sound theory。

 but it has words。And it has pitfalls。ok。So any questions for me， comments？



![](img/da0c2090d12c483138e9d0e7bc633fde_3.png)

All right。So today we are going to talk about data flow models。And。

One of the goals here is to actually to。Try to give you a sense of how you take the scheduling theory that we've looked at。

 you know， rate monotonic scheduling early as deadline first。嗯。With all their warts and pitfalls。

 the anomalies that can occur and all that and how you can use them in practice。



![](img/da0c2090d12c483138e9d0e7bc633fde_5.png)

So in particular， I'm going to use a little。呃。

![](img/da0c2090d12c483138e9d0e7bc633fde_7.png)

Problem statement in scheduling here， which is。I have a。A system here。

That is doing spectral analysis on an audio signal。Okay， so。

There's a more or less sinusoidal signal and it's doing real time spectral analysis。

 this is the time domain signal that's the yeah。That's the audio thing。

We're interested in doing some scheduling on this and the scenario here is a little more elaborate in that I'm interested in a system that has some feedback to the real world。

So in particular， assume that you've got some。Audio processing that is requiring low latency。ok。

So in the case of the application that I just showed you。

 there wasn't any there was no actuation in the physical world it。You know， kindin of， well。

 there was actuation， the actuation was a stimulus to the human visual system。Okay。

 and so the timing requirements have to do with the cycle visualual。

Properties of the human visual system。And。In order to understand that the spectral analysis that you're being shown correlates with the audio signal。

There is a latency requirement， but it's a fairly loose one。That's a latency requirement。You know。

 the psychovisual system in the。Human brain can tolerate latencies of tens to hundreds of milliseconds there and still be able to see that correlation。

So it's fairly loose。嗯。It's a fairly loose timing constraint。

 but you might have something that is a much tighter timing constraint， so for example。

 if you're doing computer music， okay？Then the。Processing between the sensing and the actuation。

 the latency of that can have an enormous effect。the human auditory system is sensitive to timing phenomena down on the order of 10 milliseconds or so。

Okay， so if you're hearing rhythmic patterns， for example。

Errors of 10 milliseconds are very audible okay。So。You know。

 you get tighter latency constraints when you have that kind of tighter feedbacks， isn' it。

 but the interesting thing about this application is that we want to combine something that has some tight。

Latency constraints with something that actually doesn't have such tight latency constraints。

 so the spectral analysis in this case， you know， maybe 100 milliseconds is fine here。

10 milliseconds is really pushing it。 We want to be。

As good as that may be better okay so those kinds of mismatches happen a lot in embedded systems and so the question is how can you use the scheduling theory that we've developed so far to address a design of that kind of system okay so you got a time critical path and a less time critical path。

Okay， so one way to handle this is you know， create two threats。嗯。And pray。But maybe you know。

 if you do a really careful job with the software， you can get this to work。

 but what scheduling theory should you apply？Well， rate monotonic scheduling doesn't apply because there's dependencies。

Across these tasks。Okay。So。Sorry， can't use that theorem。You'll have to use something else。

 all right， well so let's try EDF with precedence。Okay。嗯。But then we have to assign deadlines， okay？

And， moreover。You know， this kind of application is actually periodic。

So it would seem like great monotonic would be the right thing to use because that。You know。

 is directly talking about periodicities， but earliest deadline first isn't。

It's talking about deadlines， so we have to sign deadlines so we could say， all right， well。

 somewhat arbitrarily， we'll choose the deadlines to correspond with the ends of the periods。Okay。

But that doesn't really work for the psychovisual side here right because that one is know looser。

 so but we have to pick something if we're going to apply earliest deadline first。

 we've got to pick some deadlines， otherwise earliest deadline first doesn't make sense okay。

This is a very common problem that you face in the design of software is that you end up having to make decisions that。

You can't really make on any fundamental， foundational basis。

So you have to use some engineering judgment when you come up with some numbers。So。

Let's look at an abstracted version of this。And do the typical thing that people do with scheduling theory。

 which is。To assume the unassumable。Everything executes in a known amount of time。

Or at least a worst case execution time，And。We're going to reduce the problem to three tasks。

A blue a green and a red。Anybody in here colorblind and can't see the difference between these colors？

This is your chance because otherwise I'm going to use the colors， okay。Extensively， okay。So。

All right， so the issue here is that the red task。Represents the spectral analysis。

This is the one that is not so time sensitive。But also computationally heavy。

It's going to take quite a bit of processing to。You knowDo the analysis， do the visual rendition。

And then A and B are going to represent the low latency time critical task。

 and those are going to execute with a higher period。

 so I'm going to do the spectral analysis more rarely。So typically the way you do spectral analysis。

 like in the example that I just showed you is you collect a whole bunch of samples。

you need a whole bunch of samples to do spectral analysis。tThen you run an FFT on that。

 then you post process that FFT data， it's quite a bit of computation that has to be done。

 and then you create a visual rendition of that okay。嗯。So。All right。

 so A and B assume that those are running at a much higher frequency and that there's a low latency requirement。

 so we want shortly after A executes， we want B to execute。ok。Now， based on the data precedes here。

 let's just assume that。We're doing an eight point FFD， which is silly。

 that's too small to be of interest， right？The one that I just showed you was a。

124 point FFT that it was doing。To get the visual rendition， it's reasonable。

If I drew a picture with 1024 invocations of the red and green here， you would get impatient。

And you wouldn't be able to see the detail so 8。 F50。All right。

 and so what this means is that for every sample a produces。

We're going to think of that as an invocation of task A， the blue task。Okay。

And there's going to have to be eight invocations of that task to execute in order to invoke the red task。

哎。做。There's a model here that's a little bit different from， say， the synchronous programming model。

Because the synchronous programming model would say， well。

 these tasks execute conceptually simultaneously and instantane。That's not what's going on here。

What's going on here is there's a task that's a source of data that has to execute a bunch of times。

And the task that is consuming that data becomes enabled after a certain amount of data has accumulated。

ok。That's not the synchronous model of computation anymore。And moreover。

 it's distinctly non synchronous because actually the task that's consuming the data， the red task。

 could be postponed。In fact， if you have enough buffering， you could postpone it quite a long time。

Right。If if it really is non time critical， you， it's being used to just do logging， for example。

Then you might want to be able to postpone it arbitrarily depending on what's going on in your machine。

So that's distinctly not the synchronous model of computation anymore。

 and we can think of what we're going to do today is kind of formalize a model that actually can capture this asynchrony。

But still preserved determinism in the execution， and that's a data flow model of computation。

You've used already a special case of this in the lab， when you use LabVi。

 you're using a very specialized form of data flow。ok。

And I'll talk a little bit about what that specialization is。But anyway， okay。

So that's the scenario here， so now you can see because of the data dependencies here that we're going to need to have eight invocations of the blue and the green task for one invocation of the red task and there's precedes between these and we can draw the precedence graph for one cycle of the execution。

that's what I've drawn here on the right。And we can use that precedence graph to come up with a schedule。

 So I might execute these by executing the red and the green。Eight times。And then executing the red。

Now， how' does this schedule look to you？It look good。It's a good thing to do。Well。

 what do we mean by good right well， we want low latency between the red and the green。

Have we got that？Yeah， right， the green's executing right after the red。All right。

 so checked that box。We want periodic execution of the red and green。I mean， the blue and the green。

Have we got that？It's sort of， but with a considerable amount of jitter。Right。So。

 if you're doing audio processing， the audio samples are coming in at a fixed sample rate。

So if you go with a schedule like this， you're going to have to do some buffering of the audio samples。

If you do buffering of the audio samples， that's going to introduce latency。Okay。

 which is going to increase the latency。 So now it's not just your schedule that's going to affect the latency。

 it's also the jitter。That's going to affect the latency。Okay， is that clear to everybody？All right。

So nevertheless， we can make this work and the way that data flow models in general work is that you do buffer data between a source and a sink。

Using a first in first out buffer。And then the invocations of the destination。

Are determined by having sufficient data available for it to do its job。

 so we're going to define formally a firing rule。Which is。

 how much data does B need in order to be enabled？And once it's got that amount of data。

 it becomes enabled and enabled in very much the scheduling sense that we were using。

 when we were talking about EDF， only at that point can you start to think about scheduling it。ok。

All right， so formally。The signals that are connecting these two actors are no longer。

Time domain signal。And they're no longer the signals of a synchronous reactive model。

So a time domain signal is a function of time。A synchronous reactive signal is a function of an abstracted notion of time。

 which is a sequence of ticks。These are neither of those。Okay。

 what flows between these two actors is a stream， which is a sequence。

But there's no notion of time anymore， intrinsic in that， you have a sequence of values。

 but without a notion of time， so you can formalize that。

As a function from the natural numbers to your data type， so if it's audio samples。

 maybe it's the reals。ok。And that function represents now an unbounded sequence of values。

And we're not going to interpret the domain as representing time。

So the natural numbers here are not representing time and they're not representing ticks。

Of a global clock like they are in synchronous reactive models。就。In particular。

If you have two distinct signals in a data flow model。你。

Index n could be the same for two particular samples。In those two distinct signals。

 But that does not mean that those are in any way simultaneous。ok。So there's no notion of time here。

 just sequences。And that's the key。Okay。So I talked about firing rules briefly， right。

 so firing rules say， well。The enabling of a computation is determined by the availability of input data。

And there's a few patterns that。You find。In LabVi， there's pretty much only one pattern。

Which is all your inputs have to have one new data value。And when that block fires。

 it produces one new data value on all the outputs。We call that homogeneous synchronous data flow。

 and I apologize for the term synchronous here。嗯。It's my fault。Actually。

I coined that term a long time ago， more or less at the same time that the synchronous languages were being invented。

And。It's not synchronous in the sense of synchronous languages。

It's synchronous in a different sense that I'll。I'll you later。

 but the key thing is synchronous dataflow is an asynchronous model of computation。嗯。ok。Sorry。

 terminology is not perfect， but it is okay。Now， all right。

 so homogeneous synchronous data flow says you require one new datum。

At each input in order to be released。Okay， you can now be scheduled。

But that our spectral analysis example doesn't fit that pattern。

 it requires eight new data chunks of data in order to be released。

 so we can easily generalize this and say， well， a non- homomogeneous synchronous data flow model just has its firing rules。

The ability to specify that you need some integer number of inputs。

And you will produce some in or number of outputs when you fire。Okay， so that's a generalization。

But you might go still further， so for example， this select is a data flow actor。

That requires a Boolean input here。On the bottom input。Okay， so that's part of its firing rule。

And if the Boolean is true。Then it requires。A datum at the T input。Whereas if the Boolean is false。

 it requires a dat at the false input。Just one。Okay， so now there's actually two。

Distinct firing rules。And an execution will pick between them。

One firing rule is there's a true valued token here and a token here， now the actor can fire。Okay。

 and what it'll do is simply produce copy that token into the output， right？

And then the second firing rule is that there's a false valued token here and a token here。

A token being a chunk of data。Okay。And then the actor will simply copy that token to the output。

 so in the data flow world， they talk about tokens and streams of tokens are the data that flow between the actors。

 so a switch is a simpler one in that requires it has a simpler firing rule。

 it requires a token at each input。But then depending on the Boolean。Value of the input。

 it will route the token to either the T output or the F output。ok。

So you can do data dependent routing of tokens using these。These are very low level， by the way。

 in fact， in my view， they're the Go tos of data flow。

This data dependent routing of tokens is like GoTos in imperative programs。

And if you use them in building programs， you're basically programming with GoTos。Okay。

 so don't use them。嗯。There are better ways to do things。But nevertheless。

 they're useful for theory just like Go tos art， and you can understand kind of expressiveness of data flow models so for example。

It turns out。嗯。That if you have a single homogeneous synchronous data flow actor， a Nand gate。

And you have only Boolean data types。Okay， so the tokens are either true or false。

 you have a nagate and you have switch and select。You can build a Turing machine。ok。That's enough。

And so that says that that collection of three actors， you also have you need one more thing。

Which is to be able to initialize a stream with an initial token。This is how you break loops。Okay。

But with those four primitives。You can build a Turing machine。And why do we care， right。

 because actually。You wouldn't want to build。APro that way。

 right you wouldn't want to do spectral analysis on an audio signal using a Nandgate and switch and select。

嗯。So the reason that we care is that it tells us something fundamental about the analyzability of these models。

It'll tell us that there's a bunch of questions that we might be interested in asking about these models that are going to prove to be undecidable。

ok。And I'll come back to that in a little bit， but just keep that in the back of your mind。

 And one of the things that we're going to find is that if you don't allow these guys。

And you just have these guys。All these questions become decidal。Which turns out to be。

Kind of useful in embedded systems， particularly if you're designing safety critical systems。

 so for example。嗯。In data flow models， we use first in， first out buffers。Okay。

 so actor A produces a token， it goes into a queue。

Actor B becomes enabled when there's enough data in the queue for its firing rules to be enabled。

How do we keep the cube bounded？ok。嗯。It turns out that。

If you build your data flow model out of those four primitives that I suggested。嗯。

It's undecidable whether you can keep the cues bounded。Okay。

 so what that means is that given a data flow model。Well。

 what it means is that there's no algorithm that you can use that will analyze any data flow model and guarantee that。

It uses a bounded amount of memory for the buffers。ok。

So that's where kind of the fundamentals start to matter because we're interested in being able to bound buffers。

Particularly for safety， critical embedded systems， buffer overflows are a problem， right？O。嗯。

So buffers。If they're bounded。If they're unbounded。

 they require memory allocationation and delocation。You know， which then requires。

Management of the garbage collection。Right。Yes。It's not the allocation and the allocationloc， no。

 but mechanically if you're going to implement a system with unbounded buffers。

 then you need a mechanism for doing allocation and delocation， okay？

So that adds complexity to your system， it adds potential for memory fragmentation if you've studied this problem。

 right？Memory fragmentation is not such a problem for tasks that are finite。

Like most information technology computer programs are things you run。

 and then they stop running and they're done。But in embedded systems。

 you are often interested in systems that will ideally never stop running。And in that case。

 memory fragmentation can be deadly。Because eventually things degrade enough that you have big problems in the system。

So there's a lot of incentive in embedded systems to be able to bound these buffers。

And if you bound the buffers， you can implement a buffer of arbitrary length very efficiently using a circular buffering scheme which is outlined here。

Okay， which I'm not going to go through the details， it's very straightforward data structure。

Stuff but。You know， it can be done very efficiently if you have bounded buffers。All right。

 so there's a lot of incentive to bound these buffers。All right。

 so let's go back to this abstracted example。嗯。We'd like to bound the buffers。

 does this schedule that I've come up with bound the buffers？It does， right， because。

Every invocation of A has a corresponding invocation of B。

 so a token produced by A will be consumed by B。 we call that a balance condition。

Every token produced gets consumed。Okay。嗯。The red actor needs eight tokens。So。嗯。With this schedule。

 every eight invocations of a。Have a corresponding invocation of the Red Act。Okay。

 so that connection is in balance as well。So this schedule has the advantage of keeping the buffers founded。

 but it has the disadvantage of the jitter that we identified， there's this pause time。

If this is a heavy duty computation， that polyton could be quite large。

 which then implies you could do buffering of the sensor and actuator data。

 which means increased leaks。so we want to try to fix that。Problem。Okay。So here's one way to fix it。

Okay。Just change the schedule so that， in fact， the red and the green are， are。

Being invoked periodically。No buffering needed anymore。So what's the disadvantage of this？Sorry。Yes。

How much time what？Yeah。So， I mean。First of all， the rate at which you're going to be the sample rate at which you're going to be able to execute this is going to be determined by your non time critical task。

That's usually not a good property， right？You'd rather that the rate be determined by your time critical task。

 not by your nontime critical tasks。ok。The other thing is it's just morally offensive in computing to waste resources。

Here's look at all that CPU time that you're not using。I。

Don't know that utilization is really necessarily that。Big an issue。

 but but there is an issue that you know there's。There's an increased system cost here。

Because suppose that you have to handle a particular sample rate。

know maybe you're doing oversampled audio and you need to be able to handle。192。

000 samples per second。ok。And you've got a big chunk of computation that has to be done。

Now you design the system， you have to pick a processor that can do that amount of computation within one sample period。

You're going to end up picking a more expensive processor that consumes more power than you would need in principle if you were able to get better utilization。

Right。嗯。So this isn't such a great solution。Okay， so let's find a better solution。How about。If we。

Use multitasking。So we create two threads。One of which executes the high frequency tasks。

 the A and the B。And the other one of which executes the low frequency task。

And we misuse the rate monotonic theorem。And apply high priority to this thread and low priority to this thread。

 why do I say we misuse it？Because there's data dependencies here， right。

 so the theorem doesn't apply。Okay。But。EDF applies kind of。Okay， now。Given this schedule。

 will the buffers remain bounded？You really have no assurance。That they're going to remain bounded。

 right， I mean， suppose that the red task runs long。Sorry。Yeah， but you can postpone that， you know。

 you're not going to execute the next red task until you're done with the first one， say。Right。

 your buffers are going to keep growing the buffers feeding the red task。

 if the red desk is running long are going to just keep growing。In an unbounded fashion。In fact。

 this is generally always a possibility with data flow models when there's no cycles in the model。

 there's no feedback in this system。So there's nothing to prevent A from just keep producing tokens that are not being consumed。

Okay。All right， so we can fix that。By putting in an interlock。ok。So。Using a semaphore。

We will prevent the ninth execution of blue。From starting until the execution of red is done。Okay。

And。That will prevent that buffer over。is that enough to prevent buffer overflow？Tてる。

Why is it that the buffer between A and B doesn't over overflow？Yeah。

 there's a scheduling constraint built into the schedule that we've produced that interleaves the executions of A and B because we've put them in the same thread。

ok。So we put them in the same thread。 and we're just executing an infinite loop that fires A。

 then fires B， then fires A， then fires B。 So balances assured。In that。Okay。

 so we've guaranteed a bounded buffer on this connection。By statically scheduling。

The actors that are involved in that connection。And we guaranteed a bounded buffer on this connection between the blue and the red。

Using an interval。Okay， yes。Yes， this you still get jitter in this。

So now you're going to care about worst case execution times。And。

You're going to want to be able to validate that the thing is going to be able to keep up， right？

That's。Potentially a problem。 You do have alternatives， right。One is you could treat it as a fault。

If your red task runs longer than you expected。In a safety critical system that might actually be a reasonable thing to do。

Particular if the red task is a non criticalit thing， it's doing some logging or something like that。

 you treat it as a fault， you abort the task。喂。You may switch to a degraded mode where you stop logging stuff or something。

There's also a notion of any time computation that can be useful。If you're doing data analysis。

has kind of a background process。A well structured data analysis algorithm might be able to give you useful results。

 even if it's only partially completed。So for example。

There are spectral analysis techniques that are incremental instead of deciding ahead of time that I'll do a 1024 point FFT。

Right， I do a 16 point FFD， and then I use those results to create a 32 point FFD。

 and then use those results to create a 64 point FFD。Okay， and then when I'm out of time。

 I just take the FFT that I got。And use that。For the visual rendition。

That's known as an anytime computation， that's a nice way of enforcing a worst case execution time。

 right you just say this is by definition the execution time bound and I'm just going to take the results that I've got so far and abort the computation at that point。

So that's potentially a useful thing to do there。嗯。Now。We need another interlock here。To。

Respect the data dependence。ok。Because thread2 is also in an infinite loop。

 it's just in repeatedly invoking the red actor。ok。But what's to keep it from starting early？Well。

 if it just repeatedly invokes the Red Act or nothing。

So you have to put something in there that ensures that the second execution of the Red actor doesn't begin until its firing rules are satisfied。

It needs eight new datums。I think those are called data。datata is the plural of datum。

It needs eight new tokens， that's why people in dataflow use the word tokens instead of data because。

A lot of people think of data as being singular， not it's plural。It confuses people。

So the red needs eight new tokens， so we're going to need another interlock to make sure that it doesn't start executing until it's got eight new tokens。

Okay， so with this pair of interlocks， we can get a deterministic execution， right？Now。

 notice that if one of the blue or green tasks runs long。That。Everything's okay。

 We don't need another interlock to protect。For that。Why is that？It says right on the slide。

The fact that this thread has higher priority means well， the red task is not going to get around to。

Well， actually， I don't even think actually， does the priority even matter。

Would this still work if I reverse the priority？There's a good。I give the red task。

Higher priority than the blue and the green。If I have these inner life。

The timing constraints may not be satisfied。But the data flow might be correct。Okay。Is that true？

That would be a really good， true， false question for midterm too。Okay。嗯。You know， give you。

A schedule that works with a certain priority and ask you。

 does it still behave correctly if you reverse the priorities？Yeah。So in this case， you。

 the static scheduling that's occurring in thread1， which gives you a fixed interleaving of A and B。

Guarants that the data flow requirements on the connection between A and B are satisfied。

 no matter how long anything takes to execute。喂。The two interlock。

Are guaranteeing that the data flow requirements。From A to C are also satisfied。Okay。

 so the data precedences will be satisfied even if you reverse the priority。

The only thing that will be affected is the timing。Degrade， okay？And in fact。

 it will degrade because if you reverse the priorities。

 the red task will execute to completion without being preempted and we're back to the high jitter schedule that we had before。

Okay。All right。I think I said all that。All right， suppose that you have a slightly more elaborate data flow model here。

So this is， by the way， if you've ever used simullink。呃。

Simulate notation for blocks that run at different rates is you specify a sample time for them。

Which you're supposed to read is the amount of time allocated to processing a single sample。

But it's not really time。So it's kind of misnamed。But anyway， what this means。

Is that B will execute one fourth as often as a。Okay。In simlink notation。

Psumably consuming four tokens produced by a。All right。So in this case。

 if I come up with a sequential schedule on a single processor。

 it's going to look something like this， I'm going to need to do four invocations of A before I can invoke B。

Once I invoke B， say it produces four tokens on its output， then I can invoke C four times。Okay。

 and I get a schedule like this。Now。If I'm interested in latency and jitter。

 this is a pretty unattractive schedule。So is there any way to fix that？Well。

How about trying some threading？Okay。就。Here's an alternative schedule right that puts the red in a low priority task and the green and the blue in a high priority task。

And has interlocks， so once the blue has executed four times， the red becomes enabled。嗯。Once。

Why is there an interlock that is preventing the green？Right。

 green is requiring four data tokens from the red。So it's going to react at this time。Okay。嗯。

Now here's a question for you in terms of latency。RightLatency we could define as the time between when。

A produces a token。And C consumes something that。Depends on that token right So if a is a sensor。

Right。It takes a reading。How long do you have to wait before that reading can have an effect on an actctuator？

That's the latency。so what's the latency of this schedule？It's not very good， right？

The sensor reading is taken here， and the first effect it can have is here。And here。

The first reading is they can hear and the effect that it has is here。Okay。So。嗯。This is。Actually。

 in practice， these two latencies are going to end up being the same。

 because the reason why are these things spaced out？And these are not。

The only way that you could have the sensor。Fire four times and then not fire again for a chunk of time is if there's some buffering going on it。

 this is doing regular sample rate。Sensing。There's going to have to be some buffering。So， in effect。

You didn't really get anything any improvement。In latency by going to a multi threadreaded schedule。

Okay。And you've added a lot of overhead because there's context switching over。All right。O。嗯。

So data flow first of all。嗯。There's a very long history of looking at data flow models。

It's been a little bursty in time。And actually， this。A particular list doesn't go up to the present。

 but there's a whole bunch of other stuff after here。嗯。

Dates all the way back to some work that our very own Dick Carp did way back in 1966。嗯。

Our former department chair， David Culleller， wrote his PhD thesis on data flow models。

I wrote my PhD， thetheus on Dataflowlow models and in fact coined the term synchronous dataflow。

 creating enormous confusion because at pretty much exactly the same time。

 the loosester programming language appeared and was described by Paul Caspy as a synchronous data flow language。

And Paul actually， in the second paper that he wrote on Luccer， he cited my thesis。

Without having read it。And he simply assumed that because it had synchronous data flow in the title that I was talking about the same model of computation that he was talking about。

But。I wasn't， they're two completely different models of computation。

So be careful when you cite people's work， you know。

 it's really a good idea to actually read the papers。嗯。But anyway。

 because it's one of my favorite topics， I'm going to tell you about this synchronous data flow model。

And。You know， and a little bit about。More expressive models。So this particular model is。

It's not very expressive in the sense that it cannot describeuring machine Turing complete computations。

 okay， it is not Turing complete。But there's a class of things that it can do very well。

 and for those things， the ability to analyze the model completely is a very powerful tool。

So there's kind of a trade off， it's kind of the same argument， why do we use finite state machines。

 finite state machines are also not doingcompte？But we use finite state machines anyway because we can exhaustively search their behaviors for anomalous behaviors。

 that's what SP does。spinin looks at all the possible behaviors。

And then gives you definitive answers about the whole family of possible behaviors that this machine can have。

And you can't do that in general with touring complete models of computation。

So synchronous dataflow is another more constrained model like finite state machines。

 but it's very different from finite state machines， it has a very different character。

 it's about stream processing。Okay， so the key constraint with synchronous data flow is that the firing rules of every actor are really simple。

They require a fixed integer number of tokens on the inputs。And then they become enabled。

And when they fire， they will produce a fixed integer number of tokens on their outputs。

So if you have a connection between two actors。You can write down a very simple equation。

That relates the executions of these two actors that guarantees that you will keep everything in balance。

ok。So here's the balance equation for this particular connection。

It says that if you fire actor a QA times。ok。And it produces P sub C tokens on connection C。

That that should equal the number of times that you fire a or B。

Times the number of tokens that it consumes。Very straightforward。

 right that's how you keep things in balance， all the tokens you produce should be consumed。

But there's something a little weird about this， right？This。Model fundamentally never terminates。

A can keep producing tokens and B can keep consuming tokens。So aren't Q A and QB both infinite？Yeah。

 they could be。And in theory， it'll still be imbalance， right， infinity equals infinity。

In some sense。At least。These two infinities will be equal。But that's not a useful conclusion， right。

 so we're going to want to do more limited analysis。So let's look at a slightly less trivial example。

Here's a data flow model that consists of three actors。This one has two output ports。

 it produces one token here， two tokens here when it fires。

This one consumes one and produces two here。ok。And this one consumes one and one。

So is it obvious that this？Can be kept in balance。Well。Maybe yeah， it's， I don't know。

 depends what you mean by obvious， right， You have to notice that。

Acctor three needs to execute twice as often as these guys。

And these two need to execute the same number of times。To keep things in。Right。

But the balance equations for these three connections will tell you that。

So the balance equations can be described very compactly。As。A very simple matrix equation。

Where this is， if you've studied graph theory， this equation looks a lot like an adjacency matrix for describing a graph。

But instead of just describing adjacency， it's also telling me how many tokens are produced and consumed。

So the way you construct one of these matrices is you create a row for each connection。In the graph。

So this is connection number one， which connects actor A and sorry， actor 1 and actor 2。Okay。

 so that's the first connection。And then you create a column for each actor。

And you enter into the matrix the number of tokens that are produced or consumed by that actor on that connection。

 so actor1 produces one token on connection one。Actor2。Which is the second column。

 consumes one token from connection one。So you put a negative number there。

Actor3 isn't involved in connection1 at all。So it doesn't produce or consume anything on that connection。

 so you put it in a zero。Right。So you can construct such a matrix。And then you construct a vector。

 which is the number of invocations of each of these actors。

Q1 is the number of times actor1 executes， Q2 is the number of times actor 2 executes。

And then balance simply requires that the matrix product of gamma times q is equal to 0。Okay。

So it's a very compact representation of this balanced constraint。就。For this particular example。

 the balance equations look like this。 This matrix is not necessarily square， notice。

Because the number of connections is not necessarily equal to the number of actors。

You have one row for each connection， one column for each actor。Okay。And you can see that actors。

Well， this must be actor B， and this is actor C。In the picture。Violating lexiographic order。Okay。

But you can see that this equation， I mean， this matrix represents the production consumption patterns of these with appropriately labeled。

Columns and rows。Okay。All right， so going back to this。Slightly more interesting example。嗯。

We've got this matrix equation， and the a key question arises。

 do we have any assurance that there is a solution？Oh that's the first question， actually。

 you tell me。Is there a solution to this equation？Can I find a vector Q？

Such that gam times  Q is equal to 0。Where any。Well no。

 this specific one you're given the solution right here， so in general。Yes。

If it's full rank and there isn't， well， actually it's not quite true。There is always a solution。

 what's the solution that always works？0ero。You can always keep a data flow model in balance by not firing any actors at all。

Okay。But probably that's not what you wanted to do。So you're interested in finding a nonze solution。

And the existence of a nonze solution will depend on the rank of this matrix。Okay。

We're not looking for any what are we actually looking for？We're interested in integer solution。

 you know， if the solution says that we should fire after one pi times， actor two pi times and a3。

 two pi times。It's not very useful because you can't fire an actor pi times。Right。

You also are not interested in solutions that say something like you should fire actor one once。

 actor two negative one。And actor three twice。Because you can't fire an act or negative ones。ok。

Like you have to unfire the actor。So we're interested， in fact， in positive integer solutions。

To the balance equations。ok。So。Rational solutions are enough because if you can find a rational solution。

 you can find the least common multiple of the denominators。And then find an integer solution。Right。

So。Yeah， so。In this case， in this particular example。

 there's many solutions to the balance equations， this one will solve the problem。

 this the trivial solution where zero negative firings works， irrational firings works。But of these。

Only these two are interesting。And this one is arguably more interesting than this one。

Because it's the smallest positive integer solution。ok。

So if we're interested in solving the scheduling problem it's。

It should be intuitive that dealing with fewer firings is going to make the scheduling problem easier than dealing with more firings。

But that's not actually quite so obvious because it turns out that if you deal with more firings。

 you have more flexibility in the scheduling and you could come up with better schedulecheds。

But nevertheless， okay。So here's the key result。If this matrix does not have full rank。O。

There always exists a positive integer solution to the balance equations。

 and there always exists a least positive integer solution to the balance equations。And moreover。

There's a very simple linear time procedure for finding that solution。Okay。That's a key result。

 and it's actually very easy to see why that result holds because。

The number of tokens produced and consumed is always an integer。And in fact。

 always a positive integer。As a consequence， if I arbitrarily set。QA to1。

Then I have a rational solution for QB。Okay。So now I've got。To。Of my vector elements。

 I've got values for them that are rational。喂。If the graph is connected。

 this is for connected graphs， right， if the graph is connected then。

Either actor A or actor B is also going to have a connection to another actor。Okay。And consequently。

 I can find a rational solution for the number of firings of that actor。

And then once I've got that rational solution， I look at what it's connected to。

 and I can find a rational solution for that guy， and I just pervaed through my model until I've got a rational solution for all of the actors。

So now I have a rational solution， a positive rational solution。ok。

Now I can go through and find the least common multiple of all of the denominators multiply through by that least common multiple。

And these comment or what am I interested in， the greatest common divisor？Whatever。

Depends on whether you're looking at the numerator， multiplying or dividing， right？But anyway， yeah。

 so you can find a rational solution if one exists。But if the matrix has full rank。

 then the only solution is the zero solution。And how will that manifest？As you're trying to do this。

傻微。It manifests very simply， which is that you。You're going to have to have a loop right so when you reach out to the next。

Actor that you're connected to you discover， oh， I've already got a solution for that。

 and guess what this new balance equation isn't satisfied by that solution。

So discovering imbalance is also done in linear time。Okay。So terminology。

 a model is called consistent if there exists a non zero solution to the balance equation。Okay。嗯。

Here's an example of an inconsistent model。 This is slightly， very。

 ever so slightly different from the previous one。Instead of producing two tokens。

 actor two produces only one。Okay。Here's what the production consumption matrix looks like。

The only solution to the balance equations now is to not fire any of the actors。

And you can see this intuitively， right if I fire after one， it's going to produce two tokens here。

And one token here。At that point， I can fire actor two once。

 and it's going to produce one token here。 So now I've got one token here and two here。

This is enabled for one firing。And it'll consume the one here and one of the two here。

But now I have a leftover token and no way to consume it。ok。If I repeat this process。

I'm eventually going to get buffer overflow on this connection。Okay。

 because it'll just keep accumulating tokens yeah。No， I haven't given you a proof of this。

 but I've given you a proof sketch， right？Because。So。Well，You should read my PhD thesis。

 It has the proof。Sorry。That's right。You also know for sure that there is a solution。

 there is a least positive integer solution if the rank is not full。Well， actually。

 the way to prove it is， I'll give you the proof sketch for that too。

If the matrix doesn't have full rank， then a spanning tree on the model has exactly the same information as the full model。

Okay。Because。No full rank means that there are linearly dependent rows or linearly dependent columns。

 and so the columns or rows that are linearly dependent are redundant。

So you can find a spaniting tree and then show that the spanning tree has the same set of solutions as the original model because of the lack of full rank of the matrix。

For a tree， it always works， a tree is always invalid。 well that's the sketch of the proof。Okay。

So in this case。For this example， there's no nontraal solutions。

 and the nice thing is that you can analyze this model and reject it。As an erroneous model and say。

I cannot execute this thing with bounded memory。Now notice， I mean， that kind of a statement。

 being able to make that statement about a program， this is a program。Is non trivial。

 you can't make that statement in general about any program in a touring complete language。I mean。

 or rather more precisely。There is no algorithm。That given a program in a touring complete language。

 we'll be able to answer the question。Of whether it can execute with bounded memory。Okay。

 but with synchronous data photographs， there is an algorithm that can answer the question of whether it will execute in bounded memory。

Okay， by the way， that's a proof that this is not a touring complete model of computation。

Because the boundedness question is decidable。ok。嗯。

So consistency is a necessary condition to have a bounded memory， infinite execution。

You can execute the model forever with a bounded amount of memory。

Is this also a sufficient condition？In other words， if I know that I have a consistent model。

Do I know that there exists a bounded memory， infinite execution？What do you think。

Is it if I know that the bottle is consistent？Can I conclude that there exists a bounded memory。

 infinite execution？No， it doesn't depend on time。The existence of a bounded memory infinite execution just it doesn't matter how long the tasks were。

So what I've sketched for you is a theorem that says if the model is inconsistent。

There is no bounded memory infinite execution。ok。But I haven't said anything about whether if the model is consistent。

 is there a bounded memory？So the question is， is there？I see one， you want to explain why not？

You could have a deadlock。How about this model？Okay。The balance equations have a solution。

You can execute both actors once。But you can't execute both factors once because neither of their firing conditions are satisfied initially。

And so。There's no infinite bounded memory execution， in fact， there's no execution at all。喂。

It's a bounded execution， it's not an infinite execution， right。

 it's a bounded execution that executes all actors exactly zero times。That's a deadlock。Okay。

By the way， I want to point out that in data flow models， deadlock is considered evil， right？

In Carpen Miller's first paper in 1966。They did exactly the reverse in the classical theory of computing。

Failing to halt is evil。Okay， so in that paper， they were explicitly interested only in models that deadlinelocked。

 those are the only interesting ones because they would specify a halting computation。

And in the Turing Church theoryory of computation， all the computations that fail to halt are equivalent。

And they're defective。ok。So that's an interesting twist。 But here in the case of data flow models。

 we're actually。halting is an evil property， so when halting is evil， we call it deadlock。

When it's desired， we call it halty。But it's the same phenomenon。ok。So this model halts immediately。

 I mean， deadlocks immediately。Okay。Now， deadlock could be a little harder to determine， right。

 I mean here you can determine at a glance that this is going to deadlock。

Suppose you've got something that has some initial tokens available。And does this deadlock quick。

 quick， Yes， no， well， at a glance， you can't tell， right you got kind。runun through an execution。

 and of course as the model gets bigger， it could get difficult。

 more difficult to answer the question of whether it deadlocks。But fortunately。

 the question of whether a data flow model， synchronous data flow model deadlocks is also decidable。

Okay。And。I think I have time to explain that。嗯。So。One way to determine whether a model has。

A bounded infinite execution。Is first。You check whether the model is consistent okay？

If it's not consistent， you say， well， yeah， there's no bounded infinite execution， I'm done。

 if it is consistent， however， now you still have to worry about whether it's going to deadlock。

So the one way to determine whether it deadlocks is to construct the schedule。

A schedule that can be executed infinitely often。Now。

But how do you know that constructing a schedule is a bounded process？

That's the key thing that we have to be able to。Ascertain。

So here's how you construct a schedule and simultaneously prove that the process of constructing a schedule is a bounded process。

 it terminates。Okay， so it falls in the。During church class of。Useful programs。Because it terminates。

 not deadlocks。Okay， so how does it work， Well， we're going to augment the model slightly by keeping track of how many tokens are in the buffers。

 So we introduce a new vector B。It has an element for each buffer and simply tells me how many tokens there are in that buffer。

So in this particular model， we start out with nothing in any of those buffers， so we have 0，0。

0 for B。We have solved the balance equations。And we found that 112 is a solution to the balance equations。

 which says that actor1 should fire once， actor  two should fire once， and actor3 should fire twice。

Okay。Now， interestingly。When we do the firing， what happens？Well。

We've used up one of the firings of actor1 if we fire it。So we could decrement the vector Q saying。

 okay， we've taken care of that firing。And we've had an effect on the buffers。Okay。

Which is we put a token into buffer one and two tokens into buffer three。This operation， by the way。

 moving from here to here。Is just。Multiplying the。The same production consumption matrix。

By a vector that tells me which actor I fired。I'll show you that operation in a minute。

 but intuitively you can see that we can keep track of the buffers， okay？So at that point。

 we can fire actor2。By the way， one of the things that we do is。

What are our possibilities now for firing the next actctor？In the theory of data flow。

The enabled actors， when my buffers are like this， the enabled actors are actor 1 and actor 2。

 those are both enabled。Okay， but I will not consider firing after one because I have zero firings left。

 this is what makes the process bounded。Okay I'm just going to rule out firing Act1 because I've already done all the firings of Act1 that are needed。

Right。So my only option is to fire actor too。I can update the buffers again。ok。

And now I decrement the firing vector， so that I no longer have to do any more firings of vector 2。

I still have to do two firings of Actctor3， but fortunately both of those firings are enabled now。

And I can bring my buffers back to the initial state。Okay。

 having satisfied all of the firings required in my solution to the balance equation。Okay。

 this process is guaranteed to terminate because。This vector is abounded。Positive integer vector。

Okay。Well， that's right， so you have a lot of choices typically in a data flow model。

 in this particular example， I only had one choice in each step。

But normally you have a lot of choices and let me show you an example that's really interesting about that。

嗯。This one right here。ok。嗯。This is an example that was studied by a student of mine in his PhD thesis。

 this was Schover about that Char， who's on the faculty at University of Maryland now。

And he was considering the problem of converting an audio signal from the compact disc format into digital audio tape。

So digital audio tape， I'm sure you guys。Don't know anything about it because it was a flash in the pan。

 it didn't last very long。But it was a technology that was introduced by Sony that was supposed to replace cassette tapes。

Okay。But it failed， all right now， but in the process of developing this digital audio tape technology。

 Sony decided that the sample rate on digital audio tape recordings should be different from the sample rate on compact disks。

So on compact disc， the sample rate is 44，100 samples per second。

And so they decided on digital audio tapes to use 48，000 samples per。Why？Sorry。Yeah。

 that was the marketing argument was higher sample rates better。So let's do a higher sample rate。

That wasn't the real reason。The real reason， yes。They wanted to make it really hard to make a perfect copy of a CD onto digital audio tape。

 you know， this was before everyone had CD burners。

C burners were expensive pieces of machinery back then。And so they wanted to make it。

Difficult to make a perfect digital copy of a C on a digital audio tape。

 So they picked an extremely awkward sample rate ratio。Okay。

So it turns out that you can convert a CD to a digital audio tape by first doing a two to one up sampling。

Then a two to three downs， then an eight to seven down samplingamp， then a five to seven up sampling。

So this is a data flow actor that consumes seven tokens and produces five。

This is a data flow actor that consumes seven tokens and produces eight。

These are numbers numbers are backwards for some reason。

And the solutions for the balance equations are shown under the actors。

This is the least integer solution to the balance equations for this particular model。

You execute this guy 147 times， this guy 147 times because this produces one， this consumes one。

This produces two。And this consumes three， so there's a two to three ratio between these firings so this executes 98 times。

 this executes 28 times， this executes 32 times and this executes 160 times and this will get you from 44。

1 kilohertz to 48 kilohertz。Sample rates。So anyway。

 Sva studied all the possible schedules you could construct。For this。

For a bunch of different criteria。And this is the schedule that minimizes the size of the buffers。ok。

And there's no patterns here， right， this is like chaos。

The schedule is it's very difficult to encode using an encoding algorithm。

Because it has no repeating patterns in it。At least not that repeat for very long。So。Yes。

 you have a lot of choices in the scheduling and depending on what criteria you're trying to satisfy。

 in this case， he was focused on minimizing the size of the buffers。嗯。

Then you might have a very interesting optimization problem to solve in constructing these schedules。

Yes。They all give the same data flow computation。 All of the schedules will produce the same。

Result in the end。But they will use a different amount of resources。They also， I mean。

 he also looked at just the problem of， you know， the size of the encoding of the schedule has a memory cost。

Right。So we want to factor that in as well as the buffer sizes。

So there's a book on this that Schva led the writing among the data flow。Efficionados。

 this is known as the Green Book。Because it's green。嗯。And。Here's a few of the， you know。

 it shows that there's a really big you can get really big effects。Okay。

So the amount of memory devoted to buffering of data in various schedules that are optimizing different things。

Can range from 1000 to a high of 1000 to a low 32。嗯。Chunks of data for this particular。

 rather small model。Okay。So that's a pretty big ratio of differences。All right， so ever so briefly。

 synchronous data flow is not very expressive， it's not to incomplete。

 that's why deadlock is decidable and boundedness is decidable。

If you augment the data flow model by just adding the switch and select。

You get a Turing complete model， it's no longer decable whether the model can execute in bounded memory。

 it's no longer decidable whether it deadlocks。Now。

 that doesn't mean decdable doesn't mean that for a particular model。

 you can't answer those questions。It just means that there's no algorithm that can answer those questions for all。

Okay。So this is a particular dynamic data flow model that does have a bounded memory schedule。

And it doesn't deadlinelock， in fact， it obviously doesn't deadlinelock。

No model without feedback loops， deadlocks。You need feedback loops to get deadlinelock。

So it turns out that you can extend the notion of these balance equations。

And put in symbolic variables in these balance equations and then solve the balance equations symbolically。

The existence of a solution becomes undecidable， but there are algorithms that for。

Well constructed data flows will always give you a solution， they give you a symbolic solution。

 and from that symbolic solution， you can then construct a schedule that includes conditional firings。

So for this particular model， for example。Based on a boolean that you observe。

 you can choose to fire actor 3 or fire actor 4。And you can systematically construct the schedule。

That looks like one of these static schedules for synchronous data flow。

 except that it's guarded by Boolean valued symbolic variables。ok。

It's undecidable whether you can construct a schedule like this， but if you can。

 you've got a proof of boundedness and you've got a proof of lack of deadlock。

So that was another PhD thesis by Joe Buck。These have very real practical applications。

 This is an example that was had a very nice paper。Aairly recently。

 there' has been a budget follow up on this paper， and this is a video coding example that also uses an interesting extension。

Of synchronous data flow， which is essentially parameterized synchronous data flow。

Where the number of tokens produced here is actually parameterized by， again， a symbolic variable n。

Okay， and you can use the same theory and extend the same theory to be able to do。

Scheduling of these kinds of models。Okay， I talked about the undecidability。

 and that's really all I had to say。 I mentioned briefly that。Lab view is a data flow model。

It's a very simple homogeneous synchronous data flow model。

But it has these constructs for doing loops and conditionals and so on。

You can if you think of switch and select as Go tos。These are structured programming。

Because they keep things on the boundary very well behaved。

 they look like homogeneous synchronous data flow， which is easy to analyze， easy to schedule。

But they allow for dynamic decision making in a very structured way。Okay。

 so that's it about data flow， See you next week or maybe tomorrow， don't forget， so announcements。

Three things to talk tomorrow。The Cyin survey and the Doodle poll and all three of these are on the assignments page no。

 I forgot to put this one up， this one's not on the assignments page on the。But the other two are。

 if you don't have to copy down the links now， just go to the assignments page on our website。



![](img/da0c2090d12c483138e9d0e7bc633fde_9.png)

![](img/da0c2090d12c483138e9d0e7bc633fde_10.png)