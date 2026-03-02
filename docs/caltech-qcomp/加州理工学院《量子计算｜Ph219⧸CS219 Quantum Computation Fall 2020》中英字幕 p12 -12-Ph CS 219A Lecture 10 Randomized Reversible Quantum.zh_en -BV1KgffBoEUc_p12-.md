# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p12 -12-Ph CS 219A Lecture 10 Randomized Reversible Quantum.zh_en -BV1KgffBoEUc_p12-

![](img/fb116fe076679c79d7d1f68319f8deb2_0.png)

All right， hello there， Quantum friends。Good to see you again， I appreciate your enthusiasm。

And actually， although this is a quantum course last。Lecture。Was kind of on the classical side。

We'll continue in that vein for a little while， because there are elements of the。

Classical theory of computation that we want to lay down so we can build on them as we erect and study the quantum model of computation。

So let's get going。And last time we talked about the classical circuit model of computing。

 we talked about Boolean functions， decision problems， we considered the idea of universal gates。

And the notion of uniform circuit families for the purpose of classifying the computational hardness of a language in the circuit model。

 we talked about the complexity classes， P NPP and CoP。

 we explain the notion of reduction and the related notion of NP completeness。

And today we will continue for a while to talk about classical computing。

I want to introduce the model of randomized computation and reversible classical computation。

 and then we'll be all set to start talking about quantum computing and we will segue into that by the end of this lecture。

We're already almost halfway through the course。We're all eager to talk about quantum computing and that will be the focus from now on for the remaining lectures starting at the end of this one。

So let's talk about randomized computation last time we talked about circuits that compute Boolean functions。

And in randomized computation， I'm going to imagine my computer has access to random numbers。

 There's a random number generator that can be consulted。 So in each step of the computation， we can。

Choose from among more than one possible gate that we could apply。

 we flipped some coins and we decide to apply gate A or gate B or。

Some larger set of possible gates governed by some distribution that we sample from。

And so if we perform a whole circuit in that way， we're really taking a sample from many possible computational paths。

 many possible circuits。That we could have been realized and we sample one in each front of the computation。

 that means even for a fixed input。We're not going to get the same answer every time。Nevertheless。

 the randomized model can be useful if it gives the right answer most of the time。

With some probability greater than one half， I get the right answer and in fact a probability greater than one half by some non zero constant that doesn't depend on the size of the input。

Then although in a given run， I might not be so confident that I'm getting the right answer。

To are the evaluation of some Boolean function or the solution to some decision problem。

I can run multiple times and take a majority vote on the outcomes to decide whether the answer is yes or no。

And if I run a sufficient number of times， it will be unlikely that the majority of the times I got the wrong answer so we can amplify the probability of getting the right answer to something very close to one without having to run a very large number of times。

So let's see a little more quantitatively how that goes。

 So we're going to suppose that when we run a circuit in the randomized model。

 we're going to get the right answer with a probability 1 half plus delta Delta is some positive constant。

And now we're going to run N trials of the computation。

And each time we're going to get a one bit outcome as。When we evaluate a Boolean circuit。

So there are two to the n possible sequences of outcomes that we could get。

 if the outcome is a bit zero or one， we get a zero or one and times there are two to the n possibilities。

And then if we take a majority vote。The majority vote is going to give us the wrong answer only if we got the wrong answer。

 the majority of the time。At least and over two times。嗯。So let's ask， what is the probability？

Of getting the wrong answer altogether n sub w times n sub W W4 wrong in n runs。

 So getting the wrong answer is something that occurs with probability less than one half。

 namely one have minus delta。And that's going to occur。And sub w times。

 if we got the wrong answer and subw times。And the probability of getting the right answer is one half plus delta。

 so if there were a total number of capital n trials then and minus ns sub w is the number of times that we got the right answer。

 so i'm considering one particular sequence。Where I get a zero or one each time。

 and I can assign a probability to that particular sequence。

The way I said here in each case where I got the wrong answer。

 it occurred with probability 1 half minus delta when I got the right answer。

 it occurred with probability 1 half plus delta。But to get the majority wrong。

 I had to have the wrong answer at least and over two times。

 so for any NW which is at least n over two， I can bound this probability of the particular sequence of outcomes。

By 1 he minus delta to the n over 2，1 half plus delta to the n over 2。

Okay because the most likely possibility is that I just barely had a majority wrong answers and to have even more wrong answers when a wrong answer occurs with probability less than one half。

Is less likely than having exactly half of the answers be wrong。

One half minus delta times1 half plus delta。Is just a one quarter minus delta squared。

 So if I take out that4 and I raise it to the power run over 2。

 that gives me a factor of one over2 to the n in front。

And then the one minus delta squared gets raised to the n over2 power。

 and I can observe that1 minus x can be bounded above by。E to the minus x。

And so I can bound this by one over two to the end。E to the minus4 delta squared。

 and that all gets raised to the and over2 power。And that's the probability。

For a particular sequence of getting a sequence of answers in which the wrong answer came up。

The majority of the time or at least half the time。

 the total number of possible sequences is2 to the n。

 so to get the total probability of getting the wrong answer。

 I can just multiply this by2 to the n I'm using the the union bound for probability。

And that means the total probability of getting the wrong answer。

 the one over two to the n gets canceled by the two to the n possible sequences。

 it's just this expression e to the minus2 capital n， delta squared。

So the great thing is that as n increases， that drops like a bomb， it's exponential in n。

And so that in fact， if I will be willing to tolerate。A probability of air epsilon in the majority。

Vote， then it will be good enough to run the computation a number of times capital n。

 such that n is at least one over two delta square times the log of one over epsilon。

That's what it takes。 That's the value of capital N that I need for this probability of having the wrong majority to be less than or equal to epsilon。

But remember， we said that delta is a constant independent of the input size。

 so the number of times I have to run to once a delta has some fixed non-zero value。

 the number of times I have to run to get my acceptably small error or probability epsilon has nothing to do with the size of the input it only has to do with delta and epsilon。

 the probability I'm willing to accept and the probability of being wrong in each run。

 And furthermore it goes logarically logarithmically in one over epsilon。 So that's pretty good。

 I can make epsilon really small with a modest number of trials。

 So this is called the churn off bound on the probability and one way of thinking about it。

 as you know that you know， if I flip a bias coin many times the probability of getting a certain fraction heads or tails can be well approximated by a。

