# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p10 -10-Lecture 10_ The Minimax Theorem & Algorithms for Linear Programming).zh_en -BV14CAUeUEPj_p10-

All right so today we're going to do two topics I want to give you an application of strong linear programming duality which we covered on Tuesday I'm going to show you how a famous result in game theory called the Minax theorem follows from strong linearar programming duality。

 Minax theorem in addition to being basic in game theory also has applications in computer science I may have a chance to tell you about those later。

Second topic is to actually survey some of the algorithms that are really used for solving linear programming and the discussion of their efficiency。

All right， so first。Zero sum games。 So for example， you guys all know rock paper scissors。

 right a Rochebo。So okay， we're going to play a couple rounds。Ohre we're going four， right？4our。

 okay， sorry。No， no sorry， it's four， I'll get to write this down， all right ready？All right。

He gave me two to three， so I have a proposal for you。

 let's now play it where you go first and then I go second。So pick one。😀Yeah。嗯。All right。I won。

So how about that's I agree。 That's very unfair。 So what if I only made you commit to a probability distribution over your strategies over rock paper and scissors。

 So you just said， I'm going to randomize in the following way。 Okay。

 then I have to choose a response。 and then nature flips some coins for you。Now， actually。

 right in rock paper scissors， it's not so bad if you have to commit upfront to just a way of mixing。

Because if you just commit upfront to choosing a strategy uniformly at random。

 each one equally likely， then no matter what I do， the probability that you win。

 lose or tire equal all equal to a third。So in rock paper， scs， if you're allowed to randomize。

 you can go first， and it's not a big deal。 You can still protect yourself。 The in max theorem。

Says that in any so called zero sum game。Similarly。

 a player can go first and protect themselves by randomizing in an appropriate way？

So what is a zero sum game？So it's specified by matrix， M by N matrix。And say have two players。

 one chooses a row and the other chooses a column， so they're naturally called the row and column players。

So one player chooses a row。The other chooses a column。

And so what are the semantics of the matrix entries？

So the matrix entries could be positive or negative， and we interpret AIJ as the payoff。

Earned by the row player。If the row player chooses row I and the column player plays column J。Okay。

So payoff of the row player。In the outcome， I comm a J。And why is it called zero sum。

 it's because we also define this to be the negative。Pay off。Of the other player。So in other words。

 you should think of AIJ as the amount of money that the column player has to pay to the row player。

Now AIJ might be negative， in which case the payment goes in the reverse direction。So for example。

Rock paper scissors。How would you encode this？As such a matrix。Well。

 the diagonal is where the two players choose the same action， so that's a draw。

So that's going to be zero。I think nobody wins nobody loses。Now here， paper beats rock， right？

So in this entry， it's the row player that wins， okay？So we put a one there。

 so if the row player chooses paper and the column player chooses rock。

 then the column player should pay a dollar to the row player。Down here it's the opposite。

 right so the row player plays scissors， then it's a loss to a column player playing rocks。

 so in that case the row player pays a dollar to the column player。And similarly。Okay。

So any questions about the basic formalism？So the difference is just that in a general zero sum。

 you're can to have any number of rows M， any number of columns n。

 and the entries can be whatever you want。So。I mentioned the idea of。Choosing a strategy at random。

So suppose x and Y。Our probability distributions。Over the rows and columns respectively。

 Okay so think of x and Y， the probability distributions， but think of them as vectors。

 X indexed by the rows， Y indexed by the columns。 What does it mean that they probability distributions。

So the semantics R is just each entry of x is the probability with which the row player will choose that particular row。

 so probability should be non negative。And they should sum to one。Okay。So consider for now。

 just sticks a way in which the row player randomizes all over the rows and the column player randomizes over the columns。

 so they randomize independently。Notice。Again， this is all sort of building up to the statement of the Minm Max theorem。

So the expected payoff。Of the row player， okay so whenever you see expected。

 youll always just do a sanity check and say， oh， what's the expectation over， what's the randomness。

 The expectation is over which row gets chosen and which column gets chosen from the distributions X and Y respectively。

So what's the average payoff of a row player when the players choose strategies according to these distributions？

Well， by the definition of expectation。You just look at everything that might transpire。Okay。

 so the probability that we wind up in the outcome I comm a J， the row player picks I。

 the comp player picks J。Times。The payoff that the row player receives in that particular case。

 when that's the outcome。 And then we just sum over all the things that could happen。嗯。

So that's the definition of expectation。Now， the row player and the column player。

 they're picking strategies independently。Okay。Which means that the probability that the I row and the Jth column both get selected。

Is just the product。Okay， so this is by independence of the random coins of the row and the column player。

In our vector notation， this is Xi。And this is Yj。Okay。

And so if we really want to be succinct writing this in matrix vector notation。

So some over I IIj times X Yj， so the x x belongs to the rows， it's multiplying the rows。

So we should have an x transpose to the left of the matrix A。

 Y is the one that corresponds to the columns， multiplying the columns。

 so we have a y on the right hand side。So again here， x is going to be an M vector。

 A and M by N matrix and y and n vector， distribution of the row， distribution of the columns。

So this is how the row player evaluates。How well he or she is doing？

When the row player randomizes according to x， comp player randomizes according to y。

This is the payoff of the row player， x transpose a y and expectation。

So now let's go back to this issue about whether you play simultaneously or whether you have to go first or whether you get to go second。

So question。Is it better to go first？Or second。And I mean， intuitively， in a zero sum game。

 it can't help to go first， there's only a first mover disadvantage。

 why because the second player gets to adapt to what the first player shows and you saw this when I forced you to pick a strategy up front so I was able to respond and win the game every time。

And so but there's this question about， well what if you only commit to a randomized strategy。

 so maybe we make the row player go first， commit to an X and then the column player gets to respond with a Y or maybe device vice versa。

So then what， okay， it still can never help， you can never be better off going first than going second。

Why， well， consider what you would have done if you had to go first。

You're still perfectly free you to do that if you go second。 Okay。

 you can choose to not adapt if you go second， if you don't want to， Okay。

 so you have only more options if you go second， So you're all going to be better off。

But the Minm theorem。Is the sort of stunning statement。That it actually doesn't matter。

It doesnn't matter if you go first or second。 Okay， what do I mean by that exactly？

Here's what I mean。So remember， this is just the expected payoff to the row player when the row mixes according to x。

 sorry these are sometimes called mix strategies， so when I say mix I just mean randomized。

Row is chosen according to Xcom， chosen according to Y。

 this is the expected payoff of the row player。So what does it mean for the row player to go first。

 i。e。 for the column player to go second？Well， naturally we're going to assume that the column player it's a zero sum game。

 so whatever the column player wins， we lose， so we assume the column player is going to do the optimal thing given whatever we chose in the first round。

