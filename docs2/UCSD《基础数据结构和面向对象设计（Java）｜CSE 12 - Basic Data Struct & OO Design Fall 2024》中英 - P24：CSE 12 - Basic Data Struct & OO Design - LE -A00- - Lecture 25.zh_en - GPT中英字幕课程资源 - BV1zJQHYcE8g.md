# UCSD《基础数据结构和面向对象设计（Java）｜CSE 12 - Basic Data Struct & OO Design Fall 2024》中英 - P24：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 25.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

![](img/6df09d858db3a9858b9784a20339d5fb_0.png)

， let's get started in here。 Sorry for the DNA。No嗯。Of of a sudden， it's week 9， right， So week9 here。

So today， we'll definitely finish binaryaries3。 And I think we are done with our quizzes。

 We are done with our quizzes。嗯。So there is no more quiz。 The only assessment。

 formal assessment will be the final exam， okay。Now， for this week， we'll finish B ST。

 and then we need to get started with sorting for P A 8， the last P A。

 it is due not this Thursday but the coming Monday。 so you have some extra time。嗯。Last time。

 we started binary search 3。And we finished find。 We finished build。

 The only thing we didn't finish we can't delete and traverse。Right。

 so that's what we'll be doing in here today。This note doesn't include these pages in here。

 So it should be from the old note。 The new note is only about sorting。嗯。

Are there any questions before we start？All right。So last time we talk about the definition of a B S T。

 right， So you have a tree structure。 Every left up tree is less than the， the， the root。

 Every right up tree is bigger than the root。 And this probably applies to every node in the tree。

And then we say how to insert something。 if found insert something into。Into a B， SD， normally。

 you would traverse from the top， traverse to the right spot， then do the insertion。 right。

 If you need to look for something， it's very similar as insert。

 you basically utilize the property of you only need to go through。

Either side or like one side of the， the sub。 right， So if you're looking for 10。

 you're gonna try to go to the left， go to the left， go to the left， go to the right。

 If you hit empty， that means it doesn't exist。If you assume the tree doesn't allow duplicates， okay。

What we want to do now is I want to think about how to delete something from。A B， S T， right。

 This part is a little bit tricky because when you try to remove something。 like， for example。

 if I remove the root， I want to delete 42， how am I supposed to take care of this， right。

 there are several situations， you have to watch out。

 in a situation where if you want to delete something And this node。

 you want to delete so happens to be a leaf node。What would you do if this is a node that has only one child or the node has two children。

What can you say about these situations， right？ So， for example， if I want to delete 35。

What can I do。If you want to delete a beef note。What should I do。Can I just remove it。

And they just say， okay，35， you gone。The tree is not a nice anymore。 It's not a complete tree。

 What that matter for B S T。It doesn't matter。 right， So in here， if you delete a leaf。

 it's pretty straightforward。Just get rid of it。 right， The。

 the tree may end up being pretty bad shaped， but it doesn't really matter。 Okay， so just delete。

Just remove。How do I remove a node from a tree。If I want to delete 35。Right。

 so you got to first kind of， if you think about it， iss， it's like you try to go from 42， right。

 you go down。 And then once you hit 35， if you know your parent information。

 like if the note has a parent property is pretty easy。

 But if the note doesn't have a parent property， you have to make sure you have access to the parent before you remove it。

 right， So you need to set the parent。呃。Correct， child information to be now。And， as how you。

 how this node is removed， if this object has no reference to it。

 then it will be deleted by Java in C I C 30，100。 when you take when you finish C S C 12。

 you may have the right。Cos in C， C doesn't take care of that part for you。 In other words， in。

 in job in C， you may say32 is an object。 and Ive set the the right child reference to be now。

 you can do the same thing in C， but this thing still lingers。New memory。

C doesn't delete this thing for you。 You have to delete it by yourself。

See give you this tool called delete。Or free that would allow you to remove a certain amount of memory from the he。

 So you have to do that by yourself。 that's kind of some of the things you have to adjust。

Joba is nice to take care of the memory management， but C， C plus plus doesn't。

