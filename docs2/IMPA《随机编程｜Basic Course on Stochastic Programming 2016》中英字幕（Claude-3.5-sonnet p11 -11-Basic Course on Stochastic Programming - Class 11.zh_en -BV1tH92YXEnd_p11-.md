# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p11 -11-Basic Course on Stochastic Programming - Class 11.zh_en -BV1tH92YXEnd_p11-

Okay， hellello， everybody。 welcomecome to the tense lecture of our course on basics stochastic programming。

Today， we will continue our quest for a a good recipe。For solving no smooth problems。

 And we particularize the algorithms we will study for the case of。

to stage stochastic linear programs that were when written as records with a record formulation that these well the。

 the basic。Model the and most useful model for this for two stage optimization in this setting。Okay。

 so as usual， resolution should be good enough。And recall that with with Sul last class last week。

 sub gradient methodss that are not good。 They are easy to implement， but they are not good for。



![](img/e7e5790610044bfa7bfaecc826dde820_1.png)

Implementations， unless well， you are satisfied with relatively。



![](img/e7e5790610044bfa7bfaecc826dde820_3.png)

Inaccurate solutions。 let's say， in some cases， it makes sense in combinatory optimization。

 but not in this setting。 So we have we will consider now the case of minimizing a convex function over a compact polyhedrum。

 It's a convex set capital X。 So it corresponds well to our two stage stochastic linear program。

And we don't know F in an explicit manner。 That is not a formula for evaluating F at any point。

 but instead。We have available what we call an oracle。 The oracle provides for each iterate X I。

 the value of the function and one sub gradientdient， only one and no more。

 And with this information， we can define a linearization for our convex function。

 it is so this is a function value at X I。 this is the one sub gradientdient at X I。 And so at X I。

 the this linearization is tangent to f。 And then it is stays below of the function。

 This linearization because F is convex。 And the maximum of all those cut in planes that are called those linearization is still a convex function that also supports the graph of the F from below。

 And since it is a model。 we call it M。And this is something that we can compute because it's using the information that we assume it's available。

1 the functional value and one sub gradientient that each iterate。Okay， so。

 and we prove that ititeration will include more and more of such linearizations。In particular。

 then theeration on K plus1， this is the definition of the K plus K plus ones model。

 Then it is a maximum of the current model and the last linear session。And you see in particular。

 then that as K increases， the model becomes more and more tight and and closer to the function。Okay。

 and X K plus1。 How do we introduce new pieces into our piece wise a fine function， a fine model。

Well， we just set of mini in F。 We minimize the model。 And then this gives us the next eater， right。

And this is called the cutting place myself。😊，So， as I said， instead of。Solving in one shot。

 this problem。 This is what we are interested in solving finding one solution of this minimization problem。

 Since we don't know F。 instead of doing that， we minimize iteratively a model that we will be improving。

😊，And then。The piece for provided by the last minimizer here of the model K。 And then we we loop。

So this is called the cat compliance method。And if the convex said， the the fact that x。

 the the set capital x is assumed to be compact， it's important。



![](img/e7e5790610044bfa7bfaecc826dde820_5.png)

Because if it is not compact， you can see what happens in the beginning of the iterations until we manage to get an approximation that。



![](img/e7e5790610044bfa7bfaecc826dde820_7.png)

It has。Like two sides So if it is only we have make approximation from one side。

 we will have a model， for example， in the first iteration， This is our first model。 This is x1。

 We call the oracle。 We get the F1 at G1。 We define this。 I fine hyperplane or the cutting planee。

 And then if we minimize this over a said that is not compact It may what happen that we go to minus infinity。



![](img/e7e5790610044bfa7bfaecc826dde820_9.png)

So for the problem， for the method to be well defined。

 we need the minimization to be carried on on a set that is compact。 If the set is not compact。

 then it has to be intersected with some box that is big enough for us to believe that inside of the box there is a minir。

 It has to be bounded。

![](img/e7e5790610044bfa7bfaecc826dde820_11.png)

![](img/e7e5790610044bfa7bfaecc826dde820_12.png)

Okay， but in our case， what we will do is we will assume that our set capital x that in the two states setting。

 capital x was of the form。

![](img/e7e5790610044bfa7bfaecc826dde820_14.png)

X in R N。So' that A X。Equal B and x。Leer than 0。 So we will assume that this is a compact set。

 This is， this will be a good assumption。 But you have to remember always to check that this is the case when you use it in an algorithm。

 because。

![](img/e7e5790610044bfa7bfaecc826dde820_16.png)

This problem may meize。Okay， so how this algorithm graphically， how。

 how can we see the progress of this method。 So we have the first iteration there。Now。

 then we minimize over this set。 Then the optimum will be here right next to。



![](img/e7e5790610044bfa7bfaecc826dde820_18.png)

![](img/e7e5790610044bfa7bfaecc826dde820_19.png)

This is x2。 Then we call the oracle， and the oracle gives us again the value of a function and a sub gradientient。

 and this defines this。😊。

![](img/e7e5790610044bfa7bfaecc826dde820_21.png)

Blue linearization。 The next model will be the maximum of the two。Of those two linearization。

 So you see， now we cross， we close it。 So we could dispense the set capital X if it was artificial。

 but here it is not。

![](img/e7e5790610044bfa7bfaecc826dde820_23.png)

Okay， so we get that right approximation。 This is M2。Women in IM 2， we obtain x3， we call the oracle。

 we obtain the blue line。Then again， we take the maximum of the red model and the blue line。

 This is M4。 No， yeah， now X K plus 1 is M3。

![](img/e7e5790610044bfa7bfaecc826dde820_25.png)

So this is a red。The rare modeled here。 piece wise are fine。We minimize again。 We obtain x4。

 We introduce the linear recession that we got from the call to the oracle。

 and then we get the tighter and tighter model， we get the red model again， we got， we minimize it。

 We get x 5。 and then again， we introduce it in a recession。 and we got the whole function。 by now。

 at least in the area of interest here。 No， but we don't care。 So and well。

 you see that if we minimize， sorry， let's go back。



![](img/e7e5790610044bfa7bfaecc826dde820_27.png)

It womenize now。

![](img/e7e5790610044bfa7bfaecc826dde820_29.png)

The maximum between the red model and the new linear session， that is this blue line。

 Then we are actually minimizing the function， at least in the area where we， the minimum is。

 and we will find the minimum。 that is here。 well find the our point X star。So， this is a goan。

