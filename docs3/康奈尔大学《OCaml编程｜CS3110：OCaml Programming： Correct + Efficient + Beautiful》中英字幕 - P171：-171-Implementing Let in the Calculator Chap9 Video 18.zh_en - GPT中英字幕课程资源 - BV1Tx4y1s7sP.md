# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P171：-171-Implementing Let in the Calculator Chap9 Video 18.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's implement let expressions in our calculator interpreter。

We're going to need to extend the AST type to represent variables and let。😡。



![](img/5926d364919c8aa160bc7e0c524b1cd4_1.png)

So I've added two constructors to my AST type， one for variables that carries along a string。

 I'm just going to represent identifiers as Ocal strings here。



![](img/5926d364919c8aa160bc7e0c524b1cd4_3.png)

![](img/5926d364919c8aa160bc7e0c524b1cd4_4.png)

And lead expressions are another kind of node that carry along with them a triple containing a string that's the variable being bound。

 an expression， that's the binding expression， and another expression， which is the body expression。



![](img/5926d364919c8aa160bc7e0c524b1cd4_6.png)

Of course， I could use a record to keep track of binding versus body。

 but I think I'll be able to do that successfully myself without needing field names。

I've already extended the Lexer and parser to handle variables and lead expressions。

 I won't demo that here， but you can look at the provided code after I build the code again。

 my interpreter， my step function and all the other functions related to it。



![](img/5926d364919c8aa160bc7e0c524b1cd4_8.png)

Those have a lot of warnings now that's because I added those new AST nodes and now I have inexhausttive pattern matches。

 so I'm going to need to go ahead and add in some implementations of each of those pattern matching branches for the new AST nodes for is value neither a variable nor a lead expression is a value only integers are。

 so this one's easy。😡，I have a stub implementation in here of the substitution function。

 we'll come back to that in a moment， but first let's move on to the step function。😡。

I need to put in some code here to handle stepping of variables and of let expressions。Okay。

 now at least my code is compiling， and I need to fix it up to make it do the right thing。

How would a variable step。This is a bit subtle。If we reached the point of having just a variable name。

It means we've reached a variable that was never bound。For example， if you were in the top level。

 suppose you just entered the variable X。That X has never been bound anywhere。

 it's never been part of a definition here at the top level。So when I evaluate that。

 I get an unbound value error。It's the same thing going on at this point in the interpreter when I reach a variable name that has never been substituted away。

 So here I want to return an error to indicate that this variable was unbound。

I've introduced an error message here that we can now fail with if we get an unbound variable。

Why did I bother factoring that out to give it a name？

It's because when there are errors that are expected as part of an interpreter and therefore we want to test for them later。

 I'd rather use a name for that error message than hard coding the string in my test file later。😡。

That reduces duplication。In fact， you can see that in my test file here。

I'm going to eventually have a test case here for an unbound variable。

 and the expected return for that is going to be the unbound var error。

 I didn't have to put the same string in both my test file and in my evaluator。Of course。

 I didn't really need to give the variable here a name I could have just written underscore because I never need to look at what that variable name is。

😡，Next let's implement let expressions We know exactly what to do for these。

 we worked it out by defining the single step relation on the slide before。

So the final line of that pattern match takes a step of the binding expression。

When it hasn't yet reached a value。But the next to last line， when E1。

 the binding expression is a value， we'll take that step of execution by reducing down to the body expression E2。

At the same time as doing that step， it does the substitution as well。

 so we pass E2 along with E1 and X into the subs function。😡，That's defined up here。

 Sub E V X is E with V substitute for x。 So when we use it down on line 25。

 what we're saying is this is。E2。With。E1， substituted for x。And of course。

 we know that E1 here is a value because that was part of the guard of the pattern。

So now we just need to implement substitution。😡，We've already worked through that on the slides as well。

 It's just a matter of putting that math into code。All right。

 the first thing I'm going to do is pattern match against the expression E that I'm doing the substitution on because that's how substitution was defined。

 it depended on the exact syntactic form of the expression。

So we've got four cases for variables in induced binary operators and let let's handle each one of those separately now。

We know how to substitute inside of integers that was the easiest case。

There is no substitution to be done， so I can just return the expression E that was passed it。

What about for a binary operator？What we know for that。

 we just need to recurse down into the two sub expressionions。

So I'm just calling subs recursively on E1 and E2， passing in V and x still。

 and then forming a new binary operator node with the result。Variables。

 we know that we need to do the actual substitution if we encounter the same variable name。

 but leave the variable name unchanged if it's different。😡，Let's implement that。

So if x and y are the same variable name， the same string， the same identifier。

Then we do the substitution and return V。Otherwise。

 we leave the expression E that was passed in unchanged， it will still be var y。

The last piece of this is implementing the let substitution。Let's pause here。

We know that no matter what we always do， the substitution inside of the binding expression。

So I'm going to go ahead and substitute v for x inside of E1 first that gets me E1 prime。

But what I do next depends on whether I have found a rebinding of the same variable。

If I did find the same variable name， then what we learned before is we should stop substituting now。

 we should not do any substitution inside of the body expression E2。😡，On the other hand。

 if they were different variables， we should go ahead and do the substitution。

So we do recurse down into the body expression E2 and do the substitution of V for x and produce a new let node on our way back out。

Now we've implemented all of the evaluation for our calculator language with let expressions。

I do have a test file here with some basic tests for it， and I can run those。😡，And they all pass。

 yay， we've successfully implemented let expressions。



![](img/5926d364919c8aa160bc7e0c524b1cd4_10.png)