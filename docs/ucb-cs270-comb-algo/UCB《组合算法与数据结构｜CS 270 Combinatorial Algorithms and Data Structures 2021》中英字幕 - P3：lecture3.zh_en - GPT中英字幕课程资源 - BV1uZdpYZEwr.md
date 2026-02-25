# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P3：lecture3.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

Read for homework one homework one was a little bit more tricky because the scribe notes were coming in as the homework was due I think will be better off next homework convert and in terms of scribe notes actually I'm using Piazza for all of the communication almost all of it so I'm posting scribe notes。

 lecture links， everything on Piazza so。You can find the scribe notes on Piazza， thanks to the group。

 there's a very great nice scribe notes for last lecture from last Monday。

 which quite nicely describes Midessent。Yeah， so。Its good。

Basically data structure where it's first in first out。 So you can。you， and then I will be the next。

唔使。And。All right， okay， so let's。Let's start okay， so today the plan would be the following so。

So right now， when we are fresh， I want to do like a proof or a proof sketch of mirror descent。

Just to remind you， and then we will see how general this framework is of mirrordesscent and gradient descent and to see how we can apply to online convex optimization。

And in particular， we'll see how we can use it to solve linear programs。Okay。

 so let's start right away。 So just to fresh fresh your memory so。Mirror descent is this algorithm。

 so the starting point for mirror descent is you start with a strongly convex function。Hch。

So for example， yourx strongly convex function could just be H of x is equal to norm of x whole squared。

There would be the to Nopsquad or any other strongly convex function。

And a strong economicx function is one that satisfies the following property that。按。

H of y is greater than the linear approximation at point X。By a fact， by a significant amount。

Which is。This quadratic。And so that's a strongly convex function it's never flat。

 it's always bending upwards and if you give me any strongly convex function hedge。

 I can define something called the brgman divergence。

So fragmentman divergence is sort of like a distance， but it's a asymmetric quantity。And。

Distance of y from x， D of y from x。This an asymmetric quantity is given by。

H of y minus the linear approximation atx。You know for me。

 the seeing this picture is what really helped me。Learn this definition and I think I'll never forget this definition because of this picture the picture is just you have this function at x you can draw a linear approximation to the function at x and then hit the pregnantg divergence is how far above the linear approximation the point y is okay so that's br divergence and as you can see as you go away from x it keeps increasing and it gives you like a penalty function or moving away from x okay so now that we have the brg divergence。

We can define mirror descent。Vredesscent is essentially the following algorithm。So。

If you're at a point， Xt。If you're at a point text T。

Then you have a linear approximation to the function at that point。Which is this。

F of xt plus the gradient， so that's your linear approximation to the function F at that point。

And then。You want to minimize that linear approximation。

With an additional penalty which prevents you from going too far away and the penalty is given by the divergence。

 the brgman divergence from x。you find a new point yt plus1。

By minimizing this linear approximation plus the divergence。And。We end up at a point。Y d plus one。

Which could potentially be outside your region of interest。

 so imagine if you're trying to solve minimize F ofx。X is in a convex set K。

 so this is a convex set K I've drawn here。And your Y plus could go outside。Okay。

So that's the one way to write down what Yt plus1 is。But， you know。We can simplify this a little bit。

And let's see。So in order to simplify this， well I have to what do I need to do I need to minimize this function on the right hand side or all y so I just you compute the derivative and set it to zero。

 so Ill compute the derivative so with respect to y and set it to zero。So what do I get？I'll get。

If you put in an eater here。Let me put an Eta times the function plus the device。

 So you get Eta times。The gradient of F of xt。Gs。Gradient of h of y。Minus the gradient of。

Hdge of X D。So以。Rianient at Hs of xt。This is zero。 So I get this by just use， you know。

Taking the function。Which is。Which I need to minimize。

And differentiating it with respect to y and setting the derivative to0。

 I get this identity here I have used the expansion for d recall that D is given by this function d of y from x is h of y minus h of x plus gradient h of x times y minus x。

So I just use that equation expression for D， and then I get this and simplifying this further。

But clearly， why is a point such that the following courses？

Graadient of H of y is actually gradient of H of xt。Mus Eta。Graient F of X T。And that's what y is。So。

 if I had to。Write down what Y T is or do there。So， if。I would say white is actually。Somehow。

 if I take this gradient function。I invertted。So this is expression。four。😔，Y or y yt plus1。诶。Yes。

 on the chat I see a couple of questions let me see。Okay， so let me just remind。

Remind people what the role of H is。H is in a strongly convex function， which acts like our。

A replacementplacement for distance。Some of h you can think of H has just the2 norm。

 then you'll recover the usual gradient descent and for different choice of H you'll recover different versions of gradient descent and so pick any strongly convex function so in your mind you can pick h ofx to be the two norm and then you get a version of the penalty which is the pregnantg divergence penalty for moving away from x。

And you add that penalty and you write the stuff。So what you have here is。

Something like the following I mean this we can interpret this expression that we have as follows。

Well， we have a domain， I'm calling the domain omega。

This is the domain on which h is defined the convex function H is defined okay for simplicity。

 you can assume that this domain is just all of r to the n。And。Given any point。

You can compute the gradient。So there's a gradient map。Graient of edge map that given any point。Z。

Returns， gradient， HFC C。Okay， and as we discussed it last time。

 really gradients should be thought of as living in the dual space because their linear functional really not vectors。

So this is a dual space or the space of linear functional。

So gradient of fetch gives you a map to the dual space。Okay， and then gradient of h inverse。

 assuming there's an inverse which is nicely defined。Well give you a map back。There's a。

