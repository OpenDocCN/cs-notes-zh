# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p17 NETS 4120_ Algorithmic Game Theory, Lecture 17.zh_en -BV15kLRzTExU_p17-

一想技的。

![](img/37e96de51f194eda24f6fb714fd9f82c_1.png)

Yes，对。So let's continue our study of mechanism design， so just to briefly recap。

We learned about the VCG mechanism， which。In some sense。

 solves a huge fraction of the problem space and mechanism design right we you could define these sort of arbitrary。

Spacees of alternatives you could choose between this captured not just single item auctions。

 but complicated multi unit auctions with constraints。

 public projects problems and the VCG mechanism。No matter what。

 would solve those problems in a way that maximized welfare was dominant strategy incentive compatible。

 was budget balanced and was individually rational。嗯。And we ended that lecture。

know it was sort of a remarkable result but we ended the lecture by sort of complaining about the things that it didn't do。

Now one of those things was handle objectives other than welfare。

 and we spent last lecture characterizing。Exactly when you can and cannot implement truthfully some objective。

 and it turned out to be exactly when the corresponding allocation role is monotone。

But there was another problem with the BCG mechanism that we sort of hinted at。

 which is that even when you're objective。Is welfare even when the thing that you care about is choosing the alternative that maximizes you know this utilitarian。

Some。Happiness subjective。That。Sor of step one in the VCB mechanism。

 this this step that when we were talking about it we didn't dwell on very much was just。You know。

 like choose the alternative that maximizes social welfare right like like in the VCG lecture。

 the way we were speaking about this was that the allocation rule wasn't very interesting if we wanted to maximize social welfare our hands were tied we had to just choose the welfare maximizing allocation and the only thing to focus on was the payment rule。

And that's true as far as it goes but。You know this this problem of maximizing welfare。

 which is easy enough to write down， choose the alternative that you know maximizes some bitter valuations if the space of alternatives is very big and complicated。

 this might be easier said than done。Like this is not necessarily a computationally tractable task。

And so。The question I want to ask in this lecture is。

What if we're in a setting that is in principle solved by the VCG mechanism。

 we want a truthful mechanism， you know it's budget balanced。

 individually rational all of those nice things， and indeed the thing that we care about is maximizing social welfare。

 but we just can't solve this problem exactly because it's complicated， suppose it's NP hard。Okay。

 like like what do we do in that case？And。If you've taken。An algorithms class。

 a natural idea you might have at this point is。You know， you might say， look， sure。

 there's plenty of complicated problems that we can't solve。Exactly， and some of the。

Real world auction problems we've hinted at like auctioning off pickoff and landing slots that American airports are auctioning off radio spectrum across the United States are examples of such problems like their NPR。

 not just。You know， in principle， not just in the worst case。

 but like we really don't know how to solve these problems。

 the real instances of these problems exactly。But。Like often we can get pretty good approximations。

Right， like either maybe you have like an algorithm that there's an approximation algorithm that has some provable approximation guarantee。

 say it always gets you within 99% of the optimal welfare or maybe you don't have that。

 but you've got pretty good heuristics， you know you write down and enter your program and you run CPX sonnets and it you know gives you a pretty good solution。

So。If the only thing you were interested in was solving the algorithmic problem。

 then that would be great， you'd be done， right， you sort of try to solve your energy program。

 you sort of give a best effort solution and to the extent that it approximates the optimal objective within 99% like you're super happy。

But the problem is like。We're solving a more complicated problem than the algorithmic problem。

 We're solving the mechanism design problem and。Our allocation rule interacts with our payment rule in very delicate ways。

 So if you sort of remember how our analysis of the VCG mechanism went for every single statement we proved。

 you know， like that it was dominant strategy truthful that it was individually rational that it was budget balance at some point we relied on the fact that。

The thing we were computing， the allocation we were computing was exactly the thing that maximized social welfare。

And if you just sort of naively plug into that。😡，A solution that is。99% optimal。

 but not 100% optimal then。All of those guarantees can break catastrophically。

 it's not that if you approximate the welfare objective that your approximately dominant strategy truthful or approximately budget balance things can break catastrophically all of your payments can become negative。

 for example。Okay， so like the problem is。U。Our analysis of the VCT mechanism。Like in particular。

 its incentive properties really delicately depended on exactly solving the optimization problem and so。

We need something more clever than just sort of plugging in our， you know。

 state of D approximation algorithms when we encounter。

 you know like a computationally hard allocation problem。Okay， so this is sort of the problem。嗯。

That's what I want to point out and for the。Rest of the class what i'm going to sort of walk through is a particular case study。

 something I'll call Napsack auctions that you know is an example。

 an example of working through a solution to。One time this can arise， but more generally。

You should think of this as an exemplar， like there's all sorts of hard allocation problems beyond what we're going to see today and you'd need to go through a similar exercise for all of them。

So let me stop here and just ask。Whether the problem that we want to solve makes sense。

Like the VCG mechanism。With great， but like。We just assumed in the analysis that we could solve this optimization problem。

 we didn't think twice about it。The setting we were operating in was very general。

 so the set of alternatives could be extremely large right if I'm giving out。Bundled。

 even just for even just for auctions of goods where I'm selling stuff to people， you know。

 if I'm selling K items。But you might want more than one of them。

Then there's two to the K bundles that any particular person could get。 It's you know like。

Very quickly it becomes impossible to just enumerate all solutions and so you need a more clever algorithm for this and sometimes they don't exist。

Okay， so is the problem clear？Yeah。对。Yeah， so if you sort of。Revisit the proofs for why， for example。

 the payments are always positive right like we're sort of subtracting you know what are we。

We end up sort of comparing the。You know， your。Negative externality。

 we were looking about your negative externality by entering the auction。

 So we're sort of looking at the difference between。

The exactly welfare maximizing solution on everyone else。

 assuming you did participate and the exactly welfare maximizing solution on everyone else。

 given that you did not participate。And。Since it's a difference。Um you know， so that's first of all。

 that's two of these NP hard problems we might have to solve what's the welfare maximizing solution with you and and what's the one without you。

