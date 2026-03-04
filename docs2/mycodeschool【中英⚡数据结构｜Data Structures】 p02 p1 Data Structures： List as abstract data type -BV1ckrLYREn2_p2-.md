# mycodeschool【中英⚡数据结构｜Data Structures】 p02 p1 Data Structures： List as abstract data type -BV1ckrLYREn2_p2-

![](img/0f8923331f67af85a7f43a555f2c8269_0.png)

In our previous lesson， we introduced you to the concept of data structures。



![](img/0f8923331f67af85a7f43a555f2c8269_2.png)

And we saw how we can talk about data structures in two ways。

 one as a mathematical and logical model that we also call that we also term as an abstract data type。



![](img/0f8923331f67af85a7f43a555f2c8269_4.png)

![](img/0f8923331f67af85a7f43a555f2c8269_5.png)

Or AD DT。 And then we also study data structures as concrete implementations In this lesson。

 we will study one simple data structure。 We will first define an abstract view of it。

 We will first define it as an abstract data type， and then we will see the possible implementations。



![](img/0f8923331f67af85a7f43a555f2c8269_7.png)

![](img/0f8923331f67af85a7f43a555f2c8269_8.png)

![](img/0f8923331f67af85a7f43a555f2c8269_9.png)

And this data structure is list list is a common real world entity。



![](img/0f8923331f67af85a7f43a555f2c8269_11.png)

![](img/0f8923331f67af85a7f43a555f2c8269_12.png)

List is nothing but a collection of objects of the same type。 We can have a list of words。

 We can have a list of names， or we can have a list of numbers。

 So let us first define list as an abstract data type。 So when we define abstract data type。

 we just define the data that will store and we define the operations available with the type and we do not go into the implementation details。



![](img/0f8923331f67af85a7f43a555f2c8269_14.png)

![](img/0f8923331f67af85a7f43a555f2c8269_15.png)

![](img/0f8923331f67af85a7f43a555f2c8269_16.png)

![](img/0f8923331f67af85a7f43a555f2c8269_17.png)

![](img/0f8923331f67af85a7f43a555f2c8269_18.png)

Let us first define a very basic list。 I want a list that can store a given number of elements of a given data type。

 This would be a static list。 The number of elements in the list will not change。

 and we will know the number of elements before creating the list。



![](img/0f8923331f67af85a7f43a555f2c8269_20.png)

![](img/0f8923331f67af85a7f43a555f2c8269_21.png)

![](img/0f8923331f67af85a7f43a555f2c8269_22.png)

We should be able to write or modify。

![](img/0f8923331f67af85a7f43a555f2c8269_24.png)

Element at any position in the list。 And， of course。

 we should be able to read element at a particular position in the list。

 So if I ask you for an implementation of such a list and you have taken a basic course in programming。

 a basic introductory course。 then you'll be like， hey， I know this。

 and array gives us all these features。 all these operations are available with an array。

 we can create an array of any data type。 So let's say if we want to create a list of integers。

 then we。

![](img/0f8923331f67af85a7f43a555f2c8269_26.png)

![](img/0f8923331f67af85a7f43a555f2c8269_27.png)

![](img/0f8923331f67af85a7f43a555f2c8269_28.png)

![](img/0f8923331f67af85a7f43a555f2c8269_29.png)

![](img/0f8923331f67af85a7f43a555f2c8269_30.png)

![](img/0f8923331f67af85a7f43a555f2c8269_31.png)

Dclare the array type as in teacher。 and then we can。



![](img/0f8923331f67af85a7f43a555f2c8269_33.png)

Give the size as a parameter in declaration。 I can write or modify element at a particular position。

 We The elements are a 0， A1 and are accessed。 something like this。 We all know about a race。

 and then we can also read elements at particular。

![](img/0f8923331f67af85a7f43a555f2c8269_35.png)

![](img/0f8923331f67af85a7f43a555f2c8269_36.png)

![](img/0f8923331f67af85a7f43a555f2c8269_37.png)

不执行。The element at Iith position is accessed as AI。



![](img/0f8923331f67af85a7f43a555f2c8269_39.png)

