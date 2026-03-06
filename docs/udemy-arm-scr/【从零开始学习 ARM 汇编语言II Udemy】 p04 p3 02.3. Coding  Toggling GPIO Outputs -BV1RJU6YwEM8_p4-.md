# 【从零开始学习 ARM 汇编语言II Udemy】 p04 p3 02.3. Coding  Toggling GPIO Outputs -BV1RJU6YwEM8_p4-

Hello， welcome back。 So let's make our LED blink。I'm going to create a copy of the last project we created。

And I'm going to add the word blinking。😔，Ill say blinky， I'll call this number two。😔。

And I'm going to open this。😔，And I'm gonna to minimize this。



![](img/f352f29e1cab8b49f551642e82bc8d62_1.png)

Right， so we're going to create a delay function， if you may。



![](img/f352f29e1cab8b49f551642e82bc8d62_3.png)

Yeah， and this is。This is going to be a pseudo delay， right。

 We shall see how to create precise delays later。Okay。So I'm gonna create a constant here。

 And this constant is based on the， the clock frequency of my microcontroller， which is。

Around 16 MHz， which is 16 MHz。 It's around。 It's not perfectly 16， but it is considered 16。

 And this constant is also based on things like my compiler， et cetera。So without talking much。

 I'm just going to see one second。Equals this。I'll say EQ you。EQU， and then this is one second okay。

And half a second is gonna be somewhere around。This。

And these are constants we shall be using for this type of delay later on。

 we shall talk about time is and have precise delays。所。😔，I'm going to create a new subroutine here。

Over here， our code ended and we aligned so we can create our new subbri in here。

I'm going start off by calling this one。 This first one。 I'll create two of them。

 This first one is going to be called delay。 This is what would help us delay。 So I'm gonna use S U。

 S U subs S U B， S and S， U B， S， whenever you see， Well， we've spoken about this in the。

Basic assembly language course。 but I'll point this out again。

So we have instructions such as Ser art， et cetera。

 Whenever you see these arithmetic operations with S appended。

This means that when the operation is performed， we want to update the APSR flags。

 We want to update flags。 and by updating this flags， we can run some conditional code。

 We can check if the C flag is 0 or not， if another flag is something else。 So basically。

 when I say S U B S。 I want to update the flag。 This will help me。

Run the next instruction that I would write after this。 So we're going to pass a constant into R 3。

 We're going to pass an argument into R 3。And to perform our delay。We're gonna say， our three。

Equals r 3-1。 This is what this line means。 subs means performance subtraction pro 1 or pro 2 store the results in op pro 3。

Right， so we just subtract。 So what it iss gonna happiness。

 we're gonna take one of our constants here。 We're gonna take one second。 pass it into R 3。

 and we keep subtracting。 We keep looping until， you know， there's no more subtraction to be done。

 And how do we find out that there is no more subtraction to be done。 We can use P and E。

This means branch， if the Z flag is not equal to 0， That is why I had to add S here。

 because we want to update the Z flag。So branch， if the sea flag is not equal to0。

 what do we want a branch to， We want a branch to the label delay。Right， so it will brings。

 bring us back here。 This is essentially a loop， and the loop terminate when the Z flag 0 and the Z flag becomes 0 when we perform the when the result of。

呃Yeah， the the。Yeah。The loop terminate when the Z flag becomes 0 and the z flag become and the z flag becomes 0 after we've subtracted everything out of this huge number。

 right， So we keep doing this number -1，-1-1 until， you know， the z flag is 0。

 which at which time the number will be 0 itself， okay。So， we can。We can。Return Bx Lr。

Of prefer a cops。Okay， so this is our delay。And then I'm going to， so this part here。

 we have this code for tanin on the LED。 I'm going to comment this out。

 We're going to create a different subrout for blink and the LED。And I'll come over here。😔。

And what I'm gonna do here。This is still the GPU in it。Inside the GPIU unit it， I'm going to。

I'm gonna clear register R1。Simplic say， move。R1， the number0。In case。 then I'm going to see ODR。

In fact， we don't need to clear our。 Sorry bother。I was trying to do something， Be creative。

 and the life codingt。That's always a problem。 Okay。

 so we're going to load R 2 with the address of our output data register。

 We're gonna put this into R 2。 So I'll do this。So by the time we come out of the subroutine。

 our two would have。Our GP U A output data register。Okay。

