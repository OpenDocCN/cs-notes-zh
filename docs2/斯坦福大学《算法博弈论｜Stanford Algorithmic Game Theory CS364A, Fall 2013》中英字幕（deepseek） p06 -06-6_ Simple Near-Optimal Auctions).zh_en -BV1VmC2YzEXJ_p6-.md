# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p06 -06-6_ Simple Near-Optimal Auctions).zh_en -BV1VmC2YzEXJ_p6-

。So Monday's lecture was a very important one。 So I want to just start by reiterating the main points and make sure I never lost you you never lost the forest for the。

 for the trees。So， we worked pretty hard。To prove a formula。 But the good news is。

 is the formula is going to be very useful。 The hard work will pay off。

 I'm going to use this over and over again already today，😊。

So what we did is we showed that for every auction， optimal or not didn't matter。

If you look at the payment。The expected revenues so we averaging。

 again over the distributions that were given， which defined the the input distribution。

So just evidently， this would be the expected revenue of an auction。But we show that actually。

 this can also be written。With an expression that doesn't reference the payment rule at all， which。

 again， is kind of shocking， given that the whole thing we're trying to maximize the payments。

 But rather， references only the allocation rule of a mechanism。The virtual surplus。Okay。

So this was the main thing we proved Monday。let me just remind you where。

Phi I refers to the virtual evaluation of a bidder。 It depends on its value。

 It depends on the distribution from which the value is drawn， and the formula is V I minus。

1 minus the distribution function of V over the density。At V。Now。

 I already gave you an application of this， a very important application on Monday。

 which is under an extra assumption on distributions。

 this actually tells us exactly what the optimal option is。 In fact。

 in every single parameter environment， this tells us what we should do， at least in principle。

So the problem definition is to make this as large as possible。

 we've reduced that to making this as large as possible。

And the obvious way to do that is just to you know remember this looks a lot like surplus。

 The only difference instead of values we have these coefficients that are virtual values。 You know。

 And so what do we do in surplus， we just said， well， give us the bids。

 Let's treat them as the valuation。 Let's just pick the outcome with the biggest surplus。

 So we're going try exactly the same thing here。 We get the bids of the values。

 We compute the virtual values。 We're just going pick the allocation that has the largest virtual surplus on this particular input。

So I'm going to call that the virtual surplus maximizing allocation rule。So formally。

X just picks the arg max。 Okay， so it looks it。 It looks over all of the feasible solutions。

 Remember， a single parameterer environment。 This is just which things are feasible。

 like in a single item option。 And most one person gets the good。

 And you just look over all feasible solutions， Which one has the biggest virtual surplus。😊，Okay。

So this is exactly what we studied in surplus maximization。

 except the VI has been replaced by a VI of VI by a virtual valuation。

So if this allocation rule happens to be monotone， then we're done。So then it is optimal。 And again。

 by optimal， this week， I always mean maximizes expected revenue over all DSSIC auction。

 That's what optimal means。So this characterizes the revenue of every auction。

 If just making it as big as possible， separately on each input actually gives us an implementable allocation rule。

 we're done。So that's the first thing we realized。The following fact we only thought through in this special case of a single item auction。

But actually， it's more general， as I'll ask you to prove on the exercise set。

So if every distribution is regular。And we define this Monday。 I'm actually for simplicity。

 going to make the condition a little stronger。 starting today。

 It's going to be that the virtual evaluation function is strictly increasing。 Monday。

 we said non decreasingecreing。 let's say strictly increasing， just to make our lives a。

 a little simpler。Yeah。So as long as and so remember。

 the uniform distribution gave us a strictly increasing function many of the distributions do as well。

 as you'll see on the exercise set， not all function， not all distributions give us regular regular。

 but many are in that case， then this totally works out this design paradigm okay。

So then it is monot。And here by it， I mean that virtual surplus maximizing allocation rule。

So when we have regular distributions。 and again， this is what we proved by the end of last lecture。

 any single parameter environment， any set of regular distributions。

 we actually know what the optimal action is。 We totally solved it。 It's this。Okay。

This is how you choose the allocation。 You always choose it to maximize virtual surplus。

 It's monotone。 Myerson's Lemma gives us the suitable payments， okay。

So we solve the problem just into the regularity condition， full generality。Now。

 we also spent a little bit of time interpreting this on Monday。So single item options where， again。

 it's very easy to understand the feasible set and most one bidder gets the good。

 You just have to choose who， whom。So if you have a single item option and also you have IID。

Regular bidters。We observed that， in fact， this rule is a very simple one。

 Okay to maximize virtual surplus， you give it to the bidder with the highest virtual value。

 If there' is someone with a positive virtual value and by virtue of it being IId。

 everyone has the same virtual valuation function， virtue of being regular。

 it's an increasing function。 So the highest， the highest virtual value bidder is also the highest value bidder。

 I either the one chosen by the victory a。 So if you actually think through what is this rule look like in this special case。

 It's an a that we know and love， namely the victory a with the suitable reserve price。😊。

So in other words， under these assumptions， you can actually implement the revenue maximizing auction。

 despite the richness of the things you could try， eBay is already going to do it for you as long as you choose the opening bid。

Appropriate okay。So。This is fantastic。This is just a totally killer application of auction theory。

 So we sort of did this very rigorously informally， but what popped out at the end。

 we got a very crisp， very conceptually meaningful and downright practical auction。

 that's what's being advocated by the theory to use to maximize the seller's revenue in this situation。

 That's great。 That's really exactly， you know， that's the best case scenario。 Okay。

 when something you can really use just pops out of the theory。 without without any further work。

 that's what we got。So。The plot thickens， however。When we make the environment a little bit more complicated。

