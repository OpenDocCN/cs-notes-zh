# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p23 NETS 4120_ Algorithmic Game Theory, Lecture 24.zh_en -BV15kLRzTExU_p23-

All right。

![](img/92c0595e1a05838084937907d59081e4_1.png)

So let's begin。So。Um。You know， a theme throughout this course that we've seen a bunch of times is that we've。

Taken problems from mechanism design。And we've sort of reduced them to learning problems。

Of various sorts。Right。Like starting with like the polynomial weights algorithm， which is really。

 you know， like some kind of sequential prediction algorithm， like we use that as a tool to。

Talk about how people playing in say， a zero sum game might converge to national equilibrium or how people playing in a general game might converge to correlated equilibrium。

We you used it again in sort of revenue maximization and。In these other auction settings。

 we reduced tell learning problems right from sort of estimating the revenue of the best fixed price and the random sampling auction just to be sort of bandit learning algorithms that we used in dynamic pricing。

And so for the last two lectures in this course， and there's only two lectures left。

What I want to do is。Think about the reverse direction。Okay， I wantna。

Take things we know about game theory。In particular， the minimax theorem。

And use it to derive machine learning algorithms of various sorts。Yeah。In fact。

 there is a strong sense in which learning algorithms like the polynomial weights algorithm are actually sort of equivalent to the minimax theorem so so we proved the minimax theorem like what we did in this course is first we derived the polynomial weights algorithm and we used it to prove the minimax theorem。

But we could have done the reverse， we could have proved the minimax theorem using its original proof you know the way von Neuumman proved it and then from the minimax theorem we could have derived the existence and even the algorithm itself of the polynomial weight algorithm so there's sort of a very tight duality between the kinds of。

between the minimax theorem， which sort of underlies you know the basics of like equilibrium structure in zero sum games and between the kinds of machine learning algorithms we've been using。

Okay， so I'm not going。so I like one thing I could have done is given a lecture showing how to derive the polynomial weight algorithm for the minimax theorem I'm not going to do that so i'm going to over the course of the next two lectures derive two other learning algorithms from the minimax theorem Okay。

 today we're going to think about how to get an algorithm that can make。Calibrated predictions。

 meaning predictions that sort of behave like real probabilities。

 but when predicting events that are chosen by an adversary for which like there aren't actually and for which there aren't real probabilities。

And and。Next week in our last lecture， I'll show how you can derive what are called boosting algorithms。

 so sort of powerful， empirically useful class of algorithms directly from the mini Maxax theorem and the polynomial waste algorithm。

Okay， so you know， up until this point， we've been sort of game theorists who happened to know a little bit of。

Learning theory now we're going to。You know，T around and see if we can be learning theorists who happens to know a little bit of game theory。

Okay， so let's tell a story about this problem of calibration。嗯。So you wake up。You know， and I。

You check the weather forecast， maybe you turn on the TV or something and there's this guy and he tells you there's a 10% chance of rain tomorrow。

Okay， so。You know， what does this mean like and does this guy know what he's talking about？

like if if you want to like sort of。Think deep philosophical thoughts you can spend a long time actually thinking about。

What this means， you know like the frequentest foundations of probability are sort of about repeatable events if I you know flip a coin100 times。

 what fraction of times in the limit will it come up heads that's sort of the probability of heads。

For an event that only happens once， you know， like what does it even mean that the probability that it occurs？

Is 10%。Suppose the weatherman tells you there's a 10% chance of rain tomorrow so you don't bring your umbrella and then。

It rains like was he wrong， well not necessarily like 10% events that have a 10% chance of happening sometimes happen。

U。But suppose like the weatherman tells you like look there's really in a very deep sense。

 he really in some very deep sense like knows the probability ofs going to rain。

 like the weatherman's story is that every morning before breakfast he receives a phone call from God。

 God says to him like good morning weatherman， here's what I'm going to do today I'm going to flip a coin。

 the bias of today's coin is 10% and you know if it comes up heads。

 I'm going to like cause it to rain and otherwise I won't and the weatherman says all he's doing is he's receiving these morning phone calls from God and then passing the knowledge on to you。

And you are skeptical of his story。And are perhaps looking for a way to falsify it。

 looking for like something like a statistical test to falsify you know。

 this claim that the weatherman has made that that he really knows every day。

The probability it's going to ramp。Okay， so that's sort of the the thing I want us to think about how would you go about like testing？

This weatherman who claims that he knows day by day this like individual probability probability is's going to rain today。

Okay， so let's。Think about this in a simple model。So。We'll call this the weatherath prediction game。

So it's going to happen sequentially because you know days take place roughly one every 24 hours and what happens is every day in the morning。

 the weatherman goes on TV。And。He predicts the probability that it's going to rain。Okay。

 so let's say that maybe he's got some discrete set of predictions。

 maybe he predicts the probability it's going to rain up to like plus or minus like。You know。

 up to like one percentage point of granularity， like he says there's a 23% chance of rain he never says there's a 23。

92865% chance of rain。Okay， so so he commits to a prediction in the morning PT with the probability he says it's going to rain。

And then， you know， at the end of the day， we learn the outcome， we get， you know。

 just like a binary outcome， it ran or it did not。Okay， this happens for two days。 remember the。

The weatherman is asserting that what's happening every day is that the outcome。

Is actually realized by a coin flip whose bias， whose probability of had is exactly PT。

 the thing he said it would be。And what you are， you're skeptical of this。

 you're looking for some kind of like statistical test that would pass the weatherman if indeed he was correctly predicting according to the true probabilistic process。

 you know， like the probability that it rains every day。

 but might have some chance of failing the weatherman。You know， if he's not doing that。

 if he's a faker。ok。So is the problem clear？There's these sort of non repeatable events you don't get to repeat tomorrow 100 times to like measure the probability of rain tomorrow。

Someone asserts to you that they know the probabilities of these events。

And you want to see if there's any test that you can cook up that might falsify that。Claim。

