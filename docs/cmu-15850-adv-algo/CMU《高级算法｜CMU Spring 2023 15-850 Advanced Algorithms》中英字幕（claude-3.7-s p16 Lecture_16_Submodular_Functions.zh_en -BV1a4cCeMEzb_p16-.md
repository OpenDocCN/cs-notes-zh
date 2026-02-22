# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p16 Lecture_16_Submodular_Functions.zh_en -BV1a4cCeMEzb_p16-

I guess we'll get started。So we have seen certain commin optimization problems。啊，来。Max matching。

 min matching， min spaning trays。Max cut， Min cutt， and。You know， setは。And so on。

 So these are some of the comminal automation problems we generally are interested in and。

So what is a communal optimization problem in general？Very generically， I can write it as。Minor max。

iphone fans。Such that， I is in some。Combinator and family， some set of feasible solutions。哎，稍到。

You can think of you as the ground set of edges in a graph and a face。subsetubet of these edges and。

A special subset of it just they can be either。呃 three。Or a cut。呃，高温还没。Yeah。按照。

It can be many objects， but very generallyally， this is what。

The form of a combinatal optimization problem is right so。Have we observed that till now。

 we are only optimizing linear objectives in the sense。I take a tree。

 I give weights to each edge and the cost of my tree is just some of them。So， what I'm saying is。

Here is a class of cost functions。呃。There is a weight function from the elements to。The real and。

Really， the cost of your set is chest。那。Its says this linear sum of which。哎。So。In other words。

 if you are taking a new edge， you already selected a bunch of edges and you are selecting a new edge。

😊，The contribution to the cost。Or the increase in cost when I add this edge。Do say galaxy of。I mean。

 same Im I'm iteratively forming a tree and I'm adding edges。 So the new or increase in cost is just。

😊，F of S plus。E minusF of。And this is the same regardless of what I is。😊，Yeah。Right， so。嗯。

This is what we have till love。So， functions of this。

Functions that satisfy property are called linear or modular。

So can you see that these two are equivalent？Well not exactly， but。

Can you show that if a function satisfies this， then it really has to be of this form。嗯。

It's pretty obvious， right？呃。Can anyone just tell me how？是。

I suppose you could just define the weight of an edge to be the。Apple。

And he said that doesn't include the edge。What might。Yeah so有 saying嗯。Just some fix some set。这新来第。

P that doesn have find the way to be at the best right So you take an element and this quantity。

Is the same regardless of what absentee just lets just call it W E That is what you saying right and then。

I'll just use this。 and you know。Yeah。Yes。I mean， once I have this。

 I can just keep using that for F of S and then I'll keep extracting W Es。😊，And finally， really。

 what I'm improving is F of S minus F of the。😊，MP set some。So up to a constant shift。ベトは一個。So， yeah。

So， given that this is modular， this is the definition of what a modular function is。😊。

What's someone。在对。Yeah。好意。嗯。really not sure I have a sense of why it's the case。

 but I'm really not sure。By history of what， what does modelular mean。Not exactly clear at the。

 but yeah。But anyway， so I'll tell you what some functions are。Say you go to a a grocery shop。

 you do some shopping so say you go to giant table and you are scanning these items。

Did you observe that you have scanned some items and you scanned new items？

You see that the price drops a lot。上等。Like， say， say the price of chocolate bar is like。

 I don't know，$2 or something like that。 I don't know。When you scan it。

 you get credit sometimes goes it drops by 50 cents or something like that。😊，So I mean， this。

 this is discount， right， if you already buy some stuff， the cost， the marginal cost of an item drop。

That's a。 That's how market works。If you buy more， if you just add one more item to your car。

The cost is not exactly the cost of the item itself。 it's a bit less。So， then。

So what I'm saying is let's define a marginal cost of an item J。😊，Given that you already bought us。

Is this， right。And it only makes sense when j is not in s， well if it's in s is 0， but。

We only talk about， I mean， we only write that generally when this is not in mess。

