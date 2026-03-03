# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P63：19_03_03_二叉搜索树基础-第二部分.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So what I want to do next is test your understanding of both the search and insertion procedures by asking you about their running time。

 So of the following four parameters of a search tree that contains in different keys。

 which one governs the worst case time of a search or of an insertion。

So the correct answer is the third one。So the height of a search tree governs the worst case time of a search or of an insertion noticeice that means merely knowing the number of keys n is not enough to deduce what the worst case search time is。

 you also have to know something about the structure of the tree so to see that just let's think about the two examples that we've been running so far。

One of which is nice and balanced。And the other of which， which contains exactly the same five keys。

 is super unbalanced。 It's this crazy linked list， in effect。So in any search tree。

 the worst case time to do a search or an insertion is proportional to the largest number of pointers left or right child pointers that you might have to follow to get from the root all the way to a null pointer Of course in a successful search you're going to terminate before you encounter a null pointer but in the worst case or an insertion you go all the way to a null pointer Now in the tree on the left you're going to follow at most three such pointers So for example。

 if you're searching for 2。5 you're going to follow a left pointer followed by a right pointer。

 followed by another right pointer and then that one's going to be null so you're going to follow three pointers on the other hand。

 in the right tree you might follow as many as five pointers before that fifth pointer is null。

 for example， if you search for the key0 you're going to traverse five left pointers in a row and then you're finally going to encounter the null at the end So it is not constant times certainly you have to get to the bottom of the tree it's going to be proportional to the logarithm in the number of keys if you have a nicely balanced binary search tree like this one on the left。

beal to the number of keys n as in the fourth answer。

 if you have a really lousy search tree like this one on the right， and in general。

 the search time or the insertion time is going to be proportional to the height。

 the largest number of hops you need to take to get from the root to a leaf of the tree。



![](img/58b1e09cf16d117f734089fb113201dc_1.png)

Let's move on to some more operations that search trees support， but that， for example。

 the dynamics data structures of heaps and hash tables do not。

So let's start with the minimum and the maximum， so by contrast in a heap。

 remember you can choose one of the or the two， you can either find the minimum easily or find the maximum easily。

 but not both in a search tree it's really easy to find either the min or the max。



![](img/58b1e09cf16d117f734089fb113201dc_3.png)

So let's start with the minimum， one way to think of it is that you do a search for negative infinity in the search tree。

So you start at the root。And you just keep following left child pointers until you run out until you hit a null。

 And whatever the last key that you visit has to be the smallest key of the tree， right。

 Because think about it。 supposeuppose you start at the root， right。

 Suppose that the root is not the minimum， then where's the minimum got to be。

 It's got to be in the left subtre。 So you follow the left child pointer。

 and then you just repeat the argument。 If you haven't already found the minimum。

 Where is it got to be with respect to the current place。

 it's got to be in the left subtre and you just iterate until you can't go to the left any further。

So for example， in our running search tree。You'll notice that if we just keep following left shadow pointers。

 we'll start at the three， we'll go to the one， we'll try to go left from the one。

 we'll hit a null pointer and we return one， and one is indeed the minimum key in this tree。Now。

 given that we've gone over how to compute the minimum。

 no prizes to guess how we compute the maximum。 Of course， if we want to compute the maximum。

 instead of following left child pointers， we follow right child pointers by symmetric reasoning that's guaranteed to find the largest key in the tree。

 It's like searching for the key plus infinity。All right， so what about computing the predecessor。

 so remember this means you're given a key in the tree an element of the tree and you want to find the next smallest element so for example。

 the predecessor of the three is two， the predecessor of the two in this tree is the one。

 the predecessor of the five is the four， the predecessor of the four is the three。



![](img/58b1e09cf16d117f734089fb113201dc_5.png)

So here I'll be a little hand wavy just in the interests of getting through all of the operations in a reasonable amount of time。

 But let me just point out that there's one really easy case。

 and then there's one slightly trickier case。 So the easy case。

Is when the node with the key K has a non empty left subte。 If that's the case。

 then what you want is simply the biggest element in this node's left subt。

So all good for you to prove formally that this is indeed the correct way to compute predecessors four keys that do have a nonempty left subt。

 let's just verify it in our example by going through the trees that have a left subtree and checking that this is。

 in fact what we want。 Now， if you look at it， there's actually only two nodes that have a non-empty left subte。

 the three has a nonempty left subte， and indeed the largest key in the left subte of three is the two。

 and that is the predecessor of the three。 So that worked out fine。

