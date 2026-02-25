# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p15 -15-Basic Course on Stochastic Programming - Class 15.zh_en -BV1tH92YXEnd_p15-

Okay， good afternoon。 Welcome to the bus lecture number 15。So continue。

 continuing working on stochastic Mo stage stochastic programs。 Today， we are going to focus on the。

 the linear case。I'm going to re， to， to revisit that the T RM you saw on the last we saw last the class。

 But for the linear case， I'm going to pass quickly。To this Ethereum。

 And then we are going to focus on a multi stage to ask linear programme problem based on scenario 3。



![](img/d536f8e85cdef1b38381a776353b0898_1.png)

And， well， we are going to start also on on optimization。

An algorithm for solving this kind of problems。Well。



![](img/d536f8e85cdef1b38381a776353b0898_3.png)

Okay， let me start here。Once again， resolution should be good enough。Well。So far。

 we were focused on the， we were focused on the， the more general case。

The this function can could be nonlinear。 Yesterday。

 we made an assumption that saying those functions were convex。

 We assume they were convex and these feasible set， the feasible sets for each stage linear。 Well。

 today we are going to。To assume。That those functions are indeed linear。

 I have added here indicator of the indicator function， the indicator of this feasible set。

The no negative orthoant。But we can just move this constraint。

 this indicator put as a constraint here in this feasible set that we are assumed linear。Once again。

 because the last class， we also assume the linear。Let me see if there is something。No， okay。

 So just the。To say that today， this is the focus。Well。Assume the function is linear。

 as I in the previous slide， we had the indicator function。 So I， I removed the indicator function。

 but I put here the constraint Sp explicitly for each stage。 We have the stage。

 We have this constraint。

![](img/d536f8e85cdef1b38381a776353b0898_5.png)

Well， our function。Linear or each stage。 Once again。 Well， we assume what are the。

 the random data here， Well， could be。Maice B， matrix A， this vector B， the cost C for each stage。

 So I'm just calling this Kci。呃。This big vector， with all the data。



![](img/d536f8e85cdef1b38381a776353b0898_7.png)

Can be uncertain。Well， this is the nest formulation。 as I said previously， previously。

 we can use here the conditional expectation。

![](img/d536f8e85cdef1b38381a776353b0898_9.png)

The same thing。

![](img/d536f8e85cdef1b38381a776353b0898_11.png)

How it becomes for the dynamic problem formulation。



![](img/d536f8e85cdef1b38381a776353b0898_13.png)

Well， we focus on the start from the last stage。So in this case， well。

 we assume that are given to us a previous decision within the previous stage realization of the random data。

And here we are just minimizing。 well， we are minimizing a linear cost over a set of linear constraints。

 And since we are at the last stage， we don't have a future。Cost here， okay。



![](img/d536f8e85cdef1b38381a776353b0898_15.png)

For the other stage。Notes that we， we are using the same notation than last class or this function。

Okay， here we are minimizing the， the cost of that at that stage plus the future cost。

 the expectation， conditional expectation of future cost。And。At the beginning， the first stage。

 what we wish to solve。Is this problem here？

![](img/d536f8e85cdef1b38381a776353b0898_17.png)

Well， we saw。That this is a convex。Program。Because the this function， this partss linear， this。

 the future costs this function。 we call it the requires function is convex in x。 and well。

 we have linear constraints。I would call attention。Call your attention here for。



![](img/d536f8e85cdef1b38381a776353b0898_19.png)

One thing that you may say， well， this formulation is not general enough because you may have problems。

I written this form。For example。

![](img/d536f8e85cdef1b38381a776353b0898_21.png)

Thanks。Expectation。So。The first stage cost。Plus。Second stage。

I'm assuming this decision depends on the history up to stage 2。Plus。UpTo the end of the horizon。

And here， once again， this variable is depending。On the stage T。啊。Here。

We have the first stage constraint。To one。So nothing the same thing than our formulation。Here。

 for the second stage。We just change the notation bit here to be  one。X1。2。This x。Depends。

On the history。Now comes the difference。Because I'm assuming。The one。X1。Plusus。B2。X 2。Plus。A3。

What's the difference when you make the decision at stage3。

 we depend not only on the decision of the second stage， but also the first one。And so on。So。

You want x1。Be。So even though， okay， when we are at the last stage making a decision。

 this decision is depends is ind by the decision we made at the first stage。



![](img/d536f8e85cdef1b38381a776353b0898_23.png)

So， if you look。Compared this program， this formulation。With the one we are using here。

I's not the same。Okay， the formulation is not there。

 I wrote as general formulation here as an necessary the formulation。 But the fact here。

 you see that at one stage， you depend。

![](img/d536f8e85cdef1b38381a776353b0898_25.png)

Only on the previous one， not in the history。All the scene you have made along the history。呃。

