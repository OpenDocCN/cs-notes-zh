# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p06 -06-Basic Course on Stochastic Programming - Class 06.zh_en -BV1tH92YXEnd_p6-

Hello， welcome to our6 lecture。

![](img/5d86be08ec84b983d08a24c79468ec70_1.png)

Today is holiday in some places where we are working。 Thank you， everybody， for being here。😊。

So today， we will finally see that an example of a records Spec records function that these continuous。

😊，Not just polyhedra as all the cases we have been seen for discrete distribution。

 So for continuous distribution， it is not the case。

 it is that is a smooth in effect because we have a sampling space that is continuous。

 and we will also prove CRM on optimality conditions can the solutions of to stay stochastic linear program。

Okay， so let's start with the beginning， the usual beginning。

 dont forget to set the resolution to 480 pixels。😊。

And then I want to make a comment because I said something slightly wrong last time when I was defining a class of measurable sets。

 when we revised fastly the concepts of measurability。 So everything is correct。

 everything that is written is correct is what I said that was slightly inaccurate。 So remember。

 we had a class that was abstract in the probability space and we had the measure that was allowing us to define the size of the set in this class。

 And the class was defined in an aximatic way so that every time set was measurable。

 itss complement is measurable2。 and the union of sets that are thejo pairwise has a measure that is given by the sum of the individual measures。

 And by the way， here this should be f and F， not A and I because we are in F here。😊。



![](img/5d86be08ec84b983d08a24c79468ec70_3.png)

Okay， so everything is okay the sets in this class are the events in the probability space and the triplet defines the probability space。

 so we have the sampling space mega， the set of measurable functions in that is capital a for calligraphic f and the measure P。

😊。

![](img/5d86be08ec84b983d08a24c79468ec70_5.png)

，The set of the class of measurable functions， these calligraphic F is called a sigma algebra。 Okay。

 this is the name。 and I said that it was a filtration。

 That was the mistake it is a filtration when we it will be a filtration when we will study the multitage problems where we have more than one opportunity to apply the records and correct the decision made in the previous stages。

 So uncertainty now we' are assuming that uncertainty becomes known from one time forever in the future。

 while for this multitage setting that will be explained by Wellington there is successive steps steps where the realization becomes known。

 for example， in the。

![](img/5d86be08ec84b983d08a24c79468ec70_7.png)

![](img/5d86be08ec84b983d08a24c79468ec70_8.png)

example， the oil production example， it would be it is known from one day to the next one。

 What is the or the one week to to the next one， What is the actual demand of premium gasoline。

 and then the week after that， we have to wait one more week to to wait until the realization of the new uncertainty。

 And if we make our horizon of the decision is one month。

 Then we will have successive station stages where we will get to know more and more the uncertainty。

 In this case， this if here will be a filtration。 And it will be a set of sigma algebras。 Okay。

 so this is just a precision not to。

![](img/5d86be08ec84b983d08a24c79468ec70_10.png)

Confuse you。 I hope not to confuse you with these explanations。Okay。

 so I recall that to illustrate all the properties of the spectral records function。

 we consider a very simple case that is sufficient to explore all the properties of this function that we are in R then。

 and we have only these stochastic equality to which We give a meaning we make this problem tractable by a model with records。

 this problem we make it tractable by certain a model with records。

 which means then that we will adhere here variables。

 So y plus and y minus that will be the Y and C variables plus a cost。



![](img/5d86be08ec84b983d08a24c79468ec70_12.png)

Of that will correspond to the cost of making these corrections。

 And then this gives rise to the cost function that is now a very simple linear programming problem for each。

First stage variable or here and now， decision variable and each realization of uncertainty that enters here only here in the right hand side。

 So this is a linear problem problem。 We have only vectors variables。

 What here there are not even vectors。 There are scalealrs。 And this is our error course problem。

So the model that treats uncertainty for the stochastic greener programming problem here is this two stage greener program that has this form。

And we proved the last class two days ago that the dual physical set of the records problems of the wait and see problems is not10 not empty If if and leave the records is sufficiently expensive。

 Oh， forgot the larger than 0。 here there is larger than 0。Okay， yeah for a particular case。

 when we have that the records for shortage and for surplus is equal to one。

 Then this records function has a close expression。

 and it becomes just the absolute value of omega minus x。

So it's very clear that it is piecewise linear。 And if we have a finite support。Then we will have。

K realizations of uncertainty here， W K， and the expected record function that now we call phi of x because it will be shorter。

 So in this class， in this lecture， it will be p of x。

 is convex and is polyheedra and the kings what that is the point where there is discontinuity in the derivative is a point W K here。

 that that constitute events in our probability in our sampling space。 the probability space， omega。



![](img/5d86be08ec84b983d08a24c79468ec70_14.png)

![](img/5d86be08ec84b983d08a24c79468ec70_15.png)

Okay， and then so well that is here， it will be just the sum。If they all have the sability。

 for example， we co consider the if omega。It has a uniform distribution。In the set of0，1，2， and3。

 Okay， so only the those three。4。Point， so W 1，2，3， and 4。 Then k is equal to 4。

 We consider that they are equally equi probable， then phi of x。Would we one fourth。

And the sum of those。So W goes first right。 So is 0 minus x。Plus。

 absolute value of1 minus x plus absolute value of 2 minus x。Plus， up to the value of 3 minus x6 x。