So array is a data structure that gives us implementation for this list。 Now。

 I want a list that should have many more features。 I want it to handle more scenarios for me。

 So I'll redefine this list here。 I do not want a static list， a static collection with a fixed size。

 I want a dynamic list that should grow as per my need。

 So the features of my list are that I'll call my list empty。



![](img/0f8923331f67af85a7f43a555f2c8269_41.png)

![](img/0f8923331f67af85a7f43a555f2c8269_42.png)

![](img/0f8923331f67af85a7f43a555f2c8269_43.png)

![](img/0f8923331f67af85a7f43a555f2c8269_44.png)

![](img/0f8923331f67af85a7f43a555f2c8269_45.png)

If there are no elements in the list， I'll say the size of the list is 0 when it is empty。

 And then I can insert an element into the list。

![](img/0f8923331f67af85a7f43a555f2c8269_47.png)

![](img/0f8923331f67af85a7f43a555f2c8269_48.png)

And I can insert an element at any position in the list and in an existing list。

 I can remove element from the list。 I can count the number of elements in the list。



![](img/0f8923331f67af85a7f43a555f2c8269_50.png)

And I should be able to read or write。

![](img/0f8923331f67af85a7f43a555f2c8269_52.png)

Or rather， read or modify element at a particular position in the list。



![](img/0f8923331f67af85a7f43a555f2c8269_54.png)

And I should also be able to specify the data type for the list so I should be able to。

 while creating the list， I should be able to say whether this is a list of integers or whether this is a list of string or float or whatever。



![](img/0f8923331f67af85a7f43a555f2c8269_56.png)

![](img/0f8923331f67af85a7f43a555f2c8269_57.png)

![](img/0f8923331f67af85a7f43a555f2c8269_58.png)

Now I want a data structure which is implementation of this dynamic list So how do I get it Well。

 actually we can implement such a dynamic list using arrays。

 Its just that we will have to write some more operations on top of arrays to provide for all these functionalities。

 So let us see how we can implement this particular list using arrays。



![](img/0f8923331f67af85a7f43a555f2c8269_60.png)

![](img/0f8923331f67af85a7f43a555f2c8269_61.png)

![](img/0f8923331f67af85a7f43a555f2c8269_62.png)

![](img/0f8923331f67af85a7f43a555f2c8269_63.png)

Lets for the sake of simplicity of design assume that that the data type for the list is integer so we are creating a list of dynamic list of integers。

 What we can do is to implement such a list we can declare a really large array we will define some max size and declare an array of this max size now as we know the elements in the array are indexed as a0 a1 a2。



![](img/0f8923331f67af85a7f43a555f2c8269_65.png)

![](img/0f8923331f67af85a7f43a555f2c8269_66.png)

![](img/0f8923331f67af85a7f43a555f2c8269_67.png)

![](img/0f8923331f67af85a7f43a555f2c8269_68.png)

![](img/0f8923331f67af85a7f43a555f2c8269_69.png)

And we go on like this。So what I'll do is I'll define a variable that will mark the end of the list in this array。

 So if the list is empty， we can initialize this variable or we can set this variable as -1。

 because the lowest index possible is 0。 So if end is -1， the list is empty。

 at any time a part of the array will store the list。 Okay。

 so let's say initially when the list is empty。 this pointer end is pointing to。



![](img/0f8923331f67af85a7f43a555f2c8269_71.png)

![](img/0f8923331f67af85a7f43a555f2c8269_72.png)

![](img/0f8923331f67af85a7f43a555f2c8269_73.png)

![](img/0f8923331f67af85a7f43a555f2c8269_74.png)

![](img/0f8923331f67af85a7f43a555f2c8269_75.png)

Index -1， which is not valid， which does not exist。 And now I insert an integer into this array。



![](img/0f8923331f67af85a7f43a555f2c8269_77.png)

And let's say if we do not give the position at which the number is to be inserted。

 the number is always inserted towards the tail of the list towards the end of the list。

 So the list will be like we will have an element at position 0 and now n is index 0。

 So at any time n marks the this variable n marks the end of the list in this hurry。

 Now if I want to insert something in the list at a particular position。

 let's say I want to insert number 5 at index 2， then to accommodate 5 here at this particular position。

 we will have to shift all the elements。

