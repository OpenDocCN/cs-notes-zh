# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p06 -06-(Lecture 6_ Gross Substitutes-Welfare Maximization in Polynomial Time) -BV1fNVNzhEBg_p6-

So what I want to talk about this lecture。Is。Okay， so remember。

 you know the quest for this first part has always been to have simple ascending options and it was always the case that a sanity check would be well there better at least be a polynomial time dominant strategy implementation and of course。

 for welfare for max that means VCG So we always paused for like two seconds to say， okay， well。

 VCG's in polynomial time， at least right？Now， it turns out once we get to the generality of gross substitutes。

 it is actually quite a bit of work to prove that you can implement VCG in polynomial time and that's the goal of this lecture And what's interesting is we're actually going to use the stuff we talked about last lecture。

 the fact while lawss and equilibriumlib are guaranteed to exist。

 we're going to use that directly improving that we can implement this in polynomial time So hopefully this will give you sort some indication of all the intricate connections between properties of gross substitutes valuations because again。

 these two seem like to have very little to do with each other lawss and equilibriumlib it was just an existence question seems to have nothing to do with computation and then the payments weren't the same as the VCG payments。

 And so now here we're switching a computation we're switching to VCG and somehow the same condition is sort of the right one。

All right， so poly time。Implementation。A VC G。Okay。嗯。ちちちちち。Right， so a couple comments。

So we're going to do this using linear programming。both to sort of reason about how this might work。

 And then the actual algorithm we'll use linear programming as well。 It will be not practical at all。

 Okay， so the point is just to show today， in principle， you can do welfare maximization。

 And therefore， the VCG mechanism in polynomial time with gross substitutes。 I mean， keep in mind。

 we're gonna to be using pretty heavy machinery。 But I mean， keep in mind。

 this is somehow a pretty big generalization of bypartite matching。

 which is already not the most trivial problem to put in polynomial time。

 we're really going significantly beyond that。Speaking of bipartite matching。

 I want to basically develop all the relevant linear programming in the context just of scenario number three。

 just in the context of unit demand bidders， where we can think about welfare maximization as bipartid matching。

The reason I'm going to do that is because the general proofs are exactly the same proofs。

 but it's going to be， I think， quite a bit easier to just understand what's going on if we keep a concrete for a bipartid matching。

 Okay， so， you know， we're going to go retro for a little bit back to scenario 3。So warm up。

Unit demand。So， let's think， let me。So if you never knew。

 if you knew some linear programming and you never knew that there were common trail algorithms for bipartite matching。

 let's， let's give an argument about why the V G mechanism can be implemented in polynomial time via linear programming along the way。

 we'll get a very satisfying interpretation of raw rising equilibrium in terms of optimal dual solutions。

 which is actually a good way to think about them okay。😊，All right， so。

Let's start with an integer programming formulation of welfare maximization in this setting。

 and again， welfare maximization is just bipartite matching。Where you have the bidders on one side。

 again， this is for the unit demand case。Items on the other side。And it's a complete graph。

And the weight of an edge。Is VI J， bitter eyes value for good J。

 So welfare maximization is exactly the same as max weight byite matching in this graph。

So let's encode this as an integer program。So we're going to have one decision variable。Xi J。

 either zero or one。For each bitter I and item J。One just denotes that J gets assigned。To I。

0ero means J is not assigned sign to I。So we should talk about what we want。

 which are objective and then what are the constraints。 So we want to max welfare。Right。

 so the welfare is just well。Let's look at each bitter eye in turn。Let's look at the various。

 let's look at the goods that I might have gotten。And whenever X I J equals one， meaning， in fact。

 item J goes to bitter I。 that contributes VI J to the welfare。 Okay， So this is just the。

Welfare objective。Now， for this to make sense。Two constraints have to be true。So first of all。

An item， of course， can only go to one person。So we have a most one。

And this is summing over all the bidders to whom it might be assigned。And then second of all。

 in a unit demand case， we want to focus on just bidders getting a single item because remember。

 they don't want more than one。So we have another set of constraints for all bidder's eye。And again。

 this is at most one。And now it's a sum over all of the items J that the bidder might get。

So the assertion， which I can elaborate on if you want， but I won't， if you don't ask。

 is that this integer program exactly encodes the max weight bipartite matching。

feasibleeaible zero1 solutions to this exactly correspond to bipartite matchings。

 and the objective function exactly corresponds to welfare。Any questions about that。All right， now。

 so lots of integer programs are hard to solve。 This one is not。

 Many of you have seen bipartite matching algorithms which whether they know it or not。

 are producing optimal solutions to this integer program。That said。

 I still want to think about the linear programming relaxation。 Okay。

 often linear programming relaxations are for problems that are n hard， which this one is not。

 but still， I want to think about dues。 That's useful interpreting all ro equilibrium。

 Okay Dus of what dues of this。Programs linear relaxation。So what's the linear relaxation？

It just means that we remove the only thing which is not linear， namely this。

 this is a binary constraint， and we replace this with a linear constraint。Okay。So LP relaxation。

You take each constraint of this form。And you replace it with a constraint， XIj is non negative。

Your first thought might be to also have a constraint that X I J is in most one。

 Not that would be redundant with these constraints。 So we're just gonna have X I J non negative。

Okay。Now this is a linear program。Okay， and linear programs can be solved in polynomial time。 Okay。

 that's not an obvious fact。 And I'm certainly not going to prove it in this class。

 but it's a true fact， which you should know。 Okay。

 so linear programs can be solved both in theory and in practice。Okay。各有。Now。

Let's think about the duall in your program。 So let me actually just do a little review of dues and what they mean and where they come from。

So we'll call this the primal linear program。Okay， in this context。So the point of a duel。

What it's really doing is it's encoding a family of upper bounds。

On how big the optimal solution to this linear program could possibly be。

So listening a program has some optimal objective function value， 123 or whatever。

 and I'm going to give you a way to encode proofs that this optimal value is at most something。

So let me be more concrete。 So let's do a thought experiment。So， imagine。So how would I convince you？

That the optimal solution to this linear program is at most whatever， has value of almost 123。Well。

 here's an approach I could try to use to convince you that you can't do better than 143。

Suppose I dream up。Some non negative weights。Both for the items and for the bidders。是。

So it doesn't matter where these come from。So， non negative weights。To the bidders。

 So I'm going to call these the UIs。 Eventually we'll be able to interpret them as utilities。

And the items， so these are the PJs。Which eventually we'll be able to interpret as prices。Okay。

 so inside， so if we think of this as a bipartite graph， the nodes corresponding to the bidders。

Get these weights， UIs and the nodes corresponding to the items， get these weights， the PJs。

And suppose。I cover the values of all the edges。So they're all edges。Are covered in the sense that。

If I sum up the weights。On the edges endpoints， so think about just a pair IJ。

And I compare some of the weights of its two endpoints， namely UI and PJ。

With the weights or the value of that edge， V I J。The node end point weight should be at least as big as the edge value。

 that's what I mean by these weights covering all of the edge values。

Suppose to some of these weights， all of the U Is and all the PJ。

 supposeupp some of all of these is at most 143， I claim then you have to admit that the max value of any matching is at most 143。

So why is that true？Well， for any matching。Okay， so when you pick an E I J， of course。

 the contribution to the welfare is V I J。 But you know what I'm gonna be I'm gonna be a nice guy。

I'm not going to give you V I J。 I'm going to give you U I plus P J。 instead of V I J。

 the edge value， I'm going to give you to some of the edges， the endpoints， weights。

 which is at least as large。 So I'm doing you a favor。 I'm giving you a larger number。Now。

 it's matching。So each node on each side only participates in one edge。

