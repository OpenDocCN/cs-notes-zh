# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p17 P17 apr16 -BV1Dao8YQEEn_p17-

Okay， so。Guess we'll get started。so just as a reminder。

 PSE4 is due this afternoon and PSet 5 is out also， so that'll be due a week from now。

P at five basically covers the material that we're doing this week， including today。All right。

 so Robin lectured on Tuesday， so he told you about peace space， peace based completeness。

Surely maybe just to review a little bit what Robin covered。

 so we can sort of start filling in our map of the complexity world。

Peace space is kind of a ceiling for what we're usually interested in。

 although this there certainly is stuff above peace space， you know exponential time， you know。

 you can have peace space， complete problems， complete problems。

 you know they're all defined in completely analogous way as NP complete problems okay。

 but these are even sort of higher gradations of hardness，And then。Below peace space。

 we've seen that there's this polynomial hierarchy， of NP， NP to the NP， NP to the NP to the NP。

 and so forth， all the different levels of it。呃。系。And。And then down at the bottom。

 we've got P and then what Robin started telling you about on Tuesday was probabilistic complexity classes。

 okay， which are going to be our focus for today， guess。So he showed you RP。

 which is a randomized polynomial time， which is like you can think of it as the subclass of NP。

 where if the answer is yes， and they're not merely does there have to exist in accepting witness。

 there has to be lots and lots of accepting witnesses。

 in fact it has to be true that if you pick a string at random。

 then with probability at least a half， it is an accepting witness。

Okay and you know and there's nothing very special about the constant a half we could have picked a tenth instead。

 you know the important point is just that it's a constant。

 okay a constant fraction of all of the possible witnesses actually cause you to accept so then you know the in some sense the only reason why your problem might not be in P。

 it was just that you know you can't you know if you pick the deterministically and accepting witness。

 you know if you pick the deterministically a witness then you know you might just happen to choose you know all the bad witnesses and not find a good one okay but RP is a subclass of NP okay and then。

You know you've got the complement of RP， CoRP， which is a subclass of CoNP， did Robin Joe use ZPP？

You。Okay。Let's see okay， you just mentioned it。😊，呃。

So ZPP is defined as the intersection of RPp with coRP。

So just to give you an intuition for these classes。

 know RP is the class of decision problems that are solvable by some polynomial time randomized algorithm which has the property if it ever outputs yes。

 then you can be totally certain that the answer is yes， you can take that to the bank。

 you know have a witness that the answer is yes okay but it might just fail to find such a witness say with half probability in which case you would have to run the algorithm again。

 know and just keep running it if you run the algorithm a thousand times and it never finds a yes witness any of those times then at that point you can be pretty damn certain that the answer is no。

 you you're still not totally you certain there's a two to the minus a thousand chance that you just got extremely on。

Lucky and never found any yes witness even though they were all over the place okay but you know the two to the minus100 probability that your randomized algorithm failed is much much smaller than the chance let's say an asteroid would have just come through the roof and destroyed your computer anyway so for that reason you don't really you could say you don't really care about it that much you know we accept far。

 far higher probabilitybabilities of failure in everyday life for all sorts of reasons you know there's know and you get on a plane there's a far greater than two to the minus100 probability that it's going to crash but but you still get on it probably so and then that's really like a key property of randomized algorithms that gets exploited all the time which is which be called。

Amplification。Okay， and Robin told you a little bit about that。

It's just the fact that you can if you don't like a randomized algorithm's， probability of failure。

 you can just keep running it over and over with different choices of random bits and just combine all the answers somehow just look at whether any of the runs succeeded。

 for example if it's an RP algorithm。U。呃。You know and what makes this work is that you what allows this to work is that when we're talking about randomized algorithms。

 we're not saying that the input is random， right， the input could still be anything， okay x。

 you know the input could still be anything at all。

 you know our algorithm has to succeed for every possible choice of x， but in addition to x。

 there is some auxiliary random string， R， let's say that the randomized algorithm also takes R is just chosen as some random string to help you decide whether x is in L or not。

So you think of your touring machine right， it's actually taking two inputs， x and R okay in R。

 you know you chose it once， you could just choose another one。

 you can just keep choosing Rs if you have the ability to generate random numbers at all that just keep generating more and more Rs and try running your machine with x comma R1。

 x comma r2 and so forth and you could always just look at all of these outcomes if you want to push down your probability of being wrong。

Okay， so。All right， so that's RPRP CoRP is just the same thing but where we flip the roles of yes and no okay or of accepting and rejecting okay。

 so CoRP， you know you if your algorithm ever says that the answer is no。

 then you can be completely certain that it's no， okay if not。

 then maybe it just fail to find a no witness and so then you have to run the algorithm again。

Now ZPP， can anyone give me like an intuitive interpretation of ZPP？

What does it say if you have a ZPPA algorithm for your problem？Yeah，No。Well， you know， okay。

 for the definition， it means you have both an RP algorithm and a coRP algorithm。

 but what does that mean？Well。Yeah。Yep。Yeah， yeah， exactly。

 it means you know you can get a yes witness， you know。

 and then you're certain you know your algorithm like like if the answer is yes。

 then with good probability， your algorithm will give you a yes witness and you'll be totally certain that the answer is yes。

 you know if the answer is no with good probability you'll give you a no witness and you'll be totally certain the answer is no。

 so now why is this not already a P algorithm like what could go wrong。Like。

 why is ZPP not just obviously equal to P？Well， yeah。Yeah， exactly。

 there's still a chance that you're not going to get either witness right。

 There's still a chance that the algorithm will fail to produce a yes witness and fail to produce a no way。

 in that case， you know the algorithm will just sort of shrug its shoulders it will say you know I don't know the answer。

 I don't know whether X is a L know but at least it will know that it doesn't know okay you know you know it's never going think it has an answer when it doesn't okay so you know so then you know you may have to just run the algorithm again and again and again until it gives you one of the two witnesses but you know with overwhelming probability you know before long you'll find one or the other Okay so ZP algorithm is like the best kind of randomized algorithm that you could hope for you know short of a deterministic one。

