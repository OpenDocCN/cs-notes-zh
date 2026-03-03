# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p18 -18-Lecture 18_ Five Essential Tools for Analyzing Randomized Algorithms). -BV14CAUeUEPj_p18-

Okay。So the purpose of today's lecture is to talk a bit about randomized algorithms Now in your previous study specifically 109 and 161。

 you already learned some of the tricks of the trade of analyzing randomized algorithms you probably saw applications to the running time of quick sorts and perhaps some analysis of hashing as well Now there's also this class 265 which is entirely about randomized algorithms so sort of like more than you ever wanted to know about randomized algorithms It's an awesome class so I encourage you to take it But so in 261。

 we kind of have this one lecture which is sort of a bridge between you know the introductory stuff in 161 and 265 and specifically you know there's some tools which you don't learn in lower levelvel classes most specifically what we'll call the turnoff bound which get used all the time and in particular。

 any future algorithms course that you'll take you'll need them and also a lot of machine learning classes you needing to know some of these probabilistic tools as well。

So you know you should have you've seen probability now in many previous courses。

 so just to kind of like remind you what the standard setup is， but again。

 hopefully your intuition is regionally well developed for this stuff so we have a state space so for us we're thinking like there's a randomized algorithm it flips some coins and apointing the state space is just the sequence of heads and tails that the algorithm happened to flip so mega sort of captures the randomness which you don't know a priori。

A random variable。 that's just a real valued function defined on the state space。 So again。

 for us we usually think about an algorithm。 So say like for a fixed problem instance。

We might be interested the function of the running time。

 So as a function of the coin flips made by the algorithm。

 what is the running time of the algorithm or you know as a function of the coin flips。

 what is the objective function value of the solution produced by the algorithm。

 Those are the kind of random variables that we care about in the analysis of algorithms And of course。

 like the first thing you kind of might want to know about a random variable is what is it on average so a random variable will take on different values at different points in the state space。

 But you might want say on average over everything that might happen， know what's the average values。

 So that's just the expectation so you just average the possible values that the random variable could take on weighted by whatever probability distribution you're assuming on the state space。

 so for example， if it's just uniform random coin flips。

 This is all just going be with respect to the uniform distribution。And then finally。

 you know just to remind you about this key concept of independence。

 an events remember is just a subset of omega。 So an event just tells you whether sort something happened or didn't happen。

 So if you look at if you look at the probability of the intersection or conjunction of two events if theyre independent events by definition they factor this is the definition of what it means for two events to be independent probabilities factor。

 And then if you have two random variables which are independent。

 meaning that the events of them taking on any particular pair of values are independent events。

 then expectations factor。 so this is true for independent random variables。

 notice that neither of these is true of they're not independent random variables so imagine you had an event E1 and then E2 was the complementary event。

 So exactly one of e1 or E2 happens， but not both well then on this side you'd have a zero because they're complementary events on the right hand side you'd have a positive number times a positive number so the equality would fail similarly here。

 if you had x and y with the indicator random variables。ary events。

 this side would be zero and this side would not would be positive。 Okay so certainly。

 you know certainly plenty of examples of things which are not independent。

 We'll see examples today of both independent and non independent random variables。And so。

You know using sort of approximation algorithms is kind of the framing device。

 we're going to talk about five kind of really essential tools for the analysis of randomized algorithms。

 a couple of these you've seen before， so I'll treat them very quickly。

 but maybe at least one or two haven't and so we'll spend more time on those So here's number one the first of our five essential tools linear of expectations。

 super simple but super useful so you've seen this before let remind you what it is。

And then we'll put it to use in approximation algorithms in a second。

So suppose you have n random variables， all on the same state space。

And linear expectation just says you can take sums and expectations and interchange them to your heart's content。

 you can just like swap them back and forth and it's the same number。And so the point here is that。

The reason it's so powerful is there's no independence assumption。Okay。Not necessarily independent。

Oh yeah， what's the statement so the statement is。The expected sum。

Is equal to the sum of the expectations。So like when I teach CS161， I give 20 lectures。

 I put a box around exactly one thing in the entire quarter and this is what I put a box around because sort of like the bang per buck is sort of how easy it is versus how useful it is is sort of off the charts。

 I'm not going to prove it。 The proof is sort of trivial。 You just expand the expectations into sums。

 you reverse the order of the double summation。 This is what you get okay。What else。Okay， right。

So that's the key thing to remember about linear of expectations。 They need not be independent Now。

 why should you care， What can linear of independence excuse me。

 linear of expectation do for you Well here's sort of the canonical use case in a lot of things。

 but particularly in algorithms， imagine you have some random variable that you really want to understand。

 like the number of comparisons that quick sort makes for example。

 or the number of iterations that a randomized min cut algorithm takes to terminate something like this。

Often you can take a complicated random variable that you care about。

 like the number of comparisons used by Quick sort and write it as a sum of much simpler random variables。

 often， in fact， just 01 or indicator random variables。So linear of expectation then says。

 if you want to understand the expectation of this complicated random variable。

 that task reduces to just understanding the expectation of each of the simple constituent random variables。

 then you just add it up and you get the answer that you want it so if you like think of this as a reduction from complex random variables that are really sums to just analyzing the sums independently。

And so this is all kind of very elementary， but this already gives us actually some pretty interesting results again you've seen some in previous classes。

 but let me give you an application and approximation algorithms。

Or this is the only tool we need okay？So it's the max 3 S problem。 Okay， so you know about S or3 S。

 That's a yes， no problem。 This is an optimization problem。 The input is the same。

So Ill give you a threeS or  three CF formula。M clauses。Each with three。Distinct literals。

So remember how this works in a SAT formula， you have variables， Boolean variables， x1 through XN。

 a literal is either a variable or its's negation。And a clause is a disjunction of three literals。

 So it's going to be something like x3 or not x7 or not x 10。 so that's a particular clause。

 this triple， this disjunction of three literals， and then the CF formula is a conjunction。

 So ideally you want to satisfy all of those disjunctions， if you can。So that's the sad problem。

 Can you or can you not satisfy all clauses simultaneously。 The max sad problem says， well。

 if you can't satisfy them all simultaneously， at least satisfy as many as you can。

 I do the best you can。Given a possibly unsatisfiable formula， all right？

So that's the max3 set problem， just a number of satisfied clauses。Okay。So output。

Truth assignments are you just going to set each variable to either true or false。

And you want to maximize number satisfied clauses。This includes the SAT problem as a special case。

 right， that's just checking whether or not the optimal solution is M。

