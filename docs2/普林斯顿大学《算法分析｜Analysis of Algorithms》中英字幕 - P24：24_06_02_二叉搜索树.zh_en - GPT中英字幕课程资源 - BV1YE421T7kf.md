# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P24：24_06_02_二叉搜索树.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/2dfa0aad12a760231bf1c58b47c36645_0.png)

Next， we're going to talk about binary search trees。

We saw that binary trees are a classic structure in combinatorics and they're enumerated by the catalan numbers。

 but they're also a classic structure in computer science。

 it's a fundamental data structure that is used for all sorts of things。

 but one of the most important is for implementing symbol tables where we have lots of information。

 each piece of information is associated with a key and we want to insert things into the symbol table and we want to retrieve them by key。

You can find much more information about symbol tables in our algorithms book or on the book site associated with the book。

 but I'll describe what tree binary search trees are because that's one of the most important algorithms in computer science。

 and it uses a classical data structure of the binary tree。

So we work with nodes and those are things that we can write programs to manipulate each node has a key and the keys have values that are so-called comparable values。

 that means means that we can take two of them a node where they're one's less equal or greater than the other that's all。

呃。Now usually in the implementations we do nowadays， we assume the keys to be all distinct。

 We can do things with equal keys， but both for the analysis and for the implementation。

 it's better to use distinct keys。Now in the binary tree representation， nodes have two subtrees。

 left subtes and right subrees， which are empty or might be whole trees。

And if there's keys in the left subte， all those keys are smaller than V。

And if there's keys in the right subt， they're all larger than V。That's what a binary search tree is。

Now。In Java and again， without going into detail of Java code for those of you who don't know it。

 it might take some it might have to read the algorithm's book a bit to really follow all of this and those of you who do know it。

 but either way it's very this elegant and simple and small amount of code to implement nodes and binary trees in Java so we build a data type that holds this associated information so that we can manipulate it and keep it together and write programs that manipulate。

 you'll see what those look like in just a minute and the only operation that we need to perform is to be able to create a new node with a given key and value and that's what this code does。

 it's defines that data type that holds a node's got four fields it's got a key in a value and it's got a reference to the two subtrees。

 the left subtree has smaller keys and the right subtree has larger keys。

And that's how we represent it。And for programming language aficionados。

 we usually use generic types for keys， which means that we can hold any type of data with that and again you can read about these details in the algorithms book。

So that's what the computer representation of a binary search tree looks like。

 we have nodes that have keys and values， and then each node points to another node which is another binary search tree。

 the one on the left with smaller keys and the one on the right with larger keys。

And it's a recursive structure， and eventually we get to places where the left subre is empty or the right subre is empty。

 in which case those links would be null。So that's the structure and now what I'm going to describe is programs for manipulating that structure。

 for inserting new keys and for searching for keys。

The easiest do search and let's look at the search implementation。

 this is a recursive program that operates on that recursive structure。

There's some programming language jargon at the top that has to do with the generics。And otherwise。

 let's look at what it does， So this is a data type for manipulating binary trees。

 what is a binary tree， it's a root node， so that's what the first line of code says。

Then there's a definition of low nodes， and then this is a method for retrieving the value associated with a given key。

I'll do it line by line， we have a variable x that we set to be the root of the tree。As long as that。

Noode X is not nu。Then we're going to compare the key at x， that's x dot key。

With the key that we were given to search for。That comparison can have three outcomes。

 either less than zero， greater than zero or equals zero。If it's less。

 the key we're looking for is less than x's key， then we'll go to the left。

Go to the left is x equals x dot left。 That's recursively moved down the tree to the left subree that contains。

Smaller nodes than x's。 and we have a smaller key， so that's where we want to go。If it's greater。

 we go to the right， and if it's equal， we're done， we return x's value。

That's the implementation of search for binary search trees。

 so in this example you can see to search， say for M， we started S， M is less than S so we go left。

 it's greater than E， so we go right， and then we're successful to see M。

If we're searching for something that's not in the tree， say we're searching for Q。We go left again。

 Q's less than S。 It's bigger than E。 We go right， It's bigger than M。 We go right。

 but now we're on a null link。 and essentially that says that。

If Q were in the tree would have to be here， but there's nothing in the tree here， so it's not here。

 and in that case， down the last statement in the G implementation， we return all。

So it's a very simply expressed algorithm， this is in a modern programming language。

 it's also easy to program these in even the or machine language if people my age have done that even in any programming environment you can implement binary trees pretty easily with a small amount of code。

Oh， that's unsuccessful。Now what about insert， so this is the code for insert out of the algorithms book and essentially what it does is when we do an unsuccessful search and we come to a null link。

 so say to insert Q， we get to the same place， but then what it does is create a new node for Q。

