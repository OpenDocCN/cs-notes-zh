# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P181：-181-Lexical vs Dynamic Scope Chap9 Video 28.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

So we now have seen lexical and dynamic scope。Lexicalcope is what you have been taught all along if you've been taking courses in Python or Java or almost any other program language。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_1.png)

After decades of programming language design， the consensus is that lexical scope is the right choice。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_3.png)

The main reason for that is it doesn't lead to surprises。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_5.png)

A programmer can change the name of a local variable without the meaning of a function changing。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_7.png)

If you think back to our example， the meaning of this program was highly dependent on how we handled the name of the variable x。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_9.png)

![](img/33483add75b6bf29a3f7bdd9b08fc2d4_10.png)

Under dynamic scope， if we change the second binding of x to say let z equal to or some other variable。

Then it would change the meaning of this program， it would change what it evaluates to。😡。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_12.png)

But under lexical scope， we are free to change that second binding of the variable x to any other variable name we want。

 and it won't affect the results of the computation。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_14.png)

That's what I mean when I say lexical scope leads to fewer surprises。

 You get to change variable names without those kinds of surprises。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_16.png)

![](img/33483add75b6bf29a3f7bdd9b08fc2d4_17.png)

But dynamic scope is still useful in some situations。

 and so some languages use it by default or offer some kind of support of it， latex， pearl。

 rackcqueet， and some others。Most languages， though， these days， just don't have it。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_19.png)

With one big exception， which funnily enough is called exceptions。If you think about exceptions。

 they are somewhat like dynamic scope。

![](img/33483add75b6bf29a3f7bdd9b08fc2d4_21.png)

Raise or throw of an exception actually transfers control to the most recent place where that exception could be caught。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_23.png)

And that's kind of like how dynamic scopepe uses the most recent binding of a variable。😡。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_25.png)

Nonetheless， I find it very difficult to think about dynamic scope because it's just not how most languages work。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_27.png)

![](img/33483add75b6bf29a3f7bdd9b08fc2d4_28.png)

In the textbook， you will find an interpreter that you can use to play around with expressions and change between dynamic and lexical scope to see how they evaluate。



![](img/33483add75b6bf29a3f7bdd9b08fc2d4_30.png)

![](img/33483add75b6bf29a3f7bdd9b08fc2d4_31.png)