GauianAnd that Gaussian becomes narrower and narrower as I increase the number of trials。

And eventually it becomes so narrow that having the majority wrong is way off on the tail of the Gaussian。

 there's very little probability weight on that tail。

 so the probability of having the majority wrong if we have a sufficient number of trials gets small very quickly。

So I don't really care very much from the point of view of the scaling of the complexity of getting the right answer。

 if I have some randomized circuit with some specified size， let's say polynomial。In the input size。

 then I just have to run if as long as Delta is a non zero constant。

Some constant number of times to get a very small probability of being wrong。

 and Delta can be any of positive constant for that purpose。

It only affects the prefactor of the polynomial， how many times I have to run。

 that itll be the circuit size times some constant that depends on deelta。

And so since Dlta doesn't really matter very much， we often by convention say that our goal is to achieve a delta of 16。

 that means a probability of getting the right answer， which is at least two thirds。

A probability of getting the wrong answer， which is no larger than one third。So with that in mind。

 we'll sometimes say that a randomized uniform circuit family decides a language if for x in the language。

 the probability of acceptance is it's not going to be one now because it's a randomized model。

 but if it's greater than or equal to two- thirdhirds for any x in the language we're happy as long as we can't fool the circuit family。

 the probability of when x is not in the language of acceptance it willll be less than or equal to one third。

 and then we'll be able to amplify our success probability to whatever level we file。

 we find acceptable。And so now we can define a model which is analogous to。

 or I should say we can define a complexity class， which is the analog of P P is the polynomial time class in the case of deterministic circuits which compute functions。

Here we're talking about randomized circuits which sample from a distribution of outcomes。

 but the analog of P is called BP， it stands for Boed error， probabilistic， polynomial time。

 and it means the languages that can be decided by polynomial size， uniform。

 randomized circuit families。Now it's clear that BPP， what we can do with randomized circuits。

 what we can solve efficiently if we have access to a random number generator contains P。

 we always have the option of not consulting the randomness at all。

 not using that random number generator that corresponds to deterministic computation。

 it is encompassed by BPP。嗯m。And whether BPP is equal to P is actually an open question。

Generally believed on the basis of evidence I'm not going to go into that in fact。

 BPP is equal to P having access to randomness does not allow us to solve efficiently problems that we couldn't solve efficiently without access to randomness。

 but that's never been proved。Now， just as in the case of P。

 where we noted there was a larger class or potentially larger class。

 very very likely larger class called NP， those are the problems that we could。

Verify the solution efficiently if someone was kind enough to give us a suitable witness or certificate。

And there's an analog of that for randomized computation， it's called Merlin Arthur。

 the computation class is called Merlin Arthur， that means that you can efficiently check the answer with the randomized computation the name comes from the Arthurian legend in which Arthur was mentored by the powerful magician Merlin。

 so we imagine that the all powerful Merlin。Provides the witness provides the proof。That Arthur。

 although a mere mortal， is able to efficiently check。

Which allows him to verify that X is in the language， but he needed Merlin's help。

But with Merlin's help， he was able to do the verification efficiently。

Oh it's the same story as P and NPP except now for randomized computation。

 we call the classes BPP and MA so just to say that in parallel to the way we said it when we talked about NP last time。

We say that a language is in MA Merlin Arthur。If and only if there's a randomized verifier。

 the randomized verifier is a uniform circuit family that it takes as input both。

X and where we're trying to determine whether x is in the language and the witness y。And this。

Randomized verifier is supposed to have the property that when x is in the language。

 then there is some witness that Merlin can provide for us such that when we had the witness。

 the probability of acceptance of x and the witness y is at least two thirds。

And if x is not in the language， Merlin can't fool us。

 there isn't any witness that Merlin could give us such that the randomized verifier would accept with probability less than one third when x is not in the language okay so it's clear just as was the case for P and NP that MA contains BPPP。

 remember NP contains P because。In the case of P， Arthur doesn't need Merlin's help at all if you want to use the Merlin Arthur。

Ay in the case of deterministic computation， we don't need the witness。

 we can just do the computation ourselves to see whether x is in the language and that's a special case of the scenario in which a witness is provided same thing here if a problem is in BPP。

 we don't need help from Merlin we don't need the witness we can just do the randomized computation ourselves。

To。To see whether x is in the language or not， and furthermore。

 just as it's clear that BPPP contains P because P is the special case where we don't consult the randomness at all。

 so it is that MA contains NPp because。And P is just the special case of MA in which the witness is deterministic in which the verifier doesn't need to consult the randomness at all。

Now I'd like to talk about another。Model of classical computation， which will be helpful。

As a step towards the quantum model of computation that we're leading up to。

 but it's also interesting in its own right， as we'll discuss。To introduce it， I'd like to。嗯。

Point out。An important physics principle， which is called Land hours principle。

And it can be stated this way， it's named after Ralph Landauer， who formulated it in the 1960s。

That if we want to erase a bit。Add。Some non zero temperature T。 we have to do work。Quantitatively。

 the amount of work that we need to do to erase one bit is Boltzman's constant K。

Times the temperature times the log of two the base of the logarithm depends on our convention for。嗯。

Defining， well， it doesn't matter， let's just say it's loggged2。And so why is this so？Well。

 I'll give you a example of a memory where we can see in rather physical terms。

That we do need to do work。To achieve erasure， and I will assert that this principle is much more general and gives a hand waving argument in support of that contention。

So let's think about our memory this way， we want to store one bit in a memory okay。

 so we want to have a state， we want to have a system with two states okay。

 and we want to be able to put the system in either one of the two states。To。

Distinguish the two possible values of the bit。And so I'm going to take。Just one molecule。

You can think of this as a gas， but it's a very minimal gas， it just has one particle。

 which is inside the box， but there's a partition in the box。

