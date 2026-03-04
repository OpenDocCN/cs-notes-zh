# mycodeschool【中英⚡数据结构｜Data Structures】 p04 p3 Data Structures： Arrays vs Linked Lists -BV1ckrLYREn2_p4-

In our previous lesson， we introduced you to linked list data structure。



![](img/b0ec2f032554321893308df01f28831d_1.png)

And we saw how linked lists solve some of the problems that we have with arrays。

 So now the obvious question would be which one is better an arrayri or a linked list。

 Well there is no such thing as one data structure is better than another data structure。



![](img/b0ec2f032554321893308df01f28831d_3.png)

![](img/b0ec2f032554321893308df01f28831d_4.png)

![](img/b0ec2f032554321893308df01f28831d_5.png)

One data structure may be really good for one kind of requirement while another data structure can be really good for another kind of requirement。

 so it all depends upon factors like what is the most frequent operation that you want to perform with the data structure or what is the size of the data。



![](img/b0ec2f032554321893308df01f28831d_7.png)

![](img/b0ec2f032554321893308df01f28831d_8.png)

And there can be other factors， as well。

![](img/b0ec2f032554321893308df01f28831d_10.png)

So in this lesson we will compare these two data structures based on some parameters based on the cost of operations that we have with these data structures。

 so all in all we will comparatively study the advantages and disadvantages and try to understand in which scenario we should use an array and in which scenario we should use a linked list。



![](img/b0ec2f032554321893308df01f28831d_12.png)

![](img/b0ec2f032554321893308df01f28831d_13.png)

![](img/b0ec2f032554321893308df01f28831d_14.png)

![](img/b0ec2f032554321893308df01f28831d_15.png)

So I will draw two columns here， one for array and another for a linked list and the first parameter that we want to talk about。



![](img/b0ec2f032554321893308df01f28831d_17.png)

Is the cost of accessing an element irrespective of the size of an array。

 It takes constant time to access an element in the array。

 This is because an array is stored as one contiguous block of memory。

 So if we know the starting address or the base address of this block of memory。

 Let us say what we have here is an integer array and the base address is200。

 the first pipe in this block is at address 200。 then let's say if we want to calculate the address of。



![](img/b0ec2f032554321893308df01f28831d_19.png)

![](img/b0ec2f032554321893308df01f28831d_20.png)

![](img/b0ec2f032554321893308df01f28831d_21.png)

![](img/b0ec2f032554321893308df01f28831d_22.png)

![](img/b0ec2f032554321893308df01f28831d_23.png)

![](img/b0ec2f032554321893308df01f28831d_24.png)

Eleement at index i， then it will be equal to 200 plus i into size of an integer。In bytes。

 so size of an integer in bytes is typically 4 bytes， so it will be 200 plus 4 into I。

 so if0th element is at address 200 if we want to calculate the address 4 element at index 6 it will be 200 plus 6 into 24 which will be equal to 224。



![](img/b0ec2f032554321893308df01f28831d_26.png)

So knowing address of any element in anRA is just this calculation for our application in terms of big O notation constant time is also called big o of 1。



![](img/b0ec2f032554321893308df01f28831d_28.png)

![](img/b0ec2f032554321893308df01f28831d_29.png)

So accessing an element in an array is big O of one in terms of time complexity。

 if you are not aware of big O notation， check the description of this video for a tutorial on time complexity analysis。



![](img/b0ec2f032554321893308df01f28831d_31.png)

![](img/b0ec2f032554321893308df01f28831d_32.png)

Now in a linked list data is not stored in a contiguous block of memory， so if we have a linked list。

 something like this， let's say we have a linked list of integers here then we have multiple blocks of memory at different addresses each block in the linked list is called a node and each node has two fields one to store the data and one to store the address of the next node so we call the second field。

 the link field， the only information that we keep。



![](img/b0ec2f032554321893308df01f28831d_34.png)

![](img/b0ec2f032554321893308df01f28831d_35.png)

![](img/b0ec2f032554321893308df01f28831d_36.png)

![](img/b0ec2f032554321893308df01f28831d_37.png)

![](img/b0ec2f032554321893308df01f28831d_38.png)

With us about a linked list is the address of the first node which we also call the head node and this is what we keep passing to all the functions also the address of the head node to access an element in the linked list at a particular position we first need to start at the head node or the first node and at the first node we need to see the address of the second node and then we go to the second node and see the address of the third node in the worst case to access the last element in the list we will be traversing all the nodes in the list in the average case we will be accessing the middle element maybe so if n is the size of the linked list n is the number of elements in the linked list then we will traverse n by two elements so the time taken in the average case also is proportional to number of elements in the linked list。



![](img/b0ec2f032554321893308df01f28831d_40.png)

![](img/b0ec2f032554321893308df01f28831d_41.png)

![](img/b0ec2f032554321893308df01f28831d_42.png)

![](img/b0ec2f032554321893308df01f28831d_43.png)

![](img/b0ec2f032554321893308df01f28831d_44.png)