So certainly this is an NP hard problem。No， doubt about that。But it turns out it's actually。

 and linear expectations will tell us this。 It's actually sort of embarrassingly easy to get a kind of。

Pretty good approximation guarantee。So here's the claim。Imagine you took a random assignment。

 meaning for each variable， each of the n variables is you assigned it independently uniformly or random to either true or false so among all two to the end possible truth assignments。

 you just pick one uniformly so up here our state space for this claim is just mega is all possible truth assignments。

 the distribution is just the uniform distribution。

If you do that and you look at the expected number of clauses that you satisfy。

You're going to satisfy at least seven eighths。Of the clauses or 87。5%。Now。

 opt can't possibly be any bigger than M。 So by being within78 of M。

 you're certainly within 78s of opt。 So in other words， picking a random assignment。

Is a  seven8s approximation average。At least with respect to the expectation。Okay。

So this has a sort of existential consequence， which in my experience。

 many people find very counterintuitive。Every single three sat formula。

 no matter how deviously you pick all those clauses。

 admits a truth assignment so that seven8s of the clauses are satisfied。

 You can always satisfy  seven8s。Why。Well， a random assignment satisfies on average 78 of the clauses。

 so there's got to be some truth assignment that does at least as well as the average。

So you can always satisfy seven8 of the clauses in three S formula。

So any questions about that before we do the very short proof？

Is there any efficient reason to find this。Well， define efficient， I mean。

 just picking one a random is pretty efficient。You want a deterministic algorithm？

I'm just wondering because we can only prove the existence No， no， no， no， no。

 So the existence is a consequence of the claim。 The claim says flip one fair coin for each variable。

 and on average， you'll satisfy 78 of them。So the expected number of clauses is indeed a 78 approximation algorithm。

 You could ask about a deterministic algorithm。Is that what you're asking about， Yeah， so you can。

Basically， we'll talk about something called Markovs inequality in a second。

 and I won't go through it in detail， but just to tie the things together。

 a Markov inequality type argument will say you have at least say a 1% chance of getting 87。4%。

And then you can just run it a bunch of times。And it's going to succeed once now it's with very high probability。

There's other ways to just completely derandomize it， which is also not very hard。

 but it's outside the scope of this lecture。 so you can absolutely get a deterministic seven8 approximation。

Other questions？It's a good question。All right。So proof， well。

 we're going to use exactly the same template that I told you about so what is the random variable that we care about。

 Well， obviously the random variable variable that we care about is how many the number of clauses which are satisfied。

 so we're going to decompose that into a sum of very simple random variables。

 analyze each of those separately and then add it up and we're done by linearity of expectation。So。

 proof。So define random variable xj for each clause。

So let xj be1 whenever clause J is satisfied or0 otherwise so this is a random variable again。

 our state space is just truth assignments， so omega is the two to then truth assignments。

 given a truth assignment， you certainly know whether or not clause J is satisfied and it's just equal to1 or0 accordingly So in other words。

 it's the indicator random variable for the event of clause J being satisfied。Now。

 these are our simple random variables， so we're just going to analyze their expectation directly。

And then we'll sum them up。So what's the expected value of xj？Well， for indicator random variables。

 the expectation is just the probability that the event actually happens right， so just expanding。嗯。

Right， so theJ satisfied。Plus  zero times the probability that J is not satisfied。Okay。

So just expanding the definition of expectation。 Obviously。

 we don't care about the zero and the one we can ignore。 So the expected value。

 and this is true for any0， one random variable。 the expected value is just the probability that is equal to1 I。

e。 that the event occurs。So let's zoom in on this clause， the Jth clause， for simplicity。

 maybe it's the clause x1 or x2 or x3。What's the probability that this clause gets satisfied？Well。

 how could it not be satisfied， x1 or x2 or x3， the only way you could screw it up is if you manage to pick x1 false。

 x2 false， and x3 false。Any of the other seven out of eight possibilities satisfies the clause。

We're picking a true assignment uniform there random。

 So the probability that we get one of the seven that work is 7 out of 8。 And of course。

 there's nothing special about x1 or x2 x3， any clause。

 only one out of the eight possible assignments to the three variables contained in the clause could fail to satisfy。

So that's where the  seven8s comes in。O。This' is also why I'm using the assumption that the three literals are distinct in each of the clauses。

And I'm using that they're independently chosen。Okay。And now we're done。

So some of xJs from JL in the M， this is the number of satisfied clauses by definition。

By linear of expectation， we can reverse the summation and the expectation。

We just argue that this is seven8s exactly for every single clause J。

 so we're just adding up seven8s M times。And that's proof。Other questions？Yep。

 to imagine the clause was not x10 or not x2 or not x3。

 the only way you could screw it up is by picking true， true， true。

Any of the other seven are going to work。So you really have a one and two chance to get each of the variables right。

 the cause is satisfied if any of the three variables are right。

 there's only a one or eight chance in screwing it up there' a 7 and8 chance of getting it right。

Other questions？Allright， so it's remarkable if maybe a little depressing that if P is not equal to NPp。

 you actually cannot beat 78s for the max 3 S problem。 In the worst case。

 there's no polynomial time algorithm with approximation ratio better than 7 over 8。

 unless P equals NP P， which is a little kind of kind of hard to know how to interpret this because clearly this is not the algorithm you're going to be using in practice。

 notice this algorithm never even looks at what the clauses are。And it gets to seven8。

 and there's no way you can do better in the worst case。 Okay。

 so obviously there's a lot of things you could do in practice to try to do better。 but in theory。

 in the worst case， we can't do better。Okay。So some announcements， so problems at four the last one。

 I'm sure you're happy about that is due Tuesday， exercise number nine。

 I'll post shortly either today or tomorrow， I'm not sure whether or not there'll be an exercise set number 10 yeah。

wondering why did you the claim than let me finish announcement。 and then I'll take the question。

 So I don't know yet whether or not they'll be an exercise set number 10。 if there is。

 it'll be optional。 Okay， so exercise number 10 if it exists will not be important for the final。

 Speaking of the final。 It's at the standard time。 So that's gonna be Monday。 March 14， Three。

30 PM time slot。 The room got assigned it's 300，300。 and one thing you should know。

 So it's closed book except I'm happy for you to bring in two sheets of notes that is four pages。

 so two sheets double sided。 you can have arbitrarily small font size。

 but you have to prepare them yourself。 but it should really be your own work。😊。

