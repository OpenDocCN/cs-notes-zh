# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p01 -01-Basic Course on Stochastic Programming - Class 01.zh_en -BV1tH92YXEnd_p1-

Of the basic course on stochastic programming， we have students attending live。

 Thank you for being here。 And we have students attending from abroad。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_1.png)

E through the YouTube channel of I。And it's a new technology for us。

 So we have to learn there is the possibility of interacting through the chat of YouTube。

 And then you please let us know if something is not well in the reception。

 The first important thing is to set the right resolution to YouTube。 by。

Hereby going to this wheel of settings and choosing 480 pixels for having a good resolution。

 let us know if something is not right， please。Okay。

 so this first this course is the first activity of Suvan 2016。

 a thematic program on stochastic programming that on more generally than stochastic programming sorry on very stochastic variational analysis。

😊，And we are very happy of having this feest of uncertainty here at IPA for these three months。

 actually first， if we count the beginning of the month like now， there are many activities。

 mini courses and workshops and congresses， and we will let you know along the the classes when there is some activity that may be interesting for you to participate in addition to the course。

😊。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_3.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_4.png)

Okay， we are three professors in this course。 and one of them is here。

 The other one is travel into a Congress。 So Huamppa La Luna will be here。Maybe in two weeks or so。

 the other professor is well into deelvaa。EWho is online in the YouTube channel as a moderator。

 So please tell us tell him if there is some problem in the transmission。Okay。

 something that I should also say is that I speak fast。 So if I'm going too fast。

 stop me and ask at some point， I will stop to ask if there are doubts。

 And it will be the moment for people from abroad， maybe to send them or maybe for Wellington to collect them and so that we can answer to them And also here you can send your questions in any language。

 Well， in in Portuguese。s Spanish。English， French or Italian。 But so send your questions and we'll。

 we'll try to answer to them。 As I say， we have to learn。

So let me see another so let me see if I have some other issues here before starting with the real class。

😊，Well， if you have questions on the on S class， you can send an e mail to this general address fromrov at I dot D R。

 And so that we don't get too lost。 just put in the subject， the。

 the acronym of the course and the date of the class。 Okay， and then we'll。Will reply to it。

 This is the general address of the thematic program。

 So there are many things going on in this email。About the grading system， how we will do。

So before getting into the text into the grading system。

 I should say something that is specific of applied mathematics。

 This is a course on applied mathematics。 and it requires skills， both in theory and in practice。

 Okay and we have students who are coming from different backgrounds from mathematics and from engineering。

 even from administration， apparently， So we will And， but this is course in mathematical institute。

 So we will be do in mathematics， complemented with practice， because a computational practice。

 And because of that， so the in the grading system。

 we prepare some mix of those two important points。😊，We will have for the grazing。

 we don't know yet the percentage of weight of each one of these items。 but these are the items。

 We have two lists with exercises， one in theory and one in computational practice。

We have one example on theory。And this will be taken on April 21， which is a holiday in in Brazil。

 But what， but we can arrange things I will be open。 and some of us will be here。

As for the local people who is taking the course from abroad。

 we have a local responsible who will be in charge of taking the exam and this local responsible should coordinate with Wellington。

 Wellington， Liba for the details。He will be coordinating these things。

 please for exchanges by e put in copy the address Suzaan Prague。Okay， so we'll have， as I said。

 one example theory on April 21， and then we'll have one project， a final project。

 a computational one that can be in Matlab or perhaps in Otave Otaavi is the free or a version of Matlab。

 and it will be， will have to be we will give you the project in advance。

 And it is to be given back or prepared by the end of June。 Okay， because in August。

 we have to get all the grades。😊，And as is customary。

 since this is a course for masters students and PhD students。

 PhD students have to work a little bit more。And this will be in the form of some additional list for PD students that will be more focused on theory。

 for students in mathematics and more focus on developments for students coming from engineering or other areas。

 Okay， so I will make this distinction for PD students。Okay。

 in addition to these theoreticalore or these classes， like I don't know。 these well。

 these classes here by YouTube， we have two or3， what is called in Portu is out long。 it's a session。

 where we will be available for reviewing exercises it will be just after you give the exercise。

 the list of exercises。 So to correct them And to see mistakes and doubts。 And plus， well。

 maybe new questions and doubts of of new issues。 and we will give you the the dates when we are closer to this to the the time。

 And according also， it depends on how we progress with this system of teaching that is a little different and。

 So we are not sure how much we will cover in each class。Okay， what else？ As I said。

 YouTube communication is possible via chat。 If you want to send your live questions， As I said。

 Wellington is a moderator。And I think。What else I want to say， Let me see。嗯。Well。

 we'll use the blackboard and the video。 today will be mostly class on the with slides。

 but we will be using the blackboard to make proofs。 Of course。 So and other than that。

 I think now I can really start the class， okay。😊，So this course is about stochastic programming。

 stochastic programming is a branch of optimization where data is uncertain。And because of that。

 the area。Has some specific features that make it different from what could be sort of as classical optimization or deterministic optimization。

 But is when data is unknown。EOne specific feature is that there are different ways of representing uncertainty in the optimization problem。

There is not a unique way today They will revise some of them。 And because of that， we are left with。

A map of which is this representation of the real， of the real continuous optimization problem that we would like to solve。

And there is a difference with between the discretized problem or the problem that is representing uncertainty in a discrete manner。

 And so there is a separation between this model and the continuous model。 And because of that。

 every time we solve a stochastic problem， we need afterwards to assess the the the quality of the solution。

 We cannot trust the solution and trust。 We cannot trust the solution。

 but we cannot take it as given as a final answer to our problem。

 because for solving the our problem， we represented it in a。In a discretized manner。

 you could think of it like these。 And then there is a gap between the representation and the model。

 the problem we want to solve。 So we need to assess the quality。

 And this means doing some simulations and performance analysis。 We will see an example today。

Another feature that makes stochastic programming challenging is that it's important also。

 since we have to decide how to will represent uncertainty in the problem， we need to。

To choose a model for stochasticity。 This involves defining some stochastic process for the evolution of the unknown data or making some econometric model So we have to use some statistics to generate the data that will feed the optimization problem。

 That is the stochastic program that we will solve。

So there is an important component in all these problems that comes from this first part of gene a statistical block that feeds the optimization problem。

In this course， we will not consider these techniques for generating in what is called scenarios。

 but in the beginning of May， we have a mini course on scenario generation that is the week of 8 of May where we are bringing to super specialist that will teach us fast how to do things in these in this sense。

 So I urge you to attend to those mini to that mini course too it will also be recorded in the imp video system。

