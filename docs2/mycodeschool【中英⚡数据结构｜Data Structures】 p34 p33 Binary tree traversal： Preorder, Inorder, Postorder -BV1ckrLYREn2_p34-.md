# mycodeschool【中英⚡数据结构｜Data Structures】 p34 p33 Binary tree traversal： Preorder, Inorder, Postorder -BV1ckrLYREn2_p34-

In our previous lesson we talked about level order traver cell of binary tree which is basically breadth first traver cell now in this lesson we are going to discuss these three depth first algorithms preorder in order and post order I have drawn a binary tree here data type filled in the notes is character now as we had discussed in earlier lessons in depth first traver cell of binary tree if we go in one direction then we visit all the nodes in that direction or in other words we visit the complete subre in that direction and then only we go in other direction。



![](img/def8e156c486e964b5fec4df027d80a5_1.png)

![](img/def8e156c486e964b5fec4df027d80a5_2.png)

![](img/def8e156c486e964b5fec4df027d80a5_3.png)

![](img/def8e156c486e964b5fec4df027d80a5_4.png)

![](img/def8e156c486e964b5fec4df027d80a5_5.png)

In this example tree that I have drawn here， if I'm at root and Im going left。

 then I'll visit all the nodes in this left subree and then only I can go right and once again when Ill go right I'll visit all the node in this right subree。



![](img/def8e156c486e964b5fec4df027d80a5_7.png)

![](img/def8e156c486e964b5fec4df027d80a5_8.png)

![](img/def8e156c486e964b5fec4df027d80a5_9.png)

If you can see in this approach we are reducing the problem in a selfsim or recursive manner。

 we can say that in total visiting all the nodes in the tree is visiting the root node。

 visiting the left subre and visiting the right subre。



![](img/def8e156c486e964b5fec4df027d80a5_11.png)

![](img/def8e156c486e964b5fec4df027d80a5_12.png)

![](img/def8e156c486e964b5fec4df027d80a5_13.png)

Remember by visiting a node we mean reading or processing the data and Act node and by visiting a subre we mean visiting all the nodes in the subre in depth first strategy。

 relative order of visiting the left subre right subre and the route can be different。



![](img/def8e156c486e964b5fec4df027d80a5_15.png)

![](img/def8e156c486e964b5fec4df027d80a5_16.png)

![](img/def8e156c486e964b5fec4df027d80a5_17.png)

![](img/def8e156c486e964b5fec4df027d80a5_18.png)

For example we can first visit the right subre then the root and then the left subre or we can first visit the root and then the left subre and then the right subre。

 conventionally left subre is always visited before right subre with this constraint we will have three permutations。



![](img/def8e156c486e964b5fec4df027d80a5_20.png)

![](img/def8e156c486e964b5fec4df027d80a5_21.png)

![](img/def8e156c486e964b5fec4df027d80a5_22.png)

We can first visit the root and then the left sub3 and then the right subre and such a traversal will be called preorder traversal or we can first visit the left subre。

 then the root and then the right subre and such a traversal will be called inor traversal and we can also go left right and then root and such a traversal will be called post order traversal。



![](img/def8e156c486e964b5fec4df027d80a5_24.png)

![](img/def8e156c486e964b5fec4df027d80a5_25.png)

![](img/def8e156c486e964b5fec4df027d80a5_26.png)

![](img/def8e156c486e964b5fec4df027d80a5_27.png)

Left and right subt will be visited recursively in same manner as the original tree。 So in preorder。

 once again for the subt， we will go root left and then right in in order will keep going left。

 root and then right。 The actual implementation of these als is really easy and intuitive。

 Let's first see code for preorder traveral。

![](img/def8e156c486e964b5fec4df027d80a5_29.png)

![](img/def8e156c486e964b5fec4df027d80a5_30.png)

![](img/def8e156c486e964b5fec4df027d80a5_31.png)

![](img/def8e156c486e964b5fec4df027d80a5_32.png)

I've first written the algoicum in words here。In preau rev we first need to visit the root then the left subre and then the right subree Now I want to write a function that should take pointer or reference to root node as argument and print data in all the nodes in preorder let's say visiting a node for us is printing the data in that node in C or c++ my method signature will look something like this。