And so this is the segue into today's topic。So if bidders。

 so I'll keep all the assumptions exactly the same。

 except I will not assume that the bidders are I I D， Different bidders。

 I will have different F subs， but all the F subs are regular， and it's still a single item option。

So， if bidders。Not IID。Turns out things get weird。So what do I mean， for example？Right， so， you know。

 this thing over here， Vuction with a suitable reserve price。

 You can explain this to someone who's never had any auction theory。 Okay。

 you just say it's ebay right， with some opening bid。

I don't know how to explain the payments in this auction without referencing virtual valuations。

 which， of course， would have no meaning to someone who didn't study auction theory。 Okay。

 so the payments， even though they're just these critical bid payments。

 they're still pretty hard to interpret if you don't。

 if you haven't satAT in on this week's lectures。You also get weird and sort of provocative things like the winner in this optimal auction need not be the highest bidder。

And that's also something I'll ask you to work through on the exercise。

 It happens even in very simple examples。 So the optimal a advocated here really has these properties that we never see in the world。

 okay。And in some ways， there's no way out right so if you 100% believe in the model you set up。

 you 100% believe in your distributions， your FIs， and you want 100% of the optimal revenue。

 this is the only way to do it。 It was only one allocation rule it's going to accomplish it and for the allocation rule。

 there's only one payment rule it's going to make it incentive compatible so you're stuck with this。

So， but this is unsatisfying， right， So this， this theory is a little bit harder to interpret or reply that it gives us these sort of strange options that we don't see in the world。

And so。The theme for today's lecture。As well， can we get much more plausibly implementable auctions。

 And， of course， we can't， if we want 100% of the optimal revenue。

 But giving up a small amount of revenue。 Okay， so get almost optimal with a much simpler and much more practical option。

So that's the motivating question for today。Are they simpler？More practical。More robust。

Opts that we can prove are near optimal。Okay。So for context。

 let me point out that this is the second time。We've turned to approximation to get us out of a bind。

Does anyone remember the first one？So last week。So again。Npsack， yeah。

 so what was what did we not like about sort of the optimal option in that case？Right。

 it was computational intractability。 right We needed to solve an MP complete problem to implement the auction。

 So to recover a polynomial time， we relaxed exact optimality。 And something similar， though。

 a little more vague is going on here。😊，We saw for the optimal auction， and it's out there。

 and we know what it is。 And again， we sort of don't feel comfortable saying this is something we're going to implement。

 It's not because we think it's going to take an exponential amount of time。

 It's just because there's sort of no。You know， precursors out there in the world of how to sort of explain this option to people and get them to use it。

 Okay so， you know， I'm going to leave words like simple， practical and robust。

 kind of safely undefined in this lecture。 frankly。

 there's a lot of work last five years on exactly this theme。 And it's basically an open question。

 an important open question to figure out the right way to define a simplicity of as so that we kind of have this entire theory on solid ground。

 But what we do have over the past five years are a number of concrete examples。

 situations where there's an auction which is evidently simpler than the optimal one and which is not too far away in terms of revenue。

 And so those are some of the things we'll give you a taste for today。Question。这个看。Sping。

So were like。Yeah， this whole weekss about revenue maximization。

This whole week is about revenue maximization。Well， I mean， if。

 if're going talk about optimizing something， you kind of got to pick an objective。

 There's interesting work on trade offs between the two， but I'm just going to treat each， in turn。

Other questions。Okay。Allright， so another point I want to make is that so the basic theory we covered on Monday。

 it's very know essential， crucial stuff。 It was developed mostly by Roger Myerson。

 who's an economist。 He wrote the corresponding paper in 1981。 He won a Nobel Prize。

 a few years ago for that paper， as well as other contributions。 We're gonna be talking about today。

 these approximation guarantees for simpler， more practical auctions。 This is much more recent。

 so this has been done almost entirely in the past five years or so。

 It's been done mostly in the computer science， literature and community。 so in the econ community。

 They've studied approximation very little。 They have not really thought about what it can buy you。

 So this is much more recent stuff I'll talk about today。All right。

So next is what may seem like a digression。 I hope a fun digression。But it will be relevant。

 Itll give us our first example of a simple， near optimal auction。

I want to tell you about something called a profit inequality。And given the context。

 maybe you think I'm using the wrong spelling for profit。 Maybe you're expecting PRO FI T。

 But it turns out this inequality， you know， was not developed for option theory per se。

 So that's the， that's the profit。 And I'll explain why。And， you know， this is。

 this is a cool result。 And this is one of those results where like pretty much anyone who likes math is gonna like this result。

 Okay， so it's just， you know， something you can。😊。

You can sort of whip out at your next nerdy cocktail party to make some small talk。

Don't pretend like you don't go to any of those。So here's the， here's the setup。

 So there's one person playing a game。And the game iterates through end stages。Okay。And stage I。

You will be offered a prize with some value。I'm going to use pi I。For the value of the prize。

And as the person playing this game。You know， GI in advance。It you know G1 through GN。

But you only learn pi I when and if you get to the I stage。Okay。

I should also mention that the distributions are independent。

And the way the game works is at each stage， you have a decision to make。 Okay。

 So there's some prize， you know， worth $107 or whatever。 Maybe you're just stage 7 out of 15。

