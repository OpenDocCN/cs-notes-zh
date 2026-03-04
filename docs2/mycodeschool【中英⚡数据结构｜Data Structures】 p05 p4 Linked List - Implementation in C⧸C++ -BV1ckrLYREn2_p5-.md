# mycodeschool【中英⚡数据结构｜Data Structures】 p05 p4 Linked List - Implementation in C⧸C++ -BV1ckrLYREn2_p5-

In our previous lessons， we described linked list。 We saw the cost of various operations in linked list。

 and we also compared linked list with arrays。

![](img/a640654184be69c31222a364361d27d2_1.png)

So now let us implement linked list the implementation will be pretty similar in c and C plus plus there will be slight differences that we will discuss。



![](img/a640654184be69c31222a364361d27d2_3.png)

And the prerequisite for this lesson is that you should have a working knowledge of pointers in C++。

And you should also know the concept of dynamic memory allocation。

If you want to refresh any of these concepts。Check the description of this video for additional resources。

Okay， so let's get started。

![](img/a640654184be69c31222a364361d27d2_5.png)

As we know in a linked list data is stored in multiple noncontiguous blocks of memory and we call each block of memory a node in the linked list。

 so let me first draw a linked list here so we have a linked list of integers here with three nodes as we know each node has two fields or two parts one to store the data and another to store the address of the next node what we can also call link to the next node so let's say the address of the first node is 200 and address of the second node is 10 and the address of the third node is 300 for this linked list this is only a logical view of the linked list so the address part of the first node will be00 the address of the second node and we will have 300 here the address part of the last node will be null which is only a synonym or macro for address00 is an。



![](img/a640654184be69c31222a364361d27d2_7.png)

![](img/a640654184be69c31222a364361d27d2_8.png)

![](img/a640654184be69c31222a364361d27d2_9.png)

In valid address， a pointer variable equal to0 or null with address 0 or null means that the pointer variable does not point to a valid memory location。



![](img/a640654184be69c31222a364361d27d2_11.png)

![](img/a640654184be69c31222a364361d27d2_12.png)

The memory block， the address of the memory block allocated to each of the nodes。



![](img/a640654184be69c31222a364361d27d2_14.png)

Is totally random There is no relation。 It's not a guarantee that the addresses will be in increasing order or decreasing order or adjacent to each other。

 So that's why we need to keep these links。Now the identity of the linked list that we always keep with us is the address of the first node what we also call the head node。

 so we keep another variable that will be of type pointer to node and this guy will store the address of the first node and we can name this pointer variable whatever let's say this pointer variable is named a the name of this particular pointer variable that points to the head node or the first node can also be interpreted as the name for the linked list also because this is the only identity of the linked list that we keep with us all the time。



![](img/a640654184be69c31222a364361d27d2_16.png)

![](img/a640654184be69c31222a364361d27d2_17.png)

![](img/a640654184be69c31222a364361d27d2_18.png)

So let us now see how this logical view can be mapped to a real program in C or C++ in our program node will be a data type that will have two fields。

 one to store the data and another to store the address。



![](img/a640654184be69c31222a364361d27d2_20.png)

![](img/a640654184be69c31222a364361d27d2_21.png)

In C， we can define such a data type as structure， so let's say we define a structure named node with two fields。



![](img/a640654184be69c31222a364361d27d2_23.png)

![](img/a640654184be69c31222a364361d27d2_24.png)

First field to store the data， the type of the data here is integer so this will be node for a linked list of integer if we wanted a linked list of say double this data type would be double the second field will be pointer to nodestruct node star we can name this link or we can name this next or whatever。



![](img/a640654184be69c31222a364361d27d2_26.png)

![](img/a640654184be69c31222a364361d27d2_27.png)

![](img/a640654184be69c31222a364361d27d2_28.png)

![](img/a640654184be69c31222a364361d27d2_29.png)

This is C style of declaring node star or pointer to node。

 If this was c plus plus we could simply write node star。 I would write it this way。

 the C plus plus way it looks better to me。

![](img/a640654184be69c31222a364361d27d2_31.png)

In our logical view here， this variable a is of type node star or pointer to node each of these three rectangles with two fields。



![](img/a640654184be69c31222a364361d27d2_33.png)

Are of type node and this field in the node， the first field is of type in teacherger and the second field is of type pointer to node or node star。



![](img/a640654184be69c31222a364361d27d2_35.png)

![](img/a640654184be69c31222a364361d27d2_36.png)

It is important to know which one is what in the logical view。

 we should have this visualization before we go on to implement linked list。Okay。

 so let us now create this particular linked list of integer that we are showing here through our code。

To be able to do so， we will have to implement two operations。

 one to insert a node into the linked list， one operation to insert a node in the linked list and another operation to traverse the linked list。



![](img/a640654184be69c31222a364361d27d2_38.png)