![](img/def8e156c486e964b5fec4df027d80a5_34.png)

![](img/def8e156c486e964b5fec4df027d80a5_35.png)

This function will take address of the root node as argument argument type is pointer to node。



![](img/def8e156c486e964b5fec4df027d80a5_37.png)

I'll define node as a structure with three fields like this。



![](img/def8e156c486e964b5fec4df027d80a5_39.png)

Data type in this definition is character and there are two fields to store the addresses of left and right children。

 Now in preorder function， I'll first visit or print the data in root node。

 and now I'll make a recursive call to visit the left subre。



![](img/def8e156c486e964b5fec4df027d80a5_41.png)

![](img/def8e156c486e964b5fec4df027d80a5_42.png)

![](img/def8e156c486e964b5fec4df027d80a5_43.png)

I have made a recursive call here and to this call I' am passing address of the left child of my current route because left child will be the root of left subre。



![](img/def8e156c486e964b5fec4df027d80a5_45.png)

![](img/def8e156c486e964b5fec4df027d80a5_46.png)

![](img/def8e156c486e964b5fec4df027d80a5_47.png)

And I'll have another call like this to visit the right subre。

 there is one more thing that we need to add in this function and we will be done。



![](img/def8e156c486e964b5fec4df027d80a5_49.png)

We cannot go into recursion infinitely； we need to have a base condition where we should exit if a tree or sub tree is empty or in other words for any call if root is null。



![](img/def8e156c486e964b5fec4df027d80a5_51.png)

![](img/def8e156c486e964b5fec4df027d80a5_52.png)

![](img/def8e156c486e964b5fec4df027d80a5_53.png)

We can return or exit Now with this much of code， Im done with my preorder function。



![](img/def8e156c486e964b5fec4df027d80a5_55.png)

This will work fine in C or C++。Actually in C， make sure you writestruct space node instead of writing just node。

 rest of the things are fine。

![](img/def8e156c486e964b5fec4df027d80a5_57.png)

It will be good to visualize this recursion， so lets now quickly see how this preorder function will work if this example tree that I am showing in right here is passed to it。

 I'll redraw this tree and show it like this here I am depicting node as a structure with three fields let's say the leftmost cell here is to store the address of left childild the cell in middle is to store the data and the rightmost cell is to store the address of right child。



![](img/def8e156c486e964b5fec4df027d80a5_59.png)

![](img/def8e156c486e964b5fec4df027d80a5_60.png)

![](img/def8e156c486e964b5fec4df027d80a5_61.png)

![](img/def8e156c486e964b5fec4df027d80a5_62.png)

![](img/def8e156c486e964b5fec4df027d80a5_63.png)

Now let's assume some addresses for these nodes and let's say the root node is at address 200。

And I'll assume some。Random addresses for other nodes as well。

 and now I can fill in left and right fields for each node。



![](img/def8e156c486e964b5fec4df027d80a5_65.png)

![](img/def8e156c486e964b5fec4df027d80a5_66.png)

And as we know， the identity of tree that we always keep with us is reference or address of the root node。

 this is what we pass to all the functions。

![](img/def8e156c486e964b5fec4df027d80a5_68.png)

![](img/def8e156c486e964b5fec4df027d80a5_69.png)

In our implementation， we often use a variable of type pointer to node named root to store the address of root node。



![](img/def8e156c486e964b5fec4df027d80a5_71.png)

![](img/def8e156c486e964b5fec4df027d80a5_72.png)

We can name this variable anything， we can name this variable root or we can name this variable root PTR。

 but this is just a pointer this particular block that Im showing here is for pointer to node and all these rectangles with three cells are nodes。



![](img/def8e156c486e964b5fec4df027d80a5_74.png)

![](img/def8e156c486e964b5fec4df027d80a5_75.png)

This is how things are organized in memory Now for this tree。

 let's say we are making a call to this preorder function。

 I'll make a call to preorder passing it address 200。



![](img/def8e156c486e964b5fec4df027d80a5_77.png)

