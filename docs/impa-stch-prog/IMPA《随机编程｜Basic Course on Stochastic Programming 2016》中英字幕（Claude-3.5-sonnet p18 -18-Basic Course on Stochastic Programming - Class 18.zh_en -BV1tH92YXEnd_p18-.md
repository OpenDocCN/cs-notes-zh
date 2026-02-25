# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p18 -18-Basic Course on Stochastic Programming - Class 18.zh_en -BV1tH92YXEnd_p18-

Okay， guys， good afternoon。 Welcome to the Baa lecturec number 18。



![](img/51d7dbd527e455a90acb509fa63235ce_1.png)

Well， today， we are going to continue with。The the composition， do all the composition。

 It remained to prove a proposition at the end of the last class。 And then we move to another method。

 which is a well known method in non nonlinear optimization。

 that we apply this a tool for sastic stochastic programs， a stochastic program。

 which is a multiplier method。

![](img/51d7dbd527e455a90acb509fa63235ce_3.png)

Well， so two is start。I'm going to， to review our notation。Well， again。

 we are interested in the linear case， a multi stage locast linear。Problem。

So feasible set is a linear。And well， we can short this notation by defining the objective function in this way。

 which is the linear cost。 If we are feasible and plus infinitefin otherwise。We still。

Can short this notation。 Well， we will be based on a scenario 3 with finitely many scenarios。

 So the notation for the scenario， this class is K。



![](img/51d7dbd527e455a90acb509fa63235ce_5.png)

So capital O K is the number of scenarios。Well， the idea is， again， we are getting。

Putting together all the variables in a large vector。はい。嗯。

So we have the idea is we have here three scenario at three stage。And。For scenarios。The notation X。

Is equal to。1。To。3。2。3。Here。😔，Those are the decisions related to the first scenario。



![](img/51d7dbd527e455a90acb509fa63235ce_7.png)

Here， second scenario。And so， on。We are going to call the decision related to a scenario by X K。啊。

In this case， x1 related to the first scenario。That's an。And we we saw in last class well。

 we need to， to， to deal with non an， non anivity constraints。

We require those variables at the first stage。This should be equal to this one。ということです。오빠。

You go to this one。For in this case， this variable related the second stage first scenario。

Should be equal to the， the variable， the second stage。Second， second stage first scenario。

Should be equal to the， the variable at the second stage， second scenario。And those two。

Must coincide。For example。This is how we deal with， not how we deal with nonanceptivity。

 but just to saying that those variables should be equal and we modulate the nonanceptivity constraints as a linear constraint of the form。

G times x equal to。0。睇嘛。Just to recall。So today we have more students， the students from Argentina。

But and from San Carl， too。Well。We， we use this notation。So the。

 the dimension of that variable x is this one。啊。So F is measurable with respect to the sigma。

 where if the nonceptivity constraints are satisfied。

We can use this compact formulation to represent our multi stage stochastic program。No。

 I want to write that function here， too。F of x。Z equal to the sum。For all the scenarios。Oh。

 these steaks。Function evaluator at the stage T。セナルキ。Probably it's missing。YeahPro。

so this is the function you want to minimize subject to this constraint。 So you want to minimize。

F of x subject。Subject to this constraint。Okay。呃。So in the last class。

 we use the lagentian relaxation to define the dual de composition。So， we saw。By defining the。

 by using the lag， the problem can be split into scenarios。And at each scenario， we must to。



![](img/51d7dbd527e455a90acb509fa63235ce_9.png)

To solve a linear program problem， considering all these states from stage 1 up to。

Up to the last stage。 So in the total， we have。Capital K some problems to solve。 So the I。

 the idea is。We dualize this function。 We end up with the dual problem， which is。Maximize。

The of you U is we don't have constraint on you。This function。The of you。Is a sum。Over K。Okay。

And each every， every。Sub function here。 This is more this is other function is。



![](img/51d7dbd527e455a90acb509fa63235ce_11.png)

Theop value。Of from Ali。Gaohong。We solve what's。The， the， the property of。

That we can split this function。In a sum of functions， this is important because when。

Optimizing this dual problem。We will assume。An articleacle or a black box that。We define。

Are you a you a dual space。We sent this point to a black box。This black box needs to solve。

Its to compute。To solve a linear problem problem for scenario 1。

 So use all the information that scenario， solve。This。L里P。We need to solve for the other in。In fact。

 for everything。O， Jay。And well， we need to compute this。Here we some。And well。

 we need also a sub gradientient。 So this is the value of the function。 And when you solve。

This LP here， in fact， for a given U J。Well find a solution on X， that will depend。

On the U we gave because the U enter is here。So index this U by J。 So the solution of。

 a solution of that problem， I would call it。呃XT。Okay。J。Loation is not， not good。

Just to say that this is the premount solution for that stage T scenario K。

 but depending on this dual variable to the iteration process Jane here。 So for each one。

 we are going to have this。Here to。And。If you get all this vector。All those vectors， call it。The x。啊。