You can clean this because you have a copy of it from the other project。Okay。

 so we'll come out of this， which are to having the address of our output data register。

 And going to create another sub brought in here known as blank。And now she。Blanlink like this。

And okay， we start off by moving our。Our LED into register r1。I'll come over here， see R1。Co， move。

Sorry， everyone equals LED on。 Remember， LED on is a constant we had。Over here。Right。

And once that is done， we can store this。 We can store LED on into our2 cause our2 has the address of our output data register。

 So I'll simply say store。What is in our1， This is the source。

And as the destination address are to here like this。 Okay， once we've stored this。

 meaning the LED is gonna turn on。And once the L is on， we want to delay for a while to delay。

 I'm going to say load register R 3。With。Our constant， how about we say half a second each sec。

 We're going to load register R 3 with half a second。Remember。

 register R 3 is the register used in our delays are brought in here， right？ R 3 has the data we do。

R 3 contents -1， and we keep doing that onto the Z flag tells us， O， now the subtraction result is 0。

Okay， so once we've loaded our3 with half a second。We branch。To our delays sub routine。Right。

So this essentially is going to turn on the LED。And then wait for half a second。

 and that's not precisely half a second。 But we are assuming this is half a second。

 This is an approximation of half a second。Right， well see how we works。 So once we do this。

 we wait for half a second。 We want a 10 of the LED。 I'm going to create a constant known as LED off。

And LED of， essentially， would be to arm。乐一。So to turn the LED off the same way we shifted one to position 5。

 which is bit number 5。 We're gonna shift 0 to bit number 5 to turn the LED off。So come down here。

Now say LED underscore of。And this also say EQU。0 shift to position 5。Right。

 so now we have a symbolic name for LED off。 So we said， turn on the LED。 Wait for half a second。

 Once that is done， we wanna turn it off。 So do move。R1。And I wanna move LED off。And。😔。

I want to store this into our2。 our2 still has。GPI U A output data register。

So want to store this here。R1。A two。And then I wanna wait once I'm done this。 I。

m once I'm done with this， I would like to wait for half a second again。 So I'm going pass R 3。

With half a second。 And then I'm going to。Brunch to the delay for this to be processed。Right。

 so turn on， wait half a second，10 off， wait half a second， and we can loop。We can go back to blink。

To create a loop， we simply say be。Branch， branch to the label blank。 So it will go back up here。

 So that's how come we get a blank effect。 It doesn't just go on and off。

 It doesn't go on and off just once。 It goes on and off， on and off， on and off， on and off。

 like that。In a sense， we have a loop。And we can try this out。

 We can just remove our return statement from here so that when we run。

 the initialization is' going to run up to this part。Whenever you put B X LR。

 you mean return from the subroutine。 I've taken it out。 So in a sense， this bit。

All up to the parts that we have our BX LR， this entire bit。

It's going to be executed when we call our GPO in it。Right。

I'm going take out this loop thin that we had over here or keep it simple like this。Okay。

 let's go and see what we have。I've click to build。We have zero arrow。

 click here to download onto my board， it says。😔，No S link connected， Let's see。😔，It's downloading。

It's finished downloading onto my board。And as can see， the green LED is blinking。

 is blinking rapidly。 Like I said， our delay here is an approximation。 We shall see how to。

How to code。More precise delays using our timer， our hardware timers。 How I will try with one second。

 I'm going to copy this。And。I'm going to put it over here。Wait。

 let me take a video of this of the microcontroller to include to the。

 to the video before I change it to one。Okay， let's change it to one second。

 so I'll just paste one sec over here and one sec。Click here to build。

Click here to download onto the board。Right。It looks precise。 It looks a bit precise。

 So that's what one second looks like。On off， on off。What。

So those are for this lesson in the next lesson， we shall see how to configure the GPIU of our STM 32 board using the P using the DSRR registers。

 so it's a single register I should say the BSRR register， we shall see how to use that register。

To control the the GPIU output。 So I'll see you in the next lesson。 If you have any questions。

 just let me know and I'll see you later。 Have a nice day。



![](img/f352f29e1cab8b49f551642e82bc8d62_5.png)