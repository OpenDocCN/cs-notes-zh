# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p14 P14 -BV1zNSCBkEgW_p14-

有。

![](img/f0c28dbcaa986effa47e40328f2ffaf9_1.png)

Okay yes， I'll just get started。So a couple things one is。

I think I sent some email about project proposals which are due next week， Thursday。

 I don't think the website has a time。呃。If it does have a time， you should stick for that。

 I think it doesn't。 So that means anytime Thursday， which means， I guess。11，59 PM。Thursday evening。

嗯。Yeah， and you know the primary purpose of this product proposal is。

To just make sure that you're looking into potential projects， right。

 So the project is due sometime in December during， I guess the last day of reading period。

 whenever that is。And I just wanted to make sure that。You know， you don't start， you know。

 you don't start thinking about project ideas the week before or something， right， So this is。

This date is here to force you to think about project ideas。嗯。And yeah， so you shouldn't。

Even if you think you might want to change your project later。You still have to do this。

 And if you do want to change， you can， but you would have to like submit a new proposal。

 and these things aren't that long anyway。 but I just want to make sure you have some project idea。

By next week。AQuions about anything related to the project。Good。Yeah。

 so I guess last week you had a couple guest lectures。And before that， I think I ended with。嗯。FP ta。

 F Pra and。SDPs， inity apps and SDPs， right， So， okay， so good。 So for a while now。

 we've just been talking about linear programming and saying there is some magic machine that can solve linear programs。

 And we never really got into how you would actually do it。😊。

Okay so it's about time that we actually give algorithms to solve linear your programs。

 and so today I'm going to start off with the simplex。I'm also going to prove strong duality。

 and you'll see that kind of the proof that simplex works。

Implies like it just gives you strong duality for free。 Okay， so like at the end of simplex running。

 you like you'll be able to read off a dual， feasible solution。Which achieves opt， okay。

 so that implies strong duality。嗯。And then if I have time， I'll say a little bit about。

So one issue with Simx is that it works well in practice。

 I'll cite something during lecture that gives some evidence for why。But in the worst case。

 all known implementations of simplex， in the worst case， take exponential time。

So then I want to tell you a little bit about how to get polynomial time in your programming algorithms。

Okay， so today。So one， is going to be let's say solving LPs。So one is going to be the simplex。

Algorithm。And two is going to be， we'll see， for example， certain things like strong duality。

And complementaryary slackness。And three。🤧。We'll see a little bit about ellipoid。

 just like what it is。Or what it's roughly about。Okay。So。First of all。So LP is linear programming。

So far， I've been saying that we want to do minimize C transpose X such that。And then。You know。

So many linear inequalities。Okay， so for example， it could be that。A dot x is equal to B。

Or is that most be or is that least be， there are many different types of inequalities you could have here。

Okay， so I want to put everything in what's called standard form。Okay。Which is men。C transpose X。

 such that。AX is equal to B， and x is at least0。Okay， where。This is a vector。

 so what I mean here is that coordinate wise， it's at least zero。Okay， and here。嗯。

X is an n dimensional vector。A。Is M by N。And。N is at least 10。Okay， so I claim that any。嗯。

Any LP of this form can be written as in this form， and I'll say why。And， you know。

 if you have a maximization problem like max C transpose X， that's the same thing as。

LikeSo this could be Max Orman， right？But you could， without loss of generality。

 say it's min because if it's max， that's just minimizing the negative。

 so you can put a negative sign on all the entries of C。Okay。

 so so how can I write anything in this form。So first of all。So getting to standard form。

 how do I do that？Becauseuse as I'm going to describe the simple algorithm。

 it assumes that your LP is written in standard form。 So that's why I want to put it。Like that。

So how do we do that， Well， if I have a constraint。Imagine this is like a row of A。

 if have a constraint that says AI dot x is equal to B。Okay。

This is the same thing as having the two constraints。AI。t X。Is at least BI as well as？AI。X。

Negative A dot x is at least B negative B。Is that what I wanted to say， so I wanted to say yes。

 I believe so okay？And similarly。AI。tX。Is at most， BI is the same thing as negative AI。tX。

Is at least minus B？So this already says that the only constraints we have to deal with are greater than are equal to constraints。

Okay。And then we can define Slack variables。For each constraint I。We define。A slackck variable。S I。

 which we， and we write a constraint that S I has to be at least 0。

And the point is S S is going to represent the difference。 So if this is greater than equal， it's B。

Then this means that we can write AI dot X as B I plus S I。 So S I is just the gap between these two。

 between the left and the right hand side， Okay， so。So replace。AI。X。Is at least B？With。AI。X。

Plus minus S。Equals B。Okay。Very good and then so that already。

That already says we can turn everything into this form that AX equals B。But there's one more thing。

 which is this x greater than equal to zero business。And actually， let me just write that here。

 actually。So。We can write， for example。X。X to be X plus minus X minus。Where。

Xi plus is at least0 and Xi minus is at least0。any number， whether positive or negative。

 can be written as the difference of two non negative numbers。O。Good。

 so once we do all these transformations， then all the variables that appear in our LP。The slacks。

 as well as these plus minus variables， are all non negative。 Okay。

 so all the variables in the LP are non negative， and all the constraints are equality constraints。

Okay。And the reason that n is at least M is because for each of the constraints。

 we have a slack variable。Plus we have all the variables we have before。

 so the number of variables in this LP is at least the number of constraints。Questions about that。

Yeah。I mean， I haven't told you why any of this is important， why did I put it in。

