# 【从零开始学习 ARM 汇编语言II Udemy】 p40 p39 09.3. Coding  Writing the SysTick Timer Driver -BV1RJU6YwEM8_p40-

![](img/31a00097cea802ce8520180d2a299d3b_0.png)

Hello， welcome back， so let's write our driver。

![](img/31a00097cea802ce8520180d2a299d3b_2.png)

I'm going to start off by putting my directives。😔。

![](img/31a00097cea802ce8520180d2a299d3b_4.png)

Sps them here like this。And。I just creates a bit of space down here。



![](img/31a00097cea802ce8520180d2a299d3b_6.png)

And underscore underscore score main。😔，And we start off by。Enably our GPRU B。😔，GPRU in it。

And then what I'm going to do is， could you post the video and try to implement the GPIO in that subroutine on your own？

And once you are done， you can un pauseuse it and。

![](img/31a00097cea802ce8520180d2a299d3b_8.png)

We do it together。Okay， now let's see how that I done。 We've done this on multiple locations。

So this is the name of the subroutine。😔，I'm going to start off by。😔。

By enabling the clock access to GPRUF。First， we do this and then。Think。😔。

Iming to do this faster load。20。A1。And then， we perform all。2020。Then GPIU F， E N。And then we store。

😔，20。R1。And then we wait for a while。😔。

![](img/31a00097cea802ce8520180d2a299d3b_10.png)

By using NOP。What that stand。

![](img/31a00097cea802ce8520180d2a299d3b_12.png)

The direction register， we're going use GPRU。 We're going to use the red LED here。

So I'm going to do load。I'll align this a bit。😔，When I do load R1。GPI U F。D IR register。And then。

 load。Our siro。A one。And then， or。Auu。A lady red。And then， store。R0， R1。Like this。

So this would set the red pin as output。Next， we can digitally enable the pin。Ld。Load R1。Next。

 we do digital enable by accessing the digital enable register。T E N underscore score R， and then。

Load。😔，Our zero R one。And then oh。😔，2媳2媳。The LED red pin。



![](img/31a00097cea802ce8520180d2a299d3b_14.png)

And then， restore。二 she wrote。R1。And then this is done， we can return from the subroutine。



![](img/31a00097cea802ce8520180d2a299d3b_16.png)

Right。So next， what we have to do is implement the cysttic in function。



![](img/31a00097cea802ce8520180d2a299d3b_18.png)

To initialize the cystic timer。 Okay， so once we， once we enable our GPI U。

We would enable our cystic timer。So we branch to BL。😔，I this stick and going it。

So I'm going to copy this。Then I'll come here just stick in knit。😔，So first。

 what we do is we disable a timer before we change anything， it is advisable to disable it。

 so I'm going to do load。R1。 And then I'm going to。So select the cystic control register。

 that is where we enable and disable。And then I'm going to move0 into r0。



![](img/31a00097cea802ce8520180d2a299d3b_20.png)

And then I'm going to put that into the system control register by saying install。

Or you are one like this。

![](img/31a00097cea802ce8520180d2a299d3b_22.png)

Right， once we've disabled it， we're going to load the maximum value。The， the value into the。

 the railload register， the 0 x 0，0， F， FFF。So I'm going to do load。😔，A one。Because。And Vic。

See reload。And then I'm going to load R0。

![](img/31a00097cea802ce8520180d2a299d3b_24.png)

And this is going to be the constant。This one over here。Im to put this into r0， and then。

I'm going to do store。😔。

![](img/31a00097cea802ce8520180d2a299d3b_26.png)

20。Ner one。Okay， so once that is done， we need to clear the current register and to clear the current register。

 we， we need to write any value into that register so we can simply write 0 there。 I'm gonna do load。



![](img/31a00097cea802ce8520180d2a299d3b_28.png)

R1。And Vic SD。Current。And let's go R and then move。R 0， the number0， and then store。R0， R1。Right。

 so once that is done， we can enable our cystic timer。



![](img/31a00097cea802ce8520180d2a299d3b_30.png)

When I do load。R 1， I'm going to go back to the cystic control register by doing NVIc， S T， C， T， R。

 L， underscore score R。And then。I'm going to select the clock source as well as enable it all in this block。

I'm gonna do move。Our0。I'm gonna do。We have a constant for enabling。



![](img/31a00097cea802ce8520180d2a299d3b_32.png)

This one here。😔，It's like performing an or operation twice。So'll say plus。

 and then I'm going to do clockoxos。Like this。So once this is done， I'm going to do move。😔，Or0。Now。

 I've already done move of stall。😔，Ouru。R1， and then Bx。A lawyer。



![](img/31a00097cea802ce8520180d2a299d3b_34.png)

Okay。It looks good， so。In the next lesson， we are going to implement the cystic weight subrouts。

 These are our delay subrouts I'll see in the next lesson。



![](img/31a00097cea802ce8520180d2a299d3b_36.png)

![](img/31a00097cea802ce8520180d2a299d3b_37.png)