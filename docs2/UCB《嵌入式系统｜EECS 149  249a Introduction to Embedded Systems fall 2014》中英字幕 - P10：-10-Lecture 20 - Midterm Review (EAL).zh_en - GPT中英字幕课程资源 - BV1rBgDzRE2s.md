# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P10：-10-Lecture 20 - Midterm Review (EAL).zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Good morning。So we are here October 28， you have a homework due today at midnight。

 we will be posting the solution at midnight so we won't accept any even slightly late homeworks。

Okay， so please get it in on time。The reason for posting the solution is so you can have a look at it in case it's useful for reviewing for the midterm。

 which will happen here on Thursday。Now， a couple of announcements。

 which I've summarized on both sides of the board here。

I have to change my office hours time tomorrow because we have this huge annual review starting tomorrow afternoon。

 so I will hold office hours from 10 to 11 tomorrow morning instead of from 1130 to 1230。

And I have office hours today as usual， from 2 to 3 pm。

Please try to find me if you have questions about the midterm， particularly or about your projects。

On the projects， we've gone through the project charters and we have feedback for all of you and what we'd like you to do is to meet as a team。

With a GSI。Preferably in one of the lab sessions that happens today， I mean this week or Monday。

 if if the Monday lab session is the one that works best for you。

 and what I would suggest is that as a group， you try to figure out which of the lab times has at least the possibility for you to consistently meet every week as a group。

Okay， because we would like every team to meet every week。

 even if just briefly with one of the GSIs and the best time to do that is in one of the lab sessions okay。

 and the GSIs will。you know be basically holding office hours during the regularly scheduled lab sessions。

 okay， so you should try to align your team with one of the lab sessions and then you will have one of the three GSIs who will be your primary point of contact。

 okay？For things like ordering parts， helping you deal with problems and so forth okay now because of this annual review and various events we have to slightly adjust the lab session times this week so today this afternoon's lab will occur from 3 to five instead of I think it's normally 330 to 630。

So it'll just be a two hour window， but if that's the one that works best for you。

 please try to come to that the Wednesday lab will also be shifted to one hour earlier。

 nine to 12 instead of 10 to one， I think is what it normally is。Okay。嗯。What did I forget？John。

 is there anything else that I needed to say？Okay， any questions about this， yes？I'm sorry。Yes。Soon。

So we're trying to do the alignment to do a good workload balance between the GSIs and the complication is that we also want to make sure。

that the team can meet once a week in a lab session that that GSI is responsible for。

 so there's sort of a matchmaking problem here that we need an operations research major to solve for us。

 any volunteers。嗯。So it's going to be a little bit chaotic。

 but where we will come to you with a proposal， if you show up in one of the lab sessions this week as a group。

 we'll try to make that GSI be your mentor if the load balance works out so you can be proactive if there's a particular time slot that works best for your group。

 then。You can try to steer things in that direction， modo workload balance for the GSIs。

Any other questions about this？So the project charters overall looked really good。

 I think it's going to be a fun time。Most of them were really quite ambitious。

 and so I encourage you。To， you know， you want to take a very scientific approach， right。

 So if you're planning to use。Sensors for， for example。

 know being able to recognize your classmates by recognizing their face and then being able to talk to them in natural language。

啊。Have some。Fallback plan Okay， so， for example， you know。

 a good general fallback plan is you have a problem statement and you'd like to assess。

The efficacy with which a family of possible candidate cs can address that problem。Okay。

 so you're going to want to make measurements of these sensors。

 you're going to want to do characterization and modeling of the sensors。

 and you're going to want to determine find a way to determine goodness of fit for those sensors for solving that problem。

The nice thing about structuring a problem that way is that it's perfectly okay if the sensors you picked can't solve the problem。

Because you've structured a scientific experiment to assess。That question， right？So。

Think of it in those terms， it's okay to be ambitious。

 but your goal is to do good quality engineering。Which often involves determining what cannot be done。

As well as what can be done？The other thing is we really don't want you to just hack something together and get it to work。

For the 30 seconds that it'll take to make the video that you can show us。

That's not good enough for a project， just having something that works。Is not。

I doesn't make a good project， okay？I'd rather see something that doesn't work with a good engineering analysis of why it doesn't work。

ok。So it's the engineering analysis that is really the most important part of these projects， right。

 not the snazzy demo。All right， any questions about that？O。有。In theory。

 you can come to the demo day and say， this is how you fail， yes。Absolutely。嗯。

With a good characterization of the。The problem， the sensors， and what you know why？

This thing couldn't be done within these requirements， you'll do fine as a project。Okay。Yes， John。

Oh on on the question of ordering parts， some of the projects have， you know， in the charter said。

 well， we want to use this particular processor board and Im there's no good reason given。

 and I'm suspecting the reason is that。Oh， I used it in a class last semester and so I know it。

 or I've got one in my drawer or something like that， that's not a good reason。Okay。

 and we won't accept that as a reason for using that particular processor or board。

The reason has to be based on the capabilities and how well they match the problem that you're addressing。

 and we've got a bunch of very good， very。Modern platforms available to you。

We're not going to buy a platform with equivalent capability just because it's one that you like better for some。

Unbeknownst reason， okay？嗯。So you if one of the platforms that we already have has equivalent capabilities to the ones you're proposing to use。

 well， I mean， if you insist on using the one that you're proposing to use。

 you'll have to spend your own money on it because it's not a good use of our instructional funds to buy an equivalent platform without a good justification。

If you have a good justification， by all means。Make the case。ok。But otherwise。

 you plan to use one of the ones that we have。All right。



![](img/585abce8ecde6900d13696a86c61b40a_1.png)

O。So。Today we're going to talk about scheduling and kind of wrap up the discussion about scheduling。

 and I want to。Tell you， you know， we're basically。

 I'm covering real time scheduling in two lectures。

