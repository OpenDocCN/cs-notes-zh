# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P70：2 - Fall 2022 Discussion 12 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

That's what makes you good。

![](img/04ca18b5fa165263c0af79dce91682b7_1.png)

Okay， so for question one， this is just running mechanical sorts on a particular list of integers。

 so for part A， we're actually to show the steps taken by insertion sort on this list over here so if you remember insertion sort it's basically the one where we go through each element of R and we try to swap it backwards as much as we can until we hit a stopping point when we can't swap back anymore what I mean by that is you want to keep swapping with your left neighbor as long as you are smaller than your left neighbor Okay so in this case we'd see the zero。



![](img/04ca18b5fa165263c0af79dce91682b7_3.png)

![](img/04ca18b5fa165263c0af79dce91682b7_4.png)

![](img/04ca18b5fa165263c0af79dce91682b7_5.png)

![](img/04ca18b5fa165263c0af79dce91682b7_6.png)

![](img/04ca18b5fa165263c0af79dce91682b7_7.png)

![](img/04ca18b5fa165263c0af79dce91682b7_8.png)

And we're at the beginning of our array so there's no need to swap left and then now we see this four and do we need to swap left well four is greater than zero so there's no need to swap that so we move on to position two in our array we're going to see that two is smaller its left neighbor4 right so it's going to make a swap there and then it's going to look at its left no left neighbor now because two's left neighbor is now zero there's no need to swap there so we leave it B and we're going to move on to position three in our array so in position three of our array we have seven there's no need to swap with our left neighbor which is four so we're going to move on。



![](img/04ca18b5fa165263c0af79dce91682b7_10.png)

![](img/04ca18b5fa165263c0af79dce91682b7_11.png)

![](img/04ca18b5fa165263c0af79dce91682b7_12.png)

![](img/04ca18b5fa165263c0af79dce91682b7_13.png)

We look at six， six is less than seven， so we are going to make that swap。

 six is not less than four those， so we stop the swapping there。



![](img/04ca18b5fa165263c0af79dce91682b7_15.png)

Then after that， we're going to move on to one the next index in the next index position that we haven't seen yet。

 so at this point。

![](img/04ca18b5fa165263c0af79dce91682b7_17.png)

We're going to keep swapping one left。 so one's going swap with7。

 then it's going to swap with6 right because one is less than6 that it's going swap with four and finally it's going to swap with two and there's no need to swap with 0。

 So now we know that this sub array has already been sorted right we need to now sort the rest of the array with the three and the five。

 So the three is going to take similar steps above it's going to swap with the seven it's left neighbor right because it's smaller than7 than the6 than the four and it's going to stop there because there's no need to swap after that And finally with our five over here we're going swap left with the seven。



![](img/04ca18b5fa165263c0af79dce91682b7_19.png)

![](img/04ca18b5fa165263c0af79dce91682b7_20.png)

And then the six and we're going to have our sorted list because we don't need to swap with four anymore。

 okay， so that's insertion sort。

![](img/04ca18b5fa165263c0af79dce91682b7_22.png)

For1 B let's do the same list， but let's do selection sort so we want to find the smallest element after the linear pass over all elements in the array and then swap that element into position zero right because we know that position zero if we have an array want it sorted in ascending order the smallest element in the array should be in position zero so we're going to find that the smallest element is just zero and there's no need to swap zero because it's already in position zero right so we know that this part of the array has already been sorted so now we just need to look through the rest of the array over here to find out the next smallest element to put into position one。

😊。

![](img/04ca18b5fa165263c0af79dce91682b7_24.png)

![](img/04ca18b5fa165263c0af79dce91682b7_25.png)

![](img/04ca18b5fa165263c0af79dce91682b7_26.png)

![](img/04ca18b5fa165263c0af79dce91682b7_27.png)

![](img/04ca18b5fa165263c0af79dce91682b7_28.png)

So we're going to make a linear pass over the rest of this array over here and that's going to be one right so now we're going to swap one into position one so the four is going to end up over here。



![](img/04ca18b5fa165263c0af79dce91682b7_30.png)

![](img/04ca18b5fa165263c0af79dce91682b7_31.png)

