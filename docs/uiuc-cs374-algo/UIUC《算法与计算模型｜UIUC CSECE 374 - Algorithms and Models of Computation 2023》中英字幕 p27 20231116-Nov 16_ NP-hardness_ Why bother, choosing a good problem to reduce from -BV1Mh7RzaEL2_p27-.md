# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p27 20231116-Nov 16_ NP-hardness_ Why bother, choosing a good problem to reduce from -BV1Mh7RzaEL2_p27-

![](img/a56b1374809a5ff0be933b841b460f5d_0.png)

我是直歌。你这个证话来。

![](img/a56b1374809a5ff0be933b841b460f5d_2.png)

Okay。嗯，有好吧确定。在。你说。Okay hi everybody， thanks for coming out。

 especially you know it is the last day before break， it's gorgeous outside。呃。

I'm going to try to do you know one last one last talk about NP hardness and mostly what I want to talk about today is sort of。

High level strategy。How you approach NP hard problems when you want to prove that they're hard。

 go through a couple of examples， and I think one thing that I've seriously ignored here when I've been talking about NP hardness。

嗯。Is。Why are we doing this？Right， so。I don't think。That。

The idea of designing efficient algorithms needs all that much motivation you you know you know most of you。

 I hope are deeply enough sort of ingrained。In developing。呃。Code。

To solve some problem that you understand the utility of wanting that code to be correct and wanting that code to be fast。

So why do we bother to prove that certain things are hard yeah， sorry theres a question。Oh yep。

 sorry。There is still going to be a homework party tonight， but not on Saturday。

It's still in development， if it's ready in time， we will deploy it Monday after break。

 if it's not ready in time， then we might put it out late as like a thing to practice with。

 but then we'll be still dropping to GPS as when recalculating the final grade。表。

Other admin questions？Yeah。Yeah， everything， so if we do drop one GPS。

 then all the GPSs in the homework will be slightly worth slightly more。嗯嗯。

We don't want to raise that basically there's a cutoff of this much of the course is allocated to exams and this much of the course is allocateating non exams until we'll adjust in the non exam part。

Based on what actually gets assigned。Yeah。Y。是的。We're aiming to get midterm two back the week after break。

Um， u， whether it's early in that week or late in that week will depend on how things go。

But we the absolute deadline is like the Thursday after break。

 so it's you know still have one week after that before the final exam。

It means that all your Ts are going to be working over break。嗯。Okay。So worry about to do this。

The idea is。嗯。If you proof。problemble is going to be hard。U。Then that relieves you in some sense。

From the responsibility of coming up with an algorithm that is provably efficient and correct for all possible inputs。

Because if it's NP hard， such an algorithm almost certainly doesn't exist。

 so what this means is at some level you're trying to solve the wrong problem。😡，Now， it could be。

 you know。That。What you're actually doing is trying to solve the problem that you want。

 but you've developed a strategy to attack that problem and you've actually shown that wait。

 this strategy would actually imply an efficient algorithm for a subpro or a related problem or more general problem and so you should put that problem down。

 put that approach down。😡，And try something else another thing is to try to specialize。So。

You you already know that the traveling salesman problem is n hard？

So there's no provably efficient algorithm that solves the traveling spellssome problem for all edgeduated graphs。

On the other hand， if you happen to know that your graph is a DAg。

 then there's a simple dynamic programming algorithm that we' will find the heaviest path in that deck。

Okay， so if you examine the problem that you're attempting to solve and if you can make。😡。

Restrictive assumptions about the input based on the kinds of input that you actually expect to see in your application。

 often you can specialize。The problem from something that's NP hard to a special case that can be solved efficiently。

U。No。Another possibility is to say I don't necessarily want the absolute best solution to this problem。

Because that's going to be hard， in fact， what my application needs is not the best solution。

 but just a good solution。And so there's an entire field or subfield devoted to approximation algorithms where I could say。

 for example， for the traveling salesman problem， I can't solve to exact optimum the traveling salesman problem in arbitrary graphs。

 but it's relatively easy to get an answer that's within a factor of two of the optimal solution for the traveling salesman problem。

And then a little bit harder to get within a factor of three halves and then a little bit harder to get within a factor of four thirds and depending on the context。

 maybe you can drive that approximation factor as arbitrarily close to one as you want provided you're willing to spend more time。

And so maybe what you need is not。The absolute optimal solution。

 but something that's just provably close。Or something that's privateably close under some restrictive assumptions that you can reasonably justify based on your application。

Yet another version is。Rely on。Well， I guess one way to say this。Is。Build。Euristics。That。Work。

In practice。So now we're stepping away from the land of doing theory to something much more practical。

So in most。Instances of the traveling salesman problem that come from real geographic data。

 there are methods that work in practice， we don't completely understand why。

