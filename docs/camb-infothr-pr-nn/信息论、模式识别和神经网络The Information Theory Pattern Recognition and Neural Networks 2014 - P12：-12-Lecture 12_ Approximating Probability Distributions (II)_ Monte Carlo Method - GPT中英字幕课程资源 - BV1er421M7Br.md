# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P12：-12-Lecture 12_ Approximating Probability Distributions (II)_ Monte Carlo Method - GPT中英字幕课程资源 - BV1er421M7Br

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_0.png)

Yeah。Welcome to lecture 12。 Today， we're going to be talking about Monte Carlo methods。

Moontic Carlo methods are one of several methods you can have in your probability toolbox whenever you've got a complicated probability distribution that you are interested in。

When we were first looking at simple inferenceprint problems。

 we just did a brute force complete enumeration of all 10 million hypotheses that could account for the data。

 So that's always available as an option， but typically complete enumeration just ends up taking too long。

 The moment you have more than two or three parameters in your problem。

Laplace's method is in the book。 I'm not planning to talk about it。

 The idea of Laplace's method is you take this complicated distribution that's a bit too big to enumerate。

 and you approximate it by a simpler distribution， namely a Gaussian。 So that's a simple idea。

 App the distribution of interest by a Gaussian and Loplace's method does that for you。

 And that can be quite useful for a lot of problems。 We're going to talk about Monte Carlo methods。

 which are ways of dealing with nasty complicated probability distributions by using。Random numbers。

 So we're going to use random numbers today， and。There's going to be two lectures on Monte Carlo。

 a simple lecture today， and then the next lecture will be on advanced Monte Carlo methods that really get us in a good place where we have powerful Monte Carlo methods that can do things that simple ones can't。

 or at least they can do it faster。

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_2.png)

Then the following lecture will be about variational methods。

 which are methods that don't use random numbers to deal with the difficult problems that we are setting ourselves。

Just to remind you， this course has a website and the book， which looks like this。

Hissory online on the web。So here's a little roadmap of where we're going with Monte Carlo methods' going to talk through some very simple Monte Carlo methods and Markov chain Monte Carlo methods which are slightly more complicated and then we'll get on to the really fancy methods and the lecture plan is we've already discussed clustering in this lecture on simple Monte Carlo we're going to get up to oops。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_4.png)

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_5.png)

This far， as shown by the red line， so we'll get up to Atropolis method and Gib sampling。

 leaving the second half for the following lecture。And let's go back。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_7.png)

I want to remind you what we did in the last lecture。 it was about flustering。

This gave us an example of a probability distribution that we were interested in。

 and it it worked like this。

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_9.png)

Yeah。P。The probability distribution we were interested in was the probability of a whole load of unknown means。

 mu 1， mu2 dot dot dot， a whole load of unknown standard deviations， Sma 1， Sigma 2， dot dot。

A whole load of unknown weights， pi 1， pi2， the piequet of K Gasians。

A whole load of unknown assignments of points to clusters， C1， C2， C3 up to CN。

 where you can think of C1 as being which class the first data point actually belonged to。

 and it was either in cluster1，2，3。😡，Up to K。I still haven't completed the list of things we don't know or have I。

 Yes， that's the list of all the things we don't know。接人。The data。

 which was a set of points x1 x2 up to x。嗯。And。The probability we're interested in is the posterior probability distribution。

😡，Pa。All of these things。Given。For data。And。😡，Yes。Given the assumption。That。For data。

Come from a probability distribution with these means and standard deviations and weights and so forth。

 So given that the xs are assumed to come from a mixture of Gaussians。

 that was the model we were assuming in the last lecture。

And we discussed briefly the idea that you could have alternative models instead of a mixture of Gaussians。

 a mixture of some other sort of distributions。And still。

 you would have an inference problem where you are now interested in inferring the unknown cluster locations and sizes and shapes and the unknown assignments given the data。

As a real world example of this。😡，You could imagine that you have 1000 manuscripts that have been transcribed by scribes back in the era when everything was done with with handwriting。

And you take those thousand manuscripts， each of which is a beautiful document full of beautiful。

 curly letters。And what you want to infer is out of all of these characters。

 which characters were written by which scribes， because if you can infer that。

 you could deduce interesting things about the sociology of the community of scribes in the ancient world。

😡，And they're all trying to make the hand of writing look fairly similar to each other。

 But nevertheless， you can actually cluster them and say， a， Yes， that's。

 that's one of this guy's A's rather than the other guys。

So that's an example of why you might want to do this with handwriting recognition。

So what does that posterior distribution look like， Well， if we call all of these parameters Theta。

Then the probability we're dealing with。Is B of theta given all the data and that by base theorem is。

Probably of all the X is given theta。Yes。嗯。I say I'm going to change my mind about how I define Theta。

Let's。I for to be all the parameters that say where the means go。

And then let' have the actual assignment be another thing called sea。

Then what we're interested in inferring is where are the clusters and what are the assignments。

 And the answer is， well， how well did those hypotheses predict what actually happened and how probable。

Yes。52。Those hypotheses in the first place。 And then you normalize。By dividing by。He of state us。

So that's based theorem。And。Often it's a good idea to deal with the logs of things like this because this probability of all the data is a great big product from one to n of probabilities of individual data points。

 and so we often work with log probabilities so that instead we have a great big sum of things like log probabilities plus。

Things looked like this。嗯。Plus possibly some other thing， All right。Okay。No。Actually。

 let's get rid of the plus dot dot dot and let's talk about。W the log。Of fiscally as half。

At given feature。And C， which is the business and the data depend bit。 That does look like this。

 And once you've dealt dealt with some sort of log of square root of two pie。Sigma squared by terms。

 Then you can put a full stop and this is。You has to be correct。Okay。

 and then these terms here will be whatever your prior distribution is。啊。Okay。

 I've got my log pies in there。阿be这行。行行。For this to be true that I have my P of C given feetta。

Thereま？The sum of those is this lot。The logs of the pies being。Coming from here。

 the probabilitybabilities of the assignment， so this isn't the probability the end point。

comeses from。Class， weve assigned it to by sea， and。And then this lot here is。I missed。All right。

 Why am I writing this all out， Well， it's to remind you of what we did last time and to emphasize that the probability distribution we are interested in is something we can write down。

 It has There is a mathematical formula for it。😡，And we can write down almost the whole lot。

 except usually this normalizing constant here is complete pain in the b because to actually write down that。

 we would need to do an integral。Dm D Sigma。D5 and a great excation of overall seas as well。

 because we have some over all the possible hypotheses to get this normalizing cost。

 But it is just a single constant。 It's just one number。So。😡。