And a little bit about the final， so it's a three hour exam but I expect many of you will finish earlier。

 it's intended to be frankly kind of easy if you've been actually coming to lecture and sort of following the class。

 so unlike the problem sets which are really pushing you to sort of expand your knowledge of algorithms。

 the final is just meant to test like your basic understanding of the most important concepts in 261 as covered in lecture and so I promise you that at least half the problems will be literally identical to stuff that's on the exercise sets the other half of the problems will be roughly the same level so much。

 much less substantial than the problem set questions。

So any questions about the final or other logistics before I go back to this technical problem？G。

Okay， so you're saying， why you greater equal Yeah， so it is equal。 You're right。 I mean， you know。

 claim still true。 But but you're right。 I mean， it's it's a good observation that's exactly 7，8 m。

 Somehow， like as far as our interpretation from an approximation algorithm standpoint。

 This is the direction of the equality that we're interested in。 But you're right。

 It's no better than that。 Absolute correct。は。So， so the linear expectation is great if you're happy just analyzing the expectation of a random variable。

 it's really。😊，It sort of does what you need in many cases。

 so but if you want to make a different statement， if you want to not sit。

 talk about the average value of something that you want sort of a higher probability guarantee。

 So if you want to say some number is big or some number is small almost all the time with high probability。

 that requires different tools。 Okay， so these tools are called tail inequalities。

And this is what we're going to be talking about。For the rest of the lecture。Okay。

So the point of a tail inequality is to say that a random variable is very likely to be quite close to its expected value。

 Okay， so there's not much fluctuation。 People often talk about this meat being proving the concentration of a random variable。

 So if you think of like the density function， you know this should sort of be this big spike。

 you know so think about like a Gaussian that's kind of very skinny So you want sort of sharp concentration around the expectation。

Now， the way it works with tail and equal and just randomized algorithm analysis。

 sort of no surprise， the stronger the assumptions you can make about the random variable you're talking about。

 the sharper the concentration you can prove and so it depends on sort of the context how much you have going for you and depending on how strong your properties are you're gonna be able to prove better concentration bounds So my plan next is to just show you the three most frequently used points on this tradeoff curve。

 we're going to start with one where you assume like nothing and what you prove is very weak and then we'll culminate with turnoff bounds where you assume much more。

 but you prove really quite sharp concentration but all three of these are useful in many。

 many different context。 but so just keep that trade off kind of in mind as we do them。

And my plan is， so just to。You know， make the trade offs between these tail inequalities as clear as possible。

 I'm going to back off from approximation algorithms a little bit。

 I'm going to talk about a simpler setting， namely just hashing。 But then at the end of the lecture。

 I'll bring it back and show you some ramifications for approximation algorithms okay。

So as we discuss these， there's going to be three。I want to use as a running example。

 sort of the load of buckets in a hash table， say a hash table with chaining， you can think about it。

So just to remind you the setup for hashing。So its script H be a family of hash functions。

Family just meaning set。Hash function just meaning a function H， taking a big universe。

 think of this as like 32 bit or 64 bit values and mapping it down into some small number n of buckets。

Okay。So here's your huge U， here's your very modest size array of end buckets and your hash function。

Is mapping everything to you okay？Gt。So。What I want to study is I want to study。

 So we're gonna be thinking about picking a hash function at random little H from big H。

 And we want to know how sort of crowded can these buckets be Okay， and the hash table。

 So if you like， if you think about chaining， how long can these linked lists in different buckets be And what we're going to see is as we assume more and more about the family of hash functions we'll be able to prove better and better concentration of how loaded the most loaded bin is bucket it is。

😊，So， for starters。We're just going to assume something very weak will strengthen the assumptions as we go along。

So for again， its assumption on the hash functions So for now。Let's just assume that， you know。

 for any particular universe element， like any particular 64 bit value。

Any it's equally likely to map to any of the n buckets。 So if you just look at one element。

 it's going to be uniform across the n buckets。Importantly。

 I'm not assuming that where different elements get mapped are independent events。

 And once you look at two of them， all bes are off。 but if you just focus on one。

 you see it going uniformly at random between the end buckets。So for all universe elements。

Through all buckets。The probability， okay， so the state space here is just the hash functions。

 We're picking a hash function uniformly or random。So H drawn from H。That h of x equals i。

Equals one over n。Okay。It's kind of a pretty minimal assumption for hash functions to be reasonable。

 Any given element should be mapped， basically， uniformly。All right。

So this property is already enough to say some interesting things about expectations。

So suppose we hash some subset。Okay， so n is the number of buckets。 just， you know， for simplicity。

 let's say we also hash end things。 Okay， I don't care which end things。

 just some end things from the S universe U okay。So certainly on average over the table。

 we expect one item for each bucket， this n buckets， there' n items， but more than that is true。

 if you just sort of zoom in on some bucket， say bucket I。

The expected number of items you expect to see in any given bucket is also equal to one。

 And that's true by linearity of expectation， okay。So the expected load。

 by which I just mean the number of elements that hash to it。So the expected load in I。

Is by linear of expectation。So again， we're using exactly the same paradigm right。

 so if we care about the expected load， the expected number of things that hash to this bucket。

 we can just have an indicator random variable for each element of s。

 one if it hashes to this bucket， zero if it doesn't。Using linearity of expectation。

 we just have to analyze the expected value of these indicator random variables。

 which is just the probability that this element maps to this bucket by assumption the probability that a given element maps to a given bucket is one over n。

Okay。So be linearing of expectation。This is just going to be the sum over everything we're hashing。

Times the probability that this particular element x matchs to this bucket I。By assumption。Okay。

 so by P1。This equals 1 over n and remember for simplicity。

 I said let's just go ahead and hash n elements， so there's going to be n。

Copies of one over n also known as one。Okay。So been clear so far。So this is not surprising？

So linear expectation tells us that as long as each element is uniformly distributed。

 not necessarily independently， you're going to have expected load of one in any given bucket。So。

 let's now turn to。Concentration。To what extent can we say that this random variable。

 the expected load in your favorite bucket I， is concentrated around the value1？I should say， know。

 I didn't just make up this statistic from nowhere。 when you're talking about hashing。

 you really do care about this。 So thing about hashing with chaining， for example。

What's going to be the worst case lookup time in a hash table with chaining。

 What's going to be whatever the longest linked list is in one of your buckets。

 so this is really what we care about。 We care about how big can the worst case load I'm calling it worstors case number of elements hash into a particular bucket be。

 So again， this is of like， if you only care about one statistic but a hash table。

 that would probably be the first one you'd pick。All right， so what about concentration？