A reliable method special in a situation here like here where the function F is piece Y a fine。

 You see， there are no round。Cbs here all the， the parts of this function F is R linear。 No our fine。

 actually。 So when we approach it by a fine pieces， eventually， we will be。Find， in fact。

 the model will coincide with the function。 Its well， its a kind of the idea situation。Okay。

 so it is good what these method has is is good about this method than the。

 that the successive of values of the model at the rate at the E rate。

 So we minimize M K over capital x to 10 X K plus 1。

 and this function value the model at the data rate increases。 So this was the first one。

 the model at X 2 M1 at X 2 M2 or x 3 M3 at x 4 and4 at x 5。 So it is monoton。

 and is increasing towards the minimum of f。😊。

![](img/e7e5790610044bfa7bfaecc826dde820_31.png)

So this is good， but this has something that is not good because it's a good recipe。

 but not the best one。

![](img/e7e5790610044bfa7bfaecc826dde820_33.png)

So what happens to the functional values。 We want to approximate， we want to minimize F。

 We are using the model is a proxy， something that we can build because we don't know F。

 So what happens here， as you can see is that。The sequence of functional values at successive iterates F of X 2。

 F of X 3， F of X 4 here we decreasing。 And it teach what we want to want to minimize the functions So we want to monotonically。

 ideally， monotongonically converse to a minimum。 But then here you see F of X 5。

Because this linearization at X 4 is very very horizontal because were close to the minimum。

 it takes us far。 And， in fact， it made our functional value increase。 So it is not moreton。 And。

 and this is the optimum。 And then we go back。 But well here we it was not too unsafe because we are in dimension 1。

 we don't have many pieces when we in our minds because it is not possible to right to draw the situation in in in higher dimensions。

 we will this kind of mono of oscillations between good functional values and bad ones。

 This is taking us closer to where we want to be。 And the next one takes us farther from where we want to go。

 This is bad from the converses point of view。 And it produces。

 So here we see that F of X 5 is larger than F of X 4。And we see that。

 and this type of phenomenal introduces oscillations that are bad from the numerical point of view。

Okay， so， but we have a stopping in test。 This is a great improvement over the subgient methods。

 We can measure the improvement。 It will not be。😊，It continues improvement monotonically。 so。

 but we will proven asytotically。 And this will be measure by computing the distance between。

 So we minimize minimize our model。 We get X 2。 We call the oracle。

 we get the value of the function at X 2。 And then since we optimize our problem。

 we know also the value of the model at X 2。 this distance。😊。



![](img/e7e5790610044bfa7bfaecc826dde820_35.png)

Is always non negative because the model is always below the function by convexity。

 So this is what we call like a predicted decrease。And。O then note here by Delta K。

 Delta 2 in this case。And it is non negative。 And you see， for example， here， it is smaller here。

 it is smaller here。 it is smaller。 It may not always be monotonically decreasing。

 but asymptotically， it turns to 0 because we are tightening more and more with more and more pieces。

 our model making it closer to the function。 So the distance becomes also smaller in the limit。

And this will be the stop in test。 We will stop。When our predicted decrease that K is smaller than a certain tolerance。

So when the value of the function that we come we can， we know this is， everything is implementable。

 This is what is good here。 We know it because we call the oracle。

 and we get this value function is in other parts， I wrote it， F K， not at X K， F super per K。😊。

And this is a model at the， at the optr。 And we also have is the optimal value of the problem that we solve to compute X K。

 So everything is computable。And this is good。 Yes， we have a question。it。

 we have a question about epsilon subgrads。嗯h。😊，おばち？嗯h。ESo the question is。

 if we could not make an an implementable stopping test。

 using epsilons of differential for the subgrading method。So the answer is no， because。

The subgradd methods do not remember what happened in past iterations for building the epsilon sub differential。

 you need to have memory of what the algorithm did in the previous iterations。And then with that。

 you create some convex hall。 And this is an approximation of the subdi that is actually sub differential at some point。

With the sub gradientdient methods。It's as if every point was the first point of your algorithm。

 It's you don't keep it in in memory。 If you keep kept it in memory。

 then you would not be advancing in the direction of the sub gradientdient。

 but you would be advancing in the direction of an epsilon sub gradientdient。

 And then it would be an epsilon sub gradientdient algorithm。

 And there you can And there you can yes， define the a stopping test based on the epsilon sub differential that has would con the properties as a multifunction。

 But the epsilon sub gradientient the sub gradientient algorithm。 No， it is this is what it is。

 It is forget what happened until now start from this point and advancing this direction。

 For what it you did then And then you go on and go on。 It is anesic。😊，Welcome。 So okay， so it。

 we have a stopping test here。 and this is good， so。😊，What is the or the， the method then。

 So in episode pseudo algorithm way， you have your first point。 It has to be capital X。 sorry。

 I didn't put。 but it's important that we remain in this bound。C set。

We initiate our iteration counters， and we define our first model as minus infinity。

Then we call the oracle， and we obtained the value of the function at the an sub gradient X K。

 and we build our current model as a maximum between what we had and the new linearization。 Okay。

 and this is why we put here minus infinity。 So that the first one is just the。

 the first linearization。😊，Then we minimize the model over our set， and we obtain the new iterate。

 and we set K equal K plus 1， and we loop。So it is a little bit more complicated than the surprises because。

For the subient method， we didn't have to solve an optimization problem here。

We just had X K plus  one equal X K plus D K， G K。Now。

 we have to make a little bit more involve calculations。

 And the good thing is that this gives us the stop in test。 So because so far here。😊。

As it was before here， without a stop in test。 Well。

 this is an algorithm that cannot be implemented because we don't know when to stop。

This is now an implement a let ago， the recipe。 and we have。This difference， the predicted decrease。

 It is the decrease that the model predicts。 That's why it's predicted， right it is。

Based on the information of the model。What is that we reduce the distance。

 how much we reduce the distance to the function。 That's why it's called predicted degrees。

 And then tall isn tolerance。 And then if we are below the tolerance， we stop。Okay。

 there are good properties for this method。 The first one is all this chain of inequalities。

That well， we can。 they are rather simple， so。Mk。呃。Is larger than the linearization at the point X K。

 This is the first one。 It's a maximum between the previous model and the linearization。

Because we take the maximum over the model and linearization。

A model with K plus plus 1 is larger than the model with index K。

 And because we are in a convex setting。We only have here inequ linearization of this type and the subient inequality holes for all the pieces that compose the model。

So in all cases， the subient inequality holds for all the pieces。 F I plus E I transpose X minus X I。

 This is smaller than F at x， right， Use the subent inequality definition of a sub sub gradientient。

 And then if we take the maximum， the inequality still holds。

 So all the models are staying below the function and they are increasing from below。😊，In particular。

 if we， for example， take here of this inequality and we minimize over capital x， what will happen。