At a lot of other institutions you can take a whole course on real-time scheduling because there's a lot of professors out there scattered around the world who do realtime scheduling as a living。

 that's all they do right and so any course you take from them is going to be an entire semester of real-time scheduling so you're getting a little snippet into it。

嗯。And but it's a big subject， okay， but hopefully this snippet is enough。To give you both， you know。

 the basic knowledge to kind of recognize the terminology in the field。And also。

 my goal is to give you a little bit of skepticism。About it so that you know when to say，h。

 I don't know that I really trust that。Okay。So that's why to some degree， you know。

I'm going to emphasize over and over again that the most important thing with these scheduling results。

Is understanding。What the problem is that the result is purporting to solve。

And you have to recognize that that problem is often not a realistic problem。Okay， so for example。

 rate monotonic scheduling， you assume you have end tasks invoked periodically。

 the periods are well defined and you have worst case execution times for all of those tasks。

These tasks are independent of one another， which makes you wonder why they're running on the same machine。

They have no interaction with one another， which makes you wonder why they're't running on the same machine again。

There's no mutual exclusion locks， there's no precedence relationships。Not a very realistic scenario。

 All right， Nevertheless， the result does give you some guidelines。

 and it's a pretty result from a theory perspective。 So you know， it's worth knowing about。 Okay。

 so the theorem says。That if any fixed priority assignment yields a feasible schedule。

 then priorities ordered by period will also yield a feasible schedule。

And it's important to realize that this doesn't say anything about this being the best schedule。

It just says。Of all the schedules that will schedule a task once per period。

If there's any schedule that will do that， then the rate monotonic schedule will also do。

That's what it means to be optimal in the sense of feasibility。Okay。

So the most important thing about understanding this is not understanding how to prove it。

 which isn't that hard， it's just a little tedious， okay？

But rather understanding what the problem statement is。And what the theorem says and doesn't say。

It's important to know what it doesn't say。Yes。Yes。Well。

 when you say optimal in the sense of performance， you don't necessarily mean that it's the best performing。

You mean that。Among all the schedules that match that performance。

If there's any schedule that matches that performance。

 then the one that you're asserting is optimal also matches that performance。

It doesn't say anything about that being a unique answer。And this is the same thing。Right。It's。

If there's any schedule that's feasible， this one will be feasible。

But it there's nothing unique about this schedule。 There may be another one that's feasible， also。

Exactly。Which is really the same thing you say when you're asserting that a schedule is optimal in the sense of performance。

It's not necessarily the only schedule that's optimal in a sense。All right。

 so that's rape monoonic scheduling。 Then the second big one that we talked about last time was。

Earli as deadline first。And that is。Right here。嗯嗯。嗯。And。This has a couple of changes。

 One is that first of all it。Allows priorities to be dynamically changed。Secondly。

 you don't need to know ahead of time what your tasks are。Thirdly。

 you don't need to have periodic tasks， the tasks， a task becomes available， arrives。

And is ready to execute at an arbitrary point in time。

Okay and now it has a deadline associated with it， so that means it has to execute by that deadline。

So completely different problems。Nevertheless。The two can be compared right if you happen to have periodic tasks。

 you could say well the deadline is to execute the task by the end of the period each time and the arrival of the task is it arrives at the beginning of each period so you can sort of you know you can come up with problem scenarios for which both theorems apply。

But there are definitely problem scenarios for which this theorem applies where the other one does not apply。

Okay。So the earliest deadline first result due to Hor says that if you're given a set of end independent tasks with arbitrary arrival times。

Then。呃。The optimal algorithm。An optimal algorithm is one that at any instant is executing the task with the earliest absolute deadline among all the tasks that are available to execute。

ok。So。And this is optimal in a different sense， it's optimal with respect to minimizing the maximum lateness。

ok。So there's a couple of nice things about that in that this gives you an optimality result。

 even if you miss deadline。Whereas rate monoonic scheduling doesn't say anything about infeasible schedules。

 just the theorem says nothing about infeasible schedule。Okay。But here。

It does say something about infeasible schedules， it says that this will actually perform at least as well as any other scheduling algorithm。

Even if you missed deadline。But at least as well means minimizing maximum lateness。Okay。

So that's the problem state。Yes。This does not ensure that you will adhere to all the deadlines。

 However， it's easy to show that if you're optimal with respect to minimizing the maximum lateness。

Then you are also optimal with respect to feasibility。Okay， if you minimize the maximum lateness。

 if you have a schedule that minimizes this。Then。That schedule is feasible as long as the maximum lateness is negative。

ok。And so this says， well， if this schedule minimizes it。

 it's going to give you the most negative number。 right， So if there's any feasible schedule。

 any feasible schedule would be would give you a negative number。So this optimality criterion says。

 well， if there's any schedule that gives you a negative number。

 this one will give you a negative number。so it's also optimal with respect to feasibility。

 but it's a stronger result。Because it says something about infeasible schedules as well。All right。

 so， so those are kind of the two key results that we went over last time。 Now。

 what I'd like to do today is。Broaden these results a bit by adding more realism to this scenario。

Okay， and there's two problems that we're going to consider， one is precedes。

 you can't execute the tests in arbitrary order， you've got to execute this one before that one。Okay。

 and then the second one is mutual exclusion locks。

And the effect that those could have on scheduling。

And the bottom line of what I'm going to tell you is that。Nothing works perfectly。

There's lots of weird stuff that happens with。Real time scheduling。

I'll show you some of the weird stuff that happens。啊，是的。Precentnce constraints， okay。

 so suppose that you have a set of six tasks。And。It's just a fixed set。

 you have to execute them once。Okay， so we're not talking about periodic scheduling at all。

 So it looks like earliest deadline first might be the right。Scenario。Because。

