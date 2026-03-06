# 【从零开始学习 ARM 汇编语言II Udemy】 p07 p6 02.6. Coding  Developing the GPIO Input Driver (Part II) -BV1RJU6YwEM8_p7-

Hello， welcome back。So， yeah， let's continue where we left off。

So what we're going to do is we're going to write a simple assembly program that turns on the LED when a person presses their push button。

So we're going to write a subrout to get the input and then another one to turn on the LED and then a third one to turn off。

And then finally we add our delay function if we wanted to blink or something。

 we can add delay there。Okay。So I'm going to come over here。I'm going to write a up routine。

 I'll see。😔，彩 LED。On。And then what I'm going to do， essentially。😔，Is to。Move。Sorry about that。

 I prefer the cups。Move R1。Let's see how to accomplish this。😔，We can use the B S， B S R。

 R registers that we used earlier。 So I'm gonna start off by load。R 2 with the address of the PRR。

GPIU A。PS SRR。And then I'm going to do move。R1。PS SR， R 5。Reset， so this is gonna be off。

And then we're gonna store it， store。😔，ron R。Right。What I'm going to do， actually。

 I'm going to keep this in our loop。 this is something we're going to be doing often。

After the initialization， we're going to be running a loop。So I'm going to keep this somewhere here。

😔，And I'm going to have a loop here。😔，You can think of this as our War1 loop in sea languagegu W 1。

Loop。And then， branchnch。Prch to loop。O。So when we turn on the LED， we want a branch back to loop。

 So I'll say branch。When we turn it off， I should say to loop， okay， this。This is early off。

I have written。Now， let's have LED on。A little honest， the same thing。

Just that we have to change PRR。To set， rather than reset。Like this， and this becomes LED on。😔，Right。

 so let's create。The the get input。Get input。And we're going to load the input data register load。

Aan。GPI U I DR。And then we'll do load。😔，20。R1。And then to see what I do， the button is pressed。

We're going to compare the content of the input data register with our button pressed constant。

 and we're going to do an end operation here。 going to do end。

R0 store the result in R0 after you perform R0。And。B Tianpin。This is their button pine。Right。

When we do that， we're going to store the result in our0 and we can return。

 and we're going to take a look at the result and this would help us decide。

If we've pressed the button or not。So B X LR， okay。So now we can come to our loop and implement it。

So， we gonna start off。Lets start of by， this is our loop。

Our program is going to start by branching to GPI units to initialize the GPIU。

 and then it will branch here to the loop。And when we get here， what we wanna do is go get the input。

 So we， we branch to get input。And once we've got the input， we want to compare。

 So I'm going to do C， use the compare instruction。

CMP and what I want to compare is the content of r0 because。We go in and now get input。

We store the the result of the end operation in r0。 So I'm going compare the content of r02。

Our constant button on。Is the button on。And then we use the B EQ branch if equal2。If it is on。

 we turn on。Turn LED on。And then we're going to compare again。We're gonna compare this to。Button off。

 still the content of our0。If it is off。We branch to tunnelity off。Like this。Right。Okay。

 let's build and see what we have。So I'm gonna click here to build。We've got an error。

Part symbol says over here。I would you hear you in it， the label doesn't exist。Okay。And over here。

 we forgot。It says bad symbol GPIU A， we forgot the underscore here。😔，Right。

 I'll click here to build。Over here， we forgot the number sign。😔。

Click here to build to appear successfully， click here to download onto the board to download it。😔。

And I press the button， nothing is happening， so let's see。😔，My mistake。

 I was pressing the arm the reset pin， the reset button rather。 But this our push button。

 the blue one here。 as can see when I press， the lady is on， when I take my hand off。

 it goes off when I press， it comes on。 So this all there is for this lesson。

 If you have any questions at all。 Just let me know and ask you later。 Have a nice day。



![](img/f0ac1e5281a01d6fb8cdaa50bc732fbf_1.png)

![](img/f0ac1e5281a01d6fb8cdaa50bc732fbf_2.png)

![](img/f0ac1e5281a01d6fb8cdaa50bc732fbf_3.png)

![](img/f0ac1e5281a01d6fb8cdaa50bc732fbf_4.png)