What do we notice about this distribution that we are interested in， We notice we can compute it。

 except for its normalizing constant。So I'm now going to define the rules of the game that are going to apply when we're dealing with Monte Carlo methods and variational methods。

The rules of the game。Yes。that we've got a probability distribution that we're interested in。

And it's going to be called P。😡，And it's going to equal P star divided by Z。

And the rules of the game are。That we can。Evaluate。Pacetop。And secondly。But we don't know， Zed。But。

 it is。Of interest。Someone could tell us Z， we would be delighted to know it because remember what was Z for。

 this is what we needed to do model comparisons。 So if you want to compare the theory that says these four clusters。

😊，In your data with the one that says that 7 clusters。

 you need to know this normalizedizing constant for those two hypotheses。

 Then you can actually answer that inference question。So we can evaluate P star， we don't know Zed。

 we'd love to know it， but well be we won't complain if we don't end up knowing Zed at the end of the day。

Goal of the Monte Carlo method isn't going to be to evaluate that。 If we get it， it's a bonus。

And in general， I'm now going to generalize and say the thing that it's a probability distribution over。

😡，This thing here， in this case， the unknown parameters and the unknown assignments。

I'm going to give that a name and with apologies， it's going to be called X from now on。😡，So。

 this is the thing。The unknown。Varis。I'm going to call X while we talk about Montecollo methods。

 So now X is the name。 If we're actually talking about clustering。

 X is the name for the unknown means and standard deviations and assignments of data points through clusters。

 for example。So what else do we say about the rules of the game？ Well。

 what do we actually want to know， We've got a probability distribution we are interested in。

We can evaluate it， at any particular。Any particular。Argument X。 so you can pick an X。

 and we can go there， plug in that value of theta and C and work out what this ho expression comes out to。

And what do we want to do？😡，Well。What we want to do is we want to solve these two problems。

So just a recap notation， we've got a red distribution。

 and I'll always write the nasty distribution in red。It's red， and it's。

Can be written without loss of generality as e to the minus E of x divided by Z。Okay。

 that' was just taking the log of E star。So the assumption is that we can evaluate P star or equivalently。

 we can evaluate E of x， child， or sometimes call it the energy of X， maybe。

So we can evaluate this thing。 What do we want to do， Well， we want to solve problems 1 and 2。

 ideally， Pro one is we would like to draw samples from this nasty distribution。 What does that mean。

That means I want to take this posterior distribution and come up with some plausible representatives of it。

So I want to draw a few times from it and say， well。

 I don't know what the means are and what the assignments are， but here's one credible hypothesis。

 and here's another， and here's another。 I'm tell you what it means could be here could be there。

 could be there。 It could be signed this way that way， the other way。That's task 1。 All right。 Now。

 when I say I'm drawing samples， please don't get confused and think that I'm drawing points in this。

Rice hair。It's I've taken a risk here。 X is now the name for。The unknown variables， All right。

The data is given its fixed， and now we're wandering around in hypothesis basin and coming up with samples from the posterior distribution over hypothesis。

All right。Problem 2 is we would like to estimate some expectations of functions under this distribution。

 What do I mean， Well， let's give you an example。 Let's imagine that we're very interested in knowing whether two particular characters were written by the same scribe or not。

 because if we can resolve that， then we can figure out who murdered King Henry VI or something。😡。

All right， so what would that mean you want to know were these written by the samescribe？😡。

That means， we want to know。For two data points。The end warmth。And and tooth points。

Are there Cs equal to each other or not。And the answer is we don't know， but given the data。

 we can infer how probable it is that they are the same。

So what we want to do is take the posterior probability。Of everything。The feers and the seas。

 given the data。And we want to know the average。Averaging over the and summing over。

All the possible theories about assignment， we want to know。

How probable it is that this proposition is true。 So I'll have the one function that says this is true。

 It's one。 It gives you one if this state statement it is true。

And we want to know the average under this postuserior distribution of this function。

 which is one when the two C's are equal this 0 otherwise。 If we can compute this expectation here。

 then we've got the answer to the question。 what's the probability that those two letters were written by the samescribe。

So what am I saying， I'm saying that the question， how probable is it that these two Cs are the same can be written as？

😡，Pation。Another thing you might want to know if you're doing clustering。Is。He might want to know。

How probable is it that one of the means is somewhere in this book is is in this box。And again。

 you can introduce a function that is one when the mean is in this box and zero otherwise and average that function under the posterior distribution over hypotheses。

😡，Yeah。So。Questions that you have。Can usually be expressed as expectations。Questions of the form。

 What should I believe about this variable。Given the data。So generalizing that。

 the general problem in the Monte Carlo method is someone gives you a nasty distribution and they give you some functions whose average values they want to know。

All right， so that's the setup。And now we can forget about clustering because we've been motivated to want to solve these two problems。

Just in case you don't care about clustering， I'm going to give you one more problem that can be expressed in this way。

So let's wipe out cluster strength。I'll give you another problem from physics。😡。

So this is a problem of understanding a nanomagnet。Because nanotechnology is really cool。

So let's say you've got an a magnet。And you've got。A theory of what the energy of the nanomagnet is。

the energy depends on the state of all the spins in your nanomagnet。😡。

So let's call x the state of the nanomagnet。And let's say it's a tiny little nano magnet。

Made out of 10 by 10 by 10 spins。 So it's got only 1000 little spins in it。 It's tiny。

Or maybe it's a planar object made out of 32 times 32 spins over those are equal to10。

 So we've got 1 thousand spins。And we've got ourselves。An energy function。

Which is the energy of those bins if they're in a particular state。And what might that look like？

Well， maybe it's a nice， simple nanomagnet。The energy involves couplings between pairs of spins。

So each of these xs it takes on the value， the minus one or plus one。

And so X lives in space -1 plus1 to power X。And binary variables， and maybe。P of x。

Given the couplings J between the spins and the inverse temperature beta。

Is each to the minus be at times the energy。Divided by normalizing constant， which depends on beta。

And the couplings， where the couplings。Me of。Determine the couplings J。

 determine the energy in the following subway。 have a sum over all spins。 So some。

 let's say there's n spins。 So sum over n。And and prime。You have a coupling J and。

 and prime cats and。Okay。So that's a fairly standard expression for。

The energy of a magnet with second order couplings between spin。

And what sort of things does someone want to know about their nanomagnet， Well。

 they might want to know， what's the average energy of this thing。Under the distribution P。

 I forgot to draw the distribution P in red。 This is red。He is red and nasty。 It's not that nasty。

 iss it？ It's just a sum of。Coling Heso， we've got fairly high standards of。A redness slip。

But it is nasty because actually， if I tell you， O， here's the coupling matrix。 And I say。

 what is the average entityity， You'll struggle to answer that question。

 You could try to do it by complete enumeration。If you wanted to do it by completing anyway way。

 you'd have to do a sum overall values of x。E of x， red。Here of X。

