# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P72：28_04_03_全域哈希链式分析-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So in this video we're going to start reasoning about the performance of hash tables。

 and in particular， we'll make precise this idea that properly implemented the guaranteed Conantine lookup。

So let me just briefly remind you of the roadmap that we're in the middle of so we observed that every fixed hash function is subject to a pathological data set and so exploring the solution of making a real-time decision of what hash function to use and we've already gone over this really quite interesting definition of universal hash functions and that's the proposed definition of a good random hash function more in the previous video I showed you that there are simple such families of hash functions they don't take much space to store。

 they don't take much time to evaluate and the plan for this video is to prove formally that if you draw a hash function uniformly a random from a universal family of hash functions like the one we saw in the previous video。

 then you're guaranteed expected constant time for all of the supported operations。

So here's the definition once more of a universal family of hash functions。

 we'll be using this definition of course， when we prove that these hash functions give good performance So remember we're talking now about a set of hash functions。

 these are all of the conceivable real-time decisions you might make about which hash function to use so the universe is fixed this is something like IP addresses the number of buckets is fixed that's going be something like 10000。

 say and what it means for a family to be universal is that the probability that any given pair of items collides is as good as small as with the gold standard of completely perfect uniform random hashing that is for each pair X Y of distinct elements of the universe so for example for each distinct pair of IP addresses the probability over the choice of the random hash function little H from the family script H is no more than one over N or n is the number of buckets。

 So if you have 10000 buckets， the probability that any given pair of IP addresses winds up getting mapped to the same bucket is。

One in 10，000。Let me now spell out the precise guarantee we're going to prove if you use a randomly chosen hash function from a universal family。

So for this video， we're going to only talk about hash tables implemented with chaining with one linked list per bucket。

 we'll be able to give a completely precise mathematical analysis with this collision resolution scheme。

We're going to analyze the performance of this hash table in expectation over the choice of a hash function little H drawn uniformly from a universal family script H。

So for example， for the family that we constructed in the previous video。

 this just amounts to choosing each of the four coefficients uniformly at random。

 that's how you select a universal， that's how you select a hash function uniformly at random。

So this theorem and also the definition of universal hash functions dates back to a 1979 research paper by Carter and Wgman。

 the idea of hashing dates back a quite a bit before that certainly to the 50s。

 so this just kind of shows how sometimes ideas have to be percolating for a while before you find the right way to explain what's going on。

 so Carter and Wgman provided this very clean and modular way of thinking about performance of hashing through this universal hashing definition。

And the guarantee is exactly the one that I promised way back when we talked about what operations are supported by hash tables and what kind of performance should you expect。

 you should expect constant time performance。As always with hashing， there is some fine print。

 so let me just be precise about what the caveats of this guarantee are。 So first of all。

 necessarily this guarantee is an expectation， so it's on average over the choice of the hash function little H。

But I want to reiterate that this guarantee does hold for an arbitrary data set。

 So this guarantee is quite reminiscent of the one we had for the randomized Quickword algorithm。

 In Quicksort， weve made no assumptions about the data。

 It was a completely arbitrary input array and the guarantee set on average over the realtime randomized decisions of the algorithm。

 no matter what the input is the expected running time was n log n。 here we're saying again。

 no assumptions about the data。 What doesn't matter what you're storing in the hash table。

 an expectation over the realtime random decision of what hash function you use。

 you should expect constant time performance， no matter what that data is。

 So the second caveat is something we've talked about before。

 remember the key to having good hash table performance。 not only do you need a good hash function。

 which is what this universality guarantee is providing us。

 but you also need to control the load of the hash table， So of course。

 to get constant time performance as we've discussed。

 a necessary condition is that you have enough buckets to hold more or less the stuff that you're storing。

 that is the load alpha。

![](img/05160d386c5b055b3de860b718287b48_1.png)

The numberumb of objects in the table divided by the number of buckets should be constant for this theorem to hold。

And finally， whenever you do a hash table operation。

 you have to in particular invoke the hash function on whatever key you're given。

 so in order to have constant time performance， it better be the case that it only takes constant time to evaluate your hash function。

And that's， of course something we also discussed in the previous video when we emphasize the importance of having simple universal hash functions like those random linear combinations we discussed in the previous video。

In general， the mathematical analysis of hasht performance is a quite deep field and there are some quite mathematically interesting results that are well outside the scope of this course。

 but what's cool is this theorem I will be able to provide you a full and rigorous proof so for hash tables with chaining and using randomly chosen universal hash functions I'm going now prove that you do get constant time performance All right so hash tables support various operations。

 insert delete and lookup but really if we can just bound the running time of an unsuccessful lookup that's going to be enough to bound the running time of all of these operations remember in a hash table with chaining。

 you first hash the appropriate bucket and then you do the appropriate insert。

 delete or lookup in the linked list in that bucket so the worst case as far as traversing through this linked list is you're looking for something that's not there because then you got to look at every single element in the list and fall off the end of the list before you can conclude that the lookup has failed Of course insertion as we discussed is always constant time deletion and successful searches well you might get lucky and stop early。

