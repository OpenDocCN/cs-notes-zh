# IMPA《随机编程｜Basic Course on Stochastic Programming 2016》中英字幕（Claude-3.5-sonnet p13 -13-Basic Course on Stochastic Programming - Class 13.zh_en -BV1tH92YXEnd_p13-

Okay。So， good afternoon。Welcome to this bass lecture， number 13。I am a well known elevator。

 and I will be with you in these coming weeks。And well be studying multi stageage stochastic program。

Before we start with this subject， let me recall you that well， we， we have an exam next Thursday。



![](img/735d75348d3b6b939c5a37173128ff0f_1.png)

So I will send the exams to the professors in the other universities by mail。

 And so I apply the exam here and the other professors in other institutions， will apply the exams。

D exam there。Well。So Clauddia and Juan Palo was discuss the two days stochastic problem。



![](img/735d75348d3b6b939c5a37173128ff0f_3.png)

The Mo stage is an extension。Is an extension in sense that。



![](img/735d75348d3b6b939c5a37173128ff0f_5.png)

We make。A decision。Let's say x1， the first stage。And then。At the second， second stage。

The uncertainty is revealed。Xci 2。 And when these uncertainties revealed。

 we have the opportunity to make another decision。Let's see。X 2。And then we have a third。Stage。

Some the uncertainties。I revealeded。We make another decision。And。So完。Up till I stage。呃。X0。嗯。

So the two stage we stop this part。 Here。 we continue。So this kind of of approach。

 Mo stage program appears in many practical applications， in many real life applications。



![](img/735d75348d3b6b939c5a37173128ff0f_7.png)

嗯。I have we， we， we have many。

![](img/735d75348d3b6b939c5a37173128ff0f_9.png)

We have several ways to， to deal with this stochastic program。 Mo say stochastic program。

 I'm going to present the three main formulations。So when we deal with these kind of problems。

 we have more difficult， for example， in notation， notation is a bit more difficult。

 The algorithms to solve the problem in America。It's a bit more involved。

 And I'm going to try to this to， to， to show you。 I'm going to show you some formulations and algorithms。

 So today， I'm going to start with an example。 we are going to discuss an example。

 I point out the the main differences between the， the， the two stage model。

 and I want to present some。Some formulations， the three formulations we are going to discuss。

 to discuss。So， first of all。So the resolution should be good enough。Cled this。

We are going to start with the flower girlru problemum。The problem is the following。

The former girl sells rose at the price P。But has to buy them at the cost that the price is see。

 before she starts to sell， she buys。At cost， C。If， if the flower girl。

 fly flower girl doesn't sell all their roles in one day。

 the remaining rows can be started and can be sell in the， the next day。And， well。

 I don't have a notation here， but I have next。But you can just save the roads for one day。

 If you need to save more， it's it's impossible。 You cannot save。And well。

 the demand for the rows are uncertain。 I represent this demand by H ofsi。This is demand of the。

 the day tea。And the flower girl wants to mix maximize her total expected profit。

The horizon is related to the number of stage for which the flower girl continues selling roses without break。

嗯。Let's concentrate in a nice a simple case in which the flower girl buys orders。They rose on Friday。

To sell on Saturday。If there are， if， if the girl doesn't sell all the flowers。

 she can keep the flowers to sell on Saturday。On Sunday， sorry， but also on Saturday。

 she can order more flowers， so she can order on Friday and Saturday。U。So the， the。

 the amount of flowers she's going to order order on Friday is X 1。And there is the demand， H2。

On Saturday。So。We assume that we don't pay。 She doesn't pay to store the roses。And， but well。

 this is an assumption。Simple， it doesn't influence it in anything。

 We can just assume that for example， she， she pays a place to put the roles。 It's not a big deal。

And also on Saturday， she buys X2 amount of X 2 new roses。The amount of flowers she， she stores is S。

Of course， depends on an uncertainty。 She buys an amount of roses and depending on uncertainty。

She will store some rules or not。And on Sunday。There is can can we we she may have。She possibly。W。

 this W is， is the amount of unsold roses。 So in this case， on Saturday， if the rose she cannot sell。

 she will throw away。Of course， this is not interesting because she paid the ruless。

 and then she throws away。Okay， I think this is everything for our problem。A description。

 I split here at the first stage。Friday night。Well。

 our decision variable is just the amount of flows。And she used to buy the constraint。 Well。

 we need to buy something， some rose， No negative constraint。 Second stage， Saturday。

 demand is revealed。So variables are the amount of is stored at is stock at roses。And x 2。

The amount of roses she will， new roles she will buy。Constraints， well。

She's going to keep some amount， No negative amount。

 She would order some non negative amount of rules。 And， of course。

 the amount of rules she bought on Friday。呃。Minus the amount of rows left should be less or equal to the demand。

Third0 stage。Demand is revealed。So variables here in this case are just the amount of un unsold roses that will be throw away。

Constraints， well， this is no negative and the amount of row she bought on Saturday plus the amount of remaining row mines the one she will。

Throwaway should be smaller than less than less or equal than the demand at the stage 3。So the。

 the idea， see， new decisions are made gradually。According to the uncertainties。

 when the uncertainties are revealed。 So you make new decisions。So she wants to maximize her。

Her profit。

![](img/735d75348d3b6b939c5a37173128ff0f_11.png)

So we call it the C， the cost of buying roles， the。The price of selling。

So this difference is the profit for the amount of rose she bought on Friday。And sold on Saturday。

We are not assume that， she will pay for starting the， the， the un soldolder roses。

Here are the pro for the second stage I he， the last one is the cost。

 because if she throws some roses away， well， there is the。This loss， the。

 the the amount of rose and the cost she paid。Well， just organizing， we have the second line。Well。

