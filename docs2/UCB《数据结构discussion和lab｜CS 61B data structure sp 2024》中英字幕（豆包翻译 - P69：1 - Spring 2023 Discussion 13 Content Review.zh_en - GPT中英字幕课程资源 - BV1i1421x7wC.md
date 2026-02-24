# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P69：1 - Spring 2023 Discussion 13 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼比哈比。🎼Oh。

![](img/217bc4b16db93545037d4292247b09d4_1.png)

![](img/217bc4b16db93545037d4292247b09d4_2.png)

Hello everyone and welcome to CS6 UNB Spring 2023's walkthrough of discussion number 13。

 which is going to be about sorting。😊，I actually to escape over the announcements because I know I'm recording this a little bit late。

 but really quickly as a reminder， Project3 as a whole is going to be due on Monday， April 24。

 so please get started on it if you haven't already and now it's just jump right into the content review So today we're gonna learn about a couple of different kinds of sorting algorithms and sorting as a whole is a really important and cool topic or in my opinion it's really cool a really cool topic in computer science because it's like a simple problem that is very useful on the everyday right like how do we sort a list in alphabetical order。

 how do we sort of list numerically or by points or something like that it's something that we see on an everyday kind of columnplace basis So now we're going to get into the nitty gritty of like well a computer can only sort according to how you tell it right it's not like us where we look at a line of numbers and we can immediately see like oh one is the smallest number in this list we know that's gonna to be like the first element in our。

ed listen to any order a computer can't do that super easily right so we need to tell it how to do it programmatically and we'll talk a little bit about the different kinds of ways that we can tell a computer to sort as well as the relevant runtime okay。

😊，So first up we have insertion sort so insertion sort iterates through a list and swaps items backwards as necessary to maintain sortedness。

 So what I mean by this is let's say we have this list 35，12，4 and we want a list that's like one，2。

3，4，5 at the end right we want it to sort it in ascending order what it's saying is basically I'm going to start at the beginning of my array and see if it is smaller than the any of the elements to the left because if this element oops if the element at any position in the array is's smaller than the element to its left then we know it's not in sorted order right because we want the elements to be ascending so what we're going to do is we' going to start at the three we're going to see that trivially  three is the first element of the list there's no element from the left of three so we don't do anything then we're gonna move on to five and say okay5 has three to the left of it the five is greater than three so it could be that these two are sorted relative to each other right？

😊，Now things get a little more interesting when we hit the one because we're going to see the one and see that the element to the left of five sorry the element to the left of one is five and we're like wait a second one is less than five I know that one should be to the left of five so what we're going to do here is we're going to try to swapamp。

😊，Okay， and what that's going to result in is going to be a list， something like this， three，1，5，2。

 four。Well， we're not done， though， right， because we know that we haven't seen everything to the left of one after we made a swap with5。

 So we're going to continue looking at this one and see that the element to its left is a three。

 Well， we know that one is less than3。 So we're going to swap in。

One over here and our list so far is going to look like this， three， one， three， five， two， four。

Okay， so at this point we know that we already looked at the element in index two of our list right so we have insured because we went from left to right in our underlying array we have ensured that the first three elements in our list have already been sorted relative to each other so we can just jump right over to the fourth element in our list aka the element at index3 in our array right so we're going to look at this two and do the same thing we're going to see that two is less than five so let's make a swap。

After we make the swap， our list is going to look something like this。 and once again。

 we need to consider swapping to as far down as it goes。

 right So we're going to see that two is less than three and we're going to try to swap again。

And we're going to get a list that looks like one， two， three，5， four。

 and we know that these first four elements have been sorted with respect to each other right we don't know what's what comes after the fourth element in this list because we haven't seen it yet。

So when we do actually look at that fourth element in this list， well see that it's a four。

 and we're going to swap that with the five。😊，And we'll get one， two， three， four， five。

And that's our list。Okay， so in the runtime over here。

 we say that the general runtime is big O of n squared and the reason for this is that the best case in the worst case for insertion sort are very different Okay。

 so we say that it's big of n squared because。😊，At the worst， it could run in n squared time。

 And let's give an example of this。 So as an example list， let's use 5，4，3，2，1。

If we had to do insertion sort on this list， we'd have to swap this right and then we'd have to okay that would result in a list like 4。

5，32，1， then we'd come over to this element over here and we'd have to do two swaps。Okay。

 so then we'd get3，4，5，2，1。 Then we come over here to the two。 and we have to do three swaps，2。

