# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P6：-06-Lecture 6_ Noisy Channel Coding (I)_ Inference and Information Measures for - GPT中英字幕课程资源 - BV1er421M7Br

![](img/e80d2d285ddb8d41149ad04c607240ef_0.png)

Welcome again。 today， I'll recap what we've done in data compression。

 and then we'll get back to the central topic， if you like， of the information theory course。

 which is noisy channel coding， which we looked at in lecture 1。😊。

Let me start with a little question I set for you last time。The question is about this ensemble。

 ABC D with probability to half a quarter，8th and 8th， and with the symbol code。Sn there。

 And the question is， if we are encoding from this source and then we reach into the encoded stream and pluck out one bit。

 What's the probability that it's a one。 Please talk to your neighbor about your answer to this question。



![](img/e80d2d285ddb8d41149ad04c607240ef_2.png)

![](img/e80d2d285ddb8d41149ad04c607240ef_3.png)

Okay。WellLet's have a quick vote。 There are three options there you've worked out P1。

 I hope you've talked to your neighbor about it， and。I'm gonna ask you。

 is your P on less than a half half or bigger than a half， And you can also vote for Z， which is。

 I don't know。 Votes for Z。 I don't know。Okay， votes for A P1 is less than a half。Okay。

 got a few votes there for。For a votes for B， P1 is equal to half。Wen。One vote for B。Votes for C。

 P1 is bigger than a half。Everyone else， except the people who， okay。

 we've got one there and no one voted for Zed。 So everyone else must be asleep already。Okay， well。

 we've got a range of of answers there。 people from community A who've got P1 less than a half。

Could a volunteer take us through the argument What。

 What is your P1 and what was your method for calculating P1。Since you' were in the majority。Okay。

 who voted Ray。Alright， what was， what was your P1。What was the value。Anyone。Unknown。Okay。Well。

 can I help that。Let's talk about。The fraction。Of the code word that is made of ones and see what happens if we look at that。

 so。Code word A， the code word for a， which happens half the time。Has got 0。Ones in it。

 code word B is half ones。 Code word C is two third ones， and D is 100%。1， so I'。

 I've defined a thing called F I。 It's the fraction of the code word， which is ones。

So a lot of people are voting for A， but you're being very shy about saying why。

 And I'm gonna now give a possible argument that might give an answer that's in the A camp， so。

We pick a code word first with these probabilities。

 Then we pick a random bit to see if it's a1 or a 0。

 And these are the probabilities of it being a  one or a 0。

 So here's a calculation probability of getting a one。 I'll put a question mark on it， because。

I want to check if I've got your reasoning right。 Prob of getting a one is a sum over all letters in the alphabet。

Probability of picking that letter。Times the probability of it turning out to be a one when you pick a random bit from the code word。

 Yeah， is that the sort of reasoning that the a community went for。

 You're allowed to nod if talking is difficult difficult。 Okay， we're getting some nods。 right。

 so we add that up。 and we've got a half times 0。Plus a quarter。Times。然后。Plus。And8。Times two thirds。

Lessson 8。Times 1。Alright， which gives us。1，8。Plus。And8。Plus。And8 times two thirds。Which is。1。

8 times 2， and two thirds。2 and two thirds is 8 over 3。Which has given us one third。Okay。

 does anyone who voted for a think that this is roughly why they voted for a hands up。 If that's so。

 okay， we， we're get， we're getting somewhere。 So there's a candidateid answer there of a third。

But not everyone agreed。 We've got some Bes and Cs。 Does anyone want to。Challenge this and say， no。

 it's wrong。 Here's an argument why that's wrong。Anyone。Or has everyone gone over to the A side。Yeah。

😊，Yeah， Martin。Okay， so Martin just said， if you reach into the stream and some of the code words are long and some are short and you reach in and pick a random bit。

 you're more likely to hit one of the long code words。Right。

 so this isn't the correct way to pick a random bit from the stream。

 We need to take into account the lengths。So that's a good argument。 Okay， so this is probably wrong。

 At least it's the wrong method。 It may not be the wrong answer。So， length matter。

Length of code words。买车。Any other argument for an alternative answer。Okay。

 let me give you one other argument for this。 And then we'll do the calculation again。

What's the information content of this probability。Here， and。1 B，2 B，3 B and 3 B。

 What's the ideal encoded lengths for probabilities。

 The ideal encoded length are the Shannon information contents， which are。from now on。

 I would just call them the information contents。What are the lengths of these code words。

 lengthngth I is 1，2，3， and 3。 So the lengths match the information contents。

 So this is a case where we have a symbol code。With perfectly matched code lengths。

