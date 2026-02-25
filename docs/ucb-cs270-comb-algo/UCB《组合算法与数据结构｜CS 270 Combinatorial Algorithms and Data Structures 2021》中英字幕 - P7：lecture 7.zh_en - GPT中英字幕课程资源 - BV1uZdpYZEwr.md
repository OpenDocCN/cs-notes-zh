# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P7：lecture 7.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_0.png)

Thank。Okay， so。The first plan of for today would be we finish an algorithm for robust in estimation。



![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_2.png)

嗯。

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_4.png)

Okay。😊，So if you recall the problem。You have a。嗯。You have a data set， which is a set of points。

Endpoints。X1 through xn。And out of which one minus eilon of them。Andre in layersar。And F7N outliers。

Which have been inserted by an adversary。Adregresssally。

 as in he gets to look at the data points that you have。And he look。

 he decides what outlets to add and how many of them to add， let's say， less than epsilon。



![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_6.png)

So I'm just trying to。Yes。I'm sorry I'm having an echo here I'm trying to avoid that in the recording。

Yeah。

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_8.png)

Okay。そご。Okay， so we want to estimate the mean。Do people hear an echo？Okay， great。

So we want to estimate the mean of the distribution。Yes。So here's the approach that we'll take。嗯。

So imagine this is our data set， the blue points are in layersar。And the red points are outliers。

And we try to fix this。

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_10.png)

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_11.png)

Thanks。

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_13.png)

Okay， that should take care of the audio， echocho， thank you。the blue points are in layers。

 the great red points are out layers， and of course we don't know which points are which。

So the hope is， you know， we will。Select。Some subset of points。

 as in we want to filter out thelayers， but it's unrealistic to hope estimate to believe that you can actually。

Precisely take out all the outliers。And so what we'll do instead is， you know， we'll find。Yes。三。

Some other subset。Of points。W whichch might include some inliers and some outliers。Right。

 so we want to find some subset of points。Okay， so and then we want to hope that the new the mean of this subset of points after this sort of filtering is close to the true mean of the inlayers。

So how can we achieve this？So in order to achieve this， let's。

An important notion that we would want to define is this。Notion of stability。

So I'll define it first for a data set， and then we can define it for distributions。So。

So here's the definition。It take a data set， I guess。I I just mean a set of points。

If we take a set of points。It is stable。If。You know。

 I cannot change the mean of the data set by removing a small fraction of the elements。Like， if。Mean。

It does not change。On removing。Let's say Epsilon N。Elements。

So no small subset of elements can drastically alter the mean if you take them out。

That's a stable set， so formally what you want is for every subset。

If I take any subset of let's say one minus epsilon n elements。

If you take any subset of at least one measurepsilon elements。

 if I look at the mean of just that subset。That must be close to the true mean on the dataset。

Of the of the of the set。So I guess there are two parameters here one is the number of elements that you remove and the other is how much the mean shifts。

 so actually what we mean is we mean as a subset of points is epsilon delta stable。

If removing an epsilon fraction of the points moves the mean atmost Dlta。ok该。

So it's sort of a set of elements whose mean cannot be altered by small。

Substs of removing small subset elements。Okay。And so。Okay， so what's the claim the claim is？Firstly。

 here's an assumption we'll make and it we'll see why that's true。

 the assumption is the in layersarers。If I look at the in layersar。嗯。

Let's say they are Epsilon Den table。So what that means is you right like let's say the inlayers are chosen from the Gaussian distribution right so these are actual truly samples from the Gaussian distribution。

 no adversarial elements there and suggest the in layersers among themselves are epsilon data stable so that makes sense because if have a lot of samples of the true Gaussian distribution no you know no adversarial examples if I take out any subset of a small number of them I don't change the true mean so that makes sense so let's assume that for a moment so this subset the green set here Dn has a property that that it's stable。

ok。And what we will do。This， will find。Subsid s。This set as the red set that we find。

Which is also Delta epsilon table。And it has a lot of points， right？Okay。

So like what we'll try to do is we'll try to find a subset which is epsilon del table。

 of course we like you know if we found the in layersars。

 if s is equal to the in layersar we' would be happy。

 but you know it may not be right S can be some set which has some in layersers in some outliers。

 the only thing we know about s is that it is also a stable set。ok。So if these two happen。Then。

 I claim that。These two together imply that the mean mu of the set s。Is。Close。

To the mu of the in layersars， which is what you want。Like what you want is a。Yeah。

You want this to be true。Let's say to delta。It is the game。

So I'm saying that if you find a stable set， then its mean is actually close to the true in layer mean。

Okay， why is this true， Well， it's basically because of the。Overla know the intersection。I mean。

 you should imagine these sets both DN and S to be nearly everything because they only exclude an epsilon fraction of elements。

 they are nearly everything， so imagine them to be like 99% of the elements。Okay。

 so you have two sets which pick up 99% of the elements。All right， so they are here now。嗯。

