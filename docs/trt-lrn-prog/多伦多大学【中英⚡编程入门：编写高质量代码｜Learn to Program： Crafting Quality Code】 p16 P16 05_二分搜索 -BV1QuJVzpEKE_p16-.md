# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p16 P16 05_二分搜索 -BV1QuJVzpEKE_p16-

![](img/4ed5fd6f7b069e8b0dd071c1ed6efbe5_0.png)

Linear search searches for a value in a list starting an index era。

 It proceeds linearly through the list until it finds the value。 If there are n items in the list。

 then linear search might look at all n items。 For example， if the value is not in the list。

 then it will examine each item in the list。Linear search works on both sorted and unsorted lists。

 However， if we know that the list is sorted， we can do much。

 much better using an algorithm known as binary search。



![](img/4ed5fd6f7b069e8b0dd071c1ed6efbe5_2.png)

Here is the function header and do string for binary search。Like with linear search。

 it takes a list and a value and returns the index of the first occurrence of that value in the list or -1。

 if the value is not in the list。Binary search only works if Ella is sorted。

It turns out that it also only works if each item in L can be compared to V。

Here's an example to get you used to the idea Here。 we have asortred list of numbers。

 and we're searching for five。We want the first occurrence of5， the one at index 3。

Let's draw a dividing line。 This line divides the items that are less than V from the items that are bigger than or equal to V。

 Notice that this includes the item in index 3， the five that we're looking for。

Let's say we have a list of 100000 items。We can calculate the middle index pretty easily。

 and we can examine that value。If that middle value is less than the value we're looking for。

 then because it is distorted， we know that all the values to the left of it are also less than the value we're looking for。

 And therefore， we can eliminate 50000 items with just one comparison。

So part by through our binary search algorithm， we have three regions in our list。

 on the left are all the items that are less than V。

 on the right are all the items that are greater than or equal to V。

 and in the middle is the unknown section， the items we know nothing about yet。

Let's mark the beginning of that unknown section with variable B and the end of the unknown section with a variable E。

When this function is called。We know nothing about any of the values in the list。

 and so B will start off at index 0， and E will start off at index length ofel-1。Here's the code。

At the end of this process， the unknown section is empty。Everything on the left is less than V。

 Everything on the right is greater than or equal to V。The unknown section is empty。

 variable B is to the right of the line。And variable E is to the left of the one。

This is what it looks like at the beginning。 And this is what it looks like at the end。

So this loop is going to continually march B and E closer to each other until they cross。In our loop。

 we'll calculate the midpoint between B And D。Then we'll examine it to see if that item is less than V。

If it is， we can set B's new value to M plus1， because all these values are less than V。

On the other hand， if the item in index m is greater than or equal to v。

 then we can move E to index M minus1 because all of these values are greater than or equal to V。

Let's write our loop。We'll figure out the loop condition in a moment。

 But if the item an index M is less than v， then we're going to move B to index M plus 1。

 And if the item an index M is greater than or equal to V， then we'll move E to index M -1。

And now for the loop condition。In the end。B is greater than E。

We continue then as long as B is less than are equal to E。

 because and there are still items in the unknown section。And here's the condition。

All that's left is to calculate the value for M。We take the average of two numbers like this。

 but because we don't want a floating point number， we need to do integer division。This code。

Produces this， but we not quite done。What if this value isn't V？Well， in that case。

 we are supposed to return minus1。

![](img/4ed5fd6f7b069e8b0dd071c1ed6efbe5_4.png)

We have to be a little bit careful here because all of the values might be greater than or equal to V。

 or they might all be less than V。If they're all greater than or equal to V， then this section here。

Takes up the entire list。B is on the right， E is on the left， B must be0。I can look at Elin Ne0。

 that's fine。But what if they're all？Less than V。Then this line ends up over on the right because this whole section takes up the whole list。

 And in that case， B ends up here and E ends up there。 B is now the length of L。

 And I can't use that as an index。 I'll get an index error。I'm going to write a if statement。

In one situation， I'm going to return -1。 That's when V is not in the list。Otherwise。

 I'm going to return index B， because if V is in the list。

 B is going to be the index of the first occurrence of V。

I know that one situation where V is not on the list can be detected by comparing B to the length of L。

So if B is the length of L， I want to return -1。Or if L index B is not equal to V。

 then I also want to return minus1。If B isn't the length of L and L it B is equal to V。

 I want to return index B。Let's write some do test code。If this module is the one being run。

 then we'll import doc test and we'll run our tests。Keep your fingers crossed。



![](img/4ed5fd6f7b069e8b0dd071c1ed6efbe5_6.png)

And we win。