And I can put the molecule either on the right side or the left side of the partition。

 and when it's on the right side of the partition as it is here。

 then we say we've stored the value zero in the memory。

 and when it's on the left side of the partition as it is here。

 then we've stored the value one in the memory。So now what does it mean to erase what it means to erase is that I need to come along and carry out some process which no matter whether the initial stored value of the bit is zero or one。

 will map the bit to a fixed value to some standard value， let's say zero。

 let's say the goal of erasure is to take the memory。

 whether it stores a zero or one and map that to zero。Now。

 this process should not make use of any information about。The value of the stored bit。

 I don't want to process that ase is one way when the bit is one and ase is another way when the bit is0。

Why don't I want that well， because if I were to carry out that procedure I would need to know whether the bit is zero or one and that knowledge would have to be recorded somewhere so I would leave a record behind whether it was zero or one and that would mean I hadn't really accomplished the task right？

I mean， if I look at the memory and I see it's zero and then I mark that it's a zero or I see that it's a one so I mark that it's a one and then I apply procedure zero。

In the case where the bit is zero and procedure one， in the case where the bit is1。

 then well look I've left behind the mark that indicated which procedure to carry out that's no good。

 I need a way of mapping the bit to zero without knowledge of whether it's a zero or a one to begin with。

So here's a way we could imagine doing that， so we have this one molecule gas in the box。

With a partition is either on the left or the right。

 the first thing we do is we remove the partition。 and now the molecule is able to bounce around。

 Oup either the right side or the left side of the box。😊。

But now I turned the wall on the left of the box into a movable piston。

And I carefully compress the gas。Pushing the partition back to the middle。

And now that I know for sure the molecule is on the right side and then I lock the partition in place there and I put the cover on the box again。

 and now although I don't know for sure whether the bit was zero or one to begin with after this process is carried out。

 I do know for sure that the bit has been met to zero。

But here's the thing that isothermal compression of the gas is going to cost some work。

There's a thermodynamic reason for that， the first law of thermodynamics。

It says that the work I need to do to reduce the entropy。

In an isothermal process where the molecule stays in equilibrium with a surrounding environment。

 which is at temperature T。Is at least in a reversible process。

The temperature times the change in the entropy。And it would be even more work if the process were irreversible。

So what's the change in the entropy， well， you can think of the entropy as the logarithm of the number of possible microstates of the system。

 in this case， our one molecule gas。And the one molecule now can either be on the left side or the right side。

嗯。So to begin with and at the end， it only is on the right side。

 so the amount of phase space available to it， the number of possible states it could be in has been cut in half when the volume of the box。

Goes from two to one in suitable units。 So that corresponds to a change in the log of the number of possible states。

Which is log two， a change in the entropy of Boltzman's constant K times log2。

 which means that the work that we have to do is Kt log2 and that's what Landauer said。

So the key point here is that if we're going to erase， we have to somehow compress。

The phase space compress the space of possible states that our memory could be in。

 that the system could be in， and that requires a dissipated process to squeeze down the phase space。

According to fundamental thermodynamic principles， it's necessary when that dissipation occurs that there be a flow of heat from the memory to its environment。

Where does the energy corresponding to that heat come from。

 it has to come from work that we do on the system。

So in order to have that entropy of K log2 flow out of the memory when we。

Compress its space of possible states by a factor of two， we have to do an amount of work。

 which is at least temperature times the change in the entropy or KT log2。

So it's really a very general principle。Erasure necessarily has a thermodynamic cost。

You need work to erase， you got to run a battery or something to erase bits。Well。

 you can also apply this principle of land hours。Two gates in a circuit。

Because the gates in a circuit that we discussed last time。

 like an an gate or an ore gate map two input bits to one output bit。 that reduces phase space。

 It reduces the number of possible states that the system can be in， and therefore。

 land hours of land hours principle applies。 It must cause some work。To perform the gate。

 because in an effect of raceses， it compresses the space of possible states。

 let's say it's the and gate， for example。Well the endgate takes three possible inputs， 00，0。

1 and 10 all to the same output zero。And it takes the input 11 to the output one。

So if the output is one， then we know for sure what the initial state was before the gate。

 it had to be 11。But if the output is 0， we don't know there are three possibilities that it could have been 0。

0，0，1 or 1，0， and the action of the gate has destroyed that information。

 that information about the initial state。Has been lost by the execution of the gate so we say the gate is logically irreversible。

 you can run it forward， but you can't run it backward because when the output is0。

 you can't go back in time and say whether the initial state was 0001 or 10 so if we imagine that the possible input bits the four possibility001001 and11 all occur equal probably then average over that distribution the amount of information that will be lost。

I can write as three quarters times the log of three。Three quarters。

Because three quarters of the time with probably three quarters will be in one of the three initial states for which the logically irreversible operation occurs and log three because the。

There are three possible initial states which got shrunk to just one。

And so that means on average's about， well， it's about 1。2 bits。

So Landauuer argued that just like erasure， when we do a gate in a computation。

 there's an unavoidable thermodynamic cost， somebody's got to pay a power bill when we do a gate because gates are logically irreversible。

Now you could ask， is that why I need a battery in my laptop。

 is that why I can feel the heat being dissipated when I put my computer on my lap？Well， not really。

The numbers don't quite work out。 let's say we're talking about room temperature your laptop may run a little hotter than that。

 but close enough。So at 300 K。Kt is about four times 10 to the minus 21 joules。

And let's say you've got a pretty fancy CPU， it's got a few billion transistors and it's got a a clock speed of a few gigahHtz Well even if we imagine that those transistors are switching every clock cycle and all 3 billion transistors are simultaneously in play。

 which isn't quite true， but it's enough for giving us a bound on the number of bit operations。

 so that would be 3 billion times 3 billion operations in。

In a second which is 10 to the 19 bid operations per second。 So what would Landauer say he would say。

 okay， well， then you're going to have to have a power cost or a number a number of jos per second。

Which is 10 to the 19 times KT。And that turns out to be about 40 millijoules per second or in other words。

 40 millwatts。A power and actually your laptop。Is using more energy than that maybe it's running at 100 watts or something like that。

 so land hours thermodynamic cost doesn't really account for all the power that's being dissipated in the CPU in your laptop in fact a lot of energy is being wasted。

Now， heat dissipation really is a constraint on computing。

Technology today and you have to worry a lot about keeping a CPU cool。

 you don't want it to melt if you put together a big parallel computing system like a supercomputer。

 then you need a lot of cooling to keep things from running too hot that's。Certainly the case。

 there's a lot of thermodynamics involved in state of the art computing。

 but not really because of land hours principle at least not yet maybe someday will reach this fundamental limitation and we won't be able to reduce the。

