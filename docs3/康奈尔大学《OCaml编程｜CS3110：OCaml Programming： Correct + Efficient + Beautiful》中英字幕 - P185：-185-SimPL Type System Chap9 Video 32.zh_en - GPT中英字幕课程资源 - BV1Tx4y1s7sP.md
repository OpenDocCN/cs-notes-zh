# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P185：-185-SimPL Type System Chap9 Video 32.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We're going to do this in the context of a language that I'll call typed simple。😡。

So this is almost exactly the same language as simple， it's just I've added in some types。

 so now I'm going to require the programmer to write down colon T in a let binding。😡。

So there's no type inference here， you must write down the type。

 willll return to type inference later。There's only two types in this language， int and bo。😡。

Type checking of values and variables is quite easy。😡，No matter what the static environment is。

 let's just call it n of E and V。It's always going to show that an integer constant has type int。😡。

And that a boolean constant has tight bo。Furthermore。

The type of a variable name is going to be whatever it's bound to in that environment。😡，Of course。

 if the variable name is not bound in the environment， then there's no way to look it up。

 so we'd never be able to conclude that a variable has a type if that variable is not present in the static。

😡，Binary operators all look about the same for each of them。

 we recurse into the sub expressionpressions E1 and E2。😡。

Determine that each of those has type int in the static environment。And given that。

 we're able to conclude for each of the binary operators。That it has the appropriate type。

 So for plus in times， that's going to be int。For less or equal to， it'll be blue。

Now notice that we recurse into each of those sub expressionpressions using the same static environment each time it's not changing。

And the reason for that is whatever evaluation occurs of E1 on the left hand side of plus。

 it's not going to change the variables that are in scope when we go to evaluate the right hand side of that plus。

 the subexpression E2。So variables are contained within scopes that way syntactically。

 and that's a good thing for an if expression， we need to check three preconditions here。

 three premises of this rule， we need to check that E1 has type bo E2 has type T for whatever that type T might be。

 and that E3 has that same type T。So the entire if expression then has type T because that's the type of the branches。

 Finally， let expressions are the most complicated because they actually have a type showing up inside of them syntactically。

So if we have let x colon t1 equal E1。

![](img/8626b4af8211aa6e169fdc84d196ac2c_1.png)

Then the first thing we need to do is type check E1 in that same static environment。

To make sure that it really does have type T1， so we're double checking here that the programmer got it right when they wrote down that type annotation。



![](img/8626b4af8211aa6e169fdc84d196ac2c_3.png)

![](img/8626b4af8211aa6e169fdc84d196ac2c_4.png)

Then we recurse into E2 and type check there。😡，But in a new static environment。

 So this is the first time we've changed the environment in all of these rules。

Here we bind X in the static environment。To that type T1 that the programmer specified for。

And in that extended environment， we'll go ahead and type check E2。If it has type T2。

 then that's the type of the entire let expression。



![](img/8626b4af8211aa6e169fdc84d196ac2c_6.png)

So notice， there's a real strong similarity here between the type checking rule for let and the evaluation rule for let in the big step environment semantics。

In both of them， we extend the environment to record information about the identifier。

In type checking， we're just recording the type。In evaluation， we're recording the actual value。

But of course， that type is going to be an approximation or an abstraction of the value。



![](img/8626b4af8211aa6e169fdc84d196ac2c_8.png)