To the probabilities。That means you can't compress any better than this。

Because we have our source coding theorem that says you can compress down to the entropy。

 And if the expect， if the length of your code words match the information contents。

 it's unbeatably good。😊，And this is a valid code。 It's a prefix code。 So this， this will work。Now。

 if we use this code to encode stuff from the source。

And if it were the case that the bits coming out after encoding。Were not 50，500s and ones。

 completely random， independent， unrelated to each other。If they， if they were not 5050。

Then we could compress it some more。Because Shannon says， if the probabilities aren't 5050。

 we can make codes， you know， with。Justusin bags full of lottery tickets and all that sort of stuff。

 We could do further compression。But you can't compress anymore because we've already got it down to the entropy。

 Therefore， without doing any calculation at all， it must be the case that P1 is a half。

 So B is the right answer。Because it's perfectly compressed。 And if it's perfectly compressed。

 it'll look random。Okay， so the right answer。There's B。 So what went wrong with this calculation。

 Well， let's just redo it， and。Do the calculation in a way that takes into account length。

Let's think about it this way。 We've got a great big bucket。 We're going to。Put bits into the bucket。

Each time you pick a code word， some more。Bits go in the bucket， and some of those are ones。

 And we're interested in the ratio in this bucket。 What fraction of them are ones。

So let's give ourselves an extra column in here， which is not the fraction that are ones。

 but the actual number that are ones。So the number of ones in this code where is 0 in this one。

 it's 1 in this one， it's 2。 And in this one， it's 3。So on average， when I pick another code word。

How many new bits go into the code word， We'll put that downstairs。And the answer is， ser over I， P。

 I。L I。And on average， how many ones go into the bucket。Oh， that's some over eye， the I。And I。Okay。

 how does that differ from what we did over here， Well， F I is the ratio of N I。Over。L I。

 so you can see。We're using a different thing upstairs。 and to compensate for that。

 We're using something different downstairs。Okay， so this is the average number of ones that go in the bucket。

 Whenever you pick a new code word， This is the average number of bits that go in。

 The ratio of those is gonna be the fraction of bits that are ones。 And if we do that。We have the。

Upstairs， thing is。Half times 0。Plus， a quarter。Times。Wang。Plus， and 8。Times 2 plus。And 8 times 3。

 And downstairs， it's our old friend， the expected length， which is the entropy。

Of this probability distribution， which is。Is it not 7 over 4。I'm doing this in memory。

And what's upstairs。That's the quarter。And来。3，8。And that's a quarter。So in 8。

 we've got2 plus 2 plus 3， which is 7 over 8。I was seven before。我知啥。

So that's the long way to get to the answer that the sneaky information theory based answer is just to say it's perfectly compressed。

😊，Case closed。 It's 5050。And it's not only 50，50。 It's got no correlations in it at all。

 there can be no correlations in the encoded stream， because otherwise。

 we could use the information theory argument and say， oh， those correlations could be exploited。

 Those dependencies。Any questions。So we love information theory。 It provides you with very powerful。

 very brief arguments for things that mean that you don't need to do calculations anymore。Last time。

 let me just recap what we did。 we introduced symbol codes。Or rather， the time before last。

 we introduced symbol codes。And。嗯。Symbol codes are widely used。

 We have a Huffman algorithm that gives you optimal symbol codes。

 and their expected length are within 1 B per character of the entropy。

But we argued in the previous lecture a week ago that doesn't actually wrap up compression。

 We don't like symbol codes because being within 1 B per character is not very good。

 If the actual entropy per character is something small， like 0。1 B。

 And we argued that often that will be the case。 if， say we're compressing English。

We played a game that gave us the idea that you could use identical twins at the sender and the receiver in order to make a compressor。

 And then we looked at arithmetic coding。 And arithmetic coding is this way of thinking about a binary file as defining a single real number between 0 and 1 to an extremely large precision and any source file can be represented in the same way as an corresponding to an interval on the real line between 0 and 1。

😊，And。I argued that when you do arithmetic coding， you will get compression down to within 2 Bs of the information content of the entire file。

 So this is， in terms of its overhead， this plus 2 is potentially about a factor of n smaller than the overhead you get if you use symbol codes。

 So athmetic coding is， in almost all cases， far， far better than symbol codes。And。

