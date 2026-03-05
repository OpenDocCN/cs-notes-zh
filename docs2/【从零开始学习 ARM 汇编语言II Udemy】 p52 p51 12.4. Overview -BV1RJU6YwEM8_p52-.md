# 【从零开始学习 ARM 汇编语言II Udemy】 p52 p51 12.4. Overview -BV1RJU6YwEM8_p52-

Hello， welcome back。In this lesson， we shall give a quick overview of SDM 32 Cuba X。Okay。

 so my cubeba makes us open over here to create a new project， I can just click。

I can open existing projects if I had existing projects。 that will be listed here。

 but I do not have any， so。There's nothing here I can start from Access MCU selector Access Bo selector。

Or access cross selector。Right， one other key point is the the tabs we've got over here。

 we've got a file type for new project load project and a list of recent project if we have any。

 we've got a Windows type。And this allows us to set the the font size， et cetera。

 And then we've got this one。 this very important one。 The help one。 When you click on help tab。

 you can check for updates。 You can manage embedded software packages。

 Let's say you want to install a B， L E for Bluetooth low energy。

 If you want to install a Bluetooth low energy package or some other package。

 You've got to come to manage embedded software packages to do that。

And you can set your user preferences by clicking over here as well Over here。

 you can give consent for data to be sent to S microelectronics to sort of monitor the usage of K X in order to improve the product。

As said it's written over here， if you don't want to do that， you can simply uncheck this。Right。

 and you can check for updates as well by clicking this。

 So I'm going to start a new project by coming over here， Access to board selector。 or click here。

It's opening， it's the first time， so it's taken a while。

It's still got certain things to download and on zip。😔，It's quickly doing that。



![](img/4906809a7ab4e0295633feaff35d52ae_1.png)

And it's opened。

![](img/4906809a7ab4e0295633feaff35d52ae_3.png)

So here we are。 we've got our various development boards over here。 we've got the discovery ports。

Different types cause I'm under the port selector。 If I want to select just the MC U chip。

 I can click over here and simply search the chip of the SDM 32 F 41，1。And then it will list。

 And when you check here， it gives the parameter。 I gives the price range as well over here。

 the price that from 2。284 to 3。45。 I can reduce the price range if I cannot afford all of this to reduce the options。

 These are the options that I have， if I want the price to be within this range。Right。

Because the the cube mix is set up from， you know， prototype into development such that you have a clear picture of what you are dealing with over here as well。

 it gives the peripheral flows available on a particular port。

 We can filter by peripheral flows as well。 So should I say I want。I want two ADCs。

And other peripherals， I can just enable them and hit enter and cube X will suggest。

Other MCs that I can use。So let's see you can select by core as well。

 this one that I typed is a codetex M4 that is why just codetex M4 is highlighted。

I can delete this such that I'll let Cuba X make the choice for me。

 I'm going to select codetex M33 over here。And it gives me the options， these are the options。

 and these are the peripherals available as well。Right， so this for the MCU selector。

Let's see how about code X M7 I've included code X M7 and it's increased my list。

And we can check for the lines over here whether we want F1 series。F0 series， etc and。Okay。

 this is what I meant by the lines， F1， F0， etc。And then the prize。😔，The package as well。

 you can select the package if you are into designing your own PCBs。

 you can filter by packages as well。Right。So。I'll just close this and then I'll come back to board Selector。

😔，And then I'm going to just select the nu。F 411 VET。



![](img/4906809a7ab4e0295633feaff35d52ae_5.png)

There is the nucle F411 over here， test I will click this。And when you highlight it。

 it tells you it gives you the specifications of the board。If it obsolete。

 it would tell you it's obsolete， but this is active。 Therefore， it is written。 and at market price。

 the retail price is over here。 This is $13 and the features of the board is listed over here or are listed over here。

 I should say。 And if you want access to the data sheet， as well as other documentation。

You can click these tabs over here to take a look at them。Okay， so once I've highlighted。

 I can double click it or just click Start project over here like this。And。When you select a board。

 it would ask you whether you want to initialize all peripherals with default mode。 I'll click， yes。

