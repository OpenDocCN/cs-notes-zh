# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P80：5 - Spring 2023 Discussion 14 Question 4.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发比哈比。🎼不必。

![](img/b28c34f7ba56ab75b2f9fc6b865231d5_1.png)

🎼And。🎼Yeah。

![](img/b28c34f7ba56ab75b2f9fc6b865231d5_3.png)

![](img/b28c34f7ba56ab75b2f9fc6b865231d5_4.png)

All right so let's now move on to question for conceptual comparison sorts。

 this is extra on this worksheet because it kind of is review from last week but I think it's good practice anyway so we're going to get right into it answer the following questions regarding various sorting algorithms that we've discussed in class so we're asking to give a five integer array that elicits the worst case runtime for insertion sort so the worst case runtime for insertion sort this big data of n squared and I could give you the answer right now about like a five integer array but let's intuit it out a little bit based on the best case runtime which is n。

So the best case runtime happens when we have no swaps necessary。

And that would be a case where let's say we have the list1，2，3。

4 and5 and remember how insertion sort works so we would start at the beginning of the array and we tried to swap our number left if it's smaller than the element to its left right and we keep going until we run out of elements to swap with so here trivially when we start off we'll see a1 there's something to swap with two is not less than one so we don't swap three is not less than two we don't swap four is not less than three so we don't swap and likewise5 is not less than4 so we don't swap and effectively we went through our entire array in one linear pass with no swaps right we just had to check each number。

So that means that in the worst case with n squared， we get the max number of swaps。

And you'll notice here that we had zero swaps because the numbers were already in sorted order。

 so that means that the worst case scenario would come from us giving something like54321 so a number Im sorry an array in descending order。

And the reason for that is we'd get。😊，N times n minus1 over2 swaps total。

And this comes from the summation formula。Of I equals1 to and 1 of I。 So you can， what is it called。

 you can like check me on this if you'd like later。 But this is。

 I'm just telling you right now that this is the maximum number of swaps。 So over here， we'd see。

Starting from the beginning of the right no swaps because there's nothing to the left of five then we get to four we have to make one swap with five right when we get to suite three we'd have to make a swap with the five and then the four we get to two we have to make a swap with the five the four then the three and so on and so forth right so we effectively do n minus1 plus n minus2 plus n minus3 plus n minus4 all the way down to one work and when we add that together that's effectively n squared and that's like based on the maximum number of swaps right。

So that's it for part A。Now for part e part B give some reasons as to why someone would use mergeL over clickSo so we can talk about this in I think like the most intuitive ways to consider like advantages and disadvantages is in terms of runtime and space complexity so。

For runtime。We know that the best case for both mergeO and QuickSo is N log n right。

 but in the worst case for QuickSo we have n squared and the worst case for mergeSo is still n log n。

 so we would say that mergeS。Worst case。Is better。Then。Quick sorts。Worst case。Of theta of n squared。

 so that could be one reason， right？And then we can talk about。Space。So。Oh actually。

 space would not be an advantage of mergelo over Quicksort because Quicks typically uses less space than mergelor。

 sorry， excuse me， not space， but we can talk about stability as well。

So if you recall merge sort doesn't do any like crazy swaps over like multiple numbers in the array。

 so merge short is stable。Whereas quicksort typically isn't and when I say typically it's because we usually use horror partitioning when we run quickst instead of three scan。

 three scan partitioning will result in a stable sort。

 but it's not typically desired because it uses extra space。So I'll say Quicks is usually unstable。

Another thing that we might consider is that merge sort can be highly paralleled because we can split merge sort into two hals and those halves don't interact until the end right they kind of like are treated as like separate entirely separate subproblem versus like horror partitioning requires us to look at the entire rest of the summary that we haven't already seen right and then merge store is also preferred for sorting a link list so i'm not going to get into the details of that it has to do with memory access and cache locality I believe but these are the two main ones in which you would use merge sort over Quickstar so the first one is runtime the second one is stability okay。

