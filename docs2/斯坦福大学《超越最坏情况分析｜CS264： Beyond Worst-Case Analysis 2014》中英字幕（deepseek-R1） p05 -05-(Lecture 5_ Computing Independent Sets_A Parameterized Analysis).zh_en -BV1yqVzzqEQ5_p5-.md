# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p05 -05-(Lecture 5_ Computing Independent Sets_A Parameterized Analysis).zh_en -BV1yqVzzqEQ5_p5-

So as far as what are we're doing today so we're going to have one more lecture which is focused squarely on parameterized analysis I'll remind you what that is in a second。

 so this will be the last lecture that's purely about it。

 but it'll be a recurring theme throughout the course as we'll see and so I want to talk about another case study today for another fundamental problem that of computing large independent sets in graphs and then time permitting we'll do a little toward dori of kind of parameterized analysis and the various parameters maybe you should know about that you'll see on the homework to some extent but otherwise I won't have enough time to really discuss in class。

Remember the point of parameterized analysis。 you really want to have some numerical measure of how easy or how difficult a particular input is and then ideally。

 you want to parameterize the performance of an algorithm in terms of this parameter in terms of theasiness of the input。

 So an algorithm is going to do better and better in some sense as the instances get easier and easier。

 We've seen some examples。 The first one was 2D maxima and lecture number two So then we actually saw multiple ways to parameterize the running time of Kirkpat Sll first N log n purely in terms of the input size N log H in terms of the input and output size。

 and then we had this complicated parameter， which was sort of necessary for the instance optimality result that we were shooting for。

 Last lecture we did a parameterized analysis of the LRU algorithm so there the inputs were page request sequences。

 We weren't thinking about running time。 We're thinking about the page fault rate was a different performance measure。

 it didn't matter。 parameterized analysis was still a good idea。

 We parameterized sequences in terms of the amount of locality and we showed that LR sort of improves with a。

And in fact， it improves faster than competitors like the FiIO algorithm。 And so today。

 we're going to see one more example。And there's a lot， let me just also review。

TheThe reasons that we're seeing about why this is a good idea。

 So the reasons why actually answer all three of the goals that I set forth for mathematical analyses of algorithms。

 So if you remember them， there was the explanation goal or equivalently。

 the prediction goal where you actually want sort of guarantees for algorithms you can interpret literally that are meaningful。

 Then even if you don't do that， you might want the comparison goal。

 So you want a good ordinal ranking。 So the relative performance of algorithms。

 you want to at least get right。 So you want good advice about what's an optimal algorithm。

 The third goal that we haven't talked about yet， but we'll start talking a little bit about today is the design goal。

 So having sort of a yardstick to measure algorithm performance naturally leads clever and creative people to design new algorithms that are better with respect to that yardst。

 and parameter analysis is useful for all of these reasons。So first， I mean， just， you know。

 if nothing else doing parameterized analysis， you just get more information。

 It's just a strictly stronger mathematical statement than general worst case analysis parameterized by the input。

 And just remember 2D maxima and log N。 it seemed like it was tight。

 But then when we looked a little closer。 we sort of zoomed in a little bit。

 we realized we could have a more finegra performance guarantee about the algorithm's performance。

 So that's the first reason。 So finegra information。 same deal with paging。 So it seemed like。

 know we didn't do parameter analysis， LRU and PIFO were the same。 again。

 we sort of zoomed in the microscope using this framework and we were able to distinguish the two。

 It was more informative and allowed us to differentiate things that we couldn't before。

 So that's progress on that comparison goal， comparing different algorithms that we couldn't make without it。

😊，Another reason to do it。Is it gives you advice about when to use an algorithm， by which I mean。

 on what types of inputs and what kinds of domains。 Okay， so imagine。

 imagine you're not really looking to build an algorithm from scratch。

 You just want to be an educated client of the algorithms that exist。 Okay。

 well then part of sort of what you'd like to be on the you know。

 instructions on the back of the algorithm， if you will。

 is advice about what kinds of inputs it's good for what kinds of inputs it's bad for。 Okay。

 and that's something parameter analysis can give to you。

 so whatever instant inputs are easy with respect to an algorithm。 That's where you want to use it。

 Okay so when to use an algorithm。And again， this is often in theoretical research。

 you know things aren't necessarily phrased this way。

 although you we did talk about the example about algorithms that are good for sparse graphs versus dense graphs。

 you see it sometimes， but in general， this isn't so much the emphasis in the theoretical guarantees。

 but it really is a big part of how practitioners think about algorithms。

 so that's another reason to do this。嗯。I mentioned briefly last time how it offers a two step approach。

Toward explaining。Why an algorithm， which is bad in the worst case， is actually good empirically。

 So the twostep approaches。 First of all， you do this parameterized analysis。

 so you identify easy inputs on which the algorithm performs well， much better than the worst case。

 And then secondly， you make some argument about why real inputs are easy。

 Maybe it's a parameter you can compute explicitly out on the standard benchmarks。

 Maybe you propose a generative model and you prove that with high probability on samples from that model。

 the instances are easy。 In fact that's exactly the philosophy of smooth analysis。

 When we get to that later in the course。So that sort of progress on the explanation goal。

And then again we haven't seen this yet， but this will be one of the points of this lecture is that indeed。

 once you have a novel way of parameterizing performance。

 you naturally the Pavlavian response of any theoretical computer scientist worth their salt is to start thinking about how can we do better than the state of the art and we'll see exactly an example of that today。

Okay。Allright， so these are some of just， you know， we'll do these concrete examples。

 But just big picture。 These are some of the things I want you to remember about， you know。

 the meaning of all this stuff。 What's the point。Okay。

 so any questions before we descend from these sort of lofty statements。

 And actually talk about a real problem， actual problem。Questions。No question。Okay。

So heres a problem I'll bet you've at least heard of at one point in your life。

 I'll certainly remind you what it is。We want to find the maximum weight independent set of a graph。

对。A well known MP hard problem。So the input is a graph and the weights are on the vertices。

 so the graph is undirected。And the weights are not negative。And we want to find the independent set。

 no prizes with the maximum weight。So what's an independent set， got to remind you that？

Independence said is a bunch of vertices。So that no pair of them are adjacent。 Okay。

 so no edge has both endpoint in this set。So if X Y are both in S。

 then it should be the case that the。Is there's not an edge between them？

Maximizing and by max the weight is just the sum of the weights of the vertices in the set。

So maximizing sum over V and S W sub V。So one sort of very canonical case of this is just the unweighted special case。

 that's where every weight of a vertex is one。So then you're just trying to basically pack in as many vertices as possible without。

嗯。You know， subject to being an independent set without capturing any edges。 So like in that。

 in that red graph there。What's the maximum size， maximum cardinality of independence set？2， anyone。

Anyone vote for a higher number？Yeah。Can I get to okay？So because， you know， it。

 it's pretty clear that the only way to get3 would be to have one in each layer， if you like。

 But if you take the last vertex it precludes picking both of the ones in the middle layer， okay。

