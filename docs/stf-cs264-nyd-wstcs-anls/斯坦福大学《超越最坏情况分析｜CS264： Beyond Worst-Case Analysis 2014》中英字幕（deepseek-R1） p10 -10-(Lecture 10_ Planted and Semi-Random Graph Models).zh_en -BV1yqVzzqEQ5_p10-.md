# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p10 -10-(Lecture 10_ Planted and Semi-Random Graph Models).zh_en -BV1yqVzzqEQ5_p10-

Yet another flavor of exact recovery， although know a lot of the details will be different will have a fairly different flavor technically。

So this is going to be back in the spirit of lectures 6，7 and 8 where we took NP hard problems。

 posited extra structure on them and then showed we could have polynomo time algorithms to get back the optimal solution。

 those lectures focused on these different stability properties we had approximation stability for K media perturbation stability for both K median and cut problems so here we're going to be going back to graph problems like we were studying in lecture 8s and we're going to be studying conditions that have the flavor。

Of these stability conditions， I think in spirit， but technical are going to be fairly different。

 They're going be randomized models。 So we're actually going to be looking at we're going to posit a generative a distribution over graphs。

 And we're going to argue， we want to know like with high probability。

 can we have poly all time algorithms that solve n be hard problems like finding the maximum clique。

 finding the minimum bisection， that sort of thing。All right。Again。

 what we're trying to accomplish with these models is we want to have a different way of reasoning about graph algorithms。

 especially so recall we talked about maximum weight independence set。

 if you don't make any conditions， if you just talk about approximation ratios。

 all algorithms have a terrible approximation ratio， there's no way to distinguish between them。

 so now we're asking can we have a different model of inputs which allow us to get more informative analyses of algorithms and maybe suggest using one over another。

And so we're going to think about distributions over graphs， so average case analysis in a sense。

And if you want to talk about distributions of graphs， you have to start with a Ado Srei model。

So we're not going to actually wind up using these。

 but it's important to understand what they are and why they're not sufficient for our goals of differentiating between different algorithms。

So when people talk about the model GNP， this is two parameters n in P。

 and is the number of vertices， p is the edge probability or expected edge density？

So there's n vertices， that's deterministic。And of the end choose two possible edges for each of those edges。

 you flip an independent coin with probability P， it comes up heads and you stick in the edge with probability 1 minus P。

 it comes up tails and you don't stick in the edge。Okay。

And so you can go ahead and think about P equal one half as a canonical case， if you like。

So each edge presence。IID。Probability P。Okay。So if P equals1 half， this is。

 in fact the uniform distribution over all of the undirected graphs in the world， turns out okay。

All right。So this is the first place to start。 There's a beautiful theory of irishrania random graphs。

 So how about using it for algorithms。😊，And for some computational problems。

 you can say some interesting things about  Erdora you grasp。

 I'm going to pick a couple of problems where it's really not a very helpful model。

Because it can't differentiate between different algorithms。是。And so this is true for。

 I'm going to show you two examples， but it's true for many， many problems， many M hard problems。

 Let me show you a really extreme example。So let's talk about the min bisection problem。

This means you want to find the minimum graph cut， except I'm also going to insist that the two sides of your cut have equal cardinality。

 each one has exactly half of the nodes。So input， let's just focus on the unweighted case。

Even number of vertices。And so the output should be a bisection as compliment。Of equal sizes。

Minimizing the number of cut edges。All right， so why is this sort of not an interesting model to study algorithmically？

So here's something， I'll sort of state it now and leave the details to the homework。

 it's a sort of straightforward exercise and probability。Which is if you take a random graph。From G。

Then， with high probability。All of the bisections are pretty much exactly the same。Okay。

SoWith high probability。Every bisection。Cuts roughly。And squared over 4 p edges。get the door。嗯。

So why is this true？So this is basically the， you know。

 this is roughly the total number of edges and squared over 4。 Each one is sorry， so sorry。

 fix a bise and over two vertices on the left and over two vertices on the right。

This is the number of potentially crossing edges， because you have a choice of one of n over two vertices on the left。

 one of n over2 on the right， each of those edges is present with probability P so for a fixed bisection if you then flip the coins for the edges。

 this is the expected number of edges that get cut by that particular bisection。So in expectation。

 every bisection is the same and these random variables are well concentrated okay so let's say if P' is a constant。

 and so this will be the exercise on the homework， which you can prove using so-called churn off bounds that there's very little difference between all of these differ very little from their expectation。

So suppose you had different heuristics for minimum bisection。

And you wanted to say which one was better。Well， even if you had an algorithm where your bright idea was to compute the maximum bisection。

That would be as good as any of these other heuristics。

RightBecause any bisection is as good as any other bisection。 So really。

 there's just no way to talk about different algorithms in this model。Makes sense， okay。

So they're just sort of not very interesting for the respect of this problem。Here's another example。

 so a more interesting example。So this is a famous problem， actually， whoop's not planted。

Getting ahead of myself。Clleek， Max click。Right。So you should all know this problem。

 It's just a complement of independent set。 So I give you an undirected graph。

 A clique is just a bunch of nodes so that they're all connected to each other and you want to just find the biggest click in the graph。

 So that's just as hard as independent set。What about in Erish R graphs， Okay， So it is easier。

 It's an easier problem in airish R graphs。 But somehow， again， it just doesn't。

Force us to design interesting algorithms。 Okay， We just don't learn anything illuminated by studying the problem in such graphs。

So， let me explain。So fact number one。So let's just take p equal12。Okay。

 so each edge is equally there or not。And G N1 half。So what do we think the answer is going to be。

 So for by section， right， we thought the answer was going to be n squared over four times p。

Here it's a little less obvious。But I'll show you a heuristic calculation that the expected。

Repect the Mac clique's size。To be roughly2。Log based two of that。OK。So。Hereuristic proof。

