# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P10：-10-Advanced Algorithms (COMPSCI 224), Lecture 10.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

Okay， I'll get started。

![](img/a697c74e559116fc1ffeb05264bcbc1d_1.png)

So today we're going to。Finish off。More examples of the prim dual method to develop good online algorithms。

嗯。And then hopefully if we have time， we'll start something else， namely approximation out rooms。

Okay， so I promised you last time that we're going to again take another look at ski rental。

So cost of renting。Is $1？Cost of buying。It be dollars and I think you're describinging today， right。

 is that right， okay？うんうん。嗯。And we saw deterministically， you can get a two approximation。I mean。

 two competitive algorithm online。Okay， so now I'm going to show you a randomized algorithm。

 The bound that I'm going to show you is originally， so today。We got a randomized。嗯。

A randomomized algorithm。With competitive ratio。Okay， so the competitive ratio is going to be。

Roughly e over e -1。But to be more precise， it's going to be one plus one over。1 plus1 plus 1 over B。

To the B minus-1。Okay。And as B gets large。嗯。Notice that as when B is large，1 plus1 over B。

To the B is roughly E。Okay。So this is roughly 1 plus 1 over e minus1。

Which implies that this thing is roughly e over e minus1。SB gets large。Okay。

 so this thing is always at least e over E minus-1， but it converges。

 it goes down toward E over E minus1， and the worst case is when b is 1， when b is 1。

 this will give you two。Wenshan。B is certainly at least one。Otherwise。

 you would never bother renting。Okay。So。This bound。Is due to。Carin and others。Carlin et all。

Algorithmmic a 94。But today I'm not going to show you。The result， the way that they did it。

 I'll show you。Today。You will show you will see a primal dual。View。Of。Getting this bound。And this。

So you can see this book。诶。By bookbender an hour。So。They introduced in 05， I mentioned last lecture。

 this primal dual approach of getting good online algorithms。And then they wrote a book。

 I believe in either 07 or'09， I can't remember。That gives this as one example amongst many others。

Okay， so remember that。Remember the model。Okay， so we have a covering LP。

And we see the constraints one at a time， and if the constraintss not satisfied when we see it。

 we have to make an online decision to change some of the variables to satisfy it。

And the variables that throughout time， the variables have to be monotonically non decreasingecreing。

 so let me remind you we did this last time what the LP are， so for ski rental。

 we have the primal LP。Which says minimize。BX plus the sum i from 1 to Kzi。

Okay so ZI tells us whether we rented on the IF Day。

And X tells us whether we've bought the skis and there are K days。Of course。

 we don't know K ahead of time。And there are the constraints。One constraint is that for all days eye。

We had to either rent it or but。And also。X is at least0， and for all I， Z is at least zero。

 so this is a covering LP。And then we have the duall。Okay， so remember in the duall。嗯。

Constraints in the prime alterar into variables in the duall。

And the right hand side and the primal turns into the objective function in the duel。

The thing that you dot product with， so you get Max。Some I from1 to K。Of Y I。

 So you have one variable for every。For every day， such that。Okay。Such that。🤧。

The sum I from 1 to k of Yi is at most B。And also that for all I。呃。

I think zero is less than equal to Y I is less than equal to1。Okay。

So the way we're going to do this is we're going to online build up both the primal and dual solutions。

Okay。And they're both going be we're going to maintain that they're both feasible。

And we're going to say that the objective。呃。Cost on the primal solution we find is not too much bigger than the dual。

 yeah。嗯。Let's see。Right， so for us， as we build this， YI is either going to be zero or1。嗯。So。

Basically， Y I is going to be one for the。WhyI is going to be one for the days where we run。

And then it's going to be。嗯。And then it's going to start being zero。

So it signifies that you rented on that day sort of， but not， I mean。

There are no integrality constraints here。Okay。Yeah， I mean。

 we will see in the next example when we do set cover。We will see that。Well actually。

 not then when we do approximation algorithms and we analyze。A set cover approximation algorithm。

 there will be a more intuitive。Way of thinking about the was。Okay。

So here's going to be our algorithm。Initially。X。呃。All Z， I。And why I。Are zero。Okay。

When we see constraintsstraint， so what are we seeing online， we're seeing these constraints online。

Every day we see a new constraint， x plus ZI is at least one。So when we see constrained I。Online。嗯。

If x is already equal to 1。Do nothing。Okay。Otherwise。We're going to set ZI。To be 1 minus x。

We're going to set x to be。1 plus1 over B。X plus 1 over CB。

C is a constant that I'm going to choose later。And we're going to set Yi。To be one。