AndSo pay attention to that。Now， if I say， I want to remove a note that。Has exactly one child。

 like 12。I want to delete 12。What can I do。有。呃，就是。Cut this thing and link 6 to be with 32。

Will this always work？If you think about， you have a note summer in the tree。It only has one child。

And this trial may be the parent of some。A subre， right， So this is the thing I want to delete。

This is the parent。This is X， for example。If I want to， if this is why parent is why this is the。O。

Basically， our idea to say， you want to delete this node X。We want to do this。

 We want to convert it into why。Zi。Something like this， right， That's what I want to do。

 If I want to cut off X。Can you talk to your neighbor a little bit。Why this one would work。

I would just attach my child， my only child to。I parent and then delete this x。 Why would this work。

I want you to justify this move by thinking about the。Pperties of a B，ST。Can you have a discussion。

 why would this work？How can I just remove this x and attach C to it。

 and everything would work out just fine。This is the left tro。 so just to be more precise。

This is the left child of why。What can you say about the。Order， like which one is bigger。

 Which one is smallerer。Kind of thing。How can I justify it。I don't know if the clicker would work。

てまし。Can someone justify this， Why would this work。If this act is the left child of Y， similarly。

 you can think about the other three situations。 Yeah， in the back。还有。Alright， so one thing， we say。

Since this， this area started at x is on the left side Y。 So everything in here is less than y。

Everything in here is the rest of I。 So I get rid of this thing， and I put Z in here。

So this thing is still less than why。 It is still less than y。

 And we didn't really move anything here。So this thing just copied in。

 So all the properties in here is never changed。Without， is that a good justification for that。

Alright， so， and you can think about what if x is the right child。 Y is the same idea。

 What if this child is the left child of x。 So there are three other situations you can try to justify。

 but you can just。Attaach the child。To parent。Okay。

 so you just attach the child directly to the parent。 That's not。To bad。And obviously。

 at this moment， if you have the parent information is's pretty easy。

 But if you don't have the parent information， you got to keep track of the parent of the node you want to delete。

 You also need to access the child of the node you want to delete。So。you just是 touch第。

You just let the live child Y to refer to the。 That's about it。In this example。Now。

 the tricky part is this thing。 I want to delete， for example。Dlete 32。

What should I do if want to delete 32。Think about this。 Okay， oh， I want to delete 42 of 40，56。

 Can someone tell me， how do I delete 32。What do I do when I delete a node with exactly two children。

With exactly two children。Think about this。How would I delete a note with exactly two children。

I want to make sure that I。I have the， So I have， have this X。 You may have a parent。

And have exactly two children。What should I do。有。Switch。Switch the child with a greater value。

So if I， I think you are getting somewhere in this example， if I want to D 32。What should I use。

To replace 32。35， so I want to swap 32 with 35。And then。And then keep deleting 30。2 over there。Right。

 that's what I want to have。In this example， why does this always work。

 So can it be any child that is bigger than 32。Can it be any child， Like， in other words。

 I'm looking at something on the right side。 Can I pick anything here and replace with X swap with x。

这，都。有问。Alright， so we say it must。 it can be a one of the， the child that is bigger than x， right。

 the it should be the smallest data in the tree that is bigger than X。

 the smallest data industry the tree， which if we are 32 iss 35。 But if I want to delete 42。

 It shouldn't be like anything to the right side， it can't be anything just to the right。

 I need to find this 48。Right， so 48， I'll swap it。What's going on here。So， I would swap 40。18 there。

 put 42 in here， and then。Recursively delete this node。 Why would this work though。

If I'm looking for the smallest。Data， that is bigger than x。One of the argument is。

 if you replace this thing。With x， like， for example， this is this is y。 you put y in here。

 You put x in here。Why would why would it always work。看。You have a discussion like， why would。

 why would this work with， like， would there be any violation of the tree property。

If I put wine in here， I would swap them。Right， so I put x over here。And Ill put Y over there， why。

Would this create any easier。有。OK。Alright， so I think the， the， the order， right。

 what can I say about everything in here， folks。Canness is always less than X。If you have a tree。

 this part must be less than x。 and this y is bigger than x。 So if I put y over there。

 this part is gonna be less than y。对。Now， how about the right side， right side。

 since Y is gonna be the smallest on the right side。

 Everything on the right side at this amount will be。Bigger than why。Will be bigger than mine。