![](img/04ca18b5fa165263c0af79dce91682b7_32.png)

Okay， and then we're just going to repeat this stuff over and over again right that's just what selection sort is we're going to look at the rest of this unsorted array over here because we know that these first two elements have been sorted and then we're going to see that the smallest element is two two is already in position to so no need to swap。



![](img/04ca18b5fa165263c0af79dce91682b7_34.png)

![](img/04ca18b5fa165263c0af79dce91682b7_35.png)

![](img/04ca18b5fa165263c0af79dce91682b7_36.png)

And then let's continue on with our linear pass with the 76435。

 we're going to see that the smallest element in this sublist is three。

 so we're going to swap three into position three of RRA and that's going to swap with the seven over here so seven' is going to end up right here。

😊。

![](img/04ca18b5fa165263c0af79dce91682b7_38.png)

![](img/04ca18b5fa165263c0af79dce91682b7_39.png)

![](img/04ca18b5fa165263c0af79dce91682b7_40.png)

U。

![](img/04ca18b5fa165263c0af79dce91682b7_42.png)

And then let's just repeat this process until we get fully sorted so we're now looking at these remaining four elements。

 we see that the smallest one is four so we're going to swap four into position four same thing with the last three elements we see that the smallest one is five we're going to swap this into position five so on and so for so we're going to swap six and then we're going to swap seven but there's no need to swap these two left so that's how we do selection sort。



![](img/04ca18b5fa165263c0af79dce91682b7_44.png)

![](img/04ca18b5fa165263c0af79dce91682b7_45.png)

![](img/04ca18b5fa165263c0af79dce91682b7_46.png)

![](img/04ca18b5fa165263c0af79dce91682b7_47.png)

Okay， so hopefully insertion sort and selection sort are pretty intuitive。

 I think where things start to get weird is like merge so and quick so and heap sort so let's go through those a little bit more slowly。

😊。

![](img/04ca18b5fa165263c0af79dce91682b7_49.png)

![](img/04ca18b5fa165263c0af79dce91682b7_50.png)

Here we want to figure out the steps taken by merge sort。

 So remember that merge sort basically takes a list and recursively splits it in half over and over again until there's only one element left in each sublist right。

 because we know that if a list only has like one element in it。

 it's trivially sorted right because it's the only element in its list。

 And once we have that we're going to try to get two elements and zipper them together in a sorted fashion。

 So what we mean by that is。

![](img/04ca18b5fa165263c0af79dce91682b7_52.png)

![](img/04ca18b5fa165263c0af79dce91682b7_53.png)

![](img/04ca18b5fa165263c0af79dce91682b7_54.png)

![](img/04ca18b5fa165263c0af79dce91682b7_55.png)

Once we have two elements that are just by themselves we know that we can make just one comparison to figure out the order of those two elements like in a sorted manner and then we'll just zipper those up continually until we have to zipper the last two big halves of our list so what this looks like is when we split it up into all these teeny tiny little subs is we'll see that the first half of the array goes here here's the second half and then the first half itself gets split down again right the0427 gets split down into04 and 27 likewise the6135 gets split down into61 and35 and then these all get sorted and see these tiny little sublist of size one where they're the only element right？



![](img/04ca18b5fa165263c0af79dce91682b7_57.png)

![](img/04ca18b5fa165263c0af79dce91682b7_58.png)

![](img/04ca18b5fa165263c0af79dce91682b7_59.png)

![](img/04ca18b5fa165263c0af79dce91682b7_60.png)

![](img/04ca18b5fa165263c0af79dce91682b7_61.png)

![](img/04ca18b5fa165263c0af79dce91682b7_62.png)

So now that we know that we have these like elements in their own arrays。

 we can start comparing them， so here let's start comparing zero and4 we'll see that zero is less than4 so we're going to end up with zero in a left position and a four in the right position。



![](img/04ca18b5fa165263c0af79dce91682b7_64.png)

![](img/04ca18b5fa165263c0af79dce91682b7_65.png)

And then next if we focus on two and seven， two is less than7。

 so two is going to end up in the left position sevens ending up in the right position。



![](img/04ca18b5fa165263c0af79dce91682b7_67.png)

