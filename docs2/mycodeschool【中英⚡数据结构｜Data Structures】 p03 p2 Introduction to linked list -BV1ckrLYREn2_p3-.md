# mycodeschool【中英⚡数据结构｜Data Structures】 p03 p2 Introduction to linked list -BV1ckrLYREn2_p3-

In this lesson we will introduce you to linked list data structure。



![](img/9cf1bf71440583e497998c584e7bc225_1.png)

In our previous lesson， we tried to implement a dynamic list using arrays and we had some issues there。



![](img/9cf1bf71440583e497998c584e7bc225_3.png)

It was not most efficient in terms of memory usage， in terms of memory consumption。



![](img/9cf1bf71440583e497998c584e7bc225_5.png)

When we use arrays， we have some limitations。To be able to understand linked list well。

 we need to understand these limitations。 So I am going to tell you a simple story to help you understand this。



![](img/9cf1bf71440583e497998c584e7bc225_7.png)

![](img/9cf1bf71440583e497998c584e7bc225_8.png)

Let us say this is computer's memory and each partition here is one bitete of memory。 Now。

 as we know， each bitte of memory has an address。

![](img/9cf1bf71440583e497998c584e7bc225_10.png)

![](img/9cf1bf71440583e497998c584e7bc225_11.png)

We are showing only a section of the memory。 that's why it is extending towards the bottom and the top。

 Let's say the address increases from bottom to top。 So if this by is addressed 200。

 the next by would be addressed 201 and next by would be addressed 20，2 and so on。



![](img/9cf1bf71440583e497998c584e7bc225_13.png)

![](img/9cf1bf71440583e497998c584e7bc225_14.png)

![](img/9cf1bf71440583e497998c584e7bc225_15.png)

What I want to do is I want to draw this memory from left to right horizontally instead of trying it from bottom to top like this。



![](img/9cf1bf71440583e497998c584e7bc225_17.png)

![](img/9cf1bf71440583e497998c584e7bc225_18.png)

This looks better。

![](img/9cf1bf71440583e497998c584e7bc225_20.png)

Let's say this by here is address 200。 and as we go towards the right， the address increases。

 So this is like 20，1 and we go on like 2，0，2，20，3， and so on。



![](img/9cf1bf71440583e497998c584e7bc225_22.png)

![](img/9cf1bf71440583e497998c584e7bc225_23.png)

It doesn't really matter whether we show memory from bottom to top or left to right。

 These are just logical ways to look at the memory。 So coming back to our story。

 Meory is a crucial resource， and all the applications keep asking for it。 So Mr。

 Computer has given this job of managing the memory to one of his components to one of his guys who he calls the memory manager。

 Now， this guy keeps track of。

![](img/9cf1bf71440583e497998c584e7bc225_25.png)

![](img/9cf1bf71440583e497998c584e7bc225_26.png)

![](img/9cf1bf71440583e497998c584e7bc225_27.png)

![](img/9cf1bf71440583e497998c584e7bc225_28.png)

![](img/9cf1bf71440583e497998c584e7bc225_29.png)

What part of the memory is free and what part of the memory is allocated。

 and anyone who needs memory to store something needs to talk to this guy。



![](img/9cf1bf71440583e497998c584e7bc225_31.png)

![](img/9cf1bf71440583e497998c584e7bc225_32.png)

Albert is our programmer， and he is building an application。

 He needs to store some data in the memory， so he needs to talk to the memory manager。

 He can talk to the memory manager in a high level language like C。

 Let us say that he is using C to talk to the memory manager。 First。

 he wants to store an integer in the memory。 So he communicates this to memory manager by declaring an integer variable。



![](img/9cf1bf71440583e497998c584e7bc225_34.png)

![](img/9cf1bf71440583e497998c584e7bc225_35.png)

![](img/9cf1bf71440583e497998c584e7bc225_36.png)

![](img/9cf1bf71440583e497998c584e7bc225_37.png)

![](img/9cf1bf71440583e497998c584e7bc225_38.png)

Something like this。

![](img/9cf1bf71440583e497998c584e7bc225_40.png)