And suppose we solve the first one to within 99% of optimal。

 and we solve the second one to within 99。5% of optimal。All of a sudden， like。

The magnitude of the difference can change by quite a lot。食 makes三。Okay， so is the problem clear？

Okay， so as our sort of case study in thinking about this problem。

I want to think about something called a NapsAC auction。

 which is related to the NapsAC problem in combinatorial optimization that you might have been captured before。

That is the following。We've got N bidders。And maybe just to have like a concrete example in your mind as I'm describing this。

 maybe think about the problem of auctioning off airline seats on like airplane seats on like a particular airplane okay。

 so there's like like what's going to happen is I've got a particular number of seats on my airplane。

And I've got different。Groups of people who want to travel on my airplane but you know each group might have a different size。

 so there might be sort of solo business travelers there might be families of five there might be like a volleyball team it's got however many people a volleyball team has on it。

And the point is none of them want to be。broroken up across different trips right like if I have a family of five I'm not I don't want like you know four tickets on like this airplane and then I send my two year old on like the following one。

Okay， so maybe this。Is something you can keep in mind just as an exemplar as we talk about the abstract problem。

So we've got n bidders， think of each bidder as know one of these parties who'd like to get airline tickets。

And they each have a publicly known size， which I'll call WI and think of as the number of members of the party okay there's the family of five。

 they have size five， there's the solo business traveler， they've got size one。

 there's the volleyball team that's got size equal to how many people are on a volleyball team。Okay。

 so this is we're going to assume that the size is not something that people are going to like misre。

 like I'm not going to try to like only buy four airline line tickets。

 even though secretly I need five like the size we're assuming is like publicly reported。

And the mechanism has what I'll call a public budget B。

 which you should think of maybe in this example as the number of seats available on this airline。

 like maybe there's 100 seats to sell。And。What I can do is I can you know。

 I can decide which of these。Parties， which subsets of these parties get to fly on my airplane。

 but like subject to the budget constraintsst。So the set of feasible alternatives in this mechanism design problem are all subsets of bidders whose cumulative size is at most be。

😡，Okay， so I can serve any subset of these parties such that the total number of airline seats they need is less than B the number of seats on my airplane。

Like this。Okay， so this is subsets of n items， so we're talking about a sort of a we're starting to talk about a comminatorarily large set of alternatives。

 there might be lots of subsets of N items。And just notally。You know。

 like an alternative written this way is a subset of the bidders。

But let me abuse notation a little bit and pretend that a is like a vector。

 just the indicator vector for the subset。 and I'll just write AI equals one to mean that。

Party I is served Bi eye is one of the winners of the auction and AI equals zero otherwise Okay。

 so AI will just be like an indicator one or zero specifying whether they were one of the winners of the auction or not。

And。We're going to think about these as single parameter domains where we sort of imagine that everyone prefers to win the auction。

 then to lose the auction， and if they lose the auction， they don't care。

Which subset of people want it？And so the only thing that we don't know is what their value is for being served。

 so every agent， every bidder will have this sort of secret， this private number VI。

 and if I choose alternative a，Bitter eyes value is VI times AI。Which just means their value is V。

 if they win， they get to go on the airplane and take the trip， and it's zero otherwise if they lose。

Okay， and the reason I'm writing it this way is because。

I want you to see that this problem is a single parameter domain as we talked about last class so that we can use our characterization for last class about what we can what our design space is for this coming up with a truthful mechanism。

Okay， so is the problem definition clear， is it clear what a Napsack option is？ok。

So the reason these are called NapsAC auctions is because the welfare maximization problem。

 which the VCG mechanism would need to solve， which is just find the feasible find the sort of set of feasible allocations that maximizes。

The total value amongst the agents subject to my budget constraints right this is just the welfare maximization problem。

Um， is like a famous combinatorial optimization problem you've probably seen before in like an algorithms class called the Napsack problem and it's NPhar。

Okay so。Like in particular， like since the allocation you know。

 this is the allocation rule for the VCG mechanism。

There is no polynomial time algorithm probably for implementing the VCG mechanism for NapsAC auctions and if we want to have a polynomial time mechanism for solving Napsack auctions that has nice incentive properties。

 we're going to have to come up with something else。Okay， so this is。

A concrete exemplar of the kind of issue。We were just talking about where。

The VCG mechanism would be great if only you could run it。

 but we don't have polynomial time algorithms for running it in this case because the welfare maximization problem is a combinatorarily hard problem。

Makes sense。O。So。You know， like what should we do？If our goal is to come up with a polynomial time algorithm that has the incentive properties we want。

Well。You know， of course， we can't。Hope to exactly maximize social welfare anymore since we know there aren't。

I forget the incentive properties there aren't polynomial time algorithms that exactly optimize social welfare in this problem。

 but like okay， our goal is to。Have an approximation algorithm that always approximates the social welfare objectives。

But we'd like to pair it with a pricing rule that makes truth telling dominant strategy to full and hopefully also is individually rational and budget balanced and has the other nice properties of the VCG mechanism。

And we know that like we can't just pick our favorite approximation algorithm for an Napssac and parrot with the VCG pricing rule in fact。

 we can't you know like。We can't even compute the VCG pricing rule。

 like to figure out the prices for the VCG mechanism。

 you also need to solve the welfare maximization problem。

So we need to come up with an approximation algorithm for NApsAC。

And we need to pair it with a pricing rule that makes truth telling dominant strategy that makes truth telling a dominant strategy。

And so。Like naively， if we hadn't。If we hadn't had last lecture， this might be a tricky problem。

Because coming up with an approximation algorithm is live。

already kind of a hard problem on its own and like somehow we would need to like simultaneously come up with an approximation algorithm with it together with a matching pricing rule that makes truth tellingling a dominant strategy。

But because this is a single parameter domain and because we had last lecture。

We actually don't need to solve the pricing problem。Right。

 like what did we learn last lecture we learned that。An allocation rule。

Can be made dominant strategy truthful。You know， meaningan can be paired with a pricing rule that makes truth telling a dominant strategy。

If and only if the allocation rule is monotone non decreasing。

