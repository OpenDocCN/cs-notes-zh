# 【从零开始学习 ARM 汇编语言II Udemy】 p17 p16 04.6. Coding  Writing the UART Receive (RX) Driver -BV1RJU6YwEM8_p17-

Hello， welcome back。 in this lesson， we shall see how to receive characters。Through the U。

 we going to。Configure our U add driver to receive from the other side。

 we saw how to transmit in the previous lesson。 Now we're going to see how to receive。

 So I'm going to make a copy of the last project。IP this over here。I'll call this number 7， U at A。

And double click to open it。😔。

![](img/a3c5a4a55179b467a549e1b0decf1998_1.png)

All right。 So we just need to add a few things to our current project to be able to receive data through the U at over here。

 we have the T X flag。 We need another flag for R X in order to check whether the receive p is full。

 So I'm going to create an RFf an R X flag here。Sa R X B F。X。B F flag for R bufferffer flag。

EQ you and。The flag here were looking for is 0 x20。

If you go to the data sheet and you check the status register and you expand this hex more code to it binary form。

 the bit that is one corresponds to the bit for checking whether the receive buffer is full or not。

 So I'm just creating a symbolic name to hold this here。Right， once that is done。

 we need to be able to configure our PA3 as well， remember。On our microcontroller， PA2。Is our T X。

 our transmit pin， PA3。Is our Is so far， we've done the alternate。Alternate selection for P A2。

 We've selected in the mode register P A2 to be set as an alternate function pane。

 We've also selected in the alternate function。 alternate function lower register。

 we've set P A2 as U at。 Now， we've got to set P A3 like that。As well。So I'm going to come over here。

😔，Over here， we said A F select A F select over here。 Remember。

 we said in our A F in our alternate function low register。

 we need4 bit to configure a single pin like we saw earlier in the in the reference manual。

 We saw that This one here。 This fares 0 here corresponds to 4 binary bits。

 And this is used for configrine。Pin 0 of any port。

 This next one here corresponds to another four bit。 This is4 bit and hexademo at 10 here。

 And this is for con for configuring pin  one of any any port you are dealing with。

This third four bits here。Is for configuring pin 2 of any port you are dealing with。

 Now we want pin 3， so。We simply pass 7 here。 So I'm passing 7 here。

 I'm going to disable the T X functions。 So I'll pass 0 here。 such that。This is what we have now。

This four bits for configuring Peter pin 0， we skip it。 This for con configant pin 1， we skip it。

 This for configant pin 2， we skip it。 This for。For configant pin 3。

 we said it to you at hence we have three zeros here。And then to seven， okay。

So this would configure a P A3 for you at and the P A3 is the T X line。 Later on。

 we shall see how to combine T X and R X and will have both of them configured。Right。

So for the GPI also， we need to configure P3 for alternate function。The the code for GR U O。

For P A 3 would be 0 x。 if we take a look at the data sheet， we need to do 0 x 0，8。We need to do 0。

8 or 0 x，8，0。 if you wanna mention it like that。Now clean this。If you expand this。

 you realize that this corresponds to configuring pin。

P pin 3 as alternate function in the mod register。Right。So what else is there to change？Okay。

 so we need to go to our U at configuration constants as well。 and then change a few things。lexi。😔。

Over here， okay。So we have our control register。 Where is it， We've got our control register。

 this one here， we're going set a different board rate。So how about we use the board rates， we use。

The other popular portrait is 115200。 We can set that here。 there the hexa theres more code for the0。

0，8 B。So now our part rate is going to be 115。1，1，5，2，0，0。And over here， C R1。

 we are going to configure it for RX for receive mode。For receive mode， we need to。Right，0。X 4 to。

 to our control register 1。Everything else remains the same。Right。

And what we're going to do is we actually going to enable an LED such that if we receive a character。

 the LED be turned on。So I'm going to add the the code for enabling our our green L again。

 so that I mean， we're going to test receive。So we would see that the LED comes on whenever you send a character from the keyboard。

I'm going to add number of。Symbolic names here， I'm going to do GPIU。GPIU。Out S O T。一Q u。

And wish shall use this。😔，To set our LED pins outputs，0 x。4，0，0。 we did this before。

And where do you have GPU A enabled。And we've got to do GR GPIU。

Moode 5 outputs course remember our LEDs connector to P 5。 So I'm going do。

 I'm gonna create a symbolic name for mode 5。Out。And this is equal to。Set in on。

This is equal to set a shift in。1 to position 10。So this over here is the same as this。

 so we can use one of them。 if you expand this， you'd realize that。This corresponds to7 bit 10 to 1。

Okay， I saw clean this。 I don't know why I was going to use that because I was trying to follow this naming convention。

 but with， we already created a naming convention for accomplishing the the。

 the same thing in the previous LED， you know。Project so we keep this right。

 we're going to set the LED on and off using the BSRR register， the bit set reset register。

