# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p14 P14 01_3-2-1-B树简介 -BV1KnLCzXEcQ_p14-

![](img/64fc78fb4afe651377757c1e88aa1474_0.png)

![](img/64fc78fb4afe651377757c1e88aa1474_1.png)

Up until now， we've discussed algorithms such as binary trees， AVL trees， arrays and lists。

 and they have incredible runtime performance in terms of big O notation。

But Big O notation doesn't explain everything。In fact。

 BigO notation assumes a uniform access time for all of our data。😡，But in reality。

 uniform access time for all of our data isn't actually the case。 Let's look at an example。

 For example， if we consider all of the Facebook profiles on Facebook。

 we might give a conservative estimate that there are 500 million users on Facebook。

 I'm sure there's more than that。And let's think about every single Facebook profile。

 We might imagine that the total amount of data that's on each profile is going to be at least 5 MB。

 Again， another conservative estimate， because likely all the photos and all of the information was in Facebook is probably going to far exceed 5 MB。

Thinking about the entire amount of space they would take to store all of this data。

 we can multiply 500 million by 5 megabytes。Doing that's going to result in us having 500 billion times5 kilobytes。

500 trillion times five bytes。 and then moving this over。

 that's going to be 2500 trillion bytes or 2。5 petabytes of data。

This is an incredible amount of data。2。5 petabytes of data is far more than you can store in any main memory on any system。

 So we're going to have to store some of that data on disk。 And by storing on disk。

 we know that that operation is going to be somewhat slower than in main memory。

The goal of a B tree is to create a data structure that's going to perform extremely well in both main memory。

 as well as in on disk。 specifically， we want to optimize the idea that we want to make as few disk seeks as possible。

 So this algorithm can be as optimal as possible。 And in fact， I said in the term disk seek。

 But what we really can think about is anywhere the data stored somewhere else。

 This might be on the cloud somewhere or this might be anywhere else。

 So let's look at how we might construct such a data structure。

 A B tree is constructed by having a node that contains a number of keys。

I'm going to draw a node as simply a large rectangle， and as part of this node。

 we're going to have several keys inside of this node。And the keys can be any value。

 I'll assume that we're going to have integers here in the beginning。

 The first key might be have the value of  one。 The second key might be 100， Then the value 2，50，400。

900 and 1600。Each of these keys are going to have a pointer to another tree node inside of it。

 So between 1 and 250， this pointer right here is going to contain another node that's going to have another set of keys。

 Everything in this node is going to be between the number 100 and the number 250。😡。

We're going to define every bee tree as having an order。

 The order of a bee tree refers to the size of the nodes。

 not the fact that the keys are insert sorted order。

The order of the B tree is the maximum number of keys that a given node can have， plus one。So。

 for example， here's an example of a B tree of order 9， having8 keys in this node。

 The goal of every single B tree is to minimize the number of network packets。

 disk seeks or whatever operation we have to get at the data。

 So we want to minimize the seeks to reach our data。

SoNow that we understand the motivation of a B tree。

 we want to actually understand how we can implement it and how we can build operations like insert and find this Be tree。

So we'll do that next lecture， and I'll see you then。



![](img/64fc78fb4afe651377757c1e88aa1474_3.png)

🎼。