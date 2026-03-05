# 【从零开始学习 ARM 汇编语言II Udemy】 p26 p25 06.3. Coding  Developing the General Purpose Timer  Driver -BV1RJU6YwEM8_p26-

Hello， welcome back。So， yeah， let's implement。

![](img/494489777607460524688a3fc6df818a_1.png)

Ill code and。So I'm going to just bring in this standard stuff to reduce the amount of typing。

 these are our directives。underscores underscore mean。And then we're going to branch。😔。

To initialize our GPI report a。

![](img/494489777607460524688a3fc6df818a_3.png)

And。😔，I'm gonna bring in this subroutine causeuse we've sort of used it over。

 We used it almost in every， every lesson。 Yeah， every single lesson had。



![](img/494489777607460524688a3fc6df818a_5.png)

，How the LED blink in。So anyway， because we've used this over and over again， we need not ti it。

 I'm sure you understand everything involved there。



![](img/494489777607460524688a3fc6df818a_7.png)

Right。So this is the GPU unit now。

![](img/494489777607460524688a3fc6df818a_9.png)

Today's work， implementing the timer。We've got a。😔，I've got a return from this。😔。

P it letter like this， okay。So implementing the timer， I'm going to say timer 2 unscoring it， right。

😔。

![](img/494489777607460524688a3fc6df818a_11.png)

Okay， so we start off by enabling clock access， enabling clock access to the timer。

 and we do this by saying。

![](img/494489777607460524688a3fc6df818a_13.png)

In C language， I'm going to do RCC A P B1 enable register。

 and I'm going to apply friendly programming by putting the vsco line here。

 and I'm going to say timema 2 E N， right this single line with sort of thumb。



![](img/494489777607460524688a3fc6df818a_15.png)

![](img/494489777607460524688a3fc6df818a_16.png)

Do it for us by an assembly。 We've got to do load。Mipulate and then store。Right。

 so I'm going to do load。R0 equals。RCC AP PV1 enable register。And then I'm gonna do。

Take what is at this address and put into register R1 like this。And then once that is done。

 I'll perform the or operation。😔，A one， then。Timer to enable。And one I， once I stand。

 I'm gonna write it over there。

![](img/494489777607460524688a3fc6df818a_18.png)

St20。Okay， so this will enable clock access to our timer2。 Next， we going to set our。



![](img/494489777607460524688a3fc6df818a_20.png)

Preki I register。

![](img/494489777607460524688a3fc6df818a_22.png)

So， in sea language。How do timer 2。PSC。And then we created a symbolic name for what we want to write to the register the PC cF。



![](img/494489777607460524688a3fc6df818a_24.png)

PC configuration， and。Like we said， O， we rate。 we wrote a comment for this。

 I need not add explanation to this。Okay。So I'm going to simply do load。20。And then。

The name of the register。😔，Yes。We gave it a name timer2 PC。PC， O。

 And then I'm going to do Mo W Mo Ws used for moving， you know， data greater than 8 B to be specific。

 I think 16 B data we use this。So I'm going to do Mo W over here。Then， everyone。then， PSC。

Because we PSC CNF configuration， this is a symbolic name we created。



![](img/494489777607460524688a3fc6df818a_26.png)

Right， so I'm going to this， this。I1。二0。

![](img/494489777607460524688a3fc6df818a_28.png)

Right， now we go to the auto reload register and C language。 I'm going do timer 2 A R R。

And then we created a symbolic name for that， which is known as the ARR。CNF。

 and then the constant 10000 is stored in in this variable， And D constant1600 is in here。



![](img/494489777607460524688a3fc6df818a_30.png)

Right， so we're going to do exactlyly what we did load。R0。This time， they registered timer 2。

I've got the word I've got the number two over here， timer2， A R， R， and then move W。And then。R 1。

AR R。CNF。Right。And then STR。Awa。20。

![](img/494489777607460524688a3fc6df818a_32.png)

