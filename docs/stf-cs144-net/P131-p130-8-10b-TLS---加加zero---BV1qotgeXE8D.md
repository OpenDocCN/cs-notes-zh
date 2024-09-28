# P131：p130 8-10b TLS - 加加zero - BV1qotgeXE8D

 So TLS random values are 32 bytes long。

![](img/6d1de0022680b93f822a67de986f60cf_1.png)

![](img/6d1de0022680b93f822a67de986f60cf_2.png)

 There's a 4-byte timestamp and 28 bytes of randomness。 The pre-master secret is 48 bytes long。

 2 bytes of protocol version and 46 bytes of randomness。



![](img/6d1de0022680b93f822a67de986f60cf_4.png)

 Suppose your TLS session uses these to generate 1，024 bytes of keys。



![](img/6d1de0022680b93f822a67de986f60cf_6.png)

![](img/6d1de0022680b93f822a67de986f60cf_7.png)

 What is the maximum number of tries an adversary might have to make。



![](img/6d1de0022680b93f822a67de986f60cf_9.png)

 to crack the session keys is soon an exhaustive attack。

 Assume the adversary can correctly compute the output of a pseudo-random function from its input。

 So they can see the random function。 They can see the random values。

 They don't see the pre-master secret and they can compute the pseudo-random functions。

 Write your answers to the base two exponent。 For example， if it would take 2 to 31 tries。

 then write 31。

![](img/6d1de0022680b93f822a67de986f60cf_11.png)