![](img/0f8923331f67af85a7f43a555f2c8269_79.png)

![](img/0f8923331f67af85a7f43a555f2c8269_80.png)

![](img/0f8923331f67af85a7f43a555f2c8269_81.png)

![](img/0f8923331f67af85a7f43a555f2c8269_82.png)

![](img/0f8923331f67af85a7f43a555f2c8269_83.png)

![](img/0f8923331f67af85a7f43a555f2c8269_84.png)

![](img/0f8923331f67af85a7f43a555f2c8269_85.png)

![](img/0f8923331f67af85a7f43a555f2c8269_86.png)

One unit towards the right。

![](img/0f8923331f67af85a7f43a555f2c8269_88.png)

All the elements starting index 2。 we need to shift all the elements。

 starting index 2 towards the right。 Okay， I just inserted some elements into the list。

 Let me also write the。

![](img/0f8923331f67af85a7f43a555f2c8269_90.png)

![](img/0f8923331f67af85a7f43a555f2c8269_91.png)

Function call for these。 Let's say we went in this order。 We inserted 2， Then we inserted 4。

 and then we inserted。 in the end， we are inserting 5。

 and we will also give the position at which we want to insert。

 So this insert with two arguments would be the call to insert element at a particular position。



![](img/0f8923331f67af85a7f43a555f2c8269_93.png)

![](img/0f8923331f67af85a7f43a555f2c8269_94.png)

![](img/0f8923331f67af85a7f43a555f2c8269_95.png)

So after all these operations， after all these insertions， this is what the list will look like。

 This arrow here marks the end of the list in the array。 Now。

 if I want to remove an element from a particular position， let's say make a call to something。



![](img/0f8923331f67af85a7f43a555f2c8269_97.png)

![](img/0f8923331f67af85a7f43a555f2c8269_98.png)

![](img/0f8923331f67af85a7f43a555f2c8269_99.png)

To the remove function， I want to remove the element 2。 So I'll pass the index 0 here。

 I want to remove the element at index 0。 So to do so。

 all these elements after index 0 will be shifted one unit towards the left or towards the lower indices。



![](img/0f8923331f67af85a7f43a555f2c8269_101.png)

![](img/0f8923331f67af85a7f43a555f2c8269_102.png)

![](img/0f8923331f67af85a7f43a555f2c8269_103.png)

And two will go away。This in end variable here is being adjusted after each insertion that we are making。

 So after this insertion and will be 0 after this one。



![](img/0f8923331f67af85a7f43a555f2c8269_105.png)

2，3 and so on。 after this remove and will be4 again。 Okay。

 looks like we pretty much have an implementation of this list in the left that is described as an abstract data type。

 We have a logic of calling the list empty when we have this variable n is equal to -1。

 We can insert element at a particular position in the list。 We can remove element。

 It's just that we have to perform some shifts in the array。



![](img/0f8923331f67af85a7f43a555f2c8269_107.png)

![](img/0f8923331f67af85a7f43a555f2c8269_108.png)

![](img/0f8923331f67af85a7f43a555f2c8269_109.png)

![](img/0f8923331f67af85a7f43a555f2c8269_110.png)

![](img/0f8923331f67af85a7f43a555f2c8269_111.png)

![](img/0f8923331f67af85a7f43a555f2c8269_112.png)

We can count the number of elements in the list。 It will be equal to n plus one。

 The value in the variable N plus  one。 we can read or modify。



![](img/0f8923331f67af85a7f43a555f2c8269_114.png)

![](img/0f8923331f67af85a7f43a555f2c8269_115.png)

Element at a position。 Well， this is an array。 so we can definitely read or modify element at a particular position。



![](img/0f8923331f67af85a7f43a555f2c8269_117.png)

If we wanted to choose the data type， it was just choosing the array of that particular data type。

 This looks like a cool implementation， except that we have one problem。

 We said that the array will be of some large size， some max size。



![](img/0f8923331f67af85a7f43a555f2c8269_119.png)

![](img/0f8923331f67af85a7f43a555f2c8269_120.png)