We're going to assign them deadlines， but there are precedents relations。

 We can't execute them in arbitrary order。 We've got to execute one。

Task one before we can execute two or three。And we've got to execute two before we can execute four or five。

 so that precedence relation is described using a directed acyclic graph。Okay。Now。

 with apologies for。Doing what everyone in the scheduling literature does。

You fabricate a problem statement that shows that weird stuff happens。

There's nothing realistic about this problem statement。Okay。But。You can't。In a sense。

 realistic problems are too complicated to explain on one slide。And actually， it's even worse。

We don't know what the deadlines are for tasks。And we don't know what the worst case execution time is for tasks in reality。

 So we would be pulling those out of a hat anyway。So。Even if I give you a realistic problem scenario。

 it's still going to be artificial once I reduce it to a scheduling problem。So you might say， well。

 what is the value in all of this then？Well， it gives you guidelines。

That's really the value is guidelines。It also， you know。

 one of the things that I'm going to emphasize today is you know。

Building a little skepticism into the results， because one of the things you'll see through a series of examples。

Is that the results are actually very sensitive to things over which you have no control。

 such as execution time。And the answer can change drastically。

Even with small changes in execution time。And here。

 we've greatly oversimplified the problem by saying， well。

 we assume we've got a bound on the execution time。All right。But anyway， here's the problem scenario。

 so the capital Cs are worst case execution times and the D's are deadlines。Okay， so what this says。

 for example， is that taskask2 has an execution time of one and a deadline of five。

And task four has an execution time of one， and a deadline of three。Now you should， if you're awake。

 you already see something pretty strange about this problem。You see something a little bit weird？

Yes。Yeah， I mean， this is stupid。 Task four has a deadline of three。

 but you can't execute it until you've executed task two， which has a deadline of five。

Where did you get those deadlines？Well， I pulled them out of a hat。啊。

Maybe they're written into the contract。Okay。You're doing a DOD contract and these tasks are missile targeting things。

And， you know， task one is being written by one subcontractor and task two by a third second subcontractor and task four by a third subcontractor。

And in the process of the contract negotiations， these deadlines were written into the contract。

Decided by lawyers。Not engineers or whatever， you know， all， it's artificial。But nevertheless。

 it creates a weird situation。And it shouldn't be all that surprising that if you just blindly apply early deadline first。

 it's not going to work out so well。In this case， because your deadlines are stupid。Okay。嗯。

Here's what you get with the earliest deadline first schedule if you have a single processor。

The only task initially enabled is task1， so deadlines don't matter。

 That's the only thing you can execute。But once task one completes。

 you have a choice between two and three， and three has an earlier deadline than two。

 so you're going to execute three。ok。And。After you've completed three。

 then two and6 are both enabled。And two has an earlier deadline， so you execute two。Okay。

Once you've executed two， you can execute four， but you've already missed the deadline for four。

So this schedule is， in fact not feasible。Right。Is there a feasible schedule？Yeah。

You should have executed two before three。Right？Even though it has a later deadline。Okay。

 so do we have a counter example to Horn's theorem？

On's Theorem says that the earliest deadline first schedule is optimal with respect to minimizing maximum lateness。

And we have a corollary that says it's optimal with respect to feasibility。And here。

 we've applied earliest deadline first， and it failed to find a feasible schedule。

And yet there is a feasible schedule。Do we have a counter example to harden's theorem？Yes。

There is a feasible schedule with these deadlines。There it is。That meets all the deadlines。

 and it meets all the precedentnce constraints。Yes。Right。I mean。

 Horn's Theorem says an independent tasks that can be run in any order。Okay。

 so we don't have a counterexample to Horne's theorem。

This is why it's so important to understand what a theorem says and what it doesn't say。

 because these aren't independent tasks。嗯。Okay， so this。呃。

The schedule that is constructed here actually follows a different algorithm that is。

Called rather strangely， latest deadline verse。And this was first described by Gene Lawer。

 who was on our computer science faculty here。Very nice guy， by the way。

 when I first joined the faculty here， I'd spent a lot of time talking to him and really interesting guy。

But。Anyway， so latest deadline first， well that's a little bit of a weird term。

What he's actually doing is reversing the scheduling problem and he's saying， all right。

I'm going to decide first what to do last。Okay。So the first decision I make is。

Which task is going to get executed last？Well， if I just execute the one that has the latest deadline last。

Okay。That's going to be。呃。Among these three that all could be last。

These could be last because of the precedence constraints。There's exactly one of them。

 taskask 6 that has the latest deadline。So we choose to execute task six less。Then。

Task three could be next to last or five or four could be next to last among those。

 I picked the one with the latest deadline， which will be task5。

Okay and I just keep working backwards。 By the way。

 this is a really good project management technique。

You've got a deadline for your project presentation， figure out your precedences。

And figure out which things you can do last。And then work backwards and emphasize the things that you can't push out that far。

Okay。Because of the president's relations。Okay， so in this case three has the next deadline at this point now the only possible next choice。

Is four because of the president's relations， then it's only two， then it's only one。ok。

So Laer just reversed the timeline and said， instead of being making my decisions in chronological order。

 make them in reverse chronological order。Of course。

 this requires you to know ahead of time all the tasks that are going to be executed， right。

 because if you're going to do them in reverse chronological order。

You make your decisions in reverse chronological order。 You've got to know what's coming。

So it turns out that inspired by this， it's not that hard to modify the earliest deadline first strategy。

 yes。嗯。Right。Yes， but。No， no， because you still have to respect the precedeency。

So when you're working backwards。Four has to come before。Have to come later than two。

 right so you have to just make a decision about four before you make a decision about two。Yeah。O。

All right， so inspired by Loler's twist on Hor's problem。嗯。Several people。

 more or less simultaneously came up with the observation that。Well， D。

 you can just modify earliest deadline first to achieve essentially the same result， okay？

