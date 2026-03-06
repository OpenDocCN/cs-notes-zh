# 【从零开始学习 ARM 汇编语言II Udemy】 p09 p8 03.3. Coding   Developing  a GPIO Driver (Part I) -BV1RJU6YwEM8_p9-

Hello， welcome back in this lesson we are going to see a much more practical assembly example with the cube IDE and what we're going to do is write a GI or driver using just assembly code。

 we're just going to go to the we're going to start off by going to the data sheets。

 the reference manual and the other document and extract the memory addresses and then assign symbolic names to them and then access these memory addresses or locations using our assembly instructions and manipulate bits So I'm going to create a new project I'll come over here file。

And then new ST 32 project and it's going to initialize the target selector。



![](img/318a039f99789a3a787999222b687b4c_1.png)

And I'm going to select my board。😔，Over here， SDM 32 F 411 VET。Ete T 2 F411 should be fine just this。



![](img/318a039f99789a3a787999222b687b4c_3.png)

I'll make a selection and then I'll click on next。Next it down there， I'll just drag it up a bit。😔。

Now you can see this is next。And then I'll give this project a name。GPIO underscore。Assembly。Okay。

 GI your driver。about well let's just keep the name so that we have the bare metal and then assembly。

 but they are both bare metal Okay， I'll click next to over here and then finish。I'll say no。

 but it's going to open the perspective regardless。😔，Okay。Okay。

 so I'm going to close this and then I'm going to come to our call folder this our project GPR U underscore assembly。

Okay， so。This is called。 like we did earlier， we come to source。 We don't need any of this。

I'll just delete the main， you can delete the rest。Actually， I think at the end。

 we should try deleting the rest and let's see if it's affect our project。It shouldn't， it shouldn't。

 but we'll delete it once we've tested it。Okay， so we said we're going to ride the GPU drivers。

The GPU yeah， driver for。For our board。 and we're going to use just assembly language。

 We already saw this in the in D。I mean， depending on where you are watching this particular lesson。

 if you are watching this lesson as part of the STM 32 QMX course， we've already seen how to write。

The beitto。The baremet GPU driver， if you're watching this as part of the the arm assembly course。

Then perhaps the baremet lesson won't exist there since that course is just about assembly。 In a way。

 ourll just stuff from scratchch。 and this will save us a revision if you already know some of this stuff。

 but I think there are differences between。The arm assembly and the arm。

And the GCC that we have to take note of， that is why we have this lesson， especially the directives。

A number of things change with regards to the directives， that is why we are here。Yeah。

 so let's get started， so we start off by we set。We said we。

We have to enable clock access to the port and then access the data and direction registers to get it to do whatever input or output okay。

Before we do that， we have to create our main dot S file right click new。This one here。😔。

New fall over here like this。And then I'll give it a name。Man does like this。Okay。Okay。

 so we said we have to take a number of steps。We have to。A enable clock。And they will click。And then。

We're going to be toggling the LED so a enable clock to port a。And then next， we've got a。

Set the mode。We say set。P5。To output mode。And then。We write to PA5。

So these are the things we need to do， but there's a lot of work involved here because we've got to get the memory addresses of each component so。

Let's start with our GPI port A because we need to access GPIport A we need to because we need to access port a for its data register。

 it mode register。And yeah， because we need these two register from port A。

 we need to find a memory address of port A to do that， we need to open one of our document。

 we need to open the data sheet document。

![](img/318a039f99789a3a787999222b687b4c_5.png)

We have the data sheet and the reference manual。 So the data sheet1 is the。



![](img/318a039f99789a3a787999222b687b4c_7.png)

The shorter one， the one with about 140 pages。So this is the data sheet。

You can just come up here and then you recognize it by this over here in the number of pages it's got。



![](img/318a039f99789a3a787999222b687b4c_9.png)

So we can find what we're looking for at page number 54。

 This gives us the memory boundaries of the various components。 I simply come to。

Our search arm 54 here。 We need page 54。 So our search 54。 Okay。

 so 54 here gives us the the register boundary addresses。 So when we search here will tell us。

These are the cortex M4 registers。It says from this range is reserved。

 this range is for internal peripherals。And when we come over here， GPIO A starts from 0 x 4，0，020，0。

 So this is the base address of GPIU A。Is the base address of GI U。 so we have to keep thy in mind。

I'm going to copy this。

![](img/318a039f99789a3a787999222b687b4c_11.png)

Over here。And then I'll bring it to our project。こうです。GPIUA。GPIO。ABs。O。This over here。

 we don't need this other stuff。 We just need a starting position， a starting point。Okay。

 so this is GPIU A base。 We would also need to get the arm。We also need the AHB。Remember。

 we have the AHB。The AHB1 enable Reg is what we use to enable the port。

 So we also need to access the AHB， the AHB。The AH B is part of the RCC。To access AHB。

 you go through the RCC， even in the data sheet it's written RCC underscore score AHB。

