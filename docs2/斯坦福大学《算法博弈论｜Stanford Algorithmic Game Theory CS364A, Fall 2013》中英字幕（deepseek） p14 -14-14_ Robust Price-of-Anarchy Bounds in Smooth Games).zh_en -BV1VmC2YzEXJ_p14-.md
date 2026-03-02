# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p14 -14-14_ Robust Price-of-Anarchy Bounds in Smooth Games).zh_en -BV1VmC2YzEXJ_p14-

So this is a fun lecture to give actually， because the theory I'm going to tell you about today has its genesis in this very class in CS364A so the story was is five years ago。

 I was in the same sort of segment of the class teaching a bunch of price of energyarchy analyses and really just for pedagogical reasons I was trying to figure out sort the optimal way to present all of these proofs to make it as transparent as possible and as I was doing that it became clear that there really was for many of the most well-known price of anarchy bounds there was a generic recipe for deriving them and in fact that generic recipe can even be precisely formulated as a definition which is a definition you'll see today and then what was cool is this definition actually has consequences。

 implications and we'll use it today to prove price of anarchy bounds on coar correlated equilibriumlibria so those was the biggest set of equilibriumlibria that we talked about on Monday so the hardest worst case upper bounds to prove and those are the ones we will be deriving from this definition。

It came out of the class about five years ago。All right。

 so before I give you I'll give you this definition， about halfway through class or so。

 the intent the definition again is to unify a number of price of anarchy analyses。

 So before I do that， I want to give you one more important example。

 So it's an application domain that's already interesting in its own right。

 but for it will also serve as another key special case of the general definition。

 And so before doing the second price of anarchy analysis。

 let me just tell you what are the similarities you should be looking for compared to the one we saw last week which in the one last week was the 2。

5 for the price of anarchy and atomic selfish routing games with the affline cost functions。

 So it's not important to remember the calculations， the details from last week's proof。

 but let me just sort of remind you what the high level structure of the proof last Wednesday was。

So we started know we had an arbitrary sagera game Maine cost functions。

 We started from an arbitrary equilibrium and arbitrary optimal solution。

 and the very first thing we did is we said how are we going to ever use the hypothesis that we're working with the Nash equilibrium we said well。

 know N equilibrium means deviations only make you worse So that seems like a good idea we can generate upper bounds on individual player costs by considering hypothetical deviations So which hypothetical deviation should we use Well。

 sort of the obvious thing to try was the optimal solution， you say player I。

 how come you're not doing what you're supposed to be doing in the optimal solution and that gave us an inequality。

So step one。Was invoked the Pna equilibrium hypothesis。To derive inal of the following form。

 I'll write it in the notation of cost minimization games that I introduced on Monday。

 So for a given player I， So here S is the equilibrium， if it deviates， then it only gets worse。

 And in particular， if S star is the optimal solution。

 if I deviates unilaterally to what we wish we were doing in the optimal solution。

It would only get worse。And one important point， which I'll mention several times today is turns out。

 if you look back at that proof last week， this was the only time we ever used the hypothesis that S was an a equilibrium。

 In effect， after we generated these K inequalities， one per player。

 we threw it out and never used it again。 That's going to be an important property of that proof。

So that was the first thing we did。 So second step there's going to be four total。

Second step we just summed these inequalities over all of the players。

And what was really cool about that is we had an upper bound on the individual equilibrium player cost。

 and we sum over the players， the left hand side was exactly the equilibrium cost。

 And in a price of energy analysis， that's exactly what you're trying to upper bound。

 So the left hand side after summing was exactly what we wanted it to be。 Now。

 the right hand side was weird。😊，Okay， so we did this sum。

 And we got this sort of like entangled version of the optimal and equilibrium flows。

 So in the notation last week， what we observed was we had like a term with the product of F star E and F E。

 And we had no semantics for that。 We just didn't care about it。So step3。

 which was kind of the hardest one， was relating the entangled term that we didn't care about to the only quantities that we actually do care about。

 the equilibrium and optimal costs。So， in step 3。不是。We related the entangled term。

Which was the right hand side after summing。2。The two quantities we cared about。

 the equilibrium cost。And the optimal cost， precisely what weve proved is that this entangled quantity is bounded above by5。

5 third times the optimal solution plus1 third times the equilibrium cost。

 that was the precise statement。And then once we've done that。

 we just solved for the price of energy。Okay， so we had equilibrium cost both on the left and the right。

 We had a one third times it on the right。 We subtracted that。 We multipied through by three/2alves。

 And that's what gave us that the equilibrium cost was the most。2。5 times the optimal cost。 Okay。

 so again， not important。 You remember the details。 but this is the high level structure。

 I'm going to show you in a different application domain how we can apply exactly the same structure to get another tight price of anarchy bound。

 And then we'll zoom out and ask what what's the sort of generalization of these arguments。

 And then we'll turn to applications of that generalization to robust price of anarchy bounds。

 So that's the plan。So here's the next application domain。

So this is a type of location game game where players are trying to figure out how to position themselves in a network。

So the one I want to talk about today。There's a set F of possible locations。

Where players can locate themselves。You can think of these as like， you it could be anything from。

 you know， where you're deploying a， you know， web server cash to where you want to build the next artisan chocolate store。

 as you like。There is potential customers， consumers， whatever， it's called them markets。

And in each market， there is some value that they have for receiving whatever service all these players are trying to sell。

And these values are just known。 It's not like in mechanism design。 Everybody knows what the VJs are。

 Okay So you know how much money you're going to make if from somebody。

 if you can sell them artisanal chocolates。Now there's also。A cost。

So for every location L and market J， there's some cost of providing the service with the product to J from L。

So in the simplest case， this could just be the distance。 But in general， it's just some kind of。

 some kind of cost。 It could， for example。Relate to how well your technology fits。Fits theirs。

