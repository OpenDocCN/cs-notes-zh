# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P8：-08-Lecture 8_ Noisy Channel Coding (III)_ The Noisy-Channel Coding Theorem.zh_e - GPT中英字幕课程资源 - BV1er421M7Br

![](img/199719264367b6848c83a6e735b56ad0_0.png)

Welcome to lecture 8 of information theory， pattern recognition and neural networks。

 This is one of the pinnacles of the course， where we will prove what for me is one of the most remarkable pieces of mathematics of the 20th century。

 Shannon's noisy channel coding theorem。 Id say we'll prove it。 The proof is in the book。

 will'll give a a partial proof。 and a complete proof for a special case。 today。😊，Where have we been。

 Well， last lecture， we defined the capacity of a channel。 A channel is a set of inputs。

 each of which gives you a probability distribution over outputs。

The way you get the capacity of the channel is you invent a probability distribution on the inputs。

 You then define the mutual information between the inputs and the outputs。

 and you maximize that mutual information with respect to the arbitrary input distribution。

 That's a theoretical construct that gives you this quantity called the capacity。

And what we're going to prove today is that this isn't just an interesting number。

 It is actually the rate at which virtually error free communication is possible over that channel。

 And that's a really remarkable thing。 It's a sort of something for nothing result that you can achieve abitrarily reliable communication at nonzero rates as big as the capacity。

😊，So last time we defined the capacity and we started looking at a few simple examples of channels and asking the question。

 well， what is the capacity of this channel， And we looked at a few。

 And I left you with the exercise of looking at。The noisy typewriter。 So the first question is， okay。

 what is the optimal input distribution of this noisy typewriter and what's its capacity。

 So please turn to your neighbor and discuss your answer to this question。



![](img/199719264367b6848c83a6e735b56ad0_2.png)

Okay， who's got a capacity first， What's the capacity of this channel。Anyone。Okay。

 let me take you through it。It's the maximum possible mutual information that you can get between input and output。

 What's the mutual information。Well， you can write it in a。Pair of different possible ways。

 You can say it's the entropy of the output， minus the entropy of the output conditional on the input。

And we want to。Maximize that， so。What are these two objects。Well， the second one is。

What's the enpy of the output conditional on the input and any input gives rise to three possibilities with equal probability。

 So whatever input distribution you choose， the answer to this quantity is it's just log 3。

No choice about that。What's the entropy of the output？ Well。

 it's the entropy of whatever distribution you end up spitting out onto the outputs。

 If you always send B， then you get a distribution with only log 3 B of entropy。

 But if you use a uniform distribution on here， you can get a uniform distribution on the output。

What's the biggest possible entropy you could get on why the output answer。

 the entropy of the uniform distribution， Can you achieve that， Yes。

 I just told you one way of doing that。 So the answer is log 27。And。

That's the maximum value that this can have。 So this is the answer。Which is Lo night。

So that's the capacity。 And the optimal input distribution is the input distribution that achieved this maximum entropy on the outputs。

By symmetry， one way of doing that is to pick the uniform distribution。

 So the optimal input distribution is。1，27th，1，27th，1，27th。

And that is an input distribution that achieves this maximum。

Does anyone have any suggestion of an alternative input distribution。

Is this the unique one or other alternatives。Great， so if you pick only the letters， say B， E。

 H dot dot dot Z。

![](img/199719264367b6848c83a6e735b56ad0_4.png)

Then。You're putting one9 of the mass。On each of those options， every third， one。

And this has the nice property still that a uniform distribution on those inputs will splitit a uniform distribution of the outputs。

 Therefore， it achieves this maximum。 So it is an optimal input distribution。

 but it also gives you a hint of a way of communicating reliably with the noisy typewriter channel。

 Naly， you never use the other inputs。 You just use it inputs， B， E， H and Z。😊，And therefore。

 you can communicate reliably。 How fast can you communicate reliably。 Well。

 each time you use the channel， you can pick one of 9 possible inputs。 Therefore。

 you will be conveying log 9 bits per use of the channel。 So this is another case。

 slightly more interesting than the ones we had last week。😊。



![](img/199719264367b6848c83a6e735b56ad0_6.png)

This is a case where we can find a way of reliably communicating at capacity。

 So the noisy channel coding theorem is true for this channel。

 And this channel is giving us a bit of insight into how we actually solve communication over noisy channels。

 One of the messages of today's lecture is going be that if you use any channel a lot of times in sequence。

😊，Then that collection of， say， N uses of your noisy channel is a lot like a noisy typewriter。

 So what applies to the noisy typewriter applies to。Noisy channels， in general。So， where we're going。

Is。We want to establish Shannon's noisy channel coding theorem， which says。for any channel。

There exist coding schemes。Each of which will have a rate and a an error rate。

 a frequency of mistakes。The noisy channel coding theorem says that you can achieve。

Everywhere in this diagram， write the way down， arbitrarily close to 0 error probability while keeping the rate finite at the capacity C of the channel。

 which we have just defined it。 The maximum nuclear information。 So everywhere here。Is achievable。

Whereas here is non achievable。 And the exciting part of this theorem。Is。This bit。

 the fact that you can get arbitrary closer to 0 with communication rates as close as you like to the capacity。

 And so this is the really exciting。😊，Part of the diagram。对。

And that's what we're going to prove today。There are other bits of the theorem。

 namely that you can get anywhere in here as well。 That's proved in the book。

 And the fact that you can't achieve anything over here is also proved in the book。

 We won't do that today。So， here's the idea。For why we should believe this is true for a general channel。