Space of the on which you won' to optimize and then there's a dual space and its gradient in effects lets you go from one to another and back。

And what mirrordesscent seems to do is。嗯。Seems to do the following。It。First， maps， X D。

To gradient H of Xt。Okay， that's。Here。And then you。

You can add your gradient just like you in gradient decent。

 you added the gradient to your function here before adding the gradient you map via a gradient H。

 then you add your gradient step。What is that Well it was always minus Eta times the gradient。

F of XD。Okay， that's the。Thing that you added。And you end up at。诶。A new point。And you map it back。

We are great and in verse。You end up at Yp+1。So that's what this equation is saying。Okay。Right。

And so that。And then you know， we're still not done because if you're solving constrained optimization。

 we want our next ti rate to also be inside the convex set K。Okay， and in order to do that。

 you want to project yt plus one back to。Next the sec。You want to say that xt plus1。

 your next itt rate is a projection of Yt plus1。And it seems natural， I。

That you would want to use this。Distance you defined right now， this D function。

 the pregnant divergence as a way to project because。You know so far the algorithm is using D。

 so we as well use D for this step also， so the projection is the following step you say。

X T plus one。Is。The point inside your set that you care about， which has the smallest diveer jets。

From Yt plus one。Good。So that。So these two together give you one step of mirror descent。

 so really mirror descent， if you want to visualize it via the gradient He map， it takes Xt。

 maps it to the dual space via the gradient He map。And then you add the gradient。

You map it back and then you finally project。On to Xt plus one。Okay。

 so that's the whole one step of the iteration and you repeat this。ok。Any questions on this？

see if have any questions。Please unmute yourself ask me questions if you have。All right。

Professor yes， I had a quick question， so how do we know in what situations we can use different divergences？

What's how to pick the divergence you're asking how to pick the divergence in a given situation Yeah as in like the intuition behind one to use different divergences in different situations。

Right。Yeah。系。Yeah， I think it's。Yeah I don't have a very good answer to that you know there are of course a few standard examples like the multiplicative weights or the grade usual gradient descent or matrix multiplicative weights and often these suffice you know。

But。嗯。If you。Like if you want to pick a very different very unique it area very unique divergence it's I don't have a good answer as to how you would come up with that it's sort of a little bit of。

You know。Guesswork， right。Yeah。But you know， most of the time you typically use the standard ones。

 the standard ones being if you use KL divergence， then you'll end up with a multiplicative weight algorithm。

 if you use a two norm， you end up with the gradient descent。

 there are very few occasions where I've seen people have used different completely different divergences。

AndYeah。嗯。是。Yeah。Okay so I also have a question， you refer to the inverse of the gradient of H and I was wondering if that was viable because of the strong convexity of H right。

 no it's not purely because of strong convexity， I think you just have to I mean in this we're in a setup where we' are assuming that the gradient is invertebible。

 this gradient map is invertebible。It's not immediate in by any sense， yeah。Yeah。

 that's a good question。Yeah， it's more of a framework this is more of a framework where many things fit together and it's sort of。

Gives you。A framework in which you can add or change things and sort of it in my mind is like the sort of the almost the most general framework in which you can talk about gradient descent。

Okay， so that's good all right so that's the lets to recall Miradesscent now I think I'll try to do a very quick proof of mirrordiscent I'll try to skip steps and try to show you just the important steps。

And let's see how quickly we can get through this all right。

 so here's the theorem the theorem is if if you have a strongly convex h the function you define the divergence with and let's assume for now that your gradient function is actually a bijection from the set omega to R to be and so it's invertible and so on let's assume that the gradient of f ofx is always at most L its lip shifts continuous in that sense。

Then this is the claim， so it looks very similar to the gradient decentcent claim that we had earlier。

Like the very first grade and decent claim that we proved。Except that。You see that。

Like the diameter is replaced by the divergence。

![](img/08d769afc7e7ddb036446cfb205ca55e_1.png)

Something happened to me。

![](img/08d769afc7e7ddb036446cfb205ca55e_3.png)

Okay。Allright， so。对。So first okay， and the claim is very very very similar to the gradient decentcent okay let's see it moves very much like the gradient decentcent proof that we saw last class。

 so first you write down。F of x minus F of x star， if x star is the optimal is at most。The gradient。

F of excess。In a product with excess minus X star。This is， of course， just definition of convexity。

Applied to X and X where X is the optim。This is for all us in any step S the following words。

And then as we did last class with the gradient descent。

 you again replace the gradient by the expression that we had for the gradient in terms of the step。

 so I'm going to write it as one overeaer。Graient hedge of。Excess minus。Gient hits of X plus1。

In the product S minus X star。ok。So this is。Where do we get this， well， we get it from here。

By the definition of。嗯。Okay。Sorry， I should sorry I should be careful。Okay。RightSo that this is just。

Okay， so then like if you recall in the last two last time in the proof of gradient descent。

 this time at this point we applied something called the law of cosine， right？

Essentially the same thing you do here。But now instead of the law of cosine。

 where we have two norms you have divergences， so this is an identity。Which is the。

Let me write this identity， this quantity is equal to。Okay， so sorry， let me just write this clearly。

Yeah。

![](img/08d769afc7e7ddb036446cfb205ca55e_5.png)

So this is the analog of。The law of cosines， which was here。



![](img/08d769afc7e7ddb036446cfb205ca55e_7.png)

In the world of divergences。

![](img/08d769afc7e7ddb036446cfb205ca55e_9.png)

