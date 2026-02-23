# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p03 -03-Basic Course on Stochastic Programming - Class 03.zh_en -BV1tH92YXEnd_p3-

![](img/3f5ba5e644a81434cedf134217ed9f20_0.png)

Okay， hello， everybody， welcomelcome to the third lecture。Today。

 we'll speak about a specific class of stochastic programming problems that are linear。

Constraints and the objective is linear and is formulated in the form of model withcourse and is that it is called in two stages。

 referring to the here are now variables and the wait and see variables。

 Here are now variables are first stage and wait and see variables will be second stage that can be decided once the realization of uncertainty becomes known。



![](img/3f5ba5e644a81434cedf134217ed9f20_2.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_3.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_4.png)

Okay， the usual one。So there are some questions about the homework that were sent and that I will display here so that during the the class。

 you have time to think about the answer。 And then at the end of the class。

 we will talk about this we will answer these questions。

EAnother thing that its important to know is that this homework is mandatory for PhD students。



![](img/3f5ba5e644a81434cedf134217ed9f20_6.png)

About the date of when we will be where it will have to be delivered。

 we were thinking about after Easter or so not before Easter， not too much after Easter either。

 So the week after Easter， we will fix the date。

![](img/3f5ba5e644a81434cedf134217ed9f20_8.png)

Next week。So it's good to start working on that if you。

 if you have to or if you are interested in into doing this。

So the two questions are referred to how to model the worst case case scenario。

And what can be done about the scenario analysis with the solution。The first question is， well。

 for the worst case scenario scenario， is it okay to take a 99% confidence interval and then add the maximum value on the interval of the oil demand。

Is this the model we are thinking about。 So this is one question。 So you can think。

 or maybe if you have the answer， you can send it through the chat in YouTube。

 And then scenario analysis。 Remember， I said this， in fact， scenario analysis。

 in spite of being popular because it's easy。

![](img/3f5ba5e644a81434cedf134217ed9f20_10.png)

It is rather useless because it is answering to the wrong question。

 It's not what we want to to model just one realization of uncertainty。



![](img/3f5ba5e644a81434cedf134217ed9f20_12.png)

And then the question is， how do we evaluate， do we evaluate and assess the quality of the solution provided by these methodology。

 Because since we run K times if we have K scenarios， we， we would solve K different linear programs。



![](img/3f5ba5e644a81434cedf134217ed9f20_14.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_15.png)

Then。What is the， the response that we will give to the manager of the company。 What。

 what shall the manager do so there are， this is a point that has to be decided on。

 And then so we will， there are some possibilities。 There is one possibilities or some possibilities。

 Let's say we'll discuss some of them at the end of the the the class。 And as I said。

 if you have some answer， just send it to the chat and well comment on that at the end。



![](img/3f5ba5e644a81434cedf134217ed9f20_17.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_18.png)

Okay， so now。Yes， let's remember our records model for the the example。

 we have a cost for importing oil or for bringing oil from the platform， to domestic one。



![](img/3f5ba5e644a81434cedf134217ed9f20_20.png)

A capacity constraint and the fact that we always have a positive non negative quantity for this input。

And then to attend the demand constraints that are uncertain and uncertainty here。 I'm trying to。

 I will today move from the notation we have been using to the notation of the book。

 that of the book of Shapiro and Chava and Rosinski。

 because it's a little bit different And it's a little tricky The notation there。

 So I want to make very clear what is it what it is written in the book so that with the example that also helps。



![](img/3f5ba5e644a81434cedf134217ed9f20_22.png)

Okay， so we had here we represented uncertainty by case scenarios。For the demand， also。

 the productivity of each of the oils in order to produce。Premium or standard oil。 We have our。

Slack variables that as wait can see， this is the gasoline that we will go and buy outside of the factory if we have a shortage。

 given the realization of uncertainty omega K。And well， we have also， it also are slack variables。

 what else。 And we have the probability。 And there is a cost that is paid for buying standard gas or premium gasoline。

In the amount that so that we don't have a， we don't fail to deliver to the client。Good。

 so this is the model。The first， so we will get into the abstraction。 we will get。

 we will write the cost as this vector。 It's a linear cost。

What I also wrote the constraints that involve only the here and now variables in the standard form for a linear programming problem。

 the quality constraint plus non negativity of the variable decision variable。

We can also write in vector form。Our here and wait and see variable。 why。 So now this is a vector。

 And there are as many as uncertainty scenarios。 we are representing in the problem。

 So in particular， it is important to bear in mind that if we had a continuous distribution。

 this would be a function。 Okay， of uncertainty is not a vector， but a function of uncertainty here。

 except that we are discretizing it in this formulation。Okay， if we progress into the vectorization。

 the compact representation of our problem， then。We have the productivity is represented by this technology Ma the matrix that depends on realization of uncertainty times the here are our vector。

 we have added our variable sla variables。 So how now here we have a vectorial equality。In R M。

 let's say we have M quality consency that evolve。Fair stage and second stage variables or here and now and wait and see variables that are coupling those two。



![](img/3f5ba5e644a81434cedf134217ed9f20_24.png)

Decision variables。Well， now we have So the physical set is all。

ACompactified represented in an abstract manner。And another。

generalralization we will do is that the wait and C variables can be multiplied by some metrics。

 because when we represent this as。As in a vectorial form， there may we。

 there may be equi where we don't have the issue of variables in the wait and see part。

 So there is not always only always the vector， but there is a matrix that multiplies this vector。

 And since these are the records variables， the variables that give us this correction in case we made a mistake with the here and now variable。

 Then this W matrix is called the records matrix。 So we have the technology matrix and the records matrix。



![](img/3f5ba5e644a81434cedf134217ed9f20_26.png)

In our relation。 Okay， so the a specific feature of this identity。

 this equality is that it linking the variable X and the variable y。There the other ones now。

 we have either only x or only y variables。Okay， so where is uncertainty in this model。

 Untain as we wrote it in the oil production problem is in the technology matrix。

 this alpha and beta that was given us the amount of input that was coming depending on uncertainty on each quality of oil。



![](img/3f5ba5e644a81434cedf134217ed9f20_28.png)

And we had uncertainty in the right side that is the demand of train， the demand。Okay。

 this is not the only possibility in a general model。For example， the cost。

 the weight and cost that we will call Q。

![](img/3f5ba5e644a81434cedf134217ed9f20_30.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_31.png)

