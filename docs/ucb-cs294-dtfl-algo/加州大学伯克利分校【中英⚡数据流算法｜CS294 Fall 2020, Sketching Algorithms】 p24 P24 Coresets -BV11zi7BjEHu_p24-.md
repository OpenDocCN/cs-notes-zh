# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p24 P24 Coresets -BV11zi7BjEHu_p24-

![](img/ad55bd2a2fa9aba8527d76dc73d18def_0.png)

All right， so welcome to the last lecture of the semester we do have three more lectures scheduled but those are going to be devoted to final projects so Wednesday。

 next week Monday and next week Wednesday will all be final projects。

I did post the schedule for that already on Piazza。Theres there are a couple of people。

 a small number， maybe two or three people on that schedule who。Still have not submitted。

Their final project proposal。 and I've I've emailed them several times and have've never gotten a response。

 So I'm not sure if those people are actually just not in the class and maybe forgot to。

Forgot to drop it i'm not really I don't know， but I guess we're going to find out Wednesday or。

I'm going to send them a final p right after this lecture and if they don't respond before Wednesday。

 then we'll just remove them from the schedule and assume that they're not actually in the class anymore。

I'm also going to have， I didn't have office hours this past Friday because it was the Thanksgiving holiday weekend。

I will have it this Friday， but some of you are presenting on Wednesday。

 so office hours on Friday are not that helpful。嗯。So for anyone who maybe I'll make a Piazza pose。

 but basically if there's anyone for whom it would help to have a meeting before they present on Wednesday。

 I'm happy to open up some office hours tomorrow on Tuesday。So， just let me know。

So we've talked a lot a lot about various things in this semester so far right we've started off with basic streaming problems counting problems in the streaming model we talked about lower bounds we talked about linear sketching。

 deanaimization dimensionality reduction， randomized linear algebra and compressed sensing。

 and then we talked a little bit about。嗯。ind of instance wise bounds using kind of the theory of stochastic processes and the sparse Fourier transform。

So today I just want to end with kind of one more topic again this is just one lecture so we're not going to get too deeply into it。

 but it is something that I think is a useful thing that you should I should definitely at least tell you about you should know about so today we're going to talk about core sets。

And I'll just say see more。In the survey it's a brief survey。

 but it's a gateway survey so it has links to lots of other things that you can read it's not very comprehensive。

See more in the survey by。Batam， Lucsch and Krause。So what is a corset？

So there are both what are called wheat poor sets。And strong corsets。Okay。

 but what unifies that is basically。A weighted。The weighted subset。Of the inputada。Such that。

Optimizing。Over the subset。Gives。A near optimal solution。For the original data。So specifically。

 this is what's called the week corset。A strong， strong means。Strong means。The cost。Of。Any solution。

To the subset。Is approximately the same。As the as。嗯。As to the original。

Maybe I'll try to make this concrete， but basically what this is saying is let's say that you're trying to solve。

K means， right？ So K means you have a bunch of points。And I'll make this more formal soon， but。

Okay so let's say you would like to cluster these， I mean this has a very obvious clustering。

 but let's say that you'd like to cluster this into four clusters。

 you know the optimal clusters are something like， you know maybe choose this point this center。

 this center of this center。系嘅。These red points are the opt。The op centers。

The black points are the original points。Okay， what is a corset， the corset is。For example。

So let's say this orange is the corset。So what does it mean that it's a coreet？

If it's a weak cor set， what it means is。Suppose that you forget about the black points altogether。

 okay， the only information you retain is the yellow points。😡，Okay。

 and now I ask you to optimally or almost optimally cluster the yellow points。😡。

You're probably going to come up with a clustering with four cluster centers。

That are pretty close to those red centers， which are the optimal centers。Right。

 so that's what it means to be a weak coret it means that。

If you optimize you know a subset is a core set I'm going to write it more formally about a subset basically is a core set and it could be a weighted subset so for example。

 this point right here we could give it you know the original black points all over one point each so they all had weight one。

But we could make the yellow points weighted so like for example。

 this point maybe has weight three or something。Okay， but the point is if you then。

And when I say waited， I just mean like。You imagine that there are three copies of that yellow point。

But we don't have to remember all three copies， we'll in memory to minimize our memory。

 we'll just remember the number three that there are three copies of that point。

But in terms of evaluating the cost function for K means。

 we're going to act as if there had been three points there。

 so the distance squared from that yellow point to the center will get multiplied by three because we imagine that there' are actually three points there。

Okay， so。So what it means to be a weak corset is if we forget about the black points and we just give someone of the yellow points and we say optimally cluster these yellow points or optimally fine centers or near optimally fine centers for these yellow points。

Whatever cluster centers you find。😡，Will be nearly optimal for the original blackpoint。😡。

Okay so we basically reduced to the optimization problem over a smaller set。Okay。

 that's what it means to be a weak coret。To be a strong corset means。

Not only is it true that optimizing the yellow pointss gives a your optimal solution for the black pointss。

But even crappy solutions to the yellow points have their costs approximately preserved。

 So you can imagine， like， take those yellow points and look at the following， you know。

 four cluster centers。 I'll put like two over here。One here and one here。Okay。

 so those four points are that is a valid， you know， choice of four centers。

 it has some cost for the yellow points， not a great cost， not nearly optimal， but it has some cost。

