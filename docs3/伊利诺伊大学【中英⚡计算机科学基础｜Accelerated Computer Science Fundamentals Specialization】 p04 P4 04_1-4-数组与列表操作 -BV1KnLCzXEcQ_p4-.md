# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p04 P4 04_1-4-数组与列表操作 -BV1KnLCzXEcQ_p4-

![](img/4963a84e415d11d3bb2f1d78f87368a5_0.png)

![](img/4963a84e415d11d3bb2f1d78f87368a5_1.png)

A arrays and links list are both ordered collections of data。

 There are several key operations that we want to compare and contrast between these two collections。

We've already talked about accessing a given index in the collection。

 We saw in a previous video that an array we can access in o of one time that we get direct access via a formula。

 where we must transverse every single node in a list in order to get to the particular index。

 So an array takes o of one time to access a given index。 A list takes o of in time。😊。

When we insert at the front of the array， we know that we need to resize the array every so often。

 by inserting at the front of the array， we can double it every single time and give us an amortized access time of O of1。

In a linked list， we saw that inserting at the beginning of a linked list。Is simply all of one time。

 It was， in fact， just three lines of code。By adding the new data at the beginning。

 setting the new datas next pointer equal to the old location of the head and setting the head equal to the new node we just inserted into the list。

Let's think about finding data， given data， How do we go about finding data inside of a collection。

 So if I want to find the orange cube in an array， I have no other choice but to start at the beginning。

And look at the first element。 Then look at the next element。 Then look at the next element。 Aha。

 I found the cube。So the amount of time of looking at every single element。Is going to take。

Operations equal to the amount of the data in there。 So to find the orange cube。

 we need to check every single piece of data。 So that's going to take O of n operations to find an orange cube。

 Suppose we want to find the purple cube。In our list。If we want to find the purple cube in our list。

We need to look at the head of the list。 Start looking， Nope， not the purple cube。 Go to next one。

 Not the purple cube。 Go to next one。 Not the purple cube。 Go to next one。 Not the purple cube。

 Go to the next one。 Not the purple cube and so forth。 So eventually。

 we're going to find the purple cube or possibly not find it。

 but we're going to also have to travel through every single element in a list to potentially find it。

 So we also say finding an element in a list is O of N。So to formalize this given data。

 find the location of that data in the collection。 Well， in an array。

 it takes O to find a particular piece of data in a linked list， it also takes O of in time。

 So it takes the exact same amount of time。 and both of these structures to find a piece of data。

 But could we do better。 So looking at the code to find an element inside an array。

 we saw this code in our arrays lecture。 and an example 4。

 you'll see that lines 29 through 34 has the code defined find an element。 in the list that Hp class。

 We saw that we have a fine function that finds the data inside of our list。

 So you have the code for both of these。 If you go back to linked memory or their arrays and you can actually play around with this find algorithm。



![](img/4963a84e415d11d3bb2f1d78f87368a5_3.png)

![](img/4963a84e415d11d3bb2f1d78f87368a5_4.png)

But I'm going to argue that we can really improve this find algorithm。If our data is sorted。

So that's the same objective。 We want to give in data。

 We want to find out the location of that data within the collection。

 But the only difference here is now we know that our collection is sorted。 So if we want to find 17。

 we could go and say 2，3，5，7，1113。 Oh， by found 17。 I could use my O of in strategy。

Called a linear search。But I think we can do better。I think if I want to find 17。

 it's sort of like a phone book。If I want to find something in a phone book。

 I don't start start at the beginning of the phone book。 Instead。

 I start in the middle of the phone book。So here， if I want to find 17。

 I'm going to jump to the middle of the array。And by jumping through the middle array。

 I can see is 13 greater than in less than 17。 Well，13 is less than 17。

 So I know that 17 must appear on the right hand side。

 so I can eliminate half of this data from my search completely。

I can then repeat this process with the rest of this data and say。

 is 19 the middle of the what's left。Greater than or less than my data。Well， it is greater than。

 so I know my data must be on the right hand side。And now in just three operations。

 I found the number 17。I found my data in the array。