For this call root is not null so we will not return at first line in this function。

 we will go ahead and print the data in this node at address 200。

 Ill write output for all print statements here。

![](img/def8e156c486e964b5fec4df027d80a5_79.png)

And now this function will make a recursive call， execution of this particular function call will pause。

 it will resume only after this recursive call preorder 150 finishes。

 this second call is to visit this left subre， this call preorder 150 is to visit this left subree。



![](img/def8e156c486e964b5fec4df027d80a5_81.png)

![](img/def8e156c486e964b5fec4df027d80a5_82.png)

![](img/def8e156c486e964b5fec4df027d80a5_83.png)

Address of the left child of Noda 200 is 150。

![](img/def8e156c486e964b5fec4df027d80a5_85.png)

Once again for this call， root is not null， so we will go ahead and print the data data in node at 150 is D and now once again there will be a recursive call。



![](img/def8e156c486e964b5fec4df027d80a5_87.png)

![](img/def8e156c486e964b5fec4df027d80a5_88.png)

With this call preorder 400， we are saying that we are going to visit this sub3。

 Once again we will print the data and make another recursive call Now we have made a call to visit this particular subre with just one node for this call we will print the data and now for node at 250 address of left child is 0 or null we will make a call preorder 0 but for this call we will simply return because the address in this variable route will be null we have hit the base condition for our recursion。



![](img/def8e156c486e964b5fec4df027d80a5_90.png)

![](img/def8e156c486e964b5fec4df027d80a5_91.png)

![](img/def8e156c486e964b5fec4df027d80a5_92.png)

![](img/def8e156c486e964b5fec4df027d80a5_93.png)

![](img/def8e156c486e964b5fec4df027d80a5_94.png)

![](img/def8e156c486e964b5fec4df027d80a5_95.png)

Call to preorder 0 will finish and preorder 250 will resume now in this particular function call we make another call for right sub3 for node at 250 even the right child is null we will have another recursive call passing address0 but this once again will simply return and now call to preorder 250 will finish and call to preorder 400 will resume now in call to preorder 400 we will make another recursive call to preorder 180 with this call preorder 180 we are visiting this particular subre with just one node for this call first we will print the data and then we will make a recursive call to preorder 0 now preorder 0 we simply return and then we will have another call to preorder 0 for right child of 180 the recursion will go on like this there is one thing that I want to talk about here that's happening in this whole process。



![](img/def8e156c486e964b5fec4df027d80a5_97.png)

![](img/def8e156c486e964b5fec4df027d80a5_98.png)

![](img/def8e156c486e964b5fec4df027d80a5_99.png)

![](img/def8e156c486e964b5fec4df027d80a5_100.png)

![](img/def8e156c486e964b5fec4df027d80a5_101.png)

![](img/def8e156c486e964b5fec4df027d80a5_102.png)

![](img/def8e156c486e964b5fec4df027d80a5_103.png)

![](img/def8e156c486e964b5fec4df027d80a5_104.png)

![](img/def8e156c486e964b5fec4df027d80a5_105.png)

![](img/def8e156c486e964b5fec4df027d80a5_106.png)

![](img/def8e156c486e964b5fec4df027d80a5_107.png)

Even though we are not using any extra memory explicitly in our function， because of the recursion。

 we are growing the function called stack。

![](img/def8e156c486e964b5fec4df027d80a5_109.png)

![](img/def8e156c486e964b5fec4df027d80a5_110.png)

We have discussed memory management a number of times in our earlier lessons。

 you can check description of this video for a link to one of those lessons as we know for each function call we allocate some amount of memory in what we call stack section of applications memory and this allocated memory is reclaimed when the function call finishes。



![](img/def8e156c486e964b5fec4df027d80a5_112.png)

![](img/def8e156c486e964b5fec4df027d80a5_113.png)

![](img/def8e156c486e964b5fec4df027d80a5_114.png)

