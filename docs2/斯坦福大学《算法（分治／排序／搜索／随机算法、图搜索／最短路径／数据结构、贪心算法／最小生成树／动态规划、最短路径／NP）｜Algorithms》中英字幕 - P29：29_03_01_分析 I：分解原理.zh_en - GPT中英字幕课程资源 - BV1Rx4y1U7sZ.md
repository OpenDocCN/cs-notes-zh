# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P29：29_03_01_分析 I：分解原理.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

SoThis is the first video of three in which we'll mathematically analyze the running time of the randomized implementation of Quicksort So in particular we're gonna to prove that the average running time of Quick sort is big O of n login Now this is the first randomized algorithm that we've seen in the course and therefore in its analysis will be the first time that we're gonna to need any kind of probability theory So let me just explain upfront what I'm expect you to know in the following analysis Basically I need you to know the first few ingredients of discrete probability theory so I need you to know about sample spaces that is how to model all of the different things that could happen。

 all of the ways that random choices could resolve themselves I need you to know about random variables functions on sample spaces which take on real values I need you to know about expectations that is average values of random variables and very simple with very key property we're going to need in the analysis of quick sort is linearity of expectation So if you haven't seen this before or if you're too rusty definitely you should review this stuff before you watch this video some places you can go to get that necessary review。

You can look at the probability review part1 video that's up on the course's website if you prefer to read something like I said at the beginning of the course I recommend the free online lecture notes by Eric Lehman and Tom Laton mathematics for computer science that covers everything we'll need to know plus much much more there's also a wikibook on discrete probability which is a perfectly fine obviously free source when you can learn the necessary material so after you've got that sort of fresh in your mind and you're ready to watch the rest of this video and in particular we're ready to prove the following theorem stated in the previous video so the quickword algorithm with a randomized implementation that is where in every single recursive subcall you pick a pivot uniformly at random we stated the following assertion that for every single input so for a worstcase input array of length N。

 the average running time of Quick sort with the random pivots is O of n login and again to be clear where the randomness is the randomness is not in the data we make no assumptions about the data as per gu principles no matter what。

The input array is averaging only over the randomness in our own code。

 the randomness internal to the algorithm， we get a running time of n log n。

 we saw in the past that the best case behavior of quickword is n log n。

 its worst case behavior is n squared So the theist is asserting that no matter what the input array is the typical behavior of quick sort is far closer to the best case behavior than it is to the worst case behavior So that's what we're going to prove in the next few videos。

 So let's go ahead and get started。So first I'm going to set up the necessary notation and be clear about exactly what is the sample space。

 what is the random variable that we care about， and so on。

So we're going to fix an arbitrary array of LinkedIn that's going to be the input to the Quickword algorithm。

And we'll be working with this fixed but arbitrary input array for the remainder of the analysis。

 case will just fix a single input in your mind。 Now， what's the relevant sample space。

Well recallll what a sample space is it's just all the possible outcomes of the randomness in the world so it's all the distinct things that could happen now here the randomness is of our own devising。

 it's just the random pivot sequences， the random pivots chosen by Quicks。

 so mega is just a set of all possible random pivots that QuickSo could choose。

Now the whole point of this theem proving that the average running time of Quicksort is small boils down to computing the expectation of a single random variable。

 so here's the random variable we're going to care about。For a given pivot sequence。

 remember that random variables are real valued functions defined on the sample space。

 so for a given point in the sample space or pivot sequence Sigma。

 we're going to define capital C of sigma， as the number of comparisons that Quick sort makes whereby comparison。

 I don't mean something like with an array index and a for loop that's not what I mean by a comparison。

 I mean， a comparison between two different entries of the input array。

 like comparing the third entry in the array against the seventh entry in the array to see whether the third entry or the seventh entry is smaller。

Notice that this is indeed a random variable that is given knowledge of the pivot sequence sigma。

 the choices of all pivots， you can think a quick sort at that point is just a deterministic algorithm with all of the pivot choices predetermined and so a deterministic version of quick sort makes some deterministic number of comparisons so for a given pivot sequence sigma we're just calling C of Sigma to be whatever however many comparisons it makes。

 given those choices of pivots。Now the theorem I stated is not about the number of comparisons of QuickSot。

 rather about the running time of Quicksort， but really if you think about it。

 kind of the only real work that the QuickSot algorithm does is make comparisons between two between pairs of elements in the input array Yes。

 there's a little bit about the bookkeeping， but that's all noise， that's all second order stuff。

 all QuickSot really does is comparisons between the pairs of elements in the input array。