The memory manager sees this declaration and he says that okay。

 you need to store an integer variable so I need to give you four bytes of memory because integer variable is stored in four bytes in a typical architecture and let us say in this architecture it is stored in four bytes。



![](img/9cf1bf71440583e497998c584e7bc225_42.png)

![](img/9cf1bf71440583e497998c584e7bc225_43.png)

![](img/9cf1bf71440583e497998c584e7bc225_44.png)

So the memory manager looks for four bytes of free space in the memory and assigns it or allocates it for variable X address of a block of memory is the address of the first byte in the memory。

 So let us say this first bite of memory here is。

![](img/9cf1bf71440583e497998c584e7bc225_46.png)

![](img/9cf1bf71440583e497998c584e7bc225_47.png)

![](img/9cf1bf71440583e497998c584e7bc225_48.png)

At address 2，1，7。So variable X is at address 2，1，7。

 So memory manager kind of communicates it back to Albert that， hey。

 I have assigned signed address 2，1，7 for your variable x。 You can store whatever you want there。

 and Albert can fill in any data into this variable。



![](img/9cf1bf71440583e497998c584e7bc225_50.png)

![](img/9cf1bf71440583e497998c584e7bc225_51.png)

![](img/9cf1bf71440583e497998c584e7bc225_52.png)

![](img/9cf1bf71440583e497998c584e7bc225_53.png)

Now， Albert needs to store a list of integers， a list of numbers。



![](img/9cf1bf71440583e497998c584e7bc225_55.png)

And he thinks that the maximum number of integers in this list will be 4。

 So he asks the memory manager for an integer array of size 4 named a。 Now。

 array is always stored in memory as one contiguous block of memory。 So memory manager is like， okay。

 I need to look for a block of memory of 16 bys。

![](img/9cf1bf71440583e497998c584e7bc225_57.png)

![](img/9cf1bf71440583e497998c584e7bc225_58.png)

![](img/9cf1bf71440583e497998c584e7bc225_59.png)

For this variable， this array， a。 So the memory manager allocates this block， starting address 2，0。

1 and ending address。

![](img/9cf1bf71440583e497998c584e7bc225_61.png)

![](img/9cf1bf71440583e497998c584e7bc225_62.png)

2 and6 for this variable， a， which is an array of foreign teachers。



![](img/9cf1bf71440583e497998c584e7bc225_64.png)

Because array is stored as one contiguous block of memory。

 and memory manager conveys the starting address of this block。

 When Albert tries to access any of the elements in the array， let's say he tries to access。

 Let's say he tries to write some value at the。

![](img/9cf1bf71440583e497998c584e7bc225_66.png)

![](img/9cf1bf71440583e497998c584e7bc225_67.png)

![](img/9cf1bf71440583e497998c584e7bc225_68.png)

Fourth element in the array， which he accesses as a3。

 Albertt's application knows where to write this particular value because it knows the base address。

 the starting address of the block a， the array A and from base address using the index。

 which is3 here。

![](img/9cf1bf71440583e497998c584e7bc225_70.png)

![](img/9cf1bf71440583e497998c584e7bc225_71.png)

![](img/9cf1bf71440583e497998c584e7bc225_72.png)

It calculates the address of a3， so it knows that a3 is that address 2 and3。

 so to access any of the elements in the array， the application takes constant time。



![](img/9cf1bf71440583e497998c584e7bc225_74.png)

![](img/9cf1bf71440583e497998c584e7bc225_75.png)

And this is one awesome thing about arrays that irrespective of the size of the arrays。

 the application and application can access any of the elements in the array in constant time。



![](img/9cf1bf71440583e497998c584e7bc225_77.png)

![](img/9cf1bf71440583e497998c584e7bc225_78.png)

Now let's say Albert uses this array of foreign teachers to store his list。

 So I'll fill in some values here at these positions。 Let's say this is 8， this is2， this is 6。

 this is 5， this is4。

![](img/9cf1bf71440583e497998c584e7bc225_80.png)

![](img/9cf1bf71440583e497998c584e7bc225_81.png)