Because why is the smart is O here， The only exception is this X， you keep。You have to remove this x。

Now， can you have a discussion， What situations do I have to deal with， Like， in other words。

 how can I find the smallest data in here in this rice sub tree that is。Just be bigger than x。

How do I find this， Why， Where is this， why。Once I go mean go。Right， so if I go right。

 I'll keep going to the left。Let me ask you， is so the idea is how to find this， why。Once you， like。

 for example， you say find y  for 42， you say you go to the right child and then keep going left。

I'm gonna hit this node。I， I do have a question， though， So if this is why。The question is。Must。

Why be a leaf。Can you are voting。Is it guarantee that this why as I'm looking for the。

The smallest data on the right subre， right， say go right and keep going to the left。

 Is this y guaranteed to be a leaf， Because I have to swap X and y and then delete X at this moment is y guaranteed to be a leaf node。

Let's take a look。Look at the vote。We disagree with each other quite a bit。 Can we have a discussion。

 please， is why guarantee to be a leaf。 What did you vote for。Have a talk with your neighbor。

 What do you do vote for。Did you say it must be a leaf。All right。So the answer is no。Right。

 why doesn't have to be a leaf。 Why doesn't have to be a leaf。For example， if you have。

 if have this node and say this is like。20。And then， I was 21。For example。Exces。嗯。

This is the rice opportunity of 7。 I'm on the D 7。 What is the smallest data。Its just this one。

This 20 is not that E。It's not the leaf。In other words， if you have the right， even if you say， oh。

 what if you have a live child。Like， for example， this is like 15。And then this is like a 16。

 something like this。If you look at it， what's the smallest data that is just be bigger than 7。

You go to the right， and then keep going left。15， this one may have a right child。

So why doesn't have to be。A leaf。Can why have two children。Can why have two children。No， it can't。

 right， Because if one has a left child， then you should keep going to the left。

So why is guaranteed to be either a leave， possibly a leaf or a node with exactly one child。

So you go back to the previous two examples， situations。 So in this example。

 what you're gonna see is if has two children， you swap it with。 we call this the successor。

You swap with successor。What is the successor。Of a node。

 it is simply the smallest node that is bigger than this node。

Or if you do in order traveral of the tree， you're gonna see this is the next data that got printed out。

 So you swap this data with this successor and then successfully delete the successor。系。

Any questions。有。Right， the successor of a node does not indicate like。Like in this delete。

 if you say I have a node that has one child is guaranteed to be like on the right side。

 the leftmost node。 But if， if you have， like， if you just say what is the successor of a node。

 there are several situations。 We're gonna look at it right now， fact Okay， so in the P A。

 you are supposed to find the successor of a node。 for example， if it who is the successor of。32。

 it is 35。 Who is the successor of 12。 It is 32。Right， so it's the next。Data in light。

 that is bigger than this value we are looking for。 So who is the successor of 35。42。

 Who is a successful 42。48。Right， the success 48 is 56，56， successors，60，60 has no successor。Now。

 how do I find the successor。Of a note。The successor， by definition。

 is the smallest data that is just。Bigger than the。The X， for example， who is the success of node X。

嗯。What are the situations。How do I find the successor of a node。有。Right。If right child exists。Then我。

There is the left most node。On the right subre， right。So the idea is this。

 if this X has a right child。Then you are looking for this note in here。 This is the successor。

If we had a right。Chd。Does that make sense。Is this guarantee to be a leaf。

 Can I say it's gonna be the。Leftmost leaf on the right side。It's not a leaf。

 This thing is the successor of this X。 If has a right child， it's not guaranteed to be a leaf。

 It's the leftmost node， the leftmost node。O。What if it doesn't。You has no right child。

So this x may have live child may have a right child。

 but if this x only has potentiallyity a live child or has no children at all。

 where is the successor of this act。有。So E5， this situation。Where is the successor of x？

Where's the successor packs。Is just this parent。 This parent is guaranteed to be。

