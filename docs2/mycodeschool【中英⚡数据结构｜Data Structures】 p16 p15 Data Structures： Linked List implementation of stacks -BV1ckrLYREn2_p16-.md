# mycodeschool【中英⚡数据结构｜Data Structures】 p16 p15 Data Structures： Linked List implementation of stacks -BV1ckrLYREn2_p16-

In our previous lesson we saw how we can implement stack using arrays now in this lesson we will see how we can implement stack using linked list。

For this lesson Im assuming that you already know about both stack as well as linked list stack as we know from our discussion so far is called a last in first out data structure。



![](img/c438207c84c03a0a066706c1e948823f_1.png)

Whatever goes in last in a stack comes out first， it is a list with this restriction that insertion and deletion must be performed only from one end that we call the top of stack an insertion in a stack is called push operation and deletion is called pop。

To implement a stack all we need to do is enforce this behavior in any implementation of a list that insertion and deletion must be performed only from one end and we can call that end top of stack it is really easy to enforce this behavior in a linked list I have drawn a linked list of integers here this is logical representation of a linked list a linked list is a collection of entities that we call nodes each node contains two fields one to store data and another。



![](img/c438207c84c03a0a066706c1e948823f_3.png)

To store the address of the next node， let's assume that these nodes are at address as 100 200 and 400 respectively。

 so I will fill up the address part as well， the identity of a linked list is the address of the first node that we also call the head node。

 a variable stores the address of head node we often name this variable as head unlike a linked lists are not a fixed size and elements in a linked list are not stored in one contiguous block of memory。



![](img/c438207c84c03a0a066706c1e948823f_5.png)

![](img/c438207c84c03a0a066706c1e948823f_6.png)

We already know how to create a linked list or insert and delete elements from a linked list from our previous lessons。

 I'm just doing a quick recap here。To insert an element in a linked list we first create a new node which is basically blocking some part of memory to store our data in this example here let's say for my new node I'm getting addressed 350 we can set the data part of the linked list as whatever value I want to add in the list and then I need to modify the address field of some of the existing nodes to link this node in actual list now for a stack we want that insertion and deletion must always happen from the same end we can use a linked list at stack if we always insert and delete a node at same end we have two options。



![](img/c438207c84c03a0a066706c1e948823f_8.png)

![](img/c438207c84c03a0a066706c1e948823f_9.png)

![](img/c438207c84c03a0a066706c1e948823f_10.png)

![](img/c438207c84c03a0a066706c1e948823f_11.png)

![](img/c438207c84c03a0a066706c1e948823f_12.png)

We can insert or delete from end of the list what we also call tail or。



![](img/c438207c84c03a0a066706c1e948823f_14.png)

![](img/c438207c84c03a0a066706c1e948823f_15.png)

Beginning of the list that we call head。If you remember from our previous lessons inserting a node at end of linked list is not a constant time operation the cost of both insertion and deletion at end of linked list if we have to talk about the time complexity of it is big O of n here in the definition of stack we are saying that push and pop operations should take constant time or their time complexity should be big o of1 but if we will insert and delete from end time complexity will be big O of n to insert a new node in a linked list at the end we need to go to the last node and set the address part of that node to make it point to the new node to traverse a linked list and go to the last node we should start at the head or the first node from first node we get the address of the second node so we go to the second node and from second node we get the address of the third node it's like playing treasure hunt。



![](img/c438207c84c03a0a066706c1e948823f_17.png)

![](img/c438207c84c03a0a066706c1e948823f_18.png)

![](img/c438207c84c03a0a066706c1e948823f_19.png)

![](img/c438207c84c03a0a066706c1e948823f_20.png)

You go to the first guy ask the address of the second guy and then you go to the second guy。

 ask the address of the third guy and so on Now once I've reached this last node in my example here。

 I can set its address part to make it point to the newly created node all in all this operation will take time proportional to number of elements in the linked list。



![](img/c438207c84c03a0a066706c1e948823f_22.png)

![](img/c438207c84c03a0a066706c1e948823f_23.png)

To delete a node from end， once again we will have to traverse the whole list。



![](img/c438207c84c03a0a066706c1e948823f_25.png)

We will have to。Go to the second last node， break this link。

 we will set the address field as0 or null and then we can simply wipe off the last node removed from the list from computers memory once again the cost of Traveral will be big O of n。



![](img/c438207c84c03a0a066706c1e948823f_27.png)

![](img/c438207c84c03a0a066706c1e948823f_28.png)

So inserting and deleting at end or tail is not an option for us because we will not be able to do push and pop in constant time if we choose to insert and delete from end the cost of inserting or deleting from beginning。

 however。

![](img/c438207c84c03a0a066706c1e948823f_30.png)

Is big O of one。It will take constant time to insert a node at beginning or delete a node from beginning。



![](img/c438207c84c03a0a066706c1e948823f_32.png)

To insert a node at beginning we must create a new node in this example here。

 once again I have created a new node， let's say the address of the new node is 350 I will insert some data in the first field of this node okay so to insert this node at beginning we just need to build tool links first we need to build this link so we will set the address here as whatever the address of the current head is and then we can break this link and make this guy the new head。



![](img/c438207c84c03a0a066706c1e948823f_34.png)

![](img/c438207c84c03a0a066706c1e948823f_35.png)

![](img/c438207c84c03a0a066706c1e948823f_36.png)

By setting its address here in this variable， named head。



![](img/c438207c84c03a0a066706c1e948823f_38.png)