Of。Oh oops that we're going to do the sublist over here my bad so now that we're here。

 we have to zipper these two lists together。 So what we mean by that is we have to look at the respective fronts of each of these two sublist right because we know that these sublifts themselves are in sorted order but but we can't just concatenate them together because this isn't necessarily in sorted order right like 0。

4，27 not necessarily in sorted order。😊。

![](img/04ca18b5fa165263c0af79dce91682b7_69.png)

![](img/04ca18b5fa165263c0af79dce91682b7_70.png)

![](img/04ca18b5fa165263c0af79dce91682b7_71.png)

![](img/04ca18b5fa165263c0af79dce91682b7_72.png)

So what we're going to do here is we're sorry we're going to compare the heads of the two lists so zero and two we're going to see that0 is less than two so zero is going to go into the array first and now what we're going compare next is the two and the four two is less than four so we know that two is going to go into the array next and now we're comparing four and7 so I hope that makes sense as to how we like think about like。

😊。

![](img/04ca18b5fa165263c0af79dce91682b7_74.png)

![](img/04ca18b5fa165263c0af79dce91682b7_75.png)

![](img/04ca18b5fa165263c0af79dce91682b7_76.png)

Like or like how we move on and consider which elements in the array right as soon as the element we're looking at goes into a the array we look at the next element to compare when we're comparing like the front of our list that hasn't already been processed right so next when we compare four and seven we're going to put in four and then lastly trivially there's only one left so we're going to put in seven so that's kind of what we mean zip bring these two lists together right like we basically have to。



![](img/04ca18b5fa165263c0af79dce91682b7_78.png)

![](img/04ca18b5fa165263c0af79dce91682b7_79.png)

Kind of compare the fronts of both of these lists because they themselves are sorted and kind of like weave them together such that they give us an ultimately sorted list over here so we're going do the same thing over here with the six and the one one is less than six so one comes first over here three and five three is less than five so three is can come first and then we're going to do the same ziping scheme where we where we compare one and three one goes in first so next we compare three and six three goes in next so after that we compare five and six five goes in after that and then finally six goes in there and we're going to repeat the process right because this is recursive so we're really slowly building this list back up for this recursive process we're going to zipper these final two sublists together so in the same manner that we've been ziping these ones below together so we're going compare the front of these two relatively sorted lists right they are sorted in their own sublist and zipper。



![](img/04ca18b5fa165263c0af79dce91682b7_81.png)

![](img/04ca18b5fa165263c0af79dce91682b7_82.png)

![](img/04ca18b5fa165263c0af79dce91682b7_83.png)

![](img/04ca18b5fa165263c0af79dce91682b7_84.png)

![](img/04ca18b5fa165263c0af79dce91682b7_85.png)

![](img/04ca18b5fa165263c0af79dce91682b7_86.png)

![](img/04ca18b5fa165263c0af79dce91682b7_87.png)

![](img/04ca18b5fa165263c0af79dce91682b7_88.png)

![](img/04ca18b5fa165263c0af79dce91682b7_89.png)

![](img/04ca18b5fa165263c0af79dce91682b7_90.png)

These together。So this is going to compare zero and one so zero goes in then we compare one and two one goes in then we compare two and three two goes in。

 we compare three and four， three goes in and then four， five， six， seven。

 so on and so forth and that's how we get merge sort for our list all right。😊。



![](img/04ca18b5fa165263c0af79dce91682b7_92.png)

![](img/04ca18b5fa165263c0af79dce91682b7_93.png)

![](img/04ca18b5fa165263c0af79dce91682b7_94.png)

![](img/04ca18b5fa165263c0af79dce91682b7_95.png)

Now。U。

![](img/04ca18b5fa165263c0af79dce91682b7_97.png)

For heap sort。This one， we have a smaller example because we don't want you to draw like the heap too large because that would be really annoying。

Here we're going to heify our list， right we want to the the basis of hub sort is we're going to make a max heap out of。



![](img/04ca18b5fa165263c0af79dce91682b7_99.png)

Out of our list and then continually pop off the max and reheapify until we run out of elements to pop off in our heap right so when we heify this is what it's going to look like if we're treating this as like the regular heap ordering right like the zero is like the root and then six and two are the children of zero and7 and four are the children of six right it's kind of like the ordering here represents kind of like a bFS traversal of like a binary heap right if you don't remember that。



