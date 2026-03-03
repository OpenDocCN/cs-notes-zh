# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p01 -01-Lecture 1_ Course Goals and Introduction to Maximum Flow).zh_en -BV14CAUeUEPj_p1-

So welcome everyone to CS261， I think of this class， or in my mind。

 the title of this class is a second course in algorithms is an actual SQL to 161。

 the official title in the course books of aDifferent optimization and algorithm paradigms。

So before I do any technical content， let me just open with a few words about what the goals of this course。

What you going hope to learn if you choose to take choose。And so there's really two different goals。

And of course， splititzs roughly 50， 50 down the middle with respect to each of these。

So the first one。It's going to be very much in the spirit of CS161。The focus will be on algorithms。

 best algorithms。We fundamental problems。The fundamental and well solve。And indeed。

 if we were at a semester school。So the first part of 261 would really just be what we would do in the weeks 11 through 14 of a semester long version of introduction to algorithms。

And so the theme here is， you， out there in the world。

 there's a collection of fundamental problems that are simultaneously kind of basic and flexible enough to model lots of different applications。

But also， happily。Admit fast algorithms for their exactaries。So you saw several of these in 161。

 so you could think for example， about the shortest path problem。

 so what did you learn in 161 you learn the definition of the problem in various variants maybe negative edge costs or non negative edge costs。

You learn some famous algorithms， Ds algorithm， development toward algorithm。

 definitelyly parts of the greatest hits of algorithms。And hopefully。

 maybe you also got some practice recognizing that certain problems which don't immediately look like the shortest path problem nevertheless can be solved using the shortest path algorithm。

 so for example， maybe planning a sequence of decisions over time might have been something that you solve。

是。So while of this form that both come up all the time and also have fast algorithms。

 those are pretty much the top priorities to cover in a class like that。

 it's kind of the number one thing I want to give you before you meet the course。So why。

 well you a major skill you can get by taking26 when you couldn't get it elsewhere would be you avoid reinventing the wheat。

 so first of all， you recognize out there in the world the problem you care about really is just something that's already well solved。

Once you recognize it as such you have in your toolbox and algorithms。

 you can just code and solve the problem quickly， you don't have tovent a new algorithm from scratch。

 and again， also a major thing that will practice a little more on the homework than in the lectures。

 but still the skill that I hope you get is the ability to recognize。

The many problems out there that show up in the real world are really just thin disguised versions of the basic problems that we focus on。

And again give yourself some examples of that， we say short passed。Okay。

 so you're already know that short has passed， so obviously we'll be covering other problems。

 sort of more sophisticated problems。So in the first five weeks。

 we'll talk about the maximum flow problem， and we'll start on that today。呃，大时么样。ra cuts。

Which is closely related to the Max problem。We'll talk about computing matching。

This will culminate in the study of when approaches it。

Which is one of the sort of most general problems for which we know algorithms that are efficient。

 both in theory and practice。So we'll talk about algorithms for all of these problems and also why you should care about these problems。

 what kinds of standards they model， so the running times won't be quite as blazingly fast as in 161 and 161 almost everything winds up being near linear time。

 so these won't often be near linear time they might be say quadratic time but they're still fast enough that generally if there's a problem that you actually care about and it reduces something on this list。

 you should be pretty happy because there office shelf algorithms would solve them pretty quick。

So that's going to be the gist of the first ethnic class。Now， unfortunately。

Lots of problems that you're likely to bump into。And your future career don't actually fall into this collection。

So the second course goal is to give you some tools。For dealing with problems that while important。

 are not so well solved。And we'll look at two categories primarily。

 there's a bunch dividend one split every year， but21 will focus on two things。So first of all。

 we'll talk about problems which are empty hard。Meaning problems where we don't think there's any polynomial time algorithm for're solving it exactly。

 the P equals NP， unless P equals NP。So you have to do something else so you have to compromise in order to solve empty hard problems。

 so for example， one thing we'll look at is heuristics。

 and this is often how you actually deal with empty hard problems out there in the real world。

 so it'll say okay， if you want what's a principle way to design algorithms will not guaranteed to always be correct。

 or at least mostly correct， hopefully almost all of the time。

And so we'll look at a lot of the design and analysis techniques for heuristics， building。

 for example， on our working and linear year program in the first half。

other category of sort of hard to solve exactly problems。We're so called online algorithm。

So this is pretty anachronistic at this point， so this is not referring to the internet。

 this is not referring to social networks， online algorithms just means your algorithm is forced to make decisions without knowing the future or you could think about it without knowing the entire input。

So it's almost like it forces you into a greedy type algorithm。

 even if you wish you could do something smarter， and so that comes as you can imagine。

 all the time you have to design algorithms and make decisions that are important。

 but you don't really know what's going to happen later。

 so these problems again come up a lot and you probably haven't seen about them anything about them in previous algorithms courses 261 is where you learned the basic。

I guess one other comment just about the course， I sort of think of it being two audiences for 261。

 both audiences， I think。For me you're very important I'm very interested in the first audience。

 some of you this will be the last algorithms class you've ever take so you'll graduate this year or next year without taking any and so for you I really want to pack the course of the essentials right so if I only get 10 links of your time to tell you sort of algorithms you don't know yet。

 I think about 261 I think about what are the algorithms that make your cut that are worth telling you about。