And ZPP is， you know， so if RP is contained in NP andRP is contained in CoNP。

 then ZPP is contained in white anyone。😊，Yeah， NPP intersect Co andP， right？Okay。

The class where there were both yes witnesses and no witnesses。on PS at5。

 one of the things that you prove is that ZPP is also equal to just a set of languages that are decidable by a randomized algorithm that runs in expected polynomial time。

So that's a different characterization of， you know。

 and which is always correct when it produces an answer。

 so that's another characterization of ZPP yeah。Yeah， so I would like to be able to。😊，The problem is。

 you know， we don't。 okay， here's。So the classic example for many decades of you to illustrate these probabilistic complexity classes was primity testing。

😊，So you know， testing whether an integer is prime or composite， okay， so in the 1970s， like in 1975。

 I think you know it was showing that the primity is an NP okay。

 so you know so it's obvious that compositeness is an NP you know。

 if a number has a non-trivial divisor then an NP witness for that is just。

The divisor right you know you can check that okay but but how do you prove an NP that a number is prime that takes a little bit of number theory okay you know even even that right so that was shown in the 70s and then people improve that and they showed the primity testing is in RP Okay so there is in other words there is a certificate that you can have that will prove that a number is prime if you can find it。

You know， and then it was also found that there are certificates you know that you can get that will prove that a number is composite okay let me give you you know examples of these things。

IShowll you what I'm talking about so there's something called the Fmats。呃。

This is also called Ferman's a little theorem， not to be confused with his last theorem，Okay。

 so this is what it says。Did I。Did I get it right should this be P minus-1， Robin？Yeah， minus1 yeah。

All right， so yeah， heres so it says if。if。嗯。If p is a prime number。

 then it always satisfies this equation， okay you can pick any nonzero x you want。

 raise x to the p minus1 power， look at the remainder when p goes into that and you'll always get one。

Okay， we can do an example， if you like。😊，What what's someone's favorite prime number。17 all right。

You can pick a smaller prime number。5， all right， cool。

And now what's your favorite x from one up to four？One is not going to be too uninteresting。2。

 all right， two so what's5 minus1 it's4，2 to the4，16。

 modd 5 as wt leaves1 right from Os little theorem is vindicated once again all right so now this is you know a kind of useful you know very useful fact you know why is it such a useful fact well you know we'll see you know it's useful we you know the use of a generalization of it I guess when we come to the RSA cryptoy okay but another use is that let's say that you have a P and you don't know if it's primeer composite okay and let's say that you just pick some random X。

There's randomness， okay， and you try out this equation and you find that it doesn't hold。

 then what can you conclude from that？Yeah， you can conclude that P was not prime， you know。

 you then have a certificate that proves that P was composite。Okay。

 so you have a certificate of compositeness if this equation fails。

 then P is composite okay now unfortunately this is not quite enough by itself to give you an RP algorithm for compositeness okay and the reason why it's not enough is actually extremely interesting。

 it turns out that there are numbers that always pass this test even though they are composite。😊。

Okay， so those numbers are called the carmichael numbers。

But another name for them is the prime pretenders， okay， these are the numbers that， you know。

 as far as the Fma test is concerned， they pretend to be prime， but actually their composite。Okay。啊。

Okay， I remember that the smallest carmic number is561。

 I don't remember what its prime factors are if anyone wants to go you know figure that out then that would be cool buth。

What？Three， yeah， I guess， but it is， yeah， all right， good， so then what are the others？😀ふ。😊。

Not too， yeah， thank you。😊，h11， all right。So how many times does 33 go into this？17 all right。

 awesome， okay。So。All right， so so that's the smallest carmicel number。

 but it was actually proved like 20 years ago that there are infinitely many carmicchael numbers so there are infinitely many cases where this forma test doesn't work but fortunately it's not such a big problem because it was shown in the 1970s how you could patch up this test to get a test that always works and thing that if your number is composite。

 there will be lots of witnesses to its compositeness and and there will never be such witnesses if your number is prime so then that showed that compositeness was in RPp or alternatively that primity is in coRP now it was also shown by different methods that prim。

it was an RP there are also witnesses to primality and which you can find know that lots and lots of them exist。

 you know you can choose a number at random like an a at random and with high probability it will be a witness to piece primality but we just did not know how to choose such an x deterministically so then you had both an RP and a coRP algorithm for primality so then what could we have concluded about primality at that point。

😊，Yeah， the primity was in ZP Okay， and this is what we knew。

 So what we knew about primity testing for a couple decades was that。呃。

Was that it was in ZPP you know， so primarilyity kind of made a long you know journey downwards。

 you know for NP to CoRP， I guess the ZPP， yeah。The RP。Yes。Well， yeah， yeah。 okay。 That's right。

 But but you can do this， right， You can always do that。 You can always just。

 you know alternate running them。 Okay， you can always just， you know， first run the RP algorithm。

 you know， a few times， see if it succeeds， if not， run the KRP algorithm a few times。

 see if it succeeds， run the RP algorithm a few times right， you can always do that。😊，Okay， you know。

 it's like dovetailing， except with just， you know， two。Yeah， with just two things okay but you know。

 alternatively， if you just define ZPP as the intersection of these two classes。

 then once you know that your language is in both classes。

 then it is immediate that it's in ZPP it is true by definition， right。

 you know the further observation is that if your language is in ZPP。

 then you can you know just do the thing where you you know always find either a yes or no witness。😊。

