# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P22：lecture 22.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

Good to see you。

![](img/9a1f99e6050df919b42d16cc2272e8cd_1.png)

Today we'll finally see a couple of applications of some course SDP we've been sort of。

We wrote down the SDP， then we looked at duality and how the duall of the degree sumos square SDP corresponds to some square proves。

And we built up all of this machinery and today well see a couple of applications so。So let me start。

😔，So the。So let's start right away and so let's look at the the first application that I want to show you is to this problem called robust。

Linear regression。Okay， so what is this problem so the setup is like this。

 so you have some unknown linear function。So a linear function， let's say specified by a vector L。

 so you have some vector L L hat。This is an n dimensional vector。Its length is one。

Just normalization。 And you have this unknown linear function。 Let me call that。L hat effects。

Is equal to L in the product X。Okay， so you have this unknown nonlinear function and know you're getting samples from this。

So how are you getting samples from this linear function？嗯。So let me call。

 let me say what the true samples are， So the true samples are， let's say。These are the true samples。

 they look like you have some vector x hat。Ex hat is。And the value of the function。And。Exhat。Okay。

 where x hat is some point， let's say random Gaussian vector or let's say random plus minus one vector for simplicity。

 let's say random plus minus1 vector。And this is the value of the linear function there。

Okay you're getting samples like this。Well， if you just got samples like this you know finding the linear function is really this linear regression actually let's add in another little piece here。

 let's just add in some little bit of you know some kind of simple noise。

 let's say gamma gamma is a Gaussian noise。It just for。To some random goian nice。Okay。

 so now so you're getting samples from this， and if you just got samples from this。

 the most natural thing to do is to， you know you just fit the linear function is to do least square regression and you'll get back L hat okay。

Okay， so in particular， really what you want to care about is you want to find。嗯。Your goal if in。

If there was no noise， or is to sort of given the bunch of samples like this。Exha I。维系。Examples。

You want to find the linear function。L， that minimizes。Let's say the squared error， right。

 the squared error would be so you could find like something like。P you do this。Pro不。去。Great。

 this is the problem you saw。Okay， and did get that。Okay。

 but this is just the usual linear regression。Now what the setup we are in is a little bit more complicated in that you don't get these true samples。

 you get these samples mixed with outliers okay， so the actual example。

 the input distribution that you have is you know for simplicity。

 let's say it's like this so your linear regression with outliers。So without layers。

 the situation is。You get。X A y a。But then。With one minus epsilon fraction of the time with 99% of the time。

It's actually a true sample from the distribution that we care about。Okay with pro t1 minus epsilon。

 it is a true sample， but then with probability epsilon， it's arbitrary and adversarial。

So about 1% of your samples are arbitrary and adversarial and one mepsal infal。嗯。True samples。

 and you want to still find the linear function L。记得唱个。Their goal is to still recover。

Recover the original linear functional hat。Okay， close to approximately and note that， you know。

I intuitive， it's kind of。Makes sense that you should be able to recover this because。

You are being on a linear function， being you satisfying being close to linear function is such a strong constraint that。

If you only corrupted 1% of your samples， in you'd imagine that there's still a unique linear function that fits the data or fits 991 minus epsilon per fractional data。

But I guess the key computational question is how do you find this linear function the difficulty is you have some data points。

And you don't know which ones are actually true data points and which ones are。False state up。

 which ones are just adversarial points and。I guess you know that's really the problem it's difficult to figure out which ones are true and which ones are spurious if you knew which if once you figure out which data points are the true data points。

 it's you know youll just run the linear regression so really the difficulties in figuring out which ones are true and which ones are not。

Okay， so that's the problem we'll solve and we'll solve this problem using someos Square SDDP。

All right， so to do that， you know， let me just。What do you do always when you want to use a Sos SDP。

 you first formulate your problem as a system of polyno equations。Okay。

 so let me write down what the system of polynomial equations are。So here's the polynom system。

For linear， for。嗯。Yes。So let's assume that you have， I guess did I use N already？Let me say D。

 let's say our samples are in R to the D。Okay and let's say you have N samples。

Any some really large value will fix it to be something largely。You end samples。

OkayNow I want to write a polynomial system， what are the decision variables。

 the key thing which is un missinging is which sample is a true sample and which is not so let's say we have a variable for that。

So WI。Is。Is you know， the intent like what we intend for W is that it's1 if I is a true sample。

I is a X the right sample is true。And。Zero if it's unverilient。Okay， that's our intent。Okay。

 those are WI variables。 you have W for I equal to13 n。ok。Allright。

And then what are the variable we have once we figure out the WI。

 what we also care about is of course the linear function。

 so we have some vector L this is an unknown vector L。This is a linear function that we want to find。

L in r to the D。你等下。in LA code L 13 LD， this is the linear function that we want to find。

 so these are our variables。Okay， and what's our linear system going to be okay so let's write down the link not linear system on the poly system。

 the poly system， okay firstly， we know that W is 0 or 1。