![](img/b0ec2f032554321893308df01f28831d_45.png)

![](img/b0ec2f032554321893308df01f28831d_46.png)

So we can say that the time complexity in average case is big O of n。



![](img/b0ec2f032554321893308df01f28831d_48.png)

So on this parameter， cost of accessing an element， array scores heavily over a linked list。

 so if you have a requirement where you want to access elements in the list all the time。

 then definitely array is a better choice。

![](img/b0ec2f032554321893308df01f28831d_50.png)

![](img/b0ec2f032554321893308df01f28831d_51.png)

![](img/b0ec2f032554321893308df01f28831d_52.png)

Now the second parameter that we want to talk about is memory requirement or memory usage with an array we need to know the size of the array before creating it because array is created as one contiguous block of memory so array is of fixed size what we typically do is create we create a large enough array and some part of the array towards our list and some part of the array is vacant or empty so that we can add more elements in the list。

 for example we have an array of seven integers here and we have only three integers in the list。



![](img/b0ec2f032554321893308df01f28831d_54.png)

![](img/b0ec2f032554321893308df01f28831d_55.png)

![](img/b0ec2f032554321893308df01f28831d_56.png)

![](img/b0ec2f032554321893308df01f28831d_57.png)

![](img/b0ec2f032554321893308df01f28831d_58.png)

![](img/b0ec2f032554321893308df01f28831d_59.png)

Rest4 positions are unused， there would be some garbage value there。



![](img/b0ec2f032554321893308df01f28831d_61.png)

With linked list， let's say we have， let's say we have this linked list of integers。

 There is no unused memory。

![](img/b0ec2f032554321893308df01f28831d_63.png)

We ask memory for one node at a time， so we do not keep any reserved space。

 but we use extra memory for pointer variables。

![](img/b0ec2f032554321893308df01f28831d_65.png)

And this extra memory requirement for pointer variables in a linked list cannot be ignored in a typical architecture。

 lets say integer is stored in 4 bytes and pointer variable also takes4 bytes so if you see the memory requirement for this array of7 integers is 28 bytes and the memory requirement for this linked list would be。



![](img/b0ec2f032554321893308df01f28831d_67.png)

![](img/b0ec2f032554321893308df01f28831d_68.png)

![](img/b0ec2f032554321893308df01f28831d_69.png)

![](img/b0ec2f032554321893308df01f28831d_70.png)

![](img/b0ec2f032554321893308df01f28831d_71.png)

8 into three where8 is the size of each node，4 for integer and4 bytes for the pointer variable。

 so this is also 24 bytes if we add one more element to the list in the array we will just use one more position while in linked list we will create one more node and we take another 8 bytes so this will be 32 bytes。



![](img/b0ec2f032554321893308df01f28831d_73.png)

![](img/b0ec2f032554321893308df01f28831d_74.png)

![](img/b0ec2f032554321893308df01f28831d_75.png)

![](img/b0ec2f032554321893308df01f28831d_76.png)

Liinked list would fetch us a lot of advantage of the data the data part is large in size。

 so in this case we had a linked list of inte so inte is only4 bytes。 What if we had a linked list。



![](img/b0ec2f032554321893308df01f28831d_78.png)

![](img/b0ec2f032554321893308df01f28831d_79.png)

![](img/b0ec2f032554321893308df01f28831d_80.png)

In which a data part was some complex type that took 16 by。



![](img/b0ec2f032554321893308df01f28831d_82.png)

So4 bytes for the link and 16 bytes for the data， each node would have been 20 bytes。

 an array of 7 elements for 16 bytes of data would be 16 byte for each element would be 112 bytes。



![](img/b0ec2f032554321893308df01f28831d_84.png)

And linked list of four would be only 80 bytes， so it all depends if the data part for the list takes a lot of memory。

 linked list will definitely consume a lot less memory。



![](img/b0ec2f032554321893308df01f28831d_86.png)

Otherwise， it depends what strategy we are choosing to decide the size of the array at any time how much array we keep unused Now one more point with memory allocation because arrays are created as one contiguous block of memory sometimes when we may want to create a really really large array。

 then maybe memory may not be available as one large block。

 but if we are using linked list memory may be available as multiple small blocks。

 so we will have this problem of fragmentation in the memory。

 sometimes we may get many small units of memory but may not get one large block of memory this may be a rare phenomenon。



![](img/b0ec2f032554321893308df01f28831d_88.png)

![](img/b0ec2f032554321893308df01f28831d_89.png)

![](img/b0ec2f032554321893308df01f28831d_90.png)

![](img/b0ec2f032554321893308df01f28831d_91.png)

![](img/b0ec2f032554321893308df01f28831d_92.png)

![](img/b0ec2f032554321893308df01f28831d_93.png)

But this is a possibility， so this is also where linked list scores。

Because arrays have fixed size once array gets filled and we。



![](img/b0ec2f032554321893308df01f28831d_95.png)