Look at their intersection。ok。So。You know， suppose。Basically。

 if I look at t is equal to s intersection， the in layers， the in layers that are in the set s。ok 诶。

Well。This set T is。Also a large set， right It excludes a small number of elements of SNDN so by。

You know， epsilon Delta stability。Of this of the in， because the in layers are stable。

You know that the distance between。The in layerer mean。And this。Mean of T is small。Allright。

And again， by the same by epsilon Delta。Stability。Of the set S。We have the same property that the。

Mean of the set minus the mean of the。subsetet T is， again， less than delta。Okay。So therefore。

 by triranangling equality， the in layersarers and the。

Set as have said very close to each other means very close to each other。

Just to say it in a couple of sentences。Both DN and S have the property that deleting small number of elements doesn't change their mean。

 so the mean of Dn is close to the mean of T and mean of s is also close to the mean of T。

 therefore mean of Dn is close to mean of s。It very happy。

Right and that's it so so all we need to do is to do the following we want to given a given a data set with some in layersers and outlays。

 we need to find a set that is stable。Okay，If we need to find a subset of elements that is stable。

Okay。All right， so that that's the broad outline， so now we'll see how to find this stable subset。So。

In order to。You know talk about finding stable subsets We need an efficient sort of characterization of stability or an efficient sufficient necessary condition for stability like for example。

 this definition of stability， you see that it's actually。

Not atable definition because we're saying for every subset。The of the of your set。

 the mean should be the same as the entire set。 So there's no efficient way to verify it as。

Where if check if a given set is stable， let alone find a stable set。Okay。

 so and that's what we'll do next we'll see how。You can find you can define an efficient。

Characterization or efficient， sufficient condition。For stability。Of I set subsidtive points。O。

Any questions on this？Yeah， this is just a sketch of the algorithm we'll get go through a little bit more detail now Al right。

 so okay， so how do we。So before we get into the algorithm。

 let me make a slightly more broader definition。Because we'll be dealing with not just sets。

 but probability distributions， let me define something。More gender， so。Okay， so okay， so。Right。

 an epsilon filtering。Of a。Seid。You know， if you have a set of data points S and Epsilon filtering is another is any set。

嗯，B。With the coordinate of T is at least one minus epsilon S。

So an epsilon filtering is something where you throw over epsilon fraction of the limit。

 you filtered out epsilon fraction of the elements right it's a natural difference I just want this word epsilon filtering instead of saying。

You throw away small number of elementsments， and epsilon filtering is something where throw a small number of elementslaments。

Okay， that's an epson filtering。But well want this definition also for not just sets。

 but also for distributions， so here's a definition。A distribution。Did in。Is a。Epsilon filtering。

Of a distribution。Data。So intuitively， you have a distribution theta over let's say， R to the end。

 like the Gaussian distribution or some distribution or R to the N and an epsilon filtering is some other distribution which looks like you threw away an epsilon fraction of the elements。

 like you filter it out an epsilon fraction elements but a clean way to define this for our purpose。

 is that，Thetan is any distribution。A distribution is an epsilon filtering。

Of a distribution theta if for every point x。Like the probability。

Under theta n is not much higher than the probability under the original distribution theta。

Right to bit。嗯。When we're talking about sets that are saying you can remove an epsilon fraction of points when you're talking about distribution。

 it turns out it's cleaner to talk about for every point。

You can increase its probability by a multiplicative factor of one perception on it's sort of intuitive the same thing。

Yeah。Okay， so that's the definition of an epsilon filtering。

 but for your mind if you just keep or think of theta nness gotten from theta by deleting an epsilon fraction。

Elements。Okay， so that's an epson filter。 Okay， so now we are ready to define true stability for。

Distributions， okay， a distribution。Theta is epsilon Delta。Stoo。If for every epsilon filtering。

 no matter which way you filter that distribution， you don't change the mean。By much。

 you don't change the mean by much。 So I'm using mu of this theta to be the mean。几。

It's what it's basically what we had for stability just now for distributions。

So Gaussian distribution is actually stable and you know we'll see a very easy。

AS condition under which a distribution is stable。Okay。All right， so that's good。嗯。Okay。

 if that's clear， let let's let me now state sort of the main。Sort of lemma or the mean lemma。Which。

Which is going to be。嗯。What we'll do is repeatedly。Okay。You give me any distribution。

I claim that it has some stability， what is its stability。

 a distribution theta R again is Epsilon delta stable。4。Delta equal to。Square root of。Epsilon times。

The blood， the。Operator norm of the covariance matrix of theta。So operator norm is just the， I guess。

 I mean， just the largest eigenvalue of the covariance。Mas a。Right if you recall。

 we had this intuition even last time， basically if you give me any distribution。

The claim is that if you give any distribution。Of points。If I draw these ellipses。

 that ellipsoid that I get by the covariance matrix， a covariance matrix sort of gives you。

 the mean gives you the center of the ellip side and the covariance matrix gives you like the shape of the ellip side that sort of encapsulates the data set or the distribution。

