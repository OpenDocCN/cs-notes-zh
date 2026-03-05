# 【从零开始学习 ARM 汇编语言II Udemy】 p27 p26 07.1. Overview of the ADC -BV1RJU6YwEM8_p27-

So， welcome back in this lesson， we shall give an overview of what an ADC or an analog to digital converter is。

Analog to Digital converters are among the most widely used devices for data acquisition。

Digital computers use binary or discrete values， but in the physical world everything is analog or continuous。

Temperature， pressure， humidity， velocity are just a few examples of physical quantities that we deal with every day。

 a physical quantity is converted to electrical signals using a device called transducer and a transducer simply convert a physical quantity to either voltage or current。

Transdors used to generate electrical output are referred to as sensors。Sensors for temperatures。

 velocity， pressure， light， and many other natural physical quantities produce an output that is voltage or sometimes current。

Therefore， we need an analog to digital converter to translate the analog signals to digital numbers so that the microcontroller can read and process these numbers。

Now let's talk about the concept of ADC resolution， an ADC has n bit resolution where n can be 8， 10。

 12， 16 or even 24， so you hear of people saying this ADC's 10 bit is 12 bit is 16 bit。

Higher resolution ADCs provide a smaller step size。

 where step size is the smallest change that can be detected by an ADC。

This table over here shows the number of steps as well as the step size。

 given the number of bits the ADC has， so for instance an8 bit ADC would have 256 steps and how do we know this we simply do2 to the power8。

And we get 256 and to compute the step size， we've got to take the reference voltage into account。

 so assuming the reference voltage is 5vol， we simply do5 divided by 256 and this gives us 19 and this gives us 19。

53 millivolt a 10 bit ADc。Has 1024 step size and the smallest change this 10 bit ADC can detect is 4。

88 millivolt in the same way a 12 bit ADC has 4096 number of steps and the smallest change this ADC can detect is a change in 1。

2 millivolt。A 16 bit ADC would have 65，536 steps and the smallest change this ADC will be able to detect will be 0。

076 millivvolt。V ref is an input voltage used for the reference voltage the voltage connected to this pin。

 most microcontrollers have the V ref pin and we can connect our own input voltage to or we can just say use the。

Same voltage as the one used by the MCU， so the voltage connected to the VR bin along with the resolution of the ADC chip。

Determine the step size as you can see over here， so assuming our VF is 5volts and the resolution of the ADC is 8 bit。

 then we end up with 19。53 millivolt step size。Right。

 so this order is for the short overview on ADCs。And we shall see how they work programmatically。

 I'll see you in the next lesson。

![](img/e042419147dddaf9eda331f237bf8b79_1.png)