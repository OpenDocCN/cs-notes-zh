# P124：p123 8-6f Confidentiality - 加加zero - BV1qotgeXE8D

 So the answer is A， 0x EBEB0027。

![](img/156e69bccb8eb726be377fd99e60eb02_1.png)

 Look at the path that L0 takes through the network。



![](img/156e69bccb8eb726be377fd99e60eb02_3.png)

 R2 is equal to L0 XORD with P1。

![](img/156e69bccb8eb726be377fd99e60eb02_5.png)

![](img/156e69bccb8eb726be377fd99e60eb02_6.png)

 Since we know L0， the first plaintext is all zeros。



![](img/156e69bccb8eb726be377fd99e60eb02_8.png)

 This means that P1 is equal to R2， or 0x7B77 DCA2。 Since we know P1。

 we can then compute L0 of the second plaintext by XORing。



![](img/156e69bccb8eb726be377fd99e60eb02_10.png)

![](img/156e69bccb8eb726be377fd99e60eb02_11.png)

 It's R2 with the second with the key。

![](img/156e69bccb8eb726be377fd99e60eb02_13.png)

 If you XOR 0x7B77 DCA2 with 0x0 DC/DC85， you obtain 0x EBEA0027。



![](img/156e69bccb8eb726be377fd99e60eb02_15.png)

![](img/156e69bccb8eb726be377fd99e60eb02_16.png)

 If you didn't want to do the full XORD， you could just look at the bottom byte。



![](img/156e69bccb8eb726be377fd99e60eb02_18.png)

 A2 XORD with 85 is 27。 R2 XORD because 2 XORD with 5 is 7 and A XORD with 8 is 2。



![](img/156e69bccb8eb726be377fd99e60eb02_20.png)

![](img/156e69bccb8eb726be377fd99e60eb02_21.png)

 [audience members talking to each other]。