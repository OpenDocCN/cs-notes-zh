# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p12 -12-Basic Course on Stochastic Programming - Class 12.zh_en -BV1tH92YXEnd_p12-

Hello， good afternoon， Welcome to Ba lecturec number 11。So today is my last class in this course。Sn。

 sniff。 well， I will be appear from time to time。 But after this class， there。

 there will be the turn of Wellington to start teaching and then Km Pablo。

So today we'll talk about it has been very nice to meeting all of you。

 And I hope to see you soon and often many more times。 So today。

 we'll talk about implementation issues of two stage methods。 In fact， the method that we studied。😊。

E the L shaped method， then。Okay， so let's get started with our usual slide that we all dream with。



![](img/e76eee2adebdb4f9c906b28bffab2c20_1.png)

And then let's remember that for our。

![](img/e76eee2adebdb4f9c906b28bffab2c20_3.png)

Records model model with records where we define So the two level decision。

 two level model for the decisions with first stage here are no variables and second stage。

 the variables Y corresponding to each scenario S。 then we have to solve。

I teach it had to solve a problem of this form。That if everything。IIsly near the cost。

 records cost records here， the first stage cost and the。Constraints， like we have seen so far。

 then in principle， even if when we do a scenario representation of uncertainty。

 this will be ending linear programming problem that we could solve directly。 principle。

 except that when we choose many scenarios， this becomes increasingly more and more difficult。

 And then you probably saw in the very simple problem with only two variables。

 these old production problem that it very soon gets out of hand。

So it is important then to put in practice method that the composes and replaces the solution of one big problem by a successive solution of smaller problems。

 so of course， the composition makes sense if we manage to define a digitaleration sub problems that are much。

 much easier to solve than the original big problem。 Otherwise。

 we would have replaced a difficult problem by a sequence of difficult problems。

 And this is not the best approach。 unless they pay you by hour or some scenarios。 I don't know。

 Well， anyway， So in the setting where we do have many scenarios because many scenario represent well represent well uncertainty and the。



![](img/e76eee2adebdb4f9c906b28bffab2c20_5.png)

2 level formulation gives。Sub problems， like as we studied。

 involved with evaluating the records function at the specific point X K at each single scenario。

 this gives an linear programming problem of reduce size。

And so we are in the setting where the composition is suitable。

 and we saw that this oracle approach that defines iterate X Xk for the first stage problem with information that given by the oracle that is the value of the function and only one sub gradient。

 then in this type of setting this is suitable for the two stage to castastic clean programming model。

 and what we saw is that since this function that this spectral records function is not available analytically。

 we only have the information of the black box， the method instead of to produce a new iterate。

 the first stage iterate， the method will replace this function by a model。Okay， so all that。

 you know， but redundance is not bad。 So I will at the first slice or a little bit recalling and putting together all the information。

 So what is the model， The model is the cut in play model。

That is the maximum here we represented in the model by this additional scalealar variable R。

Is the maximum of all the optimality cut that we define in past iterations。 past iterations here。

 You see the set of past iterations。Where we could eva effectively evaluate the spectral records function at X I because it was belonging to the domain of the spectral records function。

 That is， for all those sub problems。Of the individual record functions。 They are the E O boxes。

 the X I that we sent gave a feasible set in the primary formulation of these。

Of these individual records problems。 So， and then we made the wait sum upon all scenarios。

 This is a multiplier that correspond to the dual formulation or to the constraint that。EInve X， I。

 T， X I plus W， Y S equal H S。Okay， so these are the optimality cuts。

 And this is the model of the function。And if we had an iteration， a past iteration I here。

 past iteration I， where X I was not in the domain of at least one of those individual records functions for some S。

Not for all， for some。Many maybe one or maybe more。Then we were using this。

A feasibility function U that replaces a function Q at the scenario S。

 And we in the same with using the same ideas that right in a different world。

 we could define the feasibility cut， a feasibility cut were closing the set where we were looking for the new point X K that solve this problem by incorpo facets of the domain of the of those functions。

That are the domain is polyheedral， because those are。Peace wise， they are polyedral functions。Okay。

 good。 So that you already know there is a lot of notation， but the idea is。

 is rather simple and clear。😊，And then so in our graphical。Representation of the composition scheme。

 the caiteration then solves these type of problems。 Those。

 this is a linear programming problem that。Will have as many reliance here as iterates past iterates where X I was in the domain。

 and here， as many as where X I was not in the domain。 and as many scenarios where this happen。

 So the number of rows that we have in the in the metrics that defines a feasible set of these linear programming problem will be at least the number of past iterations。

 But maybe more because we have for each scenario where we have feasibility will are adding in a cut。

Okay， and then here we could either evaluate the function or evaluate the feasibility function。

 The records are the feasibility function。 and this amounts to solving the do well。😊，Program problem。

 the dual formulation with variable P。All they do a formulation with the variable a where I put one below the other for you to see that they are really very s similar。

 You see the same objective function。The feasible set here， instead of having Q S， we have 0。

 and then we have the norm， one norm in the dual norm， either L1 or L infinity。

 depending on what we chose。So this is， is rather simple to the scheme。And。There is a variant。

 And we saw that。 Yes， if we solve all those problems of the yellow boxes with the simple method。

 then we will have vertices of the。Of the solution set。 and these these ensurers that。

