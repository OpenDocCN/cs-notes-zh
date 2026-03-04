# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p178 37_07_generics-versus-subtyping -BV1bw4m1D7MM_p178-

In the spirit of showing the complementary benefits of different approaches。

 I want to finish by comparing generics the type variables we saw in ML with subtyping。

 this is right up there in the course with comparing functional decomposition with OO decomposition or static typing versus dynamic typing and what we'll see is the generics and subtyping are simply good at different things。



![](img/1e5a4d2149fd8aceee7e67cda109df7b_1.png)

So let's start with what generics are good for。 We saw this M， so I'll present it in terms of ML。

 They're great for types for functions that combine other functions。 For example。

 we were able to write the compose function in ML and give it this beautiful type that said it can take any function of type quote B arrow quote C and any function of type quote A arrow quote B and will return something that has type quote A arrow quote C and these types can be instantiated with any type in our language。

 it describes precisely what compose is doing。😊，We also saw that generics are great for functions that operate over generic collections。

 that a length function for lists can work for any type of list that the map function takes has type alphaarrow beta and alpha list to beta list it doesn't care what the list elements are provided that the argument type of the function you pass expects that type。

 so in general we saw many other idioms， generics are great when you have code that can work for any type of thing。

 but some of the things have to be the same type， which is when you see quote A or quote B appear multiple times in a type。

 it expresses those type qualities。😊。

![](img/1e5a4d2149fd8aceee7e67cda109df7b_3.png)

So generics are great not just in functional programming that's why Java and C sharpharp also have generics。

 they tend to be a little clumsier to use because there isn't as much type inference。

 they used to be they often are a little more difficult semantically because of how they were added later to the language and how they interact with OOP and objects but nonetheless we even saw in an earlier optional lecture how to code up things as fancy as closures or manual effect of closures in Java and you know it's not so bad and that's why people in Java and C sharpharp do use generic types in all the situations that they're useful in ML where we saw them there Now we didn't study Java you're not responsible for the syntax which no one tends to love。

 but you here is a very simple pair class in ML that even has a swap method and this class works for any type of things that go in the first component。



![](img/1e5a4d2149fd8aceee7e67cda109df7b_5.png)

Second component， which I've called x and Y here。So you do not want to use subtyping in these situations that I've remarked here。

 generics are good at， that if you try to use subtyping for things like a container like a pair。

You just end up using the wrong thing everywhere。 What should the type of the fields of a pair be if you don't have generics。

 If you have to make one type for all pairs， Well， I guess you would have to use something like object。

 and that's what people did in Java back before Java had generics。 and it's really unfortunate。

 It's really using the wrong programming languages tool for the job， which is。

 I guess what you have to do if you don't have the right tool。

 Now we have the right tool in most of our statically typed languages and you should use it。

 What you end up doing is you end up putting on your fields。 you know。

 the components of your pair that it has type object。 And thanks to subtyping。

 that's fine when you right to the fields when you create a pair。 You want to pass in a string。

 no problem string is a subtype of object。 you want to pass in color point， no problem。

 Colpoint is a subtype of object。But then when you get the fields back out and let's be honest。

 the only point of having a pair is to get it out at some point right when you get it back out。

 all you know it is that it has type object and there's nothing you can do with it until you somehow get back that it has some other type and in Java and C sharpp we do that with a downcast this is basically a runtime check that says。

 you know I actually think it's a string And if I'm right。

 please give me back of something of type string and if I'm wrong， raise an exception。

So by having to put these downcasts in， we're not getting static checking。

 those tests could fail and we're paying the runtime cost of actually doing the check and we're making our code harder to read so it's kind of a lose。

 lose lose compared to generics and that's because generics are better for this kind of programming。



![](img/1e5a4d2149fd8aceee7e67cda109df7b_7.png)

Subtyping is great for other things。 There are some great uses of subtyping。

 which is sometimes in fancier verbiage called subtype polymorphism。

 right When you have some code that needs an object that behaves like a fo。

 and you have some object that has more than a food needs。

 you have some subclass of food that has a bunch of extra stuff。😊，No problem。

 It's great to be able to pass that in。 Generics don't have that idea。 Generics are about。

 I work for any type。 This is about saying， no， I need a foo， but if you have a subtype of foo。

 no problem。So where does that come up？😡，As I've shown in this section repeatedly。

 there are many simple examples like something needs point， but you have a color point。

 That color field is no concern to anyone。 subtyping lets us capture that idea and generics don't The other canonical example。

 or I think object ored programming has just been very。

 very successful is in programming graphical user interfaces。

 So you have some super class which has ideas in it。

 there's some super type that says anything of this type has has the ability to be on the screen to respond to mouse clicks to be resized and you know some code can can operate over anything with that type。

 but presumably the things actually being passed have much much more like a color and a default font and you know all sorts of menu bars and all this sort of stuff and subtyping feels like the right thing there that you have some code that only needs some things And then you have some。

😊。

![](img/1e5a4d2149fd8aceee7e67cda109df7b_9.png)

Objects that have some more things。 Subtyping is great for that。

And if you try to do even simple things like points and color points in ML。

 it's frustrating Now nothing's impossible， there's always some way to code it up if you're willing to go through enough workarounds。

 but ML really does not have subtyping So if you try to write in ML this is actual ML code here。

 a distance to the origin function that takes in a record with an X field in the Y field distance origin works just fine。

 but its type is record with x of typere Y of type real to real And if you try to call it with something that has extra fields。

 just doesn't type check the types are not equal M does not have subtypes。

 it would make type inference more complicated and M chose not to add it。

So you cannot call disISA origin with this record。Now what you could do if you're interested in the workaround the same way in Java pregenes。

 there were ways to do collections， they were just cumbersome。

Is you could change just the origin to not take an x colon real y colon real at all。

To actually take anything of type alpha， but make the caller pass in a getter for the x coordinate and a getter for the Y coordinate。

And if you do that， then what you end up with is a function that has type alphaarrow reel and alpha arrow reel and alpha to real make the caller pass in how to get the x coordinate in the Y coordinate and then the actual V here can be anything you want and that's frustrating if most of your code just wants to do this with plain old points it would have to you create a helper function that had the get the right getx and get Y but this code could actually be used with something that was a color point provided we passed in the appropriate getters and yet because of the lack of subtyping and M。

 you would actually have to use different getters and setters for points and for color points you really cannot reuse code and ML for points and color points and that's because subtyping which ML does not have is the right tool for this task。



![](img/1e5a4d2149fd8aceee7e67cda109df7b_11.png)