Before you hit the end of the list， so all we're going to do is bother to analyze unsuccessful lookups that will carry over to all of the other operations。

So a little more precisely， let's let S be the data set。

 this is the objects that we're storing in our hash table。

And remember that to get constant time looked up， it certainly needs to be the case that the load is constant。

 So we're assuming that the size of S is big O of the number of buckets n。

And let's suppose we're searching for some other object， which is not an S， call it X。And again。

 I want to emphasize we're making no assumptions about what this data set S is other than that the size is comparable with the number of buckets。

So conceptually doing a lookup in a hash table with chaining is a very simple thing。

 you just hash to the appropriate bucket and then you scan through the linked list in that bucket。

 so conceptually it's very easy to write down what the running time of this unsuccessful lookup is。

It's got two parts， so the first thing you do is you evaluate the hash function to figure out the right bucket and again。

 remember we're assuming that we have a simple enough hash function that this takes constant time。

AndNow， of course， the magic of hash functions is that given this hash value。

 we can zip right to where the linked list is to search for X using random access into our array of buckets。

 so we go straight to the appropriate place in our array of buckets and we just search through the list ultimately failing to find what we're looking for X。

Traversing a linked list， as you all know， takes time proportional to the length of the list。

So we find something we discussed informally in the past。

 which is that the running time of hash table operations implemented with chaining is governed by the list length。

 So that's really the key quantity we have to understand。 So let's call this。

 let's give us a name capital L it's important enough to give a name So what I want you to appreciate at this point is that this key quantity capital L。

 the list of the length in X's bucket is a random variable。 It is a function of which hash function。

 little H we wind up selecting in real time。 So for some choices of our hash function little H。

 this list length might be as small as0， but for other choices of this hash function H this list length could be bigger So this is exactly analogous to in quick sort where depending on the realtime decision of which random pivot element you use you're going to get a different number of comparisons。

 a different running time So the list length and hence the time for the unsuccessful search。



![](img/05160d386c5b055b3de860b718287b48_3.png)

Depends on the hash function， little H， which we're choosing at random。

So let's recall what it is we're trying to prove， we're trying to prove an upper bound on the running time of an unsuccessful lookup on average。

 where the on average is over the choice of the hash function little H。

 we've expressed this lookup time in terms of the average list length in X's bucket where again the average is over the random choice of H summarizing we've reduced what we care about。

 expected time for lookup to understanding the expected value of this random variable capital L。

 the average list length in X's bucket， so that's what we got to do。

 weve got to compute the expected value of this random variable capital L。Now to do that。

 I want to jog your memory of a general technique for analyzing expectations。

 which you haven't seen in a while。 The last time we saw it， I believe。

 was when we were doing the analysis of randomized quick sort and counting its comparisons So here's a general decomposition principle which we're now going use in exactly the same way as we did in Quick sort here to analyze the performance of hashing with chaining So this is where you want to understand the expectation of a random variable which is complicated but what you can express as the sum of much simpler random variables。

 ideally01 or indicator random variables So the first step is to figure out a random variable capital Y is what I'm calling it here that you really care about Now we finish the last slide completing step one what we really care about is capital L the list length in X's bucket so that governs the running time of an unsuccessful look up clearly that's what we really care about step two of the decomposition principle is well the random variable you care about is complicated。

 hard to analyze。Directly but decompose it as a sum of 01 indicator random variables so that's what we're going to do at the beginning of the next slide why is it useful to decompose a complicated random variable into the sum of the01 random variables while then you're in the wheelhouse of linearity of expectation you get that the expected value of the random variable that you care about is just the sum of the expected values of the different indicator random variables and those expectations are generally much easier to understand and that will again be the case here in this theorem about the performance of hash tables with chaining。



![](img/05160d386c5b055b3de860b718287b48_5.png)

So let's apply this three step decomposition principle to complete the proof of the Carter Wegman theorem。

So for the record， let me just remind you about the random variable that we actually really care about。

 that's capital L。The reason that's a random variable is because it depends on the choice of a hash function little H。

 This number could vary between 0 and something much， much bigger than0。

 depending on which H you choose。 So this is complicated， hard to analyze directly。

 so let's try to express it as the sum of 01 random variables。

 So here are the 01 random variables that are going to be the constituents of capital L。

 we're going have one such variable for each object Y in the data set。

 Now remember this is an unsuccessful search， X is not in the dataset capital S。

 So if y is in the data X and y are necessarily different。

And we will define each random variable z sub y as follows。

 we'll define it as1 if y collides with x under H。And zero otherwise。So for a given Z Y。

 we have fixed objects X and Y so x is some IP address， say Y is some distinct IP address。

 X is not in our hash table， y is in our hash table。

 and now depending on which hash function we wind up using these two distinct IP addresses may or may not get mapped to the same bucket of our hash table so this indicator random variables just indicating whether or not they collide。

 whether or not we unluckily choose a hash function little H that sends these distinct IP addresses X and Y to exactly the same bucket so that's Zy clearly by definition it's a01 random variable。

