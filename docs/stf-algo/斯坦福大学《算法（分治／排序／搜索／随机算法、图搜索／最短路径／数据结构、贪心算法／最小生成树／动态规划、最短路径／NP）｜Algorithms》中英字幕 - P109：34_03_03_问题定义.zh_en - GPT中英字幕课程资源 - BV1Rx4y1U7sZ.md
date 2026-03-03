# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P109：34_03_03_问题定义.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/9d08a0c857ed29c332f7f10b82ec5274_0.png)

So we clearly have something to be excited about。 there's clearly this opportunity to design binary prefixfr codes which improve over the obvious fixed length solution。

 So we'd like to have a， in some sense， optimal algorithm for this problem and for that。

 we of course need a crisp problem definition。 So to do that。

 it turns out to be useful to think of codes as binary trees。

 So this video will develop that connection concluding with the final formal problem statement。

So the last video introduced us to this very interesting computational problem。

 namely given characters from an alphabet with frequencies。

 find the best binary prefix free encoding， find the code which minimizes the average number of bits needed to encode a character。



![](img/9d08a0c857ed29c332f7f10b82ec5274_2.png)

Crucial to reasoning about this problem is thinking of binary codes as binary trees。

 so to give you an idea of this correspondence， let's just revisit three of the binary codes we saw in the previous video and see what kind of trees they correspond to。

So let's just continue with the four symbol alphabet ABCD。

The obvious fixed length code where we encode ABCD with 00。

0110 and11 is just going to correspond to the complete binary tree with four leaves。

So let me label this complete binary tree as follows。

 I'm going to label the leaves A through D from left to right and I'm going to label each edge of the tree with a zero if it corresponds to a left shd relationship and with a one if it corresponds to a right shd relationship and now what you see is there's a correspondence between the bits along root to leaf paths and the fixed length encoding so for example for the symbol C if we follow the path from the root to the leaf labelbeled C we first encounter a1 because it's a right child then we encounter a zero because it's a left child that gives us a one and a zero that's the same as our encoding of the symbol C in this fixed length encoding and the same of course is true for the other three leaves。

Next， when we first started playing around with variable length andcoings to motivate the prefix free property。

 we studied a code where we replaced the double 0 for an A with a single0 and the double one for a D with a single one。

 Now， this code was not prefix free。But we can still represent it as a binary tree。

 it's just not going to be a complete one。So I'm going to label the edges of this tree the same way as before left childil edges will be given a label of0。

 right childil edges will be given a label of1。 I'm going to label the left and right children of the root A and D respectively and the two leaves will be given the labels B and C。

 The reason I labeled the nodes in this way is because then we have the same kind of correspondence between the encodings that we proposed for the various symbols and the bits that you see along a path from the root to nodes with those symbols So for example。

 if you look at the node labeled D the path from the root only has a single bit1 and that coincides with the proposed encoding of the symbol D。

 Now remember this code is not prefix free and so therefore as we saw it had ambiguity So if you're wondering what some encoded message means and you see zero you're not sure that zero might be representing the symbol A or alternatively it might be the first half of an encoding of the symbol B。

So this ambiguity is also noticeable in the tree and the property in the tree that tipss you off to the ambiguity is that there are symbols at internal nodes of the tree。

 the symbols are not nearly at the leaves as they were with the first tree with the fixed length encoding。

 but there are also two internal nodes that have symbols。

So let's draw the tree for our final example， which was the variable length but prefix free code that we looked at in the previous video。

So this is going to correspond to a tree which is not perfectly balanced。

 but it will have labels only at the leaves of the tree。

So if you label the edges of this tree the way we've been doing all the left child edges get a zero。

 all the right child edges get a1 and we label the leaves of the tree from A to D going from left to right。

 you'll see we have the sand correspondences in the previous two trees the sequence of bits from the root to a leaf coincide with the proposed encoding for it so for example。

 if we look at the leaf labeled C because you traverse a right child or another right child and then a left child to get to it。

 that's the sequence 110 and that it's precisely the proposed encoding for the symbol C。



![](img/9d08a0c857ed29c332f7f10b82ec5274_4.png)

So in general， any binary code can be expressed as a tree in this way with the left childil pointer being labeled with zeros。

 the right childil pointers being labeled with ones。

 and the various nodes being labeled with the symbols of the given alphabets and the bits from the root down to the node labeled with the given symbol corresponding to the proposed encoding for that symbol。



![](img/9d08a0c857ed29c332f7f10b82ec5274_6.png)

![](img/9d08a0c857ed29c332f7f10b82ec5274_7.png)

