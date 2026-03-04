# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P150：-150-Red-Black Tree Rotations Chap8 Video 34.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

There are only four possible ways that the insertion of a red node could have violated the local in。

I've drawn all of them here。In every case， we have a black parent， followed by a red node。

Followed by the violation of another red note。Now we know the parent had to be black because the original tree satisfied the local invariant。

So there's four cases because at each point you can go left or right and then left or right。

Let's look at the first of those cases。I've named each of the nodes here， X， Y and Z， by that。

 I mean the value stored at the node。And then I have some subtes coming off of X， Y， and Z。

 I've called those subtes， A， B， C， and D。I don't care what's in those subtes very much。

 we're not going to look inside of them， it's fine if they are leaves。

So the violation here is with X as a second red node。Let's see how to rotate the tree。

 get some more balance in it， and restore the local invariant。First off。

 we're going to take Y and make it the root of this subt that we construct as the result。😡。

I didn't pick Y， randomly。I chose Y， because it's the red node。And that's part of a violation。

That is closest in value to Z to the root。Because by the BST invariant， x has to be less than y。

 y has to be less than z， so y is closer to z than x's。So I'll take why。

And then imagine that like physically， I pick it up and pull it up into the air。😡。

And that the other values in the tree have some weight to them。

 and they kind of settle down with gravity around that。Here's where they fall。

Z ends up on the right hand side of Y。It has to。 It's a bigger value than y。

 so it can't go on the left of Y。 It's got to go on the right。That maintains the BST environment。

The two subtes， C and D， likewise， fall down on the right hand side of Y。

Because both of them are bigger than y， according to the original tree， in that tree。

 the BST invariant says that anything in C has to be bigger than y because C is the right subchild of Y。



![](img/a83d6086092e2f4cec1f5074b310d1b6_1.png)

![](img/a83d6086092e2f4cec1f5074b310d1b6_2.png)

![](img/a83d6086092e2f4cec1f5074b310d1b6_3.png)

And anything in D has to be bigger than y。Because Y itself is less than Z and D is the right subchild of Z。

So both C and D end up on the right hand side of Y in the new tree。Of course， D is on the right。Of Z。

 because that's where it was in the original tree， all the values in D are bigger than Z。



![](img/a83d6086092e2f4cec1f5074b310d1b6_5.png)

![](img/a83d6086092e2f4cec1f5074b310d1b6_6.png)

C， on the other hand， ends up on the left hand side of Z， because in the original tree。

 C was also on the left hand side of Z， so that means all the values in C are less than Z。



![](img/a83d6086092e2f4cec1f5074b310d1b6_8.png)

Okay， so all of that follows from the BST invariant， it's a little tricky to work out。

 you might want to stop and make sure you can work it out yourself as well。😡，Next。

 we need to deal with X， which was the violation。We'll keep it as a child of why it has to be the left child by the BST invariant。

And now we will change its color to be black that fixes the local invariant violation for x and Y。

Subrees A and B can go as the children of X just where they were before。

 Nothing has changed about their values。 The BSD invariant is fine with themby。



![](img/a83d6086092e2f4cec1f5074b310d1b6_10.png)

![](img/a83d6086092e2f4cec1f5074b310d1b6_11.png)

![](img/a83d6086092e2f4cec1f5074b310d1b6_12.png)

Now let's think about the black node we just created X。

We need to be convinced that we're maintaining the global invariant as we go。



![](img/a83d6086092e2f4cec1f5074b310d1b6_14.png)

Well， in the original tree here， we had one black node along all paths that we've shown here。

Now there might be some other black nodes inside of A， B， C， and D。

 but we're guaranteed that there's the same number of them in each case because the global invariant held of that original tree。

Well， in the new tree， we again have one black node that we're showing along every path。

ABC And D could still have their own black nodes， but it's fine。 It'll be the same number of them。

So we're maintaining the global invariant by doing this recoloring of X。

What that means is we've now succeeded in maintaining the BST invariant。

 maintaining the global invariant。Fixing up the local invariant for X and Y。

But there's a new problem。Z here， the original root of this subtree。

 was not necessarily the root of the entire red black tree。



![](img/a83d6086092e2f4cec1f5074b310d1b6_16.png)

It itself might have had some other nodes above it。So when we return this new tree with a red root。

We might have just created a new violation。Because。

The parent of Z in the original tree might have been red。



![](img/a83d6086092e2f4cec1f5074b310d1b6_18.png)

In which case， y would then be a second red node right below it？So we need to keep recursing up。

Go to whatever the original parent of Z was from the tree。Rebalance。

 keep doing this all the way up to the root of the entire red black tree。Okay。

 so that was one of the rotate operations， the others are extremely similar。

For the second red black rotate， we again pick up Y because it's the closest in value to Z。

Because x is less than z， but y itself is greater than x。So why is closer to Z still than exit？

So we pick up Y and we let everything fall off of it into the right place， we recolor X to be black。

The third and fourth rotation operations are pretty much symmetrical to the ones that we just saw so I won't go through those in detail。

But I do want you to notice the right hand tree in every one of these slides。

Just focus on it for a second。 I'm going to flip back。

There is rotation3 and rotation 2 and rotation1。In every single case， the output tree is the same。

This is the beauty of Okasaki's algorithm。No matter what the input is。

 we get the same output in every rotation。And what that means is there's a very elegant implementation of this with pattern matching。

Here it is。Each of those rotations corresponds to one branch of this pattern match。

 I've put in comments here so you can track it back to which rotation it is。

So we have four different patterns that we've written here。But only one right hand side branch。

 we've used an orR pattern here to combine them all together。And that's it。

All of that complicated stuff that it takes to show with pictures。

 we can actually implement in these just few lines of code with pattern matching。How cool is that。

Now I'm not going to go so far as to say that you can really get an intuition for what this algorithm does from the code here。

 not at all， in fact， I find the pictures much easier to understand in that respect than the code。😡。

But when you look at implementations of red black trees in imperative languages and go ahead。

 go look one up， you'll find that they aren't nearly this compact。

So let's finish off Okasaki's algorithm。We went ahead and colored the new node red。

We recursed our way back up the tree， balancing as we went。And then when we get to the very top。

 the last step of his algorithm is to make the root black。

Because it's possible that we rebalanced and pushed a red note up to the root。

If we do recall a red note at the root to be black as the last step here。

 that will increase the black height of the tree by one。😡。

The black height is the number of black nodes on any path through the tree。

This is the only place in the entire algorithm that the black height of the tree is allowed to increase。

😡。

![](img/a83d6086092e2f4cec1f5074b310d1b6_20.png)