# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p25 -25-Basic Course on Stochastic Programming - Class 25.zh_en -BV1tH92YXEnd_p25-

Okay， good afternoon。 Welcome to the bus lecture number 24。呃。So today。

 we are going to start some specialized optimization methods for solving convex。

 but non smooth convex and non smooth opt optimization problems。

 We are going to focus on bundle methods。 and， of course， our aim is to attack。Stto ask problems。

So we， we have three lesson，3，3 classes left。So， today。



![](img/dbd7c01a5fe5abd176206d8384e47628_1.png)

啊，O。Today， we are going to deal with。Proox small bundle of math。So， this is。The class of today。

Next Tuesday， we are going to， to start。Another class of a bundle methods。And。On Thursday。

 we are going to start inex。Bundle methods。 And we are going to。

 to consider exact evaluations for the function at sub gradientient。

And we are going to consider the two methods。Both the proximal and the level  one。 Well， the。

 the problem we are going to deal with is the problem of minimising。A function。Over convex function。

Over。convex set。Well， we know that for example， in two stage stochastic programs， we have a function。

 Well， that's consider here。To stage programs。D function。Is。The cost of the first stage decision。

Plus。The expected value。Of。Second stage decisions。Costs， future costs。Well， we here again。

 this is the expected value， but we， we can consider， for example， a risk measure。

 Well So the fact is。You are going to assume this function。啊啊。To be convex。

We know that for the two stage。Programs， this function is not defishable。But convex our。

 our feasible set is a polyheum。 for， for example， or the entire。RN。嗯。And also， I didn't say here。

 but just consider functions。From。OrM。To玩。啊。Well。

![](img/dbd7c01a5fe5abd176206d8384e47628_3.png)

So this is exactly what I wrote there。Our feasible set can be can be a polyhedrum can be R N can be other things。

 The only assumption we require on x is convexity。And x should be easy set， for example。

 minimizing a quadraact function or minimizing a linear function over this set should be easy。

This is our requirement。呃。This general formulation covers， for example。

 to stagetoastic program problems。 what I have just。Written and also， the mood stage。

Programs when we， we deal， when we attack the， the problem by the du of formulation。

Just recalling the those two items。So in two stage linear program problem。Well， we。

 we need to solve this large LP。Well， here once again。

 consider expected value could be a risk measure。 no problem。嗯。Since okay。

 we can rewrite that problem。In this formulation。啊。

Where Q of x and the Xs is the optim value of the second stage linear program。Well， we are。

 we are already ready。We have already studied。 We know that this vector here is a sub gradientdient for the function。

That， that point。Well， in fact， what we have seen is。This expectation is a sub gradient。

For the records function， the expected value of this。 So。

 but since we are considering this function with this linear term， we we add， if。

 we add this linear vector， this vector here， we have a solid gradient for this function， well， P。

pi I is the dualo solution。 Oh no news here。If you consider。Andmo stage programs。Once again。

 on our formulation， the random parameters can be the cost。 the recordscourse matrix。

 these mattress A and the vector B， the demand can be。All of those ingredients or just some of them。

We， we stated we， we know how to reformulate this problem。 considering the non anipivity constraints。

 we can reformulate this problem。 We are going to have this linear constraint at the end。

 And if you do all lies， we end up。With the dual problem which is a maxim problem， however。

 change the signalo。You can consider a minimization problem。

This function depends on the dual variable， is the sum of d of I。And the of I is a linear program。

 considering all the stage from stage1 up to n for a given， given scenario。 I。

 So we split the problem into。呃。Capital N。Elys。We also know that。Once we give up you。

 we solve all the N。LP， we get the optimal solution here。 this optimal solution。Depends on the。

 the dual variable we， we give。 is here， depends on the scenarios。So， but once we saw for all LP。

 we have this big vector。And。This product is a sub gradientient for。嗯。This function。Is a solution。

 Yeah， theres a subgregating for function F。So the problem you are going to consider is this formulation。

 So you keep in mind that， oh， this is applicable for two stage and multi stage or more general for other kind of problems。

嗯。Both in two stage and multi stage setting。Function F is difficult to evaluate。Because we give her。

X or the the the remote stage setting do all variable U。We need to solve N。Sripro。

 which is written here。 You need to solve any optimization Serpro to evaluate the function and computer sub gradient。

But well， that's possible if n is not too large。It is possible。 And this procedure of given X。

Evaluating the function， as sub gradientdent， we call this an naacle。Or a black box。U。

In also above settings to stage or mood stage， function F is convex， but noise smooth。

 general linear。Pace ofwise linear。And well， you， you。

 you will now have the experience when you are dealing with the L shaped method and the project。

I'm sure youll know that most of the time to solve the problem is spent in the black box in the or。

Because you have to solve a sequence of LP。Well。ETherefore， this oracle is expensive。

 and you don't want to call it so many times。Therefore。

 subgraate methods or cutting plan methods are not so。So efficient for this context， because， well。

 both sub gradientient and mainly sub gradientient method requires so many oracle calls。

 You have to to have so many functional evaluations。 And well， you want to avoid this。

 We want to solve the problem， calling the oracle。As few as possible。

So we need more efficient methods。 And when I say here， the cuttyplan method， of course。

 the cutty plan method applied to the two stage setting is a shaped。 We want。

 we want something more efficient than all shaped。That's the goal。And。Here， here I'm just recalling。

Just remembering you， what is the cutplan method for solving a problem like this。

 X needs to be compact If you are using a cuttyplan method。So you are。

 you already know this algorithm。 just so I'm going to pass quickly。

 So we start with an initial point。 We call， we call the oracle to compute the function。

 a sub gradientient。With this， we can。Define this cutty plane。