What happens if the demand were known in a advance。What would be the。

 the best decision for the flower girl。If she knew。What she would sell， the amount of flows。To be。

 she would sell on。Sunday， Saturday and Sunday。If she knew the demand， well。

 the best decision is to buy exactly the demand。So， in this case。If a Friday。

 she buys exactly the demand of Saturday。And on Saturday， she orders this。

 the exact amount of the demand of Sunday。So the pro would be this one。 And that's the。

 the best decision。She can make。Well， however， we don't know the demand。 The demand is uncertain。

So how should she proceed in this case。Well， she could， for instance。

 make a decision that is optimal on average。 So in this， in this。

In these weeks that we are going to study the multi stage stochastic programs。

We are going to be focused on the the average。 We are minimizing the spec value。 Okay。

 we're not going to consider risk measures here。 It's possible to consider whom probably will show this later on。

But we will be focused on minimizing the expected value。嗯。Well， I， I I haven't said。But well。

 the assumption here is the same than the beginning of the course。 We are assumed that the。

The assumption， the， the， the uncertainty doesn't depend on the decision we make。



![](img/735d75348d3b6b939c5a37173128ff0f_13.png)

For example。U。The decision that the flower girls makes will not impact the demand for us。

So that's a standard assumption。 It's natural。 Most of the case， for example， if I。

If I bring an umbrella to the class today， this will not influence it if it's going to rain today or not。

So that's the kind of assumption we assume here。There are， of course。

 cases in which the decision influences the， the。Theスカスasticプロです。For example。

 if you are a very rich person。Very well known person。 and well。If you say one day。

 if you make a statement， I'm going to invest all my money in such a company。So this view。

People can think， well， what's going on with that company。 You made I， I would like to invest there。

 too， because that that person is a wise person and rich person is invest all the money there。

 because something is good。 Let me invest， too。 So the variability of the financial stocks of that company will change。

 The stock cast process of the price will change。 So this is an example in which decision can stock process。

 But you are not concerned about this case here。 Okay， I'm assuming that you are not。 so that。

millionillionaire， not so that rich that you can influence the sas cross in certain problem。Well。

Let's continue here。So as I told you， in this case， I told you that we are going。

 we are going to be concerned about minimizing the expected value。 In fact。

 here we are maximizing the expected value。 But well， the same thing。

 Just change the signal and we are done。So， but for this example， we are maximizing。

So the problem and the general formulation of this example。Of the flower girl problem is the falling。

We want to maximize the expected value of the cost subject to these constraints。

 You have this constraint。 Here is the amount of rose to be that she buys at the first。

Stage on Friday here， the constraints related to the second stage here。

 the constraints relate to the third stage。Well。What's important to mention here。

Is the amount of rose you will buy on Saturday depends。On the。Uncertain here， for example。

 the demand。For example， if fish， the demand is so low that the。

most of their roles was most of their roles were unsold。So she has any stock。

 She can sell those rows on next day。 So this amount of。Rose will depend on the certainty。And。

 of course， at the third stage。The amount of rules she will throw away will depend on the uncertainties and not only on the uncertainty of the third stage。

But the second。And third。So， well， see here we are putting the dependence on the second stage， too。

 And here I'm not using any number because I mean the entire path。Well。

 I'm going to discuss to present what is a scenario 3 for a Mo stage program。 But before that。

 just let me write here because it can help to understand that。



![](img/735d75348d3b6b939c5a37173128ff0f_15.png)

Problem。So well have the stage first stage。So， for example， we have a demand here。Other on。

Let's suppose that's high。没的。Lu。That's Sir。Second stage。Let's suppose the's same thing you have。

For the。Third stage。Hi。Hい。Low medium。Lu。And here is the。Stage T T equal to 3。Of course。

 when you are considering standard3， we are making a various assumption that this to process。

 the demand can assume only these three values here。 And then for each node of these three。



![](img/735d75348d3b6b939c5a37173128ff0f_17.png)

For this， for the next period， only more three events。

 This is an assumption is a simplification of the problem。Okay， but this is just to now for us to。

To help our understanding。In fact， we have many possibilities here。F的 demand。When we are。

Talking about maximize the expected value。If you come back with it is 3。

 we are looking at this three。Like that。You I seen the entire tree。

We want to maximize expected value considering this three。 Well consider this stochastic process。

Well， of course。So here we have the realization for the second。Stage here。

 realization for the third stage。Third stage。And。The decision you make in this note， for example。

 will depend on the decision you made here， not the decision you made in this note， the module。So。

 you have to keep。So what you are going to do here。

 What will happen in this case will depend on this。A bust。

And how you consider this link between one stage to the other。In this case。

 in this formulation is this variable here。W。So in our formulation。

 this variable is taking into account the temporal dependence one stage to the another。

 So this is another reason why I didn't put index here。Okay， because coupling the two states。Well。

Here， x 1。Doesn't depend。 Nothing here depends on uncertainty。

 We can move this expectation to this other part。And this is the same thing。Well。

 this is general formulation。For this。A simple example。It's just on。One formulation， there are。

Several formulations for dealing with stockto cast products。No， I would say that。

All of them have a advantage and advantage。So which formulation you should apply will depend on your problem。

And I， I hope I O I will make this clear along the， the next classes。

So this is a formulation we call gene gene formulation。There is this one。

Which is the nested formulation。

![](img/735d75348d3b6b939c5a37173128ff0f_19.png)

In this case。We are using here， the ex， the conditional expectation。So instead of seeing。

 let's come back to our example here， this three。These three， the following。

 instead of considering these three。Like it。Looking。Other parts， you just。Taking a look here。

You have an expectation here。 The decision you are going to make here。That's good for the future。

 Which future only。都是万。So we call these nodes of the trees， the three。

 those nodes are the children of this node。So when you want to make a decision here。

Which is good for the future on average， considering。The children。The same here。