So what do we need to understand？We need to understand what's the ratio between the objective functions？

In the primal in the duel。And we also want to ensure that X and Y are both feasible。

Or the primal and the dual solutions are both feasible。So first off。嗯。Let's bound。The primal car。

 the primal。Objective。Over the duel。Objective。Well， in every step of this。

 they either both don't change。Okay。Or。The dual objective changes by one， it increases by one。

And how much does the？How much does the primal objective changed by？So。In every step。

The change in the dual objective。And every stop， okay。Either。Both。Objectives。Don't change。Or。

The change in the dual objective。Exactly equals 1 because we increment Yi by one。And。

The change in the primal objective。Well， what's the change in the primal objective？嗯。It's。B， right。

 there's this B here。😡，B times the change in x。Plus。ZI。And what's this？What's the change in X？

This is B times。The new value of x is。1 plus1 over B。X。Plus 1 over CB。

And the old value of x was just x。And this x cancels that x。So this is so this whole thing。嗯。

This whole thing is。诶。X plus1 over C。And then when you add in ZI， and then let's say this is plus ZI。

When you add in to ZI， remember Z is 1 minus x， so this is 1 plus 1 over C。

So the primal objective over the dual objective is at most1 plus1 over C。

 namely 1 plus1 over C divided by 1。Okay。Good。So now we just need to say that this thing is feasible or that x and y are feasible。

Okay， so let's look at the primal。Now。ZI is just 1 minus x。So exactly that's a tight constraint。

And certainly we never make anything negative。So the primal is seen to be feasible。

How about the dual solution that we're building up？Well。

 definitely all the Y eyes's are between zero and1。

But then there's this constraint that we need to ensure happens。Okay。So。

So primal feasibility is just immediate。And then we have dual feasibility。

We need to ensure that the sum I from 1 to K of Yi。Is at most B？Okay。How many wat how many times？

Do we set Yi to1， while we do that as long as x is less than1。Once x is 1。

 we don't do this else condition。So we just need to make sure that。

We can only be in this else clause B times。We need to show。Can only have。X less than1。

At most B times。Okay。So。Let the increment。To X。On the I day。B X。In other words。

 I mean x is the sum over I of Xi。So x x starts off as 0， then we add some amount x1 to x。

 then some amount x2 to x。So。It's not hard to convince yourself from this formula of that。

First of all， x1 is 1 over CB。And。The X。Are geometric。With ratio。Cub being1 plus one over B。

This implies that。The sum。From。The first day to say the B minus first day。

Of X I is equal to1 over CB。Times the sum。going from sorry to the be Day， I guess。嗯。

I going from let's say J going from0 to b minus1 of Q to the J。Okay。And this is equal to。One over CB。

Times。What's Q1 plus 1。Over B to the B minus1 over。呃。Q minus-1， which is1 over B。Bees cancel。

That B cancels that B。And this is equal to。1 plus 1 over B to the B。Minus1 over C。Okay。

And what did I want？I wanted that after B days， x is going to be1。So now I'll choose C。So。Set C。

Equals。1 plus1 over B to the B。-1。So that's it， we have a1 plus1 over competitive ratio。And。

C is this， which is exactly what I。Promise to you， and now X and Y are both feasible。

And what's the point， the point remember is that。In general， you have that。Any dual solution。

 so let's say。呃。Cost of the dual。Is always at most， let me call that cost of D D for dual。

 is always at most opt of the primal。Is always at most cost of the primal。

Where these are feasible solutions， so across the prime I mean for any feasible solution。Okay。

And we just said that the cost of the primal is at most one plus one over C。Cost of the dual。

So now you can bring this optt over here， this implies。

That the cost of the primal solution we found is at most1 plus1 over C。Times opt of the primal。

So we're 1 plus1 to C competitive。Okay。So。Are we done？

Do I now have a 1 plus1 over competitive algorithm for ski rental？It's not integral。

The ski rental problem says every day。 I mean， what does this mean， Like， I'm every day。

 I'm buying some fraction of the skis and I'm renting some fraction of the skis。

 That's not actually a valid。Ski rental solution， okay。And， you know， as。You in。

I haven't used randomness anywhere， I told you I'm going to give you a randomized algorithm。Okay。

So how are we going to actually get？A valid integral， randomized solution。Well。

 this is the ratio I want。So as you might imagine， what I'm going to do in my randomized algorithm is somehow get this in expectation。

Okay。So。Problem。We can't。Fraactctionally。Rent or buy。On each day。We must be integral。