And this last course you're ever going to take on Howard。On the other hand。

 there's a second audience some of you might be contemplating deeper study of algorithms。

So maybe you're thinking about research or at the very least。

 maybe you're thinking about other 200 and 300 double theory courses and so for you I want to give you a little bit of a sense of the cutting edge so when there's opportunities to present themselves we'll talk about recent developments and the topics we're discussing and I want to give you a little bit of a glimpse of like what lies in your future if you take more say 200 and 300 double algorithm those courses here at Stanford so that's the second thing we'll talk a little。

So。Just because I think about sort of where 261 lies in the overall curriculum。

I think of as sort of a gateway to advance data。At least for the second of the two audiences that I met。

And indeed， so after you're demo to 261， you're extremely well equipped to think any of the other 200 or 300 double algorithms courses that we teach at Stanford。

 and now there's a bunch。Atity one， it also sort of interpolates， I think。

 between just the pace and the difficulty of 161 and what you can expect to see in courses。

 either other 260 something courses or 3000 courses。

 so it's definitely going to be a faster pace than 161， but definitely not as fast。

As when I teach 300 level courses， I mean， I sort of have this mental model for the typical student in each of these classes。

So you know， I teach 161， that's required for all major。

So I look out there in the audience and my baseline assumption is that a constant fraction to students would rather not be there and maybe even hate that。

And I try to give them great course， despite the fact that that's kind of the type of true science that sale fine。

261， I assume you want to be here， I think of this as a self selective group。

I think if I'm talking audience people who like algorithms and want to know more about it。

I'm not going to assume that you necessarily necessarily of love math。

 but I think I am going to assume that you don't keep it。そ how为一す。Through adult classes。

 I'm thinking more about people who really wanted to research these students and undergraduate and master students that are thinking of going on program。

Okay so that's sort of another level of sort of depth and sophistication。

So that's where I'm coming from。In261， that's of how I think about。

So pause for questions in a second， and I'm sure one question that's on the major mind。

so what do you have to do？let me first mention a nondeliverable。

 so every week is going to be an exercise set， it's going to be posted usually on Thursday or Friday and it will cover itll be related to the two lectures that just happened earlier now。

 and these are not to be turned in， we will not grade them if you're turned in any solutions。

So the point of the exercise sets， it's really a framework for you。

 that gives you sort of a litmus test for whether or not you're understanding what's going on in the two。

So if you can answer those exercise set problems， then you're in good shape and if not。

 then well they're not turned in， so just talk those in office hours。

 we're happy to just walk you through the solutions for anything that doesn't。

Now as far as incentive to actually look at it to actually do the exercise sets， the final exam。

 I'm going to promise you at least 50% of it will be drawn either directly or will be minor variants of these problems that show up on the exercise set questions so it's what I think is really important for you to take away from the lecture。

 so no coincidence it's also where。ば。So that's a nonnuable。So what are you grade on。

 there's going to be four problem sets。So that would be 75% of the grade。

 so these are to be done in groups， groups of up to three。And only one right up per group。

So you can split up the problems amongst you， or what I'd recommend is at least two people work on problem so you can exchange it。

口完住。So a few goals for the problem sets， so one thing I'm trying to do is just basically give you a way to think long and hard about algorithms outside of class。

 which is really kind of the experience of learning algorithm you probably already saw this some in CS161。

 tough problem you just got to think about for a long time to crack them but in doing so afterwards you feel like you're a little smi。

 so to sort of give you that experience in the problem sets。

I want to give you an opportunity to collaborate with other students which especially in a class like this for these kinds of problems I think it's really fun actually to cooperatively solve these problems and then third through the problem sets I'll be able to supplement complement the material that I do in lectures so you'll actually learn new cool results through the problems that。

For that reason， they're pretty challenging， you can't sort of learn stuff for free。

 it takes some work， so you can have two weeks to do them， they'll go out every Tuesday。

 starting next week， they'll be two weeks to turn them in。So budgets and time for that。

 I think most of you will find them challenging， interesting， I hope the challenge。

And there is a late day policy， I'm not going to talk about in class， it's up there on the website。

 which at the end。It is live。That's the first thing and then I alluded to a final。

So the final will be in class three hour exam at the time specified by the registrar。

 and this is very different from the problem sets， in particular the final question is going to be much easier than the problem set questions as reflecting the back of in class exam。

You don't have two weeks to do it， and the goal is also quite different， right。

Whereas here you're really going to be building and extending the lecture material for the final I'm really just making sure that you've mastered the most basic and useful concepts that we teach in 61 so it'll all be stuff that you saw in lecture if you sort of understood all the lectures it shouldn't be really quite easy last year I actually got complaints on my evals。

The find was too easy。Which is I don't if you know my reputation， CS161 never had that。And again。

 as I said， at least 50% of it， you already know what the questions are will be drawn from the exercise。