And the modification is a little bit curious here，Bear with me and I'll try to explain it okay。

So the first thing is。You know，In a way， precedences and release times。Are related。Okay。

 so the notion of a release time is when the time at which a task becomes enabled to execute。And。

It can't become enabled to execute in this case。Until all of the precedences are satisfied。

So in fact， it's really in this problem formulation。Release times are the only。I mean。

 precedes are the only thing affecting release times。

 right as soon as all the preceding tasks have completed。The subsequent tasks are enabled。

 so they've arrived。All right。So the first thing is to say， well， let's stick with EdDF。

 EdDF does allow arbitrary arrival time。For task。So let's just figure out what those arrival times should be。

 so that's the first change。So we assign a release time to these tasks。 Now， so task1。

Has a release time of zero because there's nothing that comes before it。Task 2， we will say。

 all right， Well， task 1 has a worst case execution time of one。

 So let's give task2 a release time of one。Now。You pay a price for this。All。

 release time means I'm not going to start executing task two before time1。

What price have I just paid by choosing to do that。Yes。Right， if one happens to finish early。

I'm stuck。 I still can't do anything。Okay， until。Its worst case execution time has elapsed。ok。Now。

 worst case execution time， what's that？Well。A fictionction。I mean。

 I told you that before and we'll look a little bit at how you determine where case execution times of programs。

You know， if it's really a worst case execution time。

You're probably going to have to assume every memory access is a cache miss。

Okay you're going to have to make lots of very pessimistic assumptions about execution times and as a consequence。

 by setting these release times to be equal to the worst case execution time at task one。

 you're dooming your processor to a bunch of idle time。ok。So that might not be a great choice， but。

 you know， it's a price you pay。 right， But nevertheless。

 you can solve this scheduling problem by doing this。 In part。

 we're also going to have to modify the deadline。Okay， because as we observed before。

Setting a deadline of 5 for this is stupid。 So how do you think you should modify the deadline of 2。

We modified the release time by looking at precedences and execution time。Right。

 we could do the same thing with deadline。Look at the execution time of four and its deadline。

And say， well， it has a deadline of three in a worst case execution time of one。

So that really means two has to finish by time2。Not time five。If four is going to meet it federal。

Okay。So we can do that。 In fact， we just set a revised deadline for task2。

 which is the minimum of its own original deadline， which was pulled out of a hat by a lawyer。

 probably。Okay。And the deadlines of all of its downstream components minus their their worst case execution。

Now， again， you pay a price right， because it's minus the worst case execution time。

 So we've set a deadline for task 2 that may actually be earlier than it really needs to be。

Because we're using a worst case execution time instead of an actual idea。O。Nevertheless。

 when you reformulate this problem this way， then EDF actually works。

And it is optimal with respect to minimizing the maximum length。

Having modified those release times and modified those deadlines。We get an optimality result。Okay。

ThisThis is a very classic result about EDF， and EDF is probably the most widely used real time scheduling strategy today。

 even in scenarios where the deadline is pulled out of a hat。

Because actually most real scenarios of the deadline is pulled out of a half， right。I mean。

 I've been working with。People at United Technologies who worked on the electric power system for the Boeing Dreamliner。

 Remember， that's the one that。Where the plane was grounded after flying for a couple of weeks because the batteries kept catching fire。

嗯。And。You know， they have requirements like。If you have a critical load。

 meaning a piece of electronics that。Is you have to keep it powered to keep the plane in the air。

That's what we call a critical load。Okay。That you should not leave it without power for more than 50 milliseconds。

When I first heard that， I was scratching my head， saying，huh？It's a critical load。

 and you're telling me I should not leave it without power for more than 50 milliseconds。

 why isn't that zero？Why do you think actually？Why did they allow me to leave a critical load without power for 50 milliseimes？

Yes。Yeah， hopefully in the power supply for that device。

 maybe there's some capacitive storage so it actually won't shut down within 50 milliseconds。

So maybe that argument is it's maybe okay。But wouldn't it be even better to say zero that a critical load should not be left without power period？

Yes。You want， you want to log the error。 No， that's not the reason。

 But that's actually a good observation。 You do want to be able to。 There is accountability。

 The lawyers are going to want to know who to sue。If the plane crashes and if the black box has a log of。

 you know， the critical load got deep powered。For some period of time。

 then that could be useful for accountability。Another。Yeah， I mean。

 part the part of the issue is that， you know， suppose where does the power come from on a plane。

 Well， it turns out it comes from multiple sources， right， So a typical modern plane， the Dreamliner。

 in fact， has two engines。ok。There's a generator on both of these engines that generates electric power。

But you can't hook up these generators to the same power buses。For one thing。

 they're operating at different frequencies because the frequency generated by a generator is determined by the mechanical rotation speed。

 okay and you don't want the mechanical rotation speed of the engine to be determined by what the frequency of the power that you're trying to generate is。

The engine needs to be able to rotate at speeds for different reasons， like powering the plane。Okay。

 so so the power buses actually operate at different frequencies。

 So if you connect two of these generators together。

One becomes a load to the other instead of both of them becoming generators cooperating on powering the loads。

So you can't have the two generators driving the same buses。

So what do you do if one of the generators fails？And on its bus was a critical load。Well。

 you got to switch over to the other generator。But you can't have these things constantly connected to the same power bus because they will。

Basically fight each other， the new generator。So you need to allow for some switching time。

So where did they come up with the 50 millisecond number？Contract negotiations。Really。

Because now the subcontractor who provides the box。

Does the flight control system that determines the positions of the flaps。In the rudder and so on。

He is told in their contract that they have to be able to operate for 50 milliseconds without power。

