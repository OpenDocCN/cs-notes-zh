# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P2：02_02_04_二分查找.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/3d3999c48401001e63c51a9b68401085_0.png)

So here's a better method， it's a very classical method called binary search。

 and it's quite intuitive。So the idea with binary research is that first of all。

 we put the whitelist array in sorted order， now we're going to have to talk about how to do that and that's the second part of this lecture。

If it's in sorted order， then what we want to do is examine the middle key。

If that one's the one we're looking for， then just return that index， we found it。If it's larger。

 then we know that our key must be in the lower half of the array the ones with lower indices。

And if that one in the middle is smaller than our key。

 then we have to look in the half with the larger indices。So for example。

 here's our list again and we're looking for Oscar。

 we check in the middle is that key there Eve is that the key we're looking for and the answer is no。

 our keys bigger so we can eliminate the first half of the array and just look in the second half and we look in the middle of that one in this case it's peggy。

 our key is smaller now we can eliminate the。Top half of the array and concentrate on the lower half of that part of the array and again Oscar it's not mallllory so we know it has to be bigger and eventually we get down to where we find our key or we get to an array of size1 that's not equal and we know that our keys not there。

 one of the two must be true。So in this case， we found a match we returned 10。 That's binary search。

So it takes a little bit of arithmetic， we'll use a mathlike notation if we say a of square bracket low comma high we' low and higher indices in the array。

 and then regular parenthesis that means that we are considering a of low a of low plus1 all the way up to high minus1 but not high itself it's an open interval and math and the same thing works for an array in Java and so if we're looking in this part of our array where we include low and not high。

 high is bigger than low or equal to it， then if we want to look in the middle where the way we get the middle is subtract our two indices divide by2 and then add that to low。

 so the number of elements is high minus low divided by that by two that's half the size of the array and add that to low。

 that's our middle。And then we once we've compared our key against mid we don't have to consider that one anymore。

 so we just include it is with the open parentheesis to exclude that in the lower half of the array and then the upper half of the array we do mid plus1 and then again we use high but exclude A of high and this is just a detail that helps make the arithmetic easier to check when we implement the recursive routine that's going to do this。

You need to study it a little bit， it's easy to get this wrong。

 but it's worth it to take a quick look at this。Okay， with that in mind。

 let's look at the Java code for implementing this search。

So that's the method that we're supposed to implement taking our key and the array as arguments。

 and we're going to call a recursive routine that also includes the indices within the array that we're concerned with。

Low and high as on the previous slide， so that's all set up。

 the array goes from  zero to a dot length minus1， so with our open interval notation if we call the recursive routine from zero to a dot length we're doing exactly what we want search the entire array。

And then recursively we checked that our high is bigger than our low， if it's equal。

 then there's nothing in the array or even if it's less there's nothing， nothing in the array。

 so that's our termination condition， that's an unsuccessful search we never found our key。

Then we compute the index of the middle element just as on the previous slide。

And we compare that element against our key and just that result is minus1， if our key is less 0。

 if it's equal in one if it's greater， and then we just test that to see whether we're in the left part of the array in the right part the part of the array with bigger indices。

 or if it's not greater or less then it's equal to 0。

 and then we return successfully with the index that contains the key。

So that's a recursive method that solves this problem。And again， it's easy to make mistakes in this。

 it's worth a study， it's worth some study， but it's basically a pretty simple program once you make sure that you have some discipline in making sure that you test for the case when it's empty or it's got just one key as we have。

Okay， so here's what it looks like， say with the recursion trace， so in our example。

 searching for Oscar， we're searching from  zero to 15。So to do that， then we compute7。

 the Oscar is bigger than Eve， so then we go to the higher indices from8 to 15。

And now the middle's 11， Oscars less than Peggy， so now we go in the part with the lower indices。

 that's 8 through 10， and now the middles nine， Mallory。

 Oscar is bigger than mallory so we go the part with higher indices 10 and 11。

 10 and 11 is just an array of size1， and that's where Oscar is so we return that index。

And then we go back up the recursive tree returning that value all the way up to the main return 10。

 and that's a successful search。All right， what about the。

 let's do a mathematical model to study this method？First simplicity。

 we'll do an exact analysis when the number of keys is a power of 2 minus1。

 and you'll see in a bit why it works that way。So if big n equals2 to the little n minus1。

 then little n is about log based 2 of n， it's actually equal to log base 2 of n plus 1。

But let's look at what happens in this case， so if you subtract1 and then divide by 2。

 you're always going to get so for the first call it's always2 to the little n minus1。

 but if you subtract1 and divide by 2 for the second call it's always going to be 2 to the n minus1 minus1。

And again， subtract1， divide by 2， the size for the next call is2 to the little n minus2 minus1。

You keep going that way。 eventually we get down to always for the anth call。

 the subboary size is going to be exactly one。So every search miss is going to be a top to bottom path in this tree and the total number of compares。

 so for every call we do one compare against our key against the middle key in the current array。

 the total number of compares is going to be little n， which is about equal to log of big n。

That's an indication of how binary search gains its efficiency so almost that is a proof that binary search uses about log n compares for a search miss and with a little more work you can show that same is true for a search hit and it doesn't matter if it's a power of two you still get these same results so these are kind of interesting exercises in discrete math。

 but you can see that the running time is going to be proportional to log n for whatever in this and you can learn more about this maybe in a course on algorithms。

But understanding it in terms of when n is a power2 minus1 is fine for our purposes。

So our model is that the cost of a search is going to be log base2 n about log base2 of n。

 that's the point of this mathematical analysis。 and again， we want to test this empirically。

Aice has already signed up for the course on algorithms。

So let's do our empirical tests for the scenario that we considered for sequential search。And again。

 we'll do the same story and now we'll test binary search， not sequential search。

 so in this case for 100，000 it takes just one second。For 200，03 seconds。For 400。

6 seconds and now our ratio is a lot closer to 2 than four and we can go up to 1。

6 million and it's only taken 30 seconds， remember for sequential search it taking hours and so for 10 million you can do it in a few minutes and the ratio is about two and we're at about 50。

000 transactions per second in holding。So that validates the hypothesis that each of the n searches takes time proportional to n log N。

 that's something that will scale， and binary search is certainly much more effective method for solving this problem than sequential search。



![](img/3d3999c48401001e63c51a9b68401085_2.png)

But the question is， how do we get the list into sorted order at the beginning。

 That's the thing that we're going to have to consider next。



![](img/3d3999c48401001e63c51a9b68401085_4.png)