Okay， I will not right there anymore。 But while you see， it is clearly。

 it's a function that has kinks。

![](img/5d86be08ec84b983d08a24c79468ec70_17.png)

Of these type。 And these kinks is are the points where the the absolute value function is not differentiable and it's not differentiable at when the argument is equal to 0。

 So it is when x is equal to W 1， W 2， W 3 or W 4。

![](img/5d86be08ec84b983d08a24c79468ec70_19.png)

These are the kings。Of this function。

![](img/5d86be08ec84b983d08a24c79468ec70_21.png)

Okay， so now the long time promise that today will finally be answered。

 but it will require some work from you because it will be we will have an exercise here。

Is what happens when omega is is a continuous set。 We have a continuous distribution。

 The probability to distribution is continuous。Okay， so now what is the change。

 the change is that instead of the sum， we will have an integral and taking in with the the with the measure of probability that defines our space。

Now， for integrating with respect to the probability measures， sometimes it's a little complicated。

 and it is useful when in the probability the distribution is one of the well known ones。

 for example， the uniform one。 This is what we will do， example。

 it is useful to rewrite this integral in terms of variables in R。 And for that， we make use of the。



![](img/5d86be08ec84b983d08a24c79468ec70_23.png)

Cumulative distribution function， F O Z。That to each real assigns the probability that the the So it is the commmulative distribution function of the random variable C。

So it assigns the probability that for the events in the sampling space。

 the random variable is smaller than Z。 So here it's a number between C 1 because the probability know。

 here， here is a number between C 1。 And Z can be any， any real number。

 And so it is a more handy object to in integrate with respect to the CF than to make the integration here with respect to a probability measure。

So paired with the CF， that is the one minus the commutative distribution function that is called the tail of the distribution where we see the probability that the random variable is larger than z。

And then it was here where they not it with a bar on top a bar C。So。here。

 the sum of those two functions is equal to one。Okay， so now to make all our calculations。

 we will take then the records cost equal to one so that we have our records function。

Equal to absolute value。 And we will consider instead of a discrete distribution。

A uniform distribution now， it continues。Uiform distribution in the interval。A B for A and B。

I don't know。 here I put。Let me put parentes， so that we don't have。Squares， twice squares。Maybe。

 so the comparison that we will make will be to respect to a equals 0 and B equals 3。So， uniform。

In0 3。Even from distribution in serial 3。So we that is U。 I will give you hints。

 will show that this function fee， in fact， is a very smooth function。

 And for each x0 in the interval where the uniform distribution is defined Ca this form x0 square plus x0 minus a square divided2 times B minus3。

 In fact， I made this calculations， I didn't take it from any， any book。

 So you will tell me if I made the calculations， right， Okay， I think it is okay， but in particular。

 you see that if we take a equals0 and equal equal 3。😊，Our distribute， our inspect records function。

Wouldd be 2 x 0 divided by 2， divided by 3。 So it's one third x0 square， right。And then。

 you can compare。X， sorry， square you can compare with the continuous with the discrete version。



![](img/5d86be08ec84b983d08a24c79468ec70_25.png)

Okay， so how is it that we prove these relations we will use， as I said。

 to make the integral here a relation that you will also show between the。

EIn with respect to the probability measure and the integral involving the tile of the distribution so that we can integrate in R。

EAnd for that， we need to know what are the probability， the CF and the tail of the uniform。

Distribution， and then for a continuous version， then we have the detail。The titleno， the CF。

 So the probability that the random variable is smaller than the left interval extreme of the interval is equal to 0。

Then if we are to the right of the interval， the probability is equal to1 because we have like explore all the interval and this is expression if we x is in the open interval A V。

 A B。😊，And the tail， while it the symmetric or I don't know the corresponding relation so that we always add to one in these in in each line。

 One， if C is smaller than a， this expression in the open interval and 0， if C is larger than B。😊。

So with these expressionspirations， then now。The first important result that you would have to show is that。

Thespec， and this is general。 it doesn't depend on the distribution while considering it。

 If we have a random variable that takes non negative values， That is our case here。

 And this is why we are staying we taking here a large or equal to 0。

Then the expected value of the random variable。 So what we use here in the integral the probability measure is the same than integrating between0 and plus infinity the now in R。

 So with respect to the this the variable that well looks at the probability of C is smaller or equal than or larger or equal than C。

So this is a result that。You have to prove， and。I will。

 I will tell at the end of the class when you will send it and where you will send it scan or give it in hands to me。

So。Then now， why， how is it that we use this， We have our respected。

A recordss function or any or any。And in number， in R。

 then we can express it as the sum of the positive part and the negative part。Then。If we do this。

We will have our random variable。That e will be a positive in both cases， C plus and C minus。

And then we， we will write our respect our function C is the expected value of this。Records function。

Then we will compute the individual expected values of the positive part and of the negative part。

Okay， so in the in this case， then we can use these results， this here。

To show the those two equalities。And wait， that means you again。So this is an exercise。 It's a。

 it's a， it's a homework。EThat the expected value of for the。E now it is now here， yes。

 This result is for the uniform distribution in in A B， you have A M B。

Then the value of the positive part。 Then it's integral。 and we are evaluating at x0。

 So here we have is the integral bit， It's the integral between x 0 and B of the tail。

 This follows from these relations and the part of the expected value of the negative part。

 Its the integral between a and x0 of the C S。😊，So this is this can be shown use in this result。And。

