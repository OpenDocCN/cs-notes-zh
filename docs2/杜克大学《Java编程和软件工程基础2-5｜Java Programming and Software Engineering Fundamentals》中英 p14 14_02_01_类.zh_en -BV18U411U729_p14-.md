# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p14 14_02_01_类.zh_en -BV18U411U729_p14-

![](img/2667ac1ba5aac79d80e62252709d9bfc_0.png)

As you continue learning how Java works， it is important to talk for a bit about objects and classes。

 Before we delve into the specific semantics， let's talk for a minute about the high level concepts。

 When you are writing a program， you often have data in the form of variables which store the values you are computing on and code。

 which manipulates that data， according to the algorithm you have designed object oriented programming is a paradigm of programming languages that group data and the code that manipulates it together into logical units called objects。

 This language design aims to help programmers think about their program by grouping the code and data together into one logical unit。

😊，As you write larger and larger programs， this principle becomes more and more helpful。

As you progress and learn more about Java， you will learn about a lot of important principles that go along with these ideas。

 For now， however， we are just going to start with the basics here。

 you can see an example of a class declaration。 A class is a template that specifies how to make objects。

 Let's look at each piece of this declaration。 The first line tells Java that we are declaring a class called point。

 As with variables， we have a lot of freedom in what we name classes that we create but we should name them descriptively here。

 we are making a class which represents a twodimenional point。 So point is a good name for it。Next。

 we declare two fields， int X and int Y field is the name for a variable that is inside of an object。

 They are also called instance variables， since they are variables that are in each instance of the objects created from the class。

 These look like variable declarations， except that the word private comes before them。

 Private means that only code inside of this class can directly manipulate these fields。

 You'll learn more about why that is important as you become more skilled in Java。 But for now。

 we'll just make all fields private。Next is the declaration of a constructor for the class。

 a constructor specifies how to create objects of this class。

 It is code that gets run when an object is created to initialize that object。

 Note that the constructor looks like a function but has no return type and is named the same as the class。

 These are the hallmarks of a constructor declaration。In front of the constructor， we have the wordp。

 which means that any code can use this constructor to create a point。After the constructor。

 we have three methods， Git x， Git y and distance Me are functions that are inside of classes In Java。

 Everything is inside of a class。 So technically all functions in Java are methods。

 These methods are invoked or called on a particular object and implicitly act on that object。

 You can see a method call here， where the code says other point dot git X。

 This calls the git x method on the other point object。

 It will get the X of that particular point object。Last， we have the declaration of a static method。

 These behave a little differently from regular methods。

 They don't act on any particular instance of the class。 They just belong to the class in general。

 That concept is a little tricky， and will'll explain it more later。This method is called Maine。

 which is a special method。 If you run your programs outside of Blue Jay。

 Maine is the starting point。 executionution begins in Maine before any objects are even created。

The ideas of objects are supposed to help programmers think about their data in terms of objects that make logical sense。

 For example， if we make a new point， we are creating an object which represents something we can concretely think about。

 In this case， a point on a plane。We can then make another point。

 which has its own X and Y and represents a different instance of the same type of thing。

 Another point on the plane。 You can， of course， create as many of an object as you need for your algorithm。

Once you have some objects， you can invoke methods on them， such as P1。distanceP3。

 which you can think of as asking P1 to compute the distance to P3。

 that is you can think of this line of code as saying P1， go figure out how far you are from P3。

You can think of the code that executes for this method called as logically belonging to the P1 object。



![](img/2667ac1ba5aac79d80e62252709d9bfc_2.png)