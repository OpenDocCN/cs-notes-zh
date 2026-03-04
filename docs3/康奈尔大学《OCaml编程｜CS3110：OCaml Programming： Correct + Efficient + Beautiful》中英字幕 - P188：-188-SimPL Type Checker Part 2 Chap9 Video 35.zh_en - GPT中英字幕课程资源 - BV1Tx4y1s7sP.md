# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P188：-188-SimPL Type Checker Part 2 Chap9 Video 35.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next， let's implement let expression type checking。We'll pause here。

I'm starting to accumulate a bunch of helper functions。And at that point。

 I should probably be writing a specification for each one of those。Now。

 how do I implement type of Let Well， the rule that we invented before for type checking of Let tells me exactly how I need to type check E1。

 make sure that has the type T as the programmer specified and extend the static environment with it to type check E2。

So we'll implement that。Okay， let's pause here。We've type checked E1。

You've gotten the type T prime for that。And then we compare T and T prime to see if they're the same。

If so， then the programmer got it right， The types are correct in the code。

And we should proceed with type checking the bot。I've invented a new helper function here。

 I want to extend the static environment to bind a name to a new type。😡。

And in that extended static environment， I will type check E2 and return whatever that type is。

We'll write that helper function in just a second for now let me finish off type of let if T and T prime were not the same。

 then we have a type checking error。Now this is a new error。

 one that didn't occur before at runtime because we never had types around before。

 so I'm going to need to introduce a new string for representing type annotation errors。😡。

So now I have my annotation error message。Type of let is almost finished。

 I just need to write that extend function。And of course。

 I can implement that extend function quite easily since this is just an association list。

All I'm doing is coning on that new binding。Do I need to worry about duplicate bindings？

The semantics of the language involves shadowing。A binding of a variable name in an inner scope shadows a binding of the same name in the outer scope。

So by putting the new binding at the front of the list。

 I'm guaranteeing that that new binding shadows any previous bindings。Therefore。

 I rather nicely get exactly the right semantics， and I don't even have to worry about crawling down the list to remove any duplicate binding。

That finishes type of let。Now I can go back and add the next syntactic form。Okay， we'll pause here。

 I have introduced my new helper function for the type of if now I just need to implement the type checking rule。

 which is to say check that the guard has type Google and check that the two branches have the same type。

We'll pause again here。

![](img/22b5526f7456ef73616dbd12c969ce98_1.png)

I've implemented checking the type of the guard to make sure that it's bool if it's not boool。

 I will raise a type error。 This is yet another example of something that could have been a runtime error or a type error。

 We're going to prevent this error at runtime with type checking。

 but we still have to leave the branch in farther down below in the code。😡。



![](img/22b5526f7456ef73616dbd12c969ce98_3.png)

Now we can implement checking the branches。

![](img/22b5526f7456ef73616dbd12c969ce98_5.png)

So I type check recursively the two sub expressionpressions to get their types T2 and T3。

 If those two types are not the same， then I'll raise a type error。

 otherwise I could return either one of them because they're equal。

 so I'll just go ahead and return T2 kind of arbitrarily。



![](img/22b5526f7456ef73616dbd12c969ce98_7.png)

Now I have a new kind of type error here that never existed before。

 and that's because at runtime I never evaluated both the then and the else branch and then compared their types the evaluation semantics that you only evaluate one of。

😡，Well， here in type checking， we've got to look at both。

So that means we've got a type error that would never correspond to any runtime error。Okay。

 so I've added in the error message now。And that concludes the implementation of type of if。

And furthermore， that concludes the entire implementation of type of。

That means my entire interpreter is now finished。 I've added all of type checking to it。



![](img/22b5526f7456ef73616dbd12c969ce98_9.png)

So I could go ahead and run a test suite Now， of course。

 I should have been running these test cases all along as I implemented this using test driven development。

 I trust that you understand how to do that and can use it effectively now there are times when you need to use it and maybe times when you don't Here was a case where I was confident in what I was doing so I didn't feel the need to use it but I could always have returned to it if I needed to so I do have a test suite here。

 basically the same test suite that we've been using all along for our simple interpreters but now I've added some type checking to it my lead expressions are all annotated with types and I have some cases here to check type checking of。

Mismatched binary operators with operas of if expressions that have various type errors and of unbound variables。

Let's run that test suite。And it succeeds， yay。We've finished adding type checking to simple。😡。



![](img/22b5526f7456ef73616dbd12c969ce98_11.png)

![](img/22b5526f7456ef73616dbd12c969ce98_12.png)