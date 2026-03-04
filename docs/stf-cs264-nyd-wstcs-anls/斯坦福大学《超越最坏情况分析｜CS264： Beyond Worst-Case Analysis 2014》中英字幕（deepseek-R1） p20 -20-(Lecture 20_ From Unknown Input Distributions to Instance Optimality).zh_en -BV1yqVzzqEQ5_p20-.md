# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p20 -20-(Lecture 20_ From Unknown Input Distributions to Instance Optimality).zh_en -BV1yqVzzqEQ5_p20-

What I want to do today is I want to close the loop。 Okay， so when I put courses together。

 I sort of think of them almost as like a playlist and a really good playlist is the one you start wantna playing from the beginning。

 right when you end it。 So we've been talking about these unknown I D distributions over over inputs and algorithms that are good for them。

 I want to connect that to our very first topic， which is instance optimality， okay。😊。

So let me remind you about instance optimality。So this means you're basically optimal。

 at least up to a constant factor， input by input because it's the strongest possible least controversial notion of optimality。

So whatever your cost measure。Algorithm A is alpha instance optimal。

If for every algorithm B and every input Z。Youre within an alpha factor of the cost of B on Z。Okay。

So provided alpha is reasonably small。 This is a super， super strong guarantee。

 Really the best you could hope for。 So strong， in fact， that often these algorithms don't exist。

 okay。And so we talked about， at least for values of alpha that are interesting。Okay。

 so this is we mentioned a couple relaxations like throwing in the alpha。

 and then the other relaxation we mentioned， which is the one I'm really going to focus on today。

As you can say， well， you know， maybe our algorithm A isn't as good as every single other algorithm on every single input。

 but maybe it's as good as every other reasonable algorithm or every other natural algorithm B on every single input。

So the relaxation is restrict B， the competing algorithm。To a subclass。Scrip C。Of natural algorithms。

So that's an idea。But then， of course， you know， the question， and in fact， really。

 we sort of did this when we talked about 2D maxima。

 This is way back in the very first week of the class。

 We observed that this definition is problematic because this when you're given a point set。

 you're trying to compute the maxima the preto optimal points。 And， for a given input Z。

 there exists in algorithm， which is basically memorize the input of that input Z。

 And the way we got around that is we kind of said， well， those algorithms are unreasonable。

 That's only look at algorithms， which don't memorize the input in the sense that their running time or at least our running time analysis is independent of the order in which the points are presented。

 Okay so effectively for 2D maxima， we define script C as the order oblivious algorithms B。

 So that's what we're doing back then。Now， in general， for a general problem。

There's this question of， know， how what should C be， Okay。

 so what other algorithms be should we be competing with。So what's a good。

 well motivated choice for the set seat。And clearly。

 what we're looking for is we're looking for sort of a sweet spot。So on the one hand。

 C should be small enough that we can prove something interesting so that we can actually prove an instance automaticmatic result for some algorithm。

 which is nice。 On the other hand， you know subject to that， we want it to be as large as possible。

 as rich as possible， encompassing everything we might plausibly implement。 So by doing the analysis。

 we're hoping to kind of say， well， among everything we could imagine actually implementing。

 here is the best one， here's a few ones that are kind of as good as it could get within that class。

And so what I want to point out。And sort of the main conceptual point of this lecture。

Is that all of our discussions about， you know， sort of unknown underlying distributions motivates a way to define these sets Sc C。

And so unlike。The previous three or four lectures where we were literally assuming that there was a distribution over the inputs。

 and we proceeded to analyze algorithms。 According to that assumption here。

 we're going to think right now， temporarily about distributions over inputs only as a thought experiment。

 Okay， only to define the set C。 so in this lecture。

 just I mean I know I'm getting ahead of ourselves。 but just to clarify this lecture。

 we will never actually do average case analysis。 We will never actually take expectations over an input。

 we're only going to look at distributions over inputs to define the set C。

 Then once we have this set of competitor algorithms。

 We're going to look for an instance optimality guarantee in this sense。All right。

 so how do we do this？Well， again， so just temporarily， suppose there was a distribution over inputs。

 okay？And maybe we don't know what it is。 Maybe it's unknown， but we， you know。

 like in many lectures， we've seen， we have some set of distributions where which might be governing the input。

It's a set of distributions over inputs。And again， in sort of a different context。

 we've seen many examples of what these sets might look like。 So in smooth analysis， this would be。

 for example， you know point masses slightly perturbed or sufficiently diffuse distributions。

 when we were talking about local search when we were talking about hashing。

 this would be all distributions that have enough randomness in the sense that we defined in that lecture So in self-improving algorithms and we talked about sorting there。

 we were assuming that the different entries of the array were independent。

 So we were thinking about all distributions subject to being independent across different different array elements。

 when we talked about pricing algorithms， a couple lectures ago， we had this regularity notion。

 for example， saying that this revenue curve was conca， But other than that we made no assumptions。

 So all of those are examples of families of distributions capital D and again， the point is。

You know， often， it's plausible that you know something about the distributions on a course level。

 about the inputs， but you don't really want to assume something like a parametric form。

 that they're Gaussian or that they're uniform or something like that。 Okay。

 so all of these are examples of what these kinds of families of distributions look like。All right。

So in previous examples， we were thinking of inputs as literally being drawn from that distribution。

 But now let's just。Use a set of distributions to define a set of algorithms。

So once youve fixed a set of distributions。Define the corresponding set of algorithms， C sub D。

As all of the algorithms that arise as optimal algorithms for these sets of distributions。

So this is a family of distributions， This is gonna be a family of algorithms。

 which are the algorithms。 Well， you just range over the distributions in your head。 you ask， okay。

 well， what if inputs were drawn from some distribution， capital F， What would I do。

 There'd be some algorithm A， which is the best of all algorithms in expectation over that distribution F。

 You put that in this set。 Then you move on to the next distribution in script D。

 You ask the same question。 You get a different algorithm。

 You put that algorithm in this set and so on。 Okay。

 so you just iterate through all these distributions。

 Look at all the corresponding optimal algorithms， and that's your set。So a optimal。

For some distribution。F and D。And just to clarify， so what do I mean by optimal， well。

 once you fix the distribution。Remember， then there's an unequivocal notion of what it means to be optimal。

 you just to get the expected cost of the algorithm on the distribution。

 so every algorithm has this one number attached to it， it's expected cost。

 some algorithm has the smallest expected cost， that's the optimum。

So minimizing the expectation with respect to the distribution F。Of the cost。

Of A over random input Z drawn from the distribution F。It's a question。

 How does this prevent an algorithm which like checks if the input is。

Crazy and outputs some like memorizes some input for which you wouldn't consider in your distribution。