So let me write a constraint for that W squared minus W equal to 0。For all I equal to 1 through n。

 So this is the same as saying W is 01。Okay， okay， what are the constraints？

I know that at least one minus epsil in fraction of samples are true samples。

 so I need to say that if I add up i equal to one through N W。This is at least one minus Epsilon n。

 so let's just say it is equal to1 minus epsilon n for now。Okay this is a。

This is just saying that the number of true samples is at least one is epsilon it。Okay。

 and then we have some normalization on L， right？So what is the normalization of L， let's say。嗯。

Right the2 normall is is1， we assume that right， so2 normal fell squared this is saur I L squared。

 this is1。Les than equal to one， I guess yeah， less than to one， whatever yeah。Okay。

 so these are the constraints and。What do we want， we want to。

Minimize the average the square error right and we want to minimize the square error on the true samples really。

 because that's what。We want to do。 And so I'm going to write a minimization。

 So the mini minimization would be。mininimize。The true error error。 So the true error， you know。

 is going to be。Samurai， W， I。So W will select only the true samples。Times the error。

 which is Y I minus L in the product。X世。Whole square。T equal do one through him。Okay， so that's the。

That's the quadratic form， I dont know， that's I guess a cubic。This is the true error。

Andm just going to divide it by。Some normalizing factor。This is just to say， you know。

 I know that there are n times one minus epsilon samples which are true and so I'm just going to divide so we get average quantity this average error。

Average squared or just this first one， it doesn't matter what factor you put in there。

So I want to minimize this polynom。O。And。😊，Okay， that's the setup。And you。

 one thing I want to stress here is we're going to be manipulating polynomials。

And these polynomials will will have true indetermininateants there are variables in the polynomial and then there are constants that we know so let's sort of remember what are the variables our variables are only ws and the L because that's what we're trying to find so everything else here is known like the n and one minus epsilon this is known and of course that's known but also here in this minimization the Xs are samples that we have Ys are also part of the samples that we have so really this is a polynomial just in W and L。

So polynomial in W and L of degree3， w is degree 1 in W and degree 2 in 3 L。Okay。

So it's important to I guess， remember， all our polynomials are polynomials in W and L。

Everything else that you see are constant and known thing， things that you know。🤧嗯。All right。

 so this is our polynomial system and as you can imagine it's sufficiently in general polynomial system that if I just gave。

 you know it's probably NP complete to just solve such a polynomial system in general like if I give you any polynomial system in general it's going to be NP complete to solve。

So， but what you can do is you can solve SOSSDP relaxation of this polynoural system。Okay， and。

So if when you solve the SSDP relaxation of this polynomial system， it gives you moments。

So let's say you' all。Solar degree。Let's fix the degree later。

 let's say degree 10 for now degree 10 S O SSSGP。Relaxation。Of this system and when you solve it。

 you get moments like you get back you know， the moments every sub of every polynoal in W and L。

So for example， youll know what E Eil W w1， Eil W W n。啊。And then you'll know it of L， LJ。E W W I W J。

You know， it of W I。Aline。And W I L L A LB。things like this。He， you'll know all the moments。Okay。

 and these are， again， to remember， these are fictitious。我速度。冇ments。

Of a distribution or solutions of the system。Two system， let me call the system peak。

So this is the system， let me call the system P。Do the system be？Okay。

 so you just get these bunchs of numbers now we need to extract a linear function and you know we need to prove that it works Okay。

 okay so。Okay， so how are we going to extract the solution？Well， you in this case。

 it turns out that there's a very easy way to extract the solution。嗯。You just set。You know。

 you just look at Eilda。L。Eilda l1。E in the L。This gives you a linear function that you want。

You just output this。Outputel star is this。It's an or we are outputting the function linear function L star of x is this quantity E tilda of。

L in the product X。You're outputting this linear function。Okay， and that's the fit。 Okay。

 when we'll see why this works。 Al right， so， okay， so let's do that now。Okay， no。

So we solve SD relaxation， we have no idea what these numbers are。

 this just gives you these numbers and how do we infer facts about these numbers well we infer facts about these numbers why are some of squares proofs。



![](img/9a1f99e6050df919b42d16cc2272e8cd_3.png)

For example， well， okay， let's look at the simplest fact。



![](img/9a1f99e6050df919b42d16cc2272e8cd_5.png)

We know well， the simplest fact is， well， we wanted WI to be。What did we want it to be。

 we wanted WI to be in zero， well actually we want W to be0 or one。1。W， I to B0 or1。Okay。Well。

 of course it's Eilder W， this implies that we want the moment Eil our WI。We want it， this is one。

 we want it to be a number in0 and one。Because it's supposed to be the expectation of a quantity which is zero or1。

 so should be a number between0 and 1 and should sort of tell you the probability that WI is one。

That's what E W should be， but so can we prove？So how do we show？How to prove that。

EildawiI is actually a number in0 and one。Like in this interval 01。

