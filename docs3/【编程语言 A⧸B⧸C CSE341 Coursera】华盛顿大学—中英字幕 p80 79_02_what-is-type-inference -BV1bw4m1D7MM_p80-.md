# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p80 79_02_what-is-type-inference -BV1bw4m1D7MM_p80-

As we begin our study of type inference， I want to start by making sure we're as clear as we can be about what type inference is and what problem it's trying to solve。



![](img/05ddd67e4fbd47284292822d2cb5059d_1.png)

So when you have type checking at compile time， which is called static type checking。

 it lets us reject programs before we ever run them。

 and we do this to prevent the possibility of some errors， so statically typed programming languages。

 or languages that have this feature， so you might have some function that does not type check because potentially it might say try to call a number。

 treat a number as a function， we don't actually have to execute the function to get that error。

 we get that error before we ever run our program。Conversely。

 dynamically typed languages do little or perhaps none of that sort of checking。

 so you would have to actually not just call the function but actually get the particular problematic expression to evaluate with variables bound to the right things before you see the potential error。

Now the relative advantages of static and dynamic type checking is a major concept in the course。

 and we're going to study it， but I want to do that after we've used the dynamically typed programming language for a while and racket is one so we'll be in good shape there。

At this point， we've only seen ML， an ML like Java， C， Scala， eta， is statically typed。

 it has this property that certain things don't type check even before we run them。

And what all of these statically typed languages have in common is every variable we introduce is given a type。

 Every binding has some type and for the scope that it's usable。

 it maintains that type and can only hold values of that type。

 So we keep our strings and our bos and our functions and our topples separate。

Now the reason why I'm emphasizing this is that even though ML is statically typed。

 it is implicitly typed ever since the beginning of section 2 or so。

 we have not been writing down the types of any of our variables。

 we never did for Val bindings and only at the beginning of the course when you were using hash1 and hash2。

 did we for arguments to a function。

![](img/05ddd67e4fbd47284292822d2cb5059d_3.png)

So just because ML is implicitly typed， it can sometimes be confusing to remember that it is statically typed in this first function here。

 F， the two variables， F and X both have a type， F we had type int arrow int， x has type int。

 and they're just as statically typed as if this were Java or C where we have to write down the types of all of our variables when we introduce them。

That is why when you have a function like G， we end up with a type error。

 the reason for the type error here is that one of the type checking rules in ML is that the then branch in the else branch of a conditional have to have the same type so that that can be the type of the entire if expression and in this case。

 therefore the return type of G and so when these don't match like a bo here and an int here。

 we get a type error， this is exactly the sort of thing that in a dynamically typed language I would expect to be allowed and depending on the argument to G。

 you either get back a bo or an int so in that sense of static type checking。

 M is more like Java or C and less like Java or Python。



![](img/05ddd67e4fbd47284292822d2cb5059d_5.png)

So what then is the type inference problem？The type inference problem is take a program。

Like we saw in the previous slide and try to give every variable and binding and expression in that program a type such that if you wrote down all those types。

 type checking would succeed， so we need to infer all the types such that the program would type check。

If we cannot do so， if it is impossible to give such types。

 like in that second example where true and x times 2 simply do not have the same type。

 then it's the role of type inference to fail and presumably give some sort of error message。

So in principle you could set it up exactly like this。

 you could have a type inference procedure that wrote down the types for everything and then have a type checker that checked those types in practice and an implementation of a language like SML。

 we often don't separate things out so cleanly， we just have the type inferencer in type checker be the same thing and either your program type checks or it does not。

The last thing I want to emphasize before the next segment， when we get into type inference 4 ML。

 this segment was really about type inference in general and what it is is's the type inference can be easier or difficult or impossible。

 it depends on the type system that you're trying to infer types for。So as two extreme viewpoints。

 if if every program type checks， that's very easy to infer， just say yes， if no program type checks。

 that's also easy to infer just say no， so type inference doesn't get easier or harder necessarily by having a type system that accepts more programs or accepts fewer programs。

 it's not so simple to figure that out。 this is part of the difficulty of language design if you want type inference。

 but the reason why we're going to study M type inference is that it is a bit subtle。

 but it's also extremely elegant， and it may at this point in the course， seem magical。

 we've seen these polymorphic types sort of inferred for us， but through a series of examples。

 I want to convince you that it's actually a fairly elegant and straightforward procedure。



![](img/05ddd67e4fbd47284292822d2cb5059d_7.png)