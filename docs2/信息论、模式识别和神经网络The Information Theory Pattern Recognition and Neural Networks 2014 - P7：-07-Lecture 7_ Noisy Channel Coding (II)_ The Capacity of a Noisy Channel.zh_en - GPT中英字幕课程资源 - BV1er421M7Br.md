# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P7：-07-Lecture 7_ Noisy Channel Coding (II)_ The Capacity of a Noisy Channel.zh_en - GPT中英字幕课程资源 - BV1er421M7Br

![](img/74e3067b49176b87d0e6507f741e1042_0.png)

Last time， we discussed。Inference and information measures for a pair of random variables。

 a pair of dependent random variables。 Let me just recap。Those two topics fairly quickly。Inference。

One of the examples I mentioned was the three doors problem where the rules of the game are that the game show host hides the prize behind one of the three doors at random。

The player chooses one of the doors。For example， we might choose door 1， as shown by the blue circle。

Then the host promises that he will open another door in such a way as not to reveal the prize。

 Then the player will be given the chance to stick or switch。And if they switch。

 then they get what's behind the other closed door。嗯。Which， in this case， would be behind door 2。

So the rules are explained。 Then the player the game。 The player chooses a door 1。

 The host opens a door 3， revealing nothing as promised。

 Should you stick switch or does it make no difference。 And last time you already voted on this。

 Everyone knows now because the word has got out that you should switch。

And what I want you to know is how to answer this sort of problem in general。

 because maybe people have memorized that they should switch。

 but they still don't actually know how to answer inference problems。

 how to solve inference problems。The general rule for how to solve inference problems is write down the joint probability of everything。

 then condition on what you know。And then you'll have the right answer。 And that。

 that's a universal rule for solving probability problems。That have any inference element to them。

 Often， when you do that， when you。Write down the probability of everything。

 then condition on some data。 What you'll end up doing has a particular form。

 which is called basees theorem。So in general， the joint probability of everything can often be written as shown in the top right hand side of the top line there as the prior probability of some hypotheses。

 which could account for the data multiplied by the probability of the data given hypothesis。

And then when you condition on a particular data outcome， you get the thing on the left hand side。

 the posterior probability of your hypotheses， given the data。

Is that joint probability normalized dividing by the data that actually happened。

So let's illustrate how this works for the three board The three adores。Problem。

 we've got three doors。 The prize could be behind。Any of them。And in this particular situation。

 the player has chosen door  one before the game show host does his thing。

 The data is going be which door does the game show host go and open。 So we actually know that。

The positive abilities could be he might open door 2 or he might open door 3。

 The original hypotheses are。That the prize is behind door 1。

 door 2 and door 3 and clear on my notation。 So the hypotheses are there。 H is 1，2 or3。

 Their prior probabilities are a third or third， a third， because the prize could be anywhere。Now。

 what's the likelihood？ What's the probability If H is true that you get D equals 3。 Well。

 let's go through the， the three cases。 If the prize is actually between behind door  one。

 then they've got a free choice of opening door 2 or door 3。

 So these two data outcomes are equally likely。 gonna have no knowledge about。

How the host picks the door when he has a free choice。 So it's a half a half。

 So the probability of the data being3， given that value of H is a half。

If the prize is behind door 2， then he's obliged to open door 3。 He doesn't have any choice。 In fact。

 So the probability is one of D being 3。If the prize is behind door 3。

 then he's not allowed to open door 3 at all。 So the probability of that happening is 0。

So that's the probability of the data under the three hypotheses。

 The way of thinking about this this is what we're doing is the prior says how probable the hypotheses were before we got data。

 Then the likelihood is is measuring how well did those alternative theories predict what actually happen。

 And you reward things that predict well。 And the way you do that is you multiply the prior by the likelihood。

 So we do that。And in your head， you can work out a third times a half。 We've got a third times one。

 And we add those up to get a normalizing constant。 and that adds up to a half。

 So now when we multiply those two across， we get the third times a half。

 and we normalize by dividing by a half and we get a third。

 we get a third times one and we divide by a half。And we get two thirds。Incidentally。

 what is this normalizing constant。 Well， that's how well you would predict the data that happened。

 given your state of prior knowledge where you don't actually know which hypothesis is true。

 So when I ask you， okay， the the player has chosen door warm。

 You haven't got a clue where the prize is。 what do you think is going to happen。 You now， say， well。

 I don't know。 he could open either door is 5050。 And that's what we just worked out here。

 The probability of door 3 being opened is a half， if you don't know where it is。

 don't know where the prize is。Okay， so that's what we normalized with。

 And we've got our posterior probabilities popping out on the right hand side there a third。

 two thirds。 Therefore， you should switch。 It gives you a two thirds chance of winning if you switch。

