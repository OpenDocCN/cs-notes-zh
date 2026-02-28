# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p17 17_02_04_数据类型.zh_en -BV18U411U729_p17-

![](img/5eb70202600239835e9b71992094be26_0.png)

At this point， you have seen a variety of types， such as it， point and file resource。

 But what exactly is a type。 A type specifies how data should be represented。

 interpreted and operated on， as well as what operations you can do with it。

 One important rule of computing is that everything is a number。

 If you didn't learn about the everything is a number principle and whatever intro courses brought you here。

 We'll give you some links to videos about it。😊。

![](img/5eb70202600239835e9b71992094be26_2.png)

![](img/5eb70202600239835e9b71992094be26_3.png)

Specifically， this means that everything is stored in the computer's memory as bits， ones， and zeros。

But not all numbers mean the same thing。 Some numbers might mean plain numbers。

 while others might mean letters and others might mean the locations of data and the computer's memory。



![](img/5eb70202600239835e9b71992094be26_5.png)

![](img/5eb70202600239835e9b71992094be26_6.png)

So the type of a value specifies how to interpret those numbers。

It tells Java how to assign meaning to the ones and zeros stored in memory。

The type also specifies what operations you can perform on the data。

 The type tells Java not only what you can do， but how it should be done。

 Let's talk about both of these points in more detail。

 We just said that the type tells Java how to interpret the ones and zeros in memory。

 Let's talk about that a little bit more。 Ha On the left。

 we have the conceptual representation of the program state that we have been working with。



![](img/5eb70202600239835e9b71992094be26_8.png)

There's a box for a variable called X。 On the right。

 We have a bunch of bits from the computer's memory。 The blue ones correspond to X。

 But what do they mean for the value of x。 Well， if x is an int。

 then these bits would mean it has a value of 1234567890。

 We're not going into the details of how you can figure that out here。

 nor do you need to know it for beginning Java programming。

 But if you take a computer organization class， you will learn a lot more about how data is represented。

😊，The point we want to make here is that if x had a different type like float。

 then the same bits would have different meaning。 These same ones and zeros would mean 1228890。25。

And if X were a string， then the bits would be the location in the computer's memory of the actual string object。

 which would have a sequence of characters。😊，Those would also be stored with a bunch of bits。

 That would be interpreted as letters since their type would be char。

We also said that the type tells us what operations we can do and how they' are done。

 Consider this simple bit of code X plus y， is it legal， and if so， what does it do to answer this。

 you need to know the types of both X and Y。

![](img/5eb70202600239835e9b71992094be26_10.png)

If x and y are both ints， then this code is legal and performs in a aristhmetic。

 If x and Y are both strings， then this code is also legal， but performs string concatenation。

 It makes a string with the letters of x first than the letters of y immediately after。

 noticeice that even though the plus operation is legal for two different types。

 we may perform that operation differently for one type than for the other。



![](img/5eb70202600239835e9b71992094be26_12.png)

![](img/5eb70202600239835e9b71992094be26_13.png)

![](img/5eb70202600239835e9b71992094be26_14.png)

![](img/5eb70202600239835e9b71992094be26_15.png)

If x and y are both points， then this code is not legal。While we're talking about types。

 you might be wondering what you do if you need to convert between types。

 the answer is that it depends。

![](img/5eb70202600239835e9b71992094be26_17.png)

For some type conversions， they can happen implicitly if you have't it and you need to convert it to a double precision floating point number。

 the compiler will just automatically insert the conversion for you without complaint。



![](img/5eb70202600239835e9b71992094be26_19.png)

The general rule is that you can use implicit conversion whenever the compiler will consider it safe。



![](img/5eb70202600239835e9b71992094be26_21.png)

Here we are turning3 into 3。0， which is not a problem。

Note that the compiler does not consider the values only the types when deciding if an implicit conversion is okay。

For some type conversions， you can explicitly cast。

 This means that you tell the compiler that even though what you're doing is questionable。

 you are sure you want to do it Here。 We are turning the double 3。14 into an it。

 which will discard the fractional part， leaving us with x equals 3。

 The compiler was to be sure that we meant to do this。

 So we explicitly cast by writing it and parentheses。😊。



![](img/5eb70202600239835e9b71992094be26_23.png)

Other conversions require calling methods to calculate out the converted value， for example。

 if we have the string quote 3， quote and want to turn it into an integer。

 we just can't just directly cast it because the conversion is actually somewhat complicated。Instead。

 we have to call a method like integer dot parsson， which will perform the conversion。

The last thing we will mention about types is that there are two major categories of types in Java。

 primitives and objects。 There are eight primitive types， int， double char，buoan。

 long float bite short。 We primarily use the first four of these Vas of primitive types hold their value directly in their box。

 Priitive types don't have methods so you can't do dot method call on a primitive and they can't be null。

 although each primitive type has an associated raper class。

 which gives you an object to hold that primitive。

![](img/5eb70202600239835e9b71992094be26_25.png)

![](img/5eb70202600239835e9b71992094be26_26.png)

Everything else is an object type。 Some are built into Java， like string。

 Others are part of libraries that you might use， like point or file resource。

 and yet others are classes you will create yourself。 Whenever you make a class。

 The class you make is its own new type。 Unlike primitives。

 the value of variables of object types is an arrow pointing at the object。

 This arrow is called a reference。 You can invoke methods on the object with dot method name and the reference can be null。

 meaning it doesn' not refer to any object。If you dos equals on two objects。

 you're checking to see if the arrows point at exactly the same object。Okay。

 that's the basics of types。 We know it's a lot to absorb at once。

 but you'll get better with these ideas as you practice more Java。



![](img/5eb70202600239835e9b71992094be26_28.png)