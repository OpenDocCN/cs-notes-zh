# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p83 82_05_polymorphic-examples -BV1bw4m1D7MM_p83-

In this segment， we'll continue with our type inference examples。

 but the examples here are all going to produce functions with polymorphic types。

 So the key ideas will start the same。 We're still going to collect all the facts we need for type checking。

 we're still going to use these facts to constrain the type of the function。

 the only difference is we'll end up with so few constraints that some of the arguments or the result can still be any type。

 and we'll use that information to then figure out a polymorphic type where some of the arguments or results might need to be the same type as some others or not。

 and then we'll have inferred polymorphic functions。

 So even though this is conceptually perhaps more difficult。

 it's actually easier because we have fewer constraints to deal with。



![](img/9988096c7e2b8d90c6be4f7973a3d9f1_1.png)

So let's just go over here and let's start with an example that's a lot like the sum of the elements in an int list that we saw in the previous segment。

 this is just computing the length of a list， but we sort of know what the answer is going to be。

 we know that length on a list can work for any type of list so it will'll be building up to showing alpha list arrow int。

So we start， as we always do， by saying that length better have type T1arrow T2 because it's a function and its argument better have the argument type。

Everything continues， as we did in the previous segment。

 we noticed that since we're pattern matching with x and x is prime。

 there's going to have to be some type T3 such that x has type T3 and x is prime as type T3 list just from that pattern since we are pattern matching against x's。

 that means that T1， the type of x' is has the equal T3 list。

We know from trying to return 0 as a possible result of our function that T2 has the equal int。

And let's see that's about it。One has type B， so we can have that be an argument to plus length is our recursive call。

 so we better call it with a T1， well x is prime has type T3 list and we already know that T1 equals T3 list。

 so we have no more constraints， everything type checks with what I've already written down。

Therefore。Putting all those constraints together， I end up with T3 list arrow int。

And there's nothing more to say。😡，There is no constraint on what T3。

 the type of the list elements of x' is need to be。 After all， we never used any of the elements。

 the contents of them here。 we could have written an underscore there instead of x。

So when we have a type like this and it cannot be further constrained。

 what we do is we take all these T's that are in there。 there's one in this case。

 and we replace them consistently with type variables。 So in this example， we take that T3。

 we replace it with the first letter， the alphabet quote a arrow int。

 and that is the type we would give we would say for all types quote a or alpha we can take in a list of quote a's and return an int。

And that's how you type check the length function， the Q a simply falls out from having no reason to prefer any particular type for the list elements。

So now let's do a more sophisticated example， it's a less interesting function in terms of actually wanting to use it for something。

 but it's just function F that takes in three arguments X， Y and Z and either returns X， Y。

z or Y Xz now you can look at this function and say， well。

 if true it's always going to return this one but the type checker follows the type checking rules and the type checking rules for a conditional is that we don't know which branch might be returned。

So let's just go through this and pretend we're the computer doing type inferences。 So F。

 I'm going to go ahead and say takes a T1 star T3， arrow T4。 I could write out more steps and say。

 well， it takes one argument， and then that argument's a pattern。 But if you just look at this。

 it's going to have to take in some triple and return some fourth type T4。

 And certainly X1 has type T1。 Y has type T 2 and Z has type T3。Okay。So at this point。

 we don't need to type check this true。 That is type pool， just like if then else needs。

 And we just notice that we're either going to return this or we're going to return this。 So T 4。

Either has to have type T1 star T2， star T3， or T4 has to have T2 star T1 star T3， and in fact。

 those both have to be true。Because the type checker doesn't know which of these might happen。

 So the result type has to be the type of x comma Y comma Z and the type of y comma X comma Z。

 So both these constraints have to be true。 And the only way。

Those can both be true is if T1 equals T2。Right，There's no other way for T4 to equal both of those things。

 So that's enough。 Then we'll have the same thing in both cases。 So if we put it all together。