行。Depending on J。SoSo there is this relation。 We give。doout point， we solve all the LP。

 and you have this information。Okay， this， this large vector with this large vector。

This other vector here is a se gradient of this function。 You know that。G of J belongs to。嗯。

The superf。Of the。At the point。Uugene。Well。So， this is for。For each iteration of the solve。

 we are going to apply。To solve this dual problem。 So with the dual solution sent to this black box。

 we need to compute。All the， the solutions for the， opt value of the， those LED P。

 you have this vector We therefore have a sub gradient of the function。You can already see。You。

 you may see that this is a difficult task。 If you have a very large tree with many scenarios。

 So you have to solve many LP and not mention that this LP can be really large because we are taking account all the states。

So we have to solve many P， and those LEDP might be large。Must， I might have。High dimensions。

 The fact is。Well， this method， when you solve by the duo is interesting when this AliP is not so that large。

 Okay， you have a short ho horizon， and then we can use that。 And Efi or 3。

 scenario 3 is not so that very large。 So it's a restrictive method。嗯。

But we don't need other assumptions。 You don't need assumptions on on the， for example， how the， the。

 the arounddo， the stocast process is defined for you don't。

 don't need to assume stage wise independence。 So this can be。General， in fact。The function。

 the objective function can be nonlinear。 You can have nonlinear constraints here as long as you can solve this sub problem in a fast manner。

 So you can consider more general formulations here。 Okay， but the strong assumption is。

 you don't have so many scenarios and the whole the timing horizontal is not。Much big。

So this is one difficult。 But there is something interesting here。 For example。

 we can use parallel computing。For evaluating this function and a sub gradient。You can we give U J。

If you have K processors， you， you send you， you gave you one LP for each one of the processors。

 and you can compute at same time。And， well。

![](img/51d7dbd527e455a90acb509fa63235ce_13.png)

Another alternative， you can skip computing some of those LP or finding on a feasible solution for each one。

In this order。

![](img/51d7dbd527e455a90acb509fa63235ce_15.png)

In this， in this manner， the。The objective function， this value of the function will be in exact。

 if you don't solve this exactly， of course， this is inex。

 But there are no methods that can deal with this assumption。



![](img/51d7dbd527e455a90acb509fa63235ce_17.png)

And the interesting thing is that those matters dealing with inexness here and the evaluation。

 in in inexness in the black box。Have been exploited in the two stage case， not in the remote stage。

 For example。 I I I don't know a method dealing with for example。

 what we call on the amountda accuracy。 You give a and you compute those values we think that you provide。

 So there is smart methods that I think it haven't been applied to this context。

 So perhaps is now because this idea is odd。 But you now。

 we now have a more specialized methods to solve this dual problem。

 And you can combine some new ideas to try to， to solve the the problem in a faster manner。So。

If you are perhaps interested in doing some some work on stockto castastic optimization。

 you might be interested to verify this。 And if you want to talk to me later， you can discuss。



![](img/51d7dbd527e455a90acb509fa63235ce_19.png)

Well。But let， let's， let's stay with the simple， a very simple method that the 1 I。

I considered last class。 that is the sub， the cuttypa method。Well， we give。A dual variable。

 we call the oracle， have this information。The， this function is。Concave。

 because it's the wall function。 we can compute。A cutting plane， A a linearization for that function。

 for example， for a given you。You have this inequality。已有。あそな。Disneyequality is true。For。

All you because con because concad this is concave。So the idea is， if you gather a longer tradition。

 the， the teleative process。All those informations， this value the function， the sub gradientent。

 we can construct a cut planning model。And the cut planning model will be。Theminium。Of G。

Belonging to the F can be the first iteration second up to the last iteration。 I think I call it L。

So this is what we call。C plainium model， that's the maximum of those linearization minimum in this case。

And I think I name it。I love。Because it depends。On the number of iterations。

Mo of tradition will have performed。You。Okay。So the idea is this is concave。

 polyhedral because of our case。It's a linear problem。

So let's suppose that function D of U is like that。So， we give。A point。U of J， we call the black box。

 black box。Compute the value of the function。And oops， disanization is not okay。ですね。

Andal linearization。The next8 is given by。Belongs to the。Ag Max。But， of course。If you don't have。

 if the， if you don't， if you don't， we don't bound the feasible set。When we maximize。This line。

 we go to in。Plus infin。 So therefore， we need to bound。Minus m for x。You need bounce here。

An upper bond。 let's put in this。Suppose that yeah are here。Of course， we need to upper bound。

 We need to have a good estimates for those bounds。 Otherwise。

 we can cut cut off the solution of this problem。So when we maximize here on this set。

The other solution will be here。This will be J plus 1。Well， in fact， here is。L。Here will be。

Hel plus  one。Compute call the， the orac again， Comp the function。An other。Deneialization。

 the cut planning model now is this one。Ingram。that's the minimum of those linearizations。呃。

Note that now we don't need the bounds anymore。 If you maximize here。

 you're going to get the optimum here and this in inside the bounds。So the idea of the bounds。