We can introduce the idea of an extended channel， which means the channel that you get when you use the channel you first thought of n times in a row。

 So， for example， if we're dealing with a binary symmetric channel。

 you take n uses of it and you've now got yourself a channel whose possible inputs are。

Everything ranging from a string of n zeros。Lots of zeros and1。Lots of zeros，1，0， all the way up to。

 like that。 So you've got an input alphabet now size 2 to the N。For this example。

 extended channel and its output， alphabet is the same set of strings in this case。

 because the output of the binary symmetric channel looks。Has the same alphabet as the。Input。So。

Here you go。If we take our binary symmetric channel and we define this new extended channel。

 each of these inputs can give riseise in principle to any output at all。 But for large n。

 there will be a typical set of。Outputs。Like this。So if you send all zeroes。

You can be fairly sure if n is very large that you'll end up getting an output that has about F N ones F N flips。

Plus， or minus is something fairly small that's going as square root of n。

And that's our typical set for this particular input。 for the input next door to it。

 there's a typical set， which has a lot of overlap。So here's the typical set for this one。

 And every one of these has its typical set， and its neighbor will have。

An almost identical typical set。 And here's the typical set for this guy。And。😡，In general。

 for a general channel。If you take all of these。Overlappping typical sets。

And if you pick inputs to this extended channel by using a probability distribution on the inputs。

Of the type P， X that we've just been talking about when we define the capacity。

 So you pick each input bit or each input symbol just from a distribution P， X。

 Then this collection of all the typical sets。That could come out here is going have a size 2 to the n times the entropy of y。

And the size of each of these typical sets。Will be about 2 to the N， H of y。Givenive x。Now。

 cast your mind back to the noisy typewriter。 Where did we get logged 9 B from？ Well。

 we took the total number of typical outputs， which was 27 possible outputs。 We divided that by 3。

 and we got 9。And that was how many non confusible inputs there were。Similarly here。

 we can take this extended channel as long as end's really large。

 and we can imagine that we might be able to come up with a set of non confusible inputs to this extended channel。

😊，And the number of non confusible。Inputs。When I say non confusible， I mean， almost certainly。



![](img/199719264367b6848c83a6e735b56ad0_8.png)

Non confusible inputs。Will be。The size of this typical set of outputs divided by the size of each of these blobs here。

2 to the an。H of Y。2。To to the end。H of y。Givenive x。Okay， which is due to the end。

Times the mutual information。Which is H of Y minus H of Y given x。

And so if I now repeat this little story， we just told picking inputs at random。

 but using the optimal input distribution， we will maximize this thing here。 And in that case。

 we will then establish that we could get。A set of non confusible inputs whose size is 2 to the n。

Times the capacity。Which means that each time you use the extended channel， which is end uses of the。

Original channel， we can communicate N C bits by picking one of those non confusible inputs。

So you can send N， C bits。Per and。Channel uses。Q E， D， and that's amazing。 That's the amazing result。

 This is not a proof。 It's just a sort of plausibility argument。

 It's to help you understand why this might be possible。😊。

What we're now going to do is we're going to actually prove this theorem for the special case of the binary symmetric channel。

 Yes， question。😊，it wasn't so clear to me why the size of you。5了。Okay。

In the case of the binary symmetric channel。The actual size of this entire space here is 2 to the N。

In general， for a general channel， it could be as big as alphabet size to the end。

 So for a general channel。If you've got an alphabet size， A Y。

 you take that and raise it to a power M。 That's the entire size of the conceivable alphabet。

But what I then said was， you pick the inputs from some distribution P， X。 And that's up to you。

And when you do that， you may find you're not using the full range of the output alphabet。

Which may or may not be a good thing。So you got to choose P， X。

 that then determined which typical inputs you're using。 So they might， you know。

 let's say you flipped a bent coin to determine which what your input sequence is。

 That would mean you never send this one because you never send ones。 You'd be sending a typical set。

 that's much smaller over here。 And similarly， you'd never get out of the channel all ones。

 because that's very improbable， too。 So it's possible if you want。

 you could pick a probability distribution P X。 such that you're not actually using the full input alphabet nor do you use the full output alphabet。

For a symmetric channel like this， you're absolutely right。 But when you do this optimization。

 and you say， how big can I make the set of non confusible inputs， The answer is， oh。

 make sure you've got a nice uniform distribution over the outputs。 And that's very often the case。

 but not always。Okay。Any other questions。All right。So。Here is the theorem we're going to improve。

And we'll make the theorem a bit more precise。 And I'll remind you what we already know about the binary symmetric channel。

 And then we will prove the theorem for the binary symmetric channel。Okay。

So let's write down a theorem。The theorem says。That。For the binarysymmetric channel。

With flip probability。F。The general theorem is for any channel。

 but we're gonna prove it for this particular case， the binarysymmetric channel。

With a flip probability， F。Whose capacity incidentally。Is C equals 1 minus H2 of F。Now。

 we get the theorem statement。For any。Epsilon， no matter how small， as long as it's bigger than 0。

 epsilon。Lurrks on this diagram。And for any rate。As long as it's smaller than the capacity。

 So anywhere in this yellow region。On this diagram。

You can pick an N the number of times you use the channel。

And the way I'll put that is for large enough n。Then you can make a code that will be this good。So。

For that Xilon and that R， and for sufficiently large N， there exists a code。With that length。

