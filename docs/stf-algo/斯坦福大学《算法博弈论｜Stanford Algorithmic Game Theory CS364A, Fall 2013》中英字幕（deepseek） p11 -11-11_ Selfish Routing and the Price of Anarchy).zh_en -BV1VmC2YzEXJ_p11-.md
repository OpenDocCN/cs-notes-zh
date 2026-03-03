# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p11 -11-11_ Selfish Routing and the Price of Anarchy).zh_en -BV1VmC2YzEXJ_p11-

Okay， so we've wrapped up the mechanism design segment of the course。

 you might recall from the first lecture that that was part one of three。

 So we're going to start part  two of the course today。

And part two is about understanding the inefficiency of equilibriumria。Enga。

So this area is motivated by the actually fairly common scenario where you don't have the luxury of designing a game of designing the rules from scratch so so far we've assumed that you knew some information about the environment and you got to pick the rules of the game and so that the outcome of strategic behavior was what you wanted or as close to what you wanted as possible。

So now we're gonna look at games， you know， the most basic form games that just occur in the wild。

 okay， which already exists where strategic behavior is already there。 We want to know， you know。

 which ones function well and which ones don't。So when the game in the wild。If you will。Nevertheless。

 have near optimal equilibrium。So sometimes they do， sometimes they don't。

 our goal is to have a delineation between the two to really understand which are the good cases and which are the bad cases。

Now let me open with just some comments about the difference between this part of the course and the previous one。

 So on a technical level our analysis of the inefficiency of equilibrium or the so-called price of anarchy。

 They'll have a different flavor on a couple of levels So first of all。

 the games will generally not have dominant strategies。 Again。

 we didn't have the luxury of defining them。 In fact， dominant strategies are pretty rare。

 So we're actually going to have to analyze nontrial equilibrium， we'll start with naash equilibrium。

 But look at a couple of other equilibrium concepts as well。As you might expect。

 if we don't have the luxury of designing the game， we're typically not going to get full optimality。

 So there's certainly going be no analogous result like the VCG mechanism， which says in principle。

 you can get full surplus if you can design the rules of the game。 In fact。

 forget about full optimality， even approximate optimality， in some sense。

 the game has to have fairly special structure。 so the hope is to。

 is that there are application domains of interest。😊，Assumptions， which on the one hand， are strong。

 but are also met in interesting scenarios where we can prove that equilibriumlibria are near optimal。

 And I'm happy to say we now have about 15 years of experience of different domains where you can actually prove that equilibria are guaranteed to be close to optimal。

 One thing that'll be simpler in this part of the courses， there won't be private information。

 So for example， in a traffic network， all players are gonna be fully aware that all of the players just want a shortest path。

 They just want to get to their destination as quickly as possible。 By contrast。

 in the auction setting， I didn't even know what other people wanted。 So if you asked me。

 would this other bidder， prefer to win the item at a price of 10 or lose， I don't know。

 depends if the valuations at least 10 or not。 I couldn't answer that question。 in rock paper。

 scissors， if you ask me， given that I'm playing rock， would they prefer to play scissors or paper。

 I know the answer。 I know they prefer to play paper。😊，Okay。

 so it's going to be mostly full information games。

 For those of you who take the SQL course in the winter。

 there'll be a nice dovetailing of these two areas。

 and we'll look at things like the inefficiency of Bayes Nash equilibriumlibria。

 which is a way of modeling private valuations and this kind of setup。 But for this course。

 we'll just stick with the full information case。😊，I guess one final historical comment。

 So in mechanism design， I taught you a mixture of classical economic theory。

 So Myerson's theory of optimal auctions being a good example。

 and the novel contributions coming from computer science have been know。

 novel questions or novel extensions on top of this classical economic framework。

 One thing that's cool about this part of the course is really。

 these questions essentially were never asked。 Certainly never asked systematically until they until about 15 years ago。

 And that came out of the computer science community。

 So this idea really has this genesis in a paper of Ktsupus and Pmitri to computer scientists back in 1999。

 The following year I started working on it myself with my PhD advisor， Avatdos。😊，Okay。

So any questions before we get started？Let me quickly remind you of what I mean by a game in the wild。

 Okay， this is gonna be brace paradox。 We talked about this in lecture 1。 Let me jog your memory。

So what you want to think about is you want to think about traffic。Okay。And， you know。

 computer scientists who have studied this were motivated more by data networks。

 communication networks。 But the model goes back， as you might expect to transportation scientists。

And you may as well think about， you know， morning commuters leaving at 8 AM from a common origin S to a common destination T。

 And， of course， drivers take whichever route they want。 Okay。

 there's no central authority dictating which route you take from point A to point B。

 And we're going to assume always that they want to minimize their travel time。

And what makes it interesting， the reason you， as a driver。

 care about what other drivers do is the congestion on roads goes up。 and as it goes up。

 your travel time increases。 So in the basic base paradox network， we have two kinds of roads。

 we have very simple ones labeled by the cost function， C of x equal1。

 that's a constant cost function。 So that says driving on this road takes an hour， no matter what。

 so think of as a long road with an infinite number of lanes。 So then we have these other roads。

 C of x equal x。 So these are roads that get congested as more and more people use it。

 Okay so there's one unit of traffic overall， if x units or when x fraction of the traffic takes one of these links。

 we assume it cost x hours。 So if half the traffics on one of those links。

 it takes 30 minutes to cross that particular link。So。What we did on lecture1 is we first asked。

 you know what would what kind of equilibrium would they settle into in this basic network。 Okay。

 so this already is a game without any dominant strategies， If more people。

 for whatever reason are using the top path， you'd prefer the bottom one。

 If more people are using the bottom one， you'd prefer to use the top。 So your quote unquote。

 best response。 Your best action depends on what others are doing。

 Okay so there's no dominant strategies。 But by symmetry， we argued that we expect traffic。

 know if these are the same people listening to the traffic report day after day。

 there's really no reason to prefer one of the paths over the other。So we'd expect a 50，50 split。

Okay。For an average commute time of 90 minutes。The reason it's called Bra's paradox is when you augment the network。

By a teleportation device。So zero cost to teleport from the midpoint of the top path to the midpoint of the bottom path and no congestion。

 Now， all of a sudden， I've introduced a dominant strategy。

 So it turns out no matter what the other drivers do， you always want to use this teleport。

 It's always in your best interest。The problem is， is that when everybody rushes to follow their dominant strategy。

And 100% of the traffic is on the zigzag path。 The congestion on the upper left and the lower right links have gone up to one。

 and the commute time has gone up to two hours。 Okay And because this is the dominant strategy of all the drivers。

 there's no other equilibrium。 This really is what happens。 And people have run lab experiments。

 If you introduce the teleport， this is really what happens。

 Okay people wind up in this this equilibrium with a higher commute time than than before the introduction of the teleportation device。