If the set capital x is compact， that the method will have finite termination。嗯。Okay。

 there is also a multi cat variable。 I will explain it here briefly on the blackboard。

Let me go for that。Here。It， it is related to the fact that the function P and then the cat。

 the function P is the sum of P A of P of the probabilities times the function。

 the record functions And then the cats are also sum。

 and the multi cat here we're adding one cat per in the multica will be adding S as many as scenarios also for the for the optimality cat。

So for that， let me just go to the blackboard here and consider then our problem。

 the non smooth optimization problem， because this has nothing to do with the fact that we are dealing with with stochastic stochastic。

 that is just the fact that the function that we are trying to minimize is a sum。

 It's a parallel by sums。 And then so we have。

![](img/e76eee2adebdb4f9c906b28bffab2c20_7.png)

Our problem minimize f of x for x in a polyhedrum compact polyhedron。嗯。

And then the cutting plane methods was a。Approxmating a iteration K， at the case iteration。呃。Solve。

The minimum of the models。T x in capital x。And this was given the ex itererate X K plus1。

 And with this itererate， we call the black box。 We obtained a new linearization。

 and we improve the model。This is what we as we here what we did for the cutting plants method。

 is what we are doing for the L shape method。Now， every time you have structure that you know a little bit more。

 You see here， we are saying we don't know anything of our function。

 except that it's non differentiable and that we have the right。と。呃。Use at each iteration。

 the value of a function and one sub gradientient。I'm going to put K plus one because it's the output here。

Okay， so this is a very general scheme is's good。 Now， every time we know a little bit。

 we can use this a little bit again， because we use introduce more knowledge in the algorithm that we are developing。

 And what is it that we know here。 We know that the function F。😊，Is a sum of two functions。

 Let's call it them with a lot of originality， F 1 and F2。Then， in fact。

 when we will be calling the oracle。What we will be。Do， likely。

We will have two separate oracles that each one will give us the value。Of the function。

At the point that we sent that。Okay， let's let it be。Xk plus1。To be consistent？

And it also gives us one a of each individual function。And then， D C。

Our oracle for F that is here where we will just add。 and then it will give us。Fk plus  one。And J。

 G K plus  one。Okay， then。Here you see this black box， we open it a little bit。

 and we know a little more。 So what we can do is a state of use in the aggregate information that is where we send。

 We can use the individual information。And what can we do with individual information instead of doing one linearization for F。

 we can do individual linearizations for F1 and F 2。嗯。So。K plus one。Plus z1 K plus 1。Transpose。

X minus x k plus 1。嗯。F2。Okay， plus one。えと。Okay plus one transpose。X minus x。K plus one。

These are those functions are convex。 Again， the the linearization is a lower hyperplane is a that supports the epigraph the graph of the function。

 so。F of x， F1， F1， sort right here and F2。Oh， it's a3。

This means that if we keep separated the formation。We can。

 instead of doing a model for the the function F， we can have two separate models for the function F 1 and F 2。

嗯。So， we can define。M1。The cable is low， okay， and one k。Of eggs。It would be the max。

For I is smaller than k of all the linearizations of No， sorry， F I1。Plus G， I transpose1。X-6， I。

And same thing for， too。For left， sorry。F。2 I plus G2， I transpose x minus X I the maximum。

 So we have separated the two models。And here then go compare with M with the here。

 Let me write it since we have， we haven't written it。This is a max。All， it's smaller than okay。F。系。

Z系。Ts suppose。Xマイのセサイ。So we have the maximum of the sum。AndHere we have that。

Sn of the maximums Max ma。And。This is lower， is smaller than the sum of these two models。嗯。So。

We had that Mk。Was smaller than f of x。And now， we。Sandwich is inside a better model。That is the sum。

And it seems that the calls are not very good in there。In the screen， so。Let me。M1， k。Of x plus。M2。

Of x。So if we are since we want to approximate our function。 F having a tighter model。

 one that is closer is in principle better in terms of conversiongence。

But every time we improve on one side， we lose on the other one。 Remember。

 I told you it's very moral optimization。 What is it date， But what it has to do with here。



![](img/e76eee2adebdb4f9c906b28bffab2c20_9.png)

When we represent the， the master problem with an additional variable for taking care of the max。



![](img/e76eee2adebdb4f9c906b28bffab2c20_11.png)

So if we use our aggregate model， is a name。Agggregate model。아， 그래。Gate。Model。

 this is an aim in non smooth optimization。

![](img/e76eee2adebdb4f9c906b28bffab2c20_13.png)

They said every time we have a exam， what cant do this。G。ItGives a master a first stage。

Problem of a form。 So we have the minimum。Now， the first stage cost。Bless。M1 K plus M2 K。

 So we have a variable R1 and R 2 R 2 here for representing the maximum。 So R 1 plus R 2。