And the operator norm， the lambda max of the covariance matrix is basically the length of this longest axis of this ellipide and the claim is that the claim that this is saying is that if you give me a distribution whose operator norm of the covariance matrix or the largest eagonoid of the covarience matrix is small。

Let's say this is Lambda。is得。Then。This distribution is actually stable if you take away an epsilon fraction of the points。

 you can only move the mean by square root of epsilon times lambda。

So all you need for stability is just that your distribution doesn't have very large eigenvalueage for the covarience matrix。

So now we can see that clearly the Gaussian distribution is。

The standard Gaussian is very stable because for the standard Gaussian。

 the covariance matrix is just the identity， so you'll get epsilon times square root epsilon stability and you can it's a very easy to check sufficient condition for stability。

几。Any questions on this？So we'll see a proof of this。

 so today Im actually decided to do most of the details。

 so I'm sort of you know going over most of the details of the argument carefully。嗯。So yeah， let's。

Yeah， let's see how this goes。So this is actually the most critical lelemma that we'll use。And。

So this is。Yeah。Like what do we need to prove， we need to prove that。

S you give me any filtering of this。Okay， suppose the in is an epsilon filtering。Of data。Okay。

 you just threw away an excellentpson fraction of points to get beta in。

I need to prove that to prove that the mean of theta n。Mineus the mean of theta。Is utmost Dlta。

The mean doesn a moment。Okay。Okay， so I'm going to do I mean。I'm going to do a proof which。

Goes as follows。So firstly， I'm going to make a claim。Here's a claim。You can write theta as。

A convex combination of the。Things that you of the in layersars are the things that you。Left。

Bless the things。That got filter out。2。Yes。I mean， don't worry about what I'm writing right now。

 I'll explain this but。嗯。Yes。Okay， so so the claim is the claim is just that you can write your original distribution as。

A conve combination of your in layers or the or not the in layers intuitively we want them to be layers but you can write as convex combination of your filtered distribution and something and the rest that you took out okay it is sort of you know intuitive very obvious if you if these were not distribution but sets and you actually took out an excellenton fraction of the。

Elements then it all I'm saying is the original set is equal to things that are left plus an epsilon fraction of things that took out right and and now you know we are talking about convex combinations and so on because these are not sets but they are actually distributions over sets these are distributions over point like where they have weights on them not just set sets。

 but they have weights on the elements the probabilities but you know。

Like all I'm saying is that theta out is a distribution if you define theta out like this。

If you define the out like this。And if you define gamma like this。Then。Theta out is a distribution。

And， you know， theta is equal to whatever1 minus gamma， theta n plus gamma theta out。Okay。

 just give us check。 This is。Okay， so why do why did I write the original theta like this。

 You'll see that I'm going to appeal to another neat。Identity， here's another identity。 Okay。

 suppose you have， suppose。You have a distribution theta。

 which is comicx combination of two distributions。Okay。

 we have a distribution theta which is a convex combination of two distributions。ow诶。

What can we say about the mean and the covariance of these things right So it's look okay。

 so so firstly， the mean is easy right， the mean of theta will actually also be the convex combination。

 It'll be mean of。Did得 in。Times 1 minus gamma plus the mean of theta out。Right， this is。就是。

It's an identity， can check that it's true by just writing what the definition of the mean， right？

Okay， that's easy now this， what can you say about the covariance matrix？

So covariance matrix of theta。I'm going to write down the formula。 It's equal to。

1 minus gamma hole squared times the covariance matrix of the in。

Plus gamma squared times the covariance matrix of the out。Plus2 gamma times 1 minus gamma times。

M in minus mu out。这也是就是。So i点样。嗯。As we write it clearly， plus2 gamma times1 minus gamma times。😔。

New of data in。Minus mu of theta out。M is a vector， not that mean is a vector。So。New did in。

Minus mu of theta out。😔，Transpose。Okay。So。You know。ItBasically it's an identity， it's an equality。

 right。And sadly in our world in our like in our world as in my world at least I rarely see any equality that's actually nontrivial as in most equal that I see are provable by computers isn't you substitute their definition then expand it out things with cancer and left hand side equal go right hand side none of these equal that I write in this class will be true for any I think most I don't think there are any equal that I wrote I'll write in this class that true for any deep reason apart from okay LHS is good RHS expand out things with cancer so just take me take my word on that for this yeah。

It's very hard to find like you discover new equalities that are true for non trivial reasons in our world only inequalities are non trivial if you go to pure math。

 maybe you'll find。Equalities that are actually true for nontra reasons like。

Sation1 over n squared is equal to pi squared by6。That's anequ that's true for very non trivial reason。

This is not like that yeah so we'll yeah， so just trust me that these equal are true are just expressions you can expand out and okay。

 that's for reason why。Writing these claims this way。 Okay。

 so now we just use the claim as a black box right Okay， so professor， okay。

 so what do I need to prove， I need to prove that the mean doesn't shift by much， right。Okay， so。呃。