I just wanted to flesh out how you'd use arithmetic coding in practice。

 I talked about the idea of an oracle that being a piece of software。

 which uses some procedure to predict the next character。

 given all the characters X1 through X T-1 that have been seen。

 And I wanted to just give you an example of how this works in real state of the art compressors。

 So here is a fragment of Jane Austen's Emma。 this is the last 50 or so characters And the context is alarmed at the PR O。

 And the question is what comes next。 So how do real compress algorithms work。 Well。

 a fairly near state of the art compressor that's very widely used is a compressor called PM。

 And here's how PM works。 It's called prediction by partial match。 And it's slightly ad hoc。

 But there's a bunch of theoretical justifications and improvements we can make to it。

 But let me just describe the ad hoc method。 Here's the idea。😊。

at the context of the last five characters of the document to define the context for the next character。

Then we look at the entire file of everything that we've seen so far。 and we say。

 have we seen that context before in the entire file。

 So this is how we're going to then predict what happens next。

 But go and find all of those occurrences。 And here they are shown in blue。

 So E space PR R O has happened 1，2，3，4，5 times already in J Nousten's Emma。

 And this shows what happened next。 There was a V， A V and O， A P and an S。😊。

So a first stepb would be to say， let's use these 6 G statistics， the raw 6 gra statistics to say。

 alright， there's a 2，6，2， how many were 1，2，3，4，5。 It7 five times。

 So there's a two fifth chance of getting a V next。 There's a one fifth chance of an O。

 a one fifth chance for a P and a one fifthth chance of an S。

 but it also haven't seen that much data。 So wed better allow some probability for other things happening。

😊，How do we allow for other things happening？ Well， the PM approach is to say。

 let's back off to shorter length context as well and say what happened in context， space PR O， PR O。

 R O， O， and in any context at all and fold in those other1，2，3，4，5 possibilities。

 in addition to the 6 G statistics and weight them together in a a smartish way。

And that's how PM works。 And it gives you extremely good compression state of the art。😊。

On most files， it doesn't do as well as humans do。 Human audiences like yourselves can predict English a lot better。

 And clearly， it doesn't understand grammar and dictionaries and， and so forth。

 But it does a lot of learning of raw statistics。 And that gets you a long way towards good compression。

So that's PPM。It important all the individual five characters。Before。新です。Okay， so the question was。

 does it learn the 6 G statistics of the document of the entire document and then compress it。

 or does it do it on the fly， And the important answer is， it's just like you guys。

 the identical twin audiences， it does things on the fly。

 So when we're asked to predict in this context。 We then say。

 how often has espace PRO happened already before now， we don't look ahead into the future。

 So the predictions are based only on what we have already seen。😊，Okay， any other questions。

There's a couple more things I want to mention about arithmetic coding。 One is。

 as I showed you last time， we can make other uses of arithmetic coding。

 We can make an extremely efficient writing system。The 1 I showed you was called Daa。

 That's based on the idea that writing involves making gestures of some sort。

 maybe wiggling fingers or scribbling with a stick。

 And we want to turn those gestures into text as efficiently as possible。

And compression is all about taking text and turning it into a bit string。

 which in arithmetic coding is viewed viewed as a real number。

 And so we can make a very good writing system by saying， okay。

 let's have the gesture Just define a real number by steering our spaceship in a two dimensional world。

 And that will make us， if we turn it on its head a very efficient writing system。

 So we make your gesture and out text。 So that's the dash concept。😊，And I showed you that。

 and it's free software。 And help is always welcome to make Dsha better。😊。

And there's another application for arithmetic coding I wanted to mention。

 And this is the idea of efficiently generating random samples。Let me give you an example。

 Let's say I asked you to simulate a bent coin。 And I said， okay， let's fix P A。2， I don't know，0。01。

And PB is the rest。Please simulate。10 million tosses of this bent coin。

 And I will provide you with random bits， a random number generator。 The question is。

 how many bits will you need to use to generate 10 million。Tosses of this coin。

Let's say n from now on， instead of 10 million。A standard way of solving this problem is to say， oh。

 well， I'll use the random bits you can provide me with to make real numbers between 0 and 1。

 So I'll generate things that I'll think of as real numbers。Uniformly distributed between 0 and 1。

That will guzzle up 32 Bs per real number。If it's a standard random number generator。

 So we read in 32 B， interpret them as defining a number between 0 and 1。

 Then we look to see if U is less than P A。 And if it is， then we spit out an A， and otherwise。

 we spit it out a B。This method will cost you 32 B per character。Alright。

