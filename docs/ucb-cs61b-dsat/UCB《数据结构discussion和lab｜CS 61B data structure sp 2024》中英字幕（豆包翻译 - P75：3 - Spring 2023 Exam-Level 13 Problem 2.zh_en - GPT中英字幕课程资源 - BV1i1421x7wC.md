# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P75：3 - Spring 2023 Exam-Level 13 Problem 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/9fd6acae7ab34d6d647528e3f77150b1_0.png)

Everyone， this is Sherry and this is the spring 2023 exam level。

13 walkthrough in this video we'll be going over problem two conceptual sorts just like the problem says it this is just a bunch of true or false questions and other conceptual questions about sorting algorithms。

And these are the kinds of questions that you might see on exams about sorts because it's kind of hard to test coding questions on sorts so we like to give you conceptual or algorithm design questions instead。

 so with that let's just jump right in I'm assuming that you're already relatively familiar with all the sorts that we learned in this class because this is just a recap of what we learned last week。

So let's start with the very first question， so we can see that if we have a system running insert searchion sort。

 we find that's completing much faster than expected and what can we conclude based on this。

As you should probably remember from class， insertion sort runs really fast if the array is sorted。

Or it's like almost sorted and that's because insertion sort has runtime theta of n plus k where k is a number of inversions so if it's almost sorted then this K will be very small and it will basically be linear so what we can conclude is that this array is sorted or it's almost sorted and that's why insertion sort is running so fast。

Okay， now let's move on to the next part which says you have a five integer array that elicits the worst case run time for insertion sort。

 so we just discussed above how the best case for insertion sort is when it's sorted。

 but actually the worst case as you might expect if we're kind of like building off the best case is when it's reverse sorted。

And this is because there's a maximum number of inversions in a reverse sorted array right if we have something like let me just。

So this is our， for example， our five integer worst case input。

 there's an inversion between every single pair of numbers and that's the maximum number of inversions。

是。Okay， so that's the best and worst case for insertion sort now we're moving on to He sort and there's a very simple true false He sort is stable。

And this is actually false， I'll just remind you that stability means that。

The relative ordering is maintained。And what that means is that if we have two items， for example。

 let's called them 20 a and 20B and we sort both of and we sort the array。

 these should end up in the same relative order with 20 A before 20 B in the final sorted array。

 and this is not necessarily the case with heAP sort because of the heEAP operations。So for example。

 if we push and pop from an array， if we push and pop from a heap and we do like the bubbling up。

Or down。This can cause our heap to get out of order in terms of the relative ordering of items that are equal。

 so I won't go through a full example here， but if you want to do heap or on this array。

And you run the algorithm， you'll see that these two actually end up switched in the final array。

 which is not stable。Okay， and just in general for stability。

 you should probably just memorize which sorts are stable and not stable because it's actually very hard to prove to yourself like on an exam or something。

Okay， and then for the next part。😊，It asks us give some reasons as to why someone would use mergeSo over QuickSo so we learned in class that QuickSo is like empirically faster。

But we don't always want to use quick sort， so I'll give you guys a couple scenarios where merge short might be better and there's a lot of possible answers for this one。

 so these are just some possible answers so first of all merge short is theta of n log n。In any case。

 right？Well， quickSo it can be。Data of n squared in the worst case。

 so if we want to guarantee that it's always n log n。

 then we would probably use merge store the other reason is that merge store is stable and quickstore isn't。

 especially if we use whole partitioning。And then also merger can be paralleled。

That's because we have like the two halves that don't interact until the very end so if we have some kind of parallel computer that has multiple cores we can sort each half within itself at the same time and that's kind of out of scope for this class but just know the idea of like you have separate hals that don't interact so you can sort them at the same time and finally。

We use merge sortt for linked lists and you can see why partitioning wouldn't really work for a linkedist because partitioning involves like swapping things around in their positions and that's really hard for a linked list because there are physical nodes that can't really be easily swapped around so those are just some reasons that we might want to use mergechstore over quicksort。

Okay， now the next part we're given six different sorts as well， sorry。

 we're given five sorts and a none of the above option。

 and we have to match which of these statements match with。Any of these sorts。

 and there can be more than one sort for one property or there can be no sorts at all。

So let's just start off we have Quick sort merge selection or insert sort and heapS and we just have to list all the letters that apply to each of these properties so for the first one it asks us which of these is bounded by an omega of n log n lower bound what this means is that this sort always runs n log n or slower。

