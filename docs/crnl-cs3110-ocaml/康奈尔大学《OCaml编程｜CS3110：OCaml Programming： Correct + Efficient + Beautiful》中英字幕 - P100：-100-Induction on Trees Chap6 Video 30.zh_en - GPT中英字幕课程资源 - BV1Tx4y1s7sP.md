# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P100：-100-Induction on Trees Chap6 Video 30.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've seen how to do induction on natural numbers and on lists。

 but how about more complicated variants Well， sure you can do induction with those as well。

Let's see how to do it for trees so remember that a binary tree as we coat it up here is really not so different from a list。

 it just carries one additional piece along with it instead of a list which carries one sublist binary tree carries two subtrees that's all there is different。

The format for an inductive proof on trees is therefore really similar to that for lists or natural numbers。

So suppose you want to prove that a property P holds of all trees tea。

And you want to do it by induction on T。Well first off。

 there's a base case that's where tea is the smallest possible tree In this case that's leaf because that's what's representing the empty tree here。

 just like for lists， we had a smallest possible list which was nil and for natural numbers。

 we had the smallest natural number， which was0。So we need to prove that the property P holds when instanttive on that smallest value。

 in this case leaf。We also have an inductive case， in this case， the tree is bigger。In fact。

 it's one bigger than something before it。 so just like we had a successor of a natural number or we had a list where we cons something onto the beginning。

 here we have a tree that we formed out of two smaller trees。In this case。

 it has to be too because we're talking about binary trees。So， we've got a node。

That has a left subte and a right subt as well as a value carried at that。

And we're going to try to show that that property P holds of that bigger tree constructed with node。

And what's different from before is we get two inductive hypotheses。

 We actually get to instantiate the property P on both of the smaller values of the type。😡。

Now this never happened before because we only had one smaller value of the type。

 we had one natural number， or we had one smaller list in the tail。

So here we've got a left subtree and a right subtree。

 so we get to assume that the property P holds of both the left and the right subtrees。

Let's do an example of this。By computing the number of leaves and nodes in a tree。

So the number of nodes in the tree is going to just be the number of times we encounter a node constructor if we walk over the tree。

The number of leaves in the tree is going to be the number of times we find a leaf constructor。

 so the leaves are all going to be at the bottom， the nodes are all going to be in the middle and at the top。

So the claim that I want to show here， and maybe it's not obvious。

 is that the number of leaves in a tree is one more than the number of nodes in a tree。In fact。

 if you want to pause and just draw out some trees。

 you might convince yourself that holds on some examples。But how do we prove it rigorously？



![](img/7fb884aac57d1095fc274e325fc7845f_1.png)

I've started my proof here， we're going to show that the number of leaves is equal to the one plus the number of nodes and we're going to do it by induction。

Okay， so I've set up my base case here， I'm trying to show that the number of leaves in leaf is one more than the number of nodes in leaf。

Okay， this one will be easy。

![](img/7fb884aac57d1095fc274e325fc7845f_3.png)

We know that leaves when applied to leaf pattern matches and returns one。

 so I get to take that step of evaluation to one there。



![](img/7fb884aac57d1095fc274e325fc7845f_5.png)

And we know that nodes when applied to leaf is going to return zero， we can see that right up here。

 if pattern matches return zero in the case of leaf。



![](img/7fb884aac57d1095fc274e325fc7845f_7.png)

![](img/7fb884aac57d1095fc274e325fc7845f_8.png)

So now we just have one tiny little bookkeeping thing to do by algebra， of course， that's one。

 and so we've reached the same value on both sides， we've shown what we need to show。

Let's do the inductive k。Okay， that took a little bit of work to set up。

 but it's always worthwhile to do that work to keep us on track in an inductive proof like this。



![](img/7fb884aac57d1095fc274e325fc7845f_10.png)

So we have two inductive hypotheses， I could name them one and two if you like to disambiguate them。

 I could also name them maybe L and R to show that I'm instantiated on the left and right subte。

 I kind of like that。And I want to show that the number of leaves in that bigger tree is one plus the number of nodes in that bigger tree。

 but I get to assume that that's true for both of the smaller trees right so the number of leaves in the left-hand subre is one plus the number of nodes in the lefthand subt and the same for the righthand subree。



![](img/7fb884aac57d1095fc274e325fc7845f_12.png)

Okay， so now I can start in on this proof block。So we get to take one step of evaluation here because I know that leaves is going to pattern match against node。

And when it finds a node constructor， it's going to recurse on the left and right hand subtes and return the sum of those。

So I've got leaves L plus leaves R。ANow look at what that lines up with in my inductive hypotheses。

 I know what leaves L is equal to， I know what leaves R is equal to so I can use both of those。Okay。

 but that's about as far as I can take this， I can't simplify this any further。

 let me start working on the right hand side。I was able to take one step of evaluation because I know what nodes is going to do when applied to a node constructor。



![](img/7fb884aac57d1095fc274e325fc7845f_14.png)

Its right up here， it returns one plus the number of nodes in the subtrees。

 so that pattern match can happen。

![](img/7fb884aac57d1095fc274e325fc7845f_16.png)

And back down at the bottom， that means I've got one plus。

 so that's the first one plus there on here。One plus。

 so that's from the evaluation of nodes and then the results of those recursive calls。Now， of course。

 I can simplify that and be done。And that finishes my proof that the number of leaves in a tree is one plus the number of nodes in the tree。



![](img/7fb884aac57d1095fc274e325fc7845f_18.png)