And then the other node with a non empty left subtre is the five。

 and its left subte is simply the element 4。 Of course， the maximum in that tree is also 4。

 And youll notice that is indeed the predecessor of 5 in this entire search tree。

 So the trickier case is what happens if you have a key with no left subtree at all。Okay。

 so what are you going to do if you're not in the easy case Well， given at this node with keyK。

 you only have three pointers and by assumption the left one is null。

 So that's not going to get you anywhere。 Now， the right child pointer。

 if you think about it is totally pointless for computing the predecessor remember the predecessor is going to be a key less than the given keyK。

 the right subre by definition of a search tree only has keys that are bigger than K。

 So it stands to reason to find the predecessor， we got to follow the parent pointer。 maybe in fact。

 more than one parent pointer。So to motivate exactly how we're going to follow parent pointers。

 let's look at a couple of examples in our favorite search tree here on the right。

 So let's start with the node2。So we know we got to follow a parent pointer when we follow two's parent pointer we get to one and boom one in fact is to's predecessor in this tree。

 so that was really easy to compute to's predecessor。

 it seems that all we have to do is follow the parent pointer。So for another example， though。

 let's think about the node 4。Now，4， when we follow its parent pointer。

 we get to5 and 5 is not for's predecessor。 It's fors successor。 right。

 We want a key that is less than where we started。 We followed the parent pointer， and it was bigger。

 But if we follow one more parent pointer， then we get to the three。 So from the two。

 we needed to follow one parent pointer from the four， we needed to follow two parent pointers。

 But the point is， you just need to follow parent pointers until you get to a node with key smaller than your own。

 And at that point， you can stop and that's guaranteed to be the predecessor。

So hopefully you found this intuitive， I should say I have definitely not formally proved that this works。

 and that is a good exercise for those of you that want to have a deeper understanding of search trees and this magical search tree property and all of the structure that it grants you。

The other thing I should mention is another way to interpret the terminating criterion。

 So what I've said is you stop your search of parent pointers as soon as you get to a key smaller than yours if you think about a little bit。

 you'll realize you'll get to a key smaller than yours the very first time you take a left turn。

 So the very first time that you go from a right child to its parent。

 look at the example when we started from two， we took a left turn right we went up a link going leftward two is a right child of one and that's when we got to the predecessor in just one step。

By contrast， when we started from the four， our first step was to the right。

 So we got to a node that was bigger than where we started4 is five's left childil。

 So it's got to be smaller than five。 But the first time we took a left turn on the next step。

 we got to a node that was not only smaller than5， but actually smaller from four。

 smaller from our starting point。 So in fact， you're going to see a key smaller than your starting point。

 the very first time you take a left turn。 the very first time you go from a node to a parent and in fact。

 that node is that parent's right child。So this is another statement， which I think is intuitive。

 but which formerly is not totally obvious。 And again。

 I encourage you to think carefully about why these two descriptions of the terminating criteria are exactly the same。

 So it doesn't matter if you stop when you first find a key smaller than your starting point。

 it doesn't matter if you first stop when you follow a parent pointer that goes from a node that's the right child of a node。

 either way you're going to stop at exactly the same time。

 So I encourage you to think about why those are the exact same stopping condition。

 a couple of other details。 if you start from the unique node that has no predecessor at all。

 you're never going to trigger this terminating condition， So for example。

 if you start from the node one in the search tree， not only is the left subtree empty。

 which says you're supposed to start traverseing parent pointers。

 but then when you traverse a parent pointer， you only go to the right。

 you never turn left and that's because there's no predecessor。

 So that's how you detect that you're at the minimum of a search tree。 and then of course。

 if you wanted to compute the successor of a key instead of the predecessor。

 obviously you just flip left and right throughout this entire description。

So that's the high level explanation of all of these different ordering operations。

 minimum maximum predecessor and successor work in a search tree。

 let me ask you the same question I asked you when we talked about search and insertion。

 how long do these operations take in the worst case？Well the answer is the same as it was before。

 it's proportional to the height of the tree， and the explanation is exactly the same as it was before。