The minimum over。A a capital x of M， K is M is at X K plus 1。

 This is a definition of the next eater rate。 So M。

 K at X K plus one is smaller than the minimum of the function at x。And we call it S bar x。Right。

 so it's taking minimum here and here。And while this is。

 this will be important for proving conversionence of the algorithm。

 because the sequence of values of the model。Along all the sequence that we generate will be bounded above。

 and it's growing。Ts a row。Because of this relation。This monoton。 we saw in the drawing also。

 that is monotton。Well， okay， so I was advancing myself。 I forgot that I had read it。

 So what happens。If we take consider here。 So M K at x plus 1。Is smaller。Then， a。Or M K plus1 at X。

 K plus 2。It's larger than N K at X K plus 2， right， We evaluate at the minimum here。But M。

 K at X K plus 2 is larger than M， K at X K plus 1， because X， K plus 1 is the minimum。

 I make a mathematical。Proofs we were talking today。So， this sequence。

Of the successive optimal values of our model is increasing。 is increasing。

 but it has a roof here That is F bar X。 and the convergence proof will be。 we will show that。

 in fact， it doesn't accumulate below before F bar X， but it goes all the way until F bar X。

 And data will right in the blackboard。 I will not talk about。Okay。

 another important property is that because we start with a feasible point that I didn't put here in in x。

 Well， and actually， it doesn't even matter now that I think what matters is that afterwards。

 we are always minimizing taking iterate that minimize the model over capital x。

 So our iterate is feasible for this problem。 So we remain in the set capital x that we assume to be bounded。

 is compact。 So the sequence is bounded。So there will be a sub sequenceequence that will be convergenant。

 and these will also will be using in our convergence proof。Okay。

 so these are our three properties that I will。I would write in the blackboard。To make our proof。都。

We have first。Maybe I would write it with x now to make it easier， not with the dot。This is for。

Exie next。And。Mk of x K plus 1。No， totally。 I know。 Yeah， Okay， it's no， no， okay。

 I to write that this F bar。え X。With。Its k。boundunded。嗯。The sequence。Of optimal values。Increasing。

Okay， so now we'll go and we'll have a next slide。 If I remember， well， sure， because I wrote it。

I know， okay， forgot。 Okay， not the next idea yet。So that is also an important consequence of staying in a bounded set is that。

A convex function like we are considering here。 F is sleepian， lipsian and is locallyly。

 And because of that， the sub differential is locally bounded。So since we are staying。

 all the sequence X K is stay in a set that is x， the diameter of the sub differentials of these sets。

Is also bounded。 There is a bound。Here there is where you can find the the proof of this result。

 But well， so not only the， the values ex the it rates is k are bounded， but the sub gradientds。

 all the sub gradientds that we will be using in our models can be bounded above by these uniform bound that doesn't depend on K。

 I mean， and。And no， yes。Now， we have our conversion theorem。We have a function。

That is defined on the reals。 It doesn't go on the extended reals。 It is convex。

 and the set where we are minimizing is convex and compact。 And suppose we take tolerance equal0。

 So we don't stop。 keep defining an infinite number of itererates。



![](img/e7e5790610044bfa7bfaecc826dde820_37.png)

And then the limit this I forgot here K that goes to infinity。 The result is。The values of the model。

 So of those optimal values of the excessive problems we solve to find iter rates。

Has a limit that is our optimal value that we are looking for。 And this is a number。 It's not a if。

 It's a mean， because x here is compact。And also， this optimal value coincides with the functional values with compute at the it age。

 but not the limit because it's a non one not sequence， but the limits of the records。

 the the elements the。If you at a T lit K， we take the smaller functional value。

This gives us the record at iteration K at the iteration K plus 1。

 we take the minimum of all the functional values at the T iteration K plus1。 And then this sequence。

 it's a sub sequenceequence。 then of the all the functional values that we have。

 This is what cons to the optimal value that we are looking for。 That's why here is the limits。😊。

Okay， so now we will make the proof of this of this result。 Okay， and then now how will come here。

Okay， so we have。

![](img/e7e5790610044bfa7bfaecc826dde820_39.png)

That our sequence of model values is monoton， and it has a roof that is bounded above by F bar x。

But we don't know if it accumulates and stops and converses before F bar X， right？

 what we need to prove is that indeed， the limit is F bar X。 It doesn't stop before。 So the， I mean。

 the comparisons。 So then this kind of proof we do by contradiction。 We suppose that there is。

 suppose。That there is some positive number。Such that。Mg。O x K that1。A smaller than F bar。X minus c。

For cat sufficiently large。 So we suppose that there existed positive C and some。Capital K。

 such that this inequality holds for。我。Okay。L改 done。And then we will obtain a contradiction。

 This is how we will make our proof。 So let me write the reverse inequality。

 F bar minus C is larger than。Okay。At X K plus1。And now we start using our properties。

 You have to reason with sub sequenceequences here because we know that the sequence X K is bounded。

 So we will take a convergt。Subsequence。Xk J， And here I will be moving in J。Okay， so now。

 let me think。What is it And I it is now。 it is convenient to write this inequality with k -1。

 So I will write it。So I will put -1 here and K here。So this is still true。 is our。

 is our assumption。 And we would consider this case， the subsequent， the K Js in our subsequent。

 So I will put the J。

![](img/e7e5790610044bfa7bfaecc826dde820_41.png)

No。嗯。So， this is also true。And now we start playing with our inequalities。嗯。

Because what I would want to have since I have a this subequence is convergent。

 I want to get a difference between X， K， J and X， K， J-1， the -1 here， not up here， like here。

So what would we do，The model。Are increasing as the index increases。

 So here we have because of this property。Here， let me call it。1。Apply enough time that。

This inequality holds with the -1。Okay。J。So now the -1 when the here went down。Okay， here goes up。

 Now we on。And this number is smaller than or or smaller or equal than K I -1。Good。

 so this is because of one。Right one。Okay， and now I will come here and use this inequality。

那 quality度。And I will write it a little smaller so that I don't have to。 let me move it by one。

Let me move it here。So that I don't get out from my area。So， M K J -1 at。X， K， Z。Okay。

 and this is larger than if I put。Here you see M K。

 the the the delineization is at the index of the model。

So this means that this is larger than F at K。AndJ。Mineos1。Blash。The gradient。K， J-1 transpose。X K。

 J minus。The point at which I called the oracle to create the linearization So x， K Z-1。Good。

 then now I have what I wanted because I have two successive itererates of my subsequent。

And then now， what do we use。 Remember here we have S bar x here。 we have。F at the point。

 And it's a point that belongs to the set capital x。 So this value is larger than。F by x。Okay。

