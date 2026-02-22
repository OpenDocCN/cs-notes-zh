# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p25 Lecture_25_Approximations_&_SDPs.zh_en -BV1a4cCeMEzb_p25-

Okay。So let me get started。So today， I'm going to。Talk a little bit more about approximation algorithms in particular and I'll talk about approximations using semi defite programs。

😊，But first， let me just finish the binpacking LP that we talked about last time。

Then I'll talk about Spss and its view and vector programs。

 which are how we typically tend to use them。 And then I'll talk maybe about。

Some subset of these three pros， depending on how things go。对。So let me get started with bin packing。

We were talking about last time we have N items。哦，西部。S 1， S 2。Up to S N。

 all these sizes are between0 and1。 We have an unlimited number of bins。Oh size。1。We want to。

Minimize the number of bins。Go back。哦系 don。And I'm going。Is the an。That。Uses。嗯。

One plus7 epsilon times optt。Plus， some， you know， F of epsilon。Many bins。Okay。Good。So。Good。

 so so here's what we did last time。 and this is so what we did was we made two assumptions。😊。

That firstly， the number of unique item sizes。If at more somebody。And then we said each item。

Offf size。Adhesive。So under this assumption， we are going to give a result。

 and then we'll remove both these assumptions。And the way we handled the situation was we said， okay。

So we'll say a configuration。Is a collection。哦。Item sizes。That of total size。都是 size。

So if the sizes happen to be 0 point you know， whatever， A， B and C。Let， let's just give an example。

 point2。3。5 and we have like 50 of these guys and 17 of you know。

17 of these guys and 13 of these guys。😊，Then， you know， I could。

 configuration could be something like 02。Timem 5。I'm pack five copies of this item size or 0203。

five。4。3 times 3， et cetera。So basically， these are just patterns。And what do I want to say。

So point4 point to24 as well。 it doesn't really matter。 In fact。

 you might as well always include maxim mu collections， as you will see， you know。

 it's really covering Lp because what we are saying is we are trying to pick the fewest。😊。

Configuration， So we are saying for every configuration type C。

X is the number of these configuration that we picked， such that。The sum overseas， which contain。嗯。

Item type S， let's say。哦。X， C， S X， C。Must be， at least。The number of。Items of types。

So N S is the number of time I it。好细嘅。不。This is not true， right？So， I should just say。

Some overall configuration C of。Some matrix， A C， S， A C， S。Is the number。哦。Ca these。Of S。And谁。

So if I were looking at point2。Then A C S here is before。1，0。So。

 I want to make sure that I have enough room to pack all these。50 items type 5。

2 into the configuration。And of course， I say X C。Is greater and equal to 0。From corporation。他现来。呃。

没明白。I have Max cut on the brain today。This makes sense。

Minimize the total number of configuration fixed so that every item is completely covered。😊，Thanks。

The LP value is at least。Is at most the optimal。The optimum is a solution。Actually， this is a fact。

 let's just say the fact on the site， suppose I was trying to minimize C transport x。😊，A X is。

At least B。X is non negative。And there are B constraints out there。Then， my claim is。

Ac a basic feasible pollution for the LP。N， n is the number of variables。 Let me say n。그앤 돼도。

You know n。T constraints must。In fact， there should be linearly independent type constraintsstrain。

Now， these type constraints can come from these D。Or these。Non negativity constraints。 So therefore。

 you know， at least。N minus B。Must。B哦 this。But tight constraints means those variables are0。佢啲货。

Atmost B。90。冇错。Tmo B。对什么。反。YeahYeah。So this just says the is x。Is X hack。 No。

 X is a basic feasible solution。To do feet。没。Ht。If I looked at the L1 norm of that。

 that's just the L1 norm，This is just the L10。O。They are not negative。

 So the L1 normal to fancy L1 normal exact is oh， sorry。So then we if we define X hat to be just。

The rounded up version of x。Ha L1 norm。Atmost L1 normal X。对这里。Their D variables which are fractional。

 even if I round them up， I lose only。没看。😊，So I lost it detail。车 didly。Now， I'd like to make B small。

Of course， you know， it could be my， it could be the cases the number of unique sizes is N。

 every item is a unique size。😊，This is a useless。Slect6。And so this is an idea。 I mean。

 this whole thing is a paper due to。Fnandez。For man is。就留这噶。And。呃，捞一个。So what do they？They say。

 I'm going to reduce the number of unique sizes。应该是pro。Because， you know。

 if I increase this size of an item， it you know， my solution might become inasible。 I had some。

 you know， op solution。 it might become inasible。And if I decrease the size of the item。

 I find a solution。 there is no good for the original。😊，So they came up with this stunning idea。

So they listen， okay。Let's put all the items。Let's sort all the items for。

And let's just line them up。These are all items。ベレサ。行。I want the unique sizes。

So here's what I'm going to do。I'm going to break this into， let's say D is。5。Yeah。

I'm going to break this collection into five pieces。好。Yeah。嗯。嗯。

I'm going to take these items and make their size equal to the maximize。

