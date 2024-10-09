# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P77：L77- Markov Chains & Transition Matrices - ShowMeAI - BV1Sq4y1K7tZ

This video is my second video on Markov chains。 and if you haven't seen the first video of Markov chains。

 check out the link down in the description In this video。

 we're gonna to use some formalisms of linear algebra， the idea of matrices。

 the idea of vectors and how to multiply those to make the kinds of mans that we need to do when studying a Markov chain much。

 much simpler。 And in the introduction video we ended with a computational difficulty that we're going to solve in this particular video So here's the idea imagine I have a transition diagram。

 That's what this is。 a transition diagram lists the possible states of some system。

 So in this example it might be in state A or state B。

 And then there's a bunch of arrows between those states。

 and the numbers on each arrow described the probability。 So for example， the 0。

75 that is on the arrow that goes from state A to state A represents that there's a 75% probability that state A and。

😊，One iteration is going to transition to being state A in the next。

So what Im going do first is introduce some notation to help me describe different things。

 The first is going to be what I will call s not and this is referred to as the initial state of the system and it's a vector it's got a1 and a0。

 So what does that mean。 So basically the top component of my vector refers to state A and the bottom component to state B。

 if you had more components in your system ABC， for example。

 than you'd have three components in your vector and the fact that it says1 and0 means there's a 100% probability that it starts in state A and a 0% probability it starts in state B。

 I just asserted this， but it could have been something different。

 perhaps your initial state would have two different probabilities that would add up to1。

 So this s not vector is just a little bit of formalism to encode the initial state of the system indeed I sort of highlighted that in pink in my transition diagram is to illustrate I'm starting at state A。

Okay， then I want to go to S1。😡，S1 is the state after one iteration， that is if I start at my S0。

 my initial state and I go one iteration into the future， I am then at S1。

 the state after one iteration。And likewise， the 0。75 and the 0。25。

 the top number is still referred to as the state A and the second number is referred to as the state B。

 and so the 0。75 in the S1 is referring to the fact that there's a 75% chance of it being back in state A after one iteration。

So then the question becomes how can I manipulate to go from the S0 to the S1 I mean in this case we were able to sort of figure out what the S1 was just by looking at the diagram。

 but I could then follow up on this well how do I go from S1 to S2。

 the state after two iterations or S2 to S100， is there a process that allows me to do those types of manipulations efficiently？

😡，And indeed， the answer is yes， there is， and we're going to use the notion of a matrix。

How this works is let's consider the transition diagram there are four numbers so let me just forget the rest of the diagram for a moment and just pull those four numbers together This is going to be called a matrix then array of different numbers the way I think about this is I imagine that my columns are denoted with an A and a B and I imagine that my rows are denoted with an A and a B So something like the 0。

75 represents if I start in state A I will end up in state A。😡，Something like the 0。4 says。

 if I start in state B， it's in the second column， so if I start in state B。

 then I will end up in state A， that's what the 0。4 represents。

This type of matrix is called a transition matrix， and we often just write it as P for the transition matrix。

 Now here is the magic of matrix algebra。 The formula to go from s to s1 it just multiplying by this matrix P In other words。

 S1 is P times s and if I want to write that out with the actual information in this case。

 the s1 was the 0。75。25 the p was that matrix and the s n was the 10。

 this is matrix vector multiplication。 Now， if you don't know what matrix vector multiplication is。

 that's totally fine。 So I have a video for you that introduces matrix vector multiplication has nothing to do with mark of chain specifically because this little piece of algebra is useful all over the place。

 Ill encourage you check that video out and make sure you're comfortable doing matrix vector multiplication I'm just gonna assume that for the rest of this video。

 Nevertheless， for the purpose of this particular video all that's worth noting is that when you do this multiplication on the right you get exactly that vector that we predicted。

😊，On the left， now， thus far we haven't really gotten a big improvement because you are capable of coming up with the S1 just by looking at the diagram。

 we didn't need to do all this formalism。But what about going towards S2？The second state is again。

 just take that transition matrix and multiply it now to the S1。In other words。

 I can go and take a look at this， this is going to be a new multiplication。

 that same transition matrix， but multiplied by 0。75。

25 and if you do that matrix vector multiplication you get 0。66， 0。34 for the S2。😡。

Now I want to note that in the first video on Markov processes。

 we actually did this computation via a tree diagram and I showed how to justify it。

 and so right now I really just want to note that using this matrix method gives us the same answer that we've done in the past。

But now it generalizes what have I just done if I just look at this S2 is p times s1 S1 was p times s So in other words。

 what this is is p squared times s n and in general。

 if I wanted to figure out what the n state of my Markov processes would be。

 it would be just start the s start at the initial state and then multiply by n transition matrices p to the n and this is my final answer for how I can do manipulations in Markov chains。

 the n state is just this transition matrix multiply n times to the initial state。😡。

So if you're given a problem about a Markov process。

 the main steps are going to be to one write down that transition diagram so you can get all the numbers two take that transition diagram and put it into a matrix form and then three you can figure out any future state just by multiplication of that matrix a sufficient number of times Allright I hope you enjoyed this video on how to use transition matrices to solve problems and Markov chains if you have any questions about the video please leave them down in the comments if you like the video。

 give it a light for that YouTube algorithm and we'll do some more math in the next video。

