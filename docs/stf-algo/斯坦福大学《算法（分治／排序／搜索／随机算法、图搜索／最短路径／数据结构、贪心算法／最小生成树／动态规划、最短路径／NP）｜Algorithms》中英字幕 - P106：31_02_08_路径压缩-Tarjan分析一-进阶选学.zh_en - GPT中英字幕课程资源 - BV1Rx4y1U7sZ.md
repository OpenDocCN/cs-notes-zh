# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P106：31_02_08_路径压缩-Tarjan分析一-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/ec90e4ab647cbf714ec867bc2d5626d1_0.png)

So in this video we're going to prove Tns inverse Ackerman bound and the performance of the Union find data structure with union by rank and path compression Frank。

 I hope you're kind of excited this is one of the crown jewels in the entire history of algorithms and data structures。

Let me remind you what the bound says， you've got a union find data structure。

 we're doing laser unions， we're doing union by rank， we're doing path compression。

 and for an arbitrary sequence of M find and union operations。

 the total amount of work you do over the sequence of operations is bounded above by M times alpha of n where n is the number of objects in the data structure and alpha is the inverse ackermen function that we defined in the previous video。

I want to give a shout out here to Dexter Koin's beautiful book， The Design and Analysis of Alrithms。

 it is his analysis that I will be following closely here。

So it's true that nearly stating Tns bound is non-trivial。

 we had this entire video defining the ackerman function and its inverse so we could make sense of the statement that said we're well positioned to approve Tns bound In fact the template of the proof is going to very much mirror what we already did for the log star analysis by Hocroft and Omen。

 so in that spirit let's review what were the two basic workhors。

 the two building blocks that drove forward the Hocroft Omen analysis。

So the first building block is the rank lima which dates back all the way to the video's prepath compression。

 and remember the rank limma gives us control on how many objects can exist with a given rank and in particular that upper bound is decreasing exponentially with the rank。

 it's n over2 to the R objects at most with a given rank R。

But of course we needed a second building block to exploit the facts that we were using the path compression optimization。

 so how did we quantify the progress made by path compression。

 while we argue that every time a node has its parent pointer updated in path compression。

 it acquires a new parent with strictly larger rank。

So you can think of the hotcroft o analysis as a clever and essentially optimal exploitation of these two building blocks。

 How did we use them Well we defined a notion of rank blocks and each rank block had size two raised to the size of the previous rank block Why were rank blocks useful while they allowed us to measure progress as we followed parent pointers we defined an object to be good if following its parent catapulted you into a subsequent rank block because there's only a log star number of rank blocks you can only visit log star good nodes on any given find operation So that gave us a per operation bound of a log star for visits to good nodes and then for visits to bad nodes。

 we used the second building block to argue that every time you visit a bad node the rank of its parent increases and that can only happen so many times before the rank of this object's parent is so much bigger than this object's rank itself that the node has to be good。

 you have to make a lot of progress by following its parent pointer。And the point is。

 if we want to do better than the Hocroft omen analysis。

 we're not going to do better by taking these same two building blocks and exploiting them in a better way。

 that can't be done， so we need to do is have a better version of one of the two building blocks。

 so the key idea and targets analysis is to have a stronger version of the second building block we're going to argue that path impression doesn't merely increase the rank of nodes parents by one。

 but in fact it increases typically the rank of objects parents buy a lot。

And what's kind of amazing is the length of the proof we're about to do is really basically the same as that in the hotcroft omen analysis and the steps match up almost perfectly。

 so the bound is even better， the argument is even more ingenious。

 it's even harder to imagine how one would come up with this idea oneself。

 but as far as checking it as far as understanding it the complexity levels are roughly the same as what we've already done in the log star analysis。

 so here we go。So in this slide， I'm going to give you a definition and the point of the definition is to measure how much progress we make in terms of ranks when we follow a nodes parent pointer。

 So the definition here is going to play exactly the same role that the definition of rank blocks played in the Hocroft Oman analysis。

So what I'm going to define is a number， a statistic measuring the difference。

 the gap between the rank of an object and the rank of its parent。

 So this definition is only going to make sense for non root objects X。

 One thing I want you to remember from previous videos is that once an object is not a root。

 it will never again be a root and its rank will never again change。

 So non root objects have rank fixed forevermore。So we're going to use the notation delta of x for the statistic。

 and the definition of delta of x is the largest value of k， such that a sub k。

 this is the ackerman function， remember， such that a sub K applied to the rank of this object x is bounded above by the rank of x's parent。

 so the bigger the gap between the rank of x as parent and x's rank。

 the bigger the value of delta of x。So let me talk through some simple examples just to make sure this makes sense and also review the ackerman function a little bit。

So first of all， let me just point out that delta of x is always non negative for any non rootot object X。

So why is this true well remember and this goes all the way back to our union by rank discussion。

 the rank of an object's parent is always at least one more than the rank of that object and the function a sub zero recall we define just as the successor function so for every object that's not a root it's always true that its parent has rank at least one more than it and that means we can always at least take K to be zero and have this inequality be satisfied。

Now， when is it going to be true that an object X has a delta value at least equal to1。 Well。

 that is equivalent to stating we can take k to be 1 in this inequality and the inequality holds。

 So let's remember what is the function a sub1 in the previous video we discovered that was just the doubling function so we can take K equal to one and have this inequality satisfied if and only if the rank of the nodes parent is at least double the rank of that object。

