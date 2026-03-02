# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p20 -20-20_ Mixed Nash Equilibria and PPAD-Completeness).zh_en -BV1VmC2YzEXJ_p20-

So for the final lecture of the course， what I want to do is continue our study of the limitations of what is possible in equilibrium computation。

 both in the sense of what we can expect from quickly converging learning dynamics and also what we might be able to expect just with any centralized polynomial time algorithm So again。

 just to remind you of sort of the big picture a couple of weeks ago we had these totally sweeping results course correlated equilibrium and for correlated equilibrium。

 any game at all， we can compute them in polynomial time and people can learn them in a distributed way using no external or no swapwork algorithms respectively for pure Nash equilibriumria。

 we've been studying those we studied those for routing and congestion games。

 we had very limited positive results and on Monday we developed the theory of PLs completeness to explain the limitations of our positive results for pure NH equilibrium。

Now for mixed naash equilibrium， where players can also randomize at the moment。

 we only have again pretty limited positive results。

 we showed that for two players zero sum games mixed Nash equilibrium are tractable so two players and where one players pay off as the opposite of the other that can be solved with linear programming or what we did in class will solve it using no external regret algorithms And so the obvious question is you know what about mixed Nash equilibriumria in more general cases for starters let's just say still two players。

 but not necessarily zero sum so so-called by matrixtrix games And so the plan for today is to develop again the relevant complexity theory explaining why we don't have stronger positive results than what we already know。

So formally， we're thinking about the following computational problem。So again。

 it's a two player game， but just not necessarily zero sum。 so rather than just one payoff matrix。

 we need two payoff matrices， so two M by N matrices， A and B。

So there's a row player and a column player with M and N strategies。

 A is the payoffs of the row player， and B is the payoffs of the column player。

 So zero sum would be the special case where B equals minus a。

And the goal is to compute a mixed strategy。 N equilibrium。 Alice will discuss later today。

 There's going to be at least one for sure。 There may be many。

 And I just want to give you the easiest equilibrium computation problem of the mall， which is。

 give me any。 I don't care which one。 Any other problem about national equilibrium is only going to be harder than that one。

So， compute。Mix strategies。X hat for the row player， Y hat for the column player。

So that the row player can't do any better， given what the column player is doing。

So if for any other mixed strategy it might consider。Keeping why hat fixed。It can only do worse。

 This is for all mixed row strategies， X。And similarly， for the column player。Sorry， B。

The column players' payoff should be at least as high under Y hat as it would be any under any other。

Mixed column strategy Y。Okay， so that's the goal。 This is the input， this is the desired output。

 and that's the computational problem we're going to study today。So。Here's a fact。Fact is。

 we don't know how to solve this problem efficiently came polynomial time。So to date。

 there is no known polynomial time algorithm。Okay。And a lot of very smart people have thought pretty hard about this problem。

So， you know， as usual， once you're stuck in the algorithm design for days or weeks or years or decades。

 you start wondering if one of these algorithms doesn't exist。 and you wonder how you might argue it。

 And again， we're not going to hope to prove an unconditional result。

 just proving flat out that there is no polynomial time algorithm that would separate P from NP。

 but perhaps you're going to have some notion of completeness saying that this problem is as hard as every other problem in a large class。

 so that's going be the plan for today。 we're going to develop the relevant complexity theory again。

 a suitable analog ofmp completeness to a mass evidence why this is actually an intrinsically hard problem and there will never be a polynomial time algorithm。

One， I guess quick aside。If you're starting from the special case of two players in zero sum。

 which we know is tractable。What I did is I said， let's keep the two player and let's make this general。

 A different sort of baby step you could try to do is you could keep the zero sum and you could bump up the number of players to three。

But actually， I claim that three players zero sum games are going to be at least as hard。

 at least as general as two player general games。 Does anyone see what。That's right。 So basically。

 any two player game you can embed in a three player0 sum game。

 Just add a third dummy player with just one action whose payoff is the negative of sum of the other two。

So we're actually really looking at in some sense， you know， the next baby step， okay。

 for national equilibrium computation， keeping with two players， but looking at general sum。

 and that problem already is hard in a sense we'll discuss today。All right。So。

The really tricky question with this very simple computational problem or simple to state computational problem is if we think this is a hard problem。

 and you， we're trained， we have some training and complexity theory。

 So we know that probably means complete， in some sense。

 what would be the right complexity class for which this problem is complete。

And this is tricky answer。 I'll give you the answer today。But it's going to take most of the lecture。

And it took， you know， really， the leading thinkers in the field a number of years to。

 to figure out the right answer to this question， okay。So I'm going to develop it sort of slowly。

So what I want to do first is I want to explain in in a formal way why N completeness is not the right notion for computing mixed strategy as equilibrium。

 Okay why that's too strong a statement to try to prove。

 And that argument will hold equally well for the P L S complete problems we discussed on Monday。

 because it's also going to justify our development of this analog。

 this weaker analog of N completeness， P L S completeness from Monday。

So let's think about what it would mean to try to prove that the problem of computing a mixing national equilibrium is NP complete。

So first， just sort of a type checking issue。 So when you normally study NP problems。

 you study decision problems。 The answer is either yes or no。For equilibrium computation。

 the way I phrase the problem， I don't you know， I really want the equilibrium itself。

 I want the answer。😡，So let me first define rather than NP， the class FNP。

It's just a very simple variation。 So the F stands for functional。

So this just means instead of a yes， no， if it's a yes instance， I actually want an answer。 Okay。

 so for SAT， I don't just want to know is it or is it not satisfiable， if it is satisfiable。

 show me a truth assignment。 Hamiltonian cycle。 if there is a Hamiltonian cycle， show it to me。

 So that's FNP。So all NP search problems is what they're called。Okay。

So in the abstract and MP search problem， you're just given an instance。X of an NP problem。And again。

 just an MP problem you can think of is there is an efficient verifier to recognize alleged solutions。

SAT Hamiltonian Cycle what have you？And the output。So if there is a solution。

And solutions should have polynomial length in the instance's length。So if there is a solution。

 a polynomial。Solution。In this context， solutions are also called witnesses。偶尔。You know， obviously。

 if it's an unsatisfiable assignment， you can't show me a satisfying truth assignment。

 you should just correctly report no。No， if no solutions， okay。