So the fix is going to be using randomization。And how do we do that？So the randomized algorithm。Okay。

 the randomized algorithm that I'm going to tell you。

Is going actually is going to actually maintain that。Okay， in its memory。

But it's going to do something first。 So the first thing it's going to do is so。Initialize all of X。

zi and Yi to zero as before。But it's also going to。Pick at the very beginning， just a random number。

Uniformly at random。Okay。And。When seeing new constraints。We will update。The X and Z and Yi as before。

 fractionally。Okay。But now we need to choose， Are we going actually rent or buy。

 So we have these fractional solutions lyinging around。 Do we rent or buy。

We buy- so here's going to be the picture。When do we decide to buy？

So I think it's easier to just draw it。So heres。Here's the interval from 0 to 1。

We picked the random alpha。Alpha happened to be here， let's say。And x， remember。

 I defined these x size， these increments that happen。So。No， this is not Chuck。嗯。So first。

 we increment x by some amount x1。Then we increment to buy some other amount me。This is X1 here。

Then we increment by some other amount to x2。Then we then x three。Then。X4。

Remember and x is just the sum of the X's。When do we buy， We buy on the。Day that Alpha landed in。

Okay。So here。We'll buy on day four。🤧。Okay， so now let's analyze our expected cost of doing this。

The expectation of the cost。Well， the cost is just。

The sum of money you spent buying and the money you spent renting。The expectation of。

Money spent buying。Plus， the expectation of money。Spent。Renting。Okay。So this thing here。So now。

The expectation of the money I spent buying。That's just equal to B times the probability that I buy。

And if what's the problem that I buy？Well。let's say x is the sum of the Xi， so x x is right here。

So the probability that I buy is the probability that alpha is less than equal to x。

Which is exactly x。Okay。And what's the expectation of the money spent renting？Well。

 that's by linear expectation， linearity of expectation， that's the sum over I。Of the probability。

You know you can define an indicator random variable for whether or not you rent it on dayI。

And then the total number of days you rented is just the sum of those indicator random variables。

Okay。And the expectation of one of those indicator random variables is just the probability that you bought。

 So this is the sum over eye of the probability that are rented。 Sorry。

 the probability that you rented。On day I。What's the problem that you rented on dayI？Well。Alpha。

Has to be less than。X1， x 2， x1 plus x2 plus dot dot up to X I -1。Okay。So， this is equal to。

The sum over I。嗯。Sorry， sorry， so if alpha is less than that， it means you buy， you don't rent。

So alphafa to not be less than that。So it's 1 minus that。So one minus。1 minus。

X1 plus x2 plus dot dot dot plus X I -1。But this is just what X was at that point in time。

So this is 1 minus x at that point in time， which is exactly ZI。So what do you know。

 our expected cost？Is b times x plus the sum of the ZI？Which is exactly。Did I erase it。

 which is exactly the。Prial objective。 So in expectation， we achieve the primal objective。

OkaySo we get， so now we actually do have our。We actually do have our close to E over e minus1 competitive algorithm。

Questions about that algorithm。Yeah。Yeah， yeah， that's right。Because the way we update X。I mean。

 the way that these Xs are deterministically defined。Once we， once we pick alpha in the beginning。

 we know when we're going to buy。That's right。Any other questions？He looks like。

 give have a questioner。What。嗯。Should it be ex？If we rent it on day I， So let's say。

 So the probability of renting on day I is is one minus probability of buying on day I。

So what's the problem that we buy on dayI， Well， at the beginning of dayI。

 we haven't done the increment to X yet。Yeah。So for example， think of day1。

 day1 x at the beginning of day1， x is still 0。And then we add the increment in dells。else。嗯。

But certainly， even if， I mean， even if you。Even if I somehow M off by one， if you added an X I here。

 that would only。Help you because then you'll be at most CI。Okay。Yeah。

Okay so I want to show you one more example of。A primal dual。Online algorithm。I。

So here I want to look at set cover。And the algorithm。

 the the bound that I'm gonna show you is due to。Alone， our book。Zzar， Binder and Naware。This is。

SyCO 09。诶。So let me refresh everyone's memory and introduce some notation for set cover。

We have a universe， so the problem。Definition。So we have a universe of elements。1 up to n。

And we have M sets。S1 up to SMM。Each one is a subset of the universe。And our goal， and let's also。

our goal here， okay let me write this out our goal。Pick。Sub collectionction。Of the S。

Covering the universe。Their union should cover the universe。

Any questions about the problem definition？So I haven't said anything about online。

 but this is what I mean by Se cover。So what's online about this？