So， and then that's it， that's the st。あどかどうこ。Any questions？あ two。So there's no textbook。

 but I will be posting Western notes。AndI write the lecture notes after I give the lecture。

 so this should be up on the web generally。But when the lecture occurs。

 so that'll be the primary source， I'll post other resources。And again， as I mentioned。

 the videos will be taped and up on YouTube within a couple of days after the lecture。

 so if you want to rewatch one or if you're out of town or something or sick for one。よこし。All right。

 then let's go ahead and start our first topic。It's no problem。

So this is a stone cold classic algorithm。over。So it's very easy to understand intuitively。

 let me first just kind of give you a sense forward through an example。

 then I'll give you a formal definition。So it's problem in graphs for networks。

So I'm going to draw a picture which is going to look a lot like the pictures we drew after you study short path。

Although the semantics are going to be different。So we have a directed graph。

 you can also look at maximum flow and undirected graphs。

 so I'll ask you to explore that in the first exercise set， but for lecture。

 let's just think about directed graph。Each edge has a number of attacheds to it。

And the meaning of that is the edges capacity。So that's the amount of stuff。

But the edge can carry in some sense。And the Max problem is all about understanding how much stuff。

Can you push through the network？From S， which is called the source for text。

Which is called the simple。So for example。In this network。

It's clear or if you think about it a little bit， actually。

 let me ask you to think about it a little bit。Even though I haven't defined the problem formal。

 so just informally， if these numbers represent how much stuff an edge can carry。

 what would be your guess about how much stuff you could push for Minister？So I heard of you find。

 which is a good answer。So here'd be a way you could push five units。

You send two units on the upper two hop hat。Two units on the bottom two up。And then a fifth units。

I'm a zigzag。And the amount of stuff you're pushing across any edge is at most it capacity。

 rescinded。You要先面。Three units of flow here。这从老 here。You to flow。Well here。

And so the point is all of those purple numbers are most of like。その作た。

So how know we can't send more than five units？在哪里？This is a way to get five。

 so shows we get at least five。Could we possibly have more of than？We couldn't。

 and it's actually kind of obvious to see why， which is， just look at the source ver S。

We only pump five units out of the source。So that's the total capacity outcome going。

So five is the best history。So that's sort of the gist of the maximum flow problem。

You me define a little bit more formally。So given as input a directed the graph。The vertices。

Directed edges。Again， Max flow the algorithms we'll talk about also work on undirected graphs with minor modifications。

 as we'll think about。There's a source for T S。Capacity for simplicity with。Afters with ingers。

So an integral capacity。To just like picture。这言会。Now what are the feasible solutions。

 so what are the objects that an algorithm is allowed to output， what are going to be flows？

And so in the picture I described flows by drawing these paths。But for algorithms。

 it turns out to be much better you just think about sort of the superposition of the。

And think about these purple numbers， remember these purple numbers or what's the total amount of stuff being sent on a particular edge？

So we're going to work with these flows on edge。So what is the flow？We sign a non negative number。

To every age。And again， in this example， these non negative numbers correspond to three， two， one。

 two。Three was the noinated members of talking Brown。And to be a flow。

 you have to satisfy two types of constraints。The subject2。So first of all。

 there are capacity constraints， you can't send more stuff on an edge than it has capacity。😔。

So the way you write that is just F。Well。おります。All edges is within those are capacity constraints。

And the other thing we need is we need what are called conservation constraints。

So if you look at any vertex V other than the special source and the special sink。

 it better be the case of the amount of flow going in。The same as the amount of flow going house。

What I mean by the amount of flow going into the vertexivity is just what you think I look at all of the edges that enter V。

 I sum up the total amount of stuff that any of them here。

Llow out is look at to be outpoing edges that they're going to sum up the flow。

It just says the total flow coming into D should be the same as the total flow going out。For example。

 here。Think of ver text like this one。So we have three units of flow going from S to this vertex。

 so three units go in。Three units also go out。Split two on this edge and one on this edge。

 but still the total flow out is three， which is is the total flow。So that by definition is a flow。

 there a non negative number on each edge that meets the capacity and conservation constraints。

if you have an outputs， number is satisfying the feasible solution。Of course。

 you could just send everything to zero。be a feasible solution， not solution。So， we actually want。

这去的。The goal is to amongst all flows。Maximize the flow of value。What is the flow value。

 it's just the total amount of stuff going out of the source。Again， here。そ问。Pro of those countriess。

So one minor detail don't worry about this if it hasn't occurred to you。what's the point of a source。

 stuff's supposed to go out of the source？So there's no point for that to be an edge going into the source。

😔，That has no point， similarly there's no point for an edge out of the sink because stuff is dested for the sink。

 so just think like we preprocess the graph in advance and we delete any edges going into S。

 we delete any edges going out of it。😔，So no edge。That's。

And this is without loss of generality because those edges would be not useful for a maximum。

So S just as edge is only going out， T as edge is only going。

That's a flow among all flows we want the ones to push the maximum possible amount。

Out of the source as we'll see， this is the same as maximizing the amount of stuff going into the sink Okay。

 so just as five units go out of this， there's also five units going。It well。二位。The questions。About。

Definition of an maximum。Can there be multiple things？Good questions。

 that'll also show up on the exercise set。The short answer is yes。