Then subject to x in capital x and。R1 is larger than all the cuts for F1。1， I。I1 I don I suppose。

X minus X I。唉。Okay， our2。In done。On the cut。For。Z度。So， if you compare。This version。With this version。

 So single the the single cut or the， And well， forget about the feasibility cuts。

 What we are doing here is here。 So we pass we increase our problem with some more scalar variables。

 which is not a tragedy。

![](img/e76eee2adebdb4f9c906b28bffab2c20_15.png)

![](img/e76eee2adebdb4f9c906b28bffab2c20_16.png)

EIt is not match here。 We will have as many R as terms we are approaching。

But what is really having a strong impact is that we will have。We will be。

Add in as many constraints for as many cats that we have。

 you have more constraints in the same number of constraints for for each term。So remember。

 I told you that the problem the convergence problem or the converence weakness of this type of methods is that we cannot throw away rows in the matrix that define a feasible set。

 We cannot throw away cats。 And this makes this brings eventually this effect that is known as tail of effect that makes the method oscillate and have numerical errorss And because we have too many rows here that are alike and the problem is condition Now。

 this will happen much more earlier with the multicat。So if and this what， why it is multica。

 So in non smooth optimization， then this is aggregate model because we' are always thinking about those models for our non smooth functions in the L shape method。

 This is the multi cat version。So the multi cat variant， then will have。One term here。

 per term of the。Expect the record function。 we decided to approach。It can be as many as S。

 So for the L shape method， then the problem will be。Can be minimize C transpose x plus。

The sum over all scenarios， we can take all of them capital a。B S。RS。Right，7 say2。

X in capital x and R S larger than the cuts。 the objective cuts were with the form P。嗯。If I。

Transpose。H S minus T。X I for I in the objectives in the。即我唔知对。What was your name。 I。

 I put names to things， but I forget the names。 Let me see。 No here。呃。They。K plus  one。

 And these for S。Equal 1 to S。So if we have 1000 scenarios and 1000 cuts， we have 1 million lines。

 is fat。However， we can do some partial aggregation if we have F of x。That is F1 of x plus F 2 of x。

不来。Okay， F3。Plessers for。We can make a model for each one of those functions。

But we can also make a model for。If one。Plus F2 of x。Buff。A3 plus a 4 of x。

We can consider that we have only two。 we separate。

 And how is it that we will choose how to separate。 Well， this is rather simple。

 We remember our the composition method。And here。And then so we are defining an oracle for a group of yellow squares。

 and then。Depending on the application， the sums here， they。

 they will be more or less all of them similar。 probably the they all those second stage problems。

 But maybe there is sense a problem that takes a long time。

 If there is some a problem that takes a long time and then three others that take short time。

 then we will put together the three that takes short time。

 and then we'll leave alone make another prior term。For the one that takes long time。 And like this。

 we will be balancing the time that we spend in solving and obtaining the response from the oracle。

Right， this is， this has to be so。Well sort of when we deal with real life implementations。

 because it is really has a strong impact for the case of those of you who know a little bit about the and relaxation and hydrothermal plant in energy。

 then a typical bottleneck is the solution of the hydro sub problems。

 So here we will be solving an optimization problem for each power plant And then the thermal power plants are very easy to handle them very fast while the hydropower plants there big large linear programming problems in general。

 And then because they couple along a valley a lot of dams and reservoirs。

 So then the time that we spend in solving one rectangle here。

 yellow square is like 10 times the time we spend in solving all the other rectangles。

And then what what we can do is we consider an articleacle for all the these rectangles。

 the light ones together。 And we leave the heavy ones separated。

 So aggregation doesn't mean that because we have a sum of all the terms that we have to do a model an individual model for each one。

 which is were in common。 and it typically it is a good idea to gain this advantage that the model is tighter。

 It is a good idea to do this multica， but not to do many cats， many multis many terms in general，😊。

I don't know，3，4，5， no more， even if we have。1000 scenarios and 1000 terms。Okay， so now you know。

 everything about L the composition。And the outside， the outside method。 and the。

The multi cat variant。So now we will spend the the rest of the class in some application that I would want you to think of。

 And then we we， it's not true that we will not meet again。 We will meet again。

 and except that it will be after the exam because the exam is on Thursday。Right。

 and then if you start thinking of what I will tell you to think of before。

 probably you will not think of it because you will be thinking of the exam。

 So we will meet after the after that to do some class on the implementation of this type of method。

 the exam。 So before we get there。 then let me talk about the exam。

 it will be on Thursday for those who will be here And for those who are following the course by the YouTube channel each local representative with6 in the dates it will not be pro in some places。

 it will be also at the same time in others we don't know yet。

 we are waiting for responses from the from the local coordinators。In any case。

 well have all the exams in our desks scanned or written by you on paper on on Monday on the Monday after the So after the holiday。

26， I don't know1 is 26， but all the 26，20 word， Yeah。

 it Monday I think or Tuesday after Tida Tida holiday。Okay， so now， e so。

 so the exam would be on theory， like the least。EThat you made。

 And now let's go and talk about implementations。And one the application。

 we will use us to model all the formulations that we will study in the in the class。

 in the course will be the cash matching problem。 So suppose you own a company。

 you are very successful in the mathematical business and you own a company。 And you have to plan。😊。

