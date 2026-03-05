# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p05 P5 05_1-5-队列数据结构 -BV1KnLCzXEcQ_p5-

![](img/69b472c4b50e056f6efa931eb9ddb26d_0.png)

![](img/69b472c4b50e056f6efa931eb9ddb26d_1.png)

A queue is a first in， first out data structure similar to waiting in line will represent a queue visually by having an array or a list or any type of container inside of a series of lines。

We'll see an inner point and an exit point。 So you can imagine if you're waiting in line for a cup of coffee。

The first person who arrive in the line will get their drink first。

 People arrive at the back of the line and move through the line in the order， which they arrived。

This kind of model will model with a cue。When we talk about data structures。

 we'll always talk about a data structure in terms of their abstract data type or how data interacts with the data structure without talking about an implementation。

 So an ADT is not an implementation， but it's a description of what the data structure does。

 then we'll explore the implementation after knowing the description。😡。

The abstract data type for a queue is going to have four different functions。

 The first is we need to be able to create a queue。

 and that will create an empty queue with nothing in it。 We need to push data into the queue。

 and that will add data to the back of the queue。When we want to remove data from the queue。

 we'll pop the queue and popping the queue will take the first element of the data and bring it out。

And finally， we need some ability to determine whether or not the queue is empty or not。

And the empty functionality will determine if the queue has anything in it， or is completely empty。

So let's consider simple operations on a queue thinking only about the abstract data type and what we know about how a Q functions。

 We first are going to create a queue of integers。 So we'll go ahead and initialize this Q。

 and we know it's going to contain integers。And we'll go ahead and push the number 4 onto the queue。

 Soll add 4。4 is ready to be the first person off the queue。

 The second thing we'll do is we'll push number 2 to the queue。And then finally。

 we'll pop a number from the Q because the Q is going to take the first thing to arrive。

4 is going to get popped off the queue， Remove from the Q。

 And now two is the next element to be removed。

![](img/69b472c4b50e056f6efa931eb9ddb26d_3.png)

In C plus plus， we actually have a queue provided for us by the standard library。 This is an STD Q。

Similar to a standard vector， we can use a standard Q by doing SD Q。 It's a template type。

 So here we have a Q of strings。Here I'm going to in queue three different elements。

By saying push orange， push blue and push Illinois。We expect orange to be first。

Behind orange is blue。And behind blue is Illinois。On line 21， we see out the first pop。

 so we get the Q at the first element。 So we expect this to print out orange。

Since orange has been popped off top the queue， we now go to the next line， line 25。

 we add Illinois to the queue。 We see the inner here is at the end of the queue。

 So we'll add Illinois。Sorry， we'll add Alina， not Illinois。

And then we do S second pop is queued up front。 So what's at the front of the queuee now， it is blue。

So the output of this program， understanding our cu is that after adding three elements。

 when we pop off an element， the element should be orange。 After adding a line eye。

 we pop up another element， and it should be blue。 Let's see if this logic matches it when we run the implementation。



![](img/69b472c4b50e056f6efa931eb9ddb26d_5.png)

Moving into the Q directory。Running make。And dot slash main。The first pop is orange。

 exactlyactly what we expect。 The second pop was blue。 Exact what we expect。

 So our logic and the code matches up。 But let's actually understand what the queue does internally。

😊，And how fast it runs。

![](img/69b472c4b50e056f6efa931eb9ddb26d_7.png)

Internally， a queue can be implemented with either of our two basic data types that we've already discussed。

 We can have an array based queue。Or a linked list base queue in an array based queue。

An array is going to sit in the queue。And we'll。Have an index for each element in the array。

The array will be initial size， and again， we can expand it by doubling the size or shrinking it by half the size as we need to。

When an element arrives in the queue， we'll simply add it to the Q。

And we can continually add items to the queue as they arrive。

 We only need to ensure that the elements as they arrive。

 is placed further back in the queue than all of the elements that currently exist。

In this array based queue， notice that we can always have a counter to determine the index where we should enter things next。

 and we can always keep track of the index。 For example。

 here we might be at index 8 of where we should be removing from the Q。

There's a number of different ways to set up the arrays。

 But so long as you keep track of where the insertion point is and where the removal point is or where the pop and push points are。

 we can always just suggest them by adding one or subtracting one and resizing the array as needed。

All of these operations。Are just operation of indices and are always going to run an o of one time。

A list implementation is slightly different。 We're going to have a linked list， and。

We know in the linked list， we can insert up front and o of one time。

By inserting at front and O of one time， we can continually add things to the head as they arrive into our list。

What we absolutely don't want to do is to have to traverse through the entire list。Instead。

 what we want to do is we want to store a new pointer called a tail pointer。

That's maintained the very end of the list。This tail pointer will allow us to always access the last element of the list。

 and is something we can easily maintain。The last thing that we need to do to maintain this tail pointer is in linked memory instead of just linking our memory forward。

 Let's make sure we link all of our memory backwards， as well。So if we do this。

 whenever a new element arrives， we can always add it directly to the head。

We know that adding to the head takes o of one time。On the other side， when we have a tail pointer。

 we can always find the element at the very end。In all of one time。

We can remove this element and update the tail pointer。To the previous element。

 if we have this doubly linked list where we have back pointers。 so update。

Also takes O of one time if we're careful with the design。 So using the base idea of a list。

 we could implement a list by adding a few minor features and getting an O of one time for both push and pop onto a list。

 just like we were able to with an array。😊，So summarizing all of this。

 creating a Q data structure is going to take O of one time to create an empty array and O of one time create an empty linked list。

 We argued that push and pop were both o of one time so long as we have a doubly linked list for a linked list and so long as we do an intelligent resize where we're doubling the size every time we run out of room in our array。

Notice that we have O of one operations in the array because we're always inserting it at the front of the array and removing from the back of the array。

And finally， we can determine what the size of each of these components are in all of one time。

So when we're building a queue， every operation we perform on a queue is an O of one time operation。

 That means it doesn't matter if we have a million things in the queue or just one thing in the queue。

 By using a queue， we guarantee there's going to be a constant run time。

 no matter how large the queue grows。So a queue is a first and first Saturday data structure that mimics waiting in a line。

 A queue may be implemented with either an array or a linked list。And by using。

Wise implementation for both of these structures。 We can build a queue that runs in constant O of one time。

This is going to be a powerful data structure that we're going to use to manage a lot of things as we go forward in this class。

The sister data structure to the queue is the stack。 And I'll talk about that one in the next video。

 I'll see you there。

![](img/69b472c4b50e056f6efa931eb9ddb26d_9.png)

![](img/69b472c4b50e056f6efa931eb9ddb26d_10.png)