The the power bill further， at least that's what Landauer imagined when he proposed his principle except。

He was wrong。When he said that computing has a thermodynamic cost necessarily。

 he was right about erasure， erasing information really is necessarily logically irreversible it compresses phase space and that means it costs energy。

 it takes work to ase， but computation doesn't have to involve dissipation。

 it's possible to run a computer reversibly so that you can run the computation forward in time and then keep the full output of all the bits and then you can run it backward because it's really computing a invertible function。

 okay and so I want to convince you that that's the case that it's possible to compute reversibly and therefore evade the thermodynamic cost that Landauer was talking about。

Now， just because it's reversible doesn't mean that we can't do a computation。

 what I want to argue is that a reversible computer would be able to simulate a Boolean circuit efficiently。

 so the circuit we talked about last time where we had a universal gate set of and or and not we'd be able to simulate that even if we had reversible hardware and without。

Much of a price to be paid in the cost of additional gates。So in principle。

 we really can compute for free。It's erasure that's hard and computing is easy。

 a little bit counterintuitive because。I forget stuff all the time and it seems easy to do whereas cogitating seems like hard work。

 but at least from a fundamental point of view， it's the erasure that's hard。

 not the processing of information。So what a reversible computer is doing is it's computing an invertible function。

😊，So it's not going to take n bits to one bit like a Boolean circuit does。

 it's going to take n bits to end bits。 it has to be a one to one function， right。

 otherwise it wouldn't be invertible so there can't be two different values of the input that get mapped to the same output because that would be logically irreversible。

If it's one to one， that means there are two to the n possible inputs and there must be two to the n possible outputs as well。

 so really what the invertible computation does taking n bits to end bits you can think of it as just a permutation of all of the n bit strings there are two to the NN bit strings two to the un possible inputs。

 there are two to the n possible outputs and what the computation does is it determines。

For each one of the two of the impossible inputs， which of the two of the impossible outputs it gets mapped to。

So if I want to count all of the reversible functions。

 all of the invertible functions from n bits to n bits。

 it's just a question of counting permutations of length and strings。

 so those are permutations of two to the n objects okay there are a lot of those。

Two to the n factorial， and if I use Sterling's approximation， I can approximate that pretty well。

By M factorial is well approximated by M over e raised to the power M。That's what I'm doing here。

 except M is2 to the n。So with n bits going to n bits， the number of permutations。

 therefore the number of invertible functions is approximated well by2 to the n divided by e race to the power 2 to the n。

that's really a lot of invertible functions。But actually。

 it's a tiny fraction of all of the functions， not surprisingly。

 the invertible ones are rather special。 It's a small fraction of all of the functions that take n bits to end bits。

 Remember， we said the number of Boolean functions。😊，Was two to the two to the n。

And if we're taking end bits。Of input to n bits of output。

 you can think of that as n Boolean functions， so the number of those is the number of Boolean functions raised to the end of power。

And so that's actually two to the n to the two to the n。

The number of invertible functions is smaller than that by  one over e raised to the power2 to the n。

And that's a very large power of one over E。 so that's what I meant when I said that it's a tiny fraction of all of them。

 but there's still lots and lots and lots。Of invertible functions taking end bits to end bits once and is no longer very small。

Now， it's also clear that if I want to encode a Boolean function， it's possible to do so。With a。

Invertible function， here's one way of doing it。There's some function that takes。

Let's call it F that takes an n bit input to a one bit output。Well。

 I can consider this invertible function， I call it F Tilde here。Which has。And n plus one。Bit input。

The input consists of x， which is the input to the Boolean function F of x。

 and then one additional bit， which I've called Y here。

 and what F Tilde does is it preserves the value of x in that input and bit register。And then it。

Essentially， it flips the extra bit which had the initial value y if f of x is equal to1 and it doesn't flip it if F of x is equal to zero。

 so I wrote that as the x or of y and F of x and x or is just the same thing as addition modo2。

Or in other words， if f of x is 1， it flips the value y and if F of x is0。

 it doesn't flip the value of y。And so the information about。What F of x does is encoded there。

 if I set y equal to zero initially， then what f tilde would do is it wouldn't affect the input register at all。

 but it would print out the value of the Boolean function of of x in the extra output bit。

The N plus first bit。Okay。So we can ask， are there universal reversible gates？So what does that mean。

 well， it means the same thing as in the circuit model we talked about before except this time for invertible functions。

 we'd like to know whether there are some simple operations。

That when composed together allow us to construct， to build up any invertible function we might be interested in that takes n bits to end bits for any value of n。

Well， in fact， there are。Universal， reversible gates in that sense。But and now。

The gates with two bits of input won't do。 that's not enough。 Of course， if they're invertible gates。

 they take two input bits to two output bits， So I call them two to two bit gates here。AndIn fact。

 there are not universal two to two bit gates which are invertible。

 which allow me to construct any invertible function I have to go to a three bit input there are。

Three bit to three bit invertible gates that we can use to build circuits that allow us to evaluate。

Any invertible function of n bits to end bits。So how do we see two isn't enough？

Well suppose we consider the linear operations of two bits to two bits。

 that's what I've indicated here， so all of these numbers。X， Y， x prime y， prime， A B。

 they're all binary， so the numbers are either zero or one。And M is a matrix。

 the addition is understood as modo 2。So there are four possibilities for AB， which I listed here。

 00，01，10 and 11， so what the plus AB does is depending on the values B and B it either you know flips the or not the first bit and the second bit。

And then I want to choose the matrix M so that it too is binary so that its entries are 1 and0。

 so when the matrix M x on the input bits x and y， it gives me output bits if I evaluate the matrix arithmetic modo2。

 which would binary either zero or 1。And if this is going to describe an invertible operation。

 then M has to be an invertible matrix， and what it means to be invertible here is that it can be inverted by another binary matrix。

Whose entries are zero and one？And in fact， it's not hard to make a list。

Of all of the binary matrices with entries 0 and1， which can be inverted by binary matrices。

 and here's the list。 some of them are familiar ones like the identity and the thing we called polyx before。

 And there are also these other guys， all of which have a determinant one or minus one and trace。

