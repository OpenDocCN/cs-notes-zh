# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P159：-159-Calculator_ Addition Chap9 Video 6.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's move on to our next unit test， which is addition。

So now my goal is to be able to evaluate 11 plus 11。

Let's check and make sure that fails at this point。Indeed， it does， in fact。

 we can't even lex it because it has a plus sign in it。So we're going to go back and fix all of that。

In our AST， we now need to be able to represent binary operators like plus。



![](img/27ded28b91303152d0f34b0bdbce9d2f_1.png)

So I'm going to go ahead and add a bin op constructor here to represent binary operators。

 and it's going to carry along with it what the binary operator is。

 it's either going to be plus or times and the two sub expressions on the left and right of that。😡。



![](img/27ded28b91303152d0f34b0bdbce9d2f_3.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_4.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_5.png)

Now of course I need to define a type here for binary operators and so that'll just be a variant。

 that's kind of like an enum that just has a couple constant constructors in it for add and Mt。



![](img/27ded28b91303152d0f34b0bdbce9d2f_7.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_8.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_9.png)

Okay， so now I have an expression node for representing plus and times as well。



![](img/27ded28b91303152d0f34b0bdbce9d2f_11.png)

Since I'm not going to implement times yet， I'm going to leave that line comments it out for now。



![](img/27ded28b91303152d0f34b0bdbce9d2f_13.png)

In the Leer， I now need to be able to recognize plus tokens as well。



![](img/27ded28b91303152d0f34b0bdbce9d2f_15.png)

So I'm going to add what's called the production here to this parse rule to be able to recognize when I see a plus character。

 I want to return a token， which I'll just call the plus token all in caps Now of course I need to create that token over here in my parser So as part of the parser I will put in here a new token declaration of the plus token。



![](img/27ded28b91303152d0f34b0bdbce9d2f_17.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_18.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_19.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_20.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_21.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_22.png)

And I need to be able to parse that as part of an expression here。 So let's have E1。

 which is a sub expressionpress。

![](img/27ded28b91303152d0f34b0bdbce9d2f_24.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_25.png)

Followed by the plus token， followed by E2， which is another sub expression on the right。

 And when I get that， the Ochemel value I want to return is the binary operator with add E1 and E2 inside of it。



![](img/27ded28b91303152d0f34b0bdbce9d2f_27.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_28.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_29.png)

At this point， I ought to be able to parse plus expressions。

 So let's go ahead and give that a go in U top just for a second to see whether parse is working。

 So can I parse now one plus one。

![](img/27ded28b91303152d0f34b0bdbce9d2f_31.png)

![](img/27ded28b91303152d0f34b0bdbce9d2f_32.png)

So O can， and that gets me back the ASD containing a binary operator， which is add with two subtes。

 the integer  one and the integer  one beneath it。Of course。

 I can't yet evaluate that or interpret it because I haven't implemented stepping。😡，4 plus， in fact。

 if you look at what happens when I run make build here， you're even going to see。

 I got a bunch of errors here。 Some of them were saying things about pattern matching not being exhaustive。

 That's because when I added this AS T node for binop。



![](img/27ded28b91303152d0f34b0bdbce9d2f_34.png)

Everything in here that was pattern matchinging against just int suddenly became inexhausive。

So what's awesome about building my interpreter this way is every time I add an AST node to that type。

😡，I get it to do list that the compiler automatically figures out for me。 The Oamml compiler。

 that is right， It's looking at this and saying， oh yeah， you added a new AST node。 Well。

 here's all the places you need to go fix next。This is one of the reasons that we sometimes discourage you from writing catch all cases and pattern matches if you had a catch all case in any of these。

 it wouldn't give you this to do list。All right， so let's go back and finish writing each of these pattern matches to account for the fact that we now have binary operators。

All right， now all my pattern matches are exhaustive。For string of vow。

 if a bin op is ever passed in there， that violates the precondition because E has to be a value。

For is value。Any binop is not a value， so we return false。And for step。

 now we need to implement taking a step to do an addition。

The way I'm going to choose to implement this is leftmost。😡。

So if the left hand side of a binary operator can be simplified a bit。

 I'm going to do a little bit of simplification there。

And then if the left hand side is already all the way down to a value。

 then I'll start working on the right hand side， so I'll implement some pattern matching branches to do that。

Let's pause here。I've done what I said， I would do。

If I've got a value on the left and the right hand side already of the binary operator。

 then I've left that to do at this point， but that's where I'm going to finally reduce and simplify the whole thing and get rid of the binary operator。

😡，But if the right hand side is not yet of value， then I'll step the right hand side。And finally。

 if the left hand side is not yet a value， I'll step the left hand side。

 So notice this forces me to do things left first， because this pattern in the middle is only going to match once the left hand side is already a value。

 So until the left hand side is a value， I'm going to end up going down to the very final pattern matching branch and stepping the left hand side。

Okay， now for reducing the case where both the left and the right hand side are already values。

 let me implement a helper function to do that。😡，Okay。

 I've implemented my helper function here to step a binary operator as a precondition。

 both of the arguments passed to it have to be values。😡，We only have one operation so far。

 which is add， so there's really only one branch that's meaningful right now， an add of two values。

 which is an integer and another integer。😡，To implement that。

 I just use the OcaMl Priitive Ed operator。So notice what's going on。

 I'm reducing addition from the source language， my silly little calculator language down to addition in Ocal。

 that's not really cheating any more than compiling a plus in OcaMl would be down to the plus operation that's implemented on the hardware beneath it。

😡，It's all just reducing things down to a lower level。

 and here we're reducing the calculator language down to Ocal and our interpreter。So for this case。

 I can actually fail with precondition violated。Because the only other way to get into this pattern matching branch is to have an ad that does not have a value on either the left or the right hand side。

Now we should be ready to make our test case pass。Yay， it does pass。