So you may see， you may think that this is very different from that formulation。 in fact， no。

We are not losing。Generalality， when we are using that formulation， and I will show you why。

But before， let me write the dynamic。Programm equation for this。This problem。So， our。

Cost to go function at stage T。Well， youll depend。嗯。All the history up to stage T-1。And the history。

 also of these decisions。Okay。This is。The Asian。哦。Have the cost。Plus， the future cost。

Of the cost go function stage plus1。 And here。All the history。Oh the hester。This one。And in fact。

 the constraint I here the decision is xt。And the constraint will be。The sun。到。Is starting from。

1 up to， up to T-1。Mattris B。Gao。X。Al plus 80。Xt。一。And X T。

So I forgot to write here all the decisions。

![](img/d536f8e85cdef1b38381a776353b0898_27.png)

In fact here。My I got greater or equal to 0。And you want to satisfy。Those constraints， almost surely。



![](img/d536f8e85cdef1b38381a776353b0898_29.png)

Well， in this case， well we have to pass all the history the decision we have made since the beginning。

Because we depend， we need these those decisions here to define the feasible set。So， if you look。

For this dynamic program equation。

![](img/d536f8e85cdef1b38381a776353b0898_31.png)

Here is different。It just depends on the previous one。But the fact。



![](img/d536f8e85cdef1b38381a776353b0898_33.png)

If you make a little change。We can cast this problem in that formulation。

And the trick is default fault。We can define。X variable， Rt。That's going to be equal to。R I R T-1。

Plus。아。This one。T equal to1。St。And starting with R 0 equal to 0。Assume this trick。

 we can write this problem as depending only on that variable R。That's going to be。A tea。us1。

The history。いこう。If分。啊。第一。X， T。Plus。The expectation， again。

And the future will depend only on that variable。In this case， our team。And。Well， decision variables。

Well be。XD。RRT。The constraints。Willll be。Rt minus1， what's given？Plusus。

And we just updated the new variable R to pass to the future。This is going to be。Just this。Well。

 wait， I think I。Did something wrong here。Yeah。I think I did。Let me see if this makes sense。こ存。

Do might not one。Well， yeah。That's true。So fact here is just tea。But just me check of my notes。Okay。

 here。No， it's correct。

![](img/d536f8e85cdef1b38381a776353b0898_35.png)

Not T -1， but T。But now， if you looked at this problem， it has the same formulation than this one。

Okay， a variable of the previous stage。Rt minus-1。Enterters as a parameter here in this problem。

 Here， I'm going to define another variable。And you are going to pass to the future。

So if you we arrange， give another name for this mattress。

 we can arrange and write exactly the same way。So there is no loss of generality considering this sort of dependence。

 One stage depending exactly the previous one。Okay， there is no loss of scenarioity。Okay。

 so let's continue。啊。Well， our goal is to solve。This problem in red。Well， we may call it differently。

 using this choiographical queue。Which is the records function。 Nothing changes here。

 the same notation。Other classes， except for the constraint and the objective function hit。

 that is linear。And。Let's check again。 Once again， the theorem of last。Clas。Well， in our case。

 now we can。Call this function F T as the linear cost plus indicator function。Well， this is the。

 the dual variable that lies in this set。That is the set of flag multipliers for this。 be problem。

And the theorem we， we studied last class is the following one under some assumptions， for example。

 in Italy many scenarios and polyedro function F， which is the case here。A feasible policy。

Is optimal if only if there exists measurable。well variable。Such that this inclusion is verified。

Well， so we proved this theorem last class。 The difference here。

 Well we're just going to replace this function。By this one。And since the。Well。

 the domain of a linear function is the entire space， and we can use the。



![](img/d536f8e85cdef1b38381a776353b0898_37.png)

Moio hookkaellereller theorem and pass the sub differential compute here for indicator function。

 The the sub differential of indicator function is the normal con where let know。

And you have this alternative， exactly the same thing， but。Inclusion for this case。呃。What's。

What does this inclusion mean？The this optimal condition。If you are。Well， you want to。

 to find the optimal policy for the your entire horizon。Planning horizon。Does it。

 is it saying that the decision you have to make the。

 the optimal decision for entire horizon is the decision that the optimalimum for each stage。

So its my a question。 Let me repeat。For a policy to be optimal to entire horizon。

 the policy has to be opt for each stage。Is this what the theorem is saying。In fact。嗯。But。

Let's make a drum。Drawing。So what I saying is， I want to find a policy which is optimum for the entire。

Hizan。The Ethereorum is saying that， well， to construct this policy。

 you have to make the optimal decision in each node。 So this is going。

 you have to make the optimal decision if this uncertainty is revealed。



![](img/d536f8e85cdef1b38381a776353b0898_39.png)

We have to make the optimal decision decision at this stage if these uncertainties are valid。Well。

 the answer is no。It's not that。You have to make the optimal decision here， but take into account。