And we've got to create that， we've got a create the address for that。

I'm going to come over here and include it offset。PS SRR。

 we use it in the in the print fierce project， so we need no create。The address， again。

 we didn' not fetch it from the data sheet。 I just paste it here。

 We found that the offset for this re is this， and we created by mode。

 the GPI A base plus the offset。 Once that is done， we're going to create symbolic names to help us。

Set and reset the the pin using the B， S R R。 So I'm going to say B， S。B S。R R 5。Ca our penis P5 set。

To set。😔，We gonna shift。One to position 5。And we're going to do PRR。5 reset to reset。

 we've going shift。 We're going shift one to position 21， as we saw in the reference manual earlier。

Right。Okay， so what else is left？We already have everything we need， we can stop。😔，Implementing。Okay。

So since we've changed the values for these constants， these constant， these configuration constant。

Then we don't need to change the U add at all because these new values will be written to the various registers。

 so we wouldn't need to change the。 The first thing we would have to do moving forward is to arm。

To set our LED。 So we've got to access the Mo register and set pin 5 as an output pin。And。

I'll come over here。😔，So what we need to what we need to do is。GピIオ。More register。😔。

And then what we want to do is。Mood。Would5 out。😔，This is what we want to do， so let's do this。

I'm going to load。R0 equals。GPIO A。More to register。😔，And then。R of1。20。And then。

All operation are one。😔，And it correspond on to this。The constant is more 5 out。 Okay。

 so that was correct。UWhere is it？😔，It's over far here。😔，Over here， okay， so one step is down。😔。

Go to do this。R1。A you like this。Right， though this is going to set our LED pin as an output pin。

Okay。So we've got to write a subroutine for you at Re so that we can read them。

We can read what is sent to us， because over here in our T X example， we had a U at right character。

 Now we want to read。 So I'm'm gonna say U at。Let's go read。Read。Chaaw like this。And we start off by。

😔，Loowad in the data register。Load R1。You at2。We start off by loading the status register first。

 we've got to check what idea the receive buffer is full or not。So we load that and then。

Well read the content of the status register by doing load。R2， loading to R2， the content of。

The register the content of the address held in Reg R1 this essentially read。

This will read our status register for us。 Okay， once we've done that， we can perform end。And R2。

 cause after we read it， we're going to have it in R 2 so we can do N R2 R X。Bf。Flack。

And then we compare to0。The results after this end operation。

 the result is going to be starting in R2 so we can compare this result。To0 x00。

And then we branch if equal， we branch to。We can branch to。I loop。

 I'll create a label called I loopop。And the label will be over here at the top。😔，Right。Okay。

 so this we're going to read。 Okay， so we keep waiting onto the arm。 They receive Pafi nofu。

 Then we move on to。You know， reading the content in the data register because if something is sent to us is going to be its going to be in the data register with so we've got to read it。

 so I'll say load the data register。First by seeing R3 equals。Of course you add to data register。And。

😔，Load。Load the content， load the content。😔，At the address held in register R3 into r 0。

 So r0 is going to be our return value。 The return value is going to exist in register r0。

 essentially。 So then we do B X LR to return from the subroutine。Like this。Okay。Okay。

 so what we're going to do is。Were going to design a simple experiment， such that。

If you press one on your keyboard， the LED turns on。 In other words， if our were。

 if our U at receives the number one。Then it's going to turn on the LED。

 so I'm going to create a new subroutin here known as。I'm going to call this LED blank。😔。

I'm going to call this LED blink， and I'll start off by Ls C。😔，I'm gonna start off by load and D。那11。

O。Okay， so we said the return when， when we receive a character。

 the character is going to be stored in。 Reg r 0 according to the the code weve written here。

 So I can use r 0 for comparison， or I can just transfer it。

 So I'm going to transfer what is in R 0 into r 3。 and then we perform the comparison from there。

And what do I mean by that， I'm simply going say move。Let's see。 I'll start off by moving。Into our3。

For this in r0 like this。 And once that is done， I'm going to compare this to number one。

 So I'm going to do comparearrow 3。To compareare the content of r3 with this number here。

 this exodademal number 0 x0，030。Right， and this corresponds to the code of key1 on the keyboard。K1。

K1 is actually。I think its 3，1。We can verify this later， so I'll compare this。2 key1。Right。

 and I'm going to branch。 I'm gonna say branch， if。

I'm going to do the result is going to be stored in hour3。So I'll do B， EQ。B， EQ。

 and I'm going create a new label。Call P T 0。 I'm just giving this a name，00。Right。

 and then always escape this。B B X L。And at over here， p0， this label， I can do my blink。😔。

