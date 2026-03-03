# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P23：Chapter 2 11.Karnaugh Maps (K-Maps).zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/705055859aacb210f8737f0859b77b22_0.png)

Hello， the topic of this video is Carno mapps。So we've been talking about how to simplify truth tables。

For。Bolean equations。So one method of doing that simplification is the sum of products。

 You could take each row in the truth table。I write out a bulloleying equation。And in this case。

We have。Two rows that are one。We write out why。Equals a bar， B bar， C bar， or A bar， B bar， C。

And then we could apply Boolean algebra。Get。Equals a bar， B bar。Another method。

Is that we could just do inspection。We could see why is only true in these cases where A and B are both false。

 So we could just write out by inspection。 Y equals A bar， B bar。And for many truth tables。

 they can just be done by inspection。But sometimes you come across a truth table where doing the booleing algebra is tedious and truth tables too complicated to solve just by inspection。

And k maps give us a nice visual way of doing the simplification。

They rely on this notion of combining that P and a for any expression P。

 P and A or P and a bar is just P。 The A doesn't matter。

And we're going to arrange our variables in a graphical way where adjacent boxes only differ in true and complement of one variable and let us simplify。

So。Let's go through this truth table。When a is 0。B is 0。 C is 0。

 We need to talk about the arrangement of the carnal map。

So we're going to write out eight boxes corresponding to the eight rows of a three input truth table。

 We'll put A and B on the horizontal axis。 C on the vertical axis。 C is just either 0 or 1。

 A And B could be 0，0，0，1，1，0， or 1，1。And notice that we need to write them in this funny order where the one one is here。

So that each column only differs in one variable。From 0，0 to 0，1， only B is changing。 from 0，1 to 1。

1， only a is changing。From 1，1 to 1，0 only be as changing。 And， in fact， if you wrap around from 1。

0 back to 0，0。Then， only。A is changing。So now we can put the elements of this truth table into the Carno map。

 We'll start with 0，0，0。That's this box right here。 And y is one。0，0，0。Next for 0，0，1。

 That's the box。Why is one again。Now， for 0，1，0，0，1，0 is the sps， and y is 0，01，1 is the sps。1，0，0。

 We have to be careful。 It's actually this box。1，0，1 goes here。1，1，0 goes here， and 1，1，1 goes here。

And now， we can circle the。Once in the truth table。And in this case， we see that the circled block。

Is active when A is 0， B is 0， and C doesn't matter because it could be either 0 or  one。

 So we can just write out that y equals not a。Recap that。We've circled。The column。That has the ones。

And。We see that Y in this column， C doesn't matter because it could be either 0 or 1。

 A and B are both 0，0 in this column。 such y equals not a。

Let's do another slightly more interesting example of a three input car map。So and again。

 we'll go from the truth table to the kernel map。 The most difficult part is just accurately populating the kernel map。

So 0，0，0 goes here y 0。0，0，1 goes here， while 0。0，1，0。Its here，0，1，1 is here。1，0，0 is here，1，0。

1 is here，1，1，0 is here， and 1，1，1 goes here。Now。We see。If we circle。Rectangular boxes。嗯。

That contain the ones。We have to do two circles to get all the ones。This circle。Is。True， when C is1。

A is either 0 or  one， So it doesn't matter。 And B is one。So， this。Pair corresponds to a。Implicant B。

This term here。Is true when。A。Is false。Bei。Is true。 And C doesn't matter Could be either 01。

So we get B or A bar B。So let's add another definition。 we've talked about complements， literals。

 implicants remember implicants are the products of literals。

And prime implicants now are implementants corresponding to the largest thing you could circle in a car map。

So to use Knoap to simplify， we need to circle every one at least once。

Each circle has to be a power of two in squares in each direction。 So 1，2 or  four squares wide。

Each circle should be as large as possible。 That gives us the greatest simplification。

 and a circle can wrap around the edges。So for example。

 here's a foreigncarno map Let's first go from the truth table。0，0，0，0。Is this element。

 and that was a one。0，0。0，1 goes here。0，0，1，0 goes here，0，0，1，1 goes here。Next， we're up to this row。

 010，0。Goes here，0，1，0，1。Goes here，0，1，1，0。And 0，1，1，1。Next， we have 1，0，0，0。Go here。1，0，0，1。1，0，1，0。

And 1，0，1，1。And finally， the last four rows of the truth table were all zeros。Just put them in。Now。

 let's circle the largest blocks we can。That capture all of the once。So here's a two by two block。

We can circle。Here's。😔，Hey。2 by one block。And。Here's a。2 by one block。

And now we've got a couple choices。This one， by itself。Would just be a one by one。

 but we could make it bigger by wrapping around the edge and circle something adjacent。

 We could either circle here or circle here。 Doesn't really matter， let's suppose。Re circle this one。

And the same way， this block。I could also wrap around and circle something。 Let's suppose。can。

Circle around here。 So now this element has been circled multiple times。 That's fine。

And I left out an important observation。 These four corners。Actually。

We could circle all of them at once and get a four by a2 by two。Circle to capture the corners。So。

 now。We have the。Circles， and let's read off the Boolean equation from here。

 So starting with the green block。A is0 on both of those columns。 So that's a bar。B is either 0 or 1。

 so it doesn't matter。C is always one。And C bar D is either1 or0， so it doesn't matter。

So the green block is a bar C。The blue block。This is true when B。Because low。Sorry。That would be。

A is low。And B is high in this column。Xi。Is either 0，1， so it doesn't matter。 And D is 1。So a bar B。

 D for the blue。How about for this red。A is true。B is false。Xi。Is false。T doesn't matter。And finally。

 the funky one going around the four corners。In this case。Ai。It is either 0 or1。

 so it doesn't matter。B is 0。C， that's this row in this row。 C is either 0 or1， so it doesn't matter。

 And D is always 0。So this should be B bar， D bar。

![](img/705055859aacb210f8737f0859b77b22_2.png)