Need more memory then there is no other option than to create a new array of larger size and copy the content from the previous array into the new array。

 So this is also one cost which is not there with linked list so we need to keep these constraints and these requirements in mind when we want to decide for one of these data structures for our requirement Now the third parameter that we want to talk about is。



![](img/b0ec2f032554321893308df01f28831d_97.png)

![](img/b0ec2f032554321893308df01f28831d_98.png)

![](img/b0ec2f032554321893308df01f28831d_99.png)

![](img/b0ec2f032554321893308df01f28831d_100.png)

![](img/b0ec2f032554321893308df01f28831d_101.png)

![](img/b0ec2f032554321893308df01f28831d_102.png)

Cost of inserting an element in the list。 remember when we are talking about array here。

 we are also talking talking about the possible use of array as dynamic list。

 so there can be three scenarios in insertion。 first scenario will be when we want to insert an element at the beginning of the list。

 let's say we want to insert number three at the beginning of the list。



![](img/b0ec2f032554321893308df01f28831d_104.png)

![](img/b0ec2f032554321893308df01f28831d_105.png)

![](img/b0ec2f032554321893308df01f28831d_106.png)

In the case of array， we will have to shift each element by one position towards the higher index。

 so the time taken will be proportional to the size of the list。

 so this will be big O of n let's say n is the size of the list。

 this will be big O of n in terms of time complexity In the case of linked list inserting an element in the beginning。

 will mean only creating a new node and adjusting the head pointer and the link of this new node。

 So the time taken will not depend upon the size of the list it will be constant。

 So for linked list inserting an element at the beginning is big O of1 in terms of time complexity。



![](img/b0ec2f032554321893308df01f28831d_108.png)

![](img/b0ec2f032554321893308df01f28831d_109.png)

![](img/b0ec2f032554321893308df01f28831d_110.png)

![](img/b0ec2f032554321893308df01f28831d_111.png)

![](img/b0ec2f032554321893308df01f28831d_112.png)

![](img/b0ec2f032554321893308df01f28831d_113.png)

Inserting an element at end for an array， let's say we are talking about dynamic array。

 a dynamic list in which we create a new array if it gets filled filled if there is space in the array we just write to the next higher index of the list so it will be constant time so time complexity is over if array is not full if array is full we will have to create a new array and copy all the previous content into new array which will take O in time where n is the size of the list in the case of linked list adding an element inserting an element at the end will mean traversing the whole list and then creating a new node and adjusting the links so time taken will be proportional to n I'll use this this color coding for linked list。



![](img/b0ec2f032554321893308df01f28831d_115.png)

![](img/b0ec2f032554321893308df01f28831d_116.png)

![](img/b0ec2f032554321893308df01f28831d_117.png)

![](img/b0ec2f032554321893308df01f28831d_118.png)

![](img/b0ec2f032554321893308df01f28831d_119.png)

![](img/b0ec2f032554321893308df01f28831d_120.png)

![](img/b0ec2f032554321893308df01f28831d_121.png)

![](img/b0ec2f032554321893308df01f28831d_122.png)

Here and is the number of elements in the list。 Now。

 the third case would be when we want to insert in the middle of the list at some Nith position or maybe some Iith position。



![](img/b0ec2f032554321893308df01f28831d_124.png)

![](img/b0ec2f032554321893308df01f28831d_125.png)

Again， in the case of array， we will have to shift elements。



![](img/b0ec2f032554321893308df01f28831d_127.png)

NowFor the average case we may want to insert at the mid position in the array。

 so we will have to shift n by two elements where n is the number of elements in the list。

 so the time taken will is definitely proportional to n in average case so complexity will be big go of n for linked list also we will have to traverse till that position and then only we can adjust the links even though we will not have any shifting we will have to traverse till that point and in the average case time taken will be proportional to n。



![](img/b0ec2f032554321893308df01f28831d_129.png)

![](img/b0ec2f032554321893308df01f28831d_130.png)

![](img/b0ec2f032554321893308df01f28831d_131.png)

![](img/b0ec2f032554321893308df01f28831d_132.png)

![](img/b0ec2f032554321893308df01f28831d_133.png)

![](img/b0ec2f032554321893308df01f28831d_134.png)

![](img/b0ec2f032554321893308df01f28831d_135.png)

And the time complexity will be big of n。 if you can see deleting an element will also have these three scenarios and the time complexity for deleting for these three scenarios will also be the same。



![](img/b0ec2f032554321893308df01f28831d_137.png)

![](img/b0ec2f032554321893308df01f28831d_138.png)

And the final point， the final parameter that I want to talk about is which one is easy to use and implement and array definitely is a lot easier to use linked list implementation。

 especially in C or C plus+ is more prone to errors like segmentation fault and memory leak。

 It takes a good care to work with linked list。 So this was array versus linked list in our next lesson We will implement linked list in C or C plus+ we will get our hands dirty with some real code。

 So this is it for this lesson， thanks for watching。



![](img/b0ec2f032554321893308df01f28831d_140.png)

![](img/b0ec2f032554321893308df01f28831d_141.png)