And I did this by looking at half of the data each time and eliminating half it。

 The array has to be sorted， but we use a strategy called a binary search。By using a binary search。

 we were able to eliminate the need to look at every single data。

 and we were able to cut in half each time。 when we cut something in half。

 that's a log based2 operation， which we denote as log n。 So when we L G。

 that denotes simply log based 2。Of in。 So this is a log in operation。

 So we say the total running time is O of log in because we're constantly cutting our data in half and half and half and half。

So that's awesome。 So we know we can do better than O of in time if we have a sortded array。

 Let's look at a list。😊，Inside a list here we have a list that is sorted just like array。

 and we want to find 17。So how do I jump to the middle of the list。 I can't。

 There's no magic pointer that points to the center of the list。

And even if we had a point of that point to the center of list。

 as we added to the beginning of the list。That pointer would be out of date very quickly。

 So there is no way to jump to the center of a list。 Instead。

 the best we can do is still travel the list。 Look at the first element。 Look at the second element。

 Look at the third element， Look at the fourth element。

 Look at the fifth element and keep going until we find 17。

 So only by doing a linear search to the list， Can we find an element when we have a linked list。

 So a linked list。 Even if the date is sorted is still O of in time。So given data。

 find the location of data， our entire analysis。Is going to be an uncertained way takes us over in time。

A sorted array takes us log in time， and a list takes a o in time。

 You should not only know these run times， but you should also know the intuition behind these run times。

 So when you see a similar data structure， you'll be able to drive these run times and go through the analysis of understanding why they work the way they work。

So I'm going to look at one last operation that is often going to prove extremely useful。So。

 given an element。We want to insert a new element immediately afterwards。

So this is essentially insert after operation。 So if we have a linked list node。

We want to know how much time it takes to insert after that linkedless node。

Given an array index like index 4 inside of an array。

I want to know how much time it takes to insert right after a given index。

 So if we have a linkedless node or if we have an array。

 how much time does it take to insert after that element。So look at an array。

 if we want to insert a purple cube after the orange cube。Then if we look here。

 we need to stick a purple cube right in here。So with an array。

 all of this data is sequentially in memory。 What that means is there's no way we can just slam that purple cube right in the middle there。

 Instead， what we have to do is we have to copy the data that's already after our orange node。

 move all of this data over。 and only once we moved all of this data over。

Do we have room to insert the node。Since we have to keep moving all the data。

 either all data to the left or to the right， we can move in either direction。

 But if we insert an element at the very center of the list。

 we're going to have to move in divided by two data moves。So by moving in divided by two elements。

 using big O notation， we know that this is big O of n To moves。

 So the amount of time it takes to insert after a given element。Is O event。On the other side。

 if we look at a list。 So given an element。 So given a linkedless node。

 given this linked list node right here。How much time does it take to insert after our linked list node。

 Well， we can just create a new list node。Put this purple cube in there。

And change this next pointer to be here and put this next pointer to our Greg cube and done。

 So insert after our known lengthless node。 This is O of one time。

 It doesn't matter if this data is a million nodes wide。 We never have to copy over any data。

 We just have to stick one thing right in there。 Reair a few pointers。

 It's three lines of code and no loops whatsoever。 This is O of one time。

So if our objective is to insert an element， either a linked list node or an index。

Immediately afterward， after a given element。Then it's going to take O of n time in an array or O of one time in a list。

Likewise， we can see that the lead after operation is going to be the exact same as insert after。

If you think about removing the next element in array。

 we have to copy over all of our data and move it back to make sure our array is still is sequentially in memory。

 While a list we can just repair the pointers。 So whether or not we have insert after or whether or not we have delete after If we have a given node with an array。

 it takes us O of in time to delete delete insert a node right afterwards。😡，In a list。

 it takes us just o of one time。So you've seen that arrays and list are both ordered collections that can have trade offs between the runtime and the flexibility of their implementation。

 We're going to build data structure on top of a raisein list。 And we're often going to question。

 what do we want in the base of our data structure， Do we want an array or do we want a list。

And these two fundamental linear data structures are going to build everything else that we're going to build in this class。

 I'm Looking forward to building these with you， and I'll see you there。



![](img/4963a84e415d11d3bb2f1d78f87368a5_6.png)