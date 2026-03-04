# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P3：03_01_04_内置数据类型.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/0bc56fd1e53959c7803720a38517ddb0_0.png)

Now we're going to get into writing some actual Java programs。And to get started。

 what we need to do is talk about the types of data that you can use and manipulate in Java programs。

 and we're going to start from the beginning with the data types that are built into the Java language。

So what is the data type， Well， it's a very well defined concept。

 A data type is a set of values and a set of operations on those values。And right now in this table。

 we'll look briefly at the built in data types for the Java language。

So there's a type called char or and that's the set of values is the characters that say we type on the keyboard。

 so like A or at sign or 1 34， any character that you can type is of type char。

Now those are the values， the operations that you can do in those values。

 well you can compare characters and we do that to put words in order and other things like that。

 we'll see。One thing that we do with characters is we put them together to make a type of data called string。

A string is a sequence of characters， So examples of a string in a Java。

 we put them in double quotes， is hellello world or Cs is fun。

 any string of any sequence of characters within double quotes is a string。

The operation that we perform on strings is called concatenation。

 and we'll look at that operation in detail。And then there's numeric data types at the beginning we write programs that manipulate numbers。

 the same way in history， computers were developed in order to write programs to manipulate numbers for scientific commercial engineering applications。

One type of number is an int， so that's just an integer and so like 17 is an integer， 1，2，3，4。

5 are integers， and the operations that we perform on them are this standard arithmetic operations like add subtract。

 multiply and divide。We also work with real numbers in Java。

 the data type double represents floating point numbers that you're familiar with from science。

 and so that's like 3。145 or 6。0 to2 times 10 to the 23。

Floating point numbers approximations to are real numbers that usually approximate the numbers that we want。

 and again， we can perform the operations of ads subtract multiply and divide。

And then there's a data type called Boolean， the set of values for Boolean is just truth values。

 true or false。And the operations that we can perform are and or not we'll talk about each one of these in more detail next。

 along with programs that use basic operations to manipulate variables that of these types of data。

So everyone has to know the answer to this question on any exam that I write， what is a data type。

 it's a set of values and a set of operations on those values if you really internalize and understand this definition you go a lot further in programming than if you don't。

So。Now， in terms of manipulating data， we have some basic definitions that appear in all our programs。

So the first thing is a thing called a variable。 That's a name that refers to a value。

 So in this case， A And B are variables。 This is a short program that adds two numbers。

Then there's a thing called a literal。 That's a programming language representation of a value。

 So for an integer， literal is a string of digits。Went to9 and， zero to9。

Then there's a thing called a declaration statement that associates a variable with a type。

 so these two declaration statements say that A and B are of type int。

 so the set of values that they can take on is the integers and the set of operations you can perform on are add subtract multiply and divide。

Then the other kind of statement that we're going to use for most of the programs today is called an assignment statement and what that does is associate a value with a variable。

 so this one associates the value 1，2，3，4 with a and the second one associates the value 99 with B。呃。

So then this last one， you can actually combine a declaration and an assignment statement。

So let's look at a really simple example of a complete program that uses all of these concepts。

So what happens is that we have two variables A and B 12，3。

4 and 99 that we set up like on the previous slide and they're both int values。

 and then this is a program that exchanges the values of A and B。

Usually at the beginning to understand what our programs are doing。

 we write a table called a trace that just gives the variable values after each statement。

So we start out with none of the variables declared， we say int a equals 12，3，4， then 1，2，3。

4 is associated with A。 that's what the table shows。B equals 99，99 is associated with B。

 that's what the table says， and then T equals a takes the value that's 1，2，3。

4 and associates that with T。 So after that statement， T is 1，2，3，4。

 Now the assignment statement is not equals like mathematical equality。

 It really says associate the value with the variable。Which is different。Okay。

 so now we say a equals B， so we find the value associated with B that's 99。

 and we can see that from the trace and then we associate that with A。And then B equals T。

 then we have the  one，2，3，4 associated with T， and then we give that value to B。

 so that trace of these five statements tells us what that program does。

So the question is what does this program do and actually if you type in this program and run it。

 well nothing's going to happen， there's really no way to tell what it did。

 we need some output for that so we have to put a print line like for hellello World and we'll talk about that in just a second。

But what the program does is exchange the values。Okay。

 so in order to provide that output so that we see it when we run the program。

 that's what we use strings for。Again， the string data type。

 the values are sequences of characters in between quotes。

Our operation is concatenate and we use the plus sign to indicate that we want to concatenate strings。

 and so if we write an expression using the operation。

 if we take two strings and put a plus sign between them。

 then it just puts the second one after the first it makes a new string that contains all the characters in the first string followed by all the characters in the second string。

It doesn't matter any string at all so this is the string one concatenated with the string space two space。

 concatenated with the string one， and then you get one space， two， space one， and like that。