So there's node I with weight Ui that's only going to contribute to this some once。And this node。

 J with weight， P J， that's only attributed to some once。

 So the best case scenario is you pick up each of these weights from every possible node once。

That's the sum of the PJs and the sum of the UIs。Okay。

 so that's definitely an overestimate on the value of any matching。Great。So this is。So notice。

 like for the matching problem， if you wanted to convince me that the optimal solution is at least some value。

 like 111， it's clear how you do that。 Show me the matching。Go inspected， count up the values。

 I'd be like， yep， that's 111。 The best matching is at least is good。

 So this is how we get bounds on the other side from above。 Okay。

 we're putting node weights that cover the edge values and then summing up all of the node weights。😊。

Okay。Alright， so this is a generic method you could use to upper bound the value of the max weight matching。

 the dual linear program。By construction， by definition， is just the best。

 the smallest upper bound you could ever prove。This way。对。Oh， something I forgot to say。So notes。

The upper bound argument I just gave， it doesn't just apply to matchings。

It also applies to so called fractional matching。That is it applies to any feasible solution of this linear program。

For exactly the same reason。 Okay， so if you pick an edge。At 05， again。

 instead of giving you 05 times its weight， I'll be a nice guy。

 I'll give you 05 times the sum of the weights at its end points。This says that。

 know counting up overall all edges in incident on a bitter eye。

 it's going to contribute at most to one overall， so at best you'll get the full UI contribution from this bitter eye and at most you'll get the full PJ contribution from a good J。

Okay， so even if it's a fractional matching， which is a bigger set， gives only more of them but。

These proofs also upper bound the best possible fractional matching。So anything feasible。

For this linear program is upper bounded by the sum of the weights for any choice of non negative weights so that knowledges are covered。

And again， the dualLP is just the best I。E smallest upper bound of this form。So， formally。

The dual LP is。Well， so we have this constraint here。U I plus P J。Is the most of VIJ。Looking ahead。

 let me suggest rewriting this constraintst。As UI， at least VIJ minus Pj。To be suggested。

 it's the same constraint。For all IJ。As I said， all these things should be non negative。And。

Amongst all such upper bound proofs and the corresponding upper bounds that they give。

 we want the best one possible。So we minimize。Okay。So， we've argued。

We've already proved weak duality。Which says that the objective function value。

Of every primal feasible solution。 that is every fractional matching is bounded above by any of these。

 Any feasible solution gives an upper bound。AndAgain， when I hear it。 So in the primal。

 when I say objective function value， I mean this over here。

 when I say the dual objective function value， I mean this。So this we already proved。

Because that was the argument about being a nice guy and so on。Okay。So。Good， sets weak duality。

 That's very important。 I want， let me just sort of emphasize。

 especially if you haven't followed literally everything I've said， Just keep in mind。

 if you ever review this later， Basically， nothing up to here has any。Math， content， whatsoever。

 Okay， there's conceptual content in this sense。 I think this is a good way to think about stuff。

 But this is all by construction， by definition， up to this point。There's been nothing nontrivial。

Okay。And so actually， I'm gonna continue that for a second。Really。

 there's only going to be one non trivial thing。And， when I say trivial。

 I don't mean it should make sense the first time you see it。 That's not what I mean。 I mean。

 at some point， if its not， if it doesn't， if it's not crystal clear now。

 you can definitely get to a point where it's crystal clear。 That's what I mean。Okay。

So what I want to ask Ns is。So we have this inequality， you take any primal solution。

 any fractional matching， you take any covering of the nodes of this form。

 and you know that the primal deduct function value can only be less。

Then the dual objective function value。And now I want to say under what conditions。

 joint conditions on this pair， the primal dualual feasible pair。

 When would it ever be the case that this inequality holds with equality。Okay。

 so that's going to give us what's called complementary slackness conditions。It's a question。

When does a equality hold？For some primal dual pair。Okay。Well。I mean， in general。

 suppose you have a chain of inequalities， right A is the most B is the most C is the most D。

And you want to ask， when is a equal D？Well， they' equal exactly when all of the inequalities in the middle hold with equality。

Okay。So week to alley， we argued through why this was an inequality。 right， We said， well， you know。

 over here， you get the fractional matching。And then， you know。

 we could have the upper bound where instead of doing VI J。

 we could instead charge something which is only more U Y plus PJ。

Because that's the first inequality， instead of using the VIJs。

 we use the sum of the weights of the endpoints。We used it in two other analogous ways。 So first。

 we said at best。You get the full weight you survive， you might get less。And we also said， at best。

 you might get the full weight piece of J from Adam Jet， you might get less。

So those are the three inequalities。And so weak duality will hold with equality。

 if and only if those three inequalities are tight， hold with equality。

So that's complementaryary slackness。 Complimentary slackness is just saying。

Theyre just the conditions that those three inequalities hold with equality。So， formally。So， answer。

If and only if。All right， so we have the first one to the first potential sloppiness was that the sum of the weights of an edge might exceed。

The value。 So we want that to hold with the quality。 Okay， one exception。 I mean。

 so if an edge doesn't participate in the matching at all， if X I J is 0， then who cares。

 it's as if that edge didn't exist。 So we don't care about this。So really what we mean is。

There should be no overestimate。Or again， it might be more suggestive to rights。

UI equals VIj minus Pj looking ahead。Whenever。The pair Ij is actually put to use whenever XIJ is strictly positive。

And then we have the analogous ones about just saying， you know。

 a better be that actually you don't just get up to one U to the UI。 You better get the full UI。

Well that UI zero then who cares。And， similarly。As long as PJ is not zero。You better get。

You better use it fully。Okay。So in terms of this graph， the first condition says， you know。

 consider any fractional matching right So that's just sort of a percentage of use on each of these edges and saying unless this is0。

 it better be the case of the two node endpoints is exactly the value and then the second one that's referring to the bidders。

 So it says just the total fraction on edges that are incident to that node on the left- hand side should be one unless its value is0 and then the third condition is the same thing about nodes on the right hand side and the incident edges adding up to one。

Okay， so that is the answer。 Okay， so just， again， there this is just nothing but straightforward algebra。

 The answer to when would you have a quality here， if I gave you a given feasible primal solution and feasible dual solution。

 if and only if。These three conditions satisfy。 Okay。

 just because whenever you have a chain of inequalities， you know， to have equality of the endpoints。

 you need to equality everywhere in between。 that's all this is。Now。Here is the one。

Statement with significant mathematical content。Strong dual。You know， again。

 don't be too scared of this if you've never seen it before。

 we could prove this in maybe 45 minutes at the most。 I'm not going to do it here。

 I'll put some notes on the course web page， if you want to read more。😰。

So strong U says it is always possible。For any linear program， in particular for these。

To choose a feasible solution to the primmal and to the duall so that this holds with the quality。

Okay。And that is not obvious。 So， in other words。I talked about these dual solutions as being a method by which you could generate upper bounds on the optimal solution to a matching。

 But who's to say that there isnt some other class of much better upper bounds。

 that will give you much sort of tighter understanding of what the optimal solution is。

 So strong audience says， then I worry about it。 All you need are these dual arguments。

 This is sufficient to prove the correct upper bounds。

 to proven upper bound that's equal to the actual optimal solution value。So strong dual says。

The optimal。Prial value。Equals the optimal dual value。Okay。Questions。All right。So。Good。

So that's important。 And then corollary is important。 So now， suppose。

 so the point is going to be that。Complimentary slackness characterizes optimalphity linear programs。

 Okay， and that's going to be very useful for us in a second。So even without strong duality。

 let me point out the following。so forget about this for a second。So suppose。

 suppose you didn't know whether strong held or not。

 But suppose I succeeded in coming up with a primal dual pair。