And so remember it。The semantics of these entries are the row player prefers bigger numbers。

 the column player prefers smaller numbers。So when the column player goes second。

And knows the row player's choice of a strategy， choice of x。

It's going to pick the best response as it's called， it's going to pick the Y。

 which minimizes the row player's payoff， I maximizes the column players payoff。

 given that the row player chose X。So this is for a fixed X。

What we expect to happen when the column player responds？Now， from the role player's perspective。

 if you have to go first。You， of course， are expecting the column player to respond in this way。Well。

 you want to make your payoff as high as possible。So you will play your best strategy。

 the strategy that maximizes your expected payoff， assuming an optimal I。

e worst case response by the column player。 Okay so mathematically。

 this is what it means to say that the real player goes first and the column player goes second。

If you reverse their roles， you just reverse them min and the max。Okay。

So if the column player is forced to go first， they will choose whatever probability distribution gives them the optimal payoff and again。

 remember the column player wants to minimize。Under worst case play by the opponent。

 which would be a maximization。Yeah。Of a transpose， A。Okay。

So that's the formal statement of the Minmax theorem。Here A here is any matrix you want。

 it doesn't matter。And X and Y arranging overall possible probability distributions over the rows and columns respectively。

So currently， we are choosing the target redistriion instead of the fixed strategyasur， right？

Like after we choose the distribution then everything happens and we don't， I mean。

 we can't actually control show。So nature flips coins is what happens。So first。

 the first player will choose the distribution。 Right。

 The second player should distribute distribution。 That's right。 And then the first player like。

I mean， something happened。Think of it this way， think of it like each player writes a computer program。

 which flips random coins inside。Okay， and so the row player first has to submit their code。

 the column player gets to inspect the code and then submit some code。

 and then I'm just going to run their two randomized algorithms and see what happens。Makes sense。

Okay。All right， so that's the formal statement of Min Max theorem。 Okay， So we argued that， you know。

 going first can only hurt you。 So we'd certainly expect this to be at most this。But in fact。

 they're equal。And spoiler alert， this just follows from strong linear programming duality？

Three questions before I。Explain why。Is the statement clear？All right。

I actually I guess a little backstory so this was first proved by von Neuman in the 1920s， so Brell。

 one of the cofounders of modern probability theory， thought he had disproved the Minax theorem。

 but then von Neuman realized it's actually true， Von Neuuman proved it using arguments kind of related to fixed point theorems if you know what those are。

Then actually in the 40s to 20 years later， Von Neumman proved it again。

By using arguments that are basically equivalent to linear programming duality。

 they are arguments I'm about to show you and so that's why when George Danzig we'll say more about later。

 but he's the inventor of linear programming and the simplex method so when he went and met von Neuman and von Neumman at this point was really a big shot Danzig was quite young so he was quite nervous and so he nervously told Vanon Neumman about this crazy linear programming thing he'd just come up with and von Neumman Insens was like oh and he just kind of wrote duality theory on the board in front of Danig。

Because he'd basically been thinking about it in the context of these different types of proofs for them in Max thereem。

Okay。So。Here's how we're going to start。We're going to adopt the role of the row player。

When they have to go first。We're going to consider just the computational problem。

 Suppose I actually wanted to figure out what to do。

 Suppose I wanted to actually figure out what is my best strategy。

If the other player is going to respond in the optimal way， so for rock paper scissors。

 it's not that hard to convince yourself that the best thing to do is to randomize uniformly。

 that guarantees you expect to pay off zero。But what about in a general game？

So we're going to show you is that we can actually encode this as a linear program。

So computing the left hand side can be formulated as a linear program。Now， initially。

 you should sayhuh。It shouldn't necessarily be very obvious。 I mean， there's the nested Max and min。

 which you don't have in linear program。 so that makes you nervous also if you remember。You know。

 what is this expression， this expression is multiplying x's and y's together and we're sort of thinking of both the x's and y's as being decision variables。

 so it has a nonlinear kind of quadratic flavor if you just stare at these expressions。Nevertheless。

 using the tricks I've already showed you， you can formulate this as a linear program。So to see that。

 here's a preliminary observation。Which is that actually， if you get to go second。

Life's pretty straightforward。You actually don't have to randomize So suppose the row player went。

 Okay so I know the distribution with which the row player is randomizing over their choices。

I can just say， okay， if I choose column 1。What's my expected payoff？If I choose column 2。

 what's my expected payoff And the expectation here is over the random choice of a row by the row player。

So I can do this thought experiment for each of my columns， each of my strategies。

I can just look at which column gives me the best expected payoff。

 and I may as well just play that deterministically。So in rock paper scissors。

 if you do something where you skew toward one strategy at all。

 okay so if you're strictly more than a third say on rock。

 then I'll just deterministically respond paper。So if you're going one third， one， third， one third。

 well， if I want， I can just always play rock。OkayI'll win a third of the time。

 lose a third and tie a third okay I could also if you're randomizing uniformly。

 I could randomize uniformly that's just as good， but without loss as the second player I may as well just pick a best action。

 breaking ties arbitrarily and play it。Okay。Co。All right。So that's the first simplification。

 then actually for the second player we don't have to think about optimizing over all of these mixed strategies。

 all of these distributions， we just have to think about optimizing over the finite set of possible strategies。

So no need。For a second player to randomize。So that means。We can rewrite this thing。

Let me unpack it again in the summation notation。Yeahcha。

So we've just said that the second player rather than minimizing over all distributions。

 y can just minimize over all of the columns， all of the columns J。

So what would it mean in this notation for the column player to just always choose column one？

It would mean that y1 is equal to 1 and the other entries of y are 0。Okay。Similarly。

 if it always played column 2， y2 would be equal to 1 and all the rest would be  zero。Okay。

So when the column player just chooses some column deterministically。This expression simplifies。Yeah。

Okay， so now I'm just going to look over all possible strategies， all possible columns。

Now I'm going to sum only over the rows。And I'm going to get AIJ。X， I。Okay。So for a fixed J。

 I've just plugged in the vector y， which is one in the Jth coordinate and0 everywhere else。

 again that corresponds to just always playing column J。

So this is what the column player will get or the column player will get the opposite of this if it always plays J。

 given that the row player is playing X， what's the column player going to do is's going to pick the best choice of J over all of the options。

So I claim these are exactly the same number， I follow that。Okay。All right。

 so what progress have we made， the big progress that we've made is we took a term which used to look like sort of a quadratic term。

And we've replaced it with something which looks like a linear term。 Remember。

 AI Js are just constants。 And so now this is a linear function of x。