So whenever you see in the word， whenever you see one word underscore another。

The first word or the first characters or the first abbreviation is the base。

 The underscore is the offset is the same with GPI U such that when we see GPI U A underscore。

Moode register， GPI U A is the base address。 Mo register is the offset。 So for this arrangement。

Each module is the base is is a base address， and the various registers in the module serve as the offset。

 such that。We have the GP and we have the GPI your base address over here。If we want GPIU A。

Data register， output data register is just an offset from this base address。

 meaning we simply need to add some number to this to get the output data register。

 If we want the mortgage register is an offset from this。

 we simply need to add a number to this sum number to this to get that So is' the same for all port in the same way we know Rcc is written。

RCC underscore AHP， So if we want to get the AHP address。

 we simply add a particular number to the RCC because the base is RCC if you don't understand this explanation。

Please let me know in the Q& A area。 So we have to。Get the base addresses。

And then we find the offset， so。In in C language in baremet embedded C RCC we often do RCC AHP1。

 AHP1 enable register like this。 and then when we're dealing with GPIU A we probably do GPIU A。

We we probably do GPIU A and then mode to register and then this。

This that we see over here when we go to the reference manual。

 we see that this is written in there like this。Its written with the underscoreco。

 it's the same thing when we go to the reference manual we'll see that this is written in there。

With an underscore like this。Right， where but。More specifically。

 this will be written with an X to indicate that is the same， is the same for GPIU A， BC。

 the all the way to H。So I'm saying this bit is the base address。 This is the base address。

 If you want to get this。It's just an offset from this base address。

 so if you want to get this entire thing， it could be that you just take the base address of RCC plus2。

RCC plus2 could give you RCC A H B1 enable register in the same way if you w to get the address for mode register of GPU A。

 it could be the base address of GPIU A plus 5。 So you just add that to get the address of the mode register。

 This is what I mean by base address and offset。 So I'll just verify for you that indeed in the data sheet is written this way。

In the reference manual， sorry， so come to our document over here。



![](img/318a039f99789a3a787999222b687b4c_13.png)

And this is our data sheet。 It has the 149 pages。 I'm going to go to the reference manual over here。



![](img/318a039f99789a3a787999222b687b4c_15.png)

And then I'll come over here and。U住 controltr F。And then， A H B。Do AHP1 and when I hit En。

 you see that word starts with RCC underscore AHP。 This is for a a different register。

 but all of them are offset from RCC that is why they are written that way If we do AHP enable RCC underscore AHP1 enable register。

 right。

![](img/318a039f99789a3a787999222b687b4c_17.png)

Okay。Wu。So we have this one， we need the RCC base， the RCC base is already know this one。

 but you can go and find it out。So the RCC bay will be this in order not to spend more time hunting all of them down。

 I'll be putting some of them in， but when there is something different or pointed out we'll go and fetch together。

 RCC bases addresses this。0 x。4，0，0，2。380，0。 This is the RCC base。Right， so we've got。

The GPIO A base and then the RCC base， we're basically going to be dealing with these two bases because we know we need RCCAH1 enable register。

To enable clock access to GPU A。 And then we need GPU mode register。

 and then we need GPU output data register to set our pin to output and to toggle the LED， right？

 So what we have to do next is to find。The offset that would give us the other registers So for GPRU A。

I'll see for GPIU air over here， this comment will clean them later。

 I'm using this as the whiteboard for GPIU air。We need。We need the output data register。

 and then we need the mode register， so we would have to get the offset for this。And then， for RCC。

For RCC。We need the A H AH P1 enable register because that's what we use to enable clock access to GPIU port。

 A and all other GPIU port。So what we have to do to get the offset is go to the data sheet。

 but before go to the reference manual， but before we do that。

 I'm going to create a symbolic name to hold this number here。

To create a symbolic name or use the EQU， EQ U， Ausce dot。Dot E Q U here like this。

 This is a directive。 And what I want to do is I w to assign a name for this hexadademal number。

 I'm going to assign the name G， P I， O A underscore base。So this hex a decmal number。

Such that whenever I want to fetch this hexademal number。

 I simply use the name of assigned signed GPU Abase。Okay。So I'm going to do the same thing for RCC。

I'm going to say dot EQU here。And then I'm going to assign a name， I'll call this ourcc base。

Araisi underscore。Base like this。And then over here。We know the RCCB， we said this is it。Okay。

 I'll assign the symbolic name here like this。This is just comment， we don't need this。Right。

