# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P43：-043-Exceptions Chap3 Video 21.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've put off talking about exceptions for a while now。

 the reason why is that they really are just variants now that we know about variants。

 we can understand exceptions。There is a type in Ocaml called EXN。

 This is the built in type of exceptions。And all exceptions are actually values of that type。

You can define your own exceptions by just saying exception and then the name of that exception。

This behaves as a constructor of type EXN。And since it's a constructor。

 it could be constant or non constant， it could also carry data along with it。

 so you could have an exception which is a bad thing， an exception oh no carries along a string。

Type EXN here is special in that it is a built in extensible variantNormally when we define variants。

 we have to list all of the constructors right there as part of the definition EXN allows us to provide the constructors later on with that keyword exception。

Exception， oh， no of。String。That comes back and says， yes。

 you have now added that constructor exception ohO of string。And now I could have ohO。

 which carries along with it， a string， maybe oops。And that is of type EXN。

 so you can see it is a constructor that produces a value of the exception type。

And now if I want to raise an exception， I can do that， it's just the raise keyword like in Python。

You can see that instead of a normal kind of result that I get back here。

 Oel says there's been an exception， oh no oops was raised。

 similarly to how dividing by zero would say exception division by zero so actually division by zero here know that it's capitalized that is a constructor of type EXN that was predefined in the standard library。

The exceptions we create do not have to carry any data， I could have an exception， a bad thing。

And now I can raise a bad thing that doesn't carry along the extra helpful information about like an error message or anything。

 but maybe all I need to know is that a that。OcaMel programmers are more likely to create their own new exception than some Java programmers are。

 just because it's really easy to create your own new exceptions in OCMl。

 it doesn't require all of the effort that Java does of creating a new class file and defining constructors and so forth。

So that built in function raise is a type EXNarrow alpha。

 it takes in a value that is an exception and it raises it。Because it raises that exception。

The expression in which you wrote raise is itself never going to produce a real value。

It's not going to return any value instead the exception gets raised。

That's why the return type of raise is alpha， we can treat it as having any type we want because it's never truly going to return。



![](img/3f48ca806aa6a498e8f5865e25886c6b_1.png)

For example， I could say let x of type int equal rays a bad thing。Now， of course。

 a bad thing is not an int， raise a bad thing is not truly an int。

 but we're allowed to say that it has type int。Because it's never actually going to return something to that context that it's in。

There's never going to be an integer produced by rays that could get stored inside of X。

 so the type system allows this There are many predefined exceptions in the standard library。

 two useful ones are failure and invalid argument。

![](img/3f48ca806aa6a498e8f5865e25886c6b_3.png)

They both carry strings with them so that you can supply a helpful error message。

The documentation in the standard Library of failure says that it is an exception raised by library functions to signal that they are undefined on the given arguments。

Compare that to the documentation of invalid argument。

 which says it's an exception raised by library functions to signal that the given arguments do not make sense。

Now， if those sound a lot alike to you， you are right， in reality。

 we could have gotten away with just one of them， but we have both。

There are two built in functions in the standard library for raising these as just kind of convenience functions。

Fail with raises failure， invalid arg raises invalid argument。



![](img/3f48ca806aa6a498e8f5865e25886c6b_5.png)

So you can either go to the trouble of writing， raise failure。

 and then provide your error message here。

![](img/3f48ca806aa6a498e8f5865e25886c6b_7.png)

Or a little more conveniently， you can just write fail with。My error message。

And all that really does， it just calls raise with the message you provided。

