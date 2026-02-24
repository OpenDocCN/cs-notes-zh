# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P2：Lecture 2.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/bdf811107d5ae55e5281bcd04a800b3b_0.png)

All right， welcome today we'll continue talking about convex optimization as a tool for design algorithms。



![](img/bdf811107d5ae55e5281bcd04a800b3b_2.png)

Let me share。

![](img/bdf811107d5ae55e5281bcd04a800b3b_4.png)

So。Right， so what's the plan， So the plan is first we will。

Finish the proof of gradient descent from last time we didn't really do a proof。

And then maybe the couple of small remarks， and then we'll start talking about mirror descent。Okay。

 so， okay， so let's。Go back to our algorithm that we had discussed last time。

 which is the gradient descent algorithm。

![](img/bdf811107d5ae55e5281bcd04a800b3b_6.png)

Okay， so。So just to recall， this is an algorithm we have。We have a convex function F。It's Liphis。

 meaning for every pair of points， X and y， well， I guess the way we will use it as the gradient of F ofX。

Is always at mostel in norm just abound on the how quickly the function changes and our iteration is clearly the following it's just xt plus1 is。

Xt minus Eta times the gradient Okay， so what's the theorem we want to prove about it？m sorry。

So the theorem that we want to prove about it is the following。So you want to claim that。After。T its。

Okay。After the three iterations， if I look at the average value of the function。On my its。

It's not much larger than the optimum value。 So this is the optimum value of the function。

 this the minimum value of the function， this is mean。X， if of x。And。What to say the most。为啲。Where。

R is the distance from our original point。And the。O。

So if you start at a distance r from the optimum and then you run  for Terations。

 your difference between the average values of function and the optimum is at most R。Okay。

 so what's the proof？Well， the proof is going to be short。

 but let me just do it carefully because it's。Sort of you know the same kind of schema or proof schema will appear again and again。

Allright， too。Yeah。对知道。do。Let me write down the first。Xt times xt minus x star。Okay。

 so where is this coming from， well this is coming from the definition of convexity for a convex function。

If you recall， f of y is always at least f of x plus the gradient of f of x times y minus x。

其实 this is。The function is always about the linear approximation so if this is x the linear approximation to the function is this and the function is always about the linear approximation okay and a consequence of this is you know if you just invert it another way to you know flip this statement around is。

You know， if you're anywhere somewhere， let's say you're here， right， your Xt is here。Okay。

 and your X star is somewhere here。Good。Now， another way to say this is you want to say that the gradient of atxT is steep。

 at least as steep well。我我。How steep is it Well， the claim is that the gradient at Xt。

Is steeper than。This line that joins。Xt and external。Is steeper than。

Line joining xt and x star so I mean in one dimension of course you the multidimensional version of this。

 but basically what is the line joining X X， how steep is that well there is f of xt minus f of x star divided by xt minus x star。

Okay， in some sense， this is the reason why。You're never actually lost in a convex function。

 you have a smooth convex function wherever you are， it doesn't matter where you're in the domain。

 if you look towards X， which is the lowest point。Along that direction。

 the gradient or the terrain the gradient to be very steep along that direction if you just look towards extra。

 no matter how complicated where you are。So that's what this is and that's our first step and we are saying the gradient is at least this effect statementma is a effect star。

Okay， so this is good now。Now， what do I do， I'm going to。Just substitute for the gradient。

From my update room， I'm going to write this as。X。T plus one。Sorry。I to say。XD。Minus x d plus1。

Over eater。In a product， X T minus x star。Okay， I write。

My fonts on x are confused like there some are different but all of them are the same x so it's just xt minus xt plus one divided by Eta times so this is just by definition of grain descent。

This is from the update rule。RightOkay， so so far so good。 and now。

We'll forget about the Eer for a moment。And。We will use。This other fact。

And writeite it on a separate page because we'll be using this in a different form again。

It's just a silly identity， but。It has a name。Because。Love cossine。I think it's the law cosine。 Okay。

 so what what is it， Well it's just this。Simple fact。呃。So。Let me get this right。 Okay。

 let me just write it and see。ok， so诶。It's this why is it called the law of cosine。

 it's just an identity you can expand out and verify but why is it called the law of cosine you know if you remember from。

Clain geometry。If this is a， this is B， this is C， I guess let me use different letters。

 not confusing so if。If this is x， this is y， this is z， then z squared。

Is equal to x squared plus y squared。I wanna say， plus。2 x， Y cosine of the angle theta between them。

This is in terms of vectors， it you could say it's norm x squared plus norm y squared。Plus two。

In a product， X come away。Yes， okay， thanks for the correction， it's a minus2 x y co。Thanks。Okay。

 so so this is basically that， you know， if you call this point a， this called point B， this point C。

 you know， a minus C is this vector b minus C is this vector and。a minus B is this vector。

So it's just that okay， so， you know， and the way to verify is the proof of this is just expand out the RHs。

Expand our rHs and it will turn out to be equal toHs。Exs just。Lazy。So。

I'm going to apply the lo of cosine here。And expand out。Okay。So。嗯。So Ill keep the Eta outside。

What I end up with， Ill get a two because I。Because law cosine， So it'll have xt minus。X T plus1。

Hold squared。Gs。X D minus。X star holds squared minus。The difference between the two。

 which is xt plus1 minus extra hole squared。Okay， so that is。Okay， just apply the lo of cosine。 Okay。

 so now this is good because。If you。Look at this expression。There is a telescoping happening here。

So what do I mean， I'll just rewrite this whole expression again in the next page。 Okay。

 so I have F of Xt。Minus f of x star。This is less than。I keep the one over eatta out。😔。

I get x t plus1 minus xt hole squared。😔，Plus。XD。Minus x star hole squared， minus x。T plus1 minus x。

Hold square。Okay， that's that's the expression we have。 Al right， so what's happening here。

 the second term。Here。The second term， you see that it's a difference of。YouT and T plus one。

 it's like D sub P minus D sub t plus one。That's the second term， it's a difference of two distances。

Whereas the first term is， of course， is just the length of the step you took。

