# 【从零开始学习 ARM 汇编语言II Udemy】 p43 p42 10.2. Coding   Assigning Symbolic Names to Relevant UART Registers -BV1RJU6YwEM8_p43-

Hello， welcome back。 in this lesson， we' are going to see how to develop the U art driver for our TM4 C123 microcontroller。

'm going to create a new project by coming over here， new U visionsion project。

Create a new folder for this。 Go this。You ought。

![](img/2bc9f7c8855cb898f04fec5d3e47fa77_1.png)

Then the project， I'll call you art。And I'm going to select my port T4 C。😔，One，2，3，0 H，6 pm。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_3.png)

Okay。And then under Cms， I'm going to select the core under device or select the startup。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_5.png)

Okay。And this is it。 My target is the Tm4 C123。And the source group here going rename it to A P。

I'm going to right click， add new item。Dot S， and I'll give it a name， main。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_7.png)

So we have our main S file， so were going to configure the the U at peripheral on our microcontroller and we've got a number of UUs that we can use。

 I think we have U at 0，1，2 3， and even 4。In this experiment， we're going to use you at 0。

The Rx line， you at has two lines， there is the receive and the transmit， RX and Tx。So you add  zero。

 I'll put a comment here。We find the R X at P A0。 Remember， the UU is connected to a normal GPIU。

 So in order to use the UU， we need to configure the GPIU to be S PI O special purpose input output。

And。Another way of saying this is we need to configure the GPU for its alternate function。

 one of its alternate function， because a single GPIU pin could have multiple alternate functions。

 You can have one pin that you can configure it to save as a U add pin， an A0 Z pin or even。

A D AC pin。Right。So we're going to use you at  zero， which。Its connected to PA0 and PA1。Rx and Tx。

 respectively。Okay， so we would need to configure P is0 P1 for alternate function。Right。So。

Let's go to the data sheet and find the addresses of the relevant registers that we need。

I'm going to open my data sheet， I've got it over here， were starting with GPIO A。嗯。

Less control F for GIU。Let's see。 we have GP U here。 I'm gonna go to。Register descriptions and。

I'll be bro here。😔，So I'm going to get the GPIU A base address。你是谁？Or close is so that。Yeah。

 this is it。 I'll copy it。And then。I'm going to come over here。And then。

I'll say GPIU A underscoreco base。いQゆ。This is the base address， I just delete this from here。

And then what we also need is the the system control base。 and then the system control offset。

 we already sorted that out in the previous。In the previous lessons。

 I'm just going to bring that piece of code that we already wrote the assignment we did for that。

 So this is a。System control base address， because we need to enable clock access to GPIUA and we would have to go through system control to do that。

Right， so we've got GPIU Airb。Now we can get our various registers， we would need to configure the M。

We need to configure the。Digital enable。And then we may have to。Not May。

 We definitely have to access the alternate function register to select the alternate function。

 We also have to deal with things like disabling analog functionality and perhaps， you know。Yeah， we。

 we need not touch the con the direction register here so we can leave that out。

 So I'm gonna get the， I'll just create symbolic names for the registers that we're going to be touching。

We're going to be accessing GIU A。GP A。GP A D， E， N， which is the。D youital enable register。

DEN underscore R。No， offset first。😔，EQU， we don't have that yet。😔。

We leave it and then well do GPI U A。D EN， the register equals。Base。Plus， the offset like this。Okay。

The next one。She's gonna be GIU A。Alternate function select。Oset。😔，We do not have it。

 so I'll just leave it blank。And then GIU a。But they function。Select register。This。Equals the bay。

Plus。It's offset。And。Yeah。I think these are the two registers we we needm trying to have a minimalist code over here。

嗯。Okay， we' need a PC TL register to think well need that。

 I don't want us to sometimes some register， some of the registers have their default values the way we want them。

So often the best practices， even if they register default value is 00 and you want that bit to be 0。

 you should actively set it to 0。But in order to minimize the code， I sometimes avoid that。

we need a PC c t o register，And I'll say GPIU A。Pc。Offpsset first。😔，AQU。Then。P A。PCT。L。Do register？

Is equals。The base plus the offset。Ass the offset。This one here。Right。We have the digital enable。

Can we have this。Okay。So。A symbolic name for enabling GPIU A。To enable GPU A。

 we need to go to the system control register。And then， we need to。We need to set bit number 0 to1。

We need to go to the system control Rrc GC GPI you register， this one here and set bits number0 to1。

 and we shall find that in the data sheet， so I'm going to create a symbolic name for that。

I'm simply gonna say GIU A。GPIU A， E， N。Ecors。Shift1 to bit number 0。And then， over here。

We need to enable clock access for the。For the U at as well and to enable clock access for the U at。

 we would need to access the。RRCGC。You are register。 We have the R CGC。

