# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P4：-04-Advanced Algorithms (COMPSCI 224), Lecture 4.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

You's going to be the last。

![](img/c1e8d5d5f0f999e494b279db19d96e82_1.png)

Day that's exclusively on hashing。I just want to correct dilemma。

That I stated I guess the end of class or at some point in class last time。

It was related to cuckoo hashing。Well before you do that today。What are we going to talk about today？

So we're going to finish linear probing。And I'm going to show you how you would argue about it with five Y independence。

 it's almost the same proof as sevenYs。One trick that you have to observe。

I'm going to talk about approximate membership。So this is bloom filters。

I'm going to talk about cuckoo hashing。Blue mirror filters。

Which solve a different problem than moon filters well generalization。

I'll say a little bit about like。The power of two choices。And6 is， well。

 I might say some other stuff， okay。嗯。Okay， so before we start with the five Ys， I just want to。

Very quickly recap the seven wise and tell you what the lemma was that I should have said。

 So thelemma that I should have said。 So let's recap。This is for linear probing。Okay。And。

We have an array， so we haveh。To an array。Of size M。And I think I assumed that M was。Yeah。

 like at least let's say2N。Okay。And。We said， L。So let's say I。Eyes and interval。Of。Aray locations。

And then I said， Eli。Is the number of J and the set S S to the set of things that live in。

 the keys that live in our data structure。Such that H of J。Is an eye。It'sThe size of that set。Okay。

And I gave a definition。I said that I is full。Okay。If L of I。Is at least the size of eye？

So then I stated some lemma about the number of probes relating the number of probes that we do in inserting X to full intervals。

Here's ama that should have stated， which I sent by email。 By the way。

 is everyone here on the class mailing list， Is there any， please raise your hand if。

 if you did not receive an email about。Well， about class related things， raise your hand。So okay。

 I guess everybody's on it。 Okay， so if someone's too shy to raise their hand。

 you can go to the class website and there's a link to sign yourself up。Okay。

 so thelemma that I should have said is。If。Inserting。X takes。K probes。Then。H of x。Is contained。

In at least。K full intervals。Each。Of length。At least K。Okay。And the proof of that。

It is you draw the array。H of x goes somewhere。Okay。And some window about this is taken。

Is occupied by items while I'm using。It's just。Some window is taken up by items。

 and then there's a free spot and then also going backwards， some window is taken up by items。Okay。

And the point is that。And this is empty。And the point is that。This interval here， this interval here。

诶。It lands somewhere， so H of x will eventually go there。This interval here。

 including the item X itself， is a full interval。Okay。So if you just take。

 so any prefixed interval is also full。So if you just take the K。

The K different prefix intervals that start with here。 So like this one， take that one。

 take that one， et cetera。 Those are all full intervals yeah。え備や前イ。Well。

 know the thing is you know that this。This here。Has length of K because we're making K probes。

 So what you can do is。Start here and go K to the right。I means， well， start。don't need。

Oh it doesn't yeah， sorry， sorry， this interval doesn't have to be size exactly K。

It can be sized larger than k。So start from the beginning and just go all the way to H of X and then more if you need to to make it length K。

 Do you have a question。えれ的のまま。嗯。Why is it false？everything catches the H of x。

Everything hashees here。No， but then this interval of this interval would be full。Oh。

 I see what you mean。 Oh， yeah， okay， fine。 Okay， yeah， okay， good。 So man。

 So this lem is really causing me a lot of problems。😊，Okay， I see。And okay。

 so what was the purpose of this lemma， The purpose of thislemma was we wanted to say that the number of probes。

To insert。X is at most the number of full intervals。Containing X。Okay。

So this inequality was the whole point of that lemma。And the reason this is true is， in particular。

 like the K different interval intervals that appear in this di lemma。嗯。

Are a subset of all the full intervals containing X， containing H of X。Okay。

And then we carried on from there。And then we said this thing here is at most the sum over all k。

Well， it's equal to the sum overall k from 1 to infinity， the sum over intervals of size k。

 such that H of x is in I。Of the probability that I is full。And this is at most the sum over K。

 the sum over the same kind of I。H of x。Contain an eye of the probability that。

L of I minus the expectation of L of I。Is at least the expectation of L ofI？

Because the expectation of L of I is the size of I over2。Whereas if it's full。

 we know that at least I things landed there。 So it's at least I over too bigger than its expectation。

And then we use the moment method。We can raise both sides to some power。

 reraise it to the sixth power。Yeah。さ緒？modern。I' sorry I say it again。ろ。I'm counting all intervals。

 K is a parameter。I'm counting all intervals。And then this thing。This thing is at most。Some over k。

There are k intervals of length K that contain H of x， So K times。One over so this is I over 2。

So this is K over two。To the sixth times the expectation of this thing。LI minus expectation of L。

To the sixth。Okay。So。I don't want to say much about。How to bound this thing。I mean， well。

 I want to say something， but I'm not going to actually do the computation。But。I'll give you。

 I guess， a useful trick that lets you easily compute those things。

And then I'll leave it to you to execute the trick if you really want to see the final value。

So what is this random variable LI？Okay。So we can define some indicator random variables。 So define。

