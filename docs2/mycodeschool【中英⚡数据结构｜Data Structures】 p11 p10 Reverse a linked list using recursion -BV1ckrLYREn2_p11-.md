# mycodeschool【中英⚡数据结构｜Data Structures】 p11 p10 Reverse a linked list using recursion -BV1ckrLYREn2_p11-

![](img/93d740a0d43cd728328ff624c79c69e9_0.png)

In our previous lesson we saw how we can traverse a linked list using recursion we wrote code to print the elements of linked list in forward as well as reverse order using recursion we did not actually reverse the list we just printed the elements in reverse order now in this lesson we will reverse a linked list using recursion this is yet another famous programming interview question so if we have an input list like this。

 we have a linked list of integers here。

![](img/93d740a0d43cd728328ff624c79c69e9_2.png)

![](img/93d740a0d43cd728328ff624c79c69e9_3.png)

We have four nodes in the linked list each rectangular block here with two partitions is a node first field is to store the data and another to store the address of the next node。

 the second field stores the address of the next node and of course we will have one variable to store the address of the first node or head node we name that variable head。

 we may name it anything I have named it head so this is our input list and after reversal our output should be like this。



![](img/93d740a0d43cd728328ff624c79c69e9_5.png)

This variable head should store the address of the last node in the original list。

 the last node in the original list was at address 250 and we will go like from 250 to 150150 to 200。

 200200 and 1002 null null is nothing but address 0。



![](img/93d740a0d43cd728328ff624c79c69e9_7.png)

![](img/93d740a0d43cd728328ff624c79c69e9_8.png)

![](img/93d740a0d43cd728328ff624c79c69e9_9.png)

We have already seen how we can reverse a linked list using iterative method in one of our previous lessons。

 let us now see how we can solve this problem using recursion。



![](img/93d740a0d43cd728328ff624c79c69e9_11.png)

In our solution we must reverse the list by adjusting the links by reversing the links not by moving around data or something。

 so let us first understand the logic that we can use in our recursive approach if you remember from our previous lesson where we had used recursion to print the list backward print elements in reverse order then recursion gives us a way to traverse the list backward in our C c++ program programmatically node will be a structure like this so let's first look at the function from the previous lesson the recursive function that was used to print the list backward to this function we pass the address of a node initially we passed the address of the head node。



![](img/93d740a0d43cd728328ff624c79c69e9_13.png)

![](img/93d740a0d43cd728328ff624c79c69e9_14.png)

![](img/93d740a0d43cd728328ff624c79c69e9_15.png)

![](img/93d740a0d43cd728328ff624c79c69e9_16.png)

And we have this exit condition if the address passed is null then we simply return else we make a recursive call and pass the address of the next node。

 so main method will typically call reverse print passing it the address of the head node and this guy will first make a recursive call and then when this recursive call finishes then only it will print so I'm writing Rps shortcut for reverse print so the recursion will go on like this and when it reaches this particular call when argument is null it will return so this call will finish and again the control will come to this call with。



![](img/93d740a0d43cd728328ff624c79c69e9_18.png)

![](img/93d740a0d43cd728328ff624c79c69e9_19.png)

![](img/93d740a0d43cd728328ff624c79c69e9_20.png)

![](img/93d740a0d43cd728328ff624c79c69e9_21.png)

![](img/93d740a0d43cd728328ff624c79c69e9_22.png)

![](img/93d740a0d43cd728328ff624c79c69e9_23.png)

AndAddss 250 as argument。 and now we are printing the value。



![](img/93d740a0d43cd728328ff624c79c69e9_25.png)

Of the node at address 250， which will be4。And then this graph finishes and then we go ahead and print5 and similarly we then go on to print6 and2。



![](img/93d740a0d43cd728328ff624c79c69e9_27.png)

So recursion kind of gives us a way to first traverse the list in the forward direction and then traverse the list in the backward direction so let us now see how we can implement reverse function using recursion let's say for the sake of simplicity in implementation that head is a global variable so it is accessible to all the functions now we will implement a function named reverse that will take the address of a node as argument initially we will pass address of the head node to this function Now I want to do something like this in my recursion I want to go on till the end I want to go on making a recursive call till I reach the last node for the last node the link part will be null so this is my exit condition from recursion this exit condition is what will stop us from going on infinitely in a recursion and what I'm doing here is something very simple as soon as I'm。



![](img/93d740a0d43cd728328ff624c79c69e9_29.png)

![](img/93d740a0d43cd728328ff624c79c69e9_30.png)

Reaching the last node， I'm modifying the head pointer to make it point to this guy。



