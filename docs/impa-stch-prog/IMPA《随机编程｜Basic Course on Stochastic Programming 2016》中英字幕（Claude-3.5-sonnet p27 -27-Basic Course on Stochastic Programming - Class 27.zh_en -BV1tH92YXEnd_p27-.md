# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p27 -27-Basic Course on Stochastic Programming - Class 27.zh_en -BV1tH92YXEnd_p27-

Okay， good afternoon today。

![](img/b3ee092578312ebc009a8cbd9b3be07d_1.png)

Do they have the two good news， The first one。Is that the project will be postponed， so。For you， the。

 the final project。We can deliver this project to us up to。18 of July。

So you have more than one month month to finish。Because we would like you to many for those that who will visit the Rio and Boes。

 we would like you to， to take an opportunity and enjoy the conference。

 the international conference on Stocktocast program that will be held in。😊，In Bozes。 And next week。

 we are going to have two mini courses at the campus。 So would like these students to。

To take this opportunity。And well， this is the first good news。 This is redline。For the。

Final project。

![](img/b3ee092578312ebc009a8cbd9b3be07d_3.png)

Well， the second good news， is's today's the last class。So yeah。Yeah， we are finishing our course。

 And today， we are going to continue the subject of bundle methods。😊，But， we are going to study。

A different kind of oracles is smart oracles that take the。

 the advantage of the structure to stage stochastic program problem to accelerate the optimization process before we start with it is。

 the this is marked oracle。 we are going to consider。

We are going to start the conversation analysis analysis of。The left of bono methodss。

 The one I presented the last class。Well。

![](img/b3ee092578312ebc009a8cbd9b3be07d_5.png)

So the this is light。 I just I'm repeating the。The algorithm we saw last class。Here， I made more。

What I did here， I made available The， the this is step， step 2。That's the one we update Dis center。

 So just to， to recall the algorithm。 we have a cut model we have here。

 This is the bundle of information。 We can have。That just fuel linearizations。 If you want。

 the next three will obtained by projecting a stability centre onto a level set。

 the level set of the model。Well， the first situation you have what's good in this。

 this method Ive forgot to mention is we need just one parametermeter。 is this gamma。

And once you define these gam， all the other parameters， for example， this is fundamental。

 this level， but is a function of that one。 So you just have to set one parameter。And that's good。

 And also， in theory， we can find the optimal。G嘛。I， I， if I'm not mistaken， is something like 0。

0 dot 2。3 something。Well， I will give you a head for the paper。 But the fact is。

 we can find the optimal gament。In theory， impact not necessarily is the optimum。

 but it gives you the， the the fastest conversions。But I usually， I take this number。嗯，做个嘛。

For the stopping test。 Yeah， okay， that indeed， Kaa mentioned we have two parameters。 This is the。

 for the stopping test。 this toleranceance。 Yeah， yeah， but this is mis standard all they are good。

 right。For the algorithm itself。Because when you have an algorithm， but many parameters to set， Well。

 you have many combinations。 You'll never know which one is the the best。But here。

 it's easier to set up your algorithm mean， once you're called。

 you just make some choice here and you easily find a good one。Good parameter。Well。Here。

 I mentioned we need this lower bound for the optum value。However， it easy to compute。

 If you don't know， it see to compute。 you solve a linear problem problem。

 You minimize the first linearization of your feasiblesible set。嗯。What else， Okay。

 so you call the oracle， you compute the value of the function sub gradient。

 you update the upper bound。 I'm putting here this L。 This is the the counter。

 I I'm counting the number of time times I update date Dis center。 Okay。

 so the first the first you give a x 1。 This X1 will be stability center。

So I call this is the first of center。You stop you set your optimal gap Since we compute upper bound there and lower bound you have。

 it's it's a given。 Well， by the way， should be one here。Should be one， sorry。

If it is optimal gap is small enough， you stop。And this is another test that you might update your stability center or not。

The idea is， if you decrease enough your stability center， you may think of upd。 Sorry。

 if you decrease the opt gap， you may think of updateddated stability center。 And if you update date。

 you just count here。Of time， you are updating it。So the idea is we have here。Upper bound。

 suppose that we have the optimal value here。And you have。A lower bound。

And we take as the level parameterome。Something。In between。These values。If it。

 if you are minimizing function and you know the optimum value， sometimes it's， it happens。

 You know the optimum value， but you don't know the solution。 If you know the optimum value。

 you could set F level equal to the optimum value。The idea here， when you don't know this， this。

 this option value， you takes something level the level parameter in between these bounds and how you do that。

You just make a convex combination。

![](img/b3ee092578312ebc009a8cbd9b3be07d_7.png)

Which is。3。Can you take something in between。Could be。Here， for example。

Or could be greater than the option file。 we never know。

But the the important thing is you have to keep it in between the box。嗯。When。

What happens if you choose this level。Greater than or equal to the optimal value。

If it is F level is here in this part， the level set will never be empty。

 But if it's under the absolute value， the level set might be empty。It can happen。If it's am。

 it's because this guy is a lower bound。 so we can just updateate this one。Here。You becomes the next。

