# 【从零开始学习 ARM 汇编语言II Udemy】 p36 p35 08.5. Coding   Assigning Symbolic Names to Relevant GPIO Input Registers -BV1RJU6YwEM8_p36-

Hello， welcome back。 In this lesson， we are going to see how to configure our GPI U as an output pin。

I'm going to make a copy of the last project。And then we continue from there。

Call this GPIU output input。 Sorry， we're going to see how to configure our GPU pin as an input。

Right， we've already done output。Okay， that will click you open。



![](img/c28d30c1e61824c90df3ee42e4b900ca_1.png)

To right。To configure as an input， it's really simple。

 All we have to do is go to the direction register and set it as an input。

And then we have it as an input。 But for our experiment。

 were going to use the switches provided on the board。

 We have switch 1 and switch 2 at P F 4 and P F 0 respectively。

We need to enable the pull up register for these switches。

 so we need to enable the internal pull up resistor。

 We need to enable the internal pull up resistor that are connected to these two switches and to enable them。

 we can use the pull up register to enable the internal pull up registeror。So we have to get。

 we have to create the。The address for that。So I'm going to come over here and create a new address I've already gone ahead to get the。

To get the offset of the pull up。Pull up pull up register。So I'm gonna create it。 I'll say G P I O F。

P， UR for pull up register。Offset。The offsets is。0 x，5，1，0， and you can go and search。

P UR in your data sheet， and you find this offset there。So to create the the resistor。

 we simply do GI U F。P U R， and let's go R over here。And we know we compute this by。GPIu F base。Plus。

GPIU。P UR offset。That is point number one。1， right， there's another thing we have to deal with。

So I will switch P F0 here， which is switch number two。It is locked by default。

And this means that we have to unlock。 We have to unlock this pin。

 The reason this spin is locked is because it is。The P F0 is connected to what is known as the NMI。

 the nonm pro interrupt。 and because the designers of the Texas instrument。

 microcontroller don't want us to alter the state of the the the pin by mistake。

 they've locked it such that if we want to use it we've got to unlock it with a particular unlock key。

And then we can use it。 So we've got to unlock this。And to do this。

 we need to access what is known as the lock register。

 and then we write a particular on lock to this。 And once we've unlocked this。

 we've got to commit our new setting through the commit commit register。 and mind you。

 we only doing this because we are using P F0。 if we connect our own switch to the arm。

To the microcontroller board， we don't。 we don't need to unlock any pin if it's not locked。

 Just P F0 has this issue。 Or for now in our experiment， it just has to do a P F 0。

 If I'm to connect a pin to P F 5。 I wouldn't need to unlock it， I'll be good to go。

 But because we're using P F 0 and internally is connected to the enemy， we need to unlock it。

 So I'll create the register for lock in and unlock in over here。GPIUF。The register is GPU F。

 I'll call it LCCK for lock。Offset the offset here。Its 0 x 5，2，0。And then， we can create。

To register itself G value F。L C K underscore this call R。AQU。We take the GPU F base。And then。

We add this， the offset。Right， so there's one that I register。Once we unlock the key。

 we've got to commit the changes and we commit using the commit register known as C R for short。

 and we can create that as well of say GP U F。Xier。Offset。EQU。This is your X。5，2，4。And then GPpiIu F。

See R underscoreco R。EQU。GPU F based address。Plus， the CR offset。Right， so this is it。 So the key。

 the lock key， the key to。To unlock our portf， I'm going to create a symbolic name to hold this extraod Smal value。

And that this can be found in the data sheet as well。Coest lock。Ki。This is this value here。Right。So。

I think we are set。Let's create some symbolic names to correspond to the bits of our switch1 and switch。

Switch2， I'm gonna come over here。Come down here。And say S W1 for switch1。Shich one we know is that。

Pin for。And then， switch to。We know this is to pin 0。Right。We can create more symbolic names。

Remember。Our switch is an active low switch， meaning by default， the switch is high。

 When we press the switch， it goes low。 meaningan， if we detect that。

 if we read the switch and its state shows that it is low， it means someone is pressing it。Hence。

 it is called an active active low switch。Right。So I'm going put a block of comment here。

I'll call this output。😔，um。SO P1。Pressed。Wait。Let's see， how do I write this？😔，Okay。

 so the output is gonna come out in the arm and register I Europe。If is 0 x，01。This will mean。

Switch one。Sitch one is pressed。Sorry about that。Okay。Fr0， which has the output is 0 x。1，0。

This will mean。Switch to。Ipressed。If ourro， which is going to be our output register， has。Through x0。

0。This will mean both switches。Opressed。If R0 has 0 x。1，1， this you mean。😔，No switch。Is pressed。

 Remember， we said its active low。Right。算了。This is a comment。

 so I'm going to highlight this and comment this for your explanation。Okay。

I'm going to create symbolic names to hold these states。So come over here。

 I'll see S W1 underscore the。Pressed。And there's EQU。Is0 x，0 1。And then SW to underscore pressed。

This E Q U。0 x，1，0。This。😔，Both。😔，Pressed。eQU。😔，S x00。This。😔，No press。😔，AQ you。Sure x。1，1。Right。

 so now we have all the registers and symbolic names we need。Yeah。

So how about we continue in the next lesson， let's implement our code in the next lesson。

 I'll see you there。

![](img/c28d30c1e61824c90df3ee42e4b900ca_3.png)