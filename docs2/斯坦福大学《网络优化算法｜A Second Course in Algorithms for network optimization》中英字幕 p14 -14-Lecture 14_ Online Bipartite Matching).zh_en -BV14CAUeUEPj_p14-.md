# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p14 -14-Lecture 14_ Online Bipartite Matching).zh_en -BV14CAUeUEPj_p14-

This is going to be our final lecture in the third section of the course。

 which has been on online algorithms， so we're going to culminate in this section with a discussion of the online bipartid matching problem。

Some of you just quickly remember what that is， so it's going to be bipartid matching。

 so there's a left side call it capital L， a right side call it capital R。You know。

 the whole left side up front。 Okay， I tell you that before anything starts。

 It's the vertices of the right side that come online one at a time。 Okay。

 when a vertex on the right hand side shows up， it shows up with all of its incident edges。

 It's a bipartite graph。 So all the incident edges go back to capital L。You want a matching。

 you want a big matching， the rub is that you can only match a vertex on the right hand side at the moment it shows up。

 you can't delay and wait to see who else is going to show up and then match it later okay。

So that's the definition of the problem。 And the goal is just to compute you a max matching。 Okay。

 so there's no edge weights， just max cardinality matching。

 You'd like that to be as big as possible as big as the max matching in hindsight after you've seen all of the right hand side vertices。

So any questions about the problem， this is what we had last lecture。

Last lecture I also sort of told you about a killer app of online bipartite matching and web advertising。

 the interpretation being the lefthand side vertices。

 which you know upfront those correspond to advertisers who have purchased a certain number of targeted ads and then people potential customers come in online like as soon as they type in a search query or as soon as they view a content page and the edges correspond to the potential consumers on the right hand side who match the targeting criteria on the left hand side it's one reason why this problem's gotten a lot of attention over the past know seven。

 eight years or so。Comicical announcements problems at number three as I'm sure you know is due Tuesday。

 I posted the seventh exercise set and then my office hours they're normally three to four today。

 there's a talk I have to be at so they're going to be at four to five instead okay so one time only my office hours will be one hour later today okay。

All right， so we'd like a good online algorithm for this online bypartite matching problems。

 we'd like a good competitive ratio。 Okay， so we'd like to always produce a matching。

 which is almost as good as what we could have achieved with full hindsight。😊。

So what kind of competitive ratio can we expect to attain so remember last lecture we saw online scheduling。

 we got a two competitive algorithm， we studied the onlinesteinner tree problem。

 we got a log K competitive algorithm where K was the number of terminals。

 so here we're trying to maximize so we'd like to get as close to one as possible。

And so an example that we went through briefly last lecture， I'm going to go through it again。

And so what the lecture shows is that with deterministic algorithms， you can't beat a factor12。

 you cannot have a competitive ratio strictly closer to one than one half。

So no deterministic algorithm。Has competitive ratio。Figer and a half。All right。

It's a very simple example that shows this。So you're going to start with two vertices on the left hand side。

So you're thinking about some arbitrary deterministic online algorithm。

A vertex shows up on the right hand side。Connected to both of the vertices on the left hand side。

So the online algorithm it now has to make a decision it can match it to neither one but that would be a disaster if this is the only vertex that ever shows up or it can match it to the top vertex or to the bottom vertex And the point is no matter what the online algorithm does in the first step。

 there's a vertex I can feed it in the second step so that it regrets what it did。So for example。

 if you have an online the algorithm in question。Pickix this edge to match。Then what I'll do。

So nefarious leaves， define the second vertex so that its only neighbor is to the one that you already matched to。

And then that'll be the entire input。Allright。So the algorithm will just have a matching of size1 where as clearly a matching of size 2 as possible。

 obviously by symmetry， the same thing is true for deterministic algorithms。

 which pick this edge instead in the first step。So no matter how smart you are。

 just because you have to make this decision at time step one without knowing what's going to happen later。

 deterministically at least you're going to be off by a factor of one half at least。

So algorithm equals one， but optt equals two。Everyone clear on that argument？

Just a simple adversary argument。Okay， so this raises a couple questions。

 question number one is can we achieve one half， is there a matching positive result with a deterministic algorithm say？

And then the second question would be can randomization help and allow us to beat the one half Remember。

 for example， that when we talked about online decision making。

 it was totally crucial that the algorithm had used randomization。

 Remember we had a lower bound for deterministic algorithms with respect to the regret benchmark So we're used to the idea that randomization can help with online algorithms。

So the answers to both those questions are yes， so you can get a 0。

5 with a deterministic algorithm that's a pretty easy result， which I'll show you next。

 and you also can beat one half with randomization and I'll give you the main ideas of that in the remainder of the lecture。

All right， so as far as the matching positive result。All you need is greedy。

So greedy has competitive ratio。One half。What do I mean by greedy。

 I just mean when a vertex shows up on the right hand side， you look at his neighbors。

 obviously all of its neighbors already matched， you can't do anything。

 but if at least one neighbor is unmatched， you match it to an arbitrary unmatched neighbor okay？

So that's the greedy algorithm and the claim is this always will output a matching with size at least half of the maximum possible。

Now this is actually pretty easy to prove directly， but that's not what I'm going to do。

 Okay so I'm going to give you a more sophisticated than necessary proof of this claim because this argument will generalize usefully when we talk about beating the one half with the randomized algorithms okay。

So the what we'm going to do it is actually buy duality， so weak linear programming duality。

So let me remind you what the primal and dual linear programs look like for the max Carinality bipartite matching Pro。

So for the primole。Right so the semantics R here is we're thinking of Xc being one for an edge in the matching。

 X is zero for an edge not in the matching， we want to maximize cardinality， There's no cost notice。

 just maximize cardinality。What are the constraints， Well。

 we're not insisting that it's a perfect matching， we're sort of hoping we compute a perfect matching。

 but it's not a feasibility requirement。 We just want it to be a matching。

So that means for all vertices on either side。If we sum over the edges incident to the vertex。

And most one of those should be in the matching。Okay。And then these should be non negative。All right。

Now there's a few minor differences between the primal dual pair we looked at back when we were talking about bipartid matching because back then we were thinking about the min cost perfect matching problem Okay so here's no costs and there's no need to restrict attention to perfect matchings so you see the two differences instead of having a min and min cost perfect matching。

 we have a max and instead of having equations here。

 which is when we're insisting on a perfect matching here we just have inequalities。

 those are the two differences between this primal linearial program and the one we talked about a couple weeks ago。

