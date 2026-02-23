# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p05 -05-Basic Course on Stochastic Programming - Class 05.zh_en -BV1tH92YXEnd_p5-

Hello， welcome to our class number5 of the basic course is stochastic programming。

 Thank you for being here。😊。

![](img/a8946f6359ad386be21758ba26a2dc50_1.png)

Today， we will continue studying the expected records function。

 We will study properties that need need to be satisfied for it to be well defined。

 well defined in a sense that is specific to functions depending on。E random variables。

 And we will also revise some concepts that are known to mathematicians and not as known to engineers or computer scientists。

 such as measurability and probability spaces。Okay， so as standard， we have a resolution reminder。

 and also a question on the homework that was， it's an observation。Ned by Eli De Carters from。

Pama Kriivva。 So in the homework， we had some normal distributions with mean 0。

 And then the second parameter was 9 or6 or 16。 Now， depending on the book。

 you will see the second parameter is the standard deviation or the variance。



![](img/a8946f6359ad386be21758ba26a2dc50_3.png)

嗯。So I would say that here， since this is a square。

 and these two this I would tend to think that I would tend to take it as the variance。

 But in the examples that we ran in the first class with this common M VN。

 CMD that Wellington had made， He used the this value square And this is because he was following the notation of the Shapiro and Koer's book。

 and there is the notation of the book by Peter Car and Stan Wallace that uses the variance。

 So while there is this ambiguity。😊。

![](img/a8946f6359ad386be21758ba26a2dc50_5.png)

I would say that we fix that we use that this is the， the variance。 Okay， in this data。Kttle。

We have a senior student who arrived just now for everybody who is not here。So I am。

So this is then sigma square and sigma square for your rank。 In fact。

 if you want to play with an observe what happens to the solution in terms of reliability。

 you could try both， right， and， and observe you will be generating if this is sigma instead of sigma square。

 that means that scenarios will be more different there is more volatility。And then， in principle。

 they。Reliability of the solutions found by the different stochastic programming in formulations。

Should be less right？ So well maybe you can check。 you can play a little bit if you already have made your。

 you can play and see if you observe notice some difference。 And then well， let us know and or also。

 there may be some formulations that are more robust with respect to changes in the in the variability in the value then of the standard deviation or use in the square world。

 you will see probably it's likely that the chance constraintsstrain formulations will be less effective。

 right， since we are solving a risk neutral model where always we use as measure for。



![](img/a8946f6359ad386be21758ba26a2dc50_7.png)

![](img/a8946f6359ad386be21758ba26a2dc50_8.png)

![](img/a8946f6359ad386be21758ba26a2dc50_9.png)

Evaluating the way of the record decisions in the first problem。 we use the value， right。

 This means that we don't really care much about the variability。 We care about the。Average。

 behavior of their。The cost of the records or the records cost。

 So there should not be so much difference， but in the objective value， the optimal objective value。

 but there can be variability differences in the reliability when you make your simulations and you analyze what is the。

 the percentage of。Situations in which the proposed solution is。Feasible this there。

 you should see a difference。 But while， anyway， you will tell me， because all this is my intuition。

 I I'm not sure。 So you will make the rans， and you will tell me。



![](img/a8946f6359ad386be21758ba26a2dc50_11.png)

Okay， so now let's go。Into our recur function， that its a very important one， since we are。

Given to it quite many lessons here。 So we have that and the reasonable assumptions having。

 for example， both feasible sets non empty we have equality between the primal and dual formulations of the linear programming program that to each。

X and each realization of uncertainty in the elements that are considered uncertain， fixed。

 So we have a quality between the primal and the dual formulation。

And then we wrote our records function as a function that we call V。 that is a support。

 the support function of this set。 and compose with the a fine。transformationform H minus of T X。

 And then we， we analyze the subdi of this function V as the set of all all the maximizeimrs and the complex combinations of all the maximizers of the dual formulation of the second stage problem。

Okay， and then the sub differential， then we， when we apply at the fixed x 0。

 then the for the composition between V and the f transformation。

 we have the sub differentialent of each individual records function that has this form。



![](img/a8946f6359ad386be21758ba26a2dc50_13.png)

Simple。

![](img/a8946f6359ad386be21758ba26a2dc50_15.png)

So this is a set， right， if we have more than one maximize certain here。



![](img/a8946f6359ad386be21758ba26a2dc50_17.png)

Well now the beef and the difficulties are in computing the sa of the expected records function。



![](img/a8946f6359ad386be21758ba26a2dc50_19.png)

I'm not a vegetarian。 That's why I speak about beef， okay。So， things。

The difficulties in making the valuation in computing the sub differential are very the level of complication is very different depending on the support of the random variable that were which we take the expected value here。

If the random variable has a finite support， we just have K realizations of K events defining the the the space of random variables。

 we have K scenarios。 So K different situations for C， then life is easy。

And the situation is complicated and is more delicate in terms of analysis。

 If the random variables depends on general distribution， probability distribution。

So the easier case we killed last time。 the Leisi case depends on。 it is less。

 much less simple to establish conditions when these records expected records。



![](img/a8946f6359ad386be21758ba26a2dc50_21.png)

Is finite， for example， And it depends on what is the structure of the records。

 And this means it depends on which of those random elements。 T H in P here that is W and Q。

 So this four elements that define where uncertainty intervenes in the our formulation。

 It depends on which of those elements are uncertain。 And this is called the record structure。

 And there are different names for each of those types of situations。

 So this is what we will see in today。

![](img/a8946f6359ad386be21758ba26a2dc50_23.png)

