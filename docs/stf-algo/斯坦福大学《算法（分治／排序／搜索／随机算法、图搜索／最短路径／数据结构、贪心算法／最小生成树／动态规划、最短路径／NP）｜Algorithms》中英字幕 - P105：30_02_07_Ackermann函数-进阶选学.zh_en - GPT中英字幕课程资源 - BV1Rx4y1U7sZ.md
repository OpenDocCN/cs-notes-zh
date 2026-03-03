# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P105：30_02_07_Ackermann函数-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/ebdc7efb10db19c69c8b57f7470b6884_0.png)

Hckgrave Olman guarantees states that if you implement a union fine data structure using lazy unions union by rank and path compression。

 then you get a pretty amazing guarantee to any sequence you want of Emmet union and fine operations。

 the total amount of work done by this data structure is bounded above by big O of M times log star of n。

 where n is the number of objects in the data structure。So on the one hand。

 I hope you're suitably impressed by this result。 So the proof of it that we gave in the last video is。

 frankly， totally brilliant。 And secondly， the guarantee itself is excellent。

 What with log star of n being bounded above by5 for any imaginable value of n。On the other hand。

 I do hope there's sort of a little voice inside you wondering if this log star bound could really be optimal。

 can we do better， maybe by a sharper analysis of the data structure we've been discussing or perhaps by adding further ingenuity。

 further optimizations to the data structure for all we know。

 you might be able to get away with a linear amount of work。

 so O of M work to process an arbitrary sequence of fines and unions。

It turns out you can do better than the Hocro omen guarantee。

 there is a sharper analysis of the exact same data structure that analysis was given by Tarjn and here is the statement of his guarantee。

So the improved bound states that for an arbitrary sequence of M union and find operations。

 the total work done by this data structure union by rank and path compression is big O of M times alpha of n。

 Now， what you may ask is alpha of n。 that's a function known as the inverse ackerman function。

So what then is the inverse ackerman function。 Well。

 the short answer is that it's a function that incredibly grows still more slowly。 In fact， much。

 much， much more slowly than the log star function we discussed in the hotcroft almond bound。

 The precise definition is nontrial。 And that is the subject of this video。

 In the next video will prove this theorem and explain how the inverse ackerman function arises in an optimal analysis of union by rank with path compression。

😊，So I'll first define the ackerman function and then I'll describe as inverse。

 One thing I should warn you is you will see slight variations on these two definitions out there in the literature。

 different authors define them in ways convenient for their own purposes。

 That's also what I'm going to do here I'm going to take one particular definition convenient for the Union find data structure analysis。

All of the variants that you'll see out there in the literature exhibit roughly the same ridiculous growth。

 so the details aren't really important for the asymptotic analysis of data structures and algorithms。

So you can think of the Acroman function as having two arguments。

 which I'm going to denote by K and R， both of these are integers， K should be at least zero。

 r should be at least one。The ackerman function is defined recursively。

 the base case is when k equals 0 for all r， we define a sub0 of r as the successor function。

 that is it takes as input R and it outputs r plus 1。In general， when K is strictly positive。

 the argument R tells you how many times to apply the operator， the function， ak minus1。

 starting from the input R。That is， it's the r fold composition of a sub k minus1 and again applied to the argument R。

So in some sense， describing the acroman function isn't that hard right。

 I didn't really need know that much of a slide to actually write down its description。

 but getting a feel for what on earth this function is takes some work。

 So the first thing maybe just as a sanity check is note that it is a welldefined function。

 So you know you're all programmers。 So you could easily imagine writing a program which took as input K and R and at least in principle。

 given enough time computed this number， it would be a very simple recursive algorithm with a pseudocode just following the mathematical definition。

 So it is some function， given K and R， there is some number that's the result of this definition。

 Now， in the next sequence of quizzes， let's get a feel for exactly how this function behaves。

And so let's start on the first quiz just by fixing k to be 1 and now viewing the acromen function with K fixed at  one is a function purely of R。

 So what function does a1 of R correspond to。All right， so the correct answer is B。

 at least a1 is quite simple to understand All it does is double the argument。

 so if you give it R it's going to spit out to R。So why is that well a one of our by definition is just the function a0 applied to R R times a0 by definition is the successor function it adds1。

 so if you apply the successor function R times starting from R， you get to R as a result。