😊，Okay， so that is base theorem。 And we will need to use that when we're playing with channels as well。

 if we ever want to infer what the input of a channel was when we see the output。And last time。

 we defined how to measure information for a joint ensemble with two random variables in it。

 So trivially， we were able to define the joint entropy。

 because that's just the same as the entropy we're familiar with。 We defined the marginal entropy。

 H of X and the marginal entropy， H of Y。😊，Then we define things called conditional entroes。

 H of X given Y， H of Y given x， And we define a thing called the mutual information。

 which we write I of X， semico and y。And。The mut information is a measure of how much dependence there is between the two random variables。

Okay， so that's what we did last time。 And now we're going to talk about noisy channels。

And we're building up to the pinnacle of this bit of the course。

 which is the assertion that if you've got yourself a noisy channel like the binary symmetric channel。

 which flips a fraction F of the bit， it is possible， even though it's an unreliable。

 noisy channel to communicate reliably over that channel by the cunning construction of an appropriate encoding and decoding scheme。

 you can communicate arbitrarily close to perfect reliability。😊。

So what we're going to do now is repeat what we did in the last lecture。 We're going to say。

For the case of noisy channels， how does inference work and what are the information measures for a noisy channel。

 And the way this works is a channel itself only defines a set of conditional probabilities to actually get a joint distribution。

 We have to invent some input distribution。 Then we can talk about the joint distribution of the input and the output。

And we can also talk about information measures。So。Once we take the channel。

 which has in green a set of conditional distributions。

 the probability of the output given the input， if we then bring along an input distribution that's under our control。

 We can invent what the input distribution is P of X in purple。

 You multiply those two together and you get a joint distribution with that distribution。

 you can do inference。 and you can also compute the mutual information between the input and the output in the way we defined last week。

So that's the game plan。So we'll play with channels a little bit。 We'll do some inference。

 We'll compute some information measures， and then we'll talk about how that relates to the noisy channel coding theorem that says you can actually communicate reliably over these things。

Let me tell you some channels。So， the favorite channel is already。Up there on the screen。

The binarysymmetric channel。Which。Flip a fraction F of the bits。

 We can represent that channel if we want by a transition probability matrix or sorry。

 a matrix of conditional distributions。And I'll write it this way round with。

Alternative values of the input across the top， and alternative outputs。A down a。So， if x is。0 or 1。

The probability of the output being。0，1 is respectively on minus F F or F on minus F。Okay。

 so that's one channel。Here's another one。This one interestingly is called binary because it's got two inputs and two outputs。

 It's called symmetric because there is a symmetry。

 If you sort of interchange 0 and one at the inputs and the outputs， you get the same channel。

 Here's another one。 It's called binary， erassure channel。And this is a great toy model of another。

 another phenomenon that happens in communication， which is sometimes。Your message。

Doesn't come out at the other end correctly。 And the receiver knows that。

 but they still don't know what you actually sent。 So you have a symbol called called question mark。

And there's a probability， say， F。Of a question mark coming out。Allright。So， the。

Set of conditional probabilities for that channel looked like thiss 1 minus F， F 0，0。1マ n。

Channels don't have to be symmetric。 You can have asymmetric channels。The Z channel is one where。

 whenever you send a 0。It's received perfectly。 And whenever you send a one。Maybe you got a one。

 or maybe you don't。Okay， so in general， this set of conditional distributions is。

Represented by a matrix， Q， J given I is the probability that the output is element B。

 J in the output alpha ofbet， Given that the input was element I。In the input alphabet。

