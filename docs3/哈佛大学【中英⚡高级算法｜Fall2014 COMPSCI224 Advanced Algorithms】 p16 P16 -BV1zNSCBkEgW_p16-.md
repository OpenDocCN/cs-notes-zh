# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p16 P16 -BV1zNSCBkEgW_p16-

![](img/47c5fe87f7774f8e9987f42d8f160327_0.png)

嗯。Yeah。Hello。I we'm not sure exactly where people are。I guess I'll wait one more minute。

Is there some event today， you？Oh， let me make sure。ok， well。I guess I'll just get started。

 So today I promised you we're going to cover。Interior point。so。This is， oh， are you todayscribe？

 Okay， good， let me。I， so okay， so I just started like five seconds ago。嗯。

So today we're covering the interior point method。And this this is a method for solving。

Solving convex programs， but。You， we're just going to look at it。

We're just going to look at it for linear programming。And。

I think I mentioned last time at the end of last lecture。And this is introduced。As a method。

For solving LPs。By Carmarcar。This is combminatora 84， so combinatora。Okay。🤧。And。

I said some very vague things last time， so our setup。Let me just remind you of the vague outline。

 our setup is we want to minimize。C transpose X。Subject to AX is at least B。ok。

Where this is coordinate wise。嗯。As。Let's say it's an Mbi in matrix。And B。SoAnd B is well。

 B has to now be in R。MAnd x is in Rn。Okay。So the basic idea of an interior point method。

And I'm going to keep abbreviating the interior point method is IPM。Okay。The basic idea。Is。Minimize。

F of lambda of x， which I'll define to be lambda times C transpose x。Plus。Some barrier function。

Let's call it P of。I'll say what this is in a second， P of S of x。Where。S of X I。Is the slack？AI。

 x minus B。so for any feasible solution X， we have that the eye throw of a， let's call it AI。

 AI dot X is at least B。Okay， so AI dot x minus B is some non negative real。For any feasible X。

And the vector of all of these differences is called the slackck vector。

I'm calling it the slacklack vector。So S is defined as follows as this。

P P of S of x goes to infinity。If any。S of X I。Goes to 0。ok。

So the point is that if any of the S of x sizes are0。

 that means you're right upon the boundary of the feasible region。Right。

By penalizing the objective function in terms of this barrier。

 this P is called a barrier function because it keeps you away from。

It's a barrier preventing you from getting too close to the boundary， basically。

Right by penalizing with this barrier function， you're ensuring that the optimal X for this is not too close to the boundary。

 So it stays well in the interior of the feasible region。

 And that that's why it's called an interior point method。 You have， you basically keep track of。

Points interior in the feasible region，And the point is as。Lambda goes to zero。嗯。Basically。

 C doesn't matter。And。The optimizer。Let me call it。X lambda。

So this is the optimal solution for this F of lambmbda， the minimizer。

This goes to what's called the Ananalytic center。Of the feasible region， the feasible region。

 let's call it P， which is the set of all points x or that ax is at least P。Meanwhile。

As x goes to infinity， or lambda goes to infinity。X of lambda goes to。嗯。X star where。

X star is the minimizer。Okay， and I'm not going to spend too much time on this， but。

You can assume that if this thing is feasible and bounded。That the minimizer is a unique vertex。

 There's only one vertex， which achieves the minimum。The basic idea to ensure that is。

 so we discussed earlier that there's some precision thats that this LP obeys like all the entries have Ls of precision or some such thing right What you can do is you can create a new cost vector where you just add kind of random noise。

At the 10L bit of precision and beyond。Okay， so that random noise will ensure that there's a unique vertex that's optimal once you randomly pertuurrb this cost vector。

So I don't want to get into precision issues， but there are standard tricks that ensure that the vertex。

 which achieves the minimum is unique。Okay。I'll put a link in the notes to some of these because there are too many such minor tricks that I don't want to get to。

Okay。Okay， good。To actually implement this basic idea， Well， I mean， who says that。

Who says that we can solve this problem either， right？So what are we going to do？So。

The vague outline。OfOf the algorithm。We'll look as follows。Step 1。Let me call this。This is our LP。

Modify。LP。To LP prime。Such that。LP prime。Trivially， has some trivial。Interior point。嗯。2。Okay。So that。

If the LP is bounded and feasible。Then， we can。Read off， basically。The optimal solution。To LP。

From the optimal solution TLP prime。好。Okay， so now we have this LP prime that we're trying to。