Okay， so。Okay， so so we knew that about primality actually other there were a bunch of other things that we knew about primality。

 for example， we knew that it was。It had been shown。The primality was solvable in time N to the log。

 log log n deterministically， okay I'm not making this up。

 this is really what was shown okay and the other thing that was shown was that that was known since the 70s actually was the primity is in P is solvable in deterministic polynomial time assuming the generalized rhman hypothesis。

So we had actually a deterministic primity algorithm。

 and the only problem was to prove that it always works。

 right and the proof that it always worked assumed the Riman hypothesis。😊，Okay， so so we knew。

 you know， so so like you know the saying was right that this problem is just hanging above pe by like a tiny threat little thread but you know。

 but it took a major effort to sort of cut that thread so you know in 2002 finally，😊。

Aroal Kyle and Sxina were able to， you know， come up with well。

 different randomized the algorithm for primality。 But one that they were then able to deranize。

 Okay， they were able to show how you could actually， you know。

 choose the witness in a deterministic way， rather than a random way。 Okay。

 and that finally gave us that。😊，Primality testing is in P。Okay。

So you know and the deterministic algorithm I should mention is still a lot less efficient than the randomized ones that we know right deterministically we now know how to do it and something like end to the sex time okay whereas with randomized algorithms。

 we know how to do it and like N cube time okay so you know if you're generating random numbers for you you' huge random prime numbers for use cryptography。

 almost certainly you're still using randomized algorithms to do it so。😊，All right，You know。

 I help you know illustrate some of these concepts right and just you know like the different types you know of certainty that a randomized algorithm can give you right。

 like certainty that your number is prime if you find a prime witness， certainty that it's composite。

 if you find a composite witness certainty either way， or， you know， or you know。

 then the best that you could have is is just either deterministic algorithm。So。All right。So okay。

 but now and I'll show you other example， later today。

 I'll give you another example of a problem that's in RP。

 but which to this day no one has been able to show is in P and it's a big challenge to show it's in P。

We have very， very few such examples with ZPP anymore。

 so you know a lot of people think that you know ultimately ZPP is just going to be equal to P okay in fact even you know。

 I think even that RP coRP， you know that all these randomized classes are just ultimately going to be equal to P okay but no one has been able to show that。

😊，So。Okay， but also none of these are like the most general class of you know。

 the most general probabilistic complexity class that you could have， right。

 the most general one is BPP。So I think Robin， you defined BPP on Tuesday。

 but this is the class of languages that have a polynomial time randomized algorithm with two sided error。

So sort of a stylized definition of it will be， you know。

 it's the class of languages that are solvable by some randomized you know know that have some randomized algorithm M with the property that if for every input x that's in L。

 M excepts with probability greater than or equal to two thirds and for every x that's for every input X that's not an L M excepts with probability at most one thirdd okay where you know there's nothing magical。

 you， we're going to prove that there's nothing magical about two thirds and one thirds right these are just two you constants you not zero and not one and which are bounded away from each other。

That's all that really matters about them。So a BPP algorithm is one that never gives you certainty right it never gives you a witness for a yes answer or a witness for a no answer you know all it gives you is it gives you a statistical evidence that x is an L or that x is not an L you could run your algorithm 10。

000 times and of those 10，000 runs， 7，000 you of them except then you could be pretty damn certain that X is an L right and if you run it you 10。

000 times and only 3000 except right then you could be pretty certain that X is not an L okay but you're never entirely certain either way okay it's like you taking a political poll you pull some people you have some margin of error you and。

You know， and you know， and there's some bell curve you know where you。

 that says that like with some you know， extremely small probability， you know。

 you could have made a really， really enormous error， okay you know。

 so we'll be more rigorous about that soon。All right， so in order to be。

You know so you know we would like to be able to answer questions like well okay you know just how many you know suppose you have a BP algorithm。

 you know a probabilistic algorithm for some problem right you know and let's say you know you want some given level of certainty okay you know a given level of confidence and the answer just how many times do you have to repeat the algorithm you know to get the level of confidence that you want you know and that's like in some sense that just a pretty classic statistics problem it's like you know if you want you know you know we could have asked right if you're doing a political poll and you want you know you know1% margin of error how many people do you have to call right are you know are these are very classic problems okay but so you know the language that we need to talk about them is you know the language of probability theory okay so let's spend a little time talking about that okay。

So probability theory deals with events， okay an event is something that could either happen or not happen。

 basically， so it has some probability of happening which is a real number between zero and1 and you can do Boolean logic with events okay so you can say not a the event that a doesn't happen you the probability that a doesn't happen。

 you it should surprise no one is1 minus the probability that a does happen。Okay。

 and then you know you can also take combinations of events like you know you have two events A A and B right what's the probability that either one of them happens right what's the probability of a or B okay and you know there is a formula for that well you know basically you know you have the probability of a plus the probability of B okay。

 but you know we're not done yet right because A and B could be correlated okay you know you know and you have to account for the correlation somehow okay so you can say you know minus the probability of a and B okay。

 so this is you know if you just think of it as。Right here's a。呃。Here's B。

 you know think of it like this right and now if I want to know you know here's a or B。

 okay I want to know the probability of either one of them happening so I have to add up the length of this and the length of this。

 but then you know over here I've sort of double count it so I have to subtract off you know the length of A and B okay and then I get the length of sort of A or B。

 you know which is the probability that either A happens or B happens。