嗯。It's optimal on that crazy input， but it's also optimal on the D。Well。

 so it might be hard to simultaneously be optimal and a crazy input and be optimal for D。Right。

 I mean， because basically， so what is。 So if you memorize an input， what do you do， Basically。

 the first thing you have to do is you have to check that the input actually is。

 So we insist that you're correct on every input generally， right。

 So if you've guessed an input to try to be fast， the first thing you have to do is check if that's it。

RightAnd then so you waste some time checking and then if that's never the case。

 but so imagine it's a distribution where that's a very unlikely input， right。

 you just always spend this time checking for it， which is a waste of time。

 and then you have to default some algorithm anyways。

 you'd be much better off just using that algorithm。So there's this inherent tradeoff。 I mean。

 so that's always the issue right， So with algorithms is if you're going to be faster on some inputs you're generally going be faster on others or slower on others right if you can be faster on every single input just do it。

 So really thinking about the pareto frontier of algorithms where it's all about tradeoffs between different inputs and then a distribution lets you sort of reason about how to make those trade offs。

 which is just using the expectation。All right， so is this clear， this actually， I mean。

 so it's sort of。This is an important point Okay so the question was how do you come up with a family of algorithms that you might want to compete with and so what we're doing is is we're saying。

 well， let's reduce it to a family of distributions over inputs that you think you know might describe the world and why don't you just try to compete with every algorithm that arises as an alpha the one for one of those distributions so it reduces choosing Sc C to choosing Sc D。

Okay。Okay， and so here's sort of here's the formal connection between an unknown underlying distribution and instance optimality。

 and it's very simple。 know， it's almost trivial， but it's sort of one of the key points of the lecture。

 So let me just you know just do it。So it's not lost in anyone， so suppose you have an algorithm。

And it's instance， optimal。With respect to a set of algorithms like this。 So script C sub script D。

With some constant alpha。Then。For all distributions in your set。

Algorithm A is almost as good as the best for this distribution capital F。

Meaning if I look at the expected cost。Of algorithm A。On a random input drawn from F。

This is the most alpha times the expected cost。Of the optimal algorithm for F。Again。

 evaluated on a random input drawn from。Okay。And the point I want to emphasize here is that on the left hand side。

 this algorithm A， this is independence。Of distribution F。O。

So this is like when we had results where basically you knew the set of distributions。

 like so for example， you knew it was ID or you knew it was regular or whatever。

 and the algorithm could depend on that information about the set of distributions。

 but it couldn't be tailored to the particular distribution。By contrast。

 what we're competing with over here， Opbeth， this is tailored to F。Okay。

So another way had to think about this guarantee and so when I first introduce the notion of hybrid models。

 interpolations between worst and average case analysis。

 this is exactly the kind of inequality we have on the board。

 So one way to think about this is you compare two different scenarios，1。

 I tell you the distribution of inputs， then you get to pick whatever algorithm you want。 Of course。

 you'll pick the optimal algorithm or in the much more unfair world。

 I don't tell you the distribution， I force you to first pick the algorithm。

 and then I show you the distribution constrained only by the fact of the distribution being in scriptee。

So if there's an instance optimal algorithm， then that says you actually lose only a factor of alpha in these two worlds。

 Clearly， you're only worse， right If you have to choose the algorithm without knowing the distribution。

 but there's some sort of way to hedge your bets。 Okay， if there's an instance optimal algorithm。

 you're simultaneously near optimal， no matter what F is。 Okay So it's sort of robustly near optimal。

 as long as you believe that the distribution comes from scripti。So this is the claim。Al。

 so if your're alpha instance optimal with respect to this class of algorithms。

 then your average your alpha approximate on every expectation from script D。Qu back。 So well。

 it doesn't actually affect the result that you just proved。

This script see seems to be very different from our usual notion of like what's a reasonable algorithm。

 because you could imagine plenty of reasonable algorithms that aren't optimal for any particular distribution。

 but are just generally good。 I would say it depends on whether you believe。

 It depends on how strongly you believe that reality is roughly modeled by a distribution。So I mean。

 if you believe more or less that inputs are coming from some distribution you just don't know what it is。

 then if you want to use a subbotimal algorithm， fine。

 you know I'm also competing with that just by transitivity。

 so you're right that if you really you want to use some total totally other measure of how good an algorithm is doing。

 like say worst case， so if you wanted to optimize the worst case performance。

 you definitely might well use an algorithm outside of this class。

So are the algorithms that we learned in 161 and 261， do they have this property？去。

That's a good question。Usually if you're worst case optimal。

 you're also optimal with respect to some distribution。Sure， so like take merge short， right。

 runs an analog end time。Okay， on the end， if the array inputs are scrambled uniformly。

 there's a lower bound of M log n on the expected number of comparisons of any sorting algorithm。

 So you may as well use merge sort。 It is optimal for the uniform distribution over inputs。

 So in that sense， it's going to be thrown into C sub D。

 as will zillions of other sorting algorithms because merge sort is not going to be optimal for other kinds of distributions。

I mean， partly what I'm doing here is it depends on alpha too， right， but so I mean。

 if you're willing to sort of allow me small constant factors。

 then you may as well throw a merge short into the set。

 merge short basically will get thrown into the set plus a lot of other stuff。

So that's not always true。 It's not， you know， there are cases where optimizing the worst case gives you you know。

 a fundamentally different algorithm than if you optimize with the spectral natural distribution。

 but。But， you know， for a lot of fundamental problems。

 this is only going to be kind of a stronger guarantee。 I mean， is So it's instance optimality。

 Right， So I mean， it's in the spirit of what we're trying to do at the beginning。

 where if all we wanted to do was be optimal in the worst case。

 you kind of learn how to do that in 161。 And we want to kind of have a more input by input kind of guarantee。

 Well not just on worst case inputs， but every input we want to do as well as we can。

 So here we're saying， okay， not you know， as well as we can with any algorithm。

 But as well as any algorithm， which。At least that's expected optimal in some description of reality。

Is there any a question？U。All right， so proof。So the proof is。Straight forward。 But again。

 it's sort of important enough。 Let me just spell it out。 Basically。

 instance's optimality is an input by input guarantee。And this is just an on average guarantee。

So if you have an approximation factor input by input， you also have it on average。

 no matter what distribution you're averaging with respect to。 right， So let me just actually。

Leave it at that。 Okay， so instance optimality， point wise。Only stronger。

Then an expectation guarantee。Okay。So formally， if you really wanted to write this out， you'd say。

 okay， well， fix your favorite distribution capital F。

Look at the optimal algorithm for that distribution F。By the definition of our set of algorithms。

 optt F belongs to our set。 This is defined as all of the optimal algorithms for different distributions。

By the definition of instance optimality。A is at least as good up to an alpha factor。

 input by input as opt depth。So if you average over all the inputs。

 you're also at least within an alpha factor。So it's really just chaining the definitions together。

 how we define C of D and what's the definition of instance optimality。So the point here。

 what I'm trying to say here is that now we're going to， okay。

 so the connection is that thinking about unknown distributions。