![](img/9cf1bf71440583e497998c584e7bc225_82.png)

Now， Albert at some point feels that， okay， I need to have one more element in this list。



![](img/9cf1bf71440583e497998c584e7bc225_84.png)

Now， he has declared an array of size 4， and he wants to add a fifth element in the array。

 So he asks the memory manager that， hey， I want to extend my array a。

Is it possible to do so I want to extend the same block and the memory manager is like when I allocate memory for an array。

 I do not expect that you will ask for an extension。

 so I use whatever memory is available adjacent to that block for other variables in some cases I may extend the same block。

 but in this case I have an element and a variable X next to your block。

 so I cannot give you an extension。

![](img/9cf1bf71440583e497998c584e7bc225_86.png)

![](img/9cf1bf71440583e497998c584e7bc225_87.png)

![](img/9cf1bf71440583e497998c584e7bc225_88.png)

![](img/9cf1bf71440583e497998c584e7bc225_89.png)

![](img/9cf1bf71440583e497998c584e7bc225_90.png)

![](img/9cf1bf71440583e497998c584e7bc225_91.png)

So Albert is like， what all options do I have Me manager is like， You can tell me the new size。

 and I can recreate a new block at some new address。

 and we will have to copy all the elements from the previous block to the new block。

 So Albert says that， okay， let's do it。 But the memory manager is like。

 you still need to give me the size of the new block。

 Albert thinks that this time he'll give a really large size for the new array or the new block so that it does not fill up。

 This new block starting address 2 to 4 is allocated。

 Albert asks memory manager to free the previous block。

 And this is some cost he has to copy all the elements。

 all the numbers from the previous block into the new block。

 And now he can add one more element to this list。 And he has kept his a large this time just in case he needs more numbers in the list。



![](img/9cf1bf71440583e497998c584e7bc225_93.png)

![](img/9cf1bf71440583e497998c584e7bc225_94.png)

![](img/9cf1bf71440583e497998c584e7bc225_95.png)

![](img/9cf1bf71440583e497998c584e7bc225_96.png)

![](img/9cf1bf71440583e497998c584e7bc225_97.png)

![](img/9cf1bf71440583e497998c584e7bc225_98.png)

![](img/9cf1bf71440583e497998c584e7bc225_99.png)

![](img/9cf1bf71440583e497998c584e7bc225_100.png)

So the only option that Albert had was to create a as an entirely new block as an entirely new array。



![](img/9cf1bf71440583e497998c584e7bc225_102.png)

![](img/9cf1bf71440583e497998c584e7bc225_103.png)

And Alberttis is still feeling bad because if the list is too small。

 he is not using some part of the array， and so memory is getting wasted and if the list again grows too much。

 he will again have to create a new array， a new block and he will again have to copy all the elements from the previous block into the new block。



![](img/9cf1bf71440583e497998c584e7bc225_105.png)

![](img/9cf1bf71440583e497998c584e7bc225_106.png)

![](img/9cf1bf71440583e497998c584e7bc225_107.png)

![](img/9cf1bf71440583e497998c584e7bc225_108.png)

Albert is desperately seeking a solution to this problem。

 and the solution to this problem is a data structure。



![](img/9cf1bf71440583e497998c584e7bc225_110.png)

![](img/9cf1bf71440583e497998c584e7bc225_111.png)

Named linked list， So let us now try to understand linked list data structure and see how it solves Albert's problem。



![](img/9cf1bf71440583e497998c584e7bc225_113.png)

What Albert can do is that instead of asking the memory manager for an array。

 which will be one large contiguous block of memory。

 he can ask memory for one unit of data at a time， for one element at a time in a separate request。



![](img/9cf1bf71440583e497998c584e7bc225_115.png)

![](img/9cf1bf71440583e497998c584e7bc225_116.png)

![](img/9cf1bf71440583e497998c584e7bc225_117.png)