So that all three of these conditions hold。Okay， so I show you a matching。

 and I show you these node weights。And it's the case， you just read them off。

 you just check that all these three conditions are satisfied by that primal dual pair。

What do you know？Well， first of all， this is necessary and sufficient to have a quality。Okay。

 so that means that， you know， this primal solution has value 123。

 and so does the dual solution of 123。So by checking these。

 you immediately know that they have an identical objective function value。

And then you go over and you look just at weak duality。 and you say， oh， wait a minute。 Well。

 if there's no way a primal can be bigger than any duel。

And there's no way a dual can be smaller than any primal。

And I just found the primel on the door with exactly the same value。

That automatically certifies the optimality of both。Okay。

Even if you don't know strong duality is true。 Okay， the point is。

 if I ever show you something that satisfies common or slackness。

 you know the involved prominently involved will have to be optimal just from weak duality。Okay。

Because again， no primal could ever be bigger than a duall。

So if you have a prim that's equal to a duel， that's as high as it gets。Same thing。

 No dual can be less than a primal。 So if it goes all the way down to a primal。

 then it can't get any lower。Okay。So one direction， you don't even need strong duality。

 If complementaryary slackness holds， then both of the involved primal and dual solutions have to be not just feasible。

 but they have to both be optimal。 I that statement1。Now， strong U says， well， look。

In any linear program？There is going to be a pair。Where the objective function value is meet and therefore。

 of course， are optimal。Okay， so what that means is if you don't satisfy the complementarys sness conditions。

 okay。Well， then you're not going to have a equality。

 The primal objective won't equal the dual objective。So then they're not both optimal。

 One might be optimal， but they're not both optimal。 Okay。

 Strong Ga audience says something out there meets with equality。 Those are the optimal ones。

 So if I show a prime in a duall that has a gap， one of them is not optimal。

 And if you don't meet the common slackness， then you have a gap。Okay。So summarizing。

 we are the following。But X。Be primal feasible？Wet。U comm a P， remember in the duall。

 we have both U's and P's so that U P be dual feasible。So what we now have is that。Then， x。

And UP are both optimal for their respective linear programs。If and only if CS1 through CS3 hold。

Okay， that's the we just talk through。And again。This direction doesn't only requires weak duality。

Okay， whenever you see all of these three， you get identical objective function values that certifies both as optimal。

 But strong dual says， in fact， that's the only way to be optimal。 Okay。

 there's no way that something that doesn't satisfy this will ever satisfy that。Okay。Allright。

 so any questions about that。All right， so hope that was good view。

Now what I want to do is I want to connect。All this stuff to the existence of Ororizon Elibria。 Okay。

 so stuff starts getting kind of cool here。So， here's the theorem。And this theorem will follow。

 really quite directly from this complementaryary sinus condition。

 quite directly from this corollary。So the way I'm going to state this theorem is going to look a little weird for the bipartiteite matching special case。

 but it's going to generalize effortlessly。 So that's why I'm going to state it in this particular way。

All right， so we've got a linear program。Sorry， we've got our integer program。

Where the feasible solutions are matchings。So call opt。LP and opt I。The opt value of the primal。LP。

And the opt value of the original IP。So of course， the primal LP， this is only bigger。

RightSo we're maximizing here， the feasible solutions are these 0，1 points only。

 And here that feasible solution is those same 01 points， plus a bunch of fractional stuff。

So optLP is only going to be at least as large as opt IPP。Okay。

So here's what theorem says there's two parts。 So first of all。Again。

 in this statement will look a little weird the way I write it。There exists rise in equilibrium。

If and only if。In fact。The linear programming relaxation is exact in the sense that both the integer program and its linear relaxation have identical objective function value。

Texas's claim one。Now， why is this weird？It's sort of weird to write this。

 because the left hand side。What do we know about the left hand side in this biparttheite matching context？

We just know this is true right， Yeah， so I mean， this if only if makes it sound like there are cases where it's true cases where it's not Okay。

 but again， thinking forward， this will make more sense Okay but for unit demand bidders for bipartite matching。

 this always holds。😊，So in particular， this is asserting that for any bipart matching problem。

 In fact， the linear relaxation is exact。 Now， that's a well known fact。 Okay。

 this isn't some novel proof of that。 Okay， people have known this forever。 Okay， but I mean。

 you know， certainly， the coincidence should be reassuring in this case。Okay。

 so here's something which has a little more meat in the current context。In this case。

Meaning when well lawst equilibrium exist， meaning for bipartitean imagine， always。In this case。

Price vector。 So a vector P on items。Is part of a Walez in equilibrium。So remember。

 while is in equilibrium is two things。 It's prices， and it's an allocation。 Okay。

 So we're going to talk about a price vector， I talk about it being part of a war is in equilibrium。

It's part of a one equilibrium， if and only if。P is part of an optimal。Dual solution。Okay。

 again remember， a dual solution consists of two things， A U and a P。 Okay。

 so it makes sense to say part of a dual solution。So in this sense。

 rise in equilibrium price vectors correspond precisely to optimal dual solutions。

 or rather their projection onto the item part， onto the price part。Okay。So again。

 this is sort of weirdly e vacuous at the moment， this has some content。Alright。

So questions about that？And if you think about it， I mean， this this is still pretty neat though。

 in a sense。 I mean， if you think about generalizing this。 So you know， the left thing said， well。

 why is in equilibrium， they seem to be about like nothing but prices。 That's the whole point。

 They're about market clearing prices， right。The right hand side， the right hand side actually isn't。

 okay， So first of all， whenever you see prices， you should think there's probably some dualls in the background。

 Okay， and we'll see that that is the case here。 But actually， the right hand side of one。

 that doesn't even that's not even talking about the dual linear program。

 That's talking about the primal integer program and its linear relaxation。

 So it's characterizing existence of prices in terms of exactness of a linear relaxation。😊，Okay。

 so it's a neat connection。And then the second part is something sort of one might expect to be true。

 but it's worth sort of just teasing out exactly what the formal statement is。 And that's what it is。

O。So， let's prove this。And the proof is the proof is not hard。All right。

So I'm going to prove something that is going to imp both one and 2。Okay。So I'm going to prove that。

Given pair， a price vector and an allocation， which in this context I can think of as a matching。

Is it well rise in equilibrium？If and only if。The prices participate in an optimal dual solution。

And M。Is an optimal solution。To the LP relaxation。O。So we have our integer program。

 We already know from the first welfare theorem that M is a max weight matching。

 So we know it's an optimal integer solution。 And so but here on the right hand side。

 the assertion is that actually more generally， even if you allow fractional solutions， still M。

 this integer solution is the best。Okay。So this implies one and two。So why does it imply1 and2。 So。

 for example，'s okay。 So the second part is sort of you can just read off from this。

 So the second part is really kind of almost a special case of what I have up there。

For the first one， all， so suppose the while and equilibrium exists。

 then on the right hand side there， we have that M。

 this integer solution is optimal amongst fractional。

 so that's a proof that optide peak was opt LP so conversely suppose that the LP relaxation exists exact that means there's an optimal integer solution there exists an optimal dual solution and so you pair those together and those together give you the water in equilibrium on the left hand side。

Okay， so if that was too fast， I'll leave it for you to check offline。

 So we can get one and two in one swoop by just proving this。All right。

 so the harder part is this side。So suppose I give you a rise in equilibrium。 Okay。

 so a price vector P and a matchingshing M。Right。I guess that's too bad。So the dual is still here。

So at x be the。LP。Solution。Corresponding to N。Okay， so this is just notation。 Okay。

 so M is a matching X is just this the characteristic vector of the matching。

 The zeros and ones corresponding to the edges in the matching M， O。Now， so that's fine。

 So this is talking about a dual solution and a primal solution。

 The primal solution that's relevant is X。 So now there is some work we have to do。 Okay。

 it's not hard。 but we have to do it。 So a dual solution。 Remember， So here's the dual。😊。