So you can only get two of those vertices without capturing an edge as well。Okay。

 so that's the independent set problem。Any questions about that， definitions clear？Right。So you。

 when you first study NP completeness， you sort of learned that all NP complete problems are the same。

Well， yes and no， okay， they are sort of all the same with respect to you know whether or not they can be solved exactly in the worst case in polynomial time in that sense。

 yes， they're all the same future from almost any other angle。

 they start looking like a very diverse group of problems and one sense in which they're very diverse is to what extent they can be approximated in the worst case by heuristics by polynomial time algorithms。

And as NP complete problems go， independence sets a very。

 very hard problem even amongst N complete problems。So here's a fact， I'll tell you。

 I'll sort of write this in standard shorthand， I'll tell you what it means。

Basically what it says is you can't have any approximation algorithm that runs in polynomial time and gives you a nontri guarantee in the worst case。

 that's basically what it says okay。All right， so think of epsilon。

 epsilon here can be as small as you want， but think of it it say as 0。01 for concreteness。So。

By approximate the problem， what I mean is the following。

 So a C approximation algorithm for a maxim problem like this one， by definition。

 what it does is for every single input， opt is， whatever it is。

 And the promise is that the algorithm will return to you an independent set whose total weight is at least C times whatever the maximum possible is。

 Okay， so if C is like 05。 then it says you're getting at least half of the optimum。 Okay。

 it was 001， it would sound kind of pathetic。 You're getting 1% of the optimum and so on， okay。嗯。

So I guess I should really。Do one over this。 the way I just described that。 Okay， now。

 suppose you just wanted like a one over n fraction of the maximum possible independence fit。

 Let's start with the unweighted case。And that's a pretty easy problem。

So a vertex is definitely an independent set， so that gets you one。How many could opt get， Well。

 there's only in vertices， So an approximation is not so impressive right。If there are weights。

 you can just pick the max weight vertex， that will be an approximation， so not so impressive。

This is almost saying there is no polynomial time algorithm with a better approximation。 Okay。

 it's not saying there's nothing better than n， but it says， you know， n raised to the 0。99。

 you can't get N raised to the 0。999， you can't get and so on。

 Okay So unless P is equal to N P in which case， of course。

 you may as well solve the problem exactly。If P is different than NP。

 you can't get anything nontribual。So for worst case analysis， the problem is essentially closed。

 I mean， you can say， well， you know， maybe I can get， you know， root log n over n。

 maybe I can get log n over N。 And you know there actually are algorithms that beat one over n a little bit。

 but that's all you can do okay。So for worst case analysis。

 poly time algorithms totally stuck with this problem， it's really not a lot you can say， all right。

So there's some parallel to you know when you're talking about competitive ratios for online paging algorithms。

 I do want to point out that the reason that we're doing so badly is because of a different handicap So with paging algorithms。

 the reason we were so far from optimal， it wasn't that we had to run fast it's just that we didn't know the future it was a lack of information here the reason we're doing so poorly is because we don't have enough time on our hands right we have all of the input and if we had exponential time。

 we could of course solve it exactly but we don't so our handicap is polynomial time but under Pnot equal to NP we have a very similarly damning negative results。

So again， this doesn't say that one shouldn't attempt to reason about various algorithms about independence yet it just says we need to kind of change our viewpoint。

 we need some new way of comparing algorithms if we want to say design new algorithms。

 interesting algorithms or analyze old ones。So let's go through that exercise。

So idea number one is to say， okay， well， let's parameterize the inputs in some way。

And have a heuristic which does better and better， hopefully much better than this terrible lower bound on relatively easy inputs。

So there's a lot of ways you can parameterize graphs， many， many ways of doing it。

 You're certainly used to vertices。 You're certainly used to edges。

 What we're going to use right now is the maximum degree。 Okay。

 the maximum number of edges incident on a vertex。 There's many others。

 You've probably seen many others。 Okay， so idea number one。Prameterize。By the max degree， Delta。

Okay。And。The intuition that we're hoping， we're hoping that somehow as Delta is smaller。

 this problem gets easier。I gotta say， the narrative for this isn't quite as strong as it is with locality in the LRU algorithm or something like that。

 I mean， in some sense， it's not going to any harder there's only fewer and fewer graphs you have to handle as Delta gets smaller。

 The vague intuition is that， know independent set， that means once you take a vertex。

 you can't take any neighbors。 So if you're using a heuristic， you're gonna screw up sometimes。

 And somehow like the cost of screwing up by erroneously adding a vertex is now you've blocked all of its neighbors。

 So if the degree is small， that means sort of any mistake won't penalize you that much because there aren't that many neighbors incident to it。

So that's kind of the best intuition I can give you about。

 you know until we talk about once you see an algorithm， you'll see why it matters。

 but without an algorithm that's kind of the best I can say。

 it's intuitively mistakes seem less costly if the degrees are small。

But we'll see this is in fact the case。All right， so let's talk about an algorithm then。嗯。Yeah。

All right， so remember， capital Delta is the maximum degree of the graph。

So this is going to be the random greedy algorithm。Very simple algorithm。First thing you do。

 so you're giving a graph。First thing you do is you impose an ordering on the vertices。

 and this ordering is chosen uniformly or random from the n factorial possibilities if n is the number of vertices。

Now we're going to do a single pass through the vertices， greedily constructing an independent set。

Remember what an app penace set means， that means if you've already got one endpoint of an edge。

 you can't have the other one。So。Now we just do our one pass。Start with the。Empty independent set。

And we maintain the dairy that S is always an independent set。So we get to a vertex， we just check。

So if adding I to S， it would still be an independent set， I。e。

 if no neighbors of I are already an S， then we pick it， otherwise we skip it。

And then after the pass， you're done。So that's the algorithm。Any questions， The algorithm clear。

like you code that up in like 30 seconds。Good。Good， good， good。

One thing that's pretty weird about this algorithm。

 Not it doesn't even look at the weights of the vertices。

 there were these weights that you're supposed to like maximize。What elses。はは。Okay， but actually。

 especially when the max degree is small， this algorithm does reasonably well。So here's the keylema。

And。Now， what I want to do is I'm going to state the limma。

I want you to think on your own for like 30 seconds about what the proof of dilemma is。

 and then after that I want you to discuss it with a neighbor around you， swap ideas， okay。

Here's a dilemma， here's a claim， and this is the key claim for the analysis。

Which is pick your favorite vertex。And look at the probability that V is in the output。 Okay。

 so remember's randomized。 now， we're going to pick this ordering at random。 Okay。

 so this is saying equivalently， for which fraction of the orderings does V wind up in the final output。

I claim this is at least one over the degree of V。Plus one。All right。

So you tell me why that's true and I'll find out what the score in the Giants game is。Tally is good。

This degree is the number of neighbors that I have。