These items make it easy max size， these items， max size， these items， max size， these items。

How many item sizes do I have。没。呃，这里。So B， you know， this is there n over d， n over D。

And over D in each group。So there are， you know， B many different item sizes。 So B item sizes。

 B unique sizes。My construction。Okay。How much have my。Optimal changed。I want to say。That。Look。

 two things， suppose I find a solution for the yellow sizes。

Then I can pack the white items into those yellow sizes。Because wherever this this yellow item went。

 the white item is only small。😊，So the white item can fit where the yellow item。This yellow item。

Wherever it went the light， I can think。そういう making the size ofです。

So if you find me a solution for the yellow things。Those are good for white。So basically， if I find。

 yeah。The only problem is。What do I need to show that the optimal solution for the whites。

Might not be feasible for the yellows because the yellows are bigger。 But how much is the so opt for。

The rounded instance。I want to claim is not too much more than opt for the original instance。

Blessson。How much。后来啊。三百年啊。Suppose I gave you a solution for the opt guys。😊。

You want to find a solution for the rounded up。我出不。So here the information。Look at。

Don't worry about the first win。Look at the first item in the second then。What it where。

The first item in the first payment。The second item went。我老钟。We are starting from the yellow sizes。

 and they're going up。So just the yellow guys。Are are equal to the largest item size out here。

Wehich are smaller than the smallest item size， O。So you could just take these three items and put them where these three items were。

 these three items where these guys were this， where these guys were。😊。

Through the shipping the entire yellow grid。To the left。The only problem is the first B doesn't fit。

But how many items are there that are like most n over B in？嗯。

So now I find the solution for this guy。And I'll handle all these bags separately。

You've got this like an overview even just like fines that I'm not quite sure what they are。

 but't you also like。To just like N over D， you put exactly N over D into each bucket。

 Can you also just make the buckets。Like one over D2 over D，3 over D4 over。同你的。Good。

 so you can start being a little smarter about this thing。😊。

TheSo the one piece that I don't understand is。If you made this bucket smaller with fewer items in there。

How would you make sure that， you know， how would you find homes for these next few days。

Are you thinking of something different okay so。Next one over be。Good。数据开放的。Good。

 so what would happen， Let's， let's just look at an example。So。I have one item like this。

 and there's a whole bunch of items of size one。

![](img/2ccad39b1eaa1ea5b3514f357a213ef3_1.png)

1 over B plus epsilon。It toldson the problem is that all these guys might become of size2 over being。

Suddenly， the volume has gone up by a factor of two。I have a lot more stuff perspective。

So each of these items did you add in a one over D to it。So。

 so basically I'm imagining that there are all n items。

 There is one item which is of some size and everybody else was a size 1 over D plus epsilon。😊，Now。

 I made them all too over pretty much。So basically， the volume of my system。

 apart from this one item， even forget it。 I mean， in fact， I didn't need this way。よし前順で、すね。

The total volume is doubled。人可以。啊。YeahGood。Good， but here is the problem that's going to happen。

Its it has increased。 the volume has increased addly by an over day。😊。

But the thing is that imagine that one over deep plus epsilon like so many of these items nearly fit into a bin。

😊，Now， you have doubled the volume。You'll need place with manys。

So I don't know how to show that this volume increase that you have done。Oh， I see。 no， no， no。

 but maybe， maybe， Okay， I take it back。 I it too because I was。当 you说 really你的心态。Yeah。

 but the increase in volume， hopefully， okay， so I have to think about this okay。



![](img/2ccad39b1eaa1ea5b3514f357a213ef3_3.png)

There might be some ideas out here to do this slightly differently this one I like is this sort shifting idea is very cute。

😊，Okay， so basically what I'm saying is look， I rounded up the item sizes。😊。

These I brought them into N over these item C。And each item size。

In this group is equal to the size of its large。But that is at most the size of the smallest item in the previous time。

😊，So I could just take these guys and put them where these guys。😊，These guys were these guys were。

 these guys were。 these guys were。 these guys were these guys。But these guys don't have a home。

 So I just find new bins them。 I just open up。嗯。我。So I got an add and over D term more。

 Now I need to do something about it。 actually， I don't have not， so well have to wing it anyway。

Will这。嗯。这对。So I can get。Opt of the original。Plus N over day。And then I need to do something else。

Okay， what do I need to do。嗯。Good。So just for the moment。Let me choose。

B to be1 over epsilon the squared。Okay。滚。So this is opt of the original plus epsilon squared n。

 right？What is epsilon squared？All items size the are of size， the key steps are。So， optta at least。

开了次了。我你咁细细到佢场。So softptted n X， because the volume is at least N。嗯。

So this quantity is at most epsilon times。Because items are at least steps。I crucially used that。

If you。N over D， epsilon square。Epsilon squared n is Epsilon times Epsilon n。

But opt is the three steps in one。 So this is the key steps。AIコンセ。So this is。好。😮，Plus Epsilon opt。

 That's one plus epsilon opt。Plus。One over epsilon square。是。嗯。O看。我放说吨。

It's something which people worry about。If I'm saying items are a case of saving。

