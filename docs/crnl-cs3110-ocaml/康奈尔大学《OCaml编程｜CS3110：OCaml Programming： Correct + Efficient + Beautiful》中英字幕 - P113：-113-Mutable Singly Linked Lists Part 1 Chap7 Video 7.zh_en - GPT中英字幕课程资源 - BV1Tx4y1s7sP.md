# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P113：-113-Mutable Singly Linked Lists Part 1 Chap7 Video 7.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's implement mutable Sly linked lists in OCL。You'll recall from implementing linked lists in Java that a linked list typically has nodes。

 those nodes store values， and each node has a pointer to the next node in the list。

 Let's create an Ocal representation type for nodes。We'll pause here。

An alpha node is a node that's going to contain a value of type alpha。

So I've created a record for that with a field named value。 That's what stores the value at the node。

 I've also created a field named next。 That's going to be the pointer to the next node in the list。

Now I want to be able to change what the next node in the list is， I want to be able to mutate it。😡。

One way of doing that would be to make the next field mutable。Now， when I want to。

 I can update what the next node is in the list。Of course。

 another way of doing that would have been to use a ref instead。

I could instead make next an alpha node ref and mutate that ref。

We know now that refs and fields are really the same thing since you can implement refs in terms of mutable fields。

 so I'm going to stick with the mutable field implementation here to keep the types a little bit simpler。

Now， what if we're at the last node in a list？There's no other node after that。The problem is。

 our next field is going to force us to put another node after it and another node and another node will never be able to end the list。

We need something like no， in Java to do that。OCel， as you know， has options。

 which gives us a principled way of representing values that might be nothing。

So I will make the next field an option。Read it from right to left。

 this is an optional node containing an alpha。Either it's nothing。

 which case we're at the end of the list。🎼Or it's something。

 So we're able to follow to the next node in the list。

 I should document some of this with an abstraction function。Good， now。

 when someone one comes along to read my code later， they'll understand what I meant with this type。

When implementing a linked list， it's also typical to have a separate type for representing the list itself as opposed to just a node and for that separate type to have a pointer to the first node of the list and maybe contain some additional information as well like the size of the list。

 Let's create an Ocal type for linked lists。So an alpha M list is going to be a mutable singly linked list。

 which contains values of type alpha。I've created it as a record type。

 that record has a field named first， which is the pointer to the first note in the list。Of course。

 if I want the first node in the list so also be mutable so that I can change what the first node of this list is。

 maybe by prepending a node to the list， I'm going to need for that field to be mutable。

And if I want the list to possibly be empty， such that there are no nodes in it at all。

 I'm going to need to make that first field optional as well。😡，Finally。

 I ought to document an abstraction function for this representation type。

Let's write some code to create lists。First， let's create Singleton lists where we just pass in a value and create a list that contains only that value。

So I've written two functions here， Singleton creates an M list whose first field is initialized to some new node。

😡。

![](img/54090c16c968d8319b75003f8f27c2b3_1.png)

![](img/54090c16c968d8319b75003f8f27c2b3_2.png)

And that new node， I have factored out a function to help create。

 It creates a node that points to no other nodes and just contains the value fee。



![](img/54090c16c968d8319b75003f8f27c2b3_4.png)

![](img/54090c16c968d8319b75003f8f27c2b3_5.png)

I should definitely write some documentation comments for each of these。



![](img/54090c16c968d8319b75003f8f27c2b3_7.png)

Let's try using these functions to create a list。Now I have a new Sly linked list。

 itss first node contains the value 31 Z and does not have any links to other notes。

