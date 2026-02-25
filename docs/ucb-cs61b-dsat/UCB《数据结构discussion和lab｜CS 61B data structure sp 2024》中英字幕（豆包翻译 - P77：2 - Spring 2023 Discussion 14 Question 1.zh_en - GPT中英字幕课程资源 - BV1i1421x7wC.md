# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P77：2 - Spring 2023 Discussion 14 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼哈必哈必。😊，🎼不别。

![](img/e6a7e7faae6be2396dc14b6e568bdc68_1.png)

Allright， let's jump right into question one quicks we're asked to show the steps of running Quicks on the list below selecting the first item as the pivot and using threeway partitioning so in this one we're using the not inplace partitioning scheme but I personally think this is a little bit easier for us to visualize remember for three way partitioning what we do is we pick our pivot and then we make three scans of our list right so in the three scans of our list we want to put find elements that are less than the pivot and then we've un finded elements that are equal to the pivot and then elements that are greater than the pivot so what that's going to look like is first of all our pivot is going to be 18 right and so when we make our initial scan of our list let's support elements that are less than the pivot okay。

So when we do that we're going to see that 7，11 and four are less than our pivot so let's pop those into the front of our array okay next let's look for numbers that are equal to the pivot so we scan the pivot so it's going to be 18 and we see another 18 so let's pop 18 into our array in the middle along with like both like both the pivot and the duplicate of the pivot right and finally we're going to do a final scan and check for elements that are larger than the pivot so we'll see that that's 22。

 34 and 99。Okay， so now after our very first partition， we have these。

This underlying array that's split up where 18 is the pivot so it's like the middle elements right everything to the left of 18 is smaller than 18 and everything to the right of 18 is greater than 18。

 but we have no idea about the state of how like everything smaller than 18 is sorted like for example 711 and4 is not sorted right but we have no clue of knowing that from a computational perspective right when we're looking at this programmatically。

So what we need to do is remembering that quick sort is。

Qusort is an a recursive algorithm is that we need to run quicksort and repartition the right and left submars right so what we're going to do is let's focus on the7 11 and four next。

In this case， we would like to pick our pivots in this sub。

 so our pivot is again going to be the first element of our list， so our pivot is going to be seven。

And what we're going to do is make a scan for elements that are smaller than seven in this subarray right elements that are larger than seven and elements that are equal to seven so what we're going to do is when we scan for smaller elements。

 we're going to put a four in there。When we scan for elements equal to the pivot we're going to put our seven and finally we will scan for elements that are larger than our pivot so our 11 is going to go there and we are going to move on to recursing again over here because once again we have our seven and we have the left and right subs of seven right and trivially we're going to see that because like there are only one element each right the elements that are less than seven and elements that are larger than seven in the sub array there's only one of each that's trivially already sorted right so we don't need to worry about those so we're going to call back up here。

And basically we've already after we recursed with quickSo onto our left sub array so all the elements that are smaller than our pivot。

 we know that the elements that are smaller than our pivot were already sorted so we can move on to our pivot now and when we move on to our pivot we'll see that there's two18s which is totally fine we don't really need to sort our pivots here so we can just pop them into our array and finally we will recurse onto the right subar of our original list after we partition right because we want to be able to sort the elements that were larger than our pivot so we're going to look at the 2234 and 99 and here we have 22 as our pivot right because it's the first element in our sub array。

So when we scan for。Elements that are smaller we want to scan for elements that are smaller than 22 in the sub over here we're going to find none that's totally okay then we are going to scan for elements that are larger than 20 sorry equal to 22 and we'll see that we just have the pivot so we're going to put 22 and it's place right here and finally we're going to do a scan for numbers that are larger than 22 so we're going get 34 and 99 and pop them into our over here。

So now once again， because there are there's more than one element in the right summary of。

Numbers that are larger than 22 we're going to have to recurse onto these numbers right so trivially we can keep 22 in its place because it was the pivot but we have to look at the 34 and the 99 next right？

So when we do the 34 and the 99 what's going to happen is we're going to treat 34 as the pivot because again it's the first element of its subarray right so the pivot's going to be 34 and we are going to scan over our remaining list of 34 and 99 for elements that are smaller than equal to and larger than the pivot and what that's going to result in is going to be a list of 34 and 99 so lucky us we didn't have to change the ordering right so we found elements that were equal to 34 then we found elements that are greater than 34 and trivially because they are only one item each were all good we've sorted it and we are now done with our quick sort with threeway partitioning on this list。