Right， so， so what do I do， Well， let's look at。In equation 2。Okay， in equation2， what do you do。

 let's apply you know， hit hit equation2 with。A play。I guess we transpose V。Right to。Where。

V is equal to the unit vector along。Theta in minus。Me of the out。是。Okay。

basicallyically if I look at this unit vector。V along the。The difference between the means。

And I hit both sides of the equation2 with that。Well， okay， firstly on LHS， what do I get。

 I get v transpose covariance of theta v okay， since v is unit vector。

 this is at most the operator norm of the covariance matrix。Okay， that's nice。

Right this is what it is。 Okay， now what about the RHS。Well， RHS， okay， so I get。We transpose。

Some1 minus gamma squared， some covariance v。Plus， v transpose gamma squared covariance v。Covariance。

 some covariance V， okay， the first two terms。嗯。Right， but。

And then like the last term is what's interesting， the last term I'll get two gamma times1 minus gamma。

Note that this vector in this claim is actually V right is not the unit vector along v。

 but it like we normalize this vector together。So really， the third term really becomes。What we want。

 it becomes the distance between the in layerer mean。Minus the outlier mean。Hold square。这。

The first two terms are whatever they are， and the third term becomes two gamma 1 minus gamma。嗯。

The in like the in layer mean minus the。Outlayer mean square。ok。So and so what do we do now。

 well all we are going to use about the first two terms is they are greater than zero right so so you get RHS is at least。

I'm just going to drop these two terms because theyre greater equals 0。

 Why are they greater equald0 because the covariance matrix is always a PSD matrix。

 So we transpose something a covariance matrix v is always a non negative quantity。

 So I'll get RHS is at least two gamma times one minus gamma times the norm theta in。

Minus the data out。Oh it's great。是。Okay， and that's it。

 So now we compare L right So this is equation one is equation2。 We just put one and two together。

 we are almost there。 we get。I'm just going to sorry。I'm just going to write it here。

 So it's me of theta n minus me of theta out。Co school。let me not use。Yeah， squared。Is at most。

Square root of the。嗯。I guess the operator norm。Of the covarience matrix。Divided by2 gamma。

1 minus gamma。Okay， that's it。嗯。Yeah， that's that's part right and just applying one and two together。

 And now you know， we are。Kind of there， I mean we are almost there。

 we got the distance between the in layerer mean and the outlier mean。Right。

 we got but what we wanted was the distance between theta and in me， but you know。

 so what we care about is me of。Theta minus me of theta in mean。

The whole set and the filtered set that's what we care about， but this is actually equal to you know。

 if you just substitute for me of theta， this is actually equal to。Gma times。Inment。

Minus outlier mean。Yes。This is just I'm just substituting the expression for the entire mean in here。

And I'll get this， and。So therefore you get a bound， which is gamma times。

Square root of the covari matrix of theta。哦不。Tta by 2 gamma times 1 minus gamma。 And this is。

What is this， I substitute for gamma， I guess I had gamma somewhere。

 which is epsilon by 1 plus epsilon。Basically， you just get what you want。

 you get square root types along times covariance matrix of theta。The operator alone。是。对。Yeah。Yeah。

The the I mean the。The intuitive idea is exactly， it's very simple as we said earlier and this is just the know just write out the proof and basically these equalities。

 this claim makes some of the computations easy you don't have to do complicated computations once you have this。

Can。Okay it's really square right so we got the we got what we wanted so nice so okay。

 so basically we are almost there what we we now have a very nice characterization of stability given the data we can actually verify that it's stable。

Without actually checking every possible subset of one minus epsilon。

Fraction of what fraction of points we can it's a polynom time algorithm to check for stability you just have to compute the covariance matrix。

 compute the largest eigenvalue of the covariance matrix and youre done。Okay。So okay， that's good。

 And so now all we need to do is， okay， so now we。At least we can recognize the answer if somebody hands us one。

 if somebody hands us a stable set。We can recognize it by computing the largest eigenvalue。

But now we need to find the stable set， right that's the sort of the next level of thing。Okay。

 so how do we find the table set？So。So I'm just going to write what it means to find a stable set。

Okay， so basically we have our original data set。X1 through xn。And our goal。

Is you want to find a stable set or a stable distribution， so you want to find some weights。Okay。

 what are these weights well initially we our distribution is。Like initially。

 all our weights are one over the size of the data set， right one over n。

Which sort of is like the uniform distributional or data set。That's our original distribution。

 What you want to find is we're going to throw away some bad points there so that what is left is actually a stable set as in it。

It satisfies these properties。 Firstly， right， what do we want we want。嗯。We want。We don't。Like。

 we want。Right we want W to be an epsilon filtering。Of the data set。

