# 【计算机体系结构】普林斯顿—中英字幕 p46 45_06_dynamic-events-and-clustered-vliws -BV1ii421D7WR_p46-

![](img/aad6d41bbc6d3f851317f201683f1b93_0.png)

Okay， so let's， let's。Talk about some of the other things that were on our list of。

Litters to instruction level perism and ask ourselves。

 are these things which we can solve very easily？Well。Things start to get harder， pretty。

 pretty fast here。Like I said， dynamic events。They're basically things the compiler has no way of。

Reacting to。Now， the instruction set might not be might be able to react to it。

 You can add things into the instruction set。 You can maybe take a branch dependent on a dynamic event。

 But let's look at some of dynamic events。First dynamic event here， Cash M。Well。

 it's really hard for compiler。All things being equal。

 knowing whether a load is going to take a cash miss or not。

It might have some guesses and that could influence the code。 But， you know。

 actually doing something about it。 If you think about what an out ofvo superscale does。

 if you take a cache miss， it'll reschedule the code。Around the cache miss。

 it'll take the non dependent instructions。That the instructions that are not dependent on the load and pull those up and try to execute those。

But if the load hits in the cache， you want a totally different schedule。

 You want to actually try to start executing the instructions their dependent tenant load as soon as possible。

So A Vor superscale has dynamic means to be able to do this。 has dynamic instruction execution。

 But our VIW processor， which is statically scheduled， can't really do this。

So what's some techniques to go about after this？One thing is something called informing loads。

As far as I know， this actually has not been built in any hardware， but it's been proposed。

 at least in the computer architecture。Academic circles or in in the computer architecture literature。

 and informing loads has actually come up。The， the original paper about this is by one of our faculty members or one of our faculty members here at Princeton。

 Margaret Martin Nosi wrote a， she's one of the authors of this paper。

 But the the basic idea is that if you have a load。That misses in the cache。😡。

You can not execute subsequent instructions。Else， you can there's actually no there。

 the load misses in the cache， you just don't execute some subsequent instructions。

 You can basically nullify those instructions。And this allows you to change the code sequence depending on whether the load hits in the cache or whether it misses in the cache。

 And this was done with Todd Maorory Margaret Martin Noi Prossor Margaret Martin Noi and professor Todd Maorory。

 I think both when they were graduate students。 And Mark Kitz from Stanford was on this paper。

 I think a couple。 I remember who's the last author， the professor on this。On this work。

Another option。Is something that the Alberus。Or Els processor people did。

 So you've probably never heard of this processor。 It was something that was built。In the， well。

 I don't actually don't know who's ever。Finished， I think they had a prototype of it。

 sort of in the Soviet Russia day right when the Soviet Union was kind of breaking， breaking down。

 This was the design house in Soviet Russia， which was made all of the sort of military processors。

 They later went off and that same design team， was gonna go build some commercial processors after the fall of the Soviet Union。

So they went and， you know， they went to go build this processor。 and it's V I W processor。

 It's some very long instruction word processor。 And they had an instruction in there which tried to solve this dynamic。

Event。Problem around cash misses。So what it said is if an instruction misses in the cache。Go execute。

A different piece of code with a different schedule than if the instruction。

 if if a load hit in the cache。So you could effectively have two different code sequences。

 The compiler could actually generate two different code sequences。

 and you can get back to a lot of the performance and get back to almost exactly what a out ofor superscaler could do。

Now。This processor never really made it commercially。

 And later the company went under and was bought。 I actually don't know if the assets were bought by Intel。

 but at least all the the people who worked at this company now work in Intel effectively。

 So they still live in Russia。 So that's a funny story there that yeah， I didn't work out from a。

Commercial perspective， but they had some cool ideas in there that you could actually try to schedule around branch predict schedule around cash misses。

