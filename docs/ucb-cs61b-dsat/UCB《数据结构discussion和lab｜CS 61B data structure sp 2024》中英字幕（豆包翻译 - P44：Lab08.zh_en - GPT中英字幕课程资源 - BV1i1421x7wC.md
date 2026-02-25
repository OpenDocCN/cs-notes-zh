# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P44：Lab08.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

Right。

![](img/982c01dbbf99b90ba6d54d74a97faa0d_1.png)

Everyone， welcome to Lab 8 Lab 8 is going to be about LLRBs or left leaning red black trees。

 and so in this lab you're going to go ahead and implement the main rebalancing functions of the LLRBs to maintain a few rules that we have to keep about the LLRV structure so let's go ahead and jump right into it。



![](img/982c01dbbf99b90ba6d54d74a97faa0d_3.png)

Before I actually cover the entirety of the LLRB as well as the rules。

 it's sort of important that we go over the 23 tree from last week's lectures and so if you recall a  two3 tree is essentially a BSD except we allowed each node to have up to two values and up to three children。

 hence the name23 tree。And so the mapping is as follows。

 so it follows much of the same structure as the BST。

 so all of the elements strictly less than go into this right box。

 we add that all the elements in between so between like for example。

 this three and five are going to go in this middle。😊。

And everything greater than is still going to go on that right note。And so the importance of a  two。

3 tree is that all of the children are the same distance from the root node and why this sort of matters is because when we try and level out the tree like this。

 it gives us better performance in particular for searching and inserting elements。

 so we're trying to avoid that worst case O of N for our very spinly tree and we're trying to reach of log n performance。

And so let's go ahead and talk about the LLRB then。😊。

And so we want to try and move away slightly from the23 tree。

 particularly because  two3 trees are a little bit nasty to implement。

 so we're going to move towards LLRVs。The way we're going to convert from a 23 tree to an LLRB is for every single one of these nodes with two elements in them。

 we call these three nodes， we're going to change it into two separate notess。

And so I've done a color mapping here already， but essentially what we're going to do is we're going to take each of these three nodes。

 we're going to take the larger element， keep it as a black node in the LLRB。

 and we're going to take that left， smaller element， push it down to the left and make it a red node。

So here we have three，5 inside our two，3 tree， we're going to split these into two separate notes into five and three。

 and this three is going to be down and to the left as well as the red child。

And so this is what we mean by a left leaning， so we push it down to left red black tree。😊。

And in particular， it's important to note that each two3 tree has a one to one correspondence to an LLRV。

 so each two3 tree has its own unique LLRV。One thing I do want to go over really quick though is during lecture we talk about LLRBs as having red links。

 so red edges instead of red node， whereas in this lab we talk about red or black notes so in this lab we deal with red or black notes because that's just a lot easier to implement but the way that we treat the difference between red links and red notes is that every single time we see one of these red links like this one down here we're just going to convert that lower node to a red node。

😊，There's slightly more specifics about this inside the La spec。

 so I recommend you go ahead and look at that for more info， but that's sort of the gist of this。



![](img/982c01dbbf99b90ba6d54d74a97faa0d_5.png)

Okay。Let's go ahead and talk about the LLRB rules then so this is copied basically one to one from this spec so I won't go over all of these necessarily super in-depth。

 The main idea here is that there's some rules that enforce how our LLRB is structured and so essentially whenever we're trying to insert elements into our LLRB remember an LLRV is just sort of like a fancy BST it might violate some of these rules and the main ones we have to pay attention to are these ones that I have highlighted with a blue star and so when we violate any one of these rules we have to apply some sort of function to change the LLRV to make sure that it still obeys all of these rules。

And so mainly these are going to be rotations and color flips， and we'll see about that really soon。

😊。

![](img/982c01dbbf99b90ba6d54d74a97faa0d_7.png)

So before jumping straight to the thick of things I do want to cover rotation just really quickly。

 these are copy pasted from the LLRB lecture so I highly recommend going ahead and looking at that。

 but I'll go over this really quickly。😊，Whenever we want to rotate something。

 so we have rotate right and rotate left。There's two sort of main things I like to think about while dealing with this。

 So let's pretend we're on this left side of this graph。

 So over here and we want to call rotate right on D。The two things we're going to do here are first。

 we need to push D down。😡，And to the right。 So what's going to happen is going to go down。

En to the right， like this。The second thing that's going to happen is this B node then needs to come up。

😊，To where D was。And so we can think about a rotate right and rotate left as technically like sort of two operations we're going to push that main node down into the right or left and then that left or right node back to where the original node was and so we're going to focus on rotate right here but rotate left is very similar。

One thing to keep in mind and this is just a small tip in general for LLRBs is that you want to be careful where this purple node goes。

 So whenever we're rotating， we might notice that B already has two children and when we want to move B down and the right we do need to connect it to B all over again。

 So we might get this weird looking structure that is not allowed because it has three children。

 And so the question is where we put this purple triangle And as it turns out it's。😊。

Next to list D right here， the reason I won't go into too much during this video。

 I recommend checking out the lecture， but that's just something to keep in mind as we do rotations。

😡，All right， let's jump into these rules as well as how we are going to fix any violations of them。

 so let's go ahead and jump straight into it so our first rule is if a node has one red child。

 then it has to be on the left。And so the way that we're going to go about this is we're going to pretend we're inserting into an LLRB。

 we're going to see how each of these rules are violated and then how we're going to fix them。😊，So。

Inside this case， we start off with a simple LRRB， pretend we are at this node A。