Well， here there is a hint for you too。ETo that can be useful for these relations。Well。

 and then once you have these equi， you just need to add those two expectations， expected values。

 And then we get our function p。 and it just well have to integrate a very simple function that will be quadratic。

 so that we get our function p， for example， here of this form when a is a 0 and B is3。Okay。

 so this is the my gift， my Easter gift for you。So to do these， these calculations。Okay， so。

 well now actually， I can say now。I'm getting hot because I got to wear this for the microphone。

 So I maybe you can。 yes， let's fix the date and let's fix where you will send when if you are not here。

 just scan the the So this exercise， the you respond and send it to Z probe。嗯。No， okay。

 listen it was。Svan pro。At I dot B R。Al I don't know how to write in parallel series。 Okay。

 in parallel B are。呃。Before。Next class， it will be 29。29 is nice graph。Okay， then。Let's say the3。嗯。

Okay， so it's something to do some exercise calculations to do while you are in the bus coming in to import something。

Okay， so now let's let's now yes， go into the optimality conditions。And as usual。

 we will separate the case where we have a finite support or a continuous， continuous one。

So what what do we mean by optimality conditions。We have our two stage schastic linear program that now were right in this form。

 So the linear first stage cost plus the expected records cost。

And we take our here and now variables over a polyheum that is of this form。

 No negative variables and equality constraints。And well just for fixing the dimensions， the matrix。

Has N， B lines and N X columns。 Let's say， a these。And beat。Times。N x。Okay。

 and since we are in the finite support case， we have case scenarios。

 and then the expected value is just the sum with the positive probability of evaluating at each x the。

Realization of the individual scenario K that here we wrote in the general form C， K。

 because now we are no more in illus example And C K is C of W K， right。

 is the random variable evaluated at the case event W K。Okay。

 and then that means that we have put we have to put case in all our random data， Q， W， H and T。

 and we have the primal and the dual expressions。Good。

 so the optimality conditions are a set of a system of inequalities that。

The data has to satisfy at a certain point for that point to be declare a minimum a solution to this problem。

For example， something that the problem has to the this point needs to satisfy is to be feasible。

Things like this。 And that is always attached to the primal object that solves the primal problem。

 multipliers that are related to the constraints here in those ones or here to the variables in the dual formulation of the second stage problems。

Okay， to make our proof， we will need to show some results。 So we will start。

 And this is independent of being continuous or discrete。

 Those results hold for because there is no distribution， in fact， involved in these results。

 So let's prove this the first one。Reing that。 So we said that the point needs to be feasible。

 So it needs to be in the set capital x and capital x。Is a set of points。



![](img/5d86be08ec84b983d08a24c79468ec70_27.png)

是啊其他。X is larger than 0， and Ax is equal to B。Now， to the a function that。

A senses a value to the fact whether that the point belongs or not to this set is called the indicator function。

A。A ghost from R， N X。To the extended three else。Se that to each x。It assigns the value 0。

I x sorry here。 So it is called the indicator function of this set x， so 0。If x belong is feasible。

 So it is in our set and plus infinity otherwise。So if the set X is close and complex。

 we have a question。

![](img/5d86be08ec84b983d08a24c79468ec70_29.png)

Un。Yes， it' with one。 it will be full domain。 we will apply it。 Yes， here there is an neat mission。😊。

Let me go back to the first one。So， okay， so if x is close and conve。



![](img/5d86be08ec84b983d08a24c79468ec70_31.png)

Un come backs， well are not empty。Then this indicator function is proper and complex。呃。Proper。嗯。

Convex function。 It's a convex function， right， but it's a proper convex function。Now。

 what is the subdi of of convex function。 It is the set of all the sub gradientients and the sub gradientdients where the slopes of all the hyperplanes that were tangent to the function and supporting the graph of the function from below。

 This is a fancy wording for a very simple relation is that S belongs to the subdi here of this function X。

At x bar。If and on Eve。I X of x is larger than。 So the graph of the function stays above。Hyperplan。

That passes through X bar， and has slope。S， and this for all x in。In。儿。N X。Okay。

 so from this relation， we have then to characterize what is a differential of this indicator function。

 Then the first observation is， well， x bar is feasible。 So it's in x。

 We're assuming that x bar is in x。In capital x， then this means that this value is 0。

And then what we have to find is slopes as such that this inequality holds。For all eggs。In our。

 in our end。What this is， Who is is。Okay， so if X is not in the set。This value is plus infinity。

So it holds the， the inequality holds trivially It for N E S doesn't matter what S is。嗯。So， any S。我。

Satisfy the relation。And if the so we have to look。 So this is one case。 The second case。

 if x is feasible， x is in the set capital x， then the indicator function is 0。So， S needs。

To satisfy。They你过里啲。0。Rather than is transpose x minus x bar。

 And these for all x in the capital x set。嗯。And this reminds you of some。Definition。

 and if it doesn't， I will。 This is a definition of the normal cone。Of the set X at the point X bar。

 the angle between the normal elements and the differences of points that are in the set needs to be up so that this。

 this scatter approach is negative。Right， this is a definition。Of this。Is equivalent to say。

 to saying that S is。En normalmal element。To the set a capital x at the point， X bar。So。