like last lecture was sort of a reduction from a mechanism design problem to an algorithm design problem that is if our allocation rule is not monotone non decreasinging。

 then we know that we don't have to try to think hard about pricing rules。

 they just don't exist There are no pricing rules that make non monotone。Alllocs truthful。And。

If we do have a monetary of allocation rule， we also don't have to think hard about pricing rules because the pricing rule was given last lecture generically。

So。To solve the Napsack auction problem。We just need to solve like a well defined algorithm design problem。

We need to come up with an approximation algorithm。

For an Napsack problem that is monotone non decreasing。Okay。

 it's just like another constraint on our algorithm design problem， okay， some algorithms。

Some approximation algorithms are monoton none decreasing others are not we need to if we want our algorithm to be。

Able to be turned into a mechanism that is dominant strategy truthful。

 we need to figure out an approximation algorithm that does have this monotone non decreasing property。

Okay does that make sense， so we're getting sort of a lot of mileage out of this characterization from last class。

 it's making the problem we need to solve here a lot simpler。Is that clear？Okay。

 so let's review maybe some basic definitions let me remind you。What an approximation algorithm is。

 let me remind you what the monotone non decreasing constraint looks like in this setting and then we'll think about how we might be able to achieve both of them together。

So first， maybe some notation。You know， like what's an instance of。

The Napsack problem or what's an instance of an Napsack auction？Well， for each of these n bidders。

I need to tell you two numbers， I need to tell you what their value is。

 and I need to tell you what their weight is， much how much do they collectively value flying on the airplane and how many people are there in their party？

Okay， so I can think of them both as vectors right like V specifies。

The value for each of the n bidders and W specifies a weight for each of the n bidders。Okay。

 so if I give you these two vectors， V and W， I have communicated to you an instance of an Napsack problem or an instance of an NApsSAC auction。

And so let me write opt of V W。As my notation for the value of the optimal solution。

 for the instance of the Napsack problem given by V and W。It is just the social you know。

 it is just the social welfare maximizing is the social welfare of the social welfare maximizing solution of that instance。

 okay， so it's just the maximum among all feasible subsets of bidders。

 all subsets of bidders whose weight is below the budget。Of the。

Social welfare obtained by that solution。Okay， so like。On every instance。

 the VCG mechanism would obtain social welfare optive VNW， we would like to do that as well。

 except it computationally hard。So since we are going to want to design a polynomial time algorithm。

 we're going to have to settle for something that doesn't always obtain this benchmark value opt。

 but we'd like it to not be too far off。So we'll say that an algorithm。

 which takes us input an instance of an Napsack problem and outputs a solution， a subset of bidders。

Is an alpha approximation algorithm for the NApsite problem。

No matter what instance we plug into the algorithm for every instance defined by V and W。

Two things should be true。Like first， it should always output a feasible solution。

 it should never sell more tickets than there are on the airplane。And。Second。

The social welfare of the solution it produces should always be。

Comparable to oxs should always be at least the value of the optimal social welfare solution divided by alpha。

So for example， if I say I have a two approximation algorithm。

 that means that the algorithm always is guaranteed on every instance to output a solution whose social welfare is at least half of that of the optimal social welfare。

Does that make sense？So， you know。The VCG mechanism。Would be a one approximation algorithm。

 but it wouldn't run in polynomial time。Our goal is to come up with。

An algorithm that does run in polynomial time and is an al approximation algorithm for hopefully some value of alpha that's not too big。

Make sense。Okay， so we want to come up with an Al approximation algorithm and so that we can pair it with a payment rule that makes truthful reporting a dominant strategy。

We'd like to make sure that our algorithm is monotone non decreasing。

So let's just remember what that means in the context of our problem here。

What monotone non decreasing means is that。No matter what the instance is of the NapsAC problem。

 fixing any V and W。And no matter what bitter eye we care to look at。

If bitter eye raises their bid from VI to some higher value VI prime。Well， generically。

 the monoonicity property means that bitter eye should get an allocation that they prefer。

And since here， there's only two things they care about either they。

Win the auction and get their airplane blind seas or they don't。 All Monteity means here is that。

If at bid V， I am a winner in the auction。 I get seated on the airline， then。

I should also get seated on the airline at a higher bid V prime。

It should never be the case that I can raise my bid and go from winning the auction to losing the auction。

The reverse can happen right it could be that I can go from losing the auction to winning the auction by raising my bid。

 but it should never be the case that at a lower bid I would have won and at a higher bid I do not that is the monotononicicity property we want to enforce on our algorithm and if we can come up with an approximation algorithm that satisfies this monotonicity property than we know from last class how to pair it with a payment rule that makes truth tellingling a dominant strategy。

Okay， is that clear？Okay， so for the for the rest of the lecture we're going to like ignore prices and incentives and just rely on last lecture for that right like last lecture we proved that this property on the allocation rule is sufficient to handle all of the incentive issues and we're going to take advantage of that and for the rest of this lecture we're just thinking about approximation algorithms that satisfy the monotononicity property。

Okay。O。So let's start thinking about how to think about approximation algorithms。

So I want to start by。Doing something that sort of is just syntctic Im going。Not do anything clever。

 I'm just going to reexpress thenapsack problem as。An integer linear optimization problem。Okay。So。

Say that I'm optimizing over these variables X， for one for each of the bidders。

 Okay so there's n variables X。That are Boolean， they are either zero or one。

And the meaning of Xi is that if Xi is1。That means that。

Party I is going to be seated on the airplane， party I as a winner of the auction。And if X I is 0。

 then they're not， they lose。ok。So in this case I can just reexpress the Napsackack problem。嗯。

In the following way， where there's like this linear function that I would like to maximize。

 subject to a linear constraint。Okay， my goal here is to find values of the excise。

 winners and losers of the auction。So that I maximize the sum over all of the bidders of Xi times V。

Well， what is that？It's just the sum of right like if X is zero， then this term just zeros out。

 so this is really just the sum over all of the I such that XI is1 of V。

Which is just the sum of the values for the people who win the auction。

 which is just the social welfare。Okay， so I'm trying to find an allocation that maximizes social welfare。

Subject to the constraint that the sum over all of the bidders of Xi times WI is less than the budget。