So it's just the analog of decision problems where if there is a solution， I want it。All right。

 And so again， this is to sort of tight check with equilibrium computation problems where I'm not asking you something like does there or does there not exist in equilibrium。

 I'm saying， give me one。Alright， so。So for example。

The functional version of satisfiability is complete for this class FNP Cooks theorem。

 if you look at it actually establishes a bijection between satisfying assignments of the three set formula。

 That's the output of the reduction and witnesses to the NP problem that you started with。

 So that's just a complete problem。Let me also point out just to relate this to yes。

 Monday's lecture。That PLS， so the local search problems that we discussed on Monday。

Are naturally thought of as a subset。Of FNP。 So remember a PLS problem I give you these three algorithms that are the minimal ingredients necessary to run local search。

 and the definition of the computational problem for PLS is give me a locally optimal solution。

 So again， the output is supposed to be a solution itself。Now， for FNP。

 sort of you're asking very little of the verifier So when an NP problem。

 all you have is a subroutine at your disposal， which given an alleged solution that says yes。

 that's satisfying or no， that's not satisfying PLS。

 you actually know it's in some sense easier in that a PS problem has extra functionality in the verifier right so if I'm looking at say a cut in maximum cut and it's not locally optimal。

 not merely does the verifier say no， this is not a locally optimal cut。

 it also suggests a better cut for me but if we just ignore that extra functionality in the PLS problem。

 we just see it's an FNP problem。So the correspondence here is you know， witnesses。

And the NP sense correspond to local optimum。Of the PLS problem。And the MP verifier。

 which is only responsible for saying， yes or no it is or is not a solution， is or is not a witness。

 this is already done by our third algorithm。Of the PLS description。

 the third algorithm was the one that either said locally optimal that that's equivalent to verifying that it's a witness or it gives you a better solution。

So local search problems can be thought of as members of this search class， FNP。Also。

Problem we're talking about today。So I'll just write ME for the computational problem of computing a mixed national equilibrium of a given by matrixtrix game。

This is also。An FNP。And so proving that really just boils down to proving that you。

 if I showed you a naash equilibrium， you could verify that it was one。 Okay。

 so if I give you a strategy for the row player， a distribution similar for the column player。

 you can in polynomial time， either say， yes， this is a mixed na equilibrium or no。

 this is not a mixed Nash equilibrium。 That's what this statement really means。Okay。So， you know。

 why is that true？So suppose I handed you these two probability distributions。 Well。

 you would first adopt the row player perspective and you'd say。

 well is the row player doing the best thing it can do， given what the column player is doing。

 So how would you do that， while you just look at each of the rows。

 you computed expected payoff of each of the rows given what the column player is doing and the best response of the row player has to be mixing over all of the pure best responses。

 So you maybe you have three rows and their expected payoffs or 17。

17 and 12 and as long as you're mixing only over the first two rows， that's the best response。

 that verifies the equilibrium condition for the row player and similar for the column player。

So that's not hard to do。So's a reason。XY， so notice' the reason I did that argument。

Is because sort of naively， if you look at the equilibrium conditions。

 you might get a little nervous because we have a for all overall probability distributions。

 which is an infinite set。 But the point is it just suffices to check all pure strategies。

 the finite number of pure strategies available to each player okay。So。X，Y。

There's a mixed nach equilibrium。If and only if each player。Uses， or let's say randomizes。

Only over its pure best responses。Okay。ButAgain， the point is。

 given an alleged mixed na equilibrium of a biometricx game。

 you can efficiently check whether it is one or not。 That means this is an FMP problem。

So when you're trying to prove somethings intractable。

 you want to prove it's at least as hard as as many problems as possible。

 So the more problems it's at least as hard as， the stronger evidence of intractability。

So this problem is inside of FNP。 Okay， so the hardest imaginable result we could think about is it's as hard as every single problem in FNP。

 It's not going be harder than that， because it lies inside this class。

So if we're feeling ambitious on the negative results side and we don't believe there's an algorithm for mixed naache equilibrium。

 we could show we could argue that， well， if there's a polynomial time algorithm for this。

 there's a polynomial time algorithm for everything in FNP， for example。

 for the functional version of S。 So that would be a way。

 that would be sort of the first cut way we might try to establish intractability for this mixed na equilibrium problem。

It's a question。Could it be？FMP competes， could it be that every single problem in FMP。

 like for example， SAT reduces to the problem of computing a mixed N equilibrium？

Thatd be the first thing you try。 And the answer is， no， at least。

There's strong evidence that the answer is no。In the following sense。So in this form。

The theorem is due to megito and Papami true。Only。Okay， so they don't give an unconditional answer。

 It might be。 it might not be。 but if computing mixed national equilibrium is FMP complete。

 there are some extremely surprising consequences。So only if。NP equals co MP。Okay。So， only if。

Problems whose yes instances can be efficiently verified also admit efficient witnesses for their no instances。

 So this is， this is not as strong a collapse as peak was NP。 But I mean， again。

 this is something that just would surprise everybody。 So just to get a handle on this。

 So instead of satisfiability。 think about unsatisfiability。Okay，So's unsatisfied。

 So basically I'll give you a three set formula and I'm asking you， is it unsatisfiable？

So that's a co MP complete problem because that is N complete。 So if N B equals co MP。

 that means you can efficiently verify there exists some short proof of unsatisfiability。

 which can be efficiently verified。So if a SAAT formula is satisfiable。

 you can certainly convince me very quickly。Just show me the satisfying formula。

 I don't know where you got it from， but if you found it， I can verify it。

 What if you wanted to convince me that there wasn't a satisfying truth assignment。

And there's two to the n possibilities， of course。 So how would you convince that none of those two to the n work for this formula。

Could there be some sort of way to compress that too to the n amount of information into something that's polynomial length that I can quickly verify。

Well， we don't know。I mean， that's tantamount to asking his MP equal co or not， so we don't know。

 but we don't think so。Okay， so NP equals Co NP would mean in particular。

 there's short certificates for unsatisfiable formula， okay， which we don't believe。