Similarly， an object X has a delta value equal to at least two。

 if and only if we can take k equal to2 on this right hand side of the definition and have this inequality be satisfied。

 So let's recall what the function a sub2 is， a sub2 of R is just R times 2 to the R。

 So an object X has delta value equal to 2， if and only if its parents rank is substantially bigger than its own rank in the sense that if it has rank R。

 its parents rank has to be at least R times2 to the R。And in general， the bigger the value of delta。

 the bigger the gap between the rank of the object X and the rank of its parent， and of course。

 because the ackerman function grows so ridiculously quickly。

 the gap between this object's rank and its parent's rank is growing massively as you take delta to be larger and larger。

 So now that we understand this better， one thing that should be clear is that the delta value of an object X can only go up over time so remember we're talking only about non-route objects X。

 so the x's rank itself is frozen forevermore， the only thing that's changing is it's acquiring potentially new parents through path compression and each new parent's rank is bigger than the previous one so the gap in the ranks is only going up and therefore the delta value of this object X can only go up over time。

So one final comment you'll recall in the Hographth almonman analysis the way we defined rank blocks ensured that there weren't too many of them that are only log star。

 similarly here， the way we're defining the statistic delta guarantees that there are not too many distinct delta values that objects can take on。

So we've already argued that Dlta is an integer that's at least zero。

 and we can also bound it from above， at least for any object X that has rank at least two。

 which will be good enough for our purposes， if an object X has rank at least two。

 its value of delta cannot be any larger than the inverse acromen of n than alpha of n。

And this is really just by the way we define the inverse ackerman function alpha。

 we defined it as the smallest value of k， such that if you apply a sub kta 2。

 that catapults you beyond n。And since ranks of objects are bounded above by n。

 actually they're even bounded above by log n， but in particular， by n。

 that means you'll never see a delta value bigger than alpha of n for any object X that has a rank at least two。

So that completes the definition of the statistic delta of x and once again the point of the statistic is to quantify progress through rank space as we traverse a parent pointer from an object。

 so in the hot graph omen analysis we used rank blocks for that purpose here we're using the statistic delta of x and now we have to redefine good and bad objects to reflect this different measurement for progress for gaps between ranks of objects and ranks of their parents。

So that's what I'm going to provide for you on this slide， a definition of good and bad nodes。

 and this definition will play exactly the same role as it did in the Hocroft Omon analysis for the good nodes we'll be able to just get a per operation bound for how many visits we make to them and then we'll be stuck with and this will be the main part of the proof。

 a global analysis arguing that the total number of visits to bad nodes over a sequence of operations cannot be too big。

So the bad objects will be those that meet the following set of four criteria。

 if an object fails to meet any of these four criteria， it will be called good。

So the first two criteria will be familiar from the hotcro omen analysis， so first of all。

 roots get a pass and direct descendants of roots also get a pass so to be bad it must be the case you're neither a root nor are you the child of a root。

So what's the motivation for these two criteria while it's exactly the same as it was in the Hocroft Omen analysis。

 it's just to ensure that bad nodes after they're visited on a find get their parent pointer updated so remember when you do path compression after you've done a fine from an object X all the way up to its corresponding root。

 everybody's parent pointer gets updated except for the root and except for the child of the root。

 those two nodes keep the same parent pointer so to make sure we have progress we want to exclude the root and the direct descendants of the root from being bad will' account for them separately。

The third criterion is not conceptually important， it's just for technical convenience。

 sort of an artifact of the way I've defined the inverse Ackerman function。

 where we're going to give nodes that have rank 0 or1 also a free pass， so in order to be bad。

 we're only going to worry about the case where the rank is at least two。

So the final criterion is really the ingenious one and it's the one that ensures that when you do path compression。

 typically objects， parents ranks will increase extremely rapidly， not just by one。

And this criterion says for an object X to be bad， it has to be the case that it has some ancestor Y。

 so an object you get to by traversing parent point is from x that has exactly the same value of delta。

 so if an object X has delta of x equal to 2 for it to be bad。

 there has to be some ancestor object Y that also has a delta value equal to 2。And again。

 if x fails to meet any of these four conditions， then x gets a pass， X is called a good object。

Now I said that the role of this definition is going to be to split the work done into two groups and that we're going to be able to easily bound even on a per operation basis。

 the number of visits to a good node， so the next quiz asks you to think about that carefully。

All right so the correct answer is B， it's theta of the inverse acroman function of n。

 and this is really one of the points of how we defined good and bad nodes。

 we guarantee that there cannot be too many good nodes whenever we do a fine operation。

So to see why this is true， let's just count up the number of nodes along a path that can fail to meet each of the four criteria。

Well so the first criterion was we give roots a free pass。

 so there's at most one node that's good because it's a route， Similarlyly on a given path。

 there's at most one object on that path that's a direct descendant of the root。

Because ranks always strictly go up when you follow parent pointers。

 there can be at most one object of rank0 and at most one object of rank1。

 so we at most two objects get a free pass because of the third criterion。Well。

 let's think about the interesting case， nodes that are good because they fail to meet the fourth criterion。

 How many can there be。 Well， let's focus on a particular value of Deltas。

 Let's say think about all of the objects along a path that have deelta of x equal to 3。

 There may well be lots of objects on this path with Delta x equal to 3。

 Maybe there's like 17 of them。Call the highest the closest to the root。

 such object Z of these 17 objects with delta x equal to 3。

 Z is going to be the only one that is good。 The other 16 objects with delta x equal to 3 are going to be bad。

 Why， while any object other than Z has an ancestor， namely Z with exactly the same deelta value。

 So that those 16 objects do meet the fourth criterion， they will be classified as bad。

 summarizing for each of the alpha of n possible values of Delta， only the uppermost object。

 the object closest to the root without that particular delta value can possibly be classified as good。

 So that bounds at alpha of n， the number of objects that fail to meet this fourth criterion。

 that gives us the total bound on the number of good nodes on any path。



![](img/ec90e4ab647cbf714ec867bc2d5626d1_2.png)