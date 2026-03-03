# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P14：14_02_02_计数逆序对的O(n log n)算法 I.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this next series of videos， we'll get some more practice applying the divide and conquer algorithm design paradigm to various problems。

 This will also give us a glimpse of the kinds of application domains to which it's been successfully applied。

 We're going to start by extending the merge short algorithm to solve a problem involving counting the number of inversions of an array。

Before we tackle the specific problem of counting the number of inversions in array。

 let me say a few words about the div and conquer paradigm in general。 So again。

 you've already seen the totally canonical example of D and conquer namely merge sort。

 So the following three conceptual steps will be familiar to the first step no prizes for guessing as you divide the problem into smaller subproblem Sometimes this division happens only in your mind it's really more of a conceptual step than part of your code Sometimes you really do copy over parts of the input into say new arrays to pass on your recursive calls。

 The second step again， no prizes here is you conquer the subproblems just using recursion。

 So for example， in merge short you conceptually divide the array into two different pieces and then you recursively conquer or sort to the first half of the array and you do the same thing with a second half of the array。

 Now， of course， it's not quite as easy as just doing these two steps dividing the problem and then solving the subproblems recursively usually you have some extra cleanup work after the recursive calls and two。



![](img/6609d7b07bbe86486f7bff92611d10b4_1.png)

together the solutions to the subproble into one for the big problem。

 the problem that you actually care about recall， for example in merge sort after our recursive cause。

 the left half of the array was sorted right half of the array was sorted。

 but we still had to stitch those together and merge into a sorted version of the entire array So the third step is to combine the solutions to the subproblem into one of the original problem General the largest amount of ingenuity happens in the third step how do you actually quickly combine solutions to subpros into one to the original problem Sometimes you also get some cleverness in the first step with division Sometimes it's as simple as just lay an array in2 but there are cases where the division step also has some ingenuity Now let's move on to the specific problem of counting inversions and see how to apply this divide and conquer paradigm。



![](img/6609d7b07bbe86486f7bff92611d10b4_3.png)

So let me begin by defininging the problem formally。We're given as input in array A of Link n。

And you could define the problem so that the array A contains any old distinct numbers。

 but let's just keep things simple and assume that it contains the numbers one through n。

 the integers in that range in some order that captures the essence of the problem。

And the goal is to compute the number of inversions of this array。

 So what's an inversion you may ask。 Well， inversion is just a pair of array indices I and J with I smaller than J。

 so that the earlier array entry， the Ih entry is bigger than the later one than the J 1。

 So one thing that should be evident is that if the array contains these numbers in sorted order。

 If the array is simply 1，2，3，4， all the way up to n， then the number of inversions is 0。

 The converse you might also want to think through if the array has any other ordering of the numbers between1 and n。

 other than the sorted one， then it's going to have a nonzero number of inversions。

 Let's look at another example。 So suppose。

![](img/6609d7b07bbe86486f7bff92611d10b4_5.png)

We have an array of6 entries。 So the number 1 through 6 in the following order，1，3，5， followed by 2。

4，6。 So how many inversions does this array have， So again。

 what we need to look for are pairs of array entries so that the earlier or left entry is bigger than the later or right entry。

 So one example we tra right here would be five and2。

 Those are right next to each other and out of order， The earlier entry is bigger than the other one。

 But there's others， There's three and2， for example， Those are out of order。

And5 and 4 are also out of order。 And I'll leave it to you to check that those are the only three pairs that are out of order。

 So summarizing the inversions in this array of length 6 are 3，2。5，2， and 5，4。

Corresponding to the array entries， two， four，3，4， and three，5。Victorialally。

 we can think of it thusly， we can first。Write down the numbers in order one up to 6。

 and then we can write down the numbers again， but ordered in the way that they are given in the input array。

 So 1，3，5，2，4，6。 and then we can connect the dots， meaning we connect one to one。

 we connect two to 2 and so on。 It turns out and I'll leave it for you to think this through that the number of crossing pairs of line segments precisely correspond to the number of inversions。

 So we see that there are one，2，3 crossing line segments。

 and these are exactly in correspond with the three inversions we found earlier，5 and 2，3 and 2。

5 and four。Now， why might you want to solve this problem， you might ask？Well。

 there's a few reasons it comes up， but one would be to have a numerical similarity measure that quantifies how close two different ranked lists are to each other。

So， for example， suppose I took you and a friend， and I identified 10 movies that both of you had seen。

 and I asked each of you to order to rank these movies from your most favorite to your least favorite。

 Now， I can form an array and compute inversions and it quantifies in some sense。

 how dissimilar two rankings are to each other。 So in more detail， in the first entry of this array。

 I would put down the ranking that your friend gave to your favorite movie。

 So if you had your favorite movie， Star Wars or whatever。

 and your friend only thought it was the fifth best out of the 10。

 that I would write down a5 in the first entry of this array。 Similarlyly。

 I would take your second favorite movie。 I would look at how your friend ranked that。

 I would put that in the second entry of the array and so on all the way up to the 10th entry of the array where I would put your friend's ranking of your least favorite movie。

Now， if you have exactly identical preferences， if you rank them exactly the same way。

 the number of inversions of this array would be zero， and in general。

 the more inversions this array has， it quantifies that your lists look more and more different from each other。