That was crucially using that。you might say， why are I say the？So here's this simple idea。

 And you know， in fact。Not even worth spending too much time on。

 but it's actually worth spending time on。So here is。I have my instance。

There are items which are of size at least epsilon， and there are items of size at most。是的是的。

Items upside the key epsilon， I'm going to solve them this way。I left with all the items。

 I found a solution。These are pains。These are no longer items。 These are bins。

 but they all look exactly the same。 I always draw my， you know， skyline the same way。

These bins are filled up to some amount。 Who cares。These were handling all the items。

 which were large。I've got a very good solution for them。I need to handle these fast。

 what should I do with these guys？These are dining items。They like sand。

I just kind of try to sprinkle them。I take my first small item。

And I try to put it into one of these bins， if it's free。Maybe maybe this can take a small light。

This can take a small item。 This can take a small item。 This can take a small item。

 This can take a small item。 so so。Suppose a bin can't take a small item。 I need to open a new bin。

What can you tell me about all the bins？When I need to open a new bin。The benchs are really full。

1 epsilon4。So the volume， you know， the size is one。 The volume is1 minus epsilon。

 So theyre like one plus epsilon approximation all right。😊，I don't need to worry。So， basically。

 the point is that if the item sizes are really small， then first weight， next fate。

 all these algorithms are awesome。😊，Because whenever you open a new bin。

 all other bins are very full。That。You can handle the small items at the end。I mean。

 it's kind of like what you do right when you are packing your office。

 you pack everything and then you find these little ETBD bits and you just kind of stick them to various。

😊，非论调解。Oh I found， you know， a little。办的。But。So that's pretty much idea of these guys。

 Fernandez Zlavega and Loker。 And you know， just in case you write a paper， this is his last name。

 shouldnt this is his first name is Vs。😊，是吧。이 이제 저긴 해 거。Give him full full names。Anyway， so。

 so they gave this algorithm。Which achieves this guarantee。And then， people started improving it。

And then a paper of kmarker and carp， carp of you know， whatever。During award winner， Kl Markel。

 the guy who will sort of develop interior point methods。

 they gave an algorithm which achieves the following guarantee opt plus。logg。Noong。Square。

InIn the interim people gave an algorithm which was opt plus log opt。😊。

And then they improved it to optt class log， log， optt square。 I think I'm getting this。

And recently using some very nice techniques using discrepancy theory。

 well you know maybe you know we'll talk about it， you know recently people improved it to this kind of behavior。

😊，What we don't know is how to get opt class a constant。It could be true。我等可一下。对我走。完了。

I don't know是 quite。你疗个。packed。Show an example where Rockless constant is not possible。

 I think that might be a pretty valuable paper。 I think people would be very。Okay。

 so this has been tacking a plastic problem going back to the 50s in fact。

 oh one thing we did mention， how do you solve this helping？😊。

This LP has a large number of variables。Of course， there are two things you could do。

 You could say how many variables are there， how many possible configurations are there。😊，Each。

 remember， item sizes are large。So they can be at most one over epsilon items in each configuration。

And there are only D sizes in D like one over epsilon squared。

 So there is only one over epsilon squared thats D。To the one over epsilon， many items。

So the number of variables is only constantly many。Of course。

 you'd never want to solve an LP of that kind。Mta。It's constantly many。 So in theory， it's fine。

in practice， what you would do is you would use problem forward from your current homework。

You would use this idea of column generation。It's a acute problem。 Please do track。换了换去去。

It uses duality and eside my third in mice。😊，O。关信。Most not。 And let's get to the main。Job of today。

Which is semideite programs。

![](img/2ccad39b1eaa1ea5b3514f357a213ef3_5.png)

And hopefully， you guys have already。Bred up on semi defite programs， or at least semide。

I'm interested in seeing different programs。Yeah。So at least I have to give you one or maybe two definitions of positive semideiniteness I am only looking at symmetric matrices。

 real symmetric matrices。😊，Ssymmetric， real matrix。Is BB。Positives semidefinite if forronx。

X transpose X x。It's not negative。Or if there exist vectors。Be one。Up to B， N， oh。

 this is a matrix in N cross n。So if there exist n vectors， such that。

AI J is equal to the inner product between V and。All。If they exist。Vctors。

X1 up to Xr for some rank curve such that a is equal to the sum。Xi。

 Xi transpo without a product human。A many other possible ways in which you can view SDP。Okay。

what's semi defite programming？Sing defin programming。

They are two ways of viewing it and both are kind of useful in their own way。嗯。The first one is。

 I write an LP。嗯。Plus， I say that a certain matrix is positive semi me defite。So小孩子我带的东。

I'll have an LP。With。Varis。And now， for some reason， my variables are indexed by X I J。

They have two indices。And so these variables naturally sit。😊，In some matrix x。

 this is a matrix of variables。And so I have constraints of the form。You know， minimize。Sation C I J。

唔使啫。Such that。AI J1。X I J。TheAI J， K， X， I， J， some overall possible I J。

 this is some overall possible I J is at least， let's say B。对。