So the paradox was， unlike an optimization， where adding more feasible solutions can only make you better off。

 Here， you add extra options in the equilibrium。Gets worse。So the commute time goes from threehalves。

To two okay。And so its in particular， in this new network。You know。

 we're asking when are equilibrium optimal or near optimal。 Well。

 the equilibrium in this new network is certainly not optimal。 so I mean。

 it turns out the optimal thing， even after the teleporter。

 the best thing to do is just ignore it and stick with a 50，50 split。 Okay So in the new network。

 the equilibrium has commute time2， but the optimal commute time。 if you。

 in principle had dictatorial control。 everybody， you could achieve a commute time of 90 minutes。

So the price of anarchy is just defined as the ratio between these two quantities。

 You look at the performance achieved under strategic behavior。

 the performance you could hypothetically attain。 if you could dictate actions to everybody。

 that's going to be a ratio at least one。 In this case， it's four thirds。So PUAA。

In the new network after the teleporter。Equals  two divided by three/ hs or four thirds。哎。

And so the price of anarchy in these kinds of networks is just defined as the equilibrium。G time。

Over the optimal。Commute time。 And again， it turns out in the network with the teleporter。

 you cannot do better than that 50，50 split。 Okay， that turns out to be optimal。

So that I think hopefully jos and memory what we've already discussed back in lecture 1。

 There's actually an even simpler so calledled sal routing network。

 which shows you that the price of energyarch can be four thirds。 So that was from 1968。

 Let's go back even further。It's 1920。Or in his book， The Economics of Welfare。

AC Pigu discussed at least qualitatively the following example。So he said。

 what if there's just two parallel roads。 Okay So literally Highway 1，0，1 and Highway 2。

80 connecting Stanford to San Francisco。So just to make the example kind of as stark as possible。

Let's use these same， you know， totally flat and then identity function cost functions。

So what do we expect to happen at the equilibrium here， again。

 assume there's one unit of traffic overall。 So what would you do as a driver， take the top。

 take the bottom。Yeah， so here we again have a dominant strategy。

 turns out in this particular network。So it's always a good idea to take the top。

The best case the worst case scenario on the top is as good as the best case scenario on the bottom。

So does it seem like could you do better with respect to the average commute time if I could move some of the people around if I was a dictator of this system。

In fact， anything would be better actually， than this equilibrium。 Okay。

 so it turns out the optimal thing to do was a 50，50 split。 It's a simple calculation。😊，Yeah。

So what's the average commute time with a 50， 50 split？So half the people take an hour。

 half to take a half an hour。 So it' on average， it's 45 minutes。So， again。

Pre of energyarch is one divided by three/4 or four thirds。

We'll discuss to what extent this four thirds is or is not a coincidence later in lecture。All right。

 well let me come clean。Turns out， even in these simple routing networks。

 so the price of an was always four thirds， no matter what， arguably we'd be pretty happy。

 because remember， this is a system where we're exerting zero control at all。

 which is letting people do whatever they want。 And if they inadvertently wind up getting a pretty good approximation of this hypothetical optimalal solution。

 we're going to define that as a well functioning system。

 so we'd actually be happy if this was the worst we ever saw，4 thirds。😊。

Turns out I don't have to tweak this example too much to show you that in these routing networks。

 the price of anarchy can unfortunately be much larger。So let's look at a nonlinear version。

A pigous example。So keep everything the same。Except instead of this function， C x equal x。

I to make it C of x equal D， X to the D。We should think of D as large。10， 100，1000。

 some large number。So how does this affect what happens at equilibrium。

 changing D equal 1 to D equals some larger number。No change。 Okay，' still a dominant strategy。

 Take the top edge。 When everybody does that， you still get a solution in which the average commute time。

 In fact， the common commute time is an hour。It's a selfish solution。Still costs one。

What are the optimal solution。So even if you just keep the 5050 split already。

 the optimal solution is going to improve as D grows large right because on the bottom。

 you'll still have these half of the people that have an hour travel time on the bottom。

 But that 50% on the top， their travel time is going to be x to the D or one half raised to the D。

 So as D grows large， that's going to 0 so there's people on top are getting there instantaneously So that already give you a factor 2 because opt would drop to 05。

 But in fact， this situation is even more serious the optimal flow can do even better because why bother putting as many as one half on the link of constant cost of one。

 Why not just sacrifice a very small number of martyrs to the link with constant cost1。

 You're gonna have a one minus epsilon fraction of the traffic on the bottom link their common cost will be one minus epsilon raised to the D。

1 epsil is less than one。 So as you keep powering up， it's again， just going to 0。

 so you can find an optimal solution where almost everybody gets to T almost instantaneously。

 And then there's a few unlucky people who are taking an。

But they contribute very little to the average。So a little more formally。So the optimal。

Average commute time。Is epsilon times1。So what I'm doing here is I'm putting epsilon on the bottom。

1 minus epsilon on top。So the epsilon on the bottom contribute epsilon times one to the average。

 and then the rest of the average is the one minus epsilon fraction of the people。

We have travel time 1 minus epsilon raised to the D。

So for any given D I could solve for the optimal epsilon。

 But what's going to be true is as I take D larger and larger。

 the optimal epsilon is going to be smaller and smaller。

 And then the limit as D goes to infinity and epsilon goes to 0。

 this optimal cost is actually going to 0。 And therefore， the ratio。

Between the equilibrium commute time， which is one for every D and the optimal commute time。

 which is going to 0 with D。 this is blowing up to infinity。Okay。So in conclusion。

Price of energyarch goes to infinity。As D goes to infinity， an epsilon goes to zero。

So we're seeing already in these very simple traffic networks， even in just two no2link examples。

 sometimes for whatever reason， the price of energy is good。 I it's close to one。 Sometimes it's not。

 Okay， So the best we can do as analysts is understand as thoroughly as possible， You know。

 When are these networks， When do they function well and when do they not。

So that's the question that we want to answer。As thoroughly as possible in this lecture。不。

When that is under what conditions。Is the price of anarchy？Of selfish routing。Small。

Or small means as close to one as possible， okay。So what might be hoped for？Well， for example。

I've shown you three different networks。 I've shown you one braces paradox where the price of energyarch is four thirds。

 not too bad。I'm showing you another one。 Picker's example where the price of anarch is four third。

 not too bad。But then I showed you the linear variant where it is be。Okay。

And if you're feeling kind of very cavalier。Maybe you'd look at these three examples and say。

 you know， what's the coolest fact I could imagine possibly proving， given what I know is true。