And either you pick the prize， get you walk， you walk home with $ hundred70 gay ends。

 or you discard it and continue。It's up to you。You know what G8 through G15 R， you don't of course。

 know what the pi8 through pi 15 are， if you did， it would be trivial。对。

P is a number of Gs of distribution。Is the game clear？And is it clear that it's not obvious。

How to play it。So there's an obvious tradeoff。 Do you stop relatively early。

 possibly missing out on some large prize later on。

 or are you very patient with the possibility that you'll be stuck accepting some very lousy prize in the an stage。

Yes。Ps in each。Yep。And stage I offered price pie eye。So here here's the very cool fact。Okay。

So there exists a strategy， in fact， a strategy with a very special form。

The guarantee is going to be competitive with what a profit could obtain。 What do I mean by profit。

 I mean， someone who has full clearair voyance。And knows in advance what pi1 through pi n is。

AProfi's just going to wait till the biggest prize shows up and take it in that stage。

So the payoff enjoyed by a profit。Will be the expected value。Over the realizations of the pies。

Of the largest prize。This is what a prophet can obtain in this game。Now， obviously。

 we're not gonna get this much。 Okay， that's ridiculous。 As soon as you had two prizes， right。

 you get the first one。 Its like 100 bucks。 as long as there's some chance that the second one might be above 100 and might be below 100。

 after the fact you might regret whatever your decision is in stage 1。Okay。

 so there's no way you'll do as well as a profit。Our priority， I think most people's intuition。

 including yours， truly， I that there's no reason you should get close to this at all ever。 not。

 It's not there's any strategy smart enough that can compete with someone with so much more information than you have。

Right。Nonetheless， there's a strategy which gets half of what the profit gets guaranteed。

No matter what the GIs are。Okay。So， in fact。It's not even a complicated strategy。

It's what's called a threshold strategy。A threshold strategy with threshold T。Works as follows。

At the very beginning of the game， I look at G1 through G， N。And I picked some threshold teeth， okay。

And then in some stage， I see if I get a prize with value， at least T， I take it。And if not， I don't。

And I never change。 doesnn't matter what， what pies I see。

 I don't even in the final stage when there's no future stoop to accepting a prize less than tea。

So obviously， these threshold strategies are not optimal。That's not what I'm claiming。

 I'm not claiming they author I'm just claiming that they do almost as well as a profit。So， even。

A threshold。Strategy works。Okay， so that's an addendum to the theorem。Or again， what this means is。

You accept pi I， if and only if pi I。At least tea。So now let me show you the proof。

So notation I'll use， whenever I have a number， a real number。

 I'll write that plus if I just want to take the max of that number in 0。

So what I'm going to do is I'm going to do a generic analysis for how well a threshold strategy does。

 It will be parameterized by the threshold T。 We will choose the right threshold T at the very end of the proof once we understand the trade offs between bigger and larger teams。

I mean， qualitatively， I hope the trade off is clear。 the bigger the threshold。

 the more money you'll make if you， if you're so lucky as to see a prize as at least T。

 But the greater the chance you won't get any prize at all。 Okay the lower the threshold。

 the more likely you'll get a prize， But who knows if it'll be any good。

So one other quick piece of notation。Q of T。 So again forgiven threshold T。

 Q of T is the probability that you wind up empty handed。

That every single prize is less than your threshold。And that， of course， is going down。

As your threshold， as your bar is going up。Questions。So， the plan。So okay。

 so the theorem is about comparing two things， It's about comparing the expected prize， if any。

 that you get from this T threshold strategy。To the expected profit or the expected value that the profit obtains。

Turns out those two expected values seem hard to compare directly。

So we're going to do something which is very common in approximation guarantee proofs like this one。

Which is we're going to replace one or more quantities that are hard to work with directly by suitable upper or lower bounds that are easier to work with or easier to understand。

So what're gonna show you first is a lower bound on the expected value obtained by this threshold strategy。

So it'll be something that's even worse than our threshold strategy。

And I'll show you an upper bound on how well the profit does。 Itll be even better than the profit。

 I'm actually going to show that those two things which are even farther apart。

 even those are within a factor two of each other。 Okay。

 and these lower and upper bounds will be easier to compare directly。

Then the two quantities we started with。All right。So I got to do 2。

 I got to give you a lower bound and upper bound。 They both， they both have a couple inequalities。

 but they're not， they're not too hard。So let's start by lower bounding how well a threshold strategy does。

 okay。Yeah。 and again， we want lower bounds for this one。Well。

 there's some probability our payoff is zero。😡，So just， just to remind everybody， what's that。

 what's that probability。Q of T， That's how I defined it。 Like Q of T， you get nothing。

So1 minus Q of T， you get something。 when you get something， its value is at least。Ti。

So totally valid and actually a very good first cut lower bound。Is this。

The probability you get a prize times the minimum value that prize could be。

So it turns out to make this proof work， we need a somewhat sharper， lower bound。 Again， this is。

 this is correct。But we want to make this right hand side a little bigger。Okay。So。You know。

 so why is this not not an optimal lower bound？ Well， you know。

 what if our T is 100 and then one prize shows up， It's above T。 And it actually is 120。Okay。

 then the value， the， the value we get is 120。 It's not just 100。 We don't just get the threshold。

 We get whatever the actual value is， which might be well more than the threshold。

So that sounds like a good idea。 We want to actually put here kind of like the pi I for the prize above T that we get。

But here's what's kind of annoying。 right， So suppose there are actually two prizes above T。

 like a threshold to 100。 There's one prize。 that's 120。 there's another prize。 that's 130。