But there are ways of phrasing the traveling salesman problem。As for example。

 one way to approach it is to phrase it as something called an integer linear program。

And then there are techniques that for broad classes of inter linear programs。

Solve those things to optimality quickly。But when I say brought classes， this is not a theorem。

 this is sort of an observation that in practice these things can be solved quickly， yeah。U。

 so the question was， has any progress been made towards finding a polynomial time algorithm for any NP hard problem？

No， and part of the reason for that is nobody believes it's possible。There are very。

 very few people who work in theoretical computer science， I won't want say none。

 but very few who actually believe that P equals NPP。

Most people accept p is not equal to NPP is kind of a law of nature and move on。

Most effort to prove one who resolved the conjecture one way or the other have been devoted to showing that they're different。

Again， this is mostly， there's a bit of a self referential argument。

That suppose there were a proof that P is equal to NPp that would be readable by a human being。

Then because P equals NPp， it would be just as easy to come up with that proof from scratch as it would be to verify that proof。

But we haven't come up with that proof yet。So。If solving problems from scratch is just as easy as coming up with the proof。

We were verifying an existing proof。We should have been able to come up with a proof of scratch for that fact。

有。I'm not satisfied to that。在。So the theoretical computer science definition of a heuristic is an algorithm that doesn't work。

And if I'm being a little bit more generous， it's an algorithm that we can't prove works。But that。

We'll say things like here here's here's a reasonable heuristic for the the traveling salesman problem so let's suppose I。

And trying to solve the traveling salesman problem and I in the middle of my my algorithm I discover a tour that looks like this and I say well you know。

That's。Right， but let's look for some place where I can make。a small improvement。

 so if I cut these here， no not that one the other way。

Cut this here and cut this there and I erase those。Then now I've got a shorter tour。

So one greedy heuristic for traveling salesmen is come up with any tour you like。

 and if you can do this kind of swap with two edges going one way to two edges going another that makes the tour shorter。

Do it。😡，Now that heuristic is absolutely not guaranteed to find the absolute best tour。

But then you could say， oh， maybe I should look at swapping triples of  edges instead of pairs of  edges。

 and then you can make further improvements。And if you combine enough of these heuristics。

Sometimes you can actually reach the optimal solution。

 just not necessarily in a way that we understand。Under what circumstances this leads to optimallody。

Or even we don't necessarily understand when these heuristics lead to something that's approximately optimalim。

But in practice， they seem to work。You do it an actual experimental evaluation of the heuristic based on the data that you're actually going to be using and say。

 yes， this is good enough for our purposes。But then somebody else is going to come along with a different kind of data set。

And the same heuristics might not work for them。Yeah， so of them these kind like。Cared。Yeah， I mean。

 this is the swapping idea here is you know a fairly common sort of hill climbing heuristic。

 see if you can make things a little bit better， see if you can make things a little bit better see if you can make things a little bit better in the context of freeat for example。

 you've got this boolean formula and you're trying to make sure there's at least one true literal in every clause。

 see you make up values to the variables and you look through the clauses and some of them are satisfied and some of them are not so you say。

 oh well I'm going to pick one of the clauses that isn't satisfied。

 I'm going to pick one of the literals in that clause and I'm going to flip that value so now this clause is satisfied。

But now other clauses might not。So I'm trying to locally tweak the solution I have to make it better。

 sometimes it works， sometimes it doesn't。Sometimes it leads to something optimal。

 sometimes it leads to something only close to optimal， sometimes it wanders off chasing wild geese。

Um。But the pile of heuristics that people apply to traveling salesmen in particular。Actually。

 experimentally seem to work for basically every real world instance。

That we can give it in a reasonable amount of time。嗯。U。But。For your inputs。So the， I mean。

 all of these strategies actually are reasonable practical approaches to solving problems。

 even if you can't prove that something isnt Pe hardd。

 but you know the diehard theoretician who works in your office is not going to be like what I really want is an algorithm that just solves the problem。

 full stop， no assumptions n squared time。Complete optimality。

 that would be better than doing any of these。And you say， nope， 10 PRr okay， fine。

Let's do something else。Right， so。I think the other piece of this puzzle。Is you're sort of by by。嗯。

I'll answer your question just a second。嗯。TheThe other reason I think to to talk about MP hardness and get used to this idea is that you're taking problems that。

m at least the problems of the book， not you're starting to move in this direction。

 the problems and the homework， you're taking problems that look very different。

andtraining yourself to do transformations from one of these problems to the other。

 and this is also really useful for developing you know actual software you could say oh。

 here's this weird problem over there that I don't know how to solve but I know how to reduce it to this much more constrained。

 much more。Cryrisly defined problems， so I should try to attack that instead。Now。

 normally when you're developing software， you take existing subroutines and you build up。

 but being able to actually approach the solution to your problem by starting with the problem you want and reducing it to other problems which seems simpler。

 but you still don't know how to solve and reducing those to other problems that seems simpler。

 but you still don't know how to solve is also really useful。😡，Yes。The following traveling。