And you say， okay， well， obviously， an obstruction to having a price of energy close to one is having highly nonlinear cost function。

If you have these， you， X to the D for super big D。You know， you can't prove anything， right。

 The Nominina Picks example shows that。So if you're feeling very optimistic， you might conjecture。

 that's the only obstruction。So as long as you didn't have very nonlinear cost functions。

 you're gonna be fine。 For example， maybe at least if you knew that the cost functions were linear or at fine。

 So of the form A X plus B， like in braces paradox of pig's example。

 maybe as long as the cost functions are at fine， the price of energy is not too bad。

That's kind of the strongest statement that might be true。 given what I've shown you so far。

 Turns out it is true。 I'll show you proof in this lecture。

Let me pick down the model a little bit more。Before I explain the statement。

 we're going to approve today。So in general， we have a directed graph。Okay。

 with an origin S and a destination T。This is given。And you're also told how much traffic there is。

 So our units of flow or traffic。Or to go。From S to T。And a directed graph。G。

 that set E vertex set V。I'm assuming one origin， one destination。

 Everything I prove to you about these selfishv reality networks remains true。

 even if there are multiple origins and multiple destinations。

 And I'll ask you to do that extension on exercise set number 6。 It's really exactly the same proofs。

 Just a little extra notation。 So to keep the notation down in lecture。

 I'm gonna assume one origin in one destination。And then the only other part。

 only other ingredient in the model。 So you have the network， and then you have edge cost functions。

I'm going to use CCB。That's a CB。To denote the cost function of an edge。

I want to emphasize this is the cost of the travel time per unit。Okay， so， for example。

 if it's 30 minutes， all traffic on that edge takes 30 minutes。 Okay so it's per unit of traffic。And。

We'll add some extra assumptions as we need to to derive good bounds。

 But the baseline assumptions are very minimal。No time machines。Travel times are not negative。

Traffic's only bad。So cost functions are non decreasing。 They can be constant。 That's fine。

 but they can't go down。And they're going want them to be continuous。

So those are the baseline assumptions。 But， you know， in your mind。

 as you go through this lecture today， go ahead and if you want。

 think about just the aine cost function case。 I'm fine with you just keeping that as a concrete running example in your mind。

So what are going to prove。Let me explain the result a little bit informally。

Then I'll develop the definitions that let me state it precisely。

Let me just tell you conceptually what we're going to establish today。This is no old result of mine。

Yeah。So the main result is going to say that， always。Worst case examples are extremely simple。

 just like that pick's example that you already saw。 That's the high level message。

So among all networks。With cost functions。In the set seat。So to state this。

 I'm going parameterize by a set script C。 These are the permitted cost functions。 So， for example。

 the set C might be the set of aine functions。 All functions of the form A X plus B。O。

 or maybe it's gonna be a bigger set。 O， And of course， the bigger the set。

The more networks I'm trying to prove a statement about。

 So the worst case price of energy is gonna be going up as I permit more and more cost functions in this set。

 But for now， go ahead and think of this this set C as just the aine functions。 A X plus B。

 it turns out the proof is sort of easiest to state at a higher level of abstraction。

 And that's why I'm doing it。So search the world， all networks in the world。

The one restriction is that you can only annotate your edges with cost functions in C。

 That's you have to obey that rule。And I claim that， you know。

 when you come back from your search of all networks in the world hunting for the largest price of energyarchy ever。

You're going to come back and you're going to show me a dirt simple network。

 You're going to show me a network that looks like the Pigu network， two nodes and two links。 Okay。

 You have looked at all of the more complicated networks。

 You won't have found a larger price of anarchy。 It's not going to happen。So obviously。

 the next order of business is going to be making this more precise。 What's a pigoo like network。

 What do I really mean， Okay， But I wanted to start with kind of conceptually what the mathematical statement is going to mean。

So let me also just sort of say why。You might care about this formulation of it。So as a special case。

 just looking ahead a little bit。This theorem will imply as a corollary， as a special case。I lost it。

 That among all networks， no matter how complicated。That have a find cost functions。

 The worst one is just that one and X pigs example。 O， for networks with aine cost functions。

 nothing is worse than the one and X。So worst case examples are simple。And as a consequence。

 if you want to know what the worst case price of anarchy is。

 this theorem reduces that question to a dirt simple computation。 Okay。

 this theorem is basically going to hand you a network with two nodes and two links。

 And it's going to say whatever the worst case price of anarchy is。

 it's whatever it is in this network。So now you just do a back of the envelope calculation on this network。

 and it gives you the magic number。 So for aine cost functions， it hands you the one and X example。

 we already did the computation that the price of anarchy is four thirds in pig's example。

 So as a consequence， the worst case price of anarchy in any network with aine cost functions is4 over 3。

😊，The benefit of phrasing it this way is that it's not just about aine cost functions。

 This is a generic statement， whatever the set of cost functions。 The magic number will be different。

 but this characterization of worst case examples remains the same。

So by virtue of worst case examples being guaranteed to be simple。

It is straightforward to compute the worst case price of anarchy in。

For any class of cost functions you might care about。So again， I'll give you。

 let me just again help you interpret this。So。As special cases of this general theorem。

As I just said， you get that the worst price of energy is 4 thirds。

If we take the permitted cost functions。To be。Affine cost functions。 That is degree 1 polynomials。

With not negative coefficients。If you， for example， allow the degree to go up to 2。

 what the theorem will tell you is that the worst example is just the pig's example。

 except with the x replaced by x squared。 There's just one in x squared。

Now you just compute the price of anarchy in that network。

 and this theorem tells you that's the worst in any network。So that turns out to be。Roughly 1。6。

For the D equals two case。Squigggle 1。6。Again， d equals 3。 The worst case example is one and x cubed。

So that's going to be like 1。9。D equals 4 is an interesting case。

 because at least at one point in time in transportation。

 some people were advocating using quarttic functions to model travel time of real traffic。

 They of actual transportation traffic。So the worst case example for cortic functions， of course。

 is just one and next to the fourth。 that turns out to be 2。1。

 So in transportation models that were considered you know， appropriate by some researchers。

 you've got a price of energyarch reasonably close to 1， just 2。1 in the worst case。And in general。

 this is growing sublinear in the degree bound D。Okay。This is， of course， going off to infinity。

 We already knew that。 We already knew it without a degree bound。

 there was no bound possible in the price of anarch。

So what we're doing in this lecture through this result is we're giving a precise answer to this question。

 I gave you three examples。 In two cases， the price of anarchy was small。 in one case， it wasn't。

 We wanted to understand， when is it small and when is it not。

So highly nonlinear cost functions or an obstruction。 they can cause large price of anarchy。

 And this theorem is a converse。 It says if your network， no matter how complicated it is。

 has cost functions that are well modeled by low degree polynomials， then under no other assumptions。

 the price of anarchy is close to one。Okay。So when is it small， it's small in the worst case， even。