So with there is case scenarios， this is just。then for each scenario， we call it K， the case real。

 And then we just put everywhere K。 and we w with the probability。 And and we get， then this is。

 again， it a set。It's written in this form， but there， it is L M S that are sum of P。

 K T K and some maximizer in this， in this set。Okay。So， for a general distribution。As I said。

 it is more delicate。And the first concern before computing the sub differential is when the function over which we are taking。

 the sub differential is well defined and well defined is a aiming name in in this probability space environment that。

If we。That is related to。Right in to avoiding having situations where we add and subtract infinity plus infinity minus infinity。

What it is。 And so。

![](img/a8946f6359ad386be21758ba26a2dc50_25.png)

We have the expected value of， let me see。 I will leave it here。

 So I will right in this little corner。 The expected value of some。Random 가。



![](img/a8946f6359ad386be21758ba26a2dc50_27.png)

C is well defined。will put the expected value of a function。 sort of。 let me， let me go to。

 let me keep the same notation。 There is no need to introduce your one。要不急。

If the function over which we are taking the expectation is measurable。So it has a size that we can。

Count， I will explain。 I would give them some。reminderminders of what is measurability。

 And the second is related about is related to writing in a number。 Let's take T and R。

We can write the number T as the combining two positive terms。 T is equal to T plus minus t minus。

 T minus where T plus is a positive part and T minus is the negative part， so。



![](img/a8946f6359ad386be21758ba26a2dc50_29.png)

![](img/a8946f6359ad386be21758ba26a2dc50_30.png)

T plus is the maximum。Between C and T。Anti minus is the maximum， minus the maximum。

Between 0 and minus-1。Those two quantities are non negative。

And we have that the absolute value of T is equal to the sum of T plus and t minus。Right。

 graphically， this is quite easy and intuitive。

![](img/a8946f6359ad386be21758ba26a2dc50_32.png)

![](img/a8946f6359ad386be21758ba26a2dc50_33.png)

We have T and0， then。This line。Is the function。E it the。Now， the positive part。

Is the maximum between0 and T is this one？嗯。And the negative part。Minus a negative path。

I was told that some colors do not。Go well in the screen。 So let me share with the yellow。Or blue。

 maybe。 And you will tell me blue is visible。So the minor the negative path。😊，Is this one minus。My's。

M-2 minus。This one。Is T plus。So the sum of t minus and T plus is the absolute value。

 and the sum or and subtracting T plus and t minus， we get T。 Okay， so this is， well。

 the graphical representation of these relations。 and what this has to do with measurability。 Well。

 well， the the the fineness of the expected value is that the function the。



![](img/a8946f6359ad386be21758ba26a2dc50_35.png)

Either。The expected value defined if Q is measurable， and either。



![](img/a8946f6359ad386be21758ba26a2dc50_37.png)

The expected volume。Of the positive part。A sign it。Or。Thepect value of minus。

The negative part is finite。And in this way， we will not have to deal because since the expected value is just a linear transformation。

 So the expected value of  Q is the expected value of  Q plus minus expected value of  Q minus or plus expected value of minus  Q minus。

 So if one of those is finite， we will not have to be sum in and adding in plus infinity。

 So this is and this depends on which kind。

![](img/a8946f6359ad386be21758ba26a2dc50_39.png)

Of， what are the。

![](img/a8946f6359ad386be21758ba26a2dc50_41.png)

What is the uncertainty in the variables， H， T in the data， H T， Q and W。

 And if they have expected values that are finite。 This is what we would see。 And then like these。

 this this condition would be ensured。Okay， so the answer is here。

 I just wrote in the blackboard what I wrote in the。

 well in the slides what I wrote in the blackboard。 And well。

 the positive part is called expected surplus。 remember that Q is the record function is a correction and it's some a cost that is related to having to correct the decision of the first stage X。

 So the positive part is called expected surplus and the negative part is called expectedus shortage。

 Well， actually here we can put the minus。 Well， if the1 is， if this is finite minus。

 it's negative is also finite。 So if we want the shortage to be positive。😊。

Then we will put the minus here。 Otherwise， well， we can have the convention that shortage is negative。

 and that's it。Okay， so for that， we need to remember a little bit what is measurability。Well。

 many of you know it。 Many of you do not know it。 So I had to choose a way in between。Okay，😊。

Measurability is or what is a measure。 It's a way of defining the size of sets。

 You can think like this。

![](img/a8946f6359ad386be21758ba26a2dc50_43.png)

And if we are in our end。Then we can think the most elementary set in our end is an interval here where component white。

 we have left and right extremes in the interval。The next level of set in our N is close bounded set。

 a。

![](img/a8946f6359ad386be21758ba26a2dc50_45.png)

Then we， so we will first revise what is the measure of an interval。 then for a close bounded set。

Then if the set is not bounded by steel close。 and then for any set in our end that can also be open。

 how do we measure the size of those objects。

![](img/a8946f6359ad386be21758ba26a2dc50_47.png)

![](img/a8946f6359ad386be21758ba26a2dc50_48.png)

Well， the first one is super easy。So we will define the measure mu of the interval。

 It will be just the product of all the lengths of these hyper cube。

Wes a of a measure of of a hypercu。And in particular。

 it satisfies a property that we will see repeatedly when dealing with probability。嗯。

And it is that we， if we take the union of intervals that are when taken by pairs 2 by  two。

 they are disjoint。Then the measure of the union。Is the sum of the individual measures。

So all this is natural and clear。Okay， so now what do we do。

 How do we define a measure for a close bounded set， no more， no longer an interval。Well。

 you can guess there will be sets involved intervals involved。 and there are two sets。

E1 is called a coverin。And the other one is a packing of the set A， the covering。

Is a union of intervals that contains the set and the intervals are designedjo。 Okay。

 so that we can define the measure of this coveringvari as the the sum of the individual in intervals。

