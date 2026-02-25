# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P62：2 - Fall 2022 Discussion 11 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/9c8046b67eebe3bf09cd5dbd98feabb6_0.png)

Problem1 asks us to implement the longest prefix of method within a try。

 which will return the longest prefix within that try of some given string。So for instance。

 this try has the strings that are written out on the right hand side。 So CR RY S T is one prefix。

 and then T R Ie。 S is another one。If we try to get the longest prefix of the string crystal。

 it should return C， R， Y， S T。If we try to get the longest prefix of the string， Chris， CR R Y S。

 it should just return CR R Y S。

![](img/9c8046b67eebe3bf09cd5dbd98feabb6_2.png)

So one thing to note about the skeleton code for this problem is that uses this class called string builder and string builder functions very similarly to our basic strings in Java。

 except instead of using the plus sign to concatenate to a string， use dot append。

 And the only difference here is that the string builder is slightly more efficient for adding on to a string。



![](img/9c8046b67eebe3bf09cd5dbd98feabb6_4.png)

Now itd be a good time to take a look at the problem and the skeleton code and pause the video and try to figure out on your own how to solve this problem。

 I'll give you a couple seconds。Okay， hopefully you've paused the video and taken a shot at how to write out this algorithm。

 We're going to go with the solution together。So the basic idea is that we want to iterate through all the letters in the key and then traverse the try for each character in this key until either we've traversed through all the characters or we've hit a point within the try where we have no more children that match the next character。

In that case， we'll just end our loop and return early。

 and we'll keep track of all the characters we've coveredd so far， and that'll be our return value。

So let's see this algorithm in action。

![](img/9c8046b67eebe3bf09cd5dbd98feabb6_6.png)

Given this crown on the right hand side。

![](img/9c8046b67eebe3bf09cd5dbd98feabb6_8.png)

We'll start our traversal from the root， which is pointed to you by this curve pointer。Here。

 we're trying to get the longest prefix of the string crystal。

 So we expect it to return the string C， C， R， Y， S T。

We're going to get the first character of the given key string， which is the letter C。

And we're going to see if the children of our current node contains that character。

That's what this if statement is checking for when you have Kdon map。

That map contains all the children of the current node。

So we're going to check if the children contains a sea。And because it does。

 we don't execute that brake statement。Instead， we'll update our current pointer to that child node。

 and we'll add that child node to our output。So now output just contains a letter C。Okay。

 so our loop iterates and we get the next letter in our key， which is a letter R。

 So we'll check whether the node C has a child with the letter R and it does。

 So we'll advance our curve pointer again and we'll append this R to our result。

 So now our result is C R。We keep going。 the next letter is now a Y。

 We'll check if the node with R has a child with the letter Y and because it does。Again。

 we'll advance our pointer and append Y to our result。So we keep repeating this process。

 checking if S is a child because it is we event S。

And then checking if tea is a child because it is we pan T。Once you get to the A and crystal。

We'll check whether or not this T node has an A as its child and because it doesn't。

 we will trigger this brake statement within the F statement。And return。

 whatever our prefix has appended to so far， which is just the letters C， R， Y S T。



![](img/9c8046b67eebe3bf09cd5dbd98feabb6_10.png)