Any way that something doesn't end up in the magnetic said。

 one of his neighbors has to improve one more than right again。because hass that。of what of the。

All right， glad you had a chance to discuss a little bit。So let me give you a sufficient condition。

 Let me give you a sufficient condition for a vertex I being included in the final set S。

 Suppose I shows up before any of its other neighbors。Then there's nobody has to block it。Right。

So pick your favorite vertex V。 Maybe it has like five neighbors。 agree is like 5。

 So now we have six vertices that were interested in V in its five neighbors And a random ordering the vertices。

 the six factorial relative orderings of those six vertices are equally likely。

 V in particular is equally likely to be in the first second， third， fourth， fifth or sixth position。

 One out of6， it's in the first position。 If it's in the first position， it definitely gets included。

😊，Okay。Is that an equation， should that hold to the quality？No good okay。

 so there are ways you might sort of luckily wind up in the independent set even if you weren't first。

 maybe someone was before you， but they were already blocked by one of their neighbors and then it turns out you're free to be added to the algorithm anyways。

All right， it's a proof。Happens provided。V is first。So， the earlier。Then all neighbors。Okay。

So now we're pretty much done。By our trustee Fran linearity of expectations。

So let's look at the let's know， the weight of the solution returned as a random variable。

 It' a randomized algorithm。 So let's look at its expectation。So the expected weight。

I'm just going to write RG for the solution returned by this randomized greedy algorithm。

 and the expectation is over this choice of ordering。Well， so what is this， right。

 So what we're going to do is， you know， we're just going to break this down vertex by vertex。

 So this is a sum over the vertices of the contribution of a given vertex V。

AGiven vertex V either contributes its weight， WV to the solution or0 exactly depending on whether it's in S or not in S so if what the probability it contributes。

 it's it's exactly this it's lower bounded by this and when it's in S it contributes its weight。

So by linearity of expectation。This is just this。We can get the same bound if we just sorted our vertices from S force。

From best to worst。Is that obvious？You can't get this probabilistic claim。Yeah。

 but you can make a different， a different related bank。

So I'm going to leave as an exercise for homework number three。

 how you would have a deterministic analog of this algorithm。 Okay。

 so there is the deterministic algorithm that gets you the same guarantee I'm not going to present it here。

In what sense？It's completely random so anniversary kind'。Sure， sure， if you like。 Yeah。

 So I mean I mean， in this sure， I mean， if you want， you can view it as in the spirit， a quick sort。

嗯。You know， that' shed， you know， often， right， so you have to be。

You can get the same guarantee deterministic， but you have to work epsilon harder， not much harder。

 but you're right， epsilon harder。So somehow just being completely oblivious and random is enough to be good on any input can do what he was saying but also have some noisy ranking。

You need to be careful with the ranking。 Yeah， so that's the one twist to the deteracy problem。

 You have to be a little smart about which ranking you choose。

 But there is a ranking for which you wind up getting this guarantee。Right， but so today。

 I'm going actually show you two randomized algorithms today。

 Both of them have deterministic versions。 But the main point is just what's sort of possible。

 So I'm gonna to kick out the deterministic versions to the homework。Okay， so。

 and now what we see is that indeed we can talk about this algorithm's performance as parameterized by delta。

 parameterized by the max。Degree of the graph。So in light of corollary number one。

 the randomized greedy algorithm has approximation ratio at most Delta plus  one。 So again。

 Delta is the maximum degree for a randomized algorithm。

 I just mean the expected value of the solution is at least。Okay。

 so what I mean here is the expected value of the solution is at least a one over delta plus one fraction of the maximum possible。

Why is that true， Well， so if the max degree is delta， this isn't most delta。

 so each of these terms is at least a one over delta plus one fraction of the vertex's weight。

We're something over all the vertices， okay？How big could the optimal independent set be， Well。

 here's a very coursear over bound at best。 if could get every single vertex。 Okay， so at best。

 you get this exact same sum with that hidden。Okay， so how far are we off。

 We're off by the biggest the denominator could be。 that's Delta plus 1。Cool。So。

There's good news and there's bad news。So the good news is that we can definitely treat this as another kind of feather in the cap of parameterized analysis。

 We took a fundamental problem that was super hard。

 We found a natural graph parameter or a natural algorithm and we showed how this algorithms performance。

 again， the algorithm just is works on every graph。

 the algorithm isn't somehow tailored to our parameterization。

 but it just sort of automatically works better， if it happens to have an easy input in the sense of a low maximum degree graph。

 And in fact， I'll leave this as an exercise， too。 If we're only worried about the unweighted version of the problem。

 So if all the weights are one， actually， this also implies that you can you get the same bound with the max degree replaced by the average degree。

 that's a stronger statement。 So there are graphs with low average degree with high maximum degree。

 So even average degree is good enough for the unweighted case。😊，So that's pretty cool。

Here's the bad news， though。 Or here's why we might want something better。

So one way you might critique the maximum degree parameter is that it's not a very robust parameter。

 Okay， it's brittle in the following sense。I can take a graph with very low delta。

 change it by basically in an irrelevant way and find myself with a graph with a really big delta。

So imagine you have this graph G。And it has small Dlta。 Maybe it's a cubic graph。

 Okay maybe Dlta is like 3。 So we know that we're getting at least 25%， not just of optimum。

 but we're getting 25% of the weight of all of the vertices in the graph for the randomized greedy algorithm。

 So that's pretty good。😊，But now， suppose I come along。 and I just。Add one more vertex。

And connected to everything。Okay。So you might ask， what's the weight of this vertex。

 I don't really want to worry about it。 Let's say the weight is， you know。

 at least the weight is small enough that optt doesn't take it。

 So if opt notice that in an independent set， if you take the pink of vertex。

 you can't take anything else。 It's connected to everything else。

 Okay So let's just assume the weight is less than like the sum of the other weights in the graph。

 So optt hasn't changed at all。 okay。And if you think about it， greedy is barely different also。

 Okay， like once in a while， this pink vertex will come up front， and it'll screw up。

 but that's going happen like one and n times。 And it's not a big deal。 Okay， so ops identical。

 greedy is almost the same， but our analysis is gone from proving a 25% guarantee to like a one over end guarantee。

 Okay so our analysis is very brittle。 It's of just not faithfully modeling what's happening。Okay。

So that's what's unsatisfing about this。 right， So we somehow want an analysis of parameterorization。

 which is robust to small modificationifications to the graph like this。

 So that's where we're going next。So。Here's kind of the slightly hand wavy observation。

 but that we'll be able to turn into something precise。Which is like， oh yeah， okay， You know。

 the graph has a high degree vertex。But you know， really。

 we're just trying to get a constant fraction of the best independent set。

 we have the optimal independent set， and the optimal independent set has exactly the same， you know。

 the degrees are almost the same as before。so there's still a max weight independent set where all the degrees are small。

And somehow， the feeling is that should be good enough because we're only trying to compete with up。

 We're not trying to compete with all the vertices in the graph really。Okay， so art。Still has。

