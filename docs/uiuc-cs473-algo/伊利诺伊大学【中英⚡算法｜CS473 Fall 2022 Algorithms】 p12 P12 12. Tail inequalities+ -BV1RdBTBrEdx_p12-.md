# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p12 P12 12. Tail inequalities+ -BV1RdBTBrEdx_p12-

![](img/aba68f304485d98ef9e64c32a57eb8aa_0.png)

等一。Okay， so let's go ahead and get started， sorry for the brief delay。U。

I don't think there are any logistics that I need to talk about。

The 120 exams have all been scanned into grade scopepe and the TAs and I are starting to grade them。

The plan is to get everything back into your hands by the end of next week。Which still leaves。

One week before the undergrad dropped deadline。嗯。And I'll keep if something looks like it's going to get delayed。

 I'll give you plenty of warning for that。U。Otherwise。

 I don't think there are any logistical things I need to say， but I'm happy to take questions。Yeah。

I'm sorry。So。I don't curve exam scores。What will happen is everything will get folded into the final grades。

If it looks like one of the problems might be have been significantly harder than we expected。

 we'll do something reasonable like drop one of the exam problems and weigh the others more heavily rather than。

😡，Trying to play games with statistics。We've also got as a backup， a curve for the whole class。

And so at the end of the semester， we'll compute your grades once using the fixed cutoffs。

Which are slightly more general than the curve has been in past semesters。And the curve。

And whichever of those。Gras。Whichever of those gives you the better grade， that's your grade。

 whichever gives him a better grade that's his grade。

 so it won't be it'll be a choice for every student。😡，So。U。One of the。

Downsides of having a global curve for the entire class。Is it creates。

The somewhat discouraging narrative that there there's only room for so many A's and so on。

 which is absolutely not true and in fact has never really been true。

But it switched to using fixed cutoffs a few years ago。Mostly because in 374， especially。

People are getting kind of， you know， simultaneously freaked out and discouraged。That there's only。

 you know， he's only going to give out 10 A's out of40 no。You get above this line。

 you get an A the question， if you get below this line， you might still get an A。

Because of other adjustments。Yeah。I'm sorry。can'tI'm having trouble hearing。嗯。

I wasn't planning to go through。The complete midterm in detail。

I was planning to try to save some time at the end of the lecture to talk about problem three in particular。

Okay。So。Randomized algorithms。So we。Seen a couple of examples。Which turn out to be。

more or less equivalent to each other， just different ways of viewing them， so we've seen quick sort。

Which you can think of either through the lens of。😡，When I partition。

 I'm going to choose a random pivot。Or you think of the recursion tree as a data structure and you analyze it and manipulate it like a data structure。

 then it's called troopss。😡，But。The the punchline from the。嗯。Quickword analysis is。

That the expected running time of cookssort is big over log in。Right。another， you know。

Another one is。Treop search runs in。Log and expected time。好。

So what I want to do is actually strengthen both of these。To。A technical term。

Called with high probability。And。This。Basically requires us to look a little bit more deeply into these random variables。

 the running time of this algorithm， and not just look at the mean of the distribution。

 but to look at，😡，The probability that the random variable lies close to the mean。

 so the intuition that you should have。😡，Is。Roughly this is probability and this is time。

The sort of profile of this。Random variable running time。Has some probability distribution that。

 oh okay， here's my expected time。That's what I get by。😡，Really。

 the expected time I should think of is the area under the curve。

 But if I think of like averaging it， where would that land on the time axis， that gives me。

This nice vertical line。And what I'm interested in bounding。I's the probability of being above。😡。

Some even bigger line that's maybe twice or three times the expected value。😡，So。I want to show。That。

This tail。Of the distribution。Is small。Okay， so if this were a normal distribution。

Now you a little Gaussian curve， then asymptically that tail looks like the function e to the minus x squared over two。

😡，So the tail is decaying super exponentially， and so the area beyond。

 you know a little bit away from the mean for a Gaussian is really， really tiny。

 the probability of a Gaussian variable being far away from its mean is really tiny。😡，Okay。

 none of the variables that we're going to talk about have a normal distribution。😡。

And so I don't want to rely on specialized arguments for binomial coefficients or or you know。

 normal curves rather。Everything is going to rely。On。Decomposing。

The random variable that I care about as a sum of indicator variables。