When cost functions are not too on nonlinear， That's the answer。 Okay。

 So that's how that theorem answers this question。Alright， so let me tell you about the plan。

For the rest of the lecture。So the first thing I want to do is I want to give a couple。

 I want to give a formal definition of piggu like networks。

 Tell you what I mean in this theorem statement。Step 2 is we're going to define using these piggo like networks a lower bound on the price of anarchy。

 So this is analogous to our four thirds lower bound for the Aine case provided by pigguoo's example。

 So a generic version of that four thirds lower bound。

And then the final part of the lecture will prove a matching upper bound for any network。

 not just these trivial piggu like networks。 Okay， so that's the plan。

Any questions before we do those three steps。Okay。Alright， so again， define pig like networks。

 use them to derive a lower bound and prove it matching up or bound in any network。

 That's what we got to do。So。Definition。こ。So it's a pig like network。Well， it has only two nodes。

 namely S and T， the source in the destination。And only two parallel links。

 So every piggu like network， by definition， looks like this。Okay， that's not all。

I will give you two free parameters。 Okay， so the first free parameters is the amount of traffic。

So I'll call a traffic rate。You can pick that to be any positive number， real number that you won。

 Okay， It doesn't have to be one。 It could be anything。I also， as a second free parameter。

Allow you to pick the cost function of one of the links。So you can assign the top link。

Any cost function you want。So if we have in the background a set of permitted cost functions like aine cost functions。

 then this is any function you want from that permitted set。K。So， one link。Ha a cost function。是。

But those are the only two parameters that you get， Pre parameters。

So given the choice of the traffic rate R， given the choice of the top links cost function， I insist。

That the other link。Has a constant cost。 Okay， Like in Pick's example， we had a one。

 It's going to be a constant cost。 And I even insist on the constant。

 The constant is the cost function of the top link C evaluated at the full traffic rate R。Okay。

So this is a function like X Depend on how much traffic。 This is just a constant， a number， O。

 like one。So that's a pig like network。Two， three parameters。The traffic rates。And the， yeah。

 and the cost function of the top edge。Don't want to do that。Questions thus far。

So that was step  one。 If step 1 was just to formally define， what do I mean by piglike networks。Now。

Remember。For a given set of cost functions， like， for example， the aine cost functions， our goal。

Is to determine the worst Ie。 the largest price of anarchy we're ever going to see in any network whose cost functions lie in that set of permitted functions。

 So， for example， any network with Alline cost functions。Now， to lower bound this quantity。

 this quantity is the worst case over all networks in the world。So to lower bound the quantity。

 all I have to do is exhibit a single example。 So like Pgu's example already gives us a lower bound to four thirds。

So at lower bounds on the price of anarcha。 are easy。 We just exhibit examples。

So step 2 is just to formalize this， say， well。One place we can look for bad examples is these pig like networks。

Yeah， there's a lot of other things we could try。 Okay， but let's just start simple。

 Let's just say how big a lower bound， How strong a lower bound can we get just by confining our attention to these pig like examples and nothing else。

 Okay， so that's we're going to do now。 formalize that idea。All right。So， definition。Oops。Sorry。

So the reason I define pig like examples the way that I did Okay。

 is that they're really easy to reason about。哎。It's really easy to figure out what the equilibrium flow is in a piggu like network。

 And therefore， it's really easy to understand what the price of energy iss the ratio between how well an equilibrium is and how good an optimal solution is。

So let's just go through that。Finding a specific example。

So the price of anarchy for a set of games is defined as so far。

 I've defined the price of anarchy in a single game。G in a single game， you look at the equilibrium。

 You put that on top。 You get the optimal solution。 you put that on bottom。

 So that assigns a number to every single game。I'm defining the price of anarchy of a set of games。

 like， for example， all networks with aan cost functions。 So that's an infinite set of games。

 So I'm defining the sets price of anarchy as the largest I。e。

 worst price of anarchy of any game in the set。So to lower bound that， I just need to show you one。

Upper bounding it is the nontrial part。Yeah， so we're doing worst case analysis of the price of anarch。

 That's sort of the point。Okay， note。So I claim piggo like networks are easy to reason about。

So what is the equilibrium。Of a piggo like network。What do the selfish drivers do。

 selfish traffic do？They take the cup， the top path。Basically， what I did is I said， look。

 I give you two parameters。 Tell me what they are。 Tell me your R。 Tell me your cost function， C。

And now I'm going set the constant on the lower link， just high enough。

That even when the top link is fully congested， no one's tempted to use it。Okay。

So if everyone's on the top link， they all incur costs C of R， and I make the cost on the bottom。

 exactly C of R。嗯。So the， the tip shot is a dominant strategy again， for people to take the top link。

 So everyone on top gives us an equilibrium。Yeah。classroom。That's right。

That's one of the baseline assumptions， non negative， continuous， non decreasing。Yeah。You right。

 I mean， otherwise， what I just said would not be true。But non decreasing。

 So no one's tempted to go to the bottom。All right， so note。And a piggu like network。

The equilibrium flow。Has all traffic on top。And as a result。

 we can just write down what the cost of the equilibrium flow is。

So it's the travel time per unit of flow。 Okay， And that's C of R。

 because the top link is fully congested。 All our units are there。

 That's the per unit cost times the amount of traffic。

So R times C of R amount of traffic cost per unit of traffic。So in Pgu's example。

 this was just one times one for one。O。Now， the optimal solution。

 we're not going try to characterize。 Okay， so the optimal solution just somehow takes this our units of traffic。

 It puts some amount X。 Don't know what， but it puts some amount X on the top link。

 And it has to put the residual flow R minus x on the bottom link。 And it does whatever it does。

 It picks the optimal X。 Okay， That's all we're gonna say about the optimal。So the point being。

Is that the。PO A。In an arbitrary piggo like network， well。It's just the ratio of equilibrium cost。

 And we just said that was R times C of R。Now， if a flow， the optim of flow。If it puts X units。

On the top link。It's going to incur the per unit cost when there's x units of traffic times the amount of traffic on the top link X。

 Again， this is conditioned on a choice of routing X on top。Everything else goes in the bottom。

 Everything else is R minus x。 The bottom remembers this constant always equal to c of R。Okay。

So this for a given choice of x， the optimal flow by definition chooses x to make the denominator as small as possible。

 or equivalently to make this ratio as large as possible。So we're going to do soup。