So concatenation operation， so you have to pay a little attention because the meaning of each character depends on the context。

 if a plus is within quotes， it means the character plus if it's not within quotes。

 it means the concatenation operation。So in this first case we get the plus character。

 in the second case we just get a bigger longer string of digits。So again。

 the interpretation depends on the context and I just gave that one example where two of the pluses are operators and the other one's a character。

 and this is another one with spaces。If the spaces are outside the quotes。

 Java doesn't care about them， you can put any number you want， if they're inside the quotes。

 they're part of the string and they're significant。So that's computing with strings。

And why do we compute with strings Well， we want to put together output that we print on our terminal window so that we can see what our program did that's why we talk about strings right away。

 we use them for input and output。So but you can also write programs that compete with strings here's a program and the goal of this program is to print the heights of the divisions of aurr so the little line under the two is say four units high。

 the ones at the half inches are three units high the ones at the quarter inches are two units high。

 the ones at the8 inches are one units high and if you write out this string， 1，2，13，1，2，14，1，2，13，1。

21， we want to write a program that does that and this is a really simple program that accomplishes that goal just by building up using concatenation to build up a big string。

Now all the operations are concatenations and again we can write a trace to see what this thing does。

 so the first thing sets ruler 1 to just the one string。

 and then ruler2 is that one plus space two space plus another one。

And then the next one takes that string and then puts a three and then another copy of that string and then ruler four does it to get four。

 so simple four line program and then if we want to see what string we got。

 all we have to use is print line just like we did for Hello world with Hello world we had the string Hello world now we've got the string ruler4 and so when we run this program we get this string printed out and we've got a program that computed something interesting just with string operations。

So we type Java ruler， we get that string up。Computing with strings。Okay。

 so we need input and output and we use it for the result of our computations， the thing is。

 and especially at the beginning， very often our programs are working with numbers and we're working with strings。

 so for output， we use system。 outdo printline to print the string。And even if you print numbers。

 Java will automatically convert the numbers to sprint strings to output them for input if you type Java and a program name。

 any strings you type after the program name are available to the program and we'll look at how to get information into our program as strings from the command line。

 so those are the two ways at the beginning that we're going to use input and output to get information to our program and to learn what it did。

So those things that we type are strings because we're typing them how does Java know if we type 1，2。

3，4， whether we mean the string 123，4 or the integer 1。

234 Well there's a system method that converts that and we'll look at the use of that in just a second。

And before very long， we're going to look at lots of different options for input and output and also lots of different options for converting types。

 but we need lead to talk about these few just to get started on the rest of the programs that we're going to look at today。

So as I said when we had this Exchange values program we don't know what it did unless we print out the results。

 so if we add these two print line statements to this program again A and B our integers。

 their data of type in， their integers， but Java will automatically convert them to string for output so if we type Java exchange and the other thing is that this program takes from the command line to arguments as 0 and as 1。

 they come in as strings we call parse in to get them converted to numbers and that's what we set to A and B。

So they start as strings， they become numbers， then the code exchanges them and then when we print them they get the result gets converted back from string numbers to strings and so what does this program do。

 it reads two integers from the command line and then prints them in the opposite order。

 it actually reads strings， converts them integers。

 exchanges them prints them out in the opposite order so just looking at this program now it's a template for lots of programs that we can write where we provide parameters as strings that easy to convert to numbers。

 process the numbers and then print them out with the system automatically converting them back to a string。

So now we can look at computing with integers。So the int data type again。

 what's the set of values in a computer it's got to be finite and we can talk about the details。

 but in Java the set of values for an int are the integers between minus2 to the 31st and 2 to the 31st minus1 and this range has to do with the way the integers are represented within the computer。

And it's useful for typical applications and again。

 literals are just strings of digits that represent integers in this range。

Now operations add subtract multiplied divide and remainder。And again。

 there's only two to the 32 different int values， so they're not quite the same as real integers。

 which could be bigger than that， but for many purposes they're useful enough。

 and then we can do operations like add to integers， subtract them， multiply them。

If we divide two integers， then the result we get， they drop the fractional parts so that the result is an integer。

 if you take the remainder， you get the remainder of the division or the modD operation and if you divide by zero that's an error。

 you'll get runtime error from the Java system。We can write longer expressions and there's a concept called precedence。

 if you write an expression that's got a couple of operations。

 which one's going to get performed first， while multiplication and division are going to happen before addition and subtraction。

So in the first case the multiplication gets done so that's 15 they subtract the two that's 13 in the second case the division happens first and it's two drop the fractional part and then add the three to get five。

If you write a couple of operators that have the same precedents。

 Java expressions are so-called left Associative， which means the one on the left gets done first。

 but it's better styled to use parentheses to express your intent as a programmer and not try to trick the person reading the code。

