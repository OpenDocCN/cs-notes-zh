# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p18 P18 01_冒泡排序 -BV1QuJVzpEKE_p18-

![](img/6539017ba4afbc73c145fed963749291_0.png)

In the next few videos， we'll be exploring a classic computer science problem。

 The problem involves sorting a list of objects from smallest to largest。As you'll soon see。

 there are many different ways to do this。In this lecture。

 you're going to learn about the bubble sort algorithm。



![](img/6539017ba4afbc73c145fed963749291_2.png)

To learn about bubble sort， we'll start with an example。Here is the first list that we'll sort。

It has the value of 7，3。5 and2。And we're going to follow the bubble sort algorithm to sort it。

I're going to start at index0， which I'm going to label with I。And work towards the end of the list。

 which I'm going to label with E。We'll start by bubbling the largest item in the list into the rightmost position。

We do that by comparing the IM index I， the7 with the IM index I+1， because7 is greater than 3。

 we'll swap these。Now the three is it index0 and the seven is at index 1。

The rest of the list is unchanged。E still labels the last position。

We move the I to above index 1 because we're about to compare the item at index 1 with the item in index2。

We compare the item at index I with the item at index I plus1，7 it's larger than5。

 so those items are samp as well。The I is now above the item at index 2， and the E again。

 is still over the last item of the list。The item at indexex I。

 the7 is compared with the item at I plus1， the do， and those items are swapped。

We've now completed one pass of the bubble sort algorithm， and the largest item in the list。

 the7 is in its correct sortded position。We'll start the second pass of the algorithm。This time。

 the end is the second last item of the list。The last item is already sorted。

And we still start at the beginning， so we'll label that with I。

We use this line to distinguish the unsorted part from the sortded part。Like before。

 we compare the item at index I with the one and I plus 1， and we swap if necessary。 In this case。

 we don't need to swap the5 and the three。Next， the five is compared with the two。

 and they are swapped。We've reached the end of the second pass。

 and the five is now moved into its correct ordered position。The second last position in the list。

There's one more pass to do。The sorted part of the list now has two items in it。I begins at index0。

 and this time the end is at index 1， the last item in the unsorted part of the list。

The item at index I is compared with the  one and I plus 1， and the three and two are swapped。

The third pass through the algorithm is complete， and the list is now sorted。

Now that we've seen a specific example， we'll draw a few pictures of the state of the list in general as the algorithm progresses。

At the beginning， the entire list is unsorted。After some number of passes have been completed。

 part of the list is unsorted and part is sorted。 The unsorted part goes from index 0 to index end。

End of the algorithm， the index end is at index0。And all of the items of the list are sorted。

To be precise， the item at index 0 is technically unsorted。

 but we know that it's smaller than the rest because it's been compared to the others。

Now let's implement the algorithm。Who'll keep track of the index of the last unsorted item of the list。

Initially， end will refer to the index of the last item in the list because the entire list is unsorted。

We know that we need to make several passes through this algorithm， and in our implementation。

 we'll do that with a while loop。We stop when n is equal to zero， so we continue as long as it isn't。

In each pass， we bubble once through the unsorted section of the list to move the largest item to index end。

 At that point， the sorted section of the list has grown by one。 So we decrease the index end by one。

Starting at index0 of the sorted section， we compare the element at index I with the one in index I+1。

 if it's larger than it， we swap the items。

![](img/6539017ba4afbc73c145fed963749291_4.png)

Notice that we're using a new notation。The listed index I is assigned the item of the list originally at I+1。

 and the listed I+1 is assigned the item originally at Inex I。Also， notice the for loop petter。

 The unsorted part of the list goes from index 0 to index end。But the value of I。

 the largest value of I is n of -1。 That's because in the body of the loop。

 end -1 would be compared to the item 1 greater than it， The item at index end。



![](img/6539017ba4afbc73c145fed963749291_6.png)

Finally， let's run the doc test。The test case passed， so there's no output in the shell。



![](img/6539017ba4afbc73c145fed963749291_8.png)