So the players is， each player is just responsible for picking one location。 Okay。

 so one element from the set F。Oh。So I'm going to go ahead and just say that each player I has some restricted set of permissible locations。

 F sub I， if you want， just think of the F's as being F。

 Think of that any player can locate anywhere if they want。But more generally。

 you can have a permissible locations F sub I。Allright， so in defining a game。

 what I need to tell you。 I need to tell you the players。 told you the players。

 I need to tell you their strategies， told you their strategies。

 So now I have to tell you their payoffs。 Okay， so let me do that using an example。

 and then I'll be clear what the payoffs are in general，So。

We have the possible locations over here in the possible markets here。Let's say we have two markets。

Each with value 3。Let's say there's three possible locations。

And let's say for there's just two players。 So player one key to go on the top in the middle。

Is it' two strategies？And player two can go in the middle or the bottom， that's the two strategies。

So there's only four possible outcomes of the game。 two strategies for the two players。

 So let me tell you in this example， how the payoffs are going to work。Basically。

 what's going to happen is you， once these players locate。

 they're going to engage in price competition to try to sell to these markets。

 I have to tell you the C，2， I now realize。So let's say from the top to the top or the bottom to the bottom。

 it costs one。 So these are the C LJs。And from the middle， it costs two to either market。And in fact。

's say， let's say it's infeasible to serve the bottom market from the top location or vice versa。

Alright， let me just talk through this。 So let me just talk through two possible outcomes to tell you how it's going to work。

 So suppose player number one chooses the top location。

 Player number two chooses the bottom location， okay。So it symmetric。

 I'll just talk through player one situation。So player 1， if it locates a top。

 it's unable to serve the second market。 That's infeasible。

 but it can serve the top market at a cost of one。Okay。And moreover。

 it has no competition in the top market， given that the player number two has located on the bottom。

number one is the only firm that can actually sell to that market。

 so it's just going to price at the highest price it can get away with。 Now。

 the most the market to be willing to pay is three。

 So the assumption is going be that given that there's no competition。

 firm one sets a price of three extracts all of the value from the first market。

 it costs one to serve it。 So it's payoff will be 3， the price that it charges -1。

 the cost that it pays for a payoff of two。Same thing down here， exact same reasoning。

So suppose instead。That player number one。 So that's also going to be a na equilibrium in the sense that a unilateral deviation from that could only make your path worse。

So to see why， So imagine that the top player relocated to the middle， okay。

So a couple of things change now。 So if you look at the second market。

 it used to be that the second player had no competition in the second market。

 It was the only one capable of supplying it， okay。That's no longer true with player 1 here。

 it could also supply the second market， although it would cost it too。Al right。

So the way we're going to think about it is， you know。

 while the second player would love to continue to charge a price of three just like before。

 now I can't get away with it。 If it charge3， it could be profitably undercut by the first player。

 we would assume a player can serve any number of markets。 Okay。

 so there's no capacity constraints on the players。So if it charge the price of 3。

 this guy could charge 2。5 and steal away the consumer base。 So price competition。

 given that these two players at these locations， well。

 this guy can now get away with a price of 2 or 2 epsilon， something like that。

 So it'll price just low enough that it becomes， there's no incentive for this guy to enter the market。

 so this guy will just take the full second market。 The value 3。

 but it's only gonna get a revenue of 2。 and then its cost will be a payoff of one。Now。

 in the middle node， it's still the case that player 1 has market  one uncontested。

 And so it's still gonna charge a price of  three。 But now it pays the cost of two。 It's production。

 its transportation cost has gone up。 So both of the players， cost of drops。

 payoffs have dropped to one in this case。So let me write down the general payoffs then。

 and then I'll see if it makes sense。So in general。

So I'm going to continue to use this sort of S vector notation。

 this is just a choice of location for each player。And always in this situation。

 the payoffs you just going to handle the different market separately。

So the path of a player is it's pay off from all of the markets。So what's the path for the markets？

Well， basically， to get any path at all from a market， first of all。

 you better be located closer to that market than anybody else。

Because that means you're the unique person who can set a price low enough to get the consumers in that market。

 Second of all， you better be close enough that you can cover your cost okay with their value。

So it's going to be  zero。So， okay， let's say。Say I picks location L。

So if the cost to of serving L from ofserv J from L is more than VJ than forget it。

 There's no way to have a profitable transaction， So 0。If CJ is at least FJ。

Or if theres some other picked location， which is even closer to J。 Okay。

 then they're going to be able to just。Kick you out with price competition。So， or。L not closest。

Choseen location。To Jay。On the other hand， if you are the closest。

 then you're the one in the position to actually extract the value from that market and you're going to charge the highest price you can get away with。

 the highest price you can get away with。 Well， that's governed by whos second closest。 So remember。

 that's what we had here。 So the price that this person could charge this market was bounded by two。

 because that was the next closest location or the minimum of that and the maximum this person is willing to pay the value。

So this is going to be。I'll say DJ2。So this is the price you're going to charge。

This is the cost that you still have to pay。And the definition of this。Is just the minimum。

You can't charge more that they're willing to pay and then you also。

Can't charge higher than the point at which the next closest person could undercut you。So in effect。

 what we're saying is that as a player， the revenue that you can capture your payoff that is is going to be your sort of competitive advantage of the respect to a given market。

 Okay so a different way of thinking about is if your technology if your cost is better because your technology is better。

 then your payoff is going to be the extent to which your technology is better than everyone else is and your serving cost is less。

 So we think of players as picking these locations。

 then people just charge the highest prices they can get away with and this ones up being their payoffs。

 If you want you can sort of derive these payoffs from first principles。

 you can set this up as a three stage game， you can study what are called sub gameme perfect national equilibrium。

 which are appropriate for games of multiple stages， we're not going to talk about them in class。

 but it is covered in the AGT book if you're interested。One other thing I'll say is， you know。

 we've sort of flipped maximizing versus minimizing compared to routing， routing。

 We wanted to minimize costs here。 We want to maximize payoffs。 neededless to say。

 that's just a cosmetic difference。All right， so what do we want。

 So we're going to study surplus maximization。And in this context。Surplus is just the value provided。

 So the sum of all the VJs of the markets were served by somebody minus the costs。 Okay。

 so minus the CLJs。 for everybody gets served。So let we would just write that this way。

