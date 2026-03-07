# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p17 P17 07_比较搜索算法 -BV1QuJVzpEKE_p17-

![](img/fb3a6b2893d8716a72b22e2d30d150bf_0.png)

You've learned about two ways to search for a value in a list。 One of them。

 linearar search will work on any list， regardless of whether the lists are sorted。

Binary search requires that the list is sorted， but as you've seen。

 it looks like it can be a lot faster than linear search。

 Let's poke at these two algorithms a little bit more so that we can get a feel for how good they are and when we would use one or the other。



![](img/fb3a6b2893d8716a72b22e2d30d150bf_2.png)

Computers play a lot of tricks in order to make code really fast。

 So it's hard to know exactly what to count。 However。

 we do know that there is a comparison that happens each time through the linear search while loop and that there's an assignment statement。

So let's count these comparisons and the assignment statements that happen each time through a loop。

For linear search， we see that there are two that happen in each iteration， one comparison。

And one assignment statement。Again， this is a rough， rough estimate of what goes on in code。

 But it turns out that this rough estimate is going to be good enough for us to conclude that binary search is just wildly faster than linear search。

 at least when lists are large。In binary search， we have a much simpler comparison。

 but we'll still count it as just one。We have one assignment statement， a second comparison。

 and then the result of that comparison will lead us to one assignment statement or the other。

 So we have one comparison here， one assignment statement another comparison。

 and then one of these is going to happen。 So in binary search。

 we actually have sort of four steps on each iteration of the loop。

Because the initializations and the if statement at the end of each happen only once。

 no matter how many items there are in the list， and there are about the same number of steps in both linear search and binary search。

 we're going to ignore these in our analysis。In linear search then。

 we figured there were roughly two steps per iteration。And in binary search。

 there were roughly four steps for iteration。We're going to compare these algorithms in the worst case that happens when the value is not in the list for linear search。

As an example for linear search， if my list is。One， two， three， four， five。

 so there were five items in the list and I'm looking for value maybe six then。I look here， here。

 here， here， and here， and then I'm done， so that looked at all five items。

Let's make a table of the number of items and the number of iterations。If there's one item。

 then there's one iteration。 If there's two items， there's two iterations。In general。

 if there are K items， there are K iterations。And now， for binary search。If there is one item。

 then on the first iteration。We set M， we do a comparison， we move either B or E。

 and then the loop terminates。Let's start building our table if there's one item。

 then there's one iteration。If there were。2 items。 Then we're going to throw away one half the first time for the loop。

 leaving us with one item。 And we know how many steps that's going to take。

 So if there are two items， it takes us two iterations。

Here's where things start to get kind of interesting。

I'm actually going to skip 3 and go right to four。 If I have four items in my list。

 then in one comparison， I'm throwing away about half。And that means that Im。

 I end up with a two item list。 Well， it took me one step to get to this point。 So that means that。

I just have one more iteration than I had when I had two items in my list。

This means that I can process twice as many items with just one more iteration。Using this knowledge。

 let's fill in a few more rows of the table。Eights twice 4， 16 is twice 8， 32 is twice 16。

 64 is twice 32， and 128 is twice 64。With  a hundred and 28 values。

 we can find the index of V in this list in only8 iterations。 Linear search would take 1 28。

Let's plot this on a graph。Our axes are the size of the list or the number of items and the number of iterations。

If the list has one item in it， then there is one iteration。Two items， two iterations， four items。

 three iterations。Eight items and four iterations。When we double the size of the list。

We increment the number of iterations by one。So thinking about this backwards。

If I have 128 items in my list， then。After one comparison， one iteration of binary search。

I end up with only 64 items left to consider。When I have 64 items left to consider。

 then in one iteration， I'm throwing away half of them so that after that iteration。

 I only have 32 items to consider and so on。This is awfully powerful。

Mathematicians have a name for this function。It's called。The logarithm， base 2。

Of the number of items。Here's one more way to think about logarithms。

It's the number of times you can divide by two in order to reach one。Song。