So the duall is basically the same as what it was before， although again with just some minor tweaks。

So before the dual was a maximization， but now the prim was a maximization。

 so the dual is a minimization。Again， there's going to be one dual variable per constraint。

 so per vertex is going to be one constraint per variable or per edge。

So we want to minimize sum of the vertex prices。And so because it's minimization。

 these inequalities are going to be greater than or equal to inequalities。So this is going to be。

PV plus PW for all edges。VW and the graph。And in case it wasn't clear。

 so we're thinking about sort of the graph after we see it at the end of the algorithm。

 these linear programs are going to be only for the analysis， so we just run the greedy algorithm。

 we let it run and then this is all sort of an expos facto analysis of what happens so this is where every edge that ever arrived。

And then previously because these were equations， we had real value decision variables。

 now these are inequalities。So we have non negative decision variables。Okay。So。

That's the primal dual pair for the max criminal bypartite matching。

Which you've basically seen before， modular of these minor cosmetic differences。All right。

 so why did I write this down Okay so we're trying to prove a positive result。

 We're trying to prove that this algorithm did something good that it got close to optimum。

 And remember when you're trying to prove these kinds of things， the challenge is always。

 how do you know when you're close to optimum So last lecture。

 we just had a couple ad hoc arguments for online scheduling for online Stener tree。

 But we figured out how to do it But also if you think about it。

 the whole culmination of the first half CSs261 was sort of the message that duality is sort of the ultimate answer of how do you know when you're done。

 how do you certify your own correctness。 And as we'll see in the rest of this course。

 it's also super useful for proving approximate correctness。

 So this will be our first sort of nice example of that today's lecture。

So I'm running down the primal dual pair because I'm going to show the way I'm going to prove that the matching that the greedy algorithm outputs is good is I'm going to compare it to a dual feasible solution and remember dual feasible solutions by definition。

 by construction of the dual are bounds on what the optimal solution that the primal could be。

And so maybe that， you know， maybe that sounds kind of fancy。 But actually， you know。

 exhibiting the duall is very simple for this claim。So here's what we do。Again， remember。

 we've run the greedy algorithm to completion and we're doing this sort of in hindsight analysis。So。

Now what I'm going to do is I'm going to show you， okay。

 it's not quite a dual feasible solution but it's on the right track。

So for every vertex of the graph。Set Qv to be equal to one half。If。V matched by greedy。And equal to0。

Otherwise。So again we ran greedy。It didn't necessarily output a perfect matching。

 might have output something worse than a perfect matching。

 but so after the fact we sort of scan through the veres and say， well， whatever's match。

 give it a Q value of1 half， whatever's unmatched， a Q value of0 or if you want。

 you can think about it like we actually define this dual in tandem with running the online algorithm so a new vertex shows up if the greedy algorithm matches the new vertex on some edge at that point we set the Q values of both endpoints to be one half。

That's another way to think about it。Okay。So what can we say about these cues。

So call the greedy matching M。So the first thing to notice is that。The sum of the Q values。Is what。

In terms of M。It's the cardinality event。We're sort of imagine defining the dual in tandem with the algorithm。

 every time the algorithm adds an edge， we set the Q values to the two endpoints to a half。

So at all times， including at the end of the algorithm。

 the sum of the Q values equals the sum of the edges that are in the matching。

We're using the fact that， you know， in that I mean， because it's a matching。

 no one's ever going to have their Q value set twice。

 you either just stay at zero forevermore or you're set to one half exactly once when you're matched by the greedy algorithm。

Okay。So but here's the more important point。Now I'm not going to claim that the Qes form a dual feasible solution。

 remember， this is the dual here， So dual feasible means that some of the prices on the endpoints of an edge should be at least one。

So I'm not going to claim that the cues form a dual feasible solution， but if we double the cues。

 I claim that's a dual feasible solution。So I claim P。

 the vector defined by just doubling all the Q values is feasible。For D。So again。

 feasibility just means that if you look at any given edge of the graph。

 the sum of the P values of the two endpoint should be at least one。So really。

 all this is saying is that for every edge， at least one of the two endpoints got a Q value of1 at least one had a Q value of 1 half once we double the sum of the P values of this edge is at least one。

Okay。So for all VW in the edge she。It's going to be true that QV plus QW。Is at least one half。

And therefore， once we double， it's at least one。So why is that true， well， how could it be that？

Both V and W， both QV and QW are 0。 What would that mean？That would mean。

The only way at zero is if he didn't get matched。So that would mean both V and W didn't get matched。

But then what on earth we doing when the vertex W showed up？Right。

So how could we not have matched W if V was available， its neighbor V was available at that time。

 okay。So another way of thinking about it is the greedy solution outputs a maximal matching。

 so there's no way you're going to have two points connected by an edge， both of which are unmatched。

So we'ret okay of that？So now we're done。So now we can use。

 so remember the dual always bounds the best possible solution of the primal。

 so our primal is a maximization problem， so every dual is going to be an upper bound on how big the max matching could possibly be。

 so we're going to use this dual feasible solution to compare against our matching。

so just copying this down。So rewriting this in terms of half the P's。

This is the objective function value of our dual feasible solution。呃， yeah。

Which is an upper bound on how big optt could be。Okay。And that's the proof of the claim。

 This is the size of the matching output。 But by greedy， we proved it's at least。

Half of the best possible。 So it's a one half competitive ratio。So any questions about that？

This idea we'll see a few more times where you have an algorithm。 It's not to notice。

 We didn't solve a linear program in our algorithm。 Our algorithm is just the greedy algorithm。

 We use linear program to analyze it to prove that it's approximately optimal。

 We'll see that several more times where we're looking at natural heuristics， natural algorithms。

 We want to know how do we prove the near optimal。 We're going to use a suitably constructed dual solution。

 okay。All right， so any questions about that？Make sense。Okay。All right。

 so that was the answer to the first question。 Could we actually get one half say with a deterministic algorithm。

 The answer is yes， So can we do better with randomization。So。

I'm actually not going to answer that question for you in lecture。

So rather than thinking about randomized algorithms for integral matchings。

I'm going to think about deterministic online algorithms for fractional matchings so remember in a matching。

 you have to pick an edge， every vertex should have a most one edge picked incident to it。

 but then you can also talk about fractional matchings where you can have fractions on edges between0 and1 so in some sense feasible solutions that are not  zero1 to this primal or correspond to fractional matchings。

