# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P136：Chapter 9 8.Interfaces.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll talk about interfacing， how to connect different components together in a digital system。



![](img/03d04ed48955fdb48ac43a943ab7de9b_1.png)

So let's say we had our microcontroller and as we want to control the real world。

 we may need to connect to sensors。To monitor what's going on。

 to actuators to cause things to happen or to other processors。

So if we were running a chemical plant， we might have sensors measuring your temperature pH。

Humidity and these things going on in the plant， you might have actuators to turn on motors。

 to move things， turn on valves， to allow stuff to flow。

And then there might be other microcontrollers in the system operating different parts。

 and we want to send messages to them。So there are three general methods of interfacing devices。

 parallel， serial and analog。In the parallel interfacing。

 we send a bunch of wires to send an entire message many bits at once。

That can be expensive if you want to send a lot of wires。In serial interface。

 instead of sending a bunch of wires， we send one wire of data。

 and then we send use that wire many times。So for instance， the serial peripheral interface。

 we have a clock wire， one data outwire， and one data in wire。

And we can send a message from a master device to a slave。By using many clock cycles。

 say we want to send a byte， we'd use eight clock cycles on each cycle。

 we'd send one bit of data on the data out and get one bit back on the data in。

Universal asynchronous receiver and transmitter is similar， but it doesn't have a clock。

 instead it's asynchronous。 Both sides agree in advance on what rate they're going to send data。

 and they have to detect that data transition。Another common standard is the Inter integratedtegrated circuit or i squared C。

And this has one clock pin and one bidirectional pin。

 It's a little bit more complicated to use because of that bidirectional。

All three of these are widely used and will'll focus on SPI in this class。

Another way of communicating data is with the real world it's analog。

 so if we wanted to measure a voltage， we could use an analog to digital converter to turn that voltage into a set of bits proportional to the voltage。

Same way， a digital to analog converter， we could take a number and produce a voltage that's proportional to that number。

And with pulse width modulation， we could take a signal and alternate it between a low voltage and a high voltage at a high enough frequency that when you smooth it out。

 the average value of the waveform。Is proportional to the desired output。

So a little bit more on parallel interfacing。So if we wanted to send， say， eight bits。Of information。

 we would need eight wires。And we also need to either send a clock or some sort of hand shaking signal like a request and acknowledge to show when the data is ready。

These parallel buses are expensive and they're cumbersome because of the large number of wires。

 you get thick cables， they don't bend easily， and they're paying to use。

So this is mostly used for high performed short distant communication。 For instance。

 hooking dynamic ram chips to the processor on the motherboard of a computer。



![](img/03d04ed48955fdb48ac43a943ab7de9b_3.png)

Cerial interfaces send1 bit at a time， so to send a lot of information， you need many clock cycles。

And you also need to be sending the timing information about when the bits are valid。As we discussed。

 SPI， I squared C， and UART are three of the common interfaces。Another one that's more complex。

 but very powerful is USB。And that one can send data gigabits per second。

Because even though we're only sending one bit per cycle， we can run the clock at very high feet。