So let's now move from A1 to A2， so let's think about exactly the same question。

 fixing k at2 and regarding it as a function of R only what function is it？

So the answer here is C for every positive integer， R， A2 of R is equal to r times 2 to the r。

And the reasoning is the same as before， so remember A2 of R just means you apply A1 R times and the last quiz we discovered that A1 was doubling。

 so if you double r times that' has the effect of multiplying by a 2 to the R factor。

So let's take it up a notch yet again， let's bump up k to3 and let's think about as sub 3。

 but let's not yet think about exactly what as sub3 is as a function of R let's keep things simple What is just a sub3 evaluated when r equals 2 so K equals 3 r equals 2 that's a number what number is it。

Okay， so the correct answer is the third one， it's 2048， also known as2 to the 11th。Let's see why。

 well a sub3 of2， that just means we apply a sub2 twice to two。

Now in the last quiz we evaluated not only AC sub 2 of 2， but a sub 2 of all integers R。

 we discovered it was r times 2 to the R。So that means it's a simple matter to evaluate this application of a sub 2 twice first a sub 2 of two。

 that's just two times two to the two， also known as eight。

And then a of2 of8 is going to be8 times 2 to the8， also known as 2 to the 11 or 2048。

So what about in general， how does the function a sub 3 behave as a function of a general parameter R But when we answer this question。

 we're going to see for the first time the ridiculously explosive growth that the acromen function exhibits。

 and this will just be the tip of the iceberg， right， This is just when K equals 3。So by definition。

 a sub 3 of R， you start from R and you apply the function a sub 2 R times。

 So let's remind ourselves what the function a sub 2 is。 We computed that exactly。

 That's r times2 to the R。 So to make our life simple， let's just think about the2 to the R part。

 So in the real function a sub 2， you also multiply by R。

 But let's just think about the2 to the R part。 So imagine you apply that function over and over and over again。

 What would you get， Well now you get a tower of twos where the height of the tower is the number of times that you apply that function。

 if you apply at once， you get2 to the R。 if you apply it twice。

 you're going to get 2 raised to the2 to the R three times 2 to the2 to the2 to the R and so on。

 So R applications of a sub 2 gives you something that's even bigger than a tower of R2s。

So let's move on to a4 and this is the point at which personally my brain begins to hurt。

 but let's just push it a little bit further so that we appreciate the ridiculous growth of the ackermen function。

And as with A3， let's punt for the moment on understanding the dependence for a general R。

 let's just figure out what a sub4 of 2 is， so k equals 4， r equals 2。Well， so this by definition。

 you just take two and you apply a sub 3 twice。We computed As sub3 of2 in the previous quiz。

 we discovered that was 2048， so that's the result of the first application of A3。

Now we find ourselves applying A3 to 2048， so in effect R now is 2048 and remember we concluded the last slide by saying。

 well AI3， whatever it is， it's at least as big as a tower of R2s， and here R is 2048。

So this of course， has now the land of truly ridiculous numbers that we're dealing with。

 I encourage you to take a calculator or a computer and see how big a tower of twos you can even compute and it's not going to be anywhere close to 2000 I can promise you that。

And hey， that's just a4 of 2。 What about the function A4 for a general value of R？Well， of course。

 in general， a4 of R is going to be R applications of A3 starting at R。Now in the last slide。

 we argued that A sub3， this function is bounded below by a tower function。

 so A sub3 takes in some input， some integer and it spits out some tower with height equal to that integer。

 So what happens when you apply that tower function A3 over and over again now you get what's called an iterated tower function。

So when you apply the function a sub 3 for the first time to R。

 it's going to spit out a number which is bounded below by a tower of height R， a tower of2s。

 R of them now when you apply a sub3 a second time。

 its output is going to be a tower of2s whose height is lower bounded by a tower of2s of height R and so on every time you apply a sub3。

 you're just going to iterate this tower function。You will sometimes see the iterated tower function referred to as a wower function。

 You probably think I'm pulling your leg， but I'm not kidding。 You can look it up。

So that is the ackermen function and a bunch of examples to appreciate just how ridiculously quickly it is growing so now let's move on to define its inverse now the ackermen function as two parameters K and N K and R excuse me。

 so to define an inverse I'm going to fix one of them specifically I'm going to fix R equal to2。