So the claim here is that if。Right， so remember， we're trying to prove intractability for Magna Libia。

 And we're starting out sort of asking， what's the strongest statement that might be true。So he said。

 well， it's an F problem。 So the strongest statement that might be true is that it's FNP complete。

 And this is asserting， that's probably a little too much to shoot for。

If you successfully prove its FMP complete， you've actually shown that MP equals CoMP。

So the moral of this theorem is you should set your sites lower than proving FMP completeness of mixed national equilibrium。

That's the role this plays in the current narrative。All right， so the proof is not hard。

It's a bit of a mind bender， but it's not hard。So let's assume we did prove。

The mixed naturally equilibrium was FMP complete。 I supposeupp it were true。

So assume there is a polynomial time reduction。 And so these are search problems。 So a reduction。

 I mean， in the same sense as for the PL S problems。

 you have an algorithm that hass instances to instances and then a second algorithm that maps solutions back to solutions。

So suppose we have a reduction from FMP complete problem， like satisfiability。

To computing mixed Nash equilibrium。So what would that mean？So that is。

So we have the first polynomial time algorithm that maps instances to instances。Okay。

 so it takes us input some SAT formula。And it outputs a game by matrix gain。And two。Right。

 the second part of the reduction， just like on Monday。There's a polynomial time algorithm B。

That maps solutions here back to solutions here。Okay。

 so a solution on this side is going to be a mixed na equilibrium。 right， That's our target problem。

What's the solution here， Well， if this is satisfiable。

 then obviously the solution should be a satisfying assignment。 if there's no satisfying assignment。

 then you know， just the string no is going to constitute a solution。So basically。

 given a correct answer of the B matrixchema mixed national equilibrium。

 we get a correct answer to the FAT problem。So again， this is just we assumed。Okay。

 we're assuming that there exists a reduction from satisfiability to computing mixed natural equilibrium。

 This is just what that means。 Okay， reduces means that these algorithms A and B exist run in polynomial time and satisfy those properties。

 That's a definition of a reduction。So let's assume that those algorithms actually exist。

 And now let's conclude that MP equals Co MP from that assumption。Well。

Think about the case where fee actually is unsatisfiable。So in the latter case， meaning case B。

I claim that this mixed natch equilibrium， y。But a mixed na equilibrium Y of the game A of V constitutes a short。

 meaning polynomial length and efficiently verifiable proof of unsatisfiability。

So in the latter case。Any mixed N equilibrium Y of the game， A of P。Okay， so why is that true， Okay。

 so suppose we have this formula fee， And you want to convince me that it's unsatisfiable。 Okay。

 and again， remember， we're assuming that this reduction exists。

 So these polynomial time and correct algorithms A and B exist。 Okay， they're out there for my use。

So then you want to convince me fee is unsatisfiable。 So what do you do， How do you prove it to me。

 You say， here's a mixed Nash equilibrium， Y。Okay， here's a pair of probability distributions。

 So I have my formula fee。 You give me a pair of probability distributions。 Okay。

 So here's how I check。So first， I run the algorithm A on my formula feet。 It spits out a game。

 I can verify that the distributions you gave me are a mixed national equilibrium of that game。

 A of P。And then I can just run this algorithm B on this mixed na equilibrium and check that the output is no。

If both of those two things check out by the correctness of algorithms A and B。

 this is a proof that fee is unsatisfiable and it's shortened efficiently verifiable。

 so that gives us the NP certificate of a Co&P complete problem。Now， again。

 don't forget why I did this， What was the moral。The moral is。

 we set our sights too high in thinking about proving mixednash liver is FM complete。 Okay。

 it's actually not that hard。 It's not as hard as all FM problems under the assumption that MP and Co MP are different。

 So if you want to prove it's as hard as some complexity class。 FMP is the wrong one。 It's too big。

 We need something that's smaller。So quick comment。This exact same proof。

 if you look at what we used about the mixed N equilibrium problem， This proof you know。

 is not very specialized to computing mixed Nash equilibrium。

 The only property of the problem of computing mixed Nash equilibrium that it used was that solution was guaranteed to exist。

 okay。So there is no way the answer was no to the bioMax game problem。

 And we'll talk about the proof of that later。 Okay。

 but Nach's theorem says you always have na equilibrium。

 so there always exists at least one witness to the computational problem of finding a mixed na equilibrium。

And given such a solution， you can efficiently verify it。 Given just those two properties。

 this proof works。So in particular， for these PLS problems okay where witnesses correspond to local optima。

 that means we know for a PLS problem， there's always a witness。

 there's always a locally optimal solution。 you can just run local search till it stops So again for any problem in PLS there's no way that problem is NP complete either unless NP equals coNP so I didn't say this Monday I wanted to give you a warm up first but we really needed PLS completeness on Monday for local search。

 N completeness was just too big a class。 It was not well suited for the local search problems。

The same proof。Applies to every。FMP problem。Guaranteed。To have witnesses。Including， for example。

 not just mixed na Gliia， but also all of PLS。And so this subclass event again。

 contrasts this with satisfiability， right， you know， a Sa formula does not always have a witness。

 There's not always a satisfying assignment。 There's other possibility the answer is no。 Okay。

 for P S problem， there's no possibility the answer is no。 There's definitely local optimum。

 for mixed national equilibrium， there's no possibility the answer is no。

 There's definitely an Ash equilibrium。 because there's really a difference。

So this subset of FM problems where you always have at least one solution is sometimes called。TFMP。

For total FMP。对。So I apologize for the increasingly long acronyms， it's not my fault。

I was born too late for any of this stuff。Good。So。The picture， then。The complexity class landscape。

So we have these local search problems。And we observed that local search problems， of course。

 always have at least one witness， there's always one locally optimal solution。

There's other problems like。The one we currently care about。

Computing a mixed strategy in Ash equilibriumria， The shirt doesn't feel like a local search problem。

 So I'm not going put it in P， L S。 That seems sort of weird。But it does always have witnesses。

 I'm going to put it in TFNP。Okay。And then FMP is strictly bigger。So again。

 SAT would be something thatd be an FM， but not TFMP。

And so we argued that by virtue of computing mixedna equilibrium being inside TFM。

 there's no way it F's no way it's MP complete。 Okay， unless MP equals co MP。 So this set。

 this hourmost set is too big a class to prove that mixedna equilibrium is as hard as everything in there。