Want to make a decision that's good That's good for the future。

 considering those children and the same thing。Here。Well。

 but our problem are not is not folks on those stages。 folks on the three stages here。 So you have。

 again， to consider it。Everything。So， I'm making a confusion there。But how you can represent。

 what is the intuition。 Well， what I explained there is the intuition of this formulation， because。

 well， see， you want to maximize the profit。 You are taking into account on the decision the first stage。

 here there's expectation for the future。 But this expectation takes into account。

 The profit at the second stage。And also， the expected profit profit of the future of the children old。

So for this， this is why it's called nested because it's nested。 one thing nested。



![](img/735d75348d3b6b939c5a37173128ff0f_21.png)

Along these stage。And。Well。Here。The first expectation you are taking account。

The probability distribution of those nodes。Here。So the first node is assumed。

 as always in our our course。It's assumed to be known。So， probability here is one。So the。

 the other expectation is here。The， the second expectation is taking account the history for this is。

 This is why I considered。Expectation。Of。The uncertain at the third stage。Well， in fact。

 I use the opposite here。Also uncertainties at the third stage， giving the the historical。

What happened。So you are some of these nodes and you take the expectation of the children nodes。

This is what's happened there。There is a subtle difference here。Is the fact。X 2， here is nothing。

Is not a function， Well in fact。You can see this， this variable as a variable of that stage on X2 locally。

 locally。 If you， we come back to the previous slide。You have x 2， x 2 and this variable x。

 depending on。你在哪有。And on the on the nodes， the uncertainties。 And this one， depending on the。

 the entire path since from the root node up to the end of the， the nodes， the， the， the， the stage。

But so in this case， those variables are functions of the uncertainties。When we use this formulation。

We see them as just the variables， normalmal variables。Why。

 because we are folks on the part of the the tree。 I'm， I'm telling you3。



![](img/735d75348d3b6b939c5a37173128ff0f_23.png)

But， in fact， can be any start process can be continuous。

 I'm just telling about the three because it's easier for us to see what's happening。 Okay。

 cool it's more general。And。So whats the dependence。In this case。Well。

 the dependence is implic here because we are using this nest。Forulation。

Because while the decision I make at the second stage will depend on the。

 the cost of the children knows， the decision you make for the do that children knows。

 So it's very place here。 and also for the conditional expectation。



![](img/735d75348d3b6b939c5a37173128ff0f_25.png)

This is another way to represent the links。对对对对。Yeah， they link between one stage to another。So。

 when you consider。This formulation， you have algorithm suitable for this formulation。Okay。

And you have also。Going back。You have algorithms suitable for this case。 Well。

 when you think of solving a real life multi stageagetochastic problem。

We have to discretize this stockas process and consider it a scenario。In this case。

This is everything linear。 Here will be a sum of probabilities。And。So， these of。

Variables are function of the stocastastic process function of the uncertainty。

So we have to create many variables， one for each scenario。 This is a kind of formulation。

 So the fact that when you deal with this， you have many variables。 focus on a scenario 3。

 you have many variables。 the number of variables can be reduced if you consider this case because you don't see them the variables as。

Depenent of the， the， the stock cast process， indeed。However， this has another difficulties。

Many algorithmically， you are going to see。the future。And the fact is。

 when you consider a scenario 3。This formulation is good。

 when you solve you formulate your problem as a large scale linear program problem。

 So and then you this become a very large LP linear program。And you solve it at once。 Of course。

 this is not so that realistic。 you can deal along with is small problems。嗯。Okay， I have。

Fed discuss about this。Well， we have seen two formulations。 There is another one。What， what is this。

 that is this dynamic formulation。Well。This is。This comes from the， the， the， the other analysis。

 Well， because we are， we are focusing on the。On the notes。Shouldilren notes。

So I think it's better if I。To this。Dhrowing again。So in this case， we start at the last。

 we start at the last period。And which we know the decisions at this node， for example。

So when you at this node， we know。X 2。The amount of flowers are going to buy to sell on Sunday。

And we know the amount of row left in stock。And we， we come to the third stage。Here。

We have a node of the train depending that depends pen this earlier this is one。

Realization of the stock process， another one， another one。

So we are going to optimize with respect to。We are going to optimize in each note， giving this。

Values， these variables we are going to optimize in each node of the three。So， this is。

What's written here。You have this decision in the past and the second stage。

 the amount of rows and the amount of left roses。You have the realization at the end， of course。

 depends on the， the entire， the， the entire path from the stage 2。3。And we are going to。Maximize。

This value。In fact， we are minimizing the amount of rules。That， the， the。

 the the flower girl you throw away。And we are going to solve。

This LP for each one of the those three nodes when you are considering a standard 3。

For each one of them。And then we move， okay。We do this， So here。Then we have another decision here。

Are going to solve for these 3，3 nodes。 And here， same thing。I could say that here。

 they are different。So I put a tilt。 I put a heart here。

Different decisions because we are in different conditions here。And， but we optimize for each node。

 depending on the past。And then。We move backward to the stage 2。 Now you want to。

Make the best decision for each one of these nodes。When you are here， you depend the amount of rose。

The flower girl ordered it。So you are going to order X 1。And here is。Uncertain X 2， X 2。

Each one of these nodes。 And then giving this。This is the first stage。Given the， we optimize。

 but not optimize only this node。 Of course， we are taking into consideration the future， too， so。

This is why dynamic dynamic。 So what I explained there is the phone。 You have the amount of lows X1。

Theialization for the。The second stage， which is Saturday。And we are going to maximize the profit。

But take into consideration。This expected profit for the children notes。And。You go backward。

And the first stage， we have this problem to solve。And。Well。This is interesting， because if you we。

Forget stage 3。Forget this dependence and the， the cost of stage 3。Look at only this part。

 this LP and this。Problem here。 we are in the second two stage stochastic problem。嗯。Same thing。 But。

 well， you have to take into consideration another stage， another step of decision。Uncertain。And。

 well， the temporal dependence is。Once again。You can consider here for this expectation。