Again。If Xi is0。Then the corresponding term just zeros out。

 so the sum is just the sum over all of the bidder's I such that X is one。

 all of the winners of the auction。Of their weight。So this is just saying。

I want to maximize social welfare， but subject to this constraint that。

The set of people I allocate the set of people I decide are winners must have total size that does not exceed my budget。

Yeah。喂。对。对方。Oh so VI is just you know however much your party values getting on the airplane right so like it might be that the volleyball team that has however many people are in a volleyball team in it has a very high value reflective of the fact that there are probably lots of people on a volleyball team。

Okay， so it's not like。VI is， you know， zero or one。

 like it might be that the bigger parties have correspondingly bigger values。But maybe not， right。

 like maybe。Even though the family of six going to。Bca Raton， Florida， you know。

 there's six people in them like maybe their value for that trip is actually less than the value of like the。

Business traveler who's going to close his like series A round and。Menlo Park or something。嗯。

So anyways， yeah， like there's， we're not assuming any relationship between the value of the party and the size of the party。

 but there certainly could be film。Other questions？Yeah。听响。

That's an input to the problem right so every bidder has a value how much they how happy they are if their party is seated on the airplane and the size。

 how many people are in their party。So an instance of the problem is given by VI and WI。

 and I'm just writing down， this is just a different way to write down like the NApside problem。

 I want to maximize social welfare subject to a budget constraint。Okay， make sense。Okay。

So like so far I haven't done anything I've just written down the problem in this form。

 this is called an integer linear program and it's not like I can just solve this。

 like the fact that I'm able to express the Napsack problem as an integer linear program is actually proof that integer linear programming too is NP hardD right so like I've just expressed this in a you know only more general optimization framework but it is like also NP hardD。

 but like are we all on the same page that this is still the Napsack problem。Okay。

 so like solving the inter problem is empty hard， not clear what to do about it。But。

 but let me sort of make a。Philosophical points。Like。When a problem is NP hard。

 of course that so most directly， that means we shouldn't expect to have a。

Polynomial time algorithm that can solve it but。It also kind of means that we shouldn't expect to be able to。

Productively reason about the structure of the optimal solution somehow。

This isn't a rigorous statement。 This is sort of a moral argument。

 but somehow we should expect that like。NP hard problems don't have lots of tractable structure around their optimal solutions。

 because if they did， we could exploit that structure to come up with efficient algorithms and there are no efficient algorithms。

 so probably they don't have that structure。Now our problem here in trying to come up with an approximation algorithm to an NP hard problem。

Is that。We need to prove a theorem。That relates whatever are。

Algorithm is going to do to the optimal solution to every problem instance。And so even if you know。

 like even though we can't solve this problem， like and our intention is not to exactly solve this problem。

We need to prove a theorem that somehow grapples with the optimal solution to this problem。

 And so mathematically， we're going to need to exploit some structure about that optimal solution。

 it seems and。Like maybe we should be worried about that because probably optimal solutions tend be hard problems don't have a lot of structure。

O。😊，So that's like。One reason for。Having a little bit of anxiety at this point。And so instead。

What I want to think about is。A relaxed version of the same problem。

It looks very similar to what was on the last slide。Okay， we still have these。

 we're still an optimization problem over these variables， X。One for each bidder。

We're still maximizing the same objective。The social welfare objective。

We're still subjecting ourselves to the same constraint， this budget constraint。

The only thing that's different is that these variables used to have to be either zero or one。

 they were binary， you had to either assign someone as a winner to the auction or not。

And now I've like relaxed that constraint， I say these variables can actually be real numbers that take values between zero and one。

Okay， so this is a。You know， syntactically very similar problem to what was on the last slide。

 but has this important difference， like the solution will no longer be。

Integer like a it's no longer clear what problem this optimization problem is solving because this。

 you know， like if， if your party gets， you know， if your party I and you get X I is， you know， 0。23。

 like what does that mean。嗯。And we'll have to pick about that。But。

The reason I want to think about this problem is that this problem。Is called a linear program。

 is' an instance of a linear program。And。😊，This problem is solvable in polynomial time。

 We know how to solve linear programs sufficiently。 So somehow the thing that was making。

The thing that was making thenapsack problem hard， it wasn't these like linear constraints。

 it was this constraint that the Xs be integers that they'd be either zero or one。

 and if we get rid of that，Of course， it's no longer clear what we do with the solution。

 like it's not a solution to the NApsack problem anymore but。

This kind of problem we have efficient algorithms for。

Now this is going to get back to the moral point I was making。

The thing that I want to do next is not just solve this linear program because。

It's not clear what we would do with the solution to this linear program。

 it gives fractional allocations and we're not allowed to do that in the real problem。

But the reason I want to the reason it's going to be useful for us to think about this linear program is because。

Related to the fact that linear programs are solvable in polynomial time。

 the optimal solutions to linear programs have some nice structure。

 and that's going to help us think about them。ok。So let's call this the fractional problem。

 This is like the fractional NApsack problem。 and the reason I'm calling it fractional is because。

You know， a solution to this problem might now assign a party like a。You know。

 fraction of a seat on an airplane。Yeah。3 again。Good， good question， good question。 Yeah。

 so let's give a name first to the optimal solution to the fractional problem。 Let's say that opt F。

given an instance， V and W， let's say that optt F is the optimal value of the fractional problem。

Okay， so。This is not problem this is not directly the quantity we care about。

 we want to solve the integer problem， but I want to make a claim， a simple claim first。

 which is that for every problem instance， for every instance of the NApsack problem given by V and W。

 the optimal value of the fractional solution is only bigger than the optimal value of the integer solution。

 and can you tell me why？Yeah， exactly。The fractional version of the problem is only less constrained。

Like before the original problem required that these Xs be either zero or one。Well。

 if the Xs are either zero or1 in particular， they're between zero and1。

 so something that was a feasible solution to the originalnapsack problem is also a feasible solution to the fractional relaxation。

 but the fractional relaxation might have more solution。So in particular。You know。

 the optimal solution to the Napsack problem， the optimal solution to the integer version of the problem is a candidate feasible solution to the fractional version。

 so certainly。The fractional optimum can't be smaller than the integer optimum。

 but it could be bigger because there might be solutions that really take advantage of this fractionality that get even higher objective value。