So the next obvious thing to try。 Well， maybe mixed N Lib is as hard as everything in TFMP。 Okay。

 maybe it's as hard as any other N T search problem。

 which is always guaranteed to have at least one witness。So shooting our sites is a little bit lower。

Refin goal。Maybe we should try to prove。But M E。Is。TFMP completes。So as hard as any other problem。

Which is an NP search problem guaranteed to have witnesses。嗯。How would you prove it's in PLS？Well。

 for all， we know everything is equal to P。So I can't unequivocally say it non Ps。

But it sure doesn't。 I certainly have no idea how to find a mixed na liver I'm using local search。

Yeah。Okay， so this seems totally reasonable then。So the reason we can't prove it's NP complete is because it always has witnesses。

 So let's just prove it's as hard as any problem that always has witnesses。

So this is not what we're going to do。准。We don't know how to do this。And here the obstacle。

It's a little more wishy washy， but still， it's a real obstacle。

Which is we actually don't know any complete problems whatsoever for this class， TFMP。

Is we have no cooks theorem for TFM。And we don't really expect one。So let me try to explain。

 although the only argument there is for this obstacle is conceptual， it's not mathematical。

So think about the complexity classes， which do have complete problems。 Okay， So obviously。

 there's MP completeness。 But there's other ones you've probably heard of。 You can be P complete。

 you could be P space complete， for example， okay。So what do these classes like PNP and P space。

 what property do they share that something like TFMP does not？Well。

 so how do you know that a problem is a member of P or NP or P space。

 It's sort of a very simple reason， It's because it's accepted in some kind of particular machine model。

 T machine that runs in polynomial time and nondeterministic turninguring machine that runs in polynomial time。

 polynomial space， whatever。 so this is really kind of simple generic reason for membership at the complexity class。

 which is just being accepted by some very specific competition machine model。Now。

Membership in TFMP is not。 I mean， we don't know of any proofs putting problems in TFM that go via acceptance in some kind of machine model。

 Let me give you an example。So the claim here。And again， this is not really mathematical。

 but just there doesn't seem to be a generic reason for membership in TFMP。So concretely。

 if there's time， we'll discuss it。 But the reason why mixed naash equilibrium is in TF M is because there's always going to be a mixed na equilibrium。

 That's Nash's theorem。 from a long time ago。The way Nash proves that theorem is basically using topology。

 it boils down to a fixed point theorem。 So that's one branch of mathematics。

 That's the reason that the M E problem is a member over here。

me tell you another problem that's in TFMP。So， factoring。So Ill give you an integer。

And the output is supposed to be the unique factorization of that integer。

So it's not hard to prove that any integer has a unique factorization， but， you know。

 it's not a fixed point argument， right， It's sort of algebra slash number theoretic。

 This's different branch of mathematics。So different problems。

 computing mixedN equilibriumria or factoring wind up in this TFMP class for totally different reasons that don't really seem related to computational models。

So the only reason we know of of having complete problems。

 which is this generic membership by accommodation models， is not how TFM is defined。Okay。

 so that's why we don't expect to see complete problems。

 Sometimes you hear problems like TF MP called a semantic class。

And problems like FM is syntactic class， where syntactic just means， again。

 you can write down a machine model and the languages are precisely those accepted by these machines。

 And if it doesn't have that kind of definition， like TFM， then it's a semantic class。

So no generic reason for membership。EG mixed na equilibriumlibria。Versus factoring。

Could there be a common mathematical argument about why both of these problems are TFMP problems。

Maybe， but we have no idea what it would look like。

 We don't necessarily expect there to be one either。Okay。

So that's why we're going to site set our site still lower than improving TFM completeness。

 We just don't think that's a good way to go。Based on experience。So here's the idea。

 So this is sort of where Migito and Popa Dimitri left off。

 kind of observing that there was this hard conceptual issue。And so the next chapter of the story。

It was written by Papa Dimiu。And here was his idea。 He said， well。

So let's actually look at a still smaller set of problems So identify subclasses。Of TFmpP such that。

You know， first of all， this should be interesting， not trivial。

 it should contain problems that we care about。Not known to be NP。

Like the problem we're currently obsessed with computing mixed strategy a equilibrium。And two。

They do admit complete problems。And again， half complete problems we're sort of identifying with as having a generic reason for membership as being specified by acceptance in some kind of you know。

 precisely described computational model。So this is the idea we're going to pursue。So。

We've actually already done this。We've actually， on Monday。

Spent the whole lecture discussing a subclass of this type。

Just remember the two properties I just covered up。 So first of all。

 they should be subclasses of TFNP。 so there problems that always have at least witness， one witness。

There should be problems that are not believed to be in P and there should be complete problems。

 and PLS on Monday satisfied all of those properties。Again where witnesses correspond to local opt。

You always have at least one， so it's a subclass of TFNP。

It has problems that we don't think are in P， like finding a locally optimal solution of a max cut instance with general weights。

 And it had complete problems。 we talked about that on Monday。

And the reason it has complete problems is。You know。

 the description was a little more complicated than for NP P or something like that。 But still。

 when we defined a P L S problem， I just defined it in terms of these three polynomial time algorithms。

 A， B and C。 Okay， so an N P problem， I only need one algorithm。 the efficient verify for P L S。

 I needed three， but still a problem was N P S。 if and only if it could be described as the locally optimal solutions of the local search process induced by these three algorithms。

 Okay so we had to work harder， but it still was a syntactic class。 Okay。

 I just wrote down the Turing machines that induced the problem。Okay。So we need a analog of P。

 L S for mixed Nash equilibrium。 And it's going to sort of introduce it kind of by a via metaphor with P L S。

So local search， it's not hard to imagine local search as just following a path through a dag。

 through a directed acyclic graph。We're in the graph。Nodes just correspond to feasible solutions。

So you can think about max cut as a particular instance so I give you some graph with n vertices。

 there's basically two to the n cuts， two to the n feasible solutions。 Okay。

 so this kind of metagraph is going to have two to the n vertices Okay， it's a big graph。

So nodes in correspondence with feasible solutions。And then edges correspond to improving movess。

