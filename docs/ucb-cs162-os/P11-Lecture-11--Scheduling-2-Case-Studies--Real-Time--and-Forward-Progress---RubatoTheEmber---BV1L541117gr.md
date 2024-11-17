# P11：Lecture 11： Scheduling 2 Case Studies, Real Time, and Forward Progress - RubatoTheEmber - BV1L541117gr

 Okay， I'm not sure if we're going to get speaker or not。 So as long as you guys can still hear me。 can you hear me still。 Say yes， somebody。 Okay。 All right。 so welcome back everybody we have a little technical difficulty。 So。 those of you that see me here get to see me。 Ta-da。 Maybe we'll grab it from course capture as well。

 Let me zoom into。 The tighter camera angle and so I want to pick up where we left off last time with scheduling。 And if you remember from last time。 We were kind of talking about scheduling as deciding which of a set of things that happen to be in a queue。

 Get to go next。 Okay， and so。 In particular， the ready queue is one of the things that we often talk a lot about here。 And so in that instance that's going to be， whoops， where did this go here。 This is going to be。 This queue right here。 Okay， and it's， it's the queue that feeds into the CPU。 So now。 Scheduling is basically making a decision。 And over the course of today and next time we're really going to talk more about possible scheduling policies。

 All right， and so if you remember from last time we talked about the simple policies like minimizing response time。 By minimizing the elapsed time for something to be done。 Or。 And the response time typically what a user sees right so when you're typing。 If it takes has to schedule a thread to get your keystroke to then put it up on the screen。

 That can be a scheduling question。 Another thing we talked about is maximizing throughput。 Okay。 and this is a。 Maybe maximizing the number of operations per second so you're doing some cloud computing。 And if you remember one of the things we talked about last time is that response time and throughput are。 Sometimes it odds with each other right because response time means。 Quickly preempt and go with。

 The thread that's the here just we can't do that let's just keep going。 Because I need the。 This is feeding microphone to people on zoom right now so。 So。 If you think about it minimizing elapsed time。 Is preempting for the thread that's going to do that。 He stroke maximizing throughput is really。 Not not preempting letting it run through so that you get good cash behavior。

 Okay， and then fairness was another thing that was a little。

![](img/4260482ca94a2a81e81abb1159ffd00f_1.png)

 Complex here and we'll try to get to that in a moment。 Sorry about the interruptions everybody。 So if you remember an example of round Robin。 With the time。 Quanta was really one of the things we talked about。 You know。 FIFO was the first thing but that's not very interesting。

 And so the way to think of round Robin really was that you have a set of processes。 They each have a burst time。 Which is the time they run until they're done and start doing IO or something like that。 And so in this example here we have P one P two P three P four with their burst times and a quantum of 20。 And so really， you know， this is not rocket science you can kind of work this through the P one。

 Runs for 20 units and then it gets swapped out because the quantum spin exceeded。 P two takes over。 It's going to end up only running for eight。 Why is that？ Well， because P two only has a。 And then P three runs for 20 P four runs for 20。 And then we go back around。 And so there's a file queue involved here。 When we pull something off the CPU we put it at the end of the queue and we just keep doing that。

 Okay。 And so then we talked about metrics like average waiting time and average completion time。 That are important metrics， especially the users who are interactive。 Okay。 and average waiting time is basically just adding up all the times that process has to be weighted in the queue。 And then dividing by the number of processes and average completion time is sort of just looking at the end。

 And adding those times up and dividing。 Okay， so I want to pause here because this is like the most basic schedule or other than FIFO which nobody actually uses that we talk about。 So were there any questions on this。 Because I'm going to assume that this is kind of yeah go ahead。

 Good question so our first time's pre calculated no first times are something we know about after the fact。 So that's going to be a little bit of a challenge when we try to do an optimal policy based on birth time because we're going to have to do some prediction。

 Okay， so all I've done for this slide is I've said well let's suppose that we knew in advance those were the birth time。 Okay， good question。 Any other questions。 Okay， so。 But if we knew the future。 Could we always mirror the best first come first serve so if you remember the thing about first come first serve was it's great if you go shortest job next shortest job all the way up。 And then you get the best average time for waiting and response time。

 And so we came up with this idea of either shortest job first or shortest time to completion first。 Okay， they're pretty pretty close to the same thing。 And the idea really is in shortest remaining time first is really that。 And it's all the possible things on the queue， if we knew the first time because we have a crystal ball。

 we would pick the one with the shortest first time and we just run it and then we pick the next one and we pick the next one。 Okay， and this is kind of where we were at at the end of the lecture we kind of rush through it so I want to make sure this made sense to everybody。

 The difference between s js F and s r t F is really just the preemptiveness so if you have s r t F and a new short thing comes in it will implement it will interrupt the thing that happens to be running on the process or if the thing on the。 processor has a longer burst time。 Okay。 And you know you can apply this the whole program or the current CPU verse。

 etc。 But the idea here is to get the shortest jobs out of the system as quickly as possible thereby making your average response time faster。 Okay。 And the way to think of us， I'll say this again。 is if we knew the future and a bunch of jobs came in， we rearrange them and do FIFO。 but we do it in a way that always had the shortest one first and the next one then the next。

 Any questions on this。 So I think in reference to the question earlier。 the issue here is that this seems crucially to depend on there being a crystal ball。 Okay。 that we somehow know what the various times are here for birth so that we can then pick the shortest one。 And so what we were doing at the very end last time was we were looking at。

 And then we had examples of SRTF and why it would be useful if we had it so this example was an example with two long threads and one interactive thread or one real time thread I'll say the long threads a and B will run for a week。 Okay， thread C has some very special special properties of it it needs to run for a millisecond。

 and then do a millisecond worth of disk。 And then run again。 Okay， and so if we have that situation。 you can see that it becomes very important that we somehow always start that thread whenever it's ready to go so the idea here is that one millisecond。

 It then starts a disk operation that takes nine。 And then right after those nine milliseconds are done it runs again。 and this will be the maximum throughput we can get out of the disk， it'll be a 90% busy disk。 but only if we manage to schedule this little thread。 Red when it's time to go。 Okay。 And so with first come first serve。 This is bad right if a or B gets in there。 They run for a week。

 the disc is idle， get zero percent out of the disk。 What about round robin or shortest remaining time first。 Okay， can anybody kind of guess。 What would happen with round robin here。 Okay， a lot of context switch so what do you need by that。 Yeah， so somehow， remember that round robin's kind of a blunt instrument。

 we would have to pick our timing， so that we're switching what every one millisecond so that we could somehow make sure that see always get scheduled。 But even that wouldn't necessarily work right， because you have to be ready to schedule the moment that it's the disk is done。

 So if you look here， here's basic。 For instance， that's the time I told you is pretty standard。 you run for one millisecond。 The disk runs for nine。 but by then a has started it's running for 100 milliseconds B runs for 100 milliseconds。 And then see gets to pick up。 And what do we get here our disc utilization is nine out of every 201 time units it gets to run and so our disc is down to 4。