Now let's move on to part C， which is my favorite part of this question I think is really cool because it challenges a lot of our ins of what we know about sorting so we're given an answer bank each item of which may be used multiple times。

😊，You may not need to use every answer and each statement may have more than one answer so basically it's like a choose all that apply situation okay so the first one is a quick sort where we choose horror partition and use the leftmost item as the pivot we have merge sort selection sort insertion sort and heap or or F which is none of the above okay so list all letters that apply all answers refer to the entire sorting process not a single step of the sorting process for each of the problems below assume that n indicates the number of elements being sorted。

So first up we have bounded by big Oomega of n log n lower bound。

 so I think this one is actually a little bit tricky because we tell you in this class that in the average case there's no sort that's going to run faster than N log n okay that's in the average case we're not talking about the best case。

But you might remember that in the best case for something like selection sorry in the best case for something like insertion sort。

 if we get a list that is perfectly sorted like I talked about in part A。

 then we are finished sorting in linear time right so we can't say that selection sort is lower bounded by n log n it's technically lower bounded by n right it's linear in the very best case。

 but remember that we're talking about lower bounds here not the average case where we would more generally talk about the n log and lower bound for comparison sorts so already for this part A we can't say that insertion sort is part of it。

😊，Likewise， in heap sort heap sort's best case scenario is also linear。

 so we can't count heap sort as part as being a lower bounded by N login and I believe the。

The the linear time he sort comes from when you have a lot of duplicates in your list。

 so basically the answer to this bounded by omega of n log n is going to be A B。

And see so QuickSo is we know that it's best case scenarios is n log n merge so it's best case scenario is n log n selection sorts best case scenario is n squared right it's consistent across the best and worst case scenario。

 but ns word is lower bounded by n log n so we can say that that's totally fine just that insertions or and heapO are not part of this lower bounding of n log n okay。

嗯。Now in the next part， we're asked what about the worst case runtime that is asymptotically better than Quick source worst case runtime so Quicksource worst case runtime。

Is going to be theta of n squared So we want to find out which of these sorts has a worst case runtime that is better than n squared so quicksort trivially can't have a better worst case runtime than quick sort itself so we know that a is not going be part of this let's cross that out merge sorts worst case runtime merge sources actually consistent across the best in the worst case the worst case runtime is actually n log n so we know that merge source is going to be on this list。

Selection sorts worst case runtime again， selection sort is consistent across the best and the worst case。

 so it's going to be n squared， so we're not going to have selection sort in this list。

Insertion sorts worst case runtime is also n squared， right。

 We discuss this above with the maximum number of swaps。 so we know that insertion sort。

It's not going to be in this list。And next we have Heap sort Heap sorts worst case runtime results from popping off n elements from your heap and having to reheify every single time with log n we each time。

 so that's going to be N log n in the worst case， so Heap sort is going to make it onto this oops heap sort is going to make it onto this list。

 so we're going to have B and E here。All right。All right， let's now move on to the next part。

 which says in the worst case performs theta of n pairwise sops of elements， so this one。

I'm sorry it's worded a little bit ambiguously in the worst case we don't mean the worstcase runtime we actually mean the worstcase number of swaps that we could possibly get during the sorting algorithm and because of that it's a little bit a trick because we don't typically think about most of these sorts in terms of like swaps or not so let's walk through these one by one So first up we have quicksort I'm actually going to leave quick sort for the end because I think it's the hardest one to conceptualize but merge sort。

 this is a bit of a trick question because merge sort even though you might think about merge sort going in like a zipper fashion merge store actually doesn't swap at all right merge sort has zero swaps because when we like when we zipper our list together we're not swapping anything we're just appending elements to a list so merge sort has zero swaps。