So let's do something different。Let's actually， just for a given size of clique's K。

 let's just count how many cleaiques of size K are going to be in this graph in expectation。

 And let's just look at sort of like you know， what's the magic number of K for which we expect to be roughly one like one K clak。

 And we're going to heurically interpret that is you know。

 sort of the likely size of the biggest K clak。 It doesn't prove that。 It proves the correct answer。

 but it's not a proof of of that fact。 Okay this gives you an idea of like where does this number come from。

All right， so for parameter K。How many K cliques are going to see in a random sample from GNP？Well。

 how many opportunities for a K C do we have。For N vertices。

 theyre N choose K ways of choosing a subset of K vertices。

 That's a clique if and only if every single one of the edges amongst those K vertices is there。

 there's K choose two edges。That need to be there for it to be a clique。

 he is there with 50% probability。 So if we're given choice of K vertices。

 it is a cleaique with probably two raised。To the minus k choose2。So this is exact。

 this is the expected number of K cliques。Let's， you know， just kind of do some sloppy estimations。

 Let's say this is like end to the K or so。Let's think of this as like k squared over  two。

So now the question is， so we want to know when is this one for what value of k is this equal to 1。

 that's the same thing as saying for what value of this what value is this going to be。End of the K。

All sorry， for which value of k is this term equal to the reciprocal of this term？

And that's going to be。When K is like2。Log based two event。O。You can plug this in and check。So fine。

 In fact， I mean， just a little trivia effect。 It turns out that again， we didn't prove it， but。

It is true that it's very likely that the maximum clique is going to be around this number。 In fact。

 it's one of the most concentrated random variables you'll ever see。

Probability tend to one as N grows large。 it's either the floor or the ceiling of that number。

So it's one of two numbers with overwhelming probability。 And you start seeing stuff like that。

 you're like。Maybe this uniform distribution of graphs isn't actually giving me good information about know graphs that I encounter in real life。

 It's a beautiful model， but there's not a lot of real world distributions over graph for which it's a good first order approximation。

O。So， that's fact1。The target。 So if we're running an algorithm for Max Cique on Erdo Srii graphs。

 this is sort of what we're shooting for。 We'd like to get as close to this as possible right。Now。

 it turns out。So we don't have any algorithm that can get this。Which is okay。 I mean。

 it's not clear we expect this problem to suddenly become easy。

 like polynomial time sovable errors graphs。 But what's frustrating is。

No matter how smart or stupid you're opponent on the time algorithm。

 everything gets exactly the same performance， which is you get one times log base two event。Okay。

So fact two。All heuristics get stuck。At log basedase2。More or less。Including， for example。

 and I'll ask you to analyze this on the homework， just the obvious greedy algorithm where you pick a node。

 you take an arbitrary node that's connected to it。 you make that a two click。

 you try to find a node that's connected to both of them。 If you find one that's your three click。

 you try to find a node that's connected to all three of them。

 And so and you can just do that until they get stuck。 That's gonna get stuck like log n。

 turns out and we don't really know how to do better。 nor do we know how to prove。

 this would also be super So would be super interesting to do better than that。

 it would also be super interesting to say， you know。

 if you could do better then a two approximation， some other unlikely consequence would happen。

 But because this is sort of an average case problem。

 we don't really know how to connect average case problems to kind of MP completeness。

 So there's no connections between making progress on this problem， making progress on say S。

So there's really nice open problems there。 But the moment， the state of the art， know。

 trying to come up with clique algorithms on it graphs has not led us to any interesting new results。

 Is that a product of our lack of imagination or is it something more fundamental。

 It's a good question。Okay。All right。That's what I want to say about Erda Shni graphs。 Okay。

 So if you're talking about random graph models and you're going to do something other than Erda Srini。

 you have to explain why。 And hopefully now I've explained why。 it's not good enough。

So how are we going to change the irerusran model to hopefully get more interesting algorithms？

So the next thing we're going to do。Is talk about planted solutions？

It's a problem can't differentiate between different algorithms。Fix。Were plants。

A clearly optimal solution。And we're going to ask upon atime algorithm to recover。Okay， so again。

 this is， I think， very much in the spirit of the lectures on stability properties。

 stability assumptions。So let me show you the planted version。Of both minimum bisection and。

Max clleique。They're both quite nice problems。So example。Planted bisection。

And so this was studied all the way back in the early to mid'80s， even。So what we do。

 So this is how we generate an instance。 Okay， So if you like， there's， again。

 going to be a distribution over graphs。But it's going to be non uniform。

So here's how you sample from this distribution or generate a graph from this distribution。

So you first partition V。Into S1 and S2， where these have equal size。Okay。

 so you can do this randomly， or you can do it arbitrarily by symmetry。 It's not going to matter。

 Okay， so there's some sort of target partition。Now， how do we make this， okay， so that's our plant。

 How do we make sure that it's clearly optimal？Well。

 rather than picking every edge with the exact same probability。

 we're going to bias the edges so that we're much more likely to see edges inside S1 or S2 than we are to see edges crossing between S1 and S2。

This is how we'll ensure that this bisection cuts fewer edges than anything else。

 They we're going to bias the distribution so that the bisection is sparse，So edges inside S1， S2。

With probability P。Between S1。As to。With some probability Q less than P。嗯。So we have S1。We have S2。

Possibly pretty dense inside。But fairly sparse between them。Okay。Now， needless to say。

 the algorithm isn't presented with the graph。With a nice picture like this。 right。

 these things are all scrambled together。 And so the question is。

 can you figure out where like even I tell you there's one of these sparse bisections， But you know。

 there's a lot of bisections to try。 So can you quickly find that sparse bisection。Okay。

So the theory question。That's sort of really nice to think about then。There's something very clean。

 Okay， so hopefully， it's clear that， you know， this problem is going to get easier and easier as the gap between P and Q grows。