And that would be the average energy， but to do that。

 you would have to sum over2 to the power N states， which is 2 to the power 1000 states。

And to the power 1000。Is。嗯。😊，Let's put it this way。

 Imagine that you had access to all the electrons in the universe。There's 10 to the 80。

Electrons in the universe。 And imagine that you manage to turn every one of those electrons into a powerful computer。

And that can do operations for you and that you have the entire age of the universe to do it in。

 So the age of the universe。Is actually 2 to the pound 98 peak ofconds。

So this was two to the 266 electrons。So if you have every single electron in the universe being a supercomp fill。

 you doing an operation， every peak second， and you have the whole age of the universe to do those operations。

 You multiply those two by each other and see how many operations you can do with your。😊。

Biggest computer imaginable。 The answer is two to the 364。

 So you can't sum up over all states of a little 10 by 10 by 10 and the magnet by exhaustive enumeration。

 even with。Unverse of supercomputers。So you can't do this。

 even though the energy is a very simple thing to write down， at least I say you can't。

 you can't do it by exhaustive a new relation。Yeah。

So that's one thing you might want to know Another thing you might want to know about your nanomagnet is what's the fluctuations in its energy。

 so you might want to know the variance of the energy or equivalently you might want to know the average of the energy squared if you know both of these and you can work at the variance。

 fluctuations are an interesting thing to know about so you might want to know that。😡。

You might want to know what's the mean magnetization？😡，Of。The magnet。

Or you might want to know what's the variance of its magnetization。

 So you define the magnetization in some way。 It's a function。 You invent it， and you。

Say I am interested in knowing its mean or its variance。

You might want to know the entropy of your nanomagnet。 And that is the average of log。1 over P。

He might also want to know。That。The normalizing constant。Because Z， for physicists is very exciting。

 You don't just have to do basices in inference to care about Zed。For a physicist， Zed。

The log of that。Is essentially the free energy。Of your nano magnet。

 and free energies are fantastic things that you want to know in order to understand all sorts of properties。

Things like heat capacities as well， can all be expressed。In terms of expectations of things。

 the only thing on this list that can't be expressed that way is log Z。Which isn't an expectation。

 It's just the normalic constant。 and the S has got a log Z alert community as well。

 S is roughly the average of the energy， but it's got a log Z too。So。😊，That's a second example of。

A problem that conforms the rules of the game。 We have a probability distribution that can be written as each the minus and energy。

 The energy can be evaluated and at any X quite easily。 It's an easy thing to do。

 But the entire distribution itself is a difficult thing to work with because you I give it to you。

 And I say。Well what are typical states， drawaw me some samples。

 show me 10 random samples of this and you're at a loss， you just look at this function and you say。

 well， I don't know how to draw 10 random samples from this distribution。

A final thing to note is we want to solve problem one。And we want to solve problem too。

They're both of interest。To solve problem 2， which is to know these expected values of things。

 you don't actually have to solve problem 1， but if you have solved problem 1。

 then you can use that as a way of solving problem 2 if you want。 So problem 2。😡，Can be solved。

If problem one is solved。Because if。Someone。Gifs you。Some points。

 which I'm now going go to label with an R for random sample。 If they give you a set of capital R。

Points， X， R。Which do really come from the nasty distribution P because you have solved problem 1。😡。

Then。You can。Estimate。Expectations of functions， for example， if someone says。

 what is the average value of F of x under P。So they want to know this the expected value。

You can estimate that by saying， well， I'm going to write down F hat。And I'm just going to tot up。

For all the points that you've just given me in this random set。

 I'm going to see what the mean of F is。😡，And。That empirical distribution。Okay。

And that means that any functions F。I can just take you the R random points that you give me。

 and I can estimate their expectations。Using those are points。And the bigger R is。

The better those estimates will be the。Closer， they will be to the true value of the expectation。So。

 that means that。It's of great interest to solve problem one。

 and often if the one to solves problem one， we can just spit out answers to Pro  two。

Not all Monte Carlo methods will solve problem 1。 However。

 some of them only give you solutions to problem 2。Okay。

Two final things to emphasize are on the screen here。

We are not trying to find the most probable state。 The goal of these Monte Carlo methods is not to say what is the state that minimizes the energy。

 What is the most probable X， We don't want to do that。

 you might want to do that if you had a different motivation。

 But for the sort of problems we're studying here， We don't want to know what is the most probable state of an nanomagnet。

 because the answer is just what it's the ground state。

 And that's completely unrepresentative or what happens at the temperature T。

 And for the assignments of points to clusters and where do the means go。

 We don't want to know what is the most probable assignment， because then you get silly answers。

 Like， remember last time。We had。Mix of gars like this and the most probable way of assigning points to means if you put the means here。

😡，And here。is to say， well， all of these definitely are in class two and all the others are in class one。

 and that isn't a probable assignment， it's the most probable assignment。

 but it's not very probable because the typical set has all sorts of other allocations where these guys in the tails could be in could go either way。

Yeah。Right。So we're not trying to find the most probable state。

Nor is the purpose of problem one to visit all states。

 we're not going to try and exhaustively enumerate all states in some random way because that would take the lifetime of the universe。

 even for a tiny problem。😡，We're not visiting all states。

 not even visiting all typical states because a typical set for a system will still have two to the very large number of typical states。

So。I'm trying to be clear what we want to do in a Monte Carlo method。Actually。

 what we're trying to do， it would be brilliant if we could just draw。

 say a dozen points independently compete， because once you've got a dozen points。

 you can already get fairly good estimates of functions you're interested in。

 so the sort of value of R that we're interested in is a dozen or maybe 12000。So that's the ballpark。

 And that's true for any size problem。 It doesn't matter if it's a very。

 very high dimensional problem。 Still， all you need in order to estimate expectations of functions reasonably well is a dozen or 12000。

Poins。So let me know。😡，Show you some Montecallo methods。And what we're going to do。

Because we're going to introduce some green things and green things are our friends。

 They are easier to work with。And the green thing will often be called Q。Yes。

And I'm going to work on problems， which I can show on the screen。

 which means there mainly going to be one dimensional problems。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_11.png)

So， here is in red。A probability density， P star of x that hasn't been normalized， but it's a P star。

 and it's got an unknown Z， which is what you would get if you sung the overall values of x。

 which left front lot of this axis。You sum up you star， that will give you Z。

 and then youd have it normalized。So we don't know Z。All we have is the ability to pick a value of X。

 and then the computer will spit out the value of P star there。

 So this picture is sort of misleading。 The real world of a Monte Carlo problem is sort of we don't know where we are。

 We're just we're in Xspace。 And we can ask and pick a place to sort of take up the blindfold。

 And all you're told there is at that point， what is P star there。😊，And then you go somewhere else。

 and you ask， okay， what's P star。 So you're a sort of blindfold person every now and then you can take off the blindfold。

 And all you can see is P star at that one place。 You never get this big picture that you guys can actually see on the screen。