![](img/e6a7e7faae6be2396dc14b6e568bdc68_3.png)

![](img/e6a7e7faae6be2396dc14b6e568bdc68_4.png)

Okay moving on to1 B， what is the best and worst case running time of QuickSo with horror partitioning on n elements。

 given the two lists4，4，4，4，4 and12，3，45 assuming we pick the first element as the pivot every time which list would happen to result in better runtime so what's going to happen over here is first of all we know that the best in the worst case of running running time of QuickSo so the best case is going to be and log n and that's when we split the list relatively evenly right and the worst case is when we don't split the list evenly with the partition at every step and we end up doing n squared work。

And now that we know our best case and worst case， let's figure out which of these lists would result in a better quick sort runtime if we were to run it with horror partitioning so the first one we have four four four。

 four four and the second one we have。One， two， three， four， five， all right。

 let's do hard partitioning so we're going to pick this front floor as the pivot。

And let's initialize our left and our right pointers on the all duplicates list with all fours， okay？

Remember that in horror partitioning we want L to be a pointer to the leftmost element that's not the pivot and we want G to be a pointer to the rightmost element that's not the pivot right so what's going to happen here is we want to walk pointers towards each other as much as we possibly can and how we do that is that the left element sorry the left pointer only likes elements that are strictly less than the pivot and the right pointer only likes elements that are strictly larger than the pivot and if at any point they land on something that they don't like then they should stop moving okay so basically when we start out when we see this element is G we'll see that they're both pointing to four and four is just the pivot right so actually both of our pointers are going to stop here。

Because they're like wait a second four L is going to be like the left point is going to be like four is not strictly less than four so i'm going stop here and the right pointer is going to be like four is not strictly greater than four so I'm going to stop here so what you do at this point when both pointers have stopped is you want to swap the elements。

That left is pointing at and that right is pointing at here trivially both therefore。

 so it's not really going to make a difference and after we swap the elements。

 we move these pointers one step closer to each other。Okay。😊。

So let's repeat the process because we're not done right because horror partitioning only completes after we cross the left and the right pointers right and after we cross the left and the right pointers we want to swap the pivot with the element that the right pointer is pointing to okay？

So what that's going to look like is after we walk these towards each other after swapping that's just how horror partitioning works。

 we're going to once again take a look at whether or not we like these elementss so the left pointer is going to look at the floor and be like yuck this is not strictly less than four I'm staying here and the right pointer is going to say yuck this is not strictly greater than four so I'm going to stay here so remember that when both pointers stop we just do a switcheroo。

We swap the elements that they're pointing to and trivially again i'm not going to redraw because they're both four and after that they're going to both move in the directions I want to walk towards so the left is going to move one position to the right and the right pointer is going to move one position to the left so what that's going to look like。

Is this？And at this point， this is great because this means。😊。

That we need to stop or partitioning now because the pointers have now crossed so what we do in this case is we're going to swap the pivot with the element that G is pointing to and now again。

 because they're all four it doesn't really matter。

But basically this means that our original pivot is now in the middle。

 which is great because that means that our pivot nicely separated the left and the right right so you can think about this so we just chose a duplicate list as an example of in the extreme case but you'll see how who partitioning nicely partition this list when it was all duplicates right so because the pivot ended up in the middle and everything to the left of the pivot is like smaller than the pivot or in this case it's like in this case with duplicates it's equal to the pivot and everything to the right of the pivot should be larger than the pivot and in this case it's equal to the pivot and that's just how it works when you're on a duplicate list but that's fine but you might be able to see how we generalize this to when we pick the pivot nicely basically right it'll separate our lists into two approximately equal and nice sublists okay。

Now on the other hand， what if we were to run horror partitioning on this list of one， two， three。

 four and five， so I'm going to do this one in light blue。And in this case。

 this is an already sorted list and let's choose the first element as the pivot。So once again。

 I'm going to initialize my left and right pointers。😊。