![](img/abf2262cb4af6437fbed09b494e00e06_1.png)

And if you want to know what I mean by that a little more formally， dominated by comparisons。

 I mean that there exists a constant C。So that the total number of operations of any type that QuickSo executes is at most a constant factor larger than the number of comparisons。

So let's say that by Rt， I mean， the number of primitive operations of any form the QuickSot uses and for every。

Pivt sequence Sigma， the total number of operations is no more than a constant times。

 the total number of comparisons。And if you want to prove of this， it's not that interesting。

 so I'm not going to talk about it here， but in the notes posted on the website。

 there is a sketch of why this is true， how you can formally argue that there isn't much work beyond just the comparisons but I hope most of you find that to be pretty intuitive So given this。

 given the running time of Quick sortt boils down just to the number of comparisons we want to prove the average running time is n log n all we got to do quote unquote all we have to do is prove that the average number of comparisons the Quicksortt makes is of N log n and that's what we're going to do so that's what the rest of these lectures are about。

So that's what we got to prove， we got to prove that the expectation of this random variable C。

 which counts up the number of comparisons quick sort it makes is for this arbitrary input array A of length n bounded by BigO of n log n。

So the higher order bit of this lecture is a decomposition principle。

 we've identified this random variable C， the number of comparisons。

 and it's exactly what we care about it governs the average running time of quick sort。

 The problem is it's quite complicated， it's very hard to understand what this capital C is。

 it's fluctuating between N log N and then squared and it's hard to know how to get a handle on it。

So how are going to go about proving this assertion that the expected number of comparisons that QuickSo makes is on average。

 just O of N log n？At this point， we've actually have a fair amount of experience with divide and conquer algorithms。

 We've seen a number of examples。 and whenever we had to do a run incomee analysis of such an algorithm。

 we wrote out our recurrence， we applied the master method or in the worst case we wrote out a recursion tree to figure out the solution to that recurrence。

 So you'd be very right to expect something similar to happen here。

 but as we probe deeper and we think about quick sort。

 we quickly realize that the master method just doesn't apply or at least not in the form that we're used to the problem is twofold。

 So first of all， the size of the two subproblems is random， as we discussed in the last video。

 the quality of the pivot is what determines how balanced to split we get into the two subproblems。

 It could be as bad as a subproble of size0 and one of size n minus1。

 or it could be as good as a perfectly balanced split into two subproble of equal sizes。

 but we don't know it's going to depend on our random choice of the pivot。Moreover。

 the master method， at least as we discussed it， required solve subpro to have the same size。

 and unless you're extremely lucky， that's not going to happen in the QuickSo algorithm。

It is possible to develop a theory of recurrence relations for randomized algorithms and to apply that to Quicks in particular。

 but I'm not going to go that route for two reasons the first one is it' really quite messy。

 it gets pretty technical to talk about solutions to recurrences for randomized algorithms or to think about random recursion trees both of those get pretty complicated The second reason is I really want to introduce you to what I call a decomposition principle by which you take a random variable that's complicated but that you care about a lot you decompose it into simple random variables which you don't really care about in their own right but which are easy to analyze and then you stitch those two things together using linearity of expectation so that's going to be the workhor for our analysis of of the quickword algorithm and it's going to come up again a couple times in the rest of the course。

 for example， when we study hashing。So to explain how this decomposition principle applies to Quickword in particular。

 I'm going to need to introduce you to the building blocks。

 simple random variables which will make up the complicated random variable that we care about the number of comparisons。

 so here's some notation。Recall that we've fixed in the background an arbitrary array of length n。

 and that's denoted by capital A。And some notation， which is simple。

 but also quite important by Z sub I， what I mean is the Ith smallest element in the input array capital A。

 also known as the Ith order statistic。So let me tell you what Z is not。 Okay。

 what Z is not in general is the element in the I position of the input unsorted array。

 What Z is is it's the element which is going to wind up in the Ih element of the array once we sort it Okay so if you fast forward to the end of a sorting algorithm and position I you're going to find Z。

 So let me give you an example。 So suppose we had just a simple array here unsorted。

With the numbers 6，8， 10 and 2。Then。Z1， well， that's the first smallest。

 the one smallest or just the minimum。 So Z1 would be the two。Z2 would be the six。Z3 would be the8。

 and Z4 would be the 10。For this particular input or rep， okay， so Z is just the I smallest number。

 wherever it may lie in the original unsorted array， that's what ZI refers to。

