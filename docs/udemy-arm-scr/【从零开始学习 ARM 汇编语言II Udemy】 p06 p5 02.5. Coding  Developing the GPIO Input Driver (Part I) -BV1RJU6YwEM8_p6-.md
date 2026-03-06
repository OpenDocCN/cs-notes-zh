# 【从零开始学习 ARM 汇编语言II Udemy】 p06 p5 02.5. Coding  Developing the GPIO Input Driver (Part I) -BV1RJU6YwEM8_p6-

Hello， welcome back in this lesson， we shall see how to configure our Y GPPu for input。

In assembly language， I'm going to create a new project by coming over here new U visionion project。

I'm going to keep in a new folder， call this。😔。

![](img/13915789904c9ccaa5e43416575fdcd4_1.png)

GPIO input。And my board is STM 32， F 4，1，1， V E T。

![](img/13915789904c9ccaa5e43416575fdcd4_3.png)

And under CmC osllate the core。😔。

![](img/13915789904c9ccaa5e43416575fdcd4_5.png)

And the device， also at a start。Okay。And my target is ITM 32。😔，So group here。

 I'm going to renamed it。😔，Rename this to up。I'm going to create a new file here。😔。

This is going to be main do S。Give it a name， main。



![](img/13915789904c9ccaa5e43416575fdcd4_7.png)

Like this。And I'm going to set my target options。I'm using the SD link debugger。Click over here。😔。

Reet him run， O and an okay。😔，So on our nuclear board， the push button is connected to PC 13。

 so we will have to configure PC 13 as。A GP P I O input pin。

 and we have to go through the same process we did for the LEDs。 But before we do that。

 I'm going to bring our LED information what we already wrote in the previous lesson。

 I'm going to bring that here。Put it over here。And we wrote some。

We had some information regarding the。The BSRR register as well， or break that here。Okay。

So what we have to do。As to find the base， the base address of PC 13。

So we go to the data sheet to do that。

![](img/13915789904c9ccaa5e43416575fdcd4_9.png)

So over here。😔，Okay， PC 13， is's the base address。Of PC， sorry， we are looking for port C。

 the base address。 is's about the port， not a pin。 So the base address of pin 13 is this over here。

So。😔，I'll bring it here。Just a moment。Right。Okay， so create G I O。GPIu C base。And this E Q U。Is this。

Right。Then the mode register is the same as GPIU A mode， so just copy。I mean。

 the mood offset is the same。 The offset are the same。So I'll just copy this and change this to C。

And then。I'll copy this。And then just change everything to C。 wherever there is port A， I make it to。

 I change it to port C。Right。So we've sorted out the mode。😔，And。Over here we have GPIUA。😔。

Enable and I've included GPIU C enable because to enable GPIU C to enable port C。

 we've got to put the number one at bit number2。Bit number 0 is for port A。

 Bi number one is for port B。 Bi number 2 is for port C。 So we shift one to bit number 2。

 and then this will give us GPI U enabled。Right， another thing we need is the eat。Output。

 we will need input data register because we're configuring this as an input pin。

 So let's go to our data sheet to get the offset of the input data register。

 We go to the reference manual。I'll come over here and search Ct F of such I D R。

And then our'll search IDR again， this is the one we're looking for GPR UX input data register。

The offset is 0 x 1，0。Right， so this is where。We read the input from the input data register。

 so let's create this register。

![](img/13915789904c9ccaa5e43416575fdcd4_11.png)

I'll come over here and see。😔，GPI you see。IdR offset。And then the offset was 0， x1，0，0 x1，0。

And then we can see a GPI you see。Id。And the idea records the base。😔，Plus， the offset。Like this。

 so we have the idea offset as well。Okay， so one other thing， our button is active low。

What does this mean， It means when the button is it the default state of the button is  one。

 When we press it， it becomes 0。 So when the button is on， it's actually 0。When it's off， it is one。

 And what I mean by it is 1， it is 0 is essentially PC 13。 where the button is connected is 0。

 When we press， it becomes 0 when we press the button and when we release it。It becomes one。

 So we call this the active low switch。 I'm going to create some symbolic names for our button here。