Then， the 7 and the 12。Can very well depend on the real on the uncertainty。

 It may be that in some situations where there is high demand， for example。

 then we are really in shortage。 And then we will have to pay more than in some other realization of uncertainty where the is not so high。

 So this event， in fact， is should be replaced or it's likely to be replaced by some cost that depends on the。

Okay， and。So we will write it in this way。 Q of omega K transpose。 it everything is linear here。う。

Now we have。Another object that can be uncertain， and it is the records matrix。

 the amount of the reaction that we have phase to phase shortage can be depend on can depend on the realization of uncertainty。

 You could see， for example， that we have a contract with the client that we will provide additional gastion in buying in the market if the shortage is larger than a certain percentage not。

 not below below the the gas station knows well they can handle with what is stored。

 So the records matrix also may depend on uncertainty on uncertainty。

 And in general problems that have uncertainty here in the records metrics are more difficult to solve。

 but let's consider for now this general situation So we have uncertainty in the。

wait and see cost in the in the penalties that we are paying for accept to have some invisasibility measured by the wait and see variables。

 we have uncertainty the technology metrics in the records metrics in the right hand side of this relation。

 And these are the four elements where we will admit some uncertainty in the representation。Good。

So as you can see， if we start putting omega case in all these objects。

All the notation gets very heavy。 So there is some simplification that it is done in the book。

And we start by dropping all the。

![](img/3f5ba5e644a81434cedf134217ed9f20_33.png)

All thega the dependence on omega K。So we start where on the cost。

 We eliminate the dependence on the cost， but we don't forget that the cost may be uncertain。 Okay。

 here is the trap。 It's So then let me see we take it from the technology and the records metrics and we take it from the right hand side and we also take it off from the variable。

 why So this is what is it is a little bit confusing if you are not aware of all these manipulations when you start reading the book。

 you some， you may forget about this fact。 So this is why I'm。

 I'm I'm being so slow here to the in explaining this some so careful。 Let's say I'm not slow。Okay。

 so now we have this notation。 you see， well， there is something that has to be done with all these saying how many constraints are we dealing with。

 And then well， they resolve this by Tom。 So where are we， Okay， here by saying almost everywhere。

So we'll put here almost everywhere。 almost surely so or for almost every realization of uncertainty。

And we will say that uncertainty is represented by these random variable Oomega that is in some probability space。

This is the convention in the writing of the book。Okay。

 so what else we need now to get rid of this here。 Okay。

 the probability and the expectation and the sum， let's say over the case scenarios。Well。

 and then like this will just write the expected value of Q transpose y relative then to the uncertainty that is represented by the random variable。

 omega。 so in the probability space under consideration。clude。

 so there is another further compactactification。 And it's that， okay， how we will。

All these colorful objects here that are uncertain。 They will be put in a long sausage。

 and they will they are random。 Then they will define this random vector C。

That will be said to depend on the events that if I， I will define in the probability space， omega。

So， and then all the uncertainties of writing all the time。 Q of omega t of omega and so on。

 we will consider C of omega or sometimes C， and we will forget that we will not forget there will be no re reference to the probability space and omega。

 this C will be representing。 So all the randomness in the problem。嗯。So we。With that。Then。

We have to remember that Y is a random variable in this setting。 Okay， it is here you do see。Yeah。

 you but it is important to remember that X， its here and now and y。

 because of this almost everywhere here， it is a random variable and it leaves it's a function of the random variable omega。

That is the one that determines for each realization of omega。 What happens to Q， T， W and H。Good so。

This is the form。That it is considered in the book。 and its what defines a two stage stochastic。

 linear program。 We minimize here and now cost plus the expected value of the wait and see cost。



![](img/3f5ba5e644a81434cedf134217ed9f20_35.png)

With the the the deterministic here and no constraints。

 the constraints that link here and now and wait and C variables。 And then it's almost everywhere。

 And here is and then non negativity of these slack variables that are of the type of the wait and C type。

And so we remember， we have to remember here that Y lives in a probability space。Like I say。

 this is how it is written。Fortunately， there is a way of reformulating this problem in two levels。

 And this is why is's called two stage that will allow us to see why as a vector in our M。

 let's say there are M variables H here。😊，As a vector and no， not as a。



![](img/3f5ba5e644a81434cedf134217ed9f20_37.png)

A function in a probability space。要不然 no饭谁。So how is it that we do that。



![](img/3f5ba5e644a81434cedf134217ed9f20_39.png)

We do this reformation。By。Separating all day。 Let me go first to， so。



![](img/3f5ba5e644a81434cedf134217ed9f20_41.png)

Here， here， we will then consider a problem all in x variables。



![](img/3f5ba5e644a81434cedf134217ed9f20_43.png)

And then we will consider a problem only in y variables。

 and they will be linked by the y problem will be parameterized by the x variable。

 So it is the first stage。 And then that will be in a second level here and now variables only that are parameterized by the x variable that is in this first stage。

 Okay， so now that I said all that is complicated。 which start then we will consider only x variables。

 So our feasible set will be no random deterministic。😊，Here。

 and in the expected value that we had before the wait andancy cost。

 we will introduce a new function that depends on x and depends on the certainty。 And here is this。

Long vector。That depends on the random variable omega。And that gathers all day。

 all the uncertain objects。

![](img/3f5ba5e644a81434cedf134217ed9f20_45.png)

Okay， and then who is this my this function Q。 This function Q is called a record function。

 It is a function that for a given x and a given uncertainty realization。



![](img/3f5ba5e644a81434cedf134217ed9f20_47.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_48.png)

It tells us what is the cost of the ensuring that we will have feasibility with the X that were considering。

Okay。So it's important to understand this here， I just。

 since the variable is why the decision variable here in this level is why I， I wrote the。

The constraints so that the term with the X variable D X minus T X appears on the right hand side。

 Now it is a data。To to solve this problem， we send as data a specific realization of the uncertain objects。

 This is C C。And we also send the variable X with that。 we define this problem。

 and we can find a solution， a minimizer Y。 that will be a function of X and C。 Of course。

 it will be depending on the parameters that define the problem。

 And this is called the records function。

![](img/3f5ba5e644a81434cedf134217ed9f20_50.png)

And you can see that the formulation is equivalent to the one that we had before， because， well。

 we just once we know these values， if we have， we take the expected value and we are solving our original problem。



![](img/3f5ba5e644a81434cedf134217ed9f20_52.png)

Okay， so what's the advantage of writing these in two levels。Well。

 there are some advantages that I will。 I will now explain。 and you will see it。

 So it's it will allow us to abandon the this the fact that to。