To be a strong corset means， whatever its cost is for those whatever the cost of those Tl points is for the yellow points。

Its cost for the black points would be almost the same up to a constant factor or up to one plus subpsilon or whatever the quality of your corset is。

😡，是的。😊，Having that level of preservation is what it means to be a strong corset。O。

So does that make sense the difference between just this is definitional。

 what's the difference between in a strong core set and a weak core set？对。Okay， so。

I just want to in this lecture give you a couple examples of how to you construct corsets and then I want to say that having corsets gives a pretty generic way of designing streaming algorithms。

 low memory streaming algorithms for optimization problems okay and actually maybe what I'll do is I'll。

All first。I'll first say that so the claim。Again， I'm not i'm going to write it informally and then it's going to be clear from the calculations what we're getting what we're getting mathematically。

 but the claim is that。你是。You know。There's a systematic way， this is an informal plane。

 there's a systematic way。Of turning。A corset。Construction right the name of the game in Coret says obviously you want to make that subset that yellow set as small as possible because presumably it's harder to optimize over a large set than a small set so if I can turn my large data into small data by taking a subset a weighted subset I can optimize over that probably more efficiently。

So if there's a systematic way of turning a court， so the claim is that there's a systematic way of turning a core set。

Construction。Into a low memory。Streing algorithm。For that optimization problem。And the proof again。

 there's no real proof here because I'm not saying anything mathematical。

 you can write downside you can formalize this， but I think it's going to be obvious from what I'm writing that what I mean here。

The basic idea is that。嗯。The corset。Of。Let's say the well， yeah， I'll say it as the core set of。

A course set is a coreet。Okay， so let's， for example。Take， you know， K means。

So we see a stream of points in Kas， this is some point in some metric space。

 this is some other points in the same metric space， etc。Let me just draw a few more circles。

Conceptally， this is what I want to do。Okay， I'm going to imagine that there's actually a perfect binary tree built on these endpoints。

So I'm seeing endpoints in a stream。You're coming at me in a stream。

And I don't want to have to store all of them。O。🤧So。What I'm going to do is。I'm going to， you know。

 so let's say my memory。It's going to look like this so。First， I'm going to see the first point。

And then I'm going to store it。Then I'm going to see the second point。And then I'm going to store it。

Yeah。And then what I can do is。I can then， you know。Merge these into a core set。I mean。

 let's say that our cost， what is our cost， right？I's basically the sum。Overall。X in the plane set。

Oh， okay， so yeah， let me like this。The distance from x to the centers。Where C is a set。Of K centers。

 and actually it's the square distance。是。And for this， what you actually want is。You want a corset。

 you know。You want a corset that。Basically。Has the property that if you add。

If you add more points to the corset， then it still remains a corset。😡，Right so。

I guess what I'm saying is you want the property that if you look at the cost。

Like for all possibly weighted subsets， S of the point set。If you look at the cost function。

On S and for all， let's say T， which are possible extensions。To to x points that you might add later。

 the cost of S union T。Apply to。Some solution。C is the solution。

 It's the set of centers you're using。 Let's say， is that most the cost。Of。Xun T。是。

And which is at most， let's say some alpha， which or beta。

 which is the approximation factor times the cost。Of SU and T。So you want a construction， you want。

 of course， a construction that has this property that。

You know if you have your cor set and you extend it by an arbitrary set。

 which is like the set that're extending your points by。

 then you still have this cost maintenance property。So this would be like this。

 as I wrote it here would be also kind of a strong corset property because this is true for NeT。嗯。

Or true for any C。Okay， so what you would do is you would basically。

 you know you would store this as like that point as a core set of itself。

 of course the set itself is always a core set of itself with approximation ratio one。

Then you see the next point， you would see this and store that as well。

 and then you would stop storing these。And then you would run your corset construction procedure on these two points。

 and then you would get a corset that you store， which is the corset of those two points。

Then you see the next point you store it， you see the next point you store it， and then you're like。

 I'm actually going to now merge these。And then I'll merge them into a core set of that data。

 and then now I'll take these two data， I'll take these two weighted subsets of different sets of points and merge them。

And then I'll take a core set of the union of these two。

So a course of the union of these two will give me a courseet up here。

And then now I don't need to store these anymore。And you just kind of proceed in this fashion。And。嗯。

😊，The point is you'll always have at most log in active nodes in the tree where you're actually storing any cors set at all。

So that means that this construction implies that if the original cor set。Construction。Give size S。

Then the streaming algorithm。Uses space。Of S log n。And the approximation factor。

The quality of the cor set。Becomes something like。Beta to the log end power。

Because if you lose a factor of beta every time you create a corset。

Like every time you take the data set and create a cors out of it。

 cors out of you lose a vector of data， if you do this log in times up the tree。

 you're losing data to the login power。But imagine what you'd want then is we'd want something like。

Bit density， something like one plus epsilon over log n。