That's a definition。受。Let's formalize what I just said。If you buy more， you pay less。

Or the marginal cost drops。If you're buying more。What I'm saying is。The marginal cost of S。

Its only less。啊。Maybe， let's see use A and B。If be the superstarter。零。That makes sense， right？

I just abstracted out the property of。Orisees of items。万68。This makes sense， and it's true。

Where F of S is the cost of items as。And this。你car。Some more later。If is equal is modular。😊。

With less， it's a model。You get a discount at sub model， sub less。O。那这他 mean。That's just。

The abstraction， we need to get we get so much power just from this abstraction functions that satisfy this。

They are amazing， we'll see。Also， the O， So this is one definition。Yeah。嗯。Turns out equivalent。

 you can simply say。Any C And。The value of C union D and see intersection D。

 if you add them is less than the values of c and D come。And these two are equivalenting。

You can try to prove it， but it is not important， but both of these are very powerful。

 we tend to switch between them。😊，Based on what's useful。あら applicationな。O。Oh。

So what are some examples of submoar functions？So yeah， that's that's the definition。

 Maybe I'll move。So can you tell me some examples of someone。I mean， we just， we just。

Look at prices of items in the market。 That' one。Equality is an inequality。Yeah。嗯。Yeah。现在。

You said other。And you said have to be like some of the weights did the。这为。嗯。这样会。

So we will get to the mat rank function but。I still don't understand what you're saying。

So S is a bunch of elements， what of s。Its some of the。位置。Of individual if it's， if it's an magic。

 otherwise。哦。给你的此。I'm not sure that。啥网。So， it is not a basis。

 if it is not independent the weight is 0， if it is independent it just a sum。Yeah。

I don't think it's a， but we'll check。按那个。This is trivial。Because we just have equality there。

 instead of an equal。SoWhat's the second example？Sa一个多不分。

And you have a calorie budget I mean you like each item the amount you like an item is the number of caloriess。

 but you can only eat so much。😊，So， after a point of reading some your your marginal value to any item is says0。

 I don't care handful。So what I'm saying is。It's just a linear function， but I add a cap。

Why this subor。Yes， let's try to use the definition， I guess。I mean， regardless of the cap。

 if you a a lot， you will value item less。真不。And the value could just be its its value at 0 based on whether you already crossed the budget or not。

That's。是他张某人。嗯。困了。So what's the coverage function。I have a。Room of people。People are elements。

And each person is in some community， right， mean what the community is。I say it's a set of people。

There are several communities。Our clubs。These are people。That sets are communities。If I pick。

A representative。The representative。It represents some communities。So I'm just saying hitting set。

I pick a person that belong to some sets that represent those communities。If I select。More people。

 they all represent some communities。Forly， what I'm saying is above hedge is。

The number of communities you represent in the sense， these are the sets。S oneS。あさ。

The number of communities that。2的。Eating set language the number of sets you hit。

Hch is the subset of elements。Why is the sub。Yeah。Whenever we ask， why is something submodular。

 we should look at the first definition。Try to justify that。This diminishing returns。Probably。

还在 yeah。So， I'm collecting people。I'm adding a new person。

The number of additional communities they can represent or the number of additional sets they can hit only gets smaller if I already have。

If I have a super set of people， it can only reduce right the number of extra sets I can hit。

That's it。这他怎磨的。反 then呢。The major rain function。So what。We know what the metro rank function is。

 given a mettro dam。Down set you and independent set。Set off in independence。Rannk of a subset。

 Why is just the。Maximum size subject。Oh。That's the rank function， right？If I give you a set。

Was a maximum size of an independent set that's inside it。It is a model。And that's in homework too。

 right？Yeah， we saw whys someone more learning。And we proved exactly that， right。😊，嗯。

But if I remember the statement is something like。Rannk of B union E。I'll just be blessed。

It's intuitive to why that's true。Say I have B， and I'm adding E if the rank increases。

