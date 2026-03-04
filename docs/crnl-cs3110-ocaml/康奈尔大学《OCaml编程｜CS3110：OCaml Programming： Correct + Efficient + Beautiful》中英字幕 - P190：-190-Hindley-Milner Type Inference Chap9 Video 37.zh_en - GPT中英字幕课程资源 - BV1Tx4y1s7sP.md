# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P190：-190-Hindley-Milner Type Inference Chap9 Video 37.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've learned how to do type checking for OCMl， but in that case。

 the programmer wrote down type annotations and the compiler or interpreter checked them。

What if the programmer leaves them off as we're allowed to do in OCl？

Then we have the problem of inferring or reconstructing those missing types。

Ocael and related languages use an algorithm that was developed by Hindley and Milner back in the 60s and 70s for type inference。

 They actually discovered it independently， so it's often attributed to both of them under the name Hiinley Milner type inference。

 or just HM。HM is in some ways more of a family of related algorithms than one specific algorithm。

 but they all share this in common。They never infer the wrong type for a program。😡。

They almost never need the programmer's help to find the types。

 in fact in small enough fragments of a language they don't need the programmer's help at all。

 in the whole big language of Oaml there are some corners of it where it can't perfectly do type inference and does need your help。

😡，And more， the algorithm usually runs in linear time。

 you've probably never had to wait very long for OKMm to infer the type of your program。

 that's because for most programs it's really quite efficient。😡。

Robin Milner won the T Award in part for his development of this type inference algorithm。

 He got the award in 1991 for ML， the first language to include polymorphic type inference。

So how do you infer types mentally？Well， as you've learned OCel and learned the syntax of the language。

 you've also implicitly along the way learned to infer types as well。😡。

And really that was true in Java and maybe even Python too。

 as a programmer you learn to look at a program and figure out what the types are because no language forces you to write down the type of every single sub expressionpression in it。

😡，So how would you infer the type of this program， let Gx equal 5 plus x？Maybe pause for a second。

 I'm sure you already know what its tight is， but think about。

 do some introspection about how you figured that out。Well， as I look at this program。

 the first thing I notice is the plus sign。😡，That plus is going to take two ins as input in Ocal。

So from that， I know something about the operarans on either side of it， the5 and the X。 Now，5。

 obviously to me is an int。But I learned from where X and plus are showing up。

 that X must also be an int。So where x shows up in relation to that plus sign puts a constraint on the type of x。

 and that constraint is that it must be an int。Now。

 what about the type of the entire expression 5 plus x Well as I look at that。

 I know that the plus operation is guaranteed to produce an int as output。

 so now I know a constraint a fact about the expression on the right hand side of equals。😡。

This function G must output an int。Well now I know both the input and output types of a function because I've inferred that x must be an int。

 and I've inferred that 5 plus x must be an int。So G therefore must be a function that takes an int and returns an int。

Now that's a lot of words to say what your brain at this point can do very quickly。

The challenge next is for us to turn that into an algorithm that a computer can do。

So how does Hndley Milner infer types？Here's the big picture view of it。

It processes each top level definition in order。😡，So if you're working in Utop。

 think of that as meaning each phrase that you type in and in with a double semicolon gets fully type inferred before moving on to the next one。

😡，If you're working in a dot ML file， it means each definition。

 each let definition in that file in particular， gets processed in order。😡。

So that's one of the main reasons that OKML doesn't let you use later definitions inside of earlier ones unless of course you make them mutually recursive。

 which then means they'll both be type inferred at the same time。So for each definition。

 HM is going to collect a system of constraints， so think of this in the sense of like an algebraic system of equations like you learn to solve in high school math。

These are equations， though， not on numbers， but on types， equalalities that must hold between types。

Then after collecting that entire set of equations， that set of constraints。HM is going to solve it。

 similarly to how you might have learned Gaussian elimination to solve sets of equations in algebra。

HM type inference will solve that set of equations and thereby infer the type of the expression that is being defined。

 We're going to need a little language to demonstrate HM type inference for。

Simple is actually too simple to use as an example language because with simple。

 you can actually infer all the types without even needing to use something as fancy as HM type inference you literally can just basically guess and check what the types have to be in。

😊，So to do something a little more complicated， let's take simple and add the Lambda calculus to it。

Now， at the same time， I'm also going to remove let expressions from the language。

It surprisingly turns out that they're the trickiest part of type inference。

So we're going to leave those out for now and come back and add them in again to the end what that leaves us with is this language。



![](img/50e8e47dcdf66802927e1c69a9051771_1.png)

An expression can be either a name。😡，Now this is a new syntactic class。

 I'm introducing it to generalize both identifiers and binary operators。😡。

So a name n can be either a variable identifier X， or it can be a binary operator。

 but now I'm going to write those as prefix functions rather than infix operators。



![](img/50e8e47dcdf66802927e1c69a9051771_3.png)

Really， all I'm doing here is de sugaruging what OKMl lets us do with Infi operators so that I can treat operators and functions uniformly in this language。

😡，After names， we have integer constantss， Boolean constantss， and if expressions。

 those are all the same as in simple。

![](img/50e8e47dcdf66802927e1c69a9051771_5.png)

And we have the Lambda calculus， anonymous functions and function application that's as usual。



![](img/50e8e47dcdf66802927e1c69a9051771_7.png)

The language of types here is that a type can either be a type variable。

 so I'll write single quote and then a variable identifier like x to indicate a type variable。😡。



![](img/50e8e47dcdf66802927e1c69a9051771_9.png)

Or a type can be int or bo， or a function type， T1arrow T2 for any two types， T1 and T2。



![](img/50e8e47dcdf66802927e1c69a9051771_11.png)

This little language will be good enough to explore most of the interesting issues in HM type inference without overwhelmingness at first。

😡。

![](img/50e8e47dcdf66802927e1c69a9051771_13.png)