And with a rate。That's big and or equal to the R that has been requested。

And there's a decoder for that code。Such that。The probability。Of block error。Is less than。

The required value， epsilon that you've been given。All right。I'm gonna clean the board。

 And I'd like you to turn to your neighbor and remind yourself what you know about the 7。

4 hamming code， which we introduced in the first lecture。O。The 74 Hammoning code。

 when we encountered it in lecture 1。Looked like。This。We had our little encoding rule where we said。

 the user gets。To pick four bits， which are written here， S1， S 2， S 3， S4。

 then we use four constraints represented by these three constraints。 Sorry。

 represented by these three circles to set the remaining three of the seven transmitted bits，25，2，6。

T 7。Then we had a decoding rule that said。When you receive them， receive bits。

 you write them into this circle， This set of three circles。 you write in R 1， R 2。

 dot dot do dot dot R 7 into this diagram。 And you see which constraints are violated。

 That's called the syndrome。Which is a pattern of sort of happy and sad。Circleles。

 and then you use that syndrome to deduce。The most probable explanation。

The explanation being an account of which bits， you think probably were flipped。

 And then you could un fliplip those and deduce what the original 7 transmitted bits probably were。

Okay。So that was a 7，4 having code。 And it has the property that if you flip any one bit。

 if the channel flips any one bit， then that bit can be that error can be detected and corrected。

 And we use that for the binary symmetric channel to take the rate down from one。哎。

With the error probability of F。Down to something that was more of order F squared。 And so the 7。

4 havingmon code。Was a code with a rate of4/7th， rather than one。

And it had a smaller error probability。 So that was one of our nice examples of a block code。Now。

 on the screen， I'm showing you another way of defining the 7，4 haming code。 It's the same code。

 but I'm showing you the three constraints by a matrix。 And this is called the parity check。Matrix。

And the idea is。That for any linear code， you can define the set of constraints。By a set of rows。

 each constraint， we have three here， three circles， each。

Constraint is defined by a row of the matrix。Valid transmissions satisfy this equation。 H times t。

 where t is the transmission is equal to 0。 So that means that the top constraint gives you 0。

 The second gives you 0， and the third gives you 0。

 And the places where the ones are in this matrix is identifying which bits are in which circles。

 So this is the first。Circle here。This is the second。And this is a third。And circle 1 contains bits。

1，2，3， and 5， which is why the matrix goes 1，1，1，0，1，0，0。Okay。Circle 2 has 2，3，4， and 6。

 So we put a one in columns 2，3，4， and 6。And the third circle has。1，3，4， and 7， in it，1，3，4，7。And。

Because this particular code has the property that every one of the constraints has just got a lone。

 dangling extra parity bit sitting in it。 You have this nice。

 simple property that at the right hand side of this matrix。

 we've got a little identity matrix lurking here。And that makes the code very easy to encode。

 You just slap in whatever values you want for the first four bits。

 Then you can read out what these bits need to be set to。 But in general。

 you can make codes where you don't have a simple identity matrix sitting there。

 That makes encoding a bit more difficult。 You have to do some linear algebra。

 But you can imagine codes where we don't have this nice simplification。Nevertheless。

 you could come up with an encoding rule where the user sets some number of bits， K。

Which hair is for。And then the total transmission of N Bs here 7 is set in such a way that these constraints are satisfied。

Alright， so that's the general way of describing and codingd。

 We've got a list of constraints that must be satisfied。 The sender sets some of the bits。

 The constraints determine the other bits。Then， you receive。A received vector。

 which we're thinking of as being T plus n。 And when I say plus， I mean， modulo 2。

 So we're doing bitwise edition， modulular 2。We compute the syndrome。

 which is which circles are happy and which are sad by multiplying H times R。 That's called Z。

 Z is our name for the syndrome。H times R will shall， Sha I do an example。 Let's have an example。

 Let's say that we flip。Bit number 2。All right。Then whatever we transmit。

 the way this syndrome is gonna come out， since this is H times T plus N。

 that's equal to H times T plus H times N。Which is just H times n。

 because whatever we chose to transmit， satisfied H times T is 0。 So we lose the H T。

 and we're left with a syndrome that just depends on which bit we flipped。 If you flip bit 2。

 then the transmission， for example， might have been 0，1，0，0，0，0。Sorry。

 the transmission might have been all zeros。 The received might be 0，1，0，0。0，0，0。

 And if you multiply H times that thing。Written as a column vector。Then it'll spit out 1，1，0。

Which is。The three bits that you find in the second column across。Alright。

 and by looking at this syndrome， you can say， aha。

 which of these columns possibly could be an explanation for this syndrome。

 And you notice the second column across says 1，1，0。 And so you say， aha， that is the answer。 right。

 That's how easy syndrome decoding is in this case。 So you just look in the matrix。 And you say。

 what is the one column that could have explain this。😊，In general。

 if the noise has flipped more than one of the bits。

 it's maybe a harder task to do syndrome decoding。 You get some received R。 You hit it with H。

 and you get Z。And now the task is to say，That's H N。 I wonder what noise， the noise was。

 And this itself is actually an N P complete problem in general。

 But we're going to assume that we can solve that sort of problem and come up with a guess of N。

Which well call N hat。 So that's the job of the syndrome decokoda。 You give it a syndrome。

 It comes up with the most probable explanation。 The smallest weight noise vector that accounts for the syndrome。

Okay， so that's how the 7，4 Hammon code works， and。

