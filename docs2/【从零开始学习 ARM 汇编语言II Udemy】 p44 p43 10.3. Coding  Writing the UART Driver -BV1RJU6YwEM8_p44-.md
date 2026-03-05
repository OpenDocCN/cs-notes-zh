# 【从零开始学习 ARM 汇编语言II Udemy】 p44 p43 10.3. Coding  Writing the UART Driver -BV1RJU6YwEM8_p44-

![](img/cfadd29ee48ba00c2f0d82ea4505529b_0.png)

Hello， welcome back， so let's develop OU at driverver。 I'm going to create a bit of space over here。

I'm going to start off with our directives。Area。Dot TXt。And then there's the code area。

Just read only。We align。Then thumb。Thiss the entry。We' gonna export。Or main label。Right。And。

We're going to start off over here underscore underscore main。😔。

And we're going to branch to first up routine， not as you add in it。😔，Right。

 so we start off by implementing our U in。You are in it。Like this。Okay， this is rather far away。😔。

而且是。Move this a bit。Right。Okay。So were going to initialize the U add。

 I'm going to start off by pushing the link register。Saveing the current value of the link register。

 as it is。And then next， I'm going to load a wire。Or U at RCGC register and then enable clock access to the U at。

 So do load。Or one。Because。Cis control。RRC GC， U。Under the score R just the name of the register。

And then I'll take what is in this register and put it in R0 like this。

And then I'll perform an or operation。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_2.png)

With our symbolic name you at enable。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_4.png)

Where is it。You are zero enable。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_6.png)

And once that is done， I'll write the result back to the register。😔，Right， once we've done this。Okay。

😔，Once we've done this， we can enable the clock access to GPI port A。And。

For those of you who are not familiar， yeah， I'm wondering about this。

 I'll just put a sea code here in sea language。This is going to be。A thinkis control using Cmis。

It's going to be ci control U at。Oh， control R C G C U add。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_8.png)

And then all。😔，You at zero enable。 This is what we type in sea language to get this impal embedded sea。

Right， so the next thing we're going to do is。It's going to enable clock access。

For our GP you poured in。So I'm going to in C language is's going to be ci control。R CGC G P I O A。

 No， R CGC G P I O。And then。It becomes GPI U A E， N over here will perform an or operation for that。

 So I'm going to do load。In assembly， we do load。This is control。RRCGC GPIU。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_10.png)

Let us go R， we take what is in there and put it into register R 0。

And we perform on our operation with。With our。GPIU A enable。And we thought to register back。😔。

We store the results back into the register like this。😔。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_12.png)

Okay， so this will enable clock access for GPI report A。

 the next thing we're going to do is were going to set。We're gonna set our you at pin。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_14.png)

For alternate function。But before we do that， we can digitally enable our U pins。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_16.png)

P is0 and P 1。 We're going to digitally enable them。 I'm gonna come over here and。I'm gonna do。

And C language。 I'll do G U A。Digital enable registerister。And I'm simply going to。

I would sort of write this。This will correspond to the bit that this corresponds to the bit for。

GPU pin A and GPIU pin one and GP IU pin 0。Right， so I'll do this。In an assembly。Load。A1。

We have GIOA。D E，N underscoreco R。Then we take the content。😔。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_18.png)

Put it into r0 like this。We perform an or operation。😔，Of R 0 and。0 x。0，3。Oh， three。Remember。

 this is the same as this。All this。All of this。The zero before the digit doesn't matter。Right。

So after we do this， we write the resort back store。Rro， R1 like this。Okay， so once that is done。

 we configure that you at we go to the port control register。

And then we first cl a port control field for PA1 and PA0。

 and then we write new values to that field。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_20.png)

Okay， so I'm gonna。This。Let see。In C language， we do GPIU A。PC T R is the port control register。

PC T L， it is。 And then what we're going to do to cl a bit， we do。嗯。

Ambund equals and then until day over here。 And then we're going to use this hexademal number to clear the bit for。

For what you call it。For P 0 and PA1。Right。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_22.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_23.png)

Okay， so I'm going to。I'm going to implement this。And once we've cleared a bit。

 we would need to sort of。We need to。We need to write a new bit to it。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_25.png)

We need to configure the P0 P1 as you add in the port control register。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_27.png)

So I'm going to load the register。😔，Load r1。Equals GPIU A。😔，Pi。😔，CTL on score register。😔。

And then we're gonna take it content and put it into r0。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_29.png)

Then， we're going to。Cled a bit using the B IC instruction。Then we start the result back into R0。

 we cleared a bit of what is in R0。Clare these using this exademal number。

 and then the result is pulled back into our0。 we could use two opera here if we want。

By I'm using Aio， if I use just this it' the same as this。 so you need not worry。

So once that is done， we're going to configure this the same bit。

I will use End the results after clearing is going to be put here。

It's going to point to our0ro so I'll say R0。End。And then I'm going to configure。

P A0 and P1 as you at is the same as saying Aro Aro。

 The third operaran is the destination in the case where you don't add the third operaran。

 The second operaran becomes the second operaran， as well as the destination。Right， so this。

Did you do this for us？Did we deal with the alternate function register？We've not dealt with that。

So I'm going to enable the alternate function register。I'm gonna put that up here。OCGPIUA。