So we already defined the sample space that's just all possible choices of pivots the Quick sort might make。

 I already described one random variable， the number of comparisons the Quick sort makes on a particular choice of pivots now I'm going to introduce a family of much simpler random variables which count nearly the comparisons involving a given pair of elements in the input array。

 not all elements just a given pair。So for're a given choice of pivots， a given sigma。

And for given choices of I and J。Both of which are between1 and n。

 And so we only count things once I'm going to insist that I is less than J always。

 And now here's a definition by X I J。And this is a random variable。

 so it's a function of the pivots chosen。 This is going to be the number of times。

That ZI and ZJ are compared in the execution of Quick sort。Okay。

 so this is going to be an important definition in our analysis。 It's important you understand it。

So for something like the third smallest element and the seventh smallest element， Xj is asking。

 that's when I equals 3 and J equals 7， x37 is asking how many times those two elements get compared as quick sort proceeds and this is a random variable in the sense that if the pivot choices are all predetermined if we think of those being chosen in advance。

 then there's just some fixed deterministic number of times that Z and Zj get compared so it's important you understand these random variables XIj so the next quiz is going to ask a basic question about the range of values that a given XIj can take on。



![](img/abf2262cb4af6437fbed09b494e00e06_3.png)

So for this quiz， we're considering as usual some fixed input array and now， furthermore。

 fixed two specific elements of the input array， for example。

 the third smallest element wherever it may lie and the seventh smallest element wherever it may lie。

 Think about just these pair of two elements。What is the range of values that the corresponding random variable XIj can take on。

 that is what are the different numbers of times that a given pair elements might conceivably get compared in the execution of the QuickSo algorithm？

All right， so the correct answer to this quiz is the second option。This is not a trivial quiz。

 This is a little tricky to see。 So the assertion is that a given pair of elements they might not be compared at all。

 they might be compared once， and they're not going to get compared more than once so here what I'm going to discuss is why it's not possible for a given pair of elements to be compared twice during the execution of quick sort it'll be clear later on if it's not already clear now that both zero and one are legitimate possibilities a pair of elements might never get compared and they might get compared once and again we'll go in more detail on that in the next video So but why is it possible to be compared twice Well think about two elements。

 say the third element and the seventh element and let's recall how the partition subroutine works。

 observeer that in quick sort， the only place in the code where comparisons between pairs of input array elements happens it only happens in the partition subroutine So that's where we have to drill down So what are the comparisons that get made in the partition subroutine Well。

 go back and look at that code。The pivot element is compared to each other element in the input array exactly once。

 Okay， so the pivot just hangs out in the first entry of the array。 We have this four loop。

 this index J， which marches over the rest of the array， and for each value of J。

 the J element of the input array gets compared to the pivot。

So summarizing in an invocation of partition。Every single comparison involves the pivot elements。

 Okay， so two elements get compared if and only if one is the pivot。All right。

 so let's go back to the question， why can't a given pair of element and the input array get compared two or more times Well。

 think about the first time they ever get compared in Quicksort。

It must be the case that at that moment we're in a recursive call where either one of those two is the pivot element。

 so if it's the third smallest element or the seventh smallest element。

 the first time those two elements get compared to each other。

 either the third smallest or the seventh smallest is currently the pivot because all comparisons involve a pivot element。

Therefore， what's going to happen in the recursion。

 Well the pivot is excluded from both recursive calls。 So， for example。

 if the seventh smallest element is currently the pivot。

 that's not going to be passed on the recursive call， which contains the third smallest element。

 Therefore， if you're compared once， one of the elements is the pivot and they'll never be compared again because the pivot will not even show up in any future recursive calls。



![](img/abf2262cb4af6437fbed09b494e00e06_5.png)

So let me just remind you of some terminology。 So a random variable。

 which can only take on the value 0 or1， is often called an indicator random variable because it's just indicating whether or not a certain thing happens。

 So in that terminology， each X I J。Is indicating whether or not the Is smallest element in the array and the J smallest element in the array ever get compared。

 It can't happen more than once。 It may or may not happen。

 And X I J is one precisely when it happens。 So that's the event that it's indicating。

Having defined the building blocks I need these indicator random variables， these Xjs。

 now I can introduce you to the decomposition principle as applied to Quicksort。

 So there's a random variable that we really care about， which is denoted capital C。

 the number of comparisons the Quick sort makes。 That's really hard to get a handle on in and of itself。

 but we can express C as a sum of indicator random variables of these Xjs and those we don't care about in their own right。

 they're going to be much easier to understand。So let me just rewrite the definitions of C and the XI Js。

 so we're all clear on them。So C recall counts all of the comparisons between pairs of input elements that quicks or whatever makes。

 whereas an XIJ only counts the number and it's going to be zero or1 comparisons that involve the I smallest and the Js smallest elements in particular。

