# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p24 NETS 4120_ Algorithmic Game Theory, Lecture 25.zh_en -BV15kLRzTExU_p24-

其他人其他。

![](img/84c186961113b6b351d092f21a530599_1.png)

All right。So congratulations everyone for making it to the final Net 412 lecture or 4120 as。

We say no。Um。And so for most of the class， up until like last lecture， if you recall。

 we've sort of been game theorists that head like of。

Learning theory problem you know maybe we knew some little bit of learning theory and we made productive use of it。

 you know we we use the we drive and use the polynomial weights algorithm to prove the minmax theorem and to think about dynamics in games and to give online auctions we。

I studied bandit learning algorithms like the upper compete bound algorithm to drive dynamic pricings and in general we sort of took advantage of things like statistical estimation and random sampling auctions。

And then starting like last lecture， we sort of transitioned from being game theorists with a learning theory problem to learning theorists to a game theory problem。

 like rather than reducing problems and mechanism design to。

Problems in statistics and machine learning that we could solve。

Last lecture we started from sort of this purely learning theoretic problem。

 we wanted to make predictions， robust predictions against an adversary。

That had some nice property that were calibrated in the worst case。

 and we sort of derived algorithms using what we know about game theory in particular by reducing to the minmax there。

And so today I want to do something similar。 I want to start with a。You know。

 purely machine learning problem this boosting problem， how do you take a predictor。That is。You know。

 okay， a little bit better than random guessing and combine predictors of that sort into predictors that are actually quite strong that are good at making predictions。

And I want to solve this problem using what we know about game theory。嗯。So yes。

 what I want to do today is sort of。Derive from scratch this sort of class of。

Machine learning algorithms called boosting algorithms that you might have encountered if you've taken a machine learning course or played around with things。

 they have names like add a boost or gradient boosting and。The general idea is， you know。

 like if you've got some simple method， like the ability to learn shallow decision trees or something is that is sort of kind of nontrivi。

 like better than random guessing， but not great。How do you？Use that method。

 maybe run it a few times and combine the simple rules you've learned into a single model that is substantially more powerful。

 substantially more predictive。Okay， that informally is the boosting problem。

And so let me try to give you like a crash course in machine learning。

Is this stuff you might have seen before if you've taken a mission learning class。

So just to sort of fix the setting。😡，We're going to think about。

Data sets that consist of labeled examples， what is a labeled example well。You know。

 it's got like some features， maybe if it's like an image labeling problem。

 the features are like the pixels in an image。And it's got a label， you。

 the label could be anything in this class sort of。

Think about binary labels so so the label says you know。

 is the thing in the image like a cat or a dog， a hot dog or not a hot dog？And so for example。

 you know， although。These choices aren't too important。

 you know oftentimes like the features will be things like vectors of numbers。

 like that's the case if the thing if you have like an image classification problem right like then the features you have available when you're trying to classify whether something is a hot dog or not a hot dog are like the pixels in the image which we can encode with real values。

And then we've got like a binary label， for example。

 where one denotes that the image is a picture of a hot dog and zero denotes that it's not。Okay。

 so we're given a data set， which is a collection of N such labeled examples。Okay。

 sampled from some distribution， presumably。And our goal， right since we're given。

A bunch of examples together with you know like the answer。

 the thing that eventually we'd like to learn to predict does the image contain a hot dog or not。

 but our goal is to learn to predict labels on new examples we haven't seen before and to do that we need to learn some mapping that looks at only the features and tries to predict the label takes as input like the pixels of the image and tells us does it contain a hot dog or not。

We'd like to do this in a way that has high accuracy。

So there's different ways you could measure accuracy。

 but I want to think about maybe sort of the sort of simplest one the the one youd maybe think of first。

 which is just。How frequently do you get the answer right？Okay。

 so suppose we've got some predictive model takes as input images， outputs， labels。

The accuracy on that model， on a data set is just the fraction of points for which our model correctly predicts the label。

Okay， so it's just like the average overall of the points in our data sets。Of the indicator。

That when we apply of the event， that when we apply our model to the features， okay。

 the model doesn't get the labels， the prediction of our model is correct。

 It actually is the know actually is the。The label。Okay， so like on any particular example。

 this is one if we predict the label correctly and zero otherwise。And so this average。

 the accuracy of our model on the data is just the fraction of examples it correctly predicts the label on。

Now。You know this notion of accuracy just sort of uniformly weights all of the points that sort of saying all of the points are equally important。

 I'm just measuring like the unweighted fraction of points that the model gets correct。

But you can also imagine defining a weighting that sort of informally says some of the points are more important than others。

Okay， and so we could also imagine given a weighting that you can think of as a distribution over the points。

Asking， what fraction of points does our model correctly label， not under the uniform distribution。

 but under this other weighting under this reweighting？Okay。

 so I can also talk about the accuracy of my model on a data set。Under some waiting。

Which is just the same thing as the accuracy of the model。

Except instead of giving every point the same weight one over n。

 different points could conceivably get different weights。

Okay so these are both you know like the weightings this should be like a distribution over the point。

 so in either case these numbers are numbers between zero and one like what fraction of the points do we get correct。

You know if there's no weighting it's just what fraction of the points under the uniform distribution do we get correct if there is a weighting then we're asking what fraction of the points on this reweighted data set where we've said some of the points are more important than others。

Okay， does that make sense？We've got some model， we can like ask how accurate it is on our data set。

 like what fraction of the labels does it predict correctly？Okay。I just want to like。

Mention up front， something that I'm basically going to ignore for this lecture。

So an important statistical aspect of machine learning。Is， of course， that。