And it's setting up the project。Okay， so that's what it looks like。



![](img/4906809a7ab4e0295633feaff35d52ae_7.png)

So there's our nuclear MCU over here， these are the default setups and we've got the push button enabled for us。

We've got the LED also set as an output pin。And then we've got the U art at PA2 and PA3。

And then we've got other things with regards to the serial wire interface and the clock settings。



![](img/4906809a7ab4e0295633feaff35d52ae_9.png)

Okay。

![](img/4906809a7ab4e0295633feaff35d52ae_11.png)

So。This known as the pin out view。 we've got a pin out and configuration tab over here。

 we click to set a pin。 Let's say I want to set P81 as an output pin。

 I will simply click this and select GPIU output， and it becomes an output pin。

 Let's say I want to rename this。 Al right， click this and say enter user label。

I can simply call this my output。And then it becomes an output pin as simple as that。

 If I want to set it to a different type of pin， I simply click and select the type that I want。

This is known as the M。Thiss known as the pin out， pin out and configuration view， right。

 And I can drag。I click and hold to drag to move it around。 It's allowable to do that。 I can zoom in。

I can zoom out。I can rotate if I want。Right， okay。So that's the pinout view。 And we have these。 So。

 you know。In microcontroller setup when we select a pin。We've gotta do further。Felder configurations。

 And what I mean by this is to set up。To set up something like a U U。

 A U U is an alternate function on the MC C U。Meaning we take a GI U。

 and then we set its alternate function as you at before we are able to use it。 So， for instance。

 if I want to set this as you at， as it is done over here， after I have selected it as you at。

 I've got to come over here and configure it alternate function。So under the system core over here。

We are given， you know， we are given options to configure our GPIU and these often we wouldn't talk much about these。

 We just explain them when we require them。 Rcc over here is the bit that configures these lines our clock high speed external we're not using this So we are same bypass or we can simply say disable As I click disable。

 you realize that this chain to yellow。But。I can see bypass。

 which is at default modeest to green and low speed extend or here， Thus。

 we are using a crystal for it。 So if I disable it。

 you see that its pins will get disabled from here。So as I click theable， it becomes yellow。Right。

 yellow means you've set the GPU。 You've gotta go and do its actual alternate function configuration。

 So whenever you see a pin as yellow， it means its setup is incomplete。So I'll say you ceramic。

And then it's back to green。Right， and then S W over here。The zero wire， I can disable it。

I'll show you that is on the other side。 I just disabled it when I say use zero wire。

Atend back to green。Right。And this you can still you disable a pin by selecting reset。Okay。Right。

 and we've got tabs here for other configuration。 If we want analog configuration for our ADCs。

 we simply click analog and then we select our ADC。 This MCU has a single ADC module。

 but this single module has about 16 channels。So if we want an ADC。

 this is where the configuration will be done， but we're not using an AC now。So ADDC is under analog。

 we've got timers， and this tab allows us to configure our various。General papers's timers。

 as well as our real time clock。We've got connectivity as well， this deals with things like the I2C。

The SI and the U U。As we can see， the U at 2 is set up over here。 That is why it is green。

 and that is why we've got a correct or atic over here。

So to see the configuration or to change the configuration， I'll simply click here。

 and as you can see。It says mode is synchronous and then hardware flow control disabled。 O。

 when I disable this， when I come over here mode and disable it。

When I come over here and change it or disable it。You would see that these pins will be affected because these pins are the ones connected to the U U。

 Let's say I go single wire。You see now we've disable the Rx line。

 it shows that the Rx is back to yellow meaning。 its configuration is incomplete。

 single wire or half tuplex means just one direction communication。I'll go back to asynchronous。

And then this。Is here。 and the configuration of the actual ADC or the actual U I should say。

 is down here。 things like the board rate we can change over here。

 the word length we can change and select。The parity。The data direction， etc。 if we are using DMMA。

 we can click over here and add。And GPU settings。We know is P2， PA3。 When we selected these pins。

 they go added here automatically。And whether we want to set ADC interrupt we come to NVI settings。