So in Max cut， for example， this there'd be an arc from one cut to another。

 if they differ in a swap of exactly one vertex， and if the head of the arc has higher weight of the cut than the tail of the arc。

And so。That induces a dag。So again， nodes here correspond to feasible solutions or cuts， if you like。

And Arcs corresponded to with an improving local move。And so， the objective function。

Just keeps improving as you follow path through the DAG。

So a local search you can think of this way if you want， obviously。

So why does local searchL terminate， well， because if you're in a dag。

 there's no cycles and if there's a finite number of nodes。

 eventually you terminate at a sink and the sinks of this dag just correspond to the locally optimal solutions？

So， again， the reason I sort of want you to think of P。

 L S this way right now is to introduce by analogy。A complexity class called PPAD。Which is similar。

But different in the details。T PLs。So it turns out to be relevant。

For the problem of computing mixed strategy， N equilibrium。Is PPD。

So many people have noticed that the complexity class P P A D was defined by somebody named Papa Dimitri and sort of wondered about。

That。Allegedly。PPAAD stands for Ponomial parity Argument directed version。But if you believe that。

 I've got a bridge to sell you。So the picture in PP8D is not a dag。

It's instead directed paths and cycles。So。So remember。

 a local search problem specified by these three algorithms。

 The first algorithm tells you where to start。And the third algorithm tells you which arc to follow next。

 and you can use the second algorithm to verify that you're making progress。

 improving the objective function。So PPD problems， are're never going to actually write down the three algorithms。

 but the flavor is exactly the same。 There's going to be three algorithms。

And the first algorithm again， just here nodes again are feasible solutions。Or you know。

 some sort of solution space。 And the first algorithm tells you where to start。 Okay。

 so there's going to be some starting point given to you by the first algorithm。

And there's again going to be a third algorithm that sort of tells you which arc to go on next。

 if you want to proceed。And the PP8D picture。Is it's going to be a directed graph with in and out degree of most one everywhere。

 it's going to be paths and cycles。And there can be cycles。

And there can be past that you can't reach from the given starting point。

That's the same as local search。This is different than local sorts。 fact that there are cycles。

 So the in degree and out degrees at most one。 And also。

 it's going to be the case that this source has in degrees 0。whichch means you can't loop back to it。

Alright。So in any such graph， if you start from the end of one of these directed paths。

 you just follow it at some point， you'll get to the end。Okay。And that's guaranteed to be a witness。

 that's the definition of a PPD problem。So in local search。

 the definition of a PL S problem is in effect that you're given a dag， you're given a start point。

 you're given a way to follow arrows， and you're going to terminate it a sync。

 The definition of a P80 problem is， again， you're given three algorithms。

 The first one tells you a start point， the third one tells you where to go next and you're guaranteed that if you follow it long enough through a possibly exponentially many note nodes。

 it's not solely polynomial time。 but you're guaranteed that if you just keep following the arcs。

 you'll terminate at a witness。So that's the， this is。

 this is the sort of impressionistic version I want you to keep in mind of PP D。

So there's no objective function。But nevertheless， it's going to be a guaranteed termination point。

Okay。Yeah， question。How do you have cycles and？BecauseHow would you move into a cycle， you can't。

So it would only be if I somehow magically teleported you there。You would loop。But again， remember。

 so let's go back to P， O S though。 Remember。 So what's really hard about sort of the complexity is。

So' what's relatively easy to prove is that if you if you insist on finding a local optima by doing local search。

 it takes a long time。That we know to prove actually。

 we just have unconditional exponential lower bounds for local search。

 what we really don't understand is whether or not there are other clever algorithms that just zoom around the search base and ignore the structure of this graph。

And so the same question is true here， right， So basically， in some sense， you know。

Unconditionally proving that you can't solve nationalash equilibrium in polynomial time is more or less tantmount to saying there's no way you can you know。

 shortcut this possibly exponentially long path。 So it's conceivable Some other algorithm。

 not just to the generic one would care about this part of the search base。 But yeah， I mean。

 intuitively， I mean。This is the problems have this property。

 but you're absolutely right that the generic algorithm would never see it。对。Okay。Good。Right， so。

So the generic reason。For PPD membership。Okay， so remember， we have a few criteria here。

Right so the plan was to have subclasses， so first of all， they should be in TFNP。

And then they should have interesting problems。And so this one's going to have mixed nalyus。

 That's going to be an interesting problem， and they should be syntactically defined。

So in the same way， that。Following a path through a dag can be syntactically defined using those three algorithms。

 so can following a directed path like this。So solvable。By following。A directed path till it ends。

Okay。And as far as this syntactic definition， I'm not going to say more today。 Okay， it's。

 it's exactly the same flavor as on， as on Monday。 And if you want the details， you can look at the。

 you can look at the supporting reading。What I want to spend the time on instead is just trying to convince you why you know。

 this directed path picture has anything to do with anything we might care about。

 which is completely not obvious。Alright。Okay， so this definition should seem this P D definition should seem obscure。

And so in particular， what you should be wondering is。

 what does this have to do with mixed Nash equilibrium？

So you should believe me that this can be syntactically defined。 It is a subclass of TFM。

 It's guaranteed to have solutions because this is guaranteed to terminate at a solution。

 You shouldn't know why it's interesting。So let me tell you about the canonical。PP80 problem。

Which is something called Spurner'slemma。So let me just tell you about this problem。

 sort of standalone first。And then I'll hand wave about what it has to do with Nash equilibrium。

But for the moment， this is just going to be comminatorques。It's a Spurner'slemma。

So we're going consider a simplex aya triangle in the plane subdivided some number of times。

So there's going to be a notion。 So Sperner'sle states that if you take a subdivided simple X like this。

And you color it， you color all the nodes， red， green， and blue。Meeting certain boundary conditions。

 then no matter how it was colored， there's going to be a small simplex that is trichromatic。

 whose three corners have the three vertices。So， so what are the boundary conditions。So each corner。

It's a different color。On a side of the triangle， it's only allowed to have the two colors of the endpoints that it bounds。

So I could do something like this。Here I could do something like this。Here I is something like this。

And the in vertices can be colored arbitrarily， any of the three colors。谢你。