And I've got one more favorite example， which is the noisy typewriter。

 which is up on the screen there。 The noisy typewriter is a channel where the inputs are the。27 keys。

On a typewriter。 But what actually comes out isn't necessarily the key that you hit。

 It may be the one either either side， left or right。 So there's a probability of a third。

Each when you hit the C that you get a C， A B or a D and so forth with circular symmetry。

 I'm imagining a circular keyboard， if you like。Okay， so that's the noisy typewriter。

And what we're going to do with these channels is we're going to first imagine that we spray some random data from an input distribution that we get to define into the channel。

And we're going to， thus。As it says on the screen， define a joint ensemble。

P of x times P of y given x。 We're going to do inference。

 and we're going to compute how much information is conveyed。 Let's start。

With the binary symmetric channel。And。We'll pick a particular channel with a particular flip probability。



![](img/74e3067b49176b87d0e6507f741e1042_2.png)

So let's say it flips 10% of the bits。And then。So what I mean。Okay。

 then we need to pick an input distribution。So， let's pick。This。This input distribution。

Probability of a 0 is going to be 0。9。The probi of a one。Its going to be 。1。 So we're going to。Send。

Say a bent coin sequence with lots of zeros and a few ones into this channel。

So we're spraying in these bits and outer coming outputs， why。

And I want you to assume that now we look at a particular moment， and we observe。

What the output of the channel is。And the question is， given this。Output。

What do we think the input was， Okay， please work this out。What's the probability。That。X。Where's one。

And what's the probability that it was 0。 Please chat your neighbor and。Let's work out an answer。



![](img/74e3067b49176b87d0e6507f741e1042_4.png)

Okay。Time to vote。If you're still working it out， sorry， you can vote for Z， which is I don't know。

 And I've got a few options for you to choose from here。So vote for Z。

 I don't know what the probability is that X is 1。哎。Three votes。Votes for a 0。1。Votes for B。Okay。

5 votes。 vote for C。3 votes for something else。Anyone， there's lots to choose from。Okay。Right， okay。

 let's work through this。 What's the probability that the input was a one。

 given that we see an output that's a one。We write down base theorem。

 We need the joint probability on the right hand side。And as is normal with bath The。

 it looks like this。 You've got your priorryor。On the inputs， and you've got your likelihood。

And then we need a normalizing constant， which is the probability that you see the data。

 the output white was one that you've actually seen。 And that's sum overall possible values of X。

Of the thing that we have upstairs。 It's the normalizing constant。 We have one given。X。

 let's call it x prime。We have x prime。Sir。We need the probability of if you put a one in。

 what's the chance of getting a one out。 And the answer to that is 。9。

 because the flip probability is 10%。 So have 。9。As the likelihood。

 the prior probability of having a one is there。 It's no。1。

Then we divide by the normalizing constant， which is the sum of all these terms for all the different explanations of what we saw。

 So the first explanation we've just worked out is that it was a one and it didn't get flipped。

 But the other explanation is， it wasn't a one。And it did get flipped。And the probability of it。

Not being a one。Is 。9， and the probability of it being flipped is 01。

 I hope what I just said then made sense。 Any questions， Are we clear。So these are the two。

 two explanations。And when you top them up。We can make a note of what the probability of y equaling one is。

Which is no。1。eight。And it just happens when we look at that， that it all cancels rather nicely。

 and we get a h。So， the correct answer。Here's a huff。Any questions。Okay。If we observe the output。

 y is 0 instead， then。What's the probability that x equals one？Any don I want to。

Hasard a guess what the answer to this is。If you see a 0， what's the chance that x is1。Just I guess。

Ha。Any advance on half， no。What do you think。Much lower。Yeah， less than 0。1。 Okay， good。

 So let's work it out。So upstairs， we've got the prior probability of getting x is1。

 and we've got the probability of a flip happening。😊，Downstairs。

 we've got the probability of what has happened。So upstairs， we have 0。1 times 0。1。

The probability of a one being put in is only 10%， and the probability of getting flipped。Is 10%。

 Then downstairs， we have。That。Plus， the other way of getting。A0 out， which is what was put in。