The way I've described it leads itself very nicely to a generalization， namely for bigger n。

And for any code rate R that you're interested in， you can imagine making a much bigger matrix H。

 so you can make one。😊，With。N columns where N could be enormous， and M rows。And。

If we define K to be n minus M。Then。This set of constraints that we've written down。

Probably defines a code with a rate。 Something along the lines of R is K over n。

It may not be exactly this rate， because if the constraints you've written down are actually redundant。

 If you've got the same constraint twice， then it doesn't currently ought to subtract off one row for this to be right。

 So assuming that you haven't got any redundant constraints that imply each other。

 then this is the rate of your code。So I've now described for you the entire field of coding theory for binary channels。

 The task is just to come up with a parentity check matrix。

And you also need a decoder that can solve this。Problem here。

And the assertion of Shannon's noisy channel coding theorem is no matter how small the error probability and no matter how close the rate is to the capacity of the binaryish symmetric channel。

 you can actually find a linear code。 You don't have to do anything fancy and nonlinear。

 you can define a parity check matrix H that will get you as close as you like to the capacity and it can have an error probability as small as you like as long as we get to choose N and M sufficiently large。

😊，So that's the theorem we are now going to prove。And we're going to prove it with the help of something that we had a few weeks ago。

 Remember， when we proved that data compression was possible。

 we sent you off to the lottery ticket office and your task was to buy the smallest number of lottery tickets for the Benco lottery such that you could guarantee that you were going to win the Bencoin lottery。

And。We solved this by thinking about typical sets。 And you came home with a very large dustbin bag full of tickets。

On the front of every ticket was a string of zeros and ones of length n。

And all the tickets that you got had roughly a fraction F1s。

So the number of tickets that you bought was all the typical tickets。

 and the number of those we worked out was2 to the power n times the binary entropy of F plus a little bit to do with square root of n。

Which is small， compared to N。So that was how many tickets you had in your very big bag。

And we're now going to make use of those tickets to prove the noisy channel coding theorem， as well。

And you can imagine this working in two ways。If I tell you a theorem that there exists a good code。

 the standard way of proving such a theorem is then to describe how to make that good code。

 So I tell you what epsilon is required， what R is required。 And then you say。

 follow the following algorithm a bit， you know， like when we prove that you can make good symbol codes。

 We have the Huffman algorithm， which was the algorithm to construct the good symbol code。

So I' give you an epsilon and an R。 And it would be nice if I could just give you an algorithm and say。

 now， follow this algorithm。 and you will make a code。 And here it is。 And you follow the algorithm。

 out comes H an enormous great matrix， which has the property that its rate is bigger than R or equal to it and its error probability is small than epsilon。

 that would be called a constructive proof。 And proofs are polite in civil society。

 that if you say something is true， It's nice if you can actually show that it's true。😊。

And what we're now going to do is a rather outrageous thing。

 which is we're gonna have a noncon proof。 So I'm going to show you that this is true that there exist good codes。

 In fact， that almost all codes are good， but we're going to do it non-constructly。

 And it works like this。 let's have an analogy set in Iraq。

 So let's say some skeptics about world diplomacy， say that actually。

 in spite of our magnificentvent interventions in Iraq。 There exists a malnourished child in Iraq。

 which will be a sad outcome。😊，And one way you could do that is the constructive method that you identify the child whose weight is less than a kilogram。

 say let's say that's the definition of malnourishment。 The child weight is less than a kilogram。

 So you identify this malnourished child by name。 and you say there they are。

 And that's the street they live on。But Shannon's method is much cheekier。

 He gathers all the children in Iraq， puts absolutely all of them in a weighing machine。

 weighs all of them simultaneously and finds the total weight。

From which you can deduce the average weight of all the children in Iraq。

 And if that average weight is less than 1 kg， then that establishes。

 since they're all positive weights， there must be at least one baby with weight less than epson。

 In fact， you've established that almost all of them have weight less than epson。

 at least half of them must be malnourished。😊，Without ever identifying any particular one of them that is malnourished。

And that's the way we're going to prove Shanon's knowledge Tam coding theorem。

 I'm not actually going to tell you a particular way of making the parity check matrix。

 What we're going to do is a great big average over all parity check matrices。 And we'll say。

 what is the average probability of error of all of these codes。

 And it turns out to be much easier to answer that question than to identify one good code。😊。

We'll find that we can make the average probability of error of all the codes。Tiny。

 we can make it as small as we like。 Therefore， there exist good codes。 In fact。

 almost all codes are good。The task of actually making a good code is left as an exercise for the reader。

 And that's what coding theory is all about。 And that's another field with decades of work now under its belt。

Okay， so that's the plan of campaign。 And we're going to use our lottery tickets。 We're going to。

Use them in conjunction with the set of all conceivable parent check matrices。

 and we will prove the theorem。And the theorem here says， it said before。

 we've got the theorem on the board as well。 We've got the capacity definition。

 And we're going to show that we can achieve reliable communication。 Okay， what's next。😊，Here's the。

 the proof。 the steps we go through。We will take a linear block code。

 So well pick a particular parity check matrix H， which will actually end up picking at random。

 We imagine that we have chosen that。We can then define a syndrome decoder。

 using that particular code。Our syndrome decoder is not actually going to solve this problem perfectly。

 We're not going to find the most probable N。 I'm going to define for you an alternative decoder based on the syndrome。

 which is going to be good enough。And then having done that。

 we will defined an encoder and decoder for that particular code。

