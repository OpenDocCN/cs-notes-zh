# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P104：29_02_06_路径压缩-Hopcroft-Ullman分析二-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

I need to begin by setting up some notation and definitions。 The first one is that of rank blocks。



![](img/9b2e1ddf90e3e7b4b733649553822bf9_1.png)

So for a given value of n， the number of objects in the data structure。

 we define the rank blocks as follows， zero gets its own block as does one， The next block is2，3，4。

 The next block starts at five obviously and the last entry is going to be two raised to the fourth。

 so two raised to the final rank of the previous block also known as 16。

The next block then starts at 17 and goes up to two rays to the last rank of the previous block。

 so two rays to the 16， also known as 65，536。And so on。

 until we have enough rank blocks that we capture N。Actually， if you think about it。

 because ranks can only be log in， you only have to go up to log in。

 but that actually doesn't affect anything by more than a constant。

 so let's just go ahead all the way up to end。So how many rank blocks are there Well focus just on the largest member of each of the rank blocks the largest member of a given rank block is the largest member is2 raised to the largest member of the previous rank block so for the teeth rank block roughly what you have as this largest entry is two to the two to the two raised T times how many times you need to do that before you get in by definition you need log star n so that's how many rank blocks there are that's where log star n enters the analysis。

So I realize this must be a very inscrutable definition， these weird rank blocks。

 so let me tell you how you should think about them。

They meant to encode an intuition that we had on the previous slide where we said well。

 you know we should be happy if the rank of an object's parent is a lot bigger than the rank of that object itself。

 why well when we traverse that object's parent point and we make a ton of progress through the rank space and you can only make a ton of progress through the rank space a limited number of times so that means a small number of parent traversals that means fast fines。

So these rank blocks are just a very clever way of defining sufficient progress when we're going to be happy with the gap between the rank of an object and the rank of its parent。

 specifically we're happy whenever these two ranks lie in different rank blocks。

 we're not happy if they lie in the same rank block So for example。

 if you're at an object and it has rank 8 and you go to its parent and it has rank 18。

 then we're happy because 18 is in the rank block after the one that contains 8 On the other hand。

 if you go from rank 8 to rank 15， then we're not happy we're going to call that not a big gap between the rank of the object and the rank of the objects's parent。

So let's build on that idea to make another definition。

So consider a given snapshot in time that is we've done some sequence of fines。

 we've done some sequence of unions， So we're going to call some objects at this point in time good and some of them bad。

 here are the criteria by which you are good。 So first of all， if you're the root of your tree。

 you're going to be good。 if you're a direct descendant of the root。

 that is if your parent is the root of your tree， then you're also good。

 if not though if you're deeper in the tree， then you're going to be good if and only if your parents' rank is in a strictly larger rank block than your own rank So that is in the previous example。

 if your rank is 8 and your parents is 18 then you're good。

 if your rank is 8 and your parents is 15 and your parentss not a root， then you're going to be bad。

The role of this definition is to split the work that we do into two parts。 First of all。

 we do some work visiting good nodes。 Second of all， we do some work visiting bad nodes。

 The work we do visiting good nodes will be very easy to bound。 No problem。

 We'll have to do a separate global analysis to bound the total work that we do visiting bad nodes。

 This dichotomy is exactly the same as something we faced when analyzing Cruesco's algorithm when we implemented it using the union find data structure with eager unions。

 There you'll recall， there were some parts of the work in Cresco's algorithm that were easy to bound just iteration by iteration。

 For example， every cycle check cost only constant time。

 But then there is this more complicated type of work。

 namely all of the leader pointer updates that we had to bound globally via a separate argument。

 The exact same thing is going to happen here。 Good nodes will be able to bound operation by operation。

 whereas the bad nodes will have a global analysis controlling the total work done over all of the operations。

So more precisely， I've set up the definitions so that the work done visiting good nodes is bounded by Big O of logstar N every single operation。

Indeed， how many good nodes could you possibly visit during a find operation， say from some object X。

 So you started actually， and you traverse these parent pointers going all the way up to the roots。

 Well， there's the roots。 Theres the descendant of the roots。 So that's 2。 So let's set those aside。

 What about the other good nodes that you encounter on your path。 Well， by definition。

 when you visit a good node， The rank of its parent is in a bigger rank block。

 Then the rank of that node itself。 That is every time you traverse a parent pointer from a good node。

 you will progress to a subsequent rank block。 Well， there's only log star and rank blocks。

 So you can only progress through subsequent ones log star n times。

 So the total number of good nodes you're going to see is big O of log star N。

So now let's go ahead and express the total amount of work that we do over all of the fine and union operations and these two quantities work done to good nodes。

 which we now know is just log star an each operation， plus the visits to the bad nodes。

 which at the moment we have no idea how big it is。

