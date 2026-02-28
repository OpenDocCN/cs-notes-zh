# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p87 21_02_05_构造函数.zh_en -BV18U411U729_p87-

![](img/12414606c78d3b91df51a6eec771c464_0.png)

Welcome， the last object oriented concept you are going to learn in this lesson is constructors。

 recall that the object oriented Caesar cipher we wrote had a constructor。

 which took the key as a parameter and initialized the fields on the object。😊。



![](img/12414606c78d3b91df51a6eec771c464_2.png)

When you want to write a constructor， there are certain rules for declaring it。

 The first is that its name has to be exactly the name of the class it is in。Here。

 the constructor's name must be Caesar cipher， because it's in a class called Caesar Cypher。

The second rule is that the constructor has no return type， not even void。Normally。

 you would write a methods return type here between public and the name of the method。

 But for constructor， you you do not need to write anything between them。Like a normal method。

 a constructor has its parameter lists and parentheses。

 You can make constructors with any number and types of parameters you want。

 You can have no parameters to a constructor， or several。Here we have one parameter of type it。

 the key。Finally， a constructor has a body like a normal method。

 you can write whatever code you want in the constructor's body to specify how to initialize the object。

Constructors are not quite like normal methods。 However， you do not call them directly。 Instead。

 they are automatically as part of knowing an object。 when you create a new object。

 the constructor is invoked to initialize that object immediately after the new object is made。

 This is one of the great benefits of constructors。

 They allow you to specify how an object should be initialized。

 and you can be sure that code will always be run for every object as soon as as soon as it is made。

 you do not have to worry about bugs in your code from forgetting to call some initialization code。😊。

What happens if you do not write a constructor for your class whenever you write no constructors。

 as you've been doing up to this point。

![](img/12414606c78d3b91df51a6eec771c464_4.png)

The Java compiler will provide a default constructor for you。

The constructor that the compiler provides looks like this， it is public， which you should recall。

 means any piece of code may use it to initialize an object。It takes no arguments。

 so you would pass no arguments when you create new objects， and it does not do anything。

 There is no special initialization of the object。Now that you know the rules about constructors。

 let's see how a constructor works。Let's suppose you had a line of code somewhere else in your program like this。

 Caesar cipher C C gets new Caesar Cypher 22。 This line of code S Java to make a new instance of the Caesar cipher class and initialize it by passing 22 to your constructor。

Let us see what this does by starting when Java is just about to execute this line。

 The first thing it does is create a new variable C C。

 Then it creates a new instance of the Caesar cipher class。

 That means you have a new object with its own copy of the fields of that class。

 alphabet and shifted alphabet。Then it calls the constructor passing 22 for the key。

 Once inside the constructor， Javava begins executing the code you wrote to initialize the object。

 This code initializes alphabet。Then initializes shifted alphabet。Having finished the constructor。

 Java returns back to where you are creating the object。

 The key was just a parameter to the constructor， so it only exists during that call。 However。

 the fields are part of the object， so they continue to exist in it。

And then finishes the assignment statement by initializing the CC variable to the newly created object。

 Great， now you know the basic rules of how to write constructors。

 what they do and how they are used to initialize objects。 Thank you。😊。