Okay， so this bisection will be more obviously there。

The bigger the differential between the density of edges across the bisection and those inside the clusters。

 So obviously， if P and Q are the same。We sort of argued it's not an interesting problem。

 And if they're super far apart， then presumably trivia algorithms work。 So the question is。

 what is the gap between P and Q that's necessary and for exact recovery by polynoal time algorithm。

Oh。So what is the reason for like creating this？Perhaps very contrived trying find algorithm That's an excellent question。

 So I thought about sort of talking about this at the beginning so。Right。

 so if we think about where do these so this is now like I think the fifth lecture we've had basically on exact and approximate recovery。

 And I think you're right to point out that there's sort of a shift here。

 So we had these three on these stability notions where we sort of argued it's like， well， you know。

 if you're solving， if you think these are interesting problems to solve。

 you're implicitly making these assumptions anyways。 And that's kind of where the story came from。

 Plus， I mean， I don't。 there's some kind of intuitive appeal to the at least maybe approximate versions of these stability notions might hold for say。

 clustering problems that we care about。Then we had the last lecture。Where， you know。

 our sufficient condition was a little hard to get our head around these almost Euclidean subspaces。

 but at least we sort of proved that the ends justified the means， right。

 So basically it allowed us to solve the problem that we wanted。

 and it holds for lots of random matrices。And I think the models we're talking about in this lecture don't really satisfy either of those criteria。

These， I think， are more， you know， so sometimes when you're stuck on a problem， right。

 so when all of your current theories are failing， it can be a useful exercise to kind of invent a model which seems likely to force you to design new algorithms。

 or again， even I'd say， you know， maybe you would have a sense that one algorithm is better than another one。

 and you're just sort of looking for any rigorous justification of that fact。

 So sort of separate the two of them。 And。In that sense the models I'm going to be describing today。

 I think have been successful， I think for example， for the maximum Cek problem。

 there's been some interesting algorithms that have come from so we're in sort of part two out of three of this lecture so this is the plant of models then we're going to have these semiran models so once we passed to the sort of most robust model。

 there have been interesting clek algorithms that have emerged from the study of this model。嗯。

And it's also the case that these semi random models。

Identify a sense in which a certain more sort of sophisticated algorithm is better in the sense of being more robust than simpler。

 more brittle heuristics。So I think more， you know。

 more than any of the lectures of this exact recovery sequence， we're sort of， you know， you know。

 not really believing the real instances conform to this model。 So so more than， I mean。

 all of them require a bit of a leap of faith。 But I mean， here， I'd say we're not。

 we're not even trying to spin a narrative about what this has to do with it。

 We're really just saying， you know， look， you know， clique is kind of a disaster。

 It's interproxiable。 you know， you can study these special cases， but it。

 we're not getting anywhere。 And so this is this is sort of a novel angle。 I would say。But， you know。

 it would be nice。 so so you could imagine studying kind of stable you know stability notions in the context of the clek problem。

 I'm not sure if if that hasn't been done or if it just sort of winds up not being interesting and that's why there aren't results on it。

 But I think there's definitely room to try to take the conclusions of today's lecture。

 which are some justifications of some algorithms and differentiations between different algorithms and try to recreate those in a model of data。

 which has more intrinsic appeal， I think that's definitely。

 would be a very nice thing for someone to do。Yeah。Any other questions？O。Right。

 so this is just kind of the challenge problem。 You know， it's like， all right。

 we don't have good guarantees from in bisection。 Can you at least give me an algorithm that does me this once P And Q were sufficiently far apart。

 okay。All right。So question， right？嗯。How big？Does p minus Q need to be？

Need to be in order for there to be upon a multi time algorithm for exact recovery。 Okay。

 so I'll tell you the answer to that question a little later in lecture。

Let me talk about the planted version of Ceeique。And so the Plan Ck version， the Plan Cleek problem。

Has actually。So going to be a very intriguing creature， actually。

 And I'll say a little bit about that。ち。So here's how this works。So there's some parameter k。

And what you do is you plant a cake clak。So you pick a subset of the vertices， Okay。

 so you just have some， you think of it， you start as with to sh。

 you start with n vertices and no edges。 you pick a subset of size K。Again。

 you can pick randomly or you can pick arbitrarily， it doesn't matter by symmetry。

You make see a clique。 Okay， so that's the planted C K clique。And then for every other edge。

 you include every other edge outside of the clique with probability P and think of P as one half for the cleaek problem。

So here the picture is。You have this cleeique。And then it's sort of buried in some fairly dense。

If P is a half。Fairly then sort of ambient graph。Okay， you're supposed to find it。And again。

 what's clear， hopefully， is that the bigger K is the easier this problem is。So like。

 if K is too small， if K is like at most log n or something。

 it's just going to be totally hidden in this random graph。 if P is a half。

 it already had plenty of cleas to that size。 So you're not going find this one。Good。

And so now the question is。How big。Does K need to be。Before there exists an algorithm。

That does exact recovery with high probability？All right， so are those two problems clear？Okay。

 so what I'm going to do next is I'm going to give you an algorithm。

That solves plant to clique for K sufficiently large。

 But the algorithm is going to be kind of unsatisfying。

And that's going to motivate our third genre of models， these semi random models。 Okay。

 but let me show you actually a positive result for Planet Creek。Actually。

 let me just let me point out some structural properties that these instances of planet clique are likely to have。

 And then the algorithm will just sort of reveal itself。All right。So。

Suppose you took a sample of a graph like this，Think take p equal half。

And suppose you looked at the vertex degrees。 So the number of incident edges and you sorted the degree sequence from minimum degree to maximum degree。

Okay。What， what's the expected， So again， P a half。 What's the expected degree。

 basically of a given node in this graph without the clique。 Sorry， no clique at the moment。 Okay。

 just G， G in one half。And over two， yeah， and minus1 over two。Thanks I got over to。

