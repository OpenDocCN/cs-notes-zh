# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p16 -16-(Lecture 16_ Pseudorandom Data and Universal Hashing).zh_en -BV1yqVzzqEQ5_p16-

In this lecture we're going to be having on our hat where we seek to explain sort of an empirical ground truth about algorithms。

 so specifically the fact that when you look at hash functions。

 empirically they behave as well as if they were fully random functions even though in the theoretical worst case that's not always true so we're going to be seeking some kind of theory which explains why simple hash functions work so well in practice and the solution we're going to put forth is similar to the spirit of smooth analysis。

 we're going to assume that the data has at least a little bit of randomness in it and under that assumption we'll see that indeed simple universal hash functions are guaranteed to do as well as fully random hash functions。

So just a little bit of， you know just jog your memory about hashing and the specific motivating application of hashing I'm going to use。

 which you may not be familiar with， linear probing。So first， just hash functions。

So we're thinking about there being a big set capital M， you know， maybe really， really big。

 maybe astronomically big， bigger than the number of atoms in the universe even。

 and hash function is responsible for basically compressing those。

 So given giving each element of capital N and nickname that lies somewhere in capital M。

So this is what a hash function does。Maps elements of capital M。

 the elements of capital M or capital M is much smaller again， depends on the application。

 but maybe today I think of capital M as being like logarithmic in the size of capital N。

 for example。Now， what I else don't want you to remember。

 So because we're compressing mapping a big set to a small set by the pigeonhole principle。

 inevitably， there will be collisions。 There'll be distinct elements of capital N that get mapped to the same element of capital M。

 and in your data structure。 Think of it as an array， say where you have a bucket。

 you have to somehow deal with these collisions So that's part of the implementation details of a hash table。

 one of the simpler ways， and usually what's emphasized in an undergraduate course， for example。

 is chaining。 So this is where in each bucket， you have a linked list。

 So everything that hashes to the same elements just gets concatenated to each other in a linked list in that bucket。

 So's not what we're going to be talking about today。

 so we're gonna be the motivating example is going to be a style of open addressing。

 So this is a different way of resolving collisions。

 where you maintain the invariant that in your hash table there's only going to be one item stored in each bucket。

 Okay So clearly the load better be less than one。 the number of things inserted。

 better be most the number of buckets because there's only one per bucket。

And so that means is when you hash something and you go to put it in a bucket in a slot。

 if it's already full， you need to look elsewhere to find an empty slot to put this element that you're inserting。

 so there's many flavors of open addressing depending on how you search。

 how you do this search for an empty bucket so you have to formally speaking define find a probe sequence。

So。U。What I'm going to use as motivation is。A particular。Probe sequence。

 a particular way of doing this search for an empty slot and a hash table called linear probing。

 may be the simplest thing you could think of。So。If you're trying to。

 so you're given some element X in capital N and you apply your hash function H。

 So that maps it to capital N。 What do you do if that slot is full。

 You just search subsequent slots until you find an empty one。 Okay。

 and you just dump it in the first empty slot that you find wrapping around to the beginning of the array。

 The beginning of the hash table as needed， okay。So starts。Add a bucket H of x。

And then you look at h of x plus one。H of x plus2， et cetera。As needed to find an empty slot。

So on an insertion， so， think about the case where there's no deletions。 Okay。

 I don't want to deal with deletions for an insertion， you just start H of x。

 and you just go forward until you find an empty slot。 And then that's where you put it。

 And then if you're doing a search， you start looking at H of X。 you keep looking forward。

 If you ever find that element。 Obviously， you're done and you return it。 If you find an empty slot。

 then you conclude that the element isn't there。 And it's an unsuccessful search。😊。

So that's a linear proven。So why do this and why not do this， what are the pros and cons？um。

So it's obviously simple and the main reason that this is useful in practice beyond simplicity is it is primarily sequential accesses to a disk or to the data structure as opposed to random accesses。

So mostly sequential access。Okay， so I'm thinking here about know hash table which is an array。

 just stored contiguously in memory。 Okay so that interacts well with a memory hierarchy。

 It interacts well with things like prefeting。 So empirically。

 you often get quite good performance from linear you' probing And it is fairly common in practice for those reasons。

 contrasttrat that with， say， chaining right if you have a linked list。

 it can be hard to make sure that your linked list is contiguous in memory so that might be jumping around in memory as you follow the linked list。

 Similarly， if you tried to do something more clever as a probing strategy that took you to and fro within the hash table that again would be lots of random accesses。

😊，All right， so but what should one be concerned about with linear probing。Well， you， intuitively。

 here's what your sort of worry is going to happen So you start inserting things into your hash table randomly。

And， you know， for a while， when it's very sparse， you're not even going to have any collisions。

 Okay， so it's not a big deal。Right。And then maybe by chance。

 just two things map in to say adjacent buckets。And but then you know。

 sort of you're worried about this sort of amplification of clumps。 Okay， so now。

 as soon as you have two things in a row， now all of a sudden， you know， there's a double the chance。

 right， So two out of the number of buckets that the next thing will go， will hit either of these。

 And whichever， you know， whichever these attempted inserts you try to do， you're going to wind up。

You know， searching forward and putting the new element here。 Now， all of a sudden。

 there's three different slots。 where if you try to insert in any of these。

 it's going to wind up inserting something here。 right， And then maybe even these things join。 Okay。

 So somehow， the bigger the blocks get， it feels like the more likely the blocks are to get even still bigger。

 okay。So， intuitively。Linea probing is vulnerable to clumps。And obviously。

 the insertion time of the search time is degrading as you have these big clumps because on average。

 you'll sort of find yourself somewhere in the middle as a starting point。

 and then you have to search through half of this clump。So that's what you're worried about。

 that's why it's not actually so clear that the performance is going to be especially good for linear pro。

So but there's an old result。Of my colleague， the living legend Don Cannuth。

I forgot the exact date of something like 1960 or so。Where he said， well， you know。

 let's ignore the details of what the hash function is。

 let's just assume that actually the hash function is totally random Okay so that every time some new X shows up and you map。

 you look at H of x， let's just assume that's uniform not only is it a uniformly a random bucket but it's also independent of everything that's happened in the past。

 so that's a fully random function since everything to a uniformly at random place independently。

So under the best case scenario。Of a fully random age。And again， fully random independent H of x's。

Then it turns out。The expected time。Of the teeth insertion。Is a function of the load only。Okay。

 so the exact function turns out to be basically。1 over1 minus alpha， that's an alpha。Alpha squared。

Where here， alpha denotes the load of a hash table。

Its not dependent on how the elements are distributed。Well， so it's an expectation right。

 so there's always like the really unlucky case where you know， they're all in a row。

 but so on average， over the randomness in the hash function， if the tables say half full。

 so that corresponds to alpha being 0。5， then you're expecting to do basically four probes on the teeth insertion。