So to understand the dependence on the height， let's just focus on the maximum operation as is stated in the question。

 the other three operations， the running time is proportional to the height in the worst case for exactly the same reasons。

 so what does the max operation do when you start at the route and you just follow rightchd pointers until you run out of them until you hit null so you know the running time is going to be no worse than the longest such path it's a particular path from the route to essentially a leaf。

So it's never going to have running time more than the height of the tree。 On the other hand。

 for all you know。The path from the root to the maximum key might well be the longest one in the tree。

 It might be the path that actually determines the height of the search tree。 So， for example。

 in our running unbalanced example， that would be a bad tree for the minimum operation。

 If you look for the minimum in this tree， then you'd have to traverse every single pointer from5 all the way down to one。

 Of course， there's an analogous， bad search tree for the maximum operation where the one is the root and the five is all the way down as a leaf。

Another thing you can do with search trees， which mimics what you can do with sorted arrays is you can print out all of the keys in sorted order in linear time with constant time per element。

 Obviously in a sorted array， this is trivial。 you just use a for loop starting at the beginning。

 going to the end of the array， printing out the keys one at a time。

 and there's a very elegant recursive implementation for doing the exact same thing in a search tree。



![](img/58b1e09cf16d117f734089fb113201dc_7.png)

And this is known as an in order traversal of a binary search tree。So as always。

 you begin at the beginning namely at the root of the search tree。And a little bit of notation。

 let's call all of the search tree that starts at R's left child T sub L and the search tree rooted at R's right child T sub R。

In our running example， of course， the root is3， T subl would correspond to the search tree comprising only the elements 1 and 2。

 T sub R would correspond to the subt， comprising only the elements 5 and 4。 Now， remember。

 we want to print out the key is an increasing order。 So in particular。

 the first key we want to print out is the smallest of them all。

 So something we definitely don't want to do is we don't want to first print out the key at the root。

 For example， in our search tree example， the roots key is3。 We don't want to print that out first。

 We want to print out the one first。 So where's the minimum lie。 Well， by the search tree property。

 It's got to lie in the left subte T subl。 So we're just going to recurse on Tl。

So by the magic of recursion， or if you prefer induction。

 what recursing on T Sbel is going to accomplish is we're going to print out all of the keys in T CL in increasing order from smallest to largest。



![](img/58b1e09cf16d117f734089fb113201dc_9.png)

Now that's pretty cool because TCL contains exactly the keys that are smaller than the key at the root。

 remember that's the search tree property， everything bigger than the roots key has to be in the left subte。

 everything bigger than the roots key has to be in its right subree。So in our concrete example。

 this first recursive call is just going to print out the keys 1 and then two。

 And now if you think about it， it's the perfect time to print out the key at the root right。

 we want to print out all the keys in increasing order。

 We've already done everything less than the roots key。 where you know。

 recursing on the right hand side willll take care of everything bigger than it。

 So in between the two recursive calls。 And this is what it's called an in order traversal。

 That's when we want to print out。😊，Rs key。And clearly， this works on our concrete example。

 the reverse recursive call prints out one and2， it's the perfect time to print out three。

 and then the recursive call will print out four and5。

 and more generally the recursive call on the right substrate will print out all of the keys bigger than the roots key in increasing order again by the magic of recursion or induction。

So the fact that this pseudocode is correct， the fact that this so-called in order traversal indeed prints out the keys in increasing order is a fairly straightforward proof by induction。

 it's very much in the spirit of the proofs by induction of correctness of divide and conquer algorithms that we discussed earlier in the course。

So what about the running time of an in order traversal。

 The claim is that the running time of this procedure is linear。

 It's O of n where n is the number of keys in the search tree。

 And the reason is there's exactly one recursive call for each node of the tree and constant work is done in each of those recursive calls in a little more detail。

 So what is the in order traversal do or it prints out the keys in increasing order in particular。

 it prints out each key exactly once。 Each recursive call prints out exactly one keys value。

 So there's exactly n recursive calls and all the recursive call does is print one thing。

 So n recursive calls constant time for each。 that gives us a running time of O of N overall。

In most data structures， deletion is the most difficult operation， and in search trees。

 there are no exception。 So let's get into it and talk about how deletion works。

 There are three different cases。 So the first order of business is to locate the node that has the key K to locate the node that we want to get rid of。

 right， So for starters， maybe we're trying to delete the key to from our running example search tree。

 So the first thing we need to do is figure out where it is。