My blink would require a delay。😔，Okay， so we would have to write the delay subroutin。 Okay。

 let's just write this。 We'll write a subrout later。 So I'll do move S。Move S R0。And what I'm gonna。

Move。Its my。😔，B， my B SR R 5 set。I'm going to move this into the the BSRR register。

And then I'll do load。😔，R。Load r1。And then over here， I'm gonna。Get the address， GI U A。😔，PSR R。

 and then I'm going to store。20。At Ar like this。😔，Okay。So essentially。

 this is going to set the pin high。 P 5 is going to be turned on。 And in effect。

 our L is going be on。 And once that is done， we wantna delay。 So I do load。 I'm going create。

A constant for our delay。I'm going to say load R3 width。😔，One second。

 we're going to create a symbolic name to hold this one second。

 and then we're going to branch to delay。Okay， so once we've done this， then let's than it off。

 course we set it's a blank。 a blank is on enough。So I'm going to do move verse。20。And then。

 over here。😔，PSR R。It's PSRR 5。 It's still 5。Reset， because this is the symbolic name we gave to it。

 and this is the same as moving 1 to bit 21。Okay， and then we do load。😔，And an R1。Eals GPIOA。😔，BSRR。

And then we store。😔，20。I1。Once this is done。😔，Were going to。Delay for one second again。

So we load this into R3， and then we plunge to that delay sub routineoutine to execute。

Once this is done， then。We can read the next character。By doing。BL。You are。Read。Chaw like this。Okay。

😔，Okay。😔，Now， let's test it out。😔，I'm going to change the name of the subroutin to IO in it。

 not just U in it because we also initialize in the LED。So this I'll call IO in it。😔，Right， and this。

 the content of this loop， we no longer send in yes， so I'm going to take this off。😔，And。So we start。

 we initialize our I O， and then we read a character， so I'll change this to branch to read。Ch。

Read character after you've read a character， then we want to branch。One branch to our LED blink。😔。

S routine。And。😔，Once that is done， we branch to the loop。😔，Okay， so before we forget。

 let's create a war。Our delay suboutine， we said we created a symbolic name for。One second。One sec。😔。

One sec equals this constant， like I said， we're going to be using this pseudo of delay for a while until we go to times。

I'm gonna to see。😔，Okay， this is approximately one second and this is based on my microcontroller running a 60 meHtz and also the compiler I'm using。

 this is an empirically derived value。Yeah， we just use it until we get much more precise timers。

Okay， so let's create the delaylayup routine。Could you pause the video and try to create this delay sub routine because we created it once。

 even more than once， we've created it a number of times。Once you are done。

 you can unpost the video and watch me do it。Okay。So。Let's do it together。Simply delay。😔。

And how do we delay。😔，Whenever we branch to delay， we start a delay value in register R 3 OK。

 So we're going to subtract the content in R 3 by one。And we do that by using。你。😔，Ss instruction。

 subs RV3。Over3。N number one。So keep subtracting one from R3 and then start the result back into R3。

And then， branch。Branch to。Branch back to the top of disk。Label。

 branch back to this label if the Z flag is not a equal to 0。If the zero flag is not set。Then。

 brunch。Branch to delay， so this is how we get the M。The delay is basically spinning。

So we subtract one， we come back here， we subtract one from from this number。

 we keep subtracting until is0。And， in effect， would have our delay。Right。So what we have looks good。

Let's try it out and see if it works。I'll click here to build。😔，And we have an error somewhere。😔。

Says part Simbol。It's because I forgot the equal sign here。😔，Click to build。😔，Over here。😔。

It says part symbol。😔，Interest in。😔，We should half this， let's verify if this is spellt correctly。😔。

PS S，R， R 5。I wrote R here instead， O， let's click here to build， to build successfully。

 click here to download onto my po。😔，Okay， I'm going to open myterra term。😔，My zero program。😔。



![](img/a3c5a4a55179b467a549e1b0decf1998_3.png)

Over here， and I'm going to set the portrait rate to the new one by clicking set0 port。

 click the drop down。 This is the one we configured，1，1，5，2，0，0。😔。



![](img/a3c5a4a55179b467a549e1b0decf1998_5.png)

![](img/a3c5a4a55179b467a549e1b0decf1998_6.png)

Right， and I'm going to press one on my keyboard。And as you can see， the LED is on。

 I press one again。As can see， it is on。 If I press any otherda key。The LED stays。Stays off。Of Tuda。

 again。So we've configured it in a way that the kda is pressed is not echoed back over here。

 That is why you don't see one appear on the screen。 But when I press， as you can see。

 the LED is on on the microcontroller， I'll press again。I just can see it is on， so this is it。

This order is for this lesson if you have any questions at all。

 just let me know and I'll see you later， have a nice day。😔。



![](img/a3c5a4a55179b467a549e1b0decf1998_8.png)