If it's not true。Is that clear？ok。Okay， so the world in which the weatherman says he lives is this。

Every day。The probability that Ray occurs really is what he says it is。Let's say that。

If the weatherman， you know， if the world is as the weatherman says。

 like the thing that the weatherman reports to us really is the true probability of rain。

 not only then is the coin flipped。嗯。You know， and let's call the world。

 let's call if that's what he's doing， let's call him the oracular weatherman he said has some kind of like oracular knowledge of the weather。

 then the test we design should the oraccular weather man should pass the test。

 it's not an interesting test if it would fail him even if he knew what he was doing。And you know。

 in order for it to be an interesting test， it should at least be possible to fail the test。

And so maybe here's like a first cut。At。You know， like a test。

 something we could test for that would at least be possible to fail and that would pass the oraccular weatherman。

Let me call it average consistency。And it's basically just checking that the weatherman's forecasts aren't like statistically biased。

Okay， so the test is pretty simple， I'm just going to like。Average overall T days。

 the probability that he said it would rain over those T days。

 and I'm also going to keep records and I'm going to average over those T days。

 the fraction of the days it actually rained and I'm going to check that they're close。Okay。

 and if they're close。And it should be how close is close。

They should get closer and closer the longer you know， we're measuring the weather man's performance。

Okay， so that would be an extremely simple test。And it would at least be possible to fail it right。

 like if I said every day that it， you know， it's going to rain 100% of the time and it never rained like I would fail this test。

And。You know， not only is it possible to fail the test。

 like the oraccular weatherman would pass the test if you sort of remember the turn off Hing bounds we used to analyze the upper confidence learning algorithm for this bandit learning problem。

 like what it says is sort of like a quantitative version of the law of large numbers。

 what it says is that if every day rain is realized according to a coin flip， with biasP。

 then in the long run， the expected probability of rain will converge to the actual frequency of rain。

So the oracular weatherman passes this test， it is possible to fail this test。

 so it sort of you know maybe meets the minimal。Criteria we've set out here。Yeah。

But this test is sort of too easy to pass can anyone？Suggest to me a way in which you might。

 if you are， if you find yourself in the position of being a weatherman。You know。

 you're going to be fired unless you pass this test away in which you might。

Past this test without having to go study meteorology。Yeah。对，不感。Yeah。

It's an even easier way to do it。A way that doesn't require as much record keeping。

Well 5050 would be bad because if you predict 50% chance of rain every day。

 then like you're going to be screwed unless it infect rains 50% of the time so that's not 5050 is no good。

Yeah。LikeYes。Right。You know， like if that's the test， you can keep。

 you can stay employed without needing to study any meteorology just every day confidently predicts that the thing that's going to happen today。

Is exactly the same as the thing that happened yesterday。Okay， so like if yesterday it did not rain。

 then predict that today there's a zero% chance of rain and if yesterday it did rain。

 then predict that today there's 100% chance of rain and。If you look at。

This test that we sort of impose on the weatherman。

 I mean he's going to pass it with flying colors because the average of his predictions。

Is actually the same thing as the average of the outcomes， it's just off by one。

Like his predictions are equal to the outcomes just shifted over by one。

 and so the difference in these two things， the average of these predictions and the average of the outcomes。

You know， it's at most at most one over t right because you know like。

The sums are the same except for at most one point， potentially。Okay。

 so if this is what we use to test weather men， then weather men can。Yeah。

 they don't have to invest in meteorological training。哎。Now。We might。Okay。

 so maybe this is how we keep our weather men employed and then someone figures out， you know。

 they can use this yesterday weather men strategy and they start。Using that。

 maybe we can come up with like a different statistical test can anyone。Think of a way to like。

Catch out like。This particular strategy， the yesterday weathererman and discover that he doesn't really know what he's doing。

What's something that's going to happen differently for his predictions compared to the real ones？对。

Even simpler。Yeah， like he's wrong in sort of like obvious ways like like he frequently says things like there is a 100% chance that it's going to rain today and there is a0% chance that it's going to rain today and like sometimes he's wrong about that right like sometimes like sometimes he says there's a 100% chance it's going to rain today and then it doesn't rain and sometimes he says there's a  zero% chance of rain and then it does rain and that is never something that happens to the weatherman who knows the true probabilities。

Okay， so like that is something that clearly delineates like the weatherman who knows the true probabilities ones who from the one who does not and so can form the basis of a very simple statistical test that will result in the yesterday weatherman getting fired right like I don't just look at the fact that he's like unbiased on average I look at how frequently it rains when he says there is a 100% chance of rain and I fire him if it's like well below 100% and I look at how frequently it rains when he says there's a  zero% chance of rain and I fire him if it's like well well above0% and that will result in。

You know， the unemployment of the yesterday weatherman。

 but the continued employment of the oracular weatherman。Okay。Does that make sense so like， you know。

 just asking that the predictions of the weatherman be unbiased on average。

Is a you know that's a test that's too easy to pass you can just like predict what happened yesterday。

 but like you know we can think about sort of tests that are more difficult to pass and you know like here's the basis of a test basically that。

That won't be passed by this particular dumb strategy。Okay， does that make sense？Yeah。

And so trying to actually sort of turn this into like a concrete test。You know。

 what we were the test that the yesterday weathererman was designed to pass was just checking whether his predictions were like unbiased on average。

And like the test that actually catches him out。It checks whether he is unbiased。

 not just on average over everything， but like。Conditional on the value of his prediction。

Like checks that he's unbiased， conditional on the fact that he predicted 100% chance of rain and conditional on the fact that he predicted a  zero% chance of rain。

Okay， so instead of you sort of in。Comparison to like average consistency， this simple test。

 let's call this new test that's going to check that he's unbiased。

 conditional on his own prediction as prediction condition average consistency。Okay。

 we're just going to like condition on his own prediction。O。U。Now。

 you have to be like a little careful about this because。