Okay， so yeah， so sort of as a simple relationship between these two。

 we know that if we have an instance of the Napsack problem and then we take its fractional relaxation。

😊，All we've done is we've made the optimal value larger， not smaller。Makes sense。Yeah。Okay。So like。

How is that useful to us， right？Like we need to come up with a solution to the original problem。

Like our goal is to be able to find a solution such that we can prove that it always has welfare at least to opt over Al。

Now that might be hard to prove because we don't really understand the structure of optimal solutions to the integer problem。

But if we can prove the stronger theorem。That we always get at least an alpha。

Approximation to the fractional version of opt。If we can come up with an integer solution。

 whose welfare is always at least the fractional optimum over alpha。Well。

 since the fractional optimum over alpha is at least the integer optimum over alpha， we will have。

Accomplished what we wanted to。 we will have come up with an alpha approximation to opt。

Does that make sense？So we're going to actually try to prove a stronger theorem than we need。

 not only do we get are we going to try to aim for an alpha approximation to opt。

We're going to try to aim for an alpha approximation to the fractional version of about。

It's a stronger theorem than we need， but it might be easier to prove because we can take advantage of the additional structure that the fractional version of OpT has and since it's a stronger theorem than we need it implies the theorem we want。

That's going to be the strategy。That makes sense。Okay。So like this whole。

Plan is like premised on the assertion that。The fractional problem has nice structure in its solutions space。

Okay， so let's like。See if that's actually true。SoSo here's going to be like the structure of the fractional problem we take advantage of。

 the simple structure of the fractional problem。Okay。

 so fix any instance of the Napsack problem V and W。And。

Let X be an optimal solution to the fractional relaxation of the NApsite problem。Okay。

 so X maximizes welfare subject of the budget constraint。

 but it might like now fractionally assign people's seats。

So then the claim is that x must have the following structure。Pick any two people I and J。

Such that when I compare。Like the what I'll call the value density for I by which I mean。

Their value divided by their size。Okay， so the business traveler who really wants to get to Menlo Park to close his series A has very high value density because his value is very high and his size is very small。

 the family of 12 that wants to go to Boca Raton， Florida but they're not going to really enjoy it because there's so many kids。

 they have very low value density because their value is small and their size is large。

And the claim is if I have two bidders I and J， such the bitter I has higher value density than bidder J。

Then。If in the solution， Bi J is assigned。Any seats at all， even fractionally。

Then it must have been the case that we fully satisfied the demand of bitter eye。

That is we won't satisfy the demand of any bitter J。

Until we have fully satisfied the demand of every single bitter eye who has higher value density。

That's the claim。Okay， this is a claim that like optimal solutions to the fractional problem have to have this structure。

Does the claim make sense？Okay。So let's prove。So suppose this were not the case。

 what would that mean？That would mean that there was some instance of thenapsack problem given by V and W。

That had an optimal solution X。Such that。There was a pair I and J。

 such that indeed I had higher value density than J。But in the optimal solution。

 Bi J had their demand partially satisfied。Satisfied to a degree strictly greater than zero。

And bitter eye。Demand might also have been partially satisfied but was not fully satisfied。

 This is the thing thelemma says shouldn't happen。That I has higher value density than J。

 but X is not fully bitter I is not fully satisfied and bitter J is already partially satisfied。

Suppose that were the case。Then let me define like what's the strategy of the proof here just to like look。

A step forward。We want to say if this is the case。Then I can find you a different solution that is also feasible and has higher welfare。

And that's a contradiction because x is supposed to be the optimal solution。Okay， so our goal。

 if we're given such a solution is to perform a little surgery on it to like actively modify it while maintaining the feasibility conditions and strictly improving the welfare。

Okay， that'll be a contradiction because the premise here is that x is the optimal solution。

 so I shouldn't be able to do that。Okay。So I wanted to define this number delta。

 which is going to be the smaller of the following two quantities。

It's going to be the smaller of X J。And1 minus X weighted by the ratio of bitterized size to bitter j's size。

And for now， the only thing I want to notice about this quantity is that it is positive。

 it's strictly positive。Why， well， by assumption， xj is bigger than zero。And X is less than1。

 so one minus X is bigger than  zero。 So we're taking the minimum of two terms that are positive。

 so this is some positive number。Okay， so I want to define a new solution X prime。

And argue that it is feasible。And that it has higher objective value than x。

 and that's going to be my contradiction that'll contradict the optimality of x。Okay。

So here's how I construct a new solution X prime。So first of all。

 like what I'm going to do is I'm going to mess with the allocation to bitter I and to bitter J。

 I'm not going to mess with anyone else's。So for any bitter L that is not I or J。

 their allocation in x prime is exactly the same as their allocation in x。

The only messing I'm doing is between bitter I and bitter J。

Now what I'm going to do is I'm going to give bitter J。Slightly less stuff。

 I'm going to lower the allocation to Bi J， I'll subtract Delta off from it。

And I'm going to give bitter eye slightly more stuff。

I'm going to increase the allocation I'm giving to bidder I。

 I'm going to increase it by delta times the ratio of WJ， it's WI。Okay， less stuff to bitter J。

 more stuff to bitter eye。And we need to show two things about X prime。

 one that we haven't violated the feasibility constraints。

 that X prime still satisfies the budget constraint。And the next prime has strictly higher welfare。

 that'll be our contradict。Okay。So first。Let's check that we haven't。Violated the NApsack constraint。

m so。How much did we？Change the total size of our allocation。Well， on the one hand。

 we made it bigger。Because we increased the allocation to x prime， well。

 how much bigger did we make it， well we increased the allocation to x prime by exactly delta times wj over WI and bid I has size WI。

 so we have to multiply that by WI。And the WI is cancel out， the numerator and the denominator。

