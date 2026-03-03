# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p12 -12-Lecture 12_ Applications of Multiplicative Weights to Games and LPs).zh_en -BV14CAUeUEPj_p12-

So this is going to be one of those lectures where I tie together a bunch of the themes that we've been discussing。

 both to sort of reinforce the concepts， but also expose you to the connections between them。

So we're going to talk more about multiplicative weights and in particular we're going to use it as a black box to derive various interesting algorithms and results we're going to talk a little bit more about zero sum games we're also going to talk about linear programming then next week we'll start kind of traditional introduction to online algorithms so we it multiative weights as an online algorithm it solve as the online decision making problem where the reward vectors come in online one by one other than that we're actually not going to really focus on the online aspect today we're going to focus more on applications which are even interesting offline like linear programs。

So last lecture we covered multipl of weights， so it's a very simple algorithm。

So we're not going to actually need the code of the algorithm today。

 so it's okay if you don't remember exactly what the update rule is。

 but I do want you to sort of remember you know that it was some super simple algorithm。

 which was very lightweight and easy to implement that much you should remember so you can look it up if you need it。

The analysis was not that easy， but we went through it and now we're just going to use it as a black box。

 so let me tell you what we remind you what we proved。On Tuesday。

 so an adversary picks these reward vectors， so there's some set of actions。

That you're allowed to pick。Actually， this should be minus11。

And each day you commit to a distribution over actions using this multiple of weights algorithm that an adversary produces a reward vector with all the rewards between one and minus1。

 you want to have the biggest sum of rewards that you can and remember the benchmark we use is the best fixed action in hindsight。

So we look at the best actions summed over all time periods of what reward you could have got。

 had you always played that action every single day。And the guarantee is that the expected。

 so the expectation is over the coin flips in multiple of weights， it's a randomized algorithm。

So the expected reward earn earned by multiple weights is as good as this benchmark up to an error term that grows sublineniarily in the time horizon capital T。

So we proved that last time。For today's applications。

 I'm going to need some sort of very minor extensions of this guarantee。

 So let me tell you two sort of very simple extensions。So first of all。

If we think about this for a second， the multiple weights algorithm doesn't just have a guarantee with respect to every fixed action in hindsight。

 it also has exactly the same guarantee with respect to every mixed strategy over actions in hindsight。

So if I gave you， so right now I'm sort of doing the counterfactual。

 Well what if I just always played action 1， What if I just always played action2。

 What if I just always played action 3， So I could give you the more seemingly more general counterfactual where you could say。

 what if I always play 60% on one and 40% on two， What if I always play 20% on2 and 80% on four etcter。

Okay， so this guarantee immediately implies。The guarantee for probability distributions。So notes。

For any distribution。Or mixed strategy P。Over the actions， it's actually true。

That the expected reward of multiplicative weights。

Well actually let me just write it this way I mean the upshot is is you know in hindsight。

 there's no reason to randomize in hindsight you may as well just play a best action that's the best you can do So why is that we'll think about any fixed distribution。

And imagine every day you mixed， you chose an action according to this distribution P。Then on day T。

What would be your expected reward？Well we look at each of the actions。

 we look at the probability that you play that action and we look at what you would have gotten on that day if you wound up randomly picking action A。

that's what you would have gotten and had you played the next Str P every day。So if we just。

Some in the other direction。You start seeing what I mean that there' in hindsight。

 there's no reason to do anything other than just play a fixed action。Because right， for each term。

 for each A， this is。At most， the best action。So this is just saying for some action A。

 what would you get if you played a day day after day after day？And by definition。

 that's at most the maximum over those same quantities。

So we just upper bound this by the best fixed action in hindsight。 This is a probably a distribution。

 So it sums to one。 And so we're just left with。No better than Max over A。Some。Takeick going the tea。

rTA。Okay。So again， I mean， I'm not saying anything deep here， I'm just saying that you know。

 because in hindsight fixed actions are the best things， if you want。

 you can interpret the multipllicative weight guarantee is also being good against any fixed mixed strategy but it turns out that's a convenient form to plug into our applications。

So clear on that， I hope that's straightforward。Okay。

So let me also remind you then about a second way of stating the multiple weights guarantee。

So sort of an interpretation and this is the form in which we're going to apply it in today's lecture so here we say。

 okay， well how do we know how to think about this error term you know minus2 square root t log n and so the suggestion is well let's think about it time averaged meaning we divide through by capital T so then that becomes root log n over root T so that's the sort of per step regret that we're suffering。

And then we asked the question， if we had some target per step regret epsilon。

 how many days would we have to play this game before time the per time step regret had dropped to Epsilon or below？

And so phrase that way。This is equivalent to saying。Once we've played a game。

At least four log n over epsilon squared time steps。Then。The time average regrets。Is it most epsil？

Yeah。And so again， how do you get that， you just divide this thing by T and then you ask what does t have to be between before2 square root log n over t becomes less than epsilon and it's four log n over epsilon squared And again。

 I mean， I want to emphasize this is like really good we don't see a lot of stuff which is logarithmic and kind of the input size。

 but here that convergeenceul of weights， even though you have n actions a sort of logarithmic and the number of actions。

 So just notice， you know， you will not have played very many actions by the time this algorithm stops right if you think of epsilon as being not too small So you just randomly sampling an action each day。

You're going to terminate within the logarithmic number of days and you have n actions。

 so you have played a vanishingly small fraction of the actions。 Okay， while you've done it。

 So it's really very fast。And that's one of the reasons why multi of weights has a lot of applications because of that logarithmic only dependence on the number of actions。

Okay。So。Here's the other simple extension， which we'll also use。

So we've been making the assumption that the rewards are bounded between minus1 and 1。

And I said that's without loss of generality by scaling， which is true。

 but actually you have to think a little bit about what effect that scaling has on the convergence rate。

So and in our applications， we're going to want to allow， we're going to work with rewards。

 which are not necessarily minus11。So suppose the rewards are in minus M。Okay。

For some possibly big number M。And now suppose we again wanted to get per time step regret at most epsilon。

So how do we do it， well we do it just by reducing the previous case。

 we're just going to scale the rewards。Run our old algorithm in hereit the old guarantee and then scale back up to the original setting。

 Okay， So one thing we got to like remember is that if we're going to scale down by capital M。

 And after we scale back up， we want regret only epsilon。After we've scaled down。

 we need to make sure we have regret a most epsilon over M so that when we scale back up。

 it's the most epsilon。So。To get。And most epsilon。Scale all rewards down by him。

So now they lie in minus11， so we can just run our old algorithm on these scale down rewards。

We run multiplicative weights on the scaled costs， scaled rewards， excuse me。So the average regret。