To not consider anymore Y as random variable， even in the probability space。 Now。

 it will be a vector。 This is what is important here。Okay。Well， yeah， I'm。

 I'm killing my own suspense。 So since now C is fix。 This fix is all the data。

 And then x is a vector。 So here we have just a very like a common linear programming problem。

 And Y is a vector in our M。 This is very important here not to forget not to。

 to keep in mind that we are always having this ambiguity。😊。



![](img/3f5ba5e644a81434cedf134217ed9f20_54.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_55.png)

E between the when we see the problem as in， in one stage formulation formulated altogether。



![](img/3f5ba5e644a81434cedf134217ed9f20_57.png)

Here。Here。Well， the way to realize what's going on is to look if there is here or not almost everywhere or what we could have put here。

 we will not put Y is in RM。 but y lives in the probability space。

 If we put the dependence of each of the decision variables here。 Okay。

 so here y is in the probability space。 and we are considering the problem。



![](img/3f5ba5e644a81434cedf134217ed9f20_59.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_60.png)

Without the composing it in two levels of decision。Here。



![](img/3f5ba5e644a81434cedf134217ed9f20_62.png)

We have first stage a problem with only here are no variables， and。



![](img/3f5ba5e644a81434cedf134217ed9f20_64.png)

Many problems for each uncertainty realization。

![](img/3f5ba5e644a81434cedf134217ed9f20_66.png)

And as the function of the first stage variable， we have problems that are linear programs。

 Y is now a vector in R M。So this is good and it's useful because it allows us to。

 to do to study this function that has some interesting properties。



![](img/3f5ba5e644a81434cedf134217ed9f20_68.png)

Okay， so what are the names involved these in these separation formulation in two levels in two stages。

 These are the two stages。 So we have decisions seizure that are taking today。

 And these are the here and no variables。 This is the first stage problem。And then we have。

The objective function here， the second term is given by the expected value of the records function and the records function。

Is gives the value for each X and， and each realization of uncertainty of what will be the correction that we will have to make。

Because we made the decision X and the uncertainty Q， W， H and T realized。So this is the corrective。

Proion or not the correct production， but the what。

 how much we will buy of gasoline outside of our factory and how much it will cost。

 given that we decided to produce this amount of。With our own oil。 But the demand was H， H of C。Okay。

 and these are this is called second stage problem。 the variables， all with variables。

 wait and C or second stage variables。 So first stage is here。 Now， second stage is wait and C。And。

 So these are the names。And already。You can see it is is true that this function is a linear programming problem。

 a simple one， principle， at least it looks simple when written in this way， in abstract manner。

EBut this is for each pair， X and C。And those of you already have studied algorithms for solving optimization problems know that if we want to solve this first stage problem。

 now we only have to care about how to solve our first stage problem。

Then what we will usually do in a nonlinear programming it this is nonlinear Okay。

 because well the expected value is linear， but this record function we will study now。

 this is polyheral specieswise linear。 so it is a nonlinear programming problem with linear constraints。

 Okay， but we have an objective that is non nonlinear。It is， in fact， non differentiable。

 We will also see that。Today， but then if you want to define an optimization method， an algorithm。

 how do you generate a new iterate by at the current point evaluating X K。

 let's say evaluating the objective on the constraints and making some model， right。

 to generate X K plus  one。This is the， the standard way of defining of defining sequence that is a minimizing sequence for our problem。

But now you see there is a difficulty here because to evaluate the objective function at X K。

 will have to evaluate the expected value function。 And the the expected value function is， well。

 you can discretize uncertainty。 then C， you will， we will have scenarios。

 it will be an approximation because if we have a continuous disc distribution。

 we are approaching it by a discrete one。And not only that， it's for X。

 K and for each realization that we are considering。

 we will have to solve this linear programming problem。

 So the evaluation of the first stage objective function。

We require to solve as many linear programming problems here as scenarios we are considering in our model。

 and this for each iterate X K。 So there is a substantial effort that has to be done to。

Simply evaluate the objective function here。And if you have studied optimization algorithms。

 you know that sometimes you are that often you use not only the function value， but the gradient。

 right？ So I while here， we will not have a gradient。

 we will have a sub gradient because this function。As a。A polyheedra is not the。

It will only be smooth well we have only one solution here。

 but it's for all possible realizations of action of uncertainty。 So it's not。

 it's not a possibility。Okay， so you see now that what is the object that we have to understand well is this record function。

 We have to understand。

![](img/3f5ba5e644a81434cedf134217ed9f20_70.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_71.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_72.png)

What is the meaning of making this reformation。And this is what today we will study this。

 And by the way， before I forget， remember that in the first class。

 we use some measure M catigraphic M that was trying to give a meaning to how we would choose our among all our possible realizations of uncertainty decisions taken under different uncertainty ras in the objective。

 And this measure here is the expected value function。 We put it as an example in that。😊。



![](img/3f5ba5e644a81434cedf134217ed9f20_74.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_75.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_76.png)

In that in that class， Another possibility is to use what is called a risk measure。

 A risk measure is， for example， the conditional value risk。

 This depends on the model on the problem that we want to solve As I said。

 in this setting of the oil production problem that is something that is repetitive。We may very well。

 try to， in average to define productions that gives us give us some good solution after we。

 when we simulate， gives us some satisfaction in average。



![](img/3f5ba5e644a81434cedf134217ed9f20_78.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_79.png)

If this problem was to represent some portfolio， optimal portfolio problem。

 where we want to buy commodity stock in the market。

 and we are very scared of high fluctuations this is not something that is repetitive even we maybe。

 we may be playing every day in the market。 that we don't what is not repetitive is uncertainty The fluctuates a lot。

 And then we may be more interesting rather than being satisfied in average we will may want to make sure that we don't make mistakes that are too large。

 And this correspond to changing our measure here by a risk measure， for example。

 that we known by now conditional value risk that is now called average value at risk that penalizes it's rather than the expectation of the。



![](img/3f5ba5e644a81434cedf134217ed9f20_81.png)

Records function。 It is the expectation of the， let's say，10% worse。Scenaars that we may have in our。

 in our representation。 So with that， what we will do， we will be minim our cost。 and， for example。

 the。The manager will make sure that the gasoline that it will have to pay for the shortage will not be costing too much in the worst cases of shortage will be trying to minimize the loss that it will will be having or she will be having for having missed with X to phase the realization of demand C。



![](img/3f5ba5e644a81434cedf134217ed9f20_83.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_84.png)