Which says which node of the three。You are making decision。So that。Expectation。

 conditional expectation。Is saying which part of the three。You are concerned you are dealing with。呃。

Okay， so this， let me see。Yeah。These are the the three formulations we are going to consider， yeah。



![](img/735d75348d3b6b939c5a37173128ff0f_27.png)

See， yeah， the question was。Well， what is the meaning of this。Third stage here， right， that well。

 the question was， we want to minimize the amount of rows that we are going to throw away。

 The answer， yes， that's it。

![](img/735d75348d3b6b939c5a37173128ff0f_29.png)

In this case， this is easy。 Well indeed， it's not optimization problem。 Yeah， it's just simple。

But we want？Yeah， it's a number。 Yeah， this is really simple。 for this case。

 But if you consider for this example， if you consider another more involved example no and the fact you are going to solve here。

 for example， a linear program。Okay。So， three formulations。But we can have more formulations。

Those are not unique。 You can consider。Different。 So if， if you have。More states， for example。

I suppose youll have more states。4。So you are seeing that the three grows exponentially。

We could remember that I I， I thought that when we are in the nest formulation。

 we are going to consider only the tuor nodes and then the tuor nodes of these and so on。So we can。

 for example， consider。This， using， for example， general formulation is the first one。

For each one of those。And then you consider here， this is a combination of two formulations。

 The first one is only for this is small tree。And then。A dynamic one， when you consider this。

 So in this way， the the， the formulation is is different from the， the three that I。

 the three formulations I have presented。Well， we could think of solving a problem by is it on this three using like。

 okay， I have a decision here。 I send to this note decision。 And for this future， I use solve。

 I could， I would say， okay， if I concentrate on this sub3 sub 3。I have。

 I can apply a multi stage aastic algorithm to solve here， G the decision I sent。

So you are going to solve exactly for the same x of alternative。And then the same thing here。

 our plan to solve exactly。This mo stage toask sub problem。 And here。

And this possibility is not the best possibility， but it's one of those。

 So what I'm going to what I I have shown， I have shown。Is the three men。

Are the three main formulations used in the litator。We are going to discuss more on this in general。

 this is only for the example to be easy。But we are going to consider for each one of those formulation。

 we are going to study an algorithm。Well， so here I'm talking about scenario 3。

 but I have already discussed。

![](img/735d75348d3b6b939c5a37173128ff0f_31.png)

So when you consider another three。So the expectation becomes this probabilities here， just as sum。

 in this case， this will be a linear program problem。Well。

 depending on the number of scenarios we have the number of nodes of the tree。This can be solve the。

At once by commercialmer commercial solve， for example。Well， let me explain here。

So I'm considering this。With this aota 2， is the realization。Of the uncertainty at stage 2。

And this is the probability of reaching that scenario node。Let's start like that。

Let's make it easier。So we have， for example， here the probability of that three。Go。B two，2。飞出完。

And for each node， we have a probability of moving from this node to that node。 So if I call here。So。

 for example， here is the probability of moving to this first node to this first node。Here。

 the probability of moving from this first node and second stage to the second node in the third stage。

If you sum this rubit should be has to be one。So， this is how we。Right。

 here's the probability of the node itself。 And here's the T the the probability of moving from these nodes to another one。

This is how you。We do in a。Reapplication。Questions。



![](img/735d75348d3b6b939c5a37173128ff0f_33.png)

Well。In this example， we are dealing with。

![](img/735d75348d3b6b939c5a37173128ff0f_35.png)

We have three stages。On Friday。We decide the amount of rose are going to sell on Saturday， Saturday。

Well。The flower girl can buy another。Order more roses on the store roses。And we have three stage。

 three periods。And。In this case， the problem is a linear problem problem。Well， three stage。

 three periods。 Each period is one day。 Each stage is one day。So in this case。

 stage is the equal to period。But it's not always like that。We have case。

In which we have multi periods， but only few stages of in which we can make decision。For example。

 you should take advantage of these three。We have one stage。Zu。3。If you make。

 if you continue this three like that。Sas the following。 when we are here。We know the future。

There is no uncertainty。If you want this node， you know the future。So， in this case。Well。

We have four periods。In which you can make decision。

But we have three stage because once you are here， youll know the future。

 you don't need to split unless your problem is so big that you cannot solve from here to the end。

 you have to split。 But well， once you are here， you can just optimize directly using these two nodes。

So this is an example in which we have。4 periods。But only three states。So don't con。 you don'。

 don't make confusion between stage and period。Okay， we can， we can have also。

Mulip period twist stage program。Oh， this is an simplification that we， we can find in。

In many real applications。新为 you。You make a decision today。지 이거 또한。You have to make decisions。

T equal22。

![](img/735d75348d3b6b939c5a37173128ff0f_37.png)

And then， you have。Is future ahead。But。Once you know， once you I。In one of those nodes。

 you know the entire future。Problems of this type you can solve using the same tools of two stage stochastic problems。

 Okay， there is no difference。 The difference is， Im said， there is no difference。

 There is one difference。 The second stage study the problems。

Are bigger because you are not considering only these。The stage here on this period。

 But you are considering the next periods two periods，2。 So your second stage is going to be larger。

 but the same tools you have already studied can apply in this context。

Not in this because you have this opening here。 this uncertainty here in this case。Okay。

 this is just to make sure。To make clear that East stage is not equal to period。



![](img/735d75348d3b6b939c5a37173128ff0f_39.png)

Many periods doesn't give many periods。 don't give us so much difficult about stage， yes。DM2。

Difficult to deal with。Well， I think this is just what I have said。

 The main variables are fish stage， this。Okay。And as always。We are most， more focused on the。

 the variables at the first stage。When you solve a problem in this based on this scenario 3。

