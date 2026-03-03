# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P100：25_02_02_按秩合并-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/0b0bacd842c21ca8652947a6a1dacea1_0.png)

So let's start thinking about this alternative lazy unionbased approach to the Union find data structure in some detail。

 to get this to work as quickly as we want to， we're going to need two optimizations。

 this video will introduce the first of those optimizations， union by rank。

So let's have a quick slide making precise what we learned in the previous video so in our new implementation。

 it's still the case that each object has one extra field。

 you can think of it logically as a pointer to some other object really it's just recording the name of some other object but the semantics have changed in our first implementation of union find with eager unions this field we call it a leader pointer and the invariant was that every objects pointer points directly to the leader of its group in this lazy union implementation we are relaxing that invariant so I'm going to change the name I'm not going to call it a leader pointer I'm just going to call it a parent pointer and the new relaxed invariant is that the collection of everybody's parent pointers induces a collection of directed trees。

Each tree in this collection represents one of the groups in the partition that we're maintaining。

 each of these trees has a root vertex that is a vertex which points back to itself。

 it is these root vertices， these root objects that we think of as the leaders of these components。

 so as before we're going to refer to a group by the name of its leader vertex and that leader is by definition the root of the corresponding directed tree。

One way to think about things is that when we had eager unions。

 we again associated a directed tree with each of the groups。

 but we also insisted that it was a super shallow， bushy tree that it had depth only one that is all you had was a root。

 the leader， and then everybody else who pointed directly to the leader in this lazy union implementation were allowing the trees to grow deeper。

 We don't insist that they have only one level below the root。

So as far as the initialization at birth in a union fine data structure just consists of end de generaterate trees。

 each object just initially points to itself and is a root at the beginning。In general。

 how do you implement find from some object well you just have to return the leader of its group and we know you can get to the leader just by traversing parent pointers from X until you get to a root until you get to some object that points back to itself。

 that's what you return at the end of the fine call。

 how do you do union while given two objects X and Y， you have to find the respective roots。

 so you just invoke the fine operation twice， once for x to get its root S1。

 once from Y to get its root S2 and then you install either S1 or S2 as a child of the other。

 so you do one pointer update after the two finds。So for now I'm going to leave union underdetermined。

 I'm not going to give you a rule to decide which of S1 and S2 becomes the child of the other and the next quiz I want you to think through you what would be the worstcase running time of these operations if we make that choice arbitrarily。

 if we just pick S1 or S2 arbitrarily to become the child of the other。All right。

 so the correct answer unfortunately is the last one。

 both fine and union can actually blow up to linear time operations if you're not careful about how you implement the union。

So why is this true well first let me just point out that B is definitely not the correct answer。

 whatever fine in union's worst case running time is is definitely the same for both of them。

 remember union reduces to two calls to fine plus constant work so that's going to tell you that they're both going to have the same operation time in the worst case。

Now， why is it linear， the reason you're stuck with linear time is because the trees that you build through a sequence of unions can。

 in the worst case， become very scraggly。And to see what I mean。

 imagine you just do a sequence of unions and at each time you're unioning a group with just one object into the group that you've built up so far。

So if you union together a group of size two and a group of size1， well if you choose arbitrarily。

 maybe you make the group of size1， the new route。So now you've just got a chain of the three objects。

 maybe you union in another singleleton group and arbitrarily you choose the Sleton group to be the new leader that gives you a chain of four objects。

And so on。 So if you do a linear number of unions and you're not careful about who you make a child of the other。

 you might well end up with a chain of linear length。

 And then if you do fines for the objects toward the bottom of that chain。

 they're gonna require linear work。 And again， union has a subrout of fines。

 So it's going then take linear work as well。So when you see this example。

 you know I hope your immediate reaction is well geeez， we can certainly do better than that。

 we can just be somewhat intelligent with when we do a union which of the old roots do we install as the child of the other one？

There's a rough analogy with how we made a natural optimization with our eager union implementation of Union find there we had to make some kind of choice between which of the two old leaders do we retain。

 We retain the one from the bigger group to minimize the number of liter updates。

 So here the natural thing to do is well， look at which of the two trees is already deeper。

 and we want to keep the root of that deeper tree。 That's to avoid it from getting deeper still。

 So we install the root of the shallower tree as a child of the deeper one。

 Let's make that precise on the next slide with the notion of the rank of an object。

So the rank is just going to be a second field along with the parent pointer that we maintain for each object。

 it's just going to be some integer。Let me tell you how I want you to think about the ranks at least for now so I'm going to give you some semantics。

 very natural semantics， but I want to warn you they're only going to hold valid for the next couple of videos when we introduce something else called path compression。

 these semantics are going break down， but initially this is how I want you to think about ranks。

 it's going to be the maximum number of hops required to get from a leaf of x's tree up to X itself。

 So for example， if x is a root， this is going to be the worstcase length。

 the maximum length of any leaf to root path in the tree。So just to make sure this is clear。

 let me draw a quick example。So here in blue I've shown you one particular union find data structure that has two groups。

 now it's very easy to compute the rank of leafs that's zero because the only path from a leaf to that node is the empty path。

