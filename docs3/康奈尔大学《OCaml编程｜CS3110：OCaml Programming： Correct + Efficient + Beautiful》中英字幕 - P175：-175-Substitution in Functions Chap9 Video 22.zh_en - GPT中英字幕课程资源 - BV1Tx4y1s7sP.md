# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P175：-175-Substitution in Functions Chap9 Video 22.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's try to define substitution for core Ocael。 The tricky case is functions。

 Everything else is straightforward。So how do we define substitution for an anonymous function？



![](img/19ad66c4cf03f32059434bc1c52e03ee_1.png)

Suppose we're substituting v for x inside of the function， fun x arrow E prime。



![](img/19ad66c4cf03f32059434bc1c52e03ee_3.png)

Well， we could let that be fun X ROE prime that is stop doing the substitution。



![](img/19ad66c4cf03f32059434bc1c52e03ee_5.png)

This is something we discovered before when we looked at definitions of substitution。

 we should stop substituting at a binding of the same variable name。



![](img/19ad66c4cf03f32059434bc1c52e03ee_7.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_8.png)

So since x already is the argument of this function。

 we're not going to recurse inside of it to do the substitution。



![](img/19ad66c4cf03f32059434bc1c52e03ee_10.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_11.png)

What about if we get a different variable name， So suppose we have fun Y arrow E prime and we're substituting V for x。

 Well， x and y are not the same variable here。 So it stands the reason we should recur inside of the body of that function。

 and go ahead and do the substitution of V for x inside of E prime。

 This corresponds to what we looked at in a previous definition of substitution where we would continue substituting inside a binding of a different variable name。

 Well， let's look at how this works out when we try it with two little functions。

 I've got fun Yarrow x and fun Z arrow X。 Let's suppose that x is already in scope from some outer definition that I'm just not showing。



![](img/19ad66c4cf03f32059434bc1c52e03ee_13.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_14.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_15.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_16.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_17.png)

Obviously， both of these should just return x whatever X happens to be。



![](img/19ad66c4cf03f32059434bc1c52e03ee_19.png)

Well， let's look at how our definition of substitution works with these functions。



![](img/19ad66c4cf03f32059434bc1c52e03ee_21.png)

Suppose I have a binding， let x equals z in the first of those functions， the blue one。

 fun Y arrow X。😡，Well， according to the semantics of let， that's going to step to fun Y ArOX。

 the body expression。With Z substituted for x。

![](img/19ad66c4cf03f32059434bc1c52e03ee_23.png)

And according to the definition of substitution for anonymous functions we just gave。

Since y and x are not the same variable name， we should go ahead and do the substitution of z for x inside of the function body。

That would get me the function， fun Y arrow Z。

![](img/19ad66c4cf03f32059434bc1c52e03ee_25.png)

That's going to ignore its argument， which is what we wanted these two little functions to do。

And it's going to return Z。Well Z is what x is bound to， so this is exactly the right thing。

 this is what we wanted to have happen in the end the right value is being returned。



![](img/19ad66c4cf03f32059434bc1c52e03ee_27.png)

Now what about the other function， fund Zarrow X， which I put in orange？



![](img/19ad66c4cf03f32059434bc1c52e03ee_29.png)

Well， if you work through the definition of substitution here。

 we're going to get to substituting z for x inside of that function。



![](img/19ad66c4cf03f32059434bc1c52e03ee_31.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_32.png)

But since Z is the argument already being bound by that function。

 we're going to stop and not recurse inside of it。

![](img/19ad66c4cf03f32059434bc1c52e03ee_34.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_35.png)

But look what just happened。We got the identity function at this point。

 This function does not ignore its argument。😡，It returns whatever's past to it。

So these two functions are not the same function， they will not behave the same way in all contexts。

There's something broken here with our definition of substitution。



![](img/19ad66c4cf03f32059434bc1c52e03ee_37.png)

So let's take a closer look at that second example。 I've color coded the variable name here。

 Z to indicate the difference between where it's been bound。

 The orange Z was bound somewhere outside of this scope。 We're not showing it here。



