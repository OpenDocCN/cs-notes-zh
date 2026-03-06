# 【从零开始学习 ARM 汇编语言II Udemy】 p03 p2 02.2. Coding  Writing the GPIO Output Driver -BV1RJU6YwEM8_p3-

![](img/eae157d3ea1b00721452d924b5cc88f5_0.png)

Hello， welcome back。 So let's continue。Okay， so we're gonna make symbolic names for our register。 We。

 our registers， I should say， we have more than one of them。 We've got our nodes here。

 So I'm gonna start off by creating the RCC。

![](img/eae157d3ea1b00721452d924b5cc88f5_2.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_3.png)

I'm gonna start off by creating the A H B1 enable register。 Okay。

 so when I'm gonna start for readability sake。I'll start off by commenting this first。In assembly。

 we commence with a semicolon for readability's sake。 I'm going write this in a step by step manner。

 I'm going start off by saying R C。Base， and I'm going to use the E Q U instruction。

 or the this is not an instruction。 It's a directive。 So I'm going to use the E Q U directive。

And E Qs used to give a symbolic name。So。We have A H P。

 We have the base address of this here RCC base and the symbolic name。Now。

 whenever we want this hexadademal number， we can simply use the word RCC base we've given a name to this hexadademo number。

 right？Okay， once I've done this， I'm going to create another symbolic name， I'll say A HB1。的内部。

Enable register offset。And。We have this information as well。

 We're going to give a symbolic name to this EQ U。And we have A H B1 offset at 0 x 3，0。Okay。

 so what did we say， We say the full name of A H P 1 is RCC underscore A H P1 enable register。

 and that tells us that。A H P1 is an offset from RCC。 So to get the。

 So to get the actual A H P1 register。Ill create a new symbolic name， or say A HB1。ENR。

I'll give it the proper name。 I'll say R RCC A H B 1， E， and R。 And this， we can compute this。

By simply doing RCC base。Copy paste plus you can guess or A H P1 enable offset。

 So we just add the offset to the base， and then we get a name。 And this is the interesting bit。

If we write this in C language using our CMC standard， we simply write RCC。

 and then we do this A H P1。E and R， for those of you who have taken the C version of the course。

 you know that this is how we。This is how we initialize the AHB1 register we first to RCC。

 and then we use the arrow operator and then AHB is the same as this。

Writing this length writing this in C language gets us this address。It's basically takes us to。

Base plus offset， writing this。And is the same thing。 This is what we have constructed here。In fact。

 you can copy and paste this sincere language and it would work like magic。

 This is how Cms is constructed。 So those of you who have seen the C version of the course。

 you'd see that this is exactly what we did there。Okay， so we have our RCC， A H B。

 and it's not just ex， it's not just exclusive to this。 Everything that we write。

 you would see that it follows that format when we say GPI U A mode register in C language is GPI U Aarrow mode register。

And what this means is this is a structure。In C language。

 those of you who are experiencing your program is。

 you know this is a structure to write something like this。

 this is a structure and we have a pointer to the structure and we are accessing the structure member using thearrow operator so by seeing this you simply know that this is a member of the RCC structure and because it is a member of the RCC structure that is why it is an offset from the you know the base address of the structure。

Right， so moving on。So we have our RCC underscore A H B1 enabled register。

 Let's move on to the next one。 Let's configure our less。Let's create， I should say。

 let's create our mode register。 So if we do the same thing， Ill say GPR U A base address。

 and I'm gonna give you a symbolic name by saying E Q U。And we have this。 It's this one over here。

Then I'll move on to say。Moud register offset。And the name will be GU A。Mo R。Offset。

And then I'll give this a symbolic name。This is the symbolic name。 I'll get the offset is0 x。 I mean。

 this， you know， the mode register is the same as the base。It's the same as the debate address。

 but in order to keep our readability， I'm going to do this as well just by adding0 to the number。

Okay， so once we've done this to construct the GI， your air mode register。

We simply do base plus offsets， like we've seen。

![](img/eae157d3ea1b00721452d924b5cc88f5_5.png)

Like this。Right。Okay。So。Now how about you post the video and try to do the same thing for the ODR。

 the output data register， you've seen the way I have done it。For these two。

 construct the ODR register。 and then you can， once you've tried it， you can。

Play the video and watch me do it together。 Okay， and also。

And sea language will simply write this like this。Right， as simple as this。Okay。Okay， so for the。

For the ODR register， the output data register， we already have the base address of。Pot port a。

 so we need not write that again。 So I can simply say GI U A。ODR offset。And EQ U。

O our offset is this。And then once I've got the offset， I can construct the Reg GPI U A。Odyier？

And this is equal to GPIU ab。Plus， the ODR offset。Okay， right。 So we have the registers we need。 Now。

 we had other things like。You know the constant to enable GPI port ear I'll bring that here。