The smallest data in the tree That is bigger than x。Is you guaranteed。Its guaranteed， right。

 because this parent is bigger than x because X is the left child of this parent。

And this parent may have some rice up tree。 And this。

Everything in the rice up is bigger than the parent。 So parent is bigger than this right。

 If theres any parent。Of this parent， theyre gonna be， for example， if how about this grandparent。

 if I have this node， can this node be the successor in here。

Can this note be the successor of this x。Is it possible。This note， be the successor of X。Why not。

This value is less than x， right， so it can't be bigger than x。 So this parent is bigger than x。

 but this value is less than x。 How about you， if， if， if it's right side。

Can this node be the successor of x。Why， why can't this not be the successive act。Because it's what。

biggerea than this parent。And this parent is bigger than X。

 So this thing is not the next thing in life。So parent。 So in other words， if this node。

X has a parent。 And if so happened to be the left child of the parent。

 Then the parent itself is the successor。 It's pretty straightforward。What if。You have this X。

It has a live child， potentially， and then has parent like this。

Can this parent be the successor of X。Why not。Why can't this current be the success of act。

It's less than X， So it can't be now。Can。This one be the successor of x。No， it's even smaller。

 It's getting even smaller。So if you keep going to the left， it's not gonna work。

 You can keep going until you see。This is the one。So if X is the left child sorry。

 if X is the right child of the parent， you keep going up until you go up until the parent is the left child of another node。

 And this Y is a successor。So that's how you find the successor of a node。

Because you have to keep going up until you see this kink structure。That's the successor。

And you can justify it， because。Everything in here is less than y。 And there's nothing。

That goes between in between this x and this Y。 So x is bigger than of them。Right。

 so x is the first value。 that is。嗯。Les than。Are there any questions。嗯。

How about So this is the successor， right？ so you can find the successor。

 Is it possible a note doesn't have a successor。When， when does a note have no successor。Yeah。Right。

 so when you keep going up， like you have no rice up tree。 You keep going up。

 but you can never see this kink structure。 Then there has no successor。 in other words。

 it's gonna be the largest data。In the tree， that would have nothing that is bigger than it。

 So that's only note that doesn't have a successor。all the other node would have a successor。

 Either it's on its rice up tree or it's going up。Only the largest data wouldn't have a successor。

Does it make sense。Right， so that's kind of how you delete and how to find the successor。No嗯。

Other things， let's look at。Other， the last part is called traveral of a。B， SD。

 when you are given the B， SD， you can try to traverse the tree。 We know we can use D F， S， B， F， S。

 We know how to do it。 There is also kind of a a standard way for you to traverse a binary tree is called the three order in order。

 traveral pre order and post order。New order goes like this。 New order means you。

 you take care of the left。And then the root。 and then the right。

You do this for every node in the tree。 for preorder， you do the root。And then you do the left。

Then you do the right。Post orders route is move to the very end。The in order traveral by default。

 would sort the tree。The preorder and post order they are that are basically the same thing。

 and their usage a lot of times is to compress a tree into some sort of data structure that you can transmit。

Normally， that's what you can do。 Okay， so can I ask folks to do the in order preorder and post order of this tree on the right。

 Can you try to do it。So if I do in order for words of this tree。

 what do I end up with If I do preor， if I do post order。What will be the answer。

So this part can be a little bit confusing to some of us because you are doing this recursively。

 It's not just like。The one node is youre applying the rule to every node in a tree。Okay。Right。

 so how， how about we do the in order traersal， right， in order means you want to take care of。

 So when youre sitting on a node， you start at the root。 when youre sitting on this node。

 you want to take care of everything on the left subre， and then the node is off。

 and then the right sub。That's what it does。 So you say youre signal 42。

 Let's take care of the live sub。 Now you're jumping to the sub。 Roy that 32。At 32， you say。

 let me take care of the live subre， which is this part。And then I'll take care of 32。

 then take care of the right side。 You jump over to 12。 first。 I want to take care of the left up。

And then 12， then rise sub。 Now you have， I have a left sub So for 6。

 I' try to take care of the left sub， Nothing in there。 Take care of myself。 That's when you visit。

 like， if you say， let me print out a note once it is the data。 So you print out 6。

