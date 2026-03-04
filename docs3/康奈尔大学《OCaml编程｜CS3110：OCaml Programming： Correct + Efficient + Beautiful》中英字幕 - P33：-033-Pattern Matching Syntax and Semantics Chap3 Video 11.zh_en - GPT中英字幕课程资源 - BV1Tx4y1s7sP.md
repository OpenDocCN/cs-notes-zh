# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P33：-033-Pattern Matching Syntax and Semantics Chap3 Video 11.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've now seen many examples of pattern matching。 Let's take a step back and look at its syntax and semantics。



![](img/767b73320ac244a5acd33f681144fb47_1.png)

The syntax of a pattern match is written with two keywords， match and width。



![](img/767b73320ac244a5acd33f681144fb47_3.png)

We match an expression E against a series of patterns。And for each of those patterns。

 there is an expression that could eventually be evaluated。



![](img/767b73320ac244a5acd33f681144fb47_5.png)

Each of the lines here in the pattern match is called a branch。

 We can have many branches inside of a pattern match or even just one branch， as we've seen。



![](img/767b73320ac244a5acd33f681144fb47_7.png)

![](img/767b73320ac244a5acd33f681144fb47_8.png)

And P here represents a new syntactic class of pattern expressions。



![](img/767b73320ac244a5acd33f681144fb47_10.png)

These look more or less like any other kind of expression in Ocael。

 which is why I've been able to sneak it in without even me talking about the syntax So far。

 The only new piece really has been the underscore。



![](img/767b73320ac244a5acd33f681144fb47_12.png)

There are some other syntactic forms of patterns， and you will find those in the textbook。



![](img/767b73320ac244a5acd33f681144fb47_14.png)

For evaluation of a match expression。

![](img/767b73320ac244a5acd33f681144fb47_16.png)

First， we need to evaluate E to evaluate V。Then proceed， top to bottom。



![](img/767b73320ac244a5acd33f681144fb47_18.png)

Through the pattern match。Try to match V against the first pattern， P1。If it matches。

 we're done trying to find the right branch。 We don't look at the rest。



![](img/767b73320ac244a5acd33f681144fb47_20.png)

And we evaluate the right hand side of that branch。 So if P1 was the pattern that matched。

 we would then evaluate E1， and E1 is what we would return， Or rather， E1 evaluates to evaluate V1。

 and V1 is what we would return。

![](img/767b73320ac244a5acd33f681144fb47_22.png)

If P1 didn't match the。Then we'd go on to P2。If P2 didn't match。

 we'd go on to P3 and so forth and so on。 until we finally found a pattern that matched or。



![](img/767b73320ac244a5acd33f681144fb47_24.png)

We didn't find anything。In that final case， if there's no patterns that match。

 the name exception gets raised。

![](img/767b73320ac244a5acd33f681144fb47_26.png)

That exception is named match， underscore failure。

![](img/767b73320ac244a5acd33f681144fb47_28.png)

We don't like exceptions to be raised in programs。 And so all of the code I've written with you so far has avoided having any kind of pattern match that could fail in that way。



![](img/767b73320ac244a5acd33f681144fb47_30.png)

We'll see an example， soon。

![](img/767b73320ac244a5acd33f681144fb47_32.png)

Type checking of match expressions。

![](img/767b73320ac244a5acd33f681144fb47_34.png)

Is really driven。By those evaluation semantics that we just discussed。All of the patterns。

 as well as the expression being matched， need to have the same type。



![](img/767b73320ac244a5acd33f681144fb47_36.png)

And that makes sense because we're matching the value of that expression against those patterns。

 so they all should have the same type。

![](img/767b73320ac244a5acd33f681144fb47_38.png)

![](img/767b73320ac244a5acd33f681144fb47_39.png)

Likewise。The type of the entire match expression needs to be the same as the type of all of the possible things that could be returned from any branch of it。



![](img/767b73320ac244a5acd33f681144fb47_41.png)

![](img/767b73320ac244a5acd33f681144fb47_42.png)

So all of those sub expressions， E1 through E N need to share the same type。



![](img/767b73320ac244a5acd33f681144fb47_44.png)

![](img/767b73320ac244a5acd33f681144fb47_45.png)

And that's also going to be the type of the entire match expression。



![](img/767b73320ac244a5acd33f681144fb47_47.png)

Okay， so to put that a little more carefully， if E and all the patterns P have a type TA。



![](img/767b73320ac244a5acd33f681144fb47_49.png)

And if all the E I have a potentially different type TV， then the entire match expression has type T。

 As for that pattern syntax， the most basic pieces of it are identifiers， underscore。

 and any constant you like。

![](img/767b73320ac244a5acd33f681144fb47_51.png)

![](img/767b73320ac244a5acd33f681144fb47_52.png)

![](img/767b73320ac244a5acd33f681144fb47_53.png)

So the identifiers are the pattern variables， underscores that wild card。

 and the constants are syntax like 42 or the string Hlo or the Boolean truee。



![](img/767b73320ac244a5acd33f681144fb47_55.png)

![](img/767b73320ac244a5acd33f681144fb47_56.png)

![](img/767b73320ac244a5acd33f681144fb47_57.png)

How does matching itself work？Well， a constant matches itself， so 42 matches 42。



![](img/767b73320ac244a5acd33f681144fb47_59.png)

Whenever you have an identifier， in other words， a pattern variable。



![](img/767b73320ac244a5acd33f681144fb47_61.png)

That will match anything。And it binds the value that it matches in the scope of the branch。

 We've seen many examples of that， with our list functions。



![](img/767b73320ac244a5acd33f681144fb47_63.png)

![](img/767b73320ac244a5acd33f681144fb47_64.png)

The underscore， a K， the wild card character。

![](img/767b73320ac244a5acd33f681144fb47_66.png)

Matches anything， but it doesn't bind it。 And we've seen examples of that， too。



![](img/767b73320ac244a5acd33f681144fb47_68.png)

And for more pattern syntax， every data type has its own kind of pattern as well。

 We've seen the empty list and the cons operator as part of patterns。

 because those are the two ways to build up the lists。



![](img/767b73320ac244a5acd33f681144fb47_70.png)

Note that aend is not a pattern。 That's just a function that we wrote almost。



![](img/767b73320ac244a5acd33f681144fb47_72.png)

You can also use the square bracket syntax as patterns。For tuples and records。

 you can write those as patterns as well， and those can have nested patterns inside of those。



![](img/767b73320ac244a5acd33f681144fb47_74.png)

So all of those are going to match the corresponding data type values and combined parts of them as well。



![](img/767b73320ac244a5acd33f681144fb47_76.png)

There's a very rich syntax for how you can nest these and get deep pattern matches and have other kinds of patterns that say one pattern or another pattern might match the details of all of those can be found in the textbook。



![](img/767b73320ac244a5acd33f681144fb47_78.png)

![](img/767b73320ac244a5acd33f681144fb47_79.png)

![](img/767b73320ac244a5acd33f681144fb47_80.png)