Fll that what。One characteristic of a map。That。That doesn an awful arbitrary graph is。

It must exist days unless you have ridges。Or tunnels。电方识唔死食出。Every graph can be embedded in space。

Oh oh yes， so it lives in a metric space and there is a triangle inequality。

 traveling salesman is still hard part with the triangle inequality。Um， yeah， I mean。

 there there are better traveling salesman still hard for graphs that can be drawn in the plane without any edges crossing。

Um，h， even when every vertex has degree three， there's a bunch， you know， they're very。

 very tightly constrained actually， where every vertex is an integer grid point and every edge has length one。

Traveling a salesman is still hard。So very， very tightly constrained versions of TSP are still hard。

 but those more constrained versions are easier to approximate。How much。好3。Well， like I said earlier。

 if you have the I didn't say if you have the triangle inequality。

 but if you have the triangle inequality， it's very easy to solve the traveling salesman if you're happy with something that's within a factor of two of the shortest solution。

You build a minimum spanning tree。And then you do a tour of the minimum spanic tree that that's a factor to approximation。

Um，Uh， if you're in the plane with actual geometric data。

 you can get within one plus epsilon of optimum for any epsilon in time that's like linear times of function that grows with epsilon。

😡，Yeah。So the question is about basically what do we know about how well appximable different problems are and the landscape is varied。

So on the one hand， there are problems where computing the optimum answer。

 which is always an integer， is NP hard， but if you're willing to be off by one。

 the problem can be solved in polynomial time。😡，So the correct answer is either delta or Dlta plus one where delta is the thing that my algorithm output。

 it's NP hard to distinguish between those two cases。

 but if you're happy to be off by one then you're done。On the other hand， the maximum clique problem。

 it's NP hard to distinguish between the two following scenarios。

 I've got a graph with n vertices and I promise you that there is a clique of size n to the 0。9999。😡。

Or I promise you that there is no clique with size larger than n to the 0。0001。

So either there's a clique that fills up almost the entire graph。

 or there is no clique that uses more than a tiny， tiny fraction of the entire graph。😡。

Just distinguishing between those two cases is the NP hard。

 which means there's no hope of any kind of approximation for the maximum C program。

So its and there's all kinds of intermediate things between those two extremes。Yeah。

So this is the nightmare scenario for theoretical computer scientists， maybe P equals NP。

 but the fastest algorithm for threeSAT runs in time into the Google。It's polynomial。

And there's a lot of sort of folk belief that this can't happen。

 well every problem that we actually ever care about really when we solved the polynomial time algorithm。

 has quickly been brought down to cubic time and then quadratic time and then maybe after a few decades near linear time。

That's not actually true， first of all， so there's no mathematical reason to assume that just because something can be solved in polynomial time。

 it can be solved in square time， so the nightmare scenario might happen。嗯。

I think people want to be optimistic and say， you know。

 its it's actually quite difficult coming up with problems where provably。

The fastest algorithm runs an end of the  tenth0th time。

There's certainly lots of problems where the fastest algorithm we know runs an end to the 10th time or into the 20th time or end to the seven digits time。

Um，h， and u the but the only cases we know where that's actually provably optimal is because you have to output a structure that can have that size。

if I have to output something that provably needs N cube bits to write down。

 then there's no way to run in less than N cube time。😡，Um， but most of what people， you know。

 theoretical computer scientists are interested in are problems where the output is a single bit or a single integer。

And then we basically don't know how to prove anything is hard。Whatever version of hard you want。

We just don't know how to do it。Oh。嗯。I think my favorite example of this is there's a problem called three sum。

Which is given a set x of integers。UAre there？Elements。A B C in x， such that A plus b plus C equals0。

Okay， obviously this can be solved in polynomial time for all A for all B for all C。

 do they add to zero and there three nested loops。There is。A relatively straightforward algorithm。

That can solve this problem in squared time。Again， it's pretty easy to see how to do this if you're allowed to use hashing。

 you don't need hashing。endcord time can be this problem can be solved in endcor time without doing any kinds of hashing tricks in 2016。

Somebody figured out how to solve it a little bit faster。And that's all we know。

So there's an open question， is it possible to solve this problem in this much time？啊嗯。Nobody knows。

This is much simpler than3at or TSP。Distinguishing。But。

 distinguishing polynom from exponential might seem like an easier thing because it's a bigger spread。

 but just distinguishing near linear time from quadratic time， we also don't know how to do that。

U and there's a whole parallel theory of reductions between three some hard problems and then there are other other families of。

 you know， these problems are all related and if we could only solve all pairs shortest paths and end the 2。

