# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P35：35_09_02_概述_2.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/0130436b1a1052e437d9570e8f8a45ec_0.png)

Well， last lecture you saw the utility of using data types that you can create on your own This time we're going to take a look at the process of creating our own data types。

Let's start with a quick overview of what we need to do。

 This is the last in our building blocks for programming。

 where we've already considered all these basic things up through functions and modules。

 and now we're going to talk about programming with objects。

And this is going to give you the ability to bring your own abstractions to life。So in general。

 this process is called object oriented programming or OOP。It's where we create your own data types。

 create our own data types， use them in our programs。

 and creating the data type and using it in our programs is really what we talk about as objects where an object is something that holds a data type value。

So our variable names refer to objects and objects hold data type value。So， for example。

 when we worked with color， we had our set of values。

 our operations were getread component and brightrighton and so forth。

 there were objects that hold these data type values that we manipulated。

 and we looked at picture where the set of values was 2D array of colors and then we have objects that hold those values in strings and so forth。

And really， what we usually want to do is create what's called an abstract data type。

Where it's the data type whose representation is hidden from the client。

The impact of that is that we can use abstract data types without knowing much about the implementation details and these are examples of abstract data types last time we use those we wrote programs that made use of them without knowing anything about the implementation details so we talked about client programs for several abstract data types in the previous lecture now we're going to talk about how to create them。

 how to implement your own abstract data types。So to create it。

 what we have to do is provide some code and very specific tasks that we need to do with this code。

 So one thing we have to do is define the set of values and we do that with what's called instance variables。

And then we have to implement， implement operations on those values。 and those are called methods。

And we also have to be able to create and initialize the values of new objects。

 and we do that with special methods called constructors。So what are instance variables， Well。

 there are declarations that associate variable names with types and as usual。

 but the set of type values of the set of instance variables is the set of values for the data type。

 and we'll see that in examples， it's very simple。Methods are like static methods。

 and they can refer to instance variables， and again， it's very similar to static methods。

 but with a profound difference and you'll see it with some simple examples at the beginning。

And a constructor is also like a method that has the same name as the type and it doesn't actually return it doesn't have a return type because it's going to return reference to an object of the data type Those are the basic steps that we have to do and we'll look at these in much more detail in just a minute。

The constructor， by the way， is invoked by new in Java。

 the new keyword in Java and it returns an object of the titan。

So in Java all of this put together is known as a class and so heard Java classes that we consider are all going to have this basic structure and for every data type that we implement we'll look at it exactly in this framework。

 we'll look at what are the instance variables， what's this set of data type values。

What are the constructors， how do you create an object and initialize its value。

 what are the methods， what are the operations that we can perform in the values。

 and then also we always add a test client or include a test client in every Java data type that we implement。

So that's the process that we're going to go through for several examples in this lecture。

So here's just an anatomy of a class with real code。

 and we'll look at each piece of this code in detail just in a minute。

So we put the whole class in a text file name charged at Java and the class name go public class and give the class name that's going to be the same as the file name。

 and then inside the braces go are four components， the incidence variables， the constructor。

 the methods and the test client。Now， Maine is a static method。

 and you can have other static methods in a class。 So we're familiar with that。

These methods here are not static and we'll talk about what that means。

 that's really the essence of what goes on with object oriented programming。

 and that's really what this lecture is going to be all about。



![](img/0130436b1a1052e437d9570e8f8a45ec_2.png)

![](img/0130436b1a1052e437d9570e8f8a45ec_3.png)