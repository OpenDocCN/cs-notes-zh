# 【从零开始学习 ARM 汇编语言II Udemy】 p21 p20 05.2. Coding  Assigning Symbolic Names to Relevant SysTick Registers -BV1RJU6YwEM8_p21-

Hello， welcome back and this lesson， we are going to see how to write a driver for the cystic timer。

I'm going to create a new project by coming over here project。😔，New Usion project。

Acre forwarder for this project。Cool thisす。Cote assististic。And then， the name of。

The project is going to be in the folder， and I'll call it cyst stick as well。



![](img/c5687853e2111b7e9d69dc90e28bd2d2_1.png)

And I'm going to select my board STM32 F411 VET。

![](img/c5687853e2111b7e9d69dc90e28bd2d2_3.png)

Click over here， okay。And the C says， I'm going to select the core and the device。

 I'm going to select the startup。

![](img/c5687853e2111b7e9d69dc90e28bd2d2_5.png)

And then， okay。Then。The target here is the SDM 32 F。DSTM32 F4 board。So as group here。

 I'm going to rename this to APP。😔，And I'm going to create a new file in here。

 right click at new item。😔，I'll give this a name， Maine like this。



![](img/c5687853e2111b7e9d69dc90e28bd2d2_7.png)

Right， so were going to create a driver for the cystic timer。An aic timer。

 it a qua peripheral for the cortex。M architecture。

 And what this means is that this profile is provided by。Mean。Regardless of the silicon manufacturer。

 any arm cortex import board has a cystic timer because that belongs to the architecture。

 The reason I'm pointing this out is that you could have an arm microcontroller without an SI module or a USB module or an I to C module because these are a modules or peripherals。

 they are included by the silicon manufacturer。A silicon manufacturers a company such as Texas Instrument。

 S T microelectronics， Motorola， etc ceter。But when it comes to cystic timer。

 cystic timer is a core module or a cork peripheral。 This is part of the。The architecture。

 so it comes with any armed cortex board。Right。So one other thing is the code we write in this in this particular and the driver we write for the cysttic over here should work on any arm cortex board regardless of whether it is cortex M3。

 M4， or even M7。Right。Right， so let's take a look at the registers we need in order to be able to configure our our cystic timer。

 So like I said， cyststic is is a core cortex M peripheral。 So because of that。

 we find the information。Concern and assist timer in the cortex M4 generic user guide。

 we're not going to the SDM32 document， but we're going to the cortex M4 document。

 this one here called the generic user guide。I'm going to double click over here。

And I'm going to jump to page 218218。I'll just go218 over here。And over here。

This gives us a summary of the various parts of the cortex M core peripherals。

 And what I mean by core peripherals are the peripherals provided by the arm， remember。

Arm is a company that designs the the processor architecture and companies such as S T Microelectronics。

 Texas Instrument by the the design from arm。 and when they buy the design。

They add their own features to their design。 So things like the ADC， the U at the SI。

And USB other peripherals。 they are added by the silicon manufacturer。

 and the silicon manufacturers are those that buy the design or license， the design。

 They buy license and they pay annually for the designs that they use。

 So what I mean by the core peripherals mean the the the peripherals that are part of the design that everyone gets。

Right。So over here it talks about them， it says cortex M4 peripherals。

 and this is what I call the core peripherals， and it gives the address boundaries here。

 the address for the cystic timer， Okay， it even calls it core peripheral here。

 So it's not a term I made， right。It's， yeah。 So if we wanna talk about cystic timer。

 we can just click over here if we w to read about it。 So to configure the cystic， we need basically。

We need three registers。 We need assistic。Lo register。 we need a current value register。

 and then we need the system control register。 But to talk more about this。

 I'll just click here to jump to this place。아。Where did it bring me。😔，Sorry about that。

I'll go back to 218。I think I clicked on the wrong side， on the wrong。😔，On the wrong。I clicked。

 I clicked on the wrong page number。Sist them timer。 I think system time， I should assist timer。

Right， cyst timer。 cysttic timer is the same as system timer Si here is a short form of system。

So over here， we， we get assistic registers that we need。 so we would need assistic。



![](img/c5687853e2111b7e9d69dc90e28bd2d2_9.png)

We need us register here， known as the M。The system control and status register。

This is the address for this register。I'll just copy this。This is the control。And status。