short answer is that and this is the point of exercise that again。

 maximum flow in the seemingly more general case of multiple sources reduces to the case ofre recovering。

Again， that's something I hope really， it'll be an explicit theme， especially in the exercise helps。

We'll cover a basic algorithm， but actually lots of bells and whistles。

 you can really just produce back to the basic algorithm and it's very useful。

Another question you might ask is just why should you spend time on a nice phone？

Who cares about an maximum？So like all of the kind of great outweing problems。

Maximum flow both just sort of arises naturally so sometimes you just literally care about the maximum Pro problem。

 but and something that's a little less obvious what we'll see throughout the course is that many applications are really just thinly disguised versions of maximum flow and again we'll give some air time to that。

futureな。So for example， all these some very kind of obvious applications of very literal translations。

 you can think about road traffic and transportation networks。

datata packets and a communication network， you get to about oil being routed through a oil distribution network。

 and indeed this algorithm has been used in all of those applications。

And it's sort of a very natural way to model them。Les obvious would be why something like image segmentation。

 so given an image。Pasify the pixels into a foreground and a background that also turned out to be reducible to the maximum。

あです。Okay， so that's the problem。I want to start talking about algorithm。And know again。

 because you're sitting in this class， and getting lectures on this。

 you probably have in your minor case， it's going to be some fast out。But keep in mind。

 if you've never seen this problem before without picking about it， we're all we know at NPPB。

So it would be cool if there was an efficient hour because later in the course we get spoiled in the first half。

 but the second half we're going to have equally natural problems that don't have been fast out。

So here we're still in a happy case where we had that。Okay， so。How should we tackle the mass？

か you think。I think you be。Well， let me give you idea number one。Yes， by number Mo。Here number one。

 I mean this will not be。Sufficient。It's a good starting point。Which is， okay。

 so we learned a bunch ofy algorithm algorithm design paradigm in CS161。And in many problems。

 a good one to start。We had this greedy greed out。Very commonly greed algorithms do not work。

But usually at least trying them out and seeing why they don't work。

 you understand the problem better and you get a better idea of what good algorithms go。😔。

So even when they don't work， it's up with useful exercise。All right， so what's going to be？

Our first attempt。And it attempt number one， so giving it away that it's not going to work。

 it's an applicant to try。AGy algorithm for the maximum。

So we're just going to compute a sequence of loads。Each one having higher value than previous。

So you start with the all zero flow。to send everything to zero obviously satisfies capacity and conservation constraints。

Now we try to make the flow bigger。So how do we try to make it a little bigger Well。

 actually it's sort of a lot like what we did and when we first sort of played around with that very first example。

 we're going to look for a path。Where there's capacity left over on every idea。

And then we'll route flow on that。I think it's a very natural first algorithm to try for Max well。

a little more formally。We search the graph。For a path for an ST。So that all of the edges have roof。

The current amount of flow on the edge is strictly less than the capacity。We alls on the。

So I guess we needed a subroutine to do that。So how fast can we accomplish that？I give you a graph。

 I give you a flow。I want you to find me a path for SD。With his room on everyH。

 or I want you to correctly report that no。How long does that take kind of running？

So what would be a sub routine team you could just plug in and basically solve exactly that problem？

ちせだね。D。 Zs actually slightly overdue。Because we're not only' shortest path。

 we're just looking for APp。Breread first search or depth first search。

 your favorite linear time graph search algorithm to check whether or not there exists a path in a graph between two designated birds。

So this is something you already know to do。And the good news is is it's linear your time。

 as somebody mentioned。So linear time。I would say breathth for search。Reject。By the way。

 I don't know if my handwriting reputation precedes me or not。

But I definitely I' wondering no delusions about it sporadic。Reibility。

Soll give you all an infinite quota to clarify what I wrote。Thiss we got excited to start writing。

So suppose me okay， so you might find a path you might not。So we don't find a path。下问地吧。

We just stopped and we just output whatever the final。If we do find a path。

 whether we just do the obvious thing and increase the flow along the。As much as we can。So otherwise。

 suppose we find a path peak now there may be many paths peak for now let's just think about picking one orator。

Arbitrarily classroom against with room on every edge。With capital Delta。Deote。

The amount by which we can increase the flow along this path。系呀。So how much is that？Well。

 for a given age。This is how much room we have to increase its supply。

It's capacity that sounds we're already rabb on。On the path overall。

 well we have to make sure we satisfy each of the capacity constraints。So we look at the minimum。

Overall， the edge didn't impact。So this is the room left on an edgech。不该 from。

So this is the minimum amount by which we can increase flow on key without violating capacity constraints to nuts。

So that's basically completely specified element。I wouldn't agree。

You feel like we just go code this up and Python and happen it out。All right， and again。

 this is a totally reasonable thing to share。The question， of course is， does this actually work？

All rightSo what can it mean to not work Well it's going to terminate。It's going to output a flow。

so it maintains the fact that F is a flow by induction， it's an invariant， the all zeros。

 that's a flow， when you increase things along the path。

 well for any vertex on the path the incoming flow goes up by delta。

 the outgoing flow also goes up by Dlta， so they stay equal。

So it's doesn going to terminate with a flow， the way it could fail would be to terminate with a flow。

 which is not a maximum。Does anyone see？An example。

