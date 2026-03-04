# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p81 80_03_ml-type-inference -BV1bw4m1D7MM_p81-

So let's now begin studying how ML does type inference。

 how it figures out the types for all our bindings and the way we're going to do this in the next few segments is via examples。

 so giving the general algorithm implementing this actually showing how it does everything in the whole ML language its a slightly more advanced topic it would just take more time in the class than I wish to spend on it。

 especially if you start supporting things like functions defined in other functions。

 but I think this series of examples which we will do manually will be enough for you to do type inference in your head to look at a piece of ML code and in most cases be able to figure out that type or understand what the ML type checker is telling you and at least appreciate that there is complete step- by step procedure that a computer could implement that infers types for code in ML。

So here are the key steps we're going to see for every example we do。

 This is how M type inference works。 First， it determines types of bindings in order。

 So unless you have mutual recursion in which case it needs to look at all of the things that call each other at the same time as we'll see in a later segment。

 you look at the first binding and further type for it than the next binding and for the type for that and so on。

 And this is why you have to put helper functions before the functions that use them。

 Otherwise you just get a type error because things simply aren't in the environment yet。

 that's the semantics of M。 but we do use those earlier bindings。

 we already know their types before we move on to the next ones。 and we can use that。

Then for each binding， say a Val binding or fund binding。

 we have to figure out the type of that binding。 What we do is we analyze the definition for all necessary facts。

 These are essentially things that are going to constrain the type in some way。 So for example。

 if you see the expression x greater than or equal to0 inside a function that takes a parameter X。

 The x must have type int。 We simply look at the function body in order to figure out the type of the function overall。

We gather all these facts， we figure out what those constraints imply。

 and sometimes they imply things that can't possibly all be true。

 and that's exactly when you get a type error if we try to have in our function body x greater than an equal to zero and x concatenated with the string high。

 then x has to be an int and a string and that's impossible and so you get an error message。Now。

 after we've figured out everything that constraints imply and if it's not a contradiction。

 so the function or variable will type check， sometimes we still have too few constraints。

 things that can still be anything， it doesn't matter what type they have。

 and that's exactly when we get to infer a polymorphic function。

 something with a quote a or a quote B in it， for example。

If you have some function argument that the function body never uses。

 then it can clearly be anything。 doesn't have to be the same as any other type。

 and we can introduce a fresh type variable for that argument。And then there is this last step。

 which was we have to enforce the value restriction。

 and we're going to ignore that until one segment later in the section that's focused just on the value restriction。

Alright， so here's an example in future segments， we're going to do our examples much more step by step。

 very much like the actual algorithm does it。 But to get a sense of how these constraints work。

 let's just keep it high level and do this more like how humans would do it。 So we have two bindings。

 which we're going to do in order。 First， v X equals 42。 That's easy。 you see 42 it as type n。

 So X must have type n。Now we have this function F so we know it's going to have some function type。

 we have to figure out the types of the arguments and the return type。

 so we just look at the function body， we see if y， then something well y must have typepo。

We see Z plus x。 Z must have type int because X is an int。

 And the only thing you can add to an int is an int。 So great， Y is a bull。 Z is an int。

 There's a bunch of other things we have to check。 We have to check that this x really does have an appropriate argument for plus it does。

 We have to check that this 0 has the same type as the type of the expression in the then branch。

 It does。 So we're checking all this as we're doing inference。 And now we're basically done。

 The entire body here can have type int。 So the return type of F will be int。😊。

And then we notice the W over here never got constrained。W can be anything。

 There are no facts that constrain what has to be in any way。 So we know that F must return an int。

 and we know it must take a bo and int and anything you want。 So as that sort of last step。

 we turn that anything you want into a type variable。

 And we give F this type bo star ant star Alpha arrow int。 And if we go over here and try it out。

 we'll see that that's exactly what the type checker says。



![](img/ecff276dca0322bf17eea1de84897fdd_1.png)

As well。

![](img/ecff276dca0322bf17eea1de84897fdd_3.png)

Okay。So one more point I want to make， which is that a central feature of ML type inference is that it does generate these polymorphic expressions。

 things with type variables whenever it can。 This is great for code reuse and for understanding functions。

 it actually tells us in that example that， you know you're never using the argument W。

 which is why I was able to give it this more general type。

But I want to emphasize because it is often confused that type inference and polymorphism with type variables are entirely different concepts。

 You can have a language that has type inference and doesn't have type variables。

 It would make it harder to infer a type for that previous example。

 but they really are separate concepts。 And conversely， you can have languages with type variables。

That do not have type inferences that require programmers to write down all the types。

 And Java in most situations is a pretty good example of that。

 If you want a polymorphic function in Java， you still have to write down all the types of all the arguments of the method that happens to be polymorphic。



![](img/ecff276dca0322bf17eea1de84897fdd_5.png)