# 【从零开始学习 ARM 汇编语言II Udemy】 p12 p11 04.1. Overview of the UART Protocol -BV1RJU6YwEM8_p12-

Hello， welcome back in this lesson we shall give a brief overview of the universal asynchronous receiver transmitter。

 otherwise known as the UU Comps transfer data in two ways parallel and serial in parallel data transfers often eight or more lines or wires are used to transfer data to another device in serial communication the data is sent one bit at a time。

In the past， parallel data transfer was preferred for short distances because it may transfer multiple bits at the same time and provide higher throughput。

 as technology advances， the data rate of serial communication sometimes exceed parallel communication while parallel communication still retains the disadvantages of the size and cost of cable and connector。

The crosstalk between the data lines and the difficulty of synchronizing the arrival time of data lines at longer distances also still existed in the parallel communication。

UA is one of the most common serial communication protocols。

 and in this lesson we shall explore some of the basics of the UA protocol。

The data coming in at the receiving end of the data line in a serial data transfer is all zeros and ones。

It is difficult to make sense of the data unless the sender and receiver agree on a set of rules or a protocol on how the data is packed。

 how many bits constitute a character， and when the data begins and ends。

Asynchronous zero data communication like the UA is widely used for character oriented transmissions in the asynchronous method。

 each character such as ASI characters。Is packed between stat and stop bit This is called framing the start bit is always one bit。

 but the stop bit can be one or two bit。 the start bit is always0 and the stop bit is indicated by one For example。

 over here we send in the ASI character a which has the binary number 100001 we shall talk about this other0 later。

 but there's a reason we have another0 added here。As we can see， the data is framed between。

The start pits and two stop pits， the stop pits， as we said。

A indicated by one and the start bit is always indicated by0 and the stop bit can be2 in number but the start bit is always one。

 you can have either one bit for stop or two bit for stop in this example we've got two bit for stop。

The right most bits are the LSB。Asent first， the LSB stands for the least significant bit。

In asynchronous serial communications， peripheral chips can be programmed for data that is5，6。

7 or8 bit wide， while in older systems ASI characters wear  seven bit。

 the modern systems usually send non ASCI8 bit data as well。

Now let's talk about parity in some systems， in order to maintain data integrity。

 the pary bit of the character byte is included in the data frame。This means that for each character。

 we have a single parity bit in addition to the start and stop bit。The pary bit may be odd or even。

In the case of an odd parity， the number of data bit， including the parity bit。

 has an odd number of ones。Similarly， in aneven parity， the total number of bits。

 including the parity bit is even。For example， the ASI character a has the binary number 100，001。

 and we've got0 included to the beginning here。Of course， heroro added here for even parity。

UA chips allows programming of the parity bit for odd even and in fact we can choose not to have parity at all when programming the chips。

And we shall see how to do this programmatically Now we look at data transfer。

The rate of data transfer in serial data communication is stated in Bps or bits per second。

 Another widely used terminology for Bps is the bo rate。 However。

 the B rate and Bps rate are not necessarily equal。

 This is due to the factor that B rate is defined as the number of signal changes per second。

In modems， it is possible for each signal to transfer multiple bits of data。

But when we are talking about wired connections like the UR， the boat rate and BPS are the same。

So this order is for this short overview on UART and the UA data transfer protocol。

 if you have any questions just let me know。I'll see you later。