There's still the other problem we mentioned， which is you have this weird nested min and max。

 and a linear programming objective only handles one of those。But also three lectures ago。

 I showed you some tricks for replacing things like absolute values and maxes and mins by using extra variables and extra constraints。

 and exactly the same idea works here。So here's how you can formulate solving this problem as a linear program。

So we're going to maximize something。Evidently。Intuitively， we want to maximize this， okay？

But this is a min。And so the way we're going to encode them min is by having an extra variable。

 extra decision variable， which I'll call V， and V is forced to be at most each of these terms。

 and since its every one of these terms， it's also at most the minimum of these terms。

So V is going to be our extra decision variable， which is meant to be a proxy for this number in parentheses。

What are the constraints， Well， there's some obvious constraints， which is that x。

 we still have the x variables。They should be。Probability distribution。An X is not negative。

Our new decision variable V is unrestricted。Because again。

 the numbers in these matrices could be positive or negative。

And so now we want constraints which say that indeed that really enforce the property that V is going to take on the value of this minimum。

So how do we do that， well we just say V should be at most this number for every J。Okay。And again。

 this is something the first time you saw something like this was when we were dealing with absolute values。

 when we were fitting a line， we did a similar trick。

 and then we also did a similar trick when we talked about hinge loss at the very end of lecture number two okay。

Now the way this is written right now， remember vs are decisionciion variable and so are the x's。

 Okay， normally in the standard forms， you have all the decision variables on the left and then you just have a constant on the right。

 So let me just rewrite this。So i。e。V minus。This stuff。Is at mode zero。Okay。So that's the proposed。

Lining a program。Why does it work？Oh yeah， other announcements， exercise five， I'll post that soon。

 it might not be till Saturday， but no later than that。

 and problem that number two recall is due on Tuesday。Okay。So here's the claim。So consider。

 suppose you okay， so observation one， this is a linear program， whatever it's doing。

 it's a linear program so we can solve it。Decision variables are V and the Xs。

 all the constraints are linear， objective is linear。

So if we solve it and we get not the most solution。V star， X star。The claim is that V star。

Really will be equal to。This minimum。Okay。Why。Well， certainly V star can't be any bigger than this。

 that's just by feasibility。So these constraints explicitly say V has to be at almost as big as each of these。

 so it's almost as big as the minimum。Suppose V was strictly smaller than this number。Well。

 then you wouldn't be optimal because you could just leave x fixed and you could increase V slightly。

 And if this is a strict inequality， you can increase V slightly and get a。

 bigger objective function value。So feasibility says you can't be bigger than this。

 optimality says you can't be smaller than this。And so what this means。Is， in fact， that。

Since we're also optimizing over all choices of the x's。V star really is max X。ComEn of this stuff。

Which， as we've discussed earlier。Is the same as MaxX。Minwai。X transpose AY。Okay。An x star。

The probability distribution computed will be in the AGm。

 it will achieve this number v star just by the encoding of the linear program。Okay。

So any questions about that。 So again， what have we proved。

 we've proved that we can write down a linear program whose optimal value is exactly equal to the number on the left hand side。

Okay。So how do you do it， you optimize on behalf of the row player。

 envisioning each of the possible columns that the column player might play in response。

You can encode worst case behavior for the column player as a family of linear inequalities。

 one per column， and then you just do your best with respect to those constraints。

So any questions about that？All right。So naturally。

 we can also write down a linear program for the right hand side。 Okay。

 we can do exactly the same exercise。😊，And so what do you get， you get something analogous to this。

So now we're optimizing on behalf of the column player， so we're going to be minimizing W。

So now W is encoding a maximum， not a minimum。So the inequalities are going to go the other direction。

 okay？It's going to be MinW。Subject to。W minus。The appropriate。When you're in combination。

So it's going to be non negative。For all rows。Okay。So this again。

 is the column player doing the thought experiment about each of the possible devious things that the row player might do in response to why。

And again。Should be a probability distribution。So Yj is not negative。W unrestricted。Okay。

And's by the same reasoning。The optimal value of this linear program is going to be exactly。Min w。

Maxex。X transpose AY。Any questions about that？Again。

 you derive this doing exactly the same exercise we did on the row players behalf。All right。

 so the punchline。She already sort of gave away。We have two linear programs， that one。And that one。

These are dual linear programs。You take the dual of that， you get that and vice versa。These are dues。

Now probably the best thing is you should just， you know， I'll put this on exercise set five。

 you should just go back and look at the recipe I gave you a week ago and notice that。

 you know if you just follow the recipe， this is exactly what you get。

 okay there's literally nothing to do other than observed that it's conforming to the recipe。

Actually， I mean， just to convince you a little bit in real time。

This is very close to the standard linear programming form we've always been using of maximizing subject to inequality constraints and non negative random non negative decision variables。

 The only twists are you have one constraint， which is an equation。

Saying it's probability distribution， and you have one variable which is unrestricted instead of non negative。

 other than that， it's the same form as max flow， et cetera， that we talked about at a length。

And it's not a coincidence that you have one equation and you have one unrestricted random variable。

 decision variable when you go to the dual。The decision variable W is the dual variable that corresponds to the quality primal constraint。

 and that's why you see the W is unrestricted。So just some preliminary pattern matching should give you some confidence that this really is true。

 but again， something you should think through offline。So it's the upshot？So call this W star。

 the optimalim solution to the second linear program。Well， give in。

But this is a primald dualual pair。And given strong duality， we talked about last lecture， Also。

 they're both feasible linear programs。 That's easy to see。 So strong duality applies。

And what a strong dual say， it says there's never a gap between the optimal objective function values。

So v star equals W star。And just by definition of what these things mean。This proves the。

Minimax there。So any questions about that？All any questions。

 otherwise we're going to move on to the second topic of the course。

 which is an overview of algorithms for linear programming。Com passman。在诉讼。

So speaking of rock paper scissors。Did you know？There's a World series。Of rock paper scissors。

Last time I checked the top prize was 50K。So I watched， you know。

 I did due diligence for your 261 lecture and I watched a couple YouTube clips。Word series of。

Of rockock paper scissors。The main takeaway I had is that it is just like pure psychological warfare at these tournaments。

 it's crazy。Which maybe partly explains why。The sort of otherwise curious fact that。

To a large extent， the same players tend to make it into the late rounds of these tournaments， which。

 of course， if everybody was randomizing perfectly， it would be totally random right。

 Who would dances in the tournament， and there is a lot of randomness。

 but some players do systematically better than others。Interesting to think about。Also。Did you know？

That researchers at the University of Tokyo built a robot hand。

Which has a winning probability of winning percentage of 100% in rock paper scissors。

How do you think it works？Yeah。It just it has like a super high speed camera and only needs one millisecond。

