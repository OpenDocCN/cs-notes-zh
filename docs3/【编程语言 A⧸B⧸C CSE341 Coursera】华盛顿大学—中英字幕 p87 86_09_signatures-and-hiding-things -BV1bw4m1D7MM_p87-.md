# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p87 86_09_signatures-and-hiding-things -BV1bw4m1D7MM_p87-

In this segment we're going to give types to modules， we'll call those types signatures。

 we'll start with the basic idea and then show the most important thing signatures are used for。

 which is to hide things inside of modules from all the code outside the module。

So I really do want you to think of a signature as a type for a module。

 but the same way we call module structures， we will call their type signatures。

 we're just using different English words， and what a signature indicates about a module is what bindings are defined in there and what type do they have。

So we can define a signature actually separately from any particular module。

 and then we can say that module has the signature。

 So let's see how this works with the example we used in the previous segment。

 So we can define a signature as you see here at the top。 we use the keyword signature。

 It's somewhat conventional to use all capital letters， you don't have to do that。

 say this is the mathlib signature， then sig， which is a keyword， although it's not an English word。

 the types of bindings， just like we've been seeing the reel print out。

 So we would write vowal fact colon int arrow int to say any module with the mathlib signature must have a variable fact of type int arrow int。

 however it's defined， it doesn't matter if it's defined via function binding or a variable binding or any other way。

 The point is that it has such a thing that it defines Similarlyly halfp and doubleubr and then the keyword end。

Now our structure that we defined in the previous segment， my Malib could have this signature。

 It defines all the things that the mathlib signature requires and in such a situation you can write colon angle bracket and the name of the signature in your structure definition between the structure name and the equals and now the structure will only type check if you provide everything at an appropriate type so if this signature had something that the structure did not provide。

 we would get a nice error message from the type checker reminding us that we didn't provide it and similarly。

 if we provided something but not at the correct type。Okay。So。In general， the way we do signatures。

 you just write signature name of your signature equals sig the types for your bindings very much like the repel has been printing things out for us and end and in fact。

 one way you can get start to your signatures is paste in what the repple says a structure has in this signature you can have things for variables。

 types， types and data types and exceptions， we'll see examples of that in a future segment。

 and then when you want to ascribe a signature to a structure you do it like this。

 So the advantage of having this as we will see， so we can define a signature once。

 and then have different structure in our program that all have that signature and we can just reuse the signature name And as I mentioned the module simply won't type check unless it has everything at the right types。

 So if we see that over in our file here， I have the same structure had before。

 but now I have the signature as you've seen from on the slides then my。



![](img/63db7f1d56dfbf017426fa5b10e549f9_1.png)

Structure， and then later here in the file， the same uses。 And if I load all this up in the repple。

We now see that it defined this signature， having done so。

 all it's going to tell us about the structure my mathlib is that it has that signature。

 and then we have Pi in 28 and everything works great。

 So that's the basics of signatures but now let me show you what they're actually good for and that is hiding things the real value of signatures is not to document and write down the type of everything in the module It's to hide implementation details which is the most important strategy for writing correct robust reusable software is to say to the outside world。

 I don't want you using everything defined in this module I want control over what's public and what's private。

 What you can use and what you should not assume even exists。

 So we actually have ways to do this already in ML whether it's with local helper functions or whatnot you know here are three versions of a double function and there are all sorts of reasons why clients of this function have no idea how it's implemented。



![](img/63db7f1d56dfbf017426fa5b10e549f9_3.png)

Doesn't matter whether we write x times 2 or x plus x or x times y where y happens to be equal to 2 where the function is defined。

We also know that if we define helper functions locally。

 no one outside of the let expression where the function is defined even knows that function exists。

What module systems are giving us， in addition to other things is the ability to do this for a sequence of bindings at the top level of the module。

 It would be really convenient to have some functions that are private and some are public In a lot of programming languages。

 we do this by actually marking the functions private or public in M， we do it a little differently。

 it's nice to see something different What we do in M is we just write our module how we want。

 and then in the signature we leave things out。 and anything not in the signature cannot be used outside the module。

 So here's how that works。 if I just go back to my example。

 and I take out one of the bindings from the signature。The module。

 the structure can still have that type。 The module is allowed to have things not in the signature。

 It just has to have everything that is in the signature and whatever is not in the signature cannot be used outside the module。

 It can still be used inside the module。 So let me show that over here with the code。



![](img/63db7f1d56dfbf017426fa5b10e549f9_5.png)

So let me go back up here and let me comment out for my signature， the doubleubr function。

 so no one on the outside can know that Doubr exists。

 but I can still use it inside so I could have a value 8 here that would be a doubleubr of four that will work just fine and then if I go over here and recompile everything。

 I'm actually going to get an error message。And we will see that the error message is on line 27。

 there's an unbound variable， my mathathlib。 Doubr， and indeed there is right here on line 28。

 there is no such thing as my mathlib。 doubleubr outside of the module。

 and so I simply cannot use it。Alright so having fixed that， everything should now work。

 I still have my Val Pi。 I still have my structure， my mathlib that has the signature mathlib。

 so that is hiding for us。 and that is one of the ways we are going to use modules to hide things from the rest of the program。

 We'll see that signatures have even more power that will let us code up neat things in the upcoming segments。



![](img/63db7f1d56dfbf017426fa5b10e549f9_7.png)

![](img/63db7f1d56dfbf017426fa5b10e549f9_8.png)