Then I can say that the rank also increases when I add it to a。That's how the proof goes， roughly。

 right。I mean， these are either zeros or ones it services to prove that if this is one。

 then it implies this is one。That's all you need to prove to prove that。And yeah， we know why it's。

那在那个什么方。嗯。And the last example， these are a lot of examples。确实。安道费。What what do I mean by entro？

Say you have a random variable X。It takes values in the alphabet。呃，m KX嗯。

And it's distributed according to this function。So what's the entropy F。Yeah。Yeah。That's。

 that's that。So where is our what's our function， what's F of us。

Is the say you have several random variables。X1 x2 of pi x n， you have N random variables。

And Ifacees the joint entropy of all the。The joint random variable are all the random variables in S。

X I。系呀。Why is this sub model？你马。不在发生问题。Entropy is not modelular。 no， I mean。So， it's not true that。

Enthroppy of x and y。你不道比较在。比较快。That's not true， right。It's actually less than the sum。好。

Entropy is sub additive。actually。And the subra is called mutual information。外的。

So have you heard of conditional entropy right？Unless define it anyway。

Entro of x and y minus enopia of y。Uses the joint conditional entropy。我。And。

And that's a marginal rate， marginal of x given y。Yeah。I don't understand。Oh， I see so。

When you can take two random variables， they can be correlated or independent。

You can treat them together as a random variable， right。So x has domain x and maybe y has domain。

Scrip boy and， and。You can define the random variable Xma y that' is distributed in。So you write。

Ex I there， those are。をする什么。Yes。But他。你的是。And your have of Ana like。

Exactly really the entropy just needs the values of the probabilities。😊，But I don't yeah， I mean。

 I also dont understand this isn't just modular。 Give add another point。Okay， okay， okay。

 I guess I guess it's it's it's。Confusing。 So O， let's take two points。Let's say both are fair。

Whats the entropy of that？Of a single gra。It's minus half log half plus minus half log half。

 it's one。There's one bit of entropy in each other。We call this con X， this con white。

What if these coins are untangled， they are not independent。

What are these kind give this coin is going to give that。That grown somehow。Whats a giant intro。走。

Ha scales， head scales。 This is x。 This is y。嗯。This is a giant distribution。If access heads。

 y is going to be heads。If taxi stands y is going to potential this this sentence are 0。

So whats the entropy of this guy this？The coins together。It's still one。

Can you just explain how that relates？And I know I've heard of this in people， but I just don't。

So you don't understand the notation the way I wrote。F of1 is enthtropy of x。呃对会审表会。耳环科密度。单车表。

It just ever versus the joint entropy of random variables。Indexed by elements in。

And X is just the same。I， not。This。Yeah， like P is the same as。 Those are just like a problem。Yeah。

 P is the probability function mapping like。This is really the head centers。NBC是。Yeah。So。

 I guess it it is clear entropy is not modular and it is clear what I mean by F ofs it is a giant entropy of all the random variables indexed by us。

😊，OK。And that's a murderlet。Okay， I guess I guess let's not， let's not get into that but。

It's not hard to prove。Anywayyway。Observe one thing。In all these examples。

We had one more property that we don't need。If I take more， I get more。对。等。Linear function。

 I imagine the weights are positive if I take more， the cost is more。😊，Budgeted。 I eat more。

 Im more fulfill。Our X I tech more people like our more communities。😊。

Mter rank function yet I increase B， the rank is only going to increase。

Or maybe better than say non decrease。It may not increase。Antropy， it's increasing。So， we had。

F of B is at least F of a。毕业收不收到。We dont need this in these examples this is satisfied and this is called a monitor property。

😊，And any function that satisfies this is called a monoton function。

And these are examples of monotons of modular functions。There are non monitor sub functions。Examples。

I'll just take any function with。You know， always decreasing slope like a negative。

Minus F of S or F of S monitor， that's what youre saying。上人。No， no， that being never someone。