So we're going to see lots of examples of programs that manipulate integers and we're going to use them for math calculations and other applications。

So this is an example of computing with integers and again。

 just to make sure that everybody's thinking carefully about the difference between integers and strings and type conversion so take a look at this program for a minute and try to see what it does。

u。Again， one thing that I didn't mention is that if you take a string。

And you add it to an integer using the plus operation Java figures out that really what you meant to do was convert that integer to a string and then go ahead and concatetnate so it's another automatic conversion that Java does convert the invalue to string for concatenation。

Then with that piece of knowledge， you can see what this program does is it takes two arguments from the command line。

Then it performs the basic plus times divide mod int operations， the sum of the product。

 the quotient the remainder， those are then computed and theyre a part of Java's int data types so their integers。

 those values and then it prints out a string that represents the expression that it computed it takes the int A and so in this case it's going to be five and then it concatenates that with plus space plus space and then puts the B。

 then space equal space and then puts the sum and it does that for each of the four operations so you get a little table defining the result of Javas computation for these operations and this is a nice program to make sure that you understand what's going on in terms of type conversion and integer and string operations that's just computing the remainder for you。

Okay， next， we're going to look at a data type for computing with floating point numbers。

 the double data type。So again， the values for double data type are。

Floating point numbers are scientific notation， so this one is 6。022 times 10 to the 23rd or 3。

14159 in like that and again the operations are the familiar arithmetic operations now it's important to remember that often or typically double values are approximations to the actual number you might be thinking about like there's no double value for pi representation within the computer can only have a finite number of values or for square root of two or even for onet in Java representation there's no double value there's one that's extremely close but it's not exactly equal to one thirdd and that's something that we have to take into account when we're writing programs that are working with approximations to real numbers。

So these are the types of expressions that we write with double。

 and again we get the results pretty much that we expect。

For math computations get good approximations to the numbers that we want in the case of double there's some special values。

 so if you say one divided by zero with doubles， there's a special value called infinity and you can compute with infinity and get the kinds of results that you expect。

But there's also not a number， if you take the square root of minus1。

 that's not a real number and there's a value， not a number that you can work with as well。

Those are the basic values and operations for the double data type。And again。

 we use this for scientific calculations and we'll see plenty of examples of programs that do scientific calculations with this type of data。

There are other built in types for representing numbers in Java that we don't use too much。

 but sometimes there's one called short， which is same operations as int， but smaller set of values。

 and another one called long， which is same operations but a much larger set of values。

And there's one called float that is like double but it's a smaller set of it's less precise and so the reason that we have different numeric types is that it's a tradeoff between how many bits do we want to use to represent the number and for integers it's a straight tradeoff is what's the range and for real numbers it's how much precision do you want to get with the number and I guess the range as well so and without going into a lot of detail that short is 16 bits in and float are 32 and long and double or 64。

And it's important to be aware of these kinds of restrictions in really knowing what the set of values is。

 because you can get into situations where it's important and we'll talk about a situation like that in a bit。

Now with doubles we have lots of built-in functions that we can use to compute on double values and actually a lot of them work for and other types as well。

 so you can get the absolute value， you can get the larger two values of the smaller of two values。

 you can compute the sine function or the cosine or the tangent or the arcs r and so forth。

 and it's done in radiance but there's functions to convert back and forth to degrees there's the exponential function there's the log function which is a natural log there's a to the B power。

 there's round to the nearest integer there's random which gives a random numbers between0 in one but less than1。

 there's square root， we're going to actually talk about how we might implement the square root function later on and you can get the value of E and pi。

These kinds of functions， we can write programs that do lots of familiar computations from science and math。

And one thing that you can do is if you have a calculator。

 throw it away because you don't need it because you can write Java programs to do anything that your calculator does。

 and the advantage is the Java program can be long and complex。

 but it's a text file and also you can save it and use it again quite easily the same way that you save all kinds of other information on your computer。

So with the match library， we're already past the calculator， so here's just an example。

 so if you want to。Have a polynomial x square plus b x plus C。

 Then you can find the roots using the quadratic equation。

 So what are we going to do Well we're going to take the coefficients from the command line。

 that's the B and C， and these are of type double So they're going to be strings but we don't want them to be integers。

 we want them to be of type double because we're going to do things like take square root So we use double de parse double whereas before we use integer de parse in。

So we take the two things from the command line and put them in B and C and then we do the quadratic formula so first we compute b squared minus 4 c。

 so that's going to be a value of type double that we call discriminant and we write the expression B squared minus 4c a lot of times when we're computing with doubles and we have constants integer constants even we write 4。

0 rather than just 4 just to make sure that it's a double literal。Then we take the square root。

 that's D， and then there's two roots， minus b plus the discriment over 2 and minus b minus the discriment over two。

 and then we write them out and these things are double but again， if you're writing it out。

 Java automatically converts it to a string。呃。So roots of x squared minus3 x plus 2 are 2 and1。

 that factors into x minus 2 x minus1。As you remember from grade school。