So they designed that into the system。Okay， so that's where deadlines come from in practice， right。

 they are kind of pulled out of a hat， but in big systems， you know。

 they require some negotiation and some cooperation among people。Okay。All right。Yes。Actually。

 modifying the deadlines and respecting the precedences is sufficient。Right。But if you。

 if you just purely want to use EDF。Right。As stated。

 the problem in EDF is you have n independent tasks with arbitrary release times。And。

Arbitrary deadlines。And here's the scheduling algorithm。

So if you want to take this problem and recast it in that form。

The only way to respect the precedes is to modify the release time。Right。Yes。应当。And maximum lateness。

 both。If that's right， this I mean， it's important to know what it says and what it doesn't say。

 so what results will we get if one of the tasks exceeds its worst case execution time？

The theorem says nothing。有。So keep in mind that this theorem was developed in the late '70s。

And there's been hundreds of PhD theses written about scheduling problems since then。

So if the question is， is there a variant of it that does such， the answer is almost certainly yes。

But I couldn't point you to it。You know，Right off the top of my head， but there's a lot of variances。

有有。If you set the release sentence to zero and then do earliest that， yeah， actually， it might work。

I think that certainly worked for our example。But。Because the deadline by definition is yeah。

 actually。 so you're right。 so probably we don't really need the release time modification。

Good point。 I'll have to take that up with Gio Bthzzzo。

It was the guy who wrote the book after which I fashioned this story。嗯。Okay。All right。

 so what I'm going to talk about next is what could go wrong？Mmhm。Well， a lot， okay？嗯。So。

In particular， today， what I'm going to look at is mutual exclusion。嗯。And let's just go。Directly。

 okay， so remind， what is mutual exclusion？Okay。So。When we talked about threads。

 I showed you how you could acquire mutual exclusion locks。

On chunks of code called criticaltical section。And it's also。

 it's really important to understand what this does and what it doesn't do。ok。Because。

It it doesn't do as much as you would like it to do sometimes， right。

All it does is it says that there's no other code that can be executing。

 that can acquire this lock while I'm in this block of code。If I have a thread that holds a lock。

 it holds it exclusively， and any other thread that attempts to acquire that same lock will block。ok。

All right， so that's just a reminder。So priority inversion。So here's a picture that。

Summarizes a very practical problem， and by the way， let me just motivate this problem first。嗯。

This problem was on the front page of the New York Times。

And not a lot of scheduling problems make it to the front page of the New York Times。Okay。

But this one was。Because this problem exactly showed up in the Mars Rover Pathfinder while it was on the surface of Mars。

And the symptom was that it was it was actually working fine for a few days。But after a few days。

 it started sporadically missing deadlines and it was logging what was going on。

And it had a routine that was monitoring those logs that said， well， I missing deadlines。

 something is wrong。 What do you do when something is wrong， You reboot。Okay。

 so the rover was rebooting， and it started rebooting rather frequently。Okay。

And so the engineers at NASA started looking at the code and saying。

 why the heck is this thing rebooting？And they could get the logs also， albeit with some latency。

And they studied the problem and found out that it was a priority inversion problem。 so specifically。

 there was a low priority meteorological task。 So that's just measuring the weather。

And it was holding a lock that was blocking a high priority task。嗯。

But then a medium priority task was sneaking in。And being able to execute for an arbitrary amount of time。

 effectively blocking the high priorities。So how does that come about？Okay。

 so here we have three tasks， task one has the highest priority， task two has the middle priority。

 task three has the lowest priority。Okay， so initially at time zero。Tasks1 and two are not enabled。

 so task three is executing。And it acquires a mutual exclusion law。

And it's holding that mutual exclusion lot when task1 becomes an name。

Task1 becomes enabled and preempt task three because it has higher priority。

Task one starts executing， but then it tries to acquire the same mutual exclusion block。

That task three。Okay。Now you could say， well， it has higher priority， why doesn't it just evict？

Three and grabbed a lock。Yeah， I mean， that would completely undermine the whole point of having a mutual exclusion。

Because that means that the critical section in task 3 would not execute atomically with respect to other critical sections that are holding the same lock。

So if you're going to do that， don't bother with locks and use a Toyota style of design。Okay。

 by the way， we have a。Speaker coming。In a few weeks on a Friday， on a Friday afternoon。

 watch for the announcement who worked on the NASau Commission that studied the Toyota software。

And he's going to tell us stories in a special seminar on a Friday afternoon about the Toyota software。

 I really recommend it。So watch out for it in the department seminar announcements。Anyway。嗯。Okay。

 so you can't just grab the lock away from this task3， so instead you yield the task3。

 which is supposed to now execute until it can release the lock safely。Okay。But at time four。

 task two becomes enabled， and since it has higher priority than task 3， it preempts task three。

And now task two can execute for an arbitrary amount of time。

And even though it has lower priority than task one。

 it is effectively blocking task one for an arbitrary amount of time。Okay。

That's called priority inversion， because in effect。

The priorities are not getting respected during the time that task2 is executed。O。

So the NASA engineers were able to fix this problem and stop those periodic reboots。

And the way they fixed it is by using something that。

They should have known about when they wrote the code in the first place。

 but they hadn't taken this course。And so they didn't know about it。嗯。

But if you look about at the dates， this was published in 1990 by Louis Shah。

 Raj Raj Kumar and Lahaski。This was Raj Raj Kumar， it's a big part of his PhD thesis。

 he's now in the faculty at CMU。But okay。What is priority inherent？Well， it's a strategy that says。

That。嗯。When a low priority task。Blocks a high priority task。Because it's holding a lock。

It acquires the priority of the high priority tax temporary。

It's actually sort of an obvious thing to do。 right。

 The high priority task is trying to get the lock。The lo periodortic task has to run to the end of its critical section before it can release the lock。