So， this is。To， to the flavor of the problem and to the perception of risk that the person that wants to solve the problem has。

 okay。We are studying here the expected value because it is the， this is a basic course。

 But and we start with the， the most。like a used a risk measure that is a measure that doesn't care about risk。

 In fact， is neutral to risk。 and it's expected value。

 And advantage of that is that the expected value is linear It's linear because it's a sum of ways probability waste times realization of Q and some scenario K of of X C K。

 So it's a linear function。 And this makes much easier also all the solution algorithms and the representation。

 the other risk measures are not nonlinear and nonlinear at best， they are piecewise linear。

 And this also introduces some additional difficulties。

 So we'll start with something that is very useful and simpler that these expected value function。

 But by the the end of the course we will study also risk measures。

 and these E here will be changed by some row。This the。

 the notation for a risk measure that will include the expected value function as a possibility。

 but will also give us more。The capacity of model。The is makers that the risk covers。Okay， so。

Let's look then at the first stage problem。And as I said。

 we need to study the properties of the records function to realize。

What is the difficulty and what is the meaning， not the meaning。

 What is the difficulty and what it it entails to try to solve the our problem by solving the first stage problem。

Okay， so this is our records function。 And if we fix uncertainty in sumization on C Tilda。



![](img/3f5ba5e644a81434cedf134217ed9f20_86.png)

Then， and we consider the record function as a function of x。 So here。

 the only thing that moves here is x then。

![](img/3f5ba5e644a81434cedf134217ed9f20_88.png)

Well， we want to minimize the the here and now cost plus respect function of this function。

 So it is sound to us when it is finite。 When do we have a finite value for this function。

If we don't have a finite value of pre function， what does it mean to have a value of minus infinity here。

 So this to be a。Mathematicrop should have written here in。

And then what does it mean if we have plus infinity。And， well， we will answer those questions today。

 And they， well， they， they seem to realize what those two。

situations mean the trick is to think in our example。 This is why the example is useful。

 We will also， we will state assertions， mathematical assertions that will depend on what happens to the W H T and and all the elements defining the the linear programming problem under consideration。

 But if you think of on， on our example。

![](img/3f5ba5e644a81434cedf134217ed9f20_90.png)

EThis cost was the， the cost of making a correction to our here No decision that was not rule for satisfying the demand。

So with the cost is minus infinity。 God does this mean。Or if the cost is plus infinity。

 this one is easier。 If the cost is plus infinity。

![](img/3f5ba5e644a81434cedf134217ed9f20_92.png)

It means that we cannot afford this invisibility。 It is so much the invisasibility。The。

 the best that we can do is to pay infinity， to spend infinity money to satisfy the client with the shortage。

Right。Here。If you think that way， it' the opposite。It is that we will not spend anything。

 It is a very cheap record without there is no penalty for having shortage。 It is to this is。

A super low penalty cost in general， those cus are non negative to avoid these kind of situations。

 So， well， but well， there are situations where we can't maybe if we don't want to store too much of why in our tanks。

 for example， then there is a price， a negative pricing if， if it becomes too big， too large。

 And then this can be negative。 but well， it's， this are pathological situations to avoid。



![](img/3f5ba5e644a81434cedf134217ed9f20_94.png)

So。

![](img/3f5ba5e644a81434cedf134217ed9f20_96.png)

The do。The two situations here are infinity situations is， if the records function is minus infinity。

It seems that in our model， inasibility is an advantage， right， because we will spend less。 We want。

 don't want to spend money， and we will spend no money。It is advantage to have feasibility。So this。

 so this is a situation that is likely not to arise very often Its pathological。

 And it is referred to the fact that the function record function is proper。 It's not minus infinity。

 It's above minus infinity。 Does it mean that the gasoline is。

Sa that that you are being paid even for the。 So the question is。

 if it means that the gasoline is free in the market。 It's Yeah。

 you are being paid for taking gasoline from somewhere and given it to the client。

 So it is you see it is a trade situation。 But well this is because we're thinking in this particular model。

 They may be models where we may want to penalize。 but this is deception。 The other situation。 No。

 The other situation where we are in plus infinity。 It may be sound in fact， convex functions。

 This is a case of a convex function。 They are defined on the extended real numbers。

 They can be have real value or an infinity， plus infinity value。 And this is the case。😊。



![](img/3f5ba5e644a81434cedf134217ed9f20_98.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_99.png)

Where we are willing to pay for the gasoline， but the shortage is so large that it costs infinity。

So infinity， the in feasibility， it's， it's in not we cannot take this feasibility。

 We cannot resolve the invisasibility。Okay， so again， I'm sorry if I' am repetitive， but it's。

 I don't want that you get confused here， I use C Tilda。 And this means to fix in all those values。

 and I use the tilda， but the book doesn't use the tilda。 Okay， there is no tilda， and it is fixed。

 So and well， it says that sometimes that it is clear from the context。

 And sometimes it's not if you are starting especially in this， in this business。 So we have fix。

Uncertainty。 and we consider Q as a function of x。 So we will consider this oh sorry for what here。

 So is the til does here。 But our problem will be a this form。

 and x is the only thing that moves well and y， of course。😊，Y子。そあ。How big or。How taller。

Is the matrix W or mini。Have you usually do you have？Then re course fair。Usually， I have the same。

So there is a question about the size of the records the size of the here and now variables and re and the constraints。

 in fact， and that this what defines the number of wait and see variables and the records metrics。

So I would say that in general， there are less first decision variables and more second stage ones。

 because when you make a disctization of your uncertainty， you want to put many scenarios。

 And then that means that you repeat， you have many here realizations of uncertainty。 Now。

 once you fixed。Why it depends on your problem， What was the size of your， of your problem。

 It doesn't it， There is no relation。 What is the size。 What makes a problem。

 the original problem big。So this one， the well， well get here here。

 What makes this problem large is that you will have here many uncertainty realizations。

 and this will increase the number of wait and see variables。



![](img/3f5ba5e644a81434cedf134217ed9f20_101.png)

And there will be the dimensionality of each wait and see variable for each scenario。

 K will be given by your problem where there is uncertainty。 So if you want to keep things control。

 you have to be very parsimonious and very careful in where you decide that you will represent uncertainty because this is what is expensive and well。

 there are， as I said， there is uncertainty that is more important and has more impact in the problem than other other uncertainty。

 So you have to be very， very picky on that。

![](img/3f5ba5e644a81434cedf134217ed9f20_103.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_104.png)

