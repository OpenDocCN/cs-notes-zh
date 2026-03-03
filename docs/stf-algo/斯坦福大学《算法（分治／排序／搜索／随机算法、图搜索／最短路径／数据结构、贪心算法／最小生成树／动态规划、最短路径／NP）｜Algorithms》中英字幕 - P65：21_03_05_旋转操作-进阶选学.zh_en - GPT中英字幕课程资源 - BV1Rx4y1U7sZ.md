# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P65：21_03_05_旋转操作-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this video， in the next， we're going to take it to the next level and peer under the hood into implementations of balanced binary search trees。



![](img/090e437f1d2ca4b353be386228a2a670_1.png)

Now， frankly， the nitty gritty details of all balanced binary search tree implementations get pretty complicated。

 and if you really want to understand them at a fine grain level。

 there is no substitute for reading and advanced algorithms textbook that includes coverage of the topic and or studying open source implementations of these data structures。

 I don't see the point of regurgitating all of those details for you here。

 what I do see the point in doing is giving you the gist of some of the key ideas in these implementations。

 In this first video I want to focus on a key primitive that of rotations。

 which is common to all balanced binary search tree implementations， whether it's red black trees。

 AVL trees， B or B plus trees， whatever all of them use rotations。In the next video。

 we'll talk a little bit more about the details of red black trees in particular。

So what is the point behind these magical rotation operations。

 where the goal is to do just constant work， just rewire a few pointers。

 and yet locally rebalance a search tree without violating the search tree property。

So there are two flavors of rotations， left rotations， and right rotations。 In either case。

 when you invoke a rotation， it's on a parent child pay in a search tree。

 If it's a right child of the parent， then you use a left rotation will discuss that on this slide and a right rotation is in some sense。

 an inverse operation， which you use when you have a left child of the parent。

So what's the generic picture look like when you have a node X in a search tree and it has some right child Y。

Well， X in general， might have some parents。X might also have some left subre。

 let's call that left subre of x capital A， it could of course be empty。

And then why has its two subre。 Let's call the left subtre of Y B and the right subt C。

It's going to be very important that rotations preserve the search tree property。

 So to see why that's true， let's just be clear on exactly which elements are bigger than which other elements in this picture。

 So first of all， Y being a right child of x Y is going to be bigger than X。Now， all over the keys。

 which lie in the subree A， because they're to the left of X。

 these keys are going to be even smaller than x by the same token。

 anything in the subree capital C that's to the right of Y。

 So all that stuff is going to be even bigger than y。What about subre capital B。

 What about the nodes in there， Well， on the one hand， all of these are in x's right subre。

 right to get to any node in B， you go through x， and then you follow the right child to Y。

 So that means everything is B is bigger than X。 Yet， at the same time。

 it's all in the left subtre of Y。 So these are all things smaller than Y。

 summarizing all of the nodes in B have keys strictly in between X and y。

So now that we're clear on how all of the search keys in the different parts of this picture relate to each other。

 I can describe the point of a left rotation。 Fundamentally。

 the goal is to invert the relationship between the nose X and Y。  Currently， X is the parent。

 and Y is the child。 We want to rewire a few pointers so that Y is now the parent and X is the child。

Now， what's cool is， given that that is our goal， is pretty much a unique way to put all of these pieces back together to accomplish it。

 So let's just follow our nose。 So remember the goal。

 Y should be the parent and X should be the child。 Well， X is less than Y。

 and there's nothing we can do about that。 So if X is going to be a child of Y。

 it's got to be the left child。😊，So your first question might be， well， what happened to x is parent。

 So x used to have some parent， let's call it P。And now x's new parent is Y， Similarlyly。

 Y used to have a parent X。 And there's a question， what should Y's new parent be， Well。

 Y is just going inherenther x's old parent P。So this change has no bearing for the search tree property。

 either this collection of nodes was P's left subtree。

 in that case all of these nodes were less than P， or this subtree was P's right subtree in which case all of these are bigger than P。

 but P could really care less which of X or Y is its direct descendant。Now。

 let's move on to thinking about how what we should do with the subtes， A， B and C。

 So we have three subtes。 We need to reassemble into this picture。 And fortunately。

 we have three slots available。 X has both of its child pointers available。

 and Y has its right child available。 So what can we put where。Well， a is the sub of stuff。

 which is less than both X and y。 so that should sensibly be X's left child。

That's exactly as it was before。 By the same token， capital C is the stuff bigger than both X and Y。

 So that should be Y the bigger nodes right child just as before。

And what's more interesting is what happens to subre capital B。 So B used to be Y is left child。

 but that can't happen anymore， because now X is wise left child。

 So the only hope is to slot capital B into the only space we have for it。 X is right child。

Fortunately for us， this actually works。 Sing B into the only open space we have for it。

 X's right child does indeed preserve the switch tree property。 Re。

 we notice that every key in capital B is strictly between x and y。 Therefore。

 it better be an x's right sub tree and it better be in Y's left subre。 But it is。

 That's exactly where we put it。😊，So that's a left rotation， but if you understand the left rotation。

 then you understand the right rotation as well because the right rotation is just the inverse operation so that's when you take a parentchild pair where the child is the left child of the parent and now you again want to invert their relationship you want to make the old child the new parent and the old parent。

 the new child。And once again， given this goal， there really a unique way to reassemble the components of this picture so that the goal is accomplished so that y is now the parent of X。

So what are the laudable properties of rotations， Well， first of all。

 I hope it's clear that they can be implemented in constant time。

 All you are doing are rewiring a constant number of pointers。 Furthermore， as we've discussed。

 they preserve the search tree property。So these nice properties are what make rotations the ubiquitous primitive。

 common to all balanced search tree implementations。

So this of course is not the whole story and a complete specification of a balanced search tree implementation。

 you have to say exactly when and how you deploy these rotations。

 you'll get a small taste of that in the next video。

 but if you really want to understand it in more depth。

 I again encourage you to check out either a comprehensive data structures textbook。

 check out a number of balance search treere demonstrations which are readily available on the web or have a peek at an open source implementation of one of these data structures。



![](img/090e437f1d2ca4b353be386228a2a670_3.png)