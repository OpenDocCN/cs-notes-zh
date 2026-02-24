# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P81：1 - Spring 2023 Exam-Level 14 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/1ea0274715be23b16c57bfe1a8afbcf9_0.png)

Hi， I'm Angel and welcome to CSs 61 and B exam level discussion or team question1。 Alright。

 let's go ahead and before we get started， I thought it' would be nice to put up this table Here we have table of the best case and worst case runtime for each of the sorts。

 so feel free to pause and take a quick look before we jump in。😊，All right。

 now that you've hopefully returned back to the world of sorting。

 let's go ahead and jump into question one。So here we have question one， sort in runtimes。

 we want to sort an array of n unique numbers in us order。

 determine the best case and worst case runtimes for the following sorts。Okay。

 so it sounds like that table will be useful Part A。

 once the runs and merge sorts are of size less than or equal to n divided by 100。

 we perform insertion sorts on them with the best case of big theta blank and a worst case a big theta blank which we have to fill out All right。

 let's go ahead and do kind of something similar to merge short and break this down into smaller more digestible problems with that first part being once runs and merge sorts are of size less than or equal to n divided by 100。

So how do we even get that， how do we get this inequality to be true Well to get this inequality to be true。

 let's go ahead and take a look at how merge sort runs when we have at the beginning。

 when we don't have any recursion， we're just going to go ahead and have this be size n array that we start with and then when we recursse at the first level。

 we're going to go ahead and have each size be n divided by two and E divided by two splitting that array in half。

😊，Then after we do that， we're going to go ahead and continue with n divided by four and n divided by four splitting that n divided by two and half for both of them。

 so here we're also going to have n divided by four and n divided by four length arrays。😊。

So how do we decide how do we find that the level or the size of an array or a run in bird sorts well in this we're going to go ahead and say that a size is each time we recursse we're kind of adding another factor of two to divide by so a way to find the size of the runs is going to be n divided to to the power of x where X is the。

It was the level of recursion we've done so far and to get that original thing we were looking for。

 we needed to satisfy less than or equal to and divided less than or equal to n divided by 100。😊。

So now that we have that， we can go ahead and try to find an x that satisfies this。

 and this will go ahead and be n divided by2 to the x or2 to the7 to the x to the original one。

 and that will equal n divided by 128， which is less than or equal to n divided by 100。😊。

Now now that we've done this， it looks like we're going to recur and do seven splitting slash merging now the question here becomes how much how much does this affect our runtime and if so how feel free to pause to think about it before I reveal。

And the answer here is that it actually does not work or does not affect our runtime terribly watch now why is that so in order for something to affect our runtime the input size must be what affects it so here。

Whether we have end NB a million， 2 million， 3 billion，4 million or five trillion。

 we're still going to have to split slash merge7。Al right we're still going have to split slash merge seven times to get this inequality to be true。

 So the amount of， if the amount of time that we split slash merge is going to be fixed。

 we actually find that we're not going to。We're not going to have that be anything but constant in our runtime operation。

 so here we're going to have this part running constant time。Cool， wow， seems like a。

 seems like a pretty good runtime so far。But then we have second barbs， we perform insertion sorts。😊。

On them， on each of these little runs。All right， so let's go ahead and break this down so if we run insertions sort on just one of the runs。

 which is N divided by 100th length， how would that work out？

So let's take a quick look at insertion sorts here we have a best case of n and a worst case of n squared。

 So if we ran this on。N divided by 100， how would our would our if we run insert sort on an array of n divided by 100。

 what would our best case and worst case be for that？

And the answer here is actually going to be big theta N for our best case and big theta。

N squared for our worst case。And that feels kind of crazy because if you look right here。

 we were dividing n by 100。 You know， it feels like that should have had an effect， but。😊。

It's important to remember that in asymptotic analysis。

 multiplying or dividing by a constant will not affect our asymptotic analysis。