And instead of these being non negative these being non negative or something like this。

 actually my constraint is x。Is a positive semi definitely。

Thats my that's my shorthand notation it's known as loner ordering。LW。嗯啊。

But a out on there is a lunar outing。It just says this is x is positive x is PB。啊。

And since these As and Cs are also indexed， you know， Doubly indexed， I'm going to just define。

A product， so I'm going to say a is a matrix。Dot x is a is another matrix like this is just the sum。

 You know， it's just， it's like an inner product， but it's just。It's over mates。

 so just AI J X summed over。Here is my definition。 I think this is called the Proveus product of the haammo product or I keep forgetting。

😊，For being你说的。Say it again。这证据。原告会。Oh， yeah， thank you。好吧。So if I write things like this。

 basically Im saying minimize a C dot x such that a dot x ak dot x is at least the k。Scalar。

 yeah ferity。X is。Positive。And if you were squinting real hard。

 you would think this is a linear program， pretty much a linear program。

 except that the inequality is changing to way。😊，It's a very nice one。W。Yeah。So that's。Yeah。

 it somehow seems like a mysterious quantity。 We'll see how to use it in just a moment。

 Maybe I I'll write down another way of viewing it。 So this is view1。

Almost never do I find this useful， sometimes it will be。View two， which I find more useful。

 but your you know， your mileage may vary if you work on on this， sometimes you need this viewpoint。

Vector programs。I just imagine my variables。啊。Viectctorors。I don't get to control their dimension。

They might have， you know， some number of dimensions。 So variables are vectors。 So my vectors are V1。

 V2。A做。And really， in general， I have no control over the dimensions。 So they are lying they are。

And variables and dimension。のか。If you had more than and dimensions， you could always， you know this。

 this。Bring it down to end dimensions。 They can only span an end dimension sub。没有。嗯。

Vable of vectors and constraints。啊的。Of the following form。怎么。Constraints are on。Linear。Conbinations。

Of inner products， B I。So you might have a constraint which says you know summation。AI嘅。VI vJ。

In at least。过来。그。So just some linear combination of inner products。😊，They will a constraint。

And you're again， maximizing or minimizing that minimize。サネーションシ。

Wherever you want it to put down the variable， now you put down it in a product of two vector。このです。

these are exactly the same right？A matrix is PSD if and only if it has this representation that AIj is equal to V dot vj。

So I could just do a search and replace out here。The fact that x is positive。

 I mean definitelyite just means that there are vectors V IVj whose inner product is equal to for every item。

😊，W equal to X I for。So maybe I should have been。你个。Okay。

So that viewpoint is very useful because it's a geometric viewpoint。 its。

 I'm giving you my perspective。 I find it very useful。 It's geometric 1。

 I like geometric perspectives。😊，It's yeah， different people。OK。对。So let's， let's do。

 Let's solve a couple of problems。So here is here is the problem let's try to solve。By the way。

Let me give you a couple of facts。 I'm not。 I don't know how much youll do。 So facts about。SD。So。

 SV Bs。Have。Do sD。Okay。This。Is a SDP。Let me write down its dual。

And the way I write it down is almost exactly the same。 Look， men becomes mass。

What would like if I had this thing， the objective function would be。Sumation。B。き。Why。Okay。W are。

 let's say， reals right now。So this is， this is just like， you know， S an LP， right。

If this was you know， this would be AX is at least B。This would be B transpose y。But。

Now I have to make a so so this this constraint looks like summation。诶。嘅。Y k， remember。

 ak is a matrix Y K the scalar。So I'm summing up a bunch of matrices multiplied by a scale variable。

Normally， I would say this is less than equal to C。I want to say this is less than equal to C。

But Im not allowed to write lesson equal to what does a lesson equal to mean in。In， in this world。

没有没有。😔，拜托代。Basically， this means c minus this quantity is positive similar。😊，嗯。And in this case。

 why is because these were not all wiser。This is a duall。 You can。Okay。

 should we try to prove weak duality just just to get our feet wet。😊，Let's prove Greek to All。嗯。

Let me do this here， and then I'll hide it。So I want to prove we to have it。So I want we。

The weak duality should say。Any solution here should be at most any solution。

let's look at the solution。这上面行。没。Yeah。Why here。Yeah。Why is that not negative， O， why K。doesn't like。

 It's available。What in be gay。Bk is at most ak dot X。Why is that non negative？

So I can write this is that more。给嘅。Not X。W得 on你。么。It's a scalar， right。

 is two scalrs that we multiply。Okay。So this is equal to summation。哦。Y k。可见。W。

This dot was a linear operation。Okay， what do I know about Yk dotakk？Its。At most。

So this term is at more C。O。And here is the fact here is another fact about PSU matrices that hopefully you write on page two of the notess。

😊，And个。嗯，那。This is less than this than multiplying it by another PSD matrix。😊，Maintains this sign。

So this whole thing is less than equal to C dot。可这的。And really。

 all these are sort of special cases of an idea called cone dualality。 If you're interested in this。

 I can point you to this we can just where will come up with。😊，This notion ourselves。

 it will just take five minutes afterward。So big dual is true。You guys happy with this？OkayOkay。

