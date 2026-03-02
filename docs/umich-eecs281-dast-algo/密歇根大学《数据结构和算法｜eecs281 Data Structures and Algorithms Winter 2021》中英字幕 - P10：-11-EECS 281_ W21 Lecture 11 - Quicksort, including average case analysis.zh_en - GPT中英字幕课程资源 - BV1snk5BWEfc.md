# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P10：-11-EECS 281_ W21 Lecture 11 - Quicksort, including average case analysis.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

![](img/bfa1f1329a6c16454fc58a8203b2d51b_0.png)

Right。It's noon quick My check。🎼1，2，1，2。🎼Anybodyが。Is there anybody？🎼你也回家。Hhs up on the chat。

While I go fetch some water， I'll be right back。All right， we can hear you。All right。

So I think we're good on video and sound。Let's give it another minute。folksolk to join。Um， yeah。

 we could actually also talk about the quote， I think this is the same quote that I had last time。

Which I forgot to address the quote just one second let me stop the music， okay， Google stop。啊。

So another one of my favorite quotes， it from Richard Feynman， very famous physicist， Nobel Laureate。

The first principle is that you must not fool yourself and you are the easiest person to fool。

 and I like that quote because it's very relevant to debugging。So。

We often get at office hours where we're trying to。

Make suggestions as to what a potential issue or source of the bug would be。

 and often students would be like no， that can't be it because I know that should work。A。

Lo and behold， after further debugging。A lot of the assumptions that and this is not limited to students。

 this is everybody that does programming， any assumptions that you had about parts of the code working。

嗯。If it's not tested enough。Can be a fallacy right they can be like stuff that you assume what's working correctly lo and behold it is not or doesn't really work as you were expecting given a new particular context or I don't know。

 context being like different inputs or your algorithm doing something different。All right。

 let's formally start with the material today's lecture， the formal title should be quick sort are。

We are a little behind in terms of the schedule I talked about this last time。

 but no worries will definitely catch up by Thursday。Usually the ME sort lecture is not long at all。

 so we can catch up there， so today we'll basically then focus where we left off in the previous lecture which was insertion sort and actually I forgot to list it there on the left hand side of the video we're also talking about counting sort。

And then we'll start Quicksort and we'll finish off quicksort and do all of Mer sort on Thursday。

Okay， and so before I continue with insertion sort， since we cover most of the elementary sorts。

 it's good to kind of there is this visual algo。net site that encourage you to visit it's you know it's a really nice way to visualize each one of the algorithms and how they behave I mean it's nice to visualize because that's what it's supposed to do so it actually gives you also a pseudocode and。

Basically highlights the steps that are executing in the pseudo code as it's making the arrangements in the array that you're seeing there right so for example。

 right now we have bubble sort selected and if I click down here to sort。

You can actually compute the inversion index， which I'll talk about what that means。

 but for now we're going to leave it unchecked and I'll let you try it out on your own by checking it because I don't think we'll get to。

 but we will get to what is the inversion index。Allright， so that's the pseudocode for bubble sort。

 which you can see it's a little bit different than what we gave you in terms of code for bubble sort。

 but it basically shows it up quite nicely however everything is working I believe in the code that we gave you the two indices that are moving along there actually one should be starting at the end and it's moving along all the way down whereas here both indices for the outer and inner loop are starting from the left that's basically but the concept is effectively the same it also the outer loop here is' a while loop or as opposed to a for loop I like a for loop better but you can see that this is taking advantage of this is the adaptive bubble sort if you recall because it has that boolean that detect whether there was a swap or not。

嗯。And you can see it's fairly fairly slow algorithm and you can see that it's doing way more comparisons that you would potentially need let's look at how selection sort works。

Again， you can bring up。The pseudo code， then click sort boom。mAnd。

You can see the way that it's behaving it's basically starting and now it's looking at the second position and it's finding the min。

 it had found that five was the min then it updated to three and that was it once it's found its min for the second position。

 then it swaps it right there right so it found its for now swap it back to that third position in the array so on and so forth。

So it's really nice that as it's doing things it's really highlighting the pseudocode so a good exercise would be to match this pseudocode that you have or you're visualizing with the pal things would be happening in the code that we gave you。

And so， you know， I'll let you run through the rest of that and then we have insertion sort。Bong。



![](img/bfa1f1329a6c16454fc58a8203b2d51b_2.png)

Click on sort。And then go。And you can see with insertion sort。

 all the updates are happening in the left hand side of the array。That is already sorted。

 It's the section of the array that's already sorted。 right， it highlights red。

 the new element that I'm looking to move to its rightful position on distort sorted section of the array。

 right， which is。Quite different from how selection sort works。Boom。

 and there's a pseudo code for it and now we'll go back to the code that we have for insertion sort and actually see what type of improvements we can make to the insertion sort algorithm。

Talk a little bit about。When the algorithm， when assorting algorithm is good to use。

 so there are instances in which you'd want to use selection sort over the other elementary sorts。

 and then there's other choices where you want to go with insertion sort over all the other elementary sort。

 basically we never really rely on bubble sort at all for elementary sorts。

 we could use either selection or insertion sort。Those are remains。Choice is there。All right。

 so let's go back to slides。Here。Bong。Okay， and I'll just let me zoom in a little bit。Oops。

 all right。Software is a little bit quirky。All right， that's just good。That's soon as I can get。

 all right， this was the code for insertion sort that we had last time。I covered it last time。

 so I won't go into too many details right now， as the visualizations showed。

 you're basically picking one of the next element or more precisely the right sorry the leftmost element in the unsorted section of the array。

Um， pickick that one and see where to place it in theum sorted section of the array。So that's。

In general， what it does， let's look at how we can improve。Insertion sort。For one thing。Well。

 actually， I won't go since we visualized， I won't go over the example in detail。

But here we have our input 4，251，3， it would be that the onsorted section right here would be just the four and then so we would look at the two and say where to place it in the unsorted section which at this point is just four and then perform the swap right so that's the swap right here and then we would look at the five。

 determine where we should place it in the sorted part sorted section of the array。

 but then determine that it happens to be in it's right for place， no need to swap。Then look at one。

 say where should it be in my sortex section of the array and it would be swapping all the way down to the first position down here。

 so on and so forth。We spoke about the analysis。4 insertion sort which was still an n squared algorithm。

 both in terms of comparison swaps on the average case it's a little bit better in terms of swaps。

 but again it's a constant factor asymptotically it's all n squared。

And so far this current implementation is only slightly sensitive to the input。

 right so let's look at potential improvements that we can do。嗯。😊，So。Here。

 let's just get right into it。Move versus swap， Okay。

 So if you notice the algorithm is relying on swaps， basically it kind of。

