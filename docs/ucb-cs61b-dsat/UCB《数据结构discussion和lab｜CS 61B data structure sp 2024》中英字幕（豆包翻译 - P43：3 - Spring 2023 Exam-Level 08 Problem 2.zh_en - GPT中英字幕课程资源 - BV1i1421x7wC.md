# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P43：3 - Spring 2023 Exam-Level 08 Problem 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/271452ce01d3b7755eff8e2af79b3dbb_0.png)

Everyone， this is Sherry， and this is the spring 2023 exam level 3 walkthrough in this video。

 I'll be going over problem 2， hashing on crazy。 This problem just really tested your knowledge of hashing and how to use the equals function and how external chaining works。

 So make sure you understand those topics。 Also， as I noted in the previous video。

 I do have a bit of a cough。 And I'm too lazy to edit out all my coughings。

 So please just bear with me as I walk through this。😊，嗯。

So in this problem we'll be dealing with objects and an externally chained hashmap。

 so like the problem states the EC hash mapap begins at size4 and never grows so let's just draw those boxes there's the zero12。

 three exactly four boxes in our hashmap and this is externally chained which means that when we add keys and they hash the same bucket we'll just add a linked list at that bucket。

Okay， so with that in mind let's just jump into this problem and the first thing we're going to do is we're just going to execute everything line by line and draw any objects that are created so we notice that on line two and three we create two taA objects Sherry and Noah so i'm going to write Sherry and then Sherry's name is Sherry the goat。

And then she has semester value 10， and then NOAA is also a TA object and he has named NOAA and semester value 20。

So the next thing we do is we do map。put sherry1， so that means we're going to put sherry in our map with value1 and the key is this sherry object。

So the first thing we have to figure out is where does Sherry hash to well sherry has semester value 10 and the TA class the hash code is just defined as the semester so what we're going to do is we're going to take the semester and we're going to modify by the number of buckets。

Which in this case is four， which gives us two， so Sherry is going to go in bucket2。

And she's going to have value one， so this is our key value pair。

 the value is one and the key points at sherry and note that the key points at the sherry object it does not like create a copy of the sherry object so just make sure that you remember that we're working with objects and Java is passed by in Java when we like reference an object we put a pointer to it and we don't copy it。

Okay， the next thing we do is map up put NOAA2， so again we're going to hash NOA 20 mod4 is zero。

 so NOA is going to go and bucket zero with value2。SoSo let's do that。

 this key is pointing at NOAA and he has value2。Okay。

 the next thing we do isOAA dot semester plus equals2。

And so we're going to increment a semester of 22， note that we do not rehash NOAA the only time we rehash something is what we call putton。

And since we're not calling N NoOAA put yet， just because we change the hash code of NOAA doesn't mean we actually change which bucket he's in。

But in the next line， we do call Ma。putOAA， and in this case NoA' is going to go in bucket2 because now 22 modd 4 is equal to 2。

And so when we have two things that collide in the same bucket， for example。

 now noA's going to go in bucket two， but there's already a key here。

 we just check if they're equal to each other by the dot equals method。

And the T do equals method just checks the first letter of each name and since Sherry and Noah have different first letters of their names。

 they're not equal， so what we're going to do is we're actually going to add another box here。

We're going to add another box here， let me move NoAah a little bit。

And this points here toOAA and we're going to add another like another linkless node and this is going to point at our new key and it's going to have value three because we put it with value3 so notice will be there when we have a collision between two keys that are not equal we just add an extra linkless node and we keep adding more linkless nodes for any keys that hash to the same bucket。

Okay cool and now we say sherry dot name equals n Harry。

 so instead of sherry the goat Sherry's name is now giving me n Harry and if we look at this now we're going to do map dot put NOA again with value 4 and in this case if when we go to bucket2 because 22 mod4s 22 we see that sherry and NOAA are actually equal by the dot equals method because。

If we compare the first letter they're the same so when we have two keys that are equal that hash to the same bucket instead of creating a new link list node we just replace the value so in this case we're going to replace the value and notice that we don't change the key the key does not change because by the definition of equals these two keys are equal so it doesn't matter which one is actually pointing which one the key actually a pointss to by the definition of equals method so we just change the value to four and we don't do anything else。

Okay， next thing we do is sherry。 semester plus two so now sherry has semester 12 and we're going to do mapped output Sherry 5 so now sherry's going to hash to bucket zero and since sherry and Noah are still equal they have the same first letter of their names again this is just going to replace a value with five and nothing else is going to happen。

Okay， finally， we put Sherry's name back to Sherry。And we create a new TA object cheese guy。

 So let me move this down a little bit。And we're going to put cheese guy up here。

And Cheese Gu has named Sam and Se value 24。And we're going to do map do put cheese Gu 6。

 so 24 mod 4 is equal to zero， so he's going to go and bucket zero and。If we look at bucket zero。

The first key is for NOA， and since NOA and Sam have different first letters of their names。

 they are not equal by the equals method， so we do have to create a new linkless node and this says value6 and is going to point to cheese Gu。

And that is the final state of our map， so we're going to have notice that both of these keys are in different buckets。

 but they actually point to the same object， otherwise we have the sherry and cheese Gu and that's the final state of our hashmap。



![](img/271452ce01d3b7755eff8e2af79b3dbb_2.png)

あ。