Trrack chromatic triangles。それが。Any others？How many total？I think there's probably five。Okay。Okay， so。

 all right， so here's one coloring where there's a trichematic triangle。

 But why does there have to always be one okay。And could we have a systematic way of finding one。

So it turns out， both proving the existence of the trimatic triangle and finding it reduces two following paths in a graph exactly like that。

And the reason is。Let's。Put a node。 So we're gonna superimpose a graph。

And it's going to be a node for every face。And we're going to have an edge。

We need to pick two colors。 So let's say red and green。I we're gonna have an edge。Whenever。

We have a red green。Ark。Agr。Anymore should be more of it here。Here。Sure。What's up。

 or did I oh I messed one up didn？That's wrong， actually。Any more？けど？Okay。

So there should be a correspondence between the nodes of degree1。And the trichromatic triangles。Okay。

 so the key observation here is that。Alright， so look， remember。

 there's an edge whenever there's a red read triangle。 So consider this face。Okay。

So it's red on one end， and it's green on the other。 Okay。

 so it toggs from red to green at least once。 There's certainly at least one entering arc on this side。

 In fact， there's one entering arc every time that the color changes。So you know。

 you can enter the triangle。And now， once you're inside here。If you think about it。

 whenever you enter a triangle that has， whenever there's a triangle that has at least one red green。

Side。There's either it's trichmatic， right either you get stuck if the third vertex is blue or if。

 if you're not at a trichmatic triangle， you enter through red green。

 The third one has to be either red or green。 So that's a second arc by which you can leave。So。

That's the justist。So we upshot。Finding a。Try chrommatic triangle。In a spurner。Simpplex。

Is a PP8 problem。对。So the starting point is the outer face。

And then you just follow these red green arcs until you get stuck。

 There is this detail you might actually exit back out a different side of the triangle。

 But if you think about it， that by the parity argument means there's another place you can go in on the same side。

So I'll let you think through the details。 But this just kind of shows that， you know， P P8。

 at least has some。Problems that fit the formula。So questions about Merlama。

So I claim actually Spurner's Lemo。This canonical P8D problem actually has a lot to do。

With computing， mixed strategy national equilibrium。So connection to M&E。So， in fact。You can use。

 it turns out， Spner's lemma。I'll explain this a little bit。To compute。An approximate。

Nash equilibrium。Not in polynomial time。Because the path you follow could be exponentially long。

But computing a mixed na equilibrium， at least an approximate one。

 actually reduces to a sperner'slemmapathel in computation。

Okay so this forges a connection between the problem we started with mixed National Libria and the obscure st complexity class PAD。

So what's the connection between Spurner's Lemma and Nash equilibrium。Well。

 so it happens in two steps。 and the intermediate point is brower's fixed point theorem。

It so Bs fixed point theorem says that if you give me any compact convex set。

And you consider a continuous function， a continuous operator that maps that set to itself。

 and has to have a fixed point。 And that's barrels fixed point there。 Comp conx。

Function back to itself， it has a fixed point。It has to be convex because if you had like a donut。

You could rotate the donut， and there'd be no fixed point。Has to be compact because， you know。

 for example， if you took you know， some， the interval from one to infinity。

 if you doubled every number， it would be continuous， but it wouldn't have a fixed point。

So it has to be compact， it has to be convex。So claim one is that Spner's lemma implies B fixed point theorem。

 Claim  two is that B's fixed point theorem implies Nash's theorem， existence of equilibrium games。

So let me just sort of outline a little bit how those go。

So suppose you wanted to prove Bart's fixed point theorem just for the triangle。

 just for the simplex。Okay。Basically， it boils down to Spner's Lalemma。

 followed by a limiting argument。OkaySo how what are these colors？

So suppose you had a continuous function mapping this triangle back to itself。

So I discretize it really small， really tiny triangles。

So how do I know whether it color something red， blue， or green？So I'm gonna color。 So again。

 we have this function。 F your favorite continuous function。So any of this point。

 so at a given point。If it moves farther away from this side， then I color it blue。

G if it moves in that direction， I color it blue。So certainly this node can only go that way so that gets colored blue。

Similarly， anything that gets moved that way by the function gets colored red。

 anything that moves this way by the function gets colored green。

There has to be a trackmatic triangle。Again I' make these triangleles really tiny。

So there's one vertex is red，1 vertex is blue，1 vertex is green。

 So that means there are these points that are really close to each other that are all getting moved in different directions。

They're all going in different directions。So if I take the limit it's a continuous function。

 the only way this can happen is if in the limit， I have a fixed point。

If I have all these tiny points right next to each other going different directions and they'll limit they're staying in the same place。

So that's how you go from Sperer's lemma to Ber's fixed point theorem。

Going from Ber's fixed point theorem to Naash's theorem。 So this is Nash's original argument。

 it's actually a nice， not that difficult reduction from Nash's theorem to Ber's fixed point theorem。

 So basically you just think about collections of mixed strategies。

 The sort of first idea is you want to define an operator that takes as input probability distributions。

 mixed strategies for every player and then returns the best response。

 The only issue is that's not a continuous function。

 So you add what these days we would call a regular riser to this best response function that makes it continuous and it's easy to set up a byjection between fixed points of this regularized best response function and the naA equilibrium of the game。

So that's how you go from Spner's Lemma to B's fixed point Theorem to Na's theorem。

The proof is reasonably constructive。 So if you just sort of follow the proof。

You can actually compute a prox mixed Nsh equilibriumria by using a path argument like this。

So that's sort of the high level argument about why PP D。

 this complexity class defined by a path following。

 does actually capture the problem of computing a mixed Nash equilibrium。So upshot。

So what's the takeaway from all this， So first of all。There's a subclass of TFMP。

 So P L S was the subclass we studied Monday。 right now， we're defining a different one PD。

 same flavor， but different， it seems。But like PLS， it's a syn tactic class。

 so we expect it to have complete problems。And two。Remember。

 our original search was if computing NA equilibriumlibria is complete for something。

 what would it be complete for， we've rejected NP， we've rejected TFMP。So。We have a new candidate。

Let let me just add a few details here。 So the argument I gave you here to two things。

 So first of all， it didn't assume that there were two players。

 So Nash's theorem and its proof works no matter how many players you have。 So that's the good news。

 The bad news is that the proof I gave you only holds for approximate naash equilibrium。

 So what I showed you is that approximate mixed Nash equilibrium for any number of players is a member of PD。

