# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P17：-017-Recursive Functions Chap2 Video 12.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Here's another piece of syntax related to function definitions。In Ocamel。

 you must explicitly state that a function is going to be recursive by adding the rec keyword in between let and the name of the function。

😡，This is a design choice in Ocael。 Other functional languages have made different design choices。

 There are some arguments for doing it this way， but they're not terribly important。

The most important thing is just to remember to put that wreck keyword in。



![](img/e7e9accf54f5267a1893154f0d5e155f_1.png)

Suppose you wanted to write the factorial function。Let factorial of N be。 Well。

 what is it to take a factorial？If n is zero， zero factorial is1， so return one。Else。

Now if n is not zero， if it's bigger than zero， then what do we do。

 We take n times the factorial of n minus1。ok。Of course。

 I should probably document a precondition that says， and。Wirres。

N is greater than or equals to0 because otherwise people might call this with a negative number。

 and that would be on me。Okay， what is the little squiggly going on here？

That's telling me unbound value fact if this is a recursive definition you should add the rec keyword online to。

Common mistake to make is to forget that wreck key word。

 You have to add it in there in order to make the function recursive。

 A couple other notes about the syntax here。 I did need to write fact parentheses and -1。

 because if I left out those parentheses， implicitly the way Ocamel understands that is that they are around here。

 which is not going to produce the result that I want。 In fact， that will result in an infinite loop。



![](img/e7e9accf54f5267a1893154f0d5e155f_3.png)

Can see that if we put this code into U。You can see we got a stack overflow there。

 what happened is that the function called itself so many times that the call stack got too big and okay we'll stop the computation。

 that looping recursion question mark is a hint to that there。



![](img/e7e9accf54f5267a1893154f0d5e155f_5.png)

So if we do want to get this right， we need to put the parentheses in the proper place to force Ocaml to parse the argument as n -1。

 not just n。 And with that change， our factorial function will work correctly。



![](img/e7e9accf54f5267a1893154f0d5e155f_7.png)

We can take the factorial of 10。

![](img/e7e9accf54f5267a1893154f0d5e155f_9.png)