Okay， so let's start the bibliography of the course。 It's in the web page。 The main bibliography。

 today， the main one is the book by Alex Shapiro theinka andcheva and Andre Rosinski。

 But today will start with an example that is illustrates well that the challenges and specific features of stochastic optimization and is taken from the book by Carl Peter Carl and Stanangwaas KW。

Okay， so the the problem refers to the production of oil of a company。

 It's a very simple model here where we have a company that。E has refineries。

Where it transforms into gasoline， the oil oil that it receives and its stored in some tanks。

 and the oil have can be their own that comes from platforms offshore。

Or can be imported oil that comes from another countries here。 There is a world。

 a world map to represent these。Okay， this oil is there are different types of oil。

 Os have different qualities， and it's transported by ships to the storage， to the tanks。

 It stays there until and it goes through pipelines through the refineries that have the capacity of transforming into different types of gasoline or diesel or different types of derivatives of oil。

The， the raw material that they receive。And once this， the final， the product is finished。

 it goes again into storage from where it is distributed to the gas stations and to us。

 the final consumers。 Okay， so this is our。Oil production chain。 It's very simple。 Of course。

 there are many possibilities here。 There are more many types of refineries。

 The problem can be very large if we want to model a realistic one。 But for us， this will be enough。

ESo if we want to， what is the purpose of， of the， of the game here， we want to。

Produce at minimum cost， the gas enough gasoline to attend the demand of the clients of us in the gas station。

So， and it has to come to end the decision amounts to deciding how much national and imported oil to import to buy or to well to use。

 So that mixing those different types of oils。 We obtain the products that we need to feed the gas stations。

 And we'll consider that we have two types of gasoline the premium and and standard gas。

 So we have two oils， to products， to final products， two raw raw materials and two final products。

EAnd we want to manage all these production system at minimum cost。Okay， so what is the beef here。

Oil has different qualities， and it can be it。 It has different performance productivity rates for producing a certain type of gas。

you can suppose that the one is lighter， and other one is heavier。

 And then there is more a bigger process。 You have to more ways with one than with the other。

 If you want to do a better gasoline， for example。 So this is called the productivity of the raw material。

 And if we want to write our problem。Okay， here。 Now， let me hear。 Sorry。

 If you want to write our problem as a mathematical optimization problem。 Then we have， as I said。

 there were two types of oil or wine and all two。And we produce one gasoline， one and gasoline， too。

The cost of the oil is given by the C1 and C 2 that is 2 and3。

 is more expensive to import than to use the domestic oil。Then the。

 the amount of oil of each type of domestic or imported will be the by x 1 and X 2。

 And what this T here is a transposed。 and I'm using it because we be dealing with。

Software like Matlab or Otab， where it's important to be very systematic when representing vectors。

 So all of our vectors will be column vectors。 Okay。

 say it's important not to make mistakes when you afterwards do your calculations in Matla or or。

octave。 So here。 So this is a vector 2 3。 column vector same the variables and the production cost is f of x is C transpose x。

Okay， so this is how much we will pay for the oil。 The。

 how much demand of each type of oil of a gasoline sorry。

 standard and premium is given by vector H1 and H 2。 Where follow it's not called D by demand by H。

 because this is a standard notation in stochastic programming we want to be in agreement with what will come afterwards in the。

 in the theory。And then as I said， each oil has specific quality。

 and this is called the productivity。 We need different amounts。 For example。

 two units of national oil， oil or six units of the imported one to make one unit of standard gas。

 So this is expressed that if you want to attend the demand of national of standard gasoline。

 then we need。To combine two units of the domestic oil plus 6 of the imported one。

While for the premium gas， the relation is different as so we can use the same amount of each one of the oils to produce premium gas。

 And we want to attend the demand。 So we can write it as at we have at least to produce what is the demand of the clients。

 each one and each2。 knowing that if there is more it can stay in the tank stored。Okay。

 as for the refineries， well they have a capacity。 They will combine these two types of oil。

 So X1 and S 2， and well put it smaller than 100， which to write it as inequalities。

 we write we multiply by -1。So if we do put together all this information。

 we get this linear program here。Where we minimize the cost subject to the demand of standard gas。

 of premium gas， the capacity and non negativity of the constraints。

 because we need a non negative amount of oil to start making our refinery process， from。

So this is a particular instance of this linear programming problem。

 minimize a cost a linear cost subject to inequality constraints and non negativity constraints。

 We put it here in something that is near to the standard form linear programming。Okay。

 so what do we have here below It's how this would be written if we were to use how if we want to solve this problem。

 we want to know how much oil we have to use from each of the two sources。

 we can write this optimization problem in therefore in a language of， for example ofoctave。

 you can use Matlab， it's practically identical。 But since this is open software。

 we prefer here octave。 but probably in this same class another slide that will be Matlab。

 There is no actual difference。 And actually， I have been using here。

 this is some Python Jupiter notebook because not today， but in other classes。

 we will run programs here live。 and then you will see。How， how the well， the the goals。Okay。

 so if you so up to solve this linear program， the solver is called GLPK。

 It's like Li probe in Matlab。 but it more general。 It's a general linear programming code。

 I suppose this is the K not sure。 So And then it is more general because well we put here as first input argument。

 the cost function， the matrix， the righthand side term B lower and upper bound。

 And then here there are this variables， I will explain those first2 C type means if the variable。

 you can say if the variable you you are solving the pro is continuous or or binary， for example。

 GLP K can solve mixed integer linear programs here。

 we have x1 and X2 is continuous we consider the oil。

 So we put C we define this variable as the string C because。Components are continuous。

And then we have the what else is there， the war type and the。C type。 Okay， so let me first。

 and well send some parameters parameter。 you can check。 So let's go with other input arguments here。

 Lower bounds are 0 for both。 There are no upper bounds in a realistic model。

 There are upper bounds because there is as much oil that we can。Store， for example。

 So that it is sound to， to use upper bounds here。 We no need this just two variables。

So this is the cost to 3。 Then we have the right handsite term。

 which is the demand more demand of standard gasoline than of premium。

 And then the right handsite term has the demand and minus the capacity。 Okay。

 is the three constraints that define our linear program Here is， and as you see。

 I have put here for all the vectors semicolon to the parallel elements because this defines a column vector。

 So try to be systematic about that to avoid problems when programming。We could have put commas。

 but do not put commas， put semi columnlons and， and life will be easier for vectors。

 You see for the matrix， a line is separated by semi columns。 This is a little bit counterintued。

 but you just have to remember， to remember it。Okay， and so the components， for example。

 these-11 is the third line that correspond to this constraint that I re we reversed like-61 plus-62 larger than -100。

 And you see the right hand side term is -100 in the third component。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_6.png)