F flow。 And then we choose another left a between these two box。

And I show with the last class when the level set is empty。 Indeed， this guy heres a lower bound。嗯。

Okay， once you have this the nexted 8， we call the oracle。 We updateate here， the upper bound。

For the bundle management， you can just add more one more linearization in your bundle。

 or you can compress。 compresspress means that you delete everything you have。

 You keep just the last， the newest linearization and aggregated the one。

 So they aggregated the one we saw how to compute last class two classes before。

One thing that I haven't mentioned。Is the fact。EIf you don't delete any linearization。

We don't need to keep this。This key K of a。Also， if you delete linearizations that are inactive。

What does it mean。So， every。Ititeration。You find escape plus1。And this。

Is written like you have a linearization。And this linearization。For all J in your bundle。O。

Once you solve this problem， you have some lag multipliers here。

Let's say that alpha J R the La multiplies for this constraint。You may update the， the star， the。

 the， the bundle。As。The next one。We will be。The new linearization。And all the， the sets， the index。J。

 such that。Alpha J is strictly positive。This is another way。Because if this la multipier is 0。

 it means that this constraint is not contributing for defining this aer rate。You may delete it。

 So if you manage your bundle。In this way， you don't need to put the。They are great linearization。

Because if you add， it will not contribute， because if you remember the aggregate linearization is a convex combination of all the study gradients。

And for the convex combination， we are taking this guy here， this alpha。 So if you add。

 this information is un included here。 which like you are。Give you more information that is not new。

 So in this case， you don't need。呃，Well。And that's all。 And the algorithm is simple like that。

 The Intuition， the you already know that you we saw some figures last class。And， well。

 the last slide of last class I said that I show with this， in fact。That we are going to split。

Our iteration process into  cycles。And it， and with define final cycle by this counter， L is the。

 the the counter index counter。For the disability center， when we change the center。呃。Well。

 you may call this。Set。Let me start here。Are you called this set。K。Of L。Which is。

 which is composed by the iterations， such that。slide this。て。L plus  one。嗯。In this。

 for those iterations。They stability center。Is。Is the same。 It fix it。I may say that it's like that。

It's fixed it。Okay in this。In the exact。The level parameter。Is also no increasing。Why。

Because in for those iterations， we are not apppidating the lower bond。This idea haven't shown。嗯。

This is fixed。For example。嗯。I haven't。Shown that。If。You find， if you find the if the。

 the level set is emptyed。Let's come back here。We are here。You try to， to get an exiter rate。

 The Q P is infeasible。 We are going to updateate the lower bound。In this algorithm。

 this is the only point that where we updateate the lower bound， because here's fix it。

If you update the lower bound here。When you come。Well， necessarily。Disneyequality satisfied。

And we are going to count L plus one here。Why this。Instead of。Making some competitions。

 I think it's easier to show。Ius illustration。You have fear， F okay。F。Okay。Suppose that our level。

Is here。O， so。This distance。Is going to be。Up man， this will be。I want to know this distance。

This distance is Eia Qua。And if you， we use the definition。Okay， so this distance here。Is。어떻。No。

Let's pay attention here。 When you updateate the lower bound。So， it means。That。This guy comes here。

And this。This distance。Will be。The next Dlta K plus  one， because we make。Thissipate。嗯。And， indeed。

D K plus  one will be equal to this other measure。So that you are going to surf。

 I didn't count K plus1 here。好。But。Yeah， I could here to be equal to the the algorithm。In this case。

 we are going to satisfy this inequality。And then。Well， why this？ This is just to ensure。That。

The lower bound doesn't change inside this cycle。Okay， what else we have。Okay。

 this is comes from the definition。When you update the lower bound at the， the disability center。

 you have this inequality。 This is the definition。If you expand。In L。

 we are going to have this inequality。And since gamma is between 01。 This is a number between 0，1。

If L goes to infinity。Then， these terms tends to 0。And we are going to have cons。

 The upper and the lower bound will coincide。Yes。2。Here。Just a convex combination。

You make a convex combination between the upper and lower bound。No， sorry。 I didn't understand。

 Could repeat。Yeah，How， how can you， how can you identify if the。

 the the Q P is feasible and feasible。QP。Yeah， this one， this projection。This projection。

 So how you do this， What are doing practice the following。I have out the data。At this point， I mean。

 I have Sa built center。 I have the model。 I have this parametermeter because the parameter I define it here。

So I called the Q piece over。And if it solved the problem for me， to will give X K plus1。

 And that's it what I want。 And I continue。But otherwise， this feasible set can be ampt。啊。

White it can be em。 I show you a figure last class。嗯。Suppose this is your function。This is。

To the decision you have computed。 And this is your model。Okay。The optim values here。Yeah。

 you have to be， if you， you have to get a lower bound。A level parameter。Above this one。で、ミニマフでもある。

But because if you have， if you are not in this case。If you are here。Then your Q P will be invisible。

Uhhu。Okay。嗯。So what you want to， to show is that this inequality will be satisfied infinite many times for L。

That is， after finitely many steps， we are going to decrease the optimal gap by this fraction。

And how we show this。The idea。For the conversion analysis。Is the phone。