Right the first time the length of step you took second on the difference Well。

 the good thing about these differences like this is that if I add it up over different values of t the telescope so meaning if I take this inequality and I add it up over values of t equal I equal to1 through t。

If sum this over all values of I equal to 13 t。Okay， what do I end up with， Well。

 Ill have f of xt minus F of x star。I guess。That's fine is less than or equal to。Well。

 the first you know you can't do anything， you're just going to add it up over all values of x equal to 1 through t。

So， it's just a。Because the first term is。Some of squares of how much you move。Right in each step。

Okay I'm going to keep it that way。 The second term is nice right the second term something nice happened there well。

 it was a difference of t and t plus one。 So when you add it up overall t from  to1 through T。

Things neatly cancel out and what you' end up with is just the first term。So this is。

 I just got this by adding up oralty。Professor， what's I over here。Oh， I'm sorry。 I should。Thanks。

 I should say a for p si minus x star。Yeah or or。Yeah， let me just change that to tea。😔，Let me do。ok。

Yes， let me add a for I equal to 13。Thanks。Yeah，这 a big one。Okay。Does it make sense？Okay， so now。

Okay， so now what about the first term well the first term is kind of you know we're going to use a very naive bound on the first term so precisely when you telescope。

 you still need minus D like minus some x t minus x star right？Or the last term。

 do you mean the last term， Yeah， when you telescope， only the middle term should cancel， right？呃。

INo， I think， so basically the telescope is of the form D1 minus D2。Plus D2 minus d3。

Yeah so add those up and you're gonna get d1 minus D3 right you add the first two terms right you get D dt minus dt plus one if you add them up Ill get d1 minus dt plus one that's right yeah yeah that's right actually there is a final term but that's basically zero so that's zero or actually order in fact it's sort of going in a direction which is good for us because negating us right it's going to be minus xt plus one minus x。

Wold square and I'm going to， since there's a less than equal to here， I'll just decide to drop that。

つる。GoodOkay， so then right then we are just left with the first term。

 the first term we're sort of going to use a naive bound well what's a naive bound。

We know that X minus X X plus1 minus X is just。Eer times the gradient。At F of X I。That's， of course。

 the definition of the algorithm。 So we're talking about。The norm norm squared of this guy。 And。

 of course， we assume that the function is lips shits。

 So meaning the gradient is never longer than L。 So it is Eta squared L squared。Okay。

 so you just use that bound here and you end up with。Eta squared。

Let me just simplify stuff writing everything down Okay there was a two here I think I missed。😔，Yeah。

But basically， I get Eta l squared over2。但啲。Plus。嗯，啊。我尔 do立的。Okay。

 where r was the distance between the first initial point and the optimal maybe we should have a square here to avoid this complication。

So then， you know， you just。嗯。Solve for the best value of。Eita， right。

 you pick the best step size right now。Step size Eta to be the one that minimizes this。

So i think you big up。R over L square root t。Actually， let me use R squared。😔，Or squared。Yeah。

I think this is good。So then you get this to be Rl overrupD。けた。So that's the theem。So。I mean， the。

Yeah。You see that it's fairly symbolic， but very few pieces of critical steps。

I guess the most critical thing to remember is this fact that at any point the gradient is steeper than this per value。

That's your certificate that you can make progress and that's what we started with。

 that's our first step in this。Proof。吓。Afterwards， there's a little bit of symbolic manipulation。嗯。

Yeah。Any questions about this？Professor， how do you get from the step where it says ata squared L squared to the next step？

So the last here or this one， or I substituted right， I had this， I substitute this over here。Oh。

 I see。 Okay。 Thank you。Professor lastly， Hugh said that this theorem only works for appropriate Eta。

 Does that mean this specific R over L square root T right， Yeah， that's right。 Is there like a。

Bigger， you know， possibility。OhAs in right， so this proof as of now。

 I didn't use anything about the value theta until the last step。

Until the point I came here so you can pick a different value of eta then you know it'll still mean you fix an eta then you can find a t at which things will work right this is sort of if you want the best possible rate of convergence for a given t if you fix a T and you want the best possible rate you could do this you could pick this eta but you know alternately you can just fix an eta that you think is fine and then you pick t large enough you still。

This is still work。So I think at the end I sort of skipped another step。

 so what we calculated here is the total error or total error across T steps or total regret。

 I guess will come to this term noulatorator， but basically this total regret across T steps。

And then of course， the theorem had was。Pse， you know， per height rate， What is the re divide by T。

 So it's a。You say1 over t submission F ofxii。Mus f of x star。Is a。Eta L squared over。到弟。pl。Aqua。

Over to830。Okay， so that so you see here you can fix any Eta you want then you make t sufficiently large you're fine and I think the best choice of E in this for this particular analysis is to pick this and you get one over square root t convergence。

Okay， thank you。我不发事。in the when you do the average， I regret。

 I don't think there's a T in the denominator in the first term， because and when you divide through。

 doesn't it go away。😔，So in the second term， you mean。

 so this on the right hand side yeah over here right yeah thanks。好right。Anything else？

For a practical setting， we wouldn't know what R over L is， right？Well。

 you would know you would have some estimate on R and L。Okay。

You'd have some estimate an RNL and as we said， you fix any value of RL and Eta。嗯。

You get some bound right， you know this this proof still works， which is some bound。

 the bound improves with S T goes to infinity， but yeah。Yeah嗯。

It doesn't go to zero as was pointed out。This first term is independent of T。

And that makes sense because if your function changes at you know。At the rate of L。

 then you should know that and you should take step sizes smaller than that like that that's your。

Margin of error， if you take steps exercise ET， you will link error which is EL。If it good。

Professor how do you get from the inequality from the second to last step to the equality and the last step should the last step have an inequality instead of inequality thanks yeah。

 that's right yeah。便ing过れ yeah。Thanks go。Yeah， sorry， yeah， Okay， so this is that's right。去。

Okay so that's good so we have basic analysis of gradient descent for different variants of great gradient and descent you do sort of you know slightly modified versions of this analysis。

 so for example this is kind of an important variant just to show you what is this important variant while you have。

You want to minimize a convex function。Subject to the function。

Subject to the x being inside a convex set K。There's a convicx at K。Then xt is inside。

