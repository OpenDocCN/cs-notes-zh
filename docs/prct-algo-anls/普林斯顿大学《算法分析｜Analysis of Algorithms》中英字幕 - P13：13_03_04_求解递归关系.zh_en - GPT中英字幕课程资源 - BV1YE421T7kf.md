# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P13：13_03_04_求解递归关系.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/f93ded3b3fb36fb898e63c4bfccea719_0.png)

Now we're going to take a look at the use of generating functions to address the important tasks that we brought up in the last lecture。

Programs， many of which can be cast as recursive programs or algorithms immediately lead to mathematical models of their behavior called recurrence relations。

 and so we need to be able to solve recurrence relations in order to be able to analyze algorithms。

And so now I'll take a look at how you use generating functions to solve recurrence relations。

And it's pretty much an algorithmic process that is we want to hate to use a meat grinder。

 but it gives the idea we want to put in a recurrence relation and we want to turn the crank and we want to get out a sequence。

 we want to get out a simple expression for what it represents。

And it's pretty much a general procedure that we can always follow and I'll give many examples。

So first thing is we're going to make the recurrence valid for all values of n。

 and it's easy to do that and I'll show you in the examples。

Then multiply both sides of the recurrence by z to the n and sum on n。

So it's an equation that's valid for all N so that we can do that and usually we make it just for non negative n。

Then that'll give us some sums， but some of those sums will involve an unknown generating function and maybe some well known generating functions。

 the end result will be an equation that's the OGF corresponding the recurrence has to satisfy。

So then what we need to do is to solve that equation to get an explicit formula for the OGF。

 a lot of times we can go ahead and do that and we'll give plenty of examples the initial conditions play a role。

And then we'll expand the OGF to find the coefficients。So the recurrence corresponds to a sequence。

 the OGF is a way to represent the sequence， we'll use the recurrence to find out what the OGF is。

 and then we'll expand to get the coefficients， which is the goal， that's what we're trying to find。

So let's look at the example now in the case of linear recurrences with constant coefficients。

 the procedure really is an algorithm， we always can get a solution and actually people have implemented this in symbolic mass systems。

So here's an example from the previous lecture， so that's a recurrence that is defined for M bigger than two with the initial conditions a0 because0 and a1 equals 1。

So the first thing is make it valid for all n and so it's all n greater equals0 and so all we do is use the chronicer delta notation。

 so for one this thing and you assume that for negative indices at0 so a0 equals0 so that would be0 that would be0。

 so for a1 would have to add a1， so when n is1 we want to add one that's what that chronicer delta is at the right there。

A0 is expressed then in terms of A's with negative indices which are zero， so it's okay。 a0 equals 0。

 so that's a recurrence that's valid for all n greater equal is 0。

So now we multiply by z to the n n sum on n， some n greater equal to0， a to the n， z to the n。

 that's our generating function， A of Z that we're going to use to represent this sequence a event。

For the first term on the right hand side， it's some A n minus1 Z to the n change n to n plus1 throws out of Z。

 So that's5 Z A of Z。And for the second term， we change n to n plus 2 in the sum and throw out a z squared。

 that's minus6 z squared a of z。And the chronicroner Delta term， that's sum on all n。

 but that thing is only one when n equals1， so that's z to the n in that case is just z。

So that's an equation that the generating function has to satisfy。And that's a。

Easy equation to solve with some algebra， so that is it's just A of z is just z over1 minus 5 z plus 6 z squared。

That's， again， an equation that that generating function has to satisfy。

So that's a generating function now we want to extract coefficients because our goal is to find an expression for AN。

So how we're going to extract coefficients Well in the case of ratio of two polynomials。

 it's not difficult， it's the technique known as partial fractions where we factor the polynomial in the denominator and we know that our solution must be of this form because if you cross multiply then in the denominator。

 you get the right polynomial because you've factored it and then the numerator。

 you've got two equations in two unknowns， you have to have c0 plus c1 equals0 and you have to have the 2 c0 plus 3z1 equals minus1。

