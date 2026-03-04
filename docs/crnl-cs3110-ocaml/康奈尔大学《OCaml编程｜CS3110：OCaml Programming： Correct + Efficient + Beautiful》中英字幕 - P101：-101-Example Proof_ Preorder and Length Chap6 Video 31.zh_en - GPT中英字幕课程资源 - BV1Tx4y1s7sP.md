# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P101：-101-Example Proof_ Preorder and Length Chap6 Video 31.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

As another example of how to do induction with trees。Let's prove this claim。

It's something to do with the preorder of a tree， so remember first off what the preorder traversal of a tree means。

 it means you visit the value of the node， then visit all of the left children and then visit all the right children。

Okay， so the claim here is that the length of the list produced by this preordered traversal is going to be the size of the tree and what's the size of the tree。

 well it's the number of nodes in it， so this is the same function as our nodes function that we just looked at。

 I've just named it something different here to be a little more suggestive of what it means。Okay。

 so the length of the preorder traversal of a tree is the size of the tree that makes sense。

 the list that you produce by traversing it is going to have the same number of elements in it as the tree does itself。



![](img/97eed5ca434bd60b21f8f152db75c673_1.png)

Let's prove that by induction。I've started off by putting the code in here as well as what the claim that we want to approve。

 let's start the proof。It just occurred to me as I was writing this that maybe all along it could have been bothering you because I have this equality here and maybe that's a little hard to parse as I'm writing these proofs。

 I'm used to reading this， it doesn't bother me， I know that I'm defining P here to be the expression on the righthand side。

 but if that bothers you you could always write something like this just to say that that's what P of T is I've even seen some people write it like this to say defined as it doesn't really bother me any that you want to write that。

Okay， let's set up the base case now。I imagine you know exactly how this is going to go based on the proofs that we've done with lists and trees already。

Okay， so the base case is really easy， we get to take one step of evaluation of pre order leaf because we know that preor when applied to leaf is going to return the empty list。

So that means we have the length of the empty list。And what is that， well。

 you remember the code for the length function I didn't write it in the file here。

 but what is length do when it's passed an empty list， the nil。

 it pattern matches against Nil and returns。So we've got zero there。Now， of course。

 the right hand side is easy to take care of as well。Because we know that size pattern matches。



![](img/97eed5ca434bd60b21f8f152db75c673_3.png)

We have that up here。 And when it finds a leaf， it returns 0。



![](img/97eed5ca434bd60b21f8f152db75c673_5.png)

Okay， so that establishes the base case， next let's do the inductive case。

OkayWe've done the bookkeeping here to set up what we want to show and what our inductive hypotheses are。

 this is important to keep us from making mistakes as we go further through the proof。

Now let's launch in on showing that the left hand side here does equal to right hand。

The first thing I can do is take one step of evaluation， and that's because preorder。

 when it's applied to a node constructor， we know exactly what it's going to do。

 it's going to return the value V append preorder L， append preorder R。So that's what I have here。

So at first it might seem like we're a little stuckier。

 there isn't really another step of evaluation we can take with preor L or pre-order R。

 the inductive hypothesis isn't able to be applied to either of those yet， and length。

 well we don't exactly have what looks like a cons operator or a nil going on here。

 so it's hard to see what to do with it。For a little clever， though， we can make progress。

 Remember how we prove that length distributes over the append operator。

We showed that in another proof already， in fact。Here it was just to remind us of that。

 we showed that the length of x's append Y is the same as length x's plus length y。Now， of course。

 that was for two lists appended together。But we can think of this in exactly that way as being the list V appended together with some other bigger list。

 which involves preorders。So， let's use that lemma。And simplify the expression we have here。



![](img/97eed5ca434bd60b21f8f152db75c673_7.png)

And now I can do the same thing over again with this list， well， two lists， actually， pre orderder L。

 append preor R， and distribute length over those。Now I'm at a point where I can use the inductive hypotheses because both of them apply to one particular sub expressionpression that I've got here。

 length of preorder L。And length of preorder are。And finally。

 what do I know about the length of the list V Well， of course。

 really that syntactic sugar for V cons nil。And of course。

 I know what length is going to do by taking two steps of evaluation there。

 it's going to return one plus the length of the empty list and the length of the empty list is going to be zero。

So that's just going to be one。And that's as simple as I can make the left hand side of what I wanted to show here。

 so let's work on the right hand side。Actually， that was really simple and quick。

 We know what size is going to do when applied to the node constructor。

The pattern matches and returns one plus the size of the two subtes。



![](img/97eed5ca434bd60b21f8f152db75c673_9.png)

And so that's what I have here。1 plus the size of L plus the size of R。

 And now I have gotten both sides of what I wanted to show to be the same expression。

 So I am done with that inductive case， Q， E D。

![](img/97eed5ca434bd60b21f8f152db75c673_11.png)

And I've now shown that the length of the preorder traversal of a tree is the same as the size of the tree。



![](img/97eed5ca434bd60b21f8f152db75c673_13.png)