And the iteration， the projected gradient decent iteration is you add eta times the gradient。

You get Yi。嗯。Well， let yeah， YT plus one。You get y0 plus。

 which is outside because this is after you add the gradient and now you to get the next trait。

 you project back。To the con website。With project back is just。Minimize the L2 distance。Find z。

In the convex set， such that z minus yt plus1。The L2 norm is minimized the closest point in L2 distance inside the set。

So that's your project。Okay， so this this is a slightly different gradient so each time you're going you know adding the gradient and then presenting back to the convex set。

 so how do you analyze this？If like essentially， the proof is。Nearly the same。U。Except for。

A small change。 So let me。We try to show you that with a different color。😔，All right。

 so this is the analysis of projected gradient descent。Well， again。

 you start with the same expression。And then instead of xt minus xt plus1。

 you write down xt minus Yt plus1。Right， this is。This is what， I mean。

 that's the only thing that changes。Okay， and then you apply loF cosine。To what you have here。

 So you get。So， you get。Xt minus yt plus1 whole squared。Right。Plus xt minus x star hole squared。

Minus。喂。😔，P plus 1 minus x star holds squared。Okay， it's the same， is just redoing the same。

Thing with the Y P plus one is Xt plus one。Okay， and so then， you know。The only trick。I。诶。啊竟然。

This the first term here。For xt minus yt plus1 hole squared， you will use a nive bound which is like。

 you know， this is the gradient。This is the gradient， so you use the na bound that this is at most L。

Just like we did here， the first term be bounded by L。

The second term looks like it has this xt minus x star， but the third term。

 instead of being xt plus1 minus x star， it's yt plus 1 minus x star。

 okay so you're not getting telescoping， but you' just one step away from telescoping。

 what do you use， use the following fact about projections。

So what's the fact about projections if you have a convex set K？

And then if you have a point outside y and you have a point inside x star。And you project why。

To some to get to the convex set， you get pi of y。So the projection is always closer。Then。

The original point。Okay， the projection of the point y is closer to extractt than。Why is to extra。

This is for all X in the convex set。And then for all while。

Basically it's just saying the projection always takes it closer and so you just use that inequality here and you're done okay。

You go back to the same proof， the rest is the same proof。Okay， so it's time。Okay that's。

It's about all I wanted to say about the proof of gradient descent， any questions on that？Okay， so。

All right， so before we go on to mirror descent， some comments on gradient descent。

 which I think some of this we we commented on last week， but。

Just to make sure it's all there so first thing to notice is the number of iterations is actually independent of dimension。

That's kind of nice， so this method is in dimension independent。

You can do it in n dimensional space or in square dimensional space all that matters is our infinite dimensional space also it doesn't matter all that matters is that。

Your distance optimum is R。And you have a lips sheetitz function of L。 So for example。

 you could be doing gradient and descent or the space of functions or the real line。

 which is an infinite dimensional space and the same。Bounded toward。

Okay that's kind of that's very nice fat property to have it's well the the convergence bound we got to order one over root convergence right so order one over root error。

In P iterations。 So this is actually。T。As in this optimal。ForFor lipsshs functions。

So note that the only thing we assumed about the function is that it slip sheets and so it can be nonm。

 right？So it need not have second derivatives， of course we assume the implicitly in our algorithm we assume that it has first derivatives because we use the gradient of f in our algorithm in on the homework there is a version of this where you use sub gradients instead of gradients so which means it doesn't even have to be differentiable at every point。

So， but this is optimal and note that this error is actually。It's fine， but it's actually。

Sudopalnomial time。In like， in the。It。Right。Meaning to get for error。Epsilon。

You take order one over epsilon squared iterations。

Which is a little bit bad because you know if you want two to the minus b bits of precision。2。

 not want2 to the minus B precision or B bits of。2 to the minus B error or B bits of precision。

 then you would need runtime， which is not2 to the 4 b or something，2 to the 2 b。

It is exponential in the number of bits here。Okay， and。What else well。嗯。嗯。The。

The other thing is we all only thing we assumed is you can compute gradients or actually as you'll see in the homework you just have to compute sub gradients so you just need a gradient or a right you just need to be able to compute the gradient of the function to run the algorithm and in many cases you don't even need a gradient because。

Even if you just have a value or a meaning you can just estimate the value of the function。

 you can estimate gradient easily if you can estimate the value of the function。So。Right。

 so I mean the。So you know there are many estimators to many ways to estimate the gradient。

 the most naive way is if you're at a point sort of sample points in the tiny neighborhood around it and then try to fit a linear function right that's like the most naive thing but you know you can you can try most。

Simpler， you no more succinctly clever things like， for example。嗯。You know， if I pick a random delta。

嗯。不错。Like this is sort of an estimate of a gradient。嗯。切。Well， basically all I mean is sir。Okay。

 let me not， let me try to。嗯。你得岁 so。Yeah， so F of x plus delta times delta。

W intended to scale it appropriately。做。嘅诶。You know， if you like this is basically in one dimensions。

 this is just saying Id take f of x plus delta minus f of x minus delta and divide by two delta okay in many dimensions as a portion of this。

 but。Yeah you know it's quite easy to estimate the gradient and also you can even have a randomized estimate for the gradient and that brings us to I guess what's one of the most widely can used thing nowadays。

 which is a stochastic gradient decent and in stochastic gradient decent you you don't have the gradient but you have an estimator for the gradient。

So you have an estimator， let me call it E of x， well e is probably a bad theta f。

Such that the average value of that estimator is the gradient adapt。是。Okay， so this is nice because。

You can basically。への意見うん。Basically pretend that theta is a gradient。

And you can just run the gradient decentcent algorithm and if you look at the analysis of the we just did。

 you can actually， if you go through it carefully， you'll see that the analysis interact nicely with this averaging。

So although theta is only on average the gradient， the analysis works neatly with a。

 it can push the averaging inside the argument， so I mean that sort of gives you like the basic stochastic gradient design。

Okay， and。Finally， you know。This is sort of the worst possible situation you can be。

 you have a lipsts function， which is non smoothmth。Usually you're in much better situations。

 your function is smooth。Right meaning the gradients change slowly。

 that'll be you can get1 over t or even better sometimes you will be in a situation where。

