# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P194：-194-Inference of Functions Chap9 Video 41.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next， let's look at type inference for anonymous functions。

Suppose we're inferring the type of the function xarrow E in Environ N。

That's going to have the type tau 1， arrow T2 and generate a set of constraints。Now yes。

 I am being careful here， the first of those is a type variable tau 1。

 the second one is a type T2 that might not just be a variable。So let's see where those come from。

First off， we introduce a fresh type variable tau 1。

That is going to be the type of the argument to the function。

So we don't know what x is looking at this， you know。

 maybe you and I as a human could look a little bit further into E and figure it out ourselves with our brains。

 but an algorithm looking at this a priori is going to have no idea what type was intended for that variable。

So the algorithm introduces a new type variable to stand for the type of x。

 That type variable is tau 1。😡，Then。😡，We go ahead and infer the type of E。

In an environment that is extended to bind the name X to the type tau 1。😡。

So anywhere we go to look up that name inside of E now。

 we'll get back that his type is tau 1 in that type period。Well。

 type inferenceen of E will eventually return with a type T2。😡，Along with a set of constraints。Now。

 if x is ever used in an interesting way inside of E。

 that set of constraints will end up talking about tau 1。

Maybe we'll discover inside of E that x has to be an int or a bool。

 and so we'll end up with a constraint that says tau1 equals int or tau 1 equals bool。

That's how we'll figure out the type of that variable。😡。

So the type of the entire anonymous function then is the type of its argument， which is tau1。

Arrow the type of its body， which is T2。So the algorithm picked a type variable for the argument。😡。

The algorithm inferred a type for the body。And finally。

 the set of constraints returned for type inference of the Ananous function is just the set of constraints that were produced by inferring the type of its body that set C。



![](img/96599a8f1c8fda98d99ce5458361ace9_1.png)

Let's try an example with an anonymous function。The type of the variable X will be represented by a new type variable。

 So let's call that alpha。 So we want to continue doing inference in an environment that maps x to alpha。

And we need to infer the type then of the body of the function， which is itself an if expression。

Well， we know how to infer the type of an if expression， we just covered that。

The type of the guard we've just looked up inside of the environment that gives us back alpha and generates no constraints。

 The types of the then and the else branches are just constants。

 so those are both have type int and generate no constraints。

 and then of course we need to generate all of the constraints for the if expression itself。

We give the if expression a type beta， which is a fresh type variable here that we've introduced。

 and we record the constraints that the guard must have type that is equal to bool。

 so that means recording the alpha from here equals bool。

And that the two branches have the same type， so whatever type variable we introduced here for the if expression beta here must be equal to int because of the int showing up for the then branch and again equal to int because of the int showing up in the else branch。

So as that set of constraints， then， if we wanted to simplify it a little bit。

 we could say that we're left with alpha equals pool and beta equals int。Now popping up one level。

 weve finished the inference for the body of the anonymous function。

And now we can say that it has type alpha because that's the type variable we introduced for the argument to the function。

Arrow。Beta， because that's the type that was inferred for the body of the function。

And that comes along with the set of constraints， which is that alpha equals bo and beta equals int。

So now if you and I look at that as humans， we could say， a。

 well the type of this function then must be bo arrow int。

 and that's probably no surprise you guessed that right away when I wrote that down later on algorithmically we'll need to solve that set of constraints to figure that out。

 but for now we've done what we needed to， which is to collect the constraints。



![](img/96599a8f1c8fda98d99ce5458361ace9_3.png)