What's online is that so we know that there are these M sets。 in the beginning。

 we know there are M sets S1 up to SMM。But we don't know anything about what they contain。 Okay。

 and online， we see elements。And when we see an element。

The person will tell us which sets contain this element。

And now we have to if we haven't already picked one of those sets into our set cover。

Then we need to choose a set right there and then to cover it。Okayright， so。Me see。Elements online。

And must。Immediately。Cover them。So that's online tech cover。

Who has seen Se cover at some point in their lives？It has not scenes I cover at some point。Okay。So。

who has not seen NP hardness， the notion of NP hardness？I mean， people have seen it beyond in game。

So set cover isn't。An NP hard problem。Meaning that unless there's some。

Huge breakthrough in computer science。 We're not going。

 We don't expect to have a polynomial time algorithm。呃。Okay。For that reason。

I claim that at least if our online algorithm is efficient， you know， we're not going to hope to get。

呃。Oh and further， not only is it NP hard to solve set cover exactly。

But it's even hard to approximate， meaning that if I give you the entire set system in the beginning。

 there's no online here， it's an offline problem， and I say find me the best set cover。

It's hard to find a set cover。That's。 better than a log n approximation of the optimals that cover。

Small， yeah。 so want to find you want to find subset cover that's not worse than alpha times the best in terms of size of sub collectionlection。

So beating alpha being log n is a hard problem。はいそ。Log and approximation。Yeah， what do you mean？

Let just say you have two sets which are will missing one that's better than like having a bunch of。

If you have two sets that are just asking what the optimal okay， so you。

 you must cover all the elements， that's a requirement。 you optimize for number of sets。

Fierer number sets。All right， right， and I guess I didn't say that。Minimize。Number of sets taken。

In your sub collectionction。So if we're efficient online。

 we don't expect to do better than a login competitive ratio。

If otherwise we would have a better offline。Just pretend that the things came online。

 even though they you know。Okay， so。嗯。Will show。Online。log。Log n， times log n。Competitive ratio。ok。

First， I'll show you。I think in both cases， the algorithm will actually be the same。

 but first I'll show you a purely primal view。And we can， and you know。

 we can prove correctness just for this primal view。 but then I'll show you。嗯。

Then I'll show you a primal dual view as well。Okay， good。So let's write。呃。

An LP relaxation for the set cover problem。So primal。

So we're going to have one variable for every set。嗯。🤧坐到 me。So let me just write this M set。

 so we have a collection C of sets。Which is S1 up to SM。Where S I。Is a subset of one to N？Okay， so。

The primal， we're going to have one variable for every set。

 and we want to minimize the number of sets taken， so we want to minimize the sum over s in our collection。

Of X orS。And normally， excess has to be。Either zero or one。

 but we can't enforce integrality in linear programming if you enforce integrality。

 that becomes integer programming， which is NP hard。Okay， you can encode， for example。

 threeAT as an integer program。So what are the constraints， So for every I and N。

 we have a constraint。That says that the sum。Over。S containing I。Of excess has to be at least one。

 and furthermore， x coordinate Y has to be non negative。You could say， you know。

 we could also have a constraint saying X has to be at most one。

 but that's not necessary because no optimal solution would make any X I bigger than one。

It has the primal。There's the duall。Remember， we have one variable for every constraint。

 so we have one variable for every eye， so this is maximized。The sum over I。From one to n of Yi。

And for every variable， we have a constraint。 so for all sets S in the collection。

 we have a constraint which says that。The sum over I in S of Yi is at most one。

And we also have the constraint。That。Why is。At least zero。And对。Yeah。Oh。

 this doesn't matter so at most one again doesn't matter so much because this already sort of enforces that。

Okay， good。So。Just out of curiosity， who here has？Not seen any differential equations。Ever。OhOkay。

 good。Yeah， maybe you thought， you know。Maybe when you learn differential equations， you thought。

 why would I never use diiffy cues。 I'm going into。Field X。Which。Where that doesn't appear。 So this。

 we're gonna use diiffy cues。 Okay， so， but not， not anything too fancy。 You'll see in a second。

So what are we going to do， we're going to maintain as usual。

We're going to maintain primal and dual solutions。And we're going to show that we can get。

Feaible solutions for both where the objectives are not far off from each other。

 this's the usual game。So。The algorithm。Remember， we know。

The thing that's coming online are the elements， okay， not the sets。We know the set。

 So we know that their M of them initialize。X to be 1 over m everywhere。And now what comes online。

One of these constraints comes online， an eye comes in。Okay。And。😊，I might not be covered。Okay。

