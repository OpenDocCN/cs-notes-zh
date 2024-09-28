# P132：p131 8-10c TLS - 加加zero - BV1qotgeXE8D

 It will take it most to two to the 368 attempts。

![](img/c523bbed62b48531258f3702d33f52a4_1.png)

![](img/c523bbed62b48531258f3702d33f52a4_2.png)

 The two random values are known by an adversary because they're sent in clear text。

 The one true secret is the pre-master secret， which is 46 bits long。



![](img/c523bbed62b48531258f3702d33f52a4_4.png)

 If the adversary can guess this value， then it can recompute the master secret using the。



![](img/c523bbed62b48531258f3702d33f52a4_6.png)

 pseudorandom function。

![](img/c523bbed62b48531258f3702d33f52a4_8.png)

 With the master secret， it can recompute the keys。 2 to 368 is enormous。



![](img/c523bbed62b48531258f3702d33f52a4_10.png)

 [BLANK_AUDIO]。