What can we say about the value that we get？First all。Right， okay。

 so whichever of those happen to come first in the ordering， It might be 1，20 It might be 1，30。

 That's the one we're going to pick。So it's not like just because there was a 130。

 it's not like we can really say we got 130， might have been blocked by something that was 120 that was earlier。

So it turns out we can get away with just totally punting on this complication。 right。

 So here's what we're going to do。 And this will'll make it clear to lower bound。

If theyre more than one prize bigger than T shows up。I'll just say， you know。

 I'm only going to credit myself T。Okay， clearly， I get more。 I get one of these V。

 that's bigger than T。 but I'm only going to give myself tea， which surely I get。

 because whatever prize I pick it at least tea。On the other hand。

 if exactly one prize gets instantiated to a number bigger than T。

 then I'll give myself the extra credit of V I minus T。Okay。And that'll be the lower bound。

So let's just write that out。嗯。So whenever， remember， this says at least one prize is at least T。

 So I always get T in that case。Plus。So I'm gonna sum over the items or over the stages。

 And in a given iteration， I， I'm say， well， you know。

 sometimes item I Pri I will be bigger than T and everything else will be less than T。

 And in that case， I'll give myself the extra credit of V I minus T。Okay， so some。

Over the candidates for being the sole prize above tea。And so what is that going to be。Yeah， good。

 good。So here's the extra credit。Pi I minus t。And the case I'm interested in。

Is where Pri I exceeds the threshold and everything else does not。Okay。So this is the。

 this is the bonus I'm going to get。Now， the formula is not quite right because I have to multiply this times the probability of this actually happening。

 Maybe this never happens， right， But so this gets multiplied。

Times the probability of this stuff of what I conditioned on。So I'm gonna to write this。

 I'm gonna actually factor this。 Remember， the distributions are independent。

 So this event and this event are independent。So let me just write probability of pis at least t times the probability。

That Pi J is at most TV for all J。Not equal equal the eye。And again。

 what this means is we just give ourselves the extra credit when there's exactly one prize that's at least T。

Sos let me simplify this a little bit。So I already mentioned。

 we already used the fact that the G Is are independent when I wrote these probabilities this way。

Let me use it again。Because the G I are independent， the fact that。

These other prizes are less than T has no bearing on the expected value of pi I minus T。Okay。

So by independence， that conditioning is irrelevant。

And so now let me just clean this up instead of actually just looking at this expectation condition on the event that's not negative。

 I'm just gonna to write this with my plus notation instead， okay。Just for simplicity。

So what do we have？One minus q of t times t plus sum over the stages。

Times the expected extra credit we get。In stage I。Times。What's left。

 the probability that everything else。Is less than the threshold。Okay。

So I did was combine this and this into the expected value of the non negative version of V I minus ST。

Now， what will be really cool is， right， we have this1 minus Q of T here。 That's some probability。

 We have some probability here。 Do you see any relation between this probability and Q of T just to make this a little simpler。

😊，Say it again。是这。Something I'm looking for something simpler。 I don't think so。So what is Q of T。

 Q of T is probably that nothing is above the threshold。What's this。

This is a probability that everything other than I is below the threshold。

So this is a less stringent condition。So this is a higher probability。

So we can lower bound this by Q of T。Okay， the smaller event that everything is below the threshold。

 including on。Okay。So that ends step 1。We can lower bound how well we do。

By one minus the probability that we get nothing times t or threshold plus。It's sum of extra credit。

P again。Oh， it should be pi， sorry。I've been too immersed in auction theory these last couple of weeks。

Yeah。Questions。So that's our lower bound on our value。

So now we want an upper bound on the value of the profit。

Which hopefully we can compare very easily to this lower bound。

 That was the whole point of this exercise。Yeah probability。こか。How did I get from what to what？

So the， the prizes are independent。 right， So what is that expectation about。

 That expectation is about the Ith Prize。So telling you anything about the other prizes has no bearing on the value of that I prize。

So I can just cross out the conditioning。Other questions。Alright， so upper bound on the profit。

This is easier。And so we just kind of want to like， copy this format。Somehow。喂。

To make them easy to compare。So we've got this tea here。

So what are we trying up bound remember trying up bound the profit， which is just the。

Value of the biggest prize。And， you know， because I somehow， you know， want T to get involved。

 There's no T here。 Not， This is the profit。 It could care less about a threshold。

 So in the analysis， I have to get to the threshold involved so I can make a comparison。

So let's just sort of add and subtract it to get the ball rolling。So remember。

 we're going for upper bounds now。Right， so this could be positive or negative。

 So it only gets bigger if I take the， if I make this non negative。

And'll see I want to do that in a second。Shoing。Okay。So this is， this is just a max。 Now， again。

 we're trying to have something we can easily compare up here。And， you know。

 so this involves non negative versions of the， this involves kind of the extra credit values。

 the pi I minus the T's。 But the biggest one。 This involves the sum。But fortunately， you know。

 non negative numbers， the sum is going be at least the， the biggest。

So is there some value of Q of T that would be kind of super convenient for relating these two quantities？

By these two quantities， I mean。That one and this one。嗯。One half。Right， a Q of T was a half。Then。

 up here。That would be a hell。Yeah。That would be a half。And we be done。

Tll me that's even worse than our threshold strategy's value is at least 50% of something that's even better than the profit。

