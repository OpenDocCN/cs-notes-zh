# 【从零开始学习 ARM 汇编语言II Udemy】 p13 p12 04.2. Coding   Assigning Symbolic Names to Relevant UART Registers -BV1RJU6YwEM8_p13-

Hello， welcome back in this lesson we're going to see how to develop the UU driverver and this first UU lesson we're going to see how to just develop the TX part of the driver。

 meaning the transfer， we're going to transfer data from our microcontroller through the UUt to a serial programme on our computer。

Okay。So I'll create a new project， but before I do that there's something I have to point out about our last project and want GP tellU input project。

If you remember， this was the initialization for the GPIU。

We initialize the LEDs by setting mode 5 of our here to output。

 but we didn't initialize any mode for the input。And the reason we did not initialize that is that in order to set the pin to an input。

 you've got to set the two bits that corresponds to that pin。

 the2 bit in the mode register that corresponds to that pin。 you've got to set it to 0，0。

 Since by default， these two pins are already 0，0。 That is why I did not bother to write 0，0 to them。

 So don't be confused。 We configured it to input。But we didn't touch the mode register。

Because it's already 0，0。 And to set to input， you've got a right 00 there because that default value 0。

0， we didn't do anything about that。 So it does coverV it。I'm going to create a new project。

 I'll come over here， new Uvission project。Of story in the new folder that I've created over here。

 or this U at T X。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_1.png)

And then my board is SDM32 F411 VET。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_3.png)

Okay。And of Cms osll the core on a device， oll the startup and an O。😔。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_5.png)

And then I'm going to give my target a name。😔，ThisSt 32。F4。😔，Soce group here。

 I'm going to give it a name。😔，APP。And then over here and at APP， I'm going to add new item。😔。

It's gonna be a dot S file orll give it a name， main like this。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_7.png)

Okay， that's what we have。Right， so。Like we did before。

 what we have to do is find the U at registers。 We've got to get a base address of the U at。

 and then we find the offset for each register that corresponds to the U at。

 But before we even find the base address of the U at。 we've got a no。

How to enable clock access to the UU to do this， we have to go to the plot diagram we saw earlier。

That block diagram is found in our data sheet So come to books and then I'll double click over here。

 data sheet。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_9.png)

And then down here。😔，Just the plot diagram we're looking for。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_11.png)

I'll just open it like this so that you can see。Okay， I's scroll down。And over here in S M 32。

 the U at is known as the Uat。 The reason this is。It's because we can configure this module the user as either a U at or a user。

You a。R T stands for Universe or Ace In。UART stands for Universal Asynchronous receiver transmitter。

 whereas USART stands for。Universal synchronous receiver transmitter， US R T， I should say。In a way。

 let me show you。 So you see it's written you sat one here。The S stands for synchronous。

 The A stands for asynchronous。 So they are trying to tell us this is universal synchronous asynchronous receiver transmitter。

 But when we are talking about U at， we just want the asynchronous bit。

 We don't care about a synchronous bit。 So when we want to call this U at。

 We just delete the S such that becomes universal asynchronous receiver transmitter。

 That is what we will be working with。So we are configuring the U at here and we're going to nominate you at2。

This is U add 2 is connected to the APV1 bus， so to enable clock access to U add 2 we've got to go to the APB1 enable register and toggle the bit that corresponds to Uat 2 It's called Uat but we're going to configure it for U add so do not be confused by that。

Okay， so we know this is APB。AP P2。And the next information we require is going to be the。

It's going to be the base address for the user， so we go to page 54。I'll come over here。

 I'll search 54 over here， it will bring me over here the register boundary addressesees。

And we should have youat down here somewhere。Okay， let me start taking notes。

 Remember this course starts from scratch。 So if it's too slow for you， you can speed up the video。

 or， you know， just keep it if you're already familiar with this。 So we said it's A P B1。AP PB1。

 unlike the GPIu port a， which is AHB1。The user is APP1。And then。

Use a two base that is what we're looking for next。Uat 2， this is USAat 1。Let's see。Okay。

We don't have it here。Okay， it should be up then。 I could just search。Interesting， how do control F。