Whose union contains a。 And the packing is other way。

The packing is the unit of intervals that are contained in a。Always rejoined。No。

 and then what is the measure of a。Who will look at the measures of all the covering。

And that the measure of all the co since they contain a will be larger than the size of a。

 The measures of all the packings that are contained in the set。

 So the measure will be smaller than the size of a， and we will declare the set measurable。

If those two， the in of one coincides with the soup of the other。So the set is measurable。

 if we take。The infaome over all the coverings of a and the the the measure of all the coverings。

 And it coincides with the supreme of all the。Of the measures of all the packings。

Everything is rather natural and reasonable。Now， if we have an abandonedbound set。So we， so we put。

 we have our set， A， we put intervals， and we see how many intervals。Fit in the set D and。

 or how many we need to just cover all the set A sorry know D said A， And then we take the measures。

 and we can do that because the set is bounded。 Now， if the set is not bounded， what do we do。

Its the mathematical answer to this is go back and see what you know how to do when you have to do for close banded sets。

 Okay， then we will consider the intersection of our set with all the intervals。

 And this will be become with any interval and this will be become in become a close bonded set for which we know how to design this this decide when it is measurable。

 And then if the property holes for all the intervals。😊，Then， air is measurable。

So you see it' it's aum。And it is closed and un'bounded。 Now。

 you have a set that is no longer a closed。 And he said， how do we define。

E measurability the class of measurable sets in our end。So for this。Then we， we consider， then。

An aximatic definition where we have the the class capital calligraph a of measurable sets in L N。

 And with a measure。 So this new。If。EAny time we have a set。That is measurable。

 its complement is measurable， too。That is a very reasonable of assumption。And。Also， anytime。

We have a family of sets that are measurable。 Their union is also measurable。嗯。T there in town。

 then with that， with those conditions， we have our class of measurable sets。

 And because we have here the that if a is in the， its measurable， its complement is too。

 the complement of the union is intersection。 and then these conditions imply that the union of measurable set is measurable。

😊，Then also that the measure of is non negative。Oh the empty set has zero measure。 And again。

 the measure of the union is the sum of individual measures。 If we have a pair wise nu intersection。

Okay， so we are almost where we want to get， except that we are considering objects in our N。嗯。

And for our random variables， we' are considering a sampling in space。 It's omega。

 not necessarily the the space。So what we will do。We will define F。A class of measurable sets。

 a calligraph F E of the sets will be then F subsets of omega。 And the measure。

 now we will call it probability measure。This the size will be given by the probability measure。

 So is our previous new。And then again， this axiomatic definition， if we had。

It said that is measurable。 Its compliment。Taken with respect to our space in general space is also measurable。

 And for that， well， of course， we are considering that our space is a measurable set。

 This is also some axiom。 And again， the union。EOf and then here， we。Take measurable sets。

That are pairwise haveal intersection。 Then the probability of the union。

 The measure of the union is the sum of individual measures。Those side of them。The。

 the axiomatic definitions that well you can see are very much related to， to those here。

 It's an extension getting now from R N。Okay， and who is F。

 Who is We know already that the measure P is the probability。 omega is our。

Abstract space where leaves the random variable。EF is called in a more set in afiltration。

 They set of measurable sets。And in two stage， Well， it's less important。

 this concept that in multi stage that Wellington will play。 In some weeks。

 it becomes an important concept and is related to scenario trees for those who。

 who know a little bit。Okay， and then who are the set F in this setting。

 They set F are what we call the events。 All the possible realizations of uncertainty that whose union configure configure the set the space omega。

And then the， the three objects together， the space， sampling space。

 the filtration and the probability defines a probability space。So now you have some。

 those who didn't know have some。Like a first big idea of what we are talking about。

EThere is one more concept， also that these。Important， so here， I just copied。

EThe our definitions for in an abstract space。And then what is a random vector。

 We all the time speak of random variables and random vectors。Well， it is a complicated definition。

 even though its some simple object， in fact。 So it is some application from the abstract space into our N。

Such that if we take measurable sets in our end。Then the image of inverse image that is will come from here to here。

 So we are here in the sets of events， right？ So the inverse image of any measurable set。

In the extra probability space is formed by events。

Such that when the random variable is evaluated in this event。E it， it， it belongs to the set a。

 and this is a measurable function。嗯。Ca to， if you think a little bit about it。

 it's understandabilityities。 So we take measurable sets in our end。

And then we see which are all the events。That are mapped through this variable into this measurable set。

 a。And this has to be measurable， but now consider here。So we take things that have a size， and。

EThey are coming for events that are also having a certain size。Okay， so size is the measure。

 what I meant。 So， and the probability inducedd by this。A random variable in the set， a。

Is the probability of all the events whose inverse image is a。Right。

 this is a probability induced by the random vector。

So this is it that you come and go from omega to R N。 it's a little tricky。 But we if we we will。

 there is a very simple example that I think enlightens the these concepts。

All this is from the book of K La Wallace。 that I explain。

So a very simple probability space and why we need to think of omegas and we cannot give numbers。

 assign numbers and put everything in terms of numbers in our N because we could think， well。

 let's nummerize everything。 We cannot。 So suppose we have bought a box of bananas。



![](img/a8946f6359ad386be21758ba26a2dc50_50.png)

In the book， they buy apples， but I know who are here。 Let's buy bananas。 No， a whole box of bananas。

 These bananas are in a， they come in a cloth package， and they have different qualities。

 and we want to sell them and to see how to assign to classify them according to different properties。

 And then so we have defined our space will be they said we have unusable bananas that are wasted。