Naturally motivates a set of algorithms for which you might want to prove instance optimality and proving instance optimality is only stronger。

 Okay， so again， if you think about the statement， A is instance optimal for every algorithm in some set。

 There's no distribution in this statement。 Okay， it's an input by input guarantee with respect to a set of algorithms。

So we thought we we had a thought experiment about distributions just to define who we want to compete with and never again will we reference a distribution of inputs。

All right。Any questions about that？So that's kind of the main conceptual point of this lecture。

But now I want to show you an example of why this is useful。And a concrete problem。Okay。

So the concrete problem we want to talk about is online decision making。Very。

 very well studied problem。So here's the setup。So there's a set of actions， capital A。Okay。

 and the problem is interesting， even if a only has two options like buy stock or sell stock today。

 okay。So then here's how it works。So there's going to be。T capital T days。

 Think of capital T as known for lecture， although that assumption can be removed for simplicity。

 think of capital T is known。So what happens on each day is you have to pick an action by you。

 I mean， your algorithm can be randomized if you want。So you pick an action。A t and对提。

And then an adversary， after you've chosen an action or at least chosen a distribution over actions。

 an adversary。Picks a cost vector。Indicating the cost incurred by each action and costs are going to be real numbers between zero and one。

Okay。And。Our cost measure so of a given algorithm A。

So an algorithm A just says as a function of what's happened so far。

 what action or what distribution of reactions do you pick at the next time step？

An input is just a sequence of capital T cost vectors。

 and so the cost of an algorithm on a given input is just defined as the total cost。 Okay。

 or total expected cost if it's randomized。Okay。So we'd like this to be small， if at all possible。

Now。You know， you see this description and you should say。You know， doesn't this seem kind of unfair？

Because we're forced to go first and pick an action。

 and then the adversary gets to sort of decide how expensive the different actions are after it sees what we did。

Or at least whatever distribution we're going to use。And you know。

 so there are some obvious and possibilitys results just because of the asymmetry of information between the algorithm and the adversary。

 so for example， it's totally hopeless to try to compete with the best sequence of actions you possibly could have taken in hindsight after the capital T days。

Right， so for start， like imagine your algorithm is deterministic for starters， right。

 So the advers series could just like look at your algorithm be like， okay， what are you gonna do。

 So say there's two actions，1 and 2。 The algorithms will be like， oh。

 you're gonna do action 2 on the first day。 Allright， I'll make the cost of action 2，1。

ll make the cost of action 1，0。Okay，Now I'll simulate your algorithm。 given that that happened。

 I'm going look at what you do on day two。 Maybe then you try action 1。 Okay， well。

 then I'll make one cost one and action 2 co 0。If it's randomized， well。

 you still have to play one of the two actions with at least 50% probability。

 So I'll just give that one cost one and the other one cause zero okay because every day I gave an action cost0 in hindsight。

 there's a sequence of actions with total cost 0。 but you're gonna to pay capital T or at least an expectation capital t over two for a randomized algorithm。

 Okay So that's kind of trivial。 that's not interesting。 And this is actually if you think about it。

 this is basically a negative result for instance optimality。 Also。

 if you think of instances as cost vectors， whatever algorithm you pick。

 there's going to be some input on which your total cost is high。

 yet some other algorithm which memorizes the optimal sequence of actions has caused zero。

 So there's no hope for an instance optimality results without any further assumptions or restrictions。

And it turns out this paradigm， this idea of sort of defining a restricted class of algorithms and doing it in this principled way of thinking about hypothetically。

 if there was a distribution， what would you do， this turns out to be a sort of perfect way to make progress about reasoning about online decision making so this approach。

 this sort of a modern way of thinking about it this is sort of only mostly the past five years that it's been described this way。

 but it regenerates kind of the way people have always thought about these online decision making problems over the past half century or so。

Okay， so。All right， so note。Can't competes。With the best action sequence。In hindsight。

So let's do the distributional thought experiment。 Okay， so again。

 not because we're going to assume that inputs are drawn from a distribution。

 but just to have a principled way of defining the algorithms we want to compete with Sc C sub script D。

Let's think for a second about distributions。So。Question。What if it was the case that？

There was a distribution capital F on cost vectors， okay， so one sample。

From capital F is a cost vector。 So if there's two actions， it's going to be a pair of numbers。

And imagine it's I I D。 Okay， so every single day， we have a fresh draw of a cost vector from capital F。

So suppose that were true and suppose we knew what capital F was。

 think for a second about what would you do， how would you make this decision at each time step。

It's actually a very simple answer。 if you think about it。 it sort of makes the problem degenerate。

 actually。Like， because you could say， okay， well， what if I picked action 1 or what happen。Well。

 I guess there's some expected cost of action1， according to distribution capital F。

 so that's what I get an expectation and you could just think about that same computation for every available action and there's no reason not to just pick the one with the smallest expected cost okay。

So that's what we do on day number one。Day number two， given what happened to day number one。

Who cares what happened on day number one？It's I， right， It's the exact same question。

 exact same answer。 right If action 7 was optimal day one， it' going to be optimal day two。So。

Optimal algorithm is to play。The argument。Of the expectation。Where here C is drawn from F。Okay。

 so just every day， you pick。The same action， the action which minimizes expectation。

And because capital F is not varying with T， Little T。 Neither is what you should do。 Okay。

 so the optimal thing is to play the same action day after day after day。 Now， of course。

 as you vary F。The action， which is the best one to play every day， will change。So now think about。

 so remember， remember this thought experiment works。 You posit a set of distributions。

 And then you think let you go distribution that distribution and you say， what would I do。

 And then you look at the entire set of algorithms that you get。

 So what we just observed is that if you just specify one of these distributions， F。

 assuming only that each T is a new fresh sample I D from this F。

Then you're going play a fixed action。 So with no other assumptions。 F can be arbitrarily weird。

 You're gonna have correlations between the costs of different actions doesn't matter。

 Ranging over all capitalphs in the world。 The only algorithms you're ever going to find are the ones that play the same action every day。

So， in other words。So thus。If script D。Equals all F。And again， it should be IID。

So we do need to assume that each day is exactly like the previous day。 you could generalize it。

 but today I only want to talk about the case where each day T there's a fresh draw from the same distribution capital F。

If that's your set D。Then your induced set of optimal algorithms is just the fixed。

Meaning time andvari。Action sequences。Okay。So it's a very simple result of this thought experiment。

 We range over all distributions。 We see what are the optimal algorithms。

 It's just the things that always play the same thing。So like if there's 10 actions。

 then there's 10 possible optimal algorithms， one of these distributions。

So what would it mean to be instance optimal。With respect to this set of algorithms。That would mean。

 say， for some， you know， factor alpha， that would mean that we have an algorithm A。Okay。

So that input by input， and remember input is a sequence of capital T cost vectors。

 so we'd have an algorithm that no matter what the sequence of cost vectors is。

 our total cost is at most released least up to a factor at most。

 the best total cost achieved by any of those cardinality of a optimal algorithms in the C sub D。

