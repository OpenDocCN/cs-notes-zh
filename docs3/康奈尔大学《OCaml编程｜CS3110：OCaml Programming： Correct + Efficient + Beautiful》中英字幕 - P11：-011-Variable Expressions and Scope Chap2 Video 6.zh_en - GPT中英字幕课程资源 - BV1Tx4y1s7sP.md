# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P11：-011-Variable Expressions and Scope Chap2 Video 6.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/3c0a0171dad26438471e930678bf9d93_0.png)

We've seen before that it's possible to evaluate a name just by itself。



![](img/3c0a0171dad26438471e930678bf9d93_2.png)

For example， I could say let a x equal 42。And then evaluate x。

 So how does X itself come to have meaning here in the top level。Well。

 the way to think about that is that implicitly every let definition in that top level is actually like just the beginning of a let expression。

Implicitly， when I say let x equal e， what I'm really saying is in the rest of what I'm going to type in the future in U。

So if you have a bunch of let definitions in a row， like A is big， B is red。

 and then C is a can cat B， what that really gets understood as is equivalent to let a equal big in。

Let B equal red in。Let's see equal A canca B in， and then we're going to continue on with whatever else is typed in the future。

Given that。We can now understand evaluation of just variable names。As substitution。So really。

 when I said let x equal 42 here。Anywhere else I put X in the future in Utah that's going to be understood as a substitution。

 just as it always is for lead expressions， so that x is going to get substituted away and replaced by 42 anywhere else it occurs in the future。

So ultimately， it's really just a substitution inside of a giant nested lead expression。

Let's return to the notion of scope。Scope is where a name is meaningful。😡。

And inside of large nested lead expressions， names will be meaningful in some places and not in others。

If we say let x equal 42 in， then in that body expression， x does have a meaning。

 but not outside of it。We have a nested interlet expression here， let y equal 3110 in。

Why is meaningful in the scope of that inner lead expression。

 but it's not meaningful in the scope of the outer lead expression。

So lead expressions are what give us the delimitation of scope inside of an Ocal program。

What can get confusing is if we have overlapping scope。Here， for example， is a。

Program that looks a lot like one I alluded to earlier。

In which I've got overlapping scopes for the name X。 let x equal 5 in， let x equal 6 in X plus x。

 It's a little bit of a brain twister to try to figure out what that means。

Now it does have a well defined meaning， but first off， let me just say it's darn confusing。😡。

And so we should try as we write programs for other humans to understand to avoid this kind of hard to think about program。

But now that we have a semantics in particular， evaluation rules for lead expressions。

 we can figure out the meaning of this programs and others like it。The meaning that they have。

Ad heres to something that I'll call the principle of name irrelevance。As far as I know。

 I'm the only person who uses this term， but I think it's a pretty good one。To me。

 the principle of name irre says the name of a variable should not intrinsically matter。😡。

Let me put it in the context of math。 If you open up a math textbook and you have two functions。

 F of x equals x plus1 versus F of y equals y plus 1。

 I think most people are going to agree that these are the same function。They both do the same thing。

 They both add one to their argument。So the name of the argument was not actually relevant to what the function truly means。

To ensure name irrelevance in programs。We actually have to behave very carefully when we're doing substitution。

Which is we need to stop substituting when we reach a binding of the same name。Now。

 much later in the semester， I'm going to give a very careful definition of what I mean by this and we'll even implement it as part of a program。

But for now， this is a good enough explanation for us to do some examples。Suppose。



![](img/3c0a0171dad26438471e930678bf9d93_4.png)

We had a program， let x equal 5 and let x equal 6 in x。 What does that actually mean？Well。

 we've now developed enough to figure it out。Evaluate five to value。5ve。

And then substitute phi for x。Well， that would mean taking let x equals6 in x and substituting5 for x。

 What does it mean to substitute 5 for x in it？

![](img/3c0a0171dad26438471e930678bf9d93_6.png)

We just agreed on what it means， it means stop substituting when you reach a binding of the same name。

😡。

![](img/3c0a0171dad26438471e930678bf9d93_8.png)

We did， we just reached a binding of that same name X， so we stop doing any substitution。

 we don't touch the rest of that body expression。😡，So let x equal5 and let x equal 6 in x。

Means we now need to evaluate let x equals 6 and x。

 and we know how to do that that just evaluates to 6。

 So that's the result of evaluating that entire let expression。



![](img/3c0a0171dad26438471e930678bf9d93_10.png)

And we see an unused variable warning here。 We've seen that once before。

 Now it makes a little more sense。 Actually， what O Campbell is doing is saying that first binding of X to 5。

 you never used it。 It just got thrown away。 It got dropped on the ground。

 because substitution stopped at that inner let expression that bound the same name X。



![](img/3c0a0171dad26438471e930678bf9d93_12.png)

The outer one was never used。That's not to say we couldn't use it。For example。

 we could say let x equal 5 in x plus。Let x equal 6 and x。 And now we would have。

A substitutestitution to perform， substitute 5 for x。 But then stop。

 Don't descend any further into that nested lead expression because it binds the same name that we're already substituting for。

That would give us5 plus 6， and the result of the whole thing would be 11。



![](img/3c0a0171dad26438471e930678bf9d93_14.png)

Let's just double check that inside of UTop。Indeed。

 we get 11 and we don't get an unused variable warning this time。

Because we did actually use the binding of x25 in evaluating that entire expression。



![](img/3c0a0171dad26438471e930678bf9d93_16.png)

![](img/3c0a0171dad26438471e930678bf9d93_17.png)