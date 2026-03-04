# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P193：-193-Inference of Ifs Chap9 Video 40.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

How about type inference for if expressions？This is the first place where it's going to start to get a little complicated。

We're inferring the type of F E1， then E2 LE3 in a static environment M。

We're going to infer a type tau for this， so I'm pronouncing tick T as tau。

And there's going to be a bunch of constraints involved。

 so this is the first time we've actually generated any constraints。

Let's take this one step at a time。First， tau here should be a fresh type variable。By fresh， I mean。

 it's never been used anywhere else in type inference for this program。

 so it's completely brand new hence fresh。😡，The type of the entire if expression here is going to be inferred as just that new type variable tau。

That's because looking at this syntactically， without descending into E1 or E2 or E3 without looking any deeper into those。

 we don't yet know what the type of this if expression should be。😡，Now， of course。

 you and I both know that if we were to look deeper into E2 and E3。

 we could figure it out because the type of an if expression is the type of its then and else branches。

😡，But algorithmically， we can't do that yet。😡，Next， we're going to take that static environment N。

 and we're going to do type inference for each of the three sub expressionions。

 So we'll infer the type of E1。😡，That will be some type T1。

 Now we have no control over what that type is going to be。

 The type inference algorithm might return bo。 It might return a type variable。

 it might return something even crazier than that。😡，All we know is that it's some type。

 so let's just let that be T1。The same will be true for E2， the same will be true for E3。

Each of those is going to independently generate its own set of constraints potentially because of the code nested inside of it。

So let each of those constraints be C1， C2， and C3。Now， to pull all this together。

 we know that there are some relationships that most told between the types that have shown up here。

😡，And that's what we record in this additional set of constraints C。So set C will be T1 equals bo。

Because we know that we need to constrain the type of the guard to be Boolean。Furthermore。

 tau needs to equal both T2 and independently T3。Because the types of both the then and else branches must be the same in an if expression。

So inference returns tau as the type of the if expression。

Along with all of the constraints from the sub expressionions， C1， C2 and C3。And additionally。

 unions in those three new constraints on the type of the guard， the type of the then branch。

 and the type of the elsese branch。I'm writing comma here between these sets of constraints rather than a union symbol just because it's easier to type on my keyboard。



![](img/d39dc15aa18633303c37eec7beeaaa51_1.png)

Let's try an example of inferring the type of an if expression。

Suppose I am trying to infer the type of， if true。Then。0 L1。What would it be。Well， first。

 I need to invent a fresh type variable。How about I just use alpha as my type variableable that's not been used anywhere else around here？

So I'm going to return alpha as the type of this if expression。😡。

And of course there will be some constraints， I need to figure out what those constraints are though。

So to do that， I need to go ahead and infer the type of the guard。How do I do that Well。

 that's a booleyan constant， So we use the rule for constants that we introduced before that has tight bo and generates no constraints。

I also need to infer the types of the then and the else branches。 So the then branch。

 that's the constant 0。That has type int。And it generates no constraints。Lastly。One also has type in。

And generates。No constraints。Finally， I need to form the set of constraints。

That is added on top of everything else that I got before by the if expression。

So my set of constraints is going to be that I haveB equals bo， now where did I get that from？

I took the type that was inferred here for the guard， put it here， and then said that must equal bo。

 That's what the rule says up here。 Whatever type T1 shows up， I have to say T1 equals bo。😡，Now。

 in this case， that's trivial because the guard was a trivial expression。 it was just a constant。

 Of course， in general， we might get something more complicated。

 like maybe there's a function application in the guard， for example。😡，Next， my type variable。

 alpha needs to equal whatever type showed up as being inferred for the then branch。

 So that was int here。 So I have to write alpha equals int。And after that。

 I need to again write alpha equals int that comes from tau equals t3 here。

 so I need to say that my type variable equals the type that was inferred for the else branch。

 which is also int in this case。Okay， so now I know the set of constraints that I need to write for this entire thing。

 I need to say that I have all of the constraints from the sub expressionions。

 Well those were all empty sets， so let's not bother writing that down again。

And then I have the set C here， which I defined down here below。

 Google equals Google Alpha equals int。 Now， of course， I could collapse all of that。 But really。

 the only thing that interesting that came out of that was alpha equals int。

 So I could write that down as my set of constraints up here if I wanted to simplify on paper a little bit。

Alrithmically， when you implement this， you might or might not notice that there are duplicates here。

 you might or might notice that there are trivial identities showing up here。

 that would be additional code that you could write to simplify things just a little bit。

So notice at the end of doing inference for the if expression。

 I have a type alpha for it and a constraint on that type。😡。



![](img/d39dc15aa18633303c37eec7beeaaa51_3.png)

![](img/d39dc15aa18633303c37eec7beeaaa51_4.png)

And you and I can look at that and say， oh yeah， so that means the type of the entire if expression is int。

But remember， in implementing this as an algorithm。

 we're going to end up with potentially a large set of constraints that need to be solved。

 maybe it's even too hard for our human brains to solve them because there's just so many。

So we'll return to the notion of how to solve that set of constraints and combine it together with the inferred type alpha later on。

😡。

![](img/d39dc15aa18633303c37eec7beeaaa51_6.png)

![](img/d39dc15aa18633303c37eec7beeaaa51_7.png)