![](img/eae157d3ea1b00721452d924b5cc88f5_7.png)

And we've gotta put EQ U here。

![](img/eae157d3ea1b00721452d924b5cc88f5_9.png)

And we also had this one here。Moode register out to set mode 5 to output we push。1 to bit number 10。

 so。We EQ you that as well。And we said LED on to1 the LED on。 We need to push one。

Or shift one to bit number 5， because our LED is connected to P 5 so。



![](img/eae157d3ea1b00721452d924b5cc88f5_11.png)

I'll bring this here as well。O。Right。So now I can clean on nodes。O。Okay。

 so we can start our actual code。So I start with the area directive and there's the code area。

And a prerequisite of this course is the。assemblyly。Programming from ground up course。

 So I expect that you already know the instructions and the directives will be using here if you do not have that course。

I would suggest you kindly stop and get yourself familiar。With the initial lessons。

 you can watch up to the part that talks about instructions or a。I'll add this in the requirement。

 and I'll add a note。To the video， to explain where exactly one should watch up to in the arm assembly course in order to be fully prepared for for this course。

Okay， you don't have to see the whole course， but perhaps 50% of it because the rest of the course is above。

Case studies developing algorithms and others。 But you simply need to get familiar with the with the directives and the and the instructions。

 So if any of this。Looks strange to you。 I'll suggest， you know。

 you go see that course first and you can send my message。 Ill send you a coupon for the course。Okay。

 so this's the code area。 And this read only。And we'm going to align this to。

 and we using in the thumb instruction set， and this is the entry point。

And we're going to see export underscore underscore main because。This is where our program starts。

Okay， so once I stand， I'll create a label here called main。And then， I'm gonna branch to。

A branch to a subrout here called G U A in it。And it's over here that we're going to initialize the GIU port。

Okay， so once we start。We export in Ma because the reset handler needs to know where to start。 Okay。

 once we start。W branch to the subrtine。 so let's write it。Let's implement it。

 I'll bring it over here and we can start implementing it。😔。



![](img/eae157d3ea1b00721452d924b5cc88f5_13.png)

First， we you going to。What we going to do is， I think in order to make this helpful。

 I'm going to write the C code as comment。What we have to do is say RCC。AH P1。

Enable register and what we want to write to A HB1 enable register。Is this over here。

We have it over here。 We w to put this our GPR U A enable into H P1 enable register。

 we wan to or it so that we don't change the other bit。 This is what we want to implement。

So to start off， we load the address of our RCC AHB1。Into our0。

So these first initial lessons would have a lot of comments so that you get familiar with this。

 After this， the course is going to start speeding up。 initially start slow。

 And I know some students。

![](img/eae157d3ea1b00721452d924b5cc88f5_15.png)

Complain， sometimes they expected it to be slow throughout。 And others complain， saying is too fast。

 you know。It gets very， you know， frustrating on U Emmy sometimes。

So the next comment I would put here for you is what we're gonna do。 We're going to。Loot。

Address of RCC A H， P。Rightrite as it appears， RCC underscore A H B1， E and R。I have thetypo here。😔。

We're going to load this to our server。And we do that by using the load instruction。Just。

As simple as LDR。And then Ihiro。And then we want to load the address of this。😔，We' gonnana load this。

Like this。 once this is done， we' are going to load the value found in r 0 into r1。

 So we have the address of this。 We're going to go inside this address and see its initial value。



![](img/eae157d3ea1b00721452d924b5cc88f5_17.png)

We're going to take the initial value of this。Of this address。

 we're going to take what is at this address currently。 And we know this address is basically。

The addition of these two numbers， this and this， we're going to fetch what is there now。

And put it into register R 1。 And we do that by using the load instruction again， load。And then。

Take from R 0 location like this。 Okay， so now we have the current content of R CC， A， H P 1。

 E and R in register R1。 We're going to perform an all operation。



![](img/eae157d3ea1b00721452d924b5cc88f5_19.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_20.png)

With his content and then store the results back there。So， were simply going to do。

Or we use the all instruction， and then we say R1。And then we apply our GPI U E N here。

 And the reason we have in two opera， we saw the result back into R1。 We could have written this。

With three opera such that this will mean perform an or operation between this and this install the results back here。

But if you write just this。It means all this and this and put a result here。

 So the reason we are performing an all operation is because we don't wantanna。

 We don't want to disturb the other bits that were now interested in。

 If we simply write our new value to the register， we might end up disabling some of the bits。

 Remember the register had some reset values。 those values are important。

So in order to maintain its current state and enable the bits that we want。

 we perform this or operation， it's known as friendly programming。So once we've done this。

 we can store the new value after the all operation， the value is going to be in R1。

 Now we can take what is in R1 and put it into our RCC AHP1 enable register。



![](img/eae157d3ea1b00721452d924b5cc88f5_22.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_23.png)