You have a smooth， strongly convex function。You have a smooth。And strongly convex function。Yes。So。

In this case， actually， you can get to exponential convergence after。The iterations。You can get。

Exponential convergence。Smoothness parameter。And alpha is a strongly convex parameter。

Strong convexity parameter。So。嗯。So I mean， like alternately， if you know that the hessian。

The second derivative matrix of the function， the hessian of the function。

Has its smallest eigenvalue。So the smallest taken value of the Hassian。Is at least alpha。

And the largest eigenvalue of the Hessian。Is always at most beta。If you know this fact。Then。

You can get a better analysis of the。Algorithm， you get an exponential convergence to the optimum。

Okay， and this is usually what we mean by polyno algorithm we want to compute B bits。

 you take poly in P time。嗯。This is really a truly polynomid time algorithm in some sense。

And that would be the gold standard。Okay， any questions so far？Okay， that's good， all right。Oh okay。

 so we are I think we are halfway through it。 So here's a plan。

 let's just take a quick five minute break and then we'll talk about medicent and what I'll do as we take the break is I will。

P the。嗯。A bunch of breakout rooms。And I won't assign anyone to any room。

 but if you'd like to just go and chat。I'll just create a room and I'll close out the rooms in five minutes。

All right， okay。And if you want to just hang out here and ask questions， that's also fine。Professor。

 I had a quick question。 So when you say polynomial time algorithm De mean in number of bits， Yeah。

 that's what I mean Okay， okay， cool。 Thank you。Yeah。You know， that's。Right。Yeah。

 I mean that is actually sort of at the boundary of two areas so the whole area of comminatal optimization and minpanning trees and all our good old polynom algorithms is polynomial in the number of bits and then there's a whole community which is numerical methods and so on where this is not you know super important。

Yeah clearly important to get expensive convergence， buts of it's not clearly brought up。



![](img/bdf811107d5ae55e5281bcd04a800b3b_8.png)

But yeah。There's some cheating going on here， right， because。You're arithmetic up till now。Leeds to。

Be of arbitrary precision， right， right？And then you're now you're saying， oh。

 I'm accurate up the D bits。是。Oh oh yes， yeah you're right so actually yeah there a lot of cheating in that sense。

 but writing the sense of how accurate I am yeah usually that is actually quite Harryy to really work out as in if I did all these operations。

With the finite precision like B bits， if everything was finite bit precision B bits。

 how well does it work， it's quite。But it's done。I mean， I guess， well， there's just。

Addition and multiplication it be better， right， So if。If your Eda is like a power of two， then。

Probably not that bad。Yeah， I think， but like I guess really following through on the number of bits is quite annoying actually。

 if you think about even。Solving linear systems actually， that's annoying already there but。

I think if you go back and look at the first polynomial time algorithm for linear programming so that's where actually I guess one place where this interface between the two communities comes up right so well linear programs were solve in practice since what 40s or whenever it was invented by simplex so on form right and the first polynomial time algorithm was Kaian in the late 80s or something early late 70s and it's a big deal the first polynomial term algorithm。

But then if you try to say， okay， is it really poly time， you。

 you try to look into that the paper by。Gts loa sand。I miss for missing the third name GLL。

 maybe Ltra， Okay， basically three people who basically comprehensively worked out every bit calculation。

 what happens if you do in this precision and so on you should look at if you look at that paper。

 it's like。So long， but it's yeah。It's quite tedious actually， to do it。 but， but， you know。

 that is the sort of the。that's just that just that too much work please please don't do that Oh I mean no yeah I。

😊，いや。嗯。So when they did the analysis did it turned out to be polynomial in a number of bits Oh yeah。

 I mean they have I guess I mean it is it is polynomial a number of bits you just have to be really formal about what we mean by being poly for example。

 if I just say a linear program can be solved in polynomial time。That is。Fair thing to say， because。

Linear programs have a special property that if I give you a linear program where every coefficient is a B bit1teger。

Then the solution is also a rational number， so at least you don't need infinitely many bits to write down the solution exactly。

 so you can write it on in polynom in fixed number of bits。

And then the question is is the number of bits you need。

 does it grow super polynomly as you do all these operations that intermediate operations you don't want it to grow。

 so yeah you need to like really work out to prove that if I give you a linear program with B bit in teachers it can write down a solution in poly in B time。

RightThat is it's a little tricky thing to completely work out but。

If you go to other things like SDP is a s program the true optimum cannot even be written out in finite number of bit meaning it's not a rational number。

 so if it's not a rational number then you it really had to deal with accuracy you say。

To get it in epsilon accuracy。Then， yeah， it's a little bit。

If we whether what's the right definition of efficient？

But it is important to get exponential convergence。And they call it Linux invertance。

 I close at the breakout room。All right， so this is good。とお。Sorry。O。K。All right。

 so now we'll talk about mirror descent。Okay， so one thing that should really sort of make one uncomfortable if you stare closely at gradient descent is it's sort of a strange thing to do。

I mean， geoally it looks fine， but if you think about it。Wai， could you share your screen？Oh。

 I'm sorry， yeah。ip panda。So it's a strange thing to do because。Gemetrically。

 it just looks like you're going in the direction of the gradient。But。



![](img/bdf811107d5ae55e5281bcd04a800b3b_10.png)

As you brightly or in terms of units， it's a little bit off because you're taking a vector。エ？Right。

 and you're adding the gradient to it。if just in terms of units and physics units。

 x and the gradient。As not in the same units right right it's a strange thing to just add the gradient。

And you know this is more conceptually wrong if you think about you know mathematically where do these xt and gradient live Okay so what where where is xt so let's call the space Xt that's the place where we optimize that xt lives in the space which is R to the N。

It's called that the primer， I mean。It is very exilious。Right， and if you have。A space like that。

 the gradients。Live in the dual space。嗯。The gradients live in a dual space。So。

What I'm going to say now is not super important to follow what' happens next。

 but you know in basically in if you look at function spaces or in functional analysis。

 you have for example， like you know LP space LP space is。Or to end。

