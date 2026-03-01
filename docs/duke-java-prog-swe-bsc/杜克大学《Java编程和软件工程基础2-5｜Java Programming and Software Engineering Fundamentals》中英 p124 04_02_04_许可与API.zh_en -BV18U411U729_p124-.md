# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p124 04_02_04_许可与API.zh_en -BV18U411U729_p124-

![](img/438f81961910ca85999ba8882523fe39_0.png)

Hello， in this lesson， we'll discuss how we are able to use the well tested Android location class in our programs。



![](img/438f81961910ca85999ba8882523fe39_2.png)

The location distance 2 method has a comment that indicates what the method does。

Reading documentation is an important part of creating programs。

This method returns the distance in meters between two locations。

 we remember that the distance is in meters when writing code later。

You can also see that the method uses the WGS84 ellipsoid standard。

Adhering to standards is a good idea。 It helps to ensure our code is robust。

 accepted in a large community and as verifiable as being correct。

The world geodetic system established from 1984， is used here。

 We should be glad that we can rely on this standard。

 rather than trying to determine the distance between two points on a three dimensional sphere like ellipoid that is the planet Earth。

😊，Let's work to understand the location class API。

![](img/438f81961910ca85999ba8882523fe39_4.png)

The location class we are using comes from the Android system。

 Android powers more smartphone and devices than any other operating system。



![](img/438f81961910ca85999ba8882523fe39_6.png)

You can read the documentation and understand the location API on the web， like many modern APIs。

This API is really useful in developing the many location aware applications that run under Android。

To use the location class， you'll need to do several things。

You'll want to read the documentation to see how to use the class and what the API says about using the class。

You'll need to create location objects using the ideas you read about in the API。

You'll also call methods like distance 2 by adhering to what the API documentation says and by testing your code using the concepts from the API。

The Android location class is licensed for reuse。 The location class uses an Apache 2。

0 open source software license。 You can read the details of what this license allows online。

 The documentation that comes with location Java from the Android system indicates which license is used。



![](img/438f81961910ca85999ba8882523fe39_8.png)

The Apache 2。0 license specifically allows for reuse of the code in the location class and for the code to be changed。

 This is great since we've taken the code and made some modifications to it。

 Our adaptations remove the location class's dependencies。

 So it is usable outside of the Android system。 We still benefit from the robust testing and development of the class。

 So we're confident it will work。😊，We have also adopted the same Apache license as you can see here。

Because we've chosen the Apache 2。0 license， you can adapt the code and make changes to。

It works as given in our examples， so you can simply use it without making changes if you want。

This kind of shared community programming is a powerful tool in creating software。