Okay， the C type is related exactly to these inequalities。 So they are all lower。

 They are larger A X is always in all its lines is larger equal than B。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_8.png)

If I wanted not to change the sign for the last equation here， then I would have put one and one。

 and then this the last C type would have be U from upper LL U。Okay， well， so this is rather simple。

 If we run， then GLP K it the output。With this data。

 the output is 36 units of domestic oil and T 18 of imported one， and the optimal value。

 The cost is 126。 There are two other outputs。 One is the number of error。 If there is an error。

 and then a structure extra with more information。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_10.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_11.png)

There is no one mistake。 There is no error。 the problem run。 It was feasible。

 Everything was right well defined。 And the first important information is the multiplier of the constraints。

 Here is the the sub field of the structure extra that is called lambda。 This is this information。

 And the fact that these two variables。 The first one。

 the first two variables are positive by complementarity。 that may come up here。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_13.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_14.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_15.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_16.png)

Those two first variables， those two first constraints have a positive multiplier force these constraints to be active at the optimum。

 That means that they are satisfied with equality。 So with this problem in this problem。

 we are satisfying exactly with our production， the demand of， of both types of gasoline。

 We' are not producing more， which is reasonable since we just want to。Send to satisfy the demand。

And then the last one is 0。 It is refers to the capacity。

 It means that the refineries are not operating at full capacity because the the inequality constraint that refers to the component here of lambmbda is in a strict inequality。

 is not active。 That is not satisfied as inequality。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_18.png)

Okay， so there are also reduced costs and the time it takes and status that is refer five means there was no error。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_20.png)

Good， so this is a very simple example。 and it is so simple。 In fact。

 that we can make a drawing and find the solution graphically。😊，So we can for that， right。

 the first thing we do in linear programming， especially in R2， where it's easy to， to make drawings。

 is to make a drawing of the feasible set right in X 2 as a function of x 1。 And， for example， here。

Now over there here， not here。 let's see。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_22.png)

Well， this constraint， the， this constraint means that x2。

 if we look at the line that separates the fe feasibility for this constraint is x2 equal 100 minus x1。

 right， And we do the same with all the others。 And we go。 and now were write。

 this is a very fancy way of writing graphs in it it it in in that。

 you can do it in a simpler manner， I just wanted the fonts to be big。 And the and the lines to be6。

 So I had to do some。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_24.png)

Manipulations here， but you see here we a degree between0 and 100。 This is the capacity line。 Okay。

 it's x 2 has to be 100-61。 It's represented by this。 And the other two，2，1。

 two represent the demand of standard gasoline and of。Premium gas。

 So here there are why right the the pictures， what important and then what is important here。

 What is the the drawing。 So we have， right， we have our X axis with one until 100。

 And this is the capacity constrain， right？ It's 100 minus- x 1。

So we have to stay below this blue line， and the red and green lines represents the premium and the standard gasoline demand。

 So we have to stay above those lines。 And as a result。

 the feasible set is given by this yellowish region。

 and what we are also considering non negativity of our variables， right。

 that's why they said the polyheum ends here and is not extended to the the whole plane。

So if we want to find the solution graphically， how is it that we do。

 We look at the cost vector and we we know that the the gradient of the of the of the the objective function。

 which is given by the cost vector because we are in a linear case here。

 It is perpendicular to the level set of the function。 So we will write and this is a linear case。

 So here is the drawing。 we have this is a vector 2，3 of the cost。

 This are our perpendicular lines that are the level sets。

 It means that along these lines F of x1 x2。 That means the cost at x1 x2 is constant right。

 and it decreases。When we go closer to the origin。The lines are parallel because this is a linear。

 a linear。Problem。 And then so we have to move our。

 go in our with our level lines at the lowest that we can with without getting out from the feasible set。

So if we do so， then we will come here Ro。 and then well go to this point。 And this point is 36。

18 is the， the one that was found by GLP K。Well， that is just some。Okay。

 some game for making drawings。 let's say。 So we have here X bar 1 is 36。 X bar2 equal equal 18。

 And the cost is 126。 And at this point， I will use the blackboard because I want just to remember that if there is no uncertainty。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_26.png)

嗯。And Sarah，20。Our cost is 126。 So I will put。Of X bar， we spend 126。Good。

 so this is a well defined in a program。 super simple， easy。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_28.png)

And it is well defined because we assume that we know everything。 We know all the data here。

 We know the cost， how much it will cost the oil imported and domestic。

 We know what would be the demand of the client， which is the more doubtable one， let's say。

We also know。How much productivity， how the refinery will be able to function with the oil that it receives。

 And this is not a given。 There can be parts of break or sometimes when there is not the a platform has problems to send the oil it promised it sends one that is similar。

 but eventually， the similarity is not so much alike。

 And then the refinery cannot produce with the same rate with the same combination of oil。

 the same product。 So it changes the productivity。 this kind of variations of the the oil and the quality。

 And also， well it can happen that the capacity at some point。

 a piece in the factory in the refinery breaks。 And then the capacity that we thought we would have for the week。

 We don't have it anymore。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_30.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_31.png)

So this is why in our optimization problem here。Everything is fine and business as usual。 We know C。

 We know all the elements of A， We know B。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_33.png)

This doesn't happen in stochastic programming。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_35.png)

So。Let's go down。And it doesn't happen。 But what does happen is that without knowing exactly what this data will be。

 we still have to provide a plan for production of the refineries， right。

 we have to provide an answer， X bar 1 and X bar 2 and， and these before knowing the exact data。

 So in the model that we will see now for the simple example， will complicatedlicate it a little bit。

 And that making some premises。 And this is always very important。

 It's the way of modeling in a real life problem。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_37.png)

![](img/54f6b0288b8b240704a36f2cb5a29ffe_38.png)

So we will consider that。We have， we have to make the model for one week。 Okay。

 it is very important when in stochastic programming to decide to。

 to set the model in accordance to the horizon of the optimization problem。

 Orizon means you want to have optimal decisions for which period of time。

 It's not the same if it is for the next week， or if it is for the next year。

 Uncerty will be different。 And this would change the optimization problem。So we want to。

 to define our week， weekly production process。And。It may be that the platforms cannot change。

 cannot send the amount that they promise。 and it will。

 this will translate in the fact that for producing standard gasoline gasoline。

 this number two will not be a known data anymore。 will become2 plus noise。

 a random variable and our assumption is that random variables will be always our assumption our notation will be that random variables will always be de with Greek letters。

 okay。Greek is random。So， okay， so these two here。Is not the two is2 plus Eta。

