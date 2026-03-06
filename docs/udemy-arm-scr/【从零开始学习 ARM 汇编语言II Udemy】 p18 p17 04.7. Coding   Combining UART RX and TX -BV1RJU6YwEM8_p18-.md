# 【从零开始学习 ARM 汇编语言II Udemy】 p18 p17 04.7. Coding   Combining UART RX and TX -BV1RJU6YwEM8_p18-

Hello， welcome back。 and this lesson were going to combine our wire。

U art RX and T X and have a single project that works both for transmit and receive。

I'm going to make a copy of the last project so that we can just continue from there。

I'll rename this， call this number 8。😔，And。😔，I'll wipe this off。😔，So this becomes Txrx。

And I'm going to close the old project so that I can open this new one。😔。



![](img/24d45c8b864f9e47ee3778aae9ef0664_1.png)

Right。

![](img/24d45c8b864f9e47ee3778aae9ef0664_3.png)

过来。Close this as well。Okay。So this is what we have。

 This is the last project we configured our our Rx and we this in turn was it was a copy of the T X project。

 so we didn't entirely clean things。 We didn't delete the T X part。 We changed a few things though。

 but we didn't clean it completely。So one thing we did over here is the alternate function select we've set only PA3 for alternate function。

 meaning we've set only the arm。We've set only the R bit。In the previous lesson。

 we set this bit here to 7， and this bit here didn't exist。 So to have both P A 2 and P A 3。

 it has to be 7 and 7 here because 7 piary 7 is 1，1，1，1，1，0 is 3，1， and a 0，1 like this。

So essentially what we've done now。Is like this meaning P2 should be set to 1，1，1，0。

 which is the A F 7， which means P2 should be set for U at and P3 should be set for U at as well。

 So that's the first change。And。Yeah， it seems that's the only change we need to do。 Okay over here。

 the control register one， we've enabled just RX。 So we've got to enable both RX and T X。

 So we've got to change this over here。This0 x4， we change it to 0 x C。

And if you go to the control register one， you realize that if you expand this zero X to its binary form。

 the bits that shows one correspond with the bits in the register that I use for enabling T X and RX。

Okay。And okay， we can go back to our old part rate if we want， which was 683。And。Yeah。

 so now we have both。We have both RX and Tx。How do we know this， We going to test it out。

Let's see what else is left。 I think there is one thing left。😔，Over here， G P。

 I O A alternate select this code here corresponds to setting only。Only PA。

GPI your A alternate select。Wait before I complete this statement， let's see。Okay。

So this is what we used in the mode register to select the alternate function。 Okay。

 this corresponds to only setting PA3 as alternate function。

 but now we want to set both PA3 and P2 as alternate function。So I'm gonna change this number 8 here。

To character a。 And if you expand this， you realize that this a。

Corresponds to setting both P2 and PA3 in the motor register to alternate in the yeah。

In the mode register to alternate function mode。 So this， we write this。

We write this value into the mode register， whereas we write this value into the alternate function lower register。

 First， we've got to tell the mode register this bin is going to be alternate function。

 and then we go to the alternate function register and choose what type of alternate function we want in this case。

 U at alternate function。Right。So I think these are the changes required。Once we've done these。😔。

Yeah。We have both T， X and Rx flags here。Okay， and we didn't clean a wire。

Read and write so we can test the read again and make sure it's working just like we expected。

I'll click here to build it build successfully。I'll click here to download onto the board。😔。

And I'm going to open to our term。😔，And。I'm going to press one on my keyboard， and the LED is on。

 You can verify that for yourself。Right， so now I'm going to test the transmit part。

I'm going to come over here。😔，And I'm going to。Transm a simple character。嗯。Over here。怎么关了。

Comd this out， and I'm going to send。😔，Yes。I'm going to send why， however， just why。

 because we run in a simple test。Move R0。And decode for why is。0，5，9，0，5，9，0， x，0， x 5，9， Sorry。

0 x 5，9。 and we branch 2。You ought right， character。Right， cha。😔。

Okay let's build this and see what we have， click over here to build。

 click here to download onto the board。😔，And to return。😔，And as you can see， we have YY， y， okay。

 so we have both Tx and Rx working。Right， so what we're going to do next is we are going to continue in the next lesson。

 We're going to see how to call these。These U are subroutings in a C file。

 we're going to call this these assembly functions in a C file。 And then we're going to add。

Other functions like the print F so that we can type an entire statement。

 and then we call our U at write and U at read and send this or read this to our serial port。

 So this order is for this lesson combining the T X and R X part。 I shall see you in the next lesson。

 If you have any questions or told us， you know。Send me a message or leave in the questions area and if you're finding the course useful kindly take some time off to leave a review and I'll see you later。



![](img/24d45c8b864f9e47ee3778aae9ef0664_5.png)