# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p17 P17 -BV1zNSCBkEgW_p17-

![](img/a42ebd654c6a706901ba8c4c4521c326_0.png)

Okay， I guess I'll just get started。🤧嗯。So yesterday I gave you the outline of Inter point and then I started。

Discussing。呃。Some optimization tools such as gradient descent， which is a first order method。

Meaning that it has access to some function F as well as its gradient on any query point。

And we'd like to minimize the function F。Today I'm going to tell you about a second order method。

 this is called Newton's methodod。And Newton's in the second order method。

 you're not only allowed query access to the function and its gradient。

 you're also allowed query access to the hessian of the function。Okay。

And I will show you an analysis of。Of Newton's method that will be relevant for interior point Okay。

 so just a recap。嗯嗯。Some things I want you to remember， so our goal of Interior Point was。

To minimize C transpose x， such that Ax is at least B。any LP can be written this way。And we。

Repeatedly。Approximately minimized。F of lambda。We're F lambda x。

Is defined to be lambda C transpose X。Minus the sum arguinggling from 1 to M。Of lawn。

 of slack of X at I。Where。The slackck vector。Is defined as Ax minus B。

So we're going to use Newton's method。To get better and better solutions to F lambda。

I want to tell you a little bit about New's method。So。Second order。Optimization。second order methods。

We want to minimize。Some function。F， which maps Rn to R。And we are given。Orracacle access。To F。

The gradient of F and the hessian of F。And what I mean by that is give it a point x。

There is some way for us to get our hands on F of x， the gradient of F ofX， and the hest of F ofX。🤧嗯。

So， as usual。We start。With some。Initial。呃。Excell it。Let's say inRN。And repeatedly。Apply。

So update rule。And what we want to understand is how much does our error decrease as we do some number of updates？

Okay。Set up clear for people。So this is Newton's method。We're at some current iterate。

 so we have some current。X0。In Rn。And what's the update rule？And。We set x1。系。To be。

X0 minus the Hessian inverse。Apped to the gradient of Fx0。Okay。

 so that's going to be the update rule that we're going to analyze。ok。And。Where does that come from？

Well， remember what gradient descent did？Graadient descent wrote basically the first order Taylor approximation。

Of the function。Plus some error bound that comes from Taylor's theorem。Okay。

And then gradient descent just tried to minimize that expression。

So what Newton's method is doing is it's taking the second order。Expansion， Taylor expansion of F。

 And it's minimizing that second order expansion， right。So Taylor's theorem。Says。That。You know。

 if you look at F of X1。Well， let's say F y。Just some F of Y。

Approximately up to some arrow that comes out of Taylor's theorem。This is equal to。F of x0。Plus。

The gradient of f at x0。Dotted with y minus x0。And。Plus one half。Y minus x0 dotted with the Hessian。

Of y minus x0。Okay。So。This is what Taylor's theorem says in terms of approximating F by its second order expansion。

And。Newton's method is basically just assuming that this is in equality and then just tries to minimize the right hand side。

And the minimum of this right hand side is exactly this。If you do calcus。All right。

 so we just need to understand。How well Newton's method does。 So are there any questions？So far。

It's only right down a theorem。So again， for T。In01。Define。XT。To be x0 plus t times x1 minus x0。

Where。By x1， I mean that x1 and by x0， I mean， our initial the point that we're currently at。어 어 어。

Suppose。There exists in epsilon。A positive epsilon， such that。

For all t in the interval from  zero to1。We have that the following is true。One minus epsilon。

Times the hessian of F。At a zero。Is that most in the loaner ordering？The Hessian。At Xt。

Is that most of the loaner ordering？One plus epsilon。The Hesianinex0。I suppose that that's true。

 So remember when we're analyzing gradient descent。It was， It was a first order method。

 We only had access to the gradient。 We couldn't actually compute the Hesian。

 but we had a promise about the Hesian。 right， We were told that the hessian is well conditioned。

There's some small gap between its largest and smallest singular values。So again。

 for Newton's method， we need to have some kind of promise to say that Newton's method does well。

And the promise that we're going to make use of is that the Hessian doesn't change too much。

On the line that connects x0 to the next iterate。Okay。Just a recap when I say that。

A matrix A is not most of matrix B， remember that means B minus a is positive semi deffinite。

So suppose that's true then。I want to measure progress。

 and the way that I'm going to measure progress is that。Okay， so。Is to say this。

So the norm of the gradient of f and x1。😡，Under。This。嗯。I'll say what this means in a second。

