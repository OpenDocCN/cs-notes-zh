# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P33：5 - Fall 2022 Discussion 7 Question 4.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/44569375c7de458942dcebb3a6b9a924_0.png)

![](img/44569375c7de458942dcebb3a6b9a924_1.png)

All right on to question four which is about BST asymptotics we want to know the runtime for find on a perfectly bushy BST in terms of n the number of nodes in the tree and we're wondering if we can generalize the runtime to a tight bound okay and what we mean by type bound is can we use the big theta bound to describe the runtime for find okay so over here we see that find is defined with like a tree that it takes in right the root of a tree that it takes in sorry and a key S so this is a recursive function that basically stops when tree is nu which means we've gone through the whole tree right？

And fine basically works by comparing。The key SK to the trees key okay so basically if SK is equivalent to the tree's key's value。

 then we just return the tree because we know that we found the the element at the root of the tree right otherwise we want to make some comparisons so if the value of SK is less than the value of the tree's key。

 that means that we know that if we there is the value SK in our tree。

 then it must be in the current tree left subchild right because we established by the invariance of a BST。

That all nodes left of the root of a BST must have values less than that root right so we're basically going to recursively search the left subchild of the tree rooted at the pastin tree until we find or don't find our value right and then similarly we want to do a comparison actually this is like with an else case but the else case implies that if SK is greater than the tree's key value than we move on to the right subchild of the tree and try to find it there okay so for a reminder a perfectly bushy BST is basically a BST that has its keys distributed in such a way such that each node has approximately two children if it's not a leaf right？

So it looked like this nice little pyramid so to have like the root and then the root has two children and those children have two children and so on and so forth that's like a nice perfectly bushy PST。

So if you recall like maybe you like remember it like directly from the slides。

 but like we've been talking a lot about like recursive trees and stuff in like question three even right so if you remember that like the branching factor of the BST is2 right that means that we can basically get top to bottom or you can think about it in terms of like the levels of the tree。

 there are log base two of n levels in our BST our bushy BST right because it's like if we can kind of think about it like let's say n was seven。

 there's seven nodes in the tree， if we had our seven nodes。😊。

Distributed in the way like I described like there's the root and then that has two children and those children have two children each then we would to get a tree of approximately height a log n okay so now let's think about the runtime of find though because it's log n but is it a tight bound so we know that find is going to stop once it either reaches the end of the tree right we've reached a leaf and then we can't find anything anymore or we've actually found the element。

In our tree right， so basically that means that find has the possibility of stopping early。

 It doesn't necessarily go through the entire tree to like look for an element right and the good example a good example of this would be。

 let's say like。Let's say that our key was five and the root of our tree was five that means the moment that we pass in find on the tree root at five and key as five if we make that comparison to the tree's key we immediately return right because we know we already found it because it was the root so lucky for us that takes constant time right and friendly reminder that。

Best case and worst case are not necessarily based on the number of nodes in or it's not necessarily based on the input size so in this case it would be the number of the input size will be the number of nodes in our tree right well notice here that no matter how big our tree is it gonna have like a zillion nodes right it doesn't matter in the best case because then because in the best case it's not based on the input size it's based on whether or not we pass in the roots value the roots key because if we pass in the roots key then it's like over we don't have to make any comparisons right so we know that this function fine is going to be lower bounded by。

Constant time which is when we find the root we call fine on the root of the tree right alternatively on the other hand。

 we could have in the worst case scenario we could have log n time right and so the worst case scenario which take place is if there's one of two cases so number one the key that you're trying to find is actually not in the tree in which case you would get all the way through the tree to a leaf and then you'd get to this case over here if tree is no return all and you'd realize that okay my value wasn't even in the tree but in that case you traverse the entire path from root to leaf right which takes approximately log n time and similarly the other case is it's in the tree but it's a leaf so once again you would have to traverse the path from root to leaf which takes log n time。

And because of that we know that find is going to be lower bounded by constant time and it's going to be upper bounded by log sorry it's going to be lower bounded by constant time and it's going to be upper bounded by log end time okay so now when we're trying to generalize to a tight bound remember that we can only use big theta notation to describe the run time of a function if it is lower and upper bounded by the same function but clearly we see here that it's not because the lower bound is constant and the upper bound is log n so we cannot define a tight bound or like an average case for it all right and we would say that because we can't define a type bound for it we usually go with big O like of the tightest bound that we can possibly find。

Now using the same implementation of find in what order should we insert the keys 625。

90 and negative3 to the BST such that the runtime of a single find operation after all keys are inserted is linear or like O of n and we want to draw out the resulting BST so if you remember from the slides。

Or the content review BSTs can be bushy or they can be spininly， right。

 so we just talked about the bushy case in which the height of the tree was login， right？

And here in the spindley case， the find operation might take linear time， right。

 which basically means that we're traversing through essentially all the nodes that are in the tree before like being able to return something conclusive right either we return the value or we return null。

So now we have to come up with a spin leaf tree based on these keys because insertion order does matter in the BST right so if you think about how insertion happens in the BST so all insertions get inserted as as sorry as a leaf that essentially means。

那嗯。Anytime we have like our BST and we want to insert some key into it our key has to like make it through comparisons of the BST and through all its children until it gets to like the relevant position but as a leaf node right it's not going to replace a node in the middle of the tree so we know it's always going to like have to make it through the bottom right so in this case。

Since we want the fine operation to be linear in the worst time right like once again。

 like it's still has going it's still going to have the constant time best case in which oh you just called find on the root of the BST。

 but in the very worst case we want it to take a linear time。

 which means we have to go through all the nodes， which means that。😡。

The the look of our BST should be relatively linear and if we go back to the idea of inserting everything as a leaf and making all these comparisons。

 the easiest way to achieve a spinly tree would to be inserting the keys in either ascending or descending sorted order so here's what I mean by that here I did the ascending tree but basically if you think about sorting this entire array we would get negative 30256 and9 and so we would try to insert negative3 okay so we insert negative3 that's the root there's nothing in our tree yes that's fine。

😊，Then we try to insert zero， okay？So we're going to insert zero。

 we're going to make a comparison with negative3， we're going to say is zero less than or greater than negative3。

 it's greater than okay， so we're going to make it the right child of three negative three sorry。

Then we tried to insert two we're gonna make a comparison is two less than or greater than negative3 it's greater let's move on is two less than or greater than zero it's greater let's move on and then so now we're going to add two as the right child of zero and so on and so forth right so once we get once we put all our keys together in a sending order it's basically traversing the whole path every single time right because it's just like not very nicely inserted in a way that we can get a bushy tree so any time that we want to insert we're effectively appending。

😊，A leaf to this like long trail or like this long chain of linear nodes right so this like looks like a bit of a linked list。

 So now if I say that I wanted to find like 10 or something like that right I would do that same like comparison So I'd start here it'd say it's 10 greater than or less than negative3 it's greater than move on greater than or less than zero it's greater than move on greater than or less than two it's greater move on so on and so forth and so on and so forth and you'll see that if we try to call find on 10。

 it's not in the tree but we had to go through this entire like chain of nodes in the tree right in order to find out that there wasn't a 10 and that's why sorting your keys and then inserting them in either ascending or descending order is going to give you a spinlay tree that gives a worst case runtime of linear for a single find operation okay。



![](img/44569375c7de458942dcebb3a6b9a924_3.png)

And that's it。