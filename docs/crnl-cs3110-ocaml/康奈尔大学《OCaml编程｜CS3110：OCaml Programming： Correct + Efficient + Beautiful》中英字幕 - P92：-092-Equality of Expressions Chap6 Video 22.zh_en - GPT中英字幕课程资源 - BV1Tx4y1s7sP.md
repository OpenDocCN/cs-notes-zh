# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P92：-092-Equality of Expressions Chap6 Video 22.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

But what does it mean to prove the correctness of a program， how do you do that？

We start from the standpoint of a specification。So here's a program that competes factorial。

 actually I haven't given you the body of the function， but I haven't given you its specification。

That specification has a post condition in it， and as I've been teaching you this semester。

 the way I prefer to write these kinds of post conditionsition is as equalityal。

 an equality between the function output and some other description of it。

 which usually is a mixture of English and mathematics。

 describing how the output is related to the input。Well。

 our correctness proofs are going to be based on equality between expressions。

 much like how our specifications have been based on that notion of equality。

Now it's really hard to reason about equality between code and English like how do you know that a piece of Oaml code actually correctly implements some English language sentence。

 that's a really hard problem， we're not going to tackle that。

What's easier is the reason about equality between two pieces of code。So as we go along。

 we'll see ways of treating one piece of code as the specification and another piece of code is the implementation。

But right away， what that means is we need a way to think about equality between expressions。

 equality between pieces of code。Now I'm not asking here about Ocall's Boolean equality。

 that's not the notion that I have in mind when I write this equals sign。😡，Rather。

 I'm asking about when two pieces of code are equal。😡。

So here's an example that helps us think about that。😡。



![](img/12ad6164231d6e31730197d1bbd8c850_1.png)

Is 41 plus 1 equal as a piece of code to 42？

![](img/12ad6164231d6e31730197d1bbd8c850_3.png)

There's at least a couple different answers we could give to that question。



![](img/12ad6164231d6e31730197d1bbd8c850_5.png)

One is the syntactic answer。These syntactically are not the same pieces of code。

You could represent them as trees， for example， as you learned in 20110。

 to represent Java expressions as trees。Well， the tree containing a node with plus and then sub childrenildren。

 41 and1， that's clearly not the same tree as 42。

![](img/12ad6164231d6e31730197d1bbd8c850_7.png)

So syntactically， these are not the same。

![](img/12ad6164231d6e31730197d1bbd8c850_9.png)

Semantically。They both evaluate。To the same value。That is the notion of equality on code that I have in mind here。

😡，Two pieces of code are equal if they evaluate to the same value。



![](img/12ad6164231d6e31730197d1bbd8c850_11.png)

Now that was for a fairly simple expression。Let's look at a slightly more complicated expression。

What about functions？

![](img/12ad6164231d6e31730197d1bbd8c850_13.png)

Here are two versions of the identity function。Is fun X arrow X equal to fun Yarrow Y。Well。

 once more， syntactically， the answer has to be no。

Because there are two different variable names in use here， X and Y。



![](img/12ad6164231d6e31730197d1bbd8c850_15.png)

Semantically， that's a little harder of a question to answer because what does it mean for functions to evaluate to the same thing？

We don't really have a crisp answer to that yet。Well， there is an answer to it。

And it is that both functions will always evaluate to the same value when past to the same input。😡。

Or in other words， for all values V， if you take fun X0 x and apply that to V。You get V。😊，Likewise。

 if you take fun Yarrow O Y and apply that to V， you get V。So for all values。

 the two functions produce the same output。

![](img/12ad6164231d6e31730197d1bbd8c850_17.png)

That is a notion of equality on functions that is calledexality。

Extenctionality is well known from mathematical logic。

 you might or might not have encountered it before。

 but that is the notion of equality we will use on functions。

So two expressions E and E prime are equal if they evaluate to the same value。

Now there is some fine print here that I have to give as a caveat， but I don't want to focus on it。😡。

These two expressions must be well typed， we're not going to think about badly typed expressions。

 they must be pure in the sense that I talked about before and they must be total。

 which is to say they must terminate。And not raise exceptions。



![](img/12ad6164231d6e31730197d1bbd8c850_19.png)