Okay well we solve SDP we got this answer， how do you prove that this is is in the range 01 well this is going to be why are some of square proofs so what do we know？

We know that。W squared is W。So let's try proving some something very simple okay。

 let's try to prove that Eil at WI。Is greater than equal to0。Well， why is this true well because？

We know that W squared is equal to W。And w squared minus w equals 0。Right and therefore。E tder w。

Is equal to E in the W is squared。Right and it the W squared is actually a square of。

It's a pseudo expectation of a square polynomial， so therefore this is grade equal to 0。

Because W is squared is squared polyno。We know that in every square pole， let's acknowledge。Okay。

 but alternately it could I can say that I want to prove that mean equivalently this is equivalent terminology。

 okay， I want to prove that W is greater equal to  zero。

How do I prove that Well W is equal to W squared from the constraints of the polynom system and W squared is square so it's greater than equal to 0 and that's it so this is a proof。

I it proof that WI squared is great is great？Right so。

If in order to prove that E is greater equal I need to find a sum square proof that W is greater ne0。

 Okay let's do something slightly。And。冇日。Interesting， so okay。

 so let's say I want to prove that WI is less than one。Okay。How can I prove W is less than one？

So how do I prove this， well here's a proof。The proof is。诶。Yeah。1 minus WI。

Is actually equal to1 minus WI whole squared。Let me write it this way。Okay， if I look at1 minus W。

Square。This is grade equal to 0 clearly， and what is this equal to this is 1 minus2 w plus W squared。

Okay， that's create equal to0， but that is equal to 1 minus w。Because。

I guess because w squared minus w equald0。So I proved that1 minus w is greater equal to 0。

So which means WI is less than equal to one。So1 minus w is greater equal to0 implies W is less than equal to 1。

ok。So we got that what so what did we get， we got Wl less equal to1 using an S S proof。

 we proved that W is less equal to1。Using SSs。说。Okay， so I guess you're like the。

So just to say the difference here， right？So here's a。As so as like we saw。

We saw anSo we proved that WI is in zero the interval zero or1。All sorry。

 let me just be more precise。 We proved that W less than one。Actually， let me please yeah。

We proved that W squared minus W equal to 0。In place。That WI is less than one。ok。

And we proved this using a degree2 sum of square proof。And of course， you know。

 like in the real world， if I just gave you w is squared minus w equal to0， right？

And ask you to prove WLSn equal to1。Here's a perfectly valid proof。

 you would say w is squared is w equal to 0， therefore w times 1 minus w equal to 0。

 this implies WI is0 or1。This implies W is less than 1。Okay， this is a valid proof。

It's a valid proof， but it's not a summer square proof。

Because it involves not just algebrazebraic manipulation， it involves， you know。

 it's just really a proof where you use all the things that you can do。

But the proof that we saw here。This is an algebraic some square proof。

Okay this is an algebraic sum square proof of the inequality okay so that's what we are going towards so why is an algebraic sum square proof good for us because if you once you have an algebraic sum square proof you derive the same fact about the SDB solution。

Because of this algebraal square proof， now we know that E t of w is less than equal to one。Okay。

Okay， I'm not going to formally define。嗯。What a summer square proof is， but I guess you know。

And sometimes the rules are something like if you derive。

Let's say you're starting with a polynomal system。If you derive a of x greater equal to zero。

 and then you derive b of x greater equal to0。Then you can add the two， right。

 you can derive starting with the same polymerno system， you can derive E of x times。嗯。历车。

I don't know you can multiply by square polynomial。So a of x times alpha of x whole squared。

Plus b of x times beta of x whole squared is greater equal 0。

That's the rule if you derive two things， you can derive their sum。Right and what else， of course。

 you can always derive one is great ne zero or alternate。Ally， you know。

 you could say you can always derive a square polynoial is greater equal to zero。

Alpha of x squared red equal 0。These are basically the rules。

And you have to derive what the statement that you want。From the polymer system that you have。Okay。

Allright。Okay， so呃。Yes。Okay， so let's see what good this is。Okay， so what we will prove。Is the fo。

 so we have this polynomial system for linear regression。嗯。

We have a polyomic system for linear regression。Here's something that you would want to know once you write down the phenomenam system。

Okay， here's a。Identifiability。It's called identifiability。This is what you would want to know。

You would want that any solution to this polynommal system is。Gives you a good linear function。喂。

You would want the following thing。Any。Solution to B。7。Kil， any solution。

 let me write down the solution， any solution W comma L。An actual solution。

Here I'm talking about an actual solution。To this sleep system。I。

Good for you what is a good what's good where it's close to the true linear function right what' what is close to linear function mean let's say satisfies small error right satisfies small error on the true examples。

Right so， let's see。If I look at the true examples。嗯。So let say。Let me call true examples to be。S。

These are the true examples on the true examples， if I look at the error。Incurd。

Right this you want it to be small， I don't know if some smaller than some delta。Okay。

 is what this is the sort of statement that you would want。