So， setting tea。So the Q of T。 And let's notice this is actually conceptually kind of really。

 really neat。 It kind of says， like， what should you do in this kind of game。Okay， it says， well。

 you know。You want to be aggressive enough。 So there's at least some chance you'll get nothing。

 because otherwise you're settling for too little too often。 Okay， And so what's the rule of thumb。

 It says， well， you know， make it 50，50， whether you get somebody or you don't get somebody。

 and you're going to do two approximation of a profit。Okay。So that's it。

So that's a profit inequality。Okay。Any questions about that？Other than。

 why did I just teach you this。Yeah。Take again。In which。And2。Yeah， that's a good point。

 that's a good point。Yeah， this is always at least tea。 No， no， that's fine。 actually。

 I just added ined tea。This is where the inequality comes in。Whathy are we choosing a pump？

Because then the expression on top is exactly half the expression on bottom。

We're choosing T so the Q of Ts a half。So we want the probability of getting a prize to be a half。

5050 get a prize。I mean， T in itself has no meaning because we don't know the scale of the prize。

 They could be in dollars or billions of dollars。 We have no clue。So。Yeah。Excellent question。 Yeah。

 so， so does there exist such a T。 So you know， with continuous distributions。

 you're be you're gonna be okay。 if you want to this does extend to discrete distributions。

 I I'm sort of debating whether to put that in exercise set 3 or not。

 but basically you know a variation on this proof extends it， even if there is no such T。

 There is still always， no matter where the distributions are threshold strategy that gets you a factor two。

Yeah。管理是什。There， in fact， cannot be better solutions than one half。 So， in fact， this bound is tight。

Good questions。Other questions。Alright， then let's see what we can。

Let's understand the implications for the design of simple， almost optimal options。And in particular。

 what I want to focus on is exactly the simple setting where things already got weird。

So I want to focus on single item options。Where the bidders are drawn from regular distributions。

 but not necessarily the same regular distribution。I should say， you know， this。

 this is just a representative result scratching the surface of a lot that's been going on in the past five years。

If you want to know more，ve been， I'm using this book draft of Jason Heartlines for this part of the course。

 and Chapter 4 of his book is all about these guarantees for simple near optimal auction。Okay。

 application。So single item auction。Yeah。Regular， not necessarily identical distributions F1 through FN。

Here's the idea。Okay。I'm gonna connect this to the profit inequality， kind of， sort of immediately。

Okay。Let's regard。The virtual valuation of a bidder。

Or rather the maximum of that and zero as a prize。OkayP I。You know， and from F sub I。

 we get some induced distribution G sub I over these pi's over these virtual values of the bidder。

Sure。The Fs， we're assuming are independent， as always， this week。

 So the relevant G Is are independent。 So the profit inequality will apply。

 It's not clear yet what it's going to mean， but we can invoke it and see what what we get。Now。

 here's where the connection starts to become more clear。嗯。Let's think about the optimal revenue。

 achievable。In this setting and the single item a。Okay。Okay。Well， as we know。

 it's exactly the same as the optimal， the maximum possible expected virtual surplus。嗯。

So let me write X star to denote the virtual surplus maximizing allocation rule。承认。

And in a single item auction， what is this？Well， this is just either the highest virtual value。

Or if everything's negative， it's going to be 0。That is in a single at auction for the optimal auction。

The revenue， or rather the you， equivalently virtual surplus of that optimal auction。We can write。

As the expected value。Of the maximum。Virtual value。Or zero， if they're all negative。Okay。

So if we regard these things as prizes。This， in fact。

 is exactly what we were competing with in the profit inequality application。

So we can regard the revenue of the optimal auction for the single item auction as the expected prize value of a profit。

So let me now propose a simple a， actually， really a family of simple as。

 And I'll give you a particularly attractive instantiation in a little bit。So again。

 so if we did the full blown optimal virtual surplus maximizer， we could do it in principle。

 It's sort of a crazy mechanism， but we could do it。 This is what we get。Suppose， instead。

Guided by the profit inequality。The first thing the a does is it looks at the distributions。

 and it chooses a threshold T。So that。嗯。ち。As we said before。

 so that the probability that one of these prizes is at least t is exactly a half。

So that's the first thing the auction does。Then what does it do， it takes it gets into bids。Okay。

 looks at the bitters。Compututes the virtual values。Anybody who's below T？Its thrown out。

K just like in a reserve price。And if there， if there's no one left， nobody wins。

 If there's one person left， obviously， they get the good。

 There's only one person virtual value above T。If there's more than one person with a virtual value above this choice of tea。

 it awards the good arbitrarily。For now， let's say arbitrarily。 I don't care how。 randomly。

 lexxiographically， it's not going to matter for the analysis。

There's something I forgot to tell you about profit inequality analysis。

Which is relevant for this arbitrary tie breaking。Okay。

 so just the claim is that any auction of this form。

Gets within a factor two of the best possible expected revenue in a first price auction。Sorry。

And the。Optimum action。Okay， so any simple optionuction like this is within a factor two of the full blown optimal auction。

 That's where we're going。To forge that link， I have to explain something that handles these tie breaking rules。

So observation。About the profit inequality。Alright。

 so I'm going to ask you to page back in what we're talking about with the property inequality。

So remember there are these prizes and there's this threshold。

In when we're talking about our threshold strategy。Suppose that。

Multiple prizes turn out to be above the threshold。So as was， you know。

 acutely observed from the audience， what actually happens with the threshold strategies。

 whichever one of those winds up being first in the ordering。

 that's the prize you're gonna to go home with。 because you pick the first prize above the threshold。

But I claim that our factor2 guarantee applies to an even worse version of that threshold strategy。

 where instead of just going home with the first prize above the threshold。

 you actually pathologically go home with the worst of all of the prizes that exceeds the threshold when there are many。

