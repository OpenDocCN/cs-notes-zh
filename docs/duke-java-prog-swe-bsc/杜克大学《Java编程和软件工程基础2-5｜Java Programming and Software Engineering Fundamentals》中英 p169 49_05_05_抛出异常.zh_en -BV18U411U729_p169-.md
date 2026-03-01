# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p169 49_05_05_抛出异常.zh_en -BV18U411U729_p169-

![](img/a8b4a18859e0bc9d3443b52ba5b46e9c_0.png)

You can throw exceptions in your own code whenever it encounters a problem and cannot handle。

 you have seen this principle already when writing your Markov code。

 This piece of code comes from that lesson and gets a particular word from the word gram class。

 As you can see here， it throws an exception when the requested index is invalid。

 The code is encountered a problem that it cannot deal with。

 The program will crash unless some color of this method catches the exception。

 The syntax for throwing an exception is to write the keyword throw。

 followed by an expression which evaluates the exception you want to throw。 As is the case here。

 this expression will typically make a new object of whatever exception type is desired。

 passing in any useful information to the constructor。 So what exactly can you throw。

 technically speaking， any class which extends jas built in thable class。 However。

 more common is to throw an object of a class which extends exception， which itself extends thable。



![](img/a8b4a18859e0bc9d3443b52ba5b46e9c_2.png)

Java has 57 built in exception types。 Well， okay， maybe not 57 billion， but it sure has a lot。

 Some of these may be familiar， such as array index out of bounds or null pointer exception。

 Io exception is another common one， which indicates a problem reading or writing data and is why exceptions are important to understanding how to read files on your own。

 Most of the time， the built-in exceptions will provide you with whatever you need。

 and you can find out more about them in the Java API documentation。

 If you write a program where you need exceptions beyond the built-in ones。

 you can always write your own。 You would do this by writing your own class and making it extend the appropriate existing exception type。

 We aren't going to delve into the topic of creating custom exceptions。

 but we wanted to mention it as part of our discussion of exceptions in case you ever find yourself needing it in your future programming endeavors。

😊。

![](img/a8b4a18859e0bc9d3443b52ba5b46e9c_4.png)