We have bananas that are only good for cooking because they are to ripe， but not yet rotten。

 so we can still use them。Or convince somebody to use them。And buy them from us。

 And then we have those that are good for eating as they are。 And those among those。

 there are different qualities， too。 There are those that are first class。

 second class and third class， for example， And this depends on the appearance。

 if they are too black。 we don't like them， the flavour。

 that we can maybe judge from looking at them。 And then if the。

 they are stinky or the smell or the fragrance。 I don't know。 I just invented something here。

 some numbers， some qualities。 But those are qualities。 Those are not numbers。However。

 we can assign a value， a random variable that will take those qualities and will assign a value to these qualities。



![](img/a8946f6359ad386be21758ba26a2dc50_52.png)

And this is this variable random variable here see of the events that we have the this here。

 the value of the news variable by one of this event would be 0。



![](img/a8946f6359ad386be21758ba26a2dc50_54.png)

![](img/a8946f6359ad386be21758ba26a2dc50_55.png)

The value of those that are good for cooking will assign one half。

And then for those that are good for eating raw， we will assign for appearance。

 taste and fragrance and value between C and1。Quality to qua classifies。 And then we。

 the value of those events will be one plus a，1 plus D and one plus F， the the product。

We multiply them。So you can see that here we can arrive until 8， right， with the value。

 we start this from 0 to1 half。 and here we can have from  one to 8 any possible value。😊。

And this helps us in pricing the bananas。Because， for example。

 we can say if we have the value So is V。 It was here is C。 I had written V。

 then since previous slide I had written C， I remember to change them here， but not here。 sorry。

 So here is C。So if the value of the， our bananas is between 6 and 8。

 this is kind of the highest we can get， then well charge a high price。If it is between4 and 6。

 for example， this is totally arbitraryrbit you see， you see it's where we put the， the cut。

 is's just a decision that we make。 Then we charge a little less unless even less if we are between  one and 4。

Now， if we are good for cooking1 half even less and we don't charge anything， if it is unusable。

 maybe we should even pay for for getting rid of the bananas that are rot。

 So this is this is a random variable that is taking。😊，No。Equalities that are not number。

 So we are in this space， omega， and give them a value in the set of measure。

 in the measurable sets in R here。So Id say， it is。Well， it I think it is illuminating。 For example。

 if we take a set， if we take a set of the unusable and。

And unusable and good for cooking only bananas。 Then we can see we can take the value01 half and see what these inverse image from which events。

 from which bananas from which events we got into into these values。

 And this will be the inverse image we were talking about。

 It doesn't have to be joint it doesn't have to have an intersection here。

 it doesn't have an intersection those two sets Well you see that well on purpose。

 I was defining open in one extreme， exactly not to have an intersection So that when we defined the probability of these events。

 then we can do the sum of the individual probabilities or combination of of those events。

 for example， first and second class bananas then we can sum the probability of those two events。

 and the probability will be probably the I don't know。 our。

Experienced manager who has been buying bananas and selling them for many years。

 then it will assign the probability。Okay， so what are all the events then here。The， the value again。

 C here， I forgot to to change。 So C of the full space is the union of 0。

1 half and the whole interval1 and 8。So this is the image of the。

Rand variable of the hot space through the random variable。Okay， so now we have。

 we know we have a better idea。 And what is it that it means for Q to be measurable。



![](img/a8946f6359ad386be21758ba26a2dc50_57.png)

And now we can。 so you know， now we have all these concepts。

 We know what is measurable and what is the probability space and the images of random variables。

 So now let's consider when this other。A condition holds。And you see why we need to well。

 It is clear why we need to know when， why we need to have either or the positive part or the negative part to define it。

 We need this for being able to have some number that we can manage。 So can be infinite。

 but cannot be infinite minus infinite。This is what I already said that。 no need to repeat。

 So we're okay with the measurability。And as I said。

 this part depends on the the structure of the records。 and there are very complicated conditions。

 depending on which is the the records。 We will start with the the first condition。

 the most important one。

![](img/a8946f6359ad386be21758ba26a2dc50_59.png)

Well it is called fix records。 So we have those all these concepts。 fix records， simple fix records。

 complete fixed records and relatively complete fixed records。 And it is now by。

 not by chance that we have fixed fix fix and fix。 It is because when records is not fixed。

 things get very nasty and difficult， difficult。 And what is fixed records。

 fix records means that the matrix the， the records matrix is not random。

 It's deterministic is fixed。So。

![](img/a8946f6359ad386be21758ba26a2dc50_61.png)

For our example of the oil production。We did have fixed records because we were just willing to go and buy a gasoline in the amount that well in in the full amount to the retailer。

 So records was fixed。 And that's a good thing。

![](img/a8946f6359ad386be21758ba26a2dc50_63.png)

Okay， what is simple fix records， Simple fix records。So it's a fixed record。

 so mega will be an nottriendom。

![](img/a8946f6359ad386be21758ba26a2dc50_65.png)

So， simple fix。Recors。but it is even more。 it is really like the problem we we solve with the records model we did for the oil production example。

 because the singlech fix records。Ha。The matrix omega。Is the identity a minus identity。

 Remember that we added y plus minus y minus。For our gasoline。不诶 demand。Constraints。

 so it corresponds to our example， and then。The recordscur cost is deterministic， is also not random。

 The technology matrix is not random。And that's all the demand man can still be random。 Otherwise。

 there will be no more randomists。 Yep， I have a question。The value was。OrIn which case。

The definition where so the question was， if the variables are non negative。

 The definition is on top of our model。 that is first station， second station。

 where we always had x and the y is non negative。 So everything is non negative。

So the single fixed records has all the elements are not random。

 except for the demand for the vector H。 that would be。

 And the records matrix has a very specific structure。 So we。

