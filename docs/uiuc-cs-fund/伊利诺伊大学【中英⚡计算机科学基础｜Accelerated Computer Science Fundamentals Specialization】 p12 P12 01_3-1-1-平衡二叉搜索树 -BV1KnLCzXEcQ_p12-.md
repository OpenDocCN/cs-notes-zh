# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p12 P12 01_3-1-1-平衡二叉搜索树 -BV1KnLCzXEcQ_p12-

。

![](img/148206e714cc9f3cd9cad5a66b8553c7_1.png)

![](img/148206e714cc9f3cd9cad5a66b8553c7_2.png)

In the last video， we talked about the balance factor of a binary tree。 Now。

 we're going to talk about the balanced binary search trees。

 which are trees are height balanced to ensure that nearly half the data exists on that left half of the tree。

 Nearly half the data exists on the right half of the tree。 Here on the left。

 we see a very balanced binary search tree。 While on the right。

 this binary search tree is far out of balance。Let's analyze substructure of this tree and develop an algorithm to ensure that we can turn a binary search tree that's unbalanced into a binary search tree that's completely balanced。

 There's two substructures that we're going to identify in a graph We're going to identify a substructure that we're going to call a mountain。

 which is a node that has both a left and the right child and a substructure called a stick。

 which going to be a node that has two children the same direction。

And no children in the other direction。The stick is going to be something that we're going to want to transform into a mountain by transforming sticks into mountains。

 We're going to make sure that our binary tree stays as balanced as possible。

So let's consider a binary search tree and a pretty simple example。

This binary search tree was initially balanced。 We know it is balanced because we can check the balance factor of every single node。

 which is the height of the right child， minus height of the left child。

 height of the right child in original tree is simply going to be one。

 The height of the left child is 0 and doing one-0。We see the balance factor of the root node is one。

By adding a new node to the end of this tree。 now， the height of this right subt is 2，2-0 is 2。

 And because the magnitude of the balance factor is greater than one。

 we know this tree as a whole is at of balance。So when we look at this tree。

 we want to consider where the deepest node that is out of balance。 So here this new node added。

 it has a balance factor of 0。 We have the same number of children on both sides。

 Its parent has a balance factor of one， because it has one extra height on the right side over the left side。

 Next tree has a balance factor of one。 again， left side， having a height of one right side。

 having a height of 2。 only here at the root node Do we see that the balance factor is 2。

 And that's the deepest point in the tree that we're out of balance。

Once we've identified the deepest point in the tree。

 we're going to identify the stick that causes the node to be out of balance。Here。

 we've done just that。 Not a stick running from U V an unenlabeled node is three nodes that make a stick。

 That is the reason this tree is out of balance。 Let's try and transform this into a mountain。

To do that， I'm going to pick up the middle note in the stick right here。 this V。 raise it up。

And by raising up this middle node by pushing this whole node up。

 we see that this node is going to become a mountain and this mountain。

 then we simply repair all node notice till left of view。 there's a pointer。 to left of view。

 there's a pointer。The node that was off the left of Y is now going to be on the right of you。

And the right of why is going to be untouched。So what we've done is we have created a tree that's going to maintain the factors of being a binary search tree。

 So all of the order here is maintained。And we've decreased the balance factor of the root node。

 So here now， the balance factor was 2， and you've transformed it into a balance factor of 0 through using a simple binary search tree rotation。

So if we consider this arbitrarily， we can talk about generic left rotation。

The idea of a b rotation is we're going to consider the deepest point of the tree that has an imbalance to be node B。

 So here right at the top， this is the node。 This may be somewhere deep inside the tree。

 All we know is this node B is the lowest or deepest point inside of our tree where we've detected imbalance。

 An imbalance is a balance factor that has a magnitude greater than one。 So here。

 the balance factor is 2。 When the case the balance factor is 2， we need to look at this next node。

 So we look at C。😊，Given that we found B， we now look at C and see what the C's balance factor is。

 If C's balance factor is 1， we know that B is out of balance heavily to the right and C is also almost out of balance to the right。

 That means our tree definitely has a terrible slant to the right。