Either。Either one or two， and anyway， they all have the property they can be inverted by the matrices from this list。

 so they're invertible in that sense。And the thing to notice is how many of these there are。

 these are the linear operations taking two bits to two bits where linear means。Linear。

 but with respect not to real numbers or complex numbers， but the finite field， Z2， the binary field。

嗯。I'm doing linear algebra。On a vector space where。

The vectors are binary strings and we can multiply them either by zero。

 which of course maps them to zero or by one， which leaves them alone。

And that's the vector space I'm talking about， and because it can be expressed in this linear form。

 this is a linear map。When we do an addition moduleular2， but since we have six of these matrices m。

And we have four choices for the additive term A and B。

 therere altogether six times four 24 possible linear transformations。

And that exhausts all of the invertible two to two gates， right because？The number of them is。

Two to the two factorial。Or of four factorial， and that's 24。

 So all of the invertible gates are linear。In the case where we have two input bits and two output bits。

 but that won't do if I want to do universal computation and in particular。

 if I wanted to simulate Boolean circuits，I can't multiply if all I have is linearity， I mean。

 I can multiply by one， but that doesn't do anything。And I can't make an an gate。

 I can't make an ore gate， we need those things for universal computation and we just don't have them if we're stuck with these linear operations。

If I want nonlinear operations， I have to go beyond two input bits。

And here's one which will do the job， it's called the Toffley gate。

 or sometimes we call it the controlled controlled knot。

Here's the notation that I'm going to use for it。And what is controlled controlled not mean there are three input bits。

 X， Y and z can take values either zero or one。And if x is equal to one and y is equal to one。

Then and only then the value of z flips。for any other choice of the inputs x and y。

 nothing happens okay， but if x and y are both equal to1。

 then the third register flips and that's what I've indicated here as the X or or addition modo2 of z and the product x times y。

Which is going to be one if x and y are both one and zero otherwise。

That's what a tough the gate does。And you see it does have the nonlinearity that we'd like to realize in end gate because of this multiplication of x times y if we're able to fix input bits to be either zero or one。

 then it's easy to see that I can use this top the gate Tly Tom Tfly is a guy。

 he had got a gate named after him。Quite a distinction to have a gate named after you。

If I fix the input bits appropriately， I can use the tatheli to as simulate。

A not operation or an and operation。嗯。If we。嗯。Said x and y equal to1。

Then and you know we just enter constants for x and y。

 then of course what it does is it applies a no to the third register， it flips it， okay。

 it adds one to it。嗯。And if I said z initially equal to zero。And then whatever x and y are。

 after the topfo gate X， the product X Y will appear in the third register。

 that's just the same thing as the and of x and Y。So if you're willing to accept some junk that you have to discard this three to three gate。

Simulate the two to one gate， the an gate。If I fix c equals zero， then for any inputs x and y。

 I can read out in the third register the and of x and y。

 and then I have this superflluuous x and y sitting around。

 but I can throw those in the garbage can if I want to。And of course， as you know。

 if I can do a no and I can do an n， that's enough for doing an or just because of this Boolean identity that the or of x and y is the same thing as taking the knot of n x。

And not why。So if I can use it thoughtful to get。And not。

 then I can simulate all of the gates in the universal set that we talked about last time。

Incidentally， another thing that's worth noting。Is that if I set x equal to1。

 then the toply gate acting on the second two registers。

Becomes a useful linear operation taking two bits to two bits。

 it's what we call the controlled nod gate。Or Senidegate。

Wwhichch is just an abbreviation for controlled not remember what the topfooli does is it flips the third bit if x and y are both equal to1。

 well， if I fix x to be equal to one， then of course that means that if y is equal to1 and only then the value of z is going to flip。

So with x equal to1， then this operation on y and z is what we call a control nu or C nu K。

Notice in particular that if I set x equal to1 and z equal to zero， then what the taphali does。

Is that it just copies the value of y in the third register so y is the input bit in the second register and when x is equal to 1 and z is equal to zero after the top of the x I have y in both the second register and the third register in other words that's a copy operation。

So I've explained to you how we can simulate the logically irreversible gates in the gates that we talked about last time using a totly if we can fix input bits。

In that sense， the Tli is a universal gate， one can say more that if you want to build up any permutation of end bit strings then just a Toly gate is enough if you can fix input bits。

 and that's discussed in some detail in the lecture notes but I'm not going to take the time to go through it in class I encourage you to read that but at least I've convinced you that our reversible machine that does only toffly gates and can fix constant bits is able to simulate the circuit model that we talked about last time。

Now that might not be enough to make Landauer happy because he would say， yeah。

 but look at what you're doing every time you use a toly gate to simulate an an gate。

 you're generating junk because you got this X and Y that。You didn't get rid of。

And so unless you have some way of refreshing or erasing bits。

 you're going to be stuck with those values of x and Y in your memory and so every time you do an endgate you're going to have to load up your memory with another two bitsworth of stored information and eventually you're going to run out of memory and you won't be able to go on with the computation unless you erase the memory aha but erasing the memory does have a thermodynamic cost that does require dissipation so Landauer might say well all you've done is you've delayed the thermodynamic power bill that you have to pay for doing all of this computing。

Because eventually you're going to have to erase or else you're going to run out of memory。

But actually that's not quite right， Charlie Bennet。

 I think was the first to point this out in the 1980s。Maybe it was the 70s， Yeah。

 I guess it was the 70s。We don't need to do the erasure because we can do the following thing。

We can simulate。Whatever circuit you're interested in， which uses the gate set and or a not。

Using our toffly gates by fixing bits， like I said。

 and that will indeed start to clog up our memory after a while。

But after we finish with the computation we can then copy the answer。

 I showed you how we if we can fix inputs， we can use the toply gate to copy so I can take the answer bit。

 make a copy of it and then I can run the whole computation backwards because it's a reversible computation I just use the inverses of all the gates and run the circuit in the opposite order and that will undo all of the computing that we did。

 and so if I started out with a memory register that was set all the zeros。

 then it gets all clogged up when I do the computation going forward but it gets completely unclogged when I do the computation going backward and at the end it's set to all zeros again and I can use that memory again the next time I want to compute。