Right so so the constraint to say epsilon ws and epsilon filtering is that no point it's the probability of every point should be at most one plus epsilon times its original probability Or probability was one over n every point was equally weighted now you want to modify the weight's a little bit increase the weight of some points。

To one perception or N and maybe delete some other points。 right， That's your good。 So， so we。

 these are the constraints you want on W so that you want。

These weights to be at most one plus epsilon or n， of course， these weights to be non negative。

 sort of it's a distribution。And if you want it to be a distribution。

 you want some of the weights to be one。Okay， so you're trying to find her。Mistribition。

So this is so far vig， I guess the crucial thing is。We want the covariance matrix。

Of this distribution given by W。To be small， right， you want it to be at most lambda times identity。

Right，Like that's what it means to say or like。对对啊。

Right that gives us stability we want to find a stable subset。So this gives us stability。So嗯。

So let me in a covariance matrix， if I write it， it's sum over WI。X I minus mu of W。

Times X I minus mu of W。Transpose， that's the coerence matrix。

And you want this matrix to be at most lambda times divided。食 clear。So。

Essentially we want to find some probability distribution or data set。

 which satisfies these three properties。Ws gives you the distribution and their covarience matrix is small。

Okay。So this is good， this is exactly what we want the first two constraints are also nice because they they look like they're convex constraints。

 they're like really linear constraints。Okay， the third constraint is a little bit subtle， Okay。

 why is it subtle， it's a dig3 polynomial in W。Because W is here， that's the weight of a point。

And me of W， what is the mean under a distribution W that is also summation W Xi？Right。

So the whole thing became a degree3 point。Right， and that's the reason why。

It's a little bit more subtle， right， you can't just。Use convex optimization。

If this got to be this issue got do with this issue that covariance is sort of。

Talking about how stretched it out your ellip side is like the operator norm of covariance。

 like you want the ellipide to be sort of nice and round， that's what you want。

But then to even say how stretched out you are， it's with respect to the center of the ellipseide。

 which is a mean。And as you start taking away points， you also change the mean。

 so the center of your ellipsoid also moves as you take points out。

 so therefore it becomes a more complicated expression。Like it's not， as you can see， it's cubic。

Okay。All right， but you know， why does this even like make sense， well。

 if I look at the in layersars， purely the in layersars。Okay， what are the in layersars let you know。

 I know that my data set has a true in layersars， like let me call them D in。Right， and if I pick。

 if I。Peak W star is like。Uniform distribution or in layersars。

So basically if the point is an inlier， then you put  one over d in weight on it and you don't put any weight on the outliers。

 like if you could find this W star。You can check that W star satisfies。All the constraints here。So。

You know， wishful thinking if you found W star you would be good， at least this is a feasible thing。

 these constraints are feasible。あ。We just need to find out a way to find this。Wais。O。

Any questions so far？Oh。For the， if we choose not to include it， does it have to be a weight of0 or。

There's a question about whether this is a completely separate algorithm we covered last time for robust mini estimationimation of PCA。

 we really didn't do an algorithm last time we just sort of did an intuition of or if it stretched out you want to delete this。

 but when you get into the details of how we are going to do it， how we are going to delete outliers。

 this is where we end up because the issue is complicated by the fact that every time we delete an element。

You also shift the mean you just deleted an element because too far from the center。

 but then once you take it out， you have a new mean and now。You know。

 maybe some other point is far from the center and maybe you'll like what prevents you from removing all the elements this way or。

You don't know which word is are in lies， which are outliers， so it's not clear how to do that。

And so that seems to be the issue yeah。Yeah， any questions apart from this？Okay， so the question was。

 there's a question on whether the distribution D is uniform， yes。

 so what we are going like right now what I'm treating the situation as。

Let's not worry about where which distribution the data points came from。

 maybe they came from a Gaussian or whatever， but let's just。Sam have a data。

 X1 through X1 is our data， and let's think of it as uniform distribution or the data that I have。

 the empirical mean calculation。And of course。Yeah。

 once we get our mean to be close to the empirical mean of the inliars。

Well also be close to the true mean of whatever distribution these data points came from。对。Okay。

 but all right， so now you know all I need to do is to show how to find these wis right so there are many ways to find this Wis there is a way to make that filtering approach that we discussed last time work the filtering approach being the following you somehow compute the covariance matrix you find which points are too far away you delete them and then you find some other。

Thing， you know， repeat this process， you have to do it carefully， but you can make it work。

But I won't go， we won't do that algorithm because someone analyzing that algorithm gets a little bit more complicated because you need to prove that。

要。As you stop start deleting outliers。You start deleting points。

 you don't delete more in layersers than outliers。Right that's how you ensure progress Otherwise you are in trouble。

 so so it gets a little bit more messy， I guess all I means is just gets a little bit more messy。

 so here will you know for。Presentation purpose I'll pick a clean version。

 which is easier to just do it。And the clean version is we'll just use an ellipoid algorithm。