Okay， so but let me tell you that on problems at number four。

 So it turns out that the same ideas I'll teach you in this lecture also lead to the same improvement for the integer matching case with a randomized algorithm again problems that number four we'll walk you through the steps to translate the analysis I'll show you today to the the randomized algorithm for the integral problem。

Okay。All right， so I guess one just one quick thing to remember。And in fact。

 I first my them is weird actually， to talk about the fractional biparttheite matching problem instead of the integral one。

 because wasn't one of the points a few lectures ago that the problems are the same。So this。

 I don't know if you remember， but when we were talking about LP duality。

 one of our examples is we went back to the Hungarian algorithm and we use the Hungarian algorithm to prove that actually there's always a primal solution。

 which is amongst all fractional solution to the primal there's an optimal one。

 which is 01 corresponding to a perfect matching。 How do we prove it because the algorithm exhibited an integral matching。

 but it also exhibited a dual with exactly the same objective function value。

 So that shows that there's always a zero1 optimal solution。 Also on exercise set， I think number5。

 I ask you to prove it directly， So for biparttheite matching， there's always an optimal solution。

 which is 01。😊，So。Allowing fractions does not help you solve the problem if you're solving it optimally。

However。Allowing fractions can help online algorithms。So why is that， Well。

 let's return to our same example。Right， so we have two vertices up front on the left。

 A new vertex comes on the right connected to both。 So before we had to pick。

Either we match it to the top vertex or we match it to the second vertex。With fractions。

 we don't have to pick， we can hedge。So in light of this example。

 it's tempting if our algorithm is allowed to use fractions to match this edge 50，50 to each one。

Okay。That's something this algorithm could do that the previous one could not。And then。

An adversary can come along and say， oh， well， this one's only connected here。

But then there's still one half room here for us to at least partially match this vertex。

So at this point， the fractional online matching algorithm can assign a one half。To that protects。

Okay。So opt is still too， and we're still not as good as opt。But we got three2s。

 so that's only a ratio of three/ quarters， so it's not one half。So at least in this example。

 we're not stuck with the one half if we can have fractions，All right， so any questions about that。

 So that's why it really is a different problem when you start talking about fractional matching。

Just to kind of foreshadow what you'll see on problem set number four。

 notice that you know if you had to be integral， but you were allowed to randomize。

 there's a sort of obvious analog to splitting one unit fractionally on these two edges。

 which is to flip a coin and pick one of the two edges at random so building on that kind of idea allows you to translate solutions for the fractional problem like you'll see today to randomized algorithms for the integer problem。

Okay。So questions？Yep。For。Arbitrary fractional matching， How do we know that it was actually？

Amentable as a。ureSo' we're actually not going to insist that。 Yeah， so I mean。

 and as far as translating it to a random translating it to a randomized algorithm， it's not obvious。

 It's not obvious you can do it。 I'm just sort of giving you some high level intuition about why it's conceivable is's possible。

 But you're right。 The question is， I mean， so I mean， it's an excellent question。

 you're basically saying， So what you'd like to do is kind of realize all the fractions as probabilities over some distribution over matchings。

 And so in some sense， that's true。 I mean， in some sense， we know after the fact， again。

 just by knowing that this thing has01 optimal solutions。

 that kind of tells us that any fractional matching is indeed the convex combination of integer matchings。

But the question is， can you sort of construct that distribution online。

 So you need an online algorithm， which actually at the end of the day。

 has constructed the correct distribution。 And that's it's not trivial。 So， again， you know。

 the problem as usual， we broken down into a few steps so that you can see how it goes。 But it is。

 I mean， it you know， So last year actually didn't lecture。

 but I just decided it was too much on the topic。 It took another like， know。

 maybe 20 minutes to do to do the randomized translation。Other questions。All right。

 so let me tell you the algorithm we're going to use。

 and the algorithm we're going to use is really just sort of the natural extension of hedging， okay。

And， let me put this over here。And。I'm going to call it， sometimes it's just called the water level。

Algorithm， because there's sort of a nice physical interpretation。Of what's going on。

So the idea is you think of the left hand side vertices that are up front。

As containers for water initially empty。With capacity one。

And each arriving right hand side vertex is a source of one unit of water。

And what's interesting is what happens。When a new vertex shows up。

So when the next right hand side vertex comes。Let's call it oh yeah， W。

You want to try to send W's water over to the left hand side to its neighbors， okay。

 that's the analog of matching it fractionally。So you fill up。The neighbors。

 the neighboring containers。Always preferring the containers that are currently the least full。

With the lowest levels。So preferring。The lowest levels。

So you want to think about a picture like this， right。Suppose we look at the neighbors of W。Okay。

 so w is the new vertex on the right hand side， it's connected to various vertices on the left hand side。

So each column here represents the current water levels and how much water a given neighbor already is holding。

And so they can certainly have different water levels。Maybe something like this。

 so this is a case of a vertex with six neighbors all filled up to different degrees。

All of this is less than one。So now W shows up， and it has this one unit of water it wants to get rid of。

 So at first。RightSo so you can see why it's called what it is now。

 you just sort of imagine pouring a picture of water into this picture and letting stuff fill up。

So first it goes to sort of the lowest point。Now there's a tie。

 so after it's sent this much water to the second neighbor。

 there's a tie of the level between the second and fifth neighbors。

 so you just split the water equally amongst them。Now there's a three way tie between the second。

 third and fifth for which one's the lowest， so you send further water equally between them。

And then maybe it runs out here。Maybe at that point， it's actually。

Gotten rid of its full unit of water， at which case we stop。Okay。

 the other possibility is that it fills up all of his neighbors to the top while still having water left。

 in which case we also stop。Okay。So。Ands when one of two things happens。So in either one。

All neighbor is full。Or two。W becomes empty， i。e has no water remaining。

And if you think about a very simple。Example。What we did with this 50。

50 split was exactly the water level algorithm， right， So this node showed up。 They both had level 0。

 So it sent its flow equally。 It's water equally to the two。

This one showed up and then just sort of got rid of what it could。So when the first vertex arrived。

 we terminated because of the second case， because of the vertex got rid of all of its water。

 when the second vertex arrived， we terminated because the first case was triggered。

 all of its neighbors were full。Okay。Good。So any questions about that。

 So this is the algorithm we're going to be thinking about for the rest of the lecture。It's clear。

 I mean， I've described it somewhat informally。 So if it's unclear， let me know。