This is the address for it。Right。Just like we did。Because this is a car peripheral we don't even need offsets。

 It's just a single address。 we don't need to compute offsets。And。But yeah。

 the offset is already included。 You can think of 0 x E 0，0，0，0。0 x E 0，0，0， E as the base address。

 And this these first， I should say， if youd see anything from here， it's known as the LSP。

This first 12 LSB are the offsets。LSP means least significant bit。

And the reason I know is 12 is because each。Each number here corresponds to 4 bit。

 Each X hexodademal number corresponds to4 bit。 so you can think of these。3 as the offsets。

 since everything else is the same。You have E0，0 E E00 E。

 so these are the offsets they are already included。Right， so okay。

 the next register is the cystic reload register。 I'm going to get the address as well。Okay。

 after that。We have the。Do you assist the current value register。Let's take that as well。Right。

 and we have the the cyst calibration value register。 now about this。 Let's take this as well。Right。

 okay， so we've got the registers that we need for this。Okay， okay。

 So if you want to read more about the cysttic， you can。Read this document further。

 but I'm going to proceed and code along with you。 Okay， I'm going to minimize this。Right。

 so we've got a create symbolic names for the the registers that we have。Sou。D， when you check the。

When you check， the driver files provided by the silicon manufacturer。

What I mean by the driver file is for those of you familiar with SDtM 32。If you use the Ha library。

 Hall is builtt H AL and it stands for hardwareware abstractstruction layer。

 if you use the Ha library。If you go， if you just keep going and going。

 just click in and then going to。Go to definition of the particular function。

If you keep going or if you find where the system registers are defined， they are written as。

 they are written with a complete name。And all all I just said doesn't really matter。 I'm trying。

 I give that preview to come to this point。And the point is。

 I'm going to call the sister register N Vic。And then I'll say S T， and then I'll add the name。

EnVK stands for Nsled vector interruptt controller。

And what I was trying to say is this is the professional way that the drivers are written If you check the hall library provided by S microelectronics。

 or even if you check the CC's implementation provided by arm。

Because because cyst force under nest that vector interact controller。

 the name starts with envi like this。And so we're going to use this name and convention。

 that is what I was trying to explain。So enviC S T for cyst control and then underscoreco R for register。

 and then EQ U， we have this already。 This is this register over here。Pu this over here like this。

 And then we have。And fake。Nvi S。Sistic reload。It's just take reload。一 you。To reload register。

 we have it this one over here。And then。And V。SD。This is the current register。round E Q U。

 we have the current register here。And then， and Vic。SD。Colllib register。

 steep Col register around E Q U。We have this over here。Right， so now we can clean our notes。Right。

 and were going to。We're going to sort of create symbolic names for the various configurations that we need to place in each register。

Over here。Were going to， let's start with。We have to wait until the count flag is is set。

 and I'm gonna give this a symbolic name， or say Nvi。I'm。

 I'm gonna give the count flag a symbolic name and Vexxistic。 and we do this。In the control register。

 So I'm gonna add that to the name control。 and then I'll see count。And this is going to be EQU。Okay。

And。It's going to be EQU。0 x。1，2，3，4。 And if you go to the。

 if you go to the data sheet and you read a part about the system control register and you expand this to its binary form。

 you see that bit 0， you see that the bits。The bits， which is one。

Let me start this because I use this statement a lot。When I write a register。

 when I write something like this。And I tell you that this is going to be applied to a register such as this。

And I don't show you in the data sheet。You'll be able to find that out。

 And this is how you can do that。First， you would take this hexasmal number and expand it into its binary form。

This can be expanded into binary form you'd end up with 32 bits。

 which is equal to the size of the register。If you expand this， you realize that you find one。

You find 0，0，0，0，00 and one utter parts position。The position where you find one。

 when you expand this。You would find that that corresponding position of the register。

Deals with where the flag is。 You would see that this corresponds to the part of the register。

 where the flag needs to be set or， you know， reset。

 So that is why often I can just write this and assume you can be able to reverse。

 engineer it since we've spent a lot of time in the in the data sheet and reference manual already。

 So if you have any questions， just let me know。 But anyway。

 we're going to apply this here to this register。And this is for the count flag。

Cot flag like this and the next one is to we would have to select the clock source。So see Nvi。😔。

Set and then see okay。😔，Source。And I say EQU。And then we're going to set the on clock source to be the processor。

And then we use this Exademal number to select the processor or internal clock source if you were to use external clock source。

 we would have to pass a different value to this location of the register。

