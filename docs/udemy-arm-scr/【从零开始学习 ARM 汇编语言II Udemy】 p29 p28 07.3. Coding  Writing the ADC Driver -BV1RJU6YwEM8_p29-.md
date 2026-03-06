# 【从零开始学习 ARM 汇编语言II Udemy】 p29 p28 07.3. Coding  Writing the ADC Driver -BV1RJU6YwEM8_p29-

Hello， welcome back， so let's develop our driver。I'm going to start off with the directives。😔。

Let me zoom in a bit。술받的？U。Code。Read only。And then we align。We run in thumb instruction sets。

There's the entry。 And can I export to one main label。And thiss corner is called main over here。😔。

And。We create our means sub routine from here。😔，Mean， so what's going to happiness when we start？

We go into initialize a war。what GP you soCL。Or branch to GPU in its sub routineout GPIU。

I justs go in it。😔，It's GPIU A we are using， so GPIU A anding it。And once we've done that。

 we go into。Initialize over ADC so I can see ADC1。話こう。In it。Right， so。

How about you post the video and implement the GPU in sub routineout on your own。Once you are done。

 you can un post the video and。We do it together。 Yeah。

 so just pause the video and try it out yourself。Okay， I suppose you may have tried it。

I'm going to implement the GPI Uni subrout over here。We start off by。You know， load。

We've got our enable clock access so we load。R0。With our RCC A H P1 enable register。Load our0， okay。

 and then we take the content of this register and put into R 1。

And then with the form or operation of this content and store the results back into R1。

Once that is done。😔，The new result would put it back into the AHB enable register with the store operation。

Like this。 Okay， and this would enable clock access to our GI port A。 Next， we going to。

Seets the mode register。 and we're going to do this twice。 First。

 we're going set P A 5 to an output pin。Because that's why our LED is connected。 And then next。

 we're going to set P1 to an analog pin。Because us that is our ADDC pin。

 That's where we connect our sensor。So see load。R0。And I'm going to load GPIU。え？Moode register。

 and I'm going take it content。Put it in register r1。

And then I'm going to perform on all operation and put a result back in R one。😔。

We created a constant called Mo R mode Mo 5 output meaning set pin5 of the mode register bits number 5 to an output pin。

And then we store the results back into the mode register by doing R1。I you over here。

Once this is done， we're going to。We're going set P1 to an analog pane。 so do load again。A Siu。

We could have combined both steps。 I can simply put a plus here， and add that。

But I'll break it down for you。Right， I I can simply put a plus here and add the bit that corresponds to that。

So I'll say mode， I'll say load， sorry， GPIU A underscore mode register。

And then we check the content to put it in register R1。

And with the former an or operation start the results back in our1。

The constant we thought we run the operation with is what we call the Mo1。Annalogue。Select。



![](img/8969aa997c6a8cc4bc4f2e56414cf490_1.png)

And what I was saying is I could just do this。

![](img/8969aa997c6a8cc4bc4f2e56414cf490_3.png)

Sorry about that。😔，I could call this instruction once more。I could do this。srry about的。

I'll show you this。😔，I could do this。Copy this， put it over here。😔。

I could do this and then just forget about this bit。Right。I could do this and forget about this。

AndComend this out。😔，This is one way of， you know， setting the mode to output。

 setting P5 to output in P1 to analog。Oh， I can even do this。

I can eliminate this other line and just do this。I can do this as well， and this should be fine too。

I'll leave that for you if。You want us start writing things in a shorter form。

 you can use such a method， but for me。I'm just going write it the long way。

 the amateur way if you may but later on I'll start shortenening it， you know。

 I showed you this so that later on when I write something like that。

 you understand that I told you it's a way of implementing this。

This bits that we are implementing now Anyway， moving on。

 So once we've performed the operation and the result is put back into our。

We can store the content of R1 into our。GpiR your mode register。Like this。Right。