Also， you have the ability to evaluate phi， which is a function of interest and here phi of x is actually a linear function of x just for simplicity。

It could be anything， it could be any function at all。

 and there could be several of that you're interested in。

And what we're going to do is we're going to。Progressed through a sequence of steadily fancier Monte Carlo methods that are going to use random numbers to try and help the the blindfold person。

 So the blindfold person is now going to be kicked around by some random numbers in some way。

 and they're going to take their blindfold off and Cp or rather P star and then they get kicked around it another way and the C star again。

 And somehow the goal is that these extra random numbers that we use to kick them around will actually help them answer problems 1 and  two。

 which sounds a little bit mystifying。 how can giving a blind man some extra random numbers。

 help them appreciate the big picture and correctly answer questions。

 But that is the beauty of Monte Carlo methods that they do exactly that。

What I just showed you was a P that was defined in a real valued space x。😡。

We could also be talking about discrete space like discrete spaces like the spin space。

 which lives in a discrete space with two to the end， two to the 1000。Values。

And so here's a discrete world you could imagine being in。

 And now you're a blindfold person and you can go to a particular place X。

 and you can evaluate P star there， and then you can go somewhere else and evaluate P of that。

 And again， you don't have the big picture。 You can't see all values of P star。

There's far too many of them， and this is a simplified depiction of what that world。

Really look like okay， I'm going to start by introducing。A proposal distribution。

Or a sampler density。So I'll call it a sample density。And it's going to be Q。

 and it's going to be the uniform distribution。不是。So what we're going to do is we're going to say。

 let's assume that we can draw points uniformly over all X。

And we're going to use that ability to then discuss if solving problem2。

 so this won't help us actually draw points from P， but maybe we can find the expected value of phi。

😡，So what I've done here is I've drawn in yellow。However。

 many two dozen random points in yellow and then what we can do having drawn those points。

We can write down an estimate。O。The function。So。So what we're doing is we've got a。

Maasty distribution in ratch。And we've got a simpler distribution in Q that we can actually draw points from。

 So this sample density has the fantastic property that we can。😊，Daw。From。6。And so Q might look。

Like this。Now when we draw points from Q， something you could imagine doing is finding the average of all of these functions phi。

😡，So， as we draw。Random points， we could evaluate Phi at those。

And if we just did this and averaged divided by R， then what we will be doing as r gets larger and larger is finding the average of phi under Q。

 so this would be the wrong thing。😡，And we would get it ever more accurately， but it would be wrong。

 So how do we fix it up， Well we need to up weight each point。In the ratio of P。Over。Hu。Yes。不。

So if we evaluate P at each point as Q。Propos that， if you like。And if we evaluate Q there as well。

 and for the uniform distribution， all of these Qes will just be equal to each other。Then。

Were upweighting points in places where Q is too small and were down weight ones in places where Q is bigger。

And I said P， but actually， it's the P star that we can evaluate。

And then we need a different normalizing constant。And something you can perhaps persuade yourself of is that。

A normalizing constant that will do the job is the sum of all of these weights。So P star of X。Over。

Que of exon。So what I'm doing here is。In general， called important sampling。

So we can't draw points from P if we could， then we would have a way of solving problem2 What we do instead is we draw from a different distribution that we can draw points from and then we correct。

 we reweight all the points to correct for using the wrong distribution。

And that gives us an estimator of。The thing we're interested in。 So Phi is the true。下不方。

Is the true average value。Just have a think about this if you。

Say what is the expected value of p of x？Over Q of x。With some functioned fire。X。

 the expected value of this。 When you draw points from Q。え？This， so。

Im must answering the question now， What's the expected value。Of one of these terms here。

 expected value of P star of X R。Over Q of Xr。Times 5 of thatar。

That expected value is the integral of that thing under Q and the Q's cancel with each other。

 and so that is integral DX。P。that。5 x。Which is apart from the normalizing constant of the thing that we're after。

 So that's a justification for why this re waitinging is the right thing to do。Oh。So。

What we have on the screen here。Is the estimate that I defined find here capital Phi hat。

 And I'm showing it as the number of samples increases。

 the top graph is showing as R increased from 1 up to 50。 what happened to the estimate of Phi。

And I did that first for the uniform distribution， but you can use this formula for any distribution。

 so for example， we can make the green distribution， the simple distribution be agasian。

And here's a green gassian， and I can pick a w for that Gasian。

 and I can draw points from the Gasian， and they're shown in yellow。And there is the estimate of phi。

 the expected value of phi。As a function for the number of samples。

 and you can do this with any width of Gaussian you like。 so you could pick a very narrow Gaussian。

 and there's the estimate of Phi。And something you might realize is that if this is meant to be estimating what happens under the red distribution。

Given that most of the red distribution is here and none of the yellow points actually visited there at all。

 this particular estimate we've got after these 50 points is actually completely wrong。

And we've got no obvious way of realizing that， because we're just。

Pushing the blind man around and then he takes off his blindfold and he looks and he sees P there and he sees Petee there and we tell him this magic weight to reweight things by and we promise him that eventually if he does it for a very long time。

 we give him enough points R。Then he'll eventually get the right answer。Well。

 that's a very dangerous thing to do because obviously you could just keep visiting places and you might never visit the places where the red curve is actually to be big。

So when a moment ago， I said it would be fine if our were just a dozen or a thousand or something like that。

That was for solving problem  one， using sorry for solving problem 2， using problem 1。

 which is the ability to draw points from the right distribution here。

 You've got the wrong distribution， and so。The number of points required are for this to work could be absolutely enormous。

 It just depends how close the green distribution is to the red distribution。

And if it's very narrow or if it's in the wrong place， it will take forever to get a good estimate。

Here's a much broader distribution， and now you draw 50 points from this and you get an estimate of wanders around。

One of the themes of this lecture on simple Monte Carlo methods will be that the Monte Carlo method may have some sort of guarantee that asymptotically it will work well as R gets big。

But you have no way of knowing as you run the algorithm。

 whether it is actually giving you the right answer yet or not。

So here's a graph showing for those four distributions that we've just played with in green。

 fixed the red distribution， and we went through a sequence of green distributions， uniform。

 then one gaussian， then a skinny gausing， then a broad gausing。

 This shows the estimates that you get from those four methods。

As the number of points increased from 1 to 50 drawers from the green distribution。

 And you can see they all bumble around all over place。

 and they all have the property that they seem to be settling down a bit。