😊，It's a little bit different than the problem we first started with， which was two players。

 an exact na equilibrium。 Okay， but that problem is also in P D。

 There's sort of a second reason for there's a second reason to see why Pa falling has to do with the next N equilibrium。

 I won't have time for it。 But there's something called the Liy housing algorithm。

So this is an algorithm that works only for two player games， but doesn't have to be zero sum。

 Okay it was general sum to two player games。 Think of it as like an analog of the simplex method。

And in the same way that the simplex method reduces linear programming to path following by walking around the edges of a polytope。

 so does the ley housing algorithm reduce nasty equilibrium computation in two players to path following around the product of two polytopes。

 it turns out。Okay，So this is a true statement， two player games， exacttache equilibriumria。

 that is a member of this PPD class。 that can be solved by path following。Cool。

So the picture we have over here。Now is this。We've defined a second subset of TF MPP and one that via this non trivialvi argument。

 contains the M and E problem。 Okay， so we expect this to have complete problems。

We might hope now that computing mixed nalib is actually as hard as anything else in P D， Okay。

 as hard as any other problem that can be solved using this directed path following through a directed graph with in degree and that degree at most one。

Oh， perfect。So it still more refined goal。All right， so TFMP didn't work。B别。

So this obstacle has gone away， we define this obstacle away。

So this class was defined way back in 1990。And really one of the motivations for the class was sort of the hope that perhaps that was the class。

For which computing national equilibrium would be complete。

So it took a long time for that to be proved 15 years。But it is， in fact， true。So the first。

Paper was Doscalacs， Goldberg and Papa Dimitri， they proved this for approximate N Elibria。

 three players and more， and that was quickly extended to the two player case what we've been talking about today by Chen Deng and Tang。

So computing。M an E of two player non zero sum games。Ass PPD completes。It's pretty neat。

 one of the very first times I was actually teaching 3，64， A， you know。

 these results were getting proved sort of in the last few lectures of the class。

 So it's pretty exciting。😊，So this is， this is unlike the proof I showed you on Monday for Pu equilibrium Lib of congestion games。

 This is， this is a complicated reduction。 Okay， so， you know，20，30 pages， something like that。

So there is a nice overview in the AGT book that Papa Dimitri wrote that gives you just sort of the conceptual ingredients of this reduction。

 And that overview is accessible。 So if you're interested， I encourage you to read it。😊。

And pagess 41 to 45。I'm not going to say anything about the proof here。

I just sort of want you to understand that it's true and sort of what it means and what this class means。

And good。I hinted at this interpretation way back in the first lecture。

So we don't know if there's ever going to be a polynomial time algorithm for computing na equilibriumria。

 we just know that if there ever is one， it will be a generic way of shortcutting that exponentially long path。

 it'll be a polynomial time algorithm， not just for mixed naashria。

 but via completeness for every problem in PPAD。So we might expect that there is an a polynoial time algorithm or at least it would be quite a while before we find one。

 And so the question then is， if centralized polynomial time algorithms with all of their power can't find any mixed na equilibrium of the game。

 what does this equilibrium concept actually mean。What is it good for？

So one interpretation you could have of this theorem。 And this。

 this interpretation is not without controversy。But， you know， it's certainly the case that。

 you know， in games where no arbitrarily clever algorithm can find an equilibrium。

 you certainly don't expect players of the game to find it themselves either。

 who is not within any reasonable amount of time。So intractability。

You could interpret this as perhaps。Nash equilibrium while useful for lots of things and also predictive in lots of classes of games。

 perhaps you shouldn't take them seriously as predictions the general purpose。 Okay。

 so Nash's theorem as far as existence。 You know these naash equilibrium always exist And the question is。

 how well do you expect them to corroborate with actual behavior。

 And sometimes you expect a good cooperation。 But interacttractability in the worst case suggests that you should never sort of have a general purpose assumption that equilibrium play will be realized。

So it's unsuitable for general purpose。Behavioral prediction。Now， in some sense， you know。

 this is not， you know， a new。I mean， arguing this criticism in a complexity theore way is certainly new。

 And I think that's a great contribution of theoretical computer science to this area。 There are。

 of course， other criticisms that you can make about na equilibriumlibria that also hamper its predictive power。

 know， for starters， just the fact that it's not unique。

 to that the games can have lots of them makes you wonder。

 know how you should interpret what's actually going to happen in the game。

 So it's not like this is the first crack in the armor。😊，But， but nevertheless， this is， I think。

 a really nice contribution by computer science to this。You know， age old economic concepts。

So let me just finish the technical discussion with a couple open questions。Is any questions？小话。

Co right。So， open。So one is just， it would be nice to understand a little bit better。

Have some more evidence about whether there could be polynomial time algorithms for PPD problems like NASA equilibrium or not。

 So， for example， it would be great if we could relate the assumption that these are different to other assumptions that we make like we're not going to relate it to P not equal to NP。

 but you know， perhaps cryptographic assumptions。 Can we say that this is at least as strong or weaker than standard cryptographic assumptions。

 We know very little about this problem。The fact that national equilibrium are intractable in general makes us wonder。

 are there alternative equilibrium concepts which might have better use。Okay。

So it motivates thinking， looking at weaker equilibrium concepts that are more tractable Now。

 in this class， we've already talked about this a lot via correlated equilibrium and coarse correlated equilibrium。

 we know that they're much more tractable than Nash equilibrium。 So complexity theory kind of says。

 you know， those equilibrium sets are worth a lot of attention because of their tractability。

 One natural concept， which is not understood， is approximate mixed Nsh equilibrium。By which I mean。

 you know， you have two property distributions。 Maybe you can do a little bit better with the best response。

 but you can only do epsilon better with the best response where Epsilons， you know，0。1 or 001。

So a complexity of。Approximates。How many。Some partial results are known there's one or two problems on the final covering what's known about approximate mixed na equilibrium。

 but we just a major open question is， can you compute one of these in polynomial time or not。

 We know you can compute one in quasi polynomial time。And the final goes through that。

 but we don't know polynomial time。Questions。Okay。I we've covered a lot in this class。

 So I was sort of debating kind of how to wrap up。 So one idea I had was I prepared a top 10 list，3。