And we also think that imported oil that we thought we could use for producing premium gasoline would not be also certain。

 will not be deterministic。 And then these three will be replaced3 in the second constraint by 3。

4 minus Eta Eta 2 Eta 1 and Eta 2 Okay， we have certain in this availability in the productivity in how we mix our oils in order to satisfy the demand of each type of gasoline。

Okay， and also。Demand is uncertain。 We have variables， Zeta 1 andzeta 2。That。

Alter the numbers 18 and 163 that we had said in our linear programming problem。 All this is moving。

 So how do we write the problem， How do we solve it and what is the meaning of the solution that we get。

Okay， so what is it that， as I said， what is it that we want。

 This is the such important thing to establish for the problem we want to solve。We want the。

 the plan for the week， X Y X2。 and we have to fix it in advance。 And when is fixed。

 it cannot be changed。You have to tell the manager of the company when it's Friday has to tell to give a plan for the next week to the refineries。

 And this is what the refineries will do for the next week。 There cannot be last minute adjustments。

Okay， then that makes sense because especially for oil and derivatives of oil。

 because they change parts of the in the par in the factory to make some type of， of product。

 So this is mounted， I suppose， in the weekend or while， if maybe it's always the same。

 But if sun change involves a lot of movement of hardware。 So。Another fact is， it's not the goal。

 In fact， the， the goal is that one。 But another fact is the amount of available oil that impacts in our productivity at which rate and which。

 which is a combination of the different oils。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_40.png)

It's only known when the oil arrives in the refinery。

 It cannot be known when we make the decision of how much oil we will buy of each type。And also。

 something that is very important is that the demand for the week needs to be satisfied。

 The clients expect their demand to be satisfied for the next week。Okay， so as I said。

 we have random variables。Then we have two model how these variables evolve according to uncertainty or randomness。

 So we will suppose that the amount of the variation of the amount of domestic oil is independent of the variation of amount of imported oil。

 that makes sense。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_42.png)

We will also suppose that the demand of gasoline of。

Of standard gas and of premium gas is independent。 This maybe doesn't make much sense because you would think that if somebody needs to buy gas has a car that the person the driver cares for。

 it will try to buy premium gas。 But if it becomes too expensive， then it will be buy。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_44.png)

Standard one， that means that when one augments， the other one decreases。 so they are dependent。

 but here we are modeling of the independent。 Okay， it's a simple model。

 and it's already enough to show you the degree of complications we have to handle in this type of situations in stochastic situations。

 So， and also， well， how much imported or domestic or we have should also be independent。

 This is reasonable of how， what is the demand of the final product。 This is a reasonable assumption。

 So the only one not very reasonable is between set setta 1 and Cta 2 here。 But let's go with it。

Okay， so now we say each one moves by itself。 And now we have to define。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_46.png)

According to which process， according to which law of statistics， they will be varying。 Okay。

 here we have simple models。 As I said， the domestic oil is it's a Gaussian Gaussian。

 So a normal distribution with 0roine and 12 of a standard deviation2 with 9 standard deviation。

 You see there is much more volatility is much more uncertain here。

 This one than this one or much more no， but 30% more or something。

 more volatile the domestic oil in this modeling。Then the distribution for the variations of standard gasoline will be a uniform following a uniform law between those two parameters。

 So it can be less than what we expect-0。8 or plus 0。8。

While the premium will follow an explanation law with the parameter lambda equal 2。5。 Okay。

 so this is just to set some values， some loss here。In real models。

 the situation may be more ease more complicated。 And sometimes you have to do some econometric studies to make approximations with historical data and say of that type。

Okay， so of all those variables， random variables， there are continuous， right。

 We have an infinite number of choices， you see for Eta 1。 It's all the gauss bell。

 all the values it can take in this in the。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_48.png)

In the axis。 And then of all those， the only one that is round this itta 1 because it varies between minus-01。

8 and 0。8。嗯。So we can then say， okay， we'll constrain the other three variables to their respective。

99% confidence interval not to get things too much out of control。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_50.png)

What does it mean， Then we have to find to use the cumulative distribution function。

 set these equal to 0。9199， sorry， And then see what is the value of x that satisfies this equality。

 And then well be be well， we'll be in one of the other two extremes。 So me here is。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_52.png)

The mean that the0 here， for example，9 is the sigma， the standard deviation。 Okay。

 this is not explicit。 It can be computed withs some table or you in octave。

 but we get these values for Eta 1。 So you see， if you， I don't know。

 I will go up there and see what is the value of H1。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_54.png)

H1， H1， what is H1 here。 It was 180， right， And from 180， go down。180。

 we can go to 100 from 150 to 210。 This is the range of variation that where the man can have。

 And we have to define how we will define an optimization problem that takes into account this variability。

 in a manner that is sound for the problem we want to solve。 Okay。

 same thing for2 etc cetera one was bounded for the exponential distribution。

 We have this cumulative distribution function。 It's always larger than0。

 So this is our the variation of demand of。Gas， this was well。 Okay。

 so now what happens if we now put this information in our linear programming problem。

So we have those variables here， the random， the Greek letters variables that enter in those two。

Constraints。And where the variables are evolving in a continuum of possibilities。

 you can see there with 99% of confidence。 they would be in the intervals that we analyzed before。

Now， the question is， is this a well defined optimization problem。The answer is， no。

 it is given there in the line， in the line the last line。 So there is no surprise。 it is。

 it is undeified。 how do we solve a problem with an infinite number of of constraints。

 Because this is what it means Eta 1 and Eta 2， Eta 1 here will vary for over have this constraint for an infinite number of Eta1 And here。

 I'm saying for the second for Eta 2 and Cta 1 and Cta 2。😊，We cannot solve it。 It's。

 it's not well defined。 And we need to give a meaning to what means to us to define such a problem。

This will be the continuous problem we would have liked to solve。

We will sort something else that will represent this problem。

 And then we will have to check if the representation is really good or not。

 And this is what I meant when I spoke about assessing quality of the solution of the stochastic problem。

Okay， to see how this impact in the optimization problem， let's go again to our geometrical。

E view representation of the feasible set。If we change the demand here by moving Cta only cta 1 or cta 2。

 this means translation in the intercept of the the line the and then that defines the respective gas or a standard or premium gas。

 And for example， here， you cannot see。 But here it says H2 minus H2 and H2 minus cta 2。

 Then it went down here。 So our feasible set that was this narrow trapezoid became a little larger。