5 time we could do all these other things quickly if we could only solve the orthogonal vector's problem and something we could do all this other stuff quickly it's a huge study of sort of relative complexities of different algorithms。

All of which are sort of justified by if we could only solve this one quickly。

 wed get all those other ones too。嗯。And that in practice。Also lead to this sort of thought of well。

You're doing motion planning that's three some hard a。

 you don't have to be provably correct all the time。

 you just have to make sure that the insurance company is willing to ensuresure your robot。

They're reasonably confident you're not going to crash into the wall too often。Andng。

The other the other thing that I want to talk about is how to choose。What to reduce？From。

So but before I go on， there sort of any other questions about。

The motivation or a context that people study NPP hard for。O。What do we reduce from？Cook。

Leven theorem。Right so first of all， let me just give the definition of NP right so our NP heart the definition is。

X is NP hard。Means。If。We can solve。X in polynomial time。Then。P equals NPp。be。X here， so P formally。

 P and NP are actually sets of languages。😡，And you know the definitions are all done in terms of turing machines。

 but I think it's it's more useful to think of P and NP as families of decision problems。

 you give me an input that I'm supposed to say yes or no， true or false。Um and nothing else。

 but problems can be NP hard even if they're not decision problems， like maximum independent set。

What's the weather is the largest independent traveling salesman。

 what's the cost of the cheapest Hamiltonian cycle？

So X here can include other kinds of optimization problems， not just decision problems。

What Cook and Levin proved。Is。I think the right way to say this。Is three sat as NP hard。Okay。

 so what this implies。Is if。There is。A polynomial time。Reduction。From。Reset。To x， then x is NP heart。

哎。Suppose there's a polynomial time reduction from3 set to X。

And suppose I can solve X in polynomial time。The reduction then would give me a way of solving threeat at polynomial time。

But Cook and Levin showed that three set is NP hard， so I've just proved that peoples NP。

I assumed that I could solve x in polynomial time， and I concluded that p equals Np。

 that's the definition of x being NP hard。系。Now。嗯。Once I've done that。

 then I can use that new problem X as a new problem to reduce from so we can。Reduce。From。

Any NP hard problem。If we want to prove that a new problem is NP hard。

 so right off the bat we have three sat and really I should， you know。

 I think the original version of both Cook and Levin's proof actually went all the way back to circuits so we could say you could start with circuit as our target yeah。

No， if I want to prove that a new problem is NPp hard。

I can reduce from any problem that I already know as MP hard。Cook and Levin says。3 set is NP hard。

 so that allows me to reduce from three set as a way of proving something is hard。

So we reduced from freeat to maximum independent set。

That proves the maximum independent set of NPP hard。But now I can。

 if I want to prove something else is hard。largestrgest triangle reset set。

Then I can reach from max independent set。Instead of directly from3 sum。Okay。So。

We've got sat circuitat， different versions of this， we've got maximum cl。

We've got maximum independent sets。We've got minimum vertex cover。

We've got various kinds of coloring problems， so I want to assign three colors， the problem。

 can I assign a color， say red， yellow or blue to every vertex in a graph so that every edge connects vertices with two different colors。

😡，Um。So the simplest version of this that is NP hard is can I get away with only three colors？

One color is easy because they are there any edges， it turns out two color is also relatively easy。

 but once you get three or more colors， then things get hard。There's also， you know what you。

 the optimization version of this， what's the minimum number of colors I need or as graphorists would say。

 what's the chromatic number of this graph？Then I have various versions of Hamiltonian。

Cyclees or paths。And then I've， you know， optimization versions of this。

 like what is the longest cycle or the longest path？Or what is the traveling salesman。

 what's the shortest cycle that that is Hamiltonian？And then well， the two problems that you saw in。

Homework 10， problem one， those turn out to both be NP hard as well。

And so if I give you a new problem。Kon wants to ferry the souls of the dead from one side of the river sticks to another。

 but you can't leave anyone on the shore who might fight with each other because you're not allowed to fight and hell。

 what's the smallest boat that Karenron needs？Okay， I can use any of these。

Problems as a thing to assume that I have a black box for Karen's problem。

I can try to use it to solve any one of these things and the question is how do I choose which ones to reduce from？

😡，And so heuristically， you know this is not a hard and fast algorithm for choosing the right problem to reduce from because there is no such thing。

 but a reasonable rule of thumb。For this。So。If I'm trying to decide。

 I've got a collection of objects and I'm trying to decide which ones I should paint red and which ones I should paint blue。

Or what's the good， can I choose a subset that has some property to it？嗯。

Or can I move people on the left side of the room and everybody else on the right side of the room subject to some constraints。

 these are like setting variables to be true or false。😡。