To see what you're going to do and then by the time you've unfolded your hand。

 it's done it in the corresponding mood。The video is kind of crazy。

 I'll post it on the website for you to check out。It made me wonder if you could kind of like trick it。

 you know， by looking like you're going scissors and being like，Oh no， no， you know。All right。

That didn't make the video in any case。All right。So hopefully by now I've impressed upon you the linear programming is a really important topic。

 so both there's tons of applications， tons of problems everybody wants to solve just reduces to them。

 and also conceptually there's a lot of beautiful and useful theory like duality。

We haven't talked at all about like， okay， so all these problems reduced to linear programming。

 but then how do you actually solve linear programming？And frankly。

 I'm not going to talk that much about it。I do want to emphasize what the highest order bit about algorithms for linear programming is。

 which is that there exists efficient algorithms， so it's an efficiently solvable problem。

 if you only remember one thing about linear programming 10 years from now， that would be a good one。

So linear programs can be solved efficiently。In both theory and in practice。

 so what do I mean by that？Well， on the one hand， on the theoretical side。

 there are linear programming algorithms which are guaranteed to solve an arbitrary linear program in a polynomial number of steps。

 so that's good。There are also。Really impressive commercial codes。

And these commercial codes routinely solve problems with say hundreds of thousands of variables and hundreds of thousands of constraints。

 which is pretty good Once you get up into the millions， it gets a little harder。

 it sort of depends a little bit more on how much special structure your problem has So that's what I mean by you can solve them in practice so hundreds of thousands should be no problem for commercial codes there's also open source codes like LP solve they're not quite as good。

 but they're still pretty useful so for here so one sort of big example is CX。

 but also MatTlab has linear programming solvers just to give another example。

And as I've tried to impress upon you， lots of problems reduced to linear programming and for that reason。

 there's really a non-trivial chance that at some point in your future work you will find occasion to use linear programming。

 so it's worth knowing that these solutions exist。All right。Now。I got to come clean。

 I'm not going to tell you in any detail how any of these algorithms work， okay。

And I should say that sometimes the algorithms in these two categories are not the same algorithm。

 sometimes the one which is theoretically good is not the one which is practically good。

 as we'll discuss， I'm not going to do it because any one of these algorithms would take at least a couple of lectures that's the first reason it would just push a lot of other stuff out of the syllabus。

The second reason is， you， to be honest， you know both people who prove theorems using linear programming and people who really use them to solve real world problems。

 almost nobody pays attention to how they work I mean more than most things。

 linear programming is treated even by professional researchers。

 professional optimizers as a black box so people really just sort of feed in their linear program and see what goes out and then go on with their lives。

 so it's very unlikely any of you would ever need to code up a linear programming solver yourself。

That said， you know？Kudos， if you sort of are left wanting more details。

 it is beautiful stuff to cover。 And so I encourage you to take a class on linear your programming。

 for example， from management science。 if you want to know more about this stuff。That said， you know。

 I do feel a responsibility。For graduates of 261 to have a certain very basic literacy Okay so the sort of few higher order bits of what's up with algorithms mill linear programs。

 I told you like the one the absolute highest order bit， which is this。

 but I want to give you like two or three more bits too。So。Any discussion of the simpleX method。

 sorry， any discussion of algorithms for linear programming has to begin with the simpleX method。

 both because it's the historically first method and also because it remains actually。

 believe it or not 70 years later， the dominant paradigm for how people solve linear programs in practice which is kind of amazing。

So the simplex method was developed by the aforementioned George Danzig in '47。

 so he both sort of introduced the paradigm of formulating and solving linear programs。

 plus he gave this first good algorithm for it in the form of the simplex method。

So Danzig spent about 40 years here at Stanford， so you should know a little bit about him。

 so he joined Stanford in 66， he stayed until his death at age 90 about 10 years ago。And。

So there's this one sort of tale that you may have heard， which you probably thought was apocryphal。

 or maybe you thought Goodwill hunting was completely fictional。

 but so there's this tale about this student。Who goes into a math class？

And it was late big auditorium。So you know comes in like 30 minutes late to a 50 minute class and just sees on the board there are these two problems writtenden down right you know given these hypotheses prove this is true。

 you know similar one， problem one， problem two， so the student who's late is like oh。

 I guess that's the homework you know scribbles it down。

And then works on the problems and it was like， wow， you know， he's。

So kind of hard for homework problems， you know， but dutifully works on them for like two or three days。

 solves both。Slipps the completed assignment under the door of the professor。

OkayAnd you sort I'm sure you know the punchline， this wasn't an assignment。

 these were two famous open questions in statistics。

 it turned out okay so the professor didn't even look at it for a while because there was no homework it was just some random you know page is filled with math from some student and then six weeks later。

 Danzig who is the student gets a knock on his door at six in the morning that is like you know his sort of grad dorm room on campus and professors there's six in the morning with like a draft of a paper saying like this is amazing we have to submit this to a journal right now etca。

 etc et cea so。And that wanted to being a thesis， so that was actually true。

 and that was George Danzig at the UC Berkeley State Department in about 39 or so。

So this a little bit later， this is 47。Simpplex method。How's it work， Well。

 so the simplex method is all about the vertices of the feasible region。 So in some sense。

 it operates on the boundary of the feasible region。So remember。

In our first linear programming lecture。When I developed your intuition。

Your geometric intuition about solving linear programs。We observed that acceptance in of edge cases。

 which we're going to ignore。The optimal solution is going to be at a vertex。

 So say if this was the objective function that you wanted to maximize。Okay。

So that's something we've discussed。So recall， except in the edge cases， opt。Always at a vertex。

So why is this interesting algorithmically？What's interesting about this is this says at least there's a finite algorithm for linear programming。

 And take us， take a moment to appreciate that。 right。

 So like almost all problems you've probably seen in the algorithms class up to this point。

 it was obvious there was a finite algorithm because you could always do brute force search and try every possibility。

 right。😊，If nothing else。linearar programming， these are like real valued decision variables。

 so it's actually not even clear what brute force search would mean for a linear program。

 given the infinite number of possible solutions。But once you say， oh。

There's always an optimal solution of a vertex， there's only going to be a finite number of vertices。

 so at least in principle there's a finite algorithm for linear programming。

 go through the vertices one by one and then check which one had the best objective function value。

Now， maybe you're wondering how you would actually in an algorithm。

 go through the vertices one by one。So the way you do it is you'd say， well。Notice， say in the cube。