So okay but now you know this formula has one particular consequence that you know is sort of maybe the single most useful principle and all of theoretical computer science okay I'm not exaggerating like I can't think of any paper I've ever written that does not use this principle many times okay you know you know and it's completely you know the proof is like completely obvious。

 there's nothing to say about it， but still it's just worth you know really。

 really knowing in and out okay this is the union bound says the probability of a or B is it most the probability of a plus the probability of B these need not be equal like you know probability you know like a like let's say A and B both had probability of one right then this site is going to be two okay you know you know the probability of A or B is you know is never going be。

2， okay， that's， that's gonna be a very， you know， non tight bound。 Okay， but you。

 but you always have this inequality because just just， you know， why。

 Because just ignore this part over here， Okay， so。You know。

 so so what this is saying is that you know， if like there are two different。

 let's say you've got an algorithm and there are two different bad things that could happen to it。

 like you know， you could get， you know you know you could get hit by lightning or you could get hit by a meteor right you know and you know those two bad things might be correlated somehow it might be that you know people who are struck by lightning or more likely to be hit by meteors than people who are not or maybe that they're less likely you know and get that can get really really complicated to understand the correlations between all kinds of different bad things that could happen。

 Okay but what this says is that if you just want to bound the probability that something bad is going to happen then in some sense。

 the correlations are irrelevant all you need to know is you know if you've got if there's only at most to 1% chance that the meteor is going to hit you and there's at most to 1% chance that the lightning is gonna to hit you the probability that one or the other is gonna to hit you is that most 2% okay always okay。

Independent of any correlations， all right， so that's what makes it so useful。😊，All right。So now。

 in addition to events， we also need the concept of random variables。

So a random variable is just you know a variable that， you know。

 and we're only going to really care about like discrete random variables in this class， okay。

 so it's just you know， it's a variable that has some probability of taking on different values。Like。

哦。So。You know we could write you know there's some probability that x is equal to zero。

 there's some probability that x is equal to1， for example。

 and so on for all the different values in some range。You know， if we sum up。

The probabilities that it has all of the possible values that it could have。

 and we're going to get one。Okay， and then you the sort of the key quantity that you look at when you have a random variable or the first thing that you usually look at is what's called the expectation。

Variable thats。That's just a fancy word for the average。 Okay， So you know， it's defined like this。

 Okay， let's say you know， if x takes values that could be different integers， right。

 the expectation is that okay， it's the mean value。😊，So。嗯。So maybe you know。After the union bound。

 the second most useful principle in all of theoretical computer science。

 one that I've also used in essentially every paper I've ever written is called linearity of expectation。

What this says is that if you're interested in the expectation of x plus y。

Then that equals the expectation of x plus the expectation of y okay and again。

 what makes it powerful is that whatever correlations there are between x and y are completely irrelevant here。

 okay this is always true， you know， regardless of how x and y might be correlated okay。😊，Makes it。

 you know。Extremely useful。Okay，So now let me ask something。Do we also have this principle？

The expectation of x times y equals expectation of x times expectation of y。 No。

 what's the counter example to that。Yeah。Let's say x and y are both either zero。Yep。That is one。

All right， excellent， so they're perfectly anti correlated， you know。

 let's say uniform random variables， then what is expectation of x？😊，An expectation of why。One half。

 what's expectation of x Y？Zero， there we go， Okay， there's our counter example okay， you know。

 or you could take them， let's say that instead of perfectly anti correlated。

 they were perfectly correlated in that case， what would be the expectation of x Y。😊。

A half right which is also not equal to a fourth okay so in general you know this principle here you know well you know it you can only assume this if you know that x and y are independent okay independent just means exactly what it sounds like okay it means that if you condition on any possible value of x then that has no effect on y okay that has no effect on the distribution over y values or equivalently if you condition on any possible value of y that has no effect on the distribution over x values okay that's what independent means and if x and y or independent then this holds if x and y are not independent then it need not。

😊，Here's a question， like can this hold even can this equation hold even if x and Y are not independent？

Yeah， it can， it can Okay so theres you know， so this is not the definition of independence， okay。

 but this is something that holds whenever x and y are independent。😊，Okay。Okay。

 this always holds regardless if they're independent or not， okay。

 so now you know putting together concept of probability and expectation。

 I can give you know the third most important principle you know theoretical， you know。

 they're really coming fast and furious right now okay。And this。

The third most important is called Markov's inequality。

 I this is another of those things from back in the era when it was a lot easier to get things named after you。

And what this says is that。😊，So that if x is a non negative random variable， okay。

 this is only going to be for non negative random variables， so the take values like zero and above。

Then。It says， if you want to know what is the probability that x is at least k times its expectation。

 then that is going to be at most。1 over k。Okay so the probability that some random variable is more than 10 times its expectation。

 you know it is less than a tenth， the probability that it's more than 100 times its expectation is less than 100th and so forth。

Okay， can anyone give me a proof of Markov's inequality。

 can anyone just explain to me why it would be true？Yeah。Yeah， exactly exactly。

 we can simply say you know， I mean I could have put this on the PSE but we'll do it right now right if this is quite easy right if this were not the case。

 then you know this would say you have a more than one over k probability of being more than k times your expectation okay but well wait a minute in that case you know then that by itself would already force the average to be more than e of x。

😊，You see that right because the random variable is not negative because even if we just had a one over k probability of being k times the expected value and every other time we were just zero。

 okay， that already would sort of spend our entire budget that already would force the variable to be more than e of x。