But they're actually settling down to different value。 In particular。

 the narrow gas in is settling down to a completely different value from the others。

So what would you say if you ran this experiment and said can I stop now。

 Well the answer is you just don't know for any of these。

 you don't know if the value is actually going to lurch off and completely change so let's run it for a bit longer。

 if we run it for 2000 iterations， this is what happens。😡。

So all of them wander around all over the place， and the three bottom ones are settling down on something。

But the purple one， which is the skinny Gaussian。 Every now and then。

 it does a great big lurch because it managed to hit a place where P is much， much bigger than Q。

 And that will happen very rarely because it is such a narrow tailed green thing。

 It doesn't have any mass in the place where it really ought to。

 So very rarely we get these points they completely change our estimate of fight。

Wpping enormous weights。So。This formula may have some sort of derivation behind it。

 but it doesn't come with a very clear health warning。

 The health warning should say these weights could sometimes be almost infinitely large。 therefore。

 when you use this formula for only R equals 50 points or only R equals 50，000 points。

 you may still be getting the wrong answer because you haven't included。😡。

Some points that are going to come along in due course with infinitely large weights that completely outweigh everything you've done so far。

So it lurches all over the place， it lurches up and it lurches back down because another point happened out and a tail on the other side。

 maybe。Yes， so the comment is if you see some huge weights。

 it's an indication that you've got a bad distribution， so does that help you。

 you could have a rule that says okay， use an important sampling and keep an eye on the weights and see if any big weights come along。

😡，But just rewind a moment when we'd only seen 50 points。We didn't see any lurches there。

 There weren't any big weights。 And so just the fact that there weren't any big weights doesn't mean that everything's pipe。

 so。There's a sort of for simple Monte Carlo methods。

 there's always a nervousness that no matter how many such statistics you try to gather to say。

 hmm yes， this is looking like it's okay it could be that you are just sampling from completely the wrong distribution and eventually a point will come along and you say finally that is in the typical set that's a place where P is big and it dominates everything else so。

😊，You can keep an eye on the variance of the weights or other other moments of the weights。

 and that may help you， but you can't get any guarantee that your important supper is working unless you go to more sophisticated versions of important su。

So that's important sampling。😡，Next， let's talk about rejection sampling。

So rejection sampling also uses a sampler density queue。

 which is simpler enough that we can draw samples from it。So we have the same。

And that's the distribution P。But the assumption is。

That we have a simple distribution Q for which we have a mathematical proof， a guarantee。😡，That。

 we really know。That。😡，Yes。C times Q。Is everywhere bigger than。Hetop。

So the assumption is that somehow you have been able to prove that C Q is greater than or equal to p star of x。

Everywhere。And assuming that that is true。😡，Rejection sampling。Then works like this。

 We draw points from Q。And each time we draw a point。We also draw a vertical coordinate。

So the algorithm is like this。One， draw X from Q。2。😡。

Draw a uniform variable from the uniform distribution。That goes from 0 to C times Q of x。

So that means having drawn an x from this green distribution。Say here。We then say。

 give me a uniform point between hair and hair。And that could come out。There， for example。

Or it could come out。And then，3。If U is less than P star， which the linefold man now evaluates。Then。

😡，是し。Acccept。X， and accept means that we spit this out， and we put it。In the bucket。Okay。

That contains all of our X。Ass。Otherwise。Reject it。Hence， the name rejection sampling。

And that means you just throw it away and you don't put it in the bucket and it doesn't count the R R being the number of random samples you have made。

Theorem。😡，The points that get put in the bucket are perfect drawers from P。Okay。

 let's show this pictorially。So what I've done。Here， as I've drawn。

50 samples from the green distribution， and for every one of them。

 I've given it a vertical coordinate。That's uniformly distributed between the horizontal axis and the green light。

That means that all of those pointss， which are shown either in blue or yellow。

 those pointss are uniformly distributed in the area under the green curve。

That's what this construction gives you， step 1 and step 2。

That gives you a point whose coordinates X， U are uniform under the green curve。

 Then if you use scissors and you cut out all the ones that are coloured blue because they're under the red curve。

Those points must be uniformly distributed in the area under the red curve， so you cut them out。

 throw away all the yellow ones， and the ones that you're keeping come exactly from the red distribution。

いるはい。So that's rejection sampling。😡，And it's absolutely crucial that it must be true that CQ is bigger than or equal to B star because。

If it's not true， as shown by this example。 and if you draw points and pretend that you're doing rejection sampling。

 you will reject the yellow points， keep the blue points。

 And now the distribution you are actually drawing points from is some strange distribution that isn't the red distribution at all。

 It's some sort of hybrid between the two。So it's crucial that CQ must be bigger than R equal to P star。

 and if P star is a complicated distribution that's a little bit hard to understand。

 it may be a very difficult fact to prove that you have got a queue for which this is true。

It's not just that you have to know that it's true for some C。

 you have to actually say that it is true for a particular C because you need that C for the algorithm step two because you need to multiply by C get your uniform number。

😡，Okay。Okay， so the comment is it's very easy to check。😡。

Whether CQ is bigger than or equal to P star for the places where you actually drew the points。

 And that's absolutely true。 So you could。Just check。Not only。Draw the point。

 you but also see if you had equal one， then would。Yes。Yeah。Sorry， if if you had equaled a C times Q。

Would it still be less than each sum， So you can very easily check it。

 but that doesn't prove that it's true everywhere。Okay so yes， you can check。

 but that's not satisfactory with one Carlo methods。

 you really want a theorem that says if you run this algorithm for long enough。

You will get the right answer。And so just checking isn't good enough。Okay。

 and here again is the estimate of the expected value of phi for the methods we saw earlier。

 which we're using。Important sampling。And then in green， we have the answer for rejection sampling。

 which is drawing from the correct distribution， and you can see it it's settling down as well in the same sort way as the other three did。

Yes。Okay， are there any questions about。Important sampling or。Rejection sampling。

How do we draw samples from Q the assumption is that Q is a distribution that we can draw from so in a real space it might be a Gaussian or it might be a mixture of Gaussians that you have invented in some way in the case of the spins the sort of thing you could use for might be a distribution where each spin each of the end spins in the magnet just flips a biased coin of some sort to decide whether it's up up or down and those coins are flipped independently of each other then that's a very easy distribution to draw from so that's the sort of Q you might use。

It's typically a distribution that doesn't have strong correlations in it。

 or if it does have correlations in it among variables， they're simple correlation。

 simple enough that you can't still solve the problem of drawing from Q。Okay。

So rejection sampling is wonderful and usually you can't do it and there'll be two reasons why you can't do it either you can't think of a Q such that CQ is guaranteed to be bigger than P star because you don't understand P star are well enough。