X1 up to Xn。Where Xi is equal to 1。If H of I is contained in this capital I and zero otherwise。Okay。

 then。That implies that L of I。Is just the sum I and S。OfX of I。Okay。

So now we're looking at a deviation from the expectation。So we want to bound。The expectation。

Of some of we want to bound well， the expectation of X I minus the expectation sum of R X expectation sum of R X to the sixth。

That's what's over there。Okay， so I want to show you a trick。

To show you how to make this thing somewhat easier to manage。Okay。Trick。For such situations。

Is what I'll call symsymmetricmetization。So what's that trick？So I'm going to make a claim。

Which I'm not going to justify， you can look it up if you want， so fact。This is known as。

Benovovski's inequality。Is that。If you look at。Define。For a random variable。

So x is a random variable。Deine for random variable x。The P norm of x。

Is the expectation of the absolute value of x to the P to the 1 over P？Okay。This is a norm。

It obeys the things you usually expect。Like。The norm of A。

 the norm of the scalar times x is the scalar times the norm of x， it satisfies triangle inequality。

 et cetera。So we really want to bound， oh and then one other fact。That I want to state。

It's called Ys's inequality。And it says。If a function。It's convex。Then。F of the expectation of x。

Is that most the expectation of F of x？Oh， this is a norm， I should say， for P at least one。

So the trick。That makes computing things like this a little bit easier。Is， well， you know。

This is the same thing as the sixth norm raised to the sixth power。

 So let's just down the sixth norm。 and then whatever answer you get at the end。

 you'll raise it to the sixth power。So you'll say， look， so I have the sum of our Ixi。

Minus the expectation of some of our IxiI。Okay。And。You might as well imagine that。

 so this is just a number。 This expectation is just a number。

So might you might as well imagine that these Xs inside this expectation are independent copies of the actual excise。

 So Xi prime。Is a random variable that's independent of Xi， but is distributed exactly the same way。

So you get the same thing。This is the same number。And then。You know， you could。

 let's write this suggestively as， you know， I'm not， I'm just， I'm just rewriting where the X is。

 So this is the expectation of。Over the x primes now。Of sum over I X minusxi prime。

And raising something into the sixth power is a convex function。 Or in general。

 taking the absolute value and raising to the P for P at least one is a convex function。

So I can pull this expectation outside。So this is the sixth norm over this random variable。

 but this is at most the sixth norm over both random variables。Okay。So if this isn't clear。

 this here means。Expectation over the x's。Of。Expectation over the x primes。Some over eye。

Xi minus Xi prime。To the sixth。For the one number six。

But taking something and raising it to the sixth power is a convex function。

So I can pull this expectation outside。This here。Can go outside。And it only gets bigger。

 that's Jen's inequality。So that's what I did here。 So this randomness。

 this norm is over both x and x prime are both random。

 And now these are independent symmetric random variables。

 So this is exactly the same distribution as putting in random signs。

These are independent random signs。So I should have said this is Yenssen。And now I use the fact。😡。

That。The sixth norm is norm。So this is at most。Two times the sum over I Sigma i X。Okay。

 so what we've just shown。Is that the original sixth moment that we wanted to bound。

Is bounded up to this two to the sixth power， raise everything to the sixth。

 and then you get the sixth moment。 The sixth moment is at most two to the sixth times the sixth moment of this random variable。

 which is a symmetricatized version of the original one。So this is a mean zero random variable now。

 all these sigma I， all these guys here are symmetric random variables。 And what's the point of that。

So。You know， with the sixth power。And things don't get really that， you know。

 six power is already kind of annoying， but especially if you go to really high powers。

 it gets really annoying。But symmetricization makes things slightly easier because let's look at this Now。

 the expectationation。 remember， what is X I， X I I defined to be。This thing here。So in particular。

 Xi is equal to1。With probability12。Not one half， what am I saying？The size of I。😡，Over M。

 which is let's say K over 2 n。What's the probability you land in an interval。

 you has an interval of length K？In an array of size M。It's this。And equals zero otherwise。

So let me just this， let me call this number。P。Yeah。Yeah。So。Okay， so this really means this。

This means I took this outside。😡，So it's an expectation over both。Okay， there's an expectation of。

Yeah， so this thing here。Is the expectation over x and x prime？Of that thing to the sixth。

 to the one or6。This is this。Does that answer your question。

So now if you want to bound the expectation。Of sum over I sigma I X to the sixth。

You'll expand this out and you'll get a sum over I1， I2。Up to I6 of the exp of。

The expectation of a bunch of sigma powers， Sigma I1， Sigma I2， Sigma i6。Times， the expectation of。

XI1， X6。Okay。And the point here now is。What is the expectation of this thing here？😡。

What is this expectation？I claim the expectation as one of two possible values。0，1， and when is it 0。

 When is it 1。That will certainly make it one， but that's not the only time it will be one。Yes。

 every one of these indices I， so there's I1 up to I6。😡。

It should appear some of these eyes might equal each other， right？😡。

But if you look at the distinct eyes that appear here。

 each one should appear an even number of times。Okay。So， you know。

 the situations are all appear twice or one appears six times。

 one appears4 and one appears two times。 I think those are the only situations。Okay。

And let's that they let's say that they're all the same。 What appears six times then this is。