Where this algorithm might not it might actually terminate， or the flow is non accident。

Hint is a total of one network。And what good。Well， if you took that network， started zero。

 then you took at the zigzag first and increased it。2，4，2。对。So here's the observation。

So suppose you try to run this algorithm。On that graph。So if you want on this route。

So forget about the pink flow， imagineing a era flow and we go back to the all zero flow。

What's the first thing we do， we look for an ST path。Specifically one that has room on all the edges。

 but of course with a zero flow， everything else。These are all ST paths are legit。

We're going to pick one arbitrarily if we pick the zigzag path。So this one here。

And we route three units。On the blue zigzag path。And again。

 that is something that this algorithm might do。If it doesn' it， what happens in the next iteration？

It looks for some path from ST where every edge has roomnot in it。

And no longer are there any such power。Because every S path includes either the upper left edge or the bottom right edge。

 both of which you' saturated。So that triggers the stopping condition for the algorithm。

The flow that it returns has value only three。But we already know that the maximum flow values。

Secondく。So first algorithm doesn't work， that's fine， algorithm design is a process。You start simple。

 cross your fingers， figure out if it works or not， if it doesn't。

 you ask okay what other ideas are needed。So。Let me justSo what's an issue？Termininates。With nonna。

So this type of non match flow， it's something called the blocking flow。

 so that's what it means when you sort of plugged up all of the SP edges and we'll talk more about blocking。

Next lecture is a sub routine in the maximum flow out。O。But it may not be maximum。

So we wanted to do something smarter。What could we do。So suppose the algorithm gets stuck here。

 so it routes these three units on this glue path。You stare at this a while and youre？I mean。

 I guess it's sort of stuck in the sense that there's no SD path where everything has room。

 but if you just sort of allow me to undo，😔，Something I did last generation。

 I can totally make a product。Right。Why can't I just route two units。

 suppose the blue path has already been routed？😔，And now imagine we send two units of stuff down here。

😔，Now we send it backward。Im doinging。Part of what we push downward。

And then we just send that two units the rest of the way to tea。So now with one fell swoop。

 this one reverse zzag augmentation， you've actually transformed that blue flow into the maximum。

So that's sort of the intuition， it's kind of like， well， you know， it's a greedy algorithm。

 you're not supposed to be able to like undo things。

 but maybe we can just have sort of a next double greedy algorithm where we have limited undue power。

 namely we routed something in one direction， we're free to route it back the other direction later if we want。

So that's idea number two， and that's the only other idea we need to get our first correct。Some idea。

All undo。Operation。All right， so we need it's sort of clear what we mean in a specific example。

 but we need to be principled about this， and we need to figure out a way to sort of tell。

A computer sort of really encodes an algorithm what you're allowed to do any it of the new most sophisticated greedy algorithm。

So that brings us to a very simple but also sort of really important definition。

That of a residual graph。Again， the point of the residual graph is to encode what are the allowable undo operations。

 that's the point of definition。Sose you have a network G and you've got a current flow app。

And again， think about an example being that blue flow and that network on the top。Thats flow。

I'm going to explain to you what is the corresponding residual graph。実速。So given a graph。

 given a flow， I'm going to tell you about a new graph called the residual graph， G sub that。

What happens is that you keep the ZXN vertex set to the vertices of the same as N G。

Each edge in G spawns two edges。In G subB， one going forward。One going back。

The point of the backward edge is to encode the undo operator。So if。You have an edge from U to B。

Where the current flow is F toB。And个办案有有势的。We'll give rise in G of F。The two edges。A forward edge。

 meaning one going the same direction as the H and G。And this will have residual capacity。

You my respect。Did you going to make sense？It started with you and your unit capacity。

 you've already routed SD， so the amount of residual capacity capacity that's left is the difference。

To rehearse ourrc， this is where。The meaning is to undo previous stuff that we routed。

And so for the reverse arc， the residual capacity is defined。Absolutely。They used to have。

An edge with capacity U flow F that gives us two edges a forward edge of residual capacity U minus f。

Backward capacity or reverse edge capacity。So let's actually draw。residual network。For this graph。

And the blue4。So this a， I should mention。It's possible that when you cast the residual network。

 you might wind up with up to two parallel edges between two vertices in either direction。😡，That's错。

That causes no problems for any of the algorithms immigrant。All right， so for this network。

 there are five edges。So in the corresponding residual network， we'd expect to see 10 inches。

Zcheju and Jig is rise to two edges in opposite directions。We Chief back。Again。

 Air fromm taking to be the bluest exact clothes。Now， actually of these 10 edges。

Four of them just have zero residual capacity。I namely。

If I look at the bottom left and upper right edges， I haven't sent any flow forward at all yet。

So the reverse arc has residual capacity zero。And the forward version。

On the upper left and lower right edges， because I've already maxed out of the capacity。

 the forward versions of those edges have no residual capacity。

So I'm just going to admit those four edges from the picture will be left with a network with six。

So what is it？Soir。I have the backward version of the threes。

We still have the forward version of the twos。And now this is the one where we actually get both the forward and the reverse version。

So the forward version。Goes in the same direction as the original。