When we divide n by 100 here it really doesn't affect our outcome now we don't only do it once we're actually going to do this 100 times because there's 100 runs and we still still have a length of n so if we run insertion sorts with each of these posting with the best case and the worst case 100 times what would the result be for the best case and the worst case？

Yeah， so the answer here will actually be unaffected it'll still be theta n and theta n squared now why thats that's a great question as to why it's going to be the same reasoning for why this divided by 100 n affected because now if we're multiplying by a constant or dividing by a constant it doesn't affect it either way so we're going to keep that same runtime of n and n squared so when we fill this out we can go ahead and say that our best case is n and our worst case is n squared cool cool let's go ahead and go into part B then。

😊，Coming back to part B of question one we have a different algorithm where we're going go ahead and use a linear time median finding algorithm for our pivot of quick sort so first we need to see how does Quick sort even work without this median finding algorithm so the way it works is that it's going to go ahead and from an array it will go ahead and pick a random number and have everything and let's just say that this number will be right here everything before that number will be less than it and everything after it will be more than it。

😊，And that's really a great system to work out because in the best case。

 let's say we pick the median each time we go ahead and start with n and then we split it off into n divided by two for each time。

And then after that if both of these nodes right here or in the recursion loop pick the median as well。

 this will go ahead and split into n divided by four and n divided by four and kind of continue that process until we get that those leaves at one so there's a few questions here what is the length of what is the height of the tree we'll actually find because we're dividing by two each time the height will go ahead and be log n。

😊，Now what about how much work are we doing per level and that kind of requires us to ask how much work are we doing per node and the answer here will end up being n we're doing end work per node right now without this linear median finding algorithm why well it's going to take end work to partition that everything before this index is going be less than whatever numbers here so like let's go ahead and put 10 so it's going to take n work for everything before this to be less than 10 and everything after this to be more than 10。

So at this at the first level itll go ahead and be n work because we have just that one node at the second level it'll be n divided by two work plus n divided by two work thatll be n and at that third level it'll be n divided by four plus n divided by4 plus n divided by four plus n divided4 and we'll have n work so we'll have a total of n log。

And。Okay， cool， so this is right now our best case scenario without finding the median Now what about with finding the median now with finding the median that means that each level at each level or at each node we're going not only going to have to partition we're also going have to do this linear time and this is very important right here linear time grade run time we're gonna have to do this linear time operation so it'll be now at each work we're going have at each level we're gonna be having to do n plus n work which is equal to2 n。

😊，So asymptotically， how much work is done per a level and you may want to use something we talked about earlier。

Yep at each level this will actually go ahead and be big theta n work because while we do have this two now。

 remember constants do not matter in our asymptotic analysis so while we do have two n work per node now it'll go ahead and still be big theta n work at each thing meaning that the work over here isn't changed so we're going to go have n log n as our。

As our operation now， what about worst case now without this algorithm our worst case was we always。

 let's say we had a list of one through or one through one through。

1 through 100 so if we had a list of one through 100 our worst case would be like we're not partitioning evenly so let's say we had like we picked one well there's no number less than one so it would just be moving everything in front of it so that would be n and now we still have to break down n minus one work。

And then after that let's say we picked two Well then there's nothing before two that wasn't already sorted by one so now we're gonna to have to just move everything in front of two and two to the front before or after one and that kind of continues for each one and that worst case was we weren't picking the media and we weren't splitting it evenly and we were picking either the lowest or the highest number that really wasn't splitting it up so and we do this until we get to that last number so what would the sum here be well we would have one plus dot dot dot dot dot plus n minus one plus and that's how we got n squared which is our current worst runtime。