Was a0， and it didn't get flippedped。So that's 。9 squared， which is 。81。And top that up。

You find the probability of seeing y equal equals 0 is0。82。And what we've got upstairs is one。

 what we've got downstairs is is 82 hundredth， respectively， one。Over。82。Okay。

 so we've found out two interesting things along the way we've。Worked out for each of these cases。

 not only what the probability of the input is now that we've seen the output。

 we've also worked out along the way。 what the probability of getting that output y equals 1 is。

 or the probability of getting y equals 0。 And notice those two sum to 1。 weve got。

82 hundredth and 18 hundredths， which adds to one and has to be the case。

 So those are the sort of sanity checks you can apply if you work out these sort of questions。

Very good。 Okay， we've done inference。 And in this particular case， if you see a 0 coming out。

 it's very unlikely the input was a one。Now， having done inference， we are very well equipped。

To talk about information measures。So we can， for example， ask the question in general， On average。

 given the assumptions that we just chose there for the channel and the input distribution。

 how much information。Does the input convey about the output， or actually， more interestingly。

 the other way around， How much information does the output convey about the input。

So we're interested in how much information is conveyed about。Input。Bye。The output。

And that's called the mutual information。And it is H of x minus H of x going y。And it also is。H of Y。

Minus H of y。Givenive x。Which is a slightly remarkable identity。

 What this one is saying is the amount of information you gain on average is how much information content X had。

Intrinsically， without knowing the output， minus how much information content it still has when you have seen the output。

Okay。And this is saying you can do it the other way around。 You can just ask。

 what's the information content of the output and how much information content does the output still have。

 if you know the input。Whenever you want to compute the mutual information for a channel。

 you're free to do it either way。But a tip is that quite often。

 this way of doing the calculation is a little bit easier than this way。 Its slightly less work。

 It's not always the case。But。Let's do it both ways so you can see what I mean。

So we'll do it the first way。So to do it the first way， we need to。Oh， which way am I doing it。

 My notes do it in the other order。 Okay， let's do it the second way。To the easy way first。

 we need to know the enpy of y。 Well， what's the probability of y It's 。8 to。18。

 And that was a fairly easy thing to， to work out。 And it's often easy to work out the probability distribution of your outputs。

So， H of Y is。H2 of0。18。 This is the binary entropy function。Which we defined in the first lecture。

Now， if， you know。The input of the channel。 Now， what's the entropy of why， Well， either。

It's the entropy of this distribution。Or。Its the entry of this distribution。And the。

 those distributions both have the same entropy as each other。

 So the average of the entropy of this one and the entropy of this one， It doesn't matter how。

 how often we see this and we we see this。 The answer is， it's the entropy of。F。

 the binary entropy of S。Is the entropy of the output。Givenive X。Okay。So， now， we just。

Look up binary en。Maybe for the sake of the record of justifying what。Binar entropy function is。

 again。Okay， so we've plopped that into our calculator。

 and we get these two numbers out where F is 0。1。And we subtract。And we've got 0。2。one。Bits。So。

 that was。Fairly painless。 We just had to work out an output distribution， and then。

The conditional entropy of the output， given the input， was a very easy thing to write down。

 We can also do the calculation the other way around。

And my judgment is it's slightly harder work to do this one。We have to start out， by working out。

The binary entropy。Of 。1， which we've。Just mentioned。And then this one。

 you do have to work out all the terms。 This entry of the input。

 given the output is the sum overall possible outputs weighted by how probable it is that you get that output。

 Then what is the entry of the input for that particular value of the output。So we need to tot up。

All of those possibilities。There's a 。18 chance that the output might be the first one we considered。

 namely， the output might be one。P in brackets here。And then in that case， the entropy of the input。

 given y is the entropy of this distribution，50，50。

So we need the binary enpy of the 5050 distribution。Then to finish off this calculation here。

We need the 82% chance。That the output will actually be。0， multiplying the binary entropy of。