So that is those unknowns have to satisfy those two simultaneous equations and that's just what we got before and the solution is c0 equals 1 and C1 equals minus1。

 and so that now expresses the generating function as difference between two geometric sums and those we know how to expand its 3 to the n minus2 to the n。

So that step by step， given a recurrence， we can get the solution that is a simple expression for the coefficients and that's going to work in every case now there's complications that arise。

 let's look at a more complicated example。Sometimes and this works for actually any linear recurrence because you get a polynomial and you can always factor a polynomial。

 so let's look at this one 5 A minus-1 minus-8 AM -2 plus 4 n minus-3 same procedure to make these initial conditions satisfied。

 you start at0 and work up and find that you have to add a delta n1 and a minus delta n2 in order to make it valid for all n。

Then when you multiply by z to the n and sum on n， you get this equation on the generating function。

 5 z a of z minus8 z squared a of z plus 4 z cubed a of z plus z minus z squared。And again。

 now just using algebra。 now， we have an explicit expression for the generating function。

 It's the ratio of two polynomials。Raio two polynomials， partial fractions works。

 you have multiple terms in this case， there's the root one half has multiplicity2。

 and that means just that that polynomial。Is。I got three roots and then actually in this case。

 one of the roots cancels with the numerator， so we have a of z equals z over 1 minus2 z squared。

But that's one that we know， that's a generating function that we already derive by differentiating the geometric and scaling。

 and that says that a sub n equals n2 to the n minus1。Again。

 just algebra to find an explicit representation for the generating function and then expand。

Now it turns out that if you have roots of multiplicity 3。

 you'll get terms of the form n squared something to the n， and so forth。

 and there's other things that can happen， but it's just properties of polynomials。So for example。

 you could get complex roots， so here's an example where the roots are complex。Again。

 this is a same setup， we have a third order linear equation constant coefficients。

 we've got three initial conditions， do the deltas to make it valid for all n multiply by Z to the n and sum on n。

 and then do algebra and then that gives a again ratio of two polynomials。

 the degree of the polynomial is equal to the degree of the recurrence。In this case。

 what happens is there's one plus z squared is one of the roots， one of the factors of the。

Deenominator and again， the numerator cancels So what do we do with1 plus z squared Well we can factor it with complex and find out that a of z is a half1 over one minus side of the z。

plus1 over1 plus I of Z， and we can go ahead and expand that and get this representation that's i to the n plus minus i to the n where you can factor out an I to the n。

 and even though I appears in this solution， when you do the math。

 I never appears as a member of the sequence， becauses odd， this thing cancel when ends odd。

 this thing cancels to zero。And when ends even then you go between1 and minus1 between because of the i squared or right of the fourth。

 so that's a rather strange oscillating sequence， but it comes out immediately from our process of our algorithmic process of finding sequence corresponding to a given recurrence。

It's a nice example because it shows the origin of the oscillations that we often see when we're studying algorithms or combinatorial structure。

 those oscillations are modeled in mathematics really in this case by just a square root to minus1 squared to minus1 squared is minus1 and to the fourth power is plus1 and that's really reflected in this sequence。

 and it's going to be maybe not so easy to uncover oscillations without using complex and as we'll see。

 complex analysis plays a fundamental role in analytic combinators when we get into advanced methods。

Okay so here's a summary and then this is just math with unknowns just so that we can state a theorem and it's kind of a complicated looking theorem but next time we'll show that we don't really need all this detail but it's worthwhile to fully state this theorem because the method that we've talked about really leads right to a proof of this theorem that's not that abstract it's just a matter of turning the crank so what we know is that if you've got a t order linear recurrence with constant coefficients so that you just have t terms on the right-hand side it's going to be a linear combination of t terms and it depends on the roots of the polynomial that's induced by what happens when you get when you multiply by Zv and some on Z and do the algebra you're always going to get this polynomial one minus x1 minus like that in the denominator。