![](img/b3ee092578312ebc009a8cbd9b3be07d_9.png)

Let's suppose our feasible set is this one。And。

![](img/b3ee092578312ebc009a8cbd9b3be07d_11.png)

Let's suppose that。Our stability center is here。 Lets focus in a center in a cycle。

 When you are in a cycle， your stability center。Is fix it。

So the idea is to show that all the honor points。Will， you。

 will be far away from this guy every time， for example， if X， K is here， F K。Plus one。

Should be farther away from disability center than X K。

It's like we are moving farther away from Sabil center。And the distance。The。

 the step size you are making here。Or it's going to be bounded by this， this value。

 which is a fraction of optimality gap。

![](img/b3ee092578312ebc009a8cbd9b3be07d_13.png)

So， this inequality shows that。Iterations， iterates。Will you get far away if you compare with this J。

J plus 1 and J。 So we are getting far away from disability center， which is fix it。

And the step size is。Greater than this fraction of the， the optimalal again。

 So if you do this many times， what can happen。We are going to be far away from the feasible set。

Because you are every time far away from the set， or you'll be far outside the the the feasible set。

 or it means that that。They step size you， you decrease。 So you are going to move far away。

 but a certain point。Your step size will be really small。Because outside this feasible set。

 we are not going to be because were projecting a subset of this feasible set。

The only possibility is step size will decrease。This distance will decrease。

 If this distance decrease， it's because。The optimaltic gap will decrease。

 So this is the idea behind the， the proof。 So first of all， we are going to come to。

 to start with Disneyality。

![](img/b3ee092578312ebc009a8cbd9b3be07d_15.png)

嗯。Well， we are the in a cycle。 So I fix it here L。We have this。

This is a deious constant of the function F。Function F is convex。

 and we are assumed that the feasible sets compact。 So this constant always exist。

We don't need to know it， but ours exist。No， defus satisfaction compact。

 I me assuming we don't need this for a more， a more。General algorithm for the algorithm。

 I show that， we need compactness。Okay， only for that algorithm。

 But we have more general level bundle methods that。That doesn't assume compactness of feasible set。

Okay， but then we have to do more the conversions analysis a bit more evolving。 just simplify again。

But you agree， right， If you have a convex set over a compact。

A convex function over a convex a compact set。This function lips sheets constant has a has a lip sheets constant。

 sorry。嗯。Okay， so we want to show dis inequ。I'm going to get a J。Inside that cycle。And we know that。

X， J。Is equal to the projection。Onto the level set。Ja 만 well。Of our stability center。And。Last class。

 I showed that we can also do this。Okay，-1。 But here we only have。They aggregate unionization。

If you don't remember。This。Is this set。Such that the aggregate linearization。Okay。

 it's like you have a bundle of linearizations。 If you make a projection on the， the the level set。

Constructed by those linearizations is the same thing that I should delete and just consider the aggregate linearization。

 This we show at last class。Okay。By this。This proper。呃。The projection ortho togonal projection。

Onto a convex set。啊。So。This is。True。For all x。Be longer。To this set。Right。

 this is a property for projection。And。O。Let's skip this for a while。And。Our bundle management。So。

 if I define。The bundle at the iteration， J plus1。Cons。At the least。The index J plus 1。

 the nearest linearization。O， sorry。Dont want to show here is that J sorry J。G。K， keep us one。Yes。

How it was in the algorithm。Here。our。Moonddo management satisfied this property。So， have that。

And because of this property， and because。F love G。Is less than or equal。To F。Jame，-1。

Because I haven't written here。But inside this cycle， this property。Is also satisfying。why。I know。

 it's here。 I have already written， sorry。It's because the， the lower bound is fixed。

 the upper bound made might decrease。So their level might decrease by the， the。

The definition of the level parameter。So， this is true。With it is two properties。We have that。

The new level set。Is contained。Indi是。Because we're all。

This one is defined on with this linearization。 You will add another linearization。

 Its more costrainant。Your level ofpometer is decreasing。So you， you are more constrained。

 So this is true， okay。And。If this is true。啊 and also。We know that。 the next city8。

Belongs to this Lego set。And because the projection of the center onto this。9%。Okay。Cons。嗯。Wait。

Something is not clear here for me。This guy is more constrained。O。Okay， so it means here。喂。

Hiss opposite。2。Yeah， these guys more more constrained。 So it， it is contained in that one。Thank you。

Thank you。Nothing make sense。 what I want。呃。Okay， now， now it makes sense。

 And this point is in this set therefore4 is in this one。Now， I use Disneyequality。啊。By this profit。

 And here。We are going to have。I'm putting this guy here。Okay， now we are most done。Because I use。

 I'm going to use。Disneyequality。I just get。XG。嗯。呃。This is是一个。If I add and so be， so be track。

Extract the。The inner product。O。And now we are going to use this inequality。J plus 1 minus J X J。

 Okay， this is equal。And here， I have。The contrary。So it means that this term here。Is no negative。

And。Come back。嗯。Because here is non negative。So this term is equal。 same thing here。

 But the order is of contrary。是。So it's no negative。 So I'm going just to。To。Ignore that term。