And my left pointer is only going like elements that are strictly less than my right pointer whoa sorry I don't know why I said that my left pointer is only going to like elements that are strictly less than my pivot and my right pointer is only going to like elements that are strictly larger than my pivot okay。

 so what's going to happen when I look at my left pivot is I'm going to see that I'm on a two2 is not smaller than one so I'm stopping here on the other hand when we have G the right pivot。

G is going to be like I on5， sweet， five is greater than one， let me move on。

I'm going to move on to four， four is greater than one。 A I still like that。 let me move on。

Then G will get to three and we'll be like， oh， three is still greater than one。 I like that。

 Let's move on。😊，you will hop over to two and be like I still like that because two is greater than one right and we're going to move one more step to where it points over to one and at this point weve crossed our pointers right the right and the left pointers have crossed and remember what we want to do at this point is we want to stop and we want to swap the pivot。

With whatever element is that G is pointing to Well in this case like the pivot and G are pointing to the same element right so basically we just like swapped it in place we didn't really do anything but what that means though is that when we need to recurse with quick sort on the rest of our list we have to do this recursion on this two。

3，4 five here right all we did was ensure that this pivot one was in the correct place like that didn't really help us because it was already sorted right so when we go over here to this two。

 three， four five we have to rerun horror partitioning all these four elements as opposed to the example up here when we had all duplicates we split it nicely into two halves right versus this one we didn't really split it into halves because all four of the remaining elements are in one side of the pivot right？

So the answer to this question is that we're going to get n log n。On the list of all duplicates。

With horror partitioning and in the worst case， we're going to get n squared on the completely sorted list when we choose the minimum element as the pivot and just as a note。

 we could have also chosen like the last element as the pivot right the five here and it still would have given us n squared time because if you think about it it would have given us the same scenario where we。

嗯。Pivt on five and then everything that we need to recurarse on is already to the left of five right everything is smaller in five so it doesn't really lower the amount of work that we really need to do in one iteration of Quick sort and that's the reason why we have the best case in the worst case on these lists respectively okay。

😡，All right， moving on to1C， what are two techniques that can be used to reduce the probability of quick sort taking the worst case running time so recall that the worst case running time happens when we pick a bad pivot right every time and the bad pivot comes from choosing something。

A bad。Number two partition on， right？Oops。And what we mean by that is like like you know the example that we just went over in one B where if we had like one。

2，3，4， and five， if we partitioned on one or five， that would be super bad because that means that we really just need to sort like everything else in the rest of this list right we need to partition the rest of that list but it's only separating out one number at a time as opposed to when we have like a nicely sorted or sorry like like a pretty wellshuffled list or maybe a list completely of duplicates then we partition our list pretty nicely so that we have an approximately equal number of elements that are less than the pivot in comparison to approximately equal number of elements that are greater than the pivot right？

So we can reduce the probability of quick start taking the worst case running time by basically trying to avoid choosing the worst pivots right aka avoid choosing the minimum element or the maximum element so we can do that in a couple of ways so firstly we could randomly choose pivots that's fine like randomness is always helpful when we're trying to figure out。

Randomness is always helpful when we're just trying to pick pivots randomly sorry that was very randomabout I mean it randomly choosing pivots is really helpful for avoiding like a certain kind of pivot like for example。

 if we fed a perfectly sorted list into quicksort if we chose the first element every time that's not very helpful for us right because then we would get the worst case from the time every time but you might consider doing something like to account for the fact that you might accidentally run quicksort on a completely sorted list you could totally like pick the element in index2 and the next time pick the element at index5 to be the pivot and so on and so forth right。

Another thing is we could shuffle the list before running QuickSo and this effectively does the same thing like if we passed a list of QuickSo that that was fully sorted。

 then if we shuffle the list that helps generate like some kind of like randomness into like the distribution of numbers across our list right and finally we didn't really write it on here but you could always pick the median。

😊，For pivots。Right and ideally we want to pick the median every time because that's going to give us our best case running time right that's going to give us our n log n for quicks but again you can't always guarantee the you can't always guarantee that you'll find the median in like a really nice time because finding the median is like an entirely different problem I think Professor Hugg talks about it's called a quick I believe it's called quick select and it takes like a not insignificant amount of time so it's sometimes not always the easiest to pick the median for the pivot but yeah and that is it for question one。

😊。

![](img/e6a7e7faae6be2396dc14b6e568bdc68_6.png)