So alpha here is t， the number of things you've inserted over。The number of buckets。

 the Carinality event。Okay。And so the takeaway here is that you know。

The reason this is so cool is it says， you know， basically， you pick。Whatever you know。

 expected insertion time you want Okay and you know independent of how many insertions you're ever going to see。

 as long as you scale your hash table proportionally to the number of elements that you're going to have to hold then you can control the expected insertion time。

 so the point is it depends on T only in as much as it depends on alpha So obviously， you know。

 if you want to store double the number of elements。

 you should expect to sort of double the hash table， But what's great here is that actually。

 the performance remains unchanged as long as you scale the hash table with the number of insertions。

 Okay and that's sort of you know， you'd love to have this to be even smaller。

 like one over one minus alpha， that would be even better。

 but to have this be a function of alpha only otherwise independent of T and M is great。

 Okay so really just to scale the hash table with the data set you'll be fine。

 if it's totally random hash functions，😊，And I encourage you， you know， to check out。

 if you look at Kauth's art Comp programming Vole 3， he has a footnote where he basically says。

 you know after he worked out this theorem， he found， you know， he found the beauty so overwhelming。

 He had no choice but to devote the rest of his life to the analysis of algorithms。 I'm not kidding。

 That's what he says。 Okay， so this seduced Kauth to basically work on this stuff for the rest of his life。

Okay， so we're not going to prove this theorem， it's not sort of outside the scope of this course。

So what I want to talk about is I want to evaluate。This hypothesis。Okay。

 so the best case scenario have a fully random hash function。Now， in practice。

Hash functions are not fully random。 Okay， You might want to think about what it would even mean。

 to use a completely random hash function。 Okay， Basically。

 it means you'd have to store it as a lookup table， explicitly， all。

 which you know for any end of even moderate size is ridiculous okay。So it's really not an option。

 to use fully random agents in interesting applications。So we can't。Use。A truly random H。

So this is false in practice or the point is we're not using these hash functions。

 so then the question is all right， is theres some other way we can kind of justify the mathematics and can is derivation under what maybe there's alternative assumptions under which it would be true。

 this one over one my discovered to be true。And so， you know， so for example。

 instead of having a totally random hash function， you could have just sort of any old hash function and assume that the data is totally random。

 that each thing you want to insert is sort of uniform at random from capital N and also independent from all the previous things you want to insert so the math would remain valid。

 if you switch from thinking about a fully random hash function to fully random data sets。

 any hash function I mean， it should be， I mean， it's pretty easy to find hash functions that would be fun。

 The constant function would not be so good。 So you need some mild assumptions on the hash function。

 But many hash functions will defined if the data is totally random。

 so it's not hard to define a hash function that works well with random data。 On the other hand。

 you know， we kind that it's not fully convincing。 And that's good。

 It's good to have a second interpretation under which this is true。 but you know。

 we don't really think data usually is kind of totally random and that everything to be inserted is independent from what's being inserted before。

 seems sort of implausible。Okay， so。Given that we can't assume fully random hash functions nor fully random data。

Yeah， sort of the hope。Is that simple has functions？Namely。

 ones that we can store explicitly in small space and ones that we can evaluate quickly work just as well。

 okay。So， simple hash functions。Work just as well。As fully random ones。 So we want to just say， look。

 you know， it's， this is true under the random function assumption。

 But that hypothesis is sort of overkill。 Ga just use sort of a small family of simple ones。

 and you'll still get the same bound。 That's what we'd love to be true。So， all right， so fine。

 it's a nice idea。 So how should we define simple hash functions。 So it's a good definition。So。

 so in this lecture， we're just going to use what should be the definition you all already know from undergraduate algorithms and data structures。

 namely universal hashing。 Okay， so that's the only property of hash functions we'll be using。

So recall。So that if you have a set of family H of hash functions。

all of these mapping the same domain end to the same range capital M。We call this universal， if what？

So。We want to think about collisions， right， so collisions are important。So we say。

 think about an arbitrary pair of distinct elements in the domain。So for all X， Y and N， distinct。

And we talk about the probability， and this is over the choice of H。 Okay。

 so X and y are fixed and different。 We're picking a random hash function。 or put differently。

 We're looking at the fraction of hash functions in this family under which these two elements collide。

So again， x and y are not random， H is what's random in here。RightSo collisions are bad。

 So presumably we want an upper bound in this probability。 Now。

 what kind of upper bound would we be happy with well。

Suppose actually H was a totally random function。Okay。

 so suppose every H of x H of Y H of z was chosen independently and uniformly at random。

What would this probability be？One over the size of the range， right， one over the size of the range。

So I'm calling capital M the Rach。Why would that be true？ Well， just， you know， first。

 you pick H of X， It goes wherever it goes。 slot number 17。 Okay。

 H of y is independent of that and uniformly at random。 And so there's a， you know。

1 and M chance that it goes to slot 17， as opposed of some other one。

So universal hash functions just says， for the purposes of a pair of elements， X and Y。

 the collision probability is as low as the gold standard set forth by fully random hash functions。

That's what universal hash function， universal hashing means，Now。

 fully random functions at properties other than this one， right So for example。

 if we look at the probability of three elements collide， then we'd get a 1 over m squared here。

 And I'm not asking for that。 but I'm saying if you just look at pairs of elements。

 then it should be the random type collision probability so sometimes this is called two universal because it's about pairs of elements。

Okay， so you should have seen this definition before。 Whatition definition。Yeah， so I mean。

 collisions are bad， but collisions to be unlikely。

 and since're saying collisions is as unlikely as random fashion。Yeah。

 this is how much looser is this than like saying that it's a perfect hash function Well。

 if you're just focusing on pairwise collisions， it's exactly the same as saying it's a random hash function。

