# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p15 P15 03_线性搜索 -BV1QuJVzpEKE_p15-

![](img/d7c764cbea5404f66a9e6c445ab20da2_0.png)

Using the tools we've seen so far， our computer programs can only do one thing at a time。

We've used methods that seem to do more than one thing at a time， though， for example。

 list dot sort sorts a list of numbers， and list dot index finds the index of value in the list。

We're going to now explore these searching and sorting algorithms。

 It turns out that they're really interesting。 and there are a ton of versions of both sorting and of searching。

😊，We're going to start now by taking a look at linear search。

 where we examine items one by one in a list。

![](img/d7c764cbea5404f66a9e6c445ab20da2_2.png)

When we called help on method index in class list， we see that it returns the first index of the value that we're searching for。



![](img/d7c764cbea5404f66a9e6c445ab20da2_4.png)

![](img/d7c764cbea5404f66a9e6c445ab20da2_5.png)

For example， if we have L refer to the list with ABC， A and D as string。

 and we ask for the index of the A， we get back 0。

![](img/d7c764cbea5404f66a9e6c445ab20da2_7.png)

We don't get back3 because it returns the index of the first occurrence of the value in the list。



![](img/d7c764cbea5404f66a9e6c445ab20da2_9.png)

When we ask what the index of the string C is， it tells us 2。

 And when we ask for the index of string D， it tells us 4。Here's how method index works。



![](img/d7c764cbea5404f66a9e6c445ab20da2_11.png)

When it's looking for D， it first looks at index0， then1， then2， then 3， and then it index4。

 and it finds what we're looking for， and it returns that index。



![](img/d7c764cbea5404f66a9e6c445ab20da2_13.png)

Linear means arranged in a line， and we're essentially looking along the line from the start to the end in the list。

Here's how we're going to draw lists for the rest of this week。

 We're going to place the values inside the list instead of drawing an arrow to the value outside of the list。

 This is to save clutter to make our drawings a little bit more clean。

We'll also draw our index variables above the indices to which they refer。Here， I refers to0。

If we're looking for， say， value V， which refers to a D， then what we'll do is we'll say， hey。

 is that value e at E index I， And if it is， then we're happy， we return I if it isn't。

 as in the case we have here。 What we'll do is we will add one to I， making I refer to one。



![](img/d7c764cbea5404f66a9e6c445ab20da2_15.png)

![](img/d7c764cbea5404f66a9e6c445ab20da2_16.png)

![](img/d7c764cbea5404f66a9e6c445ab20da2_17.png)

Is the D at index I now， No， it isn't。 So we'll add one to I。 How about now， no， O。

 is L at index I equal to D， No， O， how about now， yes， we've done it。 L at index I is D。

 And so we have found the value we're looking for。 So we will return I in our linear search function。



![](img/d7c764cbea5404f66a9e6c445ab20da2_19.png)

We'll need to decide what to do if the value arere looking for is not in the list。 For example。

 what if it refers to the string。In that case， let's return -1。

We're going to continue to explore linear search by writing a function that implements it。

This function takes a list and any object and returns an integer indicating the index of that object in the list。

Here's an example call where we search for two， where two appears at index 0。

Here's another where we search for 5， which is at index 2。

And now we'll search for a number that isn't in the list。 We should get back-1。

And our description is return the index of the first occurrence of V in L。

 or return -1 as if V is not in L。Now， we'll draw our list again in order to help us reason about this algorithm。

I starts off at 0。Here's the code for that。We don't know yet when we're going to stop。

 So we'll leave the condition blank， but we do know that we add one to eye each time through the loop。

After a couple of iterations， we have this general picture。I is some index。

 We know that V is not here。Now， let's look at what this looks like after this loop is over。

What if V was not anywhere in this entire list， What value does I have。Well。

I is to the right of this dividing line that I've。Drawn。

And in this situation where the value is not anywhere in the list， I is going to end up。

Equal to the length。Aveil。So one way to stop this loop is for I to reach the length of valve。

We therefore can continue as long as I is not equal to the length ofel。The other situation。

In which we can stop is。When I find thee。At index I。

That means that as long as I is not the length of valve and。V is not equal to L at index I。

I add one to I。After the loop terminates， I can check to see if I is equal to the length of L to know whether V was not in the list。

 If it wasn't， I'll return -1。Otherwise， that means that I found fee， and I can return I。

Our algorithms that we're dealing with are starting to get more complicated。

 Drawwing pictures like this can really help develop correct code the first time we write it。

 which in the long run will save us a ton of time。

![](img/d7c764cbea5404f66a9e6c445ab20da2_21.png)

We can actually get our initialization。 I get 0 straight from this picture right here。



![](img/d7c764cbea5404f66a9e6c445ab20da2_23.png)

If I have my list。And I need the V not here section to be empty。 That puts the line right there。

 and that puts I。Rightrite at index0。

![](img/d7c764cbea5404f66a9e6c445ab20da2_25.png)

This picture is called the loop invariant。 An invariant is something that doesn't change。

 And this picture describes what's happening inside the loop after any number of iterations before index I。

 we did not see a V。We have not yet examined anything from index I onward。

 And so we still need to search it。

![](img/d7c764cbea5404f66a9e6c445ab20da2_27.png)

Lopinvaris and pictures like these are going to play a big part in the rest of the lectures this week。



![](img/d7c764cbea5404f66a9e6c445ab20da2_29.png)