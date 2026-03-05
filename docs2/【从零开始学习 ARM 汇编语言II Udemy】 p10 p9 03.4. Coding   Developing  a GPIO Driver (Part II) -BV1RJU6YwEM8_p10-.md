# 【从零开始学习 ARM 汇编语言II Udemy】 p10 p9 03.4. Coding   Developing  a GPIO Driver (Part II) -BV1RJU6YwEM8_p10-

So welcome back。 this where we left off。 We went to the。

We went to the data sheet and the reference manual to get the memory locations of our registers of interest and then we assigned symbolic names to them。

In this lesson， we will go ahead and arm。Instead start writing the initialization， you know？

Subroutine for our GPO A driver， So when the code starts。When our applications start。

 we start from the main， right， So as soon as we enter the main。

 we're going to branch into a separate that we will create。 So over here I would say。

I'll center out this a bit。Like this， Okay， so we start from main over here as soon as we enter main。

 I'm going to I'm going to say。BL branch to the subroutine that we shall call。

We shall call this GP U A in it， GP A underscore in it。

Just bear with me as I find a right indentation to use。😔，Okay， just bear with me。

I think we are good here， Okay so。As soon as it start BL GIU。GPIU in it， So let's implement this。

There label GPIU in it。And we do this to implement a label。 Okay。

 so first I'm going to be putting some comment to show what this looks like in C language so。In C。

 we would do environmental， we would do RCC。And then we'll access the AHP1 enable register。HB1。

 E and R， and then what we're going to do is set this to the GPIUA enable， which is 0 x01。

Right 0 x 01。 The reason I'm cleaning this is I just remembered it would be better if we created a symbolic name to hold this。

 So this we're going to create a symbolic name to hold this。This as well as the pit for。

As well as the bit for turning the bit for setting to output mode in the mode register。

 So we can say dot EQ U over here。 And then I'm going to call this GP U A。

Enable GU A E N and GIU A E N basically means。Shift 1 to position  zero。

And we can come over here and do another one EQU， and this which we use to set our GPIU。

GPI 5 GPI or a pin 5 to output。 So I'll call this。 I can call this。Moot register 5， Mo 5 out。

And we do this by we know what we do， we just shift。1 to position number 10 like this。

 because we have to set a bit 10 in the register to one together this to save as output。

 and then we can have LED on。 We can have a symbolic name Do 10 on the LED。 So we do E Q U。L丽迪。

LED underscore on。 and then this。 we simply know we set bit number 5 to1 to 10 on the LED。

 We can do LED off if we want。 And I know you will guess what that is set bit 5 to 0 as simple as that。

 So now that we have the symbolic name。 we can copy this。And then okay， so in our comment。

 we know to enable GI a。We do this in sea language， okay， in assembly。What we do is de load。Load。

 operate， and then write back to memory。 So we're going to load this into register R0。

 We're going to load。This we're going to load the address。So I'm going to start off by saying。

I use the cupsier load。Rciu kma。And what we want to load is HB one enable to register。

OurCC AHP1 enable will register this one here， we want to load it into our zero。And then one。

This means load the address of， you know， AHP1。I think I should put comment here。Lad address。off。RCC。

AHP1 EN R。To r0。And we know that。 We know this。Hosse the address， this symbolic name holds it。

 And once we've done this， what we want to do is。Load the value at the address found in r0 into R1。

So what we want to do in layman's terms， we want to get the。Current content of this register。

 which is the memory location， this memory location， which is adding these two numbers。

 We want to get the current content of that。And another way of saying I load value at address found in register r0 into r 1。

Because register R0。Has the address we want。The value at this address， we want to load that into r1。

Yeah。If you don't understand this， if you don't understand this。

 just leave it in the questions and answers area。Okay， so I'll just say this。F in。20。Into R1。

 right to do this we do。Load。And then we do r1 like this and then square brackets r0。Okay。

So then our now would have the current content。Of the memory location。

 which is the RCC underscore AHP1 enable register。 So what we want to do is we want to perform an all operation。

With our GPO A enable。 and by performing all operation， we don't change the current content。

 We just add our new bit enable to its current content。 So what I'm going to do is say。

Take the content of Reg R0。All it with GPIU A enable and store the resort back into our0。就是哦。

Over here。So， take the content of register R1 because after this instruction we'll have it into R1。

 we have the value in R1， take the content of Reg R1 or it with GPIU A enable the symbolic name here。

It's an immediate value， so we use this pound sign and then put a result back into our one okay。Yeah。

I'll see over here。There is no relevant comment here。 I think this is straightforward， okay。

 so once this is done。After this， we should have。We should have the right。

 the right bit arrangement to set the pin。 We have to write it back to memory。 So after this。

 the content of our one would have our new。32 bit value would that preserves the initial state of the AHP1 enable register。

 as well as enables GPI report A。So。What we have to do next is say store the content in R1 at the address found in R0。

Okay。Yeah， we make an assembly sound like it's just normal English language。 We say store the。

Content in。R1。阿弟。Add dresss found in R0。This should be one， no exclamation， goodness， I'm losing it。

Okay， so how do we execute this， We use the store operation， the store instruction。

 we say star and then。This is the source， and this is the destination。

Store the content in R1 at the address found in R0。 Okay。

 so after this we would we would we would have enabled our GPU A。



![](img/b525e477a0e2476d09232e5b01e01b3f_1.png)

Clock access to GPIUport A， the next thing we have to do。



![](img/b525e477a0e2476d09232e5b01e01b3f_3.png)

Is set our GPIU mode register when I set GPIU。P， a 5。To output pin。 So next we have to do GPIU A。