The sub differential of an indicator function have approved。That first result。

The sub differential of an indicator function at the point X bar with X bar in the set is just the normal cone。

The con normal to the set at that particular point， X。Okay， so we pursue our characterization。

And then we will see what is this， the normal cone to this polyhedron x bar x capital x that has specific form。

 So now let's go and prove our second result。We have our set x capital x that is given here。

So here we finish our proof。And then we have the normal cone。The definition is the set of。Elements。嗯。

And。In a。And。And x。Such that or here we call them S。 Let's call them S。 Okay， let's call them S。

 It's okay。 S in and X， such that。S transpose x minus x bar is smaller or equal to 0。For all。X。

Facebook。And then we have this other set that we have to prove that is equal n。And。That is a set of。

No mean R and N X。Of the form that used the specific structure now， of the set。

nu is equal to minus a transpose mu minus p。For some vector new without any。

A specification that doesn't have to satisfy any， any property just to be in the right。

 have the right dimension that must be And be here。And P， yes， it has to satisfy some conditions。

 P has to be a in okay， P， I will write it here。 So that is similar to how it's in the black screen。

 the slides P is in R N E X。And it has to be not negative。And。There is some complementarity。

Between P and X， there is not some complementity。 There is complementarity。Blesss。 somebody sneezed。

So the E scar product between this non negative variable P and the non negative x bar because x bar is in in the set capital x that has only non negative elements have to be 0。

 So when x bar is strictly positive， P is 0。 And when it x bar is 0。

 it can be P can be 0 or a strictly positive， it doesn't matter。 But what the complementarity。

 This is a complementarity relation。Okay， so I will prove one inclusion， the E C 1。

 and I will let you the difficult one。 and you will add it to the scan， okay。



![](img/5d86be08ec84b983d08a24c79468ec70_33.png)

So we will prove this inclusion。No， we will take then a new office form。

With those properties for the P term。 And then what we have to do is add this in a product here and see if the sign is negative。

So， a neutronpo。And take then。X in capital x， x we have iss given and it's in capital x then。

So we will do the inner project between nu， nu and the difference between x and x bar。Here is minus。

呃。Now right to everything minus a transpose mu minus P transpose times x minus x bar。

So now we distribute， this is minus a transpose mu。Transpose。X minus x bar minus P transpose。X minus。

Ex part。So here。Transpoing means that we change the order of the the product。

 So we have new transpose times a transpo transposees a。Times x。Minus x bar。

Minus the same term P transpose x minus。Next spot。We are We are not but。

 We're already there because x and x bar they are both in the set capital x。Pre。

So a x bar is equal to B， and A X is equal to B。So， this product here。Is B minus b。

And this inner product is 0。嗯。So， this is equal to。0 minus。P transpose x minus x bar。

And now we look and remember what is it that P was satisfying as condition。So P p transpose x very 0。

 So the second term vanishes 2。 And we are left with minus P transpose x。嗯。And B。Is positive。No。

 not negative。X is not negative。The inner project then is a negative minus。

 its smaller or equal than 0。So， we proved。The inequality that we needed to prove。To show。That no。

Be no to the normal con。Of x2 x as it x bar。The reverse inclusion uses some in hyperplan results so。

Do it and scan it and send it。 sendend it to spark in spaamp probegue。 So also before the search， so。

N contains an X。Of x。Homework。Sant probe。3。Okay， good。So， who have probe。

The first result half of a second， we will use this。Now， we need。

To to know what is it that characterise is the minimum of a function that by the way， Okay。

 before going it here， let me motivate。 Why is it that we are doing all these calculations。

 Remember that we want to solve the the。

![](img/5d86be08ec84b983d08a24c79468ec70_35.png)

To find optimal conditions for the first stage problem that is of the form minimize。

C transpose x plus。They expected the records function， subject to。X in x。

So this is the same than mini medicine。For x and constrain。C transpose x plus phi of x。

Pla indicator function。Of the set x at the point， x。X x。S better than in Portugue she some。

So this is a utility of indicator functions in in optimization is that it allows us to get rid of the constraints via this object that has a disadvantage that brings us to extended reals。

 right， it introduces infinity。 So from the numerical point of view。

 this is not a good transformation。 But from the theoretical where we have to write automatic conditions。

 It is。 So then we will be working with a function of x。😊。

Equal to this C transpose x plus so the linear term， the record。

 the records term and the indicator term。嗯。

![](img/5d86be08ec84b983d08a24c79468ec70_37.png)

So if we connected the ice， So it， we will be dealing with an optimization problem of this form。4。

A function that goes into extended res。And this is a setting， and it convex proper。

 So this is a setting that we're considering for character characterizing the optimal value。

 the an optimal a minimizer of this problem。 So X bar minimizes F in the whole of space in R and X。

 If and only if the sub differential of this function includes the 0。

 This is a generalization of the the condition0 equal to the gradient of the function at X bar。😊。

Good， so let's now go and do our。I will proof。Okay， I will not be late。

 I will write it again if I need it， I will erase it。Okay， so it is not very difficult， in fact， to。

 to prove this。To， to prove this equivalence is just the definition of the sub differential。So，0。



![](img/5d86be08ec84b983d08a24c79468ec70_39.png)

Belongs to the subdiial F of X bar is equivalent to saying that the slow。

 the hyperplane with slope 0 supports the graph of the function。 This is a sign that saying that。