Now， why might you want to do this。 Why might you want to know whether two different people ranked things in a similar way had similar preferences。

 Well， one reason would be in what's called collaborative filtering。

 So probably many of you have had the experience of going to a website and if you've made a few purchases from this website it starts recommending further purchases for you。

 So one way to solve that problem under the hood is to look at your purchases。

 look at what you seem to like， find other people who have similar preferences， a similar history。

 look at things that they've bought that you haven't and then recommend new products do you based on what similar customers seem to have bought。

 So this problem captures some of the essence of identifying which customers or which people are similar based on data about what they prefer。

 So just to make sure we're all on the same page， let me pause for a brief quiz。

 We've already noticed that a given array will have zero inversions if and only if it's in sorted order it only contains the numbers one through N in order。

 So on the other side， what is the largest number of inversions and array could possibly have。

 let's say just for an array of size 6 like。

![](img/6609d7b07bbe86486f7bff92611d10b4_7.png)

One in this example here。So the answer to this question is the first one， 15， or in general。

 in an n element array， the largest number of inversions is and choose 2。

Also known as n times n minus1 over2。W again， in the case of a6 element array is going to evaluate to 15。

 The reason is the worst case is when the array is in backwards order。

 reverse sorted order and in every single pair of array indices is inverted。

 And so the number of indices I J with Ios and J is precisely and choose 2。

 Let's now turn our attention to the problem of computing the number of inversions of an array as quickly as possible。

 So one option which is certainly available to us， is the brute force algorithm。

And by force I just mean we could set up a double4 loop， one which goes through I。

 one which goes through J bigger than I， and we just check each pair IJ individually with I less than J。

 whether that particular pair of array entries AI and AJ is inverted and if it is。

 then we add it to a run count and then we return the final count at the end of the double4 loop that's certainly correct。

 the only problem is as we just observed there's n choose 2 or a quadratic number of potential inversions so this algorithm is always going to run in time quadratic in the array length。

Now remember the mantra of any good algorithm designer， can we do better？And the answer is yes。

 and the method will be using divideide and conquer。

The way in which we divide will be motivated directly by merge sort where we recur separately on the left and the right half of the array。

 we're going to do the same thing here to understand how much progress we can make purely using recursion。

 let's classify the inversions of array into one of three types。

So suppose we have an inversion of an array， I comma J and remember， in an inversion。

 you always have I less than J。We're going to call it a left inversion。

If both of the array indices are at most and over2， where n is the array length。

We're going to call it a right inversion if they're both strictly greater than n over 2。

 and we're going to call it a split inversion if the smaller index is are most n over 2 and the larger index is bigger than n over 2。

We can discuss the progress made by recursion in these terms when we recursse on the left half of an array。

 if we implement our algorithm correctly， we'll successfully be able to count all of the inversions located purely in that first half those are precisely the left inversions。

 similarly a second recursive call on just the right half of an array。

 the second half of an array will successfully count all of the right inversions。

 It remains the question of how to count the split inversions。

 but we shouldn't be surprised there some residual work left over。

 even after the recursive calls do their job。 That of course was the case in merge short recursion magically took care of sorting the left half of the array sorting the right half of the array。

 but there was still after their return the matter of merging those two sorted lists into one and here again。

 after the recursion is going to be the matter of cleaning up and counting the number of split inversions。



![](img/6609d7b07bbe86486f7bff92611d10b4_9.png)

So for example， if you go back to the six element array we worked through before， 13，5，246。

 you'll notice that there in fact all of the inversions are split。

 so the rehearsal calls will both come back counting zero inversions and all of the work for that example will be done by the count split inversions subroutine。

So let's summarize where things stand and give an underspecified high level description of the algorithm as we envision it。

There is a base case， I'll go ahead and write it down for completeness。

 which is if we're given one element array， then there's certainly no inversion so we' can just immediately return the answer zero。

For any bigger array， we're going to divide and conquer。

 so we'll count the left inversions with a recursive call。

 the right inversions with a recursive call， and then we'll have some currently unimplemented subroutine that counts to split inversions Since every inversion is either left or right or split and can't be any more than one of those three。

 then having done these three things， we can simply return their sum。

So that's our high level attack on how we're going to count up the number of inversions and of course we need to specify how we're going to count the number of split inversions and moreover we like that subroutine to run quickly。

 an analogy to merge short where outside the recursive calls we did merely linear work in the merge subroutine here we'd like to do only linear work and counting up the number of split inversions。

If we succeed in this goal， if we produce a correct and linear time implementation to count up the number of split in versions。

 then this entire recursive algorithm will run in BigO of N log Nton。

The reason the overall algorithm will run in O of N log N time is exactly the same reason that merge sort ran in N log N time there's two recursive cause each on a problem of half the size and outside of the recursive cause we would be doing linear work so you can copy down exactly the same recursion tree argument we used for merge sort it would apply equally well here alternatively very soon we will cover the master method and as one very special case it will prove that this algorithm if we can implement it thusly will run in O of N log N time。



![](img/6609d7b07bbe86486f7bff92611d10b4_11.png)

Now， one thing to realize is this is a fairly ambitious goal to count up the number of split inversions in the linear time。

 It's not that there can't be too many split inversions。 there can actually be a lot of them。

 if you have an array where the first half of the array contains the numbers n over  two plus one up to n whereas the second part of the array contains the numbers of one up to n over two。

 that has a quadratic number of inversions all of which are split。

 So what we're attempting to do here is count up a quadratic number of things using only linear time can it really be done。

 Yes again， as we'll see in the next video。