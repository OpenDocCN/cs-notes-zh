# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P197：-197-Unification Algorithm Chap9 Video 44.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/9a5c6c90a7cf379a507ca75b38272116_0.png)

So here's the unification algorithm。Until that constraint set is empty。

 we will continue to do the following。

![](img/9a5c6c90a7cf379a507ca75b38272116_2.png)

First， we'll pick some constraint from the set， doesn't matter which one， of course。

 which one we pick does lead to different solutions potentially。

 but we'll pick some constraint t1 equals T2 and we'll remove it from the set。



![](img/9a5c6c90a7cf379a507ca75b38272116_4.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_5.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_6.png)

Then we'll take that constraint and reduce it somehow。

 I'll talk about the reductions on the next slide， but basically they will simplify the constraint in some way。



![](img/9a5c6c90a7cf379a507ca75b38272116_8.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_9.png)

After we do that reduction， one of three things will happen。

Either we'll be able to update our solution with a new substitution。

 so we added on to the end of all the substitutions we've discovered so far。😡。



![](img/9a5c6c90a7cf379a507ca75b38272116_11.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_12.png)

Or we end up adding some constraints back to the set。

 Now there's simpler constraints than they were before that happened when we broke apart function arrows。

😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_14.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_15.png)

A third possibility is that we fail because the equations are inconsistent。

 Now that didn't happen in our example we had before。

 but suppose at some point we had gotten down to an equation that said an't equal bo。 Well。

 of course that can't hold So the algorithm would have to fail at that point and say there is no solution。

 This system of equations is inconsistent。😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_17.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_18.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_19.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_20.png)

It turns out this unification algorithm was actually invented next door as it were。

 this was invented by Professor John Allen Robinson of Syracuse University。



![](img/9a5c6c90a7cf379a507ca75b38272116_22.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_23.png)

How about those reductions？

![](img/9a5c6c90a7cf379a507ca75b38272116_25.png)

Well， there's only a few different forms they can have。

The first is we might take a constraint out of the set that's a very trivial kind of constraint。

 It might say int equals in or bool equals bool or tick x equals tick X for some type variable tick X。

 But the thing is it's the same type variable on both sides of the equality。



![](img/9a5c6c90a7cf379a507ca75b38272116_27.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_28.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_29.png)

So there's no interesting information to extract from that kind of constraint。

 there's no new substitutions we get from it， there's no new constraints we need to add back to the set。

 we can just say that's uninteresting information， we don't need this in the set we'll throw it out and continue。



![](img/9a5c6c90a7cf379a507ca75b38272116_31.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_32.png)

More interesting is if we get a function type equals another function type。

So then we add two new constraints back to the set， so T1 arrow T2 equals T3 arrow t4。

 we throw that out that's no longer in the constraint set。

 but we add back in two simpler constraints that T1 equals T3 and T2 equals T4 that is the input types on both of the arrows are equal and the output types are equal。

😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_34.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_35.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_36.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_37.png)

So we're making progress here towards termination of the algorithm because even though we're adding two constraints back in。

 whereas before we only had one， each of them is a smaller constraint in terms of the shape of the types。



![](img/9a5c6c90a7cf379a507ca75b38272116_39.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_40.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_41.png)

A third possibility for a reduction is that we get that a type variable equals some potentially complicated type T。

😡，This is the point at which we can eliminate that type variable。😡。



![](img/9a5c6c90a7cf379a507ca75b38272116_43.png)

But there's a caveat。The type variable itself cannot appear in the type T。

 so tick X cannot be in T here。😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_45.png)

If it did， we wouldn't be making progress because we would be creating a substitution that doesn't actually eliminate x。

 and still has it in that type。

![](img/9a5c6c90a7cf379a507ca75b38272116_47.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_48.png)

So when we discover an equation of this form。😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_50.png)

We will do two things。

![](img/9a5c6c90a7cf379a507ca75b38272116_52.png)

First， we'll go ahead and substitute T for TX throughout the entire remaining set of constraints。



![](img/9a5c6c90a7cf379a507ca75b38272116_54.png)

That's going to eliminate tick X from that set of constraints。



![](img/9a5c6c90a7cf379a507ca75b38272116_56.png)

Second， we will append a new substitution to our solution。

 Well record the fact that we are substituting T for T X。



![](img/9a5c6c90a7cf379a507ca75b38272116_58.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_59.png)

If there's any other case of the constraint we encounter besides those three， we fail。



![](img/9a5c6c90a7cf379a507ca75b38272116_61.png)

That's the point at which we've discovered an inconsistent set of equations。

 one that cannot be solve。

![](img/9a5c6c90a7cf379a507ca75b38272116_63.png)

It turns out that the unification algorithm is actually optimal in a particular sense。😡。



![](img/9a5c6c90a7cf379a507ca75b38272116_65.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_66.png)

Which is that the output of it is guaranteed to be the most general unifier for that set of equations。

😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_68.png)

What I mean by that is that any other unifier would actually carry out some more specific substitutions。



![](img/9a5c6c90a7cf379a507ca75b38272116_70.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_71.png)

So for example。Maybe you've got the constraints that alpha equals beta  error beta。😡。



![](img/9a5c6c90a7cf379a507ca75b38272116_73.png)

The unification algorithm will output beta arrow beta substituted for alpha。

 Now that unifies that single equation。

![](img/9a5c6c90a7cf379a507ca75b38272116_75.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_76.png)

It will not output something more complicated。

![](img/9a5c6c90a7cf379a507ca75b38272116_78.png)

For example， it won't output for substitute int arrow in for alpha and then int for beta so that you get int arrow endt on both sides。

😡。

![](img/9a5c6c90a7cf379a507ca75b38272116_80.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_81.png)

Now that is a unifier， it does， if you apply that substitution to the original set of equations。

 cause both sides to end up being the same。

![](img/9a5c6c90a7cf379a507ca75b38272116_83.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_84.png)

But it's too specific in a way， right It hard codes now kind of the fact that they need to be ints。

 Well， nothing about the original set of equations said anything about ints。

 We didn't need that in the solution。

![](img/9a5c6c90a7cf379a507ca75b38272116_86.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_87.png)

So that's the sense in which the unification algorithm produces the most general unifier。



![](img/9a5c6c90a7cf379a507ca75b38272116_89.png)

Formerally， we could state that is as follows。

![](img/9a5c6c90a7cf379a507ca75b38272116_91.png)

Suppose you run the unification algorithm on a constraint set C and you get back the substitution S。



![](img/9a5c6c90a7cf379a507ca75b38272116_93.png)

Well， if there's any other substitution that also unifies C， let's call it S1。



![](img/9a5c6c90a7cf379a507ca75b38272116_95.png)

Then S1 is actually equal to the substitution S followed by some additional substitutions called them S2。



![](img/9a5c6c90a7cf379a507ca75b38272116_97.png)

So S1 is more specific than S in the sense that S1 involves first doing S and then doing some additional substitutions that make the resulting types potentially more specific as a result。



![](img/9a5c6c90a7cf379a507ca75b38272116_99.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_100.png)

![](img/9a5c6c90a7cf379a507ca75b38272116_101.png)