So I'm going to use the notation。Capital V to denote the surplus。

 which is a function of the chosen locations。 And again。

 we're just going to add it up market by market。And I'll write it this way。

Where DJ is the same thing as DJ2， except it's about the closest location。

 not the second closest location。So this is the minimum。AVJ。

 so if the closest person is further than VJ away from you， you don't get served at all。

 so it's just going to be zero。Or。The closest location。To J。So， for example， up here。

 in the first outcome we looked at with one player on top， one player at the bottom。

 both markets are served。 So that's a 6 minus a cost of two。 Thatll be surplus 4。

 If the player moves from top to middle， again， both markets are served。

 but now one of the transportation costs is gone up to 2。

 So the surplus would drop to from 4 to 3 okay。So that's the description of the model。

So when we talk about the price of energyarchy in games like this。

 we're just asking what fraction of the maximum possible surplus are Nash equilibriumria guaranteed to achieve。

So that's what theor' is going to be about。So questions about the， the model， the description model。

Yep。来继续。你て分さ。Exactly， yeah。 So I was， I didn't。 know， I didn't write it down， but。

This is closest location actually chosen by a player， and similarly here， second closest location。

 actually chosen by a player and same thing here。So if you want， you know。

 the unchosen one is just think concept of deleting them and then do these computations。And I also。

 you know， so this， of course， is a function of S。 So this depends on which locations were chosen。

 I just I didn't write that notation。Keep in mind that S determines what these numbers are。这是什么但。

It is allowed。 And what was the second question， Does it give what， No it is allowed。So I mean。

 you think about what would happened in real life。 So suppose there were sort of two。

 supposeupp there were literally two stores selling the same product at the same place， right。

 with nothing to differentiate them。 so the price competition would just drive the price down to whatever the cost of service was。

Yeah， so you wouldn't expect this a natural equilibrium， but it is allowed。 So， I mean。

 basically both markets are going to be served at a price of two。 So the surplus will be fine。

 So remember surplus surplus just says how efficiently So first of all。

 how many people are actually being served。 and secondly， how cheaply is it being done。

 that's the surplus。 Then there's this other question of how is that surplus split between the consumers and the sellers So how much of it is revenue and how much of it is consumer surplus。

 And so the consumers would love it if people colocate because then the prices are going to be low and the surplus is going to go to them。

 But we're thinking more of sort of the firms as taking as being the strategic players And so they are actually in general going to want to try to segment the market。

 in the equilibrium。嗯。Yeah so again， surplus is just about how efficiently the allocation happens and then but the payoffs are in terms of revenue。

 And so you know if you look at the global system， arguably what you care about is just you want technology to go to as many people who want it as possible as cheaply as possible。

 but then of course， the firms care about how much of that surplus goes into their pockets。

 So there's the usual friction between those two。Okay， so here's the I'm gonna prove。

Theres an old theorem of Veta。So in every location game。Every Nash equilibrium。

 And I'm not going to prove it， but there can be multiple equilibrium in these games， but every。

Pure strategy National equilibrium captures at least 50% of the surplus。So obviously， in general。

 they might capture more， but this just says in every single game。

 every single equilibrium worst you'll ever going to see is 50%。

 This turns out to be tight and the next exercise set it asks you to provide an example showing that one half is the optimal result。

So the way I want to structure this argument is I want to first。

Talk about three properties that these games have。 And in fact。

 these three properties are the only ones required to actually establish this bound to 0。5。

So keep ro。So for the first one， willll seem very intuitive given everything we've said about auctions。

Which is just that the sum of the players payoffs are either revenue。Is bounded above by the surplus。

这边。I meant to comment on that。 So this is a maximization game。Okay。But I mean， is， I mean。

 you have to make some choice about which way to define the price of band from maximization games。

 So we're defining it in exactly the same way as before， you know， objective。

Of equilibrium over objective of optimum。So this is exactly what we wrote for cost minimization games for cost minimization。

 This was the least one for payoff max。 This is the most one。 Okay， But again， you know。

Good means close to one。 That's all， that's always true。 Max or， okay。

So you will see in the literature， some people prefer to always have these numbers at least one。

 so they'll just sort of flip the numerator denominator。

So we're going to prove that this is at least a half， that is， again。

 surplus of equilibrium is at least 50% of the best possible。Okay， so as I was saying。So again。

 I want to state three properties。 and then given I'll prove them， but they're all quick proofs。

 And then I'll use those three to derive the bound。

So the first property look at the total payoffs of all of the players。

 so that is their collective net revenue。 that's it most。The surplus。Okay。And again。

 we saw this over and over again in auctions。 the revenue you extract from people can't be more than the surplus that you generate。

So I'm not going to write proof actually。So this is just because let's compare payoffs with the objective。

So， the payoff。This is sort of the cost that you incur individually and also society。

 And then what you as a seller， take home is either whichever is smaller， the second closest。

Pick chosen chosen location to J or the maximum they're willing to pay。 Okay。

 so this is always going to be at most VJ。 So sum of the pi eyes is always at most V。Allright。

 so that's， that's the really easy one。Can't extract more than the surpluss revenue。So secondly。

We have an interesting property of these games。Which is。There's a nice way to think about。

 just exactly。How much revenue one of these sellers does take home in their pocket？

So the amount of money that you make in this game is exactly the extra surplus that your location provides to the system。

So your payoff。Is exactly the extra surplus。Over。What it would be。If you weren't there。

 but I just deleted your location。So this requires a proof that that's just really a one liner。

Let's just sort to think this through。to the right hand side here。

So imagine you have K -1 players and they pick their locations。

