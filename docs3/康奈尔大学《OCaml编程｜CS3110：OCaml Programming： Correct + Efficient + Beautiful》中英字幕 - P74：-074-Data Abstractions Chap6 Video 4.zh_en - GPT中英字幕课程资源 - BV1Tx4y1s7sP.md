# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P74：-074-Data Abstractions Chap6 Video 4.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

There's more to programming than specifying just functions。Data abstractions are also。

Here by data abstraction， I mean a specification of operations on a set of values。

This is similar to what we would have called an abstract data type in 21。For example。

 we've looked at stacks in the previous。We know that stacks have push and pump and peak operations。

We know what the specification of those operations should be We don't know though what the values of a stack concretely are if we hide them behind an abstract type in a signature。

So in OCMl， a data abstraction naturally corresponds to signatures that have abstract types。

A data structure is an implementation of a data abstraction using a particular representation。

For example， we implemented list stack。And we did that with Alpha list as the type representing stacks。

And then we could use other operations with lists to implement these stack operations themselves。

So in OCML， a dot ML file or a structure naturally corresponds to a data structure。

Let's try building a data abstraction and structure for sets。



![](img/59e3cbd4ac8e276d225175933a3bb2a4_1.png)

I've now written a specification for a data abstraction called set。

A set is a set of values in the sense of CS 2800。I have a representation type for values of that set。



![](img/59e3cbd4ac8e276d225175933a3bb2a4_3.png)

Alpha t。So set dot T is the type constructor for sets。

 and that's parameterized on a type variable alpha。

That type variable alpha is the type of the element in the set， so I could have sets of integers。

 I could have sets of pools， sets of strings。

![](img/59e3cbd4ac8e276d225175933a3bb2a4_5.png)

MmpD represents the empty set。I have three operations for size， add and mem。

I've written specifications for each one of those。

![](img/59e3cbd4ac8e276d225175933a3bb2a4_7.png)

Size is the number of elements in S， and I've clarified as part of that specification。

 just in case anyone had a question that the size of the empty set is zero。

Add is a set containing all the elements of S， as well as element X。And Mem X S is true， if and only。

 if X is an element of S。 I chose the name Mem to be consistent with some of the OcaMel standard library data abstractions。

 which use a similar name。You can see from the type of ad that this is a functional data structure。

It takes in an old value of a set and returns a new value。 It does not destructively update the set。



![](img/59e3cbd4ac8e276d225175933a3bb2a4_9.png)

![](img/59e3cbd4ac8e276d225175933a3bb2a4_10.png)