This means that。So。Min- c。Is larger than。G， K， J，-1。Transpose。To little ugly notation。 but well you。

 you understand。Times X， K， J minus X， K。Z -1。And this is a conversion sequence。

Because now I'm moving in the subsequent cages of index K A。

So for some K Js of some J is sufficiently large。I can make the enormous this difference as small as I want。

嗯。So let me just now write。 this is 0。 I will multiply by -1 smaller than C smaller than again。

 the gradient K， J-1 transpose。 I will just change the order here。 K， J-1。Minus how to write nice Kz。

Okay。Okay， so now I apply take。 This is positive。 We applieds。 So we have。This is inequality。

And this is a sub gradientient。In name of。A point of a point that is in the bounded set。 So here。

 this norm can be bounded by this universal bound capital M。嗯。Well。

 then since this is a conver conversant sequence， I can take J sufficient。

 sufficiently large so that I can make this difference。Smaller than C。Divided。

 then they put I is smaller。And wonder。T C， divided by。2 M。You see where I want to be So for some。

For。Re。Sufficiently large。But then what happens。M， C to M。

 This is smaller or equal than than C divided by 2。So。EI got the contradiction。 And this is。

This is a contradiction。Because he's positive。So we conclude that the limit of。Of our here。

 the limit， sorry， the limit of our。Model values is indeed， F bar x。Now。

 we will make some similar reason for the second equality。你铁。

The would return again on a sub sequenceequ， and it will be more or less the same tricks。 So now。

 suppose so to show。

![](img/e7e5790610044bfa7bfaecc826dde820_43.png)

That。Lin。可以。すケ？Is F bar X。 So we are conversging。 Now we are coming from the other side， right。

 with functional values with the models。 So we have。This is f bar x。

 the model values we come from below。We are conversion here。Now， with the functional values。

 we are conversging in a non monotton way。Its from this side or F of it K。

So the contradiction will be， instead of here， putting minus C is saying that suppose。



![](img/e7e5790610044bfa7bfaecc826dde820_45.png)

That exists the positive C。Such that。F， ofk。J a sub sequence。

 we take the sub sequenceequ for which that makes the limit。So， if。

X of K J is larger than f by x plus C。And we will know again。

Play with inequalities to obtain the contradiction。So to play our inequality with inequalities。

 we reverse the control again。 So we have a bar。X is but x plus E is smaller than。Let me hear。

I raise my drawing then then。F of x。Kジ。Okay， and I think here。

 what is convenient is to let me see my column。Yeah， will。跟。To our inequality here。This inequality。

 too。And we will evaluate at the point where we are taking the linearization。This means that M。

 K at X， K is larger than F K。So， FK is smaller。T the model at the same point at the same ether right。

 So this is smaller than。M， K， Z。At x， K。瑞。And this is by what was the name。杜。嗯。Okay。

 and now we will add and subtract。Something that here they has K J-1。

 because we want to have the difference between two points of the sub sequenceequ。

 So this is the same。Then。M K J at x。Okay。J， minus M， K， J。At XK。Z -1。Plus， the same thing。Okay。

 is a minus1。Good。So now we have the difference of in the model at two points。

 This is a piecewise linear model。 It is lipsit。And the lips is constant。 It's given by the same M。

 in fact， which is a lips is constant of the function F in the set capital X， the global。

Lihich is constant， so。Because the model is slipes。The models areipses。Moothers。Moels。

Our lipses continues。And because actually it May， the model is made up of pieces created with values of x and gradients of x。

 It is the same which is constant than， and the， the universal constant of the sub gradientdients。

 It's all the same with mods。Is a name rather than constant， maybe moduluous。And。

So here we compound the absolute value by M times the difference of the to points。

 And what happens here this term。Remember。So it's a model。So， sorry， it's the。

It is a model at some point。 and the model is all always stay below the function value。 And actually。

 because of the monotononicity， again， of the models。Okay， let's。

 I wanna do all the steps at the same time。 Let me， let me go p step by step。 So first， we have， we。

 we keep our inequalities here that our difference， where we will apply lips is continuity。Blash。Now。

 X K z plus 1，-1 was generateder at the model。呃。M K。Is I minus-1？-1。嗯。我婚。Well。

So because of this inequality here， because of this。So is inequality here。Make in the same and again。

 this is smaller。Thenhan x bar x。So， again。F x。And again。

 then we have0 is smaller than C is smaller than。M， the norm of X X， Kz。Mus。X， K， Z，-1。

And taking J sufficient sufficiently large things is smaller than。

MC divided by 2 M equal C divided by 2 for。They sufficiently not。And again。

 we obtain a contradiction。Good， and this finishes then our probe。 It is the same。

 the same type of argument you see in the two。 And for that， it is fundamental。That they said。

Cital X is bounded。 This is really the basis of all the reasoning， because it's a way of obtaining。

Converence subence subequs and a global lips is bound。Okay， but remember that in our。In our setting。

 the function F is not only complex， but this polyhedra。So， the sub differential。

It is the convex hall of some vertices。 Remember that we， we we showed this。And actually。

 if here is piecewise assign s because it is in the is not it doesn't take plus infinite values。

 And this corresponds to the setting where in stochastic linear programming。

 We are assuming that there is record， the records is relatively complete。

 We always have that the records function has finite value。Okay， so what happens in this case。Well。

 in this case happens what we saw in the picture。 not only the algorithm converses， that convers。

 but， in fact， it stops。 It has finite termination。 After a number of iterations， it will。

 we will have Delta K equal to 0 because the model will coincide with the。With the function。 And。

 but this， for this， for this result， we， for this to happen。

 we need one assumption on which kind of subgrading comes from the oracle。So。Here。

 they sub differential。 So we said that the oracle gives us something that it is a subdi gradient。

 but we don't make an assumption。 What here we make an assumption。 it is。 It gives us。



![](img/e7e5790610044bfa7bfaecc826dde820_47.png)

Subgrades that are only those vertices， not con combinations。For example。

 if it was for the absolute value function。At 0， the orac code should give us if we send 0。

Then the oracle which give us f of 0 equals 0。 and then it will give us either-1 or  one。

 Nothing in between。Okay， it's one of the two pieces that define the max function the。

Absolute value function is a maximum between x and minus x。So， either。1 or。M-1。And in this case， yes。

 we will have a finite termination because there is only a finite number of， of。

Of point that we can get from the， from the oracle。If the oracle was to give us something in between。

 it can give us any possible alpha between -1 and1。 And then it's an infinite number。

 And then we will have all those。 remember that drawing where we have all the possible。I find pieces。

 Well， my drawings are better when I make them in the computer。

 So we had the absolute value function。I is serum。And then。OrAnying。Between here。Here。