I'll say clock source over here。😔，And then the next one is the interrupted enable。

 because cysttic is uninterrupt。 We've got a enable interrupt。 So Ill say Nvi S T。And control。U。Well。

Interrupted neighbor， we're not gonna use that in this lesson when we are dealing with interrupt。

 We deal with that。And then。Yeah， I'm gonna， I'm gonna make a number of。

I'm going give you a number of cystic examples。 Yes， cysttic is not always uninrupt。

 We have a cystic interrupt， and we can have the cystic timer without having the interrupt handler。

So we're deal with the the interrupt bit when we talk about。When we talk about the。

When we get to the dissection on interrupt programming in in assembly language。

 but I'm going to keep the symbolic name for interrupt here since when we get there we can easily make a copy of our current cyst project and then build upon that to create the cysts word interrupt。

 So I'm going to add what we need to enable interrupt over here， although we won't use it。

And just bear with me， yeah。So for interrupt enable， were going to。Pass this hexademal number。

And well， I'll show you this。 I keep saying you can expand this and see the meaning。

 Let's go back to the the generic user guide。 This is the generic user guide。

 the one that we took the register names from。 So this' is the register we are dealing with。

 sister control register。 You can see the bits 0，1，2。

 These are the bits that we use from3 to through 15。呃。These are reserved。

 bit 16 here is the count flag。That is why we have this for the count flag this here corresponds to bit 16。

Right， and then we have。Interrupt and enable。 Interrupt and enable。What did we pass for there。

We pass the number two， the number two here in binary is 01。 This means bit number one。

 and this is called tick int， meaning tick interrupt and if we want to verify。We can come over here。

 and naistic exception request。 Exceptception is the same as interrupt。0。

 counting down to 0 does no aistic exception request。 Okay。

 so this is the register we're dealing with。 You can read more about it。 This is the， the cortex M。

 This is this document here。Generic user guide， right。Okay。

 so this is war interrupt interrupted Naval。And。We've got a enable counter mode as well。

 We've got a greater symbolic name for。For setting it to counter mode， I would say。I'll say NVic。S T。

Control。Enable。And this would actually enable would assist the counter。Let's see。

Let's see our will register again。 This is bit0。 bit 0 is for enabling the counter。

 We can read about it。 Bi 0 here enables the counter 0 means counter disabled one is。

Cant enabled would end。In summary， you can think of it as a neighbour a timer。Right。Cause the timer。

 I mean， it's loosely used， it's used loosely defined as a counter。

 time and counter can be used interchangeably， although there are differences。

One of the differences is account is when the clock source is external and the timer the clock source is no external。

And yeah， but often you find the the two being used interchangeably。

 The reason why in the data sheet， it says counter enable is because we can enable。

We can enable counters for up counter in down counter。

 you could have an internal clock source yet they will write something likeU counter in down counter。

So the the word counter is a bit loose。 It's not very concrete。

And I'm not sticking to the script here。Just bear with me yeah。For enable counter enable。

 which is the same as enabling the， we would pass this value here。

 and we saw that correspond to bit number 0。 That is why we write this into the register。Right。

 and then we're going to have the load value。This is a counter mode。This means counter mode。And then。

 I'm gonna。I'm gonna create another symbolic。Value here or symbolic name。I'll say Nviic。SD reload。

M like this。And E Q U。And。I'm going to pass this why does the maximum load value cyststic is that 24 bit timer。

We can read about it here。For those of you who are not aware， N see。😔，Where， okay， it's over here。

 The processor has a 24 bit time system time assist count down from the reload value to0 reloads。

That is wraps to the value in the assistic railload value register on the next clock edge， right。

 So it's a 24 bit timer。And that's why half this here。This is2 four bits。Right， so I'll see。

Counter load value。Okay， okay。Looks good。 So these are the the stuff for the assist timer。

 So we're going to create a delay using an assist timer and because of this。

 we're going to need our LED to， so we need to make sure we need something to show us that it's working。

 So were going to enable our import in and then get the LEDs to blink as well。

I'm going to bring in the registers for the LED， We've already。



![](img/c5687853e2111b7e9d69dc90e28bd2d2_11.png)

D that。 so we need not do it again。 These are the the registers that we need for the LED。

 And we said our nuclear board， the LED is connected to。To be a 5。

So I'm going to create symbolic names for LED on LED off。

And then we've got a set mode 5 to output thats what this means over here。Right。

 so once that is done， we can start writing our assembly code。Okay。

 how about we we write the code in the next lesson because this video is getting a bit longer。