I tried to describe it at what I thought was sort of the optimal level of abstraction。

 but you never know。Okay， so before I era this just a reminder for those of you that came in late。

 my office hours today are one later， one hour later than usual， okay。

 four to five instead of three to four， that's today only。是么。O。

So I hope this picture is sort of easy enough to sort of remember and store in your brain。

 but let me actually just sort of point out what's going to be the main property of this algorithm that we're going to use in the analysis so just it's going to turn out that this algorithm does indeed beat one half。

 it's better than one half by noticeable amount， but it's not super easy to prove that okay。

So an important point in the analysis。Is the following？

So a key property of the water level algorithm。Is if you look at any edge。So again。

 think about in hindsight after all of the vertices have showed up。So， for any edge。So at YV。

BV's final water level。Okay， so X E I'm using in the same sense as in our primal。

 this is the extent to which one vertex is matched to another， possibly fractionally。

You know fractionally matching one a vertex on the right to a vertex on the left is like sending that much amount of water。

 So if we sum over all of the neighbors， okay so this is on the left hand side。

 this is one of the containers we're summing over all of its neighbors on the right hand side that might be sending water to it。

 If we look at the total water scent that's going to be the water level at the end of the algorithm of the vertex V。

So consider any edge， let YV denote the final level， water level of the container V。

And then what's the assertion？So then if you look at the source of water， W on the right hand side。

Okay。It only ever since。Water to containers。That had the current level， current water level。

Of something at most。Wice sub V。Okay。So let me it's actually very simple once you can parse it。

 let me just sort of walk you through a little bit。So first of all。

 you want to think so Y V could be as high as one。 If y V is one， this is a trivial statement。

 It just says that W only sent water to containers with the final level at most one。

 but that's sort of trivial because the level can't go bigger than one。

So you want to think about Y V being strictly less than one to be the non trivial case。

 So that means there is this container。So this would be。Like the vertex in the upper left。

 and that example。So it's a container which was not totally full at the end of the algorithm。

 it was only full up to y sub V， so maybe it was four fits full at the end of the algorithm。

And so the claim is that then know， if you look at this vertex W that's connected to V。

 it only senses stuff when their neighbor was4 fifth or possibly less。So why is that true， Well。

 think about it this way， right， So W shows up， it starts distributing its water， right， So it stops。

With everything it's sending water to at some common level， So remember in this picture。

 at all times， you're sending water to a bunch of containers that have exactly the same water level。

So when you get rid of all your water， there's going to be some common level， like4 fifths， say。

 of all of those containers that you were sending water to Everyone else who you weren't sending it to has an only higher level。

 Okay so up till then， you've only sent it to level 45s or less。

 And everybody's level at that point in the algorithm is4 fifths or more。

Fast forward the end of the algorithm， water levels can only go up。

 So this only becomes more true if there's more vertices that show up after W。Okay。

So a different way of putting it is think about the common level of everything you're sending water to at the time the W exhausts its unit of water。

 the final levels of all of the things it's connected to can only be higher than that common amount at the end of the algorithm because levels only go up。

So any questions about that？So this is really the。Almost the only property of the water level algorithm we're ever going to need。

so if you want， you can actually forget about the algorithm and just remember this property。

 though it may be easier to remember the algorithm and remember the property。O。Good。

So how are we going to analyze this？Well， back when we had our sort of determinant greedy algorithm。

 we used this dual analysis。 now we're pretty well。 It's pretty easy to apply。

 and it gave us the correct answer， gave us the tight down of one half。

 So it's natural to try to copy that same dual approach for this new water level algorithm。

So the only difference is that now you know instead of picking one edge at a time。

 we're sort of gradually increasing the fraction on edges at a time。

 but we can try to do the same thing right so before when we picked an edge we set eachq value of each endpoint to one2 now when we increase the extent that some edges matched by delta。

 we can again just sort of associate delta over2 to each of the two endpoints。So idea number one。

When some edge XVW。Is increased by deelta。Increase both QV and QW。By Delta over2。Okay。

So just like before， by construction inductively at all times， we will maintain the property。

But the value of the fractional matching。That's being constructed by the water level algorithm is just the sum of the Q values。

Okay。Whenever the left hand side goes up by Delta， we make sure that the right hand side goes up by Delta as well。

 Delta evenly split between the two endpoints of the edge。So that's good。

 So that's one of the two properties we use in our one half analysis， the other property。

 if you think about it， back in our argument where we set things to either one half or0， we said。

 okay， well， Q isn't dual feasible， but if we double Q， that gives us a dual feasible P。

So to get a bound better than one half， what we're hoping is that we can scale up the cues by some factor less than two。

That will give us a competitive ratio bigger than one2 by exactly the same argument。

So the whole question is we have these cues， how much do we have to scale up to recover dual feasibility。

 remember what dual feasibility means， dual feasibility means that sum of the prices at the endpoint is at least one。

So what we're hoping。Okay。Is that for some C greater than1 half？We can prove。That1 over c times Q。

So previously C was a half and we were doubling， now we're hoping C's bigger than a half in this case this is scaling up by something less than two。

Feaible。For the duel。If this is true。Then by exactly the same argument that's still up here on this board。

 so if we can prove that Qv plus QW is at least some C。

 then we just multiply by1 over C and we get a C competitive。

Alrim instead set of a one half competitive algorithm。Okay。

So I think that's that's the first thing to try。 So you have this new algorithm。

 The motivation for the algorithm is this idea of using fractions to hedge。

 This seems like a natural way to hedge。And so then the question is how to analyze it。

 and it's natural to just copy what worked before， what worked before。

 whenever you sort of add something that they're matching。

 you split it amongst the Q values of the endpoints and then you scale it up to get a dual feasible solution。

All right。So you probably guessed when I wrote down idea number one。

Suggesting that there's an idea number two。This isn't going to cut it by itself。

So let me show you why。Here's a bad example。So suppose we start with four vertices on the left。Okay。

So it's sort of an extension of our previous bad example。

So the first vertex on the right hand side shows up， say it's connected to everybody。

So what does the algorithm do？The water level algorithm， what does it do？Good。

 those each to one fourth。So it increases。So basically it splits its one unit of water equally between all of the eligible containers。

 right they all had level zero， so you just keep them all the same。

Suppose the second vertex shows up。And is connected just to the second， third， and fourth containers。

Okay。So in this iteration， are we going to trigger case one or case two？2。Good。

