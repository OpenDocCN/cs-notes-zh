# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P186：-186-Adding Types to SimPL Interpreter Chap9 Video 33.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's implement the type checker for simple。We'll start with the AST here。

 we know that we need to add type annotations to let expressions。

 so we'll need to represent those as part of the tree。

I've now introduced a kind of type in Ocal here to represent simple types。

 so all the different meta levell representation of types can get a little confusing here。

 but we have an Ocal variant type named tip TYP The reason I used tip instead of the word type is。

 of course， that type is already a reserved word in Ocal I would not able be able to use it syntactically there So I went with tip。

😡。

![](img/d8d51d44c48ac3153634bf4fc4d39e09_1.png)

![](img/d8d51d44c48ac3153634bf4fc4d39e09_2.png)

And I named the constructors of that type， T int and T Bool。

 I had to disambiguate them from int and bool， which I already have as part of the expert type。😡。



![](img/d8d51d44c48ac3153634bf4fc4d39e09_4.png)

![](img/d8d51d44c48ac3153634bf4fc4d39e09_5.png)

Finally， I added in one additional component to the tuple carried by let。

 it now contains a type as well。

![](img/d8d51d44c48ac3153634bf4fc4d39e09_7.png)

![](img/d8d51d44c48ac3153634bf4fc4d39e09_8.png)

I will need to extend my parsse and Leer to handle types。😡，So I've added three tokens。

 I now have colon because I need to write colon a type as part of a lead expression。

 and I have the int type token and the bo type token。



![](img/d8d51d44c48ac3153634bf4fc4d39e09_10.png)

![](img/d8d51d44c48ac3153634bf4fc4d39e09_11.png)

And I've now added to the let production colon type。

And that type production itself will either be the int type or the rule type and will return the corresponding AST node for either of those types in the Leer I just need to add in the production of those token。

Let's pause there and build our code and see what happened。



![](img/d8d51d44c48ac3153634bf4fc4d39e09_13.png)

As we might have expected， the immediate error we get is that let expressions now are missing one component。

 which is the type， so we'll need to go back into our evaluation for the simple language and fill in those missing places。

So there were really only two places we needed to fix up the substitution function and the evaluation function in substitution。

 there is nothing to do。 there is nothing to substitute inside of a type。

 so we just carry that type T through the substitution。In evaluation， we do have a type T。

 but we don't actually care about that type at runtime。 We're sort of done with it by then。

 T checking is all we really cared about for that type。 In fact。

 T is never used on the right hand side of the sub expressionpression here。😡。

So what we can do is just write on your score there to ignore whatever that value is。



![](img/d8d51d44c48ac3153634bf4fc4d39e09_15.png)