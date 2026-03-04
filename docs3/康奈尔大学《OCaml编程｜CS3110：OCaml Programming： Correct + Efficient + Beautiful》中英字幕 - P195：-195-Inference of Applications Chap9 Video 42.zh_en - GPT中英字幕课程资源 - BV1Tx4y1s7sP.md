# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P195：-195-Inference of Applications Chap9 Video 42.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

How about function application？Well to infer the type of E1 applied to E2。

We're going to conclude that it has T tau with some constraints， C1， C2 and C。

 here's where all of those come from。First， tau needs to be a fresh type variable。

The reason we're introducing that here is because once more。

 looking at this algorithmically and not really descending into E1 or E2 yet。

 we have no idea what the type of that application ought to end up being。

 so we're just going to pick a new type variable and then figure out some constraints on that variable to make it correct。

😡，So how do we figure those out？Well， we'll do type inference for the two subexpressions。

 so we'll infer a type for E1 that'll be t1 with some constraints C1。

 and we'll infer a type T2 with some constraints C2 for sub expressionpression E2。Finally。

 we pull it all together by adding a constraint。😡，On T 1， T2 and tau。

And that constraint is that T1 must be a function type。Now why does T1 have to be a function type。

 because we've used it as a function， it's on the left hand side of a function application。Okay。

 and then the input and output of that function type， Well， the input must be T2， why。

 because we've applied that function E1 to expression E2 and the type of E2 is T2。😡。

So here T2 is the type of the input to the function。Finally， what's the output of the function？

We have no idea， really。 That's where that type variable that we introduced comes in。

 That stands for that unknown output type of the function。

So we record the constraint that T1 must be the type。😡，T 2 arrow tau。

And we add that into all of the constraints that we also could have gotten from inferring the types of E1 and E2。

 Let's see an example of that。

![](img/cbc1d87bcd09735e32b78ef40a20985c_1.png)

What I'd like to do is infer the type of the partial application of plus to one。😡。

I'm going to write I here for the initial static environment that binds not just plus but also times and less are equal to。

 just so I don't have to keep writing down so many characters in this。

So to infer the type of this function application， we'll introduce a new type variable and we'll also infer the types of its subexpressions。

Inferring the type of the left hands of expression， it's just the name。

 It's just the name of the binary operator plus。 So we look that up inside of the initial static environment。

 which of course， tells us that it has type int， arrow int， arrow int。

And the name inference generates no new constrain。Type inference for the argument， of course。

 is straightforward， it's just an integer constant。And now we need to add in a new constraint。😡，Okay。

 so let's pause here， I've introduced a type variable alpha to stand for the type of this entire function application。

And I'm trying to build the constraint C on alpha。

![](img/cbc1d87bcd09735e32b78ef40a20985c_3.png)

So what does my rule say？It says that the type of the function。

 the left hand piece of the function application， the E1 in other words。😡。



![](img/cbc1d87bcd09735e32b78ef40a20985c_5.png)

Int， arrow， int， arrow， int。Must be equal to something else。 So next it needs to be equal to T2。

 So here that's int。

![](img/cbc1d87bcd09735e32b78ef40a20985c_7.png)

![](img/cbc1d87bcd09735e32b78ef40a20985c_8.png)

Arrow。Whatever type variable I introduced， here I called it alphapha， so thatll be alpha there。



![](img/cbc1d87bcd09735e32b78ef40a20985c_10.png)

![](img/cbc1d87bcd09735e32b78ef40a20985c_11.png)

So I'm left with in inter int。Equals inro alpha。Now。

 I could just copy that constraint up here if you like， I could simplify this a little bit。

 I wouldn't need to write that there。Okay， so now we've finished inferring constraints for this program。

 we haven't really fully reconstructed the type yet， we need to solve the constraints to do that。😡。

Let's once more use our brains to do it instead of doing it algorithmically。

When I look at that constraint there， I see that there's an int on the left hand side of an arrow。

 right， So there's an int here and an int here。 I could get rid of both of those ints and then say that int arrow int must be what alpha is。



![](img/cbc1d87bcd09735e32b78ef40a20985c_13.png)

![](img/cbc1d87bcd09735e32b78ef40a20985c_14.png)

So then I would be able to say that the type of plus applied to one is int arrow int。

And that's correct， right， When we've partially applied the plus operator to one argument。

 we're going to get back a function that is waiting to take in the second argument。

 then then give us back the output。O。So multiple times now。

 we've been able to use our human brains to solve these constraints and to finish type inference。

Our next task is going to be building an algorithm to do that with the computer。



![](img/cbc1d87bcd09735e32b78ef40a20985c_16.png)

![](img/cbc1d87bcd09735e32b78ef40a20985c_17.png)