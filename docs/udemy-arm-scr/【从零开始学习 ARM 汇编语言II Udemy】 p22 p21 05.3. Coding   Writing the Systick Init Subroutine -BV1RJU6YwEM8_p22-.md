# 【从零开始学习 ARM 汇编语言II Udemy】 p22 p21 05.3. Coding   Writing the Systick Init Subroutine -BV1RJU6YwEM8_p22-

Hello， welcome back。 So let's continue。So I'm going to start off with my directives。

I'll just create a bit of space here， and we would have to remember to clean the space when we are done。

Okay， so I'm going to start off。Area。We're in the code area。And like I said。

 a prerequisite for this course is my other course arm assembly programming from ground up。

 We studied all of these。And this is the entry。😔，First we can put a thumb over here becauseuse we're using in thumb。

And。Export and ask underscore me。Right。Maine。And we're going to start off with GPIU in it。

And then once GPI in it， then we perform system in it。 we've got a branch。Then。Stistic in it。Right。

Okay， so let's implement GPR unit。And I would advise you post the video and you try to write the GPIU in subroutine on your own because we've written it over three times already。

Right。Okay， you can unpost the video， so we start off by enabling clock access to GPIU A。And then。

We do that by going through this process。And then finally， we store it。 After this。

 the clock access will be enabled。 Next， we we set the mode。We set a mode of P5。

 We set P5 to output mode。Like this。Right， so after this， we would have enabled our。

Our GPIU port A and set pin 5， P5 as an output pin。Next， we've got a。We've got to come out。

 we've got a return from the subroutine。BXLR。Next， we've got our initialized cyst。Copy over here。

 paste it over here。So we start off by configuring we first have to disable the cystic。

Timer before we we set it up， it's advisable to disable a timer before you set it。So。Yeah， I'm gonna。

We enable and disable cysttic through the cystic load re control register。 this one over here。

 I'm gonna。Copy this。And I'm gonna do。Lut。😔，R 1。And then this and then。😔，Or simply。Do I move。R0。

Zro here。 and then I'm going to store what is in。Au。Into the address found in Reg R1。

And this is essentially。Let's see， I'm gonna。Well。😔，哎。Okay。

 the reason I'm making this sound is I'm using a different name in convention here。Just bear with me。

 I know this particular lesson is all over the place。 but yeah。

 you get this when you are doing live programming。 If we are to write this， using CC's code。

We would do C and then we do CT T RL because Cs defines this as CT T RL NV here is defined in the Texas instrument document and maybe S document。

 But if CC， this is what will be written。So I'm just putting this in and those of you who have the bare metal version of this assembly course。

 you see that this is how we。We sort of disable the cyst timer。

 So this is what I'll write in bare metal embedded see， right。

 So I'll keep putting the C code here for you as comment。 I think you would find it helpful。It。

 it certainly helped me when I was learning assembly language to always see the C version。Right。

So after this， we would have。 we would， we would have disabled assistic timer。

 Now we're going to load assist。 I'm gonna do。LDR。A 1？And then equals n V n V load R。

Just register here， the load register。And then。I'm going to load it。

I'm going to load it with a maximum value 24 bit over here。 So I'm going to push this value。

 I'm going to put this。 I shouldn't say push because theys say push instruction。

 So say R0 equals this。So I'm going to take this and put it into this register and we would have loaded it。

And I simply use this store。Our0。Into Ar。 And when I say take this and put into this register。

 I'm not actually putting it into this register。 I'm putting it。

I putting it at the address of the content of this register。At the address of the content。

Of fire one。Wait a minute。 Is that a good statement Okay。

 a better statement is the address found in register R1， so I'm putting this value here。

 which is in R0 I'm putting it at the address found in register R1。Right。

And register R1 has the address of this Reg has the address of this says they law to register。 Okay。

 we spoke about this in the very first practical lesson。Okay， once this is done。We can。

We can clear the current register and we clear the current register by writing any value。

 we can even write0 to that register to clear it， so that's what we'll do next。U。

This is cautious stick， let's see。

![](img/4d004ef124db22ae701e28ddadc36eed_1.png)

I want to verify something here。 the Ci load register。



![](img/4d004ef124db22ae701e28ddadc36eed_3.png)

Thes reload register， Okay， so the reload register is sometimes referred to as the load。

 So in some documentation， you would find a cyst load reload register。

But we are using the documentation provided by arm。And。And Sam Siat， to write this。

I'm going to say cystistic。And it's a capital T here。😔，Sas thick and then。I'll say load。