Like you on forgetting some Sc SDP or whatever， or if you write down the polynom system。

 you want it to be true that any solution to it has small error。Okay， now。

 of course you can prove this in any way maybe you could try to prove it using any technique。

But what we will do is we will prove this claim。Using a summer squares proof。Okay。

 we will as plan will be。妖先。And soO S proof。Show identifiability。Yes。

What is that will show this fact？Using an SSS proof will show this fact。

And the beauty is now we are just provinging some algebraic thing。

 we are proving that polymerm system P。P implies on the true examples some or I in S Yi minus L in a product Xi whole squared is less than whatever value or we'll figure out the values and everything now。

 but we're proving this thing。This is just an algebraic statement。

Using SOOS using degree I think we'll use degree4 or8 SOs or something。

 so degree4 let's say degree8 Ss using a degree8 SOS you prove this。Okay。

 this is an algebra thing and because。Of a claim， once you have an SS proof。

 the same fact also holds for the SDP solution。So， this implies that。Like if I look at eat Tider。

Of on the true samples。The error on the true samples。

Is also smaller than this whatever quantity deelta。Again。

Now this is a statement about our SDP solution。Okay， and。嗯。And then， you know。Okay。

 so this is already pretty good already， but and then you can actually go a step further and say that this this is greater than what you would have the error you would have if you look at the output linear function。

Or if you look at。If you put E tilde L， you push the E tilde L inside。

The error that you'd have there。And so you would conclude that your algorithm that outputs E till to L。

Theal good output outputs e till the L。Is actually a good algorithm as in its error is at most what our quantity delta is。

O。😊，So most of the action is to show。This is in a sum square way。That B implies this in some course。

Okay。食。Okay， so so let's。Continue。All right， so let's okay， so how do we。Sure this。就。啊。Okay。

 so how do we show this So so before we show this， you know， let's try to just。嗯。嗯。Okay。

 so let me write down a few inequal few things that。嗯。Actually。

 let's just plunge in and see and pick up， you know。

 when we need something we'll try to prove it or see how it is， okay。

 so here's what we want we'll try to prove。So the theorem that will prove is the following。

 So if Eilda is。So let me say this。Suppose itll the。Is a degree for。Sudo expectation， functional。嗯。

And。At a start。Is equal to。Eilda L。Should the expectation functional for the polynomial system？

P that we had。 Okay， and L Star is a super expectation now。 Then we want to show that。

Errror on L star， the true error on L star， which is some or I in the true samples。

 Yi minus L in a perex I。Hold squared is smaller than the error on the。

True samples for the true linear function that we had。Remember。

 we had a true linear function that we started with。But you can only compare to that。Plus。

 order route epsilon。Okay， of course， I need to normalize everything， sorry。😔，1 over cognitive S。

1 over cognitive S， where S is the set of true samples。 So on the true samples， the error of L。

Is at most the error of。L hat plus an additional square root Epsla。Okay， so。All right。

 so let's try to prove this。And again， we'll be using a summer course proof here， right。

 so how do we prove this？Okay， so。Let me in。Introduce one thing， one notation， let me call W hat。

To be actually the truth thing，1 if I is in S。I and S， as in it's a true sample。Zero otherwise。Okay。

 it's kind of useful for proof it makes it simpler。Okay。

 so now let me start with the left hand side here。What is this left hand side？nHS。I。1 over。

 I guess one minus Epsilon n， that's the size of the number of true samples。

Some are equal to 1 through n W hat， this selects the true samples。

Yi minus L inina perex I whole squared， okay？Allright， now。And。唔'm sorry。Okay。

Okay I should put El Star here， right？😔，嗯。You know， let me put an E E Tilda here。Itil I here so it。

在意。Yeah， let me put Eilda here， you just start so we have E tda here。Okay。

 this is what we are looking at。All right， okay， so now。Okay。

 what what's the you know it's just going to be a bunch of algebraic manipulation。

 so what is sum or I equal to1 through n？W I hat times1 minus W I。Times Yi minus L in a product side。

Pall squared。Plus sum over i equal to1 through n。W， I hat times， W I。Y I minus L in a product excite。

 the whole squared。Okay， so that's。What did I do here well I just。嗯。I just wrote W I had。

Times 1 minus Wi plus W hat times W， so that becomes W hat。KW I hat is。

WI hat times 1 minus W plus W hat times W。Okay， so what just happened here is。

WI hat are the true samples。WI hat times WI these are intuitively the true samples selected by the SDP W hat times one minus W of the true samples that are left out by the SDP because WI indicates whether the SDP picked or not but you know WI is not real zero or one thing just algebra prime okay alright。

 so now let me call the first term to be one。And the second term to be2。Okay。

 and let's see what how the first term and second term behave have。All right。

 so let me write down the second term first。Second term。嗰别。What is the second term？It is this。

This is a second term。Okay， so what's the okay， so what is this second term well。