How to face some debt payments that you will have to make along capital years。 And for that。

 you will buy bonds。2， in addition to a capital that you have to make money and with the return that these bonds will give you be able to honor your debt。

So we will buy n bonds we have to make at the end of each year or each year。Payments， Vt。

And these bonds are very safe。 are like those almost risk free ones。 they have a no return。 We we。

 we will not put。E stochasticity， and on the future return， at time T， the east bones past R。

And the cost when we buy them is C。 So here everything is deterministic。

And then we have a capital capital K that will also be there to help us pay our。

So what we want to know is for each one of these bones to determine。How many or the amount。

 not how many， but the。The quantity， but it will be a real value。

 not in value of the bonds of the type I。 So that the end of the horizon， we are left with money。

With all these investment that we need plus our capital in order to finance our left。

But we want that every year we are able to honor all that。 We don't want to be in in any periods。

 in any time tea。So this is the the setting。And then while we will be making formulations。

 models of the different types that are possible for from the stochastic programming in point of view。

 And today， we will make a model with records。 And this is the one that we will play with in the implementations。

Okay， so。

![](img/e76eee2adebdb4f9c906b28bffab2c20_18.png)

We have to define。 We want to have the maximum amount of money at the end of the period。

 So we have to count， accumulate how much money we will be making every at every time step and how much we will be having to pay。

So。For that， we introduce those two quantities， A and H。

A depends on the tells us at time until time T， how much。Money we made with the bond eye。嗯。

So we take the return of the bond for all the time steps previous to T。 and we discount。

 We subtract the cost。Right。Good， so this is for each bond。

 all the money that we will make will be multiplying this quantity by X I。

Which is amount is about variable， decision variable。Now， what is it that we have to pay。

 We have to pay until time T， All the payments that since the beginning of the period until the current time。

And we had our work capital that we were using。 so we sub our work capital。Okay。So， good。



![](img/e76eee2adebdb4f9c906b28bffab2c20_20.png)

With this， we can then。Right， our problem。So。We want to maximize。



![](img/e76eee2adebdb4f9c906b28bffab2c20_22.png)

The amount of money。

![](img/e76eee2adebdb4f9c906b28bffab2c20_24.png)

We have， at the end of the period。So the return of the bond times the amount。

 the quantity that of each bond。

![](img/e76eee2adebdb4f9c906b28bffab2c20_26.png)

Sing over all the bonds。 So what time compete， This is what we want to maximize。

 And at each time step， the money that we have accumulated with all the bonds。

Has to be able to pay our debt at the consider time。 The pay has to be making all the time。

 all the payments。Okay。Yes。It's good。No， you don't like the mother。 You have a good mother。

 better mother。Oh， you are the owner of the company。 So I don't know。😀Okay。😊。

Where Y X I is not equal to plus infinitefinity solution， because we don't have。Here there。

That we have， we don't have enough money。嗯。It not says， but if you want， you can also say。

What we should add here， probably that I didn't。 And I thought and I forgot is that we're always buying。

 We' are not selling。 So X I is larger than0。And if you want to bound it because like these， the。

 the feasible set will be compact。 And we are in， in the conditions of conence。

 how much money you can spend in a bond is K capitalita K。

 You don't have any more money to spend on the。 So here。We should add the constraint。0 is smaller。

 A A box constraint。 X I smaller than k。诶。All the bones。Then you close。

 But this minus k is what it makes you。

![](img/e76eee2adebdb4f9c906b28bffab2c20_28.png)

It makes you well。 You cannot spend more than what you have。嗯。So， okay。So now we are okay。 yes，1。

1 question。The who， the As， What is the sign of the， the question is， what is the sign of the As。

Well， it depends on what are， what is your data。If you are willing to pay。

If you are willing to pay for a very expensive bond， you will have to wait until many。

 many times there have passed for this coefficient to be positive。 It depends on the return。dependss。

 I will show you an example there with numbers， but it depends。

 that would be part of your investment decision or the portfolio that you would choose。

 the which are the options that you have access to。So it's likely that in the beginning， for lower T。

 AI T is negative。 And then it becomes positive from at some point on。Okay。

 so what is stochastic here， We said that the return and the cost were not is stochastic。

 So the here these metrics is the matrix because where we have different is the is deterministic。

 but what we don't know， we will assume that the payments are subject to some stochasticity。We。

 we modeled it like a normal some normal。distribution with a very high variance along the time steps。

EThen this makes the this problem stochastic with a right hand side that is random。

All the rest here will assume that it is not random because ladies will not have to generate synergiess for many for differ terms and to worry out correlations。

Okay， so well， as I said， we have this problem with a random right hand side， and we can make some。



![](img/e76eee2adebdb4f9c906b28bffab2c20_30.png)

Candling of uncertainty， like stochastic programming proposes。

 And since we want to apply it to a two stage model， we will make a two stage model with records。嗯。