For all。X。In the space。F of x。Is larger equal than this hyperplane that is F of x bar plus0 transpose。

X minus x bar。0。 It is term is 0。 So this is equal。Then f of x bar。

So f of x bar is smaller than f of x for all x in our N。

 This is equivalent to say that x bar minimizes F。都。This also is here。 It's a very simple result。

 but is is very useful because now。

![](img/5d86be08ec84b983d08a24c79468ec70_41.png)

Let me see。We can go。 No， we can this， we will not approve。

 this is a consequence of the Mooro Caeller theorem。 It's， you can。 it's well。

 I will just try the name。

![](img/5d86be08ec84b983d08a24c79468ec70_43.png)

The CRM。も。我说咖啡了。And by the way， Modo will not come because he passed away last year。

 but Rockefeller will come to our thematic program and will give a special conference in the week of the 20 of June as part of this our。

 our the program。😊，ESo the theorem of Moo Cafela establishes conditions under which for a a convex function。



![](img/5d86be08ec84b983d08a24c79468ec70_45.png)

That is defined as a sum， in fact。Sequl to F1 plus F2。呃。4。Wen。The sub differential of this exam。

 I mentioned this in one of the first classes。At the point is equal to the sum of the sub differentials。

And this involves conditions that are called regularity conditions and are related to what nonlinear programming people call contrain qualifications。

When， as it says there， so there you can go and see the result in the in the Shapiro。

Chaban Rohiki book in the。Chapter 7， I think is in the background material。

So when F1 of F2 are polyhedral and we have also were considering that they are finite value。

 In fact， so they set differential， all these results in more Ca results are。

Meaningful for functions that are extended have extended real values。

 Well when we have infinities because the self differential of。

 you can think this function may have an infinite value at X bar。

 and then the sub differential will be the empty set。While， for example。

 the sum of the two functions at text bar may be finite。

 So you may very well have the subdi of the function defined as a non empty set。 a text bar。

 But one of those two may be empty because of the because the function became it has an infinite value。

 Well， and then this is why you have to worry about this spreading the distributing the subdi。

In the alone along the sum，4 extended real value functions。

 for functions that are real value that do not take plus infinity values， the quality always holds。

When one of those conditions that are given the regular conditions that are given in this motor caferal C R M are automatic when the functions are polyethedral。

So， this also holds。When the functions are not polyed。

 if the intersection of the interiors of the respective domain。 So here int is missing。

So if there is a point that is in the interior of both of them。

 then this somehow helps to get rid of infinities and empty sets。 And then we have their quality too。

But while this is all what I would say， and you will not have to prove it is just go and read all the conditions in these CR R M of Moocca。

 if you are interested in the in the details。Cool， so now I think I have。A tone。

Everything I wanted to show to prepare our the the proof of the CR。So let's let me see if we go back。

No， we'll go forward。唔继叔。Another thing， sorry。You see that。The characterization of the subdient。

 including the0 sub gradient at the point X bar is gives a condition that is necessary and sufficient for x bar to minimize F。

 This is because a function is convex。Right， so it is a necessary and sufficient condition。

 and we are here in the we are always dealing with convex stochastic programs。

 the linear case or the convex case， where instead of having for example， a linear cost here。

 we can have a convex function。 we are always in， so we would have F1 would be a convex function。

 we are always in the convex world for all the results here， that are。

Some methodss and some results are non complex， but they will， of course。

 we will only have these would characterize critical points。 stationary points。

 not there would be maximum minimum and southern points。



![](img/5d86be08ec84b983d08a24c79468ec70_47.png)

The characterization for convex the full characterization is only for convex function。

 So for our case， we are in the everything is convex， we。This is a convex function。

 This is a convex set， a polyheedral set， and this is that expected record function is also convex。

Okay， so we have a necessary and sufficient optimality condition。



![](img/5d86be08ec84b983d08a24c79468ec70_49.png)

That we will show first， then for this， the case where we have a finite support。 Okay K， scenarios。

 W 1 until W K。So， saying that。EPo X bar solves the two stage stochastic linear program。

Is equivalent to saying that we have multipliers。 Remember that I mentioned that there is always。

 it's always primal dual， these characterizations， one for each of the scenarios under consideration。

And we have a multiplier that corresponds to the constraint in the set capital x， A X equal B。

Such that if we consider the records function evaluated at X bar。For the case scenario。Then。

 so if we maximize like this， this is Q of X bar at C K。 Then those multipliers are maximizers。

 So they saw they give the value of the the record function at X bar。 So at the optimal。

At this point。And the Sam。Well these inequality holds， P， K， T， K transpose。

 P bar K plus A transpose mu is smaller than C。And there is a complementarity here。

 condition between X bar and。What would be the negative No if you pass to this side of this vector here。

So when this one is has components that are strictly positive here。

 there is a equality at these constraints because this needs to be0。Right， this is what they saying。

Okay， so。I let you guess how we will show this。 We will use all these results that we proved before。

😊，And we will pass through the characterization of a solution of a convex problem。

 That is the two states stochastic linear program of finding a0 element。

 a0 gradient in the subdi of our function。

![](img/5d86be08ec84b983d08a24c79468ec70_51.png)

So now， though， we come here。嗯。And for our。I will need more than one black person raised here。

For our finite support case。So， we will have。That the two stage stochastic linear program is。