![](img/d536f8e85cdef1b38381a776353b0898_41.png)

The future。When you are at the last stage， yeah， you have， you make the ultimate decision。

 that stage。 for example， these stages is that day， the last day of the month。

 you are planning the expenses of your along your month。 So you have your salary。

 you are planning your expenses。 And at the last day of the salary。Of the month。

You make the optimal decision for that day。But in the previous day。

You have to make the optimal decision here， but。Seeing the future。

You have to take into account the future。 Not okay。 I will make the best decision for today。

 but the decision I make today， for example， is to exp a lot of money。

 which is not my case because I don't have a lot of money， but spend all my money。 But then tomorrow。

 I don't have any money。So you have to far in the the future。

 So what the theorem say is to construct an optimal policy， you have to make him。

An optimal decision here。 That's not all optimal for that。Note of the tree for that stage。

 but also seeing the future。 when I'm saying optimum。

 but optimum is in a sense of other average because you are using average， Okay， on average， optimum。

Well， so this is what the theorem is saying。啊。So， from now on。Let's work on。With scenario3s。

And let's see two computational methods。 One， it's very simple。But not so very efficient。

 And the other one， which is the nested de composition。

 that's it is a very well known and used methodology。 Well， this is light。

 is light is just summarizing what we saw the last week。 So this is the definition that I。

 I already show with you。For example， the number of scenarios。Is K。

 capital K the number of realization。 Each realization is called a scenario that comes from the root and old。

 So again。Up to the last stage， this is a scenario。The probability， So I call this。Saiai。

The probability of this scenario， I would call。PI。那么凶。That's strictly positive。 Otherwise。

 we could just， if it's 0， the probability of the scenario is 0。

 You can just remove that scenario from this， the， the， the three。嗯。

The set of all nodes at stage T is omega T。If you consider all the nodes here。I call it。Omega T。

Another important definition。We are going to call a shorthand for the the for the node of a three。

 We just call this aota or J or I。 doesn't matter。But the previous， the father of that node。

 you are going to use this a。It's just the ancestor of the given note。

The set of descendants called the children nodes and the set of children nodes for a giving node we are going to call by c。

Of L， yota。呃。The probability of a given node， I'm going to call by using this parent parenthsesis。

And。This is given by the probability of all scenarios that pass through that node。What's this。

In this case， well， if I know the probability here。I want to know the probability of this node。啊。

What's the probability of this node is the sum of the。The probability of alls that has this node。

Okay， this is what I'm saying here。The conditional probability is the probability from moving to an node to an another。

So， I call it。Hu。Passing from。Anode to another one。Of course。

 the sum of those conditional probabilities， one。For in this case， here， for example。

 this probability， once you are here， you know at the future。 you can anticipate your future。

 This probability is this case is one。What's the probability of reaching these nodes you are here。

 one。Okay， and the probability of okay， another form。

 another way to compute the probability of an node， just multiplying out the。



![](img/d536f8e85cdef1b38381a776353b0898_43.png)

The conditional probabilities。This is very of basic。Well。Let's start to work on with scenario。

 scenario 3。

![](img/d536f8e85cdef1b38381a776353b0898_45.png)

Let's start with the。Next of the formulation， we have already same this is what or general case for the linear setting。



![](img/d536f8e85cdef1b38381a776353b0898_47.png)

When you use the scenario 3， you are going to use this notation of conditional probabilities。

 We can write the expectation like the sum of all the nodes and the transition probabilityities。

 Its the case here。

![](img/d536f8e85cdef1b38381a776353b0898_49.png)

So you are going to sum out this probability。This probability multiplied by the cost of this node。

 the probability here multiplied by the cost， the cost。 and just this this。

 the sum is the expectation in this case。But here。I'm not very clear。Because this sum is depending。

 the sums are depending on aotta， the nodes。But I don't。 I'm not saying the。

The nodes here in this notation。

![](img/d536f8e85cdef1b38381a776353b0898_51.png)

But I'm here。Here， I'm putting the dependence。And。Well。

 so this is another way to write this problem when you are focused on as another tree。

It's not very friendly。Not， the notation becomes really heavy。

 It's already have for nature and by nature， and。Ifs another three， it becomes even。Harder。Well。

 but I I， I want to convey my idea the idea behind this formulation， which is not complicated。

 although the notation is complicated。 The idea is just you are making a decision here。

 taking account of the future。 when you are here， make a decision， taking account of the future。

But since we have a scenario3， we can point it by probabilities。The fact here。

You have some of the finite finitely many elements。For example， we can exchange these sounds。Prob is。

Strictly positive。 Well， we can multips this probability， for example， here， inside here。

 multiply this probability by the other one。And we are going to construct the probabilities of H and old。

 If you play exchanging here， the probabilities exchanging the。

 the sums we can play and arrive at this。Other formulation。For example， here。