Is the most epsilon over M。And then you scale back up。Okay。

So we're just to how many iterations does it take， It's just the number of iterations our old multiple of weights took to get down to this per time step regret。

 So that just means we pick up an extra m squared in the number of iterations。

So I'm just substituting epsilon over M for Epsilon on the upper right board。

So m squared over epsilon squared log n。Alternatively， you know。

 one way to think about the scaling is you could just kind of modify the multiplulative update。

 weight update rule so that it scales inside。 So alternatively， if you prefer， you can think about。

The scaled version of multiplicative weights where。At every time step。

 remember the weight of an action evolves from time t to t plus1。

So it's its old weight times some multiplicative update。Yesterday we had one plus ata。

 the reward of a at time T， so instead you you use one plus ata over M times the reward of time T。

Okay。So this if you like， you can just sort of work directly with the original rewards and just use this update step instead。

 and that's going to be equivalent。Okay。any questions about those extensions？

So we can compete with all fixed mix strategy distributions， and it's not a big deal。

 If the rewards are big， we just have to be sensitive to the fact that our convergence time is quadratic and are bound on the rewards。

All right， what is it going to do next？Okay。So questions。Anything clear？Yep。Yep， yep。

for like identifying something or some sort of problem like that that we're actually getting better at。

On average， yeah， on on given， there'll be some time steps where it didn't work out so well。

 But as far as， and again， I mean， you should always remember。

 we're comparing ourselves to the best fixed thing we could have done。 But absolutely， I mean。

 if there's some fixed thing， which is good。Then we're converging closer and closer to that in average performance over time。

Which is great。啊。健方。What's the meaning of that。Cl our as。老板。So the claim is， so this。

 this is the number of iteration。 So if rewards are between minus M and M and you want to get down to a time average regret of at most epsilon。

Then it's going to be M squared over epsilon squared time to log in iterations。

 That'll be sufficient。Oh yeah， yes。Thank you。It's still the four。Other questions？Yep。

What on earth is that？So sorry。This is my Ada slash3。So previously the update rule didn't have the M。

It was just  one plus eight of times the reward。 remember the reward can be positive and negative so the weight could go up or down。

 and now I'm just slowing down how rapidly the weights evolve。

We're not going to ever need this in today's lecture。 Okay。

 so we're just going to be applying this guarantee is a black box。greaterer than。No。

 so I want to know how many are sufficient。Oh， I see what you're saying。

 So I guess what I'm saying is within at most for epsilon squared overps4 m squared of epsilon squared log。

 you'll get down to within epsilon。 So it's guaranteed by that number。 Maybe it happens faster。

 but you're right。I mean， I mean， your question is a good one， I mean。

 maybe a more natural way of saying it is to guarantee at most epsilon run for that many or more iterations。

 so absolutely。So it depends on your interpretation。Other questions？Okay， good。

 then let's talk about some applications of this。So I want to say a little bit more about the Minmax theorem。

So consider a zero sum game。Think of the payoffs between one and minus one。

 although you could scale if you wanted。So I showed you the miniax theorem a week ago。

 which says that in a zero sum game， it doesn't matter which player goes first as long as they both play optimally。

 then you get the same expected payoff either way， sort of very quickly at the end of last lecture I sort of sketched how you could derive this from note from the Multi of weights algorithm。

 I'll put some details on that in exercise set 6， which I'll post in a couple of days。

And so I want to talk about a different setup than last time。

 so last time we were thinking about both players independently playing multiple weights。

Now we're going to have the players play in different ways。

So they're still going to play for capital T time steps。

 which is what's needed to get down to Epsilon regret。

 but only the row player will be using multiplative weights。

So the row player picks a distribution of a rose。Using a copy of multiple weights algorithm。

 so multiple weights outputs a distribution， so that totally makes sense。And then actually。

 we're going to make this game more unfair for the row player than we did last time right so last time we envisioned the row and column player going simultaneously。

 each using their own private copy of multiple weights to pick an action at random。

 today we're going to let the row player go we're going to force the row player to go first so the row player has to announce its mixed strategy over the rows。

 the multiple weights recommends。 and then we allow the column player to do whatever it wants afterwards。

 knowing that So in other words， we allow the column player to best respond to pick the column with the best expect to payoff。

 given the mixed strategy played by the row player。It's the column player。Response optimally。

And me remind you something that we saw last lecture， or maybe the lecture before。

 which was that if you go second， there's no reason to randomize。

So if you know what your opponent's doing first， you can just look at the expected payoff of each of your actions and play the best of them deterministically。

 so that's how we're going to think about the column player act deterministically。Okay。Now。

 I can't be done because this still isn't well definedfined Multi of weights is happy to recommend to you strategies and mixed strategies。

 but you need to feed it as input reward vectors。 So the question is， you know， the row player。

 what is it going to be feeding its copy of multiple of weights at each time step And here we use basically the same idea as last time。

 which is you know after the fact after the play at day T。

 the row player finds out what column the column player chose and then just looks at the induced reward vector。

 So what payoff the row player would have gotten in hindsight for each of the rows it could have played。

 given what the column player played at time T。So by the way， I'm going to call。

Call this deterministic column strategy Q sub T。Okay。So if QT consists of choosing column J。

When we set。For the purposes of keeping multiple ways happy。The reward of row I。

 just as the payoff that the row player gets when the row player plays row I and the column player plays row J。

 right， this is exactly the payoff that the row player would have gotten at time T had it played row I。

 given what the column player did at time T。All right， so is the setup clear？So again。

 it's the same kind of thought experiment we were doing last time。

 the twist is that we have this asymmetry in the column player。

 sometimes we've skewed it in favor of the column player by forcing the row player to go first。

So it turns out this has sort of more direct algorithmic implications， this version of it。

 as we'll see。All right， so what I want to claim about this。

So the claim is that just like in the double multited weights thought experiment last time。

Both players are going to get expected payoff close to the miniax value。Actually， you know。

 the first thing I'll just talk through， but maybe think about while I eraed the board， I mean。

 the column player is pretty happy in this game， actually okay。

So the column player is actually definitely going to get。

 there's not going to be an epsilon for the column player。

 column player will get at least its minimum max value， if not better。

Because remember the miniax value， you know there's different ways of thinking about it。

 but you know that's kind of how well the column player would do if， for example。

 it had to go first and commit and then the row player would respond Certainly you're much happier to just kind of get to respond second and not only that gets to respond differently on different days to tailor your response on dayT to exactly what the row player did on dayT。

That's kind of best case scenario for the columnlin player。So claim one。Colllin player。