As soon as the weatherman hears that what you're going to do is。Condition on his prediction。Um。

 you know， so you're going to look at all over the days， for example。

 for which he predicted a 90% chance of rain and you're going to check that it rained 90% of the time on those days。

U。Well， you know， like how well would the oraccular weatherman do on this test， Well。

 oraccularrutherman would do quite well if he if there were many days on which there was a 90% chance of rain。

But he wouldn't do very well if there was only one day for which there was a 90% chance of rain because。

You know like。Maybe it didn't rain on that day。And so this test sort of。

Is only going to pass the oracular weatherman if we。

Are more forgiving if a prediction has been made fewer times。And so like the， you know。

 our our weatherman charlatan might start to like get an inkling of an idea and it might say， well。

 you know I'm going to predict like。Crazy percentages to like the 10th decimal point of precision i'm never going to repeat the same prediction twice i'm going to predict you know like a 82。

369518% chance of rain and you know you're going to try to like condition on my predictions but'll you know at every every event you condition on happened only once and I'll say you know like tough luck you know when things that happened only once you know like。

M。will not come out exactly as my prediction。And so just to like stop him from doing that。

We're going to like bucket the predictions so we're going to say。

 look I'm not going to like look at the you know last you know10 significant digits of your prediction。

 I'm going to basically look at your predictions up to plus or minus 1%。Okay。

 so I'm going to like bucket the predictions into 100 buckets， you know， like zero% chance of rain。

1% chance of rain，2% chance of rain， so on and so forth。Okay。

 and we'll just say that a particular prediction which could have。You know， arbitrary many， you know。

 bits of precision is in bucket eye。If it's closer to I over 100， you know。

 I% compared to any other any other point J over 100 okay。

 so we're just going to we're going to make sure there's only sort of 100 distinct conditioning events that we are going to check for。

And so this is sort of going to be。The kind of test we're we're going to think about。

So given a sequence of predictions and outcomes， okay。

 so the weather Mountain says you know 20% chance of rain then we see whether it rains or not then the weather mountain says there's a 60% chance of rain then we see whether it rains or not。

 so on and so forth for tea days。嗯。😊，Let's say that NTI is just the number of days for which the weatherman predicted something in bucket eye okay。

 so the number of days for which he predicted a 30% chance of rain。

 the number of days for which he predicted a 64% chance of rain。O。

And we'll say that the sequence of predictions that he made satisfies epsilon approximate prediction conditioned average consistency for some bucket eye。

If when we average over all of the days for which he predicted。Something in bucket eye。嗯。

Of his prediction。And we average over the same set of days of the actual outcome。

 the fraction of times it rained。Those two things should be close。Okay。

 so we're asking that his predictions average out to the truth， not just marginally。

 but like conditionally on his prediction。Okay， his predictions should be right on average。

 not just overall， but like also on those days when he predicted a 30% chance of rain。

 when he predicted a 30% chance of rain averaged out it should have rained about 30% of the time when he predicted a 73% chance of rain averaged out over all of the days for which he did that it should have rained like 73% of the time。

Okay， does does makes sense。Yeah， it satisfies。If that's true for all of the buckets。

 you're disappointed disappointed。For now， this is a you know。

 we can say it does this for like bucket one and we can say it does this for bucket two。Some that' a。

Okay， so this is basically saying， you know， like on those， for every eye， on those days for which。

The weatherman said there was an 9% chance of rain， like on average。

 it should have rained roughly 9% of the time。Okay。

 so this would fail the yesterday weather ban because。

On those days when he predicts like 100% chance of rain quite frequently。

 it does not rain and on those days for which he predicts a zero% chance of rain quite frequently it does rain。

 even though on average his predictions average out to the truth。Okay。嗯。

And so the idea for it like this。Test I'm going to tell you about in a moment。

 which is called calibration a calibration test is that the forecaster should be correct on average conditional on her forecast so like basically you should have you're going to be like calibrated if you don't have very much。

You know， conditional average consistency error for any bucket。Okay。

 so the basic idea for calibration is to ask for conditional consistency on all hundred of these buckets。

😊，But there is a problem， right？Even again， we need a test that's going to pass the oraccular Weman。

And like even the oracular weathererman would not pass this test for buckets for predictions that he made very infrequently。

Like suppose there was， you know， even though we watched him for you know。

 make predictions over like，10，000 days。Actually， you know。

 like on only one of those days did he predict a 50% chance of rain？And like it ran。Okay， so like。

 you know， then is。Conditional average consistency error would be like bad for the 50% bucket because he predicted you there was only one such day。

 he predicted a 50% chance of rain and then you know no matter what happened either it rained or it didn't。

 you know， the outcome was one or zero it can't fly a half rain。Okay。

 so like if you only predict the 50% chance of rain once。

 then there's like no way on that bucket that any weatherman， including the oracular weatherman。

 could have conditional consistency error like better than 0。5。Yeah。

And so the problem is like we can't actually ask for this。

Average consistency error to be small on every bucket because。

It can't be for buckets that were infrequently used。

But what we can do is we can ask it to be small on average where what we do is we。

Average over the different buckets in proportion to how often predictions were made in that bucket。

Okay， so like， you know， if the weatherman only predicted 50% chance of rain one time， like。

 you know， okay， tough luck on that bucket， it's just impossible to have。

Conditional average consistency are less than 50%， but maybe we'll only weight that bucket。

 you know one over with weight one over t if he only made that prediction on one out of two days and more generally。

We will wait bucket eye。By the number of days for which we made that prediction prediction bucket eye over tea。

Okay， so we'll say that a prediction strategy satisfies epsilon average calibration。If。

No matter what the sequence of outcomes is。What we have is that。

When I average over all of the buckets， okay， all of the100 buckets on days when the weatherman predicts a 1% chance of rain。

 a 2% chance of rain， a 3% chance of rain， etc ce， each bucket weighted in proportion to how frequently we make predictions in that bucket。