Okay。So again， if there's like 10 actions， there's 10 algorithms here being instance optimal means that no matter what the cost。

Vectctor sequences， our total cost is essentially as good as that incurred by each of these 10 algorithms on that same input。

 Okay， input by input， cost vector sequence by cost vector sequence。

 We do at least as well as every one of these algorithms。

So that's what instance optimality means for that set。Everyone with me。O。

So it turns out what I just said is essentially exactly a very classical notion of a no regret algorithm。

So I'll tell you more about that in a second。 Those of you who've taken 364 from me have seen this before。

 but it turns out this is one way to think about and one way to sort of motivate and automatically generate the notion of neuroregraded algorithms。

Okay， and so the main technical result。Of this lecture is proof that there exists essentially。

 instance optimal algorithms in this sense。That there actually do exist online algorithms which cost vector sequence by cost vector sequence。

 have total cost， no more up to a small error of the best of those algorithms in C sub D。

So any questions about kind of the setup。So just to clarify， we。

 we should think about this adversary is sort of picking。The advance so it's a good question。

 So there's a potentially important and subtle distinction between so calledled oblivious adversaries and so calledled adaptive adversaries。

 and so whether an oblivious adversary would be one that observes your algorithm。I mean。

 it's only relevant for randomized algorithms。 so for deterministic algorithms。

 it doesn't matter because I can just know， I can basically adapt upfront because I can just simulate your algorithm and it doesn't matter。

 So for a randomized algorithm that starts mattering， which is， you know。

 can an adversary actually observe your coin flips on day 10 and use that information to pick a cost spec on day 11。

 And it would seem， I mean in general， adaptive adversaries are more powerful。

 It turns out the algorithm we're going to stare at。

 we're we're going prove guarantees about it doesn't matter。

 So I want you to think of it as an oblivious adversary。

But the algorithm has special properties that make it also the same guarantee holds for an adaptive adversary。

So I guess I just don't see how the adversary just can。Pick the cost to just punish you。 Good。

 regardless of what he。 So the a absolutely can。 So why is that， So the question then is。

 why is that not a barrier to instance optimality。Basically else going if all your competitors suck as well。

There's nothing else you can do， right？So and this is always， I mean。

 so sort of then it pumps kind of， as we've discussed， right。

 we talk a lot about sort of approximation guarantees。 they're not that meaningful of op sucks。

 But on the other hand， what else you're going to do is when you're proving a theorem。

 You're not going to do better than opt。 So， but it's true， like for it to be meaningful。

 you also want it to be the case that in the problem that you care about opt。

 you'd be happy with opts。But it's not an obstacle to the theorem itself。Good question。

 Other questions。It seems like trivially， if you try all tea options and get punished every time。

 then that means that every one of the algorithms that you continue against was punished。Right。

 that's the hope right so the question， so what your worry is you know when you try to simulate one algorithm。

 basically you have this you're just getting all the timing wrong。And actually。

 some of the lower bounds allows you to think about on the homework shows that this can happen。

 say if you use a deterministic like a round robin strategy would not work， for example。

 if you just try to round ro and simulate， we'll talk more about this so I mean there's a lot of truth to that intuition。

 which is if you just do a sufficiently smart simulation of all of the options。

 you should do fine because the only way you wouldn't do fine is if all of them are bad。

 there's definitely a grain of truth in that intuition。

 but really making it work technically requires some cleverness。

Which is why I still have it's a good thing I of 35 minutes of the lecture。

Although it is at this point， it's been， you know， at this point you can get optimal bounds with just insanely clever。

 short derivations， it's kind of amazing， but you definitely need to be a little bit clever。

Okay so okay so I want to raise this so everyone I hope remembers the setup capital T is the time horizon。

 you pick an action or distribution over actions first， then the aversary picks the cost vector。

 you want to minimize the sum of the costs and the benchmark is the best some of the costs achieved in hindsight by an algorithm that plays exactly the same thing every single day those are the algorithms in Scy Sc。

Okay， so here's the theorem。That we're going to approve。

And this is a theorem which has been sort of proved and reroved and rediscovered many times in many different decades and many different communities。

So there exists a randomized algorithm， and it is crucial that it's randomized。

That is so I'm going to be a able little to wish you Was you with a statement for the moment。

It's roughly instance optimal， I'll tell you what I mean in a second。It's roughly in optimal。

With respect to this set of algorithms， all of the algorithms that play the same thing every single day。

With alpha roughly equal to 1， I'll also say what I mean by that in a second。Okay。

 but that's the main point。 Okay， So the main point is a very strong instance automatic result。Okay。

 so in particular， remember our key fact， instance optimality is even better is even stronger than being simultaneously optimal with respect to every distribution。

 So in particular， this one randomized algorithm is essentially optimal。

In any situation where you're so lucky as to have cost vectors being drawn I I D from some distribution。

 Okay， that's a special case of this guarantee。 It's stronger because again。

 this guarantee references no distribution。 But if you instantiate this algorithm。

 when there is a distribution， then you get a good guarantee。

But you also get some kind of interesting guarantee， even if there's no distribution。

Because it's instance optimal。Okay， so what do these squiggles mean？

So the way we've been talking about instance optimality is we have this alpha。

 this multiplicative factor。 Okay and it turns out the way I've set up this problem。

 it's smarter to think about additive error as opposed to multiplicative error。

 So that's what we're going to talk about for today。So we're going to have additive loss。That's。

Big O of square root of capital T login。Capital T here is the time horizon。

 Little N is going to always denote the number of actions。 I mean， but again， even for two。

 this is interesting， but it's whole or any n。Now， okay， so again， so out of loss。

 this means the expected cost of our randomized algorithm might be worse than the best。

Of the algorithms that always play the same thing every single day。

 you sort of you see that that has to happen if you just， if you imagine capital T was just one。

You know， sort of the the only thing you do is， you know。

 basically pick an action uniformly at random。 and you might be wrong。 Okay。

 And there was some algorithm that played the best action on that one day。

 So there's going to be some additive loss， if you think about it。And right， but so it's bounded。

 So the extent to which our total cost will be larger than the best of the fixed actions is at most of this amount。

 root T times square root log n。Now， you look at this and you should think， okay， well。

 help me interpret this。 Like is this good， is this bad or what？ And in particular。

 the larger the time horizon， you know， this is growing。

 usually in these problems you think of n as being fixed， maybe big。

 but you think N is just being fixed。 And then you're interested in the scaling as capital T grows as you play the game for longer or longer。

 And you sort of hope to do better right， So the bigger capital T is your algorithm should get smarter as it has more information about the past。

 somehow here it's getting worse。 But so the way you should think about this is in terms of the per time step loss。

 Okay so on average over all of the plays of the game。

 how much worse are you doing than your best competitor。 So then you divide this by capital T。