So this is actually very straightforward。And we can return from the subrout， B XLR。Okay。

 so next we implement the ADC1 in it some routine。And。We enable the clock access to our ADC1。

 We do this through the APB to enable register。So do load。😔，R0 with the address of APB2。

The register is called RCC underscore APB。To。E and R。Right， and then once we've done this。

We're going to take its content and put it into our one， like we always do。

And we you going to perform an all operation。Install the result back into R1。 the constant is。

ADC1 EN。Then once the result which is stored back in R1。

 we can take what is in R1 and put it into our APB2 enable register like this。And after this。

 we would have clock enabled at ADDC1。Next， we're going to go to the ADDC control Register2 and select softwareftware trigger for our ADDC conversion。

So I'll start off by saying load。Load R0 width the name of the Regs AC1。C2。And then， of course。

 we fetch。😔，The content and put into R 1。And then we can perform our operation。A1。😔，S W trick。

 I'm sure you' are getting used to this Now。 It's just load store。

 load store load It's like three steps。 load， compute store， load compute store。 we load it。

 Our computation is simply the operation， and then we store。Yeah， so once you do this for。

 I'm sure once you get through once you complete this course。

 you should be able to write assembly language for assembly code for almost anything。

 because if you understand this load compute store paradigm。

 Then you should be able to perform any manipulations。

 The only thing is you have to be familiar with the instructions available， like speaking a language。

 you have to know the words in the language in order to be able to use the language is the same as assembly。

 If you know the instructions and how they are used。

 then you should be able to write in a program after you know the paradigm is load compute store and you know the the instructions to use for this then。

You way。To becoming a champion in assembly。So yeah， after we perform our own operation。

 we can store the results。R 1 over here and R0。And once that is done。😔。

This is going to select the software trigger because we created a symbolic name for this。

 And if you want to learn about the assembly instructions， the complete set。

 you have to take a look at the。I'm assembly programming from ground Up course Cota is the one that talks about all the instructions for the arm architecture。

This other peripheral course and the other peripheral course on TM4 C。Those are like the arm。

 those are the。The part2 of the arm assembly course。

 because these ones are specialization courses just for peripheral programming。

 but the other course shows how to arm。How to work with the various instructions in the。

In the arm instruction set architecture。Okay， so we've done this。 Now we've gotta con。

 We've got to select where the conversion sequence starts。

 And this is the constant we created for S QR 3 register。

 And we've got to access this S QR 3 register。' gonna do load。R0 equals80 c1。And let's go SQ。

The constant was called SQR3。This is the name of the registers in it。Okay。

 the constant was called SQL 3 cF。And the register is AC1 S QR 3。Over here， right？Okay， so。

Since we simply need to write this and we don't need to care about the other bits in the register。

 I'm not going to perform an all operation here。 I'm simply going to use move and then move our constant into register R1。

Moooth。And then， I see。S Q R3。And then CF。And then once that is done。

 I'm going to store what is in R1 into our SQR3 register by using the store instruction R 1。And then。

R1 and the N0 here like this。 Okay， so once that is done， we've got to configure the SQ R1 register。

And we're going to use the same method say load r0 equals。It is1。SQR1。Yeah。

 and then I'm going to move。or1。I'm going to move our constant into R1 here。

 and this constant is S Q R1， CF for configuration。 and I'm going to store it。

To they register by writing this。Okay， and once that is done， we can enable a war。

We can enable our ADDC， and we do that using the control register to otherwise known as the C R to register。

 So do load。20。ADC1， CR2。And then I'll take it to content to put it into register R1 like this。

And then。😔，I'll perform I'll perform an or operation。With a constant， the constant is CR2 CF。

 that's what we called it。And I'll store the results of this or operation into the control register2。

And once that is done， we can return from our subroutine BxLR like this。Okay。Right。

 I think I should add these， the C language。I've been commenting this with C a thinget of practice I should maintain。

Right， so over here。AndC language would do RCC。RCC A H P1。ENR。H P1， E NR。

And then we'll put a vertical line， and then we pass this constant that we created。