And what I'm averaging is the conditional average consistency error in that bucket。

That this quantity。To be small。Should be less than epsilon？And ideally。

 like if we have a good prediction strategy for this。

 epsilon should go to zero as T grows large as it would for the oracular weather ramp。😊。

And just sort of like looking at this condition and like simplifying a little bit。

Yeah we notice that like if we wait bucket I in proportion to the number of times we play bucket eye。

And then we look at the conditional average consistency R in bucket I。

 which is an average over the days on which we played bucket I。

The number of times we played bucket eye cancels out from the numerator here and the denominator here。

 and this measure of epsilon average calibration is actually pretty simple。

It's just the expected value summed over 10 of the buckets。And thumbmed over all tea of the days。Of。

😊，The indicator for whether our prediction at day T was in bucket eye， okay。

 every day we make a single prediction and the error on this day somehow accrues to the bucket in which our prediction lives。

And what are we summing up， well， just the difference between the outcome and our prediction？Okay。

 so this is the same as average calibration error， and we just want this to be small。ok。

So the oracular weatherman， he would pass this test and you can prove this again with like a turn off hoping bound because basically you know。

 like on every， the oracular weatherman has the property that whenever he predicts a 20% chance of rain。

 well like the expected value of the outcome， why actually is 20% that's what it means he's the oracular weatherman。

 and so this is just a statement of the form sort of saying look。

For every the weatherman's flipping a bunch of coins of different bias and for every coin。You know。

 the。Fraction of times it comes up heads is close to its expectation。

 where we allow larger deviations for coins that we didn't flip as many times。Okay。

 so this is some metric that。The oracular Weman would pass。The yesterday weatherman would fail。嗯。And。

 you know。Maybe there are a more clever weather map that would pass。Yes， like yeah。

 I mean could you could do it with like1，000 buckets or 1，000s or 10 buckets。

 but percentage points come in units of one on 100。No， there's nothing magical about the number 100。

Other questions？Okay。嗯。And just sort of like， you know。Fororeshadowing。嗯。

We're going to put ourselves in the place of the yesterday weatherman。

And like he's had his job up until now without needing to learn any meteorology。

 and now all of a sudden you know his employers have gotten wise to his strategy and they're going to like impose this more stringent test。

And the question is， can we keep our jobs without needing to like actually learn any meteorology because we？

Really don't want to。Okay。But in particular。The way we've sort of set this up。Is that。

We could say that a prediction strategy which。You know。

 maybe like an algorithm for coming up with these predictions as a function of the past is supposed to pass this test on any sequence of outcomes。

Even a sequence of outcomes that is generated by an adversary。

 if the sequence is generated by an adversary， there are no true underlying probabilities。Okay。But。

 you know， like if we have an algorithm that can pass this test。

 even when the sequence is generated by an adversary， well。

 certainly it can pass the test when the sequence is generated by nature using whatever meteorological processes we never bothered to learn in school。

Okay。Okay。So like this is the test we've set up for ourselves。Mathematically， it's going to be like。

A little bit more convenient for us to work with the sort of Euclidean version of the metric。

 which will relate to this one， so just to sort of like。Remind ourselves of what this metric is。

 the thing we actually have to pass。We're just like summing up over all of the 100 buckets。

 then we're taking like the absolute value。Of， you know。

 like the sum over all of the days for which we made a prediction in bucket eye of like our bias on that subset of days。

 the difference between our prediction and the outcome， okay， the absolute value of that。

The more Euclidean looking version of this just replaces the absolute value with the square。Okay。

 so it's， you know， so we're just summing up over the 100 buckets of the sum over all of the days for which we made a prediction in bucket eye of our bias on that bucket。

 the difference between the outcome and our prediction。

 but rather than taking the absolute value we're squaring it， which you know。

 has like kind of similar properties， it doesn't allow you know like can't become negative。

But it's a different measure。It's going to be more convenient for us to work with this because。

This is differentiable。But like these things are related to one another by the khi shorts inequality and so you know you can like confirm this at home but。

If I can promise that this metric。Become small。Then I also promise that the metric that my employer is using to determine whether to extend my contract another year is small in particular the average calibration error is going to be at you know the expected average calibration error is going to be at most。

1 over t times the square root of the expected square root calibration error。Okay， so you know。

 basically we can convert between these two things。By taking a square root。And you know， like。

This line is the kshy shorttzs inequality。Okay， so， you know。

 this part's not super important except that like we're going to try to cook up an algorithm to make this thing small。

And the point is that suffices to。If we can do that。

 that'll suffice to make this thing small and will' suffice for us to keep our jobs。O。

Okay and so right， so like from this point forwards。

 we are in the position of like a fraudulent weatherman we know nothing about meteorology we'd like to keep our jobs we're worried that。

You know like。In these times of climate change， weather might have become somewhat unpredictable so we don't want to come up with an algorithm that makes nice distributional assumptions。

 we'd like to come up with an algorithm that can make calibrated predictions no matter what。Okay。

 and just to sort of you calibrated predictions or predictions that sort of behave like。

Real probabilities that have lots of the properties of real probabilities if I look at。You know。

 if I look at the empirical transcript of what actually occurs。

 like the empirical history of what actually occurs。Calibrated forecasts are real probabilities。

 meaning that when I put， you know， like on those days for which I predicted a 20% chance of rain。

 if my predictions were calibrated， the actual empirical chance of rain was 20%。Okay。

 so our task here is to come up with some learning algorithm that makes probabilistic forecasts that appear to be true probabilities。

 even though there's no probabilistic process and the outcomes could be chosen by an adversary。Okay。

 does it problem make sense？O。So here we are， we're this fraudulent weatherman and we've made predictions you know。

 from day one all the way up through day S minus one， you know， like sunk costs， what's done is done。

 I can't change the past， but I'm deciding what I should now do on day S。

Like given what has transpired so far， you know， like what should I do on day S that will have like。

