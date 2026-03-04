# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p108 10_08_local-bindings -BV1bw4m1D7MM_p108-

In this segment I want to introduce rackc's local bindings。

 This is what an ML we use lead expressions for Raet also has lead expressions。

 but it actually has a variety of them and that'll let us understand some interesting different semantics between the different kinds of lead expressions But before we get that show you an initial example it's one of the same examples I showed you in M let's compute the maximum number in a list we'll assume we're past the list and assume that list only has numbers let's use con which we now know and let's ask first if we have an empty list。

 there's no such thing as the maximum of an empty list so there's a built-in feature and racket called error that we can pass a string and if this evaluates execution will stop with this error so that seems reasonable otherwise if we have the one element list。

 how do you check for one element list you check if the cutter is empty that makes sense then let's just return the car because the largest element of1。



![](img/23733c0fdd1a9f7798fe7d07427ee540_1.png)

list is that element itself。 Otherwise， aha， we know we better not make multiple recursive calls on the same list。

 We saw an exponential blow up when we did this sort of thing in M L。

 So let's create a local variable to hold。😊，The max of the cutter。

 and then we'll compute with that here。 Now， before I go on， let me show you。

 since I just introduced syntax， Let is the new special form I'm showing you。😊。

Then you have this starting right parenthesis and that'll eventually be matched by this closed parenthesis and then you have the body and then you close the let and what goes here in the dot dot dot is one or more variable bindings。

 each one goes in parentheses as a matter of style use square brackets and then it's x1 expression 1 x2 expression2 and so on you can have as many of these as you want。

 So this is just like in M having a number of v bindings in the same lead expression。

 And so in this particular case， I didn't need n of them。I only needed one。

And so I'll just put that back up here。 And so when you have one。

 it's often easy to forget you need this extra pair of app parentheses around it。

 but you do need those extra ones。 Otherwise， it just won't work syntactically。

 So now I have the place where I bound my variables， there was one here， tail ants。

 and now I just need the body。 And so my body will just be if the tail ants is greater than the first element of the list。

 car of x's， then return the tail ants。 Otherwise return the head of the list。



![](img/23733c0fdd1a9f7798fe7d07427ee540_3.png)

![](img/23733c0fdd1a9f7798fe7d07427ee540_4.png)

And that should work as a definition of max list。 So this is just an example of showing you this let expression。

 right， where the body is this if。 And then the list of bindings is here。

 And this one had one binding in it， which is right there。 So that's our example of a let expression。

 But now let me do the rest of this in the slides and show you that we actually have more to understand。



![](img/23733c0fdd1a9f7798fe7d07427ee540_6.png)

![](img/23733c0fdd1a9f7798fe7d07427ee540_7.png)

So it turns out RaCet has four different ways to define local variables， let let star。

 let Re and local defines， and this variety is actually good， they have different semantics。

 and so with that different semantics we can use the best one that's most convenient for the code we're writing and which helps communicate to the person reading our code which of the different semantics we mean here and is most convenient for the computation we're doing。

Okay， so this will help us learn things about scope and environments better by seeing that you actually can give three different reasonable definitions to the meaning of a let expression。

 Let versus let star versus let Re。 So let's just go through each of these in order。

 We'll start with a let。 We know that a let expression combined any number of local variables。

 I showed that to you in Dr。 racket。 But the expressions。



![](img/23733c0fdd1a9f7798fe7d07427ee540_9.png)

Are all evaluated in the environment from before the lead expression。So given a lead expression， we。

 of course， the body of the lead expression uses all the variables we defined。

 but it turns out the expressions that initialize those variables do not use the earlier variables。

 They are all evaluated in the environment from before the lead expression。

This is not how ML let expressions work。 Different languages have different semantics for things。

 Let's look at the example here on the slide。 This is a function that takes in a number x and doubles it。

 just does it in a silly way to emphasize the semantics that I want to。

So here when I say let x be x plus 3。😡，This x on the right hand side is going to be the x from before the lead expression。

 the parameter to the function。 So this is parameter plus 3 Y with plus x2。

 this x will also be the parameter。 This is not how Ml works。 So since it is also the parameter。

 Y is parameter plus 2。So if I take these together， I end up with two times the parameter plus5。

 so if I subtract 5 back out， I get twice the parameter， and that's why it's a silly double function。

😡，So why do you want this semantics， Well， if you're not reusing variable names here。

 you know the way this X is shadowing that， this doesn't really matter。

 and so if you're not doing any shadowing it's best style in racket to just use let。

But it's also convenient in certain other situations。

 like if you wanted to have some body where x was y and y was x。

 you can write it like this and under ML semantics。

 this does not work that x would be bound to the outer y。

 and then y would also be bound to the outer y because under ML semantics。

 the second x would be bound to the first one， but under racks let。

 let x be y and y be x would properly change the bindings of x and y to each other for the body of the lead expression。

So that's let。 Now， let me show you let star。 So syntactically let star works exactly like let。

 It just has one more character。 It has a star after the T and this。😊。



![](img/23733c0fdd1a9f7798fe7d07427ee540_11.png)

Is Ml's let。 Okay， The expressions are all evaluated in the environment produced from the previous bindings。