So if I is not covered， so I'm meaning this constraint is not satisfied。

 So right now I'm not going to show you， I wrote the dual up there。

 but I'm going to show you a purely primal way of looking at things before I go move to the primal duel。

 We're not going to maintain anything about why right now。 Okay， we'll just do work in the primal。

What I'm going to do is。As long。When we see constraint I。Okay， while。Suppose。I is in。Some sets。

SI1 up to SIK or SIR or something。I don't want to use eye twice。SJ1 up to SJR。So。

If if this contraint is really satisfied， we're done， if it's not satisfied while constraint。

Is not satisfied。We'll run。A continuous process。Where。嗯。XS。Changes。According to。呃。Over time。

 imagine like。Imagine that there is some time unit。

And the way that we vary excess with time is that D excess of TDT。Is excess of T。Okay。So。呃。

Run this process。Simultaneously。For。AllAll of these ss SJ1 up to SJR。Until。

The constraint becomes tight。Or until the constraint is satisfied。可以。So the solution to this， I mean。

 this is the we're not doing any fancy different cues。

 The solution to this differential equation is just E to the T。Okay， after tea the time stepsps。

 you become eat the tea。But so。嗯。After。Excess evolves。For T time steps。It multiplicatively。Increases。

By E to a T factor。Okay， I could have just said。Multiply all of these by E to the tea for the smallest tea。

 which satisfies。The constraint。But there are some fancier examples of covering LPs where。呃。Well。

 first of all， I mean， this time thing is gonna， you'll see in the analysis。 this。

 this view of things running for continuous time is gonna。You know。

 helpp us understand what's happening。Okay， so now。Definitely， definitelyly the。

 the primal solution we end up with。 I haven't said anything about the dual。

 The primal solution we end up with at the end of everything is feasible， right， because we run。

 we run this for time until it's actually satisfied。

 So everything is satisfied and everything ever becomes negative。The question is just。

 how can we argue that our competitive ratio is not that bad？So。I want to compare to opt somehow。So。

This constraint is not satisfied。But Opt is satisfying this constraint。Right so in particular。

And which sets are we incrementing？We're incrementing the excesses which which contain I。

One of those has to be an opts solution。Right。So every time we run this continuous time process。

We're incrementing， we're evolving someone who's inoc。Whenever。We run this evolution。

Some set in optt。Is increasing。Now if you particular focus on one particular set and opt。

How long how many time， how many seconds can it or time steps can it evolve。In this process。

So what all the excesses start at 1 over M？😡，And we would never bother evolving anything unless a constraint was not satisfied。

Right？So the fact that the constraint is satisfied， Oh， maybe I should， maybe I should also say this。

 Yeah， So if a constraint is not satisfied。Right。It means that that set opt is less than one。😡，Okay。

 so how many time steps can any set in optt be evolved for？Natural log of M。No， set an opt。Evolves。

For longer。Then Law and M seconds。Right。So the total number of seconds that。

Wherever in this evolution phase is at most Op times La M。

Like over the entire course of the algorithm。So the algorithm。Runs。This process。For， at most， opt。

Times longm。Seconds。Right， that's all nice。But what is the amount of time？That we run。

Have anything to do with being good compared to optt？Well。What's。

The derivative of the primal objective。As a function of time。With respect to time。Okay。收。

The only part of the primal object， so this is equal to the derivative of XS J1 plus plus XSJR。Dt。

Right。Because the other variables aren't changing。What do I know about this sum during the evolution？

😡，I'm evolving because the constraint is not satisfied。So what does that mean？Yeah， it's at most one。

 This sum is at most one。Right， so first， the derivative of this with respect to time is exactly according to our differential equation。

 It's exactly S， X J1。Of T plus dot do dot plus X， S JR。Of tea。But this is at most one。

It's less than one。 Otherwise， we wouldn't have bothered。Evolving。Okay。Now。

 the objective starts off at one。😡，It starts off- so x starts off as1 over I everywhere。

So our primal objective starts off as one。And the way that it changes over time is every time unit it increments by at most one。

It increments by most one in every time unit， and it only runs for opt times long time units。

So that implies。At the end of all the algorithm。The primal objective。Is that most opt？Times lawn M。

Okay。So we have a lot M。R long I'm competitive。Or are we。Again， it's not integral。Okay， so yes。But。

Yeah， it's better。对 yeah。😊，Yeah。In fact， I should say that in that paper。

 they show that not only can you achieve this。But you cannot achieve better by more than log log factors。

So that's up to log log。 that's basically the right answer。Yeah， so I guess， yeah， again。

 if you're looking for final projects， you can investigate this removal of a log log。