To delete a node in this example here we will have to first cut this link and build this link which will mean resetting the address in this variable head。

 and then we can free the memory allocated to this particular guy。

 this particular node deletion from beginning once again is a constant time operation。

 so this is the thing if we will insert at beginning and delete from beginning。

 then all our conditions are satisfied。

![](img/c438207c84c03a0a066706c1e948823f_40.png)

![](img/c438207c84c03a0a066706c1e948823f_41.png)

![](img/c438207c84c03a0a066706c1e948823f_42.png)

So linked list implementation of stack is pretty straightforward。

 all we need to do is insert a node at the beginning and delete a node from beginning so head of the linked list is basically the top of stack I would rather name this variable top here。



![](img/c438207c84c03a0a066706c1e948823f_44.png)

![](img/c438207c84c03a0a066706c1e948823f_45.png)

I'll quickly write a basic implementation in C I' am defining node as a structure in C I want to create a stack of integers so first field in the node is an integer another field is pointer to node that will store the address of the next node we have seen this definition of node in all our previous lessons on linked list the next thing that I am doing is I am declaring a variable named top which is pointer to node and initially I am setting the address in it as null I'm using variable named top instead of head here when top is null our stack is empty by initializing top as null I am saying that initially my stack is empty。



![](img/c438207c84c03a0a066706c1e948823f_47.png)

![](img/c438207c84c03a0a066706c1e948823f_48.png)

![](img/c438207c84c03a0a066706c1e948823f_49.png)

![](img/c438207c84c03a0a066706c1e948823f_50.png)

![](img/c438207c84c03a0a066706c1e948823f_51.png)

![](img/c438207c84c03a0a066706c1e948823f_52.png)

Now let's write push and pop functions This is my push function push is taking an integer x as argument that must be inserted onto the stack the first thing that we are doing in push function is that we are creating a node using Malo let's say in this example in this logical representation that I'm showing here I am performing a push operations so I' am making a call to push function passing it number two as argument so a node is created in memory is created in what we call the dynamic memory or heap let's say the address of this node is0 this variable is basically a pointer pointing to this node temp is a pointer pointing to this node in the next line we are setting the data field in this node。



![](img/c438207c84c03a0a066706c1e948823f_54.png)

![](img/c438207c84c03a0a066706c1e948823f_55.png)

![](img/c438207c84c03a0a066706c1e948823f_56.png)

We are de referferencing temp to do so。Then we are setting the link part of this newly created node as existing top so we are building this link and then we are saying top equal temps so we are building this link。

 this is simple insertion at beginning of a linked list we have one complete video in this series on how to insert a node at beginning of linked list let's do one more push let's say I want to push number5 onto the stack this time once again a node will be created we will set the data and then we will first point this guy to the existing top。



![](img/c438207c84c03a0a066706c1e948823f_58.png)

![](img/c438207c84c03a0a066706c1e948823f_59.png)

And then make this pointer variable point to this guy， the new top。

Let's say the address of this guy is 250 so the address in this variable top will be set as 250 after this second push this is how my stack will look like。



![](img/c438207c84c03a0a066706c1e948823f_61.png)

Top here is a global variable so we do not need to pass it as argument to functions it is accessible to all the functions in an object oriented implementation it can be a private field and we can set it as null in the constructor。



![](img/c438207c84c03a0a066706c1e948823f_63.png)

![](img/c438207c84c03a0a066706c1e948823f_64.png)

Okay， let's now see how push， sorry pop function will look like。



![](img/c438207c84c03a0a066706c1e948823f_66.png)

This is my P function， let's say for this example， I'm making a call to P function。



![](img/c438207c84c03a0a066706c1e948823f_68.png)

If the stack is already empty。We can check whether stack is empty or not by checking whether top is null or not if top is null stack is empty in this case we can throw some error and return for this example here stack is not empty we have two integers in the stack what we are first doing is we are creating a pointer to node temp and pointing it to the top node and now we are breaking this link we are setting the address in top as address of the next node。



![](img/c438207c84c03a0a066706c1e948823f_70.png)

![](img/c438207c84c03a0a066706c1e948823f_71.png)

![](img/c438207c84c03a0a066706c1e948823f_72.png)

![](img/c438207c84c03a0a066706c1e948823f_73.png)

![](img/c438207c84c03a0a066706c1e948823f_74.png)

And now using this pointer variable temp， we are freeing the memory allocated to the node being removed from the list once I exit the pop function。

 this is my stack。

![](img/c438207c84c03a0a066706c1e948823f_76.png)

![](img/c438207c84c03a0a066706c1e948823f_77.png)

So this pretty much is the core of our implementation I would encourage you to write rest of the stuff yourself。

 you can write code for operations like top and is empty linked list implementation of stack has some advantages one of the advantages is that unlike array based implementation we do not need to worry about overflow unless we exhaust the memory of the machine itself some amount of extra memory is used in each node to store reference or address but the fact that we use memory when needed and release when not needed is something that makes push and pop operations more graceful so this is linked listbased implementation of stack in our coming lessons we will solve some problems using stack this is it for this lesson thanks for watching。



![](img/c438207c84c03a0a066706c1e948823f_79.png)

![](img/c438207c84c03a0a066706c1e948823f_80.png)

![](img/c438207c84c03a0a066706c1e948823f_81.png)

![](img/c438207c84c03a0a066706c1e948823f_82.png)

![](img/c438207c84c03a0a066706c1e948823f_83.png)

![](img/c438207c84c03a0a066706c1e948823f_84.png)