And then， we have。Disney quality。Greater than or equal。嗯。G。Okay。啊。Well， to， to finish。

We just need to work out。With this。To get our result。And for that。Let's think that。X， J plus 1。

Belongs to this level set。If belongs to this level set， it implies that。The linearization you have。啊。

Why， because the initialization J belongs to this。这接帮到。Nization J belongs to the bundle。

 So it means that this linearization。Is part of the set to define the set。

If you get the next point there， it has to satisfy this inequality。Okay。Well， now I'm going just。

 I'm going to play with Disneyequality。We have using Ks inequality。 we are going to have。

The norm of this vector。Times。This distance。Oh， this is what I want。Here。呃。

This is greater than or equal， too。I passed this guy here。啊。Okay。And。This is equal。

I'm using the definition。Okay， just the definition of level parameter。And now。2。

But our function is lipshe con continues。And has a constant。Of a constant capital Lada。

 So we know that。Capital Lada。Hes bigger then。The norm of the solid gradient。Okay。

 because the functional zip sheet con containers。And with this information， we are going to have。

Dズney壊れて。嗯。This is F of x。G。And this is。Worse than the upper bound。Could get the best candidate。

 the best evaluation。 I know up to that iteration J could be the same or could be different。

 But this is。It's likely to be better than that one。 It's the best bound。Ms。A lo。And this is。

1 minus gonnamma。G。Okay。Square。It's being。Square。And， well。So you get this term in replaced here。

We have our result。So this is the idea that iterates are getting far away from the fixed stability center。

Well。So what I want to show is that。The cycles。I bounded。 You have only， finite many。Index here。

If they are bounded， so you perform some iterations。

 and then you have the algorithm will decrease the optimal gap。And now I'm going to show that。

 in fact， that cycle is bounded。 And we have the maximum number of iteration we can perform inside that cycle。

 And this is the maximum number of iterations。And where D here is the diameter of the。

 the feasible set。呃。To show that。We are going to use the prove inequality。So。

 this is going to be quick。We know that。This is what you have shown。

But I could apply the same inequality in this term。That will be。那自接算。And if you continue。

To this term。Or simply。Okay。The fact is。The optimal gap is now increasing。

So if I replace this by the last one。You not change Disneyality。It's increasing。呃。O。The level。

 the feasible sets bounded。 And I'm assuming that the。The diameter。Is the。嗯。O。

 note that we are some in I， but you don't have I。 In fact， this is equal  too。

How many elements we have in this sum is K minus。K， N plus1。Thanks。This。Now。

Think drive this K to infinite。It cannot be to go to infinitefin， because this is a non negative。

Constta number call is not constant because this is decreased。 Suppose that you have a toe。Tod us。

This is greater than a tolerance。 If you increase K。

 you cannot increase up to infinity because this is bounded。And if you arrange。

 this is the number of elements。From K of L up to K。And。You can show。We have that key。K L。Plus one。

It's less than or equal to。D。Loowned them。Over。すラマ？And it is what we have here。

It means that this is the maximum number of iteration we can perform。Inside the cycle。After this。

 one more than this， for sure， we are going to end up that cycle and start a new one。

 So you are increasing L。 If you are increasing L。We have convergence。

 So the convergence of the matter is done。We can go farther。

Bounded the maximum number of iterations to achieve a tolerance， a gap。

 optimality gap less than a tolerance。 But I'm not going to show this result。But， well。

 this is a theor M。let's assume this X is compact。This the diameter。

 then to obtain an optimal gap less or equal， less than or equal to the tolerance by a positive tolerance。

 we need to perform at the maximum these number of des。no increasing， at least。TYeah， yeah。你次。2。Yeah。

 but see， we are optimized and we give our tolerance。Greater than 0。Replace this by the tolerance。

 We still have。Thisequality。And this tolerance， its still true。And it's finite。嗯哼。嗯。No， no， no。

 The question is about this D。 If we use this D， the D is the diameter of the feasible set。

 We don't need to know it。Yeah， the bundle。Yeah said。Yeah， now。

I'm assuming the feasible set is compact。 and the， there is the level set。 That's a subet。

And you we have。We have our set。And at each generation， we。

 we have a subset of these where we project， you make the projection。Okay。

Im assume that this guy is compact。 and the diameter。Of this set is D。 We don't need to know D。

 Just assume that it the feasible size compact。 And we are also assuming。

That when this constant exists。 In fact， it， it exists because the function is convex。

 but we don't need to know this lips is constant， neither。Once again。With all this assumption。

 assumptions， the math works， and we proved have proven the convergence。 It's not that。

 it's not difficult。If you get rid of this assumption， X could be unbounded。

 We still can prove conversionence， but it's more evolving。



![](img/b3ee092578312ebc009a8cbd9b3be07d_17.png)

And we have to change the algorithm bit。You have to come here and change when you make this projection。

We are going to， to have a a range multiplier。We just don't。 we， we。

 we give a bound for this lag multiplier。 For example，100。

 Every time the lag multiplier is over there 100， we。We defied。We have to increase the level set。

 There is bit more of detail。 The definition of the level set is not this， the level parameter。