Model is the maximum of all the linearizations。 So the first linearization， we have just one。

 the first generation will have just one linearization。Well。

 the next is obtain by minimizing this model。U。So for you are going to evaluate the function so you can compute the upper bound for the optimum value。

A lower bound is obtained when we solve this model， this problem， when you minimize this model。

And we stop when the upper and lower bond。This gap is， is small enough。Once you have this new point。

 you compute the， you call the or again and you， you enrich the model and the process repeats up to you find a small gap。

So， just illustration。

![](img/dbd7c01a5fe5abd176206d8384e47628_5.png)

We need a feasible set co a feasible set to be compact。 We start with an initial point。

 called the orac， have only one linearization。 So this is our model。

 minimizing this model over this feasible set， the next point。Youll be in the extreme。2。🤢。

This is important to see。🤢，That we are near to the solution for， I don't know。

 The solution is here there。 I don't know。 but we are near to the solution here。 We start near。

 however， the seconderation。Goose far away。

![](img/dbd7c01a5fe5abd176206d8384e47628_7.png)

So it doesn't matter how good is your initial point。 You cannot exploit this， these。



![](img/dbd7c01a5fe5abd176206d8384e47628_9.png)

Information to define the exit iter rate。 So this drawback and bundle maps try to overcome this drawback。

Okay， so once you have a new point， call the articleac again。A new linearization。 And now you have。

The maximum of the linearization is the model。 So the minimum of this model， it's here。

 So the next it date。Is defined like this。 And the method continuous。Up to find the。

The optimal solution。 I'm sorry， this I'm using all the figures。嗯。To ensure convergence for this。

 So the converg channels of this method is it's easy。 already， you have already done this。

But one assumption which is important to ensure con is you you have to keep in the model out the linearizations you compute。

You cannot， for example， at certain point。 For example， at this point， I have this linearertization。

 I will， I， I don't need this other lineartization here。 I can remove it。But well， in this。

 in this example， yeah， you can remove it and you still can converge。 But in a general context， No。

 if you delete a linearization， we cannot ensure that the method will converge。

 So this is important to have all the linearizations。 But what's the problem of keeping。

En reachinging the， the model at each iteration more， the problem is。Well。

 you call the de shape that you know， every linearization is a new constraint for your master problem。

And if you need， I don't know。5，5000 iterations in your method。 you have to have 5000 constraints。

If your problem is La is big， this can give you some， some problems in solving the master problems。

 some numerical problems。And also， every generation at each generationeration is more expensive than the previous one because your problem。

 your master problem is bigger。So。EIn some applications， this is a serious drawback。



![](img/dbd7c01a5fe5abd176206d8384e47628_11.png)

Okay， so here is just to say that retaation you add a new linearization。

 So you are increasing the constraints of your master problem。



![](img/dbd7c01a5fe5abd176206d8384e47628_13.png)

One thing here。In our。Project。So in the shape math， what our master problem was。

Minimizing the first stage cost。Plus， this arm。And we had okay。Fsible set。And constraints。Cuts。Right。

 something like that。嗯。Well。We can write this problem。Because therere， okay。To stage our function。

 is this one。

![](img/dbd7c01a5fe5abd176206d8384e47628_15.png)

嗯。But this master program。Is essentially this one。 Okay， there's no difference。

This is just more general because your function can be other things。Rather than the。

 the two stage 1 for the two stage model。 But it' the same thing。 you can just。



![](img/dbd7c01a5fe5abd176206d8384e47628_17.png)

Get this。This cost and we can sum here and we appear another C here because of the subgradd and it's a key on it。

So let's consider this a more general manner here， but you keep in mind that for the two stage setting。

 this master problem is exactly the same that that one。



![](img/dbd7c01a5fe5abd176206d8384e47628_19.png)

Well。What are the advantage and disadvantage of the cut pen method。



![](img/dbd7c01a5fe5abd176206d8384e47628_21.png)

Well， it computes。It needs to compute。On a single subgraient peritation。

There are some methods that you need to know the， the， the whole sub subdi。 So in this case。

 one sub peritation， that's good。 That's a positive point。

 This is also the same thing for the subrogent method。EIt's easy to quote。Reasonable。Is it？呃。

It has a reliable stopping test。 just to just check the upper and lower bound。 but see easy。

 It's cheap。It's good。 Well， disadvantage advantage。It's not a decent method。

Because some iteration along the iterations， you can increase the function。 Remember here。

We start here。At this point， and our next today has a value a cost much higher。So， it's not desent。

So in general， it's。

![](img/dbd7c01a5fe5abd176206d8384e47628_23.png)

It's better to have。A method that a decent method， De method。It's instabletable。Well。

You can see this if you get your L shaped method and you decrease the tolerance。

 you are going to see that you are going to generate so many variations and a few improvements。

That's， that's a drawback。 It's stable。 And also because， well。

 you need a compact set and to minimize a model。EThere are problems in which later date。

We jump inside this， this feasible set。 that's not good。 and it has a low convergence。

Requires the feasible set to be compact。 Otherwise， it doesn't work。

Doesn't exploit good starting points， as I explained before。And so。

 so the problem becomes heavier and heavier because you are adding more linearizations。So。

 you want to。To overcome these drawbacks。This is the， the。

 the aim of a bundle method that we are going to start today。That is also for the two stage setting。

 a method called the regularized the composition proposed by Hoinski in 1986。

That's overcome this drawback。Overcomes these difficulties。

But it turns out that this method is just a particular case of bundle method。 It's a different name。

 but essentially is' a particular case， just a simplification。

And bundle methods were developed in 70s by Claud Marhal。呃。So。