Any a fine plane， a fine， any linearization in these two in these two regions would be a possible linearization。

 And it's an infinite number。 Then if we call the oracle and the oracle1 times third give us an alpha any any alpha between-1。

-1 and one， then would get all these。 It's an infinite number， we will not stop。

 it will not be possible because or would have all those。



![](img/e7e5790610044bfa7bfaecc826dde820_49.png)

All those combinations。This is not a restrictive con consideration of assumption for our setting of stochastic linear programming。

 because， in fact， remember that for our， in our setting。

 what is polyheedra is the expected records function C C is made up is wave sum of the records functions Q at C S at each scenario。

And each of those functions has a sub differential。 That is the the P。 they， they they。

 they do all variables that sort they dual formulation。

So how is it that we can obtain where this is when we solve a linear programming problem。

 which is what we are doing in our in， in the stochastic setting。

We have to use a method that is not an interior point method。 If we use a simplex method。

 it will give us basic solutions， basic points and the basic the simplex method。

 it goes through the vertices， right， The solutions of vertices are not edges。

 And this is what we don't want。 We don't want edges。

 we want only the vertices of the sub differential。 And in that case。

 then the method will have finite termination。Now。There is something that is interesting here in consideration。

 because in。In when we have a large scale problems， actually。

 interior point methods may better in the primal dual form maybe better as a solver of a linear programming problem。

 And then you could start thinking， but I will not have a finite termination because it will give me some point in between what I do。

 Well， the truth is that nobody cares I would finite termination when you have a large a large problem because well。

 you want to know that you are using a convert algorithm。

 this will still be true because all these holds independently of any assumption of the oracle。

 or if a function is quite， It's enough for it to become conve。

 So the method will be con will be convergenent。E if you were to use a simple method。

 nothing guarantees that because you are only getting vertices as solutions from the rawacle。

Even in the case， when F is polyhedral， that the termination。

 the finite termination will be activated before you die。 This is what happens。 There are too many。

 too many variables。 So， well， it is interesting to know that， well。

 this is potentially an advantage of simplex methods over interior point methods for solving these type of problems。

 But well， probably is more true for finite for low dimensions。 We have a question。😊，These。でそ。的定数。

So the question is that an example where the， the limb soup of the functional values is not equal to the limb of the of these functional values。

 It is practically any function that you would minimize because it's not in this not mono notton。

 So you see in the if you look， look at the drawing here。 Well we have only。

 we don't have enough points in our drawing that you see you can。

 you can create examples where you have these。

![](img/e7e5790610044bfa7bfaecc826dde820_51.png)

This situation。 And then， well， these may this may not you can。 I don't have it in mind now。 Okay。

 but because it is not monotton， you can create an example where you are in a。

 in a in a co corner like this and where you have always you are coming at the same functional values from one side on the other。

 at some itererates。 And then at the， some others， you are going down。 You see， something like this。

 Well I has to be shot in on the paper。 But this is how I will look for it。



![](img/e7e5790610044bfa7bfaecc826dde820_53.png)

So maybe you can look for it and then on Thursday， you can tell me。Yeah， good。

 I will also look for it in some when I'm。In a traffic jam， we will think of this。It happens often。

 So I will be thinking often at that problem。Okay， so in general。

 cutting plane methods are an improvement over sub grade methods。

Though you could think if you think of our a drink。

 then you have added some cassa that we had before， we know when to stop when to stop drinking。

 It is a better recipe。 Is it the best of all。 No， it is not， but it is good。

 good enough for some purposes。EIt can be improved。And why it is not good。

 It's because we have this nonmontononicity and another that makes it that there are oscills。

 you saw in the drawing that when we were getting closer to our solution。

 the linearization that this point X 4 was introduced was very original And then it was taking as far。

 further away。 And it increased the functional value that we had F X 4 was really close to F star。

 But F X 5 was further。 And this well， in many dimensions happens more times the just train this one in this drawing。

 And eventually， there are numerical  errorss because。😊，How is it that we solve our problem here。

 What is the effort that it takes to define the next iterate， It is more than the sub gradientient。

 What what is it we saw last in last class。 I， we were in this slide already。In fact。

 if we add an an additional variable scalar variable to represent the max here， minimizing the model。

 it is end then minimizing this scalar variable。

![](img/e7e5790610044bfa7bfaecc826dde820_55.png)

As in the constraint， that the barrier has to be larger than all the linearizations。Now。

 if we we add。More and more linearization here。 This means that in this linear programming problem。

 the matrix that defines the the constraints will have more and more lines。

 And because we are getting closer since the method converses to the solution。

 more and more of these lines will be。Orizonal， and we will be similar。

 And this makes the matrix of the physical set very ill conditioned。

 And when there is air conditioning， then we have numerical errors。 And then eventually。

 what happens is that。The method stalls。 It arrives to a point where it cannot increase because the numerical errors introduced by。

By these constraints that are very much alike。Are larger than the improvement that you can make from one eery to the next one。

 So this is， this is the weakness of the cut methods。 and it's called telling of effect。

 from some point on， X， K is equal x K plus one or it's even worse F of X， K doesn't improve。

And you could say， well， okay， but then I would throw out pieces of my model。

 Why I have to accumulate all of them。I have to accumulate all of them。

 If I want to make a conversionver proof。EThere are some ways to keep the conversion proof as long as we are sure。

So you can see when revising the con proof， the kind of inequalities that you need is that every time you improve your model。

You don't， you don't have to forget pieces that made you your model higher at the current at the it rate that was found at that iteration。

 that is a little complicated to explain。 But well， there are some ways， but it's not very， well。

 it is。You have to keep in memory all the pieces。 and you can put here less than all of them as long as you make some calculations that is called cut selection。

 But the the bottom line is that you are never sure of how many of those pieces you will have to put。

 And it may very very well that you have to put all of them。 And if you have to put all of them。

 then there is the telling of effect and the method numerically will not compare。

 So it is this is a problem。And its， it cannot be。Oviated。

 unless there is some other amendment that is done。

 and it amounts to introducing here a quadratic term。We， we introduce here a quadratic term。

 and these are called bundle methods that I would not talk about contrary to expectations。 maybe。

 So its will be well。 willll be explaining bundle methods。



![](img/e7e5790610044bfa7bfaecc826dde820_57.png)

So ingredients of the best recipe that we have a notion of a model。

 It is very important because it gave us the， this concept of distance and then a stop in test。

 But as I made in my illustrative drawing， we have， if this is the it is a small function。 Sorry。

 I didn't change it。 But the level set of a function that we want to minimize， we want to go there。

 if we draw the trajectories of the functional values， we will be， instead of go in。