Where I know something about the probability of each of those indicator variables being zero or one and those probabilities may not all be the same。

😡，And then I want to bound something like， the probability that x is bigger than alpha times the expected value of x。

Is less than something。The strength of the conclusion that I get here。

 the how tight a bound I can prove。Depends on how these variables are related to each other。😡，Now。

 one of the nice things about expected values is that they're linear。

If I want to compute the expected value of x plus y， I compute the expected value of x。

 I compute the expected value of y and I add them。But that linearity doesn't extend to more complicated operations like the computing these tail inequalities。

 so I have to do a little bit of extra work to figure out。😡。

How independent different variables are before I can figure out what inequality I need to apply I can apply。

😡，嗯。But the more independent the variables are。😡，The stronger claim you can make about not being far above the mean。

咁。And in the end， if I know that these are all independent。

 I'm going to get something that looks exponential like a normal distribution。U。

So this is the name of the game。It've got some random variable。

 I know how to compute its expectation by summing up probabilities， I'd like to be able to bound。

To upper bound the probability that this random variable is a lot bigger than its expected value。

And then。So I'm going to take some time to develop some technology for stating improving these tail inequalities ultimately。

😡，The math I'm doing will be summarized。😡，On a formula sheet。

 which will be attached to the back of midterm two。Okay。

So you won't necessarily need to remember the derivations of these things。

But I think it's useful to see the derivations to maybe develop a little bit of intuition about where they come from。

And at the end， I'll come back。To treats in particular。

 but Quick sorts almost identical and prove this line at the top of the screen。All right。

So let's do some probability。Everything ultimately is going to be based on something called moreovs inequ。

So the way。Markovs inequality is stated。Is if Z is any。Non。Negative。Integer。Random variable。

Then the probability that this random variable exceeds some particular value， lowercase Z。

Is it most the expected value of that random variable divided by the value that you care about and normally we use the Greek letter mu。

As an abbreviation for mean。嗯。I think this is the only Greek letter that we will use。No， sorry。

 there'll be a Delta later。But mu means mean。UmIt's that you with a weird tail on it or kind of from a。

 if you squint， it kind of looks like a weird M。Which is not surprising because that's what it is。

Where weird just means Greek。嗯。So I'm going to draw。A function。

 it's a little bit different than one than the sort of intuitive picture that I drew up there。

 but it still carries similar information。I'm going to plot。

The probability that some random variable is greater than or equal to some value on the vertical axis versus the value on the horizontal axis。

And。This is。You know little Z is only an integer， so this is going to be a staircase looking function because it only has values over for integer Z so it'll it'll be something that looks。

Um， kind of like this。And maybe this actually goes and touches the horizontal axis because the random variable has you know a maximum value that can have。

But maybe it doesn't， maybe this is the plot of maybe C is the number of times I flip a coin until I get 10 heads in a row。

😡，the probability of that being more than a Google is still positive。😡，So in that case。

 this doesn't ever actually end， it just goes off to infinity， but again just as an example。

 let's suppose that it ends。Now。嗯。The area under this curve here。I can write as。

The sum over z of the probability that z is greater than or equal to z。

And what I'm doing is for each particular value of Z， I'm defining。😡。

A little rectangle that has width one in height。That probability。

And I'm just summing up the areas of all those rectangles。系。

But there's another way that I can write this。😡，嗯。which maybe looks a little bit more familiar in this case。

 what I'm going to do is divide the world up。Into horizontal rectangles where this is Z。Right。

And so the height of that rectangle。Is。The probability that my variable is larger than or equal to z minus the probability that it's larger than equal to z minus1 or z plus1。

😡，So the height of that horizontal rectangle is exactly the probability。😡。

Of taking on a particular value。😡，The total height is larger than that value。😡。

But that little horizontal strip。Is the probability that's equal to that value？喂。

And so here's the proof of。啊。Muckovs inequality。嗯。Sorry， there's a greater than here。

This expression in blue。Is the area of this rectangle？Okay， so the width is Z。

And the height is probability that。Bandomomerial is bigger than or equal to Z。

Now I could get this by manipulating these expressions。😡。

The simplest way to do that is to notice the terms in this summation on the left can only get smaller。

😡，So I could write this as。Some me change my notation slightly。

Zero of the probability that c is greater than equal to i。嗯。