It's the upper bound minus something。 And every time the lag multiply is so large， we。

 we decrease this something。 It's a bit different。But。It only changes this is step 3。

A bit a bit of change here。 But the conversation analysis is more difficult。嗯，O。

So we have this result。 I'm not going to prove this result。 This is the first paper by。Now， in fact。

 this is in。And the first paper by Claude March Naidovnesedov in 1995。

 I gave the headphone in the slides of last class。

![](img/b3ee092578312ebc009a8cbd9b3be07d_19.png)

Well。Let's come back now。This。This one hour we have left to。

 let's come back to the Swis stagetoline program。settingtting。

And how to apply these methods to this to this this kind of problem。

 Well application is straightforward。 I'm going to give some details of how to exploit the structure of the oracle in order to facilitate the method。

 Let's focus on this problem。 We already know very well， this kind of。Optimization problem instead。

 once again instead of the the expectation， we could have a risk measure here。

 It's not a a problem for this approach。 I just keep that to be simpler。Well。

 we solve the second stage study problems and we get for free de laation multiplies of this LEP。

 and we can compute a gradient for the function。In the other shaped method， is the fna。

 We have the master and these leaves。We saw the LP here give an exit to date should be X K us one sorry。

 it's Z。 but you get them， you get the。

![](img/b3ee092578312ebc009a8cbd9b3be07d_21.png)

The nextate。 And you send the next thread to these leaves。 This is the oracle， the black box。For。

 for this X， you have to solve valueP。Ving the， the， the parameters and certain parameters。



![](img/b3ee092578312ebc009a8cbd9b3be07d_23.png)

Once you， once you solve all those LP， you compute the value of the function and a sub gradient。

 So this， we include in the in in this bond of information。

 you have the cut updateate the cut plane model and you start again。嗯。This is the all shaped method。

For the proximal bundle method， the difference is we have a quad term here。

And you make a test concerning this center。 if a serious step or old step。In the。

In this kind of problems， in stochastic program。This proximal bundle method is known as regularize the composition。

 In fact， they regularize the composition。 I think they don't update this T。

 and they have to keep all the bundle of information。 So if more details， if in fact。

 is bundle method。 if a bundle method， we can show more things。 But in practice is the same thing。

 except for this constant here， this parameter that we update it relativelyly。



![](img/b3ee092578312ebc009a8cbd9b3be07d_25.png)

Okay， so from， from that shape to this proximal bundle method， what we changed， the master。

 and we add。Addit test。Updating test。For the level method， what we change。The master， again。

And we can have here a test I is not here。 don't know why。

 but we have to test the how to updateate the fact is。

 we don't need to updateate this guy if you don't want。 It's alternative。But well， what we did。

We just change the master。And now we go， we are going to consider these leaves。

 What we can do with these leaves。 try to improve the methods。Well。

 the idea is we are not going to solve out the LEDP。We are going to solve some of them。

 Take a fast approximation for the， the remaining ones。 We are going to have an approximation。 See。

 this is not F of Z。 an approximation。Of the， the optum the of the value and approximation for the third gradient。

And with this inexact data， we are going to have an inex Cat model。



![](img/b3ee092578312ebc009a8cbd9b3be07d_27.png)

When you consider the exactness here， you don't solve out the LP， at least exactly。Well。

 this model is wrong， and we don't know what happens here。

 You are inserting inaccur into your algorithm， and you don't know if it's going to work or not。Well。

 if you handle。The inaccuracy。In these wavess， we still can have convergence。

 and the convergence will be much faster in practice。 Why faster。

Because we are going to save time in this， in the oracle。In general。

 we are going to perform more televisions。 but since each every television。Is a more。Is cheaper。

At the end， we， we gain in CPU time。So now， now let's consider how to consider the exactness them in these slaves。

嗯。Well， here is just an example concave fun convex function， piece Y linear。

It's the kind of function we have when dealing with。To stage sastic programs。

When you consider exact oracle。 So the ahore of the orac， I'm going to call by Eppsilon。

 If you don't a hore in the oracle， every time you compute the function exactly。

 we have a sub gradientient， and we can have these tangent cuts。嗯。You may have inexactness。

If you have an exactness， you may not evaluate the function correctly。

 You may underestimate your function， or you can overest， I don't know。 And also。Here。

 this lo of the， the cuts。

![](img/b3ee092578312ebc009a8cbd9b3be07d_29.png)

You don't have much control。We may cut off the function。In this situation。

 if you use an oracle that provides you this kind of information， this is exact information。

We cannot ensure optimal solution， why， because we can cut off the optimal point here。

Because of this linearization。However， it with you have in exact information。

 but out there in exact information。Approximates from below。And we decrease these errors。At the end。

 eventually， we are going to have。

![](img/b3ee092578312ebc009a8cbd9b3be07d_31.png)

We are going to get an optimal solution， exactly。

![](img/b3ee092578312ebc009a8cbd9b3be07d_33.png)

