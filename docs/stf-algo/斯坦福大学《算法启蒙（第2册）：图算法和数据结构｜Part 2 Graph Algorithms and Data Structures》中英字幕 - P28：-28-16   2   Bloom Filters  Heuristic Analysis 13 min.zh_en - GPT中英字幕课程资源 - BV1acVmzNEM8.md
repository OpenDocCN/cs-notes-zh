# 斯坦福大学《算法启蒙（第2册）：图算法和数据结构｜Part 2 Graph Algorithms and Data Structures》中英字幕 - P28：-28-16   2   Bloom Filters  Heuristic Analysis 13 min.zh_en - GPT中英字幕课程资源 - BV1acVmzNEM8

![](img/9fdc555af93e5e2ff4a65a8a81d26f89_0.png)

So before we embark the analysis， what are we hoping to understand。

 well what seems intuitively clear is that there's going to be some tradeoff between the two resources of a bloom filter。

 one resource is space consumption， the other resource essentially correctness。

 so the more space we use the larger number of bits wed hope that we'd make fewer and fewer errors and then as we compress the table more and more reuse bits more and more for different objects。

 then presumably the error rate is going to increase。

So the goal of the analysis that we're about to do is to understand this tradeoff precisely at a quantitative level。

 once we understand the tradeoff curve between these two resources， then we can ask。

 is there a sweet spot which gives us a useful data structure。

 quite small space and quite manageable error probability？

So the way we're going to proceed with the analysis will be familiar to those of you that watch the open addressing video about hash tables。

 so to make the mathematical analysis tractable and going to make a heuristic assumption。

 it's a strong assumption which is really not satisfied by hash functions you would use in practice。

 we're going to use that assumption to derive or performance guarantee for bloom filters but as always as in any implementation you should check that your implementation actually is getting performance comparable to what the idealized analysis should suggest。

 that said if you use a good hash function and if you have non-pathological data。

 the hopes and this is borne out in many empirical studies is that you will see performance comparable to what the heuristic analysis will suggest。

So what is the heuristic assumption while it's going to be again familiar from our hashing discussion。

 we're just going to assume that all the hashing is totally random。

 so for each choice of a hash function H and for each possible object AX， the slot。

 the position of the array， which the hash function gives for that object is uniform at random first of all。

 and it's independent from all other outputs of all hash functions on all objects。

So the setup then is we have n bits。We have a data set， capital S。

 which we have inserted into our boom filter。Now our eventual goal is to understand the error rate or the false positive probability。

 that is the chance that an object which we haven't inserted into the bloom filter looks as if it has been inserted into the bloom filter。

 but as a preliminary step I want to ask about the population of ones after we've inserted this data set capital S into the B filter。

 so specifically let's focus on a particular position of the array and by symmetry it doesn't matter which one。

 and let's ask what is the probability that a given bit。

 a given position in this array has been set to one after we've inserted this entire data set capital S。



![](img/9fdc555af93e5e2ff4a65a8a81d26f89_2.png)

All right so this is a somewhat difficult quiz question actually the correct answer is the second answer it's one minus quantity。

1 minus one of our n raiseds to the number of hash functions k timess the number of objects cardinality of S that's the probability that say the first bit of a bloom filter has been set to one after the data set capital S has been inserted so the maybe easiest way to see this is the first focus on the first answer so the first answer is going to be the probability I claim that the first bit is zero after the entire data set has been inserted。

 then of course probabilitys1 is just one minus this quantity which is equal to the second answer。