The probability of the input， given that the output is y equals 0。 And we worked out a moment ago。

 that is that probability distribution is 1，82th。81，82ths。还不在。Alright。

 so now we go pressy pressy with the calculator and work out the binary entropy of half。

 the binary entropy of 1，82th。 And we already had to work out this binary entropy as well。

 So that's three binary entroies， which is a bit of a f。 Plus。

 we had to do base theorem to get this number。 and we had to do base theorem to get this number。

 So that's why it feels like a bit more work。 We do all that。 We get 。47。😊，Minus 0。26。Which is。0。21。

And it's all measured in bits。 And that's the same answer。What we got here。As it should be。Okay。

 so what have we done， We introduced the channel。 We picked out of thin air。

 our own input distribution P。 It was completely up to us。 We could have picked anything。

 and then we worked out。The mutual information between the input。And the output。Of the channel。

And we had a completely free choice of that input distribution。

 And what we just worked through was the special case where the probability of x equaling one。Was。

Poin1。And for that special case here， we have worked out。But the mutual information was。0。21。

And we could have put picked any input distribution， anything between 0 and 1。

And we can repeat the whole calculation we just did。Pro the。Thous0 values there between 0 and 1。

 So please do that now and sketch a graph。

![](img/74e3067b49176b87d0e6507f741e1042_6.png)

helello。

![](img/74e3067b49176b87d0e6507f741e1042_8.png)

Okay， are you done。So when you complete the curve。You get something that looks like this。

If you always put zeros into the channel， then the output doesn't convey anything about the input anymore。

If you always put in ones， also。It conveys no information。It's a symmetric channel。

 So this curve must be symmetric， and it's going up。 So it's gotta have a maximum somewhere。

 it's got to come down。 So there's your sketch。By symmetry， the maximum must be at a half。

 and you can prove that as a homework exercise if you are skeptically inclined。So。

What are we going to do with this now。Here's the idea。We're going to introduce a definition。

We had a free choice of this input distribution。 I didn't label that access。 Sorry， P of x equals 1。

I did label it， and I wiped it out。Okay。We've got a free choice of the input distribution。

Something we could do is we could hunt around in the space of all possible input distributions for the one that maximizes the mutual information。

 Wouldn't that be an interesting thing to do， Because then that's the input distribution。

 such that you have maximum。Mual information between input and output。So。

Well then define the thing that we get from that to be the capacity of。这钱了。

So if anyone gives you a channel， you can say， the capacity of that channel Q is the maximum overall possible input distributions。

 P X。Of the mutual information。Between the input and the output and the distribution that achieves this maximum is called the optimal input distribution for the channel。

For example。For the binary symmetric channel。With a flip probability F。Of 。1。

The optimal input distribution。Is。啊哈好哈。😊，By symmetry。Or if you don't believe symmetry arguments。

 let me prove it to you。So what is the mutual information for any choice of input distribution。

I'll introduce a variable called P1， which is the probability of picking one as the input。 Okay。

 so this is our input distribution。the input distribution is P1 comma 1 minus P1。

As I vary the number P1， what happens to the mutual information？ Well， we need。

Let's do it the easy way。We need the entropy of y。Who we need the entropy of Y given x。

So we need the enpy of what's the probability that the output will be one。 Well。

 you can get it by putting in a one and having a。Flip not happen。

 or you can get it by putting in a not one or 0。And having a flip heaven。Okay。

 so that's H2 of that lot。This is， sorry， I'm working at H of Y。Minus。H of。Y given x。

 And the second term is。What's the entropy of Y given X， Well。

 it doesn't matter what the input distribution is。 The entropy of Y。 If you know。

 the input is always the binary entropy。Of F。Okay， and so that's the answer。

 that's the thing we just sketched。 And now you sketch this。And you've got your proof。Okay。

 it's not a complete proof。 right， You can prove it。 It's in the book， as well。

When you maximize this。What you get is the capacity of the binaryno symmetric channel with the flip flip probability of F is  one minus H2。