My goal is not to predict the labels of the points in my data。

 I already know the labels of those points， my goal is to predict well on new points that I haven't seen before that that are somehow you know。

 statistically similar that are drawn from the same distribution。Right。

 because actually like if I just wanted to predict the。Labels of the points in my data set。

I could do so by just writing like the labels of all of the points on my hands and whenever you asked me about a point in my data set I'd like look it up and I'd always be right and I wouldn't really have learned anything that wouldn't be a good model for points I haven't seen before。

Okay， so like our goal is not really to minimize or or maximize accuracy。

On the points in the data set， we'd really like to do this for sort of other points and sort of informally。

 a whole theory for how to do this。Informally， we want to make sure that the rule we're coming up with to predict labels。

Produces simple rules somehow， rules that can be expressed more concisely than。

Just writing down all of the labels on my hand Okay。

 so like the if the description length of your prediction rule is。You know。

 smaller than the description length of the data， then it must be that you have learned something that generalizes to new examples。

U。The approach we're going to derive in this lecture has this property。

 so it is a good learning algorithm， it's not just a look up table。

But I'm not going to talk about it， we're just going to talk about the algorithmic aspect in this lecture。

 but just like as a good piece of culture to remember the goal in machine learning is not to predict the labels in your training data set which you already know is to predict the labels you haven't seen before and in order to do that it is sort of necessary and sufficient to compress the data you want to learn something that is simpler than the data itself。

Okay。嗯。😊，So a little bit more setup。knowWe're going to learn some rule。

 what's that rule going to look like， well， let's say that a hypothesis class H is a collection of rules we might learn。

Okay， so it's like it's just a collection of predictors。

 a collection of functions of the sort we're trying to learn， each of which map features to labels。

 okay， so there's all sorts of different ways we could imagine trying to predict given an image does it contain a hot dog or not。

Um and。A learning algorithm。It was just an algorithm， This is the kind of thing we'd like to design。

That takes as input a data set， takes as input， you know， a data set of labeled examples and。

Outputs a hypothesis， right， it like takes as input data， it thinks about it。

 and it somehow outputs a rule designed to predict the labels given the features。Okay。

 and remember we talked about， and hopefully this rule has， you know， you know。

 the predictive rule you learn has high accuracy。And remember we talked about。Accuracy， not just。

 you know， like uniformly over the data set but but in this sort of weighted。

Way we can sort of weight different points so that they contribute differently to the accuracy and so a weighted learning algorithm just takes says input a data set and a weight vector telling us how important each of the data points is and it outputs a hypothesis。

 so a rule for predicting labels given features that hopefully has high accuracy under this weight vector。

Okay。So yeah， I want to point out that like。If we're in the binary prediction setting。

 if there's only two labels， if you're you know the image either contains a hot dog or it does not。

Then it is not interesting， you know， you should not be too proud of yourself if you come up with a learning algorithm that finds hypotheses that have accuracy less than one half。

I mean， there's only two answers， the label could be one or zero。

The accuracy is just the fraction of the time you get the answer correct。

 so get if you get the answer correct like less than half the time。

This is worse than you would have done by random guessing。

If I just like ignore the data and flip a coin for every example， my accuracy will be one half。

 oh I'll get half of the answers right， so it's not interesting to get accuracy less than one half。

What I'd really like is to get accuracy something like 99%。

 I'd like to find like a good learning rule that almost always is able to correctly predict the underlying。

You know，The underlying unknown label。But what I want to think about is you know。

 like the space in between。Like suppose I'm doing better than flipping a coin。

I've designed an algorithm that consistently beats coin flipping。

 but can't get anywhere near 99% accuracy。Okay， so suppose what I've got is an algorithm， you know。

 it's like learning some simple rule， you know， like a linear regression or something and。

What it can do is it can reliably get accuracy like 51% can reliably do a little bit better than random guessing。

 like no matter what data set I give it。Okay， what can I do with this。

 something that reliably does better than random guests？Okay。We're going to talk about this。😡。

An algorithm that has this property that can sort of reliably do just a little bit better than random guessing。

 but not very well， we'll call it a weak learner。And the question I want to ask in this lecture is。

 you know。If you give me a weak learner。Can I use this as a subroutine。

 hopefully in a computationally efficient way to do something more like this to get accuracy 99%？O。

So we'll talk about this you know， in more in depth， more formally， but are there questions？

At this point。We're thinking about like a prediction problem， a binary prediction problem， okay。

 given images do they contain hot dogs or not？Accuracy， 50% since there's only two possible answers。

 that's trivial， I could do it by flipping a coin。Suppose you give me an algorithm that is a little bit non trivial it can promise to get。

You know， 51% accuracy， just a tiny， you know， like a smidge better than random chance what you'd get from guessing。

Does that you know， like is that a lot easier than getting 99% accuracy or is it basically the same problem。

 like if you give me this weak learning algorithm， can I use it to get actually a strong learning algorithm？

That's the question in booster。So that the question？

That we want to ask and answer in this lecture makes sense。Yeah，好的。好。嗯。Sa the am。

So it's a binary prediction problem so there's only two yeah there's only two possible labels in general you could talk about like a K label problem in which case you know like the random guessing benchmark would be like one over k instead of one over two but in this lecture we'll just talk about two labels good question。

Other questions？Yeah。后们。We year。They could do better。

 but the only promise we have is that they get 51% accuracy。

 but maybe we get lucky and you know on this data set we get like 60% accuracy。Okay。

 so you could ask this question for you know k label problems。

 you could ask it for regression problems so in every case the question is if you give me something that does a little bit better than random guessing can I turn into something really good but in this lecture I'm just going to like ask and answer this question for the binary。