Gets its miniax。And let me write it this way。Max X。M Y X transpose， I should use P's and Q's。

 I guess。P transpose a Q。If not better。Okay。Yeah。knowThis seems like we have feedback between。

Cice of maximum weight strategy and then player two。

 and I have to repeat them the weights back to the strategy to get new weights。

 and that might change the strategy。Can you say that again？

So like how do we know that there's sort of a fixed point？😔，Between column。

While you're choosing because those call first choose your initial strategy the best thing to do。

 but then that changes the reward vector right， So how do we know there's like an equilibrium between the two。

 There's like a fixed point。 Yeah， good question。 There's no claim that there's a fixed point。

 There's no claim that there's an equilibrium。No， I claim this as well defined。

 as a thought experiment or as an algorithm if you like。

 so the order of operations is the row player goes first， knows only the first t minus-1 steps。

 knows what both players did in the previous t -1 steps， it picks a distribution。

We tell the column player now the row player's distribution at AT。

So then the column player has the information to do a best response for dayT。Then。

 and then that happens， Okay， that's actually the outcome at time T。

And now the row player sort of just as time T is ending and time Tless one is beginning。So， okay。

 given that the column player in the past played this column at day T。

 here's how I'm going to define the reward vector that I'm going feed in the multipl of weights。

 So again， remember， the reward vector is sort of fictitious here。 I mean， I mean。

 the whole multiplude of weights thing is kind of fictitious。

 We just sort of made it up and to keep it happy。 We're feeding it reward vectors。

 which are themselves fictitious。 Now， obviously， they're derived from the payoff matrix。

 But it's not， you know， I mean， the players really get the payoffs from the payoff matrix。 And。

 you know， the multi of weights is just a way for the row player to kind of have a disciplined way of hedging between the actions。

😊，Does it makes sense？Other questions？All right。So this， if you。

 if you can sort of keep everything straight， this should actually be kind of selfevi。 Okay。

 so I guess first， first， in some ways， I'm gonna write down this proof is if we didn't already know the min Max theorem is true。

 Now， we know it's true。 fine。 So we know it doesn't really matter which direction this max or this min is in。

 Okay， we know that。 But， you know， just to prove the strongest statement。

 I've written this in the way that's the best possible benchmark for the column player。

Right so the column player is going to be better off if it gets to go second。 Remember。

 the column player is the minimizer。 So this says make the row player go first。

 then the column player best responds， and then we get the we get this expected payoff。

So this is the best case for the column player and it does at least as well as this in the thought experiment。

 why because in the thought experiment， the row player again has to go first。

 and then every single day the column player gets to choose whatever cue it it wants to in response to PT。

So in other words， on each of the capital T days， the column player will get this payoff or better so therefore time averaged over the date over the T days。

 it also gets this or better。So that's easy enough， Colinberg gets to go second。

 so of course it's doing well， so no epsilon， nothing about epsilon regret here。So claim two。

As the row player， despite its disadvantage， actually gets with an epsilon of its miniax value。Okay。

This real player gets its miniax。And again， let me write it in the way where it makes it look like the strongest statement。

So let's think about the version where the column player goes first。

And then the row player goes second。So in some sense。

 a row player who doesn't know the Min Max value wants to use this as its benchmark。

 right This is the happier case where it gets to go second。

 and the claim is in this thought experiment where it's forced to go first。

 actually it gets this up to epsilon。O。When I say gets this， what I mean is， okay。

 so they play the game capital T days。Each of those days， the row player gets some payoff。

 And I'm looking at the time average of all of its payoffs over the capital T days。

 Okay So the claim is that's with an epsilon of the Minmax value of the zero sum game。Okay。All right。

 so this one requires a proof， although it's not hard and it resembles things you've seen in the past。

All right， so by definition， what is the time average payoff of the row player。

 so we average over the days on day little T。So again， that's a day T， that's a transpose。

 that's a time horizon。So by definition， this is the row player time averaged payoff。

That's just what it is。All right。Now we're going to use the fact that the row player generated the PTs using the multiplepl of weights algorithm。

So what's the guarantee， the guarantee says given the column player selections， the QTs。

The row player did up to Epsilon just as well as if it played any single fixed action every single day。

 But actually， we have our extension， right， So not only does it do as well as any fixed action。

 it does at least as well as if it picked some fixed mixed strategy and mixed in that exact same way every single day。

That's what the regret guarantee gives us。So。For every。Fixed mixed strategy distribution。

Up to Epsilon， we're doing as well。As if we just always randomized according to P。

And the column players still did what it did。Okay。That's actually， I mean。

 the rest will just follow easily。 So this is sort of the key point。

 So this is where we use the multiude of weights guarantee as a black box to derive this fact。 Okay。

 So any questions about that。This is just what it means to be doing at least as well in hindsight as the best mixed strategy。

O。Good， so now we're going to repeat a trick from last time。 So now， you know， P is just fixed。

 independent of the day little T A is fixed。 So the only thing here in this sum。

 which depends on the index， which depends on little T， is the column chosen by the column player。

 Okay， so we can take the P transpose a out。Just some then we just got the average of the QTs。

 or put differently is's going to correspond to the uniform distribution over every column that the column player ever played in this game。

So this is just equal to。Max over P， P transpose A。Cew hat where I'm defining Q hats。

To be the average column played by the column player。Again， remember， these QTs are deterministic。

 right so the column player always chooses just one column， so this is really just saying。

 you the uniform distribution over the columns that were ever played。Okay。So this is an equation。

 okay， this is just averaging over the cu's。And now of course。

 if I throw in if instead of a fixed Q hat， so remember with the in the Min Max guarantee。

 you're sort of thinking of the other players playing optimally。Q hat， know。

 the worst cases is optimal。 Maybe it's even worse than optimal for the column players。

 So the row player will do better。 In any case， obviously， if I just throw in an extra min here。

 this one will go down。So again， there's an epsilon here， there's a minus epsilon here。看。

And so that's it。So that's the proof of claim too。So any questions about that？

So just like at the end of last lecture， this gives us yet another proof of the Minmax theorem。Why。

 well， so we have the row player， we have the column player。

The column player gets at least what it would get if it got to go second and the row player went first。

Claim two says the row player gets with an epsilon。

At least what it would get if it got to go second and the column player was forced to go first。 O。

 so each player does as well as it could in the favorable scenario for it up to epsilon。

So letting epsilon go to zero， we conclude that the only possibility is that actually。

 it doesn't matter who goes first， and in this case both of their expected payoff converges to this min max value as epsilon goes to zero。

All right。So that wasn't the main point， the main point of doing this wasn't to give you yet another proof of the Minm Max theorem。

 and the main point of this is to get some algorithmic applications。

 but it's worth noting that this also gives us a proof of the Minmax theorem。All right。

 so any questions about that。 So that's what I wanted to say today about gains。

 Now I want to talk about applying。Sort of this thought experiment。

 the miniax thought experiment to solving linear programs。 any questions before that？