That's x the first line x equals null return new node and then attaches it there and that's in the recursive calls rather than just x equals x dot left we say x do left equals recursive call and that's what does the attachment of the new node。

 this is a little bit tricky but it's very concise recursive code and then now we've implemented both insert and search。

And so that's an important algorithm that we want to analyze the performance of this algorithm。

 It's actually got good performance in this' widely used。Now。

 the key fact that we have to worry about in doing this analysis。

Is that the shape of a binary search tree depends on the order of insertion of the keys。

So the best thing that could happen would be the keys are inserted in such a way that the tree is perfectly balanced。

That's like the tree that described merch sort that we looked at in the first lecture。

The height of that tree is log n and in that case， all searches are going to be guaranteed to take less than log n the key comparisons say。

A typical case is more like the one that I showed for the example where there's some nodes on either side for most subtrees。

 but it's not perfectly balanced。That's the one that we want to analyze。

 and we'll get to that in a minute。And there's also the worst case， say the keys come in in order。

If the keys come in in order， then it's not very good performance because the average cost of searching for a key in the tree is going to be about n over 2。

 and that's going to be a performance problem。If you think of a huge symbol table and nowadays most of them are huge。

 who say a million or a billion keys， this one over here is going to get to any key with 20 or 30 searches this one could require half million or a half billion。

 it's a very important performance difference that's going to make the difference between being able to address a problem and not address it at all。

 and where does the average fall in between。That's where the analysis of algorithms comes in。

So it's reasonable to analyze binary search tree structures under the assumption that the keys are inserted in random ordert。

Now that's a starting point， certainly you've got situations where clients do not insert them in random order and it's not like Quicksort where we can randomize because the insertions might come from some completely external force we don't have any source and we don't have any way to rearrange their orders。

 so it's not quite as it's not a randomized algorithm that we can guarantee performance probabilistically the way we can with Quick sort。

 but still it's a reasonable model that actually is can be validated in lots of practical situations。

 so it's a good starting point for analysis of a tree algorithm。And when you do that， if you have。

 this is BST built from  ED keys inserted in random ordert。You can see that the trees you get。

They're different， but unlike what we saw for random binary trees with each tree taken equally likely。

 these are kind of balance。Well， sometimes you get a little imbalance。

So that's typical random binary search trees， and again our goal is to characterize this analytically and explain why this is different from what we get with random binary trees。

So we're going to analyze them both。Now， the key thing is that when you're analyzing binary search trees。

The shape of the tree is a property of permutations， not trees。

 our input model is a random permutation that's in things in arbitrary order and factorial possibilities。

Bineary research trees， when we're talking about a random tree。

 we're talking about one out of a cattlealine number of possibilities， which is way less。

So that's really important to remember that we're talking about property of permutations， not tree。

 so you can have， and this gives all possibilities for one， two， three， and four nodes。

And now the one that's blown up is just one illustration that shows that two different permutations can lead to the same tree shape。

So this case one comes in and three goes to the right and then two goes to the left of three。

 and then four goes to the right of tree， but four and two could come in the other order and you'd still get the same treat。

And again。On the other hand， the tree that where the keys come in all in order， one， two，3， four。

 that's the only permutation that gives that shape。The ones that are more balanced。

 there's more permutations that give rise to them。That's an important observation to try to understand why we get more balance with binary search trees than with binary trees。

So that's an observation， and we're going to validate that。Now， in order to get it done。

 we really want to think about the question， if you have a tree shape。

 how many permutations are going to lead to that tree shape？

So that means how many if you would take a permutation and insert it into initially empty binary search tree。

 how many of them are going to give that shape？Well we sort of just did that。

 the answer to that is there's two different ones。Now2 has to be first。 That's the one at the root。

And then either you could have the one go to the left and the three go to the right or the three go to the left and the one go to the right。

 and those are the only ones。And let's look at a bigger tree， how many permutations map to that one？

Well， that's a more complicated problem。So well， one thing you know， is that the root has to be four。

 so you've got at least the first element of orientationation has to be four。

And then you have to have one， two， and three on the left。And 5 and 6 on the right。Well。

 five and six on the right there's only one order that gives that shape， five has to go first。

 and then six。And on the left， you have the two possibilities。Either the 2，1，3。

 but the other thing is that those。Two possibilities with the  one，2，3 and the five and6。

 they can be intermixed in a number of ways， so the answer is 20。

You've got five keys that's the stuff that goes on the left and the right， and you can intermix them。

 five choose two ways， and then you've got the two possibilities for the left and in this case the one possibility for the right。

 and those are the 20 permutations that lead to that tree shape。And you can check that。

 validate that if you don't quite believe or understand that math。So that's a bigger example。

 and then from that it's not hard to come to the general case。

 how many permutations map to a general binary tree。Like that。 Well。

 there's some number of nodes on the left subte。 say the left subt is T Cl then size of TFC C Cbel。