It's a sum of errors on all the true samples， but you know both。你。If I。If I dropped。

 if I add in all the samples。Then of course， the error will be only higher。

 so let me just add in all the samples here。13 and Wi times Yi minus L in a product X side whole square。

This is by adding in all the samples。So what I did was I。I dropped。

W I hat because I'm just using alternately， let's say using W I hat less than equal to one。

Using WI hat less than equal to one。I have this。And W hat is actually we are in safe territory it's really actually an integer right it's not some pseudo integer and thing W hat is whether a sample is in the true true sample or not it's actually an integer zero or one and so therefore you know this is a very legit thing I just。

嗯，好。Use W hat less than equal to one here and now what is this， well， this is just the SDP optimum。

This is what we minimize actually。AndRemember in a polynomial system。What we minimize is exactly。

Summation WI Y minus L a perx I ho squared。On the samples that SDP selects。

 we want to minimize the error。Right。So this is thet opt。Okay， so that's good and we know that。

 you know， essence since SDP opt is actually。Going to be smaller than the true of because。

There is deepP relaxation， it's a relaxation of the true polynom system。はいで。

So this is actually smaller than the error of the。True linear function。Right on the true samples。

This is because。It isDP is a relaxation。ok。All right。

 so that's good so we already bounded the second term。Here， okay。

 now we need to bound the first term， So let me just copy the first term。是。All right， okay。

 this is the first term we want to upper bound this quantity。All right。

 so here remember always that WI is these are variables， WI and L are variables。

WI hat is some fixed integer0 or1 right it's whether the sample is true or not Yi and XI are also really just actually known fixed values the real variables are just WI and L it's a polynomial in W and L that we're talking about here。

Okay， and so here we will use this identity or inequality。

 it's called the pseudo expectation Kaauhi Schwartz。Okay， so let me just。嗯。

Say what Kaushi shorttz is well， Kaushi shorttz is this right。

 you have sum over AI B is less than equal to summation AI squared。

Hold to the half times summation B squared hold to the half。Okay， that's usually Kahi shorttz。

This is our Kahi shorts inequality。Okay， there's also an。

 there's also an expectation Kahi Schwars of this， which is， if you had any real actual expectation。

 the same thing you can write， just put in expectations everywhere。Okay。

 this is usual coffee shorttz。There is a。I mean many of the algebraic statements they have some square proofs。

 so there's a sum square proof of these facts so there's actually a corresponding pseudo expectation fact here so heres a pseudo expectation Kashi short which is also true。

It is just the same thing， but with pseudo expectations。

And the way to prove this is just by constructing a。

Someumqua is proof of the statement that you care about。Okay， so but also let's let me just write it。

1 through N， AI， B I。Is smaller than。一点だ。Surai AI squared。Hold to the half。T eating till the。Okay。

 I should put the braces in the right places， some more J， Bj squared。😔，H do the half。Canect me just。

Put the brace out， it's more clear。😔，Okay， it's just the same thing。

 it's through expectations have expected。Okay， so。So how do you prove such a fact all of these are very short proofs you know you can I guess since I'm doing only one lecture of sum squares I'm not going to prove it here。

 but you know like many of the standard facts like holders inequality。

 AMGM inequality Kaushi shorttz inequality they all have corresponding sum of square proof for example if you care about Causi shorttz so what is Causi shorttzs well kussi shorttz is this right some over I AI BI holds squared is smaller than some over AI squared some over J BJ squared。

This is a usual thing and you can prove it in any way， but it's also a sum of square proof of this。

 what's the sum square proof of this？Well， you just observe， here's a sum square proof of this。

 you write on RHs minus LHs。Like this is RHs， minus Ls。

RHS minus LHS is actually equal to sum over IJ， AI， Bj minus AJ， B whole square。

So actually you know if you take Caus shorts inequality， you take RHS minus LS。

 it's actually a sum square， so this is of course greater equal0 and this is a sum square proof of the inequality so many inequalities are a summer square proof。

And so， so now we'll use the pseudo expectation kusci shorts that we have here。Okay。Okay。

 so now if you use sort expectation coffee shorts， were going to use it here。

What will our AI be or AI will be。嗯。These two together， that'll be AI。And this guy will be BI。Okay。

 so I'm just going to get。Soer expectation。S over i equal to1 through n。1 minus W， I。Hold squared。

Hold the half。Dammes。let me just put the bracket out of that。😔，It's easier to understand。😔，Oh， sorry。

 I did the same thing。Okay， yeah， times。E the love of。What is the B squared。

 it is sum over I W I hat。Times Yi minus L in a cortex I。Hold square。Hter to the half。是。

 and just use survey expectation commercial shorts。Okay， so。You can help me。Called this term。

3 and call this term four just first， Okay， what is three？3 is what， well， it's。Eil of。

S over I1 minus W squared。😔，I'm going to expand its。It did of。嗯。

Right1 minus w squared is actually1 minus2 W plus W squared。 you know。

 we can check that this is actually。Just。S over I1 minus W。This is actually n minus E t sum over I W。