That's the claim。Yeah。So I erased the reason why this is true， unfortunately。

The reason is because of the way we lower bounded the revenue achieved by the threshold strategy。

 Okay， so what we we had these terms。 what did the terms mean， Well， we said， well。

 there's some probability we get 0。 that was Q of T。And then there's the rest。

 This is probably one minus Q of T。Okay，And what was the extra credit we got， We said， well。

 for each item， there's some chance that that's the sole unique item above the threshold in that case。

 And in only that case， we get the extra credit of V I minus T。In， in our lower bound。

 whenever more than one prize was above the threshold， we just punted。 We said， you know， for。

 for the accounting， we'll just call it T among friends。And even with that accounting。

 we proved our factor， too。So that's why even with bad tie breaking。 So even if you somehow you know。

 change the rules of the game for threshold strategies that you always go home with the least valuable of everything that exceeds the threshold。

 you still are within a factor or two of the profit。Okay。

 so that's sort of a bonus observation implied not by this theorem statement。

 the profit and equality， but by the way we prove that theorem。Question。Respec your feeling。

It's guaranteed。什么。It's about expected value， but you have to take the expected value for the profit itself。

 I mean， the profit's value is random as well。So， it's about expected values。嗯。Good。

So this is a sharper version of the profit inequality and a stronger guarantee。 Now。

 let's go back to this auction。 Okay， so the proposed auction is compute threshold。

 as suggested by the profit inequality， so that the probability that a virtual value of anybody is at least is exactly a half。

Delete all of the bidders whose virtual values is below that threshold T。 If there's none left。

 nobody gets the good。 If there's one left， they get it， If there's more than one left。

 an arbitrary one gets it。 I don't care。So now， applying the profit inequality to any auction of this form。

Right， so what can we say about the virtual surplus of any auction of this form。Okay。Well。

 the virtual surplus of this auction， when it awards the good to somebody。

 it gets a virtual the virtual surplus is the virtual value of that one Bider P I of V I。

 there's exactly one V of V I above the threshold。If there's multiple people above the threshold。

We don't know。 We get one of those V I V Is。 It's undefined which one。

 but all of them are at least T by definition。Okay。

 so the virtual surplus of this simple auction is exactly that lower bound that we had in the proof of the profit inality。

 which we establish is at least half of what the profit could obtain。 And in this context。

 what the profit could obtain is exactly the maximum possible expected revenue。So that's the profit。

What do we get， We get V I V I， if there's exactly one potential winner。

 and we get T if there's more than one potential winner， And we know that that's within a factor。

 too。So the expected virtual surplus。Of the simple， excuse me。OfThe simple option。

It at least one half。That of box。And using for theumpeenth time。

 the virtual surplus and expectation is the same as payment and expectation。

 This gives us a factor to two guarantee on the revenue。Of any auction in this class。

So just to help you interpret this a little bit better。

 let me actually give you a specific auction in this class， which is very easy to describe。

 which in particular。Makes relatively minimal reference to virtual values。

So here's a specific implementation。So what do you do first， you set reserve prices， right。

 We've seen those before， even in the I I D case， the optimal optionuction used a reserve price。

 So we're used to that。Bitders have different distributions， So perhaps unsurprisingly。

 we're going to see different reserve prices。 Okay， we'll talk about that in a second。

Over in the profit inequality world， we used a single threshold in to decide who。

 who was in and who was out。Okay， so there was a single threshold TD。

 but that was about virtual values。 Okay， so everybody has the same kind of reserve price in the virtual value space。

 But those map back to potentially different reserve prices in value space， specifically。

In a specific implementation， we set for each bitter eye。Its own personalized reserve price， R I。

Defined as the inverse virtual value。Of this threshold。This is saying。

 this is just saying the same thing we said before。

 reject bitter eye If its virtual value falls below T。 That's exactly the same thing。

And then if there's lots of winners and then you just do a V reaction on top。 Okay。

 you just give it to the highest bidder of everybody who clears their reserve。

 So you have a filtering step。 And then you're on a V。 And that's it。

So this auction is now looking reasonably simple。 It's getting closer to what we see in practice。

 closer to something you can imagine implementing。 It is one specific member of this class。

 the whole class for that enjoys this factor2 guarantee for optimal。So this is a canonical。

 simple versus optimal statement。 you're not optimal。

 but you're close and you're made big progress on plausibility。In fact。

 I really say there's kind of only one obstacle to being a super practical auction。

And is there anything bothering anyone about this， about this auction that I proposed。😔，In the back。

Excellent， so the reserve price is different for different bidders。Now。

 you do actually see a few as out there where there are reserve prices specific to bidders。

 They're not unheard of。 even in sponsored search， generally advertisers who are deemed higher quality will have lower reserve prices and sponsored search engines will use often more aggressive reserve prices for lower quality bidders。

 So you do see it a bit。 But you know， if you think about ebay。

 even if you know asymmetries amongst the bidders in your auction。

 You just get to set one opening bit。 there's no way in the option format to exploit that asymmetry in your knowledge about it。

So let me get an open question。It's actually not known in exactly this setting， single item auction。

 regular distributions that are not necessarily identical。

 How close you can get to the optimal revenue if I force you to use eBt。

 if I force you to use a second price auction with a single common reserve price。

 It's an open question。I do know some bounds on the answer。So in a paper with Jason Hartline。

 we proved the answer somewhere between 2 and 4。 We don't know where。