This thing here is just Xi to the sixth， which is the same as Xi。Because X is only0 or 1。

And so that gives you P。Okay。Or if all of them appear， if there's three guys appearing twice each。

Then you'll get P cubed here。Okay， and then you also have to take into consideration the choices of all these eyes。

 So how many ways are there to choose。Three guys to appear twice each， it's like N cubed。

Time sum coefficient。So。The bottom line is kind of the dominant term is the case where。

This is dominated。By case。Oh。Three distinct items。I'm not going to do the computation。

 but if you actually did it， that's what you would find three distinct items appearing twice each。

And that gives。Well there are N cubed choices of those three items or N chooseose three choices。

 and then you have to take into consideration the permutations that all give the same thing。

So they're n cubed choices， and then you get P cubed， that gives O of N cubeds P cubed。

and remember now。P has a division by n here， so this is O of KQ。If you remember what P is？

And if you go back here。You get to divide by k to the 6。

 So k cubed over K to the 6 is one over k cubed。Times k is whenever over k squared。

And that some converts。O。So you don't have to use this symmetricization。

 It's just a useful tool because it lets you kind of reason a little， you know， combinatorily。

 like the only some the only。Moomials that matter are the ones with even powers。

 And then you can count how many there are， etc cetera， yeah。九八？

Because I want to just say that if you have an odd power。

So you're going to choose some set of six indices。I want to say that。Yeah。

 the only monoials that matter are the ones that have all even terms。All even powered。

 Like every index should appear in even number of times。

 which already tells you that the number of distinct indices can be at most three。

Because each one has to appear at least twice。If you had to consider every single monoial。嗯。Well。

 there are like end of the six choices of I went up to I6。So you know， you get this you know。

 naively， you get into 60 year， you'd have to be like more careful because。

You'd have to reason about things canceling in various places with the expectation that you're subtracting off。

Whereas if you symmetize， that sort of does that for you。The accounting problem is easier。

Does that make sense？You have another question about it， maybe？I guess it makes sense。Nowhere。

So in terms of where it comes from， I guess it's just a trick。

 I mean but in terms of why it's a useful thing to know。Maybe as an exercise。Don't summetize。

 just look at this sum。😡，Go home with this sum and raise it to the sixth power。

And try and reason about what all the monoials give you。 Some will give you positive terms。

 Some will give you negative terms。 You have to argue that there's some cancellation going on。Right。

Whereas with symsymmetricatization。You don't have to worry about that at all。

 Everything you're adding up is non negative。And it sort of automatically counts things the right way。

Yeah， it's just a trick。 It doesn't come from anywhere other than trickery。Okay。

 where was I was up there， I think。没有。Okay， so I mean。

 that's basically it for why seven Y's independence works， right？

Once we conditioned on where once we conditioned on the fact that I contains H of X。The other six。

Random variables involved in a product are still independent。

So one for x and the other for the other six guys， so that's seven y's。mSo。Good， so you know。

 we need to。I claim that sevenYs works。I proved that seven wise works， I claim that five wise works。

 that's actually what was in that paper by Pei Pei and Ruicch。The main trick for them。

The main trick for them to show that。Five wise works is to reason in more careful way so that you don't suffer this K。

Okay。We needed this to be1 over K cubed so that even when that K canceled something。

 we had a convergent sum。So that's why we needed the sixth moment。嗯。Good。

 so we need to get rid of that K。And the point is。We can be a little more clever about。

Union bounding over all these length K intervals that contain。H of x。And let me just say that。

 so I might have mentioned this last time， so pay， pay。And Rujit。I think their original paper was 07。

 but they have a journal version later。Says that five wises。Works， oh， and， you know， just。

 just to make sure we're on the same page here。 What， what did I actually prove， right， I proved。

AndThere should be an expectation here。I proved that。

The expected time it takes to insert the item is a constant。Or just so we're on the same page。So。

By fivewise works， I mean that even if H is only5 wise independent。

 the expected time will be a constant and Perashku and Thorup。I think I mentioned this last time。呃。

s four wises。Is not sufficient。You can come up with a four wise independent hash family such that there's a pretty good chance。

 actually that。The number of probes you'll do is log in as opposed to constant。Okay。

 so what's the peipei argument， Pa pe Ruzicch？Let me give myself some space， actually。

So the pay pay Ro argument。Is as follows。So we have this array here。Okay， I have length。And。

Let's say that's a power of two。We build a perfect binary tree。Okay。Over the locations in the array。

Wow， that's not a power， what am I doing？One，2，34 fives，0，8，9，10，11，1230。17 Oh， okay， yeah。As。

I practiced this on my office and I was really fast but now I'm getting slower。Okay。

 so we pulled the perfect binary tree over this array。And we imagine that every。

Every node in this array corresponds to an interval of。Of memory memory locations。

 namely everything in its sub。O。Remember， we're trying to eliminate that K there。 Basically。

 we don't want a union bound。 We don't want a union bound over K intervals of length， K。

 Wet want a union bound over a constant number of intervals of length K。

That would eliminate that K for us。And let us get away with a fourth moment。

And the basic idea is this。Call。A node。Dangerous。If。At least。Let's say three quarters。

Times 2 to the H。So this is a node at height H items。Hash there。So。系い。Of node。Is H。

