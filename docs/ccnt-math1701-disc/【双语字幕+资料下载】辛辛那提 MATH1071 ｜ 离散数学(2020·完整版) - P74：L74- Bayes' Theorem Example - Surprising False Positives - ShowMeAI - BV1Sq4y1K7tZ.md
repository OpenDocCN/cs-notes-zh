# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P74：L74- Bayes' Theorem Example - Surprising False Positives - ShowMeAI - BV1Sq4y1K7tZ

。Suppose you go to the doctor and you get some routine medical test done。Well。

 there's a couple of different ways that that particular test could be， in fact， inaccurate。

One way is what we call false positives where the test tells you that you're positive for whatevers being tested for whatever disease it might be。

But you're not actually positive， that the test was incorrect to say that you were positive。

We can also have false negatives where the test says you don't have the disease。

 but unfortunately you actually do。So what we want to investigate is what happens if you know that false positive rate。

 how confident are you in the test results that you get。 For example。

 if I imagine a scenario where I've got a 5% false positive rate。

 So that means of all the situations where you don't have the disease，5% of the time。

 it tells you that you do， in fact have the disease。 So then my question to you is this。

 supposeose you've taken a test， you've got in a positive result and you know that it has this 5% false positive rate。

 What then are the chances that， in fact， you've got the particular illness。

Now you might be thinking， well， 5% of the time I don't have the illness。

 95% of the time I do have the illness now is a reasonable first guess。

 but I want to ask you then this。Does it matter how rare the actual underlying diseases， for example。

 if one out of 100 people have it， does that change the answer that you're going to give if it's one out of 10。

000 or one out of a million or one out of three？That's something to think about and also something to think about is。

 okay， I've got a false positive rate， but does it matter if I know what the false negative rate is as well。

 in this case， maybe well say that 10% of the time it a false negative rate and you can start to think that perhaps these things do matter。

 for instance。Of the times where you actually have the illness。If it's got a very high。

 false negative rate。Then you might not always reveal that with a positive test。

 so knowing one you've got a positive test might hide a few cases。So to look at this。

 I want to imagine a sort of specific example where I've actually got 100 people。

 so here we've put up 100 different people。Now， remember， I said1%。

 one out of 100 people are not going to actually have that disease。

 so here we go we have this one person。And then there's 99 remaining。

 And we know that if all of those 99 people were going to go and take the test。

 None of them actually have the disease， but 5% of the time， it's going to give a false positive。

 So 5% of 99 is approximately 5。 So there's going to be this other group of。

Five people who are going to also claim positive。So what we see if we count them up is we have this one person who actually is positive and 90% of the time it would show that they were positive on the test and you get these five other people who are not positive。

 but they test positive because of this false positive problem so really they're sort of six people here and only one out of the six of them are going to demonstrate as having the disease so we can say there's approximately one6 chance that you actually have this particular disease。

However， this is not exactly accurate。 It's not exactly 16。 It's not exactly the 16。

67% that 16 represents because first of all， I said 5%， but there's only 99 remaining things。

 So that's a little bit off。 And then this red dot。 It actually only shows up as being positive。

90% of the time if you were to take a test。 So got little things around the edge is got to deal with。

 but。😊，Approximately one in six chancemps。By the way， one in six chance is way， way。

 way lower than you were probably thinking because you were initially guessing 95% chance and at a 5% fail rate so 95% chance。

 but here I'm telling you it's only about 16。67% far， far， far， far lower。

 and it has to do with how rare the disease is in the general population。Now。

 the way we're going to formally compute these out exactly is with base theorem。😡。

And base theorem is a way to relate different conditional probabilities when I write something like the probability of a given B。

 that's what I mean by this probability of a line B probability of A given B。😡。

This is going to tell me what is the chance that A occurs if I know that B occurs？😡。

What's so powerful base theorem is that。If you don't know that。

 you often know it the other way around， you often do know the probability that B occurs if A occurs。

 and so B there allows you to relate these different conditional probabilities。😡。

So the way I like to think about it is that we know what we have already is one of the two conditional probabilities。

 in this case the one on the right， the probability of B given A。

 but that what we want to get is the other way around the different conditional probability。😡，Okay。

 so what's A and B in our scenario in our scenario。

 we're trying to talk about the probability that you have the disease given that you've tested positive for the disease。

So in this case， our A is going to be that we have the disease and that our B is going to be that we tested positive for the disease。

Okay， so we got to be able to go and put our numbers we've seen previously into this formula。

 but I got to do one little piece of work first。😡，Let's look just at the numerator。 Okay。

 so what's going on on the numerator， Well， this is the probability that you test positive。

 given that you have the disease times the probability that you have the disease。

This is just the same thing as saying the probability if you have the disease and you test positive for it。

 that's what the numer is saying， the probability you have the disease and that you test positive for it。

But what about the denominator here， well， there's actually two different cases， the denominator。

 the probability that you test positive splits into these two cases。