So having this lower approximation， we call oracles providing exact information。 in this way。

 you call it lower oracus because inex， the cuts never cut off the function。The other case。

 in the previous case， we call this， the order providing this information as。U oracle。

 or oracle for uppercase。Because we have here。In this case， in exactlyness， the function evaluation。

 and you can have inex in the sub gradient。But， let's。For simplicity， let's consider this case here。

Okay， and I'm going to show how we can get this information。

We have also partially exact oracles that sometimes for some point。

 you call the oracle and have the exact information。



![](img/b3ee092578312ebc009a8cbd9b3be07d_35.png)

Or you can combine both of them。 For some case， you have a control of the a horse。

It's not that we don't。 We know the。 We know a upper bound for those。

And sometimes you don't know anything about the air。The idea is， this is cheap。

And this is cheaper because we don't have any control。

And we call these oracles with on theda Cur because well we wont。 we give a point for the oracle。

 We expect this oracle to provide us with the function of value。

 approximation and approximation approximation sub gradient。

 but those approximation should not be large enough。 We have a certain control。

 And we have to give this， this bound to the oracle。



![](img/b3ee092578312ebc009a8cbd9b3be07d_37.png)

嗯。Okay， the idea is default。 Exact articleacle。 This is how you know。 nothing new。

But we are going to consider oracles that receive more information。Which is。You not only send X。

 but you send the upper bound for the a。 you allow the oracle to to do。And this is a target。

And this target works as follows。 Okay， so let's assume we know this e。 We give it the oracle。

And the oracle if on the amount curious， we compute an an an estimation for the function and for the solid gradient。

 And there is this aho。We don't know it because if you know this error。

 we know this and then you compute the part of the function，F， we don't know this one， this atom。But。

 we assume that。This error is no negative in the sense that I'm app the approximating the function from below。

So， I give a x。Computing。This is F of x。This aho。I。At them。Of x。 So this error， I don't know it。

But I know that therefore I'm。I have fear。I know that。 this atta。Is less than or equal to this error。

 I pass to the oracle。And I don't want this to be true all the time。I just want this to hold。Wen。

This estimation is less than or equal to this target， I give。Its is confusing， but， in fact。

This is not confused。 I'm going to explain with illustration before。 well。

 what we need to know is the phone。We give three informations to the articleac。This information。

 this a is always not negative because we're approximating from below。We have。This is inequ。

When this approximation。Is less than this target。 This gumma is another gam is not the gamma for the level bundle metal。

 Okay， sorry this。Strange notation should have replaced this by another one。It's a target。

As a particular case， if you take。This target equal to infinitefin plus infinite。

 So this inequality is always satisfied。 It means that thisequality is also always satisfied。

 So in particular， if you take Epsilon equal to 0， we have an exact oracle。So。

If you take this target equal to plus infinitefin。Epsson equal to 0。 This oracle is exactly this one。

have a exact to。Okay， that's the case。Nothing new。The interesting part is this one。

 supposeuppose for， for the moment that epilson is 0。And you give the information to the oracle。

 I give X， K plus 1。I give this target。And I give。This bound for thehu。And， well， I compute。

And in process of compute are of the function。When I realize that this underestimation is over。

This target， I don't spend more time computing this function up to here。I just stop where I am。

 and I compute this under linearization。The idea is， don't spend time。

Computing the exact value of the function。 If that point is not good enough。

Good enough in which sense。 Well， I have this point。 And this is the best， best。

Estimate of the optimum value。 This is the best value I have。I get it。 I can set it as the target。

 saying and say to the oracle。Compute the well of the function。

 But if you realize that this points not good enough。Itop and providing what you can。So。

 this is the idea。嗯。When we don't， we consider here this upper bound， strictly positive。

 It's like we allowed to have this kind of approximation。 But in this case。

 we know this a bound for the a。 We don't know the a， but a bound。 And in this case。

 since this guy is not good enough。 I don't have any bound here。I don't have a control， in fact。

I have a upper bound because the convex set is compact。 We have a a upper bound here。

 but I'm not going to enter in detail。The fact is， you just don't have any clue of what's happening there。

嗯。How to compute this kind of oracle on the mono oracle。

Oracle with on the amount that accuracy for two stage stochastic programs。Let's simplify。

 it's possible to consider the general case。 But let's simplify。

 let's consider the uncertainties only in the demand and this technological factors。Why。

 because when I you look at to look at this problem。The duo of this problem， the dual feasible set。

 doesn't depend on uncertainties。呃。So it's fix it。 That's good。And here is how I computer on the。

 how I program。A define oracle with on the mono Curs for two stage schastic programs。

The idea is the fog。I suppose that I have some points in this set。Remember， the stochastic。

 the composition that you coded for the project。 you have， you save along the deterration。

 the iterative process， some points。Some duo points for the duo some， some points in this set。

 So consider that you have some set， some points there， I don't know，10 points，20 or 100。

 I don't know， but you have some。this is given。So we start here。 Okay， considering this J equal to 0。

 Then we see y。And to the Or is giving this point。Upper bound for the a and this target。

 The first thing we do is we look。We look for dual points in this set， that maximize。

That maximize this linear function。 Well， if I replace D。By the dual problem here。