Call here。It's very important， at the least， at the， the beginning of the interactiveerative process。

 because you don't want to escape to go to Pfin here with maximizing。



![](img/51d7dbd527e455a90acb509fa63235ce_21.png)

啊。Okay， we saw I'm just in the algorithm。 we saw last class。



![](img/51d7dbd527e455a90acb509fa63235ce_23.png)

What was the remaining to show The last class we also showed that the cutpen model， so far。

We have those ingredients， the cut pen model。

![](img/51d7dbd527e455a90acb509fa63235ce_25.png)

And the eachtation， we solve。This problem。Some bound。Yes。In general， the M。G。M is guessed。37。

I'm solving the wrong problem。 If I start with a wrong M， I'm solving the wrong problem。No。Well。

 let me see。If you look only at the maximization problem。1，1 indicative is the following。

 If you solve this problem。But using this bound。And that the solution。

 the solution of this the problem here with a bond。Let's think like that。You run an， you。

 you run an algorithm and you stop at a solution。 You want to see if that solution， indeed。

 for is in the interior of this set or not。 We just see。If it's the boundary of this set。

 you might be with a wrong decision， a wrong solution。 You should increase this N。

The idea is you are sure that you found the， the optimal solution， the dual solution。

 If the solution is the interior interior of this set。And makes sense。 that is a way of checking it。

But this is drawback of a cut planning method。 You have more efficient methods I'm going to discuss at little。

Last the classes of the， the course， I'm going to， to present you some specialized algorithms。

 and they run， they work。Using less assumptions， For example， this assumption here， we can get。

 get rid of it。

![](img/51d7dbd527e455a90acb509fa63235ce_27.png)

Well。I was telling that， well， based on this kpen model， and this is the iterative process。A cut。

 the cutplan method will converge， assume this exam is large enough。

 We will converse to an optimal solution of this problem here。

So this works because the cat method you have already analyzed the convergence， I think。

 at least twice。嗯。What was the remaining to show。Is。Once we solve this problem。

 we're solving the dualo。So if you are dealing with a particle problem。EWe solve the door。 You are。

 you are finding shadow prices because these have economic interpretation。 there's this variable。

But you， most of time， you are interested in a decision you have to make。 your planning decision。

And therefore， we need to find also an optimum solution。 We know that maximizing here。

 I will get the shadow price and。你吞饭去。But what about the primal decision， Well， we can compute it。

Helloatively。Is the way to compute this， this primmo solution。 Well， let's make some assumptions。

Let L。B， sing the counter in which the optimal solution is found， okay。



![](img/51d7dbd527e455a90acb509fa63235ce_29.png)

We also know the cut method to converse in。Fre。Fightally many iterations。

So let's assume that this is the last situation， but to converge。

And the solution we get for the dual problem is。In the interior of this set。 Okay。

 so we are not excluding the。This solution set。Indeed did this U is the solution of the。

Unconstrained to our problem。Now， we call。Alpha J。The lag multipliers related to this。S problem。

So when we solve this， we are getting theeration L U L plus 1。Okay。And this alpha J。

Theation multiplier of this constraint。Is is this clear？Well， because of this assumption。

 U is in the interior。 I can get rid of this constraint。And here， I'm just writing。这是你 quiet一。嗯。

So the problem is。you because I can get rid of the that bound。



![](img/51d7dbd527e455a90acb509fa63235ce_31.png)

This is equivalent。To maximize in U and R。R。But put this constraint。Okay。Same thing。

And now we use this definition。And we end up。With this formulation。

 just using the finish of the category model。呃。

![](img/51d7dbd527e455a90acb509fa63235ce_33.png)

So。The results saying that， if you get。Dislaation multily。Can you make this sum。

So this point is an optimal solution for the primmo program。So how we show this。

 We are going to show this result in two step。 First。

 we are going to show that this point is feasible， is's prim feasible。

And then we are going to show that the， the value of the function at this point is equal to the option value。

 And then we are done。Well， to， to show that the。That point， X is feasible。 X check is feasible。

We are going to use duality in。In our program。In our program。We can write this problem。S。Maximizing。

R。And I can use。Mus。Mus。J transpose。You help me if。我 it错。To prevent I make a mistake。

I'm just multiplying the right or hand side and bringing what is variable to the other side。

This should be equal to。Plus。Minus， in this case。Minus。Right， is that correct。This for。L G。Les。Then。

 or equal 2。Well， this is nothing but。Let's put this in。Ugly way， but just to。To be clear。

 we can write this like。In the sense。And here。The first。Constraint。Some播ing。Transpose here。

So it means that this is a vector。And here is the negative signalno。

And the last to coordinate is one。 I can do this。Of iteration。1。This is a matrix。That multiplies X R。

This should be。Less than or equal to。Dwaan。This is a LP。Now， we。We compute the dualo of this LP。

We see that the dul。Is。Minimize。The sum of these theorems。呃。

And the variable that is dual variable in this case， here is alpha。And here we use the transpose。

This will be。Mins。There's sum。I know。Okay。

