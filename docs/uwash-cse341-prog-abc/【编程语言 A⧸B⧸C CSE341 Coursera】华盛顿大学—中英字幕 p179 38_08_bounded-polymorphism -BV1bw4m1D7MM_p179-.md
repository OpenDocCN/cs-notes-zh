# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p179 38_08_bounded-polymorphism -BV1bw4m1D7MM_p179-

So now that I've shown you in the previous segment how generics and subtyping are good for different things。

 let me show you an example of where they're good together and you actually need to combine them in order to get what you want。



![](img/4144c33ad9fc74113572c289f946b573_1.png)

So to be clear， programming languages can have generics and subtyping Java does C sharpp does C++ with templates kind of does。

 so sure you can have them。 What's interesting is when you can use them together rather than sometimes use one and sometimes use the other and the way we're going to combine them is called bounded polymorphism and let us it will let us write things like any type T1 that is a subtype of T2 So in ML quote a just says any type T1。

In Java， we have subtype relationships like this is a subtype of that。

 It's only when we combine them， which we can do in Java and C sharpharp that we say things like any type T1。

 that is a subtype of T2。 So not any type， only those that meet that constraint。

 And I want to show you an example of where that's exactly the sort of thing you need to write to write the code that you want to in a statically typed situation。



![](img/4144c33ad9fc74113572c289f946b573_3.png)

So my example is a method that takes a list of points。

 a list is a collection just like lists in ML or racket。And it takes a circle。

 a circle is something that has a center and a radius。And what it returns is a new list of points。

 which is the subset of the points in the argument that lie within the circle right so you have a bunch of points。

 you have a circle filter out all the ones that are outside the circle that's all you want to do and a nice method signature and Java case you're not familiar with Java let me walk you through this would look like this。

 It's a method called in circle， it's return type is list of points。

 the same thing we would write point list and Ml list of points just use these angle brackets in this way takes three arguments it takes the list of points that it's going to iterate through it takes a point which is the center of the circle and it takes basically a real a double that is the radius and that's the signature we want and you know just to be clear at the bottom here I have an implementation in Java it's only a few lines long you don't have to understand how it works。

 but it basically creates a new empty collection that has a little loop that goes through all the points in this argument。

PS， and if it's inside the circle， it adds it to the result。

 And I'm actually assuming that my points have certain methods that make this work。 But the point is。

 it's a simple function， a simple method to write。

![](img/4144c33ad9fc74113572c289f946b573_5.png)

I would like to use in circle with this list of color points I have。 That makes sense。

 I have a list of color points。 I have some circle。 I would like the output list。

 That's all the color points that are in the circle。

Java and CSharp rightly disallow reusing the function， the method I've already defined。The reason is。

That list of color point is not a subtype of list of point。

 And the reason is the same reason we studied when we learned about depth subtyping and how it's not sound。

In circlecle， as written here， would work just fine。 if you pass it a list of color points。

 it would give back a list of color points， but we don't know that。

 The type checker doesn't know that。 for all we know。

 the list of points that en circlecle returns include some new points that it makes up。You know。

 it just makes up point you know， with an x coordinate of two and a y coordinate of4。

 And since that point that it makes up does not have a color field。

 it would be unsound to assume that everything in the output is a color point just if everything in the input is a color point。

And second， we have the same mutation problem we saw with depth subtyping that we cannot trust in circle not to add things to our input list that are points and not color points。

 And that would be the same problem。 So we cannot just use subtyping in this situation。



![](img/4144c33ad9fc74113572c289f946b573_7.png)

So if we can't use subtyping， can we use generics？So suppose we replaced the method signature up here。

 which is what we have been using with a generic one。Now， if we said。

 well in circle takes a list of T for any type T， think of T as quote a。Then it returns a list of T。

 Now， this would be great for colors because I could instantiate T with points and then have a list of points。

 get back a list of points。 I could instantiate with color point， have a list of color point。

 get back list of color point。😊，There's just one problem。If this is the type。

 then I can in Sanchiate T with anything， so I can San with integer or string or fo。

 and that means that the body of this method cannot possibly do the right thing What in circle is supposed to be doing is treating the list as a list of point things and checking if they're within some circle。

 if all it knows is that it has the elements are of some unknown type T。

 then it won't be able to call any methods or access any of the state of points and then in circle can't do anything useful so the body of the in circle method will not type check under this type。



![](img/4144c33ad9fc74113572c289f946b573_9.png)

So here is what we want， this is what we' building up to is some sort of bound。

We want to take that polymorphic version， that generic version and say yes， in circle。

 given a list of T's we'll give back a list of T's， but it assumes that T is a subtype of point。

And it assumes that and under that assumption， it can write the body just like I showed you before。

 and now callers are going to have to meet that constraint。

 They're not going to be able to instantiate T with anything。

 but they can instantiate it with any subtype of point， and so they can instantiate it with point。

 they can instantiate it with color point， they could instantiate it with 3D point if that were a subtype of point。

 but they can't instantiate it with non subtypes of point， like string or fo or int or whatever。

So we really are combining two great ideas here。 We're using generics。

 We're using a list of T here and list of T here and those can be any type。

 but we're using subtyping to constrain the generics to make sure that the elements of this list are a subtype of point。

😊，So that's the great idea of bounded polymorphism， hopefully this is a compelling example。

 there are plenty of other examples that come up， and that's all you need to know about it。

 just the high level idea that generics and subtyping can combine in this way。



![](img/4144c33ad9fc74113572c289f946b573_11.png)

For those of you who have programmed in Java I thought I would show you the actual syntax that read on the previous slide with the where this is not Java I just find it easier to explain that way This is the actual syntax you should be able to type this in and have it work I need this extra thing over on the left to say that T is a subtype of point。

 use the keyword extends for that， you need these angle brackets to introduce that this is actually a generic method。



![](img/4144c33ad9fc74113572c289f946b573_13.png)

![](img/4144c33ad9fc74113572c289f946b573_14.png)

And I should also admit one other thing about Java is that all the nice things about generics like it doesn't matter what T is the method will behave the same way and all that sort of stuff doesn't actually hold in Java for backwards compatibility reasons as well as making it easy to implement the way Java is typically implemented。

 there's always a way to use casts to get around the static checking with generics that if you use generics and you wish to put weird typecasts in weird places you'll be able to get strange results that you wouldn't get under a more conventional treatment of generics。

 that's okay Java is under a lot of design constraints and used properly。

 you can use both generics and Java as well as combining them with subtyping to get bounded polymorphism to enforce some pretty nice invaris and use them for nice methods like the incircle method that you see here。



![](img/4144c33ad9fc74113572c289f946b573_16.png)