And it looks much more reasonable。Okay， so square root of log n over square root of t。Her timet。O。

And so， in particular， if。You'd say would like to have a guarantee which says， well， okay。

You knowI'm going to be a little bit worse maybe than the best fix action in hindsight。

 but I just want to be like 1% worse or 0。01 worse per day。Then you just need to take， know。

 that's going to hold as long as your time horizon is sufficiently large。 Okay， so for Epsilon。

 you need log n over Epsilon squared。Which is actually quite fast convergence。呃，有。

So that's the right way to think about this。So this is called a no regret algorithm。

And the formal definition of a no regret algorithm is one where the average per time step regret is going to zero as t goes to infinity for fixed 10 so because we have a T in the denominator here。

 this is going to zero so the longer you play the game。

Pretty much you're converging to it as if you knew the smartest fix action to plan hindsight upfront。

And also and I'll ask you to explore this on homework number 10。

 This is the best possible result you can have by any online algorithm Okay so both simultaneously as a function of N and as a function of capital T。

 there is no online algorithm no matter how clever which has regrets smaller than this。

 So that's another sense in which we should sort of appreciate this guarantee。All right。

 so that's the formal statement。's I'm going to prove。So everyone clear on the statement。Good。

 so this is probably， you know， so these are the interpretations of the result， but you know。

 this is probably the easier way to think about it。 Okay， so just sum up all of the costs。 Okay。

 so that's scaling probably with capital T。 and then the extent to which our total cost is going to be bigger than the best competitor is at most route T times root log in。

Now there's actually a few algorithms which achieve this guarantee。

 probably the best known one is called among other things multiplative weights。

 that's the one that I've taught in 364， so I'm not going to teach it today。

 but if you're curious you can check out for example my lecture notes from my class last fall。

That has sort of very natural algorithm。 Basically what you do is you keep track of the past performance of all of the actions So say you're on day 100 and there's like 10 actions。

 a natural thing to do is say， well， let's look at the previous 99 days。

 see how well each of these 10 actions did by how well， I mean。

 look at some of the cost you would have incurred if you'd always played action one the previous 99 days。

 same thing for action2， same thing for action 3 and you should be biased toward the actions which have been doing better。

 meaning have lower total cost so you're going to make a randomized decision。

Okay at least in the multi weights algorithm make a randomized decision and it's more probable that you'll pick actions that have lower cost in hindsight。

 So that's message one you should pick probabilities in some sense proportional。

 or at least according to past performances the other thing which you need to get this optimal bound in which multiplicative weights does is you adapt fairly aggressively So even if an action had been doing very well it starts performing poorly。

 you very quickly move mass off of that action and on to others so those are sort of the two messages from multi weights。

Use past performance to choose your probabilities and also aggressively punish poorly performing actions。

I don't understand how if we're dealing with a truly adversarial。

Opponent that using the past performance。usingsing the password would at all influence the future。

You pass。Right， like if are we actually assuming there's some。Distribution over Def not。 Again。

 the name of the game is just the only way the adversary can make you perform poorly and expectation is to make all of the competitors perform poorly as well。

So don't forget the benchmark。Yeah， thank。Okay， so I'm going actually teach you a different algorithm。

 which has this guarantee， which is also very nice due to ki themala。

 I'm going to do this second one， partly just for the sake of variety。

 but also partly because there's a nice smooth analysis one can do of this second algorithm。

 So that's another connection， which I'll mention on homework 10。 Okay。

 so there's a nice connection between this other I'm going to show you and the other concepts we've seen in the class。

 Yeah，😊，Yeah。Yeah。Yeah， there's no adversary in this definition。 Yeah， so you just。You know。

 positive the distributions。 So the adversary comes up。 I mean。

 the adversary is sort of implicit in the definition of instance optimal， right。

 So this is just like a class of algorithms。 do with that， what you will。 But then all of a sudden。

 when you want to start staying， input by input， I want to be as good as every single algorithm。

 Now all of a sudden， like the way we usually think about proving those kinds of guarantees is there some adversary is trying to you know。

 prevent us from proving instance optimality by virtue of exhibiting this really nasty input where our algorithm sucks。

 but someone else is just really good。Yeah， so it's really instance out the out it。

Lynn motivates the adversarial way of thinking。But remember。

 instance optimality is just parameterized by any set of algorithms。

the distributional thought experiment is just to， have a well motivated choice of which algorithm should you think about amongst。

 you know， otherwise it's sort of cart blanche， and it's hard to know where to start。Good， all right。

 So before I show you the algorithm that does work， let me show you an algorithm that doesn't work。

But it's very natural。So this is follow the leader。And this again。

 is just sort of the simplest way you try to use past performance to decide what to do next。

So for you on each time step。So on day one， you just do something arbitrary。 It doesn't matter。

 but at every subsequent day。What actions do you choose while you just look at each of the actions。

 see which ones has the smallest cumulative cost up to this point and do that。Okay。Could。

Very natural thing to try。And you know， it's。So in homework number 10。

 turns out this is bad in the worst case。Actually， any deterministic algorithm is going to be bad in the worst case。

 In by worst case， I mean， it's not instance optimal Okay， I mean， it does not have small regret。

 case it has regret growing linearly in capital T， at least for a worst case sequence of cost vectors。

On the other end， it is good on smooth instances。Okay。What do it mean by smooth instances。

 I mean the adversary has to pick a sequence of cost vectors up front。

 and then all of them get perturbed in some way。And so if all of the cost vectors。

 even if the adversaries starts gets to pick the initial ones， if they're perturbed。

 then follow the leader point。And that sort of follows from the analysis I'll give you for a different algorithm。

So good and smooth instances。Well， it's sort of a homework， so I kind of want you to think about it。

So。U。worst case over distributions， no， there's no distribution。

Over costs over cost specter sequences。Actually， any deterministic algorithm can be bad。

 So that's sort of a hint。 It's not just this。 It's really any deteristic algorithm。I mean。

 in some sense， you can also， I mean， we're going analyze a modified。Version of this algorithm。

 So you might want to， as we analyze the randomized version。

 think about where that proof would break if it wasn't randomized。

 if you're just doing it for this algorithm instead。So。When say compared with the best exactly。

 so the claim is the following for every single sequence of cost vectors。

It will be the case that the expected cost of this randomized algorithm。

Is it most on that cost vector sequence， Is it most the minimum cost of any algorithm in C sub D on that ca vector sequence。

Up to this error term。And that's true for every single conor sequence。

So all of the randomization we're going to be talking about is only internal。

 it's in the usual sense you're used to from your algorithms classes。

 it's only internal coin flips made by our algorithm Okay there's no coin flips in the data。

 no randomness in the data。 We really want to guarantee it's cost vector sequence by cost vector sequence。

All right。Instead， we're going to look at a pertred version of follow the leader。And。