Duals have price。 They have these P's， and they have these use's。 Okay。

 so to talk about something being an optimal due， I need to tell you what the uses and what the P's are。

 And I've only been given the P's。 So I have to tell you what the use are。Looking ahead， we're。

 I'm going to construct a dual solution。 and then we're going verify that complementary slackness holds。

 And that'll give us the simultaneous optimality of both sides。Okay， so given that。

 we're going to do it in the obvious way。 Okay， so again， we're given we're all in equilibrium。

 I have the Pas。 I have the prices， and it's really tempted to just sort of interpret those prices directly as a dual feasible solution。

 That doesn't make sense。 So because I don't have to use。Allright， so so how do I define use， Okay。

 Well， I want it to be feasible and subject to being feasible， I want it to be as good as possible。

 Okay， we're good here means minimizing everything。So I've given the P's， the values are just fixed。

 okay？So what does this say， So think about this for a fixed eye。Okay， remember。

 we have to pick UI for each eye。So this has to hold for all。 So forgiven。So for giving U I。

 this has to hold for all J。Okay， or this has to hold for all Jay。Well。

 so this is just a bunch of lower bounds。 The only relevant one is the biggest one。Okay。

 so basically， look， I want U I to be as small as possible。

 I make it as small as possible so that all of that holds all those constraints hold I。e。

 I set it equal to the maximum of the right hand sides ranging over all items J。

That's the obvious way to define the use from the piece。So， define。UI。

To be the biggest of these lower bounds。Well， the only other rub， I guess。

 is that U I better be non negative。Okay，So if all those are negative， I better。Make it zero instead。

So this notation just means take the maximum with zero。Okay。Again， the point here is。I。e。

 as small as possible。Subject to dual feasibility。Okay。All right。So， now， by construction。X and。

P comm U。Are feasible。What I want to prove， I want to prove that they're both optimal。

What's my tool given to feasible solutions for proving that they're both optimal。

 I just check that the compound slackness conditions hold。Okay， so let's just see why that's true。

 Okay， so again， we're given a in equilibrium P comma M。

 I extended P to a dual feasible solution P U。 I'm now claiming these three things are true。

Why is that the case？Let's start with the first one。 What the first one。

 say says whenever X I J is bigger than 0， What does that mean， That means， remember。

 it's an integer matching。 It's 0，1 x's。 So it says whenever bitter I gets an item J。

That's what this means。 It has to be the case that this holds with equality。 I。e。

 that this holds with equality。Ie that the utility of the bidder is exactly its value minus the price that it's paying。

 Okay， notice， how did we set the U eyess。I mean， one way to think about how he said the U I is we basically said。

 look at each good J。 What would be my net utility for getting good J with my value at that price and then said U I to be the highest of them。

 I use the maximum utility I can attain by picking my favorite good at price vector P。

 Or if those are all negative at 0。嗯。So that means this holds。 okay。

 So it is the case in a rise and equilibrium。 I'm getting my favorite good at those prices P。 Okay。

 so that means the U I， which meets this with quality。 or whenever X I J is bigger than 0。

 it must be the case that U I meets this with quality。 by the rise and equilibrium condition。😊。

What does this say， This says， suppose the utility is strictly positive。

So what does that mean given how we define the Us， That means suppose there exists in item J。

 So the my value V I J is strictly more than the price。 when a rise in equilibrium。

 if I have positive net utility for some good， I have to be assigned to some item。

 I will not accept nothing。Okay， so if U I is strictly positive， it will be the case that。

 if I'm better， I'll get a good。 Okay， so that works。

 And then this is familiar as just that usual second condition of laws and equilibrium。

 If a good is unsold。 So look at the contrapositive， if this is 0， the good is unsold。

 then it must be the case that the price is 0。Okay。So， note。Cs1 through CS3 hold。And， therefore。X。

And P comma U are optimal。Okay。So X for the primal， even though it's an energyteger solution。

 P U for the dual。So that's the one direction that's starting from the left， going to the right。

The other direction is even easier。 Okay， so leave I'm not going to write it down again。

 but I'll just talk through it quickly。It's easier because they don't have to do this business with sort of making up UIs out of thin air。

If you actually give me。A P that's part of a dual solution， say part of P comma U。

 and you actually give me。An integer solution。To the LP relaxation， okay， and X。

Then by virtue of both of these being optimal。All three of these complementary flatous conditions hold。

 Remember， this was an if and only hit。And the connection between Or and Ilibria and these three connections is also an if only。

Okay， so you just run it in reverse。 Okay， you give me the optimal solutions。

 Co slackness holds that in place water is an equilibrium done。Okay。So that's this argument。

So if you like a computational test for the existence of our and equilibrium is checking exactness of the L of the LP relaxation。

Okay，And as one would hope， there's an interpretation of a was in equilibrium in terms of dual solutions。

 In this case， optimal dual solutions to a suitable linear programming relaxation。 Okay。

 that's the takeaway message for this theorem。Do any questions about that？All right。So like I said。

 this was sort of throwback back to scenario number three。

 but you know hopefully it's a little easier to keep track of what's going on in the bipartite matching setting。

 And the good news is that all of these conclusions just extend with literally zero change to the proofs。

To more general settings。So I will。 I do need to tell you exactly what the。Prial linear program is。

But other than that， I'll just summarize in the main statement。 And if you want。

 I'll leave it for you to write the proofus down again。 But it's literally just， you know。

 word for word exactly the same。So， extension。To general valuations。Okay。

 and so for the current discussion， I'm not going to assume the gross substitutes condition。 Okay。

 this is literally any valuation functions。 What I'm going to say will be true。All right。

And the old N program。We had an X J。 all we kept track of was who got which goods。 Now。

 people might want to bundle the goods。 So instead of X I Js。

 we have X I Ss or S is a subset of goods。可。There are now many more decision variables than there were before okay there used to be n times m now there's n times 2 to the M。

 we're not going to worry about it yet， worry about it later。Okay。So what's the analogous in program。

 so again we want to maximize welfare。So again， we sum over all the bidders。

 We used to sum over the goods J that a bidder might conceivably get。 now we sum over the subsets。

 the bundles that a bidder might conceivably get。 We look at the value of that bitter I for that subset S。

Time is the indicator of whether it gets it。Before we had a constraint that said everybody should get it most one good。

 That doesn't make sense because there's unit demand。

 but it doesn't make sense to say everybody should get at most one bundle。So for every eye。

 for every bitter eye， if we sum over the bundles it could conceivably get。She only get one。

It's still the case that every goods should only be allocated once。So it used to be right。

 So it's a little more complicated because now。Like before。

We have to sum over all the people who might be assigned good J。 But also for a given bitter eye。

 there's a number of ways you might get J。 O， any bundle containing J counts。

So in here we sum over all the bundles S so that item J is a member of S。Of I X， I S。

So the assertion is that whatever the valuation functions， the。

Integer solutions to this program correspond exactly to the allocations of goods to bidders。 Okay。

 where everybody gets most one bundle and every good is allocated at most once。 And moreover。

 the objective function encodes the welfare。 So if you could solve this integer program。

 you would maximize the welfare。And then again， the LP relaxation。

You just replace the integrality constraints with non negativity constraints。 again。

 putting on an upper bound of one was redundant in light of these。Okay。So any questions parting Matt？

So really just instead of the M individual good J， we just have the two to the impossible bundles S。

 that's it。Alright， so because the primal change so little。The dual has also changed。

 not very little in particular， since the constraint structure is really the same。

 We have one constraint per bidder and one constraint per good。 So in the dual。

 we're again just going to have the same set of n plus M dual variables。

 one for each of those n plus M constraints。So the duall now looks like the following exact same objective function as before。

