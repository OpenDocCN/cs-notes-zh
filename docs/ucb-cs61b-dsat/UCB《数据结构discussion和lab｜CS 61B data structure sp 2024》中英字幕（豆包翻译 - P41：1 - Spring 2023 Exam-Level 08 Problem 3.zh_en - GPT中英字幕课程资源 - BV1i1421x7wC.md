# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P41：1 - Spring 2023 Exam-Level 08 Problem 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/d9f77f27a292a28cda69daf4cf29c4e0_0.png)

Everyone， this is Sherry and this is the spring 2023 exam level 8 walkthrough in this video I'll be going over problem three buggy hash again as I mentioned the previous two videos I do have a bit of a cough I don't have time to edit out all the coughing so。

😊，Just please bear with me and feel free to skip over my coffee but yeah。

 in this problem we'll be looking at some hash code functions and determining if they're valid or not and if not。

 why they're not valid。😊，And there are basically two rules that we have to keep in mind when we have hash codes。

 which are， first of all， that the same object should always return in the same hash code。

 and the second is that if two objects are equal by the dot equals method。

 they should also return the same hash code。And those are basically the only two rules for a valid hash code。

 so let's look at these and see maybe why they're not valid。

So first we have the time zoneone class and the hash code method returns the current time and what does the current time method do well it returns the current time in the time zone。

😊，And we see that this violates one， our first rule because。

The same object could return a different hash code depending on what time it is。

 so this violates our first rule that the same object must always have the same hash code。

And if we look at the second class course， we see that this actually violates rule two。

And this is a little bit harder to see but we see that the hash code is a combination of the year offered plus the course code however。

 if we look at the equals method it only checks if the course codes are equal so for example if we have one class let's call it CS61B and the course code is5 and then we have CS61A and the course code is5。

But this year offered。Is 2001 and this year offered is 2002 well by dot equals。They are equal。

 but they're hash codes。Are not the same and this is a violation because two objects that are equal by the dot equals method must always have the same hash code。

 which is not necessarily the case here。So that's a violation of rule two。

 so actually neither of these are valid and that's because they violate the two rules that we have for valid hashags。

That's it for this short problem。But。Here's my weekly exam tip for hashing problems like these are to determine if a hash code is valid。

 all you really have to remember are these two rules and then you just have to carefully examine the hash code and see which of these two rules they violate if they do have any violations。

That's it for this problem， good luck this weekend and the rest of 6 U1B。

 and feel free to leave any comments or questions below。



![](img/d9f77f27a292a28cda69daf4cf29c4e0_2.png)