So let me talk， so here's the second of our five essential tools for randomized algorithm。

 Markovs inequality， this you may have also seen before。This is the one where we assume very little。

 but we're going to be able to conclude not a whole lot about concentration。

So all we're going to assume is that we have a non negative random variable。Like this one here。

For example。If you have a finite expectation， that's kind of never going to be a problem for us today。

Then。For all constants bigger than one。The probability that x exceeds its expectation by a factor of c or more is bounded above by1 over C。

So you have a non negative random variable， it has some expectation。

The probability that it's bigger than 10 times its expectation is almost 10%。

 The probability that it's bigger than 100 times its expectation is at almost 1%。And so on。Okay。

So that's Markov's inequality。All right。It's very easy to prove。

 I'm just going to put it on exercise set number9。 Okay。

 It's really just kind of a one line argument。Good。So let's apply this， so what does this tell us？

About the probability that the load in a bin is much higher than its expectation。So， for example。

Again， fix your favorite bucket， bucket number seven， whatever。Probability。Load and bucket I。Well。

 so we take C to whatever we want， but let's take C equal to n。

 the number of buckets or equivalent the number of things that we're hashing。So the probability。

That the load in bucket I is bigger than n。 Well remember we calculated the expectation。

 the expectation was one。So this means being bigger than n times its expectation。

 that is C is equal to n here， so we conclude that this is a probability at most one over n。Okay。

 obviously you could plug in other C's as well。But what I want to sort of the feeling I want you to have about this is。

This is like a， you know， this is nice。 you know， one over end it's like definitely a lot less than one。

 but this still seems like a really weak bound， okay。Remember。

 we're only hashing in things total into the hash table。So this is really saying。

 what's the probability that every single element hashees to bucket I under a random choice of the hash function H So with good hash functions。

 you'd expect this to be crazy， small， right， not one over n。 Like if you have 100 buckets。

 you wouldn't expect that 1% of the time， everything。

 every single thing would hash exactly the same bucket。 It seems crazy， right。

But if we don't assume anything more than just P1， we're not going to be able to prove anything better than this。

 Okay， this can actually be tight if the only thing we know about a hash function is that a given element is uniformly distributed。

So to see that。Imagine that our family of not so good hash functions。Are just the constant functions。

Okay， so functions of the form H of x equals I， no matter what x is。 Okay。

 we have one hash function that always hashees to bucket 1。

 We have a second hash function that always hashees to bucket 2。 dot dot， dot。

 We have an inth hash function that always hashees to bucket n。That satisfies his property。

If you fix an element from the universe， you pick a random hash function that does indeed go to a uniform or random bucket。

 it's just that every single other element you then know goes to that exact same bucket as you。

So if we' a given bucket eye， the probability that everything hashes to it is indeed1 over n。Okay。

So again， with respect to our current set of very weak assumptions。

 this weak Markovs inequality is basically the best you could hope for。All right。Now。

 the appropriate response on your part would be to say， well， but this is stupid。

You would never use these hash functions。 You've studied good families of hash functions like universals hashing。

 C S 1，61。 That seems like the much more appropriate family to analyze。 I agree。 I agree。

 So Let's do that next。So we're going to continue to assume property P1。

But we're going to assume something stronger。About the family of hash functions。

 basically we're going to assume is universal in the sense that you learned in CS161。对。So previously。

 if we stare just at one element， it acted as if everything was uniform at random。

 Now we're just going to say if we stare at any pair of elements。

 they're going to jointly act as if they're both uniformly at random and independent so fix your two favorite distinct universe elements range over the hash functions。

 Every single combination of buckets for those two is equally likely okay。So for all x。

 not equal to y and U。And for all， IJ， not necessarily distinct。In the buckets。

We're going to assume that the probability again， over the choice of the hash function that on the one hand。

 H of x goes to I。And also the H of Y goes to J。This should be the same as if were doing everything independently in uniformly at random。

That is1 over n squared。If everything was independent， uniform or random。

This probability would factor。This part has probability1 over n by our first assumption。

 same thing here， so we get one over n squared。So zooming in on a pair of elements。

 they're acting as if they're independent and uniformly or random。Okay。Just a quick example。

You've probably seen this before， but so these are known as I should say。

 pair wise independent hash functions。Pairwise independence， okay？

And so what's the difference between pairwise independence and full independence。Well。

 think about this。 so suppose you have x1。Being a fair coin。X2。Being a fair coin。Independent。And x3。

 which is going to be obviously not independent of x1 and x2。Is going to be x1 plus x2。Mod too。Okay。

 so think of the fair coin as flipping either zero or one。O。So clearly， by definition。

 x1 and x2 are independent。If you think about it， X1 and X3 are independent。

Because x3 is just given x1 and x3 is determined equally likely based on x2's coin。

 and similarly x2 and x3 are as a pair independent。

So they take on each of the four possible joint values probably one fourth。

But this is certainly not an independent collection of three random variables。 In fact。

 only four of the possible eight outcomes could occur。 Okay， and or put differently， you know。

 knowing x1 and X 2， X3 is uniquely determined。 So theyre not， they're not independent。

So keep this in mind， just because looking at pairs of elements。

 things act as if they're independent， it does not mean that everything is independent that you still have dependencies in general。

Okay， good so。We weren't very happy about our Markovs inequality bound。 We want a better bound。

 So we impose a stronger assumption of pairwise independent hash functions。

How do we make use of this stronger assumption？So we make use of this stronger paraed independence assumption。

Using something called Cheevby sheds inequality。So the point of Markov's inequality is to get sort of constant probability bounds when you just know something about the expectation。

 The point of Chebyzev's inequality is to get significantly better bounds when you also know something about the variance of your random variable。

 not just the expectation but also the variance。 Then you'll be able to make stronger statements about concentration。

So we're again going to assume that the。Expectation is finite。We also need the variance to be finite。

 Let me just remind you， what's the variance。 You just look at the difference between this random variable and its mean。

 you square it and you take the average so variance is just average kind of squared difference from the mean。

So expectation。The random variable。Minus this mean。Square。That should also be finite。

 which it will be in sort of all cases we care about。And then what do you？Prove。Then for all tea。

Figger than one。The probability that x differs from its expectation。

By more than a t number of standard deviations。Standard deviation remember is just the square root of the variance。

So you know， as the deviation from the mean becomes more and more， more and more deviations out。

 we're going to have a smaller and smaller probability here。In Markov's inequality。

 we just had it going as1 over C here we're going to have a1 over T squared。Okay。

