# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P96：-096-Example Proof_ Iterative Factorial Chap6 Video 26.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

For our next example of an inductive proof about a recursive program， let's look at factorial。😡。

You know this implementation of factorial probably by heart by now。

But here's another more sophisticated implementation of it as a tail recursive function。

And I've named the tail recursive helper here， fact I。😡，The eye here is meant to suggest iterative。

In fact， let's dive into that helper function to see why we might call it iterative。

The reason why is by comparison to an iterative solution in a imperative language， say Java。

 so I've written the same function that I hear in Java as well。

So notice what both of these functions named fact I do， whether it's Ocal or Java。



![](img/69c26994442669191d73dc7f4ca3a7cf_1.png)

They both have an accumulator that starts at one。The code of the helper function checks whether the number N being passed in is zero。

It multiplies the accumulator by n。It decrements N。And finally。

 at the end returns the value of the accumulator now in the Java version of that。

 that's a return statement in the Ocal version of it。

 that's the base case for the tail recursive function。



![](img/69c26994442669191d73dc7f4ca3a7cf_3.png)

So that's why we call this iterative。What I'd like to do is to prove the correctness of the iterative version。

😡，Which is to say if you take fact n， the naive recursive version of it。

 that's going to give you the same value as fact I applied to1 and n。

's starting with one as the accumulator。😡，And we'll do this by induction on N。



![](img/69c26994442669191d73dc7f4ca3a7cf_5.png)

So I've set up a proof here， I've got my code for fact and fact I， and I'm going to prove this claim。

Proof is by induction on。And the property P that I'm proving is just that claim that fact n is equal to fact I1 n。

So let's do the base case。So in both cases， we just take a step by evaluation for fact0 that evaluates to one。

 because we know that if we pass in zero， we get one。

For fact I1 in here I'm kind of going in reverse， I'm going from the bottom to the top here or you could do this in a two column proof format。

 it's just a little harder to do that in a text editor。

 but if you pass in fact I I this should be a zero， if you pass in fact I 10 there， well n is0。

 so we're going to return the accumulator， which is1。



![](img/69c26994442669191d73dc7f4ca3a7cf_7.png)

![](img/69c26994442669191d73dc7f4ca3a7cf_8.png)

Okay， so that gives us the basic。Okay， we've set up the inductive case here。

 we're trying to prove that the property holds for a number n， which is equal to k plus 1。

 we get to assume that the property holds of that smaller number K。

 so the inductive hypothesis says that for K and we want to show that the property holds for K+。



![](img/69c26994442669191d73dc7f4ca3a7cf_10.png)

So first off， what can we do with fact of K plus1？Well up here we know that since k is a natural number and therefore is at least0。

 K plus1 is going to be at least one， so we're not in the then branch of the if expression。

 we must be in the else branch of it so we can take that step of evaluation there。



![](img/69c26994442669191d73dc7f4ca3a7cf_12.png)

So we notice that we can reduce that k plus 1 minus1 to just k by algebra。

 and now we're left with a fact k， so the inductive hypothesis。Now， what can we do at this point？

Well， we don't really have an evaluation step that we can take on fact I。That's because K here。

Could be 0， could be1， could be 100。 We don't know what it is just that it's a natural number。

 And up here， we need to know what that value being passed in as the second argument of fact I is to know whether we're in the then branch or the else branch。

 We just don't know what this。

![](img/69c26994442669191d73dc7f4ca3a7cf_14.png)

So we're stuck there， but maybe we can go to the other side。

 the right hand side of the equality as if this were a two column proof and make some progress there。



![](img/69c26994442669191d73dc7f4ca3a7cf_16.png)

Now， since I can't really conveniently do two columns here in my text editor。

 what I'm just going to do is start with the right hand side here。

 another little proof block here and see what progress I can。Well， in this case。

 I actually do have the ability to take a step of evaluation because I know that the second argument here can't be zero because k is at least zero and therefore K plus1 is at least one。

 so that means we're definitely in the else branch。And that means we've got this expression。

 which I can instantiate down below。Unfortunately， now we're kind of stuck。

We have two expressions that are not equal， and we can't take another step of evaluation we the of them。

And we've already used the inductive hypothesis， so like there's just nothing left to do now。

When we reach this kind of impasse， it's helpful to take a step back and look at the situation that we're in。

 The problem is the inductive hypothesis。

![](img/69c26994442669191d73dc7f4ca3a7cf_18.png)

What we got from it was that there was a way to rewrite fact as fact I。

But that rewrite involved passing one as the first argument to fact I always。

 that was just hard coded as part of the inductive hypothesis。😡。

And we ended up with an extra term K plus1 multiplied on the outside of that。