So this is similar to the previous iteration， there's three containers it's going to split。

 all of these have the same initial level of one fourth。And so they're all tied for the lowest level。

 so it's going to split equally among the three， and it's going to distribute it to one unit of water。

 one third， one third， one third。Let me use a different color for this。So one third on that one。

One third on this one。And one third on this one。So you can guess what happens or what the graph looks like next。

 so the third vertex on the right is connected to the third and the fourth vertices。So now。

Are we going to trigger case one or case two？解错了。Case one， excellent。Why， well。

 because this container， what's its current level， one third plus a fourth。

 so it's more than a half at712s。This one's also at 7/12s， so each of those has512ths remaining。

 so this new vertex will distribute equally amongst them until they both get saturated and it'll get rid of five6s out of its one unit of water。

Good。So one half， one half。And now just add insult injury。

The last vertex is going to be connected only to the fourth vertex。

 the fourth vertex is already full。So nothing is going to happen on this last iteration。Okay。

 we just get a big fat zero right there。So let me ask you。What's the final Q value of that vertex？

我儿都是 one。Oh， sorry， yeah， this should be 512。 you're absolutely right。Absolutely right。

Sorry about that。And then where's the other one？And this one， yeah。感 you。Good。

 so what's the final Q value of the southwest vertex？One half， good。It's full。

Which means there was sort of one unit of time overall that it was participating in increases。

 and it always got half of its share of that increase。 Okay， so remember。

 when we increase on an edge， it gets split equally between the two endpoints。So how about this one。

 what's going to be the final Q value here？你就说。This is going to be zero。

Because no edge incident to it ever got increased， so it's not going to get anything。

So unfortunately， what we now see is that with this analysis approach。We would still need to scale。

By two。To get dual feasibility。Okay。Remember dual feasibility says the sum on the two endpoints should be at least one。

 so to figure out what we need to scale by， we asked the question okay。

 how small could the sum of the Q values be on a given endpoint。

 and then we'd have to scale by the reciprocal of that。

 This shows that the sum of the Q values might be only one half in the current scheme So have to scale up by two。

So that's the bad news。 The good news is。So this is a bad example for our particular analysis。Okay。

 so for our approach。Of。On this board。 So it's a bad example。

 It's a bad example for idea DN number one， but it's not actually a very bad example for the water level algorithm。

 It's not optimal here， but it's not actually doing all that badly， either。

So value of the water level solution。Okay， well， this one's fully matched， this one's fully matched。

 this one's matched up to five，6s。And this one's not matched at all。Whereas optt is four。

But this is a lot bigger than two， right This is close to three。

So the ratio in this example is certainly bounded away from one half。Point being。

 it still opens the door that the water level algorithm is actually a good algorithm。

 and we just haven't been smarter enough yet to prove it。 So。 Okay。

 well so all we know is we need one more idea if， in fact。

 we're going to prove a better bound for this algorithm。 But again， if we。

 if we believe in the algorithm， we should just keep the algorithm fixed and ask。

 how can we be smarter just in the analysis， okay。So any questions so far？All right。

So idea number two。So now you know， if we're feeling kind of lazy or uninspired。

 we might ask ourselves， okay， what's like the minimal change we can make to the last idea so that it's not obviously broken。

 okay？And you， there's not a unique answer to that。

 but what's1 thing is to keep the algorithm the same。

To keep the approach of using a dual feasible solution the same。And to keep this sort of goal。

 you of trying to sort of construct these Q values so that scaling you know hopefully gets us dual feasibility。

 and the one thing which is tempting to change is that we were doing an equal split always between the two endpoints of an inch。

So idea number two is were when we increase。The extent to which an edge is matched。

 we're still going to split that delta between the endpoints， but not necessarily 50，50。Okay。

So on equal split。Between QV and QW。And for motivation， just think about our bad example， all right？

So remember the algorithm is fixed， okay so we're not thinking about the algorithm is going to keep doing the same thing on the same example。

 The only thing we're thinking about modifying is who gets what Q value。And notice。

 you here on the right hand side， know this southeast vertex。

 it never participates in any edge getting increased at all。

So unless we do something really crazy on anatural。

 that southeastern vertex is going to get a Q value of0 because all of the edges around it are zero。

So if we're going to have， if we're going to beat one half using this kind of approach。

 we need to make it so that the southwest vertex at the end of the day winds up with a Q value bigger than a half。

Okay。That's what's going to need to happen to be to half。 Okay， it's not clear it's possible。

 but if it's possible， it's by making sure that that southwestern vertex。

Has a final Q value bigger than a half？And that's that obviously with equal split。

 we're stuck with a half because you only get filled up to one。

 so you're not going to get more than a half with equal split。

 so evidently we need to at least sometimes more aggressively give it to one of the two endpoints of a vertex okay。

And the way we're going to do it。Is。We're going to be more aggressive with how much of the split you get as you get more and more full。

So as a vertex on the left hand side gets more full。Increase its Q value。Faster。Okay。

So when a vertex on the left hand side is empty， at the end of the day。

 we'll see that it actually gets less than a 5050 share。 but by the time it's like totally full。

 it's getting basically 100% of the share。 that's what's going to happen。

And again what's the motivation， the motivation is because we want it in this case that you get filled up on the left hand side。

 even if you have these vertices on the right hand side， which  Q values0。

 you still are better than a factor of too close to dual feasibility。So that's the idea。Now。

It's a pretty vague idea。At equal split， at least we knew what we were talking about， 50，50。

 unequal split， that could be anything。So how do we pick？Moreover， this idea suggests that actually。

 we're not just going to pick some fixed split。 It's not like we're going to change 50，50 to 70，30。

 it's easy to convince yourself that doesn't work。 So we actually need the split to change as a function of how full the vertices on the left- hand side are as a function of their current water level。

And it's very hard to know how you should， you know， define this split。

 like what's going to lead to a good algorithm， if anything。

So the approach we're going to do is we're just going to sort of do a generic analysis of the water level algorithm parameterized by the way in which we're splitting a primal increase amongst these Q values。

So for the moment， we're just going to fix a function for discussion。From 01 to 01。

Which should be non decreasing。Okay。So what's the interpretation？Of G。

So I'm going to erase the primal dual pair， but the one thing to remember from the primal dual pair is just the dual feasibility。

 the dual feasibility requires the sum of the prices on the two endpoints is at least one for every edge。

 This is the thing to remember。Okay， so G is going to be our splitting function。

 and it's going to specify what fraction。Of a delta increase goes to each of the two endpoints and it's going to depend on how full the left endpoint is。