So I cap the sum instead of going over all possible values。

 I only consider the first Z different values。I suppose I should be a little bit。Careful about this。

And that's bigger than the sum from i equals1 to z。The probability that Z is greater than capital Z。

 which is equal to this。I think there may be some off by one errors buried in here。

 so get rid of the。Less than or equals。嗯。Zeros minus one。I think。

Now I've gotten rid of all the off by ones。Yes。U。😡。

I'm just throwing summations around and looking at them in different ways。

But this inequality that you get is basically saying the area of this thing is the expected value of my random variable。

😡，And the area of that one rectangle is some value times the expectation of exceed that value。

Which is Marks inequality， okay？U。So what does this tell you about？Tailbones。Okay。幼玩。

So large z is some variable that you care about。Okay，Little Z。

Is your location on the horizontal axis I know what is that red thing？不见。They're like。

 why is the equal to Z Okay， so。Height。😡，Of this rectangle。

Is the probability that capital Z is equal to little Z。

This is the difference between the probability is greater than z minus1 and the probability that's greater than z。

😡，The only event that can happen in there because it's an integer random variable is that the value is actually equal to z。

哦，是三毛。还是方で。Yeah， what's the last thing on the right， the one just below the arrow of the x axis？Yeah。

That's the name of the axis。So clearly I need to work on my notation。

So it's the x axis and a particular value on it is called x。Only I use Z instead of X。我给你。

The probability of exceeding some value。😡，Is a decreasing function of that value？

This is not the problem I'm not plotting the probability that is equal to some value。😡。

So this is like a cumulative distribution， but cumulating backwards。

There's nothing special about integer here， you can replace the sums with integrals and prove it for continuous things。

 but non negative is important here。咁。Notice there are no other assumptions about the random variable。

😡，This is by far the most general thing you can have。

 so in particular if I'm looking at you know random variable。😡，That is。

 you the sum of a bunch of indicator variables， the probability that this is larger than alpha times its expected value。

Is at most one over alpha。系。😊，So this says， for example。😡。

I know the expected running time of Quicksort is about four times n log n， that's a natural log。😡。

So the probability that Quick Short actually runs in at least eight times n log n is the most to half。

It's really very， very weak。😡，Right， and the reason it's weak is because I've made no assumptions about where that variable came from and and that's actually crucial。

 If I cannot make any stronger assumptions， this is， in fact。

 the strongest statement that I can make。All， so I'm going to have to。

Dig a little bit deeper to do anything interesting so what's the probability that quick sort。Runs。

In greater than N cubed time。Is well。Something like n log n， sorry。

 this is less than n log n over n cubed。Its about you know one over n squared。

 that's the kind of inequality that we want。The probability of running too long is some decaying function of n but。

😡，And cubed is a terrible upper bound on the running time of quick sortt。😡，Because we actually know。

What that probability is already。What is the probability that when you run randomized Quick sort。

 it takes longer than NC time？Zero。The worst case running time of Quicksort is n squared。

So I've successfully proved that something impossible happens with。😡，Withft low probability。Great。

 so I need to make some stronger assumptions here， so I'm going to say that two variables x and y are independent。

😡，If an only if。The probability of one of them taking on a particular value and the other one taking on another particular value is the same as the product of those two probabilities。

😡，In other words， this is how you think probabilities behave。They usually don't。

But in this particular case， it's more or less what you think， if I roll a red dye and a blue dye。

 the probability of getting two sixes is the probability of getting a six on the red dye and a probability of getting it times the probability of getting a six on the blue dye because the two don't interact。

😡，Unless I tell you， in fact， that these are controlled so that the red blue dye always rolled the same numbers。

Right。So real life fair dice behave this way。😡，Not all repair pairs of random variables do。

Another way of saying exactly the same thing is if I tell you the value of one of the random variables。

That doesn't tell you anything at all about the value of the other one So if I say the blue dye rolled to five。

 you know nothing about what happened about the red dye。😡。

The conditional probabilities for the red dye are the same as the independent， whatever， nothing。

 no conditions， probabilities for the red dye。😡，Right。Um。

And one of the things also that this implies。😡，Is that if I multiply two random variables and take their average。

😡，That's the same as multiplying the average of those two variables。

So if I roll a red dye and a blue dye， the expected value of the product of those two numbers is 3。