I meant to switch these。Actually， it's nice having that up。Okay。

So's another the next thing I want to revisit。Is a problem I introduced you to back in our very first linear programming lecture。

 and I was showing you that lots of different problems reduced to linear programming。

 So one of our examples was computing a linear classifier。Okay。

So this is the picture where you have x's and you have O's and you want to separate them so that all the x's are on one side。

 all the O's are on the other。Okay。So the input are just some positive points， some X's and some O's。

So inputs。Positive points。X1 up to x n。お。嗯。Or X M。Negative points y1 up to Yn。

All of these are in D dimensions。Okay。And let me remind you the goal。So the goal is to compute。

A linear function or a half space， if you want to think about it。

So that the X's and Os are on different sides， that is so that they sort of are basically on， yeah。

 so they're on different sides of the half space。All right， compute linear function。H of Z。

 sum over j equal 1 to D。AJ。あ。Okay， yeah right。Zj。Was B。

So the decision variables in the linear program that we drew right were the coefficients。

 the A's and the intercept B。And what do we mean by there on different sides of the corresponding hash space。

 what we mean is that if we plug in the positive values to this function， we get a positive number。

 if we plug in the negative points， we get a negative value。So such that。

H of Xi greater than zero for all positive points。And the age of Yi。Less than zero。

For all negative points。Cool。So back in lecture seven。

 what we did is we wrote down a linear program where the decision variables were AJ and B。

And then there was just this trick， you know， this was a strict inequality but we showed how introducing one additional variable allows you to still solve it。

 not a big deal， okay。All right， so why revisited now。

 we kind of already know how to solve this well。We talked about linear programs and how they're efficient。

 or at least they're efficient up to reasonably impressive data set sizes。

 like hundreds of thousands of points， this won't be a big deal for linear programming。

 but if you go millions， it's going to start getting a lot harder and then if you want to talk about a billion you're really going to be in trouble when your programming is not going to work。

And as you probably know， from some of the other computer science classes you've taken。

 sometimes we really want to work with data sets that are more than just hundreds of thousands。

 it's a well motivated problem， lots of data sets。Really are that big。

And so if you have a data set which is so big。say 10 million points。

 so the linear programming isn't an option， you might ask， well。

 could we have some faster algorithm for this problem。

 maybe giving up a little bit in some dimensions。So what I'm going to show you next is'm going to show you such a fast algorithm。

 which is really， you know， I'll give you a self contained version of it。

 but it's actually really just，Implementing this thought experiment we did with the two players in the Minax theorem。

Anyways， that's the motivation we want to solve this problem。

 but we don't want to use linear programming we want something kind of much faster。So questions？Okay。

 so I wrote it down in exactly the same way as I did in lecture number seven just to jog your memory。

 but actually for the algorithm we're going to want to use。

 we want to pre process it in a few ways to kind of simplify the description。

 This is sort of the most natural description， but we can do some tricks to make it sort of mathematically simpler。

So pre processing。So first of all。Without loss of generality。

We can require the intercept B to be zero。Now， if you're staring at this picture。

 that may seem like kind of weird。 It may seem like that's got to be false。 But， you know， as usual。

 there's a trick。 So it's the trick。 You add one extra dimension。 Okay。

 so the points initially are in D dimensions。 We just added D plus first dimension。

 And this D plus first coefficient is just going to play the role of B。So for that to be kosher。

 what you have to do is you take all your original data points with have D coordinates。

 you give them a D plus first coordinate with the value one。

And now your decision variables are just a1 through a D plus one。

so any half space in the original variables gives you a half space through the origin and the new variables。

So we're going assume the vehicle equal is zero without loss。Similar trick。

We can also require that all the coefficients are non negative。Now don't forget。These points。

 these x's and y's， their coordinates can be positive or negative， Okay， so this is the input。

 we have no control over it， it's just whatever it is。

But I claim that when we're computing for a linear function， we can with loss of generality。

 restrict ourselves to half spaces whose normal vector goes into the non negative ors？And again。

 this probably seems like kind of weird， it's kind of like。

 but what if in the non negative or end you have sort of both positive and negative examples。

You need to sp that non negative orent。Well， it's the same kind of trick。 Okay， so again。

 you're just going to double the number of decision variables。 So take like the first coordinates。

 remember， each point has D coordinates。 So I guess now it's D plus one。

 So take the first coordinate。Make two copies of the first coordinate。

With the interpretation that the first copy is the positive value。Of the corresponding coefficient。

 and the second coordinate is going to be the negative value of the corresponding coefficient。

 It's actually very much like a tricky use in linear programs。 So， you know， if you want to。

 instead of having unrestricted decision variables。

 You want to just have non negative decision variables。 You take your unrestricted variable。

 You introduce two non negative ones and just work with a difference。 Okay。

 so you can simulate an arbitrary real value as the difference of two non negative real values。

 So that's exactly what we're going to do here。 Okay， So basically， we have d plus one coordinates。

 we're going to double every coordinate。And for each data point， we're going to， you know。

 so if there's a given data point has a 17 in the first coordinate。

 it'll still have a 17 in the first coordinate， but now we're going to have a coordinate 1。5。

 which has a minus 17。And so basically， if our linear separator puts a positive coefficient on that second coordinate。

 we interpret it as， oh， I guess what I really wanted to do was put a negative coefficient on the first coordinate in the original space。

Okay。So that's the upshot， if we're willing to double the dimension and we are with no loss of generality in thinking of the coefficients as being non negative。

 we'll see why that's useful in a second。And then finally， this is the simplest one。

So it's sort of annoying that we have this asymmetry between x the positive points and the negative points。

 so here's what we're going to do， we're just going to take each negative point and we're just going to multiply it through all the coordinates all now 2 d plus2 coordinates by minus1。

Okay， that'll flip the inequality。 So we just sort of re encode code the negative points as the negatives of what they used to be previously。

 And now we just have this first set of constraints for all of the points。

 whether they're positive or negative。So multiply eachYi and all coordinates。By minus1。

And after we've done that。The constraints become。That x， that H。

Evaluated on a positive or a negative point。Should be strictly positive。

And I no longer have any reason to distinguish positive negative points from each other。

 so there's not going to be any y's from now on， there's only going to be x's with the understanding that some of them are actually flipped versions of negatively labeled points。