Prediction problem， two labels。Okay， and it makes sense。O。SoLet's formalize this a little bit。

So suppose we've got one of these weighted learning algorithms。

 it takes as input a data sets and a weight vector。We say that。

This algorithm is a weak learning algorithm for the data sets。If。For every weight vector I give it。

It can always find a hypothesis such that。The weighted accuracy on this data set is a little bit better than random guess。

Please 51%。Okay， might sometimes do better than that。

 the promise is just that in the worst case it's always a little bit better than random gets。

And you might say， like， am I trying to like？You know。

 sneak in like a past one here like what is this weighted learning algorithm maybe you're used to thinking about learning algorithms that like get training data and like output hypotheses。

 what are these weights doing？嗯。😊，And the weights are sort of like without loss of generality。

 so just to sort of say something quick about that。First of all。

 like in almost any machine learning algorithm。You've ever seen。

 you can just directly input the weight like if you're training like a neural network。

 you're minimizing some loss function that is just you know the average of whatever your favorite loss function is over all of the data points and you can just like plug in the unweighted average but the weighted average and the algorithm works exactly the same way。

If for whatever reason， you've got a learning algorithm that。Doesn't take as input wavess。No problem。

When I say。YouWhen I say here input a data set and weights。

 what you do instead right like what are the weights。

 they're just specifying a probability distribution over the data points in your data。

Just sample a new data set， according to that program distribution， meaning。You know。

 given your data and the weights sample a bunch of points proportion you know。

 where you sample each point proportional to the weight have've given it。

 that gives you just a new unweighted data set feed that to your learning algorithm。

Exactly the same thing。Soll i'll speak as if the learning algorithm directly takes as input these weights。

 but that's just for convenience like we everything i'm saying would be true with just sort of。

An additional added notational burden if。The learning algorithm only took as input data sets。没事。Yeah。

 the features are not weighted， it's like the the examples are weighted so maybe。Yeah。

 like images of hot dogs taken at Coney Islands are more important than images of hot dogs taken in grocery stores。

 something like that。Okay， other questions？Okay， so I'm going to talk about learning algorithms as if they take as input these weights。

Many of them actually do if they don't。Don't worry about it so you can just sample a data set and everything works if the algorithm just takes us input put a data set。

Okay， so like。Maybe it's a little the name we've given to these algorithms is like a little bit leading。

 but weak learning algorithms seem kind of weak right like the only thing they promise is that they do a little bit better than random guessing if you just wanted to get 50% accuracy you wouldn't have to do anything at all you wouldn't have to look at the data you could close your eyes flip a coin you wouldn't even have to look at the features of the thing you were making a prediction for。

And。You know， like we've got some machine learning algorithm and the only maybe it's like learning decision trees or something and the only thing we can promise about it is that it does 1% better than random guessing would。

Okay， so that doesn't sound great like it's not going to be a very useful algorithm in whatever your you know。

 deployed hot dog application is。What we want really is something that makes predictions that we can rely on。

 we want something more like 99% accuracy。Okay， and so maybe like。By analogy to。

Week learning algorithms， which get 51% accuracy。If something gets 99% accuracy。

 let's call that a strong learning algorithm。And the question is。You know。

 like is strong learning a harder problem than weak learning？Seems like the answer should be yes。

 right， like getting 99% accuracy seems harder than getting 51% accuracy。嗯。😊。

But it would be kind of interesting if the answer was no。Okay。

 and then maybe like what do we mean by get strong learning from weak learning。

 I sort of mean in the sense of like。Computally efficient reduction if you give me a weak learning algorithm。

Of course， in the other direction， a strong learning algorithm is a weak learning algorithm。

 right like 99% accuracy implies 51% accuracy。But the question I want to ask is if you hand me a weak learning algorithm。

Can I necessarily use it as a subroutine？In some otherwise， computationally efficient algorithm。

 Just call your weak learning algorithm some modest number of times and。

Get provably a strong learning algorithm。Okay， that would mean that the two problems of weak learning and strong learning are sort of equivalent in a rigorous sense that if you can solve one。

 you can solve the other with only polynomial overhead and vice versa。Okay。

 so let's be ambitious in our definition of strong learning。 I said we want 99% accuracy， but like。

Why are we leaving that last 1% on the table， let's just go for like 100% accuracy。Okay。

 so let's say that a strong learning algorithm for a data set。嗯。

Is one that like outputs a hypothesis that never makes a mistake on the data set。Okay。

 like gets all of the predictions correct。Okay， so this seems like a much harder problem than we learn。

Okay。But the theorem I want to prove sort of。One of the foundational theorems in machine learning。

Is that in fact， weak learning and strong learning their equivalents。

We learning is actually no harder than strong learning and vice versa。Okay。

 so one directions obvious if I can always， you know solve machine learning problems with perfect accuracy。

 that means I can always solve them with 51% accuracy， but the surprising direction is that。

No matter what data set you give me。If there's an efficient meaning like polynomial time。

 weak learning algorithm for the data set one that can always guarantee 51% accuracy。Then actually。

 there's an efficient strong learning algorithm。a polynomial time algorithm that can always make perfect prediction。

Okay， so this is the theorem。嗯。What do you think？How should we prove this theorem？Yeah。Yeah。

 it seems like a good idea we've done majority vote kind of stuff before。Yeah。Okay， you know。

 I guess like。Sometimes you can like guess the answers to like exam questions from the context in which they've been asked and I guess。

You know， having given a。Prefix of this lecture about machine learning。

 but like in like an algorithmic game theory class。

 that's like a hint as to what the proof idea might be the way we're going to prove this theorem is by using the tools we've developed in this class to study games。