And another consequence is here that was you will have a lot of terms to add if you have uncertainty。

 a lot of scenarios。So， but the relation between x and Y depends on the problem。It' say。

 it's independent of what you can do。 But， yes， is you could model some variables and say。



![](img/3f5ba5e644a81434cedf134217ed9f20_106.png)

Not all of my。 Let's go back to the first。

![](img/3f5ba5e644a81434cedf134217ed9f20_108.png)

The first slide。H。Here。So。Here， we said。We will buy now the oil that we need。

 and we will correct for deviations， both in standard and premium gas。W。

 you could also say if you see that the problem becomes too large or too big。 No。

 I will be giving myself the opportunity at the same time that I buy oil to produce gasoline。

 to buy gasoline。

![](img/3f5ba5e644a81434cedf134217ed9f20_110.png)

Not premium。 let's say。 I don't know，1， one of them。

 And then this variable Y would be Y1 would not would be here or now。So you see。

 and this changes the structure because now the， the matrix T， this here， we will have only T。

 We will have no w。And then we will have only one variable with one relation with the records。

On the weight and survivors and the records matrix， so。You are the owner of the of the model。

 And it has to make sense for the problem you want to solve。

 And this depends on what are the possibilities of if it is it's a real problem。

 what are the possibilities。 Maybe the manager has a partner that is willing to provide to help the company and provide gasoline at a price that is known in the like standard or premium。

 I don't remember one of them at the without having to wait until the realization of uncertainty。

 And then the manager knows， Okay， I have the capacity of production in my refineries。

 And then I have this rank who helps me， if I need some extra one of this one。

 So here I don't need to represent it with uncertainty。So。As you see。

 everything is called depends on what we want to solve and what is what we want to do with the answer of the problem。



![](img/3f5ba5e644a81434cedf134217ed9f20_112.png)

Okay。So， let's continue here。

![](img/3f5ba5e644a81434cedf134217ed9f20_114.png)

Well， so as I said， we will fix， but it remember that it is fixed， even if it doesn't appear anymore。

 Untain fixed， we see this function as a function of。

Of X only we have a linear programming in problem with an equality constraint and non negativity constrain。

 This is written in the standard form， except that the red hand side is not called。

 this is not called B， that is H minus T X， but that's all。 It's parameterized by x。



![](img/3f5ba5e644a81434cedf134217ed9f20_116.png)

So we will use linear parametermed duality to analyze some properties of this problem。



![](img/3f5ba5e644a81434cedf134217ed9f20_118.png)

Yeah。So what is the do of a linear programming problem， It is written there on the right。

 if we call P。

![](img/3f5ba5e644a81434cedf134217ed9f20_120.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_121.png)

The multiplier， like multiplier of the quality constraint。 Then in the right hand side。

 we have the dual problem。 We have to max p times the right hand side of the primal subject to the records matrix transpose times the dual variable smaller than the cost。

These are the for a linear parameter problem in standard form like it here or canonical form。

 we have this is the dual one。

![](img/3f5ba5e644a81434cedf134217ed9f20_123.png)

Okay， and what is it that we know about dual linear programming problems。

 We know that the optimal dual value and the optimal primal value are the same。

 So this is strong duality CR R M。

![](img/3f5ba5e644a81434cedf134217ed9f20_125.png)

EIf both of them are feasible。 No， so they are the same unless both of them are unfeible。

That that's the statement。So they have the same optimal value if they are both feasible。

 What feasibility means it means that。So today， I will come to the very end here， the same。



![](img/3f5ba5e644a81434cedf134217ed9f20_127.png)

Optimal value。Do all un primal。And peace。If。There is an x1， such that。嗯。W Y。1。

 it's equal to H minus T X 1。For some。Y1 non negative。 So this is primal feasibility。

 So the feasible primal set is not empty。And。There is MP P1。Se that。Omega AW transpose P1。

The smaller or equal the。什么的？No， that that rather unequal than Q。As well Okay。

 my eyes are not not good。 So we have non emptiness of the primal set and non empty of the do well feasible set。

 And there are those conditions， which is not much to ask we have。

 because here we don't even have a sign。 you see for P1 here yes。 but here it is even it is for any。

 any sign in the components of P。 So we have that the optimal values。

 primal and do well are the sign。This doesn't mean that they' are finite。

That if we have a finite value， then there are minimizers Y here R M P here。



![](img/3f5ba5e644a81434cedf134217ed9f20_129.png)

And P star and y star thats of course， depends on X and C。 And for the given pair。

 And also we have that well， the multiplier of this equation at the optimum is the solution of the dual problem and so on。

Okay， so。We will study then the function written here in this dual form and why it is interesting。

 because here you can realize what is the shape of the function。 And I。

 I used here the notation of the book。 although I don't like it much is capital P of Q is the multi dual variables that are feasible in the dual。

😊，In the problem。And then if you right now in one line， our records function。

 assuming then that we have a quality between primal and dual optimal value。

 So Q of X C is the solve the dual problems。 So we are assuming that condition they are of both problems have non empty feasible sets。

Then you can see this is， you can see that the records function is as a function of x。

Its these are linear， a fine functions of x a constant term and a term that depends on x。Right。

 and we are moving also， were taking the maximum of a functions over a set that is this set P of Q。

Right， if we do a drawing， so we have。

![](img/3f5ba5e644a81434cedf134217ed9f20_131.png)

One function for1 P1。 Let me call it F P1。

![](img/3f5ba5e644a81434cedf134217ed9f20_133.png)

Of x。Then this or F J， Let me call it F1。 then F J of x。It's given by the。



![](img/3f5ba5e644a81434cedf134217ed9f20_135.png)

P transpose or H。

![](img/3f5ba5e644a81434cedf134217ed9f20_137.png)

Minus T X。B嘴嗯。For P in this set。Cpy that P of Q。嗯。So this is J。 I don't know how many。

 There can be infinite if an infinite number of them。 But what。

 what we see there is that if we take for1 p， we have this F1， another P。

 we will have another linear function F two of x。

![](img/3f5ba5e644a81434cedf134217ed9f20_139.png)

Another。P F J of x Pj。

![](img/3f5ba5e644a81434cedf134217ed9f20_141.png)