Okay， then why before showing you what is the model with records， Let's think a little bit。

 What is it that we can do。 What is it that we need to incorporate。

 we will incorporate our records variables that will be because as it is written here we have only here are now variables we buy today for the next capital1 the years to be to not be in。

Whatever the realization of uncertainty is， you know that from the simple example that you ran that you can solve many variants of this problem。

 then the realization of uncertainty is not the one that you were taken into consideration。

 And then you will be unreed but we want to be enra。

 not in many situations from all these assessment that you did in the mat labb example。

 the simple example of the oil production problem。 The more reliable。

Solutions were given by the model of probabilistic constraints and for， of records。

 there was case probably 2。 No。 I don't remember what yeah。 there was case 2。 So， well。

 let's do a records model。 that will。Make us feel sufficiently safe。 let's say。

 because we are fans of two stage models as owner of a company。So what is it that we have to do。

 We have to introduce here some slackla that will ensure that we will have feasibility in this constraint that may become feasible because our decision doesn't depend on uncertainty。

 but the right hand side does。 This is a model with record。In terms of the problem， what can we do。

 We can say， okay， today， I make my plan。 I buy this bonds X I， the the bone X I， the amount X I。

 And then in the future， I give myself the possibility to go and buy a little more。Of the same bond。

This is a possibility for the records。 We could say every year， I will be trying to。

Add here to instead of only have an X I of the of the bond。 I。

 I will buy a quantity Y I of omega extra。 the correction。 So our variables。呃。

Records variables who are called why。And why we're calling them why it's because。

There have been called wine in there。In the book， why not？So why so。We could say we will buy。

An amount。Y I of omega。To an x additional， let's say。Formega additional formal buying。冇味。To adopt。嗯。

To a realization。Of uncertainty。奥美的。Okay， yes， there is a question。The previous slide。嗯嗯。嗯。



![](img/e76eee2adebdb4f9c906b28bffab2c20_32.png)

こと賛生。Okay。那我说到带动好都不别带过去。So。The question is， I。What kind of modelling we want to to make here。We have。

 in my opinion， what we have here is we have n kind of。bonds options and。

We have to I maximise some kind of return at the end of the planning horizon。And in each time。

 we have to meet some minimal requirement。 That is the return in the time G must be more than must be enough by H G。

So。And now。What is the meaning of the recourse variable that you're。

So I am I chose to that a possibility is not the only one。 we， we are the owners of the company。

 And I we chose what it' it's a virtual company。 So it's okay。

 So what we what I would want is to say， okay， I have this I know that I have those options these different bonds。

 bonds。 But maybe when I made my decision in the first time step， then I didn't。

 it was not good enough for this realization of uncertainty。

 So I give myself the possibility to go and immediately by at some， at some time step。

 And this is where we are going。An extra amount。Okay of the same bone。Do you have another idea。

 another proposal。Okay， then I go back so。So this is a possibility。 It's not the only one。

 And note that I。I'm here on purpose because I want a two stage model。

 I'm not saying that at each time step， I'm not writing this record function as a function of T。

 I will not。 I am too busy of a person。 And I don't want every year to go and revise my plan。

 I will do it in the beginning。 And then I don't know in the second year or the fifth year。

 I will go boom。 and Ill see， how are we did We lose money。 no we need it。 So let's try to correct。

This is a model。So， and we are the owners of the model。If you want to have a be very busy every。

 every time step， you can consider that you will do it。 you will revise and adapt every time step。

 But this would give us a multit model。 And I don't want it。 This is why I。

Wellington will talk about multistage programming， and then he would probably。Try to convince him。

 convince you that his company is better than this one。he will try to。

 He will put variables that will correct the decisions at each time step。I'm a busy person。

 so I don't want。 I want。 I do now。 And then， okay， I may have been wrong。 I will correct。

So now the question is， when do we do this correction， We are also the owners。

 and it will be at some future time that is not today。 It will not be the equal。1。

 it will be some time in the future。Yeah。Yet， I'm in the future that I chose because it's easier to write。

 is the second here。Okay， so， and this is for you to be aware that the fact that we we have time steps doesn't mean that these are the stages of the our decisions。

You see， there is a difference between time steps T equal1 to capital T and where the decision that that the states at which we make the decision。



![](img/e76eee2adebdb4f9c906b28bffab2c20_34.png)

In the here and now formulation， we make the decision。Now， and then there are capital D time steps。

In this setting。Where I own the company， and I'm willing to think of that today and next year。

 then I will have two。Stats of the， decision stagess。 the here are no variable X。

 and the corrective records measure Y， that will be。AppApp will be applied。

 and from the second year on， only once I will review my， my planning of investment。

 and I will buy things next year。

![](img/e76eee2adebdb4f9c906b28bffab2c20_36.png)

So。This is a model， as I said， then once you put you write down your model。

 you have to be able to defend it with the one who is paying for you to， to， to solve the problem。

 and you have to be able to solve it。 And then a two stage model。



![](img/e76eee2adebdb4f9c906b28bffab2c20_38.png)