Now， here's what's cool about these random variables is that。Capital L。

 the list length that we care about， decomposes precisely into the sum of the Z Ys。That is。

 we can write capital L as being equal to the sum over the objects in the hash table of Zy。

So if you think about it， this equation is always true no matter what the hash function H is so if you choose some hash function that maps this IP address x to say bucket number 17 capital L is just counting how many other objects in the hash table wound up getting mapped to bucket number 17 so maybe 10 different objects got mapped to bucket number 17。

 those are exactly the 10 different values of y that will have their zy equal to1 right so L is just counting the number of objects in the data set S that's collide with X a given Zy is just counting whether or not a given object Y in the hash table is colliding with x。

 so suming over all the possible things that could collide with x somethingming over the Zys we of course get the total number of things that collide with X which is exactly equal to the number the population of x's bucket in the hash table。

All right， so we've got all of our ducks lined up in a row now if we just remember all of the things we have going for us。

 we can just follow our nose and nail the proof of this theorem so what is it that we have going for us well in addition to this decomposition of the list length into indicator random variables we've got linear expectation going for us we've got the fact that our hash function is drawn from a universal family going for us and we've got the fact that we've chosen the number of buckets end to be comparable to the data set size so we want to use all of those assumptions and finish the proof that the expected performance is constant。

So we're going to have a few inequalities and we're going to begin with the thing that we really care about。

 we care about the average list length in X's bucket remember we saw in the previous slide this is what governs the expected performance of the lookup if we can prove that the expected value of capital L is constant we're done we finished the theorem so the whole point of this decomposition principle is to apply linearity of expectation。

 which says that the expected value of a sum of random variables equals the sum of the expected values。

So because L can be expressed as the sum of these Zys。

 we can reverse the summation in the expectation， and we can first sum over the Y's over the objects in the hash table。

And then take the expected value of Zy。Now something which came up in our quickword analysis。

 but what you might have forgotten is that01 random variables have particularly simple expectations。

 so the next quiz is just going to jog your memory about why01 random variables are so nice in this context。



![](img/05160d386c5b055b3de860b718287b48_7.png)

Okay the answer this quiz is the third one， the expected value of Zy is simply the probability that x and y collide。

 that just follows from the definition of the random variables Zy and the definition of expectation。

 namely recall how do we define Zy， this just is one if this object Y in the hash table happens to collide with the object X that we're looking for under the hash function X。

And zero otherwise， again， this will be one for some hash functions and zero for other hash functions。

 and then we just have to compute expectations。So one way to compute the expected value of a0。

 one random variable is you just say， well， you know。

 there are the cases where the random variable evaluates to zero。

And then there's the cases where the random variable evaluates to one。And of course。

 we can cancel to zero， so this just equals the probability that Zy equals 1。

 and since Zy being 1 is exactly the same thing as x and y colliding。

 that's what gives us the answer。 case it's the probability that x collides with y。

So plugging that into our derivation， now we again have the sum over all of the objects Y in our hash table。

 and instead of the expected value of Zy， let's write that in the more interpretable form。

 the probability that this particular object in the hash table Y collides with the thing we're looking for X。



![](img/05160d386c5b055b3de860b718287b48_9.png)

Now we know something pretty cool about the probability that a given pair of distinct elements like X and Y collide with each other。

 what is it that we know？

![](img/05160d386c5b055b3de860b718287b48_11.png)

Okay， so I hope you answered the second。Response to this quiz。

 this is really in some sense the key point of the analysis。

 this is the role that being a universal family of hash functions plays in this performance guarantee What does it mean to be universal。

 it means for any pair of objects distinct like X and Y in that proof。

 if you make a random choice of a hash function， the probabilitybative collision is as good as with perfectly random hashing。

 namely at most one over n where n is the number of buckets。



![](img/05160d386c5b055b3de860b718287b48_13.png)

So now we can return to the derivation what that quiz reminds you is that the definition of a universal family of hash functions guarantees that this probability for each y is a most one over n for n is the number of buckets in the hash table。

 so let's just rewrite that。So we've upper bounded the expected list length by a sum over the objects in the data set。

Of one over n。And this， of course， is just equal to the number of objects in the data set。

 the cardinality of S divided by n。 And what is this， This is simply the load。

 This is the definition of the load。

![](img/05160d386c5b055b3de860b718287b48_15.png)

Alpha。Which we're assuming is constant， remember that was the third caveat in the theorem。

So that's why as long as you have a hash function which you can compute quickly in constant time。

 and as long as you keep the load under control so the number of buckets is commensurate with the size of the data set that you're storing。

 that's why universal hash functions in a hash table with chaining guarantee expected constant time performance。