And then well go to average overall codes and find what the average probability of error is。

Let's just check what my next slide is。 Yeah， here we go。So this is what we're going to do。

Imagine that we have chosen a block length。 N。 We'll adjust that later on， if need be。

 to make it even larger。 So we've chosen a block length N。 We have gone to the bent coin lottery。

 and we won the bent coin lottery by buying a sufficiently large number of tickets。

 and they're all in the back。 And there are two to the N H2 of F of them， roughly。

We now take all of those tickets。 And instead of doing what we did a few weeks ago。

 which was we said， oh， we want to be systematic and write little short names on the reverse。

 We rub out those names that we wrote on the reverse and use that space for an equally short object。

 Namely， we're going to write down the syndrome of that noise vector， which is on the front。😊。

We're going to write down its syndrome using the parity check check matrix H that we've just chosen。

 And on the reverse， we'll write down the syndrome。 The syndrome is H times N。And that's。

An object whose length is M bits， okay。So you take every ticket。

On the front it's got a possible noise vector。 And if F is the flip rate of the channel we're dealing with that that's what I'm assuming。

 then you can be virtually certain that you own。The ticket that is going to have today's noise vector on it when we use the channel n times in succession。

 So you've already got the winning ticket。 And on every single ticket。

 you write on the reverse of that ticket what the syndrome would be of the noise vector。Okay。

So the syndrome you just compute by multiplying H times N audioo 2。Then what's my next slide。

Then what we're going to do is。Encode in the standard way， The standard way of encoding is you let。

The user set K of the bits。Then you set the remaining M bits。So we're going to set a transmission。

 which you can think of as T 1， T 2， T3， up to T K， which might not be in this order。

 But for simplicity， let's assume they are。 So you've got your first K transmitted bit set by the user。

 Then the remaining ones， T K plus one all the way up to T N get set。By using linear algebra。

To figure out what values these guys need to have in order that all of these constraints。

 H times t equals 0 are indeed satisfied。Alright， so that's encoding。And we send it over the channel。

 We get the received vector R， which is。Transmission plus noise。 We work out the syndrome。

Which is H times Z。Then we reach into the big dustbin bag full of tickets。

 and we look at the back of all of them until we find one that's got the syndrome on it。

Or maybe we find several that have that syndrome on it。Hopefully， there's only one。

 And we turn it over and we say， okay， that is our guess for N。So that's our decoding method。

This approach could fail in a couple of ways。It could be that we don't actually own the ticket that has the correct noise vector on it。

That's possible。But it's very unlikely because we've already bought enough tickets to have a 99。

9999999999% chance of winning the Benco lottery。Where we put enough nines into that，99。909 to get。

 so the epsilon。Is， is going be so that we're going to hit epsilon。So。The probability of error。

The probability of failure is a sum of two possibilities。

 One is we might not actually have the winning ticket。

The one that has the correct noise vector on it。The other possibility is we have got the winning ticket。

 but there's another ticket in the in the bag damnit， which has the same syndrome on it。

 So we don't actually know which noise vector happened。

So the probabilityative error is equal to sum of two terms。Which I'll call P1。AndP2。

P1 is the probability。That。And。Is not。In。The bank。This is the probability of error of the entire encoding and decoding system that we've just defined using a particular matrix H。

Of this。Code。With parity check matrix。H， so it's a probability of error that depends on H。

 The first term is the probability that n is not in the bag。

 And that actually doesn't depend on H because the bag we just bought。

 there nothing to do with H when we bought all those tickets， right？ So this term is actually。

Independent。Of H。But P2 is the other possibility。 The other explanation。And that says， well。

 N is in the bag。But。呃。And twidddles。Ill roll that in the back。不。re also in the bag。

That satisfy H times n quidddle is equal to Z。Or if you like H times the difference between N and N twiddle。

Is 0。Okay。Have a chat to your neighbor to see if you're understanding me so far。

 this is the most difficult bit of the pinnacle。 So I want to make sure you're with me。

 Have a chat and we'll see if there's any questions。Okay。

 are there any questions about these two contributions to the probability of error。Ever number board。

Okay， so we can fail if end's not in the back， but we can make the probability of that as small as we like by picking。

And large。And being careful with this thing that I'm sort of fudging a little bit。

 which is the size of the typical set， which is 2 to the N H2 of F。Plus， a little bit。

So we'll come back to that， that fudge。 as long as we may N big。

 we can make this plus sort of small in the right sense。Okay。

 so the first term is dealt with just by making an enormous。This second term is much more exciting。

 This is the one that actually depends on H， because if， if I picked some dull H， for example。

1 with all the row identical， then maybe it's much more likely that you'll have identical syndromes coming out。

 You could imagine all sorts of ways in which an H could be bad。

 And it is very easy to make bad codes。😊，Okay， so let's write down this second term。

The actual definition of it。P2 of H is it's a sum overall possible noise vectors。

Subject to them being in the bag。That we bought。Then we wait by the probability of that happening。

 probably getting that noise vector。A thing that counts one。

 if there's another n twiddle in the bag and 0， if not。 Okay。

 and that'll give us the probability error。 So I'll introduce a function called one。

 which is the function， which is one。 if the thing in brackets is true and it's 0 otherwise。So one。

 if there exists an N twiddle， such that N twiddle is not the same as N。

And Twitterddle is in the bag。And H times n minus n twiddle。Is0。对。So this is the function。

 which is one。 if the number of clashes that we've got for the noise vector that actually happens is bigger than or equal to one。