5% of it's bandwidth。 So that's very bad。 Right， but all we're doing is we're switching every 100 milliseconds。 Now if we go faster what if we switch over one millisecond。 maybe we can get about a 90% like we want except that we've got a huge number of wakeups because we keep switch switch switching。 Right。 So， before we talk about alternatives。 Ask your questions。

 So does this make sense what we're talking about here。 Yeah。 Yeah。 so this is this is the disc is busy for nine milliseconds。 And then it's busy for nine milliseconds and then that's out of a cycle of 201。 Okay。 And actually it just occurred to me that I could probably use the camera on my laptop to at least give you guys a little bit of a view of me。

 Oh wait， that's not that'll take the mic out。 So no， I can't do that。 Okay， never mind。 Oh。 let's look at another option here。 So， SRTF is a much better scenario。 Why is that？ Well。 because the burst time of C is short， millisecond。 So anytime C's ready to be scheduled it immediately picks up and says， Oh， run C。

 but otherwise a or B get to run。 And the interesting thing about that is that when。

![](img/4260482ca94a2a81e81abb1159ffd00f_3.png)



![](img/4260482ca94a2a81e81abb1159ffd00f_4.png)

 A starts running both A and B were a week long， but as soon as they starts running。 A is now shorter than B and so A will always run in preference over B。 Okay。 Good question。 So if we could。 Yeah， go ahead。 How do you know what？

 How do you know the time of completion of a job you got a crystal ball。 Okay。 so SRTF is great if you can predict the future。 Okay。 so obviously you can't really predict the future。 And so， at least not yet I guess。 So。 we need to think of this as a guaranteed not to exceed good policy that we can get close to if we can approximate。

 So that's going to be where we go next。 All right。 I just want to make sure everybody's got it。 Okay。 So other questions on this before we move forward and yes indeed we have to predict the future。 That's why I told you guys all bring your stock portfolio today。 There does seem to be a little aggression in Europe that may be messing up stock futures at the moment anyway though。

 Okay， can I go on。 So。 And by the way the dis utilization is 90%。 Okay， so。 One of the obvious things I hope we can see here is starvation is a problem。 So if you have a huge number of small jobs。 They're going to completely overwhelm any big job。 And so in fact in this situation we see here at the bottom be never gets to run at all。

 At least not for a week。 Okay， so that's a problem。 Now somehow we got to predict the future that's also a problem so some systems might actually ask the user how long do you think your birth are。 Now in the case of that disc problem maybe they could say they know。 Because they met they run it a bunch of times by itself and maybe they measure it and it's regular enough they could do something。

 However， most predictions of that form are hard to do correctly。 And basically wrong。 Okay。 so you can guarantee that the best intentioned programmer has no idea how long it takes to run something。 And a malicious one is a course going to tell you what it only runs for a microsecond。 Why do they tell you that so they can run all the time。 Okay。

 so perhaps asking the user is not a good idea。 So the bottom line here is you can't really know how long a job will take。 but we're going to use SRTF is a yard stick for measuring other policies and it's optimal。 So you can't do any better so how is it optimal once again it's optimal by giving you the smallest average wait time。 And average completion time。 Okay， it's optimal in that sense。 Okay。

 So the pros and cons are optimal that's a pro。 Requires predicting the future that's kind of a con。 Okay， unfair。 Well， perhaps the world is unfair so we're not going to， but we'll call that a minus。 Okay。 So this one， whatever your notion of fairness is SRTF is definitely not。 So。 how do we predict。 Well， one of the things we can do is we can look at the history of runs of a given thread and predict based on that。

 So， come up with an adaptive policy that uses past behavior。 And it works pretty well in computer systems and the reason is most computer systems have high predictability in how they behave。 Okay， so asking a user to tell you exactly how long it takes to do something。 That's a not too good。 An option， but measuring it and building a model。 Might be a good option。 Okay。

 and this is Berkeley is like， you know， machine learning central。 So you can imagine that some form of machine learning might be good。 but we're not going to go that hard so we could use an estimator function。 which is much simpler something like a Coleman filter which you probably run into and like one of the 16 series classes。

 And so the idea is if you know a stream of previous histories。 you put them into a function that might give you the ability to estimate the next first。 Okay。 And so a simple one here is this idea of exponential averaging。 where you have an alpha parameter that tunes kind of between the， the immediate past。

 and the aggregate past。 Okay， and so basically you do alpha times the last time。 plus one minus alpha times this。 Overall average， and that gives you the new average and I realize that there's some subscripts here that got lost in the transfer somehow。

 But this is pretty simple。 It's an averaging window。 Okay。 and this is something you've run across many times。 And if we did that averaging window。 that would basically say， well， this thing behaves kind of like an average of its past behavior。 And either do that in a way that sort of keeps an infinite version of the history in the past or just uses a couple of past values that are averaged together these are both two options you can do。

 So， questions on that before we go on to lottery schedule。 So， I guess， idea。 I'd use the prediction from this filter as my burst time for each thread。 I gather that history and then as it got more and more accurate。 then I'd use that to schedule so whenever the threads in。 So， they're ready to。

 I would associate it with its model and use that to decide which thread is the shortest remaining time and bring that forward to run。 Yeah， question。 So， it started probably with， I don't know some short amount of time 10 milliseconds or something these these kind of filters。

 especially when they only have one parameter or two parameters they adapt really quickly。 To the average。 It's if you have a really many parameter model that it takes a while for it to adapt。 So， it would be a good medium time and it would quickly be erased by the actual values。 Good question。 Any other ones。 Okay， so this is one way of predicting the future。

 I'll show you something else。 So here's a question。 What's the difference between first come first serve and shortest job first。 So。 the shortest job first is like the optimal first come first serve where it finds it resorts the queue。 like putting the shortest first and then next and next。 Okay， hopefully that answered that question。

 So， all right， so let's talk about some more interesting scheduling mechanisms now so lottery scheduling is a is a pretty interesting idea where what we're going to try to do is hand out chunks of CPU time to processes。 Okay， and so we're going to give each job some number of lottery tickets and we're going to run a continuous lottery and proportional to the number of lottery tickets you are you get that many time slices。

 Okay， so if there's a hundred total tickets， somebody has five that will on average get 5% of the CPU。 Okay， because every time the time timer goes off you run a new lottery。 see whose ticket it is you go forward。 Okay， and so how do we assign the tickets well to approximate SRTF。 We have something that uses the models to kind of put short running jobs。

 First by giving them more tickets and long running jobs getting fewer tickets。 Okay。 and what's interesting about lottery scheduling， and several the other ones we'll talk about later in the lecture is we can we can avoid entire starvation by making sure that anybody who's in the system always gets at least one ticket。

 Okay， so in the case where there's a hundred outstanding tickets。 making sure everybody gets at least one ticket means that they get at least 1% of the total CPU no matter what happens。 Okay， so I will contrast this with what we talked about when we talked about priority scheduling we'll get back to that again。 where if you have enough high priority things the low priority things never run。 Okay。

 whereas with lottery scheduling you can arrange to the low priority things at least get to run a little。 So the advantage over strict priority scheduling in this instance is it behaves gracefully as a load changes。 and it adds or deletes a job。 As you add a deleted job it kind of proportionally slows everything down so you could say。 when I add a new job， I add another some number of lottery tickets into the system that will gracefully slow everybody down。

 Okay， so that's one thing that we can do by adding adding or deleting a job basically affects everybody proportionally。 So there's a lot of ways to play with lottery scheduling。 Here's a here's an example。 where we have some short jobs get 10 tickets long jobs get one ticket。 And so then in an instance where you have one short job and one long job。

 The short job gets 91% of the CPU and the long job gets 9% of the CPU。 In the case where you have no short jobs and too long jobs。 then both of the long jobs get the same amount of CP。 And so on you can look at other ones here like if they're 10 short jobs and one long job。

 then each of the short jobs gets 9。9% and the long job is 0。99%。 So you can play with these a lot。 but can anybody remind me why in this particular example， I'm giving more tickets to short job。 what would be my goal there。 Yeah。 That's right， why do I want to get the short jobs out of the system as quickly as possible。 What started us down this path。 Yes。 Lowest average wait time， yes， leading to。 Responsiveness， yes。

 So if we're interested in a mix of interactive and computing jobs。 We want to somehow figure out how to give the short jobs。 Some precedence。 And the assuming that you've modeled them somehow then the lottery scheduling gives you a nice clean way to do that。 Where you don't make， you don't basically give 100% precedence to the short jobs。

 the long jobs still get to go。 So there's no permanent starvation。 Now， of course。 if there's too many short jobs to give a reasonable response time。 That it's really hard to make progress， right。 And so this example that I gave earlier。 Actually。 I don't think let's see where did I give that example so for instance。

 if we have 10 short jobs and one long job。 You know。 the CPU that the short jobs get starts decreasing。 And if I have 100 short jobs。 It's going to go down and down and down and none of those jobs are going to make forward progress。 Okay， so this none of these scheduling mechanisms。

 Fixed extreme over consumption extreme over commitment of resources。 And you know。 you should keep that in mind。 At some point， it's possible that you just need a faster computer。 Okay， so scheduling is something that you use。 And you get sophisticated at to do a good job of dealing with resources that are contended by multiple players。 but it can't fix extreme lack of sufficient resources。 Okay， so keep that in mind。

 That's important to know。 Yeah， question。 Okay。 Say that again。 Yeah。 so if you had a lot of short jobs， let me make sure I understand your question。 But you had a really fast CPU or you had a lot of cores。 That could be fun。 Yes。 Because in that situation， you have enough resources and the scheduler can help hand them out。

 So schedulers can't make up for completely insufficient resources。 but it can do a good job of distributing the ones you've got。 Yes。 So。 so they all have an associated quanta was your question。 So what happens with the lottery scheduling is you have a big set of tickets。 Okay。

 you guys have all seen bingo right there， you know， they roll the ball。 You know。 and they say which token wins， but they just throw the ball back in in this case so you just keep randomly choosing。 Yes。 Yes。 So remember now。 In this instance， so the question was。 does the long job just keep going until it's finished。 Really by a long job。

 I'm talking about something with a large burst time。 Okay。 which really means that it's got to run all of its instructions and then it goes to sleep on an I O Q and later it'll wake up again and be long again。 So really what we're talking about here is that long jobs and short jobs represent how long they need to stay into the CPU。 but the quanta here is shorter。 And so when you draw a ticket。

 maybe it lets you run for five milliseconds。 And then you wake up and you get another guy gets to run for five milliseconds。 The long job might run for many of those five millisecond chunks。 whereas a short job would run for a few of them。 Good question。 There was another。 Yes。 Yes。 So in this situation， we are only talking about jobs that are already on the ready queue and can run。

 So the only resource we're talking about right now are things that are contending for one CPU。 Things that are sleeping on I O Qs， but happens is when the I O comes in。 they get taken off the I O wait queue and now they're put back on the ready queue and they become a new job。 That's contending。 Good question。 Any other questions。 Now。

 lottery scheduling has been around for a while。 What's interesting about it is assuming you know how to distinguish long and short jobs。 which is challenging。 It's a good way to give a smooth fraction of the CPU to different jobs in a way that doesn't have starvation。

 Okay， there's going to be others and we'll get there in a moment。 Okay。 So。 how do you actually evaluate whether a scheduling algorithm is better not。 Well。 one thing you can do is you can somehow build a mathematical model and come up with a deterministic modeling of that。 And the problem with that is that you have to not only define the scheduling workload or the scheduler mathematically。

 which you might imagine lottery scheduling has a mathematical description。 But you also have to describe all of that workload。 all the apps that are going to run against it mathematically so that then you can somehow combine it all together mathematically。 Okay， this is a great aspiration but very rarely works out well because it's just too hard。 Okay。

 so another is you can do a little better sometimes than fully deterministic modeling with a queuing model。 And we'll talk some some about queuing theory later in the term we're not going to go there now。 What people mostly do is they build a simulator that has a scheduler in it。 Some some approximation of the scheduler you're trying to test。

 And you've taken a bunch of applications and you measure a trace of how they behave。 What are all the birth times。 Okay， and you leave those and you take those traces and you can feed them into the scheduler simulator to see how the scheduler does。 And that why you would do that rather than actually running it is building a full simulator and putting it into Linux is a lot of work because you got to debug it you got to make sure it does all the right stuff。 Whereas if you have a new scheduling algorithm and already you should start to think there's many of them right if I give you that impression。

 there'll be more。 But you can build a model of a particular scheduling algorithm you can feed traces to it without having to fully implement it in a real operating system。 And without having to take all the time to really run all of the applications。 Okay， and so this is。

 you'll see scheduling papers from the past， where they did， they did simulation。 Okay。 because it's usually something that systems people can do pretty well。 Okay。 And it's usually it can end up as accurate as some of the other more mathematical models because the mathematical models you have to approximate so many things that they're not always that accurate。 Okay。 Questions。 So how to do simulation without building the real thing is a question here in the in the chat and the answer is imagine。

 since we're scheduling based on burst time what you do is you have input files that represent all of the burst times of the threads for application one application to application three。 Read them you store it into a simulation of the ready queue， you have a simulation of the scheduler。

 It pulls the next thing off but then you say well it was a burst time of 12 I'm just going to pretend it ran for 12 and I'm an advanced time for 12。 And you keep doing that and then you don't actually have to run the real thing。 Okay。 We can talk more about that another time。 So now let's go back to our goal for these lectures which is how do you handle a simultaneous mix of different types of apps。 So even kind of implying that if you have interactive and computational things together at the same time。

 You want to do the best thing you can for everybody。 And then you want to sort of said heuristically like well if you just make sure the short ones always run。 and then the long ones keep making progress you're probably okay。 But really。 the tricky part is you can have computational apps that go through phases that do a bunch of short IOs and you can have interactive apps that go through places that do a lot of computation。

 And it's always easy to know for sure just based on the burst size whether the thing is interactive or not。 Okay。 And then the other funny thing is if you think about all the computers you interact with。 say even right now on your way between here and home。 You've got your laptop you've got your phone there's stuff in the cloud there's lots of different types of computers。

 and a good question could be should they all have the same scheduler。 What do you think。 Yeah。 Probably not。 Why not。 So they're very differently constructed in terms of computational power yes。 and the application makes it's very different。 Yeah， go ahead。 You're going to say that sorry I stole your thunder thunder。 Okay， so， you know。

 so for instance we said something about maybe first time is something we can observe and build a model on short burst mean interactivity mean high priority。 I mean these are questions。 And what's interesting about this is if you look at all the schedulers that have run over time and different operating systems。

 They actually have at their base some assumptions that the people that designed the scheduler put in there to try to figure out whether something's interactive or not。 So to give it more priority or not。 And I'm going to show you one in a moment。 called the 01 scheduler from the original to 2。0 version of Linux that was supposedly great because it was order one so it wasn't computationally expensive。