minimize if。Of eggs。呃，X0。嗯。X。4。If will have three terms。It3 transpose x plus。Fe of eggs。Plus。

 indicator function of our。First stage， feasible set。

And C of X is this the spectral records function。 So where。



![](img/5d86be08ec84b983d08a24c79468ec70_53.png)

C of x。Is the sum over all the scenarios。Of the probabilities。

Times the spec the record function evaluated at x at the scenario， O。Okay， so to apply our。

Reult here that。嗯。Here， we first need to see that F is proper and convex。挂了呃。

This is a linear function。 This has full domain。 So let me call it。If one。F 2。F3 no fix。So。F1 of x。

The domain of F1 of x is， while it's linear and the domain is the whole space， So is。R and x。F 2。

Well， and it's a linear function。 So it's clearly convex and it's proper。

 Then also has the full domain。 The records function。 we also show that。The， the domain here is the。

 the domain of this record function is the positive hell of W。

 So and here we are in a finite support setting。 It's also I have two。

The domain of it2 So we it also。Mine of f2。Is a。What。The intersection of all those positive files。

And F3 is the domain of F 3 is the set capital x。嗯。Okay。

 so having inter and what theres actually So all those， this is a sum of proper functions。

 They don't have infinite value minus infinite value everywhere。 The values where it is finite。 And。

 in fact， our result is supposed。Let me come back here。

That we have a point so that our set first I set is not empty。

 and where the records function defined finite。

![](img/5d86be08ec84b983d08a24c79468ec70_55.png)

So。诶呀。Our the。F is proper and convex。And therefore， we can characterize a solution。Mimms。

The two stage linear program。If and leaf， srup belongs to the sub differentialent of F a text bar。

Now， in the finite support case， we know not only that the function fee is proper and and convex。

 but we know that its polyhedral。No。Okay here， because。Omega has finite support。Phi is polyheedral。

And now I I ask you， the linear function is called Heral。

It is the simplest case of a polyheor function。 So F1。Is polyhera。

The definition of polyhedral was that the function is the sum of a maximum of a fine functions plus the indicator function of a polyhedron。

So， the if。A linear function is polyhedral。 And because I said capital x is a polyhedron。

 the function of3 is polyhedral，2。And so。F 3。So we can use the mod rockefellereller result。

And then we， we have that X bar。呃。Miniises。If。He said， weban。

To0 belongs to the sub differentialent of one of x bar。Plus， the sub differential of F2。不。

This sub differential of F3。Okay， so who is F1， F1， It's a very simple。

A function that is differentiable。 And so the sub differential is a single tone。 It is the vector C。

They set the differential of F2。We showed or I don't even。 we showed， but we wrote。

It's the sub differential of the expected records function。

 So because the probabilities are positive， it is the sum of the probabilities times the subdi of the expected records function。

Ss functions。 So with thisM。And the sub differential of F，5 3。

Which has shown it is the so sub differential。Of the indicator function of these。Polyhedron。

 So it is a normal cone to this polyhedron and the normal cone。Has the。Expression， knew in R。And B。

Such that。My nnu is equal to minus I transpose nu minus p。Form。And B。第。And X。

No negative P complementary with x bar。Okay， so we have piece together all the parts。

The only thing that is missing now is to。Remember what was the subdi of the records function for each fixed scenario C K。

 And here is where we are were using dual theory in linear programming to characterize all the vertices all the of the feasible set in the dual formulation。

And then， we had that。4。The sub differential of the records function at the fixed realization。

Was and we write it like this。 I said T K transpose。And all the solutions of that well。

Now will not fit there。 Okay， now we'll write it down here。4。Subdi。It C， K。Equal to the minus。Di。

Okay， transpose the technology matrix times。嗯。They said to maximizers。Of the two world problem。

To our second stage problem， P， H， K， minus T K X。For P， such that W K K transpose P smaller than Q。

Okay， so this was the said P of of Qk。Good， so we know then that。诶。

0ro belongs to the sum of these three sets。So， we have to。Put everything together。

 So0 belongs to this inclusion means that there is one element。

 There There are elements in each of these sets such that we have0 inequality。So。呃。I would。

 write here the。Ciro， now， let me see how。How to write。 So here there is only one element。 So we see。

In the sub differentialential of F2， there is some P K that is how it is called in the in the statement。

In this set of maximizers where we have0 equality that makes the inclusion true。

And here in the set of the third function， we will have some normal M element that we will call nu nu K。

 And to this new K， there will be associated mu K and P K and mu will be that the one that is there。

So。呃。The inclusion。Mans。Or halt。T on the if。That is， so。Pk here， and they said。PK。

 it is for each realization on K between1 and K。Sa that。呃B呃那是C。Here。应对。A maxax。

Of the second stage problem in the above in the linear in the dual formulation。

There is then here new。呃，New bar， not new K， sort of new bar。Here， we don't have K。

 K is here the same。Beking a 4 k between one。Okay。There is a new bar in the。Normal con。Okay。

 such that。0。😔，Is equal now。 So this is the elements。

 the these are elements that make this inclusion true such that then。C。Serious equal to C。

Bless the sum of。Be gay。-3。Okay， transpose。呃B。H。Yes， it's O。 And plus no bar。No bar。

 I think I call them P R K。 Let's put bars here so that because it's for each K， each scenario。6。