Yeah that will sort of give me my best chance of keeping my job end of at the end of my contract。

And so maybe one thing I should be like keeping track of is for each bucket。

 what is my track record so far？Okay， so let's say that VIS S minus1 is sort of like my track record conditional on predicting an i% chance of rain。

Okay， so it's like， you know？The sum over all of the days for which I made a prediction in bucket eye。

 for which I predicted an 9% chance of rain of the difference between。

The actual outcome on that day and my prediction。So if I'm doing a good job。For every bucket eye。

 this thing should be like about zero。Okay， I should， you know， on average。

 my predictions should have been like correct。For some bucket this thing is very positive or very negative。

 that means I'm doing a bad job， that means that conditional on being in this bucket。

 my predictions have historically been biased upwards or downwards。Okay， so I， you know。

 like I should be getting a little bit worried if for some bucket I， this thing is， you know。

 like very big。Or very small， I should be pretty comfortable if。For every bucket。

 this quantity is close to zero。Ex sense。Now。One thing I can think about is。嗯。😊，You know。

 remember I'm keeping track of sort of my cumulative like squared calibration error。

 I'd like to keep this small。One thing maybe I should think about is。You know。

As a function of what happens today， like suppose I predict an I% chance of rain。

 I make a prediction in the if bucket and the outcome is something， the outcome is YS。

 either it rains or it doesn't。How much is that going to increase my squared calibration loss？

so let's just like write down that quantity。Let's say Dlta of S。

As a function of my prediction and the actual outcome today， I get to choose my prediction。

 I don't know what the outcome is going to be， this is recording how much my squared calibration loss is going to increase as a result of what happened today。

Okay， so it's just the difference between my scored calibration loss after today minus my scored calibration loss before today。

And you know， like if you look at squared calibration loss。

It's the sum over all1 hundred of the buckets。But for each bucket。

 I'm summing up only over the days for which I made a prediction in that bucket。

 only over the days for which I made a 20%， for which I predicted 20% chance of rain。

 only over those days for which I predicted 50% chance of rain。So today。

 when I make a single prediction。I'm going to affect the loss in only one of these buckets。

Like the additional change in calibration loss because of what I did today will accrue only to the single bucket in which my prediction today lay。

Okay， so。What's the change in calibration loss if today on day s， I predict。

In something in bucket eye， I predict the 9% chance of rain， well。

 it's just the difference in my calibration loss within bucket eye， the others are unchanged。

Right so it's just， you know， like what's my calibration loss in bucket I after I make the prediction。

 well it's the sum。Over all of the days for which I made a prediction in bucket eye up through and including today。

Of。The bias of my prediction， the difference between the outcome and my prediction。

 all of that squared。Minus the same quantity， my calibration loss。As of yesterday。In bucket eye。

 the only difference is because it doesn't include today's outcome， the sum is only from day one。

Through JS minus1。Okay， this is the change in my calibration loss as a result of the prediction that I make today if I predict something within bucket eye。

Okay， within the other buckets。Well， you know， if I didn't predict something in the other buckets。

 the calibration loss in those buckets， it's the same today as it was yesterday。Okay。😊，And remember。

 I've you know got this notation now for the calibration loss in bucket eye up through and including yesterday。

 not including today。And so the calibration lost， including today。

Is just my calibration loss in bucket eye up through yesterday？Plus， the additional term。

But comes from today's outcome， the difference between my prediction and the outcome。

All of that squared。And the calibration loss in， you know。

 the squared calibration loss in bucket eye， as of yesterday is just this V。Term。

 my calibration loss。That I've kept track of in Buck eyee。As of yesterday。

 without the new term from today， squared。Okay， so this is just my change in。

Caallibration loss because of what happened today if I predict something in bucket eye。Okay。

Now this is something we can simplify a little bit， so right we can expand out this square。Right。

 and what do I get？Well。There's going to be a VI squared term that's going to cancel out with the one I'm subtracting off。

And what I'm going to be left with is like the cross term two times my calibration loss in this bucket as of yesterday times。

Today is increase in calibration loss， YS minus PS。诶。Plus。

 the square of the difference between today's outcome and today's prediction。

 I don't know what that is， but you know。The outcome is zero over1。

 the predictions between zero and1， so whatever it is， it square is at most one。Okay。

 so I can upper bound the increase。In my calibration loss， because of today's outcome。

The increase in my squared calibration was because of today's outcome。

 if I play something in bucket I。By twice。My calibration loss in Buck eyee as of yesterday。

Times the difference between the outcome and my prediction plus one。ok。So， you know。

 as a function of what I play and as a function of the outcome that's realized by nature or by the adversary。

 my increase in calibration loss cannot be bigger than this。

so maybe I'd like to figure out a way to play to guarantee that this is small so that my calibration loss can't increase too quickly。

Does that make sense？Okay。So yeah， like that's going to be the strategy that we're going to take in trying to derive this algorithm to keep our jobs without learning anything about meteorology。

Right。We have this expression bounding the increase in our calibration loss。

We're going to try to think if we have like an algorithm that will guarantee that no matter what the adversary does。

 no matter what。The weather it turns out to be right， whether it rains or not today。

That the increase in our calibration loss is small。

 and the way we're going to control that is by trying to make sure that the right hand side of this upper bound is small。

Okay， and just like。If we can promise that every day the expected increase。

 the expected one round increase in our calibration loss is small。

 then our calibration loss can never get very big because our overall calibration loss is at most the sum over all of the days of our one round increase in the calibration loss。

So suppose， for example， we could promise that。The increase in our calibration loss was at most。

2 T over M plus one just to pick a number out of thin air M remember is the number of predictions we make。

Well。Then our expected squared calibration loss。Would be just the sum over all of the rounds of the expected one round increase in our squared calibration loss。

Well， there's T such rounds and if。At every round， the expected increase is at most2t over m plus one while then you know the overall。