Each of the vertices， each of the eight corners， it's at the intersection of three hyperplanes。

 it has three sides。And that's true in any number n dimensions， if you're an n dimensional space。

 it has to be true at a vertex， that n of the defining inequalities linear program hold with equality。

 so it meets with equality， at least a number of inequalities equal to the dimension why。

 well if it only met n minus1 or fewer inequalities with inequalities of equality。

 it'd be a direction of movement which would be feasible in both directions。

 but then you're not a vertex？All right。So we think of vertices as how would you enumerate over the vertices。

 you take your M constraints， you look at all subsets of n linearly independent constraints。

 you look at the unique solution that satisfies that particular subset of constraints。

 it may or may not be feasible， but for the ones that are feasible， you just remember the best one。

Okay。So that's not the simplex method， that would be just kind of a brute force vertex enumeration algorithm。

And， you know， a natural， smarter thing to do is to rather than do an unguided brute force search through the vertices。

 do a smart search through the vertices， so still search through them。

 but in more of like a greedy slash local search type of way。So they're really from 30，000 feet。

 what's the simplex method is doing。Is local search on the vertices。Okay。

Meaning you start at a vertex， you look at the neighboring vertices。

 you see if any of them are better， if none of them are better， you stop， if at least one's better。

 then you pick one to go to， you switch to that vertex。

 which is better so that's what I mean by local search。Okay， so for that to make sense。

 there has to be a notion of a neighboring vertex。 you know， you look at the cube。

 you kind of figure， okay， there must be some natural way to define neighboring vertex。

 So it corresponds to these edges， these sides of the feasible region， and there is。

The way you do it is you say， okay， so remember we said that a vertex can be specified by and linearly independent constraints with which it satisfies with equality。

So just call two vertices neighbors， if there are n minus constraints in common that they' both satisfied with equality。

So there's going to be endpoint of an edge in effect。

 so this one satisfies so in particular for the cube， this satisfies three。

 this is on three of the sides， this is on three of the sides。

 Why are they neighboring vertices because two of those three sides are in common between the two and so that's a definition that works in general。

So that's what local search on the vertices means。 at any given time。

 you have a subset of linearly independent constraints to move to an adjacent vertex。

 you kick out one of those constraints and swap in a new one and that's a neighboring vertex。Now。

 something which I think is intuitive。But I'm not going to prove it formally。Is that。

 you know what's the usual problem with local search。

 The usual problem with local search is okay you might you're going to stop eventually because you keep improving it over and over。

 but at some point you get stuck and who's to say that your locally optimal solution is anything as good as a globally optimal solution。

 How do you know you're not missing some way better solution。

 way over there in a different part of the search space And for lots of problems that's a real issue Okay in local search that's generally a problem。

This is a special local search algorithm in that it does not get stuck at a non global local optimum。

 The only local optima or also global optima。So guaranteed。To halt at opts， of course。

 I'm assuming opt exists， but that's the case， except for some edge cases。All right。

 and you I think if you sort of look at， you know， again， if you sort of go back to the cube。

 you should find this sort of very plausible， you're like， yeah， you know。

 suppose you were at this vertex and I told you that the objective function value only got worse if you went there。

 it only got worse if you went there， it only got worse if you went there。Well。

 somehow like all the directions that you can move and stay feasible are kind of convex combinations of all three of those crappy directions。

 so they will themselves just be crappy directions。 So there's no good directions。

 So you got to be optimal okay。And that's true in general， again。

 that geometric intuition is accurate， but formally the way the simplex algorithm actually。

 the way you actually prove it's correct， so how does the simplex algorithm know when it's done？😊。

Well， at this point， you should be ready for the answer to that。 Okay。

 the simplest algorithm generates a proof of its own correctness in the form of a feasible dual solution with objective function value equal to that of the vertex that it's currently on。

In fact， if you remember， we had these three conditions。Prial feasibility。

 dual feasibility and complementary slackness。 And if you have all three， then you're optimal。

 and we talked about how many algorithms can be thought of as maintaining two at all times and violating the third。

 the Hungarian algorithm violated primal feasibility maintained dual feasibility and complementary slackness。

 you can think of simplex as an example， which maintains primal feasibility。

It's always moving around the vertices， so it's always feasible。

 it maintains complementary slackness， it turns out。

 and what it's working toward is dual feasibility， but it terminates exactly when it has a dual feasible solution。

So that's how simpleimpX knows that it's done。And in fact， you know。

 in the same way that the correctness of the Ford Fson algorithm actually proved as a byproduct。

 the max Fem and cut theorem， the proof of correctness of the simpleimx method actually proves。

 gives an algorithmic proof of strong duality。 So's a different way to prove strong duality than than the ways I was telling you about on Tuesday。

 okay。All right， so simpleimpx is guaranteed to terminate with the optimal solution certified by a suitable。

Dual， satisfying complementaryary slackness。Okay。There's some details which I'm not going to talk about。

 You should take a linear programming class or read a good book to learn more about it。

 So there's a question of how do you get started。So how do you even know an initial feasible point that's actually pretty easy to fix you just sort of add a dummy variable which is in the objective and makes the feasibility question trivial。

 there's also the issue of degeneracy so there's a problem where a given vertex of a feasible region。

 there may be different subsets of n linear independent constraints which all describe exactly the same vertex if you have more than n hyperplanes meeting at the same point。

That means that when you're doing this move to a neighboring vertex， you swap out one constraint。

 you swap in another， you might actually stay at the same point。

 in which case you don't want that to happen forever， so you need some tricks to avoid cycling。

 but again that's well understood and can be done。So those are the main things I want you to remember about how simplex works。

 its local search on the vertices of the feasible region。

 where it just zips between the different edges of the feasible region。

And is guaranteed to terminate an optimal solution at a vertex justified by a feasible duel。Question。

But就。Theterinate that a public。I pretty local。Yeah。

 yeah I mean it's all sort of like tied together so I mean basically。

 so if you wanted to prove this from first principles， you want to prove something like okay。

 so you're out a vertex， you're primal feasible， you force complementary slackness。

And now you look at sort of like the dual solution that gets forced by compliment slackness。

 It may or may not be feasible。 If it's feasible， you're done。

And then what you need to prove is that if it's not feasible。

 it gives you a way to move to a better vertex。Yes the algorithm does have a like a way to jump from a local mental alternative。

No， so I guess let me answer you your question more directly you can think of it as so if you just wanted to prove there are no local minima other than the global minima。

 you wouldn't need simplex to prove that you could prove that really I mean the intuition is it just follows because it's a conve set and it's a linear function。

And then。Yes， so if you like。 so what you have to prove is that simpleimpx has a smart way of sort of。

え。Right so the simpleimpx never gets stuck somehow。

 so whenever it has a currently dual and feasible solution。

 it does in fact have a vertex that it can move to。Yeah， good question。Other questions？All。

So that's what I wanted to say about how it works， let me know sort of the inner workings。

 let me tell you a little bit just about its properties now， about its efficiency。

So one thing you definitely should know is that it's very fast in practice。Okay。

