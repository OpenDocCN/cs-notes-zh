# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P93：-093-Equational Reasoning Chap6 Video 23.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

What we're going to do next is what I call equational reasoning。

 although this is just giving a fancy name to a very simple concept。😡。

It's reasoning about the equality of two programs using that notion of equality on expressions that we justify。

Let's start with an example involving higher order functions。

Back when we learned higher order functions， we studied the function twice。

 which applies the function F to its argument X twice， we also learned about function composition。

 for example， if you want to compose two functions f and G。

 you could define that as apply G to X and then apply F to that to compose those two functions。Well。

 let's notice something here。If you run twice Hx for some function H and some input X。

 what does that evaluate to？We know from studying the evaluation semantics of Ocal that we substitute H for F。

 and therefore we get H applied to H X。Well， suppose you took composeose and passed H in as both its first and second arguments。

 that is as both F and G。Then that would evaluate to H applied to H applied to x。

So both of these pieces of code involving twice and compose end up evaluating into the same intermediate expression。

😡，Therefore， twice HX equals compose HHX。Why is that。

 Well you can follow it by transitivity from twice to HHX to compose。

All of these are going to evaluate to the same value。That's why they're equal。

Here's another way of structuring the claim that I just made。

 and it's a widely known proof format in the field of verification。

 It's attributed to a person named Vim Fayan。

![](img/83cb016c6ea37e017d2cbbe18d6b526f_1.png)

We start at the top with one piece of code。We end with another piece of code at the bottom。

And there's a transitive chain of equalities between them。 Those equalities are out dented。

 and the code is indented。

![](img/83cb016c6ea37e017d2cbbe18d6b526f_3.png)

And on each line where we write inequ， we don't write code with it。

 instead we write a justification of the proof step。



![](img/83cb016c6ea37e017d2cbbe18d6b526f_5.png)

![](img/83cb016c6ea37e017d2cbbe18d6b526f_6.png)

I'm going to put those justifications in curly braces， although of all the variants on this notation。

 exactly which choice of delimiter to use there is probably the one on which there's the most variation。

So I'm going to ask you to please use this proof format as you work through examples and learn this material。

 it is one that's part of the vocabulary of this area， if you will。A second example。

Let's look at more detail at composition。So we had our compose function already。

 let me actually introduce a binary operator for it written less than less than。

 although I'll continue to pronounce it compose。The p mnemonic there is that we're kind of running things from right to left because if you have F composed G。

 well， first， when you apply that to an argument X， you run it through G first and then。

The theorem I'd like to show is that composition is associative。

That is if you have a quantity F composed G， then compose H。

 that's the same as F compose quantity G compose H。Well， to prove that。

 we're going to need to use extensionality because we're trying to prove the equality of two functions here。

So by extensionality， two functions are equal if they produce the same output when applied to the same input。

So we need to show that for all x， the expression on the left here。

 F composed G composed H applied to x is equal to the expression on the right F composed quantity G composed H applied to x。

Okay， let's do that proof， I put the claim that we want to prove up here at the top。

 and also at the very top， Ive reminded us of what the definition of composition is。

So one strategy for doing these kinds of proofs is to do them in a kind of two column format。

I'm going to start with the expression on the left。In one column。

And the expression on the right in another column。And my goal is to work to get the two columns to end up in the same place。

 take a sequence of equality steps in each of those columns。

 and eventually end up with the same expression at the bottom of both of them。

So I'll start on the left here。By evaluation， I know what's going to happen if I apply that expression to X。

And the reason I know that is because I have this definition of composition up here。

 I know that I'm going to take H and apply it to X。

 so H is fulfilling the role of F2 in the original definition。From that。

 I could take another step of evaluation because I know what Comp is going to do here。

 it's going to apply G to the result of Hx and then fly F。Now I'm kind of stuck at that point。

 there's nothing further I know about how to evaluate that expression because I don't know what FG or HR。

 I don't even know what x is。So here's where I switch over to the other column and try to make progress there。

By evaluation， I know that the result of that expression is going to be Gcomose H applied to X。

 because G composeose H is playing the role of F2 in that definition of composition。

I can take another step of computation here。That ends up with F applied to GH X。

And now I have both columns ending at the same place。 Those two expressions are the same。

So now I've shown the equality of those original two expressions on the left and right hand side。

And I can say I'm done QED， which our own professor agrees likes to Joe means quit and done What I encourage you to do next is to put away this slide。



![](img/83cb016c6ea37e017d2cbbe18d6b526f_8.png)

Just write down those expressions we wanted to prove the equality of and the definition of composition and work through the proof yourself without looking back at the slide。

 that should help instill in your brain exactly what the thought process is for doing this kind of proof。



![](img/83cb016c6ea37e017d2cbbe18d6b526f_10.png)

![](img/83cb016c6ea37e017d2cbbe18d6b526f_11.png)