Added in select variables to our inequalities and our random constraints in order to make anequality。

 You can think of it like this。 the same product fixed records。



![](img/a8946f6359ad386be21758ba26a2dc50_67.png)

Okay， then complete fixed recordscourse。

![](img/a8946f6359ad386be21758ba26a2dc50_69.png)

Complete six records。Is a condition that ensures that we will have signed it。

Records function for each x and or N C fixed。 So we have has then。오메가 노트란덤。

And the positive health of。Our matrix。 Remember， it was the。Sense of P in ourm。

Suchs that omega transpose。no， sorry。 No， no， no， no， no。

 This is right in the the feasible set is the the set of Z。In R M。Such that the。

That makes that a team is。W Y for some。No negative white。So the。

 I didn't finish the what is the definition。 Okay， so the。

 the positive hall is correspond to the image of the physical set of the record function in the primal formulation We minimizing you transpo Y subject to W Y is smaller than。

TheW Y is more equal to x minus H minus T X and y not negative。

 So if this positivehu is a whole space。Is concise， then records is complete。With。啊了。嗯。

And why is that， Well， simple， it is complete because it means that since we have Q of x。See。

 then let's write the primal formulation， Q transpose y。Subject to。W， Y equal h minus t。

X and y rather than 0。If for any vector in our M， we can write them in this form。

Then this means that the feasible set here will be non empty for all possible。

A choicesices of x that we make and of an H and T。 So of C。 And this means if the primal is feasible。

 then the primal is feasible， then we cannot have both in feasible and then the expect the records function cannot be unbounded。

 either they are both un feasible， and then or one is feasible and the other one is unbounded。

 So if we cannot have if we have feasibility for or h minus T X。

 we will not have this in definition and this。Not well defined the definition of the expected records function。

So， this is complete。Fixed recordscourse。And then well one question that we can ask is when the simple recordscourse is complete。

Yes， we have a question。M哼。😊，That thing。So where， the question is， if the matrix。

 the records matrix that corresponds only to variables that are second stage have N null columns or null blocks that correspond to the first stage。

Well， when you write in Matlab， all vector like a whole sausage。With parts， yes。

 but if we write it discriminate。 And if I had written here。The same name for x， X and y。

 And then the first part would be x， and the second would be y。 Then W would be。I'm not forgetting。

 It's its because this is a different name。It is x。 Its not called。 It's not the same vector x and y。

so the emotionalality here is right。 It is when you go and program Matt that if you choose to use the same name for the variable x and y。

 and then the first part is x and the second is y， then w gets filled with zero and has blocks。

But in that case， it is not the matrix W you will be having some metrics like。T 0，0， W。

 And here your soage。That well have in the first part， I know， sausage， sausage。

In the first part for one to the dimension of x。It will have x。

 and then in the dimension of y the second part。This is only a choice that you may when represent in the the elements in your in your program at lab。

It's so the question is， if we make a sausage of representation， if we make a saus representation。

 then W will have a negative identity。It is identity minus identity。

 probably because you need to get So it will be of this form。

 It is simple records for our problem and not for the formulation with the sausage。

 The formulation like this has these records metrics for the oil production problem。Okay， good。

 So now let's come back to our， our question。 Well to my question。 Now I answer Cla's question。

 now I will， I will， I will answer my question。 So when the simple records is complete。嗯。Or yeah。

 we can。Actually， let's start by characterizing complete fixed records in terms of the set P of Q。

 remember， So well， let me start from the left。 So it change so。You want to call it。

 Let's call it proposition，That's called proposition。呃。A complete fix of course。Is equivalent。都。They。

Recession con of the feasible set in the dual formulation。 P。

 P of Q of this feasible recession con being。Just the0。 If it is not empty if。

They cup large peak peak of cu。If it's not， if it is empty， then we have nothing to， to， to say。

 and it may happen。So。Let's make ourproof no。I will start writing first regarding what is P of Q and what is its recession column。

These elementsing R M。Says that。Emantrans Q。No， B。S。 Thank you。嗯。Okay。

 and we had seen that the recession cone was the set。Of all the directions in our M2。

Such that W TD is smaller or equal than0。Because it was a way of here we can add。

As long any positive， any ray， as long as this product is smaller equal than 0。

 and we will stay in the set。Okay， so。

![](img/a8946f6359ad386be21758ba26a2dc50_71.png)

Complete fixed records is equivalent to that。Okay， so now we say that。So now let's take if。So。

 complete fix。Recall。Cause。If and only if。呃。40 C。嗯啊。M。There is a positive y， and no negative y。

That's that。Omega of y is equal to z。Good， so now we take。Let's see。

What do I want to prove that P star is equal to 0。嗯。Xin。Okay。Okay。

 we have to remember what is the recession count。 The recession count is the set of all the。

This is a characterization。 but this I said that of all the。The address con。With it said。Of。Deep。啊。

And such that。They transpose P。Is smaller than 0 for。我。No도 they뻐 날 gone。Now than suppose equal to 0。

 Let's do the other way。Right。0 w C equal to 0。 if， if this happens。 So if let's suppose that P。If。

The recession come。Is different of just the vector0。Then。There is some deep。C noし。Such that。

The value transpose the。Smaller than0。五期。And then。And the series in our M， But then。Let's see。

I don't remember the I have to choose。Why such that why。Yeah， this is then this0 in our M。

can be written。啊。The0 equal。W y 04。Sam。Y0。No negative。And then， now， here。What do we have？呃。Then。

0 is larger than W transpose。 the0 s W transpose。W。Wuawe y 0。Well， and then and y0 is can only be 0。