Here's how it works。 So basically， we're gonna do follow the leader。

 but we're just going sort of initialize it randomly。 And that's good enough， actually。So。

As a pre processingcess step， before we even look at the first cost vector。We award to each action。

 a random bonus。Okay。And lots of distributions for the random bonus would work。

 but the analysis is particularly simple if we look at a geometric random variable。

With parameter epsilon。So what I mean is for action number one， you do the following experiments。

 you start flipping coins and the coin has a probability epsilon， we'll choose epsilon later。

 think of it epsilon as small though it has an epsilon probability of coming up heads so you keep flipping until you get a heads and then you just count how many coin flips you needed to get a heads。

So if there's probably of epsilon of getting a heads。

 what's like the expectation of this random variable。One of Repsilon， obviously。

 the smaller probability of heads， the more coinless takes to get one。

 and it's one of rhpsilon for geometric。And we do that exact same experiment independently for each of the actions。

 so each action gets its own random bonus。So a number of coin flips。

To get heads or the probability of heads is epsilon。And now。

We just do follow the leader with these random bonuses。Okay。So now we just set our action。

To be the one that minimizes。The same thing， past performance。Minus。

The number of coin flips it took to get hits。OK。So everybody starts with some like negative total cost。

And it's random for different people。And then you just accumulate the real cost from then on。

So the single perturbation at the very beginning。And that's it。Does the algorithm clear？Okay。

So the claim is that algorithm。Satisfies this theorem。And the proof， the analysis is very clever。

So analysis。So again， remember， we're shooting for an input by input guarantee。 Okay。

 so fix an input arbitrarily。Okay， so fix C1， C2。C capital T。 as I said。

 think about an oblivious adversary that has to fix the sequence up fronts， although actually。

 if you think about it just so， one can realize that the guarantee extends even for an adaptive adversary。

 but think about an oblivious adversary。So it fixes。

 So the adversary sees our algorithm in effect and。

Devisise is the worst cost vector sequence you can think of。So for the analysis only。

 we're going to define a fictitious algorithm， the algorithm we can never implement。

 but it's going to be useful for the proof nonetheless。It's a defined fictitious algorithm。A。By。

So what it does is it does the same thing as perturbed follow the leader。Sorry， this is wrong。

So protuophil the leader。Right， so at the time of T。

 the information it has is the first t -1 cost vectors。 right， So the only thing， right。

 So this is what I meant to write， S less than T。So it uses all the information that it has。

 which of course， is only from the past。To make its decision。Okay。This algorithm capital A。

 it's going to also make use on day T of the cost vector at day T。Now， of course。

 no online algorithm in our model actually knows the cost vector at time T when it makes the decision at time T。

 But for the proof。Let's think about this fictitious algorithm。

 which could sort of look ahead one step。All right， so it sets。8。To be orgman。

Of sum overall s up to and including JT implausibly。And again， with a random bonuses。Okay。

And so again， for emphasisesis， we could not implement this algorithm for proof purposes only。Okay。

All right， why did I do this， Well， this turns out to be a really useful。

 intermediate object to argue about。So let me tell you the three claims。

 which together imply the theorem that I'm erasing。So three clamps， first of all。

With probability one。The regret of this fictitious algorithm A。And what do I mean by regret， I mean。

 the total cost of A。Okay， so the sum of a little T of CT AT。

So cost of a minus cost of best fixed action。that's what I mean by regret。

The claim is that this ist most。The biggest of the perturbations。

I remember x of a is the number of coin flips until I get hits？So we have this parameter epsilon。

 which we haven't specified yet， But as epsilon gets small and small and smaller。

 So the likelihood of a heads is small and smaller。

 the sizes of these xavates is going to be getting bigger and bigger。

So the right hand side here is getting bigger as epsilon gets small。Okay。Notice actually。

 that if all the xabs were 0。Okay， so if you think about this。 So this would probably one。

 Okay and the randomization is over the， the only thing that's random is these perturbations， right。

So the claim is that this is true， even if all the x ofavs are zero。Okay。So an x of a is0。Perturbed。

 follow the leader。Is exactly the same as follows the leader。

So a special case of what we're proving here is that。If there are no perturbations。Then。

The regret of algorithm A Ie follow the leader where you additionally are thinking about the cost vectoror T。

 Okay， you're sort of cheating and adding T。That's at most the cost of the。Of the best solution。

All right， so that's the first claim。Second claim。Is that， yeah， we're cheating。So what do we do。

 So what's the difference from prorrb father leaderer， PFTL and A。

 The difference is that we added the current day's cost vector into the computation。

 That's the only difference between the two algorithms。So we're cheating， you know。

 we're looking ahead into the future by day， but the claim is that cheating doesn't actually matter much for the cost computation。

Okay， so the claim is that the expected regret of an algorithm that we can implement。

Returned to follow the leader。Is it most？Be regret of this algorithm that we can't implement。 A。 O。

 it's not quite as good。But it's only going to be off by epsilon times capital T。

So epsilon sort of difference per time step。In step 1。

 the smaller epsilon was the bigger the x of As。 So the bigger our loss。 But in step 2。

 as we bring epsilon down， actually the less loss that we're doing。So for step one。

 we want epsilon to be big， for step two， we want epsilon to be small。And then the final claim。

 which is quite simple。Is that it's very easy to understand how big this is going to be as a function of Epsilon。

So an expectation。The biggest of the perturbations is going to be。

Loariththmic in the number of actions divided by epsilon。

So remember the expected value of one of these。As we said， is one over Epsilon。

 we have a bunch of things。 Their expectations is one of epsilon。 We have n of them。

 The biggest of those n is going to be like log n bigger。 log N over Epsilon。

So let me just point out that these three claims imply the theorem。So upshot。

If we chain these together。The expected regrets of。Perturbed， follow the leader。

So we chain all three of these together。Is it most？Right， right， so this regrets it most that。

 And we pick up an additional epsilon T。 And that's just that。

 So this is going to be at most epsilon T plus O of log n over epsilon。

Epsilon remembers a parameter of our choosing， so our follow up with the picture leader is just parameterized by epsilon。

 so we should set it to balance these terms。And so this is just O of。Routty log n。

With the judicious choice of epsilon。Equal to log n。Over square root of log n over T。

So this is why assuming claims 1，2 and 3。 we get the desired theorem。

 This was exactly the lost bound claimed in the theorem。Questions about that。I mean。

 so I owe the proofs of these other than that， any questions？Okay。

So let me address the claims in reverse order。This is straightforward Okay， so like we said。

 it' the expectation of one thing is one of Repsilon。 you have n of them。 the max is a log， in fact。

 are' bigger。 You've seen a lot of statements like that。

 I'm going to put this on as an exercise on homework number1。Literally。

 you just compute the probability that the geometric random variable is sufficiently large。

 you take a union bound and you're pretty much done。So that's easy。