5 times 3。5。😡，And you can confirm that for yourself by doing the brute force calculation of all 36 possibilities。

 but if you accept the definition of independence， you can also figure it out by using this identity。

系。This also implies that。For any functions of these things。These are also going to be independent。

So if I say one random variable is going to be the cube of the number I roll on the red dye。

 and the other random variable is going to be2 to the number I roll on the blue die。😡，The well。

I should tell you it's the same function， Okay， two to the red dive and two to the blue dye。

 Those are new random variables that they're non uniform distributions。

 but they're still going to be independent because they were derived from two independent variables。

All right。嗯。Similarly， if I have a bunch of。Random variables。

I'm going to say these are fully independent。If learning something about any subset of them tells you nothing about anything else。

😡，The probability of。All of them taking on the value that I want。😡，Is the same as the product。Yeah。

Of the individual probabilities。U。Sand， do you check？How do you pronounce that weird upside Mv？

4 loop。The probability that for all I。😡，The variable x sub I takes on the value littlexi。😡。

Is the same as。第一。Product again， for all。I from one to N。

 the product of the individual probabilities。😡，はい。And then finally， I'm going to say。The x1。

 x2 up through xN are。K wise， independent。If。Every subset。Of。Size K。Is fully independent。

In particular。Hair wise independent means X I and X J are independent for any I and J。

But it's not necessarily the case that x1， x2 and x3 are fully independent。Right。

So the simplest example of random variables that are。😡，Hrewise independent。

 but not fully independent。Imagine that I。嗯。Flip two fair coins。

Each fair coin has a zero on one side and one on the other。😡。

Then wem need to define three random variables。😡，Variable one is the result of flipping the coin on the left。

😡，Variable2 is the result of flipping the coin on the right。

 and variable 3 is the exclusive or of the first two variables。😡。

If I know the values of the first two， I' definitely know the value of the third， in fact。

 if I know the value of any two of them， I know the value of the third， so they're not independent。😡。

But nevertheless， any two of them， knowing the value of only one random variable doesn't give you any information about any other random variable that。

😡，Hi， so。It's just example。X1， x2 are independent。Fair coins。And x3 equals x1 exclusive or x2。

 then x1， x2， x3 or pairwise independent。But not。Fully independent。Okay。🎼U。Yeah。So。Knowing that my。

The variable that I'm interested in analyzing the running time of some algorithm。😡，Is a sum of。😡。

Pair wise， independent，0，1 variables。Pairwise， independent biased commons。Allows me to derive。😡。

Better。😡，Haail bounce so I can make stronger claims about how likely that sum is to。

Vary from its mean。All， so let me just set this up again， x is the sum。

From I equals 1 to n of some indicator random variable x sub I。

I'm going to write little piece of eye。This is the probability that the I random variable is equal to one。

This is also the expected value of the I randomom variable。And then the mean mu。

 this is the expected value of x， bi linearity， this is the sum from I equals 1 to n of little P of I。

This description of the expected value of a sum of indicator variables is a sum of probabilities we've done a couple of times now。

 so hopefully that makes some sense。I'm just establishing this because I don't want to write all his brackets everywhere。

 it gets tiring。😡，嗯。Chy chefs inequality。Oh。Who discovered Markov's inequality？Chhevy sheves。Correct。

Who discovered Shevy Shev's inequality？Beyond me， correct。嗯啊。Markov was Chey Shebb's PhD advisor。

So Shabi Sheev named it Markov's inequality。Academic politics in early 20th century。

 Russia were interesting。嗯。So。Seepyet this inequality says that if these variables are。😡。

Pair was independent。Then the probability。That this quantity。

Is greater than or equal to some value little z。Is it most mu over Z？Now this is this weird thing。

 right？noteNot really interested in the behavior of the variable itself。😡，But rather。

 how far the variable is from its mean。😡，So essentially what I'm doing is I'm centering the variable by subtracting off its mean。

 so this expression x minus mu is a random variable that has mean zero。😡。

But I don't really care about the difference between being above the mean or below the mean。

By a certain distance， so to normalize that， I'm going to square it。

 the side benefit of squaring it is this random variable now that I'm analyzing here。