And so the covering constrain looks a little different。 It used to be that a given edge。

Right should be covered by the weights of its two endpoint。 So now， instead of an edge。

 now have an item， we have a bundle。 and each of the items in that bundle has a weight。

 But so we just have a bundle and a bitter pair should be covered by the sum of the weights of the of the bidder U I and all of the PJ is。

 all of the weights of the items in that bundle。So this is going be for all I and S。

 It used to be for all I and J。This is going to be at least V comma S used to be VI comma J。

 and now instead of just a single PJ， we take the total price。Of all of the items in the bundleund J。

And again， the economic interpretation is clear if one writes this as the utility of bitter eye should be at least think of it as the maximum。

Of the value for a bundle， minus the price for that bundle。Okay。And for all I。

And it's still the case that。The U' and the P should be non negative， that hasn't changed。Okay。

Any questions about that。But。All。So。Rather than rewrite the theorem again。Let me just leave it。

So let me just see the following in this setting。with no assumptions at all about the valuations。

With absolutely no rewording， although notice the only the only difference is the LP and the I P have changed。

 Okay， the LP and I P here now refer。To this integer program and it's linear relaxation。

And as stated， this is still true。With exactly the same proofs。Okay。

Wellize equilibriumlib is also defined more generally now。

Rather than a bid getting its favorite single good。

And the given prices is getting its favorite bundle at the current prices。

The biggest thing I want you to notice is that it's no longer the case that one is vacuous？

So remember， I showed you an example。Where there's no or rise in equilibrium。

So when we have that single minded bidder and the unit demand bidder， and it's an exercise。

 but we talked through why there' was nowhere hourss in equilibrium in that case。

So at the current level of generality， which certainly can encode that example， this might be false。

 So in which case this is also false。So for that too bitterder， too good example。

 the linear relaxation is going to be strictly， it's going to have a strictly larger optimal solution than the energy program。

 Okay， we can just read that off of this。In that case， there will be no in equilibrium， so of course。

 this is not going to be the case。There are， of course， still optimal dual solutions。

 There are noized in equilibrium， so there's no correspondence between the two。Okay。All right。

 so this theorem holds is totally generally。 we' wise in equilibriumlibria。

 existence is the same thing as exact LP relaxations。Cool。

So we actually know something about when Mos and Elibia are guaranteed to exist。

That was one of the main points， right of the first lecture。It's a corollary。Suppose。

Every valuation function。Satisfies the gross substitutes condition。

What did we learn in the first lecture today。We learned that while in equilibriumlibria are guaranteed to exist。

So we had the Kelsso Crawford auction。That's what actually us motivated us to state the gross substitutes condition that terminates at in approximate water in equilibrium。

 taking the limits shows there exists or rise in equilibrium。 So not in general。

 but with gross substitutes， we always have laws in equilibrium。Which means then。

 with gross substitutes。The linear relaxation is always exact。Okay。

And I do know other proofs of that fact， but I don't know equally short proof。Okay。

 so the shortest way I know how to prove that the linear programming relaxation is exact for gross substitutes valuation is by proving that w laws and equilibrium exists and then invoking this theorem。

Okay。So that's interesting。Okay。And so I hope you're getting some。

 because I only have sort of today to talk about substitutes valuations。

 I can kind of only show you the tip at the iceberg。 but I hope you're starting to sort of see。

Kind of how intertwined everything is， because where did we start， We started with this， you know。

You know， we started with this Kelso Crawford auction。

 and we already knew it wasn't going to give us an incentive compatible auction。

 right we already knew it wasn't going to work even with downward sloping valuations。

 we knew it wasn't going to work because it was hell bent on funding awa equilibrium。

 which are not VG payments yet we went through that exercise anyways。what are we learning， Well。

 at least people lawst equilibrium exist。 We don't know how to use those directly an incentive metal mechanism。

 but we learn they exist。And now all of a sudden， when we're talking about， okay。

 what about implementing VG in polynomial time， Some that existence that while was in equilibriumria is the thin end of the wedge And as we'll see。

 in terms of an efficient procedure for computing welfare and therefore computing VG payments。

 Okay so again， somehow substitutes form the threshold at which a lot of properties go from true to false。

 Okay， computational ones like we're discussing now and noncomput ones like these。All right。Z meet。

So now let's actually talk about implementing VCG in polynomial time。Okay， so remember this。

So that's going to be important in our implementation。All right， so first， you know。

 just a quick reminder。 So VCG is a mechanism。 it has to compute both the allocation and the payments。

 But again， remember the payments， the computations are the same as for the allocation。

 So VCG is just n plus one ins of welfare maximization。

 Okay so the question of whether or not we can implement the VCG mechanism in poly all time is the same as whether forgetting about incentives。

 Just think about the algorithm question。 I just give you these valuations and ask you for the max welfare allocation。

 Okay， forget about anything else。Up to a factor of n plus one， the complexity is exactly the same。

So reduces。To welfare maximization。Given truthful bids。Okay。So for the rest of this lecture。

 we're talking about a purely algorithmic question。

 It's in service of getting this dominant strategy and se battle mechanism。

 but the VCG payments take care of that。 Okay we're just asking about welfare and maximization。

 what's its complexity。Okay。So can we do this in poly time？

So what do we mean So we actually have so if you think about it。

 we you need to take a step back and talk about foundations a little bit。

 we're veering into the we're about to start making statements that don't necessarily make sense or that are not well defined。

When we say a polym harm algorithm。What do we mean Paul on me and what？Paul me only emphasize。Okay。

 so if I talk about the problem of maximizing welfare with respect to a bunch of gross substitutes valuations。

What's the input size？We had to think about this a little bit。Yeah。There's a few answers。

There's not some right answer to this， but there's an issue。

And we need to make some modeling decisions。Okay。So， let me tell you。

 So let's begin with sort of the。Most。Sort of maybe most obvious and maybe the least useful answer。

Okay。But also sort of the most conventional answer。Which would do well， I mean， you know。

 what do we say， we said valuation functions。 It's just， you know。

 it's a private value for every subset of bundles。So each person has these two to the m pieces of data。

Okay。And so the input size is just going to be the list for each of the n bidders and each of the two of the M VIS is private parameters。

 it's just that list of numbers。So we sort of envision all these VISs provided explicitly。

In which case， the input size would be roughly n times 2 to the M。OK。Now， you know。

 if M is really small， maybe this is okay。 Okay， Otherwise， if M is modest。

 this is really a huge input size。 Okay， so this is exponential in the number of goods。

 which is maybe not that happy。We're not that happy about now that said。

 the algorithm I'm going to give you isn't it all practical。

 so maybe it doesn't make sense to kind of talk about practical instant sizes and so on。

 but the other reason this winds up to be not the most interesting approach for this problem is if this is your input size。

 it's actually pretty straightforward to solve this problem exactly and time polynomial on this input size。

 no matter what the valuations are。Gros substitutes are not。There。So， in fact， it's easy enough。

 I'll leave it as an exercise。So very straightforward dynamic programming。

You can actually solve this problem。 Okay， so again， no assumptions， no gross substitutes。

 I just tell you that the valuations are monotone。And you want to find the best allocation of the goods to maximize the welfare。

You can solve that in time polynomial and N and2 to the N。 Okay， straightforward dynamic programming。

So let me say con solvelving poly time。Where poly is polynomial on the input size。

 which in this case is this input size。But dynamic programming。