Clearly， you want that。Critical section to be executed at the same priority as the high priority task。

So in retrospect， it's kind of obvious， but somehow this had eluded people who were working on scheduling between the late 1970s and 1990。

 big gap in time。Okay， so that solves this problem because what happens is that as soon as task1 block is trying to acquire the lock that is held by task3。

 then task3， its priority changes。And it continues executing at the priority of task one。

So when task 2 becomes enabled。It does not preempt task three。

It can't do that because have it has lower priority now than task3。

As soon as task three releases the lock。It， of course， now reverts to its original priorities。

 So task 2 is now enabled， but now so is task one。Because it becomes unblocked by the release of that task。

So task one will now execute。And having acquired the lock。Will。

Carry through holding the lock until it is done with its critical section。可以。Was that clear？Yes。

That's right。So remember the mechanism by which this works， right。

 so how does task 3 release a lock well he calls this P thread procedure。To release a lot， right？

One of the things I said is that within that P thread procedure。In theory。

 as far as the task is concerned， that procedure returns immediately。

But it actually may not return immediately because the tasks the scheduler is going to get invoked as part of executing that procedure。

So it's going to release the lock and guess what， its release procedure is not going to return immediately because there are now two enabled tasks that have higher priority than it has。

 so the task scheduler will instead of returning from that P threads procedure。

It'll just save that stack。For that thread。And resume the stack of task one。

 okay so that's the mechanics of how that works。Okay。All right。

 so this is so priority inheritance is about basically making sure that you can't get this priority inversion。

But there's another problem， which is the possibility of deadlock。And in particular。

 the acquisition of mutual exclusion locks interacts with priorities in bizarre ways。Okay。

And it turns out in this same paper， Shah and Raj Kumar and Lehoski solved this problem as well。ok。

And basically showed that you could， in fact， prevent this interaction between priorities and debt。

 So here's the kind of scenario that they protect against。So here we just have two tasks。

 Task 1 has higher priority than task 2。Okay。And。Task two is initially enabled， task one is not。

Task2 acquires a lock at time one。And then gets preempted by task one at time two。

Task one starts executing， and then at time three it acquires a second block。

Dadlocks occur when you have multiple locks。If you just have a single lock。There's not a bedlock。

Okay， but as soon as you've got multiple locks， you've got to worry about whether you could get。

 you know， cross cross requests。Okay， so task one acquires block B。And then it attempts to。

 after acquiring the lock B， it attempts to acquire lock A。ok。And。That locks it。

Which will enable the execution of the lower priority task， presumably。

To finish its critical section so it can release the lot。But it doesn't cooperate。

 it instead tries to acquire lock B。And a deadlock occurs。

And now both tasks are frozen and there's nothing the task scheduler can do。

 Neither task is enabled or stuck。Hit the reset button， start over。

 and this will eventually happen again。就。But。Is there a scheduling strategy that would have prevented this。

Deadlocks from occur。Yeah。Oh decades。But that would require changing the code。

Is there something we can do with the task scheduling alone？

With the same code that would have prevented this。situation。Yes。Right。

 so that's exactly the right insight。 So it's not accidental that it was the same paper that solved this problem as well。

 because basically， the idea is pretty much the same。 It's called the priority inheritance protocol。

But basically， the mistake that was made here。Is that when task 1 called the P threads method to acquire lock B。

 it should not have been allowed to continue。 It should have blocked。Right。

So what's the policy that we should use？Well， the policy is written here and it's a little bit of a mind bend to read。

 okay， no， it isn't written。It's written here。ok。So first。

 you associate a priority ceiling with every lock。Okay。

And a priority ceiling is just a number that is going to be interpreted as a priority。

And the priority ceiling is equal to the priority of the highest priority task that can acquire that loss。

How do you know what task can acquire a lot？The task in this case is a thread。Any ideas， yes。Yeah。

 you could do static analysis， but let's be very specific。 So how。

 how do you create a thread in P threads。You define a procedure。And then you call a P threads。

Procedure。And pass it a reference to your procedure。ok。

And the P threads the library will create a thread that will begin executing your procedure。ok。

So you know that that procedure is associated with a thread。

Look at all the code that's reachable from that procedure。Every procedure that it calls。Okay。

And you don't know for sure whether a particular procedure is going to be called because it might be deeply nested within a bunch of if statements。

Okay。But if the procedure makes any reference to another procedure。

 you have to assume it might be called。ok。And so you just do this reachability analysis。

 you brute force， you look at this procedure and all of the code that can be maybe be reached from that procedure。

And if any of that code includes a call to the P threads Library that acquires a lock。

Then you have to assume that that thread can acquire that lot。

There's all kinds of ways to mess this up， it's also， I mean， the way that you pass locks。

To to the P thread procedures is an address of a variable。It could be a computed address。 So。

 in fact， static analysis could fail here。 You might actually not be able to determine which procedures are called by this thread。

嗯。Sorry， better make sure you write your code in a way that you can determine this or you're not going to be able to apply this policy。

Right。有。In Python。Oh， and compile that。Well， yeah， I mean， in C， in fact。

 this question is undecidable， because C allows for arbitrary aliasing and address manipulation。Okay。

 so。You can't in principle with C programs。You know。

 whether you can even use the priority ceiling protocol is an undecidable question。

There's no compiler。That can definitively apply this policy to all C programs。Okay。

But there are compilers that can apply to some sequence。

And you better make sure you write your program in such a way that the compiler will be able to do this。

We're going to look a little more at the static analysis question later on。

 so we'll come back to this。This issue of how you analyze programs like this。Nevertheless。

 it's worth in the spirit of trying to infuse you with some skepticism。 if any。

 you're working on a project， there' some high up manager。Tells you， this isn't a problem。

 You can just apply the priority ceiling protocol。And you're going to know better。