But if you look at like three elements or four elements， it could be significant。

 then there's no guarantee。So you should know this definition， I hope， and what else should you know。

 So you should know that。There are plenty of constructions of small families， small script Hs。

 So in other words， hash functions that can be stored in small space。

 for which you can also evaluate the function， little H on any domain element X quickly。So。

 for example， the1 I usually teach in undergrad algorithms is the one where you take a domain element。

 like an X。 you break it into small blocks， and then you take a random linear combination of the blocks of X。

 Okay， so you just pick coefficients in a linear combination at random。

 And then you take that modo a prime。 that's a universal family of hash functions。

 I'm not going to prove that now， I'm just saying that early， hopefully to remind you。

 but also just to give you kind of a verbal proof that it's not hard to come up with functions that satisfy this property。

 Okay， simple classes of functions satisfy this property。So that， I mean， there are other。

 there are even simpler hash functions that don't satisfy this definition。

 but I'm just saying it's not unreasonable to take for。

 especially for the purpose of provingrov a theorem， a simple hash function。

 we're going to take this as the definition。 Okay， it's kind of。More or less。

 the minimum property under which you could hope any theorems would be provable under any kind of you know。

 reasonable assumptions。Okay。All right， so that's one thing you should know about these families is they do exist and they're small ones and they're practical one。

 practical ones。 Another thing that you might have seen is that actually this property alone is sufficient to justify the performance of chaining Okay so remember。

 chaining is where you have a hash table and you have a linked list in each bucket。

 And you can talk about things that know what's the expected。

 say unsuccessful search time in a hash table with chaining。

 And it turns out if you tell me nothing about the hash functions that you're using。

 other than that the hash function was chosen at random from a universal family。

 that alone is enough to argue that as long as the hash function has constant load。

 the expected unsuccessful search time is constant。

 So universality guarantees constant operation time in hash tables with chaining with constant load。

 And again， don't forget the order quantifiers you you talk about hashing。

 you think about the data set being worst case and fixed upfront。

 And then you think about picking a random hash function from a family。For this worst case data set。

 okay， that's the usual quantifiers when you talk about universal hashing。So for chaining。

 you don't need anything more than this assumption。

But it turns out the plot thickens for some open addressing strategies and in particular。

 for linear probing。So what would be great。😊，So， again， so to summarize for chaining。

 universal simple hash functions in this sense are as good for the performance metrics that we care about as fully random hash functions。

 So we'd love to just say exactly the same thing for linear probate。😊。

Don't use a random hash function， just use a universal hash function。

 and you still get the one over one minus alpha squared upper bound on expected search and insertion time。

However。Not that long ago， just maybe a little over five years ago。We have the following result。

The point of this result says。That conclusion for chaining is not true for linearproin。

 If all you tell me is that your hash functions are universal。

 then it is not the case that you get an upper bound。 Fort about1 over1 minus alpha squared。

 You don't get any bound that depends only on the load alpha。So formally。There exists。

A sequence of ever， you know， we're going to let the range grow larger and larger。

 So there exist universal families， script H of has functions。And worst case data sets。

Meaning things to be inserted into the hash table under a random hash function from this family。

Of arbitrarily large size。Such that the expected。Time of the teeth insertion。Grows with tea。

Even as the load stays fixed。So despite alpha T over M。Stay in constant。

So being a little sloppy with the way I'm writing this。 really what this means is there's a sequence。

 Okay， of domain and ranges， capital ns and capital Ms， and they' get going to infinity。

 Okay also going to infinity is so M's going to infinity。

 So the hash table size is going to infinity。 So is the number of items that we're inserting。

 they're going to infinity at the same rate。 and their ratio is alpha and that stays fixed。

 Okay as t goes to infinity， despite the fact the load is constant。

 the expected time of the teeth insertion is also going to infinity。 In other words。

 the expected insertion time cannot be bounded above as a function purely of the load alpha。

 It also depends on the size of the data set。 and that's different than what we have for linear probing。

For fullyul random hash functions， it's also different from what we have for chaining for just universal hash functions。

Okay， is this the time where you can apply the smooth analysis to kind of get rid of this？Yeah。

 so that's sort of the spirit of this lecture。 Okay， so it's not so smooth analysis per se。

 It's not totally clear what that means。 Okay because for smooth analysis。

 at least as the way we've been talking about it， and everyone else talks about it， there's numbers。

 And you have these small perturbations to numbers。

 Everything with hashing is fully abstract There's just an abstract set N and abstract set M。

 So one way to interpret this lecture is what would。

 what would it mean to analyze hashing in the spirit of smooth analysis。

 And so I'm gonna give you what I think is a satisfying answer to that question。😊，Yeah。

 so it's not an accident that this lecture is adjacent to this mood analysis ones。

 very much in the same spirit。Okay， other questions。Is a constructive group。Yes。

 I even was tempted to put it on homework。 and I may torture some future year of this class with that。

 yeah。It's not， it's just like a little too long for a problem on a problem set。But， it's close。

You know， I'd probably have to give it like 50 points over all of the parts or something that put over the problems。

 And you've seen some 40 pointers， so。I still might do it sometime。But anyways。

 I encourage you to read it if you're interested。 it's， know。

 it's just roughly about a page of a journal paper page and a half。Okay， so what do we want？

So empirically， I should say。Empirically， this does not happen。 And I guess this is the other point。

 I mean， this is the other。All right， so empirically we also saw this。

 then we wouldn't expect some kind of smooth analysis to help us right so the other sort of triggered that should give you that know the same response Eliliott just had is you want to see a gap between what the worst case theory predicts and what you actually observe for real data。

 but that is the case here， So empirically universal hash functions。As good as random。

So almost no difference in many different senses from many different domains。 Okay， so a pretty。

 pretty robust empirical conclusion。So what do we think might be going on？Well。

 it's reasonable to draw the following cartoon and wonder if there could be a theorem that corresponds to the following cartoon。

So we've got our universal， not perfectly random， but universal hash function。And that's。

Mapping the buckets。So this is capital M。And we're observing that this is essentially uniform。Okay。

And not just uniform each time you insert something。

 but also just if you look at the whole joint distribution over everything inserted。

 even that's uniform， so you're even observing independence roughly between the different things you're inserting。

So this isn't true in general， right， So in particular， you know， this says that， you know。

 the distribution induced by universal families is not close to uniform。 if it was close to uniform。

 then we wouldn't inherit the one over1 minus alpha squared。 Okay。

 so the distribution looks different。 And it's popping up here in a different expected search time。

 But that's for a worst case data set。 And so especially coming from sort of the smooth analysis lectures。

Maybe we just have sort of mildly random。Again， we don't want to assume fully random data， One。

 we don't believe it。 And two， we're sort of hoping it's overkilled mathematically。

 maybe we have mildly random data。And if you feed that into a universal hash function。

 maybe that's enough to explain the empirical observation that you basically have a uniform distribution over the buckets。

So that's kind of the cartoon that we're hoping for。

 We're missing a little randomness in the hash function。

 but maybe that can be compensated forward with a little bit of randomness。

 we'd expect in realro data。Okay， so that's the target theorem。

 So the target theorem says sufficiently random data， which， of course， we have to define， again。

 you know， because they're not numbers。 We don't。 It's not clear what we mean to have a perturbations。

 sufficienticly random data and an arbitrary universal hash function gives us。

Performance as good as totally random hash functions。So that's actually true in a very， I think。

 interpretable and satisfying sense。All right。Before we're in a position to prove any theorems。

 we've got a couple of missing definitions， okay。So the first sort of the simpler definition。

 though I do want to be precise about is what does it mean to say a distribution is kind of squiggly uniform。

 Okay That's the first thing。 The other thing which I obviously need to define is mildly random data。

 so I'm going to do those in turn。Alright， so how should we define squiggle for distributions？ Well。

 actually， there's a zillion different ways to do this， okay。