But we made some additional room because we subtracted off Delta from Bi J's allocation。

 how much additional room did we make well？Bitter J has sized W J。

 So we made Delta WJ additional room。 And so the。You know。

 additional space we're taking up with bitter eye exactly matches the additional room we made by subtracting off allocation from Bi J and so we haven't changed the size of the bundle and so if we satisfy the NApsack constraint before we still satisfy the NApsack constraint。

It's also important that we haven't made either Xi prime or Xj prime either bigger than one or less than zero right to the XI is we're supposed to be between zero and1。

But that's true because of how we define Delta。Remember， Delta is only smaller than xj by definition。

So subtracting delta off from Xj leaves Xj prime non negative。And similarly。

 Delta is only smaller than1 minus X times W over WJ and so。Adding。Delta times WJ over WI。

 the amount we're adding to bitter I， make sure that Xi prime doesn't exceed one。

So we still satisfy all of the feasibility constraints and this XI prime solution。

 is still a feasible solution。😊，Right， we haven't talked about it's subject value yet。

 but like it's still feasible。Okay， so because x was feasible， x prime is also feasible。Now。

 how much did we change the value of the solution， we need to claim now that x prime has strictly higher objective value。

Well， we changed it in two ways。By increasing the allocation to bitter I。

 we increased the value of the allocation by exactly the value of bitter I V times the amount of the increase delta times Wj over WI。

 and we decreased the value by decreasing the allocation to bitter J。

 well we decrease the allocation to bitter J by delta so we decreased the total welfare there by delta times VJ。

And we need to argue that this change in welfare is strictly positive。But it is。And it's because。

By assumption， right， the whole premise of this was that bitter eye。

Had strictly higher value density than bitter J， right V I over WI。

 we assumed was strictly bigger than VJ over WJ。And so just multiplying both sides by WJ。

 right like this was our assumption， multiplying both sides by WJ。

 that just means WJ over WI times VI， this quantity that we're adding。Is bigger than VJ。

 this quantity we're subtracting。And so。X prime is a better solution than x。

 which is a contradiction because the assumption was that x was the optimal solution and so we've proven that optimal solutions to fractional abstractside problems have to have this simple structure where we just sort people in order of their value density and allocate them fully。

In this order until we run out of space。Okay， makes sense。Okay。

So now if we want to think about the fractional version of the problem。

 we don't need to write it out as a linear program anymore。

 having realized that it has this special structure。

 we can just write down the following simple combinatorial algorithm for the fractional NApsSe problem that is like super easy。

We just sort the bidders in decreasing order by their value density。

And keep track of how much space in our Napsack on our airplane we've used so far。

And in this sorted order， just march down the list and say， look。You know。

 can I make if I make the next bidder on the list， bitter I a winner， will that still。

Satisfy my NApsack constraint will the current size I've taken up so far plus the full weight of bitter eye。

 will that still be less than my budget？And while that's true， I'll say， okay， well， you know， hey。

 better I， congratulations， I'm fully satisfying your demand and I'll do the bookkeeping to keep track of how much space I have left。

And at the end。We get to this final bitter eye。Whose demand I cannot fully satisfy？Right。

 like it's the volleyball team。They've got， however many people are on a volleyball team。

 but like I have two seats less than that on the airplane。Well， it's the fractionalnapsack problem。

 so no problem I just。Pracxictionally allocate。I allocate the fraction of them that will fit on the airplane。

And I call it a day。Okay， this algorithm has to give us the optimal solution to the fractionalnapside problem because of this structural result we just proved to do anything else would violate the structure that we just proved optimal solutions must have。

Okay， make sense。Okay。Now。Of course， like。What do we do with this。

 like this is not a solution to the Napsite problem because。

Its sort of like almost a solution to the NAps side problem， right。

 like you might have worried a priori that by allowing。Fraactctional allocations。

 we would get completely nonsense solutions where every bidder is allocated fractionally。

But at the very least， that doesn't happen like there's at most one bidder in the optimal solution who's allocated fractionally。

Like what this algorithm does is it fully allocates。

Fits in this descending order of sort of value density until it can't anymore and then for the last person on the list it gives them a fractional allocation yeah。

对以对。也对。We don't have to， we can break ties however we want。

 in which case the previous lemma would just say that there exists a solution that has this structure。

Okay， so so you might， you know like so our question is like。

 does the existence of this algorithm tell us anything about how to get a solution to the integer program？

The enteredteger problem。And like you might。Be encouraged by the fact that until this last step。

 this algorithm really is constructing an integer solution。

 it's just like at the last step when it's not。And so like your first thought might be like， okay。

 why don't we just like skip the last step， like why don't we fill up the airplane。

in order of you know， value density and then when we get to the first party if it doesn't fit's like okay。

 we can't fractionally allocate them， what if we just say sorry like I'm going to fly with however many empty seats there are like that's not going to be the optimal solution but it's only going to leave off one person well why don't we just do that。

So what do people think， is that a good idea？嗯。Here's where I。Yeah。

 so like that's not a good idea because you might end up with a ton of empty seats。

And maybe here's like an example。Okay， so let's suppose there's two bidders。

And one of them is big and valuable， okay， one of them has size 10 and value 10。

And the other one is you， small and not valuable， it has size one and value 1。1。

And so as our budget is 10。Okay， so big valuable agent， small not valuable agent。

 but it happens that the small not valuable agent has slightly higher value density。

The big valuable agent actually has value density one， whereas the small。

 not valuable agent has value density a little bit higher， 1。1。So we have 10 seats on our airplane。

 like the optimal solution is obviously to seat， but like we can only seat at most one of these parties they're not going to both fit the optimal solution is obviously to seat the big valuable party and then we get you know welfare 10。

But what is the algorithm we just proposed going to do well it's going to sort people by value density。

 so the small not valuable customer is going to be first in sorted order， it's going to seat them。

They only take up one seat， we're going to have nine empty seats and we're going to say look。

 we don't have room for the for the valuable customer anymore like two bad and so。

That algorithm will get value only 1。1 when it could have gotten value 10。Okay， so it's like。

 you know。Could be as bad as a 10 approximation。And there's nothing special about 10。

 you could have come up with a version of this example where the algorithm we considered doesn't even get a one over 100 fraction of the optimal welfare or a one over 1。