3 and so on and so forth， right So the example I gave over here is of a list that is completely inverted。

 it's in the opposite order in which we want to be sorted right Like we want to have our sorted order be ascending here it's descending If the elements are in reverse order you're gonna to get the worst case time on insertion sort because you're going to do effectively one plus2 plus3 plus4 plus5 all the way up to n minus1 swaps right And if you add all of those swaps together like1 plus2 plus3 all the way up to n1 you're going to get approximately n squared swaps。

 So we say that the worst case time of insertion sort is n squared。

 Okay I'm going actually write this down so。Well say the worst case？

He'll do n squared swap so it takes n squared time and in the best case。

Is kind of like the converse of the worst case right so in the worst case we have a list that's completely flipped。

 but it's in perfectly descending order In the best case。

 we would have a list that is already in like perfect sorted order。

 so we'd go across each element and realize that we don't need to do any swaps so that would be at worst a linear pass across the entire array right you check the one。

 there's nothing to swap with you check the two， you don't need to swap you check the three。

 you don't need to swap， but you need to go throughout the element in the array right so that's one linear pass so in the best case your run time for insertion sort is gonna to be big theta of n all right。

So moving on to selection So， I personally think that selection to sort is the most intuitive of all the sorts that we see over here。

😊，But selections are find the smallest remaining element in the unsorted portion of the list at each time step and swaps it into the correct position。

 So what this is going do is given this list of 3，5，1，2。

 and4 we're going to make a linear scan through our entire array that hasn't already been sorted and look for the minimum element so we're going to look look look look look oh we see that one is the minimum element in our entire array and let's pop that into the front of our array and how we do that is we're going to swap these two elements we're we know that because we haven't sorted anything so far the smallest element that we see next should be in position zero of our array so when we swap these it looks like this and I'm going to draw a bar here to represent that we've already sorted index zero of our array we already found the smallest element right so when we want to look for the next smallest element to go in position one of our array we only need to consider these remaining four numbers so I'm going to do the same thing again I'm going scan through。

These four numbers of five， through two， and four， I'm going to see that the two is the next smallest number。

And so I'm going to pop in to。To its rightful position in index one and what that's going to look like is with a swap。

 right？And I'm going to put two here draw bar to represent that we've already sorted that part。

And it's going to look like three， five， and four。Next up。

 we know that the first two elements in index 0 and one respectively have already been sorted with respect to the rest of the list right so we only need to look for the next smallest element in the remaining three numbers so these are three。

5 and4 we'll see that the next smallest number out of all these is a three three is already in its correct place。

 let's move on。Oops， let me draw that in red actually。

And we're going to do the same thing for the rest of our list。

 We're going to see that four is the smallest number of the remaining numbers。

 We're to swap it into its right place。And trivially at the end，5 is the only one left。

 so that's how we get our sorted list， okay？Now you'll notice over here that selection sort has a runtime that is not big oh it's big theta。

 which means it's consistent。 it runs every single time you run selection sort in n squared time and the reason for this is that unlike insertion sort like the one we just saw above or you were doing swaps there is no like best difference between the best and the worst case so in insertion sort in the best case we did zero swaps right where we see that the list is already sorted and we just go bam in selection sort we don't have that luxury in selection sort we have to go through every single index it doesn't matter if every element is already in its correct sorted position right because we don't know that we just need to scan the entire array to find the minimum value every single time so when we scan the entire array for the first time for the minimum value that's n work right then when we scan the remaining parts of the array that are not the minimum value it's n minus one work then M-2 work M2 work so on and so forth until we only do one work and when we sum that all together remember our summation formulas。

One plus two plus three plus all the way up to n or in this case it's going to be like n minus one right or actually in this case it would be n it would be n yeah。

And it's an arithmetic sum and remember arithmetic sums sum to the last number in the sequence。

 right the largest number of the sequence squared。And that's how we get the runtime for selection sort。

 okay？All right。No。Moving on to merge sort。 So merge sort is one。

 So we just talked about insertion and selection sort。

 And these are two sorts that I think are fairly intuitive to program because they tend to be like in place。

Actually， both yeah both of them are in place we'll talk a little bit about what that means in a second。

 but basically they're a little bit more intuitive because they don't really require you to call like a separate function whereas the next couple of sorts we'll see will probably require you to have like a helper function especially like recursion right so merge sort in particular is recursive in nature so merge sort splits the list in half applies merge sort to each half and then merges that two havealves together in a zipper fashion so what we mean by that is。

😊，Given this list of three，5， one， two and four， lets split let's split it like this just arbitrarily right we have an odd number of elements and basically what this is going to look like。