It comes from a bubble sort if you if you look at the code bubble sort versus insertion。

 so a little bit， they're similar。And the big advantage of insertion is that you don't have to rely on swap。

 you can actually just use a move right so all you'd be doing is instead of continuing to swap all the way down。

 you'd basically just shift things along right so we're getting rid of this we don't really need to swap all the way down all we need to do。

AsYou know， assuming that we know the J that is here is declared inside。Of the inner loop。

 it's now a declaration that's part of the outer loop right here， right。

 so that's the declaration of J。Um， and we need it so that it the scope of it。

 it exists outside of the inner loop so that I can make the proper assignment of the value right there。

So this change is just basically， let's not have to do swaps， lets you a direct move。

 largely because I can'。There's really no need to use a swap and in fact。

 the visualization that we saw earlier。Did use a move rather than swaps all the way down if youd take a look at it。

 So that's our first improvement kind of straightforward what we would want to do。

Second improvement would be， well， inter loop can just be a wow， right， there's really no need。

To make it a for loop， it can just be a while and then that way inside of the inner loop。

 there's no need to check this to have this if right because。

We basically are going to continue moving。The element to the left。

 which is what line five is accomplishing as long as the constraint is met。

 that the value that you're looking at is still less than than the element to the left。

Okay so if that's the case， then you continue shifting once you found out that V， okay。

 which V is what you know， the element。For the IF element in the array where I is the。

Co in position that you're looking at。Because it's the index of the outer loop。

Once you've determined that V is greater than then there's no need to continue shifting right and you basically reached you now know the point at which you need to place V。

 which would have been given by J because J was basically keeping track of all the elements that you had been shifting。

So when you can no longer shift， you just place it there okay so that's。Another improvement。this one。

 there's no particular performance improvement， this is just really。

 it's nicer to look at if it's a while loop。And also because。

It's going to facilitate the next improvement if we turn it into a while loop okay and this next improvement is the fact that if you look at the condition for the while loop。

 you'll see that the condition that J is greater than left。Okay。

 which you need to check just so you know your inner loop is not going out of bounds in the array。

 right that's the purpose of checking whether J is greater than left。Okay， that's its only purpose。

This means that this test， right， if its only purpose is to just check that J does not go outer bounds on the left hand side。

It's going to be seldom false， right most of the time it's going to be true rather than false。

So basically， can I get rid of this particular check inside of the condition for my Wily。

 and that is what we can do if we ensure that the first elements。

In the array is the min for the entire array？Then we can be sure。

That we don't need to check whether J goes out of bound on the left hand side。It should not happen。

 provided again that I am sure that the first element of the array is in its rifle position I've found whatever the min is of the entire array。

 placed it in my first position， and then I could say， well。

 there's then no need for me to check whether J is greater than left。

Because it's going it's always going to be so。Right？

So that's our next improvement is or their third improvement would be that hey。

 let's just compute the min of the entire array， that's what that does right there。

 shift it to the first position and we're going to call this value now our sententinel value because the placement of that value allows us to get rid of this check right here in the inner loop。

And that's。It's the whole purpose and furthermore， this placing of the first elements of the array。

Okay。😊，嗯。It's using swaps you can actually make them。Well， let me jump right into it。

 you can actually make that a move rather than a swap。Oops， I thought we had code for that。

 but if not。You could potentially write this code using a move rather than a swap。

 but here in the code that we have on the slide is just making swaps all the way down。诶。

So once I place that Sentinel value right there， then I can remove this check and notice that because I've basically found my min for the entire array。

 and I've placed it at the first position， then I need to start the inner loop as of left plus2。Okay。

Because now this basically accounts for what would be my first iteration of that outer loop。Allright。

 so let's look at how this would work。 Well， let's say given the same input， I have 4，2，5，1，3。

 that's our input。 Well， first， just find them in in there， which would be one right。

 and that would place it right here。 So at that point， I am done with this code right once。

Once I have placed that sententinel value。In the first。Position of the array。

I'm done with this section of the code and now I go about my business for my insertion sort。

 which would be assuming this is my sorted section。

 I again would look at four and see where would need to be placed in my sorted section and which would means that it stays there because you four is greater than one then again expand to look at two and see where that would be placed in my sorted section so I would move it to place it here。

So that's first pass and then so on so forth as a previous example and by past three we would have。

Our sorted output。All right， so so far， we really haven't made any big。Performance。

Before we did the third improvement， we hadn't made any big performance improvements。

But now with this third improvement。We basically get to the point where in the best case situation。

 we can get a linear time in terms of comparisons for insertion sort。嗯。

Both worst case and average case in terms of asymptotic complexity is still the same and squared。

 this is elementary algorithm。 There's no way that we're going to。Make it better than n squared。

And now it is an adaptive insertion sort algorithm。

Oh wait let me I just saw a quick question Soya is asking why is a move better than a swap think about the code that would go into the swap function right a swapwab will have to create a temporary variable。

 store it there then perform the actual updates that would accomplish the swap get rid of the temporary variable right that's on each swap so a move is just a plain copying of element elements throughout to do the shifting and then just one more copy to place the element where it should be okay。

So you can see that's definitely more operations if you're doing swaps all along rather than just a move okay because each swapwa has multiple copies if you look at the swap code。

 actually last lecture， we went over a code for the swap function and you see that there's at least three operations in there。

 whereas a move will just have one copy for each shift as opposed to one swap for each shift。

All right， so。Avantages of adaptive insertion sort， more efficient data manipulation。

 so because we're moving， it actually goes to the question that was asked right。

 we're moving rather than swaps is you know one third of the work of a swap because here you go。

 there's at least three statements in a swap。There's fewer comparisons。

Use only when a key is smaller than a key of item being inserted， right， that's you know。

 if you look at the code， that's basically what we're doing。Then the finding of the Sentinel。

 it is the smallest key， of course it's the smallest key if we're sorting acending order。

It would be the opposite if we're sorting the sendinging order。嗯。

So there is an overhead for you know， actually finding the Sinel and placing it。

 but it's no worse than what we had before。So I'd rather invest the time。

To place that Sinel so I can make my comparison in the inner loop。the inner while loop。

 much simpler okay and those are the sort of tradeoffs that you often do with algorithms。

 right this is sorting， which is a rather simple problem So it seems like a very kind of trivial optimization。

 if you will， but it is nonetheless an example of what can happen with you know much larger algorithms。

 And you notice that we got here right we didn't we didn't get to this point by immediately jumping from like let's implement insertion sort and get to the most efficient version of insertion sort immediately。

 No， we kind of implemented insertion sort in its more straightforward fashion and then the iterative improvements to get to a more efficient version And that's in general what you have to do with algorithms both in academia and in industry And in fact。

 if。I've seen you at office hours， I've often mentioned like don't be afraid to have to rewrite your project or lab code。

 okay， in fact， out in industry， if I had to guess we're probably rewriting code 80% of the time。