Alernative function select。And what we want to do over here。

It sets P A 0 and P A1 to their alternate functions。

 Soll pass this here like this to do this in assembly or do load。R1。GPIUA。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_31.png)

Alternate functions select to register。Take the content。😔，And put it into R0。And then。

Perform an or operation。With this。And then， store it back。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_33.png)

Like this。Okay。Right， so once we are done with this， we can start configuring the U at。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_35.png)

To configure you as we start off by disabling it。So we're simply going to disable the UU。

We can just write0 to the U at control register so that everything in the register set to 0。

 or we can just set the particular bit， the enable disabledable bit in the register to 0。

 If we want to set a particular bit to0， we have to use the M。PIC instruction， so let's do that。

Start off by doing load。R1 with a U at control register。You add 0。C TL underscore R。

 and then we're going to take the content。😔，Of the register put into our0。

And then we're going to clear it by doing BIC。Store the result in R0， take r0 and then。

Apply U at control enable， which we created a symbolic name for。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_37.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_38.png)

This one over here。Right， and then restore the resort。R0， R1 like this。Next。

 we configure the about rate。We're going to access the two bo rate registers。

 the one for the integer part and the fractional part。So， I'm gonna say。Load r 1。

Board rates register。And the name we gave it was。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_40.png)

It should be up here somewhere， let's get the name。😔，This is the first one。 U at IBRTR。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_42.png)

This is the integer board rates to register。We load this first。And then。And then。

 then we compute the board rate。 So to compute the board rate， we have to。

Divide our clock frequency by 16 multiply by the boat rate we want to use， remember。

Popular board rates that we often use include。um。Popular board rates include 9600。1，1，5，200。Et ceter。

So to compute the value to put into the birth rate inte register。

The formula is to take our clock frequency。 The frequency of my MC U is 16 megaHtz。

 meaning 16 million。I'll take this 16 million。And then， I'll divide by 16。

Multiply by the board rate I wan to use。 Let's say I want a board rate of 1015，1000。15 and 200。

 Sorry，115200。Un I want the board rate of 115200。I'm going to compute this。

 I'm going to do 16 million， divided by 16 times。115，200。 if I want this output this year。

 if I want a broad rate of 9600， I'll multiply this existing by this。 If my frequency is different。

 let's say I'm running at 50 MHz， I'll have to change this 16 to 50 to half 50 million。

 but I'm running at 16 MHz。 This is a constant。 So these are the two variables。Right。

And when I compute this。When you perform this calculation， you would get。8 point。6，8。0，5。

So this is going to be the answer， this is the integer， the integer bitier is 8。

 so we've got to take this8 and put it into the integer board rate register。Right。

So what I'm going to do is move this to the to the register。So， I'm gonna do。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_44.png)

I'm simply going to use the move instruction to achieve this。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_46.png)

Or do move。Move。21人。The number 8。And then I'll store it into the Integer portrait register by to install what is in R。

Thats our like this。 Okay， so now we've sorted out。 we've put just this 8。 How about a fraction part。

 Ca it's not complete。 We're going to store a fraction part in the。A fraction register。

So I'm going to load that。I'm going to do load。R1。E course。You are 0 FRD。Fction。Bd rate is FB R T。

 yeah。On a school R。And to compute the fraction part。We use a different formula。 We take the flux。

 we take the。This part here。This fractional number we multiply by 64 and then 0。5。

 so we take what is left here。That is gonna be。This is going to be 0。6805。Multiply by 64。

What supply by 3。5。And the answer we'll get will be 44。052。So this time we just take this as well。

 we don't care about this last bit is fine。So we're going to move 44 into register R0。

And then we're going store it。Right。So once this is done， we have to set our。Our web length。

 the data length we want to use， and we do it is by accessing the line control register。

So I'll do LDR。I 1。I want equals。You are 0。L C R H underscore score R for register。

And then we're going to do。😔，LDR。😔，20。We take the content and put it into our receiver like this。

And then once we have that。We're going to。We're going to disable。 we're going to clear all fields。

And we can do B I over here。BIC阿uu。F F。And once we've done that， now we can set the width。

As well as enable。 So I'm going to do add our serial and our se， sorry。And ourro， ourro。

And I'm going get the symbolic name we created here。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_48.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_49.png)

I'll get this。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_51.png)

And then I'll include P0 and nal as well。 I'll get  P0 a nal。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_53.png)

This one here。Bring it over a here like this。And once that is done， we can store。

We use the slow structure， S T R。20。A one。Okay， so finally， all we have to do is。

Enable a UU because we disabled it。When we started， so we access the control register， O DR。R1。

You are0。CTL underscore R。And then。We move the content into register our series like this。

And then we perform an or operation。We created a symbolic name。Called U at。Ctl。😔，You got E。Right。

 and then we can store。20u。A1。 Okay， so because we pushed the link register。 when we started。

 we've got a pet。to pop。Elar， I'm got to。唔关注。😔，I'm going to pop the L here。😔，That she。Yeah。Okay。

 so this is going to be a。There's going to be our U at initialization sub routineoutine。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_55.png)

So the next thing we've gotta do is。Create other subrs for for reading and writing data。



![](img/cfadd29ee48ba00c2f0d82ea4505529b_57.png)

Okay， so let's do that in the next lesson。