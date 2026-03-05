# 【从零开始学习 ARM 汇编语言II Udemy】 p34 p33 08.3. Coding  Writing the GPIO Output Driver -BV1RJU6YwEM8_p34-

Hello， welcome back。 So let's implement our GPI your driver。So I'm going to start with the。

With the directives。 And for those of you who don't know。There is a pre requisite for this course。

 before you take this course， I expect you to take the M。Theum。

Im assembly programming from ground up course。And in that course。

 we went through the instructions step by step， the directives step by step who explained everything。

 So over here。I'm not going to be explaining the instructions and the directives much。

 I'm just going to I'll be demonstrating how we use those instructions and directives to write usable drivers for our microcontroller board so。

For those of you who haven't taken that course， I would suggest you stop this course and then go view the first few lessons up to the point where you view the lessons on directives and instructions and then you can continue here you can send me a message I'm going to send you a coupon for that you need no you know buy it at its expensive price。

So I'm going to start off by yeah， using the area directive。Text。In this decocode area。

 it is read only。We're going to align two。So thumb over here， theres the entry。😔，And then。

 I'm going to export。Underscor underscore mean like this。Let's go let go main。

And I'm going to start off by。En I'm going to start off by branch into a subrot to enable our GPIU or call this GPIU in it。

And then。Let's implement a GPI units now。GPR you underscore in。So we start off by。

Enab the clock access for port B if we had to write this environmental embedded C。

Using CMms orll do C control like this。And then RCGC GPPIU。And then I'll use this。

 I'll put a verticaltic sign for all。And then I'll take this symbolic name we created。Right。

 and this would enable clock access to port C。 This is a comment， right， in assembly。

 So this is what we're going to implement。So to do that， we need to load the address of this GPRU。

CGC GPPIU。So I'll see load。R 1 equals。We have the address here。And then I'm going to sort load。Take。

Basically， to use this in plain language， what this is， I'm gonna say， take R 0。I do take。

So basically， this means take。Take the content off。How do I put this in plain language？

Take the content of what is located at our1。And put into our sro。So something is located at R1。

 or R1 is pointing to something。Take the content of what R1 is pointing to and put into R0。

 so in effect we take the content of the current content of system control RCGC。

 GPI register and put into R0， I'm going to perform an all operation of that。When I say oh， I Siro。

A Siro and then。GPIU enable。So。So after that， after this line， what is in。

This register is going to be put in R0ro， so we're going to take what is in I0ro and then we perform an all operation with GPIU F enabled。

 which is the symbolic name we created here。And store it back into our0。 We can use two operas。

 If we use two operas。 It means the result， this is the source number two。

 as well as the destination。 So we can keep it like this and it's going to be stored in our0ro。

Rightr once that is done， meaning with modified what is in R0 now。

 we can write the new content of R0 at the location of this register。In effect。

 at the location of this。At the location of this address， the reason why when I say register。

 I always freezes that。We've got Regs R0 R1， R2， R3， and this is a register too。

 but when I say this register， are you thinking is it a cortex， is it the？

Is it the system control RCGC register or is it the register in the register Bank such as R or R1。

 so what I'll do is I'll endeavor to call these addresses。

 although their registers are referred to them as this address rather than register to limit confusion。

Anyway， if you， if at any given point， you， you have a question， just send me a message。

 I don't know how this is going thus far， cause I keep explaining random stuff。

 But should you find yourself confused about in a little thin， You can send me a message。嗯。Right。

 so we're going to use the store instruction。 I'm gonna say store。The source res R 0。

 and then R1 here。 So after this， we would have executed this。Right。

And we can allow some time to finish activating by using the no operation NOP。NOP NOP。

 this would just allow some time as like here。Wait a bit。O。

So now the next thing to do would be to set awa。Our pin to output pin。 Our red pin。Read over here。😔。

We need to set it as output， and we do that by accessing the GI F direction register。

 So in C language， I'll do GI U F D IR。And then I'm going to say0 x。0，2。I'm going to do this。

 but we've already created a symbolic name for 0 x02。As should point out x02 is the same as。

Is the same， I。Is the same as this。 Why do I say that， Because if I expse your X2 to its binary form。

 I'll end up with。Z， B，1，2，3，4， and then one，2，1，0。Right。So this0， this hex that's more0 this。

Sorry about that， this hex decmal zero corresponds to this four binary zeros。This too in binary form。

 will give us this。This too here。If we convert it to binary，4 bit binary， this is what we get。

 So this is the same as shift shifting one at position number one， bit number  one。

 So this is bit number 0， bit number  one。 So if I do this。I'm saying shift one to bit number one。

 which is the same as have in this。Which is the same as having this in Hxademo code。Right。

 and we gave a symbolic name to this， this shift one at position number one。We call that LED red。