Where the geometry is a P norm geometry， p norm as in summation x the norm of a vector。I。

The norm of affected。summation X to the P called to the 1 over P。

 So L2 space is the most natural Euclidean space that we think about。

 but you can pick a different value of P。 So if you pick L infinity or L1 that these are all different spaces Okay。

 and if you have。嗯。Your vectors x living in LP space， the gradients naturally live in LQ space。

W is a。Also， know， which is basically art to the end。Where the norm is the Q norm。Okay， and。Yeah。

Theyre the Q norm and such that Q is1 over Q plus1 over p is1。It's the dual space。Al。

 another way to say actually you know formally in functional is the easiest way to say what these are is the following。

 well x is just a vector。Right x is just a vector。ok。

What is the if you think about it in terms of types， what is the type？Of the gradient。

What's the type Well， if a gradient is something which if you give it a vector。

It'll give you a number。Gradient is basically the type of a gradient is it's a function that takes vectors and gives you a number。

It's a linear functional。So in some sense of a different type， it's an object of a different type。

 it lives in a different space， which is the dual space and you know it's an object of a different type。

Like why is a gradient a type which takes a vector and spits out a real number。

 well what is a gradient gradient is something？The computer is differentiation of gradient tell what you do。

You at a point， if I tell you some direction to go。

 the gradient tells you how steep it is in that direction。Right， it's a。あ。

So that's why just adding the gradient to this is not the most。Obous or natural operation。

 And in fact， there is no natural。Single operation that you can do with the gradient you can。

Use the gradient in different ways than just adding it and that's what we'll see so it doesn't matter if this discussion didn't make so much sense I was just trying to for people have seen a little bit of functional analysis or LPLq spaces is to point I just trying to make make show it together there but basically you know something is odd with the gradient gradient decent algorithm the types don't match。

So here's a different version of gradient descent with a great different way to state gradient descent。

 which actually makes more sense。So this is called， I guess， proximal gradient descent。

So what's this version。So the idea is， of course， you have a starting point。

 right x1 is a starting point and you're new it。So how do you calculate the new it rate？Well， okay。

 you are。Okay， you are at Xt， right， you are at Xt。Okay， and。Around Xt， around Xt。

 you have an approximation to the function， a linear approximation to the function。Right， sorry。

Have a linear approximation to the function around xt well what is the linear approximation。

 it is just the gradient of f of xt times x let me use y。嗯。Let me use x， let me just use x minus xt。

less。F of fixed0。Okay， so this is a linear approximation。Let me call this function。G h。嗯。Of x。

So this is just a linear approximation to the function。Around X。

 that's how the function looks like around Xt， so you could say let's just minimize this linear function。

Okay， that's a natural thing。 But then， you know this， you know that this approximation。

 linear approximation is going to fail if you go a little bit far away from X T。

 you don't want to go too far away from X T。 So what you do is you write down a different。You say。

 minimize。The linear approximation。Which is。Eer times。嗯。Okay， minimizeim the linear approximation。

 but you add a penalty for going too far so you say。So you had a penalty， which is in this case。

 the two norm squared。For going too far。So you say your next point is the minimum value or the point that minimizes the following function。

Okay， so that is really。So it's an algorithm， it's a definition of an algorithm at any point take your later approximation。

 add a penalty for going far away， which is this quadratic penalty and you minimize this。

Coratic function now。And you go to the minimum of this， that's your next point and so on。

So each step of citration。Is actually minimizing a quadratic function。

that's what you're doing each step。嗯。Right， so。Note that this。The way I wrote it。This。

Linear function looks different than the linear approximation here。

But I have basically dropped terms which don't depend on x。Thank度。Drop terms that don't depend on x。

Because you're anyway minimizing or x So whether you minimize。Like this linear approximation。

Or this simplified one， it's the same。 So for example I could as well write minimize h of x plus the quadratic clause it's the same thing。

So。That's why。It like。Finding the。嗯。The point that minimizes H of x plus the quadratic loss is the same as a point that minimizes this thing that I wrote here。

Okay， so does it make sense？So that is really。Okay， and actually did。

This is a different way to look at gradient descent。In fact。Let's just work that out。Well， okay。

 what did at each step， I ask the algorithm to minimize this。Wt to minimize。This function， which is。

Eta times the gradient。F of X0。In a paratex plus。好。Noome x minus X D， quote square。ok。

So I ask the algorithm to minimize this， right that's how I get xt plus one。Okay。

 so you know it's a quadratic so you can do the minimum you can find out the minimum just by calculus right you can if I call this H of x。

Let me call this just avoid confusion let me call this G of x Okay， I mean。

 how do I minimize it Well I said I take the gradient of G of x and set it to zero right this is a standard calculus you want to find the minimum of quadraatic or any function if you want to find。

Stationary point， you just set the gradient to0。 So if I want to set the gradient to0。

 what is the gradient。Graient is gradient with respect to x， of course xt is fixed。

 x is our variable。So， well， there's the linear term that just gives you。Eta gradient f of x0。Okay。

 and then。The quadratic term gives you。Let me write it， say， half。Do。X minus  x。Okay。

 this is just differentiating I'm just differentiating G of x with respect to x and seeing what I get and you can see that this is the same as saying the my x is actually xt minus。

Eta times the gradient of f of x。Okay， you see that。

We essentially recovered the gradient decent update rule。But in a somewhat more natural way。No。

 I'm not just adding the gradient that I'm just saying。

Minimize this linear approximation with the penalty added in。

So the definition doesn't go through dual space as of now， the definition of the algorithm。

Does it make sense？So it's just a reformulation of gradient decent， okay， that's correct。So。

But what it opens up is now it opens up the possibility that。I can。 I don't have to。Add a penalty。

 which is a quadratic penalty。I can think of adding any penalty。

Any penalty that sort of prevents me from moving away from Xt。Too much。诶暗。

And depending on what function I pick， what function I add as this regularizer。

This is a regularizer depending on what regularizer I use。I will get a different algorithm。

And essentially you can you can imagine putting down any regularizer any。Regularizer， but。

There are some properties of the function that you want to put there， which will actually make。

