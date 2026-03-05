# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p21 P21 05_4-5-堆运行时间分析 -BV1KnLCzXEcQ_p21-

![](img/c38b8c2ac5d538edbcda6f3fa83b1228_0.png)

![](img/c38b8c2ac5d538edbcda6f3fa83b1228_1.png)

One of the last bits to talk how to heap is to really dive into things we can do with a heap。

 because what we know right now is we know that we can do an insert and remove operation by just doing simple tree operations from our knowledge about trees。

 we know that these are login operations because we have a complete tree。

The other thing we know is we can actually build a heap o in time。So we can build it in linear time。

 which is a fantastic result， and it leads to us actually doing interesting things with a heap。

One thing I want to dive into is one interesting algorithm you can use by using a heap。

 and this is the heap sort。So looking on the heap sort。

 we're going to look at how we can actually build a sorted array by exploring the fact that we have a heap。

 Let's dive into this example。😡，Doing a heap sort is going to be three steps。

 The first step is we were want to build a heap and to build a heap。

 we can do this operation in simply O of time to create a heap out of a list of elements。

The next thing we need to do to actually get at the heap。A sorted list in our heap sort。

 we need to call in calls of remove。So once we've built the heap in O of in time。

 we can call remove in。😡，Men for log in time each time。

So what this means is we have a login operation。Every in times for in log in runtime。

And then only if it's needed， which may not be necessary， we may want to swap elements。

To order our list in the proper way， either ascending or descending。

So notice that we have a heap and we continually call remove Min。

 we're going to get at a list that's going to have four as the minimum element， then 5， then 6。

 then 7， then 9， and so forth。 By continually removing minimum from our tree。

 We know the slowest operation here is build heap， which takes in time。

But the log in time is going to be required for every single movement in operation。

 So in the very worst case， our running time is going to in times log in because we have in operations of log in time。

 which is going to dominate the building he call of of in time。

So even though we can build a heap and just O of in time。

 we can actually do what it's called a heap sort in an optimal time for sorting in log in time。😡。

We care about this sort because it's often going to be very convenient to do this sort entirely in memory if you're clever about using this zeroth index that we leave completely empty。

 you can do a heap sort without using any additional space then the space you have in this array this means as long as we have our data in any format that's in an array。

 a heap sort is going to be an ideal sort that allows us to order the data and provide some benefits form being in memoryory and will give us some advantages if the data structure is already semisorted。

😡，So we figured out how to actually understand what is it is to be a minimum heap。

 we figured out how to insert into minimum， how to remove min from minimum heap。

 we understand the running times of minimum heap， and now we understand some application of a heap in a min sort。

So what we're going to do next is we're going to start using all of these concepts to build something really great。

 So next week， we're going to dive into what it means to have one more algorithm， a disjoint set。

 and then we're going to finish off this semester by going in depth in graphs。

 and graphs is an amazing data structure that's going to unlock a lot of potential and allows us to solve a lot of really interesting problems。

 So let'll see then。😊。

![](img/c38b8c2ac5d538edbcda6f3fa83b1228_3.png)