GPI you register to enable clock access for our various GPU ports and because we have multiple UUs。

 we need to go to the RCGCU U register to enable clock access for the UUs that we want to use so I'll say UU0。

E。And this。Its also。Passing one at bit number 0。 So we need the。We need the RCGC U U register。

 we need to create a symbolic name for the， we need to get the address and give it a symbolic name because we have just RCGC。

嗯。R C GC GPIU here， we need a UU。So， the RCGC。U art register is simply going to be an off an offset from the system control base。

 So I'm gonna say。The same way we have GPI here。 I'm going to have RCGC U add here。 So say R C GC。

You are offset。We do not have that， so I'm going to leave it。And then I'm going to see。

So this control。😔，You know， system control。Is often written with a T。

 but because we are given our own names， we can write it how we want it。

 but we can fix this and make it look good。 I just change thearrow to T here。Okay， system control。

So the Registtry code System control RCGC U art。Lets go R， and this is going to be。

The system control base。Plus， the offset。CGC U are offset like this。Okay。

 so we would have to fetch this from the data sheet as well。And then we've got the。

We've got a bit shift to enable our。To enable our you at。Right， U add in GPU A。

 so now we can go to the data sheet and search what we want。All right。

 now let's go to the data sheet and get the offset of the various registers lists out with the RCGC。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_9.png)

I'm going to go to my data sheet here， C F to search， and then you can simply type R C GC U art。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_11.png)

And then I'll hit enter， and then it brings me here， register 63。😔，R C youC。

 you are to click over here and the offset is。0 x618， So'll copy this。And I'll bring it over here。😔。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_13.png)

And we can read a bit about it， like I said。This register is used for enabling the clock access for our various U U。

 Let's see what bit number 0 does。Sa over here， you at module 0 run mode clock in controlt。

 If we pass 0 to bit 0， if we set bit 0 to 0， you add module 0 is disabled。 If we set it to one。

 we enable and provide a clock to U at module0 in run mode。

 So that is why we have this symbolic name shift1 to bit number 0 for you at enable。Okay。

 so the next register is the GPIU A digital enable register D E N。So I'm going to go to GIU。

Go to come up here and search GIU。And。😔，We just go to click， we click Reg descriptions here。

And then he should bring us to the registers。And what we need is the the D EN。

 the digital enable register。😔，So we can keep scrolling until we find it。😔。

Should be down here somewhere。😔，Okay， we would need we need the alternate function select to register as well。

 so how about we just copy it， although we are looking for the DEN。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_15.png)

So I'm copying the offset of the alternate function select。And。😔，Put it over here。Right。

 let's go back。And。Where is the D， E， N。Okay。Let's see， goodness。 Okay， here we go。GPIUDEN。Okay。

 I'll copy this。DN。No， we're looking for the PC TL。Or a， let's go， let's scroll down。

This is the port control register。😔，I'm going to copy this。And you can read。

 you can read about these registers， if you。You can learn more about them。

 and if you want to read more about the Uad。You can read more about the U from the data sheet。

 just like we saw how the data sheet provided step by step instruction。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_17.png)

For initializing the GPIU in our GPIU section， there's the same step by step instruction for you at and in fact for any peripheral that the microcontroller provides。

 I'm scrolling up to the bits that talks about initialization， so just bear with me。

So it should be under U add， there is always a section under the initialization。Ts okay。

 so it talks about the initialization procedure here， So if you want to read more about it。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_19.png)

You can do that。Oh， no， this is GI U。 But if you go to the U at section， there is。

 if you go to the section under U at， there is a subsection called initialization and configuration。

 and it gives the steps for initializing。 Okay， so now we've got our。We've got our。

GPIU registers with regards to the UU。And now let's take a look at the U at registers。

 We would need to enable the U at， we would need to sort of configure certain U at registers。

 We would need to configure the U at in transmit mode or receive mode or both。

 We would need to decide the。The data length will need to decide whether we are using5 or not。

 we need to decide whether we use an interrupt or not。

 and we need to enable the U at All those stuff we do them using the U at registers。

 So I'm going to come up here。And search U at again， Cr F U at。And it brings us here。😔，And then。

I'm going to go to register descriptions。So this is the U at DR register。

 the U at data register who need it。So what I'm going to do is I'm going to create a symbolic name。😔。

For that。I'm going to come over here。😔，You add zero base。We need to grab you at zero base。😔，Okay。

 once we've grabbed that， you add 0。Once we've grabbed that， we。We say you add0 Dr。

 that's the name of the register。D R offset。一Q you。And then the register itself， you add  zero。

D R underscore score R， and this is simply。The base plus the offset you are0。Das over here。😔，Plus。

 the D R offset set。

![](img/2bc9f7c8855cb898f04fec5d3e47fa77_21.png)