I'm cleaning up the memory here。Once again， let's say Albert wants to store this list of four integers in the memory。

 What if he requests memory for one integer at a time。

 So first hepings memory manager for some memory to store number 6 memory manager will be like， okay。

 you need space to store an integer So you get this block of 4 bytes at address2，0，4。

 So Albert can store number 6 here。 Now Albert makes another request a separate request for number 5。

 Let's say he gets this block starting address 2，1，7 for number 5。

 because he makes a separate request。 He may or may not get memory adjacent to number 6。

 High probability is that he will not get an adjacent memory location。 So similarly。

 Albert makes separate requests for number 4 and 2。

 So let's say he gets these two blocks at address 2，3，2 and 2，42 respectively for number4 and 2。

 So as you can see when Albert makes separate requests for each integer。



![](img/9cf1bf71440583e497998c584e7bc225_119.png)

![](img/9cf1bf71440583e497998c584e7bc225_120.png)

![](img/9cf1bf71440583e497998c584e7bc225_121.png)

![](img/9cf1bf71440583e497998c584e7bc225_122.png)

![](img/9cf1bf71440583e497998c584e7bc225_123.png)

![](img/9cf1bf71440583e497998c584e7bc225_124.png)

![](img/9cf1bf71440583e497998c584e7bc225_125.png)

![](img/9cf1bf71440583e497998c584e7bc225_126.png)

![](img/9cf1bf71440583e497998c584e7bc225_127.png)

Instead of getting one contiguous block of memory， he gets these disjoint non contiguous blocks of memory。



![](img/9cf1bf71440583e497998c584e7bc225_129.png)

![](img/9cf1bf71440583e497998c584e7bc225_130.png)

So we need to store some more information here， We need to store the information that this is the first element in the list and this is the second element in this list。

 so we need to link these blocks together somehow with an array it was very simple we had one contiguous block of memory so we knew where a particular element is by calculating its address using the starting address of the block and the position of the element in the array but here we need to store the information that this is the first block which stores the first element and this is the second block which stores the second element and so on。



![](img/9cf1bf71440583e497998c584e7bc225_132.png)

![](img/9cf1bf71440583e497998c584e7bc225_133.png)

![](img/9cf1bf71440583e497998c584e7bc225_134.png)

![](img/9cf1bf71440583e497998c584e7bc225_135.png)

To link these blocks together and to store the information that this is the first block in the list and this is the second block in the list。

 what we can do is that we can store some extra information with each block。

 So what if we can have two parts in each block， something like this。



![](img/9cf1bf71440583e497998c584e7bc225_137.png)

![](img/9cf1bf71440583e497998c584e7bc225_138.png)

![](img/9cf1bf71440583e497998c584e7bc225_139.png)

And in one part of the block， we stored the data or the value， and in the other part of the block。

 we stored the address of the next block。

![](img/9cf1bf71440583e497998c584e7bc225_141.png)

In this example in the first block， the address part would be 21，7。

 the address of the next block that stores5。And in this next block or the second block。

 the address part would be2，3，2。

![](img/9cf1bf71440583e497998c584e7bc225_143.png)

In the block at address 2，3，2， we will store the address 242。

 the address of the next block that stores number 2， and the block at 242 is the last block。

 there is no next block after this， so in the address part we can have address as 00 is invalid valid address0 can be used to mark that this is the end of the list。

 there is no link to the next node or next block after this particular block。



![](img/9cf1bf71440583e497998c584e7bc225_145.png)

![](img/9cf1bf71440583e497998c584e7bc225_146.png)

![](img/9cf1bf71440583e497998c584e7bc225_147.png)

![](img/9cf1bf71440583e497998c584e7bc225_148.png)

So all but now actually has to request memory manager for a block of memory that will store two variables。

 one an integer variable that will store the value of our element and one a pointer variable that will store the address of the next block or the next node in the list。



![](img/9cf1bf71440583e497998c584e7bc225_150.png)

![](img/9cf1bf71440583e497998c584e7bc225_151.png)

![](img/9cf1bf71440583e497998c584e7bc225_152.png)

![](img/9cf1bf71440583e497998c584e7bc225_153.png)

In C， he can define a type named node like this。 He will have two fields in the node。

1 to store the data。 This field will be an integer and one more field to store the address of。



![](img/9cf1bf71440583e497998c584e7bc225_155.png)

