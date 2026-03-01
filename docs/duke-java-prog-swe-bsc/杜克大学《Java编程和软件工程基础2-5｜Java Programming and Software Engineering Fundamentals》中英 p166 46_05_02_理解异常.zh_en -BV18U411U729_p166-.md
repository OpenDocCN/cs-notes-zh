# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p166 46_05_02_理解异常.zh_en -BV18U411U729_p166-

![](img/83dae4d8ed9f85f526565ac445b949db_0.png)

Hi， you've probably seen exceptions and know that they mean your program crashes because something went wrong。

But what exactly are exceptions and why does your program crash in this particular way？

How could you use them in your own programs？An exception means that the program could not do something that it tried to do。

Sometimes this indicates a mistake in the code， such as when you access an invalid index in a string or an array。

 however， sometimes an exception indicates a circumstance beyond the programmer's control The user asked your program to open a file that does not exist or their internet connection went down while your program was trying to download information real programs have to deal with such problematic situations and exceptions are actually one of the nicer ways to handle these types of problems。

This exception message， which is likely similar to something you have seen before。

 is called a stack trace。When your program has an unhandled exception。

 one that indicates something went wrong and your program did not say how to deal with it。

 your program crashes and prints a stack trace。If you look at this in detail。

 it starts by telling you that there was an exception， something went wrong。

Then it says in thread main， we're not going to talk about threads。

 which are a fairly advanced concept。 And unless you start using them。

 you can ignore these few words of the message。Next。

 the message tells you what kind of exception happened。That is what sort of problem the program had。

In this example， I made a mistake in my program and access to string at an invalid index。

 so I got a string index out of bounds exception。Many exception types are nicely descriptive of the problem。

 but you can always check the documentation for more information。Next。

 the message provides some more information about the problem。

Here it tells me what the invalid index was。 I tried to access element 82。

 which was not legal for that string。The information here will depend on the type of exception you have。

Lastly， the message has the stack trace。 that is the list of methods which had been called。

 but not yet returned when the problem occurred here。

 the problem happened inside of strings do Carat method。

 specifically on line 646 of string Java in the Java library。The next line shows what called strings。

cart method， which was do stuff and test。java on line 5。

 this is the first method that we see that is in my code rather than a library。

 which is generally where you will want to start looking for the problem。Last。

 it shows where main called do stuff on line 8 of test Javava。

Which just said that your program crashes and prints a stack trace If it does not handle the exception。

 Your program can， however， handle an exception， specifying what to do to deal with the problem。



![](img/83dae4d8ed9f85f526565ac445b949db_2.png)

![](img/83dae4d8ed9f85f526565ac445b949db_3.png)

Handling exceptions involves three new concepts， try， catch and finally。

 which you will learn more about shortly。

![](img/83dae4d8ed9f85f526565ac445b949db_5.png)

After you learn about try catch and finally， you will learn about exception propagation。

 where a method that does not know how to deal with an exception will propagate the exception to its caller。

 The caller can then either handle the exception or propagate it to its call and so on。

 You do not have to do anything explicit to propagate the exception。

 which is one of the key benefits of exception based error handling。😊。



![](img/83dae4d8ed9f85f526565ac445b949db_7.png)

![](img/83dae4d8ed9f85f526565ac445b949db_8.png)

But you do sometimes need to declare that the method might throw an exception。



![](img/83dae4d8ed9f85f526565ac445b949db_10.png)

Finally， you will learn about throwing your own exceptions when your code discovers that a problematic situation has happened。

 Thank you。😊。