![](img/d536f8e85cdef1b38381a776353b0898_53.png)

呃。We are Sammi。All the second stage costs validateated by the probabilityities weighted by the probabilitybaities。

Here， third stage， and so on。Constraint， the first stage constraint doesn't change the same thing。

 but the second stage constraint。For all the scenarios， okay， we are linked by the。

 the the decision you made at the first stage。 Okay， doesn't depend。Well。

 it doesn't matter where you are。 If it is node or that one。

 you are always depending on the decision you made here。But when you look at the third stage or more。

When you are arranging the constraints for this node， you have to take into account well， well。

Im am from this node or that one， so you have to make it explicit。

 So this is why we use this A here to see the ancestor is the father node。So when you are going。

 if you code。U。I script to solve this problem。You have to be very careful。

The way you construct the constraints。 if you link different nodes with different with other children。

 children nodes， you。Your formulation may not represent the problem you， you are willing to solve。

But， well， this is a way to solve the problem。 It's called equivalent deterministic。

Is a linear problem problem。So it's not easy to solve。

 Perhaps it's going to be a bit complicated for you to， to write down the constraints。Partter。

Once you have the problem mounted， solving is not a big deal。If the dimension is not so that high。

 large。嗯。I want to give you an example。

![](img/d536f8e85cdef1b38381a776353b0898_55.png)

Suppose our。Planning horizon is 12。

![](img/d536f8e85cdef1b38381a776353b0898_57.png)

And for each node of the three。Each node has four children。Oh this is the case。For this。Proruin mode。

We have four。Children and here。Again，4。And so on。Up  to T equal  to12。

So the total of scenarios is this number for more than 4 million scenarios。 So you have a。



![](img/d536f8e85cdef1b38381a776353b0898_59.png)

I really。Big three。And I'll suppose that for each and old。The decision variable。Has this dimension。

So the total， the， the number of variables of this problem。It is really， it's huge。So， we cannot。

We cannot mount this problem in a computer。 Its probably we are going to have problems of memory。

You cannot。Gather all the information to construct the model， not even to solve。

So this is really difficulty。 So the， the equivalent deter。

 it works if you are dealing with a small scenario tree and the dimension of your problem。

 it's reasonable， not so that big。So it works， but for a small problem。

But you know that to represent well thetochastic process， we need to have large amount of scenarios。

And。In order to solve。 So you need to solve larger problems。And for that， we need to。

Use some decomposition techniques。 It's what we are going to see now。



![](img/d536f8e85cdef1b38381a776353b0898_61.png)

呃。Okay， so that was an alternative to solve the Mo stage or Ca linear air problem problem by the equivalent entertainmentist。

 It's simple， however， not so efficient。 The other one。



![](img/d536f8e85cdef1b38381a776353b0898_63.png)

Is by the next of the composition that we are going to start to see now。Well。

 we start from this dynamic program formulation。 At this stage T， we have this cost to go function。



![](img/d536f8e85cdef1b38381a776353b0898_65.png)

The other stage， the cost to go function is written in this form。



![](img/d536f8e85cdef1b38381a776353b0898_67.png)

Well。Here we are taking account the expectation of the future con conditional expectation。

 because we are focused on the children nodes for this given node， a item。Well， here I'm saying。

 all the decision of the X I'm passing。I have to， to be careful which you won， which is the。



![](img/d536f8e85cdef1b38381a776353b0898_69.png)

Ancestor node。And。At the end， this is the problem we want to solve。Well。



![](img/d536f8e85cdef1b38381a776353b0898_71.png)

It's not easy to solve with this formulation， because the functions。Are implicitly defined。

 So when you are optimizing here for a given x1， you have to come here and solve。A problem that for。

 for each given x2， you have another。Function， future function。 And it's requisive。

How can we do that， How can we solve this a problem？ We are going to solve by approximating。

They cost to go functions。By cutting plane， like we， we did in two stage。呃。Case， two stage setting。

So instead of solving， considering the cost to go function。

 we are going to consider approximation for those functions， we know that they are convex。

They are polyhedro。 We're going to discuss this next。 later on。 They are polyhedro。And， well。

The idea。If you have a convex polyhedral function。

![](img/d536f8e85cdef1b38381a776353b0898_73.png)

At each tradition， what we are going to do is to approximate this function。By some cuts。So。

 for example， you have this cut。It cuts， and。This gives。Sort of approximation。

The maximum of those cuts。 Of course， if you look at this drawing。

 it's not a very good approximation。 You have a gap。But the idea is， iterly。

 we are going to construct more cuts， and we approximate this function。So， we you。

Use many cards to represent this this function。 Eventually。

 you may be dealing with the exact function in a neighborhood that is interest to us。

 the neighborhood near to the solution， for example。