Okay， we're always searching for better ways to do the same thing。Okay。

 so that means it's rewriting the code so in general。

 avoid trying to get too slumped down with like how to jump immediately into the most efficient version of your code because you know。

It's better to just write an initial version， it might not be the best or most efficient version。

 but it gets you submit to the auto radar faster， and then you can iterate and improve。Okay。

 so it's still an S grade algorithm， we haven't changed that it's still nested for loops each run running and。

Running an total n squared time。诶。ItIt's a stable rhythm。

 which if you recall our definition for stability。Sometimes desire that。

So that is particularly key if you're looking for a stable sorting algorithm insert search and sort works。

Remember that compares that's in contrast to selection sort， which was not stable， it is not stable。

 we talked about that last time， go back and check why selection sort is not stable but insertion sort is okay。

嗯。😊，And it turns out it is kind of the best sort to use and this is。

Even if we consider the most efficient sorts。Um，If。The size of N。

Or the size of the array that you're looking to sort。It's rather small。

What is small here is very relative， right， it kind of depends on。You know。

 kind of even the architecture that you have， what you would consider to be generally， it's like。

If it has less than。32 elements。Kind of a word size。

But it's really open to interpretation what we would consider small。But if it's small enough。

 you might you can fold back to insertion sort because it can't。Execute quite fast。

Practically on small values of N， asymptotically speaking is still an n squared algorithm。All right。

 so elementary sorts are quadratic time， for the most part in on worst in average cases。嗯。

This is assuming that the inputs are uniformly distributed right we've made no assumptions about the distribution of the input other than。

You know， it's uniformly distributed， right？So。If we。

If you've got a particular situation in which you're trying to use a sorting algorithm。

And your input array follows some specific distribution。诶。

Maybe you can come up with your own custom sorting algorithm for those specific types of distribution。

 I doubt it would be any sort of。I mean， I'm sure it won't be any sort of asymptotic improvements。

 but maybe for your particular problem， it would work rather fast。对。

So we've always been analyzing number of comparisons specifically。

 and then we've also looked at number of swaps that were needed。They're not the same thing， right。

 make sure to go back and note the difference between。

Counting number of comparisons versus counting the number of swaps。

Oftentimes they end up being on the same order of magnitude， right if it's n squared comparisons。

For some of the algorithms that we saw， it was also n square swabs， but it need not be so right。

 you can have so for example， insertion sort， you'd have。And squared number of comparisons。

 but it could end up doing。On the order of N swaps again， but it has to be under their specific。

Input conditions。All right， so let's look now at what we have been describing as。

Somewhat sorted or close to sorted。Okay， I promise that I would show you a more precise definition for what we meant by that。

嗯。And that metric is called inversion。Okay， so if you have it's a single inversion would be a pair keys in the array that are out of order。

诶。So think about this if you had an array and in the array only its always has to be pairs right if they're in incorrect positions。

 so if you had all sorted array except for so here's an example right if I won， three。😡，5。For six。

 right， let's say this was my array， this， the number of inversions。It's just one， right。

 because it's just a four and the five that are inverted， right， which are out of order。

So that's inversion。And it turns out that with this definition of an inversion。

You can actually for an array， just compute。😡，Count how many inversions it would take。

To make the array sort， sorted。诶。Um so。You would do for each item。

 you can determine the number of inversions， number of items to the left that are greater。Okay， so。

Each item。Should be fairly easy to determine。How many inversions？嗯。Would be needed。

To place that element in its correct position。And then for each array， which is the input。

You can determine the total number in versions。😡，To get you to a point where the output array is sorted。

And this gives you a sense of presortness。Okay。And what that allows you to do is to pick what would be the best。

Sohort algorithm to use based on this particular metric。And of course， you might be thinking well。

 but isn't that when that require compute time to figure out this metric， yes。

 but you can do it in linear time， you can compute this metric in linear time。

 it'd be a nice exercise for you to do。那们。So try and do that。

 how would you compute this metric in linear time and oftentimes if your array is large enough。

 you'd rather invest that linear time to get the value for this metric so that you can make a better decision with your sorting。

Think about it if I spend linear time。Compute the metric， determine based on the metric like， oh。

 I should just use insertion sort because if it's insertion sort。

 this metric tells me that insertion sort would behave in linear time。

 which means that I would complete my entire sorting in linear time， rather than n log n。

 which if you recall even efficient sorts， take at least n log N。All right， so let's talk about that。

 let's say that we have the property。Here is a property for insertion and bubble sort。嗯。

Based on the definition of inversion， I can say that formally。Insertion and bubble sort。

Are going to take linear number of comparisons and swaps。For data， we're the constant upper limit。

In the number of inversions。嗯。So let me let me rephrase that there is a constant limit for the number of inversions for each element right so it means that if on this metric。

嗯。I only a few slots away。For each element to reach its correct position。And few。

 it's kind of another term for saying like there is a constant upper limit on the number of inversions that are needed。

 right， It's just fancy terms for saying like， I only need a few。Um。

Inversions to getum the element where its rightful place， if that's the case。

 if I can ensure that's the case。诶。Then I can be sure that insertion sort。

 even though it's an n squared algorithm。Will behave in linear time。

So that's kind of the interpretation that we have down here right it's actually also true for bubble sort。

 but again， we don't ever really use bubble sort so the main importance here is for insertion sort。

 but it is also true for bubble sort。They are efficient on partially sorted data when each item is close to its final position。

诶。All right， let's look at this other property， insertion sort uses a linear number of comparisons and swaps for data with a constant number of elements having more than a constant number of inversions。

So I。e。 a small number of elements are very far from their location。Um， so it is and if you're like。

 well， what's the difference from what we're saying here in what we said in the previous slide， okay。

um it's， it's a little bit of warwarsmithing。But if you look at it。

 it's kind of the flip coin of the previous property， okay， the previous property was saying like。

I'm kind of saying that there's only a few inversions to get any element to its rightful position。

Here is saying the flip side of cone I've only detected。That a few items will need a lot。

Of inversions to get them to their rightful position， right？

So they basically are kind of measuring the same thing。

 which is kind of why the wording is very close， but from a different point of view。Okay嗯。So。

The idea， what this entails is that for insertion sort。

 and notice that this part of it is not necessarily true for bubble sort。Okay。

Is quite efficient on sorted data when a new item is added to the sorted data。😡，Okay。

 so to show you an example， let's say that in project。In project。Two。

 where you're implementing the sorted PQ。It you're maintaining the array at all times in sorted order。

Okay。嗯。And then at maybe what you do is say like and this would be out of the context of Project two。

 but let's say that's similarly you're writing code to keep an array sorted at all times。😡。

