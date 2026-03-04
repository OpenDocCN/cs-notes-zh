# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P189：-189-Type Safety Chap9 Video 36.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

I've mentioned a few times now that the goal of type checking is to ensure that runtime errors don't happen。

Nonetheless， we saw when we implemented the interpreter that had type checking that we had to provide branches for runtime errors in。

The notion that a type system can prevent those kinds of errors is something that we prove on paper rather than something we convince Ocael of。

The kinds of evaluation errors we're looking to prevent can be described as those in which evaluation gets stuck。

So evaluation of an expression E is stuck if E is not a value， but E can't take a single step。

 so we're back to the single step model here in order to give this definition。😡。

That means it's stuck because it's not yet reached a value。 Computation is not yet finished。And yet。

 there's no way to continue going forward from there。So a little more precisely。

 the goal of a type system is to guarantee that no expression gets stuck during evaluation。

There's a name for this， it's called T Safety。Type safety means never getting stuck。

And you can actually divide type safety up into two pieces。

 Those pieces are called progress and preservation。

Progress says that an expression can always take a step。Unless it's already a value。

Preservation says that taking a step never changes the type of an expression。

So to state those a little more carefully。Preservation says that if an environment shows that an expression has type T。

And if that expression takes a single step to a new expression E prime。Then in that same environment。

 E prime still has that same type。So stepping preserves typing。Here's an example of that。

Suppose you had the complicated expression 10 plus1 plus 5 plus6。

Well we know that that takes a single step， reduces the 10 plus 1 to an 11。And indeed。

 11 plus 5 plus6 continues to have type int。Progress says that if an expression has a type T。

Then one of two things is the case。Either E is already a value。

Or there exists another expression E prime such that E takes a single step to E prime。So for example。

 10 plus1 plus 5 plus6 that has a type int。And there does exist in E prime that it takes a step to。

 which we saw in the previous slide。Progress doesn't say anything about badly typed expressions。

 so X cannot be given type in in the empty environment。But that's okay。

 progress doesn't say that x is a value or that it must take a step because it has no good type。

In fact， this is a expression that would produce a runtime error。

 and so it's a good thing that we can't give it a time。



![](img/ef8cd8aaa0ece47642b6298d9e6b9bb5_1.png)

Finally， notice that that empty environment in the statement of progress is actually important。

 we can't extend it to arbitrary environment。😡。

![](img/ef8cd8aaa0ece47642b6298d9e6b9bb5_3.png)

For example， if we started off in the environment that did have x bound to end。

 then we would be able to conclude that that is well typed because x does have type into that environment。

But x is not a value， and x does not step。So it's important for progress that this be an empty environment。

To prove type safety， we can use progress and preservation together。

So here's a sketch of how such a proof would work。Our claim would be that well typed programs don't get stuck。

 that's what type safety means。So we begin by assuming that the program is well typed。

And we proceed by induction on the number of steps it will take to reach a value。😡。

The base case is zero。 There are zero steps remaining till we reach a value。

 So we've already got a value。Well， since it's already a value。

 it's not stuck because stuck means not being a value and not being able to take a step。Okay。

 so that case of the proof would be done。In the inductive case。

 we would have one or more steps remaining。Well。Progress。Says that if a program is well typed。

 then it can always take one step。So we can take that next step。

Now there might be zero or more steps remaining， but we took at least one。By preservation。

 when we took that one step。The new expression we reached is still well typed。Well。

 that means the inductive hypothesis from this induction applies because we have a well typed program。

 but it has one fewer number of steps to take until it reaches a value。And so by induction。

 that new well typed program will not get stuck。😡，And so we're done。

Now this is not a kind of proof that I expect you to be able to do in this class。

 I just wanted you to see the structure of such a proof。

 if you're interested in knowing more about them， take CS4110。But this is the goal。

 this is why we have type systems。 They ensure that our well typed programs don't get stuck during evaluation。

😡。

![](img/ef8cd8aaa0ece47642b6298d9e6b9bb5_5.png)