Okay， so let's grab the。

![](img/2bc9f7c8855cb898f04fec5d3e47fa77_23.png)

The offset is your exc meaning is the same as the base address， no problem。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_25.png)

But we have to find the base address。The base address should be here。

So over here over here gives us the base address of our various U at modules。 Look at that。

 we've got seven different U at modules。So I'm going to copy the B's address from here。

Highlight this control C to copy。

![](img/2bc9f7c8855cb898f04fec5d3e47fa77_27.png)

And I'll paste it over here。😔，Control feature to paste or clean this。Right。

 so we've got our U at data register。

![](img/2bc9f7c8855cb898f04fec5d3e47fa77_29.png)

Let's go。And you can read more about this， if you want。And let's go。

 Let's see if we have other important registers。 Of course， we need more registers。

We need to deal with at least eight registers。This is the U at flag register。

 So this we would need to check whether the transmit flag set， the receive flag sets， etc。

 So this is an important register。I'm going to copy the symbolic name。

 and then I'm going to copy the offset， sorry， and then I'm going to create。

A symbolic name for the register。So I'm going to say you at 0。FR register， FR of set should say。

Opsset。EQU already copyied this。I'll simply paste this over here。And then。You add zero。FR。

 the register。EQ U as the the base， your0 base。Plus。The offset like this。Okay。Let's move on， okay。😔。

So we will be taking a look at the Tx RX flags。bitits number 4 and bits number 5。

 we would monitor these flags to see whether there is receive or transmit flag the the receive or transmit flags are set or whether the U at is busy。

 So when we start creating symbolic names for these T， X， F， F and R X， F。F， F or FE， then。

You should know we are talking about this， but we'll talk about that later。

So we would use TxF to check if the U at transmit PIO is empty TxFF to check if the UU receive PO is full。

Right。And then there is the rec pfo。 and then there is the transmit p4 fool。

 and then there is the receive P4 empty。Like I said， I'll assure you。

I I spoke about the section on initialization and configuration。 Okay， so over here。

 if you want to read more about the U or if I'm saying something and you don't quite grasp it。

They provide initialization and configuration steps here。

 step by step for doing what we are we are going to do so you can spend some time reading this if it's not so clear。

 and， of course， you can send me your questions。 If you have any questions。

 you can send me a message or leave in the Q and A section。But all of this is written here。

 I know this because I've read this stuff before。Yeah。Goodness。

 let's go back to the top and look at you at。Controrl F。And we need to go to register descriptions。

Okay。So we had just created a symbolic name for our flag register。

Let's see other relevant registers we require。This is the U at low power register。

 Well we're not dealing with low power now。 Okay， there's another important register。

 this is the U at integer board rate divideisor。So we would have to set the board rate of our U at communication。

 whether we want the standard 9600 or the other popular one， which is 115200。

 we have to set that and to set the board rate， there are two registers。

 there is the integer register and the fraction register， so we need to get this register。

I'm going to copy this。And I'll show you how to calculate the board rate when we start， you know。

 calculating it。So I'll say you at0。The name of the register is Integer portrait IPD， IP RT。

 and then the offset。I've already copied it， so I'll simply paste it over here。😔，And we say。

 you add 0。And IP PRRD。The register。This is EQU。And it's simply the base address of you at 0。

Sorry about there。Plus， the offset over here。Okay。Right， let's go to the next one。

The next one should be the fractionction one。So we would have to okay。

 Ill just explain this while we are here， we would have to write the the borderrate integer part here。

The first 16 B of this 32 B register is the part where we store the the board， the board rate。

 The board rate is going to be。Is going to have a whole number and a fraction。

 We take the whole number and we put it here in the first 16 bit of this register。

 The fraction bit is going to be stored in the U add fractional board rate divisor。

 and this the M there's the offset for that register。

 So I'm going to copy this and create a symbolic name for it。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_31.png)

You got zero。FDRD。Offset。EQU。This is it。And then the name of the register is， you add zero。FBRD。

And let's go R and。😔，You know this by now， simply。Base address。Plus， the offset。Okay。😔，Control C。

 Cl V。Right。Okay。Lexi。Okay， our next register is the line control register。

 and this is the register that we shall use to sort of configure the， the length。

 whether we want 8 bit we length or 7 bit。 We need this register to configure the data length。

 So copy the。The offset and coming created。You are0。Line control register。It's often written as LC C。

RH。Right， let's see。Yeah， it's written as LC C， R H， okay。Opsset。EQU。

This is the offset and we can create the register U0。LC RH。Or for the register。BQU。

We crop the base address and。Pish it over here。😔，We add the offset as well， copy。Paste it over here。

Okay。She。

![](img/2bc9f7c8855cb898f04fec5d3e47fa77_33.png)