![](img/dbd7c01a5fe5abd176206d8384e47628_25.png)

So whats the the bundle methods or bundle methods in Portuguese and method fasciious。

Why this name bundle， Because you have a bundle of linearizations to， to represent your model。

 a bundle of linearizations。 and this bundle， you can keep it bounded。 You don't need to。

 to have all the linearizations along with itative process。 Sometimes you can just forget something。

 alleviate your your master program and continue。Because we can allow we allow to， to， delete。

 to discard some linearizations。 I'm going to call the cut planeium the model by a different name。

 This is the model。 There is a M。Could be。This model。Aitration K could be， for example。

 the cut planning model that we are interested。 we are used to could be the fact is。

 we have more flexibility to in define the the model， approximating the function。 Okay。

 this can be just fuel linear yourization， for example。 So I， I'm giving a different name for it。

And also， we always require that this model approximate the function from below。 functions convex。

 We are approximating from below。So this is the first ingredient。



![](img/dbd7c01a5fe5abd176206d8384e47628_27.png)

Another one is a stability center。And I call this point with a hat X hat。

 Why this point is the best point we know along the iterative process。

 So whenever you get a point that gives you a lower value for the function。

 you keep that point and call it X hat。

![](img/dbd7c01a5fe5abd176206d8384e47628_29.png)

So it's the best one， you know， the best candidate for the the solution， okay。

And then other ingredient is a parameter。 and we have two different kind of parameters。

 A T or this F level。 And we have to update those parameters at every iteration。And the fact is。

It's not difficult to update these parameters。 And for we are going to see how to do that。And well。

Either you consider a T。Or F level。 This will depend on the， the。

 the the variant of method you are going to consider。呃。Dooming。

Bundle methods are the proximal and the level one。That is another one。

 that doubly stabilizes the bundle metal that combines above。 and boom， there are more methods。

 Let's consider。This two， the classical ones。Here for the proximal bundle method。

 we have the model here in the objective function。And we add this quadratic term， that is。So。

 it says that we are going to define a new point。 X K plus  one。

 but we want this point not to be far away from our best non point。 Okay。

 you are just keeping is a kind of stabilization。 and this T K is。

 is defining how far you want to be。 on here you want to be。From this。Best point you have， you know。

And。So if you， if you remove this quadtic term。We have a cutipplanar mode method。

 And if this model is the cutipplanar model， you remove this。 You have the cuttyplane method。Well。

Ctting payment method， we need to solve LP。 The master program is a LP。

 Here is a Q P quadratic program。The， the other variant is takes this model。

 the the model and moves to the constraint， so。It's here we are defined in exitate。

In the level set of the model， here's the model。 This is the level set of the model。

 This is the reason level bundle methods。This one was the first Boma was the proxima one proposed in 70s。

 And this one was prop this proposed by Claud de Marhal。As a French mathematician。

 And this one was proposed in 1995 by Cla de March Naidovov。So two Russian guys and one French。Well。

 so today， today， we' are going to focus on this method。 Okay， next class， we start this one。嗯。

So you may ask which one is better。But我I。There's not a clear answer for that。

But there are some kind of problems， for example， when this is。Our N。This method is likely to。

 to work better in practice when you have a compact set。This one seems to work better。

 but it's not clear。 Depend on your problem。And， in fact， they are related。

We are going to see to the next class that there is a relation between these two master problems。嗯。

So before presenting the algorithm， let， let me let， let's， let's see how it works。 I。

 we have the same function。 PC Y is linear。

![](img/dbd7c01a5fe5abd176206d8384e47628_31.png)

We start with a point called the oracle。 have the linearization。 So far so good， no problem。

 no difference。 nose， we don't need the F the feasible set to be compact， to be bounded。呃。

Let's consider this case。 And then our model is just a cut model， just to， too easy。



![](img/dbd7c01a5fe5abd176206d8384e47628_33.png)

The illustration。

![](img/dbd7c01a5fe5abd176206d8384e47628_35.png)

So the next hit today is obtaineded by minimizing the model。

 plus this quadratic term centralized in your best candidate。 So we have just an initial point。

 The best candidate we know is this point。So we are going to define the next one， but you don't。

 We don't want to be far away from this point。응。And idea is that， well， when we have。



![](img/dbd7c01a5fe5abd176206d8384e47628_37.png)

Your model。Plus， the quadrara theorem， you have this blue curve。

So we want to minimize this blue curve。And well， if if you want to be neither to x 1。



![](img/dbd7c01a5fe5abd176206d8384e47628_39.png)

You should。Decrease T。Then this curve would come near。So。

The form of this curve is defined by this parametermeter。Yes。嗯。Okay。

 the question was in the dark question was a comment。 In fact， well。

 it seems that it's better to have this regular regularization when you have enough linearizations。

 because if you start far away from the solution and if you， you keep。

Your next rate near to the A bad point。 It's like you are going to be slow to conversion。

 Is that the cloud， yeah。Yes， you are， yeah， you are right， but you depend on your rule。

 So this is what important to have a rule to define this parameter because you can't be far away from the solution set。

 But if you have a large T， you can。Go near to that region， easily faster。

But even though you don't know a good rule for this。😊，Eventually。

 this organization proves to be faster。It's， it's better than the， the cut planning method method。

 because， well。The cut panelium model can jump from part to another。 You don't have any control。

 Here， we have some control。 And this improves the method in practice。

 So you are going to see in the third project。 I mean， the second project。Final project。

 we are going to see that it， it helps。Okay。Once you minimize this model。