So this is going to be。The average degree。Okay， so degrees。对。

What's going to be like the standard deviation of the degree？You think。Squa root of n。 Yeah。

 times a constant。 Yeah， All right， So you're expecting a deviation of like root n。OK。So over here。

 you have this minus root n。Plus， root in。 And if you plotted， you know。

 you'd have a whole bunch of stuff around here and you'd still have plenty of stuff within the abbation。

O。Now I'll leave this as an exercise， but if you want to know when does this die out。

So where's the minimum degree going to be and where's the maximum degree going to be？

This is going to die out after about square root of log n standard deviations by Chevy says inequality。

So this is just an Erestriion graph。So no big deal。 So this doesn in。So what？Here's the point。 Okay。

 now， so the way I described it here is I planted the clique first。

 and then I sort of flipped coins for the ambient edges。 Do them in the reverse order。 Okay。

 it doesn't change the distribution。 Okay， so imagine you。Pick a sample from G in what half。

 and then you plant a cake clak。O。Now， suppose， O， so suppose you've done the first step。

 So you've picked your random graph， the ambient random graph。Now。

 suppose you were not one of the lucky fellows in the Cap League。What happens to your degree？Nothing。

 right， Okay， You don't get any new edges。 What if you are in the clique。

 What happens to your degree。Please okay。It goes up。You know。

 maybe you' already connected to some of those guys in the ambient thing。

 but it goes up significantly， certainly by like K over 2 an expectation because it goes up by like a lot Constant times K。

So。In terms of this picture。That means anybody not in the clique， stays where they are。Anyway。

 who isn in the clique jumps case spots or constant times case spots that way。

So once K becomes a constant times the square root of n log n。

Even if you were the least popular node in this graph。You will catapult。Past everybody who's not。

So the upshot。Is that when K？Is at least a suitable constant times square root of n log n。

Was the algorithm？Take the nodes of the highest degree。 The K versus is the highest degree。 Yeah。

 exactly。 Take the K nodes of the highest degree with high probability that's going to be the plan week。

TheS thenen is very large。It is， It is。 It's still， you know， good news。 N is big。

 It's a very small fraction of the graph。 Its much larger than I think our login result we It is。

 Well， we didn't get a login results to be clear。 we said， we just said that you know。😊。

You mean this if you want to call that？呃。I mean， we didn't recover anything。

 So I guess in Een graphs， you know， there's this two logging clique and we don't recover it because there's sort of like no recovery statement。

 It was much larger than the clique could expect to exist。Yes， well， so right， right。

 So let's put it this way。 You might hope you could do it for K much smaller。Like。

 maybe even like 100 log n， why not？Its intuitively， a dwarfportt was there before。

 even it was 100 login。Okay， so I mean， that's so right。 So one thing that's unsatisfying。

 which I'm sorry to say I won't be able to satisfy you。 this lecture is that this is big。 Okay。

 a second thing which is unsatisfying is， you know。

You might want to have a smarter algorithm in this。Right， I mean。

 you could probably find real world networks where actually。

 this would do reasonable things for finding dense subgraphs。 But people who find dense subgraphs。

 you know， on actual， say， social networks， they do things that are smarter than this。 Okay。

 so you'd like to actually have the theory kind of force you to do something smarter than this as well。

 This feels kind of brittle。And actually these semi randomum models will make precise a sense in which this is bri。

Okay。All right， so that's an exact recovery result in a planted model， it's not always satisfying。

But it's something。There are， and that's actually the next thing I was going to say。Which is。

I shouldn't say sophisticated， but sort of moreum。Morn non trivial。Alrithms。Work。For。K。

 constant times rootin。你看。So it is known how to shave the root log factor。Right。And again， you might。

 you might hope， you know， it seems like if K is 100 times log n， you should be able to do it。

 right So it's not， I'm not expecting to be blown away by the root end。 Nobody knows。

Whether or not it's possible to recover planted leaks with high polynomial time for k less than rootin。

I think people generally think perhaps it's not possible， but again。

 because it's an average case problem， we don't really have complexity theory that would allow us to prove that。

So we neither have the language to prove it's impossible nor do we seem to have any good algorithmic ideas about how to do it so it's a sort of interesting problem that really just seems beyond the reach of state of the art techniques。

 upper or lower bounds。In fact， it's gotten to the point。

 you know people are frustrated when they stop trying to resolve a result in either way and just start using it as an assumption to prove other results and that's sort of the state of the planet clek problem ci the last less than a decade so the first result of this sort was you know you started having people there' is definitely like a crypto system。

 not a practical one， but a theoretical one where you can show that the security of the crypto system can be laid on the hardness of finding planted cleks for K well less than root end so that can be done。

There's been some really interesting connections people have developed just over the past few years。

For example， there's a connection between finding planted cleeeks and computing Nash equilibriumria of certain sorts in various games。

And also recently， people have actually connected the hardness of finding planted cleeeks to the hardness of certain statistical estimation problems。

 Another very interesting connection。 Okay， So you， to answer the question about。I mean。

 when you ask someone to defend a model and sort of like the biggest cop out answer you can ever give is。

 oh， well， it might lead to interesting connections someday。

 So that's kind of like if you have nothing else to say。

 And know that's like your last resort defense。 But then like sometimes it's true。 So I mean。

p Carp proposed the Plan Creek problem back in 76。 And you just really 21st century。

 it's just taken on this new life and being much more richly connected to issues in different communities than I think anyone realized even say。

10 or five years ago。So sometimes。Sometimes if it just feels like a natural model。

 it can be worth worth investigating。 Again， you should always strive for a stronger story than that。

 but sometimes。Sometimes things are connected even you don't know it。Okay， so open。Close gap。