Now， the in since here know。you感。メリカ？We have to make。 We have to make between D0 and C。

 This is what we have to make。 So in other， it were not function。 Okay， seems you。Then。Okay， D our N。

 O， so。0 is strictly smaller than d0 transpose d0。This is what we need。

And then this0 transposees y0 transpose， W transpose。The theorem。But now。

 w value transpose this0 is smaller than 0。嗯。And y0 is non negative。 This equality is not possible。

 And this is the norm square norm of the0。 if we suppose that this0。

So we're supposing that this zero is non non null。 So this is a contradiction。Any contradiction。

 or it can only hold。그럼 트 액션。The管理的。On the relation， only whole。Only hurt。Her。For this0 equals 0。 So。

 in fact， this is ifan leave。And these we can， we can refund the way same way。 So complete records。

If complete fixed records is the same， then our positive will be defining the whole space。

 And we had seen that the domain of the function， the support function V。

Was the positive hell of of W。 And this means then that。When we have complete fixed records。

 we will have our ex the records function Q of X， C that is always finite。They record function。

 not respect the record function。Okay， and then we can answer the other。

 who can ask the other question is when simple fixed records is complete。

 Is there a relation between those two concepts。 So we'll go one blackboard forward to the left。



![](img/a8946f6359ad386be21758ba26a2dc50_73.png)

嗯。And then， our researchion is。Simple fixed records is always complete。唔计。Don the proof。

It is rather easy because now we have the， the form。 We will use our previous proposition。

 and we can look at the first the co， the the physical dual set。P of Q and its recession column。

When there is。Fix， simple， fixed records。The matrix W is I minus8。Do I。I-5。And on my W transpose。

 then it will be I minus I in a column。So。呃。This is going to make square piece。B of Q。I it what doで。

Vectctorors in our M。Such that。

![](img/a8946f6359ad386be21758ba26a2dc50_75.png)

B。Is smaller or equal than， Well， let me write it first fool。 And then I minus I。呃，B。Small transport。

That好。I minus I。嗯。B。Is smaller than the vector Q。 So it is convenient here to split the vector Q in the components that correspond to the first block of identity and the second。

 And we will call it Q plus and Q  Q minus。Okay， then this means that。The elements in this set。

They need to satisfy their condition。 P is smaller than。Q plus。And minus p is smaller than  Q minus。

嗯。And now you see why， I call them like this because， in fact， this is just an interval。

Minus Q minus。With extremes。Minus Q minus Q plus。Okay。Right，Here。

 P minus P is smaller than  Q minus means that minus Q minus is larger than a smaller than T。

So this is the set。And here I see one concept that is attached to。To simple records。

 And is the fact of having sufficiently expensive records。 sufficiently expensive records。 We need。

 because we need here these extremes to be well defined， right here they。So。

 the first observation is that。B of Q。Is not empty。 Otherwise， we have nothing to talk about， right？

 Remember， we said they have to be not empty if and only if。呃，Q。Plus plus Q minus。Is not negative。

 Otherwise we have that will have actually positive because to be。

And this is said to be that records is sufficiently expensive。

 You will see why when I will see this is a simple example here。But， you can see that。 So we had。

Define， Well， I didn' not write somewhere。 Well， complete fixed records is not random。

 And these holes。 But for that， we need the set P of Q to be un empty。

 No emptiness is characterizedized by those extremes being left and right extremes on the interval and is equivalent to co Q plus plus Q minus non negative。

 And this is called in the jargon records is sufficiently expensive。Remember that this is cost of of。

The records is a records cost is。Sufficiently expensive。

And this doesn't mean that all the components have to be positive， right。

 It's just that this sum has to be positive。 And this is， for example。

 a situation when that can arise when you think in the。Yeah， nowadays in Europe。

 they have a negative interest rates， right， people in Switzerland has to pay for the bank to keep their money instead of getting tax get in interest from the the bank keeping their money。

 So this is for it is for trying to encourage expanding spending instead of saving， right。

 And then this corresponds to records if we want were the bank owners to set in a records for negative records variables。

 that is negative。 But as long as well， they every time they lend you money， they charge you more。

 And sum of this is positive， then they will have a non empty feasible set and they can do their calculations。

 if they write a model of in the two stage formulation。Okay， so but I'm in by way of the。

 of the proof。 I haven't done my proof。 So I just wrote what is sufficient responsive records to keep it in mind for single fixed records。

 And then when is this records complete。So the recession con。

 we can just see what is a recession count of an interval。Can we go in。

 and we are in R here or we we are in R M。 Can we go in any direction of the hypercu cube and extend the semi the halfline to infinity and stay in the hyper cube。

 No， it is a bounded set。 And a bounded set has a recession con that is equal to 0。Into a B。Of two。

It's a bounded set。Is so the only direction where we can go until infinities in the zero direction that is nowhere。

 It's rec con。I。The infinity。Equs0。应几。Okay， so we have all those。ASt。

 simple and complete fixed records， relatively complete fixed records。Is。

The weakest condition under which reasonable things happen。 And， of course。

 it's the most difficult one to check。 We have a question。



![](img/a8946f6359ad386be21758ba26a2dc50_77.png)

Yeah， you can also check the definition directly and see。 Yeah， actually。 Yeah， it is。 And。

 and actually， you know， that's why I started writing this。😊，That's why I wrote this。 But I forgot。

 So the suggestion is， why don't we just prove directly。

From the definition of complete fixed records， that single fixed records is complete。 And then the。

 the definition is that the positive hell of this matrix is the whole space。

 and the positive hell of this matrix， I will write it here is more。Positive hell of y minus y。

