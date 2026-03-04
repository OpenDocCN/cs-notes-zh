# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p51 50_01_introduction-to-first-class-functions -BV1bw4m1D7MM_p51-

This segment of the course is all about first class functions， and in this first segment。

 I just want to give you a little bit of a sense of what that means。

 introduce a little bit of the terminology and actually start by taking a bit of a step back and asking what is this functional programming stuff that we've been doing and will continue to do through this segment。

So functional programming can mean a few different things to me。

 it really is about two concepts that are actually separate。

 but for historical reasons and somewhat good reasons。

 they've been combined together and we call the result functional programming。

 The first we've already studied quite a bit。 And that's avoiding mutation。

 not using assignment statements， not having data that lives in locations that can change。

 We've done a lot of that。 we're going to continue to do that。

 And we'll even see cases where we don't want that where actually mutable state is a reasonable programming idio。

 And then the second thing which is what this section of the course is all about is using functions as values passing them around in that sort of thing and I'll give you a sense very soon of what we mean by that。

Now there are a few other things that people often think of when they think of functional programming and these are not necessarily bad aspects of the definition of functional programming if you will。

 first of all， functional programming often uses lots of recursion and recursive data structures like lists and trees and we've seen that in our sections so far you also often see a programming style or even a syntax that's much more mathematical。

 the definitions we write down tend to look much more like the mathematicalmatics that we studied in school than other styles of programming tend to。

There is something that some functional programming languages such as Haskell have。

 which is laziness， this is actually a technical term， I'm not saying that anyone is being lazy。

 we will study laziness briefly later in the course。

 many courses would emphasize it more than we're going to that's just a matter of perspective and then there's a lot of definitions to make a whole lot less sense sometimes people think that oh if it's not object oriented programming or it's not C。

 maybe it's functional programming and that's pretty sloppy thinking and we'd like to avoid that one。

Now once we know what functional programming is， then what is a functional language and I've taken to decide that this really doesn't make a whole lot of sense as a yes or no question。

 a functional language is one in which you can do functional programming but I think I can do functional programming as described here in pretty much any language it just might be more or less convenient and might be more or less the default。

 so to me a functional language is just one where functional programming is the easy natural conventional way to do it。

 all the libraries are generally written in a functional style and so on。All right。

 so if this course is not entirely about functional programming， it's broader than that。

 but if that's a big focus and if a big part of functional programming is using functions as values。

 it's about time we really got started on that part of the course。

So a first class function is like in ML， like in many programming languages。

 a situation where functions can appear and be used wherever we use other values。

 wherever you use numbers or lists or strings or trees， you could also put functions there。

 so functions can be arguments to other functions， they can be results of functions。

 they can be a part of a tuple， you can bind them to variables。

 you can put them in data type constructors and so on。



![](img/edcdf60936f9d2e82d8d9709cd818e83_1.png)

So we're not going to do a lot of code in this introductory segment。

 But I thought I would show you just a little bit of how this really can be done in M。 And in fact。

 not using any features that we didn't already have just onces we didn't think to use this way。

 So here's two functions。 One doubles its argument。 The other increments its argument。

 That's not very interesting。 But now let's make a tuple。 We're in the tuple。

 this is gonna be a triple。 So I'm gonna have three parts。 What if in the first part。

 I put the function double。 So I'm not calling the function。 I'm not passing in an argument。

 I'm just going to look double up in the environment。

 get a function back and put that in the first part of my tuple。 Similarlyly in the second part。

 how I put increment。 And just to contrast the difference between a function and the result of calling the function。

 What if here I put double of increment of 7。 Now， this third position is going to call increment with 7。

 get back 8 called double with that and get 16。 Allright。And then we could even down here in Val 18。

 we could get out using our old hash1 operator that we used before we learn pattern matching hash one of a tuple。

 that is going to give back the double function。 And then we could call it with9。

 So this is an example of first class functions because I'm putting functions in a tuple。

 And then later I'm pulling them out and using them。 So let's make sure I got this All right。😊。

And show you what the Reple shows for this， this will be useful to us this over here。And sure enough。

 it says as we're used to， double is a function of type in int。

 increment is a function of type arrowent int。 This a tuple。 very interesting。

 It is a triple where the first position hold some function。

 the repple never actually prints out functions other than to write fn。 The second part is fn。

 and the third part is 16 just as I promised and the type is a triple in int star in int star int and finally。

 18 where we pulled out the double function from the tuple and then called it with 9 did actually give us 18 right so that's a little sense of the sort of thing we'll be doing and later in the section after we learn the semantics and how to use first class functions will see useful idioms。

 the code there was obviously on purpose just a little bit silly。😊。



![](img/edcdf60936f9d2e82d8d9709cd818e83_3.png)

Okay， so to finish up， let me just give you a couple more terms。

 the most common use of first class functions is not putting them in tuples and pulling them out of topples。

 although that can be very useful， the most common is to pass a function as an argument to another function or as the result of another function。

 And when you're doing that。 The function that takes or returns other functions is called a higher order function。

 It's just the term。And high order functions are a powerful。

 powerful idiom for factoring out common computations， and we'll see examples in upcoming segments。

One other term we'll get to later in the section is a function closure。

 A function closure is a function that uses bindings from outside the function definition。 Now。

 how can it do that， if it's not an argument or a local variable。

 How can it use something the same way we always have an M。

 things that are already in the environment can be used by a function。😊。

Once you have first class functions functions being passed around and returned。

 the way this environment interacts with the functions is more sophisticated。

 more interesting and much more powerful， we're going to put that off just a bit and talk about function closures later so to me。

 first class functions means functions you can pass around and put anywhere you want function closures means functions that can use things in the environment。

 not just arguments and local variables and these are technically separate concepts。

 but because functional languages always support both and they're often used together。

 use both features together， these terms are often confused with each other。

 and even though it's an important conceptual distinction。

 I'm not going to harp on the definitions in the terminology because they're so commonly used incorrectly and it's frankly not that big of a deal。

So that's our introduction， hopefully you're excited about the idea of first class functions and we'll start learning how to use them for actual interesting code even in the very next segment。

😊。

![](img/edcdf60936f9d2e82d8d9709cd818e83_5.png)