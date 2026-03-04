# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P169：-169-Substitution Examples Chap9 Video 16.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's do a couple examples to build up our intuition about what the definition should be。

 and then we'll actually give it。😡，Suppose we have the expression， let x equal 2 plus 2 in x plus x。

That would single step， the binding expression would reduce to four。Then that would single step。

We would take the body expression and substitute4 for X in it。Now intuitively。

 what we want to have happen there is both of those occurrences of x get replaced by 4。

So I'm going to write that that's equal to 4 plus4 after doing the substitution。

 so notice that substitution here is not a step， it's not part of the single step relation。

 we're just treating these two expressions as equivalent， essentially。😡。

4 plus 4 would then finish by taking a single step to 8。All right， so that was one example。

Let's try another example。This one's more complicated。

 We've got two occurrences of the variable X in it。

And so to help us keep those two occurrences straight， I've color coded them。

 we've got a blue X and an orange X。So， let blue X equal 5 in。

An expression that has an occurrence of blue X and also has another binding of orange x。

 with x equals 6 in X。How are we going to do substitution here？Well， this takes a single step。First。

😡，By taking that binding expression 5， which is already a value and substituting it for blue X。

So that means that we need to replace the occurrence of that blue x with5hi。

So notice what we're not doing here。😡，We're not going to substitute inside of the inner let expression that's binding the same variable name。

 Why not， Because we want shadowing and scope to work out the way that we have learned them thus far。

😡，Next， we evaluate that interlet expression by substituting6 for x inside of its body。

That means that x gets replaced by6。And therefore， the final step of evaluation here is that the entire thing steps to 11。

So we learned something important from this example about when to stop substituting。😡。

Let's work on a third even more complicated example。Here we have a binding of x twice。

 but in the second one， where we bind the orange X， we use the original binding of x， the blue x。

So let's work this one out。We want to take a single step。

 which means we'll get rid of that outer lead expression that binds x to 1 and step to the inner lead expression。

 and we want to make some substitutions in that inner lead expression。

But we have to be super careful about which substitutions we make。For one thing。

 as we learned in the previous example， we don't want to substitute inside the body expression because it's a rebinding of the same variable name。

 We want shadowing and scope to work correctly。 So inside that orange x plus x。

 we're not going to do a substitution of one for x。😡。

But and this is what's different from the previous example In the binding expression。

 we do want to do a substitution because the blue x plus x there really does mean the binding of x to 1。

😡。

![](img/cfc18e1d617b20cb4fb454804ece296d_1.png)

![](img/cfc18e1d617b20cb4fb454804ece296d_2.png)

So that substitution will occur and reduce the blue x plus x to 1 plus 1。

So the new thing here is that we do substitute inside a binding expression。

 even if it's the same variable name。😡，Therefore， substitution inside of the binding versus the body expressions works different。

The rest of this is pretty easy to work out given everything we've done so far。

The let x equal 1 plus 1 in x plus x will step 2， let x equal 2 in x plus x。

 that will step to x plus x with  two substituted for x， and that will be equal to 2 plus 2。

 And finally， that steps。Okay， so we've learned some important things now about how substitution should work and how it should be defined。

😡。

![](img/cfc18e1d617b20cb4fb454804ece296d_4.png)