Now。Here now let's go ahead and say that we do change to this median finding algorithm to picket as the pivots Well。

 if we pick the pivot as the median each time we actually will never have this or we will never have this tree again we will only have like picking the median so if we have that let's from one to 100 we would pick 50 and then each of those partitioned ones will pick 25 or 75 and then itll continue to break down evenly into this nice tree because now we're picking the median instead of having the possibility of picking the worst one that we had before So if we're only picking the median and we can never pick the worst one。

 this tree will never happen and only this tree will happen。

 meaning that we're gonna go ahead and use this tree and we already solve this tree runtime which was really nice of being in log N so we can go ahead and say our worst case scenario is going be n log and we have our solution there All right let's go ahead and go into part。

で？All right， let's go ahead and come back for a question1 C where let's go ahead and read the algorithm。

 we implement a heap sort with a min heap instead of a max heap So it's a bit different you may want to modify or you may modify heap sort。

 but you must maintain the constant complexity So what would would be our best case in our worst case in that case scenario maybe too many cases in that So how did heap sort work before。

 Well， you would use that maxheap where let's say that we're going to continue that theme of a list from one to 100 when we use a max heap。

😊，first or the largest number will go ahead and be at the beginning and 99 and 98 will go ahead and follow it in either order。

 so I'm just going to put 99 right next to it and we have a bunch of numbers in the middle and what we're going to do is we're going to take that largest number from that heap and we're going to bring it to the end so we're going go ahead and do in the next step 99 and we're going to put 100 with the max heap。

So and this works out nicely because then after we when we pop 99 out。

We're going to go ahead and have 99 be right before 100。

And that's super nice because then by the time we end。

 it's going to be in us ending order and it's going to be sorted。Now。

 what if we do this with a min heap， Well， if we do this with a min heap， it'll be a little odd。

 So let's go ahead and。Erase this。And say that instead， we pick。1 and2。Well。

 when we pop off one and move two up because it's going to be a men heap so you're going to take the next smallest number。

 so let's go ahead and put one at the end and two at the end。Then after that。

 we're going to go ahead and pop off two from the beginning and move it to the end。

We're going to end up with something that's in descending order。

 We're going to end up with something going from 100。

To 99 to 98 dot dot dot dot dot to two and then one and this is kind of sorted but in reverse order so how could we how could we get this。

 how could we move this。To actually。Being sorted in a order and the idea here is that actually this won't take too long It actually will take only going through that array once because what will happen here is we'll say okay until we're like at the halfway point let's go ahead and swap everything with its reverse So let's go ahead and swap 100 with one。

😊，And we're going to go ahead and move this here and then let's go ahead and hopefully not move。

 all right， let's go ahead and hopefully not move that bracket and move 100 here and then let's go through that to the next number where we're going to swap 99 with two。

😊，And then continuously go through that and we find that this will only take an n amount of work it'll take only one iteration of the array so let's go ahead and have our algorithm and it maintains that constant space complexity because we're not adding a new list here so how do we kind of adjust for this so right now in order for our heapspher to work we have to heify and that takes end log end。

And this is what causes our current heap sort right here to be in log n。

 So we're just going to say that we're gonna to heapify。

 and then we're gonna go ahead and we're going add that plus n operations to swap it from usending our descending order to us ending order。

 But remember， in asymptotics， we only take the largest operator or the polynomial that takes the largest。

 So here n log N is going to grow significantly faster or at least the decent link faster than N。

 So we're just going go ahead and say our asymptotic analysis of this will be N log N。

 So for both best case and worst case we go have ahead and have n log n and N log N。😊，Cool。

 now let's go into the final part of D， although that's a little dece evening because there's a few in there's bullet points in part D。

So let's go ahead and read the instructions， we have we run an optimal sorting algorithm of our own choosing。

 so that first one we're going to have at most N inversions。

 so what could our best case and worst case be？😊，Well， if we have at most inversions。

 we is to think about what could we possibly do that would minimize the amount of work we would have to do and the answer here will go ahead and be using a sort that weve may have heard of before called insertion sorts。

And why is that， that is a great question， why are we going to go ahead and use insertion sorts for this question？

And the reason is is。And certain sorts takes。An amount of work that is n plus K。

