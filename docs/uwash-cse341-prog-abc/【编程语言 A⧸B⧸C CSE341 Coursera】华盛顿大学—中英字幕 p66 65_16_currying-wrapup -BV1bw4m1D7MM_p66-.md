# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p66 65_16_currying-wrapup -BV1bw4m1D7MM_p66-

There are just a couple more topics I want to cover with cur。

 and the first is that sometimes the function you want to call isn't organized the way you might wish it were。

 maybe you want to cur function and it's a tuled function or you want a tuled function and it's a cur function。

 or maybe you want to use partial application but not with the first few arguments。

 maybe with the later arguments and you can't do that。 given a cur function。

 you have to pass the first argument to it。 but what we could do is use our idea of combining functions to once and for all write very generic。

 very reusable functions like we did with function composition that let us change one kind of function into another。

 So let me motivate that with a short example， we've seen this example before where I wanted to take this function range which takes two numbers I and J and returns a list with all the numbers from I up to J。



![](img/ce187e7625b40d2c41584acf34663fc3_1.png)

Use that to create a helper function count up that just goes from one to the number and then use that countup function。

So this code as written will not work， and that's because this version of range is tuled。

 it takes a pair and here I tried to use partial application Now of course I could work around this or I could change range but there's a very general thing I could do。

 which is to take write a function that takes a function expecting a pair and returns the same function incurred form。

So it basically takes a function and curries it。So what if I did this， I could take this function F。

 and then I would return a function that takes two arguments in cur form。

And then calls F with the pair because F expects a pair。

 but cur of f will return a two argument cur function， and now down here for count up。

 I could juststill call instead callcurry of range， and this will now work。So that's pretty neat。

 Let me clean it up a little bit more just by using the syntactic sugar we've seen before。

 I could have just written it like this。That's curry。And at the call site。

 these parentheses are optional。We can go the other direction as well。 if we had a curried function。

 but we wanted to pass it a tuple， and that could actually be useful if you were composing functions or chaining them together。

 we could take two， we could take F and X comma Y and return a function that would look like this。

 So now when you call uncurry with some function fo。

 you would get back a function that expected a pair。And then called F with two arguments in cur form。

So that's pretty neat， let me quickly show you the types of curry and uncurry。They're very generic。

And I will lead you to puzzle over them， but I want to point out one very neat thing is there's a deep connection to logic here。

 You're not responsible for this， but if you have studied logic。

 read these as logical formulas where the star is and and the arrow is implies。

 and you'll see that these are actually true logical formulas。

 And that hints that there's actually a very deep connection。

 a very mathematical connection between toppling and cur。

 and I'm going to leave that as a mysterious statement for you。

One other thing I want to show you that also has these logical formulas once you look at their type is switching the arguments of cur functions。

 so if you had a two argument cur function and you wanted to partially apply it to the first argument to the second argument instead of the first。

 you couldn't do that unless you took that function and passed it to this function first instead。

So F takes two cured arguments， but other curry of F will just take the arguments in the opposite order。

 It takes an x and a y， and then it calls F with y and x。

 and we've seen before there's syntactic sugar for this。 We could just write it。That way。Okay。

 so just more fun playing around with combining functions。

 hopefully I've shown you that this thing is at least a little bit useful。

 and functional programmers do often program with these things in order to get things elegant and pretty and arranged range just how they want。



![](img/ce187e7625b40d2c41584acf34663fc3_3.png)

So that was one topic I wanted to discuss， the other is people often want to know isn't cur really slow if I want to create all these closures the call a function。

 and it turns out that it depends and that's up to the language implementation and language implementations can actually make cur functions very efficient。

So in general， both calling a function with a tuple and calling a function via occurring with multiple arguments。

 these are plenty fast， these are constant time operations。

 you should program in a way that makes your code elegant， short， concise and correct。Alright。

 but for those tiny portions of your program， those inner loops where performance actually matters。

 Well， then maybe you might want to know which is faster。

 This is not part of the language definition。 It will depend on the language implementation。

And it turns out that the implementation of SML that we are using。

 the SML New Jersey compiler does faster with toling than with cur。

 so cur would in fact be a bit slower for some function you were calling tons and tons and tons of time for a performance critical application where it actually matters。

I should point out that this is actually not necessarily the case and in fact。

 most other functional programming language implementations out there today。

 Ocael F sharprp Haskell do better with curing than with couplingling Now the optimizer might do very well with both of them but in those other languages we tell performance conscious programmers use curing。

 it will work just fine if you use partial application which is something up to callers that might be a little bit slower。

 but in languages where curing is always the norm。We tell programmers even when they're learning to program。

 oh， it's just the three argument function and the same way I lied to you at first and told you the toppled version was a three argument function and then went back and told you the truth。

 that's what these other languages do with cur Cur is the default。

 almost everything is cur and you only topple things in those situations where it's more convenient。



![](img/ce187e7625b40d2c41584acf34663fc3_5.png)