Okay it's of course an inefficient way to do it there's a very efficient reasonably efficient filtering based approach it just takes more it's just more messy okay so what are we going to do were going to find WI by by find WI。

嗯。Using aip。 Okay， so firstly。What's the situation well you have this convex set？

I'm just going to draw simplex。This is like the set of distributions。We satisfy these two properties。

Okay， you have this nice convex。Okay and you have a point in the set that the true in layersers。

 if I pick that I would satisfy all the constraints that I want I mean it'll be the ideal thing this is WI star it's a true thing and all I need to now for the ellipard algorithm to work is I need a way to just。

Given any point。あ。Like if I give you any point， W。哎。For or algorithms。

 might just need to be able to find a separating hyperplane。Or a hyperplane such that。

WS star is on one side of it。As long as I can。Tell you which way to go give you a hyperplane and tell you go to the left or go to the right you can run aip side right you can repeatedly do this and then you will end up with you know the true true WI star or it get very close to it。

Okay， so I just need to given any point W， I just need to be able to point you in the right direction。

Okay， and so how do I do it？Well， okay， given you're given a point W。And。Well。

 if the W is already satisfied the。If it satisfied the covariance condition， let me write it again。

嗯 sorry I should。Like if the operator norm of the covariance matrix for W。If this was small。

 then I would be done。If this was less than w， then I would say okay。

 use this W and everything will be done so it's not small。

 okay it's a cubic polynomial in W and it's small， it's not small。Okay， so now I need to tell you。

Hyperplane and the direction to go。So here's the hyperplane。I'm going to define L of y。

As the following linear function。Okay， actually let me before I define L of5， let。

Now let's say the covariance matrix of W has an operator norm equal to Lada。For some lambda。Okay。

 it's equal to lambda。And let V be the top eigenvector。Okay， so we transpose covariance of W。

V is actually equal to lambda。Okay， that's。Okay， so now I need to tell you a way to go。

 right so I'm going to define this linear function。So I'm going to write the linear function。

 then it'll be I'll tell you what we just did there。Sorry。是。Okay。

 so what we just did was firstly note that it's a linear function of YIs。Lineal function of y。 well。

 basically all we did was the expression that we have here for the。

Covariance matrix of w it as as I said it's a cubic it has three w's in it there's a weight here。

 then there's a weight inside this mean and then there's a weight inside this mean it's a cubic so I got a linear function by just。

You know， what I did was I left。This W as is。This W as as in fixed two of the Ws to be W right and only if I only vary。

The W outside， if I only vary the W outside， it becomes a linear function。

 you see that it's a linear function of y。Like for fixed W， X， whatever。

 all the things are fixed here。Fixed X X size， of course， fixed， the W is fixed and the v is fixed。

This becomes a linear function，And it's in the same space as it's a linear function of the weights。

 LO Y is a linear function of the weights。Okay， and the claim is just， of course。

L of w is actually equal to lambda。That's， of course true because。You know， just by definition。

 L of w is equal to lambda。Okay， and then the。I love W Star。Like the true point。

 the true optimum or the not the true， well， they the true in layersar。

That is actually will show is much less than lambda。Which is it's something like。eppsilon lambda。

给 me show。So that means that。You know， if I look at L of y less than lambda。This is a lean is。

Hyperplan。Is a hyper plane so that。A true answer is on one side of it。 A W is at the。

On the Hy planee。And through answers on one side of it。ok。Okay。

 so we need to show that L of W star is at most order reps one lambda。Yeah。Okay， that's。嗯。So far。

 so good。Okay， so let's see why I love W stars it's kind of。Like when you try to actually do it。

 there's so many details in this sort of a thing， but the basic idea is very simple。

But pale of W star， to remind you what W size W star is uniform distribution over in layerss。

 the true answer， like which we would want。So I'm just going to substitute for the y as W star so it so let me just write what it becomes the expression becomes。

嗯。Yeah。The WA star is one over cardnet T FS。I did so。1 over the star is just all in life， right so。

Yeah。It's WSL uniform distribution or in layers。Thanks so。Yeah。Okay， I should put in。

 of course I should put in V transpose me here。Okay。是。结稣。That's good。Alright， again。

 I'm going to do my thing， and I'm going to write。I'm going to write an equality and。

Trust me on that there's no content in it it's well there is some content in it， but it's not。

It's just algebra manipulation。So嗯。So this is algebraic fact。系。し。诶。对。

It's's like it's not super important why this is true， but if you want to。嗯。嗯。Yeah。Yeah， okay。

 so let me not go into why this is true theres I mean there's some explanation of why this is true。

 but it's not important just for now let just to think of as an algebraic community， which is this。

Okay， so。Basically， what we did was we sort of。In recentered the variable。

 these variables are all me of W。They were somehow in the wrong mean。

Because you're weighing every variable by WI star， it want me of W star here， whatever me of W。

 so I've inserted me of W star and it removed me of W star。Okay， so。Okay， anyway。

 so the first term is actually we transpose covariance matrix of W star。你。