The analysis is simpler， which make it to help you analyze。So。So that's what we'll do。

Actually press out can I ask you one more question， yes。

So the fact that these regulars and is like the。I's a quadratic term in the distance is what makes it。

Kind of complicated。 right， if it wasn't a quadratic term and who was linear， then you can do this。

This sort of looks like expert algorithm。But you just update each。

Each if you look at this with like each component of the vector x。

 if you just have the inner product term， then it's pretty easy to update each X right the non trivial term comes from this regularizer。

Right， so actually we we， I guess in with regards to experts。

 we see that you put a different regularizer， which is the Kl divergence。

 cover the experts algorithm them。 So so different choices of regularizers you put there gives you different。

えの。Algothms， and they are sort of。Suitable for different you could I want to say they're suitable for different geometries of the problem No my point more is that this this a minimizing seems like you can do it really well。

Per coordinate， right， except for this last term， right？呃。Yeah， no。 so the so the usually。

So usually what you do is you pick a regularizer will pick a penalty function for which this argument is actually easy to compute。

As in in all the cases that we'll see or in all the special cases of the algorithm that we'll see。

 we'll actually be putting in some quadra regularizer like the quadratic or whatever exponential or whatever regularizer we put in。

 this update by itself would be easy to compute。And so for the quadratic update。

 you see that we recovered the good old gradient descent。And that is very easy。

 you just have to add the gradient。Right just had add eer times the gradient。

 so we recovered basically our simplest work algorithm。It just just looks more complicated。

 but you the' different in all the cases we'll see， we'll actually pick fairly natural regularizers。

嗯。So。So actually let me。Yeah， so I think right， yeah， you in this case。

 you get the coordinate by coordinate update yeah but。

That seems like a huge bonus for choosing this quadratic regular。 That's what I'm trying to say。

 Right， right， right。 No， yeah， you， you do get actually in in。We try to keep the regularizer。

 usually many algorithms try to keep the regular riser simple。Here， so that are。嗯。Yeah。

 they keep the regular simple at the algorithm。And each step is simple， yeah。Yeah， I mean， also。

 I mean， I think。Right。I mean， he's just a general comment on this sort of。

Work right so note that all of the things that I'm describing mirror descent and gradient descent and everything。

 this comes from literature， which is back from the 80s or 90s from optimization， right？

People like Nemirovski and so on。 And in that world of algorithms。

The description of the algorithm and the algorithm itself。Are usually extremely simple。

As you see gradient descent is just add the gradient and the mirror descent in all the standard versions of mirror descent is just yeah。

 okay just do the most natural， simple thing so as in the algorithms are very simple to state。嗯。And。

I guess you could say that when you try to design algorithms for combinatorial problems。

You can try to venture out to doing things which are more complicated for the particular application at hand。

Right， so for example， if you have graphs right， you know， maybe you should pick a regularizer。

 which depends on the graph like which is some function of on the graph right so that's more right we are getting right that's sort of。

嗯。Yeah， that's where like our work meets here。是。RightSo so okay。

 so what sort of the broad setup for this kind of a thing。

 this is called mirrordesscent so the basic。嗯。Function that。

S that you used to substitute for a quadratic is a brakegman divergence。 So what's a br divergence。

 you know to let you pick a convex function as strictly。Convex function strictly or you know。

 you could even say strongly convex， but basically。A strictly comics function is。You know。

 as you can imagine， it's a function that is never flat。 it always is moving， you know。

There's no section of it， which is flat。Right。It's never a linear function but it's always there's a little bit of tilt up words at every point。

Right， that's a。你我。It's never flat okay。Okay， so what's the if you give me any strictly convex function。

On some set， let me just say。Let me just say R to the end for now。

Here you have a strictly convexed function H。So how do you define brgant divergence so a you can associate a brgant divergence with it。

D of it。Okay what is d sub batch it's like a distance function right it's you want to calculate the distance of y from x。

Okay， so what is the distance of y from x？Let me see if I can reproduce this picture， I think。

If you just。Remember this picture。😔，Sort of is good so。😔，So this is our function H。Okay。

 and you're at a point x。Okay， and there is a linear approximation to the function at x。Okay。

This is a linear approximation to the function attacks and of course your H will stay above this linear approximation it's on top of this and if you give me any other point why。

Let's say this is why。Okay， and so this is H of Y。And you see how much bow。

The linear approximation H of y gets。So， this。This distance between the linear approximation and curve。

That is the brgman divergence， that is the divergence d sub batch of y from x。Right so。

So clearly what is it while it is just。You take the function at y and see how much above the linear approximation it is。

H of y minus h of x plus gradient h of x in a product y minus x。So that is a brgigman divergence。And。

You can see that it's for a convex function as you move away from X。Intuitly。

 the divergence goes up right So it does seem like a penalty that you incur like this looks like a penalty function that is。

嗯啊。Keeps you close to X if you add it。It grows as it go away from x。

So that's the definition of brakegman di， you pick any convex function。

 you can write on a corresponding brakeg dirgence。其就嗯。嗯。嗯。So you know。嗯。

Here are a couple of examples。RightSo if I pick it's my convex function to be just the two norm。

Then as you can imagine， the pregnant divergence。Nicely turns out to be， I mean。

 it's a good exercise to work it out， but it nicely turns out to be the distance。Square。

So this is this recoverer。So a gradient descent vanilla gradient descent starts with the convex function。

 which is the two norm and you can write down its corresponding beman divergence and。而家都有点。And okay。

 what else can you use？Well。If you use this function， which is。Okay， this is。It's the。

It's a normalized entropy。Of a probability distribution。

 but basically for now just think of it as a function or positiveitoryial numbers like this is a function defined on。

Because I'm taking longing over here， it's a function that defined on r+ to the n。Okay。

And then the corresponding fragment divergence is something that we sort of。

I must have seen in some context， which is。The care and diligence。Which is like the K divergence。

Between the probability distribution y and the product distribution x， you know， it is sum over I。嗯。

Y I lawn， Y byxixi。Okay。So that's good， so now you can just use this。