All right， yeah。Okay， if N twiddle， the question was， why does it matter if N twiddles in the bag。

We only have a problem if when we're reaching into the bag and you look at the back of each other。

 when you say， is that the syndrome No， Is that the syndrome。

 Is that the syndrome when you go through all of them， and then you say， oh woo， there it is。

 that must be N。 Now， if that happens twice， you say， woo， woo who。

 then we're screwed because we found two noise vectors that are different from each other。

 So it has to be in the bag。To cause trouble。Okay， because then we don't know what then is。

The assumption we're gonna be making。啊，is。That， yeah。

 the way the decoder works is if you find the syndrome on on the back。Then。

We turn it over and we say， that is the noise vector。 That's my guess。

And we want that to be exactly one ticket that has that syndrome on， on the back。

That will fail if we haven't got the right noise vector， and that's handled by this。

 If we have got the right one in the bag， we will also fail if there's another one in the bag with the same syndrome。

O。Alright， this is a slightly cunning proof， maybe。

 because it's using this notion of the syndrome decoder， which you're maybe not super familiar with。

 But let's， let's see， let's see if this works。 There's another completely different proof of this theorem in the book。

 which is the proof for general channels。 And you can look at that， too。Right。Now。

 this proposition is saying that the number of clashes is bigger and equal to  one。

If you think about that function。That is a function， which as a function of the number of clashes。

Starts out being 0 and then increases when you hit one to the value of one。

 and then it remains one thereafter。 So no matter how many clashes there are， we're screwed。

 which means we get a one out of this expression。 Alright。

 so the function we're talking about as a function of the number of clashes， Well looks like this。

And that has the property。That it is less than or equal to。This function here。

 which is the number of clashes。Okay， so in yellow， I've shown the number of clashes。And in white。日本。

We have the function， long。numberumb of clashes。It is great and equal to one。Why am I laboring this。

 I want you to be clear that the yellow function is bigger than the white function。嗯，可以。Now。

What should we do next。Let's。Useum inequality。And。Let's do a bit of redefining of this。

 So the first thing we'll do is we'll leave it as a sum N， P of N。But I'll rewrite this as。

A sum of propositions， which is going to be the yellow light。So now let's do it in yellow in fact。

 So you can see what it is。I'm going to add up。The sum over all N twidddles。

That are not equal to the noise vector that actually happened。

Subject to the constraints that N twiddle is in the bag。And I'm going to ask， hello， Mr。 Enwiddle。

Is your syndrome the same as the syndrome of the actual noise vector。

 So which is the function H N minus n twiddle。Is equal to 0。Alright。 so I've relaxed this thing。

 I've made it bigger。😊，And I'， I'm now showing that P2 is smaller than this quantity。

 And as long as I can show that this is tiny， Then I've also established that P2 is tiny。

 That's where we're steering。 I'm trying to manipulate P2 into a form where we can say， aha。

 if I now do this and this and this and this， I can make it tiny。😊， yes。It's fine。Yes。

 so this is the number of n twidddles who clash with me。

 It's the number of them because I'm now summing over all n twiddles。 Alright。

 so this is looking at every single one of them。 And there's an enormous number that's two to the N。

 H2 of F of them。 So I've replaced this simple quantity here， which is either 0 or1。

 by a sum of2 to the N H two of F terms。 So there's now a trillion terms。

 And every one of them were saying， is it you do you match， do match， do match。

 And if any of them match， will'll get some ones appearing in here。 Okay。

 so we've just done this relaxation here。😊，No。The next thing we're going to do。

We've made a little bit of progress。 We've perhaps simplified this a little bit。

And still got an H dependence in it。And what we end up。

 we want to end up showing is that we can make this very small。

And it's going be difficult to do that with any particular H。

 So we're going to average over all Hs and show that the average of all the P2s。Is very small， okay。

So we're now going to look at average of P2。And we're gonna average over。All Hs。

 And when I say average over all H's， I just mean literally take the set of all possible binary par to check matrices and pick completely independently at random。

 So every 0 or1 in this matrix is 0 or1 with probability 5050。 Allright。😊。

So the average of all those P2s is the sum overall H。P of H。Sm over Anne。In the bag。Even文。

Salm over and twiddle in the back。And we will not equal to n。

Notice there's no P of n twiddle in here。 There is a P of N。

 This is just how the mathematics is working。And we have 1，4。H of x equals 0。

 where I've defined a new thing here。 X is defined to be n minus n twiddle。Okay。All right。那。

Let's reorder these summations a little bit。We'll take the sum over N。

 the sum over n twiddle outside and put the sum over H on the inside。So have a sum over N。In the bag。

Pment。S over and twiddle。In the bag。But not the same as Anne。Some over H。P of H。1， if。

H times x equals 0， where inside here， x is just by definition。

 the difference between N and N twiddle。Alright， so we're summing over all typical noise vectors weighted by their probability。

 We're summing again， over， typical noise vectors and twiddle， not weighted by their probability。😊。

And then we look at the question。 if you take the difference between those and hit it with the matrix H。

What's the probability， Averaging overall matrices H that you will get 0。

 That's the meaning of this term in here。So， to answer that question。This thing here is。

The probability that。This is all given a particular8 X Now。 We're。

 we're given X because once we've defined n in this sum and n twiddle in this sum。

 we've got ourselves an X。Now， here， this is the probability for that given x， the probability that。