So the inverse acromen function is going to be denoted by alpha， for simplicity。

 I'll define it only for values of n that are at least four。

 and it's defined for a given value of n as the smallest k so that if you apply a sub K to2 to r equals 2。

 then the results is at least n。So again， it's simple enough to kind of write down a definition like this。

 but you really have to plug in some concrete numbers to get a feel for what's going on。

 So let's just write out， you know what are the values of n that will give you alpha of n equal 1 thatll give you alpha n equal 2。

 alpha n equal3 and so on。Okay， so for starters， alpha of4 is going to be equal to1 right so if you applied a0 to2。

 that's the successor function so you only get three so that's not at least as big as4。

 on the other hand， if you apply a sub1 to2， that's the doubling function。

 So if you apply it to two you get four。 So a sub1 does give you a number which is at least as big as n when n is 4。

So next， I claim that the values of n for which alpha of n equals 2 are the values 5，6，7 and8。

 Why is that true Well， if you start from 2 and you apply the function a sub 1。

 the doubling function， you only get4。 So a sub1 is not sufficient to achieve these values of ns。

 On the other hand， if you apply a sub 2 to 2。 remember that's the function which given an R outputs r times 2 to the R。

 So when you apply it to 2， you get  two times 2 to the two also known as8。

 So a sub 2 is sufficient to map 2 to a number at least as big as8。By the same reasoning。

 we recall that we computed a sub3 of 2 and we computed that to be 2048。

 so therefore for all of the bigger values of ns starting at9 and going all the way up to 2048。

 their alpha value is going to be equal to3 because that is the smallest value of k such that a sub K of 2 is at least those values of n。



![](img/ebdc7efb10db19c69c8b57f7470b6884_2.png)

And then things start getting a little bit ridiculous。 So remember。

 we also lower bounded a sub 4 of2。 We said that's at least a tower of twos of height 2048。

 So for any n up to that value， up to a tower of twos of height 2048。

 alpha of those ends is going to be equal to 4。This。

 of course implies that the inverse ackerman function value of any imaginable number is at most for。

 and I don't know about you， but my brain is already hurting too much to think about which of the values of n such that alpha is equal to 5。

So as a point of contrast， let's do the same experiment for the log star function so that we get some appreciation about how as glacially growing as log star may be。

 the inverse ackerman function is growing still qualitatively slower。

So the log star function remembers the iterated logarithm。

 So it's starting from n how many times you need to hit log in your calculator。

 let's say base 2 before the result drops below1。So when is log star of n going to be equal to1。

 well， that's when n is going to be equal to 2， then you hit log once and you draw from2 to1 and you're done。

If n equals 3 or four， then you need more than one application of logarithm to drop below one。

 but you only need two applications， so log star of n is going to be2 for n equals 3 and 4。

Similarly for n anywhere between5 and 16， log star n is going to be equal to  three right if you start from 16。

 that's two to the four， so if you apply log1 so you get four a second time you get two a third time you get one。

By analogy， the values of n for which log star n equals 4 are going to be starting at 17 and going up to 2 to the 16。

 also known as 65，536。So let's just go one more step for which n is log star of n equal to 5。

 well obviously we start at 65，537 and we end at two raised to the largest number of the previous block。

 a two raised to the 65，536。So these numbers are impressive enough on the right hand side。

 there is no imaginable number of importance for which log star is going to be bigger than five。

Looking at the left and the right hand sides， though。

 we see that there really is a qualitative difference between the rate of growth of these two functions。

 with the inverse acromen function in fact growing much， much slower than the log star function。

So perhaps the easiest way to see that is to look at the right hand side and on each of the lines on the right hand side。

 look at the largest value of n so that log star is a given number。 So for example。

 in the third line， the largest n such that log star n equals 3 is a tower of twos of height 3。

2 to the two to the2， also known as 16， Similarlyly on the fourth and fifth lines。

 the largest n that give values of log star equal to 4 and 5 are a tower of twos of height 4 and a tower of twos of height 5。

On the other hand， look at the fourth line on the left hand side。 So already。

 when we ask about the largest values of n that have inverse ackermen value 4。

 we're talking about towers of twos， in fact， of height 2048。 So that is the ns。

 which give us alpha n equal to 4。 we would have to write down 2048 lines on the right hand side。

 before we had values of n that were equally big。This indicates how the log star function while growing glacly indeed。

 is nevertheless moving at light speed compared to the inverse acrament function。