So when increasing。The fraction on some edge。By some infinitesimal amount， Dz。

And with the current water level， YV。member， this is just。

The sum of the fractions on the incident edges。Okay so getting more full just means your YV is closer to one。

The plan is to increase QV。Bye。G evaluated at the current water level， DZ。

So this is non decreasingasing or increasing， so that is reflecting the point that as a vertex on the left gets more and more full。

 closer and closer to one， we're going to aggressively give it more and more of the split。

 That's what G non decreasingreing means。And then we want to give the balance to the right hand side note。

Okay， so GW goes up。By1 minus。G ofYV DZ。O。So for example。If you really wanted。

 you could set G to be the constant function0。That's going to result in only the vertices on the right hand side。

 getting positive Q values， everything will go to the right hand side。If you wanted。

 you can say g equal to 1。That'll give you all the Q values on the left hand side。

If you said G to be the constant function1 half， that saying always do an equal split。

 So that corresponded to what we were doing before， setting G to be the constant function1。Okay。

All right， so here's where we stand。 So you should be clear on the algorithm。

 The algorithm hasn't changed water level。 We're trying to be smarter about analyzing it。

 How are we trying to be smarter by allowing sort of varying splits。

We parameterizing that by a function， you should agree that for any choice of G。

We get well defined well defined set of Q values at the end of the algorithm。Remember。

 the goal is to get for every edge VW， QV plus QW to be as large as possible。

 we need at least one p feasibility， so we want to get as close to one as possible before scaling up。

And what should not at all be clear is how to think about G and like what G might be a good G？

So we're just going to do a generic analysis and then solve for the best G。But that's the approach。

 and so this is the last idea we need。 so it turns out if we choose G in just so。

 we're going to be able to prove a better than one half bound for water level。Actually。

 an optimal bound for water level。Let me just point out that again， by construction。

The value of the water level solution。Is again， equal to the sum of the Q values。

 Okay so just by construction， we maintain this inductively at all times。

 whenever we increase the value of the fractional matching。

 we increase the some of the Q values by the same amount。

So the whole trick is to understand how to pick G so that for every edge。

 the sum of the cus is as close to one as possible。Is everyone clear on where we are？

So G denotes our splitting schedule， you want to solve for the best G。

 what does the best G mean means the sum of the Q values on the endpoints of every edge is big。

 big means close to one。In particular， we want to be bigger than a half。

Because let we scale by less than two， and we get a better than one half competitive ratio。Questions。

All right， so analysis。And again， this is going to be sort of generic with respect to the choice of the function G。

And then once we do our analysis， we'll get some guidance about what G is going to give us a good competitive ratio。

All right， so fix an edge。And again， remember all of this is in hindsight。

 so the whole graph has showed up， okay so we know the whole graph it's just in the analysis。

Fix an edge that showed up。What we want to do is we want a lower bound。So goal， lower bound。

 QV plus QW， this is what we want to be close to one， certainly bigger than a half。Okay。

So we're going to look at two cases。The two cases correspond to the two ways in which this processing of a new vertex can end okay。

 so remember a vertex shows up on the right hand side， one of two things can happen。

 either it successfully distributes its entire unit of flow that is it's fully fractionally matched or the only way it can fail to distribute everything is if all of its neighbors are totally full。

 that is all of its neighbors are themselves fully matched。So those are the two possibilities。

 Let's start with a possibility。That this vertex on the left is full。

At the end of the water level execution。And again， full just means that the water level YV。

Defined like it is up there。Its equal to one。So we want to lower bound some of the Q values of the endpoints。

Well， I erased it， but you can still sort of see here。An issue is that for all we know QW is zero。

 okay？So this could be。Could be zero。So we kind of want our analysis to work。

 So we're going to do a very crude approximation here。 We want to lower bound to sum of the Q values。

 But for all know Qw0。 So let's just lower bound。The left hand side Q value。And actually。

 this is very easy to write down。As a function of our choice of G。Okay。V， by assumption。

 V is totally full at the end of the algorithm。 so it's totally filled up。G specifies。

As a function of how full it is at a given time。What share its getting of the current increase。 Okay。

 so think about it from these perspective， right， First， it gets filled up to a fifth。

 then it gets filled up to2 fifth， and it gets filled up to4/7。 You know， this happens in stages。

 but it's all kind of continuous。 So it gradually。 It level gradually goes from 0 to1 in a continuous way。

And in any given level， y G of y is the instantaneous fraction of the increase that it's getting at any given time。

So integrated over the course of the whole algorithm over the whole lifetime。

What is the Q value going to be？Well， we just integrate over all of the water levels that this vertex ever has。

 and again it goes gradually from  zero to 1。And so that's going to be。DZ。

And at a given current level， Dz。G is the by definition is its。Split of the current increase。Okay。

 so this is just by the definition here。So for example。

 when G is the constant function12 like we had before。

 we're going to find out that when a lefthand side vertex is full， it has a Q value of12。

 which indeed is exactly what happened previously in general。

 what's its final Q value if it's full was the integral of G over all of its water levels between0 and1。

So any questions about that？So again you have no sense for whether that's a bigger or small number。

 It's obviously going to depend on G， right， So remember， we want that to be big。

 We're trying to lower bound。 We want this to be close to one。 So the bigger G is the better。

 but that number will be bigger or small， depending on whether G is bigger or small。

But you agree with this inequality， in particular， did you agree with this equation？

And it's kind of by definition of our analysis approach。Any questions about that？Okay。So again。

 just for a given choice of G。This is just going to be the number you see on every left hand side vertex。

 which is full。 It used to be a half。 Now we're hoping it' would be bigger than a half。All right。

 but this isn't the only case。If this was the only case we'd be done because we could just set G to be the constant function 1。

 we'd have a great lower bound。 It would be at least one way bigger than one half。

But this isn't the only case。Case 2。Is that at termination， V is not full。哎 right。Obviously。

 that's the other case。Now， notice if this left hand side vertex V is not full。

 if it has space remaining。It must be that its neighbor on the right hand side。

 W got rid of its full unit of flow。Why， well， if W still had flow left and V still had room。

 the water level would have sent more water on that edge。Okay， so again。

 it's sort of a maximality property of the water level algorithm。So if V is not full。Then W is。

W is empty。So W sense。All itss water。Okay。All right。Good。