Function could be like this。Its a scalr to a scalar。 And then。You take the number of elements。

And then you apply this function。带不走。He could say， okay。Given a subset of acts， just。

How many elements are then apply the Scalar function app？But always decreasing stop。

You're saying a of us。Is G of modest。This is some con cave function。

 but that's really what it saying。O。Is it submodlar， I am not sure I think it is。

 but it is not monitor。If Im taking more， these as is increasing。Its it's a con function。

 so it can reduce。But we need to verify that it。Submon， it is。But， yeah， that's an example。嗯嗯。Well。

 the intuition is concare functions capture the notion of diminishing returns， right。

Let's imagine this。Actually， I'm not sure if it's a， but。Gca functions are useful。If I move1 meter。

 my height increases is so much， but if I move again， it doesn't increase as much。

It captures the notion of diminishing returns。 So sub functions can be related to concavity。

 They have aspects of concavity what。LetLet's give an example。Graph cuts。

WhatWhat's the gut function office this。I's the number of edges。UV设计袋。U belongs to us。

 and we does not belong。In other words， it's just。And the b。It's the number of outgoing interests。

The biggests a model。It's not monotone。I pick all of them， my cut value is 0。What is of wonder？

Whether it's directed undirected doesn't matter。不意思。It's a little hard to see。But。

Let's define an even periitive function like this。F， of S is one。一。

S UV of S is one if U belongs to S， V does not belong to。0什么意思？

A as doesnt care it just looks at a particular edge if this had is crossing I will say 1。😊。

W's not El 0。Is this a modellar。喂。是。What。It does， but。Like， yeah。

 the intentiontuition is that if you include more， you can only hurt yourself by including both you and we。

More or less， like say your one initially， you have you and you don't have the。

But any superet you take。It can only be1 again or 0。Because now you included V as well。

That's the thats thats you can see diminishing returns there。As youre increasing。

 you can go from 0 to1 fine but。I mean， when you're writing a new element。

Your chances of going from 0 to one is better。If you're a small as。

Is it possible that this is where Richard should be using。definition。耳朵。进个就买了。

I think you can use that。啊。Let's not worry about it。 but it's pretty clear that。This is submal。

This has diminishing returns。 The cut value can。You can hurt yourself by having more that at least says that it is not monotone。

 but anyway， this this is sub modeler。😊，We are convinced。Isn't it just some of those guys。

What在 office佛。Glame。In each of those counts， if UV is cut。In the sum what all。好的。安代く。So yeah。

If this is true， and。Adding subar functions。if theres a closure with respect to tradition。

For some modity。Then we are done right。That proofs of the graph cut is someone。If F submodular。

G submar。F plus Z is some。一人关。Use a definition。Slab G here had just add them。Very have。没。

So this is ala。 This is sumation so。That function of。And it's not monitor。

Will not cover more examples。 So that that's that's good。

So there is another property we call symmetry。Say the graph is undirected。😊。

And my cut function is the under cut。So number of Hs UV are that either U is in S and v is not or v is in S and U not。

哎。那找了什么了？We can prove it like that。And it's symmetric， right？😊，Right。

 if it's undirected cut case the cut value， whether I take these vers or these vers。

The crossssing is just all the same。And this property is called symmetric。嗯。Yeah。So。

One example of sesymmetrictic function is undirected graph cut， but。

Can a function be monitor andsymmetric？Sero cost。Proof， it's easy， but。

Proves that a symmetric monoton function is constant。I第 equal。上来。This is from symmetry。

 and this is from monoton and they equal。O。From monoity， and these are equal。那次。

So whenever we are talking about monitor， we don't see。

We don't even talk about symmetry bird because it's boring。Anyway， also。

 all these functions are positive or non negative， right？We are generally only interested in in that。

If it's monitor at on。If I face monoone。V 96 value is 0。P is not monoton。

With the self of as noinated。应有可能。So， symmetry function being symmetric is just a property。😊。

It could apply to a submod function submod function could be submitted。