This is what we write in sea language。And then。Over here， what we do in C is。GPIUA。Mo register。

And then。We apply our constant。Would 5 old but this one a here。Okay， and then。

Over here in sea language， we still do GI U A。Moode register。It calls this over here。😔，Right。

And this one here， what we do。😔，Yes in three language， we do RCC。APB2， ENR。And we pass our constant。

 it is one enable。Like this。And。Onceat that is done。Over here。We access the CR2 register。

And we do this。把声音。ADC1， and C language ADC1。And then。The Reg CR 2。And then all。

We add our constant here like this。Over here the register is SQR3。We do ADC1。S QR 3。Oh。

And then we add our constant。Yeah， I like this。And then this over here。😔，It is one。

 there should be one over here。😔，It is 1， S Q R1。Then all。We add our constant over here like this。

Okay， and then the last one is the controlt register。😔，It is a1。See our two register。And then。😔。

We are a constant here。Although this， this has no a。

 So I delete this the verticalt line here gives us the a operation。We didn't use or here。

 So we delete this。 This has no awe as well。 So we delete this。 Okay， so in sea language。

 you have this。 You can try it。 You can copy the C code and put in a main C file and I expect it to work exactlyile the same way as the assembly。

 Right， moving on。 So next， we you going to crates。

Another sub routineout and this one is going to read DM the data。A as the ADDC1 read subroutine。

So I'm going to say8C1 underscore read。😔，And。What were you gonna to do actually？😔。

Did we create a constant for start conversion？Okay， over here， CR2 stuff conversion。Okay。

 I'm going to copy this that conversion constant。Okay， and then in。In C language， we simply do ADC1。

 CR 2。And then we start conversion。 That's what we're going to do first in our ADDC read subrout。

 So I first that。But Luden。R0 with or register ADC1 underscore score CR2。And then take the content。

And put into R1。Like this。And then we perform our all operation。

And then install a result back into our one。And then。Take the result。

 the new result and put it into our control register too。Like this。Okay。Once we've done that。

 we've got to wait for conversion to be complete。In sea language， we write this as well。AC1。

Stus register。And then we perform an end operation with with bit number one。

 So we pass two here like this。 Remember if I write two in binary。To in binary。Equals0 B。

2 in binary equals 0 B，0。One zero like this。So this is bits number0， bits number one。So if I do this。

 it corresponds to bits number one， co bits number one is the bit in a while。

Just's the bits in the world。S I register that we。We need to check。Right。Okay。

 so that's just a comment for C。And while this is not while this returns。Fals， then wait here。

 wait till conversion is complete。 essentially。 Okay， and once， okay， this is the C language。

 let's it implement it。 Yeah， I almost skipped it thinking we had implemented it after I have written the C。

 So to do this an。An assembly。We do load。Load， we load our status register， of course。8C1。

Studs register。And then load。I1。알저し요。And then we perform an end operation， this over here。

We perform an end operation。With the content of r1 and I think we created a symbolic name for the flag。

Okay， this is it。And then we compare that the result will be put back into our1。

 so we compare what is in R1。2，0，0。And then we do B， EQ。To the top。

Call this LP1 and put the LP1 label here。Right， so after conversion is complete。

 now we can go ahead and read our data register or to load。Or two。Equals8 is C 1。

Data register and then load。20。A two。 so we have the result placed in our0 that's the return register。

 the return value is gonna be in register R0ro。LR like this， okay。So。😔。

This is it weve finished implementing our ADDC driver。In the next lesson。

 we shall write a subrout to control the LED。 and we're going to create a threshold such that when the threshold is crossed。

The threshold of the analog sensor data。If it is crossed， the LED turns on and if it is not crossed。

 the LED goes off。 So this all there is for this lesson。 And I shall see in the next lesson。

 If you are finding the course useful， take some time off to leave a review。 I'll see you later。



![](img/8969aa997c6a8cc4bc4f2e56414cf490_5.png)