So the real complaint we have here as modelers is that this。

 this way of modeling input size suppresses really interesting differences between different types of valuations。

 and this is a real thing in practice。 So， for example， in practice。

 when you want to solve these problems， commercial auction， etcter。

 They're much easier when there are substitutes and they're much harder when there's compliments。

 We'll talk this more about this more next week。 But the point is the actual real world complexity of the problem depends on structure in the valuations。

 And if you model the input size this way， the theory is unable to tease apart those distinctions。

 So that's the main sense in which this is a failure。

 more than the fact that just you know two of the M is a frightening expression。Okay。Good。

So I'll tell you two other approaches。 Both are reasonable。

 We're only going to talk about one of them the day。

 but both are reasonable and lead to interesting and sometimes enlightening results。

So sort of a good rule of thumb in this area would be that。

 you know and somehow we want a model where it's reasonable to ask for algorithms that run in time polynomial in n and M okay。

 and the number of items， not the number of bundles， not in2 to N。So we have to ask ourselves， okay。

 so what notions of input size So what do you learn in 161 or intro algorithms， you often learn okay。

 you have to read the input so we need to somehow have a notion of a model of the input which is not exponential in it okay。

To be able to have algorithms that run in time， not exponential in it。So answer number two。

Would would say， okay， well， I guess I don't really mean totally abstract gross substitutes valuations。

 I mean， you know， valuations would satisfy the gross substitutes condition and also have some。

 you know， succinct representation。Okay，So think about like those K unit demand valuations。 Okay。

 so all I need to specify are n times M numbers of V I J for each bitter I and each item J。

 And then by definition， your value is just sort of the top K of the V I Js。

 if you get a bundle of goods， you just pick the best up to K goods。Right。

So those are gross substitutes。 Okay， of course， it's not all gross substitutes。

 but it's a reasonable class of them。 and you can specify them succcly。

 And it makes sense to ask for algorithms that run in time polynomial and N&M。Okay。

 and that's reasonable。 We're not going to do it today， but that's totally reasonable。

So what are we going to do today。So what we're going to do today is we're going to just think of。

Each valuation， we're not actually， we're going to be agnostic as to how it's represented。

 We're not even going to try to model how VI is described。

 We're just going to model our input output， behavior with these valuations。

So we're going to think of each evaluation as just a black box。Okay that exists in the ether。

That answers queries。Okay questions that we give it。 All right， And if this， I mean。

 if this seems kind of too you know， wishy washy， I mean， let me point out that， you know。

 when we were talking about our ascending auctions and we were actually kind of envisioning interacting with bidders。

 I mean， we really were thinking of them as exactly this。 Okay。

 we were thinking of sort of real human bidders as black boxes。 where we say these are the prices。

 What do you want。 Okay， and we're not modeling their representation。

 we don't have a notion of their input size， we just expect an answer whenever we ask them a question。

So it's actually not that unreasonable。Okay。And。So then the goal。Okay。

 so when you're trying to design an algorithm to say maximize welfare， what， what do you want。

 What's the analog of polynomial running time， Well， you just want to， so goal。

So if you combine sort of the quoteote normal operations of your algorithm。Plus。

 the number of queries that you asked the black boxes evaluation valuations。

 this should be poly in the number of bidders and the number of items。我这儿。And so， you know。

 because there's no explicit list of two to the M numbers。

 there's no obvious lower bound showing that this can't be done， okay。And as we'll see。

 actually this can be done in interesting situations。So one question that's natural to ask is， okay。

 what are these queries， All， But again， you know， if if you think about the ascending a。

 we've seen the examples of these queries， here are the prices， what do you want， now， in general。

 it's sort of negotiable when you do research on this problem， what the queries are。 But obviously。

 when you're proving when you're designing algorithms， proving upper bounds。

 the simpler and the more natural the que is the better。 Okay。

 the more plausible your algorithmic solution。So two of these people have focused on a lot。Okay。

 they're both very natural。So the first one we've kind of seen already in our ascending auctions is just a demand query。

hich is given prices Q。 So basically， you have this black box， you feed into it， a vector of prices。

And you're expecting it to give you back a set in its preferred bundle。 Okay。

 something as demand set。So output'll put a set。Of DIP， okay。

 one of its utility maximizing bundles at the prices P。

 That's the for individual items Ex In this case， it is。 yeah， yeah。对。Right， so so basically。

 you feed it an M vector and you get back a step。The other very natural query。Just a value query。

Which is now you just ask a bitter， seemingly simple question， which is like， here's a set。

 What would you be willing to pay for it， Okay， give me just one bid。

 Here's the set I want to bid for。So give an S。Output V I of S。嗯。And it should be intuitive that。

 you know， sort of value queries seem simpler and easier than demand queries。

 right So like a value query is like me asking you about some product and best buy。 know。

 like that Xbox， how much you're willing to pay for that X box。 A demand query is like， okay。

 this price tags on all the items is in best buy， tell me which subset maximizes your utility at those prices。

 which you know， to be fair like we do do approximations of those problems all the time。

 But it seems like a harder problem。 It's true even formally。

 you can show that you can simulate value queries with a sequence of suitable demand queries。

 Okay so sometimes there's controversy about whether or not demand queries are okay， but frankly。

 in an auction context， I think they're very fundamental。

 And then these should be even even less controversial。 once you start doing anything else。

 it starts getting a little。You know，Controial if it's reasonable queries or not。Okay。So。All right。

I there any questions about that， yeah。It seems like demand query should be easier than value query because the easiest thing to do is a pairwise comparison。

And you can get it to one clearly out of less than M squared pair comparisons。That's not are you。

 Why do you say pairwise M。These are on bundles， remember， so for a demand query。

 remember the candidate answers are all two to the M bundles。For the m。

When you work out your value query as a business you're really asking like how much money can I make out to this bundle compared to like all the business I could implement Where power Well really in an absolute sense。

 Oh you're saying including the opportunity cost。Yeah， okay， But， I mean， still， I'd say here。

 there's a sense。I mean， there's a sense in which this is really an optimization。

It's almost like this is more just like a single estimate。 And I'm not saying that's always easy。

And it is an estimate might and of course， a real setting， you won't literally know this。

 you might hire a team of consultants and you pay them a lot of money and they'll give you their best guess so point definitely taken that this is not necessarily easy in practice。

You know， this， you know， I'd say people solve this approximately and people saw this even more approximately would be my take actually。

 Again， remember， this is optimization over a lot of different options。

But it's not optimization over things you can answer exactly， probably。Sure。Sure。But somehow， I mean。

 I'd say here there's an aspect of search。Through a big space， which I don't think is here so much。

this is a non formalal statement I'm making。嗯。Yeah， and there is a mathematical statement about it。

 which basically says， for any valuation， if you allow me the power to ask demand queries。

 I can answer any value query by invoking this appalling a number of times at different prices。

 and the con is false。Again， so now this is the math part。

 which you could know you could argue with the model， but I mean， these are true statements。

 So there are evaluations for which if I give you the power to answer value queries。

 you need an exponential number of them to simulate a demand query。

So there is a formal sense in which demand queries are only harder than value queries。 Again。

 in practice， you know， you can debate it。O。Good。Good， good， good。All right， so again。

So what's the high level takeaway of this discussion， So the first high level takeaway is just that。

 know when you start dealing with these abstract evaluation classes like gross substitutes。

You have to make some decisions about representation。 and they're annoying， but you have， know。

 you have to talk about it。 The second thing is， is just that for today， this is our model。 Okay。

 valuations are black boxes， each we can ask them a demand query。 We can ask them a value query。

 We count those as just one step of our algorithm。 Everything else is one step。

 And we want to be polynomial in the number of bidders in the number of items。 Okay that's the goal。

And the main results that I want to sketch a proof of in the time remaining is we can achieve that goal for welfare maximization。

With gross substitutes valuations。So theorem。With a black box， gross substitutes valuations。

Can compute the welfare， maximizing。Allocation。And hence running at n plus1 times。