Where K will be the number of operations that we will have to do。

Are the number of inversions that we have and inversions basically means when we have to swap something so when we have to swap something in that case that'll just go ahead and be big omega n plus and what's our worst case scenario or what's our best case scenario well that would be one where there's only one inversion that'll go ahead and translates to n plus one and remember we don't consider constants。

 we only consider the biggest thing so thatll go ahead and turn into big theta n。As our best case。

 And what about our worst case， Well， in our worst case， we have big N， our big theta with n plus n。

 And that turns into big theta。ToN and a major theme about the questions we've had so far is that we ignore constants so we're going to go ahead and have big theta and as our worst case so in both our best and worst case we're going to go have big theta and as our answer。

😊，So yeah， if you ever run into a question that's dealing with inversions and you want to see what could be really fast using this comes to be very helpful in the future yeah and then let'sooh okay。

 let's go ahead and go into the second part of this。😊。

Our next question part D was going to be there's exactly one inversion now we have to think about how our best and worst case would be effective so there's only one swap we have to make that's what an inversion means so what is our best case。

Well let's think of a general algorithm first our best case is that when we review the array it's going to be the first two so like let's say it's two and one well that's a really easy those are really easy two things swap because we basically only had to evaluate one thing so that'll go ahead and be our best case of constant time where the things that we do have to swap are going to be those first two elements。

And what's our worst case， Well， our worst case is going to be that we have to go through the whole array to find which。

Or what is out of place。So， for example， that would be。One， two。

 and let's say we're considering things in order and then we have 90 or sorry。

199 here we had to go through the whole array to find which is which order or where the inversion was。

Because we still had to check the ones before 199， otherwise we may have accidentally skipped to the inversion。

And we weren't as lucky in the first one where it was the first two we looked at。

 so our worst case is going to be end time because we still have to go through the entire array。

 unfortunately。All right， our last one is a little odd where it says there are exactly n times n minus one divided by two inversions and that sounds like a lot that sounds like a lot a lot of swaps in fact。

 how is that even possible so let's go ahead and talk about how is it even possible first because that seems like a lot of swaps so how did this number even come to exist？

😊，Well。In this， we have to talk about how can we or the process。

Of how many possible inversions there are in an array。And to do that， we would need an of。

Let's go ahead and say that N could be swapped with。Everything but itself。

So the possibility are to be can to be swapped with everything but itself， that'll be n minus one。

 but this process would double counts because it would say， well， let's say we have。1 and 2。

AndIn that array of 100。If we swapped this， it would count the same for swapping these two twice。

 so we're going to need to divide this by two。So this means that we have the maximum amount of swaps that are possible because n multiplied by n minus1 divided by two is。

AWay to get every possible swapth without double counting it。

So everything that is possible are that is possibly swaps from the。

If everything that is possible that can be swapped from a sorted array is swapped。

 what does that mean？Well， that means that it's actually in descending order because let's say that we。

We think of the worst possible order that could be in it'll be 100 and then 99 and then dot dot dot dot2 and one well then this is going to say。

 all right， this should be swapped with one， this should be swapped with two and etctera。

 et because itll be at every step it'll be like are you have the wrong element at this element。So。

In order to solve this， how would we have thisending or descending array and we should change it to be ascending。

How could we do that but we actually solved that earlier today in this video in this heAP problem where we said we would have to take N operations to go through the array and just swap these corresponding indices so we're going to have the best case BN and the worst case BN as well here。

And that's because this is the maximum amount of total。

Possible swaps there are through the sum theorem and in order to。

In order to swap those from us order or from descending order to us sending order。

 we have to use that same process of going through the entire weight array and swapping it。Okay。

 so that helps conclude problem one of discussion or exam level discussion 14。

 hopefully that was helpful yeah and if you have any other questions feel free to post on Ed goal。



![](img/1ea0274715be23b16c57bfe1a8afbcf9_2.png)