Assuming again， this weight is not too huge， then all of optimize lies in this graph with small degrees。

And let me notice， let me point out。That actually were immediately done。 Actually。

 we still get corollary number two。Under this assumption。

 under the assumption that optt comprises only low degree vertices。 Why， well。

 you know we know this is true， no matter what the graph is， okay。

So the right hand side only gets smaller instead of summing over all of the vertices。

 I only sum over the vertices in the best independent set。 Okay， it's only worse。 so I can do that。

But now all of a sudden， the independent set only has small degrees。 I'm again。

 getting a very large fraction of each of the weights in the independent set。 Okay， again。

 a one over delta plus one fraction。So I'm not getting a one over deta plus one fraction of all the vertices in the graph necessarily。

But I'm getting one of a delta plus one fraction of the optimal solution。

 If its degrees are all at most deelta。So。Cooleary number two still holds。Okay。

 still holds under the assumption that the opt maximum independent set has only degrees at most capital Delta。

Anybody clear on that？So what I want to do next is just turn this observation into bona fiide parameterization。

But this is sort of really the key insight about where the parameter comes from。Yeah， that's right。O。

So that's going to be the idea in this case study， this independence set case study。Praterize。

By the degrees in opt， not the degrees in the graph。

So this is so I think the closest analog to this parameterization that we saw was the output sensitive bound for 2D maxima。

 So back when we were talking about Patrick Sall， we had these three parameterizations。

 And the second one was n log H。 it was parameterized by the input size N。 And in some sense。

 the structure or the size of the optimal solution of the number of maxima。

 that H was showing up in the bound。 So that's sort of what we're doing here。

 We're almost kind of like we're trying to compute something that approximate opt。

 But for the purposes of analysis for the purposes of defining this parameter。

As a thought experiment， we're saying， well， imagine opt look like this and' have low degree vertices。

 And then that's going to be our guarantee okay。So formally。

So here's what first of all is going to be true for randomized greedy， and second of all。

 it's going to be the parameter that we then try to see if we can do better than randomized greedy。

So the claim is we've proven the following， so this is basically just a restatement， well。

 sort of a generalization of corollary number one。So the expected weight of randomized greedy。去。

Is at least our usual friend。For every independent sets。I of G。Now， again。

 I'm stating something which is， know， weaker than what's true for randomized greedy。

 right because we， we prove that actually， you know， remember。

 every term of this sum is non negative。 Wes are non negative。

 So throwing out terms only gives us worse lower bounds。 right， So we have a lower bound。

 even for the full sum。 So obviously， I'm free to throw out any subset I want， know， for any subset。

 know， I can lower bounded by this in particular for independent sets。 Okay。

 but this will be useful as we go forward and try to optimize this。 Try to make this better。

So the two things I want you to understand right now， first of。

 I just want you to be able to parse what the statement says。And second of all。

 I want you to agree that。We've proven this statement with a one on the right hand side。

For randomized greeting。Okay。And've proven a stronger statement where this is any subsetstive vertices。

 not just independent sets。Okay。But again， when you sort of move on to how to interpret this bound。

 you could imagine you might want to throw out some of these sumans that have high degrees because then you get this nice statement about you get a good approximation of anything that comprises only low degree vers。

All right， so any questions about that。 Everyone agrees that this we've proven that this is true for randomized greeding。

Right， so I guess another thing I want to point out is。

 so I've written this a little bit more generally。I've said that this is true for every single independent set。

 So in particular， you could imagine， well， you know， maybe the actual max weight independent set。

Has one high vertex or some high degree vertices。 But there's an independent set。

 which is almost as good， almost as much weight。 Okay。

90% as much weight that always has super small degrees。 Okay， well。

 then that's the independent set you want to invoke this guarantee for。 So really。

 what this says is as long as there's any independent set。

 which simultaneously has pretty high weight and pretty low vertices， your golden。 Okay。

 the heuristic will do well。 That's really what this says。😊，Okay。Oh， a couple of the comments。Yeah。

 so you could ask， all right。 So this is， this is nice in that it tells us sort of when randomized greedy works well。

 It works well if there' a new optimalim solution with load vertices。

 Another follow up question you might ask is， well， is that a condition I ever expect to be true。😊。

Okay so like when we were parameterorizing paging， we sort of， you know。

 we knew we had all this empirical evidence for assuming that there was high locality。

 What's our evidence for sort of assuming that typical independent sets that have high weight have low degrees？

Not clear， actually， right I think it's plausible。 You know。

 it's plausible that in typical instances， you're going to prefer vertices that have low degree because they're more likely it'll let you pick lots of other vertices instead。

 seems reasonable。 But I don't know。 Also， it's not actually clear how you check this。 right。

 So unlike that locality measure， where you could just compute the functions F and then compute the alpha and see what you get。

You know， this is talking about independent sets like Max weight independent sets。

 which we don't know how to compute。 Okay so， you know。

 the bottom line is if you run this heuristic and you get awesome independent sets。

 you probably don't care if the condition held or not。 but it's sort of like a faithbased approach。

 Okay， you're thinking it's a reasonable real data would satisfy this。 And in that case。

 I know this works。 And then， of course， if the heuristic fails badly。 You know。

 this was not true right And you need to sort of have a different approach。is I mean。

 this is true for the algorithm that works over the whole set， right？I mean。

 my question is that maybe like。Could we have an algorithm？

That only works with or would we have maybe a better algorithm if we explicitly ignored the。

I should high degree。Yeah， so that's a good question。 So it does。

 you're right that it suggests the following， it says。You know， basically。

 if you have vertices that are very high degree and very low weights。Go ahead and prune them。

I agree with that。 Yeah， And in particular for randomized greedy， that actually。

 I think that would improve the empirical performance because now know。

 there's no chance it's going to show up early and sort of screw up your whole algorithm。

So absolutely， so sort of thinking about the guarantee you get can definitely guide you to smart ways to pre processces the data。

 Yeah， exactly， which we're going to sort of you know， also tackle head on next， but yeah。

 I completely agree with the suggestion。Good coming。Other questions？All right。

 so what I want to do next is I want to sort pivot。

 I want to change our perspective in a way that to something which you're very used to from other algorithms classes。

 but we literally have not done yet this entire lecture， which we're now going to say okay。

 instead of trying to get more faithful and useful analyses of algorithms we already have。

 we're going to flip it around and say let's look at how we're analyzing algorithms。

 does that suggest better algorithms， So we're now going ask can we do better。

 not from an analysis perspective， but from a design perspective。Okay。So can we do better？

And what I mean is， can we do better than this one？Okay。So can we do better than randomized greedy？

In the sense that it's getting this fraction of every independent set， weighted by the degrees。