![](img/04ca18b5fa165263c0af79dce91682b7_101.png)

![](img/04ca18b5fa165263c0af79dce91682b7_102.png)

![](img/04ca18b5fa165263c0af79dce91682b7_103.png)

![](img/04ca18b5fa165263c0af79dce91682b7_104.png)

![](img/04ca18b5fa165263c0af79dce91682b7_105.png)

Maybe like revisit the heaps discussion a little bit， I'm not going to get too much into it。

 but basically we're going to treat this as if this was the array representation of our max heap and then just keep ary from here so。



![](img/04ca18b5fa165263c0af79dce91682b7_107.png)

![](img/04ca18b5fa165263c0af79dce91682b7_108.png)

Since we want this to be a max heap we'll have to move some of these elements around so we're going to do a couple of swaps right because here7 is greater than6 and in a max heap each node should be greater than each of its children node so we're going to swap the six and the7 and then once again we're breaking the violation here where we need zero to be bigger than7 and2 which is not the case we're going to swap up seven and then we have to reheapify right here right because zero is not greater than six or four so we're going to swap the zero with the six and now we have this like nicely formed heap and we're ready to go so。



![](img/04ca18b5fa165263c0af79dce91682b7_110.png)

![](img/04ca18b5fa165263c0af79dce91682b7_111.png)

![](img/04ca18b5fa165263c0af79dce91682b7_112.png)

![](img/04ca18b5fa165263c0af79dce91682b7_113.png)

![](img/04ca18b5fa165263c0af79dce91682b7_114.png)

Here we have our max heap we're going to pop off the seven and we know that as the max element in this list。

 it's going to end up in the end of our list right so we're going to pop off that seven。



![](img/04ca18b5fa165263c0af79dce91682b7_116.png)

![](img/04ca18b5fa165263c0af79dce91682b7_117.png)

And basically。

![](img/04ca18b5fa165263c0af79dce91682b7_119.png)

Put it at the end of our list。 So he sort can be done in place。 So I think over here。

 we kind of just like。

![](img/04ca18b5fa165263c0af79dce91682b7_121.png)

Shi we pop this off and then we shift everything over one。 You can kind of think about it like that。

 And then we're going to pop the7 onto the end of R。 So that's what RA looks like now。

 And then when we reheapify our max heap。We have to take the maximum child of the root that we replaced right and heify that up。

Oh actually sorry， I misspoke。 So when we take the seven out。

 it's going to swap with the four down here， sorry I didn't make these slides very good and then the four is going to basically bubble down over here because it should swap with six right so the four comes up to the root and then four is going to bubble down and exchange places with it's the larger of its children because it is in the max heap right so now we're going end up with four over here we have our max heap again and then we're going to repeat the process we're gonna to pop off6 and we know that six is the next largest element in our array So six is going to swap over here with the zero。



![](img/04ca18b5fa165263c0af79dce91682b7_123.png)

![](img/04ca18b5fa165263c0af79dce91682b7_124.png)

![](img/04ca18b5fa165263c0af79dce91682b7_125.png)

![](img/04ca18b5fa165263c0af79dce91682b7_126.png)

![](img/04ca18b5fa165263c0af79dce91682b7_127.png)

And now we have to reheify so the zero is going to come up here in the root and since this is no longer our max heap we're going to swap with the larger of our children so we're going to swap with the four and four is going to be the new root right repeating the process we pop off the four and then we swap the two and the four over here right so now we know that the last three elements of our array have been sorted and then two is going to come up to be the new root right and then this is a max heap right because two is greater than zero so we don't need to reheappaify so we're going to pop off the two and put that into the next largest position of our array。



![](img/04ca18b5fa165263c0af79dce91682b7_129.png)

![](img/04ca18b5fa165263c0af79dce91682b7_130.png)

And after that， we only have one node left it's just a zero。

 so we're going to pop the zero off and we have our sorted list for Heap ort， and I think that's it。



![](img/04ca18b5fa165263c0af79dce91682b7_132.png)

Awesome。