😡，Or if you can come up with such a view for which you have a proof of this property。

It may be so much higher than the P that you end up rejecting every single point。

 You just run it and you reject reject。And you never get an accepted point because you are only able to prove this theorem for a green thing that's so much higher than the red thing。

Okay。So that's the sad truth about rejection sampling that unless you're very lucky or very clever。

 you won't actually be able to make a satisfactory rejection sampler for a real problem。

In one dimensional problems， like the ones we had on the screen just now。

 you can realistically do rejection sampling and one approach to。The methods we're about to discuss。

 which are metropolis the metropolis method and give sampling is you can perhaps use rejection sampling as a component in those。

 So let's move on now and talk about the metropolis method。So the methods we've looked at so far。

Yeah。Amon column methods。Where the blindfold man。😡。

Was told to go to a random place and look there at P star and maybe some other information at that location。

 keep on moving him around in a way where every move is independent over the previous move。

 So the new location we sent it to was just raw from Q every time。 Now。

 that's true for important sampling and rejected sampling。Now。

 the metropolis method is going to be an example of a Markov chain Monte Carlo method。

 which means that instead of asking。The blind old man to go to a new location。

That's completely independent of where he's been before。

There is now going to be a dependence on where he is at the moment。 So wherever he is now。

 we're going to move him to a new location that depends on his current location。

Why should that help is not at all clear that it should help。

 Why do we want that to be a dependence on this previous location， But that's what we're going to do。

 So now we're going to have a Q of X。X prime， where this is。The next location。あ。And this is。

The current location。And the assumption is going to be that we can draw from Q。

 So Q is going to be something simple like a Gaussian distribution or flipping bent coins or something like that。

 And we're going to assume that we can evaluate Q。And。We have a nasty distribution。She's red。

So here's the nasty thing。And2。Could look like。This， for example， if。

This is the current location X prime。And if。This is the current location。I'll go x double prime。

Then maybe two might look like。That's the sort of concept we have。

 that maybe Q is just a distribution that's centered on the current location and put tus things a little bit。

It can be any distribution you like。😡，As long as you can draw from it and you can evaluate it。

 So you can think of this cu as being a completely general distribution that you can draw from。

 But this is the sort of thing that people use in practice。 It is a small nudge to the state。

Or perhaps a big nuch， you could use very broad gastionianss if you want。

Or any distribution that you can draw from。So it's okay。For Q to be。Simple or complicated。

And something to emphasize here。Is it's okay for Q。To not。Looked like me。

Important sampling and rejection sampling both work really well if Q looks just like P because then you're done sort of instantly。

😡，But if you can make a queue that looks like P and you can draw from it。

 then that means you can solve the original problem that we were trying to solve。something odd。

In the metropolis method， it's okay to have a cu that doesn't look at all like P。

It can be completely different in its in its characteristics。 So it would be okay。To have a cu。

But it looks like this when x prime is here， and it looks like this when x prime is here。

 it can look like that if you want， and that's not going to be a problem。

The typical property that Q is actually going to have is going to be that typically Q just makes a small change in the energy of the system。

 So if it's going to work。Then。Usually。就。Makes。Just a small change。To the energy。

Energy being logged free stuff。Small meaning of order one。Okay。

So the distribution we're going to draw a point from depends on the previous state。

So how does the algorithm work？It's going to work like this。So at time T。😡，We are at a location X T。

And we do the following。哇。Generate。A new point。X。From。就。Exty。Two， compute something。😡。

That tells us whether we want to go there or not。 The computer thing called a。

 which is the acceptance ratio。And a looked a lot like the things we had in important sampling a moment ago。

 is going to have a P star at this place。 And it's going to be divided by。A queue。At。This place。

So that looks just like the weight that we had in important sampling now。

But we also need to take account of what the weight is in the place that we've come from。

 so we'll take a P star of Xt。😡，And we'll take the corresponding Q。

 which says if we were in x and we drew from。This place X is2 distribution。

 How likely is it that we come back to X T， which is where we are at the moment。 So we work out also。

How big Q of x T is assuming that you start from X。And that's the acceptance ratio。Yeah。So。

 the question is。Do we need to know the normalizing constant of Q， And the answer is， well， no。

 not necessarily。 if both of these cues have have。The same normalizing constant as each other。

 then you don't need to know the normalizing constant。On the other hand， if。Q has the form。

Q star on Z。 And that Z depends on this argument here。 Then you do need to know the Z， so。In general。

 that's the nature of that。 It will， in general， have an X T dependent。If it does。

 you need to know Z， at least you need to know this is Z within some constant that really is a constant。

All right， so that's acceptance ratio。 Then this is the exciting bit。 What do we do？And。

If we ignored the acceptance ratio， then all we would be doing is some sort of random war driven by Q。

 So we wouldn't be looking at P at all。 You'd just be saying， okay， Q， tell me where to go now。

 tell me where to go now。 here。 tell me where to go now。

 So your blindfold man would be doing a random war never looking at P at all。

 Step 3 is where the blindfold man will look at P star and。

Those that leakage of information is going to modify this random walk driven by Q into a new random walk that actually has exactly the property we're after。

 And the rule is， if the acceptance ratio is bigger than one， then we accept。Ex。Otherwise。

We accept X。With。Probability。8。A being the acceptance ratio。 Now， what do we mean by accept。

Except beans。That， we set X。T plus1 equal to x。Sorry about about writing。If we reject。

 on the other hand。Which is what we do if we don't pass。Either of these tests here。If we reject。

 then what we do is we set X T plus 1 equal to。X T， so we repeat， we stay where we are。

 We don't move。 We reject the proposed move and we stay where we are。 And in this way。

 we create a list of points， X T。😡，So this algorithm will spit out as time evolved at some time going up the screen。

 it'll go step， step， step， step。Sip， step， step。Step， step， step， Stay in the same place。

 Stay in the same place， step。Stay in the same place。 step， step， Stay in the same place。

 Stay the same place。 Stay the same。That's the sort of thing that will happen will either stay in the same place or not。

 and this is generating a sequence of points。😡，T where T was0，1，2， three，4。

And what's the point of that you might ask？😡，Well， a point of that。Is。That asymptotically。

 the probability distribution of Xt。Is。He。soundedunded like a power cut。Are we still recording okay？

So let me show you。Imppo in sampling。And what I'm going to do。

Is draw points that asymptotically will be coming from the red distribution。Wow。最のです。

And I'm going to start on an arbitrary point。 So you pick any x 0 to start from。

 It doesn't matter where it is。 We're going to run this thing for a long time。

