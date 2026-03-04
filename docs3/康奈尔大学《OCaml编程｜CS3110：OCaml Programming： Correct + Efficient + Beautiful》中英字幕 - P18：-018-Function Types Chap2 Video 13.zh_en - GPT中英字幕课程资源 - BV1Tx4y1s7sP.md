# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P18：-018-Function Types Chap2 Video 13.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've explored the syntax and dynamic semantics that is the evaluation rules of functions。

 let's take a closer look at the static semantics of functions， which is their type checking rules。

A function type is written with an arrow type T arrow U is the type of a function that takes an input of type T and returns an output of type U。

😡，Likewise， if you had a function that took in two arguments。

 type T1 arrow T2 arrow U would be that functions type， it takes in an input of type T1。

 takes in another input of type T2 and returns an output of type U。

So the last type at the end of all of those arrows is always the output type of the function and all of the types that come before that in that chain of arrows are the inputs。

 You could have functions that take in any number of inputs this way。

So notice there's a kind of dual purpose going on in the language here for the arrow syntax。

 it's being used for function types。And it's also being used for function values when we use the anonymous function keyword fun。

And that's kind of nice because it's showing us that these two things are really closely related。

 They're both a notion of transformation of transforming an input or maybe multiple inputs into an output。

 The type checking rule for anonymous function expressions。😊。

Essentially says that the type of the function is just the type of its arguments arrow the type of its output。

So writing that down mathematically， if each of the arguments can be given the type。

 if x1 can be given the type T1 all the way up through XN， given the type T in。

And if the body of the anonymous function， E has a type U。

Then the anonymous function expression Fund x1 through XNarrowOE has the type T1，arrow， et ceter。

arrow TN，arrowO U。Let's look at a couple examples of this to make it a little more concrete Let's try type checking the anonymous function that increments its argument。



![](img/ff1ec8fce4f497d93fdbf687d34c45c3_1.png)

So if we have fun X，arrow x plus1。Of course， we know that the programmer could have written in a type annotation on X。

 saying that x has to be an integer。OAMl figures that out through type inference if the program relieves it out。

Let's put aside the problem of type inference for now。 you and I can， of course。

 with our human brains， look at the right hand side of that function expression and say， well。

 if x is being added together with one with the plus operator， then X must be an integer。 Of course。

 That's approximately how Ocamel figures it out， too。Okay。

 so if we knew that X had type int to begin with here。

What would the right hand side of the function expression be， X plus 1 would have type int。

 of course， because it's the result of taking that plus operator and applying it to two integers。

So we know that X has type end。 We know that x plus one has type end。 Therefore。

 the entire anonymous function expression， Fun X， arrow X plus 1。Would have type int， arrow， int。

 the argument type， arrow， the output type。Let's try this on a multi argument function。

Suppose we had fun X， Y， arrow X plus Y。Well， if X had type int and if y had type int， theyre again。

 kind of hypothetical statements being provided by the type inference part of Ocal。

 you and I can figure them out with our human brains once more by saying will the plus operator has type intarrow into O int。

 So X and Y have got to be ints for this whole thing to work out。

And if the body expression X plus Y has a type， what type would that have to be。

 It would have to be int again because of the plus operator there。

 Then the entire anonymous of function expression。Would have the type。Int， arrow， int， arrow， int。

We figured that out by postulating what the argument types must be。

 figuring out what the body type was， and using those together to form the type of the anonymous function expression function application is very similar。



![](img/ff1ec8fce4f497d93fdbf687d34c45c3_3.png)

If the function being applied， which of course could be an expression E0。

If that expression E0 has a type T1。Arow dot， dot， dot，arrow T N， arrow U。

 which is to say it has arguments of types1 through N， T1 through T N， and an output type of U。

And if furthermore。Each of the argument expressions has the right type。

 according to the functions type。Then the result of the entire function application will be the output type of the function。



![](img/ff1ec8fce4f497d93fdbf687d34c45c3_5.png)

![](img/ff1ec8fce4f497d93fdbf687d34c45c3_6.png)