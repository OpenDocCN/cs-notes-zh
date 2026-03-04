# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P180：-180-Closures Chap9 Video 27.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

How are we going to implement time travel for the semantics of Oaml functions？Well。

 we'll do it by saying that a function value is really a data structure that contains two parts。

 we'll call that data structure a function closure。

The two parts of a closure are the code and expression E。

 Now this is what we have always really been thinking of a function as as just some code。

But we're going to kind of close off that code with an environment。

That environment that was current at the time， the function was defined。

So we're basically going to save the old environment as part of the function value。

And that code of the function together with its defining environment are the closure。

So we'll notate this as a kind of pair， I'll write E comma N and I'll put parentheses around it。

 but I'm going to put a set of square brackets around it as well just to emphasize that this is not an Ocal pair。

😡，In fact， a function closure is not like an ocal pair in the following ways。It's indivisible。

 you cannot write any Oaml syntax to actually access the pieces of a closure。😡，And second。

 it's inexpressible。 you actually cannot directly write a closure in Oaml syntax。 You write the code。

 the Oamml compiler figures out what the closure is from it by figuring out what environment to say。

😡，Closures are a real thing。 So if you do a search in GitHub on the Ocaml compiler source code。

 you will see all kinds of instances of where closures show up。

 We really are now looking at the kind of data structure that's used in implementing a functional language。

😡，So an anonymous function is going to be a closure。

To evaluate a function fund XROE in the environment end。That will big step to a closure。

 which saves the function itself， as well as the environment at the time the function is being defined。

To do function application， it's almost like normal function application that we came to know from the substitution model。

But we have to be careful about which environment we use and where we use it。

So to evaluate E1 applied to E2 in an environment end。

What we'll do is first evaluate E1 in that same environment end。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_1.png)

That must produce a closure because this program type checked， so E1 has to be a thumb。

So we'll look at that closure， it's going to have some code in it， fund X0E。

 and it's going to have an environment that's been saved away。

That's the environment that was in effect at the time that function was defined。

 so I'm calling this death end， the defining environment。Okay， separately。

 we'll evaluate e to the argument。😡，In the environment end。

 so we're still using the current environment at the time of the function application。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_3.png)

That gives us a value V2。

![](img/47be6ac964d85e3df12ac1c0eddb99c5_5.png)

And now here's where the magic occurs。We evaluate the function body E。In the environment， death end。

So we go back in time to that defining environment。But we updated in one way。

We update it to bind the function parameter X to the value of the argument V2。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_7.png)

![](img/47be6ac964d85e3df12ac1c0eddb99c5_8.png)

So evaluating the function body then is going to give us a value V。

 and that value will be the result of the entire function application。😡。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_10.png)

Let's do an example of this， we'll bind x to0。And then apply an anonymous function。

 Fund Y arrow x plus Y to1。Now， of course， you can look at that and probably figure out exactly what you should evaluate to。

 or you could put it in U， but let's work through what the semantics says carefully。First。

 we need to evaluate the binding expression for x。 Well， that's just a value0， evaluates to0。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_12.png)

Next， inside of an environment that binds x to0， we need to evaluate the body expression。Okay。

 so let's figure out what that is。

![](img/47be6ac964d85e3df12ac1c0eddb99c5_14.png)

To evaluate the body expression， first， we evaluate the left hand side of the function application。

 so that's the anonymous function。

![](img/47be6ac964d85e3df12ac1c0eddb99c5_16.png)

That will cause us to create a closure。So that closure contains the code of the function。

 Fund y arrow x plus Y。It also contains the defining environment that binds x to zero。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_18.png)

Okay， continuing with the function application， we need to evaluate the argument。

 let's just evaluate one。And now for the key line of the whole evaluation， really。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_20.png)

We take the function body from the closure。Which is x plus y。We evaluate that in an environment。

We start with the environment that was saved as part of the closure。

 so that it's the environment that binds x to 0。And then we extend that environment to bind why。

The function parameter。To the value of the argument，1。

So now we have an environment that binds x to0 and y to 1， we evaluate x plus y in that environment。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_22.png)

From here on it's just standard binary operator semantics。

 we evaluate x to0 by looking it up in the environment， y to 1 by looking it up in the environment。

 and getting0 plus 1 equals 1。So now we can work our way back up the recursive call chain of evaluation here。

 we know that x plus y is1， we therefore know that the application of the function to the argument one returned one and therefore the entire expression returns1。

As a third example， let's go back to the same piece of code that gave us such trouble before。

I've again annotated each line here with what the dynamic environment would be。

 We could do a whole proof tree， but it would get so big that it doesn't really fit cleanly on a slide。

 Unfortunately， Let's just push through to the dynamic environment that we get on the final line here。

 line 4。

![](img/47be6ac964d85e3df12ac1c0eddb99c5_24.png)

Which has a binding of x to2 from the lead expression on line 3。And a binding of F to a closure。

That closure contains the code for F， it also contains the defining environment at the time F was created。

 and that's from line 2， which binds x to 1。

![](img/47be6ac964d85e3df12ac1c0eddb99c5_26.png)

Okay， so now what happens when we evaluate the function application？Well。

 we'll first evaluate F to a value that is now a closure containing both code and an environment。

Will evaluate the argument，0 to evaluate。We'll extend the closures environment to map that parameter。

So the closure had X bound to 1， we extend that to bind y the variable from the function to 0。

Now we can evaluate the function body in that environment and of course。

 looking up x inside of that environment gives us one。

So this is what gives us the right answer in terms of matching the kind of scope that OCMel provides。

It's using that environment from the closure to evaluate the body。



![](img/47be6ac964d85e3df12ac1c0eddb99c5_28.png)