And what we do is we start at that point。 My Q is always going to be a Gaussian centered on the current point。

 So I draw a point from that Gaussian， and it's shown in orange。 So this is the X of the algorithm。

 We've just done step one。Then we evaluate P at the new location and we say。

 what's the ratio of P at the new location for P at the current location and by symmetry。

 the two Qs canceled for this particular proposal distribution。

 So these two cus are going to be the same as each other because they're both asking how big is a Gaussian centered on me at you and how big is a Gaussian central arm。

 this place at your place。And those are by symmetrymetry the same as each other。 So these cancel out。

 All we need to know is the ratio of these piece。 What is it， Well， it's bigger than one。

P at the new location is bigger than P at current location， So we accept automatically。

 we don't need to draw any more random numbers。 We accept that， and we have now moved there。

 and we have generated x1。Now， we draw from a gas and sent it on that point。

And we propose this small step to the right。And it's smaller。So will it be accepted or not。

 We don't know。 We have to draw another random number。 So we flip bentco with a bias A and we say。

 is it acceptable， And the answer is， yeah， the Benco came out heads。 and so we accept。

We make another draw from the distribution centered on x2。And it takes us a bit up。

 so we're going to accept this definitely no question。Foraw another point。Now。

 it's going down by big factor。 We evaluate P star at this new location。

 and the rate shows about1 to 2。 So there's only a 50% chance we accept this。

 So now we get ourselves a Benco and buy of 50%。 We toss it。 What happens。Itcame our heads。

 so except。You grow again。No change in B。 So will'll accept that。

So that was five steps of the algorithm。 And in fact， every single step got accepted。

 which means that essentially we were just doing a random walk under Q。 But if we run it for longer。

 then you can see some rejections happening， and I've shown them above each other where theyd pile up。

 So you can see we spent more time。 We did some rejecting。

 We did some heavy rejecting in places where P was big and we didn't do so much rejecting in places where P was small。

 We sort of make sense。So。The decision to to reject moves when we were in places where P was big causes us to get more samples so far in those places where P is made。

And there's a theorem that says， if you run this thing sufficiently long。

And then pick the one point that you've got at the very end。

 So you keep on going with T getting bigger and bigger and bigger。

 And then you take the very last point。The probability distribution of that pint comes from a distribution that is ever closer to the red distribution P。

 the longer you understand from。Okay， so that's a beautiful property。😡。

It leaves you with a lot of question marks。 still。 You don't know how。

 how long to run this thing for。And you have to invent you。😡，As well。 So what's a good you。

 I don't know how long do I have to run it for。 don't know。 but nevertheless。

 there's a theorem that says when you run it for long enough， you will get a point to co P。

And indeed， if you keep on running it for longer， then subsequent points also have that property that they are coming from P。

 They don't come independently from P。 You can see there are they're doing such sort of random work。

 So each point will look a bit like the one that came before it。

The probability distribution of any one of them， if you have run the chain long enough， is P。

 and that's fantastic。😡，Okay， I'm now going to tell you about gi sampling。And Gi sampling is a。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_13.png)

Markov chain Hunt King method， which only makes sense if we have two dimensions。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_15.png)

So what I'm going to talk about now is a problem that has two dimensions。

 namely the inference of the mean and the standard deviation of a Gaussian given n points from that Gaussian。

So how does Gib sampling work？I'll be done in five minutes。Get something。The assumption is。

 and this is a big assumption。Okay。We assume。That even though here itself is a red nasty distribution。

 we assume that we can sample。From。The conditional distributions。Yeah。Of one。Of these dimensions。

 conditional on all the others。 So P is a nasty red thing。With some complicated。S。

But the assumption is that a slice of this， keeping。All of x 2， x x 4， x 5 fixed。

 And just looking at that x1 dependence。 that we can actually draw from this conditional distribution so we can draw from here of X 1。

 given x 2。And here of X2， given x1 in the case of a problem where there are two variables。

When the algorithm works like this， start somewhere。问如。

X1's new value from the conditional distribution of x1， given x 2。T are you。

Then draw x 2 is p plus1 value from the conditional distribution of x 2。G x1s new value。

 so you take the new value。And you plug it in here， and then you repeat。

 which means the new value of x2 is going to get for 10。

That's how you do it with just two variables and if you've got K variables。

 you just cycle through drawing each of them from its distribution conditional on all the others。

So this is a big assumption that you can do this， but there are examples where this is quite easy。

 and the Gaussian distribution is a good example of this。 So if I give you some data。

 here's five data points。 and then I say what's the posterior probability of U and sigma。

 You know the answer to that。 You can enumerate the hypothesisthes。

 you can make a surface plot we've looked at this before， It's a dependent。嗯。Distribution where。

The conts aren't concentric。That's what it looks like。

 but any slice through this is fantastically simple。

 So even though this is a slightly complicated dependent distribution。

 a slice in this direction through any of these is a Gaussian。

And a slice in this direction is just a gamma distribution。 So these are gammas。And these are normal。

And as long as you have a piece of software that can draw from gamma distributions。

 you can do each of these steps， and you just alternately do one then the other， one and the other。

 So off we go。In red I'm showing you what the true distribution actually looks like。

 that's what the blindfold man can't see。 All the blindfold man can do is you can say， well。

 I'm starting from somewhere where's that。😡，So that's his start。

 and I'm showing you in data space what that hypothesis looks like as well。

 so it's a very broad Gaussian rhythm a mean in the wrong place。😡，And then you tell them， okay。

 update view by drawing it from the Gaussian distribution， which。

Leaving sigma fixed to this broad value。 and he can draw from that Gausian because that's a simple thing to do。

 He can work out given the five date points， what's the conditional distribution of the mean given sigma。

 So he does that。That's his first set。And then， the second step。Is。He's got to update Sigma。

And he draws it from a gamma distribution， and that changes the standard deviation from the broad value we just randomly initial highlighted to for a new value。

 then we update the mean and we update Sigma， then we update the mean， and we update Sigma。

And there is a dependence between these points。 Each one of them is created in a way that depends on the previous one。

And every other set I'm highlighting in yellow when we've gone through two of these and we're back up at a new time step。

 So keep on going， think。Liinnk。And。😡，AndNow I've got it running and you can see in yellow what was happening to the hypothesis as it wandered around。

 and here's a summary of what happened after I don't know， 20 iterations or so。

 so our initial point was off there top left and then we just wandered around and is the theorem for you this is a metropolis method and so asymptotically it raws from the correct distribution。

Now， you can do this。For a whole range of models。And the model that we discussed in the previous lecture was the clustering model。

 where we believe data comes from not one Gaussian， but a mixture of Gaussians。

So let's now change data。Here's a new data。😡，With 13 points。

 And you can see that it sort of looks like there's a bit of a cluster here。

 And then maybe there's a broader cluster。That account in accounts for all the other data flight that aren't there。