Okayay similar to what we had to do for Project two。But then in your particular context。

 you might say like， all right， so if I have to insert a couple of elements。呃。

I can do that without immediately sorting the array。

And that way I'm sure that I'm bounding the number of elements that would be out of order。

 right because if I'm just inserting anywhere in the array。

 which presumably would be the last slot in the array， to make it a constant time operation。啊。😊。

Then only a few elements might be out of place。And so if I have this particular heart constraint where I say like。

 I can。Insert only up to five elements。That will take constant time to insert because I'm placing them anywhere。

Then once I reached that limit， I would have to call on insertion sort。

To make sure to resort the entire array。And that would be a linear time operation for insertion sort。

Because of this particular property that we' highlight in here。

So that and that's actually often used in practice， right。

 maintaining a sorted array for your data is used quite heavily in practice。😡，For example。

 when you're using it for project two for implementing a priority queue， but in other contexts。

 it does come up that you have to maintain a sorted array at all times and then。

You have insertions into the array， but you don't want to have to spend so much time after every insert to maintain the sorted array。

 so you just say like all right， the first up to five times I don't care if the array would be kind of in a dirty state right because even though we're supposed to maintain an inserted order。

 there are a few elements that might be out of place。😡，And it might be okay to do that， and if it is。

 then you get a lot of advantages because you can then pass the array to insertion sort and it will behave quite fast。

All right， so here's another one selection sort runs in linear time for data with large items and small keys Okay。

 so if you。嗯。Go back to our previous lecture where we're talking about。

The types of sorting algorithms we had in place， outplay， which is related to memory。

And then we also had the type of sorting algorithm you would really be only sorting the keys。

 not necessarily the data itself， okay？And in that situation。

 selection sort is fairly good because if you recall， a selection sort would really。

Only move or copy what needs to be moved and it does it only once and never again。Okay。

 if you recall selection sort in terms of number of copies that it needed to do or swaps。

 it was linear time。Okay so you need to when your constraint is that it is hard to shift data around。

Selection sort might be ideal in those situations。So there you go。

 so if you thought that you know elementary sorts were useless and you would never want to use them。

 there's particular situations for your work。They're actually quite useful。All right， so in summary。

 elementary sort and squared algorithms in terms of。Asymptotic complexity。

We've discussed bubble sort， selection sort， insertion sort， each one of them。

 we've discussed adaptive versus not adaptive。There is a link there。That's a different。

 I think that's also a visualization tool for the algorithms， I like visual I'llgo better。

 but that's one that you can rely on as well。嗯。And so now we're going to look at a count sort。

 which will save you this expense is linear time。Okay， I're like， oh my God， wait。

 why if we have a linear time elementary sorting algorithm？Why do we even have efficient？

Sorting algorithms， well， it's because they're linear time， but they're very restricted in when。

 when and where they can be used。Okay， and we'll talk about that and you'll see why in the next few slides。

And so this is an example of a sorting algorithm that does behave much faster than even efficient sorts if you know for special cases right and we will talk about what that special case is all right so that's counting sort here is an example of when you would want to use counting sort suppose that you're trying to sort。

All these characters right here。嗯。In general， counting sort is good for when you're sorting and there's a limited number of different or unique keys that you're looking to sort。

Okay， so here's the example， you have a bunch of characters there， let's say they're in the array。

But if you count the number of unique characters in there。

 there's what there's then we just have to count the colors here， one， two， three， four，5，6， six。

 I think thinks is the number of unique keys based on the colors that we have。

So if your particular context。For sorting。Is in this matter similar to this。

Then you can rely on counting sort and get away with a linear time sorting algorithm。

But I'll also save you the suspense。It is a linear space。Requirement algorithm， which is also set。

Which now you see why it's like， oh， why are we not talking more about counting sort？Well， again。

 because it's quite limited in when and how you can use it。All right。

 so the way this algorithm it generally uses three passes。

 there's again multiple ways to implement this， but it'ss fairly known that you would want to do。

Three passes， the first pass would be about counting okay。

 basically all that you would do is and this is where the extra array would be needed， again。

 linear space requirement。You will need an extra array array in the size of the number of unique keys that will store。

The frequency of each key。Okay， so if you see here， there's only one of the dark blue right here。

 which is the a， there is two of the green， which is the B's。

 there is only one of the black and so on and so forth Okay so that's the first pass is to compute that array frequency array then the second pass is to based on those frequencies。

I can compute the offsets。Of each element。As they should be in the output array。诶。

So that's the second pass is compute offset where each key would start in sorted order， Okay。

 so that would mean here in this example that well if you know。

Our comparator would just be based on alpha numeric comparison， so the dark blue。

 which is just the A， right， we'll start at the very first position。And the output'll a array。

And then there's only one of them， so that means that the next section of elements which would be the be's should start at one and that's my offset right so should start at one and then I would say like well there's two of the greens so my next offset okay and I know that because of the output of the first pass I know there's two of the greens so the next offset should start at three and so on and so forth。

😡，And then after I've done all of that， then the third path is just copying。Okay。

 everything into the output container。Okay， and this is where the main kind of。Or then space。对。

Would creep up。All right， so let's see how this would work in a very nifty animation。

 there's your example array and。What we would do is first compute all the frequencies。Okay。

 so they all started zero， my first pass would be I'm going to count all the elements， boom。

 boom boom。All right， first pass none。Okay， now that I'm done with the first pass。

 I continue on with the second pass， which again is based on the output of this first pass。

Which would mean that based on these frequencies， I can just establish what the offsets are for each position of the elements in the array。

In the output。To be quite clear， once I've computed those offsets， which are like the you know。

 coloring here。Then I could just go ahead and copy what。Everything。Okay， based on those offsets。

 right？And那び done。So， very nifty animation right there。嗯。All right。

 so let's look at the fact that counting sort， even though it， you know seems。Quite straightforward。

嗯。Why would't we always use it well， well because it can only really be used？

When the number of keys is limited。哎。And presumably small。Okay。

 and this is the number of unique keys， right， So this should he in the number of。Unique。

That's supposed to be a queue。Unique keys。I's limited。Okay， so examples of this would be， oh。

 if I'm sorting by a birthday。Right， number of possible birthday， it's really small。

 it's just like 366 or you know。嗯。Maybe I'm sorting by class standings， right， which is， you know。

 maybe just it's accountable， small size。Okay， and then you might say like， well， I'll just。

 you know， declare my。You know， frequency counting。Aray to be of int Max。Okay。😊，啊。

And then be done with it and no don't do that it's you know， it's not reliable again。

 you should have heart constraint and make sure that the number of unique keys is。

Comparably small right， and of course， again， similar to what I was alluding to earlier when we were discussing。