I think there's a gap of log log， but。Yeah， okay， so again。We have the same problem。

This is not an integral。Solution， you know， we have to at every time step。

 we have to actually take some set。One of the x's has to actually be set to one。

 we can't just keep them as fractions。So before I fix that。

You know I want to give a primal dual view。Actually， I should investigate。

 I should check that paper more carefully。 this paper came out。

 the conference version came out before。They came out in '03。

 which is before Bookbinnder and Naor did the whole prim old dual view of online。Algorithms。

 so I didn't actually， I didn't actually read the paper， but I think。

They only did this primal view of things， they didn't do the primal dual view。I think， I mean。

 otherwise the time doesn't make sense， so let me show you the primal dual view。So， this is。

This is all the purely primal view， we never talked about the duel。So how about the primal dual view？

Okay， so we'll maintain。The excesses as before。Okay。🤧。But we also want to maintain why， so why。

Is initially set to zero。And as。We。Run evolution。To satisfy the I constraint。We also。Evolve。Y I。

 according to。The differential equation DYi of T DT is one。In other words。

 every second YI goes up by one。Okay。So already we see that。Already， we see that。

The primal objective in every time step is going up by at most one。The dual objective。

RightThe dual objective is just the sum of the Y I is the dual objective in every time step is going up by exactly one。

 This already tells us that。嗯。At the end of the day， when we get our x's and Y's。

 are primal and dual solutions。The cost of x is at most the cost of y。

The primal cost of x is at most the primal cost of y。Now。That's how something is a little off。

 it sounds like right， because the primal is feasible and the dual were feasible and the primal is at most the due。

Well we know that the dual is always at most the primal， that would just say primal equals due。

 which says we got the optimal thing。So the catch is that this duel is not going to be feasible。

But what we're going to show is that if we scale the dual down。By log M， roughly。

Then it would be feasible。Again， that's going to be good enough。So x， just like before is feasible。😡。

We already talked about that， x is feasible。So a claim。Is that if you take y and entry Y。

 you just divide by log M。That's dual feasible。Feaasable for the dual program。Okay， proof。I mean。

 basically， what does that mean we need to show。Need to show。That for all S。In the collection。

The sum over I and S of Yi is at most long M。I mean， we need to show that this constraint is。Is only。

Unsatisfied by a law and M factor。And that would give it to us。Well why is that the case？Well。

Let's focus on a particular set S。😡，好。Now。Look at this sum。

 If some Yi is being increased in this sum。We're also simultaneously increasing excess。

For every S that contains I。So whenever this sum is increasing。We know。That excess is increasing。

But we already talked about this， how long can excessS possibly increase？Law M seconds， right。

 because then it becomes one。 and then we would never run the evolution again。So that's it。

Whenever sum of Yi。INS increases。嗯。We know。Exccess is increasing。

And this is increasing at a rate of exactly one at every time step。So after Law M time steps。

 this is exactly Law M。We know excess is increasing。An excess。Can only increase。

At most lawn M time steps。So that implies that。Some over I and S。Y I is that most line。

So if you divide by1 and M， it's feasible。So's what we just showed。We just showed that， again。

 the cost。Of， the cost of y over line M。Is that most the dual cost， is that most opt of the primal？

Is that most？The cost of the primal on x。And which we know is at most the cost and the duall of why。

Right， and this is。This cost is linear， so this is just1 over La M。Times the cost of y。

So that implies exactly what we want， that implies that just bring this opt over here。

That implies that， the primal cost of this x that we found is at most La M times optt。Okay， great。So。

 I mean， we didn't do anything different。 We， Well， I mean， we didn't get anything new。

 We just saw a primal dual way of looking at it。 in the purely primal way we compared directly with opt。

In the primal dual way， we never really talked about what Opt was， we just built a dual solution。

Okay， so now。Let's talk about actually fixing。This thing。So。Kind of the first attempt is。

The first attempt。So first let me write。Yeah。Getting an integral solution。So the first attempt。

Would just be。At the very beginning。For each。S in the collection。Pick。Uniformally random。Alpha sub S。

In zero to one。Once x of S。Is bigger than alpha S。 So maintain the fractional solution just like we were doing。

 once that fractional solution on S is bigger than alphas sub S。Take。Take it into the collection。

 take S。Into。Our solution。Just to be clear。That doesn't mean we set X， S to1。

 we're going to keep the fractional solution running just as it ran before。Just on the side。

 we're going to maintain the sets that we're actually going to output。Okay。

So when we decide to take S into the solution， that means we're going to output S as being one of our sets。

 but we're still keeping X of S the fraction that it was before。Okay， so that we can still say。