That amounts to solving this Q P。We define the nextiter rate。

 So apologize here because I'm using different notation， this Z。Should be X。

 And this X should be X hat。 So I'm sorry， this is all。All the figures。But I think I will convey my。

 my idea here， the， the idea of the method。Okay， we have the next point at this filehi of one is just this。

 this function， okay。Define the next， define the next iter rate。



![](img/dbd7c01a5fe5abd176206d8384e47628_41.png)

We call the Oracle。Computer linearization， update the model。But see。

The value of the function at this point， first of all。

See that we don't need this feasible set to be compact。 We replace this capacity。By this collector。

 it helps us in this sense。Another thing。This is the value of the function here。

It's higher than the one we know。So it means that this point is not a good candidate， at least。

It is worse than this one。 So we keep this one as the center as the X height。

We keep it as the center of the， the quadra term。

![](img/dbd7c01a5fe5abd176206d8384e47628_43.png)

And this point it' useful to update the model on for。So since we keep this as the stability center。

 our quadraact term is centralized in this point。We want to keep neither to the best point we know。

But we updatedd the model。 This curve is different。And do we minimize again。And obtain。Next point。



![](img/dbd7c01a5fe5abd176206d8384e47628_45.png)

In this case， the right of the function。Is better。 We decrease it。If you decrease it， well。

 we change this point here by the， the best one。And it amounts to move。



![](img/dbd7c01a5fe5abd176206d8384e47628_47.png)

And this term to that one。And， of course， there is a rule to define。

 to change the stability center when you have improvement of the function。

 But sometimes you have a small improvement。 and this is not enough。

 You have to have a good improvement。 And this will be clear in the next slides。Okay。

 the math functions is like that。And for the same problem， the other， the cut method。

Needed the six iteration is this one， only4。

![](img/dbd7c01a5fe5abd176206d8384e47628_49.png)

呃。So advantage and disadvantage。So as in the cut method， we require only one subgient peritation。

It has a ease and reliable stopping test。 It's not explained it here。 didn't explain yet。

 I will explain。 But you are going to see that it， it's reliable and it's not difficult to compute computationly。

This method is stable， and this is due to the quadratic term。It is a descent。Methods， you may ask。

 well， is that true。Since I start this point and then the other point had a higher value。

For the function。Well， it's descent， descent in the0， in the dis cent for the best points here。

 So if you consider x 1。So， the other point was。this， I don't know。 Now this。 and then that one。

 the function decrease only for those X that， in fact， should be X hot。

So we have a sequence of points in which the function decrease。It exploits。

 it exploits good quality initial points。 Well， if you given a good point， you tune your parameter T。

Small enough。Our put3 T here is small enough。

![](img/dbd7c01a5fe5abd176206d8384e47628_51.png)

To find an exiter age near to the point， you know， that's a good candidate。呃。



![](img/dbd7c01a5fe5abd176206d8384e47628_53.png)

Well， so the problem， defined find X K plus one can be kept small。 although it's a quad problem， you。

 you， you may， you may say， but Q Ps are more difficult to solve to be solved than LP。 That's true。

 However， this Q P program。 This Q P problem is small。 You can keep it small because you can。

You have control on the number of constraints， and you don't have control the number of constraints for the。

 the master problem。Of c method。Well。Good advantage advantages。 But we have。When a disadvantage。

 which is the convergence analysis is more involving。 depending depending the method it easy here。

 it's more evolving。 But， in fact， this is not a drawback since we are going to study this today and we are going to。

 to be convinced， I hope。That the method works。And once you know that。

 this is not a drawback anymore。It has one parameter more to， to be tune。 That is T K。

 the proxy parameter。啊。Let's see。How do you define the model。Well。

 we define a model in this expression。 So here we are considering index set B， K is the bundle。

 the bundle of information。And。If you take the the usual caplanium model， it amounts to having。B， K。

 like all the linearization， all its。So if you have some things。This is true。

If you have that bundle of information。Youqu the index for of all your iterations。

But we want to consider more economical。Model。Because， well， you know。



![](img/dbd7c01a5fe5abd176206d8384e47628_55.png)

That fewer it index。Here。In this here， we have the master problem is easier to solve because you have less constraints。

嗯。Okay， this we know we solve this Q P to define the next iter。And how we can。Write this model。 Well。

 once again， this， this is a master problem。Once again， we can， we， we remove this。

 we write this model additional variable， and we move the neizations。So the constraints。嗯。Again。

If you don't have this quadratic term。And B K is the set of all the its。 This is the master program。

 the master problem of the Catplan method。And。The interesting thing。If x is the is R N。We can。

 we may solve this problem by its dual and its dual has a nice structure。

 and we can exploit some structure and design specialized cut planee specialized methods。

 QP methods to solve this problem。 and this was done by Anton Fran is some years ago。

 Christoph Kel as well。 And we have a good QP solvers to solve this QP。

 but you can also use your favorite QP solver tool to solve。 It's not a problem in this way。

 Just saying that you have more efficient manners to deal with that。



![](img/dbd7c01a5fe5abd176206d8384e47628_57.png)

Math problem。Well。Here comes。Our decision rule our， our rule to define。St its centers。

And every time we define a stability center， we change the stability center， actually。

We call this a serious step because you make some improvement。 Let me come back here。For example。

 in this case。

![](img/dbd7c01a5fe5abd176206d8384e47628_59.png)

This value of the function is higher than the previous one。 We say that this is8。

 this step to generate this point is an is no is a old step。

 because while it's no instance that we don't have improvement of the function。 However。

 we can use this information to construct to to enrich the model。

And when we change the stability center。This step is called serious， because we had improvement。

And how we change。

![](img/dbd7c01a5fe5abd176206d8384e47628_61.png)

