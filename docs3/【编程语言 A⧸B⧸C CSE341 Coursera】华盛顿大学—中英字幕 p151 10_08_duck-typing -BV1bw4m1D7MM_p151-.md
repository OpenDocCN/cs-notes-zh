# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p151 10_08_duck-typing -BV1bw4m1D7MM_p151-

Any study of object ored programming in a dynamically typed language would not be complete without studying the topic of what has become known as duck typing。

 So first， let me explain the name。 There's this funny expression in English that if it walks like a duck and it quacks like a duck。

 it's a duck。

![](img/e6aefa4186530c6f160a67ce56d75846_1.png)

A more precise saying would say if it quacks like a duck and walks like a duck。

 it's not relevant for our present purposes that it may not actually be a duck。

So that's the idea and in programming， what comes up is when you're writing some method。

 you might be thinking， oh， I need to take in an instance of some class food。

But really all you're doing is taking in some argument and calling methods on it。

 and if there's something out there that walks like a foo and quacks like a foo。

 but is not actually an instance of foo， then in a dynamically typed language。

 your code might still work and it might be appropriate for clients to pass something that is not actually a foo。

So when you embraceduct typing like this， you really stick with not assuming anything about objects except that they have certain methods and you can call them with certain arguments and you avoid language features which Ruby does have for things like testing are you actually a foo。

 what is your class are you an instance of a particular class so people generally argue that by embracing duct typing。

 you get more code reuse。😡，And you get more code reuse because you're taking a very OOP approach that the only thing you care about an object is what messages you can send it。

Now the minus of this is that it makes almost no code equivalent。

 It makes it impossible to replace one set of method calls with a different one because then things that used to look like a duck don't look like a duck anymore。

 that for numbers， x plus x and x times 2 are equivalent in Ruby。

 but if people are passing in things that are not numbers and that handle x plus x and x times 2 in different ways that making this sort of change is going to have find or confusing behavior。

 so callers in a duck typing world can end up assuming too much about how a method is implemented and you end up losing all the abstraction advantages that are so important in programming。

So let me show an example of this just here on the slide。



![](img/e6aefa4186530c6f160a67ce56d75846_3.png)

Suppose there was some class out there for points in the plane。

 so they had an X coordinate and a Y coordinate。And suppose we wanted to be able to mirror a point。

 So we want to update a point to change its x coordinate to its negation while leaving its y coordinate alone。

 This is what happens when you look at a mirror， if you will。

 And OP style would actually make a mirror update method be a method of the point class。

 But for sake of example， suppose instead， I just have this helper method that takes in a point。

And changes it。 So it's point do x equals point do x times minus-1。 That's the idea。

 So the natural thought is the look of this code and say oh well。

 it takes a point object and negates the x value updating it in place。

 but that's not actually what this does。 a slightly closer look at it would say。

 well it takes anything that has getter and setter methods for an at x instance variable and then replaces at x with at x times -1。

So if I had something that was not an instance of point， but had these getter and set methods。

 then this code would presumably do something useful on such an object。Now。

 hopefully at least some of you are saying， but wait Dan， that's still too restrictive。

 you're assuming that the getter and setter methods are actually updating an x instance variable。

 and that's part of the object implementation that's none of our business as the writers a mirror update so a more precise description yet would say that mirror update can take anything with methods x equal and X and what it does is it calls the x equal method with the result of multiplying the result of calling the X method by minus1。

Whether these things are accessing an instance variable。

 whether the x equal method even updates anything， it would be poor style to have a method called x equal that didn't actually update something。

 but nothing would stop you。 And if you have any such object。

 you can pass it to mirror update and something presumably useful will happen。😡。

And just to finish the story， this is still not quite correct because you're assuming in this description that the star method is actually performing multiplication。

 there's no reason that needs to be the case， I would say that the trueduct typing interpretation of this code is that it takes anything with a method x equal and a method X where the result of calling the x method where we say point x is an object that has a star method that can take minus1。

And then what this method does is it sends the result of calling x the star message minus1 and sends that result to the x equal message。

 That isduct typing。 It's often convenient。 What I don't like about it is now our documentation for the method is essentially the entire body of the method。

 We've hidden absolutely nothing from clients。 We've told them exactly what we're going to do so they could have just used the code themselves rather than relying on our method。

😡。

![](img/e6aefa4186530c6f160a67ce56d75846_5.png)

So the plus of this is that maybe Mi update is now useful for classes we did not anticipate that by writing the code without checking that we take an instance of point。

 other clients can reuse our code in ways that may be useful to them。

But the minus is that if someone does reuse our code with an instance of an object that relies on things like there being a times message or x equal being a setter or whatnot。

 then we can't replace code like point x times -1 with something like  point dot x。

 This works if we know we have a point that returns a number and because we know negation and multiplying by -1 is the same on numbers。

 But that's assuming things that duck typing does not get to assume。So for examples like this。

 like mirror update， I think duct taping is actually often poor style that there may be things that are not quite points that are appropriate to pass the mirror update。

 but I want to want to pass some arbitrary thing that just happens to have methods x and x equal。

But there are good examples ofduct typing， I have to admit。

 if you take simple helper functions admittedly this is a little too simple to be compelling。

 like something that doubles its argument by calling x plus x。

 it's rather nice that given this I could pass in a number because those things have plus messages。

 I could pass in a string and then I would concatenate a string with itself。

 or I could even take my own code like the myration objects I defined in earlier segments and because I defined plus I could then pass those objects to this double function and have them get doubled even if the original writer of this code was thinking numbers or was thinking I can support anything that has a plus message and that's sort of the pluses and in my opinion。

 minuses of duck typing and how it's relevant to object oriented programming in a dynamically typed language。



![](img/e6aefa4186530c6f160a67ce56d75846_7.png)