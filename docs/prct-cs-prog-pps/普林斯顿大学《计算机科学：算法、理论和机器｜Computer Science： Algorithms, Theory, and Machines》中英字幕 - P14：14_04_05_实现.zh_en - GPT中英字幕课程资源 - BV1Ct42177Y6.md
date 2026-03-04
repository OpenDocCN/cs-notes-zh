# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P14：14_04_05_实现.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/54718c0b5973e22a94e4c749161b3864_0.png)

We'll follow through the standard method that we do for implementing an abstract data type。

 looking at the instance variables in constructor and the client code and methods。

So let's just review what it is that we want to do。

 so we have an idealized model of an associated storage mechanism and what we want is an ADT that allows us to write Java programs that use and manipulate symbol tables and here's the API for that ADT that we articulated early on。

And then we have these performance specs， and we don't consider an implementation to be a symbol table unless it meets these specs。

The order growth of the running time should be low algorithmic at worst。

The memory usage should be linear in the size of the collection if it's not emptyty and there shouldn't be any limits within the code on the collection size。

 so that's what we're going to embark that's the challenge we're going to embark on right now。Okay。

 so we've made the data structured choice that we're going to use at BST。

 so what do the instance variables in the constructor look like？Well。

 there's only one instance variable， that's the root。

Now we do need this private class that we're going to use to。

Build up the binary search tree and it's got those fields key in value and then references to the left and right subte。

 and then a small constructor that will initialize the key in value。And that's it。

 that's one instance variable， and then the private class that describes the data type that is a node。

Okay， what about the test client， we already looked at that。

 that's the frequency counter test client that we looked at before that tries out all our code and so that's we expect it to do the frequency count and actually print out the keys in sorted order。

 the example we did before we sorted them again based on the frequency count。

 but this is the behavior that we expect from our symbol table。And then there's the methods。

 so these are is empty as the binary search tree empty， well， if the roots null it's empty。

The put method， that's the code that we looked at when discussing the BST data structure and we'll see it again on the next slide in the same with the get method contains。

 we just get the key and see if it's associated with null that our convention allows us to implement contains with that one liner。

And then iterable， we talked about that one as well， and we'll summarize it again on the next slide。

So those are the four components of the data type implementation。

And here's the complete code again it fits on the slide maybe a slightly smaller font than others。

 but not too bad， so that's the instance variable， the nested class。

 the methods so those are the public methods that are in the API and then each one of those is supported by a recursive helper method。

 that are private methods that are not visible to the clients and then we have our test client。

So that's a complete implementation of the symbol table using the binary search tree。

And this is just a quick trace to see what it does for our example。

 so we have it and then was comes and not even showing the frequencies just focusing on the keys。

Then the arrives to the left of was best is smaller than it， so it gets added on the left of it。

 and then of is bigger than it left less than was less than the and so forth。

 so you can see the binary search tree getting built up by new nodes getting added at the bottom。

Next， we have to look at the analysis and try to understand this performance and do we meet the performance specifications that we've set？



![](img/54718c0b5973e22a94e4c749161b3864_2.png)

![](img/54718c0b5973e22a94e4c749161b3864_3.png)