So what we're going to do here is we're going to give an estimate a lower bound on W's Q value。

 Okay so in our bad example， the reason we had a bad Q value on the right hand side is because the vertex wasn't matched anything。

 So now we're thinking about a vertex W on the right hand side， which is fully matched。

 So it'd better have a nontrial Q value。Okay。All right。So here's where we use the key property。

It's the key property here。SoRemember what the key property says。

 the key property says consider a vertex on the right hand side。

Consider any of his neighbors on the left hand side。

 suppose the final level of that water level of some neighbor on the left hand side was know why。

 then whenever W was sending water to anybody， it was sending it to a container that was carrying y or less units of water。

So in other words， the final level of any neighbor of W is an upper bound on the level at which any container was when it was injecting flow to it。

So we're going to use that property now to give a lower bound on QW。So what's the lower bound？

All right， so。Here's what it's going to be。Okay。Since。So remember G we picked to be non decreasing。

 So the more full something on the left hand side is the more bigger split you get。

 So 1 minus G is non increasing。And so therefore。What does that mean？Well。

 whenever W was sending any of its water， remember it was sending it to something。

With current level at most， the final level of any of its neighbors in particular of Y sub V。So Ws。

Share a split。Was at least one minus G。Of Y subv。Okay。So this is by the key property。So again。

 just to recap， we fix some edge v comma W。 we're looking at the case where v is not full and W got rid of everything。

 we're trying to say lower bound the Q value of this full vertex W on the right hand side。

So how do we do that， Well， we have this key property， which says， well， look。

 supposeose on this edge that we're looking at， the container on the left ended up only 80% full。

The key property says that whenever。The vertex W was sending flow to anybody。

 was to someone who was at most 80% full。We're trying to lower bound the Q value that W gets。

 so the worst case for this lower bound is that whenever it sent flow to anybody。

 the level was as high as it could have been 80% so that's all this is said so this is 0。

8 so if it's 80% this is the share of the increase that goes to the lefthand side vertices。

 W gets the balance。Okay。So again， we're using that whenever it sent anything。

 it sent it to a level that was at most wise sub V， and then we're using the G is non decreasing。

1 minus G is non increasing。Okay。So that gives us the lower bound。re any questions about that point？

That's really where the algorithm and analysis come together the most tightly。是。Okay。

 if you believe this， we're basically home free。O。All right， so what does this mean？

So what's the accumulated total， the final Q value of this vertex on the right hand side？Well， again。

 remember a wine's up full。Right so this is case2。 V is empty。 that can only happen if W is full。

 so we can again integrate over its entire lifetime， all the levels it ever took on between0 and1。

And we know that at any given time in its lifetime， it was getting at least a split。

Of1 minus g of y v， where again， V here is just some neighbor on the left， Y V is its final level。Dy。

 sorry。Okay。This is a very easy integral。The ingr does not depend on the integrating variable。

So this is just one minus g of y sub V。Okay。And so that means。In case two。So summarizing。In case2。

QV plus keyw。Well， first is the contribution from QV QV。 So this remember in case one， this was one。

 now it's going to be less than one。But we can still integrate。From zero to the final water level。

A V。Of its share of the split。So this is the contribution， this is exactly Q sub V。

And then we have our lower bound on Q sub W。Okay。So。Let's call this number two。

And this thing up here number one。Okay。So again， just to make sure you don't lose the forest for the trees。

 what are we trying to do， we're trying to prove that these Q values are pretty close to being dual feasible。

 What does that mean， It means that sum of the Q values on each end on the endpoints of any edge should be pretty big。

 close to one。So quantity 1 is a lower bound on the sum of the Q values of the endpoints of an edge in the case where the left hand side vertex was full。

Okay， yeah， left hand side vertex was full。 So this is a lower bound on the sum of the Q values in one of the cases。

That is a lower bound on the sum of the Q values in the other case。

Where the left hand side container is not full and the right hand side container did got rid of all of its water。

So what do we want to do， so again， G is still a free parameter。

 so we want to choose G so that both one and2 are big as close to one as possible。Okay again。

 we want to say that some of the Q values of the endpoints of every edge is high。

 some of our edges will fall into case1， some of our edges will fall into case2。

 so we need to make both the expressions one and two large simultaneously。

 If all we wanted to do was make one large wed just choose G to be the constant function one。

If all we wanted to do was to make too large， we'd just choose the constant function G equals 0。

 So the tricky part of the analysis is balancing this perfectly。

 getting both of these numbers to be big simultaneously。

Notice that if we choose G to be1 half like we were doing before。

 we would at least prove that one is at least a half。And the two is at least a half。

But wed like to do better because so we want to get better than a half for both with a suitable choice of G。

Okay。So questions about that？All that's left is to solve for the best G。

 which actually isn't as hard as it sounds， it's not that bad。Okay。All right， so to do。

To do solve4 G。To maximize。Remember， we want to get these numbers as close to one as possible to maximize the minimum。

Of one and2。And let me also point out that when I say two actually2 is a whole bunch of different things because there's a free parameter or y sub v on the right hand side。

 remember y sub v is just however full the left-hand side vertex wound up at the end of the algorithm。

 somewhere between 0 and1 we have no control over what So really I mean we want to maximize the minimum of1 and 2。

 even for a worstcase choice of y v and01。Okay。So for all Y sub V。And zero one。O。

So this may sound kind of intimidating， right because you have this free parameter G G is a function right from the interval to the interval。

 There's a lot of functions from the interval to the interval。 So how do you know which one to use。

Well， one kind of non rigorous， but useful guiding principle is that you know。

 in in optimal algorithms， especially which this one is， as we'll discuss。

They often have the property that kind of， you know your loss is perfectly spread。

 your errors are just perfectly balanced across all possible cases。

 there's no slack in the error in any case。So if you think that's going to be true here。

What it suggests is saying， well， let's see if we can find a function G。So that one。Equals2。

And actually one equals two， no matter how we choose the free parameter y sub V and0 comma 1。

So again， think of one as sort of one condition， think of two as actually an infinite number of conditions。

 one for each choice of y sub v in0 comma 1。Okay。So the trick or the idea， and again。

 this is often super helpful in analysis is try to equalize all of the different cases。

So that is in particular。Maybe we can make， maybe we should choose G so that that expression in2 is just a constant independent of the choice of y Z and 0。

1。Okay， so this is just going be a guess。But again， the season analyst often makes use of this guess。

So we're going to get look for the G that we really want。Two is a constant。Independent of Yv。

