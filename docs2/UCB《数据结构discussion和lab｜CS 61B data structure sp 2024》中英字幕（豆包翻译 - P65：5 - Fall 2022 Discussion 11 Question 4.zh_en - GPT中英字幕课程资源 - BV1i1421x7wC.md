# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P65：5 - Fall 2022 Discussion 11 Question 4.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

This question gives us a series of C， S classes， and the prerequisites。

We want to find a way to take all these C， S classes without running into conflicts with prerequisites。

So we're going to draw a graph and then run some algorithms on this graph to determine which classes we should take in which order。

So let's start by drawing this graph。Here， we're going to take each class。

And then if that class is a prerequisite for another class。

 we'll draw a directed edge going from the first class to the second class。So here， 6。

 and A is a prerequisite for 62 and B。 So we'll draw an arrow going from 62 and A and 6 and B。Okay。

 so 6 to and B is a prerequisite for 621 C。 So we'll do the same。



![](img/2307742f09384468080c1ab9f73a76b7_1.png)

And 70 has no prerequisites， so it has no errorss going towards it， but it is a prerequisite for 170。

 So both 70 and 62 and B are prerequisites for 170。

 So we'll draw errorss going from both of those classes to the class of 170。

 And then 6 to and C is a prerequisite for 161。 and so is Cs 70。 So again。

 we'll draw two errorss representing both of these prerequisites。



![](img/2307742f09384468080c1ab9f73a76b7_3.png)

![](img/2307742f09384468080c1ab9f73a76b7_4.png)

Now we' asked， suppose that some new prerequisites were introduced。

So now you have to take 161 before you can take 170。

And you have to take 170 before you can take 601 C。

So are we still able to take these classes in a way such that we satisfy all the prerequisites before taking the class。

Take a moment to think about it and try drawing out the  errors on this graph in the way that we did before。



![](img/2307742f09384468080c1ab9f73a76b7_6.png)

So if you drew out the arrows， you'll notice that these new dependencies create a cycle。



![](img/2307742f09384468080c1ab9f73a76b7_8.png)

And because it's a cycle， we now can't possibly take all these classes in a way that satisfyis all the prerequisites。



![](img/2307742f09384468080c1ab9f73a76b7_10.png)

For example， if we wanted to take 6 to1C， we would have to take 170， but to take 170。

 we would have to take 161， but to take 161 we would have to take 6 to1C and so on so we have this kind of infinite loop where each class depends on another class which depends on it itself。

 and we can't end up taking any of those classes。

![](img/2307742f09384468080c1ab9f73a76b7_12.png)

![](img/2307742f09384468080c1ab9f73a76b7_13.png)

![](img/2307742f09384468080c1ab9f73a76b7_14.png)

![](img/2307742f09384468080c1ab9f73a76b7_15.png)

So now we're back to the original series of prerequisites。

 and we want to determine what order we can take these classes in so that we'll satisfy all the prerequisites before taking that class。

So we can do this by performing an algorithm called topological sort。

The way that topological sort works is that we're going to do a depth first traversal。

 and we're going to place each node into a list。Once we were done， visiting the note。

So note that we don't place the note in when we first visit the node， but instead。

 once all the nodes neighbors are finished being visited， then we place that note in。



![](img/2307742f09384468080c1ab9f73a76b7_17.png)

At the very end。We're going to reverse our list and that should give us our topological story。



![](img/2307742f09384468080c1ab9f73a76b7_19.png)

So let's see this algorithm in action。

![](img/2307742f09384468080c1ab9f73a76b7_21.png)

Well start by placing 62 and A on our stack， because that's the first node that we want our search to go from。

Then D F S will visit all 6 and A's neighbors， which starts with 6 and B。



![](img/2307742f09384468080c1ab9f73a76b7_23.png)

And D F S will visit all of 6 to and Bs neighbors。 So it will break ties when we're going to 621 C first。



![](img/2307742f09384468080c1ab9f73a76b7_25.png)

![](img/2307742f09384468080c1ab9f73a76b7_26.png)

And we'll visit all of 61 C's neighbors， which is just 1，61。Okay。

 so once once 161 is done being visited because it has no neighbors。

 then we'll place it into our result。

![](img/2307742f09384468080c1ab9f73a76b7_28.png)

![](img/2307742f09384468080c1ab9f73a76b7_29.png)

And now we're back to 61C。

![](img/2307742f09384468080c1ab9f73a76b7_31.png)

6 to and C has no more neighbors to visit。 So we're done with 6 to and C。

 and willll post it on our result。 And now we're back to 6 to and B。



![](img/2307742f09384468080c1ab9f73a76b7_33.png)

60 and B still has one neighbor we haven't visited yet。 So let's go ahead and visit it。

 And because 1，70 has no neighbors， we can put it into our results。



![](img/2307742f09384468080c1ab9f73a76b7_35.png)

And now we're back to 6 soon and B， and 6 to B has all of its neighbors being done visited。

 So we'll pay 6 soon B into our results。

![](img/2307742f09384468080c1ab9f73a76b7_37.png)

![](img/2307742f09384468080c1ab9f73a76b7_38.png)

And 6 and A has number neighbors to visit so on。

![](img/2307742f09384468080c1ab9f73a76b7_40.png)

So we've done a DFS of all the nodes reachable from 6 to a。

 but we haven't actually visited all the nodes in the graph yet。

 So we'll continue DFsing from any unexplored nodes。 In this case， it's just the class C70。



![](img/2307742f09384468080c1ab9f73a76b7_42.png)

![](img/2307742f09384468080c1ab9f73a76b7_43.png)

Which will place into to our stack。 And it has all its neighbors already visited。

 So let' us place it onto our post order。

![](img/2307742f09384468080c1ab9f73a76b7_45.png)

Now， if you reverse the order of all the classes here。



![](img/2307742f09384468080c1ab9f73a76b7_47.png)

We should get a valid ordering。 So in this case， it would be 7，6，2 and A，6，2 and B，1，70，6，2， and C。

 and 161。

![](img/2307742f09384468080c1ab9f73a76b7_49.png)

![](img/2307742f09384468080c1ab9f73a76b7_50.png)

You can double check yourself that in this order， we won't run into any conflicts。



![](img/2307742f09384468080c1ab9f73a76b7_52.png)