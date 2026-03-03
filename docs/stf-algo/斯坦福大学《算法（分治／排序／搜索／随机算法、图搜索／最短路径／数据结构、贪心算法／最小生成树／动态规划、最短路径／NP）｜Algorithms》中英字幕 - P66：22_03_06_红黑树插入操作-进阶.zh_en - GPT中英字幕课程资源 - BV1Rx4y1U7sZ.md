# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P66：22_03_06_红黑树插入操作-进阶.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

For this final video on binary search trees， I want to talk a little bit about implementation implementation details for the red black tree data structure in particular。

 the insertion operation。 As I've said in the past。

 it really doesn't make sense for me to spell out all of the gory details about how this is implemented if you want to understand them in full detail。

 you should check out various demonstrations readily available on the web or comprehensive textbook or an open source implementation。



![](img/33522144b18b58bdb3c3517d1911fb18_1.png)

Red black trees， you'll recall， satisfy foreign invaris， and the final two invaris in particular。

 ensure that the red black tree always has logarithmic height。 and therefore。

 all of the supported operations run in logarithmic time。

 The problem is we've got to pay the piper whenever we have an operation that modifies the data structure。

 it potentially destroys one or more of the invariance。

 and we have to then restore that invariance without doing too much work。 Now。

 amongst all of the supported operations， there are only two that modify the data structure insertion and deletion。

So from 30000 feet， the approach to implementing insert certain and delete is to just implement them as if it's a normal binary search trees。

 If we didn't have to worry about these invariants。 And then if an invariant is broken。

 we try to fix it with minimal work。 And the two tools that we have at our disposal to trying to restore an invariant are。

 first of all， Recoling， flipping the color of nodes from red to black。 And second of all。

 left and right rotations， as covered in the previous video。

My plan is to discuss the insertion operation， not in full detail。

 but I'll tell you about all of the key ideas。 Now， deletion。

 you got to remember that even in a regular binary fridge tree， deletion is not that trivial。

 And in a red black tree， it's downright painful。 So that I'm not going to discuss。

 I'll defer you to textbooks or online resources to learn more about deletion。

So here's how insert is going to work so suppose we have some new node with the key X and we're inserting it into a red black tree。

 so we first just forget about the invariance and we insert it as usual and remember that's easy all we do is follow left and right child pointers until we fall off the end of the tree until we get to a no pointer and we install this new node with key X where we fell off the tree that makes X a leaf in this binary search tree。

Let's let Y denote Xu's parent after it gets inserted。Now， in a red black tree。

 every node has a color。 It's either red or black。 So we have a decision to make。

 We just added this new node with key X。 and we' got to make it either red or black。

And we sort of between a rock and a hard place， whichever color we make it。

 we have the potential of destroying one of the invariants。 specifically， suppose we color it red。

 Well， remember what the third invariant says， it says you cannot have two reds in a row。

 So if Y X's new parent is already read， then when we color X red。

 we have two reds in a row and we've broken invariant number 3。On the other hand。

 if we color this new node X black， we've introduced a new black node to certain root null paths in this tree。

 and remember the fourth invariant insists that all of the root null paths have exactly the same number of black nodes。

 so by adding a black node to some but not all of the paths。

 we're in general going to destroy that invariant， if we color X black。

So what we're going to do is we're going to choose the lesser of two evils。 and in this context。

 the lesser of two evils is to color X， red。 Again， we might destroy the third invariant。

 We'll just deal with the consequences later。So why you ask。

 is coloring X red and destroying the third invariant the lesser of two evils。 Well， intuitively。

 it's because this invariant violation is local。 The flaw in our not quite red black tree is small and manageable。

 It's just a single double red。 And we know exactly where it is。 It's X and Y。

 So there's sort of more hope in squashing it with minimal work。 By contrast， if we colored X black。

 Then we've violated this much more global type of property involving all of the rootutinal paths。

 And that's a much more intimidating violation to try to fix than just this local one of having a double red between X and its parent。