![](img/4260482ca94a2a81e81abb1159ffd00f_6.png)

 But it had a lot of heuristics to try to recognize application types。 Okay。 And so， you know。 again what about apps that sleep for a long time but then compute for a long time or apps that run under all circumstances periodically。 etc。 Could be a problem。 So， think， think that recognizing apps is hard。 So what about this。 So this is what's something that was done in several operating systems call a multi level feedback scheduler。

 So what you should see here is you see a bunch of cues and the top cue feeds into the second cue feeds into the third cue。 etc， etc。 And each one of these cues potentially has a different scheduler on it。 Okay。 and the way I've got this here is for instance the top cue is around Robin with quantum equal to eight the next cue is around Robin with quantum equal to 16。 And this one is a cue is a is a first come first serve。

 And this is a way of exploiting past behavior this showed up very。 very early in the game in the CTS system。 And basically every cue has a different priority and a different scheduling mechanism。 And so what you do is you start by putting a thread up top。 And if it turns out that it's got such a short burst time that it doesn't exceed the top quantum。

 then you keep putting it up top。 But if it exceeds quantum equal to eight。 you then put it into the quantum equal 16 cue， and it runs with lower priority。 And if it exceeds that one， then you put it into the bottom cue where it runs with the lowest priority。 And so， and every cue can have its own scheduling algorithm I'm showing you here to around Robin's and a first come first serve。

 And there's many versions of this。 And we can adjust each prior jobs priority is the way I said where you start at the top and you kind of work your way down。 Why the heck might we do something so complicated。 What are we getting after here。 Okay， so。

 you're on the right track you said you could have an interactive cue and a non interactive you right now there's just this structure。 How does this help us figure out interactive versus non interactive。 Yeah。 So the interactive ones stay toward the top because they have really short first。 And the compute computational one stay at the bottom。

 And if you have ones that kind of have short bursts and then a few long ones。 They'll filter their way down but they'll never get to the bottom because they'll get back up to the top pretty quickly。 Okay。 And you get back up to the top when you end without exceeding a quantum so here。 You could think of this as a way of approximating。 As our TF as well。

 So this is like trying to get a crystal ball by by going after what the history was。 But the history in this sense is which cue did you land it。 Okay。 And this by the way is very was very common in a lot of operating systems to have multiple priorities with multiple cues and ways of feeding one into another。 Okay。 And， you know， the long running compute tests keep getting demoted down to the bottom。

 So the result is kind of like our TF because the CPU bound jobs dropped like a rock to the bottom short running I owed jobs stay up top。 And now we have to figure out how to schedule between the cues because I've just introduced priorities。 High priority low priority in between。 So how do I deal with that。 So one idea is fixed priority scheduling you always do everything at the top first and then the next you and then the next you。

 Or we could time slice。 So that each cue gets a certain amount of CPU times the first the top one gets 70%。 The next one gets 20% the next one gets 10%。 So， can somebody tell me which one of these they might favor and why。 Go ahead。 Which one。 You want to fix priority or the time。 Okay。 Okay。 so if you notice here the fixed priority scheme has straight priority so that the short ones always run first。

 So the question that you should be thinking about is why might I do time slice instead of fixed priority maybe that's the way I should ask the question yeah go ahead。 Yeah， so the time slice version is avoiding starvation of the poor jobs that happen to fall to the bottom。

 Because we're continuing to give them at least 10%。 So it's kind of like priority。 but with an out to make sure these guys already run always run a little bit。 Okay now。 Notice the heuristic we're talking about here sort of starts things at high priority and slowly demotes them。 If they run too long。 You can imagine an arbitrarily number of interesting complex heuristics to try to assign what you things are in。

 And pulling it up or down based on how it's behaving isn't that what we've got here。 If it behaves with a bunch of short bursts it close to the top of it behaves with a lot of long bursts it close to the bottom。 And then we schedule based on that。 Okay， and you could almost imagine this is a very simple idea but you could have something more complex。 Where every job that comes in gets classified by some heuristics put on a cue and scheduled with that cue。

 And now， whoops， we just lost our better camera back and now the question is。 how do you build those heuristics。 And why not just say well， doom。 Okay。 I like doom we're going to call that interactive and I like this other thing。 Okay。 and we're going to just keep。 Classifying apps in a huge table。 Okay。

 you can imagine heuristics like that。 And you know the history of scheduling and operating systems is kind of rife with people trying to do exactly that。 Okay， so， and an interesting thing I will tell you here is once you start having heuristics complicated or not。

 You can start thinking about this as the user。 If they know the scheduling policy can now be foil can foil the policy。 So they can come up with countermeasures like if a user wants a lot of CPU。 what they do is they do a bunch of print apps because those are I also make short bursts for them。 and they'll stay at the top and they'll get a lot of CPU。 Okay， and in fact。

 in the early days of computer games where you have to a fellow program playing with each other whatever。 So， there's actually an example of somebody who figured this out and one of the fellow programs got a lot more CPU time because they figured out to do enough I always to keep themselves to the top of the scheduling queue。

 Okay， so heuristics can be gained。 Let's talk about the Linux 01 scheduler。 Okay。 so this was in the two。0 version of Linux。 It had 140 priorities。 Okay。 where now lower here is higher priority。 The bottom hundred priorities， 0 to 99。 So， you know。 so we'll call real time priorities。 All right， and the top 40 were ones that were used by regular user programs。

 Okay。 So there's 40 for user tasks and that's set by a nice， how many people have discovered Nice。 Okay， so nice is a program that you run in the shell that says okay this guy's running but make it higher priority or lower priority using that。 And unfortunately for many people running on shared machines you can only make the entire priority if you're super user。 Okay， you can always lower your priority。 So what was good about the 01 scheduler was it had lots of options。

 And run real time stuff we'll talk about that in a moment on the lower priority ones。 and it had a bunch of heuristics in the high priority ones to try to figure out whether something was interactive or not。 and to move things among those 40 priorities。 Okay。 and there were two separate priority cues and active and expired queue。

 And so the way that it avoided starvation was， it would take all of the jobs。 and it would run the highest priority first and the next and the next。 Meanwhile。 new jobs would come in on this other inactive thing yet。 And then when you emptied out everybody on the active queue you'd swap them。

 And you'd run the next one and swap them and run the next one。 And so as a result。 you made sure that every priority got to run a little。 Okay， and it adjusted the quanta downward。 So， so that as you went down you've got less and less of the CPU。 Okay。 and so the time slice dependent on priority was linearly mapped onto the time slice range。

 And then you've got a multi level queue， one queue per priority so you can think this is like there's 140 cues。 Okay， and execution got split into time slice granularity chunks。 And it was round robin through priority。 So this is kind of like。 we took all the stuff we taught between last class and this one。

 and he put it all together into 140 priorities， and you decided you wanted to have real time stuff at the same time you had interactive stuff。 You might come up with this。 Okay， I could imagine this would be something you might come up with over coffee sometime。

 All right。