Player K shows up with his new location， okay， when we put that into the system。

So how does the surplus change？So what's the surplus， well it just decouples over the markets。

And the surplus of a given market is the difference between its value and the distance to its nearest chosen location。

So if we're given J， there's two possibilities， either this new case location is its new closest location or it's not。

If it's not the new closest location， there's no change in this market。 It's the same as before。

 if this isn't the new closest location， then the jump in surplus is exactly the extent to which this is closer than the previous one。

Okay。So the jump in surplus， when you add a new location。As you sum over the markets？

And you just say， well， what was the distance of the old closest location？

And what's the distance of the new one。And if you think about it。

 what do you take home in your pocket as one of these。One of these firms， one of these sellers， well。

 again， you look at you sum over the markets。 and what you take home is exactly your competitive advantage。

 the extent to which you are closer to it than the second closest competitor。

 so it's just exactly the same as the payoff。So that's property too。Property 3。

Is that the welfare function V。Is what's called some modular。

I think many of you have probably encountered some modularity on the homeworks。

 but I'll certainly remind you what it is here。One aside is。

 so this property too is a pretty nice property。 it shares some of the spirit of VCG。

 if you recall the way we defined payments in VCG was internalizing externalities。

 and in some sense the rebate that you get should be exactly the surplus that you added to the system。

 In fact， this property lets you prove that these location games or potential games in the sense of Monday's lecture or the surplus provides a potential function。

All right。Submaularity。So submodularity is a form of diminishing returns。

So what you want to think about is you want to think about a small set of locations。

Thenhan a bigger set of locations。And then the case you should keep in mind is where we're thinking about a location。

 which is not in either of those。 although actually， it doesn't matter。 But this is sort of。

 this is the case that's， that's the most relevant。And we want to say， what is the added value of L？

To T 1。 what is the added value of Elda T 2。 And so diminishing returns just says T 2 being that you have more stuff already。

 The added value should be less to the bigger set T 2 than to the smaller set， T 1。

So what this means is that。For all locations。L。And sets of locations。T1 and T2。Again， if you look at。

The value added of L to the bigger set。That should be bounded above。By the value that L adds。

So the smaller set。So this is the definition。Of some modular。 So that's what I mean when I say this。

 Now， why is it true in location games。Well， it's true， basically， just if we kind of recall。

Our discussion is surplus。And we recall this equation star。So remember， back in start。

 we were reasoning about how the surplus changes when we added a new location。

 So that's very relevant here。 We're thinking about adding a new location to a bigger set or a smaller set。

And we argued that the jump in surplus。Is exactly summed over the markets。

 the extent to which the distance to the closest location has gone down。And market by market。

 that's true。 So if I just throw sort of extra locations into， into the system， Okay。

 the distance between the closest one to a market is only going down。 Okay。

 so the value you add can only be dropping as there's more and more other people who might be the previous closest。

Location to the market。So， that is。If you inspect star。

Which expresses a surplus increase as you add one new location。

Then the bigger the set T that you're adding something to。The smaller the previous D sub Js。

 so the closer the previous closest location would be。

So that's why the net increase in surplus from adding a new location is only going down as the set that you're adding in to is going up。

Yeah。So those are the three properties。So given this。

 we're going to prove that in these location games are really in any game that satisfies these three properties。

 of which location games are one of in fact， many interesting examples。

 as long as these three properties hold，Nash Libria capture。Half of the surplus。

Any questions before we do that before we approve the one half pound？不。やらさい。Because it's。你嘅。Right。

 so in the example， in the first document， we talked about where there's one person on top。

1 person on the bottom。D subj of2 was plus infinity。There was literally like， I mean。

 I didn't draw those edges。 So basically， the other person wasn't even the market。

 So it was the minimum of  three and plus infinities。 That's why I was three。So。

Here's how we derive ven theem from properties 1，2， and3。And this is the point。At which。

We're going to。Mimic the four steps that we did， proving the 2。

5 for selfish routing and the price of anarchy there。So again。

 we're going to use the National gl hypothesis first， once and only once， we'll never use it again。

For each player we'll ask， how come you're not doing what you're supposed to be doing the optimal solution。

 And in this case， it's payoff maximization。 So we'll get a lower bound on the equilibrium payoff of each player。

 then we'll sum， then we'll have an entangled term。 Then we'll have to plot。

 This is where the nonchvia work is。 So properties one through three are mostly relevant for disentangling the entangled term。

 and then we'll solve for the price of energyarch。 we're going to do that again right here。So。

 consider an arbitrary。Location game， consider a pure strategy a equilibrium S。

And an optimal solution。S star optimal meaning maximizes surplus。So step1。

 use an actually equilibrium hypothesis。So what does that mean。

 that means deviations only make people worse， only decrease the payoff。 in particular。

 if someone tries to unilaterally deviate to their strategy and as star， their payoff only drops。

So in equilibrium， they're doing at least as well。As how will they do if they switched to its optimal location and the optimal？

And everyone else stayed the same。Sure。For all I。And again， it turns out。For the rest of the proof。

 we'll never again use the assumption that that is a Nsh equilibrium。

 this is the only time we ever use it。Second step is we sum。 And again。

 the reason we do that is because then the left hand side is something we care about。

 is the equilibrium objective function value。 We're almost in this case。 So if we sum over I。

We get that sum of players payoffs。Is at least this entangled thing we don't care about？有。So， that's。

Clear， I hope。Now， you know， this left hand side is also not what our theors about。

 Our theorems about the surplus of an equilibrium。 And this is just the sort of net revenue to the sellers at the equilibrium。

 But remember， property one of these games says that， you know。

 you can't extract more than the surplus。So you can certainly use the sum of sellers' revenues as a lower bound on surplus。