And then。The maximum that is Q。Its here you can see the maximum is this function here。Okay。

 this is Q of X。9。For Fix C。Right， so it is in this drawing。

 It is a piecewise linear function that is convex because it's a maximum of a fine functions。

 And at the point where two functions coincide here。 We have that there is no the derivative。

 there is where the the function is not differentable。

 These are the kings of this function that is convex that is non smoothm。😊，Right。

 so this is a row in R 2， in R， not even R 2。 And in a more general setting。

 we will prove we will show today that we will see I will do some hand waving because there is some convex analysis involved in this manipulations that I will make。

 but that this function is convex， and it is polyheedral polyheral means that its piecewise is a fine function like this plus some infinite values outside of a set。

 The plus an indicator function。😊。

![](img/3f5ba5e644a81434cedf134217ed9f20_143.png)

Okay， so。This is an introduction。 Now， we will study a little bit more in detail now。

 writing in the blackboard。 Let me see if we。So yes， Q is a maximum of a fine of a fine functions。

 And the maximum is taking over this set。 So all those P1。

 P2 and P J are in this set capital P of Q that it is given by this linear inequality。

 And this is a polyhedrum。

![](img/3f5ba5e644a81434cedf134217ed9f20_145.png)

![](img/3f5ba5e644a81434cedf134217ed9f20_146.png)

All its intersection of half space。 So it is a polyheedum。Each one of the alliance of these。

 we have to the columns of W multiply by a P。 the this each column gives a line here。

 And then the intersection of all these half spaces is the this polyhm。Okay。

 so now we will go into the Blackboard to review。All these complex analysis concepts。

 I will try to be precise without entering into much in detail。

 which may mean that I we may miserably fail， but I will try。

 So if you don't don't understand something just ask。 So we start with cones。

 we need to work with cones， I will。So I will just， maybe I will copy here。

 What is our function that were studying。

![](img/3f5ba5e644a81434cedf134217ed9f20_148.png)

Q of x。

![](img/3f5ba5e644a81434cedf134217ed9f20_150.png)

See is。The maximum。Of P transpose。H minus T X。Sject two can be short。W transpose P smaller than Q。

And with a note the by the set capital P of Q。They say the feasible set in the in this S respiration。

 the will transpose P smaller than you。Well， one thing that is straightforward to see is that for example。

 if we know that this set is compact。Then we are here maximizing just a a linear function over a composite set。

 This would give a finite value to our records function at these at x。At any X， in fact。

 So properties of this set of this polyheedron are important。

Another thing to realize before we go to the other side of the blackboard is that。

This function is a composition of two functions。When that the book calls S Q。That applies our M。

In our the extended。3 years。And that to each sea。Asigns the maximum。

Of the inner product between C and P。For P in our set， polyedral set。So if I compose this function。

Wait the assign fine。诶诶。Relation H minus T X， I get Q。 So Q of x。See， it is this function S cube。

Evalu that z equals h minus the x。H minus。对呀。And why is it that I'm doing that。Okay。

 so my queue is more cur than the queue there。 Let me do it more square here。Kim。

And went into the here relationship。Lo there。So。So we have this relation。 Okay。

 so this is an a function。 If we are to use the chain rule， for example。

 to know of the differentiability properties， of the first order object of this Q function。

 Then we will the derivative with respect to x of the argument is minus T transpose。

And then we will have to see what is the derivative of the function S S Q。

 This is what we are doing this to it is composition to get rid where and see where the difficulties come from all the of this records function comes from this function。

 S Q， not for from this linear term that is easy to deal with。

And this function is called the support function of convex analysis。

 It's a support of the set over which we are taking the max。嗯。

This is the it's an important object in complex analysis。Okay， so we would come back。

To our function S Q in， in books of convex analysis， this is called this the notation is different。

 The notation is for a set S a function is sigma S。

 the support function sometimes is called delta versus of S。 So the Q here it。

I don't know why they chose well。 I know why。 but I they。

 there is no relation to reference to W in the notation， for example。

 So it's a little weird as a notation。 but this is what it is。 So this is a support function。

The support。Function of the set。B of。Good， now， yes。 let's go to the other side and play with cones。

So suppose we have an ice cream cone that is easy too。To 들어。呃。

This cone ohs are usually dennoted by k。A go。In the。Where are we living there in our M？Our M and。给给。

So for a cone， the definition of a cone is that you take an element in the cone。

 You multiply by a positive scalar and you stay in the cone。 right， This is a definition of a cone。

Now， what is interesting also is that if we take a point in a con， let's say here。

 let me see how I call them。 I call them X， okay。I'm not sure I should be actually let me give any minute。

呃。Z， I will call them Z because I here where I want to Z。C C0。In the cone。

 And then if you consider the half line， you take a direction。Deep。In R M。

 and you consider the half line that starts in C，0 and grows in the direction。

So this is C 0 plus T D。 No， sorry， the T TD for T。T larger than 0。

T that grow from0 to plus infinitefinity。 So this halfline。So a cone has you can。

 there are directions where you will stay inside of the cone and go to infinity。 And well。

 if I take something like this， of course， I will， I will hit the bottom of the cone and I will not stay in the cone in the I will not stay in the cone go in along the half line。

 if I go with the go into infinity。Okay， so， in fact。If we have a cone that is close and convex。Okay。

 here， everything is prepared。Im doing it。 And That what。Okay， so it's close and convex。It can be。

It can be shown that， in fact， a cone is a set of all those directions that when I start from a point and I go in the half line。

 I state inside of the cone。 so it can be proved and it can be proved is that I will not prove it that K is is equal to。

Or the。The sets of directions。Let me see how will I write this。That its intersection。

For0 greater than 0。 T a little。 So I take。X in x C0 sorry， C0。I take a point in the con。And。

It points in the cone and then C0 plus T D a direction leaves in the cone。 So the cone is， in fact。

 formed by all those directions。Along which I can go a halfline and stay in the cone here。

 it will be like the directions are here in this， in these the the mouths of the ice cream cone。

I could have also a poly call。 Then it would be square here a more like with angles。 Okay， so a con。

 in fact， can be written in this way for any  point C0。试试咯 in the讲。

So all the directions along which I can go to infinity starting from points inside of the con。

So the recession cone is the extension of this object here for any set。嗯。So。Now， we take a seat。

close。Gvic。可以。Sit。CN RM。Consider。The set of， then of all I take。My set。And I have a CC O。

 I divide by T and the intersection for3 positive。😊。

What does this mean is take a point this0 in the in the set C and look at the half line in which direction you can go to infinity。

 If I have a polyhedron。Is this a sea。I take C0 here。

