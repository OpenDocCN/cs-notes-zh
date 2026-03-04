# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P174：-174-Core OCaml Small Step Chap9 Video 21.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now that we've implemented an interpreter for simple。

 let's continue to scale our semantics up to an even bigger fragment of Ocal。

 I'm going to call this fragment core Ocael because it contains almost all the really core features of the functional programming language of Ocal。

What we've added next is functions and application those were missing from simple。😡，Pairs。

 including construction of pairs and taking the first and second component of them。Pattern matching。

I've hard coded only two constructors here， left and right。

 and we can do a pattern match against those two。And for values， we now have functions as values。

 pairs of values are themselves values， and a left or right constructor applied to a value is a value。

Next， let's cover the small step semantics for core Ocal。For functions。

 E1 applied to E2 takes a small step， a single step of execution to E1 prime applied to E2 if E1 takes a single step to E1 prime。

A value V1 applied to E2。Steps to V1 apply to E2 prime if E2 itself steps to E2 prime。Finally。

 when we get down to both expressions being values， the first one must be a function。😡，Of course。

 a type checker would reject the program if it had not been a function。

So that will step to the body of the function E。😡，With the argument value V2 substituted for the functions argument name X。

Pairs are pretty straightforward。 The pair E1 E2 takes a single step to E1 prime E2 if E1 steps to E1 prime。

Once we have a value as the first component of the pair。

 we can then start stepping the second component of it。First。

 applied to two values gives you back the first of them。

 Second applied to two values gives you back the second。For constructors。

 we simply step the expression inside the constructor。

 whether that's the left or the right constructor。And for pattern matching。

 it gets a little hard to write this down on one slide because the expressions get so big。

 but first we step the expression E that's being used between match and with here。😡。



![](img/ca58f61888dfaddccdf7f698efed9218_1.png)

![](img/ca58f61888dfaddccdf7f698efed9218_2.png)

Then if we eventually get down to a value left V。

![](img/ca58f61888dfaddccdf7f698efed9218_4.png)

We're going to step that to the branch corresponding to the left constructor。

 so that's the branch with x1 and E1。And that will step to E1 with the value V that was inside of the matched expression substituted for the variable x1 that's the pattern variable there that's being bound。

Of course， the symmetric thing happens for right as well。

 that's going to step to E2 with V substituted for x2。



![](img/ca58f61888dfaddccdf7f698efed9218_6.png)

We've used substitution a few times now in pattern matching and in lead expressions。

We need to give a definition of substitution for core Ocheml。 We'll do that next。



![](img/ca58f61888dfaddccdf7f698efed9218_8.png)