In which case we call it a symmetric subder function。😊。

And one example is the underwritingwritten graph。And monitor property is a general property for any set function。

submodal function could be monitor。 in which case， we call it monoone submodal function。OK。So。

 that is examples and there are some closure properties we just saw that addition is a closure。

 in fact， any non negative linear combination。Is F plus 2 g， you know。

We just get that from the definition。And this is a closure， right？😊，GFSSFFS8。I flipped the function。

I that。If I face some does yeast is some。嗯。就是。Re clear。你发译。Yeah。And then I read the as。唔知啊。是全。

And Ill set C complement and D complement to CM。那那他谁那电啊，也就说。

So those are some closure properties and some examples of monotone non monoone。

Now well get to optimization。不用按摩。Okay。First of all， before asking this。How do I know the function。

 how do I have access？How do I know FFS？So if a function is linear。

 I just need to know the values of the single element， single tons。那这。

AComp way to represent a linear function。If I ask what for first， I can just go and add them。

What if it submodler。It need not have such a。Compact representation。

The representation is just all the values of our。So， before even asked this。

 we need to talk about how do we have access to F ofs？That's the value orac model。SoThere's a box。

You ask， what's the value of a professors， It gives you value of a professor。可以。

Let us assume this and what our measure of our notion of time is how many times are you asking it？

I mean， I can ask it all the sets and then I have my function。 I' will just speak the best。😊，Clearly。

 you need to ask。As less questions as you can。And's all this。受。What if I face monoton。

Why do I do I yeah。And just take。Every。Thats monitor， I don't even ask a question I say the universe。

😊，是。Let's consider the case when I face monoron。If I just say this， then I just。

 I'm not doing anything。 So I need to say。Give me a set with utmost k elements。Now would makes sense。

I， the question makes sense。Whats the哪。What if a face modular。That's talk some。What do we do。

就是这个也要玩直。Yeah was。Yeah， bigger elements， right。So we ask and find out the values of all the singletons and then just show the best K ones。

 thats it。It modeler that sees it。Have we heard of the。Max cake our problem。It's， it's。

Is this setting you need to pick。Kay people and cover as many communities as you can。

 hit as many sets as you can。This is an instance of that。And max K cover is NPp heard。是。是是。

I just said that to let you know that， okay， Im not asking to I am not looking to find the optimal answer。

Yougan。There's any approximation algorithm。Whenever we think about algorithms。

 I mean you want to design an algorithm， what's the first。Easy attack。对哦。

What would be a great deal them。I mean， the algorithm we used for when it is modularry is green。😊。

On the way you say it。Might be easy to generalize or not。Let's。

 let's think of a greedy algorithm there。There are a bunch of people， a bunch of fe like。

You want to select gay people to cover the most communities it most sets what do we do。

What a greed algorithm there。Yeah。Yeah。I couldn't。我合。好时。Yeah， we can do that。

 but you are picking so that you are covering the most of uncross communities， right。Yeah， so。

So ready algorithm에 있어。I pick a person who covers the most communities in the first step。

I cross off those communities。没能来搞。Then the person is here。Now。

 I have to find a new person that will cover the。Most new communities， I mean。

 if they are covering communities that are already covered， they're useless， right。

I'm looking for a person that's covering。默认。Uned。So the greedy algorithm is initially as is empty。

一 is。Max。嗯。Is in U minus S。Okay。So what， what's the。What do we mean by。So。

 when we pick the first person it the value of them is the value they are bringing to me is the number of sets they are hitting。

😊，After that， my value of the second person is the。😊，Marginal value。

Or the number of additional sets they are hitting。And that's， thats this right。

 it's basically if you already have this， the value of e is the marginal value。

And I'm picking the guy with the best model。那知道。So when k is 1。What can we say。No。

 like what's the is it optimal， I it， what's approximately。If there is only one one， I mean。

 we are only looking for one set then we can just find them。And this algorithm will find that。