Over here we had original capacity five forcinending three units of flow。

 so for the forward version we have two units residual。

And then the reverse edge corresponding to an undue operation。three units。

So that's the residual network。We just scratched。Any questions about that？

And I want you to notice that。Something that we sort of hand waved through。

 it now shows up very precisely in the residual network。

We talked about how it was sort of annoying to get stuck with the blue flow because intuitively we just wanted to route two units。

On the reverse exact path， undoing some of our previous。Ring downward。And so that。Roouted doing our。

Operation。Tranlates very directly。And they're outing two units of flow on this particular path。

So in the residual network， I'll give you the formal algorithm in a second just just to make sure you have your intuition in the right shape。

When you wrap traffic through the residual network intuitively on all of the forward edges。

 you're doing the same thing you were doing before。If it hatch to the capacity you left over。

 you're now increasing the flow value。Whenever you route。When you're at flow on an edge。

 which corresponds to a reverse edge。That's undoing flows that you route in the forward direction。

Okay。So that's the vision。So。What's cool， like I said， we don't need any more ideas。

 so basically we're just going to do the greedy algorithm except in the residual graph。

Other than that we're going knew everything exactly as before， and that's going to work。

Not obviously works， that the prove view it works。不是。

So let me sort of do it as sort of edit distance from our naiverie algorithm。

So test number two is actually a famous algorithm。Orward。A long time ago， mid 50th。Start to saying。

Miitialize with the zero flow。Now here we're going to do a different search。

So this is the whole bug of the 93 out。Because it gave up to easily。It might be the case。

 you can't find a bathroom as to T where there's residual capacity in every edge。

 but still if you can undo stuff， you can make more projects。So we're going to do。

Instead of writing search for a path key。So the flow is less than the capacity on the。

We're going to say search for a path key。In the residual network。

Search for an ST PA feed from the current Re network of GA。At all given times。

 we're going to have some flowette。Any given time is a corresponding residual graph G set。

It may or may not have an SP path， but we want to know。look for answer。Just like before。

 this is just a graph search sub， literally you're just checking for the existence of an SD path in the residual graph。

DFS， DFS， whatever， gives you linear your time implementation。

If you don't find an SD path in a visual graph， we don't know what do to're in a haul。

If we do find a path from S to T in the residual graph， we want to augment along。

We want to min along it as much。So。In the residual network。

 the forward edges have this is their residual capacity。

But the reverse edges have just kept to that residual。So let me just replace this。から年自。そ咩。

The residual。So what does it mean to we min？我话咪睇啊。In the residual graph。Well。

 it's a mixture of increasing the amount of flow on the forward edges。

And decreasing the amount of flow on the edges corresponding to reverse it。なです。Instead of just。

Oage is B&P。I'm going to say for all foreign edges。这样子。They actually。Re reverse。Ts。

And that's the entire full purpose out。Any questions about。It's definition。

If you feel like you have trouble coding this up in Python in a short amount of time。

 if something doesn't make sense， let me know。So。Just as a sandity check。

 back in our running example。So again， there may be many choices of this path。

when the residual graphing may be lots and lots of paths from ST， today。

 let's just think about taking an arbitrary one and be smarter about that choice on Thursday。

So if you run this full focus algorithm。On our right example， the white Ne。Again。

 in the first iteration， it might do the same thing as our Naive Go。

It might well route to three units along that blue is exact。

But now I going algorithm that doesn't give up。It forms the residual network。Yes we have there。

And it finds one name with a purple panel。It looks at the biggest residual capacity of the three edges on the purple path。

都。The smallest residual capacity， which is two。Two units along that path。

 which corresponds to increasing the amount of flow hereby two。

 increasing the amount of flow hereby two， and decreasing the amount of flow hereby。

And once we do that， we get exactly。two iterations。For focus dozen't be。

C the maximum flow in this particular example。It's hardly proof that it all works。

 it's a sanity check that at least it fixes the problem have。没 agree。没告。めぞ。Okay， so。

Let's talk about whether or not this。Why are you。For all we know。

 this prediio is as broken as our previous。We're watching this example great。

 but it's not clear what that cells looks more generally。

So I want to focus on correctness today we're not going to talk about running time at all。

 we'll talk about that in future lectures。So let's just try to understand whether or not the whole focus algorithm terminates with a maximum。

Well first of all， I certainly claim that it terminates。This is Samy check。When。

Why this thing can't run forever， I mean， intuitively it's because it keeps making progress。

 keeps sending more and more flow at some point you're going to run on our flow thing。

The towns are really go。The first qua。board focus how we're going to maintain the flow gap。

So obviously you start with the all zero flow， that's a flow。

 the claim is every time you do one of these augmentations， you again get a flow。

So strictly speaking， there's sort of like four cases here because in a given verex in the path。

 both the incoming and the outgoing edge might be a forward edge or reverse edge。for example。

 if they're both forward edges and the flow in goes up by Dta。

 the flow out goes up by Dlta so it' still the same， if they're both reverse edges。

 the flow in goes down by Dlta， the flow out goes down by Dlta， but this did the same。

It's all four kids。So augmenting along a path of the residual graph yields。To maintain the。