Of course， we want to make a decision today。

![](img/735d75348d3b6b939c5a37173128ff0f_41.png)

And we are， we want to use some information about the future。 Some well， you can， you want to。

To take into account then search in the future to make here。

As good as possible decision for the first stage。And。The， the variable that you are most concerned。

 most interested。 are the variables in this first stage。 Main here in some practical publications。

 you have decision of investments。So you want to invest， for example。Let's think of。

Maural gas planninging problem。You want to expand the network of natural gas in a country。

 for example。And they want to。To decide if you are going to。

Construct new pipelines along your country to， to distribute gas。You are going to decide。

 So you have to decide investment on construction， construction of pipelines。 You can。

Decide from where you are going to import gas or some case export natural gas。

And so when we import you， of course， you are going to make to sign a contract for that。

 to have to decide on a contract。 So mainly here the decision we' are going to make today。

 it's more important。 I'm not set， not telling the other decisions here are not important。

But the f is here。In general， So， for example， you are going to decide which pipelines you are going to construct from where you are going to import gas or export gas。

 And once you make this decision when you are here， the other periods。 For example， one year later。

 you have to make another decision。 But when you have to make this decision one year later。

 you have already some pipeline is constructed。 For example。

 you have already your contract of gas and you can plan your network using the decision you made previously。

Okay， for example， in the another example is also， if you decide to construct new。

Power plants for generating power electricity。So， for example， you can decide here when I'm going to。

 to construct new pipeline， a new。Power plants， for example，1 year，2 years，10 years。 I don't know。

 Once you have that， that power plant working， you operate your system using how the structure you have available。

So this， this just to emphasize that the main focus is on the first stage。Well。

What we have seen is this。Okay， here I mean， folks， first stage。

 second stage decision are allowed to adapt to additional information。 Of course。

 you are going to make an information depending on what happened。

And the third stage well are allowed to adapt， to adapt to additional information here， and。

The third stage， when the uncertain， uncertainties are revealed。And in this way。And so on。

 you can have many。St。Hizon time is what， we are going to represent in our course by T。And well。

 on this part of the course， we are going to be focused on the case and the stochastic problems in which T is greater than 2。

So far， you have studied T equal to2 with Hu Paablo and the Clauddia。

St not necessarily Re to time periodss。 Okay， this I have said。

To stay with mood periods or have discussed it。Okay， we have discuss this。

How would be this two stage mode period for this。Examp of the flower girl。Would be the falling。

 She could。 She can order roses on on Friday。And she on Friday。

 she needs to order rose to sell on Saturday and to sell on Sunday。 She cannot order on Saturday。

 for example。So， this is a two stage。Program， but smooth period， because we have Friday。

Saturday and Sunday。But she can decide on Friday。The amount of rose for the two coming days。Okay。

 this is an example of to stage multi the program。So it's easier to deal with this kind of problem。

Her。Okay， before I move on。With。The notation you are going to use in。Along this。Classes， we need to。

To defineine。Just are some definitions。 Most of them have already seen。

From Claudia and from Huanbabu。 So I'm going to pass quickly here because this you already know。

The first one is about a sigma algebra。Well， let's consider a B an arbitrary set。

 So for with this notation we represent all the possible combinations of that set。

 if you have a discrete set with finite many， finitely many elements。

 these is all the possible combinations of that set。S sigma algebra is。Is a subset of this power set。

And the sublima the， the sigma algebrala。Needs to satisfy。These three conditions。 So the。The set。

 the entire set， is a subset。So the sigma algebra is close under complement。

 It means that if you want set in the sig sigma algebra， is complement。 the， the， the。

 its complement is also the sigma algebra。And it under。Councountable unions。 So you have a sequence。

Contable union Con sequence of subsets， if use。The。

 the union of those subsets also belong to the sigma algebra。And， of course。

 this is also true for the intersection， once you remember。That an intersection between two sets。

If you have。1 and2。Yeah。These intersections。Is。Equal to the。Set。The complement。You name。

The complement。A complement of this union。So。Since these， these two sets belong to the sigma algebra。

 the complement to the unionium。Of these two sets belong， belongs to the sigma algebra。

And also the complement。 So we can use here， also the intersection。

From these two definitions we have also that the empath set。Belongs to the sig module。

 because the complement of the entire set。And， well。Yeah。A very simple sigma algebra is， for example。

They one。With two elements。The set and the empty to set。So this is a sigage， for example。Filtration。

 I don't know if you， someone talked about this before。But the idea is simple。If you have， well。

A sequence of sigma algebras on the same set here。 And well。

 the this sigma algebra is a subset of the， the sigma algebra 2 and so on。If satisfy this condition。

 you say that this sequence is a filtration。Futiltration of sma algebra。This is。

 this is will be important among dealing with scenarios 3。Because we can。



![](img/735d75348d3b6b939c5a37173128ff0f_43.png)

Let me show you an example of a filtration。

![](img/735d75348d3b6b939c5a37173128ff0f_45.png)

Using scenario 3， this the definition is more general。Suppose you have these three。

I will say that this is A，B， C。D。This is。至二个弯。E equal to T equal3。I can define。

The sigma algebra at this stage。As。The power set of。ABC。

The other possible combinations here of this set， okay。



![](img/735d75348d3b6b939c5a37173128ff0f_47.png)

We can define。Sigma algebra at stage 2。As the set of descendants of each node。 For example。

 if you focus on this， with focus on this node。The deathsants， the children are AB。They set， A B。

If you focus here， the set is C。We have。The empty set。We have this union。Of course。

 this sigma algebra。Is contained in this one。And because he have all this。All对。Subset。

And we can define， also。A sigm algebra here at the beginning。As。

The empty set all the descendants at this stage。We are here。 Let's look at the last stage。