So to do that， we simply use the SDR。And then SDR。This is the source， which is the I1。

 and the destination is the。It's in R0， so once we execute this instruction。

We have the content of Ar stored in AHP1。So， this basically means。I've got to comment this for you。😔。

Okay， how do I put this in simple terms， store the。Content in R1。U。

Just bear with me yeah at the address found in our zero。Okay， so whenever you see the square bracket。

 we're dealing with address。Store the content in R1。

 take the content in R1 at the address found in R0 and we know the address found in R0 is RCC AHP1 E andR because over here we did load address of RCC AH P1 E and R。

Noです。Load this into or to usio whatever the word is， okay。And then over here， what we did。

We said load value at。Agress founded。20日。Into everyone。So what are we saying， We simply saying。

Load the content。Load the content。In。Loow the content。In the address found in our0ro into Iran。

Azio has an address。 And when you get to this address， there is something there。

 take what is there and put it into our1。 That is what it means。 Yeah， if you can wrap your head。

 if you can wrap your head around this language。 Okay， I think we've heavily commented this。

 we can move on。 Okay， so after this， we would have executed this single sea language instruction。

The next one would be to configure the mode register。And in C language， what we do is we say GI U A。

I have to comment this。 We say GPI U A。 and then we'll do this。

 We access the mode register like this。 And what we'll probably do is apply the same method and take mode out here because we know this has。

We've created a symbolic name for it。 right。 So that is what we have to do next。

So we start off the same method。 we do load register R0 with the address of the mode register we are talking about。



![](img/eae157d3ea1b00721452d924b5cc88f5_25.png)

And the address should be here over the address whereas it is over here， GPIU A mode register。



![](img/eae157d3ea1b00721452d924b5cc88f5_27.png)

Okay。We have a here。 and once this is done， we're going to take what is currently in this address and put it into register R1。



![](img/eae157d3ea1b00721452d924b5cc88f5_29.png)

Like we did initially， so Ill say lu。H1。二0。And once we've done this。

 we can perform an all operation on it。

![](img/eae157d3ea1b00721452d924b5cc88f5_31.png)

哦。R1 and then。Moode 5。😔，Mo5 out， as we have over here。

And once we've done that we can store the results， remember after this execution the result is going to be stored in R1。

 we can take what is in R1 and store it into our Mo register address。And then I receiver right， okay。

So that this is it。So once this is done。

![](img/eae157d3ea1b00721452d924b5cc88f5_33.png)

The next thing would be to access the output data register and turn the LED on。So in C language。

 this is going to be G PI OA。O迪R。And what we would do is。Simply turn it on。

We can decide to just set this on if we had multiple LED， we may wan to do an or operation。

 but in this example， we're dealing with a single LED so we can simply。C equals LED on。Like this。So。

😔，We can do LDR。Our Siu。And then the the register is GPU ODR over here。Paste it over here。Right。

 and then we can either use the load or move instruction。 All is fine。

I would say Lord our one with our constant， which is LED on。



![](img/eae157d3ea1b00721452d924b5cc88f5_35.png)

This is going to turn on the LED。

![](img/eae157d3ea1b00721452d924b5cc88f5_37.png)

And once that is done， we're going to store。Awe。Which is LED on。

 we're going to store it in the output data register， which is our0。And once we've done this。

 we've got a return。We are done with this function or subroutine。 We can return by using the B X， LR。

And once we're done， we can align this。And since this is the end of the of the assembly code。

 we put the end directive here。

![](img/eae157d3ea1b00721452d924b5cc88f5_39.png)

Right。So。Simple， if we want to add a loop， our loop currently is empty， but later on。

 our loop is going half。

![](img/eae157d3ea1b00721452d924b5cc88f5_41.png)

It's going to have certain things we can see loop， loop is a label， and then we use branch。

And then we simply say branch to loop。Branch to the same label。Such that。It。

 it just keeps going to label。 It keeps branching to label when it gets to the end when it gets here。

 it would run this code， branch to loop。 And this will bring it here back to the top。

 And then you'll come back here， branch to loop。

![](img/eae157d3ea1b00721452d924b5cc88f5_43.png)

Okay， now we can try out our code and see what we have。So right。

 I'm going to click over here to build。

![](img/eae157d3ea1b00721452d924b5cc88f5_45.png)

We have a single error， let's see， says were missing a comma。😔，And indeed。

 we missing a comma from here。Okay， click here to build。😔，It's builted successfully。

I'll click here to download onto my board。

![](img/eae157d3ea1b00721452d924b5cc88f5_47.png)

And as you can see， the green LED is on right。 congratulations。

 you've written your first driver in assembly language。 So this all there is for this lesson。

 If you have any questions at all， just let me know， and I'll see you later。 Have a nice day。😊。



![](img/eae157d3ea1b00721452d924b5cc88f5_49.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_50.png)