Can we do better And do we care， The answer is， yes and maybe。So， yes。

 we can do much better because we could take an arithmetic coder。😊，And think about it this way。

 Let's wipe the board。Imagine sticking a pin into the world of an arithmetic coder。😊。

What happens if you stick a pin。Uniformly at random into this line that goes from 0 to to 1。Or into。

而。Into one of those lines， what comes out， What's the probability。Of what comes out。

 If you stick in a pin and use it to select。A string of text。Have a chat to your neighbor。Okay。

 what I've drawn on the board here is a couple of different arithmetic coding worlds that run from 0 to 1。

This is one， for some source within alphabet with characters ABCD with different probabilities。

 And what we noticed last time was。The arithmetic coding method gives you intervals between 0 and 1。

 whose size is the probability of the string equaling that particular string。

 probability that X is a followed by C is the size of this little interval here。

Here I've drawn the one for the bent Co， is。99%。And this is 1%。

And then we recurse and subdivide this。In the same way。 And we get。

 this is the little bit for A E B in here。And then here's a bit for A， A B， and， and so forth。

Alright， if we come along and stick in a pin， the probability that the pin will land inside this interval here is this probability。

 So the probability that if you then read out the string we've got。

 the probability it will begin A C is the probability that a string begins with A C。

 So sticking in a pin at random is a way of picking a string from the probability distribution of your language model。

😊，Okay， so what we can do with bent coins is make the arithmetic decoder encoder and decoder for the bent coin。

Then bring along random bits， random lotss and worms so as to， to define where a pin goes in。

The the pin， you stick in a pin between 0 and 1。 You。

 you do that by having an infinite source of zeros and ones to define where we are on the line。

And so you start guzzling up those zeros and ones。 Find out where the pin is to the first bit，2 bit。

3 bit and start reading out bits with your decoder， reading out A's and B's with your decoder。

How many bits is that going to need， Well， on average， it's just like compression。

Whatever the binary entropy of0 。0aught1 is。Point1 or something like that。That's， on average。

 how many bits you will need。 So in contrast to needing 32 B。perer。Coin toss。

 You'll need this many bits。So the arithmetic coding method。

For generating random samples for the bent coin is going to need。Binal entropy of 。01 Bs。呃。Coin。Tos。

 which is smaller than one， quite a lot smaller than one。 So the。

 it's gonna be more than a factor of 32 times more efficient with your random bits。

 And if random bits are a valuable thing， you may well want to do this。 It。

 it may strike you as elegant。 and it may actually save you money。 And I want to close this。

Discussion by just giving you a little bit of evidence。

That we do actually care about saving random bits because random bits are not free。

 If you want random bits， you have to get them from somewhere。

 And if what you're doing has any sort of principle purpose。

 you need to verify that they're good random bits。And so here's a C。

 D that I received in the post a few years ago。 and the C， D came with a message saying that this C。

 D contains random bits and they've been generated thanks to the financial support of a couple of US government grants。

 and they're distributed under that grant from Florida State University to academics or around the world who want random bits。

 So random bits are valuable。 And this is proof that serious researchers and funders。

 food random bits as being important enough to actually spend US government money on。

 So that's an argument for not wanting to waste random bits。Any questions？Okay， we have now in。

But also another way of view live。First method you。Sugest it isn't optimal。

You could actually make numbers a lot。オプゼシにてで。O。So。最初とごつ。Yes， so the question is。

 are there other ways of thinking why this is a bad idea to do with the precision of the numbers you need。

 So to make this decision about， is it an A or a B。

 often you only need the first bit to already tell you， okay。We。

 we don't need to look at the next 31 Bs。 The first bit has already made the decisions。

 So we're wasting bits there。 and conversely。Actually。

 if you look in detail at the probability that this will spit out a one。

 It's not gonna be exactly 1%。 Is it， It'll be some ratio of sort of N。Let's call it。M over 2 to 32。

 where M is some integer。And so it's not actually gonna perfectly nail exact ratio。

 It'll be within one，1 part in 2 to 32， which is pretty good。 But it， it won't give you the right。

 exactly the right answer。So， yes， it， it's， it's wasteful because it's using loads of bits to make a decision about a single bit。