Okay。So what have I showed you， I've showed you that this problem。

 know just finding this separating half space for the two sets of points。

 that's really the same problem。In a higher dimensional space。

 of finding a half space going through the origin whose normal points into the non negative or end。

 so those is really the same problem。Oh， so now like that you're no longer trying to split the points。

 you're just trying to get all of the points on the same side of a single half space。

 and the question is can you do that or not？All right， so any questions about that？

So this is now the version of the problem we're going to solve， okay。

 so it's the same as before except there's no B。And the A's are not negative。

And these are the constraints。And again， we can code this as a linear program if we want it。

 but that's not we're going to do。 we're going to use multiple of weights to solve it instead。Yep。

In the original classfire， it possible that there's nothing。Right。You country things that did。

How would you always find a solution？Ca like。I mean。

 you just you just reflect all the points to the other side line you need like something like a line to。

What do you mean you reflect all the points of the episode？I mean， multiply each Y I5 minus1。

 Why already did that， so。I'm a little confused， Okay， right， since you're saying this problem。

 I mean， I will say this problem would be trivial if these had only non negative coordinates。

 the Xise and the Y I's。Then you could just set all the A's to be positive numbers and you'd be fine。

But the sign patterns of these things are arbitrary。And so I don't see why。

Why it would be obvious that you can do this？And indeed， I mean， you can't necessarily have。Yeah。

I mean， that was sort of， yeah。Yeah， that's related。Other questions？Okay。

 so the new problem statements clear。So you want this half space where everybody's on one side。

 same side。Okay， so。So we're not going to solve it using linear programming。 And as a result。

 we're going to have to make a small compromise。 It's not a big compromise， but you know。

Need to talk about it。So the assumption， we're going to assume that there's a feasible solution。

Not only that， we're going assume there's a feasible solution with a little bit of wiggle room。

 with what they call a decent size margin。So here's what that means。

So we're going to assume that there exists。A vector coefficients， a star。So that。Be sum to one。

And two。If I look at each of my constraints， actually not only are they satisfied。

 but they're satisfied with epsilon room despair。Okay。So。If I look at the relevance。Dot product。

Oh by the way， so D is now like the new set of dimensions。 Okay， so you know， we took it。

 we multiplied we added one。 we multiplied by  two。

 I'm just going to recall that new number of dimensions again， D。

And so this should be at least greater than Epsilon。For all data points， aye。Okay。

So a given data set may or may not satisfy this， but I'm going to give you a guarantee when the points do satisfy this。

And we did talk a little bit in lecture number seven about the idea of how do you make it more likely that your data is actually linearly separable。

 including with a big margin， well there are things like adding features and going to a high dimensional space and so on。

 which you can learn more about in 229 So here I'm just going to assume that there's a feasible solution with Epsilon Google root。

ち。Okay， and the running time that we're going to get is going to be parameterized by epsilon。

 So we'll get a good running time provided Epsilon isn't too close to 0。 Okay。

 It's going one of Epsilon squared dependence。All right， actually， I also need some notation。

We're also going to assume。That。All magnitudes of all of the data points are bounded above by some number m。

Okay。So N can be whatever， but our running time is going to get slower as M gets bigger。Okay。

So M is just a bound on sort of like how big a ball we need to blow up around the origin so that we capture all of these data points。

 all of these Xs。All right， some to the algorithm。So。

We're going to do it's going to be a black box reduction in effect to multiplative weights。

 So to run multiplative weights。 I have to tell you， like， first of all， what are the actions。

So this isn' an online decision making this is finding linear classifier， so again。

 to type check multiple weights， I have some explaining to do。So for the actions。

They correspond to the D coordinates。Okay， so the dimensions of the space in which the data points lie。

So J equal one up to D。Now there's going to be our algorithm now is really sort of how you can solve this problem。

So we're going to take a number of iterations necessary。

 or rather I should say sufficient to get the regret down to epsilon when the rewards are between M and minus M。

嗯。So as we talked about with that extension at the beginning。

 that'spsilon m squared of epsilon squared。Times log n， or I guess n here is the same as D。

So maybe I'll say D here。Because there's the actions。Okay。We're going to ask multiplative weights。

For a probability distribution。Over the deco coordinates。It's a proper distribution。

 or maybe we'd rather think of it as just like a bunch of numbers that are non negative and some to one。

Okay， which is also， you'll notice kind of the format of the assumption up there。

And so what we're to do is we're going to get this probability distribution back from what bit of weights。

 interpret it as a real value D vector， and check if it works for a half space。And if it does。

 we're golden， if not， we have to figure out what to do。Okay。So use motor weights。It generateerates。

Probability distribution。A star， A T， I should say。AT。And RD。嗯。ち。Where do this go？Oh yeah， okay。So。

 if。We satisfy all of the constraints。So what does that mean？

That means the dot product of this vector AT。With each of the data points。

ItShould be greater than0 for all I than we're done。Remember。

 this is exactly what we're trying to find。 We're trying to find coefficients， a vector。

 so that if you look at the dot product， if you at the corresponding linear function。

 evaluating the data point， it's strictly positive。All right， to call this。

So this is sort of the linear function that we're trying out on day T， call it H sub T。

So what if it doesn't work to L's？That means there's at least one data point that it gets wrong。

Because every data point right， we're done， otherwise pick some arbitrary point that it gets wrong。

So what does it mean to get wrong， it's a0 point X？

So that if we evaluate it with our current try for a linear function。It's non positive， okay？

I'm going to use this violated data point to define a reward vector。

 which I'm going to feed in the multi bit of weights to encourage it to give me a better guess next iteration。

So set RT。For a given coordinate。E国。Two， the JS coordinate of the bad data point。看。

And then feed RT to multiple weights。Okay。So why is this not totally crazy。

 like what would be some intuition about what's going on here？Well， you know。

 suppose you have this current linear function， right， So you have these current vector of。

 of A's of A Js and you get some data point wrong。 Does't mean to get it wrong， I means。

 your dot product with that data point is negative。

What do you want to do then I guess at least you want to modify the coefficient vector。

 So you at least do better on this data point。 What does do better mean it means the dot product gets higher。

 Now， maybe you'll screw up your dot products with other data points when you do that。

 But let's forget about that for a second。 So we want to modify the A's so that the dot product with X gets higher。

So that means whenever you have a positive coordinate。

We'd like to have a higher coefficient on the positive coordinate。

And whenever we have a negative coordinate， we'd like to have a lower coefficient on the negative coordinate。

And if you think about it， if you remember back to multiple weights。

 that's exactly what this is going to do。 so multiple weight sort of takes in the reward vector。

 it sees how well things have done so far， and it plays the better performing actions with higher probability。