That would imply that beta to the log n is equal to one plus o of epsilon。So if you have a way of。

 for example， for k means or k mediaian constructing a small corset。

 and it turns out that this is possible， a core set of size。Something like polyly K， polyly log N。

 polyly1 of Rexon。If you have a way of doing that， then you automatically。

 and this it has this property also that I mentioned here。Yops。And it has this property。

 then you automatically have a low space streaming algorithm。对。So it's useful in streaming。

 but honestly people even outside of streaming care about corsets because it's just a nice way of summarizing data into a lower memory form。

So let me give two examples for today。W is there going to be K median？So camedian is。

Men over the choice of。C should be like， let's say， so we're given data set X。In some metric space。

With distance。Function， let's call a D。We want to find。The art men。Over all C。

 which are center is a subset of x， the size of C is k。Of the sum。

The sum over all points p in X of the distance from P to C， where the distance from P to a set。

 oh sorry。It is already upset。Is just defined to be the men overall centers in that set of centers。

Of the distance from P to little C。So it's very similar to K means。

 K means is the square version it's where you take d squared instead of D and usually I mean。

 not always， but oftentimes people study the case where D is Euclidean distance。

 but you can study these problems in arbitrary metrics。

So this looks like it's just K means for the L1 norm。

 or is this actually a median D D could be the Euclidean distance。

So right like D isn't so I'm just afraid so Kate， if I said k means。K means。

I think when we talked about Kaines earlier in the class， D was Euclidean distance。

 but more generally sometimes when people say came meanss what they actually mean is this？ok。

So median just means you take the sum of distances to the centers。

 means means you take the sum of distance squared。UBut you know。

 as we talked about Kines earlier in the class， we focused on Euclidean distance。

 which I think is probably the most common one that people talk about。Well。

 I'm getting tripped up by the word median， is there actually like a median getting computed here？

Yeah， so this is just I guess the standard terminology in the literature， why is it called median。

 I think I think if you take this if you take the points to be one to like numbers，😡。

And you take the distance to just be the absolute value of the difference。Then。

And you look at the case where K is1。Then the optimal center is the median。😡，ok。Does that make sense？

Yeah， that makes sense。So kind of K median is a generalization where you don't just want one center。

 but you want K， and then people in the literature tend to further generalize it where it's an arbitrary metric space and not just absolute value of difference on a line。

Okay， yeah， again， yeah， this is just the jar of the of the field is what people call it。O。嗯。Yeah。

 so again， so let me。We're now dealing with the means version。

But think people construct corsets for key means as well， and they get very similar results。

The other one what we'll look at is minimum and closing ball。Which is also M B。Which is。Compute。

The a okay， so again you're given， let me write it again， you're given。You're given set。X and here。

 X has size N。You even set X as above， it's size N it's in。Actually。

 we're going to look at we're going to look at the put in space。Okay。

 so you're in a subset of Euclidean space of size n and D dimensionsal Euclidean space。And you want。

To find。The smallest radius ball that encloses all the points。So find the men。Overall。The argument。

 I guess。Over origins centers O in RD。Of。The max over points in x。Of P minus O。可以。So， you have。

you have these points， you could choose this center。

Which would probably be a terrible choice because if you want that to be the center of your ball。

 probably the ball has to have radius that looks like this。That's not a very perfect ball。

 it's very lopsided， but you get the idea。A better choice would have been something that's kind of snack in the middle。

And then probably the smallest ball is this ball。That doesn't quite contain everything。

 but let's pretend that it does let's just delete the point that's not in the ball。

 okay delete the two points that are not in the ball。Okay。

 so that this yellow one would be the optimal one。你这。Does that make sense， the problem statements？嗯。

So I want to talk about kind of optimal。Im not optimal。

 there's some constructions that are known for these problems。嗯。It turns out that。Sorry。

 just give me a second。Just want to make sure I say the correct year。

 I think it's Feldman and Lanerman。And la。So诶。For like something I came eating， for example。

Feldman and Langberg。In 2011。Show that。Coursesets。Of size。

 something like O of Kd of Rpsilon squared exist。And can be efficiently constructed。Right。

It's pretty nice， I mean it's and the quality。Is beta， which is wonderful stepsilon。Right。

 so this is specifically the case of。I think this in the case of。D dimensional。Euclidean space。

So capital D is D dimensionally Euclideion。But people have also worked on kind of more general。

More general constructions that work in other metrics as well， like for example。

 the one I'm going to show you today is not going to do nearly as well as this。

 but it's going to get something that's non trivialally better than trivial it's going to be non trivially subline。

And works for arbitrary metrics。So let's see came media。So today。我嘅。A weak corset。Of size。嗯。

O of square root of N。So it's always， it's never worse than N。Right，But if k is small。

 if k is a constant， you get a core set of size red n and it can be iterated。To get。An arbitrarily。

small。诶。Exponent。好人。对。At the cost of increasing the or worsening the quality of the approximation。

 this is not going to be a corset that gets one zpson。

 there' is going to be a corset that gets some constant quality of approximation， big O of one。So。

 the assumption。No， and I should give the reference for this。This was due to Guha Mira。

Mtwani and Ocalian。I want to say it was like。Maybe 2001， it's one of the earliest constructions。R。

 it's04， but yeah， since the end of the early 200s anyway。

 I'll put it in I'll put the exact reference in the lecture notes。And the assumption。