And what's cool about thinking about codes as trees is that the really important prefix free condition。

 which seems like a nuisance to check in the abstract， shows up in a really clean way in these trees。

 namely the prefix free condition is the same as leaves being the only nodes that have labels。

 no internal nodes are allowed to have a label in a prefix free code。

The reason for this is that we've set it up so that the encodings correspond to the bits along pass from the root to the labeled node。

 so being a prefix of another corresponds to one node being an ancestor of the other。

 and so if all the labels are at the leaves and of course nobody's an ancestor of the other and we have no prefixes。

The other thing that's really cool about this tree representation of codes is it becomes pictorially obvious how you do decoding。

 given a sequence of zeros and ones from a prefix free binary code。

 namely you start at the beginning and you start the root of your tree whenever you see a zero you go left。

 whenever you see a one you go right at some point you'll hit a leaf。

 that leaf will have some label and that's the symbol that's being encoded after you hit a leaf you just start all over again back to the root。

So for example， if you were using our variable length prefix free code for the four letter alphabet as in our running example。

 and you were given the sequence of  zeros and1s，011，0111。

 what would you do Well you'd start at the root？And you see a zero。

 so you follow the left child pointer and you immediately get to a leaf， it's labeled A。

 so you're going to output an A as the first symbol now you start all over。

 you return to the roots now what do you see you see a one so you go right。

 you see another one so you go right and now you see a zero so you go left and that gets you to the leaf labeled C。

Now you start all over again， you see a one， you go right， you see a one， you go right again。

 and then finally you see yet one more one and you wind up at the leaf labeled D。

So by repeated traversals through the tree， you decode this sequence of zeros and ones as a CD。

 there was never any ambiguity because when you hit a label。

 you know you're at a leaf there's nowhere to go at every internal node， it's unlabeled。

 you know to expect another bit， another traversal further down in the tree。

So a final important point about this correspondence is that the encoding links of the symbols。

 the number of bits needed to encode the various symbols are just the depths of the corresponding leaves in the tree that correspond to the code。

 so for example in our running example， the symbol A is the only one that needs only one bit to encode and it's also the only leaf in level one of the tree and similarly B needs two bits it shows up in the next level。

 the C and the D that which need three bits show up in the third level。

So this correspondence is really just by construction， so how do you encode a given symbol。

 well it's just the bits on the path from the roots and that the number of such bits is just the number of pointer traversals you need to get from the root down to that leaf and that's just the depth of that leaf in the tree。

So we're now in a great position to really have a crisp definition of the problem， the input。

 of course， is just the frequencies for a bunch of different symbols I from some alphabet capital sigma。

 I'm going to use P sub I as notation for the frequency of symbol I。



![](img/9d08a0c857ed29c332f7f10b82ec5274_9.png)

![](img/9d08a0c857ed29c332f7f10b82ec5274_10.png)

So we know what it is we want to optimize， we want to minimize the expected number of bits needed to encode a symbol where the average。

 the expectation is taken over the provided frequencies of the various symbols。

 but let's express this objective function using our newfound correspondence with binary trees。

 in particular， the fact that we can think about encoding lengths as depths of leaves and trees。



![](img/9d08a0c857ed29c332f7f10b82ec5274_12.png)

So given a tree T， which corresponds to a prefix free binary code。

 that is it should be a binary tree and the leaves of this tree should be in one to one correspondence with the symbols of sigma。

 we're going to define capital L of T as the average encoding length。



![](img/9d08a0c857ed29c332f7f10b82ec5274_14.png)

![](img/9d08a0c857ed29c332f7f10b82ec5274_15.png)

It's an average in the sense that we sum over all of the symbols of the alphabet。

 we weight each symbol by the frequency and remember this is part of the input so by the provided frequency piece of I of that symbol I and then how many bits do we need to encode that symbol I well it's just the depth of the leaf which is labeled I in the given tree capital T so this is what we want to make as small as possible。

So for instance， using the data from the previous video， the letter is ABCD with frequencies 60， 25。

 10 and 5%。Then if we use the complete binary tree that is the fixed length encoding。

 we just get two bits per character。Well， if we use the lopsided tree optimized so that each A only takes one bit while suffering three bits for C and D。

 then the average encoding length drops to 1。55 as we saw in the last video。



![](img/9d08a0c857ed29c332f7f10b82ec5274_17.png)

So what then is the goal， what's the responsibility of our algorithm。

 well amongst all binary trees which have leaves and correspondence to the symbols of Sigma。

 we want to compute the one which makes this average encoding length as smallest possible。

 which minimizes our objective function capital L turns out Huffman's greedy algorithm does it more details to come。

