# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p118 20_18_memoization -BV1bw4m1D7MM_p118-

I want to show you one more idiom that helps us avoid repeated computations and how it's useful。

 turns out this idiom does not really use ths， but that's okay， it's still worth knowing。

 and it's called memmoorization which is not an English word。

 but it is a technical word we use for this and we really do leave the R out and call it memmoorization。

 not memorization， and it's been called that for a long time。



![](img/6ce5b32374e503fcd86dc86456ade458_1.png)

So here's the idea。If a function has no side effects and doesn't read anything that can change。

 there's no point in computing it twice for the same arguments。 If you call it twice with 7。

 you're going to get the same answer。 If you call it twice with the same list。

 you're going to get the same answer， doesn't matter how many times you call it。

 So what we could do is keep what's called a cache of previous results。

 keep some data structure that remembers， hey， if you call this function with 7。

 this is what you're going to get back。And this can be a great idea if maintaining and using the cache is cheaper than recomputing the results。

 and if people actually do the recomputations， they actually call the same function with the same argument again。

 otherwise the cache is a waste of space and a waste of time。

So this idea is really pretty similar to promises， that thing we saw with force and delay， right。

 that when we do the first force， we'll store the results。

 so any later force just has the result there。But force a delay was for ths that don't take any arguments。

 Once you take arguments， you can't just have one thing that you store for future reference。

 you need a table of them， depending on what the arguments are。

 so that's where memmoization is a little more sophisticated。

 and I'm going to show you an example where're using memmoization with a recursive function actually leads to a program that is exponentially faster。

 and so it's a common technique， something you can apply almost mechanically that could actually lead to programs that are much more efficient。

 other times they're just a little more efficient and it's still considered a convenient thing to do。



![](img/6ce5b32374e503fcd86dc86456ade458_3.png)

So I'm going to show the most of the rest of this with the code。

 I'm going to use this classic example for memorization。 This is what most people use。

 Here is an implementation of the Fibonacci function。 This is a function for mathematics。

 the same way we've been using factorial， which says that factorial of n is times factorial of n -1 with a base case of factorial of  zero is1 Fibonacci is a little more sophisticated。

 it says Fibonacci is one for both one and2， so just read the rackcet code here If x is1 or x is 2。

 it's1。 Otherwise it's the sum of Fibonacci of x minus-1。😊，And Fibonacci of x -2。

 So you see two recursive calls here。 And it turns out that these two recursive calls cause this to be a very inefficient implementation。

 This is exactly how it's defined mathematically。 You call Fibonacci1 with 30。

 you get a nice big number， like 830000。 But if you call it with 40。

 This takes about 1 thousand times longer to evaluate。

 And I don't have 1 thousand times longer to wait。 So I'm just going to stop this and say that this is not a good implementation of the Fibonacci function。

Okay， so what are we going to do about it。 Well， one thing you could do。

 which I'm not going to focus on here is throw away that algorithm and implement this other bottom up algorithm that uses a local helper function that takes an accumulator and starts at low numbers and figures out Fibonacci up to high numbers by adding the two previous numbers as you go along。

 You're welcome to look at the code。 It's not that complicated。

 I just want to admit that this algorithm exists before moving on and showing you a different way to do this efficiently that shows this idea of memoization。

So we're going to forget about that second version。 Just move on to the third version。

 I know it looks big and complicated。 We're just going to go through it line by line and see that it's just implementing this idea of keeping around all the previous results。



![](img/6ce5b32374e503fcd86dc86456ade458_5.png)

So anytime we compute Fibonacci of anything， we're going to put it in our table。

 And because we're going to do that， even when we make recursive calls。

 it's going turn Fibonacci into an efficient function。 So let's see how that works。

 So the first thing you'll notice is that Fibonacci ends up just being this helper function F。

 So I'm going to define this function F here。 and then just return it。

 And the reason why I'm doing that is I need F to use this memo table， this cache。

 This thing that is initially null， but is bound to this variable memo。😊。



![](img/6ce5b32374e503fcd86dc86456ade458_7.png)

![](img/6ce5b32374e503fcd86dc86456ade458_8.png)

![](img/6ce5b32374e503fcd86dc86456ade458_9.png)