Between O of login versus omega Rn。Okay so that's a major open question that really no one has any clue。

 I don't think， about how to improve either the upper or the lower bound。Okay。

So now I want to talk about semi random models a little bit。Any questions？Right。

So semi random models。This is。In the spirit of one of the recurring themes of the course。

 which is finding clever hybrids between average case and worst case analysis so we can sort of think of planet these planet problems as basically average case analysis。

 the distribution we're doing an average case over is kind of it's an unusual distribution it's not uniform it's with this planted clique or plant bisection。

 this has a partial worst case flavor to it which again the goal is to sort of drive us toward even more robust。

 even more interesting algorithms and it's been reasonably successful in that regard。Okay。

 so there was an early paper by Blum and Spencer， and I'm going to be talking mostly about stuff。

From a paper of Fga and Kiian。So let me explain how this works simultaneously in both the bisection and the clique problems。

So first。So there's both nature and there's an adversary。

Where the adversary is trying to devise a bad input for your algorithm， okay。So nature goes first。

 so you start with a random planted instance。It could be cleaique， could be bisection， whatever。

Then nature hands over its sample to the adversary。

The adversary gets to change the input that nature started with。Now， of course。

 the adversary shouldn't be allowed to change it in a totally arbitrary way。

 because then it could just throw nature's sample in the garbage can and give you a worst case instance。

 so it hass to sort of partially respect the randomness of nature's sample。

So what the adversary can do。This is going to sound funny when you first hear it。

The adversary can take the dense regions， and make them denser。

Or the sparse regions and make them sparser。 So like in the bisection picture。

Where we have this planted bisection。Dense regions in the inside， fare across the bisection。

The adversary can add more edges inside S1 or inside S2 if it wants。

Or it can remove edges from crossing the bisection， if it wants。For the clique。

 it can't screw up the clique。 I to leave the cl there。

 Any other edges that can delete it if it so chooses，So in this sense， the adversary。

Wn the certificate of the plant， yeah。And has to respect it。So again。

 certainly not like any kind of literal model for how data is constructed， yeah。Okay。So， right。

 So why？ Well， I guess a couple things。So first， thiss just a quick observation。

 So can the adversary change the optimal solution。just makes the optimal solutions even more pronounced。

So that it sounds weird first like it sounds like， why call it an adversary。

 if it can only help you out？Right。On the other hand。You know。

 maybe there are some algorithms which work in the plant model and don't work with this adversary。

And a semi model。In fact， if you think about it and this is an easy one。

 but I'll ask it on the homework anyways。Top K degree no longer works for Cek。O。

So if there's an adversary and your algorithm as the top K degrees。

 you might actually return something other than the planted clek， forget about root end。

 even if the clique almost has a linear size， you might not get it with this algorithm。

So again this model has allowed us then to take an algorithm which。Intuitively。

 it felt like it was kind of cheating。 It was kind of really using detailed statistics of the distribution over inputs。

 And therefore was sort of a brittle solution。 And so this is a way of saying， no， no， no， no。

 that's not a robust enough algorithm。 For example。

 if you had some adversary tweaking with the input in an intuitively helpful way。 all of a sudden。

 the algorithm stops working。 We'd really like algorithms that are robust。What does robust mean。

 We not can mean a lot of things。 This is one notion of robustness。

 It sort of says your algorithm's success should have monotonicity with respect to the easiness of the input。

 That's basically what we're saying。Okay， so that's what we want。ち。Okay。So interpretation。

Only robust algorithms will survive。I mean I guess in general， I mean。

 this has been these plan models。 This is one of the first examples we've really seen where we posited distribution over inputs。

 We haven't done that。 We had a number of lectures where we just allowed any inputs in parameterized analysis。

 We never restricted the inputs。 We just analyze the performance of an algorithm in terms of some easiness parameter。

 More recently， we've been having some actual restrictions on inputs， like say。

 even earlier this lecture。 we claim nothing for arbitrary， sorry earlier today。

 We claim nothing for arbitrary constraint matrices In effect， we were saying like。

 let's only solve the problem in this restricted family of inputs。 But there。

There was sort of a distribution last lecture over A's， you know。

 But think of the stability properties， There was no distribution。

 It was really just a subset of instances we were solving exactly。

Here we're doing flat out average case analysis there's a distribution of inputs。

 we know what the distribution is， and we sort of tailored our algorithm to exactly what that distribution of inputs is。

 and we're going to develop this theme more strongly as the course goes on from now。

 but basically the theory that I'm sort of curating for you in this class is meant to prevent you from designing algorithms which are too overly fitted to any particular distributional assumption。

And so you want to sometimes。Build into your analysis framework or your model of inputs。You know。

 kindd of safeguards that that prevents you from designing algorithms， which make。

Overly detailed use of the distributions， these semi random adversaries are one， you know。

 fairly successful and fairly generally applicable such safeguard。All right。Questions。All right。

 so for the rest of the lecture， I want to talk about some positive results for min byse。

 I guess I'm not going to plan on say any more about Ceeique。 but let me just mention for Ceeique。

 it is known how to again， get this K equal to root n with a semiran adversary。

 those are some nice results。 they're a little they're a little lengthy to present in the lecture here。

 but they do exist so the root end can be achieved in the semi random model and no one knows how to do better even in just the regular planted model。

So I want to talk about min bisection， the rest of the lecture。So is everyone clear on。

The model we're studying， okay so this is we have the P in the Q。

 it's this dense parameter P inside the planet bisection。

 it's the sparse Q across the bisection and adversary can delete stuff from the bisection or add stuff inside a cluster。

Okay， and so we want an algorithm which recovers the planted bisection with high probability over nature's moves and for arbitrary then additions and deletions by the adversary。

So a men bisection。So here's the regime we're going to work in。Assume that P&q are constants。