What about selection Well if you remember how the selection sort algorithm works is that it starts with your whole array and we go through our entire array and try to find the minimum value and then we put that minimum value that we find in our whole array into the next smallest position that we haven't already seen right so we would put it in like in the very beginning we would put it in like index zero or something like that right and then how we would do that is we'd swap the element that we the minimum element and the array that we found into position zero and then move on find the minimum element in the remaining array and swap that into position one and so on and so forth right？

So if you think about how selection sort works is that it has to go through the array and the remaining array every single time it runs an iteration right which means that in all iterations of selection sort there's one pairwise swap that happens right we need to swap the minimum value that we found into the next smallest unsorted position right so actually selection sort is great it's actually going run with theta of n pairwise swaps of elements right because we need to basically swap in the n like minimum values in these remaining array that we haven't already found the minimum value of right that's the whole stick of selection sort what about insertion sort Okay so we did talk about insertion sort above。

😊，In a part， like。A and I did talk a little bit about the worst case scenario with selection sort insertion sort I'm sorry So in the worst case scenario on insertion sort。

 you're going to get on the order of n squared swaps right so in as an example in a descending order you would have to swap the four back one position you'd swap the three back twice the two back three times and back four times so on and so forth so you're really doing one plus2 plus3 plus4 all the way up to n minus one work and when you add that all together that's going to give us this number of swaps is n squared so we know that insertion sort is not going to fall into this category because it's n squared swaps right。

HeapSSo is interesting because HeEAPS all of the work from HeEAPS sort basically comes from swapping right and we know that the swaps that happen in HeAPS are a result of like reheapifying our array or our underlying list and we know that the worst case runtime or the worst case number of swaps that we do is going to be N log N。

Right and that's going to be like n for the number of elements that you're trying to remove from your heap and log in for the number of times you're trying to there log in for the amount of work it takes to reheapify your heap so this is definitely not going to be part of our list so we know that selection sort is for on this list but what about quick sort so quick sort is a little bit tricky because。

Because in QuickSo when we use horror partitioning。

 the number of swaps that we have in our rate is dependent on not just the input。

 the kind of input we get， but also the pivot that we choose right and actually in the worst case scenario of Quicksort runtime I'm actually going to write this out worst quicksort time。

Is theta of n squared， right， and the best quick sort time。Is the of N log n？

The worst quick sort time actually results in the least number of swaps。

In horror partitioning and in the best case when we have N log N， depending on like your input。

 right， we could get a runtime of N log n to sort quick sort。

 but this could result in the max number of swaps。So it's a little bit convoluted here because technically speaking。

 it's a little bit strange because the worst quick sort runtime results in the least number of swaps whereas the best case runtime for quick sort results in the maximum number of swaps and to illustrate this I'm going to take you through an example really quickly so oh actually。

I'll just write it from scratch。 So in the。Best case。Run time。

ULet's do the example that we did in like question one。

 I think it was like one B where we were asking about like the best case scenario。

 let's say we have this list。It's all fours okay and let's try to run quick sort on this with horror partitioning so I want to pick this first four as my pivot I'm going to literally initialize my left and my right pointers and remember that my left and my right pointers they want to stop whenever they see something they don't like so my left pointer wants to stop if I see something that is not strictly less than the pivot and I want my right pointer to stop when I see something that is not strictly greater than my pivot well in this scenario with the besties runtime with n log n。

In horror partitioning。What's going to happen is initially when we start we immediately stop our both our left and our right pointers。

 there's nothing to move on because we don't like the fact that four is equal to four in both of these cases right we don't want to be the same as pivot so what happens here is remember that the next step after we stop both pointers is we swap the elements。

😡，Where these two pointers are pointing and trivially they're both four so it's not going to change the underlying array basically unless you're talking about stability but they're both going be four right so that's one swap that we do and after that we want to move the left and the right pivots closer to each other again。

Okay in this case it's the same thing that happens again we stop both of our pointers because they're equal to the pivot right we don't want that so we'd swap these two elements and we'd walk。

😡，Them forward and backwards respectively。At this point。