Like the first element is just top。When case 1 is up。What happens when case 2。嗯。

So I'm going to show an analysis of that。And I'm going to show this。In generals。

So let's analyze that algorithm for cover max K cover。

And this problem is called max K cover when F is the cover。Okay。答得乜。Two sets are these。

So the first set I pick。Can I say that it covers。How much can I say that it covers in comparison to the optimal guys。

So these two are the optimal pair， but I pick someone。That covers the most。那是不是。

But have to it covers at least half of the。你。Because。One of these guys cover atist half。

Of the total amount the they cover together。So the maximum coverage edge guy。

Will be at least stopped by two。你找那里。アバ。So， really， I am left with。I I'm waiting to cover half up。

What happens when I select the second。走。I picked one guy and I am sure yeah is they are covering at least half the number of they are hitting at least the half the number of seats that the optimal pair。

😊，It's already got half of the money。I'm left to cover up by tomorrow more。

And when I select a new second person。How much can I say that they cover now？At least half more。Well。

 less than half， because I guess that's a definition of opt。I mean， yeah， that's true。

Anyone else should cover at most of by。If if。Given this person is already carrying out by two。

 this person can't car more than then。They have to be。Sure， but。That's an upper bond。

 but I need a lower bond。嗯。Can I say a by4。我闭。对。This guy is on quarter。不说。这个法外。跟说一。嗯。Yeah， yeah， you。

But yeah， it isn't。Is at most I Yeah， that's true。 That's true。Yeah。

 let's imagine that the first person covers exactly out by two。

 Then its true that I will cover at least out by four。😊，喂。I look at the uncovered part。

Like the part of the optimum that the first person didnt cover。

If this is exactly out by then that's at least。U。And they do together cover at least that much。😊。

So one of them should cover at least half by four。So and more generally you don't need to assume that this guy is at least。

U外度。Overall， you can say the first greedy person and the second greedy person take over at least three folds。

😊，generaleneral claim。代理的发言暂停。Uncover of peace。Yeah。A or minus half。这。

Let ST be the set after time tea。Initially， as0 is empty set。S T is the set after time sub。O。

And by f of S， I mean the value or the number of sets they hit elements in S。😊。

And F of O O is optimal solution。An uncover of teeth。This blue shaded region。In my head。

Is the number of elements。That opt covered what I didn't。Poughly， not exactly， but。

This is a lower bone。Glame。Okay。After one step。The number of， so what happened here。

After taking one guy。My uncover is at most half1 gave to。And if for taking two guys。

 it's at most one fourth。So I cover at least three4。This saying exactly that。

 but for general case enough to。When k is 1 is 0， lets see say it is covered in the first instance。

Anyway。How do we prove this？I mean， the intuition is more or less given already。

 but you just need to write it down。对。What's。What should we use。Like， how do we plan to progress。应那。

Inction呢。Is it enough to prove this？那怎呢。Uncover T plus 1 is at most 1 minus1 by k times uncover T then。

Use that。W is this need to prove this。Whatever the number of uncovered elements are。

I can add one more element that will cover at least1 by k of this。

And man cover goes down by this much。Did' you tell we have it already。But。黑色不。Yeah。So。그 거。Yeah。

I have a stay with me。The people I have already collected。And they's opt out somewhere somewhere。But。

 let's say， I know。What I will do is。Some of the people in art， I already have。

So what I'm saying is this is S result。And these are people by。So。

 what I' am going to do is I line up all the people inO that are not in。Let them be。E 1 E2 upson E L。

This is just up。Minus S。OK。I'll start adding them one by one to ST。So right now I'm covering F of SD。

After I'm done， what is my value？If I add all these elements， what my how many am I covering？

What is the set of the all this。都频。They're covering at least as much as stopped。Yeah。

 so the set is as the union operates。咩嘢。If's like。If I add optt minus S。To us。

 it becomes our Unionist。好吧。And use this at least a ofrup。I all。だからほら。喂。W not on。O。So完的。All people。