So for any random variable。The probability that is at least two standard deviations away from its mean is the most of fourth。

 Probably it's the most 10 standard deviations away from its mean is at most 1% and so on。

That's Cheby sayss inequality。So it's the tail inequality。

 which is useful and kind of like the handle you have when your random variable is variance and not really anything else。

 then you're kind of stuck with chubby chip。So what does this mean for us for our running hashing example。

All right， so let's put this to use。So I me be a little bit more formal about the。Hashing setup up。

So in your favorite bucket， bucket number 7， whatever， the load is just the sum。

Over for everything that's being hashed of indicator random variables where this is equal to one。

If it hashes to bucket I and equal to zero otherwise。So Xy equals one。

 if and only if we pick a hash function mapping y to I。Okay。So we said this at the very beginning。

 right so we already know that the expected value of this equals 1。 we already knew that from P1。

Let me actually call this X。So as we saw under P1， we have that the expected value of x is 1。

Then we've had that all along， so that's not a new idea。So what about variance。

 so what about the variance of the load？Well， here again。

 we're going to take this complicated random variable。

 and we don't want to analyze the variance directly。

 we instead want to analyze the variance of the constituent parts。Okay。

So focus on just one element y， which is getting hashed， so we fixed our favorite bucket， bucket7。

We think about some universe element， why。The indicator random variable about whether or not y gets mapped to bucket 7。

 Well， that's just a benoully random variable with probability 1 over n。 So by property P1。

 y goes to bucket 7， probability 1 over n， otherwise it doesn't。So really。

 this is just the variance of a Bernoulli random variable with probability 1 over N。

So you looked that up on Wikipedia。And you're like， oh yeah， it's p times1 minus p， that's right。

I knew that。And for our purposes， let's just use an upper bound of one。 Sorry， one over in。Okay。

So very easy to just analyze the variance of one of these little guys。

But what we care about is the variance of the load， the overall load in bucket do。

So this is now the first time we use P2。So the variance of x， well。

 if you follow linearity of expectations syntactically， what you certainly want to say。

 So this is a sum over the x Ys。 you'd like to say that you can reverse the summation in here。

And the variance operator。Let me actually。Write this out。Okay。

 that's what we do with linear of expectation。 Now， these are not expectations。 This is variance。

 okay。Now， let's remember， actually variances don't necessarily add。

When the variables are not independent。Again， think about the case where you just have two random variables。

 the first one is equally likely to be  zero or1。The second one is deterministically the opposite of the first one。

Okay， each one has nontri variance， variance a quarter， but you add them up。 The sum' is always one。

 So the sum has variance 0。 Okay so the sum of the different parts did not add up to the variance of the sum。

However， we're not dealing with arbitrary random variables here。We're dealing with sum of these XY's。

XY is just the indicator for whether or not。Why gets sent to this bucket or not？

And the different X Ys， okay， they're not independent。Like that would be nice All right。

 so I guess the thing I should say is for independent random variables and you would have seen this in 109 for sure。

 variances do add if they are independent so that's fine。Now here。

 so if we had full independence between these indicator random variables。

 we could write this and it would be correct。We don't have independent random variables。

 but we do have pair wise independent random variables by assumption。Okay， so given any pair， X。

 Y and X， Z， they act as if they're independent。So go back to your 109 notes， look at the derivation。

 which says that for independent random variables， variances add。

 and you will see that actually without any change。

 it continues to hold for pairwise independent random variables。Okay。So basically。

 the variance of a sum is the sum of the variances。

 minus correction terms which involve the covariances of pairs of random variables。

 and if they're parazed independent， all covariances of pairs of random variables are zero。

 so you really just get the sum of the variances as you design。So this is just notation。

 this equality， this equation is using the assumption of paralyzed independence and the fact that variances add for parazed independent random variables。

And this is totally canonical use of chubby Che you have a handle on variance。

 Why do you have a handle on the variance， Well maybe you can just analyze it directly or maybe you use this trick where you decompose the complicated random variable into pairwise independent a sum of pairwise independent random variables。

 then you just analyze the variances of the simple ones。

 you get the variance of the complicated one and boom， you're off to the races with chby Che。Okay。

So for us， the variance of each Xy is at most1 over n。

So we're summing over the end things that we're hashing， so this is going to be at most one。Okay。

Which sounds pretty good。 That means the standard deviation is also at most one。

So the expectation is one and the standard deviation is the most one。Okay。So。

If we plug that into Cheby Cheev， what do we get？So now what's the probability， let's again。

 just look at the extreme event。The probability that。X is at least n。Okay。

So the expected value was one。The standard deviation is at most one。

So X being bigger than N basically means it's， it's， you know。

 bigger than its expectation by n standard deviations。 Maybe's n -1。

 let's call it n standard deviations。 Okay， so in other words， T is equal to N。

 If we think about this inequality in this format。Okay。So with t equal to n。

 we get number bound of 1 over n squared。Okay。Definitely better than our bound of one over1 we got from Markov。

 But it still seems a little crazy。 right Like if you had a good hash table and you hash 100 things and you had 100 buckets。

 one out of 10000， every single item would go to the same bucket， really。😊，Seems kind of crazy。

 But yet again， and this is a good puzzle for you。 If the only things we assume are P1 and P2。

 you cannot prove a better bound。So in fact， there are pairwise independent hash function families where。

The expected load to something。 Everything will hash to a single bucket with probability one over n squared for that bucket。

 Okay， It really can happen。 So again， you might want to think about that as a puzzle off line。

So any questions， That's what I want to say about Chevy Cheev。Again， to take away。

 if you have a random variable where the best thing you can say about it is something about its variance。

 Chevy Cheve is is what you want to go。Markov is you really can't say anything other than about the expectation。

And I guess I should say it''s important not only can you say something about the variance。

 but the variance should be like small for Cheubby chef to be useful。O。So any questions？All right。

 so now let's go to the other extreme point of our trade off curve where we assume the most and we start getting really sharp concentration。

So let's actually assume that， you know。We just have fully independent hashing。 Okay。

 So each pair of items match， So all items are sent uniformly and independently to different buckets。

So independently。Plus， uniformly distributed。Okay。So no dependencies at all。

This is the same thing as basically saying you've picked a completely random function to be your hash function。

 Okay， It's not a very practical hash function family， but it'll just illustrate the point。Okay。