I I'm saying okay。All right， so this is， once again。

 extremely useful principle for upper bounding the probability that something really bad is going to happen to you。

Okay。U。Okay， but now。What know we would like to apply some of this to understanding the class BPP so with BPP。

 you know the standard way of defining it is you it' the class of languages for which there's a polynomial time randomized algorithm such that you know whenever the answer is yes。

 you have at least a two- thirdhird probability of accepting and whenever the answer is no。

 you have at least you have at most a one thirdhird probability of accepting， okay but you know。

knowOne third and two third these are pretty arbitrary constants right you know and we would like to make sure that our definition of BPP is independent of the choice of these constants okay and even you know more than that we would like to show that if we have a BPP algorithm that we can make the probability of you know by just repeating the algorithm a whole bunch of times and taking a majority vote。

 we would like to show that we can make the probability of error really。

 really small like exponentially small。Okay， so how can we show that？Okay， so。

So we're going to imagine。That we have a randomized algorithm that looks like this。

And then we're going to run the algorithm。What what I call this let me call it M times okay m times and take the majority vote of all of the outputs okay and this seems like a really good you know good way of aggregating or you know what we learn from each of the runs because you know intuitively like what's the chance that we're going to make a mistake well let's suppose x is not in the language right then you know each of these runs you know has in that case that most a one-td probability of outputting yes okay and so then the only way we're going to make a mistake is if more than half of them end up outputting yes okay so imagine you know that M is a000 you got1000 runs right on average you know 333 of them or so you know most 333 are going to accept okay and now you we're saying that the only way that we're going to make a mistake here is。

If somehow 500 or more of them accept。Okay， you know， and that seems very unlikely okay。

 but now you know the question is how do we formally argue you know just how ridiculously unlikely that is right it's you know。

 it's like you know intuitively right you flip a coin a thousand times you know。

 you' you know you don't expect that you're going see 700 heads okay you know you know that that seems astronomically improbable right。

 but how do we how do we actually to get a usable upper bound on the probability that this is going to happen Okay so。

So could we just use Markov's inequality to do this。

 could Markov's inequality by itself just give us a decent bound？Well。

 it'll give us some bound right， because Markovs inequality will tell us， well。

 look the expected number of acceptances is is it most M over three if x is not an L and we're worried that we're going to have at least M over two acceptances and what upper bound on the probability of M over two acceptances could we get from Markovs inequality？

Well。We could get， you know， the expectation divided by the thing we're worried about。

 basically okay， which is two third。Right。So， so Markov's inequality would tell us that there's， you。

 at most a two thirds chance that our algorithm is going to screw up。 That's not very impressive。

Okay。We would really like there to be at most a point000 one probability that our algorithm is going to screw up Okay。

 so if we want that， then we're going to have to work harder than just using Markovs inequality okay and and the key point you know is that is that。

😊，You know， suppose that these runs were all correlated with each other okay so suppose that yes。

 you know each run of our algorithm has you know has a two- third probability of getting the right answer okay but if one of them screws up。

 then they're all going to screw up okay suppose that that we' true in that case it wouldn't matter how many times we were running our randomized algorithm right if it's like you know you know this is exactly the mistake that led to the 2008 financial crisis okay you know for those of you who remember it okay you know people said。

 well you know we have all these you know mortgage backed securities each one has some small probability you know that the person is going to default on their loan okay but you know and as long as only you know you know at most 20% of the people end up you know defaulting then then we're okay right？

The probability that that number of people are going to default right it's you know astronomically small okay except that you these were not independent events okay you know they could all you know if the entire economy goes down and they could all do it at once and that was the problem okay so。

😊，So independence of your random variables is extremely important。

 like important on the scale of trillions of dollars。

 and we're going to need to use independence in order to analyze the amplification of BPP algorithms。

Okay， so。Why cant we assume independence in this case？

Why do we know that the different runs of our randomized algorithm really are independent of each other？

Yeah。result。Well， yeah， that's， you know and why doesn't it， yeah？Yeah， exactly。

 because we get to pick the random bits， right， we get to just pick them to all be different from each other and to all be uncorrelated with each other。

 right， so we get to enforce independence， if you like。So。嗯。

So now you know the question that interests us is this okay。

 let's say you know we've got a bunch of zero or one random variables okay。

 so you know like each one， let's say。Okay， let's say， you know， each of these variables is one。

 if the IAron of a randomized the algorithm accepts and it's zero otherwise okay then。

Each of these variables， I should say， has an expectation。😊，Sa it most A。

 like in the case that interests us here， a is one third。

 but you know it could be anything All right， and now we are interested in upper bounding the probability。

That the sum of all of these random variables you know is greater than or equal to some b times m okay in other words at least a b fraction of the runs except for some B which is greater than a like in the case that interests us here。

 B is equal to a half because that's the threshold where our randomized algorithm is going to start making the wrong going to start output putting the wrong answer okay so okay but then you know we would like to just upper bound this knowing only this and knowing also knowing that the X size are independent of each other okay so the tool that we use to do that in theoretical computer science is called the turnoff bound。

Okay and there's a whole bunch of different variance of the turn off bound。

 There's all different statements of it that you know you that you know some are better than others and in different circumstances。

 All right， so what I'm going do is I'm gonna just prove for you you know， a rough and ready version。

 you know know that gives you something okay and then you know， and and then I'll just state for you。

 you know， a version that you can get from fiddling around with the numbers。

You and which is easier to remember when applying it in practice， this， by the way。

 is like the fourth most useful thing that I've ever found in any of the research that I've ever done。