hich are the desons。 All of them are descendsons of these nodes。So you have empty set。

And all the dissons。IBCD。Oh。We have F1。Con contained an F2。F。So given these three。

 you can construct a filtration。Well， this will be useful for when we deal with algorithms。 Why。

 because we want the decisions we make in each node。To be。Measurable。To be。

Consistentent with thefililtration， for example， the decision we make at this node。

But if this happens。The decision here has to be the same decision we make here。And when you。

 you are going to， to use this saying that decision you make for this path is the same decision here that for this path。

We are somehow dealing with futuretrations。 This will be。Cl， when you are going to study algorithms。

呃。Okay， so the elementary elements of each sigma algebra as subset of this given set in our example here。

The given set。Is just。8。See。D。Well， we can define also。I guess。



![](img/735d75348d3b6b939c5a37173128ff0f_49.png)

This was already。Explaining this course。We can define a sigma algebra generated by a function。

 You can say there here a function between two measurable spaces。

 We have two measurable spaces F this this calligraphal F is a sigma algebra of this set。

 Carigraphal G is the sigma algebra of omega。And we have a function， X。To this set， to the other one。

So why I use X。Because our decisions in a multit program。We are going to use x for that function。

 for those functions。The ver， the decision variables， in fact， are function of the uncertainty。Well。

 we are going to define the sigmas were generated by this function S X。

 thennoted by sigma X and using this。EDefinition。So， here。All the collection of the subsets。

Events that when you apply the function X。To the set， you arrive in this sigma algebra。

it's written here。I保。Well， how can I can explain this better？ Let me see。啊 you should have。

A scenario 3， like that。I always use another3， because it's easier。To stage。So。Here。

 we want to make a decision X 1。 here， we want to make a decision X 2， we have。这是哪律是？This scenario。

 I will call it acito。This side 3。So I want to make a decision X1。I want to make a decision。X2。

That depends on an uncertainty。So， for the first uncertain。For the first scenario， sorry。Here。

 for the second。是哪了。Stage3。Okay， x1， decision we make here。 X 2 decision make the second stage。

If you are concerned with this is small scenario 3。

 we want to make the same decision here in this node。 So what you are going to do is the form。

The decision we make for the first stage for scenario 1 has to be the same decision we' are going to make。

Considering scenario 2。And here we don't know。 it it can be anything。

 You can make a different decision here， okay。But let's suppose let's focus on this function， X 1。So。

 the inverse of this function。Of a value a， for example。Is equal to。Empple set。If。For example。呃。X1。

I think I should write。Here。意思。X 1。The first scenario。Is different。No。The first case。This will be。

是哪种啊？S哪的 two。If x1 is equal。读。一光。2 a。And。Ampt。Otherwise。So， when you have。



![](img/735d75348d3b6b939c5a37173128ff0f_51.png)

You make a decision here for these two scenarios。 the value you obtain here is exactly the same you obtain here。

So the inverse of this function。 Okay， one here。Well。

 for this value is equal to the two scenarios if。This satisfied。

If x1 for scenario 1 is different from this。So， we don't have。

Any scenario in which you can have different decisions here。So this is an example of this function。

Our function is measurable。If。With respect to the sigma algebra。F。If the this set。

Is the element of the sigma， which。And to say that the function is immeasurable。

I'm going to use this notation， okay。So everything you see， every time you see this notation。

 I want to say that this function is measurable with respect， respect to the sigma module。

 that's sigma module。Okay， here's just probability function。

 It's called a measure on that measurable space。

![](img/735d75348d3b6b939c5a37173128ff0f_53.png)

If you get every collection。Of subset， this joint， this joint the joint subset。

And if the probability， if the， the measure of the union is the sum。Of the measure of each set。Well。

 you call this measure a probability。 If the， if you apply the measure on the entire set。

 this is value。 this， the value is one。So a measurable space， when you have a set sigma algebraable。

 and also you add probability measuring。 we call this space。

Probaability space filtered probability space。So this will already have seen。Other is definitions。

A measurable functionci from a probability space。呃。Okay。

 from this probability space to R is called a random of variable。 But if the image is another subset。

 more than one， you call it a round of vector。Okay， this is where seen。We need some definitions here。

Well， okay， we view the， the sequence of thistoaut process。Of these random vectors。

 this is the stock stochastic process。You're going to call Psi。So the。

 the stock has process a sequence of vectors with a specific probability distribution。

This notation is going to be very useful。So when I'm talking about。

I stage T or a specific node of scenario 3， for example。I'm going to use。

Or the random vector of stage T is this。But when I， I write。Like that。It's because I meaning。

I am meaning。The history up to stage。D。Okay， if you are this the three。So， if I consider。For example。

 this。Beth。I' you call it。X。3。1，2，3。He that this is the notation。 Ill the。

The history up to this stage。What are going to call a scenario。Okay。

 here I use it for the function X。The same idea。But I was explaining to say， but same idea。

So for scenario， one scenario， what I mean by a scenario is。Exite of。

Is the whole path from the rotten node up to the live node。For example， this is。A similar。Okay。

All the path。What other definition， the stock has process is stagewise independent。

That's also useful for some algorithms。 Some algorithms are based on this assumption。

Is the fact that。

![](img/735d75348d3b6b939c5a37173128ff0f_55.png)

The probability。Of arriving here， this node。May depend。On this history。Or not。

 there are a case in the de that are to arrive here。For example， we have this probability one。

Probability 2。1，1。网突。Cause this is one。This。P1， B21。So in this case， if。P 11 is equal to。Bi。And this。

We are saying that the stage is the， the stockas process is stagewise independent。

It doesn't matter which node you are When you move to one node。

 this the probability here is the same here。For example， you have if you have。High and low demand。

 High and low demand。 The fact to arrive in a。High demand in this stage is the same probability that if you come from a high demand or from a low demand。