And most of the linear programming solvers that you're going to see out there are based on some variant of simplex。

 So when I said hundreds of thousands of constraints and variables， no problem。

 that's usually a simplex type code。ち。On the hand。And this is kind of frustrating for theoreticians。

Strictly speaking， the Sx algorithm is not a polynomial time algorithm。

 not in the way you normally define it， not in the way you learned it in CS161。

So the running time is exponential。In the number of dimensions n。Exponential。In worst case。Okay。

So how could that possibly be？Well， the first thing you need to realize is that the number of vertices of a feasible region can grow exponentially with the dimension。

That's the first thing to notice。 so certainly the brute force search algorithm is not going to be polynomial and N。

And already， the cube shows you that。So every time you add a dimension to the hypercube。

 you double the number of vertices， so that's growing like two to the end and in dimensions。

Now this is a stronger statement， this is saying， well， not only there are a lot of vertices。

 but somehow I can actually concoct things so the simplex algorithm visits every single one。

That's not a particularly easy result， it took a long time。

 so it was an open question for quite a while whether the simplex algorithm was polynomial time。

But clay and minty back in 72。Gave an example， which is kind of what they call a squashed version of the hypercube so that indeed the simplex method visits every single vertex so it actually does two to the n iterations on this particular example。

One thing you might be complaining about is。If you remember a local search。

 it says if there's a neighboring spot which is better， go there。

There could be many neighboring vertices， which are better。

 and you need some rule to decide amongst them。In this context， for the simplex method。

 this is called a pivot rule， pivot rule is the specification of when there's many better neighbors。

 which one do you go to？And so when you talk about simpleimpX being exponential in the worst case。

 you need to be talking about a specific pivot rule。

 but following Clamenti researchers came up with these exponential lower bounds for pretty much every natural deterministic pivot rule that anyone had ever been able to think about。

 so it's not something you can fix just with a clever pivot rule， at least's not deterministic。

Sort of an interesting twist and this is more recent work。

 this is more like last 20 years is that randomized pivot rules， so for example。

 if you know five of your vertices， five of your neighboring vertices are better than you pick one uniformly at random。

 they have a worst case running time， worstcase expected running time。

 more like two to the square root of n。Ithis actually， a lot better。

 I mean it's still not polynomial。 It's super polynomial。

 but it's actually a lot smaller than two to the end。 Okay， so randomization。

 at least for these theorems can can help， can give you better bounds on simplex。

There's also sort of a very famous conjecture in combinatorial geometry， which。This touches on。

So related。Is the heararsse conjecture？So the Hise conjection' has been around for a long time。

 and it's unsolved。So what does it say， it says， well。You know。

You can look at a feasible region like this。And you can think of its boundary as a graph so like here you have these eight vertices and then you also have these 12 edges so you can just think of the skeleton。

 if you like， of the feasible region as a graph with nodes and edges。

 You can then talk about the diameter of that graph。

So the longest to max overall pairs of vertices of the shortest path between them。

And if you think about it， this definitely has something to do with simplex because what simplex doing。

 simpleimpx is doing some kind of walk through this graph。 Remember。

 every move of simplex you go to a neighboring vertex。

 which corresponds to walking along an edge of the polytope。

 So every trajectory of simplex gives rise to a path between its starting point and the optimal point。

That path may or may not be a shortest path， but certainly， however long that path is。

 it's at least as big as the shortest path between those two points。So it's the point。

 so the Hirsch conjecture is about the diameter of polytopes。And just the thing to notice here。

Is that the diameter of the feasible region？Is a lower bound on the worst case number of simple ex iterations。

有谁。Because again， simpleimpx has to do a walk。So what is the hearse conjecture。

 the hearart conjecture asserts that every bounded feasible region。呃。Has diameter linear。

In the number of dimensions and inequalities， and constraints。

So that's a far cry from these exponential lower bounds we have on simplex。But that's open。

 so the best known results， the best known upper bound。

 so the conjecture is that there's a linear upper bound on the diameter。

The best known upper bound is actually very far from that。 Okay。

 The best known upper bound is what's called quasi polynomial。

 which means a term of the form N raised to the log n。so that's not polynomial。

 polynomial needs to be n raised to some constant， but it was proved by Colan Klyitman。

 this was in '92 that for every feasible region， the diameters at most end to the log n。

To bizarre always is at least quasi polynomial length pass。

 That doesn't mean that simplex is ever going to find them。 Okay， by following its rules。

 It's monotone improvement rules， but pass exists of length ended a log in。 Big open question。

 What's the right answer。Okay。So like I said， the fact that there are these bad examples for simplex poses a quandary。

To sort of the researcher in algorithms right because you know in 161 I teach you that polynomial time algorithms are kind of a first cut definition of what is a good computationally efficient algorithm and of course you know when I teach that I also talk about all of the different edge cases and linear programming is definitely one of those or not really linear programming but the simplex algorithm is one of those weird edge cases where even though it's exponential in the worst case。

 it's very fast on almost all inputs。So that then throws the gauntlet back at people who analyze algorithms。

 and the question is how can you sort of correct the theory so that it better reflects reality that simpleimx is almost always really fast。

So in the 80s。とと？There was a flurry of work by a bunch of people， Borgwort， Adler and Carp， Sil。

 a lot of big names。Showing that， on average， in some sense。

 the simplex method runs in polynomial time。 So for a random linear program。

The algorithm needs only linear time， sorry， polynomial time。Now。

 one thing which is tricky about this is it's not clear exactly how to define a random linear program。

Most definitions you might first think about writing down are going to always generate for you infeasible linear programs。

 So it's a little tricky to do that in an uncontroversial way。And but still， this was a big deal。

 sort of getting the theory closer to you know what was sort of empirically true and then actually crossing over into the 21st century now。

So spman and tangang。In 2001。Prove that the Sx algorithm has what's called polynomial smooth running time。

And this is like a very robust version of an average case analysis。 so here's how it works。

So you have simplex。And there's an adversary， the adversary wants to make your simplex code run super slow。

 and we know， you know， without changing the model。

 the adversary could pick the clay Mini cube and force simplex to run forever。

So I'll change the game a little bit。The adversary can pick whatever linear programming they want。

 linear programming they want， and then nature will perturb it very slightly。intuitively。

 I just sort of like flick all of the numbers by a little bit in this adversaries linear program。

 Okay， so it's a worst case， initial linear program。

 and then a small random perturbation around that first case。

And so what Spe and Tang proved is that no matter what your worst case starting point is。

 on average over the perturbation， simplex will run in polynomial time。

