# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P132：Chapter 9 4.General-Purpose I O (GPIO).zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/45e432103f3e069eb21ebbdec5d750ad_0.png)

In this lecture， we'll talk about general Purpo IO or GPIO。

So general purpose IO pins are pins that we can either write to of logic 0 or 1 or read the zero or1 from the pin。

So some examples of things controlled by GPIs could be LEDs that you turn on or off。

Switches where you read the value high or low or connections to other things like Digital logic。

 other chips。In general， as you are trying to get your head around GPIO for a new microcontroller。

 first thing to do is look at how many GPIO pins the microcontroller has and how they're named。

Each pin generally can be configured either as an input or an output or some other special function。

 say a serial port or a data converter。So you need to figure out how to do that configuration。

And then you redirect the pin。So on the FE310 board， there are。There's one GPIO port。

 GPIO0 that has 32 bits associated with it。However。

 our chip doesn't have enough pins to bring out all 32 GPIOs， so only 19 of them are accessible。

And on this picture， we see the mapping。 Here's pin 0， pin 1， pin 2。3。Pin 4。Pin 5 and so on。

Some of the GPIO pinINs have multiple functions， for example。

 pinN3 through5 are also associated with a serial peripheral interface。

 and we can either use them as regular GPIO or as SPI。

There's a blue LED on the board that's connected to GI05。 So when you drive that pin high。

 the LED turns on， when you drive it low， the LED turns off。

 And if the serial clock S clock is pulsing because you're doing serial transmission。

 youll also see the light pulse。So the numbering on these pins is very small and unless you have very good eyes or a magnifying glass。

 you may not be able to actually read it very well from the silk screen of the board。

 So this page is a pretty handy one to refer back to that shows which pins are which they're also labeled on the back of the board。

 but that doesn't help you very much if you've plugged the board into your breadboard。

The GPIOs are controlled by memory map I， and you may recall that the base address for the GPIOs was address 10012000。

There are a bunch of registers starting at that address。 Each register is 32 B wide。

And has 32 individual bit fields to control the 32 different GPIOs。So 32 bits is 4 bytes。

 so each register is four bytes past the previous one。And the first four registers are input value。

 input enable， output enable， and output value。Then there are some registers related to controlling an internal pull up。

 setting the drives strength of the pin， a whole bunch involving interrupts。

And two of them for IO special function registers to enable or select special function register that we'll talk about later。

So on reset， three of these registers are all initialized to zero to disable all the pin GPIO pins so they don't act as input output or have an internal pull up。

 and that way that chip won't do anything funny after reset。

So let's say we wanted to write some code in the previous example。

 we didn't talk about the enables yet。 so now let's introduce the red lines of code。

To provide the enables。So。The input value register。Was that 1001。2，0，0，0 plus an offset of 0。

That's this。The input enable register is an offset of four。

So that's the same base address plus the offset of four。

The output enable at an offset of eight and the output value。Offet of sea。

So we've got pointers to all the registers。Let's write a one to bit 19 of the input and AL register to make input 19 GPO 19 be an input。

 and we'll make GPIO5 be an output。Then just like we've done before。

 we could read and write the bits。We could read the value。GPI 19。

By looking at all 32 values in the input value register。

 shift right by 19 and then and with a one to get just bit 19。

do the same thing to look at the value and then wait for that value to be1。 So while it's not one。

 we will wait， and then it becomes one。If we want to write a one to GPI Ob bit 5。

We or that bit with a one in column five。Here to make that would also turn on the blue LED。

If we end with a one in every column except five， then we turn off the LED。

You need to be a little bit careful if you're using the red5 redboard instead of the thing plus because the numbering on the board is different than the numbering of the GPIOS。

 it's Arrduino style， but it's pretty confusing if you're writing programs with respect to the GPIO numbers。

So the pin named0 is actually GPI0 16， the pin named1， is GPI0 17 and so on。



![](img/45e432103f3e069eb21ebbdec5d750ad_2.png)

Pin named 8 is GPI0 0。Let's take a look at an example。

So suppose we had a switch and an LED and we wanted to write a program that would read the value on the switch and hooked up to GPO 19 and write that value to the LED on GPI05。

This is a little bit silly because we could have done the whole thing with a wire instead of a $30 microcontroller board。

 but what the heck。So we again declare our pointers to the four registers。We。

Need to enable the registers。 So we。Make。Pin 19， and input。Pin 5， and output。And then。

 we can have a loop。Where we read the value on pin 19 using our idiom to read a pin value。

And if that value is true。Then we turn on pin 5， otherwise we turn off pin 5 and we repeat indefinitely。

So most GPO pins are also associated with other special functions， for instance。

 our microcontroller has serial ports， several types， and pulse width modulation signals。So。

For example， GPIO。Pin2 can also be used as a chip select for a serial peripheral interface。

Pin or has a pulse width modulation output。Pin  three。

Is a data signal for the serial print from interface face or another pulse width。

Pin 5 is a clock for the serial peripheral interface， no other options。

So if we want to use a pin as a special function。We use the IO function enable。Set that to one。

To use special functions instead of GI。And then we use the I O F select to。

Pick which function we want。So for example， if we wanted to make pin 13。Be a pulse width modulation。

We would write bit 13 of the iss。F enable。To be one。To enable special functions。

And we'd set IOF select to be0。 if we wanted to use it for I squared C。

 we'd make it one if we wanted to use it for a pulseulive modulation。