The first is that you actually have the disease and that you test positive for it。

 so that's what we're going to say the probability that you have the disease that you test positive is exactly what the numerator is。

But the other possibility is that you don't have the disease and that you get a false positive and you do test positive for it。

 so that's another way that you can test positive， you don't have the disease。

 but you do test positive。So this denominator， this P of B， I don't have an immediate answer to it。

 but I actually notice the sum of these two different cases。

 the one case is just the numerator and the other case I'll figure out。😡。

So let's expand that an denominator keeping everything else exactly the same And what we're going to get is this formula。

 So on the lefthand side we have that same if you test positive and you have the disease。

 that's the probability of B given a times the probability of A。

 but then on the right hand side what we're going to have is this is the probability that you test positive even though you don't have the disease。

 the sort of squiggly sign means not this is saying the probability that you don't have the disease and you're asking what's the probability you test positive given that you don't have the disease。

😡，Okay， so now you have a formula， this is base formula in the case of two disjoint cases。

 you either have it or you don't， and it separates this denominator into these two different buckets。

 if you will， you can see my previous video for a different example having multiple buckets。Now。

 if we remember all the way back at the beginning where I laid out the statistics for my hypothetical test。

 we said that there was a 10% false negative rate， which means that 90% of the time that you actually have the disease。

 the test says yes， you have the disease so the probability of B given A the probability that you test positive given that you have the disease is 90% so I'm going to come in there and put in a 。

9。Okay， but probability you have the disease， we said one out of 100 people are going to actually have it。

 so this is going to be 0。011%。And then down the bottom on the left hand side。

 remember that was exactly the same so I can just plug that in same numbers Now the probability that you test positive。

Given that you don't have the disease。Well that was our 5% false positive rate so I can come in here and put a 5% in for that and finally。

 the probability you don't have the disease， well if 1% of people have the disease 99% do not so I going to put in 0。

99 and I can compute this out and I get about 15。4% just a little bit lower than the 16 that we sort of reasoned our way we was going to be close to at the beginning。

This is really bad， this is a really small number， or maybe you should think in the case of not wanting diseases is a really good thing that is a small number if you test positive。

For a rare disease， it actually doesn't mean you're that likely to have the particular disease。

 and indeed you want to do multiple tests to be able to confirm this。So what if we do that。

 when we've done one test， it says we're positive， but we only think there's a 15。

4% chance that we're actually positive so let's do this whole thing again。All right。

 so now what I'm doing is the same base formula that I had before Now this changed and the actual formula except。

When I'm calling B has now changed， B is now that I test twice positive in a row。

 I test positive once and then I do it again and I test positive a second time。

 This is going to change a lot of the numbers Some I are going to say the same the probability of A and the probability of not a those don't change so I can come in here and just put those in the same 1% and 99% they were before。

😡，Okay， but what about the probability that you test positive twice in a row given you have the disease？

Well， let's think about it， the first time you take the test。

 you got a 90% chance of testing positive if you have the disease， 90%。

So then if I do it a whole second time， it's 90% of that 90% and since 9 times 9 is 81。

 this gives me 0。81 or 81% of the time So if I if I have the disease 81% of the time the test will tell me twice in a row that yes。

 I have the disease All right， so I put that 0。81 in final thing to figure out okay what's the probability that I test twice positive if I don't have the disease well。

If you don't have the disease， it's only a 5% chance that you're going to test positive。

 that you'll have a false positive the first time。So 5% the first time， 5% the second time。

 so 5% times 5%， this is going to be 0。0025。And I can compute that out and what I get is approximately 77% so I've gone way better。

 I've gone from some about 15% chance of having this particular disease all the way up to a 77% chance of having this disease。

 which still is nowhere near the 95% that you might have initially guessed。

So what's the big takeaway from this， it's the rate of which something occurs in the general population is actually really。

 really important if instead of 1% we put in say one in 10 or one in a million。

 all of these numbers are going to really change that said。😡。

Think about when you might actually get a test so for example。

 if I go in and get a particular blood test， it might be that everybody in the population is getting this particular test。

 in which case the rate at which the disease occurs in the population this 1% we put in here is the relevant thing to consider。

A lot of the time when you get a medical test， you actually know something else。

 you come in with a list of symptoms and those symptoms influence the sort of category of people that you're in。

 So， for example， if you're going and getting a prostate exam as an older male。

 well you don't want to compare to the rate of prostate cancer in for example。

 all males you would want to consider the rate of prostate cancer in males of your same demographic Now this kind of thing is very common in Bay serum because the whole point about Bayesian analysis is that as I learn new things is I get more information coming then I get to update the probabilitybabilities by which I believe events are going to occur that there's a difference between my probability of having a particular disease。

 if I don't do any tests is just one in100 if I take one test which was this 15% or if I take two tests which is this 77%。

If I then update my information even more and I find that I'm actually in some high risk category given my symptoms。

 then my probabilities are going to go up further and further so you need to be always very clear about what your assumptions are and as more information comes in。

 you can adjust accordingly using this Bayesian inference。😡。