😊，In particular， we're going to define an appropriately defined zero sum game。

We're going to analyze the value of that game， we know that zero sum games have a value by the minimax theorem。

And the way we're going to derive the algorithm that。Witnesses the statement of this theorem。

 the actual algorithm that is the reduction from weak learning to strong learning will be。V。

The computation of the equilibrium strategy in that game。

 which we know how to do with the polynomial weight algorithm。Okay。

 so that's going to be like the outline of the solution we've got this basic sort of foundational problem in machine learning we're going to solve it using you know。

Our favorite toolkit from。Netets 4，120。Have you guys gotten used to the？

All of the classes having like a zero at the end of it it seems like a waste of like the last digit right it's like always zero。

So there's this。Banknot from Zimbabwe during like periods of hyperinflation where they just added like 10 zeros to the end。

 I feel like the same thing's happening here。Okay， so let's prove it。嗯。

So we've got this week learning algorithm A， someone has handed this to us。

And it's got some hypothesis class right like you know you give it a data set。

 what it does is it outputs a hypothesis， the hypothesis class is the set of all hypotheses it might output give。

 you know like for any data set you give it。And so what I want to do is I want to define the following two player zero sum game。

What do I need to do to tell you a two player zero sum game and need to tell you who are the players？

There's two of them。I need to tell you what are their actions， what with their action set。

 and I need to tell you what is the function that the minimization player wants to minimize and the maximization player wants to maximize。

Okay， so first of all。The minimization player， which maybe I'll refer to as the data player。嗯。😊。

Their action set is going to be。The set of。Labeled examples in the data sets。Okay。

 remember the input to a learning problem is a data set consisting of n labeled examples like images together with the label of whether they contain a hot dog or not and so like the set of pure strategies for the data player the minimization player will。

Correspond， know they've got N peer strategies， each one corresponds to one of the labeled examples and a mixed strategy for the data player corresponds to some distribution over those examples。

 like a weighting of the data set。And the action space for the maximization player。

 which I'll call the learner， that corresponds to the hypothesis class of the learning algorithm。

Okay， so out of all of the hypotheses that the learning algorithm might output。

 like a decision tree of depth for， for example， a puret strategy of the learner corresponds to one of those hypotheses。

 one of those models aimed at predicting labels from features and a mixed strategy for the learner is a distribution over models。

 awaiting of the hypotheses。And there's a cost function that the minimization player。

 the data player would like to minimize and that the maximization player。

 the learner would like to maximize。And let's try to put the cost function in correspondence with accuracy。

you know， like anthropomorphizing these characters a bit right like the learner would like to maximize something。

 the natural thing he'd like to maximize is the accuracy of his prediction。They remember。

A pure strategy for the data player is a labeled data point， a feature vector on a label。

A pure strategy for the learner is a model， something that predicts a label given the features。

And so let's say the cost， given a feature vector on a model is just the indicator of whether the model chosen by the learner correctly predicts the label of the data point chosen by the data player。

Okay。So for example， if the data player plays a mixed strategy。

Which is just a weighting of the data points， a distribution over the data points。

 the expected cost for the learner。The thing that the learner would like to maximize is just the weighted accuracy of the hypothesis that he chooses。

Okay， does that make sense？So we've set up like a zero sum game。

In which the minimization player plays， well， if they're playing mixed strategies。

 plays distributions over the data set， so weightings over the data， the maximization player。

 the learner plays hypotheses or maybe distributions over hypotheses and the thing that the learner would like to maximize is their accuracy and the data player would like to play so as to minimize the learner's accuracy。

Does the game make sense？The rest of the proof is going to be thinking about this game so this is。

A good point， this is a good time to like take a moment to just make sure we all understand the game。

Yeah。What。So remember a zero sum game？It is just one in which there's like a single objective function that one player wants to make big and the other player wants to make small。

R， why is it called zero sum， right like suppose both players have a utility function。Well。

 this is the utility function for the data player， they'd like to make it big。And we're sorry。

 this is the utility function for the learner this the accuracy。

 the learner would like to make this big。What's the utility function that the adversary would like to make big。

 well it's the negative of this because they'd like to make this small and so if I sum up this and the negative of this at zero。

Yes but but yeah， like when we've talked about zero sum games， there's like。

Rather than talking about two functions that are， you know the negative of one another。

 it's easier to talk about like one function that the maximization player would like to make big and the minimization player would like to make small。

That makes sense。Yeah。Thatて。Well， what does anyone really want like like within the game their objective is to minimize accuracy now of course like。

This this is like an object we're constructing in the proof， like like in real life。

 there's no data player， but you know， the data player who is a character in the proof， you know。

 yeah， they really want to minimize accuracy。That makes sense。O。Other questions？Okay。And so。

 you know， like what do we know about zero sum games。

 like the one thing we know about zero sum games is the Minmax theorem。

 which which means that the game has what we call a value。Right， like like in general。In games。

 we think about them when we think about Nash equilibriumlibria as both players playing simultaneously。

In general， things could play out differently if one of the players went first instead。

 if like one of the players had to go first， commit to their strategy and announce it and gave their opponent the ability to best respond。

 the opportunity to best respond。And the special thing about zero time games is that the order of play didn't matter so long as everyone played optimally。

😡，Okay， so like in rock paper， scissors， if I。Tell you upfront my strategy。

 I'm going to like randomize uniformly at random between rock and paper and scissors that does not give you the ability to exploit me。

Similarly， if I tell you that， and you best respond。