And know that be careful， okay， maybe it doesn't always work。Okay， but nevertheless。If it。

 if it can work， if you， if you do， in fact， know。What。

Wwhichch pieces of code can acquire which locks and which pieces of code are reachable by each thread procedure。

 then in principle， you can calculate a priority ceiling for each lock。ok。

Then the policy is a task key is allowed to acquire a lock only if the task's priority is strictly higher than the priority ceilings of all the locks currently held by other tasks。

ok。So let's look at how that applies in this case。So。Task one has high priority。ok。

But it attempts to lock B。But taskask two is able to lock B also。

Task two has lower priority than task1。But the priority ceiling of task of lock B。

Is the highest priority tasks that can access it， which is the priority of task1。Okay。

So task one is going to be allowed to acquire this lock。

Only if its priority is higher than strictly higher than its own priority。Which it can't be。

So it'll be prevented from acquiring the lock。呃，B。And instead。

 task two will be allowed to continue will hence be able to acquire lock B。

Refinish its critical section， release both lock， and only at that point will task1 be able to acquire lock B。

 and then lock A。Okay。Yeah。That's a really good question。So you know the question is。

 is there any way to quantify how often you need this or whether these kinds of scenarios are likely to arise？

嗯。I think the short answer to that is no。There isn't anyway。嗯。And。嗯。Yeah， so。

I go back to my statement about multithed programs， they're incomprehensible to humans。

And so if you need to prevent these kinds of scenarios from arising。

You're going to have to be do some very， very conservative design。

And that's in practice what people do， so in safety， critical avionic software。

 they don't use threats。Here。No priority ceiling protocol， no priority inversion， no thread。Okay。

That's the one way to do it。But it really restricts what you can do。Yes， a question。Well。

 they had a more complicated problem than just controlling the flaps and the rudders。

 right that's a sort of classical control system problem， but you know， I mean。

 even in avionics control， the problems have gotten a lot more complicated。

 and so they're really up against the wall， the complexity wall in these kinds of situations。

So one of the things they do， in fact。Next week。Alberto is going to talk about synchronous reactive programming models。

嗯。Airbus。Uses a concurrent programming language called SCD。To design their safety critical software。

And the principles behind this language are completely different from threads。

And the resulting concurrent programs are much more analyizzable。And in fact。

 you can prove very strong safety properties about these programs。Okay，You know。

 your choice of programming style can have a big effect。All right。嗯。So。In general。

 all thread scheduling algorithms are brittle。Brittle means a physical object is brittle if you bend it a little and it breaks。

That's what it means to be brittle and brittle problems in software are ones where small changes have big consequences。

ok。So I'm going to illustrate this by walking you through a very famous theorem。

 which is called which is named after Richard Graham。

 and it's one of those really unusual situations where this result is。I named after his first name。

So。It's a result that is widely known as Richard's anomalies。

And it's really because when he first presented it。

 it really popped the balloon of a whole bunch of people in the scheduling world who thought they had all these beautiful optimality theories。

And he said， hmm。You guys should be a little more careful about what you assert。And。

He came up with a really beautiful illustration of a really nasty problem。Okay， so he。

Put this in a multithreaded a multiprocesor context。

 so this applies more broadly than to single processor scheduling problems。

 but the single processor versions are also interesting。

 but the multiprocesor versions are even more interesting。You have。

Three cores and a bunch of tasks with precedences。And you have worst case execution times for those。

Okay。And you schedule them according to some priority based schedule。ok。So in particular。

In in Richard Graham's example， this example comes from his original story。

Task one has the highest priority， Task 2 has the x highest priority， Task 3 has an x。

 so these are all fixed priority tasks， so that the priorities are just equal to the task numbers。

Okay， that nine is the lowest priority。And execution times are shown。

 task one has an execution time of three， and execution time is two for task 2， et cea。

And there's precedence relations。Okay。So with the numbers as given here and three processor。At first。

 tasks one through four are all enabled。So we just execute the three highest priority ones。One， two。

 and three。We've got three processors available， go ahead and schedule。When test2 completes。

We now have a processor available。But the only newly enabled task is4。 I mean。

 it's not newly enabled。 It was originally enabled， but the only enabled task is4。 So we schedule 4。

When task one completes9 becomes enabled， so we can execute that。 and when taskask4 completes。

 all four of these become enabled。 and so those get scheduled on the remaining processors。

And the whole set of tasks completes by time 12 under this scenario。

So then Richard Graham pointed out。That。If you increase the number of processors to four。

Schedule gets worse。The completion timing is later。

If you decrease the execution times of all the tasks。The the schedule gets worse。They complete later。

Okay。And if you remove precedences， which gives the scheduler more freedom。The schedule gets worse。

You end up completing tasks later。喂。So these are known as non monoonicity results。

 so finishing early。Can cause a deadline to be nice。

And that is generally true in real time scheduling。 If you finish early。

 you could cause a deadline to be missed。If you finish way early。

 you're more likely to cause a deadline to be missed than if you finish close to the edge。

 it's weird， but it's true。Okay。So this creates a brittleness in these systems that makes them really difficult to verify for safety。

So here's what happens if we increase the number of processors to four。Nothing else has changed。

 We just added an additional processor。 Well， the additional processor says， well。

 we can we had four tasks initially enabled， so great， we can execute them all at once。ok。

But then when these two three tasks complete， when four completes， in fact。

 all four of these become enabled。Okay， so we're going to execute them before task 9。

 and things actually got worse by a lot。Okay。So。This is， by the way， this scheduling strategy。

 in general， a scheduling strategy that。Doesn't look into the future。

So it's ignoring the fact that task9， which is going to become enabled later。

Actually has a really long execution time。This is known as a greedy scheduling algorithm。

Ingredy scheduling algorithms are usually suboptimal。嗯。