What's the rule to change。Is。Rritthm here。Well， we define， I think this is a better explained with。

Other。Let's go the this function。嗯。That's suppose we have this model。This is our model。あで。

Quaddratic model and our stability center is here。し。This is x。Okay。So the next the quadra quadratic。

Moel。Os。With above。Something like that。In red， we have our module。In blue， we have。Our model。Plus。

De qua。对。And well。The next date is here。X key。Plus1。呃。So at this point。This point is。

The value of the model。At the new point。Okay， evaluate the model at this point。 have this。Here。

I have。Okay， so here I have the value of the function。Stability center。And here。The model。Okay。

 we have this。Distance。And we call this distance。Zke。Okay， and this is the。

Predicted predicted decrease。 So this is how we would like to decrease our function。 We are here。

 Wed like to decrease， We are here。 Wed like to decrease to this point。

But this is not what I going to this is not what's going to happen because here。

 see the function value is there。 But we don't know yet。

 We just defined the point and we have this information because we know the model。 still don't call。

 haven't called the orac。 We don't know this point this value here。Okay， so this is。

What would like to decrease is the maximum we can decrease the maximum amount we can decrease giving。

DK。X， K and our model。 Okay， given these ingredients， this distance is the maximum can。Decrease。

Then you call the orac。 You have this van。And this value。Somewhere in between。

And we are going to call this point X hatt， a stability center。If this distance。

Is greater or equal than。A fraction of this distance。Okay。This is what's written here。If this value。

啊。If x。K， plus 1。Is。Is smaller than。The point at the last center。Mine something positive。

 that is this this。 A fraction of it。 There is a coppera。And this cara is。

 is a number between 0 and 1。 It means a fraction of this disk。So you should have。We call this， well。

 this is our test。 And if you have this decrease， you say we have enough decrease。

 This is enough to change。 And then the next point the center will be this one， if not。For example。

 if this value of the function were really near here or up， you don't change。Okay。And we， we。

 we define that iterate as an old step。呃。So here we can see in this case， we don't change the center。

 Here we can see that the sequence of。

![](img/dbd7c01a5fe5abd176206d8384e47628_63.png)

Ciro step。 This， this is a sequence of Si step。Is a sub sequenceequence。 This is a sequence。

 sequence of series steps。Is a subequ。Of the， the sequence。Of the eaters。



![](img/dbd7c01a5fe5abd176206d8384e47628_65.png)

You have， you generate a lot of itererates， and you have a sub sequenceequence composed by the series iterates。

 and the function for those points。This sequence is no increasing。

So we had to say that the method is a decent， decent method， because。This decrease。

But if you look at this sequence here。Then we cannot say that， and this can oscillate。对。It's clear。

Okay， so I think we are now ready to present the algorithm that you already have an idea how it works。

Not yet。呃。This is a beautiful lamb。

![](img/dbd7c01a5fe5abd176206d8384e47628_67.png)

To， to define。嗯。This is useful to define the stopping test。Well， it's saying that the exititer rate。

 when you solve that Q P。Is。I step。Of this size。From that point， in this direction。And。Well。

 this direction is the sum between a sub gradient of the model。

 plus I element in the normal corner of the feasible set X。Well， that's not difficult to show。Well。

The next point。You can write it as。Minimizing the model。X。不。Okay。Here we have the stability center。

Plus， I'm moving the constraints to the objective function。And considering the indicator function。

Okay。嗯。This function is convex because the feasible size is convex the model is convex。

 So optimal conditions for this problem is 0 belonging to the sort differential of this function。

 right， So optimal conditions。0， belonging to。Well。Giving our assumptions。On the feasible set。

We can pass this operator inside， given the assumptions。Our assumption implies that 0。Belongs to。

If you differentiate here。This will be。TK。Well。You get a point。

 It means that it exists a point in this set。Such that0 is equal to a point。In that set。Pf。Plus。

 this term， I think it's better if I write here。That implies that0 is equal to a point in that set。

Plus， these。哈。Plus， a factor。That。Okay， and this gives。Our result。Okay， that's。It's simple。

This linearization， we call it。

![](img/dbd7c01a5fe5abd176206d8384e47628_69.png)

Aregate linearization。That's crucial for bundle methods。Because remember， as I when I said。

 we can remove some linear in the model。 We can remove anyone you want。



![](img/dbd7c01a5fe5abd176206d8384e47628_71.png)

But we have to keep this one。So we can do anything we want with the model as long as we keep this one。

So this is very important for the conversionverence analysis， for the method to work。嗯。

So it's important。 It's interesting that disization satisfied Disneyequality and why that。Well。

 we know that。This point。Belongs to this。苏必非是吧。EWe， we， in fact。

 we have to keep two linearizations in the model。EAnd one of them is this one。嗯。It's like。

 I'm going to give more details， but it's like。You can do everything you want with your model。

 De any， any linearization as long as you keep that one and the the newest one。Because this。

 it's like it condenenseates all the information we have in the past。

Because you use the value of the model and this vector that well， it's considering a gradient。

A sub gradientient of the model。 So it keeps some information the past here。It's like you， okay。

 I have so many information in the model， but I cannot afford such amount of information I'm going to exclude some。

 but I have to sumize that information， how you sumize through this linearization。Ja。呃。

But it's important that， this organization should has to satisfy this inequality。

And this is what we are going to show。F to show that， we need to use this assumption。 No No。

 our definition， this is， a vector in this set。And this one。This。Well。From this information。

We can use the subgreg anti quality。Because this is sub gradientient for the model。So， it's like。

If I have the model。At this point。Plus。P， FK。Do suppose。X minus X key。Plus， one。This is smaller than。