Back in the definition of the algorithm here。What you recover is the multiplicative weights algorithm。

 the multiplicative weights of the expert algorithm。

 you get that by just using this as your regularisizer。Okay， and。You can use the。Instead of。You know。

 we。The version of。Entropy for。Prob distributions instead if you use the version of entropy for PSD matrices。

 you get this algorithm called the matrix multiplicative weights if you have heard about it。

 but basically you can by just using a different choice of this edge you recover different algorithms。

And so all of them are doing just this thing。嗯。And actually。

 let's do one example which is kind of nice， it sort of goes back to our thing earlier。

So let's say I use。H of x to be。Instead of the so earlier we had the quadratic。Right， it was X，x。

This is what gives you gradient descent。So instead of this， if I use。H F x to be。X。Some other matrix。

 let me call it a。X。Okay， where a is a PSD matrix。So I mean。

 if you want to think about it instead of summation Xi squared。

 let's say I use summation W Xi squared for some W greater than equal to0 right basically it's you can use any quadratic P positive semi different quadratic as my convex function。

 all of them are convex functions so I can start the whole fragment divergence business with that convex function。

Right， and then I will get。You know， what do I get？I'll get the update。

 which looks like I'm going to write down the update will I'll leave it as an exercise to work this out it basically。

If you use H as this function。H of x is x transpose ax， you use that。

And you construct the Bgman divergence Dh， and then you use that in the algorithm as a penalty。

 then you'll recordcur an update that looks like xt plus one is xt minus。A inverse。Graient。F。At。XD。

So I mean， and I guess the only thing I want to sort of emphasize here is that what happens if you just use something like。

诶。Something like this where。要。Change your penalty， you change your penalty。

Right to from summation X squared that was the original penalty for going moving away from the function now it's a different penalty。

 which is summ W X squared。It's sort of。A penalty weighs different directions differently。

 some directions， the penalty doesn't grow quickly。

 some directions the penalty grows quickly depending on the values of this Wis or depending this depending on how this quadratic function behaves。

So。This gives you what we were referring to last time。

 this is basically preconditioned gradient descent。So in the last class towards the end。

 we were talking about this issue that if you have a contour which is very steep along one direction and very flat along another direction。

嗯。You would want to adjust your gradient descent to。Sort of。Take into account this。

 meaning it can take long steps in the direction where it's flat and very narrow steps in the direction where it is steep。

Baically in our gradient decisionnt analysis there's a single Eta which is a step size effectively what you want to have is two different ats right like it should moving faster on the direction very flat and slower on the direction very steep。

So how do you achieve this Well you can if you knew that the geometry looks like this and if you knew the a corresponding to that as in the quadratic form that forms these contours。

 then you could use that as your you know。H or the pregnant divergence。

 or we could write down the corresponding。Precondition grade and descent and that will work。

 you know thatll just。That'll work faster， meaning it will。

It'll give you exponential convergence where only you didn't have that。So that's the。So basically。

 but this。Proximal gradient descent by instead of picking the。

Two norm quadratic norm because you're picking a pregnant divergence here。

You're picking you're allowed to pick a very strange looking penalty function。

 you're allowed to it lets you exploit your knowledge of the geometry of the situation。

It lets you change the geometry right using the two norm is like saying I have the same penalty。

 whichever way do I go and my penalty is how far you went that is a two norm。

 but if you know something about the geometry of the problem you should use the use it So meaning you for example。

 for probability distribution， it turns out that。This function is especially nice。

And that's why multiplicative weight have much better。

Performance than just good old bra descent when you're dealing with probability distributions and you're dealing with probability distribution。

 the space you're working on is a space of probability distributions the space of probability distribution is。

The geometry is the L1 geometry， the geometry is I mean。X in not Dl one。

 the natural geometry is the KL divergence geometry。

So the most natural geometry for probability distribution is the one given by KL divergence。

 so if you use this as your strongly convex function， you get the right algorithm。

 which is the multiplicative weight。For vanillailular gradient descent in Euclidean space。

 the geometry is given by this thing。You can be super aggressive and say the following I don't care I don't know what this domain is at every point I will look at the function and choose the geometry。

That could be an algorithm that corresponds to using a regularizer。Which depends on the function。

 So if I did Xt plus one is augment。Or x of the linear part， which is gradient。

F of X T in a product X。Okay， and then the penalty。What penalty do I use here？Well。

 I'm going to use a quadratic。The quadratic I will use is。Ex transpose。ht。Of X T。X。

 so just to write it down， H of X T is the。Logo。Hian。Of the function。

F H sub F is a hesian of the function， meaning。It's the you know it's the second derivative matrix you have a convex function locally locally you have a hesian which is the PhD matrix right so you can say okay that's my local geometry of my domain so I just use directly that as my。

Penalty， so this looks very nice， unfortunately this is much harder to analyze。

 but this is what is called the Newton method。So the Newton method。New is essentially this。要。

You could say it's proximal gradient descent where the penalty is given by the function itself。

But there's another simpler way to say the whole thing。If I look at the first。一飞。😊，一。

If I look at these two terms together。That is the first two terms of the tailored series expansion of the function F。

It's the quadratic approximation of the function F。

RightBecause the first term was of course the linear approximation and then what I did was the second term also I picked the from the function itself。

 so I got the quadratic approximation to the function so minimizing that is the neutralton method so actually I think I got this little wrong here let me start let me write us x minus xt。

X minus 16。Sorry。So you know， it should be like the quadratic that I use there is x minus xt transpose hit sub f hits sub f for xt x minus xt。

Okay that's the。Penalty to use。So professor， should this be a factor of1 half？

Sorry or should there be a factor of one half the Oh yes。

 this should be a factor of1 half Yeah actually you know there's also I could also use an Eta here right like in our original yeah but this should be a factor of one half if you that will be the quadratic approximation to the function yeah so Newton method is is a factor of one half and have this。

But this turns out to we have very， very good convergence。

So the convergence of the Newton method is even faster than the。嗯。Strong convexity gradient descent。

 so the convergence is log log1 over epsilon， so to get epsilon accuracy。You just need log。

 log one over epsilon iterations。It's very nice， but you can only prove this convergence in us under it。

sufficiently nice neighborhood。If you started a sufficiently nice neighborhood。So it's yeah。