Indeed， some of the time we'll just get lucky， and it will just so happen that X's parent Y is colored black。

 And then we're golden。 This new node X that's colored red。 It doesn't create a double red。

 There's no other violation to the other invariance。 And so boom， we've got a new red black tree。

 and we can stop。So the tricky case then is when X's parent Y is also red。 In this case。

 we do not have a red black tree。 We have a double red。

 and we have to do some more work to restore the third invariant。So suppose Y is red。

 What do we then know， Well， remember， before we inserted X， we had a red black tree。

 All four of the invaris were satisfied。 So therefore， y， by virtue of being red。

 it could not have been the root。 It has to have a parent。 let's call that parent W。 Moreover。

 by the third invariant， there was no double red in this tree before we inserted X。

 So by virtue of Y being red， its parent W must have been black。

So now the insertion operation branches into two different cases。

 and it depends on the color on the status of W's other child。 So in the first case。

 we're going to assume that W's other child that is not Y。

 but the other child of W exists and is colored red in the second case。

 we're going to treat when W either doesn't have a second child。

 Y is its only child or when its other child is colored black。So let's recap where things stand。

 So we just inserted this new node and it has the key X。 and our algorithm colored this node red。

 So X is definitely red。 Now， if it's parent Y was black， we already halted。

 So we've already dealt with that case。 So now we're assuming that Y X's parent is also red。

 That's what's interesting。 Now， by virtue of Y being red。

 we know that Y parent that is X's grandparent W has to be colored black And for case 2 of insertion。

 we are assuming that W has a second child colored Z and that Z is colored red。

So how are we going to quash this double red problem， We again， we have two tools at our disposal。

 One is to recolor nodes。 The second is to do rotations。 So for case1。

 we're only going to actually have to do recolor it。

 we're not even going to have to bust out our rotations。In particular。

 what we're going to do is we're going to recolor Z and Y black and we're going to recolor W red。

 so in some sense we take the reds that are Z and Y and we consolidate them at W。

The important property of this reoring is that it does not break the fourth invariant。 Remember。

 the fourth invariant says that no matter which path you take from the root to a null pointer。

 you see exactly the same number of black nodes。 So y is that invariant still true after this reing。

 Well， for any path from a root to a nu pointer， which doesn't go through the vertex W。

 it's irrelevant。 None of these nodes are on that path。

 So the number of black nodes is exactly the same。 So think about a path which does go through W。

 Well， if it goes through W to get to a nu pointer， it has to go through exactly one of Z or Y。

 So before we did the reing， this path picked up a black node via W。

 and it did not pick up a black node via Z or Y。 Both of those were red。 Now。

 any such path does not pick up a black nodeed W， that's now red。

 but it does pick up exactly one black node， either Z or Y。 So for every single path in the tree。

 the number of black nodes it contains is exactly the same before or after this reing。Therefore。

 since the fourth invariant held previously， it also holds after this recrate。

The other great thing is that it seems like we've made progress on restoring the third invari。

 the property that we don't want any double reds at all in the entire tree。 Remember。

 before we did this reing， we only had a single double red。 It involved X and Y。

 We just recoled Y from red to black。 So certainly， we no longer have a double red involving X and Y。

 And that was the only one in the tree。😊，So are we done， do we now have a bona fide red black tree？

Well， the answer depends， and it depends on the color of W's parent。 So remember。

 W just got recolored from black to red。 So there's now a possibility that W being this new red node participates in some new double red violation。

 Now， W's children， Z and Y are black。 So those certainly can't be double reds。

 So W also has some parent。 And if W's parent is red。

 then we get a double red involving W and its parent。 Of course， if W's parent was black。

 then we're good to go。 we don't get a double red by recoling double W red。

 So we have no double reds in the tree， and we can just stop。

Summarizing this recoloring preserves the fourth invariant。

 and either it restores the third invariant， or if it fails to restore the third invariant。

 at least it propagates the double red violation upward into the tree closer to the root。