NVx stands for Neested Ve Interrupt controller。So yeah， so connectivity provides us access to our。

Connectivity modules and these are the I2 C， the SPI and the U art。Okay， the next one is multimedia。

 We have I2 S over here， which we can use for sound and other things。 We've got computing。

 and we've got this modulejo known as the CRRC， meaning the cyclic redundancy check。

 we can use that as well。 If we want to add at a middleware such as a file system。

 we've got fat Ephs that we can include here。We can also include a real time operating system like free art。

 and we can include the embed TLS if we want， as well as USB devices。Right。

 so these we talk about them deeper when we are using them。

 The next tab up here is known as the clock configuration。 So we can simply click here。

 and this gives us a view of our clock。We can， we can increase the clock frequency。

 It says over here the max is00 MHtz。 So we've got to keep thin mind。

 and we can know the clock for our various peripherals。 For instance instance， over here。

 it tells us that the clock for our time is the time is connected to the AB1。The A PB1 bus。

 the oclock currently is set at 84 MHz。The clock to the cortex system time or the cyst time S clock is 84。

 et cetera。 So over here， we have exactly the values that our various peripherals would have for their clocks。

 So let's say I want to increase the clock to 100。 I simply need to。Type 100 here， hit enter。

And iss going to configure everything appropriately。 And it's sort of rearranged everything。

 And over here， too， we can see we are using the high speed。

Internal H S I here stands for high speed internal。 Remember in our setup。

 we say it bypass high speed external HS E。 That is why this is selected。

 High speed internal is being used。And we are also using low speed external。Right。

Are we using low speed external， let's see。U。So we said low speed external use the ceramic。

Cerammic resonator。 And I think there is a ceramic resonator or oscillator on our PCB。

 on our microcontroller，board I should say。Okay， so this a quick overview of the clock tab。

And then the next top。Let's see toolss， there's this tools here。

 which you use for checking the power consumptions and other things with regards to your your port。

The final tab in the process is to click the project Manager tab。And over here。

 you can give your project a name。 You can I'll call the simple。

And then you can decide on the tool chain you want to use。

So I can say I want to generate code for STM 32 cube IDE M MK。哦，あ的。Other Ide， if I prefer。

 So this allows me to generate code for various Ides。 and you can come over here。

 This is the project。 There's another taba called code generator。

Okay it says a project location cannot be empty， so we've got to give a location for a project。

Let's see。A create a folder called Q M X。Okay， so。Right。

 so let's say we want to generate a project for SDM 32 cube I DE。Like this。

 And then there's the code generator here。 And over here。

 you can take such that your files are separated into their various dot H and dot C files。

 I often do this。 So you simply tick here like this。

And then once you've selected the IDE you wish to use。

 you can simply click generate and it would generate it for you。

 We see how that works when we start dealing with actual projects。And there isn't much anymore。

 We can also generate a report over here。 We can generate a report for our setup。

 Simply come to file， generate report over here。And then would you like to create the project first。

 I'll click here because the project hasn't been created yet。Okay， the report has been generated。

 so I'm going to open the folder。And the report comes in two formats thats the TX D file。

 as well as a Pf encapsulatingulating all the selections you made。

So I'm opening the PDF so that we take a look at it。So there's the PDF。

 the project name and the MCU you chose。As well as the date all of it exists。



![](img/4906809a7ab4e0295633feaff35d52ae_13.png)

And this is the pin out。And your clock configuration is also included here。

As well as the other setups that you have， the RCC set values。 you find them here。

 This says the U art。Everything is included here。 so there's the report。



![](img/4906809a7ab4e0295633feaff35d52ae_15.png)

Right。So there's a quick overview of the SDM 32 QM X5。

 If you have any questions at all just send me a message or leave the questions area and I shall see you in the next lesson。

 Have a nice day。

![](img/4906809a7ab4e0295633feaff35d52ae_17.png)