So again， clearly， a stronger assumption。 We'd like to have sharper concentration。

 But how do we use this assumption， How does this help us， So this helps us because it allows us。

To apply something called churnoff bounds。And again， really in this whole lecture。

 probably the main thing to sort of focus your attention on or turn off bounds。

 one because you may have never seen them before， two because if you take any more classes and algorithms。

 machine learning and so on， you will definitely see it again。

So churn off bounds is the fourth of our five most essential tools。

 It's the only one with a nontrivial proof really。 Oh Cheby Cheev。

 I forgot to say follows in one line from Markovs inequality。

 So I'll put that on exercise set number 9，2 so all of our tools， while essential。

 have been really easy to prove so far。So churn off bounds。So we're going to say。

 suppose we know that the random variable we care about is a sum。

Of random variables with values between0 and1。Okay those are properties we had before。

 but also that they're independent random variables， so that's the point of the churn off bound。

 Somes of independent random variables concentrate really well and churn off bounds just give you like a magical formula to plug in parameters and see just how much concentration you have for your application okay。

So assume x。Is the some random variables？Where the XJs。Ourre independent。So this is the key point。

 this is what we didn't have in the previous hashing contexts。And let's say they don't have to be 0。

1 round of variables， but they have to be bounded。 Okay。

 so let's scale so that everything is always between 0 and 1， right。

So they should be bounded and they should be independent。Then。

Here are some things we can say about the concentration。

There's going to be two parts to the true off bound。

 one saying that it's not likely to be much more than the expectation。

 one saying it's not likely to be much less。 Today， we'll only use the first one， but in general。

 the second one is also useful。So how do you say， how do we say can't be too much more？

We see the probability。That x， it exceeds its expectation by a 1 plus delta factor。 if delta equals1。

 we're saying what's the chance that it's at least double its expectation。This is the most， okay。

 sort of a weird number。But I'll show you some concrete examples in a second。

 but I do need to get it on the board。This is E meaning 2。718 dot dot dot， that's what that E means。

And then upstairs， we have the same one plus delta times the expected value of x。Okay。

 so exactly the same number here on the right hand side。Shows up in the exponent。

 Okay So you're going to want to think of Delta as being at least two so that this number inside is less than one。

So that's the first thing。 So this is saying this is saying a sense in which it can't。

 It's not likely to be。Too much bigger than its expectation。 And then also。Again。

 we won't use this today。Very' useful。Probability that it's much less than its expectation is also small。

And here is actually a bit of a simpler formula。One half。Delta squared。Again。

 with the expectation of x。Okay。Again this is the one we will use a couple times。Now， okay。

 there's all these letters on the board。But here's what I want you to focus on。Okay。

 so  first of all， I want you to focus on that there's stuff on the exponent。

 which is way different than Markov's inequality or Chevbu's inequality。

 There we had one over C or one over T squared。so there's this parameter parameterizing the magnitude of the deviation that we had only this inverse polynomial dependence on the probability bound with respect to that parameter T。

Here。You have something in the exponent。Exponents can get really small， really fast。 So again。

 think of Delta as being at least two， so that number is less than one。

This says that as soon as either delta is quite big。And again。

 big is only going to mean logarithmic here， or the expected value is quite big as soon as one of those two things are true。

This probability is going to be getting real small， real fast。So that's really the takeaway。 Okay。

 you've got both Delta， which parameterizes how big the deviation is。 Plus。

 you have the expectation both in the exponent。 If either is big， you get a really good bound。

All right。So let's put this to work。Oh， so the proof。

 we totally could do the proof in 261 wouldn't be a big deal。 Take us maybe 20 minutes。

30 at the most。 But it's really just the kind of thing that you prove in 265。

 That's really the appropriate place to spend 30 minutes on the proof of the churn off bounds。

 So for our purposes， I'm happy if you just kind of know that these are true and have a sense of how you put them to use。

 Okay， and know that if you ever need the proof， you're all perfectly well positioned to read it in a book or in 265。

😊，Okay， so。Time permitting， I'll give you three examples of churn offdowns。

 let me to give you a couple。So first， let's return to the hashing example。Now。

 under our strongest assumption。That that's a totally random hash function。

 meaning everybody's buckets is uniform and independently distributed。 Well。

 then this same sum were looking at。 Okay， remember the load in bucket I。

 That's the sum over these indicator random variables。 X， Y， X。

 Y saying whether or not Y goes to bucket 7。 Those X， Ys are now not just parawise independent。

 Those X Ys are now independent random variables。 Okay， and there's 0，1。So the load in the bucket， I。

e Capital X， is now the sum of independent01 random variables。

 which is exactly the wheelhouse of the Chernoff bound。Okay。

So we can just apply the turnout bound to the random variable we care about， capital x。

So the only thing right， so we know what EX is， we know the expected load is one。

 we do have this free parameter Dlta。 Okay， sometimes it takes a little trial and error to figure out like what you should be taking Dlta to。

But let's start with this。 So let's just start with the probability that the load in bucket bucket number 7。

Is bigger than the natural log N。So remember， the expectation is one。This is one for us。So for us。

 one plus delta here is log n so it's log n times1， so one plus delta is log n。

So if you just plug in this blue circled quantity， what do you get？You get E again， 2。718。

Over the natural log of n raised to the natural log of n times the expectation， which is one。

Everyone call that？One plus delta is log n， the expectation is1， that's what we get。Okay。

So if you like we're saying Delta， well to log n -1。All right。

 so let's try to get a feel for this number a little bit。So let me ask you the following first。

What if this， instead of being this weird thing， what if this was1 over E？

1 over E to the natural loggged N。That's also known as。One over at。O。

So if this is a constant less than one and you raise it to the log。 well。

 now you just get back a polynomial。 So you basically took the log and then you took the exponent so you get back a polynomial。

So here， this isn't just like， one half or one over E。

 This is something which is really small as N grows large。 So it's actually going to。This。

 this ratio is actually going to 0 as n grows。 Okay。

 so this is sort of even better than any inverse polynomial bound。Okay。So， this is。

Smaller as N grows large than one over end of the D for any constant D。Okay。

So I hope you can see the massive improvement we're getting over when we just use Markovs and Cheby Cheevs inequality。

 So first of all， we've got a much more reasonable number here。😊。

RightWe're not talking about this ridiculous probability that everything hashes to one bucket。

 We're just talking about the probability that a logarithmic number of things goes to one bucket。

 And that already， we're getting a much better probability bound than we had before。

 before we had one over n or whatever n squared。 Now， it's like it's better than anything you want。