There was just this fact， this this one little fact about PSD matrices that if a is less than B。

 basically I am saying it a is less than B。😊，And X is B SD。Then a dot x。It's less than equal。

Another way of saying this is if a is PSB， if C is PSB， let's say。And x is PSP。And see our next。Okay。

 if you can say if C is PSD， if and only for every egg。😊，也是这么的。我那 character。

He estimated made magically。Comptely 맛있。 but anyways， this these are not you know， difficult things。

O。あまないです。So big duality is true。we I don't know how to like week。Strong dual is false。

So every time you do PSD duality， you better think about it。In some cases。

 it's true if you have something called a slater condition。Then you get strong reality。So。

 whenever you want to do duality， strong duality with PSD matrices just be you know be careful。

 pull out your you know convex analysis book。😊，我知。Remember。

 LPs used to have polynomial size solutions。SDp。So by polynomially sized。

 I mean the numbers that you would get would be only exponential。In the input numbers。Svpss may have。

Exponential phase solution。Yeah。You can write an SDP， which actually does kind of。

So it makes sure that x2 is equal to x1 squared and then x3 is equal to x2 squared。😊，Et cetera。

 So you're squaring every time。Your numbers will be doubly exponential in the input numbers。

 So the length will be exponential in。NDP is dangerous objects。So if you are working with FVPs。

 you got to be careful， you want to make sure that your solutions are reasonably sized。😊，However。If。

Reasonably sized。Or solutions。And by reasonably size， I just mean poly sized。Then。There exist algos。

那。Fd。嗯。Solutions which are you op plus epsilon。嗯但。嗯。帮你。The input side。こあのラのか。Basically。

 thellside method。Inter point methods， this will work。

 but you need some assumption about the input about the solution size。

You can't approximate them well， by the way。You might not even be able to write down the selection。对。

Absolutely， so this is why you won't be able to write down the exact solutions for sure。 Oh this guy。

 actually， these guys， I mean， the optimal solutions will be integers。 You know， it will be like X1。

😊，2 or something like this X2 is x1 squared。So really X n is two to the two to the two to the。

勾勾 the肚的点。No， I'm say like it be important。one is。他去个这个投户。没对。然后。Sure okay。

 so maybe I should have mentioned that SP may have not only exponential size solutions。

 but they might have irrational。真录性。So absolutely it's possible that you will not be able to compact write down the solution。

 but it' is okay we are usually okay with an additive E。😊，我冇见。So we will make assumptions。 well say。

 oh， we will find solutions which are good enough。For today's lecture。

 I'm going to assume that SDP can be solve exactly。😊。

All these you have to take with a slight grain of salt。That what if the solutions are not exact。

 what would you do？And the solutions and the algorithms I'll give you will work Well。

 They're robust against these kind of approximation。😊，But for right now。

 I'm going to just assume that STP can be solddex。The rationals。Regardless。

So let me tell you about the first approximation。Using S。And this was。So you know。

 SDPs were around for quite some time。But course a long time， we didn't know what to do with them。

And when the first algorithms came out。They were so surprising because they were so simple。

But we could actually you know。Yes is。I， you know， it is a little before my time。

 but I I'm guessing I should find out from the people who are just developing this that you know other people probably kicked themselves for not having seen。

The ideas。But you know， it's a very pretty idea。没有申。Yeah。不让你坚持。O。

So the next problem we're going to be talk about is a problem called max time。😊。

Its perhaps the most basic problem ever。 the simplest problem to state you are given a graph。呃，经。

Un weighted undirected， let's say。Let's not worry about it。F迎。Of partition。S and V minus S。

So this is my graph， find a partition。S and V minus S， which maximizes the number of edges such that。

Edges going from S to v minus S are maximized。Given a graph。

 maximize the number of pages crossing the car。Opposite of mint cut， mint cut in poly time。

 mass cut NP P heardd。嗯。Interesting Rob。Let me give you one algorithm。嗯。

So we are trying to maximize the number of edges being cut。

 So here is an algorithm that will make sure that we expected So this is going to be a randomized algorithm and make sure that the algorithm cuts how many edge is it cut cuts。

😊，At least。他 for P也就是这。And since the optimal solution can't cut more than all the edges。

 the graph this cant be more than October。😊，Can't be less know about。对不是。Like SB。Random， you know。

 so S。A V do S。With probability in half。Independently。For all word。Expectation。Of the indicator。刚。

Is one house。Condition on one endpoint the other endpoint will have will be you know。

 one endpoint either being in s or not in s， the other endpoint will be not in s or in s with probably1 half。

😊，没缝。系。你明系啲。Onter expectations。Expected side of the cut。现在听。嗯。那。嗯。一个。I can cut half the edge。

There are the algorithms you can do， you can do the greedy algorithm， pick a vertex on one side。😊。

 absolutely。You can run the greedy algorithm， put a vertex on the left hand side now for every vertex look at how many edges are going on the left。

 how many edges are going on on the right， put it on the side which maximize number。😊，啊。Local search。

 half。And then we， you know， everything you try half。And being half。LP with extra const。

