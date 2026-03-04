# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P23：23_06_01_树与森林.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/b34e64b206c7b621ddf41970d8da84ad_0.png)

Today we're going to talk about trees， this is the first second half of the course is the first of a series of lectures on applications。

 just a little bit in the way of orientation before we begin。For the first half of the class。

 the first thing we did was introduce analysis of algorithms。

 but then we have spent the rest of the time surveying the basic methods that we need in terms of mathematics in order to do scientific studies about the performance of algorithms。

 and then we finished off last time by introducing analytic combinatorics。

So this is all about mathematics and about techniques。

Now we're going and now we're going to switch to the second half of the class。

 We're going to switch to applications and we're going to talk about some basic classic combinatorial classes with lots of applications and we're going to look at。

Techniques from analytic combinatorics that we use to study them。

 including applications to the analysis of algorithms。

And this will bring us to really basic combinatorial class with all kinds of applications， trees。

 permutations， strings and triess， words and mappings。

 and we'll be using labeled and unlabeled classes alternating with ordinary generating functions and exponential generating functions。

 really applying all the mathematical techniques that we learn in the first half of the class。

So today we're going to begin with trees， and we'll start off by talking about basic definitions of trees and forests。

To begin， I'll review what we've talked about in terms of binary trees。

By contrast with the general trees that we're going to talk about today。

I recall that a binary tree is an external node or an internal node and two binary trees where the order of the internal nodes is significant。

So at the top is a root， and in this case that root has two binary trees or two。

Internal nodes as its children， and down at the bottom we have some nodes called leaves that have both of their children are external。

 and the external nodes are signified with little boxes and the internal nodes are signified with circles。

And we talked about binary tree， we've talked about those before。

 so now we refer to the level or the depth of a node in the tree。

 starting with the root at depth zero， the children of the root at depth one and so on。

 and the deepest node in the tree， that's what we call the height of the tree。

 and we'll look at other parameters of trees later on。Now remember。

 one of the first problems that we looked at in the last couple of lectures is how many barary trees are there within nodes and that's the Catalan numbers。

 and we did a derivation with a symbolic method that I'll just rush through because we've done it so many times。

 but just to get back on the notation。So we have a generating function。

 which is the sum overall objects is see to the size of that object which collects together objects by their size and we have atoms that are internal nodes and external nodes and depending on how we set the size of those atoms。

 that's what we're going to count in this case we're counting internal nodes。

And then we have a combinatorial construction that comes as is a mathematical representation of our explicit definition of what we mean by a binary tree。

And then， our basic transfer theorem translates that construction immediately into an equation on the generating function。

Which then we can solve and get asymptotic estimates of the coefficients。

So that's just a quick review of the symbolic method for binary trees just to set the context for different problems that we're going to do in this lecture。

So now in general， the mathematical classical mathematical concept of a tree is in terms of forests。

 so a forest is a set of trees and a tree is a forest with a root added to the top and there's actually just from this quick observation the generating function that enumerates forest is just one over Z or the function that enumerates trees is just Z times the generating function that enumerates forest by corresponding to adding the root。

So this is a recursive definition but these are recursive structures。

 a forest is a sequence of disjoint trees， a tree is a node called the root。

 and it should say forest is empty or secret of disjoint trees。

 tree is a node called the root connected to the roots of trees in a forest and so now a root can have any number of children including zero。

 and the leaf nodes of the nodes with zero children。So。And then the level is the same as before。

 we start with the root at depth zero， the children of the root at depth to one， and so forth。

 and the height is again the deepest node in the tree。In contrast to binary trees。

 we don't have external nodes in general trees。So that's now a question comes up immediately is enumeration。

 how many different forests are there within nodes？So these are all the forests with one， two， three。

 and four nodes。And immediately， right away， you can recognize that the catalin numbers are arising yet again。

 so there's five forest with three nodes just three individual nodes or a tree of size2 in a another node in either order or the。

No root node connected to two children or the straight line。

 which is a root connected to a child connected to a child。 noticeice that order is significance。

 a forest is a sequence of trees， and that's consistent with computer applications where we have to represent the thing in the computer some way we pick a sequence usually。

So anyway， the Catalan numbers are here and of course a tree is a root connected to a forest。

 so if you attach roots to all of those you get all possible trees and it's the same numbers with shifted over by one。

So let's look at the analytic combinatorics for deriving the catalan generating function for trees and forests。

So， and we just follow through the basic steps that we've outlined many times before and we're going to be doing this a lot。

 but a small mistake leads to completely the wrong answer， so it's good to be careful。