But where we really wanted that K one was as part of the accumulator。

 we wanted to multiply that K plus1 into the accumulator。

 That's the point in the proof at which we were stuck。

 So if we could just have a more general induction hypothesis。

 one that let us put values into the accumulator， then we would be good。😡，That's what we'll do。

We will strengthen the property P that we want to prove。And that will give us a stronger inductified。

So let's generalize the property P from what we had before。We won't have one in there anymore。

 instead we'll allow ourselves to plug in something else that gets multiplied into the accumulator。

 So we'll call that thing that we're plugging in P。😡，For all P， P times fact n equals fact I P n。

So basically what we're saying there is you can pass in something as the initial value of the accumulator there。

 and that just means you're getting it whatever factorial n you want times that value P。

Let's use this technique and go back and revisit our。



![](img/69c26994442669191d73dc7f4ca3a7cf_20.png)

All right， we're going to change our property P here and generalize it to say for all p P times fact n equals fact I PN。

Now， I'll go through and adjust the。So the base case is quite easy to handle if we have some arbitrary factor p times fact0。

 or fact0 we know evaluates to 1， so that's just p likewise we know if we pass in0 as the second argument of fact I。

 we're going get back the base value of the accumulator， which is just。Let's pause here。

 I've updated my inductive hypothesis and what I want to show to add in this quantification over P and the factors of it and using it as the accumulator。

All right， we now have a chance to use the inductive hypothesis。

 and we do have a P times fact K that we could rewrite as fact IPK， so let's try that。

And we'll move on to the right hand side now。So I've added in that factor P in all of the places here。

And， oh， no。We're still stuck。We still have a term here。

 P times k plus1 that's not equal to the term up here。

 And we still have this factor of K plus1 sitting on the outside。 Now。

 I promised this it was somehow going to get us through when we strengthen the inductive hypothesis。

 So what went wrong。Up here， when we apply the inductive hypothesis。

 I deliberately chose to apply it in a way that wasn't as smart as I could have been。



![](img/69c26994442669191d73dc7f4ca3a7cf_22.png)

So。😊，The inductive hypothesis here actually quantifies over all values P。 Now。

 I happen to use the value P that had been used along through this proof that I could have chosen a different value P right there。



![](img/69c26994442669191d73dc7f4ca3a7cf_24.png)

In fact， take a look at the form of this expression here on line 33。 we've got a quantity here。

 p times K plus1。Times another quantity fact K。

![](img/69c26994442669191d73dc7f4ca3a7cf_26.png)

Well as I highlight those， look up in the inductive hypothesis up there。

 this P could be the p times k plus1 down here。And this fact K of K， of course， could be that fact。



![](img/69c26994442669191d73dc7f4ca3a7cf_28.png)

So let's do that。 We're going to let the P from the inductive hypothesis be。

 and I'm going to write out kind of like I don't know this is a little bit of a mutable operation here or something。

 I'm intending it as a kind of substitution。 What I mean here is that I'm going to replace the P in the inductive hypothesis with the term P times k plus1。

😡，Okay， so that means that in this right hand side of the inductive hypothesis here。

 where I have a P， I'm instead going to use p times k plus1。Which gets me。Fact I of P times K plus 1。

And now flow and behold， we're happy because the expression at the end of this proof block is the same expression as the one at the end of this proof block。

 we've managed to now show the relationship between the left and the right hand side that we wanted up here that they are in fact equal。

😡，So we've finished that proof， QED。Or have we， let's go back up to the top and account for one more thing。



![](img/69c26994442669191d73dc7f4ca3a7cf_30.png)

What we really wanted to show was a relationship between fact and fact I that didn't involve P。

 but I actually just subtly changed things when I changed the property what we were trying to prove here。

 So really what we've done at this point is we've proved dilemma。



![](img/69c26994442669191d73dc7f4ca3a7cf_32.png)

We have proved thelemma that for all P P times fact n equals fact I PN， and we did that by induction。

 We had a claim up here that we wanted to show， which was that fact n equals fact I1。Well， of course。

 that claim follows immediately from the lemma that we just proved as a corollary by just letting P equal 1。



![](img/69c26994442669191d73dc7f4ca3a7cf_34.png)

So that's a very quick proof。Finally， we could finish off by showing the correctness of our tail recursive version of factorial。

And that's very straightforward just take one step of evaluation of fact TR that becomes fact I1 in because that just calls its helper function。

And the lemma that we just proved indeed suffices then to show that that equals factor。

So what's really cool about this example is we've been able to prove the correctness of an efficient version of factorial。

 and we did that by showing that it behaved the same。

 that it got the same answers as an inefficient version whose correctness we could look at and be immediately convinced of just as a naive recursive function。

 so this is a technique that we use to prove the correctness of programs。😡，Write the slow。

 dumb version。 that's obviously correct。Write the fast version that's not obviously correct and prove that the two agree。



![](img/69c26994442669191d73dc7f4ca3a7cf_36.png)