# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P196：-196-Intuition for Unification Chap9 Video 43.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've solved systems of type constraints in our heads many times now。

How can we solve that algorithmically？Well， let's go back to high school style systems of algebraic equations to get some insight。

Here's a system of equations， How would you solve for x and Y in it？Take a moment。

 go back and do that， but think introspectively about how you are doing。All right。

 perhaps you know some fancy techniques from linear algebra。

 perhaps you remember Gaussian elimination from high school。

 let's just work through a really simple way of solving this set of equations。



![](img/64c26fd84ee62a04ccc0302b048a161d_1.png)

One thing you might notice right away is that the second equation gives us a pretty simple way of isolating either x or y。

 For example， we could rewrite that second equation as x equals y minus-1。

Since we've isolated X that way， we can eliminate it from the system。

We can then continue simplifying that equation。And now we can plug that back in in the equation we had for x。

And now we have values for both X and Y。 Now， if I plug in those values in the original equations。

The two sides of each equation will become the same。

So I have substituted the values of x and y that we discovered， x is1， y is 2。Now。

 if I simplify those equations， that becomes9 equals9。And it becomes negative one equals negative。

So by taking that substitution I've discovered for X and Y。

 I can actually make both sides of the equations be the same they become identical。

 or another word might be they get unified。

![](img/64c26fd84ee62a04ccc0302b048a161d_3.png)

So how do we solve a set of equations？ Well， here we eliminated a variable。

We use that to find the value of the other variable。😡。

That enabled us to go back and find the value of the original first variable。And as a result。

 we got a solution that we could think of as a substitution that unified the set of equations。

That's what we are going to do to solve systems of type constraints。

So a substitution here could be something more complicated， though。

 in the end than just a single substitution of one for x or maybe int for alpha。In fact。

 we're going to have a sequence of substitutions that we could have as a solution。

 so each of these is individually its own little small substitution of something for a variable。

But we're going to carry them out in order as part of that sequence。

We will say that such a substitution unifies a constraint T1 equals T2。

 if by applying the substitution on both sides of the equality。

 we end up with both sides being the same。 they've become the same， they're unified。

And then a substitution unifies an entire set of constraints if it unifies all the constraints in the set。

 let's try an example of unifying a system of type constraints。



![](img/64c26fd84ee62a04ccc0302b048a161d_5.png)

So here I have two type constraints， I could start off working with either one of。

The second one looks a little easier because it's already isolated Y on one side of the equation。

So suppose I create a substitution then of x， arrow x for y。Well。

 I could replace y in the first equation with X 0 x。 Then。 let me do that。

 I'll grab that first equation and replace y with。X。Arrow X。Well。

 now I have an equation that has some pieces to it， and some of those pieces are function arrows。

Now I know function arrows associate to the right。 so if I put in the missing parentheses here。

 it would look like that。What if I break this down a little bit further？

I know that I've got to function with an input and an output on both sides here。

The input on this side is x。 the input on this side is int。Well。

 in order for those two function types to be the same， their input types would have to be the same。

So from this equation， I can actually extract some more information。

 I can break it down a little bit more and say x must be equal to int。

 that's the input types on each side of the arrow。😡，And the output types have to be the same as well。

 So X arrow int would have to be the same as X arrow X。 So I got that from here and from here。

All right。 So I have these two equations now to work with。 Well。

 the first one immediately gives me another variable that's been isolated that I could try to eliminate from everything else。

 So let me add in now a substitution。 I'm going to have a substitution of int for x。Okay。

 so if I take that substitution and apply it to this remaining equation， what do I get。

 I get int arrow int equals int arrow int。Now， of course， looking at that。

 we can immediately see that's the same type on both sides of the equality。

If we wanted to be a little more algorithmic about it。

 we could say once more we have a function type， and we could break that down the left hand side of the arrow has to equal the left hand side of the arrow in both places。

 so that's in equals int and the same thing for the right hand side both of the arrows。Okay。

 so at the end， we got this substitution。 first we do x， arrow x substituted for y。

 then we do int substituted for x。Now that's only one possible solution to this system of equations。

 In fact， we could get a different solution if we chose to eliminate variables in a different order。

 So let's make a second attempt。The first time we chose to eliminate y first by working with the second equation。

Well' start' with the first equation first this time。So we've got this equation。And from it。

 we can extract something about the input types and the output types。Okay。

 so all I've done is say that the left hand side of the arrows and the right hand side of the arrows both have to be the same。

Well， now if I wanted to， I could eliminate x because I know x is int。

I'd replace x by int in that second equation。And now I know that y is actually inent。

So the final substitution I end up with that time is going to be different。

It's still a substitution that unifies this set of equations。

But it's a different substitution than the one I came up with the first time。

So we can get different solutions depending on the order in which we process all of the equations and eliminate the variables。



![](img/64c26fd84ee62a04ccc0302b048a161d_7.png)

![](img/64c26fd84ee62a04ccc0302b048a161d_8.png)