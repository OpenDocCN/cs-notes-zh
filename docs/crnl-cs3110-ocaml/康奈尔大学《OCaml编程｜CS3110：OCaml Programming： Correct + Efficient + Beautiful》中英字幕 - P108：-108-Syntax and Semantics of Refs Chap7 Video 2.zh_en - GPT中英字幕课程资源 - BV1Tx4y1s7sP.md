# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P108：-108-Syntax and Semantics of Refs Chap7 Video 2.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's take a closer look at the syntax and semantics of references。

A reference is created with Ref E Ref is a standard library function to create references。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_1.png)

To evaluate Refi。Ocamo first evaluates E to a V。

![](img/35a43c36d630c9ad43f078c85bbbe0c5_3.png)

Then it allocates a new location in memory。 let's call that location look。

That is where V will be stored。

![](img/35a43c36d630c9ad43f078c85bbbe0c5_5.png)

Ocamll returns that memory location as the result of the function call to Rph。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_7.png)

For type checking， we now have a new type constructor， which is also written Ref。

 so don't confuse these two things RefF is used both for the type and for the function that creates references。

T refF is a type for any T， so you could have an int ref， a string ref reference to a variant type。

 whatever you'd like。Reef E has type T ref。If E has T T。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_9.png)

Locationations are values。But， they are not expressions。

You cannot directly write down a location in an Oaml source file。

 You can't directly write down addresses in memory。 You can't do arithmetic on addresses in memory。

So as I warned you back in the first or second week when I showed you this picture。

 this Venn diagram is not telling the whole truth。For the values we were looking at back then and for the first month of the course。

 values were all expressions。

![](img/35a43c36d630c9ad43f078c85bbbe0c5_11.png)

But now we have values that are not expressions。Location values are not expressions we can directly write down in a program。

So really the truth is the Venn diagram ought to look like this。

 where there are some values that are expressions and some values that are not。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_13.png)

The assignment operator is written E1。Colon equals E2。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_15.png)

To evaluate such an assignment， first evaluate E2 to evaluate V2。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_17.png)

Then evaluate E1。 It must produce a location block。And store V2 in that location。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_19.png)

And as the result of the assignment， return unit。

![](img/35a43c36d630c9ad43f078c85bbbe0c5_21.png)

To type check an assignment。Well， if E2 has type T。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_23.png)

And if E1 has type T ref。Then E1 becomes E2 has type unit。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_25.png)

So notice that type checking maintains the type stored at that reference。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_27.png)

As we've said， the type of a value stored at a memory location may not change。

 So it is appropriate to think of references as pointers to typed locations in memory。

 Let's talk a little bit more about unit。 We've seen it from time to time before。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_29.png)

![](img/35a43c36d630c9ad43f078c85bbbe0c5_30.png)

![](img/35a43c36d630c9ad43f078c85bbbe0c5_31.png)

Unit is a type。And its only value is the unit value written with parentheses。

There are no interesting operations to do on unit because it's the only value of its type。

If you like， you can think of unit by analogy to Booleance。Bool is a type， and it has two values。

 true and false。Unit is a type， and it just happens to have one fewer value than Booleions do。

 It just has one value， and that's unit。The closest analogy in other languages you've used before is probably void。

When you have a procedure in Java or C with no interesting value to return， well。

 its return type is void。You can think of that as just a single value that you can't do anything interesting with。

So this is similar to both print and assert in Ocael。For example， if you do a print string in Ocheml。

 that's a function that takes in a string and returns unit in other languages。

 it might just be a void return type。Similarly， if you assert a Boolean expression that has type unit。

 there's nothing interesting that can happen。

![](img/35a43c36d630c9ad43f078c85bbbe0c5_33.png)

![](img/35a43c36d630c9ad43f078c85bbbe0c5_34.png)

Other than， an exception would get raised if the assertion fails。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_36.png)

The D reference operator is written B E， where E is an expression。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_38.png)

Notice this is not negation。 In many other languages， The exclamation point is Booleian negation。

 Here it's not。 its's de referenceence。

![](img/35a43c36d630c9ad43f078c85bbbe0c5_40.png)

To evaluate a D referenceence， first evaluate E that must produce a location lock and just return the contents of that location。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_42.png)

Type checking， if E has type T ref， then B E has type T。

 The bang operator is essentially getting rid of that Rph。



![](img/35a43c36d630c9ad43f078c85bbbe0c5_44.png)

![](img/35a43c36d630c9ad43f078c85bbbe0c5_45.png)