So that's going to result when you give in these more positive coordinate values。

 higher weight and multiative weights， so a bigger probability of playing at next iteration。

 which corresponds to a bigger value of the relevant A values。So again， that's not all a proof。

 but that's just why it's not insane to think about defining rewards in this way。

 it does at least go the right direction in some sense， okay。All it。So any questions？So again。

 what is the algorithm， the algorithm is literally just run multiple of weights as a black box。

 So again， you have to unpack then and say what do you mean， what are the actions。

 what are the reward vectors， So the actions are just distributions over coordinates which can be interpreted as coefficient vectors for linear function。

 and then the rewards are just defined by some point that you get incorrect in a given iteration。

And so the claim is going to be that actually， by the time you get to the last iteration。

 if not earlier。You actually will find a feasible point。Okay so on one of these capital T days。

 multiple of weights will hand to you on a silver platter。

 something you can stick in and have a linear function which correctly classifies everything。

And the proof is quite immediate from what we already know about multiplative weights。

So two observations。So the first question is。Plus， I guess here's the key observation。

Let's think about the expected reward that multiplicative weights gets at each time step。

When I set the reward vectors in this way。So add time T。Expected reward of MW。Well， you know。

 it's just sum over the actions，' the probability that you pick the action？Times the reward。

So how did we set the probabilities， that's just our current guess for T。So we have our ATJs。

How did we set the rewards， we set the rewards according to the。Bad data point。OkaySo the data point。

 which is on the wrong side of the half space， which is a negative dot product。

So the expected reward of multiple weights at time T is just the dot product of the strategy it chose。

 the coefficients A。With the reward vector， which is just the same thing as this data point that it got wrong。

So by our choice of the data point I。And by our definition of the reward vector。This。

Is going to be non positive。Okay。So in other words， if multipleative weights hands us。

Something which is not a feasible solution。Then we're in a position to adversarial give it back a reward vector where it gets non positive reward。

That's really sort of what it means to get this half space wrong， given how we define the rewards。

 okay？So as multipleude of weights keeps running， keeps giving us suggestions。

If it's not a good suggestion， we keep feeding it in these sort of adversarially chosen reward vectors to keep its expected reward non positive every time step。

Deec there。Okay， so really exploiting the fact that it's making mistakes to keep multiple weights。

Expected reward low。So that's the first observation。

That every single time step that this procedure proceeds。

 as long as it hasn't found a feasible point， it's never going to be getting positive expected reward。

Now to invoke no regret guarantee， we have to talk about the best fixed action in hindsight or as we've seen maybe the best mixed strategy in hindsight。

And by our assumption。We know there is a good solution out there to be found。Okay。

So the other thing we need to note。Is that there does exist。

A probability distribution over the actions， so that is coefficients over the coordinates。

 non negative sum to1。Such that。No matter what data point the adversary chooses。

It satisfies it by epsilon or more。 Okay， that's our margin assumption。

 There exists a choice for these coefficients so that every single data point has a dot product。

 of at least epsilon。Such that for all tea。Some over J equal1 to D。Of AJ star。X I J。

At least strictly greater than epsilon。Again， this is just our assumption。好。So remember， every day T。

 the reward vector is just some data point and if you're playing a star。

 you don't care which data point gets chosen because you have margin epsilon in every single one。O。

So as long as this thing doesn't stop。Multiple of weights has expected reward at Mo zero。

While there exists a solution that has expected reward at least epsilon in hindsight。

So this cannot be true if the regret is epsilon。 So the regret epsilon exactly says that。

Your expected reward over time is within per time step is within epsilon of the best you could have done in hindsight。

So sure， you know， maybe in the first iteration， multiple weights gives you something which doesn't work。

 maybe in the second iteration。But eventually， once capital T is so big that the regrets is dropped to epsilon。

 this is no longer sort of viable pair of conditions。

 So there's no way both of these two things can be true once the regret is epsilon。

The only way this algorithm can stop is with a feasible solution。So within one of these time steps。

It must be the case that you find a coefficient vector that works that classifies all the half spaces。

对。So that's the correctness of the algorithm。So it's guaranteed to work within this many iterations。

So， you know， how good this is sort of depends on what kind of epsilon you're willing to tolerate and how big capital M is？

So Epsilon remembers the margin and capital M is how big a ball you need to capture all the data points。

 but if the data points are fit inside a reasonable sized ball and you've got a decent margin。

 this algorithm is going to do really well。Okay。And again。

 we don't need to know anything about the guts of multiple weights。

 just using its guarantee as a black box， you can deduce the correctness of the algorithm。

 which is pretty nice。So any questions about that？Yep。

So we're basically having our cake and eating it two a little bit， so we're interpreting。A star or A。

Either as a mixed strategy or as a non negative vector sum to one。

 as is fit for our current kind of discussion。So you know。

 as far as the semantics of the original problem is just going to be a coefficient vector。Now。

 what was the point of all this pre processing， the point of all this pre processings was to say。

 oh well， without loss of generality， the coefficient vector we're looking for actually is just a distribution over the coordinates。

So we did this trick to make them non negative， obviously you can scale up and down to control to some of the AIs。

And then we wanted it to be at zero。So with the preprocessing said without loss。

 we're looking for probability distribution， and now it starts type checking with multiple weights。

 which gives us probability distributions。And so you of course， I mean， if you implemented this。

 you wouldn't actually it wouldn't actually be a randomized algorithm。

 so you would not actually flip coins， you would literally just look at these dot products so this is actually not a randomized algorithm。

Good other questions， y。おスゼ。Say it again， say it again， what was it？

What if any reasonable solution has sigma AI star like much bigger than one？Well。

 now you can always scale a star， right so if there exists any solution。

Then I can say where the sum is a million。I can just divide all those numbers by a million。Well。

 so let me say it again。Here's what's important， right， So there's really two。

 so there's two conditions here。 Okay， that the margin is big。 here's a different way of putting it。

 right， So like if I just wrote this， if I just wrote condition2 and not condition1。

 this would be a totally stupid condition。Because， you know。

 epsilon would be meaningless because because I could just scale things。 So in other words。

 suppose I didn't require this。 And you showed me some coefficient vector that achieves this for epsilon equal001。

I'll just multiply all of your coefficients by， 10，000。

 and all of a sudden this starts holding with 100。So you can only talk about the meaning of a margin with respect to some normalization。

 So this is the normalization we're using。It's a fair question。Other questions？Yeah。Okay， so。Really。

 the last two things I told you about， namely this sort of proof of the miniax theorem when one player chooses a distribution and the other chooses a best response。

 and this algorithm for computing a linear classifier when the margin is big。

 I really just told you the same thing twice， exactly。

So something you might want to think about more offline。

 but let me just kind of tell you what the correspondence is。Buts remember。

 here was our thought experiment。Right were so it's weird， because this is like a zero sum game。