Let's see button on。And I'll simply say EQ U。 and I'm just gonna this time I'll use this rather than a shift 1。

2，3，4。 It's fine。 And then I'll see。BTN again， BTN pin， the pin of the button is PC 13。

Another way of indicating PC 13 is this。How do I know this is PC 13， because I know。

Each0 here represents 4 B。 So we have 4 B plus another 4 B。 We have 8 B， plus another4 B。

 We have 12 B。 And when we expand this number 2 to its binary form， we have 0，1。ze zero。So from this。

 we already have2 off bit。If we add this， we have 14 bit now， meaning this is at position 14。

 but we count from 0。 so therefore this is at position 13， hence this corresponds to PC 13。

If you don't understand what I just said， just send me a message。Right， so this is it。Okay。

 and we said if it is on， if it is one， if PC 13 is1， it means the button is off。 So I'm going to。

Create another symbolic name known as button off and it' going to be the same 0 x200。Like this， okay。

I think we've got everything we need。And then。We can start off。We can start。With our directive area。

Text。This is the code area。It is read only。And then we align two。And then。

We're using the thumb instruction set。We said this as entry。

The reason I put entry is if you have a different version of the car U vision。

 you might receive a warning in that no entry point is indicated。

But I think the latest one doesn't need it， that is why this doesn't show the blue colour like the other directives。

 so you can take entry out and see what would happen。So I'll export over here。This all mean label？

And then I'll do underscore underscore main over here。😔，And then。Or do be L。

Or branch to the subroutine GI O in it。So we're going to initialize both GPIUs together， both GPIU。

A and GPIU C。 So let's start with GPIU A， our LED GPIU。Like I did before， I'm going to。😔。

I'm going to write this。And C language to help you。 So pull。Poor comment here GIU a。

Were starting with RCC。 So were enabling clock access to GI A so RCC A H P1 enable register。

And what we want to do is。We perform an our operation with its current content。And by。

Performing all with this， we enable GPIU A， so we write the assembly code for that and you can post the video and try to do this on your own because we've done this before。

Right， once you are done， you can do it with me。 So we say R0。Its RCC。

And then the name of the register is AHp1。E and R 1， enable register 1。 Once that is done。

 we do load。We do load r1。With what is found at the address stored in Reg R0。And once that is done。

 we perform our all operation。 and then we store the results back in Er。That is GPIU A enable。

Once we've done this， we can store the results。😔，At the RCC AHP1 enable register。

And we do this by saying take r1， that's the source。

 and then the destination is the address phone that's r0。Once that is done。

 we can go on to configure the mode register。So。What we are going to do here is GPIU。

We're gonna do GIU A。M register。And what we want to do is modify out。

 performing an or operation with it。So I'll do that by saying load。😔，Auro。GPIU A。Moode to register。

And then， load。R run。I you。And then we perform an all operation like this。😔，I1。And then。😔。

Muld five out。It's a constant we've created。And then， we store。R1。二0u。Okay， so once that is done。

Okay， we've configure this。 We don't need to deal with the output data register or the BSRR now。

 Let's configure the。The push button as well。我 put的 comment贴。

P button clock in it and what we're going to do is essentially。😔，RCC A H P1， E， N R。2CC。AHP1， ENR。

And what we want to do is。😔，G P，I O， G PI O。C enable， cause PC 13 is what we are dealing with。 Okay。

 so that's the C language in assembly we're gonna do。Load。ICu。Equals。Icc register over here。And then。

 load。Aan。20。And then， all。R1。GP I O C， enable。And then store。R1。Or0。Once that's done。

 we can return from the subroutine using the BxLR。And then we align。😔，And we end。Okay。

So thiss our initialization。Okay， so the video is getting a bit long。

 How about we continue in the next lesson， I'll see you。



![](img/13915789904c9ccaa5e43416575fdcd4_13.png)