Caallibration loss will be at most t times this， so it'll be on the order of t squared over m plus t。

嗯。And remember the actual average calibration loss that。You know。

 our employer is evaluating us based on it's not this squared calibration loss it' this。

Absolute average calibration loss， but that's bounded by the square root of our squared calibration loss over t and so that's going to be something like one over root M plus one over root t。

M is the number of distinct predictions we can make。And so if we。

Allow ourselves to make a number of distinct predictions that grows with T。

 then we can make our calibration loss go to zero at the rate of one over root T。

which is the same as the oracular Weman would have been able to obtain and if I flip t coins。

 then the deviation of the empirical average of the outcomes from their expectation is on the order of one over root T。

Okay， so like think about like suppose we've got the oraccular weatherman。

 God calls them up every day and every day it's actually a coin flip like every day。

God says there's a 50% chance of rain。So every day the weatherman predicts a 50% chance of rain。

 but you know it won't actually rain on exactly half of the day it'll rain on something like half of the day plus or minus one over root t one over root t is sort of the。

Tightest value of this test that you could use that would still pass the oracular weatherman and what this is saying is you know if we were able to prove that there was a strategy that you know this fraudulent weatherman could use that would guarantee that。

His increase in squared calibration loss was as small as this。

Then he could pass the same calibration test that the Oracular weather man could pass。Right。Okay。

 so that's going to be our goal。We're going to try to come up with like an algorithmic strategy for this fraud。

To try to figure out what he should predict the chance of rain is tomorrow as a function of what's happened so far。

And the guiding principle of of our strategy is we're going to try to make sure that。This term。

I's guaranteed to be small in expectation， this upper bound on how much the squared calibration loss can increase。

And here we are in an algorithmic game theory class。

 so we're going to try to do it by thinking about zero sum game。Okay， so at every round F。

We're going to define a zero sum game that we'll use to guide the learner strategy。

So the learner here， remember the learner is， you know。

 this fraudulent weatherman is making a prediction every day。

 the strategy space for the learner will be the set of predictions that he might make， okay。

 discretized at some granularity1 over M。So he might predict that the chance of RA is one over or two over or three over。

 all the way up through one， that's his strategy space。The learner is the minimization player here。

The adversary。Okay， this is God， God gets to decide every day whether it rains or not。

Is the maximization player the adversary would like。

The weatherman to get fired because the weatherman doesn't actually know anything about weather。

 which is an affront to God。And the strategy space for the adversary is， well。

 whether it rains or not， zero or one。And the cost function。

This function that is a function of the adversaries。

Prediction and the actual outcome that the learner would like to minimize and the adversary would like to maximize。

Is just。This upper bound that we proved on the increase in calibration loss。

The one round increase in calibration loss， if the learner predicts P and then the outcome is y。Okay。

 so the cost function is just twice the。Value so far， twice the。

Historical calibration loss in the bucket corresponding to the prediction。Made by the learner。

Times the outcome chosen by the adversary minus the prediction made by the learner plus one this was what we proved was an upper bound on the increase in。

Caallibration error of the learner。So。If we can prove at this point that the value of this game is sufficiently small。

 remember the value of the game is how well the learner can guarantee by playing a Min Max equilibrium strategy。

That would imply that there exists an algorithm the learner could play that in particular just plays every day the Nash equilibrium strategy of this game that guarantees that the increase in calibration loss every round is small。

 which will guarantee that he's not fired on the basis of a calibration test at the end of the day。

Okay， so let's figure out the value of this game。Now。

 remember what the Minmax theorem tells us about zero sum games is that the order of play does not matter。

What's actually happening in matter of fact， when we're trying to design like an algorithm for the prediction player for the learner that has to do well against every adversary。

 is that the learner is committing and announcing their strategy upfront。

The learning algorithm that they use is their strategy it determines what their distribution on predictions is going to be every day。

And if the algorithm has to perform well against an adversary， well。

 adversary might know their algorithm and so has to perform well even against the adversary that is best responding to their prediction strategy。

So what's really happening in the situation we're analyzing is the learner is committing to their mixed strategy first and the adversary is best responding。

 and we're interested in how well the learner can do。

But the Minmax theorem tells us that when analyzing the game。

We can imagine that what's happening is the reverse。

Because order of play does not matter in a zero sum game。

 that is the statement of the Min Max theorem。So we can imagine when analyzing the game。

But the adversary goes first。Now what does it mean that the adversary goes first？

It means that every day the adversary commits to and announces。

The probability that it's going to rain today。And only then does the learner need to make their prediction？

And it is so much easier to predict the probability it's going to rain if someone has already told you the probability it's going to rain。

And that is what's happening in the world in which the adversary goes first。

The advers mix strategy is just the probability that it's going to rain。

When the adversary goes first， that means you are told at the beginning of every day the probability is going to rain。

 and then only then do you need to come up with your prediction？So when the adversary goes first。

 you as the learner actually are the oracular weatherman。

You've been told before the outcome the probability it's going to occur。And so。You know。

 knowing the mixed strategy of the adversary。The expected cost that the learner will incur in this game if they predict P。

Is just twice the historical calibration loss for the bucket that prediction P lies in？

Times the difference between， well， not today's outcome anymore since we're taking expectations but。

The probability that it's going to rain today。Minus the prediction。

 minus the predicted probability it's going to rain today plus one。But if I know Q ofs。

 if I know the probability is going to rain today。That's a really good prediction to make。

I should predict Q of us， and that'll zero this out。Now there's you， not quite so fast。

 I can't predict Q of S exactly because remember I don't have， you know。

 in order to have the Minmax theorem apply， this had better be a finite game。

And so I didn't give myself the ability to predict。Arbitrary probabilities to you know。

 arbitrary decimal precision， my strategy space corresponds to predictions that are multiples of1 over M。

For M that I get to choose， so I can predict one over M2 over M3 over M。

So I can't just predict exactly to decimal precision， the probability that it's going to rain。