And so this problem kind of smells like it might have something to do with bullolean satisfiability。

 so that might be a problem that's useful to reduce from。Yeah。

A lot of buying choices can be done with。An inequality optimization for。啊系。Number。So I you're right。

 but I want to point out that you're getting dangerously close to thinking about this。

 what we're trying to do backwards， yes， I can model binary choices by inequalities。

 but this sounds like you're trying to figure out how to solve the problem。

I'm not trying to solve the problem， I'm trying to prove that it's hard。

Right I mean this is still useful definitely to keep in mind that you can often phrase discrete things using inequalities just declaring your variables to be integers。

 this is the whole integer linear your programming thing。

But that's not necessarily the best way to think about the problem if I'm trying to prove that it's hard。

So maximum clickique and maximum independent set， when are those likely to be useful， well。

' trying if I'm not just trying to split and see if there is a good way of splitting up a set or a good way of choosing a subset。

 I want a subset that is large as possible， subject to some kinds of constraints。😡。

So the maximum independence sub problem is here is a graph， find the largest subset of the vertices。

That makes sure that any edge doesn't have both ends in that subset。

So if you can phrase your problem as I want to find a large subset subject to some constraints like there are no triangles。

Then maximum independent set or maximum clique might be something suitable to reduce from similarly。

 if I'm looking for a small subset。That satisfies some constraints。

Then maybe minimum vertex cover is the right thing to go for。U。呃。The coloring problems is to。

I'm trying to split a set into several subsets and you either say I have a fixed number that want I want to split everybody in the room into4s。

subject to some constraints， that's starting to smell a little bit like the four color problem。

 which is harder than the three color problem。Okay， so I should probably put that in three color。

Four color。Et cetera。But not too color。Or I want to know what's the minimum number of teams that I could split people in the room into that makes a good partition。

 whatever that means there's some constraints so when you color a graph and color the vertices red。

 yellow and blue， you're partitioning the vertices into the red vertices that have no edges。

 the yellow vertices which have no edges and the blue vertices with have no edges。😡，U。

So maybe coloring is the right thing to do looking for a Hamiltonian cycle or how longest cycle or traveling salesman。

 you're trying to find an order。啊。For the objects， so Hamiltonian cycles， can I order everything？

subject to some constraints， longest path is can I find the largest subset that I can put into some order traveling salesman is I can find the least expensive or most expensive or most valuable or heaviest or most glamorous ordering for these objects。

So a Hamiltonian cycle， or maybe I should say a Hamiltonian path in a graph is in some sense a permutation of the vertices subject to the constraint that adjacent things in the permutation are connected by edges。

 so if you're looking for an ordering for a bunch of objects，😡。

Or if that's what the problem is asking for， then maybe this is something that you can get from proof hard by using the reduction from Hamiltoniansism。

U。These are。Sort of questions about balance， so partition is not just can I split things into subset you knowq equal size subsets like three S。

But the objects have weights， and I want to make sure that am I actually going to get to say this。

 yes， I want to make sure that the two sides of the Ories mechanicique。

 Donalili Caral are actually balanced。Um。So if you want to do things like load balancing， scheduling。

 where you need to distribute resources that have costs to multiple agents or multiple consumers。

Then maybe you want to use something like。Partition。

 can I split these cardboard boxes onto two trucks so that each truck is carrying the same amount of weight。

 that's what the partition problem is really asking yeah。Sure。

 these are equivalent because I can take compliments， but the question is。

 do you want to spend a neuron on the word complement or not？You've only got seven neurons， remember。

 so you want to go as directly to the one that's closest to your problem as you can。3。So。

If x is in NP。There is a reduction from x to3s。The definition of NP hard is the thing in black。Sorry。

Then it's not an NP。嗯。If X is NPR， do we know that there's a polynomous time reduction from three set decks？

U。Possibly but I need to think about it， but I don't know why I would care。It then hand me now。Thank。

原发这个单子。你得。I probably forgot that。I don't know and I don't know why I should care。I mean， mean。

 maybe I don't understand your question。But it seems like you're asking。

Is NP hard space simple in the way that I want， the answer is no。

what do you share some subtle problems by the you think other？喂 no。

What do you can tell that problem in time that there's no problem to reduce it， but。

That and that think。Oh， I see what you're asking。So all of these NP hard problems。

 there's a chain of reductions eventually leading from freesat。

 so that's how we know these things are NP hard。😡，Threeat reduced to maximum independent set。

 which reduced to vertex cover， which reduced to Hamiltonian cycle。

 which reduced to traveling salesmen， which reduced to Mario Brothers。

That's how we know that Mario Brothers is NP hard。INo， not joking。嗯。The question is。

 could there be NP hard problems out there that can't be proved using this？Technique。Yep。

 there could be。No， then we just don't know that they're NPp hard。This is the technique that we know。