Is we're going to oops。Split it into three， five， and one， and two， and four。

And these this two element list。And this three element lists are going to split in half again。

 so we're going to get something like this。And let's just say it goes with the left element if we have to break ties。

So。I'm going to split this 351 into  three5 and one。Okay。

 so when we do merge sort we have this kind of recursive pattern where we keep breaking down。

 keep breaking down where the base case is there's only one thing in your list right because if there's only one thing in your list then your list is already trivially sorted right there's no need to sort a one element list。

 So what's gonna happen when you do merge sort is once you get to these one element lists when they go back up the recursive stuck to the point where they split off it's going to try to order these numbers in a zipper fashion So it's going to see that I have a three and a five and I'm going to try to merge these two list together be like okay。

 I see that the three is less than the5 so three should go in front of the five lucky for us it's already been sorted right here right so you don't need to worry about that and over here in the 351 block。

 we see that the one trivially is already sorted right so what's going to happen when we try to zipper the three。

5 and the one back together because we know that this three5 has already been sorted and the one is trivially already sorted。

Is we're going start at the front of both lists so the one and the three and see which one is smaller and which everyone one is smaller let's put that one into the list first and advance the like pointer in that list to the next element in that list or something so basically when we zipper these lists together it's going to look like we'll see this one so we'll see this one compared to the three and we'll be like okay one comes first right then next after we like move on the pointer from the list of one there's nothing left in the list of one so we can just kind of tack on the three in the five here because we know there's nothing else to compare after the one right。

Similarly over here， we're going to get down to our base cases with the two and the four。

 we're going to come up here and try to merge the two and the four the zipper fashion luckily for us two and four are already in sorted order we don't need to touch those you know I'm just going to。

😊，Put all of these in blue， actually。So then when we come back up here to the topmost level of the recursion。

 we have these two lists that we're trying to zipper together right so we're going compare the first elements of both lists。

 we'll see that one is less than two so in our final list we'll put the one first and then we'll kind of like we'll kind of I'm going cross this out we'll be like okay we already saw the one so we know that we already put the one into the list now let's compare this heads of the two list again so now we have a two versus the three the two is the less and the three so we're going to put the two in our list next and then we're going to cross out the two to be like we've already seen the two and so on and so forth we're going to move on compare the remaining heads of the list So a four against the three the three is gonna go next。

We'll cross out the three and then we'll do the same thing with four and5 we'll cross out the four then we'll cross out the five and that's how we get our sorted list from like the zipper fashion Okay so in terms of fronttime merge store is gonna to run consistently in big theta of n log n time there's no way that merge sort can like exit early right because merge sort kind of blindly trusts like or it's not it doesn't trust but like I know like hey I know that if I split down the middle every single time and I split my elements like that like that's going to give me and log n work right and if you think about this it's because if you split the array in half every single time that gives you log n log base two of n but basically log n levels we talk a little bit about this something we're talking about with the height of a binary tree it's the same idea here so you have log n levels and at each level we do n work because of this zipper ring operation right because we need to go through every element in that layer and that's where we get the that's where we get like the n log n。

Work。And run time from， okay。Okay， so let's now talk a little bit about Quicksort which is in my opinion。

 one of the coolest sorting algorithms， this one's really neat because it uses a pretty unique process so Quicksort picks a partition for example。

 the first element， you could pick the first element in your array， the last element in your array。

 the middle element in your array， it doesn't really matter what you choose or it doesn't matter what you choose as the pivot for terms of runtime but we'll talk about that in a little bit but basically it uses horror partitioning to divide the list so that everything greater than the partition AK the pivot is on the right and everything less than the partition is on its left。

So we will talk about QuickSot like a little bit in this discussion。

 but it's more so covered next week because there are like several lectures about QuickSot because it's such a deep topic and so I'm going to talk a little bit about this partitioning scheme here because it's not the only partitioning scheme we can use in QuickSo okay？

So the idea behind Prickar is remember we need to choose a pivot right。

 and in this list over here with the 3，51， two and4 as an example。

 let's just say that the first element is the pivot， okay？Okay， so。

How this works is in horror partitioning is that we want to set up two pointers。

 let's call them L and G just to stay consistent with what Professor Hu uses during lecture and we're going to initialize them to point at the first the leftmost element in the array that is not the pivot and the rightmost element in the array that is not the pivot respectively so L is going to be the leftmost one and G is going to be the rightmost one okay。