Of all the legitimate choices of X。You can replace the soup by a max， if you prefer。

 by compactness and continuity。So this is the equilibrium flow。

 The in for the denominator is the optimal flow。 So by definition。

 this ratio is exactly the price of an anarchy in a particular piggu like network。All right。So。

 here's a。Quick technical point。 No real conceptual content。 Just convenient for later。I claim that。

 actually。If I erase this upper bound on the choice of x， then the number doesn't change。And again。

 that's just useful later。 Why is that true？ Well， think about when x is equal to R。Okay。

 first of all， I just claim that if I set x equal to R and then I make it even bigger。

 then the denominator gets even bigger。 So this ratio gets only worse。 Okay。

 so it's not an optimal solution。 It doesn't attain the soup。So if I set X to B R。

 and then I start increasing it， this is decreasing at a rate C of R。

 and this is increasing it at a rate， at least C of R。Okay， so if you wanted to do this soup。

 there's no point in using a value bigger than R。 So that's why I can get away with dropping the upper bound on R。

On X， excuse me。So， note。Again， using that C is non decreasing。I can drop the at most。

 are without loss。Okay。Good， so now we're ready for。To formally say。

 what do we mean by the strongest lower bound provided by piggu like examples。

So what we've said so far。This expression for a given choice of R and a given choice of the cost function C。

 So for instantis of the two free parameters， this is exactly the price of anarchy of the corresponding piggu like network。

So if we want to do our worst， if we want to exhibit the largest， strongest lower bound。

 we should just optimize over our two free parameters。

 we just want a worst case choice of the traffic radar and worst case choice of the cost function C。

 worst case meaning to make this quantity as big as possible。Okay， so that's the next definition。

So it's C。Be a set of cost functions。The pig bound。Which I'm going to note by alpha of C。Is defined。

As the worst POA。And a pig like network。With cost functions in C。Which we just argued。

Is you take a worst case choice of the first free parameter。

Which cost function you put on the top link。You take a worst case choice of the second parameter。

Meeting the choice of the traffic radar R。And then you just write down the same thing we had before。

 okay。So what I'm writing here is exactly what we had before。Okay。Said again。あ。Speak up。Yes。

 thank you。Thank you。So I know it's a lot of symbols。 But just remember。

 we arrived at these symbols as just the natural outgrowth of something you know。

 conceptually straightforward。 We have this collection of examples that we understand。

 P like networks。 Any given pig like network gives us a lower bound。And we just said， well， you know。

 what kind of lower bound can we get just using these， Okay。

 And this is just the symbolic representation of that idea。 There's three supres。

 Two of them are just because there are two free parameters in a pig like network， the cost function。

 the traffic rate。 The third supre is just because I'm being lazy about figuring out what the optimal is。

 You know， it's just the best case choice of X。So it's a lot of symbols。

 but to express something really， very simple。Okay。

So it allows you to understand this quantity a little bit better。

 this piggu bound a little bit better on the current problem set。So， for example。

If C is the appine functions。Okay， so Ax plus B。A B9 negative。Or even， in fact。

 all concave functions that are not negative， then。The pig bound is exactly4 thirds。

I've already told you， it's at least four thirds because I showed you a pig like network with aine cost functions that got four thirds。

 So all this is saying is， you know， if you try replacing the one and the x with you know。

 some other constant some other a cost function， it doesn't help。

 you can't do four thirds by beat4 thirds by twidling around the coefficients and Pgu's example。

 That's all it's said。And in fact， you can even the problems that we ask you to go through other things like for bo degree polynomials。

 Okay， and you get this D over log D dependence， in particular， for low degree polynomials。

 Al of C is regionally close to one。So what that what that computation tells us is that， okay。If our。

 you know， very modest ambition is just to understand how big， how bad piggo like examples can be。

 piggo like examples aren't that bad。 That's all we've done thus far。

It says amongst examples with two nodes， two links and a constant cost function。This alpha C。

 you know， if you do this computation and problem set number three。

The price of energyarch is pretty close to one， for low degree polynomials。What's interesting。

Is to ask about， well， what about be， there's a whole world out there beyond these trivial piggo like examples。

 Okay， how do we know that the price of anarchy doesn't grow with the network size。

 Ive not yet shown you a network with more than four nodes。Okay。

 so that you should have no reason to believe that the price of energyarchy stays constant as I scale up these networks to arbitrarily large size。

 Okay， and that's the main part of the theem and the main part of this lecture。

Give me any network with these cost functions。 The price of energyarch doesn't go up。 doesn't matter。

All right。So， by construction。Really， by the definition of the piggo bound。

For a set of cost functions， C。Alpha of C， the piggo bound is a lower bound in the price of energyarchy。

 each of these was a legitimate network that we could exhibit。

 We take the worst of those lower bounds。 and that's still a legitimate lower bound。And now。

 the formal version of the main result is as follows。For any set of cost functions， as always。

 the cost functions are non negative， non decreasing and continuous。

 rather than that can be any set of functions you want。Okay。And now。

 the main point is for all networks， no matter how big。With cost functions in C。

The price of anarchy in such a network。Is upper bounded。By the pig bound。So again。

 we know this is a lower bound。 This is a lower bound achieved already in trivial networks。

This is an upper bound for any network。So that's why we conclude as a consequence that worst case networks are always simple。

 no matter what the cost functions are， okay。And again。Computing alpha of C is not such a big deal。

 So knowing that alpha of C achieves the worst case price of anarchy reduces computing the worst case to just on these simple networks。

 Okay， which I'm asking you to do on the homework。Okay。

So the original formulation and proof of this is an old result of mine。

 The proof I'm going to show you today benefits from simplifications by a few different people。

 So Emir Ronan and also by a subsequent paper by Korea Schuls and Ste Moses。

So any questions before we start talking about the proof of this theorem。You know。

 I glossed over that。 It's excellent comment。 So that's for the lower bound。

 It's not for the upper bound。 So the question was。

 the question was pointing out that I'm actually cheating in a small way， okay so。

If you look at the definition of a piggo like network， I use it one cost function， C of something。

 And then I use a constant cost function。So to really claim that this piggu like network is a legitimate lower bound for a set of cost functions。

 C， C better include the constant functions because I'm using that on one of the links in my example。

 So yes， So for the lower bound only， you want to assume that there are various weaker assumptions that are also sufficient。

 but that's the simplest version。For the upper bound， which is what I'm going to prove。

 you don't need any such assumption。 Yeah， good comment。Other questions？Alright。

 so I need to do some preliminaries。Before we prove this。

And the preminaries will be very familiar to anyone who's say， taken C S 2，61 or worked with flows。

The reason I have to do these is because so far I we've only talked about equiria in very simple networks where it's kind of obvious what they are。

 So we just really， you know， to be rigorous， we should pin down what are flows。

 what are equiria and what are the costs of flows in a general network。So let's do that real quick。