Of F。Okay， I said I didn't prove it。 Well， actually， here's a proof。

 What's the biggest value that the binary entropy function can possibly have。

 The biggest value it can have is one。Here's H2 of x。Has X。Varies between 0 and 1。

 The biggest value it can have is  one。 It's achieved when the argument in here is a half。Q E， D。

 the biggest match， the biggest mutual information you can have is 1 minus H2 of F。

 There's no dependence on P1 in there。 So there's a proof。

 And you achieve that by making sure that the argument here is a half and。Indeed。

 setting P1 equal to half does that for you。 Okay， you got yourself a proof。

So what we've worked out is the capacity of the binary symmetric channel。

With a flip probability of F。And now what we want to do next is we'll carry on exploring this idea of what is the capacity of a channel。

 But the real goal is to prove that this capacity actually measures how fast you can reliably communicate over the channel。

 And that's an amazingly profound result， but we'll get there by the end of the next lecture。😊。

So where we're heading is we want to prove Shannon's noisy channel coding theorem。

 which says that reliable， that is virtually error free communication is possible over this channel at rates up to。

😊，At any rate， up to the capacity of the channel。Okay。So let's do a few more examples。

And then next time， we will indicate how to prove。Ms。 Theorem。



![](img/74e3067b49176b87d0e6507f741e1042_10.png)

So for the binary symmetric channel， it's not at all obvious that you can communicate reliably at this rate。

 If we're talking about the channel with a flip probability of F equals0。1。

And this capacity is roughly0。53。So that， the assertion in this theorem is that you can take。

Lousy disk drives that flip 10% of the bits， combine two of them together in a coming way。

 and you can achieve you can emulate a perfect。😊，Single disk drive using the two lousy disk drives。

So that's not at all obvious。 Let's look at some other example channels where maybe it's a little bit more obvious。

嗯。Whether this theorem is correct。 So let's start by looking at。A channel with four inputs。

And for outputs。Which has this。Set of conditional probabilities。

Please work out what the capacity of this channel is。 And then when you've done that。

 see if you can invent an encoding and decoding method to communicate at that rate over the channel。

😊。

![](img/74e3067b49176b87d0e6507f741e1042_12.png)

。Okay， what is the optimal input distribution first。Anyone。Uniform distribution。 think。

Seems a reasonable guess by symmetry。And what's the capacity if you use。That input distribution。2 B。

 okay。So where does that come from， Well， we can write it down either way， Entropy of output minus。

Interry output given inputs， for example。If you use this input distribution。

 the output distribution is also uniform。The entropy of the uniform distribution is。2 Bs。

 because it's。Look for。And if you know what the input is， then the entropy of the output。

Is 0 because it's a certain distribution。Okay。So that's 2 Bs。 Okay。

 can we communicate reliably over this channel， Yes。

 because you could take someone who's got a load of bits。 And you can say every time you get 0，0。😊，0。

1，1，0， or 1，1， respectively， for the next two bits in your source， turn them into As。

 B Cs and D's in this way and then use the mapping back again。Okay， so that's a trivial case。

Let's now。Mentioned two more cases。Which willll do。In the next lecture。

So this channel is called the Ternary Confus Chanel。And。If you put in A's， you get at M。

If you put in C's， you get our Ns， and if you put in Bs。You get。Random， M or N。Okay。

So where we're heading with this task。Is we want to know what's the optimal input distribution。

 But to start with， let me ask you， if you put in a third or third a third。Now。

 what's the mutual information。 So have a chat to your neighbor and work out an answer for that。

 And then if you're， if you've done the first questions。The next question is。

 what's the optimal input distribution and what's the capacity。



![](img/74e3067b49176b87d0e6507f741e1042_14.png)

So when I say what's X， obviously， the answer is， you're not sure what I'm really asking what's the。

 is what is the probability distribution of X given that information。Okay。

And we'll got an answer to this first question。 What is。X。

 assuming this input distribution and assuming that you see an output。Y equals M。

What's the probability distribution of x。Any guesses or answers。No。Okay， what could X be within M。

 It could be A or B。Are they equally likely？Let me give you a hint。Okay。This is called A。

This is called C。And way the channel works， this is called B。Okay， when you pick an input。

You pick a card， you pick one of the three cards， A E， B， or C。

 and then it gets plopped down on the table at random。

So it might be this one or this one or this one。 And what the output is M or N is。

 is it white or is it brown。Okay。さな。If you see y equals M， which means you see。White。