And what we loaded actually， is this。We loaded this value。 Look at that I made this mistake here。😔。

So this is what we've done here。Right， now we're going to clear the。The sister current register。

And it's known as the current value register。 The issue is in the documentation。

 arm uses different words， but in the CMC standard provided by arm， they use another word。

 for instance， in the documentation load here means the reload register。

For those of you who don't know what CC is， C C stands for Cortex M softwareft interface standard。

 Yeah， I think so。 Coltex M software interface standard。

 and it's like a unified standard that makes a developer that gives a developer the ability to sort of use the same coding format for any arm processor so that when you are using。

A cortex from different manufacturers。 The way you write the code is the same thing。

 And what do I mean by this， The architecture is that you have a base address， and then。Everyum。

You have a base address and other registers are offset from that address。Like we saw in the。

In the GP in the GPIU section。The base address is implemented as a structure。

And the offsets are simply members of that structure。 and you access the offset。

Which are other registers using the using thearrow operator like you see over here。

 you can think of the structure name astic and control C T R L here is a member structure。

 and physically this is an offset from the address of cyststic。 and this。

 this arrangement is the same for any arm cortex microcontroller。

When you are using Cs so that you know that if I have an N XP microcontroller and I w to access their GPI U。

 the GPIU data register might have a different name。 It might， They might call it GI U。

Data U register and GIU data D register for up and down。

 But I know that I first have to go to GIU and then use the arrow operator to select data U。

And then use， you know， and then assign my value。 And if I'm using SD M 32。

 I first have to go to data register， use thearrow arrow operator to select their O DR or whatever。

 you know， you get what I'm saying。 You first have to go to the structure。

 Use the arrow operator to select your members。So by doing this。

If you already know how to program on one on one arm platform， I shouldn't say platform。

 If you already know how to program one board such as SDM 32。

 it becomes really easy to be able to program with with Texas instrument， why， because you know that。

When dealing with GPIU， there is GPIU， All the registers relating to GPIU are offset from the GPIU base。

And this means there is a structure called GPIU， and all the registers are members of the structure。

 such that in Texasex instrument， If I want to enable GPIU port A。

 if I want to set port A to Les say output， I'll face a GPU A and thenarrow D E N to select D arm。

The， the digital enable register， and thenarrowru。Data to select the data register， and thenarrowu。

D I R to select the mode register。 they call it a direction register。

 So I simply need to lend the names given to these registers that I'm already familiar with。

 but the paradigm structure arrow is the same across all arm code exports。 And this is C M C， right。

 if you have any questions regarding this， you can send me a message。 I'll be glad to elaborate。

 But forgive me for going on a tangent here。 But anyway， yeah。Yeah。So。So this is cystic。

 So we said we're going to clear the cystic current register and in C language， CMC standard。

 I'm going do cyststic。And the， the current register is known as current。

The current register actually is known as current value register， so it's called VAL right。

 they should decide on the name to use， so I'm going to clear it by passing zero to it。Okay。

 so let's do this in assembly。I'm going to do load。Ad 1。A error course。And Vic Esty。Current。2。

And then I'm going to move。200。And then I'm just simply going to write。

You know the zero into the current value register by simply doing install。20。I run like this。Right。

So next I'm going to enable system with a core system clock。And。In C language， what I'll do is this。

Look at that you learn in assembly and baremet embedded C at the same time for those of you who are not familiar with how to write this em baremet code。

Right。But I suspect most people who have this course has the baremet version， right？

 So I'm going to do this and I'm gonna do C T RL for control register。

And what I want to do is set it for the core clock。And we have this symbolic name for that。

I'm gonna do。Let's see。 we have this。 I'm going to set a core clock and then enable at the same time。

 So what I'm going to do is use the R operator。 I'm going to do this。And then。And nabu。All at once。

Right。O， so。What I'm going to do over here。What I'm going to do over here is load to the register。

Lo R1。And then。And Vic S。Control， register， and then。We're going to do move。R0。And then。This。Plus。

This。Right， and then I'm going to store it。啊是る。R1 and then。PXLR。

 So this is the end of the cysttic in it。Okay， right。So this is it。

Next we're going to implement the the cystistic weight subroutine and this is what is going to create the delay for us without prolonging this video。

We let's just continue that in the next lesson so that we don't end up having a 30 minute or one hour video。

 so I'll see you in the next lesson。

![](img/4d004ef124db22ae701e28ddadc36eed_5.png)