Our next register。It's the Uar control Reg and we will use this to enable and disable the U art I'm going to copy the offset from here。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_35.png)

You at zero。Contrl register， CT TL， we call this。This is the offset。😔，EQU。CT。😔，To register itself。

一QU。This is space。Ps。Plus， offset。Right。Okay， so we need other our registers since we'll be talking about interrupt。

 how about we just add the registers that would help us with？

Enabling you at interrupting other things so I'll just go ahead and add all relevant registers so that the next time we talk about U at。

 we wouldn't need to add any， you know any new registers。

We wouldn't need to create symbolic names for registers。So。Yeah， with this， we would。

 we would just need to check our sort of status register。

 We just need to add other registers to check the status whether， you know。

It should be called a status register。Anyway， let's just add all registers that we need for you at Rx Tx and interrupt so that when we're dealing with other topics on U at。

 we wouldn't need to add in a further registers Okay， so I'm going to go ahead。

And look for more registers that I think will be relevant to us。Okay。

 register for 54 level select we wouldn't need this。Okay。Interrupt mask。

 this is an important register for interrupt。 so I'm going to copy this I'm going to create a symbolic name for it。

You are zero。I am。Offset。BQU。You are zero。I am R。EQU。Sue at zero。Bace。Plus， I am offset。😔，Right。

 moving on。Let's see we saw one with regards to PIO， we may need to experiment with this。

 I'm going to create a symbolic name for the interrupt PIO level select as well。Soll copy this。

You got zero。IF LS。Offset。YouQ you。This is it。And then。You are zero。IFLS， underscore score R。

EQU is the bays， you add zero Bays。Plus the offset。This one over here。Like this， okay。Moving on。

Let see， let she。Okay。O， so this the。U RIS row interrupt status Reg it's definitely useful。

 I'm going to copy the offset。Come over here。You got zero as。Offset。EQU。Pate over here。You are0。R， R。

EQU。As the base。You had zero base。Plus the offset， this one over here。Pased over here。Right。

 moving on。P to scroll down。This is most。Mosques， interrupt status。We we sorted this register out。

 did we not。0 x 4，0。Okay。Okay we can leave that one out。srry but let's see。 Okay， here we go。Okay。

 there's an important one。 register IC R register is the interrupt Claire register。 Okay。

 this is going to be used for clearing the interrupt。Sou。Come over here， you add zero。ICR offset。EQU。

能。You are0。ICR R。DQU。The bay。Plus， the offset。 I see our offset here like this。Right。

So I think we have enough registers。Okay， let's hope we've not missed an important register。Right。

 so now we're going to create symbolic names for the various constants that we shall be writing to the various registers。

 so for instance， to enable the the U at module， we may need to set bit number maybe bit number one to one。

 we may need to set bit number2 to one or something。

 Were going to create a constant to hold this such that we just write a constant to make our code more readable and you know what I'm talking about because we did it for the other lessons。

 So let's do that now。Okay， so le start with creating a constant for checking if the receive P4 is empty。

I'm going to call this。You at。U at and were going to be applying this to the the flag register。

 So I'll say F R and then R X for receive and then F for5 or and E for empty。

 And this basically would be to perform an end operation with bit number5 set to to one。

And this is what it looks like in hexademal form。Right， if you expand this。

 this hexadeademal number you see that bit number 5 is what is set to one in the entire 32 bit。

Receive 54 mt。Okay， the next one is going to be a constant to set our。EData l to。To8 bit。

 So I'm gonna say u at。And then the Reg you'll apply this to is the line control register LCRH。

And we're going to set the word length， W then to 8。EQU and the constant is this。This means。

8ight bit。Wed length。Right。The next one would be to。Enable the U at 54。To enable the U at 54。

 we would need to access the the line control register。So I'm going to start u out。

Line control register again。And5 for enable。It's going to be EQU。And the hexod mode。

Is basically set bit number 5 in the 32 B to register。Set in bit number4， sorry， this is bit number4。

 If you expand this， this is this one hex theres more。Digit would give us four binary digits。

And this one here is。It's 1000， right， but because we count from 0。

 this one would end up corresponding to bit number4， not bit number5， iss the fifth bit。

 but because we count from 0 is bit number 4。And so this， this for。Enable 54。Okay。

 the next one will be to enable the UU and this one we're going to access the UU control register。

 so'll say UU。CTO。😔，You're at E。EQU。And this is basically setting bits number 0 to1。

Enable you at right the next one here。Is to check if they receive54 timeout occurred。

And I'm simply going do。You ought。I am。Because we're going to apply that to the IM register interrupt mask。

And then I'm going to say R T I am。EQU。Right。Okay， so now we are done assigning the symbolic names。

And we shall start developing our drive in the next lesson， so I'll see you in the next。



![](img/2bc9f7c8855cb898f04fec5d3e47fa77_37.png)