's better than one over n to the 10 doesn't matter okay。So it's better in both senses。

So you can actually get away with even a somewhat smaller parameter。Instead of log n。

 you put in log n over log log n。So this is to be clear， this is the natural log of。

The natural log of n， that's what that means。Times 3。This is the most one over N squid。Okay。

And I'll let you go ahead and verify this if you're interested or plot it later to see that this is true。

If you're wondering like， okay。Log over log log is kind of weird， like where did that come from？

It's actually not that weird when you realize， okay。

 suppose I wanted you to solve the equation X raised to the x equals n。So in other words。

 what number raised to itself is equal to some integer n。There's no closed form for that equation。

 but up to lower order terms， the answer is log n over log log n。That's how it comes up。

 It's the solution to x to the x equals n。Why do we have an X to the X。 Well， over here。

 we have this one plus delta or what you know。One whatever，1 over one plus delta。

 and then there's a one plus delta。 So that's why we care about x to the x。Okay。Good。And so just。

 just for comparison purposes， if we did plug in x being at least n。

 the way we did for Markov and Cheby Cheb， where we just got these pathetic bounds of one over n and1 over n squared。

Here he plugged in the probability of x being at least n， we get something exponential。

 exponentially small in n， we get like1 over2 to the n or something like that。

 and that maybe sounds more like about right right so like if you hash 100 things into 100 buckets you're never going to see all of them in the same one one over 2 to the 100。

Okay。Three questions about that？All right。So this is also a good excuse to tell you about the fifth out of the five。

Essential tools for the analysis of randomized algorithms。 This one， I'm sure you've seen before。

 but I guess use all the time。 It's also， it's again， kind of trivial， but's super useful。

 The union bound。Which says that for any events that you want。E1 up to EK， now in algorithms。

 usually these are like bad events， these are things you hope doesn't happen。

 like your algorithms screwing up， okay。So if you have bad events。

 so what this says is just if you don't have too many bad events， and each of them is very likely。

 then it's very likely that none of them will occur。So precisely the probability that。

At least one EI occurs。Is in most the sum of their probabilities？Okay。So why is this true。

 we'll just think about your state space。An event remembers just a subset of the state space。

So just draw the circles corresponding to all your events。This left hand side。

 this is just the area of the union of all of your events。Okay。And clearly way。

 you can only overcount the area of the union of all of your events by looking at each event separately and adding up their respective areas。

This is basically like the inclusion exclusion formula， but without any of the correction terms。

 you'll only overestimate by summing these up。 You'll overestimate in general。

 because there'll be some overlaps。 If the events are disjoint。

 that's the case where this holds with the quality okay。That's the union bound。So again。

 what's the point if you have not too many bad events， each one is quite unlikely。

 then with decent probability， none of them will happen。For us， what are our bad events。

 Well remember when we did this analysis with hashing throughout， we always said， well。

 pick your favorite bucket。 number 7。 How likely is it to be very heavily loaded。But really。

 if you think about it， if you're think about a hasht or something， you care about。

 you don't want anything to be overloaded， you want everything to be very well balanced。

But here we said that you know， our favorite bucket number seven。

 the probability that it's loaded bigger than3 log n over log log n is at almost1 over n squared。

There's only in different buckets that can be overloaded。

So we just take the union bound over this event for each of the buckets，12 up to n。

 So union bound over n events， each of probability at most one over n squared。

 so that probability is of most one over n。这样。Okay。So any questions about that？

That's sort of the fifth of the things， the fifth of the essential tools， the union bound。Okay。

All right。So just real quick， I'll mention one sentence about exercise example number two。

Because they mostly want to focus on a third example。So for simplicity， I was always saying。

Let's suppose we hash exactly n items into our hash table。But remember。

 when we were talking about the Chout bounds， I said the key point is that this gets small。

 whether if either Delta is big or if the expectation is big。So in example， number one。

 the expectation was not big， the expectation was only one。But Delta was big， Delta was logarithmic。

So let's look at the other case。Suppose instead of n items。

 let's suppose it's a more heavily loaded hash table。So we insert like n log n elements。

Andto the hash table。Well， we've boosted the amount by a factor of log n。 So for a given bucket。

 the expected number of items there is no longer one。 Now。

 the expectation of a bucket is natural log event。So the expectation is jumped from one to logarithmic。

Which means， let's just think about。哦。The probability of the max load。

Is sort of a modest constant factor larger？Okay。Rememberber last time we had our expectation of one and we were having this sort of fluctuation of up to log over log log。

 which is tight actually， by the way， so in general。

 the longest linked list in a hash table even with a fully random hash function will be asymptically log over log log。

So here I'm saying， well， let's even just look at much smaller fluctuations， a factor of four。Well。

 how do things change in the blue circle？One plus delta used to be log n。

 but now one plus Dlta is only four。On the other hand， the expectation used to be one。

And now it's the natural log event。Okay， so Delta is now constant。

 but now the expectation makes up for it by being logarithmic。So again。

 the blue circle is going to be less than1 over n squared。

If we just plug in these numbers for Delta on the expectation。

 taking the union now and over all of the buckets like before says that with property at least one over n。

 nobody。Is bigger than four times its expectation。and this is pretty useful actually right so if you have sort of a sparsely occupied table。

Then you can have big fluctuations， but if you have just even like a modest load， it's very even。

So this can be useful when you're doing load balancing， you know， think about data centers。

 something like that。 It's pretty nice that just random choices wind up balancing themselves quite evenly。

 It's a useful property。All right。So last example。So now I want to sort of bring it back on home to approximation algorithms。

We already saw one application max3at of randomization and approximation arguments。

 but let me give you a， I'll only have time to sketch it briefly but let me just give you a sense of this。

 this ties in with what we were talking about last lecture namely using linear programs to design approximation algorithms。

And so in particular from last lecture， though， one I want you to remember is our first vertex cover to approximation。

How did it work？We wrote down a linear programming relaxation。 What does a relaxation mean。

 it means any vertex cover corresponds to a  zero1 solution。

 but then there's other fractional stuff as well and the relaxation。

You solve the linear program optimally。So that gives you a lower bound on the best possible vertex cover because it's a relaxation。

Now， in general， the vertex cover will have fractions。

 as we saw last time and fractions don't make a vertex cover。

 You got to massage it into a vertex cover。 How do you do that， You sort of round it to integers。

 How did we do that last time， We just said， well， you know。

 any variable that's at least a half make it one。 Any variables that's less than a half make it 0。

 In other words， round everything to the nearest integer value。 that worked great for vertex cover。

