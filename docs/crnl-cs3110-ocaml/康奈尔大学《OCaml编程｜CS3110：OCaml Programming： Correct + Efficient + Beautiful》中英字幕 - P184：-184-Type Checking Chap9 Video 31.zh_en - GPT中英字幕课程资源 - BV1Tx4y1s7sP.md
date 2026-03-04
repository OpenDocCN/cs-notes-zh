# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P184：-184-Type Checking Chap9 Video 31.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

When we built the big step， substitution model interpreter for simple。

There were three places where a run time error could occur。

 A variable just by itself does not step because it should have been substituted away。

 A binary operator could not step if it had a type error。 For example。

 a plus with a5 on one side and a false on the other。

 And an if expression required its guard to be a boolean， not an int。



![](img/2841b4cb79edc78ecf3735fd2c95e1d8_1.png)

In the interpreter code， each of these corresponded to a failure that we raised at runtime。

So when we got to the point of having a variable that had not been substituted away。

 and we tried to evaluate that， we raised an unbound variable error。

When we got to a binary operator that didn't have the right types of arguments on either side of it。

 for add， it needed to be an int and an int for mult the same and for less than equal to the same。

 then we raised an error， and for if expressions， if the guard did not evaluate eventually to either bo true or bo false。

 then we also raised an exception。

![](img/2841b4cb79edc78ecf3735fd2c95e1d8_3.png)

The goal of type checking is to prevent such errors。

 We'd like to avoid ever having those kinds of runtime errors occur in a program。 After all。

 those are errors that not just could bother us as a programmer。

 but maybe you could have end up appearing to our end users to the clients we're developing our software for we don't want them to see those kinds of errors。

 We'd rather to prevent them to begin with。😡，And that's what type checking can do T checking can help us prevent all of these kinds of errors that really are detectable at compile time so they will never happen at runtime。

So a type checker is going to analyze a program。😡，And it's going to reject that program if it contains any detectable type errors。

It's going to refuse to ever let that program be run if those errors are detected at compiled。😡。

To accomplish that goal。A tight checker needs another kind of environment that we haven't seen so far。

 I alluded to it before。We already had dynamic environments around those mapped from identifiers to values。

Now we're going to have， for sake of type checking， a static environment。

This is going to be a map from identifiers to types。So if x is going to be a 42 at runtime。

At compile time， we might know that excess type int。

 so you can think of the static environment as kind of being an approximation or even better yet an abstraction of the eventual dynamic environment。

😡，We abstract away that actual value 42 and we just say， we know it's going to be some int。

 we just don't know which one。The static environment also is scoped like a dynamic environment。

So for example， in this inner scope here after the binding of 42 to x， at compile time。

 we know in that scope， the x is going to have type int。

And then in the inner scope where y has been bound to 3110， we know that y also will have type。

So the static environment also called a typing context。

 is what gives us this notion of scope for the types of variables at compile time。😡。

To express type checking mathematically and precisely， we're going to need a new relation。😡。

And we've had a lot of relations before， but they've all been for evaluation mostly。

 we had the big step evaluation relation， the small step evaluation relation。

 we had substitution and environment model relations。😊。

Now we're going to have a type checking relation， also called a typing judgment in the sense of making a judgment about the type of an expression。

It's a turnernary relation。And it' written stag environment， which is end here。



![](img/2841b4cb79edc78ecf3735fd2c95e1d8_5.png)

Turnt。 and you pronounce the turnt as either shows or proves this is a symbol for mathematical logic that expression E has type T。



![](img/2841b4cb79edc78ecf3735fd2c95e1d8_7.png)

So the E colon T part of this is entirely normal， you're used to this from U。

 it even shows you this if you put something in。But the static environment is usually hidden from us right We don't usually see that in Utah。

 there's no way of really printing out what the static environment is。Here， though。

 we're going to write it down because we have this mathematical relation describing the typing judgment。

Here are several examples of that typing relation。And the first example。

Suppose we're trying to type check X+ 2。And we are doing that in a static environment where we already know that x has type int。

Well， in that environment。It is the case that the expression X plus 2 has typed in。

You and I know that we can look at that and figure that out ourselves because we know a lot about Ocael。

Pretty soon， we're going to write down the actual mathematical rules that would enable anyone to figure that out。

Now suppose we're in adifferent environment as in the second example here。If x has type rule。

 that does not show that x plus 2 has type end。 In fact。

 that would be a nonsensical expression in OM well to try to add a Boolean and an int together。

Likewise， if x has type n， then x plus 2 does not have type bool， also nons。And as a final example。

 in the empty static environment in which no identifiers have been bound to types。

That does not show that x has type in， In fact， it can't show that x has any type at all because x is not bound in the static environment。



![](img/2841b4cb79edc78ecf3735fd2c95e1d8_9.png)