All right。Now， one question you should actually ask first is well wait a minute。

 do we even need a better algorithm， Maybe we just need a better analysis， But turns out no。

 it turns out if you just stick with a randomized greedy algorithm。

 you can't prove anything bigger than one here。 Okay。

 so one is tight for the algorithm under discussion。 So if we can do better。

 it has to be with a smarter algorithm which is good because right now。

 that's actually going to be sort of our mindset。Alright。

 so let me just give a little credit where credit is due。So， this。Sort of objective， if you will。

 of trying to design algorithms that make this constant as high as possible。

 This is called the recoverable value。And this independent set case study is from FigA and Reichman。

From a few years back。And this is a particularly clean special case。Of the so called pass framework。

Here PA stands for parameterized by the signature solution。

 so you should sort of think of this degree weighted stuff as being a signature。

 like low degrees being a nice structural property of an optimal solution。

And this was a few years earlier。 But again， pretty recent， this was from 09。对。

And the motivation of this work is exactly what I sit Okay， it was basically to say， well。

 input parameterizations are great， but perhaps we can have more robust parameterizations by actually looking at what the solution is and what we were previously having as parameters on the input。

 we impose them on the output instead， okay。So that's going to be a weaker assumption about the input。

 So your algorithms will only work for wider families of instances。

 That was sort of sort of the idea。Okay， so。So to what extent can we beat this one。Well。

 actually we can't improve it by a lot。So。The window of opportunity is fairly small。But。

Big enough to get us an interesting new algorithm。So what's the line in the sand？嗯。

We can't get it up to four。Okay。Why can't we get it up to 4。Well， suppose G was a cubic graph。

Let's think about what this would say。 Okay， so suppose we could prove this guarantee with the one replaced to by a4。

 And now let's instantiate that guarantee on a cubic graph， okay。That means all degrees are three。

so this denominator is a4， which cancels out our alleged coefficient of four。

So this would actually say that the algorithm is getting all of the weight of every independent set。

 That is4 is equivalent to saying in a cubic graph， you're solving the problem optimally。

Turns out this problem is NP hard to solve exactly in cubic graphs。

So we can't replace one by four because if we could。We get exact solution。Cubic graphs。

For independent sets。嗯。Which would imply P equals NP。

So I should say we can't replace one by four unless P is N。 to be precise， to be pedantic。Okay。

But here's sort of the main， here's like the main cool algorithm for the lecture。By Fargan Reckman。

Which says we can replace。The one。Byu a two。Okay。So we can get double this guarantee。Now。

 I think what's interesting here， you know， So most know， analysis frameworks。

 you when you're in this sort of， when you're in the design goal mode。

 analysis frameworks prove they're worth by you know， guiding you to algorithms。

 which one you wouldn't have thought of otherwise。 But two， once you see them， you're like， oh， wow。

 that might be a good idea。 Okay， so that's really。

 I think the litmus test on which this algorithm succeeds。 You know， one versus  two。

 it's a little hard to interpret。But striving for bigger constants gave us the following algorithm than which I think is。

 pretty neat， actually。So what's the algorithm？So it's， you know。

 a slightly beefed up version of randomized， randomized greedy。First steps the same。

So order the vertices randomly？So here's going to be the modification。F I equals one to n。Oh。

 it's one thing I forgot to say with randomized greedy。 If you look at the way we analyzed it。

 So the algorithm was very natural。 Just said， you know， go through it in one pass。 And if， you know。

 you can pick it。😊，When you look at that analysis， and you look at how we prove the guarantee。

 the guarantee would have held equally well for the following stupid algorithm。

 which was do a single pass through the vertices， if this vertex beat all of its neighbors as earlier than all of its neighbors。

 then take it。Otherwise， don't。Okay。So then that lemma holds with equality， that lemma。

 the probability of v is an s equals one would instead of being at least one over a degree plus one would be equal1 over a degree plus one because we're taking the sufficient condition from the proof and we're saying let's modify the algorithm。

 or it's a reverse engineer the algorithm that only takes vertices when the sufficient condition is true。

 but the analysis would still hold。So this is going to look a lot like that slightly less smart version of randomized greedy。

 okay。So instead of saying， you know， if a vertex V is first amongst it and his neighbors。

 we're going to say， well， it's O if it's second too。We'll take them as well，So， if。At most， one。

Of I neighbors already seen。Add。I to T。Okay。Now， you should have an immediate reaction。Which is。

 dude， this is not going to be an independent set。That's right。So that's why I have a step three。

Which says amongst the vertices that survive， the ones that are in T。

 amongst those compute the best independent set that you can solve the max weight independent set problem。

Return a max weight independent set。Of T。So let's call the independence of S。O题。Okay。

So any other questions about the algorithm other than why on earth did this run in polynomial time and why on earth does this give us a performance guarantee。

 Anything else。I have a question about before。And。Can we also say free because if if we had dive veries in the line and we had a performance guarantee of three times。

We would basically have the sum of the weights and we know that even the optimum can get the sum of the weights if we just line up Oh be careful about having the sum of the weights right。

 at look at what the statement says the statement the guarantee we're shooting for is not。That。

The weight of your solution of your algorithm is at least you know whatever times the weight of all vertices。

 so the actual guarantee we're shooting for just says for every single independent set I of the graph G。

 you should get at least the sum over the weights divided by degree plus ones of that independent set。

So you write that randomized greedy achieves a stronger statement than what this asserts。

 randomandized greedy gets the one。 But with a bigger sum here over all of the vertices。 Okay。

 but what we're asking for now now that we've focused on this idea， actually， really。

 what matters are the vertices of the independent set themselves。 So let's only quantify over those。

 Now we can ask， can we do better in this metric。 Yeah， It's a subtle point。 It's a good question。mm。

I just the third step in that。Al use itself or does it does not care Right， So that's why it's。

 I mean， it's not clear， right， So for now， maybe you you're just thinking step 3 is like by brute force or it's not even clear。

So I'm saying return。 So notice， I'm not saying approximate anything。 I'm saying。

 solve the problem exactly on T。 So that's why it you shouldn't。 You should be asking me。

 why does this run opponent all time。 I thought I thought it was going be a hard problem。

 That's what you should be saying。All right， so let me address those concerns。

So let'ss start with a running time。I mean， intuition， you know， about like。

 where does this algorithm come from。 So the idea is， you know， rather than， you know。

 lose a bunch of weight， lose a bunch of information。

 like in the randomized greedy algorithm and just outputting an independent set in one shot。

 let's sort of harness a bit more stuff from the graph。But， you know。

Few enough stuff that we can compute and independent set in what's left in polynomial time。Okay。

 so T is sort of the sweet spot where it captures more of the graph。

 So that's why we're going to get a better approximation。

 but it's still simple enough we can solve independent set exactly。😊。

So let's start with the running time。Here's another lemma I want you to think about for 30 seconds and then discuss for 30 seconds。

So I claim that with probability 1， So remember， it' to randomize the algorithm。 Okay。

 so the vertices will have various orders， depending on the order， you'll compute a different T。

 And depending on the T， you'll compute a different S。But I claim that always， with probably one。T。