In particular， the conservation。The second thing which is worth noting。

And this is why I assume that the capacities are integral integralteger。

I claim him that at all times。The current flow F uses only integer value。And again。

 like the previous one， this is going to be by induction on the number of iterations。

if it's true so far， all the flow values are imagesteger。

Well remember the capacities are also injuries。So everything in the residual network is a manager。

So Delta is going to be injured。So the flow stays in。Let me just keep repeat。

Why is that interesting or why is that useful， well， if it stays in integral。

 then it means every iteration you're routing at least one unit of flow。

So Delta can't be smaller than one， there'll always be at least one。

You start worried about a Xenos paradox， maybe you've about a half and then a fifth and then a 25th and your worried has never stop。

But given that you sent at least one unit to flow every iteration。

 and given that there's a finite amount， the capacity you say out of the source vertex that's clearly can't go on。

It's got to terminate？When it terminates， it terminates with the flow， so again。

 the only way it could not be correct is if the flow terminates with is not maximum。

So I'm not spending a maximum flow right now， spending is current。But you know。

 weve really at all this stuff。All of this exact same facts are true， but I housing doesn't work。

So what's different now？Well obviously what we're hoping is that because the residual network includes more augmenting paths than in our naive gritty algorithm by having these reverse arcs。

 we expect it to make more progress。Before it finally gives up and stops， the question is。

 is it get all the way there？before it stop。So this leads to sort of a very basic question。

 which is going to be really maybe the major theme in the first half course。

Ifre designing algorithm like this algorithm for maximum flow， how do we know when we're done？

By which I mean we've got a flow in our hands， how do we know whether or not it's a maximum？😔。

And so really， if we want to terminate this algorithm and be correct。

 we need to somehow know or be able to prove。That our stopping condition implies that you can't do any better。

That's what it means to prove an algorithm like this correctly from people。

It knows that you're going to be。And this is relevant， frankly， it relevant。

 even if I just sort of handed you， say there was a big network。

 and I gave you a flow and I alleged that it was a maximum flow。Is there some simple way。

 some simple check you could do to see if I'm or telling the truth？

But I wanted to convince you something was not a maximum。If that would be easy enough。

 I'd just show you a different flow that was even bigger and they're like， oh yeah， at this point。

But what I want to show you that there is no flow better than this one？然后他就取的。这翻译的太狠。Right。

Then I think what you're getting at is if you don't。对对。No， so you do find it happening。

Then I can show you the video。So' you're getting ahead of us， but it's a good point。

We're interested in the Congress。So suppose this algorithm fails to make progress。

Is that because no more progress is possible or is it because their algorithm is through？

That's our first algorithm。Spped， but it was because the algorithm was done。

 It wasn't because we hadt。And so now we're again in the same quandary。

 I've already kind of given it away that here actually you are correct。But how do you know。

How does the algorithm somehow know it's done it？Sure， that'd be great time defining an income。

就我我啲得放过。あなそ。So how do we know that we're just？So the algorithms at some point it's terminated like can do better。

 and so again， this is going to come up over and over again in the problems we study in the first half it'll culminate with linear programming dual。

 which is in some sense like the ultimate answer。But how you doing。

At least four problems tend to be hollow on。So maybe just to illustrate the points。这是用这的。

Suppose I keep the same network， but it just changed the capacities a little bit。

so I should recall at the very beginning of the lecture。

We had a Max flow example and it just didn't seem like a big deal to know that we were done。

It just drew the pink flow。We sent five minutes。When he said， well， just look at the source。

 you can't have more than five humans coming out of source。

 so clearly you've met the destinations area， good job you next。

But imagine I tweaked the capacities a little bit。Imagine these are the capac。

So it's sort of unclearcru， you might be hoping that the max flow value is about 100 them。

But what have I tried to tell you that actually。The best flow only sends。都异议。

So consider the following flow。3。So I' said three out of S， split one， two。

Csymmetric on the other side and then one up and none down。

So one thing that's easy to check is that this is indeed the flow。Theac fans are satisfied。

 solar conservation two units going in here。That's going out from those two paths。

So this is a flow of value three。But do you really believe that there couldn't be anything even better than having three units？

With all these huge passes on。Certainly， the total amount of stuff that the source can send out is 101 way way dividend than flu。

Same thing for the sink teeth。There's no obstacle。So how would you convince someone that this is？主这个。

Do this formally on Thursday， which is kind of。Plant the see through the foreshadowing。

Here's the idea。Suppose rather than looking only at what's happening around the source。😔。

What was having around the sink？Suppose I split the graph actually into two pieces。

 which are sort of more complicated。So I'm going to single out the source and also this bottom birthday。

Look at all of the edges。That go out of this set。Meaning that either go out of the source or go out of this place。

What is the total capacity available on all of the edges？Going out of this step。3。So。

I claim again went to discuss Thursday， that this is the exact same kind of obstacle to having a flow of a certain value。

Before it was a little simpler， you just sort of sort there's only five units out so you can't do better than five。

 but here now I've drawn kind of like a big moat。Around you with a source somewhere in the middle and the capacity across anywhere of this mode is only three。

