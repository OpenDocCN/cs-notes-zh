# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p21 20_10_let-expressions -BV1bw4m1D7MM_p21-

Okay in this segment， I want to start talking about the last big language feature we need before we sort of understand the basics of M programming。

 and that's the ability to introduce local variables， which we're going to do with lead expressions。

 but before we get to that， let's just review kind of where we are and how far we've come we've seen a bunch of different types of data。

 ints and bos， we've seen tus built out of smaller things， lists。

 we've seen functions that take arguments and return a result we understand how environments work at least at top level and with function bindings and for each of functions and tus and lists。

 we know how to build them using some language construct we know how to use them either to call a function or to access the pieces of either a tuple or a list。

 So what we don't know how to do yet is how to define local variables。

To put variables inside of a function that can only be used in that function。

 And that can be very good style and extremely convenient。 And in this segment。

 we're going to go over the basics of how to do that。 And then in the next segment。

 we're going to show that you can use the exact same language construct。

 to put one function inside of another， which is a great idea that unfortunately。

 you see and far too too few programming languages。 Then the segment after that。

 will'll discuss efficiency and learn that there are situations where you really need local variables and let bindings in order to write a reasonable algorithm。

😊，But through all of this， the thing I'm going to emphasize is that all we're going to add to our language is a single new kind of expression。

 it's just an expression， we don't have to add anything else to our language and it's going to capture all the ideas we need for all of these purposes。

So without further ado， let me show you the expression， I'll give you the formal definition first。

 and then we'll write some code， just some silly examples showing how to use it。

So the syntax of a let expression involves three keywords， let in and end。

 and between the let and the in， you can put any number of bindings， so these aren't expressions。

 they're actually bindings just like we've been putting at the top level of our program we're now going to be able to put those in any let expression and since they're an expression。

 that means let expressions are expressions， that means we have a way to put bindings pretty much anywhere in our program and then between in and end。

 we have one more expression， which I'll call the body of the let expression。

Let me talk about the evaluation ruless next and we'll come back to type checking。

 the idea is that we're just going to evaluate each binding in order just like we would if those bindings were at the top level of the program。

 so each binding will be usable in the bindings that follow it but not the earlier ones。

And then they're all usable in the body。 So we evaluate each binding in order， then the body E。

 and the result of that body E will be the result of the entire lead expression。

 and those bindings will have no effect on any environment except in this lead expression。

So given those evaluation rules， type checking works pretty much the same way。

 we're going to type check each binding in order， use that new static environment for type checking the other bindings will allow all those bindings to be used in type checking the body。

 and then the type of the body E will be the type of the entire lead expression。

OkaySo that's really all there is to it。 How about we write some code to sort of make this concrete and understand it。

 I don't claim that this code is going do anything。

 So how about I just call it silly1 since I'll write a couple functions here。

 just write a little function that takes an int。 And here as we know。

 this function body can be any expression E How about I make it a let expression so it's going to have this form let in n and I'm going to have some bindings here。

 How about v x equals if z greater than0， So when I go to evaluate this expression here or type check it。

 I can use all the bindings that are already in the environment here。

 So Z or anything that came earlier in the file would be fine。



![](img/7cca0972fb7452d3e28cb8e6fc2a36a4_1.png)

And then when I do another binding， say v Y， I can use X， I can use Z。

 I can use whatever expression I want。 And so that seems like a perfectly reasonable expression for binding to y。

 So when we evaluate this will'll evaluate x to the result of if z greater than0 than z L 34。

 then we'll evaluate Y to be x plus z plus9。 and then our body can use X and y and z and everything else so it could just be something like this。

 And now the type of this whole thing。 silly want to end up having type int arrow int because its body has type int。

 and that's because the body of the lead expression has type int and that's because the body is an if expression and both the then branch and the L branch have type int。

Allright， so that's an example of a lead expression。 Let's do one more。

 So let's again have our function body be a lead expression。

 But now let's really emphasize that we can put lead expressions anywhere。

 So what if this body where an addition expressions。

 So we know addition is going to take two arguments。 And these could be lead expressions if we want。

 You can put a lead expression anywhere， you can put an expression。

 So what if I did something like v x equal2 in x plus one。😊，And。How's that going to work， Well。

 I'm going to be in an environment where x is bound to1， but then when I evaluate this。

 I'll create an inner environment where this X shadows the outer X。

So x will be two when I go to evaluate this body， so x plus one will be3。

 and this entire lead expression will evaluate to3。

 The outer x will simply be irrelevant because I shadowed it。

 All What if I had a different lead expression over here where I had x plus2 in y plus one Well now there's no shadowing So this x in this x plus2 is going to refer to this outer one。

 So I'll get three here。 y will be bound to3 and so this body will be 4。

 notice that the lead expression over here。 only affect the bindings and expression in that lead expression。

 That x is completely irrelevant over here on the right where I have a different lead expression and the x refers to whichever one is in the environment when I go to evaluate this lead expression So x will be one there All So we can try this out real quickly。

 let's try lead expressions do sml and if I want to run call silly2 just pass zero argument。

Pas it a unit value there。 and I get 7， which is what I expected。 Allright。

 so that's lead expressions。 As you can see， I'm really emphasizing that they're just expressions。

 but they do introduce a really new thing for us。 and that is this idea of scope of when is a binding in a particular environment。

 Where in the program can we use that binding。 When we only had top levelvel bindings。

 we said that a binding was in the environment for the rest of the file unless it was shadowed。



![](img/7cca0972fb7452d3e28cb8e6fc2a36a4_3.png)

But now with these lead expressions， when we have bindings there。

 they're in scope for the later bindings and the body of that lead expression and nowhere else。

 So it really does give us a powerful idea of local variables。 But anyway we have an expression。

 we can introduce a local scope with a lead expression to introduce bindings for just there。

 And other than that， we haven't added anything new to our language。

 We're reusing the whole idea of bindings and type checking and evaluation rules like we did at top level。

 We just are now doing it in a local way where it only affects that lead expression and nothing outside of it。

So that's your basic introduction of lead expressions。

 And now we're going to use the idea in the next couple segments to do some additional important things。



![](img/7cca0972fb7452d3e28cb8e6fc2a36a4_5.png)