And this is what we're trying to prove something about。 Okay。

 We're trying to prove that the surplus of the equilibrium is pretty good。

 It's at least something else， at least some fraction of optimal。O。So that's step 2。 Now。

 step 3 is the， is the work。Generally。Which is how do we take a quantity we don't care about。

 It's this weird mixed up version of the equilibrium the optimal solution and relate it back to the only two things we care about。

 in this case， the surplus of the equilibrium and the optimal solution。

So what we're going to prove is the following。And again， we want lower bounds。

 lower bounds on equilibrium surplus。So we're going to take the entangled term。And lower bound it by。

The optimal surplus。Okay， that's a little bit too good to be true， right， becauseuse remember。

 a chain of inequality starts with the equilibrium surplus。

 and it's not going to be the case that every equilibrium is fully efficient。So minus。

 so it's at least alpha the onester plus minus something。

 And we're going to prove it's minus the equilibrium。Welfare。

 so at least the optimal welfare minus the equilibrium welfare。So step three is proving this claim。

All right， so。The first thing we have going for us is that we have a way to take seller payoffs and relate them to surplus in the system。

so we have this kind of VC G like looking property， too。

 which says that the payoff enjoyed by one of these sellers is exactly the surplus its location is adding to the system。

 Okay， so that lets us write and set a pie。 Let's us write Vs。 So that seems like progress。😊。

So by two。The left hand side。So this is just。The surplus in the entangled outcome。

Minus the surplus if I wasn't there at all。Okay， so is by property through。Now， you look at this。

 and you， and you know， you have a little bit of hope because it's sort of this， you know。

 summation of differences。And it doesn't seem like the terms are changing very much for the different indices。

 So this sort of has the flavor of a telescoping sum。 Okay， now it's not a telescoping sum。

 If you look， you know， if you look at I and I plus1， it's not the case that you get a cancellation。

 But you know， the next and basically final step is to massage this so that it is a telescoping sum。

 And that's where we use some modularity。Why might some modularity be useful？ Well， what is this。

 This basically says， what is the added value of the location chosen by I in the optimal solution。

 What is the added value of S star I， Give that you already have S minus I。

So modularity says diminishing returns， which says we can lower bound this difference。

By the added value of adding S star I to any bigger set。 And he said bigger than S minus I。 Okay。

 that's what some modularity says。And once you have that idea and you stare at this a little bit and you。

 you have the goal of making this telescope， you can figure out whats sort of the right set of players to add to S minus I to get the famous is telescope。

 turns out the right set to add is you want to add S I back in。Okay， so Is equilibrium location。

 plus to get it to telescope， you want to add in the optimal locations of the first I -1 players。

So let me to write that down。So by three。Meaning sub modularity。If we look at this this difference。

So the added value。Of S star I given S minus I。That's lower bounded by the added value of SI in any bigger set in particular。

I'm going to add in the optimal locations of I through I minus1。

And I'm going to look at the equilibrium locations of all K players。

 So this is a set of K plus I locations。Minus， again， it's。S star I's location。

 I'm thinking about its added value。So it should be absent over here。 So this one goes up to I -1。

 and again， I'll have all of this。So that's by sub modularity。And again， really。

 just by construction， I've chosen。This maneuver。So。That' the difference of welfare terms telescopes。

So now， if you look at the right hand side here and you compare I and I plus 1。

 you'll notice there is a cancellation。 Okay， so this term will， sorry。

 this term will cancel with the minus term with I plus 1。

So that means once you plug in this lower bound into the sum。

 the sum telescopes were left only with a positive contribution from the very first summan and its first term and a negative contribution from the second term of the last summan。

That is。So the biggest of all the sets is just the  two K locations， the equilibrium locations。

 S and the optimal locations S star superimposed。This is what you get from the first cement。

At the very end。Have it reversed。Let have it reversed。Minus v of S bar。Eququilib。So sorry， yeah。

 So you have the minus term from the first sum。 That's this。

And then you have the plus term from the final sum。 That's this。That's what you get after after the。

 after the smoke clears。 that's what's left。If you think about it， surplus is definitely monotone。

 You add more locations， The closest locations to places only getting closer。

 So the surplus is only going up。So I can lower bound this by just。

The surplus and the optimal solution。Minus the surplus and equilibrium。Ask Cla。

So that was the hard work。 So that was the disentanglement step for location games。

 You can lower bound the entangled term by the difference between the optimal and equilibrium welfares。

So step 4， the template is now， after you've done the disentanggling。

 you just solve for the price of anarchy。And so putting together steps 1 through 3。

We have on the left hand side， the equilibrium welfare。We have on the right hand side。

 the difference。Between the optimal and the equilibrium welfare。So if you rearrange。

 you just get that。Price of an key。Which again， I'm defining。As the fraction。

Of the optimal surplus achieved by the equilibrium。There's always one half。

And that's the proof of vetus theorem。Any questions about that。So again， one point of this is just。

 here's another relevant application domain Ma where it turns out it's analytically tractable to understand how close to optimal equilibrium are。

 And especially given that you're looking at both worst case games and worst case equilibriumria。

 it's quite pleasing that it can't be arbitrarily far away from optimal。 even for worst equilibrium。

 it's 50%。 And of course， in general， it will be better。

So that's point number one of these location games。

 And that's the reason they originally studied long ago。But so higher order narrative。Is that day。

Furnish a second。Very nice example。 The first being atomic selfish routing。 So a second。

 very nice example of。What are called smootha games？Okay。And the definition of a smooth game。

Is meant to articulate exactly what this， what one of these four step price of anarchy proofs looks like。

 Okay， so this is going to be the precise formulation of what this generic recipe for proving price of anarchy bounds is。

So I'm going to give you this definition。 and， we'll observe that these are two special cases of the definition。

 and then we'll move on to applications。 So nice properties of smooth games。 Okay。

 So questions before that。All right， so。So they're going to give you separate definitions for cost minimization games。

 like selfish routing and payoff maximization games like that location game。 But they're pretty much。

 you know， obvious analogs of each other。 So let's start with cost minimization games。