From 1 point1 outer ellipse to an inner one and to an inner in a monotonic way。

 who will be doing all this kind of Six sagon。And this makes it unstable。

 And there are all those ociations。 And we in monotonity。

 And this is what abandon methods was bring into the picture。

Somehow it identifies it will be still defining points everywhere。

 but it will be remembering points where we got thescent of the functional values。

 And these are the so- calledled serious steps in bundle methods。

 And this is what will be monoton and will be convergent to a minir。

 So this is what the bundle methods， to。And this is a good recipe。 It's a real good caperia。

 And it's one in turn， who will tell you something。At the end of the， of the course。

 youll have to wait for link this good caperia。What we will do now。

Then it's now that we know about cutting plain methods。

 We will specialize it to to stage stochastic linear problems with fixed records with W， not random。

 Remember， I told you it was the most general case that was reasonable。And well。

 the name of the cutting play method when we applied the two two stage stochastic linear problems is the L shape method。

And I would make like you to think why it this L shaped。

 You will tell me maybe next class or maybe sometime you will。

 we will see maybe next class why it is L shape。 It is the。

 the structure of the matrix that we are the of the matrix of the when we write problems with records that has a shape of an L。

So， and this was introduced by V like and Rosa Wes。 As I said。

 Rosa Wes would come here to give a mini course the 20s of Z。It's also， it has many names。

 It my the idea of making approximations making a model of a function that we don't know。

 And if it is convex， we have all those。Ter and tighter models。 It is。

 it is applicable in different contexts， and it's also applicable in mix in programming。

 And it's called the vendors， the composition。 It's the same， the same animal。

 and they are different names。Okay， so。Now， we consider for our two station in a program with fix and records relatively and relative fixed records and relatively complete records is fixed and relatively complete。

 So this means that now we have w， not W S in our individual records function。

 when we evaluate at X K。 Well here is what we。😊，We saw in last last class or many classes already。

 you know it by heart by now， what is this expression in the primal and the dual formulation。

And then。So far， the con was proof that we saw its for a function F that has finite values。

 It does is's not defined in R union plus infinity， but in R。

And this corresponds to having relatively complete records。

 So we are always assuming that the X K that will be generated along the iterations of the cutting plane methods will be such that this constrain is feasible or dually。

 such that this problem is bounded is not unbounded。Good。

 so what happens if it is not the case and what do we do。

You have to do Samsung because records may not be relatively complete。And in this case。

 if records is not relatively complete this， then this is inible。

 It's equivalent that the dual is unbounded。 That means that this values plus infinity。

Q at this specific scenario is plus infinity。 then phi would be plus infinity。So， we sent an X K。

To the oracle， that is not in the domain of P or in the domain of these of sum of the records functions。

EThat define that word function fee。Good， so what do we do。We can do things for that。 Well， just。

 let me remind you that we computed the gradient， the sub gradient and just the fact of solving all those individual problems for each realization of uncertainty was given us this multiplier and with this multiplier。

 we can also build the sub gradientdent。 So we have the linearization。Fe of this form。

And at this stage， it's useful to realize that， in fact， here。

We are building a catto linearization for the sum of all the Qs。 That is V。

But we have linearization for each individual function Q， Q， right。We have。So we sent our X， K。

 And then for some specific scenario S。

![](img/e7e5790610044bfa7bfaecc826dde820_59.png)

おomega。S， we evaluate the function Q at X K X C， S。And this means that we found。呃。

They multiplier PkS。And with the multiplier PkS， we have defined the functional value。

Individualivular one。And they。Subgradient。Or minus- t。S transpose。呃B。Minus t is from post P。SK。

This case order here。I think sometimes I write K S another say is K M。 sorry。

 I have not been very consistent。 So we decided to sum all the sub gradients and all the function values and make it in a recession or a cut for fee。

嗯。

![](img/e7e5790610044bfa7bfaecc826dde820_61.png)

But we could as well have define individual linearization for each Q S。

 So keep this in mind because this is related to what is called the multi cat version of the L shape method。



![](img/e7e5790610044bfa7bfaecc826dde820_63.png)

![](img/e7e5790610044bfa7bfaecc826dde820_64.png)

Okay， so now we have them this linearization。 And if you remember our scheme。😊。

So we want to solve our first stage problem with the spectral records function。 And then for that。

 we will apply an optimization method for no smooth optimization that will generate its X K。

 And then to have the value of the function to the oracle that will give us the value of the function and a a gradient that will define a cat or a linearization that we will。

 for example， including the cut in place model。It's this it requires to solve for each single scenario。

 The second stage of problems that we can solve in the prim or form。

 It's a linear programming problem。Good， if we suppose that we forget that there is this problem of efficiencyibility。

 for now， then instead of solving this function fee。

 we don't know what we know is the problem is a model， right？ So， in fact。

 at each iteration at the case iteration of the L shape method， we will replace phi by its model。😊。

And we will solve this linear programming problem。That whose solution， one minimizer would be Xk。

 then would solve all the problems and will get another cut。

And then if we write it with the extra variable R， then， in fact。Will we may。

 will be solving this linear programming problem， the variable larger and all the cuts that we generated so far and the cuts。

At the sum of the。cuts that were provided by solving for each individual realization of uncertainty。

Okay， now then here， look， I put。Most if we go to write here。

 but I manage here in the with a rotation。 though we solve our dual problems for eachization of uncertainty。

 evaluate another X K。 And we have a question。😊，All these calculations can be done if the random matrix is random。

 Yes， I could put an S here。 Yes， Yes， it can。But not define termination。

may have problems for the final termination， I think。I think。

Maybe you have to do some assumptions on the randomness。Yes， so the。

 the comment is that you can speed up。 You can find ways of solving faster the individual problems。

For example， paralleling it faster， but also， you can also cut before the calculations of each solver。

 You can come before it optimal the precision of the solver。

 But this means that your cat will not be exact， right。Okay， yes， that is also a good idea。

 You can use a simplex method and then use make what is called one start。

 Remember what was the factorization or the basic matrix of the previous iteration and then use it to do the calculations here in an exact manner。

 but starting from good the factorization， for example。 Yes， there are many things that can be done。

 And one good thing is that， for example， if this Q is also fixed。 The records here。

 the the cost of records is not random。 then this set is the same for all S。 And you can use then。😊。

The solutions that you got from C 1 to62 and try if it gives you as an initial point。 for example。

 there are warm starts indeed these that can be used to accelerate the calculations。And by the way。

 notice that why is it that were studying this is because when you implemented your methods for large K。

At some point， the memory。Was like not handling the number of scenarios for solving everything at once。