The assumption is that there exists。诶。An offline。Of one optimal。Approxiation algorithm。For K median。

That runs。In linear space。It just needs to， in other words， it just needs to remember。呃。O and D。

 O of。Of let's say endpoint。With maybe all of an extra data。

And it turns out that this has existed for at least 20 years， people have。

 I think the best known approximation ratio in the hour that people can achieve。Is。

Arbitrarily close to like。Today。Cannt achieve。Arbitrarily close。To kind of one。

Plus2 over E approximation。这是什么？But the constant doesn't really matter for us。

 call let's give us a name this is。This is B。So there exists some B approximation I mean Kmeian by the way and K means are NP hard problems。

 so that's why we're talking about approximation algorithms here so our assumption here is just that there's an approximation algorithm。

That runs in。That's fast and runs in linear space to the number of points。And this is due to。

Go ahead and a。And others。And it's somewhat recent， but even as far back as 2000。

 I think there was an algorithm that was。Arbitrarily close to a three approximation。

 so people have been getting better bees， but it's just from one constant to a better constant。

I'm not going to talk about how these。Approxiation algorithms work they're not really about streaming。

 they're just about designing approximation algorithms。

 so let's just take it as a black box that it exists。Okay so the algorithm。

So we have this set of n elements。We're going to break it up into B blocks。Or blocks of size B。

Break into。Inver B blocks。How size be。So each one has size B。

And then what we're going to do is we're going to run。A B approximation。You each block。Okay。

 and that's going to that's going to give will give us。U， I guess。K points per block。Ops。so诶。

Bk points total。No。Not be hit total。N over be times K points total。Right。

When we run the B approximation of a block， it's going to spit out like when I say run the approximation of each block。

 what I really mean is pretend the blocks have nothing to do with each other。

Each block is its own camedian problem and I just want to say like find the best clustering for the points in this block。

 ignoring everything else。😡，So you're going to spit out K points。Which are your best centers。

 And here you're gonna spit out K points。Et cetera。And since the number of blocks is n over B。

 the total number of points here is n over B times k。可。And this will be our corset。😡。

What's the space requirement， So the space。Is in each block of size B。诶。😊，Wait a second， so。Yeah。

 so in each block of size B， we're using a linear space algorithm， so we're using B space per block。

And we also have to remember all the cluster centers that we're finding along the way。

Until the very end， so we also have to remember N over B times k points。

So we minimize this expression by setting the two terms equal。Minimize。

When B is equal to n over B times k。Which implies that。B square root equals equal to N。

 which implies that b is equal to the square root of N。So this implies that。The total space。

Then becomes O of spirit rootative NK。And also the corset size。Becomes oh square rootd I。

So we're able to construct。A small corset in low memory。Right。I mean， maybe I should。 yeah， so。嗯。😊。

Maybe I should have said this in the beginning for the purposes of weak constructing weak corsets。

The name of the game is always to compute the weak cors set using low computational resources。

 right like low memory， low time， whatever， because if you didn't care at all。About， like's say。

 for K median。If I said， look， I want you to give me a really good core set that's really small。

 really good approximation ratio。嗯m。😊，Like what could you do if you didn't care about computational resources。

 what would be like an amazing week course set？😡，Well， just the optimals solution itself， right？

So right， if you take the optimal solution。And then you you that's K points。

 and then you the best you try to find the best K clustering of those K points。

That's going to be the points themselves， which is an amazing solution to the original point set。

If you're allowed arbitrary computational resources。

 then yeah just use the use the opt itself as the corset and that is a weak corset。

 but that's kind of。Uninteresting because this is an NP hard problem。

 it's not easy to come up with the optimal points， right？

So the name of the game really is like how good can you make how small can you make your course set or how good can you do that。

 how well can you do this when you have some constraints， like for example， here a space constraint。

So here in subline memory， we're able to actually compress into a subline size corst。行。

And now what I want to show you is if you take this core set of root N K points。

And you optimally or near optimally cluster it。😡，Using K centers。

So now this is your new set of points。I want you to k cluster that set of points。

 I claim that the clustering you find will be approximately optimal for the original data set。

 it'll also be o of one optimal where the O of one will be something like b squared。

 it'll be roughly four times b squared okay。😡，Right， so。We'll show。That。This course set。

Has approximation quality。At most，4 B times b plus1。So roughly four times b squared。So。

 the first claim。Yeah， so first before Cla， let me just write some notation down。

I'm going to say that cost。Of AA or let's say cost of A B。Is the best。Canadian cost。Possible。

To cluster。A。When the cluster centers。Have to B and B。嗯。So the first claim。Is that for all？And me。

The cost。Of clustering A with centers in A is at most。

Two times the cost of clustering a with the centers and B。啊。Why is that？So let's say we have a。

So this is hei。And this is， this is B。嗯。So we have our point set。Let's say I'm doing k equals three。

诶。Maybe what I do is I say， look。This is I'm going to choose this as one center that's these are the optimal centers。

 these are my this these three are my optimal centers。

 so I'm clustering a using centers that also themselves are an A。Now， you know。

 what's B B is some other setup points， like maybe B is all of space， for example。

Let's say these all space， what would the optimal centers be？Probably something like this。

 roughly this for K means anyway to be this， right which be the centroids。And the point is that。