![](img/4260482ca94a2a81e81abb1159ffd00f_8.png)

 All right， and this is just showing how the two users swap。 And the thing about the 01 scheduler was there's a huge number of ad hoc heuristics。 So if you look at those 40 priorities， what it did was it tried to you take the nice value that was given oftentimes right in the middle。 because that's sort of the default。 And then based on its assumption。

 It's observation and some heuristics， it would even move it would move it down in priority or up in priority plus or minus five。 Purely based on whether it thought something was interactive or not， and it did that on heuristics。 Okay。 So heuristics plus or minus five in the priorities they had they would compute sort of how often it sleeps and use that to decide what to go up or down。 give you something called an interactive credit。 You earn credit when you sleep。

 you spend it when you run a long time。 You get some here hysteresis so you're not flopping around in your priorities。 Whatever you come up with the interactive ones get to run more。 Isn't this great because it solves all of the world scheduling problems。 Okay。 And then the real time tasks don't do this adjustment on priority they run strict priority。

 Because if you've decided you really want them to run in a certain priority you do。 How many people think this sounds great。 I'll have a couple of you yeah there was a question go for it。 So hysteresis is basically anytime you have something that's， say， moving a value back or forth。 Hysteresis is a time averaging concept of trying to prevent it from flopping too rapidly so when there's。

 you have to wait for the pressure to raise it to be around for a little while and then you raise it。 And then hysteresis is preventing it from flopping the priorities frequently。 Okay there's lots of different types of hysteresis you'll run into over time here but。 So this sounds flexible。 I will tell you Linus hated the old one scheduler it got so complicated and let me tell you why you put in some heuristics。

 You're trying to do better at your scheduler but you don't want to piss off your existing application holders because they already know how the scheduler is supposed to behave。 So if you change anything you got to keep the old heuristics in there maybe you have some new ones and the heuristics get more and more and more complicated。

 And there's an implicit assumption that your users will always， you know。 get the same heuristics they had before。 Yeah， messy。 All right。 And so by the way it got。 but it got punted for something we'll talk about later in the lecture。 Okay， so we have the exam。 This is。 Oh， I guess this is this type here so our mean is kind of around 53 or so。

 If you have any regrade requests they have to be in by Sunday。 Okay。 Solutions are posted。 I've already seen there's a thread up on Piazza for people asking questions about solution。 So。 please do。 I want to apologize for the size of the answer key boxes or the answer boxes that was really not。 A good thing we this was an experiment to see whether it made everybody's life easier and I think it certainly made your lives harder。

 So， we'll do something better next time。 So this is。 I just realized that these numbers are actually not correct at the moment。 Somehow I put in the right answer the right。 I put in the right。 Herb and then it seems to have disappeared on the version I'm showing you so this is not correct。

 But the numbers I remember roughly was that the mean and median were pretty close to each other about 53。 That's about the right number and that tends to be about a B。 Okay， so that's a good question。 Project one final report do next week。 Also next week we have pure evaluations。 So what I want to say a little bit about why we do that is we're very interested in how your groups are performing。

 Okay， and so the key idea behind。 Here evaluations is to get us give us a flavor of who's contributing what in principle if there's somebody who's not contributing ever anything at all。 In principle， we take a zero some approach and some of the points from people who are not contributing at all get transferred over to the people that are。

 Okay， but this is based on a lot of things， especially your TAs understanding what's going on。 Part of the data that we want to understand what's going on is the peer evaluation process which everybody needs to do。 And the idea is simple。 If you have four partners or if you're in a four person group。 Your other partners are how many of them are there three right those are the other not you。 Okay。

 four people。 The other people are the three people that are out there。 Every person in your group gets 20 points。 You add it all up that's 60 total points and you can hand that out to your other members any way you want。 Okay， you can't give yourself points。 You are notoriously bad judge of how good you are。 We don't we don't want to know how good you think you are we want to know how you believe the other folks are working and we want some justification based on。

 you know， right， right up what you say。 Okay。 Questions。 So if you're in a three person group。 how many people are in the other。 Two。 The other is not you right so three minus one is too。 How many total points you get 120。 You get to distribute 60 times to wherever you want。 Okay。 do we got or not 120 40。 You get to distribute 40 however you want。 Okay。 Good。

 If you're in a two never mind。 Okay， we won't go through that anymore。 Okay。 Any questions。 I will point out by the way that the first midterm tends to be pretty hard in this class because it's about synchronization which is one of the hardest topics in this class。

 Yeah， go ahead。 Yes。 Well， they're kept。 We know them。 Now we're not going to tell your we're not going to tell your group members。 unless you want us to what you put in your evaluation。 And this is just one of many tools we use to try to figure out how you're doing。 Okay。

 Your TA is your， your main person who needs to know how you're doing。 Okay。 so make sure they know how you're doing and they find they see you at design reviews。 They see you in section。 Okay。 Questions。 All right， so let's go forward。 So does the OS schedule processes or threads。 Well。

 many textbooks use the old model with one thread for process。 So in a lot of cases。 if they don't make it clear， they're talking about a one thread for process thing and they might say schedule processes when they mean schedule threads。 Switching threads versus processes have different overheads。 We already talked about that。 So switching processes has more overhead because you're switching the translation tables and flushing TLBs and so on。

 Okay。 And if you remember， however， simultaneous multi threading is a good example where the hardware switches for you and that's fast。 Now， multi core is something we haven't talked a lot about in this in this class so far。 but algorithmically it's not a huge difference from single core scheduling except that there's more cores to use。 Okay， but one thing where it is very interesting is you can have a per core scheduling data structure for reasons of cash coherence。

 etc。 But you can have what's called affinity scheduling so affinity scheduling says if I have a bunch of threads and thread a was right was running on core one in the past。 The scheduler might try to keep affinity with core one and rerun that thread on the same core。 Why？

 Well， because there's better cash state better TLB state， etc。 Okay。 So one of the things you can take advantage of differently in multi core than you could in single core is affinity scheduling。 And let me show you a different one。 Okay， so we talked about spin locks that look like this where a choir says while test and set。 You know， wait， and the release that's required release is set the value to zero。

 Now is this a good thing to do。 Well， we said no。 Why not。 Busy waiting， right。 we're wasting cycles。 Yeah。 However， when might this be preferable。 Well。 when you have a multi core and you can make sure that the threads that are synchronizing are on different cores and running at the same time。 It might actually be better to do a spin lock on one core if you know the other threads running on the other core because it'll keep running and release you and go forward。

 Okay。 So， the only way and by the way， this is what that test and test and said I talked about really comes into play。 Okay， because then you're not wasting a lot of memory bandwidth。 And basically that looks like this you basically say while the lock is taken。 Just have a really tight loop here。 And then as soon as it goes to zero。

 then you do the test and set。 And this test and test and set actually avoids problems with ping ponging of values。 But you only time you want to do spin locks is when you know for a fact that the person that might be the thread that might be releasing is also running on a different floor。

 Makes sense。 Okay。 And so the only way you do that is with all gang scheduling。 So we talked about affinity scheduling couple slides ago gang scheduling is a simple idea that if you have threads that are known to be working together。 you gang scheduled them so that they are always running simultaneously on a set of cores。 And so there's a lot of multi processor gang schedulers that you can use。 Okay。

 and we won't talk much more about them。 And so there's some alternatives where the OS kind of tells the parallel program how many processors are actually running。 And we're not going to talk about that right now。 But I do want to talk about something else。

 which is real time scheduling。 And that Tesla we talked about that better stop when you hit the brakes。 or when it decides you want to break。 So， the goal of real time scheduling is very different from the goal of the scheduling we've talked to up until now。

 right， the set of goals we started out with last time and this lecture as well。 Minimizing response time or maximizing throughput or fairness。 Okay。 the case of real time scheduling is that predictability is more important than any of those things。 It's far more important to know that when you hit the break。

 The breaks will engage in less than pick a number， nine milliseconds， whatever it is。 so that you can design the hardware to do that。 Okay， so that's a real time requirement deadline。 Okay， and we don't care if it happens in two milliseconds， or seven or nine。 It's just got to happen by nine。 Okay， and so if we can use scheduling to guarantee deadlines without worrying about the fastest possible but the most predictable possible that's where we get into real time。

 Okay， everybody see the difference。 So you can kind of think of the previous things the previous goals were really optimizing up some performance metrics。 This is optimizing a predictability metric。 Okay， different problem。 So hard real time is typically when you have time critical safety oriented systems。 Basically。 you got to meet all the deadlines。 Because if you don't somebody might hit a deadline， right。

 so this is， this is a situation where you're kind of dealing with the breaks in a car。 or you've got a heart monitor in a hospital and there's some deadlines there or there's other things。 These are hard deadlines that have to be met。 And there's some pretty good standard things I'm going to show you the earliest deadline first scheduler but there's also least laxity first and rate monotonic scheduling。 etc。 So， software real time is like hard real time but softer。 Don't think about that too long。

 It's basically says that missing a few deadlines is okay。 Because nobody will die。 Good example of that is video right so video you can occasionally miss a frame without noticing too badly right in fact you could often pick it up。 So， good video and coders will be able to adapt to network problems by dropping frames and doing other things。 Why is it real time at all well because you need to have a frame every well defined period of time。

 but we call it soft real time because we can allow a little bit of flop。 Okay， so the， you know。 slop， not too much slop but a little bit of slop may make it easier to implement。 Okay。 and there's some examples of that which if you take 262 with me we'll talk about， for instance。 the constant bandwidth server， which gives you soft real time by using earliest deadline first did a clever way。

 Okay， question。 So the most important thing to think about for real time is it's a little different than what we've been talking to up till now。 And for instance we're going to talk about what typical characteristics of a real time task are。 So rather than tasks having burst times in this case they have deadlines and known computation times。 So for instance here is a set of three threads and notice that we have the time when thread for arrives by the way time is left to right。

 So thread for arrives first in this great rectangle here represents the computation that that thread needs to do。 And over here， I'm sorry I'm not showing you。 Okay， so， there's a pointer。 So。 thread for arrives at this point the greatest of computation but the deadlines here。 So what you can get from this figure is that if we schedule that computation anytime between arrival and deadline we're okay。

 Okay， so that's C， which is the gray rectangle there has to represent worst case time of computation。 So a lot of these real time compilers and so on have to do very careful analysis of the code under all circumstances so that you know what the worst case compute time is。

 Okay， now take a look at these three， these four threads and tell me if you only have one CPU is this a valid schedule for those four threads。 Why are one up。 Why is that。 Well， the simple answer here is simpler than you're going for notice that we've got computing overlapping that's not possible with their only one。

 So， we're going to take a slice through time here you see we've got two things computing at the same time。 And so on the， on the chat here somebody says， not valid should prioritize test with earlier deadline。 Good idea。 So this is why earliest deadline first might actually be a good policy for us。 Here's why round Robin is not a good policy。 If what I do is I take that that set of things I showed you earlier。

 and I try to schedule them with round Robin， what you see here is that round Robin really doesn't have anything to do with deadlines。 So， we just sort of switches out on a quanta， right。 So if you look。 we have thread four is the only one in the system so it gets to quanta。 and then when thread three shows up and thread two shows up。

 Now we're alternating between four three and two， and then one shows up and now we're alternating between all of them。 And then， surprisingly we missed a deadline。 Why is that not surprising well round Robin has no idea about deadlines。 Okay， so why should it work。 Questions。 Early as deadline first assumes a couple of things so first of all tasks come in periodically。 So rather than a deadline， we have a period。 So what that just means is every time the thing arrives。

 One period later is the deadline。 One period later is the deadline。 So we look at typically look at periodic tasks。 And it's a preemptive priority based dynamic scheduling so every task ends up with the current priority。 It ends up with a priority based on when it arrives， computing its deadline。 and the test whose current deadline is closest to now is the one that gets to run。

 we'll preempt and run that。 So here's an example， where we have thread one has a period of four and needs one compute。 thread two has a period of five and needs to compute thread three as a period of seven and needs to compute。 they all arrive at zero。 All right， which one has the earliest deadline。 Number one， why。 Because it has the shortest period， which means that its deadline is for out。 Okay。

 And so here I'm just computing the deadlines。 Notice that thread one's deadline is here thread two deadlines here thread three deadlines here。 which ones the earliest deadline。 Oh， thread one。 So it's going to get to run in the first place。 But now at this point， now we have to start running thread to because it has the next earliest deadline and so on。 And if you work your way through this。 You'll find it works。 But with some constraints。

 does this always work for any set of threads。 Okay， somebody was shaking their head， why not。 Yeah。 why might the deadline be not possible。 Yeah。 So if I were to add up all of the blue here and it were to take more than 100% of the time。 It can't， it's not possible to schedule the CPU。 Okay。 And so the way we figure that out is take a look here this thread one really needs 25% CPU。

 Why do I say that it needs one unit of CPU every four units。 Okay。 And so you could imagine in the best of all possible world that perhaps if I added up all of those utilization and it was less than what。 What do I want to be less than if I had all the utilization up 100% or one。 Then it might work。 And in fact， even EDF of course won't work if you have too many tasks。 Just what we said。

 although P is for deadline here。 It's basically out of all the utilization if they're less than one。 you have a feasible thing。 Okay。 And so that is what's great about EDF is you can give a very simple feasibility test。 which is sufficient。 Okay， and necessary for this to be a scheduleable and you can run your run this very simple equation and see whether you can schedule it。 Okay， so questions。 Yes。 Ah， yes。 Very good。 I'm glad that you brought that up。 So he says， well。

 the scheduler has to trust what the user said。 Professor Cooby。 didn't you say at the beginning that the user never knows。 So this is impossible， right？

 I did you didn't say that， but I'm saying that， right？ So the answer is。 in the case of real time scheduling。 The only way you could schedule is if you have very careful tools that evaluate what the maximum compute time is。 and then you relay that information into the kernel。 So real time scheduling is a good example where you have to trust what comes in with the threads。

 Okay， but you know that behind all of that is some pretty complicated compiler analysis and so on to know。 Okay。 Good。 Good question。 Other questions。 Yeah。 How does it do it？ Well。 in it's very hard to get it right。 Okay。 And in fact。 what you need to do is it's worse than what you just said with computing number lines of code。

 You have to turn it into assembly and then you have to compute cash misses and figure out what's the worst case cash misses and then add it all up。 And under the， you know， all possible circumstances。 What's the longest it could be。 Okay。 not an easy cap。 Lots of papers。 We could point you to on people doing that。 What's kind of an interesting alternative is folks over in Corey。

 have even talked about building processors without any cash is there any other unpredictable things precisely so it's easier to get compute。 Okay， so you could imagine when you're doing a lot of real time scheduling you might actually build a custom processor to make it possible。

 Okay。 Now of course the， the goal would be to use a regular processor so you could do both real time stuff and regular stuff like watch videos。 And so， you know， then what has to happen is you have to way overestimate the computer。 Good question。 All right。 So， let's talk a little bit at one more topic here。 So。 I want to leave real time with you。 So what do you want to get out of the real time thing one。

 You need to have really good estimates on compute to the deadlines really matter。 especially if it's hard real time because， you know， somebody could die as a result。 So that's very important。 And certain schedulers like EDF allow you to compute upfront whether it's even possible。 Let me tell you why EDF is not always used。 The problem is that to order to run you。

 you notice how we're actually splitting。 We actually end up splitting things up if you were to follow it you would see that we pre up。 And some threads will run for a little bit and then be preempted and then come back and run。 Okay。 And I noticed I don't have that here in this example but it's that comes up with EDF。 And so。 you know， you may not want to preempt。 And so there are simpler things that don't require preemption that don't allow you to have this 100% utilization。

 So there's a bunch of different schedulers will talk and if you， you know。 come to 262 will actually talk about several of them。 So， let's circle back for a moment。 And then the next question is what starvation is what starvation is when a thread fails make progress for an indefinite period of time。 And starvation in this lecture is not deadlock。 That's kind of the next lecture。

 because starvation in principle can resolve。 So start a nation is a situation where you're not making progress。 But if the right circumstances show up， you'll eventually make progress。 So what are causes of starvation well scheduling policy。 For instance。 if you have a priority scheduler， and you're， you have a stream of high priority things maybe the low priority task never runs。

 That's starvation it's that deadlock because the high priority queue could finish and then the low priority thing would run。 Okay。 Now， deadlock is going to be distinguished next time by the fact that there's an actual cyclic dependency that can't even in principle be resolved。

 So， there's a straw man so called non work conserving scheduler。 where a work conserving scheduler is one that never leaves the CPU idle when there's work to do a non work conserving scheduler could trivially decide not to run stuff。 And now you got starvation。 Okay。 So we'll assume that we're not going to do a non work conserving scheduler because that's the bad idea。 So what about last come for a serve。 So this is a stack。

 So if you have this as a scheduling structure， a late arrivals run get really fast service。 And the ones that arrived earlier may sit back there in the depth of the stack and never run。 So this should be a pretty trivial about。 Pretty trivial clue as to why this has starvation。 Okay。 Now， of course， the flip side of life， oh， it's bifo。

 The problem there is if too many jobs arrived and there's not enough compute time。 Then the new jobs just never run。 So is first come for serve prone to starvation。 Well， if a task。 So this was from last time we kind of showed this example of the convoy。 where the red task runs for really long time and all of these things build up。 This， however。

 is not starvation because it eventually lets things run。 What would be starvation is if it gets stuck in an infinite loop。 Okay。 and that's why first come for service， not a particularly good general operating system policy。 And why we want to put preemption with timers into the picture。 Okay。

 but I will tell you some of the early personal operating systems actually could be subject to。 Is round robin prone to starvation。 Well， each of the end processes get one over answer the CPU。 Always。 And if there's a quantum cue， then you know for a fact that you'll always get to run。 In N minus one times Q milliseconds or whatever so there's no starvation there either。 Right。

 because you always get to run。 Now， of course， round robin then it's fair in terms of how long you have to wait。 It's not necessarily fair in terms of throughput because you can voluntarily give up your time slot and then you won't get that time back。

 How about priority scheduling。 That prone to starvation。 I mean。 people think priority scheduling is prone to starvation。 Okay， not too many of you。 Yes。 we've been saying it's prone to starvation the whole lecture。 Right。 So yeah。 why because you could have a bunch of high priority jobs and never let the low ones run。 All right。

 But there's more serious problem which I want to kind of close out with today。 such as priority inversion。 Okay， and this is a situation where even high priority threads might become starved。 Let me show you the example。 Here's a priority scheduler job one running at priority level one。 Doesn't acquire。 I'm a lot。 Okay。 So at this point。

 which job does the scheduler choose while job one was running。 but now we got three jobs on the queue which one gets to run next。 Well。 assuming for a moment that high priority is priority three。 not always a clear thing and you have to ask yourself but in this case job three gets to run。

 So what happens if job three runs and tries to do an acquire will acquire succeed。 Because the low priority job one already has a lot right。 So here job three is blocked on a choir。 Job one has the lock。 And so job three won't get to run until job one completes except job two is stuck there in the middle running。 Okay。 This is called a priority inversion because the low priority thing is preventing the high priority thing from running。

 And so whatever you thought you were doing with priorities by putting them in this priority it just failed。 Okay， because your attempt to classify priorities didn't work。 Does everybody see why this is a priority inversion？ Yes。 So why don't I let job which run。 To well。 but job to may run forever for a long time。 See， and as long as job two still has time to run。

 it's not going to let job one run。 So the point of this was。 if we let this run for a while and job two has a lot to do we're stuck。 Okay。 and and job three is stuck not making progress because of a low priority test that's a priority inversion。 And so we have to say it won't resolve but right now we're stuck in a priority inversion。 Yeah。 Yes。

 Great。 He says， would it make sense for job three to somehow change job one's priority to let this happen。 Yes。 So we'll get there in just a second。 Good。 Good question。 I paid him to say that。 So we're a high priority task is blocked waiting on a low priority task。 And the low priority one must run for the high priority to make progress。

 And a medium priority task can starve the high priority one。 You may think that this is ridiculously complicated。 But it isn't。 I'll show you in just a second。 What else might lead to this starvation。 Well， here's another one where the high priority thread does a spin lock attempt to acquire but the low priority one already has the lock。 Okay， now the high priority one's just going to be spinning in a loop and the low priority one's never going to run and we're never going to resolve。

 Okay。 So， here's the donation idea。 Very good。 So， right。 Job three tries to do the acquire。 It goes to sleep， but it gives its priority to job one。 And job one runs for a while until release。 And then the priorities are restored and job three gets to acquire no priority inversion。 Okay。 Great。 Everybody catch that you want to see that here we go。 Job three is blocked。 Okay， wait。

 let's go back here。 Okay， so job three tries to acquire job three block。 but it gives its priority job one job run runs releases the lock。 Job three gets to go and everybody's happy without priority inversion。 Welcome to project number two。 But let's close on something more interesting than project two for now。

 In July 4 of 1977 pathfinder lands on Mars。 Pretty amazing process of landing with balloons that bounced it out of orbit onto the ground and the balloons clap so it's great。 It worked perfectly。 First us Mars landing since Vikings in 1967。 Now we'll delivery mechanism as I said with with balloons around it and they bounced it out of orbit onto the ground and then the balloons deflated and the rover went off。 It's beautiful。 You know， the best example of technology gone。 You know， perfectly。

 And then few days into the mission。 Multiple system resets happen reboot reboot reboot。 That's the old。 That's kind of scenario where you've done all this great job of delivering a rover and it's not working。 Okay， the system is rebooting randomly。 I'm sorry。 How many people ever had that happen to a phone。 I actually had that happen to one of my phones， but。 What was the problem priority inversion？

 Believe it or not。 A low priority task， which is collecting data grabs a lock on a bus。 And then the high priority task。 Needs to grab that lock to actually transfer the data。 And meanwhile， there's a medium priority thing that's running。 It actually happened。 Okay。 and why did this reboot？ Well， fortunately， they had a watchdog that noticed the progress wasn't happening and it decided to reboot everything。

 So that it could keep going。 Why is that fortunate？ Well。 it meant that they could debug it from earth and figure out what was going on。 Okay。 and what they figured this out， believe it or not。 And the solution was。 Somebody in the instance in the interest of making everything be high performing decided to turn off the automatic priority or donation mechanism in the operating system because well that's going to waste time tracing locks down so we don't want it。

 And it turned out if they hadn't done that， this would never have happened。 But through debug。 Through the debug mode remotely from earth， they were able to go in and turn the tri priority and donation back on and voila。 they fixed the problem。 Okay， so if you think the priority donation is not necessary。 You will be surprised。 All right， so let's finish this up。

 So we talked about some traditional performance based scheduling for goals minimizing response time maximizing throughput fairness。 But then we introduced predictability。 So I wanted to make sure you were aware that real time schedulers might have a very different set of goals。

 We talked about round robin scheduling a little bit more。 Pros are it's better for short jobs。 We talked about the guaranteed not to exceed optimal shortest job first or shortest remaining time first。 We talked about the multi level feedback scheduler as an approximation of shortest job。 shortest remaining time first。 We talked about real time schedulers like we talked about lottery scheduling。

 The thing we didn't quite get to which we'll get to next time is the Linux CFS scheduler。 which is what Linus after getting really annoyed if you'll one scheduler decided to do instead。 All right， next time Anthony will be here teaching。 He's back。 So I will see you， Mignana。 but have a good rest of your day and have a good weekend。 Thank you。 [ Silence ]。





![](img/4260482ca94a2a81e81abb1159ffd00f_10.png)