The average payoff in the game is going to be the same as if you told me your strategy up front long as it was optimal。

 randomizing between rock and Paver and scissors is my best respond。

And then sort of what the Minmax theorem tells us is that's like a property that's true of all zero sum games。

If the minimization player goes first and announces their strategy and gives the maximization player the ability to best respond。

 the expected payoff is the same as if the maximization player goes first and announces their strategy and gives the minimization player the ability to best respond and whatever that payoff is since it's the same in both cases。

 we call that the value of the game。So the first question we can ask about a zero sum game is what is the value of the game？

But。Okay， so。You know， again， like。This is sort of similar to last class。

What's really going on when we design a learning algorithm and we want it to have worst case guarantees。

Is like we， the learner， are sort of going first because we're like committing to an algorithm。

And then if someone's trying to like falsify that we have worst case guarantees。

 they might try to like best respond with knowledge of our algorithm， with knowledge of our strategy。

 trying to falsify those。But。It's easier to analyze games often if we reverse the order of play in our imaginations and imagine the adversary goes first。

And we can figure out what the value of the game is。

 and that tells us how well we can do if we go first。

 because those two numbers are the same by the Min Max there。Okay， so going through this exercise。

I claim that。The assumption that we have been given a weak learning algorithm。

 that there exists a weak learning algorithm。Implies that the value of the game has to be at least 51%。

Okay。Let's think about it。Let's imagine the data player goes first。

The data player is the one who wants to minimize accuracy。

So we're looking at the min max value of the game first the data player commits to a mixed strategy。

 a distribution over the data points。Then we get to look at that distribution over the data points。

 W， and best respond by choosing a hypothesis that maximizes accuracy。

And the way we evaluate how well we've done is we compute the expected utility。

 which the way we've set things up is just， well， it's just the weighted accuracy on this data set。

It's just the weighted fraction of points that we predict correctly because the cost function is just the indicator of whether we predict a point correctly or not。

ok。Okay。So。This expression that we get when we sort of write down the Minm value of the game。

 it's just the minimum over distributions over the data points， over weightings of the data points。

Of the maximum over hypotheses。😡，Of the weighted accuracy of the data sets under that weighting。

And remember。Like。What was the object we were given it was a weak learning algorithm and what a weak learning algorithm promised was exactly that。

No matter what weighting of the data set we were given。

It would produce a hypothesis that does a little bit better than random guessing。

That predicts a little bit better than a coin flip that gets accuracy 51%。Okay， so in particular。

 for whatever waiting the data player chooses to play if they go first and tell it to us。

One way we could imagine。Responding to that was by just feeding that weight vector into our weak learning algorithm and the weak learning algorithm has the promise that it will give us a hypothesis that has weighted accuracy at least 51%。

 and so the min max value of the game can only be bigger than that。That makes sense。Okay， so。

We've written down this game， and。We're curious about the value of the game。

It's often easier to think about the value of the game。

In one of the orderings of play compared to the other。

We've chosen to think about the ordering of play in which first we're given a distribution over the data and then we get to pick the hypothesis。

And。You know， we can think about the weak learning algorithm as basically a best response。

Orracle in this game， it tells us given a distribution。Overact of the data player。

 how should we pick a hypothesis that has high accuracy that maximizes the accuracy in this case。

 the cost in the game？And it's at least 51%。Could we have a weak learning algorithm。Makes sense。Okay。

So。You know， if the adversary goes first and tells us aing。Over the data set。

 you know the learner in this game can best respond and get predictive accuracy at least 51%。

You know， that's not really how we're interested in playing the game。

 we want sort of ultimately a learning algorithm that sort of always does well。

But what the Minmax theorem tells us is that。Well， the min max value of the game is equal to the max min value of the game。

In a zero sum game， it doesn't matter who goes first。So in this case， in particular。嗯。

That means we can reverse the order of play， we can say， okay。First。We can imagine the learning。

 you know， the first we can imagine the learner having to commit to a mixed strategy。

 which in this case is a distribution over hypotheses。

After the learner has committed to this distribution over hypotheses。

Data player can pick a single data point。Can pick the worst data point for this distribution of our hypotheses。

 the one that minimizes expected accuracy。So then the data player picks the data point that minimizes in expectation over the mixed strategy of the learner。

The probability that the learner's hypothesis gets the answer right。Okay。

 that's just the game described with the order of play reversed。First。

 the learner commits to a mixed strategy， which is a distribution of our hypotheses。

Then the adversary best responds， like pick a data point and。

The value of the game is the same in this ordering as it was before。

 so if both players play optimally the learner has。A distribution such that for every data point。

For at least 51% of the hypotheses under the learner distribution， that hypothesis gets the answer。

 correct。Okay， so just saying that。Again。There is a fixed distribution， let's call it P star。

It is the。Max Min strategy for the learner in the zero sum game we've just defined。

That has the following properties。So first of all， like what kind of object is this？Well。

 it's a distribution over hypotheses like if our weak learner outputs。Decision trees。

 this is a distribution over decision trees。And the property that it has。

Is that for every single in instance to say max min value right it's promising something in the worst case for actions of the adversary in this case actions of the adversary correspond to data points and so the promise is for every single data points in our data set。

At least 51% of the probability mass。Of P star， this distribution over hypotheses is put on hypotheses that predict the correct label for this data point。

That's true for every single one of the data points。ok。哦。You know， this was like an important switch。

But。All that's the way we're doing it is we're just applying the the minim there。

And the min Max value of any zero sum game， including this one is equal to the max min value。Okay。

 so so just to like emphasize the switch， this is where all the action is happening。

We went from the weak learning statement， which said。For every weighting of the distribution。