000 fraction or a one over a million fraction。It like this algorithm that just runs the optimal algorithm for the fractional and Napsec problem。

 but then skips the last step because it can't allocate things fractionally。

 it is not an approximation algorithm for any finite value of alpha。That's how good。Okay， so right。

 the problem was like， you know， optimizing in this bang for buck order might leave the whole plan empty。

So here's maybe a second attempt。Suppose we sort the bidders in decreasing order again by their valued density。

And we do the same thing we did before， while there's still room on the airplane for the next party in this sortred order。

 we make them winners of the auction temporarily， at least we consider that they are candidates to be seated。

Okay。And at the end， we have this candidate allocation S， which is exactly what's the algorithm。

That we just thought of that wasn't very good would have allocated just the prefix of people in the bang per buck ordering that fit on the airplane。

And we'll consider outputting that。But we won't output it just yet， we'll say， look。

There's this last guy in the ordering that the fractional solution would have。

Fraracctionally allocated。He won't fit in our solution。But we'll ask。

 does the cumulative value of the？Solution that we've just come up with exceed the value of just this one guy。

That the fractional solution would have。Fracctionally allocated。If it does。

 then we go ahead and we output this set S that our previous algorithm would have done。

But if it doesn't， if we end up in like something like the bad situation from the previous algorithm where this set S consists only of like the low value bitterder and this guy I。

 at the end， he's the high value bidder。Then actually what are we going to do。

 were going we're going to scrap this solution S and what we're going to do。

Is we're going to output a solution that seats just a single bidder， which bidder。

 well the single bidder that has the single highest value。And if you want， you know。

 if there's empty seats on the airplane， you can seat them too however you want。

 but we're going to analyze the algorithm as if you only seat this one guy and even in that case。

 something good will happen。Of course， you wouldn't really need to leave all of the other seat empty。

Okay。So is the algorithm clear？So it's sort of like what we were doing before。

 just sort by bang for buck， leave off the last guy who we can't allocate fractionally。

 but it just has this like little band-aid at the end， this little sanity check that says， look。

 if youre the cumulative welfare of the entire solution you're proposing is not as high as like。

You know， allocating to like a single bidder， then allocate to the single bidder instead。Okay。

So the claim is that this bandai is enough， you sort of patch up the algorithm by putting this bandaid on it。

 not only does it solve this like one bad example for our first idea that we went through。

 but like actually on every possible input it is guaranteed give to obtain welfare that is within a factor of two of the optimal wealth。

In fact， like we're going to prove something even a little bit stronger than that。

 it'll obtain welfare that's within a factor of two of the fractional optimum， which is only larger。

Okay。Okay。So let's think about this。So。Remember our algorithm。Enumerates people in this。

Sored order of value density。And what is this set S。

 it is just the largest prefix of that sortded order。That。

Do not exceed the whose size does not exceed the budget， whose， you know。

 total number of demanded seats does not exceed the number of seats on the plan。

And then there's this guy I， who's the first。Person in this sorted order who didn't make it into the set S。

ok。Now。We know that。The fractional solution， the fractional optimal solution， what does it look like。

 well it fully satisfies the demand of everyone in this set S。

 this prefix of people in the density sorted ordering。

And then it fractionally satisfies the demand of bitter eye。

After which the Napsack is full and nobody else gets their demand satisfied。So we know that。

In the fractional optimal solution， x star。Any bitter J who is not either in this set S。

 this prefix and the sorted ordering that fully fits on the plane， or is this guy I。

 who's the first person who didn't get their demand fully satisfied in the fractional optimal solution。

 every other bitter J gets nothing。RightThat was because of what this optimal algorithm for the fractional optimal solution looks like。

So the fractional optimal solution， what welfare does it get？Well。

It fully satisfies the demand of everyone in this set S。

 so it gets welfare equal to the sum of the values of the people in this set S。

And then it fractionally satisfies the demand for this bitter eye。

 so it gets some fraction of his value。And that's it。

So if we consider the sum of the values for everyone in the set S and bitter eyes value。

That's only larger than the fractional optimum。Because the fractional optimum gets this and then only gets a part of bitterized value。

And similarly， the fractional optimum is only larger than the integer the optimal solution to the actual Napst problem。

And so if I've got these two quantities that I'll call like A and B， say。

And I know that a plus B is at least opt。And it's got to be that either A。

Is at least opt over2 or B is opt over 2？If they were both less than optto2。

 then their sum would be smaller than opt。So I know that the maximum of the welfare obtained by。

Seedating everyone in this set S。And the welfare obtained by seeding the first person who didn't make it into this setI。

 the better of those two welfares has to be at least talked over to。And what does our algorithm do。

 Well， it actually doesn't take the better of these two things。 It takes the better of。

The welfare obtained by the set S and the welfare obtained by exceeding the single guy who has the highest value。

VI star。But by definition， VI star is only bigger than VI， VI star is the largest value。

And so the welfare obtained by our mechanism， which is the largest of these two quantities。

 is at least stopped over two。ok。So it's a two approximation out。Does that make sense？Okay。

So like we does that into an approximation algorithm。But remember like our。

Goal was to solve a mechanism design problem， we wanted to design a truthful auction for theps the Napsack option problem。

And remember， in order to we know since this is a single parameter domain。Like。

We've got a particular algorithm here， we have a very simple way of determining whether we can pair it with a payment rule that will turn it into a truthful auction。

OrThat was what we spent last lecture characterizing。

We will be able to take this algorithm we just developed and use it as an allocation rule and turn it into a mechanism by pairing it with a payment rule that is dominant strategy truthful exactly if。

The algorithm we just designed is monotone non decreasing for every agent I。

 which remember just means must have the property that if agent I。At a given bid。

 wins gets their demand met。Then they must also win。

 they must also get their demand met at every higher bid。Okay， so to establish。

 we we've established the algorithmic properties of our allocation rule。

 so it's a two approximation algorithm to the NAps problem。To establish the incentive properties。

 we need to。Established that the allocation rule is monotone non decreasing。And if we can do that。

 we can look up the slides from last lecture and come up with a concrete payment rule。

