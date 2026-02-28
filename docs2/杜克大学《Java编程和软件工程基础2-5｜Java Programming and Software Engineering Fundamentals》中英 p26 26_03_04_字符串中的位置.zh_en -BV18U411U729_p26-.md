# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p26 26_03_04_字符串中的位置.zh_en -BV18U411U729_p26-

![](img/04c74bcfd3aa01731ac6574f5d0c5af9_0.png)

To move forward implementing a gene finding program。

 we will explore a couple of important string topics in this video。

 The first of them is how we can represent the position of something in a string。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_2.png)

To answer this question， we return to the recurring concept that everything is a number。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_4.png)

![](img/04c74bcfd3aa01731ac6574f5d0c5af9_5.png)

That is， we will give each position in the string a numeric index。

Notice that these numbers start at 0 in the first position。 not one。 This may seem a bit odd。

 since we usually start counting from one， not 0。 However。

 many programming languages start numbering sequences of things such as strings from 0。

 because it makes some tasks easier， as we shall see later。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_7.png)

These numbers， which describe the positions in the string are called indices or indexes。

 either word is O is an okay plural of index。For example， if I wanted to talk about this E。

 I might say the letter at index 3 is E。

![](img/04c74bcfd3aa01731ac6574f5d0c5af9_9.png)

We have now answered the first question， we can represent the position with a number。

 and we can talk about the index in the string where we find the AG。

Now it is time to answer the second question， how could we get all the letters in a particular range？



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_11.png)

Which we could now be a bit more precise and say between two particular indices。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_13.png)

One option would be for you to write your own algorithm to do this。 However。

 you can also use a built in method of the string class。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_15.png)

Whenever there is a built in method to accomplish a particular task。

 it is better to use it than write your own。 Not only does it save view work。

 but the built in method has already been heavily tested by expert programmers。

 so you can be very confident that it works correctly。For this particular task。

 you want to use the built in substr method。 However， before we show you how to do that。

 let's take this example string and make it an actual Java string assigned to a variable。

Here we have a variable declared with the name S of type string。

And an equal sign to make an assignment statement and a semicolon at the end of the line to end the statement。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_17.png)

However， this isn't quite correct yet。We also need to put the string literal in quotation marks as shown here。

 If we did not put these and just wrote the word， Java would think Duke programming was the name of a variable and give us an error that is undefined by putting the text in quotation marks。

 Java knows that we want a string that with that literal text。

So now we have a valid statement which makes the variable S be the string du programming。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_19.png)

Next， you can see an example of using the substr method here we declare another variable of type string called X and assign it to the result of S dot substring 4 comma 7。

What do these numbers mean and what does this method call do？

The first number specifies the index in S from which we want to start making our substr。

The letter at this index will be included in the resulting string。

The second number specifies the index and S where we want to stop making our substrate。

The letter in this index will be excluded from the resulting string。

The method will stop right before it gets to that letter。This may seem odd。

 Why would you want to specify the index after where you want to stop。

There are a variety of reasons why this method and many others are designed this way。

 But one nice reason is that the length of the resulting string will be the difference between the two numbers。

7-4 is 3。 So we will get a three letter string as our answer。In particular。

 you will end up with this three letter string made up of the letters from the indices 4。

5 and 6 of S。So x will be the string PRO。While you are learning about this built in method to of string。

 let's take a moment to talk about a few other useful methods and what they do。

 You just saw substr and learn how it gives you the letters in a particular range of indices。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_21.png)

![](img/04c74bcfd3aa01731ac6574f5d0c5af9_22.png)

Another useful method is dot length， which tells you how many characters are in the string。

The string S has length 15。Notice that for a string of length 15， the valid indices are 0 through 14。

 If you try to access an index outside of this range。

 your program will have an error with a string out of bounds exception。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_24.png)

Another really useful method is dot index of you pass this method， another string。

 and it tries to find the first occurrence of that string within the string you called the Methadone。

For example， here， we have asked the index of method to find the string program。Within the string， S。

You can see that the first occurrence of program is right here since it starts at index 4。

 That is the value that the method call would return。

Here is another call to index of S dot index of G。Can you figure out what this would return。

This will result in7， since the first occurrence of the string G starts at index 7。

If you call dot index of on a string that is not found， such as dot index of F， it returns negative1。

You can also give dot index of a second parameter specifying the index to start searching from。

Here we have passed 8 as a second parameter。 So the dot index of method will ignore。

Characters in the indices 0 to 7 as it searches for G。 It will then find this G。

 which is the first one when you start looking from index 8。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_26.png)

So this method call evaluates to 14。Another useful method is dot starts with。

 which tells you if a string starts with another string。Here you can see that S starts with Duke。

 so this method call evaluates to true。Likewise， dot ends with check to see if a string ends with another string。

S does not end with king。 So this method evaluates to false。Wow。

 that was a lot of methods and a bunch of information。

How would you know all of this without us telling you about every method in the string class and should you be memorizing all of these details？

Of course not， programming is not about memorization。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_28.png)

Although as you program a lot， methods that you use commonly will naturally become familiar。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_30.png)

Instead， you should learn how to make use of the language documentation。

 which describes all of the built in classes and their methods。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_32.png)

![](img/04c74bcfd3aa01731ac6574f5d0c5af9_33.png)

If you search the Internet for Java string， your first result will probably be something from Docs。

 oracle co。 Oracle is the company that makes Java and Docs。

oracle co is the website where they host the language documentation。 If you click on this link。

 you will end up with a page that tells you all about the string class。If you scroll down a bit。

 you will find a rather long list of all the built in methods and string。 Here are a few of them。

 including a few that you have just learned about dot index of and dot length。

 These entries give a brief description of the methods。 And if you click on one of the method names。

 you will get a more detailed description of what that method does。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_35.png)

There is also a documentation page on the course site at Dukeleunderprogram。com。

 that page has simplified documentation of some important methods for quick reference。



![](img/04c74bcfd3aa01731ac6574f5d0c5af9_37.png)

Great now you not only know about indices and strings and some useful built in methods。

 but also how to learn about other methods when you need them。