They were okay。And no。Okay。Good， so a new bar。Is equal to here。

Minus a transpose Mo bar minus P bar for some。Of elements in this satisfying this condition。

 So minus E a transpose。We were minus P 4。We were non negative and complementary with X。Okay， well。

 but we are there because now you see。The P case， paper case are in the sets where we want to。 Now。

 we need to show these two conditions。 And you are just guessing that all this term， in fact。

 will be our。

![](img/5d86be08ec84b983d08a24c79468ec70_57.png)

A positive term P in the normal element because it's complementary with X bar。H。

And this will be well， no would say what this what it is。 So now let's write here。

The what replace by no bar in the。Relation we have in the identity。

 we have then for the sum between one。Go be done gay。P， I will put the term minus here， So minus。

T K transpose P bar K plus。No bar that effect has only negative terms， or minus。A transpose。Mbar。

Mine of。B。This means then， that all these。Okay， so then with P letters or equal to 0。

 So minus P is moderate or equal to 0， so。We have that C minus the sum of k between one and K of P。

 K， T， K transpose P bar K minus A transpose。明白。嗯。A smaller。See minus。Is equal to。Is equal to P bar。

Right， then adding imp to both stands。And what else was operate then P equal to c minus。

 and then P bar is less or equal to 0。Then C is larger or equal than the sum of those two terms。

And this is our first relation。嗯。Good。So。The second bullet。No。Theer bullet， also is。Straightfor。

 because P transpose bar。Since。T bar transpose X bar。Is equal to 0。This big review of the equivalent。

 the relation here。 this is the same saying that I wrote first x transpose P。 Okay。

 that's write P transpose X ver as。X transpose P。哦。By。Do。

Is it the same that saying that x transpose bar。T trans X bar in a product with C minus the sum of P。

 K， T， K transpose P bar， P， K minus。A transpose new bar。Is equal to 0。And this is a third。Borole it。

Okay， so this is I have not completed all the if and only， if， in fact。

 because what I what we did was to show that if 0 belongs to the subdient。

 then the conditions called right， because we are showing the three conditions。

 Now to go the other way， it's it's rather simple because we just need to prove that with these conditions。

This vector here。We can be in the vector nu， such that。The， the sum is 0。

 And since this belongs to a sub differential of F1， this belongs to a sub differential of F 2。

 and this belongs to a sub differential of F3， F 3， then。0 belongs to a sub differential of the sum。

 And this is the same that it belongs to a sub differential of F at X bar。 And then we finish。

 we come back and finish with the E final E proof。So， these finishes concludes。There are。The proof。

Of a。X bar minimizes。Implies the three conditions。So， you can prove them。The reverse。This as I said。

Can受。The reverse。Implication。You have all day。All the tools or the weapons to kill this trophy。Okay。

 so。For people who is familiar with linear programming。

 this is resembles a lot to the linear programming conditions。 the primal dual conditions。

 This is so complementarity。 this corresponds to well here we have the dual feasibility。

 And this is related to to primal optimality， prim primal un dual optimality。

 And this is the condition on。EOn S3 complementarity。

 prim and dual feasibility follow from the fact that we are saying that X bar is in x and that T bar is in the set in the dual feasible set。

Good。There is another way of making this proof that doesn't use the results of sub differentials。

 And is' just remembering that in this finite support case， we can write our stochastic。

 the two stage stochastic greener program， not in two levels， but altogether。 It is the same。



![](img/5d86be08ec84b983d08a24c79468ec70_59.png)

![](img/5d86be08ec84b983d08a24c79468ec70_60.png)

This will not be the case in all the situations here。 I forgot P here。

 here there is the probabilitybabil missing。So if we write altogether as a large linear program。

 the the two stage problem that is with here and now variables and white and C variables。

 then we obtain a very large linear programming problem。 Everything is linear here。

 Here it There is a P I missing。You see here now we have variables， X and Y。

 K will resolve all at once the。The here are now the and the corrections for all the possible situations we foresee。

In our sampling space， that has case scenarios only。Okay。

 so we can write the optimality conditions for the linear programming problem。

 And then you will get something。

![](img/5d86be08ec84b983d08a24c79468ec70_62.png)

That is。To be like to， to compare to， to be equivalent to what we have as the three conditions needs a little。

 a little trick。 And it is that when you write the lagrantian and the dual world and you see that there is no reality gap。

 and then you equate objective。

![](img/5d86be08ec84b983d08a24c79468ec70_64.png)

primal dual objective， optimal primal objective with dual optimal dual objective here。

 the multiplier that depends then on the scenarios we don't use the standard in a product。

 but we use in We we multiply by the probability P K。

because the probabilities are equal air positive。We have hereequities， nothing changes。

 And if there were inequalities， they would not change inequalities， we would have the same solution。

 And then we write the， the optimality conditions for this， this problem。 And this is the way。

 So we have to multi here by the probability P K when writing the the。 And then this means that。

 in fact， we are using product that is weight。 Its correspond to what is called do or pairing in the probability space。

 we are always having the way of the probabilitybabilities。 when we use。

 when we make the product between primal and do or variables。



![](img/5d86be08ec84b983d08a24c79468ec70_66.png)

Okay， so。Then， just to finish。What happens if we have a continuous distribution。