😊，So how would we， okay， so we need the upper bound this and ideally。

 you know we want to our goal really is the upper bound this by something that is exponentially small in M。

😊，Okay， that's that's the real ambition here。 right。

 We want the probability of screwing up to decrease exponentially with the number of repetitions of our algorithm。

 That's what we really want。real you。There's a nice board okay， so how could we do that？😊，All right。

Okay， so so so there's like one clever trick that goes into the proof of the turnoff bound and the clever trick is to look at exponentials of these quantities so what we're going to say we're going to say this probability here is obviously we could pick any C we wanted and this would just be equal。

 let's say any C greater than one that we wanted。And this would obviously be equal to the probability that C to the x1 plus xM。

 plus x2 and so forth plus XM is greater than or equal to C to the BM。😊，Right？Okay。But now that。

Is equal to the probability that。C to the x1 times c to the x2 and so forth。

Up to C to the XM is greater than or equal to C to the Bf。Right。

 so this is now what we are interested in。 Okay and now we can use Markovs inequality。 Okay， know。

 so we're going to use Markov's inequality， not for the original statement， but for this statement。

Okay we were going to say， you know， because because you know C。

 you know these numbers greater than what you the C， let's say C is 2 or something right。

2 raised the various powers， this is a non-ne we the variable right you notice that okay so we can say the probability of this happening is at most。

The expectation。Of。C to the x1。And times you know and so forth up the C to the XM divided by。

C to the BM， right， we're interested in the probability that you know this random variable will exceed its expectation by you know by more than this factor right So its you know it may know you just this is just a rewriting of this。

 okay。😊，All right， now， what can we say about this thing in the numerator， anyone？Yeah。Oh。

We can separate it out。 Yeah， we can separate it out because the exc are independent。 Okay。

 this is where we use independence。Only。呃。Okay， because these guys are all dependent。

 you that is why we can separate these out。Okay， now what is the expectation of C to the Xi？

Canone calculate it for me？But what's Xi， first of all？X，huh？XI， let's say is。

Is a 01 random variable， right which。You know， we might as well just take the worst case just assume that this is equal。

 then it's random variable that it's one with probability A and it's 0 with probability 1 minus a。

Okay， so then what's the expectation of this？😊，Well， with probability A， we have what？C， yep。

 and with probability1 minus a， we have what？1 right probability 1 minus a xxii is 0。

 so if we get c to the0， which is1。Okay， and we have that M times。So now we have this。Okay。

So we get this upper bound on the probability of the bad thing happening okay and you know so all right。

 there's something weird you know inside here you you have to mess around with okay but just assume that there's something you know。

 you know but remember that we get to choose C however we want okay so you know。

 so now to just assume that you've chosen C in such a way that this weird thing inside is less than what then what is this bound basically。

Then this bound is decreasing exponentially with that， okay。

 which is exactly the thing that you wanted。Okay。😊，All right。

 so like an easier to remember version than you know you know and then you have to know solve a calculus problem of you know choosing C to optimize that bound and you you don't have to exactly optimize it just get something that's pretty good right so then you know the question is like you know just how good you need it to be versus you know how hard is the resulting formula going to be to remember so。

So one sort of relatively easy to remember version is that if B is at least1 plus delta times a。

 then。You can get the probability of something bad happening to be at most e to the minus delta squared AM divided by3。

Okay。So in the case of BPP， we would have， you know， B is a half， a is one third。

 so Delta is what anyone。A half， right， Dlta is a half。 So then you you would get E。To the minus。

 what a quarter times a third。Times m divided by3， right， which is y。

 which is1 over which is e to the minus m over 36。Okay so then this would tell you that you know the probability that your BPP algorithm is going to screw up if you repeat at M times and take the majority vote among all the answers will be at most e to the minus M over 36 okay so you know。

 so maybe it doesn't decrease quite as fast as you know you could have hoped， but you know。

 but it does decrease exponentially with M。So you know you repeat thousands of times。

 this is going to become a really， really small probability of error。

 so that's the turnoff bound's here， I should。😊，Oh。Here is the form that we derived。

 here's the form that you can remember。Okay， and the turnoff bound in particular justifies us in saying that you know the exact choice of constants when we were defining BPP。

 which is not very important right， we could have said if x is not an L。

 then you accept with probability at most 0。8 and if x is an L then you accept with probability at least 0。

9 right and as long as you've got two numbers that are bounded away from each other。

 then you can amplify them okay by a repetition。Okay。呃。In fact。

 something even stronger than that is true in fact。

Even if you know we had said that like if the answer。

 if x is not an L then you have to accept with probability at most a half and if x is an L then you have to accept with probability at least a half plus epsilon where epsilon could be something really small。

 it could be1 over n， let's say it could be something that decreases with n okay how many by the way。

 does anyone know。You know， if you have a coin and you're trying to decide whether it's fair or whether it has a bias of epsilon。

 you know， about how many times are you going to have to flip the coin you know。

 as a function of epsilon in order to decide that with， you know， let's say you know。

 90% probability of being right。This is a very useful thing to know。

This this is not the turnoff bound right the turnoff bound is sort of addressing a different question right that once once you've gotten。

 once you're right with 90% probability right then how many times do you have to repeat until you're right with 99。

999 you% probability okay here we're asking a different question here we're asking if you're right with probability just slightly more than a half then how many times do you have to repeat until you're right with 90% probability。

So if you can make a gas of something and it's going to be right a half plus epsilon fraction of the time。

 then how many times do you have to repeat your gas until you're right， 90% of the time？Okay。