So we had to pay a little price， we had to run the computation twice once forward and once backward to avoid the thermodynamic costs of erasure。

 but that's not such a big deal we just made the computation twice as long in terms of the number of gates the gate complexity and actually you don't really need to make it twice as long there's a discussion in the chapter five lecture notes of how。

Through a recursive procedure in which you run backwards some somerouts of the computation。

 in the course of doing the full computation， you can reduce the memory requirement。And。

That's kind of a fun thing， but I'm not going to go through it。In class。So。

It's a nice thing to know that processing information does not in principle carry a thermodynamic cost。

And what it means is that。The reversible computing model has the same computational power as the circuit model we talked about last time because it can simulate it efficiently。

And so if we were stuck with only reversible computation。

 our conclusion about what problems are hard and what problems are easy。

 the classification of problems we can solve with polynomial size uniform circuit families and the ones we can'。

 well， it would be the same classification， whether we use the reversible model or the original circuit model。

 which has logically irreversible gates。Okay， so now let's talk about the quantum model。

I'll just introduce it briefly and then we'll get into its properties in more details last time。

So now we're going to talk about a computational model which we think really is more powerful than the classical circuit model。

 and we don't really know how to prove that for first principles。

But we wouldn't be teaching this course if we didn't believe that quantum computers can do certain things efficiently that we can't do efficiently with classical computers and that's captured mathematically by saying that there are algorithms that we can run。

In the quantum model， which have circuit sizes that are polynomial uniform circuit families in the quantum model。

 which are polynomial size， which can solve problems。Decide languages。

That we can't efficiently solve within the classical circuit model。

So what are the ingredients in the quantum circuit model？

Well I talked about this some already in the first lecture， but let me remind you again。

 so first of all there's the arena in which the computation takes place quite different than in the classical model we're not processing bit strings anymore we are processing vectors in the Hilbert space we could consider mixed states but we don't have to so we can imagine that we have a pure state。

In a Hilbert space of N qubits and the computer processes that state。

 and in the end it's going to read out an answer， which is classical by making a measurement。

So the important thing is。That。There's some notion。Oh。Decomposing this really。

 really big Hilbert space in which that state vector lives。

 which describes the state of our computer into small subsystems， which we usually take。To be qubits。

 so in the classical model， there's a kind of locality assumption there too。

Because we represent the information in terms of bits and the gates which we consider to be simple operations just act on pairs of bits or three bits at a time。

 something like that， so they're pretty simple to execute in hardware。

 but in the end we put them together to build up these very complicated operations that act on many input bits。

And。We have to have a notion like that to talk about complexity because if we want to say some computations are hard and some are easy。

 while we have to have in mind that those operations that just act on a couple of bits are the ones that are easy。

 but when we put them together to do operations on many bits that can be hard and we need a similar notion to define complexity in the quantum model。

And so it's not enough just to say that there's a Hilbert space which has dimension two to the end。

 which is the arena for the computation， we also need some preferred decomposition into small subsystems that's needed to define the model。

And so what's the physics of that Well， again， it has to do with the fact that we think。

Physics is local， in the sense。That it's hard to do operations which act collectively on many qubits at once。

 so qubits are encoded in hardware in lots of different possible ways。They could be carried， say。

 by single atoms or single electrons or single photons and other more complicated ways as well。

 we talked about that a little bit。In the first lecture。But if you have a system of many atoms。

 for example， you can encode the qubits in the atoms and it's relatively simple for you to manipulate one atom at a time or two atoms at a time。

 much more complicated to do some collective operation on many atoms at once。

 and so that's very important for talking about complexity when we say a quantum computation is easier or hard。

 we're talking about how many of those simple operations we have to put together to do the computation。

And I said physics is local， I meant it's much easier to act on a single atom or two atoms than to act on many atoms at once。

Now we're going to have to initialize our computer。That is。

 we'll have to be able to set all our qubits to some standard initial st。And in particular。

 I would like that initial state to be a product state。

Highly entangled states might in general be complex to prepare using our quantum platform。Yeah。

But product states not so much， I just have to set each one of the qubits to some standard value by convention。

 I can say that I set each one of them to be zero so like if I have n atoms in some laboratory device。

I could initialize by setting each one of those atoms to the same microscopic state。

 let's say everyone is in its ground state。That would be the all zero state and so I'm taking it for granted in my definition of the computational model that that's not such a hard thing to do。

In hardware， you can think of it as。Cooling that we have to take generally if you have a bunch of atoms。

 let's say in an ion trap or something like that they're not all going to be in the ground state。

 they're going to have some distribution of internal states and to initialize I'd like to cool them all down to withdraw entropy so they can I can put all the atoms in a particular state。

 put the system of n atoms in a particular state。And I want to say that's not so hard to do in the lab and you know it might be challenging in practice I've got to optically pump the atoms or something like that。

 but physicists have learned how to do those things and because we're just preparing a product state we'll take it to be something that's。

Simple from the point of view of the computational model。

Now we're going to have a set of universal gates。Like we did in the classical circuit model。

 but things are a little bit different now。Each one of the gates。

Is going to be a unitary transformation？It's not enough to have unitary transformations that act on just one qubit because we couldn't build up entanglement that way。

 the product state would stay a product state， so in order to be able to access entangled states we're going to have to have unitary transformations that act on at least two qubits。

At a time， but actually that is enough for universality， what does it mean to be universal。

 it means that I can take。Gates in my universal gates set and by composing them together in a circuit。

I can build up an approximation which is arbitrarily good to any unitary transformation of interest acting on the Nqubits。

Putting aside for the moment， the question of how complex is it， how many gates do I need？

Universality means that。In principle， if I put together enough gates。

 I can get as close as I want to any desired unitary in that two to the m dimensional Hilbert space。

That's the analog of in the circuit model that we could compute any。Boolean function。

 there are lots and lots of them， so it typically is going to take really big circuits to do it。

 But once we have a universal set of gates， that's enough to compute any Boolean function。

 or in the reversible model， we can get any permutation of the endbit strings by putting together our universal gates like toply gates in the。

In the reversible model。Now， one thing you might wonder about。Is。In the model。

 we usually assume that the set of- and this isn't really necessarily that essential。

 but we usually assume。That we have a finite set of possible universal gates to choose from。

