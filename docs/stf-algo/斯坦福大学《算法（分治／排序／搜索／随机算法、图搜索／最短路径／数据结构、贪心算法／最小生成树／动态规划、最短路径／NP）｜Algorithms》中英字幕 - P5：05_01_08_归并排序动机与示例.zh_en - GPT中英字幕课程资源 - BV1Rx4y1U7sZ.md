# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P5：05_01_08_归并排序动机与示例.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Okay， so in this video， we'll get our first sense of what it's actually like to analyze an algorithm and we'll do that by first of all reviewing a famous sorting algorithm。

 namely the merge sort algorithm， and then giving a really fairly mathematically precise upper bound on exactly how many operations the merge sort algorithm requires to correctly sort an input array。

So I feel like I should begin with a bit of an apology here we are in 2012 a very futuristic sounding date and yet I'm beginning with a really quite ancient algorithm so for example。

 merge sort was certainly known to John von Neummann all the way back in 1945 so what justification do I have for beginning a modern class and algorithms with such an old example well there's a bunch of reasons when I have' even put down on the slide which is like a number of the algorithms we'll see mergege sort is an oldie but a goodie so it's over 60 or maybe even 70 years old。

 but it's still used all the time in practice so this really is one of the methods of choice for sorting it's the standard sorting algorithm in a number of programming libraries so that's the first reason but there's a number of others as well that I want to be explicit about So first of all throughout these online courses we'll see a number of general algorithm design paradigms ways of solving problems that cut across different application domains and the first one we're going to focus on is called the divide and conquer algorithm design paradigm So in divide and conquer the idea is you take a problem。



![](img/d8692c32c402c46b065de33292000352_1.png)

You break it down into smaller sub problemsble， which you then solve recursively and then you somehow combine the results of the smaller subproblems to get a solution to the original problem that you actually cared about and merge sort is still to this day。

 perhaps the most transparent application of the divine and conquer paradigm itll just be very clear what the paradigm is what analysis challenges it presents and what kind of benefits you might derive as far as the benefits so for example you're probably all familiar with the sorting problem probably you know some number of sorting algorithms。

 perhaps including merge sort itself and merge sort is better than a lot of the sort of simpler and I would say more obvious sorting algorithms。

 so for example three other sorting algorithms that you might well know about but that I'm not going to discuss here if you don't know them I encourage you to look them up in a textbook or look them up on the web。

 but so three sorting algorithms which are perhaps simpler first of all is selection sort so this is where you do a number of passes through your way repeatedly identifying the minimum of the elements that you haven't looked at yet so you do basically a linear number of passes。



![](img/d8692c32c402c46b065de33292000352_3.png)

![](img/d8692c32c402c46b065de33292000352_4.png)

Each time doing a minimum computation there's an insertion sort which is still useful in certain cases in practice as we'll discuss。

 but again it's generally not as good as merge sort where you repeatedly you just maintain the invariant that the prefix of the array is a sorted version of those elements so after 10 loops of insertion sort you'll have the invariant that whatever the first 10 elements of the array are they're going to be in sorted order and then an insertion sort completes you have an entire sorted array Finally some of you may know about bubble sort this is where you identify adjacent pairs of elements which are out of order and you do repeated swaps until in the end the array is completely sorted again I just say this to jog your memory these are simpler sorts than merge sort but all of them are worse in the sense that they all have performance in general which scales within squared when the input array has n elements so they all have in some sense quadratic running time but if we use this non-trivial divide and conquer approach or non-obvious approach we' get as we'll see a much better running time than this quadratic dependence on the input。

We'll get a win first sorting in Divine and conquer and merge short as the algorithm that realizes that benefit。

So a second reason that I want to start out by talking about the merge sort algorithm is to help you calibrate your preparation I think the discussion we're about to have will give you a good signal for whether your background is at about the right level of the audience that I'm thinking about for this course so in particular when I describe the merge sort algorithm you'll notice that I'm not going to describe it in a level of detail that you could just translate it line by line into a working program in some programming language my assumption again is that you're solid enough programr that you can take the high level idea of the algorithm。

 how it works and you're perfectly capable about of turning that into a working program in whatever language you see fit so hopefully I don it may not be easy the analysis of merge sort or the discussion of merge sort。

 but I hope that you find it at least relatively straightforward because as the course moves on we're going be discussing algorithms and analyses which are a bit more complicated than the one we're about to do with merge sort so in other words I think this will be a good warmup for what's to come。