The idea in randomized rounding。Is to， again， you solve the LP， solve an LP relaxation。

And then you're going to round it to an integral solution like before。

 but you're going to do it probabilistically。Okay。Specifically， right。

 so the problem with the LP relaxation is it has fractions。

So the idea is to interpret these fractions as probabilities。

And then around the fractional variables accordingly。

 up or down in proportion to what that fractional value is。

Here's sort of the canonical application of randomized rounding。I'll give you a graph。

It could be directed or undirected。And I give you source sink pairs。Okay。So you have a graph。

Sourcing pair。And the question you want to know。can you choose a path， just one path from S1 to T1。

 from S2 to T2 and so on from S to TK， so K pass in total。

 so that no edge of the graph is used in more than one of the paths？Zhen。So for example。

If you have these two paths which meet it a vertex， but don't actually share any edges。

This would be a legitimate solution。 if actually those two paths also shared an edge that would not count as a feasible solution。

 you want to know， is there any way to connect everybody to everybody else that want to be connected to without using any edge more than once。

Okay。So that's an MP hard problem。In directed graphs at NP hard even already if k equals 2。

So what do we do， So what would an approximation algorithm look like？

We're going to do this randomized rounding approach，So we're again going to solve the LP relaxation。

I'm not going to write it down。 You've actually already seen this LP relaxation a couple times on exercise sets and problem sets。

The relaxation here is just going to be multi commodity flow。What's the disjoint path problem。

 It just says I give you a graph， I give you SIT I pairs， just like a multimod flow。

 and I want you to pick a single path。For each SITI pair， so that no edge is used more than once。

 that is a capacity of one is respected。What's multi commoditymodity flow。

 I'll give you the same input， a graph and SITI pairs， and you route flow fractionally。From SI to TI。

Okay。So the LP relaxation is just going to say， does there exist a multi commoditymodity flow fractional so that from each S I to each T I simultaneously。

 one unit of flow is being sent， subject to a capacity of at most one on each edge。Okay。

So that's the LP relaxation， multi commoditymod flow， unit capacities。

 you're trying to send one unit for each SIT I pair okay。Now， if your LP solver comes back and says。

 couldnn't do it。Couldn't find a multimod flow。Meeting those constraints， well， then you're done。

Because any collection of edge of dis jointin paths is a very special case of a multi commoditymodity flow routing one unit from each side side to TI with no edge over capacity。

So if you can't even have a multi commoditymod flow， then you're not going to be able to have。

Destroy paths。So what are we going to do so the interesting case is where the LP is feasible。

Now it's an N hard problem， so there's going to be cases where the LP is feasible。

 but there's no disjoint paths。So we need we want to somehow round the LP so that we still get approximately disjoint paths。

嗯。So here's what we do。So we choose a path for so we have the LP solution。

 we have the multimod flow for each SIT pair independently。We say， well。

 look at how it distributed flow over paths from SI to TI。It's sent a unit to flow total， remember。

We're just going to pick an STIpath at random。With probability equal to the amount of flow on that path and the LP solution。

So the fraction。Of eyes flow like between SI and TI。Be of carries。And again。

 this makes sense because in the LP relaxation， a unit of flow gets sent from S to TI so we can interpret its fractional splitting of flow over the paths。

We can interpret it as non negative number sum to 1。

 we can interpret it as a probability distribution。

 so it's well defined to say pick a path according to that distribution。

 and then we do that independently for each SITI pair。Okay。So that's randomized around。

So what can you prove about it？With high probability。Provided the LP solution。

 the LP relaxation is feasible。Randomized rounding will produce a solution。Such that the。

Max number of paths。Using any edge。There's the most three log n over log login。Okay。

So these are not disjoint paths。 disjoint paths would say that the max number of paths using any edges are almost one。

Again it's MP hard。 So we're not expecting to find M to find disjoint paths。

 But this says at least we can find a solution where no edge is used by too many paths。

So if you like， this is an approximation algorithm with respect to the objective function of minimizing the maximum load on any edge of the network。

 it's another way to think about it。So this is the original and still to this day canonical application of randomized rounding it's from the mid-80s so back then the authors is Raanna Thompson they were motivated by circuit layout problems。

 so they were thinking about know the graph would be like a grid okay where you'd be laying out a circuit。

 their SITI pairs they were contact points on the boundary where you needed to have a wire laid in the circuit in between the two contact points。

And actually， this kind of solution was fine for them because you could always just sort of widen the channels in the chip so that actually a whole bunch of wires could be laid down in parallel。

 So the fact that over here on a single logical edge of the network。

 you actually are routing a logarithmic number of different things。

 that was an acceptable solution for the application。

 You just make the channels a little bit wider and you're good。So how do you prove it。

 We're almost out of time， so' not going to prove it formally。

 I'm just going to sort of argue by analogy。Really。

 this follows from the hashing analysis we already did from our example number one of churn off bounds。

 and this is really the paper that ported churn off bounds over into the algorithms community so you zoom in on a single edge。

On a single edge， the expected number of paths that get routed on it。Is it most one？Why。

 because in the LP relaxation， we gave this as unit capacity。 So the total fraction。

Total amount of fractional flow using this edge was at most one that translates to an expectation of at most one of how many paths get chosen to use this edge。

Now on this edge， once you have this now you have this sum of random variables。

 okay so just like before we said how many elements get mapped to a particular bucket。

 now instead of a bucket we have an edge instead of elements we have these paths。

 how many paths get mapped， you know how many paths get chosen that include this edge。

 that's exactly that same sum of random variables。Again。

 we have independence across commodities so we can use the churn off bounds because all the parameters are the same。

 we can even stick in the same number here。 Actually， I should say。M。Okay。So what we had before。

 that one so up there， that most one over n squared。

 here we're going to get that with probability all but one over m squared。

 a given edge has load no more than this。And now again。

 we just do a union bound over all M of the possible edges。 so it's one over m squared for each edge。

 summed over all of them。 it's a most probability one over M that anybody has a load this big。

 So in that sense， with high probability， this algorithm obeys this bound。So for directgraphs。

 this actually turns out to be the best you can do for this problem unless peak equals N。

 there's a matching lower bound saying it's NP hard to beat log over log log N。

For the under case it's actually still sort of quite intriguing gap。

 so we don't really know algorithms better than this one for underregraphs， but they may well exist。

 the best lower bounds we have are super constant but not by much。So that's all I got for today。

 see you on Tuesday。