We're going to try and insert an element， and so keep in mind whenever we insert a node into an LLRB。

 it's always going to be read。So we're going to go ahead and insert x。

 suppose here x is going to go to the right of a。😡，This violates the rule that we set out here。

 so if there's a red child or one red child， it has to be on the left。

The way that we're going to solve this is we're going to call rotate left on a to try and move a down to the left and X up。

And so what this is going to look like。😊，Remember from before。

 a needs to come down until to the left。X。Tries to go where A was。So let's go ahead。

Draw these two notes。I guess that one's going to be an oval。So A is going to come down。

X is going to go up， let's go ahead， connect these two nodes and the rest of the tree。

And so one thing to really note with all rotations is with these two notes that are mainly involved。

 so the pushing down and the coming up。😊，We want to change these two colors。To be the other one。

 So if that wasn't worded too well here we're just going to swap these two colors。

 And so in this case， X was red before。 So now it's going to be the color black。A was black before。

 so now it's going to take the color red。And so what we're going to do here。

Let's go ahead and change the A nodes color to RE。And so as we see。

 we've gone and fixed the problem of having a red right child。

And now it's on the left just with a rotation， and so that's how we might come across this problem and fix it。

Let's go over our next problem then， and so our second rule here is that a node can't have two red children。

😊，And so what we're going to do is now we're going to we're going to call something called color flip。

 and so let's start from our problem before， so we're inserting into an LLRV and then we go ahead and violate some rule。

The way that this rule is going to get violated is suppose we have this LLRB on the right。

 we have B in in the orange rather， so we have B and A。

And then we're going to go ahead and try and insert X onto the right of B。

 And so now we've gone ahead and violated this rule number two， the way that we deal with that。

 as I said before， is a color flip so all color flip is going to do is it's going to flip that node that is passed in so in this case that's B as well as its children。

😊，And so what's going to happen here is none of the nodes actually change or rotate where they are。

So all these nodes are going to stay where they were。All we're going to do is change their colors。

And so。Since A and X were previously red， they're going to turn black now。

 so we're going to leave those B， but since B。😡，This note B。Was black before？

We're going to color it right now。And so as we see， we've gone ahead and fixed this problem。

Let's go over our sort of last case technically it's two cases。

 so the third rule was no red node can have a red parent。

 there's two small subcases here and then we're going to go over these one by one。So as usual。

 let's go ahead and start from our original LLRB and then see how we violate this rule。

 so before we have this LLRB， it's just going to be B and a。Suppose I want to insert a new node X。

 x is going to be a red node， and we want to insert it to the left of a here。

And so now we've gone ahead and violated this principle， we can't have two red left notes in a row。

And so this red X node has a red parent A， and so how do we fix this？😊。

We're going to call rotate right。On B。And so what happens here with rotate rights as before。

 B is going to try and come down into the right。And this a node is trying to go up where the B node was。

So let's try and visualize this a little bit， so I'm going to draw the B node。

So this B node is going to come down into the right。And the A。Is trying to go where the bee was。

So I'll sort of look like this。And then this x node is sort of untouched。

 it's still going to be attached to the A， so I'm just going to draw that in right here。

And it's still going to be attached there。And so x's color is not going to change here。😊。

So let's go ahead and color it red again。And so note that whenever we rotate we're going to swap the two nodes that are involved。

 we're going to swap their colors and so in this case B was black， so a。

Which was red is going to take on the color black。And then B， which was the color black。

 is going to take on the color of A， which is run。😊，And so in this case。B is going to turn red。

And actually， as we see here， this is another case we've already dealt with。

 this is the two red children case， and so whenever we come across this particular case where there's two red left nodes。

 we're going to first call rotate right， and then we're going to need to call color fliplip afterwards to try and fix this problem。

😊，Okay， that was a little bit of a doozy， let's cover this last final case line。😊。

So our last case with the no red node can have a red parent is what if instead of being on the left。

 this X node was on the right， so let's go over our case again。So our LLRB is this in orange。

 we have B and A， whenever I try and insert x， suppose I try and insert it to the right of a。

 so we've gone ahead and violated this rule again。And the way we're going to fix this is another rotate operation。

😊，Now we're going to try and rotate left on a if this isn't super clear。

 we hopefully this visualization will clear this up in a second。

 but suppose for now that we call rotate left on a。😊，What's going to happen is a is going to go down。

Untilto left。And then this x is going to try and go where a was。So。

B in this case is not really going to get touched， so。Let's go ahead。And put B where it was。

So a is going to come down to the left， so I'm going to draw a down here。

And then x is going to come over。To where A was。And so this is what our sort of tree looks like now。

And then recall， whenever we try and do a rotate left， the two nodes are involved。

 so in this case that's A and X， we're going to swap our colors。In this case。

 nothing changes because both A and X were already red。 So let me go ahead and color them red。

And as we can see， as a result of our rotation， we've gone ahead and changed this case into the case where we have two left red children in a row。

And so this is actually the same case as we had above。

 And so the way that we deal with this particular case where we have。😊，哦。

Where we have the red node with a right red node， so this B a X on the left here。

 the way that we deal with this is actually a rotate left。And then。😊。

We head into this case which is a rotate right which finally applies a color flip to fix the entire node and so this last one can be a little bit tricky and annoying to think about。

 but these are pretty much all the cases you need to deal with。

 especially how we violate an LLRB while we violate the LLRB's properties and how we might go about fixing them and so this lab is all about these fixes and so I really encourage you to think about all these cases。

 how we might arrive with them and how we fix them but that being said that's pretty much it for the conceptual oves as well as a visual sort of cue on how to deal with these rotations and color flips and with that I wish you good luck on the rest of the lab。

😊。

![](img/982c01dbbf99b90ba6d54d74a97faa0d_9.png)