![](img/d8692c32c402c46b065de33292000352_6.png)

Now， another reason I want to discuss merge sort is that our analysis of it will naturally segue to a discussion of how we analyze algorithms in this course and in general。

 so we're going to expose a couple of assumptions in our analysis。

 we'll focus on worst case behavior we'll look for guarantees on performance。

 on running time that hold for every possible input of a given size。

 and it we'll also expose our focus on so-called asymptotic analysis。

 meaning we'll be much more concerned with the rate of growth of an algorithm's performance than on things like lower returns or on small changes in constant factors。

Finally。We'll do the analysis of merge short using what's called a recursion tree method。

 so this is a way of counting up the total number of operations that are executed by an algorithm。

 and as we'll see a little bit later， this recursion tree method generalizes greatly and it will allow us to analyze lots of different recursive algorithms。

 lots of different divide and conquer algorithms， including the integer multiplication algorithm that we discussed in an earlier segment。

So those are the reasons to start out with merge sort So what is the computational problem that merge sort has meant to solve Well presumably you all know about the sorting problem。

 but let me tell you a little bit about it anyways just so that we're all on the same page so we're given as input。

An array of n numbers in arbitrary order and the goal， of course。

 is to produce output array where the numbers are in shorted order， let's say from smallest to large。

 Okay so for example， we can consider the following input array and then the goal would be to produce the following output array Now one quick comment you'll notice that here in the input array it had eight elements and all of them were distinct。

 It was the different integers between one and8 now the sorting problem really isn't any harder if you have duplicates。

 in fact， it can even be easier but to keep the discussion as simple as possible。

 let's just among friends go ahead and assume that they're distinct for the purpose of this lecture and I'll leave it as an exercise which I encourage you to do which is to think about how the merge short algorithm implementation and analysis would be different if at all if there were Thomas but we'll go ahead and make the distinctness assumption for simplicity from here on out okay so before I write down any pseudocode for merge sort。

 let me just show you how the algorithm works using a picture and I think it'll be pretty clear what the code would be even。

Given a single example， so let's go ahead and consider the same unsorted input array that we had on the previous slide。

So the merge short algorithm is a recursive algorithm and again that means that it's a program which calls itself and it calls itself on smaller subproblems of the same form okay so the merge short is its purpose in life is to sort the given input array so it's going to spawn off calls of itself on smaller arrays and this is going to be a canonical divide and conquerg application where we simply take the input array。

 we split it in half， we solve the left half recursively。

 we solve the right half recursively and then we combine the results so let's look at that in the picture。

So the first recursive call gets the first four elements， the left half of the array， namely 5，4。

1 and8， and of course the other recursive call is going to get the rest of the elements， 7，2。

 six and three。You can imagine these are being copied into new arrays before they' are given to the recursive calls Now by the magic of recursion or by induction。

 if you like， the recursive calls will do their task。

 they will correctly sort each of these arrays of four elements and we'll get back sorted versions of them。

So from our first recursive call， we received the output 1458 and from the second recursive call we received the sorted output 2367。

 so now all that remains to complete merge sort is to take the two result of our recursive calls。

 these two sorted elements of length four and combine them to produce the final output。

 namely the sorted array of all8s of the input numbers。

And this is the step which is called the mergech。And hopefully you already are thinking about how you might actually implement this merge in a computationally efficient way but I do owe you some more details and I will tell you exactly how the merge is done in effect you just walk pointers down each of the two sorted subarrays copying over populating the output array in sorted order。

 but I will give you some more details in just a slide or two so that's merge short in a picture split it in half solve recursively and then have some sick mergesion procedure to combine the two results into a sorted output。



![](img/d8692c32c402c46b065de33292000352_8.png)