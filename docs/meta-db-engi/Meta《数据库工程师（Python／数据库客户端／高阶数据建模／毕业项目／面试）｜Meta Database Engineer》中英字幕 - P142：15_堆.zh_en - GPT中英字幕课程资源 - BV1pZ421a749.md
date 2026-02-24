# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P142：15_堆.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

A heap may not sound like a particularly promising name for a data structure。 However。

 it is a very important organizational tool and combines some features and benefits of other data structures。

In this video， you will learn about the structure and features of heaps。

 You will also discover how heaps can be used to organize elements from least to most important and how by limiting the functionality of heaps。

 productivity can be increased。 So let's get started with heaps。😊。

A heap is a specialized data structure that is modelled like a tree。

But behaves in a similar way to a cue， though， with a notable difference of assigning priority to some elements。

Each element in a heap has a key value， and the priority can either be the smallest or the largest key value。

😊，Heaps that place priority on the lowest valued key are called min heaps and ones that place the priority on the maximum value are called max heaps。

Heaps were first introduced as a means of storing and searching data efficiently。 But since then。

 it has been recognized that there are a number of very useful operations that a heap can be applied to。

 A heap has a few select core operations that it can perform。Insert， find， underscore min。

 and delete underscore min from min heap， and insert Find underscore Mac and delete_ Mac for a max heap。

For the rest of this video， the discussion will revolve around min heaps。

 but you can reverse everything said and it will apply to a max heap。😊。

The only difference between the two is where the priority is placed。

 As with many of the data structures discussed on this course。

 these methods are the fundamental elements that constitutes a heap。

Different implementations in different languages could have additional methods added。😊。

An instance of which may be decreased key。 This is where the value of a key is changed。

 The motivation for which would lie with the priority of the key in real world instance changes。

 When discussing trees， it was mentioned that binary trees sought values in order of size。

 If the value is less than the node go down the left path。 If the value is greater than the node。

 go down the right path。

![](img/aef111c036afdce4e2540f23485213ad_1.png)

![](img/aef111c036afdce4e2540f23485213ad_2.png)

![](img/aef111c036afdce4e2540f23485213ad_3.png)

Because of this underlying architecture， heaps are often built using binary trees。

 though another approach would be to make an array act in a way that mimics the behavior of a binary tree。

 The minimum value is placed on the root node， and each subsequent value is placed on the hierarchy。

 where their value dictates。

![](img/aef111c036afdce4e2540f23485213ad_5.png)

This means that to retrieve the minimum value from a heap is O of one because it will be stored always at the root。

 Unlike a stack， retrieving a value does not cause it to be moved from the tree。Instead。

 a delete min method exists that can be called if the intent is to remove items as they are processed。

Typically， a heap would not support operations such as deleting items other than the priority element。

😊，The reason being that a heap is built for specialized purpose that involves identifying the most important item and returning this in the shortest time possible。

Then queuing up the next item of importance， deleting items in the tree would require restructuring the tree。

 and this would lead to a degradation in performance。😊。



![](img/aef111c036afdce4e2540f23485213ad_7.png)

If you are looking for a data structure that can act in this way。

 then you might consider structures other than a heap。

Insertion into a min heap is done through propagation。



![](img/aef111c036afdce4e2540f23485213ad_9.png)

Each item is inserted at the root。 A comparison is then made with the left value。

If this is less than the newly inserted item， they are swapped。

 This continues until the newly inserted item has no greater value above it。

 and the value below is lower。Insertion in a heap can be achieved in O of log N time。

Having examined the underlying mechanisms that power a heap。

 you may now have some idea of how this data structure can be applied。

Considering that its inherent structure prioritizes a particular value from a group of elements。

 the natural application would be for scheduling。This can apply to CPUs， routers or packet handling。

Additionally， one could imagine that such a structure would be useful in prioritizing certain tasks like interview scheduling。

 where the key used to store the candidate may relate to what stage of the interview process they lie at。

😊，Or what priority the role has within the organization？



![](img/aef111c036afdce4e2540f23485213ad_11.png)

Having a process that automatically applies schedules based on importance can be a huge time saving device。

😊。

![](img/aef111c036afdce4e2540f23485213ad_13.png)

In this video， you have gained a greater understanding of heaps and how they can be used to organize elements from least to most important。

 You have been shown that by limiting functionality， productivity can be increased。

 As with the selection of any data structure， It is important to find the right tool for the right job。

😊。