So there are case in which this makes sense。Not always。For example， if you consider it。

If you throw a coin。And you are going to。To register if it's a tail， tail or head， so。

It's independent what happened in the past， What's going to happen in the future。

And the probability is the same。m sorry probability is the same。

 So this is what I mean by stagewise independent。Well。

 I'm going to use this notation for multi stage stochastic。Most stage schastic programs。 T is the。

Time horizon。We can see our decision variables as a function of the history。

And this is another stochastic process。 We have this s stochastic process。

 kssai and another one that depends on this kssai。Well， and if you consider not a scenario 3。

 but a continuous toas process this X is， in fact。A function that belongs to appropriate function of space。

Scenar 3。We have been talking about this。Since the beginning。 but like， let's make some。

So I wanted to， to present you some other definitions that。



![](img/735d75348d3b6b939c5a37173128ff0f_57.png)

Are going to be useful。So， let's assume that we have。K realizationizations， K scenarios。

 In this case， we have four scenarios。Once another is this。Another one， that 4。啊。哦。

Let come back here。Well， we are going to assume that each scenario。This is an number one。是哪里种？Its93。

Sar 4， again， all the。The bath。Each scenario are going to assume that it has a probability。Be one。ビト。

Before。We are going to use。2。We are going to use this notation for the set of nodes at each stage。

 which is Oomega。So I think I should give names here。



![](img/735d75348d3b6b939c5a37173128ff0f_59.png)

ABC。D。嗯。Yes。🤢，G。So if you consider the set of nodes， the first stage。Is just。A。Set off an olds。

The second stage is。V and C。And D， E， F， and G for the third stage。The total number of scenarios is。

 of course， the number of nodes we have at the last stage。Well， here。

 I saying that we can call a node of the， the， the， the three。At this stage， well get a scenario。

And when you focus at this stage， a given stage， we have a node。 for example， choose one scenario。3。

 if you focus on the second stage， we have this node， C。

Sometimes you call it the scenario at this stage。 sometimes just call it by a index。So it。

Has a unique note。Each scenario side has a unique node at this stage for a given stage。 Of course。

 we have a unique node。Ancestor of an node， we are going to use this notation， this a。So。

 for example。What is the ancestor， A， I could not use here as a。2。So， for example， if I get node E。

The ancestor of nodede E。The father。Is B。This is going to be a useful notation。

 So the notation for a multita stock has program。Is a bit hard so many things。

 So I advise you to start this， this notation。Because it's a bit confusing。I mean。

Once you understand， it's not confused， confusing。 But at the first glance， yes。呃。

The set of descendants， we are going to call children， and we are going to represent this set by C。

Of course， depends on the node。For example， in this case， the set of children。Often node B。Is。7第一。

Of course。This set of notess。Is the collection of all the children of the node， the past。

This is what I'm representing here。Of course， the last node， we call this live。对。They leave notes。

 They don't have children。And this root node doesn't have ator。Leave notes。Well， here。

 how do you compute， We call the probabilities for the probability of a given scenario， a given node。

 we are going to use this notation。And。Well， if you get all this the。

 the set of all scenarios passing by a node。This case， this scenario， this scenario。

 and you sum the probability of those two， these two scenarios。

 you have the probability of this node。 What's written here。

And we have here the con conditional probability， of course， to reaching this node。

 given that you are here， you have a probability of from， from moving to this node to that one。

We call these from the ancestor nodes to the node you are interested。 So conditional probability。

 can write like that。And the probability of。A scenario， for example， here。

 P1 is the probability from moving to this node to that。Notode B to node D。

So if you make the product， you have the probability of this scenario。That's just simple。Well。

 some more definitions。嗯。I， I， I thought， I have read。Yeah。

 have already discussed what is stage wise independent。But this doesn't depend on the the history。

And。Under this assumption， as scenario another tree like that。For example， in this case。

 we have common samples in the sense that this black and old。Has four children。four different colors。

And those children are also children from of of this grey node。So those are the same values。

So you can just compress this three。 You have the other one。

 This is a compact form to to represent the three。 That's an assumption for some stochastic programs。

 We use these。 This， for example， case of。Many power system problems， planning。

 power system planning problems。To use this assumption。So you can compact the tree。

 You have less nodes to visit when we are making our optimization that we have to visit nodes。

 We have less nodes to visit here。 So in this case。

 it' more efficient about the presentation of a stock cast process。 Well， this is another thing。

I'm not expert on that。But depend on the， this， the， that the size of these three。

 We have a good representation， of course， and we have a good model to generate scenarios。

Another different。Another definition is about is this one of Markov of Chang。The fact that。

The probability of a node， given that you are here。Doesn't depend on this history。

So a probability of having a white node in this last stage doesn't depend on this path path is the same probability then here。

No， no， no， sorry。 That's stagewise。 It depends on only the last one。 So we have a history。

You have a history。But， in fact。Giveniv this history。Doesn't impact the much。The probability。

 what's important only。The， the ancestor note。Okay。So， it doesn't matter。

Probil of arriving on a white node here depends on the probability of having this grey node。

Not in this path。 For example， the probability of arriving is node white and these one。

Is the same because we have a gray and gray here。Although the history is different。This case is。

Microov Ch。Okay， with this， we have。

![](img/735d75348d3b6b939c5a37173128ff0f_61.png)

We have seen the definitions we are going to use。Along the。The coming weeks。For the scenario 3。

 So I advise you to take a close look of those definitions again。And， well， we can now state。

The problem， the mood stage stock program。In a more general form。So， that's。Well。

 that this is the nestda formulation。That you are already have already seen。

