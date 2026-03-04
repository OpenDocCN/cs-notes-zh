# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P22：22_06_03_经典示例.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/3e7c09f6f895cff896d52452e7a3dcfc_0.png)

Next， we're going to look at a classic example of the use of recursion。

 There's actually a number of examples that are very much like this that indicate the structure。

 basic recursive structure that's often useful。And one of these examples is our subdivisions of a ruler problem where we want to print out the length of the subdivisions of a ruler down to one over two to the n inches。

And so we did a function like this that did not use recursion for small values of n。

 and we did it with a loop。 but here's the recursive solution to that problem。To print out。

 to create a string， a ruler string for n， if it's zero， we just return a space。

 otherwise we sandwich the integer n between two copies of the ruler function for n minus1。So again。

 we can do these small examples and get exactly the same way as we got before。

 and of course if we try a huge example， then there's not going to be enough space for that string and because it's recursive we get out of memory error of that form。

But it's a simple expression of this computation， which we can use for small values of N。

 which is sometimes what we might want to do in practice。So keeping that one in mind。

Let's first of all， let's look at the idea of tracing a recursive program to kind of understand the structure of this computation。

 and then we'll look at another one that's similar but more interesting。So what we use is。

 and we can use this for any program that calls functions， but for recursive functions。

 it's particularly useful。We're going to have a tree。

 it's going to have a node for each recursive call and we're going to label that node with the return value after the children are all labeled because we don't know what we're going to return until our children have returned。

 so if we call ruleer4， it calls ruler 3， it calls ruler 2， calls ruler 1。

 ruler  zero returns the space。And then ruler 1 makes another call on ruler 0。

 and that returns a space。 When those are both done， then ruler 1 is going to return space1 space。

So now ruleer 2 makes its second recursive call， computes the same thing。

 and then makes its return value， which is 121 with spaces in between。And in ruleer3。

 that's going to compute the same value in the same way， and then we have ruler 3。

And now we do the right half of the tree to get the second copy of Ruler3。

That's the second copy of ruler3 and then we put those together to get ruler 4。

 so dynamically it shows us what's happening with the computation and statically it shows all the function calls。

 it's a very natural way to visualize what happens in a recursive program。

So now let's look at a classic puzzle called the Towers of Hanoi puzzle。

This is a legend where we've got 64 discs of differing size。

We have three posts and the discs are sitting on one of the posts from largest to smallest。

And so there's a prophecy that says the monks have to move the disc to another post。

 but they have to follow some certain rules， and when the task is completed， the world will end。

And the rules are you can never put a bigger disk on top of a smaller one。

 so you've got to move them all over and follow these rules， you move the disc one at a time。

 never put a larger one on a smaller one， and so that's our question。

 how what sequence do we move the disc， how do we actually do it？

Can we generate a list of instruction for the monks to get the disc moved？

And then if we have that list of instructions， maybe we'll have some idea when the world will end。

 So that's a practical problem。 if you believed it prophecy。Okay。

 so now to make the instruction simple， we're going to use cyclic wraparounds all that means is we're always going to say either move the disc right or left。

 so move right means one to2， two to3 or three going around to one。

And move left means the opposite means one going around to three， three to two or two to one。

So always we say move right or move left。 And if you're at the left edge， you told to move left。

 you go around to the right edge。So now our instructions can just be the name of a disk。

 the name of a post containing a disk and。Either an L or an R for right or left。

So what we're going to look at now is a recursive solution to this towers Hannoi problem。

So we have our N disk to move。 And what we're gonna to do is recursively move n-1 disk to the left。

 That leaves the biggest。Disk still on the middle post。 And then we move that one to the right。

And then we move those n -1 disk to the left again and put it that put it recursively。

 And then we've accomplished the move of the whole pile。

That's a recursive solution to the towers of an oil problem。

So let's just see what it looks like for n equals 3。So we moved the little one to the right。

Then the next one to the left。And they moved the little one to the right。

 and now we've got the whole pile moved from the center to the left。Now we move the big one over。

And now we're supposed to accomplish the task of moving those two discs to the left back onto the big one to do that first。

 we have to move the little one to the right。And then the blue one to the left or ci it rack around。

 and then the little one to the right again， so we accomplished the task of moving the discs from the center pole over to the right pole using that sequence of seven moves。

So that's what it looks like for n equals 3。 And now let's look at code for printing out these instructions。

So just following that exact scheme， so we're going to get the string of the move。

 so the N disc is for n equals  zero， we'll just return a space。Otherwise。

 we'll make the specified move for disk N， which is either right or left。

 and then we sandwich that between two copies of the moves for n minus1， we move the pile。

 we move one direction， we move the disk， we move another direction， and that's the entire code。

 recursive code to print out this list of instructions。

The recursive program takes a second argument direction， which left， if it's true， you go left。

 otherwise you go right。And then that's the direction that you move the big disk。

 and then you move the little， the pile of disk and the recursive call， the other direction。

Now you notice that this is very much like the ruler program。

 it's just got the lefts and right added into it， but that's a complete solution that'll do the job it'll give that exact set of instructions for three and we can do more。

So now looking at the recursive call tree is instructive， it's the same as for the ruler function。

 And let's look at what the tree is。 and then we'll look at some interesting facts that it suggests。

So this is the same process that we went through for the ruler function。

 except that we're keeping track of the right and left。And switching directions at at each level。

So let's look at what the tree looks like。So that's the full instructions。 Now。

 one thing that you notice looking at this is that disk 1， for example， always moves right。

This too always moves left and so forth。 Every disc always moves in the same direction。

 and then you can easily convince yourself of that fact。

And the other thing is that every other move involves moving the smallest disc to the right。

And when you think about it， if you just move the smallest disk。

 then the next move that doesn't involve the smallest disk， one of the two discs has to be larger。

 so it's determined what the unique legal move is。You don't need the instructions。

 move the smallest disk to the right， then make whatever move is necessary。

So that's very interesting insight that we can get by studying the recursive program。

That happens on lots of occasions， we use a recursive formulation to understand the computation and then find a better way to do it。

🎼。🎼，🎼，🎼。

![](img/3e7c09f6f895cff896d52452e7a3dcfc_2.png)

You probably figured out that it's not too difficult to add sound to that。

 just play a tone according to the size of the disc。So generate list of instructions for the monks。

 yeah we can do that but really the short form is which you could write on a small。

 you could chisel on stone next to the pile tell them what to do and so the question now is when might the world end well for 64 discs you need two to the 64th minus one moves and that's easy to prove from the recursive program you have to actually also prove that there's no better way to do it but anyway we're fine if you could do one move per second it would be 5。

8 billion centuries until the world ends if you have really fast monks and you can do a billion moves per second we still have 584 5。

84 centuries so world's not going to end for a while。



![](img/3e7c09f6f895cff896d52452e7a3dcfc_4.png)