So there two parameter is lambmbda and mu。 Okay， these corresponds to the two coefficients and these disenttanglement arguments that we've been looking at。

 So they're going to correspond to five thirds and one third in the disenttanglement argument from last week。

 They're going to correspond to one and one in the disentangle argument I just showed you here。

So land use smooth。 And for the cost minimization case。We need mu less than one。If。

The following property holds basically if you can disentangle。

So if the entangled version of an outcome S star and an outcome S， and again。

 what do I really mean by entangled， I mean， a vision starting with the K vector the strategy profile S。

And then think about all the single component changes you could make。 Okay。

 you could go to its I component and you could change it into some other one S star I。 Okay。

 so starting with the starting point of S， there's K different vectors you can get by changing a single component。

 These are those K other outcomes。 in some sense， or it hamming distance1。

 And we just look at the cost of the deviator or the person who changed and sum them up。

 This is the entangled term that we kept seeing。Again， we don't care about this per se。

 We just want to relate this to what we do care about。

So random new smooth just means you can relate this back to the cost。

A S star with a coefficient of Lambda。Was new。Times the cost of us。Okay。And here。

 you might if you're wondering what this cost operator is， this is just any objective function。

 which is bounded above by the sum of players payoffs。So we' cost。

Of an outcome is an objective function satisfying this inequality。With selfishv routing。

 this helped with quality。 those were our various expressions of the total travel time。Okay， oh。

 I almost forgot the most important thing。Which is this should hold。For all outcomes。SN S star。O。

We may have in mind， as a particular instantiation of the inequality。

 we may be thinking or guided by the case when S is an equilibrium and as star is an optimal solution。

 But that is not what the definition says。 The definition says for every pair of outcomes。

 no matter what they are， you should be able to disentangle。 So， for example。

 in a selfish routing network， any two pairs of traffic patterns。

 Arrbitrarily crazy traffic patterns， the inequality should hold。

 not just under the assumption that one is an equilibrium or the other is an optimal solution。

So that's what it means we' going to be smooth。And then for payoff maximization， there's an analog。

So now the entangle terms are in terms of payoffs。 now， because you're maximizing。

 you want a lower bound。And again， because you're maximizing。

 you're gonna subtract off an error term rather than add an error term。And again。

 this is where should have the property， like in the location games。

Where the objective function you care about can be bounded below。By the summer of Clare payoffs。

And again， this is。不哦哦。S and S star。So， that's。Is the definition of a smooth game。

So given any pair of outcomes as an astor。If you form this entangled version where you take S as a starting point。

 look at the K ways to massage it in one component toward S star。 Look at the cost of that you know。

 massage outcome。 and you sum them thumb up， you can bound those against a linear combination of the two outcome costs S and S star。

 That's what it means。We've seen two examples。 this won't necessarily be obvious to you。

 but you should go back to your notes and verify this。 If you go back to our proof one week ago。

The price of energyarchy and atomic service routing networks for that cost functions is five/2s。

What we actually proved in step 3 in the disentangling。

 we actually proved that every such game is smooth with the parameters，5 third and one third。😊，Yeah。

And the reason that's what we actually proved is that in step 3。

 while we had in mind that S was an equilibrium and as star was an optimal solution。

 we never used that fact in the disenttanglement argument。 That was all just algebra。 Remember。

 we had this sort of y times Z plus one is most this， you know，5 thirds y squared， blah， bla， bla。

 blah。 That was just about numbers。 It wasn't about equilibrium。

 so we proved the disentanglement for all pairs， not just for equilibrium。

 Similarly in the proof I just gave you， it was only in step1。 we used that S was an equilibrium。

 and in the disenttanglement step， that was just algebra。 sub modularity。

 telescoping sums had nothing to do with equilibrium。

 So we actually verified these conditions in both of those examples。Alright， so that's fine。

 So thiss just all Ive all you should be convinced of now is I've given you sort of a common language to talk simultaneously about you know。

 multiple price of anarchqu proofs， you know， which is nice。

 but it's not necessarily clear that it's good for anything。😊，So in the rest of the lecture。

 I want to explain some of the things that it's good for。

I want to tell you about when you actually wind up verifying these smoothness conditions。

 automatic and interesting consequences that those games enjoy。So let me begin by connecting things。

To the main topic of Monday's lecture， which was our hierarchy of equilibriumlibria。

Hereure strategy in a equilibrium， mixed strategy in a equilibrium。Created equilibriumo。And course。

 Cotic Leon。The theorem I'm about to state is about the biggest set。Course correlated equilibrium。

 So let me remind you of the definition。Yeah。Yeah二。Firstt few。In the payoff lambda。That's right。

It's lambda。That's right。 The reason is's just， I mean， it's just because of Max versus men， right。

 So， you know， you'd love to be， you know， So like， imagine if Lando was one。

Which it actually was in the location game example。 Okay， so imagine Lambda was one， and mu was 0。

Okay， now it implies something incredible， which is that equilibrium are fully optimal。Okay。

So in effect， so the mute term lets you say something weaker and says， okay， well。

 we're not gonna claim that the equilibrium is at most one times an optimal solution。

 We're gonna claim that its one times the optimal solution plus or minus an appropriate error term。

Now， if it's something that you want to be small， then the error term is something you'd add that would weaken your statement。

 so that's the reason for the plus mu times cost， if you're trying to lower bound the cost of an equilibrium and you want to have a weaker statement which is actually true。

 then you want to subtract something off。肯定希望。To the same。Not， it's not actually， but again。

 it's not I wouldn't necessarily worry about。I mean， it's just， yeah， I mean。

 it' it's not for interesting reasons。 I mean， you'll see exactly。

The new less than one will become clear in a sec for the Cosization case。So think of these as。

 despite some， you know， minor syntactic differences。

 think of them as basically just being exactly the same thing from inmization max position。

 so when you work it out， this is just the appropriate version for the two cases。O。