So there are three possibilities for the number of children that a node in a search tree might have。

 it might have zero children， it might have one child that might have two children。

 corresponding to those three cases， the deletion pseudocode will also have three cases。

 so let's start with the happy case where there's only zero children like in this case where we are deleting the key two from the search tree。

Then， of course， we can， without any reservations， just delete the node directly from the search tree。

 Nothing can go wrong。 There's no children depending on that node。

Then there's the medium difficult case， this is where the node containing K has one child。

An example here would be if we wanted to delete five from the search tree。

So the medium case is also not too bad， all you got to do is splice out the node that you want to delete。

 that creates a hole in the tree， but then that deleted node's unique child assumes the previous position of the deleted node。



![](img/58b1e09cf16d117f734089fb113201dc_11.png)

I could make a nerdy joke about Shakespeare right here， but I'll refrain。For example。

 in our five node search tree， if we wanted to， let's say we haven't actually deleted two out of this one。

 If we wanted to delete the five， the five， we'd take it out of the tree， that would leave a hole。

 but then we just replace the position previously held by five by its unique child 4。

 And if you think about it， that works just fine。 in the sense that that preserves the search tree property。

 Remember， the search tree property says that everything in say a right subtree has to be bigger than everything in the node's key。

 So we've made four， the new right child of three。 but four and any children that it might have were always part of three's right subtree。

 So all that stuff has got to be bigger than three。

 So there's no problem putting four and possibly all of its descendants as the right child of three。

 the search tree property is in fact， retained。

![](img/58b1e09cf16d117f734089fb113201dc_13.png)

So the final difficult case then is when the node being deleted has both of its children。

 has two children。 So in our running example with five nodes。

 this would only transpire if we wanted to delete the root if you wanted to delete the key three from the tree。

 The problem， of course is that you know you can try ripping out this node from the tree。

 but then there's this whole。 and it's not clear that it's going to work to promote either child into that spot。

 you might stare at our example search tree and try to understand what would happen if you tried to bring one up to be the root or if you tried to bring five up to be the root problemsblem would happen。

 that's what would happen。This is an interesting contrast to when we face the same issue with heaps。

 because the heap properties， in some senses perhaps less stringent there， we didn't have an issue。

 when we wanted to delete something with two children。

 we just promoted the smaller of the two children， assuming we wanted to export and extract min operation。

 Here， we're going to have to work a little harder。 In fact， this is going to be a really neat trick。

 We're going to do something that reduces the case of two children to the previous solved cases of0 or one children。

 So here's the very sneaky way we identify a node to which we' going apply either the K0 or the K 1 operation。

 What we're going to do is we're going to start from K， and we're going to compute K's predecessor。

 Remember， this is the next smallest key in the tree。 So， for example。

 the predecessor of the key 3 is2。 That's the next smallest key in the tree。In general。

 let's call case predecessor L。Now， this might seem complicated we're trying to implement one tree operation namely deletion。

 and all of a sudden we're invoking a different tree operation predecessor。

 which we covered a couple slides ago。 And to some extent you're right。

 delete this is a non-trivial operation。 but it's not quite as bad as you think for the following reason when we compute this predecessor we're actually in the easy case of the predecessor operation conceptually。

 remember how do you compute a predecessor。 Well it depends What does it depend on it depends on whether you've got a non-empty left subtree or not。

 if you don't have a nonempty left subt。 That's when you got to do this thing where you follow parent pointers upward until you find a key which is smaller than where you started。

 but if you've got a left subtree， then it's easy。 you just find the maximum of the left subtre and that's got to be the predecessor And remember finding maximum are easy All you do is follow right child pointers until you can anymore Now what's cool is because we only bother with this predecessor computation in the case or case's node has both children we only have to do it。

In the case where it has a non emptyty left sub。 So really when we say compute case predecessor L。

 all you got to do is follow K's left child。 That's not null because it has both children and then follow right child pointers until you can anymore。

 and that's the predecessor。Now here's the fairly brilliant part of the way you do implement deletion in a search tree。

 which is you swap these two keys， K& L。So for example， in our running search tree。

 instead of this three at the root， we would put a two there， and instead of this two at the leaf。

 we would put a three there。Now the first time you see this， it just strike you as a little crazy。

 maybe even cheating like we're just completely disregarding the rules of search trees and actually it is like check out what happened to our example search tree。

 we swapped the three in the two and this is not a search tree anymore right so we have this three which is in two's left subtree and the three is bigger than the two and that is not allowed that is a violation of the search tree property oops。

 so how can we get away with this we can get away with this because we're going to delete three anyway so we're going to wind up with a search tree at the end of the day。