How many times can I divide two by two in order to reach one？Once。What about four。

 if I can divide four by two to get two and two by two to get one， that was two divides。

8ight is going to be one division by two to get four， four divided by two is2。

2 divided by two is one， so that gives us three divisions， 16 is four divisions。

 32 is five divisions。Then so on。So， let's try。To calculate the logarithm of 1024。1024 is。

512 times 2。When we divide 512 by 2， we get 256 then。128， then 64， then 32， then 16， then 8， then 4。

 then 2， and then one。 So there's one division，2， three divisions， four divisions，5 divisions。

6 divisions，7 divisions，8 divisions，9 divisions。1en divisions so。The log base2 of 1024。Is going to。

Produce， what did I say，1，2，3，4，5，6，7，8，9，10。Module math has a log function。

This function returns the logarithm of a number with a given base here are bases two because we're dealing with binary。

If I ask what the logarithm of 2 is in base 2， it tells me one。If I ask what the logarithm of  two。

 a foreign in base 2， it tells me 2。8 is 3。 The logarithm of 16 and base 2 is 4。

 and the logarithm of 32 in base 2 is 5。So let's see if we can get an impression for just how much faster binary search is by looking at。

The number， well， that's 1 million。 Let's do 1 billion。

So I'm just going to delete these commas because I'm not allowed to use them when I'm writing an integer。

Now linear search on a billion items is going to take a billion iterations。

What is the logarithm of 1 billion？In base 2。Just under 30。

 So it's going to take 30 iterations of binary search in order to find a number in a billion items。

Let's call binary search and linear search on a long list of numbers to see just how different these two are。

We'll search for a value we know is not in the list。So with 10 million items。

 binary research is nearly instantaneous。Linear search is noticeably slower。Here we go。

See profile is a module that contains code that allows us to profile other code to profile means to measure in some way。

 See how much memory it uses， how much time it takes to run。

Function run in module C profile takes a statement to execute and then presents profiling information。



![](img/fb3a6b2893d8716a72b22e2d30d150bf_4.png)

![](img/fb3a6b2893d8716a72b22e2d30d150bf_5.png)

It uses something called execec， which takes an object which can be a string or a code object and then executes it。

A code object is something we haven't encountered yet， nor do we need it。

 because we can just use a string。 Let's try calling exec。

If we if we give it something that isn't a string， we're told that argument one must be a string。

 bytes or code object。 Okay， let's put three plus four inside quotes。There's no error。

 but we still don't know exactly what's going on。Well。Run takes a statement。

 Perhaps exec can take a statement as well， maybe an assignment statement。

When we do the function call， indeed variable X is created。

Let's try assigning a string to variable Y。Remember that L refers to a list with 10 million items in it。

Let's call function run module C profile with a call on binary search。

 looking in that list for value that isn't there。We see a table。There were six function calls。

 that took very little time。There was one call that took the total time of no seconds。

 and it was on the string that we passed in。There was one call on binary search。

 There was one call on Exec one call on lend and one call on a method disable of the profiler。

 that last one is completely irrelevant to our analysis。Here we see that in linear search。

 there was one call on the function linear search it took nearly three seconds to complete。

There were。10 million and2 calls on methodth L。 That took nearly a second， just by itself。

That gives us a hint that we could optimize linear search。Let's call L on L outside of the wild loop。

 and then use variable length。Everywhere instead of the colon limb。



![](img/fb3a6b2893d8716a72b22e2d30d150bf_7.png)

When we run this again and profile it， we see that we went from nearly3 seconds for the near search down to just over one and a half。

 That's a remarkable speed up。However， that doesn't even come close to how fast binary search is。

This is all if the list is sorted and all in the worst case。In the best case。

 where we search for the first item of in the list， linear search is also blazingly fast。

Mathematical analysis of algorithms and profiling can give us significant insight into how algorithms work and why they are so good or bad。

This analysis of algorithms is actually a discipline within computer science。

 it's a subfield of computer science， and people study this kind of thing for a living。