So that's a paper from the EC conference 2009。So that's what I have to say about guarantees for simple mechanisms in this sense。

Again， chapterpter 4 of Heartland's book has。Tons of stuff on this topic。

Let me levy another critique。Against this auction。 And actually。

 even the killer application we reviewed at the beginning of the lecture。Okay。

 victoryy auction with a suitable reserve price if for the I I D Se it。

In all of these situations so far， what we've assumed is that these distributions F1 through FN are known to the seller in advance。

 Okay， Or if you like， we're in effect， assuming that it's an auction environment where you have excellent data about what's happened in the past。

 Angel willing to make the assumption that what happens next is going to be similar to the past。

 to be clear， that's a reasonable assumption in many contexts。

 especially with the amounts of data that people have on lots of things now。 But there's other cases。

 socalled thin markets where you don't necessarily have good data or good prediction about what people's value for what you're selling is。

So what I want to ask next is， suppose we didn't know these distributions at all in advance。

 Is there anything nontrivi we can do。So you might be worried that we're back in sort of the。

 the challenge model that we started revenue maximization with， where we knew nothing about bidders。

 And it wasn't clear what price you could set。 And that was the whole reason we adopted distributions。

 So actually， I'm going make a a more fine grain relaxation。

 We're still going to assume that there are distributions。

 We're still going to do average case analysis with respect to F1 through F N。

 we just insist that when you design your auction。It cannot reference any distributions F1 through F N。

 The auction format should be independent of distributional assumptions。

 But when we talk about the performance of an auction， it will be。

 as we've been doing all week with respect to the distribution over valuations。

 So the question then will be， can we have an auction。Which， in effect。

 doesn't know the distributions but whose performance is almost as good as if we did。So。Such options。

 And I'll give you an example， next。But the buzzword here is prior independent auctions。

So prior is just what refers to as these distributions F1 through FN。

 prior independent auction just means that your auction cannot reference any distributions。

 should be well defined， independent of what any distributions are。 And hopefully。

 you can analyze it and improve performance guarantees as well。 So this again， this has been。

 I'm only gonna say you sort of one precursor result in the field。 But again。

 this has been kind of a very hot topic the last three years or so。

 And I'm quite proud of my previous PhD students， Pina and Chi Chi Yan。

 who have been sort of the main pioneers in this area。😊，All right。

But I don't want to tell you about a result from the last three years。Although if you're interested。

 Chapter 5 of Heartline's book has plenty of stuff on it。Rather。

 I'm going to tell you about an older theorem from 96。

It was proved by a couple of economists actually。Including Jeremy Bulow。

 who's here in the business school。But I think it's a very It feels like a very computer science theorem to me。

It's one of those ones where， you know， you look at it。 you're like， man。Wish I could approve that。

It's a cool result。So。So a theorem。Labulo and Climpper。

So I'm again going to state it for a single a auction， although you can generalize it。

And now we're going to go back to assuming that the bidders are IID。Okay。And as usual。

 we'll assume that their valuations were drawn from a regular distribution。

And so what the reload Cl theorem compares。Is the expected revenue。Of the victoryy auction。

 so just the usual second price auction we talked about on lecture 2。

And it compares that to the expected revenue of opt。O。And this is a simple， simple enough setting。

 We know what opt is， right， So what is opt under these under these assumptions。

So this is the simple case， right， the I D case。So that's just the second price auction with a single reserve。

So this is the victoryy a in effect with a reserve of zero。This is just victory a。

With the suitable reserve。Which is the inverse virtual value of0。So that's what the theorem is about。

 Its comparing those two quantities， right。So which one of those quantities is obviously bigger than the other。

I mean， the right side is bigger， right， On the website， we have an auction。On the right side。

 we have the best option。But let me tell you which way the inequality goes in the Bueau K theorem。

Go that way。So what's the catch。Here's the catch。On the right side。We have N bidders。

And is any integer at least one。On the left side， we have n plus 1 bidders。On both sides。

 we have the same distribution capital F。 On both sides， we're taking IID draws。 On the left side。

 we're using a suboptimal a with one extra draw， and we do at least as well。Super cool。

So the usual interpretation。Of this result is。You know。

 you can obsess over your auction format over the distributions if you want。

 But maybe what's really important for making money is making sure it's competitive。

 They bring extra people to your auction。 That's probably more important than getting the details of the auction format。

 just so。So， you know， this conclusion depends a little bit on the application。

 But certainly when you have a scarce situation， like a single item a。

 I think this is pretty good advice。どと。Of course， there's always the case where you are unable to scrounge up more competition。

 and then， of course， the optimal option becomes very important again。

But this is still a good thing to know。Okay。So let me tie this。 Sos a statement of the theorem clear。

We'll prove it a sec。It's not that hard。So just to tie this back in with。The critique。Right。

So remember you saying like， well， you know， what about thin markets where you don't have good statistics about the bid valuations or maybe youre sort of have something that's volatile。

 The valuations are changing rapidly over time。 What if you're not comfortable tailoring your auction to a distributional assumption。

 What can you do， Are there good prior independent auction。So the left hand side。

Does the left hand side depend on any distributions。

This is the second price of auction with no reserve， right。It's well defined， no matter what。

 It revenue will vary as you vary the distribution。

 But the specification of the auction does not reference a distribution。

How about the right hand side， Does that depend on the assumed distribution F。It does。

 because it uses a reserve price。 The reserve price depends on is this inverse virtual value of 0。

 and the virtual value is a function of the distribution F。O。So if you think about it， really。

 there's an infinite version。 There's an infinite number of instantiations of this theorem as you vary the distribution F。