But if you think about sort what we So what are we trying to accomplish。

 or what are we trying to say， We're basically trying to say it's like， look。

We're really trying to justify any analysis out there for hashing。

 which has made the assumption that things are fully random。 So you want to say， look。

 do your analysis for the fully random case。 And we want to say it'll translate automatically to slightly random data and universal hashing。

 and we don't really want to know even what kind of analysis you're doing。

 Just whatever you do with fully random hash functions is going to be fine。

So that motivates the following definition。Basically that， you know。

 if you look at two distributions， any event should have essentially the same probability under either distribution。

 Okay， because again， don I dont， I don't want to know what events you care about for your downstream analysis。

 okay。So that's going to be this assumption or this definition。So distributions D1 and D2。

 and let me just say now in this lecture。It'll always be the case that one of these is uniform on some set。

 and the other one is almost uniform。 That's going to be the only case we ever care about。

 So distribution Z1 and D2。On the same set say omega。Our epsilon clothes。If for every single event。

And we're going to go ahead and think of omega as finite because that's we need the probability under one distribution。

Is the same as the probability under the other distribution up to plus minus epsilon。Okay。

So the difference in the probability is assigned by the two distributions to any one event。

 is at most epsilon。So in other words， whatever events you care about and you've bounded under the fully random assumption。

 the same thing is true。Under other assumptions， up to an epsilon。

So this is what the sququigle means。嗯。Now。So I've stated the definition in the form where I think it's clearest that this is what you want。

 given why we'rerov this theorem， which is to go back and forth between the fully random case and universal case。

 let me actually restate it， or rather explain to you how you're going to prove it can be restated in a way that's easier for the proof it turns out this is basically just the same as an L1 distance between these two distributions。

So this is not hard， I'll ask you to prove it on the homework。

Which is that two distributions are epsilon close if。Viewing them as vectors。Over omega。 Okay。

 so think remember， think of omega as finite and finite。 We only care about the finite case today。

 So then， you know， what's a distribution。 It's just how much probability it assigns to each you know。

 element in the finite set。 So you can think of distribution as a vector indexed by omega。 Okay。

 given two vectors， you can talk about their distance in a various norms。 like the O1 norm。

Epsilon close just means that in the L1 norm。The two distributions are at most two epsilon apart。

Okay， and that's actually a and。All right。It's pretty easy to prove basically the key insight is that what is it saying。

 you know， this is basically saying。Even for a worst case event， so because it's for all S。

 even if an adversary chooses the S to make the probability between these distributions as big as possible。

 even then it differs by at most epsilon。Well， if you are the adversary， if you think about it。

 it's actually pretty clear which S you're going to do to maximize this probability distinction。

 You're just going to look element by element and omega and you're going to say， oh， well。

 let's look at exactly the ones where D1 puts more mass on it than D2。

 And I'm going to collect all of those into an event。

 And that's sort of the worst case discrepancy between these two distributions。 And actually。

 that's just half of the L1 norm if you think about it because of the two distributions some to the same thing。

 I'll let you work that out in the homework。But that I mean， the point is the proof is short。Sorry。

 there should be a one there。All right。So this is， this is the conceptual point of the definition。

 And then this is the mathematical version of it that we're actually going to prove。 Okay。

 we're gonna to show that you know， random hash functions， those correspond to some distribution。

 mildly random data plus universal hash function correspond to some other distribution。

 And then thell1 norm between those two distributions viewed as vectors is small。Any questions。Okay。

On the next definition， what would it mean for data to be mildly random。So。

Consider a random variable with some range。Again， we may as well think of it as a finite range for our purposes。

For example， R could be buckets。Now， the first idea is actually。

 even though there's no perturbations。If you think about the version of smooth analysis。

 the type of perturbations we were using the past few lectures， actually。

 that definition does make sense， even totally abstractly of what we're talking about now。

 What was the definition， The definition was the distribution shouldn't be too spiky。

 We were there thinking about sort of continuous numbers。

 So we're talking about the density function being bounded above at every single point。You know。

 now we have this finite case。 So we have like a probability mass on each element。

 We can again say not too spiky， nowhere in omega or I guess nowhere in R。

 can the probability assigned to R be too large。 That's totally analogous to this density upper bound。

 We had the last three lectures So that's a natural first idea。🤧。So the biggest probability。

 so the biggest spike that you ever see。Assigned to a particular range elements that X could take on。

Is it most some Delta？Delta here is a parameter。 so the smaller delta is the more random。

 the more diffuse this random variable capital x。Actually， this is a totally fine definition。

 It turns out we're going to use a different definition。

 not because there's anything really wrong with this one。

 but just because we'll use a definition which is even weaker， and it's no harder to work with。

 So we'll just get stronger results。But there's again， nothing wrong with this definition。

 This is a good definition。So here's what we're going do instead。Idea number two。

Instead of assuming this。We're going to say， well， consider this random variable x， capital X。

 And suppose you instantd it twice。They have two copies， independent， same distribution。You know。

 once in a while， both of the copies will take on the same value。Okay so this is like， right。

 what it is what is， Sometimes it's not， sometimes you get different values。

So we're instead of saying the maximum probability。It's going to be a most delta。

 We're going to say the probability that two independent copies of x take on the same value is the most delta。

So formally， we look at all the values that X could take on。And we say， well。

 the probability that both copies of the random variable take on that value is just the probability。

That one copy takes it on squared because they're independent copies。

And we're going to think about that being mounted above by Delta。好看。

So take 30 seconds to convince yourself that if the first， sorry， if the first condition holds。

Then the second condition holds。For the same value of Delta。

So just stare at it and convince yourself that that's true。

So this is called the collision probability。Okay， again。

 because it's the probability that two independent copies collide， I。e。 have the same value。

So why is that true was so suppose this holds， so suppose every single probability of x equal I is bounded above by Dlta。

 okay？Think of this as that means so break this into two independent copies of itself。

So you take the first copy， you can bound every one of those by Dlta。

 you bring Dlta out in front of the sum， you're left with a sum over I。

 the probability x takes on the value I， so distribution says is equal to 1， so that gives you Dlta。

So when this condition holds， this condition holds as well。 Okay， so this is a weaker assumption。

 So if we prove positive results under this assumption， it's better。

 it's the more sweetened positive results。 and that's what we're going to do。Any。

 this is kind of like the max norm versus the L T norm， right。

 I't it like the maximum norm was bigger， Let's see。 So the， the max norm。

It's always going to be smaller than the L2 norm。But I mean，'s on some levels。Same kind of stuff。

I mean there's different ways to take vectors and squeeze them down into numbers you know。

Some are bigger than others and usually can control how much bigger one can be than the rest。Okay。

 so this is gonna to be our definition of sort of a single data element。 Okay， I you， you。

 I owe you a more full blownown definition。 But this is， this is really， this is important。 Okay。

 the rest kind of falls easily from this。 So think of this is like a single data element。 Okay。

 our definition of being sufficiently random is that the collision probability is not too big。Okay。