So I'm going to copy LED red and put it here like this。嗯。I'm gonna see。Like this。

 I'm just going to over comment this， okay， right？As the course goes on。

 I'm going to reduce the amount of comments I use。 Okay， so this is the C language。

 Let's do it in assembly。 I'm gonna see load。R 1。GPIU F。DIR， register， anddent。Ld。😔，Our0。R1。And then。

 I'm gonna perform or。哦，2C2C。I can use a single upund。Over here I had to bring the number sign。

 sorry。LED red。Then I can write it back by using the store operator or operator store。

Store instruction， I should say store。😔，Like this。 Okay， now we have set this as output。

I'll put more comment here set。Pf1。U output， that's what we just did。Enable clock。Access to port F。

Right， that's what we did here now。We're going to。Digally enable。😔，P F1。So to do this and C language。

 I would do GPIO。F DEN for digital enable register。And I'm simply going to do this LED red again。

I'm writing the same thing， but this time to the digital enable will register。Right。

 so in assembly language， how about you try it， Could you post the video and try to enable this in assembly language。

 you can look over what we did over here and over here。Right， so once you are done。

 we can do it together。I'm going to do load。I。E callss GPIU F。D ENR。And then load。😔，I sure。I won。

 and then。Or。I0。LED red。And then store。😔，R0， R1。Once that is done， we are done with the subroutine。

We can return from the sub routineout by using the BxLR。Like this。Okay。Right。So now we are done Next。

 let's write a subrout to 10 on the LED。 I'm going to call this LED on。Going to come over here。😔。

And have。Sorry for that。A lady on over here。And then。😔，We start off by loading the。The data register。

 remember。To turn it on， we need to write one to the Pf。To Pf1 of the data register of port F。

And because the LED is connected there when we write one that the LED in effect will be turned on。

So I'm going to just show you how to do this in C language。😔，G P I O。F。Data。And then this。

We can use friendly programming again。Is simply right in。😔，LED red， I think， yeah。😔，Okay。

So I'm going to do load。I'm going to load the address。I have a typo here， there should be DIR。😔，Okay。

 so GPIU。F。Data。😔，On the school R。And then。This is going to be a simple move。Oh。

 do you move into register R0。LED red。And then， store it。And then。BxLr。And then align。And then end。

Right。O。Okay， we look good。So what I'm going to do is I'm going to call this subroutin as well。

So we start off。Bye。Enabling our GPU， once we've done that， we're going to branch to turn on the LED。

And then we're going to create a loop by branching。By branching to the top over here， P。

Such that after we turn on the LED and we execute this next line。

 it's going to take us back to the top and back to the top， we come back， we turn on the LED。

This is going to take us back to the top， in effect， this is our wild one loop。

So now let's test what we have。Right， so I'm going to set up my debugger or come to target options over here under debug drop down still there is IDI。

I'll click on settings。😔，And then I'm going to click reset and run OK， and then OK。

And then I'm going to click here to build up here。😔，It's built successfully。

 click here to download onto my board， it's downloaded。And my LED is not on。 Let's see。嗯。

let's check our code。From the top。I think the reason this。

 the reason the LED is not blinking is from the system base， the system control base address here。

I'm sally bother this address， let's go to the data sheet in D see。嗯。



![](img/2ba7e7c8fb40dcbd6d325b57c8e2406f_1.png)

Come over here。 I'm gonna search。I'm gonna search system control base address。

And then it's Pro me here， we can start from the top， a simply type system control base address。😔。



![](img/2ba7e7c8fb40dcbd6d325b57c8e2406f_3.png)

And then is Pro me here register map。😔，Sa as the offset list that is access as more incrementalcrement to the registers relative to the system control base address。

So it says this is the base address of the system control。 So I'm going to use this instead that。

I'm going to copy this and I'm going to search more and see whether this is the persistent base address given to system control base address。

Over here it talks about system control Reg description。

 all addresses given a relative to system control base address。

 and this's the system control base address。And register provided for Le software support。 Okay。

 so it's the same address we saw earlier。

![](img/2ba7e7c8fb40dcbd6d325b57c8e2406f_5.png)

Right。Okay， it's the same thing。Right。Right， so this indeed a system control base address。

 I'm when I use that。So yeah， taking the system control base address from the RCC base address won't work。

Yeah， sometimes they are such nuances， and with experience you'd know what to look for。Okay。

So now let's try， I'm going to click here to build。Click here to download onto my board。

And it's downloaded right， if you have any questions。

 just let me know and I'll see you in the next lesson。



![](img/2ba7e7c8fb40dcbd6d325b57c8e2406f_7.png)