And basically what we want them to do is how the algorithm works is we want to walk the pointers to each other until they want to stop and how do we define when they stop well the L pointer likes items that are smaller like strictly smaller than the pivot right so if it's greater than or equal to the pivot it should stop。

The G pointer likes elements that are strictly larger than the pivot so it should stop once it hits something that is less than or equal to the pivot okay and basically we want to walk these pointers together stop on an item they don't like and when both pointers have stopped we want to swap the elements that both of those pointers are pointing that and shift the pointers one step closer to each other each okay and when both pointers cross or're done walking we're done partitioning and we're going to do is we're going to swap the pivot with G okay。

And I'm not gonna get into like the correctness and the nitty gritty of that I will let you chew on that for a little bit It is left as an exercise to the watch。

 but if we were doing horror partitioning on this list because we wanted to run Quick sort。

 we set our L pointer here and our G pointer here and let's take a look at our L pointers our L pointer is going be like okay I see that I'm pointing to a five but I only like items that are strictly less than three my pivot right so I'm not going move I'm stopped here。

😊，Then the G pointer is going to look at four and be like I like items that are strictly greater than my pivot。

 which is three， I see that I'm on a four， this is great。

 I'm going to move on and walk towards the left pointer。😊，So now G is pointing to a two。

 but it's like bo， I don't like two two smaller than three， right。

 I only like elements that are larger than three。 So at this point。

 what we're going to do is we're going to swap the elements。At L N G。

 So the five is going to become a2。 And the two is going to come on a5。

 And we're going to move L N G one step closer to each other。

 So now L N G both point to the same number over here。ok。

So what's going to happen now is once again we're going to try to walk the pointers we're going to try to walk L to the right and G to the left as far as we can。

 so L is going to see that it's on a one great I like ones right one is lesson than three so I'm going move L on to the next number。

And then L is going to see that now it's seeing a five right because we swap the two and a five and L does not like fives because five is greater than three。

 so we're going to stop here。Now G， which was pointing to one。

Let me sc this up a little bit G is pointing to one and G is like wait， one is less than three。

 I don't like this number， so I'm going to stop。And you'll also notice that when。G stops。

 We've also crossed our L and G pointers right and remember that in the horror purchasinging algorithm。

 if at any point we cross our L and G pointers， what do we have to do。

 we need to swap the pivot with G。 So what that's going to look like is we are going to。嗯m。

Swp out the one and the threes so the one is here and the three is here。

 so after one iteration of gra partitioning， we got it。This。Right， so now you'll notice though。

 or yeah， you'll notice that we our original pivot was three， right？

And now three is in the middle of our list in the sense that it nicely separates the elements that are less than it from the elements that are greater than it right the one and the two are strictly to the left of three。

 the5 and the four strictly to the right of G sorry of three but you'll notice that the five and the four they aren't in sorted order themselves right so this is where the recursive part of Quickor comes in so you can kind of think of like okay。

 we just put the pivot in its right place right we know for sure that the pivot is separating the elements that are smaller in it from the elements that are larger than it。

So we can kind of draw a little barrier around here and say hey I know that the three is in the right place。

 I want to run quicksort on the remaining two sublists that are to the left and the right of the pivot and basically when you do that with Quicksort you're going to do the same thing and run horror partitioning on this list of one and two horror partitioning on this list of five and4 until you get like a quick sort list that is nicely sorted in all components and you can all bring it back up to the top recursively and get your nice sorted list okay？

Soum。You'll notice that there's like a bit of like a caveat down here with the runtime of Quicksort So in the average case we say that Quicksort runs in n log n and in the slowest case it'll run in n squared which is dependent on pivot selection and what we mean by this is so in the N log end case this is like the best case well it's also the average case but let's think about it in the best case because I think that's a little bit more intuitive to think about is you know how in merge sort every single time we split the list into two hves it's the same idea here with quicksort if like we choose a pivot such that every single time we run the partitioning I'll grade them like horror partitioning with this pivot we split the list into two nice sublist that are approximately equal in the number of elements then we basically get a case similar to merge sort where we're having every single time right so that's where the N log n runtime comes from as for the n squared runtime that's a little bit trickier but you can think about let's say in this list with Quicksort。

In the original 35124 list， we always chose the minimum value like just somehow right like maybe by accident。

 we always coincidentally chose the minimum value。 So what we would do when we're running the partitioning scheme is we'd see we'd say our pivot is one and you'll notice that everything in the rest of the list the2。