嗯。I don't remember what we're discussing， but it's actually architecture relevant right what you consider small you know。

 if you have a supercomputer then small is different than if you're running things in a laptop okay。

So that's why you shouldn't really rely on something like it Max。

 which itself would change depending on the architecture that you're using， okay？😡。

So for 64 bit computers， it's quite different than if you had， I mean。

 there's not that many 32 bit computers anymore。There's definitely 128 bit。Computers。

I'm just kidding there isn't really right now， maybe some supercomputer is 1208 bit。

But I'm sure in the future we， I mean， it's not really needed right now。

 but maybe in the future we'll get to 120。128 bit computer。But the point is。

 make sure that the context in which you're using counting sort is where there's unique keys of relatively small size。

嗯。Here's sample code。For you to， this is a first pass right here， second pass and third pass。Okay。😊。

Notice the need to use a swap right here。This is an SDL swap。嗯。To make sure that the input array。

 which is just students will contain。The actual output that was stored in work copy。

So I'll let you run through this code。And play around with it。

 should copy and paste it and then run it。嗯。So that is counting sort， it's very。

 very similar to Rad sort。We'll let you kind of research the details of Rad sort。

 it's a bit more complex than counting sort， but the principle is the same。Okay，The space complexity。

 as I mentioned， is actually to be more precise， is n plus k right， where n is the size of the array。

And then K is number of unique。Cez， but。嗯。Because it's always assumed that K is much。

 much smaller than n， this usually boils down to say over。

But it is more precise to say that the actual space and runtime constraints are。Oban。Okay。Sorry。

 it's more precise to say it's O N plus K， but usually we just say O because。Tay is much larger than。

 much smaller than。All right， and so that is counting sort and a bit on the usage of STL sort。

You probably have， if you started Project two， you're at least part B of project two where you're implementing。

 again， the sorted PQ， then you might， well， if you're not， you should be using the SDL sort。嗯。

So it takes on at least two parameters for the beginning and iterators that of the range that you're looking to sort。

Okay， the third parameter would be a funter。Which is what you're using to compare the elements in the urine。

Or the vector。呃。So it is the funter that determines the sorted order， so for example。

 if you had parameters A and B for ascending sort， your funter should return true if a is indeed D less than B。

 for descending order it would be the other way around。

 so it depends which direction you want to sort your array it's all driven。

Whether it's ascending or descends is driven by the functer， right similar in Project two。

 you need if you have funs。And you need your priority queue to behave as a sth。

 then you'd have a sitth puncture， and then if you need to priority queue to behave or Jedi。

I guess Jedi because that's plural， then you have a specific function for that。All right。

 so let me pause here， see if there are any open questions， thank you to staff that are on the chat。

嗯。嗯。嗯。Zhu。How good question how is counting sort stable if you look back at the code， right。

 let me go back。Here the way that we're looking to once I've determined pass one。

 which gives me the frequency， so frequencies。Past  two。Is the offsets？

So once I've computed the offsets。It's all a matter of looking back at the input array。😡。

And seeing the elements left to right。That would be placed next。

 given the current offset that I'm at in the output array。Okay， so the fact that yours。

Searching left to right means that they're going to come out in。

The same relative order that they were given to you as input。Allright。

 so let me in there with elementary sorts。 and then we can move on to。



![](img/bfa1f1329a6c16454fc58a8203b2d51b_4.png)

Let's start this。Qu art。All right。😊，So most of you have probably already heard about Quickert。Okay。

 it is a very interesting algorithm， it's also the only example of a randomized algorithm。嗯。

That we'll see in this course。 and it's probably the first time that you're going to be looking at a randomized algorithm in detail。

 Now by randomized as you're going to see， it means that。It。It considers as the algorithm executes。

 it relies on。Basically statistics。Um， to make its computation。

 that's what we mean by a randomized algorithm。And we'll see in a bit how Quicksor does that。So far。

 all the algorithms have been know completely deterministic。

 first example is going to be quick sort now。This is you have used a random number generator。

 the fact that you might be writing code that uses a random number generator does not mean。😡。

That you are implementing a randomized algorithm， right just to make that distinction。嗯。In fact。

 Quicksort is a randomized algorithm that doesn't necessarily need to use a random number generator at all。

 okay you're going to see why。But it is nonetheless a randomized algorithm。

 which makes its average case analysis。Quite tough to do so we won't go over too many details of the average case analysis like we won't derive the average case analysis leave it out to you to sort of work on those details this is not kind of203。

Or 376 for that matter。But we will talk about what that is and how it is that we get to an N log in。

Run time analysis。 So we won't derive it mathematically。

 but we will nonetheless discuss quite a bit of details about it。 Al right。

 so what do efficient sorts look to address Well， the basically。

That elementary sorts asymptotically suck right their n squared algorithms， okay again。

 situations in which we want to use them， but if we're just talking generics and asymptotics。

You know， bad runtime Okay， and for your reference， right， in practice。

 if the algorithm is n squared in practice for scalability issues。

 it's almost useless Any algorithm that's anything and。Worse than N log N。

It's almost useless in practice and by practice I mean that you're dealing with input that's in at least the millions right with what we do nowadays。

 input to any algorithm， you should at least consider that it could grow to a million。m。

And of course， if it's an n squared algorithm and the input is a million。

 then it's a million times a million that doesn't work。Yeah。So。啱妈。So they might compare。

 so the elementary source might compare every pair of elements。 Okay。

 that's why it's on the order of n square right you go back to 203 and you wanted to count all pairs。

You know。Remember your choose function for county。嗯。So n choose two。

 so that's n squared some the other， I mean its more， you know， n squared divided by two。

 whatever it is， but。They also often move elements one place at a time。

 so that's more specific to bubble and insertion sort。诶。😊，Remember。

 that was the advantage that we just talked about for a selection sort is that it will only move what needs to be moved。

诶。嗯。So the idea is that faster or more efficient sorts are the idea is that they will tackle these specific problems right。

 and that's why we you know they're more efficient。Um so。Quick sort。

 we say easy to implement in quotes the reason why we say easy in quotes is because there's a lot of things that can go wrong in the implementation。

 so it's often as you're implementing it。You know， there could be a lot of things that could be the sources of bugs in your in your coat。

 even though conceptually， it's really not a hard algorithm。

OkayNow the thing that makes it really good in practice is that it works well with a variety of input data right。

 and this is why the STL sort function relies on Quickert quite a bit because STL as a library cannot make assumptions about the input array that it's given。

And this is an algorithm that if can't make any assumptions about the input。

And then it performs fairly well without making those assumptions， which is good， right？

It is the other important thing is that it not only is it efficient， it's also in place Okay。

 so no extra memory or data is needed Okay it's it's in place with regards to the input array。

 but there is some additional memory that's used in the stack frames because as you will see。

 it is a recursive algorithm。 So that's what makes quick sort。