You can compute the VCG outcome。In polyly steps。Poly of Nm steps。And queries。Okay。And so warning。

 I mean， this is， this is， I mean， the algorithms I'm going to give you is about as impractical as you could imagine。

 Okay， so this is a purely in principleable result。That now what but again。These gross substitutes。

 I mean， it's very abstract in general。 Okay， so to have such a general result。

 we have to expect pretty heavy machinery would be required。 Moreover。

 we'll see next week that if you generalize gross substitutes just a little bit， you cannot do this。

 so there are lower bounds saying you cannot get exact welfare maximization in polynomial time。

All right。So we're again going to use linear programming。

 but we're going to need a tool beyond what we've discussed already。

So who among you have heard of the ellipsoid algorithm， Raise your hand。

And who has not heard of the ill algorithm？5050， okay， that's about what I expected。So good。

So let me tell you a little bit about it。Basically， thisoid algorithm is total magic。

 That's the one sentence explanation。 Okay， so here's， all right。

 so there's certain kind of linear programs we can solve well in theory and in practice。

 And those are the ones that are explicitly described。😊。

So if you have a reasonable number of variables and you write down an explicit list of a reasonable number of constraints and it's a linear program。

 we can solve them in practice， we have pretty good theoretical bounds and so on。It turns out。

 at least in principle， we can solve linear programs which are not explicitly described in this way。

 Okay， and we can't use an arbitrary linear programming algorithm to do that。

 We have to use a special one called thelyoid algorithm。 So let me elaborate。And I should say。

 independent of this class， this is a tool worth knowing。

 if youre ever interested in proving in principle tractability results。

 poly contracttractability results。This， of algorithm can do things that pretty much of nothing else that we know of Ken。

 okay。And it's not，'s not a recent algorithms。 This was developed by Catian in 79。 But to this day。

 it feels very magical。😊，All right， so let me tell you。

Let me tell you the kinds of linear programs that the ellip algorithm can solve in polynomial time。

To consider linear program with。So the number of variables needs to be reasonable。Okay。

 so let's say capital N。Dimenssions or decision variables。Okay。And so just， okay。

 and so just looking ahead a little bit， remember。That in our prim linear program。

That we wrote down for welfare maximization。 We had a decision variable for each bidder in each subset of goods。

 So this is exponential in M。Okay， so it's not actually clear why thislipoid algorithm is yet going to be useful because that linear program already had too many variables。

 but bear with me。So two。Any number of constraints。 So this is the magical part。So concretely。

 think of the number of constraints as being exponential in the number of variables N。Now。

 it's the catch。So the catch is， it's important that these large set of constraints。

 It's important that you can efficiently search for one that is violated。 Okay。

 so this is called a separation oracle or a cutting plane in certain other contexts。So a poly times。

 so here polynomial means polynomial in n and the maximum number of bits used for any to describe any number。

So a polytime separation oracle。So what is this？So this is an algorithm。

That takes as input an alleged， feasible solution to this linear program。Okay， maybe it's feasible。

 Maybe it's not supposed to be feasible。 Someone claims it's feasible。

And the separation oracle is a verifier。转。It's supposed to be fast。

 but it's supposed to be able to figure out。Whether or not this purported。

 feasible solution really is feasible。 O now， if there's only a polynomial number of constraints。

This is really easy。Right， if you give me the alleged solution and there's a small number of constraints。

 I'll just check each one。 No problem。The problem is when there's an exponential number of constraints and you give me an a alleged solution。

 and I can't check them one by one。Okay， but。If it's the case that I can empower poly them all time。

 verify them all， then it's a separation of goal。 Actually， I need a little bit more。

If it's feasible。Then you can just tell me。I mean， you have to be correct。

 but you can just tell me that's feasible。Now， if it's infeasible， it's not enough to just tell me。

 O， I need a proof。But it's infeasible。By proof， I mean an inequality。

 which is violated by the alleged feasible solution。

So that's a separation oracle for a given linear program。Okay。

 so if I assign a number at each of the decision variables。

 I can invoke this algorithm either that says good job feasible or it says infeasible。

 and here's why。And should run on polynomial time。Linear programs that satisfy properties1，2， and3。

Can be solved in polynomial time。Not by any old linear programming algorithm。

 almost all linear programming algorithms need an explicitly described linear program。

 but it can be solved in polynomial time using the ellipsoid algorithm。

I when I say polynomial time polynomial in n。And the max number of bits needed to describe any number。

Importantly， independent of the number of constraints， that's the whole point。Okay。

So that's just a fact。 All right。 I'm not gonna to prove it。 If you're curious。

 I wouldn't be too frightened of it。 Like in a 75 minute lecture。

 I could give you the of this algorithm。 Okay， it's not kind of algebra geometry or something。

 Okay it's messy。 But the conceptual ideas are actually nice and understandable。 But for now。

 most practicing researchers just accept this on faith that this thing exists and then uses it as a tool。

 And you are welcome to do the same。 okay。😊，And it's good to know。

 You should know that this is possible。 I should also say that， you know。

 thinking in this way isn't necessarily， you know， have nothing to do with practice。 I mean。

 these separation oracles you know are used to these exact this exact same problem arises in so-called cutting plane algorithms。

 which can be very practical methods of solving integer programs。 Okay But for now。

 this is what we're going to use。All right， so any questions about that？I'll post。

 I'll try to find someones some good lecture notes on the Web and post them on the course site about the algorithm。

 if you， if you want to learn a little bit more about it。Okay。Then we're going to。

 we're just going to accept the di algorithm exists。

And now I'm going to show you a proof sketch of this theorem。Okay。

Why welfare max is possible to gross substitutes。 And again， remember。

 this is not going to be possible even a little bit beyond gross substitutes for so called even submodular evaluations。

 We'll talk about that next week。Alright。So proof of theorem。Alright， so what might。

 what might we apply the ellipsoid algorithm to。So we website algorithm， powerful， though it may be。

The running time does scale with a number of variables。And the linear program that we care about。

The prime mill linearar program， which remember we know is exact。 and they'll leave that over here。

So holds for GS valuations。So we're trying to prove something specific to gross substitutes valuations。

 right？ So we're actually going to use the gross substitutes condition in two different ways。 Well。

 know really one main way。 So the main thing gross substitutes is buying us is it guarantees that we don't actually have to solve an energy program。

 which would be scary。 We only have to solve a linear program， which is less scary。 Unfortunately。

 the linear program still has two to the two to the end decision variables。

 So it's not amenable to the ellipsoid method。 However。So if you remember that linear program。

 I'll write down the dual again， I won't write down the primal again。But in the primal。

 we only had one constraint for each bidder saying I got it most one bundle。

 And we only had one constraint for each good， saying it's only allocated once。

 So the number of variables may have been big， but the number of constraints was small。

 just n plus M。So not coincidentally， in the duall， we had a small number of variables。 Okay。

 the U Ys and the PJs。 Yeah， we had a ton of constraints。

 but then we're in the wheelhouse of the elloid algorithm。Okay， so the idea is， okay， first of all。

 gross substitute says we only need to solve linear program。 Second of all。

 the dual has few variables。 Let's try to nail it with the elloid algorithm。Okay。So， step 1。

So try to solve solve dual LP or apply lipssoid。And it's actually going to be important to remember what this is。

So minimize some of the UIs。Plus to sum of the PJs。Subject to UI plus sum。

 so basically every valuation should be covered。And again。Better to think of this as UI， at least。

Max S。V I。S minus sum J and Sj。And non negativity constraints。So apply episode to the dualLP。

So the big question then is， do we have a separation oracle？For this dual LP。

 if we have a separation work that runs of polynomial time。

 then the  ellipsoid algorithm will solve it in polynomial time。