I don't care if I don't approximate that function， the costs toable function。 In fact。

 the requires function in this part。Here。So I'm not interested in approximating this function there。

 I'm just interested in near to the， the solution the mean， yes。Okay， the question is， well。

 although we construct some cuts for the function， sometimes we want to evaluate our policy in another sample。

 And we， when we are using another sample， we don't not necessarily have this polyheedral function。

 We can have something different。 I don't know。Something like that。

 And this approximation is not a very good approximation for the other one。Okay。So when you， you。

 this is the strategies out of sample simulation。 you make a policy using scenario 3。

 And once you have a policy， you have all the approximation。

 you generate another sample and you are evaluate your policy。EWell。The policy are going to。

 you are going to evaluate。 The decision is not going not necessarily。

 will not be necessarily the best decision for this new sample， for this new function。 However。

 it gives an indicative if your decision is good or not。 Well。

 if you construct out of sample of simulation and the cost of that out of sample is something statistically similar to the what you obtain using this mouse sample。

 you can say that it's good that your policy was good。 But the idea is。

 if you can also using out of sample and improved construct new cuts。Great， but the fact is。

 in general。Use out of sample many scenarios， and you just do it for evaluating your policy。

 And you don't construct more cuts there， Although you are allowed to do if you want。一。全。Well。

 but when， when you are trying to solve this problem or approximate a function。

 They cost the go function， the requires function。Yeah， it's a neighborhood。 We。

 we don't have we cannot ensure that we are going to represent represent the function in this part。

 We just representing the part near to the option。And we cannot ensuresure。In fact， there。Well。

So let's make this idea more precise。Let me see what I have here。Okay。Here I'm working with nodes。

And I'm using here instead of the the records function。U。An approximation。And this is the。

The maximumim。Of the cuts， in fact， is approximation of that function。 requires function。 So in blue。



![](img/d536f8e85cdef1b38381a776353b0898_75.png)

Here， we have。And。Requires function。In yellow。This V。It's not the yellow。We have the approximation。

At that。Itteration。And the idea is that iteratively。

 we are going to improve this approximation to eventually coincide with this function。

 at least here in the part that interests to us。Well。In fact。This cutting plane approximation。

Accillation tea。That will depend on the decision。The argument。That you want to evaluate。

Here to Houston。In fact， this is the maximum。Of linearization， Of cuts。The cuts。

That we have constructed so far。Up to iteration K。As iteration K of the algorithm。

 you have a set of iterations， the previous iterations， you have a set of。Cas。

You can call here alpha T。Plus。Be20。X， T-1。And。Well， of course， here depend。On the Italian counter。

So， this represents。This idea， you take the maxing。Of cuts。So， for example， here。

This can be constructed by a。好烦。Jing。G。对。That's1。And ideas just take the maximum of those cuts。

But how we can construct。Those cuts。That's what I're going to， to see。We are going to see this now。

Well， we already know how to construct this at last stage， right。Because it's the same what you。

 you did when you solve the two stage to cast air program problems。So at last stage。

 there is no secret。Just stick。So we go the end of the re function。And you end up with the cuts。

You need。LetMe see from where I should start。Okay。So the problem we want to solve is this。

At iteration， this iteration。That one in red。Well， we can just make a trick here。Oh。

Our decision variable is x1。But you can use。For example， R 2。And get。This function。And just write。耳图。

Okay。And then we can use the cuts， and we represent this function by a set of constraints in equality。

 Okay， that， that's the， the idea。So， each。Cutip plane approximation。At stage T。



![](img/d536f8e85cdef1b38381a776353b0898_77.png)

Iteration K。It's going to be。The expectation with respect to the past。手机。Should you steep -1。

So I prefer to call here。Plus 1， plus one。Di。Plus，1。Here will be our approximation。Cos。

There is something wrong。There's no one here。In fact， here there is one。This if。T， equal2，2，3。听满算。

And， of course， the last stage， we don't have a future cost。Is the end of the world。

don't care about it。 Its 0。S7。一空。Cpt tea。And， well。

Who is this approximation is exactly what's written here。 So I'm not going to write it down。Yeah。

So you call this category approximation。

![](img/d536f8e85cdef1b38381a776353b0898_79.png)

Well， let's define those cuts。To construct a formulation for this Cat planer model。

We start from the last stage。Res function， the exact。Recorres function， calligraphal。

Depends on the decision， s。Xi。And giving our assumptions is the minimum。Deion next。Well。Sorry， no。

 that's not a calligraph。 This is， in fact。This one， the cost to go function。てかります。

This is what we have。Well。What we know from this definition。We know that if you。

 we take the negative of these metrics。Multiplily by a lagrian multiplier。 O， get this matrix。

 We have the lagrian multiplier。You call it。Be team。And we know that。These vectors。

 this vector belongs to the subish financial。Of this function。Okay。