So now let's proceed to the global bound on the total amount of work that we perform on bad nodes。

 and this is really the crux of the whole theorem。So let's just review the definitions real quick。

 what does it mean that you're a bad node so first of all you're not the root second of all you're not a direct descendant of the root that is you have a grandparent and third it is not the case that your parents' rank is in a later rank block it's in exactly the same rank block as your own rank that's what it means that you're bad。

So how much work do we spend on bad nodes， well let's analyze it one rank block at a time。

 so fix an arbitrary rank block， let's say for some integer K。

 its smallest rank is k plus1 and its biggest rank is2 to the K。

Now I told you what our two main building blocks were first one is the rank lemma I'm going to ask you to remember that in a second but first I want to put to use our other building block。

 which is that path compression increases the rank gap between objects and their parents that's what we're going to use right now。

Specifically， consider a fine operation and a bad object X that it visits by virtue of being bad。

 X is not the root， and it's not a direct descendant of the root。

 So root is a higher up ancestor than its parent。 Therefore。

 X's parent pointer will be changed in the subsequent path compression。

 It will be rewired to point directly to the root， a strict ancestor of its previous parent。

 Therefore， the rank of its new parent will be strictly bigger than the rank of its previous parent。

 That's going to keep happening every time that X is visited while it's bad。

 It keeps getting new parents and those new parents keep having ranks strictly bigger than the previous one。

 Well， how many times can this happen before the rank of X's parent has grown so big that it lies in a subsequent rank block。

The biggest value in x's rank block。 And remember， x is a non root is rank is frozen forever。

 so it's always stuck in this rank block。 Once its parent rank gets updated。

 let's say at least two to the K times。 Then the rank has to be so big that it lies in the next rank block。

 At that point， X is no longer bad。 It parent pointer makes so much progress。

 It goes to another rank block。 Now， we got to call it good。And of course。

 once X becomes good in this fashion， it will be good forevermore。 It is not a root。

 It will never be a root again。 It rank is frozen forever， and its parents' rank can only go up。

 So once you're good， once your parents' rank is sufficiently large。

 it'll be sufficiently large for the rest of time。All right， so we're almost there。

 Let's just make sure we don't forget anything that we've done。

 So the total work we're bounding in these two ways。 So first of all。

 we visit logstar n good nodes for each operation。 So overall M operations that over M log star N for the good nodes。

 plus there's the number of visits over the M operations to the bad nodes。

 we're going bound that work globally but we're going to proceed rank block by rank block。

 So we're fixing one ranks K plus1 up to2 to the K。

 what we showed on the last slide is that for every object X whose final frozen rank lies somewhere in this rank block。

 The number of times it gets visited while it's bad。

 the number of times it can be visited before it becomes good forevermore is bounded above by2 to the K。

So we've now used one of our key building blocks that path compression increases the ranks of parents。

 now let's use the other building block the rank limit。

The rank lema you'll recall says that in any given moment in time and for any possible rank R。

 the number of objects that currently have rank R cannot be any bigger than n over2 to the R。

 so let's use the rank lemma and apply it to upper bound how many nodes could possibly have their final frozen ranks lying somewhere in this rank block could have their final frozen ranks somewhere between K plus1 and2 to the K。



![](img/9b2e1ddf90e3e7b4b733649553822bf9_3.png)

So let's just sum over all of the ranks in the rank block。 So starting at K plus1。

 going up to 2 to the K。By the rank lemma for a given value of I。

 we know there's a most n divided by2 to the I objects that eventually wind up with rank I。

 and by the usual geometric sum， this whole thing can be upper bounded by n divided by2 to the kid。

So this is now starting to look like a magical coincidence of course we made a number of definitions in the analysis specifically we structured the rank blocks so that this magic would happen。

 specifically the number of inhabitants of a rank block n over two to the K times the maximum number of visits to an inhabitant in the rank block while they're bad times two to the K that's actually independent of the rank block。

 we multiply these two things together， the number of visits per object2 to the K。

 the number of objects n over two to the K， what do we get， we get n。

Now this was only counting the number of visits to bad objects in a given rank block。

 but there aren't them any rank blocks， remember there's only log star n of them。

So that means the total amount of work spent visiting the bad nodes。

 summed overall of the rank blocks is a big O of n times log star of。

 combining the bounds for the good nodes and the bad nodes。

 we get quantity M plus n times log star event。At the beginning I mentioned that the interesting case is when M is big omega of n in that case。

 this boundage is big O of M times log star nEssential if you have a very sparse set of union operations。

 you can just apply this analysis to each of the directed trees separately so that's it that's the full story。

 a complete analysis of the brilliant hot craft omen analysis log star n on average operation time under path compression brilliant as it is。

 you can do even better That's the subject of the next couple videos。

