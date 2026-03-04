# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P31：31_08_02_概述_1.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/5648f787a6d708f6e06d1602b74efe6a_0.png)

Now that you're familiar with the basic elements of programming from Java's numeric data types to conditionals and loops。

 functions， recursion， IO libraries， and the like， and even performance。

 we're ready to move to another level of programming。

 where you're able to define and use your own data types。

 and that's what we're going to start on today。Let's start with a brief overview。First。

 a basic definition。 we talked about this before。 a data type is a set of values and a set of operations on those values。

 and we looked at a number of Javas built in data types。

 and that's what we've been using as the basis for composing our programs up to this point。

In the primitive types in Java language like int and double and so forth。

 the values immediately map to machine representations and the operations immediately map to machine instructions。

 so programs that use these are very efficient， that's part of the design of Java。

But we want to write programs that process other types of data that aren't built into the machine。

We're going to talk today about programs that manipulate things like colors and pictures and strings。

 And later we'll talk about complex numbers and vectors and matrices。

 All kinds of data that we're familiar with， but are not going to be built into the computer。

And to do that， what we use is what's called an abstract data type。

 It's a data type that's a set of values and set of operations on those values that are well defined。

 but the representation is hidden from the client。 and that's a very important point that we're going to come back to often。

It leads to a style of programming known as object oriented programming。

And what we're going to do in object oriented programming is create your own data types and then use them in your programs。

Manipulate objects that hold data type values， and we'll talk about the details of defining these terms in a minute。

So an object is something that holds a data type value and when we have variables in our programs。

 they're going to refer to objects。So examples of this that we're going to talk about very soon。

 first one is color。A set of values turns out to be three，8 bit integers。

 and then we have various operations like get one of the components are brightened or darkened。

Then we'll look at pictures， which are 2D arrays of colors。

 and there we want to get or set the value of a pixel in the picture。

We have been using strings and we'll talk about them in more detail。

 whereas we know a string is a sequence of characters and there's lots of operations that we can perform on strings and many interesting。

 important programs around strings。Now， in all of these kinds of data types。

 our best practice is to use an abstract data type where the representation is hidden。

And the big impact of that is that clients can use ADTs。

 abstract data types without knowing the details of the implementation。

 All they need to know is how to use the operations。

In this lecture we're going to talk about how to write client programs for several useful ADTs and in particular we won't talk about the implementation。

 so we'll write programs that make use of these useful ADTs without knowing the details of the representation。

And in the next lecture， we'll talk about how to implement your own abstract data types。

Just as an example， we'll take a quick look at strings because string is an abstract data type that we've already been using。

We have some idea of how they're represented within the machine。

 but our programs don't really depend on any particular representation。

So we define a string to be just a sequence of Uniicode characters。

And Java Str  AD0T allows us to write programs that manipulate strings。

 but the exact representation is hidden。 The Java could change it， and our program would still work。

And we've used a number of operations on strings， you can find the length。

 you can take a substr and we'll talk about these in much more details later in this lecture。

So the basic idea， and we have been doing this already， but in the context of abstract data types。

 I want to look at the major features of things features that you need to know in order to use it。

So what you need is you need to know the name of the data type。

 And that's a capitalized name in Java like string with a capital S。

You need to know how to construct new objects and associate variables to those objects and you need to know how to apply operations to a given object。

 Those are the three things that are critical in writing client programs that use abstract data types and again。

 we've already been doing this for string， here's a little example of string code kind of like hello world but with a little few string operations。

So to construct a new object， we use the keyword new。That's the purpose of that key word。

 Invoke a constructor that makes a new object。 constructor is a special method that makes a new object。

And then we use the data type name to specify object which type of object it is。

 which constructor that we're going to call。Now， once we've constructed a new object and associated it with a variable with an assignment statement。

 then we can imply an operation on that object or in orpedlingo。

 we say invoke a method on that object。So what we do is we use the object name that says which object。

Then we use the dot operator to indicate that we're going to apply an operation to that object。

 and then we use a method name， which is just like a regular function call or method static method call in Java but it's associated with that object says take a substr from this string hello world that's the way that we use data types constructors and methods。

 Now we're going to see many， many more examples of this。

 I just wanted to point out that we've already been doing the basic operations on abstract data types。

 and now we can move in to more interesting examples。

 And I want to make sure that everyone knows for any kind of quiz we're going to ask what is an abstract data type。

 and you should know that that's a data type whose representation is hidden from the client。



![](img/5648f787a6d708f6e06d1602b74efe6a_2.png)

![](img/5648f787a6d708f6e06d1602b74efe6a_3.png)