Everything we created with it。People were like， maybe we can't do better。And then there was a tiem。

 there was an algorithm。Due to Goman and Williamson。It's yeah， it's a very famous algorithm。

 but very simple as well once you have the right technology。😊，That exists。 And yes。

The expected size of the cut。Is going to be， they're going to give an algorithm。

Who expected size of the car is0 point。8，78。Thanks。Its not just half plus epsilon。

s half plus a huge epsilon。😊，It is lateness。I think best paper at Fox 95。

Maybe they didn't have best papers back。We were so poor reading didn't that。Yes。

So this is the algorithm。 sorry this is the theorem。 the algorithm I'll tell you more。😊，And know。

 maybe you've seen this， but it's still one of those things。So多谢咩。诶。

So how do you come up with So were going to use SP to solve this， of course。

 So how do you come up with an SP and here's one where。😊，So， you start with。quadratic 쪽。就 saw。

Remember what we said earlier we said， oh， we are going to write an integer linear program to solve the problem and we are going to relax it together get an LP。

😊，Now we are going to write a quadratic program to solve the problem and we are going to relax it to an STP。

😊，So here's how I'm going to write a quadratic program。😊，I going to say maximize。

Sation over all edges of the draw。Of X， I minus X J。Square。Such that。X I squared Oh， so for every。

 yeah。 So vertic C are index by AI for every vertex， its either one or minus1。😊。

Every vertex on one side is going to1， every vertex on the other side is going to minus1。😊。

So if these were scalrs， this is just the only solutions here are plus 1 or minus1。

And so I'll either get0。Or I'll get 4。maybe是。Yesesttation。嗯。

This is a quadratic program formulation of our problem。Let's relax。So instead of looking at products。

Remember members。I going to look at vector。So， instead of looking at scale。

 I'm want to look at vectors。And instead of looking at products， I'm going to look at inner products。

上面个 max。网花者。Exformation。So this is really X minus xj squared。

 I'm going to take the inner product between X minus。😊，系た。But that is the same。If you says。たくさんマイナス。

ご。It it is an inner product。 The only reason I wrote it earlier was to make sure that you know。

 it is an inner product if really really I'm doing。Xi Xi。对。Minus twice X I J。Plus X J。Same thing。

 I'm just doing out a。That's that。 So what's the constraint for that。백셀 x x。你是觉是认识吧。

Neither unit vector。来做了马。This is my linear program that SDP I want to make。

Youve stared at it for a second， you know。First time you see SDPs， you are convinced some things。

Something weird going。This is just Xi minus。で。Only to describe。O。来。Look at this， this term again， X。

 X is one， exactly one。 I just set it to be one。This is also one I ci it to be one。So this term。

Is the same。 I'll just rewrite it。 Matts of。Some， I'll come to back to the one fourth。Two。

 this is one， this is one， both are constraints。us two times。IXG。We are vectors now， actually。

And데 was one 고에던데。33。I'm looking for unit vector。Which are maximizing this kind of。What do I want。

I want for every edge。 So this is some overall edges。I want these vectors to be kind of orthogonal。

 to be antipoal to each other。How do I maximize this term。

 I maximize this term by making this as negative as possible。😊。

What does negative inner product mean they should be kind of antipolar to each other。But， of course。

 you know， I'll get back some weird of vectors， which might not be antipoal creature。

So that's you know we need to handle one thing I can do is I can get rid of this two。

 get rid of this two and make this a。😊，征地方。So what have I got， Have got。

This is supposed to be a ball this。I've got these vectors。X 1， because would like to X2。

So come back to x3。 All these are unit vectors in some high dimensional space。

And theyre maximizing this objective。Now， of course， this objective is at least stopped。

Because opt is a solution to this thing。I could take a vector and it antipoal vector。And I could get。

Basically，0 for every non edge crossing the car one for every edge crossing。So how do I get。You know。

 these vectors， you know， there might be vectors all over the place。

Some vectors are close to each other， some vectors are far away from each other。

 who knows what they do。And what Gos and Williamson said。I want to， I want to round。

 right This is relaxing round。So I relaxed。嗯，And now it needs to ground。Somewhat down。W。Yeah。Yes。

So what's the rounding algorithm？The rounding algorithm says take a random type to play。

Yes uniformly random them hyper。Everybody on one side that's plus one， everybody on the other side。

So big。P I call this G。From the。five uniform别听下。They pick a direction。And then， I say。嗯。X， I hack。

With equal to the sign。哦，唔知多。Back next side。We you speak the random vector。

Everybody who's got a positive correlation with this is one otherwise。My claim。Is。

So I asked the question， what is the probability。That the edge I J。This is the question I'm asking。嗯。

How do I analyze whether Ij is correct？So here's what I mean。I say I corresponds to vector。X二。

This is on the。Yeah。J corresponds to a vector。Thank。The random Gaussian or not Gaussian。

 the random vector。When is it going to cut it。Suppose the angle between them is theta。So。

 I'm going to cut it。Whenever the sort of hyperplane defined by G is going to be cutting this way。