If there are other things out there that are hard that can't be proved using this technique， okay。

 there's a theorem out there that we don't know how to prove。当然在。That's we're ignorant。要。反正下。

Long stpo is not one of the empty hard problems，But as long as half is。NoThere are thousands。

 there are tens of thousands， there are hundreds of thousands of NPR problems on yes。

That's because when you get the final exam， we will make sure that you can reduce from one of the problems on that list that is not meant to be a complete list。

 it is meant to be a useful list。So allowed to reduce from longest cycle or yeah， fine。

 because you can reduce from Hamiltonian cycle to longest cycle in one sentence。

Is the longest cycle length and， yes， there's a Hamiltonian cycle， no， there isn't。So yeah。Yeah。

 in the exams， you can assume that 17 color is empty。Yes。NP hard， but not NP complete。

 maximum independent set。It's not in NP because it's not a yes or no question。

 an NP complete means NP hard and in NP。In NP， to be careful。

 what this means is if the answer is yes， then there is a proof that the answer is yes。

 which you can verify in polynomial time。The answer is five。Five is not yes。

 so is that's the right kind of thing。I mean， a more extreme example of something that's NP hard。

 but not in NP as far as we know。Is。Generalized generalized go， okay。

 so there board games all board games are solvable trivially in constant time because they you have a constant size of board。

 have a constant number of configurations of the pieces。

 you build a big lookup table and it tells you whether whether a given move is a winning move or not。

😡，But if you look at an end by end generalization of the board game， now the question is interesting。

 how hard is it to solve as a function of the growing board size？So checkerss chess go。

 other kinds of games that are played on roughly an N by in grid。

Depending on exactly how you generalize the rules are either。

Polynomial space complete or exponential time complete should sort of the next two big jumps up P andP exponential P space。

 exponential time。So generalized go is X time hard。😡。

And therefore P space hard and therefore NP hard。But nobody believes that it is only an NP there's no nobody believes that I can convince you on this end by N go board that you can win if you only do these things。

And I can check in time polynomial and end that yes， indeed， I will win if I do only do these things。

嗯。So there are further levels of difficulty beyond NP hard。

A really extreme example is formally the halting problem is NP Har。

If I could solve the halting problem。In polynomial time then P would equal to NP， yes。

 if I were the queen of England， then P equals NPp。from a false premise， you can prevent anything。

But there's no way the healthy problem is in NP&P。Okay so and there's there's there's one more thing that I want to I want to so there's this weird one。

 three partition， this is can you partition。Into sets。Of three elements each。All with。The same。

Some I really wish that the naming gods had called that partition into threes and not three partition because three partition sounds like can you take a set and split it into three subsets but the naming gods we're not kind this again is something that can be used for sort of load balancing things and I want you to go out on a limb here and I want you guess how do we prove three partition is NPR。

Think of the stupidest reason for choosing one of these problems that you can。

What should I reduce from？Yeah。Three set， why？Because it has a three in it as is exactly right。

So this is i'm dead serious， so these three problems here， three color three partition it has。😡。

A three in it。Works remarkably well as a heuristic for choosing what to reduce from。It's freaky。

All of these things， if I replace the three with the two， they become easy， all of these things。

 if I replace the three with an 11， they stay hard。There's something about two as easy。

 three is hard that seems to show up over and over and over again， and you know。

 it sounds like a joke。But I。I've seen this numerous times in research papers where they said something here that it looks kind of threeish。

 so let's just go to threeat。And it works。And if you actually look at the， I mean。

 it's also a little bit， there's a reduction from three set to three color in the textbook。

 which I hadn't had time to talk to talk about in class。

 but the number three plays very different roles in those two problems。

 so it's not like the three literals that show up in each clause somehow correspond to the three colors that I'm using to color the graph because there's more than one clause and there' but there's only three colors。

So it's weird， I don't understand why it works， but it does。Yeah。Re。嗯把这 three法。嗯。Yeah。

 you'd think that the word partition would be a clue， but the power of three is stronger。

Than the power of English words。I don't know of a reduction from the partition problem to the three partition problem。

Yeah。Thank two respond reduce from。Part谢tion。We can find participants learning into two groups of people。

Yes。That's also NP hard。And you can prove that by just throwing in one lump that has the right sum。

And now splitting your new subset into three， two of those pieces will be a partition of your original set。

And then you can do that again for four， five， six， seven， and so on。

You have to be a little bit careful if you insist on your sets being sets not multi sets， but yeah。

It's all fine。Yeah。Okay。So this is this is the this is the。

List of things that I keep in my head when I want to try to prove that something is hard there are other versions of this like if you can draw a planar graph it's something about moving around in the planar graph theres a there's a restriction of circuit set called planar circuit set where I can draw the circuit in the plane without any of the wires crossing that also turns out to be NP&P hard that you can reduce from that planar thing because it's planar can draw pictures and so great。

 I get to draw pictures of gadgets and I get to draw pictures of the reduction and preserve planarity and that restriction is really nice。