You know。喊。That is n minus1 minus Epsilon n， so this epsilon n。

 we like you just say is Epsilon n is equal to Epsilon n。I mean， why did we get this， Well， you know。

 it's just remember we have a polynomial constraint that。There are one minus epsilon n samples。

That are picked by the SDP some or I W is 1 minus Epsilon n。Okay， someur I WI is1 minus Epsilon n。

 so some I 1 minus WI is Epsilon n so。Yes。So we get that this is at most epsilon。

This third third quantity is actually I ut most argument。

 depending on the way you write it in see equal depth on。Okay， so。All right， so。

So I guess we are left with just the last the fourth quantity here。嗯。Okay。

 so let me do the fourth term。是。嗯。The fourth term is what it's some or IWI I mean don't worry if you didn't sort of keep got get all the pieces of what's going on in your mind it's okay it's a bunch of algebraic manipulation。

 but really what's happening is really we're doing great school algebra to go from polynomial system that we have to the inequality that we want to prove the inequality that we want to prove is this inequality。

Okay， and we are just doing grade school algebra and the only restriction is our hands are tied we can't just you know prove it any way we want we have hands are tied because we're only supposed to do add multiply。

YouSee that if you see a square we can say what's greater a those are the only things we have allowed lot to do。

 but everything else is like you know just you know we're manipulating algebra right okay that's what we're doing so。

So okay， so what's this fourth thing that we have here？Okay， it is this， well what is that？Okay。

 how do we bound this Okay， so let me。Write it。 some of I W I hack。Y I minus L in a X I。H square。

Sorry， W squared to the4， sorry。😔，Yeah， okay， there's a。Yeah， Mr。 square here。

 this is a square here and there's a four here。😔，Yeah okay that's the key point so there's a square and a four right it's really because when you did Causi swordtz we squared the terms here so we got square and a four Okay so this is what we are Aa squared times okay so now okay we have some inequality like this How do we deal with this well。

Okay。嗯。So。Okay， so let me。Right， okay， so let me do it。W I hat times。Yeah。

 I think we are in good shape。 because just let me do something very simple。 Okay， so you know。Okay。

 here's something I can prove using summer square you can check this so I can prove that a plus behold to the four is smaller than。

I guess it plus behold the four is smaller than。嗯。I think I want to say two to the eight。嗯。8。

 a to the4 plus a b to the4。Okay， I think I can prove this using summer squares。 Okay。

 so using summer squares， the key point is。Using S O S。I know this Okay。

 so therefore I can have this a plus behold to the four here。 I can replace this by eight times E。

Some or W squared times Yi to the4 plus。L in a paraex I hold to the four。Okay， hat said W hat。Okay。

 so exist。嗯。I can improve using some scores。 So therefore I can write that。 So now， okay。

 so now what are the numbers here， I just want something very like in this in this part of the expression。

 I what I'm looking for is some reasonable bound on the numbers involved Okay， so so I have8 and。

Okay， so this W hat is at most one in fact W hat is zero or one right so let me just write。嗯。Okay。

 let me be careful about that， let me say that some or I in the true samples。Yi to the4。

 that's what I have and some I in the true samples。Of Elina product Xi。Or do the four。Okay。

 so far as。y， okay， so now诶。Allright， so now what is。嗯。Okay， what's the bound I have？Well。

Okay firstly these YIs are in the true samples I'm summing our true samples I got a some or true samples because I had some or everything here but it had a WI hat in the big top front WI hat is one only p' is and a true sample and zero otherwise that is a definition of WI hat therefore it got only true samples and for the true samples I'm going to say that。

Typically the YI value is order one。In fact， you can。You can bound the first term by order N。

It's even a constant right it doesn't depend on Eilda， it's a constant， so the first term is orderM。

Because remember what YI was。For at least for the true samples， the YI was what。

 let me just go back here。Well， why I was firstly。You have standard Gaussian noise。

 which is order one， you know an expectation or squared nu is order one， and then Elleena protects。

 the baby scaled it。L is a unit vector， x is a random plus minus1。

 you can check the L in enough product X， this is order1。Like， I mean， not always。

 but if you look at the squared expectation， it it's order one。It's one， in fact， with。So， therefore。

对。Y I is order one， So you get order and the。Fort moment。ok 。It's， yeah， it's a。

We someborn in the fourth moment。on the of the random variable， and then okay。

 then I need to bound this guy。N。P I pull to the4。ok 嗯。All right， so。Okay。

 so how do we bound this while we say， you know， this is order end。Plus eight times。

 I guess keep the details around， I guess。You didn的。Of some。Eina product。

So let me just write it out fully Elena products I hold to the four is something like。Some are A， B。

 C， D， L A， L， B， L， C， L， D， X。X， I A， X， I， B， X， I， C， X I， D。

I'm just expanding alienena products hold the floor。Okay， so order n plus8 E tda。Okay， so let me。嗯。

Could we put a one over。If people let me。Sorry， let me put a card at your fasci。It's simpler。点だ。

