# 【从零开始学习 ARM 汇编语言II Udemy】 p16 p15 04.5. Coding   Testing the UART Transmit (TX) Subroutine -BV1RJU6YwEM8_p16-

Hello， welcome back。Right， so let's test our code。So， this is our main。We start off by。

Brunchching to initialize our U art。Okay， once that is done， O， let's test it out。

 with' initialized after this。 The next thing I'm going to do is I'm going to move a character to register Airro because remember our argument is stored in register Arairro。

 so Ill say Airro。And then I'm going to pass。0 x59 this corresponds to hexadadeimmo。

 and this corresponds to the letter y。This corresponds to why。Okay。

I'm going to send this and see what it looks like， so I'll move this into our0 and then I'm going to branch。

😔，To our U at right subroutine。Right， this are you outright characters， Sa routineoutine。And。😔。

I'm going to once we're going to write this in a loop。😔，We're going to loop forever。

 You can think of this as a world1 loop。So I'm going to put the label for the loop over here like this。

😔，Right， so if you don't have any zero program I have I'm going to take a video on how to install Terra term from one of my other courses and add it to this course so that you can install one。

 I have Terra term this one here this is the one I use so this is what we're going to test with I' will include the videos for downloading and installing that here。

You can go to the setup section if you've not done that， you can go to the the。

The last sections of the course。 often I include such things in the last sections。

 So that people who already have that installed， I don't want them to be blocked by such videos。

 So if there is something that I use and you don't have it installed。

 Just check the last sections of the course。 there is a video that should be a video there showing you how to install it。

 how to download and then install it， If you do not have Ter them， check that side and you find it。

 Okay， I'll click here to download my board。Let's see what we have。😔，We have one error。😔，B symbol。

 it says because we forgot the equal sign here。😔，I'm going to click here to build。😔。

You attitude not defined。😔，Yeah， you see what's happening here a number of typos， so about there？😔。

What is this you ought to enable？😔，This is number one。😔，Put this over here， you are to enable。😔。

This one is missing an A。😔，You at to。😔，迪二诺。😔，Oh man， okay。

 we didn't create the address for the U art data register。😔，Right。

 so let's go to the data sheet and get the offset of the U data register。あ。Come over here。😔。

Controrl F。嗯。Let's do well， let's go to the table of content。 I wanted to search DR。

 but as if almost every single peripheral has a data register。Not everyone。

 but a lot of them have a data register， the ADC has a data register at peripherals of data registers too。

 so it's going to be a long search。It's going to be quicker to screw down like this。😔，Over here。

Where is it？This U at， okay， U at D R。 okay， this is the offset，0 x，0，4。I think we sorted this out。

 you say。😔，0X，04， let's see。Well， we don't have it， okay， so let's create it。😔，gonna see。You are to。

第二。Offset。Icue you and this the offset。And then。You add2 DR。you are 2DR IQ equals。The base。

 you ought two bays。Plus， the offset。Right， so now we have our data register。Okay。

 let's build again and see。It's built successfully， I'll come over here。😔。

I' set up my target options。😔，Debagger， I'm using the SD link debugger。I'll click settings over here。

 Flash downloadload。I'll select reset and run。😔，Okay， and then okay。

I'llCl here to download onto my port， it's downloaded。I'll go to my serial program。😔。

When you click Teratem， this is what opens， you go to serial， and then you select the port。

 this my port， STM， microelectronics。Then I'll say this， and then I'll click to reset my code。Okay。

 nothing is happening， let's see you。😔，What we have。Okay， let's inspect our code。First of all。

 we have a typo here， the offset for D R。 When I was copy and paste and I paste at this here。

 you add2 E， N over here by mistake。 The offset should be 0 x 0，0。

 like we found in the reference manual。I'm sorry the the offset of the data register is 0 x 0，4。

 no0 x。0，0， issue is0 X04。 Let's try our code once more of the。 I'll download onto my port。

 orll check my0 porter。And I'll select my comp here， this one。😔。



![](img/aa5f1217e4a7ca0291f06153800af950_1.png)

And I'll press the reset my board。😔，And this is what we have， as you can see it。Why， why， why， why。

 just like we are printing over here。😔。

![](img/aa5f1217e4a7ca0291f06153800af950_3.png)

Okay， so it's working， let's print something more。I'm going to。个是。Let's print multiple characters。

How about we print yes， and then we print new line。New line， new line。

 I'm going to create a label for new line。And what I mean by new line is， you know， new line。

 you've got to send the courage return， C， R， and then L F， which is the line feed。

 I'm going to create a number of symbolic names here for。Asky symbols that we often use。

I'll come over here and I'll say C R， which is courage return。See R over here。😔，一Q you。C R。

 the code for CRRS， Xod mode 0 x0 D。LF for line feet。EQU。It is0 x。0入 a。We have B S。A Q U。

 this one is 0 x。28。Escape， if you want to send the escape key on the keyboard， this one is EQ U。

This one is。Z x1 B。How about space， if want to send space。Space is a directive。

 that is why it became blue， so let's just use S。The code we send to right space is 0 x。2，0。

How about deletes， if wantna delete something。EQu。Sure x 7 F。Okay。So， I'm going to send。Okay。

 so this is， yes， I'm gonna send。I'm gonna I'm I've sent y。 I'm gonna send E。 and then I'll send。S。

 then I'll send a new line so that it would print Yes， new line， Yes。

 new line and so on and so forth。 So come over here， move。 We always pass the character。

 we wantna move we want to send into register Arro。And then we branch to our U at right subroutine。

So the code for E is 0 x65。And then。Once I've put in our0， I can send it by going to you at。Right。

 character。Okay， so this will send E。And then I'm going to send S。 This is oururro。只X。

Why we've said why。😔，E。The code for S is 73。I forgot。There should be a comment。😔。

So put a comment sign here as well。😔，Okay， so after this。We simply bru。So we are going to send yes。

How about we send the new line？New line， we have to send C， R， and then send L F。

So I'm going to move the courage return， move。😔，I youu。And。😔，We have courage return。😔。

We have this over here at SiR， I called Sir， so I just bring the code here。😔，C R。

 and then I'm going to branch。😔，So we move CR。And then we branch。😔。

You add right character once I stand， we've got a sin。😔，Ettle F as well for line feet。 So do move。

Lin biu。😔，Right character like this， okay。Let's build in see what we have。😔。

I'm going to click here to build。😔，We've got a tripo here。I'm going to click here to build。

 click here to download onto the board。😔，And I'm going to open Terim from here。😔，And as you can see。

 we have yes， yes， yes， yes。As you can see， I'll come over here， let me increase the font size。😔。

Should we hear fonts。Okay， so this one we have。😔，So we are sending YES。



![](img/aa5f1217e4a7ca0291f06153800af950_5.png)

Right， later on， well see how to be able to easily send more text， we will be able to use Prif。



![](img/aa5f1217e4a7ca0291f06153800af950_7.png)

To send sentences， right。 So this order is for this lesson in the next lesson。

 we shall see the the the R X part of U at， meaning we shall see how to receive information from the computer。



![](img/aa5f1217e4a7ca0291f06153800af950_9.png)

Okay， so if you have any questions， just let me know and I'll see。