They 뭐 are。X。Sality。I'm just using this this。Definition。To have。

This inequ because we know the model is by assumption convex。We can use the same thing here。And well。

Here， in fact。Have this， right。But the next to date is feasible。And because it's， by definition。

 feasible。 See， if it's feasible， this indicator function is 0。Now， some。If you sum。

And use a definition of that linearization。If we have。Oh， sorry。妈的。In fact。

 our modelto is approximation from below。After what we have is gifts。Or。Is the same， but。This is。

 by definition， our linearization， aggregate linearization。



![](img/dbd7c01a5fe5abd176206d8384e47628_73.png)

At the point， x。Okay this。In particular， for all X。Feasible， because when x is feasible。

 this part is 0。O。This is an artificial linearization。And it says。

 if you include this to define your model， you are not going to damage your model。 It's not like。

This is my function。This is my model。

![](img/dbd7c01a5fe5abd176206d8384e47628_75.png)

And if I add。Disarization is like， I'm going to have something here。Or perhaps not， not improve。

 But I have something。Are you。By no means。Have something like that Cutting off the function。

 This will not happen because of this property。

![](img/dbd7c01a5fe5abd176206d8384e47628_77.png)

So it says。Well， if you add disonization。

![](img/dbd7c01a5fe5abd176206d8384e47628_79.png)

We are not going to damage our model。You may consider it。 In fact。

 we should consider that linearization。Question。Iization。Yeah， yeah。Yeah， in fact。

 I think this result it， this result holds also if you。Theyine this。Neneization。 Well。

 I like to define this way。 Claudia， for example， she defines this anization only with this piece。

Okay， and it has the same theoretical， theoretically， is the same thing。 in practice。

 I think it's different， but I don't know which one is better。 I'd like to consider this， this way。

the interpretation interpretation ofization， okay。Let me see。嗯。W。And suppose this is your point。

Exhat。

![](img/dbd7c01a5fe5abd176206d8384e47628_81.png)

嗯。The draw is complicated， because。If I take this。No。Wait， wait， wait。Is an。Iization on that point。嗯。

I have done this before。Suppose that your it date is something。Like here。This is。X，k plus 1。啊。

In the draw， it'， complicated because if I。If you in this side of the model。

This denization we coincide here。If I'm this side that linearization。

 will you coincide with this one。呃。Well， but I could be。Here， for example。

 let me see what happens here。 if I' here。In this case， okay， here I think I can have an idea。嗯。

That linearization will be something like。Smunization here。Okay， because when。We evaluate。

 you evaluate that linearization， this one。At X K plus 1， this disappear and remains that。

 So it means here。If you go along this line。We always， you will be always under the module。

So all the linearizations here is possible。Okay， but we have just one。but the what time was。呃。

Telling you before is if you are in one side， then that organization will coincide inside with the one you have。

It makes it gives an interpretation when you have this combination。to pushush。Yeah， it's。

It's saying here， if you decide to delete this linearization。

You have to have this one to ensure conence。Because if you delete that and don't consider this white linearization。

 Well in theoretical interior theory， we cannot prove convergence。So you remove one。

 but to have to keep this。 But here it's just this stupid right。 You remove one and keep an other。

 What's the game， Nothing。 The fact is， if you have 1000 linearization。

 you can remove 900 as long as you keep this。And this makes a lot of a difference in practice。Yes。

 because see。This。Un go here。Which is。This vector。呃。This vector is a combination。Between。

The sub gradient here and there。 So I'm not entering。 If you exploit more here。

 we are going to see that。诶就咁谂。Were going to see that， that point。P F of k。Is， in fact。

A convex combination。Of all the subdi gradients for the function。And here， the size of your bundle。

 Okay， the size of your bundle and。Alpha I。Or negative。Alpha I equal to one。No， there is no gain。

There is no game。This is interesting when you Bondo is big。Yeah。

 and this more one could be of any size。 you can， in theory， replace 100 linearizations。

By 1000 realization or more by 2。 But in practice， is is not good。 In practice as。Yeah。Exactly。

 exactlyly， exactly。 You are sum sum sumizing， but it works in theory。

 In practice it's better to work with a bigger bump。 So it， it's a trade off。

 You have to consider your computer。 It's good enough。 You have。

 you are working up powerful computer。 You can consider many linearizations。 and your。

 your master problem and define X K plus one is too cheap。 So keep out linearization you have。😊。

But if your problem is too large， x is too large。Sometimes it's convenient to work with a smaller bundle。

 a smaller bundle。And you work a smaller bundle。 You have to consider this linearization。

 and this linearization sumize your past because this X hat。Is defined。

By the sum of two things that is in some place here。

And this vector is the combination of your past linear sub gradients。



![](img/dbd7c01a5fe5abd176206d8384e47628_83.png)

This is this。哦， no我 didn send question。You， you want to isolate here here。

So one way to compute this is you solve the Q， P。 you get out the lag multiplieries。

 That's is the lag multipliers。 You make this this sum and you have that point。 And。

 but you don't have this element in the normal coin。 So how you compute that G。As Cla said。

Just write that equation。That's important。 Thanks， Colad， because， well， I'm saying。

 consider that linearization about how you can compute the G。He compute the G heart。S。呃。

X hat minus x K plus 1。Over T K， you know this guy， this one， you know。

 because you have solved the Q P。 and you know this parameter。Therefore。

 you know this guy here and you can compute the initialization。Okay， this is useful information。



![](img/dbd7c01a5fe5abd176206d8384e47628_85.png)

Okay， let's move forward。嗯。I have said about the predicted decrease。 URL are know this measure。



