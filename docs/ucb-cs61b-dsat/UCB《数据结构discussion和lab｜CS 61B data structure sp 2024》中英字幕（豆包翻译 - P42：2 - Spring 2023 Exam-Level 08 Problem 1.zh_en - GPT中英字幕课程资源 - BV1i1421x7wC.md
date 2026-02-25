# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P42：2 - Spring 2023 Exam-Level 08 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/5b98b5c43444c74f1a857df8f80fa0b0_0.png)

Everyone， this is Sherry and this is the spring 2023 exam level 8 walkthrough in this video I'll be going over problem one LRB insertions。

This to start off I do have a little bit of a cough。

 luckily viruses are not contagious over the internet， so just bear with me in case I start coughing。

Because i'm too lazy to edit out all the costs but yeah so in this problem we'll be just inserting some things into an LRB and then looking at the relationship of this LRB with a two three tree so before we get started there are three operations that we need to know that allow LRB to maintain their nice balance properties so。

The three operations are rotate left， rotate right， and color flip。So。

In order to maintain our allRB invariance there are kind of three violations we can have and then within those violations there are three ways to fix each of those violations so the first is if we have a right red link and just by the way i'll be using a schoooggly line to represent a red link and I recommend you use this technique on exams because it can take a lot of time to switch colors between different pens and things like that。

So if we have a right red link， it's not a left leaning tree。

 so what we do is we rotate left on a and one trick that I like to think about when rotating left is I push up the child and I combine them into like a temporary node。

And then I push down whichever node I was rotating on so in this case I was rotating left on a。

 so I'm going to push down a and I'm going to make it the left child of B and then the children are still the same。

So this is going to have child。C， because B's left child is now replaced and then D is still going to be at the right of B。

And this is how we maintain the invariant that all red links are left leaning。

The other thing is that we can't have two consecutive left links red links。

 so if we look here we have two consecutive red links in a row so in this case we will rotate right on a and again what this looks like is now I'm going to push up the I'm going to combine these into the temporary node。

😊，D and C， and then I'm going to push down whichever node I'm rotating right on。

 which is in this case is a， so B is going to have a right child of A and then it's still going to have its left child D and then since we just replaced B's left child we'll make it the right child the left child of A。

And then finally， as you might have seen here， we cant also cannot have two red children of a single node。

 so the way we fix that is we color flip on that node， so here a has two red children so。

The color flip we change all the colors of the links leading into it。

 and so all of these two red links become black。And this link becomes red。

And those are the three operations that we need to know in order to insert into LLRBs。So with that。

 let's just jump into the problem and here we do a couple different things。

 we do a couple insertions and then we're going to convert it into a two，3 tree。Okay。So。😊。

What we're going to do is first， let's draw the current state of our tree。

Which is like this and so right now we only have one red link。

So the first thing we're going to do is we're going to insert seven and what's that going to look like well we're going to find the correct place to insert7 first of all。

 and then we're going to do the LLRB operations to make sure our tree is still balanced and a proper LLRB afterwards。

So if we insert seven， we notice that it should go to the right of five but to the left of nine。

 so what we're going to do is we're going to put seven there and this actually doesn't cause any violations。

 so we're good。The next thing we're going to do is we're going to insert six and in this case。

 six is going to go to the right of five。And it's going to go to the left of nine。

 and it's going to go to the left of seven。And in this case。

 there is actually a violation because now we have two red links in a row。

 so what we need to do is we need to rotate right on seven so that we no longer have this violation so what that's going to look like is now I'm going to end up with a tree like this。

After I rotated。And then now again I have another violation。

 which is that seven has two red children， so I need to perform a color flip。

 so I'm going to do that， so this note is going to become red and these two links are going to become black and then now I have another violation。

 which is that now five has two red children signed a color flip on that。And so after inserting six。

 I have this tree and there are actually no red links in this tree。

 so the LLRB and the B tree are the same， that's just a side note to think about。😊，Okay。

 next I'm going to insert two。And where's two going to go。

 well two is going to go to the left of five， the left of three， and to the right of one。

In in this case， we do have violation because we can't have a right leaning red node red link。

 so what we're going to do is we're going to rotate left on two。

And that's going to give us this and in that case， this is valid now because it's a left leaning red link and we don't have any other violations so we can move on。

Next we're going to insert eight and when we insert eight。

 that's going to go to the left of nine and that actually doesn't cause any violations so we can just move on。

The next thing we do is we insert 8。5 and so 8。5 is right between 8 to9。

 so it's actually going to go to the right of eight。😊，And in this case。

 we start off with a violation， which is that there's a right leaning red link。

 so we need to rotate left on this。And this is going to become 8。5 and8。

Now we have another violation which is that we have two red links in a row so what we need to do is need to rotate right on nine and so let's do that so 8。

5 is going to end up here8 is going to be here9 is going to be here and now we have another violation because 8。

5 has two red children so we need to color flip on 8。

5 so all of these links are going to change color this one's going red these two are going become black。

And now we still have a violation， which is that seven has a right red child。

 so we we need to do is we going to rotate left on seven。

And since this is a bigger rotation operation， I'm going to write the temporary node where I push up 8。

5。And。Then I'm going to push down seven because I'm rotating left on seven。

 so what that's going to look like is 8。576。诶。And then。

This is going to have its right child eight and this is going to have the right child neck。

And of course we have to maintain this red link between 7 and 8。5 so this is going to look like this。

 so that's what it's going to look like after the entire left rotation so I'm going to clear this out and replace it with the left rotated version。

ooops诶。And that is it for a tree。And so the final state of our is going to look like this。

And there are no more violations at this point， so we're good to move on because although there's only left leaning red links and there no there's only one red link so there's no two red links in a row and we don't have any two red children。

So the next part of this problem asks us to convert this LRB into a23 tree so the way we do that is we just draw the exact same tree except for any red links。

 we kind of smush them into a single node， so what that looks like is all of these are going to be normal。

 but seven and 8。5 are going to be a single node and they're going to have three children because there's two items of the node so it has to have three children and then same for this node here which is going to have one and two together。

And that's the corresponding23 tree and that's it for this problem so here's the weekly exam tip for LLRB problems just remember these three violations and how to fix each of them and you should be able to do most LLRB problems just keeping these three violations in mind good luck in this good luck in this week and the rest of 60B and feel free to leave any comments or questions below。



![](img/5b98b5c43444c74f1a857df8f80fa0b0_2.png)