The type of F。Is T1 star T1 star T3， because I know T1 equals T2。

 And I want to write down the type for F that incorporates all the constraints I havearrow， not T 4。

 but what T4 has the equal after all my constraints。 So T1 star T1 star T 3。

 And what this type says is that x and Y have to have the same type。

 Z can have a possibly different type。So there are no other constraints。

 There's no reason to prefer anything in particular between for T 1 or T3 and T1 and T3 do not have to be the same type。

 So at this point， we replace these capital T's with quote A and quote B consistently。

 so we can pick any letters of the alphabet， but every T1 has to be quote a。And every T3 has to be。

 quote B。And so we end up with this type， which is actually correct。

You can call this with any types of arguments you want， but X and Y have to have the same type。

 Z can have the same type， or it can have a different type。

 This is exactly the sort of polymorphic type we've seen before。

 Now we just know how to infer it and how type inference works for this sort of thing。Okay。

 so that's our second example。 We saw two type variables here。

 Let's do a final example that's actually going have three and is actually one of our favorite functions。

 So here is function composition。 We've written this before。 It takes in two function arguments。

 F of G and returns a function that takes in an x and returns F of G of X and type inference will work for this just fine。

😊，Compposed takes a pair for its argument。 So let's call that T 1 star T2， arrow T 3。

 where F has type T 1 and G has type T 2。 All right。

 Now we just need to look at this function body and see that it is a。Anonymous function。

 So we have this argument X， and it's going to have to take in some T 4 and the body being a function。

Has type T4， arrow T5。TheThe body of compose here has to be some function。

 and that has equal the return type of compose。 So let's say that T 3 has the equal do。 Okay。

 for some T 4 and T 5。So from G being past X， which has type T 4， we actually know that T 2。

 which is G。 G has to be a function。 If you're gonna write G space X is going to have to be a function。

 So G is type T 2。 T 2 is going have to equal T 4arrow T 6 for some T 6。 T 4 is the type of X。Okay。

 so now from F being passed。The result of G， T1， the type of F is also going to have to equal some function。

 and it's going to be have to equal function。 That's the return type of G as its argument。

 So T 6 and then some T 7， say， for what it returns for some T7。Okay so we've looked at everything。

 but now we have to say from F being the body of the anonymous function。 Remember。

 our anonymous function was this T4arrow T5 from a call to F being the body of that function。

 We know that T7， the return type of F has to be equal to T5。

 the return type of that anonymous function， because we call F。 and then that's our result。

So now we can just put it all together， so put it all together。We end up with the T1。

 the type of F has to B T 6arrow T 5， because we just decided T 7 equals T 5。

 T 2 was this T 4 arrow T 6。 That was the type of G And T 3， which is our result for compose。 Well。

 that's T 4 arrow T 5。And if we actually put this all together， just for T1 star T2 arrow T3 here。

 what we end up with is T6，arrow T5。Star。T 4，arrow T 6。Arow， T 4， arrow， T 5。

 And that's actually a good type for compose。 Take in something。 G takes a T 4， returns a T 6。

 F takes a T 6， returns a T 5。 So the whole thing takes in a T 4 and returns a T 5。

But we always replace these capital T consistently with type variables。 When we're all done。

 there are no additional constraints here。 So let's just use a。 We'll just go left to right。

 So the first thing we see is T 6。 So we'll use a for that。 second thing we see is T 5。

 So we'll use B for that。 Third thing we see is T 4。 So we'll use C for that。

 And now when we see another T 6， we have to use a again。And when we see another T4。

 we have to use C again。 and when we see a T5， we have to use B again。

And except for these unnecessary parentheses over here on the right。

 this is exactly what the repple will print out as the type for compose。

 it's something that takes in a function from quote a to quote B and a function from quote C to quote A and returns a function from quote C to quote B so the process was exactly the same as for the other examples。

 gather all your facts constrain everything as much as you can。

 and then replace any unconstrained types consistently with type variables。

 and that is our examples of type inference。

![](img/9988096c7e2b8d90c6be4f7973a3d9f1_3.png)