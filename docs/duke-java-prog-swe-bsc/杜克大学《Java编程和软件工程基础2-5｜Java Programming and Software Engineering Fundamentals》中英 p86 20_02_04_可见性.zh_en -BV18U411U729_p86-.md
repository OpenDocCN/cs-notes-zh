# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p86 20_02_04_可见性.zh_en -BV18U411U729_p86-

Welcome back In this lesson， you are going to learn about the two visibility modifiers that you saw in the object oriented version of the Caesar cipher。

Public， which was used here。And private， which was used here。

 there are two other visibility modifiers， however。

 explaining them requires some more advanced concepts， so you will only learn about these now。

When you declare something， whether it is a class， field， method or constructor as public。

 it means that any code anywhere in your program can access that thing code from any class can call a public method。

 read or update a public field， use a public constructor when making an object。

 and make use of a public class。By contrast， when you declare something private。

 it tells Java that only code inside of this particular class can see the thing you declare private。

These two fields are declared private， so all the code inside of the Caesar cipher class can read and update them。

 but code outside of the Caesar cipher class is not allowed to access them at all。

 So what happens if you write code that tries to access private fields or methods from outside the class。

The Java compiler will give you an error like this， which says that you are not allowed to do that。

 In general， when you get this sort of error， it either means that you are improperly using a class。

 especially if it's a class that is part of an existing library。

Or that you have designed a class and made something private that should not be。

So why do you want to declare things as private， After all。

 it seems like it would just be easier to make everything public so you can just access whatever you want wherever you want。

Remember the idea of abstraction， the principle that you want to separate the interface from the implementation。

 restricting the visibility of the implementation details helps you enforce abstractions you design。

You can make the interface of a class all the methods that other classes are supposed to call public。

And then you can make the implementation details private。

No other class should know about the implementation details directly。

 and declaring them private lets you enforce that rule in your code。In our Caesar cipher example。

 you want other classes to be able to call encryptpt。

 but they should not know about the implementation details。

 such as the fact that you made a variable called Shi alphabet。

Keeping these details private means that you can change them and be sure that no other code relies on the private implementation details。

As you start to think about designing your own classes。

 there are a few general pieces of guidance to get you started on how to choose public or private。

First， fields are generally part of the implementation of an object。

 so they typically should be private。For methods， it depends on what the purpose of the method is。

 If the method is part of the interface you want your class to have。

 that is part of the behaviors you want it to provide to other pieces of code。

 you should declare that method public。On the other hand， some methods are helpers。

 You write them to abstract out specific complex tasks。

 which are not meant for other classes to call。They just help accomplish the public interface。

 These methods should be private so that only the code in your class can call them。For classes。

 you should always declare them public as you become more skilled in Java。

 you will learn some more advanced topics that lead to situations where you might want non public classes。

 but for now， always use public。

![](img/2a19bfe23a1400348bf9d86e575159e7_1.png)

Likewise， for constructors， you should always make these public for now。 Typically。

 constructors are part of the public interface of a class。 They specify how to make an instance。

There are situations where non public constructors are appropriate。But as with non public classes。

 these only come up when you have learned some more advanced topics。 So for now。

 you should just make constructors public。Great， so now you know what public and private mean。

 why they are useful， and some general guidelines for how to use them in your own classes。 Thank you。



![](img/2a19bfe23a1400348bf9d86e575159e7_3.png)