So this is height zero， height 1， height2， height 3， height 4。So。The number of locations there is。

Is 2 to the H。 And we're saying that it's。呃。So yeah。

 the height the number of locations is 2 to the H， and we're saying that a large fraction are occupied。

 and what do we expect， how many people do we expect to hash there？Well， if M is equal to n over 2。

 we expect a half to theH。It's a map there。So we're like we're a constant factor larger than the expectation。

Which you can， which you can show happens with。Pretty small probability。

 Let's say this two to the H is roughly K。 You can show using like a K。

 you can show using like a P moment that this would be like whenever K to the P or。呃。

Or P two or something。Okay。So now what's the point， the point is。Oh。

 I really shouldn't have era that sum， so let me just write something up here。So at some point。

 we have this on the board， the expected number of probes。To insert x。

Is that most the sum over all k， the probability that there exists？呃。So that's at most。

The expectation of the number of full intervals。Containing。Containing H of X。嗯。Wait a second。

Have I confused myself again， I really。呃。I wanted to say this is almost the probability that。

There exists。A full interval。Of length， K。Containing。H of x。But that。

That would only work out if these things or at different lengths。Yeah。Okay。

 so adjust dilemma yet again。So just the dilema to say that。So number prime。The the prime is。

K probes。Implies。At least K full intervals。Of。Containing。H of x。Each of different length。

So by a modification of lemma。You can prove this。嗯。And now， this thing。I want to argue that。

To argue whether or not there's a full interval of length K containing H of x。

 we only need to union bound over a constant number of intervals of length， roughly K。Okay。So given。

I of length K。Look at。At least four and at most nine。Nodes。In tree。So， let's say。呃。

Containing spanning。I at level。H minus2。Where。K is in the interval from 2 to the H up to 2 to the H plus1。

Okay， so we， we have this interval of length K。And I'm saying。K is roughly 2 to the H。

 Look at intervals that are roughly four to eight times smaller。'4 eight times smaller in the tree。

 so like two levels below。And look at the ones that span this thing。

 And I claim that they're certainly at least four because they're four times smaller and they're at most9 because。

They contain at least an eighth of the interval， and there might be one leftover。Okay。Anyway。

 they were constant is the point。So。If you want to see an example。Look at， for example。

 this interval。One， two， three， four， five， six， seven， eight。So that would be。Too cud。

 let me go bigger。 so let's look at this interval。So we need to look at the nodes。

That are two levels lower。That contain- so8 is in the range from  two cubed to2 to the fourth。

So H corresponds to three here。So we look two levels lower and look at which nodes fully contain this thing。

 so you only need to consider basically these nodes。There are five of them。

So that's what I mean over here。哎。So。Look at。The first。4。Of these nodes。Okay。

And what I want to say is。These guys。The second these guys。呃。Are completely occupied。

And this guy here。Might not be completely occupied。Okay。But I claim that。

Every guy had to start their hashing from at least here。

 So every guy started his hashing from at least here。So what I want to say。

 so let me call this point A。Everyone。And first four。Paashed。It's a or later。And first four。Contains。

Not least。嗯。Three times 2 to the H minus2 plus1 items。

This is the number of items that hashed somewhere in the first four。😡，Which implies。That。

One of these four。Has。L of that interval。Bigger than three fourths times2 the H minus2。Namely。

 it's dangerous。Okay。So now the point is。If we're looking at intervals of length K。

There are k of them that contain H of x。But they themselves are contained an interval of length。

 2 k minus2。All the intervals。Of length K。Containing。H of x are contained。In an interval。Of length。

2 k minus 2。And if you look at all of these。Intervals and look at， you know。

The first four that you would consider for。The first of the intervals。

 the first four that you consider for the next intervals in this kind of spanning argument。

Kind of the total number of nodes at height h minus2 that you'll consider is a constant。Right。

Are people with me？So that the total。Number of height。H minus two nodes。Used to span。These intervals。

It's some constant。And we know that。If one of them is full。We know that if one of them is full。

 one of these constant guys has to be dangerous。 So it suffices to just argue that。

There are no dangerous people in this range。We just need to show that if none of these constant number people are dangerous。

Then it means that none of these intervals under consideration can be full。So。诶。This a。

Just the beginning。So。嗯。So。If there exists。Full interval。Of length K。Containing。H of x。Then， one。Of。

These O of one。No nodes。Of length。Theta K。Let's say at least camera eight。Must be dangerous。

That implies that the probability that there exists a full。Interval。Of length K。Containing H of x。

Is that most0 of1 times the probability that some length K over8 interval？It's dangerous。Thank for。

Oh， it's about to appear。Okay， so the reason I。The reason the reason。

We call this dangerous is the number of people you expect to land in this interval of length K。

 So K is 2 to the H here。The number of people who expect to end there is half of the interval length because M is 2 n。

And being the number of cells in the array。We expect a half times2 theH to land there。So kind of。

Having much more than that land there， like a multiplicative factor。

 more land there is sort of an anomaly。Yeah， you can crank out an argument that uses any constant factor bigger than a half。

嗯。You could do that。So the probability that's some length。C eight guy interval is dangerous。

Let me call this interval I prime。That's equal to the probability。

 That's at most the probability that the length of I prime minus the expectation of。

