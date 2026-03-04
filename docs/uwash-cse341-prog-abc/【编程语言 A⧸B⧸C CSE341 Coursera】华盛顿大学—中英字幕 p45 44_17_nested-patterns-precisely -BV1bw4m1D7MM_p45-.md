# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p45 44_17_nested-patterns-precisely -BV1bw4m1D7MM_p45-

I want to wrap up our discussion of pattern matching by giving a precise definition of when a pattern matches a value and this is a bit more complicated now that we have nested patterns。

 but it leads to a very natural and elegant recursive definition so just to be clear what I'm doing here is describing the semantics the evaluation rules for the part of pattern matching where you have a pattern and you have a value and you want to know whether they match or not so for example the value would be the result of the expression between the word case and the word of and then the patterns would be each branch of the case expression in order now these rules also apply to when you have patterns in function bindings or in Val bindings but the key issue is here's a pattern here's a value。

 do they match and if they do match what variables are introduced and what are those variables bound to。



![](img/85e48c82be08b5b41a301102576a0243_1.png)

![](img/85e48c82be08b5b41a301102576a0243_2.png)

Okay， so in the presence of nested patterns， this is a recursive definition。

 And we would have one case of this definition for every way of writing down patterns。

 So I haven't written an exhaustive list here on the slide。

 but I think by going through these examples， you'll get the sense of it。

 and you'll get a sense of how pattern matching is itself in the language definition a recursive procedure。

So let's start with the base cases of that recursion。

 and that's when the pattern is either a variable or that wild card， that underscore character。

So we have a pattern， we have a value。 One case of our definition is the pattern is a variable。

 if that's the case， the match always succeeds， no matter what the value is。

 and we bind the variable to the entire value V。That makes sense。And the underscore case。

 the wildcard case， is exactly the same， the match also always succeeds， and we don't find anything。

Okay， good。 the other cases are recursive。 They build out of the smaller nested patterns。

 those nested patterns might be base cases like variables。

 that's how we started using pattern matching or they can be nested patterns in which case this recursive definition will apply。

So for example， suppose we have a topple pattern， so we'll have some pattern of the form P1 comma P2 up to PN。

Then that will only match values that are also topples with n values inside of them。

 and it will only match if P1 matches V1， P2 matches V2 and so on up to PN matching VN that recursive matching is appealing to the same recursive definition so we would use recursive call。

 if you will， to the pattern match procedure。Now， if all of those subpatters。

 those nested patterns match， then they will all introduce various bindings of variables to values。

 and the overall pattern will be the union of all those binding。

 So all the variables introduced by P1， all the variables introduced by P2 up to all the variables introduced by PN。

 The one extra rule in pattern matching is you're never allowed to use a variable more than once。

 if you try to use the same variable more than once in a pattern the compiler will reject that and tell you directly that you're not allowed to do that。

Let's do one more interesting case。 This is the case for when we're using a constructor。

 So on the slide here， where see that capital C， assume that that is one of the constructors for some data type that's been previously defined。

So one kind of pattern we can write down is that constructor C， followed by a nested pattern P1。

 that nested pattern is often a tuple， but it doesn't have to be。 It can be any kind of pattern。Now。

 if we have a constructor with a pattern underneath it。

 the only thing that will match is a value that was built out of the same constructor。

And a value that matches the pattern。 So we need the same C。 And then we also need P1 to match V1。

 And then whatever variable bindings are produced by the recursive match of P1 matching V1 are the variable bindings that we have for the larger pattern。

 C of P1 with the value， C of V1。So hopefully that gives you a sense of how pattern matching is a recursive procedure and we can use this to understand much better what it means when these nested patterns are matching against values of certain shapes so here are three examples in the first example here you see a the pattern a cons on to B con on to C conzon to D and if you follow the recursive procedure treating colon colon as a constructor but we have are the nested pattern A and then the nested pattern B cons on to C cons on to D and so on recursively and what this will end up matching is any list that has greater than or three elements because we'll recursively match a against the first element B against the second C against the third and then D against the rest of the list if the list is too short will end up trying to match the empty list constructor value against the cons constructor pattern and that simply fails to match that's okay we would move on to the next case。

The next branch in our case expression。The second pattern a conon to B conon to C conzon to empty list would match all list with exactly three elements。

 matching A to the first element B to the second and C to the third， if the list is too short。

 then just like in the previous example we'll have some empty list value that fails to match if the list is too long we'll end up in the recursive position where we have the empty list pattern trying to match against a non-empty list value and that will fail to match。

And then in this third example， we have some more nested patterns where we have a cons constructor pattern with a variable on the right that said variable E。

 and then on the left we have the sort of pattern that requires a pair of two nested pairs so this will only match against a non-empty list whose elements are pairs of pairs and then we'll introduce five variable bindings。

 so that is our more precise definition， hopefully it gives you the sense that pattern matching is not a fuzzy concept。

 It's a very precise concept， and that better explains more completely explains the examples we saw in previous segments。

😊。

![](img/85e48c82be08b5b41a301102576a0243_4.png)