So。Consider a。Graph with source and destination。Okay， so SD network。With our units of traffic。

And all the points that I'm going to try to make in the next few minutes are already illustrated by the racist paradox graph。

So everything I'm about to say， I would just try to interpret。

On the racist paradox graph with the teleporter involved okay。So what do we really mean by a flow。

Well， the flow just explains how the R units of traffic are split over the path of the graph。

So formally， it's a non negative vector。Sorry。On the ST paths。Scrt P of G。And of course。

 it should be the case that the total amount of flow sums to the total amount of traffic。

So with some over the flows， over the paths。Equal to R。So for example， in the braces Paradox network。

If we say it's one unit of traffic， a legitimate flow would be to route 50% on the zigzag。And 25%。

On the two two hop paths。So there's three SD pass in this graph。

 I just show you a way of splitting one unit traffic over the three。W your F。Now， sometimes， in fact。

 often。We're going to want to zoom in。And understand what's going on on a single edge of the network。

The reason pig like networks are so simple is because edges and paths are the same thing。

Not so in a network like the Brace Paradox Network。

A particular edge in this network participates in more than one path。Okay。So。We will write。

For a given edge， we zoom in。And by F subB。I just mean。

The total amount of flow that at some point crosses this edge in its path。So I just sum。

Over the path， that contain the edge。And I look at how much flow it puts on that edge。So。

 for example。How about。This edge right here。 So consider this flow， the 25，25。

50 flow upper left edge。 What's F sub B for the upper left edge。075。RightThere's a contribution of 0。

5 from the zigzag and 0。25 from the upper 2 hop path。So that's going to be 0。75 on that edge。

Symsymmetrically 0。75 on that edge。How about this one。25。Same thing here。

How about the zero of the teleport？Point5， only the zigzag uses that。Okay。So given flows on paths。

 we can zoom in on an edge and ask how much total flow crosses this path。So。

When is a flow in equilibrium。Well， the intuition， I hope， is clear。 O， The intuition is just。

 if you look at any path that some traffic actually uses。

That better get to the destination as quickly as possible。 That would be the shortest path。

So all flows should be on shortest paths。Now， it's sort of more subtle than that， right。

 because which pass or the shortest also depends on what people are doing。Right。

 so like in the Bra Paradox network， or before we added the teleporter。

 if everybody's on the top path， then the bottom path is the shorter one。

 If everyone's on the bottom path， then the top path is the shorter one。

 So when we say everybody is using a shortest path。

 it has to be with respect to the current traffic pattern。

 with respect to the congestion and all the edges。Okay。

So here's the definition in general of an equilibrium flow。It should be the case。

 So a flow is at equilibrium if and only if it meets the following condition。

So an equilibrium flow F。It should be the case that whenever。A flow from S to T is actually in use。

It has to be the case。This is the shortest path。Okay。And again， what does shortest path mean， we say。

 well， let's look at how much traffic is on each of the edges。In the path。Ananimate。Okay。

 so I write F E here。 That's the traffic under this traffic pattern on the E E。

 What's the travel time along the path， But it just adds over the edges in the path。

And as a shorthand。I will abbreviate this notation， as the cost。Of a path P。

With respect to a traffic pattern， F。Okay。So。The a traffic pattern or a flow。

 We're going to use flow and traffic pattern interchangeably。So， for example。

 suppose I add cost functions now to this network。 Suppose I add the canonical cost functions。X0。

 x11。Is this flow and equilibrium in this network。Why not。What's the violation of that condition。

So the first question is， there's three paths in this graph。 Okay， I've fixed the flow。

 So let's just ask， how short are the three paths given this flow。Well， out of the top path。

 So with respect to this orange flow， what's the travel time along the top。1。75， exactly。

075 here because there's 。75 traffic on it， plus a warm。Okay， by symmetry， same thing in the bottom。

1。75。 So those are paths that are being used。But they're not shortest paths。

G a zigzag path is 075 plus 0751。5 less。 So the violation of the equilibrium condition in this flow is that。

Some path in use， In fact， two of them are not minimizers， or not shortest paths。

And so I hope it's intuitively clear that， you know， any such violation。

 we shouldn't call an equilibrium。 Okay， if some path is in use and longer than all the rest。

 there's an incentive for people on that path to switch to load balance。

 to switch to one that's shorter。 Okay， So this is the definition。

 This is what it means to be an equilibrium。There's two facts about equilibrium flows that for today。

 I want you to take on faith。We will understand why they are true next week，So， the first fact。

Is that an equilibrium flow exists。So when we prove theorems about equilibrium flows。

 they're not vacuous。 Okay， we actually are talking about something。 Again。

 we'll see why this is true later on。And then as I've stated， the price of anarchy， a hold on。

All right， so。Last ingredient of the preliminaries。The objective function。Okay remember。

 the price of anarchy is the ratio of these you know， travel times。

 So how do you express the travel time for a flow in a general network。

There's actually two ways to do it。And it's important you're familiar with both of the ways to do it。

 You can either count up travel time over paths。Or it's exactly the same that count it up edge by edge。

So let me write down the formulas。 and then we can go back to the brace Paradox graph and interpret it。

So our objective function， the quantity we'd love to minimize， given the option。So first。

 I'll just write it down in terms of the paths。 So we just want to accumulate all the travel time that anyone experiences。

And so just like in pig like networks， we looked at an edge。 And we said， what's the travel time。

 How many people experience it Here， We're gonna look at a path。Okay， so we're given path P。

We just say， what's the per unit travel time。On a path， remember C sub P of F。

It's just the sum of the travel times of the constituent edges。

 because that's just how long it takes you overall to get from S to T。So that's the travel time。

 like 1。75 from S to T。F C P， that's how much traffic。Inncoururage that travel time。

 And we better make sure we account for everybody。So we just sum over all the path in the network。看。

So that's the way you count up travel time path by path。The other way you can do it。

 which is exactly the same thing。But I'll leave it to you to verify。As you can go edge by edge。

 so in other words， you say， let's zoom in on an edge。

What is the travel time that people experience just on this one road？

Let's look at how much of the traffic at some point experiences that travel time。And again。

 let's make sure we account for everything by summing over all of the edges。Sure。

The equivalentence of these two things is literally just a reversal of sums。

 I'll leave it to you if you're unsure about that。So all this would say is that if we wanted to compute the total travel time of this orange flow。

 we could do it in two ways。 We could do this say， okay，5 of the traffic has travel time 1。5。

 And then this other 。5 has travel time 1。75。 That would be the path based way of counting。

 Or we could just say， look， you know，075 experiences 075 here。 Same deal here。

25 experiences one here。 Sam thing here。 And that's a 0。

 Thatll be the edge by edge way of counting at the same thing。😊。