I do not want you to be confused。 So let me write in here in order。

Is the first thing that I got printed out is 6。 And then you go back to a parent。 this is the root。

 which is 12。And then the right sub of 12， nothing。 Then you go back to your parent。

 the left sub of 32 is taken care of。 Then you print out 32。And then you take out of the rice option。

 which is just 35。Now， you go back to the parent of 32， which is 42。

You try to take care of the rice up tree。 The rice up tree。

 you will first take care of the left side of 56， which is 48。And then it goes back to its parent。

Then that's how it goes。 So in order， would print out all the data in order。Are we good。

And for the other two orders， is mostly just the。而。As a， as a preorder。For pre order。

 you will try to take care of the root first， then the left， then the right。

 So when you are sitting at 42， the first node you want to print out is 42。

And then you want to take care of the left side， then the right side。

 When you try to take care of the left side。 you are sitting at 32。 You print out 32。

 Then we try to take care of the left side of 32， and then the right side。

So the left side of 32 is 12。So when you are sitting at the subre rooted at 12。

 you print out 12 first， then the left， which is 6， then the right。

 you are done with the left side of 32。 Then the right side 32 is 35。Right， after the 35。

 is's gonna be what what's gonna be the。The next video。Is there 56？Right， so iss the。

 the right side of 42 is 56。And then the left side，48， and then 60。That's the preauder。

 preauder traversal of this tree。And post all there。Post order means you take care of the left。

 take care of the right， and then the root itself off， so。嗯。

You would try to take care of this left up tree， then rise up tree， and then 42。

 So is it guaranteed that 42 will be the last node in here。That we printed out。

Is it guaranteed 42 will be the last node that we print out。Yes， so42 will be here。Well。

 we don't have to do it。 But I mean， in the end， we can， we can print out。

 So we'll try to take her of the left side and then the right side， it is post。

Just the reverse of this thing。Is post just a reverseers or pre。이제。No我 not。Right。So。

Try to take care of the left side。 This is the right side。

 So if you try to take care of the left side， you're gonna try to take care of this left side first。

 and then the right side， then 32。 Now you come in here， the left side。Is 6。

 So we're gonna print out 6 first， okay。And then the right side in here is not， and then 12。Okay。

 so 6，12， and then 35。And then，32。And so this left side is now taken care of。 Now。

 we need to take care of the right side， the right side you see of 40。8ight。The left side of 56。

 the the right side of 56。And then 56， and then 42。So it's not just a reverse of pre， right。

 So opposed， remember， everything is recursive。嗯。Questions。And to see。

 some of our students may struggle with this because I've seen people doing office these hours。

 Are there any questions for。The traversals， pre order in order， close order。All right。

We have some exercises in here， but I do want to get started with sorting。 So we。

 we'll come back and do these exercises later。 They are not gone。 They're still there。 We just。

 I just want to get started with sorting because you need that for。For your PA， okay。So。嗯。

Sorting is is something that got forced into CSE 12。 I mean， some of them use data structures。

 but a lot of them， you just basic idea of sorting。 Okay。

 sorting is is a very useful technique that would facilitate computing， okay。So in this class。

 we're gonna learn a few sorting algorithms and。They may seem to be unrelated to data structures。

 Some of them are， right。 But if you think about it， I it is， you need our to store the data。

 So it's part of the data structure。 So what we will learn in this class is quick sort， merge sort。嗯。

Heap bubble insert selection， tree。Couning sort。 those are the sorting methods well learn， okay。嗯。

We will。Kind of look at some of the sorting algorithms today。 And then probably on Wednesday。

 well look at quick sort and merge sort。A little bit。So， for tree sort。

The the idea of tree sort is your given array is a less's sorted。Using a tree。

 So youre gonna basically peel the P， S T out of this。And then do an in order traveral of the P SD。

 That's how we sort it。Okay， in Java， it's like you build a tree set。

 You keep inserting this data into the tree set， and then you go through the tree set。

That would basically sort the the data。 Okay， so that's tree sort。 Can you。Try to do a tree sort。

Of this data set。B the B SD out of this。And P B， S the art of this。嗯。Let's see。

 I do not want to have duplicates。Here， you complicate things a little bit。 about 12。 make that a 12。