But what I can do is I can choose the prediction in my action space that is closest to the probability it's going to rain。

And since my action space corresponds every prediction between0 and1 up to this discretization of1 over M。

 I always have a prediction that is within one over M of the true probability is going to array。

And so the maximum value of the game。meaninging。If the adversary goes first and picks a probability that's going to rain。

I get to look at that probability and I get to best respond。The maximum value of the game。Well。

 you know？It's at most the。Maximum of the。Caallibration loss I've experienced so far in any bucket。

Times 1 over m， so I can make this as small as1 over m plus one。

And the calibration loss in any bucket， it's just a sum over t rounds of number bias terms that are between minus1 and1。

 and so it's at most 2 t over m plus1。Okay， which is what we wanted it to be。诶。In order to guarantee。

That we do as well as the oraccular weather forecaster。Okay。

So that was the maximum value of the game。😡，The minimax theorem tells us that the Min Max value of the game is the same thing。

meaning。If we have to go first and first commit to a distribution over actions。

 and then the adversary can pick whether it rains or not in a worst case faction to sort of cause our calibration loss to increase as fast as possible。

Well， that's bounded by exactly the same thing， also 2t over m plus1。And so in particular。

 like we don't know what it is yet， this was like a non constructive argument。

But we know that at every round S。The learner actually does have some strategy， P of S。

 the min Max value of the game we defined at round S。That guarantees that。Simon， you know。

 like no matter what God decides to do today， whether God's going to make it rain or not。

 the increase in our calibration loss and expectation over our own randomness will be small。Okay。

And so we've proven the following theorem。嗯。😊，There's an algorithm， there's a prediction strategy。

That doesn't have to know anything about meteorology in particular。

 like it works against arbitrary sequences of outcomes that might not follow any probabilistic process at all。

And nevertheless， is guaranteed to satisfy epsilon average calibration for epsilon going to zero at a rate of1 over root C。

 which is the same rate that the Oracular Weman would have obtained。Now so far。

 we don't know what this algorithm is， like we've just argued for its existence。

 like non constructively using the inm there。But。Like we sort of know what the algorithm is。

The algorithm is to every day play the equilibrium strategy of the learner in the zero sum game。

So what is the algorithmic problem that we need to solve？Well， it's just， you know。

 we have this particular zero sum game that we cooked up at every。

Round of this prediction interaction。What the learner needs to do is to compute the equilibrium of that zero sum game and play according to that equilibrium distribution。

Now we know how to do that。Because we've taken this。4120。嗯。In particular。

 like it's not like a very big game， like the adversary only has two actions。

And the learner has M actions， but M doesn't have to be that big， it's like T rounds。

And so if we wanted to， we could just like solve of this with polynomial weights。

We know how to compute des or some games。But in this case， like。You know， so like。

You can derive all sorts of stuff。So far， in the pattern of what we've done so far。

 know like you could you could derive the polynomial weights algorithm itself sort of in this way。

And you know， you can always like end here you can be like， all right， you know。

 we need to play the equilibrium of some zero， some game like we know how to do that， you know。

 just solve it。But。In this case， there's actually sort of a。More efficient direct solution。

 like the equilibrium strategy has like a very simple closed form， it turns out。

 so we can actually by thinking about the equilibrium structure of this game come up with like a concrete like commentatorial algorithm to solve this learning problem。

O。So remember what we need to do。We know that the increase in our calibration loss as a result of what we do today and the actual outcome today。

 you know， what prediction we make and whether it rains or not。Is upper bounded by this expression。

Which is like two times some number are historical。

Caallibration loss in the bucket we predict we can't do anything about what that number is。

 it's a function of what's happened in the past。Times。

This linear function of our prediction and the outcome plus one。

And what we're trying to do is we're trying to come up with a distribution over predictions so that。

For both possible outcomes， rain and no rain， the expectation of this quantity on the right hand side is small。

 smaller than risk。And so let's just sort of think this through in cases。

Remember like what are these calibration losses in each bucket。

 it's like the difference between averaged over the days for which we made particular predictions。

 like the days for which we predicted a 50% chance of rain。

It's the difference between our prediction， 50% and the actual outcome。

So it could be positive or it could be negative， right。

 we could be biased upwards or we could be biased downward。So suppose that for every single bucket。

Our calibration error in that bucket is actually positive。Okay， like everywhere we are。

I guess biased downwards。Well。In that case， I claim we should just confidently predict。

That the probability of rain is 100%。we should confidently predict that it's going to rain。

And so like how come well， what's the？Increase in our calibration loss is going to be when we do that。

 we don't know what the outcome is。 We don't know if why is going to be 1 or 0。

But since we predicted like 100% chance of rain。We do know that this term。

 the outcome minus our prediction。嗯。😊，This is going to be negative or at least non positive。And。If。

 you know， if we're in this case， it's because。Our calibration loss in every bucket was positive。

So a positive number times。A negative number is a negative number。

And so that plus one is that most one。Okay， so that case is good。

Our calibration loss is actually even smaller than we needed it to be at most one。Okay。Case two。

 maybe actually like we're biased upwards everywhere。

Maybe all of these calibration loss quantities are negative。In that case。

 I claim we should just predict there's going to be a  zero% chance of rain。

We don't know if it's going to rain or not， but this term。

 the difference between the outcome and our prediction is going to be non negative。嗯。

And so like a non negative number， you know， like a positive number at times。A negative number。

 right we've assumed that the calibration loss in every bucket is negative。Well， that's negative。

And so again， this quantity plus one。YouIt's bounded by one even better than we thought。Now really。

 we don't expect either of these cases to occur， like we don't expect to be biased upwards consistently across all of our predictions or biased downwards。

 consistently across all of our predictions， these are really corner cases。

 like probably for some of our predictions we're biased upwards for other of our predictions were biased downwards。