You said to she。Okay， here we go。 Sorry about that。 Okay， so this is U 2， this is the base address。

 So I'm gonna fetch this。And then I'm going to put in my notes。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_13.png)

O。We've got the U 2 base address， right， So now that with've done that。

 there are a number of things we've got a configure in order to set up the user。 Remember。

 our user is connected to GPU pins。 UAT 2 is connected to PA2 and PA3。PA2 is the Tx line of U 2。

 and PA3 is the Rx line。So there are two configuration types that we have to do。

 We've got to configure PA2 as well。And we've got a。

Enable clock access to port A set P2 as alternate function and select the alternate function as you add。

T thou get P2 ready to serve as a U at pin once that is done。

 Then we go on to configure the the U at module itself。Right， so let's start off by doing that。

 let's start off by configuring P2 and then setting it as alternate function。

 Once we've done that we can go to the reference manual to get the use that registers we' need for this。

So。Let's create our address lies。I'm just going to。I'm gonna bring the。你。

I'm going to bring the port ear registers that we created。Of course we've already done that。

 we can we shouldn't type that from scratch， So this gives us RCC AHP1 enable register this which shall use for PA2。

And we have the demo register， as well。Because we were going to need a mode register to configure P 2。

This the mood。And then。😔，The more registers this。Right。And I'm gonna create a new。

I're going to create a new symbolic name here， I'll say GPIU A。Af。R L meaning alternate function lu。

Opset so。We've got to write something to the alternate function Lu， register。

And the alternate function law register is， is going to also help us。

 So I should roll back in order to configure a pin as alternate function。Apart from selecting the。

Apart from setting D。The alternate function mode in the mode register。

 there is another register known as the alternate function register。

 This register would allow us to select our alternate function type。

 whether we want to as a U at an S P I， I2 C， etc cetera。 Let's take a look at this register。

 alternate function。So I'll go to books and。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_15.png)

I'll call to reference manual over here。And I'll search controlr F。😔，AF alternate function。

 this stands for alternate function。L， meaning low， our alternate function， low register。

 there is alternate function， high register as well， and we shall see that。Okay， interesting。 Okay。

 AFRL O function Reg Lo。 that is what it says。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_17.png)

Okay， so we can jump here。I'll click to jump here。Okay。

 so this is used to set the alternate function， and there are different alternate function types。

 We have AF0 AF1， AF 2， AF 3， AF 4。All the way to A F 15。Right。

 and there's its counterpart the alternate function high， AF R L。

So we need the offset of alternate function law over here。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_19.png)

I'll copy this， I'll put in my notes。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_21.png)

So to see the alternate function types， we can go to page 1，49 of the reference manual。Right。

 so this is an image of a multipleer。Right， for those of you who are familiar with digital。

Digital electronics。This symbol here has a multiplexa。 This allows us to select one of this。

 This is like the selection。And based on what you pass here。

 you get one selection that comes out as output。Okay。

 what brought us here is to know which one is U at2 and AF7， as we can see over here is U add 2。

And we already saw the meaning for A F7， we shall go back there， So AF 0， AF1， AF 2。

 AF 7 here is USAAT 1， USAAT 2。Right， so let's go back to our alternate function register and see what A F 7。

Me。And this over here。S TM is for the alternate function register Lo。

And this the meaning of the we have AF7 here， if we want you add。

 we've got to use the code for AF 7 if we are dealing with opening function register high。We are。

 we use things like O T G， I to C U at 6。 They are in the alternate function register high。

 So because the one we're looking for belongs to alternate function register low。

 That is why we are looking here。 So let's go back to。

The alternate function register and see what A F 7 means。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_23.png)

后 said。I'll search。AFR L over here。 and then it'll bring me to the AFR L register。 So over here。

A F7 means code 0，1，1，1， meaning if we pass code 0，1，1，1 to our respective。AF RL position。

 then we get da pin sets as a U at for us。And then， let me explain。

Over here you can see is that from AFRL0 and ends at AFRL7。A F， R。

 L 0 corresponds to bit 0 of any pot。 A F R， L 1 corresponds to bit 1 or pin 1， I should say。