AndJust reading it off of the slides from last lecture it a pair with this allocation rule and we'll have a truthful mechanism。

Okay。So want to verify that the mechanism is monotone。

Remember what we need to do is we need to establish that。If at some bid profile。

 bitter eye wins the auction， gets allocated seats， then if they raise their bid。

 they must still win。And we just have to like think about this in a couple of cases because there's two different ways you could win this auction。

Like remember， what does the allocation rule do？It sorts everyone。By their value density。

And comes up with this candidate solution， the prefix of people in sorted ordering。

 the largest prefix of people in sorted ordering who fit on the plan。Now。

 it might output that solution。But it might also output the singleton set that contains the single bidder who has highest value。

 who might not have been in the original solution。So there's two ways to be a winner。

 either you could be in this set S。Come up with by the algorithm or you could be the highest value bidder。

Okay。So let's fix any instance of thenapsack problem given by weights and values。

 and let's zoom in on some agent's eye。Okay。And let's say that VI is his original bid。

And let's say that VI Prime is some higher bid that he might consider making。Okay。

 and let's just call the bid vector V prime， the vector that comes from leaving everyone else's bid fixed。

 but letting bitter eye unilaterally deviate from VI to VI prime。

And let's say that if we run our algorithm。With bids V。The solution we get is T。

 T is the set of winners of the auction。And if we run our algorithm with bids V prime instead in which Bi eye has raised his bid。

Let's say the solution is something else called it T prime， these are the winners of the auction。

And so the thing we need to show。Is that if？I is in T。 If I wins at the lower bid。

 then I is also in T prime。 I wins at the higher bid。Okay。So remember this mechanism， you know。

 there's like two there's two ways to win the auction， there's two internally。

 the mechanism generates the set S， which is just the largest prefix in density sorted order that fits on the airplane。

S may or may not be the same as t right T will either be S or it will be the singleton set consisting of the highest value bidder。

But whether or not S is the same as T or not， let's just give a name to S。

 you know when I run the algorithm。On the original bid vector V。

 let's say that S is the name of this intermediate set the。Largest。

Prefix in value in density sorted order that fits on the plane and。Similarly。

 let's call this set S prime when I run the algorithm on bid vector B prime。ok。

So S is this prefix of bidders that fit on the plane when the bids are V。

 S prime is the prefix of bidders that fit on the plane when the bids are v prime。So。

We need to argue that if。I is in T， then I is in T prime， the actual winning set。

T may or may not be S， T prime may or may not be S prime， but as an intermediate step。

I want to just argue that。If I is an S， if it's in this。

Prefix of bidders who fit on the plane then I as an S prime as well。

So let's just remember what S and S prime are。SNS Prime right there， the prefix of bidders。In。

Density sortdid order whose total size is less than B， less than the number of seats on the plane。

And what's the difference between S and S prime， well the only thing that has changed is that bitter eye has raised their bid。

So。The densities for all of the bidders other than bitter I， VJ over WJ， those remain the same。

And the density for bitter eye has increased， raised his bit， and his size hasn't changed。And so。

When he raises his bid， he can only move himself earlier in this density sorted ordering。

 his density went up and nobody else's density changed。And so if he was already an S。

 if he was already early enough in the ordering。To fit on the plane。

Then by raising his value and moving himself only earlier in the ordering。

 he'll still be early enough in the ordering to fit on the play。So by raising his bid。

 if he was already in S。He hasn't taken himself outside of it。And so。

If we are in the case where in both instances of the algorithm。

These sets S and S prime were chosen as the set of winning bidders。Then in that case we're done。

 that's one of the cases and if T the winning bidders。We're S。

 when we ran the algorithm on the original bid and S prime， when we ran it， but the raised bid。

 then we're done。How about the other cases？Yeah。Well。Note that。If bitter eye was in this set， S。

 if before he raised his bid， bitter eye was already in the prefix of bidders in。

Denssity sorted order that fit on the plane。And given that when he raises his bid。

 he continues to be in that set。When I look at the total welfare of people in S prime。

That's only going to be bigger than the total welfare of people in S。

Because the only change was that bitter I raised his bids and since if he was in S。

 he was in S prime， that increase was entirely accumulated within the set S prime。

Right so the nobody。Nobody in this set decreased their value and， you know。

 like bitter eye increased his value and so nothing changed。And so in particular。

Since we choose what the algorithm chooses what's set to output by comparing the welfare of the people in S。

With something else。If before he raised his bid。The algorithm output。Said S。

It'll still output sets after he raises it。Okay， so if t was S， then t prime was S as well。

And so there's only one remaining case。Which is that it might have been。That。

Bitter I won the auction before he raised his bid。嗯。But not because he was in this set S。

 but rather because he was the single bidder who had the highest value that could happen as well。

But notes。But if that's how he won the auction。It was because。Even before he raised his bid。

 his bid alone。Had higher value than the entire cumulative bids of everyone in the CS。

That was why we might have output the singleleton set。And so in this case， by raising his bid。

Bitter eye must also continue to be the winner。How come， well， if he was already the high bidder。

If he raises his bid， he's still the high bidder。And so。If。After he raises his bid。

 the algorithm continues to output the singleleton set containing the high bidder。

 while it's still him， he still wins。Now it's possible that after he raises his bids。

 the algorithm doesn't do that anymore。Because it might be that the welfare of S Prime increased after he raised his bid。

But the only way that could have happened is if he raised his bid enough so that he moved early enough in this。

Density sorted ordering but he was in S prime。And so in that case， he wins as well。ok。

So for this algorithm。There's no way to raise your bid that causes you to go from winning to losing。

So the algorithm is not only a polynomial time two approximation for the Napstack problem。

 it is monotone non decreasing， which means the payment rule we covered last lecture makes it a dominant strategy for people to tell the truth。

Okay， so even though isn so we have a truthful mechanism that approximates welfare in this allocation problem。

 whose welfare optimization objective is NP hard， the VCG mechanism wouldn't have done that for us。

 but。Our characterization of single parameter domains helped out。ok。So I'll see you guys next time。

Yeah。

![](img/37e96de51f194eda24f6fb714fd9f82c_3.png)