If you look at the distance。From any one of these points。If you looking at the distance， listen。

 So what is K media， K media is like。The sum over all points in a of the distance from the point set to。

 its closest。Center。So for example， that would be like sum of these distances。You know， like。

 for example， this distance， this distance， this distance， et cetera。

And then it listens to itself there。Letst we get any one of these terms like let's just give these names。

 let's say that this is。Little C for center， and this is a point little P。

Then on the one hand on the left hand side， we have the distance and let's say this orange point is Q。

诶。The distance from P。To see。Is that most？The distance from。P to Q plus the distance from。诶。C得 here。

This is just triangle inequality。哎。诶。You see。 And then what I wan to say is。Okay， sorry。

 I think I confused myself， but。I think what you want to do is basically now some overall points P。嗯。

Yeah， this is definitely。Sorry， I think I， let me， I might have to fix this in the notes。

 I think I confuse myself in my own notes， but。This definitely park here would be the cost。

Just me the cost of a B。And this would be the cost of AA。

And then I guess I would still have to argue about the sum of this part。Which， for some reason。

 is euding me right now， but。嗯。Let me fix that later。 Let me not。

Let me not try to unconfuse myself live， because I'll probably just eat up some time。

But I'm pretty sure that I can come back and fix this inequality。

AndNow let me go back and name these subset。 so remember the whole thing originally was x。

 let me call this subset x1 x2， and this is x and over B。嗯。

And now what I want to do is I want to look at。F2。Which is just that the sum overall eye of the cost。

OfXI using centers in XI is at most。Twice this is the cost of clustering X using centers and X。

So the proof of this is just via the previous claim， so what I can say is。

The sum over I of the cost of clustering Xi using X。Is that most？Twice times the cost， of course。

 of the sum of the costs。Clustering X with C where C is like the actual optimal centers。

And this is just two times the cost of fostering X the Abin centers。Okay跟。是。W wait。

 did you mean to write something different on the top line then。Oh， yeah， probably It this。Yeah。う。😊。

Okay， so now let me look at， let me also look at， you know， let's call this set of points。

Let's call this X prime。Which is the coreet。So the size of x prime。Is O of K。嗯。Right， are you。

So I guess what I want the first thing I want to say that is。If we be approximate。In each。诶。Xi。

Then we paid。Total cost。At most， the sum。B times the sumr I of the cost of X I X。

Which is at most basically。2 b times opt。Or this is for the original data set。Byike flame， too。

And then now I want to talk about what happens when we then try to optimally cluster X prime。

And then we're going add those two cost together。Yeah。切。And by the way。

 I mean X prime might be a multiet， it might be the case that some of these K points across sets are the same。

 but that's okay， then treat it we'll just treat it as a multiet or a way set。嗯对。So。

We're just going to use well use triangle in quality。So again， we have this。我什么叫。Sum Q。

 which is in X prime。And consider。The Ps that are assigned。 so maybe I should say it like this。

Q is an X prime。 So I can say that， you know， it came from。It came from some XI。

And I say is consider the peas。In X i。That our closest。It's a queue。Right。嗯。Because。

The things that are in X prime are like nearly optimal centers。

 cluster centers for the points in their partitions。So for any point in some x p。

 it is the center that some of the P's in that X are closest to。And then also。Consider the centers。C。

呃。Clsest to these pes。ok。So what do we know？We know that the sum of costs。You know， from。呃。

The cues to the Ps。You know， across all the cues and Ps。Is at most2 b times opt。

And also the some of the costs。From pe to Cs。So their respective centers is just equal to opt by definition。

So therefore。What do we have。We have that。The cost of， let's say， X prime。

Aing X prime with the optimal centers。Is that most？To B plus。2 b times the opt。Plus。

 ops by triangle inequality。Some of these two things。Which implies that。The cost of。

X prime using centers in X prime is at most two times。诶。Two times opt。 Well。

 two times basically this。 So let me factor out opt two times opt。Times2 v plus one。Okay。

And then there was also what we lost。By moving， there's also what we lost by moving from the original points to。

to the to x prime we lost this to be opt。So then B approximation。Toax prime。Has total cost。At most。

To be opt plus。Actually。呀。Plus。Did I write this correctly。Two times。To be opt plus opt。

Two times to be odd。その？So the total cost is at most to be opt plus，Or maybe write like this。

 can to be opt。Plus， this thing。We is equal to opt times。2 B plus2，2 B plus1。

And this thing in here is what。wo b plus4 b is6 b plus one。

I seem to be bad at math because I was supposed to get four。诶。Oh， oh， I know。So the point is。Yeah。

 good， good， good， good。 So the point is。If you optimally， if you optimally。K cluster x prime。

 you'll get a cost of this。But we're not optimally clustering K x prime。

 we're getting a B approximation right all we have in our hands is an efficient B approximation。

So actually。What I should have written is that our total cost is going to be to be opt。

Plus b times the thing above。Plus， B times the thing above。And that's equal to optt。times two b plus。

2 B2 b plus one。And then I can factor out the 2 b， and this is equal to 2 b times optt。