Is the set of elements in R M。Such that。A zip。Can be written as。Y plus minus y minus or c plus。

 maybe not whether。 but it's just that I want it to be y Y plus minus y I。

 y minus4 y plus and y minus not negative。Right。This it is three double。 I don't know。 Okay， Well。

 And then every number in R M， the same way I made here， my， my drawings。



![](img/a8946f6359ad386be21758ba26a2dc50_79.png)

E in R， every number in R N component wise， you can see of a scalar and then can be written as the sum of a positive of two。

 the subion of two Po positive numbers， its positive part and its negative part。

 And then you have this。😊。

![](img/a8946f6359ad386be21758ba26a2dc50_81.png)

A straightforwardight， pro of the one that I made at this ladies。Okay。

 so relatively complete records。 relatively complete records is the most general condition。

 and it remembers what is it in which context we are。

 We are trying to solve the first stage problem that。😊。



![](img/a8946f6359ad386be21758ba26a2dc50_83.png)

![](img/a8946f6359ad386be21758ba26a2dc50_84.png)

I will， right here。So our first stage problem is。Minimize Ctruspo x plus the expected records function。

And we have constraints of first stage constraints， subject to。A X equal B。Anエスなネガティブ。嗯。Then。

 in fact， we don't care what happens to the expected record function for points that are not feasible for Xs that are not feasible for the first stage。

 So they relatively complete records requires that so relatively。Complete。Fix。Recors。

Often in the writers， in the papers and in the books， this fix is omitted。

 and everybody works with the fixed records matrix。 Okay， I put in it here。

 so that well you get them。they what it is。 It is the。You get the。the that is fixed that is always6。

 So you learn that is always6。 I found the one。 So the relatively complete fixed records is complete records。

 but only for the points that are feasible in the in the first for the first place。

 complete records was saying that the positive hell of the matrix W is a whole space。

 And this was a equivalent to saying that the records function Q was finite。

 We saw that we remember that we proved that the domain of of Q of this function was the this positive h。

 So relatively complete records is complete fixed records is that for all X larger than0 such that。😊。

A X is equal to B。哦。The records metrics。Its finite。嗯。For all， for all。



![](img/a8946f6359ad386be21758ba26a2dc50_86.png)

I般嗯。In our space， it's not with probabilityability 1。 This is what I I just want to make sure。No。

s talk here。 What is my call。Yeah， this would， yeah， no， this would probably the one。

 It would probably the one。 It's not for all。So it's for almost everywhere。Which makes sense。

 in fact， I will。对不对我。For almost every C in omega。An omega in omega， in fact。In omega and omega。

 because C X of omega。 Remember that C is H T N Q。And our sampling space has events oome。

So why almost everywhere because in a set that has a measure0 that means a probability0。

 and when we make the integral， the probability0 doesn an enter in the calculation sets with probability0 do not enter into a calculation。

 So if we have set of0 probability where the expected records function is infinite we don't care because it will not count in our expectation。

 That's why we write in this way relatively complete records。

 but as I said relatively complete fixed records it's definition and it's an that is often stated in the paper we assume that there is relatively relatively complete fixed records because like that you can start working with non with finite records functions but it's very difficult to prove in general。

 what it is true is complete records all simple records。This is very easy。Good。

As this is what we proved that simple fixed records is always complete and complete fixed records is equivalent to the dual feasible set being bounded。

 So it's a recession cone is serum。Okay， so now。We'll see， for an example， the function the6 records。

 that is feehi。 I I it is shortened to feehi because expected of Q value of Q iss a little long。

 So let's。Okay， let's come here。And well consider an example。Where in R， it's enough to get all the。

All the complications for。

![](img/a8946f6359ad386be21758ba26a2dc50_88.png)

Es Kaar eggs。Consider the stochastic Clean program。Minimize a cost。 It's not a vector。

 So it's a scalar。 I don't put re transpose。Ex。Subject to。呃。X， no X is in French。 X。 No。

 it's in English X equal omega。 So we don't even have a a random variable directly。 our event in the。

 in the space。 so almost。Every omega in omega。I lets put the non negativity conditions to provide the walls easily。

So we have this stochastic linear problem。It corresponds more or less to having only one oil and one type of gasoline that we produce an infinite capacity。

 We don't care about capacity， right。So what would be the records model for this stochastic linear problem。

We have to write the introduce the records variables。 And then what we will do。

 we will introduce a records cost and variables here。Y plus and y minus。都呃。Correct our decision。

 So has。Records more than。Minimize C， X plus。Okay， let's the first try it the。

Q plus y plus plus Q minus Y minus。Subject two， we have two other selects variables， why。Yes。

 x plus y plus minus y minus。被关。と omega。And x。La than0， and this like variables。So now。

 so for  Q plus and  Q minus the records cost U Y plus and y minus the wait andancy variables。

 the second stage one。 So if we now write the two stage formulation。The two states。

 schastic linear program is。Then the first page will be minimize of x plus p。

 Remember that we call it。S to x。Ls are equal to 0。And then where feet。

Is the expected value over omega of the records function。4。The record function is the second stage。

Problem defines a secondt problem that is minimize。On the Y variables， right。

 having X as a parameter。So minimize Q plus y plus。あ。Plash。Q minus Y minus。是不是都。

Y plus minus y minus equal omega minus x。On why plus。1 minus later equal than0。Okay。

 this is the second stage problem。And。This。If we take， well。

 so the first observation is this is a problem with simple fixed records， right。走。The example has。

example。For the example。Simple fields records holes。Because omega is one times one matrix。

Is that the。1-1。嗯。Then we have Q plus。you minusナ。The matrix T is just one。The fact the number one。

Are not。Random。So sufficiently expensive records will mean that the sum of those two costs is non negative。

 as we saw。 And in which case， everything well， the records is simple and is complete because simple records is always complete。

