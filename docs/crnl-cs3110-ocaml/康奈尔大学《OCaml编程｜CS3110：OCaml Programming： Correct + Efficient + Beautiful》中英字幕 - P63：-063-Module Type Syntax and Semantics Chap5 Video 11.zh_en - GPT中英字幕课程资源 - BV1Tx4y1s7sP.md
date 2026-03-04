# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P63：-063-Module Type Syntax and Semantics Chap5 Video 11.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we have some understanding of module types。

 let's take a closer look at their syntax and semantics。

A module type is written with the keywords module type， followed by a name。

Then equals the keyword sG， some specifications， and the keyword end。Curiously。

 the name does not have to be capitalized for a module type unlike a module。

 but it usually is for consistency。There is an older idiom that you might still see out there in some code bases。

 which is all caps and underscores。 We tend not to use that anymore。

 it just kind of looks like your code is yelling at you and no one likes to be yelled at。

Module underscore type， underscore Da。The specifications that are part of a module type can include。

Vels， as we've seen so far， you can specify types， exceptions。

 and you can even nest other module types in them as well。Now that we have module types。

 we can go back and update our syntax for module definitions。

 you can put in a colon and a module type there。You can also， by the way。

 instead of writing colon in the module type， actually put the module type annotation in on thestruct。

 this kind of makes it look like a standard type annotation that we've known that you could put in all along as well。

As for semantics， well， there's no evaluation semantics because module types are just types。

 there's nothing to evaluate with them。But there is a type checking semantics for it。

If you give a module a type。😡，Then the type checker is going to do a couple things。 First。

 it's going to do signature matching。 It's going to make sure that everything specified in the module type sig is defined in that module mod。

 And furthermore， it has to be defined with the right type。And second。

 the type checker is going to ensure encapsulation。

Only what is specified in SIG can be accessed from outside of MauD。

We say that the module is sealed at that signature。😡。

It's sealed in the sense that you can't get anything else out of the module。

 only those names that have been identified in the signature。😡，So for signature matching。

 every name specified in SIG must be defined in MoD。

And the types in Mau must be the same as those in Sig。



![](img/396a7f6fc4c0148148f8f23658026a18_1.png)

Or they're allowed to be more general。Suppose we had a module type that specified there had to be a function F whose type was int arrow int。

Then we could implement that with a module， which really does have a function of that type。

We could also implement it with a function with a more general time。

Here I've implemented moduleule IDF with the identitydent function。

 which of course normally is happy to work on any type of value， the identity function works on bos。

 it works on ins， it works on floats。Here I'm allowed to use it to implement IntF。😡。

Because I could never get a type error by using a more general function type。😡。

That identity function is perfectly happy to take in an integer and return an integer as IF requires。

The fact that it could also take in other types of values。Doesn't matter here。

 it suffices that it's able to take it an int and return an int。😡。

So you see the type of F here is really alpha arrow alpha。

 but that suffices to implement a function of type int arrow int。

 because we can instantiate alpha with int。

![](img/396a7f6fc4c0148148f8f23658026a18_3.png)

![](img/396a7f6fc4c0148148f8f23658026a18_4.png)