![](img/51d7dbd527e455a90acb509fa63235ce_35.png)

Yeah。This should this part is equal to 0。And。This sum and J。Of J， if you sum。

 with respect these ones， we are going to put equal to one。This is the dual。 if you can。Well。

Let's folks， now。On this constraint。So this is saying。That。Some of J。Ziji。This is0。

But what's the definition of this vector G。Is the big my actress。With this， the prim solution。Okay。

 that was the definition。啊。呃。Now， this is a linear。 This is linear this is a matrix fact。Oh， this is。

Y。X， check our definition here。So， we have Sean。That X check is prim feasible。



![](img/51d7dbd527e455a90acb509fa63235ce_37.png)

Surprising and。I think you the honest thing surprise。呃。Okay。

 now we have to prove that the function evaluate at this point。Is， indeed。The optimalim value。That他。

To do that。We are going to use the cut planning definition。I we need this not。诶。They got playing。

Aiteration L。At this point。We know that。The optim value。Is this。



![](img/51d7dbd527e455a90acb509fa63235ce_39.png)

Because there is no gap of dual， dual gap。 there is no。And by the assumption of our proposition。

 this is equal to maximizing the model。Could you play a model。This is the assumption。

So this is equal。So they got play model。this point。Now， we are going to use。The cut model definition。

But for that， let's take。This set。Is it。The set off for Js。Such that。The cut plan model is active。

 is indeed。This one。What what is this set is when we are maximizing the plane mode。

So here's a minimum of of many。Have fine functions。 So if you are here。呃。Okay， let's do the。

 This is the function。 and the cut plane model is this one。Okay。And this is L plus 1。

 I want to get the index of the cuts， active。For example， this is active this。

 this part because it coincides with the function and well。



![](img/51d7dbd527e455a90acb509fa63235ce_41.png)

Here we are not touching this cut。So this is what I I say when the。

 the cut planning model coincides the point you give。Well。And if you continue here。

We can just say that。Zbar。Is。Yiguo。对。This term。This， for all。G。In this set。Okay。

 only for J in this sign。Well， now。With this function。This function。Is。啊。The sum。Okay， equal one。

Okay。Okay。But， I would say。Fact， this is。This function。At the optimal solution of the sub problems。嗯。

Okay。Bs。Why this。Because。D of U is the e the lag over x。 So we give U J， We find X J。And well。

 this is the lagation。It just什么？Okay。呃。Plusus。This vector， we know。That it is。Capital G。And now。

 this。Well， now this termm here， you can sell。Plus。Transposed G of。Okay， it's clear。看 must there。Now。

 I'm going to get all the， the indices in this set。 I use some。each side of this equality。

 But are you consider。D lag multipliers alpha。Because you know that they are known。Negative。

 and a sum。1。So， if you。Conttainer here。OfSome both sides of this equality。But for G。In this index。

 in this index set。Is equal。To the sun。Of G。I can just see。This is。And here。missy。嗯。诶。Well。

This part here this is convex。So， this is。This is by convexity。Okay， here is Lina。

J in that index set。So， but this is nothing but。And we know that at this point， is feasible。the X。

 X is feasible。X hot。So， this will be 0。So。X check is feasible。

 and the value of the function is less or equal。To them。Less or equal than the opt fair。

Less than or a week to this optimum value。 So it's feasible cannot be。This implies that。fact。

 we have。And this X hot X check。Is optimal。不毛。Solution。So in this way。

 we can recover primmorphfius ability。Well。We assumed that here， convexed of this function。

And it's true。But it's true。 also， for example， if you don't have a linear function here。

 you have a convex function， a linear convex function， we will work in the same way。

Our matrix is always， this is always a mattress because we are modeulating the constraints of nonceptivity。

And well， what else we need here。 that's it。2。Suppose that we are dealing with。

A stochastic program with mixed energy variables。You， you add more constraints here。

 saying some of those xs must be interge。Well， you can use the same idea as long as you assume that you can solve each one of those sub problems in an efficient manner。

And。But when you make this convex combination， I want to go back there。

When you make this convex combination。This point here， X had not necessarily。Is prim or feasible。

Because you are make a convex combination of interge point。 This not necessarily the inge。However。

 people use this method of in mixed interge s programs。To get a lower bound。

 because when you maximize the dual function。We get lower bound for the minimization problem。Because。

 you're not in convex to convex world anymore。 So you have a a gap of duality。

 You may have a gap of duality When you Ma maximise here。

 this value not necessarily coincides with the opt。But still， we have a lower bound。

 and this can be useful for branching brown strategies， okay。

I want to come back to this slide because I forgot to mention。This exercise。Here， we define the lag。

In this way。啊。Uucreideian inner product。I would like you to do the same math， but using。

This in their product here。 So they find the lagian function in this way。

Like we did in the beginning of last class。We are going to define another function， D of U。

And I' would like you to see it to， to show me how is， how you can， how is the。

How you define this function D and how you define the sub gradientient。

