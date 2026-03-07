# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p10 P10 -BV1zNSCBkEgW_p10-

Okay， I'll get started。

![](img/3ae3de5738fc1aed64c9e32125760a30_1.png)

So today we're going to。Finish off。More examples of the problem dual method to develop good online algorithms。

嗯。And then hopefully if we have time， we'll start something else。

 namely the approximation algorithms。Okay， so I promised you last time that we're going to again take another look at ski rental。

So cost of renting。Is $1？Cost of buying。It be dollars and I think you're  scbing today， right。

 is that right okay？うんうん。嗯。And we saw deterministically， you can get a two approximation。I mean。

 two competitive algorithm online。Okay， so now I'm going to show you a randomized algorithm。

 The bound that I'm going to show you is originally， so today。We got a randomized。嗯。

A randomized algorithm。With competitive ratio。Okay， so the competitive ratio is going to be。

Roughly e over e minus1。But to be more precise， it's going to be one plus one over。

1 plus B1 plus1 over B。To the B minus-1。Okay。And as B gets large。嗯。Notice that as when B is large。

1 plus1 over B。To the B is roughly E。Okay。So this is roughly 1 plus 1 over e minus1。

Which implies that this thing is roughly e over e minus1。AsB gets large。Okay。

 so this thing is always at least e over e minus1， but it converges。

 it goes down toward E over E minus1， and the worst case is when b is 1， when b is 1。

 this will give you two。Wichan。B is certainly at least one。Otherwise， you would never bother renting。

Okay。So。This bound。Is due to。Carin and others。Carlin et all。Algorithmmic a 94。

But today I'm not going to show you。The result the way that they did it， I'll show you。Today。

You you will see a primal dual。View。Of。Getting this bound。In this。So you can see this book。诶。

By book Binder an hour。So。They introduced in '05， I mentioned last lecture。

 this primal dualual approach of getting good online algorithms。And then they wrote a book。

 I believe in either '07 or'09， I can't remember。That gives this as one example amongst many others。

Okay， so remember that。Remember the model。Okay， so we have a covering LP。

And we see the constraints one at a time， and if the constraints's not satisfied when we see it。

 we have to make an online decision to change some of the variables to satisfy it。

And the variables that throughout time， the variables have to be monotonically non decreasinging。

 Okay， so let me remind you we did this last time what the LP are。 So for ski rental。

 we have the primal LP。Which says minimize。BX plus the sum i from 1 to Kzi。

Okay so ZI tells us whether we rented on the Ith Day。

And X tells us whether we've bought the skis and there are K days。Of course。

 we don't know K ahead of time。And there are the constraints。

One constraint is that for all dayss eye。We had to either have rent it or bought。And also。

X is at least zero and for all I， Z is at least zero， so this is a covering LP。

And then we have the duall。Okay， so remember in the duall。嗯。

Constraints in the prime alternative to variables in the duall。

And the right hand side and the primal turns into the objective function in the duall。

The thing that you dot product with， so you get Max。Some i from1 to K。Of Yi。

 so you have one variable for every。For every day， such that。Okay。Such that。

The sum i from 1 to k of Yi is at most B。And also that for all I。呃。

I think zero is less than or equal to Yi is less than equal to1。Okay。

So the way we're going to do this is we're going to online build up both the primal and dual solutions。

Okay。And they're both going be， we're going to maintain that they're both feasible。

And we're going to say that the objective。呃。Cost on the primal solution we find is not too much bigger than the dual。

 yet。嗯。Let's see。Right， so for us， as we build this， Yi is either going to be zero or1。嗯。So。

Basically， Y I is going to be one for the。WhyI is going to be one for the days where we run。

And then it's going to be。嗯。And then it's going to start being zero。

So it signifies that you rented on that day sort of， but not， I mean。

There are no integrality constraints here。Okay。Yeah， I mean。

 we will see in the next example when we do set cover。We will see that。

Well actually not then when we do approximation algorithms and we analyze。

A set cover approximation algorithm， there will be a more intuitive。Way of thinking about the wise。

Okay。So here's going to be our algorithm。Initially。X。呃。All Z， I。And why I。Are zero。Okay。

When we see constraintsstraint， so what are we seeing online， We're seeing these constraints online。

Every day we see a new constraint， x plus ZI is at least one。So when we see constrained I。Online。嗯。

If x is already equal to 1。Do nothing。Okay。Otherwise。We're going to set ZI。To be 1 minus x。

We're going to set x to be。1 plus1 over B。X plus 1 over CB。

C is a constant that I'm going to choose later。And we're going to set Yi。To be one。

So what do we need to understand？We need to understand what's the ratio between the objective functions。

In the primal in the duall。And we also want to ensure。