So we saw this in proposition last， last class。And also， this is the same thing。

 then it's to stage stochastic。、プます。So if it take， I， I'm going to call。Ghii。

Equal to the conditional expectation。With respect to this past。-1 sorry。Off。

So I'm considering I'm based on a scenario3。This is expectation。

Belongs to the sub differential of these。Cliographical function here。Okay。We know this。

 just applying。The expectation。Okay， the expectation of this。This function， This is one。

 that requires function。Well， we know。That the records function is convex。Okay。And it's convex。

 and we know a super super gradient for it。 Just solve this problem。 get a dualom La multiplier。

 dual variable。We define this vector， take the expectation。

 We have a sub differential or sub gradient for this function。Okay， the function is convex。

If the function is convex。We take this calligraphal T。Q。Stage T。Depending on a given decision。

Anyones。This is history？Disfunction is convex， we know。Using the super gradient inequality。

This is greater or equal to this the same function， but evaluate at this point x。

The same history here。Plus。That's the vector。T suppose。This point。Minus。This is subent inequality。

Okay。No。I want like you to pay attention on this LEP。If we use the du of formulation。

The optimal value of this problem。Using the dual formulation。Is equal to this this value here。Is。

The expectation。With respect to the past。off。The optimal value I can， write。S。Bty。

Using the optimal decision。To do our optimal decision。It's clear。It's clear that。

This value is equal to this one。Fhilip。Okay。No。What I did， just that。Now。

 we are going to use the definition of this subgraient。C this one。So， plus， the expectation。Minus B。

suppose。And all of this。Multiply。Okay。Well。Now see， we have a expectation here， you have B， T， X， T。

 minus1。P气。We have the expectation。B T B T， you have x again， so we can cancel。

And we should continue。If you container。Oh。To be the expectation。Okay。Plus。What's his remaining？Is。

Mines。B T trans。T suppose。Pretty。I think慢。And。I'll call this termem。alphapha T。

And suppose we are at iteration。Okay， for example。So if I'm an iteration K。

 I have to give names here。Kk。Can you just sure。That's it。Andand here。UBK。And call this alpha K plus。

买搭。Okay。So this is one cut approximating。The function。 So the idea。What we have done here。

You have this。S나 3。Here we have a function。Records function from this node on。And we constructed。

A cut。For it。 So you have a function that is。Singing。Like that， polyhedro convex， we just added。

For example。I can't。Thank you。But we have to do this for。Each history。Oops， os， there is。

 I think there is a notation here。 I index it it's not okay。It it's a missing-1。Yeah。这撕必。

With your notation。Well。But this is for a given point。 You are in this history。 You construct a cut。

 but here don have another function requires function。 just take into account this future。

 You have to construct another cut here。 This for one iteration。

And how is going to be the cut for this node in this case， is going to be the same formula here。No。

 a bit different。 So let's， let me show how it's going to be。One thing that。'Like to highlight。

Is the fact you have shown。The records function。Deepless swan。-1。Is。Bigger than one cut。

 But for any cut you construct so you can take the maximum here。The maximum of all the cuts。

For all iterations。You take the maximum， this is what we call。The Cat model。This point。Well。

Aitration K for allitations at the last stage here。

The cutine approximation always approximate from below the function。And this is。A property。

Thanks to the convex of the function。Well。Let's move to a previous stage and let's see how we can compute。

てかs。The idea is the same。However， you have more constraints to deal with。Well。4 t equal to，2，3。

Capital T-1。The cost to go function at stage。T。一光。Here不自己。This case。I's not a requires function， but。



![](img/d536f8e85cdef1b38381a776353b0898_81.png)

The courseible function。Well。This is。The minimum。Here， we use the cut plane approximation。D plus one。

Xt。And history。Subject to our constraints。Okay， I just wrote what's written there。Or the idea。

Is the same。We can move this cuttingillium function put as a constraint since we add a new variable here。

ART。I T plus one because I am going to replace this caterpillar model at the stage T plus one。Okay。

Same， same thing。Well。We now use。You know， we know that this is the maximum of some cuts。

We can just say。This is equivalent。哎。S。Use these cuts here。Jing。Yi。嗯。Xt。

And this for all J smaller than K。说。So constraint。 This， this is one constraint。

 but you can write as a set of constraints。Okay， just using the definition of this cutting model。

 you can think that we are at this stage。T equal equal Tme1。If you are， we are at this stage。

 So we know this cut。Could you have just。Computer to the here， okay。We can just remove this。And this。

那。another way to write the same approximation for the conable function。Well， from here。



![](img/d536f8e85cdef1b38381a776353b0898_83.png)

This function is convex in x。Well， once again， using the same theory。You can show that， minus。

If you take our optus duo solution， condition which apply for this problem。We know。

That at this point， I'm not using okay。This belongs to this， with financial。Okay。The same theory。嗯。