I model。 So with records like here has it like can be seen as a good compromise between not correcting anything in the future and being only here and now regarding decisions variables。

 And every year， say， no， no， I made a mistake。 I made a mistake。 I made a mistake。

 and then correcting。 And this is a multi stageage approach that gives a very。

 very big and untractable from the numerical point of view。Problem even after the composition。

 So that are every time you make a model in decision。

 this has consequences from the numerical point of view and consequences from the。

Usefulness and utility of the response that you get from the problem。Okay。

 so the first model that we started with is this one we only determine today all our planning investment planning for the future。

 And this is a formulation without regards。Well， we might be interested or was something we will not care。

But as I said， we can buy today。X， I and make a wait and see adjustment Y I of Oomega in the future。

 And the owners of the company decided the future will be equal to。

This is because it's easier afterwards to， to write the equation。

 because let's let's write them in the black now。没。Com here。



![](img/e76eee2adebdb4f9c906b28bffab2c20_40.png)

So。嗯。And well， the interest of doing this game that's saying I will buy more of the same is that we have already the return on the cost。

We don't have to look for additional data。 we could say， we could say， oh。

 I will see if there is some other type of bone bond that I could use here。 now， we will。

 we have our portfolio is composed by these N options。 And then this is。

 we will always choose from there。 and we have all the data already to make the two the two states formulation。

 So the data was the。The return item T of the eastbound， the cost。No have the no the doesn't matter。

 What matters， in fact， is， So this corrective step， this corrective action will change the。

The a the accumulated return that we will have。 we have not change that right hand side that is the depth。

 This is what it is， right， that has nothing to do with us buying more or less。

So we had the cumulative return of the case bond was the sum Atee then the sum of the returns。

Between one and T。Minus。The cost。And this multiply by。What we decided to buy。

In in the beginning of the horizon。Now， we are buying also an amount。Yhy I of omega。

At the time step 2。Then， this means that。We still have to pay C for it。But the return。

It will be from the time step 2。Let's say， well， we could say that this trade doesn't doesn't matter much。

 but we are supposing that there is no zero time。 as soon as we die， it starts giving us our return。

So， this is the term。

![](img/e76eee2adebdb4f9c906b28bffab2c20_42.png)

That we will add in to our accumulation of profit the profit that the bond。The here and now。

 decision gave us with the bond eye。 and then we some some over the ice。Okay。

So this was what we call the variable， this AI T。呃，但。呃。X I。The same was AI。And now。

 if you compare the difference here between those two factors。

 we are we having the same that we have up minus the first return。嗯。Right， here only。

The were term with tau equal one is missing。So this is equal to A I T minus R。I1。嗯。😊，单。

Thanks Y I of omega。Okay， so now we have our two stage formulation。So the formulation with records。

So here I wrote again just I wrote it in 4 equal1。 We have only our bond here and now decision on the bond I40 larger than2。

 we have what we had in the previous time step by a plus。From now on。

 we will have X I and is correction。The depth doesn't change because we are no。

 the debt is what it is， and we have to honor it。Okay。

 so this is the same as what I wrote in the blackboard。 We have this relation。

And if you remember then the the two stage stochastic the linear programming formulation。

 we are in the setting because this corresponds to the matrix T times x right we will write these for we will have to sum over all the bonds。

 and then for each time step larger are equal than two yeah none two then this is linking first stage and second stage variables。

The term that was multi。 The first variable is the technology technology matrix。

And the term that is multiplying the records variable is the records matrix W。 So T And W here。

 those would be lines of T and W。 Well， after we sum over all the the bonds at each time step。Okay。

 so this is our records model。We maximize。The return， the。

 the accumulated gain of the bond that is here and now decision related to a here and now decision plus the expected value。

Of the accumulated gain， of their records， records variables。given by this here we sum over them。

The帮s。Here I put here。 I remember one of the side of the boxes。

 all the variables can be bounded above by our capital we。

 because its the most money that we can spend our capital K。

 So I can put here capital K and capital K。To got。Sorry。

 then we have this constraint where at the first time， we know for this year what will be overlapped。

 So it is run， it is not random。 It is deterministic。 And then this makes up the said capital X。

In our formulation， our after formulation。 And here we have for each T each time step here I put one is 2。

 Here is 2。Then for each time step larger or equal to one。

 we have this relation between the first phase decision and the corrective。Wait and see variables。

Okay， so this is the problem that you will have to solve。And then for that。

 I'm giving you hints and data because I want you to。

 it's easier for me to look at what you did if you did things。



![](img/e76eee2adebdb4f9c906b28bffab2c20_44.png)

Similar to what I have done。That means that you take my， my， my， my structure。 And then well。

 if you want to do it in Python inocta or not in matla or C plus plus。 Okay， I can manage。

 But at least the structure has to be similar。 otherwise， well everybody。

 there is a lot of creativity in this class and everybody has things very differently。 Okay。

 so what is the， the first phase for any， the first step， let's not speak space。

 like these stages for the the technical meaning。 So the first step when you have to solve。😊。

A problem that is given by numbers and real data is you have to generate the data that you when you get out from the blackboard and you have to go and。

