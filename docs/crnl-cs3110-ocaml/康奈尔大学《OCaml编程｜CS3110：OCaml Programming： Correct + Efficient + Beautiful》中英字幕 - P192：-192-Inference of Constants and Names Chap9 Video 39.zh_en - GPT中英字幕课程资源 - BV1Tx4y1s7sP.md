# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P192：-192-Inference of Constants and Names Chap9 Video 39.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's start defining the type inference relation and we'll start with the two simplest cases which are constants。

An integer constant I always has type int and generates no constraints。 Likewise。

 a Boolean constant B is always of type pool and generates no constraints。

 Let's write down a couple examples。

![](img/4e1dbe77f976450978f2f7abb59f8992_1.png)

In the empty environment。The integer constant 31，10。Has type int。And it generates no constraints。

 the empty set。So I'm using empty curly braces here to represent both the empty environment and the empty set of constraints。

 hopefully that makes sense， both of them are sets。

 it's just the environment is a set of bindings and constraints are a set of type equations。Likewise。

 in the empty environment， the integer constant true has type pool and generates no constraints that must hold on types。



![](img/4e1dbe77f976450978f2f7abb59f8992_3.png)

Type inference for names is almost as easy。In a static environment end。

N has whatever type the environment says it has， and that generates no constraints。Now， of course。

 if that name was not present in the environment， that is there was no binding for that name。

Then type checking or type inference rather， would fail at this point because there is no value corresponding to N of N。

😡。

![](img/4e1dbe77f976450978f2f7abb59f8992_5.png)

Suppose we have the static environment that binds X to type int。In that environment。

 we go to infer the type of X。😡，That produces int as the type。Along with no constraints。Now。

 suppose we were in the empty environment and we tried to type check X。

X is not bound in that environment。 So this would fail。 There is no type that can be inferred here。

 Perhaps we could write a slash through the turns style if we were working on pencil and paper here。

 I'll just put a slash in the middle to say we can't inferred。 Finally。

 suppose we wanted to type check the plus operator。How do we infer the type for it。Well。

 every program that we write in this language ought to start off in an initial static environment that has the types for the3 Booleion operators。

So that environment should always have in it that plus is of type int， arrow， int， arrow int。

And that should also have the same type for multiplication and a similar type for less than or equal to。

Given that， the name rule tells us how to infer the type of plus。 just look it up in the environment。

 so that must have type int， arrow int。Arrow int。And generate no constraints。



![](img/4e1dbe77f976450978f2f7abb59f8992_7.png)

Here are the three bindings then that should be in every initial static environment when we start off doing type inference for this language plus n times and less than or equal to should always be bound to these types。



![](img/4e1dbe77f976450978f2f7abb59f8992_9.png)