0 corresponds to pin 1 of all po 1 corresponds to pin 1。I would just ruleeb， sorry boy there。

0 corresponds to pin 0 of all ports。 whatever you are dealing with AB C D， as it is written here。

 one corresponds to all pin ones，2 corresponds to all pin 2，3 corresponds to all pin 3， In effect。

 we need 4 bit to to configure a single pin， each pin requires4 bit to configure。

 So we have our four bit here。 So if we take these four bit，1，1，1，0。 and then。

We write it to the first four bit over here， meaning bit 0， bit 1 B 2 B 3。

 This would configure our pin 0， P A 0。 It would configure P A 0 as U at 2。Right。So。

What we are dealing with is P2， we want to configure PA2 as the user mode。

 We want to configure that for it use that mode。 So we've got to come to PA2 over here。

And then when we get to P a when we get to P a2， which is the same as A F R L 2， we take A F 7 here。

 which means 1，1，1，0 and apply it to it for bit。 So we're going to write one here， write one here。

 write one here， and then write0 here。And in effect， after doing this。

 P2 is going to be set as a U2 for us。Right。So you might wonder， okay， I said。

A F R L 0 is for pin 0 and A F R L 7 is for pin 7。 How about pins 8，9，10 and anything above 7。 Well。

 that is why we have the A FR H register。 the H register start from 8。

 So if you are dealing with a pin and the pin number is above 7。

 and you want to configure it for its alternate function mode。

 you are going to be using the A FR H register。And this one is the same as the AFRL register。

 you configure the four bits like that。O。So that's the meaning of AF 7。

 if you do not understand what I just said， just send me a message and I'll elaborate further。Right。

 so let's move on。Let's see。Okay， so。We have the offset of this。 Let's create the register。

And then I'll share EQU。😔，And then what I need is the RCC base。The name of this register， actually。

No， I don't need the A CCB， sorry bother that。 I need the GPI or earb。😔，Plus， this offset here。😔。

Right， so。These are the registers we need to configure our GPI U A P2 for U at mode。

 How about the the U art itself， we said。U at or U2 base register is this。

 and we said it is connected to the AP PB1 bus。 So let's see what in the A PB1 bus。

 Let's see what we need to do to the APB1 register in order to get clock access for U2。

 Let's take a look at the A PB1 enable register。 This will throw more light。I'll come over here。

And then I' do I controlt F。And then I'll do APB1 ENR。sorryrry的 I forgot it。Bi。A P1 E R。

 and as you can see over here it says bit number 17 bit number 17 is used to enable U 2。

 That is why the name for bit number 17 is U 2 EN， meaning if we write 1 to position 17 of the AB1 enable register。

 we would enable clock access access for U2 if we write 0， we disable clock access。

 so we need the offset of this。I'm going to copy the offset。And then I'm going to bring it over。

S about的 control。I'm going to put it over here。😔，Okay， so now we can create this。So， I'm gonna see。

APB1， E and R。AP P B1， E and R， AP B1 the enable register。Offset。The offset equals EQU。😔。

And I'm going I pass this iss still in my clayboard， so I need not， you know。😔，copy it。Okay。

And once that is done， the real Reg becomes RCC APP1 enable Reg。And this equals RCC base。

This the course。RRC base。Plus。The opposite here。And this is this。This line， this EQU。Which is。

This number plus this。We get access to this when we write this in C language when we write this。A。

 B1， E and R。Is the same as what we have here。Right， this will fetch this for us。

 And we know that A P B1 is a member of the Rcc structure in the same way。

 A HB1 is the member is a member of the Rcc structure。 Okay。

 we saw that we require to set bit number 17 to1 in order to enable the use at2 module。

 So were going to create a symbolic name to represent that as well。So I'm going to come over here。😔。

And see。😔，U at or Uat， you can call it whatever you want。

 but we are configuring it for you at so Ill just call it U at as a U at EN equals。

And I'm going to shift one to position 17。And let's not forget our GPIU A enable， so I say GPIU A。

Ein。Equs。Shift 1 to position  zero。😔，Right。Okay。So now that we have this。

