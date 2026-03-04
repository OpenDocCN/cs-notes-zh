# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p46 45_18_optional-function-patterns -BV1bw4m1D7MM_p46-

This is an optional segment where I'm going show you one more way that you can write down patterns。

 particularly with functions。 This is a style that I've never particularly liked。

 but there's nothing wrong with it and other people do like it。

 So if you want to use this you can and if not like I said， it's optional。

 So let me just show a couple examples by showing you some code remember this data type binding we had for arithmetic expressions。

 So these are trees where the leaves are constants and the internal nodes or negations。

 additions or multiplications and the most natural function you would want to write over such a data type is something that evaluates it。

 So something of type X arrow int where we produce the result of evaluating the arithmetic expression and we have this great recursive function that uses pattern matching with a case expression to do that。

 So it turns out there's another way you can write functions where the function body is just a case expression。

 So if the entire function。

![](img/59c161d8b061bdc32a05f178b9046dda_1.png)

Bod is a case expression。 You can get rid of the case expression by moving the patterns up into the function binding。

 So we already know that， in fact， when you write a function name F， you can follow that with a P。

 any pattern you want equals E。 But so far， we only did that for each of patterns because you want that pattern to match any value that might be passed to the function。

 But as you can see here with this other version of Eval， you can， in fact， have multiple。😊。

Fun F P equal E， but you don't， for the subsequent ones， Re the fun keyword。 Instead。

 you write a pipe and then repeat the function name and then put a second pattern and a second body。

 So when you put all that together， you end up with fun eval first pattern。 This second pattern。

 this third pattern， this It's shorter。 People also like that it's a little more mathematical。

 We' defining the function eval， And it has several cases。

 eval applied to a constant is this eval applied to a negation is that and so on。

 But it's just syntactic sugar for a case expression。

So just to show you one more example you see down here at the bottom， my favorite function。

 a pen and aend is itself something whose body was just a case expression。

 And now we can use nested pattern to be able to do this all at once， we can say aend。

 if the two arguments match this pattern。 So the first list is empty and the second list is any list because anything matches the variable pattern Y。

 then the result is wise。 Otherwise， if the two lists match these this pattern。

 then return x cons on to aend of x' is prime Y。 So that's another example。

 this is another way to write a pen。😊。

![](img/59c161d8b061bdc32a05f178b9046dda_3.png)

So just to generalize this and show you what's going on over here in the slides in general。

 if you had a function binding where you had fun Fx equals case X of patterns。

 you can rewrite that as I've shown you by writing multiple patterns。

 repeating the function name and putting pipes， so the pipe character between the different versions。

 if you prefer one little detail here， this is of course assuming that you don't need that variable X in any of your branches。

 you usually don't you usually pattern match it often in your case expression and then just use the variables that you bind in the variable branches。

 various branches， so that's your optional syntax if you choose to use it。



![](img/59c161d8b061bdc32a05f178b9046dda_5.png)