And in fact， even acting on just a single qubit or two qubits。the unitaries form a continuum。

 so there are really an infinite number of possible unitaries and you might have said well why can't I do any single cuid unitary I want or any two cuid unitary I want。

 Why do I have to pick them from a finite alphabet。Well。

 it's a good question in the lab you might be able to do essentially any single qubit unitary with about。

About equal difficulty。But the idea of specifying a finite instruction set。

 a finite number of possible gates is。That we have to somehow reconfigure our hardware if we want to do a different kind of gig。

And we'd like to。Avoid doing that if we can。 So we only want to have a finite number of。

Hardware primitives that we need to call in order to build up our unitary transformation of interest rather than selecting them from a continuum。

Now this idea really becomes highly relevant when one gets to the issue of quantum error correction and fault tolerant quantum computing because as I think I've briefly mentioned in previous lectures。

And fault tolerant quantum computing， when you're acting on encoded information protected by some quantum error correcting code。

 typically there really are just a discrete set of transformations that are easy to do。

That preserve the code and perform some non trivial logical operation on the code without exposing the encoded information to。

Damaging errors。 and so there it really is important to stick with some a finite set of universal gates and we'll consider that to be part of our model。

I'm going to take it for granted that there's a classical computer in the wings。

That I'm going to use say to design a quantum circuit if I have some problem that I want to solve。

 I don't want to hide complexity in the difficulty of finding the circuit。

 we encountered the same issue in the classical model remember that's why I introduced this at least informally the idea of uniform circuit families。

 we want to use a similar idea in in the quantum model that it isn't computationally difficult to find the quantum circuit that solves a problem for。

Any number of input bits rather than having to start from scratch every time you change the。

The size of the input。So if I really wanted to formalize that。

 I'd have to go beyond the circuit model and use something like a Turing machine model of computation。

 which I'd rather not talk about， but we're really not in worse shape in the quantum model than we are in the classical circuit model as far as that goes and so I'm going to imagine as I did in the classical circuit model that the task of deciding what sequence of gates to perform to solve the problem has been farmed out to some classical computer。

 and we want that classical computer to be able to solve that part of the task efficiently in order for us to say that a problem can be solved efficiently by the quantum computer。

And。In the end。The let's say I'm trying to solve the decision problem or I'm trying to decide whether an input is in a language or not in a language。

I'm going to have to output classical information， I don't want you to deliver to me some state of and qubits in some vast Hilbert space。

 I want bits and that means for the final readout we're going to want to measure。

In some basis and I don't want to hide complexity in the measurements that I perform to perform a collective measurement on many qubits at once that might be highly complex I want to do something that。

Is physically reasonable， something that would be simple to do in hardware， like read out。

A single qubit in a standard basis。 That's something that， you know。

 the physicists have learned how to do。 Let's say it's an atom。

 It's either in its ground state or it's in some particular excited state。

 You can interrogate the atom。With a laser， and。If it's in one state， it will stay dark。

 if it's in the other state， it will fluoresce and you can see its shining and so it's pretty easy to read out an atom。

Efficiently and pretty quickly。And so we're going to consider that to be part of the model that it's not difficult it just sort of counts as a single step in the computation to read out a single qubit。

ACoive measurement or many qubits may be complex but a measurement on a single qubit will be easy。

 so really we want to consider simple measurements at the end for the same reason that we want to consider simple initial states。

 we don't want to hide complexity in the preparation at that initial state or in the complexity of that that final measurement。

So that's it。 These are the steps in a quantum model of computation， I guess one remark I could make。

Is that。You might want to have the option。Of measuring a qubit and then conditioned on the outcome deciding what。

Operation to apply in the next step， in particular。

 if you wanted to simulate the randomized classical model， you might want to do that。

Because you can simulate randomized computation。Using the quantum model。

 if say you prepare aqubit in the state zero and then you perform a gate which rotates it。

To an eigenstate of the poly operator X like a uniform superpositionion of 0 and1 and then measuring the01 basis。

ll that'll generate a random bit。And you might want to consult randomness in the middle of the computation。

 but really there's no loss of generality it is encompassed by the model I've described。呃。

Even if we do all the measurements at the end， because it just。

Mathematical trick I can model the task of performing a computation partway through。

 performing a measurement and then doing further operations conditioned on the measurement。

 what I can imagine instead is that there's some quantum operation which is conditioned on the state of one of the qubits。

And I don't read out that qubit until much later， but in the end。

 the effect on the final result will be the same as if I measured it midway through and then perform a conditional operation。

 so I'm just saying there's no loss of generality that we need to worry about if we delay all the measurements to the end。

As long as you're allowed to measure more than one qubit at the end and I'm going to allow in the model for me to measure any subset of the qubits that I want and including possibly all of them。

Now we think。That。Well， there's no question。That a randomized classical computer can simulate this model。

 there isn't anything in this model that classical computers can't do。

The gates are just matrices acting on vectors in a Hilbert space。

 and classical computers know how to multiply matrices。

 and they know how to compute how matrices act。On vectors， the issue is。

Efficiency that the Hilbert space is so huge， it grows exponentially。

With the number of qubits or the matrices we have to deal with have an exponential size in n。

And you know the number of qubits is going to scale like the size of the input to the problem。

 so as we scale up the input。We're going to have an exponentially growing Hilbert space in that as far as we know。

Though we don't know how to prove it from first principles。

 we don't know how to simulate what's going on without an exponential resource explosion either we don't。

 as I'll discuss next time， we don't really need an exponentially large memory to store all these matrices。

But or to store this vector in a huge Hilbert space， but if we don't store it。

 then it's going to cost us in terms of the time complexity， the algorithm。

 we're still going to need a very large number of gates to simulate what the quantum computer is doing with the classical computer。

So as far as what functions are computable in the Tring machine sense。嗯。The story is not change。

By quantum circuits as opposed to classical ones or if you like quantum Tring machines as opposed to classical Tring machines。

 the conclusion about what functions are computable is the same。

But the conclusion about what functions are efficiently computable with uniform circuit families of polynomial size。

 scaling polynomially with the input size， that we think is a different story with quantum circuits than with classical ones。

Now。There's an analog to the class BPP， the randomized class， which we talked about not long ago。

