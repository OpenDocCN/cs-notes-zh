# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P24：Chapter 2 12.K-Maps with Dont Cares.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is Carno Mas with Don't Cares。



![](img/e842d9a1d5b6f5bf862e249b6c1a626f_1.png)

So recall that sometimes we can describe a logic function with the truth table that has don't cares。

 In other words， rows where the answer could be either 0 or  one。 We don't care。

And carno maps let us easily exploit those dont cares to find the simplest。

 some of products expression。But would do that。By optionally circling the don't cares in the equation。

 if it helps minimize。So best way to see this is by an example。

 here we have another truth table of four inputs， and now we see that some of the outputs are don't care。

So let's supply this to the truth table。Neing to populate truth table again。

 This is the easiest place to mess up on the 0，0，0，0 row， y is 1。0，0，0，1， y is 0。0，0，1，0。

 careful to put that here。And 0，0，1，1。Next，0，1，0，0。I0。0，1，0，1。X。0，1，1，0， careful goes here and 0，1，1。

1 goes here。1，0，0，0。There's a one。1，0，0，1 is a1。1，0，1，0 is an x，1，0，1，1 is an x。

And all the remainders are。Now， we want to circle the biggest blocks that capture all the ones。

 and we can optionally circle x's if it lets us make bigger blocks。

 but we don't have to circle all the x's because we don't care what the value is on an X。

So here we have a giant block。Of4 by two block。Here we have another giant。4 by two block。Here。

 we can circle the four corners again。And there's a leftover X here。

We don't have to circle it and circling it doesn't make it any simpler。So drawing that out again。

 a little neater。 This is our kernel map again， And we can look at our four blocks and write out the。

Implicants for each。 So starting with this blue block。This blue box A could be zero。 A and B are 0，0。

0，11，1，1，0。 So all possibilities。 So A and B don't matter。C is one on both of these。

 and D is either 0 or 1， so it doesn't matter。 So the blue block just corresponds to C。

The red block here。A is eithers one。 A is one in both columns。B could be 1 or 0。

 so it doesn't matter。 C and D could be any of the four possibilities， so it doesn't matter。

And finally， the corner。did this last time。 This was true。 A could be either 0 or1。

 so it doesn't matter。Be。He is always0， said Sp bar。C is either 0 or 1 doesn't matter。

 And D was 0 on both of them。 So D bar。So the simplest minimal sum of products expression for this truth table。

Is C or a。

![](img/e842d9a1d5b6f5bf862e249b6c1a626f_3.png)

BB bar D bar。