There are two nodes that have rank one。Then the root of the bigger tree has rank2。

And if you think about it， in general the rank of a node is going to be one plus the largest rank of any of its children。

 for example， if you're a node X you have a child Y and there's some path from a leaf Z up to Y that requires five pointer traversals while going from Z all the way up to U at X is going to require six pointer traversals。

And of course， when you initialize the data structure you you want to set everybody's rank to zero because everybody's just in a tree by themselves at the beginning。

This notion of rank is going to be a super crucial concept throughout this entire sequence of lectures on Union fine。

 so make sure you understand this definition， I encourage you to draw out some of your own examples。

 do some computations to get a better feel for the concept。

For the moment we're just going to use rank to avoid creating scraggly trees。

 so let's go back to the bad example in the quiz let's remember what the intuition was。

 we wound up with this long chain and therefore really bad worstcase running time for our operations because we were stupidly taking a tree it was already pretty deep and installing it as a child under a single node under a super shallow tree thereby producing a tree which is even deeper so the obvious way to avoid that is when faced with merging together a deep tree and a shallow tree。

 you install the shallow tree as a child under the deep one that's going to slow down this deepening process as much as possible so we can make that precise just using this rank notion notice that the rank is exactly quantifying the depth of a tree so the rank of the root of a tree by this invariant is equal to the depth of the tree So if you want to make the shallower tree。

 the child of the other one that means you want to make the smaller rank tree the child of the bigger rank tree。

This optimization is what is meant by union by rank。

There still remains the case where the two roots have equal rank that is where the two trees that we're refussing have exactly the same maximum path length。

 and in that case we do just arbitrarily choose one of them so in the pseudo code I've written here。

 I've arbitrarily chosen Y root to be the one that remains the root x's root S1 is going to be installed as a child of S2。

 but again you can do it either way， it's not going to matter。Now we're not off the hook yet。

 remember， this is a data structure where we're intending for an invariant to hold these semantics for the ranks as quantifying worst case path length to the node。

 and we made a modification to the data structure。 We rewired somebody's parent pointer。

 So now it's our responsibility to check does the invariant still hold。 and if it doesn't still hold。

 then we have to restore it， hopefully using minimal extra work。

So in this quiz we're going to think through how ranks change when we do a union。

 remember that notation we're the middle of a union of the objects X and Y S1 and S2 refer to the ranks that is the leaders of the groups of the trees that contain X and Y respectively the first thing I want you to think through and convince yourself of is that for objects other than S1 and S2 other than the pair of objects that are involved in the actual pointer rewiring。

 nobody's rank changes so make sure you think that through and convince yourself ranks are invariant except possibly for the objects S1 and S2。

In this quiz， we're going to drill down on how do the ranks of S1 and S2 change。

 given that we took one of them and rewired its parent pointer to point to the other。



![](img/0b0bacd842c21ca8652947a6a1dacea1_2.png)

Okay， so the correct answer to this quiz is the fourth one。So remarkably in many cases。

 there's no change at all to anybody's ranks， including S1 or S2 if the ranks were different before the union。

 both of the ranks stay the same。 The one exception is when you take the union of two ranks which are equal。

 then whichever one is the new root and then the pseudocode that I showed you S2 is chosen to be the new root It rank gets incremented。

 it goes up by one。 I think the easiest way to see this is just with a couple pictures。

 a couple examples。So let me just draw two directed trees in the corresponding ranks。And in this one。

 S1 has strictly bigger rank， its rank is 2， so we install S2 as a child under S1。

So recomputing the ranks in the fuseed together tree， we see that again。

 the rank at the root at S1 is2， the same thing as it was before it didn't go up。

 So what's the general principle here。 Well， in general， suppose you have these two trees。

 and suppose the first one's root S1 has a bigger rank， say rank R。

 What does that mean So that means that there exists a path from a leaf to the root S1 that requires a full R hops And in the second tree by virtue of its rank being less than R most R-1。

 It says that every single path from a leaf to the root S2 of that tree uses only-1 hops。

 So when you install S2 is a child under S1。 Well， you know the length of every leaf to root path Now the root is S1。

 It's only gone up by one。 you just have to get to S2 and then one more hop。

 you make it all the way to S1。 So if all those paths took a most R-1 before。

 all the paths all the way up to S-1 to S1 take a most R hops now。

 So the worstcase path length has not gone up That's exactly what happens in this example。

 So it's true that when we install S2 under S1 we have yet another path that requires two。

That goes through S2， but we had one previously so the rank doesn't go up。

 the worst case pathlink exactly the same as before。

And this is same kind of reasoning explains why the rank has to get bumped up by one when you fuse together two trees that had the same rank。

 so suppose S1 and S2 both have rank R well then both of them have a leaf to root path that requires a full R hops and now when you install S1 is a child under S2。

 that path where you needed R hops to get from the leaf to S1 now to get all the way up to S2。

 you need one more hop so now suddenly there exists a path from a leaf to the new root S2 that requires a full R plus1 hops。

 that's why the rank's got to go up。