Induces a forest。Yeah。Oh， sorry。 let me make sure this should say。

 maybe a little bit more precise about this and remind you what induced graph is。

So step two is just picking a bunch of vertices。 And so remember。

 when we talk about an induced graph。It's just， so you talk about the graph induced by a subset of the vertices。

 It comprises those vertices plus edges that have both endpoints amongst those vertices。 Okay。

 So the subgraph induced by these four blue。Vertices would just be these two edges。 Okay。

 would just be a disconnected set of two edges。 so that's what I mean by the induced graph。

So step two picks a bunch of vertices in step three， you form the graph。

 which is the vertices of T plus all the edges that are both endpoints in T。

 and that's the graph on which you compute an independent set。

 and the lemma is claiming that that graph that induced graph is always a tree so think about that for a little bit。

さ。Okay。I。Yeah。Its basic area。is less。O。So basically， we have a show。to going into their form。

And then。あ。So， because it would be the last one in the cycle It and。The we can。That。All right。So。

Cs pretty simple。Consider any cycle of G。Here's a cycle with six vertices。

One of those vertices shows up last。And when it shows up。

 both of its neighbors have already been looked at。Okay。So every cycle has one vertex omitted。

 so what's left has no cycle， so it's the forest。Okay。So for all cycles， C of G。I mean。

 maybe other vertices are emitmted as well， but at the very least， the last vertex。Of C。Is omitted。

Donngqi。Okay。Agreed。So T need not be an independent set， but it's not very complicated either。

 In fact， it's so simple that we can implement step 3 in polynomial time。Okay。

So I'll leave that also for the homework。Which is that you can solve。Max weight independence set。

Exactly。In poly time， actually in linear time。And trees。Okay。And the hint is dynamic programming。

 So if you' a little rusty， you can use this is a good。Good thing to jog your memory。

So I hope we all agree now that the algorithm runs in polynomial time or can be implemented to run in polynomial time。

So why does it replace the one with the two？That was that was the assertion。Here's analysis。

Which is pretty slick。So we have to show that this holds， except now we want it two， right。

So we're shooting for this。With Figar Reichman。So we want to prove that。

We want to prove something for every single independent set I， so fix your favorite one。

And don't forget， T and S are random variables。 Okay。

 so they'll be different depending on the random ordering you choose in step 1。But， you know。

 in any case， with probability 1。If you look at the projection of the independent set I onto S。

 that's going to be an independent set in the graph induced by T。So I'm using as G square brackets。

To denote the induced graph。 Okay， so， first of all， right， so I' is a set of vertices。

 I' is an independent set in the original graph， the whole big graph。S is the final set of。

The final set of vertices that you output。That's not what I want， I want I intersect T。

 that's what I thought。That makes much more sense。So T's a set of vertices。

 These So all vertices in here are vertices in here。 Moreover， it's an independent set in here。

 right， So I is in an independent set。 There's no edges between them and the original graphs。

 drillinging。 there's no edges between them。 And there's only smaller graph。All right， so what？So。

What we're really interested in。I you interested in the expected weight of the independent set that the algorithm outputs。

 Okay， that's our right， That's our left hand side here， okay。So how do we get our hands on this。

 we want a lower bound on this。Well， remember， no matter what t is。

 S was chosen optimally in the graph induced by t，So the projection of the independence at I onto T。

 that was an option。 I intersect T was a feasible solution。 We picked S， which was optimal。 Okay。

 So T by T， we pick an S， which is at least as good as I intersect T。😊。

That's why that inequality follows。 S always beats iron orect T for every single T。Okay。

 why did I do that， Well， Iect T is a lot easier to think about， because I here is just fixed。

So now let's use linearity of expectations again。So let's look at the contribution。

Expect a contribution to use a vertex of I。So the only vertices that have an opportunity to contribute here are those of I。

 So we're just going to go through them a at a time。Under what conditions does I contribute， Well。

 if and only if。It's in tea。Is that what I want？H last。 So it turns the probability essentially。

 Right， okay， So， so if it contributes， it contributes W V。And it contributes W V。

 if and only if it's a member of Iect T， that is if and only if it's in T， okay。So probability。

That V isn't he。Okay。Or get the probil over the order。So with the ordering。

 sometimes V will wind up in T。 Sometimes you'll see V first or second amongst its neighborhood。

 Sometimes you'll see it later。So this is the fracture of the time that it's in the first two。

Whenever that happens， it's a member of I or our 16。

 Okay We're already assuming he was a member of I。And so now we just use the same argument as before。

Right so for our first lemma。We said， you know what's the probability that someone winds up at that point for randomized greedy。

 we were thinking about in the final independent set and it was if and only if， not if and only if。

 but it was if they are first amongst them in their neighbors。 In this case。

 V is chosen for T if and only if it's in the first two positions in the relative ordering amongst it and all of its neighbors。

 So instead of a one over degree plus one， we have a two over degree plus one。

So V is chosen if it's first。 V is also chosen if it's second。 And that's because of。This tweet。

 right here。Okay。So this equals two over。Degree of v plus one。有。

So this comes from the same place as our1 over degree of v plus1 before。

 exactly the same as the limma。So that's it。Reranging some over V anI。WV。Degree of V plus one。

I was an arbitrary independent set， so that's exactly what was state。So any questions about that？

Yeah， so is the problem with increasing it from either either being first or second first second or third。

 there's no issue with the analysis that good can solve Excel， exactly right。Yeah。And， I mean。

 so I mean， if you think about it， you could still hope to play this game further。 And in fact。

 this is how they get some better results for unweighted independence sets。 You can say， well。

 you know， maybe if I allow at most2， I get a graph where I can't solve it exactly。

 But maybe now I can have a parliament time algorithm that approximates it really well。

 So in general， there's sort of this trade off between like， you know。

 how much weight do you lose getting to step 3 and then how much more weight do you have to lose by just using some heuristic for the special graph in step 3。

So in fact， so for weighted independence set， as far as I know。

 there is still no known result which beats two for the weighted case。

 as far as I it's still open to close the gap between two and 4。

For the special case of unit weights and this is actually sort of odd because it's pretty rare you find sort of rigorous guarantees that hold for the unweighted case of a problem like this and don't hold for the weighted。

 So for the unweighted case that use tricks along those lines to get it up to sevents and that's kind of where things seem stuck and so it's similar ideas but you do have to work a bit harder you have to basically combine a couple different algorithms together for a couple cases it's not much better than two。

 but it is better and it is what's sort of curious so again two things I mean first of all。

 it kind of motivates designing different algorithms。

 sort of more sophisticated algorithms which might be useful independent analysis framework so that's one reason why it's interesting second thing conceptually it's it's again unusual to see the separation between the weighted unweighted cases So if we're sort of nerds and these kinds of approximation algorithms that's also kind of an interesting point。