But often youre stuck you're stuck with greedy scheduling algorithms because you may not even know about taskask 9 until task 1 has completed。

That's often a problem。O。This one is even weirder。So this is the original schedule that we have now suppose that everybody finishes early。

All of the tasks complete。One time unit earlier than the original problem。What happened？Well。

 we get a worse schedule。Okay， here's the schedule we get。When it starts out in a similar fashion。

 right，1，2，3， and 4 kind of have the same pattern。But they're all finishing earlier。O。

 but once four completes， all four of these become enabled blocking9 from executing。

 which then results in an extension of the completion。

Every task finished early and the overall set of tasks finished later。Why。

So weakening precedence constraints。So Graham noticed that if you were a move。

The precedence between four and eight and four and seven。That you will get a worse schedule。In， yes。

This one。Yes， because they have higher priority。The priorities are。According to the task numbers。

So the point Richard of Graham's observation here is not that， I mean， you could fix this by saying。

 well， you assign the wrong priorities。Right。You could assign other priorities and you'd get a different result。

His point was that any priority assignment is subject to these anomalies。

So it doesn't matter what policy you're using to assign the priorities。

 You still have the potential of getting these kinds of anomalous behaviors。

Because if something finishes early， it could reverse the order in which two things happen。

 no matter what priority assignments you're giving。Okay。嗯。I'm sorry。Right？Yeah。

Maybe all of these anomalies would evaporate if you did that。Okay。

 but I'm pretty sure that you could then come up with another problem that would result in similar anomalies。

So the issue is not that you're going to encounter these anomalies in a practical scenario。I mean。

 what Graham was simply pointing out was that you can。That there's priority assignments。

You think will work and this is borne up， by the way， I you know。

 there was a wonderful keynote talk at one conference that I went to by。

Vice President at Lockheed Martin， who designs software for aircraft also。Okay。

 and they were working on the joint strike fighter， which if you know anything about， you know。

 DOD contracting， that was one of the most。Spectacular cost overruns in all of history。Okay。Huge。

Cost overrun billions and billions of dollars， right？And anyway。

 he was telling stories about things like， you know。

 they they were making small changes in the software fairly late in the game that。By in depth。

 detailed analysis of the code shouldn't have affected the scheduling。And it did。

Small changes in one piece of code would cause deadlines to be missed in seemingly completely unrelated code。

Okay， inexplicably。And。You knowThey were running into problems like that all the time。

 and so it happens in practice。You can't I mean， the real cautionary tale is that these things are so complex。

That。It's hard to know what all the possible scenarios are that could manifest in the field。Okay。

And that's really what Richard Graham was pointing out is that， you。

 the problem seems to be a little bit fundamental to the whole approach of doing priority based scheduling。

Okay， so weakening precedence constraints can also make things worse。In this case。

Because of the weakening precede's constraints，8 and 7 get executed early enough to block 9。

 and things get really bad。 This is the worst of all。Schedules we've encountered so far。Okay。嗯。

New Texas。Okay。So。If you have a program that uses mutual exclusion locks。

And it works fine on the test bench。And in the field， for some reason。

 some of the tasks finish early。Okay。Maybe things are better than you expected them to be on the test bench。

That doesn't necessarily mean that you will meet your deadlines。ok。

And this example is also due to Richard Graham， so you've got a two processor schedule。嗯。And tasks。

2 and 4 share a resource so they， they're both complete critical sections。

 They can't execute simultaneously。Okay。嗯。On the test bench。

 you get this schedule where processor one executes task one and then it can't start task two right away because task four is executing and holds a lot。

Okay， but as soon as four releases the Lockcut begins executing task two。

But if task 1 finishes early。ok。Task  two will acquire the lock。Blocking task4。

 which will extend the overall completion time。So this is yeah。2。

Why couldn't five run on processor one？I think in Richard's scenario in Graham's scenario。

 I keep calling him Richard， it's impolite， and I really should be calling him Graham。

 but he's known as Richard's anomalies。His scenario was fixed priorities and fixed processor assignments。

And you know， the point wasn't that， well， all right， maybe that scenario is unrealistic。 Yeah。

 of course， all these scenarios are unrealistic。His point was that these techniques fundamentally are brittle。

Right。And that you you know if。If very simple artificial scenarios like this give you these weird conundrums。

 imagine what real world scenarios are going to give you。

That that's the way you have to interpret these results， right？Right。Yeah。

 there could be a precedence relation between four and five， for example。That's another。

Good argument for doing that。In any case， as I recall。

 I don't remember him stating why these were mapped this way， but he doesn't really have to。

 right the is。Okay， yeah， he just assumes they're statically allocated to processors， okay？嗯。Yeah。

All right， but this is， by the way， this is a very common situation。

 because the acquisition of mutual exclusion lock， the whole reason you have a critical section is to prevent two pieces of code from running at the same time。

And whichever piece of code gets to that lock first is going to lock it for some period of time。

If you ever have a situation where two threads are kind of close and when they might。

Get to the point where they're going to request the lock。

Then the order in which they get the law could change。That can have big effects。

That's what brittleness is。Okay。Small changes in the timing of a program can have big changes in the way it behaves in the field。

So okay， so I think I've said this， be skeptical， okay。

 but you do want to know about these results because they're useful as engineering guidelines。

If you're designing safety critical systems， you have a lot more work to do than just relying on these scheduling results。

 it's not enough。So that's it for today， any last questions？We have a couple minutes。All right。

 good luck on the midterm tomorrow， don't forget my office hours tomorrow will be 10 to 11 a。

 instead of 12， 11， 30 to 12 30。Today's lab is three to five。Wednesday's lab is9 to 12。

 and please with your team， go see a GSI to get feedback on your project charter。



![](img/585abce8ecde6900d13696a86c61b40a_3.png)