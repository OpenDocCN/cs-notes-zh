# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p170 50_05_06_使用Java NIO读取文件.zh_en -BV18U411U729_p170-

![](img/2c6dbc753d8872dda84fcc87dbe33781_0.png)

In this lesson， we're going to provide reasons for why we decided to hide some information about how files and URLs work with Java and how you can write programs using standard Java libraries。



![](img/2c6dbc753d8872dda84fcc87dbe33781_2.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_3.png)

Having to understand the details about how files and URLs are used in programming can easily get in the way of solving higher level problems。



![](img/2c6dbc753d8872dda84fcc87dbe33781_5.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_6.png)

That's why we provided theedduu。duke Library and the class file resource to help you more quickly solve real problems by programming。



![](img/2c6dbc753d8872dda84fcc87dbe33781_8.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_9.png)

All languages and all libraries insulate programmers from complex details that can get in the way of solving problems。



![](img/2c6dbc753d8872dda84fcc87dbe33781_11.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_12.png)

The libraries we provide are a great insulation and protection for those first learning Java。

 but even the regular Java classes provide insulation and protection。



![](img/2c6dbc753d8872dda84fcc87dbe33781_14.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_15.png)

We've worked to empower you to solve problems， to think creatively about writing programs that will help you learn about programming and problem solving together。

Now we'll show you how to write the Hello World program without using the file resource or URL resource classes。

See how this is done could help you implement your own classes to insulate common issues you have while programming。

What for us was two classes in the Eduu。 Duke package。

 plus a third exception class that some of you may have encountered will be at least six classes in three different packages that are harder to use than the classes we designed。

Using the Java libraries will require understanding exceptions and several programming idioms that are more complex than the simple four each loops we started with。

Let's look at one of the first Java programs we used to print Ho world in several languages。



![](img/2c6dbc753d8872dda84fcc87dbe33781_17.png)

This code uses the dotedu do file resource class and the method run hello， as you can see here。



![](img/2c6dbc753d8872dda84fcc87dbe33781_19.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_20.png)

This method prints Ho world in different spoken and written languages by reading the text from many languages and printing the words read。



![](img/2c6dbc753d8872dda84fcc87dbe33781_22.png)

The code first creates a file resource object to reference and read the file containing the words we want to print。

Then the method loops over each line in the file using a for each loop as shown here。

Reading a string and printing the string in the body of the loop。

Let's look at the same code that uses Java， not our libraries。

 but rather a way to do this with just the standard Java libraries。

 This code uses seven classes in three packages。 Both programs use the system class。



![](img/2c6dbc753d8872dda84fcc87dbe33781_24.png)

There are many ways to do this， but the one that we're showing will highlight some of the flexibility these extra classes provide to reduce duplicated code。

The first step is to create a path object in the code we've named this object P。

 It represents a path to a file in the file system Here， we've used the path do get。

 Note the extra S to get the path。 The idea of a path is the same with a file or URL。

 something that goes from folder to folder to the file in the actual file system。

One standard way to read a file in Java is using a buffered reader from the Java。 Io package。

 the paths and path classes are in a different package as we'll soon see。To create a buffered reader。

 we first ask the files object again， note the S in files。To create one for us to use in our program。

We'll see other ways to create buffer readers when we use a URL instead of a path to a file。

We use a loop and the readerer dot read line method to read each line of the open file until a null reference is returned by readline。

 That means the file has been completely read， and the loop exits。

 Both this code and the code with our file resource object use loops， but the loops are different。

 The two main packages we use to read files in Java are Java dot I O and Java dot N I O。

 The N in N I O is for new。 though the package is actually old。

 but it is newer than the Java do I package。

![](img/2c6dbc753d8872dda84fcc87dbe33781_26.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_27.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_28.png)

The I stands for input， reading and the O stands for output writing， in other words。

 these are the input output packages。

![](img/2c6dbc753d8872dda84fcc87dbe33781_30.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_31.png)

The classes， paths， files and path are in Java dot and I O。 These classes。

 files and paths use static methods， which you have recently learned about。

 You know that these methods do not belong to a particular instance of a class。

 but rather the class as a whole。 So you do not need to create new objects to use them。



![](img/2c6dbc753d8872dda84fcc87dbe33781_33.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_34.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_35.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_36.png)

Many of the methods for doing reading and writing， as well as some constructors can throw exceptions。

 Now that you have learned about the basics of exceptions。

 you know that you should handle these with trycach blocks and that if you do not handle them。

 you must add a throw to the appropriate exception type to your method declaration。



![](img/2c6dbc753d8872dda84fcc87dbe33781_38.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_39.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_40.png)

![](img/2c6dbc753d8872dda84fcc87dbe33781_41.png)

The Java。Io package provides other classes for reading and writing。



![](img/2c6dbc753d8872dda84fcc87dbe33781_43.png)

The buffered reader class is often used when reading sources。

 buffering what is read for good performance。 The Java dot I O dot I O exception class is thrown by many input and output methods。

Using these classes requires reading the documentation and looking at examples because there are many ways of reading files。

 raw bytes or objects or parsing information we created the file resource class to make these things simpler。

Let's look at one more example， how to read URLs without using a URL resource but using the Java。

 net package。

![](img/2c6dbc753d8872dda84fcc87dbe33781_45.png)

Reading URLs with this package is similar to how reading works with our Eduu。duke。

 URL resource class。 First， you create a URL object by providing a string that represents the website。

You'll then use this URL object to create a buffered reader from the Java。 Io class。

 but that takes several steps。 The first step is to open a connection to the associated URL and get a stream representing its data。

Then use this stream to create an input stream reader。

 then use the input stream reader to create a buffered reader。

 That's three steps to replace the one step we had in creating a URLs resource object。

The purpose of these extra steps is to provide different ways to create an object that implements the reader interface so that you can read the data from a file or a URL using the same code。

So you read using the same buffered reader loop that we use in the last example。

 this kind of reuse is harder to do with our simplified resource classes。

 and one of the reasons it is useful to take the time to learn more about these complex classes。