Now， since every comparison involves precisely one pair of elements。

 some I and some J with I less than J， we can write C as the sum of the X Js。

So don't get intimidated by this fancy double sum。 All this is doing is it's iterating over all of the ordered pairs。

 So all of the pairs Ij where I and J are both between1 and n and where I is strictly less than n。

 this double sum is just a convenient way to do that iteration and of course no matter what the pivots chosen are we have this equality the comparisons are somehow split up amongst the various pairs of elements。

 the various I's and js Why is it useful to express a complicated random variable as a sum of simple random variables Well because an equation like this is now right in the wheelhouse of linearity of expectation So let's just go ahead and apply that remember and this is super super important linear of expectation says that the expectation of a sum equals the sum of the expectation and moreover this is true whether or not the random variables are independent and I'm not going to prove it here you might want to think about the fact that the Xjs are not in fact independent So we're using the fact that linear of expectation works even for non-inent。

Randdom variables。Again， why is this interesting， Well the left hand side。This is complicated。Right。

 this is the this is some crazy number of comparisons by some algorithm on some arbitrarily long array。

 and it fluctuates between two pretty far apart numbers and log n and n squared。 On the other hand。

 this does not seem as intimidating。 a given X I J。 It's just0 or1。

 whether or not these two guys get compared or not。



![](img/abf2262cb4af6437fbed09b494e00e06_7.png)

So that is the power of this decomposition approach。 Okay。

 so it reduces understanding a complicated random variable to understanding simple random variables。

 In fact， because these are indicator random variables。

 we can even clean up this expression some more。So for any given XIj being a 01 random variable。

 if we expand the definition of expectation just as an average over the various values， what is it。

 it's just well there's some probability it takes on the value zero， that's possible。

And there's some possibility it takes on the value one。And of course， this zero part。

 we can very satisfyingly delete cancel。And so。The expected value of a given X I J is just。

The probability that X I J equals1。And remember， it's an indicator random variable。

 it's one precisely when the heights smallest and the Js smallest elements get compared。

So putting it all together。We find that what we care about。

 the average value of the number of comparisons made by Quicksort on this input array。

Is this double sum， which iterates over all ordered pairs。

Where each sumand is the probability that the corresponding X I J equals 1。

 that is the probability that Z I。And ZJ get compared。

And this is essentially the stopping point for this video for the first part of the analysis。

 So let's call this star。And put a nice circle around it。

So what's going to happen next is that in the second video for the analysis。

 we're going to drill down on this probability， probability that a given pair of elements gets compared and we're going to nail it。

 we're going to get an exact expression as a function of I andJ for exactly what this probability is then in the third video we're going to take that exact expression。

 plug it into the sum and then evaluate this sum and it turns out the sum will evaluate to big of and log n。

So that's the plan， that's how you apply decomposition in terms of 01 or indicator random variables of pi linearity of expectation in the next video we'll understand these simple random variables and then we'll wrap up in the third video。

Before we move on to the next part of the analysis。

 I do just want to emphasize that this decomposition principle is relevant not only for Quicksort。

 but it's relevant for the analysis of lots of randomized algorithms。

 and we will see more applications， at least one more application later in the course。

 so just to kind of really hammer the point home， let me spell out the key steps for the general decomposition principle。

So first you need to figure out what is it you care about so in quick sort we cared about the number of comparisons。

 we had this lemma that said the running time is dominated by comparisons。

 so we understood what we wanted to know the average value for the number of comparisons。

The second step is to express this random variable Y as a sum of simpler random variables。

 ideally indicator or 01 random variables。Now you're in the wheelhouse of linearity of expectation。

 you just apply it。And you find that what it is you care about， the average value。

Of random the random variable y。Is just the sum。The probabilities of various events。

That given X L random variable is equal to one。And so the upshot is to understand the seemingly very complicated left hand side。

 all you have to do is understand something which in many cases is much simpler。

 which is understand the probability of these various events。In the next video。

 I'll show you exactly how that's done in the case of Quicksort where we care about the XIJs。

 the probability the two elements gets compared， so let's move on and get an exact expression for that probability。



![](img/abf2262cb4af6437fbed09b494e00e06_9.png)