What'在。Very。Yeah， so， so I have to worry about。You know， picking G somewhere out here so that the。

The the normal passes between these two guys。But really， you know。

 what the the probability of picking the appropriate Gs is proportional to。😊。

2 theta divided by 2 point。我咩设机可调。都可得你话。This data by by。해。So the expecting， okay。Yeah。

 so the expected。Gout。平是 equal是3。어 but all 애제가 이제。哦， k i j你为呢个。What's the SDP value？Half of。

1 minus the inner product between V I and VJ。嗯。The inner product between VI and V。

This is my SDP bill。But what's the inner product between VI and VJ。查一。我双也可的。哎，对。行。So it's a sum of。

 you know。 So now heres， here's the simple fact， right， So suppose I have a one plus a 2。

Plus A and all these are non。呃，どさけ？So呃 yeah be one plus be two。The end。

I don't know if I really need non negative numbers。I want to say this is at least。

Men of AI and what be。嗯。This over this is at least。😊，Men over theta of theta。

Divided by pi over 1 minus。Cass theta。 and maybe I'll push the two upstairs。

So I'm just looking at the， you know， there is some over something， some over something。

 It's at least the min of the ratio of this corresponding。对。

And now if somebody has a ultra alpha open。 Could you please throw this。我们你说这太。

We could throw it a chat GT as well， it will even give you the history of this algorithm then。😊。

I think就个。Have the。I know only the first five digits of。嗯。This turns out to be。0。87。这。That's it。

 that's the。So the L take a random Hyclaim， everything on one side， everything on the other side。

And this LP had been floating around。 People had been looking at it。

But people don't know how to round it。 And then these guys realize the random hyper plantses wouldn not。

Was it point。Still loading。 Don't worry about。OK。Can we do better。So I can give you one tip。

It's not the theorem we want， but it's very close to the theorem we want。So Ryan O'donnell。

 is faculty in the department。So， court。Kingler， Mossel and Odono。They proved the theem。That。

A certain conjecture， which， you know， if I had more time， I'd tell you about。

 iss called the unique games conjecture。And the unique games conjecture is。In some sense。

 the modern version of the P versus NP conjecture， I don't know if people believe it as strongly。

 most people would believe that P is not equal to NP。

The unique games canject not clear if people believe it strongly。

 but what these guys showed was that if you can do better than this in polynomial time。

Then the unique games conducted is false。And so that's that's。Fairly compelling evidence。

 This is someone saying that look doing better than this is actually solving a hard problem。

 You know， this is what all reductions are， right， I mean， what does P equal to NP things say， Well。

 if you can solve this and something really weird will happen。😊。

So this is just doing better than this， something， something reasonably weird will happen。

 something surprising， something that will win you best papers anymore。Thank deposit positions。

Or definitely impacted。So， they showed that you know it you know。

 so so this alpha you know I'll call this alpha Gomans Williamson。

 so getting this minus epsilon for some constant epsilon in polynomial time implies that UGC is false。

We would like to say that this implies P p is equal to NP。We don't know how to prove this。

We would like to show。That， so， a recent。Stongger。Weakicle injecture。

Is called the 2 to two conventionjecture。 You know， all these things， know。

 they have very reasonable。So reasons for having these names。 I'll catch， you know， again。

 take too much time， but catch me some time。 I'm happy to。

 You guys should feel free to ask me questions and Piazza， if you want。😊。

It it should be like an ask me anything。 I can， I can hold for。

I would like to show that this implies the 222 conjecture is false。😊。

We don't know how to do this because the Studio2 conjecture has recently been proven to withdraw wrong so。

If we could do that， then that could be。Or that's been shown to be as hard as。Be worse than before。

 anyways。Blabbing。Uhhu。The lines below。So it showed it for any epsilon great。So， you can't yeah。

There is like a quantitative variant， you know， a quantitative version that is going on。

 but for any epsilon rate than0 there if you can show sorry if you can show this for any epsilon rate 0 then there is something that is been。

😊，Then the unique game problem has algorithms of this complexity。Is there any hope of getting like。

Alpha GW minus epsilon。Times opt plus some like we get。so。

 so one thing with the with the Max Scott is that。Yeah， so you can get slight improvements。

And you can definitely get alpha Gw plus something that depends on the degree of the graph。No。

 I'm saying like， it depends on you have it。Alpha Gw minus epsilon times top and then plus some function of epsilon。

Let some function okay， yeah。Don't know。有。O。嗯。有有。Yeah， is。啊。What else if I have seven minutes。

 I can't tell you that much more about。SDP is， SDP have been very useful。If for nothing else。

And a bunch of problems。That was stuck。Using LP， we were able to improve using SDpss and in particular。

 a lot of recent。Machine learning algorithms， you know， it's like， oh。

 I want to learn mixtures of Gaussians stuff like this Pro could Huri works on this quite a bit。😊。

And its now， you know， extended into an idea called the sum of squares。