We would have to deal with our war。Our U U registers， we've got to create our U U registers as well。

 I think will be best if we created the UU registers， and then we move on to write the the code。

 so let's deal with those registers now。So to configure the you at， we need to。

Configure about five different U art related registers。 Let's take a look at them。First of all。

 we have the Uat2 base address here。 This is the offset of APB， not USAAT。

 so Ill just take this from here。So that it won't confuse us。 So first of all。

 let's take a look at the CR1 register， which means the control register 1。

Let's go and take a look at the UAT 2 CR1 Reg， this register enable us would allow us to enable and disable the UAT or Uar module depending on how you want to call it。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_25.png)

Right。So， I'll see。Uat2。 Oh， no， I'll just say C R1， cause the oh， a better。

 a better way to search will be UAT X， cause we've got different UAT。 And then C R1。

 Let's see if this would get us what we want。 No， we can't find it。So simply do see R。Okay。

 the number of CR1s is as if each peripheral has its own CR。No problem， patience。😔。

Oh sorryrry about that Okay， we've got to find this the way yeah。😔，Well。

 this is what goes on when you are developing drivers from scratch。

 you spend a lot of time in the data sheet， so just bear with me here。I've got GPIU part here。

 DMA interrupt ADC。😔，Time is。General purpose time is。11。😔，Real time clock。Okay， here we are。Okay。

 here we are。So we've got the control Reg 1， CR1， so let's take a look at this， the CR1。嗯。Okay。

So the offset of control register。Sid one is this。I'll copy this。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_27.png)

And then I'll take note。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_29.png)

And we can read up on some of the， the what the bits for CR1 does。

 We would use CR R1 over here to enable the U， the。The UU model the UU module for Tx or RX mode。

 whether we want Tx or RX mode， we're going to toggle a bit here。

Whether we want to set8 bit data or seven bit， we've got to decide that through this register and if we want to enable it。

 we've got to decide it through this register as well。So。Let's take a look at that。Okay， so。

Let's see， let's see， let's select some of them and take a look at。 Let's， Let's start bit number 7。

 We just take a look at few of them， and then you can take a look at more of them if you want on your own。

 because we cannot examine each and every bit here。 Let's say bit number 7。

 If you want to read up on bit number 7， you just scroll down to bit number 7。Okay。

 bits number 7 is the T X E interrupt enable。 So when we when we get to the lesson on U at interruptt。

 were going to have to configure this for interrupt enabled to enable it interrupt。Okay。

Let's see one of the bits that we would use。Let's go up here。

 This one U E here stands for U at enable。 and this is bit number 1。

 So U E here when we set it to one we enabled our U at module。

 So we're going to be setting this to one。Right。And there are so many other bits。

 so I would advise you spend some time to read upon them， but I've seen these before。

 I've worked with them before， and I have the the particular bits numbers。That we need。

 And we just going to use that now course like that。 Okay， this is the CR R1。

 Another register we need is the B R R This known as the bad rate register。

We use this to configure the above rate， so I'll copy this as well。And take notes。Okay。So again。

 you can read up on this。On the meaning of this。And after boat rate， we have the data register。

 whether we are transferring， whether we are in T， X or R X mode。

The the data is going to be in the data register if we receive data it's going to be in the data register。

 if we want to send data， we have to put it in the data register to send。

So I'm going to copy the offset of data register as well。We also have control Reg2 and 3。

 Let's take a look at those。We are going to use。Control Reg2 to you know， set the stop bit。

 whether we want a one stop bit or we don't want a stop it， things like that。Contrl Reg2。

 is the offset。This is CR2。There is control Reg 3 as well。And control Register 3。

 we shall use two sets whether we want flow control or no flow control。Or copy this。

See our three offset。And there's one last register we have to look at。

 Its known as the status register。 And the status register would tell us whether the the U at buffer is full or empty。

 We've got to check the status。So we need the offset for that as well。Here it is。

 the status register offset is serious here。Right， I'll copy this。Okay。

 so we're going to create these registers， okay。

![](img/e1921c4d3b2c45ca86b6703f6f5ee523_31.png)

Okay， so let's create the registers。 I'm gonna。Start off by creating the base。😔。