Then the root has to be that number plus one。And then the Right sub tree has its number of notess。

 and then by the same argument that we just gave， if you define P sub T to be the number of permutations that map to a tree T。

 then you have a recursive formula。P of T equals T sub L plus C R choose t subL。

 it's a number of different ways to intermix them， the smaller elements in the larger elements。

 and then for whatever all the ways of intermixing them。

 you can still put them in any one of the piece of T subL orders or any one of the piece of T of R orders。

 you have to multiply all those together to get the number of permutations that map to a general binary tree。

So that's an interesting observation and actually you can apply that formula recursively and just read off from the tree the number of shapes that that mapped to it。

 but we're going to use that exact formula a little bit later on。

So and the other thing to observe from this formula is that that binomial coefficient is going to be much。

 much larger when the two subtrees are nearly balanced， that's the Gaussian distribution。

 so it's much larger at the middle and we verify that analytically。If it's within square root of the。

 it's going to be much， much larger and if T of L is small or T sub R is small。

 it's going to be exponentially smaller， so the number of permutations that map to an unbalanced tree is way。

 way smaller than the number that map to a balanced tree and why that's what we observe in practice。

So in summary， so far， I've described two different binary tree models that they're both fundamental。

 random binary trees from the cattlealan is classic combinatorial structure。

 binary search trees is a classic computer science structure。

 in the one model the BST model that we use in simple table implementations。

 balance shapes are much more likely and actually one way to think of it is what's the probability that the root is of rank K for a given K from1 to an。

Well， in the BST model， it's built from a random permutation。

 so it's the first element in the permutation that goes at the root。

 so the probability that any particular value is at the root is just one over in。

 It's the same for all。That doesn't seem like it balances， but if you compare it with。

 and so anyway that's what it balances and then second will'll compare that probability with what you get for the other case。

So the Catalan model， on the other hand， each tree shape is equally likely。

And this is the probability that the root is of rank K in a random binary tree。

You can have any tree on the left and any tree on the right out of all possible trees that's called a Cataland distribution。

And that gives rise to these much more unbalanced trees， two fundamentally different models。

I want to emphasize that because we go into the analysis and we get it into the math without the picture。

 it's easy to lose track of the fact that we're talking about something that's totally。

 totally different。In fact， here's a plot of that Catalan distribution。

That the root is a rank K in a randomly chosen minor true than nodes， and again。

 this is normalized the way that we usually do these distributional plots so that we can see how it converges to a curve and look at the curve。

most of the weight is off on the edges extremely close to the edges in fact， so as n gets larger。

 most of the probability that the root is of rank n over two becomes exponentially small and the probability that the root is the smallest or the largest actually is a quarter。

 so it's actually pretty good chance that it's going to be unbalanced。And just by the way。

 there's no magic in plotting and distribution like this and people who are comfortable with programming I encourage you to go ahead and try to develop plots like that。

 you can it's easy to write inefficient programs， but if you think about it and this one even isn't that all that efficient。

 but anyway this is the program that I use to produce that plot。So as I mentioned。

 the probability that at least one of the two subtrees is empty is about a half。

So that's why it's going to be unbalanced， It's like flipping a coin and in putting it empty or putting a random one。

 it's going to lead to much， much different shape than we get for the other case。Now again。

 just to full disclosure of the code that I'm using to make these pictures for people that are comfortable with programming。

 the code that I use to generate random binary trees and it's all very similar to the code that I talked about for binary search trees。

 the only difference is that I ask add coordinates to get the height in the width and there little calculation in terms of where to place nodes and I used are。



![](img/2dfa0aad12a760231bf1c58b47c36645_2.png)

Programming model from the algorithms book site to do the drawings。

 but what I want to talk about now is the generate method that's supposed to generate a new tree at a certain depth。

And what that node does is basically it's a recursive program that computes the internal rank of the root according to the appropriate probability distribution。

 and then recursively generates trees on the left and on the right。So and in this case。

 to make the trees look good， I actually included the invisible external nodes in the rank field and the point of this is to show there are a lot of similarities and I use this same code to generate both kinds of trees。

 the only difference is for random BST I uniformly choose the value of that rank and for a random binary tree。

 I went to that Catalan distribution to use it， so with the relatively small amount of code。

 I've've been generating these tree diagrams。And then again， full disclosure。

 and I'm not going to go through that， this is the code using our standard drawing model from the algorithms book site that scales and draws the binary tree as I talked about。

A few minutes ago， and for those of you who enjoy programming。

 it's an interesting exercise to implement the centered by level method that I did for。

Random Catalan trees and to draw general trees and forests and other things。

 each one of those tasks is intriguing programming exercise for people who enjoy programming。

So that's an introduction to binary search trees， and next we'll get into the analysis。



![](img/2dfa0aad12a760231bf1c58b47c36645_4.png)