But it turns out in the two parts of the proof of the theorem。

 the first part is going to be useful to think about past。

 and the second part is going to be useful to think about edges。 So I really do need them both。

Allright， And then the one other fact I told you I wanted you to take one fact on faith。

Equiilibrium flows exist。 The other fact I want you to take on faith is that theyre essentially unique。

And by essentially unique， I mean， that while there can be multiple equi。

 they all have exactly the same cost。 So there's no reason to care about which equilibrium we're at。

 Okay， they're all basically the same。So， fact。And again， we'll see why this is true next week。

And I mentioned this。Because I'm stating all these themem about the price of anarchy。

 What is it exactly。Well， it's the cost。Or the travel time， okay。Yes。

 let me have some notation for this。So I'm going to abbreviate this by capital C of F。

And the price of anarchy， by definition， is then just the cost of an equilibrium flow。

Over the cost of the optimal flow。Okay。And by the two facts I told you， this is well defined。 Okay。

 so the numerator is talking about a non empty set。 There's an equilibrium flow。

 and all of them evaluate to exactly the same cost。

 because I don't have to worry about which1 I stick in top。Alright。

 so we're done with the preliminaries。 You should now feel comfortable talking about flows in general networks。

 when they're at equilibrium， when they're not and how we measure how good they are using this total travel time。

😊， so given all that， we can now get to the interesting part and prove this。 Any questions。对。

Good questions。 You mean like worst case over the paths。第二个。没确定。Trustper。

So I guess what I'm saying is here， I don't even need to define that。

 right So if there were multiple equilibriumria that were fundamentally different。

 I would actually have a nontrivial modeling decision to make， which is， do I measure。

 So suppose they have a system with multiple equilibriumlib。

 And I want to say some stand right equilibrium。 Now I have to figure out which one do I say something about。

 So Wednesday willll have to deal with that issue。 This model is really nice because all equilibrium the same。

 So there's no need to even make a decision。we know when。系T嚟。We'll talk about that also。

 So another excellent question is it's all fine and good to prove these bounds about the equilibrium of your system。

 But how you you're an equilibrium。 So well， we'll discuss that at some length， actually。

 So that's the more kind of， know， second generation results on price of energyarch。

 but we're going to start by assuming in effect， you know， by celebrating a bound about equilibrium。

 We're implicitly kind of assuming that it's meaningful。 We're assuming the system is at equilibrium。

 So that'll be our assumptions for this week， we'll relax those and lectures to come。😊。

Other questions。What's going？Yes， so a flow， by definition is is a vector on the S T paths。

So like in the network， I just hi there were these three SD paths。

 And so that's what we're talking about。 So that somehow the flows being split amongst the SD paths。

B你要介绍面。Or would you say don't hear anything？Flow is usually the entire vector， entire set of vectors。

 yeah。Okay， so the main thing we're going to need from the preliminaries in the proof of this theorem。

 I mean， in addition to just this definition is we're gonna need to remember what the objective function is。

 these two ways of writing about the cost。So that's the one thing I'm going to really use。O。

So proof of may result。So now we have to think about any network at all。 Okay， again。

 for the lecture， I'm assuming there's a single source in a single destination。 In fact。

 the theorem even extends to multiple sources and multiple destinations。It's a fixed G。

The only assumption。Is that the cost functions lie in some sets C。 And again。

 think of C as that fine if you like。Okay。So fundamentally， I need to compare these two numbers。

 Okay， How well an equilibrium flow does and how well the optimal flow does。

So F will be an equilibrium flow。F star is an optimal flip。Okay， so stars will always be optimal。

 No star will always be equilibrium。Two parts。 Neither one is that long。And if that， conceptually。

 part  one is very straightforward， okay。The culmination of part 1 will just make precise the following statement。

So if you have an equilibrium flow， and then I freeze the cost of every edge at that amount。Okay。

 so remember， every edge has its cost function。 There's a lot of traffic。 It's expensive。

 It takes a long time。 If there's not much traffic， it doesn't take that long。

 But suppose we put the equilibrium flow in the network。And I just freeze all the costs。

 and they all become constant。This is a thought experiment。 So the claim will be， if I do that。

 if the costs are frozen， then nothing is better than the equilibrium flow with respect to these frozen costs。

And the reason is just， you know， by definition， equilibrium route paths。

 route flow and shortest paths。 Like what else could you do that would be better。

So that's going to be part  one， just making that precise。Okay。So since f is an equilibrium flow。

Whenever there's positive flow on a path。Positive traffic on a path。

We know the cost of that path with respect to the traffic pattern。 F。

 with respect to the equilibrium traffic pattern is as good as that of any other path。5天。So。

 in particular。Suppose I just look at two different paths， both of which are used by the equilibrium。

What can you say about the travel times along two paths， both in use in equilibrium。Yeah。

 they're the same。 right， So I just instantiate this twice once with each path，right。So。

 at an equilibrium。All paths in use。Have a common travel time。

And that travel time is no larger than that along any other path。嗯。

So I'm going to use the notation capital L。For the common length of all of these paths that are in use by the equilibrium。

Okay。So at L。Be the common length。Of all equilibrium flow paths。And so again。

 what we're shooting for is we're just saying if we freeze the costs in this state。

 this equilibrium is as good as anything else。 Nothing else is better。Okay， so， formally。

Let's look at the cost of equilibrium。 As remember， for this first part。

 I'm going be using the path based way of counting up cost， counting up travel time。

So we sum over the paths。we look at how many are on the path， we look at the cost of that path。So。

 this is the equilibrium。So for every term here two thing， one of two things is true。 Okay。

 either F P is 0。 The flow isnt。 This path isn't being used。 and we don't care or。If it's in use。

We know that the length of the path is exactly capital L。对。

So this sum becomes very simple to evaluate for the equilibrium flow。

This is just equal to L whenever we have a positive coefficient。And this thing just sums to R。Okay。

Becauses the flow。So it's actually very easy to understand。

Cost to the total travel time in the equilibrium flow。

 It's just the per unit cost that everybody incurs。Times the amount of flow that's incur。And。

Let's keep these frozen。And look at that star。Okay，So I guess one thing to remember is， you know。

 So F star is this optimal flow。 Okay， it's beating the equilibrium flow。 It's better than it。 Okay。

 But remember， one of the reasons it's going to be better than it is because it's going to have different costs。

 right， It might have less congestion on some edge。 Remember， like， think about pig's example。Right。

 so the equilibrium puts a full unit of flow on the X making a cost1。

 The optimal uses it in moderation。 puts only a half there。 has cost only a half。 Okay。

 so they have different cost functions。 We're doing this weird thought experiment where we penalize the optimal flow by freezing them at the equilibrium level。