At this stage of execution of my recursion for this example。

 my call stack will look something like this。 I'm writing P as shortcut for preorder because I'm short of space here。

 let's say we made a call to preorder passing it address 200 from main function。

 main function will be at bottom of stack。 At any time。

 only the call at top of stack will be executing and all other calls will be paused call stack keeps growing and shrinking during execution of a program because memory is allocated for a new function call and it's reclaimed when a function call finishes。

 So even though we are not using any extra memory explicitly here。

 we are using memory implicitly in the call stack So space complexity。

 which is measure off rate of growth of extra memory used with input will depend upon the maximum amount of extra memory used in the call stack。

 I'll talk about space complexity once more later。 For now。

 let's come back to this recursion that I was executing call to this preorder 0 will finish and。



![](img/def8e156c486e964b5fec4df027d80a5_116.png)

![](img/def8e156c486e964b5fec4df027d80a5_117.png)

![](img/def8e156c486e964b5fec4df027d80a5_118.png)

![](img/def8e156c486e964b5fec4df027d80a5_119.png)

![](img/def8e156c486e964b5fec4df027d80a5_120.png)

![](img/def8e156c486e964b5fec4df027d80a5_121.png)

![](img/def8e156c486e964b5fec4df027d80a5_122.png)

![](img/def8e156c486e964b5fec4df027d80a5_123.png)

![](img/def8e156c486e964b5fec4df027d80a5_124.png)

![](img/def8e156c486e964b5fec4df027d80a5_125.png)

![](img/def8e156c486e964b5fec4df027d80a5_126.png)

Order 180 will resume memory allocated for execution of pre order 0 will be reclaimed now for pre order 180 both recursive calls have finished so this guy will also finish。

Even for preorder 400 both calls have finished， so preorder 150 will resume now this guy will make a recursive call to preorder function passing it address 450 address of its right child。



![](img/def8e156c486e964b5fec4df027d80a5_128.png)

![](img/def8e156c486e964b5fec4df027d80a5_129.png)

![](img/def8e156c486e964b5fec4df027d80a5_130.png)

Memory in the stack will be allocated for execution of3 order 450。



![](img/def8e156c486e964b5fec4df027d80a5_132.png)

Now in this call we will first print the data and then we will make two recursive calls to preorder passing address0 each time because for this node at 450 both children are null。

 Both calls will simply return and then preorder 450 will finish and now preorder 150 will also be done if you can see the call stack will grow only till we reach a leaf node a node with no children and then it will start shrinking again。

 maximum growth of calls stacked due to this recursion will depend upon maximum depth or height of the tree we can say that extra space used will be proportional to height of the tree。



![](img/def8e156c486e964b5fec4df027d80a5_134.png)

![](img/def8e156c486e964b5fec4df027d80a5_135.png)

![](img/def8e156c486e964b5fec4df027d80a5_136.png)

![](img/def8e156c486e964b5fec4df027d80a5_137.png)

![](img/def8e156c486e964b5fec4df027d80a5_138.png)

![](img/def8e156c486e964b5fec4df027d80a5_139.png)

Or in other words， space complexity of this algorithm is big O of edge where edge is height of the tree。



![](img/def8e156c486e964b5fec4df027d80a5_141.png)

![](img/def8e156c486e964b5fec4df027d80a5_142.png)

Okay， coming back to the recursion， we are done with preorder 150 so preorder 200 will resume and now we will make a call to visit this particular subre。



![](img/def8e156c486e964b5fec4df027d80a5_144.png)

![](img/def8e156c486e964b5fec4df027d80a5_145.png)

In this call， we will print J。And then we will make a call passing address 60。

 So now we are visiting this particular subre here we will first print G。



![](img/def8e156c486e964b5fec4df027d80a5_147.png)

![](img/def8e156c486e964b5fec4df027d80a5_148.png)

And then this guy will make a call to preorder 0， which will simply return and then there will be another call to preorder 500 here we will print I。



![](img/def8e156c486e964b5fec4df027d80a5_150.png)

![](img/def8e156c486e964b5fec4df027d80a5_151.png)

And then we will make two recursive calls passing address0 every time because node at 500 is a leaf node with no children after this guy finishes preorder 60 will resume now this guy will also finish and pre-order 350 will resume and now we will have a call to preorder 700 which once again is a leaf node so k which is data in this node will be printed and then we will make two calls passing address zero which will simply return now at this stage all these calls can finish we are done visiting all the nodes。

 finally we will return back to the call of preorder 200 which probably would be the main function。