I mean， it's an esoteric point， but it's sort of interesting。 Yeah much help if we ran 10。Yeah。

 so in practice with something that's this fast， that's what you'd want to do。 Again。 So this is all。

 this should all be linear time。 So， you know， you may as well， you know。

 depends on the on the data set size and， you know， your computing power。

 how many times you can get away with。 but you definitely want to run it several times。

 It's not clear what the variance is。 So it could be it varies a lot input， the input。

 I don't think that's well understood。So like for the other one。

 there is a deterministic algorithm which gets the same guarantee。

 unlike the previous case where the deterministic algorithm was really kind of a deranomization。

 the randomized one here it's a totally different algorithm based on a linear programming relaxation so I'll put that as one of the problems on homework number three。

 it's a quite interesting algorithm in its own right， so you can get this deterministic。

 but it's not known how to do it with a simple deranization of this randomized algorithm。But yeah。

 again， the main thing I like about this， this randomized heuristic。

 especially say with some of the enhancements that you suggest， is， I mean。

 it does seem like something。 It's not clear how you to come up with this。

 And it also definitely seems worth trying。 It's simple， but it also seems sort of smart。

 So if there's people who are looking to get out of the last few problem sets。

 an empirical project on these algorithms， I think might be might be something good to do if any of you are interested。

 so。O。Questions。So that's going to be our last full blown case study。嗯。On。Pramerizations， although。

 like I said， they'll reoccur throughout the course。

 especially prominently when we talk about smooth analysis。 over the last few lectures。

 I chose a few to kind of highlight。You know， sort of perhaps less less known ones or ones。

 which are not the first ones you would think of。So we saw three examples。

 we saw parameterizing Kirkpat Saideel in a few different ways， most finally by the entropy measure。

And we saw paging parameterizing by locality and now we just saw independent sets parameterizing by the degree of an optimal solution。

 so what should you take away from all this stuff？So， you know， I know most of the details will。

 I'm under no delusions。 Most of the details will fade in you know， a month， if not two days。 But。

 you know， what do I hope if you remember， like， you know。

 just a couple things about the last few lectures。 what would I like you to take away。 So first。

 just kind of very。You know， simply is that there's lots of reasons。

You know we're kind of you know the beginning of your algorithms education really focused on these worstcase bounds。

 which are not parameterized or rather they're parameterized solely by the input size okay so I just want to convey to you that you lose a lot of information if that's all you use to measure problem complex is the input size and I'm trying to show you through example after example that not for all problems but for lots of problems。

 people have successfully had much more fine grain analyses and there's a lot of reasons why you want to do that we went through them mostly at the beginning of the lecture okay finer grain comparisons separating algorithms you couldn't either by any other way explaining good empirical performance even when the worst case performance is bad and so forth。

Okay， so aspire toward。Pramerized bounds。Now， on the other hand。I feel kind of bad。

 I feel like I owe you apology because I've chosen。

 all of the examples I've chosen for lecture have been extremely problem specific， right。

 The entropy measure， the locality notion。This one may be the least， but still， you know。

 sort of you know， the optimal solution of looking at its degrees。 know， even if， know。

 even if one of you goes on to design and analyze algorithms for a living。

 you're probably unlikely to reuse any of these parameters。 I mean。

 I hope at least it kind of shows you one can do these sorts of analyses and it's worth doing。

 But there's very little here that you can just are going be literally apply to some other problem you encounter in the rest of your work。

 okay。That said， there are a lot of parameters that are super well known and super useful。

 so I just want to sort of wrap up the class with this toward Dory zone of some of what those are。

 some of these hopefully you've heard of， if you take enough Cs and optimization classes。

 you'll encounter many of these So my point today is just so that you' kind of heard of these。

 Maybe I'd peakique your interest to delve deeper on a couple of them。

 And a bunch of these will show up in homework number three to give you some practice using them and just like better chance that you'll remember the definition a few months from now and so on。

So moral number two。And again， I feel bad because I haven't really spent lecture time。You know。

 helping you do this。 But you know， no。No standard parameterizations。 Okay。

 so ones that are broadly useful， it's good to know what these are。Okay。

And it would be totally hopeless to be encyclopedic。 I mean， basically。

 all fields of optimization kind of sometimes do ad hoc parameterizations。

 but let me just single a few out to give you a sense of what's out there。And also， maybe know。

 what are their similarities and differences and how do they compare to what we've been doing in class？

So there of a brief users God。Let me first just kind of。

M a few ways that we can compare and contrast different parameters。

 both the ones we've already seen and the ones I'm about to tell you about。And， you know。

 so all of these design decisions， when you're choosing a parameter， you know。

 both answers can be legitimate in certain cases。 I think what's just important is just be clear in your mind。

 you know， what are the features of the parameter that you're working with and which of those goals are you trying to accomplish。

 Are you trying to design new algorithms do you have an algorithm in your hands and you want to know when it works and when it doesn't work。

 Which of these things are you're trying to accomplish because the goal in mind usually guides which of these is an appropriate choice。

2。So， the first。Way that these can differ。 And we've seen about a 50。

50 split in class is you can have a parameter which in some sense is directly referencing the input。

Versus one， which is really referencing the solution to the problem。 Okay， And so like。

 remember the analog log H bound for Kirkpat' S Delt。

 that nicely showcased both of these N being the size of the input， H being the size of the output。

When we talked about paging， that was purely about the input。

 the locality of the page request sequence。 It said nothing about the eventual optimal solution about furthest in the future or something like that。

 What we did today was about the solution。 Okay， it was really saying， what's the degree in opt。

Another thing to keep in mind is， which hat you have on。

 you in the Do you have the analysis hat on or the design analysis hat on。

 Are you looking for a parameter to better understand what you've already got or to guide you to things which are better okay。

With paging， for example， we weren't proposing the parameter to design any new paging algorithms。

 We felt confident that we knew how we wanted to solve the problem。

 We didn't want something superior to LRU。 We just wanted to have a satisfying mathematical foundation for its empirical superiority。

 By contrast， we sort of shifted gears from one to the other with independent sets。

 We introduced the parameters looking for analysis， but then we shifted to design。😊，Alright。

 so now the， the third kind of thing which really can vary a lot is。

 usually you're arguing that some parameter is small。 Okay， so again。

 like a simple example would just be the number of maximum H。 You want to say， oh。

 the input is easy if H is small。So small can mean different things in different senses in different contexts。

 and that's what we'll talk mostly about in these examples。So the sense in which。

Either the input or the solution， depending on which choice you made in step one。It's small。