We can still say that our fractional solution is giving the same cost as it was before。Okay， so。我。

One thing you can show， which is basically the same thing we did last time is that。The expected cost。

Of this integral solution。Is。The cost。Of the fractional solution。

I'm not going to do that computation but。It's。Roughly the same as what we did before with ski rental。

But there's a problem， what's the problem？啊。Might not be feasible， exactly。Okay。Eite with ski rental。

If we， if we didn't randomly decide to buy， we were always renting anyway。

 So we're always feasible here， if we mess up and we don't actually take it into the solution， then。

That element is not covered， and this might not be feasible。In their sequence。And so what's the fix？

So for this fix， I'm going to。嗯。I'll assume that you at least know N。 you don't。

 you can actually remove this assumption。Maybe I'll put it as a homework thing， I don't know。

 or maybe I'll put in into notes。But let's say you know N。

 you just don't know what's contained in what。So the fix is， so what's what's really going on here。

 So we know from the primal feasibility that。So view these。

 view excess as now being the probability that we actually put S into our solution。Right。

So this sum is like view it as the number of the amount the point I is covered。😡。

The number of times I is covered。 What this is saying is that。

The expected number of times I is covered should be at least one。Okay。

But if you and then if you randomly put things into the set with this， with this probability。

 then there's unfortunately some good chance that you won't actually cover it。

So the trick is just to boost it。 So rather than say。

Rather than have it be that the expected number of times we cover the element is one。

 make the expected time number of times we cover the element log n。Okay， so。The fixes。嗯。Once。

Xs is bigger than equal to alpha S over some big constant times log n。Then。Take S into the solution。

You look troubled。Re trouble。No。There's still some。Yeah， there is。 This is going to be small。Okay。嗯。

Wait， wait， is that really what I want to do？No， no， no， no， sorry， is not。

 this is not what I want to do。 It's a good thing you're troubled。 You should have been troubled。

Yeah， I sensed。A sense。唉。Okay， so。So this is the actual fix。For each us。We will pick。Alpha S1。

 Al S2 up to alpha S。Or。In 01。Uniformly at random。And also independently。

And also R will be some big constant times long n。Okay。And then。If excess。I's bigger than equal to。

Alpha S。J for any J。Then put。Put S into。Our solution。Okay。对。So now our expected cost。

Increases by at most an R factor。Which is why we get， I don't know if I erased it。

 which is why we get a log n times log M competitive ratio an R times log M competitive ratio。

And if you look at any element。The probability that its constraint is not satisfied for any one of them。

 Let's say that the probability that its constraint is not satisfied due to alpha S1。

Is that most some constant half or something？So the probability that none of them satisfied it is exponentially small in R。

Which is one over polyang。So by a union bound， they'll all be satisfied。 There are only n of them。

 right。 So if the failure probability is one to the end， then。By union bound。

 our failure probability of not being feasible is wheneverpoan。So that's it。Yeah。Yeah。嗯。

Wait Sa again。でく。あり。还る。Okay， so one thing that's worrying about me about this like deterministic rounding without- so I mean。

 are you going to lose a log in in what you're doing？Okay， so， so one thing about。

One thing about set cover is for the offline problem。

One way to solve One way to get a good algorithm for set cover is did I erase the primal already。

 Maybe I erasse the primal。 You solve the primal。That gives you probabilities for each set。

And then you round up， then you take the set with probability equal to x of S。Okay。

 that gives you your randomized algorithm for set cover。

And you run into the same issue that it might not be feasible， so you blow things up by this login。

OkaySo for set cover， we know there's a proof that you cannot beat a log n approximation unless I think unless P equals NP。

Okay， so。yeah， so that's why I'm a little cautious about deterministic rounding。

 which doesn't lose anything。Okay， so I have about 10 minutes left。

I guess I'll set things up for next time。 So we're done with primal dual online algorithms。

 And I want to move into a new but related topic， so。So， the next。Topic。Is approximation algorithms。

So what's that all about？So the basic gist of things。Is we have。Sub。呃。Optimization problem。

We want to minimize or maximize something， for example， set cover。喂。And now we're not online anymore。

 this is all offline， okay。So we're all offline now。

And the best known algorithm for solving this optimization problem is slow。Okay。

 so maybe the problem is NP P hard and the best algorithms we have are exponential time。

 Or maybe we do have a polynoial time algorithm， but it runs in time end of the 10th or something。

 Okay， so the best， the best known algorithms are， are slow。

So maybe the problem is going' to be hard。Okay， so and that's actually this is the one we're going to focus the most on Pro algorithm for NPR problems。