And because of that， if you think of how we determine the solution。

 if we consider just one graization then of our infinite number of theta2 that will take our red line to this one。

 the hash one， then we will pass from the point that we had that was 188 1836 to this one。

With the consequent。We are minimizing over a larger set， so the the cost will be higher。Will we。

 will we mini all that set will be lower， yes。Okay， thank you， Wellington。 Okay。

 so this changes the picture that we had。 This changes our， and this is for just one set Seta 2。

 and we have infinite。😊，Okay， what happens if we change the other variables ets that enter sorry here as slopes as products of the multiplying the the variables。

 This would change the slope of the lines。 And then， well， we can have this one。

 You look how different it is the optimization problem now。And then。Well， we have different ones。

 and we have seen only three possibilities。 now， so all uncertainty equal to 0， moving1 Cta 2。

 moving Eta 1 and Eta 2， only one of them。Which is the optimization problem we want to solve。

Do we have to， do we have to consider all the feasible sets。Do we have to consider one。

 none of them will really represent in our problem。嗯。

So this is a very important issue in stochastic programming and answering to this question is down here。

 It's called handling uncertainty in the stochastic problem。

 You represent your problem in a continuous manner or the best possible ideal way you can think of。

 And then you have to think again and decide what is it that you can do， how you can solve it。

 how you can solve it。 What is it that you can solve because the idea one cannot be solve and you have to represent to write another model that represents this problem that you would like to solve。

 And this is called handling uncertainty。And there is not a unique way of hand uncertainty。

 There are many ways， and it all depends on how we perceive。

The is the effect of missing of not representing well uncertainty。

 This is called the perception of risk aversion。 What is the aversion to risk that the person who makes the decision in our case。

 the manager with respect to variations in the unknown data。Okay， so at this point。

 it's good to stop for questions because now we change to the another P D F。

 Well go out from here to P D F。 So if you have questions， this is a time。Do we don't have questions。

 Oh， everything is very clear。 And here， do we have questions or nothing is clear。 I don't know。

 It's very， we are stochastic。 Okay， so I continue。 Okay， I question， yes。😊，예h。

What is it And to choose why2 was uncertain and3 was uncertain or what is why it's Eta 1 and Eta 2。

拜拜。嗯。Yeah， was。Yeah， well， this is， this is part of the art of modeling and its part of the fact that this is a multidisciplinary。

Area you have optimizers， and you have people specialists in econometry and statistics or in stochastic processes that are discretized。

 And this it， and you have the person who is interested in solving the problem and who knows the day to day variation of the of the problem they want to solve。

 For example， the manager of this company knows how much oil has been coming from a certain platform for many years。

 And it's a combination of the knowledge of these people that makes， makes it possible to。

Make a representation。 But as I this is a model。 As I always say。

 models are So here the choice that I made is the choice of the book。 It's totally arbitrary。

 of course。 say as if it it is the choice。 there is a question totally right。

Repeat the question sorry， okay， the question。 The question was。

 how do you choose the distribution law that represents uncertainty。

 And so there was a very long answer that you you heard。

 and so there are always tradeoffs that have to make made and people has to work together。

 Because if from the optimization point of people together， I mean interdisciplinary if we are。

 we optimizers， we will try to put the simplest one， because it will make our life easy。

 it will make easier the optimization problem that will be solved。while a statistician。

 somebody special in econometrics or somebody who likes stochastic differential equations will put a very。

 very complicated model。 And then it will make the optimization problem impossible to solve So people have to work together in this in this issue。

 And the person who gives sense to all those discussions is a practitioner because it。

 it can tell us it not he or she。 Let's go honor the women's right。

She can tell us that that the model that we are using to represent uncertainty is representing this in agreement with the practice and the day to day operations that the the manager sees。

 So it's a multidisciplinary problem and as I said。

 we learn a lot about scenario generation in the mini course of Ti Tom and de melo and Guin byraan that will be given as part of the thematic program in the beginning of May。

 but of course， it will not be the answer to all your questions。 Okay。

 its an example that I can give Fipe knows it here many maybe more people is that for representing uncertainty in the water that gets into the reservoirs in all the dams and in in Brazil。

 and from which the water is taken to make electricity。😊，Okay， so how do you do that， Well。

 there are very long historical records。 And then you can take into account Nino La Nya。

 make a model。 But then eventually， at the end of it， there is some noise that has to be put。

 And this noise is represented by a Gaussian Gaussian noise and a Gaussian noise is a positive。

 right， It's always positive。 the， the graph of a normal distribution。😊，Which eventually。

 it comes to saying that。E sorry， it it's always positive。

 but for values of negative and positive of x of the or。 Well。

 this means in this model that we are allowing rain to be negative。So， well。

 is it a sound model or it is not。 It is what it is。 It is a model。

 You have to be aware that models have。 And if you want to correct it， there are complications。

 right， Philip， So there things are getting like these effects。

 If you want to change this make it only positive， this will change the complexity of the stochastic programming problem you're trying to solve。

 for example， there are these type of problems that arise when you try to to make the model more alike with the reality。

 So then eventually， there are people that are in the industry of energy that say， well。

 you can think that instead of negative rain， this is evaporation。 think think of it like this。

 So it is a model。 And I always say I would say it only once Here is Christopher Columbus。

 the one who discover America。 He had a very bad model of the the earth。

 And yet he managed to get here。😊，Right， so models are useful， but they are models。

 Don't forget that。 And this is why we always assess quality of the solution that we get with this stochastic linear programming problem that is representing our continuous one。

 which itself is already a representation of reality because as George properly pointed out this deciding that the exponential law is representing the variations of the of premium gasoline。

 it is it is a model， and the model is continuous and then we discretized。

 So there are many levels of approximation in all this problem。

 which doesn't mean that the results are useless because。Well， because Colomus arrived in America。

Good， so let's go back here where we were。 Okay， so now well see some possibilities of how to handle uncertainty。

 once we have decided what the distribution for each uncertainty in our problem is。 and also。

 once we have decided where is uncertainty。Because if you think in the model， okay， before changing。

 let's go back。Up here。No， dumb， da， dam， dom here。 Why we didn't say that the6 cannot be trusted。

Or can be trusted why we decided that the amount of imported oil that it's always the imported oil is always good of the equality that is constant enough to make for us to make standard gasoline。

 Well， this is also where the practitioner experience is very important because the person knows。

 Yeah， there are variations。 But compared to the variations I have from the productivity of the domestic oil。

 They are ne negligible。 So we can consider this deterministic。 So this is modeling。

 And for modeling， you need to interact with the person or the those who want to solve the problem who know the problem。