But before that， the first thing that we want to do is that we want to declare a pointer to the head node。

 a variable that will store the address of the head node for the sake of clarity。

 I'll write head node here。

![](img/a640654184be69c31222a364361d27d2_40.png)

![](img/a640654184be69c31222a364361d27d2_41.png)

So I have declared a pointer to node named a initially when the list is empty when there is no element in the list。

 this pointer should point nowhere， So we write a statement something like a is equal to null to say the same with these two statements what we have done is we have created a pointer to node named a and this and this pointer points nowhere So the list is empty Now let's say we want to insert a node in this list。

 So what we do is we first create a node creating a node is nothing but creating a memory block to store a node in C we use the function malloc to create a memory block as argument we pass the number of bytes that we want in the block So we say that give me a memory block that will be equal to and the size of a node So this call to mall will create a memory block。



![](img/a640654184be69c31222a364361d27d2_43.png)

![](img/a640654184be69c31222a364361d27d2_44.png)

![](img/a640654184be69c31222a364361d27d2_45.png)

![](img/a640654184be69c31222a364361d27d2_46.png)

This is an dynamically allocated memory memory allocated during runtime and the only way to work with this kind of memory is through reference to this memory location through pointers let us assume that this memory block assigned here is that address 200 Now malloc returns a void pointer that gives us the address of assigned memory block so we need to collect it in some variable。

 so let's say we create a variable named temp which is pointer to node。

 so we can collect the return of malloc the address in this particular variable we will need a type casting here because malllock returns void pointer and we are having temp as pointer to node。

 So now we have created one node in the memory。

![](img/a640654184be69c31222a364361d27d2_48.png)

![](img/a640654184be69c31222a364361d27d2_49.png)

![](img/a640654184be69c31222a364361d27d2_50.png)

![](img/a640654184be69c31222a364361d27d2_51.png)

![](img/a640654184be69c31222a364361d27d2_52.png)

Now what we need to do is fill in the data in this particular node and adjust the links which will mean writing the correct address in the variable a and the link field of this newly created node to do so we will have to dereence this particular pointer variable that we just created as we know if we put an asterisk sign in front of the pointer variable we mean dereencing it to modify the value at that particular address now in this case we have a node which has two fields so once we dereence if we want to access each of the fields we need to put something like a dot data here。



![](img/a640654184be69c31222a364361d27d2_54.png)

To access the data and adoptt link to write to the link field。

 So we will write a statement like this to fill in value 2 here and we have this temp variable pointing to this right now。

And the link part of this newly created node should be null because。

Because this is the first and the last node。And the final thing that we need to do is write the address of this newly created node。



![](img/a640654184be69c31222a364361d27d2_56.png)

In a。 so we will write something like a is equal to temp。 Okay。

 temp was to temporarily store the address of the node till the time we had not fixed all the links properly。

 We can now use temp for some other purpose。 Our linked list is intact。 Now。 It has one node。



![](img/a640654184be69c31222a364361d27d2_58.png)

![](img/a640654184be69c31222a364361d27d2_59.png)

![](img/a640654184be69c31222a364361d27d2_60.png)

These two lines that we have written here for de referencing and writing the values into the new node。

 there is alternate syntax for this instead of writing something like start temp bracketed dot data。

 we could also write temp followed by this arrow。

![](img/a640654184be69c31222a364361d27d2_62.png)

And data we will have two characters to make this arrow。

 one hyphen and one this right angular bracket， right angular brace so we can write something like this。



![](img/a640654184be69c31222a364361d27d2_64.png)

And the same thing below， we can write something like。

This to create a memory block in C plus plus we can use malloc as well as we can use the new operator。

 so in C plus plus it gets very simple we could simply write node star temp is equal to new node like this and we would mean the same thing this is a lot cleaner and new operator is always preferred over malloc so if you are using c plus plus new is recommended。



![](img/a640654184be69c31222a364361d27d2_66.png)

![](img/a640654184be69c31222a364361d27d2_67.png)

![](img/a640654184be69c31222a364361d27d2_68.png)

![](img/a640654184be69c31222a364361d27d2_69.png)

![](img/a640654184be69c31222a364361d27d2_70.png)

So so far through our program we created an empty list by creating this pointer to the head node and assigning the value null to it initially。

 then we created a node and we added this first node in this linked list when the list is empty and we want to insert a node the logic is pretty straightforward when the list is not empty we may want to insert a node at the beginning of the list or we may want to insert a node at the end of the list or we may even want to insert a node somewhere in the middle of the list。



![](img/a640654184be69c31222a364361d27d2_72.png)

![](img/a640654184be69c31222a364361d27d2_73.png)

![](img/a640654184be69c31222a364361d27d2_74.png)

![](img/a640654184be69c31222a364361d27d2_75.png)