And solve。 So my advice then， is to。this is a very simple function。

 So I write wrote in Matlab because I had them already in Matlab or something similar。

 So we generate the cache matching data by defining how many scenarios we want to choose。

 And the second variable is called for example。 This is very important。

 when you it's important in the the bag stage。😊，When you generate random data。

 and then you run your problem。 And then there is a there is a bag。Then you run。

 you make a correction and you run it again。 It generates different data。

 and you cannot chase the bag because it's a different problem。Okay。😊，You understand the， the the is。

 So to make sure that this doesn't happen， you have always to use the same seed for generating random data。

But this has to be removed once you have the bag your problem。

 and then you want to run for many different sets of random data。 so the see has to be different。

 So for that， you will use this variable or sample that will tell the random that the generator use the same seat or use a different one。

Okay， this is very important for the the bag stage。

 So this is the for these very simple function the two arguments。

 And then there is something that I call the Gave town， the big drawer。

 this is a big drawer where we will put a lot of data related to this problem， why。

 because maybe for the final project， you will use the。

The course that you will have will develop now。 But for a different problem。

 And then the data of that problem will be different。 Okay， if we have this structure。

 this is a structure that has a lot of things inside， then we can use you can use and I。

 I do use for solving different problems。 the same program。

 because it has been done in an abstract manner， not specifics only for three variables and ca matching problem。

 Now， this is will be possible to reuse for different problems stochastic programming problems up to a general certain general level of generality。

 Okay， so first thing we do every new data that we have that will be used in the future。

 we put it in our structure。

![](img/e76eee2adebdb4f9c906b28bffab2c20_46.png)

So， we assign it。To our structure。 And it's useful that it is a structure because here we only put data。

 And then data can have many， many things。 It's like a a gigantic。

 I don't know board with different doors。 And the doors can change for each different problem that we' are solving。

 Okay， and then we will call a script that puts more things in this data。And so we generate。

 and then we separate。 it is usually useful to separate the generation of generation of data specific of the problem in its deterministic form from the generation of scenarios。

 Here is what we are doing and then。Well， this is， for example， it gets out this rembling if we。

 it because if we change the see to make sure that we don't repeat it or that we repeat it。

This is a lower bound of scenarios that can be useful sometimes for some calculations。

 And this is all the scenarios that we generated here。 There will be all the H S， these that in our。

不老了。Okay。So what is it that this generate the cash matching data does。 It's a very simple function。

 It assigns I know this here was I explained this already。 Okay， I did。

 So now what is the cash matching that here are all those returns that you， you wanted to know。

 We will have only three for this example。3 possibilities for investment and is equal to3 along 15 times steps。

 All these money。 We are rich。Then these are the costs of the。Of the bonds。And you see。

 the returns are not very。 It's， it's a teach time step。 The first year， we get nothing。

 The second year， it gave 60， and we pay 980 So the first year， this AI would be negative。

 The second year， the third year。 So we will take some years。For per unit。 But well。

 it depends afterwards， how many we bought。 I don't know if we bought 20。 Then the first year。

 we already get some money from this investment for investing in the bond one。These are our depths。

 You see， it's more and more and more and more around the years。More often， oh， here it。

I wonder if no， this must be a bag because Lo was given 60 and all of his gave 1060。



![](img/e76eee2adebdb4f9c906b28bffab2c20_48.png)

We should invest in this one and say， so I will， I will look at it probably。 And although here look。

 no， there are some years where this is to perturb the perturb the to shuffle the the cars。

 There are some time steps where we really would like to have that a lot of it in our。

 in our portfolio。 But it is the same for all of them。 So we have to， to find a good balance。😊，Okay。

 here is a very simple definition of standard deviation，500 time。 So at each time step。

This is how the volatility of our depth， how will it will evolve。



![](img/e76eee2adebdb4f9c906b28bffab2c20_50.png)

And then well here， we are defining the this。Terms a and see， with sum all the returns。嗯，对了。Time。

 this is tau。 J is tau until time J。呃呃 no。J is T lower capital T。

 So here we are sum in until capital T for the bond I， and then we subtract the cost。Okay。

 and then the cost， it will be the last accumulated game。

And we change the sign because usually the solvers minimize costs and we want to maximize these value。

 So we change the sign。 And well here there is some transposition that has to be done。

 And then once we defined all our data boom， we put it in our bigger。Der in the gaze thumb。6岁。Okay。

 and this is what you would have to do。 This is my last slide today。 I will finish earlier because。

 because I I have no more to say。 you have to to work。Yeah。😊，There is always a reason。 So。

 but this is here。 all those dots are for you to feel。 And this is， this is a lot of work。

 This is where the work the， the more work is done。 So what will we be doing Now。

 this is specific for the cache match in oracle。 But any kind of problem that we will do will feed this structure。

 the one with the yellow。😊，Okay， let me come here here。This structure。

So in this cachem in oracle function， you will be making those calculations that is solving those。

problemsm， either these or that， depending the optimality or the feasibility problem。

 or maybe doing some fancy thing with the recession directions that Cx or could probably give you your is。