😊，Okay， so now yes， now we change the file。 So let me， let me hear those clicks。啊，那做咩嘢，你玩。No。

 two okay。Okay， so now， now we。Well see different ways of hand uncertainty。 And since， okay。

 and now I can pass。 Yes， like， since I was not sure I will always start with this。

 but maybe the first classes afterwards， you will know that what is the resolution that has to be put in YouTube。

 We hope that the transmission is running of running smoothly and that you can see。

We did our best here。 We have Anderson our camera and helping us with all the technical issues。

 And this morning， he made some improvements to connect a monitor instead of filming from the screen。

Okay， so let's。Let's see what are the issues here。If you don't care much about technical issues。

 but you do because you are here taking this course。

 then you can do something that is very common practice in many industries。

 And ignore that there is uncertainty。 okay， I will take everything as granted。

 And or then I will do what I will do。 Well I know that those parameters。

 maybe B and A or maybe the cost can change。 Okay， I will solve different linear programs。

 But in some of the values。 Some coordinates in C， Some coordinates in B。

 Some coordinates in the matrix A， I see what is a response。 And what is the impact。

 This is called sensitivity analysis。 people likes it a lot。 sensitivity analysis。

's you my guess from my who that is not a recommended practice。Another， another， another practice。

 commonma practice is。😊，There is always a guy who says， I know what is the， the exact value。

 I'm on the oracle， and I can carefully choose the value of this uncertain data data and make it deterministic。

😊，Well， you may guess that we， sorry， I say this is my o。 It's not the way of sensitivity。 Okay。

 so for large programs， how do you change all the， how do you analyze all the possible variations of all the different components of a matrix vectors。

 It's impossible。 It's useless and。If even if you are the super oracle who knows everything about your business。

There is inherent randomness。 Who could have thought that the oil price would be $40 a barrel now。

 when it was 150 last year。 or not gonna remember one， who。

 who can control the impact of a war in the Middle East。 who can not control， but even foresee it。

 Well， certainly not the guy who says that he can carefully choose the value。

 And I say here didn't say she in the honor of the women's Day。Okay， so。

What is it that stochastic programming provides， It provides a systematic approach to dealing dealing with uncertainty。

Always remembering that there is this distance between the real problem。

 the model that we set for the distribution laws that we for the variables that they decide are going to be uncertain for the data and another distance again。

 another step for the representation of this uncertainty in the optimization problem that we will solve。

 But its systematic。 And this is what is good in stochastic programming。So， an important E。

Pmise in stochastic programming is that we assume that we know we。

 we have available the probability distribution of the uncertainty。distributionisttribution is known。

Maybe sound limiting because of all the issues I raised before。

But we need to define uncertainty only for the important data。 And this is， as I said。

 the fact that we chose two in our first constraint to be random and not the6。

 This is a business knowledge。 what is important and what affects if it is， there is variability。

EMo than any subjective。 By now， you should have realized from all the things that I say。

 model than any subjective。And disc gratation in scenarios is natural。

 It's a natural way we perceive reality。 nature。 We say that the demand for a product for premium gas is low。

 is the standard one medium or is high。 This is considered three possibilities。

 only for all the range of cta ones or cta to。 Don' remember which one is the demand of premium gas。

 The weather， the weather is wet or is dry。 Well， in Rio is hot。 Also， it's another possibility。

 another extra hot or super hot， steamy hot。 but those are scenarios。

 And this define one realization of this uncertainty that is continuous。😊，The financial market。

 it's also important in all these optimization problems will be up or will be down。Okay。

 so there are like natural discretizations that we make in our perception of， of of uncertainty。

But always， I will say this many times。 And in fact。

 I use this color every time I refer to assessing the quality of the solution。

 So it is a representation of uncertainty when we define these scenarios。

 the situations that will describe how our unknown data varies， then we solve our problem。

 we obtain a solution， a response， for example， a production plan of the two different oils。

 And then well when we put in practice， the production plan， what the reality that happens。

 uncertainty realizes in a different way。 than the one that we put in our optimization problem。

This happens。 There is no way。So if you want to think that the we。

 we consider only wet or dry weather， maybe there was something in between that we didn't consider。

 And when it is the time when we will use our decision variable to make our production system run。

Well， it will not be wet。 It will not be dry。 It will be something in the middle。 What do we do。

 So for this， it is important to always assess a quality solution on different scenarios。

 This is called simulation。 and we will see how to do that later on。

 And this is what it's the final step in the full opt food process of solving problem by stochastic programming。

 first as you model your problem。 then you model uncertainty。 You discretize。

 you solve optimization problem。 And afterwards， you evaluate the solution by simulation。Okay。

 so this is our call of assessing quality solution。 It will be at the end of today。

 So maybe on Thursday， we'll see where we get。 No， sorry here in the other direction， okay。

So to make an example， we'll consider the case of a farmer。 the son of Z is Cino。This see。

 you camp in his land， corn， soy or bean。Here has three options。 crop，3 crops。And as I say。

 we will assume that the the season can be wet or dry， Nothing in between。

So Saio has to decide what to plant， which crop to plant。 If weather is wet。

 corn is more grows faster and is more profitable。But if， there is no grain。

 the best option is to plant soil。The idea of things right here went terms now。Okay， well， I。

 I think that that soil is good for dry and and corn is good for wet。 But while anyway。

 we are not farmers here。 Xino is a farmer， he note。😊，Okay， so what， e， what is the plan。

 the planting plan plan of zzia。It's a really reasonable guy。 So he says， I will stay safe。

 I will plant， have corn and have soily。Sounds really。 I stay。Asimmadomodo， not。

 not on one side or not to the other。 So we can see that probably it's a risk a a risk averse guy。

 Doesn't like to take risks。 This is not a risk taker。 Farmer， Farmers are usually。A risk covers。

Okay， now the question is， is this the best possible or is it a good enough。

 Let's say solution for Sasia。 Could Sainna do better。Let's start analyzing what happens。

 So let's make a profit analysis for Csia。 We have here then the profit that Csia gets if it is wet or dry season for the situations where it plants all。

Corn or soy or all be。 Okay， If it is dry and all the field is planted with corn， then it hees money。

That's why it's negative。So， now。We have the for our two scenarios， wait and dry。 We have the profit。

 And then let's analyze what is expected profit， which is the average。

Between the wet and the dry profit weight by the probability P。

 That is the probability of a wet season。Okay， so if we compute the expected value of plantin oil corn or soil or bean。

 we get those expressions that depend on pe。Good， and now we have those three options， and。