So that's why it seems a little strange， right， this seems to be about games。

 the other thing seems to be about a particularly linear program。But actually， if we want。

 we can think of our goal in in finding the classifier as a zero sum game between us and an adversary。

 and if we think of it that way， then this thought experiment is exactly the algorithm I just showed you。

It's literally the same thing。So interpretation。So what's the game， okay。

 so think about the classification problem， how do we extract a game from it？

What we think of the rows is corresponding to the coordinates。

And the column is corresponding to the data points。All right， so what's the payoff matrix？

So I've told you that the rows， so this is going to be j equal 1 down to D here。

 and these are going to be the X I's。Well， the payoff matrix that we're using is really just the coordinates of the data points。

O。So we have some number n of data points， each is a D vector。

 I just populate the payoff matrix with those as columns。That's payoff matrix。And。

So remember in our thought experiment the row player uses。Multipicative weights。In our algorithm。

 how did we generate distributions of coordinates？We use most bit of weights。

So the step where we were generating。Sort of coefficient vector to try that corresponded to the row player moving。

Now， what does a column player do？So in the thought experiment。

 the column player does the optimal response。Givenive in what the role player is doing。

And let's remember。What is the payoff？Still up here？Maybe not。I see it's under this board。 Okay。

 so optimal response， So what is the optimal response the column player remember is the minimizer。

 So given the coefficient vector chosen by the row player it wants to choose the column。

Ie the data point。That minimizes the resulting。um。The resulting sort of payoff term okay。

 and so what is the column， which is going to be best for the column player？

It's the one that's going to。Minimize over I。The dot product。

With the coefficient factor chosen by the real player。Okay， so remember the payoff。 So in this setup。

 you know， from the row player' perspective， you know， what are you looking for。

 You're looking for a big dot product with whatever get chosen。 So again。

 maybe I should put it this way。 So imagine。So think about this。

So what's a given entry of this payoff matrix Okay。

 well imagine that the row player picks what's a coordinate。Okay， so like coordinate 17。

 and then the column player picks a data point， and then we just say， okay。

 what is the 17th coordinate of that data point， that's what the column player has to pay the real player。

Okay。Now， the row player gets to pick a distribution over rows。

And so now it's just going to be the expected payoff in a given column。

 which is just the dot product。Of that distribution with the entries in that column。

 which is just the coordinates of a data point。 So in other words， when I play some distribution， I。

e coefficient vector， my expected payoff on the column player picks a particular column is just my dot product with that data point。

The column player wants to minimize， so it's going to pick the column with the smallest dot product with what the row player picked。

So there's going to be two cases， either there's going to exist a column。

Either that's not going to exist a column， which is negative， which is a negative dot product。

Then we're done。 that's a strategy for the row player which gets all the dot products at least zero。

 which is a feasible solution， or there is going to be a column which has dot product less than zero。

 and then in particular the column player will pick one of those by picking the best column for it。

 the worst column for the row player。Okay。So that's the correspondence。 So it's literally。

So that linear classifier algorithm is literally just this zero sum game with the players behaving in this particular way。

Questions。Oh， and I guess the other thing I should say is that。Our assumption here。

This corresponds to saying that we're assert that the miniax value of that game is at least epsilon。

Okay， so this is asserting that there exists some strategy for the row player so that no matter what column the column player chooses。

It gets pay off at least epsilon。 So that's saying the Min Max values at least epsilon for this zero sum game。

 And so， of course， our regret guarantee just says， well， the row player actually achieves regret。

 which is at most epsilon less， which is going to be strictly positive。

And so that's what gave us the。Terminmination bound。So questions yeah。

So that's an excellent question， that is sort of the discrepancy between the two ways that I described the algorithm。

When we talked about the linear classifier algorithm， I said just pick any violated data point。

 it didn't necessarily have to be the most violated data point that was actually good enough for the algorithm guarantee there。

 when I talked about the zero sum game， I actually wanted the column player to do a best response so doing your best response is not important for the specific application of the linear classifier as we've seen。

 but in general to get that regret guarantee you're going to want the column player to do a best response。

Yeah， good question。Other questions？All right， so let me just wrap up by saying a little bit about Max flow。

I mean， just sort of you know so what's the circle of ideas here。

 right so that when we first talked about the minimax theorem。

 we realized it was closely related to a certain primal dual pair。Okay。

Now we're sort of realizing that we can use the most weights algorithm。

To sort of solve zero sum games。The zero sum games seem a lot like linear programs if you remember the proof of the Minax theorem from strong op duality。

 so that kind of suggests that maybe we can use the multiude of weights algorithm to solve linear programs。

Again， up to some epsilon。And we can， okay， so I don't have time to talk a lot about this。

 but I want to at least give you sort of a small example to give you a sense for how that works。

So let me remind you about the。Pal dual player for Max F that we've seen several times。Yeah。

So let me remind you of the notation， so script P， so we have some graph source in a sink。

Scrriip P is the set of ST paths。I'm going to again just to keep things simple for lecture。

 I'm going to set the capacity of every edge to one okay that's not important。

 there's an analogous thing works with general capacities， but we need more notation okay。

So for today， just think about unit capacities。And so this is the path formulation version of it。

 We want to send as much flow as possible。 These are the capacity constraints。

And then what's the duel， the dual， remember we had these edge lengths。

So we wanted to minimize so before we had capacity times length， the capacities are ones。

 which is the sum of the lengths。Subject two， all paths have length at least one。For all P and P。

An L non negative for all Ei。Okay。So this was the primal dual pair that we looked at in lecture 8。

 I believe，Now， we already know how to solve max flow， not just with unit capacities。

 but with all capacities， So I'm going to give you a different approach， but why am I doing this。

 I'm doing this because the algorithm I'm going to show you extends to a problem that we haven't seen good algorithms for namely the multicommodity flow problem So in multicommodity flow。

 you have K sources and you have k Ss and you want to send flow from S to ti S1 to T1 S2 to T2 S2 to T3。

 You don't want to send it from S1 to T2 that doesn't count。

And but you know their edges have capacity constraints and all of the flow has to obey the capacity constraints。

 and then you want to send as much flow as possible。 So that can be formulated as a linear program。

 all of you could do that easily by this point， but we don't really know good combinatorial algorithms in the spirit of Edmd's carp and Dix algorithm for multi-commodity flow。

 So sort of the fastest algorithms for approximate multi-commodity flow follow exactly the template I'm about to show you。

But again， just to keep the notation down， I'm just going to talk about the usual max flow case。

All right， so how can we use multiplicative weights to approximately solve？The max flow problem。