Which is nice because remember W star is true in layers and true in layersar are a nice stable set their covariance matrix is small there。

And the second term is at most。The length of this me of w star minus me of w。记得啊。

So the first term is basically since the covarinance matrix of the original distribution。

Like the true in life is order one。 Okay， it's identity let's say it's a Gaussian or something。

 So the first term is order one because of that。 the second term is what we need to understand。

 Well the second term also I can。Okay， so this is where。

Our original argument will come into play is this is truly the。The place where啦。😔，Why is this small？

嗯。This is where our original argument about。Two sets and the intersection。

 remember the two sets and the intersection， that's where it's coming。

Because note here that W star is the in layers that is the true set。

And W is sort of our current candidate in some sense。And why do we say they are small。

 their distance is small， well because of the you go through the intersection of the two。水先。Okay。

 let me write this as me of w star minus if I take W and throw away all the outliers。是。

Return is supplying triangular equality。ok。Right，What is this？诶。Hearry。Note。W intersect D in。Is。

Order， epsilon filtering。Of W W star。And then similarly， W intersect D in is an order epsilon。

Filtering。Of W。Okay， so just by using our bound， both of these terms are less than order epsilon lambmbda plus order epsilon lambmbda。

Orpsil on now。嗯。That's the idea。Yeah， any questions so far's a it's a little bit of。Yeah。

 I was hoping we'll finish a little earlier， it's a little bit of a strenuous。H today， but。

I think it's。It was good， I think。Like you see that like sort of once to take the basic guide intuitive idea and make it into an algorithm。

 theres so much of additional detail that you need to fill in and。嗯。In fact， this okay。

 we described the algorithm， but it's not a satisfactory algorithm because it's this crazy ellipsoid algorithm which you need to use now。

You would rather want。A much more efficient filtering algorithm。Which sort of keeps。

Filtering out points until you have a nice set。Yeah。Any questions on this？Okay， al right。Okay。

 there's a question。 How do we know that this is。Small， well， okay。

 that's what I assumed was that L of W is lambda。 So I assume that。嗯。10 of w is equal to lambda。

For some lambda， for some lambda。If L of w is equal to lambda。

 that means the operator norm of the w matrix is like is exactly equal to lambda。Let's say。

 let's call right then I know that。An epsilon filtering of it。

Will be at most order epsilon Lambda away。嗯。So it's a little bit the Lada is used in a little bit of a circular fashion here because I define Lambda to be L of w。

Suppose suppose L of lambda is equal to w， this is a definition of Lada。

 the claim is that L of w star is actually or much smaller than it。And therefore。

The hyperplane L of y less than equal to lambda is a hyperplane such that W star is on one side。type。

Any other questions？Okay so okay， the question is could you de provide a high level description the filtering approach Yeah so the filtering approach is basically at a high level it's really you know。

I mean at a very， I guess at really high level it's really you have some data set。

 you compute the covariance matrix， you find which。You know， you find the top eigenvector。

 the covariance matrix and you see which points are。

Close in aligned with the top eigenvector of the covariance matrix。

You delete them and you sort of recur， but you have to set the thresholds of these things right youre to set the like when do you delete points and so on you to set it right and you had to prove that at each point you actually。

Delete more。Outliers thened late inliers。Yeah。Yeah， this is in some sense like right。

 so this is a like a whitening procedure whitening okay。

 so for those who know don't know whitening a data set is to make。

Is to take a data set which whose covariance matrix is。

Not the identity matrix and make it into make its covarience matrix， the identity matrix。あ。And。

This is like a version of whitening where you're deleting points you want to delete a small number of points so that what's left is has a covariance matrix that's。

Like the identity matrix。Okay， so so that's the。Okay。

 that's all I want to say about robust mean estimation。

 there's a lot of work on it in the last few years。Yeah。Okay。

 at least we saw one algorithm with I think with all the proofs。

 so only proof that I did avoid is the proofs of equalities。But apart from that。

 piece saw all the proofs。All right， so so Nick。Let me just start talking about what we'll do next。

In linear algebraBic primitives， the next thing which we'll consider are tensors。

So let me just start by describing what they are and so on so firstly you know。Operationally。

 a tensor is。It's just a higher dimensional area of numbers， you could say that。So。

Like a matrix is a two dimensional added。嗯。It could say operationally。

 it's just a high dimensionary of numbers， so you can concretely for example。

A tensor with three modes。Or three， you could say。You would want to say three dimensional tensor。

 I guess it's a reasonable。嗯。嗯。Reasonable terminology。

 but sometimes you want to use dimension for the size of the matrix or size of the tensor so it's you could instead say tensor with three modes。

Is a three dimension is just a three dimensional array of numbers， so T is。In R to the power。

 N by N by N。ok，It's a cube of numbers。 Of course， you can always define。嗯。う。M cross R to the power。

 M cross N cross P。These dimensions need not be equal just like you have non square matrices you have you can have this。

 so these are three dimension line numbers。All right。嗯。But you where do they show up， right？嗯。Like。

 why do we put them in an air put them in this？3 dimensionary。 Well， it it's。

