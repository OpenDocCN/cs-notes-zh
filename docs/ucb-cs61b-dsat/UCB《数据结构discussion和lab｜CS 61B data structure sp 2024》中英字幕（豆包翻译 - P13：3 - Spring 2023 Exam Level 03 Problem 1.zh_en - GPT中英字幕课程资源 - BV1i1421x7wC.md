# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P13：3 - Spring 2023 Exam Level 03 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/6b6f6b72d09379ae647e9b6da8447ad5_0.png)

![](img/6b6f6b72d09379ae647e9b6da8447ad5_1.png)

Everyone， this is Cherry and this is the spring 2023 CS61b exam level walkthrough number three。

 I'll be going over problem one boxes and pointers so in this problem we're basically just doing some practice with box and pointer diagrams and this is a really important skill to build not necessarily because you will be asked directly about box and pointer diagrams on exams but because it can be really helpful for checking or figuring out the answer to coding questions as well。

So let's just jump in。If we look at this problem， I've already drawn out line one where we create this inlist and just as a reminder the inlist itself has two properties。

 it has the first and the rest and so I'm just going to represent it as little box like this。

So I've already drawn out the first line where we create an inlist dot list of one， two。

 three and so let's move on to line two。In line 2， we do intless L 2 is a new in list。

 and the first is4， and the rest is L1 dot rest。 What's L1 dot rest。 Well， if we follow the pointers。

 we can see that this is this list。 This node here is L 1。

 So L 1 dot rest would be this two right here。 So L 2 is going to point there。

And then let's move on to line three， we see that we do L2。res。1t equals 13。

 so again we just have to follow the pointers L2。 rest is going to be this node right here and L2。

 rest do1 is going to be this2， so we're going to change the2 to a 13。Okay。

 now let's move on to line four， we see L1。ret。st。rest equals L2。

So again we just have to follow the pointers so this is L1 l1。rest is this l1。ret。

rest is here and l1。ret。res。rest so where' the last rest is going to be this null pointer here so right now it's null but we're changing it to point to L2 so let's do that and now it's pointing to L2 and I'm not actually pointing to like a specific field in L2 I'm pointing to this entire node so just keep that in mind。

Okay， On line five， we create an int list L3， and it's just one item。

 so it has 50 and then its rest is null because it has one item in it。And then finally。

 we do L2 dot rest do rest equals L3。 So again， we just have to follow the pointers to figure out what's going on so L2 dot rest is going to be。

L2。 restst is going to be this node right here and L2。ret。ret is going to be this pointer here。

 and so instead of pointing to3 now it's going to point to L3 down here。

And that is it for this problem。Here's my weekly exam tip for these kinds of box and pointer diagram problems it's just really important to keep track of your pointers and whenever you have something that has like a first and rest property。

 I just recommend drawing these two boxes and following the pointers as necessary。

Good luck in this week and the rest of 61 B and feel free to leave any comments or questions below。



![](img/6b6f6b72d09379ae647e9b6da8447ad5_3.png)