So we've got symbolic name for this。Then we would have to assign a symbolic name for we have to do an EQU。

EQU over here for GPIU。We have to do。Let's say E Q U for， let's do it step by step。 I'm gonna say。

GPU mode offset。We can do a symbolic name for the offset so we can see。GPIUA。M register offset。

So when we find the offset， we just put it here。We'll put it on the side。 We don't have this yet。

 so well fill we'll fill in the blanks and then we'll do。An E Q U。For GPIU A。

ODR output data register offset。And then we don't have this， so we fill in the blank later。

And then once we have the offset。Of this。Then we know the offset plus the base register gives us the actual base register。

 so we will。Go ahead and do EQ U。 And then now we can say GPIU A。Moode register。

 the actual mode register。And this。This is simply。This will be GPIU A basease。

This would be GPU AB over here。Plus。GPIU A mode register offset。Like this。And then once that is done。

 we come and then we do unecu you。Then this EQU will be the actual GPIU A output data register。

And you know how to derive that as well， is's going to be this offset plus the base。

 So for output data register， it's going to be this。Coopi。And then we paste this over here。

 but this has to change to the ODR offset。Like this。Okay， so after this。

We would have all our registers， the register be ready， we would have our GPIO A mode register ready。

 GPIO A O DR ready as well。So we will do the same thing over here over here we have we've already found our RCC base。

 What we need is A H P1 E and R base， AH P1 enable register base， so we do。EQ EQs， like I said。

 used to give a symbolic name to the hexademal number， so we say EQ H1 enable offset。

We do not have the offset yet， so we fill in the blanks later。And we know once we have the offset。

 we simply add the offset to the base， the RCC base to get RCC underscore score A HP1 enable so we do。

Dot EQU over here。And then we call this。RRC。A HB1 enable register just called just like it is called in the data sheet。

 and this is derived by ourCC B。Plus。AHP1 enable register offset。Like this。Okay。

So what we have to do is go to the arm。The reference manual and find the offset of these various addresses。

Right， so we go to the reference manual to fetch the offsets。Okay， I go to our document here。

We use in the reference manual， the one with the pages。 so we start with A HP1。Register offset。

 So you simply search A H P1。E and R， this is from the previous search we did。 So this is it。

 I'll click A H P1 E and R。 And as you can see， it gives us the offset over here in the data sheet。

 The offset， This means its， its keep in mind that we will be doing this type of thing。

 That is why it's given us the offset。 So we simply take this offset from here 0 x 3，0。That is。

A H B1 E andR offset。So this is0 x30。0ro x。3， zero， right。Is that correct，0， x 3，0， That is correct。

 Okay， so next， we find the offset for。

![](img/318a039f99789a3a787999222b687b4c_19.png)

Our GI mode to register。So I'm going to come up here。And controlr F to search。And then of such M。

 O T， E R mode register mod。Okay， and it brought us here。 I'll click here to jump to this place。

And the offset for mode register is 0 x 0，0， meaning is the first element is the first member。

 So the offset is the same as the base address。 So no problem。 We just set it just like I said 0 x 0。

0。

![](img/318a039f99789a3a787999222b687b4c_21.png)

So x。So X00 like this。 Now， ODR offset， the output data register offset this the register will use to control the output。

 So we search for ODR as well。I'll come over here， ODR like this， no， I have to clean first。

This doesn't exist， of course。O DR， okay， so we have this GPI report data register ODR or click this and the offset is 0 x 1。

4，0 x1，4，0 x1，4。 So we put that over here like this。To x。One4。Okay。So， we have this。Right。

 so we can clean our comments。 We don't need the help these。Comment again， enable clock。

 we don't need this。😔，嗯。Yeah， we don't need us。We know what to do。

 this was just to tell you what we're going to do or to remind you。Okay。So we can put our directives。

We can start off by。Just put in some directives about the CPU。We're using the Kotex M4。

And before here and then。Our cold area is down here。We can start our section code over here。

Dot section。😔，Lo text over here like this。😔，And then once that is done， we can。We can create our。😔。

Our global export。So I'll see the global。😔，And then we call this main。And then over here。😔。

Would have。I want man label， man like this， okay？I think we looking in good so far。Yeah。

 we no missing in it thin。 Okay， so this is it。We've got our registers。

 We've assigned symbolic names to our registers in the next lesson。

 we'll start writing our subroutine to initialize the GO A and then to talko the LED。

 So thiss all there is。 and I'll see you later。 Just bear with me if sometimes Im explaining too much or perhaps I'm explaining and it's not clear enough。

 You can， you know， leave it in the questions and answers area。 And I'll get back to you。

 But this is very simple stuff。I'll see you later。

![](img/318a039f99789a3a787999222b687b4c_23.png)