So we just need to understand why the first choice is the probability that the first bit equals 0。

 Well it's initially zero。 and remember stuff is only set from0 to1。

 so we need to analyze the probability that this first bit survives all of these darts that are getting thrown to the bloom filter over the course of this entire data set being inserted So there are these cardinality of S objects each get inserted on an insertion K darts uniformly at random and independent from each other are effectively thrown at the array at the bloom filter Any position that a dart hits gets set to one maybe it was one already。

 but if it was0 it gets set to one if it's one it stays1 So how is this first bit going to stays  zero。

 it has to be missed by all of the darts a given dart。

 a given bit flip is uniformly likely to be any of the n bits So the probability that winds up being this bit is only one over n the probability that it's fortunately somebody else well that's one minus1 over n。

 So you have a chance of surviving a single dart with probability1 minus1 over n theres the number of hash functions K times the number of objects Carinality of s and darts。

throwone right cap per object that gets inserted， so the overall probability of allluing all of the darts is 1 minus1 over and raiseds to the number of hash functions k times the number of insertions cognitive of s and again。

 the probability that it's one is just one minus that quantity。

 which is the second option in the quiz。So let's go ahead and resume our analysis using the answer to that quiz。



![](img/9fdc555af93e5e2ff4a65a8a81d26f89_4.png)

So what do we discover， discover the probability that a given bit is1 is1 minus quantity。

 1 minus1 over n， or n is the number of positions or raised to the number of has functions K times the number of insertions cardality of S so that's a kind of messy quantity so let's recall a simple estimation facts that we used once earlier。

 you saw this when we analyzed cargos contraction algorithm and the benefit of multiple repetitions of cargo's contraction algorithm。

And the trick here is to estimate a quantity that's up the form 1 plus x or 1 minus x by either to the x or u the minus x as the case may be。

So if you take the function1 plus x， which goes through the points minus10 and01。And of course。

 there's a straight line， and then you also look at the function E to the x。Well。

 those two functions are going to kiss at the point0 comma 1 and everywhere else e to the x is going to be above。

1 plus x。So for any real value of x， we can always upper bound the quantity 1 plus x by e to the minus x。

 so let's apply this fact to this quantity here，1 minus1 over n raised to the K times count of S。

 we're going to take x to be minus1 over n so that gives us an upper bound on this probability of 1 minus E。

To the minus k times the number of insertions over n。 Okay so that's taking x to be minus1 over n。

Let's simplify our lives a little bit further by introducing some notation。

 So I'm going to let B denote the number of bits that we're using per object。

 So we this is the quantity I was telling you to think about as8 previously， This is the ratio N。

 The total number of bits divided by the cardinality of S。

 So this green expression becomes one minus。E to the minus K over B。

Where B is the number of bits per object。And now we're already seeing this type of tradeoff that we were expecting。

 remember we were expecting that as we use more and more space。

 then the error rate we think should go down。 So if you compress the table a lot。

 so you reuse bits for lots of different objects， that's when you start going to see a lot of false positives。

 So in this light blue expression， if you take the number of bits per objects for the number of space。

 the amount of space little B if you take that growing very large tending to infinity this exponent tends to0。

 So either the minus zero is one。 So overall this probability of a given bit being one is tending to zero。

 So that is the more bits you have， the bigger space you have the smaller the fraction of ones。

 the bigger the fraction of zeros that should translate to a smaller false positive probability and that's what it will make precise on the next and final slot。

So let's rewrite the upshot from the last slide， the probability that a given bit is equal to1 is batterted above by 1 minus e to the minus k over B。

 where K is the number of hash functions and B is the number of bits we're using per object。

Now this is not the quantity we care about， the quantity we care about is a false positive probability where something looks like it's in the bloom filter even though it's never been inserted。

 so it's focused on some object like some IP address。

 which has never ever been inserted into this bloom filter。So for a given object X。

 which has not in the data that has not been inserted into the bloom filter。

 what has to happen for us to have a successful lookup， a false positive for this object。

 well each one of its K bits has to be set to one so we already computed probability that a given bit is set to one so what has to happen for all K of the bits that indicate x's membership in the boom filter all k of them have to be set to1。

 so we just take the quantity we computed on the previous slide and we raise that to the K power indicating that it has to happen K different times。