Times 1 plus 2 b plus1。And that's just 2 b plus two so I can factor out at two。

 and this equal to 4 B B plus1 times optt。那个。そ thatすか thats。O。So that's， of course。

 not even close to optimal the size of this cor set。Is it still has this dependence on root N。

 which is quite large compared to the best known ones we have， which are only like polyk。

I mentioned the Felman Langberg one， which is Kd over uppson squared for D dimensional Euclidean space。

 but even for arbitrary metric spaces， people can come up with。

Peopleel can come up with corsetss that have size like polyK like it doesn't。

 it shouldn't depend polynomially on N。And then the next thing I want to show you is minimum and closing ball。

And here we're going to construct a course set using。Using something that you've already seen before。

 which is basically nets。Willll construct。A corset。Of size。Oh of。

1 over epsilon to the D minus1 over 2， using a net argument。

So the nice thing here is it's totally independent of N， right？Of course。

 it has this very bad dependence on the dimension， but for low dimensional points it's not bad right and it has it's completely independent。

So what's the idea？We're going to take。An alphat。Of our point set。P1 up to PN。Call this alphat。

 let's call it V。Which is。Little V1 up to little VT。I this some subset of our D。

These are these are all in RD。 and we're looking at remember， this is the Euclidean ball。

 This is minimum repossing ball under。Underucide under Eucidean。

 so the ball is measured as a Euclidean ball。And what do I mean by an alpha net， I want an alpha net。

In terms of angle。Oh， and actually I should say I'm going to take an alphat of。The entire sphere。

And the input。Is the point set P went up to PM。So what do I mean by alphat of the entire sphere。

 it's going to be an alphat。In terms of angle， as I mentioned。meing。For all X。On the sphere。

 on the these dimensional sphere， there exists a V in the net。Such that if you look at the angle。

Between x。And V。The angle between them is at most alpha。So for example。

Imagine're working over two dimensional space。So since we're only talking about angles。

 we can just think， you know， we can even think everything here is on the sphere。

 the V's are on the sphere， the x's are on the sphere because all that matters are angles。So。

There's my circle in 2D。So I said two dimensional is the example。Kind of what's the best。

 what's the best alphat， The best alphat is you just go around the circle， kind of every alpha。

3 alpha degrees。Right where so， this is the origin。This is alphapha。This angle here is also alpha。

 et ce。Then no matter what other point you take on the sphere。

You know they're it's in between two points it's in between two black points that have angle alpha between them。

 so its angle with with with either of them is also at most alpha so in terms of angle this is an alpha net does that make sense。

And this has size。是吧。Sirference of a sphere， the circumference of a two dimensional circle。

Is O of one。Right， it's， I guess， two pi。So the size of this net is is like something like roughly two pi over alpha。

It's0 of1 over alpha。So this is the size of whatever alpha。And in general。算街。Size。

O of1 over alpha to the d minus1 where d is the dimension。Okay， and you know。

 how would you argue that its it's very similar to how we argued about net sizes in the past。

Basically it's this relationship between covering and packing so what you do is。You basically。

 you know， you look at this， let's just try and draw。Just I'm going to draw a 3D sphere， okay。

 I'm very bad at drawing， by the way。But， let's try。You basically greedily pack vectors。

So I just take an arbitrary vector。On the sphere。And maybe that I'm really gay， so again。

 this is not I don't know how to draw 3D that well， but let's pretend that it's coming at us。

So this right here is like the surface of the sphere。嗯。And then you ask yourself kind of like。

What's the， there's some kind of。Patch on the surface of this sphere。 Let's say this is the patch。

Such that any of the vectors there are within an angle， of course。

 of course the patch should look more。The patch actually is itself circular。

 I don't know why I drew this funny shape。There's some patch on the sphere around that point。

 which is basically all the other vectors that have angle at most alpha with this point。Right。

 so I can greedily try to pack。As many of these。Paches on the sphere as I can。

 such that they don't overlap。Okay， so I'll pack。Circleles。On the surface of the sphere。With radius。

Something like alpha over two。Maximally。Then double them。Double the circle sizes。To get a cover。

So that gives me a cover， which is an alpha cover and then the question the reason it's a cover is because of triangle inequality。

 this is very similar to us our greedy construction of nets in the past。

 the question then is just how big is this net？And it's just a calculation。

 basically you calculate the surface area of the Ddimensional sphere。And then you're saying， well。

 I'm packing all these little patches on the surface that are disjoint。

So there's a volume ratio that kind of constrains how many possible disuance circles I can have。

Therefore my bound on my net size is that is that volume ratio Okay so that's exactly the same volumetric argument we've seen in the past for bounding that sizes and if you do that。

You're going to get something like this， you're going to get a net size。

 which is O of whatever alpha to the D minus1 just by volume ratio。出。And then now I okay so good。

 so now we have we have this net and we know how to construct the net via this greedy packing argument。

Now how do we get a course set？ok嗯。So to get a core set。We we're going to do is。For each。

For each one of these points。For each of the V i。on store。The Arg Max。Over all， I of over J。

From one to n。Of the dot product of P J with。With V I。So we got a course set。Of size。T。

 which is of1 over alpha to the D minus1。So does that make sense， I mean。

 the perfect core set would be。The perfect coret which wouldn't lose any information would be don't just take a net of the sphere。

 but take the entire sphere， this isn't you know it's an infinite number of points。