At a particular position， we will write separate functions and routines for these different kind of insertions。

 and we will see running code in a compiler。In our coming lessons。

 let let's just talk about the logic here in this whatever unstructured code I have right now。

 So I want to write a code to insert two more nodes each time at the end of the list。

 we actually want to create the linked list with three nodes having values 2，4 and 6。



![](img/a640654184be69c31222a364361d27d2_77.png)

![](img/a640654184be69c31222a364361d27d2_78.png)

That was our initial example in the beginning Okay。

 so let us add two more nodes with values 4 and 6 into this linked list at this stage in our code。

 we already have a variable temp which is pointing to this particular node we will create a new node and use the same variable name to collect the address of this new node so we will write a statement like this So a new node is created and temp now stores the address of this new node which is located at address hundred here once again we can set the data and then because this is going to be the last node we need to set the link as null now all we need to do is build the link of this particular node right the address of this newly created node into the address field of this last node。



![](img/a640654184be69c31222a364361d27d2_80.png)

![](img/a640654184be69c31222a364361d27d2_81.png)

![](img/a640654184be69c31222a364361d27d2_82.png)

![](img/a640654184be69c31222a364361d27d2_83.png)

![](img/a640654184be69c31222a364361d27d2_84.png)

![](img/a640654184be69c31222a364361d27d2_85.png)

![](img/a640654184be69c31222a364361d27d2_86.png)

To do so， we will have to traverse the list， and we will have to go to the end of the list to do so。

 we will write something like this。 We can create a new variable temp 1。

 which will be pointed to node。 And initially we can point to the head node。

 point this variable to the head node by a statement like this。 We can write a loop like this。

 Now this is generic logic to reach the end of the list。

 it will not be so clear if we see this logic with only one node as we have in this example。

 let's draw a list with multiple nodes。 So we are pointing temp1 to the first node here。

 And if the link part of this node is null， we are at the last node else。

 we can move to the next node。 So temp1 equal temp1 do link will get us to the next node and we will go on till we reach the last node。



![](img/a640654184be69c31222a364361d27d2_88.png)

![](img/a640654184be69c31222a364361d27d2_89.png)

![](img/a640654184be69c31222a364361d27d2_90.png)

![](img/a640654184be69c31222a364361d27d2_91.png)

![](img/a640654184be69c31222a364361d27d2_92.png)

![](img/a640654184be69c31222a364361d27d2_93.png)

![](img/a640654184be69c31222a364361d27d2_94.png)

For the last node， this particular condition， temp1 dot link。

 not equal null will be false because the link part will be null and we will exit this while loop。

 So this is our code logic for traveral of the list all the way till end if we want to print the elements in the list we will write something like this and we will write print temp dot data inside this while loop but right now we want to insert in the at the end of the list and we are only traversing the list to reach the last node there is one more thing that I want to point out we are using this variable temp1 and initially storing the address in a we are not doing something like a equal a dot link and using the variable a itself to traverse the list because if we modify a。

 we will lose on the address of the head node So a is never modified the address of the head node。

 whatever variable stores the address of the head node is never modified only these temporary variables are modified to traverse the list So finally after all this。



![](img/a640654184be69c31222a364361d27d2_96.png)

![](img/a640654184be69c31222a364361d27d2_97.png)

![](img/a640654184be69c31222a364361d27d2_98.png)

![](img/a640654184be69c31222a364361d27d2_99.png)

We will write a statement like temp1。 link is equal to temp temp 1 is pointing here。

 so now this address part is updated and this link is built so we have two nodes now in the list。



![](img/a640654184be69c31222a364361d27d2_101.png)

![](img/a640654184be69c31222a364361d27d2_102.png)

![](img/a640654184be69c31222a364361d27d2_103.png)

Once again， when we want to insert node with number 6 in this list。

 we will have to create a new node by this logic， then we will have to traverse the list by this logic。

 so we will point temp1 here first and then the loop will move the temp1 to the end。

 let's say this new block is at address 300。 so this last line finally will adjust the link of the node at address hundred to insert a node at the end there is one logic in these four lines if the list is empty and there is another logic in these remaining lines if the list is not empty ideally we will be writing all these logic。

 all these logic in a function we will do that in our coming lessons。

 we will implement separate methods to print all the nodes in a linked list and to insert a node at the end we will implement a separate method to insert a node at the beginning of the list and at a particular position in the list so this is all for this lesson thanks for watching。



![](img/a640654184be69c31222a364361d27d2_105.png)

![](img/a640654184be69c31222a364361d27d2_106.png)

![](img/a640654184be69c31222a364361d27d2_107.png)

![](img/a640654184be69c31222a364361d27d2_108.png)

![](img/a640654184be69c31222a364361d27d2_109.png)

![](img/a640654184be69c31222a364361d27d2_110.png)