If you do ladies， you can put as many scenarios here as you want。 and doing some smart things。

 maybe like won starts like Philip I suggested， you can handle a larger number of scenarios and then have a better representation of uncertainty。

Good。Okay。So， then。When we have finite termination is when we use a simplex method for solving those problems。

 This is what I commented before， because in this way。

 we will be only finding points maximizers that are vertices of this polyhedron。

Then this is what we call basic。A solution in the， in this agon of stochastic programming。Okay。

 but all these functions and all the reasoning that we've done so far depends on the fact that this function。

 the function， objective function。Ha has is real value。

 And this is not the case in stochastic programming。 It may happen that the we are in feasible。

 We have an X K with an an X K that is not in the domain of those records function。

 So of one records function。 It is enough。

![](img/e7e5790610044bfa7bfaecc826dde820_66.png)

That， for one records function。For one S， this objective here。Is unbounded。

 which is a sentence saying that the primal formulation is infeasible。 and then。

This would be equal to plus infinity3 at X guy。So。

![](img/e7e5790610044bfa7bfaecc826dde820_68.png)

As I said， the feasibility in the primer for formulation， an X K that makes this a quality void。

 Then this problem is invisible is the saying that saying that we are unbounded in the dual。

So X K is not in the domain of P。 as long as just one of the expected records functions makes。

 has this problem。And then what do we do， What we will do。

We will guide the iteration so that those X K that were produced along the cut in play method that were not in the domain of the function。

Are left out of our feasible set， of the feasible set of the first stage problem。So， and for that。

 we will to introduce in the feasible set。 So of the first stage problem。 So let me go back。

 please here。 So here so。This the feasible set here then is x intersection， all these cats， right。



![](img/e7e5790610044bfa7bfaecc826dde820_70.png)

We will introduce more constraints here that we make that every time we send an X K that gives us a fee that is plus infinity。

 then we will leave we will go and look into a section of the。

 of the feasible set that is does not contain this X K。 And like this。

 this amounts to introducing here。 not only。EAppros of the objective function fee。

But here are also approximationreations of the facets， No facets of the domain of those cus。This。

 these are polyhedral functions。 So here we will introduce cats that are called feasibility cats。

 and we will distinguish， distinguish between the cats that approximate the the that define the model and approximate our function fee。

 Those are objective cats。 though， from the others that prevent us from defining points that are not in the domain of some of the cues。

 And those are feasibility cuts。

![](img/e7e5790610044bfa7bfaecc826dde820_72.png)

And cut this linear session。 It's just another name。So we defined objective cuts。

 making an average of the linear linearizations of the individual records functions。Okay。

So those are the objective cuts。 and some iteration have this form objective at the iteration I。

We will build feasibility cuts in some iterations when objective cuts are not computable。

 because we have unboundedness in the in the dual formulation of some scenario。Okay， so。

Because how do we build a feasibility cut， We think we make the reasoning that this goes in parallel with what we have done so far for the record function Q。

 We will define a new function that instead of we calling  Q， we call Q。So and it is a feasibility。

 measures in feasibility of X， K at for the scenario S。

 And how do we measure that we go back to the prim formulation。 and we re remember that， well。

 when we have don't have this purple。😊，Here， a term。In feasibility arises because X。

 K makes this inequality。Not attainable。 Y G and0 is always feasible。 It's not the problem。

 The problem is here， because of X K。Then how do we make it feasible。

 We will have to add some variable。And then the measure of efficiencyibility of violation of constraints would be the difference between these and these。

 which is the variable Z。 So we'll try to minimize the violation of the constraint。

 And this is the same than minimizing this slack variable in， in some norm。Right。

 so this is a new function again， and now。Because Z is unconstrained。 We are not， I'm not even。

 it's not even necessary to think of C plus and C I No， we can't just。

Leave Z without any sign can be that X， K makes these larger or smaller。

 And then C would be compensating for that。And then if the point X K is feasible。

The optimal value will be 0。Right， and this is has always a solution， because he can be。

Anything and why is also。 So this problem is define has a finite value for any X K that we will send the domain of this function。

For any scenario and any X， K， for any scenario is R N。

 It never has infinite values because this is always feasible。

 Z can be anything that we need for this equality to hold。So，Okay， so。

 and then what will be the feasibility cuts， The feasibility cuts will be linearizations of this function。

Instead of linearizing Q， we linearize you and how do we linearize you， We do the same procedure。

 We just write the dual， and we can the dual， or we use the multiplier of this constraint。

 And this will give us some gradient of the function U， This is again， if we use here。 Sorry。

 I have to mention something。 The normal。 Which norm do we use。

If we want this to be a linear program， then what we have to use here is a polyheral norm。

 the one norm， L1 norm or the plus infinity。One of those two norms。嗯。

Not the ugly theyre known because it will be a quadratic problem。 Now。

 we want a linear programming problem。 So either the sum of the absolute value of the components or the maximum of the absolute value of the components of Z。

 And this gives us a linear programming problem。 where in this business， everything is like before。

 except that we change the problem that we have to solve to detect feasibility。

So we can define then the function of functional value and the sub gradientdient and make the linearization because this is。

 again， a polyhedral function。Except that differently from Q is defined for all X。

 So the domain is a full space R M。Okay， if you make the calculations， and I will let you do it。

 do them。😊，So what is the dual of this problem。forgot， forgot something here。

 There is here something missing。 I will go to a blackboard and write it。That was for what to。 they。

 they did those。Too late。Yesterday， they slice。Okay， so the do well is。The maximum。Off。

A term will be now the multiplier instead of P。H is minus t。Is Xk。Sam with2。

W u transpose at Eta is smaller than 0。And we have to define the。The norm。

Is smaller or equal than one。 And the star here means the one norm。

If we use the norm one in the primer。Then in the world， we will use the norm。And vice versa。

And this is why we're interested in polyedral norms。

 because like this will have a primal and a world that are linear programs， okay。😊，So I forgot this。

 And this is important because without these， because here is 0。 because this， then。

We can have a big， a very large We can define the any some direction of any size。 We need to。

 to bound the the size of the multi of these variable8。

 And if you compare now this problem the dual problem with the one we had before with P。 It's。

 it's rather similar。 especially if you write it wrong。 like I wrote it here。

 So what we had before in the variable P， we had P， P。 And here we had Q。So it is。

 as if we were taking records equal to 0， but we have to bound here and norm the that direction。

 this the。The size of the solution。Okay。So the feasibility cut then is we solve now the feasibility cut differently from objective cut。

 there will be for each single scenario because it's one scenario。

 not all of them that makes it feasible。 our problem。

 And then the feasibility cuts has the same shape than before。 But here we have。

 you see the multiplier Eta H S minus- T X。 but for one S。

 here is we were averaging over all of them。😊，Okay。