Okay， so some other things。Branch mispredicts。Well， we already talked about one technique here。

 We can talk about， you can add predication。But that doesn't help if you have big pieces of code。

 big code sequences and big code hammocks， you can't necessarily。Predicate your entire program。

 So what do you do instead。Well。1， one solution that people have come up with for this。 And this。

 this is a hard one， hard one to deal with here is you can add branched lace slots。

So you have a VLAW processor， let's say it's 3 wide。

And you add branch delay slots in your instruction set。

And then use predication in the branched lace slots。

And what this allow you to do is it effectively lets you mask some of the branch mispro penalty and change the code schedule。

A little bit dependent on the prediction。Or change it actually completely based on what the branches。

 And the way this works is in the the。In delay slots。

 you use the same predicate that the branch is branching on。So the branch is branching on。

 let's say if a equals B。We use that same thing in the predication。 And effectively。

 you can reschedule the code differently depending on whether the branch is taken or not taken。

 And because you're putting in the。Delay slot， you can sort of get around some the problems here of whether it's taking the one direction or taking the other direction no matter which way the predict which way the mispredict happens or whether the branches can be predicted correctly or not。

 And and what we're doing is basically putting code in the delay slots that we always execute but it can be predicated and you can actually pull code up from the two destinations of the two branches。

 So it's sort of a way to get around branch mispredict penalties here。

This is actually done in a research processor that was built at MIT。

 and I think this is probably also done in some of the other H processor， but the MIT processor。

 at least was called the M machine out of Bill Daley's group。 He's now at Stanford。

 but I think the M machine was sort of built right when he was moving from MIT to Stanford。

 but they had I think three delay slots and they were three wide。

 and they could predicate the instructions in the delay slots。So last thing is exceptions。

So you take an exception and you want to schedule different code。

 And these are like impossible to predict。 the compiler has no way to try to predict this。

But this is hard on a supersar。 Also， You know， when you have a traditional supersar and exception happens。

 they usually end flush in the pipe anyway。 So and， and it doesn't happen that often。

 And probably doesn't hurt your performance that much no one's gonna to least lose too much sleep over this one。

So I briefly wanted to say something about how to build really wide VIWs。

As we start to go to wider and wider VIWs， lots of instructions execute at the same time。

You just start thinking about what does the register file in the bypass network look like？😡。

So on in this， in this drawing here， we actually have a。Fig of the C 64000 series processors。

 So these are TI DSPs or the flagship DSP processors。And this is a。

Sort of block level diagram of what they， what they have。

 And what what they actually have is they have。 They've divided the machine。

Into local register files。When they bypass within inside of what's called a cluster。

 So it's a clustered V I W， It's similar to how we have clustered supercals。

Which also divide the register file， but this is an architectural big8 architectural or ISA level architecture splitting or dividing going on here。

So in something like the C 641000。They actually have four instructions per cluster。

 so they're eight instructions at the same time。And。You can bypass。Values between。These four AluUs。

Within within them， or you could bypass within these。

 But if you want to sort of take a value from here and move it to there。

 you have a very low bandwidth sort of bypass path here。 And it takes an instruction。

 You effectively have to have a move instruction to move between the two different clusters。

So there's a lower bandwidth between the clusters and a higher latency。Between the clusters。

 but inside of a cluster's very fast。And what's important to know here is these are not two processors。

 These are all executing 1。Instruction at the same time。

 So' a eight wide instruction executing on these eight。Different as。And this is used in the， the。

 a T I。High end DSPs also iss used in HPs and ST micros LX processor。

This is probably a processor you never heard about。

 But this was actually what Josh Fisher went on to go do at H P labs after multiflow。

 So this is after a lot of the original V I W work same， same person。 want to L X processor。

 And this is sort of joint collaboration between S T micro and H P and this shows up in printers today。

 So it's not something you're gonna entirely have。 The L X processor is something you're not going to have in your desktop machine。



![](img/aad6d41bbc6d3f851317f201683f1b93_2.png)

![](img/aad6d41bbc6d3f851317f201683f1b93_3.png)