So just to get a better， Okay， yeah， So just some more examples is to get a better feel for this。

 Okay， so when would these be different。Okay， so I argued that whenever this is the most Dlta。

 this is the most Delta。 So let's see that the converse is not true。

 just develop your intuition further。Imagine you had a random variable capital X。

 so suppose you had like a really big range。 So the range was huge。And maybe like half the time， O。

 X took on the value 1。And then the other 50% of the time is uniformly distributed across like a million different outcomes。

Well， then it's pretty obvious that this number is a half。Right。

Because it takes on this one probability of probability a half。 On the hand。

 this is going to be like a quarter。Okay， because now both copies have to take on the value one for them to collide。

 In principle， they could collide on one of these other outcomes。

 but it's super unlikely it's not going to happen。So that shows that indeed。

 the closure robot can be smaller than the highest of the probability masses。Okay， and now。

 but at the same time， I encourage you to keep in mind。Sort of a canonical random variable capital X。

 a canonical sort of data elements where these happen to be the same。

 there's actually no difference between the two。 So， for example。X， uniform。Over a subset。You know。

 subset S。Of some size K。Is that describe describe of all cases where they are the same？I believe so。

 I think so yeah。So， and I guess just to connect this to the other notation I'm using， think of。

 in fact， I probably even should have done this。 Basically， think of R。As being equal to capital N。

 what was capital N， that was the domain of what we were hashing。 Okay So x is like some random。

 know IP address or some random news article or whatever it is， we'rehing into a hash table okay。

And so， you know， in worst case， it could be any element of capital N。 Now。

 we're trying to say it sort of sufficiently random in some sense。

 So one way you can think about being sufficiently random is you're like， well。

 maybe an adversary first picks a set of size capital K。

 and then nature picks like something uniform at random from capital K。Now， if capital K has size1。

 then it's not random at all， right So then the adversary picks whatever element it wants and it's worst case。

 But as the adversary is forced to pick a bigger and bigger set K and the nature picks randomly from it。

 then this element is more and more random。 And indeed。

 if x is uniform and random over a set of size K， then this delta。Is going to be exactly one over k。

In both cases。 O， so the bigger， the bigger the you know， secret subset from which it's drawn。

 the smaller the value of this delta and again， sort of。You know， a slightly cartoonish version。

 you might want to think about this assumption is we're going to do the analysis It's like。You know。

 we're gonna assume that we know that the adversary had to pick a sufficiently big set。

 sufficiently big set S。 We just don't know what it was。

 So we want to basically say no matter which set S the adversary picked from which nature that draws uniformly random element。

 It doesn't matter which it is hashing will do great。 And again， keep in mind， capital N is huge。

 Again， like all I addresses of like all news articles or something like that。

 So there's zillions and zillions of different choices of know a secret set S from which you know nature could be picking something。

 So there's a zillion different distributions， we're trying to argue a single hash function is handling all at once。

 That's sort of the power of the power of this approach。 Anyways。 So if I lost you just， you know。

 the key points here are this is our definition of a given data element being sufficiently random。

 The collision probability is sufficiently small。 as a parameter。 we'll talk more about in a second。

 Canonically think of this data element as you know this first some very small subset of capital N。

 And then it's drawn uniformly and random from that。Okay， questions。Alright， so， of course。

 we're not just inserting one thing into a hash table。

 We're inserting a bunch of things into a hash table。

So I need to somehow extend this notion of a single data element。

 a single element from capital N being sufficiently random to a whole data set。

And so that's done in a reasonably natural way。And then this is going to be our final definition of sufficiently random data set。

哇。And so this is called a block source，'s not important that you know this， but just。

For completeness， a block source with EntropyK。This is by definition， a sequence of random variables。

With range n。And again， you want to think of this as being the slightly random elements that are going to get inserted into a hash table。

 That's the point here。I's a sequence with what property。Such that。Basically。

 whenever you're about to insert something。What you're about to insert is a little bit random in the sense of having small collision probability。

 And more， it's random， even you know， conditioned on the stuff you already inserted。

So you already inserted a bunch of stuff， and you want to make sure that even knowing what the previous part of the sequence is。

 you still have sufficient randomness left in what you're about to insert now。So for all I。

So for everything you insert。Conditions on the previous stuff。Conditioned arbitrarily。On x1 up to x。

 I -1。The collision probability。 So again， remember， this is just sum of these squares。

 collision probability。The Xi condition on this stuff is at most won over。Two of little k。

So this is a little K。 I'm going to stop using little Ks。 and I'm going to use big Ks。

And big K is this。which is the same notation I was using for big K over with the uniform over subsets。

So again， collision probability of most1 over k。 so weaker then， but you could know for the lecture。

 think of it as being roughly equivalent to the probability that it takes on any given values of most one over capital K。

All right， so any questions about that？Seem reasonable。

Because does everyone understand it mathematically， The definition， that's the most important thing。

Correct。Okay， so this is， this is the final definition。 Okay， So now， given this definition。

 we can actually prove the theorem we want。So let me erase the cartoon and replace it with the formal version。

So the theorem。Which is from 08。Mit and Maer。回当。Says that。Let x1。

 the Xt be a block source with EntropyK。The as above。Let H be universal， no other assumptions。Then。

The joint distribution。Of the hash function as well as the buckets to which that hash function maps all of these elements。

Is essentially the uniform distribution。So again， essentially， that's the siggle。

 so this should be something close。I'm going to write down a slightly complicated expression here。

 immediately after finishing the theorem。 I'll help you interpret this expression。

So before I do that， though， let's just make sure we're type checking everything。

 So I'm claiming the joint distribution of this stuff。 again， what is this stuff。

This is the hash function。 The hash function is chosen uniformly at random from some from universal family script H X1 through X T。

 This is what's being inserted into the hash table under this randomly chosen hash function。

 These by assumption are also random。 Okay， theres randomness and H， Theres randomness in the Xs。

This vector， this is the hash function。 These are the buckets to which the data elements land。 Okay。

 so the Xs lie in capital N， the H of the X's lie in capital M。

So when I say close to the uniform distribution， uniform distribution on what？Well。

 the first component， this is just a member of the hash function family。So that's a script H。

Each of these is a bucket。 So Each of these is an element of capital M， and there's T of them。 Okay。

 so times M to set M。Product Tfold times。 Okay so this is the relevant uniform distribution to which to compare this。

可以。O。All right， so。So hopefully you're going to at least to some degree syntactically match what this says to the cartoon we just had。

 we wanted to say sufficiently random data plus universal hashing gets us essentially random fully random functions。

 So here's the sufficiently random data， clearly it's a universal hash function and we know closeness has something is the swill or the uniform distribution。

