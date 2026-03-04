# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P182：-182-Remaining Core OCaml Environment Model Chap9 Video 29.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Now we can scale up the big step environment model to all of core Ocal by adding in pairs and pattern matches notice that our values now contain function closures。

 which themselves contain environments。

![](img/37d6194af115926f49cd8214461a5c07_1.png)

![](img/37d6194af115926f49cd8214461a5c07_2.png)

So we have a situation much like we had with references and locations earlier。

 where we have a kind of value that can't be written in the syntax of the language。

 so this is another example of how sometimes not all values are themselves expressions。

The semantics of pairs is really quite straightforward。

 everything in black here is the same as it was before we started using environments。

 it's just the orange that's new and all that is is taking that current dynamic environment and using it to evaluate each component of the pair。

The same for first and the same for second。For constructors， it's exactly the same thing too。

 we just keep pushing that dynamic environment through whether it's the left constructor or the right constructor。

And for pattern matching， it's almost exactly the same as before。

 except for that now when we get to evaluating a branch and an expression， either E1 or E2。

 we do actually extend the dynamic environment to map the pattern variable to the value of the expression being matched。

 so here if we're matching E and E evaluates to the value left v。

 then when we evaluate E1 because we should match against left here。

 we're going to extend the environment to map X1 to V and it would be the same symmetrically if we were evaluating a right pattern。



![](img/37d6194af115926f49cd8214461a5c07_4.png)

![](img/37d6194af115926f49cd8214461a5c07_5.png)

You might be wondering， where is the code for the big step environment model interpreter for Co Ocael。

 Well， the answer is， you will write it。For at least the last five years， if not 20 years。

 we've always had an interpreter assignment in 3110 in which you implement some substantial fragment of Ocal or a closely related functional language。

 I expect the same will be true this year。

![](img/37d6194af115926f49cd8214461a5c07_7.png)