all flow going to the sink has to cross this moat， because there's only three units of capacity。

 the best case scenario is that you send a full three units through that cut。So that's the idea。

 that's sort of where we're going， is how we're going to sort of know that we're done in maximum flow problems。

 we'll be able to actually exhibit obstacles called cuts to this form showing you that there prove that you can't do better than the flow you have so far。

So that's a little bit of a digression。We be a little more precise now。

Explain how we're going to go about answering。This question， how do we know when you've done。

 how are we're going to go about answering that？就は。So the approach， which I'm going to be。

Which is classical。It give me a two step approach to answering this question。Step 1。

These are going to identify what are known as optimality。So this part of the paradigm is structural。

 it's not out。so there's no algorithms in part one， you just identify a sufficient condition。

Where if the condition is met， then you know that you're optimal， so for example。

 you know that a flow is maximum。I'll give you an example in second。

So the first goal is to write down the sufficient condition for correct sufficient conditions for optimality。

And then the second part is to design an algorithm。Where it only terminates。

When it meets these optimality conditions。S an algorithm。Determininates。For the optimal conditions。

So just by definition， we can do both steps one and two。

 it will follow that this algorithm is correct。The automatic conditions give you a sufficient condition of correctness and the algorithm going to always be。

And。This is actually， this really didn't come up in CS 161， you think of that。

There's plenty of correctness。1 sixty one。But like none of。They're all like。Really boring induction。

With no ideas with。Think about like merge to or something， divide and conquer out。

Think about the diykestra out， just a simple induction on a number of heres。

 think about dynamic programming and do the subprobles right， you get the overall problem。

And the story。So the problems in 261 are going to require this more sophisticated approach and you''re not really to be able to get away with just sort of at the same time doing the algorithm。

 doing the analysis and being correct you to actually take a step back。Think about the problem。

 think about what it means to be optimal， and use that as a guideline。😔。

To come up with what are sometimes not the first algorithm that you might think about。

And even full focusing is sort of an example of that。Maybe it's the second algorithm you think about。

So I know this is a little abstract， so how would this work， for example， for the maximum profile？

The claim。It's not hard to prove， but I'm going to defer the proof till Thursday。

 just we've already covered a lot today。And the point of this claim is to identify optimality conditions for the maximum。

Sufficient condition for a flow to。And this was there was a question alluding to this。earlier。

So suppose you have a flow graph， f than a graph G。And the residual graph， G sub F。

Has no path from S toT。The claim is this is a sufficient condition for optimism。

So if there's no ST path in the residual graph， then。That is a maximum。

We're going to prove this to you at the beginning of Thursday。But for now。

 let's just sort of accept this as true。And see what it like。So this is part one。

 sufficient condition problematic。Mardu says design an algorithm that terminates with those conditions satisfied。

Well， what's the stopping condition of the full Ferson algorithm， the stopping condition is exactly。

That there's no after residual threat。So actually， we've already solved part two。

 we already have an algorithm that only terminates when the conditions are satisfied。

There's a corollary。いかしなる。Yeah。Meaning that is guaranteed to terminate the mass。

Unlike the I agree algorithm。So just to be clear， I havet prove the claim。

 so you shouldn't necessarily see but the claim is true。

 but you should understand why the claim implies the court。And if it doesn't make sense。

 we answer the question。Is the claim only of。For that。2016。

It's hard to know how to phrase uniqueness。conditionss， but it's by far the most du one。

And it's the only one we all have occasions in using。So this is， this will be。

Very use all of our maximum algorithms。This will prove。Of course。Total number of pounds。

Good question， so yes。There are ways to remove the invalidity condition。

 so the first thing you realize is just that know rational numbers may as well be images。

 but you can always just clear denominators。And of course， if you just multiply everything by a000。

 it doesn't change the problem。So the only difference would be between rationals and real numbers and then it sort of depends what you're trying to do talking about algorithms。

 it's actually it of annoying to even talk about what does it mean for an algorithm to manipulate。😔。

Numbers with no final representation， if you just want to talk about like structural results。

 then you can do simple limiting arguments。So it's too ir rational。So the Maxloian cut theorem。

 for example， I'll prove it on Thursday for the integers， but it's true for the real。おりばし。

the original。Between two notes， I just going both ways how we're going to go。Good。

 so the residual graph will just have two parallel edges going into。And there's no。

Kwing an implementation and a real implementation， you might want to think about merging parallel arcs that go the same direction。

 but for lecture， let's have this sort of wasteful representation where we have possibly twice as many to。

But you're right， I mean you do get in general， get two in。おかしす。I don't really see the twoで。Like。

 why would you get to in different direction？It just because every edge of the original graph gives rise to both a forward and a backward。

So imagine you started with a graph。With an edge going。

 say upward and a of edge going the opposite direction。Oh sure。 okay。就道ぞ。

So in the forward one't me give you two weeks direction the other one。不会。

So playing going forward on Thursday， I'll approve the claim view finishing the correctness of Paul Ferguson。

 andm going to state and prove a famous and beautiful result known as the Maxcoman cut throughin。

There's another way to think about。These optimal conditions how to think about how are you done in an next slow problem。

 and then we're going to turn our attention to fast housing。