And how do you prove this。

![](img/08d769afc7e7ddb036446cfb205ca55e_11.png)

It's just an identity if you just write down what expand out what d is in terms of H。

 you'll see that these sort just equal equal this quantity。

These two quantities are equal just by expanding out the definition。



![](img/08d769afc7e7ddb036446cfb205ca55e_13.png)

肉是。Soれ。I't know what happened here。

![](img/08d769afc7e7ddb036446cfb205ca55e_15.png)

Okay。All right， so that's good。Okay that's the law of cosine。And then。Okay， so then。Well。

 when we did projected gradient in decent， we had to deal with this issue that we have here is that。

We have this projection operation in the algorithm where you take yt plus1 and you project it onto xt plus1。

and we need to sort of understand what that does to the distance to the set and in the usual L2 norm。

 we had a very simple statement that whenever you project you reduce the distance to your optimum。

Whenever you project。Okay， but。Here you don you don't have that very simple claim。

 but you have a slightly more complicated claim， but it's still。Nice。

 so it's the following claim So if you have a convex set K。Okay。

 and if you have a point to why outside？ and then if you point x here。All right， and you project why。

So let me call this pi of y is the projection of y what is pi of y pi of y is the point inside the set。

That minimizes the distance to y。The dives to why。Now you can ask。

 what can we say about these three divergences？诶。Like as I drawn， you can see， I mean。

 the thing that you want to say is that。This triangle behaves like an obtuse angle triangle。

So the distance。From x to y。Should be at least。The distance from。Fre of flight to。你。

Let be write this way。Distance from x to pi of y。Plus， the distance from pi of y to y。Again。

 an uptuse angle triangle， if you take an uptuse angle triangle。This is y， this is pi y， this is x。

You would have that if the。Lens of the sides are ABC， C squared is at least a squared plus b squared。

对。So the following statement is true， so for all X Y。If you pick any X inside the set。

And then you pick any y or the domain。And if you look at the projection。In terms of the divergences。

 y pi of y and x， they form like an obt angle triangle， meaning they satisfy this identity。

Kates called I guess the Pythagorean thing。So we will use that right now。So we'll use that。

To talk about this distance。professor。Yes， the last term looks like like in the last term in the like Lo Co application can go back to on the page looks like it's the same as the term before。

 Like they both look like it's D of X Y plus one oh sorry X should sorry thanks， Yeah。

 this should be Xt。Does it make sense yeah？I mean， this is quite similar to the distance to optimum that we had。

In the gradient decentcent world。对。So what you do now is you replace this D extra y plus1。

You apply this py and equality。And。嗯。对。He write one over Eta。D of。Extra。Exess。Plus， D of excess。

Y plus1。 So these are the first two terms here。And for the last term。

 I'm going to apply the Pythagoreian inequality to say that that is at most。D of。嗯。Ex star。

Xt plus one。Plus D of X T。 So x S plus1。X S plus1。Y is plus1。跟。

Because remember that access+ one is a projectal YS plus one， so it's just precisely this identity。

The边害。This inequality。If I replace that， I would get this less than equal to signine。Okay， so that's。

Okay， so we use the Pythagorean identity。I won't be proving that I test。So。So here。

 if you look at this expression， let me write on what's on the left hand side of this inequality。

 we are saying that f of x minus f of x star。Is at most this quantity。Now。

 if I take this inequality and add over all values of S。Just like in the proof of gradient descent。

The first two terms here， the terms that I'm marking in yellow。

 they telescopic each each other and they cancel out。They have they look like。

A1 minus a2 plus a2 minus a3 plus a3 minus a4 and so on so they cancel out and you're left with just the first in the last term。

 so that's kind of nice if I add it up or all S I do end up with something like，So you know。

 F of x as minus F of x star。I end up with something like one over eater。D。X star x1。

 like the first step minus d of x star。Last step， that is X plus one。So so far， that's a nice。

 just a upward distance。嗯。And then these。These terms here， these two terms。

They keep adding up and you need to bound them。And。

Let me just write down what bound you can prove for them。嗯。D of x， Y S plus1 minus D of x plus1。

Y is plus one？Okay well I mean how do you balance such a quantity I mean all you do is you just write down the definition of D right if you just write down the definition of D and you know expand out and simplify you'll。

要领得别啊。The following bound， I'm going to skip a couple of steps here and I'm just going to show you。

The bound here。Okay， so you end up with a bound like this。And。Right， so。And。

 if since you know a bound on the gradient of F， you can essentially bound this by Eta L whole squared by2 rule。

Okay， so that's so。So， okay， so so that's。I mean。嗯。I sort of skipped a few steps here。

 but I still wanted to show you。Just this much of the proof because。It sort of shows all the。

Things that well be using about this divergence。So what are the things that we needed for the first divergence well firstly we needed the law of cosines which was an identity which is easy like immediately follows then we needed this Pythagore en triplet formula which I mean all of these the Pythag enplay is of course this same is of course proof for norm x squared but there's a very short proof or it also holds for any strongly convex div function if you construct a divergence or any strongly convex function it get like this Python identity it's like a short proof。

And then， the third。Fact that we need it is here in this。When I write down this difference。

 point wise difference。I can up down the point twice difference using the gradient of F factor。Oh。

Okay， but all right， so so if you put all these together， you'll recover the proof of this year。

 It's only a page in Bubeck's book。 I point to the thing it's just as one page of。Listen。

 about a page of fancy branded book。I leave it there。Okay， so that's good， that's what we have。