3，4 and5 they end up on the right of the pivot right there's nothing on the left end of pivot So when quicks tries to run recursively on like like the lesser and larger halves of the list it's not really half of the list because you just went from n elements to n minus1 elements that you need to partition right then n minus two elements that you need to partition if you keep choosing like the worst possible pivot to choose right so when you add that work like you do n work in the initial partition and then n minus one work in the next partition n minus2 work in the next one after that you add that up that gives you n squared time okay。

That's why we say it's dependent on pivot selection。

All right so now we move on to our final sort that we're going to cover that's a comparison sort we'll make the distinction next week with the comparison and count sorts give heap sort so heap sort heapifies the array into a max heap and pops off the largest element and appends it to the end until there are no elements left in the heap you can heap aify by syncing in nodes in reverse level order so hopefully this sounds a little bit like familiar like heaps sound a little bit familiar we mostly work with min heaps in the course before right here we have a max heap so the only difference between a min heap and the max heap is that in a max heap every node should be larger than the values of its children right like versus in a min heap which is the ones we are covering earlier it's every node should be smaller than the values of its children right。

And let's define reverse level order， so regular level order。Is BFS？Which is。Top to bottom。

Left to right。And reverse level order would be。Bottom to top。Right to left。

Oops I think I'm running out of space there get right to left Okay。

 so that's how we're going to heify our node So what this is going to look like is if we read this a in level order and we like we treat it as like a heap being read in level order like a binary heap in level order we could draw a heap that looks like this。

😊，But。This isn't really a heap or this isn't really a max heap right there's all sorts of violations all over like a three is less than a five。

 we can't have that in a max heap so what we're going to do is we're going to try to heapify this first。

😡，So。We're going to heap aify from the bottom of the top。

Right to left so we're going to come over here from the bottommost row start at the rightmost position and see the four is the four less than the five which is its parent it is so we know that this relationship fulfills the max he property right。

Then we're going to go over to the two right still in the bottom row we're just moving left。

 we'll see that the two relationship with the five also fulfills the max heat property。

 this is great。😊，Now， when we come up to the next level。We're going to see the one。

 does the one obey the max he property with its parent three， yes it does， one is less than three。

 but we have an issue when we come over to the five because of five。

Does not obey the max heat property when compared to its parent three right so we're going to sync nodes in reverse level order and what we're going to do is we're going to swap these right because we want them to obey the rules。

Of。Of the max heat。So now when we swap the five with the three we're once again met with an issue right because we just swapped the three oops。

 we just swapped the three into this position and we didn't know for sure that it was going to obey the invariance of a max heap and over here we already see that we've run into this problem where three is not larger than four right so we're going to have to do one more sink down。

And what that's going to look like， we're going to swap the three with the four， right。

 because in a max， we want to swap with the larger of the two children in order to preserve that variant。

And this is what the initial heappoification of our array is going to look like， okay？

I'm going to scoot this off to the side really quickly。

I guess I'll just keep it in this corner sorry it's like very small but so now this is like kind of like our starting heap right and then you can kind of think about it like here our heap will look like if we read it off in a level order or bFS right it'll be like54 one2 and three right so now we'll see that after we max heaped this。

嗯。This initial list， will'll see that the five is in the root position， right。

 So what we're going to do is basically。Pop off the five。Add it to the end。

And then we need to reheapify this。Right so what that's going to look like after we do that is remember how we remove from a max heap or like any heap right we swap with the last element。

😊，So we're going to swap。The five and the three right because the three is the lowest element to the right。

 and then we're going to delete the five。And now we need to reheapify our heap right our max heap so we'll see over here that this relationship is fine this relationship is fine。

 but this relationship is not fine right a three is less than a four so we'd have to reheapify what that's going to look like is we're going to swap the three with the four。

And our he is going to look like this because after this we don't need to rehepaify at all right so at this point we have a four as the root node so what we can do is pop it off。

And tack it on to the next element that we haven't already seen Oh actually。Here。

You could do this And either way， I think the way that we typically do it in 6 U N B， though。

 is we'll add it before。We'll add it to like the backmost position in the array that we haven't already filled。

 but I guess you could do it in reverse order and just flip it at the end it doesn't super matter。

 but I think in this class we'll teach it that we'll add the four before the five okay so this will be like the next position that we didn't already fill from the back and we'll just so on and so forth keep repeating this process until we have no nodes left in our heat okay and the runtime of this hopefully you're able to intuit this out when we work with binary heatap especially。