Whi is the quantum version， and it's called BQP， meaning bounded error quantum polynomial time。

 and BQP consists of the languages that can be decided by polynomial size uniform quantum circuit families。

 where these circuits are built out of the universal gates。In the quantum model。嗯。

And so essentially what they captures is the problems that you can efficiently solve with the quantum computer。

 that's what BQP means。It obviously contains BPP for the reason I said a minute ago that within the quantum model。

 we can simulate。Random number generators， we can you prepare。

And een state a poly operatorator x and then measuring the z basis and the outcome will be a random bit。

But we think BQP is bigger than BPP。Because we think quantum really does give us additional。

Computational power。We hope it's larger。 otherwise， I'm really wasting your time with this class。

 We think quantum computers are。More powerful than classical ones， even randomized classical ones。

 though we don't know how to prove it。Now we can also define the quantum analog。Of MA。

 it's called QmaA or Quaum Merlin Arthur。And it's pretty much the same story as MA well except for two differences。

The verifier that Arthur uses。To check the proof that Merlin provides is now a quantum circuit。

So for a problem in QMA， we want it to be an efficient quantum circuit。

 so that's one way in which QMA goes beyond MA。But there's a second way。

We allow the witness to be a quantum state。Merlin doesn't just send some classical bits to Arthur in。

QM he's allowed to send a quantum state and Arthur can use that quantum state as part of the input to his efficient quantum computation for the purpose of verifying the proof So if you like a melin sends a classical proof。

In M A， which Arthur then verifies with his randomized classical computer， but in QMA。

 Merlin can send a quantum proof to Arthur， and Arthur verifies it using his efficient quantum computer。

So it's clear that QM contains MA。But we think it's larger。

Just as we think that BQP is larger than BP， that the quantum model is more powerful than the classical model。

 even when it comes to verifying a proof。There's a kind of intermediate class we can also define。

Which is sometimes called QcmaA quantumum Class Merlin， Arthur， we can ask。

What can we verify efficiently with a quantum computer if the witness is required to be classical。

 so Merlin in QCmaA sends a classical proof to Arthur and Arthur uses a quantum computer to somehow verify what Merlin is saying？

So this gives us a sequence of nested computational models。BP is contained in BQP。

Because BP PP is the special case。In which。We are。Just use the quantum model to generate randomness and the rest of the computation is classical。

And then BQP is contained in QCmaA BQP is just the special case。In which。

Classical message sent by Merlin isn't used and QCMA is contained in QMA because in QMA Merlin provides a quantum state as a witness。

 but he could send a quantum state which is just some computational basis state so in effect he'd be sending classical information。

 so that's a special case。Of a quantum witness would be a classical witness。

So there are a lot of questions about the quantum model。

 which I want to talk more about in the next couple of lectures。

Haven't explained very precisely the idea of universal quantum gate sets。

 so I want to say more about that and give you some examples of universal quantum gate sets。

 which will give us a better feel。For what it means to have universality in the quantum setting。And。

There's a nuance which sort of goes beyond what we had to worry about in the classical circuit model。

Because。The unitary transformations actually form a continuum。

 I can't necessarily with any finite circuit exactly simulate one universal gates set with another in the quantum model I can do it approximately。

 and so we're going to need to understand a little better what the cost is。

 how large a circuit you need to accurately simulate one set of universal quantum gates using another set of universal quantum gates。

Another thing is that because the unitary transformations form a continuum。

We may have an ideal model in which we have a finite alphabet of possible universal gates。

 and we can imagine building circuits out of those。

 but you'll never be able to capture that model precisely in hardware because we can't exactly hit any unitary transformation right on the nose。

 there will always be some small error。 So we have to understand how large an error we can tolerate gate by gate in order to still get the right answer for a computation with some sufficiently high probability if it turns out that we need some unreasonably accurate approximation to the ideal model with the gates we can realize in hardware that would be bad news。

 Another thing we can do is we can ask well。For a generic unitary transformation acting on Ncuupbits。

 how large a quantum circuit do we really need to get a good approximation to that unitary transformation。

 you remember we asked the analogous question about Boolean functions last time and that's where we concluded that for most Boolean functions you actually need an exponential size circuit in order to evaluate the function。

Not surprisingly， there's a similar statement in the case of quantum computing。For an arbitrary。

Or generic。Unitary transformation acting on Nqubits。

 acting on the vast two to the n dimensionional Hilbert space of N qubits to get a good approximation to that unitary using the gates in our universal set gates that act on just say two qubits at a time or a few qubits at a time。

 and that's going to require an exponentially large circuit to get a good approximation and it's really for the same reason that we discussed in the classical circuit case。

That the in that case， the problem was。That。There were just so many boolean functions that we needed to have many。

 many circuits to cover them all。🤧Excuse me， and in the。Quantum model。

 that's kind of a similar story if you have N qubits。

There's such a huge space of unitary transformations acting on the two to the n dimensional Hilbert space that to have a good approximation to them all is going to require many。

 many circuits typically will need circuits of exponential size to get close enough so it's kind of a humbling thing。

As in the case of classical computation， there are so many boolean functions。

 but the ones that will ever be able to compute in you know。

 the history of life in the universe is going to be a tiny， tiny fraction。Of all of them once。

 you know， and gets to be of。Modest size。 And it's the same with quantum computing that Hilbert space is incredibly vast。

 And for a pretty small number of qubits， you know， maybe just a few hundred。Um。

 it's just inconceivable that we'll ever be able to explore more than a tiny， tiny， tiny little nook。

In the huge hilbert space with computations that the quantum scientists and engineers will ever be able to realize even in their wildest dreams。

So there's a vast。Quantum world out there and the part that we can explore is just a tiny portion and the rest of it will always be essentially unknowable。

All right， so see these are some of the things that we're going to want to discuss in the next lecture and the one beyond。

 and then we'll be ready to talk about some applications and examples of quantum algorithms and the types of speedups that we can realize relative to classical computing using quantum circuits。

But I think that's going to be it for today， thanks for listening， thanks for coming。



![](img/fb116fe076679c79d7d1f68319f8deb2_2.png)

And。I'll be seeing you again in a couple of days， I hope。For more quantum fun。

 so be well and see you then。拜e拜。