So this is a it turns out this particular schema is actually very general。

We already saw that it gives you gradient descent and multiative multiplulative weight actually let me。

Add that as a thing to do if you I'm assuming that a lot of you have seen multiplicative weight。

 but if you haven't I would advise strongly again towards doing this。Pick h of x to be。

The entropy function。It's a strongly convex function。And compute the divergence。

It'll turn out to be the KL divergence。And work through all of the steps here。

Meaning all of these work through this。This computation。To recover multiplicative weight update。

method。几。そ。Allright， so okay， so let。Let me make one remark about this。屠父。So。

Like when we define strong convexity。We did something a little bit strange。

 we wanted to move away from the two norm。Right we wanted to go into different geometries and move away from the two norm。

 but I ended up putting in。A two norm in the definition of strong convexity here。

I said put at least this too norm。And。That's a little bit odd。But actually it's not necessary。

 you can put in any norm there。So。If I replace in the definition of strong convexity。

 this norm usually means the two norm， but imagine it is some other norm。

 let's say the P norm or the infinity norm or the one norm， any other norm。

Let's say you have a function H which is strongly convex with respect to some norm。

Then you can still of course， define pregnant divergence。Can define very decentent algorithm。

 nothing changes。And actually the analysis also goes through。Except at one place。Here。

Except at this place。嗯。I use the Kahi Schwartz inequality to say that the inner product between the gradient and excess minus x plus one is at most the product of the norms。

But you know， if I'm using a different norm， all I need to do is to use。A dual norm for F。And。

So if I have some， let say some norm。P， let me call it a p norm。 I'm using a p norm for for x's。

 and need use the duall of that p norm for the F。Okay， so in terms of the theorem statement。

The following more general fact is true。F take any strongly convex function。

 which is strongly convex with respect to。心郎啲。ok。😊。

And then the gradients are bounded in the dual norm。

The same proof goes through and everything is fine。And。Any questions so far？

So basically I think I mean the reason to show you this very general thing is to show you this very general machine with all the different knobs in there。

 well there's the knob of picking the divergence and then there's the knob of picking the right knob for your space and if your edge is strongly convex with respect to that。

 then everything goes through。Okay。And in fact， to derive the usual bounds for multiplicative weights。

 you will need to use scale divergence。You need to use that the entropy is strongly convex。

With respect to the one no。你婚龙。So these together give you multiplicative weight。

So I would actually be good access to work this sort if you know。You can check your。

Capulations back with， I think wishish Nois book and Bubeck's book both have this worked。

 so it's a good exercise。All right， so let me move to the next。

Thing I want to say about Korean descent。嗯。Okay， so this is like a fairly intricate machine that we have with。

 but it is just one theorem， this is just one theorem and it'll give you lots of different things。

So here's what I want to talk about next， it's the online convex optimization。

Which is somewhat familiar from the world of multiplicative weight。

So what is online convex optimization？几。So what is the online current optimization problem here？

You have， you have。And algorithm give them。Which。啊， at大 B。You know， you can say that it plays。X0。

In some convex said K。At each time you're playing some convexite K。And then you have。

 let me call this the adversary of the environment。嗯。Adversary or。The cost function， the cost。

At each point in time， a new cost function， F sub P。It chosen is given to you。

It's a convex cost function。Okay， and you incur。A cost which is F sub T of x。Sty。

This is a cost that we incurred。Or the algorithm iners in drown tea。Okay。So。You play Xt。

 there a course a new convex function F sub is revealed to you and you in a course which is F subt of xceptt。

And imagine your。Youre a convex set K and you are constantly playing some point in the convex set。

And after。Capital T steps。You want to know how well。You are at minimizing the total cost incurred。

And the way we measure ourselves is in terms of regret。Sos a regret。After capital T steps。

Is the following quantity。You look at the total cost， the algorithm incurred。嗯。

In all the rounds and then。You compare yourself。With the best single choice that you could have made for all the rounds put together。

Meaning， if you。In hindsight， if you knew all the cost functions at priorityi。Okay。

 and you picked a single point against all the cost functions。You picked a single point x star。

Against all the cost functions。 and you don't move at all for all the key steps you don't move at all。

 you'll incur some cost。And the regret is the difference between these two quantities。

It's your regret for not playing this particular X throughout the algorithm。Throughout the T steps。

But you get to pick this， this is in hindsight。As in you get to pick this x star after you look at all theF13ft。

 it's the minimum of x belonging to k of s equal to 13 T f sub S of x。That is。

 this quantity is called regret and you for convenience， we also define average regret。

when I say average regret， I just mean the average regret per round， so I just divide by T。

Does the definition make sense？Any questions about the definition？No yeah。 I have one question。

So does the adversary like choose the function based on what you've played in the past or does it just？

Just to choose the function independently what you play every single time step right so the adversary can play can choose any function independently he can even choose the function depending on Xt。

Can choose any function， basically， this is the worst case。Any function。

So it can depend on what it could depend on XT could depend on XT。Yeah。

 good question actually that goes to what I wanted to ask next。嗯。

Any other questions I have a follow up like why does it make sense to compare it against like an offline if like you know。

 like maybe the functions FS would be different if you had chosen like the X star。Yeah。诶。Right。

 so why does it make sense to compare against this？诶。Yeah， I mean it。

It really depends on the setting。I mean in many settings you're right。

 the regret as actually makes less sense， in particular you're tying yourself to not moving across different rounds。

On one hand， you' try tying yourself to not moving across different rounds， on the other hand。