![](img/0f8923331f67af85a7f43a555f2c8269_121.png)

But what is a good max size， we can always exhaust array。 the list can always grow to exhaust array。



![](img/0f8923331f67af85a7f43a555f2c8269_123.png)

There is no good max size。 So we need to have a strategy for the scenario when the list will fill up the whole array。

 So what do we do in that case。

![](img/0f8923331f67af85a7f43a555f2c8269_125.png)

![](img/0f8923331f67af85a7f43a555f2c8269_126.png)

![](img/0f8923331f67af85a7f43a555f2c8269_127.png)

We need to keep that into our design。 We cannot extend the same array。 It is not possible to do so。

 So we will have to create a new array， a larger array。 So when the array is full。

 we will create a new， larger array and copy all the elements from the previous array into the new array。



![](img/0f8923331f67af85a7f43a555f2c8269_129.png)

![](img/0f8923331f67af85a7f43a555f2c8269_130.png)

![](img/0f8923331f67af85a7f43a555f2c8269_131.png)

And then we can free the memory for the previous array。



![](img/0f8923331f67af85a7f43a555f2c8269_133.png)

Now the question is， by how much should we increase the size of the new array？



![](img/0f8923331f67af85a7f43a555f2c8269_135.png)

This whole operation of creating a new array and copying all the elements from the previous array into the new array is costly in terms of time。

 and definitely a good design would be to avoid such big cost。

 So the strategy that we choose is that each time the array is full。

 we create a new larger array of double the size of the previous array。



![](img/0f8923331f67af85a7f43a555f2c8269_137.png)

![](img/0f8923331f67af85a7f43a555f2c8269_138.png)

![](img/0f8923331f67af85a7f43a555f2c8269_139.png)

![](img/0f8923331f67af85a7f43a555f2c8269_140.png)

![](img/0f8923331f67af85a7f43a555f2c8269_141.png)

And why this is the best strategy is something that we will not discuss in this lesson。

 so we will create a larger array of double size and copy elements from previous array into this new array。



![](img/0f8923331f67af85a7f43a555f2c8269_143.png)

![](img/0f8923331f67af85a7f43a555f2c8269_144.png)

This looks like a cool implementation。The study of data structures is not just about studying the operations and the implementation of these operations。

 It's also about analyzing the cost of these operations。

 So let us see what are the costs in terms of time for all these operations that we have in the dynamic list The access to any element in this dynamic list if we want to access it using index for read or write then this will take constant time because we have an array here and in array elements are arranged in one contiguous block of memory using the starting address or the base address of the block of the memory of the block of memory and the index or the position of the element we can calculate the address of that particular element and access it in constant time big O notation that is used to describe the time complexity of operations for constant time it is written as in terms of big O the time complexity is written as big O of one。



![](img/0f8923331f67af85a7f43a555f2c8269_146.png)

![](img/0f8923331f67af85a7f43a555f2c8269_147.png)

![](img/0f8923331f67af85a7f43a555f2c8269_148.png)

![](img/0f8923331f67af85a7f43a555f2c8269_149.png)

![](img/0f8923331f67af85a7f43a555f2c8269_150.png)

![](img/0f8923331f67af85a7f43a555f2c8269_151.png)

![](img/0f8923331f67af85a7f43a555f2c8269_152.png)

![](img/0f8923331f67af85a7f43a555f2c8269_153.png)

![](img/0f8923331f67af85a7f43a555f2c8269_154.png)

![](img/0f8923331f67af85a7f43a555f2c8269_155.png)

![](img/0f8923331f67af85a7f43a555f2c8269_156.png)

![](img/0f8923331f67af85a7f43a555f2c8269_157.png)

![](img/0f8923331f67af85a7f43a555f2c8269_158.png)

If we wanted to insert element。If we wanted to insert element at the end of the array end of the list。

 then that again will be constant time。 But if we would insert element at a particular position in the list。



![](img/0f8923331f67af85a7f43a555f2c8269_160.png)

![](img/0f8923331f67af85a7f43a555f2c8269_161.png)

Then we will have to shift elements towards higher indices。 In the worst case。

 we will have to shift all the elements to the right when we will be inserting at the first position。

 So the time taken for insertion。