Right the correct way to think of it is these things is I mean they are they really signify objects over some vector spaces。

 so for example， a matrix。If I give you a matrix M， there are two ways to think of a matrix。

 One is it it a matrix M specifies。Cdratic form。Excell， let me use。Yeah， it means a bilinear form。

A matrix M specifies a polynomial in x and y。A bienar form。A linear map。That takes e vector。

And another vector。And outputs a real number。Right a matrix and can either do this。

 or you can also think of a matrix as something that you know。It takes a vector。

And outputs another vector。Right。This is as a linear transformation。

So matrices can be thought of as two different objectss here。

 either the linear transformations or bilinear forms and。What that means is like when you。

When you write on a matrix。Of course you are referring to the area of numbers as a matrix。

 but what you really have in mind is you have some vector space and you have some basis chosen for that vector space and in that basis the linear transformation looks like this area of numbers。

 but if it was a different basis you represent the same linear transformation by a different matrix so in some sense matrices are just physical you know actual realizations of。

An object which is basis free， which is linear transformations or biing forms。Right。

 so and therefore， you have all the。Like how that's why a matrix multiplication is what is defined as it is and not as something else。

 because it really you're not manipulating arrays of numbers。

 you're manipulating linear transformations over vector spaces or bilinear forms。Similarly。

 our tensors youre the same thing， you can think of a three dimensional tensor as one of three things you know。

 it can be something that eats， you know it takes three vectors。And outputs a number。

This is a polynomial T X， Y， Z is equal to sum over I JK， T， I， J， K， X， I， Y， J， Z， K。That's a ten。

 so a tensor can be a trial in your form， right， a 3 dimensional tensor or。

You know it can be other things that it can take two vectors。And output another vector。嗯。

So what is this well， let me use。And this going use T T hat or whatever T hat。T hat takes X and Y。

Okay， and it outputs this vector of polynom vector whose entries are。Some or。啲。one牌。JX I yg。

S over T2 I， J， X I， Y J。And so on， I think you'll get the picture so they still。And of course。

 the final things you can think of it as something that takes a vector and outputs a biin your form。

Out put a matrix， so I mean， so that's how you naturally end up with tensors。alternate。

 you have this array of numbers。You know， the cube of numbers。

The way I would intuitively think of it is if you had a matrix right when you do natural matrix transformations like if you had a matrix Sam when I hit it with a matrix u on the right I am taking linear combinations of the columns of a U of the matrix when I hit it with the matrix v on the left I' am taking linear combinations of the rows of the matrix right so so similar thing is through here so you have a three dimensional array of numbers right you can visualize the three dimensional array of numbers as。

A bunch of slices。these end slices then you know I can apply a matrix on one of the modes which corresponds to taking linear combinations of these these slices or I could slice it in a different way and I could apply linear transmission there you know and so on Okay so that's。

Okay， so that's basically， you know， to get you accustomed these three dimensional tensors and the one thing about。

Where like where do where do they show up well， you can。I mean。

 one natural place where they will show up is just the moments of a distribution。So so far。

 for example， we looked at the mean， meanness was the average of the points。

That expectation of x x from a distribution is a mean of distribution， and then the covariance。

We said was the average of x minus mu x minus mu transpose right and that tells you like the correlations between pairs of bits or pairs of if I have a random variable x。

Okay， the covariance tells me everything about。Correlations between pairs of elements。

 but let's say I'm interested in correlations between triples right then what do I look at well I look at the three dimensional moment tensor right？

I don't have a notation for this， lets me call this M3 this is a three dimensional moment tensor。

What are its entries。Okay， let me call it just deep。3 dimension or， So T， I JK is expectation。

 X minus。嗯你外。Times xj minus mu J times xk minus mu K。That's like the or you know。

 this is the centered three dimension moment and so you alternately if you're just interested in without centering right you know I like imagine I had just。

If I look at triple wise correlations the of the。Al rate is not equal it's alternately if you look at triple vice correlations of the entries of my vector。

Now， I have N cubed numbers and the natural place to wait to put them is put them as a three dimensional tensor because linear transformations on your。

If you do a linear transmission on your vector x， on your random vector x。

That corresponds to actual operations on the tensor。

 like taking linear combinations of the slices of your tensor and so on。So right。

 so basically tenses。You could say。You could say is one way to can be used to encode or used to。

Write down， I guess， encode。Hed higher order correlations。Of random variables。Okay， and。In essence。

 this is a little bit beyond geometry but。But yeah， okay， I think I'll stop here。

I'll stop here any questions I'm ready to ask。We'll meet on Monday and we'll look at a nice algorithm for tensors。

Thank you。

![](img/1477c0ce2c68f1ae98e1d7472b9e85ed_15.png)