The answer， you can， you can mark this out by like calculating variances or something。

 It's about one over epsilon squared。Okay， so if you had a you。

 a coin that you knew was either fair or else it had like a 1% bias。

 then in order to decide which you'd have to flip the coin， you know， something on the order of 10。

000 times。Okay， you know， which， you know， it was a lot， but it's not like an exponentially lot。

 right， It's， you know， just quadratic and one over epsilon， okay so。U。Okay。

 so so in fact we could even define BPP you know where instead of one third and two thirdhirs we had。

 let's say a half minus one over n and a half plus1 over n you know the gap between these things could even decrease with n but it better only decrease with n at a polynomial rate if it decreases an exponential rate then this one over epsilon squared is exponential okay and then you're really in trouble because then you have then you that saying that you would have to repeat your randomized algorithm an exponential number of times before you would earned anything okay and you and that is not that is really really not efficient okay and you on P at 5 you have a problem dealing with the complexity class PP right in PP is like BP except without the B。

With you the B standing stands for bounded error okay and so PP is like you probabilistic polynomial time without this condition of bounded error so all you say is that if x is in L then you have to accept with probability more than a half and x is not an L then you have to accept with probability less than a half okay and that because there is no you know appreciable gap between the accepting and the rejecting cases。

 that is an extraordinarily powerful class okay that you know in fact。

 you know you show I believe on the PAT that that class contains NB。😊。

that class can solve NP complete problems。 It's contained in peace space。It's a。

It's not even known to be anywhere in the polynomial hierarchy， but will strongly believe not to be。

 I should say， okay that so this PP is like way up here somewhere。Okay， so， so just， you know。

 a couple more things to talk about， know， one is。So we saw that RP is contained in NP。

 coRP is contained in CoNP， what about BPP， okay is BPP contained in NP anyone what does anyone think？

What could be an NP witness for a language， what could be a proof that a language is in BPP？Well。

 you know， you could think about it a little， right， and you could say， well。

 you know the witness could be， you know， here are a whole bunch of strings。

 a whole bunch of random strings， RI that cause M of XRI to accept。Here's a bunch of know。

 randomness strings that cause your algorithm to accept。 Okay， is that a convincing witness？

If you have enough of them， well， you know it's kind of like you know a politician right saying look。

 you know you know there is overwhelming support in the country for my policies because look here is a stadium of like 50。

000 supporters of me right and they all agree with everything I say right。

 you know all of them right， what's the chance that all 50。

000 of these people in this stadium would agree with me if the whole country didn't agree with me。

 is this a convincing argument？Right not quite right because you know the politician may it is conceivable that they just handpicked these people to be you know the ones who agree with them and even if only 1% of the country agreed with them。

 they could have filled a stadium of 50，000 I guess if there's at least 5 million people in the country so the same you know you have the same problem with showing that BPP is contained an NP right you know I could show you 10。

000 randomness strings that cause your randomized algorithm to accept but that still doesn't mean that a large fraction of all the randomness strings cause the algorithm to accept okay because I just could have handpicked 10。

000 that serve my purposes and so for basically that reason。

 you know no one knows how to show to this day that BPP is contained an NP。😊。

There is a nontrivial theorem， one that we are not going to prove in this class。

 although it's proved in 6840 and it's also proved in the SPSer textbook。

 if you're interested to see。And I could explain it in office hours if someone wants to say it。

The non trivial theorem from the 1980s says the BPP is contained in NP to the NP Okay so it is in the polynomial hierarchy。

 So let me draw it like this okay you know。And this is due to siper， gas and water。

From the early 1980s。Okay， you know， now because BP is closed under compliment， we also get that。

BPP is contained in CoNP。To the NPp。Okay， so it's contained in both of those。

And that's more or less the best upper bound that we know on BPPP in terms of the complexity classes that you've seen previously。

Okay。All right， now I promised you that I would give you an example of a randomized algorithm that we still to this day do not know how to derandomize。

 Okay， so you know something， you know， something which is N RPRP but which is not known to this day to BNP so there's actually a very cool example。

 I think， and。I'll call this the non zero circuit problem。Right。The NCP。Okay。

 and so here's going to be the problem。So I have a I'm going to consider an arithmetic circuit， okay。

 so you know we've discussed Boolean circuits in this class， okay。

 but I am going to consider a circuit。Where the gates do plus and minus and times。They do。

 know like the basic operations of constructing polynomials or I'd say the basic arithmetic operations except that I don't want to deal with division。

 okay？So， so the rule is you get to start with one at the bottom and then。You can have plus gates。

 like here I've done one plus one that produces the output that you would expect too。U you can。

You know， have another plus， now I've got three， okay， I can do it times， now I've got six， okay。

 and you know I could keep building up you know， bigger and bigger numbers by using these gates and then at the very top know I could do here。

I I can have a minus gate as well， so now this is six minus3 so that's three okay you know I can keep building you know building up a number like this。

 I don't know if you any of you ever played the card game 24 or like you have to build up numbers by you know combining arithmetic operations。

 okay it's a little like that。So。Okay， and now you know， I'm going to consider a very。

 very simple computational problem， okay which is I give you such an arithmetic circuit。

 you know like that， okay it just it compute some concrete number and all I'm asking you to decide is does it compute a non-zero number or not now that sounds like a really。

 really easy problem right， how on earth could this problem not be in P？😊。

Why isn't it just obviously in P？see okay， so does anyone see a difficulty with showing that this problem is NP P？

Yes， I give you as input， a description of the arithmetic circuit， Okay。

 let me let me let me let me write it on the board Okay， so so the language will consist of all。

Descriptions of arithmetic circuits that evaluate something nonze。

So I give as input the description of the arithmetic circuit。

 you have to decide whether it outputs a non zero number。