![](img/9cf1bf71440583e497998c584e7bc225_156.png)

The next node in the list， So Albert will ask a node。

 Albert will ask memory for a node from the memory manager and the memory manager will be like， okay。

 you need a node that needs four bytes for an integer variable and four more bytes for the pointer variable that will store the address pointer variable also in a typical architecture is stored in four bytes。

 So now memory manager gives us a block of8 byte and we call this block a node。



![](img/9cf1bf71440583e497998c584e7bc225_158.png)

![](img/9cf1bf71440583e497998c584e7bc225_159.png)

![](img/9cf1bf71440583e497998c584e7bc225_160.png)

![](img/9cf1bf71440583e497998c584e7bc225_161.png)

![](img/9cf1bf71440583e497998c584e7bc225_162.png)

![](img/9cf1bf71440583e497998c584e7bc225_163.png)

Now notice that the second field in the node structure is node star， which means pointer to node。

 so this field will only store an address of the next node in the list。

 so if we store the list like this in the memory as these noncontiguous nodes connected to each other then this is a linked list data structure。



![](img/9cf1bf71440583e497998c584e7bc225_165.png)

![](img/9cf1bf71440583e497998c584e7bc225_166.png)

![](img/9cf1bf71440583e497998c584e7bc225_167.png)

![](img/9cf1bf71440583e497998c584e7bc225_168.png)

![](img/9cf1bf71440583e497998c584e7bc225_169.png)

Logical view of the linked list data structure will be something like this Data is stored in these nodes and each node stored the data as well as the link to the next node。

 So each node kind of points to the next node， the first node is also called the head node and the only information about the list that we keep all the time is address of the head node or address of the first node。

 So address of the head node kind of gives us access to the complete list。



![](img/9cf1bf71440583e497998c584e7bc225_171.png)

![](img/9cf1bf71440583e497998c584e7bc225_172.png)

![](img/9cf1bf71440583e497998c584e7bc225_173.png)

![](img/9cf1bf71440583e497998c584e7bc225_174.png)

![](img/9cf1bf71440583e497998c584e7bc225_175.png)

The address in the last node is null or0， which means that the last node does not point to any other node Now if we want to traverse the linked list。

 the only way to do it is we start at the head we go to the first guy and then we ask the first guy the address of the next guy address of the next node and then we go to the next node and ask the address of the next node and this is the only way to access the elements in the linked list。

 if we want to insert a node in the linked list， let's say we want to add number three at the end of the linked list then all we need to do is first create a node in the linked list。



![](img/9cf1bf71440583e497998c584e7bc225_177.png)

![](img/9cf1bf71440583e497998c584e7bc225_178.png)

![](img/9cf1bf71440583e497998c584e7bc225_179.png)

![](img/9cf1bf71440583e497998c584e7bc225_180.png)

![](img/9cf1bf71440583e497998c584e7bc225_181.png)

![](img/9cf1bf71440583e497998c584e7bc225_182.png)

Sorry， first create a node independently and separately it will get some memory location。

 So we created this node with value 3。 Now all we need to do is fill the address properly。

 adjust this links properly So the address of this particular node。



![](img/9cf1bf71440583e497998c584e7bc225_184.png)

![](img/9cf1bf71440583e497998c584e7bc225_185.png)

![](img/9cf1bf71440583e497998c584e7bc225_186.png)

![](img/9cf1bf71440583e497998c584e7bc225_187.png)

Will be filled in this node with value 2。 And this node that rest part can be null。

 So it is the last node。 It does not point to any other node。

 Let's also show this these nodes in the memory here。



![](img/9cf1bf71440583e497998c584e7bc225_189.png)

![](img/9cf1bf71440583e497998c584e7bc225_190.png)

![](img/9cf1bf71440583e497998c584e7bc225_191.png)