Your actions can change what the doary does。 So yeah， so it。Yeah。

 it turns out to be quite a useful notion。in many settings。

 but the way we'll use it in this class it'll be sort of clear that it's useful as in we'll use this notions of regret to do something else。

 but yeah you're right you know in a real online convex optimization world when you're dealing with this。

Yeah， you would wonder why this would be a reasonable notion。Like in many settings。

 it won't be a reasonable motion。Sorry， just to clarify the cost of choosing one particular x is a saved no matter when you choose it。

No， the cost of right the cost is given by this F sub t of xt， so in round t， if we are playing Xt。

 then the cost function is F subt so our cost is F subt of xt。So in every round。

 you have a different cost function。嗯。Professor， so just to clarify， regret can be negative， right？

Regret can be negative。 Yes， regret can be negative because okay。

We are allowing ourselves to move our point whereas。The offline optimum is not allowed to move。Yes。

Okay， so okay， so why do we mention this regret？Wedy。

Point is we don't have to do any additional work。Essentially the same gradient descent and mirror descent algorithms give you the same bounds。

And。What do we need to change， we just need to add indices。嗯。Under all of our equations。

 so at time T， of course， we should use F sub T。They and just。

Writing down how the algorithms description changes well at time T use F sub T instead of F。

 you use F subt at time T。And。Essentially everything stays the same。And if you look at the proof。

Okay， if I。Take the proof and wherever I see an f of x sub S， if I write f sub s of x sub S。

Everything stays the same。The proof is essentially the same。So I have two questions about this。

So we have。Like we have like an oracle access to the function is that or sorry the gradient？

There's not the gradient depth service。Yeah， yeah， yeah， let's say we have orlas or even。Yeah。

 it depends on the setting， but yeah， for now， let's say we can compute gradient of service。Yeah。

 okay， and then second question is。Why does the gradient of the current function tell you about the next function？

Okay， so that's good Okay so first I want to show you the theorem the theorem is just that I mean the thing I wanted to show you first was that okay look if we did this proof of the theorem if I just replace every ver I see F I make it F sub S the whole proof goes through and you get this bound so you have a bound on the regret okay yeah so that you know brings me to the next question which I want to throw it at you and you guys are asking me already So it's this sort of a little bit of a paradoxicical situation which many of you have already seen this is a following paradoxical situation。

嗯。So we okay firstly the gradient decent algorithm gives you good regret bound。

 it gives you a regret bound which is order one over root T right gives you some in particular the average regret goes to zero okay that's good。

But if you look at gradient in descent or all of them。Your next point except t plus1。

Is essentially a function。Of the past。Of the past， as in it's a function of the things that you've seen so far。

 F1 through FT and the things that you've played so far， x1 through xt。Okay。

 your action is a function of the past。But your reward。Your reward or your cost。

Which is F sub t plus1 has nothing to do with the past， is independent or the past。as you see。

This should be this should mean that you can't get any bound right this should be a useless algorithm you're using the past to move。

But there is no guarantee whatsoever that your future will depend on the past， like in any way。

 F sub plus one is completely independent of the past， in fact， even worse。

I'm allowing F sub t+1 to be chosen after you fix X sub t+1。After you fix except t plus one。

The adversary will look at what he shows and then he will pick F sub2+ one。Okay。

 even then the proofs go through and you get the reward， get you get that average regret。

Scacales like order one over rootee。So meaning it goes to zero as t goes in。

So that's the nice little bit of paradoxical situation here and this is not just true here and it's also true even in the good or if if you look at multiplicative weight you have the same situation。

嗯。So why is this happening？嗯。So I actually， let me tell you why what's going on， I mean。

 one way to think of what's going on。Is the following。就。So let's think of the following situation。

It is quite analogous to where we are。Imagine this's like。You know。

Is like a road or a there's a stretch of road。Okay， and you can stand anywhere。

And wherever you're standing。嗯。The。This is where you stand and the adversary can bomb。Obviously。

 he can bomb and cause damage， but he can bomb。嗯。And this is the kind of damage he can inflict。

So this is F sub I。This is the kind of damage he can inflict wherever you're standing on this road。

 okay， and so you decide to move somewhere else。And the adversary can see where you mo and he can inflict another damage。

Good on。And you is keep playing this game。Okay， so then you know。

 what you're comparing yourself is you're comparing yourself against a single place。

 a single place where you could be standing at the。From the beginning till the end。

If you knew where the address is going to bomb。But at each time step。

 the adversary really sees where you are and he bombs so that itflicts you， maximum damage on you。

The only constraint on the adversary is he can only bomb in convex functions that his bombing should be like convex function。

So why do you end up？Having low regret here。Well， the idea is basically that。And then you you know。

 adversary follows you and tries to inflict as much damage on John as possible each time。

But in the process。He inflicts destruction on the entire set。Meaning there's no regret。

That's what's happening， so somehow in what's happening is in his effort to hurt you。

 he ends up hurting every other point in the set。And also the optimal point。

So that's what these theems are saying， these theems are saying that。嗯。Effectively。

In an effort to inflict damage on you， he infts damage on every point in the set in particular on any other optimum point you could have chosen。

And you see that that's clearly got to do with the shape of the functions。

 I'm allowing the adversary to only use convex destruction and that's why you know intuitivetuly you can see that like at least on this line you can see that you know if he tries to inflict damage。

 he'll end up damaging everyone。U。On the other hand， if I allowed for concave functions or different。

 let's do concave functions。So then for concave functions， the adversary can inflict damage。

 which looks like a peak， he can do this。hoops。It can inflict damage that looks like this。

