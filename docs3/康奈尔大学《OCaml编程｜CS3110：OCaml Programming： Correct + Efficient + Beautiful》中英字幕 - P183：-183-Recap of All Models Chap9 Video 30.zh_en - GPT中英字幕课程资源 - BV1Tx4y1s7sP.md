# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P183：-183-Recap of All Models Chap9 Video 30.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've had a lot of evaluation relations now， a lot of models。

Let's review so we can keep them straight。We've had small versus big step models of evaluation。

In the small step model， we had an evaluation relation for taking single steps of execution that was rid with a right arrow。

E right arrow E prime meant that E steps to E prime， taking exactly one step of evaluation， no more。

 no less。We also had a multi step relation， rid rightarrow star。

 that's just the reflexive transitive closure of the single step relation。

 and so that means zero or more steps of evaluation。Our goal， of course， with this。

 was eventually to reach a value V， after which no steps were possible。

To represent kind of the beginning and ending of a multi step relation。

 we introduced the big step relation written with a double right arrow。So here。

 E big step to evaluate V or evaluate to evaluate V。😡，We weren't modeling all the intermediate steps。

Recall that we wanted a consistency here。 The big and the small steps should be consistent in the sense that E big steps to V。

 if and only if E multi steps to V。

![](img/c32db5a8a70435abab1302846df1f686_1.png)

After we introduced small and big steps， we looked at the difference between two other models。

 substitution and environment models。In a substitution model。

 we implement variables with a substitution operation。And the tricky part of that model was， in fact。

 defining substitution， in particular， capture avoiding substitution。In the environment model。

 we implement variables with a dynamic environment。 So that was a kind of lazy substitution。

And there， the tricky part was closures。Interestingly， in both places。

 what makes it hard is figuring out how to implement functions。

 whether it's how to substitute inside of a function body。

 or how to use the correct environment to evaluate a function body。😡。



![](img/c32db5a8a70435abab1302846df1f686_3.png)

These models are orthogonal。Which is to say， you can have a small step or big step model。

 as well as a substitution or environment model。 There's nothing that ties you to one pairing of those versus another。

I started off by showing you a small step substitution model。

And then I showed you a big step substitution model。Finally， I showed you a big step environment。

I passed over doing a small step and environment model is really nothing interesting I want to show you about that。

We've seen all of these as well for different languages。We looked at the language simple。

 which was like a calculator but with lead expressions and if expressions。

I've given you the math and the code for the substitution model there。

 I've given you the math for the environment。We also looked at core Ocal for that。

 I gave you the math and all three of those check marks。In the textbook。

 you will also find another language discussed。 That language is called the Lambda calculus。

 The Lambda calculus is really just functions and application and variables。

 just those three syntactic forms。And the textbook gives you the math and the code for the environment model there。

 including an interpreter that allows you to switch back and forth between lexical and dynamic scope。

I hope you get a chance to play around with that interpret。The Lambda calculus， by the way。

 is very powerful。You can use it to model all of computation。



![](img/c32db5a8a70435abab1302846df1f686_5.png)

But that's a result for a different class。

![](img/c32db5a8a70435abab1302846df1f686_7.png)