Okay。So like really case three is like everything these were just corner case。

 some of the you know some of our buckets were biased upwards。

 some of our buckets were biased downwards。But let's think about what that means。Let's start。

At bucket zero。We've got both feet on bucket zero。Now I'm going to put one foot on bucket one。

 one foot on bucket zero， I's take another step forward， one foot on bucket two。

 another foot on bucket one。I must at some point have one foot on a bucket on which I'm biased upwards and another foot on a bucket for which I'm biased downwards。

Because both of these kinds exist， and so there must be a pair that are adjacent to one another。Okay。

 so there's some I such that in bucket I， my calibration error is positive and on bucket I plus one。

 my calibration error is negative。Yeah。Okay， so this is like the case we should expect to find ourselves almost always。

So let's like zoom in on that bucket eye。know if I've got like a positive quantity and a negative quantity。

Then there's some。Raatio in which I can randomize between these two quantities。

So that in expectation I get zero。Right， lets let Q be the probability such that。

If the Q fraction of the time I pick bucket I and a one minus Q fraction of the time I pick bucket I plus1。

 then the expected calibration loss in the bucket that I've picked is zero。

There is such a cue because。This number is negative， this number is positive。Okay。

 what's my prediction strategy going to be？Well， let's， let's let P。

Be the largest prediction in bucket eye。And let's let p prime be the smallest prediction in bucket I+1。

These buckets are adjacent to each other， and I have predictions at my disposal at every multiple of1 over m。

And so p prime is quite close to P P prime is exactly equal to p plus 1 over m。

And so here's my prediction strategy， extremely simple。Today I'm going to flip a coin。

And I'm going to predict P。With probability Q。And I'm going to predict p prime p plus 1 over m。

With probability 1 minus Q。And that's it。It's hardly a randomized strategy at all。

 I'm randomizing between only two things that are like adjacent in this grid。 I'm either predicting。

A 51% chance of rain or a 51。1% chance of rain。Okay。

But what's my expected increase in calibration loss？Well。With probability Q。

It is my historical calibration loss in bucket I。Times the outcome minus p。

And with probability 1 minus Q， it is the expected calibration loss in bucket I plus1。

Times the outcome minus P minus1 over m。Because p prime is just p plus1 over m。But。

Here I am averaging between something times。Q times V。Plus 1 minus Q times V plus1。

And I know that  Q times bi plus 1 minus q times bi plus 1， that's zero。

So like the bulk of this expression cancels out。What I'm left with is just this one over M term that happens to show up in front of the calibration loss for bucket I+1 and didn't show up in front of the calibration loss for bucket I。

 so this term doesn't cancel out。And what I'm left with is just。Twice。

The magnitude of the historical calibration loss for bucket I plus1。Divided by M。Okay， plus one。

And while these calibration losses， they just can't get bigger than tea。

So it said must 2t over m plus1， which is the value of the game。

 so this is an equilibrium strategy for the game。ok。😊。

And it's also a simple combinatorial algorithm to make predictions that。

Have the properties of real probabilities that are calibrated even。

In the absence of knowledge of the probabilistic process that generated the outcomes and even in the absence of the probabilistic process at all。

 the outcomes could have been generated by an adversary。And so the weatherman gets to keep his job。

And so maybe just like reflecting on this。This argument， you know。

 like we focused on this like calibration test， which is a very natural test， you know。

 probabilities should be calibrated。But our argument was not in fact。

 very specific to the calibration tests， right， because what did we do？We wrote down this game。

 and then we invoked the Minmax arguments。That allowed us to analyze the game as if。

The adversary moved first。The adversary moves first。They。Tell us the probability is going to rain。

And so actually puts us in the position of being the oracular weatherman。And so in some sense。

 like for any test。That we could apply the same arguments to， which is a very broad class of tests。

 We didn't use。Many properties of the calibration test。

This is saying that like there is an algorithm。But passes the test if the oraccular other man passes the test。

Because after we switch the min in the max and the Min Max argument。We are the orurcular weather map。

Okay， the Minmax argument in this game is telling us that it's possible to do as well as the oracular weatherman without actually having that oracle。

So it was not specific to calibration tests was。It worked for any test based on bounding sums or averages。

Aimmed at distinguishing the oracular weathererman from a fraud。

 and so it means that any such test that the Oracular Weer man could pass。We too could pass。

 but without any knowledge of meteorology。And any such test that the oracular Weatherman would fail is not an interesting test to determine whether or not we know anything about meteorology。

Okay， and it's because of the structure of the argument。

 like the Minmax theorem is allowing us to analyze the learner as if she is the oraccular weatherman。

And so， you know， this might lead you to reflect on。What we can actually learn。

From empirical tests of probabilistic models， right， like if if we're。Making probabilities， sorry。

 if we're predicting probabilities of things that are repeatable， the bias of a coin。

We can tell if those are right or wrong， we can flip the coin a bunch of times and we can see if it matches the probability。

 but very frequently we make predictions about things that are not repeatable， not just weather。

 but you know when I'm deciding whether to sell you life insurance and at what rates I make predictions about whether you're going to die in the next 12 months。

But like you will or you won't， that's not a repeatable event。

When I'm deciding whether to give you a mortgage， I make predictions about the probability you're going to。

Go into default。Again， you will or you want， I don't just have the opportunity to give you10 mortgages。

Right， like if I'm deciding。U。Whether to you know， release you on bail and I'm trying to predict whether you're going to。

Flee or commit another violent crime or something like that again it's a I might express this in the language of probability。

 but it's not a repeatable event you either will or you want。

And so there's lots of people who are in the business of making such predictions。

For these non repeatable events and what this is saying or， you know， what you might reflect on is。

Whether there's any way we can。Test whether these。Predictions are meaningful or not。

 and what it means that it's always possible to pass any such test without any knowledge of the probabilistic process。

Okay。And so you have until the next class to reflect on that， and I'll see you guys then。嗯。



![](img/92c0595e1a05838084937907d59081e4_3.png)

Oh。