If I of concave cost functions。And then of course， there's no way to win against such an adversary because wherever you're standing。

 he's going to inflict damage right there and nowhere else。Right， and that's the reason why。

You don't like this you know it seems like a paradox where it is not all it is saying is that if you if the algorithm is bad then every other point is bad as opposed to saying the algorithm is doing well。

 it never said the algorithm does well， it just said that if the algorithm is doing badly。

 every other point is doing bad。And yeah， so that's the thing。 And and this but so。

So this online convex optimization， this bound， it holds not just for mirror descent。

 if you go back to a proof of like the very first proof we did in the class， for gradient descent。

 if you take all the F's and replace them by F sub S。

The whole proof goes through and even the most naive or simplest version of gradient descent has the same advantages and properties like it has this one order one over T。

嗯理解。Professor， yes。So if we compare so to a strategy that each point picks a different point that minimizes like the cost for that particular cost function。

Are there no guarantees on the regret then， So you're saying at each time you minimum you。

You minimize F subt。Yeah well that we don't well you don't know F subT when you choose x sub t right so the way the setup is that you pick x sub T and then you see F subt。

He's talking about the regret function。啊。Oh， at each point， you minimize。Right。

 so I guess that's a good question So you're asking at each time you minimize。Your new point。

Is actually the minimum overall points。Up to now。Of the cost。

You I was talking about like so in the formula for a regret like you're subtracting the performance of a strategy that that's like staying at one fixed point right so that's where you're comparing it to But what if you compare it instead to like the best possible strategy that each time step picks the point that minimizes the cost for that like for that time T So like I guess you just interchange the you put the min inside sum right right Yeah then there is no bound as in the average the grid doesn't go to zero。

Then allow， if you compare yourself against an optimber can move in every step。

 then there is no bound and that you can get。Because it would dodge。

 I mean it it would each time each time step like the adversary will pick a function that is worse for you at that step and because adversary picks F after you pick XI so there's really no bound if you allow a yourself to move。

系呀。嗯。Yeah。就。Okay， so this is a neat thing。I mean， this is just the beginning of online algorithms and there's a lot more I can do with this。

But let me show you an application of this which is already quite neat。

So the application that I want to show you is。Gradient descent。Sorry， not great linear programming。

 solving linear programming where gradient in descent。So solving。LB union programs。

So let me write down a particular form of linear program。So here's a form。

 let's just say you have x1 through xn。Variables which are in some bounded range minus。B2 B。

 some fixed boundary range。And then let's say you have constraints on these variables which look like linear functions right。

 so li of x is WI。In a product X minus B。Is。Less than I equal to 0。4。I equal21 through M。Okay。

 so you have a linear programming system like this。Okay， so you have a linear your program， you know。

 and then how do you find a point which is feasible？So goal is find x that is feasible。

As in itselfs all the constraints。叫。So note that usually in linear programs。

 you have an optimization problem where you minimize or maximize something some other linear function。

 but it's easy to reduce。Optimization to feasibility if you can solve linear programs like this。

 you can also solve optimization by adding the optimum itself。

As another constraint to your system so you do a binary research on the value of the optimum you say you know C X is at least theta you add that as a constraint and you see if it's feasible and you sort of do binary search and you can recover that so basically solving feasibility following your programs is basically the whole game if you can solve feasibility you can solve optimization。

All right， so how do we use online convex optimization or even online gradient descent to solve this？

Okay， so here's what we'll do。嗯。So we'll use our box。

Let's say this is the online convex optimization algorithm。就。

It could just be gradient descent or mirror descent on any of them。

And let's say at every point it gives you at every point in every iteration， it gives you some。诶。

Candidate solution， acceptee。This is a candidate solution to the LP。Okay。

And then our algorithm will actually。Pick this convex cost function。Okay。

 so our algorithm will also implement the adversary。Here's the adversity。So what does adversary do？

Well， big。A constraint。That is violated。By acceptee。系。

Let's say some constraint x is violated by except t。

 let's say L pi of x sub t is less than is greater than。Let's say it's greater than。Epsilon。

It's violated by at least a little bit， it's violated by at least steps long。Okay， and then you you。

Send that violated constraint or the linear function associated with the violated constraint。As your。

Cost you he。The cost function F sub T is just this violated constraint El subbi。

And the online algorithm will return a new point X of T。

 and then you give it a new cost function and you repeat this。So your algorithm like the。

Algorithm that you have for solving linear programs is running both the adversary and the online gradient descent。

This is the algorithm to solve LP。It's。It has sort of two players in some sense one is this online conve optimization it gives a candidate solution and the adversary who just picks a violated constraint and。

A constrain is violated by least stepylum and returns it and if at any point in time the adversary can't pick a violated constraint。

Then that means that acceptee satisfies all the constraints by within an epsilon and you can return accepting right。

Adversary fails。As in。No constraint violated by epsilon。You just return the current height rate。

Return current accept。Okay， that clearly satisfies all the constraints within epsilon error。Okay。

 so that's the center。Okay， so why does this work？

![](img/08d769afc7e7ddb036446cfb205ca55e_17.png)

Well。Here's the reason why it works。嗯。

![](img/08d769afc7e7ddb036446cfb205ca55e_19.png)

Exose。There exists a point X star in the convex set。Like in this convex set。

 suppose it's a convict point。That satisfies all the constraints。All the constraints。

Sose that exists appointed such as all the constraints。连。

What would the cost incurred by such a point be Well the cost incurred by such a point is just。