😡，嗯。But as a general rule， when I'm choosing a problem to reduce from。

I want to choose the most restrictive， the strictest。

 most constrained problem I can to reduce from because I don't have control over the input to this problem。

In this box that I'm building to solve whatever。some input is coming in。To。You know， problem A and。

I'm trying to prove that problematic X is hard。So I have no control whatsoever over this input。

 but I want to be able to reason as quickly and as efficiently as possible about what it means。

for the input to return， you'd say if this is a decision problem to return yes。

 or I want to reason as quickly as possible what it means for the correct output for this problem to be the number five。

So。Looking at a problem like Super Mario Brothers， which is NP hard。嗯。

Is probably not something you want to reduce from because the definition of the problem is kind of got lots of details that all have to fit together。

So I want to choose。U choosehoose。A tightly constrained。Constrained problem to reduce from。

But I have to consider arbitrary inputs。On the other hand， when I'm doing the transformation。Um。

 so just I'm doing yes， no transformation here when I'm doing the transformation。

I want to make sure that I encode the bits of the input that's certified that the input is good。

Or the bits of the input that certify the input is bad。

 but usually you want to think of it as being good。

I want to try to leave as little freedom as I can for where those features of the transform graph can be。

 so I need to consider arbitrary inputs。😡，For the problem to reduce from。

 but I'm building very special。Inputs。To the problem here that I have called X。We're。Trying。To prove。

Harart。So there is no responsibility， you do not absolutely need to and you shouldn't even try to consider all possible inputs to X again。

 the goal is not to solve X， the goal is to prove that X is hard。

 so if I can prove that a special case of X is hard。😡，Only for inputs with this very。

 very special structure， even in that very special case。

 the problem is hard then the more general problem is also hard and I do this by by in a sense。

Controlling as much as possible。Where the features of the transformed object that give me certify that there's a good input to the outer problem。

 so I'm being a little bit vague here， I think walking through one or two examples of this would be might be helpful。

 so I'm going to just spend the last 15 minutes maybe going through two examples of this。So one is。

This problem from the textbook。Let's say that a subset of vertices in an undirected graph G is half independent。

If every vertex in that subset is adjacent to at most one other vertex in that subset， yes。Yeah。

This is a reduction from a to X。And A is known to be hard。And x is trying to prove。That it's hard。

Okay， so half the depend set。Remember， an independent set is a subset of vertices in a graph where every vertex in that set has no other neighbors in that set。

 half independent means every vertex in the set has at most one neighbor。In that set。

 not at most zero。All right， so an example of this。Here is a graph。

And here is a half independent set。In that graph。哎。

So the red vertex on the left has no other the red neighbors， that's great。

 the red vertices on the right， each of those has one red neighbor， okay， that's not great。

 but it's still less it's still at most one， so this is fine。

If I try to add any more vertices to this set。😡，Then my set would not be half independent anymore。

 so if I had tried to add this vertex for example， it has two neighbors that are already in the set so my half independence condition would be violated。

诶。😊，So I want to show that it's NP hard to find the largest half independent set in a given graph。

So the first thing I need to do is choose a problem to reduce from。Any ideas？Generally。

 I want a problem that looks as much like this thing as possible， yeah。Great。

 I'm going to reduce from the standard maximum independent set problem。Okay， which means。

Building an algorithm。For。Max independent set。Graph comes in， integer comes out。

And in the middle of that， I'm going to have a black box for the max half independent set problem。

Graph goes in， integer comes out。And what I need to do is figure out a way of transforming G into H and transforming L into K。

 so this is the question marks are my job。this thing here in the middle。That is， you know。

 a magic black box device that I shouldn't try to understand。

I know it's magic because it has a rainbow in it。嗯。

Forgetting real rabows is red on the inside or is right on the outside。Okay， I apologize。

 this is an inverse rainbow。Um， whichch is appropriate because in the end。

 I'm trying to prove that this thing doesnt leave list， okay， good。U。All right。

 so I'm given some graph let's just I don't want my graph to be purple sorry Prince I'm given some graph G and I want to find the maximum independent set in this graph and and I want to reduce it to you know if there's an independent set in this graph G of a certain size that I want to know that there is a half independent set in H with some certain size so here's my graph G I want to transform it into some other graph H and so the way that I'm going to do this。

Is。I'm going to give each vertex in G somewhere for its other neighbor in the set to be。Okay。

 so I'm going to start with G and I'm going to add on。A little tail to every other。

Every node is originally energyng。this is my transformation， G to H。Yes。Okay。

 so I think I want to walk through the proof。Before I start talking about intuition。

 because really the intuition behind this is I want to make the proof work。