So I've written the address of each node in brown at top of these nodes。

 and I've also filled in this address field of each node。

 let's say the node for value 3 gets address 2，52。 So this is how things will be in the memory and this is how the logical view will be。

 the linked list is always identified by the address of the first node。 and unlike arrays。

 we cannot access any of the elements in constant time in the case of a using the starting address of the block of memory and using the position of the element in the list。

 we could calculate the address of the element。 but in this case。

 we have to start at the head and we have to ask this element for next element and then ask the next element who is your next it's like playing treasure hunt。

 you go to the first guy and then you get the address for the second guy and then you go to the second guy and you get the address for the third guy。

 So the time taken to access elements will be proportional to。



![](img/9cf1bf71440583e497998c584e7bc225_193.png)

![](img/9cf1bf71440583e497998c584e7bc225_194.png)

![](img/9cf1bf71440583e497998c584e7bc225_195.png)

![](img/9cf1bf71440583e497998c584e7bc225_196.png)

![](img/9cf1bf71440583e497998c584e7bc225_197.png)

![](img/9cf1bf71440583e497998c584e7bc225_198.png)

![](img/9cf1bf71440583e497998c584e7bc225_199.png)

![](img/9cf1bf71440583e497998c584e7bc225_200.png)

![](img/9cf1bf71440583e497998c584e7bc225_201.png)

![](img/9cf1bf71440583e497998c584e7bc225_202.png)

![](img/9cf1bf71440583e497998c584e7bc225_203.png)

Size of the list， let's say the size of the list is n there are n elements in the list in the worst case to traverse the last element you will go through all the elements so time taken to access elements is proportional to n or in other words we say that this operation will cost us or rather the time complexity of this operation is big O of n insertion into the list we can insert anywhere in the list we first need to create a node and just adjust these links。



![](img/9cf1bf71440583e497998c584e7bc225_205.png)

![](img/9cf1bf71440583e497998c584e7bc225_206.png)

![](img/9cf1bf71440583e497998c584e7bc225_207.png)

![](img/9cf1bf71440583e497998c584e7bc225_208.png)

Properly， like， say， I want 10 at third position in the list。 So all we need to do is create a node。

 store the value 10 in the data part。

![](img/9cf1bf71440583e497998c584e7bc225_210.png)

![](img/9cf1bf71440583e497998c584e7bc225_211.png)

Something like this。 Let's say we get the node 10 at address 310。

 So we will adjust the address field in the second node to 。

2 and this node with address 310 and this node will 。2 the node with value 4。 Now to insert also。

 we will have to traverse the list and go to that particular position。 And so this will be。



![](img/9cf1bf71440583e497998c584e7bc225_213.png)

![](img/9cf1bf71440583e497998c584e7bc225_214.png)

![](img/9cf1bf71440583e497998c584e7bc225_215.png)

![](img/9cf1bf71440583e497998c584e7bc225_216.png)

Big O of n again in terms of time complexity， the only thing is that the insertion will be a simple operation。

 we will not have to do all the shifts， as we had to do in an array to insert something in between we had to shift all the elements by one position towards higher indices。

 Similarlyly to delete something from this list will also be O N。

 so we can see some good things about linked list， there is no extra use of memory in the sense that some memory is unused。

 we are using some extra memory。 we are using some extra memory to store the addresses。

 but we have the benefit that we create node as and when we want and we can also free the notes as and when we want we do not have to guess the size of the list beforehand like in the case of arrays。



![](img/9cf1bf71440583e497998c584e7bc225_218.png)

![](img/9cf1bf71440583e497998c584e7bc225_219.png)

![](img/9cf1bf71440583e497998c584e7bc225_220.png)

![](img/9cf1bf71440583e497998c584e7bc225_221.png)

![](img/9cf1bf71440583e497998c584e7bc225_222.png)

![](img/9cf1bf71440583e497998c584e7bc225_223.png)

![](img/9cf1bf71440583e497998c584e7bc225_224.png)

![](img/9cf1bf71440583e497998c584e7bc225_225.png)

Now we will discuss all the operations on linked list and the cost of these operations as well as comparison with arrays in our next lessons。

 we will also be implementing linked list in C or C++ so this is all for a basic introduction to linked list thanks for watching。



![](img/9cf1bf71440583e497998c584e7bc225_227.png)

![](img/9cf1bf71440583e497998c584e7bc225_228.png)