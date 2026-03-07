# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p19 P19 03_选择排序 -BV1QuJVzpEKE_p19-

![](img/3c164f9996ca43fd95e5c0930bb91f00_0.png)

You'll now learn about another algorithm for sorting objects from smallest to largest。

 This one is called selection sort。

![](img/3c164f9996ca43fd95e5c0930bb91f00_2.png)

We'll use this example list。We'll use I to mark the index of the first position in the unsorted Pro list。

 and initially the entire list is unsorted。Next， we need to find the index of the smallest item in the unsorted part of the list and swap it with the item at indexex I。

Let's pass over the items of the list， keeping track of the smallest one。

Three is the smallest I've seen so far。Three is still the smallest。Now two is the smallest。

And two is still the smallest。 so when I reach the end of the list。

 I find that the smallest item was the w at index 2。

Now I'll swap the aimate index I with the one at index2。We've now completed the first pass。

 It's time to start the second pass。There are now two parts of the list。

 a sorted part and an unsorted part index I represents the index of the first item in the unsorted part of the list。

Like before， we pass over the items in the unswordted part of the list， looking for the smallest。

7even is the smallest I've seen so far。 now three is the smallest。And three is still the smallest。

 so we swap the value at position2，3 with the one at position I。Next it's time for the third pass。

After passing over the items in the unsorted part of the list。

 we find that five is the smallest and we swap it with the item at index I。On the last pass。

 there's only one item left in the unsorted part。And the list is sorted。

To summarize at the beginning， the entire list is unsorted， and index I is equal to 0。

After some passes have been completed， there are two parts of the list， a sortred part。

 and an unsorted part。I represents the index of the first item in the unsorted part of the list。

At the end， the entire list is sorted and I is equal to the length of the list。

Let's implement this algorithm。As we saw in the example。

 we complete length of the list number of passes through this algorithm During each pass。

 we find the index of the smallest item in the unsortted part of the list that is the list from index I to the end。

 and we swap the smallest item with the one at index I。To determine the index of the smallest。

 I'll use the helper function named get index of smallest that we'll write in a moment。

 Once we know the index of the smallest item， we swap the item at that index with the item at index I。

Next， let's implement that helper function。We'll use a variable to keep track of the index of the smallest item that we've seen so far at the beginning of a pass。

 the smallest item that we've seen so far will be at index I。

We then pass over the rest of the items in the unssortted part of the list。

Comparing each one to the small we've seen so far。If we find something smaller。

 we update index to smallest to refer to the index of that value。Once the loop has completed。

 we return the index of the small item from the unsorted part of the list。Let's run the doc tests。

Everything passes and we're done。

![](img/3c164f9996ca43fd95e5c0930bb91f00_4.png)