So that's what it means to polymal smooth complexity。

 I teach a course CS264 calledBeyond worst case analysis where we talk lots more about this if you're interested。

 I'll probably teach that next year。So what's the point， what's the takeaway。

 the takeaway is that while there exist bad instances for simplex， they are very。

 very rare and very isolated， and the smooth polynomial running time is a way of making that intuition totally precise。

Right。That's what I had to say about simplex， any questions about that？All right。So。

Next thing I want to talk about is the ellipsoid method。So this is a result due to catch in in 1979。

 was working in the Soviet Union。The algorithm was actually from earlier。

 was from the early 70s by S and others， it was an algorithm originally for nonlinearar programming。

 and what Katsciian showed is actually this ellipsoid method this algorithm actually ran runs in polynomial time for linear programs。

So this is the first ever。Poly time， LP algorithm。Okay。For every linear program。

 it's guaranteed to find an optimal solution in a polynomial number of steps。

And so it took me a while to figure out that this had happened as it was published at the beginning of 79 in a Soviet journal。

 and then Eugene Lawler， who was a professor at Berkeley and operationseration research there。

 He went to a conference in Germany and talked to you know someone from Poland who had heard caught wind of of this article。

 finally got a copy of it in May and translated it。

 and it was sort of verified in July by a couple Hungarians and then。

In October it showed up in Science magazine as a report and then in November it went viral and it hit for example。

 the New York Times that's the handout that you all have frontron page， if below the fold。

 but still frontp New York Times， it's a good case study in how hilariously inaccurate mainstream journalism can be on scientific topics so for example。

 the New York Times， it wasn't just that article there're also followup articles。

 everybody kept trying to say that Kachen's algorithm would solve know solved the traveling salesman problem。

Which it doesn't traveling at least as far as unless P equal NP P it doesn't。

 it alls linear programs， linear programs are NP P， traveling sales and problem is NP complete。

But all the articles kept insisting that。So they also mentioned so just the first half of CS2661 is so influenced by the Cold War。

 it's just sort of crazy， so in the article there also these kind of like you know illusionusions to oh maybe this new algorithm will break the US secret codes and it's a military threat and it's really crazy。

😊，Just be glad it's not that that's over， that part of the conflict is over。嗯。Good。

So what I want to say。So that's a great theoretical breakthrough， so that's a great result。

 as far as practical relevance， not so much。I should say very slow。

so pretty much on almost all inputs， it's going to be orders of magnitude slower than simplex or the other practical methods I'll tell you about in a second。

 so it's not even close。So how could this be， how could you have this polynomial time algorithm which is sort of so much worse than some exponential time algorithm with the sort of two issues with the ellipsoid method and this guarantee the first issue is that the degree in this polynomial is pretty big。

 I forget if it's five or what this pretty big polynomial。

The second issue is that the typical running time of ellipsoid。

 so its running time in a typical instance is actually pretty close to its worst case running time。

 so it has this sort of very flat running time performance which is always polynomial。

 but a very large polynomial。 simpleimx， as we discussed， is like totally the opposite。

 The peaks are exponentially high， but not all of the landscape it runs super fast。

So that's sort of technically the difference between these two algorithms。Now。

For those of you who are considering， you know。Proving theorems in the future。

 the illll method remains a kind of uniquely great linear programming algorithm。

So it has a really amazing property that no other known linear programming algorithm has。

The algorithm remains polytime。And the number of dimensions n， the number of decision variables n。依文。

When the number of constraints。Is exponential in it。Exactly。Exactly， it makes no sense。

 You can't even write down all of these constraints in polynomial time。You're totally right。

 that's exactly the right response。Provided。So here's the fine print， but this is still amazing。

Provided there is what's called a separation Oracle。

So what's separation a polynomial time separation oracle， so what's a separation oracle？Well。

 you feed it in as input。Candidate solution。Which may or may not be feasible for the linear program in question。

 the linear program with exponentially many constraints。

And the separation Oracle is then responsible。For either verifying its feasibility， saying yes。

 this satisfies every one of the exponentially main constraints。Or。If it's an infeasible solution。

It should output a violated constraint。Okay。And so I'll give you more details in a second。

 but basically what's to go on here is the ellipsoid method will actually only generate inequalities as needed on the fly and as suggested by the separation oracle。

And so because the ellipsoid method actually terminates with a polynomial number of iterations。

 it's only going to invoke the separation oracle of polynomial number of times。

 so it'll never actually generate any more than a polynomial size subset of the exponentially mimic constraints。

So I'll to be more clear as I tell you more details about how it works。But so that's pretty amazing。

 So you have implicitly defined linear programs， you can still solve them in polynomial time。

 And because of this property， there's problems that， at least in principle。

 we know their Comp is efficient in the sense that the polytime solvable。

 And the only proof of that fact that we know uses the ellipsoid method。😊，So for theoretical work。

 this is incredibly powerful。Now， which' probably thinking now is like。Like okay。

 so what's an example， like why would I ever care about a linear program with exponential number constraints。

 if there were an exponential number of constraints。

 how on earth could I like you check them all in polynomial time。

 that that all just seemed kind of nuts？But you've already seen a linear program。

 which perfectly fits in。To this framework。 And， in fact。

 on the last problem on the problem set is' a couple more problems， which perfectly。

Fit into this framework。But let me remind you from lecture 8。The dual to our flow linear program。

 Okay， so in lecture 7， we had this very nice flow linear program with only a polynom number of variables。

😊，In lecture 8， when we were doing our kind of LP duality tutorial。

 we wrote down a different linear program for maximum flow where the vertices the decision variables corresponded to paths。

Then we took the duall of that Max F linearar program。And we got the following。Okay。

 so if you look in your lecture 8 notes， this is exactly what you'll see there。Oh， and this is。

For all ST paths P。Okay。So what did we have to say about this linear program last week？Well。

 what we observed is that if you hand me an ST cut。

I can translate your SD cut into a feasible 01 solution of this linear program where the objective function value is the capacity of your cut。

Okay。How do you do that， you just set L equal to1 for all the edges sticking out of the source side of your cut and zero everywhere else。

 that's what we did last week。So the point being is that this linear program optimizes over a superet of the ST cuts of the graph。

And we also last week used observe that because the max Fment cut theorem is true， actually。

 even though there are fractional solutions that are feasible for this。

 there's always an optimal solution which is 01， which corresponds to a cut。

So why am I mentioning it now？Well， how many constraints are there？Well。

 it depends on how many ST paths this graph has。But some graphs have a lot。Of ST paths。

So if you just think about a graph。It looks like this over and over again。

That has an exponential number of different paths because you can go up or down independently for each little portion of the path。