So instead of telling you about colorings， let me at least start off towards the sum square。So。

 the problem that we want to solve is the following it iss not an approximation problem at all。

 it's just a classical problem。I give you a polynomial。In some number of areas。



![](img/2ccad39b1eaa1ea5b3514f357a213ef3_7.png)

嗯。So this is something like， let me choose a polynomial that I know。



![](img/2ccad39b1eaa1ea5b3514f357a213ef3_9.png)

2 x1 to the fourth plus 2 x 1 cubed x 2。

![](img/2ccad39b1eaa1ea5b3514f357a213ef3_11.png)

Minus x1 squared， x2 squared。Plus 5 x。都都的。Opoponommal， multivari polynomial。

 And I ask you the question， is this polynomial non merit。



![](img/2ccad39b1eaa1ea5b3514f357a213ef3_13.png)

What all X1。I is falling on all。嗯。Why do I care about them？

I care about this because it is a mathematical problem。 And you know。

 David Hilbert was interested in this kind of question。 so we should be interested。😊。

Heilbert to this market。Also， we are interested in questions like。😊。



![](img/2ccad39b1eaa1ea5b3514f357a213ef3_15.png)

Very interesting in questions like。

![](img/2ccad39b1eaa1ea5b3514f357a213ef3_17.png)

Suppose I want to minimize。嗯。And a half time summation。系即。1 minus X， I， J， X， I， X， J。嗯。Right。

 sub subject to X squared equals 1 for all I。I start this， I could ask the question。😊，Is this。Minus。

三。Thatest value。Is this always not negative。What am I asking。啊啊is this。Yeah。C minus this。

What's the question I。I'm asking subject to some， some constraints。

 This is not this this is a constrained version of this problem。Subject to these constraints。

 I am asking you whether this polynomial is。Not那个的。Suppose you answered yes， what does that tell me？

The max cut of this graph is at most C。喂。So I'm interested in in answering the questions。嗯。Yess。B。

Greater than equal to 0。😊，化装。Xs such that Q1 of x。Is equal to0。 So Q J。

 Q I of x is equal to 0 for all。Given a bunch of polynomial equations。

I think it's called a variety or something。Over this surface。

 over all the X's would satisfy all these equality。是。Is a certain polynomial non magnet。Yeah。

Absolutely， so I mean， even interested in the case where P and Q are degree to。That captureds。

So I'm interested in asking questions like are polynomial is non negative。😊。

I have already I have just shown you that at least constrained versions of these problems are NP。

This is an N hard problem。This is an NP。Yeah。So suppose， you know。

 I can give you a sufficient condition for when polynomial。

 So let's just go back to this unconstrained hormone。😊。

So I just ask you is a polynomial non negative。P第份。Multtivariate problem。拿那个你方。So here is one case。

 suppose。Be thanks。Can be written as。The sum， oh， suppose t of x can be written as h of x。Squared。

That it's clearly known。It's the square of some object。反呢。

Pak can be recognized the square of a polynom。Right。



![](img/2ccad39b1eaa1ea5b3514f357a213ef3_19.png)

Also， suppose P can be written as the sum over。Of some of squares， some of squares of polynomous。

That it's awesome。So we can ask the question。 so this is a revised question， you know。Given the of。

Does。They have。An S， O， S， sum of squares representation。我。No， I don't know。

 I'm not being able to say whether it's definitely non negative or not。 You know， if if you say， oh。

 it doesn't have a S representation， then I say， okay， well。All back。

But if it does have an I representation， it is not negative， I'm done。😊。

So what we will show next time。Is that this problem？So这个。系。I think。Yeah。

You can ask one more question。If you。Do they exist polynomials。没加。Positive， but not S S。No。

 you looked up the solution， it's not fair。The answer is yes。

 they do exist polynomials which are positive， but not as。😊，嗯。喂。

there are some results which show that you can。Actually。

 every positive polynomial P affects greater equal to 0。😊，Andlies there exist。Q and odd。

But Q is the thumb of squares because S so was。Plus that P of x。If vehicle to queue。

It's a action function。Okay so。这 is some some 생각。Due to ML。This won't be directly relevant to us。

But it will come along the way when we start talking about Ss， we will start talking about Ss。

Not this Friday because I don't have time to prepare my lecture。

But we'll talk about it when we come back after next week's break。Next week， by the way。

 there is a break because Im moving， but after that we will come back and we will talk about SOOS so when we come back just push this on your stack。

😊，Will answer the question does P effect have an SO S representation， we write an SP for it。

 you will see an SP which is do simple。😊，啊。And then we'll， then you know， go further。

Will use these to。没。To develop a slightly more general framework work。

And this is this is a very nice framework for those of you who are interested。

 this is work thats been developed by Lasre。😊，把正咯。I'm sure I'm forgetting a couple more names。

 but these are maybe the two names that come to mind。

But it's a very powerful hammer that is good to know。So， for now。This。

 this is the question that we will solve， and then well talk a little more about somes source square of poly。

So let's stop here and we will continue on Friday Friday we will just talk a little bit about online algorithms and then we will take。