And arithmetic coding is better。Any other questions？Okay。

 so we're going to now move on to the topic of noisy channels。

 and noisy channels have inputs and outputs。 And one of the things we want to do with noisy channels is infer what the input might have been given the output of the channel。

 so。A theme of noisy channels is gonna be， we need to understand inference。

 And once we're clear on how to do inference， we'll also be talking about how to measure information content in the context of noisy channels。

 So we know how to measure information content for a single random variable。

 like tossing a bent coin or drawing a random letter from English。 It's all about log 1 over a P。

 And that's it。But for noisy channels， it's all a little bit more interesting because we've got inputs。

 We've got outputs。 We're interested in questions like。

 how much information does seeing this output convey about the input。

 So we want to learn how to do that。😊，And to start off with。

 I just want to give you a little puzzle to think about。And this it doesn't involve a noisy channel。

 It just involves three cards。And here are the three cards。

 and I'll introduce you to them one at a time。Here's a card， which is white。And white on the front。

Another verse， okay。Here's a card。 That's brown。On the front。 and the reverse。Rightright。

And here's a card that's brown on one side and white on the other。So we've got three cards。

 And now what I'm going to do is I'll shuffle them and turn them over randomly and hide them and draw one card at random。

And plunk it down in front of you so you can see it。

And then I'm gonna ask you about the other side of the card。 Alright。

 so I shuffle and random eyes andm not doing any magic tricks or anything else everything you see is what's happening。

😊，So we shuffle up， and then I randomly grab a cart and plunk it down like that。 alright。😊。

And I show you。The front one side of the card。 and it's white。 And the question is。

What's on the other side。The question is。Given that you're now seeing a white face。

What's the probability that the other face of this card is white。

 Please turn to your neighbor and have a chat about that question。



![](img/e80d2d285ddb8d41149ad04c607240ef_5.png)

![](img/e80d2d285ddb8d41149ad04c607240ef_6.png)

Okay。Votes for Zed， which means I don't know。Okay， we've got a few dons。

Votes for the probability is less than a half。Anyone， no votes。 It's bigger than a half。A few7 is。

And it's for C。 It's half。 It's 50，50。1，2，2，5，5，6 grand。 Okay。

 so we have some clear uncertainty about this grand。I like it。 when it happens't。

So let's have an argument from the second community。 Why is it 50，50。Anyone。Yeah。可以。Good。

 so the answer I just heard was by logic， it's either this card or that card that's sitting down there on the desk。

 And we don't have any additional information。 So it must be 50，50。Okay。

 and we've got a load of people who disagree with you。

 So would'd one of them like to give an argument why that compelling argument of logic was wrong。

 yes。There's basically three possible ways。Wfi。Two of which come across。Okay。

 so what I just heard was the three possible ways of getting a white thing facing up。

 You're either looking at that side or that side or that side。

 And all three of those possibilities are equally likely。

 So either this hypothesis or that one or that one。 And when we turn it out， turn it over。

 we'll find out。Whether the other side is this or the other side is this， or is that。

So that means it's two thirds。 Yeah， two thirds chance。It what。That argument。Stay towards。Good。

 does anyone want to add anything， change your mind， Give another argument。Vote for a。

Yeah don anything mean。SoPri that figures 50%，50%。In quite。And then we add more information。

ItHa to be important。呃。Okay， that's a nice argument。 So the argument said。

 think about the other side of the card， which is either gonna end up being white or brown。

 And right at the beginning， before I bought out the card， I could have asked you。

 please place a bet， I the the face that you can't see gonna be white or brown。 And we。

 we would say definitely 50，50， okay。😊，And now the question is。We see the front。

 Will that make us change our bet at all。Surely it must make a difference。

And that's a very credible argument that there， there is a dependence between the front and the back。

 So surely you shouldn't be betting 50，50 anymore。 It doesn't。

 This argument doesn't tell you what the right answer is， but it does argue， Def not 5050。

 because we've just learn something。We know something that we didn't know， and there is a dependence。

And that's a good argument， too。Alright。So let me give you a suggestion。

 always write down the probability of everything。And this is copyright Steve Girl。

Who is a professor over in the building next door。Write down the probability of ever of everything。

 all the variables in the problem。 Then you can condition on what has happened。

 and you will be able to deduce by the simple dose of probability。

 What the answer to your question is。So in this case， everything is。The front face。

And the reverse face。And before。I did the shuffling and drew the card out。

The probability of the front face being。White or black， and the reverse face being white or black。

 The probability of this pair of variables。Being white and white was one first。

The probability bit being brown and brown， was one third。And the probability of the。