![](img/def8e156c486e964b5fec4df027d80a5_153.png)

![](img/def8e156c486e964b5fec4df027d80a5_154.png)

![](img/def8e156c486e964b5fec4df027d80a5_155.png)

![](img/def8e156c486e964b5fec4df027d80a5_156.png)

![](img/def8e156c486e964b5fec4df027d80a5_157.png)

![](img/def8e156c486e964b5fec4df027d80a5_158.png)

So this is preorder traveral for you， I hope you got how this regression works code for in order and post order will be very similar in in order traveral my base case will be the same so I'll say if root is null then return or exit。

 if root is not null I first need to visit the left subre。



![](img/def8e156c486e964b5fec4df027d80a5_160.png)

![](img/def8e156c486e964b5fec4df027d80a5_161.png)

![](img/def8e156c486e964b5fec4df027d80a5_162.png)

![](img/def8e156c486e964b5fec4df027d80a5_163.png)

I am visiting the left sub3 with this recursive call， then I need to visit the root。

 so now I am writing the s of statement to print the data and now I can visit the right sub3。

 so this second recursive call。

![](img/def8e156c486e964b5fec4df027d80a5_165.png)

![](img/def8e156c486e964b5fec4df027d80a5_166.png)

![](img/def8e156c486e964b5fec4df027d80a5_167.png)

And this is my in order function。In order traversal of this example tree that I have drawn here will be this this particular binary tree is actually also a binary search tree and in order traversal of a binary search tree would give us elements in the tree in sorted order。



![](img/def8e156c486e964b5fec4df027d80a5_169.png)

![](img/def8e156c486e964b5fec4df027d80a5_170.png)

![](img/def8e156c486e964b5fec4df027d80a5_171.png)

Okay lets now write code for a post order for this function once again the base case will be the same。

 so I'll say if root is null， return or exit， if root is not null。

 I first need to visit the left subre so I have made this recursive call then the right sub tree so I'll have this another recursive call and now I can visit the root node。



![](img/def8e156c486e964b5fec4df027d80a5_173.png)

![](img/def8e156c486e964b5fec4df027d80a5_174.png)

![](img/def8e156c486e964b5fec4df027d80a5_175.png)

![](img/def8e156c486e964b5fec4df027d80a5_176.png)

Post order reversal for this example tree will be this。

So this is pre order in order and post order for you。

 you can check the description of this video for a link to all the source code。



![](img/def8e156c486e964b5fec4df027d80a5_178.png)

![](img/def8e156c486e964b5fec4df027d80a5_179.png)

Let's now quickly talk about time and space complexity of these algorithms。



![](img/def8e156c486e964b5fec4df027d80a5_181.png)

Time complexity of all these three algorithms is big O of n。

 If you could see then there was one function call corresponding to each node where we were actually visiting that node where we were actually printing the data in that node。

 so running time should actually be proportional to number of nodes。

 there is a better formal and mathematical way of proving that time complexity of these algorithms is big O of n。

 you can check the description of this video for linked to that space complexity。

 as we had discussed earlier， will be big O of edge where edge is height of the tree height of a tree in worst case will be n minus-1。

 So in worst case space complexity of these algorithms。



![](img/def8e156c486e964b5fec4df027d80a5_183.png)

![](img/def8e156c486e964b5fec4df027d80a5_184.png)

![](img/def8e156c486e964b5fec4df027d80a5_185.png)

Can be big O of n in best or average case height of a3 will be big O of log n to the base2。

 so we can say that in best or average case space complexity will be big O of log n。

 I'll stop here now in coming lessons we will solve some problems on binary 3 Thanks for watching。



![](img/def8e156c486e964b5fec4df027d80a5_187.png)

![](img/def8e156c486e964b5fec4df027d80a5_188.png)

![](img/def8e156c486e964b5fec4df027d80a5_189.png)

![](img/def8e156c486e964b5fec4df027d80a5_190.png)