So again， we're going to do this game。Okay。So I need to tell you what are the players。

 what are their strategies， like what are the rows， what are the columns。

 and what are the payoffs so I have to specify all of those things。

So the rows are going to be the edges。And the columns are going to be。The paths。So in effect。

 you can think of the row player previously the row player was picking this distribution over coordinates。

 now you can think of the row player as picking a distribution over edges that's how we're going to interpret these dual feasible solutions。

And so what are the payoffs？All right， so rows， so this is indexed by edges。This is indexed by paths。

And a given。Entry is just going to be the simplest thing it could be。

 So it's just one if the edge is in the path。Zero， otherwise。Okay。So that's the payoff matrix。

All right。So any questions about the setup？So at this point it should make sense to say。

Run that algorithm。On that game。It's not clear why we might want to do that。

 but you should agree that that type checks， okay so I've specified a zero sum game。

 I've told you the rows， I've told you the columns， I've told you the payoffs。

And you can run this thought experiment on any game， where you go capital T time steps。

 the row player uses multiple weights to go first， the column player best responds second。

Doess everyone anyone okay about this？So what I want to do now is I want to say we want to look at what are the implications of the fact that you have regret on epsilon in that sort of algorithm applied to this game。

All right。All right， so first of all， we're trying to compute the optimal solution。And let's imagine。

 just to keep it simple， let's imagine that， I take it back actually。So this is fine。

 so we're trying to solve this primmodable pair。So what does this game have to do with the optimal solution to this prim modable repair Well here's the claman。

I claim the value of the game。Is one over opt opt I just mean the optimal value to this linear program or by strong duality equivalently the optimal solution to this linear program。

 so Ie the maximum flow or the minimum cut。So that's what I claim。

 I claim the value of this game here。Again， value is in the sense of the miniax theorem。 Okay。

 so remember， the miniax says know， it doesn't matter which player goes first。

 you get the same expected payoff。 The value is just that。

 whatever expected payoff of the row player gets when both play optimally。So why is that true？Well。

Basically， what we're going to do is we're going to associate。Dual feasible solution。

 So think about an optimal dual solution。 Okay， so the sum of the Ls。Totals to opt by assumption。

We want to interpret that as a row player strategy。 Now。

 a row player strategy is supposed to be a probability distribution。And here。

 that some of these might not be one might bes going to be bigger than one。 Okay。

 so we just scale this down to get a probability distribution。So basically， proof idea。去去去。So， X。

Where this is going to be our probability distribution。Over edges。And this is。Oops， not that。Oh。

Is a dual feasible solution？Okay。And the way to understand this is， so let's again。

 think about what do the payoffs mean Okay so if the row player picks one edge and the comp player picks one column。

 it's clear what the payoff is， it's this so one， if and only if that edge is in that path。

But what if the row player is mixing over the edges？Okay。What's going to be its expected payoff？Well。

 for a given column， there's going to be ones wherever there's edges in the path。

And the row player expected payoff is just the total probability with which it picks an edge that belongs to the given path。

Okay。Also known as the sum of the probabilities on the edges in that pack。So expected payoff。

A row player。Equals sum over X E， E and E， sorry， E and P。If the column player。Pix the path Peteep。

So again， trying to interpret the payoffs if the column player has committed and the row player is mixing。

 the payoff expect pay to the row player is just the sum of the mass that it put on the edges in the path chosen by the column player。

So back to this correspondence between the value of the game and the linear programming solution。

So consider an optimal solution。Okay。To the duel。It has dual objective function value optt。

 so the sum of the L's equals optt。We want to make it a probability distribution。

So we divide through coordinate wise by optt， so we scale down L's to get the x's。

 The x's are just L divided by optt。Now， when we scale down。

 it's no longer true that every path has length at least to one。Now it's true every path has length。

 at least one over opt。Okay， so what does that mean。

 so suppose the row player in this game just you know。

 as a thought experiment solved the duall optimally scaled down by opt and played it in that game。

Well， the dual constraint would say would translate to saying that no matter what column the column player picks。

 I。e。 no matter what path they pick。The total mass that we put on edges in that path is at least one over opts。

So that's what translates every path has linked at least one here， after you scale by opt。

 every column gives the row player at least one over opt expected payoff。

So that shows that the min max value is at least one over opt。

So the row player has a strategy that can guarantee one over opts。

 and you just run the argument in reverse to show that it's not going to be any bigger than that either。

Okay。All right， time to wrap up。So let me just tell you the punchline。So。So again。

 you do the same algorithm。So now it's important。So basically， you know。

 because the value is one over opts and we want sort of relative error epsilon。

 there's actually going to be an opt squared here。So this is playing the role of our capital M earlier。

Anyways， so you go some number of iterations。Roe player uses multiple of weights。To pick。Xt。

So this is a vector indexed by edges， probability distribution over edges。The column player。

 what is it supposed to do， it's supposed to do a best response。 Okay。

 it's supposed to minimize the payoff of the row player。

So the row player has assigned some probability to every edge of the graph。

It's pay off if I pick a given path is the sum of the probability of the edges on that path。

The column player wants to minimize this payoff， so it wants a shortest path。

So what the column player does， the row player commits distribution x sub B over the edges。

The column player just runs Dytra's algorithm with respect to those XBs to the row player's choice。

 and that returns the shortest path， and that's actually the column player's best response。

Co and playerer responds。And this is the shortest path。Using。

The real player's probabilities as edge lengths。And then what's the punch line？

So you run this until the regret dropsta salon， that's how we chose this number of things。

And then how do you get your flow？Okay， well here's what's really cool。

 and I'm not going to have time to prove this， but I want to tell you the statement。

So the column puts over these capital T time steps， the column player chose one column each day。

 that is they chose one path each day。And so it turns out you can just take the capital T paths generated by the column player。

And superimpose them。And you get a max flow up to a1 minus epsilon approximation。Okay。

So if you have the flow。Equals superposition。Of all of the paths that are chosen。

 let me call them P1 up to PT。Each of them carrying。Opped over T flow。

It turns out it's the right amount。Okay。So a different way of thinking about it is when the column player picks a given ST path。

 imagine that it routed opt units of flow on it。Okay， and then we repeated this experiment T days。

 and then we just average all of the path that we're chosen by the column player over all of the T days。

Now when we did our thought experiment for the zero sum game。

 we agreed that the column player was doing better than their min Max。

 the real player was with an epsilon， if you translate that to the setting。

 it actually tells you that this flow again， take all of the columns。

 all of the pass generated by the column player， take a superposition and scale that's actually a near optimal flow not only that。

 like I said， this works even for multi commoditymodity flow。

 unlike all of the techniques we've already seen。Okay， I'll stop there next week， online algorithms。