So interesting to look at it's a recursive algorithm， it is a randomized algorithm， and it behaves。

In practice， it's quite fast。Without having to make any assumptions on the input， okay？

It is also an example of a divide and conquer algorithm， so we'll talk about algorithm families。😡。

In the second half of the semester。And you know。Svy the suspense， we have divideivide and Con family。

 we have backtracking algorithm family， we have a Bra and bound family， so on and so forth。

 so you're already seeing an example of one of those families which is divide and conquer。

What does that do， so if we often this need not be the case， but for conceptualization purposes。

 it is。Often matched， so a divide and conquer algorithm is often matched to a recursive。Algothm。

 right？Again， there's plenty of divide and conquer algorithms that are not recursive algorithms。

But most of the time， there is some recursive。Implementation that you can think of to make things easier to understand。

OkayNow QuickSo is an example of a divide conquer algorithm that's definitely recursive and you don't want to try to implement Quickword in an iterative fashion。

 it just doesn't work。So it is primarily。诶。Recursive algorithm。All right。

 so here's if it's a recursive algorithm， that means that you have a base case and you have an induct state inductive step。

 excuse me。So what's the base case， Well the base case is fairly trivial and simple。

 it is my input at the moment。Is an array that's either a length zero。

 which means I don't have to sort anything or it's。One element。

 which just means it's already sorted because it just has one element。 That's our base case。

 really that simple。Okay。😊，嗯。Then you have our inductive step。

 which is the one that actually does the work。诶。And this is going to be。This is going to be the word。

Guess an element， which we're calling ELT。嗯。😊，Guess an element in the current section of the array that you're looking at。

And this is where the randomization comes into place where we're saying guess。Guess an El。Anyway。

 we're not going to talk about right now but how that guess is， we're just going to say it's a guess。

 right？You pick one of those elements in that section of the array and you're going to partition that section of the array。

😡，Along around that element， okay so what do we mean by partition。

 it means that we're going to arrange things in that section of the array such that。😡。

Everything to the left of the element is going to be less than。

 everything to the right of the element is going to be greater than。Okay or equal。Okay。

 so that's what we mean right here。And notice that this is with respect to the current section of the array that we're looking at。

 that's where I'm going to partition。And the reason that I say a current section of the array is because we're actually going to。

Partition。嗯。The left section of the array。And then the right version， the right side of the array。

 the right section of the array。系。And so that's the divide part， right。

 and then the conquer part would be。All right， I just recursively call Quicksort。

On the left hand side section。And the right hand side section。Separately。诶。And then。It works。

 recursion works its magic。So it'll work this magic until it reaches the base gate。

And it is a bit of magic。Well， not really， but you know what I me。

Next time we'll see a visualization of or you can just do it ahead of time。

 look at a visualization of QuickSo at work， really quite interesting。All right。

 so let's look at code because we haven't really looked at code。

 we've just mainly been using pseudocode。So let's first assume that we have this function called partition that does the work that I outlined earlier in the induction step。

 so it's a black box， I mean we're going to get to it， but for now it's just some function。

That we call。Where we give it the input array。😡，We give it the current range of A that I'm looking at。

 which will be given by left and right Okay so those are the other two arguments to the partition function。

And then it returns what we're going to start calling the pivot。

So what we were calling ELT in the previous slide， the element that we were partitioning over to determine everything to the right is greater than。

 everything to the left is less than。We're now going to give that a more generic name。

 It's well known。 It's pivot。 So we're going to call that a pivot。

 And that's what the partition function returns。 And again， it's a black box。 Okay。

 we don't at this point， really care about。What partition does？Okay， it just。

Goes about its business and then tells me in my partitioning what I used as a pivot during my partition。

U，And notice that the base case is just， well， if left plus one is greater than or equal to right。

Okay， meaning similar you've seen this before， all I'm detecting is basically whether I've， you know。

 my two ends of the range that I'm looking at right now， the start and the end。

 which is analogous to left and right， have crossed each other that means you know。

 I'm basically done so I should just return there's nothing else to do。That's my base case。Um。

 this is u basically the plus one just means like。Oh。

 if the range that I'm looking at only has one element， I don't need to do anything。

 so they haven't really crossed， but all I have in the current range is just one element。

 so I would just return。 goes back to the base case that we had in the previous life。

So then we call the partition which gives me the pivot， and since I have the pivot。

 I'm just going to recursively to make a recursion call to Quick sortt。

Giv it the array that stays the same and now the range is going to be for the left hand side。

 so it would be from left all the way to pivot。And then followed by a second recursive call。

 notice that this is not an if else， it's not like， you know。

 if something called quickswordt on the right hand side only else called Quicksert on the left hand side。

 only no， it has to call both sides， it has to have recursive calls on both sides of the array。

 one includes the pivot。Whi is in this case is line five。

 the other section should not include the pivot， which is why here the right hand side has pivot plus one all the way to right。

Okay。😊，Whether you include the pivot on the left hand side call or the right hand side call is really up to you that should not make a difference。

嗯。Cool， notice the ranges here are left inclusive but right exclusive， okay？

And we'll see how that works in the implementation of the partition function。If base case return。

 those are lines two and three， otherwise we go into our divide and conquer section。

 which is basically lines of five and six。All right。

 so I'll stop here to look at the chat because I saw some activity。

A you had does ELT go on left hand side or right hand side， I just address that it's actually。

 well in the code that we have on the slide， you would put it on the left hand side。

 but it's reallys a matter of choice。I think another nine can go， okay， another nine。

 I'll let our chat handler address that because I'm not sure what it means by another nine but。

Let me keep going because probably what you're probably thinking right now is like all right。

 what do we do in this partition function， what's all is about the partition function？Okay。

 let's talk about that。Oh， well， let me actually， let me go directly into the slide for a simple partition function。

 and then we'll come back to the previous slide， which is really important， right。

 which is the question like what makes a good pivot？

Okay but first let's actually look at an implementation of the partition function okay here is the partition function as how we were using it in the previous slide in the actual quick sort function again。

 it is you know an array of items you have left and you have right。ok。😊，And this is。

 we're calling it a simple partition because it makes a really simple choice for what the pivot is。

Okay， and that happens in line two right here， it's just going to say。

The pivot is the rightmost element in this range that I'm looking at。That's it。

That's our pivot selection。And notice that that's effectively a random selection of the pivot because if I'm assuming that my input array is just going to be arranged randomly in a uniform distribution。

Then you don't know what the element is in the rightmost position in the section that you you don't know what it is and you're just picking at that rightmost element you don't know what the value in it is right noticeice that we're looking at the pivot position。

 not the value。😡，That might。Be in that specific pivot that I'm choosing。Okay。

 so it is the rightmost element in the section of the right that I'm looking at， so again。

 that's just effectively as picking the pivot in random fashion if I had a random number generator to pick one number in that section of the array left to right。