We're perfectly happy with the progress represented by propagating the double red upward。 why， well。

 before we inserted this new object X， we had a red black tree。

 and we know red black trees have logarithmic height。

 So the number of times that you can propagate this double red upward is bounded above by the height of the tree。

 which is only logarithmic。 So we can only visit case 1。

 a logarithmic number of times before this double root is propagated all the way to the top of the tree all the way to the root。

😊，So we're not quite done。 The one final detail is what happens when this recoling procedure actually recolours the root。

 So you could， for example， look at this green picture on the right of this slide and ask， well。

 what if W is actually the root of this red black tree and we just recoled it red。 Now。

 notice in that situation where the we're dealing with the root of the tree。

 we're not going to have a double red problem。 So invariant 3 is indeed restored when we get to the top of the tree。

 but we have a violation of invariant number 2， which states that the root must always be black。Well。

 if we find ourselves in this situation， there's actually a super simple fix， which is this red root。

 we just recolor it black。Now， clearly that's not going to introduce any new double reds。

 The worry is that instead it breaks invariant4， but the special property of the root vertex is that it alllies exactly once on every rootutinal path。

 so if we flip the color of the root from red to black。

 it increases the number of black nodes on every single rootutinal path by exactly one。

 so if they all have the same number of black nodes before they all have the same number of black nodes now after the reoring that completes case one of how insertion works。

Let's move on to case 2。 So case 2 gets triggered when we have a double red and the deeper node of this double red pair call it X。

 It's uncle。 That is if it has grandparent W parent Y。 and W's other child other than why。

 either doesn't exist or if it exists， it's labeled It's colored black。 That is case 2。

 I want to emphasize， you might find yourself in case 2 right away when you insert this new object X。

 It might be that immediately， it has some uncle， which is colored X。

 or it might be that you've already visited case 1 a bunch of times。

 propagating this double red up the tree。 And now at some point。

 the deeper red node X has a black uncle。 Either way， as soon as that happens， you trigger case 2。

Well， it turns out case2 is great in the sense that with merely constant work。

 you can restore invariant number3， you can get rid of the double red without breaking any of the other invariants。

 You do have to put to use both of the tools we have available in general。

 both recolings and rotations， left and right rotations， as we discussed in the previous video。

 But if you do just a constant number of each recolings and rotations。

 you can get all four of the invariantss simultaneously。



![](img/33522144b18b58bdb3c3517d1911fb18_3.png)

There are unfortunately a couple of subcases depending on exactly the relationships between X， Y。

 Z and W for that reason I'm not going to spell out all the details here。

 check out a textbook if you're interested or even better work it out for yourself now that I've told you that two to three rotations plus some re colorings is always sufficient in case2 to restore all of the invariance。

 follow your nose and figure out how it can be done。

So let's summarize everything that weve said about how insertion works in a red black tree。

 So you have your new node with key X。 You insert it as usual。 So you make it a leaf。

 You tentatively color it red。 If itss parent is black， you're done。

 You have a red black tree and you can stop And general。

 the interesting case is this new node X is parent is red that gives you a double red a violation of invariant 3。

 Now， what happens is you visit this case1 propagating this double red upward in the tree。

 This upward propagation process can terminate in one of three ways。 First of all。

 you might get lucky， and at some point， the double red doesn't propagate。

 you do the recoling in case1， and it just so happens you don't get a new double red。 At that point。

 you have a red black tree and you can stop。 The second thing that can happen is the double red propagation can make it all the way to the root of the tree。

 Then you can just recolor the root black and you can stop with all of the invariant satisfied。

Alternativelyly， at some point when you're doing this upward propagation。

 you might find yourself in case 2， as discussed on this slide where the。

red note in your double red pair X has a black or nonexistent uncle Z。 In that case。

 with constant time， you can restore all of the four invaris。

 So the work done overall is dominated by the number of double red propagations you might have to do。

 that's bounded by the height of this tree and that's bounded by big O of logan。

 So in all of the cases you restore all four invariance。 you do only a logarithmic amount of work。

 So that gives you a logarithmic insertion operation。 four red black trees as promised。