But we saw for the example of the flower girl。 Here is a general  one。Let me explain。Well。

 the function。In each state。We have a function。 So here we are considering the problem of minimizing。

 We have if。Each stage。So we can think of those functions as a cost function。For each stage。

 we have a。You can have the same cost function。 have， you can have different cost functions。

 What is interesting also is the fact that the dimension of the decision。

 decisions can be different along the stage。Doesn't mean that the。

 the dimension of x 1 is the same the dimension of x 2， not necessarily。

So the functions can be different。The first stage， our function doesn't depend on the uncertainty。

 Of course， we are on the first stage we know the reality。

 We know the all the uncertain parameters we don't know for the future。

 So we take into account the uncertainties here in this cost function。嗯。And also。

 the searches appear。The feasible set。And so on。 And you have here the this nest formulation。

The function。Depends on the x。Anti。Dmenia n and the this function depends on also on the。

 the run variable。Has this dimension。Dity。And we assume that the image is R can be R plus infinity。2。

So we assume that those functions are continuous。Aceent decision variables。Well， this set。

This is the feasible set。 Depend on the， the decision you made in the previous node。

And the uncertainty of that stage。 one example， for example， if you， if you deal with。里年。

Mood stage stock linear program。Problems， you have， we have this。Each function。FD。X D。City。Is。

 in fact。A function C。T。Can depend This function。 can depend on that scenario。This is a vector。

 I'm assuming this is a vector。Transpose。The decision variable。So let's， let's assume one thing。

That can see my random vector。Comprehend uncertainties in the vector。Of course。Some mattress。

It and demand。Okay， and this case， I can erase。 and it's simplyly say that this vector depends on uncertainty。

 okay。And。This feasible set。That depends on the decision we made in the past。



![](img/735d75348d3b6b939c5a37173128ff0f_63.png)

And depends on the current the the realizationization。At the stage team。Could be， for example。

 this is a case。Could be。Ma T， that depends on the decision， Imagine the past。

Have this decision P here。Plus。等击。X D。And you have a demand。Okay， in fact。This is。The act。

60 satisfying。This。Stister。So when the all the functions are linear。

So this mapping defines this set linear。We have。To cold。Mood stage。tochastic。给你啊。Program。

So this is an example。But does it need to be linear。When it's linear。Is the， is this the case。

It's very tough to solve this kind of problem。 very difficult。Well。

When I say that this mapping is measurable。It's because I'm。

I may assume that this map takes into account the nodes of the tree。 If you are considering a tree。

 for example。The feasible set we are going to define for this node。

Will depend on the decision we made here， the ancestor and the realization of the around process here。

Okay， so this is what I mean by measurable in this practical。The practical terms is this。Well。

 this is the NA formulation。But when I， I presented the flower girl problem， I use it here。

 conditional expectation。Well， in fact， F if you look at the， the book the。The book we are falling。

This is the notation。Well， but in fact， what it's meant there。Is the probability。

 the conditional expectation， because you are focused on that node。 if you think of43。

 a node and what the children node。 So it makes more sense to me to considering this。

 But the notation for this class of problems is really difficult。So when I was studying this book。

 I thought， well， it must have an another way to consider， to represent。This problem is。And well。

 after thinking。I say。I realized that， yes， we can use a simple notation。 However。

 we're not going to represent all the possibilities for the problem。 If you use user notation。

 it's like a particular case， we are making implicit assumption of the problem。 And the， well。

 I think the best way to， to， to use to， to proceed is to use the notation of the book。Okay。

 here we can consider all have the data assumptions。Make sure when it's stageized， independent。

 when it's a Markov or not。So， of course， when it's staized independent。

 we are going to see the notation as much simpler。 There's a notation we can find some papers but relate to a specific problem。

 for example。啊。Well。See， for example， I was talking about a difficult notation。 That's the case。



![](img/735d75348d3b6b939c5a37173128ff0f_65.png)

But。This， if you， if you， we go back and look at the flower grow problem。

 we will see that this is the same structure。 It's like we move to the， the lymph node of a tree。



![](img/735d75348d3b6b939c5a37173128ff0f_67.png)

And we make an optimization for each node。 and optimization we make here depends on the decision we made in the ancestor and the realization。

optimizationptim we make the leaf nodes depend on the decision， ancestor and realization。In fact。

 here， Im not only the aization C， brackets， because I mean how the path， how the scenario。

If you use someone， if you assume。Statiateized independent。 We can remove these blankets。

 for example。Okay。So for each one of those nodes， you can define this。Optimization problem。

Then for other states， we have this function that we call it cost to go function for， for each state。

Stage， sorry， for it。 Each stage。 you always depend on the decision we made in the past。

 the previous note and the， the history。And here， the problem is to minimize the cost at that stage。

 plus the future cost。But like， the future cost with the site in the previous。Step here。And so on。

 you go， you do this for all the states， all the， the， the histories here， the， the。

 the nodes of the tree， if are considering a tree。Up till you arrive this。The stage 1。

You want to find first stage decision。Minimizing the cost of today， plus the future cost。So。

 this is the。Dynamic problem formulation。Well， this the feasible set， I have already explained it。

The to go function。 Yeah， as I told you。There is another different notation here。

I use this calligraphal queue when I take the expectation。It's like， I have a queue here。

 another one here。 But when I。Take the expectation。I have that different calligraph coq。

The expectation， depending on the history here。And so this， this， this is called a re function。Wo。

If you think in the two stage case。티 equal equal22。This part disappears。 who have on the nodes leaf。

And the first one here。 So already， youre already know how to deal with。



![](img/735d75348d3b6b939c5a37173128ff0f_69.png)

The difference here， you have intermediate states。And this makes all the different makes comp This give providers some。

Complications when you are writing algorithms。Okay， this is just the cost to go function。So I。

 I will stop here。

![](img/735d75348d3b6b939c5a37173128ff0f_71.png)

Well， and next。Actuallyction I know。 Thursday is the exam。Okay， so。See you on Thursday。



![](img/735d75348d3b6b939c5a37173128ff0f_73.png)