Now， what do the parameters have to be for this to be meaningful， Okay， so it turns out actually。

 this is good， but it takes a little bit of thought to figure out why this is good。

 Let's just make sure you remember what everything is。So T。

 this is how many things are being inserted into the hash table。 Okay。

 We're talking about linear probing。 All right， So M is the number of buckets， slots。

 We're talking about an open addressing hash table。

 So there's going be at most one element inserted per slot。 Okay， so T is in most M for sure。

 So think actually， if T equal to M。 That's sort of the worst case。 Okay。

 so just make those the same。Now， K， this measures how much randomness there is in the input。

So the bigger K is， the more random the input， the smaller this is， which makes sense。

 the closer we are to uniform， the bigger K is the more random the input。 So the question。

 the reason we want some really precise formula is we really want to know how much randomness is necessary in the data to get epsilon close to uniform。

 Okay， And then there's going to be some functional form。

 saying how big K has to be as a function of epsilon。Okay， so to interpret。So to get。Epsilon close。

So you now you just solve， you just set this sel to Epsilon and you just solve。And what you get。

Is that you need K to be at least。M T squared over4 epsilon squared。Okay。And again。

 think of T as just equal to M。so you get an N cubed here。Alright。I。e。 if you take logs。So remember。

 we have this notion of entropy。 So this is just， so log of this is the entropy in the data。 So I。e。

 log K。Is at least basically three log m。Again， I'm setting t equal to M。

Three log m plus low order of terms， so plus stuff。Okay， so think of epsilon as some constant small。

 like 0。01，1 or 。01， all right？So how should you interpret this。

 let me give you two ways to interpret this， right？So remember， capital M is the number of buckets。

 and we want to be sort of uniform over the buckets。 So if you think of the red expression。

 you sort of think， well， you know， certainly we're going to need like log M bits of randomness to spit out anything which is uniform over M things over M buckets。

 right So if you think about a log M is sort of an obvious lower bound on the entropy required to expect anything to be close to a uniform distribution。

😊，Right。So what we're saying is basically the amount of random is necessary is only triple the number of bits that's sort of clearly a lower bound on what's required。

 So that's the first inkling that we're doing pretty well。 Actually， Okay。

 so we're then a constant of some natural lower bound。Here's another way to think about it。

 So remember， I encourage you to think about capital X， these data elements。

 One another way to think about how we're parameterizing the randomness is the adversary picks sort of a secret set and the nature picks something uniform from it。

 Okay But again， the whole problem is， our hash function is independent of the secret set chosen by the adversary。

 So we're just picking random hash function， We're hoping that no matter what secret set。

 the adversary picks。 So it's like a slightly random in a random variable。

 it gets smoothed out automatically to be uniform over the buckets。 Okay And remember。

 capital N is huge。 Capital M is small。😊，OkayAnd so what this says is that if we just force the adversary to pick uniformly from a set of size。

 at least M cubed and again， think of like n as exponential in M。 if the M is the number of buckets。

 that's maybe like a million， know， n is maybe like all possible know。

 texts of 500 characters It's something astronomical。

 So So there's a zillion different things that this subset of size K could be。

 But it doesn't matter what it is as long as it has size at least m cubed。

 or hash functions is going automatically smooth this out and gives a distribution uniformly over the buckets。

So those are a couple of different ways to interpret this theorem and senses in which we're doing pretty well。

This is the theoretical lower bound of prom。Yeah， there is。At least for the way I've stated this。

So the notes include some references， I'm not going to go into this so you can ask you know can this be improved right so it's fine okay so it's reasonable that's that's all I've tried to argue and it can be improved a little bit。

 It's also known it can't be improved a lot and I'm not going to say more about it either those two statements。

 the notes have some references about where you can read more。So it's not the absolute optimal。

 but it's， you， I think of this as enough to really give a convincing explanation of good empirical performance in lots of different applications。

 which is kind of what I wanted。Okay。One other sort of clarifying point just about this theorem statement。

 One thing you may be thinking is you' paying close attention， you might think it's a little weird。

You know， which is that the statement I've written now is maybe a little bit different than what you would have thought。

If you think about it， what really we care about。Is this stuff。RightSo when we say， you know。

 stuff's getting hashed just as good as if it was a fully random hash function， we're always saying。

 well， you know， if you look at the buckets to which everybody goes to。

 they're both uniform and they're also all independent of each other。

 So that's really just talking about the joint distribution on the buckets to which everything gets hashed。

 And I also just sort of threw and I said， oh， well， even sort of the hash function here。

 even this bigger joint distribution， the uniformly a random。 so I mean。

 this is a stronger statement。 So it shouldn't bother you too much。

 And it turns out to prove the theorem， it's really a lot nicer to have the stronger statement for an inductive hypothesis。

 Okay， and because you're proving on the homework。 the inductive step anyways。

 that's one reason you want to you want to have this here。😊，Okay， good。

 So that's the main results and。How to interpret it。

So that's how we translate the cartoon of sufficiently random data。Namly a block source with entropy。

 at least log of this amount。Plus， universal hash functions， no matter what they are。

Get you epsilon close to uniform。So any questions about that？Before I talk about the proof。Okay。

All right， so the proof is basically。I mean， this， this follows almost immediately， actually。

 even though this is a paper from 0，8， it follows almost immediately from a result in 89。

And it just took a lot of time for anyone to realize that developments going on in what's called pseudo randomness were relevant for the analysis of passion。

 Okay so the key tool。Is a well known result from。Theoretical cryptography called the leftover Hahlema。

This is due to Pagliazzo， Levin and Luby in '89。And what this is。

 this is simply this statement for the special case where t equals 1。Okay。So in other words。

 what the leftover hashlemma says， it says， suppose。

You have a single random variable with low collision probability。 Okay。

 collision probability at most one over capital K。That's the hypothesis。

The other hypothesis assume that you have this randomly drawn hash function from a universal family。

Then the joint distribution on the hash function and the hash value of the data element X is t is now1 is1 half times root M over k close to the uniform distribution now it's the hash functions times1 copy of M。

Okay， so that's exactly the leftover hash level，And so I will prove this to。 I。

 I will prove to you the leftover hashlema and。In homework number 8， I'll ask you to extend。

To the general case， by induction。Allright， and you'll notice， I mean， as you extend it by induction。

 you do lose something in the closeness parameter。 Okay。

 so you're having linear loss in capital T in the closeness parameter。 It's not a trivial induction。

 It's actually a pretty tricky induction。 Okay， but I'm going to ask you to think about that on the homework。

 right。The original motivation of leftover hashlemma。 So basically。

 the reason they cared about something like this， they were thinking where you have a secret key。

Like 32 Bs or whatever。 shows until uniformly a random。 Okay。

 and it's great because you can foil these adversaries because they can't guess your secret key。