X minus minus squared。Is non negative。Which means？I can use Markovs inequality。And in fact。

 that's basically the whole proof。All right so here's here's here's my proof i'll write it down step by step this is the the last time you're going to see this Okay。

 so i'm going to write little wise i'm going to write y sub I to be the sort of normalized。X to buy。

And then capital y is the sum of these y subs， which is going to turn out to be x minus mu。

So y subbi is a random variable that is either。😡，Minus P sub I。Or one minus p sub I。

It's no longer an integer random variable， but that's okay。

And then bi linearity summing up all the y subise is the same as summing up all the x subs that gives me x。

 subtracting off the sum of all the p sub that gives me mu。😡。

And so the thing that we're interested in analyzing。Is this the square of this variable Y？😡。

This is what's called the second moment of the variable x around its mean。😡。

This is by analogy to physics where you talk about moment of inertia。Which。

 you know I move if my arm is close to my body， I move it up and down。

 there's less inertia than my arm is far away from my body moving up and down。Again， this is about。

Difference from the center of mass。And you square it for technical reasons。So。😊。

If you remember anything about physics。嗯。诶。Moment is actually intuitive if you don't。

 maybe now you've learned something about physics。All right。

 so let's figure out what this expected value is。😡，I'm just going to expand。

So this is the sum over all I and J of y sub i times y sub j。That's。It's a。

Some of the y sub times the sum of the y subs， so I fold it all together into one double sumation。

Oh wait， expectation is linear。So I can put the summation inside。Now。

If I want to compute the expected value of this product。

 there are actually two cases that I need to worry about。😡，嗯。One is where I and J are equal。😡。

A random variable cannot be independent from itself。😡，Okay， so I need to write this as。

Some over I expected value of y sub I squared。Plus， the expected value as I is not equal to J。

They why sub？😔，Okay。U。Now， over on this side。I'll leave this alone for now。But。This expression。

I happen to know when I and J are different that Yi and Yj are。😡。

Independent because they were derived from other independent random variables， Xi and Xj。And well。

I have this thing that I can do with independent random variables。Which is to split them。Okay。

What's the expected value of y sub？Yeah。Zero。The expected value of x sub I is p sub I。😡。

So by linearity， the expected value of y sub I is p sub I minus p sub I。😡，So this is。0ero。

 and this is zero。 So I really only care about this weird sum of。Expected values of squares。

Which I can just sort of write out this point。This with probability P divide。

 the variable is going to have value one minus p sub。So the square is going to have that。嗯。Squared。

 I think I should。对。对。And。Well， not a lot， this isn at most new。So at this point， there's some math。

 I'm going to leave it out。Basically the idea is I took this sum of pairwise products of random variables。

 took the parts that couldn't be independent out。😡。

The parts that could be independent all just vanish because of independence。😡。

And then the rest of it sums up to something less than mu。Um。So this means by。Marov。the啊。

Probability that y squared is bigger than z。Is at most the expected value of y squared divided by？

Dide by Z， which is at most mu over Z the end。咁。Now。

 if I really were a probabilist or statistician or someone who does machine learning， at this point。

 I would probably trot out something called variance。

Usually if you've seen chubby chef's inequality before。

 it's probably usually explained to you in terms of variance。😡，I will be completely honest with you。

 on the one hand， I don't remember the definition of variance and on the other hand I've never needed to。

😡，So I'm just going to stick with this formulation here。Okay。So。What does this say about？

The probability of X。Being significantly larger than its mean， I'm going to。

Introduce instead of just writing alpha times the mean。

 I'm going to put a little1 plus delta here because it simplifies the final result。嗯。

A little bit of grinding。Gs you the expression。1 over delta squared mu is an upper bound on the probability。

Okay， so let's think about now what this means。😡，X is the running time of Quick sortt。On average。

 QuickSot runs in4 N log N time。So this mu over here is for n log n。😡。

What's the probability that QuickSot actually runs in five N log end time or more？😡，In this case。

 mu is our deelta here is one over four。😡，So I get some constant， Dlta is a constant。😡。

But now in the denominator of this fraction， I see the mean。😡。

So I get basically some constant over N log N。😡，So if I could write the running time of Quicksort as the sum of a bunch of pairwise indicator variables。

😡，This immediately implies that going over the mean by any constant factor has probability at most one over n。

😡，A most constant over it。鸡。I'm not happy with this this derivation for two reasons， one。

 I really want a probability that decays more than just one over end I'd like it to be like。😡。