Is there some direction along which I can go to infinity and stay in the comb。 There is none。

 So this set will be only the direction 0，0。But if I have。They said。Okay。Let's say。

 open an open mouth。That set will be given by directions that go I can go in these directions to plus infinity and stay in the in the set。

 So this is called the recession con。 and it's written。 It's thened by C infinity here。

 we will write at C0。And this is their recession call。Off。是。

And it is called the recession count of C， because， in fact， it doesn't depend of C 0。

 doesn't depend of the。Of the definition of the of the point that we are centering it in it。

 And that we will prove that， in the definition。And it is a con。 also。 So the definition。Independent。

Of C。So。Let's make a proof。AndFor making the proof， we will just take。

Two different centers and see what happens with the directions。 So we'll take show proof。

Take C 0 and C1。In our M。And then now we'll take a direction that is in the recession cone center at C 0 and will prove that is in the direction and it's a recession direction if we center at C 1。

And then since 01 interchangeable。 Then we will prove that the set is the same， Okay， so。Alet。

DV in the this recession cone at C1。So this means that the halfline there is in the。

In the in the set sea。So， that。C，0。Pless地。They belongs to sea。

So what we will do now is we will the use complexity the little portion of C 1。

 And then we will write by complexity。 We will stay in C And we will finish our proof。 So， let's。

 but for finishing， it， we have to start it。 So let's continue。Okay， so let's consider a take Z。See。

 then will be。Let me see。Z 0 times epsilome plus。呃。1 minus epsilon。诶。s one。Bless the。B。

This is see that for some epsilon， that is small。For。A small。Epsilon and。保是对不对？自试都食惯。Okay。

 so now we will write to the right things so that we are in， in our favorable condition。

 then so let's。Write it， C。Let's see epsilon times C 0。Minus。

 let me see what is the good thing to do here。哎，这这中。So no is0 plus。

T times here divided by Epsilon Z R D。 we put together those two。And then， what is left1。

Minus epsilon， C1。Right。Just the。T here a factor。 And why I did that。Because。

T divided by eon is a positive number， and。Ay。C0 plus。

A positiveitor number times d is in C because C D is a recession direction for C0。So， this。

Belongs to sea。Say1 belongs to say。And she is convex。So呃。C， convex。Implies that。That were。Is he。

A is in C。 in I said C。Okay， now this Z is parameterized by epsilom。

And we have used that the set is convexed。 We have not used yet that the set is closed。

 We will use closeness of the set C by making epsilon go to 0， driving epsilon to 0。So， letting。

Epsilon go to0。We have。That。So where do we where。The limb of a sea。As epsilon goes to 0， I could。

 maybe I could put a super epsilon so that we have epsilon in the notation here。See。

So one epsilon goes to0。We go to C1。So 1， epsilon goes to 0。Let me see， But I want it。 No。 C 1。

 When Epsilon goes to 0 here here， we can see in this formulation。 this term goes to 0。

 This term vanishing vanishes。 and then we go to C 1 plus T D。With C1 plus Td。Right。

And since the the set is close， the limit of。For of elements in C is also in the set sea。So， C1。

Flulash， did he。Belongs to sea by close means of sea。Okay。

So we have proved that if we have a recession direction for one point。

Then for any other point that we take that is different。

 the direction is also a direction of recession for this other point。

 So this means that recession directions do not depend on where we center our。Our intersection。

 And this is why， in fact， the notation is sfinity。So the recession directions are defined as。

Sfinity offinity， the set of directions in R M。Such that， then。C，0 plus Td。Belongs to C，4。S C0 in C。

Once we found one。It's true for any other one。Okay。Now。

 let's see what is the recession cone for our set P of Q。This said here。んだどやれインターネッテネント。We for。See。

Equal P of Q。A recession con。 So if we have a polyheum。Pciion。Conone。

 this cone is sometimes called the asymptic cone because it these of these lines。

 So the the recession cone。Es。Give him。我读。What we need is， by。D in R am。Search that。Okay， now。

We have ball is P。 Now， the elements in in P of Q P。 So should have called all these P bond anyway。

 So P。P0 plus TD。Belongs to capital P of Q。For some PC0 in there。In the。Well。

 but this is the same than asking that。W you transspose。P 0 plus T。D is smaller than  Q。嗯。

And all this is w T。P 0 plus T times W transpose D smaller than Q。The first term is smaller than2。

 because。P0 belongs to the set。So， and is positive。 So what do we need。For these inequality to halt。

What is the sign of this？As to be smaller or equal， right。So， I done serum。Okay， since。

Thiss positive。The mask。Satisfy。That。W transpose the。什么聊程西。嗯。So， the recession cone。Of our set。

 P of Q。I would right here。So we have this， and we have that。B of Q。Infinity。

Is equal to the set of directions。In our M。Such that omega transpose D is smaller or equal。Don't see。

Okay， so while this is incidentally， it's also called the polar combat of this set in this case。

 because we're in a polyheum。 But why this is important， because you see here。

 we will do inner products。B for elements in the set。嗯。

And if we have in this polyhedron directions where we go to infinity， if it were compact， it's okay。

 We， we have a finite value。 But for the point where we have recession directions， then we will have。

We will have this value that goes to infinity because we can make it。

 We can make this product as big as as， as as desire。 So now let me come here。Here。

And then let's continue then analyzing our polyhedron。 So a polyhedrum， then is the。A polyhedron。

A polyhedral set， well， if you want a polyhedral。呃。Is is it that is equal。

 So there it doesn't have round borders。 It has corners and it has vers。 Okay， so if it is compact。

 it will， it will be the same。A polyhedron C， let's call it C， now P P。Speep。嗯。

Is the sum of two sets。1 is the convex hall of the vertices。



![](img/3f5ba5e644a81434cedf134217ed9f20_152.png)

Right。呃。呃。Or extreme points。It's where this says， these are called extreme points。

And if they said as my throw before。If I set is compact， then our set P。

 then all these are our extreme points， the veres。 it's enough then to have those points and the convex hall of all the of these points will define my set P。

Now， if the polyhedron has some open style as in our。Secondcon？

Then we have to add to this convex call， the recession directions。

 the con defined by the recession directions。 So its a sum of two sets。

 the convex hall of its vertices and its recession con。So this is also something that can be proved。

That we will not prove because well there are too many definitions that go here in the extreme points。

 But you can say graphically， more or less get an intuition。So we have our set。

 P of Q is a polyhedron， It a polyhedra set。 And so it is the convex hall of its vertices plus its recession con。