And my objective went up from F of S3 to F of。As the Union O， which is at least a four。So。

 that means there was an instant when it bumped up the coverage bumped up by at least the average。

Like what I'm saying is there is an instant when。F of S T Union E1， upson， E i plus1。Minus F of。

Sテ union Eワ up Eアイ。I at least。UAbout 4 minus above1。M。Right，题 makes sense， right。If。

 if something increases by 10003 steps or post steps。

 then there was a step when it increased by at least 25。Outage。And this。

Can I say that what can I say about this？I already have E1 up to EI and SD， I add Ei plus 1。

I'm covering this much extra。Can I say that if I throw away people even1 up to EA and just add EI plus 1。

 I'll cover even more。😊，Have two people with me。I added a third person。And that the fourth person。

When I am the fourth person I have covered x number of or I have hit x number of communities。

Can I say that if I throw over3 and just add four。4 is going to cover more than X。Yes。

 because maybe theyll cover something more that third didn't。Our third date。I mean。

 so third did cover someone and when I added4 I didnt count those sets that four will hit that three already did。

I won't count them， but now I will。 So what I'm saying is。Is this statement。毕以了。

And what exactly is that。It's a similar letter。The marginal cost of or the marginal value of EI plus1 can only be more。

If I take lesser elements。你是什么人？So are we， are we done。So what we proved is。AOf SP Union。

 I just call that element E。完了再爸爸睡。Is at least。 And note that L is at most K。

The number of elements in。Oh and not in S is at most okay because。TheS of a isque。哦。嗯。

This is one element。And the element I pick will be more than this the gain I get。So， basically。

The E I pick there that is R max with F of S E。 So we just showed an element that has this so the element we pick also satises this。

😊，So I can just write this as。An가。系い。给你 see。So， this statement。😊，SoF of SD plus E。Mus F of SD。

Is the same as uncover T minus uncover T plus1。That's from that， it's nothing right。

And this is exactly uncovered T by K。So that shows that uncover T plus one。那's那's次。So。

What's the proof for submodlar functions in general monoton？珍部ル。

Wouldn't use anything other than mon of modularity。In this proof。来。So， the greedD algorithm gives。

i want my。1 minus1 by K to the k。他不让自面食。Okay。Which is， at least。关慢的算为一。Okay。

So my uncover k is at most1 minus1 by k to the K。If I use that here。A as case is， at least。

1 minus1 minus1 by k to the K。It is在 least上算。That's it， that's。Let's是。

Partinality constraints sub modlar， monoton submodular max。G on minus on。And it's tight。

In the sense次。There is the hardness result for max K cover。

That you cannot approximate max takeover better than。1 minus-1 by E unless P and P。嗯在。

It result by P game。Oh， I need to check this。Yeah， there is the hardness result for max scale cover。

😊，嗯。Yeah。So， yeah。We have still have something we can go something wrong。So any questions？

In the algorithm and the analysis。So a greed that gives on somebody。quickly。

Tell you what we can do for the non monitored case。不。So。Let's think of that。I'm asking Mexico。

It's un heard。But give me an approximation last。Tell me an approximation algorithm for Max cut。Okay。

As DP is sure， but no as DP is no LP is something very elementary。Random subset， right。Sorry。

 aware that if you pick。A random set。Basically tos a coin for every vertex if it sets take it else through it。

 that is your random set。That's a step。ISure。That's a simple algorithm， right， No computation， yes。

Let starting in。And whats the cut value of random set。Let's go undirect it。

Let let's do board director under。So what's the expected cut value of。

If I pick what what takes it randomly。They expected compound out just half the number of registered drive。

Yeah， so if it's undirected。Our is， at least。啊。Cut off as in expectation。

At least half number of angle。at least one fourth。If it's directed。Easy。Half because any age you。You。

 you should be in here。 We should not be in there。 We should not be in here。 That's one fourth and。