And what we'll remember is。For every point on the sphere。

 I'll remember who has the largest dot product with that point， and I'll just remember that that guy。

Because if you think about it， you know， like if you think about the optimal solution to minimum and closing ball。

 so have a bunch of points I'm trying to find a minimum closing ball。Okay， let me ask you。

Is this the minimum and closing ball？Could that be the let's say the black points are all there is。

There are no other points besides the black points that I drew in this example。

 could this red ball be the minimum closing ball？Yes。WaiWhy do you say yes？嗯。

I guess maybe my question wasn't super clear， but I mean， forget about generalities。

This specific set of black points， is this ball optimal or not？No， it's too big， it's too big， right？

And basically， I mean， any ball， the point is any ball which is optimal。

 should have at least one of the black points on the boundary。

RightBecause if there are no black points on the boundary。

 I can just take the ball and shrink it around the this is a ball around some center。

That's the center， let's say。I can just consider balls around the same center that are smaller and smaller and shrink them until I can't shrink them anymore and why can't I shrink it anymore。

 I can't shrink it anymore because I just hit a black point。😡，Right。

 so like even for this particular center。The best ball around this particular center is probably the one that like touches。

You know， these black points that I'm now touching。

 I can't shrink it anymore because otherwise I would fail to include that black point。ok。And then。

You could then say， okay， now look at the black point that is on the boundary。

And look at the line segment from the origin to that black point。What is that。

 this is just some direction in the sphere。All I about all I really care about is the direction。

 I don't really care about the length right now， so that's some direction in this sphere。Right。

So this points P。P is the Arc Max。Overall， let's say。Points P prime in the point set。

 let's call it a P star。This is P star。 P star is the artrc max over all。仔。Overall。

1 less than equal to J less than equal to n of Pj dot v， right？

It is the points in our point set that has the largest projection onto that direction because it's the points in our point set that defines the radius and this is the direction of the radius。

😡，This is the direction that defines the radius， does that make sense？收。The point is if I said。

If I said that we're going to store。For all be in the sphere。We're going to store the arc max of Pj。

v。😡，Then that would be a perfect coret。Because like whatever the true radius is in the optimal enclo ball。

 that direction between the origin and the point on the boundary of that ball。

 that direction will be captured by this and P star will be included as the Arg Max for that particular direction。

😡，The thing equivalent to remembering or like keeping all the vertices of the context all of the points。

Right， except， well， is that？Yeah， except the problem is that it's not in。

We don't know what the center should be， right？诶。Right。

 but I'm saying for the definition of the corset， at least。I's it's take the convex hall of。

Or like keep all the vertices of the convexhu of the piece of J。Yeah。

 I have to think about that'm not I'm not convinced that that's right just because convex Hall convex Hall is more of an L1 thing。

Then L2， but then L2 bowls。Or yeah， I'm sort of reminded by like the alternative formulation of the like Gausian mean with where it's like the difference or I guess okay。

 maybe we don't want to go too much into the tangent here。I see yeah。

 so I mean we can come back to that， but this is what we're going。 So basically what I mean。

 the thing that would be perfect would be taking the ag max of the dot project with anyone in the sphere。

 The problem is that that might not shrink our point set at all Each one of our points might be the ag max for some particular direction。

不。😡，At least this way， since we're only taking a net of the directions and not all the directions。

we're basically promised that the number of points that we have to remember is that most the net size。

So now the question is like， why is this a core set and what alpha should we choose to make this a core set so our goal is going to be。

Our goal is a coreset。With approximation ratio。One plus epsilon。And the question now。Is like。

 what alpha do we need。Or actually sorry， these inner products are all like optimizing over P is like optimizing a linear program。

 right？Um， so， so like the Ps that you pick all are exactly the P's。

 which can be the optimal to some objective。That's right。

So that seems like it would mean that the subs you keep are exactly the vertices of the convex well。

嗯。Yeah， it sounds reasonable， actually。That does sound reasonable。Well。

 I guess I think the one problem might be the I mean what's the runtime to compute D dimensionsal convex all exactly I think that's。

That might not be fast in high dimensions。But even so， I guess。Oh yeah。

 it might not be an efficient way to compute it， but and even aside from efficiency like。

It might be that every one of the Ps are。Oh， I see。 Yeah， but I guess the point is。嗯。Right。Yeah。

 maybe that maybe that way you're saying also makes sense， I have thing about that。

 maybe the problem is only efficiency。系对。嗯。So kind of。

 what alpha do we need to choose to make sure that this is a core set？

So here's the picture that I want to draw so let's say that。Basically what I want to say is。

What I want。So let's say a week cor set。What I want is if I compute。The MEEB of the corset。Then。

Increasing it。The ball radius。By at most one place epsilon， let's say covers all points。

We already know that the radius of the MEB for the corset has to be smaller than or equal to the actual optimal radius。

 right because？😡，The P's that we're keeping in the core set are a subset of the original P's。

 so ball that covers the any ball that covers the all the points has to cover the core set。😡。

So opt can only be smaller for the corset。 And what I want to argue is that it's not too much smaller that if you take the optimal ball for the corset and just increase it slightly。

 you do get a ball that covers all the points。 Therefore you'll that that's a way to get you a ball for the。