What we can do is we can do what's called a left rotation to solve this。Doing a left rotation。

 this means bringing C up and making a tip of the mountain and rotating everything to the left that brings B down and attaches C to B。

So looking at T1， T2， we see T1 and T2 is attached to B， C is attached to B and D。

 and finding T 3 and T4 remains attached to D。We call this rotation left rotation。

 and this rotation occurs whenever the deepest point of imbalance has a balance factor of 2。

 and the balance factor of the node that follows has a balance factor of 1。 Anytime this occurs。

 we can do a left rotation to repair this imbalance。Let's consider a second example。

 This is going to be very similar。 But instead of having a node added to left。

 we have a node added to the right。 If we identify the substructure that caused the problem。

The deepest point of im balance is now here。 It's no longer the root node。

 but this node has a balance factor of 2。 Notice that the height of the right sub tree is 2。

 The height of the left sub tree is 0，2-0 is  equal to 2。This， unfortunately。

 doesn't fit our cases that we've looked at so far。Instead。

 we've identified a structure that looks more like an elbow than a stick。

 And this is indeed our third structure。 This is sort of a hybrid between both a stick。

As well as a mountain。What we need to do whenever we identify an elbow is actually to fix the elbow to make it a stick。

 We do that by doing a rotation about the bend of the elbow。Notice here， we have。An elbow。

 We do a transformation by moving the yellow note up， this yellow note up。

 then transforms this elbow into a stick。Once we have a stick， we know exactly what to do。

 We consider this a right left rotation， because what we're going to do is we're going to do a right rotation about D to place it in place and then a left rotation。

About C to fix the stick。 So here， this right left rotation is going to be required whenever we identify the point of imbalance in a tree B。

 the balance factor of V is 2。And then the balance factor of the node that follows B is going to be negative 1。

 And insert at T 2 or T 3 is going to cause this point of imbalance。

And we simply need to do two different rotations to fix this im balanceance。 See this completely。

 we notice that we first transform this elbow into a stick。

 And once we've transformed the elbow into a stick。

We raise up the center note of the stick and make it into a mountain。

 So here we go from an elbow to a stick into a mountain。 And at the end。

 we know as we take a tree that's completely out of balance and have a nice。

 perfectly balanced binary search tree at the end of this process。😊。

So we can look at all of this rotations and think about how we can just flip this idea that when we have a left rotation。

 if we consider a tree to be out of bound entirely opposite direction。

 we simply need to do right rotation。 Look at a balance factor of the deepest note of imbalance in our tree。

If it is， too， we start with a left rotation。If it's negative2， negative 2。

 we start with the right rotation。Only then when we look at the next node。

 can we identify whether or not it's a single rotation。 So if both of the signs match。

 we say we only need to a left rotation。 This transforms a stick into a mount。Just like negatives。

 we transform a sticking amount。 When the signs differ， we know we have a case of an elbow。

When we have the case of an elbow。We need to do a double rotation or a left right rotation or a right left rotation。

 This unbs the elbow and then does the simple transformation to transform a stick into a mountain。

So I introduce these things in really simple terms so we can talk about sticks， mountains and elbows。

 And we saw visually how this code is able to transform an out of balanceance binary search tree and bring it into balance at the moment we detect the imbalance。

 So as we insert nodes， we're going to want to ensure that we' keeping in the binary search tree inbalance。

 every single insertion And when we complete an insertion。

 we're going to ensure that by the time we return it back to the user that that binary search tree is going to be balanced。

😊，BST rotations or binary search rotations is the mechanism to restore that balance。

 We know there's four different rotations。A left rotation， a right rotation， a left right rotation。

 and a right left rotation。These rotations are all local operations。

 All we're doing is changing the point of imbalance， rearranging a few pointers。 because of that。

 we can say this runs in constant time。 The code we're going to write to do these transformations are going to be as simple as four lines。

 The last thing to mention is this algorithm actually has a name。This is called an A VL tree。

 We're going to dive into all of the details about an A VL tree and talk more about it。 Next lecture。

 I'll see you guys then。

![](img/148206e714cc9f3cd9cad5a66b8553c7_4.png)