Okay， so you're going to write down a quantity which doesn't make a lot of sense。

 but it's useful for the proof。Which is I look at the optimal flow。 Okay。

 so F star is how it spreads its traffic。 But for whatever reason。

I evaluate path links as if the equilibrium flow is in the network。That's what I'm doing。And again。

 this is extremely easy， maybe not to evaluate， but at least to lower bound。 And again。

 the intuition is just。The equilibrium is on shortest pass。 How can you do better than that， okay。So。

 precisely。This is at least capital L。Right。And again， this evaluates our。

So that's what we mean by freezing the edge cost at equilibrium levels， No other flow can be better。

 Let me just rewrite this so that it exports better to part 2。Yeah。Okay。

So this was easiest to see using the path way of accounting for travel time。

 But I want to have it in the edge form。So， this。Is at least this。Equivally， if I sum over edges。

Sorry， that's at most that。So if I sum over our edges instead。This is an equivalent statement。Again。

 I take the optimal flow amounts， but I use the equilibrium costs to evaluate it。

 That's the same statement。And then again， exactly the same statement。

 and the form I'm going to use it in part 2。Let me just subtract that from that side。So， this is。

What I'm going to need from part one and part two。Again， the intuition remains the same。

If you freeze the costs at the equilibrium levels。You can't do better than routing entirely on shortest paths。

So part 2。So very roughly， this is a little inaccurate。 But sort of what we're gonna to do in part 2。

Notice we haven't used the， We haven't used anything yet。

 Part 1 is really just about equilibrium flows。 I haven't referenced what the cost functions are。

 I haven't referenced the pigoo bound， nothing like that，So sort of morally。

 what we're doing in part 2 is we're going to say， well。Let's zoom in on a given edge。

And argue that on each edge， separately。It looks enough like a piggu like network that we're not going to be doing worse than the piggu bound alpha of C when we compare how the equilibrium does and how the optimum does on a given edge E。

So the dream would be， we zoom in on an edge， and we say the equilibrium cost is no more than alpha times the optimal cost。

 And then we sum that inequality over all the edges， and we'd be done。 That'd be the dream。

 This edge by edge example。That's not quite going to work。

There's gonna be edges with this more equilibrium flow。

 It's gonna be edges with this more optimal flow。 It's kind of hard to say it's really like a piggo like network。

 But we'll say， you know， it's like a piggo like network on each edge up to some error term。

And it turns out the collection of error terms will be able to control using this conclusion of part 1。

 Okay， so roughly， we're going to treat each edge like its own pig like network， roughly。All right。

 so。Here's where use the definition of the piggo bound。 Can let me remind you what that is。

We're working with a set C of cost functions。 The piggo bound just says it's the largest price of energyarch you ever see in a piggo like network。

 So you take a worst case choice of the top links cost function。

 You take a worst case choice of the traffic rates。

That's the equilibrium cost in the piggolike network。

This is the optimal cost for the best case choice of x， and the ratio is the price of energyarch。

So we know that is what it is。Because this is a worst case choice， if we instantiate。C and R and X。

 we take particular values of those three parameters that right hand side will only be less will only be upper bounded by alpha of C。

 because alpha is the worst case， the largest choice。Okay， so any instantiation of ease。

Gives us a number that's upper bounded by the piggo bound。So how do we instantiate？

We do it separately for each edge of the network。So again， we're zming in on an edge， okay。

So there's only， you know， there's one cost function on the edge。 There's one cost function。

 this expression。 So， of course， we instantiate that outer supre to be this cost function。

We think of the equilibrium flow。 So again， keep in mind， we were given this graph G。

There's some equilibrium flow， there's some optimal flow。 What we're doing is on an arbitrary edge。

 we're sort of zooming in。It has some cost function。 There's some amount of equilibrium flow here。

 We'll interpret that as a traffic rate in the piggu bound。

Theres some amount of optimal flow on this edgy。We interpret that。As the choice of the splitting X。

So this is a particular way to instantstiate these three things。

So this quantity with those instantiations is at most alpha of C。Okay。

 so I'm just plugging these three things into that formula。Okay。Okay。Believe it or not， Romo's there。

All we have to do is rearrange in sum and then interpret， and we'll be done。

So let's swap thenominators。So let's remember what I'm trying to do is I'm trying to say the equilibrium is near optimal。

 It's not much more than the optimal flow F star or equivalently。 I'm trying to lower bound F star。

 saying it's at least a large fraction， less than one， but a large fraction of the equilibrium cost。

So let's just rearrange this to isolate the cost incurred by the optimal flow F star on this edge E that we've zoomed in on。

And we get something， actually。Kind of suggestive。Okay， so again， once we divide through。

 we get a one over alpha times that equilibrium cost on this edge。

So this inequality here is what I said was the dream。Were you zooming on an edge。

And you say the equilibrium is not doing much worse on the optimum on this edge。

 And then you just sum over the edges。 That's what that would be， if that were true。O。

 so again alpha is something like four thirds。 So this would say that on this edge。

 F stars get incurring at least three4 of equilibrium。You know， but the dream kind of not， you。

 quite fulfilled。We have this error term。So plus。F star E minus F E。Time C。A bey。

That's the residual after rearranging。But， some。Over all， the edges。

So what do we get if we sum this over all the edges？This is just the cost of F star。

 Remember one way to count up the cost of a flow is you do it edge by edge。

 Look at the cost of the edge with respect to the traffic pattern。

 Look at how much traffic concurs it。 That's exactly what this is。So if we sum on the left hand high。

 on the left hand side， we get exactly what we want to lower bound， the optimal flow。

By exactly the same reasoning， right， This is just some constant。

 This is just like three/4 or something。By the exact same reason， if we sum， you know。

 this term summed over all the edges， this is just the total travel time and the equilibrium flow， F。

Then we have the sum。Of the air terms。I've tried to let things unfurl on the board so that it's rather clear how we control this some of the error terms。

What do we know about it？嗯。The whole point of part1 was to show that that was non negative。

That's in the box。So what's in the box says this is non negative。 Again， it just says， look。

 this is basically saying the edge costs are frozen at the equilibrium amounts。

And we're just looking at kind of， we're comparing opt to the equilibrium。

 and the equilibrium is as good as it gets。 If you freeze the edge costs at the equilibrium amounts。

 So this is not negative。 Therefore， if we drop it， we still have a legitimate lower bound。

So by part one。Meing this thing。We get exactly what we wanted。

That the optimal flow is at least a one over alpha fraction of the， of the equilibrium flow。

 Or if you prefer that the equilibrium costs no more than alpha。

 the piggo bound times the cost of the optimal。Apologies for going over。 I'll see you on Wednesday。