More to register。And then we want to pause。Moode 5 out。To it like this。

 So we start off how about you pause the video and try to do this， given what you've seen with this。

 try to do this on your own。 And once you've tried， we can do it together。



![](img/b525e477a0e2476d09232e5b01e01b3f_5.png)

![](img/b525e477a0e2476d09232e5b01e01b3f_6.png)

Okay， so to do that， we do load。And then we do R0 equals。GPIU A underscore mode register。

 I'm not going to comment this much。And then we do load。R1。OurC room。

And then we do the all operation or。Or， we do our one with。Moode 5 out this constant that we created。

And then finally， we stole back to memory。Which is the register， which is yeah。

 the memory address stored in the register store。R 1。R0。Okay。Right， so after this。

 we would have GPIU。Pt a pin 5 set as an output pin。

 and if you do not understand how this accomplishes that。

Then please start watching the video from scratch again or leave it in the Q&A area。

But I'm sure by now， this is like very straightforward to you。Okay， next， we need to 10 on the LED。

 And what we do to turn it on is basically set bit number 5 in the output data register to one。

So in C language bare metal would would GI your A。5敌2。And then if we want to do friendly programming。

We can do this。LED on， but if we don't care about the other bit， we can simply write this to it。

And this。Verical line， if you've noticed for those of you with them。You know， there's a few who can。

 yeah， analyze。You realize that this is equivalent to our all operation that we always do here。

 So if I remove this， for instance， in this example。

 we won't use this so we wouldn't need to do the allwe。 So let's see how this would look in assembly。

I would simply do load。Our0 room。And then， the GIU A。ODR。Once that is done。

 I'm going to load LED on into a different register。L on here。

 I'm going to load this into register R1。So。Load。Register R1。Equals LED on like this。

And once that is done， I'm simply going to store。What is in Reg R1 at the memory location held in Reg R0？

R1 over here in R0。Right。And once this is done， we can return from our subroutine by doing BxLR because we are done with this subroutine。

 BxLR means return。O。And then we can use the end directive to indicate with ended。Right。Okay。

 so this is our program so far。 It starts from main。

 and then it branches to the subroutin GPIO in it。 And then when it enters here。

It would enable clock access to GPI port A。It would。It would set GPIO port a pin 5 to output pin。

And then it would set GPIU8 pin 5 output data register， bit 5 to1。

And this would turn on the LED because the LED is connected to P5。

And then we return from the subroutine。 And this is just to indicate this' the end of the assemblyifier。

 So what we want to do is。Yeah， we can leave it here。

 let's build it and see orll click over here to build and let's see how many arrows we've created。

Okay。Right， we have  errors with our symbolic name assignment。 Okay， so the reason why that is， yes。

 So as you do this， as this becomes your job and you do this， you will start mixing syntax。

The syntax is different in the arm asmbler over here when you do not equal you and you give your new name。

 you've got to put a comma here。So let's just put some commerce and let's see if this fixes the arrows。

So I could pull comma， I have a comma here。😔，And then come everywhere。😔，Okay。Think I may have clean。

Motor。Okay。Coma here as well。😔，Come on here。Comma everywhere， Everyone gets a comma。😔，Comma。

 and then。Now， let's see what we have。I'llCl to build， let's see how many arrow we have left。

We have four， okay， what's the cause？1。O R one， it says onshifted register required onshifted register required。

 or R one this。On shift of register required a set。Right。

 the reason for this error is the lack of another directive。

 We're going to add another directive to indicate the syntax we using。

 So I come over here and see do syntax over here and I'll say unified。Unified like this。 Okay。

 so let's build and see。 click over here to build。We have two arrows it says， let's see。It says。

Ondefined symbol mode 5 out。Let's see。 Mo 5 out。 Let's see。 Maybe we have a typo。 O。

 over here to written mode 4 is mode 5 control S to save。 Click over here to build。It's billed in。

 it's billed successfully。Okay， looking good。 So we've written our GPIO driver in assembly。

 let's see if it runs and if it turns on the LED， I'll click over here to go to debug。

And then click this and then OK。It's open， I'll say okay over here。It's download in。Okay， it's done。

 I'll click here to run。And my LED is on。Okay， so that's the end of this lesson。

 if you have any questions at all， just leave it in the questions and answers area and I hope you're enjoying the course。

This is really simple if you have any questions。Just leave it there or if you leave it in the Q&A section and you're not receiving a quick response。

 you can message me。Just remember the directives。The directives and then the symbolic name assignment。



![](img/b525e477a0e2476d09232e5b01e01b3f_8.png)

And then the rest。As the comment states here very step by step。Okay。



![](img/b525e477a0e2476d09232e5b01e01b3f_10.png)

That or I'll see you later。So for those of you who are watching this in the Kber mix。

CubM X cube IDE course if you want to learn more about assembly programming and how to write drivers for other peripherals like the ADC the timer and to learn the complete arm assembly programming you can take a look at the arm assembly programming course there is part1 and part2 and after that you'll be able to write your complete firmware an assembly But for those of you watching this in the arm assembly course just to show you how to create the project in cube IDE。

 then you already know what I'm talking about。 but we going we're not gonna to dive deeper into assembly。

 This is just to show how one who go about creating assembly assembly project in cube IDE Next what we're going to do is we're going to take a code created in the CA MK using the arm assemblyr and then we're going to bring it here and change it to run on the cube ID which uses the Gcc assemblymbler so that we can see that is basically the same thing。

We simply need to change a few directives， So we're going to do that now。



![](img/b525e477a0e2476d09232e5b01e01b3f_12.png)