Put it do not disturb。 So can you change this data into 12 and then build up the。The B ST。

 build up the B ST。And then do I in order for of the B， ST。Build the BD out of these data。

Do in order forersal。I think in other showers， you know， it's gonna give you sorted data。 right。

 So in our test， in our final， yeah， not gonna say I'll do this tree sort。

 So you must first know how to build a tree。 right。 So if I give you some data。

And they build up the tree。 And I'll ask you， who is gonna be the right child of 12。Of does。

Does0 have a。Left child。 So something like that that you must be able to。Build a tree by ourselves。

 right， And then we say if I do a preder traersal， what's gonna be the last data that get printed it out。

 What's gonna be the third data that got printed out。 So you you must know all those details， right。

 You are not gonna be asked to say， hey， what's a sorted result of this area。You don't need tree to。

 to look at it。不适合法院所区。是吧。You're building and。So if you， if you allow duplicates。

 what's gonna happen is the node itself would also have a account。 So by default。

 everything is just one one count。 But if it there are  five toolss that got inserted。

 it just increase the account of that node。If you try to delete2， you just delete one copy of it。

That's what you do。Alright， are we good， So let's， let's try to build a tree。

What's gonna be the root of the tree。5。The first node the insert will be the root。 right， So。

 and then I insert 12。 Where is it gonna be 12。Right child of5。 How about one。Left child of5。

 about 0。Left 1，6。Leve child of 12， okay。3。Right child of1，2。Lefe child of three。喂。

That's how you try to insert it in this way。 And that's the tree。 If you do any order traersal。

 you end up with asorted order。Are we good。So we know how to build a B SD。 We can do this。 Now。

 what I'm curious about is a runtime， Right over all these sorting algorithms。

 tree sort is something we just learned。 What's the runtime of building up a tree like this in the worst case。

 scenario。That can we to a boat。 What is。The part， we are not looking at tree sort。

 We are looking at just building up the tree， the worst case。To build a tree。

Worst case to build a tree。Is the system showing that okay， it is， it is。 I mean， know。

I think out of the 50 votes we are getting。Only 10 people got it right for this one。

Can you have a discussion， please， What did you vote for。Was a run time。More likely than now。

 you and your neighbor are voting for the wrong answers。What， what is the answer that we got in here。

What is the answer？Have a discussion。 Okay， try to convince each other。A lot of us voting for A or B。

A lot of us voting for A or B。有不。Alright， so the answers。C， N square， right， The answer is n square。

 because if you end up with a tree like this。You have to constantly go from the root， right， to。

 to insert， it's like using the get method of aingulus。You keep getting something。

 You keep going back to the root， find the spot insert， go from the root insert。 And this part。

 if you have the the data that is sorted， you easily end up with a situation like this。

 So the worst case of tree sort is N square。 Oh sorry， building up the trees N square。

 Now how about traverse the tree。What's the cost for me to traverse a tree。Let's do a quick quote。嗯。

What would you say to， I already have the tree， I just want to traverse the tree。

The in all the traveral of the tree。What is the worst case。I want to do an order for worse of a tree。

 It can be a nice tree like this or can be a bad tree like that。What is the cost for me to do this。

Alright， if you look at the vote， still disagree。 But I think， as it is。

 more people are voting for the right answer。The answer is a。You can only visit each node once。

RightYou are not gonna， even if you have this worst case scenario。

 you are saying I will try to get to my left。 There's nothing to the left。

 I print out then go to my right。 You are not going from the root all the way down again and again。

 You just keep going through the， the tree in here。 So overall， it's gonna be linear。

 and the cost of tree sort in the worst case is big O， N square。That's the worst case。 Okay。

 so T salt does give you the worst case。 if you look at it。The worst case is n square。

 but the average case is N loggan。 It's pretty nice。 Okay， That's the average case。

I guess we are done today。 Okay， we'll come back on Wednesday and finish more sorting。All right。

 if I don't see you on Wednesday，m happy thank you。 we'll still be here on Wednesday right。



![](img/6df09d858db3a9858b9784a20339d5fb_2.png)