If I replace the by。By this set。This problem will be a linear。

 This problem will be a linear problem problem。 But in this case。

 it's not because we have only finitely many points here。So this optimization here is quick。

I a practically， you have to multiply a matrix and take the maximum value。Okay， this is easy。Quick。

And once you have。This is going to be the first approximation for the function at this point。

 And then we can， we can compute an approximation for the function。An approximate sub gradientient。

With this approximation， we performed the first test， this approximation。Is greater than the。

 the target。I mean， we don't improve。 This is saying that。This point is not good。

 I have a better candidate。 So if I have a better candidate。

 I will give up on an investing time in that point。

 and I would just get this approximation for the function sub gradientdient。 and I go out。嗯。If not。

 if not， what I'm going to do， I get the first scenario。I start J with 0。 I get the first scenario。

And I solve the LP。I can solve inexactly， for example， I apply a integral point method。

To find a pi here， pi J， So find Disney quality。 This is。In exact optimality， now if you have this0。

 you have in fact optimality。 you can solve it by using an interior point method。For now。

 you can consider epsson equal to 0。 It means you solve the the LP exactly。

And when you solve this exactly， you may decide to put this information to that set or not。

But let's suppose that you add this set。You come here。And you are， in fact， you come to step 2。

Because now you remove that part in exact for the first scenario， we， you add this one。

 that's more exact。Less inex， in fact。You have an a new estimation。 You test again。

And the worst case， you have to do this any times， which is you solve all the LP。

It means that when you have a better， when you solve all the L EP。

 it means that this guy is a better candidate。If it's not， at some point。

 you are going to stop and return just approximations。呃。Once we have those approximations。

 we can define the， the the bundle of the planning model the same way。

 but using in exact information。But。We have this inequalityality here。

How do we know that we will never。We always compute like that。



![](img/b3ee092578312ebc009a8cbd9b3be07d_39.png)

How do you know that at some point， we are not going to cut off the function。This。

This oracle ensures that we， we compute only under approximation。

And that this is not difficult to to show。mギ。P idea。Suppose that。At the point， why。We approximate。

The second stage is a the problem。By a feasible point。In the in the door。This is just approximation。

 okay。We know that if you take the maximum over the the pi here。 And that said， we have the equality。

You just get a feasible。 You have anyality。Okay， let's assume this。Okay。Get now。Another point。X。

We know that。 the same thing。This is also true。Because this point is feasible。呃。This is equal。Okay。

 just some。So we track the， the same point。Well， this is。Okay， just we arranging these terms。

 We have that。But see， this is the approximation we have for the function。Call this guy here。

But this is the same。If you take the expectation。One side here。You take here， too。Pication here。

This will give。And the records function。At x。This estimation， why。Okay。Here I might to。And， well。

 we may some。In this case。See transpose x in this side。The same then。Computer like that。See minus。

I don't know why I put X I。 That is no X I。But。This is the value of the function。Thats。

This is the one of the function。This is the estimation we are doing。 is the。Here is this。

 the exact sub gradientient。Saing that the linearization。Is said of the lower type。Sa that。

Our organization is this type。Never cuts off the function。And this is because we are getting。

Do all points that are feasible。That's theism。So we are。Have this nice property。Okay。

 so we have thisality and things。Work more or less the same， same way。Oh， this is the model。

The upper bound。Now， instead of considering the the approximation。

 you are going to consider this upper approximation， because when we have。Have a function。

We evaluate。 we evaluate this function at this point。We have fear。The approximation。

We have a upper bound for the， for the ahore。This point here。Is F of x plus。This upper box。

We know this property。F of x， the value of the function。Is greater than approximation。

But it's less than or equal。To this schedule。You take this as an upper bond。Once again。

 because we give this a horse to the oracle， this upper bound。Okay， so we have an upper bound。

The lower bulb we may， we may minimize the cut model or just keep it fixed as in the previous algorithm。

The level parameter， you don't change the same rule to update the level parameter。This。

 the level set should be another X here not this one， so。Optimal the gap。

C our model is a lower approximation。 If you minimize here。

 we have a lower bound for the upper value。 So this， this gap is， in fact， a gap of optimality。

 although we are using wrong estimation for the upper bound， but they are upper bound。

 This is a lower bound。 So no problem。How we define。The level， the target。 There are many ways。

 One way is to make a convex combination between the lower， the upper bound。And the the level。

 for example， you have here the level parameter enter。We have。The best point we have。It can get。呃。

This target equal to the best value we have， or we can get something between these two。2 elements。

 It's not a problem。 And there are many ways to define。Here， I'm just defining this way。

 Itll bit simpler。And the idea is， we want to decrease the oracle ahore， a long iterative process。

 because eventually we want to get the optimal solution， exact solution。

 So we may decrease this ahore。In function as a function of the optimal gap。

So when you are decreasing the gap， you are decreasing your egoho。

 It means your oracle is going to be more expensive at the end。For some iterations。

Because there are some ones who don't care about the， the bond of on the， the day where。This is the。

 the same rule to define an exiter8。If you get the the， the algorithm， the one we started。

 we have only few changes to make。Oh instead of passing on x1 here， you pass also this bound。