The first row of the matrix times x is equal to 0。 and the second row of the matrix。Is 0。

 And the third row。Of the matrix times x is equal to 0。

 where H is this randomly chosen matrix whose rows are H1。H2。H3。Dot， dot， dot。 And here we have dot。

 dot， dot on all of those asserts。exSo， now we need a little sideshow。

 which is the exercise where we understand this problem。

Forget everything we've just been doing and think about this extremely simple， mathematical question。

If I give you a fixed vector to X， which is non0。It's non zero because， in fact。

 it's the difference between two noise vectors N that are different from each other。

 So that makes it non0。If I give you a fixed vector X， which is non zero， and it's binary。

 and it's got length N。And then if I bring along a single row of this matrix。H。Just one row。

 And if I call its elements， H1， H2， H，3， H 4。What's the probability that the inner product between H and X。

Is0。Habitat。就内吧。And if it helps think about just this special case here that's on the board with。

Vectctors of length，4。Okay。So， the question is。What's the probability that one row of this matrix multiplied by x。

Gives you 0， modulo 2。Any thoughts。So we were picking the H's completely at random by flipping a fair coin。

X is just a fixed vector， which has got some zeros in some places。

And it's got some ones in other places。 So in this special case here， the value。

Of H dot X is actually equal to H2 plus H 3 plus H4。Modulo 2。So let me ask the question another way。

 If I take three fair coins。And I say， we're going get a number。Which is either gonna be odd or even。

 And we're gonna get it by adding up the outcomes of the coin tossses。

 And the coin says one on one side and 0 on the other。The question is， if I add up。

The number of ones。 and find out if it's odd or even。And if each of those coins is fair。 it's 50，50。

And if I add up all three of them， what's the probability I get。An odd number。Okay， yeah。It's 50，50。

 Does that depend on how many coins I added up。No， because if I call tos just one of them。

 it's it's 5050， whether it's odd or even。 And if I give you any number， whether it's odd or even。

 And now I flip another coin。 and I add that to get an odd。 and even number is still 5050。Okay。

 so the answer is。The probability that the top row times x gives you 0。That probability is a half。

And that's true。For any x。嗯，看。For now， the probability that。All of these assertions are true。

 The probability that you。When you've got a given x。

 which is the difference between two noise vectors as it happens。Okay。

 that's the answer to question 1。Now， the question is， if I。Take a fixed X。Just as before。

 and I make all M rows of this matrix， and I make them independently by tossing coins。

What's the probability that the first row times x gives you 0， and the second gives you 0。

 and the third gives you 0。Et cetera。Have a chat your neighbour。X is fixed。

I flip coins to determine whether the top thing comes out order even。

And then I flip coins to determine whether the second one comes out hot or even。 and it's 50，50。

 whether it's hot or even。Flip coins for the next one。 They're all independent of each other。

 So the probability that they all come out even every single row is。Half the power。

Anyone think an alternative answer is true。No， anyone not convinced that half the M is true。

And you're on asleep or shy。Okay， so this is the correct answer。So we've made a lot of progress。

 because suddenly， this has all disappeared。And it's just half to the power M。

And so we can and it all vanishes。 So what's the next slide。 Okay， we don't want that。So。

Average of P2。Of H， averaging overall H。Is the sum over than all N in the bag weighted by P of N。

Some overall n twiddle。That are in the bag。And that are not the same as N。

Then we do the sum motion over H。And this entire quantity here。

 we've just argued is a half to the power M。Which is a number。With no H dependence。

 because we've averaged that out。 And it's got no n dependence and no n twiddle dependence either because it only depended on X。

 And the answer to that question we were just answering didn't depend on X。 So， whosh， we're done。

 Weve suddenly just got ourselves as a number And the number is a half to the M times the number of n twiddleles that are in the bag。

Less warm。Averaged。Over this distribution。 And this thing doesn't have any dependence on n。

 So we can just say the sum overall n in the bag。 Well， that's， that's maximum 1， isn't it。

 So this is less than or equal to1。Times。The number of things in the bag。

 let's round up that1 and say， oh， there's 2 to the，2 to the n times the entropy instead。 all right。

2 to the N。H2 of F。 So the size of the typical set。Plus， a little bit。

So that's the number of things in the bag。And then that multiplies a half。to the powerM。

What have we done， We've used Shannon's malnutrition detection scheme to establish that if you average over absolutely all linear codes。

 the average performance of those codes。The probability of error。

 if you use our slightly deranged syndrome decoder with the large binb full of tickets。

The probability of error is。Probability of error。Is less or equal to P1， which we can make tiny。Plus。

 this other term， which we can't necessarily make tiny。 It depends on what N， H2 of F and M are。

 So we have two to the power。Let's put it downstairs， shall we， Ca then it'll be clear。

What tiny looks like。 So one over2 to the M。Minus。And。H2 of F plus a little bit。O。

And this second term here。This term can be made arbitrarily small。 If what。 Well， it vanishes if。

M is much bigger than N， H2 of F。Reranging， that says， if M over N。Is bigger than H2 of F。

Or rearranging again into terms that we like1 minus M over n。Is less than1 minus H2。Of F。

And I've just run out of board， because that is saying。That this second term here vanishes。哎。

The rate。There's less。Then。The capacity。Because the right。Here's one known M N。