![](img/93d740a0d43cd728328ff624c79c69e9_32.png)

So the recursion will work like this from the main method we will call the reverse function passing it the address of the head node address 00 we will come and check this condition if P dot next is equal to null no it is equal to 200 for the node at address 00 so this recursion will go on till we reach this call call to reverse passing it address 250 and now we will come down and now we have come to this exit condition and now head will be set as P and the list will look like this and now reverse 250 the call to reverse 250 will finish and we will come back to reverse 150。



![](img/93d740a0d43cd728328ff624c79c69e9_34.png)

![](img/93d740a0d43cd728328ff624c79c69e9_35.png)

![](img/93d740a0d43cd728328ff624c79c69e9_36.png)

![](img/93d740a0d43cd728328ff624c79c69e9_37.png)

There is no statement here after。This records if called reverse function if there were some statements here then they would have executed now for reverse 150 after we would have come from reverse 250 and that's how we actually traverse the list in a reverse order if you see when reverse 250 has finished the node till 250 is already reversed because head is pointing to this node and the link part of this node node is set as null so till 250 we are already reversed now when we come to 150 we can make sure the list is reversed till 150 when we finish the execution of reverse 150 to do to do that we can write statement like this we will have to do two things we will have to cut this node and make this guy point to this guy so we will build this link。



![](img/93d740a0d43cd728328ff624c79c69e9_39.png)

![](img/93d740a0d43cd728328ff624c79c69e9_40.png)

![](img/93d740a0d43cd728328ff624c79c69e9_41.png)

![](img/93d740a0d43cd728328ff624c79c69e9_42.png)

![](img/93d740a0d43cd728328ff624c79c69e9_43.png)

![](img/93d740a0d43cd728328ff624c79c69e9_44.png)

And we would have to cut this link and make this guy point to null。



![](img/93d740a0d43cd728328ff624c79c69e9_46.png)

And that's how node till address 150 will be reversed after we finish this call。



![](img/93d740a0d43cd728328ff624c79c69e9_48.png)

So I've written these three lines in my function that will execute after the recursive call。

 so they will execute when the recursion is folding up。

And we are traversing the list in the backward direction so when we are executing reverse 150 and we have come back to it after recursion we are at this particular line so p would be 150 and would be p dot next so Q would be 250 so this guy's P P and this guy is  Q and we are saying that set  Q dot next is equal to p so we will set this particular field as 100。



![](img/93d740a0d43cd728328ff624c79c69e9_50.png)

![](img/93d740a0d43cd728328ff624c79c69e9_51.png)

![](img/93d740a0d43cd728328ff624c79c69e9_52.png)

![](img/93d740a0d43cd728328ff624c79c69e9_53.png)

So we are building this link。And cutting this link and now we are saying that set P dot next equal null so we are building this link making p dot next null and now this call to reverse 150 finishes and when this call has finished the list till 150 is reversed as you can see head is 250 so from 250 we will go to 150 and 150 from 150 we are going to null so till 150 we have a reversed list。



![](img/93d740a0d43cd728328ff624c79c69e9_55.png)

![](img/93d740a0d43cd728328ff624c79c69e9_56.png)

So this is how things will look like when the call to reverse 200 finishes till 200 we have a reversed list and once again we come to execution of reverse00 and this is how things will look like finally when reverse 00 will finish and we will return back to the main function we had seen in the previous lesson that how things will happen in the memory when recursion execute in recursion we save the state of execution of all the function calls in stack section of the memory in this function all we are doing is basically we are storing the addresses of node in a structure as we go forward in recursion and then we first work on the last node to make it part of the reverse list then we once again come back to the previous node and and we keep doing this watch the previous lesson for detailed explanation and simulation of how things will happen in the memory for recursion。



![](img/93d740a0d43cd728328ff624c79c69e9_58.png)

![](img/93d740a0d43cd728328ff624c79c69e9_59.png)

There are a couple of more things here。One thing is that instead of writing these two lines。



![](img/93d740a0d43cd728328ff624c79c69e9_61.png)

I could write one line for these two lines， I could say something like Parrow nextarrow next equal p and that would have meant the same except that this statement is more obfuscated。



![](img/93d740a0d43cd728328ff624c79c69e9_63.png)

And there is one more thing we have assumed that head is a global variable。

 what if head is not a global variable， this reverse function will have to return the address of the modified head I leave that as an exercise for you to do so this was reversing a linked list using recursion。



![](img/93d740a0d43cd728328ff624c79c69e9_65.png)

Thanks for watching。