And here you have defined this target because you don't have any candidate to be the a target。

 So you give plus infffinity。And the， the other thing， the other steps are the same way。

 except step 4。That。Before calling the oracle， we need to update the， the a on the oracle。

 the bound on the oracle a。The target。And then so that we can call the， the only amount oracle。

And we updateate the upper bound using as the same rule。And。Well， just few。Few steps。

That you perform in your old algorithmman。 you have a new one， but you have to code。

 you have to give more emphasis in the， in the oracle。

I have two problem thats those ideas I have just presented。How it works， well。Suppose initial point。

 you pass also this bound for the orac。Called the Oracle， compute that linearization。呃。

Just the level set in green。 and give up parameter diameter。And well。

 suppose that we pass this green line as the target。Remember， we give this point to the oracle。

 the oracle first makes a fast approximation using physical dual points and then starts to solve the sub problems。

 the LP。 once every at every LP you solve， you increase a bit dysfunction。



![](img/b3ee092578312ebc009a8cbd9b3be07d_41.png)

And this estimation， once you get up you are over this target， you stop your oracle。 say。

 don't spend much time computing something that I know is not good。Because， well。

 I would like to have a point with the value of the function lower than this target。 If it's up。

 I don't want to spend much time here。 I stop get thisization that we know that's lower。

 the lower type。We updatedd alpha parameter in the same rule that we have studied。We have， no。

 other level set。Call the orac again。This parametermeter here。

 I didn't mention once we are over the level。Here。Since we are over the the， the， the， the target。

 we don't know the who we are。 We don't have a bound for this。You just don't care about it。

 The theory， in the theory， we know that a bound exists， but you don't have any clue for that。Here。

When I was computing， evaluate the function at this point， this is the target。And。

The estimation that I got was here under the target， for this case。

I have satisfied this bond that I give。I give this to the the article。

And while algorithm works like that。And with just few chains。 and we saw and step 4。

 and they out them。To finalize。I want to show you some numerical experiments we have。

 This this is in a paper with Clauddium。And just to show you how this algorithm with all the amount curious oracles is faster。

Oh， so this is the， the problem we dealt with。We have 10 different problems。And for every problem。

 each problem will have considered 15 instances corresponding to those number of scenarios。Mmhm。😊，嗯哼。

No， no， wait。 The upper bound。 you don't know if it's under the target。The question was。

 when I know that。The upper bound is under the target。はい。No， no， this。

 this information we passed to the oracle。And the Oracle is going to compute something when it's over this target。

 we just stop this inside the Oracle。site。嗯。Like。No， you don't， you don't put this in the the set。

 You are going project。 You project， you give only the， the red part to the， the physical set。

 to the level set。We have an upper bound because you think that the upper bound is this guy。But no。

 it's， it's something here。But if I know。No， this target is always under the upper bound， because。

The way I did define here。Where。My define。The target here。's a convex combination between this two。

 So your question is not clear for me。

![](img/b3ee092578312ebc009a8cbd9b3be07d_43.png)

Oh。So we can talk later if。Well， just finalizer。I have here。In a total，150 problems。

 two stageto linear program problems。 So I solve。Those problem。

 we solved those problems with different algorithms。And for example， if you use the cutplan methods。

 the L shaped that you know very well to solve all those problems， we spent more than 7 hours。To so。

 more than 7 hours。If we use these ideas of on the amount cure inside the cut pain method， well。

 we reduce it in one hour。 It was already good。But if you consider this a left a bundle method。

 with on the amount that occurs。We drop the CPU time from 7。To two hours。

And this gave a CPU time reduction on percentage time。

Percent till CPU time is 72% of CPU time reduction。 That's what I wanted to show to， to say。And。

 well， these ideas of fundamental accuracy you can employ also with proximal bundle method and。

And they work more or less the same。 And we have more。You can read those a lot CPU time。

 combine these techniques。Exploiting your black box， your oracle。 That's the message of this class。

 You have to exploit your black box to accelerate the data that the the optimization process。

 When we start the optimization in general， we just assume we have a black box providing us the value of the function sub gradientdian。

 Now if it have more flexibility in this oracle， we can have。Gains in terms of CPU time。Well。

 this is the last slide。 So we are finishing with the basic course on stochastic program。

 So I'd like to thank you for attending for watching us。 And I have here called in Juan Paablo。

 I think they would like to say Chao。😊。

![](img/b3ee092578312ebc009a8cbd9b3be07d_45.png)

Mi克phone。Okay， thank you so。Just to say goodbye， we hope you have learned a little bit have got a flavor on what those subjects are and how many。

 many things can be done。 you were a little bit。 our guinea pigs because it was the first time we are getting the this course。

 We have been learning also， a lot。 So please send us feedback and questions。

 And let's keep in touch So well， goodbye。😊，The same thing it was very nice to。

 to have this opportunity to work with you。 Cla， I already said， a lot of the。😊，Lot of our feelings。

 Okay， so I don't know。不by嗯。😊，And maybe we are going to meet again in the future。

 next week certainly。😊，So see you ins from many of you。 bye。



![](img/b3ee092578312ebc009a8cbd9b3be07d_47.png)