Our right pointer has crossed our left pointer And what we want to do now is we swap。

Our right pointer element with the pivot so what that's going to look like is that we still have an array of all fours right but we've established that hey our pivot of four is now going to end up in the middle here so when I recurse we have our four pivot in place and we want to recurse on is this four4 sublift to the left and the four4 sublift to the right。

Now let's start the process again。Let's make these our pivots。

This is trivially our left pointer and our right pointer。

Or both of these cases so i'm just going to actually do just this case over here because this is the same thing over here right so when we have our left and our right pointer they're both pointing to a four we don't like that so what we're going to do is we're going to swap the element。

And move our pointers on。Right and our left pointer doesn't really have anywhere to go。

 but our right pointer is going to go down one and that's going to head over to where the pivot is。

 right？And once we get to this point we're going to be like okay。

 our pointers have crossed now let's swap the pivot with the element that I was that the right pointer was pointing to so what's going to happen here is。

You're just going to swap the for with itself。Actually。

 I suppose that whether or not you actually advanced G is dependent on the implementation of horror partitioning。

 but in this case because there's only two elements left。

 it doesn't really matter because the result will be the same。

 but basically what happened here was that we had。Two swaps， right。

 and we also had two swaps here because these two are the same case， right？

And then trivially when we get down here one more time to like the single element list。

 those are trivially sorted and those are the base case of quick surveys。

 so we don't need to worry about that。The point is， at this topmost level。

 you'll see that we did four swaps。And at this level。We did。Four swaps as well。

 it was two swaps plus two swaps。Right so the pattern here it's a little less subtle to note。

 but basically you should realize that we are doing a certain number of swaps at each level of our recursive call for quick sort right we're doing the same amount of work or the same number of swaps per level of recursive call in the best case runtime right so we did four swaps。

And they're at log N levels。Right and this four swaps per level we can actually notice and I'm not going to get into like the nitty gritty here because I promise that I'm not lying when I say that this is equal to n divided by two plus one swaps where n is the number of elements that you're trying to sort in total I actually did try it out because I was just trying to make sure that this formula was actually correct so really this formula should be like n divided by two plus one times log n swaps。

Which is approximately n log n swaps。Right so in this like worst case scenario of the number of swaps that we could get。

 which was very unintuitively resulting from the best case runtime， we got n log n swaps。

 which is definitely not the worst case number of swaps of linear right we did way more swaps than linear and just to like。

Do the worst case runtime of Quickstar just to show you really quickly。QuickSo runtime。

 so the worst case quick sort runtime will result in an n squared time。

And let's say we had this list of one， two， three， four， and five。

 and we chose the minimum value to be our pivot。If we ran through horror partitioning。

 what would happen is we would stop oh wait oh yes。

 we would stop the left pointer immediately because we see that a two is not less than one and what would happen is would keep advancing the five down because five is greater than one。

 four is greater than one， three is greater than one。

 two is greater than one one is not greater than one oh。

 we've crossed paths at this point and now I want to swap my right pointer with the pivot and what that would result in is just one swap here。

Right， so that's one swap at the top level， then when we recurse on this remaining subway we're going to do the same thing where the left pointer is going to remain at the same spot。

 the right pointer is going to swap all the way back。

And what's going happen is that there's be one swap at the end。

 So in total for the worst case quick sort runtime of n squared， you only get n swaps。

 so it's actually a little bit unintuitive right it's like you would think that the more swaps there are the worst the runtime but no in the case of Quicksort it's the opposite when we have the best case runtime of n log n we also have n log n swaps instead of n swaps and that is why we don't count quick sort as being in this performs linear pairwise swaps of elements Okay that was a lot and you can like fact-check me on this like you can draw out your own list and you will see that it results in approximately n log n swaps in the worst case number of swaps or quicks okay。



![](img/b28c34f7ba56ab75b2f9fc6b865231d5_6.png)

All right。