![](img/19ad66c4cf03f32059434bc1c52e03ee_39.png)

The red Z is being bound by the function。When we do the substitution。

 we're letting the orange Z get clobbered by the red Z。



![](img/19ad66c4cf03f32059434bc1c52e03ee_41.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_42.png)

The technical term here is captured。X and Z are actually different variables。

 but the broken definition of substitution captures the orange Z and makes it be the same variable as the red Z。

 It breaks the way we expect scope to work。

![](img/19ad66c4cf03f32059434bc1c52e03ee_44.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_45.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_46.png)

So we need an improved definition of substitution that avoids doing this kind of variable capture。



![](img/19ad66c4cf03f32059434bc1c52e03ee_48.png)

It's called capture avoiding substitution。😡，Here's the definition of it。

When we do a substitution inside of a function fund x0 E of V for x， then as we've seen already。

 we go ahead and stop substituting at a binding of the same variable。



![](img/19ad66c4cf03f32059434bc1c52e03ee_50.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_51.png)

That's the same as we've always seen。

![](img/19ad66c4cf03f32059434bc1c52e03ee_53.png)

But when we try to substitute inside of an anonymous function， that binds a different variable name。



![](img/19ad66c4cf03f32059434bc1c52e03ee_55.png)

We will go ahead and recur， but only in certain cases。



![](img/19ad66c4cf03f32059434bc1c52e03ee_57.png)

We'll continue substituting inside a binding of a different variable name。



![](img/19ad66c4cf03f32059434bc1c52e03ee_59.png)

If。And this is kind of like a precondition here if y is not in the free variables of V。Okay。

 so what's a free variable， free is the opposite of bound。 You know what a bound variable is。

 It's one that's showing up as being bound by a lead expression or bound by a pattern match or bound by an anonymous function。

So a variable is free if it's showing up and it's not been put into scope by any of those。😡。

So we don't recurse inside the body。If V has a free occurrence of y in it。

 because that would cause that y to be captured just as it was earlier with the variable Z。😡。



![](img/19ad66c4cf03f32059434bc1c52e03ee_61.png)

That makes this a partial semantics in the sense of a partial function。



![](img/19ad66c4cf03f32059434bc1c52e03ee_63.png)

There are some cases where we simply can't use this definition of substitution because we have free variables inside a V that would get captured and we're sort of stuck at that point in doing the evaluation。



![](img/19ad66c4cf03f32059434bc1c52e03ee_65.png)

So do we have to stop evaluating， Well， the answer is no。



![](img/19ad66c4cf03f32059434bc1c52e03ee_67.png)

Instead， if we're ever about to capture a variable， we can replace it with a fresh name here。

 fresh means not used anywhere else。 It's a new name。So in our example with Z before。

 if we're about to capture Z as we were here with the red and the orange Z。

What we can do is change the argument name。😡。

![](img/19ad66c4cf03f32059434bc1c52e03ee_69.png)

Because the capture is about to occur， we'll just change the argument name Z for this function to something that's not used anywhere else here I've picked Z1。

😡。

![](img/19ad66c4cf03f32059434bc1c52e03ee_71.png)

Now it's safe， I've satisfied that precondition。And I can go ahead and do the substitution inside the body of replacing the orange Z for X that gives me the function Fund Z1arrow Z。

 which is not the identity function。 So I'm no longer getting the wrong result from doing the substitution。

😡。

![](img/19ad66c4cf03f32059434bc1c52e03ee_73.png)

I hope you'll agree， substitution is a surprisingly tricky definition。



![](img/19ad66c4cf03f32059434bc1c52e03ee_75.png)

It's actually very easy to get wrong。😡。

![](img/19ad66c4cf03f32059434bc1c52e03ee_77.png)

I'm not an expert in the history of mathematics， but I'm told that many mathematicians throughout the centuries have。

 in fact， had subtly broken definitions of substitution and that it took until the 1950s for Haskell Curry to come up with a truly correct definition of it。



![](img/19ad66c4cf03f32059434bc1c52e03ee_79.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_80.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_81.png)

![](img/19ad66c4cf03f32059434bc1c52e03ee_82.png)