So remember that means that the edge is going to be fairly dense。

 so there's going to be some constant density inside each component and some lower density。

 but constant density across the bisection such that。So again， remember， it's going to get easier。

 the bigger the gap between P and Q。 So we're going to insist that the gap between P and Q is at least some constant times。

Rot log in overhead。Okay。So this is some constant。You is not。

 this is just sort of for full disclosure， you're not actually going to need to know this in the proof that I'm going to do。

The one thing I want to point out is， I mean， this is a small gap。So P& Q a constants。

So this is certainly much stronger than saying， you know， assume there exists some constant 。01。

 such the P And Q or at least 0。01 apart。 right， This is going to 0 with n。 O， the gap。Okay。

So that's satisfying。 We don't need the gap to be big to get a recovery result。

And it's also satisfying in that， you know， if we went below this。 okay。

 then we'd have this very awkward situation where， you know， we have this intended planted bisection。

 But then once we flip all the coins， actually， something else winds up being the minimum bisection。

Right，So like think about it as if like P equals Q。 and we're back in Erda Ri。 and you try to like。

 you know， plant a target bisection。 You know， like nodes one through n over  two and then nodes n over 2 plus one through n。

 like， oh， that's my secret planted bisection。 But then you flip all the coins。 Everything symmetric。

 So every bisection is equally likely to be the minimum。

 It's not going to be the target when you picked in the front at the beginning。And similarly。

 if P and Q were too close to each other， you're going to have that same problem。

 some other bisection other than when you intended is going to wind up being minimum。

So if you want to have a recovery result of your plant bisection。

 it better at least be the minimum bisection。And this is， know。

 ballpark kind of the gap you need for even that weaker property to be true。 Okay。

 so this this at least lets you have you know， the bisection is the one you intended。

 And that's also where you start getting poly Al recovery results。So necessary。For plants。

Planted to be the minimum。好看。So that's also satisfying。Okay。All right。So this。

 this problem will give me the opportunity to talk a little bit about what's called semi defite programming。

Which is a really key tool for a lot of the state of the art exact recovery techniques。 Okay。

 I may talk more about this next week or not。 I haven't decided。So for short。

 everyone calls this SDP semi deffinite programming， okay。Let me explain。Okay。

 so just a couple of words of context。 So semi afternoon programming as you can think of as a generalization of linear programming。

So it allows you to solve even more stuff， but it's still polynomial time。

It's not quite as efficient in either theory or in practice。

 but it's decently efficient in both theory and practice， Okay。

 so it's definitely you can solve decent size problems with semide programming in practice。So it's's。

 you know， it's heavy machinery， but it really is used to solve problems。If they're not too huge。

And rather than tell you what they are， let me just kind of， let's talk about bisection。

 let me just tell you about sort of a formulation of bisection。

 and then we'll explain how that leads to a certain relaxation。It's a motivation。So fix a graph。

 even a number of nodes。Let's look at a particular bisection。SS bar。

So let me encode it algebraically as follows， okay。So， Z。Is going to be a plus minus-1 vector。

Indexed by the vertices。And this is just the characteristic vector saying which node is on the left side and which node is on the right side。

 Maybe plus one means you're an S， minus-1 means you're an S bar。Okay。

 so a bisection induces a plus minus1 vector like this。Now define。

 and it's not going to be immediately clear why I'm doing this。

But I want to look at products of pairs of these Zs。 Okay， so for repair pair vertices， I and J。

Define Xi J to just be Z times Zj。Sore also plus minus， either plus or minus1。

And it's going to be useful to think of。The matrix of all of the X I Js。

So if x denote's the matrix of all the Xjs， so this is indexed by vertices。

 both in the rows and in the columns。This is just the outer product。Of the Z vector。Okay。

So Zzi transpose just means the matrix of the Ziajs。All right。So， okay， you can do that。Now。

 what I'm going to do is I'm going to write down a few constraints that。

These X's satisfy starting from any bisection， just like when we're talking about linear programming relaxations。

 we always had in mind intended semantics。 We're like， okay， if you have a multiweight cut。

 then these things are zeros， these are ones， blah， blah， blah， And then ultimately。

 you optimize over some bigger set that includes those canonical encodings of discrete solutions。

 Okay， so we're doing that same program now。 It's a little more complicated。

 It's exactly the same idea。😊，So this is our encoding of a bisection。

 let me now show you constraints satisfied by any bisection。Actually， first。

 let's just notice that we can express the objective function。 Okay， we remember dissection。

' to minimize the number of cut edges。 We can express that very cleanly in terms of the x's。

But if it helps to open the door， that's fine， too。 So it's getting stuffy in here。 I don't know。

I'm assuming the conversation has died down out there。Okay。So how can we express。Thanks。

So how can we express the objective function， the number of edges cut in terms of these x's， okay？

Well， an edge is cut if and only if' endpoints are on different sides。

 if and only if it's Z I and Zj have opposite signs， So if and only if X Ij equals -1。

 so the cut edges have a -1 and the noncut edges have a1。

So the sneaky way of writing that would just be。1 minus。Xi J。 so this is either zero or2。

 depending on whether it's cut or not， So I'm going to divide it back by  two。

And I'm going to sum this over the edges。I Jay any。So call that one。Okay看。So that's nice。

 Have a nice linear objective in the X's expressing exactly what we care about。

So now let me list the constraints， and there are three constraints。

Let me mentioned the simple ones first。So first of all。XI equals1。For all I。

 that's just because Xi iszi times Z。And Z I is plus or -1。3。Is if I sum up。

All of the entries of this matrix。Then I get to zero。And that's because I started with a bisection。

 Okay， so one important thing is that the Z here had an equal number of plus and minus ones。Okay。

 which means that also in the X matrix， you gonna have an equal number of plus and minus-1。So， some。