What's the probability that the input was the all white card And what's the probability that it was B。

 the double sided card。Anyone？It's going to be two third， one per0。Okay。Two thirds。One third。0ero。

If you're here last week， then this was all familiar because this was an inference problem we did last week。

Okay。So 20，1， third 0。And what is the mutual information。

 Please turn to your neighbor and work this out。Okay。What's the mutual information。

 assuming this input distribution， Here's five things for you to choose from。

 or Oomega is something else that I've not written down。Are you ready。

 Votes for option A log base 2 of 3。Minus the binary entropy of one third。Any vote for that。能。

Votes for 1 minus a third， which is two thirds。Okay， four votes。Votes for log 3 minus the third。

For lot three minus1。For half minus log 3。For something else。And votes for， I don't know。

 I should have asked for that first， O。Right， sorry， I didn't give you quite long enough there。

So probably I should have left you a little bit longer because the interesting thing is， typically。

 if you have a careful audience， about half of the people vote for a and a half of the vote people vote for B。

 because both of these are correct。 And you get each of them by doing the calculation。

 the two different possible ways around。 So you can either say what's the entropy of the input distribution。

 log 3， And then you say what's the entropy of the input。 If you know the output。

 And we just work that out。 It's the binary entropy of this distribution， whichever thing happens。

 So that's a very quick argument for obviously， it's log 3 minus the binary entropy of a third。😊。

Okay， so this is correct。But it's also true。 You can evaluate it this way。 You can say。

 what's the entropy of the output。 So if I pick a card and show you。The face。

 What's the probability of it being black or white， brown or white。 That's1 bit。 It's 5050。

And what's the entropy of the output。 If you know the input。 Well， if you know the input。

 now you have to sum over all the possible cases。 There's a one third chance that you certainly get the output M。

 So a certain distribution has no entropy。There's also a one third chance that you pick a C and you have a certain N。

Which has no entropy。 And there's a one third chance。That you pick。The brown and white card。

 And there's a 50，50 chance。 you'll see brown and white and the entropy of that distribution。

Is one bit。Which gives you1 minus a third， which is correct。So both of these answers are right。

 And it's not at all obvious that these two mathematical quantities are equal to each other。Okay， so。

The next question is， what's the capacity of this channel。All right。

That means you now get to pick the input distribution。 Do you want a third or third a third。

 or can you think of a better input distribution， If someone's gonna pick one of these cards to try and communicate with you。

 what distribution would you like them to pick from so that you can communicate as much as possible。

 Have a chat your neighbor And then we'll wrap up。

![](img/74e3067b49176b87d0e6507f741e1042_16.png)

Okay。What's the up input input distribution and what's the capacity。Okay。

 the optimal input distribution is a half， not half。

 So we throw away this stupid cardca it's useless。 It doesn't help。 It Just injects nice。

 We keep these two。And the capacity is。办了。1 bit。Because now we've got ourselves a channel that looks like that。

 two inputs， two outputs。Okay。Very good。Any questions。Right， so that was a slightly silly channel。

Next time， we will start with this very simple but slightly more interesting channel。

 the noisy typewriter。It's got circular symmetry。 Every input maps to three possible outputs。

 And the questions are， what's the optimal input distribution and what is the capacity。

I'll start with that question。 Then we will prove the noisy Ta coding theorem。

 at least for the binary symmetric channel。 And in the book， you can find the general proof as well。

Finally， here's some recommended homework for you to do。 some recommended exercises on the website。

 which you can find by looking for I TP R N N。 There is a handout with some more recommended exercises from the book。

 And also there's some software on the website。 if you want to make Huffman programs or rather。

 if you want to have a Huffman program that makes optimal Huffman codes for you。

 This is especially for the data compression exercise where I said。

 please make a compression method to compress an output from the bent coin with lots of zeros and a small number of ones。

😊。

![](img/74e3067b49176b87d0e6507f741e1042_18.png)

Okay， thanks very much for coming And see you next time， hopefully。😊。



![](img/74e3067b49176b87d0e6507f741e1042_20.png)