So it's just you change the inner product。 You change here。 It's like you have a different problem。

 The problem is the same， but a different way of solving the problem。 And the way you define。

 you define the inner product can impact the efficiency of the algorithm。

So I don't know if it this way would be better than define the way I def define it here。

 So I don't know if it's better。 It depends can be better for one case for one pro problem。

 but we cannot say this。In a general manner。呃。For example， one method that。

I'm not sure we are going to start， perhaps the last。

TheThe end of the course is the progressiveive heading。And for the progress you' heading。

 it's a mood stage stochastic program。And。It's defining it in one way。

 If you look at this method with another inner product。

 you get a very classical method in an linear program。So just a matter。

 if you change the inner product， you get another method for this field。

 So there you can play with these and。And see some relations between methods is already known in an elect literature tour。

So I hope I can show this at the end of the course。Okay。So now we know。

That we will solve in the dual。 We can get a primmo。Point， a prim solution。For free。

 so just do this convex combination。U。We already know also that the the， the。

 the the black box is expensive， but we can use parallel computing to try to。

To solve the problem in a more efficient manner。I have here some， some drawbacks。A。Not drawbacks。

 nothing sorry drawbacks， for example， requires solving one L personnel。

 This is good because we are decomposing the problem。 This is a good point。

It has hard to evaluate wall function。 That's true because you need to solve one LP for each scenario。

This variable U is， in general， very large。That's。It's a bad point。 And because you are so。啊。

Large dimensional problem。This， the composition has a low convergence。 Why that。Because at the end。

 we are the， the， the heart of the duo the composition is a cutplan method。That will maximize。

I got the plane model at every。Ichieration， This is why it's low。 you may use。

More sophisticated methods for doing that。For example， the regularize at the composition in which。

We define。I eat it8。Like that， maximizing。They cutium model。For example。This case。

 this is the last date。And you can put here， I don't know。Prameter。So if you use the same machinery。

 but change this sub parameter。We have another method， which is called regularized decomposition。ウ古ら。

Nicely the composition。And。It's faster。It's faster。 You。

 the your sub sub problem to define the new it rate is a bit more expensive because instead of solving I LP。

 we are， we are solving our a Q P， but it pays off。 We are going to perform less its。

 So this is good is an alternative。呃。But anyway， theyre glad。The composition， we keep all the。

 the linearizations of this function。 We may drop some linearization because this can be we can have a large set large set of constraints。

 if you want to exclude in。Inactive cuts。So in this way。

 we have to use some techniques and then comes bundle method， for example。More efficient。Well。

These two methods are really， in fact， they regularized the composition is a particular case of a bundle methods。

Or we can also use in level。The composition。Is a sort of bundle method。

 This has been applied recently with very successful to two stage schastic programs。

 but it hasn't been applied to the mood stage case。

 So one possibility for those who are interested in doing research， perhaps is。

To try more efficient methods here to solve this whole problem。 Okay。

 and using what we call on the that cures。Which is。Your black box is not so that that way。

 it's is smarter。 You can skip solving some LP and get some fast information。 It's my， is smarter。

You， but you have to be。Able to deal with inexactness of the function sub gradientdient。

 So this is the level the compositionposition we found among the curious。Also。

 hasn't been tested in the mode stage case。Other topic to be investigated。So。

There is a room to improve。The matter we have just seen。So already a old map。

 I think was developed in the 80s， but since then。More。

More efficient methodss for non smooth optimization have been developed。But we。

 I think it's a good idea to try to combine now and see what happens。 Perhaps we can get more。

 I'm sure you can get more efficient methods。Well， I think is， this is what I have S said here。

 So alternatives to， to this decomposition Re decomposition augmented like method plus not azure carbon method。

 This is what we are going to see now。 Okay， you've passed quickly。Talking about this subject。

This is also old。 at the first glance， we are going to see a very。Drawback。

 But then there is a way to overcome the drawback we are going to see。

Sometimes it's interesting in this method。I to left the composition。And another thing is。

I'm anticipating what I should say at the end， but let me see。This is also old method。 Okay。

 augment metalag is a classic method for on optimization。

 But plus this for most stage saastic programs is relatively old， I think， was developed in the 80s。

But。The idea is now， the community of。Machine learning have developed many efficient methods to deal with large scale optimization。

And well， I think it's also interesting。 If you take a close look to this new method in machine learning to try to combine here。

 and I will show exactly where to combine。And perhaps I'm sure also we are going to get better。

 more efficient methods。And that well。I look forward to， to attending the course。

 we are going to have the mini course。 we are going to have next。😊。

Week about stochastic convex optimization， apply to machine， machine learning。So I'm。

 I'm curious because we can。 So I invite you to pay attention to the， the the course。

 Perhaps you can find some very efficient methods that you can combine here。 But first， I need to。

 to show you， what's the idea。Well。The augment aggression method。thinkEverybody knows。Well。

 I'm going to consider a parameter， a pen coefficient。

And the augmented lag is the lag plus the penalization of infeibility， in this case。呃， no。

Constraints， we are penalizing。my， it's just that。で。