14 plus one4 probably is exactly half。So linear exploit have underrated case。You should be here。

 We should be there， half and half one。That's one。Claim。For any inamorance ofular function。

If I pick a random set and then just give it。그。If the output a random set。

 that's a one fourth approximation。All I need is that it's a submodder function。Let's wait。In fact。

If a is symmetric。So that's perfect， right？Half undirected。At a symmetric。 We had that。

Directed cuts need not be symmetric， but we get the one foot。That's magical， right。Okay。F。Yeah。

Let's prove this。This should be pretty immediate once approved。And the proof is。3 four lines。再来一栋的不。

So， I'll imagine that。The opt set S star is this。And let' us look at any arbitrary attacks。😊。

I'm going to define siblings of in the following day。Why is。啊，谁。ABC。喂。A is x perceptionist star。

B is x perception S complement S star complement。C is X complement in such an。V X。

It's complement intersection mix。嗯那。There is these parts。And what are the siblings。W。

Is just be unionency。嗯。That is C union D。W is a union B。I just read this。This is my x， this is my y。

 this is my Z， this is my w。And the siblings of X are Y at W。

You can see easily because of the symmetry that siblings of W are the other three siblings of Z are the other three siblings of Y are the siblings of。

😊，Basically， these are siblings。And it's an equal installation。That's why I call it siblings。Right。

Glan。observ。I发。A plus B。I'm calling Union as plus， just for ease。Okay， I'll call I'll call this。嗯。

What if I apply the submodular definition？你个先。Is it done。我的。what do I get if I apply the definition。

 the C definition。So quickly， what's the intersection of those？What's your name。Similar人ly。

What's of C plus B。Let's above C plus B。A C plus， above。Sepless， sleepless。OK。

And what are these guys x， Y， ZW？Is at least these two plus these two。What is F of a plus F of c。

At least half of a plus C。And there is intersection C which is 0。 and my function is non negative。

 so。I can just say this。This I thrive away for now。What is a plus C。So， forever， set X。So basically。

 I'm creating these buckets。In the bucket that axis， there is Y and z and W。

And one of them is at least one fourth Eer vester。Yes。You wantna pick a random set。

The expectation is at least one fourth。If that' is confusing， we can just add， right？

Let's add a call of this。And the addition I am going to split as buckets。Some of our buckets。

And each bucket has four of these。😊，And that guy is at least half vestster。

And how many buckets are there？Each bucket has four guys。So I take the two to the end there。

 That's expectation and it。8 start。That is the proof that it random set for approximation。

What if the function is symmetric？What is this。F of A， B B， What's F of C。What's up of CBD。

 What's up of a。So I'm getting another f of a plus c for3。Which is two of us。

And that gives a half approximately1 asymmetricmeter。So。In a sense， what happened here。Random set。

 if we just give it。That's half approximation。If it's asymmetricno monoton function。

It's a one fourth approximation if it。Ger。No one转方。And half is tight， in the sense。

For anysymmetric of model the function。If I have to do better than half。

 I need to ask exponential manicureries。So， this result is tight。

And the best approximation factor is half。But in general。That's a different algorithm。

 It's called double greedy， but yeah。你叫十闻兵。I the proof clear it's pretty elementary。For every setax。

 I created four other sets or three other sets。😊，So that they add up to at least。U。If it'ssymmetric。

 at least two up。And。That's kind of like an equalence like if I take all the sets， if I pick one。

 it has three siblings。😊，And their siblings are the other three， so they form this clique。

I take them and put in a bucket and I keep doing this。Each bucket has at least half of a star。

Or two F of a star if it's symmetry。那题。嗯。So in general， sub functions are very。

They are everywhere where。 they are very useful。 This is a very powerful abstraction。😊。

People in machine learning are interested。It'次。It all you can say that subarity is a discrete analog of convexity。

😊，We love on function， right。Theyre easy to optimize。You can minimize conx function。没什么。

But that's in the continuous role。Someone alert is exactly the discrete analog of。关了。