I'll call it UU in my code， you add two base。😔，We have the base address already。

 we got that from the data sheet。It's up here。Theres the bay。 There's the bay。Okay。

 so we can start off。By okay， you art。I keep writing you that， you add to BRR。😔。

Which is the port rate。Register the offset of this。We have this too。😔，The offsets is this。

Once that is done， we can create the register itself。And it's called U add2。😔。

And let's call BRR and then EQU。We take the base。We are the offset。Right， and then once that is done。

 we can go on to do you add2。Contry register 1。Offset。AQU。Is this。And then， we do。You add to。

Conrl Reg1， the actual register。Equals。You at two bays。😔，Plus。Contravers to one offset。Right。

Then we can do it full。😔，You add two， control register2。Oset。EQU。

We have control register to offset over here。And then the register itself， you add2。

Controrl register2。😔，This equals。You add two bays。Plus CR2 offset。Right， moving on。

 we do you add three。Sorry， you add to control Reg 3。Offset。And the offset for CR3 is this。😔。

Then the register itself， you add three。😔，Oh， sorry， you add to CR3。😔，AQU。And we take the bayes。😔。

We are the offset。And finally， the status register， you add two。You add to SR for status。😔。

Register SR offset。😔，こし 이QU。And this。SuX you。And。You added two。Studus register。Q you。

We take the base。And we are the offset。😔，Right， so we've got our registers。

I'm going to clean the notes。😔，Perhaps I should close it up a bit。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_33.png)

Right， so we've got our registers here。O。So next we're going to give symbolic name to some constant。

 some of the M。The bits that we going to be right into the particular Reg locations。

Make it look like this。😔，And I'm gonna to cut。I'm going to paste the down here。😔，Okay。

So I'm going to create other symbolic names。 For instance， we know to set。We know to set P 2。

 to set P2。To alternate function in the mode register， we've got to。We've got a set。Well。

 should we go to the mode register to see， okay， Ill bother rather than just type this。😔。

I promise nothing is going to be left unexplained， so I've got to come here to show you。Okay。

 control F。Would R okay。So mode R， we dealing with PA2。

So PA2 over here corresponds or belongs to multi2， like we said。Moode1 is for pin 1， mode 0。

 for pin 0， mode 6， for pin 6， and so on and so forth。So PA2 belongs to pin2 mode。Moode 2 over here。

 mode R 2， mode register2。 Okay， so we want to set this to alternate function。

 We simply come here and see what we have to do for alternate function。

 We've got a pass 0 here and one here。Essentially， we've got to take this entire mode register in pass one。

At。Bits number 5， we've got a pass one at' bit number 5， so that's what we have to do。To set this。

As to set PA2 for alternate function mode。Because this the code for alternate function 01。

 and each each pin requires 2 bits to configure。 So we pass 0 at the first bit and one here。

 and one is for bit 5。 oh it， it falls under bit 5。 So because we are configuring only P A2。

 we've got a pass one at position number 5 in the entire mode register， okay。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_35.png)

So I'm gonna create a symbolic name for that。And I would see。GPIU A。O。😔，S， L T mean alternate select。

 And then I'm going say E Q U。 And I can， in fact， say this， Sir X20。

 this another proposal we are frightenedright。 This the same as。I'll expand this for you in binary。

 this becomes 0 B。And then we have 1，2，3，4， and then。Each 0 here represents4 bit。

 So the fair 0 is this4 bit。 And then this two， this number2 in binary becomes。This becomes。0，0。1。

And then over here0。 So if we count。This is pitch number0， pitch number1， pitch number two。

 pitch number 3。Pit number 4， bit number 5。Sorry， what I did here is for binary number four。

 this is binary number2。Right， so if we count' bit number 0， bit number one， bit number2。

Bits number3。Bits number4 and bits number5 so。In Hxadademal form， we simply write it like this。

This phase 4，0 is for this0。 This first 4 bit， this next four bit。Is equal to2。

And this is the same as writing。Shift one to position number five。Right。Right。