Overall， X I J equals 0。This is sort of， this is not that important。

 This is important it's saying that X should be balanced and z should be balanced。

Which that's encoding the bisection idea。Now， over here， I sort of want to。

I want to have some constraint which expresses the fact that this X matrix is not arbitrary。

But rather， it arises as the outer product of a vector。Okay， so notice， right in general。

 for a matrix with n squared entries， I have n squared degrees of freedom。

 But for matrices that arises out of products， there's only n degrees of freedom。

 What do I populate the different Z entries of Z's with。 So I want to somehow say this。

 this matrix is structured comes from this subset。Now I'm not going to actually write something down。

 which says x is of the form x equals Z z transpose。Okay，That would be a nasty constraint。

 which you cannot optimize over in polynomial time。

 So I'm going to write down something which is more relaxed。

Which is that the matrix X of the X I J is。Is symmetric。And positive semidefinite。Okay。

So if you've forgotten what positive semi definitionite is。

 probably the best thing to do is just after class， go look it up on Wikipedia。

 but basically so that it means a bunch of things right so one definition you might have seen is only non- negative eigenvalues or maybe like a non- negative quadratic form。

 I mean the way to think about it here。Positive semi deffinite means， okay。

 you might be an outer product。 That's a special case。 In general， you're like the superposition。

 I you the sum of a bunch of outer products。That's the extent to which positive semidein is more general than what written in there。

I might not just do one out product， maybe a bunch added up。And that's if and only enough。O。

All right， so now。We're going to note by SDP。The optimization problem。

Of minimizing the objective function 1， which is linear in the x's。

Subject to the constraints two through four。This is linear in the x's。 This is linear in the x's。

 This is something you may not have seen before。But it turns out this is a nice set。

 the set of symmetric positive semidefinite matrices is conx。

 which is sort of the most important point， it's actually a cone and because you have， okay。

 it's not linear but you have this conxity， that actually means you can still solve this problem in polynomial time up to additive epsilon error。

So， fact。Can be solved in polytne。And again this is even more general than linear programming。

 as I said last week， we're going to think about linear programming as most people do as a black box。

 certainly we're going to think about semideite programming that way。All right。ちちちち。

Three questions about that。So I hope it's clear that you know。

 there's no contradiction that we can solve this in pulmonary time and the fact that in bisection is MP hard。

 right if we've solved this optimization problem， we will not in general get back something that corresponds to a bisection。

If we're really lucky。And we solve this problem and we get back a matrix X。

 which happens to be rank1， meaning which happens to be expressible as the outer product of some vertex Z Z transpose vector。

As easy transpose， then it's going to be a bisection。

 That's the lucky case where we solve the problem optimally。If instead we solve this optimally。

 we get back a。Matrix X， which has rank bigger than one。

 meaning it's the sum of more than one out of products。

 and there's no way to interpret that as a bisection。

 It's kind of some distribution over bisections or something like that。

But we are able to solve it integrated for her Z。No。

 I shouldn't have said distribution of a bisections actually。 that was incorrect。 So in general。

 we're going get back fractions。 Okay， so in general。

 we will getll get so disease actually are not decision variables of the semieite program。 Okay。

 I did that just to kind of motivate。 I did that to point out that any bisection can be thought of as one point in the feasible region here through this correspondence。

 Okay， so the program itself consists only of these n squared variables。 the X I Js。

So you solve it and you get back some arbitrary， non arbitrary。

 but you get back real numbers in those XI Js that are promised to satisfy two through four。

So I'll leave it for you to check that if， in fact， x is rank1。

 then in light of these other constraints。This is true。It think it was true。

I think it's true that if you get back a rank one solution。

 then the only way that can happen is if it's actually。Minus ones and ones。

But off to think about that。So anyway， so the thing which I need for the lecture is just that any feasible solution to the bisection problem maps onto a feasible solution of this problem。

 and therefore， if we minimize this， it's a relaxation。 in that sense。

 this is a relaxation So if we optimize over with this。

 the optimal objective function value is going to be only less。

Then the number of edges crossing the bin bysection， that's the key point。Good。没有了 questions。Yeah。

 I feel like the use of semi definite optimization has not been motivated here because it's not clear to me why something simpler or wouldn't workenial。

Yes， so。Right， I'm trying to I believe there are counter examplesamp for linear programming。

 It's excellent in question。 So you're right that the first thing you'd want to try is a linear programming relaxation for bisection。

 and there are relaxations that have been used to design heuristics。

I they have not been used to successfully design exact recovery。

And I think that's because they just don't work， for example recovery。

 but actually I haven't worked out this counter example， even for larger gaps That's a good question。

 is there some bigger gap which linear your program in work？It's a good question。

 but don't know the answer。Yeah。ok。嗯。So at H of G。Be the opt value。The SDP。For a giving graph G。

 Okay， so for any G， we can form this 7 f in a program。

 let this be the minimum objective function value of any feasible solution。

 and then B of G be the value of the min by section。Okay。

 so the actual number of edges at minimum crossing any bisection。

 And what we have by virtue of this being a relaxation。H of G is。At most， right。

 so we're minimizing over a bigger set， it can only be smaller。Good。Okay。

 and so what we're shooting for is we want to say we want to show that as long as P and Q are separated by at least that gap。

 in fact， this is going to be exact。 Okay， In fact， H of G will equal B of G。

 even though we really have no right to expect that， okay。Allright， so here's the。

 here's the key lemma。Due to five and kill。Which says that let's just consider the the usual planted model。

 So forget about the adversary for the moment。 Okay。

 so just the planted bisection model where ping Q were separated by at least C times square root log in a brand。

Okay。So for the planted model， no adversary。With P and Q with that gap。This relaxation is exact。

With high probability。好看。So this turns out to be true。This is not easy to prove。

 and we're not going to prove it。 This would actually be a great thing to prove in an advanced class。

 right。So let me just say what the high level idea is。

 so some of you know at least that linear programs have duals。

