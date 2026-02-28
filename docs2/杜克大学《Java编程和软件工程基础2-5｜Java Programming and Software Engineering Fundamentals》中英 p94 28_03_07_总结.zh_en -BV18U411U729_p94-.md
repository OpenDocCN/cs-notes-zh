# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p94 28_03_07_总结.zh_en -BV18U411U729_p94-

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_0.png)

Hi， as you get ready to start the program to create stories from templates。

 let's summarize what you've learned about the arrayist class in Java。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_2.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_3.png)

Aray lists are like arrays。 Both are indexable collections。

 allowing you to access elements with an integer index。

 Array lists can grow as elements are added to it。 This means you don't need to know in advance how much space to allocate for an array list like you did for an array。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_5.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_6.png)

Like arrays and individual string elements， indexing in an array list starts with 0。

It takes the same amount of time to access the first element of an array list or an array。

 as it does to access the 1000th element。It might help you to think of a list as a collection of boxes。

 each addressable with a number。To use the array list class。

 you must import it from the Javadot ule package。 You can import just the array list class or use the asterisk and import Java do udo dot star to gain access to all of the classes in the package。

 like the random class。When you create an array list。

 you specify the type of elements stored in the array list using the angle brackets syntext the Java uses for generic or general elements。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_8.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_9.png)

Here you see an array list that can contain string objects。

But a list can also store integer objects too。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_11.png)

Though the lists must store integers or strings， not the same type in one list。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_13.png)

The integer class allows int values like 0 or 57 or negative 352 to be stored in the array list。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_15.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_16.png)

The integer class automatically converts an in value like 57 into a value stored as an integer object。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_18.png)

You've seen several methods used in array list objects。

 The dot add method adds an element to the end of an array list。 The array list grows， as needed。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_20.png)

The dot size method returns the number of elements stored in an array list。 Typically。

 this is the number of elements added via dot addd。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_22.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_23.png)

You can write code to access individual elements with an integer index using the dot get method。

And you can change the value stored at a specific index using the dot set method。

Aray lists are typically processed and accessed using loops。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_25.png)

Here's a typical indexing loop that processes each element of an array list。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_27.png)

These four loops typically start at zero and loop to less than the size of an array list。

 which is exactly dot size elements。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_29.png)

Within the loop， each array element is accessed using the dot get method and the loop index variable。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_31.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_32.png)

When accessing array elements in a loop like this do not call dot add or dot remove。

 which will change the size as the loop iterates， typically causing a problem in your algorithm because you will either skip elements or access invalid elements。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_34.png)

You can also access the elements in an array with an iterable loop。

 the same kind of loop we used with the Eduu。 Duke iterable classes。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_36.png)

In an iterable loop， your code indicates the type of value stored in the array list。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_38.png)

Your loop takes on each value stored in the array list one at a time。

 just as with the file resource or image resource classes。



![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_40.png)

You can use this kind of loop when you don't need the index of each array list element。

 but just the element itself。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_42.png)

Just as with an indexing loop， do not call dot add or dot remove with an iterable loop。 In this case。

 Java will generate a runtime error if you try。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_44.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_45.png)

Arays are a very useful tool when used properly。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_47.png)