And。In particular， when the a polyhedron is bounded。

 then the recession con will be just the0 direction。

 and then it will be equal to the compos hell of its vertices。 This is a compact polyhedron， right。

 the compos hell of its vertices。ESo it's a sum of two sets。 It's a recession Kong。 So for our set。

 P of Q。We have that is the complex hall of。Let me call them V1 until Vk。Of it's where this is。Plus。

 it's recession con。BfQ。嗯。infinite infinite。So in our in product。

Inner product defining the support function。Cat transpose。B。We will write it as Crus post。

 the Congress He of the Artes。Plus， Crus post times the directions of recession。

Is written acironpose times sum the。The sum of alpha I V I for I between one。Okay。Plus。

 C transpose the。嗯。4。Alhi greater than0 s terms。 It's a complex combination between one and K。

And the。In the recession Kong。So for for any direction in the recession count。

 this maximum can go to plus infinity。 So what， what happens here。This maximum here。Then。SQ。Oscene。

Would be。The maximum。Off a zip。Tspo Vs for I between one。Okay。If。呃呃C呃 C。呃。Yes。

 if C is in the recession call here， please transpose。Let me see now， plus indicator function here。

Cl。They indicator function of their recession cone。B of Q Q， Mr。Let's see。嗯。Then the kto function。

sorry its anの of。Where。Are you S。At that point C。Is plus a0。If C is in the set。嗯。In the set S。

And plus infinity。Otherwise。So I can define the inner product in the in a in the compact set that is given by the vertices。

 If I get out of the inner of these compact set of the vertices。

 I can increase my my inner product as much as I as I want。

 and then the the value of the indicator function will be of the super function will be plus infinity。

 So we have a question。That think。Yes， it is a polar count， yes。呃， it对是。Upper P of Q star。Yes。

 it is the polar cone of the。Of the set， not the recession。 Yes， it's a particle。So。诶。Okay， so。

Suming up。Let's see here， PC0 plus B。M哼。😊，Plus D。Did I write。我哋双谁康谁上空。都是果了。Here is a partnerer。

 Here is a partnerer。嗯。No itちょっ is it hereか。So。See， otherwise。第一。Do you star。Well。

 and then what this， where this take us， After all， these calculations。

 So we have our indicator function， then。I will indicator function of C。Will be the maximum of some。

Fanunctions a。VI transpose C for linear functions for y between1 and M。Plus。

The indicator function of a con that is。B of Q。The star。Of the sea。And this set is a set of。

Diectction。Or is should I put it somewhere here here。嗯。The recession direction。 it's also。

 it's also the polar corner of this set。 It is the same here。It is。They set of。Diects in R M。

Such that omega transpose D is smaller than 0。嗯。So when Z belongs to the set。The support function。

Takes a value plus infinity。Otherwise， it is has a finite value。So they for all。

So we have a finite volume。Final value。Support function。I see。That belongs for4 C。For Z。Such that。

Oomega transpose D。Is larger than 0。That doesn't belong to this set。Right。And this set is called the。

Positive cone of w， so。This is post。OW嗯。呃，保对。干。Of a。Of， of， of the Ma generated by the matrix W。

 Let me， let me write try this。 Let me leave it like this here。Okay， so it is， we had。

Then what is it that we have seen so far。The record function is the composition of the support function and the linear function。

 It is piecewise linear。And it has a part that can be in infinite。

 depending on whether we are evaluating it at this in this polar cone or not。Now。

It is piecewise linear。 and we have then that it has points where the derivative is not does not exist and it has a sub gradientdient。

 So in the next class because now we went into the end。

 I will write I will explain what is the subdi of this function。

 and then we'll continue with the the the， the， the next part with what well I'm be coming a little incoherent。

 Sorry， So lets we'll take it to the next class， I will explain the subdi of this function。

 And now let me。I here， just go back to a homework。And then， so we had those two questions。

If we can take for the worst case， how do we define the right hand side of the worst case linear programming problem that represents this stochastic program that we want to handle uncertainty of。

 And then well the question was， is we can take a confidence an interval of with 99% confidence and take the maximum value on the to add it to the right hand side that we have。

And the second question was， with the scenario analysis， What would be the final answer。

 What do we take to evaluate this， the quality of the solution。Okay。

 so the answer to the first one is yes， you can do that。The answer to the second one。 What here。

 it is。You can wonder what is the you have K， K solutions。

 You solve the situation for K different scenarios， and then you have K X bars。

 K solutions that each one is feasible for the realization of uncertainty that is considered。 So。

 well， you can take some worst case solution。You can take an average of the K。

 but remembering that it has to be it will be a bad bad response， because if you take， for example。

 the average of the K optimal solutions， well it may not be even feasible if the linear is a feasible set is non linear here。

 at least it will be linear。 But so well there are you will have as a result that if you take the worst case or if you take the average of the of the case solutions。

 the quality of these solution provided but scenario analysis will probably will likely be very bad。

So for those who are not here， the this work， homework。

 we will have it evaluated in the week after Easter。

 then and we'll decide the date to accept date next week。



![](img/3f5ba5e644a81434cedf134217ed9f20_154.png)

Okay， so， yes， that's the end of our， of our class today。So see your next Thursday。

 We have a question， yes。Another question about the homework。看 of。Mmmm。😊，Mmhmm。こし。How do you。还不让我去。

嗯hu。😊，No。So I will repeat the question。 The question is。

 if you have a worst case scenario and you have the chance constrained model。

 how you compare the two the two solutions。 Well， this is the purpose of the homework for you to realize that you the worst case scenario proposes this model And then you get a solution and x W because it's worst。

 And then you write your model with the chance constraints where in this case。

 you can put explicitly。 And。You will solve and get your X P solution。

 And then the comparison will be to send simulation。

 So to assess the quality after with many scenarios me and 1000 scenarios and see if it is feasible。

 for example， in how many situations its feasible。两期。れの。You cannot know。

 you cannot guarantee because the chance con it will not。 of course， it will not。

 But this is where the decision has to be made if you are satisfied with the probability the reliability of the worst scenario or not。

 And you can also check how it improves the reliability if you increase the number of scenarios and how much more expensive it is or not with respect to the chance constrain。

 This is just you have to do the analysis and well it is this problem and this exercise is for you to realize the kind of situations you have to resolve when you do with the stochastic program。

 there is more it is more expensive。 and then it is more reliable or it is less expensive and less reliable。

 and then there is this tradeoff。Okay。Have more questions？No， okay， so now we finish this， thank you。



![](img/3f5ba5e644a81434cedf134217ed9f20_156.png)