With the reasonable of approach， what is the reasonable of approach to say。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_56.png)

We plant half of corn and half of soil。 So we have half a half of the expected profit。

 This is what it will have。 the the profit of say， will be half of the expected of corn and half a expected of of soil。

 if we stay with。E， equally probable chances for a wet or dry season。 Then we get 50。

The profit was a0。 we be 50。Okay。But。If you are Muslim you are mathematicians。

 you come and look here。😊，And look at Feong。

![](img/54f6b0288b8b240704a36f2cb5a29ffe_58.png)

We got say Z。 And then what happens。Can we do better than this reasonable option。

 Is this the best that we could do， There is something better。Well， there is something better。

 indeed。If plants， instead of planting half and half of corn。

 it plants half the whole of bean put here P equal1 half， we get 57。5。 The profit is better。

 He can expect to make more money with planting all bean and it's 15% higher。

 than the reasonable decision。Here， you have to think that， well。

 this is a decision that it this approach is optimizing the expected value。 you can say。

 but then what will be the final profit or a z， we or know。

 because it depends on whether if it will rain or not， afterwards。

 this is the analysis were doing before the profit analysis。

 and then it seems a good idea to plant all be afterwards， if it planted all be， and then if it was。

 in fact we or in fact dry， well， maybe you see if it will be good if we planted all be and。

And if plenty of be regarding with soy， but not regarding with coins So with corn。

 So well there is a， it is a good decision that will not make him lose a lot money in in either wet or dry season。

 but it will not be the best decision， if it is wet， or if it is dry。 It's a a compromise。

 a trade off between the two possibilities。Good， so。What are the lessons from C Union。

Aberration solutions do not function。 What we did was to say half of corn and half of so thinking in average does not function。

 there is a very wellknow paradox of of Sam savage professor in the West Coast in the states is of the drunken in the road。

 you have a drunken person who walk a Sixgging in the middle of a very busy road。 For example。

 here in president is a Tubar in downtown。 And then it goes in the middle。

 The road goes both ways full of buses and tracks and a lot of cars。 and it goes to right and left。

 symmetrically walking。So in average， it will never be crash by a car， right。

 But the likeness that it will be dead。 He will be dead is high。 So you don't have to think in。

 in average， thinking in average doesn't function。 Sa seniorino is losing money。 The drunken is dead。

So another issue is that the best decision that we can take today before knowing the realization of uncertainty。

When confronted with a series of different outcomes for the future。

Is different from the average that of what would be the best decision of each future。

 This is what Zya did。 He thought， I will the best。 if it is wet， I plant corn。

 The best if it is dry， I plant soy。 Then I take half I average。And the， I it was better than。

 in fact， to plant the whole field with beans。 So the best decision today was planting beans。

 And it's different。 it was against the intuition of the z。It would be very nice， if says seniorio。😊。

Before deciding what the plant could wait and see what the weather is。 that would be perfect。

 This clvoyant knowing what the future will be。😊，But he cannot wait and see he has to decide here and now。

Before knowing， if it will be raining or it will be a dry season。This means that the model。

 optimization stochastic model for theia cannot use what they are co what we call in the community。

 wait and see variables。 These are variables that。As that depend on the realization of the random variable here。

 the variables that represent well， the stochastic problem for Cia are what is called here and now。

 It says decision variables must be of the here and now type。

Here are now variables are deterministic variables that are independent of the uncertainty realization。

 So we'll see now some more formal。More formally， this for our oil production problem。

So we have this optimization problem。 and now I put tilda on the Greek letters because it is the realization of one realization of uncertainty。

 So now I have1 tilda 1，1， z 11。 So this is so that optimization problem here is a linear program well defined。

😊，In our setting， all the the decision variables here are all of the here and now now type。

 because we have to decide today。The manager has to decide today what will be the a combination of domestic and imported oil for the next week。

 cannot wait until knowing if the refinery will be working or the demands of the clients will be different has to be done today。

Now， the question is。Thus， it makes sense to look for the best possible values of the here are now variables。

For all our realizations of uncertainty。We could try to do that。But the answer is no。

 The answer is no because you can only it's what happened to Sainina。

 if actually Cia only sort of two different outcomes of uncertainty。

 but he could have consider a whole range of weness or dryness。 and well。

 the you have it is important to well， once you decide the range of the scenarios。

 you will choose about， you cannot do best for each possible scenario or for all of them。

 you have to define some criteria。 And this is the uncertainty handling。

 So it seems very little vague， but I will explain now， I will， I will get into more details。

 you will understand。So。We， the first thing that we want is that the production plan that we will send is feasible for。

E and certain situations that are consider。And then we will choose a second criterium afterwards。

 So let's see。What happens if we are really very， very conservative and we want to make sure that we take into account all the possible variations of our uncertain data in the old production problem。

 then this means that we will let in， we will add to this program。

A constraintss that say Eta 1 varies between the intervals where that we set with 99% of confidence。

 Eta2 in the other one， and each variable will vary in， in its interval。

The first observation is that if we do that， this is no longer。A linear programming problem， Okay。

 because it becomes a variable。 It's a biline。 This changes the nature of the optimization problem here Here we have a product。

 This is no more a parameter。 is a， is a variable。 And here is the same that there is not about。

 It will add add a variable only。Okay， but if we do that， what how do。

 how can we do that and still get a linear problem。

 What we will do is to consider the extreme cases resolve letting Eta1 put in a constraint with Eta 1 equal to the left hand side of the interval。

 And as in another constraint with Eta1 equal to the right hand side of the interval。 And like this。

 we consider because it's continuous here。 we can represent like this。The problem。 And then we。

 if it will be a solution that a plan， a production plan that will be feasible will be good for all the possible variations of our uncertain data。

 And then will obtain these value here， X 1 x2。 we have， you see instead of 18。 now， we need 48。

 We need much more oil， domestic and less of imported。嗯。O， require satisfaction of our constraints。

For all the uncertain data in。Probabilically speaking is not sound。

 What we do is we say these constraints are satisfied for all realizations of uncertainty。

 except for a set of null measure。 right， This is the way we speak in in a probabilistic language。

 And this means that we have an almost sure here， except constraints are satisfied almost surely。

 So this is also something a con the。Satisfaction of constraint is almost everywhere。

 almost surely preer2 by a quasiital point。Okay， so this is this fat solution that takes into account all possible all the ranges of uncertainty。

 What is the cost of this。Well， it is 172。 It's more expensive。 So I would write here。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_60.png)

Prob I will not have time to use my blackboard， but what if。In this situation， we increase the cost。