Multiply a method to apply to a multi stage stochastic program is the phone。

Soization in initialization as usual。 So our iteration here is L。So， prim update。We find。

We'll give you again。We give value。And minimize。This function over x。So here is the first。

 is the main drawback of the program。When you minimize the augmental agion。We have this term。

That doesn't allow us， doesn't allow us to decompose into scenarios。 Remember。

 when you don't have the quadratic term， then we can decompose into scenarios。But here， we cannot。

Later on， we will see how to overcome this drawback。But suppose we can solve this。

Suppose we can solve for now。So we give you minimize the augmental aggress。

 You have a primmo candidate。We stop the method when。This point X is near to feasibility。The Du it。

 the dual iterate is simple like that。 Well， we saw that this is a sub gradient for the。

 the lag function for the dual function fact。You do this you perform this apiating rule。Simple。

And we rotate。 and it was cycle this is。This is the multipier method。Nothing new。

We assume that this the dual problem has a solution。

 the Primo has because we are dealing with the linear case。Then， the sequence。

UL generated by the method， finds up finds an optimal solution of the dual problem finite many traditions。

This is the， the result。We are going to show。呃，不。In fact， here is the pure multiplier method。

 There is nothing different here。 We are not exploiting the structure of multi stage sachastic problems。

So， of course， the method will work。呃。I would like to。

Perhaps I not conclude the proof of this theorem， but I would like to give you an idea how it works。

But to show that。We've used the theory of proximal method， proximal method。

So we are going to study the proximal method and see that the proximal method is related to this one。

 And then we are done。Ups I'm not to show you all the details。

 but it what's the proximal point method。

![](img/51d7dbd527e455a90acb509fa63235ce_43.png)

see the proximal point method for those I think most of you know， if you don't know。

It's simple like that。We have a parameter， hole。And that the each iteration， the next it is obtain。

 Obtained by minimizing。 we are here in a different context。 Let me tell this function is convex。

 the method works finds a stationary point when this function is not convex。

 But let's focus in the user case。 F is convex。The domain is an non emptyy。

And we are interested in minimizing this function this is unconstrained optimization program。

The proximal method defines each iteration by minimizing the function。Plus。

 this quadraact term centralizes in the previous it。 It's more less like that。

So now I don't need this。If you have a convex function。You want to minimize a this convex function。

 So for example， we start with a point。Why。Wan。And then here it's like we are minimizing。This is fun。

 This is。F。This is。Fine。Plus。Okay we are minimizing。This ausliar function。



![](img/51d7dbd527e455a90acb509fa63235ce_45.png)

Oh， so did few minimum my eyes here。The next city to eight。Itll be this one。 and then we change。

The center。I minimize again。And so one up two， you arrive at the the optimum。

 This is how the method works。And。Let's make the phone assumptions。 The problem has optimal solution。

And this sequence。 So the sequence generatedated by the method。

Converse to an optimal solution of this problem。 The the entire sequence converses to an optimal solution of that problem。

Furthermore， if the function phi is polyhedro。Then the convergence is finite。

 So finitely after finite meditationits。We find an optimal solution。Well。

 the analysis of this method is not complicated。So let's see how it this theium。

How you prove this theory end？Let's assume。Let's assume the。Why star。Is an optimal solution。

For that minimization problem。So， in particular。那O。Just assume that。F。Then I you use this。呃。

Lierative process。As assume says that necessary condition is 0， belongs to the sub gradient。

Of five function。And。Y L plus  one。Plus。H。😔，Is this correct？Y L plus ones。

The solution is this solution of this problem， because strongly convex， the solution is unique。



![](img/51d7dbd527e455a90acb509fa63235ce_47.png)

Then， the necessary。To mild condition， and in this case， sufficient is this one。So， this is insane。

This is saying that。us4。By-1 I am。Belongs。To the switch financial。Of this function。F。Okay。

We are convexity of a function file。Now， I use this。Optimal solution。啊。team。Things like that。

Now I use the sub gradientdient。And。This point， minus this。This is true， right。 convexity。

 This is subgraity and inequality。So we didn。Inequality。A。So， lets me。Caed with。Can just see。Yeah。

Just say that。Hu。This there。Mus this。And。So since we assume this point is the opt is an optimal solution。

Theres inequality。No。We are going to use。Identity for this term and this identity。

 I don't know by heart。But I have。I have taken note of this identity I' going to use。

Is the following one。So let's stop here for a while。And let's use。Disidentity。So cl norm。Lets do。

Bund of。Minus。So this this is true。You can check it， if you want。The fact here。Well， we can。

So this is no negative sub subtracting。If I remove this term。I bootss。This one。Now。

 I want to arrive at this。In fact， here I can。We can delete that。Because this who is not negative。

 is strictly positive。No， I want to。See what happens。 We have something similar here。31 plus1 minus。

Okay the opposite。So I will bring this term here。I like that。This is。Less than or equal to。

O dismiss missing啊。2。Now you're combining with this。So， we combine。The two。We are going to get。诶。