The length of I prime。I's bigger。Then。So we we're basically a half larger than the expectation。Right。

 we expect。LI prime over two people， we expect I prime over two people there。But we got。Three。

 I prime number four。Buthi she deviates an expectation by。Half the expectation。

 So then you use this is at most。This thing here is the size of I prime over 2。

 so this is at most1 over the size of I prime over 2。To the fourth times the expectation。

Of LI prime minus the expectation of L prime。To the fourth。

And you argue about this the same way you get。You'll get something that looks like the length of I prime squared。

 and remember this guy here。Is theta K。So here you're going to get whatever over k squared。Okay。So。呃。

I feel like there must be questions。So。Well， okay。Feel free to ask me questions。 We have Piazza now。

呃。So we have this interval of length K， and we're recovering it by intervals that have length。

 roughly K over 4 to K over 8。So the number of these intervals we need is a constant。

 It's somewhere between four and nine of them。And even if you look at all the length intervals combined that cover。

That's cover H of x。That contain H of x。That's a length 2 k -2 interval。 So it's also。

It's also spanned by a constant number of length of care for eight people。Yeah。Don't we still have。

Yeah， we do have to sum over K。But then we're sum over k of1 over k squared， so this thing here。

This thing here is going to be， if you calculate it， it's going to be whatever k squared。

So this thing here， so this is whatever K to the fourth。This is going to be about k squared。

If you do， if you work it out。Yeah。Yeah。I were able。Yes， that's right。 So even conditioning。 So。

 you know， we're conditioning on where on the fact that I contains H of X。So conditioned on that。

 that's like one evaluation of H on at some point that we were conditioning on。

 There's still like four more that we can afford and they'll still all act independently because there are only five of them altogether together。

So yeah。So， that's why。Yeah， that's why the original statement by。

I think Mi I Perasku told me is the reason fiveYs works is because when you condition on a1。

 it's fourYs。That's a very very cryptic statement at that before you actually see any arguments。

So let me say something about other types of hashing。嗯。Namely approximate membership。

 who seen Bo filters， by the way。Okay， a decent number of people。Okay so。Dictionaries。So I'll just。

 I'll quickly review balloon filters， and then we'll get to。Bluemire filters。

 But before we get to blue mere filters， I need to say something about cuckoo hashing。

So this is a different problem now， this is the membership problem。Or approximate membership。

So we have a set。S， which is from。From which is in you。Okay。And we need to maintain S。

So there could be update。These are the two operations we support， one is update。

 updated X sets S to be S union X。And then there's queryery X。Which says。Is x in S？Yes or no。Okay。

So there are no keys in well， there are no values anymore in our hash table。 there are only keys。

 we just want to know the key is the key in our。Seid or not。And。I should say that with dictionaries。

 so dictionaries are where we have values associated with keys， with dictionaries。

 we were allowing ourselves to use n words of space。With membership， we want to use less space。

 We want to use like n bits of space。 Remember， a word is like log of U bits。

So now we want to get away with instead of n times log U bits， we want to get away with n bits。Okay。

 so the basic idea， so we have the basic idea is to allow some slack。So we will allow。

False positives。What I mean by that is if x is an s。The probability that。Query of x。Is one。Meaning。

The query will say yes， X is in your set。 That should be one。And if x is not an S。

The probability that query of x。Is one should be at most of half。Okay。

So this is a randomized guarantee with a probability of failing。

And the data structure that gives you this is extremely simple。So the solution。I we make an array？

Yeah。So the problem。Depends on the data structure so can vary。Like， can the answer change between。

Cating one of the。 what do you mean probability， if you make the same query twice。

 you'll give the same answer about times。So in order to boost this， I have to make two copies of。Yes。

 that's right。Oh yeah， you're answering a question。 I was gonna ask a question about that。

 So you really gave me the answer， but I'll get back to you very soon so。The idea is， look。

So pretend to be no N。 Of course， if we're updating， if we're inserting into this data structure。

 N keeps changing。 I don't allow deletions。 by the way， I'm just allowinging insertions。

Pretendending we know N。 pretendt it's just a static problem。Okay。

 we're giving all the items up front。What I'm going to do is， look， I'm going to pick an H。That maps。

My items。Into this array。And when x comes。I'll set。H of x to be 1。For X and S。

I just hash it and put a one in that bit。 This is a bit array。It's not an array of words。

 it's array of bits。So I have a question。So this list around the same page I'm asking。

So if you understood what I said， then this should， this should not be real， you know， well， okay。

 question， why is this true with the solution， the first bullet。Yeah。But， yeah， if x is an S。

 I set the bit to1 and it's1。 So the query is just going to check。 I didn't tell you what query does。

 Queery just checks whether that bit is one or not。And if it is one， it says， yes， it's in there。

Okay how about if x is not an S？😡，Why is this the case？It could be said by someone else。

 so then why is the probability at most of half？SoSo as you said， so the probability。

 so like let's say x is not an S。So then the probability that query of x。

Equals 1 is the same thing as the probability that there exists some y in S。Such that。

H of x is equal to H of y。Right。If there's someone who collides， you'll be fooled。

So how do you bound this？If I want to be a little pedantic， what's the next thing I would do。Yeah。

 yeah， some of all the possibilities。 So I would use the union bound。