![](img/dbd7c01a5fe5abd176206d8384e47628_87.png)

There is now this。Agreggate。Ahor。What's the aggregate A is the difference between。Here you have。

Your function。And here， you have。Your linearization at that point。 this is。

 this is an linearization evaluated at this point。 So this difference。This is your organization， K。

 I。Of x。So， this distance。Is what we call。Agregate一。And it turns out。This is interesting。That。

This point。Belongs。To the switch differential of the function。The functionox itself。哦。Plus。

 the indicator function。At。Xk， but this。Is there。In theex so be so differential。

So we are minimizing this function。 For example， you want 0 to belong to the Sub differential， right。

 If you want 0 to belong to the Sub differential to have optimality， we need。



![](img/dbd7c01a5fe5abd176206d8384e47628_89.png)

This guy。To go。To 0。 and also the zero。Because if you have a sequence。Those guys are， those guys。

 these guys vanish。So the cluster point of this sequence will be an optical solution。

So this is not difficult to show。 We are going to show this now。Other things。

This aggregate error is no negative。 Well， it's clear here。



![](img/dbd7c01a5fe5abd176206d8384e47628_91.png)

That's not negative。And predicted decrease is also a negative。 Well， let。

 let me show out those results。嗯。Sing。Let's use this inequality。By definition， our。Agregate ahore。

Is it equal to。The value of the function evaluate at the best point。Minus。

The value of the aggregate linearization。At the best point。But using that。Since。F of x。

Is greater than or equal to。To。For all X， the feasible。So， it implies that。

De initialization A is not negative。When we are going to start next week。

 we are going to start in exact bundle methods is when this function is not computed exactly。

We don't have this property anymore。And you have to work out on this because it's crucial for the conver。

 But so far， so good， no problem。It'sSo negative。We can represent。



![](img/dbd7c01a5fe5abd176206d8384e47628_93.png)

，Predicted decrease。By this form。How we can compute that。Show that。



![](img/dbd7c01a5fe5abd176206d8384e47628_95.png)

嗯。I just forgot。

![](img/dbd7c01a5fe5abd176206d8384e47628_97.png)

Now， I want to show this formula here。

![](img/dbd7c01a5fe5abd176206d8384e47628_99.png)

Yeah， we have to work out this one。Mi see。Yeah， exactly。From here。Is you know。啊。O吧。This is the equal。

 Now， I'm going to use the definition。Of that linearization。Dization is。때모 아。X K plus 1。Minus plus。

Xq plus 1。Just using the definition of the generalization evaluated。Upa， it's wrong。 E at that point。

Thisスで。Okay。And now。2。Yeah。This value minus this one is the。predict predict， predict。

Predicted decrease is V K。And here。We are going to use that definition and just row erase it here。

 This is a minus T J K。So， that will be。A。Easy go to。Minus。This is。Vki。Mines。Thank。Okay。

 and we have the result。啊。

![](img/dbd7c01a5fe5abd176206d8384e47628_101.png)

And， of course， V K is no negative because where we are， is the sum of two non negative。Parts。Well。

 this other one。That' the。Last inequality is important， because it's。Where we can， from where。

 we can ensure conversiongence。

![](img/dbd7c01a5fe5abd176206d8384e47628_103.png)

If de or 0。This vector is 0。This point is an optimalim solution。Okay。Let's see that。

To prove that inequ。We start。With。F of x。Is bigger。Here have to use the linearization。

 and then the model。Yeah。I'm taking this for every X。Feasible。This is true。

 We have prove a Disney quality。Now， I'm going to use a definition。Plus。Okay。Should continue here。

I'm going to some。This point。But I used be tried。Going to continue here。Okay， this is just two。

To finish。右边。Now I'm going to sum and subtract。In a product with the stability center。

That's going to be。Plus。Minus。そなんです。This。Okay。I just。Some sub these abstracted these in a product。

Yeah， it's okay。呃。Well， well， this is K。But this difference， we know that T， J K。Mus。



![](img/dbd7c01a5fe5abd176206d8384e47628_105.png)

No。In fact。Here。If you use this term。Minus V key。I bring this V here and pass this Ek to the other side。

This is。Ms。Well， this is quite saying that， in fact。This better。Belongs。

So this approximate to be differential。Well。Yeah， because here there is the normal coin and so on。

Now remember why I prefer to use delineization， as I said before。Disaggregate linearization。

 considering this term here， the normal con， because we can arrive in this situation。

If you don't consider this term here， like other researchers do， just neglect to define here。

We need to put。Andicator。O。Well， it's the same thing at the end。Because are feasible。

 So this is important to drive this point， this vector and this or to 0 to ensure conversionence。

 Well， but what we want to get is that equality。So， from here。Just khihua。Inequality。

 it's done already。This implies。But we， we want。

![](img/dbd7c01a5fe5abd176206d8384e47628_107.png)

啊。This for all the X。Feaible。Therefore， if you get。This equal to 0。 This one equal to 0。

 It means that this point is less than or equal to f of x for every x。 It this point。

X hot is solution。Okay， so we need to focus on this， the sequence of serial。Itals。

Cause this is one that we converge or a subence， at least a sub sub sequenceequence will converge to the solution。

 So what you want to do， what is to drive。You want to drive。G， K hot。And this aated error。20。

 at least for a sub sequenceequ。Yeah。Here。So I didn't understand your question。

 What's the difference。华0。This is the definition。 All the， the vectors I find this inequality。

F of x bigger than this。 This is definition。啊呃。本日さ。Yeah。Allright， this。Okay， you， you understood。

 but perhaps it's not clear for。Anyone else， let me right。This is the definition。Of a function。

 I don't know。Sa。This is just the definition。 just apply the definition there。 Of course。

 this guy has to be。