Okay， now。With sum over L。Both sides。L equal to one。So we finish it。So it's the same thing here。Well。

 here we are going to have。嗯。When L is1。This。2嗯。This will be。Check， please， if it's right。

Minus limit。Is L。Going to infinitefin。This is。Right。This is not negative。

You can just erase this part。Then equal still holds。 So it's saying that this sum。It's finite。So。

 this is。Showing that。Limit。He's the optim effect。Oh， yeah。So it's comes。

The value of the functional converses， in fact， any cluster point of this。

Sequence is an optimal solution。 This is what we have shown。Now。

 choose any arbitrary cluster point of this sequence， say。Why tilted。Replace y， y tilt。Here。

Which is also a solution。 And you do the math again。

 we are going to conclude that the entire sequence converses。To a solution。Not a cluster point。

 a cluster。 There is only one cluster point。 So the whole sequence converse solution。In fact。

 this is what happened。Okay， so we have shown this first part。



![](img/51d7dbd527e455a90acb509fa63235ce_49.png)

And the other part is nice because all the time I， I， I said about that about。finite conversions。

But I've never put oven。I't never approved it。 Now， here， it easier to prove that indeed。

 we have finite convergence， and we're going to use this result for the multiplier method。1。

You have any clue why this。

![](img/51d7dbd527e455a90acb509fa63235ce_51.png)

Why we have finite conversions if you are in the polyhedro case。The idea is， if。

 the flux is polyhedro， the number of should be differentials。The numbers is finite finite。嗯。And。

Well， no， let let， yeah， that， that's the。The key point， but how can use that？

You have to prove by contradiction。Suppose。You know that the number。And of。



![](img/51d7dbd527e455a90acb509fa63235ce_53.png)

Different。Different subgra， subdi。Because Phi is polyhedral。呃。By contradiction。

Let's prove this by contradiction。 Let's assume。Let's assume thats 0。Doesn't belong。

To the sew differential of Phi。At the point。Y L plus one。This for。On end。嗯。So， in particular。

0 doesn't belong。To the union。Each one of these set function is convex。 Each one of these set is。

Convex，2。And close it。It means that the union is， at least closed。Right， the Union of Close convex。

 our co closet set is close。Oops。Doesn't belong。So if a 0 doesn't belong， wait。

 I think I'm missing something here。This is。The fact that this is close。

 we can separate 0 from this closed set。 So there is this。A龙。Stly strictly positive， such。That。0，1。

 wait。 I most。Let me remember what I did。m。Okay， yeah。嗯。Is that true。 Am I， Am I wrong。ConConable。

 yes。Contable union is closed because this case is's countable because it's。You have different。Am I。

 am I wrong。Yeah， okay。 thank you for pointing out。 So， so why this is is closed。

 I just thought of that。You know of， yeah。So how we can ensure that this is closed。Because it's。

It's finite。 if we get， if we have finite。Number of close sets。 and the issue。No， it's not correct。

F it。 the union of finite close set is closed。So we， this is what we need。

Because we have only different men。sets here。Although there is an infinity here， but we have。

 in fact， finite different sets。Okay。No， you can think of a polyhedro function。

So think of a polyhedro function like that。啊。Is the maximum？Of a fine functions here。And， but。

A finite set here。 finite set。Okay。So the artificial of this function。At x。Is。

The convex set of the points in which it's active this maximum。 So the convex。I should put here。

I don't know。呃。And， for example。And here is the convex。葫芦丝。This points。

But Jay belong to the active sets here。And we have。The number of active。Indexes here。Is finite。

 You can have only2 to the power of n plus1 or-1 here。 I don't know， but it's finite。Okay。

 so the number of two differential finite doesn't matter the x。Okay。So let someone help me here。

 So we have a union of Fly Man。Csed set。 So this is closed， right？ So we are right now。 Okay。

 thank you for。For pointing this out。 So this is。Close it so you can separate 0 from that set。

In this case， you have。Apsilon。This inter intersection。Is empathy。For all。In this case。Okay。

 the intersection。Is empty。However。Remember that。The sequence。通verse。So to an optimal solution。呃。So。

 this。Don't know where I wrote。So this goes to0。But。So it means that whole。0ero。But this。

Belongs to the。They function， superial。Well。Indeed， we are approaching0。 This is not possible。嗯。

We don't have a fixed a。 This is true for all L。 No， it's not true。Because this is a solid。

And it's going to zero。So this shows that we， after。For Italy many its。This intersection。Is。

Different。From empt。 So after finitely many steps。We stop the algorithm。 We are。

 We are in the optimum。Okay。Well。Now， we come back。So the。Vultiply your method。 How we prove。

That it converts。Its just to show。 We need just to show。That they iterate。

Ittererative process of the multiplier method。Is related to the proximal point algorithm in the sense。

This is。Let me see。这个。So we just need to show。Show that。To multiply a method。I。一工。2。

This proximal it is。Pximal point。Al really thing。Applied to this rub。Hu。This is。And plus one。