But then at some point， you have an inkling that it's been compromised。

 So an adversary has figured out 8 Bs of your secret key， But you don't know which are the8s。

And so the question is you have to throw it out and just sort of redo a totally new secret key。

 or can you actually extract， despite the fact you don't know which 24 bits are still good。

 can you somehow extract 24 close to that bits of randomness from it。

 And so basically this Lema was saying use a universal hash function apply it to the partially compromised key。

 and you're going get an uncompromised， perfectly random although shorter key。

 commensurate with the number of bits that the adversary hasn't seen。So that was the original point。

So here's the proof。 The proof， I mean， it's really just kind of calculations， but it's a very。

 it's a very slick and almost sort of pretty arrangement of calculations。 So let me show them， too。

First， an overview。So the first thing， and really， this is the main step。Is we're going okay。

 so what are we trying to prove， remember we're proving this with t equal 1。

The conclusion says we have to say， we have to say that something's close to uniform。 Okay。

 So we're going do this in three steps。 So the first thing were we're going to do is we're going to say。

 well。You know。I'm not going to promise anything about it whether it's close to uniform or not。

 But at least for starters， I' going argue that the collision probability of the distribution is small。

Okay。So we're going to bound the collision probability of the joint distribution of the random hash function and the hash value of this element。

And this is where we use all of our hypotheses。 So we use the fact that this is random。And universal。

And we use the fact that x itself。Has low collision probability。 Okay， remember。

 that's the hypothesis。 This data element has low collision probability。 And we're saying that。

 together with universality implies that this distribution also has low collision probability。

So that's sort of the main step。But it's not really， know what the theorem states。

 the theorem asserts closeness to a uniform distribution。 Okay。

 so we know that if you think about it， or it's easy easy to see。

 if you have something that is a uniform distribution。

 then its collision probability is really small。 So now we have to reverse that。

 We have to show some kind of converse。 the only way you can have low collision probability is by being close to uniform。

So that's steps two and three。So，2。So first， we're going to apply closeness。

To uniform in the L2 norm。And then it will be easy to go to the L1 norm and recall from early in the lecture that the closeness that we care about is the same as just saying small L1 norm。

So then it applies epsilon close。It's a uniform。Any questions。O。So。On the step  one。

So let's look at the joint distribution that we care about and let's compute its collision probability。

 okay。So let's again， let's just make sure we understand exactly what is this distribution。

 we pick a hash function capital H， uniformly random it from script H。

We instantiate our random data element capital X， and we apply H to x。

 Okay so the first components is the hash function。

 The second components is an element of capital n right So x is an element of capital n。

 H of x is an element of capital n。 And so that's the random variable we're looking at。

 Remember that the collision probabilities defined as you take two independent copies of the random variable。

 and you see if they're exactly the same。 Okay so remember one copy of a random variable here is a hash function and the hash value of an element。

 Okay so that pair is one Id sample。 We're gonna to look at two Id samples of that type and ask。

 when are they exactly the same。So。By definition。A collision probability。

We take two copies of this random variable。And we say， when are they the same？So probability。

We have H， H prime。 These are drawn uniformly from capital H。We take two copies of capital X。

They both lie in capital N， and this's from whatever distribution governs capital X。

And we want to know。What's the probability？That h， h of x equals。H prime， H prime of x prime。Okay。

 this is the definition。 This is one of the definitions of the collision probability。

 We want to upper bound this。 when I say it's small， close to 0。We've got a few things going for us。

 We've got the fact that X has a distribution with lowcc probability。

 We have the fact that H is universal。Okay， so first of all。For this。To equal this。It better be。

 at least be the case。 A necessary condition is that the first components match。

H and H prime better be the same function in our two draws。So。Probability that h equals h prime。

Times。Probability that。The second components are the same。

 given that the first components are the same。Right。So this first term is not hard to understand。

H and H prime are both chosen at random from script H。

 So what's the probability that end up being exactly the same thing， over H1 over the card out of H。

Okay。Just the usual close and probability for uniform distribution。Good。So now let's zoom in on this。

 Okay， and now things are a little bit more interesting， right so。Now， we say， okay。

 given that H equals H prime。 Okay， so I'm still writing H and H prime separately。

 but these are really the same function now。 That's what we've conditioned on。So this could really。

 these could be the same thing for two different reasons。 Okay， so first of all。

 I might get really unlucky and just actually also choose x and X prime to be exactly the same。

Could happen。Or maybe I choose x and x prime to be different。

 but they happen to collide under this chosen hash function。So that gives you just two cases。

So zooming in on this。So first， let's just say， well。You know。If x equals x prime， the game's over。嗯。

家只两豆。And then on the other hand， if x and x prime are different。

So now I'm conditioning both on H equal h prime and x not equal to x prime。 That's case2。

 There is still some probability that H of x equals h prime of x prime。

So let's try to understand these。So。First of all， how about this？So the first thing to notice is。

 H and X are drawn independently。So this is irrelevant。Condition totally irrelevant。

So it's just a probability that these two copies， these two instantiations of the random variable capital x are the same。

 also known as the collision probability of the distribution from which x is drawn。

 And so by assumption， this is the most one over k。So that's where we've used。

 so let's track the assumptions as we've used them here。

 The only assumption we're using is that H is drawn uniformly random from script H。

 We're not even using it。 It's universal doesn't matter。Here。

 we're explicitly using our sufficiently random data assumption。

The fact that it has low collision probability。Let's look at the second term。

We're now conditioning on the fact that H and H prime are equal。 Okay， we don't know what they are。

 They're random， but they're the same。 And we're conditioning on the fact that X and X prime are different。

 okay。So now further fix a value for x and x prime， distinct，Now。What is this， and again。

 remember h equals h prime， that's the condition。Well so H is drawn uniformly at random from script H and H is universal。

 so whatever x and X prime are just by virtue of being distinct。

 we know that this collision probability by universality is at most as large as random hashing， I。e。

1 over capital M。Okay。So this。Is it most one over capital M？By universality。

taSo Delta was just a parameter。And so， if you recall the definition of a block source， I mean。

 it's the same。 So Delta and K are just to read you know， different definitions， basically。

Or different sort of names for the same parameter。So I guess what I was calling Delta at one point。

 I'm now calling one over capital K。Okay， so what did we just prove，'s so when the dust settles。

 what do we get。We conclude that the collision probability。Of H， H of x。Is bounded above。

 so don't forget we have this leading one over script H。

And then we have parentheses1 over K plus one over Carinal event。

RightThat that's what we just proved。Okay， so that step one。Okay。And we've used all our hypotheses。

 so now it's just a little bit algebra from here on out。Let's just， I mean， just， you know， to get。

Sort of for morale， let's just try to sort of measure how well we're doing， okay？