Tutable so that I could adjust it to if I'm this far。

 I'd be one over n squared if I'm that far be one N cubed。😡。

And I can't get that from Chebbvyev's inequality。And the second problem is。Unfortunately。

 those events are not actually parawise independent。It's a little bit more subtle than that。Um。

 but u often。For other things。This is good enough。To give you a tail inality that's useful。

There's a similar bound going the other way。Not too surprisingly。

Now I'm interested in how if it goes below the mean by some factor delta again。

 I get exactly the same expression on the on the the。On the right。Again。

The statement of Chevy chefev's inequality and these two consequences of it will show up on the formula sheet in the back of midterm two and back of the final。

Rightright。嗯。Now I can push this idea even further。😡，Instead of looking at。The second moment。

 the square of the deviation from the mean。And analyzing that under the assumption that my underlying variables are pairwise independent。

If I happen to know that my underlying variables are fourwise independent。

 then I can analyze the fourth moment。😡，And then what will happen is。

You'll end up with an inequality that allows you to square this probability over here on the right。😡。

The more independent you know your variables are the。😡，Higher degree polynomial in one over mu。

 you can prove over here on the right side of this inequality。😡，The more independent you have。

 the faster the tail on the probability of distribution is shrinking。😡，So。Intuitively。

Um what seems to be happening is the board In you have， the faster things decay。

 what happens if everything is completely independent？😡。

So no matter what you do with limited independence。

 you're always going to get a polynomial in one over mu over here， in fact。

 always a polynomial and one over Dlta squared mu。😡，So when things are fully independent。

You actually get an exponential function。😡，De cases exponentially with deelta squared mu instead of only inverse polynomial。

Yeah。😊，That's right n doesn't show up anywhere really what happens is n is buried in the expected value mu。

😡，So this analysis， in fact， works even if the random variable we're looking at is the sum of an infinite number。

😡，Of indicator variables， there is no N here。😡，Really。We take entro this one that。讲识你你贵。Yeah。

 but if n is just one， then you actually know the precise distribution。

There's no reason to have a the only reason to have a tail inequality is when you have a wide range of values that your variable can have。

 but if n equals one。Your variable is either zero or one。All right。So if we really want to。

Prove some sort of exponential thing。Instead of looking at。Higher and higher。Polynomial moments。

Second moment， fourth moment， sixth moment。I always want it to be。When I'm thinking about pulp。

 the bounded independence。Even independence makes sense because then I get a nice even degree polynomial inside that probability。

 which means。😡，I can apply Markov's inequality because the expression I get is not negative if I try to exploit third moments or fifth moments。

I can't use Markovs inequality anymore。嗯。So。So the exponential moment in equality says。

If I happen to know that my variable is a sum of completely independent random bits。😡。

Everybody in the room flips the coin， their own coin， we sum up the values， how many heads there are。

 that's completely independent。Then the expected value of。Alpha to the X。

Where alpha is any number bigger than one。Um， iss it most？😡。

This weird expression where the mean shows up in the exponent。

Now at some level this is kind of what a beginner would expect if I have a random variable whose mean is mu。

 then the expected value of two to that variable should be two to the mu if you just treat random variables like their expectations。

This is kind of the result that you would expect。😡。

It's not exactly because the base of the exponent changed from alpha to e to the alpha minus1。

And it's not quite what you expect because there's this technical assumption that everything is completely independent。

😡，系。Now。嗯。In the interest of time。I'm not going to walk through the proof of this。😡，ItIt is。

Roughly as long。😡，And roughly as interesting as the proof of Chevyev's inequality。嗯。

At some point you use full independence to take a product of things。

 the expected value of a product and turn it into a product of expected values。😡，啊。

But then the sort of。Falls out。嗯。One consequence of this is that I can write the problem。

E to that value minus mu。Times mu over x to the x。Proof。Set alpha equal to。嗯。X over mu。

So this is another form of the exponential moment in equality。OrI chose the base of the exponent。

To get the tightest possible upper bound。Yes。I did some calculus， took some derivatives。

 set them to zero。嗯。And then。Further manipulation， you get things like。TheFollowing。This is at most。

E to the delta over1 plus delta to the 1 plus delta。

To the mu or under reasonable conditions e to the minus delta squared mu over three。Again。

 there's a bunch of maths that I'm not showing you。😡。