Other two things is a third， Cause you get that by the third card， the black white card。

 this chap coming along。 and it's 50，50， which way he'll go。And so there's a sixth chance there。

's sixth chance there。 That is the joint probability of everything。And now。

 with this joint probability， we can。Condition。On data and anything else you want to throw in。

And data is what we're given。 And what we're given is we're in this world。 So today。

 the white face came up。 So we condition on front being white。

And we can then work out the probability that the reverse。Is。White， for example。

 by renorizing this probability distribution， and we get two thirds。Okay。

 this may not convince people who still really think it's 5050。 How it its 5050。

 How can you say it's two thirds。 That's rubbish。 And so I've got one final argument。

That I hope will help。And then once this argument has been accepted。

 maybe it will compel you to agree that it's a good idea to write down the probability of everything。

So here's the final argument。 And it's not that the reverse was indeed white。

 that happened to be true， but it didn't have to be。The argument goes like this。

 Imagine that we play this game lots of times。 And instead of asking， what's the probability。

 the other face is white， I always ask you the question。

 what's the probability that the other face is the same as the one you're seeing now， Okay， so。😊。

This one， they're the same。 This one， they're the same。 This one， they're not the same。

 So two thirds of the time， the face will be the same on the back as it is on the front。

So when you see a white， there's a twohirt chance that the back is white。 And when you see a brown。

 there's a twothhirt chance that the back is brown。Okay， so that's not based on probability theory。

 And I think it's a fairly compelling argument that the correct answer is two thirds。 And hopefully。

 that's convinced you that we should use probability theory。

 because if you can't actually reliably solve this exercise involving just one random variable。

 which is which card and another random variable， which is which way up it went。

 So it's a two random variable problem。 If a smart audience of graduates from Cambridge。😊。

Can't reliably solve this problem。 And Just say yeah， I I know it it's fine。 I've got the answer。

That really shows you， yeah， inference is a little bit tricky。 In isn't totally straightforward。

 Humans are often very good at inference。 But if you want to be sure you're getting it right。

 use probability theory because probability theory will always get you the right answer。😊，Okay。

Alright， so let's now talk some more about noisy channels。嗯。And actually。

 let me just remind myself what comes up。 Let， let's talk through， through this。

 where we're heading is we're gonna talk a bit， bit more about inference。

And we're also going to talk about information measures for noisy channels。

Our classic noisy channel is the binary symmetric channel up there top right， which is obscured by a。

Wireless icon。Okay， go away， poof。Okay， the binary symmetric channel with inputs 0 and1。

 and it flips a fraction F of the bits。 So we'll talk a lot about that channel in due course。

 But we want to understand coding theory for any noisy channel。

And whenever were dealing with noisy channels， we need to know how to do inference。

 And I used to introduce people to inference with a different puzzle。 instead of the three cards。

 I would show people the three doors problem where the game show host says。

 here's the rules of the game。 I'm gonna hide a very desirable prize here。 a national rail pass。😊。

FromBehi one of these three doors。The game to host always explains the rules first before the game happens。

 and the rules are， I will hide the prize behind one of these doors。 Then I will ask you。

 the player to choose a door。 or you have a free choice， and you choose it by naming it。

 And we don't open it。Then I， the game show host， guarantee that I will open another of the doors。

 not the one you chose。 And I guarantee when I do that， promise me， I promise you。

 trust me that the prize will not be revealed at that stage。

So then the prize is clearly either behind door 1 or door 2 in this example shown here。

 Do 1 being the one you chosen。 Do 2 being the other door that he didn't open。

 And then the player gets the chance to stick or switch， if you want。

And then you'll get what's behind the final door you end up at after either sticking or switching。

And the options for this puzzle then worked like this。 That was the rules being explained。 Now。

 Now you go ahead and play the game。The player chooses door 1。

 The host says in accordance with the rules， I will now open either door 2 or door 3 and will not reveal the price。

 And as promised he。He opened the door， It's door3。It doesn't reveal the price。And the question is。

Should you stick？Should you switch。Or does it make no difference。

And I used to use this as my introductory example on probability theory。

 because people would argue very hotly about him and say， well， it's either behind door one。

 door one or2。 It's 50，50。 Yeah， this empty door doesn't make any difference。 It's 5050。