For the original data set， which is within one plusulpsilon of the optimalum。对。So， let's say that。

You know， there's some。we have the subset and we take the minimumating and closing ball for the subset。

But you know， the reason that。If it's the minimum closing ball。There's some point。

You knowP P prime is in the corset。And is on the boundary。Of。The minimum and closing ball。And。

 you know。for ease of notation。I'm just going to assume that。The or the the send。

The center is zero because otherwise I'll just translate the picture so that it is and also if I you know I'm just going to assume that the norm of P prime is one。

Because everything that I'm going to say from now on is relative to the center and to the to the scale。

 which is the。Normal P prime so I can just translate and scale the picture。嗯。O。

So let's look at some other。Let's get some other。P。So， first of all， know。

 if all the original points are in this ball great， then I haven't lost anything。Otherwise。

 maybe there's some point P that's outside the ball。Okay。And let's take the P that。

 let's take the P that defines the。Sorry， let's take the P that defines the。

The radius that's on the boundary of the optimalim ball for the original point set。okay。

 take let's say take the P。Which is。Fthest away。From the center。I， that's really what I want to say。

嗯。So。That's， let's say this P。 if it's inside the ball great， I'm done。 if it's outside the ball。

 then I want to say something。 So let's say that this direction。Is W。Okay。

 all let's go on' say example's say it's V。I know because I have a net。

 I know that there's some other。There's some other V prime， which is in the net。

So this angle here has to be at most alpha。对。So where do I know， I know that。I know that。

P was not included in the coreet。😡，But P prime was and pre prime has norm one。Okay。

So if P was not included in the courseet。It must be because。嗯。What did I want to say。

I think we have a。Yeah， I guess what I want to say I just want to say。

 I just want to look at this dot product P dot v prime just give me for a second so P dot v prime。

 what do I know that equals。That equals。The norm of P。Times。The Norma V prime。

Times the cosine of the angle。Between P and V prime。And I know that this thing。Is that most？

It's at most the maximum dot product with V prime amongst the point set right since P was not included in the corset。

 there must have been something else。😡，In the core set， it had a larger dot product with V prime。

And what can I say about that point dot product with V prime？Well。

 that point is contained within this ball of radius1。😡。

So that point Do product with V prime had to have been at most one， so this is at most one。

The norm of v prime is one。These are L2 norms， so this this all implies that。The norm of P。

Is that most？嗯。One divided by the cosine of that angle。This is called an angle Theta。And。

This is at most。1 over a cosine of alpha。And what do I know about the cosine of alpha。

 when alphas small， I know that the cosine of alpha is basically one minus theta of alpha squared。

 just is by Taylor expansion。So this is utmost。One plus biggo。We one， you one plus。

1 plus o of basically alpha squared。Right and I want to I want this to be one plus epsilon to argue that if I just increase the ball by a one plus epsilon factor。

 it'll contain all the points in the original point set so basically I want。

I want this theta alpha square term to be epsilon， which implies that alpha should be basically root epsilon。

So that implies that my net， which has size theta of1 over alpha to the d minus1。

 is actually theta of1 over epsilon to the d minus1 over two。Has desired。And that's basically it。

So are there any questions about this construction or the analysis of it？Yeah， actually。

 so the initial。Dot products are computed。Computed with respect to the or like the initial center of the ball。

Is the origin？You mean initially when you take dot products？嗯。

Like the the Vs I guess like I guess like so I think I think yeah。

 so I think I see what you're saying， which is basically。

Like what if the what the what if the center is not the origin， right。

 but every everywhere like let's say that， let's say the center here was not the origin。

 but what is some other what some other。Theres some other point Q。

Then fine just instead of V look at like v minus think of it as v minus  Q and v prime minus Q or yeah but I guess like is there any requirement that the the origin like the p's need not be centered right the P' might be very far away from the origin that's true right okay so so then what I said earlier about it just being the con spell is not completely correct right it's like the vertices of the origin union with the P。

The vertices of the convex hall of the originig Union， all the piece of cha。Oh。

 right because there are instances where you need to or you don't or sorry。

 some particular piece of J might be on the convex Hall of the Ps。

 but you don't want to include it in this corset because。

It's like closer to the origin than all the other piece of Js。呃。I'm not sure right now。Okay。

 so but most of what you're doing， you're still saying though， that。

You should be able to reconstruct the coret via some convicx whole computation right yeah it's just it's just on one more point yeah。

RightYeah， I don't the thing is I don't know offhand， I mean I know。

I do know that runtime behave very poorly for convex solid high dimension I just don't't I think it maybe is also like exponential in the dimension。

 but I don't remember the exact。I don't remember the。The exact runtime。Okay。Like for example。

 is it something like end to the D or end to the D over two or something maybe it's。

Maybe it's better， I'm not sure。I'm not sure exactly them， I'll have to look that up。O。

So I think maybe we're out of time， but any other questions before we move into final projects？

Wednesday and beyond。Okay， so I hope you enjoyed the semester and I will see you all Wednesday for projects。



![](img/ad55bd2a2fa9aba8527d76dc73d18def_2.png)