There exists a hypothesis that gets 51% of accuracy。

To this reverse statement that says there is a single weighting of the hypotheses。

 there's a single distribution over hypotheses that for every example gets 51% accuracy。😊，ok。😊。

That's what happens in this case when we switch the min and the max。Does that make sense？Questions。

If I'm slipping a fast one by you， it's here。Ask questions。Yeah。😊，Yes。

 so what we now have is like a randomized way of coming up with predictions right so like each of these hypotheses。

 they map images to predicted labels， hot dog or no hot dog。

But now what I've got is like it's a mixed strategy for the learner so it's a distribution of a hypothesistheses。

 so for every example it maps to like a distribution of predictions。

 some fraction of them predict one， some fraction of them predict zero。😊。

And the claim is that for every example， at least 51% of them。Predt the right answer。Yeah。有。一。不是。对。

Yeah， good question， right。I mean， yes， right， so as described， this only makes sense if。

In principle， it is possible to。Correctly label examples。 I mean that in fact。

 what what's theorem we're proving right theorem we're proving is that。

The theorem're in the middle of proving is that if you give me a weak learner。

 then I can give you a strong learner which gets perfect accuracy and of course that's not possible if I have two examples that are observationally equivalent all of the features are the same but they have different labels because if I get one of them right I'm going to have to get the other one wrong and vice versa。

You can extend all of that to this case， but yes， and the way I've defined everything。Yeah。

 this only makes sense if。You never have the sort of exact same feature vector with two different labels。

And in high dimensional settings， that's generally the case， you know， like there's a lot of。

Even though hot dogs all look kind of similar， like if I take a you know。

 picture of a hot dog with my phone， like actually there's quite a lot of pixels and it's you would never see exactly the same image twice。

 yeah。So why before。Like the burial piece age， How does that do。啊。把呢个 change啊。Oh。

 so when we were looking at the min Max value， we were looking at the expected cost over the mixed strategy of the data player。

 the mixed strategy of the data player is a weighting on the data points， we call those W。😡。

Here we're looking at the expected payoff in expectation over a mixed strategy of the learner。

The mixed strategy of the learner is a distribution over hypotheses I'm calling that P。Yeah。第三者。

there's a good。我道。At this at。聊。Re did I think we。Yeah。

 so basically like I'm not going to talk about this。

 but but that is exactly how you fix this problem of there might of there not being a perfect classifier because they're being like mislabel points you would sort of。

Limit the data player to having to play distributions that are like。

Not too concentrated on any single data point and you can do all of that。

 but there are variants for the polynomial weights algorithm， for example， that。

That do that that guarantee they don't focus too much weight on any single point that is in fact how you solve this problem of they're not being a perfect classifier。

But we want to talk about that。Good question。So all of this， but yes。But maybe at the table。

 the assumption is that bus all the。Takeness in the hypothesis plus to few。Right。

But are there any bound。What the。不吧。One link。The case where ofrs。No。我然。Yeah。We要不要的或。不然不理。是。

I didn't quite understand the question， but is it about difference between data points in the data sets versus data points not in the data set？

Garanteed that at least 51% of the。Following us。Rebly。That I said， it's very kind。128。啥手。Well。

 this like。The assumption that went into this was the weak learning assumption。

This follows just from the Minm Max there。The weak learning assumption， the way we stated it。

Was an assumption for a particular data set。So it said on this data set。

 you have a weak learner if for every weighting of the data points。

 you can get better than 51% accuracy。O。So。Consider the following clotsifier。Okay， like by the way。

 like so far， we haven't said anything that sounds like strong learning like we've we've gone from a distribution over data points to a distribution over hypotheses。

 but like the accuracy numbers we're talking about are still 51%。However。

Consider the following classifier。Right， suppose。I compute this vector P star。

 this distribution number hypo policieses， I can do that that's just the min Max equilibrium strategy for this game for the learner。

I'm going to use。This probability of vector， this distribution of our hypotheses to define a majority vote classifier。

What am I going to do？Well， given an example， X。I'm going to compute。

What fraction of the probability mass？Under this distribution。Predict that X has label 1。

And what fraction of it predicts that x has label zero？

And I'm going to take the weighted majority vote we've seen this before in the weighted majority algorithm。

So if more than 50% of the probability mass under this distribution predicts label1。

 then I will predict label1。Otherwise， I will predict label zero。Okay。

 weighted majority votes where the weights come from the Min Max equilibrium strategy for the learner in this game。

The classifier makes sense。Then the claim is that。This classifier that takes the weighted majority vote over a bunch of weak learners。

This must be a strong learner， must have perfect accuracy。

Each H is in the hypothesis class of the weak learning algorithm。Yeah。

So let's just observe that like and just to be clear。

 like we haven't given an algorithm yet so far we're just analyzing like things existentially like we don't know how to like compute this just yet。

 we'll get there。But。Let's just observe that this thing must have perfect accuracy and that follows pretty immediately from。

The sort of minm guarantee。Right because the Minm guarantee was that for every data point。

 51% of the probability mass under of the hypoes under this distribution predicted the right label。

 and we're just taking the weighted majority vote under this probability distribution。Okay。

So the claim is。If we take the distribution P star。

 that is the max equilibrium strategy for the learner in the zero sum game。

 and then we compute the classifier that takes this weighted majority vote。It's got perfect accuracy。

Okay， I'll come。Well， let's fix any data points。😡，We need to show that this weighted majority vote classifier predicts the label correctly。

Well， we know from our Minmax calculation in this game。That for every data point。

The fraction of the probability math。That's put on hypotheses that predict the correct labels at least 51%。