You know， F sub I。好犀你死。The total cost incurred by such a point would be f sub S of x star。Right。And。

 you know， each time the。嗯。The cost function is just the constraint itself， right。

So at each point in time， remember that the adversary is just picking a linear linear function from the system of constraints and returning it right so let me call that。

As a I sub S。RightOf X star。OkayEach point in time。

 that's what the address is doing and so since X satisfies all the constraints。

All of these linear functions are linear costs are less than zero because it satisfies all the constraints。

So each of these costs are less than zero。A number that's less than zero。

So this whole entire cost of。Of this single point， x would be less than zero。Okay。On the other hand。

If the algorithm runs for T steps。Like if this interaction between online convex optimization and the adversary runs for T steps。

If adversary OCO right runs for T steps。Okay， in each step。

The OCO online convex optimization algorithm incurred a cost of at least epsylum。

 right because at each step。basicallyically the adversary picked a violated constraint and sort of inflicted that as a penalty。

 right。Transfer two steps in each step， the cost is at least stepil。

 so if I look at sum f sub S of x sub S。S equal to one through T， this is at least some over。

This is Epsil。So you see that the regret。The difference between these two。

The regret seems to be growing linearly。系。This can't happen this would mean that the average regret。

Is like epsilon。This can't happen for too long because we know that the regret goes to zero as t goes to infinity。

So what that means is。This interaction between the adversary and online connect optimization cannot go on for too long。

 it will the adversary will fail soon and return accept。As a solution。

But the solution won't be exact， of course， it will satisfy all the constraints with an epsilon error。

Sa very constant theipl。And it's a very simple algorithm note that this online conve optimization music。

 you don't even have to do any mirror descent or anything。

 mean if you do mirror disscent you might get better bounds or something。

 but you can just use the gradient descent thing that we meant like we did last time。

Just a good old gradient descent and have algorithm to solve LP， so that's a good thing。

What's the catch？The catch is really that the runtime is Pauline epsilon or one over epsilon。

At the runtime of this algorithm is polynomial in1 over epsilon。

 so it's pseudo polynomial in a sense。The sense that if you want a solution。With B bits of precision。

To take time， which is。2 to the order B。Exponentially the number of bigs are Pacific。

which is fine when many applications it's fine to have this sort of dependence in the precision。

 but apart from that this is a good in aal。To solve the new programs。Any questions Senator this？Well。

 is it acceptable if all the constraints are satisfied up to Epsilon error？In a real application。

It really depends on how youre using what you're using the LP for， right。Like。In many cases。

Eventually。对。嗯。LikeEventually。There are errors that are there in every aspect of real LP， right。

 sometimes you don't know the。Like let's say you're optimizing for。

Like let's say you wrote linear a program to solve some supply chain thing right you know you don't know the costs of things involved or you know all the constraints that you write down the numbers that themselves have some bits of precision right so you don't really need exact LP solutions in most applications and in fact。

It's sort of an accident that you can get exact L solutions。meaning啊。Actually。

 you should think about it why is it I think you can figure out why it is in exercise Why is it that。

Exact LP solutions can be expressed in finite number of bits of precision。

Meaning if I give you a linear program where all the coefficients are。

Integers with Bbits of precision。Then you can write actually write down the solution in some。

Pnomial in B bits of precision。This is not generally true for all possible convex functions。

 like imagine even if you're minimizing a quadratic。

Or solving semi different programs or something else。There's some precision involved always。

 right because the optimum may not even be rational numbers， meaning。To write it down exactly。

 it might take infinitely in many bits if it's an irrational number like square of two。Right， so。

So theres always precision in all of them and the question really boils down to in your application at hand how much precision you need。

But the gold is standard for precision。Or the thing that you shoot for always is to have a runtime。

 which is poly law is really log of one over epsilon。

You need to having a runtime of log one or epsilon， this would be the gold standard in terms of。

What position you aspire for？Like that should be the thing if on B bits， it should take you I mean。

 ideally， okay， ideally log one orypsson， but even polynomial and log one orpsone polyin B。肯定。

Anything is？Do such algorithms exist for LPs Oh yes yes such algorithms exist and that was a big deal I mean the first when they say polynomial time algorithm。

 the first polynomial time algorithm for LP was discovered by Kaan in I think late 1970s it was such a big deal that it was reported in New York Times and I think it's one of the biggest achievements in algorithms well actually talk about Kaian's algorithm I think in the next class but yeah ideally we want to get polyin log1 or Epsilon。

On this。And we can。Anththe is。To get the this algorithm for like just poly one of our Epsilon runtime。

 it seems like couldn't we have done that just directly with gradient descent in like just like some cut up function that tells us like。

You scales linearly once the constraint is satisfied。嗯嗯。I have to think about this。

 I think the tricky thing here is really that。You have a。You have many different linear constraints。

 but you have L13lM， you have many different linear constraints。

 so you'd have to aggregate all the linear constraints into a single function somehow。啱。

Right the interaction between the adversary and the online optimization。

 what it lets you do is to pick it sort of lets you pick the one which is violated。

 but you could try to cook up a single convex function that aggregates all of them together。

So for instance。I think you can。嗯。Like if you look at this function。诶。This function blows up。

If you try， if any of the allies try to get close to zero。Blows up。But yeah。

 I don't know how to use this。Fun right， So this is a single convex function。

 It incorporates all the linear constraints that you have。

 but I don't know how to use this to to gradient descent because。Yeah。

 if I start at a point where LFx is less than zero。Then， this is actually。