So believe it or not， we now have exactly what we wanted， what we set out to do。

 which is derive a quantitative understanding of the intuitive tradeoff between on the one hand the space used and on the other hand on the error probability。

 the false positive probability so we're going to call this green circle quantity a name we'll call it epsilon for the error rate and again all errors or false positives。

And again， as B goes to infinity as we use more and more space， this exponent goes to zero。

 so1 minus e to that quantity is going to0 as well and of course once we power it to the k power it gets even closer to zero so the bigger B gets the smaller this error rate epsilon gets so now let's get to the punch line so remember the question is is this data structure actually useful can we actually set all of the parameters in a way that we get both really usefully small space。

 but a tolerable error epsilon and of course we wouldn't be giving this video if the answer wasn't yes。

Now， one thing I've been alluding all along is how do we set k。

 how do we choose the number of hash functions I told you at the very beginning you think of k as a small constant like  two。

3，4，5。And now that we have this really nice quantitative version of how the error rate and the space trade off with each other。

 we can answer how to set K， namely set K optimally， so what do I mean。

 well fix the number of bits that you're using per object 8， 16，24， whatever for fixed B。

 you can just choose decay that minimizes this green quantity that minimizes the error rate epsilon。

So how do you minimize this quantity well you do it just like you learn in calculus and I'll leave this as an exercise for you to do in the privacy of your own home。

 but for fixed B， the way to get this green quantity epsilon as small as possible is to say the number of hash functions k to be roughly the natural log of2。

 that's a number less than1 notice that's like 0。693 times B。



![](img/9fdc555af93e5e2ff4a65a8a81d26f89_6.png)

So in other words， the number of hash functions for the optimal implementation of a bloom filter is scaling linearly with the number of bits that you're using per object。

 it's about 0。693 times the bits per object。Of course， this is generally not going to be an integer。

 so you just pick K to be either this number rounded up or this number rounded down。

But continuing the heuristic analysis， now that we know how to set K optimally to minimize the error for a given amount of space。

 we can plug that value of k back in and see， well。

 how does the space and the error rate trade off against each other and we get a very nice answer。

Specifically， we get that the error rate epsilon， this is under an optimal choice of the number of hash functions k。

 decreases exponentially in the number of bits that you use per object。

So it's roughly one half raised to the natural log of 2 or 0。

693 roughly times the number of bits per object B， but again。

 the key qualitative point here is notice that epsilon is going down really quickly as you scale B。

 If you doubled the number of bits that you're allocating per object。

 you're squaring the error rates and for small error rates， squaring it makes it much， much。

 much smaller。And of course， this is just one equation in two variables， if you prefer。

 you can solve this equation to express B， the space requirement as a function of an error requirement。

 so if you know that the tolerance for false positives in your application is 1% you can just solve this for B and figure out how many bits per object you need to allocate。

And so rewriting what you get is that the number of bits per object that you need is roughly 1。

44 times the log base 2 of1 over epsilon。 So as expected， as epsilon gets smaller and smaller。

 you want fewer and fewer errors， the space requirements will increase So the final question is。

 is it a useful data structure， Can you set all the parameters so that you get you know a really interesting space error trade off and the answer is totally。

 so let me give you an example。Let's go back to having eight bits。

Of storage per object so that's corresponds to B equals8。

 then what this pink formula indicates is we should use five or six hash functions and already you have an error probability of something like 2%。

 which for a lot of the motivating applications we talked about is already good enough and again。

 if you double the number of bits to say 16 per object。

 then this error probability would be really small。

 would be pushing one in 5000 or something like that。So to conclude。

 at least in this idealized analysis， which again， you should check against in any rural world implementation。

 although empirically it is definitely achievable with well implementeded bloom filters and non-pathological data to get this kind of performance even with really a ridiculously minuscule amount of space per object much less generally than storing the object itself。

 you can get fast inserts fast lookups， you do have to have false positives。

 but with a very controllable amount of error rates。

 and that's what makes bloom filters a win in a number of applications。