And other people would say， oh， no， no， no， you， you should switch。

 And some people would say you should stick。嗯。And it used to be contentious。 But unfortunately。

 most people have heard of this puzzle。 And so it doesn't really work anymore。 Wait。

 let's have a quick vote， votes for a。Votes for B。 You should switch。 votetes for C。

 It makes no difference。 So you see， it's a useless educational device。

It's been ruined because everyone's gone and talked about it。

 And the really annoying thing is they've talked about it in a way such that no one has actually learnedt anything。

And you are my proof of that， because a moment ago， you voted for a lot of you。 You know。

 not all the proof。 but this lot，ep， this controversy here between B and C。

Proves that an educational disaster has happened。 The Three doors puzzle。

 which is a fantastic puzzle。 It's really educational。

 has been ruined because everyone now knows the answer， but they don't understand it。😊，ABC here。

 These are exactly equivalent to each other。 The three cards and the three doors。

 They are the same problem as each other。 And yet I showed you the same problem。

 and you didn't get it right， even though you'd allegedly learn the answer。

 So learning isn't about memorizing things。 It's about understanding。

 So that's my little rant on the three doors。😊，So。The message people should be getting from the three doors problem is don't memorize the answer to a stupid puzzle because then you'll be useless at solving future inference problems。

 Instead， learn the message that you should use probability theory。

 and then you will be equipped to solve any puzzle of this type in the future。Okay， ran over。

So what should we do now， Let's talk about noisy channels。

What we're going to do with noisy channels is they're always going to have an input and an output。

And a channel defines a set of conditional distributions。 If you condition on an input。

 the channel defines what the probability of the output is going be。

 The channel doesn't define a joint distribution。 It just defines a set of conditional distributions。

And we can only actually do inference if we've got the probability of everything。

 So we need a joint distribution。So I'm going to run through a very simple example where I assume I've got a joint distribution。

Okay。R we here。I'll write down a joint distribution。

 and I'll define some information measures for that joint distribution。

Then when we move on to channels， we'll have to get a joint distribution by。

Adding to the conditional distributions defined by the channel， distribution on the inputs。

 So that's how it's all're gonna join up。 But I'll start with a joint distribution， or a joint。

Ensemble。And here's an example of one。And I'll define all the different information measures we can。

Make for this joint ensemble。 So I'm gonna tell you the joint probability of two random variables。

 X and Y， which are dependent random variables， a bit like the front and the back。Of the three cards。

So the first variable X can take on values 1，2，3， or 4。 Y can take on values 1，2，3， or 4。

And the joint probabilities are。1，8th，1，16th，1，32th。1，32th。1，16th，1，8th。1，32。132。16。All across。

 And then a quarter。And 0 and 0。 and 0。From a joint distribution， you can always define marginals。

And marginal probabilities。Are writtenriten in the margins。And they are playing by adding up。

 And here we have a quarter， a quarter， a quarter and a quarter as it happens for the probability of y。

 And then in the bottom margin， we have a half one quarter。1，8。1，8。Now。

We already defined for a single random variable， how to measure its entropy。

And so when we've got a joint ensemble， there's a bunch of straightforward things we can do with that entropy definition。

We can write down what the。Marginal entropy of x is。

 And we can write down what the marginal entropy of y is， for example。So I'm defining for you。

 by example。What marginal entropy means， marginal entropy of x is the entropy of this distribution here。

 And that is 7 over 4。Fix。The marginal entropy of y is the entropy of this distribution。

 And that's 2 bit。And we can define the entropy of the pair X， Y。 So you could think of the pair X。

 Y as being a single random variable that takes on these 16 possible values with these 16 probabilities。

 written hip。 And you can say what's the entropy of this。Distribution here。

So we just do the normal sum over all pairs， X， Y。Here， that's why。Log basease2。1 over P of X and Y。

Okay， and that comes out to 27 over 8。Bits for this。Joint distribution。And。

Those numbers I've just written down。 These three numbers have the property that if you show them。

Graphically。And draw H of x that way。An H of x and y。This way。

And then you try and make H of Y nudge up against this right hand side here。

You find they don't quite match up。 So H of X and H and of y added together are a bit bigger than H of X and y。

 for this example。 And this is actually always true that these guys will always overlap or they might just up。

 a but up against each other and exactly add up to the joint entropy。 And they only ever do that。

 if X and Y are independent random variables。 So the size of this overlap here。

Is a measure of how much dependence there is between the random variables。

Let me define a few more things we can do with a joint distribution。

 We can define conditional probabilities。For example， P of X given Y is。

Defined to be the joint probability of x and Y， divided by。probabilityb of y。

