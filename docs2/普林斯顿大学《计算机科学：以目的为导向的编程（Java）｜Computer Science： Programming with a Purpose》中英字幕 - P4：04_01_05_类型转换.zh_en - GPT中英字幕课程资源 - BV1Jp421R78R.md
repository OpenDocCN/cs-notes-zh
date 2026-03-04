# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P4：04_01_05_类型转换.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/f439c032820cab6ae8d8c32cbb050999_0.png)

We're going to finish with a brief discussion of converting from one type to another。

 We've already touched on that several times， but it's worthwhile to take a look at it explicitly。

Now， the thing about the computer language and the concept of data types is the variables involved in a data type operation have to be of the right type。

 it's only defined for that。And that's why we appreciate the idea that the Java compiler can check for type errors in the code if we try to add an integer to a string。

 it'll tell us， well if we try to add a boolean to a double。

 it'll tell us that you can't do that kind of operation。So there's a string times 2。

 and it's going to say you can't multiply an integer times a string， that's an error。

So and that's a good thing that the Java compiler will tell us about that error because sometimes there might be conversions that happen automatically that we might not expect。

But a lot of times， as we've already seen， we want to convert from one type to another to make types match in an operation where it makes sense。

So with the built in types， it's really converting is an essential aspect of programming。

 we have to worry about it， there's three ways that it can happen。

So we've already talked about automatic if we have plus and one of the arguments is a string。

 it's automatically going to convert。In the other is a number。

 it's automatically going to convert that number to a string to get the concatenation done。

If it can if you're trying to use a float and an integer in the same expression。

 it'll go ahead and make the conversion if there's not going to be any loss of precision。

 so 11 times 0。25 it'll convert the 11 to a float and that'll be the right type and it can perform the operation。

Sometimes we need to explicitly define a type conversion like with a function call integer。

 parse in returns an in and it's going to explicitly make the conversion of the string into an int value math dot round is another example。

And then there's a third type of type conversion is called a cast。

 and so that's what we use for values that belong to multiple types。

 like small integers like two or 12 can be either short int or long and also double values。

 we can truncate them to int values， sometimes that's what we want to do in the computation。

And the way that we make these types of type conversion is just put the type that we want in parentheses before the number。

 so if we say int of 2。71828 it'll trunccate to give an int value that can be used in another expression so those are examples 11 times int of 0。

25 that ant's going to be truncated to a 0 so the result will be 0。

And we look at these types of expressions and there's many examples in the book and in the exercises。

 and it's important to always know the type of your data because if you're not aware of the type of data。

 it can lead to problems。Sometimes type conversion gives sort of counterintuitive results。

 but it's much easier to understand with some practice and that's why we highlight it right at the beginning so here's just a couple of questions that again you might find on a quiz so 7 slash 2 times 2。

0 so what's the type of that and what's the value。Well。7 over2 is inside parentheses。

 so that's going to be itteger division， so it's going to throw away the remainder and it's just going to be3 and then multiplying by 2。

0 that three will get converted to a double so then the operation star is two doubles and the answer will be 6。

0。If you do 7 slash 2。0， then you get inside the parenthees3 and a2 because then seven will get converted to a double because the other operation a double so that's 3。

5 and then that two on the right will get converted to a double。

 so we have a multiply with two doubles and you get 7。0。It also gets a little confusing with strings。

 so the string 2 plus 2， well Java automatically converts the right hand argument。

 which is a two to a string and so you get 22 and the results a string。2。0 plus2 well again。

 that's a string， if you do arguments's a string， it's going to convert the other one to a string and so anyway those are some examples of type conversion。

And it's a good idea to work through some examples like this。

So this is just an instructive modern day story about type conversion again why do we have different numeric types it's because if we want to have a big range we're going to have to use memory for integers and if we want more precision we're going to have to use more bits for floating point and that's why we have these different types。

Now， but the thing is that because of the restrictions on the range。

 it might be impossible to do a conversion sometimes。 So， for example， say I have the number 70000。

 and I say， okay， I want to cast that to a short， so I could write short 70000。 Well。

 that's not possible because short values have to be between-32，7，68 and 32，7，67。 There's only 16 Bs。

 can't do that conversion。Well， what do you do if there's an impossible conversion or what does the system do if there's an impossible conversion Well there's a couple of approaches you could use so the one that we advocate the most is make sure that you avoid doing it in the first place if you write that cath make sure that you know that the things in the right range Java's approach is say okay there's going to be a well-defined result and going you're going to have to live with it and you can check and so forth but anyway that's Java's approach and another approach is to like not check for it not live with it just crash。

And by crash， we mean actually crash， a type conversion error of this type actually led to the area on5 rocket blowing up in 1996。

 they switched to a different representation， and there was a cast that was impossible in one of the control variables。

 had a bad value that caused the rocket to crash。 you have to pay attention to the type of your data。

Here's an example of type conversion put to good use and this is our last program of the day。

 so we've got math random that gives us a pseudorandom double value。

 what if we want to get a pseudoran integer value between0 and n minus1 for any given n like we want to roll a die we make n equals 6 or if we want to draw a card we make n equals 52。

So。What we're going to do is take the value and from the command line again string the in system method。

Then we're going to get our random double value， a number between zero and1， but less than one。

And then what we do is multiply r times n， that's going to give a result that's between 0 and n but less than n and then we're going to say。

 okay， now you can truncate that and that'll give you that first the n get convert to double to do the r times n and then there's the cast to truncate once that's done and the result is an integer value between 0 and n minus1 that we just print out。

So now we can roll a die and we get different random values。

 or if we want a random value less than 10，000， we can get that too。

So that's knowing the types of your variables and using them for a useful computation。

 and we'll use this one actually a lot in this course。So that's the summary。

 a data type is a set of values and a set of operations on those values。

 there's a lot of commonly used builtin data types for Java that we've seen programs that use them。

 there's string for input and output， which is strings of characters， there's integers。

 and doubles that we use for science and math calculations and programs。

 and there's Boolean that's computing with true false values that we're going to use for decision making in programs。

So in Java you must declare the types of your variables。

 that's not true in all programming languages， you must convert from one type to another when necessary。

 and you must identify and resolve type errors in order to compile your code。

 Java compiler will not let you go on if you're doing something like multiplying a string by an integer。

You have to pay attention to the type of your data。

And I emphasize this because it's an important distinction between Java and some other popular programming languages。

 the compiler your friend， it's going to help you identify and fix the type errors in your code。

 and you're going to have much better and more reliable code as a result。

Next time we'll talk about writing programs that have more complicated control structures and perform lots more interesting tasks。



![](img/f439c032820cab6ae8d8c32cbb050999_2.png)

![](img/f439c032820cab6ae8d8c32cbb050999_3.png)