Because I'll see the only constraint that depends on x T minus-1 is this one。

So these mattress come here。Well。The function is convex。 What are going to do is the same thing。

 We are going to use the。Sub great empty。Inequality。Okay， I'm going to release this。啊，没了。

For writing the sugar quality。We will need to use the。The world formulation of that LP。

Let's do the fog。Here。We have。A all variable associate。Here， we have。Another dual variable。HeresD。

De plus1， I think。Okay， associated with this constraint。How is the dual formulation of this LP。

That LEP is the same then。The maximum。Bzi。B。60。-1。Times。接。Considering this。I know。



![](img/d536f8e85cdef1b38381a776353b0898_85.png)

孩子。I don't tell。Well， we can just。Comput it in somewhere here。Well， what I'm going to do now。

 I want to write do our formulation of this LP。 Okay， I don't know it by heart， so。

I'm going to do a little bit of math。We can， if you write the regression of that LEP。Good depend T。

Xt。See。This one。

![](img/d536f8e85cdef1b38381a776353b0898_87.png)

This is。6。And here you be。The sum。This she。と。Multiply。O。Plus1 J。X T。Minus。Dster。

This is a la of function。I know that this whole。Should be。No。

 negative because it's related to this inequality。I want the in with as app。 sorry。

 there is a R here。Depending also in that's the primmo variable。If you take the instrument。

 with respect to。X T。啊第。I like this to be。When this will happen。So you need to gather。

All their variables depend on x。司机。M， minus， I did。你知。Whats this some。This part depends on also on X。

Oops。I'm just putting。The terms that depend on X T in this part， together。And if I take the in。

 I want the lag to be greater than a minus infinity。

So since we have the constraint that this X T is non negative。 This part should be non negative2。

This implies。City， bigger than。ちゃっと。This is one constraint。 Okay， so here I have one constraint。

That is。Zi。J， this should be。Less or equal to。City。

And if you arrange the terms here to put in evidence r plus 1。

 we have this sum multiplying these R and oops， heres r plus1。



![](img/d536f8e85cdef1b38381a776353b0898_89.png)

And this one is alone。And if you take the E with R， you want this lag to be infinite， this sum。

Should be one why。If you put together the terms。What's here， youll be。This sun。Okay。

Just putting together。And if you take the in respect to RRT。You want to be。Certainly， okay。

 you don't want to be at the mine。 So this term should be 0。It means。Should be one。

 We know that it is no negative。For j。 Okay， this is the constraint。 but remain what's left。

 If you arrange things here， what's left。This song。Jo。That is something。Else。Let me see。

It's just that。And this is the duall。If I didn't make any。Rrong。Ccus dis isn't。Okay。

 so giving optimal this optimal solutions for this LP。This approximation， the records。She's this one。

We can write it。S。B7。Times the optimum。Okay， if you take the optimal solutions。

 So the optum value is is objective function。 And now when we use。The super gradient inequality。

We can manage to compute。The cuts。Well， take this function。Stage  T。But。42。Another point。

This is the historyster。The f is convex。Use Xt here。Plus。This sub gradient。She this one。Mins。Okay。

 we can cancel something。First。We use this definition。And we can get rid of。X。T-1。So what's left is。

Pt。Transpo Bt。Pity sorry。But plus， this sum。And here。Just remain。ですが。

But this for just one costta go function， we need to take the conditional expectation。

 If you take the conditional expectation， I'm going， I'm not going to show the。The， the math。

 but it easy just to apply the， the conditional expectation。This is the assumption we are using。

We are going to end up。With this definition for the the cuts。This one we showed。Now， just apply。

The conditional expectation here。If you apply to conditional expectation。We are going to have。那3的。

Expectation。We are going to arrive in this definition。If you are an installation key。

So the cut planning model is the maximum of those cuts。 So this is the rule to comp compute the cuts。

 Well， we are now in position to show the algorithm。 but， well， I'm run out of time。

And I think a cloud would like to give you some。Some information or later。 How。

 how much time do you need， Collia。Okay， so I can continue a bit。 have more 10 minutes。Well。The de。

 the the nest decomposition， once we know how to compute the cards。It works。 It has two main steps。

A forward and a backward。The forward is step。Makes decision。

Take into account only approximation for the future。 approximation of the requires function。

So the idea is you， you perform a forward step generating policies， which are feasible。

 not necessarily， not not necessarily optimal policies。 You do a forward step。

And for each stage of the three。Each node of the three。Let's think of the first it。So， it's like。

We make a decision here without taking into account the future。

 We are muted with respect to the future。 You make a decision。And this decision， x1。

 you send to this node and also to this node。 When we are here。

 we make another decision without taking account the future。 So make another decision here。