Like this。Okay， that next is to configure the。Timema2 count register and C language I'm going to do timer2。

Xianqi。😔，equコs 0。But we stored0 in a variable on a C and T cF， I suspect， let's see。



![](img/494489777607460524688a3fc6df818a_34.png)

C N TC andF it's over here， right。 So this is simple。I'll simply do。



![](img/494489777607460524688a3fc6df818a_36.png)

Load。20。Timea two。Xianqi。And then， move。I1。Xianq。😔，现内。And then， store。A one。20。

We don't need to use move S here。 It's fine。

![](img/494489777607460524688a3fc6df818a_38.png)

Just simple move is fine。Right， so the next， the next instruction。The next thing we need to do is。

To enable our timer。

![](img/494489777607460524688a3fc6df818a_40.png)

I'm going to come over here。And to enable the timer， we need to access the control register 1。

 So I'll say timer 2 and see language， I'll say timer 2， control register 1， and then pass the。



![](img/494489777607460524688a3fc6df818a_42.png)

![](img/494489777607460524688a3fc6df818a_43.png)

Past the symbolic name。

![](img/494489777607460524688a3fc6df818a_45.png)

The symbolic name we we did。😔，We don't need to apply friendly programming here。We can simply write。C。

 I1， CF， right， that's the symbolic name we give to it。 So I'll say load。20额。唱么 two。Xiauan。And then。

M。I1。Xiean。CNF。And then， store。😔，R1。20。Then， B XL R。



![](img/494489777607460524688a3fc6df818a_47.png)

Like this。 Okay， so this will initialize our time before us。



![](img/494489777607460524688a3fc6df818a_49.png)

Right。So in the next lesson， or should we。Yeah， I think we can finish in this lesson。

 We've gone just for7 and a half minutes。

![](img/494489777607460524688a3fc6df818a_51.png)

Okay， let's continue， I think。

![](img/494489777607460524688a3fc6df818a_53.png)

I suppose I getting used to。15 minutes。Lessons by now。Right。

 so I'm going to create another subroutin here known as weight or delay。

 So I'll see Is going to score weight。Coolです。Wait。And what we've gotta do is check the we've gotta check the status flag and wait until the U I F。

Which is a yeah， wait until the UIF is set the UI flag。



![](img/494489777607460524688a3fc6df818a_55.png)

Oh， oh load， dear。Sorry。I froze over there。

![](img/494489777607460524688a3fc6df818a_57.png)

Yes， sorry。 I froze for a while。 So we are going to create this the sub routineout known as white。

 And this is similar to delay。 So like I said， we've gotta check the， the， the status register。



![](img/494489777607460524688a3fc6df818a_59.png)

So I'm going to load it。Load。Then r1 equals timer 2。😔，Starters register。And。Okay。

 what I'm going to implement here in C language is going to be well。This is going to be。Timea2。

Startatus register。End。We created timer 2 status flag。

 We' gonna perform an end operation of this with this。 While this is not a case。 While this is false。

 then just。

![](img/494489777607460524688a3fc6df818a_61.png)

Wait over here。 This is what we're going to implement， right， So we do that by saying。

LDR take what is in， take what is take what is found at the address stored in register 1 and put it into R 2。

 So we do R 2 and then R1 like this。And this essentially reads the statuss register。

 and then we use end。And then R2， and then we already have this symbolic name timer 2。



![](img/494489777607460524688a3fc6df818a_63.png)

Stud is。TheStud is raised there and then flag。😔，And then we compare。😔，By saying our2。

 compare and see if it's 0 or not。And then we B， EQ。I'm gonna create a label here。😔，For the loop。

Right。So， we wait。We keep doing this until it's no longer0。 Once it's no longer0。

 we've got a clarity the the arm。 we've got a clarity status flag。



![](img/494489777607460524688a3fc6df818a_65.png)