So we may have messed up the search street property a little bit。

 but we've swapped K into position where it's really easy to get rid of。 Well。

 how did we compute K predecessor L，Ultimately， that was the result of a maximum computation。

 which involves following right child pointers until you get stuck。 And L was the place we got stuck。

 What does it mean to get stuck。 It means L's right child pointer is null。

 It does not have two children， in particular， it does not have a right child。

 Once we swap K's into L's old position。 K now does not have a right child。

 It may or may not have a left child。 In the example on the right。

 It does not have a left child either in its new position， but in general。

 it might have a left child， but it definitely doesn't have a right child because that was a position at which a maximum computation got stuck。

And if we want to delete a node that has only zero or one child。

 well that we know how to do that we covered on the last slide， either you just delete it。

 that's what we do in the running example here。Or in the case where K's new node does have a left child。

 you would do the splice out operation， so you would rip out the node that contains K and the unique child of that node would assume the previous position of that node。



![](img/58b1e09cf16d117f734089fb113201dc_15.png)

Now an exercise which I'm not going to do here， but I strongly encourage you to think through in the privacy of your own home is that fact this deletion operation retains the search tree property。

 so roughly speaking when you do this swap， you can violate the search tree property as we see in this example。

 but all of the violations involve the node you're about to delete。 so once you delete that node。

 there's no other violations of the search tree property， so bingo you're left with a search tree。

The running time， this time no prizes for guessing what it is because it's basically just one of these predecessor computations。

 plus in pointer rewiring， just like predecessor and search。

 it's going to be governed by the height of the tree。

So let me you say a little bit about the final two operations mentioned earlier select and rank so remember select is just the selection problem。

 I'll give you an order statistic like 17 and I want you to return the 17th smallest key in the tree rank is I give you a key value and I want to know how many keys in the tree are less than or equal to that value。

So to implement these operations efficiently， we actually need one small new idea。

 which is to augment binary search trees with additional information at each node。

 So now a search tree will contain not just a key， but also information about the tree itself。

So this idea is often called augmenting your data structure and perhaps the most canonical augmentation of the search tree like these is to keep track of each node not just of a key value。

 but also of the population of tree nodes in the subtree that's rooted there。

So let's call this size of x。Which is the number of tree nodes。And the subree rooted at X。

So to make sure you know what I mean， let me just tell you what the size field should be for each of the five nodes in our running switchtry example。

 So again， remember we're thinking about how many nodes are in the sub rooted and given node or equivalently。

Following child pointers from that node， how many different tree nodes can you reach。

 So from the root， of course， you can reach everybody。 Everybody's in the tree rooted at the roots。

 So the size there is5。 By contrast， if you start at the node1， well。

 you can get to the one or you can follow the right child pointer to get to the two。 So at the one。

 the size would be 2 at the node with the key value 5 for the same reason。

 the size would be2 at the two leaves， the subt rooted at a leaf is just the leaf itself。

 So there the size would be1。There's an easy way to compute the size of a given node once you know the size of its two subtes。

So if a given node in a search tree has children Y and Z。

Then how many nodes are there in the sub rooted at X， Well， there's those that are rooted at Y。

 There are those in the left subt。 There are those that are reachable from Z。

 That is there are the children that are also children of Z， and then there's X itself。



![](img/58b1e09cf16d117f734089fb113201dc_17.png)

Now in general， whenever you augment a data structure and this is something we'll talk about again when we discuss red black trees。

 you got to pay the piper， so the extra data that you maintain。

 it might be useful for speeding up certain operations。

 but whenever you have operations that modify the tree specifically insertion and deletion。

 you have to take care to keep that extra data valid to keep it maintained。Now。

 in the case of these subre sizes， they're quite straightforward to maintain under insertion and deletion without affecting the running time of insertion and deletion very much。

 but that's something you should really think about offline。For example。

 when you perform an insertion， remember how that works， you do essentially a search。

 you follow left and right child pointers down to the bottom of the tree until you had a no pointer then that's where you stick the new node now what you have to do is you have to trace back up that path。

 all of the ancestors of the new node you just inserted and increment their subtree sizes by one。