Semidefinite programs also have duals okay and if you in general， if you sort of want to say。

 so what do you want to say here， basically like in the planet model we have this。

 we know the answer to the integer primal problem we've planted the bisection right so we know what we want to be optimal。

And so we have this relaxation。 but we want to say。

 but this integer thing is the optimal solution to it。

 And thinking about dues are exactly what lets you certify that some proposed feasible primal solution is optimal。

 you exhibit a dual。 You check that it's feasible。 Either you verify complementary slackness conditions or you compute its objective function and show that the objective function drive is the same as the primal。

 If you do either those two things。 That's a dual certificate of the optimality of your primal solution。

😊，So what this lemon needs to do is it needs to say this integral bisection feasible solution is actually optimal。

 So the way it proves is you just sort of guess and check a suitable due。OkaySo you have write。

 you have to figure out what the duall of this semi E program is， that's not that hard。

It's actually pretty easy to guess what the right due should be， the dual certificate。

And compute the objective function value。 But it's really annoying to check that it's feasible in particular to check that you get the sort of necessary positive。

 semidefinite constraint。 Okay， that takes a lengthy calculation。

 which I'm not going to subject you to。The reason I say this would be a good thing to do in a more advanced class is actually a lot of the state of the art exact recovery results follow exactly the same template okay you're looking at some mathematical programmingbing relaxation。

 like a convex relaxation and you know what you want to be optimal and the way you actually prove it is you literally exhibit the due and there's a lot of kind of nice machinery that's been built over the last few years about where do these toolss come from。

 how do you actually check the feasibility and so on。So guess and check。说那么多。Technical。Okay。

 so we're just going to accept that this is true。 F and kill and proof this。 I mean。

 it's in the paper if you're interested， but it takes some lengthy calculations。So what I want to do。

 but remember。This is for the planning model。This is not for the semi random model。

So the thing I do want to show you in lecture is I want to show you how given that the semie program is exact。

For the planet model。Then it turns out it's also going to be easy to extend that to exact recovery in the semi random model。

 So remember， the semi random model was guiding us to sort of robust algorithms whose correctness was sort of monotone in the input in some sense。

 And I'm going to show you that the semieth programs exactness property has exactly this monotonity type behavior。

 So that's what I want to leave you with。Okay。So。So here's a simple thing。

 which I'll leave for the homework。Which is。So what can the adversary do。

 The adversary can add edges to the dense regions or delete regions。

 delete edges from the sparse regions。 Okay， so we want to think about the adversary。

Adding or deleting edges。We know how the min bisection changes。 It doesn't change at all。

 So the adversary is restricted in a way that the true minimum bisection will never change。

 So instead， what we want to do is we want to see how the semieth programming relaxation changes when the adversary adds an edge to a graph or deletes an edge to the graph。

So the key but easy property。Is that if G hat？Is formed。By adding one edge to a different graph G。

Well， then the semi E programming relaxation doesn't change in a very radical way。

So we've added only more edges to the graph。You'd sort of think then that the optimal objective function value would only go up。

 There's only more things to cut。 That's true。 Also， you only added one edge。

 So you'd sort of think it would only go up by one。That's also true。Okay。So， H of G。

It's the most H of G hat。Which is the most H of G。Plus one。Remember， H need not be an integer。

But it' I mean， if it's exact， it's going to be an image， but it's a semi different program。

 we don't know what it is， okay。But so H will only go up。

 but it's only going to up by most of one when you add an edge。我看。So given that， corollary。

Even with a semi randomum adversary。SDT is exact。With high probability。

For exactly the same gap between P and Q。Also， don't forget that as a relaxation。

 it is always the case。That H of G is at most。The value of the actual min byse。Okay。

 that's true always。Its by virtue being a relaxation。So proof。All right， so it's just by induction。

 okay， so we start with the random instance。So we start with the initial planted instance where this QMma says the SDP is exact。

Now we just go by induction on the changes that the adversary makes to the graph。

 and we argue that every edge change it makes in addition or a deletion， it remains exact。

What can the adversary do， It can add an edge or it can delete an edge。

So if the adversary adds an edge。Well， before before it did this， this held with the quality。

 That's the klemma， right， H equals B。Okay。It adds an edge， it has to do it to the dense region。

So B is the same。 I， H and B are the same。It adds an edge， B doesn't change at all。

This says H can only go up。so think about it this way。Right over here， we have H。Over here we have B。

 we're at a point where they're equal。If you add it to a dense region， B stays exactly the same。

The homework problem says H can only go up。But the other hand， H has to always be the most beat。

So it can't go up， has to say exactly the same。So H still equals B。Case 2。

 the adversary could delete an edge。 If it deletes an edge， it has to be from the bisection。

So then the bisection， the minimum bisection definitely drops by plus one for sure。

 because the episodever just removed it from the bisection。So then case 2， H and B were equal。

P drops by one。The homework says H drops by at most one。But again， H cannot drift above B， right。

So H has to drop by the maximum possible amount， exactly one， and it can't drop any more than that。

H and V are still the same after the delege。Okay。So， et cetera。Sa proof by picture。Yes。

Or do you want me to write it down？It's late in the day， so everyone get that any question？嗯。

All right。So the final， the final comment to motivate another。Homework exercise。

So what algorithm that actually give you， I gave you an algorithm that successfully computes the value。

Of the minimum bisection。What do you do， solve this SDP or with high probability at least。

 solve this SDP if it says 127。Then you say，Co， it's 127。Right。On the other hand。

There's still the issue of actually extracting that bisection。

 And so you have to do a little bit of extra post processing to do that。So post processing。

It's not hard， especially with the suitable hints，'s definitely not hard。Post processing。

Yields the planted bisection。Questions。