I can't talk about that without without showing you the proof okay， so let's go one way， suppose。

G has an independent set， let's call it S of size。Okay。Okay， let's pick these three vertices。Okay。

 well I'm going to transform Ss the certificate that shows that G is good into another certificate that shows that H is good。

 you're going to take these three vertices that are in the independent set and then I'm going to add on all of these little funky leaves。

诶。Now。This set of red vertices over here in H。Is half independent。The red vertices。

 each red vertex has at most one red neighbor。And that red neighbor is connected if a red vertex has a red neighbor。

 it's connected to that red neighbor along a red edge。😡，So none of the black edges get used。

So this is part of the reason why I thought let's attach new things。

 I want to make sure that when I look at a large half independent set in H。That at least intuitively。

 I can avoid using any of the original edges。In the graph。Okay so then H has a half independent set。

S union， let's call these leaves， these things， new vertices L of size。K plus V。Okay。

 so what I've just proved。Is that the maximum half independent set size of H is at least。

The maximum and independent set size。Of G。Plus， V。I'm trying to show two numbers are going to be equal。

 the first thing I need to do to show one is greater than equal to the other then I need to go the other direction。

嗯。😊，So this is the easy direction of the proof， but the real power of putting those extra places for this stuff to go is doing in writing out the only of proof。

 so suppose H has an independent set，😡，Let's call it S， sorry。It's called S prime of size。Oh。Okay。

 so the first thing I can observe is I know that this is going to be eventually what I want to prove is that G has an independent set of size L minus V。

😡，So this is really going to only be interesting。If El is at least V。So LH has an independent set。

Of size。L minus v。And if if I succeed in proving this。

 that will imply that the maximum independent set size of G is at least。

The max half independent set size。In H。Minus v。And these two inequalities match up。

The thing if I mean， I've swapped things around in order a bit。

 but what this implies is the maximum independent set size in G is exactly equal to the maximum half independent set size in H minus v。

 so this means this k is L minus v。That' this little box here just subtracts the number of vertices in the original input graph。

Okay， that's the goal， how do I approve this now the idea is I want it'd be lovely if I could say。

 oh， that that that that that half independent set in age。😡，UInclude every one of those leaves in L。

 those red vertices that I added to the graph when I transform gene to H， but I don't know that。

It'd be lovely if that were true。But I don't know if that's true。

So I need to argue a little bit about what happens。let's suppose that。嗯。呃。

So what if some vertex in these sleep is not in S prime？听。Well， there are two possibilities。

The this vertex v is is attached to another vertex that came from my original graph G that other vertex might be in S prime and it might not so on the one hand you have you know。

😡，Case one， this other vertex u is in S prime and。Case two， U is not in this prime。可以吗？So。

If I find that I'm holding a half independent set that looks like this where there's a leaf that's not in the set。

 but its neighbor is。What I'm going to do is modify。As prime。To include the， but not include you。

Now I've taken a half independent set and I've changed it。

 I need to verify that it's still a half independent set， all of the other red neighbors。

 all the other red vertices。Either the number of red neighbors didn't change or they lost this red neighbor。

 the only vertex that actually gained a red neighbor was this one。嗯。啊。That work。Oh。

 please tell me that that work。I think I have to do this to all lead simultaneously， I'm sorry。嗯。

If every leaf that's missing， I add it， and if its neighbor is not in e prime， then I remove it。

After I have done that， I get another half independent set。

 which is potentially larger than the one that I started with。But it contains every vertex in L。

So there's a bit of legwork to actually confirm that what I'm left with after this modification is a half independent set。

Then if I remove all of the leaves from that half independent set。

 what I'm left with is a set in G that is independent。😡，And it has the right size that I want。Okay。

 so I'm not necessarily guaranteed that a half independent set has exactly the structure I want。

But I can modify it without reducing its size so that does have exactly the structure I want。Yeah。

You could， but it's really hard to argue about something that doesn't exist。It's valid。

 but you will have a hard time making it work because it is hard to argue about a graph that doesn't have something in it。

Yes， and once you're proving the positive by contradiction。

 you're just proving the original implication。No， you're doing the same thing。

You're just adding two layers of contradiction， which we're reversing the polarity twice。

 you're confusing the polarity。😡，Yeah。I had at no time meant to or tried to imply that this half independent set that I built here is the largest independent set in the graph。

 half independent set， there might be a larger one。😡，I just built a half independent set。

If I build a half independent set of size 10， that tells me that the largest half independent set has size at least 10。

Right。All right， so that's as much as we have time for， thank you for your patience。

 have a great break， please try to actually take a break and we'll see you back here in a week and a half。



![](img/a56b1374809a5ff0be933b841b460f5d_4.png)