Exactly the same result can hold。 And I wrote here the statement for a case with simple records。

 So the simplest of the fixed records is it is not in the in the book。 It is a particular case。

 but you can this is in simple records。 Remember， every object that is to be uncertain is random。

 except for the right hand side variable age。And so we have only h of W。 And then moreover。

 these metrics， the records matrix is of the form identity， minus identity。So in this case， why。

 why I wrote this is because I don't have to worry about a lot of technical assumptions that need to be applied for splitting the sub differential of the sum in the sum of the sub differentials。

 because with the expected。So it is essentially the same process， but we will not have sums。

 We will have integrals。When we， when we did with the record function， but what we。

What we have is that。For spliting the sub differential of the sum in the sum of the sub differentials。

So now we will be dealinging。嗯。Okay， sorry， I have a code。 I have no idea。

 I would reject it because I don't know who it is。And it's a tablet。 It's not a phone。 So we have。

EThen。Okay， so come back。 tell what I was say。 So we have the three terms， right。

 we function f of x with the continuous distribution。 Then again。

 is F Y of x plus F 2 of x plus F 3 of x。😊，F1 is easy。 It's just C transpose X。

 F2 is the one that is more delicate， because。It's expected record functions。

 and we have integrals now。 And F3 is the the same one of before and before。 So it's also not。

 not the problem。The potential problem can come from C of x。

 but we show that for that we when we proved thinking this blackboard for the case。Of simple。

 fixed records。The records course is complete。And呃。Records。Is complete。

And because of the particular form of our matrix D W， we have that the domain of the function。

Is is the positive hell of the value。 And this is actually the whole space。2M。N x。No。

 N N M was here in Y in the matrix in the y dimension and why this is of use。

 because let's go back here。 So here， the domain of the first function is the code of R is。

 is the herd of the space。 Now， then is I X is X。 sorry。 So is R N X。嗯。😊，Fi。Yes， thanks。X。No。

 it's not both。 It's the code of our n here。 is R n x。This is what we showed in last class。 So here。

 the first function has full domain because it's a inner function。

 The second function C has full domain， because we're in the very simple case。

 in the case of S fixed simple records。 and the third function has the the set capital x as domain。

 So the intersection as if we are assuming that X bar is in x。

 it holds three value and we can split the sum and apply the modoccaeller CRM。 Otherwise。

 there are some in the CRM in the book， there are some assumptions that are technical and that introduce for that reason。

Okay， so then what's the difference， then if everything is equal was the difference。 Well。

 the difference is now that。We have， then。EThe multiplier P before you see。

The dimension of the multiplier P。In the final support case， there are as many as scenarios。

 When omega has an infinite number of events。 it's a continuous distribution。

 Then P becomes a function， a random variable， and it's a function of the scenarios。

And then so P for each omega， we have a P， we have infinite omega。And then P。

 iss a measurable function， measurable function。 like when we were well。

 like along the lines of what we， we saw last last class。So， one that。Yes， that's all。 I will。

 I okay。 So I had written。 So because of the， we have simple records things。

 So things get simplified and there are not a lot of conditions that are technical and that are important to be aware that they have to be satisfied for the cases where records is relatively complete。

 for example，Okay， good。So。What they will do is maybe put。But we are almost done。 Okay。

 and it's a mute。 That's strange。 Okay， nobody ever calls me here， must we。Okay， so。

Other than another， another thing， how do we write。

 How can we simplify then the optimality conditions， Sorry， let's go back。Here。

So you see that our characterization involves sums multiply by T K in the continuous case。

 This becomes expected values。 It's a integral over with taking the integral with respect to the measure D P of omega and T of omega P of omega and so on here。

 So in these two terms， we will have expected values。 And this is since we are in the simple records。

We don't have T。 T is not random。 So we'll get out of the expected value。

And then all the result is that。T plus respect value of our measurable function P that depends on omega plus a transpoome is smaller than C。

 And there is complementarity。 And now this term has this expected value。 So theity conditions。

 a translation from the continuous， the discrete to the continuous universe and everything is well。

 is as it should be。 there are no prices。Okay， so do we have questions。Yes， we have one question。Who。

给呃。It is one。 It's any。 Its it's one。For each W， it is a set。 but the there is one。

 we are not saying that iss unique。It is one that satisfies inclusion。

0 belongs to the sub differentialent。Of the sum， there may be more than one。There is no uniqueness。

是第一波。So the question is， if the the question is， if the multiplier P cannot be。

 there is no need for it。 There is no reason for it to be unique。 And no。

 there is no reason for it to be unique。 So P for each value can be belong to a set。

 there is more than one depends if the there is for example， it will be unique， if this constrain。

 there is linear independence here。 there is uniqueness of the multiplier。

 but we do not know what we know is that there exists one， but there can exist more than one。

Where the relation is satisfy for each omega。So， for each。那时候。The yes， there is one that。

There is one that satisfies our relations， and there may be more than one。Inですけど。It records。那处理家。

But because is I minus I。 you're right。 Yeah， yes， yeah。

 So Hua Pablo is rightfully pointing out that in the case where we have simple records or these。

 the records matrix is。

![](img/5d86be08ec84b983d08a24c79468ec70_68.png)

The identity minus identity。 So there is linear independence and P would be unique。

 But in the general case， there is no no reason for it。Okay， some other question。No， okay。

 so thank you very much。 And H Easter and see you next week。

