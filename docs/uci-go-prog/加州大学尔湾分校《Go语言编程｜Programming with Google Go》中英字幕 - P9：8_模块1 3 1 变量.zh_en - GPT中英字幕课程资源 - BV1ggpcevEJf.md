# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P9：8_模块1 3 1 变量.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/fdcea8476ca3e3fa3937ec177e4618c2_1.png)

🎼う。🎼Yeah。So now we're going to start talking a little bit about the go language。

 we'll broach the topic of variables and talk a little bit about those variables are in every high levelvel language and we'll just see how go implements it。

 a lot of this is very similar to what you've seen in other languages。

 some things are a little bit different。So first there's naming every， you need names。

 names for variables， for functions， you need names to refer to things in your code。

So names for variables and things like that， they need to start with a letter。

They can have any number of letters and digits and underscores。 they are k sensitive and go。

 and you can't use keywords。 there's a list of keywords， you can Google these or look them up。

 but if case package all the different keywords of language， you can't use those as the names。

So variables are basically data stored in memory somewhere。

And every variable has to have a name and a type。So all variables have to have a declaration that specifies the name and the type of the variable。

So here's a really simple variable declaration。Just as var x int。

 So var is the key word for a declaration of a variable。 After that I have the name。

 so my name variable is called x， and then after that I have the type var x int， that's it。

 That's a declaration of this variable X says it's an integer。And the machine。

 the compiler needs to know what type of variable it is， what the type is。

 so it knows how much space to allocate what operations to perform and that type of thing。

You can declare many on the same line if you want to， just kinda separated， so var x kind of y int。

 and you can do that as much as you want。So variables have types。

Tpe defines the values that a variable can take and the operations that can be performed on that variable。

 So for instance， common types， basic types， integer， floating point and strengths， integers。

 the data， the variables， the values that they can take are only integral values right they integers and the operations you can perform are integer arithmetic plus minus times that sort of thing。

And there are a set of other ones， we'll talk about them in a little more detail， floating point。

Those the data that they can have， the values that they can have are fractional， decimal values。

And you have a set of operations， arithmetic operations， actually。

 they look superficially the same as the energy operations plus times divide。

 but they may actually be implemented with different hardware right because a floating point division say is significantly more complicated than an energy division。

So there's oftentimes is special hardware just for floating point divide and things like this。

 we don't have to know that as programmers， but the machine has to know which operation a map it to。

Then strings， so strings， they're a sequence of bytes。

Represented in UniIcode and we'll get into that later。But it's a sequence of bytes。

 that's the type of data， the values they can take on。

 And then the operations you can perform on strings。 There are many of them， string comparison。

 string search， you know concatenation， all sorts of operations that you can you can perform on a string。

 But the point is the type specifies these things。 It specifies what data the variable can hold and how big that data can be right is going because you need to know how much space and memory you're going to need to allocate for this the compileilr needs to know that and also what operations are going to be performed on it。

 So what thats for is。😊，Eventually the compiler is going to have to take these operations that you type and go and compile them into machine code instructions for whatever the hardware platform is and those machine code instructions can be different depending on the type so for instance you can easily have an ad for an integer and integer ad machine code instruction which is different than a floating point ad integer division which is different than floating point division and so on So this is why the compiler needs to know the types so it knows how to do the compilation and how to convert it into machine code。



![](img/fdcea8476ca3e3fa3937ec177e4618c2_3.png)