So if the label is one。That means that the fraction of the probability mass that predicts one is at least 51% and our classifier just thresholds at 50%。

 so we predict one， so we're right。And similarly， if the true label is zero。

 it must be that the fraction of the probability mass that predicts one is at most 49%。

 and we threshold it 50%， so we predict zero and again we're right。So we're right on every exam。

That's it。😊，Okay。So。Okay， what have we done so far， we've proven that。

The existence of a weak learning algorithm is equivalent to the existence of a strong learning algorithm。

 if it's possible to predict with 51% accuracy on any distribution number data points。

 then it's also possible to predict with perfect accuracy。

On the same distribution is it on the same data set。嗯。But like what's the efficient algorithm。

 I claimed something stronger than that， not just this existential equivalence。

 but actually like a computationally efficient reduction that if you give me a weak learning algorithm。

 I have a computationally efficient， strong learning algorithm。

And one thing you might worry about is that。Yeah you could say like we know how to compute the equilibriumria of zero sum games。

 all we need to do to compute this threshold strategy is to compute the Minm equilibrium strategy for the learner。

But the learner has a ton of hypotheses potentially right like suppose the learner。

 suppose I have an efficient weak learning algorithm。

 what it's doing is you know somem heuristic for learning decision trees。Well。

 in this game I just defined。Like the action space for the learner is the set of all decision treess that's enormous right so like this is a huge game。

 it's not at all obvious that I can just like compute the equilibrium strategy for this game。

But of course， if you give me the equilibrium strategy。

If you give me this distribution of hypotheses， at least if it doesn't put weight on too many different hypotheses。

 then。The strong learning algorithm， is' simple to compute， it's just this weighted majority vote。

So the algorithmic problem。Is to compute an equilibrium strategy for the learner in this zero sum game we've just defined using。

Only a small number of calls to our weak learning algorithm as a subroutine and hopefully it'll generate for us a weighting of the hypotheses that puts zero weight on most of the hypotheses so that computing this weighted majority vote isn't too hard I just you know I only want to have to enumerate like a small number of things。

Okay， so that's what remains。Yes。好的。Oh because what was this thing it was just it was just the way the majority vote so I just you know。

 if you， if you give me this vector that puts a weight on each hypothesis and maybe also。

It only puts a positive weight on like a small number of hypotheses。Then what do I do I just compute。

😡，For each of the hypotheses， this thing puts us positive weight on the prediction of that hypothesis。

 and then I just like sum up the weights and I see it's you know if the weights on hypotheses that predict one is greater than 51% or not。

So the hard problem， it seems is computing this like P star that。

Is like an equilibrium strategy and doesn't put weights on too many different hypotheses。Yeah。

That's right。Yeah。And in fact， if you sort of think about the argument， right。

 like the value of the game is like 51%。But like。When we， when we argued that。

Our costifier had perfect accuracy， but it was like thresholdholding at 50%。

So there's like a little bit of slack between 51% and 50%。

So we don't actually need to compute an exact equilibrium for this game。

 it's enough to compute an epsilon approximate equilibrium for Epsilon less than 0。01。

We just need that on every example， you know， strictly more than 50% of the weight is on hypotheses that produce the correct。

Label。And so we know how to do things like that。Right， like remember。

We studied like learning dynamics in zero sum games and we proved they converge to approximate。

Equiilibri and zero sum games and there were a few ways to do it， right？Ultimately。

 all we needed to do was simulate play of the game so that both players had。Regt less than epsilon。

So one way we could do that is we could have both players play the polynomial weights algorithm。

That would be okay for the data player because， you know。

 like he only has to maintain one weight for every data point。

 he only has an actions in this game if the data sets subsize n。

 but that would be like a huge pain to do for the learning player or the learner because。

His action space is potentially enormous， one for every a decision tree youd have to maintain a ton of ways。

But there was another dynamic。That led to both players having。No regret。

 this was actually the dynamic we used when we proved the minimax theorem。

 which was to have one of the learners play one of the players in the game play the polynomial weights algorithm。

And the other one。Every day to look at。The mixed strategy of the polynomial weights player and to then best respond to it。

One player plays polynomial weights， the other player plays best response。

This also leads to both players having their regreted。

 this is actually how we proved the minmax there。And。So。

We can have the data player play polynomial weights。

Just maintains a weight vector over the endpoints in the data set。Have the learner play best Re。

And we know how to have the learner play best response， we run the week learning algorithm。

And so the algorithm。It's something we've seen before。We just simulate play of this game。

To compute an epsilon of approximate equilibrium with polynomial weights。

 how many rounds do we need to run for？Well， just log in over Epsilon squared many rounds。

And epsilon here is a constant because we only need epsilon to be less than 0。01。

 So we run this dynamic for only log n many rounds。The data player is playing polynomial weights。

 they're maintaining a weight vector over the data points。N data points。

 a weight vector of length to N。Every day。The learner。

 they best respond to the mixed strategy implied by the data player's polynomial weight distribution。

How do they do that， or they just run the weak learning algorithm on the data set given the weight vector from the polynomial weight algorithm。

That gives us our best response。Which means for every action of the data player。

 we can compute the loss。That's just the indicator of whether this round's weak learning algorithm misclassified the example or not。

That's why we need to update the polynomial weights algorithm， this loss vector。And then at the end。

 what is the thing， what is the object that is the approximate MinmAC strategy for the learner？Well。

 it's just the uniform distribution over the hypotheses played by the learner over the course of this algorithm。

So it's just like a uniform distribution over these hypotheses Ht。

This is a distribution over hypotheses that happens to be sparse that happens to put weight on only。