It's essential， I don't want memo to be up at top level。

 I don't want to define memo up here because this is an implementation detail。

 I don't want to expose it to the outside world。😡，But I also cannot put it inside this function I'm going to define because if you put it inside。

 we're going to recreate a new table every time we call this function because we do not execute function bodies until we call them。

 We need it outside the table so that it persists so it's still around from one call to the next。

 and it's initially know， and we're going to use mutation to update it appropriately。



![](img/6ce5b32374e503fcd86dc86456ade458_11.png)

![](img/6ce5b32374e503fcd86dc86456ade458_12.png)

Okay， so when we want to find Fibonacci of x， so we just call x right here。

The first thing we're going to do is see is it already in the memo table。

 So here I'm using a little library function， a so that takes in something and a list and tells you if that something is in the list in the following way。

 Let me show you how this works。 you can look it up on your own in the manual if you don't get this quickly。

 So let me define a little list here。 It has to be a list of pairs。

Because pairs can have anything you want in them， but how about just three different pairs of integers here。

 so that's a little list。 X's just looks like this。

What a so does is it takes a number like three and a list of pairs。

 and it checks the car fields of the pairs for something equal。 And for the first time it finds one。

 it returns that pair。 So a so 3 x's returns 3，4， a soak 1 x's returns 1，2。

 And if it's not in the list like 6。 you do see a6 up here， but it only looks at the car fields。

It returns false， meaning I did not find it in the list。 So that's a so。

 We're going to use a soak up here。 So I had to tell you how it works。



![](img/6ce5b32374e503fcd86dc86456ade458_14.png)

So our memo table， which is initially null， is going to be a list of pairs。

 and what it's going to be is argument dot result。😡。

We're going to store in that list pairs of Fibonacci of Arg is result。All right。

 so here's what we do。If we find our answer in the table。

 so we got a pair here and everything that's not false is true， so this works。

 and return the cutter of that pair。We looked up the argument X。 We found it。Return the result。

So that's how we get our reuse。

![](img/6ce5b32374e503fcd86dc86456ade458_16.png)

In this else branch， we didn't find it。 So now what we have to do is compute it and then put it in the table so people can find it in the future。

So how do we compute it， that's what this let variable does nu ants， we say， well。

 if x is one or two， then it's one， otherwise it's adding recursive call of x minus1 and recursive call of x minus2。



![](img/6ce5b32374e503fcd86dc86456ade458_18.png)

Before we return。Change via setb memo to hold a bigger list。

 Take the old list memo cons onto it the pair of our new argument result pair so that in the future。

 if anyone needs Fibonacci of X， they'll find it in the table。After we've done that。

 return this thing that we computed， and that is the Fibonacci of the number。So this all works。

 And what might surprise you is that it's fast。 I can ask Fibonacci 3 of 1000。

 and I get this big number， No time at all。 So why is this so much efficient than the naive recursive version that couldn't even do 40。

 I don't even think it can do 35。

![](img/6ce5b32374e503fcd86dc86456ade458_20.png)

![](img/6ce5b32374e503fcd86dc86456ade458_21.png)

It looks like if it's not in the table， we're still doing these two recursive calls and it would blow up exponentially。

But we are doing two recursive calls， which everyone we do second will be very， very fast。See。

 the problem with exponential blowup is that we make two recursive calls and they make two recursive calls and they make two recursive calls and it blow up。

 blows up 2，4，8，1632。But what happens here is we make two recursive calls。😡。

The first recursive call ends up filling up the table with lots of numbers。

 The second recursive call ends up finding what it needs in the table。

 especially if the second one is with x -2。 The second one is x -1。

 It also have to do one more recursive call， but then it will find what it needs in the table。

And that's only at the top level。 After that， everything is already in the table。

 So recursively at every step， instead of making two expensive recursive calls。

 we make one recursive call。 And then for the next recursive call。

 everything is already in the table。 So this isn't just twice as fast。

 It's twice as fast at every level。 And in fact， it' taking something that would take time proportional to two to the X。

 and turning it in something that takes time proportional to X。

 Or if you really want to be picky since I have to run down this list doing a so， maybe x squared。😊。

But x squared for 1000 is nothing， that's no problem at all， whereas2 to the x。

 where x is 1000 is more than I believe the number of particles in the universe。

So that's our example， it's just a programming idiom。

 All we did was really something had nothing to do with Fibonacci itself， we created this table。

 we always checked it first。If we found it， we did nothing else。Otherwise， we compute our answer。

 and before we return， we add our results to the table for the future， and that is memmalization。



![](img/6ce5b32374e503fcd86dc86456ade458_23.png)