Is that the runtime of heapor is going to be and log n and the reason for that is you have to go through n or in the worst case。

 it's going to be N log n right because you have to go through each of the n nodes right there's no way around it and then the log n comes from like the heappoification process and also what happens like when you delete a node right so that's where the runtime of heapor comes from。

😊，And I believe， oh， nope， it's not。 So this is like the summary of the comparison sorts and。

We talked a little bit about all of。All of like the best in the worst cases here so I'm not gonna to repeat them you can go back in the video and rewind if you'd like to hear me explain them again。

 but let's have a little bit about civilbility so a sort is stable if duplicate values remain in the same relative order after sorting as they were initially in other words is2 a guaranteed to be before2 B after sorting the list2 a2 B and1 okay and over here we have2 a and 2B to just for our purposes so we can distinguish the fact that they're both the number two but we're just going mark them with A and B just so we know which order they're in so the idea is like if we ran each of these sorts on this like list as an example guaranteed to give us two2 a and 2 B in that order consecutively。

So in this table over here we see that in selection sort it's not stable insertion sort and merge store R and quick sort and heap sort are not stable。

 so the primary reason for this is。😊，I think this is more like an intuitionbased thing what we can talk about it a little bit more in depth is that when we run something like selection sort QuickSo and Heap sort。

 we are not necessarily swapping consecutive values in our array right so in selection sort remember that we just take the minimum value we find and we swap it into the position that like the next position that hasn't already been sorted in the beginning right so in that process let's say like the minimum value we found was at the end of the list when we initially ran selection sort and we'd be swapping the last element in the list with the first element in our list right so。

Like we'll see in this example in a little bit why that's not stable insertion sort and merge store on the other hand。

 like insertion sort， we only swap backwards one at a time right we don't swap like across two or three numbers at a time it goes incrementally we have to go one in at a time and keep checking and if we see something that is greater than or equal to sorry less than or equal to the value that we're trying to swap over then we don't swap it at all right and that's how we preserve that ordering likewise for merge sort your zippering numbers together so there's nothing really to make like a deeper comparison of kind of so we can say that merge sort is stable because like there isn't a point where you're like actually swapping over numbers right they're all going sequentially。

So quicksort and heap sort like selection sort like quick sort for example。

 we saw with the horror partitioning was that like you were literally like switching like your left and right pointers or yeah your left and right pointers when they stopped during the partition right so that had didn't guarantee that you were only swapping like consecutive numbers that were like explicitly larger or less than each other right likewise with heap sort remember if we think of heapS as an underlying array when we swap up to the parent the relationships between parent or and child are often separated or in a heap that must be separated by some constant factor in a binary heap like if you want to get the left child of a note it's like two times whatever index the parent note is at right so there's like there's like a bit of like complication with like selection quick sort and heap sort individually because you're not guaranteeing that like。

re going to be able to preserve the order so as an example of this let's run selection sort on this list so remember that selection sort scans the entire list finds some minimum value in the list that hasn't already been sorted and then pops that into the first element of the list right so if a sort were stable a stable oops。

😊，A sable sort should produce1，2， A，2 B。Right because that would preserve the relative ordering of the twos over here and again we only mark them with and B just to make sure that we were able to tell the difference here So if we had a stable sort it would do this。

 but in selection sort what's going to happen is we're going to scan this list we're going to see that the minimum value is a1 right and we're going to swap the one with the2a over here because this2 a is in position zero we haven't already sorted position zero so after we swap that with selection sort。

We're going to get a list that looks like1，2 B。To a and in the eyes of the computer。

 this is per this is sorted right， like we're done。 it's a one a two and a two。

 but we'll see that it did not preserve the relative ordering。

Of it did not preserve the relative ordering of like the twos over here because2 B ended up in front of2 a right and you might be wondering like why do we even care about whether or not something is stable right so this has like a lot of applications when you're running sorting algorithms in the real world so like let's say we're trying to we're trying to。

St people alphabetically but also by like a score that they get or something like that if you want to sort people alphabetically but also by score。

 they need to preserve that initial alphabetical order and then sort by score right and if your sort was not stable and you can't guarantee that like they get assessed correctly like that right and one more thing that we're going to talk about more in the worksheet but I'll briefly touch upon it now is this idea of a sort being in place and so what it means to be in place everyone has a little bit of different definitions of for this but in6 UB will consider a sort in place if。

😊，If it the total amount of extra space it takes is less than logarithmic。

 but basically it means like do you need an extra array to do this sorting algorithm and if it is then it's not in place Okay that that's kind of it all and that's it for a content review。



![](img/217bc4b16db93545037d4292247b09d4_4.png)