Log n over epsilon squared many hypotheses because every round the learner played one hypothesis and we're just output there's only log n over epsilon squared many rounds。

 so this distribution over hypotheses we output at the end。

 weight on it puts weight zero on almost everything。

It only puts positive weight on log n over Epsilon squared many hypotheses。

Those hypotheses that were run were produced by the weak learning algorithm over the course of the run of this algorithm。

Okay， so the algorithm is just。Wait the data points。Round the week learning algorithm on them。

Reweight the data points using the。Polynomial weights update rule， run the week learning algorithm。

 repeat for log n rounds。Output in the end， the equilibrium strategy that corresponds to the uniform distribution over the hypotheses output by the weak learning algorithm。

是可以的。Right now we like。Like just what the name。Yes。

 so what this outputs right is an approximate minm strategy for the learner in this game awaiting over hypotheses and remember。

Our final strong learner is just a majority vote。Over this waiting。Okay， so like actually。

 we just get a list of log n over epsilon squared many hypotheses。

 just the list of hypotheses output by the weak learner while we were on this algorithm。

Right so our waitinging is actually just， you know uniform over this list and so our final。

Majority vote classifier， all we do on a new example is we feed the example into every one of the log n hypotheses output in this list and if  you know if at least 50% of them predict one。

 we predict one， otherwise we predict zero。So it's actually an extremely simple。

Prediction rule at the end， it's just a majority vote over the login hypotheses output by the weak learning algorithm in this dynamic。

对。一对。The weak learning guarantee is that when we run。Our weak learner。On you know， here the。

Classification accuracy as measured by， our weighted classification accuracy。

 as measured by the weights we plugged into the learner is 51%。

 at least a little bit better than random guest。Okay， so each of these hypotheses was good。You know。

 a little bit good for the weight vector that we use to generate it。

 not necessarily for the for any other weight vector。Okay， the algorithm makes sense。

So this is a computationally efficient algorithm。Since we only need an epsilon or approximate equilibrium for like a constant value of epsilon。

Our data sets sub size n， this algorithm runs from log n iterations。At each iteration。

 we make only a single call to the weak learning algorithm。

We have to update the polynomial weight distribution。

 which is a weighting over end data points that takes linear time。

And so if the running time of our week learning algorithm is R ofA。

We've just given like a wrappper algorithm that calls it as a subrtine a small number of times the running time of this algorithm is only log n times the running time of the week learning algorithm plus n。

 the overhead of updating the。Waits。Okay， so if the weak learning algorithm was computationally efficient。

 so is the strong learning algorithm。O。And sort of briefly again。

 to mention sort of the statistical aspects of this。Remember like it， you know。Really。

 if all we wanted to do was predict the labels in the training set we could have just written them on our hand right like that's not hard the the thing we really want to do is predict。

Labels， for examples， we haven't seen before drawn from the same distribution。

And I sort of waved my hands and said， well， you know， like if you took a course in learning theory。

 you'd sort of learn all sorts of theorems that had the form。

If you can make simple predictions that are accurate on your data set。

 they're also accurate on new examples drawn from the same distribution。Okay。

 so somehow generalize it， you know， squinting your eyes a little bit。

 generalizing to unseen data happens for free if the rule you learn is simple。Now。

We've assumed that our weak learning algorithm is a the distributional version of a weak learning algorithm is that it gets 51% accuracy on new examples out of sample。

 okay， so presumably the hypotheses learned by the weak learning algorithm。

 those are simple in whatever way is necessary for generalization。

And the thing we produce in the end is just a majority vote over log n of these hypotheses。

So like it's not much more complicated right like if the hypotheses in H are simple。

 our hypothesis that we come up with at the end can be described as just。You know， a list。

Of log n of these hypotheses， just a set， even the ordering doesn't matter。And so informally。

The amount of data you need to generalize to new examples for strong learning out of sample is not much more than the amount of data you need just for your weak learner to generalize out of sample because we haven't like the algorithm we've produced has not increased the complexity of our prediction rules by very much。

We started with simple prediction rules， what we come up with is just a majority vote over a small number log in of those simple prediction rules。

 which is also simple。That you can formalize this by using words。Like BC dimension， but。

I won't cover that。Questions。So in the setting in which we analyzed it it is guaranteed to get 100% accuracy。

Now。Oh yeah， yeah， because right our arguments that we got 100% accuracy。

It didn't require that we had an exact equilibrium。

 right an exact equilibrium would get the right answer 51% of the time at least。

ItOur argument only required that we got the right answer more than 50% of the time。

So anything less than 1 。01 approximate equilibrium was good enough。No。

One way to interpret this rather than a positive result is like a negative result like obviously perfect prediction is like super hard so like maybe you know maybe like calling this thing a weak learner was。

Thisleading， right， like weak learning is as hard as strong learning。And indeed。

 like weak learning is as strong as strong learning。

 like putting this universal quantifier there was made it a strong assumption。

 the fact that the weak learner had to get 51% accuracy on every single distribution made that a strong assumption as strong as strong learning。

But our algorithm doesn't actually require that the weak learner work on every distribution。

 it only has to work on the log n distributions that we happen defeated。

And so it makes perfect sense to run this algorithm and see if it works。And in fact。

 it works great that this algorithm is basically what's called at a boost， which is。Okay。Yeah。

 very good very good algorithm it doesn't get perfect accuracy。

 but it very reliably increases the accuracy of。Simple learning techniques。All via game theory。

Normally I see C next class but。This is the last one， so have a great summer。Okay。



![](img/84c186961113b6b351d092f21a530599_3.png)