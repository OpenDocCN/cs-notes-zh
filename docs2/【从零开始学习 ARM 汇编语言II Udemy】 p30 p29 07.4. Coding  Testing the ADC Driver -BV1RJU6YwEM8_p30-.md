# 【从零开始学习 ARM 汇编语言II Udemy】 p30 p29 07.4. Coding  Testing the ADC Driver -BV1RJU6YwEM8_p30-

![](img/4ea3124f09fae5ff76c07882b983c487_0.png)

Hello， welcome Mac， so let's test out our ADDC driver with the LEDs。

I'm going to create a constant up here， which I shall call。Sensor threshold， remember。

 the ADC owner of microcontroller is 12 bit。Mean in the M， the maximum value is 4095。And。

I'm going to create a threshold over here， and I'm going to set a threshold to 3000。Oh， she sense。

Annaco thresh。T， HRR H。

![](img/4ea3124f09fae5ff76c07882b983c487_2.png)

AQU over here。😔，1，2，3， meaning if the sensor value crosses this value。

 then an action should occur and that action is going to be turned on the L。

So I'm going to come down here。And createate。Another sub routine here。😔。

I'll call this LED control in this which will use to plain the LED。O see LED。So about the L control。

Put an underscore over here。😔，And what we're gonna do is we first load our。Thshold value。

Load are one。With。😔，Ss thsh。Right， and then we're going to compare this to our0。

 So by the time we get to the subrine our0 would have had， would have。Takeak in our sense of value。

 remember when we call ADC read。

![](img/4ea3124f09fae5ff76c07882b983c487_4.png)

The value is stored in our0。Is stored in aro， the return value when we read from the sensor is stored in aro。

 so when we call LED control after ADC read。Our0 would have the sense of value。

 so well compare our sense of value to this threshold， which is our constant。So say cM p。R0， R1。

And then I'll see branch if greater done， and we're going to branch to a label cord。😔，LED on。

And then。Would do branchn if less than。And we're going to branch to a label cordor。LED of。Right。

 and then Px Lr。To return from the subrout。 So we simply need to implement these two labels。

 So we compare our sense of value to to our threshold。

 If the sense of value is greater than threshold branch to LED on if it is less than the threshold branch to LED off。

So come over here and do LED。Eity of。And then we're going to use the P S， the B SR， R registers here。

 So I do register。 I'm gonna use R 5 over here。 Ill do GI U A。PS SR R。And then I'm going to move。R1。

This is of so we use the reset， BSRR underscore score 5。And let's go reset。And then I'm going to。R 1。

A5 like this。And then。I'm gonna return from this soccerbri chain BXLR。Okay， so next is LED on。

Let's implement this。We load again。😔，A 5。GPI U A P， B， S，R， R。And then， move。A one。B， S， R。

 R on the score 5。And let's call set。I'mGo to put a number sign here。😔，Hejuhu。

And then we into the BRR register。😔，Our5 over here， and then we return from the subroutine Bx。LR。

So this's the last routine， so I'm going to align and then end the assembly file。😔，Like this。Okay。

 I'll delete these lies。Right， okay。So we can we can test it up， I'm going to come up here。

 so we start off by ADDC in it， we start off by GPIO in it and then ADC in it once that is done。

 we can read the ADC value。I'm going to do BL over here。😔。

And then I'm going to call ADC1 read which is the name of our。😔，Function。Also routine。

And then once we've read， we're going to branch to LED control。😔，LED underscore control。😔。

And once with've Ta， we're going to go back to the top of the loop。

 So this is in a way like our wild1 loop in C language。



![](img/4ea3124f09fae5ff76c07882b983c487_6.png)

Like this。

![](img/4ea3124f09fae5ff76c07882b983c487_8.png)

Okay。So now we can build and see what we have。😔。

![](img/4ea3124f09fae5ff76c07882b983c487_10.png)

I'm going to set up my target options， click over here， debug。😔。

I'll come to S link debugger settings。

![](img/4ea3124f09fae5ff76c07882b983c487_12.png)

![](img/4ea3124f09fae5ff76c07882b983c487_13.png)

I'll come to flash， download， reset and run。😔，Okay， and then okay。I'll click here to build。😔，Okay。

 we've ha， we have an error somewhere。

![](img/4ea3124f09fae5ff76c07882b983c487_15.png)

But symbolimbo。😔，Unexpected operator， let he。Okay。Deition。They shouldn't be here。Build。😔。

We've got one error。Okay。The PRR register。GPI U A P SR R， Let's see whether we have this register。



![](img/4ea3124f09fae5ff76c07882b983c487_17.png)

G， P I A， G P， I， O， A， B， S， R， R， I'm gonna copy its name。Then let's see。m when I jump there。😔。

It's because we forgot the equal sign here。A C1， C R 2， not defined。😔，那11。This is ADC 1，0 2。

So it says this is not defined。 It is1 C1 offset。

![](img/4ea3124f09fae5ff76c07882b983c487_19.png)

嗯。Okay。So over here， the offset should be CR2 offset。Okay， S W trick， not defined。😔，No problem。

Cause S W Creek here。A CR2 S W Creek。

![](img/4ea3124f09fae5ff76c07882b983c487_21.png)

Right， so the name should start with CR2。Okay， let's build。It built successfully。

 the download onto a board。It's downloaded。😔，So。😔，I've connected my potential meter。

 I' usinging a potential meter as my sensor here。 So when I move the potential meter to the far left or far right in the two opposite directions。

 I'll get the minimum reading and the maximum reading。

 So when I move it in one direction to the other end， the LED goes off。

 When I move it to the other end。 the opposite end。 When it crosses 3000。😔，The LED turns on。

 and I'll show you the pinout of our microcontroller。So this is the SDM 32 nuclear board。

This pin over here is P A1。 This pink number two here is P1。

 I've connected the middle leg of my potential meter to this。P a1 here。

 And then I've connected the left leg。To G And D over here and the right leg to 3 V3 over here。

 the middle leg to P1，1 leg to 3 v3， the other leg to G And D。 Okay。

 so I'm going to move my potential meter。And as I move it， you see the LED comes on。AMove it。

 it goes off， and move it comes on。And then it goes off。

 and then it comes on and then it goes off right。 So next， were going to。

We we're going to see how to be able to call our ADC routine in C language because I think in your practice。

 you would perhaps write some of the drivers in assembly and want and you will want to call them in C language and make use of them。

 So in the next lesson we'll see how to call these subroutines in C language。 I'll see in the next。



![](img/4ea3124f09fae5ff76c07882b983c487_23.png)

![](img/4ea3124f09fae5ff76c07882b983c487_24.png)

![](img/4ea3124f09fae5ff76c07882b983c487_25.png)

![](img/4ea3124f09fae5ff76c07882b983c487_26.png)