So this is x squared minus x minus1 and one of the roots of that is the golden ratio。

 x squared plus x plus 1 roots are complex so we get not a number and if we type something that's not a double。

 I want to know the roots of x squared plus x minus hello。That's not a number。

 And I get a runtime error saying it's not a number。And if I leave off an argument。

 well it's not always the case that the error message is crystal clear telling you what it means in this case what it means is I wanted two arguments you just gave me one you're certain to get this error message people get it all the time not really remembering how many arguments they're supposed to type and well later on learn exactly what it means but a lot of times you're going to get error messages you don't know what they mean you're going to have to study your program to figure it out not to be talking about that in a lot more detail later on。

So that's a program that computes with floating point numbers and again any math equation now you've got the tools to do the calculation。

 any kind of calculation that you might want。Maybe a little less familiar is the Boolean data type。

 It's kind of simple， but it's also kind of fundamental。 and we'll use it kind of immediately。

 And then it plays a more profound role in computing later on。 for Boolean。

 the values are true and false。 The literals are true and false。 There's only two。

 And the operations are the logical operations and or and not。

The operators that we use for these operations are double ampersand for and double bar or an exclamation point for not。

And they are completely defined by these tables。 So if a is true， not a is false， if A is false。

 not a is true。 and for the other operations， this table gives all four possibilities for A and B。

A and B is true when they're both true， false otherwise。

 A or B is true if either one of them is true and false only when they're both false。

There's other boolean operations， for example， there's an operation called X or and that one actually any boolean operation can be expressed in terms of and or not and won't quite take the time to go through this but for any boolean function in this case。

 exclusive or is false if they're both the same and true if they're different and this little table is a proof that that operation is expressed by that Boolean expression and we'll get back to this and see other examples later on right now we just want to use really simple examples with and a not and so forth。

And we're going to use these to control the logic of a program or the flow from one statement to another。

 they play bullolean operations play an important role in that and we'll see that very soon。So。

For each type of data， there's fundamental operations built into Java that allow us to compare their values。

 and that's very important in lots of computations。So these operations。

 the operas are two expressions of the same type and the result is a boolean so usually so it's either true or false so just for example there's the equal equal comparison operator so you've got two ins and two like two equal equal to that's true two equal equal3 is false and then there's not equal which is the opposite it's less than less than or equal greater than greater than or equal so we can take values from a data type two values of the same type and then we can perform these kinds of operations on them all our types the way they're compared is natural。

 the numbers is natural order the numbers on the string is a legraph or alphabetic order。

So this is an example of when you might want to use these types of operations in a program like maybe you want to test in the program that for the quadratic equation that the discriminant was positive so you might want to know is B squared minus 4AC positive or not negative or not。

 so you just say is it greater than or equal to zero now you have to be a little careful because double values are approximations but something like thats probably going to be all right。

So you want to know you've got a variable year that gives a year and you want to know if that's the beginning of a century。

 so you test whether when you divide it by 100， you get a remainder of0 or not。And that's again。

 these things have a value of true or false， and then in a minute we're going to see how we might compute with those true and false values。

Or you have a variable month that's between1 and 12 and then you can say okay iss a greater than equal to 1 in less than or equal to 12 just to check that it's legal。

There'Lo of times when we want to check the values of things and get a true or false result。

 that's what comparison operators do for us。So here's an example of computing with Booleions。

Is a given year， a leap year。Well， so the rule is that it's。If it's definitely a leap year。

 if it's divisible by 400 or if it's a divisible by4 but not 100 so that's the rule so here's how to write a program to implement that rule again we've got leap year Java it's got it name leap year it's got a mean and now we write our program so we're going to take the year from the command line it's going to be an integer value we're going to compute a boolean value that says true if it's a leap year false otherwise so is it divisible by4 but not 100 well we'll say year divided by4 the remainder when you divide by4 is that equal to 0 it's either true or false so we want to be divisible by4 so if it's4 that'll be true and year remainder when you use divided by 100 not equal to zero so this whole expression now sets leap year to true if it's divisible by4 but not by 100。

And false otherwise。And then， well if it's avisible by 400， then we also want to make it true。

 so we say it's either that thing or if the remainder when we divide by 400 is equal to0。呃。

So then we print out that value， and that's going to be either true or false。 So now we can。

 now we have a program that we can keep on our computer and any time we can type and say， okay。

 it's 2016 a loop leap here and it says yes，1993， no，1900， no， but 2000， yes。

An example of computing with Boolean data types。

![](img/0bc56fd1e53959c7803720a38517ddb0_2.png)

![](img/0bc56fd1e53959c7803720a38517ddb0_3.png)