The probability that there exists a bad Y is the sum over all Y of the probability that y is bad。

 So this is at most， the sum。 this is union bound。The sum over Y andS。

The probability that H of x equals H of y。Okay， yeah。The two bit space。ABy two separate。Yeah。

 if a bit is1， then there's nothing like you mean if two items both map at the same place？😡，地き？

To be said。For the fire to be won， right？There's you know one bit。 You just。

 so the the update algorithm， this is update。 So update。

 you just evaluate H of x and you set not set H of X。 you set。 Let's say this iss A。You said。

A of H of x to1。And the query is you just output a of H of x。So maybe I'll say what the query is。

 so query。So the query。I you output？A of H M X。And the update is you set AF Hx to one。

Does that answer your question？来到1审期。Oh， yeah， there are many implementations of bloom filters that are。

Somehow， there are trade off some constant factors and things。But yeah so。I mean。

 I haven't gotten to the actual。Blue filter yet。 This is just a bit array for now with a hash function。

But okay， so now what's this probability？1 by M， yes。And there are n different choices of Y。

 So this is。N times 1 over m， which is a half。Okay， so now now going back to your。Your。

The point that you raised。You having a false positive probability of a half is not really that great。

Whoever is using this data structure will come to me and say， you know， Glai。

 I'm willing to have a 0。01% chance of。Of false positives， but not a 50% chance。Okay。

 so suppose they tell you。You we want。That。X， not an s implies probability that query of x。Equals 1。

 is that most？Epsilon。So now what would you do？What's。What's the solution you would。Yeah。

 which I guess is what you said。But yeah okay。1 by epsilon。 Okay， I don't。 So that that works。

 but you can be。Yeah， anyone， you ready to say something。You can make that。I'll make it longer。Yeah。

 you could do that。 So yeah， so good。 So yeah， you could make it longer in particular。

 you want n over M to be Epsilon。 you make M B N over Epsilon。Okay， you could do that。

What else could you do？Yeah， that's another thing you can do。 You can take log on repon copies。

 So what you do is。You'll have a bit array of length M。M is again， 2 n。But you'll do it many times。

Okay。And the number of times you do it。Is log of1 ofpson？And here you'll have your hash function 1。

 hash function 2， hash function K， where K is log1 e rhpsilon。And when you have an update。

You'll update in every single array。😡，And when you have a query， what would you do for a query？

Search them all， and then what would your answer be？It's in all of them， Yes exactly。

 So the query you just say you know are all of these set to one？So to be fooled。To be fooled。

 you'd have to be fooled every single time， which happens probability1 over two to the K。

 which is epsilon。So the space here is n times loginpson bits。😡，So in the time。

Is O of log1 of Repson？It is possible to get more sophisticated and I think improve this time to a constant as well as。

As well as support deletions。But I'm not going to cover that in class。

 but this is one thing that's called a B filter and you know theres Blo filter。And it's due to bloom。

In 1970， I think。不是。So that's balloon filters for the membership problem。

And I want to get some blue air filters。And I mean， I'll tell you what Blue mirroror filters solve。

I'll tell you what problem they solve。So with balloon filters。We're solving the membership problem。

 where you can imagine。For every。For every element to in。Are set。

We want to be able to look up a bit associated with that element。 And here it's the bit1。

 But what if we want to associate an orbit string。With every element in the set。Okay。

And bluemi filters let you do that with n times R bits。Okay， so that's the retrieval problem。

So note that this doesn't solve。😡，Li。😔，It still doesn't solve the dictionary problem。Okay。

We never actually store the keys anywhere。Like in bloom filters， we never stored the keys， right。

 If you actually ask me at some point， what are the elements that are actually in my set。

 I can't tell you。 But if you give me an element， then I can tell you whether or not it's in the set。

Bluomar filters are going to be similar。 if you give me an element。

 I'll be able to tell you the orbit string associated with that element。But if you ask me。

 what are the keys in this data structure， I won't be able to report them to you because in particular。

 I'm not even using enough space to hold them all， right， You need N words of space to hold them。

 and I'm only using n times R bits。Yeah。It means that I might get a pit stringing。Yeah。

 so if if you give me an element that's oh， actually the way so I haven't shown you the construction of Bre filters。

 but we'll get it to be such that first of all， we're going to look at static Bomere filters。

The static problem， not the dynamic problem。 And we'll get， we'll get an algorithm that。嗯。

Doesn't make errors。So if the element X you give me is actually in the set。😡。

I'll give you the correct orbit string。If the element you give me is not in the set。

I might just give you total garbage。I mean， I won't know that I gave you garbage because I don't know what's in the set。

 Oh， maybe that's what you meant。 Oh， I see。 Yeah， yeah， sorry， Yeah。

 You'll get an arbitrary orbit string with no guarantee。 Okay， good。 So yeah， that is right。Okay。

So before we do Bre filters， I want to do cuckoo hashing。嗯。

So maybe I will spend a little bit of time on Tuesday about Power two choices before we get completely out of hashing but。

But don't want to say about cuckoo hashing， so。Goo。Good。

This will be a solution to the dictionary problem。The a dynamic dictionary problem。