So the capacity of the channel， this particular channel is。1 minus。诶，2。Thus。

 we have proved the noisy channel coding theorem for the binary symmetric channel with a flip probability of F。

 And we did it by using the same dustbin bag that we already used to prove the source coding theorem。

 So we've got two proofs for the price of one。😊，Are there any questions about this proof we've just done。

 And then we can have questions about everything we've done in the first eight lectures， yes。Okay。

 so。Right。So the question is， what was this step from here to here。3。Yeah， alright。 Why is it bigger。

 that hopefully that's gonna be easy。 Let's just make clear what we're doing here。At this point。

 we were saying， I'm worried about the possibility that a noise vector might come along。

 such that there is another noise vector in the bag with the same syndrome。

And the probability of error is the probability that the number of such clashes is either one or  two or three or 4。

Now， that's a very complicated proposition to deal with。 If I tell you。

 I want to know the probability that the number of clashes is either one or two or three or 4。

 And I don't care whether it's  one or  two or three or four。It turns out to be much。

 much easier to say。First， take this ticket out of the bag。

 I want to know what's the probability of clashing with this ticket， then add to that。

 the probability of clashing with this one， Then add the probability of clashing with this one。

 So I take every single ticket and separately work out。

 What's the probability of a clash with this end twiddle。 Then add all of those up。

 And that's much easier because answer your question about just the original N and the N twiddle on this ticket。

 That's a much easier thing。 as we found， we could answer that question。

 Then at least we could do the averaging easily。😊，If we do that， if we say。

 what's the probability of a clash with this one and what's the probability of a clash with this。

 And if we then add all of those up， we're actually over counting the probability of error。

 because errors， which may be rare errors will occur when there is a clash。

 and it could be that clashes come in clumps that when there is a clash with this ticket。

 there's also a clash with this one and this one just one on this one。

 And so adding up the probability of all the individual clashes and adding those together。

 gives you an overestimate of the probability of error because you get only one error when there's a big car crash of lots of them clashing with each other。

😊，So we're deliberately overestimating the true probability of error by。

Taking a simpler thing to compute。There's a standard name for this that I've forgotten of， of the。

 the type of mathematical operation we're doing here。Union bound。 Okay， this is called a union bound。

Alright， so you've got a load of different possibilities that you're worried about。

 And if any of them happens， it's bad news。 What's the probability of bad news happening， Well。

 we're going to work out the probability of bad thing  one happening。

 then work out the probability of bad thing 2。 then work out the probability of bad thing 3 happening and add them all together that will actually overestimate the true probability of bad bad a bad thing happening because they might happen simultaneously。

 Okay， so that's the meaning of this inequality。Any other questions。It's a union band。Right。

 any questions about this proof。Any questions about lectures 1 to 8。

Because we're now essentially done with information theory。

 I've not told you the whole of information theory， but we've done the data compression bit。

 We've done the noisy channel coding bit。And so are there any questions about。

Daate compression or lousy channel coding。OK。法院该日。Second。Okay， so the question is。

 how do these tickets relate to K， which are the bits that the sender gets to choose and M。

 which is the number of constraints， the number of constrained bits that are determined by the code that we're using。

是2。The tickets that we bought。Have hypotheses written on them of what the noise vector might be。

And they all have the property that theyve got lots of zeros and a small number of ones。

Because we know， by typicality。That it's very likely that the actual number of ones will be about N。

 F plus a minus。Square root of。嗯，呢。Time some little multiplier alpha to ensure that we get 99。

999999% probability。 So the number of ones。The looks like that。

How does this relate to what the sender is choosing to send。Well。

 it's completely unrelated because these noise vectors are what get added to the transmission。

 So the transmission itself。Has just the same length。There will be a subset of those bits。

 which conventionally often sit at the left hand side， but don't have to。

 There'll be a subset of them。Numbering K， which are set by the user。 So these will be source bits。

 S1， S 2， S 3， up to S K。And then the remaining ones will be set by the constraints。

So there'll be these M other bits here。T K plus 1 up to T N， which are determined by the constraints。

 This is what what we send。 It has nothing to do with the noise vectors。

 It won't look like any of them。 It's very likely to be a dense vector。 It's up to the user。

 And these ones are very likely to look dense as well。 So this will essentially be 50。

50 ones and  zeros。So that's what gets transmitted。 What's then received is the sum of these two。

Then we hit that with the syndrome operator， which is H。 So you bring along H。 You attack T plus N。

Which is the receive bank。And that gives you Z。And that value of Z is H times T plus H times N。

 which is。H times N。Which is completely independent of tea。So， yes。

 the user was able to choose K of the bits and set them。

 And then the constraints were used to set another M of them。

 But the syndrome doesn't depend at all on what those bits were。 It's completely independent。

Whether we will achieve successful communication on this particular use of the channel。

Will depend on what N is， because our success will be determined by the syndrome decoder being I able to identify N or not。

Whether we succeed or not depends on the syndrome decoder identifying。 and。

 and that has nothing to do with T。 It's completely independent。 Just as with the 74hamming code。

 we have the property that if you flip a bit。Then you can detect that flipped bit。

 And it doesn't matter what the source choice was。Okay， so the 7。

4 hammoning code is the analogy to use here to understand why T doesn't matter at all。If we succeed。

 then we will have identified N， and we can add it back onto T or subtract it So sorry。

 we can subtract it back off R the receive vector and deduce T again。

That's how we actually would recover the transmission。Okay， any more questions。

Thank you for being here。

![](img/199719264367b6848c83a6e735b56ad0_10.png)

![](img/199719264367b6848c83a6e735b56ad0_11.png)