Or sometimes it's not really small， it's just sort of nicely structured。Okay。So at least personally。

 I find， you know， these differences as being helpful when I'm trying to classify and compare different parameters。

 But again， all of these are legitimate in various contexts。And we've seen， I guess。

 in this class examples of all of them already。Allright， so some examples。 And again。

 most of which I'm just， you know， these are really just kind of shout outs for now。

 But most of them show up on the homework。 And that I'll give you a better chance to。

 to appreciate them。 So like on the homework。Just as a warm up。

 so these are just in the exercise category。嗯。I included or I'm going to include two problems where the goal is to understand when greedy algorithms work particularly well。

 So I'm gonna to ask you to look at the Napsack problem， which I hope you're familiar with。

 And you're going to find out that when the items are small， relative to the Napsack size。

 greedy actually is amazing because it's just almost optimal， very close to optimal。

 There's a similar example with the natural scheduling problem。

 And this is even for online scheduling。 So unlike in paging where we have these huge competitive ratios。

 it turns out there's some very nice load balancing type applications where online algorithms do pretty well。

 they do exceptionally well， if the jobs are in some sense， small。 so there going back to our list。

 it's really about the input， we're saying the input is composed only sort of small pieces in some sense。

 we're looking to just explain when greedy algorithms do well， not design new ones。

 And right I told you in what sense it's small。So that's going to be sort of the warm up on the homework。

嗯。Now， so often， you know， so this can be sort of context dependent。 but still。

 there are recurring themes， right， But so like depending on whether or not your data is sort of geometric。

 for example， like points in space， or if it's a graph。

Being well structured or being small is probably going have very different meanings。 Okay。

 so there's not going to be， you know， a single notion of well structured data that's appropriate for everything。

 But you might hope that， you know， maybe for all graph problems。

 this is a very frequently useful parameter。 or maybe like， you， whenever there's， you know。

 my data is points in R N， this is a very useful parameter。

 And there's sort of some parameters like that， okay。So for geometric data。

There's often notions of being low dimensional。Okay， know， and just geometrically。

 the simplest thing you can think of is， you know， maybe the points are in RN。

 but they all lie on a subspace of much lower dimension。 Okay。

 they're all very close to a subspace of much lower dimension。

There's notions of dimension which don't even require the points being in Euclidean space。

 So one thing I'll ask you to explore in the homework is something called doubling dimension。

 and that's something when all you need is a metric space。

 So now just imagine you have objects okay like images or something and you have some algorithm which gives you a dissimarity measure between objects so you say you run it on two images and it tells you oh these are like 140 apart in this dis dissimilarity measure。

So these objects aren't actually points in space， you just have distance information between them。

 and that's enough to describe this doubling dimension。

 so it's a notion of low dimension even when you don't have this RN structure。But again。

 in some sense， there's geometry to the data as soon as you have a dissimilarity measure。

So notions of dimension can be really good when you have sort of geometry in your data。

So what about graph？So for graphical data， there's lots of notions as sort of small or well structured。

Again， you could teach a course really just on all the different notions of this。So， you know。

 we saw one today， maximum degree， very simple graph parameter， you know， in some context。

 something like the radius is a relevant parameter on the homework I'm going to ask you to look at Twi。

Which is a much less obvious， but really very useful graph parameter。

So the tree with of a graph quantifies how tree like it is in a certain subtle sense。

 and many NP hard problems can be solved in polynomial time on graphs of bounded tree with。

 For example， maximum weight independence set， despite being so hard a general graphs。

 you can actually solve it in polynomial time exactly when the tree with is bounded。And you know。

 it's a little before my time， but I think when this first came out。

 it was thought to be some kind of fairly esoteric graph graph theory construction。

 but it's actually really useful these days。 I mean this has gotten to the point where it's used in both graph optimization and also in machine learning。

 It's a really nice parameterization。Okay， what else？

So something that's very much in the same spirit。But oh yeah。

 So back back to how to think about this。 So when you're talking about， say。

 like well structured graphs， obviously， it's a parameter of the input。

 We're really saying the graph is treelike in some sense。

 What's different is the primary goal for these parameters。

 And this is different than most of what we talked about in lecture。 Really。

 you're looking to design algorithms， which explicitly make use of this structure。

 It's not that you have some existing simple greedy algorithm and you're trying to understand when it works well。

 you're really saying， in effect， when you're the algorithm designer， you're gonna say。

 I'm going to assume that the tree width is at most for。

 And I'm going to design an algorithm that kicks butt on those graphs。

 Okay That's kind of the spirit of how you use that stuff。

 So you articulate the structure you believer in the graphs。

 and then you design the algorithm to explicitly exploit that structure。😊，Good。Something similar。Is。

You can talk about the output being small。 Okay， So something you can do here。

 not for independent sets， but if you look at the complement problem。

 if you look at the vertex cover problem。 So here， rather than max weight subject to not having two endpoints of every edge from invertex cover。

 you want this fewest vertices possible subject to getting at least one endpoint of every edge。 Okay。

 so the complements of independent sets。 So that's， of course， another MP complete problem。

 But it turns out if I'm only going ask you to find a if the optimal vertex cover is known to be small。

 say the most logarithmic size， then there's a clever backtracking algorithm that can find it in polynomial time。

So in the same way that up here， if the tree width is bounded。

 you can solve NP hard problems here for any NP hard problems， if the output。

 the optimal solution is in some sense small， you can solve them in polynomial time。

So this is actually a huge field。Called parameterized complexity。In fact， my colleague。

 Ryan Williams is teaching a class 266 on exactly this topic this quarter。

And it's somewhat more general than I'm talking about here。 But this is sort of the canonical cases。

 Okay， if you have small output， again， MP hard problems can become tractable。 And again。

 what you're doing here is you're really designing your algorithm explicitly to use the fact that the optimal solution is small in this sense。

Okay， and then the final thing I just want to use to segue into the upcoming lectures on clustering。

 which start on Wednesday。So this again is going to be really about the solution。

 not about the input。嗯。Which is you want to posit that the output in some sense is meaningful。Okay。

And you want， I mean， either you want to just have an assumption or you want to sort priorize meaningfulness and design algorithms that make use of that。

 I alluded to this in lecture number one， I said in clustering。

 we wanted to sort of make precise this idea that clustering is hard only when it doesn't matter。e。

 when it does matter， it's because there's a meaningful solution。 And that should be extra structure。

 which an algorithm can exploit to do well。 Okay so that's one notion of meaningful output。

 think about clustering， think about they actually existing a coherent grouping of the points。 know。

 sort of precursor of this from long ago， if any of you have studied and sort of remember just kind of basic numerical analysis。

 if you know the power method。 So that's how you compute the top eigenductctor。

 the top singular value of a matrix。 And basically you just sort of take a randomductctor and you powered by the matrix over and over again。

 And if you've ever studied the convergence rate of that method。

 you learn that it matters how much bigger the top eigenvalue is and magnitude than any of the others。

 And that's a sense in which the top eigenvector is sort of sticking out。 sort of more meaningful。

 It's more separated。From all of the rest。 So that's sort of， know， in spirit， a precursor of saying。

 well， you know， let's assume there's something juicy to find， okay， meaning a big top eigenductctor。

 And now let's watch how the simple algorithm works exceptionally well in that particular case。

 But again， so this last one is exactly what will' start tackling on Wednesday when we'll start the first of several lectures on finding meaningful clusters。

 See you then。😊。