That would work out just the same as what I'm doing here。Okay。😊，嗯。Okay， not exactly the same。

 but for performance purposes， it is the same， okay？And we'll get to that in a little bit， okay。

 but just considering as being the same thing。All right， so now this code looks odd because for for。

Firstly， we have this wild true， which is very， very odd to have。In fact， really。

 I would encourage you to take this code and refactor it to avoid the usage of wild tree because you can't。

 but it's easier to explain if we just use this wild true。All right。So while true。

OkayAnd that means that the only way I'm going to。Get out of this loop。Is by reaching this break。

Okay well sure enough， you will。But again。So's wild true。What is it that I'm doing here。

 I'm going to say from lines four and five， what this is accomplishing it is like。Fine。Candidate。

Element。On the left。To swap。To the right。Okay。😊，And how am I doing that， well。

 all I'm doing is checking each element on the left hand side from starting from the left hand side of the array okay。

 and if that element is less than，The value that's at the pivot。Okay。

 the element that's at the pivot， if it is less than。

Then I know it's since it's less than it's kind of in its right section。

 it correct section of the array because it is less than。

 so I just move the left pointer forward because I'm just saying given the constraint that I'm trying to get to。

 which is that everything on the left，Um， side of the pivot is less than at， that's okay。

 it's meeting that constraint right now， so I just move the pointer forward。

Until I find an element that does not meet the constraint meaning。

I found an element that sits right now on the left hand side of the pivot。

 but should be on the right hand side of the pivot because it's created enough。

That's what lines four and five do。Okay， and then lines six and seven。Do the same thing， but with。

 you know， I'm not going to write at all， but it's vice versa， right？What I'm doing is。If。You know。

 I start from the right hand side。And I move the pointer down this time because I'm starting from the right and I'm moving it down。

As long as an element that I'm looking at， I'm comparing it to pivot and seeing that it's greater than。

 so we would be assuming it's in its right section of the array， so I'm just going to skip it。

Until I reach an element。On the right hand side of the pivot。

 that is less than the pivot in which case it now becomes a candidate to potentially swap with something that was on the lefthand side so that's why it's vice versa it has an extra check right here because I need to determine whether the left and right pointers have crossed each other right but other than that it's lines six and7 very analogous to lines four or five。

Except that it's you know on opposite sections of the。Of the array relative to the pivot。Okay。😊，Um。

And if left or right have crossed each other， then I'm done， boom， break。Okay， other than that。

 I have， if if I get to line 10， it means I found a candidate on the left hand side。

And I found a candidate on the right hand side。That I could swap。

 I found two candidates that I could swap， and then I go ahead and do that。ok。😊，I do the swap。

And then rinse repeat。Okay， until left and right cross each other， then I'd be done。At that point。

I should have。A section of the array where everything is less than on the left。

Less than the pivot and everything on the right hand side is greater than the pivot。

 but notice that I haven't moved a pivot anywhere yet。

So I picked my pivot up here and that was the pivot index， but I never did anything with the value。

In the pivot have the pivot so now line 12 is about like all right。

 I've arranged my left section and my right section。

 now I need to put the pivot in its rightful place given the arrangements that I did in lines three to 10。

Okay， so that's what the swap down here， that's what line 12 would do。喂。😊，So that's what。

The simple partition algorithm would do， of course。

 we should look at an example and then we'll come back to that slide as to like， all right。

 so given what we know about the partition function。

 what would be an ideal so we're picking pivot at random right now， right？

What would be the ideal choice of a pivot， okay？So here is kind of pseudocode for why I kind of out what I kind of outline。

 right？诶。Choose last element as pivot scan from left to right from left for greater than or equal to pivot from right for less than pivot。

 if you found candidates to do the swap， then do the swap。

Rinse repeat until left and right cross each other。

 then line 12 is about moving the pivot to the middle， right？不。All right。

 so let's see how this would work。All right。Usually I do an example here。Of how this would work。Um。

 but in the interest of time， I'm going to basically start with this example on Thursday。

 today's Tuesday， right on Thursday？Let me go back to。Oops。This slide。All right， what is the ideal？嗯。

Pivot for a partition function， so you know we did not care about runtime。Um。

And I could invest infinite amount of time to pick the right pivot。

The ideal pivot would be the median of the current section of the array right if you recall。

 the definition of a median is a value that divides the。populationopulation roughly half and half。

 that's the statistical definition of a median in the array it would be。The perfect pivot。

That was sit in the middle of the array。And have half of the elements to its left。

 half of the elements to the right。Okay。😊，But。If you invest so much time to find a median。

 then basically the fits of purpose of Quickert。Okay， so that's why。Any pivot selection strategy。

 and we'll talk about more of these selection strategies on Thursday。

should take into account that they cannot spend too much time。Right you cannot spend too much time。

Pickking the pivot because it's going to defeat the purpose of the entire quicker so the whole operation for picking the pivot must be constant time。

 you cannot invest something like linear time， which is what you would need for computing the median right you cannot invest on something like linear time to find a median。

诶。So constant time， it would be a just。You know。Pick a pivot at random。对。Now， of course。

 because it's at random。It's not guaranteed to be a good pick。

 meaning if you recall the implementation for the partition function。

 there is no code around there that made sure that half of the elements were to the left of the pivot and half of the elements were to the right of the pivot no。

 it just pick the pivot and however and many elements should go in the left they'll be there and however many elements on the right they're going to be there right so it could end up that in the range of the array。

 the pivot could be here。😡，And so this the left hand size section right here， it's much。

 much smaller。Then the right hand side。Okay。😊，And this is important because they're going to have how we pick the pivot it's actually going to have。

Quite a bit of an impact on the Quickword algorithm。Okay， when we talk about analysis。诶。

So the pivot is pivotal for the performance of， it's actually oddly enough。

 the first semester that I've made that pun in the many years of teaching this course。

 I don't know why， but it's a nice pun。Pivot is pivotal for the performance of quicker。嗯。All right。

 so but what we did in our implementation of partition is again rather simple just as well as calling a random number generator。

 we just said like I'm just whatever the element is at the rightmost。Position of the section。

 that's what's going to be my pivot Could I have picked the element that's on the left。

The leftmost position of the range yes you could have would have just would have worked just as well right the only difference here this would be next sorry left plus plus in line two and then in line 12 it would be a swap with a at right and a at pivot and well there might be a few other change No I don't think so that those are all the changes but yeah it would work just as well。

Okay。嗯。All right， so now。Let's look at other pivot strategies。ok。😊，嗯。Here。Okay。😊。

