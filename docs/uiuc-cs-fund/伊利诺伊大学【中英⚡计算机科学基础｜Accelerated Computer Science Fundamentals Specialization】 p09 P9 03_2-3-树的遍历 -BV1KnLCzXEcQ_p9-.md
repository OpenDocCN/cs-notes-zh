# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p09 P9 03_2-3-树的遍历 -BV1KnLCzXEcQ_p9-

![](img/ca6451b743ee7992f6a99a2295271ab8_0.png)

![](img/ca6451b743ee7992f6a99a2295271ab8_1.png)

One of the most important aspects of trees is how do we get the data out of a tree。

 how do we visit every single node， and in what order do we visit these nodes？

All of these topics is covered on this idea of a tree traversal。

 And there' are several different ways to look at a tree。

And several different ways to do a tree traversal。Let's take a look at a sample tree。

Here's a tree that contains a total of nine nodes。These nine nodes are rooted at the plus node here at the root。

 and then on left hand side， we have minus the right hand side， we have times。

 We can see that if we view this tree in one way， we could possibly get a tree that has a math equation。

 Let's see how we might do this。 And let's look at different types of traversals。

 The very first form of a traversal is going to involve looking at every single node and then deciding to go left。

 right or to shout that node out as we visit it。Let's see what happens if we go shouting out the node first。

 then go to the left and then go to the right。 So looking at this tree again。

 if we do shout first at every node， then travel left and then travel right here at the plus node。

 we're going to shout it out。 So the first thing we're going to say is plus。Awesome。

 then since we've shouteded it out， we're going to go left。So here we're going to shout it out again。

We shot out minus， then we're going to going to need to go left and right， so let's go left。

Here at this node A， we're going to shout it out。And we shout out A。 Finally， we need to go left。

 left goes nowhere。 then we come back to a。 we means to go right， right also goes nowhere。

 so we're completely done with a。 and now we can move back up to minus。 We finished a left subt。

 Now we can go to the right subre here in the right subre。 We're going shout out division。

 Then we're going to go left。 going left。 We get to B。 we're going shout out B。

And then go to B's left， which is nowhere， B's right， which is nowhere， and now finally done with B。

 we can return to the division。We've done shot。 We've done left。 We now need to go right。

Shouting out C。Left and right goes nowhere， we done with C， done with division。

 done with minus back up to the plus the root node。

 Now we need to go to the right going to the right， we now have the multiply sign。Shout it out。

Left right。Left node goes to D。Then write notes goes to eat。So the end of this process。

 we have shouted out every single node within this tree。 And this is exactly what a traversal does。

 A traversal needs to visit every node in our tree exactly once and do something with that data。😊。

Here we did a traversal that's called a preorder traversal。

 What we did is we shouted out our node first， and then we went to left。

 and then we went to the right。 It's called pre because that's when we actually did the shouting out。

 That's when we did the visit of the node。 If we think about the source code for this。

 That simply means we need to print out the value of our node。

And then after we printed out the value of our node。

 then we need to do a recursive call to the left child and the right child。

 We can go ahead and write this code real fast。Here in a binary tree member function。

 we're going to do a preorder traversal， and the first thing we're going to do is we're going to call a shout function。

And that's going to happen on the current node。Then we need to call our preorder of cur left and our preorder。

Of cur to right， the final thing we need to do is we need to actually make sure we do a null check to ensure that we don't ever have a null pointer exception when we shout out cur or when we visit cur left cur right。

 do that we simply add our null check around this entire function。Cur does not equal。 No。

 We run all of this code。 Awesome， we have a preorder traversal。

 and I think you'll be able to find out exactly how an in order and post order traversal works。

 But let's go ahead and check them out。 Just like before， we have a traversal。

 and we've done preorder。😊，And now let's do in order。 In order means we're going to go left。

And then we're going to shout it out。And then we're going to go right。So line 52 has nothing。

 Line 56 has nothing。 Line 54 does our shout out of our current node。

 and we're doing an in order traversal。 So we have the source code。 Let's run the source code。

 In order traversal means we do left， Sho right。 So we've done left at the root node。

 So we move to the left， Left at the root node。 You move down here。 left of a goes nowhere。

 So now we shout out A。 The first thing we print out is a Now we go back up。

 Sho out the minus and now we go into our right subte。Go left subte。Here at B。

 we're going to shout out B， because there's no left child。 Then we go right。

 going back up to division。 We shout it out division， then go right and going to C。

 And we have a minus B division C going back up to the root， we now have plus shouting out D times E。

 So all I did was do an inor traversal of every single thing。 And look what we have。

 We have something that looks like a math equation。

 What we see is in order traversal in an order tree is going through the exact order things go into。

 So this tree happens to be a algebraic tree where we have a math equation encoding in the tree。

 If we had parentheses for layers。Then we can see that this code exactly shows us how we might go about encoding a math equation into a tree。

 The very last form traversal is a post order traversal。

 A post order traversal is the exact same logic， except we're going to shout at the end。

 We're going to go left， right， shout。 And that's going to be the exact order。

 we visit every single node。What that means is the root node's going to be printed last because it's going to visit the entire left subte。

 the entire right tree subre before shouting out the note。 Let's do this real fast。 Just an example。

 but it flows exactly the same way as before。 Again， the order is going to be。Left， right， shout。

And this is going to be called a post order traversal。And visiting plus， we go left。left。We get to A。

 we do left and right， and now A is shoutedted out， we then have visited left， we need to go right。

 left， right， here's B， we shot it out。And then see， we shut out division minus。

Then we go the right child。Left child D E times plus this is a post order traversal of the exact same tree。

 So what you saw is we didn't vary the tree at all through this entire process。 Instead。

 the only thing we did was change when we shouted out the node。 either at the beginning。

 before the left and right in the middle in an in order or at the end in a post order。

So these are the three most typical forms of a traversal that we see on a tree。

 but there's one more that is completely different。

So you may not want to actually go into left and right subchildren。

 You may want a different form of traversal altogether。 And for that。

 there is one special traversal that is widely used， and that is a level order traversal。

A level order traversal is going to read every single level one level at a time。

 You're going to read the plus the first level， then the second level。

 then the third level left to right。 Let's see an example of that。

 So level order traversal is going to visit everything on the root level。

Then everything on the second level。 So we see plus on the root minus times。

 then everything on the third level in order， A division D E， finally everything on the last level。

 B， C。 This is completely different way of visiting the exact same tree。

 every single traversal we did had a unique ordering of things， But every single traversal we did。

 Visit every single node exactly once。 There's one last thing I want to mention in this video before we finish it up。

 which is the idea of a traversal in a search because often these terms are used interchangeably。

 doing a traversal requires that every single node is visited。On the other hand。

 a search allows us to discover a particular node throughout the tree。

So when we discover our node in the tree， we may not visit every single node。

 We may use a strategy developed in a traversal to help us find a node quickly。

But a search ends as soon as we find that node while a traversal is going to visit up to every single node。

 This is a broad overview of what it means to do a search and what it means to do a traversal and different forms of doing traversals throughout the tree。

 which may influence the searches that we use later。 We'll dive more into trees in the next video。

 I'll see there。😊。

![](img/ca6451b743ee7992f6a99a2295271ab8_3.png)