And is for all L。So。I leave this as an exercise。Get the disiterative process。

Work on this and show that this derivativeative process。Coin size。With this iterative process。

But this is the proximal point method applied to。To the function。Minus d of U。 So we have the， the。

 the theorem here， the， the result。So we just need to show work out on。

This is in this on these A B items， A B， and show that coincide with this。 Okay。

 I'll leave this as a exercise。Well。Still have some more meals。

Let's go to the part of our main interest here。Well， as I said， the main。Well。

 disadvantage of the method is minimizing this problem。

 Here we are gathering all the variables you don't。They compose this problem。A good point is。

 the method is simple。In general， it requires less iterations than the do all decom。

 Its because we are regularizing here。 So we are going to have less iterations。 For example， here。

 we don't have to use the bounds。It's also an advantage。The， the bad point is step a。

That you cannot decompose， if you。Give more details on this on this minimization study problem。

 This is the problem we have to solve。 So in this case， the。You可见 norm。

Is couplingling other the variables。And what was the proposal。In the 80s， I think。Was the fallen。

You give you， we have to minimize this problem。Let's minimize this problem iteratively。 in the sense。

 fix some variables and minimize in another set of variables。It's like the jab method for solving。

 Well， when we do calculus， we want to solve a linear system。We can solve this using the jacb method。

 which is。You fix all the other variables and you make it you one single variable。

 And then you are going to， to vary this， this direct process is the same thing here。

 We fix some variables and optimize。No block。And， well。

I have here some more notation to make things even more complicated。TheNotation is complicated。

 The idea is not。But there' is no way out。This is the problem we want to solve， solve。

Think now for the moment that we give always we give this U L。

 but think concentrate now only the sub problem， you are going to deal only with the sub problem。

 what we can do。呃。Well， let's see。 Let's suppose we have。It's given this point。

 as I say the first guess you have for the， the， the the solution。And here。For one block。

 in this case， we are minimizing in the scenario。So we think a scenario。Minimizing the scenario。

And therefore， I remove here the sum over K。 remove the sum over K。 just focusing on the one part。

I can remove the sum of overque here， but I cannot。In this part， what I we do。

 fix all the other variables for the other scenarios and let free only the scenario one you are dealing with。

Okay。And， well， we fix for the other scenarios。 just let this。下吧。Let me see， perhaps。Yeah。

Should be here。It did， thank you。It， it's wrong there， yeah。Well。Here。So did， they look get the。

 the idea。 you fix the variables for all the scenarios and focus in one scenario only。

 and you optimize when you optimize， you get this， well， for the， for the x or that scenario。

 for that subation only for solving this sub problem。And you do this for all scenarios。 F one solve。

 then fix the other solve fix and so1。When you have。All those points。For the scenarios。

 we make this update date。 We combine with the previous one。And you get this new X field。

And this the next ex enters here again， and repeat the process。It's， it's a jaov math。

 If you think in an linear system is， the idea is exactly the same。And。In this way。

 we can decompose decompose because we are going to solve is smaller sub problems， however。

The sub problems are not LEP， but Q P。 And you have a colourette term。 So this is more expensive。

And it's not only more expensive， because of that。Remember， do other composition。

 You send a U and solve K L E P Here， we send a U， and you have to solve。K Q Ps for the same。

 for the one sub iteration。 Then you have to repeat that。 while this is。Fix it。

 So it's much more expensive it it here。However， the number of iterations in U is smaller。

For some case， this。Well， what I think is in this， this method， in general， it works。

Better than the the composition， the sa the composition。 However， this process here。Is out to date。

 This is old style。 And the fact I the thing I told you about machine learning is in that community。

 They have much more efficient algorithms to solve this。 So big problem。

 You can split and not in this a naive form。 They have more efficient。 And this is。I。

 I would like to learn。 So I'm going to attend the mini course next week。 I will Im going to learn。

 and I would think I will be thinking about this problem。

 Perhaps you can find better tools to accelerate。This minimization process， okay。Well。

 I'm just finishing。I just want to， to show that， in fact。

 you think that you have many couplingling variables in this quadact term。 But in fact。

 we are just couplingling three variables。So if you have。Sn 3。If you are dealing with this scenario。

We are just couplinging this scenario if this one and that one。So dealing with this。

 you are couplingling on these three。 So the number of variables you are couplingling here is not that much。

 And this is the， we can exploit to try to accelerate。This minimization problem。呃。Okay。

 I think that's it。its is shown in this book。 I'm not going to prove this。It's very technical result。

 but it's。It's proven that if you make a loop here。We are going eventually。

 we are going to solve the sub problem。 And if you fix some variables and minimize only for one center。

 if you do this in Italy many times， in eventually。

 you will be solving the sub problem you want to solve to compute。On the。

 the minimum of the augmented log。So then method。In fact， it works。And this。Well。

 this results just give me the head。 If you are interested， you can go take this book and check them。

 So do you have questions。

![](img/51d7dbd527e455a90acb509fa63235ce_55.png)

so I finished this class。