Infinity right log and affect it sort of infinity， So that's not good。 Yeah。

 I guess I was thinking just like you know， like a really function。

 like it's you and then you sum them up for each constraint。 you know。

 and then it's like zero if it's if it's satisfied and then really right。

 but I'm realizing now that then it's not like the lip shits constant gets grows with the dimensions grows with the number of constraints maybe that's right。

 yeah， I think yeah， I think you can do yeah， youre right， Yeah you can do such a thing I think yeah。

 you can actually sort of set up a function that grows I think eventually we need to prove the following thing I think that。

Yeah， well just have to prove that this aggregate will be if it is small。

 then all the constraints are within an epsilon。So yeah， yeah， but yeah， if we can do the relo thing。

 I think it works。I mean， this algorithm as I described it。Yeah， it can handle。

Exponentially many constraints or even infinitely many constraints。嗯。Yeah。Yeah。

 but you can actually use aggregate them into a single function and also to create insent that way。嗯。

Okay， thanks。It he is。嗯。Anything else？Okay， all right。 yeah。 So we'll meet next and we'll talk about。

Ellipide algorithm and centralroid algorithm， which gives polylog on over epsilon runtime。试间晚茶。

Thank you。嗯。Thank you。H Pro professorsor， do you know if Iman has set his office hours yet？Yeah。

 he emailed me saying it'll be on Wednesdays and Fridays。あ。

I think he might make an announcement today。Okay， thanks。

Could you go over why it is that we want polylo， runtime and not polyly。あ。

Why it is poly1 or why the runtime of this algorithm is poly1 or2 I don't know why we want polylo or we want polylo well the reason we want polylog is in some sense if we want the solution with B bits of precision。

There we want a runtime， which is poly and beat。Because essentially polline B would be。

Like poly normally in the input size。If I have inputs which are B bit integers I would want the answer to be with B bits of fan。

 I should get polyine B run time and that corresponds to like B bit of precision would be Epsilon is 2 to the minus B。

嗯哼。😊，And then I would want runtime， which is polylog 1 or Epson， which is polyB。你事。Thanks。

Also I was thinking about I was looking at it and it looks like so I think if you choose H as like a at times F。

 then you get this optimum and like one step if you obviously the argument is hard to compute then so it's not actually useful most of the time but then that made me think maybe like someone asked like how do you try to choose H so then I was thinking maybe or do you just want to choose H to be similar to F so that it like accurately represents。

The error from F。嗯。I don't know if that's if that makes sense， right， H is F。Yeah。

 what does that correspond to， I think that corresponds to。

And I'll get through that tries to essentially。Solve for gradient of f equal to  zero， right？

Oh I mean that correspond to since youre a convex function。

 the only place where the gradient is zero is at the bottom as is at the minimum so we could for instance try to solve for this right right yeah exactly so like so I guess it's pretty useless most of the time but it was making you think maybe like you want to pick the H that like you know how to calculate minimum for it that's easier to calculation this but is close to F。

Right， right。Yeah。But maybe that's not the right way to Well yeah。

 I think I think like I think for instance， like we you could pick like the quadratic。

 which is given me the hesian of F。At the point。Right so。嗯。Right， so so yeah， so this would be。Yeah。

 X H of F。X。Yeah， if you picked。If you pick this as your。Regularizer here。Well。

 the I guess what I mean is D of y from x is y minus x transpose head sub for x y minus x。

But head of for V the hetian。5。This is actually kind of the in some sense。

 the nicest thing to do because if you had any quadratic function。

 if F was really a quadratic function， it really transforms the space into the nice identity function every step。

nice but this gives you a newton method and I think we are we don't like we can we know how to analyze this。

Only when you start close to the optimum， but it gives you very。

 very strong congence as you suspect that it gives you like log， log one over epsilon time。

To be with Epsilon。So it's like it's way stronger than。Even what we wanted here。

 it's instead of polylobin orilence， loglobin or epsilon。But yeah。

 I guess the difficulty in such variance is really how how to analyze these things。

 these objects yeah I think a lot of gradient descent is ordinary a lot of optimization。Of course。

 you start with a general left。And if you try very tricky things。

 it won't work and a lot of it is also trying to be super cautious like if you look at interior point methods and analysis of interior point methods。

Like， you know， it's。Like really， like if you want to get a proable algorithm。

 you try to be extra safe with your res and everything。But you know， in practice。

 apparently inter point method just converges within three or four steps or something like this on。

It converged very， very fast in practice。But in theory， you try to keep the step size small。

 you try to move very slowly and you try to hold on to all the guard rays yeah。真。Thank you。没有。

Professor generally speaking calculating the hessian of the function is like it's where the main problem lies in the gradient descent right。

 like if you're talking about this particularly here。

 because if you weren't able to calculate the gradient of functions and then that's why we move towards sub gradients shouldn't similar case be like for hessian and then finding the H function using this。



![](img/08d769afc7e7ddb036446cfb205ca55e_21.png)

Right， you're right， but but in some cases you like you do know these Hasians very well like because you constructed F yourself。

 sometimes you like for example， linear programs， you the mean Ti point methods， for instance。

 you take a linear program with many constraints and you cook up。

As a convex function to minimize and so it's a very nice you function explicitly。Like， you know。

 it's some over logs or something it's you know explicitly and you know the Hessians explicitly in many cases。

Yeah。那个。It's really that once you start changing。The algorithm more and more。

 it gets harder and harder to。And。It's just， that's sort of really the bottleneck。these things。

Thank you。

![](img/08d769afc7e7ddb036446cfb205ca55e_23.png)