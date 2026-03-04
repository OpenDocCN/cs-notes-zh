# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p171 30_09_optional-abstract-methods -BV1bw4m1D7MM_p171-

In this segment I want to continue our understanding of OOP concepts by explaining what Java and CSharp call abstract methods and C++ calls pure virtual methods。

 I'll make this segment optional because I think it's a bit too much to understand if you have not seen a statically typed OOP language before。

 but if you have， if you have studied even a little Java C sharpharp or C++ or a similar language。

 I would highly recommend this segment because it explains additional things related to multiple inheritance and interfaces and so on。



![](img/0e93d288e0074c71f3c85d18c6e11566_1.png)

So my goal is to emphasize what a statically typed OOP language should do to support the idea that a superclass wants to require a subclass to override some method and why that would make a good thing to do and why you would want to check it statically。

 I also want to make a nice connection to higher order functions that're complementary but doing surprisingly similar things and I'll even explain why C plus plus doesn't have interfaces because it does have pure virtual methods and multiple inheritance。

 So that was a lot of jargon and buzzwords I will explain it all piece by piece and I think you'll appreciate it。



![](img/0e93d288e0074c71f3c85d18c6e11566_3.png)

So often a class is written in such a way that it expects all of its subclasses to override some method that the purpose of the superclass is to contain a bunch of code and instance variables and things like that that will be useful to lots of different subclasses。

 but there are parts that the superclass doesn't know about this happens a lot in Gois in graphical programs。

 you want to have some superclass that has lots of functionality about moving things around and placing them on the screen and all this sort of stuff。

 but certain things like the size of an object of a graphical thing on your screen。

 there's no sensible default for you wouldn't want size 10 by 10 or 0 by zero。

 so you might force your subclasses to implement some method that determines the size。So in Ruby。

 we could just put that in a comment。Right that the superclass would just say all subclasses better override this method then they can add it and you shouldn't be making instances of the superclass。

 Now this is interesting。 Normally we define classes so that we can make instances of them。

 but sometimes we say， well， it doesn't make sense to make an instance of some class like a the entire purpose of a is to be subclass and then make instances of those subclasses。

 So you see an example here on the slide。 class A define some method M1。 and the body of M1 calls M2。

 and I'm emphasizing here， this is self do M2。 and class A doesn't define M2。

 So if you make an instance of a and call M1， you're going to get a method missing error。

 but we know thanks the dynamic dispatch， this makes perfect sense。

 provided all the subclasses of a that we do make instances of provide a definition of M2。



![](img/0e93d288e0074c71f3c85d18c6e11566_5.png)

So that approach is not going to work in a statically typed OOP language。

 these type checkers want to make sure that method missing errors never occur。

 and so they can't allow code like that， So if they didn't want to allow code like that。

 we could get around this easily enough right a solution would be that in the superclass A。

 we do define M2 and we just make it raise an exception。And then we get past the type checker。

 and we still have a comment saying， you really better overwride M2 because otherwise you're going to get this exception。

We would like to do better。 We would like to have our type checker be more sophisticated and remind programmers by refusing to compile their programs if they forget to override something that they're supposed to。



![](img/0e93d288e0074c71f3c85d18c6e11566_7.png)

And that is the idea behind what Java and C sharpp calls abstract methods and C plus plus calls pure virtual methods。

 The idea is that in the super class， you indicate the type of the method。

The signature of the method， what its argument types are。

 and what its result type is without providing a definition。

And you tell the type checker to reject any program that tries to make an instance of the superclass of class A。

 so now two things happen first， you can't make instances of class A it's a type checking error。

 and second， any subclass either doesn't allow instances of it either。

 or it implements the method in the way you indicated it in the superclass。So in Java。

 this is how you would write it in your superclass A。

 you would indicate that M2 is an abstract method， the keyword abstract， you write its return type。

 you write its argument types and you don't provide a body。

 you just provide a semicolon that says any instance of a that you ever actually create is going to actually be an instance of some subclass in this method will be defined。

And then if you want to make a subclasss， you better provide a definition of that method。

That is the idea。 It catches errors at compile time。

 It communicates to readers of your code that this is this sort of method that subclasses are really supposed to define。

 but it doesn't make your language any more powerful。

 We already had a way to do the runtime behavior here。

 like in this previous version where you raise an exception。

 The only thing we're doing here is getting extra checking at compile time to catch more bugs before we ever run the program。

 And that's a great thing。 I just don't want you to think that abstract methods are anything more than that。

😊。

![](img/0e93d288e0074c71f3c85d18c6e11566_9.png)

So now let me make a connection between abstract methods and higher order functions。

 which on the surface don't seem to have very much to do with each other。 There are both ways。

 however， of passing code to other code。Abstract methods are very OOP。

 They're very related to dynamic dispatch。 They're an OO way to have the subclass give some code to other code in the superclass。

 What's going on in the superclass A， is that M1 is calling M2。

 even though it doesn't know what M2 is。It's up to the subclass to provide a definition of M。

 And then thanks the dynamic dispatch M1 will call M2。

In a very different world from several weeks ago， over in functional programming。

We saw higher order functions where we defined things like this function F that takes another function G as an argument。

And the similarity is F does not know what G is。 G is just some variable that it knows will be bound to some function。

 and so it can call it。Now there's no subclass to provide a definition of G。

 instead there's a caller， the caller to F provides some other code， some other function into it。

 so the same way really the subclass is providing code in OOP in functional program it's the caller providing code and in both situations we use this so that the common code。

 the common functionality is in M1 or F and then subclasses or callers provide the extra information that M1 and F need in order to complete their computation。



![](img/0e93d288e0074c71f3c85d18c6e11566_11.png)

The last thing I wanted to say about abstract methods or pure virtual methods is that they are why C++ doesn't bother to have interfaces。

 because any language that has multiple inheritance and abstract methods doesn't also need interfaces。

 because you have multiple inheritance， what you can do is instead of implementing an interface。

 just subclass a class。And if you subclass a class that has all abstract methods。

 you're not getting any code from that superclass。 They're all abstract。 what C++ calls pure virtual。

 The whole reason that you are subclassing it is to indicate to others that you should be a subtype of that superclass because you are going to implement all of those methods。

And this is exactly what interfaces are for， the reason why we have interfaces is to get around the restriction of only being allowed to have one superclass。

 but if you're allowed multiple superclass， there is no such restriction and that's why in C++ the way you do interface style programming。

 you declare a class with all abstract， pure virtual methods and then you just have other classes subclass that class。

 so you would only expect to see interfaces that we saw in the previous segment in a language that is both statically typed and does not have multiple inheritance and that's why you don't see it in Ruby and you don't see it in C++。



![](img/0e93d288e0074c71f3c85d18c6e11566_13.png)