So which of these sorts even in the very， very， very best case is bounded by n log n on the lower bound。

 that's actually A， B and C， so that would be quick sort merge sort in selection sort。

 these can never be better than n log n for insertion sort and heap sort this is kind of tricky but for insertion sort remember。

If we have a sorted list。This is about linear， so this is actually better than animal again and for heap or。

 we kind of have a similar thing where heplification。

Takes linear time and then if it's at all equal items so all the items in the heap are the same we're never going to bubble up or bubble down so this is actually going to be linear as well。

 so both insertion sort and heap sort can run better than n log n in the very best case。

Okay now we're thinking about worst case runtime so this question asks us which sorts have a worst case runend that is asymptotically better than quickwords worst case so there's a couple parts of this question the first part is we have to identify quickwords worst case which is theta of n squared and then we have to figure out which sorts have a worst case runtime that is better than this strictly better so let's just write down the worst case obviously quick is not strictly better than itself so we can just skip over that and then merge sort remember it's always n log n。

Selection sort is nd insertion sort is n squared in the worst case where we have a reverse sorted array and heapSo is always n log n as well。

 so that means our answer is B and E because these two sorts。

 mergerch sort and heap sort are always better than quick sort in the worst case。

Next one this one's quite tricky and it's basically asking us which sorts never compare the same two elements twice so this one's pretty tricky and I think the best way to do this is just to go through them one by one so let's start off with quick sort。

Remember in quick sort we choose a partition so let's call this P and then we put the items less than or equal to it one on one side and the items greater than it on the other side so and then we recursively sort each of these hals so you notice that every item is only compared to。

The comparison happens when we compare something to the partition to see if it should go in the left half or the right half and once we compare it to the partition we don't use the partition anymore right it's kind of like eliminated and we just recursively sort each half so nothing is ever compared more than no two pairs of elements are compared more than once because once we compare something to the partition we never use that partition again so QuickSo is one of the sorts that never compares the same two elements twice again just because once we use the partition in a comparison we don't use it again and we just recursively sort within these two halves。

Merge store is actually similar where if you remember merge store we just recursively sort each half and then we merge at the end and the only comparison that happens is when we merge because we have to compare which item in the beginning of the array is smaller to where put it to know which element to put at the beginning of our merged array so the comparisons happen during the merging and again we never compare the same two elements because we're always comparing two halves of different arrays right so if you think about this we split our array we split our array again。

And we're always comparing elements from different halves of the array right so here we're going to compare these two and these two and here we're going to compare these two and so we never compare the same two elements twice and so mergerch store is actually one of those sorts as well。

And then now let's look at selection sort， you can remember in selection sort。

 we have to define the max。And then we swap it。And finding the max， if you remember。

 we just loop through the away and we keep comparing elements to see if there's any greater elements and if we find a greater one we replace it so it kind of looks like this for n in array。

If n is greater than max。Max equals in And if we look here。

 this is where the comparison happens So this can definitely compare the same elements more than once because as we're finding the max。

 we have to compare this elements over and over again and this is part of the reason why selection sort is so slow and has a theta n squared runtime so this is actually not one of the sorts that never compare the same two elements twice okay next is insertion sort so for insertion sort you might remember the way we do it is we pick an element and we swap it to the front as much as possible and we know to stop swapping when we reach a point where this element here is is less than this element so we keep swapping until it's in its proper place in the array and you notice that for each element we only compare it to the elements in front of it never we don't care about this back half of the array because insertion sort kind of moves sorting from the beginning to the end so this part of the array is sorted and it gets。

compared to whatever element we're swapping this part of their array we don't care about when we're swapping this element。

 so actually an insertion sort since we only compare each element to the ones in front of it。

 it never compares the same two elements twice。Okay， finally， for heap sort， this one。

 you could compare the same two elements just because you have all that bubbling up。

Down and you also have the heapplification。I won't walk through a full example。

 but you can just see that in the heplification process we might compare two elements to see where they go in the heap and then we might compare them again when we're bubbling up and down so he sort is not a valid answer for this part。

😊，So the final answer is A B and D， which is QuickSo， merge sort and insert sort。

Okay that was quite long now let's move on to the last part which is which sorts run in the best case login time for search and inputs and this is pretty simple as none of the above if you remember from a lecture we prove that no sorting algorithm can ever do better than theta of n and that's just because you must look at all the elements。

At least once， because if you don't look at all the elements。

 you have no idea what's in your array at all， so there's no way any sorting algorithm could run better than theta of it。

😡，That's it for this problem， good luck this week and in the rest of 61b。



![](img/9fd6acae7ab34d6d647528e3f77150b1_2.png)