And you sent。To the other notes， when you are alive here， you have a feasible policy。For each stage。

 each node you are feasible， but that。That point， that policy is not necessarily optimal。

 So when you arrive with a feasible policy at the end， you have upper bound for the， for the optimum。

Optune value， you call this upper bond by Zbar。And when we are here， well， for example， I spend。

Some money here。 Oh my money went up the end。 I don't have any money thinking about the planning of my。

 my month。 with respect to my salary。 I'm at the end without money。 Well。

 that was not a good perhaps ineb。 That was not a good decision。

 So I should take care in the previous days。 I， I should not spend so much money。

 I have to bring this information。To this node。 and this information comes as a cut， like we。

We know how to compute now saying， well， the， the， this is not the end of the world。

 You have a future。 You should take into account this future。 How with this cut。 So I have。

 because I made a decision。 I construct a cut and I construct a cut here， too。

 This is the backward pass。So the forward， we just make decisions。The backward。

 we are going to construct approximations for the future。 Like， be aware。

 it's not the end of the world。 You have to save some money。For example。

And we are going to construct approximations for our requires function when you come here。Well。

We are minimizing。 Let me show you。The first stage。We are minimizing。Solving this LP。

This is the cut pain approximation。 It's a low approximation for the requires function。

 So this value。Is a lower bound for the opt value。Okay， so when you go forward。

 you we have upper bound。When you come。Backwards， you have。This is a lower bound。And here。

Is the upper bound。And the method stops。 algorithm algorithmgri stops。

When this difference is less than a tolerance you give。And it's like it's， it works like that。 Well。

 since I have added some cuts， when I make an other decision here， I don't see very well the future。

 but there is some information saying， keep a bit of money。 Don't spend everything。

So I will make another decision here taking account this information I get。 I got。And。

The algorithm goes forward， backward， forward and backward。 and each generation will go forward。

You are going to have。You are going。 you may decrease this upper bond every time you come backwards。

 you are， you may increase。This lower bound and upyntically， you are going to close this gap。 Well。

 in fact， close this gap infinite finitely many steps。 You are going to prove this， but。Well。

 next class。Well， here I have just the description I've just done here in the blackboard。

So you make a decision to this node， send a decision for the。The children notes。Here again。

Make another decision， evaluateval for each and one of the nodes。 And when you evaluate。

 you are the last stage， you construct a cut。So you have some information here。

 But then you solve this node again， using that information。And also， that one。

 you make the average like you， you use here， the conditional expectation。You have a cut for this。

Point。And we continue like that。U。The algorithm。Well， I'm just assuming complete。

Helative complete records。So in sense that this LP is feasible for each decision I make for each realization of the future。

 This is only for assumption。 We can also work with feasibility cuts。 Okay， just only for simplicity。

AndThe stay， the step 0。到。We don't have。Any cut the first step。

 So you may define this variable equal to 0。 It's like you are making a meal decision。

 You're not seeing the future， any approximation of the future。So this is the step 0。

 and you go forward。You have an upper bond。And then。Sorry， here's the forward step。

 and here are just definitions。Misalization。呃。You step backward， you have all this， this policy。Then。

 we're going to compute。The cuts。And we will come back each node of the three computing cuts up to the roin node。

 When you are the roin node， we solve that LP， you have a under approximation。

 a lower approximation for the optimum。And you have another point。If the difference。

 the gap is is small enough， you stop otherwise the continue here。To finalize。

I have here an illustration。

![](img/d536f8e85cdef1b38381a776353b0898_91.png)

So suppose you have a records function at the each。Each stage。And in fact。

 we have a requires function for each node。When you have a records function for each stage is when you are assuming stage wise independence。

 it， which is not the case。 This algorithm is general enough that can can consider this more general case。

 So one records function for each node node。

![](img/d536f8e85cdef1b38381a776353b0898_93.png)

Well。So what we do， we approximate the。The dynamic equations by cutplan models。

So the first iteration， we don't have any information。So you don't have cuts。 For example。

 you can use a lower bound if you have a lower bound。And we make our forward a step。

Which is make a decision in this stage， another decision there and so on。

You just go doing meal decisions。 You're not seeing in the future， but okay。

But then you arrive at the last station。 So， well， that was not a good decision。 I should be careful。

 And then you compute a cut。That the this stage approximate the function from all the stage。

 App F the cuts approximate the function from below。In the last stage， indeed， this is a tangent cut。

And then you move backward。For that point。Evaluate the function。 Con a new cut。Cuan。

To the first stage。Well， when you come here， you have a lower bound。And we will repeat the forwards。

 making other decisions， see。In blue。At the end of stage， come back。Adding cuts。

And this goes iteratively。Youre going to approximate this function in the region that we。

We want to approximate。Well， the convergence of this algorithm， it's quite easy。

 but we are going to see this next class。 Do you have questions， questions。



![](img/d536f8e85cdef1b38381a776353b0898_95.png)

Okay so。