This is some1 over S， some over I ins。给。X， I， A， X， I， B， X， I， C， X， I， D。Okay， times LA A， L， B， L。

 C， LD。RightThat's what you get and you know I had to have some over ABCD。

We should put a some more ABC。A b c d。Okay， so I mean， what's happening here is。I mean。

If you want to see what's happening， really what's happening here is just and sort of replacing。

Terms that come from individual samples by terms that come from average of the samples。

 So if you want to see it more clearly， right so。I guess this is a more clearer way to see it so what we have is this L in perex I hold to the for。

suppose I have a thing like this here L is the variable。Exse are the samples。

You know excise and then you're taking the average of a samples of a polynomia。Okay。

 and so if you have the number of samples， n is sufficiently large。呃。

Taking the you know average over the samples is the same as taking the expectation over the samples right and as well take expectation over the distribution over samples expectation over the sample distribution。

This a true sample distribution because the average are true samples of this quantity。

Of this polynomial。Okay， so right now I'm just saying， okay， so now let's see what the polynomial is。

 well it is sum over LA， L B， L C， LD times。You know， expectation over the sample distribution。

Meaning x is sample this x is from sample of X A， X， B， X， E， X， D。Okay， and okay。

 so now if x is uniformly random plus minus1， when is X A X b， X， X d equal to non zero if if x。

 remember that x the input distribution， the true distribution was random plus minus1。Okay。

 so therefore。So yeah， it's the tool。Input distribution was a random plus minus1。That means that。

This expectation is non zero only when a equal to B。C equal to D or a equal to C。

 B equal to D or a equal to D， B equal to C one of those conditions hold if all the four indices A BCD are distinct or if one of the coordinates x is is distinct from all of them and you take expectation it's zero so basically if you check it out this just becomes。

I think， at most。Like three times。The some。嗯。Of a risk。Squared。Times some LB squared。

It is at most three times， the two norm fell。Square。Hold square。

Basically all I'm saying is if you look at all the terms that survive。

 they are only squared survive so only terms survive are things like LA squared L be squared LA squared l be squared l squared and so on。

 and therefore what like this entire expression is at most some three times the two norm squared。烦。

Okay， so you substitute that here。You get that this is order end。

Plus the now eight times the number of true samples is also order and。

Times this average quantity was like。Normal squared。Whole squared。And now， itilda or itilda。

Normal squared whole squared and what is E to the normal squared squared Well well normal is at most one。

 that's a constraint of the SDP。 So this is at most order around。Order end plus order end。

This is at most one。That's a constraint in a poly system is normal squares at most one。

 so so get the whole thing is ordering。Okay， so we you。

You plugSo weve got the four is at most order end。So you plug that back in here and you have the value for three is at most epsilon n。

So this is at most end， this is atmost epsilon and and plug it back in。

 you will get back this result that we're talking about。

It is a little bit elaborate the way I did it， but we've been write down it suddenly like a page of inequalities pushing around。

嗯。And so what did we get at the end of it， weve concluded that。

If you solve SDP and your output E the L。The error is at most the error of the true linear function on the true samples plus an order root epsilon。

Square root long。Oh。In the。Any questions on this？对。So。嗯。

So you can use the somewhat basically the same schema to get。

To prove that to get algorithms for robust mean estimation or robustly learning mixtures of Gaussians。

So you have k optionss you're getting samples from that。

 you need to learn the means you write on a polynomial system。

 you prove that any solution to the polynomial system。

Is actually close to the true answer that you're looking for。

That's basically the main idea and you prove that any solution to the polymer system is close to true answer you're looking for in this case。

 for example， the true linear function， but if you're looking for Gaussians， the true Gaussians。

 you prove this fact using a summer square proof and then you're done。

And then you get an algorithm out of it。Okay。嗯。Yeah， so actually。

Ambitious levels was hoping to do the Gaussian case today。

 but it doesn't look like I have time to do it can I can post the notes that I had for that if anyone is interested but。

It's again， like right on a polymer system， then you do some grade school algebra to prove that any solution to that is actually the answer that you're looking for。

嗯。And okay， so。嗯。I guess I mean that's sort of what I wanted to say about designing algorithms in summer Square as repeat。

 maybe I'll try to see if I can say some general things about summer squares firstly a lot of univariate facts can be producing summer squares。

mials facts about unated polynomials are actually。Prorovable using summer squares。 In fact。

 I think we use this one on the homework。 We don't prove it， but。Here's a fact。

 you can try to prove it on your own a univate polynomial。The effects。Is grade equal 0？

Different only if。You can write P for all x， P of x is greater nelig for all x。If you only leave。

 p can be written as sum squares。So， therefore。Some if you had univted polymmal minimization and maximization。

 some of course SDPs work。嗯。Now you can try to prove this factor， it just need some。

I can validate to give you use。Use the fact that every degree polynomial has N complex roots。

And these roots come in conjugate pairs， you can try to prove this fact。So this is one fact。

