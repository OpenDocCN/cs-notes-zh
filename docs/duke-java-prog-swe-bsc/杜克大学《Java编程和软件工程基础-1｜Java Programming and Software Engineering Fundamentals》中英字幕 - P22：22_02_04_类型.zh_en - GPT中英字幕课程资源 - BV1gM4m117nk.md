# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P22：22_02_04_类型.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/06b00c05e8f499d412cb1406ac1fcd60_0.png)

Welcome back。 Now you've seen a bit of code that works with images and numbers。

 two different types of data。But what if we do something that does not make sense， like try to do w。

getwith？W is the number 480， which doesn't have a get width method。In this particular case。

 the code will crash when execution reaches this line。😊，So why is this call to get w fun？

But this one crashes the program。If we go back to our diagram that depicts the state of the program。

 you will see that we were working with two different types of data。

FG image refers to a simple image， which has a Gettwi method。But W is a number。

 a type of data that does not have a getwi method。So what exactly is a type？Well。

 remember that everything is a number， but we have lots of different things。

 we want those numbers to represent， letters， images， sounds， and just plain numbers。

So the type tells us what those numbers mean， that is what kind of thing the number represents。

This is important because the type specifies not only how the program should interpret the number。

 that is what the numeric value means， but also how to operate on it。

The same operation may have different behavior on different types。 This may sound confusing。

 so let's look at an example。Here we have some code， which has two plus operations in it。

 as you are about to see， these two pluses will do different things since they will operate on different types of data。

Let's step through the code。N1 equals 26 and 2 equals 16。S1 equals open quotes， A close quotes here。

 S1 is a string， a sequence of letters。 This particular sequence has just one letter， a。

S2 equals open quotes， B， close quotes。Now we're about to do the first plus operation here we are doing in one。

 which is 26 plus N2， which is 16。Both operas are numbers， so we are just doing numeric edition。

 26 plus 16 is 42。Now we are about to do the second plus operation。 however。

 here we are doing plus on two strings， A and B。What does it mean to do plus on strings for strings。

 plus does not mean numeric addition， it means concatenation。

Concatetnation is a fancy word for taking two strings and sticking them together one after the other。

So you get S3 equals the string AB。Notice how Plus meant two different things based on the type of the data it was operating on。

So how does JavaScript keep track of the type of the data？

It keeps information about the type explicitly， along with each value when it stores it in the computer's memory。

Then whatever it needs to work with a value， it reads the type and value out of the memory to figure out what to do。

Because JavaScript keeps the types of all values in memory。

 meaning that it tracks and works with the types while it runs the program。

 it's called a dynamically type language。If you stay for course two and beyond。

 in which you will learn Java， types will work differently。Java is a statically typed language。

 which means that every variable and every expression has exactly one type。

 which must be known before the program can even be run。For this to work in Java， you。

 the programmer， write down the types of your variables explicitly in your code。

Then your code can be checked for certain kinds of mistakes。

 like trying to call Git width on a number。Before it is even run。

Having this kind of mistake found before the program runs is really helpful。

You'll learn more about types and Java in Cose2 for now， however。

 we have a bit more JavaScript to do so that you can implement the green screen algorithm， Thank you。