Claims1 and2 are not especially difficult， but they're very clever。 They very clever proofs。Okay。

 so let me prove two and then prove one。All right， proof of two。All right。

We want to show that the regret。 So let's just keep in mind what the difference between these two algorithms are。

 Okay， So in both of these algorithms， they pre process the same way with these random bonuses。

 these X subs。And then at every time step， they pick the action。

 which minimizes the cumulative cost so far， plus the random bonus。

 The only difference being that A uses day T's cost vector in its computation because it uses the first T co vectors。

P proed for the leaders a real algorithm。 So it only uses the first t -1 cost vectors。

 but we want to say the expected difference in regret is most abstract on T。

So we're going to prove actually that the difference in the expected costs of the two algorithms is at most epsilon T。

so they have almost the same cost， so therefore they have almost the same regret。Actually。

 we're going push something even stronger than that。

We're going to improve on almost every single day。The two algorithms do exactly the same thing。Okay。

 so we're going to prove that for every single day tea。With probability。

 the probability that they do something different is at most epsilon。Remember。

 the costs I've assumed are between0 and1。Okay， so if you do something different。

 it at most introduces a cost of one a difference than one in your costs。

 Okay So if only an epsilon fraction of the days do you do things different。

 that translates a difference from only epsilon T in your cost， expected cost。

So that's what I'm going to prove。 Okay， so for every tea。Every day too。

ThePro that they do something different from each other is the most epsilon。So， claim。All right。

 so fixed A。Now， here's another sort of。tririvial with very nice observation， okay。

What can you tell me， that's okay， we want to prove on a given day T。

 these two algorithms are going to do very exactly the same thing。

What can you tell me about the action。That PFTL plays on dayT。

Versus the action that our fictitious algorithm plays to the previous day on day T -1。い same。Sisan。

so in day T prored follow the leader， they're using the same random bonuses。

 the same distribution of a random bonuses。P， F T， L， what does it do。

 uses all the information it has。 Okay， the first t -1 cost vector is and it picks the best one。

 Okay， the day before。A already knew that information， right。

 and it used all of that information to make a decision， okay。All right。

The probability that these two actions do something different on day T is the same as the probability that algorithm A does something different on consecutive days。

 So now what we want to prove is this this fictitious algorithm on the right。

If we look at an arbitrary pair of consecutive days， t 1 and T。

 we want to argue that with probably at least one minus epsilon。

 it proves it picks the same action both days。That's what claim two has been reduced to。Okay。

 so why is that true。So。Let me tell you a sufficient condition for that。OK。

So suppose we're at day t minus1。Because we're thinking about the fictitious algorithm。

 We're curious about whether it switches actions between day T minus1 day T。Suppose on day t -1。

 there's a big difference between the best action and the second best action。By big difference。

 I mean， the cumulative cost so far， plus the random bonuses。Is strictly bigger than one difference。

 Okay， But say the best action is action number 7， its score。

 its random bonus plus cumulative cost is 124。 And the next best one is like 121。5。Well。

 then we're definitely picking action seven tomorrow。Costs are between 0 and 1。 Remember。 O。

 So the gap in the cumulative cost between two actions can only narrow by one in a given day。

in the worst case， action7 had cost one， the second best action at cost zero。

 and the cumulative cost gets closer together by one。But if a day  T -1。

 it was already out competing the other one by strictly bigger than one。

 then we're definitely going to play it the next day， as well。O。So where do we stand。

 now what we need to prove。We need to prove that on a given day。

 or it's sufficient to prove that if we look at a given day。

The first best action is much better than the second best action with probably at least one minus epsilon。

Okay。So let me prove that， to you，So it fix a day T。All right。

And so we're going to use the principle of deferred decisions to do this。 Okay so define。不。

So would C sub A be the cumulative costs not counting the random bonuses，嗯。Yeah， no。

 so it feels like you're making the analysis by assuming the difference between the best cost function and the second best cost function is independent each day。

No， so I want to make the。 No。 So ultimately， there'll be a linear of expectations， applications。

 So I don't care about independent。 I don't need independence across days。

 So all I'm asserting is pick your favorite day T or your favorite consecutive pair of days。

 T -1 and T。I just want to say it doesn't matter what t is。

 it's just communicate case with probably at least one minus epsilon。

 you play the same thing both days。Okay， so then by our previous equivalence。

 that says that PFTL and A。Play the same thing with probably at least one minus epsilon。

 I they play different things with probably most epsilon。So that means in a given day T。

 the expected difference in cost is at most epsilon。

 and so now I just sum over the days and that's just a linear of expectation computation。

 so you're absolutely correct in the objection that different days are not independent of each other。

 but it just doesn't matter。Good question。All right， so just to remind you， what are we doing。

 we're trying to say we're considering the fictitious algorithm， I at this point it doesn't matter。

 but it's the fictitious algorithm。Weve fixed a A T。 There's some best action。

 There's some second best action。 We want to say that the difference between their cumulative cost plus random bonuses at this given time is very likely to be bigger than one。

Now， I want to use the principle of deferred decisions。 Okay。

 so that means I want to sort of flip the random coins only as I need them。

And so let's start with no random coins at all being flipped。 Okay， so it's， it's almost like。

 think of the bonuses as 0 for the moment。So that gives us these capital C subs。 All right。

 So the picture。So say there's like four actions。Okay， so there's action1。So here C subA is going up。

Okay。I guess it should be indexed by T also。It's a given day。Okay。So these are whatever they are。

 Okay， so remember， the adversaries fix some cost function sequence。

 So there just are these numbers at D， whatever they are。 Okay。

 and we haven't flipped the coins for the random bonuses yet， okay。Now。

 if we were just playing normal， follow the leader。We'd choose this one。Which is the smallest。Now。

 in perturbed father leader， we may not choose this one。

 because all of these are going to get sort of shifted down by random amounts。

 And we're going to pick the one， which after the random subtraction is the minimum。

So here's what we're going to do。 Okay， We're going to flip the coins lazily only as needed to figure out which action perturbbed by the leader is actually going to take a deity。

 okay。So's how what we do， we start with the worst action。Allright。

And we start trying to figure out what this guy's random bonus is by flipping these coins。 Okay。

 remember， we flip a coin。 If we get tails， we subtract one。And then we repeat the whole experiment。

 It's memoryless。 okay， if it's heads， then we stop。So we flip a coin for the worst action first。

 if it's heads。Then we can definitely exclude this action from further consideration。 All。

 Everybody's only going down。 So if this guy stops bigger than the other ones。

 it's definitely not going to be picked as the minimum this day， okay。So we start living coins， okay。

 but maybe， you know， maybe we keep getting tails。 Okay。

 so we keep like getting better and better lower bounds on the random bonus of this person。

And all of a sudden it's in a tie with the next best action。

So now what we're going to start doing is we're going to start flipping coins for both of these each。

 So it's almost like a runoff。 and these are going to get subtracted，So we flip coins。