So F is a class of all forests and the size is going to be the number of nodes where our atoms are now。

 there's just one kind of node， and it's got generating function Z and G is the class of all trees on the same atoms and again the same size function。

So those are two combinatorial classes， and now we can use our definitions of those classes to develop constructions directly from the definitions。

What did we say we said a forest is a sequence of trees。

And a tree is a root node and a forest when that immediately corresponds to those two constructions。

And then the transfer theorems immediately give us the OGFs for those two combinatorial classes F of Z is1 over 1 minus G of z and G of z equals z f of Z。

 that's what I referred to on the previous slide。So now if we just solve that。

 we get F of Z substitute in 1 minus z f of z for G of z， and then solve for F。

 you get f of z minus Z F z squared equals 1。And that's exactly identical to the cattlean generating function。

 so it means that the number of forests within nodes is exactly equal to the number of trees within nodes。

 which is the cattlean numbers which we know the asymptotics for and the number of trees within n nodes。

 the number of forest or n minus one nodes， so it's got a factor four less。

So that's a symbolic method that shows that the number of forests and the number of trees is exactly the same。

Now， from an analytic point of view， we're happy to get the result。

 but usually in commoninatorics when you find that you have two classes that enumerate exactly the same。

 what you want to find is a bijection showing that a correspondence between every member of one class and every member of the other and in this case。

 that bijection is important because it gives us a way to represent forests and trees in the computer conveniently。

So here's how that bijection goes， every forest within nodes corresponds precisely to a binary tree within nodes。

Now forest node can have multiple children， a binary tree， a node can have exactly two children。

So the way the correspondence goes is that for every node。

 we connect it to its left child and its right sibling。

So the node at the left in the forest corresponds to the top node in the binary tree and so forth。

 And that's a one to one correspondence between forests and binary trees。

 It's another way to look at it that's even maybe easier to see called the rotation correspondence。

 If you take this binary tree。And connected up as if it were the nodes in the forest。

 you can see that you have the forest kind of rotated。

And that's a very useful and easy way to represent forests and general trees within a computer because a binary tree is easy to represent in chunks of memory where every node has whatever information is associated and its two children。

 whereas in a forest you have to deal with a variable number of children per node。

 which can be inconvenient or difficult in some computing environments。Just as an aside。

 at this point， we're thinking about is the idea of an algorithm for drawing binary trees。

And I want to show that because I'm going to be showing a lot of binary trees and the exercise of writing a program for drawing binary trees is a worthwhile exercise for everyone to do。

So the most natural approach that we use very often。

 particularly when talking about sorting and searching algorithms。Is to， well， first of all。

 the y coordinate is easy， that's just， well， it's the depth， but since they go down。

 it's the height minus the depth。So we start with the root at the highest and then just subtract one。

 so we know the Y coordinate of every node。The X coordinate of the node。

 the easiest way to set that up is to just do a recursive in order traversal of the tree and just assign x coordinates every time you reach a node。

And that's corresponding to say a recursive program says what's the coordinate of the root。

 it's the number of nodes on the left plus one， and then the X coordinate of everybody in the right side is bigger than that and you can see immediately that that is number one it's easy to assign the coordinates just doing in order a traversal of the tree。

And number two， it spaces the nodes and the tree out nicely。Usually when we draw big trees。

 we leave big binary trees， we leave out the external nodes。

Now there's a problem with this is that you get distracting long edges for some kinds of trees。

Particularly for， say binary trees that represent general trees。

 and you can use a similar algorithm like this for general trees， by the way。

But anyway that's a problem， so what we do sometimes is take the X coordinate and at every level we just evenly space the nodes。

 if there's four nodes at that level， we evenly space them in center them on the root node。

And that's a useful way to draw trees because it gives a profile of what the trees。

 how thick the trees are， how many nodes there are at each level。

 and that's an interesting thing to know about in some kinds of analyses。

So just this is what random binary tree looks like with this idea。And actually。

 when you see random binary trees。They have many， many different shapes。

 and if we were to do random trees or random forests as well。

 youd see quite a collection of different and interesting shapes。

And so the challenge that we have that we're going to go into and the reason that I wanted to draw these big binary trees is to make clear what that challenge is is that we have to analytically characterize this in some way maybe averaging over all of these or whatever it is that we're doing in terms of the analysis it's going to have to explain this kind of behavior and remarkably we're able to get very far in doing that and so that's what we'll start doing now that's just a brief introduction about trees and forests。



![](img/b34e64b206c7b621ddf41970d8da84ad_2.png)

![](img/b34e64b206c7b621ddf41970d8da84ad_3.png)