1 have70。3ya can this round。Okay， how is this solution this approach called this。

 We just dealt with uncertainty， right？ We just resolve our issue of unfinness or of stochastic linear program。

 as I said， take the two extreme values， all the extreme values that and solve the problem considering the constraints for all those extreme cases。

 So and then this is your solution。 So I took this problem that has an infinite number of constraints And now I have some finite number of constraints 6。

 because I mean， well， two possibility for each one of the random variables。

 So no about two to force。 there， and then we obtain a problem that is solvable that has a finite number of constraints。

 So we dealt with uncertainty this approach is called worst case approach。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_62.png)

This is。Worth case。And as you can see， it's expensive。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_64.png)

And it gave so higher。A higher opt optimal value。 And it is conservative。 There is no。

 We don't the manager doesn't want to take any risk， even if these extreme situations are rare。

 And because of that， there is a price to pay is spending much more money to produce gasoline。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_66.png)

Okay。So as I said， unlike the initial stochastic linear program that has infinite the continuous one。

 this is well defined。We made M， it's also called， we made it tractable。

 The problem is became tractable。 It's also some jargon in the in the community。

 That means that while we decided how to to put represent the continuous model by something that can be solved in the computer。

Okay。And this is what using here are no variables。 and asking feasibility for any future realization for uncertainty。

 It's too much in， in general， there are cases where it could be sort， sort of。

 but really for catastrophe analysis or things like this。

Not for phenomenons that are repeated custom frequently。 So depending on the data。

 there can be extreme events， As I said， and it can even happen that the set of almost feasible points is empty。

 I we have moved the slopes and the of the our。Tezoid and the。

 the slopes and they intercept so that the， the lines do not intersect and may said that its unfeas if you want to。

 to satisfy all of them。So what do we do， This is a way of hand uncertainty， but。

It's not satisfactory， in many cases。So we cant have two options。We can either model。

Treat uncertainty in such a way that extreme events do not constrain too match the set of feasible points。

 And this will become clear late now in the next slide。

 or we can consider points that are feasible with some probability level。

 like there is some confidence interval。Not that that leaves out。

 if you put a probability of 90% leaves out these extreme events that may make a feio empty my problem。

So those two models have names and are ways of hundred uncertainty。

 The first one is called a model with recourse。 And the second one is called a model with chance chance constraints or a probabilistic model。

So we'll see these formulations for the two for our oil supply problem。Okay， so what is the idea。

 what is records records is the manager talks to the distribution on the owners of the tracks or with the clients in the gas stations and then says。

 look， I cannot always warranty。 It's too expensive for me to warranty all the time that your demand will be satisfied。

 but I'm willing to pay a penalty if I don't satisfy the your demand。in one in some situations。

 if I have a shortage because of the plan， the plan I make， I made。

 there is a shortage in production in of the refineries。

 then we will pay to the distribution companies or to the gas stations owners a fine and what will be the fine will be。

 maybe it will not be fine。 We will ensure that we will， we will go and buy in the market。

 the gas that we couldn't produce and we will sell it。 We will pass it。

We can even maybe pay it more expensive。 Of course， we will pay more expensive than it costs to us。

 So we can say， okay， we will substitute， and this will be the records。

 This will be the way we will have to compensate for these deviations from our plan that was made in the on Friday of something that happened along the week and prevented us from producing what we expected to。

嗯。So how much we will pay it or how much gasoline we will go and buy from a retailer。

 It will be depend。 it， it will be determined after we see what happened in the in the refinery。

 how much oil we could how much gasoline we could produce。

 So this is not here and now variable to decide how what is the shortage it is a wait and C variable。

 we waited and see what happened， to uncertainty and then determine， look， I。

 I said I I was going to produce this amount In fact。

 I produce three4 of this amount because something happened。

 So for this one quarter of shortage we will pay a fine we will buy a replacement。😊。

So this is a wait and see variable。 And this is the records。

 The records we have is to go and buy in the retailer。

 the gas that is already made instead of making it ourselves。😊。

The there is also a possibility that go and buy oil from a third source。 if。

 if the refinery can still produce it。 So the records can have different ways。

 It is a way of correcting a decision that is wrong because the realization of uncertainty doesn't match what we put in our optimization problem that could happen。

So。Are we going to change the way we determine our production plan， our variables， Op variables。

 X bar and X1， No， those are still Wait here are now variables。That there will be this adjustment。

That will come from buying outside of the production system there。The， the quantity that is missing。

 So now we will write the random vector to C。 Here is Cda。 sorry， this is Cta。



![](img/54f6b0288b8b240704a36f2cb5a29ffe_68.png)

And then here to forgot to change To。So， but those is now we have H1。 the demand is 180。

 What is what it it was。 The demand。 We have the， we now introduce a new notation for these slopes that were allowed to change related to productivity。

Alpha beta of the random variable C that now is a vector， considers all the uncertainty together。

And for one event， scene。So these are our constraints with this notation。And when we are unfeasible。

It is because we cannot satisfy the demand。 And this is the shortage that will be determining。

How much gas will go and buy from a retailer and their records。

Then since we are feasible because of those demand constraints。

 we will allow this shortage charging a penalty for constraint violation。

 What does it mean in our feasible set， well introduce s variables to to the。

Constraints that were are putting us into trouble。And they are like variable for inequality constraints。

 Then there is what is missing for us to attend the demand。 It is a positive。

 It has to go with a positive term。These are the wait and C variables。 Y 1。

 Y 1 and Y2 of C are the wait and C variables in our optimization and problem。

 And this is what defines the set， the new set。And what do I do， Do I stop here， Probably。

 Let me see what it continues。Maybe it's whether we'll stop here。 And then on Thursday。

 we'll continue with the models that we are still missing。The。

 the models with records and the model the probablyistic model。

 So if there is some question is the time to ask again。俾啲山。That 15 tractable。All the values within。

990%。ついく。Like。no， so the question is that when we made uncertainty。

 when we made the problem tractable in the worst case approach。

 if we consider the extreme cases of the 99% interval。 all the values， in this case。

 since all the intervals are independent of each other， it is enough to replace to。

 to put only the two extremes of the interval。In this case， in the。

 in a case that these when there is no things are not so linear or there are correlations。

 then you have to， you will be making a representation of your worst case it's called uncertainty set。

 This is robust optimization， which is yet another approach， Okay， so this is a simple situation。

 where we can consider only the two extremes。 And this already defines the set of all the encompasses all the possible combinations。

Okay， so who do we have questions， Wellington。No， okay， okay， good。 Okay， so we finished the class。