So like what is this， is this a big number or a small number， I mean， they're all reciprocal goals。

 I guess that's good， can't be too big， maybe。What are we trying to do。

 we''re trying to prove that it's close to uniform。 So let's actually ask ourselves。

 what if it really was uniform？What collision probability would we be getting instead？Okay。

 don't forget uniform over what。 Okay， so the relevant space here。

The first component is a hash function， the second component is a bucket。

So we're trying to prove close to uniform on this set。

Collission probability on this set is just one over the cardinality。

 This is the computation we'd be doing over and over again。 So if it was totally uniform。

 we'd have the same thing just with no K。Okay， so we're just picking up this1 over k。So it's worse。

 But you got to believe that， you know， like if one over K was sort of not， you know。

 quite a bit smaller than one over M， you sort of hope we'd be fine。 And it's true。

 We just have to be honest and do the computations to prove it。Okay。So that's step one。

So now's now we need to go from low collision probability and we need to show that the only way that can happen is if you're close to the uniform distribution。

 and so let's start by proving that it can only happen if you're at least close in L2 norm to the uniform distribution。

So step two。So let me just， let me sort of switch notation just to sort of have fewer letters for a second。

 So just in general， suppose you have。A distribution P on omega and Q equals uniform。On omega。

 so for S， omega is this， script H times capital N。 I've just renamed it for a second。

And now what we want to do， let's compute the L2 norm as a function of the collision probability of P。

 Okay， because we know we have a bound on this。 We want to have a bound on distance to Q。

And so actually， what I want to do is。Okay so remember。

 we're now interpreting these probability distributions as vectors indexed by omega。

 when we talk about norms。Or distances。So let's actually do the norm。Two norm squared。

So this is just sum over everything in mega。P omega minus q omega squared。And now， expanding。Okay。

 so what I'm doing right now has no content。Okay。So that's just a little bit of mechanical stuff。

 but now let's see what we got。Okay，And actually， when we got all of these terms we can interpret really easily。

 Okay， that's why I did this computation。Let's start with this one。So what's this？Again。

 the notations changed a couple times。If you can keep track of it。

 this is something we know and love。So that's just the collision probability。

 Again remember before we were saying， you know， sum over the range elements of the probability that the random variable takes on that value。

 And again， is it clear what I mean here。 So， so P here is just a vector indexed by omega where the components of the probability mass that this distribution puts on that particular little omega。

 so in other words， it's just the probability of the random variable with this distribution takes on that particular value。

 Okay， so before we had sum of a I probability that x equals I， This is exactly the same thing。

 Just a notation switch。😊，So this is the collision probability。

So collision probability of distribution P。Don't forget， Q is not any old distribution。

 Q is the uniform distribution。 Okay， so what we're doing is we're doing a computation。

 which becomes unusually easy for us because we're comparing ourselves to the uniform distribution。

 That's the point of this， okay。So if Q is uniform， what does this wind up being？Well。

 what's each term， right， So what's Q， right if it's uniform。

 then each Q is one over the size of omega。 So if that squared is one over the size of omega squared。

 and there's omega card of omega terms。So this is just going to be one over cardalality omega。

So this is a two here。So， and now once again， this also becomes very easy， this final term。

Because Q was uniform。Every single Q is equal to one over the car of omega。

So we can just bring that out in front of the sum。Now， a sum over the massive P over omega， that's。

 of course， equal to one because it's probability distribution。So this last term is just minus。

Two over omega。Okay。So the norm， the squared two norm。 And this， of course。

 is exactly why we're doing this intermediary step for the two norm is because everything just magically becomes simple。

 The squared two norm is just the stuff。 Okay， collision probability of the non uniformform distribution minus the reciprocal of the size of the set that you're talking about Now。

 for us， you know， what are all these things mean for us。 So omega for us。😊。

Is the hash functions times the buckets， that product space and the collision probability bound。

 the distribution we care about is what we computed in step 1。Okay， so this first term， these P's。

 that's just where we concluded step 1。And now our omega is just the size of script H times the size of M。

Okay。So， for us。What we proved is that the squared- so don't forget。

 we had a square at the beginning the whole time。So the squared2 norm， or let's say squared， yeah。

Squared L2 distance。Between us and uniform。Is。At most。Let's bring it up here。

inus1 over co n of H times coalityity of M。That actually will just cancel。This term。

So I'm combining these， I get a minus1 over omega， and that exactly kills off this。

So equals1 over the cardinality of H。Times K。Okay。And about this makes perfect sense。

 right because at end the step one， we said， well， what would things look like if we were uniform。

 Well， the K wouldn't be there， okay。And so while we get in step 2。

 we you could be distance to uniform， you'd sort expect to get 0。 So that's what we're getting here。

 right， So the fact that our collision probability differs from that of what uniform distribution by this one over K is just showing up and that our L 2 squared distance to uniform is one over。

😊，The number of hash functions times k。All right。So now。

 step 3 is just to go from the two norm to the one norm。That's something we've done before。

 so for example， when we were talking about compressive sensing。

 we had to understand a few things about how much bigger the one norm could be than the two norm。

And I'm going to ask you to recall。From that discussion that if you're in D dimensional space。

you have any vector V。 so the one norm can only be bigger than the two norm。

 but it can only be bigger by a root D factor。 and it's tight when you have all equal entries。

 like the all ones vector。But。Yeah。是。So again， the one norm for a fixed vector。

 the one norm is going to be bigger， but。The extent to which is bigger is maximized with all equal components。

 Okay， so that's going to be root D and D dimensions。Now for us。What's our dimension。 Or remember。

 our vectors here are just indexed by hash function bucket pairs。 Okay， so for us。

 D is just the cardinality of H times the cardinality of M。Okay。We already computed the L2 norm。

 specifically L2 norm squared。 that was at most one over a script cardinity of H times k。So for us。

L1 distance to uniform。So let's take the two norm。 So remember， this is the two norm squared。

So we get to take the square root of that。Times the squared to the dimension， which again for us。

Cin out of h times。Conode now is M。They just cancel。And over care。嗯。So remember。

 what we're just doing the tea was one special case of the main theorem。So that's why。Okay。

 so there's still sort of a slight discrepancy because there's just one half。

 But recall epsilon closeness corresponds to O and distance to epsilon。

 That's one of the things can ask you to prove in the homework。 So that's why， you know， with T1。

 that's why you have an extra one half here that you don't have here。But otherwise， that's it。

 So L1 distance uniform most square root m over k for t equals 1。 And again。

 there's this induction on the homework， which says it's not just true。

 not just this 89 result is true just for a single random data source。

 But anytime you have a block sequence with entropy of at least K。 again。

 that means even condition on everything you've inserted so far。

 you still have the sufficiently diffuse distribution of what's left。

 meaning inclusion probability of most whenever K conditionally。

 that's enough to get to epsilon close， as long as k is at least like triple the amount of entropy that you need。

Any final questions？Okay， see Monday。