The left hand side is always the same option。They're a protagonist。And as we vary F。

 it's competing with different options。 right Every time we change F is's a different optimal option that it has to compete with。

 And somehow， this is saying that the victory a is simultaneously competitive with all of these optimal options across all F simultaneously。

 again， under the assumption that you award it one extra bidder。😊，So this is a prior independent a。

 It's as good in this particular sense as if we knew the distributions upfront。

 So that's the flavor of research in prior independent auction design。Allright。

 so let's do the proof。So just as in the proof of the profit inequality。

Where we had two things we wanted to compare It was hard to compare them directly。

 and we define intermediaries that were easier to compare。 We'll do the same thing here。

 except instead of the inter intermediaries being mathematical expressions， it will be a third a。

 not one of the ones we care about per se， but one that's useful for bridging the gap between the two。

So just for the purposes of the analysis。Define an auction。A。With n plus 1 bidders。As follows。

So first。Again， this is all just a thought experiment。So we fixed N。 We fixed the distribution F。

There's some optimal option。With respect to F。So in the proof。

 we envision now with n plus1 bidders on the first n bidders， we're just going simulate opt on them。

Okay。Which really just means we run a victoryy auction with a suitable reserve with just the first n bidders。

 We've left a Bider n plus one a side in this fictitious auction A。Now。

 you're on a revenue maximizing single item oxygen。 You might sell the good you might not。

So we don't， and this auction A。Then as a backup， we give it to the last bidder for free。Okay。

It's not clear why I'm doing this yet。 Okay I just want to make sure you understand the definition。

So， auction A。Simulates opt。On bidders one at to end。

Meaning it picks the highest virtual value bidder amongst the first and if there is one that's positive。

 If none of them are positive， there's no sale。Give item to bitter。N plus one for free。

Why did I define auctionary。Well， it has two properties that allow me to bridge the gap between the two sides of the theorem。

So first note that just by definition， this auction's revenue。

With its n plus1 bidders is exactly the same as the expected revenue of the optimal auction for n bidders because it literally just simulated it on a subset of the n bidders。

Okay，So by definition， ofve equalized revenues。So， A is expected revenue。With n plus1 bidders。

Same as O。Were opt is with n bidderters okay？Also。Something I obviously enforced。Is it a？

Always allocates。Be。No argument there， I trust。So we're almost done。

This judicious choice of an intermediary a。Makes comparing the optimal and di options。

A very slick affair。So here's the last thing。That we're going prove， which is also sufficient。

To finish the proof。I claim that。If you look at all the auctions in the world that are guaranteed to sell the item。

Some optionsuction will always do that。 and some options won't always sell the item。

 But if you just focus on the subset of options that always sell the item amongst those。

The Vi maximizes the expected revenue。Yeah。So I'll explain why this is true。 But first。

 let's just observe that if we can prove this claim。

 then we're done with the proof of the Bulo Clorer theorem。Why， well think about this auction A。

 right， So well， first of all， we have optt with n bidders。So there's just some number，100， whatever。

I defined a second a A on n plus1 bidder that by definition has exactly the same expected revenue 1000。

 Moreover， it always allocates the good。Then by this claim， the victory auction， which， of course。

 always allocates the good。 The claim says that it's even better。

So the claim says victory have to be better than a， which is equal to opt with one fewer bidder。

So all I need to do is prove this claim。So， a reason。So proof of this。And notice。

 I haven't used my II D regular assumptions yet。So that better coming in now。

So suppose I gave you the very weird problem that I wanted you to always sell the good。

 And then subject to that constraint， I wanted you to maximize revenue。

So how is this different than the problem we've already been studying。Well。

 so now that sum of thexis have to be equal to one， not the most one。Okay。So these bids show up。

 They have their virtual values。 right， Some might be negative。 Maybe all of them are negative。

 And you've got to give the item to somebody， even if all of them are negative。So you， you pick the。

 you know， lesser of all the evils， right， You just pick the biggest virtual evaluation。

 even if it happens to be negative， because you got to tell the good。

 There's nothing else you can do。O。So if you want to max revenue。Subject to always。Selling good。

Alllocate to the bidder。With the largest。The I VR。Even if this happens to be negative。看。

So that's just from the very first thing we said to be in the lecture。 Okay。

 when you you want to maximize virtual surplus whatever your problem。 Okay， so in particular。

 in this problem， you want to maximize virtual surplus， it's regular so we can do it point wise。

 So this is what it says to do。Is there a question with？Good。

 so this is the revenue maximizing auction subject to always allocating。

And I claim that because it's Id and regular， actually the Viy a is doing exactly this。So why。

So what is Vickery doing？What gives item？To the person with the highest valuation。看。

Generally speaking， not the same thing。Okay。But what are our assumptions， So， first of all， it's I D。

 So all the Fi I are the same。 Everybody has the same function fee。Okay， what does regularity say。

Regularity says it's an increasing function fee。Okay。

 so if I order everybody's valuations and I apply the same increasing operator to all of the valuations。

 I get a different set of n numbers， but they're in exactly the same sort of order as before。Okay。

 so the bidder with the highest valuation is also the same as the bidder with the highest virtual valuation。

So in some ways， it's not what the Vi is designed to do。

 but it's inadvertently maximizing revenue subject to the constraint of always selling the item。

So that proves this claim， which means the victory auction does at least as well as the auction A。

 which is equal to the revenue of opt with one less bidder。Have a good weekend。 I'll see you Monday。