So this is a linear program with an exponential number of constraints。 Dec variables are fine。

 There's only M decision variables。So as soon as you see that， you say， oh。

 this is a candidate for the ellipsoid method。 there's a few number of variables。

 a large number of constraints。You can say， oh， as long as there's a separation oracle。

 then we're going to be fine。 We' can actually solve this in polynomial time。Now， again。

 you might be worried about a separation oracle because if you have exponentially many constraints。

 how could you ever check feasibility without checking every single one of them？Well。

 sometimes we're able to actually explore an exponential sized space while only doing polynomial work。

And this is one of those cases。So what's the separation Oracle here， So remember how it works。

 So a separation Oracle takes as input a candidate solution。

 So that's going to be proposed values for the LCBs。So give an LCB。

So now we need to verify whether this is a feasible dual solution or not， and if not。

 we need to exhibit a violated constraint。So。First thing to do is we can just check these directly。

Exject that there's no negative Ls， if so， then we can immediately return that as a violated constraint。

So there's an exponential number of constraints here。

But how can we actually check them all in polynomial time？The first。那个これの。Oh。

 in this particular example。Okay， good， how about in general。

An algorithm you learned in CS161 just does it right off the shelf。

So the reason I chose the variable L here was to denote lengths。Okay。

So if you sum over the edges of an ST path and you sum up the links， you get the length。Of the path。

What of the constraints say it says every single path has length at least one。That is。

 a shortest path has length at least one same thing。Okay。

 we know how to test if the shortest path has length at least one or not。

You just run Dyter's average。Okay。So you may never have thought about it this way before。

 but Dyketra's algorithm literally is searching an exponential sized space in almost linear time。

 so for specially structured problems we actually can achieve these kinds of results。All right。

 so what's the point is that this linear program， I hope I've convinced you。

Has a polynomial time separation oracle， that's what it is。And given what I told you earlier。

 you now know that we can actually use the ellipsoid algorithm to solve this in polynomial time？

And then once we do that， because we know there's zero1 optimal solutions。

 we're actually going to get a cut back from the ellipsoid method when we use it on this linear program。

 the min cut， the minimum cut with the separation oracle。Now。

 of course we know much more direct ways to compute a min cut。

 you can just compute a max flow and then do breath for search that's certainly how youd do it in practice。

 but again， sort of for harder problems， sometimes we know no alternative to the ellipsoid method。

Okay。2呀。So let me just give you a cartoon version of how it works。Which is pretty cool。

So there's this sort of silly story about how do you catch a lion in the Sahara？You know this？

So you start by encircling the whole Sahara。With a fence， a lion proof fence okay。

Then you cut the Ahara in half。Then you somehow figure out if there's a lion in the left side or the right side。

 and then you recurse。And you keep recursing until the size of the quarantine is so small。

 you know exactly where the lion is。So that's how you hunt a line in Sahara， so they say。

And believe it or not， that's like kind of a pretty accurate description of the lloid method。

So let me explain。So how's it work？So there's going to be some feasible oath。Prepro step。 So first。

 linear programming， as you know， you optimize something subject to feasibility。Actually。

 if you think about it， really optimization reduces to feasibility。 Okay。

 if I can just give you a subroutine for checking whether a linear programming is feasible or not。

 you can use it as a black box to optimize。 Do you see how。

What's the usual way if you don't know sort of the right objective function you search for it？

Binary search， exactly。So you just add a constraint which says I want the objective function to be at least 100 and you invoke the black box and either says yes。

 it's feasible or no， it's not feasible。 If it is feasible， you get more ambitious。

 you double 100 to 200。 if it's infeasible， you cut it to 50 and then you just sort of zoom in on the optimal solution。

So that's in ellipsoid， the first thing you do is you change it to a feasibility problem。 And again。

 that's good enough to optimize by binary research。 So all we're trying to understand is。

Is there a feasible point， okay？So here's what happens， so in the initialization。

The lipoid grows like a really big ball。It's trivial to compute。

And it's sure that it contains the entire feasible region。

 this ball is going to be like way bigger than the feasible region in general。

So that's the initialization。And then what the ellsoid algorithm does is it says， well。

 let's look at the center。Of the ellipsoid。 O， by the way。

 what's an ellipsoid that's just an ellipse， but in high dimensions。 That's all it means。

So we look at the center of the ellipsoid。And we ask our separation oracle。

 is this or is this not a feasible point？It's feasible。We go home， we're done， okay？

If it's infeasible， well， then the separation Oracle is responsible for telling us， nope， sorry。

I didn't previously tell you that there was this one constraint。Sing。That to be feasible。

 you got to be the left of this。Half space。O。Now it's got to know by definition。

 it's going to be some inequality， which the feasible region satisfies so the feasible region will be entirely on this side of the half space and the center will be on the opposite side because it was infeasible so this is what the separation Oracle gives you。

And so now， of course， and so you know the feasible regions on this side。

 that's like knowing the lions on this part of the Sahara and you recurse。

The one thing which is a little tricky about recursing is that rather than just keeping the shape like this semialipsoid。

 what you're actually going to do is redraw a new ellipsoid。That contains this semiulipoid。

So that's what it does Now why this obsession with ellipsoids？Basically。

 ellipsoids are the simplest objects which can give you a decent approximation of all the different kinds of polytopes。

 fat polytopes， skinny polytopes， et ceter， obviously spheres wouldn't be good if you had a very skinny polytope。

So why do you want to stick with simple objects， Well， you know， for example。

 it's very easy to define and compute the center of an ellipsoid， whereasas if you kept recursing。

 you'd start getting some super weird looking shapes， which would be tough to deal with。

 So you maintain as an invariant that you always have an ellipoid。

And some elementary but tedious calculations show that actually the volume of the ellipsoid you're working with decreases at a reasonably healthy rate。

 every single iteration。So the volume keeps going down。So what do you do you just keep running this。

 if you ever find a feasible point， then you're done。As long as it's infeasible。

 you keep shrinking the volume at some point the volume of what's left is going to be so small that given the precision of the input。

 so given the number of bits used to specify the numbers in the linear program。

 you can actually be confidence that in the super tiny region that's left there it does not exist a feasible solution。

 and in that case you can correctly declare that the problem was infeasible。

So that's how the illlloid method concludes。One final sentence。

Which is at least want you to see this phrase once。There's a third paradigm。Interior point methods。

These were developed latest in the 80s， and what's cool about them is you sort of get the best of both worlds。

They run in polynomial time， even in the worst case。

 and they are competitive with simple in practice。So for example， in MatTlab。

 one of their linear programming solvers is in fact based on interior point methods。

 especially on large LPs， sometimes interior point methods does better than simplex。

 sometimes simplex does better than interior point and it's basically an open question to understand deeply when one algorithm does better than the other。

 but so from a practical standpoint， those are the two states of the art modern simplex codes Interi point methods have a good weekend I'll see you Tuesday。

