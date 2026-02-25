# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P34：1 - Spring 2023 Exam-Level 07 Problem 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/0b60c75adea195191a39d907e975d5c3_0.png)

Hi everyone， this is Sherry and this is the spring 2023 exam level 7 walkthrough in this video I'll be going over problem three is this a BST。

In this problem， we're going to take a look at some function is BST which checks a tree to see if it is a BST and first we're going to figure out what's wrong with this given function and then we're going to rewrite it so that's actually correct。

So let's just take a look， let's just start off by looking at this buggy function and figuring out what's wrong with it。

As a reminder， a BST is a tree that has two main properties， so all of its left children。

 for any node， all the left children of the loan are smaller than it。

And all of the right an children of the node are larger than it。

And so this gives our tree some nice search properties。

 which is why it's called a binary search tree。So if we take a look at this function。

 it's kind of our like normal recursive function where we have our base cases and then we have our recursive case。

So if we take a look at this， if we have an empty BST， which means a BST is null。

 then obviously it is a BST， so return true， that's our first base case。

And our other two base cases are if we see a tree that violates the BST property。

 we can immediately return false， so if the left child is like larger。

 which is what this is checking， we can return false and similarly if the right child is smaller。

 we can also return false because this violates the property of a BST。

And then we just recursively call it on both of the children and return the final answer。

So this seems fine， but actually there are several there are several trees for which this function does not work and the reason is because we only check a nodes immediate child to see if it violates the BST property so if we take a look at an example of a tree like this。

We can see that this is not a valid BST because this child12 of 10 is actually larger than 10 and what we said earlier is that everything to the left of 10 must be smaller。

 So this violates the BST property， but it doesn't actually violate this is broken this broken is BST function because what we're going to do is we're going to start at 10。

 Both of its children are valid because 5 is smaller and 15 is larger so that's good。

 we're going make a recursive call 15 is obviously fine because it has no children。

 and then we check5，3 is smaller on the left， which is good。 12 is larger on the right。

 and this is also good。 So we're actually going to say that this is a valid BST。

 but clearly it's not because this 12 violates our condition。

So what we need to do is we need to actually be a little bit more tricky and we to keep track of what values we can have even past the immediate children。

 so at this point we should know that we can never have something larger than 10 because if we have something larger than 10 that would violate our left branch here。

So what we're going to do is we're going to not just use this is broken BST function。

 we're going to add on and we're going to track the possible min。

And max values as we re curse down the tree， so we're going to keep track of what nodes we've seen so far by keeping track of the possible minimum and maximum。

And so we're going to do this with a very common function pattern that you will see in this class。

 which is we have a recursive function that calls a recursive helper and the recursive helper actually does all the recursion。

So for our starter function we're just going to call isBSD helper and we're going to call it on the tree of course。

 and then like I said we're going to track the possible minimum and maximum values so。

In the beginning we don't know anything about the tree， we don't have any values。

 so the minimum value we're just going to say is integer dot min value。

 which you could think of as like negative infinity and the maximum possible value is going to be integer dot max value。

Which you can think of as like positive infinity。And then our recursive helper function is going to take in a tree。

 it's going to take in the minimum possible value and the maximum possible value。

And then our base case is going to be similar because if。It's null， again， if we have an empty BST。

 we can just return true， this doesn't change from our original broken function。

And then we're going to check。If t dot key， so if our current key is less than the min or it's greater than the max。

This is a violation， so we're going to return false。And now our。Bace case is a little bit tricky。

 but sorry， now our recursive case is a little bit tricky because what do we return in the else case。

 we probably want to call is BST helper on the left and right。

 Well we have to be careful about what we pass in as the min and max arguments。

So let's just first set this up and let's call it on T aboutt left and we don't really quite know what these arguments are last two arguments are yet。

 so just leave them the link。And then we're also going to check is BST Hoer。On T dot right。Okay。

 and now let's figure out what should go into these arguments for min and Max for these two recursive calls。

So if we go back up to our example here。If we are at 10。

 then if we make a recursive call on the left side。

 we know that everything here has to be less than 10 by the properties of BSTs。

 so there's no minimum value that the minimum value doesn't change because this could be like negative infinity on the left and that would still be smaller than 10。

 but the new maximum value is 10 because again， nothing in this left tree can be larger than 10 by the properties of BSTs。

And similarly， if we make a recursive call on the right。

There's no new maximum value could have positive infinity on this right branch and that would still be within the bounds of a BST。

 but everything in this right branch must be larger than 10 because again。

 that's just the properties of the BST， so our new min value is going to be 10。

So if we plug these into our recursive calls。If we make a recursive call on the left， again。

 the minimum value doesn't change， but now we're bounded by t dot key。

 which is our current node value as the maximum value because everything in the left must be smaller than our current key。

And of course， a similar case is for T dot right， except that the maximum value doesn't change。

 but now we're bounded on the lower end by T dot key。And that's it for this problem。

 here's my weekly exam tip for BST problems where you have to write code。

 you will almost always have some kind of recursive function that recurs on the left and the right。

And just keep in mind this kind of like structure where you have a recursive function and you write a helper that actually does all the recursion。

That's it for this problem， good luck in the rest of 6 UB and if you have any comments or questions。

 please feel free to leave them below。

![](img/0b60c75adea195191a39d907e975d5c3_2.png)