So we had this hierarchy of equilibrium concepts。And so maybe just remind you of the motivation。

So again， pure strategy Nationallibia may not exist。I in games that we care about。

 like sal shing with weighted players。Mixna equilibrium always exist。But are hard to compute。Okay。

So that motivated looking at even more permissive equilibrium concepts， correlated equilibrium。

We're easy you can find one polynomial time。 There are distributed learning algorithms that drive joint play to that set。

 Coarse corlatetic Lib or even easier。Okay， in a couple lectures。

 I'll actually show you the very lightweight learning algorithms that drive joint play into this set。

 Okay， that's one of the topics coming up soon。 Allright， But so the point is。

 course cotic Libria being so big and so permissive are a pretty plausible。

 relatively prediction of what might be happening in a game。 Okay。

 a lot of outcomes are course cotic Lib。 So it's just sort of a very。😊。

It's a relatively weak prediction about what's actually happening， okay。So what's the definition？

So a distribution sigma。Over the outcomes of a game。so over the product space， a1 times a2 times ak。

If。So as usual， you think about all potential deviators。You think about all potential deviations。

 S prime。Here AI is the strategy space for player or I。And what you compare is you say， well。

 you know， suppose。I always played as recommended by Sigma。

 So if we envision sort of drawing a outcome at random from Sigma。

So then I's cost is random variable。 depends on the chosen outcome。

 but we can look at as expected cost， but just blaze according to Sigma's draw。

And we compare that to how well I would do if instead it deviated unilaterally and unconditionally。

 Where everybody else continue to follow S。So that would be the expected value。Where。

I switches to SI Prime。This is deterministic。 This is random。

 This is being chosen from the distribution Sigma。 This is a fixed pure strategy deviation。

And if that inequality holds for the expected cost of every player for every deviation by a player。

 then it's called the course correlated equilibrium。And again。

 generalizing all of the previous equilibrium concepts that we saw。And again。

 the point that we concluded with on Monday is that because the price of anarchy takes the worst case over all equilibrium。

As you widen the set of equilibriumria， the good news is that you're more likely to have existence。

 In fact， you always have it。 as soon as you're at mixedstrasticlibria。😊。

You're more likely to be tractable。 And indeed， you're already tractable to correlate。

 But the price of anarchy only gets worse because there's only more equilibrium you're trying to bound。

So the strongest type of price of anarchy arguments abounds with respect to this picture would be for the biggest set for the coarse correlated equilibrium。

And so， it's cool。Is。If a gain is smooth。Then even though in your mind。

 perhaps you merely thought you were proving a bound on the price of an of pure N equilibrium。

When we were talking about routing games， were never talked about randomization。We just sort of。

Proved with our bare hands this 2。5 in this location game。

We didn't even talk about mixed strategy equilibrium。

 We just talked about pure strategy national equilibrium。 We proved the 0。5。 We inadvertently。

 it turns out， played prove that exact same price of anarchy bound for all of these。

By verifying the smoothness condition。So formerly， here's what's true。

I'll just state the cost minimization version， but the other one's analogous。So， in every。

Landom you smooth。Cost minimization game。And again， you should be less than one。The price of anarchy。

Is the most lambda。Over one minus mue。真。So just to help you relate to this formula。

So in selfish routing。We verified the smoothest condition with lambda equals5 third and mu equal one third。

AndSo therefore， land over1 minus mu is 5 point is 5 pounds。

Okay so the way to think about it is not so much lambda over 1 minus me per se。

 The way to think about it is we proved a bound in our mind just for pure equilibriumlibria。

 but because we proved it in a particular way following this canonical recipe。

 that exact same number， whatever it is， we get it for all of the sets， all four of the sets。

 it holds all the way out to Co quality delib。So in this sense。

 it's a type of price of anarchy bound that extends automatically from pure equilibrium all the way out to co correlated equilibrium。

So for payoff maximization。The only thing that changes is mu no longer needs to be a most one。

 and it's。Now going to be a number less than one。Lambda over one plus mu。 And so again。

 for the location games that we just discussed， Lambda was one， mu was one， and that's the one half。

 So again， the point is， we thought we were proving a one half for pure equilibriumria。

 We actually got it for all of these equilibrium。questions about what the。Theorem is sang。

So I'll give you a proof， but frankly proof， once you sort of think it might be true。

 the proof writes itself。As you'll see。So again， in particular。

 this tells us two examples with good price of energyarch bounds。

 even for coarse corelate equilibrium， which again means even say for agents who are distributively trying to play this game using very simple learning strategies。

 even though they may never converge to a Nsh equilibrium。

Because they're going to be in this big CCE set。These bounds of 2。5 or one half still apply。

And these are not the only two examples。 They're the only two I'm actually going to show you in lecture。

 but there's many other examples known at this point。Okay。So proof。And again。

 we can just really just follow our nose here。So what are we trying to argue about。

 We're trying to say that coarse correlated equilibrium are near optimal。

So consider I'll approve the cost minimization version。

So consider an arbitrary lamb use smooth cost minimization game。Consider an arbitrary。

Porse co equilibrium。And what we want is we want an upper bound。

On the cost of this course quality gl。 Now this thing's randomized。 So when I say cost。

 they really mean expected cost。And expected where we just look at the distribution over outcomes that Sigma is doing okay。

So think about， remember like the traffic light， right， where Sigma picked 50。

50 between two outcomes。 so they may have different costs。

 We're just averaging over all the things that Sigma might pick。Allright， so again。

 we can just think about， all right， what do we got going for us， What are our hypotheses。

 and we don't have many。Because now things have gotten pretty abstract。

 kind all we know is that this is a coar correlated equilibrium。So we've got this to work with。

And we know the game is smooth。 So I guess I've erased it。

 but we have the disentanglement inequality to work with as well。So nothing's entangled yet。

 so it seems sensible to start here。So that's about individual player incentives。 Okay。

 so this is about joint costs。 But really， we want to talk about individual player costs。