So let's wrap up this video by showing you how to implement the selection procedure given an order statistic in a search tree that's been augmented so that at every node you know the size of the subte rooted at that node。



![](img/58b1e09cf16d117f734089fb113201dc_19.png)

![](img/58b1e09cf16d117f734089fb113201dc_20.png)

Well， of course， as always， you start at the beginning， which in a search tree is the root。

And let's say the route has sub childrenildren Y and Z。Y or Z could be null， that's no problem。

 We just think of the size of a null node as being zero。Now what's the search tree property。

 It says every the keys that are less than the keys stored at x are precisely the ones that are in the left subtree at x。

 the keys in the tree that are bigger than the key at x are precisely the ones you're going to find in x's right subtree So suppose we're asked to find the 17th order statistic in a search tree the 17th smallest key that's stored in the tree where is it going to be which where should we look Well it's going to depend on the structure of the tree and in fact it's going to depend on the subtree sizes。

 This is exactly while we're keeping track of them so we can quickly make decisions about how to navigate through the tree。

 So for a simple example， suppose that x's left subtree contains say 25 keys。

 So remember y knows locally exactly what the population of the subtree is So in constant time from x we can figure out how many keys are in Y subt and let's say it's 25 Now by the defining property of search trees these are the 25 smallest keys anywhere in the tree。

Right， X is bigger than all of them。 Everything in x's right subt is bigger than all of them。

 So the 25 smallest order statistics are all in the subte rooted at Y。 Clearly。

 that's where we should recurse。 Clearly that's where the answer lies。

 So we can recurse on the subre rooted at Y。 and then we are again looking for the 17th order statistic in this new smaller search tree。

 On the other hand， suppose when we start at x。 and we look。

 we ask why how many nodes are there in your subte。 and maybe Y locally has stored the number 12。

 So there's only 12 things in x' is left subte。 Well， okay X itself is bigger than all of them。

 So that's going to x is going to be the 13th biggest order statistic。

It's going to be the 13th biggest element in the tree。 Everything else is in the right subte。

 So in particular， the 17th order statistic is going to be in the right subtree。

 So we're going to recursse in the right subtree。 Now， what are we looking for。

 we're not looking for the 17th order statistic anymore。

 The 12 smallest things are all anex subtree X itself is the 13th smallest。

 So we're looking for the fourth smallest of what remains。

 So the recursion is very much along the lines of what we did in the divide and conquer selection algorithms earlier in the course。

So to fill in some more details， let's let a denote the subte size。At why。

And if it happens that x has no left child， we'll define a to be zero。

So the super lucky case is when there's exactly I minus1 nodes in the left subte。

 that means the root here， x is itself the Ih order statistic remember it's bigger than everything and it's left subte。

 it's smaller than everything in its' right subt。But in the general case。

 we're going to be recursing either on the left subte or on the right subtree。

 we recurse on the left subte when its population is large enough that we're guaranteed it encompasses the I over statistic。

 and that happens exactly when its size is at least I。

 that's because the left subt has the smallest keys that are anywhere in the search tree。



![](img/58b1e09cf16d117f734089fb113201dc_22.png)

And in the final case， when the left subree is so small that not only does it not contain the Ih order statistic。

 but also x is too small to be the Ih order statistic， then we recurse on the right subtree。

 knowing that we've thrown away a plus one， the a plus one's smallest key values anywhere in the original tree。

So correctness of this procedure is pretty much exactly the same as the inductive correctness for the selection algorithms we discussed earlier in effect the root of the search tree is acting as a pivot element with everything in the left subtree being less than the root everything in the right subtree being greater than the element in the root so that's why the recursion is correct as far as the running time I hope it's evident from the pseudocode that we do constant time each time we recur how many times can we recurs when we keep moving down the tree the maximum number of times we can move down the tree is proportional to the height of the tree so this again is proportional to the height。

So that's the select operation， there is an analogous way to write the rank operation。

 remember this is where you're given a key value and you want to count up the number of stored keys that are less than or equal to that target value。

 again you use these augmented search trees and again you can get running time proportional to the height and I encourage you to think through the details of how you implement rank offline。