So you would see me use this method as well， iss the same thing。

 If you don't understand this example or if you don't understand this explanation， just let me know。

 I'll see you later。 Just let me know and I'll explain it。 I won't see you late。Okay。

 and we saw that we have to to set our alternate function type to you at we've got to use A F 7。

 A F 7 meaning 1，1，1，0。 we saw that already。 So I'm going create a symbolic name to hold that as well。

A F7。And let's call S LT。Meaning select AF 7， I'm going to say EQU。And what I'm going to do is 0 x。

So x 7。Ser， zero， and this corresponds to setting PA2。To A F 7 mode， which is the same as you at Mo。

 If you want， I can expand this for you as well。Okay。Over here。

 how do how do I know this exismmal number corresponds to what I want， Well， let's expand it。

This phase0。 We have two zeros here。 each， each x or demal 0 corresponds to four binary zeros。 So 1。

2，3，4。1，2，3，4。 This corresponds to these phase 2 zeros， and then 7 in in binary becomes 1，1，1。

 and then 0 here。So。As we know， the first fourbis as we saw in our war。A F R L register， H A F R L。

 you know， requires4 bit to configure。 So these phase four bit corresponds to P A0。

 These are four bit correspond to P1。 and this next one corresponds to P2。

And because we want to set it to A F 7， which is for you at， which is1，1，1，0。 we simply write this。

 And if you put all of this together， it calls this in a hexademal form。

So that is how come I know this？Right。Okay。So let's see how we're going to configure our U art。

 We're going to set the bar rate of our U at to 9600。And。😔。

This is going to be configured to work iss going to be configured to work with our 16 megaHtz clock because Ill just say I'll put a comment here for you what rate。

At 16 MHz， there's the default clock of my board。Right。And also， we're going to enable Tx。

Only Tx we using in just the transfer bit or the transmit bit， and the data is going to be 8 bit。

And there's going to be one stop bit。😔，No flow control。This。

 these are the parameters we're going to set for our U at。

 so I'm going to create symbolic names to hold all of these。

To hold the hexadademal numbers that we need to write to the to the registers to give us these settings。

 So I'm going to start off by saying B R R， this the B R， R， the board rate。Board rate register。

 I'm gonna say board rate register C and F for configure， and we would configure it with the。

Exter there small number。0 x，6，83。 And this will give us this set here。

If you go to the data sheet and you take a look at the board Ri register and you expand this to it binary form。

You realize that the bits that you set one would give you this setting。Right。The next one will be。

The C R1。C and F register， District control， register 1。Control register 1 configuration。

 I'm simply using C F here to mean configure these aren't registers。

 These are these are hex are demal numbers that we're going to be right into the registers just that I don't want us to be typing cryptic。

Numbers such as these， so giving them symbolic names to improve readability。So CR R1 enable。

We're going to pass 0 x。To x，1，2，3， and then 8。Okay， and this will enable T X an8 bit。Right。And then。

We come over here， CR2， we say CR2 configurefi。Sa EQU。And were simply going to。Pass 0，1，2，3。

And this will just give us one stop bit。Then we go to CR3 because thiss the default。

 so we keep it like this。Or we write it， we write this to it in case some other part of the application has changed the state of this register。

So CR3， CF。AQU we。Pass， 0，0，0 as well， and this will give us no flow control。And then after that。😔。

We're going to have。You are。To。Xier1 enablebel。And this will enable the U at once we've done setting the various configurations。

And this is simply2。Like this。O。Okay， were also going to have another flag known as the T X buffer flag。

 And this T X buffer is， is it's a particular bit in the status register that we have to check to see if the Paa is is full or not。

 So I'm gonna have the symbolic name or say T X。Bf。F， L G for flag。 And I'll say this equal。0 x。80。

 and if you expand this to its binary form。And you and you go to the data sheet。

 you see that the bit that is one corresponds to the bit in the register that checks the status of the buffer。

 all of these， if you want to understand more about them， you simply expand them to binary。

 you go to the data sheet and you see in its binary form， where do I find one and where do I find0。

 where you find one is what we are configuring essentially。Right。

So we are done with our register configurations。 now we can write our assembly code。 Okay。

 so let's do that in the next lesson。 I'll see you in the next lesson。



![](img/e1921c4d3b2c45ca86b6703f6f5ee523_37.png)