But remember， we're assuming that the joint cost is bounded above。By the individual player costs。

And again， this is， this helped with the quality for selfish routing。 But in general。

 as long as it's player costs or an upper bound were fine。

So this is starting to look sort of like what we want。

 Okay But the equilibrium condition doesn't apply to the joint cost。

 It applies to an individual cost。 So we'll just use linearity of expectation。

To take the sum out here。And now the CC， C， E condition is looking pretty relevant。Right。

 so this is the expected cost of player I in this course， qualitytic equilibrium。By definition。

 and of course called equilibrium， if you make any unconditional deviation， you only get worse。 Okay。

 And again， which deviation should you try？ Well， again， the optimal solution provides one to try。

So we could think about as a thought experiment， player I is deterministically picking its strategy at star I and the optimal solution。

By the CE condition， its cost would only go up。So I'm really applying this condition once for each player where S star I is playing the role of S prime I in the definition。

So now things are starting to look entangled。So now smooth this is starting to look like maybe it's the appropriate tool。

Now， smoothness， I guess， have erased it。 you let me put it back up there。So Sness says this。

So Sness talks about an entangled version， meaning this sum of player costs and these entangled outcomes。

 So that's not quite what we have here Here。 It's just sort of about a single player and its experience in a particular entangled outcome。

 But again， linear of expectations lets us focus instead。

On the expected value of the entangled term that we want。

So let's just move the sum back inside of the expectation。And now we're in business， right？

This is exactly the entangled term that smoothness allows us to relate back to things that we care about。

 the cost of S and the cost of S star。Now， notice。It's very fortunate that we can disentangle any outcomes。

Any outcome S， not just Nash equilibriumlibria， because if you look inside here。

 what do we know about this outcome S。We know very little。Okay。

So sigma is some distribution over outcomes。 Okay， you're doing this with， you know，3% probability。

 this other outcome with 17% probability， et cea cea， et cetera。

 There's no guarantee that these things are Nash equilibrium。This could be anything。

The only thing we know is an equilibrium condition on average over the outcomes。

We do not know that any individual outcome the're ravaaging over is an equilibrium itself。

So the facts that we've proved this not just for Lib， but for all outcomes。

 S gets used exactly in this part of the proof。S is random， but I don't care what it is。

 It doesn't matter what it is。 I can always relate this back to a linear combination of S and S star。

So by smoothness。Yeah。We get that The expected value of this comm combination。Now， S star。

 this is just the optimal solution of the game。 So this this is not， this is deterministic。

 So there's no randomization of S star。 The game is fixed。 The optimal solution is fixed。

So this is just。Lambda times the optimal cost。 Now， this is what's random。

 this is what's being chosen from Sigma。So we can take the mu out。Times the expected value。Of。

This random outcome。So now where did we start？We started with the expected cost under this course qualitytic equilibrium sigma。

And we've said that that is bounded above by lambda times the optimal cost plus mu。

 where mu is less than one。Times the same thing we started with。Expect a cost at equilibrium。

So now we just saw for the price of energy。We subtract this from both sides。

 it gives us a 1 minus mu on the left hand side and we divide through。And that gives us。

AtThe expected value。Of the coursearse qualitytic equilibrium。Its the most lambda over one minus mu。

The cost。A very authentic solution。So that is why in smooth games。

 you automatically get bounds for co correlated equilibrium。Question。他了。

It can be an arbitrary upper bound。So like in the location game， where a payoff maximization game。

 we observed that the sum of the player payoff was not necessarily equal to the surplus。

 it could be less。So it's whatever you want it to be。 But as long as the inequality holds。

 then the proof is correct。Other questions？So there's a bunch of other things。

 properties that smooth games have automatically。 I won't have time to tell you about many。

 but let me mention one other one。That's simple， which is to an orthogonal set。It looks like that。

Which is approximate。Sure strategy national equilibrium Lib。

So I'll tell you exactly what I mean by that， is it multiple ways to define approximate N equilibrium。

But the upshot is， is that in smooth games， as you relax the equilibrium condition。

The price of anarchy， as you'd expect togrades， so in particular if stuff is arbitrarily weird。

 arbitrarily non equilibrium， there's nothing you can prove about it。

But as you relax the equilibrium condition， the price of anarchy bound degrades gracefully in smooth gains。

So， precisely。Again， I'll just state it for cost minimization， but there's an analog for payoff。

 maximization。So S， and this is now just a deterministic outcome。Although you could， of course。

 have analogs for all the other equilibrium concepts if you prefer。

So S is an epsilon approximate pure str Lib。If for all players I and off for all deviations， well。

 you know， maybe it is a deviation that makes you better off， but not by much。 Okay。

 just by the one plus epsilon factor。That's what it means。So。Look at the cost of equilibrium。

Maybe it can be strictly bigger than something with the deviation， but only by one plus epsilon。

So that's one natural definition of an approximate equilibrium。

And following this exact same sort of derivation。In fact。

 the easier version because there's no randomization in this version。

So if the game is landing you smooth。And S is an epsilon approximate pure in a equilibrium。Then。

 the cost。Of this approximate equilibrium divided by the cost of the optimal solution。Well。

 we're not quite going to get。Our lambda over  one minus mu bound。

 That'll be a little bit too good to be true because we're allowing some violation and equilibrium。

 We expect the price of energyarch to jump up beyond lambda over  one minus mu。

 But we just pick up a one plus epsilon on the lambmbda。And also a one plus epsilon。嗯。On the mu。

And this is meaningful。Assuming。That this denominator is positive。So that's going to be epsilon。

 is it most。1 over mu minus1。Okay。And again， you know， once it occurs to you。

 the definition might be useful proofs like this to sort of write themselves。

 That's what we're going to ask you to do on the problem set that goes out on the exercise set that goes out today。

Since's it for smooth games， have a weekend， see you Monday。