And。Well， let's see。 I'm gonna put two comment here。Claire U IF。Claire U IF。 And then in C language。

 I'm gonna write this as timer 2。S R， and then I'm going to clad a bit。By doing this。

This will the flag。 So this is what we're going to implement in assembly。 So do LDR。Of3。A1。

Yhy R1 co R 1 has time or two status。 Were putting it into R 3。 and then I'll use the B I。Yeah。

 the B IC。The bit clear instruction。R 3 is stored a result in R 3。And thenll pause x。Ser one here。

I'm using three opera here。 Its fine。 You can use two opera。And then。I'll store what is in R 3 into。

 you know。Our， our status register。N1， and then BX L。Right。Okay。So now let's write our test code。

 I'm going to write。I'm gonna to write a sub routineout here known as LED blank。

 And this is going to blink our LED。LED blank。And what I'm gonna do is I'll start off by loading。

Are4 with our GI U A B， S R， R register。And then I'm gonna， I'm gonna turn on the LED or turn it off。

 move。Ill stop by moving。The the reset value， which we created a symbolic name for known as B， SR。

 R 5。Reet。And then。Im to move it into the register proper by doing store。

And then I'm going to branch to our weight。Then once it's off and we've waited for a second。

 we're going to tear it on。So I'm going to move。B S。BS or R5 set， I'm going to move this to register。

😔，I'm going to move this into our one， and then I'm going to store this into our BSR R register。

So r 1， and then r 4。And then I'm going to wait again。😔，And underscore weight。😔，And then。

 I'm simply going to。Create a loop。Come back here。And then our line and then。

I'll put the end directive there's the end。😔，Right。



![](img/494489777607460524688a3fc6df818a_67.png)

So over here， I can simply come here and。😔。

![](img/494489777607460524688a3fc6df818a_69.png)

Well， let's see。 I'm going to call this once we've initialized our GPIO。



![](img/494489777607460524688a3fc6df818a_71.png)

We will have to initialize our time as well。IllCom over here。Bll， and then。Timeimer2。😔，Like this。

Okay。Right， let's build and see what we have。 Click over here to build。



![](img/494489777607460524688a3fc6df818a_73.png)

So the target not created。😔，Yeah， it's a type or somewhere。😔。



![](img/494489777607460524688a3fc6df818a_75.png)

A P， B1， RCC underscoreco， AP P， B1， E， N， R。Not defined。 If people want enable， register or defined。

 thus what it is telling me。She。😔。

![](img/494489777607460524688a3fc6df818a_77.png)

![](img/494489777607460524688a3fc6df818a_78.png)

Yeah， I put E here。 Sorry bother there。PS SR R。Yeah， there should be 5。Okay。



![](img/494489777607460524688a3fc6df818a_80.png)

It's built successfully。I'm going to debug， select my S D link debugger set F download。

 Click over here， reset and run O， and then O， click here to download onto the board。It's downloaded。



![](img/494489777607460524688a3fc6df818a_82.png)

And as you can see， our LED is blinking at a1 hertz。A rate。

 So your exercise for this lesson is to be able to write a C function， create a C file。

 and then create。A general purpose time dot dot S file and then import our weight subrout here and import all the subroutines we have here and run the code in C。



![](img/494489777607460524688a3fc6df818a_84.png)

![](img/494489777607460524688a3fc6df818a_85.png)

Like we did in arm， I think it was in the U art section that we showed how to export our assembly subrouts and call them in C code。

 are likely to be able to blink this LED using C code such that this LED blink。



![](img/494489777607460524688a3fc6df818a_87.png)

![](img/494489777607460524688a3fc6df818a_88.png)

This LED blank implementation should be done in a main dot C file。Right。

 if you face any difficulties， just send me a message。 I'll be glad to help you。

 So that's all there is for this lesson。 if you have any questions， just。To send me a message。

 And if you're finding the course useful， just take some time off to leave a review。

 and I'll see you later。

![](img/494489777607460524688a3fc6df818a_90.png)