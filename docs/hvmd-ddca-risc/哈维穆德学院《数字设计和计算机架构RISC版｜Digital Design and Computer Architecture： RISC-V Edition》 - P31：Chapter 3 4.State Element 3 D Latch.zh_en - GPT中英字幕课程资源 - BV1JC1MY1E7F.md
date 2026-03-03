# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P31：Chapter 3 4.State Element 3 D Latch.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/ac13f194b941ce68423799c9c910fdf3_0.png)

So now we introduce a third state element， which is the D Latch D stands for data。But D is data。

And this， this circuit element has two inputs， clock and D。And stores one bit of state。

So clock controls when the output changes the output Q。And D。

 the data input controls what the output changes to。

And so the way this D latch works is it's actually built on top of。An Rs latch or an SR latch。

And so we have our S and R inputs。And are。Q or statement output。

And now we have and gates that precede this SR lottch。And so we have。

 we tie these an gates to the S and R inputs。 And then we add them with clock。 We put the。

 We and the。Put a clock input into the and gates。And so when clock is equal to zero。C is equal to 0。

 doesn't matter what's on the other input of this an gate。When clock is equal to zero， zero。

 and anything is going to be0。So S and R are going to be 0 when clock is 0。

 and we know that when S and R both have zeros on their inputs。

 then Q just retains its previous value。 So then it's in the memory state。

So now let's see what we put on the other input of those and gates。So now we have D， this data input。

It goes。Into this top and gate。So D our data or value that we want to store into that state element into this D latch。

And we put D bar into the other end gate that feeds to。Q R。And so here we have our D latch。

 So what happens when we saw what happens when clock is equal to 0 and clock is 0， no matter what。

It doesn't matter what D is 0 and anything on this gate on those and gates。 the output is 0， and the。

SR latch just stores whatever it had before， right， Q equals Q previous。

 But now when clock is equal to1， let's see what happens。 So when clock is equal to one。 Well。

 now we have one and anything， one and anything on both of those and gates。

 So now it depends on what D is。 So one and anything， right， This is just one and D， which is just D。

All， so D comes out of this gate and goes into the S input of the SR Lotch。And this is one and D bar。

 So one and D bar is just D bar feeds into the R input of that S R latch。And so， here we have。

You know， let's think about what happens when D is equal to 0， or let's start when D is equal to one。

Well， then set is one， the set input of the SR latch is one。And reset is D bar or0。

 And the output Q sets to one。And so when clock is equal to1， D just essentially flows through to Q。

Let's do the other case to make sure。When D is equal to0。Here's our other case。When D is equal to 0。

 well， S gets 0。 S the S input of the SR latch and。The R input gets。Dbar， which is one。

And then we know that if we have one on R and a 0 on S， then the output Q resets to 0。 So， in fact。

 when d equals 0。Yep， the output Q， that state bit follows D。 And as we saw before， when D was one。

 the output Q also followed what D did。So， essentially one。Clock is equal to。0。

When clock is equal to 0， it just retains its state。And clock equal to zero。This D latch。

 right if we now enclose this into a larger box， this D latch。

Retains its state when clocks equal to one， however。D just passes through。To the output queue。So。😊。

Here's our symbol for this D latch。 We have a D input。

 and we put our clock input on the top because it's a control input。

 It's controlling when D can pass through to Q。Some clock is equal to one。D just passes through to Q。

 we call the latch transparent。Because D can C through to Q when clock is equal to 0。

The latch is opaque and Q just retains its previous value。 It doesn't。

 Q D can be changing all all at once，1，0， but Q is just going to retain whatever it had last Time clock was。

 was high。And it avoids this invalid case where Q is not equal to the inverse。嗯。

Q and QR do not have the inverse relationship。So here's the Dlashtch internal circuit。

 let's take a look， well， now s is on the bottom note and R is on the top。

 but still we have clock going into both of these and gates。

We have D going into the an gate that feeds to S and D bar going into the an gate that feeds into R。

And again， here is our symbol for the， for the D lottch。And so when clock is equal to zero。

D is a don't care。 And D bar is a don't care bar。 We don't care what D is because when clock is 0。

 We get 0 and anything。On both of those and gates。 So R and S are both 0。

And Q just retains its previous value。Q previous N key Bar retains Q previous bar。

Whatever it had last time clockap was high。Now， when clock is equal to one。

Well now it's going to just allow D to pass through or D bar to pass through these and gates。

 So when D is 0。We get one and0。 We get a0 D bar with N V1， right，0 comes up here and gets inverted。

 becomes a1。 We get one and1。 R is a1。So， then we have。D bar is one。 S is 0。 R is one。

And so with an one on R and was 0 on S， we reset the output Q。To 0。 And PR the opposite。And then。

 we have。The last。Row in the truth table when D is1 and clock is still one。1 D is1。 D bar is 0。

 D being1。 D bar is the inverse 0。1 and one on this lower end gate set input becomes one。

 and we get 0 and one on the top and gate。The reset input is 0。

 So we know that when we have one on the S input of an S R latch and a 0 on the R input。

 the output gets set。2 to one， the state that being stored is is a one。And so we see that in fact。

 when clock is 0， it retains its state。But when clock is one， the output just follows whatever。

The output Q follows whatever D does。

![](img/ac13f194b941ce68423799c9c910fdf3_2.png)

So， it follows D。