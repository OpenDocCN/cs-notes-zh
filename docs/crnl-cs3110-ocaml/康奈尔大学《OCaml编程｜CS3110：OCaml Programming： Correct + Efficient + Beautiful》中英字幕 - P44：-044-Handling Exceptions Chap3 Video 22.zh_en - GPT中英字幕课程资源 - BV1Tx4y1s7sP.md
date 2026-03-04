# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P44：-044-Handling Exceptions Chap3 Video 22.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Handling an exception that has been raised。Is really just a matter of pattern matching。

Because exceptions are variance。For example， suppose you were trying to handle a division by zero。

WellNormally if you divide by zero you get an exception。

 suppose you wanted a safe division function that if a division by zero were ever attempted。

 you instead return something else like I don't know。

 maybe you define that the result of dividing by zero is just zero。

We could say let safe div of X and Y。We will try to evaluate x divided by y。If that succeeds。

 the value of x divided by y will be returned。But if evaluation of x divided by y raises an exception。

 we can go on and pattern match against that exception， so this is just like match with。

 except now it's try with and we're only going to pattern match in the case an exception gets raised。

So if the division by zero exception gets raised， then what we decided was we would return zero。



![](img/be8cce243d1fd19fb0723c9a7af1c72a_1.png)

Now when we try to take the safe division of four by zero。

 we get zero instead of an exception the syntax and semantics of tri expressions is very similar to that of match expressions。

The syntax is try E with and then some pattern branches， you can have more than two branches。

 you can have just one。To evaluate a try expression， evaluate the expression E to evaluate。

If that does actually succeed， if E is able to produce a value without raising an exception。

 then the entire try expression evaluates to V， we'll never even look at the patterns at that point。

But if E raises an exception， let's call it X。Then proceed by matching X against each of those patterns。

 just like pattern matching normally works。If one of the patterns matches。

 evaluate the expression on the right hand side and return it。Otherwise。

 if we fall off the end and there's no patterns that match。At that point， X is reraised。

 so that's a bit different than the normal semantics for match expressions because at the end of a match expression。

 if no match was found， instead the exception match failure gets raised here we rerase whatever X was。

As for type checking， the entire try expression has a type T。If E has that type T， y。

 because E is what's going to be returned as the result， if no exception is raised。

And if all of the E subs have that same type T， why。

 because one of them might end up getting to be the value that gets returned in the event of an exception。

And of course， all of the patterns themselves have to have type EXN because we're pattern matching against whatever exception might have gotten raised。



![](img/be8cce243d1fd19fb0723c9a7af1c72a_3.png)