But the important thing here is the probability that x is a little bit above。It's mean。Is。

Decas exponentially as that little bit grows。😡，And the mean of the random variable shows up in that expo。

😡，Okay， so again， if I imagine that x is the running time of randomized Quick sort。😡。

This says the probability that I'm say， off the expected value by a factor of two here delta is equal to1。

😡，Would decay exponentially the e to the minus n log n。😡，Re fast drop off。好。

Which is the kind of thing that we would want。嗯。So let me actually try to show you very quickly。😡。

I would do apply this inequality when I'm analyzing troopss yeah。我的病。Yeah。Yeah。

These are mean so we're always in the scenario where XI means an indicator variable， zero or1。Okay。

All right， so if you remember the analysis of troops。

The the expected value of the depth of the particular node。Is the sum overall I？

Of the probability that node I is an ancestor of node K。so here， capital x is the depth。

nodeode K and capital x sub I is this indicator variable I uparrow OK。关。嗯。

So one claim here is some of these now these various indicator variables that I'm summing up。

 they're not fully independent， they're not even parawise independent。

 but it turns out I can split them into two fully independent subsets。

 so the claim is that one uparrow okay。😡，To up arrow okay。Up through K minus1 up there， okay。A。

Fully independent。And that means that I can apply。嗯。The exponential moment inequality。To。

The sum of those probabilities just to the stuff that's smaller than K。嗯。And again。

 in the interest of time， because I do want to talk about problem three on the homework。U。

What this ends up。Implying。Is。That。Remember， the depth of any node。

 the expected value is something a little bit less than two times log n。😡。

So if I say what's the probability that the depth of any particular node is more than four times that more than eight n log n I get a polynomial。

 an inverse polynomial where the degree in the denominator is a little bit over two number between two and three if I change that eight to a nine。

😡，That the degree of that polynomial goes up to n cubed。😡，If I change that nine to a 10。

 it goes up to about four。So， the more slack I give。

 the less and less likely it is that the node will be that deep in the tro。😡。

So then the probability that。The maximum depth。Is greater than eight log n。Well。

 the only way that the maximum depth can be that big is if one of the individual things is that deep。

 so this is at most the sum from I equals one to K of the probability of。😡，That particular sorry。

 that should not be。K equals  one to n， the probability of that particular node is too deep。

Whi is now at most two to the n over 1。5 ish。And again， if I change that eight to a nine。

TheThis exponent here changes from about one and a half to about two and a half and so on。

The more slack I allow my。Upper bound to have。The lower the probability that I exceed that upper bound gets。

对。嗯。And so this actually now finally implies。The stronger statement that I wanted。

The expected value of the maximum depth of the tree is only lo in。So if I build a tro。😡。

Not only is it the case that the average cost of any particular search is big of log n with a relatively small constant。

😡，The probability that is significantly larger than that， decays。

Exponentialally as a function of how much larger you're willing to tolerate。

So the probability that your it is possible that your trip is 100 times deeper than you would expect it to be。

😡，But the probability that happening is somewhat smaller than the probability that your laptop just explodes。

😡，So。Morally， it just doesn't happen。Right。It is probably in all the implementations of treats that have ever been done。

 and there have been millions of them over decades。😡，Let's imagine that in fact。

 every person on earth has implemented and run troopss a million times a year since the beginning of the universe。

None of them has ever been more than a thousand times deeper than they were expected to be。Okay。So。

That also means that Quick sorts never。Then more than a times run a thousand times longer than its expected value。

U。So this last bit going through the exponential moment in equality and the application to troops and stuff。

I apologize to this went very fast。Everything is worked out in more careful detail in the notes and if we need to do this again。

We need to apply this again， I'll try to go through it again more slowly。

But I did want to save some time at the end of the lecture to talk about problem 3 in the midterm。

Before we get to that。Are there any questions about。These tail inequality things。

The moral here is the more independent you can show the tighter you can bound how that tail shrinks。

😡，Okay。Problem three。So。Just to remind you quickly what the problem was。😡，I'm given。嗯。

Two bit strings。And I'm interested in finding。The best way to line up these one bit string against the other。

😡，The way I measure how good。The alignment is， is I count how many bits are different。

So here these two are different， so this particular alignment。

 the hamming distance between the pattern and the corresponding substr of the text。😡，Is two。