If we didn't have this， we would have to nest our lets when we wanted this behavior。

 So here's our example。 You're probably more comfortable with this one only because we used ML first in our study of programming languages。

 So here when I say plus x3， that will be the x that's the parameter to the function and now for y when I say plus x2。

 I use the environment created by all the earlier bindings。 So I will use the shadowed X。

 So y will in fact be bound to the parameter plus 5。So if I have parameter plus3 and parameter plus5。

 when I add those together and subtract 8， I end up doubling the argument， so that is let star。

 it's much more like ML's lead expression。Another one。 So now that's let and let star。

 Now we do let Re syntactically， it's just like the others。

 except instead of writing let or let star， we write L E T， REC， Let Re。

 This is for the rec is short for recursion， and the expressions are evaluated in an environment that includes all the bindings。

 The earlier ones and the later ones。😊。

![](img/23733c0fdd1a9f7798fe7d07427ee540_13.png)

Ah， it's more like ML's and for defining mutually recursive things。So here's an example。

 It's a little more complicated。 It actually triples its argument。 Instead of doubling。

 we're getting into fancier stuff， right， So I have three local variables， Y， F and W。

 And if you look at F， it's a function。That when you call it uses its argument Z， but also uses Y。

 W and X and x， because we don't have any shadowing anywhere here will be the parameter to the function。

Why will be the earlier binding， which we could have also gotten with Letstar。

 We could not have done that with L。And W will be the later binding。

 and this is what you have to use let Re for， it will not work with let or with let star。

 So when we call F with minus9， z will be minus9， y will be the parameter plus 2 W will be the parameter plus 7 and x will be the parameter。

 if you put it all together， you end up tripling your argument。😡，So why does the language have letre。

 Well， you need this sort of thing for mutually recursive functions。

 F calls G G calls F all defined within a define like this。But we have to be careful here。

 I recommend only using let rec for when you have mutually recursive functions。

 It's generally not so useful otherwise， because the expressions are still evaluated in order。

 We have to be really careful here。 What if why。😊，Instead of saying plus x2 had said plus W2。Well。

 W is in the environment， that's the rule of letre。

 but we have not evaluated it yet because at runtime when we evaluate these bindings。

 we do still evaluate them in order， so racket would not like this very much。

 it turns out not to raise an error instead when it hits that X， sorry that W。

 itll return some funny undefined thing and then we will get there because if we call plus on undefined that causes an error。

😡。

![](img/23733c0fdd1a9f7798fe7d07427ee540_15.png)

So this would be bad style， it would surely be a bug。

 the reason why it works for F is because the use of W， the forward reference。

 the use of the later binding is inside a function body。

And we know that when we evaluate this expression， this lambda， we don't evaluate the function body。

 we don't evaluate function bodies until we call them， so we evaluate Y， we get parameter plus 2。

 we evaluate F， we create a closure， we evaluate W， we get parameter plus7。

 and now when we call that closure we created W has been nicely initialized， we'll look it up。

 and there will be no problem。so that is black Re。Here's an example where letre is actually needed is actually properly used。

 I'll let you puzzle through this code on your own。

 it's actually taking an argument and returning true if it's sorry if it's taking the number mod2 so if it's an even number it returns zero if it's an odd number it returns one it only works for non-negative numbers and it does it via these very silly mutually recursive functions but my point is to use letre so that even is bound to a lambda that in its body calls odd an odd is bound to a lambda that in its body called even so forward reference and backward reference。

 I am using the Greek letter lambmbda here just on the slide rather than writing out the word lambmbda it turns out you can do that in Dr racket but I'd prefer you write it out so that when you submit your homework assignments we don't have uncode characters that don't always print well everywhere but if you really want to use lambmbda I suppose we will survive and you know here's another example of you know。

Not using later bindings because you get this undefined issue that we talked about on the previous slide。

So that's my discussion of Let Re， I told you there is one other way to define local variables。

 so in certain positions in your function body， you can actually use define。So for example。

 right here I'm defining another version of this silly mod function My function body is the second everything but the first line。

 the function body is the second line， the third line， the fourth line。

 you can actually in here right define and then have bindings and you can have any number of these and those will be local variables to your function and the semantics is the same as letre exactly everything I told you about let Re is true for local defines as well。

 it's just a different syntax as long as we're using all the constructs we will use in this course and I prefer to use let star and let Re。

 it's the more traditional style it emphasizes the different semantics but I should be honest with you the biggest users and designers of the rackcet language now say that local defines is the preferred style that you should use let and let star when you want those semantics but if the semantics doesn't matter。

 meaning the result would be the same for all three。Or if you actually need let Re。

 then they prefer this local defined syntax， and so on your homework I will let you choose if you want to use local defines you can。

 but I find it easier to think about the traditional expressions， let let star and let Re。

So that's our introduction to scope， remember not only do you need to know the differences between these constructs to read rackcet code and to write rackcet code in good style。

 but it's wonderful that we have a language that lets us think about three different definitions for how a lead expression should work because each of them are the most convenient and the most useful in different situations。



![](img/23733c0fdd1a9f7798fe7d07427ee540_17.png)