And equal to one。Okay。Now， first of all， it's not clear operator that there exists a G with these properties。

 there's no guarantee of that unless we actually try。Secondly， even if we do find such a G。

 it's not immediately obvious that that's going to be an optimal G。 Okay。

 so this is a guess and check approach。 Okay， We just need sort of a principled way to explore the space of G's。

 balancingcing error seems like a good principle。 and it's going to give us much simpler equations to solve。

All right， good， so。Assume that there is a G satisfying all these properties。

 We don't know if there is one， but assume there is one。

 What must it look like if G really does exist。Let's just focus on the aspect where we want two to be equal to a constant。

 no matter what y sub V is。Or put differently， if we think about expression 2。As a function。

Of Y sub V。It should be a constant function。That is it should have a derivative of zero。So， if so。

If we take the derivative of the expression 2。With respect to the variable y sub V。

That should be zero。Okay。So if there's a G that makes that constant for allYV。

 then of course we differentiate with respect to YV， we get zero。Okay。All right。Well， now actually。

 this is really not that hard to understand。So we're differentiating2 with respect to y sub V。

 so the derivative just cancels that integral。And then， of course。

 the one disappears and we get a G prime。Or if you prefer moving this over， G equals it derivative。

Now， it's been a long time since I took ordinary differential equations， a long time。Ironically。

 I think I took it in this very classroom。I don't remember almost anything。

 The one differential equation I remember is the one about a function being the same as this derivative。

So what's the solution？E to the x。So again， if， in fact。

 there's a function G which makes that a constant， then it's got to satisfy this。

 so it's got to be an exponential function。Okay。So Gy equals e to the y。Actually。

 if you think about it， there is one free parameter here。Which is。

 we're can have an arbitrary positive constant K in front。 And no matter what K is。

 it'll satisfy this， okay。So our first guess actually really narrowed down the space of Gs to look at right we used to have all functions。

 we used to have like an infinite dimensional free parameter now we just have one free parameter namely the coefficient K in front of E to the y。

Okay。Good。So how do we decide how to pick K？Well， so now we're going to use the part of the guess where I want to equalize one and two。

Okay。So， remember。We want both one and 2 to be big， one is big when G is big。

 if you stare at a little bit， you realize2 is big when G is small because when G is small。

 this part is big。So how do we balance those， How do we pick the optimal K that makes them exactly the same。

So let's plug in。Okay， so it's again， ks of free parameter， let's plug in this function G into one。

What have we got？It's a 01 k e to the y。You do the Z rather。DZ。Okay， so pull the k out in front。

 which is a constant。Interegral of e to z is e to the z， so 1 to the0 equals k of E minus1。Okay。

 so we just turned the crank， that's all we get。And again， notice that， you know。

 the bigger K is the better from the perspective of expression 1。 And again， we knew that。

 We knew the bigger G's were better for one。So how about two。So now we're integrating the same thing。

 but not from zero to 1， but from 0 only to y。But then we also have this one minus g of y。

So that translates to 1 minus k to the EY。So the same computation as before。

Tolds us that this equals k times e to the y minus1， no longer e -1， but e to the y -1。

And we see that this Ke to the y cancels with that K to the y。So we're left with。Let's see。pl。Yeah。

 something's fishy， yeah， that should be a plus， right？Yeah。So we're left with one。Minus k。Okay。

So notice this derivation is true no matter what y is， I chose y arbitrarily in 01。

 and I got a number1 minus k that was independent of y。

 but of course we knew that was going to happen。 We chose G exactly so that this quantity2 would be independent of y。

Okay。And as we see for this to be big， we want k to be small。

 and we already observed that that 2 is more prone to be big if G is small。

So now I just set these equal。So， setting one。Equal to 2。What do we get？So move the K over， blah。

 blah， blah。Should be1 over E。Okay。So I just equalize those two solve for k get1 over E。

 plugging back into G or function G。 remember G was k times e to the y。

So that gives this G of y is e to the y minus1。Okay。And again。

 so just thinking back about the original semantics of G。

 G specifies what fraction of the share does the left hand side vertex get as a function of how full it is。

 So when you have a vertex on the left hand side， which is totally empty。

 like at the beginning of the algorithm， that corresponds to y equals 0。And so G of 0 is 1 over e。

So at the beginning of the algorithm， when you first start raising， again， again。

 remember this's just in the analysis， our algorithm has stayed the same this whole time。

 but in our analysis。At the beginning of the algorithm。

 when we're increasing edges and we have these empty containers。

 we're actually doing an unequal split that favors the right hand side，1 over E on the left。

1-1 over E on the right。This is going to evolve as y goes from 0 to 1。

 This will become a more and more aggressive split in the left hand side vertex's favor。

And when y is all the way up to its maximum about1。Then this is actually going to be equal to1。 Okay。

 so 100% of the split is going to be going to the left hand side vertex at the time that it's getting totally full。

so this is interpolating between unequal splits favoring first， the right hand side。

 then the left hand side as a function of the fullness of the left hand side vertex。Okay。All right。

 and so now what is the magic number， so what is one and what is two？So one equals two equals。

1 minus1 over E。好的。This is roughly。63。2%。Though it is， it's noticeably better than one half。Okay。

And so remember， now we're done。 this was the whole， This was the whole game。

 The whole game was to define the Q values in a way that for every edge。

 the endpoints are guaranteed to be close to one y， because then we just take those Q values。

 we scale it up by the reciprocal of this。 So E over E -1， that gives us a dual feasible solution。

 which in turn is an upper bound on the maximum possible matching。

 So the water level algorithm outputs a fractional matching with at least this fraction of our upper bound on the optimum。

😊，So that completes the analysis。So two comments， so first of all， as I said。

 can really you can have a randomized algorithm for the integral case where basically the probability is sort of simulate what's going on with the fractions。

 and so you can again get a randomized algorithm for online bipartid matching with a 63。

2% competitive ratio problem at number four will walk you through on that。Now as far as you know。

 could we be even smarter， could we keep the algorithm the same and get a better competitive ratio or maybe we could have a smarter algorithm and get a better competitive ratio。

 well the last problem on problems at number three is actually a proof that no algorithm。

Necessarily randomized or otherwise can beat 63。2% for online biparttheid matching。

So the water level algorithm， actually， at least in the worst case。

 is the absolute optimal online algorithm for the problem。

Next week we'll start talking aboutmp complete problems， have a good weekend。