Because exactly two corresponding bits differ。And the goal is to find。😡，The minimum over all shifts。

😡，Of this haming distance。Okay。😊，So。嗯。For any shift value。S。

I'm going to define the heming distance for that shift。To be the sum over all indices from1 to M。Of。

嗯。I want to compare the ice。Bit in the pattern。To the I plus S bit in the text。😡。

I want to add one if those two bits are different， and I want to add zero if those two bits are the same。

So I'm going just there's my definition。Okay。U。Now。

There's a bunch of different ways to proceed from here。

 the one that I found the most intuitive to think about is to consider two ways that that expression brackets。

😡，嗯。Would be。Derived one of them is P of I is 1 and t of I plus S is zero and the other is the other way around okay。

So I'm going to write this as。I equals 1 to M of p of I times 1 minus T of i plus S。Plus。

 some from i equals1 to M of 1 minus p of I。Times T of I plus S。So far are you with me？Right。

 I'm just。Writing stuff down， establishing some not。Now。

If I look at this stuff that I've written up here in red。

 I've got a long string here and I've got a short string here and I'm sliding this back and forth。

Making this hand motion with one set of teeth rubbing against the other。

 this is the universal sign for Fast Fourier transform。

So I need to turn this somehow into a convolution。So remember the way convolutions work。Is if I have。

Some sequence a0， A1 up through AM and some other sequence B0 B1 up through B。

 and then their convolution， a star B。C0 up to C N plus M is defined by setting。

CJ equal to the sum overall I of Ai times bj minus I。That's the definition of the convolution。

Think of the A's as coefficients of some polynomial and B's as coefficients of some other polynomial。

 then the sequence C is the sequence of coefficients of the product of those two polynomials。

To get the J coefficient， I consider。All I and J minus I coefficients from the two polynomials multiply those coefficients together and add up the results。

Now， that summation in the definition of convolution。

Kind of looks like the summations that I have up above。

 so let me concentrate over here on the sum on the left and I'll just call this a sub I。😡。

And I'll call this B sub i plus S。The difference between the two is in a convolution。

There's a subtraction here in the indices， as I look at later and later a subs。

 I need to look at earlier and earlier B subjects。😡，The summation I have up here in green。

As I increase I， the place I'm looking in the pattern and the place I'm looking at the text are both going up in the same direction。

😡，So in order to massage。The green thing to look like the blue thing。I'm actually going to define。

A sub I to be P sub M minus I。And bes of I to be。One minus。啊，我 call it。Okay。So if I write that。

 so I'm going to take the pattern and I'm going to reverse it。That'll turn that plus into a minus。😡。

So I equals1 to M of P times1 minus T of I plus S Now this will become some overall I of a sub m minus I times。

Be of。S plus I。Now when I'm walking through the indices。As I increase I。

 the index of a is going down and the index of B is going up。😡。

You're going past each other like this， so he's exactly the form that you want for convolution。

So this。The the this is the coefficient of the convolution of A and B and which coefficient it is is the sum of。

😡，The indices， which in this case is S plus M。So。😡，I can set up。😡，These sequences in order end time。

So by writing them into two new eras A and B。I can compute the convolution of A and B。

In analoglog N time using FFTs。And then I can look up for any particular value of S。

 I just look and position S plus M in this convolution。😡，And that gives me the term on the left。

And there's a similar computation using the convolution of some slightly different things that gives you the sum on the right for all values of us。

And then at that point， all that's left to do is for each S， look at those two values。

 compare their sum to a running min。😡，And then return the smallest of those sums that you found。

So the setup takes order end time。😡，Then I need to do convolution and another convolution。

Then from then on， everything else takes order end time。As I said， this is not the only way to do it。

😡，Another way that I saw at least a couple of times。Already was to look at the squares。

Of the differences。This requires only one convolution instead of two。

 but then it requires a little bit of extra work to pull some other terms out。Right。So。This。Was。

What I had hoped that people would see。IHope spring eternal。I'm happy to answer questions。

 but we've got about one minute before class is over。Did it make sense？Okay， good， not that crazy。

All right， thanks everybody， have a good weekend and we'll see you back here on Tuesday。嗯。可以。



![](img/aba68f304485d98ef9e64c32a57eb8aa_2.png)

道。