![](img/0f8923331f67af85a7f43a555f2c8269_163.png)

![](img/0f8923331f67af85a7f43a555f2c8269_164.png)

![](img/0f8923331f67af85a7f43a555f2c8269_165.png)

Will be proportional to the length of the list。 Let's say the length of the list is n。



![](img/0f8923331f67af85a7f43a555f2c8269_167.png)

Or in other words， we will say that insertion will be big O of n in terms of time complexity。

 If you do not know about big O notation， do not bother。

 just understand that inserting an an element at a particular position will be a linear function in terms of the size of the list。

 Reing an element will， again， be big O of n。

![](img/0f8923331f67af85a7f43a555f2c8269_169.png)

![](img/0f8923331f67af85a7f43a555f2c8269_170.png)

![](img/0f8923331f67af85a7f43a555f2c8269_171.png)

![](img/0f8923331f67af85a7f43a555f2c8269_172.png)

![](img/0f8923331f67af85a7f43a555f2c8269_173.png)

Time taken will be。Proportal to the current size of the list。 and is the size of the list here。



![](img/0f8923331f67af85a7f43a555f2c8269_175.png)

Okay， now inserting an element at the end， we just said that it will happen in constant time。

 It is not so if the array is full， then we will create a new array。

 Let's call inserting element at the end as adding an element。



![](img/0f8923331f67af85a7f43a555f2c8269_177.png)

![](img/0f8923331f67af85a7f43a555f2c8269_178.png)

![](img/0f8923331f67af85a7f43a555f2c8269_179.png)

Adding an element will take constant time if the list is not full。

 but it will take time proportional to the size of the list size of the array。 If the array is full。

 So adding in the worst case will be big go of and again。



![](img/0f8923331f67af85a7f43a555f2c8269_181.png)

![](img/0f8923331f67af85a7f43a555f2c8269_182.png)

![](img/0f8923331f67af85a7f43a555f2c8269_183.png)

As we said， when the list is full， we create a new copy。

 double the size of the previous array and then we copy the previous array。

 the elements from previous array into the new array。 So prime of I。

 what looks like the good thing with this kind of implementation。



![](img/0f8923331f67af85a7f43a555f2c8269_185.png)

![](img/0f8923331f67af85a7f43a555f2c8269_186.png)

![](img/0f8923331f67af85a7f43a555f2c8269_187.png)

Well， the good thing is that we can access elements at any index in constant time。

 which is the property of the array。

![](img/0f8923331f67af85a7f43a555f2c8269_189.png)

![](img/0f8923331f67af85a7f43a555f2c8269_190.png)

But if we have to insert some element in between and if we have to remove element from the list。

 then it is costly。

![](img/0f8923331f67af85a7f43a555f2c8269_192.png)

If the list grows and shrinks a lot， then we will also have to create a new array and have all this thing of copying elements from previous array to new array again and again。



![](img/0f8923331f67af85a7f43a555f2c8269_194.png)

![](img/0f8923331f67af85a7f43a555f2c8269_195.png)

![](img/0f8923331f67af85a7f43a555f2c8269_196.png)

And one more problem is that a lot of time， a lot of the array would be unused。



![](img/0f8923331f67af85a7f43a555f2c8269_198.png)

The memory there is of no use definitely the use of array as dynamic list is not efficient in terms of memory。

 This kind of implementation is not efficient in terms of memory。

 This leads us to think can we have a data structure that will give us a dynamic list and use the memory more efficiently we have one data structure that gives us good utilization of the memory and this data structure is linked list and we will study about the linked lists。



![](img/0f8923331f67af85a7f43a555f2c8269_200.png)

![](img/0f8923331f67af85a7f43a555f2c8269_201.png)

![](img/0f8923331f67af85a7f43a555f2c8269_202.png)

![](img/0f8923331f67af85a7f43a555f2c8269_203.png)

![](img/0f8923331f67af85a7f43a555f2c8269_204.png)

In the next lesson。So that's it for this lesson， thanks for watching。



![](img/0f8923331f67af85a7f43a555f2c8269_206.png)