First is whether or not to be too fancy and be safe。

 So that means that the first time you run your problem， you run it with one scenario。

 and then you put two scenarios。 And then you see if you are doing things right。

 And then you become fancy。 But first， make sure that it is correct， so。Then the oracle。

 if you have some oracle that that gives you。Information that is standardized。

 You can change the problem。 And then what we will be using here to solve the master can be used for any。

 any type of problem， different type of problems。 This is the， the interest of an oracle。

 and the oracle then is specific for each application and in my experience It's where all the bags are in general。

 It's from the more difficult to the bag。 So try to be cautiouss and well check that things are correct。

呃，so。Okay， let's go back to our last slide。Okay， so what is it that all the oracles will have the the structure。

 will have a name that will be specific。 The input will be X， K and the。

 the structure with all the data。And the output will be。

 we could get the value of the function and the sub gradientient。

 But we can also have directly the cat that is the intercept and the slope。

I don't know if you mean what I mean。 You see what I mean， but let me write it。So。Let me write here。

 So we had X K。 Here is the oracle。 and we said that it gives us。SK and G K。Right。

 the value of the function and the sub gradientdient。So with this， what do we do。

 We use it in a very specific way that is F K plus to define the cut。X minus X minus X K。

And this is a linear， an assignine function that has， as intercept S K plus minus。G K transpose。Xk。

不来。Z K transpose x。 So this is the intercept。And this is a slope。 You can。

So either get this or get this directly In the case of two stagetochastic linear program， the。

 the cat had the form。Bi。嗯嗯。Well， let me do it the one that is not aggregated。 individual or one K。

 S。I suppose。H S minus T S。X。So this is the intercept。And well。This is a slope。 the slope。Is- T。F。B。

Okay。Transpose big case。To all， the important thing is that what gets out from there is can be used to define the。

The linearization。You will make a disaggregate model。Or first， or I mean。I said dis aggregateated。

 aggregate model。 No， sorry， it's disaggregated。 The the the one that is like the sum。 Okay。

 so let's ruin in。If we use。For everyone。Bless do we use。Mk。The D max。Of the ss。Of the linearization。

 if I，m sorry。X minus X i。This is the aggregate model。 Everything is together。嗯。为。2。刘生。嗯。

Agregate model。按。If we use。MK。1 k， O1， How was it。 No， not remember， but。1 K。Of X plus。M2 k of x。

So the multica version。M题 cut。Version。This is theaggregate model。Okay， sorry for these parentheses。

 Now we close parentheses and we go back。Okay， so here， here， the inside here。Again。

 you are in command。 You are the ones who decide if you will maybe making an aggregate or a disaggregate model。

 I advise you， it's the first go for the。Sing cat。 So they aggregate all some altogether。

And then so what will we getting in out for all the oracles that we would be using。

 then the intercepts and the slope， and then。The our data where we will shuffle some extra information。

 For example， if the cat that we generated was an optimal cat or a feasibility cat that we need to know to define our or sometimes while there is an error。

 And then we have to get out a flag that says I cannot continue， and then the method has to stop。

 right， if there was a mistake in the linear program is solver。

 then they will have that flag equal-99。 And then if this is-99， not your called。

 you have to stop and make a message。

![](img/e76eee2adebdb4f9c906b28bffab2c20_52.png)

You have to be informative so that when you have an error， you， you can find it。 Okay。

 so the output then is the intercept and the slope of the catta X K。The output is its type。

 And here I， I like my， my fancy thing。 Well， maybe it's not that fancy。

 but well when we have a feasibility cat， we not only need to know if it is a feasibility cat。

 but we need to know for which scenarios because we have to， to keep track of those scenarios。😊。

And then。What we will do is we will have then some output。Invisasibility， that will be0。

 if it is an optimality cut。And if it is a feasibility cut here。

 we will pass the numbers of the scenarios where for which we're creating。The， the cut， which means。

 by the way， that in that case， this intercept will be will be a vector because we have one person scenario and the slope also will be a matrix because the slope is a vector。

 So a set of vectors。Okay。So， well， you have to， to think how to implement those things。 and then。

Well， first thing to do Also， my advice， define all the output to we elements so that if there is a mistake and it stops。

 it doesn't tell you， I don't have defined the output。 So here is we define as empty。All the。

 all these elements that are the output arguments of our function。And then here here。

 you will have to do all this solving and the and the calculations to fill this part。

 And this will entertain you for some time。 But probably after the after the class， after the exam。

 probably if you won't do it before。 but before the exam is whether to study before the exam。

 I guess。😊，So，Well， it depends also， you will tell me。

 also we will see how is it that you are doing when you are doing this and then we see when to meet to to do。

 to， to revise these and to run。Maybe I will， I will give you my vendors a composition。

 But if you want to implement it， too， it's okay。 For now， what you have to do is the。でプロでで or。Okay。

 so though we have some question。No， we have some question。 No， because this is the last slide。

 Let me see， yes， and let me see if we have some question here since today， I remember， no。

 there is nothing in the Whatsapp。 Okay， so then we'll finish here。Thank you。 and see you next time。

