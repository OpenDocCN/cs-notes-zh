# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P4：3_模块1 1 2 对象.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/134ba66fa459917ed2fc95b8ad654d00_1.png)

🎼う。🎼Yeah。

![](img/134ba66fa459917ed2fc95b8ad654d00_3.png)

So go language is object oriented， but let's say weekly object oriented。

 so what I mean by that is that it implements objects。

 but maybe they have fewer features than you would see in another object oriented language like Python or Java or C++ something like that。

So we're going to go through， I'm just going to summarize what object oriented languages are。

 what object directed programming is very briefly， just so I can highlight some of the differences in G implementation。

😊，So object Oed programming is really for code organization。In my mind is for code organizations。

 so you organize your code by encapsulating your code。

 you group together data and functions that are related to each other。

So this is essentially what a type is right so and what object going to programming lets you do is essentially create a user defined type one that's specific for whatever application it is that you're building right so typical type you have antigentegers floats that sort of thing those are generic right you can use those in any kind of program but when you're making a specific application you might like to have a type that is specific to that application domain and you can create that object going to program allows you to create that so if you think about a type。

 your standard type like an antigenteger。😊，Each integer it has data， right， the number。

 the value of the number， and then it has functions， functions that you can apply to the data。

 so you can apply addition， subtraction， multiplication， that sort of thing。

 So a type has data and has set of functions that you can apply to the data。

 So object joint programming is the same idea。 You creating types， but they are more complicated。

 they can be more complicated and they are specific to your application。😡，As an example。

You might have， let's say you're making an application and it's going to do geometry。

 some kind of geometric operations in three dimensions。

So many of the functions that you're going to work that you're going to write are going to operate on points。

 right you're going to have this idea of points because you're doing 3D geometry。

And each point is going to have some data associated with it， specifically x and y and z coordinates。

 maybe you want to put other data in there， but at least you're going to have that x， Y。

 z coordinates because in 3D Also points are going to have a set of functions。

 a set of functions that you can use to operate on points， So distance from origin。

 distance to origin maybe every point has a distance to its origin。

 you can have a function that computes that quadrant， it tells you what quadrant。

 maybe it returns what quadrant the point is in something like this。

 there are a lot of functions that you can imagine that work on points。

So if I think about this idea of points， I got a bunch of data that I want all related together。

 so I want the x and the y and the z variables for a particular point。

 I want them to be somehow associated together。 Also。

 I'd like these functions that operate on points to be associated with that too。😡。

So in typical object oriented languages， you have this idea of a class。

And if now I should know right now go does not use this term class okay but I bring it up because it's used in other object directed languages and so people might be familiar with this idea。

 So this class it defines it may I make a point class and the class defines all the data that would be inside a point。

 So x and Y and Z， maybe they're all floating point， values， something like that。

 and the class would define all the functions that you would have that are associated with points。

 distance to origin， quadrant and so on。😡，So that would be the class and then an object is an instantiation of the class。

 so I can make my point class， but then I might have many different actual points with actual data values inside。

 so if I have a triangle right I've got three points with three sets of x and y and Z values so I might have this point class that's sort of a general template of what a point should have。

 but then the point objects my three point objects will have actual values for x and y and z and so on。

So that's the idea， that's the terminology that you normally see use。

 classes and objects which are instances of that class。So different languages have this Java。

 it's very popular， Java， Python， C++ and so on。Now go。We don't use this term class。 Instead。

 they usestructs。 Nowstructs actually， this goes back to C and probably before that。

 But the idea of a struct is a struct is just just the data。

 So the different types of data that you want to associate together。

 So like with our point class you'd have a pointstruct and it would have an x and a y is z。

 maybe they're all three floating points right So just the data related together。

 but also you can associate methods or functions with those structs。

 So the struct ends up being like what you would call a class and a normal object oriented language。

 So you got these structs that have some data， some fields of data associated with them plus some methods that you want to find。

😊，Now， Go's implementation ofstructs is simplified compared to traditional implementation of classes。

 so you don't have inheritance， you don't have constructors， and you don't have generics。

 none of those。Now this one can argue makes it easier to code also makes it efficient to run。

 so it typically runs faster， but it can make it easier to code unless you like those features now if you like inheritance and generics and constructors。

 then you can see this as a disadvantage， but go is different than it has objects but is different than traditional object oriented implementation and's sort of a leaner object oriented implementation。



![](img/134ba66fa459917ed2fc95b8ad654d00_5.png)