64， a top 10 list。You want to hear it？Just remember all the things we covered。

So in chronological order。So I had to start with the Vcky a that was way back in like lecture 1 or lecture 2。

 and hopefully you can think back then and be like， oh yeah， I knew so little back then。

mean I hope you have that feeling， because that's the feeling that you learn something in a class。So。

 and you might remember， we even sort of thought then about the ramifications of whether you do first or second price。

 And we even did this sort of bidding game to make the point of how hard it is to figure out how to reason in a first price auction。

 So that was our first introduction to what I call awesome options。

 So options that are dominant strategy set of compatible。

 where we used to have a braind way of playing。 And it also runs in polynomial time。

 That's number one。😊，Greatest hit number two， Myerson's Lema。 So this was。

What was really cool here is we could reduce mechanism design with all of the game theory。

 And we had this single tool that stripped away the game theory stripped away the incentives and said dominant strategy。

 mechanism design for single parameter problems。 reduces to just algorithm design with an extra monotonity constraint。

 And we had a lot of cool applications to this。 So we get polynomial time algorithms for Napsack auctions by adapting the greedy algorithms that we learned from Napsack。

 And we had Myerson's theorem， which gave us revenue maximizing optionss when we had a common prior。

 So maximizing expected revenue reduces to maximizing virtual welfare。😊，Greater hit number three。

 the Buo Cler Ethereorem。 So this was sort of our introduction to the idea that simple auctions can be almost as good as optimal auctions。

 So this was the result which said if you have a single item auction if you just run the victoryy auction So ebay with zero reserve if you like and you recruit one extra bidder。

 one extra I bidder to your auction， your revenue was just as good as if you knew the underlying distribution and ran an optimal auction tailored for the distribution so competition is better than information in that sense。

 and again this gave us the inkling that maybe we don't have to do full blown virtual value maximization to get really close to optimal revenue。

So number four。The VCG mechanism。 So the more from the VCG mechanism was that if you can get people to internalize their externalities。

 So if you charge people the externality they impose in everybody else。

 you can get a dominant strategy implementation for welfare maxization super generally。

 So we almost only talked about single parameter problems。

 So are problems where the you have a single private value。 the more stuff you get， the happier are。

 So the one multiparameter sweeping result we have is the VCG mechanism。

 welfare maximization as widely as you want。So number five。

 the lessons of spectrum auctions and how rookie mistakes can cost you hundreds of millions of dollars in realro auction design。

 so we had like rookie mistake number one， which was if you sell items sequentially instead of simultaneously that's what happened in Switzerland in 2000 cost them 1s if not 1 hundred million what millions of dollars and then we had the New Zealand 1990 example where they ran sealed bids simultaneously auctions instead of ascending ones and as a result they had really heavy competition for some stations and essentially zero competition for others and they even published the second highest bids so they saw that the highest bid would be know 50000 and the second would be6 that 60006。

So those are the five from the mechanism design part of the course。

So then we went on to games in the wild where we didn't have the luxury of designing them ourselves。

 so we couldn't just focus on dominant strategy implementations。

 we had to start thinking seriously about equilibriumria。So we started with selfish routing。

 and we had this theorem which said that basically worst case examples are always simple。

 Whatever your cost functions， pig like networks give you tight price of energyarch bounds。

So that meant in particular。That the only way you could have a high price of anarchy and routing networks is if you have highly nonlinear cost functions。

 If you have linear cost functions or low degree polynomials。

 you're guaranteed a small price of anarchy。 And we talked about how that corroborates the empirical results。

 saying that over provisioning your network gives you really good performance guarantees。

So we talked number seven。So a lot of the canonical price of anarchy bounds。

 pretty much everything we saw in this class， routing games， location games， etc ceter。

 turns out to be you can articulate them as these so-called smoothness proofs。

 this canonical way of bounding the price of anarchy and the bonus you get is that any bound you prove applies much more generally not just to national equilibrium。

 but also to these now we understand very tractable equilibrium concepts， correlated equilibrium。

 course correlated equilibrium， no regret dynamics and so on。Number 8， another thing。

 I sort of maybe hope you remember games can have potential functions。 So the idea that sometimes。

 despite the fact， by definition， everybody's optimizing their own objective function in some games。

 they inadvertently collectively optimize a single global function。

 So we have the Rosentthhal potential function for routing games。

 And so when you have a potential function， like in a lot of the applications we discussed。

 you have pure National equilibrium。 We know you don't have those in general。

 even in rock paper scissors， But you have them in potential games。

 and you have convergence at best response dynamics。And so now getting the stuff we did recently。

 so no regret。The idea that you have algorithms， even very simple ones like multiplative weights。

 which guarantee you no regret as good as the best action in hindsight。

 so that already the single player guarantee is very interesting and has lots of applications in the context of games with lots of players if everybody uses a no regret algorithm。

 it guides the time average history of joint play to these tract equilibrium concepts。

 even the correlated equilibrium， if you use no swappper regret algorithms。

 And then finally this week we understood the limitations of learning and limitations of equilibrium computation。

 We have these analogs ofmp completeness。 They're tricky to define。

 but you really need them to reason about why we can't solve some of these equilibrium computation problems。

 Ps completeness， PD completeness culminating with the fact that by matrix games and their national equilibrium elude polynomial time algorithms。

 it seems。So let me leave with a pitch。 So there is gonna to be a sequQL course in the winner，3，64 B。

It's Wednesdays， so only once a week， so it'll be sort of a 75 minute lecture， a 15 minute break。

 and then another 75 minute lecture。So it's for the hardcore amongst you。 It's nots not。

 this is the intro survey course。' that's definitely know the focus is going to be entirely on mechanism design。

 especially stuff for the last five years。 So it's really for people who want to know what's up with a cutting edge and definitely for those of you take it for a letter grade a course project will be a part of it。

 So you'll be looking at some of the recent papers and either doing a synthesis or trying to come up with some new stuff。

 Again， I think that's it。 So acknowledgeledments， thanks to Costa and Aca， they've been awesome Ts。

 thanks to all of you。 I've had a lot of fun。