We are investing a little bit more time with this partition function in the selection of the pivot。

Rather than saying like。You know， I'm going to pick。The rightmost element。I'm going to say， well。

I'm not assured that the element in the middle is going to be the mediumn。

But I'm going to I'm'm maybe I'm lucky， maybe by， you know。

 some chance that element that's in the middle。喂。😊，Will be roughly。Close to the median。系。😊。

So that's what I do， I pick the pivot okay， as the middle element。And then make the swap in。

Assignment right here for the pivot and then go about my business and the rest of the algorithm。Okay。

 the like the only reason why I'm making the assignment in line four is so that the rest of the code that I had from the previous。

Partisition function implementation works all the same right you could have conversely just changed all the code in the previous slide。

To make it work with the middle element rather than the rightmost element。

 but we're trying to keep it simple， so that's why we have the assignment of right to the pivot after I've。

Assigned the middle the mid element to be。The rightmost element in the array。Okay。

 so that's effectively picking。The middle element。So that's yet another。

 does is this partition strategy？Or partition， sorry， pivot selection strategy。

Better than the one that we had， no， there's no way maybe there's some robust mathematical analysis that we could do。

 but you know， I'm very sure that that robust mathematical analysis is going to come up。

 that it should not make any difference in terms of runtime。系。嗯。😊，But still。

We have an open question as Sue。How could we？😮，Pick better pivots。诶。And。

We're going to get to that in a little bit。Again， none of these pivot selection strategies are going to make a huge impact in runtime or the average case analysis。

Okay。😊，嗯。But it's still interesting to look at because there might be situations in which one pivot strategy or another might do better for your particular context。

 right so if， again， if you're looking to implement your own sorting algorithm based on some particular context of things that you're looking to sort and you know that the input is going to be sorted in some fashion。

 then maybe picking a better pivot can help in the actual performance of。こさ。But in general。

 should not make a difference。All right， so。Let me go to。

Run time analysis and I'll end there for today。All right， so we now know。

The quickstar divideiding conquer algorithm， right very simple。

 it was just a matter of maybe five lines of code， we had our base case。

 we had the call to partition， then recursive call on the right hand side。

 recursive call on the left hand side。That's a quick sort algorithm。

But it relies on the partition function that was a bit more involved in terms of the implementation。

 but it's also not bad， right？Basically， again， from the left。

 I find a candidate of a value that I can swap with another candidate that I could swap on the right hand side。

 do the swap， do that until there's nothing else to swap。

 then place the pivot where it should be in the middle。boom。Okay， by the way。

 what is the runtime of the partition function？And I'll answer this real quick because we're running out of time it's linear time right even though it's a nested while loop。

 if you go back and see there's nested while loops， it's not hard to see that。Well。

 let me go back to that， right， So we have this nested while loop。 Okay， It's not hard to see that。

This is going to move forward each time a constant number。Right？

And then this is going to be a constant number of times right so on each iteration。

 I'm not decreasing left all the way down right， so this is on the constant time。

 this is constant time。This entire Y loop is constant this entire Y loop is constant time。

 even though it's a Y loop， it's constant time and then， but this whole outer loop。

 this is going to be n time so then you have n times constant time。

 so it gives you overall run time for the preition of over。Okay。😊，All right。

 so that's runtime analysis for the partition function， which is linear time。

 everything else in the overall algorithm for Quick sort which just constant。

It's a recursive algorithm so we can analyze it in terms of a recurrence relation。Okay。😊。

But this is where pivot selection comes into play。Okay。😊。

What would be the worst case for a quick sortt algorithm？Well， our very worst case。

Which I'll tell you right now， is rather pathological。Is that our pivot strategy is so bad。

That every time I pick a pivot。It does not divide the section of the array。

In roughly equal parts left then。Right greater than。Okay。😊，So more specifically。

 every pivot that I pick leads to a largely unbalanced partitioning。If that's the case， then。

Your recurrence relation boils down to what's on this subballet right here。

 you have T of n is equal to the linear time that I spend for partition。

 so this right here is partition。Then this would be our call to。One half， well。

 it's not one half because I'm specifically saying that when the pivot picks it。

 let's say that it's always bad and so。It always picks the left partition。对。Partition recursion。

And then it's so bad that every。Recursive call to the left partition is on the other of t of n minus1。

Right？And then here it'll be the right。Partition。Recursive call。W which will be just one element。

 roughly。So it's t of0 right because it'll just the recursive call on the right hand side again。

 you could just switch these to be on the right of the you know left becomes right or right becomes left doesn't matter right the point is on one of the recursive calls it basically immediately falls in the base case。

 but then in the other call， it just basically have to perform so much work because it's so un balanceanced if that's the case and you do your recursion。

Analysis and solve the recursion， you'll get that this is， oh my God， it's O of squared。

Do that by substitution。Okay。And wait wait， I thought quicksort was an efficient algorithm。

 I thought it's n log n。 How come you're telling me that in the worst case， it's all n square Well。

 the thing is。That this worst case is a is a pathological case。

 you'd be hard pressed to find a pivot strategy that always gives you a bet you really have to work hard at it。

 okay， to find a pivot。Every time that gives you the worst possible partition。

It's just statistically。Very， very improbable。ok。😊，So it's a very pathological case。

 so much so so that we don't consider it to be really the worst case situation for the algorithm。

Okay， even though it's technically you know， the worst case analysis for it。Okay，U。

 and then in the best case， it would be， I， the best case would be every pivot that I big that I somehow。

Every pivot that I pick turns out to be the median。Right magically。

 without having to invest linear time， every pivot that I pick is the median and therefore every time it divides。

The section of the array， half and half， half less than the pivot， half greater than the pivot。

If that's the case， then you solve this recurrence relation and that's where you get。And log in。

 okay， by master theorem or using substitution。And then the average case is actually， which again。

 we're going to。Skip because it's required a bit of math and bounds and probability bounds and all that sort of stuff。

But it basically， the average case also gives you an n log n situation。All right。

 so we'll stop here today， continue with this in the next lecture， but you can already see that。

This is， even though its worst case situation is that it's n squared。

 we really consider it to fall in the efficient algorithm category and we consider it to be an n log n algorithm because。

You know， even if you picked the simplest pivot strategy， you would get N log N behavior。

Rather than in squared。It does a disservice to us to consider the worst case situation for quickser to be an n squared runtime in general。

OkayAll right， so I'll stop it there。See you all。On Thursday。

 we'll continue with finish off Quick sort and then go into a ME sort。

Y'all thank you to our staff whoever's in on the channel， thank you again on the chat channel。

Catch you all later。诶。😊，Make sure。Project two， if you haven't started。Youd better start soon。

But I hope everyone has that started and has started to submit to the auto grid。All right。

 have a good afternoon。