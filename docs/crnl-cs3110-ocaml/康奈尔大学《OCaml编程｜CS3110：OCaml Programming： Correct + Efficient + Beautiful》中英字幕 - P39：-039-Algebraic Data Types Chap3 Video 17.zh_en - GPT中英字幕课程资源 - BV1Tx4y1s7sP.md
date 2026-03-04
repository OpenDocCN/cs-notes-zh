# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P39：-039-Algebraic Data Types Chap3 Video 17.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Algebraic data types are really one of the mainstays of functional programming。Honestly。

 we've been using them already， but we're going to take a closer look at what they are right now。

Let's try to model some data from the real world。Think about whether you would use a record or a variant for each of these kinds of data。

Suppose you wanted to model coins。And furthermore， that coins could be as an American currency。

 Penny， nickel， Dme， or quarter。So what would make more sense for that， a record or a variant？

While we're trying to model something that could be one of several things。

 a coin is either a penny or a nickel or a dime or a quarter， and a variant lets us do that。

It lets us have those four different constructors and any value of that type would be exactly one of them。

What about a student？So a student could have a name and an ID name。

Would you use a record or a variant for that？Well， I would use a record。

Because I know that when I model that student， I want to have two pieces of data for that student。😡。

And I could have a record with those two fields， a field for the student's name。

 and a field for the student's ID number。Of course。

 if I tried to use a variant and had one constructor for name and one constructor for ID number。

 then I'd never be able to have those two pieces of data simultaneously。

I need to have both of them at the same time that leads me to choose record。

What about desserts so I once took the hotel school cooking class here at Cornell and in it I learned that a properly formed dessert needs to have a sauce。

 a creamy component and a crunchy component。So would I use a record or a variant to model a dessert？

Well， I would use a record。Because I know it needs to have each of those three components has to have all three of them。

 not just exactly one。A word to pay attention to is the conjunction that is used when we describe the data。

When we use the conjunction or。

![](img/f0ef16359872d04ef4f3efd0b6bd8d21_1.png)

Were led to look for variance。When we use the conjunction and。We're led to use records。



![](img/f0ef16359872d04ef4f3efd0b6bd8d21_3.png)

We can think of this as a distinction between。One of types and each of types。

What I mean by that is that records and tus are examples of each of types in that every value of a record or a tuple。

Has each of the values of some other components。For example。

 a record representing students has each of a name and an ID number。

These are also called product types， the notion is that of a Cartesian product。For example。

 you could have a Cartesian product of floats with floats and that could represent points in the Cartesian plane。

Or you could take Cartesian products of any two types that you want， strings and ins。

 so you've got a string and an int， there's that word and again。

Variarianants are known as one of types， because any value of a variant is one of。

A set of constructors。A shape has to be exactly one of a circle or a rectangle or a point。

Sometimes these are called some types。Now， the reason why mathematically they're called some types is maybe less familiar than Cartesian products。

The notion is that we are taking the union。Of two sets。Whereas with Cartesian product。

 we were taking the product of two sets。So here's an example。

We could have a variant type that represents a value that is either a string or an int。😡。

So it has two constructors， capital string， and capital int。

 each of which carries along a value of the appropriate type。

And now any value of type string underscore or underscore int is going to be exactly one of either a string or an int。

 so in a sense we've taken the union of those two sets， those two types。



![](img/f0ef16359872d04ef4f3efd0b6bd8d21_5.png)

![](img/f0ef16359872d04ef4f3efd0b6bd8d21_6.png)

But there's a little more going on to it than that。

 It's not just a union because the constructor name or the tag。

Tells us which set that the value came from。In the case of the type we're looking at here。

 you can kind of tell already which set it came from because there are two different sets。

 strings are not the same thing as ins。But suppose we wanted to create something that is either a blue or a pink int。

 right now， we're taking sort of two copies of the set of all integers。And you need them together。

Keeping track of which copy， as it were the value came from。

 it was either the blue integers or the pink integers。 that's what the tag tells us。

This is known in mathematics as a tagged union， and it's written as a usual set union but with a little plus sign inside of it。

So that's what variants are， they are tagged unions because they tell us exactly which one of the sets of how you came from。

And that's why they are sometimes known as some types， because union is a lot like some。

When you have both sums and products， that might remind you of algebra。Indeed。

 variants are also known as algebraic data types。Because they allow the combination of sums and products。

 they allow the combination of each of types and one of types。

The abbreviation for algebraic data type is ADT， which is a little unfortunate because that has a name clash with the abbreviation for abstract data types。

 as you will have learned in 20110 So be careful ADT might mean either one of those things from now on。

 you'll figure it out from context。

![](img/f0ef16359872d04ef4f3efd0b6bd8d21_8.png)