So the domain of our feasibility function at the S realizationization is the whole space。

 The function is polyhedral。What does it mean to have to have a。

A point that is in the domain of the S records function is the same as saying that U the optimal way that u is equal to 0。

 Let's go back。嗯。If where we send X， K such that this constraint without the purple term is feasible。

Then the smallest Z that we compute put here is 0。 and then the optimal value will be 0。Okay。

So as I said， if we use a polyheedral norm gives an LP both in the primal and the two formulations。

And now the question is， okay， so I'm in my setting where I have my first age problem that I use the model at each iteration。

 I introduce objective cuts， and then I go and the oracle as the oracle to evaluate the records functions with some X K and ex this X K makes in feasibleible some records functions。

 Do I have to solve。At every every time， two linear programming problems because one for Q and one from U。

No， no， because。There are commercial solvers like there are the commercial solves like Guru or Cplex。

 when we try to solve the。Here。When we try to solve either this problem or this problem with a point that may makes the primarily feasible and the dual and boundary。

They come and tell us， I couldn't find a solution。 But they also tell us there is a recession direction。

EAnd these recession direction。Is the Eta。 So you don't have to is the is the the solution to。

This problem。嗯。So there are ways of not having to solve again to solve first。

 the problem of feibility to decide if C equal 0 then we have and then solving them。And then。

 and then solving the problem with Q。Here see in the primal alone they do what formulation Q in the。

In the right hand side， so。Well， it can be done in an efficient manner when we are in the linear case。

 if we were in the non converse case， now， we have to sort things again because the solvers are not that marked。

So we don't have。 and this is cool。 You can research a little bit and see what is the output of each individual solver。

 Because sometimes there is a problem with a sign， because this is something you have to be aware when you write the dual here。



![](img/e7e5790610044bfa7bfaecc826dde820_74.png)

You can write that the wall and then say or in any even without the C。

 you can say when you write the laganion， it's a multiplier times W I minus this term。

Or it can be this minus W Y。 And this makes a changes the of the multiplier that is attached。

 And you have to use it well。 you have to pay attention。

 This is a typical source of problems and bags in all the problems。Okay。

 what else do I have to say today。okay。Because U is0 for all points that are feasible for the the our records problem。

Then what happens we have。A feasibility cut is a cut for the feasibility function。 So it is。

It is u of x larger than the feasibility cat than the feasibility cat。that is the sub inequality。

 right？It's a sub gradientient inequality is that the value of the function plus a sub gradientient is smaller than。

 the function at any point。 And these visibility categories of the form， it doesn't really matter。呃。

Yeah。可的。Yes。Okay， transpose Hs。Just the X。Now， if x is in the domain of Q。嗯。There are messages there。

 maybe there are questions I have I have to say for all x in the domain of Q， Q is finite。

 And this is the same than saying that U of x is equal to 0。嗯。

This means that for all x in the So here we have 0 for all x in the domain of Q。

And this is what we written here。So if we want to cut and to avoid points that are not in the domain of our function P or in particular of some Q at some realization S。

 then what we have to do is to add a cat that is the say a constraint that is the cat smaller than 0。

Okay， this is instead of smaller than R that we were adding before for the subject cats。

 now it will be。Smaller than 0。 So here I wrote。The feasibility cut and objective cuts。

 And now that with this。Amendment of the feasible set。

 Then the conversionvers is the same what we saw for the cutting plane method for real value function。

 because were guiding our method。So that it generates points in the feasible set in the domain。

 and then not in the feasible set in the domain。 And this means that fee will have finite values。

 So on the domain， this has finite values。 And then if we。

 when we solve the problems for the optity cut or the objective cut and the feasibility cuts using a simplex method。

 and we get the basic solution。 So with these are。These are verhees， then。If the fact。

 because both Q and U are polyhedral， we will finish after a finite number of iteration。

 we will terminate also with the L method。 So now the L method is really the method that it' a cut plain method that also uses feasibility cuts。

Okay。你 say。This is the the name of this， this method。Okay， so then。At teacheriteration。

We will have it。 So I'm almost on here。 Everybody is tired with all those names and things。

 but we are almost a little bit of of patience Now， so at this iteration。

 we will go and generate a point X I at iteration。 I。

 we will send it to the oracle and we will see if X I is in the domain of the function fee。 if it is。

 will have an optimality card that will come back of this form。😊。



![](img/e7e5790610044bfa7bfaecc826dde820_76.png)

![](img/e7e5790610044bfa7bfaecc826dde820_77.png)

If it is not。We will have that for some scenario， maybe more than one。

 There is invisasibility or or aness in the， in the dual。 And then we'll have。And of feasibility cut。

 So iterations would be divided。Among， I don't know why I call it J here and I here。 sorry。

 but what among those where we could evaluate the function， the expected record function。

And create objective cardss。And those where we couldn't， because for some scenario。

So right here I forgot too close。对。They are， they they said。 So。

 and then some iterations where for some scenarios， we be So all the past iterations。

 such that for some scenario is we couldn't evaluate the function。

 and we had to create a pieceibility cut。 so iterations would be divided in this tomb。😊，Set。

 and this gives us。Then，The first stage problem。I of the form， as before。

 we have the optimality cut for those iterations where we could define objective cut。

And feasibility at here is smaller or equal than 0， as I showed you。For each scenario。

 for the different scenarios where at the the past iterations， we could not generate an optimal。



![](img/e7e5790610044bfa7bfaecc826dde820_79.png)

Okay， so this is the， then the。The algorithmic it a pseudo algorithm， but in a graphical way。

 So at each iteration， we will now have optimality cut and feasibility cards minimizing over our set capital x。

😊，And we generate X， K， the current itererate by solving this linear programming problem。

 And then in the sub problems， we would either solve our the problems for the scenario S and the point X K that gives us the record function。

 or we will have to。😊，generateerate the feasibility cat for the specific scenario。

 And then it will go back here。 Either the value of the function。

 Well we go we will get back either an optimality cat or feasibility cats。We can choose even if。

 we can choose this side。 Well if it is invisible for one， we only have one feasibility card。

 and then we don't care about the others。 But probably whether to see at all scenarios if there is more than one in feasibility so that while we get out of the bad region fast。

Okay。So there is also a multi variant。 And I would comment on this in next class。 Next class。

 we will see also some implementation of these for specific stochastic linear programming problem。

So thank you for your attention。 And until you until when。 No， sorry bye。



![](img/e7e5790610044bfa7bfaecc826dde820_81.png)