And。We would like to give。A fast algorithm， or at least not as slow as the one as this exact algorithm。

Which。Gets a cost that's guaranteed to be within some small factor the best cost。We want。

An algorithm。A fast algorithm， I should say， a fast algorithm。Which produces。Solution。With cost。

At most， let's say some alpha times opt。Where alpha is hopefully small。

 this is for a minimization problem。If our optimization problem is a maxim problem。

 then we would like to find a solution that has a value at least you know。

 at least alpha times opt alpha is less than1。At least half of opt or something。And。🤧。うん。So。Since。

Since we were just doing primal dual with online algorithms。嗯。You know， I will。 I'll start off with。

 with an example here of using the primal dual method to get good approximation algorithms。

 So we're not online anymore。 We're offline， but we can still use the method。 And， in fact。

 primal dual。The primal dual method for approximation algorithms is much older than the primal dual method for。

Online algorithms， at least the thing I'm going to show you now is from the 70s。

So if you want to see more about approximation algorithms。I mean， you know， you can see this book。

 there's a book on approximation algorithms by。VJ Varai， it's called approximation algorithms。So。

So this class is a kind of a broad advanced algorithms class。 I'm not going。

There are classes that exist in the world where all they do in the entire semester is approximation algorithms。

But as you've already seen， that's not going to happen here。But I will talk a little bit about it。

Okay， so let's look back at set cover。Okay， so。Now we know all the sets， we know the universe。

 we know which sets contain what elements， we just need to get the best。

 the smallest sub collectionction of sets。And I'll even give them costs。Sets。Set us。Has some cost。Cs。

Want。To minimize。The sum over S chosen。Of C sub S。While。Covering the whole universe。

So before CCSs were all one。Okay， so。Let look at this primal duel。Proron a little approach。So。

 I think。So for people who took CS124 with me， and I think even when Professor Misonmaer taught it。

 I think he did set cover。If the CSs are all1， there's this greedy algorithm。 I mean。

 you can run the greedy algorithm for other CSs where at every step。

As long as there is an element that hasn't been covered yet。You choose the set。

 which covers the most。Uncovered elements so far。Okay， so there's a corresponding greedy algorithm。

 which I'll tell you very soon。For， the one with costs， but so what's the primal。

 the primal is minimize the sum overall sets S of CS times XS。

 XS tells us whether or not we took the set。Subject to the constraint that for all I。In the universe。

The sum of x of s for S containing I is at least1 and x is at least zero everywhere。And the duall。

We have a variable for every constraint。So max， the sum over。I from1 to N。うん。Of why shall I。

Such that。For all sets in the collection。The sum of I in that set of y sub I is at most the cost。

And also， Y is not negative everywhere。🤧Okay， so what's。What's the greedy algorithm？As long。

As there exists。An uncovered element。We will put。S。Into our solution。Such that。S minimizes。

The ratio between its cost versus the number of elements that it covers。The number of new elements。

S colors。Right， so this is exactly the generalization of the。Of the greedy algorithm。

 when the costs are one。🤧。So let's do， I think I have time to actually do。

The analysis of this because it's very short。So。Let's do a primal duel。Analysis。So。Initially。

X and y are equal to0。When we take some set。Some set S。That means we set X to be 1。And。

We're also going to set。And also， for each。Newly covered。For each newly covered INS。Will set。

OopWe'll set Yi。To be。The cost of S over。嗯。The number of newly。Covered。Elements。At this point。Okay。

When we take a set S， we set X S to be 1。Which means we just increased。

The primal objective by the cost of S。And for all the newly covered we basically make the YI share this cost。

😡，So for each newly covered element， we set itss Y I to be the cost of S over the number of them。

 which means they share it， which means that。The primal and dual costs。😡。

Are exactly the same in these solutions we're building。So the primal and dual costs are equal。Now。

 the primal is obviously。Feaible。But the duel will not be feasible。Okay。

 we're going to see that next time。This dual， you know。

 the dual constraint is that this sum has be at most C S。But just as before。

 we everyone these constraints is going to violate this by most a certain multiplicative factor。

Which is going to be log in， by the way。So therefore， when we scale down。

 we will get a feasible solution， and that will tell us that this greedy algorithm is a log in approximation。

Okay。So by the way， this approach of violating the dual feasibility and then scaling down。Okay。

 that's called dual fitting。 maybe if you want to know。

If you want to know a name to Google in your future。This is called dual fitting。This art of。

Of violating feasibility and scaling down， O， so。That's it。 remember PSet three is due。

 I think Monday night。