And it depends on the multiplicity of those roots， so if you've got R roots where the multiplicity is m sub I。

 so if you add up all the multiplicities， you get t。

 then your solution is depending on the multiplicity。

 it's going to be for every root you got that root to a power plus n times that root to a power all the way up to the multiplicity。

 and that has a total of t terms。And again， I'm not expecting people to follow really every detail of this。

 but you can get the idea that we can actually write down a full solution to linear recurrence and generating functions give us this proof。

And the constants involved can always be determined from the initial conditions and that's using partial fractions and solving simultaneous equations。

 and again this is all automatic and people have implemented this process in symbolic algebra systems so actually nowadays you can type in recurrences and get the solution。

And don't forget， your solution might involve periodic behavior that's introduced by the complex roots。

 so it might not be the case to be able to prove that even a recurrence like this converges to a limit。

But it's all very straightforward and well understood mathematically。

What about the analysis of algorithms for Quickst， we had this rather complex recurrence that was our starting point for the analysis of Quickst。

Can we use generating functions to solve the quick sort recurrence and the answer of course is that we can to make life easiest。

 we'll first multiply both sides by n， although you can get it done without doing that。

So now we have a recurrence where we're not dividing by n and then multiply by z to the n and sum over now we sum for n bigger than equal to 1。

 and that's just because of the C minus1 here to save us a few terms。

So that's multiplying by zating the n and sum。 And now we got to look at each one of the terms and see what we have。

What do we have on the left there Well， if we define the generating function for the sequence of interest to be c of z equals sum c sub n z to the n。

 that is if you differentiate that multiply by Z that's what you get so that one is C prime Z and there's a factor of Z all the way through this divided out。

This one is two。2 z over 1 minus zq。And again， that's right out of the table。

And then a factor Z divides out and this one is a convolution， it's1 over 1 minus z times c of z。

 so I skip just a very few steps here involving indexes that go to zero and involving dividing by Z。

 but you can convince yourself quite easily that that ordinary differential equation is the result of。

Simply evaluating these sums to get the equation that the generating function has to satisfy。

So that's an ordinary differential equation and it's completely well defined。

 and so now we need to know about solving differential equations to get this solved。

And I don't want to give a course on solving differential equations。

 I just point this out as an example for people who do know that it's possible to solve it。

 just by considering the equation without the extra term and figuring out that what you need to do is solve that problem。

 in that case that problem， the solution is1 over1 minus z squared。

So if we didn't have this constant term， the solution would be 1 over 1 minus z squared。

 you differentiate that。 It's the same thing as if you multiply by one over1 minus z and multiply by 2。



![](img/f93ded3b3fb36fb898e63c4bfccea719_2.png)

And then what you do is multiply by that or divide by that factor， which winds up by multiplying。

 and it's really actually analogous and it is totally analogous to what we did when solving first stored linear recurrences where we try to find something to multiply it by to make it that a telescope。

 this is kind of similar and this comes out to be a simple equation in terms of the function1 over 1 minus z squared c of Z。

So if you differentiate that， you get this thing and that's then equivalent to our equation。

 so that's2 over 1 minus z， and now we can just integrate that simple thing and that shows that c of z times1 over1 minus c squared is equal to integral of that。

 which is2 log 1 over 1 minus z。And that's a solution。

 And so that's solving the differential equation to get an explicit representation for the generating function。

 not too bad。 It's a standard differential equation。

 And now we want to extract coefficients to find the number of compares taken by quick sort。

 but that's easily done。 we've seen that one。 that's the example that we did for an exercise。

 It's 2 n plus1， HM plus 1 minus-1。So OGFs can solve recurrences even as complicated as the quick sort recurrence。

There's many other examples of solutions of recurrences using OGFs in the book。



![](img/f93ded3b3fb36fb898e63c4bfccea719_4.png)

![](img/f93ded3b3fb36fb898e63c4bfccea719_5.png)