But then there are many things that are obviously true， but it's very。

 very hard for to have some square proof。So for example。To give you an example。

 so here's a simple fact。嗯。Well' I mean， it's an obvious fact once I write it。Can I have n numbers。

 X equal to0 or 1， can I have n numbers， X squared equal to X？

So this is this means that X is in0 or1， right that's what this implies。

That's what this constraint implies。 We know that， but the the algorithm doesn't know that。 Okay。

 say X square equal to X and。Let's say summation X is equal to some fraction let's pick up pick some fraction。

 I don't know I equal to one through n let's say it's。I don't know， N over2 plus pi。Okay。

 so what we are saying is can you have n numbers which are all01 whose sum is actually not an integer？

Okay， so this is a polynomial system。Right clearly there's a parliament system。And of course。

 it's infeasible， there is no solution to this system。Okay， but。

There is no summer squares proof of invisasibility。Well， what is true is that the following is true。

点咧。嗯。Proving that P is in， how do you prove something is inible is you start with the polym system and derive a contradiction using summer square right P implies。

I don't know， zero equal to one。Using S O S Okay， or sorry。

 not zero record one negative one red9 zero。Okay， so in order to derive any contradiction or in order to using a sum of squares algebraic proof proving that the system is infeasible。

Needs， degree。OrOmega n。You need degree omega and to prove that this system is in in particular in terms of algorithms。

 that means that you need to go to like a。Deggree order and SOSDP。

 meaning it sort of takes exponential time for the algorithm to realize that the system is infeasible。

It's a very simple fact that's clearly in， but it's。Well， okay， so this is this is related to。

 you know， okay， this is related to the Napsack problem， but let me show you a different one。

Which is even more， which is also very simple， but。Okay so。Let's say I get you。嗯。Aique。看。

2 n minus1 vertices。So I have a click on。Od number of hertic。Okay。And then I ask。

 is there a perfect match？So what is this in terms of a polynomial system well okay what's a perfect matching I need to have okay I'm going to have variables XIj and XIj is one I mean the intended well the intent is XIj is one if Ij is in the matching。

Is in the matching， perfect matching and zero otherwise？Okay。

 so this is the intent so you can write down a system right what's the system every vertex should be in one edge。

So， some over I。A sum of J X J is equal to 1。Every vertex is in one edge and。

Let's say X J is equal to Xji if I is matched to J， J is also matched to I X J is equal to X J I。

And then what else do you want， you want。Right every ver is match to one thing。

 of course X J should be 0 or 1， so X J squared is X J。This forces xger to be0 or1。Okay。

 so we have these constraints and then finally the number of edges in the matching should be what。

En or something like every vertex should be matched， I guess。So it's n2 n minus1 over2。Actually。

 we don't even need that okay for all。ジア。Every vertex is matched。嗯。And every variable is。Yeah。

 look at this poly system， this is in feu because there's no poll there's no perfect matching on odd number of vertices because of parity。

 however you might one guy will be left out。Okay， but。This needs like order and degreeOSSDP。So嗯。

This needs。Proving that this system is infeasible， needs mega n degree。As well as proof。So。

So these are examples to show that although the proof system is very powerful。

 it can prove a lot of things， there are very basic。

 simple facts which are easy to see and obvious to write a proof of。

 but it takes degree order and to prove it using SOOS。啊。

And here's another fact which is visually very good I like this。

 but nobody has proved that it seen field like this's not I think there' is no degree low degree as proof so here's a fact okay I have a grid。

Yes。Do I have an end by end grid。Okay， and then there is a。This is S1， T1。

 there are four corners S2 T2。Okay， what I want is a path from S1 to T1。

I want you to find a path from S1 to T1 any path。And any parts from S2 to T2。

Such that they don't intersect anywhere。ok。So any parts from left bottom to top right and top top left whatever from what this corner to this corner and this corner is the other corner。

Okay and clearly anyway you draw， of course the intersect， right and it's obvious。

You can try to prove it actually proving it is a pain。

 I don't know how to prove it actually you can obviously see it， you don't need a proof。

 but you try to prove it， I don't know how to prove it。

But you can ask can a summer squares S Dp prove it or okay。

 is there a summer square proof of this fact， a low degree summer square proof of this fact？

I think proving this takes big end or something in the。

Variables that tell here the variables here are the edges every edge you can ask whether it belongs to the green path or the red path and these decision variables on these decision variables this system although it's infeasible proving that it's infeasible takes degree and I think or something very high degree so it has again a very simple visual fact in this case actually yeah proving it is very hard even without summer squares and with summer squares also I think it's very hard to prove。

嗯。Okay， I think we we can stop here and next class will。嗯。Continue on different topic。

I'm still debating what to teach a few different options but。是。



![](img/9a1f99e6050df919b42d16cc2272e8cd_7.png)

IP哎。Of the recording。

![](img/9a1f99e6050df919b42d16cc2272e8cd_9.png)

哦。