And this is due to pay and roal。Journal of Alrithms 04。And the idea is to use。Two hash functions。

Instead of one。Yeah。And the power of two choices is going to be just our second example of the power of using two hash functions instead of one hash function。

 but it's sort of a different。A bit different， but。Okay。And what's the basic idea？Again。

 we'll have an array A。Of length。And being like c times n。Some cards sometimes n。

I'll imagine like4 n or something。Oh， by the way， so just make sure we're all happy with loo filters。

Remember at some point， we talked about KY's In hash families。

What amount of independence do I need to make bloom filters work。

 Each one of those hash functions over there， What independence， what。

 what kind of hash family should they come from。2， why2。Yeah。

 because whenever I reason about how a set of hash evaluations behave。

 I only care about two at a time。So two wise independent suffices to say that this is one of it。Okay。

 so we have this array of length t times n， and we pick。2。Hash functions。G and H。Mapping。You。To M。

And let's just imagine that they're actually perfect， totally random hash functions。And。I sort of。

 I don't remember exactly why it's called cuckoo hashing。

 It has something to do with I do it as a bird called a cuckoo bird or something。

And like they steal a cuckoo bird steals another cuckoo birdd's nest。Something like that。

It lays eggs in the other person's and the other bit。 Okay， good。

 So it lays eggs in the other bird's nest。 So the idea here is。Let's say we want to insert。X。

 so nests here are going to be memory cells。So。Put。X。In。A of H of G of x， sorry。

So just evaluate G that tells you an entry and put X there。But there might be someone else there。😡。

If some。X prime。Is there？So let me call this location J。Then， if。G of x prime is J。Put x prime in。

H of x prime。Oh， otherwise。If H of x prime was J。可。X prime and G of x prime。Okay。

 so we put x somewhere。And there might be an item already living there if there is an item living there。

😡，It got there because of one of its hash functions。

So we'll kick it out and send it to where its other hash function wants it to go。

But it might then collide with someone else。😡，And then that person would get kicked out。

And then move to where their other hash function tells them to go。

 And there will be like this chain of moving things around。And potentially it could go on forever。

But hopefully it doesn't， hopefully it ends very quickly。And that's kckoo hashing。Okay。

Other questions about。The insertion algorithm。Yeah。乳せく？We'll prove that the problem。

Willll augment to the insertion algorithm。So。We'll also say if this goes on。On for more than。呃。

10 log n steps。Then rebuild。The entire data structure。Okay。

 so we'll go kicking people out of their place and moving them around。

 And if we if this chain of moving things around went on for more than 10 login steps。We'll say。

 you know what， I'm not feeling very confident about what's happening here。

And I'll just pick a totally new H&G at random。And then I'll make a totally new hash table and then try and reinsert everyone in there。

And then that might loop again for more than 10 log again steps at some point。 If so。

 I'll give up again， and I'll keep doing this until it works。Yes， no， no no。Well， you could。

But what you can show is that the kind of expected。

What we're going to end up showing is that the expected。Insertion time is a constant。

 even if you take into consideration that once in a while。

 we have to rebuild the entire data structure， even with that。In consideration。

 the expected time will still be a constant。Yeah。Yeah。哦， yeah， yeah， yeah， yeah。J is the location。

 that's right。So our goal。Is to show that。The expected。Update time。Is over1。Okay， yeah。

This time is it。And。If H of x prime equals G of x prime。Yeah， they will people expect out。

 that's right。Yeah。Okay。So this is what we plan to show。Yeah， that's that's a good point。

 Like just because there's a cycle doesn't mean。We're in trouble。Although there are two cycles。

That's worse for us。But what we're going to end up showing is that the problem of having two cycles。

If you follow well， we'll get there when we get there， okay。So this is what we want to show。

Before we show this goal， let me just knock out Bre filters。

Like how are we going to use linear filters？嗯。So。To get bluere filters。So actually before I say that。

The main tool analysis。The analysis。The main tool I should have asked this a while ago do it describe。

OK好。so the main tool。From the analysis。Is the cuckoo graph。Okay， what's the cuckoo graph？

There are M vertices， it's an undirected graph。 there are M vertices。And N edges。And for each。

X and S。Draw edge。Between。G of x。And N of X。And that's the cockoo graph。So I say again。

Or like parallel edges？嗯。Yeah， I mean， is it a multigraph？So yeah， sure。 make it a multi graph。

 I don't think it will。Yeah， make it 못。And you could have a self loop if H of x equals G of x。

 for example。Okay。The way that we're going to show this goal is。For reason about， you know。

 how the cuckoo graph behaves， it's a random graph。Because it depends on this hashing。

But we want to say some things about this random graph。But before I get to showing this goal。

 I want to talk about how to get bluere filters。You can use。呃。

You can use cuckoo hashing to construct。Blu your filters。And blue mirrorre filters are due to。Chelle。

Killian。And Ruenfeld。Entao。This is from 2004。And this they solved。The orbitbit retrieval problem。

so I mentioned with every element in the set， you want to associate an orbit string。

 And when I give you an element in the set， you should output that orbit string。

 if I give you something that's not in the set， you you can output whatever you want。

And we're going to look at the static。Version。So you know all the items up front and you just need to create this data structure。

