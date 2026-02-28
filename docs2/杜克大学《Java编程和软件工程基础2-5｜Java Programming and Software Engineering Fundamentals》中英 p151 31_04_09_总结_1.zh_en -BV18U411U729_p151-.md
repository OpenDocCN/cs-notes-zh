# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p151 31_04_09_总结_1.zh_en -BV18U411U729_p151-

![](img/e434f13aca6d2c7b16353b774c6ca6c1_0.png)

We've just gone through several related programs and classes to learn some new Java concepts in the context of the useful idea of predictive and random text。



![](img/e434f13aca6d2c7b16353b774c6ca6c1_2.png)

![](img/e434f13aca6d2c7b16353b774c6ca6c1_3.png)

By developing a sequence of related classes and programs。

 we could introduce new Java and design ideas in the context of familiar programs。



![](img/e434f13aca6d2c7b16353b774c6ca6c1_5.png)

![](img/e434f13aca6d2c7b16353b774c6ca6c1_6.png)

In our example， we used Markov T generation， but these ideas help form the basis for machine learning algorithms such as those used for spam detection and for predictive and autocomple functionality in search engines and mobile smartphones。



![](img/e434f13aca6d2c7b16353b774c6ca6c1_8.png)

We studied related classes that led to designing interfaces and abstract base classes to overcome problems of copying and pasting code across several classes。

The familiar context helped facilitate the exploration of these new Java and object oriented concepts。

 We looked in more depth at Java interfaces in looking at the comparable interface for sorting。



![](img/e434f13aca6d2c7b16353b774c6ca6c1_10.png)

First， we use the same names for methods across many classes。

This allowed us to reuse client or testing code with new classes。

The testing code compiled with different classes because the methodth namess were the same。

We first developed Markov Zero， but the design of Markov 2 and Markov 1 was facilitated by reusing ideas and methodth namess from the already tested Markov Zero class。



![](img/e434f13aca6d2c7b16353b774c6ca6c1_12.png)

![](img/e434f13aca6d2c7b16353b774c6ca6c1_13.png)

![](img/e434f13aca6d2c7b16353b774c6ca6c1_14.png)

We extended the idea of common method names in creating an interface we named I Markov model。

Interfaces are a powerful concept in Java and other object oriented languages。

 Interfaces are used extensively in the Java dot U， Java dot I O and other packages and libraries。

We extended these ideas to creating an abstract base class for Markov。

This allowed us to capture common code， not just method names。

 as we captured by creating an interface。