But you see that all of the algorithms sort of are kind of special cases of this broad phenomena。

 which is。You take the linear approximation and you add a penalty and you change the penalty。

 you get different things。Okay，I think I should stop here， any questions？I had one question。

 so is it possible to instead of using the quadratic approximation use the third order approximation？

呃So I think the。Right I haven't seen an algorithm that does that， but I think the real issue。

 I mean one real issue with that is if I give you a degree three function。

 it's difficult to optimize it。There's no easy way to optimize a degree3 function。

 in fact it' will become NP hard in general for a degree3 function， but for a quadratic function。

 you can essentially explicitly write down the optimum。The optimum of a quadratic。

 I mean that's how we prove the gradient descent rate and so on。

 you can by just you know differentiating setting the derivative to zero。

 you can basically explicitly write down the optimum for a quadratic function。

And that's the reason why you wouldn't usually you wouldn't use the cubic unless you know something about the cubic。

Anything else？So when you try to minimize a cubic， you get a system of quadratics， right， right。

 yeah， so that turned out to be NP hard Yeah， I think so it's difficult to minimize a cubic。

 Yeah if you have a system of quadratics it's difficult to do that。 Yeah。

 are there numerical methods for solving systems of quadratics。嗯。Not in general。

 like there's no like you know， all the algorithms that you're seeing are proable。

 there's no provable way to minimize aqubic。And you know it sort of makes sense right even when I say minimize a quadratic。

 we are actually implicitly making sure that our quadratic is a convex function because we are picking a PSD thing。

 so really at least like the sub problemsble in every step is still a convex minimization。

 but if I just use the first three terms then I get a cubic and it might be completely nonconvex cubic right the first three terms of a convex function need not be convex right。

Taylor series approximation， so it could have lots of local minima and we don't know actually the terrain can be at。

Crazy looking。I have a question that's somewhat unrelated to like our discussion of proximal gradient descent。

More regarding when you said there are issues with adding the gradient。

To your vector because it's a dual vector now like if I if I remember differential geometry correctly。

 then isn't it the inner product with the gradient if you view that as a linear functional that's the dual vector and not the gradient itself。

 why can't what's the issue with adding。你个 돼。Right so right so so when you write down gradient as a vector right so gradient okay gradient is a vector so okay at first at the most basic gradient is a linear functional that gives given a direction tells you the steepness that this is the type of a gradient but you can also express it as a vector itself。

 you can write down the gradient。Like the way you can， since it's a linear functional。

 you can also write it as a gradient of F of x in a product Y right this gradient of F ofx。

At y along Y is grain of effectsx in a broad way。Right， but。呃。

If you write down a linear functional as a vector， that vector lives in the dual space。

 meaning it's it's。You know its geometry is in the dual space。

 so I guess you know if you work with the Euclidean space。

Like geometry is the same L2 and L2 are dual or self dual of each other。

 but I think a good example is maybe if you work with L。Let's say you work with L1， right？

Okay in L1 here， then this will be L infinity what that means is if I look at the unit ball in the x space。

 the unit ball in the x space looks like this。This is an L1 unit ball in。

 let's say even in two dimensions， in two dimensions， the L1 unit ball looks like this。

The L infinity unit ball。Looks like this。So the geometry of x。

 this is where like this is the geometry of x， and this is the geometry for the gradient vector。

Like that's the natural geometry for the gradientor， right。嗯。So like the gradient vector。

 its normalization is like。Alex。LikeThe distance for the its normalization is in the dual norm。嗯。就。

I guess I'm wondering then why the dual space naturally inherits the dual normob because it's。

The dual space in itself。You can put whatever inner a product you want on it right So right。

 why does it naturally inherit the dual alone well， you know the like。

Even before right so even before you draw a picture to the picture that you associate with the dual space。

 the dual space， if you just define it formally as the object that takes a vector。

And outputs a real number。As a linear functional， sorry。

 if you define the great dual space as a linear functional。Right。

 the natural norm on the linear functional is to say。The norm of a linear functional。

Let's say it's in the dual space， so is。嗯。The norm is。You take a unit vector。In your original space。

 let me call it。It's a unit vector and you ask what is the value that your linear functional？

Outputs on this vector。Okay， so this is a natural norm that you can define。

On the right a norm of a function right the norm of a function functional norm of a functional is the largest value it outputs on a given point inside the unit ball right the largest value takes inside input this is a natural norm I can define on the dual space of any function space even without explicitly thinking of the dual space as a vector even if I think of it as just a function。

 this is a natural norm there and you see that this norm。Becomes the。Dual known。

 like if you right to write this as an inner product。Like if I replace this by， okay。

 there's a vector that I associate with this。If I write this。Then this becomes the LQ normal vector。

That one all people is on all case one。Okay， okay， yeah， that makes sense。

 So you're looking at the operatorome of the gradient。Right， right， okay。Yeah。Thank you。 Yeah。

 so yeah。Yeah， basically the natural geometry in the dual space is the2 no。I。

And actually these things become， I mean， for us we always in finite dimensional spaces。

 so things like okay， whatever right beek norm you norm itself。

Usually you sort of push this under the rug， but。When you。

 I think if you work on real function spaces， there can be functions which have a finite LQ norm。

Right， but they may not even have a bounded LP norm， right like。嗯。Right， see very and like， you know。

Like the norm this could be infinity in right？So right， all right， so yeah。

 these things become more important。Yeah， I mean also all algorithms， dimension， sorry。

 gradient algorithms they use。They are dimension independent as we talked about earlier。

 so I'm sure there are applications of gradient descent。

Which are completely infinite dimensional and I'm sure that they're somewhere if you。Find one yeah。

 let me know。And I was looking for a nice application， which is completely infinite dimension。

 which uses the fact that the analysis is actually independent of the dimension。嗯。Yeah。

 I couldn't explicitly find one。嗯。YeahYeah。It did。Okay。All right， yeah。

 thanks see you on Wednesday we'll finish the proof of mirror disscent and we'll go to online optimization。

Thank you。是。

![](img/bdf811107d5ae55e5281bcd04a800b3b_12.png)