And you know the strings as well。So。To get gler filters。Create。Cukoo hash table。Okay。Shou。😔，That。

Probability there exists a cycle。In Cockoo Gra。Is that most than half？

Any cycle anywhere in the graph， so that probably that happens at most a half。

 that's something I'm not going to show right now。And， you know， if it's the static problem。

 you know all the items up front。 So you'll create the hash table。 You'll check。

 are there any cycles in the cuckoo graph。And if not， you're happy， if so。You'll。

 you'll pick a new hash function。And then keep doing this over and over again until there aren't any cycles。

And the expected number of times you have to do this is two。

Expect the number of times you have to construct the cuckoo hash table is two。So。

You can do that in preproces and you expect to be fast。Suppose。There are no cycles now。

Then what does the cuckoo graph look like， there are no cycle， so it's a forest。

So the graph looks like。Forest。And。Each one of these edges。What is that edge， right， It's an item。

Right。Okay。So this is one hash function。 This is like G of x or something。 So this is some item X。

 This is like G of x， and that's H of x or the other way around。And what I'm going to do。

I I'm going to say。Say X owns。It's deeper node。Like root all these forests。

So that now they have depths。And let's say that each item owns its deeper node。 So X owns this。

There's some why here， why owns this。And here's what we're going to do。

We're going to fill at each one of these nodes， we're going to store an orbit string。At the roots。

Store zero。At the roots。And then fill in these trees just from top down。😡，And when you get to a node。

Someone owns that node， namely the person who's written right here。You know what his orbit value is？

😡，And the thing above you has already been filled in because we're filling in it from top down。

So fill in this to be whatever it needs to be。So that the XO of these two is the right thing。Okay。

So let me write that down。Being the orbit string associated with X。Until we write that down。

Fill in orbit strings。In forest。Top down。Every node。Gets。A string。If we query。X。Will output。

A of G of X。X or。A of H of x。That's how we answer queries。And。When filling in。And hey。

 remember every one of these nodes。Every one of these nodes is a memory cell in A。本人。

When filling in A。Top down。But。Whatever。Value。In node V。Is necessary。So that。So that querying。

It's owner。Is correct。Yeah。Yeah and。So late。You should be sufficient。weSo wait。

 so the actual memory cells， the actual memory cells are the vertices， not the edges。

So where like so given x， where would you store xs value。

 Would you store it here or would you store it here。On the deeper node。嗯。Oh， wait。嗯。Yeah。

 so I guess the point is I really want to use。N times are bits。And。NowWhy can't I？嗯。Now。

 what you're saying sounds actually very reasonable。How do you know which one you。Well， I mean。

 if this is all static， I can write down for every， oh， I see。Yeah， okay， I see， right。

How do you know which one is deeper， so you don't actually store the elements。

So you can't have a table that says this element is。Yeah， yeah， I see。 Yeah， that's a good point。

That is a reduction to a1 bit material problem h。Oh， okay， oh someone said that over there。 Oh， okay。

 well， thanks， whoever said that。 I don't wanna take。 Yeah， okay， so yes， so yes， yeah。

 then you need to solve a1 bit repeatrie problem。 That's a good point。Okay。So I guess next time。

Next time， I'll probably just， I'll say something about cuckoo hashing。

 or maybe I'll give it as a homework exercise。 I need to decide。

 I don't want to wrap up hashing because there are a lot of algorithms out there in the world。Okay。

 so any questions？Yeah。Yeah。KY。Like degree k minus1 polynomials yeah。Yeah， yeah。Are those the ones？

how do you come up with。So there are other。Actually。Okay， so。

There are other families of Qos independent hash functions。

 One way to get them is by using something called tabulation。嗯。So。I'll just write a reference。

It's a very recent paper， you can look up Thoror。In Fox 2013。

He he shows how to construct very fast KY independent families using tabulation。嗯。

Another thing is if you choose like primes carefully。

Then some of them like the mod and division operations can be bit shifts。And those。

 those you can like be very fast with。 So one thing that I'll recommend looking at is。

I forgot all the authors， but diitzfeldingger。And others。And it's called the multiply shift。

Multiply shift hashing。So he gives some pairwise independent family of hash functions where you never have to do a mod。

 Everything is just bit shifts。Well multiplying in bit shifts。So。Yeah。

 but I guess there aren't that many families out there。Actually。

 it's a very active research in this upcoming so there's the kind of the biggest theory conferences are Fox and stock that each happen once a year and Fox Foundations of computer science is happening in October and one of the papers that's going to appear there this year is some。

So KY independent polynomials to evaluate them takes K time。

 right because you have to you have to evaluate this degree K polynomial。

 So they give KY independent families where you can， you can store them efficiently just like before。

 using little space。But where evaluation takes constant time。But we independent of K。

 but with the caveat that you have to promise me that you're gonna evaluate them in order。

 You're gonna compute H of1 then H of 2 then H of 3， which is not true in a lot of applications。

 like some of the ones we've been seeing here。嗯。But yeah， I mean。

 getting better hash families is like an open area of research。I mean。

 because their running time bounds only hold when。Like their algorithm to produce the hash values is only fast when it's sequential。

I didn't actually read their paper。 I just like read the paper， I mean。

 it hasn't even been presented yet， but it's on the archive， for example。Y。