That's what the ellsoid algorithm does， it reduces solvent EP to just designing the separation oracle。

So let's think about the separation or cool。So given an allegedly feasible dual solution。

 you comm a P。Well， the non negativity constraints， this is there's only a small number of them。

So we just directly check that we only are given non negative numbers。

Let's look at these constraints。 Okay， so remember， the V's are just part of the data。

And we were just given these allegedly feasible U's and Ps。Okay。So this is for all I。嗯。

So there's only I bidders。 no big deal。 We can enumerate over the n choices of I。

 The scary thing is that there's these two to the M possible S's。😰，Okay。

But because these are all just lower bounds， O， because each S just gives us a lower bound on U I。

 We just have to check that U I is as big as all of the lower bounds。 I。e。

 is big as the biggest of the lower bounds。And this looks pretty familiar。Right。

This is actually just a demand query。So the maximum over of this is just saying， look。

 amongst all the bundles you could buy at the price is P， which one maximizes your net utility。

That's a demand query。So by assumption， by assumption that devalation， this may seem like cheating。

 but you know， if you believe demand if you're thinking about a world where demand queries can be answered quickly。

Then with one demand query， you can in one fell swoop， figure out which set achieves this maximum。

Okay， that's what a demand query does。Now， given this set S with a value query。

 you can just figure out what this number is。 You have those numbers。

 You can just compute what this largest possible right hand side is。

 and you just compare it to you sub buy。Is that。So a demand query lets you evaluate the right hand side。

 you just compare this inequality， theres in such inequalities， and you're done。

But given it a bit you have to do demand Curry has to search to the possible。Sping two then like。

 isn't it just offsetting the computational cost to the them Well it's really so it's a good comment。

And in in fact， yes， okay， it is sort of pushing。 It's sort of delegating the computation to the bidder。

You know，So a couple of things I'd say。 So first of all， you know， you could think about。

 So there's a relationship between these two different， the second approach and the third approach。

 Okay， so you could ask the question no， is a query reasonable or not。And you can ask。

 how would you make the case that a given proposed query？

Was a sensible thing to include in the model or not。

And you could use both not mathematical and non mathematical arguments to do that。

 The mathematical argument would say， well， you know。

 consider all the concrete representations we actually might use， You know， unit demand bidders。

 you know， downward sloping valuations， K unit demand。And you might argue， well。

 in any of those concrete implementations， representations。

 we can implement these queries in polynomial time。Okay， so think， for example， about you know。

 K unit demand。Well I mean， let's， mean， let's start with unit demand。 Okay。

 so demand query is very easy for a unit demand betterder to implement， right。

 It just goes through the different。Items， and it just does brute force search basically。

If it's K unit demand， so that's when you're happy to have up to K goods， then you would just。

 you know sort things by VI J minus PJ and take the top K。Now， implicitly。

 you are searching a space of size 2 to VM。Right，There really are kind of M different bundles you might pick。

 But somehow for that valuation， the only relevant ones are the prefixes。

 So the effect of search base is much smaller。So this would be how mathematically you might argue that a given query is reasonable by saying by actually giving explicit poly andno time implementations of it for representations you care about。

Now， full disclosure， there do exist， not super you。

Somewhat reasonable concrete representations where it's MP hard to evaluate a demand query。

So the mathematical， you know， evidence， I think， is sort of a little bit mixed on demand queries。

 Often they're efficiently implementfable。 Sometimes they're not。 So for demand queries。

 a big part of the argument is just non mathematical。 It just says， you know。

 this is just kind of in an auction context。You know we're thinking that bitterders can answer questions like this and we already asked them to do this in complex auctions as it is。

But Mad， the comment's a good one。Okay， we really are。 But， I mean， I mean。

 from a modeling perspective， what's helpful is it's sort of。You know。

 isolates the relevant exponential search， okay， because。

Because at least it's just sort of one bidder making a kind of local exponential search。 right。

 So something which is intuitively much harder would be okay。

 if I have N bidders and I have M goods to split amongst them。

 right there is an exponential number of allocations。 But sort of now。

 the number of bidders matters as well。So at least this kind of reduces just saying locally each bidder should do its own exponential search within its preference space。

 which arguably is still some kind of reduction in the computation required。Yeah。

 it's a good comment。 It's a really good comment。O。Right。

 so the upshot is assuming that demand queries can be implemented efficiently。

 gives us a separation oracle that can be implemented efficiently。

 and then feeding that into the ellipsoid algorithm that allows us to solve the dual linear program in polynomial time counting demand queries is one step。

So， use demand queries。To check the rest。Okay。All right。So that's what we just did。 Okay。

 we looked at the dual linear program， and we use the assumption that we can solve demand queries to solve it optimally。

So step 2。So by strong duality， now， remember， we don't really care about a dual solution per se。

 Okay， we passed to the dual because that's what had small dimension。So now we learn that， you know。

 the optimal dual solution has objective function value 1322。 Okay， So what？ Well。

 we do have strong duality going for us。 So we know that the value， Okay。

 so now at this point in the algorithm， we know what is the maximum attainable welfare。

 We don't know how to attain it。 but we know it's 1322。 Okay， because we solve the dual optimally。

So by strong duality。Know the value。Of。Opt of the prim linear program， which byg substitutes。

 is the optimal solution to the integer program。 I either welfare maximizing allocation。Okay。

And now step 3。 So now I don't know if you've seen this before， but in general。

For so called self redducible problems， which is most of the problems one thinks about。

Given an oracle telling you the value of an optimal solution by invoking it over and over again。

 you can actually reconstruct an optimal solution。Okay， so one really one sort of one pretty。

 so like satAT would be one example， suppose suppose I gave you an oracle that just told you whether or not a formula was satisfiable or not。

Invoking that over and over again， you could reconstruct a satisfying assignment of a satisfiable formula。

And if that's something you've never thought about， that's a good thing to think about。

 so I'll put this on the exercise set。So step 3。 So again， what's the context。

We know the welfare we're shooting for。 We know the best we can it was exactly 1322。

 The question is just who gets which good。And again， like for example。

 what you could do is you could take good number one， you could try giving it to bid number one。

 and then you could solve the residual problem。O， and look at the well further residual problem。

 Again， if you don't like the answer， you could go back。

 You could backtrack and try giving good one to somebody else instead and so on。

So use this oracle sort of over and over again to guide your search to sort of guess what the optimal solution has to look like。

Okay， so again， I want to， so I should emphasize this step is where we're using the gross substitutes property。

And so we're using it with gross substitutes while re equilibrium exists。

 we prove that using Kelso Crawford， And then we argue that that implies that this is also the optimal integer solution。

So use self reducibility。To reconstruct。A welfare maximizing。Allocation。All right。

So let me just sort of tell you where we're going。 So this pretty much completes。

 there's lots more one could say， lots more cool stuff， but there's just too many of topics to cover。

 So this is pretty much where we're gonna wrap up with sort of non-mp hard detractable special cases of allocating resources to maximize welfare。

 It's also going to be pretty much the last well that's not quite true but because the problems get harder。

 we'll actually look at more modest schools。 So it's even going to be interesting to look at direct revelation D implementations for the next couple weeks。

 we won't talk about ascending options quite so much。

 I guess I didn't close the loop and tell you about ascending options for gross substitutes。

 the picture is actually a little murky so I don't want to talk about it right now。

 but I'll open with a few comments next week and then we'll start looking at two more valuation classes submodular valuation functions which in some sense are just a step beyond gross substitutes and we'll see a lot of the things that get harder。

 I also want to talk a little bit about compliments。 So when there are synergies between。Goods。

 those are also relevant in practice。 So I'll talk about a notion of restricted compliments where there's some pretty juicy open questions about dominant strategy implementations。

 So I'll leave it for the day and see you next week。