If we insist on saying there is only one Gaussian， then we can use。

Gib sampling method to draw from the posterior probability。

And we'll get a whole bunch of theories about and Sigma that look like that with this being one typical draw。

 This is the last type office you came up。But something else we can do is we can change to the model that says no。

 there's two Gaussians and is the data。And。Here we have a display that isn't looking。

Trying one more time。Okay， brilliant。 I don't know。

What the bug is that sometimes it' doesn' in this way。So what have I done？

I'm representing now a hypothesis about two Gaussians。 The hypothesis is that there's two of them。

 and they've got means and standard deviations， and they're shown in the upper graph in yellow and orange。

The sum of those two garsians， which is the mixture of Gasians， is the purple line。

 So that's what you get when you add those two to each other。The data are shown in blue。

 and then in orange and yellow， I'm showing which points are been allocated to which cluster and the initial allocation is completely random because we haven't got a clue。

😡，And now what we do is we're going to alternate between。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_17.png)

Steps that we will call。

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_19.png)

Assigning and updating。Just like in soft pay means。 Remember， soft pay means last lecture。

So we're going to cluster using Gib sampling， so all we're going to do is follow this rule here。😡。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_21.png)

And this rule here， we're going to update means and stand deviations in this way and we're going to update the assignments in this way。

And that corresponds to assigning and updating。Sned。I'll forget。So， at each iteration。

We look at who's being assigned to us and we update our mean and our standard deviation using the Gaussian distribution。

Appropriate to our mean， given the points that have been assigned to me。

 just like in the previous demo and we update the standard deviation using a gamma distribution。

And each of the clusters does that for itself。And the assignments at the point are made by working out the responsibilities which you would use in the soft K means algorithm using the current means and standard deviations。

 but instead of just working out those soft responsibilities。

 you actually draw from the bent coin with those responsibilities so for each of the 13 points we make a bentco and we flip it to decide who do I belong to now。

And so you can see at each step of this algorithm， the assignments are changing。

 Sometimes get lots of points assigned to Mr。 Orange。And then。come back and oh。

 it's come up with the idea that maybe Mr。 Ylow is where that little tenative cluster was and it's come up with the idea that maybe the orange eye accounts for the broader set。

We'mll keep on going。And it goes， buumumbly buumbly buumly buly。And it's now exploring。

 we hope the posterior distribution of the labelings and the means and the standard deviations。

And this really is asymptotically solving the problem。

 So this is a correct solution when you run it for long enough to the task of fitting。

Or inferring a mixed e Gasians from data。 And a beauty of this is you can do it very easily with a data set of any size at all。

 You can have as many points as you want， as many clusters as you want， and it scales just fine。

 It doesn't fall over。 It doesn't grow exponentially with the amount of data。

 or with the number of means。 So this is a very practical method of doing。K means clustering。

 and it doesn't suffer from some of the defects that K means that soft K means suffer from。

 So this gib sampling is essentially a randomized version of K means that actually does the right thing。

And something you can notice is in green， I'm showing what the average of all the purple lines is of the entire simulation so far。

 and so that green is the answer to the question， please predict for me where the next point。

 the 14th point would come from if I went and got another blue data point。And。

Green line is that prediction。 You can see we've got a very nice prediction that， yeah。

 given this data， it really looks like there is a bit of a hump here and a hump over there。

And if we ran it for a very long time。You would see a flip happening every now and then at the moment。

 Mr。 Yellow is the cluster that is usually responsible for these parts。

And there's an equally probable hypothesis which says no Mr。

 Orange is responsible for them and it's the other way round and logically it must be able to get to that hypothesis that a science in the other way round and itll better do so because otherwise it isn't asymptotically sampling from the true posterior and if we run it for about another 15 minutes。

 then you'll see it。😡，Probably reverse， come up with the other hypothesis。

 flip between those two explanations of the data， and it will explore other hypotheses。

 as you can see occasionally， it comes up with the idea that it's too equal with Casians。Okay。

 I'll leave that running and we've reached the end of the first lecture on Monte Carlo methodsthod。

 are there any questions now？

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_23.png)

Okay， so the question is what about if you wanted to know how many clusters there are。

 if you want to know how many clusters there are， let me kill this。😡，嗯。

You would have to represent the posterior distribution of。The weather means are。

 what the standard deviations are， what the assignments are， and how many clusters there are。

That is a much harder thing to work with， because essentially it has to include that normalizing constant that we mentioned earlier。

These mochain Monte Carlo methods， the metropolis method and give sampling。

 They don't tell you the normalizing constant。 And that gives you a tip that if you wanted to answer that question。

 how many clusters are there。These methods aren't going to be able to help because they don't reveal the normalizing constant。

There are Monticcallo methods。That do estimate normalizing constants。

 and that can correctly make transitions between models with different numbers of clusters。

 for example。So these things exist。They are much more sophisticated than what we've done so far， so。

Come along next time。 And maybe we can discuss that in the。Next lecture。

 Let me just tell you where we're going。 So I've shown you a demo of gib sampling as way of doing clustering。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_25.png)

We've got halfway through this particular set of Monte Carlo methods。

And the methods I've shown you so far have got three important problems in addition to this question of actually wanting to do model comparison。

 we can't do model comparison so that's challenge number four。

 the first three challenges are they all get around these Markov chainin Montecarlo methods get around by a random walk and that is slow。

So what we would like is methods that have less random walk behavior because random walks are a very tedious way to make progress。

The methods tend to be sensitive to the step size。 So when we were using the metropolis method。

 we had to choose a Q distribution， and Q will work well if it only makes small changes。

 but that means it makes small steps， which means it makes。

Very slow progress you'd like to take bigger steps， but if you take steps that are too big。

 you'll always reject every proposal， so there's a sensitivity to that parameter。

A third problem with everything we've seen so far is we don't know when to stop。

 We don't know when we've run it or long enough that we can say， oh， yes， we have reached asymptopia。

 And all three of those problems will be solved in the next lecture。

 We're going to discuss efficient methods that don't have random war behavior。

 We're going to discuss a method called slice sampling that gets rid of the sensitivity of the metropolis method for the step size。

And we're going to discuss a method called exact sampling。

 which is an amazing breakthrough in Monte Carlo methods。

 It's a way of taking some Monte Carlo methods and actually being able to provably say this point is a correct draw from the distribution P。

 and we can stop that。😊，We saw process and going at level。

So exact sampling is a really huge breakthrough in nonpo。

 so that's what we will discuss in the next lecture。



![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_27.png)

没以。Next。

![](img/317eb0f6cf250f9e5fd06fd0ae98a71c_29.png)