And we can write that out。For all 16。Values of x and y。So here is P of X， given y。For y。

 going from 1 to，3，4 and x going 1，2，3，4。 So if we condition on y being 1。

 then we can read out that top row probability and normalize it。 And we get a half a quarter，1，8，1，8。

The next row goes a quarter， a half，1，8，1，8。 when we normalize it。When we normalize the third row。

 they're all equal。 So we get a quarter。A quarter， a quarter。孔过证。AndWhen we normalize the bottom row。

 we get 1，0，0，0。So those four probability vectors are the four possible conditional distributions。

And for every one of those probability distributions， we can write down its entropy。

 so we can write down the entropy of X， given that y is equal to1。

 We can write down the entropy of x。Given that y equals 2 and so forth。

And the entropy of this guy here， this distribution， is's fairly familiar。 It's 7 over 4。 this one。

7 over 4 as well。This one。Entropy of the uniform distribution is 2 B。

In the entropy of one and 3 zeros。Is 0 bit， because it's a certain distribution。

 We know conditional Y being 4， that x is definitely one。So what do we think about that， Well。

 we noticed that it's possible。For the conditional entropy of X， given a particular value of y to be。

The same as what we started with，7， over 4， or the same。哦，被告人。Or smaller。 So you， when you get data。

About why。It's possible for your uncertainty about X to either go up， stay the same or get less。So。

 that's an interesting observation。And something we can do with all of these， is we could say。

 on average， when we learn why。How much information content will X then have。

 So what's the average entropy of x。Given why。 So I'm now defining for you a thing called the conditional entropy。

All of these were conditional en， as well。There were four particular conditional entroies。

 for particular values of y。 And then this is the really important one。 The conditional entropy。

 which is the average averaging over all possible values of y， waiting together， the entropy of x。

 given that value of y。 Notice I'm carefully consistently using little y to mean a particular value and capital Y is the name of the the random variable itself。

😊，Okay， and that adds up to 11 over 8。Bits。Similarly。

 we can work out what the entropy of Y given X is。Similarly。Go through the calculation， and you get。

13 over 8。Fish。No。In this case， I pointed out that the entropy of x。

 when you learn Y could stay the same， could go up or could go down。

When we worked out the conditional entropy， we got 11 over 8 B， and that is smaller than 7 over 4。

And let me now tell you a theorem。Which is that it is always the case。

That the conditional entropy with capital letters is less or equal to。The marginal entropy。

And finally， it can all be glued together like this in a single diagram。😊。

So this is not at all obvious， but it's true。That H of Y， given X fits here。And。H of x。Given why。

It here。And thus， we have rather nice word stories that we can tell。

 which is the total information that you get when you learn X and Y is the sum of the information you get when you learn Y plus the amount of information you then get when having already learned Y。

 you then go on to learn X。😊，Or the information content of X and Y。

 on average is the information content of learning X by itself， then already knowing X， learning y。

Okay， so the sum of these two is this thing here。And this overlap here， as I said。

 is a measure of dependence between these variables。

The relationship I just said about this plus this， equaling that。

 Some people call it the chain rule for entropy。The final thing I want to do is define this creature here。

This measure of dependence between X and y is going be a lot of fun when we play with channels。😊。

It's gonna be the most important thing we want to know。 And it's called the mutual information。

Between。The random of variables， X and Y， and we call it I。Of x semi co y。

And it's what it shows in the picture。 So you can pick any way of obtaining this from the picture。

 For example， it's the difference between H of X and H of X given y。Or it's the difference between。

8 of y。And。H of Y given x。And that's the mutual information。

What we're going to do in the next lecture is glue this together with a channel。

Ater is a set of conditional distributions。So for the binarysymmetric channel。

It doesn't specify how often you should use the 0 and the  one。 It just says if you send a 0。

 there's a 90% chance， you'll get a 0 out。 If you send a one， there's a 90% chance。

 you'll get a one out。 So the channel defines conditional distributions。

And then we can turn those conditional distributions if we want to into a joint distribution on input and output by inventing a probability distribution for the input。

 Then you can compute all of these information measures for the joint distribution you've defined。

 And when we've done that， we can start talking about the theory of how to communicate reliably over noisy channels。

Are there any questions。Okay， thanks very much for coming and see you next week。😊。



![](img/e80d2d285ddb8d41149ad04c607240ef_8.png)

![](img/e80d2d285ddb8d41149ad04c607240ef_9.png)