Let's take Q plus and Q minus equal to one。So that。Yes， take。Then in this case。

 the records function is super simple。

![](img/a8946f6359ad386be21758ba26a2dc50_90.png)

It's the mean。Of y plus plus y minus。72。Y plus minus y minus equal omega minus x。And Y plus。

Why minus， No negative。Now you remember here。So， we have。In the， in the constraints， it's number T。

And in the objective， we have。Right， the absolute value。 So， in fact， the， this is explicit。

 This object， this records function is nothing but the absolute value between omega omega minus x。嗯。

No。Good。Okay， so we have one student who understood and it's gone public。😀Ha。😊，I。😊，Okay， yeah。

 it this is we are here were minimizing the absolute value of a number whose value is omega minus x。

 So this is our objective assumption。 And then you can see that this is polyhe。 And moreover。

 we know how to compute itself sub differential， right。😊。

So what is the sub differential of this of this function。So it is with respect to X， right？

So it will be the single term。-1。哦。The single tone one。Or the whole interval minus-1 and1。

 depending on what happens with the sign of the argument， right。So。There are questions。

 Maybe arriving。 That's it。 Can be。 Are you looking into them。No， because I hear。

So it is -1 when this is positive。 So when omega is larger than x。 And that means that， yeah， okay。

 that x is smaller than omega。When there is a quality， we have zero there we have the whole interval。

And it is one when this is negative。 So x larger than omega。Yes。Okay， good。 So you see， we。

 we are finding all the results that we have proven in the in the， in the past times。 And so far。

 we have not gone into the continuous。Distbution。 So let me see what I wrote here。 Oh okay， so。

I forgot that I had written。 I could spare some a chalk。

 So we have our stochastic linear programming problem， who has its records problem that we wrote。

And the two stage formulation is given by that expression。

And we have that the do while feasible fat is un emptyty if the records is sufficiently expensive。

When Q plus and Q minus are 1， we have the absolute value。 If it wasn't。

 then you have to do some manipulations， but probably you can still find an explicit form。 But。

 it will be involved in Q plus and  Q minus。 So if omega has finite support。

 what is expected value of those。

![](img/a8946f6359ad386be21758ba26a2dc50_92.png)

E record sanctions。 Well， if Ome has signed support。



![](img/a8946f6359ad386be21758ba26a2dc50_94.png)

the gap omega。Fin support。 That means that we have。Then，オメガ。

It is taken in the set of omega 1 until omega capital K。 right。

 We have a finite set of realizations of events。And then the expected fee。Of x is。

Respect the value of。The absolute value of omega minus x。And this is the sum1 of the probabilities。

K between1 and K of。Omega k minus x。So it's a sum of expected value。 and then it is polyhedral。

 And then well， you see that we have older。The results that we had that won， of course。

 it could I have to， to， to be valid for this simple case。 Let me see， Okay， if Im as containers。

 right so I'm promising。 I'm promising I'm never getting there。

 and I'm getting to the end of the class， so。

![](img/a8946f6359ad386be21758ba26a2dc50_96.png)

What I wanted to say， Let me see。 Let me see。The domain。Well。

 when con it's something that I wanted to to show tomorrow in the next class。

 then we would see what happens with the continuous the。



![](img/a8946f6359ad386be21758ba26a2dc50_98.png)

That this function fee， the function， the records function fee for this simple example。

 but also for general examples， except that。The calculations are much simpler when we have a a S single six records and only randomness here。

 and it expressed only only like omega， not even as a， as a function of omega。

So that's why I'm doing things in this example。 So the function theme。here。It leaves its container。

for a continuous distribution。So how do we see that， Well。

 the domain of this function is the whole space， because。We have that the single。

 the simple fixed records that is complete。 So we take x1 and x2 in R。It's our vector space。

We have to see what happens to the difference in absolute value。好。E p of x1 minus c of x2。



![](img/a8946f6359ad386be21758ba26a2dc50_100.png)

So。This is equal to the expected value。我美噶哦。Oomega minus61。Mus。

Respecttive value in going to put omega。 It's the only variable here， omega minus x2。Absolute glad。

This is the expected value， the absolute value of expected value。 we can take a。A way就没 here。

Thespective value then is smaller than。Thespec value。Of the absolute value of the differences， right。

I know。オメガマエ2。诶嘿。酿。I know respected value。Respective value， here。

So the absolute value of the difference of expected values is a smaller than the expected value of the absolute value of the differences。

Okay， and now we have that for each single omega here， the absolute value function is slipes。

 right so。This is smaller than the expected value。Donown of some。L， omega。The difference。Here。

 that is some。L and the difference， the expected value of the difference of the arguments。

Omega minus- x1， minus。オomeガ- x2。Now， omega -61，- omega -62 is a n than x2， -61。嗯。This is an L omega。

欧omeガ。X2， x 2， minus x1。And this is some constant。嗯。X1 minus x2。if。The expected value of omega。

I finite。So。The function phi is which just continuous if。Respected value of omega。Flightment。Okay。

 so。And。Yeah， just yeah， a little bit。 I cannot， I cannot stay longer。 So I will alone surgery。

 I we will see the。Longtime promise are not yet seen What happens when omega is continues for this example that this。

 illustrates all the situations that happen for a general case。

 And this is simple enough to work with。

![](img/a8946f6359ad386be21758ba26a2dc50_102.png)

Okay， so with this， we finish our class。 Do we have questions。 No。

 we have questions Yeah in the YouTube。 Let me see， are you looking at the Whatsapp。You know。

 because maybe Wellington sent us some question， there is something in whatsApp but I don't know。O。

No， somebody else。Okay， so okay， so thank you very much And see you on Thursday。

