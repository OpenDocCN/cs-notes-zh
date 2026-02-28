# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P54：20_模块4 2 2 类型断言.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 4 interfaces for abstraction， topic 2。2 type assertions。



![](img/3835f356a37e4a2fb80ff7194d6e14d2_1.png)

So a lot of the point of an interface is to conceal differences between types。

 so if you think about it an interface can hide the differences between two different types。

 it basically highlights the similarities。 so like in this fitting yard implementation。

There's their are rectangles and their triangles。 But from the inside fit yard。

 they're all treated the same right as long as they both satisfy shape 2D。

 I can call S dot area S do perimeter right So what you're doing is what interfaces allow you to do is to treat different types that have some similarity。

 some similar methods， treat them the same So you're hiding differences by using interfaces But sometimes you need to disambigurate sometimes you need to treat different types in different ways。

 so sometimes。Likely in this function， we don't We can just say S side area S do perimeter。

 you treat them exactly the same because they have the same methods。

 but sometimes you do need to differentiate based on the type。

 you need to be able to figure out what is the concrete type right So in this example。

 S since you're just calling areaan perimeter， it doesn't matter exactly what the concrete type is the concrete type could be rectangle。

 it could be triangle doesn't matter either way， areaan perimeter， do what you think。So in this case。

 the concrete type that underlies the interface interface value。

 that doesn't matter okay but there are definitely cases where the concrete type matters in those cases。

 you're going to have to expose those type differences。 so you're gonna have to take this interface。

 which is hiding the differences between the types and peel it apart again and say， okay。

 actually this is really a rectangle， this is really a triangle so。

Situations like that might be a graphics program so I got my graphics program。

 which I've used many times。 but in my graphics program this time I want to write a method called write a function called draw shape and it should draw any shape。

 So I want to be able to pass it as an argument， any two dimensional shape。

 So I declare it sort of the top line I'm shown right there。 Fununk draw shape。 It takes a shape 2 d。

 That's the type of its argument， shape 2 D。 So it can take any two dimensional shape as an argument。

 So that's good right I've used my interface to generalize and to hide the difference differences between the types。

 rectangle triangle circle doesn't matter for passing it as an argument to draw shape anyway。😊。

Now inside draw shape， though。In this case， I'm going to have to disambiguate。

 I'm gonna have to determine this S。 iss it a rectangle。 Is it a triangle。 What is it。

 Because maybe in the underlying API， there's some kind of drawing functions that I'm using in this API right and the underlying drawing functions。

 they actually are specific to the type of the shape being drawn So for instance。

 maybe the underlying API gives me a draw rectangle draw rec and then another draw triangle and a draw circle and so on。

 which is not uncommon in these drawing APIs So you got draw rectangle， draw triangle， draw circle。

 all those Now these API functions， my draw shape is gonna to have to call these right when it wants to draw rectangle is gonna have to call draw rectangle or draw triangle to draw triangle。

 and these underlying API functions， they take they don't take just any shape。

 they don't take shape 2 d draw rec only takes rectangles。

 draw triangle only takes triangles and so on。 So this is the case。

Where I want to use my interface so that I can so my draw shape can take any argument。

 any type of reasonable shape， But inside my draw shape， I'm going to have to differentiate。

 I'm going to say， look， if you're a rectangle， call draw。

 if your triangle call draw triangle and so on。 So in this case， inside draw shape。

 I'm going to have to determine the concrete type that S is based on that the shape is based on。

So for that I use what's called a type assertion so type assertions can be used to disambiguate between the different concrete types that actually satisfy a particular interface and you can see that here with draw shape it needs to actually disambiguate so not so if it's a rectangle that's being passed it needs to call draw rec if it's a triangle it needs to call draw triangle so you can see it's doing that here at the top you got that first type assertion where you say it says rec okay colon equals so that will return rectangle if' if the s is actually a rectangle so if okay is true and it found a rectangle itll called draw rec with that rectangle。



![](img/3835f356a37e4a2fb80ff7194d6e14d2_3.png)

Otherwise it does the next type assertion actually checks to see if the type of the interface of s is a triangle so it says try OK tricom OK colon equal s dot triangle is time and so that will return okay will be true if S is actually a triangle and in that case TRI try is going to equal that triangle and so you call draw triangle with with the triangle So either way。

We use this type of session to disambiguate and determine the actual underlying concrete type for this shape 2D interface。

Now， another way to do this sort of common common thing that you need to do is what we just did in the last slide。

 We went down a list of possible types。 So rectangle and triangle in this case。

 But note that know an interface can actually can be satisfied by many different types。

 So say that an interface is satisfied by 10 different types。 you might need to disambiguate all 10。

 So of run down the list。 if you're this type， then do this。

 if it's that type then do that and so on。 And so there's a switch construct a type switch。

 which is just for that purpose。 So you got one case for every different type that you need to to deal with。

 So in this case you got two cases case rectangle case triangle。 And in each case。

 case rectangle draws draws a rectangle case triangle draws a triangle But right before that you start with the switch。

 So we have notice the type。Type assertion says S dot type in parenthees。

 you just say type the generic word type。 And so what happens is S H will be be whatever itll be the concrete type that S represents。

 So if S is S is like is actually a rectangle， then S H will be that rectangle if S is a triangle。

 then SH will be that triangle and you'll hit the appropriate case。 So if SH is a rectangle。

 then you'll execute the case rectangle。 if SH is a triangle。

 then you'll execute the case triangle So this is just a more convenient way to sort of run down a list of to disambiguate a whole set of types that all satisfy a particular interface。

Thank you。