So what would be an obvious algorithm for trying to solve this problem， anyone？

Just evaluate the number， just go through the circuit， compute the number。

 see what happens Okay can anyone see a difficulty in doing that？Doing it in polynomial time。

 I should say。Well。All right。So。This is one of these cases where you know before giving you the algorithm。

 I first have to show you the need for the algorithm， okay， so here's the difficulty。

Let's say that I took one， or right， I'll do one plus one to get two then。I do two times 2。

 All right， now I got4。 Allright， so far。 they're good。 Now I got four times 4。 Okay， now I have 16。

 right。Now I have 16 times 16， that's 256， right？Now I have 256 times 256。

 that's 665536 right now I've in fact。I'll just keep going like this。

 I'm just going to keep squaring， okay。You know， I can keep squaring and before well let's say I do that 100 times right now now I've produced a really。

 really， really big number okay， in fact， I do， if I start with two and I do repeated squaring n times。

 then what number would I get？Well。I'll get two squared， squared。Squared。Squared and so forth。

 which is if I do it n times， that's 2 to the two to the n。Okay， you know。

 how many bits does that number take to write down？2 to the end。 Okay。

 so what they're saying is that just by squaring a linear number of times。

 I can produce a number using an arithmetic circuit that takes exponentially many bits just to write it down。

Okay。So so if I were just simulating this in the obvious way。

 you know then you know this is telling me that now I've got an exponential time algorithm right and you might say。

 well who cares because if the number is so enormous anyway then you know then certainly the numbers nonzero which is the only thing you asked me okay but no not so fast because what if I had another gigantic sequence of squarings you know and now I've got these two different exponentially large numbers and now I've got a minus okay and I just cancel them against each other poof the whole thing vanishes all right well you know in this particular example of course you can tell me that you know okay in that case the output's going to be zero right but now you know you can see the difficulty right I'm asking you to design a general purpose algorithm right that's going to be able to sort of keep track of these battles among these you know doubly exponentially large numbers that could cancel each other。

😊，And tell me whether what's left over at the end of it is exactly zero or not。You know。

 not obvious how to do that without having to you know write down an exponential number of bits。Okay。

 all right， but there is a randomized solution。Okay。In fact。

Can anyone guess what would be a randomized approach that would help us for this problem？All right。

So。I'll tell you， what you can do is you can do all of the arithmetic mod P。

 where P is some randomly chosen prime number。You can just pick a random prime。

 do all the arithmetic mod that prime， okay you know you can do you know you can do addition。

 multi subtraction， multiplication， do all of it mod P right and then what can you conclude from this right let's say that you do all of the arithmetic mod P and you get something nonzero at the end then what can you say？

Yeah， in that case， your original number was definitely nonzero as well Okay。

 so what's the difficulty， Well let's say that you do all the arithmetic mod P and you get something that's zero。

 okay then what？Yeah， then you know then what you can say is that then P divides whatever was the output of your circuit okay and now you know。

 so now you can say either you know the output is0 or it's a multiple of p okay which you know that's some information。

 it's not quite what you wanted to know， okay， but now the hope is that if you would pick p at random。

 then with high probability you know you know the only way that you're going to get an answer that zero might p is if the answer is actually zero。

Okay， so that's the hope。So。So let's call the output of the circuit A， okay。

 I'll just call it a okay，'ll assume that this you know。

 let's say this was a circuit with at most N gates。

 then can anyone upper bound as absolute value for me？Well。

 the biggest numbers I can possibly produce by a circuit of Pi N is just going to be the one that I produce by repeated squaring because like each number that I can produce is going to be like most the square of the biggest number that I could produce with the circuit of sizei n minus1 so I can say that the output of an arithmetic circuit of size n is at most2 to the two to the n in absolute value。

Okay， and now。Here's a question now I want to look at a mod P。

Where P is going to be a random prime number between， I don't know。Two to the N， all right。

 let's just say it's a random prime number。From well， two is the first prime number fine。

 from two up to two to the two。Okay， so can I choose a random such prime number， the first question。

 I guess？Sure I can I mean we discussed this way back in the very first lecture right I could just keep picking random numbers in this range for each one check whether it's prime or not you know halt as soon as I find a prime you know I know how to check primity and deterministic polynomial time you know at least today I know you and furthermore the prime number theorem tells me that you know a lot of these numbers are prime okay。

You know， if I pick a number at random in this range。

 then the probability that I'm going to get a prime is going to be like C over at okay。

 that's what the prime number theorem tells me so you know after only a linear number of tries。

 you know I will get a prime okay with overwhelming probability okay now the question is，呃。

Let's say that a is nonzero then I want to argue that the probability over a randomly chosen prime P that a mod p is non-zero is really large that you there's only a very small chance that even though despite the fact that a was nonze。

 that a might p is going to be zero， okay， can anyone see how I would argue that？Well。

 I've got this nonzero number a right， A is fixed， okay now I need to I'm picking p at random。

 I need to up bound the probability that P is going to divide a。Well。

 how many primes are there that could possibly divide A？

Could anyone give me an upper bound on how many primes there could possibly be that could divide A？

All right， remember， a is it most two to the two to the n in absolute value。

 so you know something about it， all right， how many different primes could possibly divide such a number？

Well， I'll give you a hint， suppose that every prime are equal to till。In that case。

 how many primes could divide that number？Two to the N， okay， in fact。

 not all primes are equal to two。Yeah， in fact， all but one of them are unequal to two， okay。

 but that only makes matters worse， okay， because the other primes are all bigger so you can only have fewer of them。

 right， which means that there can be it。