![](img/dbd7c01a5fe5abd176206d8384e47628_109.png)

No negative。 And it is the case， our case， because we have just proven。Okay。Well。Now， yes， we have。

 We are ready to show the algorithm。You already know how it works。

This is not exactly the one is in the project。 but well， just some modification。

 you have the same one。 Okay， so don't worry when you code for our stochastic programme is it just code like it is in the project。

This is a bit more general because we are considering this function。

 not necessarily sum of a linear term plasmaza。I know one。Well， we start with this ka。

That's used for the decent step， decent test。呃。Initial pro parameter。

 And we bound this parameter from， from 0。 Okay， should not be 0 because otherwise。

 we are going to divide by 0。 Don't want this。And a feasible point。😊，A toance to stop。

 We call the articleacle， and we declare the initial point as the stability center。

 The first one stability center。 our bundle is one。 The firstization。Well。With this bundle， we have。

Our model， we minimize this cube P。 We get the nexter rate。啊。Here we define a G K。

 That's important just for this rule， we have shownn。Predicted decrease。Also easy to。

 to define because we know this value and you know this one because we solve the model， the the。

 the master program。The aggregate error also is to， to define。 So everything here。

 once you solve this problem， everything is straightforward。

We stop when the linearization layer is small enough。And this vector， the norm of this vector。

What you have just said， this comes from。The definition or the one as you want。

So we stop when both measures are small enough。We called the Oracle for this new new point。

Once you call the oracle， we have this value。 we can decide if you are going to change the stability center or not。

And this is the rule we， we saw in few slides。Before。And well， if you change a stability center。

 you may choose a bigger step。Increas this parameters means， well， if I'm think like that。

 I'm decreasing。 all the I'm decreasing。 it means while， I'm in a good direction。

 I could give La larger step。So if you are decreasing， okay。crazyaz step。Otherwise。

 if you're not moving， always a lot of no steps， it is。

 it's like it's advisable to perform a small step size。So you。It is small steps。 So you decrease。

Your pro， however， always。Bigger than this mean value here，ca you don't want it to be 0。

We are going to choose here。 we decide if you are going to keep this neization in the bundle。 Yeah。

 this you have to keep。 So the next neization， the new one you put in the bundle。Now。

 what you do with the previous ones， You can keep it。If you keep。

 you don't need to include this index that summarize all information。

 You just keep like in the cut pen mode， the usual one。Or if you decide to delete something。

 you have to include that linearization。 So， for example。

 you can work only with these two linearizations， the method。We work， however， it's lower。

 It's better if you consider larger。Bunds。And the process repeats。

So the difference with the cut you have an algorithm for the。You have a really shaped algorithm。

 Now for then next project， you have to code an algorithm like this one， a pro bundle of math。

You have to， instead of solving LP， you have to solve Q P。You have to compute。Those measures。

 and it's easy。 just applied as a rule。And the rule to decide to update the stability center is also easy。

And that's it。I think in the project， we。We didn't ask you to， to eliminate linearization， right。

 It just can keep out the B， the full bundle like you did with the shaped。So， the。Depiate is。

Let's say it's it's， it's you。And the makes's not difficult。 The， the most difficult part， shh。

 perhaps is to code the Q P。またまあなっていくかと。Well， some， some tips。Okay， just I mentioned it。

The pro is now increasing along all steps。 that's important。That's important。

For this is for the conversion。 It's a technical result。 If you perform an old step。

 you should not increase your pro。 It means you are not in a good direction。

 You're not decreasing your function。 Why you should give a larger step。 No。

 just keep the way you are or decrease your step size。That's the rule。

 That's important for the conversion channelss。呃。This is a heuristic。For you to， to define the then。

 the next pro parameter， okay。This is based on a quasi uome rule for。For approximating the。

 the Asian， Asian of a function。 So if you have studied B FGS method。

 these are sort of the ideas from there。 There is a。The way it is here is a heuristic。

 but there is a paper by calledde Maral called Marhal。That gives a lot of theory about our rule。

That's more general than these。 If you are interested， I can give you the reference。 But well。

 this aher kind works quite well。呃。2。This is， it is a divdisible to consider different tolerance for those measures。

To stop。Because， well， here we are using the same tolerance for the A and for the。For this norm。

 here's the norm of a vector disalinization。 It's like you are measuring tomatoes and potatoes of the same thing。

 There are different things。 You Use different tolerance for them， for them。 Okay， in the pra。

 you should consider different tolerance。But we are concerned here the theoretical theoretical apart。

 Well， just stop when they are small。 In fact， in perhaps， you should divide these by the relative。

Stopping test。 divideivide this by this value of the function。

Besides value to have some relative stopping test。一见。It means， you should not increase。

You should not increase。And if you decrease， don't decrease less thisvalue because you don't want it to be 0。

 just bound it。But the method works if you consider this T fix it。I don't know。

 You don't know how to do No， no， no idea and no clue to update date。Set T。

 K equal to one for all iterations。 The method will work。

But it's a divdisable to change this parameter。 And a heuristic to do that is this one， okay。But。

 this is important。It doesn't matter。 This T K can be constant as long it's non negativega it's bigger than larger than 0。

 That's okay。This is the product of the proximal bundle mat。 for the level of Bo mat。

 We have another product， and that one cannot be fixed。 But this is a subject for the next class。

Let me see if you have something。 Okay， here are just an ideas for the conversion analysis。

 But I will continue the conversion analysis next class。

 and then we move to the other bundle methods。 So C。



![](img/dbd7c01a5fe5abd176206d8384e47628_111.png)