This is how we're determining the bonuses。 As soon as we get heads for something， we can discard it。

Okay。So it's kind of this race， right， we have this coin flipping race where some people have these you know where they have different starting positions depending on the C sub base。

Now， at some point， we'll have figured out know which one is the best one。 right， So like imagine。

 you know， it comes down to a race between action 2 and action 4。So these guys。

 their head was the head was flipped and they were still really bad。 And so。

 we're going back and forth。 ate ate between actions 2 and 4。 You know， we got a tails。 We got tails。

 then we get another tails。 We get another tails。We keep going back and forth。 And at some point。

 right， we're going to get the heads on one of them， right， say this one。Okay。So this guy's done。

We actually know the random bonus plus cumulative cost of this action for。Action 2。

RightSo we've determined that this will be the smallest。

 but we haven't actually determined what its random bonus is。

 We've only determined a lower bound on its random bonus。So to fully sample action to's random bonus。

 we have to keep flipping coins， right？And what if we get a tails on the next one？おて付き。

If we get a tails on the next one， this guy' is actually going to wind up not just less than action 4。

 He's already less than action 4。 One more tails。 This person strictly more than one less than action 4。

All we need is one more tails。And that happens with probably1 minus epsilon。Okay。

So that's how you do it。So first you think of the random bonuses as zero。

 you just sort them by the cumulative costs at A without the random bonuses。

 flip coinins lazily to figure out which guy's the winner， the smallest。

 and then keep flipping and the only bad case is if you get a heads immediately after determining which action happens to be the minimum。

All right。So。Done by principle of deferred decisions， plus linearity of expectation。嗯。

So that's claim two， okay that's one of the that's super clever two claims。All right， so claim one。

律师。Alright， so claim 2， claim 1 is a quite simple computation。So， first。Assume。So I'm claiming this。

 no matter what the random bonuses are。 Okay， so this is where。

 this is really where the genius of the definition of the fictitious algorithm comes up。

 In case we're saying that the regret。 what did we want。

 We cared about the regret of follow the perturbed leader。 We had no idea how to analyze that。

 We did understand by the last claim how to at least tether the regret of perturbed follow leader to this other fictitious algorithm A。

 Turn out algorithm A is something whose regret we can get a handle on directly。

 And that was really the point of the definition of a。So in what sense can we get a handle on it。

 we want to say is regret is it most the biggest perturbation。

Let me show you me just sort of clarify things， let's assume all the Xs are zero。In which case。

 algorithm may is just follow the leader with this one extra cost vector， okay， it's not perturbed。

So in that case， I need to show you that the regrets at most 0。

 Okay So follow the leader with omniscience for one extra day is as good as the best fixed action in hindsight。

So suppose the Xa is equals0。Then。All right， so let x a star。Be best fixed。And let a1。Up to A T。

BA's action。Okay， so this is our competitor， the cost of a star day after day after day。

 and then our algorithm， algorithm capital A incurred these costs。So let's begin with our competitor。

RightSo we want to say our cost is at least as good as this。

 If we're doing follow the leader with the one extra piece of information each time step。

 So we want to lower back。Allright， so what can you tell me about the relationship between a star。

 the best fix action in the hindsight and A T。When the perturbations all happen to be zero。

So let me just remind you what the。And pert to follow the leader。 How did we。

 how did we decide things。We took the argument。With the random bonuses。

 which we're currently assuming is zero， okay， so ignore these。Plus， sum up over all the days。

 including today。Of the oops。So this was the decision rule that pertred to follow the leader used。

Okay， so look at all the days up to today。Okay so what's fictitious and pick the best one。

 cumulative cost up to today。So what can you tell me about the relationship between a star and a capital T。

 assuming all the Xs was0？A0 is。Gets to choose a different action each time。 Oh。

 so you're jumping ahead。 That's pretty much the whole proof。 actually， Yeah。

 but let's just focus on the very last one。 A capital T。 Yeah， yeah， Yeah， no you're right。 exactly。

 So a capital T actually equals a star。When the x is are all0。O。

 a star by definition is the best action in hindsight。

 If you stare at this and take little T equal capital T。

 you realize this is also just the best action in hindsight okay。But let me just you。

 write it this way as an inequality。Even though it's an equality。Okay， so basically。

 a superscript capital T is chosen so that this is true。 It's chosen to optimize this。 Okay。

 so it can only be better。So now let me just peel off continuing this derivation。

 Let me peel off the last term。So this' is just rewriting the right hand side。Whatop's minus-1。O。

So what's going to happen instead of if I substitute a capital T here with a capital t -1？

It can can can only get smaller， right， So if we look at the decision rule of the algorithm at every time step。

 it's picking the thing that minimizes the cumulative cost up to that point， okay。

So if I replace this capital T with a t -1， this only gets smaller。

So that's by the choice of A t minus1。Okay，18 -1 is chosen to make that sum as small as possible。

 Okay， so it's no bigger than if a capital T was there。 Now I do the same thing。

 I just peel off that T -1 term。so that leads me with a sum over the first capital t minus two days。

 I've substituted an a to the superscript t minus2。

 that's only better by the choice of A minus2 and so on。So at the end of the day。What you get。

 you just get to sum of all these peeled off terms。Which is just some over the days of CT of AT。

Also known as the cost incurred by the PTF algorithm， sorry。

 PFTL algorithm in the special case where the x's are0。And actually。

 it turns out and because of amount of time， I won't do this for you。

 but it' would be very easy for you to do yourself if with arbitrary X's。

All that happens is in every inequality in this derivation。Okay， you lose a little bit， Okay。

 because in general， now， it's not the case that， you know， this is at least as good as this。

 Maybe the algorithm got misled by the perturbations。 And remember。

 we expect some error in this step because of the perturbations。

 Maybe it's the case that you didn't choose。You knowThe best thing you didn't choose A star because A star got a small random bonus and your a capital got a big random bonus。

So there's going to be some error here and it's going to be just the difference in the bonuses between a star and a capital T。

 that's all that matters， you get one extra difference of two bonuses。

You get a difference of two bonuses in every single inequality。You add up all of those last terms。

 you get a very elegant telescoping some of differences。And at the end of the day。

 this exact derivation holds modulo one difference between two bonuses。 That's the only difference。

And so the difference between two bonuses， they're both non negative。

 so that's bounded above by the biggest bonus of them all， and that's what we need to prove。

So that concludes the proof of the theorem。All right。

So sometimes I do a top 10 list at the end of the class， but I'm already over time。

 so I think I'll just post a top 10 list on the website in the future。

 you've learned a ton of concepts in the course and I know it's sometimes hard to keep track of the overarching narrative but in all of the various connections。

 for example between ID distributions and optimality and all this other stuff but out of time So I would be remiss if I didn't thank Rihi。

 I think you'll agree as a totally killer T， So thanks to Rishi thanks to all of you it's been a lot of fun。

